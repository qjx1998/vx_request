<template>
	<view class="content">
		11232waerew
		{{ mess }}
	</view>
</template>

<script>
	import http from '../../utils/http.js';
	export default{
		data(){
			return{
				mess: '',
			    msg: 'hhh'
			}
		},
		onLoad() {
			var that = this
			http.getArticleList().then(list=>{
				 uni.hideLoading();
				// console.log(list)
				that.mess = list.data.banner[0].name
				// 此处的list就是config.js中，wx.request封装中resolve的值，
                //即list===res.data.data的值；
			})
			
			// 如果需要向服务器传值，可以这样写
			// http.getArticleList({
			// 	open:"value"
			// }).then(list=>{
			// 	console.log(list)
			// })
			
		}
	}
</script>

<style>
  
</style>
