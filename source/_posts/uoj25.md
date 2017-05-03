---
title: 【UOJ25】【IOI2014】Wall
date: 2017-03-28 10:32:49
mathjax: true
toc: false
tags:
- 线段树
---
线段树即可。

<!-- more -->

We need to build a wall!（雾）

标记：$(l,r)$表示将小于$l$的数变为$l$，大于$r$的数变为$r$，其余的数不变。显然对$x$取`min`就是$(0,x)$，对$x$取`max`就是$(x,INF)$。

$$
(l1,r1)+(l2,r2) =
\begin{cases}
(l2,l2), & \text{if $r1<l2$} \\\\
(r2,r2), & \text{if $r2<l1$}  \\\\
(\max(l1,l2),\min(r1,r2)), & \text{otherwise} \\\\
\end{cases}
$$

其中$(l1,r1)$先执行，$(l2,r2)$后执行。

直接上线段树，最后`dfs`一遍算出答案即可。

[Code](https://github.com/q234rty/OJ-Codes/blob/master/UOJ/25.cpp)

