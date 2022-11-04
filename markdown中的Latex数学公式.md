<center><h1>Markdown中的Latex数学公式</h1></center>

<center>作者：朱超盛</center>

[TOC]


<div style="page-break-after:always;"></div>

## 1 Markdown中使用Latex基础语法

Latex公式有两种，一种是用在正文中的，一种是单独显示的。

- 行内公式：用`$formual$`表示，例如`$\sum\limits_{i=0}^{n}i^2$`表示$\sum\limits_{i=0}^{n}i^2$
- 独立公式：用`$$formual$$`表示，例如`$$\sum_{i=0}^{n}i^2$$`表示

$$
\sum_{i=0}^{n}i^2
$$

以下几个字符# \$ % & ~ _ ^ \ {}有特殊意义，当表示这些字符是，需要转义，即在每个字符前加上\，对于\，可用`$\backslash$`命令得到$\backslash$

## 2 常用数学表达命令

### 2.1 上下标表示

- 上标：用`^`后的内容表示上标，例如`$x^{(i)}、y^{(i)}$`表示$x^{(i)}$、$y^{(i)}$
- 下标：用`_`后的内容表示下表，例如`$x_{(i)}、y_{(i)}$`表示$x_{(i)}$、$y_{(i)}$
- 上下标混用：例如`$x_1^2$`、`$x^{y^{z}}$`、`$x^{y_z}$`表示$x_1^2$、$x^{y^{z}}$、$x^{y_{z}}$

当角标位置看起来不明显时，可以强制改变角标层次或者在角标前面加上改变其大小的命令（如`\tiny`、`\samll`、`\normalsize`、`\large`、`\Large`、`\LARGE`），例如：`$y_N$`、`$y_{_N}$`、`$y_{\samll{N}}$`表示$y_N$、$y_{_N}$、$y_{\small{N}}$，并且支持中文作为角标，例如：`${\partial f}_{\tiny 极大值}$`、`${\partial f}_{\large 极大值}$`表示${\partial f}_{\tiny 极大值}$、${\partial f}_{\large 极大值}$

### 2.2 分数形式

分式命令：

- `$\dfrac{}{}$`，表示该分式是以display style设置的，例如`$\dfrac{f}{x}$`表示$\dfrac{y}{x}$
- `$\tfrac{}{}$`、表示分式是以teststyle设置的，例如`$\tfrac{y}{x}$`表示$\tfrac{y}{x}$
- `$\frac{}{}$`、表示分式根据环境设置样式，例如`$\frac{y}{x}$`表示$\frac{y}{x}$
- `${} \over {}$`、例如`${y} \over {x}$`表示${y} \over {x}$

连分式`$x_0+\frac{1}{x_1+\frac{1}{x_2+\frac{1}{x_3+\frac{1}{x_4}}}}$`表示：
$$
x_0+\frac{1}{x_1+\frac{1}{x_2+\frac{1}{x_3+\frac{1}{x_4}}}}
$$
可以使用`$\displaystyle$`表示分式，例如：

`$$x_0+\frac{1}{x_1+\frac{1}{x_2+\frac{1}{x_3+\frac{1}{x_4}}}}$$`表示：
$$
x_0+\dfrac{1}{x_1+\dfrac{1}{x_2+\dfrac{1}{x_3+\dfrac{1}{x_4}}}}
$$

分数线长度值是预设为分子分母的最大长度，如果想要分数线再长一点，可以在分子或分母两端添加一些间隔，例如`$\frac{1}{2}$`、`$\frac{\;1\;}{\;2\;}$`表示$\frac{1}{2}$、$\frac{\;1\;}{\;2\;}$

### 2.3 根式

- 二次根式命令: `\sqrt{表达式}` 、 例如：` $\sqrt{x}$ `表示 $\sqrt{x}$
- n次根式命令：`\sqrt[n]{表达式}`、例如：`$\sqrt[n]{x}$`表示$\sqrt[n]{x}$

被开方表达式字符高度不一致，即根号上面的横线可能不在同一条直线上，可以在被开方表达式插入一个只有高度没有宽度的数学支柱`$\mathstrut$`、例如：`$\sqrt{a}+\sqrt{b}+\sqrt{c}$`、`$\sqrt{\mathstrut a}+\sqrt{\mathstrut b}+\sqrt{\mathstrut c}$`表示$\sqrt{a}+\sqrt{b}+\sqrt{c}$、$\sqrt{\mathstrut a}+\sqrt{\mathstrut b}+\sqrt{\mathstrut c}$

