
<font  face="Times New Roman">

<div style="text-align: right">

*版权声明* © Copyright 2024 Boyer.
作者：Boyer 审稿：Lizer, Squareroot_2.

</div>

# Taller and Higher

&emsp;&emsp;<font face="楷体">源于生活, 高于生活.</font>

## 回顾
&emsp;&emsp;上次我们介绍了最基本的数学语言, 并亲自上手完成了一些命题或定理的证明。通过证明的过程我们感受到了来自数学世界的秩序, 已经来到了高山的山脚下。这座高山深入云巅, 奇幻莫测, 美丽至极, 我们将从山脚下的基石出发, 逐渐领略山中风景。

&emsp;&emsp;多少年来, 数学家们不断创造、维护甚至不断打破数学世界的秩序, 如此的反反复复这也才造就了如今如此辉煌的数学世界 —— 尽管她还不够完善, 但她一直在成长。


## Lesson 2 形式化的开端——命题逻辑和谓词逻辑

<!-- &emsp;&emsp;数学世界如此之大, 自然少不了用于构筑这些世界的数学工具, 本节我们讲介绍如下的一些数学工具：集合、函数、序列（数列）、归纳原理、递归定义。这些数学工具的理论基础为《集合论》, 即集合论公理系统保证了这些数学工具的存在和正确性, 虽然我们目前并不直接接触集合论公理系统, 但是着并不影响我们介绍和使用这些数学工具。
&emsp;&emsp;其中, 函数将在初一第一次接触；集合和数列会在高一第一次接触；归纳原理和递归定义会在竞赛和大学之后的课程反复使用。不同于课本教材, 本文更注重这些数学概念本身和其作用, 而不是解题技巧。所以请不要担心, 本文会从无到有, 一点点将这些数学工具建立起来。 -->


&emsp;&emsp;数学家们为了更加精确、统一地描述和研究问题, 创造了纯粹由数学符号描述的逻辑语言也叫形式化语言。与日常生活中的自然语言不同, 形式化语言是严谨的、精确的、毫不含糊的, 数学家们希望使用这一门语言实现把推理变为演算的想法。
&emsp;&emsp;我们即将接触到的, 是逻辑语言中最基础的：命题逻辑和谓词逻辑, 也称命题演算和谓词演算。除此之外, 逻辑语言还包括描述能力更强的高阶逻辑, 与之相对地, 命题逻辑也称零阶逻辑, 谓词逻辑也称一阶逻辑。
&emsp;&emsp;一阶逻辑是数学基础中很重要的一部分, 许多公理系统都将一阶逻辑系统作为自己的公理之一。但由于普遍使用的一阶逻辑公理本身较为抽象不易理解, 为了方便理解, 我们将以更加形象的 *自然演绎系统* 的11条演绎规则作为公理, 并以此代替原有的3条模式公理和一条推理规则来介绍一阶逻辑系统。

<div style="page-break-after: always;"></div>

### 2.1 命题逻辑
&emsp;&emsp;在上一节中, 我们已经接触过了基本的命题、证明等数学概念, 现在我们将进一步将命题“符号化”, 证明“运算化”。即从现在起, 一个变量$x$不再仅仅代表一个未知数或者数字的变量, 她可以代表一个命题；一个计算过程不仅仅是数字间的运算, 她还可以代表一个证明的推理过程。

#### 2.1.1 命题的再认识
&emsp;&emsp;上一节中我们已经接触过命题了, 命题指的是**具有真假意义的陈述句**。如：
**命题2.1** 如果现在是下雨天, 那么现在天上有乌云。
**命题2.2** 现在是下雨天。
**命题2.3** 现在天上有乌云。
&emsp;&emsp;值得注意的是, 上述的三个命题具有一定的关系：**命题2.2**和**命题2.3**都是**命题2.1**的一部分, 这叫命题之间的复合关系。如果**命题2.1**和**命题2.2**同时为真, 那么我可以得到**命题2.3**为真的结论, 这叫命题间的因果关系。
&emsp;&emsp;直观上来理解因果关系, 如果没有**命题2.1**为**真**的前提条件, 仅仅从**命题2.2**为真出发, 我们无法得到**命题2.3**为真的结论。但是如果**命题2.1**是真的, 那么当命题**命题2.2**为真时就能自然而然的推导出**命题2.3**为真了。

&emsp;&emsp;在命题逻辑中, 我们更关注“证明”本身, 即“推理”, 我们会将命题间的推理抽象成一种演算, 从而在一定程度上忽略一个命题原本自身的意义。我们重新考虑上述命题：
**命题2.1** $P \rightarrow Q$
**命题2.2** $P$
**命题2.3** $Q$

&emsp;&emsp;无论$P$和$Q$换成其他什么命题, 在因果关系$P \rightarrow Q$为真的情况下, 只要$P$为真, 那么$Q$就是真命题。
&emsp;&emsp;在习惯上, 我们会使用一个大写的英文字母来表示命题, 例如：用$B$表示命题“北京是中国的首都”、用$R$表示“雪是黑色的”等。在这里由于我们只重点关注命题间的关系（各种各样的复合和因果）, 而尽量忽略命题本身, 于是上面三条命题中的$P$,$Q$可以换成任何命题, 你可以将一个真命题放到$P$中, 也可以将一个假命题放到$P$中。
&emsp;&emsp;这时命题中的每一个字母称为**命题变元**或**变量**, 我们可以对每一个变量赋值(取值)$\text{True}$或者$\text{False}$(真或假), 对某一命题中的所有变量都进行赋值的一个方案称为一个**指派**。也就是说, 在这里$P$和$Q$仅仅只是一个变量, 就如同解方程中的$x$一般, 不过每一个命题变量只能取值True或者False意味着真或者假, 别无其它。
&emsp;&emsp;例如 $\text{True} \rightarrow \text{True}$, $\text{False} \rightarrow \text{True}$ 都是**命题2.1**的指派。

