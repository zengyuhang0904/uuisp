<!-- 首页 -->
<template>
	<div class="main">
		<div class="insert-warp">
			<div class="main-warp">
				<div class="insert">
				<div class="main-inster-header">
						<div class="mih-hot-tec" @click="hotTechnology">热门技术</div>
						<div class="mih-hot-act" @click="hotActive">热门活动</div>
						<div class="mih-hot-cms" @click="hotCms">热门资讯</div>
				</div>
				<div class="contanter">
					<div class="hot-mas" v-show="showOne">
						<div class="ht-msg" v-for="item in hotTechnologyMsg">
							&nbsp;· {{item.title}}
							<div class="particular-ht-msg" @click="toTechnologyContant">
								<h3>{{item.title}}</h3>
								<p>{{item.msg}}</p>
							</div>
						</div>	
					</div>
					<div class="hot-mas" v-show="showTwo">
						<div class="ht-msg" v-for="item in hotActiveMsg">
							&nbsp;· {{item.title}}
							<div class="particular-ht-msg" @click="toActivityContent">
								<h3>{{item.title}}</h3>
								<p>{{item.msg}}</p>
							</div>
						</div>	
					</div>
					<div class="hot-mas" v-show="showThree">
						<div class="ht-msg" v-for="item in hotCmsMsg" @click="toMessageContent">
							&nbsp;· {{item.title}}
							<div class="particular-ht-msg">
								<h3>{{item.title}}</h3>
								<p>{{item.msg}}</p>
							</div>
						</div>	
					</div>
				</div>
				<div class="insert-footer">
					<div v-show="showOne">
						<i class="fa fa-hand-o-right"></i>
						<span class="insert-footer-name">2099</span>
						<span class="insert-footer-text">项优质技术项目正在寻求合作>></span>
					</div>
					<div v-show="showTwo">
						<i class="fa fa-hand-o-right"></i>
						<span class="insert-footer-name">6</span>
						<span class="insert-footer-text">项行业活动正在报名>></span>
					</div>
					<div v-show="showThree">
						<i class="fa fa-hand-o-right"></i>
						<span class="insert-footer-text">查看更多</span>
					</div>
					
				</div>
			</div>
			</div>
		</div>
		<!-- <div class="message">
		</div> -->
		<div class="nav">
			<ul>
				<li @click="toTechnology">
					<div class="left">
						<div class="title">
							找技术
						</div>
						<p class="text">
							2000+成熟技术项目 
						</p>
					</div>
					<div class="right">
						<i class="fa fa-bars"></i>
					</div>
				</li>
				<li @click="toThinkTank">
					<div class="left">
						<div class="title">
							问专家
						</div>
						<p class="text">
							10000+深度合作专家
						</p>
					</div>
					<div class="right">
						<i class="fa fa-bars"></i>
					</div>
				</li>
				<li @click="toActivity">
					<div class="left">
						<div class="title">
							报活动
						</div>
						<p class="text">
							10000+行业精英共同交流
						</p>
					</div>
					<div class="right">
						<i class="fa fa-bars"></i>
					</div>
				</li>
				<li @click="toMessage">
					<div class="left">
						<div class="title">
							学创新
						</div>
						<p class="text">
							探讨企业创新发展
						</p>
					</div>
					<div class="right">
						<i class="fa fa-bars"></i>
					</div>
				</li>
			</ul>
		</div>
		<div class="content">
			<div class="head">
				<h1>汇聚全球技术 助力企业升级</h1>
				<p>2000+成熟技术项目正在推广中</p>
				<div class="content-nav">
					<ul>
						<li class="list-nav active-nav" @click="changeListNav(1)"><span>化学化工</span></li><i>/</i>
						<li class="list-nav" @click="changeListNav(2)"><span>能源电力</span></li><i>/</i>
						<li class="list-nav" @click="changeListNav(3)"><span>环境工程</span></li><i>/</i>
						<li class="list-nav" @click="changeListNav(4)"><span>材料科技</span></li><i>/</i>
						<li class="list-nav" @click="changeListNav(5)"><span>生农医药</span></li><i>/</i>
						<li class="list-nav" @click="changeListNav(6)"><span>机械电子</span></li><i>/</i>
						<li class="list-nav" @click="changeListNav(7)"><span>全部></span></li>
					</ul>
				</div>
			</div>
			<div class="body">
					<div class="product" v-for="item in product" @click="toTechnologyContant">
						<div class="shade">
							<div class="tel">
								<i class="fa fa-phone"></i>&nbsp;联系技术方
							</div>
							<div class="use">
								{{item.use}}
							</div>
							<div class="read">
								<div class="readtime">{{item.readtime}}</div>
								<div class="infotime">{{item.infotime}}</div>
							</div>
						</div>
						<img :src="item.image" alt="">
						<div class="wape">
							<div class="presentation">
							<h3>{{item.title}}</h3>
							<p>{{item.description}}</p>
						</div>
						<div class="product-message">
							<div class="site">{{item.site}}</div>
							<div class="stage">{{item.stage}}</div>
						</div>
					</div>
						</div>
			</div>
			<div class="footer">
				<div class="foot-text" @click="toTechnology">
					查看更多化学化工技术
				</div>
			</div>
		</div>
		<div class="content bk-color-ccc">
			<div class="head">
				<h1>行业顶尖专家 资深技术顾问</h1>
				<p>10000+合作技术方 更有全网专家信息可检索</p>
				<div class="content-nav">
					<ul>
						<li class="list-nav active-nav" @click="changeListNav(8)"><span>医药科学</span></li><i>/</i>
						<li class="list-nav" @click="changeListNav(9)"><span>化学化工</span></li><i>/</i>
						<li class="list-nav" @click="changeListNav(10)"><span>工程技术</span></li><i>/</i>
						<li class="list-nav" @click="changeListNav(11)"><span>农业科学</span></li>
					</ul>
				</div>
			</div>
			<div class="body">
				<div class="counselor" v-for="item in counselor" @click="toThinkTankContent">
					<div class="shade-counselor">
						<div class="msg">{{item.msg}}</div>
						<div class="particulars">
							查看详情&nbsp;&nbsp;&nbsp;<i class="fa fa-arrow-circle-o-right"></i>
						</div>
					</div>
					<div class="face">
						<img :src="item.face" alt="">
					</div>
					<h3 class="name">{{item.name}}</h3>
					<p class="position">{{item.position}}</p>
					<div class="direction">
						<span v-for="i in item.direction">{{i}}</span>
					</div>
				</div>
			</div>
			<div class="footer">
				<div class="foot-text">
					查看更多医药科学专家
				</div>
			</div>
		</div>
		<div class="content">
			<div class="head">
				<h1>行业热门活动 技术交流盛会</h1>
				<div class="content-nav">
					<ul>
						<li class="list-nav active-nav" @click="changeListNav(12)"><span>化学化工</span></li><i>/</i>
						<li class="list-nav" @click="changeListNav(13)"><span>能源电力</span></li><i>/</i>
						<li class="list-nav" @click="changeListNav(14)"><span>环境工程</span></li><i>/</i>
						<li class="list-nav" @click="changeListNav(15)"><span>材料科技</span></li><i>/</i>
						<li class="list-nav" @click="changeListNav(16)"><span>生农医药</span></li><i>/</i>
						<li class="list-nav" @click="changeListNav(17)"><span>机械电子</span></li><i>/</i>
						<li class="list-nav" @click="changeListNav(18)">全部></li>
					</ul>
				</div>
			</div>
			<div class="main-bk bk-color-ccc">
				<div class="main-warp">
				<div class="body-three">
				<div class="active" @click="toActivity">
					<div class="active-msg">
						<div class="active-msg-img">
							<i class="fa fa-share-alt"></i>
						</div>
						<div class="active-msg-text">社群交流</div>
					</div>
					<div class="new-active">查看最新活动</div>
				</div>
				<div class="active">
					<div class="active-msg">
						<div class="active-msg-img">
							<i class="fa fa-home"></i>
						</div>
						<div class="active-msg-text">行业展会</div>
					</div>
					<div class="new-active">查看最新活动</div>
				</div>
				<div class="active">
					<div class="active-msg">
						<div class="active-msg-img">
							<i class="fa fa-comments-o"></i>
						</div>
						<div class="active-msg-text">会议论坛</div>
					</div>
					<div class="new-active">查看最新活动</div>
				</div>
				<div class="active">
					<div class="active-msg">
						<div class="active-msg-img">
							<i class="fa fa-coffee"></i>
						</div>
						<div class="active-msg-text">圆桌沙龙</div>
					</div>
					<div class="new-active">查看最新活动</div>
				</div>
				<div class="active">
					<div class="active-msg">
						<div class="active-msg-img">
							<i class="fa fa-users"></i>
						</div>
						<div class="active-msg-text">会员活动</div>
					</div>
					<div class="new-active">查看最新活动</div>
				</div>
			</div>
			</div>
			</div>
		</div>
		<div class="content">
			<div class="head">
				<h1>闯创新之道 登浪潮之巅</h1>
				<p>解读企业技术创新的成功案例，分享技术创新的经验</p>
			</div>
			<div class="body">
				<div class="innovate" v-for="item in innovate">
					<div class="innovate-msg" @click="toMessageContent">
						<div class="innovate-img">
							<img :src="item.img" alt="">
						</div>
						<div class="innovate-title">
							{{item.title}}
						</div>
					</div>
					<div class="innovate-link">
						<div><a href="">{{item.linkOne}}</a></div>
						<div><a href="">{{item .linkTwo}}</a></div>
					</div>
				</div>
			</div>
			<div class="footer">
				<div class="foot-text">
					查看更多文章
				</div>
			</div>
		</div>
		<div class="content">
			<div class="head">
				<h1>成功案例</h1>
				<p>技术创新，您也可以</p>
			</div>
			<div class="body">
				<div class="ss-warp">
					<div class="success-carousel">
						<ul>
							<li>
								<img src="https://maikeji.cn/images/index/cases/mold.jpg" alt="">
							</li>
							<li>
								<img src="https://maikeji.cn/images/index/cases/voc.jpg" alt="">
							</li>
							<li>
								<img src="https://maikeji.cn/images/index/cases/gene.jpg" alt="">
							</li>
							<li>
								<img src="https://maikeji.cn/images/index/cases/qingdao.jpg" alt="">
							</li>
							<li>
								<img src="https://maikeji.cn/images/index/cases/environment.jpg" alt="">
							</li>
						</ul>
					</div>
				</div>
				
			</div>
		</div>
	</div>
