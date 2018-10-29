<template>
  <div id="app">
    <h2>{{msg}}</h2>
    <h1>{{obj.name}}</h1>
    <ul>
    	<li v-for="item in list">
    		{{item.name}}:{{item.age}},
    	</li>
   </ul>
   	<hr />
    	<br />
    	<br />
    	<br />
    <ul>
    	<li v-for="item in list1">
    		{{item.hobby}}
    		<ol>
    			<li v-for="opt in item.kind">
    				{{opt.title}}
    			</li>
    		</ol>
    	</li>
    </ul>
    <hr />
    <br />
    <br />
    <input type="text" ref='userInfo' />
    <button @click="getRef">获取ref</button>
    <hr />
    <br />
    <br />
    <button @click="getEvebt($event)" data-aid='div'>Event事件</button>
    <div ref='box'>div</div>
  </div>
</template>

<script>
export default {
  data () {//业务逻辑里面定义的数据
    return {
      msg: '您好！Vue',
      obj:{name:'丁浩宸'},
      list:[{name:'儿子',age:'2岁'},{name:'爸爸',age:'30岁'},{name:'妈妈',age:'30岁'}],
      list1:[
      	{
      		hobby:'吃零食',
      		kind:[{title:'果冻'},{title:'蛋糕'},{title:'糖果'},{title:'水果'}]
      	},
      	{
      		hobby:'玩手机',
      		kind:[{title:'球赛'},{title:'小说'},{title:'电视'},{title:'游戏'}]
      	},
      	{
      		hobby:'玩手机',
      		kind:[{title:'游戏'},{title:'电影'},{title:'电视'},{title:'小说'}]
      	}
      ]
    }
  },
  methods:{
  	getRef(){
  		alert(this.$refs.userInfo.value)
  	},
  	getEvebt(e){
  		e.srcElement.style.background='red';
  		console.log(e.srcElement.dataset.aid)
  	}
  }
}
</script>

<style lang="scss">

</style>
