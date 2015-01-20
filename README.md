# wechat

一个基于Clojure语言的微信开发库

## Usage

### 配置微信公众号
在项目的resources文件夹中，添加 wechat.properties 文件,内容如下

	#微信公众号开发模式中的Token
	token=wechat
	#公众AppID
	appid=AppID
	#公众号的AppSecret
	appsecret=AppSecret

### 常用接口

	(require '[wechat.core :as w])

	;;获取access-token
	(w/access-token)

	;;根据当前的url生成jsapi的签名包
	(w/sign-package "http://www.lninl.com#你好")
	;; 生成的签名包如 {:appid "APPID", :noncestr "ec2319a1-5895-45d7-8ae1-f0b1293a0bb4", :timestamp "1421757790", :url "http://www.lninl.com#你好", :signature "83a3a12537453de44d3e208ea4b53e692817f6b1"}

	;;验证公众号签名是否正确
	(w/check-signature? "dc3d2b94f194ffc60967e01635d570ae5445c3cc" "1421758035" "你好")
	;; 如果token=wechat，则返回true



## License

Copyright © 2015 qinains

Distributed under the GNU GENERAL PUBLIC LICENSE Version 2, June 1991.
