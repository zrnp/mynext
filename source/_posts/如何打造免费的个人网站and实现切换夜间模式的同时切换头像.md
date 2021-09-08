---
title: 如何打造免费的个人网站and实现切换夜间模式的同时切换头像
date: 2021-09-08
categories: 教程
tags: 教程
---
<p>最近整了个个人网站，非常快乐，所以来分享一下心得。整理一下我看过的教程。</p><!--more-->
<p>建议按顺序看</p>
<p><a href="https://zhuanlan.zhihu.com/p/60578464">使用 Hexo+GitHub 搭建个人免费博客教程（小白向）</a></p>
<p><a href="https://yxyuxuan.github.io/2019/07/16/GitHub-Hexo-Next%E6%90%AD%E5%BB%BA%E5%8D%9A%E5%AE%A2/">GitHub+Hexo+Next搭建博客</a>（建议用next主题，我用的是<a href="https://github.com/theme-next/hexo-theme-next">7.8.0版本</a>）</p>
<p>以下是加的特效，建议先学一学HTML、CSS、js以及能看懂cmd错误分析，如果不行，那么务必严格按照步骤做，否则会出错</p>
<p><a href="https://juejin.cn/post/6844903696455696391">Hexo+NexT 打造一个炫酷博客</a></p>
<p><a href="http://www.1226.site/2020/11/23/NexT7.8.0%E4%B8%BB%E9%A2%98%E7%BE%8E%E5%8C%96%EF%BC%88%E6%8C%81%E7%BB%AD%E6%9B%B4%E6%96%B0%EF%BC%89/">NexT 7.8.0 主题美化（持续更新）</a></p>
<p><a href="https://asurada.zone/post/Blog-Search-Engine-Index/">Hexo 博客主流搜索引擎收录详细指南</a></p>
<hr/><p>以下是个人我在夜间模式上加的功能，点击夜间模式会自动切换头像。</p>
<p><a href="https://alobal.github.io/2020/07/23/Next7-8-%E5%8A%9F%E8%83%BD%E6%80%A7%E9%85%8D%E7%BD%AE/">Hexo+Next7.8 功能性配置</a></p>

<p>1、先根据这个教程安装并配置插件：<a href="https://www.techgrow.cn/posts/abf4aee1.html#%E5%AE%89%E8%A3%85-Hexo-%E6%8F%92%E4%BB%B6">Hexo Next 8.x 主题添加可切换的暗黑模式</a></p>
<p>2、再打开存放博客的文件夹下..\node_modules\hexo-next-darkmode\lib\darkmode.css，再最后添加以下代码：</p>
<p>.darkmode--activated .site-author-image {
content:url(../uploads/image.gif);
}</p>
<p>url后的括号是图片路径，uploads文件夹放在博客工程所在目录下，image.gif是图片名，也可以更换。</p>
<p>3、在项目目录的source文件夹下新建“_data”文件夹，在文件夹中新建“styles.styl”文件，将以下内容复制进去。</p>
<p>.site-author-image {
content:url(../uploads/image.gif);
}</p>
<p>4、打开..\themes\next\_config.yml，查找到“custom_file_path:”，在其下一行粘贴 style: source/_data/styles.styl，开头空两格。</p>
<p>5、在bash里输入“hexo clean &amp;&amp; hexo g &amp;&amp; hexo d”</p>