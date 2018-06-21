<template>
  <div class="hello">
    <h1>Welcome to Rambo' Vue.js App</h1>
    <ul>用户名：<input ref="userName" type="text" placeholder="请输入用户名" v-model="msg" ></ul>
    <ul>密&nbsp;&nbsp;&nbsp;&nbsp;码：<input type="password" placeholder="请输入密码" v-model="msg1"></ul>
    <ul>用户名输入值：{{ msg }}</ul>
    <ul>密&nbsp;&nbsp;&nbsp;&nbsp;码输入值：{{ msg1 }}</ul>
    <button type="button" @click="myClick" >登录</button>
  </div>
</template>
<script>
export default {
  name: 'HelloWorld',
  data () {
    return {
      msg: null,
      msg1: null
    }
  },
  methods: {
    myClick: function () {
      if (this.msg != null && this.msg1 != null) {
        alert('用户名为：' + this.msg + '       密码为：' + this.msg1)
        console.log(this.msg)
      } else {
        alert('用户名或密码不可空！')
      }
    }
  },
  watch: {
    'msg': function (val, oldval) {
      if (val === 'admin') {
        alert('管理员不可登陆！')
      }
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}
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
