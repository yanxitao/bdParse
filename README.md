# bdParse
百度智能小程序Html富文本解析并现实

bdParse

项目介绍

百度小程序富文本解析工具bdParse，改造自wxparse，支持html转换成百度小程序富文本节点。

安装教程

下载整个全部文件，放到你的小程序根目录下
在小程序页面的js种直接引入代码:var bdParse = require('../../bdParse/bdParse.js'); 对应css中引入@import "../../bdParse/bdParse.css";
在需要的字段使用baparse，代码：（注意：article和content不要重复） that.setData({ content:bdParse.bdParse('article', 'html', content, that, 5), })
swan页面引入模板，<import src="../../bdParse/bdParse.swan" /> 然后在需要显示富文本的地方调用：<template is="bdParse" data="{{ {bdParseData:article.nodes} }}" /> (注意：data调用改为和wxParse一致写法，注意是三个大括号，原先的直接写{{article}}不再支持，请注意修改)
使用说明

swan调用模板的data="{{ {bdParseData:article.nodes} }}"和setData中的article保持一致。
调用bdparse组件的时候，组件已经把富文本内容赋值（即setData）给了article；{{ {bdParseData:article.nodes} }} 这种写法的意思是：把article.nodes的内容赋值给bdParseData,bdParse.swan中调用的是bdParseData。
其他说明

bdParse是在wxParse的基础上改造的，只是把wxParse替换换成了bdParse，包含js，swan, css
wxml修改后缀改成swan，并且修改了全部模板传值的调用方式，符合百度小程序的使用。
修复了其他百度小程序的专有组件，比如s-for，s-if,s-elif,s-for-index等等
修复其他问题，比如去掉<template name="wxParseImg">重复的mode以及去掉data-from，给所有的s-for-index添加idx（好像不能为空）。
其他修改，不再赘述
因为直接批量替换内容，基本文章可以满足使用，其他没有做过多测试，欢迎大家反馈bug
参与贡献

原作者github地址：https://gitee.com/sootou/bdparse#bdparse