</template>
<script>
  export default {
    data(){
      return {
      	showOne:true,
      	showTwo:false,
      	showThree:false,
      	hotTechnologyMsg:[{
      		title:"可多次脱模的高性价比橡胶轮胎脱模剂",
      		msg:"轮胎硫化、金属模具、硫化成型、多次脱模、胶囊"
      	},{
      		title:"重金属污染耕地修复用重金属稳定剂",
      		msg:"聚谷氨酸、重金属稳定、生物硅、吸附材料、耕地修复"
      	},{
      		title:"有机硅助剂－流平剂",
      		msg:null
      	},{
      		title:"【设备齐全】光伏电池检测服务",
      		msg:"光伏电池、检测服务"
      	}],
      	hotActiveMsg:[{
      		title:"与资本零距离｜创合汇“商学院好项目”第十期路演会",
      		msg:"上海·徐汇 2018.12.09-2018.12.09"
      	},{
      		title:"【讲座】吴晓波带您解读《避免败局》",
      		msg:"上海 2018.12.11-2018.12.13"
      	},{
      		title:"第二届平湖市科技企业投融资对接会",
      		msg:"浙江·平湖 2018.12.01-2018.12.31"
      	},{
      		title:"让技术与市场来一场真正的对话丨迈科技公益大讲堂",
      		msg:"迈科技微信群 2018.07.01-2018.12.31"
      	}],
      	hotCmsMsg:[{
      		title:"12月3日，山西省领导一行人来访迈科技，双方通过交流、了解，达成初步合作意向。",
      		msg:"12月3日，山西省领导一行人来访迈科技，双方通过交流、了解，达成初步合作意向。"
      	},{
      		title:"全球创业周丨技术转移+互联网模式初露数据力量，帮助技术“倾听”市场",
      		msg:"感谢你们一路相伴，一路相助，见证迈科技的成长！"
      	},{
      		title:"四川丨迈科技受邀第二期四川省技术经纪人培训会嘉宾",
      		msg:"助力四川技术转移，专业科技服务以四川为中心辐射整个西南地区。"
      	},{
      		title:"高效！“自助”技术对接，达成合作仅用2天！",
      		msg:"徐州某企业通过迈科技平台联系技术方自主对接成功，目前双方正就建厂、引进新设备等事宜展开合作。"
      	}],
        product:[{
        	image:"http://test.uuisp.cn/FileUpLoad/FileDownLoadLogo?ProcessID=255dd153-dd4e-4ed9-b41d-9e5dfd5de292&ProcessName=Logo",
        	title:"人民路隧道",
        	description:"人民路隧道为东西走向，西起...",
        	site:"上海市",
        	stage:"地下交通/地下道路",
        	use:"人民路隧道为东西走向，西起黄浦区淮海东路...",
        	readtime:"建成",
        	infotime:"3090m"
        },{
        	image:"http://test.uuisp.cn/FileUpLoad/FileDownLoadLogo?ProcessName=Logo&ProcessID=6dc3b762-931f-4e70-8b33-8e6994e3c248",
        	title:"深圳万科云城智能立体车库",
        	description:"深圳万科云城智能立体车库项...",
        	site:"广东省",
        	stage:"城市停车/智能立体停车",
        	use:"深圳万科云城智能立体车库项目位于深圳市留",
        	readtime:"工程项目",
        	infotime:null
        },{
        	image:"http://test.uuisp.cn/FileUpLoad/FileDownLoadLogo?ProcessID=260293cd-1cbd-4825-90e7-b3a8b081805a&ProcessName=Logo",
        	title:"重庆八一隧道",
        	description:"重庆八一隧道位于重庆市渝中...",
        	site:"重庆市",
        	stage:"地下工程技术/非开挖技术",
        	use:"重庆八一隧道位于重庆市渝中区，为双向6车道...",
        	readtime:"建成",
        	infotime:"1261m"
        },{
        	image:"http://test.uuisp.cn/FileUpLoad/FileDownLoadLogo?ProcessID=9c9a9a16-e029-4140-8c26-0345020e5eee&ProcessName=Logo",
        	title:"鸿恩寺隧道",
        	description:"鸿恩寺隧道位于重庆市江北区...",
        	site:"重庆市",
        	stage:"地下交通/地下道路",
        	use:"鸿恩寺隧道位于重庆市江北区，是连接嘉华大...",
        	readtime:"建成",
        	infotime:null
        }],
        counselor:[{
        	face:"https://res4.maikeji.cn/FlcdTlvZyfwZe8gLMBqMPwTagWoa",
        	name:"施仲衡",
        	position:"中国工程院院士、高级工程师（教授级）",
        	direction:["轨道交通"],
        	msg:"中国地铁工程咨询公司"
        },{
        	face:"https://res4.maikeji.cn/Fjfipb1pUJxqzNm12bdiE-ZDx4HO",
        	name:"钱七虎",
        	position:"中国工程院院士",
        	direction:["防护工程","岩土工程"],
        	msg:"中国工程院"
        },{
        	face:"https://res4.maikeji.cn/Fs88q36P3SlCS025FiNIOK9_sAqg",
        	name:"俞明健",
        	position:"高级工程师（教授级",
        	direction:["地下空间","道路交通"],
        	msg:"上海市政工程设计研究总院（集团）有限公司"
        },{
        	face:"https://res4.maikeji.cn/Fn6QnLSS8ORdQdT3C4eMC2ngB6NW",
        	name:"陈志龙",
        	position:"教授",
        	direction:["地下空间与地下工程"],
        	msg:"解放军理工大学"
        }],
        innovate:[{
        	img:"https://res4.maikeji.cn/FmJJBPl68Mh6pCle96rBjJS2fbTo",
        	title:"媒体聚焦 | 上海市政总院：专业服务平台助力创新发展",
        	linkOne:"交通拥堵停车难、雨洪内涝“城市看海”、管线事故“拉链路”",
        	linkTwo:"一系列影响市民生活的“城市病”也随之而来，而地上“问题”"
        },{
        	img:"https://res4.maikeji.cn/Fmwe-h9Ou9eeL9p4AOe2c-NOC3WA",
        	title:"地下空间 | 杭州将新增500万平方米地下空间",
        	linkOne:" 本文转载自“钱江晚报”   △龚子皓/制图",
        	linkTwo:"差不多再过两三年，大家去杭州武林商圈，不出地面就可以去往各个商场"
        },{
        	img:"https://res4.maikeji.cn/FuPlYHkO97XfT-yZ0RRM2XroY8sq",
        	title:"综合管廊 | 城市地下综合管廊发展前景探讨",
        	linkOne:"科技部三定方案发布，成立成果转化与区域创...",
        	linkTwo:"  城市地下综合管廊是指在城市地下用于集中敷设电力等市政管线的公共隧道"
        },{
        	img:"https://res4.maikeji.cn/FuEqbaMMVc_b6S1EwRdwnSHMW20C",
        	title:"智慧停车 | “停车难，停车贵” VS 智慧停车，你看好吗？",
        	linkOne:"“停车难，难于上青天。”",
        	linkTwo:"“去吃饭找不到停车位。”"
        }]
      };
    },
    methods: {
    	// 技术路由
    	toTechnology(){
    		this.$router.push('/technology')
    	},
    	toTechnologyContant(){
    		this.$router.push('/technology/content')
    	},
    	// 专家路由
    	toThinkTank(){
      	this.$router.push('/thinkTank')
    	},
    	toThinkTankContent(){
      	this.$router.push('/thinkTank/content')
    	},
    	// 活动路由
    	toActivity(){
	      this.$router.push('/activity')
    	},
    	toActivityContent(){
	      this.$router.push('/activity/content')
    	},
    	// 资讯路由
    	toMessage(){
	      this.$router.push('/message')
    	},
    	toMessageContent(){
	      this.$router.push('/message/content')
    	},
		  // 列表导航点击样式
    	changeListNav(n){
	    	$(".list-nav").eq(n-1).addClass("active-nav").siblings().removeClass("active-nav");
	    },
     hotTechnology(){
     	this.showOne = true;
     	this.showTwo = false;
     	this.showThree = false;
     	this.mainInsterNav();
     },
     hotActive(){
     	this.showOne = false;
     	this.showTwo = true;
     	this.showThree = false;
     	this.mainInsterNav();
     },
     hotCms(){
     	this.showOne = false;
     	this.showTwo = false;
     	this.showThree = true;
     	this.mainInsterNav();
     },
     // '插入'导航点击样式
	    mainInsterNav(){
	     	let on = {"border-bottom":"2px solid #fff","font-weight":"700"};
	     	let off = {"border-bottom":"none","font-weight":"500"};
	     	if(this.showOne){
	     		$('.mih-hot-tec').eq(0).css(on)
	     		$('.mih-hot-act').eq(0).css(off)
	     		$('.mih-hot-cms').eq(0).css(off)
	     	}else if(this.showTwo){
	     		$('.mih-hot-tec').eq(0).css(off)
	     		$('.mih-hot-act').eq(0).css(on)
	     		$('.mih-hot-cms').eq(0).css(off)
	     	}else{
	     		$('.mih-hot-tec').eq(0).css(off)
	     		$('.mih-hot-act').eq(0).css(off)
	     		$('.mih-hot-cms').eq(0).css(on)
	     	}
		  },
    },
    
  }
