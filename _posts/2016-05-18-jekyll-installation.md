---
layout: post
title: Jekyll 博客安装
date: 2016-05-18 22:19:18 +0800
categories: technique
tags: jekyll
keywords: jekyll，blog
---
nginx + worldpress 博客再次被我更新崩溃，不想再折腾。搞怎么长时间博客，大部分时间都花在了博客的安装修复上，真正写博客的时间确非常少，总是这样本末倒置，到现在真是看不到任何积累。现在真是要下定决心好好写写，记录自己的学习和感悟。
<!-- more -->
jekyll + Github Pages 的博客方式之前一直听说过，还被认为是现在程序员标配的博客方式。我大概是因为年龄越大越懒惰，越来越不愿尝试新的东西，也可能觉得这玩意是静态博客，要在本地编译，想当然的认为限制大不灵活，功能也一定很简陋。现在安装了解完，完全否认了之前的观点，这确实是一个程序员应有的博客记录方式，而且回归博客的本质，我要那么多功能干嘛。好了不再废话，接下来记录 Jekyll 安装过程。

## 了解 jekyll + Github Pages
Jekyll 是一个将写好的模板转换为静态页面的系统，有自己的模板语言，可以理解为 php 一样，只是需要预先编译成最终页面，而 php 可以在访问时动态生成页面。Jekyll 的这种方式通过用户端传数据来显示动态页面，所以无法实现评论功能，不过可以通过外挂评论的方式实现，目前有几个这样的社会化评论提供商，如 Disqus。

Github Pages 是 Github 提供的免费静态页面托管服务，分为两种：项目站点和个人和组织页面。

项目站点是在 project 中单独开一个以 gh-pages 命名的分支，在里面存放静态网页文件，访问时通过 `{username}.github.io/{respositoryName}` 的方式访问。

个人页面就是单独的一个以 `{username}.github.io` 的命名的 respository。也通过这个域名进行访问。当然这两种方式都可以绑定个人域名，这个之后再介绍。

Gitbub Pages 已经和 Jekyll 进行整合，你只需要上传 Jekyll 的原始文件，GIthub Pages 会自动进行编译，甚至你在你的 respository 里都看不到编译后的文件。不过这种方式会有很大限制，因为 Jekyll 强大的插件体系只有部分被 Github 支持，不支持自己编写插件。基本上就只能做最基本的博客写作了。不过这样优点也很明显，不需要手动编译，你可以在任何平台上传写好的 Markdown 文件就可以发文，我之前还打算利用 Github 的 hook 连上自己的 VPS 来实现这一点，现在看来用不着了。当然你要不嫌麻烦可以在本地编译后上传，这样就可以使用 Jekyll 的完整功能。

## Jekyll 安装
现在只介绍下我自己在 Ubuntu 下的安装过程。

Jekyll 是由 Ruby 驱动，需要安装 Ruby 相关组件，我之前并没有接触 Ruby，所以照着文档敲一堆命令就完了，中间也遇到一些坑，不过我没有记下来，抱歉，下面我只把想起来有用的相关命令列在下面

{% highlight shell linenos %}
sudo apt-get install ruby
sudo apt-get install rubygems
sudo gem sources --add https://ruby.taobao.org/ --remove https://rubygems.org/ # 因为墙的关系替换国内镜像
sudo apt-get install ruby-dev # 安装 Jekyll 时遇到的坑，需要先安装这个，并不知道干什么的
sudo gem install jekyll
{% endhighlight %}

{% highlight shell linenos %}
sudo apt-get install ruby
sudo apt-get install rubygems
sudo apt-get install ruby-dev 
sudo gem install jekyll
{% endhighlight %}

如果你在我之后使用这种方式安装，应该装的是 jekyll 3 或以上版本，和 jekyll 2 有一些不兼容的地方，主要在安装主题的时候会有体现。有的介绍说需要安装 nodejs，jekyll 3 不需要依赖 nodejs，我就没有安装。执行以上命令 Jekyll 环境就已经搭建完成。之后折腾主题的时候还遇到过各种依赖缺失，一般自己 `gem install` 一下就好了。

## 创建 Jekyll 博客
安装完 Jekyll 后，执行一下命令就可以新建和运行一个博客：

```
jekyll new myblog
cd myblog
jekyll serve
```

```java
public static void main(String[] args) {
    System.out.println("hello world");    // 我知道这很傻逼，但你又能拿我怎么样。bababababababa
}
```

{% highlight java linenos %}
public static void main(String[] args) {
    System.out.println("hello world");
}
{% endhighlight %}