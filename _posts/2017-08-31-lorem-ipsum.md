---
layout: default
title: "python爬虫库requests_html"
tags: Python爬虫
---

## python爬虫库requests_html

<p>requests_html是request库的升级版本，作者是同一个作者，据说是摄影技术超赞而且编程技术了得的大神。</p>

<p>之前用过request库的都知道，其功能特别强大，基本上是python爬虫必备的库了，request库其实是访问网页，搭配上BeautifulSoup是做网页解析的，这两个库搭配起来就做了爬虫的访问和解析的网页的所有功能了。</p>

<p>reuquest_html则是升级版本，无需BeautifulSoup也可解析html了，而且增加了好多的实用功能，比如访问JS等功能，可以说是封装了好多其他功能模块，就是新盖中盖，一片顶过去五片了，一口气做做爬虫腰不疼了。</p>


<h2>requests_html安装和引用</h2>

<p>安装直接在命令行输入pip安装就行了</p>


<pre class="wp-block-code"><code>pip install requests_html</code></pre>


<p>引用</p>


<pre class="wp-block-code"><code>from requests_html import HTMLSession</code></pre>



<h2>获取股票网站的最高价</h2>

<p>获取一个网站的一些数据，基本用法就是访问，然后解析处理数据，清洗数据。</p>

<p><a href="https://stock.finance.sina.com.cn/usstock/quotes/AMZN.html">https://stock.finance.sina.com.cn/usstock/quotes/AMZN.html</a></p>

<p>以获取上面亚马逊公司最新股价为例，代码如下。</p>


<pre class="wp-block-code"><code>from requests_html import HTMLSession #首先引入库
session = HTMLSession()               #类的实例化
link = 'https://stock.finance.sina.com.cn/usstock/quotes/AMZN.html'
r = session.get(link)   #定义变量r访问link数据
r.html.render()         #解析JS里面的代码，如果不输入这行代码，会出现NONE
price = r.html.find('#hqPrice',first=True)  #'#hqPrice'这个是CSS seleter路径
print(price.text)                           #打印出来数据</code></pre>


<p>如果我们会获取一个页面的数据，使用循环，访问多个页面的数据提取进行处理就是爬虫了。</p>


<h2>requests_html和request</h2>

<p>requests_html是request库的升级版本，作者是同一个作者，据说是摄影技术超赞而且编程技术了得的大神。</p>

<p>之前用过request库的都知道，其功能特别强大，基本上是python爬虫必备的库了，request库其实是访问网页，搭配上BeautifulSoup是做网页解析的，这两个库搭配起来就做了爬虫的访问和解析的网页的所有功能了。</p>

<p>reuquest_html则是升级版本，无需BeautifulSoup也可解析html了，而且增加了好多的实用功能，比如访问JS等功能，可以说是封装了好多其他功能模块，就是新盖中盖，一片顶过去五片了，一口气做做爬虫腰不疼了。</p>


<h2>requests_html安装和引用</h2>

<p>安装直接在命令行输入pip安装就行了</p>


<pre class="wp-block-code"><code>pip install requests_html</code></pre>


<p>引用</p>


<pre class="wp-block-code"><code>from requests_html import HTMLSession</code></pre>



<h2>获取股票网站的最高价</h2>

<p>获取一个网站的一些数据，基本用法就是访问，然后解析处理数据，清洗数据。</p>

<p><a href="https://stock.finance.sina.com.cn/usstock/quotes/AMZN.html">https://stock.finance.sina.com.cn/usstock/quotes/AMZN.html</a></p>

<p>以获取上面亚马逊公司最新股价为例，代码如下。</p>


<pre class="wp-block-code"><code>from requests_html import HTMLSession #首先引入库
session = HTMLSession()               #类的实例化
link = 'https://stock.finance.sina.com.cn/usstock/quotes/AMZN.html'
r = session.get(link)   #定义变量r访问link数据
r.html.render()         #解析JS里面的代码，如果不输入这行代码，会出现NONE
price = r.html.find('#hqPrice',first=True)  #'#hqPrice'这个是CSS seleter路径
print(price.text)                           #打印出来数据</code></pre>


<p>如果我们会获取一个页面的数据，使用循环，访问多个页面的数据提取进行处理就是爬虫了。</p>