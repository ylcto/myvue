<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/>
    <h1>{{ name }}</h1>
    <span v-if="age <= 5">儿童</span>
    <span v-else-if="age >= 6 && age <= 18">少年</span>
    <span v-else>成年</span>
    <table>
      <tr>
        <td>编号</td>
        <td>姓名</td>
        <td>年龄</td>
      </tr>
      <tr v-for="student in student" :key="student">
        <td>{{student.sid}}</td>
        <td>{{student.name}}</td>
        <td>{{student.age}}</td>
      </tr>
    </table>
    <br>
    按钮事件<br>
    <button @click="showInfo(name)">点击出奇迹</button>
  </div>
</template>

<script>
export default {
  name: 'App',
  data(){
    return{
      name:'李老师',
      age:15,
      student:[
        {sid:1,name:'王晓花',age:18},
        {sid:2,name:'王晓华',age:19},
        {sid:3,name:'王晓花',age:18},
        {sid:4,name:'王晓花',age:18},
      ]
    }
  },
  methods:{
    showInfo(num){
      alert("*******,点我出奇迹!"+num)
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
table {
  margin: auto;
  border-collapse: collapse;
  border: solid 1px;
}
</style>