#### 2.1.2 命题的运算 —— 联结词
&emsp;&emsp;上面我们已经简单的接触到命题之间的复合结构了, 在这里我们将更加详尽的研究命题之间的因果关系。
&emsp;&emsp;给出公理之前, 我们定义公理中将使用的一些符号。对于这些符号的含义, 我们将使用**真值表**来进一步解释, 真值表的左边**穷举**了所有可能**指派**, 右边是某些我们关注的式子在**对应指派**下的取值。

**定义2.1**(否定, 非): 设$P$是一个命题, “$P$的否定”是一个命题, 记作$\neg P$, 这两个命题总是真假相反。$\neg P$常读作“非$P$”。
&emsp;&emsp;$P$与$\neg P$的因果关系可以用如下真值表进行表述：
<div style="text-align: center;">

|$P$     | $\neg P$     |
| -------- | -------- | 
| False | True | 
| True | False | 

</div>

&emsp;&emsp;表格的左边是$P$的所有可能出现情况, 表格的右边是$\neg P$对于$P$所有可能出现情况的因果关系。
&emsp;&emsp;例如：**命题2.2**中, $P$表示“现在是下雨天”, 那么$\neg P$就表示“现在不是下雨天”。

**定义2.2**(析取, 或): 设$P$, $Q$为两个命题, “$P$, $Q$的析取”是一个命题, 记作$P \vee Q$。如果$P$和$Q$中至少有一个命题是真的, 那么$P\vee Q$就是真的; 反过来也一样, 如果$P\vee Q$是真的, 那么$P$和$Q$中至少有一个命题是真的。$P \vee Q$常读作“$P$或$Q$”。
&emsp;&emsp;$P$,$Q$与$P\vee Q$的因果关系可以用如下真值表进行表述：
<div style="text-align: center;">

|$P$|$Q$     | $P\vee Q$     |
|-| -------- | -------- | 
| False | False | False | 
| False | True | True | 
| True | False | True | 
| True | True | True | 

</div>

&emsp;&emsp;表格的左边两列是$P$和$Q$的所有可能出现情况的组合, 表格的右边是$P\vee Q$对于$P$和$Q$的所有可能出现情况的因果关系。

&emsp;&emsp;例如：用$P$表示“现在是下雨天”, 用$Q$表示“现在是大风天”, 那么$P\vee Q$就表示“现在是下雨天或刮风天”, 其为真命题时现在可以只下雨, 可以只刮风, 也可以既刮风又下雨。

**定义2.3**(合取, 且): 设$P$, $Q$为两个命题, “$P$, $Q$的合取”是一个命题, 记作$P \wedge Q$。如果$P$和$Q$都是真的, 那么$P\wedge Q$就是真的; 反过来也一样, 如果$P\wedge Q$是真的, 那么$P$和$Q$都是真的。$P \wedge Q$常读作“$P$且$Q$”。
&emsp;&emsp;$P$,$Q$与$P\wedge Q$的因果关系可以用如下真值表进行表述：
<div style="text-align: center;">

|$P$|$Q$     | $P\wedge Q$     |
|-| -------- | -------- | 
| False | False | False | 
| False | True | False | 
| True | False | False | 
| True | True | True | 

</div>

&emsp;&emsp;例如：用$P$表示“现在是下雨天”, 用$Q$表示“现在是大风天”, 那么$P\wedge Q$就表示“现在是下雨天同时也是刮风天”, 其为真命题时现在既刮风又下雨。

**定义2.4**(蕴涵, 推出): 设$P$, $Q$为两个命题, “$P$蕴涵$Q$”是一个命题, 记作$P \rightarrow Q$。如果$P$为真时$Q$一定为真($P$为假时对$Q$没有任何限制), $P \rightarrow Q$为真; 反过来, 如果$P \rightarrow Q$为真, 那么$P$为真时$Q$一定为真($P$为假时对$Q$没有任何限制)。$P \rightarrow Q$常读作“如果$P$则$Q$”。
&emsp;&emsp;$P$,$Q$与$P\rightarrow Q$的因果关系可以用如下真值表进行表述：
<div style="text-align: center;">

|$P$|$Q$     | $P\rightarrow Q$     |
|-| -------- | -------- | 
| False | False | True | 
| False | True | True | 
| True | False | False | 
| True | True | True | 

</div>

&emsp;&emsp;从真值表中可以看出, $P\rightarrow Q$ 为真而$P$为假时, $Q$可真可假。这里可能有些抽象, 我们结合之前的例子来帮助理解。 
&emsp;&emsp;继续考虑**命题2.1**、**命题2.2**、**命题2.3**。当**命题2.1**为真时, 下雨一定有乌云($P$为真时$Q$一定为真), 不下雨时可能有乌云也可能没有乌云($P$为假时对$Q$没有任何限制), 也就是不下雨时有没有乌云并不影响我们要表述的因果关系。