当开方次数的位置显得略低时，可以将开方改为上标，并拉近与根式的水平距离，即将命令中的 `[n] `改为 `[^n \!]`(其中 ^ 表示是上标，! 表示缩小间隔)、例如：`$ \sqrt{1+\sqrt[p]{1+\sqrt[p]{1+a}}} $`、`$ \sqrt{1+\sqrt[^p \!]{1+\sqrt[^p \!]{1+a}}} $`

$ \sqrt{1+\sqrt[p]{1+\sqrt[p]{1+a}}} $ , $ \sqrt{1+\sqrt[^p \!]{1+\sqrt[^p \!]{1+a}}} $

### 2.4 向量

使用`\vec{矢量}`来产生一个矢量，也可以使用`\overrightarrow`等命令自定义字母上方的符号，例如`$$\vec{x} \quad \overleftarrow{xy} \quad \overleftrightarrow{xy} \quad \overrightarrow{xy}$$`（`\quad`表示退一格）
$$
\vec{x} \quad \overleftarrow{xy} \quad \overleftrightarrow{xy} \quad \overrightarrow{xy}
$$

### 2.5定界符 - 自适应放大命令

自适应放大命令：`\left`和`\right`、此命令放在左右定界符前，随着公式内容自动调整符号大小，例如：`$\left(\frac{1}{xyz}\right)$`表示$\left(\frac{1}{xyz}\right)$

另一种表达方式：`$() \big(\big) \Big(\Big) \Bigg(\Bigg)$`表示：$() \big(\big) \Big(\Big) \Bigg(\Bigg)$

`\left`和`\right`需成对使用，只需一边时，可用`\left.`或`\right.`进行配对，例如：`$\left.\frac{1}{2}x^2\right|_0^1$`表示$\left.\frac{1}{2}x^2\right|_0^1$

### 2.6 空白间距-占位宽度

`\quad`代表当前字体下接近字符`M`的宽度

| 符号                         | 命令               | 效果         |
| ---------------------------- | ------------------ | ------------ |
| 没有空格                     | `$ab$`             | $ab$         |
| 紧贴，缩进$\frac{1}{6}$m宽度 | `$a\!b$`           | $a\!b$       |
| 小空格                       | `$a\,b$`           | $a\,b$       |
| $\frac{1}{3}$个空格          | `$a\ b$`           | $a\ b$       |
| 中等空格                     | `$a\:b$`或`$a\;b$` | $a\;b$       |
| 一个空格                     | `$a \quad b$`      | $a \quad b$  |
| 两个空格                     | `$a \qquad b$`     | $a \qquad b$ |

### 2.7 省略号

省略号用`\dots \cdots \vdots \ddots`表示，`\dots`和`cdots`的纵向位置不同，前者用于有下标的序列，例如：`$$x_1,x_2,\dots,x_n \quad 1,2\cdots,n \quad \vdots \quad \ddots$$`表示
$$
x_1,x_2,\dots,x_n \quad 1,2\cdots,n \quad \vdots \quad \ddots
$$

### 2.8 多行公式

**长公式**

无需对齐可使用`multline`，需对齐使用`split`，用`\\`和`&`来分行和设置对齐的位置，例如：

```latex
$$\begin{multline}
x=a+b+c+{} \\
d+e+f+g
\end{multline}$$
```

$$
\begin{multline}
x=a+b+c+{} \\
d+e+f+g
\end{multline}
$$

```latex
$$\begin{split}
x=&a+b+c+ \\
&d+e+f+g
\end{split}$$
```

$$
\begin{split}
x=&a+b+c+ \\
&d+e+f+g
\end{split}
$$

**公式组**

不需要对齐的公式组用`gather`，需对齐使用`align`，例如：

```latex
$$\begin{gather}
a=b+c+d \\
x=y+z
\end{gather}$$
```

$$
\begin{gather}
a=b+c+d \\
x=y+z
\end{gather}
$$

```latex
$$\begin{align}
a&=b+c+d \\
x&=y+z
\end{align}$$
```

$$
\begin{align}
a&=b+c+d \\
x&=y+z
\end{align}
$$

**分支公式**

