在Archlinux及其衍生发行版上运行迅雷极速版
=======

Deepin打包的迅雷极速版容器移植到Archlinux，不依赖`deepin-wine`

<p align="center">
  <a href="https://travis-ci.org/countstarlight/deepin-wine-thunderspeed-arch">
    <img src="https://travis-ci.org/countstarlight/deepin-wine-thunderspeed-arch.svg?branch=master" alt="Build Status">
  </a>
  <a href="https://aur.archlinux.org/packages/deepin-wine-thunderspeed/">
    <img src="https://img.shields.io/aur/version/deepin-wine-thunderspeed.svg" alt="AUR Version">
  </a>
  <a href="https://github.com/countstarlight/deepin-wine-thunderspeed-arch/releases">
    <img src="https://img.shields.io/github/downloads/countstarlight/deepin-wine-thunderspeed-arch/total.svg" alt="GitHub Release">
  </a>
  <a href="https://github.com/countstarlight/deepin-wine-thunderspeed-arch/issues">
    <img src="https://img.shields.io/github/issues/countstarlight/deepin-wine-thunderspeed-arch.svg" alt="GitHub Issues">
  </a>
</p>

<!-- TOC -->

- [安装](#安装)
    - [从AUR安装](#从aur安装)
    - [从GitHub Release 安装](#从github-release-安装)
    - [从源码安装](#从源码安装)
- [常见问题](#常见问题)
- [感谢](#感谢)
- [更新日志](#更新日志)

<!-- /TOC -->

## 安装

`deepin-wine-thunderspeed`依赖`Multilib`仓库中的`wine`，`wine_gecko`和`wine-mono`，Archlinux默认没有开启`Multilib`仓库，需要编辑`/etc/pacman.conf`，取消对应行前面的注释([Archlinux wiki](https://wiki.archlinux.org/index.php/Official_repositories#multilib)):

```diff
# If you want to run 32 bit applications on your x86_64 system,
# enable the multilib repositories as required here.

#[multilib-testing]
#Include = /etc/pacman.d/mirrorlist

-#[multilib]
-#Include = /etc/pacman.d/mirrorlist
+[multilib]
+Include = /etc/pacman.d/mirrorlist
```

### 从AUR安装

已添加到AUR [deepin-wine-thunderspeed](https://aur.archlinux.org/packages/deepin-wine-thunderspeed/)，可直接安装:

```shell
yaourt deepin-wine-thunderspeed
```

### 从GitHub Release 安装

> 由[Travis CI](https://travis-ci.org/countstarlight/deepin-wine-thunderspeed-arch)在Docker容器[mikkeloscar/arch-travis](https://hub.docker.com/r/mikkeloscar/arch-travis)中自动构建的ArchLinux安装包

在[GitHub Release](https://github.com/countstarlight/deepin-wine-thunderspeed-arch/releases)页面下载 `.pkg.tar.xz`后缀的安装包，使用`pacman`安装：

```bash
sudo pacman -U #下载的包名
```

### 从源码安装

```shell
 git clone https://github.com/countstarlight/deepin-wine-thunderspeed-arch.git

 cd deepin-wine-thunderspeed-arch
  
 makepkg -si
```

* 运行应用菜单中创建的Thunder Speed启动
* 默认使用文泉驿微米黑(`wqy-microhei`)字体，要使用其他字体，如 微软雅黑或者微软宋体放进`～/.deepinwine/Deepin-ThunderSpeed/drive_c/windows/Fonts`中。

## 常见问题

- [x] 1.解决在 2k/4k 屏幕下字体和图标都非常小, 参见[issue1](https://github.com/countstarlight/deepin-wine-tim-arch/issues/1)

## 感谢

* [Wuhan Deepin Technology Co.,Ltd.](http://www.deepin.org/)

## 更新日志

* 2019-01-06 deepin.com.thunderspeed_7.10.35.366deepin18
* 2018-01-04 deepin.com.thunderspeed_7.10.35.366deepin17