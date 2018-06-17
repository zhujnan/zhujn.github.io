---
layout: post
title:  "learn docker"
date:   2018-06-17 15:33:52
categories: docker
tags: docker
excerpt: docker learning note
mathjax: true
---
# docker 基础学习

    docker由docker server和dockerclient组成
    dockre有三大组件：
        镜像（image）
        容器（container）   #容器和操作系统是相互隔离的，容器彼此之间也是相互隔离的
        仓库（repository）

## 1 在centos 7 上安装docker（学习环境为centos 7，暂时不讨论其他方法安装docker）

### 1.1 Docker 要求 CentOS 系统的内核版本高于 3.10 ，查看本页面的前提条件来验证你的

CentOS 版本是否支持 Docker 。
通过 uname -r 命令查看你当前的内核版本

    # uname -r

### 1.2 使用 root 权限登录 Centos。确保 yum 包更新到最新。

    # yum update

### 1.3 卸载旧版本

    # yum remove docker  docker-common docker-selinux docker-engine

### 1.4 安装需要的软件包， yum-util 提供yum-config-manager功能，另外两个是devicemapper驱动依赖的

    # yum install -y yum-utils device-mapper-persistent-data lvm2

### 1.5 设置yum源

    # yum-config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo

### 1.6 可以查看所有仓库中所有docker版本，并选择特定版本安装

    # yum list docker-ce --showduplicates | sort -r

###  1.7 安装docker

    # yum install docker-ce  #由于repo中默认只开启stable仓库，故这里安装的是最新稳定版
    # yum install <FQPN>  # 例如：sudo yum install docker-ce-17.12.0.ce

### 1.8 启动并加入开机启动

    # systemctl start docker
    # systemctl enable docker

### 1.9 验证docker版本

    # docker version

## 2 使用镜像