**定义2.5**(等价, 当且仅当): 设$P$, $Q$为两个命题, “$P$等价于$Q$”是一个命题, 记作$P \leftrightarrow Q$。如果$P$和$Q$总是真假相同, 那么$P \leftrightarrow Q$为真; 反过来也一样, 如果$P \leftrightarrow Q$为真, 那么$P$和$Q$总是真假相同。$P \leftrightarrow Q$常读作“$P$当且仅当$Q$”, 也常直接读“$P$等价于$Q$”。
&emsp;&emsp;$P$,$Q$与$P\leftrightarrow Q$的因果关系可以用如下真值表进行表述：
<div style="text-align: center;">

|$P$|$Q$     | $P\leftrightarrow Q$     |
|-| -------- | -------- | 
| False | False | True | 
| False | True | False | 
| True | False | False | 
| True | True | True | 

</div>

&emsp;&emsp;例如：用$P$表示“现在是下雨天”, 用$Q$表示“现在是大风天”, 那么$P\leftrightarrow Q$就表示“现在是下雨天当且仅当现在也是刮风天”, 其为真命题时, 要么现在既刮风又下雨, 要么两者都不。

#### 2.1.3 更复杂的命题 —— 复合, 命题公式
&emsp;&emsp;我们已经知道, 两个命题可以通过联结词构成一个新的命题, 这就意味着我们可以从一些初始命题出发, 不断使用联结词反复套娃, 以此构建更多复杂的命题。

**定义2.6**(命题公式): 我们采用**递归定义**：

* True和False是命题公式。 
* 命题变量是命题公式。如：$P$, $Q$等。
* 如果$A$, $B$是命题公式, 那么$(\neg A)$、$(A\vee B)$、$(A\wedge B)$、$(A\rightarrow B)$、$(A\leftrightarrow B)$都是命题公式。
* 任何命题公式都由上述有限次复合得到。

&emsp;&emsp;于是我们的系统逐渐复杂起来：
$$
(((P\vee Q)\rightarrow W)\leftrightarrow (\neg X\wedge (Q \rightarrow P)))\\
((((A_0 \vee A_1) \vee A_2) \vee A_3) \vee A_4)\\
(B_0 \rightarrow (B_1 \rightarrow (B_2 \rightarrow (B_3 \rightarrow B_4))))\\
((\text{True} \vee \text{False}) \leftrightarrow \text{True})
$$&emsp;&emsp;这些都是命题公式, 每一条都是由若干命题复合成的命题, 当然它们可能是真命题也可能是假命题。

&emsp;&emsp;在实际使用时, 为了方便的书写, 我们引入以下约定来减少括号的数量, 其目的仅仅为了书写方便, 在容易引起歧义的地方我们还是要勤用括号。
- 最外层的括号可以省略。
- 对逻辑联结词规定优先级, 就像乘法优先级比加法高那样, 我们约定逻辑联结词按优先级从高到低的顺序依次排列为：
$$
\neg            \space\space\space\space\space\space 
\wedge          \space\space\space\space\space\space 
\vee            \space\space\space\space\space\space 
\rightarrow     \space\space\space\space\space\space 
\leftrightarrow
$$&emsp;&emsp;当遇到同一种联结词, 通常情况下从左往右运算即可, 其理论基础为**结合律**, 但是注意联结词$\rightarrow$并不满足结合律, 所以连续的$\rightarrow$括号不可以轻易删除。关于结合律我们会在稍后讨论。
&emsp;&emsp;按照这样的书写逻辑我们可以把上面的命题公式稍微减少一些括号：
$$
P\vee Q\rightarrow W\leftrightarrow \neg X\wedge (Q \rightarrow P)\\
A_0 \vee A_1 \vee A_2 \vee A_3 \vee A_4\\
B_0 \rightarrow (B_1 \rightarrow (B_2 \rightarrow (B_3 \rightarrow B_4)))\\
\text{True} \vee \text{False} \leftrightarrow \text{True}
$$

&emsp;&emsp;再次提醒, 减少括号目的仅仅为了书写方便, 在容易引起歧义的地方我们还是要勤用括号。在不确定的时候删除括号有可能导致命题的改变, 就如同$5\times 3+2$ 不能写成$5\times(3+2)$一样。


&emsp;&emsp;在这里, 我们将注意力放到一些特殊的公式上：

**定义2.7**(永真式): 设$A$为一个命题公式($A$可能非常复杂), 如果$A$在所有指派下均为真, 即$A\leftrightarrow \text{True}$为真命题, 那么称$A$为永真式。有些书籍也将永真式称为重言式。$\text{True}$是最简单的永真式。
**定义2.8**(永假式): 设$A$为一个命题公式($A$可能非常复杂), 如果$A$在所有指派下均为假, 即$\neg (A\leftrightarrow \text{True})$为真命题,  那么称$A$为永假式。有些书籍也将永假式称为矛盾式。$\text{False}$是最简单的永假式。
**定义2.9**(等价公式): 设$A, B$是两个命题公式(可能很复杂), 如果$A \leftrightarrow B$为永真式, 则称$A, B$互为等价公式, 记$A = B$。
**定义2.10**(子公式): 设$a, A$是命题公式, 如果$a$是$A$的一部分, 则称$a$是$A$的子公式。例如：$P$和$P\rightarrow Q$都是$P\rightarrow (P\rightarrow Q) $的子公式, 每个公式都是自己的子公式。

