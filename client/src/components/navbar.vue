<template>
  <div>
      <nav class="navbar navbar-expand-lg navbar-dark bg-success">
        <a class="navbar-brand" href="#">Kanban</a>
        <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarNav" aria-controls="navbarNav" aria-expanded="false" aria-label="Toggle navigation">
          <span class="navbar-toggler-icon"></span>
        </button>
        <div class="collapse navbar-collapse" id="navbarNav">
          <ul class="navbar-nav">
            <li class="nav-item active" v-if="isLogin">
              <a class="nav-link" href="#" @click.prevent="toHome" >Home <span class="sr-only">(current)</span></a>
            </li>
            <li class="nav-item" v-if="!isLogin">
              <a @click.prevent="toLogin" class="nav-link" href="#">Login</a>
            </li>
            <li class="nav-item" v-if="!isLogin">
              <a @click.prevent="toRegister" class="nav-link" href="#">Register</a>
            </li>
            <li class="nav-item" v-if="isLogin">
              <a @click.prevent="logout" class="nav-link" href="#">Logout</a>
            </li>
          </ul>
        </div>
      </nav>
  </div>
</template>

<script>
export default {
    name:'Navbar',
       
    methods: {
        logout() {
            isLogin: false
            this.$emit('logout')
        },
        toRegister() {
            this.$emit('toRegister')
        },
        toLogin(){
            this.$emit('toLogin')
        },
        toHome() {
          this.$emit('toHome')
        }
    },
    props: ['isLogin']
       

}
</script>

<style>

</style>