分段函数通常用`cases`，例如：

```latex
$$y=\begin{cases}
-x,\quad &x \leq 0 \\
x, &x>0
\end{cases}$$
```

$$
y=\begin{cases}
-x, \quad &x \leq 0 \\
x, &x>0
\end{cases}
$$

**公式编号**

可以通过命令`\tag{n}`手动为公式编号，例如：

```latex
$$
S(r_k) = \sum_{r_k \ne r_i} \text{exp}(\frac{-D_s(r_k,r_k)}{\sigma_s^2})
\tag{1}$$
```

$$
S(r_k) = \sum_{r_k \ne r_i} \text{exp}(\frac{-D_s(r_k,r_k)}{\sigma_s^2})
\tag{1}
$$

### 2.9 上下水平线

- `\overline{表达式}`：在表达式上方画出水平线，例如：`$\overline{x+y}$`表示：$\overline{x+y}$

- `\underline{表达式}`：在表达式下方画出水平线，例如：`$\underline{x+y}$`表示：$\underline{x+y}$

### 2.10 上下大括号

- `\overbrace{表达式}`：在表达式上方画出一个水平的大括号，例如：`$\overbrace{1+2+3+\cdots+100}^{100}$`表示：$\overbrace{1+2+3+\cdots+100}^{100}$

- `\underbrace{表达式}`：在表达式下方画出一个水平大括号，例如：

`$\underbrace{1+2+3+\cdots+100}_{100}$`表示：$\underbrace{1+2+3+\cdots+100}_{100}$

### 2.11 矩阵

生成矩阵的命令中每一行以 `\\` 结束，矩阵的元素之间用 & 来分隔开，例如

```latex
$$\begin{matrix}
x_{_{11}} & x_{_{12}} & \dots & x_{_{1n}} \\
x_{_{21}} & x_{_{22}} & \dots & x_{_{2n}} \\
\vdots & \vdots & \ddots  & \vdots  \\
x_{_{m1}} & x_{_{m2}} & \dots & x_{_{mn}} \\
\end{matrix}$$
```

$$
\begin{matrix}
x_{_{11}} & x_{_{12}} & \dots & x_{_{1n}} \\
x_{_{21}} & x_{_{22}} & \dots & x_{_{2n}} \\
\vdots & \vdots & \ddots  & \vdots  \\
x_{_{m1}} & x_{_{m2}} & \dots & x_{_{mn}} \\
\end{matrix}
$$

带各类不同边界的矩阵:
```latex
$$
\begin{pmatrix} a & b \\ c & d \\ \end{pmatrix} \quad
\begin{bmatrix} a & b \\ c & d \\ \end{bmatrix} \quad
\left[ \begin{matrix} a & b \\ c & d \\ \end{matrix} \right] \quad
\begin{Bmatrix} a & b \\ c & d \\ \end{Bmatrix} \quad
\left\{ \begin{matrix} a & b \\ c & d \\ \end{matrix} \right\} \quad
\begin{vmatrix} a & b \\ c & d \\ \end{vmatrix} \quad
\begin{Vmatrix} a & b \\ c & d \\ \end{Vmatrix} \quad
\left[ \begin{array} {c|c} a & b \\ c & d \\ \end{array} \right]
$$
```

$$
\begin{pmatrix} a & b \\ c & d \\ \end{pmatrix} \quad
\begin{bmatrix} a & b \\ c & d \\ \end{bmatrix} \quad
\left[ \begin{matrix} a & b \\ c & d \\ \end{matrix} \right] \quad
\begin{Bmatrix} a & b \\ c & d \\ \end{Bmatrix}  \\
\left\{ \begin{matrix} a & b \\ c & d \\ \end{matrix} \right\} \quad
\begin{vmatrix} a & b \\ c & d \\ \end{vmatrix} \quad
\begin{Vmatrix} a & b \\ c & d \\ \end{Vmatrix} \quad
\left[ \begin{array} {c|c} a & b \\ c & d \\ \end{array} \right]
$$

### 2.12 Norm-范数符号

范数命令：`\parallel`

例如：`$\parallel x \parallel _2 $`表示$\parallel x \parallel _2$

### 2.13 堆积符号

- `\stackrel{上位符号}{基位符号}`：基位符号大，上位符号小，例如:

