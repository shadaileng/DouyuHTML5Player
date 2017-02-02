# 斗鱼HTML5播放器

基于 [flv.js](https://github.com/Bilibili/flv.js) 的斗鱼HTML5播放器.

使用了 flv.js 内核提供的直播流播放, 用 JavaScript 实现了斗鱼的弹幕协议, 并支持发送弹幕和送礼物.

![screenshot](screenshot.jpg)

# 使用

[Chrome 应用商店](https://chrome.google.com/webstore/detail/hbocinidadgpnbcamhjgfbgiebhpnmfj)

[Greasy Fork](https://greasyfork.org/scripts/26901) (Firefox)

要求 Chrome 版本大于等于 49 (仅在54+版本测试过)

打开斗鱼的直播间, 如果没有错误, 播放器就已经被自动替换.

注: 如开启了 [chrome://flags/#extension-active-script-permission](chrome://flags/#extension-active-script-permission), 请注意允许扩展程序在所有网址上运行, 否则会没有权限运行.

# 原理

视频播放基于 flv.js, 弹幕发射使用 CSS3, 弹幕协议通过自制一个很小的 Flash 与 JavaScript 通信, 在 JavaScript 中实现斗鱼的弹幕协议.

由于斗鱼使用了 HTTPS, 受到 Mixed Content 限制, 只能在 Background 页面 fetch 视频内容再传到 Content Script 给 flv.js 进行播放.

具体原理请见我的 [blog](http://blog.imspace.cn/2016/10/29/DouyuHTML5Player/)

# 构建

1. `npm install`

2. `npm run build`

3. `npm run pack` 在 versions 文件夹查看 zip 文件
