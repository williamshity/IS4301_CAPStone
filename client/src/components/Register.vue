<template>
<div>
<h1>Register</h1>
  <input type="email" name="email" placeholder="email" v-model="email">
  <input type="password" name="password" placeholder="password" v-model="password">
  <button @click="register">Register</button>
</div>
</template>

<script>
import AuthenticationService from '@/services/AuthenticationService'
export default {
  name: 'HelloWorld',
  data () {
    return {
      email: 'abc',
      password: '123'
    }
  },
  methods: {
    async register () {
      console.log(this.email + '/' + this.password + '/')
      const response = await AuthenticationService.register({
        email: this.email,
        password: this.password
      })
      console.log(response.data)
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
