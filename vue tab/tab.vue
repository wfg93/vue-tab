<template>

  <div class="da">
    <div class="b b1" v-for="(item,index) of nst" :key="index"
         v-bind:class="{active:(indexs == index)}" @click="a(index)">{{item.name }}</div>

    <ul>
      <li v-for="(item,index) of list" :key="index" v-if="indexs == index">{{item.name}}</li>
    </ul>
  </div>
</template>

<script>
    export default {
        name: "tab",
      data() {
        return {
          list:[
            {name:"内容1"},
            {name:"内容2"},
            {name:"内容3"}
          ],
          nst:[
            {name:"标题1"},
            {name:"标题2"},
            {name:"标题3"}

          ],
          indexs:0,
        }
      },
      methods: {


        a(str){
          this.indexs =str
        },
    }
</script>

<style scoped>
  .b{
    width: 100px;
    height: 40px;
    border: solid 1px blueviolet;
    float: left;
  }

  ul{
    width: 308px;
    height: 308px;
    border: solid 1px black;
    float: left;
    position: relative;

  }
  ul>li{
    width: 300px;
    height: 300px;
    border: solid 1px burlywood;
    float: left;
    position: absolute;
    margin: 0 auto;
    text-align: center;
    line-height: 100px;
    font-size: 30px;
  }
  ul>li:nth-child(1){
    background: darkorange;
  }
  ul>li:nth-child(2){
    background: crimson;
  }
  ul>li:nth-child(3){
    background: cyan;
  }
  .da{
    width: 400px;
    height:310px;
  }
  .active {
    background-color: red
  }
</style>