#### 2.1.4 自然演绎系统
&emsp;&emsp;我们已经较为全面的认识了什么是命题, 以及了解了如何用联结词构造更复杂的命题, 现在我们将给出自然演绎系统的推理规则并把它们作为公理, 以此构建我们的命题逻辑公理系统即零阶逻辑系统。
&emsp;&emsp;自然演绎系统定义了一套推理规则, 每一个推理规则可以从一组真命题中得到另一条真命题。关于推理规则, 我们引入两个新的符号：
**定义2.11**(语义后承 $\models$)设一组命题$q_0, q_1,..., q_n, Q$, 如果$q_0, q_1,..., q_n$ 都为真时, $Q$一定为真, 那么称$Q$是$q_0, q_1,..., q_n$的语义后承, 记$\{q_0, q_1,..., q_n\}\models Q$。
**定义2.12**(句法后承 $\vdash$)设一组命题$q_0, q_1,..., q_n, Q$, 如果$q_0, q_1,..., q_n$ 都为真时, **可以证明**$Q$一定为真, 那么称$Q$是$q_0, q_1,..., q_n$的句法后承, 记$\{q_0, q_1,..., q_n\}\vdash Q$。
&emsp;&emsp;这两个定义的区别仅为从前面的一组命题是否能证明后面的一个命题, 如果所有的真命题都可被证明, 那么这两个定义没有区别, 但遗憾的是, 在许多系统中总**存在不可证明的真命题**。不过不用担心, 这里介绍这两个概念只是为了方便给出我们的推理规则。
&emsp;&emsp;最朴素的理解, $\{A\} \models B$表明$A$为真那么$B$为真。$\{A\} \vdash B$表明$A$为真能证明$B$为真。

**公理2.1**(否定介入)$\{(p\rightarrow q), (p\rightarrow \neg q)\}\models \neg p$
&emsp;&emsp;这条公理表明, 如果一个命题能同时得出矛盾的结论, 那么它是假的。其中$\neg p$为真表示$p$为假。这也是**反证法**的理论依据。

**公理2.2**(否定消除)$\{\neg p\} \models (p \rightarrow r)$
&emsp;&emsp;这条公理表明假命题不具有任何因果关系。$p$是假的, 你可以随便说$p$对任何事情具有因果关系, 正是因为它是假的, 所以由**定义2.4**可知, 箭头之后的命题是完全没有限制的, 可真可假, 与$p$不具有任何因果关系。

**公理2.3**(双否定消除)$\{\neg \neg p \} \models p$
&emsp;&emsp;这条公理表明双重否定表肯定。

**公理2.4**(合取介入)$\{p, q\} \models (p \wedge q)$, $\{\}\models \text{True}$
**公理2.5**(合取消除)$\{p\wedge q\} \models p$ , $\{p\wedge q\} \models q$
&emsp;&emsp;这两条公理表明了合取的属性, 即“两者都为真”。推导的目标是从已知真命题得到新的真命题，对于第一条，我们总可以从虚无中推导出$\text{True}$, 因为$\text{True}$本就是真的。对于第二条, 两者同时为真时, 前者肯定为真, 后者也肯定为真。

**公理2.6**(析取介入)$\{ p\} \models (p \vee q)$, $\{ q\} \models (p \vee q)$
**公理2.7**(析取消除)$\{p \vee q, p \rightarrow r, q \rightarrow r\} \models r$, $\{ \text{False}\}\models r$
&emsp;&emsp;这两条公理表明了析取的属性, 即“两者至少一个为真”。对于第二条, $p$,$q$只要有一个为真, 那么$r$就为真。后半部分说明：如果虚假为真，则任何命题$r$为真。这句话表明了$\text{True}$和$\text{False}$是完全对立的，虚假永不为真；如果虚假为真，那么$\text{True}$和$\text{False}$等价，为我们讨论的一切命题都没有意义，都只会有唯一的一种指派(因为$\text{True}$和$\text{False}$是一样的), 这种情况下, 真就是假, 假就是真, 那么所有命题就都是真的了(也可以都是假, 反正没区别)。所以我们永远不允许推导出$\text{False}$(事实上我们的公理系统保证了这一点)。

**公理2.8**(等价介入)$\{p \rightarrow q, q \rightarrow p\} \models (p \leftrightarrow q)$
**公理2.9**(等价消除)$\{p \leftrightarrow q \} \models (p \rightarrow q)$,$\{p \leftrightarrow q \} \models (q \rightarrow p)$ 
&emsp;&emsp;这两条公理表明了等价的属性, 就是两个命题相互蕴涵对方。

**公理2.10**(条件消除)$\{p, p\rightarrow q\} \models q$
**公理2.11**(条件介入)$\{\{p\}\vdash q\} \models p\rightarrow q$
&emsp;&emsp;这两条公理表明了蕴涵的属性。对于第二条, 如果能用$p$证明$q$, 那么说$p$蕴涵$q$。


#### 2.1.5 常用等价公式和定理
&emsp;&emsp;到此, 我们了解了整个命题逻辑的系统结构, 现在就让我们基于这些公理和定义来研究这个系统到底包含了些什么东西, 以及我们要如何使用这个系统。

**定理2.1**(等价公式的性质): 设$A, B, C$是命题公式, 则有
(1)(自反性) $A=A$
(2)(交换性) $\{A=B\}\vdash (B=A)$
(3)(传递性) $\{A=B, B=C\}\vdash (A=C)$
&emsp;**证明：**
&emsp;&emsp;(1)
&emsp;&emsp;由**定义2.9** 只需证 $A \leftrightarrow A$是永真式。
&emsp;&emsp;由**定义2.7** 只需证 $(A \leftrightarrow A)\leftrightarrow\text{True}$为真
&emsp;&emsp;下面使用公理推出该公式

