# zhihu-recover

对知乎已经删除/可能删除的问题备份

知乎删除了问题 "莆田系医院都有哪些内幕？" 从快照恢复并备份了其他几个莆田系相关问题


## 列表

(404)[莆田系医院都有哪些内幕？](https://rawgit.py3.io/zjuchenyuan/zhihu-recover/59c1bd57/%E8%8E%86%E7%94%B0%E7%B3%BB%E5%8C%BB%E9%99%A2%E9%83%BD%E6%9C%89%E5%93%AA%E4%BA%9B%E5%86%85%E5%B9%95%EF%BC%9F/%E8%8E%86%E7%94%B0%E7%B3%BB%E5%8C%BB%E9%99%A2%E9%83%BD%E6%9C%89%E5%93%AA%E4%BA%9B%E5%86%85%E5%B9%95%EF%BC%9F.html)

(404)[福建莆田私人医院的历史是怎么样的？](https://rawgit.py3.io/zjuchenyuan/zhihu-recover/e67fb18e/%E7%A6%8F%E5%BB%BA%E8%8E%86%E7%94%B0%E7%A7%81%E4%BA%BA%E5%8C%BB%E9%99%A2%E7%9A%84%E5%8E%86%E5%8F%B2%E6%98%AF%E6%80%8E%E4%B9%88%E6%A0%B7%E7%9A%84%EF%BC%9F/%E7%A6%8F%E5%BB%BA%E8%8E%86%E7%94%B0%E7%A7%81%E4%BA%BA%E5%8C%BB%E9%99%A2%E7%9A%84%E5%8E%86%E5%8F%B2%E6%98%AF%E6%80%8E%E4%B9%88%E6%A0%B7%E7%9A%84%EF%BC%9F.html)

(404)[知乎用户：哪个瞬间让你突然觉得读书真有用？](https://rawgit.py3.io/zjuchenyuan/zhihu-recover/382e96c/%E7%9F%A5%E4%B9%8E%E7%94%A8%E6%88%B7%EF%BC%9A%E5%93%AA%E4%B8%AA%E7%9E%AC%E9%97%B4%E8%AE%A9%E4%BD%A0%E7%AA%81%E7%84%B6%E8%A7%89%E5%BE%97%E8%AF%BB%E4%B9%A6%E7%9C%9F%E6%9C%89%E7%94%A8%EF%BC%9F.html) [Related video backup](https://api.chenyuan.me/zjuvideo/55cce61ebbb6cbec43f7f3e26f/455003635826)

(404)[如何评价韩国电影《出租车司机》？](https://rawgit.py3.io/zjuchenyuan/zhihu-recover/98e86c74/%E5%A6%82%E4%BD%95%E8%AF%84%E4%BB%B7%E9%9F%A9%E5%9B%BD%E7%94%B5%E5%BD%B1%E3%80%8A%E5%87%BA%E7%A7%9F%E8%BD%A6%E5%8F%B8%E6%9C%BA%E3%80%8B%EF%BC%9F.html)

(404)[如何评价北航陈小武老师？](https://rawgit.py3.io/zjuchenyuan/zhihu-recover/51cd0bb6/%E5%A6%82%E4%BD%95%E8%AF%84%E4%BB%B7%E5%8C%97%E8%88%AA%E9%99%88%E5%B0%8F%E6%AD%A6%E8%80%81%E5%B8%88%EF%BC%9F.html)

(404)[如何看待上海环卫工罢工？ - 知乎]()

[莆田人为什么这么“精明”](https://rawgit.py3.io/zjuchenyuan/zhihu-recover/59c1bd57/%E8%8E%86%E7%94%B0%E4%BA%BA%E4%B8%BA%E4%BB%80%E4%B9%88%E8%BF%99%E4%B9%88%E2%80%9C%E7%B2%BE%E6%98%8E%E2%80%9D_%20-%20%E7%9F%A5%E4%B9%8E.html)

[在知乎的医生怎么看待莆田系的医生？](https://rawgit.py3.io/zjuchenyuan/zhihu-recover/59c1bd57/%E5%9C%A8%E7%9F%A5%E4%B9%8E%E7%9A%84%E5%8C%BB%E7%94%9F%E6%80%8E%E4%B9%88%E7%9C%8B%E5%BE%85%E8%8E%86%E7%94%B0%E7%B3%BB%E7%9A%84%E5%8C%BB%E7%94%9F%EF%BC%9F%20-%20%E7%9F%A5%E4%B9%8E.html)

[魏则西怎么样了？](https://rawgit.py3.io/zjuchenyuan/zhihu-recover/59c1bd57/%E9%AD%8F%E5%88%99%E8%A5%BF%E6%80%8E%E4%B9%88%E6%A0%B7%E4%BA%86%EF%BC%9F.html)


## 从快照恢复知乎页面方法

虽然百度快照对知乎的支持还是很渣的，但几乎可以确定的一点是：**删帖不会删图片** 至少不会马上删

Ctrl+U查看源代码，发现图片其实是有链接的，只是使用了图片延迟加载的技术，百度快照页面已经过滤掉了js也就导致图片加载不出来；同时知乎的图片是反盗链的，需要设置Referer为zhihu.com才可正常加载

### 步骤：

1.打开快照页面，Ctrl+U查看源代码，Ctrl+A Ctrl+C全选复制，粘贴到编辑器

2.替换：

```
src="//zhstatic.zhihu.com/assets/zhihu/ztext/whitedot.jpg"替换为空
data-original替换为src
```

还可能需要视情况修改meta中charset的设置，例如charset=gb2312替换为charset=utf-8

3.打开网页，全页面截图保存

4.(进阶)得到离线版本

使用高级的编辑器(如我用的EmEditor)，提取图片网址，正则为：`https://pic[0-9].zhimg.com/[^" ]+"`, 全部选择复制到一个空文档，将`"`替换为`\n`，保存文档到`tmp.txt`

可见tmp.txt中还是有重复的记录，先进行去重后再下载吧：

```
cat tmp.txt|sort|uniq>piclist.txt
wget -i piclist.txt
```

下载图片完成后编辑html：找到base标签删除；正则替换`https://pic[0-9].zhimg.com/`，替换为空

再打开浏览器F12看看有没有不存在的文件，抓出来再下载一遍 over

在发现知乎404后尽快按步骤进行恢复，防止快照过期


## 欢迎贡献

欢迎PR提交更多已经被删/可能被删的知乎问题的备份文件