`$ \vec{x}\stackrel{\mathrm{def}}{=}{x_1,\dots,x_n} $`表示$ \vec{x}\stackrel{\mathrm{def}}{=}{x_1,\dots,x_n} $

- `{上位公式 \choose 下位公式}`：上下符号一样大，上下符号被包括在圆弧内，例如：`$ {n+1 \choose k}={n \choose k}+{n \choose k-1} $`表示$ {n+1 \choose k}={n \choose k}+{n \choose k-1} $

- `{上位公式 \atop 下位公式}` : 上下符号一样大，例如：`$ \sum\limits_{k_0,k_1,\ldots>0 \atop k_0+k_1+\cdots=n}A_k $`表示$ \sum\limits_{k_0,k_1,\ldots>0 \atop k_0+k_1+\cdots=n}A_k $

### 2.14 给公式加一个方框

`\boxed`命令给公式加一个方框，例如：`$$\boxed{E=mc^2}$$`表示
$$
\boxed{E=mc^2}
$$

### 2.15 字体转换

若要对公式的某一部分字符进行字体转换，可以用` {\字体 {需转换的部分字符}} `命令，其中 `\字体` 部分可以参照下表选择合适的字体，一般情况下，公式默认为意大利体。

| 命令    | 说明       | 效果          |
| ------- | ---------- | ------------- |
| `\rm`   | 罗马体     | ${\rm {D}}$   |
| `\cal`  | 花体       | ${\cal {D}}$  |
| `\it`   | 意大利体   | ${\it {D}}$   |
| `\Bbb`  | 黑板粗体   | ${\Bbb {D}}$  |
| `bf`    | 粗体       | ${\bf {D}}$   |
| `\mit`  | 数学斜体   | ${\mit {D}}$  |
| `\sf`   | 等线体     | ${\sf {D}}$   |
| `\scr`  | 手写体     | ${\scr {D}}$  |
| `\tt`   | 打字机体   | ${\tt {D}}$   |
| `\frak` | 旧德式字体 | ${\frak {D}}$ |

## 3 LaTeX常用数学符号整理

### 表3.1 数学模式重音符号

| 符号          | 命令            | 符号          | 命令            | 符号              | 命令                |
| ------------- | --------------- | ------------- | --------------- | ----------------- | ------------------- |
| $ \hat{a} $   | `$ \hat{a} $`   | $ \check{a} $ | `$ \check{a} $` | $ \tilde{a} $     | `$ \tilde{a} $`     |
| $ \grave{a} $ | `$ \grave{a} $` | $ \dot{a} $   | `$ \dot{a} $`   | $ \ddot{a} $      | `$ \ddot{a} $`      |
| $ \bar{a} $   | `$ \bar{a} $`   | $ \vec{a} $   | `$ \vec{a} $`   | $ \widehat{A} $   | `$ \widehat{A} $`   |
| $ \acute{a} $ | `$ \acute{a} $` | $ \breve{a} $ | `$ \breve{a} $` | $ \widetilde{A} $ | `$ \widetilde{A} $` |

### 表3.2 希腊字母

| 符号            | 命令              | 符号          | 命令            | 符号          | 命令            | 符号         | 命令           |
| --------------- | ----------------- | ------------- | --------------- | ------------- | --------------- | ------------ | -------------- |
| $ \alpha $      | `$ \alpha $`      | $ \theta $    | `$ \theta $`    | $ o $         | `$ o $`         |              |                |
| $ \beta $       | `$ \beta $`       | $ \vartheta $ | `$ \vartheta $` | $ \pi $       | `$ \pi $`       |              |                |
| $ \gamma $      | `$ \gamma $`      | $ \iota $     | `$ \iota $`     | $ \varpi $    | `$ \varpi $`    | $ \upsilon $ | `$ \upsilon $` |
| $ \delta $      | `$ \delta $`      | $ \kappa $    | `$ \kappa $`    | $ \rho $      | `$ \rho $`      | $ \phi $     | `$ \phi $`     |
| $ \epsilon $    | `$ \epsilon $`    | $ \lambda $   | `$ \lambda $`   | $ \varrho $   | `$ \varrho $`   | $ \varphi $  | `$ \varphi $`  |
| $ \varepsilon $ | `$ \varepsilon $` | $ \mu $       | `$ \mu $`       | $ \sigma $    | `$ \sigma $`    | $ \chi $     | `$ \chi $`     |
| $ \zeta $       | `$ \zeta $`       | $ \nu $       | `$ \nu $`       | $ \varsigma $ | `$ \varsigma $` | $ \psi $     | `$ \psi $`     |
| $ \eta $        | `$ \eta $`        | $ \xi $       | `$ \xi $`       | $ \tau $      | `$ \tau $`      | $ \omega$    | `$ \omega$`    |