|编号|公式|原因|
|-|-|-|
|$1$|$A \leftrightarrow A$|假设|
|$2$|$\text{True}$|对$\{\}$使用**公理2.4**|
|$3$|$\{A \leftrightarrow A\}\vdash\text{Ture}$|总结(1)到(2)|
|$4$|$(A \leftrightarrow A)\rightarrow\text{Ture}$|对(3)使用**公理2.11**|
|$5$|$\text{True}$|假设|
|$6$|$A$|假设|
|$7$|$A\wedge \text{True}$|对(5)(6)使用**公理2.4**|
|$8$|$A$|对(7)使用**公理2.5**|
|$9$|$\{A\}\vdash A$|总结(6)到(8)|
|$10$|$A\rightarrow A$|对(9)使用**公理2.11**|
|$11$|$A\leftrightarrow A$|对(10)和(10)使用**公理2.8**|
|$12$|$\{\text{True}\}\vdash(A\leftrightarrow A)$|总结(5)到(11)|
|$13$|$\text{True}\rightarrow(A\leftrightarrow A)$|对(12)使用**公理2.11**|
|$14$|$(A \leftrightarrow A)\leftrightarrow\text{Ture}$|对(4)(13)使用**公理2.8**|

&emsp;&emsp;好了，现在每个公式等价于自己了。
&emsp;&emsp;注意，证明过程中的每一次**假设**会对应到一次**总结**，**总结**之前可以把假设作为真命题，**总结**时表明由假设得出的结论，从而得到假设命题蕴含结论命题的一个蕴含命题，这个命题就是我们得到的一个真命题，**但是总结过后不能再使用该假设**。如假设$P$，得到了$Q$，那么$P\rightarrow Q$是我们得到的真命题，但是$P$本身是否为真是未知的。


&emsp;&emsp;(2)假设$A=B$成立，我们需要证$B=A$成立
&emsp;&emsp;由**定义2.9**和**定义2.7**：我们只需假设$(A\leftrightarrow B)\leftrightarrow \text{True}$为真，推理出$(B\leftrightarrow A)\leftrightarrow \text{True}$为真即可
|编号|公式|原因|
|-|-|-|
|$1$|$(A\leftrightarrow B)\leftrightarrow \text{True}$|假设|
|$2$|$\text{True}$|假设|
|$3$|$\text{True}\rightarrow (A\leftrightarrow B)$|对(1)使用**公理2.9**|
|$4$|$A\leftrightarrow B$|对(2)(3)使用**公理2.10**|
|$5$|$A\rightarrow B$|对(4)使用**公理2.9**|
|$6$|$B\rightarrow A$|对(4)使用**公理2.9**|
|$7$|$B\leftrightarrow A$|对(5)(6)使用**公理2.8**|
|$8$|$\{\text{True}\}\vdash (B\leftrightarrow A)$|总结(2)到(7)|
|$9$|$\text{True}\rightarrow (B\leftrightarrow A)$|对(8)使用**公理2.11**|
|$10$|$B\leftrightarrow A$|假设|
|$11$|$\text{True}$|对$\{\}$使用**公理2.4**|
|$12$|$\{B\leftrightarrow A\}\vdash \text{True}$|总结(10)到(11)|
|$13$|$(B\leftrightarrow A)\rightarrow \text{True}$|对(12)使用**公理2.11**|
|$14$|$(B\leftrightarrow A)\leftrightarrow \text{True}$|对(9)(13)使用**公理2.8**|
|$15$|$\{(A\leftrightarrow B)\leftrightarrow \text{True}\}\vdash (B\leftrightarrow A)\leftrightarrow \text{True}$|总结(1)到(14)|

&emsp;&emsp;好了，现在两个等价公式交换后还等价了。

&emsp;&emsp;(3)由**定义2.9**和**定义2.7**：我们只需假设$(A\leftrightarrow B)\leftrightarrow \text{True}$为真，以及$(B\leftrightarrow C)\leftrightarrow \text{True}$为真，推理出$(A\leftrightarrow C)\leftrightarrow \text{True}$为真即可

|编号|公式|原因|
|-|-|-|
|$1$|$(A\leftrightarrow B)\leftrightarrow \text{True}$|假设|
|$2$|$(B\leftrightarrow C)\leftrightarrow \text{True}$|假设|
|$3$|$\text{True}$|假设|
|$4$|$\text{True}\rightarrow(A\leftrightarrow B) $|对(1)使用**公理2.9**|
|$5$|$\text{True}\rightarrow(B\leftrightarrow C) $|对(2)使用**公理2.9**|
|$6$|$A\leftrightarrow B$|对(3)(4)使用**公理2.10**|
|$7$|$B\leftrightarrow C$|对(3)(5)使用**公理2.10**|
|$8$|$A$|假设|
|$9$|$A\rightarrow B$|对(6)使用**公理2.9**|
|$10$|$B$|对(8)(9)使用**公理2.10**|
|$11$|$B\rightarrow C$|对(7)使用**公理2.9**|
|$12$|$C$|对(10)(11)使用**公理2.10**|
|$13$|$\{A\}\vdash C$|总结(8)到(12)|
|$14$|$A\rightarrow C$|对(13)使用**公理2.11**|
|$15$|$C$|假设|
|$16$|$C\rightarrow B$|对(7)使用**公理2.9**|
|$17$|$B$|对(15)(16)使用**公理2.10**|
|$18$|$B\rightarrow A$|对(6)使用**公理2.9**|
|$19$|$A$|对(17)(18)使用**公理2.10**|
|$20$|$\{C\}\vdash A$|总结(15)到(19)|
|$21$|$C\rightarrow A$|对(20)使用**公理2.11**|
|$22$|$A\leftrightarrow C$|对(14)(21)使用**公理2.8**|
|$23$|$\{\text{True}\}\vdash (A\leftrightarrow C)$|总结(3)到(22)|
|$24$|$\text{True}\rightarrow(A\leftrightarrow C)$|对(23)使用**公理2.11**|
|$25$|$A\leftrightarrow C$|假设|
|$26$|$\text{True}$|对{}使用**公理2.4**|
|$27$|$\{A\leftrightarrow C\}\vdash\text{True}$|总结(25)到(26)|
|$28$|$(A\leftrightarrow C)\rightarrow\text{True}$|对(27)使用**公理2.11**|
|$29$|$(A\leftrightarrow C)\leftrightarrow\text{True}$|对(24)(28)使用**公理2.8**|
|$30$|$\{(A\leftrightarrow B)\leftrightarrow \text{True}, (B\leftrightarrow C)\leftrightarrow \text{True}\}\vdash(A\leftrightarrow C)\leftrightarrow\text{True}$|总结(1)到(29)|

