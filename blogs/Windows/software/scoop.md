---
title: Scoop 
date: 2022-04-23
categories: Windows
tags:
 - Scoop
---

## 安装

允许PowerShell执行本地脚本

```powershell
set-executionpolicy remotesigned -scope currentuser
```

配置安装目录（可选）

```powershell
# Scoop 安装目录
$env:SCOOP='D:\Applications\Scoop'
[Environment]::SetEnvironmentVariable('SCOOP', $env:SCOOP, 'User')


# Scoop 全局软件安装目录
$env:SCOOP_GLOBAL='F:\GlobalScoopApps'
[Environment]::SetEnvironmentVariable('SCOOP_GLOBAL', $env:SCOOP_GLOBAL, 'Machine')
```

安装

```powershell
iex (new-object net.webclient).downloadstring('https://get.scoop.sh') 
or
iwr -useb get.scoop.sh | iex
```

GitHub访问不畅时，可能下载会不成功 。[GitHub 加速](https://github.com/521xueweihan/GitHub520)

## 仓库

- [scoop-directory](https://rasa.github.io/scoop-directory/by-apps)
- [netlify](https://scoop.netlify.app/buckets/)

## 设置代理

```powershell
# 设置
scoop config proxy 127.0.0.1:7891
# 取消
scoop config rm proxy
```

## 常用命令


```powershell
# 添加仓库
scoop bucket add <app>
# 仓库
scoop bucket rm <app>
# 查看已安装仓库
scoop bucket list
# 查询官方仓库
scoop bucket known
# 检查潜在问题
scoop checkup 
# 查询库里面是否有这个软件
scoop search <app>   
# 安装软件
scoop install <app>  
# 卸载软件
scoop uninstall <app>  
# 更新软件
scoop update <app>  
# 更新所有软件
scoop update *
# 删除已安装软件的旧版本
scoop cleanup <app>
# 删除所有旧版软件
scoop cleanup *
# 禁止某程序更新
scoop hold <app>
# 允许某程序更新
scoop unhold <app> 
# 查看软件信息
scoop info <app> 
# 查看已安装应用
scoop list
# 移除某个app的缓存
scoop cache rm <app>
# 查看配置
scoop config
# 切换软件的版本
scoop reset <app>[@<version>]
```

## 软件

```powershell
# aria2进行多线程下载
scoop install aria2 
# aria2 配置
scoop config aria2-enabled true
scoop config aria2-retry-wait 4
scoop config aria2-split 16
scoop config aria2-max-connection-per-server 16
scoop config aria2-min-split-size 4M

# 搜索功能增强
scoop install scoop-search

# terminal 美化
scoop install starship

# jdk8
scoop install openjdk8-redhat

# python
scoop python

# node14
scoop install nodejs14

# maven
scoop install maven

# frp
scoop install frp

# typora
scoop install typora

# clash
scoop install clash-for-windows

# idea
scoop install idea-ultimate

# vscode
scoop install vscode

# datagrip
scoop install datagrip

# apifox
scoop install apifox

# grep
scoop install grep

# git
scoop install git

# powershell
scoop install powershell

# utools
scoop install utools

# nodejs
scoop install nodejs16

# sublime
scoop install sublime-text
```

## 卸载

```shell
scoop uninstall scoop
```

