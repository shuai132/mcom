找到了个替代minicom的工具`picocom`，完结散花：`https://github.com/npat-efault/picocom

截至目前(2024年10月24日)，在macOS Apple Silicon平台，一些串口工具和库（如c++ asio/rust mio-serial）对1500000等波特率支持有问题。
进而导致minicom等软件无法在这个波特率使用。

# mcom

串口调试工具 简化版的minicom

## Why

在macOS下，一直没有比较好用的图形化串口调试工具。尝试过很多论坛推荐的应用也是各有各的问题。连最基本的终端输入、复制、搜索、清屏等基本功能都非常难用。  
因此最佳的解决方案是使用minicom配合iTem2终端，能得到很好的使用体验。

minicom是一个广泛使用的串口调试工具，也曾经重度使用过，体验不错。  
但是最近发现在新版本的macOS总是遇到一些问题：打开慢、打印不显示、无法输入等。尤其是在调试Linux内核的时候，更是问题频出。用Windows或者其他调试工具都没有问题。

因此计划开发一个简化版本的minicom，支持类似的命令格式。  
为了避免二进制名称重复，取名为`mcom`。

```shell
mcom -D /dev/tty.usbserial-2130 -b 115200
```

## TODO

- [ ] macOS支持
- [ ] Linux支持
- [ ] 包管理安装