<div style="text-align: right;">

$\square$
</div>


&emsp;&emsp;我们再来证明一些永真式，这样我们可以在之后的证明中直接引入他们，从而省去一些工作。

**定理2.2**(常用永真式)
(1)$$
\text{True}\\
\neg\text{True} \leftrightarrow \text{False}\\
\neg\text{False} \leftrightarrow \text{True}
$$(2)$$
P\rightarrow P\\
P\leftrightarrow P\\
\neg\neg P\leftrightarrow P
$$

&emsp;**证明：**
&emsp;&emsp;(1)
&emsp;&emsp;由**公理2.4** $\text{True}$立马得证。
&emsp;&emsp;下证 $\neg\text{True} \leftrightarrow \text{False}$
|编号|公式|原因|
|-|-|-|
|$1$|$\text{False}$|假设|
|$2$|$\neg\text{True}$|对(1)使用**公理2.7**|
|$3$|$\{\text{False}\}\vdash\neg\text{True}$|总结(1)到(2)|
|$4$|$\text{False}\rightarrow\neg\text{True}$|对(3)使用**公理2.11**|
|$5$|$\neg\text{True}$|假设|
|$6$|$\text{True}\rightarrow\text{False}$|对(5)使用**公理2.2**|
|$7$|$\text{True}$|引入已证永真式(也可以使用公理)|
|$8$|$\text{False}$|对(6)(7)使用**公理2.10**|
|$9$|$\{\neg\text{True}\}\vdash\text{False}$|总结(5)到(8)|
|$10$|$\neg\text{True}\rightarrow\text{False}$|对(9)使用**公理2.11**|
|$11$|$\neg\text{True}\leftrightarrow\text{False}$|对(4)和(10)使用**公理2.8**|

&emsp;&emsp;$\neg\text{False} \leftrightarrow \text{True}$ 的证明留作练习。

|编号|公式|原因|
|-|-|-|
|$1$|$\neg\text{False}$|假设|
|$2$|$\text{True}$|引入已证永真式|
|$3$|$\{\neg\text{False}\}\vdash\text{True}$|总结(1)到(2)|
|$4$|$\neg\text{False}\rightarrow\text{True}$|对(3)使用**公理2.11**|
|$5$|$\text{True}$|假设|
|$6$|$\text{False}$|假设|
|$7$|$X$|对(6)使用**公理2.7**|
|$8$|$\{\text{False}\}\vdash X$|总结(6)到(7)|
|$9$|$\text{False}\rightarrow X$|对(8)使用**公理2.11**|
|$10$|$\text{False}$|假设|
|$11$|$\neg X$|对(10)使用**公理2.7**|
|$12$|$\{\text{False}\}\vdash \neg X$|总结(10)到(11)|
|$13$|$\text{False}\rightarrow \neg X$|对(12)使用**公理2.11**|
|$14$|$\neg\text{False}$|对(9)(12)使用**公理2.1**|
|$15$|$\{\text{True}\}\vdash\neg\text{False}$|总结(5)到(14)|
|$16$|$\text{True}\rightarrow\neg\text{False}$|对(15)使用**公理2.11**|
|$17$|$\neg\text{False}\leftrightarrow\text{True}$|对(4)(16)使用**公理2.8**|


&emsp;&emsp;(2)我们证明$\neg\neg P\leftrightarrow P$ 前两个留作练习

&emsp;&emsp;证$P\rightarrow P$ 和 $P\leftrightarrow P$
|编号|公式|原因|
|-|-|-|
|$1$|$P$|假设|
|$2$|$P\vee X$|对(1)使用**公理2.6**|
|$3$|$P\wedge (P\vee X)$|对(1)(2)使用**公理2.4**|
|$4$|$P$|对(3)使用**公理2.5**|
|$5$|$\{P\}\vdash P$|总结(1)到(4)|
|$6$|$P\rightarrow P$|对(5)使用**公理2.11**|

实际上直接总结(1)到(1)也可以得到$\{P\}\vdash P$。
|编号|公式|原因|
|-|-|-|
|$1$|$P\rightarrow P$|引入已证永真式|
|$2$|$P\leftrightarrow P$|对(1)(1)使用**公理2.8**|

