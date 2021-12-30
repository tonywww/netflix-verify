# NETFLIX-VERIFY

流媒体NetFlix解锁检测脚本，使用Go语言编写。

在VPS网络正常的情况下，哪怕是双栈网络也可在几秒内快速完成IPv4/IPv6的NF解锁情况判断。


<!-- TABLE OF CONTENTS -->
<details open="open">
  <summary>目录</summary>
  <ol>
    <li>
      <a href="#使用方法">使用方法</a>
    </li>
    <li>
      <a href="#效果演示图">效果演示图</a>
    </li>
    <li>
      <a href="#新特性">新特性</a>
    </li>
    <li>
      <a href="#功能实现">功能实现</a>
    </li>
    <li>
      <a href="#其他常见流媒体脚本链接">其他常见流媒体脚本链接</a>
    </li>
   </ol>
</details>

## 使用方法

1. 部署 `golang` 环境，执行 `go run nf.go` 运行本小应用。

2. 懒人一键运行包（使用编译好的二进制文件执行本小程序）

   * Github下载链接（适用于IPv4网络的机器）:

   * **x86_64:**

   ```shell
   wget -O nf https://github.com/tonywww/netflix-verify/releases/download/2.61.1/nf-2.61.1-linux-amd64
   chmod +x nf
   ./nf
   ```

   * **arm64:**

   ```shell
   wget -O nf https://github.com/tonywww/netflix-verify/releases/download/2.61.1/nf-2.61.1-linux-arm64
   chmod +x nf
   ./nf
   ```

## 效果演示图

### 简约模式

<img width="430" alt="Lite Method" src="https://user-images.githubusercontent.com/13616352/110296950-e479c000-802d-11eb-9837-e23392860b07.png">

## 新特性

在`v2.51`版本中提供了2种不同的模式，将显示完全不同的结果：

* 运行`./nf -method full`将专门为发烧友准备的利器，显示更全面的结果
* 而普通用户当以缺省参数运行`./nf`或者是`./nf -method lite`将显示更轻量级的结果，显示更加友好

在`v2.6`版本中提供了自定义解锁功能，运行`./nf -custom 想测试的电影ID号`即可查看特定影片是否在该网络上解锁


## 鸣谢

1. 感谢 [@CoiaPrant](https://github.com/CoiaPrant) 指出对于地域检测更简便的方法
2. 感谢 [@XmJwit](https://github.com/XmJwit) 解决了IPV6 Only VPS无法下载脚本的问题
3. 感谢 [@samleong123](https://github.com/samleong123) 指出了文档的解释缺陷
4. 感谢 [@ymcoming](https://github.com/ymcoming) 指出了IPv6的检测Bug

## 功能实现

- [X] 解锁情况判断
- [X] 地域信息显示
- [X] 双栈网络测试
- [ ] 半解锁检测（待实现）

## 相关名词解释

1. **不提供服务** - 所在的地区NF没开通，连自制剧也看不了
2. **宽松版权** - 有些NF拍摄的影片不是特别注重版权，所以限制放的很开
3. **解锁自制剧** - 代表可以看由NF自己拍摄的影片
4. **解锁非自制剧** - 代表可以看NF买下的第三方版权影片
5. **地域解锁** - NF在不同的地区可以看的片源都是不同的，有些影片只能在特定区观看

一般来说，需要能看非自制剧才算真正意义上的NF解锁

## 提醒

在观看Netflix影片，有一种情况极少遇到，那就是“**半解锁**”，可以观看一部分的非自制剧，却不会显示任何地域排行榜有关的信息。

这种情况由于太少见以至于**很容易被忽略**，我会在未来认真研究它，以推出更健壮的检测脚本。如果您手里有可以半解锁Netflix的机器，欢迎联系我测试，我会将您的名字加入鸣谢名单中，非常感谢。

## 推荐使用以下SSH客户端以获得良好的使用体验

NextSSH：[NextSSH.APP](https://nextssh.app)

> 如果你是Termius的粉丝，那么它绝对是你的菜。颜值功能集于一身的强大SSH客户端，同时也是macOS用户的最爱，没有之一。

Electerm：[Github Source](https://github.com/electerm/electerm)

> 目前最好的开源SSH客户端，想要的功能一样不少，对安全隐私有较高要求的用户首选。

## 其他常见流媒体脚本链接

DisneyPlus 解锁检测： https://github.com/sjlleo/VerifyDisneyPlus

Youtube 缓存节点、地域信息检测：https://github.com/sjlleo/TubeCheck

Cloudflare Warp 一键脚本（[@missuo](https://github.com/missuo)）：https://github.com/missuo/CloudflareWarp

* **特色：简洁轻量，更为适合那些不想折腾的轻度用户使用**
