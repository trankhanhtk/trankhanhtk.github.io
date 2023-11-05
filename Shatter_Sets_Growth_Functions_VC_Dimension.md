---
layout: post
title: "Shatter Sets, Growth Functions & VC Dimension"
permalink: /shatter-sets-growth-functions-VC-dimension
---
This note summarizes three basic concepts in Machine Learning: the shatter set, the growth function and the VC dimension.

## Shatter Sets
Suppose $S$ is a set $s$ and $\mathcal{F}$ is a class of sets. The class $\mathcal{F}$ shatters the set $S$ if for each subset $s$ of $S$, there exists some element $f \in \mathcal{F}$ such that:

$$
s=f\cap S.
$$

In symbols:

$$
\mathcal{F}\text{ shatters }C\leftrightarrow (\forall s\in S)(\exists f\in\mathcal{F})(s=f\cap S)
$$


Define the intersection of the class $\mathcal{F}$ and the set $S$ to be:

$$
\mathcal{F}\cap S := \{ s \cap \mathcal{F}: s \in S \}\tag1\label{eq1}
$$

We can say that $\mathcal{F}$ shatters $S$ if their intersection equals the power set of $S$:

$$
\mathcal{P}(S) = \{ s \cap \mathcal{F}: s \in S \}.
$$


## Shattering in Context of the Function
Let $\mathcal{H}$ be a hypothesis class of binary classifiers from the domain set $\mathcal{X}$ to $\{0, 1\}$. Let $C=\lbrace c_{1}, c_{2},..., c_{m}\rbrace$ be a subset
$\mathcal{X}$ and denote by $\mathcal{H}_{C}$ the restriction of $\mathcal{H}$ to $C$, that is:

$$\mathcal{H}_{C} = \lbrace \langle h( c_{1} ), h( c_{2} ),..., h( c_{m} ) \rangle : h \in \mathcal{H} \rbrace .$$

We say that $\mathcal{H}$ shatters $C$ if $\mathcal{H}_{C}$ is the set of all functions from $C$ to $\lbrace 0, 1\rbrace$. Clearly, if $\mathcal{H}$ shatters $C$ then $\left|\mathcal{H}_{C}\right|=2^{\left|C\right|}$. When the intersection $|\mathcal{H}\cup C|$ is defined like in equation $\eqref{eq1}$, that is:

$$
\mathcal{H}\cup C := \lbrace h\cup C: h\in\mathcal{H}\rbrace
$$

We can also see, from the definition of $\mathcal{H}_{C}$, that: $\mathcal{H}_{C} = \mathcal{H}\cup C$

## The VC dimension
The VC dimension of the hypothesis class $\mathcal{H}$ of binary classiers from the domain set $\mathcal{X}$ to $\{0, 1\}$ is defined to be the maximal size of the set $C\subset\mathcal{X}$ that is shattered by $\mathcal{H}$:

$$
VCdim(\mathcal{H}) := \max_{C\subset\mathcal{X}:\mathcal{H}_{C}=\mathcal{P}(C)} |C|
$$

## Growth Function

The growth function of $\mathcal{H}$ is a function of the size of a set $C\subset\mathcal{X}$ that measures "effective" size of the hypothesis class $\mathcal{H}$ restricted on a subset of $\mathcal{X}$ of size $m$, that is:


$$
\tau_{\mathcal{H}}(m):=\underset{C\subset\mathcal{X}:|C|=m}{max}|\mathcal{H}_{{C}}|.
$$



Traditionally we denote the restriction of $\mathcal{H}$ to $C$ by $\mathcal{H}|_{C}$.