证:$\neg\neg P\leftrightarrow P$
|编号|公式|原因|
|-|-|-|
|$1$|$P$|假设|
|$2$|$\neg P$|假设|
|$3$|$P$|(1)已得|
|$4$|$\{\neg P\}\vdash P$|总结(2)到(3)|
|$5$|$\neg P\rightarrow P$|对(4)使用**公理2.11**|
|$6$|$\neg P\rightarrow \neg P$|引入已证永真式|
|$7$|$\neg\neg P$|对(5)(6)使用**公理2.1**|
|$8$|$\{P\}\vdash \neg\neg P$|总结(1)到(7)|
|$9$|$P\rightarrow \neg\neg P$|对(8)使用**公理2.11**|
|$10$|$\neg\neg P$|假设|
|$11$|$P$|对(10)使用**公理2.3**|
|$12$|$\{\neg\neg P\}\vdash P$|总结(10)到(11)|
|$13$|$\neg\neg P\rightarrow P$|对(12)使用**公理2.11**|
|$14$|$\neg\neg P\leftrightarrow P$|对(9)(13)使用**公理2.8**|

<div style="text-align: right;">

$\square$
</div>

**定理2.3**(代入原则)设$a, b, A$是命题公式, 且$a=b$, $a$是$A$的子公式, 那么用$b$在$A$中替换$a$, 得到公式B后, $A=B$。
&emsp;**证明：**(不做要求，置于文末)

&emsp;&emsp;例如: $A:=P\vee a, a=b, B:=P\vee b$那么$A=B$。
&emsp;&emsp;其中$:=$为**定义符**，用于区别于公式等价符$=$。$A:=P\vee a$实际上是在说$A$其实就是$P\vee a$本身，而不是这两个式子等价。

&emsp;&emsp;将代入原则结合**定理2.1**我们发现公式等价符$=$可以用来进行公式间的运算了，下面我们给出了一些常用的等价公式。在证明它们之前，我们先直观的理解一下这些式子的含义。

**定理2.4**(常用等价公式)
(1)零和一$$
\neg \text{True} = \text{False}\\
\neg \text{False} = \text{True}\\
$$&emsp;&emsp;真假互为反义词，一个命题不为真，就是假。这一点也是由我们的公理系统推出的。

(2)双重否定律$$
\neg\neg P=P
$$&emsp;&emsp;这也是符合直觉的，尽管公理只告诉我们从左边能推到右边，但是我们通过之前的永真式的证明说明了右边也可以推到左边。

(3)结合律$$
(P\vee Q)\vee R = P\vee (Q\vee R)\\ 
(P\wedge Q)\wedge R = P\wedge (Q\wedge R)\\ 
(P\leftrightarrow Q)\leftrightarrow R = P\leftrightarrow (Q\leftrightarrow R)\\ 
$$&emsp;&emsp;结合律描述的是多个元素进行运算时的运算顺序可以自由决定。在这里多个命题“且”，需要同时为真，整个命题才为真；多个命题“或”，至少有一个为真，整个命题就为真。从这个角度考虑确实符合结合律。“等价”也是类似的，不过单箭头的“蕴涵”就不满足结合律。

(4)交换律$$
P\vee Q = Q\vee P\\
P\wedge Q = Q\wedge P\\
P\leftrightarrow Q = Q\leftrightarrow P
$$&emsp;&emsp;交换律描述的是两个元素进行运算时的相对关系可以互换。在这里两个命题“且”，需要同时为真，整个命题才为真，无所谓前后；两个命题“或”，至少有一个为真，整个命题就为真，无所谓。从这个角度考虑确实符合交换律。“等价”也是类似的，不过单箭头的“蕴涵”就不满足交换律。

(5)分配律$$
P\wedge(Q\vee R) = (P\wedge Q)\vee(P\wedge R)\\
P\vee(Q\wedge R) = (P\vee Q)\wedge(P\vee R)
$$&emsp;&emsp;分配律描述的是两种运算之间的关系。先观察第一个等价公式：一个命题“且”两个命题的“或”，第一个命题必须为真，后两个命题有一个为真即可，那么就相当于第一个命题和后面的某一个同时为真就好。可以类似的去理解第二条等价公式。
&emsp;&emsp;以前我们接触过乘法对加法的分配律：一个数乘以两个数的和，等于这个数分别乘以两个数再求和，这里也是类似的（只不过加法对乘法不满足分配律）。

(6)幂等律$$
P\vee P = P\\
P\wedge P = P
$$&emsp;&emsp;自己“或”自己还是自己；自己“且”自己也是自己。总而言之，自己成立就是成立，自己不成立就是不成立。

(7)吸收律$$
P\vee(P\wedge Q) = P\\
P\wedge(P\vee Q) = P
$$&emsp;&emsp;在这里，命题真假竟然与$Q$无关！如何理解？对于第一条，$P$和$P\wedge Q$至少成立一个，$P$成立时，因为前者成立，所以整个命题成立，与$Q$无关;$P$不成立时，后者肯定不成立了，前者也不成立，两者都不成立，于是命题为假，也与$Q$无关。可以类似的分析和理解第二条。

(8)反演律(也叫De Morgan定律，这是一个非常有用的定理)$$
\neg(P\vee Q) = \neg P \wedge \neg Q\\
\neg(P\wedge Q) = \neg P \vee\neg Q
$$&emsp;&emsp;反演律深刻的反应了“且”、“或”、“非”之间的关系。我们通过一个简单的例子来说明第一条：$a$是奇数或$b$是奇数为假，等同于，$a$不是奇数且$b$不是奇数。可以类似的理解第二条。总而言之，对命题取反时，你可以把对整个命题的“非”下放至每个更小的命题，同时它们的“且”，“或”关系会发生改变。例如：对命题“今天即下雨又刮风”取反，可以表述为“今天不是即下雨又刮风”也可以表述为“今天不下雨或今天不刮风”（对应第二条等价公式）。

