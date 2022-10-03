
# :four_leaf_clover:博白客语拼音输入法

博白客语拼音输入法是由作者本人`shuxiang` 哔哩哔哩账号 [shuxiang](https://space.bilibili.com/23428735) 制作完成

客语拼音主要来自本人的客语注音项目 [博白客语拼音方案](https://github.com/shuxiang/hakka-lang-bobai)

该拼音输入法在[四叶草输入法](https://github.com/fkxxyz/rime-cloverpinyin)的基础上制作而成.


## 使用方法
1. 安装rime输入法
2. 下载release包, 解压到rime输入法的配置目录
3. 设置rime "输入法设置" 选项为 "四叶草博白话简体拼音"
4. 点击rime "重新部署" 选项即可




------------------------------------------------- 以下内容不用看 ------------------------------------------------------


## 从本仓库源码构建

一般情况下，我在发布页提供的是已经生成好的词库和部署好的二进制文件，直接使用即可。

如果你想自己从零开始构建，或者想为别的 linux 发行版打包，那么继续往下看。

该仓库的内容只包含构建四叶草输入法方案的脚本，构建需要以下环境

操作系统： linux

python版本： 3

python依赖的库： [jieba](https://github.com/fxsjy/jieba)、[pypinyin](https://github.com/mozillazg/python-pinyin)、[opencc](https://github.com/BYVoid/OpenCC)、requests

下载工具（三者任意一个均可）： [aria2](http://aria2.sourceforge.net/)、[wget](https://www.gnu.org/software/wget/wget.html)、[curl](https://curl.haxx.se/)

解压工具（三者任意一个均可）： [unzip](https://www.info-zip.org/UnZip.html)、[bsdtar](https://libarchive.org/)、[7z](http://p7zip.sourceforge.net/)

rime基础库： [librime](https://github.com/rime/librime)

rime基础配置： [librime-prelude](https://github.com/rime/rime-prelude)

克隆此仓库，然后直接执行构建即可

```shell
./build
```

完成后，会生成 cache 目录和 data 目录

- data 是最终生成的目录
- cache 是生成过程中下载和生成的中间文件



其中，执行 build 时，可以有个参数

```shell
./build [minfreq]
```

minfreq 代表360万词里面指定的最小词频，频率低于该值的词语会被筛选掉，达到精简词库的目的，默认是100，该值越小，最终生成的词库越大，为 0 表示不精简词库（会生成大约 100 兆左右的词库）。

构建完成后，可以打包，在 data 目录生成发布用的压缩包

```
./pack [ver]
```

ver 表示版本号，例如 1.1.2



## nonsense
sudo apt-get install fcitx-rime
sudo apt-get install ibus-rime

-- to poem; bobai fix2 export opensource project; python3 test.py; ctrl h -> "(0x[a-z0-9]+)": $1:; pinyin_dict to src/pypinyin/pinyin_dict.py
-- to rime-cloverpinyin; ./build; ./pack 0.003; sh to_clover.sh; restart 小狼毫