1.如果使用大写希腊字母，把命令的首字母变成大写即可，例如：`$\Gamma$`表示：$\Gamma$

2.如果使用斜体大写希腊字母，再再大写希腊字母的LaTeX命令前加上var,例如：`$\varGamma$`表示$\varGamma$

### 表3.3 二元关系符

| 符号            | 命令                    | 符号            | 命令                    | 符号        | 命令                    |
| --------------- | ----------------------- | --------------- | ----------------------- | ----------- | ----------------------- |
| $ < $           | `$ < $`                 | $ > $           | `$ > $`                 | $ = $       | `$ = $`                 |
| $ \leq $        | `$ \leq $ `或 `$ \le $` | $ \geq $        | `$ \geq $`或`$ \ge $`   | $ \equiv $  | `$ \equiv $`            |
| $ \ll $         | `$ \ll $`               | $ \gg $         | `$ \gg $`               | $ \doteq $  | `$ \doteq $`            |
| $ \prec $       | `$ \prec $`             | $ \succ $       | `$ \succ $`             | $ \sim $    | `$ \sim $`              |
| $ \preceq $     | `$ \preceq $`           | $ \succeq $     | `$ \succeq $`           | $ \simeq $  | `$ \simeq $`            |
| $ \subset $     | `$ \subset $`           | $ \supset $     | `$ \supset $`           | $ \approx $ | `$ \approx $`           |
| $ \subseteq $   | `$ \subseteq $`         | $ \supseteq $   | `$ \supseteq $`         | $ \cong $   | `$ \cong $`             |
| $ \sqsubset $   | `$ \sqsubset $`         | $ \sqsupset $   | `$ \sqsupset $`         | $ \Join $   | `$ \Join $`             |
| $ \sqsubseteq $ | `$ \sqsubseteq $`       | $ \sqsupseteq $ | `$ \sqsupseteq $`       | $ \bowtie $ | `$ \bowtie $`           |
| $ \in $         | `$ \in $`               | $ \ni $         | `$ \ni $`或 `$ \owns $` | $ \propto $ | `$ \propto $`           |
| $ \vdash $      | `$ \vdash $`            | $ \dashv $      | `$ \dashv $`            | $ \models $ | `$ \models $`           |
| $ \mid $        | `$ \mid $`              | $ \parallel $   | `$ \parallel $`         | $ \perp $   | `$ \perp $`             |
| $ \smile $      | `$ \smile $`            | $ \frown $      | `$ \frown $`            | $ \asymp $  | `$ \asymp $`            |
| $ : $           | `$ : $`                 | $ \notin $      | `$ \notin $`            | $ \neq $    | `$ \neq $ `或 `$ \ne $` |

可以在上述符号的相应命令前加上`\not`，得到其否定形式，例如：`$\not\subset$`表示$\not\subset$

### 表3.4 二元运算符