(9)单位律$$
P\vee \text{False} = P\\
P\wedge \text{True} = P\\
$$&emsp;&emsp;要求自己和假命题之一至少成立一个，假命题不可能为真，所以还是看自己。要求自己和真命题同时成立，因为真命题已经成立，所以整个命题就看自己了。

(10)零律$$
P\vee \text{True} = \text{True}\\
P\wedge \text{False} = \text{False}\\
$$&emsp;&emsp;自己和真命题至少成立一个，那么恭喜，真命题已经成立了，你成立与否整个命题都是成立的。你希望自己和假命题同时成立，恭喜，在这个公理系统下不可能。

(11)补律$$
P\vee \neg P = \text{True}\\
P\wedge \neg P = \text{False}\\
$$&emsp;&emsp;每个命题不是真就是假，于是自己和自己取反刚好只会成立一个，“至少一个”是肯定的，“两个都要”不可能。

(12)蕴含的析合性质$$
P\rightarrow Q = \neg P \vee Q
$$&emsp;&emsp;蕴涵其实可以使用“非”和“或”表示，可以回头参考**定义2.4**思考一下为什么？

(13)逆否命题(这也是一个很重要的性质)$$
P\rightarrow Q = \neg Q \rightarrow \neg P
$$&emsp;&emsp;如果$P$成立则$Q$成立，那么$Q$不成立则$P$一定不成立。例如：如果“下雨一定有乌云”，那么“没乌云一定不下雨”，注意，光从“有乌云”无法知道是否“下雨”；或者“吃饭一定饱”可以得到“饿了一定没吃饭”，但是“不吃饭”不一定会“饿”，可能吃了零食。

(14)分类讨论实质(\\todo举例奇数偶数)$$
(P \rightarrow R) \wedge (Q \rightarrow R) = (P\vee Q)\rightarrow R
$$&emsp;&emsp;$P$和$Q$都能推出$R$，那么想要得到$R$只需要$P$,$Q$成立一个即可。怎么理解“分类讨论”一说呢？我们这样举例，$P$：有理数$a$是奇数；$Q$：有理数$a$是偶数；$R$：$a$是整数；那么关系就显而易见了（$a$可以是分数，这时推不出$R$）。这条性质指出未来我们基于分类讨论的证明是正确的。

(15)等价的析合性质$$
P \leftrightarrow Q = (P\wedge Q)\vee (\neg P \wedge \neg Q)\\
P \leftrightarrow Q = (\neg P\vee Q)\wedge ( P \vee \neg Q)
$$&emsp;&emsp;同蕴涵一样，等价也可以被“且”“或”“非”表示。式子的含义比较明显，可以自己从真假逻辑上分下一下为什么。

(16)等价的否$$
P \leftrightarrow Q = \neg P \leftrightarrow \neg Q 
$$&emsp;&emsp;两个命题等价，那么取反后依旧相互等价。  

接下来将是一段篇幅巨长的证明。
//todu

#### 2.1.6 命题的证明

//todo 一帮人有人撒谎了

### 2.2 谓词逻辑

### 本节回顾





<!-- 
### 2.2 集合
#### 2.2.1 集合的基本概念及其表示方法
#### 2.2.2 集合的运算


### 2.3 函数
#### 2.3.1 函数的基本概念
#### 2.3.2 函数的复合
#### 2.3.3 函数举例（奇奇怪怪的函数, 包括不限于基本初等函数, max, min, 各种取整）

### 2.4 序列
#### 2.4.1 序列的定义
#### 2.4.2 数列

### 2.6 递归定义
#### 2.6.1 递归定义
#### 2.6.2 举例（定义 a_0 和 递推式子）

### 2.5 归纳原理
#### 2.5.1 归纳原理
#### 2.5.2 举例
 -->




## 思考习题

**习题2.1**：证明**定理2.2**中留作练习的几个永真式。

**习题2.2**：证明**定理2.4**中留作练习的几个等价公式。

**习题2.3**：又是说谎问题



<div style="page-break-after: always;"></div>

## 参考资料

### 1. 习题参考答案

**习题1.1**：证明命题：53是奇数。

&emsp;**证明**:
$$
\because 53 = 26 \times 2 + 1\\
\therefore 53 \div 2 = 26 \cdots \space \cdots 1 \neq0
$$&emsp;&emsp;根据**定义1.2**, 53是奇数。

<div style="text-align: right;">

$\square$
</div>

<div style="page-break-after: always;"></div>

### 2. 阅读材料 —— 矩阵与矩阵乘法




### 3. 本节内容相关资料

[1] 有关几何的部分：《几何原本》
[2] 有关矩阵的部分：《线性代数》
[3] 有关命题, 证明的论证逻辑部分：《数理逻辑》
[4] 有关数字本身的定义：《集合论》
[5] 有关运算性质的部分, 如交换律、结合律、分配律等：《代数系统》
[6] 有关整数性质的部分：《数论》




<br></br>
<br></br>
<br></br>
<br></br>
<br></br>
<br></br>
<br></br>
<br></br>
<br></br>
<br></br>
<div style="text-align: right">
 
*版权声明* © Copyright 2024 Boyer.
</div>

<!--  本节需要荧光笔标注的地方有如下几处
- 1 习题1.3答案的交换律部分
- 2 矩阵乘法规则的行列对应部分


-->