</script>
<style>
	/*导航活动样式*/
	.main .active-nav{
		color: #1f94f1;
		text-decoration: underline;
	}
	/*导航活动样式结束*/
	.main{
		position: relative;
	}
	.main .main-warp{
		width: 1240px;
		margin:0 auto;
	}
	.main .bk-color-ccc{
		background-color:#F5F5F5
	}
	.main .insert{
		float: right;
		padding: 0 15px;
		width: 340px;
		height: 280px;
		background-color:rgba(0,0,0,80%);
		margin:auto;
	}
	.main .insert-warp{
		position: absolute;
		z-index: 100;
		top:-350px;
		/*right: 100px;*/
		width: 100%;
		/*text-align: right;*/
	}
	.main .insert .main-inster-header{
		display: flex;
		justify-content: space-between;
		height: 40px;
		border-bottom: 1px solid #fff;
	}

	.main .insert .main-inster-header div{
		cursor:pointer;
		color: #fff;
		height: 40px;
		line-height: 40px;
		text-align: center;
		width: 70px;
	}
	.main .insert .main-inster-header .mih-hot-tec{
		border-bottom:2px solid #fff;
		font-weight:700;
	}
	.main .insert .ht-msg{
		position: relative;
		height: 50px;
		line-height: 50px;	
		overflow:hidden;
		white-space: nowrap;
		text-overflow: ellipsis;
		/*background-color: pink;*/
	}
	.main .insert .ht-msg:hover .particular-ht-msg{
		display: block;
	}
	.main .insert .ht-msg .particular-ht-msg{
		cursor: pointer;
		position: absolute;
		top:0;
		bottom: 0;
		right: 0;
		left: 0;
		line-height: 25px;
		background-color: #fff;
		display: none;
	}
	.main .insert .ht-msg .particular-ht-msg h3,.main .insert .ht-msg .particular-ht-msg p{
		overflow:hidden;
		white-space: nowrap;
		text-overflow: ellipsis;
	}
	.main .insert-footer{
		cursor: pointer;
		height: 40px;
		line-height: 40px;
		color:#fff;
		font-size: 16px;
		text-decoration: underline;
	}
	.main .insert-footer div{
		overflow: hidden;
white-space: nowrap;
text-overflow: ellipsis;
	}	
	.main .insert-footer i{
		margin:0 1em;
	}
	.main .insert-footer .insert-footer-name{
		font-size:20px;
		font-weight: bolder;
	}
	.main .message{
		min-width: 1240px;
		height: 50px;
		background-color:#808080;
	}
	.main .message > .text{
		position: relative;
		padding:0 20px;
		height: 50px;
		width: 450px;
		margin:0 auto;
	}
	.main .message > .text span{
		display: inline-block;
		color: #fff;
		height: 50px;
		line-height: 50px;
	}
	.main .message > .text ul{
		display: none;
	}
	.main .message > .text .text-icon{
		color: #fff;
		position: absolute;
		width:20px;
		height: 50px;
		line-height: 50px;
		font-size: 20px;
		left: -20px;
	}
	.main .nav{
		box-sizing: border-box;
		min-width: 1240px;
		height: 150px;
		background-color: #F5F5F5;
		padding: 20px 0;
	}
	.main .nav > ul{
		display: flex;
		justify-content: space-around;
		width: 1240px;
		height: 110px;
		margin: 0 auto;
	}
	.main .nav > ul > li{
		box-sizing: border-box;
		width:240px;
		background-color: #fff;
		cursor: pointer;
	}
	.main .nav > ul > li:hover{
		box-shadow: 0px 0px 5px #efefef;
	}
	.main .nav .left{
		float: left;
		height: 60px;
		width: 140px;
		margin: 25px 0 0 20px;
	}
	.main .nav .left > div{
		font-size: 24px;
		font-weight: bold;
		margin-bottom: 5px;
	}
	.main .nav .right{
		box-sizing: border-box;
		height: 60px;
		line-height: 50px;
		width: 60px;
		margin:25px 0 0 170px;
	}
	.main .nav .right > i{
		font-size: 48px;
		color: #4BDCC6;
	}
	.main .content{
		padding: 80px 0 0 0;
		width: 100%;
	}
	.main .content > .head{
		text-align: center;	
	}
	.main .content > .head h1{
		margin-bottom: 20px;
	}
	.main .content-nav{
		margin-top: 30px;
	}
	.main .content-nav ul{
		display: flex;
		justify-content: center;
	}
	.main .content-nav span{
		margin:0 .5em;
	}
	.main .content-nav span:hover{
		cursor:pointer;
		color: #1f94f1;
		text-decoration: underline;
	}
	.main .body{
		display: flex;
		justify-content: space-around;
		margin-bottom: 2em;
	}
	.main .shade{
		position: absolute;
		background:rgba(0,0,0,0.6);
		top: 0;
		bottom: 0;
		right: 0;
		left: 0;
		padding:80px 20px 0 20px;
		display: none;
	}
	.main .shade .use,.shade .read{
		color: #fff;
		font-weight: bolder;
		font-size: 16px;
		height:100px;
	}
	.main .shade .read{
		display: flex;
		justify-content: space-between;
	}
	.main .shade .tel{
		position: absolute;
		right: 0;
		left: 0;
		bottom: 0;
		height: 80px;
		line-height: 80px;
		text-align: center;
		color: #F1B74C;
		font-size: 20px;
		border-top:2px solid #fff;
	}
	.main .product{
		position: relative;
		cursor: pointer;
		width: 280px;
		height: 315px;
		margin: 20px 1em 0 0;
		padding-bottom: 10px;
		border:1px solid #efefef;
	}
	.main .product img{
		width: 278px;
		height: 160px;
		margin-bottom: 10px;
	}
	.main .product .wape{
		padding: 0 1em;
	}
	.main .product h3{
		font-size: 20px;
		height: 55px;
		margin-bottom: 10px;
	}
	.main .product:hover{
		box-shadow: 2px 2px 2px #efefef;
	}
	.main .product:hover .shade{
		display: block;
	}
	.main .product:hover h3{
		color: #1E87ED;
	}
	.main .product-message{
		display: flex;
		justify-content: space-between;
		margin-top: 10px;
	}
	.main .product-message > .site{
		font-size: 16px;
	}
	.main .product-message > .stage{
		/*width: 64px;*/
		height: 24px;
		line-height: 24px;
		text-align: center;
		color: #1F86EF;
		background-color: #C6E8FE;
		border-radius: 5px;
	}
	.main .footer > .foot-text{
		box-sizing: border-box;
		height: 40px;
		line-height: 40px;
		width: 170px;
		text-align: center;
		border:1px solid #333;
		color: #666;
		margin:0 auto;
		margin-top:40px;
		cursor: pointer;
	}
	.main .footer > .foot-text:hover{
		color:#1F86EF; 
		border:1px solid #1F86EF;
	}
	.main .body{
		display: flex;
		justify-content: center;
		margin-bottom: 2em;
	}
	.main .counselor{
		position: relative;
		width: 305px;
		height: 350px;
		margin-top: 20px;
	}
	.main .counselor > .shade-counselor{
		cursor: pointer;
		position: absolute;
		background:rgb(88,118,165);
		top: 0;
		bottom: 0;
		right: 0;
		left: 0;
		padding:55px 50px;
		display: none;
	}
	.main .counselor > .shade-counselor .msg,.particulars{
		font-size: 18px;
		color: #fff;
		height: 140px;
		line-height: 2em;
	}
	.main .counselor > .shade-counselor .particulars{
		font-size: 20px;
		text-align: center;
	}
	.main .counselor:hover .shade-counselor{
		display: block;
	}
	.main .counselor > .face{
		margin:0 auto;
		border:1px solid #eee;
		padding: 5px;
		width: 115px;
		height: 115px;
		border-radius: 50%;
	}
	.counselor > .face > img{
		width: 103px;
		height: 103px;
		border-radius: 50%;
	}
	.main h3.name{
		font-size: 24px;
		color: #333;
		text-align: center;
		margin:.3em 0;
	}
	.main p.position{
		font-size: 14px;
		text-align: center;
		margin:.3em 0 2em 0;
	}
	.main .counselor .direction{
		display: flex;
		/*text-align: left;*/
		width: 305px;
		height: 120px;
		padding: .5em;
		flex-wrap:wrap;
	}
	.main .counselor .direction > span{
		overflow:hidden;
		/*box-sizing: border-box;*/
		text-align: center;
		height: 2em;
		line-height: 2em;
		border:1px solid #999;
		margin:5px 1em;
		min-width: 4em;
		padding:0 .3em;
	}
	.main .body-three{
		display: flex;
		width: 100%;
		height: 360px;
		margin-top:40px;
		background: url("https://maikeji.cn/images/index/index-activity.jpg");
	}
	.main .body-three .active{
		cursor:pointer;
		position: relative;
		flex: 1;
		display: flex;
		flex-direction: column;
		justify-content: center;
	}
	.main .body-three .active:hover{
		background-color:rgba(68,129,186,0.8);
	}
	.main .body-three .active-msg{
		display: flex;
		flex-direction: column;
		justify-content: space-around;
		color: #fff;
		font-size: 24px;
		text-align: center;
		height: 100px;
		/*line-height: 120px;*/
	}
	.main .body-three .active:hover .active-msg{
		position: relative;
		top:-40px;
	}
	.main .active i{
		font-size: 28px;
	}
	.main .active .new-active{
		position: absolute;
		left: 60px;
		bottom: 100px;
		box-sizing: border-box;
		width: 138px;
		height: 3em;
		line-height: 3em;
		color: #fff;
		text-align: center;
		border:1px solid #fff;
		display: none;
	}
	.main .body-three .active:hover .new-active{
		display: block;
	}
	.main .innovate{
		position: relative;
		width:300px;
		height:335px;
		margin: 20px 1em 0 0 ;
		padding-bottom: 10px;
		/*border:1px solid #ccc;*/
	}
	.main .innovate .innovate-img{
		overflow:hidden;
	}
	.main .innovate .innovate-img,.innovate-img img{
		width: 100%;
		height:200px;
	} 
	.main .innovate-img img:hover{
		transform: scale(1.1);
		transition-property:transform;
		transition-duration: 0.3s;
		/*transition-delay: 0;*/
		/*transition-timing-function: linear;*/
	}
	.main .innovate-msg{
		cursor: pointer;
		border:1px solid #eee;
	}
	.main .innovate-msg:hover{
		/*border: none;*/
		box-shadow: 0 0 3px #efefef;
	}
	.main .innovate-title{
		padding: .5em;
		font-size: 18px;
	}
	.main .innovate-link > div{
		margin-top: .5em;
		overflow:hidden;
		white-space: nowrap;
		text-overflow: ellipsis;
	}
	.main .innovate-link > div:hover a{
		color: #1F86EF;
		text-decoration:underline;
	}
	.main .ss-warp{
		background-color: #efefef;
		width: 100%;
		margin-top: 2em
	}
	.main .success-carousel{
		position: relative;
		width: 900px;
		height: 500px;
		overflow: hidden;
		margin:0 auto;
	}
	.main .success-carousel::after{
		content:"";
		display: block;
		clear: both;
	}
	.main .success-carousel ul{
		width: 4500px;
		position: absolute;
		top: 0;
		right: 0;
		/*轮播*/
		animation-name:success-carousel;
		animation-duration:15s;
		animation-fill-mode: both;
		animation-direction: normal;
		animation-iteration-count: infinite;
		animation-timing-function: steps(5);
	}
	.main .success-carousel li{
		float: left;
		width: 900px;
		height: 500px;
		/*margin:0 50px;*/
	}
	.main .success-carousel li > img{
		width: 900px;
		height: 500px;
	}
	@keyframes success-carousel{
			0%{
				left:0;
			}
			100%{
				left:-4500px;
			}
		}
</style>