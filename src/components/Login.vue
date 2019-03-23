<template>
<div class="container">
    <x-header :right-options="{showMore: False}"  :left-options="{showBack: ture}">Login</x-header>
  <x-input title="手机号" mask="999 9999 9999"  :max="13"   is-type="china-mobile"></x-input>
  <x-input title="密码" :max="13" type="password" v-model="password" ></x-input>
  <x-button @click.native="Login">登录</x-button>
</div>
</template>

<script>
import { XButton, XInput, XHeader, AlertModule, Alert } from 'vux'

export default {
  name: 'HelloWorld',
  data () {
    return {
      password: '',
      msg: 'Welcome to Your Vue.js App'
    }
  },
  methods: {
    Login () {
      if (this.password === '123456') {
        this.$router.push('/')
      } else {
        AlertModule.show({
          title: '登录失败',
          content: '请重新登陆！'
        })
      }
    }
  },
  HelloFromVux: {
    goBack () {
      this.$router.push('/HelloFromVux')
    }
  },
  components: {
    XButton,
    XInput,
    XHeader,
    Alert
  }
}
</script>

  

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>