# 前端框架机的搭建与使用lbf进行前端页面开发

## 1. 前端框架机搭建

### 1.1 环境准备

#### 1.1.1 下载nodejs
去[官网](https://nodejs.org)直接下载即可

	node -v
	npm -v

<b>[内部 Node.JS NPM 镜像使用方法](http://km.oa.com/group/502/articles/show/167873?kmref=related_post)</b>
	
	npm config set registry http://npm.oa.com
	npm --registry http://npm.oa.com install <package>

#### 1.1.2 下载grunt

	npm install -g grunt
	npm install -g grunt-cli

#### 1.1.3 svn地址

	svn co https://sh-svn.tencent.com/basic/basic_corporatespace_rep/static_b_qq_com_proj/trunk/store

### 1.2 本地环境搭建

#### 1.2.1 运行node服务
到指定目录下运行grunt：
	
	grunt dev

#### 1.2.2 本地端口更改
localServer默认占用两个端口80和8081<br>
<br>
80端口在store/Gruntfile.js里进行设置:

	...
	localServer: {
		options: {
			server: {
				port: 80   //改为8888
			}
		}
	}
	...

除此之外静态资源加载的部分也需要更改（store/src/views/local.json）：

	{
	    "local": {
		"THEME": "http://127.0.0.1/store/src/themes/default/",
		"LBF_VERSION": "0.7.6",
		"VERSION": "20150323",
		"PATHS": "{ store: { path: '/store/src/', root: 'http://127.0.0.1' }}",
		"HOST": "127.0.0.1",
		"BASE": "/store/src",
        "isLocal": true,
        "COMBO": "true",
		"BOSS": {
			"THEME": "http://127.0.0.1/store/src/themes/boss/"
		},
		"UDS": {
            "THEME": "http://127.0.0.1/store/src/themes/uds/"
        }
	},

## 2. 前端页面开发
### 2.1 版本拉取
+ view资源和静态资源分别新建分支：

	svn co https://sh-svn.tencent.com/basic/basic_corporatespace_rep/static_b_qq_com_proj/trunk/store
	svn co http://sh-svn.tencent.com/ba/ba_frontend_rep/view_proj/trunk/store/views

+ 将原store/src/views的svn引用进行更改
+ merge的时候也需要分别merge入库

### 2.2 开发

#### 2.1 lbf API
[lbf官网](http://lbf.epc.oa.com/) <br>
lbf源代码: svn co https://sh-svn.tencent.com/basic/basic_corporatespace_rep/LBF_pro) 

### 2.3 上线
