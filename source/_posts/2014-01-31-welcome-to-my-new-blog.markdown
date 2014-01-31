---
layout: post
slug: "welcome-to-my-new-blog"
title: 新宅入住了！
date: 2014-01-31 00:11:01 +0800
comments: true
categories:
- essay [唠叨]
tags:
- octopress
- octopress-category-list
- wordpress
- blog migration
---

我苦命的博客经过多次搬迁，现在此处入住啦！使用的是 [octopress](http://octopress.org) + [github](https://github.com)。不过，这不会是一个技术博客。

早年写过一篇 [博客搬家血泪史](/blog/2010/04/04/migration-of-my-blog/)，讲述了我的博客从 Live Space 搬到 blogger 再搬到 yo2.cn 再搬到 35.cn 的辛酸故事。但后来的故事更加辛酸：35.cn 的访问速度非常慢，而 yo2.cn 合并到 blogcn，然后我就搬回 yo2.cn 了；结果没多久人家要收费，我再搬到 wordpress.com.cn。一直以来使用 Live Writer 离线编辑 wordpress 确实很方便，但是折腾多了也没什么动力再经常更新了。当然，更重要的是观众没了，大家都跑去玩微博了。

直到很久前，老马发了这个 octopress 给我看，当时觉得挺不错，但想到要从 wordpress 迁移过来得花不少精力，于是又一直搁置了下来。现在终于过年放长假了，整整花了一天半时间把 wordpress 给迁移过来了。想了解 octopress 搭建和迁移细节的人，继续往下看吧。其他人，祝你们新年快乐！

<!-- more -->

### 搭建 octopress

按 octopress 文档的指引，发布到 github 就行了。我同时配了 wangxianda.cn 和 www.wangxianda.cn 两个域名。

### 从 wordpress 迁移

使用了 [exitwp](https://github.com/thomasf/exitwp)，按照其文档描述，把 wp 博客导出，运行命令进行转换，把转换出来的文章拷到 octopress 的相关目录下就可以了。

不过面临的一个问题就是文件名和文章的URL（slug）是原中文标题的 URL encode 格式，最后花了很多时间一个个改成英文……还好，总共只有几十篇文章！

很多文章的图片还是引用自当年的 Live Space 相册，所幸的是这么多年过去了，虽然变成了 SkyDrive，但地址还是兼容的，而且现在的 SkyDrive 访问速度比以前快了很多。

### 配置

测试发现侧边栏默认没有熟悉的标签云和分类列表。先参考了老马的配置，加了 [octopress-category-list](https://github.com/ctdk/octopress-category-list)。不过发现 octopress 不支持中文分类，接着上网找到了 octopress 2.1 分支已经支持中文分类，但 octopress-category-list 仍然没有支持（或是我没找到），自己 [fork 了一个](https://github.com/xianda/octopress-category-list) 合并了 octopress 2.1 的修改并改了几行代码解决了这个问题。

标签云则是添加了 [octopress-tag-pages](https://github.com/robbyedwards/octopress-tag-pages) 和 [octopress-tag-cloud](https://github.com/robbyedwards/octopress-tag-cloud)，算是把这两个常用功能给加上了。

最后再注册一个 [Disqus](http://disqus.com) 的帐号打开评论功能，大功告成。
