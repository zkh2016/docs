# macOS下的Conda安装

[Anaconda](https://www.anaconda.com/)是一个免费开源的Python和R语言的发行版本，用于计算科学，Anaconda致力于简化包管理和部署。Anaconda的包使用软件包管理系统Conda进行管理。Conda是一个开源包管理系统和环境管理系统，可在Windows、macOS和Linux上运行。

## 一、环境准备

在进行PaddlePaddle安装之前请确保您的Anaconda软件环境已经正确安装。软件下载和安装参见Anaconda官网(https://www.anaconda.com/)。在您已经正确安装Anaconda的情况下请按照下列步骤安装PaddlePaddle。

* macOS 版本 10.11/10.12/10.13/10.14 (64 bit) (不支持GPU版本)
* conda 版本 4.8.3+ (64 bit)

### 1.1 创建虚拟环境

#### 1.1.1 安装环境

首先根据具体的Python版本创建Anaconda虚拟环境，PaddlePaddle的Anaconda安装支持以下五种Python安装环境。


如果您想使用的python版本为3.6:

```
conda create -n paddle_env python=3.6
```

如果您想使用的python版本为3.7:

```
conda create -n paddle_env python=3.7
```

如果您想使用的python版本为3.8:

```
conda create -n paddle_env python=3.8
```

如果您想使用的python版本为3.9:

```
conda create -n paddle_env python=3.9
```


#### 1.1.2进入Anaconda虚拟环境

```
conda activate paddle_env
```


## 1.2其他环境检查

确认Python和pip是64bit，并且处理器架构是x86_64（或称作x64、Intel 64、AMD64）架构，目前PaddlePaddle不支持arm64架构。下面的第一行输出的是"64bit"，第二行输出的是"x86_64（或x64、AMD64）"即可：

```
python -c "import platform;print(platform.architecture()[0]);print(platform.machine())"
```

## 二、开始安装

本文档为您介绍conda安装方式

### 添加清华源（可选）

对于国内用户无法连接到Anaconda官方源的可以按照以下命令添加清华源。

```
conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/free/
conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/main/
conda config --set show_channel_urls yes
```

### 首先请您选择您的版本

* 目前在 macOS 环境仅支持 CPU 版 PaddlePaddle

### 根据版本进行安装

确定您的环境满足条件后可以开始安装了，选择下面您要安装的PaddlePaddle

* 请参考如下命令安装:

  ```
  conda install paddlepaddle --channel https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/Paddle/
  ```

## **三、验证安装**

安装完成后您可以使用 `python` 或 `python3` 进入python解释器，输入`import paddle` ，再输入
 `paddle.utils.run_check()`

如果出现`PaddlePaddle is installed successfully!`，说明您已成功安装。
