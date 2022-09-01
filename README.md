# bjoern-blogs

> 本仓库用于保存bjoern源码解析系列的博客

## 前言

我一直以来都有实现一个全功能web服务器的想法，奈何难度过大，计划多次搁浅。后来，在知乎读到了这篇[回答](https://www.zhihu.com/question/19589485/answer/12305131)，深以为然。于是，将目标改为先读懂一个web服务器源码。但大多数web服务器的源码都很庞大，在一番搜寻下，我找到了[bjoern](https://github.com/jonashaag/bjoern)。

经过统计，bjoern仅由16个文件、1553行代码组成。
```bash
      16 text files.
      16 unique files.                              
       0 files ignored.

-------------------------------------------------------------------------------
Language                     files          blank        comment           code
-------------------------------------------------------------------------------
C                                8            245            212           1333
C/C++ Header                     8             47              7            220
-------------------------------------------------------------------------------
SUM:                            16            292            219           1553
-------------------------------------------------------------------------------
```

你是不是已经开始兴奋了？但随着阅读的深入，我才发现bjoern源码的阅读难度并不低。

首先，bjoern是使用C语言编写的Python扩展模块，所以你必须了解C语言是如何与Python进行交互的（当然，你也必须熟练地掌握这两种编程语言）。其次，bjoern是基于[libev](https://github.com/enki/libev)与[http-parser](https://github.com/joyent/http-parser/tree/1786fdae36d3d40d59463dacab1cfb4165cf9f1d)的，所以你也必须了解libev和http-parser的相关概念和使用技巧。

你在阅读本系列博客之前，应该至少已经掌握了以下知识：
- 计算机网络基础（尤其是HTTP协议部分）
- Linux环境/网络编程基础
- WSGI协议
- libev和http-parser的使用
- CPython的C扩展接口的使用