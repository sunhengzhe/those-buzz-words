# 那些唬人的技术名词

这个项目解决以下问题：

- 有些词中文看起来很厉害，其实英文更容易理解
- 有些词缩写记不住，其实知道全写更容易记忆

## 正则

| 英文 | 中文 |
| --- | --- |
| lookaround | 环视 |
| lookahead | 顺序环视 |
| lookbehind | 逆序环视 |

**Lookaround**（环视）其实就是匹配某个位置。这个位置可能是左边有什么东西，或者右边有什么东西。

因为正则表达式是从左到右匹配的，所以找一个左边有什么的位置（朝左看）称为 **lookbehind**（逆序环视），朝右边看为 **lookahead**（顺序环视）。

> 比如 `find me, not me!` 里要匹配 find 后面的 me，而不是 not 后面的 me，那么可以使用 `(?<=find )me`（左边有 find），或者 `me(?=,)`（右边有逗号）。

| 英文 | 中文 |
| --- | --- |
| positive lookahead | 肯定顺序环视 |
| positive lookbehind | 肯定逆序环视 |
| negative lookahead | 否定顺序环视 |
| negative lookbehind | 否定逆序环视 |

除了 *有什么*，也可以匹配 *没什么*，所以分为了 **positive**（肯定）和 **negative**（否定）。肯定就是有，否定就是没有。上面的例子也称为 **positive lookbehind**（肯定逆序环视） 和 **positive lookahead**（肯定顺序环视）。

> 还是 `find me, not me!` 里要匹配 find 后面的 me，而不是 not 后面的 me，那么可以使用 `(?<!not )me`（左边不是 not），或者 `me(?!\!)`（右边不是感叹号）。

| 英文 | 中文 |
| --- | --- |
| zero-width positive lookahead assertion | 零宽正向先行断言 |
| zero-width positive lookbehind assertion | 零宽正向后行断言 |
| zero-width negative lookahead assertion | 零宽负向先行断言 |
| zero-width negative lookbehind assertion | 零宽负向后行断言 |

不得不说这是我见过的最唬人的翻译，实际上这四个名词对应的就是上面的四个环视。

**Lookaround**（环视）与匹配行开始（`$`）、行结尾（`^`）类似，它匹配的是一个位置，所以它是没有宽度的（zero width）。另外它只做匹配，不会包含在结果中，就如上面的例子，`me(?=,)` 的结果是不包含逗号的，它只是帮助你判断了 me 后面有没有逗号，所以环视是一种断言（assertion）。

那么你也就能理解为什么 **肯定顺序环视**（positive lookahead）会被称为 **零宽正向先行断言**（zero-width positive lookahead assertion）了。

## Redis

| 缩写 | 全写 |
| --- | --- |
| AOF | Append Only File |
| RDB | Redis Database Backup file |

AOF 和 RDB 是 redis 的两种持久化策略。

**Append Only File** 即每次操作完都往日志里添加（Append）一条记录，因为这个文件记录了历史的操作，所以根据这个文件，你总能恢复数据到指定位置的数据。

**Redis Database Backup file** 即数据库的备份文件（数据快照），可以每隔一段时间备份一次，那么根据这个文件，你总能恢复数据到一个固定时间点上。

## etcd

"etcd" 这个名字来源于两个想法，unix 的 "/etc" 目录和 "d"istibuted 系统（分布式系统）。"/etc" 目录是一个单一系统存放配置的地方，而 etcd 为大规模分布式系统存储配置。因此，"**d**" istributed "**/etc**" 就是 "etcd"。

> [原文](https://coreos.com/etcd/docs/latest/learning/why.html): The name "etcd" originated from two ideas, the unix "/etc" folder and "d"istibuted systems. The "/etc" folder is a place to store configuration data for a single system whereas etcd stores configuration information for large scale distributed systems. Hence, a "d"istributed "/etc" is "etcd".

## 函数

| 英文 | 中文 |
| --- | --- |
| Predicate | 谓词 |

谓词指的是一种返回 `true` 或 `false` 的函数，本质上含义就是“判断输入是否满足条件”。

## 算法

| 英文 | 中文 |
| --- | --- |
| Dynamic Programming | 动态规划 |
| Divide and Conquer | 分治法 |