| 符号               | 命令                 | 符号                 | 命令                     | 符号               | 命令                 |
| ------------------ | -------------------- | -------------------- | ------------------------ | ------------------ | -------------------- |
| $ \unlhd $         | `$ \unlhd $`         | $ - $                | `$ - $`                  |                    |                      |
| $ + $              | `$ + $`              | $ \mp $              | `$ \mp $`                | $ \triangleleft $  | `$ \triangleleft $`  |
| $ \pm $            | `$ \pm $`            | $ \div $             | `$ \div $`               | $ \triangleright $ | `$ \triangleright $` |
| $ \cdot $          | `$ \cdot $`          | $ \setminus $        | `$ \setminus $`          | $ \star $          | `$ \star $`          |
| $ \times $         | `$ \times $`         | $ \cap $             | `$ \cap $`               | $ \ast $           | `$ \ast $`           |
| $ \cup $           | `$ \cup $`           | $ \sqcap $           | `$ \sqcap $`             | $ \circ $          | `$ \circ $`          |
| $ \sqcup $         | `$ \sqcup $`         | $ \land $            | `$ \land $`或`$\wedege$` | $ \bullet $        | `$ \bullet $`        |
| $ \vee $           | `$ \vee $`           | $ \ominus $          | `$ \ominus $`            | $ \diamond $       | `$ \diamond $`       |
| $ \oplus $         | `$ \oplus $`         | $ \oslash $          | `$ \oslash $`            | $ \uplus $         | `$ \uplus $`         |
| $ \odot $          | `$ \odot $`          | $ \bigcirc $         | `$ \bigcirc $`           | $ \amalg $         | `$ \amalg $`         |
| $ \otimes $        | `$ \otimes $`        | $ \bigtriangledown $ | `$ \bigtriangledown $`   | $ \dagger $        | `$ \dagger $`        |
| $ \bigtriangleup $ | `$ \bigtriangleup $` | $ \rhd $             | `$ \rhd $`               | $ \ddagger $       | `$ \ddagger $`       |
| $ \lhd $           | `$ \lhd $`           | $ \unrhd $           | `$ \unrhd $`             | $ \wr $            | `$ \wr $`            |

### 表3.5大尺寸运算符

![image-20200311150631381](C:\Users\27815\AppData\Roaming\Typora\typora-user-images\image-20200311150631381.png)

### 表3.6 箭头

![image-20200311150739303](C:\Users\27815\AppData\Roaming\Typora\typora-user-images\image-20200311150739303.png)

### 表3.7定界符

![image-20200311150801797](C:\Users\27815\AppData\Roaming\Typora\typora-user-images\image-20200311150801797.png)

### 表3.8大尺寸定界符

![image-20200311150822355](C:\Users\27815\AppData\Roaming\Typora\typora-user-images\image-20200311150822355.png)

### 表3.9其它符号

![image-20200311150857080](C:\Users\27815\AppData\Roaming\Typora\typora-user-images\image-20200311150857080.png)

### 表3.10AMS 定界符

![image-20200311150915266](C:\Users\27815\AppData\Roaming\Typora\typora-user-images\image-20200311150915266.png)

### 表3.11AMS 希腊和希伯来字母

![image-20200311150935111](C:\Users\27815\AppData\Roaming\Typora\typora-user-images\image-20200311150935111.png)

### 表3.12AMS 二元关系符

![image-20200311151108091](C:\Users\27815\AppData\Roaming\Typora\typora-user-images\image-20200311151108091.png)

![image-20200311151136106](C:\Users\27815\AppData\Roaming\Typora\typora-user-images\image-20200311151136106.png)

### 表3.13AMS 箭头

![image-20200311151208381](C:\Users\27815\AppData\Roaming\Typora\typora-user-images\image-20200311151208381.png)

### 表3.14 AMS 二元否定关系符和箭头

![image-20200311151231562](C:\Users\27815\AppData\Roaming\Typora\typora-user-images\image-20200311151231562.png)

![image-20200311151251297](C:\Users\27815\AppData\Roaming\Typora\typora-user-images\image-20200311151251297.png)

### 表3.15AMS 二元运算符

![image-20200311151312663](C:\Users\27815\AppData\Roaming\Typora\typora-user-images\image-20200311151312663.png)

### 表3.16AMS 其它符号

![image-20200311151336109](C:\Users\27815\AppData\Roaming\Typora\typora-user-images\image-20200311151336109.png)

### 表3.17数学字母

![image-20200311151352951](C:\Users\27815\AppData\Roaming\Typora\typora-user-images\image-20200311151352951.png)

## 4 其他

### 4.1分页符

分页符：`<div style="page-break-after:always;"></div>`

### 4.2标题居中

标题居中：`<center><h1>Markdown中的Latex数学公式</h1></center>`

h1表示一级标题，对应不同标题可以改为对应类型。

### 4.3生成目录

目录：`[TOC]+enter`

### 4.4文字居中

居中：`<center>居中内容</center>`

### 4.5内部引用

内部引用代码：

`<a href="#anchor">Link to Anchor</a>`和

`<a id="anchor">Anchor</a>`

示例：

<a href="#anchor">Link to 定理</a>

<a id="anchor"> 定理</a>

### 4.6脚注使用

方法：

文字+`[^1]`

`[^1]:+内容`

示例：

脚注使用[^1]

[^1]:这是一个脚注