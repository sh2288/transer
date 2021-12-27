# 文字游戏 翻译君 (云翻 云翻译软件)
支持多种文件类型的一键翻译工具|您与汉化翻译组的距离或许只差一个软件
--|--

吉里吉里ks一键翻译|Renpy一键翻译|Rpgmv一键翻译|TyranoScript一键翻译
--|--|--|--

![image](https://img.shields.io/badge/最新版本-2021--08--08-orange)  ![image](https://img.shields.io/badge/官方QQ1群-38552538-ff69b4?style=flat&logo=tencent-qq) ![image](https://img.shields.io/badge/官方QQ2群-706514743-ff69b4?style=flat&logo=tencent-qq)  ![image](https://img.shields.io/badge/.NET-4.5.2-brightgreen?style=flat&logo=.net) ![image](https://img.shields.io/badge/windows/xp/7/8/10-x86/x64-blue?style=flat&logo=windows)


[github地址](https://sh2288.github.io/transer)
[码云gitee地址](https://gitee.com/sh2288/transer)

QQ1群(已满) [38552538](https://jq.qq.com/?_wv=1027&k=ajBHt2i4) QQ2群 [706514743](https://jq.qq.com/?_wv=1027&k=uNgezthB)
### 软件下载(解压密码706514743)目前最新版本是2021-09-08[版本更新说明](#update)
[度盘提取码:bb3b](https://pan.baidu.com/s/1qObSVEx6ZijYcia8QKic3w) 
[github](https://github.com/sh2288/transer/releases) 
[码云gitee](https://gitee.com/sh2288/transer/releases/)
### 最新消息
2021-11-15
1. 加入批量翻译中,即时导出文本,防止意外崩溃导致翻译好的文本无法导出(计划中...)

2021-10-15
1. 上个版本加入的功能,行号列右键菜单,使用说明(多用于跳过剧本脚本使用),可能说明里并没有把这个功能写明白--数字序号列点右键(按shift可多选,但不能多选翻译)
![image](img/行号列-右键菜单.png)

2021-09-15

1. 写了个shell,[rpgmaker_decrypter_shell](https://github.com/sh2288/rpgmaker_decrypter_shell),有需要折腾的拿去吧,一键解密rpgmv游戏,ogg一键转m4a,欢迎传播


2021-09-08

1. 解决错行问题(bug1)
2. 在文件中需要提取的翻译文本为空时,可移除
3. 加回rpgmv中CommonEvents.json,102选项的提取(上个版本忘记了)

2021-09-02 bug发现

1. RPGMV CommonEvents.json 中的102选项文本忘记提取了
2. RPGMV code 108,408疑似为注释,可不用提取翻译

2021-08-31 下一版本更新方向

1. 错行的处理(当翻译引擎漏翻时的处理)
2. rpgmv,当code为356,105,108...时的处理或增加选项,由用户自行选择

2021-08-30

1. RPGMV_json基本可以一键全翻,特殊除外,可达到完成度95%以上
2. 翻译面板右键菜单添加"跳过选项"

2021-08-27

1. rpgmv类型测试完毕,整体一键翻译有望实现

2021-08-24

1. 2021-08-24版本已经修正下列bug
2. 同时修复renpy bug

2021-08-20
1. 改进rpgmv类型,增加道具,装备等文字或剧本的提取
2. 改变现有ks提取中的bug
3. 正则表达式提取代码优化,修复现有bug
4. 添加复制原文按钮,方便后期二次文润
5. 下一版本将修正以上所有内容

### 软件用途

任意文本翻译 | 游戏脚本剧本翻译 | 字幕翻译 | 汉化辅助工具
---|---|---|---

### 软件介绍
![image](img/软件简介-ks.png)
1. 文本文件任意支持的语言(详见翻译API支持语言列表)翻译成简体中文
2. 翻译好的文件编码为utf16le有签名(仅ks或text类型)
3. 自动识别文件编码shift-jis和utf8,utf16,gb2312等(utf16be无签名除外)
4. 支持文件类型

---|*.ks | *.scn | *.rpy |*.json| \*.*(纯文本)
---|---|---|---|---|---
游戏引擎|吉里吉里xp3|吉里吉里xp3|rpy语言包|RPGMV|纯文本
提取剧本|自动|纯文本+正则|自动(只支持翻译包)|自动(*.json)|自动提取所有或正则提取

5. 支持的翻译接口,点击直接申请接口API,[翻译接口申请教程](#apitech)

翻译接口| [有道智云](https://ai.youdao.com/login.s) | [百度翻译(含高级版)](https://fanyi-api.baidu.com/api/trans/product/index) | [腾讯翻译君](http://cloud.tencent.com/) | [彩云小译](https://dashboard.caiyunapp.com/user/sign_up/)
---|---|---|---|---
免费额度|50元|无限或200万字/月|500万字/月|100万字/月
多线请求|支持|不支持|不支持|支持
QPS|不限|1或10|5|不限
翻译速度|快|快|一般|很快
打包字数最大值|4000|3000|2000|5000

6. 翻译字数统计
7. 人名修改系统,通过正则提取游戏内人物"说话"时的名字,请根据翻译参考或游戏人物参考对照修改
8. 采用多线程同时翻译多个文件,目前最大支持32个文件同时翻译,效率是以前的单文件的32倍
9. 打包翻译,放弃以往一句一翻的方式,采取批量打包翻译方式
10. 文润系统(后期处理文本用,可以将API返回的常见错误加以修正,例如翻译好的文本中有大量的AAAA,AAAA是翻译结果,但并不一定是正确的结果,通过文润系统可以将所有文本中的AAAA,全部换成您设定好的BBBB)

文润 | 原始 | 修正
---|---|---
----|AAAA|BBBB
例1|阿傻姬|阿萨姬
例2|雪疯|雪风

11. 加入自动激活功能,只支持支付宝付款后的自动激活

### 使用指南
<a id='apitech'></a>
>#### 翻译接口申请教程
申请网址| [有道智云](https://ai.youdao.com/login.s) | [百度翻译(含高级版)](https://fanyi-api.baidu.com/api/trans/product/index) | [腾讯翻译君](http://cloud.tencent.com/) | [彩云小译](https://dashboard.caiyunapp.com/user/sign_up/)
---|---|---|---|---

>##### 有道
![image](img/有道API申请教程.png)
>##### 百度[详细教程](https://www.3cinfo.net/course/220.html)
![image](img/百度API申请教程.png)
>##### 腾讯
![image](img/腾讯API申请教程.png)
>##### 彩云
![image](img/彩云API申请教程.png)

>#### 软件使用教程

强烈建议您在正式翻译文件之前,先进行翻译测试(翻译接口-->翻译测试)|
---|

您甚至可以利用此项功能,直接将翻译测试的结果导入到游戏中|
--|

![image](img/翻译测试样本.jpg)

1. **打开剧本**-->批量选择需要翻译的剧本文件(一定要确认不是utf16be无签名的),选择要使用的**翻译接口**,点击**翻译并导出所有剧本**即可
2. 若希望翻译完成后进行修改润色校验等工作,可以先**翻译所有剧本**,然后批量文润或单项修改,全部完成后再**导出所有剧本**
3. **打包字数**设置为**0**时,翻译面板中的文本将执行按每行翻译,而不再将文本按照设定的字数打包
4. **应用文润**在设置窗口第二页,可以设置自己的文润对应表(注意,文润只针对翻译的结果进行修正,并不是原始语言的特定字典)

文润 | 原始 | 修正
---|---|---
----|AAAA|BBBB
例1|阿傻姬|阿萨姬
例2|雪疯|雪风

5. 文本类型**text_regex**表示纯文本+正则表达式,理论上可以翻译任意文本

文本类型 |*.ks | *.scn | *.rpy |*.json| \*.*(纯文本)
---|---|---|---|---|---
游戏引擎|吉里吉里xp3|吉里吉里xp3|rpy语言包|RPGMV|纯文本
提取剧本|自动|纯文本+正则|自动(只支持SDK导出的翻译包,空字串格式)|自动(*.json)|自动提取所有或正则提取
>##### ks文件类型
![image](img/ks教程2.png)
>##### rpy文件类型
![image](img/rpy教程3.png)
[来自其他网站的renpy详细教程](https://nothamor.cn/index.php/archives/renpyTranslate.html)
>##### json(rpgmv)文件类型
![image](img/rpgmv-json教程3.png)
此功能仅供测试还不完善,至于游戏中其他公共事件和数据库等,可通过正则表达式进行提取翻译汉化,当然开编辑器改也可
>##### *.*(纯文本)文件类型
![image](img/text-regex教程2.png)
>#### 文件位置说明

所有翻译好的文本位于翻译文件的目录下的\\(所用翻译接口)_(翻译文件类型)\目录下,譬如 \彩云_kirikiri_ks\
<a id='update'></a>
>#### 软件版本更新说明

当你使用软件设置好翻译接口,激活软件后,请妥善保管软件目录下的config.ini和wr.txt

这两个文件为您的软件设置和文润设置文件,请不要轻易删除

当更新新版本时,请将这两个文件,拷贝到新版软件的目录下

[B站视频教程](https://www.bilibili.com/video/av69298736)
[youtube视频教程](https://youtu.be/8aXjUVPenW8)


>#### 文字游戏_翻译君 内置工具列表
```
\tools\ krkrrel-cn(kr打包)
\tools\ GARbro(解包打包)
\tools\ KrkrExtract4.0.1.4(kr解包打包)
\tools\ Emeditor(支持多编码转换的文本编辑器)
```
>#### 已知BUG

2021-09-08版本,已经解决 bug1
1. 错行问题,由于打包翻译时,提交出去的数据和收到的数据(翻译引擎返回值)可能不一致导致,遇到这样的问题,请在表格中出现错行的位置,点击右键-->错行调整

设置打包字数为0时,可避免错行发生,经测试,使用腾讯翻译接口比较容易发生错行
