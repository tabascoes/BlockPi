# BlockPi

**注：著者自身(@alienzhangyw)が転職して教育業界を離れたため、長期休暇をとらない限り、勤務時間を維持する時間とエネルギーがありません。 したがって、このは半放棄された状態にあり、新機能の更新は非常に遅くなり、保証はありません。**

**注意：由于作者本人(@alienzhangyw)已转行离开教育行业，平时工作时间也没有时间精力维护，除非放长假。因此此仓库处于半废弃状态，新功能更新会非常慢，并且不做保证。**

**Notice: This repo is semi-deprecated due to the author's(@alienzhangyw) new job. Updates are slow and not promised.**

[Google Blockly](https://developers.google.com/blockly/)上に構築された[Raspberry Pi](https://www.raspberry.org)用のビジュアルプログラミングエディターアプリ。RPiユーザーや子供がコーディングを学ぶために作成されました。

一个专门为[树莓派](https://www.raspberry.org)设计的图形化编程平台，基于[Google Blockly](https://developers.google.com/blockly/)构建，适用于树莓派爱好者或者少儿编程学习。

A visual programming editor app for [Raspberry Pi](https://www.raspberry.org), built on [Google Blockly](https://developers.google.com/blockly/), made for RPi users or kids to learn coding.

![](https://github.com/alienzhangyw/BlockPi/wiki/images/README.png)

## 特徴/特点/Features

- すべてのBlocklyはRaspberryPi上で無料で使用できます。  
完整的Blockly移植到树莓派上，完全免费使用。  
Full Blockly features on RPi, free to use.

- GPIOの制御や、[Sense HAT](https://www.raspberrypi.org/products/sense-hat/)、CSI Picamera、そして将来のより多くの機能への対応。  
集成树莓派GPIO控制，支持[Sense HAT](https://www.raspberrypi.org/products/sense-hat/)和CSI摄像头，未来支持更多树莓派外设和功能。  
Build-in GPIO control, [Sense HAT](https://www.raspberrypi.org/products/sense-hat/) and CSI Picamera support, and more functions in the future.

- コードはアプリ上で実行が可能で、Pythonへ変換することも可能です。Pythonを学習するのに役立ちます。  
程序可直接在应用内运行，同时可转化成Python代码，方便学习Python。  
Code runs in the app, and can be convert to Python. Helpful to learn Python.

- 英語、簡体字/繁体字中国語そして日本語に対応しています。支持繁简体中文、英语、日语。Localization for English, Simplified/Traditional Chinese and also Japanese.

- 支持保存、载入程序。Support save&load codes.

## 前置需求/Requirements

安装好官方最新[Raspberry Pi OS](https://www.raspberrypi.org/software/operating-systems/)桌面系统（Raspberry Pi OS with desktop and recommended software）的树莓派（4B、3、3B、3B+等有40pin GPIO的型号）。

A Raspberry Pi with 40pin GPIO(4B, 3, 3B, 3B+...), with [Raspberry Pi OS](https://www.raspberrypi.org/software/operating-systems/) with desktop and recommended software installed.

如果不是，请确保树莓派系统中安装了Nodejs 12以上的版本和Python 3。

If not, please make sure your Linux-based RPi system have Nodejs v12+ and Python 3 installed.

## 安装/Install

在[release](https://github.com/alienzhangyw/BlockPi/releases)页面下载最新版deb（推荐）或者AppImage安装包，保存到你的树莓派上。Download the latest release on the [release](https://github.com/alienzhangyw/BlockPi/releases) page, choose deb(recommended) or AppImage, save it to your RPi.

### deb

- 双击deb文件直接安装。Double click the deb file to install.

- 或者使用用终端命令：Or you can use command in shell:

```shell
sudo dpkg -i blockpi_1.1.5_armv7l.deb
```

注意自己的文件名。Pay attention to your file name.

如果安装失败，通常是系统内缺少必要模块导致的，输入

```shell
sudo apt install -f
```

安装模块后重新输入安装命令。

**！中国用户可能需要使用国内的Linux镜像源，请自行更改。**

If failed to install. it's usually caused by the lack of some packages, try input

```shell
sudo apt install -f
```

to install them and then try the dpkg command again.

### AppImage

先下载运行requirements.sh文件。First, download the requirements.sh file and run it.

右键AppImage文件，选择文件属性-权限-执行-所有人，确定。Right-click the AppImage file, choose file properties-permittions-execute-everyone, confirm.

双击直接运行程序。Double-click to run the APP.

如果不是官方最新系统，可能需要手动安装前置包：If your system is not the latest Raspbian, you may have to install some packages manually first:

```shell
sudo apt update
sudo apt install python3-gpiozero sense-hat python3-sense-emu sense-emu-tools python3-picamera
```

### Windows x64

下载安装包安装，在Windows上运行，可以正常编程，但是无法运行和树莓派硬件相关的程序。Download the installer and run it. You can program on Windows version but can't run any code related to RPi hardware.

## 未来计划/Future plans

- [ ] UART、IIC、SPI设备支持，比如~~数码管~~、LCD/OLED屏幕。UART, IIC, and SPI devices support, e.g. ~~LED segments~~, LCD/OLED screen...

- [ ] 更多Python功能和模块，比如~~字典~~、爬虫、图片处理、Turtle等。More Python functions and modules like ~~dictionary~~, http requests, pictures, and even Turtle.

- [ ] 人工智能 AI

- [ ] ……

## 开发/Develop

需要NodeJS 12以上稳定版，以及npm或者Yarn（推荐Yarn）。Need NodeJS v12 LTS+ and npm or Yarn(recommended).

克隆仓库/Clone repo：

```shell
git clone https://github.com/alienzhangyw/BlockPi.git
```

安装/Install:

```shell
cd BlockPi
yarn install
```

关于如何创建新积木，可以参考[谷歌Blockly的文档](https://developers.google.com/blockly/guides/create-custom-blocks/overview)。View [Google Blockly’s docs](https://developers.google.com/blockly/guides/create-custom-blocks/overview) can help you create new blocks.

打包所有积木脚本/Build all blocks:

```shell
yarn build:blocks
```

打包Python代码生成脚本/Build Python code generator:

```shell
yarn build:generator
```

运行BlockPi/Run BlockPi:

```shell
yarn start
```

打包发行Windows版本/Pack and build Windows version:

```shell
yarn dist:win
```

打包发行树莓派版本/Pack and build RPi versions:

```shell
yarn dist:linux
```

树莓派版本只能在非arm架构的Linux系统（如Ubuntu或WSL）打包，遇到权限问题需要在命令前加上sudo。RPi versions only can be build on none-arm Linux system such as Ubuntu or WSL. You may need 'sudo' if meet permission issues.

## FAQ

1. Q：软件收费吗？Is this app free？
   
   A：不，完全免费。Yes, it's totally free!

2. Q：和树莓派上自带的Scratch3有什么区别？What's the difference between BlockPi and Scratch3 on Raspbian?
   
   A：BlockPi能够生成Python代码，未来会更新更多Scratch3上没有的功能，更多传感器设备支持和人工智能功能。BlockPi can generate Python code. In the future, I will update more features than Scratch3, more sensor device support and even AI functions.

3. Q：有使用说明或者教程吗？Any tutorials?
   
   A：在项目[Wiki](https://github.com/alienzhangyw/BlockPi/wiki)页面有持续更新一些教程和案例，也可以关注我的知乎专栏[BlockPi树莓派图形化编程](https://zhuanlan.zhihu.com/BlockPi)。I keep updating some tutorials on the [Wiki](https://github.com/alienzhangyw/BlockPi/wiki) page.
