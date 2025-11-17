# Session 3: Homework on Modular Arithmetic (Due date Nov 16) 
Show all work clearly and for computational problems include intermediate steps 
## 1.	Fermat's Little Theorem: 

Compute $2^{100} \pmod{7}$


Fermat’s Little Theorem says: $p=7$ is a prime number, and $a=2$ is not divisible by 7, then

$$
2^{7-1} = 2^6 \equiv 1 \pmod{7}
$$

We need degree 6, but have degree 100:

$$
100 = 6 \times 16 + 4.
$$

This means:
$$
2^{100} = 2^{6 \times 16 + 4} = (2^6)^{16} \times 2^4.
$$

$(2^6)^{16} \equiv 1 \pmod{7}$, so

$$
2^{100} \equiv 1 \times 2^4 \equiv 2^4 \pmod{7} \equiv 16 \pmod{7} \equiv 2 \pmod{7}
$$

## 2.	Euler's theorem: 

### (a) Compute Euler’s totient function $\varphi(60)$

Euler’s totient function for a number $n = p_1^{a_1}p_2^{a_2}\cdots p_k^{a_k}$ is:

$$
\varphi(n) = n \left(1 - \frac{1}{p_1}\right)\left(1 - \frac{1}{p_2}\right)\cdots\left(1 - \frac{1}{p_k}\right)
$$

Factor 60 into primes: $60 = 2^2 \times 3 \times 5$, so

$$
\varphi(60) = 60 \left(1 - \frac{1}{2}\right)\left(1 - \frac{1}{3}\right)\left(1 - \frac{1}{5}\right) = 16
$$

### (b) Use Euler’s theorem to compute $7^{24} \pmod{60}$.

Euler’s theorem says:

If $\gcd(a, n) = 1$, then $a^{\varphi(n)} \equiv 1 \pmod n.$


Here $a = 7$, $n = 60$, $a$ is prime and $\varphi(60) = 16$.

So theorem works:

$$
7^{16} \equiv 1 \pmod{60}
$$

We need degree 24, but have 16, since $24 = 16 + 8$:

$$
7^{24} = 7^{16} \times 7^8 \equiv 1 \times 7^8 \equiv 7^8 \pmod{60}
$$

$7^8 \pmod{60} = (7^4)^2 \pmod{60} \equiv 1^2 \pmod{60} \equiv 1 \pmod{60}$, that's because $7^4 \pmod{60} = 1$.

---

### (c) Verify that $\gcd(7, 60) = 1$


List factors:

- 7 is prime
- $60 = 2^2 \times 3 \times 5$, no 7 here

They have no common prime factors so no other common factors than 1. Or by Euclidean algorithm:
- $60 \mod 7 = 4$
- $7 \mod 4 = 3$
- $4 \mod 3 = 1$
---

## 3.	Extended Euclidean Algorithm: 
a)	Find $17^{(-1)} (mod\ 43)$


We need to find the multiplicative inverse of $17 \pmod{43}$ — that is, a number $x$ such that $17x \equiv 1 \pmod{43}$. By the Extended Euclidean Algorithm:

We repeatedly divide and record remainders:

- $43 = 17 \times 2 + 9 \implies 9 = 43 - 17 \times 2$
- $17 = 9 \times 1 + 8 \implies 8 = 17 - 9$
- $9 = 8 \times 1 + 1$

GCD(17, 43) = 1, meaning an inverse exists. Now, backward substitution:

$$
1 = 9 - 8 \times 1 = 9 - (17 - 9) = 2 \times 9 - 17 = 2 \times (43 - 17 \times 2) - 17 = 2 \times 43 - 5 \times 17
$$

So:
- $1 \equiv (2 \times 43 - 5 \times 17) \pmod{43}$
- $1 \equiv -5 \times 17 \pmod{43}$
- $-5 \equiv 43 - 5 = 38 \pmod{43}$

So $17^{-1} \pmod{43} = 38$


## 4.	Verify G = {1, 3, 7, 9} is a group under multiplication mod 10 


It shall have the following properties:
- closure
- associativity
- identity element
- inverse

1. Multiplication mod 10 is closed on $G$, since all multiplications mod 10 produce elements from $G$ as a result.
2. Multiplication mod 10 is associative by its properties.
3. Identity element is 1.
4. Inverses:

Each element must have an inverse in $G$ such that $a \times b \equiv 1 \pmod{10}$.

There are inverses for all elements:

| $a$ | $b$ | $a \times b \equiv 1 \pmod{10}$ |
|-----|-----|-------------------------------|
| 1   | 1   | $1 \times 1 = 1$              |
| 3   | 7   | $3 \times 7 = 21 \equiv 1$    |
| 7   | 3   | $7 \times 3 = 21 \equiv 1$    |
| 9   | 9   | $9 \times 9 = 81 \equiv 1$    |

