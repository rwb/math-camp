## Primer for Quantitative Social Science Research

### Overview

* Instructor: Robert Brame (rbrame@umd.edu)
* Graduate Assistant: Madie Pheasant
* Location: Tydings 1102
* Dates: Wednesday-Friday 8/18-8/20, Monday 8/23, and Wednesday-Friday 8/25-8/27
* Hours: 9-12 (morning session) and 1-4 (afternoon session) each day.
* Emphasis: This course will focus on the review and development of basic quantitative skills that will be useful preparation for analysis courses in the criminology and criminal justice graduate program. This is an ungraded program but all incoming graduate students are encouraged to participate.

### Topics

##### Part 1: Arithmetic

1. integers
2. real, rational, and natural numbers
3. inequalities
4. differences, fractions, quotients
5. summations
6. products
7. order of operations
8. additive & multiplicative inverses
9. absolute values
10. exponents and logarithms
11. radicals
12. factoring
13. roots
14. quadratic formula
15. functions
16. lines
17. curves  
18. secant lines
19. tangent lines
20. limits
21. derivatives

##### Part 2: Basic Probability and Statistics

22. random variables
23. Bayes' theorem
24. binomial distribution
25. significance test
26. normal distribution
27. law of total probability
28. optimization
29. estimates and estimators
30. random sampling
31. sample size and sampling variability
32. bias and efficiency
33. confounding

##### Part 3: Software and Applications

34. introduction to Excel, Stata, and R
35. rectangular data structures
36. basic data manipulations with Stata
37. basic data analysis with Stata

### Course Materials

1. Integers

* whole numbers (no fractional numbers or decimal places)

```r
## print out a set of integers

i <- seq(from=-10,to=10,by=1)
i

## how many integers between -10 and 10

n.i <- 10-(-10)-1
n.i

## example: works for number of days between 2 dates

library(date)
mdy.date(8,1,2021)-mdy.date(6,30,2021)-1

## example: calculate the number of days since you were born

age.days <- mdy.date(8,18,2021)-mdy.date(12,30,1964)
age.days

# convert to age in years using floor function

floor(age.days/365.25)
```

2-3. Real number line and inequalities

* Real numbers are the union of all rational and irrational numbers; real numbers are distinct from complex and imaginary units.
* Rational numbers are obtained from the ratio of two integers (where the denominator is not zero).
* Natural numbers are positive integers (i.e., counting numbers).

```r
plot.new()
plot.window(xlim=c(-12,12),ylim=c(0,1))
text(x=0,y=0.8,adj=c(0.5,0.5),"Real Number Line",cex=1.2)
arrows(x0=-10,y0=0.5,x1=10,y1=0.5,lty=1,lwd=1,angle=28,length=0.1,code=3)
segments(x0=-9:9,x1=-9:9,y0=0.52,y1=0.48,lty=1,lwd=0.8)

# put labels on number line

text(x=0,y=0.43,"0",cex=0.8)
text(x=1,y=0.43,"1",cex=0.8)
text(x=2,y=0.43,"2",cex=0.8)

text(x=-1,y=0.43,"-1",cex=0.8)
text(x=-2,y=0.43,"-2",cex=0.8)
text(x=-3,y=0.43,"-3",cex=0.8)

# indicate the location of 2 points on the real number line

# sqrt(3)

n1 <- 3

arrows(x0=sqrt(n1),y0=0.5,x1=sqrt(n1),y1=0.6,lty=1,lwd=0.8,angle=28,length=0.1,code=1)
text(x=sqrt(n1),y=0.63,expression(sqrt(3)),cex=0.8)

# ln(0.1)

n2 <- 0.1

arrows(x0=log(n2),y0=0.5,x1=log(n2),y1=0.6,lty=1,lwd=0.8,angle=28,length=0.1,code=1)
text(x=log(n2),y=0.63,expression(log[e](0.1)),cex=0.8)
```

<p align="left">
<img src="/gfiles/number-line.png" width="750px">
</p>

* Closed interval

<p align="left">
<img src="/gfiles/eq1.png" width="500px">
</p>

* Open interval

<p align="left">
<img src="/gfiles/eq2.png" width="500px">
</p>

* Half-open (left closed, right open) interval

<p align="left">
<img src="/gfiles/eq3.png" width="500px">
</p>

4. Differences, fractions, and quotients

```r
## difference between 2 slopes

plot.new()
plot.window(xlim=c(-100,100),ylim=c(-100,100))

# x- and y-axes
segments(x0=-100,x1=100,y0=0,y1=0,lty=1,lwd=2)
segments(x0=0,x1=0,y0=-100,y1=100,lty=1,lwd=2)
text(x=4,y=-4,"O")

# points for line 1

x1.l1 <- -47
y1.l1 <- -27

x2.l1 <- 38
y2.l1 <- 70

points(x=x1.l1,y=y1.l1,pch=19,cex=1.2,col="blue")
points(x=x2.l1,y=y2.l1,pch=19,cex=1.2,col="blue")

# slope for line 1 -- y = a + b*x

slope.l1 <- (y2.l1-y1.l1)/(x2.l1-x1.l1)
slope.l1

# intercept for line 1 -- a = y - b*x

int.l1 <- y1.l1-slope.l1*x1.l1
int.l1

# draw a line connecting the two points through plotspace

abline(a=int.l1,b=slope.l1,lty=1,lwd=1,col="blue")

# identify line 1 on the plotspace

text(x=-60,y=-55,expression(Line[1]),cex=0.8)

# points for line 2

x1.l2 <- -75
y1.l2 <- -15

x2.l2 <- 15
y2.l2 <- 23

points(x=x1.l2,y=y1.l2,pch=19,cex=1.2,col="red")
points(x=x2.l2,y=y2.l2,pch=19,cex=1.2,col="red")

# slope for line 2 -- y = a + b*x

slope.l2 <- (y2.l2-y1.l2)/(x2.l2-x1.l2)
slope.l2

# intercept for line 1 -- a = y - b*x

int.l2 <- y1.l2-slope.l2*x1.l2
int.l2

# draw a line connecting the two points through plotspace

abline(a=int.l2,b=slope.l2,lty=1,lwd=1,col="red")

# identify line 2 on the plotspace

text(x=75,y=38,expression(Line[2]),cex=0.8)

# difference between the slopes

delta.slopes <- slope.l1-slope.l2
delta.slopes

# difference between the lines at a single point, x.s
# set x to 55

y1.x55 <- int.l1+slope.l1*55
y1.x55

y2.x55 <- int.l2+slope.l2*55
y2.x55

delta.ys <- y1.x55-y2.x55
delta.ys

# add some supplementary information to the plot

# start with showing the location of x = 55 on horizontal axis

text(x=55,y=-10,"x = 55")

# draw guide line segments

segments(x0=55,x1=55,y0=0,y1=y1.x55,lty=2,lwd=0.8)
segments(x0=0,x1=55,y0=y1.x55,y1=y1.x55,lty=2,lwd=0.5)
segments(x0=0,x1=55,y0=y2.x55,y1=y2.x55,lty=2,lwd=0.5)

# label points

points(x=55,y=y1.x55,pch=19)
points(x=55,y=y2.x55,pch=19)

# y-axis annotations

text(x=-42,y=39.9,adj=c(0,0.5),"(y|x=55)=39.9")
text(x=-42,y=89.4,adj=c(0,0.5),"(y|x=55)=89.4")

# show Delta calculation in plot space

text(x=60,y=65,expression(paste(Delta," = 49.5")),adj=c(0,0.5))

```

<p align="left">
<img src="/gfiles/fig2a.png" width="750px">
</p>

*Note*: here is a way to draw the plot without using the abline() function.

```R
plot.new()
plot.window(xlim=c(-100,100),ylim=c(-100,100))

# x- and y-axes

segments(x0=-100,y0=0,x1=100,y1=0,lty=1,lwd=2)
segments(x0=0,y0=-100,x1=0,y1=100,lty=1,lwd=2)
text(x=4,y=-4,"O")

# points for line 1

x1.line1 <- -47
y1.line1 <- -27

points(x=x1.line1,y=y1.line1,pch=19,cex=1.2,col="blue")

x2.line1 <- 38
y2.line1 <- 70

points(x=x2.line1,y=y2.line1,pch=19,cex=1.2,col="blue")

# slope for line 1
# slope = (y2-y1)/(x2-x1)

slope.line1 <- (y2.line1-y1.line1)/(x2.line1-x1.line1)
slope.line1

# intercept for line 1
# y <- a + bx
# a <- y - bx

int.line1 <- y2.line1-slope.line1*x2.line1
int.line1

# draw line 1

line1.beginning.x <- -100
line1.beginning.x
line1.beginning.y <- int.line1+slope.line1*line1.beginning.x
line1.beginning.y

line1.end.x <- 100
line1.end.x
line1.end.y <- int.line1+slope.line1*line1.end.x
line1.end.y

segments(x0=line1.beginning.x,
         y0=line1.beginning.y,
         x1=line1.end.x,
         y1=line1.end.y,lty=1,lwd=1,col="blue")

# points for line 2

x1.line2 <- -75
y1.line2 <- -15

points(x=x1.line2,y=y1.line2,pch=19,cex=1.2,col="red")

x2.line2 <- 15
y2.line2 <- 23

points(x=x2.line2,y=y2.line2,pch=19,cex=1.2,col="red")

# slope for line 2
# slope = (y2-y1)/(x2-x1)

slope.line2 <- (y2.line2-y1.line2)/(x2.line2-x1.line2)
slope.line2

# intercept for line 2
# y <- a + bx
# a <- y - bx

int.line2 <- y2.line2-slope.line2*x2.line2
int.line2

# draw line 2

line2.beginning.x <- -100
line2.beginning.x
line2.beginning.y <- int.line2+slope.line2*line2.beginning.x
line2.beginning.y

line2.end.x <- 100
line2.end.x
line2.end.y <- int.line2+slope.line2*line2.end.x
line2.end.y

segments(x0=line2.beginning.x,
         y0=line2.beginning.y,
         x1=line2.end.x,
         y1=line2.end.y,lty=1,lwd=1,col="red")
```

5. Summation (and addition)

Suppose we have the following 5 data points collected into an array or vector called *x*:

x = [7,6,3,4,5]

To get the sum of the x values, we can simply add them together:

```rout
> 7+6+3+4+5
[1] 25
>
```

Or, we can identify them as a vector and use the sum function:

```rout
> x <- c(7,6,3,4,5)
> sum(x)
[1] 25
> 
```
An advantage of the vector operation is that the data elements are indexed:

```rout
> x[4]
[1] 4
> x[2]
[1] 6
> sum(x[1:3])
[1] 16
> 
```

The notation for summing a vector, x, of N observations where each individual observation is indexed as *i = 1, 2, ..., N*:

<p align="left">
<img src="/gfiles/eq4.png" width="100px">
</p>

6. Products (and multiplication)

Let's use the same vector *x*. Suppose we want to multiply the elements of the vector. We can use the multiplication 
operator:

```Rout
> 7*6*3*4*5
[1] 2520
```

We can also use the prod function to do the same operation:

```Rout
> prod(x)
[1] 2520
> 
```

If we are working with a vector of observations, the elements are
indexed so we can work with a subset of the vector. Suppose we want
to multiply the first 3 elements of the vector:

```Rout
> prod(x[1:3])
[1] 126
> 
```

The notation for a product of the elements of a vector is:

<p align="left">
<img src="/gfiles/eq5.png" width="100px">
</p>

7. Order of operations

Consider the following operation:

<p align="left">
<img src="/gfiles/eq6.png" width="300px">
</p>

If we type this set of operations into a calculator, we get:

```rout
> 3^2+5*8/2+3-2
[1] 30
```

We can clarify the order of operations by using parentheses (which always have the highest priority):

```rout
> (3^2)+(5*(8/2))+3-2
[1] 30
> 9+20+3-2
[1] 30
```
The standard order of operations acronym is PEDMAS (parentheses, exponents, division, multiplication, addition, and subtraction)

8. Additive and multiplicative inverses

The additive inverse of 7 is *x* in the following equation:

<p align="left">
<img src="/gfiles/eq7a.png" width="100px">
</p>

so we subtract 7 from both sides:

<p align="left">
<img src="/gfiles/eq8.png" width="100px">
</p>

to get x = -7.

The multiplicative inverse for a number (7 in this example) is equal to the number, *x*, that must be multiplied by that number to get 1.

<p align="left">
<img src="/gfiles/eq9a.png" width="100px">
</p>

which can be rewritten as:

<p align="left">
<img src="/gfiles/eq9.png" width="100px">
</p>

Then, we divide both sides of the equation by *x*:

<p align="left">
<img src="/gfiles/eq10.png" width="100px">
</p>

which simplifies to:

<p align="left">
<img src="/gfiles/eq12.png" width="100px">
</p>

9. Absolute values

The absolute value represents the magnitude of a real number regardless of its sign. For example, using a calculator, consider the following assignment of absolute values for the array of integers from -10 to 10. To illustrate this operation, here is a plot:

```r
plot(x=-10:10,y=abs(-10:10))
```

<p align="left">
<img src="/gfiles/fig3.png" width="500px">
</p>

10. Exponents and Logarithms

An exponent *n* represents the number of times a number, *x*, (the base) is multiplied by itself as in: *x*<sup>n</sup>. Here is an example using a calculator with *n* set to 2, 3, and 4.

```r
x <- (-10:10)
xsq <- x^2
xcu <- x^3
xqu <- x^4
data.frame(x,xsq,xcu,xqu)
```

```rout
> x <- (-10:10)
> xsq <- x^2
> xcu <- x^3
> xqu <- x^4
> data.frame(x,xsq,xcu,xqu)
     x xsq   xcu   xqu
1  -10 100 -1000 10000
2   -9  81  -729  6561
3   -8  64  -512  4096
4   -7  49  -343  2401
5   -6  36  -216  1296
6   -5  25  -125   625
7   -4  16   -64   256
8   -3   9   -27    81
9   -2   4    -8    16
10  -1   1    -1     1
11   0   0     0     0
12   1   1     1     1
13   2   4     8    16
14   3   9    27    81
15   4  16    64   256
16   5  25   125   625
17   6  36   216  1296
18   7  49   343  2401
19   8  64   512  4096
20   9  81   729  6561
21  10 100  1000 10000
> 
```

A logarithm represents the exponent to which the base is raised given the final product and the base. Here is an example:

```r
x <- 10
n <- 2
y <- x^n
log(x^n,base=10)
log(y,base=x)
```

```rout
> x <- 10
> n <- 2
> y <- x^n
> log(x^n,base=10)
[1] 2
> log(y,base=x)
[1] 2
> 
```

which illustrates the following relationship:

<p align="left">
<img src="/gfiles/log-eq.png" width="300px">
</p>

Here is another example. Consider the following limit:

```r
n <- 0.001
(1+1/n)^n

n <- 1
(1+1/n)^n

n <- 10
(1+1/n)^n

n <- 100
(1+1/n)^n

n <- 1000
(1+1/n)^n

n <- 10000
(1+1/n)^n

n <- 100000
(1+1/n)^n

n <- 1000000
(1+1/n)^n
```

```rout
> n <- 0.001
> (1+1/n)^n
[1] 1.006933
> n <- 1
> (1+1/n)^n
[1] 2
> n <- 10
> (1+1/n)^n
[1] 2.593742
> n <- 100
> (1+1/n)^n
[1] 2.704814
> n <- 1000
> (1+1/n)^n
[1] 2.716924
> n <- 10000
> (1+1/n)^n
[1] 2.718146
> n <- 100000
> (1+1/n)^n
[1] 2.718268
> n <- 1000000
> (1+1/n)^n
[1] 2.71828
> 
```

In this example, *n* can be any positive real number. As *n* goes to infinity, then (1+1/n)^n approaches *e* ≈ 2.71828 (Euler's constant). To see the limit visually, let's graph the function. Here is the code:

```r
n <- seq(from=0.001,to=1000,by=0.001)
e <- (1+1/n)^n
plot(x=n,y=e,type="l",lty=1,lwd=2,xlab="n",ylab="(1+1/n)^n")
abline(h=seq(from=1.0,to=2.5,by=0.5))
abline(v=seq(from=0,to=1000,by=200))
```

<p align="left">
<img src="/gfiles/fig4a.png" width="500px">
</p>


Now, any logarithm with a base set to the value *e* is called the *natural logarithm*. Here is an application:

```r
e <- 2.718281828
e^12
log(162754.8,base=e)
log(162754.8)
```

```rout
> e <- 2.718281828
> e^12
[1] 162754.8
> log(162754.8,base=e)
[1] 12
> log(162754.8)
[1] 12
```

And, we can recover the original product by exponentiating it (i.e., raising *e* to power equal to the natural log):

```rout
e^12
exp(12)
```

```rout
> e^12
[1] 162754.8
> exp(12)
[1] 162754.8
>
```

It is useful to note that:

<p align="left">
<img src="/gfiles/log.png" width="500px">
</p>

```r
x <- 9
y <- 3
log(9*3)
log(x*y)
log(x)+log(y)

log(9/3)
log(x/y)
log(x)-log(y)
```

```rout
> x <- 9
> y <- 3
> log(9*3)
[1] 3.295837
> log(x*y)
[1] 3.295837
> log(x)+log(y)
[1] 3.295837
> 
> log(9/3)
[1] 1.098612
> log(x/y)
[1] 1.098612
> log(x)-log(y)
[1] 1.098612
> 
```

It is also useful to note that logarithms are *monotonic transformations* -- meaning that the rank ordering of a stream of numbers, *x*, will not change when we evaluate the log-transformed set of those same numbers. Here is an example of how this kind of transformation can be useful:

<p align="left">
<img src="/gfiles/xlogx.png" width="700px">
</p>


11. Radicals

We use the radical symbol to denote the operation of raising a base to a fractional power (i.e., a power less than 1). The general equality between radicals and fractional exponents is:

<p align="left">
<img src="/gfiles/eq13.png" width="300px">
</p>


Using a calculator, we can evaluate any radical or fractional exponent:

```r
d <- 2
n <- 1
base <- 9
sqrt(base)
base^(n/d)

d <- 3
n <- 1
base <- 27
base^(n/d)

d <- 4
n <- 1
base <- 10000
base^(n/d)
```

```rout
> d <- 2
> n <- 1
> base <- 9
> sqrt(base)
[1] 3
> base^(n/d)
[1] 3
> 
> d <- 3
> n <- 1
> base <- 27
> base^(n/d)
[1] 3
> 
> d <- 4
> n <- 1
> base <- 10000
> base^(n/d)
[1] 10
>
```

12. Factoring

Now, suppose we have the following binomials:

<p align="left">
<img src="/gfiles/eq14.png" width="200px">
</p>

To get this product, we can use the so-called FOIL method (where F = First, O = Outside, I = Inside, and L = Last): F = x*x = x^2, O = -3x, I = +5x, L = 5*(-3) = -15.

So, the trinomial is:

<p align="left">
<img src="/gfiles/eq15.png" width="200px">
</p>

13. Roots

Next, we work from a trinomial back to its binomials:

<p align="left">
<img src="/gfiles/eq16.png" width="200px">
</p>

```rout
- The three terms of this trinomial are *a* = 2, *b* = -3, and *c* = -35.
- Multiply a x c = 2 x -35 = -70
- Which 2 numbers multiplied together give a product of -70 and a sum of -3?; Answer = -10, 7
- Rewrite the equation: 2x^2 - 10x + 7x - 35
- Divide equation into 2 parts: (2x^2 - 10x) + (7x - 35)
- Factor the parts: 2x(x-5) + 7(x-5)
- Group the terms: (2x+7)(x-5)
- Check work using FOIL method: 2x^2-10x+7x-35 = 2x^2-3x-35
```

It follows that if we set x to either -7/2 or 5 the equation will be zero; so -7/2 and 5 
are the roots of the trinomial (the values of x that lead to a zero value for the trinomial).

14. Quadratic Formula

There is a closed form solution for finding the roots of a quadratic equation like the one we
just solved. The first step is to calculate a quantity called the discriminant:

<p align="left">
<img src="/gfiles/eq18.png" width="200px">
</p>

If d > 0, then there are 2 real number solutions; on the other hand if d = 0, then there is only one real number solution. If d < 0, then the solution will involve imaginary numbers. Let's consider the trinomial with which we just worked.

```r
a <- 2
b <- -3
c <- -35
d <- b^2-4*a*c
d
```

```rout
> a <- 2
> b <- -3
> c <- -35
> d <- b^2-4*a*c
> d
[1] 289
> 
```

Since *d* is positive, we now know there are two real number roots to this trinomial. We are now ready to solve the quadratic formula:

<p align="left">
<img src="/gfiles/eq19.png" width="300px">
</p>

Here are the calculations:

```r
a <- 2
b <- -3
c <- -35
root1 <- (-b+sqrt(b^2-4*a*c))/(2*a)
root1
root2 <- (-b-sqrt(b^2-4*a*c))/(2*a)
root2
```

```rout
> a <- 2
> b <- -3
> c <- -35
> root1 <- (-b+sqrt(b^2-4*a*c))/(2*a)
> root1
[1] 5
> root2 <- (-b-sqrt(b^2-4*a*c))/(2*a)
> root2
[1] -3.5
> 
```

Note that these roots equal what we calculated before.

15. Functions

A function expresses a relationship between an independent and a dependent variable where the dependent variable can only take on a single value for a given value of the independent variable. If a dependent variable can take on multiple values for a single value of an independent variable, then the expression for that relationship is not a function. The array of values the independent variable can take on is called the domain of the function while the array of outcome values is called the range of the function.  Here are a couple of examples:

```r
# Example 1

x <- seq(from=0,to=10,by=0.1)
y <- exp(0.8*x)
plot(x=x,y=y,type="l",lty=1,lwd=1)
abline(h=seq(from=0,to=3000,by=500),lty=2,lwd=0.8)
abline(v=seq(from=0,to=10,by=2),lty=2,lwd=0.8)
data.frame(x,y)
```
Here are the *x* and *y* values generated by this operation:

```rout
> data.frame(x,y)
       x           y
1    0.0    1.000000
2    0.1    1.083287
3    0.2    1.173511
4    0.3    1.271249
5    0.4    1.377128
6    0.5    1.491825
7    0.6    1.616074
8    0.7    1.750673
9    0.8    1.896481
10   0.9    2.054433
11   1.0    2.225541
12   1.1    2.410900
13   1.2    2.611696
14   1.3    2.829217
15   1.4    3.064854
16   1.5    3.320117
17   1.6    3.596640
18   1.7    3.896193
19   1.8    4.220696
20   1.9    4.572225
21   2.0    4.953032
22   2.1    5.365556
23   2.2    5.812437
24   2.3    6.296538
25   2.4    6.820958
26   2.5    7.389056
27   2.6    8.004469
28   2.7    8.671138
29   2.8    9.393331
30   2.9   10.175674
31   3.0   11.023176
32   3.1   11.941264
33   3.2   12.935817
34   3.3   14.013204
35   3.4   15.180322
36   3.5   16.444647
37   3.6   17.814273
38   3.7   19.297972
39   3.8   20.905243
40   3.9   22.646380
41   4.0   24.532530
42   4.1   26.575773
43   4.2   28.789191
44   4.3   31.186958
45   4.4   33.784428
46   4.5   36.598234
47   4.6   39.646394
48   4.7   42.948426
49   4.8   46.525474
50   4.9   50.400445
51   5.0   54.598150
52   5.1   59.145470
53   5.2   64.071523
54   5.3   69.407852
55   5.4   75.188628
56   5.5   81.450869
57   5.6   88.234673
58   5.7   95.583480
59   5.8  103.544348
60   5.9  112.168253
61   6.0  121.510418
62   6.1  131.630664
63   6.2  142.593796
64   6.3  154.470015
65   6.4  167.335370
66   6.5  181.272242
67   6.6  196.369875
68   6.7  212.724946
69   6.8  230.442183
70   6.9  249.635037
71   7.0  270.426407
72   7.1  292.949430
73   7.2  317.348329
74   7.3  343.779341
75   7.4  372.411714
76   7.5  403.428793
77   7.6  437.029195
78   7.7  473.428075
79   7.8  512.858511
80   7.9  555.572992
81   8.0  601.845038
82   8.1  651.970946
83   8.2  706.271695
84   8.3  765.094993
85   8.4  828.817511
86   8.5  897.847292
87   8.6  972.626360
88   8.7 1053.633557
89   8.8 1141.387607
90   8.9 1236.450433
91   9.0 1339.430764
92   9.1 1450.988025
93   9.2 1571.836563
94   9.3 1702.750221
95   9.4 1844.567294
96   9.5 1998.195895
97   9.6 2164.619772
98   9.7 2344.904605
99   9.8 2540.204834
100  9.9 2751.771046
101 10.0 2980.957987
```

And, here is a graph of the function:

<p align="left">
<img src="/gfiles/fig5a.png" width="700px">
</p>

Now, we consider an example of a quadratic function:

```r
x <- seq(from=-10,to=10,by=0.1)
y <- 0.25*x^2
plot(x=x,y=y,type="l",lty=1,lwd=1)
abline(h=seq(from=0,to=25,by=5),lty=2,lwd=0.8)
abline(v=seq(from=-10,to=10,by=5),lty=2,lwd=0.8)
data.frame(x,y)
```

Here are the *x* and *y* values generated by this operation:

```rout
> data.frame(x,y)
        x       y
1   -10.0 25.0000
2    -9.9 24.5025
3    -9.8 24.0100
4    -9.7 23.5225
5    -9.6 23.0400
6    -9.5 22.5625
7    -9.4 22.0900
8    -9.3 21.6225
9    -9.2 21.1600
10   -9.1 20.7025
11   -9.0 20.2500
12   -8.9 19.8025
13   -8.8 19.3600
14   -8.7 18.9225
15   -8.6 18.4900
16   -8.5 18.0625
17   -8.4 17.6400
18   -8.3 17.2225
19   -8.2 16.8100
20   -8.1 16.4025
21   -8.0 16.0000
22   -7.9 15.6025
23   -7.8 15.2100
24   -7.7 14.8225
25   -7.6 14.4400
26   -7.5 14.0625
27   -7.4 13.6900
28   -7.3 13.3225
29   -7.2 12.9600
30   -7.1 12.6025
31   -7.0 12.2500
32   -6.9 11.9025
33   -6.8 11.5600
34   -6.7 11.2225
35   -6.6 10.8900
36   -6.5 10.5625
37   -6.4 10.2400
38   -6.3  9.9225
39   -6.2  9.6100
40   -6.1  9.3025
41   -6.0  9.0000
42   -5.9  8.7025
43   -5.8  8.4100
44   -5.7  8.1225
45   -5.6  7.8400
46   -5.5  7.5625
47   -5.4  7.2900
48   -5.3  7.0225
49   -5.2  6.7600
50   -5.1  6.5025
51   -5.0  6.2500
52   -4.9  6.0025
53   -4.8  5.7600
54   -4.7  5.5225
55   -4.6  5.2900
56   -4.5  5.0625
57   -4.4  4.8400
58   -4.3  4.6225
59   -4.2  4.4100
60   -4.1  4.2025
61   -4.0  4.0000
62   -3.9  3.8025
63   -3.8  3.6100
64   -3.7  3.4225
65   -3.6  3.2400
66   -3.5  3.0625
67   -3.4  2.8900
68   -3.3  2.7225
69   -3.2  2.5600
70   -3.1  2.4025
71   -3.0  2.2500
72   -2.9  2.1025
73   -2.8  1.9600
74   -2.7  1.8225
75   -2.6  1.6900
76   -2.5  1.5625
77   -2.4  1.4400
78   -2.3  1.3225
79   -2.2  1.2100
80   -2.1  1.1025
81   -2.0  1.0000
82   -1.9  0.9025
83   -1.8  0.8100
84   -1.7  0.7225
85   -1.6  0.6400
86   -1.5  0.5625
87   -1.4  0.4900
88   -1.3  0.4225
89   -1.2  0.3600
90   -1.1  0.3025
91   -1.0  0.2500
92   -0.9  0.2025
93   -0.8  0.1600
94   -0.7  0.1225
95   -0.6  0.0900
96   -0.5  0.0625
97   -0.4  0.0400
98   -0.3  0.0225
99   -0.2  0.0100
100  -0.1  0.0025
101   0.0  0.0000
102   0.1  0.0025
103   0.2  0.0100
104   0.3  0.0225
105   0.4  0.0400
106   0.5  0.0625
107   0.6  0.0900
108   0.7  0.1225
109   0.8  0.1600
110   0.9  0.2025
111   1.0  0.2500
112   1.1  0.3025
113   1.2  0.3600
114   1.3  0.4225
115   1.4  0.4900
116   1.5  0.5625
117   1.6  0.6400
118   1.7  0.7225
119   1.8  0.8100
120   1.9  0.9025
121   2.0  1.0000
122   2.1  1.1025
123   2.2  1.2100
124   2.3  1.3225
125   2.4  1.4400
126   2.5  1.5625
127   2.6  1.6900
128   2.7  1.8225
129   2.8  1.9600
130   2.9  2.1025
131   3.0  2.2500
132   3.1  2.4025
133   3.2  2.5600
134   3.3  2.7225
135   3.4  2.8900
136   3.5  3.0625
137   3.6  3.2400
138   3.7  3.4225
139   3.8  3.6100
140   3.9  3.8025
141   4.0  4.0000
142   4.1  4.2025
143   4.2  4.4100
144   4.3  4.6225
145   4.4  4.8400
146   4.5  5.0625
147   4.6  5.2900
148   4.7  5.5225
149   4.8  5.7600
150   4.9  6.0025
151   5.0  6.2500
152   5.1  6.5025
153   5.2  6.7600
154   5.3  7.0225
155   5.4  7.2900
156   5.5  7.5625
157   5.6  7.8400
158   5.7  8.1225
159   5.8  8.4100
160   5.9  8.7025
161   6.0  9.0000
162   6.1  9.3025
163   6.2  9.6100
164   6.3  9.9225
165   6.4 10.2400
166   6.5 10.5625
167   6.6 10.8900
168   6.7 11.2225
169   6.8 11.5600
170   6.9 11.9025
171   7.0 12.2500
172   7.1 12.6025
173   7.2 12.9600
174   7.3 13.3225
175   7.4 13.6900
176   7.5 14.0625
177   7.6 14.4400
178   7.7 14.8225
179   7.8 15.2100
180   7.9 15.6025
181   8.0 16.0000
182   8.1 16.4025
183   8.2 16.8100
184   8.3 17.2225
185   8.4 17.6400
186   8.5 18.0625
187   8.6 18.4900
188   8.7 18.9225
189   8.8 19.3600
190   8.9 19.8025
191   9.0 20.2500
192   9.1 20.7025
193   9.2 21.1600
194   9.3 21.6225
195   9.4 22.0900
196   9.5 22.5625
197   9.6 23.0400
198   9.7 23.5225
199   9.8 24.0100
200   9.9 24.5025
201  10.0 25.0000
> 
```

and this is a graph of the function (a parabola):

<p align="left">
<img src="/gfiles/fig6.png" width="700px">
</p>

16. Straight lines

The usual equation for a straight line on a Cartesian plot space (x,y coordinates) is:

<p align="left">
<img src="/gfiles/eq20.png" width="200px">
</p>

The term, *a*, is the y-intercept (i.e., the value of *y* when *x* is set to zero). The term, *b*, represents the slope (rise/run) of the line. Suppose we have the following data points generated by the function y=2+2x:

```r
x <- seq(from=-1,to=10,by=1)
y <- 2+2*x
data.frame(x,y)
```


```rout
> x <- seq(from=-1,to=10,by=1)
> y <- 2+2*x
> data.frame(x,y)
    x  y
1  -1  0
2   0  2
3   1  4
4   2  6
5   3  8
6   4 10
7   5 12
8   6 14
9   7 16
10  8 18
11  9 20
12 10 22
```

Here is the code to generate the plot:

```r
plot(x=x,y=y,pch=19)
abline(h=seq(from=0,to=20,by=5),lty=3,lwd=0.5)
abline(v=seq(from=0,to=10,by=2),lty=3,lwd=0.5)
```

Here is a plot of the points in the 2-dimensional xy space:

<p align="left">
<img src="/gfiles/fig7.png" width="700px">
</p>

How can we work from these points back to the function that generated them? First, we calculate the slope of the line:

<p align="left">
<img src="/gfiles/eq21.png" width="200px">
</p>

```r
y2 <- 8
y1 <- 4
x2 <- 3
x1 <- 1
b <- (y2-y1)/(x2-x1)
b
```

```rout
> y2 <- 8
> y1 <- 4
> x2 <- 3
> x1 <- 1
> b <- (y2-y1)/(x2-x1)
> b
[1] 2
>
```
Once we have the slope of the line, it is easy to calculate the y-intercept (by subtracting *bx* from both sides of the equation):

<p align="left">
<img src="/gfiles/eq22.png" width="200px">
</p>

```r
x <- 1
y <- 4
y-b*x
```

```rout
> x <- 1
> y <- 4
> y-b*x
[1] 2
> 
```

So, now we have the y-intercept and the slope so we can draw the line on the plot:

```r
slope <- 2
y.int <- 2
x <- -1
y <- y.int+slope*x
y
x <- 10
y <- y.int+slope*x
y
segments(x0=-1,y0=0,x1=10,y1=22,lty=1,lwd=1)
```

```rout
> slope <- 2
> y.int <- 2
> x <- -1
> y <- y.int+slope*x
> y
[1] 0
> x <- 10
> y <- y.int+slope*x
> y
[1] 22
> segments(x0=-1,y0=0,x1=10,y1=22,lty=1,lwd=1)
> 
```

and we now have the line drawn through the points on the plotspace:

<p align="left">
<img src="/gfiles/fig8.png" width="700px">
</p>

17. Curves

Now, let's consider another exponential curve:

```r
x <- seq(from=0,to=10,by=0.1)
y <- exp(0.5*x)
data.frame(x,y)
```

```rout
> x <- seq(from=0,to=10,by=0.1)
> y <- exp(0.5*x)
> data.frame(x,y)
       x          y
1    0.0   1.000000
2    0.1   1.051271
3    0.2   1.105171
4    0.3   1.161834
5    0.4   1.221403
6    0.5   1.284025
7    0.6   1.349859
8    0.7   1.419068
9    0.8   1.491825
10   0.9   1.568312
11   1.0   1.648721
12   1.1   1.733253
13   1.2   1.822119
14   1.3   1.915541
15   1.4   2.013753
16   1.5   2.117000
17   1.6   2.225541
18   1.7   2.339647
19   1.8   2.459603
20   1.9   2.585710
21   2.0   2.718282
22   2.1   2.857651
23   2.2   3.004166
24   2.3   3.158193
25   2.4   3.320117
26   2.5   3.490343
27   2.6   3.669297
28   2.7   3.857426
29   2.8   4.055200
30   2.9   4.263115
31   3.0   4.481689
32   3.1   4.711470
33   3.2   4.953032
34   3.3   5.206980
35   3.4   5.473947
36   3.5   5.754603
37   3.6   6.049647
38   3.7   6.359820
39   3.8   6.685894
40   3.9   7.028688
41   4.0   7.389056
42   4.1   7.767901
43   4.2   8.166170
44   4.3   8.584858
45   4.4   9.025013
46   4.5   9.487736
47   4.6   9.974182
48   4.7  10.485570
49   4.8  11.023176
50   4.9  11.588347
51   5.0  12.182494
52   5.1  12.807104
53   5.2  13.463738
54   5.3  14.154039
55   5.4  14.879732
56   5.5  15.642632
57   5.6  16.444647
58   5.7  17.287782
59   5.8  18.174145
60   5.9  19.105954
61   6.0  20.085537
62   6.1  21.115344
63   6.2  22.197951
64   6.3  23.336065
65   6.4  24.532530
66   6.5  25.790340
67   6.6  27.112639
68   6.7  28.502734
69   6.8  29.964100
70   6.9  31.500392
71   7.0  33.115452
72   7.1  34.813317
73   7.2  36.598234
74   7.3  38.474666
75   7.4  40.447304
76   7.5  42.521082
77   7.6  44.701184
78   7.7  46.993063
79   7.8  49.402449
80   7.9  51.935367
81   8.0  54.598150
82   8.1  57.397457
83   8.2  60.340288
84   8.3  63.434000
85   8.4  66.686331
86   8.5  70.105412
87   8.6  73.699794
88   8.7  77.478463
89   8.8  81.450869
90   8.9  85.626944
91   9.0  90.017131
92   9.1  94.632408
93   9.2  99.484316
94   9.3 104.584986
95   9.4 109.947172
96   9.5 115.584285
97   9.6 121.510418
98   9.7 127.740390
99   9.8 134.289780
100  9.9 141.174964
101 10.0 148.413159
> 
```

Here is a plot of the function:

```R
plot(x=x,y=y,type="l",lty=1,lwd=1)
abline(h=seq(from=0,to=150,by=50),lty=2,lwd=0.5)
abline(v=seq(from=0,to=10,by=2),lty=2,lwd=0.5)
```

<p align="left">
<img src="/gfiles/fig9.png" width="700px">
</p>

18. Secant lines

Now, let's add to this plot by drawing a dark red *secant* line through two points in the plotspace.

```r
xa <- 2
ya <- 2.718282
xb <- 8
yb <- 54.598150

slope <- (yb-ya)/(xb-xa)
slope
y.int <- 2.718282-slope*xa
y.int

abline(a=y.int,b=slope,lty=1,lwd=1,col="darkred")
```

Here are the results:

```rout
> plot(x=x,y=y,type="l",lty=1,lwd=1)
> abline(h=seq(from=0,to=150,by=50),lty=2,lwd=0.5)
> abline(v=seq(from=0,to=10,by=2),lty=2,lwd=0.5)
> 
> xa <- 2
> ya <- 2.718282
> xb <- 8
> yb <- 54.598150
> 
> slope <- (yb-ya)/(xb-xa)
> slope
[1] 8.646645
> y.int <- 2.718282-slope*xa
> y.int
[1] -14.57501
> 
> abline(a=y.int,b=slope,lty=1,lwd=1,col="darkred")
> 
```
<p align="left">
<img src="/gfiles/fig10.png" width="700px">
</p>

19-21. Tangent Lines, Limits, and Derivatives

The slope of the secant line we just calculated is an example of a *difference quotient* and represents the total amount of change in *y* divided by the change in *x* as we move from *xa* = 2 to *xb* = 8. The formal definition of a difference quotient is:

<p align="left">
<img src="/gfiles/eq23.png" width="200px">
</p>

where *f(x)* is:

<p align="left">
<img src="/gfiles/eq24.png" width="200px">
</p>

Next, let's set *xa* = 4 and *xb* = 6. In terms of the difference quotient equation, this gives us a value of *x* = 4 and *Δx* = 2. Then, we will add a dark green secant line to the plot representing the new difference quotient.

```r
xa <- 4
ya <- 7.389056
xb <- 6
yb <- 20.085537
slope <- (yb-ya)/(xb-xa)
slope
y.int <- 7.389056-slope*xa
y.int
abline(a=y.int,b=slope,lty=1,lwd=1,col="darkgreen")
```

```Rout
> xa <- 4
> ya <- 7.389056
> xb <- 6
> yb <- 20.085537
> slope <- (yb-ya)/(xb-xa)
> 
> slope
[1] 6.34824
> y.int <- 7.389056-slope*xa
> y.int
[1] -18.00391
> abline(a=y.int,b=slope,lty=1,lwd=1,col="darkgreen")
> 
```
<p align="left">
<img src="/gfiles/fig11.png" width="700px">
</p>

So, the slope of the secant line over the range of [*xa*=2, *xb*=8] is steeper than the slope of the secant line over the range of [*xa*=4,*xb*=6]. Let's  intensify our focus on the slope of the secant line in the neighborhood of *x* = 5. 

```r
x <- seq(from=4.8,to=5.2,by=0.001)
y <- exp(0.5*x)
data.frame(x,y)
```

```rout
> x <- seq(from=4.8,to=5.2,by=0.001)
> y <- exp(0.5*x)
> data.frame(x,y)

1   4.800 11.02318
2   4.801 11.02869
3   4.802 11.03421
4   4.803 11.03972
5   4.804 11.04524
6   4.805 11.05077
7   4.806 11.05630
8   4.807 11.06183
9   4.808 11.06736
10  4.809 11.07289
11  4.810 11.07843
12  4.811 11.08397
13  4.812 11.08951
*
*
*
196 4.995 12.15208
197 4.996 12.15815
198 4.997 12.16423
199 4.998 12.17032
200 4.999 12.17640
201 5.000 12.18249
202 5.001 12.18859
203 5.002 12.19468
204 5.003 12.20078
205 5.004 12.20688
206 5.005 12.21299
*
*
*
389 5.188 13.38320
390 5.189 13.38989
391 5.190 13.39659
392 5.191 13.40329
393 5.192 13.40999
394 5.193 13.41670
395 5.194 13.42341
396 5.195 13.43012
397 5.196 13.43684
398 5.197 13.44356
399 5.198 13.45028
400 5.199 13.45701
401 5.200 13.46374
```

We can look at the slope of the secant line in the range of [*xa* = 4.999, *xb* = 5.001]. Here are the results:

```r
xa <- 4.999
ya <- 12.17640
xb <- 5.001
yb <- 12.18859

slope <- (yb-ya)/(xb-xa)
slope
y.int <- 12.17640-slope*xa
y.int
```

```rout
> xa <- 4.999
> ya <- 12.17640
> xb <- 5.001
> yb <- 12.18859
> 
> slope <- (yb-ya)/(xb-xa)
> slope
[1] 6.095
> y.int <- 12.17640-slope*xa
> y.int
[1] -18.2925
```

This slope is slightly flatter still in comparison to the previous 2 slopes. It is also useful to notice in the plot below that the function is close to a straight line in this region of the function. In the plot, the black curve is the function while the secant line is colored orange.

```R
plot(x=x,y=y,type="l",lty=1,lwd=1)
abline(a=y.int,b=slope,col="orange")
abline(h=seq(from=11.0,to=13.5,by=0.5),lty=2,lwd=0.5)
abline(v=seq(from=4.8,to=5.2,by=0.1),lty=2,lwd=0.5)
```
<p align="left">
<img src="/gfiles/fig13.png" width="700px">
</p>

As the change in *x* gets closer to zero, the slope of the secant line in that neighborhood of *x* covers a smaller range of *x* values. As the change in *x* vanishes, then the secant line becomes a tangent line. The (first) derivative of the function at a particular value of *x* is equivalent to the slope of the tangent line. To see this, we continue to shrink the difference between *xa* and *xb*:

```r
xa <- 4.99999
xb <- 5.00001
ya <- exp(0.5*xa)
yb <- exp(0.5*xb)
slope <- (yb-ya)/(xb-xa)
slope
```

```rout
> xa <- 4.99999
> xb <- 5.00001
> ya <- exp(0.5*xa)
> yb <- exp(0.5*xb)
> slope <- (yb-ya)/(xb-xa)
> slope
[1] 6.091247
> 
```

Then, we can check our work with a calculator:

```r
d <- deriv(~ exp(0.5*x), "x")
x <- 5
eval(d)
```

```rout
> d <- deriv(~ exp(0.5*x), "x")
> x <- 5
> eval(d)
[1] 12.18249
attr(,"gradient")
            x
[1,] 6.091247
> 
```
Note that we can use basic calculus (specifically, the chain rule) to derive a formula for calculating the slope of the line at any single point in the domain of the function. In this case, the derivative would be:

<p align="left">
<img src="/gfiles/eq30.png" width="300px">
</p>

which we can calculate for *x* = 5 (or any other *x* in the domain of the function we choose):

```r
d.5 <- 1/2*exp(5/2)
d.5
```

```rout
> d.5 <- 1/2*exp(5/2)
> d.5
[1] 6.091247
> 
```

```rout
Problems for Thursday 8/19/21

1. Solve cube root of 1331
2. Find log(e) of 15/10
3. Use the exp() function to "undo" the log(e) operation you carried out in #2
4. Let x go from 1 to 10. Graph the function y = log(e)[x]; Dump out the values of x and y.
5. Find the roots of the trinomial: x^2 - 4x - 21 by factoring and the quadratic formula.
6. Use the FOIL method to factor these binomial terms: (2x + 2)(5x - 7)
7. Use the quadratic formula to find the roots of the trinomial you obtained from #5.

Let x go from 1 to 10 (by 0.1). Graph the function y = sqrt(x).

8. Calculate the slope and intercept of the secant line from x=2 to x=8.
9. Use slope and intercept calculations to draw the secant line from x=2 to x=8.
10. Draw a secant line from x=4 to x=6. Report the slope of the secant line.
11. Draw a secant line from x=4.5 to x=5.5. Report the slope of the secant line.
12. Focus on x=4.999 and x=5.001. Calculate the slope.
13. Focus on x=4.99999 and x=5.00001. Calculate the slope.
14. Calculate the derivative of the function at x=5.
15. Verify that your slope calculations correspond to the derivative.
16. Check on and report the derivative at x=8.

Let x go from 1 to 10 (by 0.1). Graph the function y = x^2.

17. Calculate the slope and intercept of the secant line from x=2 to x=8.
18. Use slope and intercept calculations to draw the secant line from x=2 to x=8.
19. Draw a secant line from x=4 to x=6. Report the slope of the secant line.
20. Draw a secant line from x=4.5 to x=5.5. Report the slope of the secant line.
21. Focus on x=4.999 and x=5.001. Calculate the slope.
22. Focus on x=4.99999 and x=5.00001. Calculate the slope.
23. Calculate the derivative of the function at x=5.
24. Verify that your slope calculations correspond to the derivative.
25. Check on and report the derivative at x=3.

Let x go from 1 to 10 (by 0.1). Graph the function y = 5*x-0.5*x^2

26. Calculate the slope and intercept of the secant line from x=2 to x=8.
27. Use slope and intercept calculations to draw the secant line from x=2 to x=8.
28. Draw a secant line from x=4 to x=6. Report the slope of the secant line.
29. Draw a secant line from x=4.5 to x=5.5. Report the slope of the secant line.
30. Focus on x=4.999 and x=5.001. Calculate the slope.
31. Focus on x=4.99999 and x=5.00001. Calculate the slope.
32. Calculate the derivative of the function at x=5.
33. Verify that your slope calculations correspond to the derivative.
34. Use methods like those above to check on and report the derivative at x=8.
```

22. Random variables

* Example: Minneapolis Domestic Violence Experiment

<p align="left">
<img src="/gfiles/fig14.png" width="600px">
</p>

* The sample space is the set of possible outcomes of a probabilistic process.
* Sample spaces can be discrete (qualitative) or continuous (quantitative).
* For some sample spaces we can count all of the possible outcomes (finite) while others are uncountable (infinite).
* Probabilities are always positive numbers lying in the range of [0,1].
* The sum of the probabilities of each of the possible outcomes will be 1.0.
* Probability can be viewed as the limiting case of a relative frequency distribution.
* Or, probability can be viewed as a more subjective idea of "degree of certainty."
* Events can vary in their probability of occurrence. Just like we can think about the probability of a single event occurring, we can also consider the probability of multiple events occurring or we can think about how the probability of an event occurring might depend or be conditional on the occurrence of other events.

* Manipulation of *x* --> variation in *y* vs. variation in *p(y)*.

23. Bayes' Theorem

```rout
> table(y,x)
   x
y   Arr Med Sep
  0  83  87  87
  1   9  21  27
>
```

```rout
Note: y=0 indicates no failure; y=1 indicates failure

- p(a|b) assuming independence = p(a) x p(b) / p(b)
- p(fail|arrest) assuming independence = p(fail) x p(arrest) / p(arrest)
- p(fail) = (9+21+27)/(83+87+87+9+21+27) = 0.1815287
- p(arrest) = (83+9)/(83+87+87+9+21+27) = 0.2929936
- p(fail) x p(arrest) / p(arrest) = 0.1815287*0.2929936/0.2929936 = 0.1815287

- p(a|b) assuming non-independence = p(a) x p(b|a) / p(b)
- p(fail|arrest) assuming dependence = p(fail) x p(arrest|fail) / p(arrest)
- p(fail) = (9+21+27)/(83+87+87+9+21+27) = 0.1815287
- p(arrest|fail) = 9/(9+21+27) = 0.1578947
- p(arrest) = (83+9)/(83+87+87+9+21+27) = 0.2929936
- p(fail) x p(arrest|fail) / p(arrest) = 0.1815287*0.1578947/0.2929936 = 0.09782609
- check our work: 9/(83+9) = 0.09782609
```

So, the conditional probability of failure given arrest is almost twice as large when we assume that failure and arrest are independent of each other. This indicates some basis for suspecting the two events are not, in fact, independent.

24. Binomial distribution

One of the most basic probability distributions is based on the idea that there is a set of independent experiments or trials (called Bernoulli trials) that each have a sample space of 2 possible outcomes. Let's consider an example from Cook and Zarkin (1985).

* This paper poses the following question: what is the effect of the business cycle on crime?
* Let's begin by considering how the authors define movements in crime and the business cycle.
* Note: here is a [chart](https://www.nber.org/cycles.html) of the business cycles

<p align="center">
<img src="/gfiles/fig20.png" width="800px">
</p>

<p align="center">
<img src="/gfiles/fig21.png" width="800px">
</p>

* The probability model we will use for this problem is based on the binomial distribution:

<p align="center">
<img src="/gfiles/binomial.png" width="750px">
</p>

* Here is the R code:

```R
# 9 complete business cycles (1933-1980)
# Murder: 4 cc movements
# Robbery: 8 cc movements
# Burglary: 8 cc movements
# MV Theft: 2 cc movements 

# If there is no relationship between business cycle
# movements and the crime rate, then PC and CC movments
# in crime should be equally likely when the economy
# changes direction.

p <- 0.5

n <- 9;  r <- 0;  pr0 <-  choose(n,r)*p^r*(1-p)^(n-r);
         r <- 1;  pr1 <-  choose(n,r)*p^r*(1-p)^(n-r);
         r <- 2;  pr2 <-  choose(n,r)*p^r*(1-p)^(n-r);
         r <- 3;  pr3 <-  choose(n,r)*p^r*(1-p)^(n-r);
         r <- 4;  pr4 <-  choose(n,r)*p^r*(1-p)^(n-r);
         r <- 5;  pr5 <-  choose(n,r)*p^r*(1-p)^(n-r);
         r <- 6;  pr6 <-  choose(n,r)*p^r*(1-p)^(n-r);
         r <- 7;  pr7 <-  choose(n,r)*p^r*(1-p)^(n-r);
         r <- 8;  pr8 <-  choose(n,r)*p^r*(1-p)^(n-r);
         r <- 9;  pr9 <-  choose(n,r)*p^r*(1-p)^(n-r);

pr0
pr1
pr2
pr3
pr4
pr5
pr6
pr7
pr8
pr9
```

Here are the results:

```rout
> pr0
[1] 0.001953125
> pr1
[1] 0.01757812
> pr2
[1] 0.0703125
> pr3
[1] 0.1640625
> pr4
[1] 0.2460938
> pr5
[1] 0.2460938
> pr6
[1] 0.1640625
> pr7
[1] 0.0703125
> pr8
[1] 0.01757812
> pr9
[1] 0.001953125
> 
```
To what conclusions does this evidence lead?

- The events r={0,1,8,9} are very unlikely to occur if the acyclicality 
  hypothesis is correct.
- Robbery and burglary both fall within this region so they do not seem 
  to be acyclical (they are countercyclical)
- Murder is acyclical.
- Auto theft is more of a borderline case because there were 2 countercyclical 
  movements and 7 procyclical movements but the evidence does not seem strong
  enough to reject the acyclicality hypothesis.
  




```rout
Problems for Friday 8/20/21

1. Use Bayes' rule to calculate the p(fail|mediate) and p(fail|separate) 
assuming independence. Compare the results assuming non-independence. 
Verify the calculations assuming non-independence are correct.

Solution:

> table(y,x)
   x
y   Arr Med Sep
  0  83  87  87
  1   9  21  27
>

* Calculate p(fail|mediate) assuming independence

p(fail|mediate) = p(fail)p(mediate)/p(mediate)
p(fail) = (9+21+27)/(83+87+87+9+21+27) = 0.1815287
p(mediate) = (87+21)/(83+87+87+9+21+27) = 0.343949
p(fail|mediate) = 0.1815287*0.343949/0.343949 = 0.1815287

* Calculate p(fail|mediate) assuming non-independence

p(fail|mediate) = p(fail)p(mediate|fail)/p(mediate)
p(fail) = (9+21+27)/(83+87+87+9+21+27) = 0.1815287
p(mediate|fail) = 21/(9+21+27) = 0.3684211
p(mediate) = (87+21)/(83+87+87+9+21+27) = 0.343949
p(fail|mediate) = 0.1815287*0.3684211/0.343949 = 0.1944445
check: 21/(87+21) = 0.1944444

* Calculate p(fail|separate) assuming independence

p(fail|separate) = p(fail)p(separate)/p(separate)
p(fail) = (9+21+27)/(83+87+87+9+21+27) = 0.1815287
p(separate) = (87+27)/(83+87+87+9+21+27) = 0.3630573
p(fail|separate) = 0.1815287*0.3630573/0.3630573 = 0.1815287

* Calculate p(fail|separate) assuming non-independence

p(fail|separate) = p(fail)p(separate|fail)/p(separate)
p(fail) = (9+21+27)/(83+87+87+9+21+27) = 0.1815287
p(separate|fail) = 27/(9+21+27) = 0.4736842
p(separate) = (87+27)/(83+87+87+9+21+27) = 0.3630573
p(fail|separate) = 0.1815287*0.4736842/0.3630573 = 0.2368422
check: 27/(87+27) = 0.2368421

2. Consider the following table:

> table(y,x)
   x
y     0   1
  0 238 269
  1 240 253
>

Calculate p(y=1|x=0) and p(y=1|x=1) using Bayes' rule assuming independence. 
Compare the results assuming non-independence and verify your calculations 
using the numbers in the table.

Solution: 

Calculate p(y1|x0) assuming independence

p(y1|x0) = p(y1)p(x0)/p(x0)
p(y1) = (240+253)/(238+269+240+253) = 0.493
p(x0) = (238+240)/(238+269+240+253) = 0.478
p(y1|x0) = 0.493*0.478/0.478 = 0.493

Calculate p(y1|x0) assuming non-independence

p(y1|x0) = p(y1)p(x0|y1)/p(x0)
p(y1) = (240+253)/(238+269+240+253) = 0.493
p(x0|y1) = 240/(240+253) = 0.4868154
p(x0) = (238+240)/(238+269+240+253) = 0.478
p(y1|x0) = 0.493*0.4868154/0.478 = 0.502092
check: 240/(238+240) = 0.5020921

Calculate p(y1|x1) assuming independence

p(y1|x1) = p(y1)p(x1)/p(x1)
p(y1) = (240+253)/(238+269+240+253) = 0.493
p(x1) = (269+253)/(238+269+240+253) = 0.522
p(y1|x1) = 0.493*0.522/0.522 = 0.493

Calculate p(y1|x1) assuming non-independence

p(y1|x1) = p(y1)p(x1|y1)/p(x1)
p(y1) = (240+253)/(238+269+240+253) = 0.493
p(x1|y1) = 253/(240+253) = 0.5131846
p(x1) = (269+253)/(238+269+240+253) = 0.522
p(y1|x1) = 0.493*0.5131846/0.522 = 0.4846743
check: 253/(269+253) = 0.4846743

3. Bushway, Cook, and Philips (2012) updated the Cook and Zarkin (1985) 
study with 4 additional business cycles (for a total of 13 cycles). They 
obtained the following results: Murder (6 countercyclical movements), 
robbery (10 countercyclical movements), burglary (11 countercyclical 
movements), and auto theft (4 countercyclical movements). Develop an 
assessment of whether the conclusions from the earlier study should be 
modified.

Solution:

p <- 0.5

n <- 13; r <- 0;  pr0 <-  choose(n,r)*p^r*(1-p)^(n-r);
         r <- 1;  pr1 <-  choose(n,r)*p^r*(1-p)^(n-r);
         r <- 2;  pr2 <-  choose(n,r)*p^r*(1-p)^(n-r);
         r <- 3;  pr3 <-  choose(n,r)*p^r*(1-p)^(n-r);
         r <- 4;  pr4 <-  choose(n,r)*p^r*(1-p)^(n-r);
         r <- 5;  pr5 <-  choose(n,r)*p^r*(1-p)^(n-r);
         r <- 6;  pr6 <-  choose(n,r)*p^r*(1-p)^(n-r);
         r <- 7;  pr7 <-  choose(n,r)*p^r*(1-p)^(n-r);
         r <- 8;  pr8 <-  choose(n,r)*p^r*(1-p)^(n-r);
         r <- 9;  pr9 <-  choose(n,r)*p^r*(1-p)^(n-r);
         r <- 10; pr10 <-  choose(n,r)*p^r*(1-p)^(n-r);
         r <- 11; pr11 <-  choose(n,r)*p^r*(1-p)^(n-r);
         r <- 12; pr12 <-  choose(n,r)*p^r*(1-p)^(n-r);
         r <- 13; pr13 <-  choose(n,r)*p^r*(1-p)^(n-r);

pr0
pr1
pr2
pr3
pr4
pr5
pr6
pr7
pr8
pr9
pr10
pr11
pr12
pr13

* Here are the results I obtained:

> pr0
[1] 0.0001220703
> pr1
[1] 0.001586914
> pr2
[1] 0.009521484
> pr3
[1] 0.03491211
> pr4
[1] 0.08728027
> pr5
[1] 0.1571045
> pr6
[1] 0.2094727
> pr7
[1] 0.2094727
> pr8
[1] 0.1571045
> pr9
[1] 0.08728027
> pr10
[1] 0.03491211
> pr11
[1] 0.009521484
> pr12
[1] 0.001586914
> pr13
[1] 0.0001220703
> 

* Based on these results, it looks like the events r={0,1,2,11,12,13} are 
  all very unlikely to occur if the acyclicality hypothesis is correct. 
  This suggests the following conclusions:

- Burglary is countercyclical
- For each of the other crimes, there is not enough evidence to reject 
  the acyclicality hypothesis.
```

25. Significance test

* A central concept in significance testing is the so-called *p*-value which
  measures the probability of getting a result at least as extreme as the one
  we got, when the hypothesis being tested is true.

* Let's return to the business cycle-crime example from Cook and Zarkin (1985). 
  Recall that our evidence looks like this:

```Rout
> # 9 complete business cycles (1933-1980)
> # Murder: 4 cc movements
> # Robbery: 8 cc movements
> # Burglary: 8 cc movements
> # MV Theft: 2 cc movements 
> 
> # If there is no relationship between business cycle
> # movements and the crime rate, then PC and CC movments
> # in crime should be equally likely when the economy
> # changes direction.
> 
> p <- 0.5
> 
> n <- 9;  r <- 0;  pr0 <-  choose(n,r)*p^r*(1-p)^(n-r);
>          r <- 1;  pr1 <-  choose(n,r)*p^r*(1-p)^(n-r);
>          r <- 2;  pr2 <-  choose(n,r)*p^r*(1-p)^(n-r);
>          r <- 3;  pr3 <-  choose(n,r)*p^r*(1-p)^(n-r);
>          r <- 4;  pr4 <-  choose(n,r)*p^r*(1-p)^(n-r);
>          r <- 5;  pr5 <-  choose(n,r)*p^r*(1-p)^(n-r);
>          r <- 6;  pr6 <-  choose(n,r)*p^r*(1-p)^(n-r);
>          r <- 7;  pr7 <-  choose(n,r)*p^r*(1-p)^(n-r);
>          r <- 8;  pr8 <-  choose(n,r)*p^r*(1-p)^(n-r);
>          r <- 9;  pr9 <-  choose(n,r)*p^r*(1-p)^(n-r);
> 
> pr0
[1] 0.001953125
> pr1
[1] 0.01757812
> pr2
[1] 0.0703125
> pr3
[1] 0.1640625
> pr4
[1] 0.2460938
> pr5
[1] 0.2460938
> pr6
[1] 0.1640625
> pr7
[1] 0.0703125
> pr8
[1] 0.01757812
> pr9
[1] 0.001953125
```

* How can we construct a formal significance test to evaluate whether the 
  evidence is consistent with the acyclicality hypothesis?

* We begin with the probabilities calculated above. Let's start by adding
  all of the probabilities together:

```rout
> pr0+pr1+pr2+pr3+pr4+pr5+pr6+pr7+pr8+pr9
[1] 1
```

* Second, let's think about the tails of this distribution to formally test the 
hypothesis that crime moves acyclically when the economy moves into a recession. 
Specifically, what is the probability of being in one of the tails outside the 
central 95% of this distribution? To measure this, we can identify the central 
95% of the distribution. Let's try adding the following probabilities:

```
pr1+pr2+pr3+pr4+pr5+pr6+pr7+pr8
[1] 0.9960938
```

* So, dropping the two extremes (pr0 and pr9) gives us the central 99.6% of the 
distribution which is larger than the central 95%. So, let's try again:

```
> pr2+pr3+pr4+pr5+pr6+pr7
[1] 0.9609375
> 
```

* Now, we have dropped pr0 and pr1 on the left tail; we have also dropped pr8 
  and pr9 on the right tail. This gives us the central 96% of the distribution. 
  So, let's try one more time:

```
> pr3+pr4+pr5+pr6
[1] 0.8203125
> 
```

* So, the union of the events r= {3,4,5,6} yields the central 82% of the 
  distribution. If we adopt a (conventional) *p < .05* significance level for 
  our test, this means that the events r={0,1,8,9} clearly meet the standard for 
  rejecting our hypothesis (i.e., these events fall in the critical or rejection
  region of the probability distribution). The probability of any of these events 
  occurring if the hypothesis is true is less than 5%. So, the hypothesis of 
  acyclicality is clearly rejected for burglary and robbery (each one has 8 
  countercyclical movements). It is also clear that there is no basis at all for 
  rejecting the hypothesis of acyclicality for murder (4 countercyclical movements). 
  Auto theft is a borderline case but if we adopt the strict *p < .05* significance 
  level, the evidence is not strong enough to reject the hypothesis of acyclicality.
  
###### New Example

* Suppose homicide occurrence in the U.S. does not change from one year to the 
next. If this is true, we might expect that about half of the states would see
an increase in homicide while the other half would see a decrease. We can test 
this proposition
by thinking of each state as a separate trial or experiment with two outcomes:
(1) the number of homicides increases from one year to the next; or (2) the 
number of homicides does not increase from one year to the next. The 
hypothesis to be tested is whether the probability of either outcome is equally 
likely.

```r
p <- 0.5

n <- 50;  r <- 0;  pr0 <-  choose(n,r)*p^r*(1-p)^(n-r);
          r <- 1;  pr1 <-  choose(n,r)*p^r*(1-p)^(n-r);
          r <- 2;  pr2 <-  choose(n,r)*p^r*(1-p)^(n-r);
          r <- 3;  pr3 <-  choose(n,r)*p^r*(1-p)^(n-r);
          r <- 4;  pr4 <-  choose(n,r)*p^r*(1-p)^(n-r);
          r <- 5;  pr5 <-  choose(n,r)*p^r*(1-p)^(n-r);
          r <- 6;  pr6 <-  choose(n,r)*p^r*(1-p)^(n-r);
          r <- 7;  pr7 <-  choose(n,r)*p^r*(1-p)^(n-r);
          r <- 8;  pr8 <-  choose(n,r)*p^r*(1-p)^(n-r);
          r <- 9;  pr9 <-  choose(n,r)*p^r*(1-p)^(n-r);

          r <- 10;  pr10 <-  choose(n,r)*p^r*(1-p)^(n-r);
          r <- 11;  pr11 <-  choose(n,r)*p^r*(1-p)^(n-r);
          r <- 12;  pr12 <-  choose(n,r)*p^r*(1-p)^(n-r);
          r <- 13;  pr13 <-  choose(n,r)*p^r*(1-p)^(n-r);
          r <- 14;  pr14 <-  choose(n,r)*p^r*(1-p)^(n-r);
          r <- 15;  pr15 <-  choose(n,r)*p^r*(1-p)^(n-r);
          r <- 16;  pr16 <-  choose(n,r)*p^r*(1-p)^(n-r);
          r <- 17;  pr17 <-  choose(n,r)*p^r*(1-p)^(n-r);
          r <- 18;  pr18 <-  choose(n,r)*p^r*(1-p)^(n-r);
          r <- 19;  pr19 <-  choose(n,r)*p^r*(1-p)^(n-r);

          r <- 20;  pr20 <-  choose(n,r)*p^r*(1-p)^(n-r);
          r <- 21;  pr21 <-  choose(n,r)*p^r*(1-p)^(n-r);
          r <- 22;  pr22 <-  choose(n,r)*p^r*(1-p)^(n-r);
          r <- 23;  pr23 <-  choose(n,r)*p^r*(1-p)^(n-r);
          r <- 24;  pr24 <-  choose(n,r)*p^r*(1-p)^(n-r);
          r <- 25;  pr25 <-  choose(n,r)*p^r*(1-p)^(n-r);
          r <- 26;  pr26 <-  choose(n,r)*p^r*(1-p)^(n-r);
          r <- 27;  pr27 <-  choose(n,r)*p^r*(1-p)^(n-r);
          r <- 28;  pr28 <-  choose(n,r)*p^r*(1-p)^(n-r);
          r <- 29;  pr29 <-  choose(n,r)*p^r*(1-p)^(n-r);
 
          r <- 30;  pr30 <-  choose(n,r)*p^r*(1-p)^(n-r);
          r <- 31;  pr31 <-  choose(n,r)*p^r*(1-p)^(n-r);
          r <- 32;  pr32 <-  choose(n,r)*p^r*(1-p)^(n-r);
          r <- 33;  pr33 <-  choose(n,r)*p^r*(1-p)^(n-r);
          r <- 34;  pr34 <-  choose(n,r)*p^r*(1-p)^(n-r);
          r <- 35;  pr35 <-  choose(n,r)*p^r*(1-p)^(n-r);
          r <- 36;  pr36 <-  choose(n,r)*p^r*(1-p)^(n-r);
          r <- 37;  pr37 <-  choose(n,r)*p^r*(1-p)^(n-r);
          r <- 38;  pr38 <-  choose(n,r)*p^r*(1-p)^(n-r);
          r <- 39;  pr39 <-  choose(n,r)*p^r*(1-p)^(n-r);

          r <- 40;  pr40 <-  choose(n,r)*p^r*(1-p)^(n-r);
          r <- 41;  pr41 <-  choose(n,r)*p^r*(1-p)^(n-r);
          r <- 42;  pr42 <-  choose(n,r)*p^r*(1-p)^(n-r);
          r <- 43;  pr43 <-  choose(n,r)*p^r*(1-p)^(n-r);
          r <- 44;  pr44 <-  choose(n,r)*p^r*(1-p)^(n-r);
          r <- 45;  pr45 <-  choose(n,r)*p^r*(1-p)^(n-r);
          r <- 46;  pr46 <-  choose(n,r)*p^r*(1-p)^(n-r);
          r <- 47;  pr47 <-  choose(n,r)*p^r*(1-p)^(n-r);
          r <- 48;  pr48 <-  choose(n,r)*p^r*(1-p)^(n-r);
          r <- 49;  pr49 <-  choose(n,r)*p^r*(1-p)^(n-r);

          r <- 50;  pr50 <-  choose(n,r)*p^r*(1-p)^(n-r);


# verify the probabilities sum to 1.0

pr0+pr1+pr2+pr3+pr4+pr5+pr6+pr7+pr8+pr9+
pr10+pr11+pr12+pr13+pr14+pr15+pr16+pr17+pr18+pr19+
pr20+pr21+pr22+pr23+pr24+pr25+pr26+pr27+pr28+pr29+
pr30+pr31+pr32+pr33+pr34+pr35+pr36+pr37+pr38+pr39+
pr40+pr41+pr42+pr43+pr44+pr45+pr46+pr47+pr48+pr49+pr50

# conduct test of hypothesis that p=0.5 at the .05 significance level
# critical region must be less than 0.05
# central region must be greater than 0.95

# critical region: r ∊ {0,50}
# central region: r ∊ [1,49]

critical.region <- pr0+pr50
critical.region
central.region <- pr1+pr2+pr3+pr4+pr5+pr6+pr7+pr8+pr9+
  pr10+pr11+pr12+pr13+pr14+pr15+pr16+pr17+pr18+pr19+
  pr20+pr21+pr22+pr23+pr24+pr25+pr26+pr27+pr28+pr29+
  pr30+pr31+pr32+pr33+pr34+pr35+pr36+pr37+pr38+pr39+
  pr40+pr41+pr42+pr43+pr44+pr45+pr46+pr47+pr48+pr49
central.region


# critical region: r ∊ [0,17] and [33,50]
# central region: r ∊ [18,32]

critical.region <- pr0+pr1+pr2+pr3+pr4+pr5+pr6+pr7+pr8+pr9+
                   pr10+pr11+pr12+pr13+pr14+pr15+pr16+pr17+
                   pr33+pr34+pr35+pr36+pr37+pr38+pr39+pr40+
                   pr41+pr42+pr43+pr44+pr45+pr46+pr47+pr48+pr49+pr50
critical.region
central.region <- pr18+pr19+pr20+pr21+pr22+pr23+pr24+pr25+pr26+pr27+pr28+pr29+
                  pr30+pr31+pr32
central.region

# critical region: r ∊ [0,18] and [32,50]
# central region: r ∊ [19,31]

critical.region <- pr0+pr1+pr2+pr3+pr4+pr5+pr6+pr7+pr8+pr9+
                   pr10+pr11+pr12+pr13+pr14+pr15+pr16+pr17+pr18+
                   pr32+pr33+pr34+pr35+pr36+pr37+pr38+pr39+pr40+
                   pr41+pr42+pr43+pr44+pr45+pr46+pr47+pr48+pr49+pr50
critical.region
central.region <- pr19+pr20+pr21+pr22+pr23+pr24+pr25+pr26+pr27+pr28+pr29+
                  pr30+pr31
central.region
```

Here is the output:

```rout
> p <- 0.5
> 
> n <- 50;  r <- 0;  pr0 <-  choose(n,r)*p^r*(1-p)^(n-r);
>           r <- 1;  pr1 <-  choose(n,r)*p^r*(1-p)^(n-r);
>           r <- 2;  pr2 <-  choose(n,r)*p^r*(1-p)^(n-r);
>           r <- 3;  pr3 <-  choose(n,r)*p^r*(1-p)^(n-r);
>           r <- 4;  pr4 <-  choose(n,r)*p^r*(1-p)^(n-r);
>           r <- 5;  pr5 <-  choose(n,r)*p^r*(1-p)^(n-r);
>           r <- 6;  pr6 <-  choose(n,r)*p^r*(1-p)^(n-r);
>           r <- 7;  pr7 <-  choose(n,r)*p^r*(1-p)^(n-r);
>           r <- 8;  pr8 <-  choose(n,r)*p^r*(1-p)^(n-r);
>           r <- 9;  pr9 <-  choose(n,r)*p^r*(1-p)^(n-r);
> 
>           r <- 10;  pr10 <-  choose(n,r)*p^r*(1-p)^(n-r);
>           r <- 11;  pr11 <-  choose(n,r)*p^r*(1-p)^(n-r);
>           r <- 12;  pr12 <-  choose(n,r)*p^r*(1-p)^(n-r);
>           r <- 13;  pr13 <-  choose(n,r)*p^r*(1-p)^(n-r);
>           r <- 14;  pr14 <-  choose(n,r)*p^r*(1-p)^(n-r);
>           r <- 15;  pr15 <-  choose(n,r)*p^r*(1-p)^(n-r);
>           r <- 16;  pr16 <-  choose(n,r)*p^r*(1-p)^(n-r);
>           r <- 17;  pr17 <-  choose(n,r)*p^r*(1-p)^(n-r);
>           r <- 18;  pr18 <-  choose(n,r)*p^r*(1-p)^(n-r);
>           r <- 19;  pr19 <-  choose(n,r)*p^r*(1-p)^(n-r);
> 
>           r <- 20;  pr20 <-  choose(n,r)*p^r*(1-p)^(n-r);
>           r <- 21;  pr21 <-  choose(n,r)*p^r*(1-p)^(n-r);
>           r <- 22;  pr22 <-  choose(n,r)*p^r*(1-p)^(n-r);
>           r <- 23;  pr23 <-  choose(n,r)*p^r*(1-p)^(n-r);
>           r <- 24;  pr24 <-  choose(n,r)*p^r*(1-p)^(n-r);
>           r <- 25;  pr25 <-  choose(n,r)*p^r*(1-p)^(n-r);
>           r <- 26;  pr26 <-  choose(n,r)*p^r*(1-p)^(n-r);
>           r <- 27;  pr27 <-  choose(n,r)*p^r*(1-p)^(n-r);
>           r <- 28;  pr28 <-  choose(n,r)*p^r*(1-p)^(n-r);
>           r <- 29;  pr29 <-  choose(n,r)*p^r*(1-p)^(n-r);
>  
>           r <- 30;  pr30 <-  choose(n,r)*p^r*(1-p)^(n-r);
>           r <- 31;  pr31 <-  choose(n,r)*p^r*(1-p)^(n-r);
>           r <- 32;  pr32 <-  choose(n,r)*p^r*(1-p)^(n-r);
>           r <- 33;  pr33 <-  choose(n,r)*p^r*(1-p)^(n-r);
>           r <- 34;  pr34 <-  choose(n,r)*p^r*(1-p)^(n-r);
>           r <- 35;  pr35 <-  choose(n,r)*p^r*(1-p)^(n-r);
>           r <- 36;  pr36 <-  choose(n,r)*p^r*(1-p)^(n-r);
>           r <- 37;  pr37 <-  choose(n,r)*p^r*(1-p)^(n-r);
>           r <- 38;  pr38 <-  choose(n,r)*p^r*(1-p)^(n-r);
>           r <- 39;  pr39 <-  choose(n,r)*p^r*(1-p)^(n-r);
> 
>           r <- 40;  pr40 <-  choose(n,r)*p^r*(1-p)^(n-r);
>           r <- 41;  pr41 <-  choose(n,r)*p^r*(1-p)^(n-r);
>           r <- 42;  pr42 <-  choose(n,r)*p^r*(1-p)^(n-r);
>           r <- 43;  pr43 <-  choose(n,r)*p^r*(1-p)^(n-r);
>           r <- 44;  pr44 <-  choose(n,r)*p^r*(1-p)^(n-r);
>           r <- 45;  pr45 <-  choose(n,r)*p^r*(1-p)^(n-r);
>           r <- 46;  pr46 <-  choose(n,r)*p^r*(1-p)^(n-r);
>           r <- 47;  pr47 <-  choose(n,r)*p^r*(1-p)^(n-r);
>           r <- 48;  pr48 <-  choose(n,r)*p^r*(1-p)^(n-r);
>           r <- 49;  pr49 <-  choose(n,r)*p^r*(1-p)^(n-r);
> 
>           r <- 50;  pr50 <-  choose(n,r)*p^r*(1-p)^(n-r);
> 
> 
> # verify the probabilities sum to 1.0
> 
> pr0+pr1+pr2+pr3+pr4+pr5+pr6+pr7+pr8+pr9+
+ pr10+pr11+pr12+pr13+pr14+pr15+pr16+pr17+pr18+pr19+
+ pr20+pr21+pr22+pr23+pr24+pr25+pr26+pr27+pr28+pr29+
+ pr30+pr31+pr32+pr33+pr34+pr35+pr36+pr37+pr38+pr39+
+ pr40+pr41+pr42+pr43+pr44+pr45+pr46+pr47+pr48+pr49+pr50
[1] 1
> 
> # conduct test of hypothesis that p=0.5 at the .05 significance level
> # critical region must be less than 0.05
> # central region must be greater than 0.95
> 
> # critical region: r ∊ {0,50}
> # central region: r ∊ [1,49]
> 
> critical.region <- pr0+pr50
> critical.region
[1] 1.776357e-15
> central.region <- pr1+pr2+pr3+pr4+pr5+pr6+pr7+pr8+pr9+
+   pr10+pr11+pr12+pr13+pr14+pr15+pr16+pr17+pr18+pr19+
+   pr20+pr21+pr22+pr23+pr24+pr25+pr26+pr27+pr28+pr29+
+   pr30+pr31+pr32+pr33+pr34+pr35+pr36+pr37+pr38+pr39+
+   pr40+pr41+pr42+pr43+pr44+pr45+pr46+pr47+pr48+pr49
> central.region
[1] 1
> 
> 
> # critical region: r ∊ [0,17] and [33,50]
> # central region: r ∊ [18,32]
> 
> critical.region <- pr0+pr1+pr2+pr3+pr4+pr5+pr6+pr7+pr8+pr9+
+                    pr10+pr11+pr12+pr13+pr14+pr15+pr16+pr17+
+                    pr33+pr34+pr35+pr36+pr37+pr38+pr39+pr40+
+                    pr41+pr42+pr43+pr44+pr45+pr46+pr47+pr48+pr49+pr50
> critical.region
[1] 0.03283914
> central.region <- pr18+pr19+pr20+pr21+pr22+pr23+pr24+pr25+pr26+pr27+pr28+pr29+
+                   pr30+pr31+pr32
> central.region
[1] 0.9671609
> 
> # critical region: r ∊ [0,18] and [32,50]
> # central region: r ∊ [19,31]
> 
> critical.region <- pr0+pr1+pr2+pr3+pr4+pr5+pr6+pr7+pr8+pr9+
+                    pr10+pr11+pr12+pr13+pr14+pr15+pr16+pr17+pr18+
+                    pr32+pr33+pr34+pr35+pr36+pr37+pr38+pr39+pr40+
+                    pr41+pr42+pr43+pr44+pr45+pr46+pr47+pr48+pr49+pr50
> critical.region
[1] 0.06490865
> central.region <- pr19+pr20+pr21+pr22+pr23+pr24+pr25+pr26+pr27+pr28+pr29+
+                   pr30+pr31
> central.region
[1] 0.9350914
> 
```

Based on our assessment of the probability distribution of the sample space, 
r ∊ [0,50], combined with a 0.05 significance level for the test, we conclude 
that the critical region is *r* ∊ [0,17] and [33,50] (for a two-tailed test). 

Considering the homicide data from the CDC (stratifed by state 
[link](https://www.cdc.gov/nchs/pressroom/sosmap/homicide_mortality/homicide.htm)),
there were 17 states that experienced an increase in the number of homicides
from 2017 to 2018. Since 17 falls within the critical region, we reject the
hypothesis that p = 0.5 (where p represents the probability that a state experiences
an increase in the homicide rate from 2017 to 2018) at the 0.05 significance level.
We conclude that there were fewer states experiencing an increase than we would
have expected if the "equal likelihood" hypothesis was true.


26. Normal distribution

Many random variables are either normally or approximately normally distributed. As an example, let's explore the distribution of index crime rates in 143 North and South Carolina counties during the year 2005. We begin by entering some data points for these counties:

```R
crate <- c(4668,2538,5511,1745,1235,3330,2954,
           4105,4661,4150,2988,3421,3405, 730,
           3179,2421,5243,2413,2846,2709,1487,
           4360,5988,4318,6847,2875,5405,3508,
           3508,3400,6607,5369,5765,2314,5488,
           1356,3878,2415,5819,5346,4190,3120,
           3011,4918,4096, 514,4016,3563,3328,
           3437,4824,6610,1105,2166,1258,5162,
           2842,7733,3348,3000,5507,6445,3633,
           2828,3913, 673,4663,2492,2660,3212,
           5427,2124,3828,5565,7106,4438,3818,
           3568,3823,4991,2735,2924,3686,4172,
           1986,1869,3495,6977,3359,3168,3094,
           2821,4788,2864,4269,2772, 780,2904,
           3582,3182,5558,3906,4185,4515,3816,
           2841,6293,5704,5343,3578,4587,4914,
           7507,6323,3763,2224,4317,6861,3862,
           5026,6138,3324,7496,6822,3614,4666,
           4667,4223,3672,2317,6218,6289,3448,
           3671,6206,3872,5967,1804,5038,5585,
           4288,4127,4504,NA,NA,NA)
```

* Now, here is some information about this distribution:

```Rout
> length(crate)
[1] 146
> mean(crate,na.rm=T)
[1] 3998.364
> median(crate,na.rm=T)
[1] 3823
> sd(crate,na.rm=T)
[1] 1558.467
> 
```

* Let's create a histogram and a boxplot to display the distribution:

```R
par(mfrow=c(1,2))
hist(crate)
boxplot(crate)
```

and here is the resulting plotspace:

<p align="center">
<img src="/gfiles/hist-boxplot.png" width="600px">
</p>

* Next, let's consider what the distribution of a normally distributed variable with this mean and standard deviation would look like. To approximate a theoretical normal distribution we can draw random numbers using the normal probability density function:

<p align="center">
<img src="/gfiles/normal-density.png" width="250px">
</p>

* We can calculate this theoretical distribution:

```R
mu <- 3998.364
sigma <- 1558.467
x <- seq(from=0,to=8000,by=1)
pdf.pt1 <- 1/(sigma*sqrt(2*pi))
pdf.pt2 <- ((x-mu)/sigma)^2
pdf.pt3 <- exp(-1/2*pdf.pt2)
pdf <- pdf.pt1*pdf.pt3
plot(x=x,y=pdf,type="l",lty=1,lwd=2,main="Theoretical Normal Distribution") 
```

* Here is a plot:

<p align="center">
<img src="/gfiles/normal-pdf.png" width="650px">
</p>

* We can also draw random numbers from this distribution:

```r
x <- rnorm(n=1000000,mean=3998.364,sd=1558.467)
mean(x)
sd(x)
boxplot(crate,x,
  main="2005 NC/SC County Crime Rates & Theoretical Normal Distribution",
  ylab="2005 Index Crime Rate per 100k Population",
  names=c("Empirical Distribution","Theoretical Distribution"))
```

* Here is the output:

```Rout
> x <- rnorm(n=1000000,mean=3998.364,sd=1558.467)
> mean(x)
[1] 3997.238
> sd(x)
[1] 1556.873
>
```

<p align="center">
<img src="/gfiles/ncsc-boxplot.png" width="650px">
</p>

* Let's do some percentile comparisons between the two distributions:

```R
empirical <- quantile(crate,seq(from=0.01,to=0.99,by=0.01),na.rm=T)
theoretical <- quantile(x,seq(from=0.01,to=0.99,by=0.01))
plot(empirical)
lines(theoretical,col="red",lwd=2)
```
* And, here is the resulting plot:

<p align="center">
<img src="/gfiles/normal-probability-plot.png" width="650px">
</p>

27. Law of total probability

##### Diane Saphire (1984)

* National Crime Survey (NCS)
* p(HH not victimized in a year's time) = θnv (1975)
* S = R + NR
* p(HH participates in NCS) = R/S = p
* θnv = p x θnv|R + (1-p) x θnv|NR (Law of total probability)
* θnv|NR ∊ [0,1]
* Point-identified estimate assuming MAR = 0.732
* Interval estimate = [0.523,0.770]

##### Charles Manski (1995,2012)

* Conclusions = data + assumptions (identification)
* More credible --> answer is vague (weaker assumptions)
* Less credible --> answer is specific (stronger assumptions)
* Law of decreasing credibility

```rout
##### Empirical example 

* National Longitudinal Survey of Youth (1997)
* p(person is arrested at least once by age 18)= θa
* # of persons not arrested by age 18 = 5,369
* # of peresons arrested by age 18 = 1,164
* # of missing cases = 802
* Total # of people = 7,335
* S = R + NR
* p(person participates in NLSY97) = R/S
* p(person participates in NLSY97) = (5369+1164)/7335 = 0.8906612
* 1-p(person participates in NLSY97) = 1 - (5369+1164)/7335 = 0.1093388
* θa|R = 1164/(5369+1164) = 0.1781724
* θa = p x θa|R + (1-p) x θa|NR 
* θa|NR ∊ [0,1]
* LB[θa] = 0.891*0.178+0.109*0 = 0.159
* MAR[θa] = 0.891*0.178+0.109*0.178 = 0.178
* UB[θa] = 0.891*0.178+0.109*1 = 0.268
* Point-identified estimate assuming MAR = 0.178
* Partially-identified estimate = [0.159,0.268]
```
28. Optimization

Blumstein and Benedict (1999) [studied](https://amstat.tandfonline.com/doi/pdf/10.1080/09332480.1999.10542151) 509 NFL players and determined that 109 of them (21.4%) had been arrested. While it is trivial to calculate the arrest rate for the sample, we will conduct a "grid search" to verify that 21.4% is the maximum likelihood estimate of the arrest rate; then we will graph the likelihood function.

* Parameter of interest: pi ∊ [0,1]
* Number of cases (n): 509
* Number of people arrested (r): 109
* Likelihood function:

<p align="center">
<img src="/gfiles/leq1.png" width="400px">
</p>

Now, here is the code to solve this problem:

```Rout
n <- 509
r <- 109
r/n

pi <- seq(from=0,to=1,by=0.001) 
ncr <- choose(n,r)
likelihood <- ncr*(pi^r)*((1-pi)^(n-r))

# concatenate pi and likelihood into the
# same data frame, then select the pair
# that maximizes the likelihood function

like <- data.frame(pi,likelihood)
neighborhood <- subset(like,abs(likelihood-max(like$likelihood))<0.01)
neighborhood
```

and here is the output window:

```Rout
> n <- 509
> r <- 109
> r/n
[1] 0.2141454
> 
> pi <- seq(from=0,to=1,by=0.001) 
> ncr <- choose(n,r)
> likelihood <- ncr*(pi^r)*((1-pi)^(n-r))
> 
> # concatenate pi and likelihood into the
> # same data frame, then select the pair
> # that maximizes the likelihood function
> 
> like <- data.frame(pi,likelihood)
> neighborhood <- subset(like,abs(likelihood-max(like$likelihood))<0.01)
> neighborhood
       pi likelihood
203 0.202 0.03423706
204 0.203 0.03551709
205 0.204 0.03672451
206 0.205 0.03784975
207 0.206 0.03888380
208 0.207 0.03981835
209 0.208 0.04064591
210 0.209 0.04135988
211 0.210 0.04195467
212 0.211 0.04242576
213 0.212 0.04276973
214 0.213 0.04298436
215 0.214 0.04306857
216 0.215 0.04302249
217 0.216 0.04284742
218 0.217 0.04254578
219 0.218 0.04212110
220 0.219 0.04157792
221 0.220 0.04092173
222 0.221 0.04015888
223 0.222 0.03929649
224 0.223 0.03834231
225 0.224 0.03730467
226 0.225 0.03619230
227 0.226 0.03501425
228 0.227 0.03377977
> 
```

Notice that the likelihood function is greatest (maximized) when pi = 0.214. We now turn to the task of graphing the likelihood function:

```Rout
# Likelihood plot for entire sample of 509 cases

plot(x=pi,y=likelihood,
  type="l",lty=1,lwd=3,col="darkred",
  main="Arrest Prevalence Likelihood (N=509, r=109)", 
  xlab=expression(pi), ylab="Likelihood Function",
  ylim=c(0,0.05))

# annotations to the plotspace

abline(h=max(like$likelihood),lty=2,lwd=1) 
abline(v=like$pi[like$likelihood==max(like$likelihood)],
  lty=2,lwd=1) 
text("MLE = 0.214",x=0.27,y=0.035,adj=c(0,0.5))
```

and the output is:

<p align="center">
<img src="/gfiles/lik.png" width="800px">
</p>

Note: why do we maximize the likelihood function? The maximum likelihood estimate is the estimate that maximizes the probability of the data looking the way they do (i.e., likelihood is proportional to p(data look the way they do | model)). This is different, by the way, from another number: p(model is correct | data). The discussion of this number arises in Bayesian inference.

```rout
Problems for Monday 8/23/21

1. Set up a significance test of the acyclicality hypothesis using the
data from Bushway, Cook, and Philips (2012).

Solution: 

p <- 0.5

n <- 13; r <- 0;  pr0 <-  choose(n,r)*p^r*(1-p)^(n-r);
         r <- 1;  pr1 <-  choose(n,r)*p^r*(1-p)^(n-r);
         r <- 2;  pr2 <-  choose(n,r)*p^r*(1-p)^(n-r);
         r <- 3;  pr3 <-  choose(n,r)*p^r*(1-p)^(n-r);
         r <- 4;  pr4 <-  choose(n,r)*p^r*(1-p)^(n-r);
         r <- 5;  pr5 <-  choose(n,r)*p^r*(1-p)^(n-r);
         r <- 6;  pr6 <-  choose(n,r)*p^r*(1-p)^(n-r);
         r <- 7;  pr7 <-  choose(n,r)*p^r*(1-p)^(n-r);
         r <- 8;  pr8 <-  choose(n,r)*p^r*(1-p)^(n-r);
         r <- 9;  pr9 <-  choose(n,r)*p^r*(1-p)^(n-r);
         r <- 10; pr10 <-  choose(n,r)*p^r*(1-p)^(n-r);
         r <- 11; pr11 <-  choose(n,r)*p^r*(1-p)^(n-r);
         r <- 12; pr12 <-  choose(n,r)*p^r*(1-p)^(n-r);
         r <- 13; pr13 <-  choose(n,r)*p^r*(1-p)^(n-r);

pr0
pr1
pr2
pr3
pr4
pr5
pr6
pr7
pr8
pr9
pr10
pr11
pr12
pr13

# the critical region should contain no more than 5% of the
# probability distribution for the sample space.

pr0+pr13
pr1+pr2+pr3+pr4+pr5+pr6+pr7+pr8+pr9+pr10+pr11+pr12

pr0+pr1+pr12+pr13
pr2+pr3+pr4+pr5+pr6+pr7+pr8+pr9+pr10+pr11

pr0+pr1+pr2+pr11+pr12+pr13
pr3+pr4+pr5+pr6+pr7+pr8+pr9+pr10

pr0+pr1+pr2+pr3+pr10+pr11+pr12+pr13
pr4+pr5+pr6+pr7+pr8+pr9

The results I obtained are:

> pr0
[1] 0.0001220703
> pr1
[1] 0.001586914
> pr2
[1] 0.009521484
> pr3
[1] 0.03491211
> pr4
[1] 0.08728027
> pr5
[1] 0.1571045
> pr6
[1] 0.2094727
> pr7
[1] 0.2094727
> pr8
[1] 0.1571045
> pr9
[1] 0.08728027
> pr10
[1] 0.03491211
> pr11
[1] 0.009521484
> pr12
[1] 0.001586914
> pr13
[1] 0.0001220703
> 
> # the critical region should contain no more than 5% of the
> # probability distribution for the sample space.
> 
> pr0+pr13
[1] 0.0002441406
> pr0+pr1+pr12+pr13
[1] 0.003417969
> pr0+pr1+pr2+pr11+pr12+pr13
[1] 0.02246094
> pr0+pr1+pr2+pr3+pr10+pr11+pr12+pr13
[1] 0.09228516

To satisfy my criterion that the critical region should contain
no more than 5% of the probability distribution of the sample
space, I define the events r={0,1,2,11,12,13} as the critical
region. Any time r falls in this region, I reject the acyclicality
hypothesis.

Murder: fail to reject acyclicality hypothesis (r = 6)
Robbery: fail to reject the acyclicality hypothesis (r = 10)
Burglary: reject the acyclicality hypothesis (r = 11)
Auto Theft: fail to reject the acyclicality hypothesis (r = 4)

2. Consider the following data on NC and SC counties from 2006:

crate2006 <- c(4807,2499,4922,1882,1271,3351,2593,5090,
  4654,3716,2514,3604,3468, 870,3338,2555,4642,2666,2826,
  1610,3946,5688,4176,7380,2458,5010,3546,3546,3028,6640,
  5857,6072,2152,5301,3966,2950,5755,5270,3929,3283,2922,
  3537,3998,3682,3584,2811,4740,5831,3793,2270,1314,3466,
  2779,7664,4145,3045,6072,6158,2819,4067,4103,4337,2740,
  2567,3531,5806,2020,3787,6534,6572,4717,3178,3482,4203,
  2997,2891,3663,5337,1978,1618,3692,6996,3326,3294,2874,
  4712,2716,4797,3080, 804,3391,3986,3794,5176,3956,4480,
  4489,4004,2666,6166,5745,5525,3722,4826,5381,7581,5910,
  3968,2309,4561,6669,4244,4900,6201,4239,7222,6482,3285,
  4298,4570,3898,3502,1766,5944,5938,3244,3039,5925,3352,
  5763,1680,5392,5702,4340,3742,4237,rep(NA,10))
  
Assess the normality of this distribution.
  
Solution:

> length(crate2006)
[1] 146
> mean(crate2006,na.rm=T)
[1] 4081.544
> median(crate2006,na.rm=T)
[1] 3937.5
> sd(crate2006,na.rm=T)
[1] 1479.672
> 

mu <- 4081.544
sigma <- 1479.672
x <- seq(from=0,to=8000,by=1)
pdf.pt1 <- 1/(sigma*sqrt(2*pi))
pdf.pt2 <- ((x-mu)/sigma)^2
pdf.pt3 <- exp(-1/2*pdf.pt2)
pdf <- pdf.pt1*pdf.pt3
plot(x=x,y=pdf,type="l",lty=1,lwd=2,main="Theoretical Normal Distribution") 

x <- rnorm(n=1000000,mean=4081.544,sd=1479.672)
mean(x)
sd(x)
boxplot(crate2006,x,
  main="2006 NC/SC County Crime Rates & Theoretical Normal Distribution",
  ylab="2006 Index Crime Rate per 100k Population",
  names=c("Empirical Distribution","Theoretical Distribution"))

empirical <- quantile(crate2006,seq(from=0.01,to=0.99,by=0.01),na.rm=T)
theoretical <- quantile(x,seq(from=0.01,to=0.99,by=0.01))
plot(empirical)
lines(theoretical,col="red",lwd=2)
```

<p align="center">
<img src="/gfiles/2006-plot.png" width="600px">
</p>

<p align="center">
<img src="/gfiles/2006-boxplota.png" width="600px">
</p>

<p align="center">
<img src="/gfiles/2006-normala.png" width="600px">
</p>

```rout
3. The National Longitudinal Survey of Youth contains a
series of questions about arrest experiences. These questions
allow us to construct a life history of self-reported arrest
experiences from ages 8 to 23 years old. According to this
data, there were N = 1,858 people who said they had been 
arrested at least one time by age 23. Another 4,299 people
said they had not been arrested by age 23. For a third group
of 1,178 persons, we are not able to discern whether they
had been arrested by age 23. Using the NLSY data, derive
bounds for the probability that someone has been arrested at
least once by age 23.

Solution:

* National Longitudinal Survey of Youth (1997)
* p(person is arrested at least once by age 23)= θa
* # of persons not arrested by age 23 = 4,299
* # of persons arrested by age 23 = 1,858
* # of missing cases = 1,178
* Total # of people = 7,335
* S = R + NR
* p(person participates in NLSY97) = R/S
* p(person participates in NLSY97) = (4299+1858)/7335 = 0.839
* 1-p(person participates in NLSY97) = 1- (4299+1858)/7335 = 0.161
* θa|R = 1858/(4299+1858) = 0.302
* θa = p x θa|R + (1-p) x θa|NR 
* θa|NR ∊ [0,1]
* LB[θa] = 0.839*0.302+0.161*0 = 0.253
* MAR[θa] = 0.839*0.302+0.161*0.178 = 0.302
* UB[θa] = 0.839*0.302+0.161*1 = 0.414
* Point-identified estimate assuming MAR = 0.302
* Partially-identified estimate = [0.253,0.414]

4. Find the maximum likelihood estimate for the probability
of conviction in the NFL sample studied by Blumstein and
Benedict (1999). The number of players studied was 509 and
the number who were convicted was 43.

n <- 509
r <- 43
r/n

pi <- seq(from=0,to=1,by=0.001) 
ncr <- choose(n,r)
likelihood <- ncr*(pi^r)*((1-pi)^(n-r))

# concatenate pi and likelihood into the
# same data frame, then select the pair
# that maximizes the likelihood function

like <- data.frame(pi,likelihood)
neighborhood <- subset(like,abs(likelihood-max(like$likelihood))<0.01)
neighborhood

> n <- 509
> r <- 43
> r/n
[1] 0.08447937
> 
> pi <- seq(from=0,to=1,by=0.001) 
> ncr <- choose(n,r)
> likelihood <- ncr*(pi^r)*((1-pi)^(n-r))
> 
> # concatenate pi and likelihood into the
> # same data frame, then select the pair
> # that maximizes the likelihood function
> 
> like <- data.frame(pi,likelihood)
> neighborhood <- subset(like,abs(likelihood-max(like$likelihood))<0.01)
> neighborhood
      pi likelihood
79 0.078 0.05489606
80 0.079 0.05725542
81 0.080 0.05927356
82 0.081 0.06091835
83 0.082 0.06216545
84 0.083 0.06299882
85 0.084 0.06341092
86 0.085 0.06340269
87 0.086 0.06298319
88 0.087 0.06216905
89 0.088 0.06098367
90 0.089 0.05945631
91 0.090 0.05762099
92 0.091 0.05551540
> 
> 43/509
[1] 0.08447937
> 
```


29. Estimates and estimators

An estimator is a formula used to calculate an estimate. We usually
differentiate between population parameters (fixed but, in general, unknown)
and sample statistics or estimates (which vary from sample to sample and 
can be calculated).

* Point Estimation of a Proportion

Let's say we have a population comprised of 1 million persons.
What all of these people have in common is that they were all released
from prison and followed for 5 years to see how many of them were
rearrested for a new crime within that follow-up period. Let's further
suppose that 752,748 of these persons were rearrested during that time
while the remaining 247,252 were not rearrested. Thus, 75.3% of the
people in this population were rearrested within the 5-year follow-up
period. Here is the R code to define this population:

```R
pop.recidivism.data <- c(rep("no",247252),rep("yes",752748))
pop.rt <- table(pop.recidivism.data)
pop.rt
pop.recidivism.rate <- pop.rt[2]/(pop.rt[1]+pop.rt[2])
pop.recidivism.rate
```

and here is the output:

```rout
> pop.recidivism.data <- c(rep("no",247252),rep("yes",752748))
> pop.rt <- table(pop.recidivism.data)
> pop.rt
pop.recidivism.data
    no    yes 
247252 752748 
> pop.recidivism.rate <- pop.rt[2]/(pop.rt[1]+pop.rt[2])
> pop.recidivism.rate
     yes 
0.752748 
> 
```

30. Random sampling

Next, let's draw a random sample (with replacement) from this
populaton:

```r
samp.recidivism.data <- sample(pop.recidivism.data,size=1000,replace=T)
samp.recidivism.table <- table(samp.recidivism.data)
samp.recidivism.table
samp.recidivism.rate <- samp.recidivism.table[2]/(samp.recidivism.table[1]+samp.recidivism.table[2])
samp.recidivism.rate 
est.standard.error <- sqrt(samp.recidivism.rate*(1-samp.recidivism.rate)/1000)
est.standard.error
```

And here is the output I obtained based on my single sample:

```r
> samp.recidivism.data <- sample(pop.recidivism.data,size=1000,replace=T)
> samp.recidivism.table <- table(samp.recidivism.data)
> samp.recidivism.table
samp.recidivism.data
 no yes 
244 756 
> samp.recidivism.rate <- samp.recidivism.table[2]/(samp.recidivism.table[1]+samp.recidivism.table[2])
> samp.recidivism.rate 
  yes 
0.756 
> 
> est.standard.error <- sqrt(samp.recidivism.rate*(1-samp.recidivism.rate)/1000)
> est.standard.error
[1] 0.01364252
>
```
Your results will not be exactly the same as mine since 
we have not set up a random number seed. In this sample of 1,000 
cases, the point estimate of the population recidivism rate is 0.756 and the standard
error is approximately 0.014.

* Sampling distribution of a proportion

We now consider what would happen if we were to draw repeated samples
(with replacement) from this same population, calculating the recidivism
rate in each sample. The reason this matters is that it helps us to 
build intuition about how much our point estimate is typically going to
vary from sample to sample -- given a fixed population parameter and 
sample size. This is what we mean by the term "sampling error." Let's
look at a sampling distribution for the recidivism rate if we repeatedly
(say, 10,000 times) draw samples of size N = 1,000 from our population 
of 1 million prison releasees.

```r
prop.rs <- vector()
nsamples <- 10000
sampsize <- 1000

for(i in 1:nsamples){
  recidivism.rs <- sample(pop.recidivism.data,size=sampsize,replace=T)
  recidivism.rs.table <- table(recidivism.rs)
  prop.rs[i] <- recidivism.rs.table[2]/(recidivism.rs.table[1]+recidivism.rs.table[2])
  }

mean(prop.rs)
sd(prop.rs)

par(mfrow=c(1,3))

hist(prop.rs,prob=T,xlab="Recidivism Rates")
lines(density(prop.rs),lty=1,lwd=2)

boxplot(prop.rs,ylab="Recidivism Rates")

qqnorm(prop.rs)
```

Here is the R output:

```rout
> prop.rs <- vector()
> nsamples <- 10000
> sampsize <- 1000
> 
> for(i in 1:nsamples){
+   recidivism.rs <- sample(pop.recidivism.data,size=sampsize,replace=T)
+   recidivism.rs.table <- table(recidivism.rs)
+   prop.rs[i] <- recidivism.rs.table[2]/(recidivism.rs.table[1]+recidivism.rs.table[2])
+   }
> 
> mean(prop.rs)
[1] 0.7527641
> sd(prop.rs)
[1] 0.01360209
> 
> par(mfrow=c(1,3))
> 
> hist(prop.rs,prob=T,xlab="Recidivism Rates")
> lines(density(prop.rs),lty=1,lwd=2)
> 
> boxplot(prop.rs,ylab="Recidivism Rates")
> 
> qqnorm(prop.rs)
> 
```

Note that the mean of this approximation to the sampling distribution
is 0.753 and the standard deviation is 0.014. The plots reveal a bell-shaped
distribution of proportion estimates and a normal Q-Q plot tells us that
the distribution is approximately normal. 

<p align="center">
<img src="/gfiles/fig1c.png" width="600px">
</p>

* The 95% confidence interval of a proportion

The first step in calculating an estimate of the confidence interval
is to decide the confidence level. In this case, we will calculate
95% confidence intervals. In order to do this, we first identify the
0.025 and 0.975 percentiles of the standard normal distribution:

```r
qnorm(p=0.025,mean=0,sd=1)
qnorm(p=0.975,mean=0,sd=1)
```

and here is the output:

```rout
> qnorm(p=0.025,mean=0,sd=1)
[1] -1.959964
> qnorm(p=0.975,mean=0,sd=1)
[1] 1.959964
>
```rout

Next, we calculate 95% confidence intervals within each of
our samples:

```r
prop.rs <- vector()
se.prop.rs <- vector()
lcl.prop.rs <- vector()
ucl.prop.rs <- vector()

lcl.multiplier <- qnorm(p=0.025,mean=0,sd=1)
lcl.multiplier

ucl.multiplier <- qnorm(p=0.975,mean=0,sd=1)
ucl.multiplier 

nsamples <- 10000
sampsize <- 1000

for(i in 1:nsamples){
  recidivism.rs.data <- sample(pop.recidivism.data,size=sampsize,replace=T)
  recidivism.rs.table <- table(recidivism.rs.data)
  prop.rs[i] <- recidivism.rs.table[2]/(recidivism.rs.table[1]+recidivism.rs.table[2])
  se.prop.rs[i] <- sqrt(prop.rs[i]*(1-prop.rs[i])/sampsize)
  lcl.prop.rs[i] <- prop.rs[i]+lcl.multiplier*se.prop.rs[i]
  ucl.prop.rs[i] <- prop.rs[i]+ucl.multiplier*se.prop.rs[i]
  }

mean(prop.rs)
sd(prop.rs)
mean(se.prop.rs)
median(se.prop.rs)
pop.p.trapped <- ifelse(pop.recidivism.rate>lcl.prop.rs & pop.recidivism.rate<ucl.prop.rs,"inside","outside")
table(pop.p.trapped)
```

and here is the output:

```rout
> nsamples <- 10000
> sampsize <- 1000
> 
> for(i in 1:nsamples){
+   recidivism.rs.data <- sample(pop.recidivism.data,size=sampsize,replace=T)
+   recidivism.rs.table <- table(recidivism.rs.data)
+   prop.rs[i] <- recidivism.rs.table[2]/(recidivism.rs.table[1]+recidivism.rs.table[2])
+   se.prop.rs[i] <- sqrt(prop.rs[i]*(1-prop.rs[i])/sampsize)
+   lcl.prop.rs[i] <- prop.rs[i]+lcl.multiplier*se.prop.rs[i]
+   ucl.prop.rs[i] <- prop.rs[i]+ucl.multiplier*se.prop.rs[i]
+   }
> 
> mean(prop.rs)
[1] 0.7528406
> sd(prop.rs)
[1] 0.01361738
> mean(se.prop.rs)
[1] 0.01363167
> median(se.prop.rs)
[1] 0.01363785
> pop.p.trapped <- ifelse(pop.recidivism.rate>lcl.prop.rs & pop.recidivism.rate<ucl.prop.rs,"inside","outside")
> table(pop.p.trapped)
pop.p.trapped
 inside outside 
   9477     523 
> 
```

* Thus, the 95% confidence intervals trap the true population
parameter value in approximately 95% of the individual samples. 
This means that in any given sample, a 95% confidence interval 
has a high (95%) probability of including the true population parameter 
value.

31. Sample size and sampling variability

This case illustrates the greater sampling variability we get from drawing samples of size 50 in comparison to drawing samples of size 500. To create this simulation, we imagine a large population of prison releasees who have a true 3-year rearrest recidivism rate of 67.5%. The question is this: how close do we typically get to this estimate when we draw samples of size 50 and 500 from this population?

```Rout
set.seed(1203842)

# set parameters for simulation

pi <- 0.675
ys <- rbinom(n=10000000,size=1,p=pi) 
id <- seq(from=1,to=1000000,by=1)
df <- data.frame(id,ys)

# population mean

mean(ys)
```

and here is our output window:

```Rout
> set.seed(1203842)
> 
> # set parameters for simulation
> 
> pi <- 0.675
> ys <- rbinom(n=10000000,size=1,p=pi) 
> id <- seq(from=1,to=1000000,by=1)
> df <- data.frame(id,ys)
> 
> # population mean
> 
> mean(ys)
[1] 0.6749167
> 
```

Now, let's simulate drawing 10 samples of size 50 and 500 from this population:

```Rout
# set up repeated sampling loops

pvec <- vector() 
qvec <- vector()

for(i in 1:10) {
  s <- df[sample(1:nrow(df),50,replace=T),] 
  y <- s$ys
  pvec[i] <- mean(y)
  }
  
pvec

for(i in 1:10) {
  s <- df[sample(1:nrow(df),500,replace=T),] 
  y <- s$ys
  qvec[i] <- mean(y) 
  }
  
 qvec
  ```

Here is our output:

```Rout
> # set up repeated sampling loops
> 
> pvec <- vector() 
> qvec <- vector()
> 
> for(i in 1:10) {
+   s <- df[sample(1:nrow(df),50,replace=T),] 
+   y <- s$ys
+   pvec[i] <- mean(y)
+   }
>   
> pvec
 [1] 0.58 0.78 0.70 0.66 0.70 0.66 0.70 0.70 0.60 0.68
> 
> for(i in 1:10) {
+   s <- df[sample(1:nrow(df),500,replace=T),] 
+   y <- s$ys
+   qvec[i] <- mean(y) 
+   }
>   
>  qvec
 [1] 0.674 0.688 0.668 0.684 0.686 0.664 0.688 0.650 0.674 0.680
>
> mean(abs(pvec-pi))
[1] 0.041
> mean(abs(qvec-pi))
[1] 0.0096
> 
```

Here is a visual summary of the results:

<p align="center">
<img src="/gfiles/rs3.png" width="800px">
</p>

32. Bias and efficiency

Suppose we have a random variable y.p which is normally 
distributed with a mean, mu, and a standard deviation sigma
in a well-defined population of size N. Now, 
suppose we want to use a random sample of n cases drawn 
from that population to develop an inference about the 
population mean. Which estimator will perform better - the sample mean
or, the sample median (the 50th percentile of the distribution 
of y.s)? The following exercise illustrates what happens if we 
draw thousands and thousands of simple random samples of size 
n = 100 (with replacement) from a population with mean 
mu = 100 and standard deviation sigma = 10.

```r
# simulate a random variable, yp, for the
# population [popsize] which is normally 
# distributed with a mean of [mu] and a 
# standard deviation of [sigma]

popsize <- 1000000
mu <- 100
sigma <- 10

y.p <- rnorm(n=popsize,mean=mu,sd=sigma)

# calculate the population mean 

popmean <- mean(y.p)
popmean

# draw a single sample of size n=[sampsize] 
# from the population with replacement

sampsize <- 100
y.ss <- sample(y.p,size=sampsize,replace=T)

# calculate the sample mean and median for the single sample

mean(y.ss)
median(y.ss)

# now, let's repeat this process [nsamples] times

nsamples <- 100000

y.s.mean <- vector()
se.mean <- vector()
y.s.median <- vector()

for(i in 1:nsamples){
  y.s <- sample(y.p,size=sampsize,replace=T)
  y.s.mean[i] <- mean(y.s)
  se.mean[i] <- sd(y.s)/sqrt(sampsize-1)
  y.s.median[i] <- median(y.s)
  }

mean(y.s.mean)
mean(y.s.median)

median(y.s.mean)
median(y.s.median)

sd(y.s.mean)
sd(y.s.median)

mean(se.mean)
median(se.mean)

boxplot(y.s.mean,y.s.median)

```

And, here are the results:

```rout
> # simulate a random variable, yp, for the
> # population [popsize] which is normally 
> # distributed with a mean of [mu] and a 
> # standard deviation of [sigma]
> 
> popsize <- 1000000
> mu <- 100
> sigma <- 10
> 
> y.p <- rnorm(n=popsize,mean=mu,sd=sigma)
> 
> # calculate the population mean 
> 
> popmean <- mean(y.p)
> popmean
[1] 99.98423
> 
> # draw a single sample of size n=[sampsize] 
> # from the population with replacement
> 
> sampsize <- 100
> y.ss <- sample(y.p,size=sampsize,replace=T)
> 
> # calculate the sample mean and median for the single sample
> 
> mean(y.ss)
[1] 99.71239
> median(y.ss)
[1] 99.28097
> 
> # now, let's repeat this process [nsamples] times
> 
> nsamples <- 100000
> 
> y.s.mean <- vector()
> se.mean <- vector()
> y.s.median <- vector()
> 
> for(i in 1:nsamples){
+   y.s <- sample(y.p,size=sampsize,replace=T)
+   y.s.mean[i] <- mean(y.s)
+   se.mean[i] <- sd(y.s)/sqrt(sampsize-1)
+   y.s.median[i] <- median(y.s)
+   }

mean(y.s.mean)
mean(y.s.median)

median(y.s.mean)
median(y.s.median)

sd(y.s.mean)
sd(y.s.median)

mean(se.mean)
median(se.mean)
> 
> mean(y.s.mean)
[1] 99.97951
> mean(y.s.median)
[1] 99.98666
> 
> median(y.s.mean)
[1] 99.97897
> median(y.s.median)
[1] 99.98743
> 
> sd(y.s.mean)
[1] 1.000284
> sd(y.s.median)
[1] 1.243066
> 
> mean(se.mean)
[1] 1.002333
> median(se.mean)
[1] 1.001269
> 
```

<p align="center">
<img src="/gfiles/boxplot-mean-median.png" width="600px">
</p>

* What these results tell us is that both the sample mean and 
the sample median - on average - give us approximately the 
correct inference of a mean of 100. The two estimators differ 
in their sampling variation. The sample mean is, therefore, 
a more efficient estimator of the population mean compared 
to the sample median.

32. Confounding

Suppose we are interested in estimating the difference between
two conditional probabilities, p(y=1|x=1) and p(y=1|x=0). If we
want to make a credible statement that the difference between
these two probabilities is due to variation in *x*, we need to
think about the possibility of confounding (i.e., are there other
variables which influence both the distribution of *x* and the 
distribution of *y*?). Let's consider an example of how this issue
can arise:


| z = 0   | x = 0   | x = 1   |
|--------:|--------:|--------:|
|  y  = 0 |  442    | 406     |  
|  y  = 1 |  417    | 411     |
| Total   |  859    | 817     | 


| z = 1   | x = 0   |   x = 1 | 
|--------:|--------:|--------:|
|  y  = 0 | 136     | 399     |
|  y  = 1 | 302     | 859     |
| Total   | 438     | 1258    |


```rout
p(y=1 | x=0) = (417+302)/(442+417+136+302) = 0.5543562
p(y=1 | x=1) = (411+859)/(406+411+399+859) = 0.6120482
Δ = p(y=1 | x=1) - p(y=1 | x=0) = 0.6120482-0.5543562 = 0.057692

but within the group z = 0, we have:

p(y=1|x=0,z=0) = 417/859 = 0.4854482
p(y=1|x=1,z=0) = 411/817 = 0.50306
Δ|z=0 = p(y=1|x=1,z=0) - p(y=1|x=0,z=0) = 0.50306-0.4854482 = 0.0176118

and, for z = 1, we have:

p(y=1|x=0,z=1) = 302/438 = 0.6894977
p(y=1|x=1,z=1) = 859/1258 = 0.6828299
Δ|z=1 = p(y=1|x=1,z=1) - p(y=1|x=0,z=1) = 0.6828299-0.6894977 = -0.0066678

and, finally, the Δ with adjustment for the effect of z is:

Δ (adj) = p(z=0)*Δ|z=0 + p(z=1)*Δ|z=1 

where p(z=0) = (859+817)/(859+817+438+1258) = 0.4970344 and p(z=1) = 1-p(z=0).
So, we plug in:

Δ (adj) = 0.497*0.018+0.503*(-0.007) = 0.005 (which is only about 10% of the original estimate).
```

Next, let's consider an example where we have a randomized experiment (where *x* is
randomly assigned) and *y* is the outcome. But there are also factors, *z*, that 
influence the outcome distribution. This is not a confounding problem because *z* does not 
influence variation in the distribution of *x* (only the randomizer influences variation in 
the distribution of *x*).


| z = 0   | x = 0   | x = 1   |
|--------:|--------:|--------:|
|  y  = 0 |  562    | 696     |  
|  y  = 1 |  262    | 189     |
| Total   |  824    | 885     | 


| z = 1   | x = 0   |   x = 1 | 
|--------:|--------:|--------:|
|  y  = 0 | 372     | 486     |
|  y  = 1 | 463     | 357     |
| Total   | 835     | 843     |


```rout
p(y=1 | x=0) = (262+463)/(562+262+372+463) = 0.4370102
p(y=1 | x=1) = (189+357)/(696+189+486+357) = 0.3159722
Δ = p(y=1 | x=1) - p(y=1 | x=0) = 0.3159722-0.4370102 = -0.121038

Within the group z = 0, we have:

p(y=1|x=0,z=0) = 262/824 = 0.3179612
p(y=1|x=1,z=0) = 189/885 = 0.2135593
Δ|z=0 = p(y=1|x=1,z=0) - p(y=1|x=0,z=0) = 0.2135593-0.3179612 = -0.1044019

and, for z = 1, we have:

p(y=1|x=0,z=1) = 463/835 = 0.554491
p(y=1|x=1,z=1) = 357/843 = 0.4234875
Δ|z=1 = p(y=1|x=1,z=1) - p(y=1|x=0,z=1) = 0.4234875-0.554491 = -0.1310035

and, finally, the Δ with adjustment for the effect of z is:

Δ (adj) = p(z=0)*Δ|z=0 + p(z=1)*Δ|z=1 

where p(z=0) = (824+885)/(824+885+835+843) = 0.5045763 and p(z=1) = 1-p(z=0).
So, we plug in:

Δ (adj) = 0.505*(-0.104)+0.495*(-0.131) = -0.117 (which is about 97% of the original estimate).

Note that we obtain the adjusted estimate of the effect of x regardless of the effect of 
z on p(y). In this case, variation in z has a strong effect on the distribution of y:

p(y=1 | z=0) = (262+189)/(562+696+262+189) = 0.263897
p(y=1 | z=1) = (463+357)/(372+486+463+357) = 0.488677
Δ = p(y=1 | x=1) - p(y=1 | x=0) = 0.488677-0.263897 = 0.22478

The difference between these two case studies is the joint or bivariate distribution of z and x. 
In the first case, we have:

p(x=1 | z=0) = (406+411)/(442+406+417+411) = 0.4874702
p(x=1 | z=1) = (399+859)/(136+399+302+859) = 0.7417453
Δ = p(x=1 | z=1) - p(x=1 | z=0) = 0.7417453-0.4874702 = 0.2542751

which is a large difference; while, in the second case, we have:

p(x=1 | z=0) = (696+189)/(562+696+262+189) = 0.5178467
p(x=1 | z=1) = (486+357)/(372+486+463+357) = 0.5023838
Δ = p(x=1 | z=1) - p(x=1 | z=0) = 0.5023838-0.5178467 = -0.0154629

which is a small difference. 
```

So, for *z* to be a confounder it needs to influence the distribution
of both *x* and *y*.

##### Problems for Wednesday 8/25/21

1. In one of our simulations above, we demonstrated that the sample mean is a more efficient estimator of the population mean than the sample
median. Rerun this simulation increasing the sample size to 500. Compare your results with the larger sample size to those we obtained earlier.
Do you notice any differences?

Solution:

```rout
> # simulate a random variable, yp, for the
> # population [popsize] which is normally 
> # distributed with a mean of [mu] and a 
> # standard deviation of [sigma]
> 
> popsize <- 1000000
> mu <- 100
> sigma <- 10
> 
> y.p <- rnorm(n=popsize,mean=mu,sd=sigma)
> 
> # calculate the population mean 
> 
> popmean <- mean(y.p)
> popmean
[1] 100.0069
> 
> # draw a single sample of size n=[sampsize] 
> # from the population with replacement
> 
> sampsize <- 500
> y.ss <- sample(y.p,size=sampsize,replace=T)
> 
> # calculate the sample mean and median for the single sample
> 
> mean(y.ss)
[1] 99.97392
> median(y.ss)
[1] 99.96419
> 
> # now, let's repeat this process [nsamples] times
> 
> nsamples <- 100000
> 
> y.s.mean <- vector()
> se.mean <- vector()
> y.s.median <- vector()
> 
> for(i in 1:nsamples){
+   y.s <- sample(y.p,size=sampsize,replace=T)
+   y.s.mean[i] <- mean(y.s)
+   se.mean[i] <- sd(y.s)/sqrt(sampsize-1)
+   y.s.median[i] <- median(y.s)
+   }

mean(y.s.mean)
mean(y.s.median)

median(y.s.mean)
median(y.s.median)

sd(y.s.mean)
sd(y.s.median)

mean(se.mean)
median(se.mean)

boxplot(y.s.mean,y.s.median)
> 
> mean(y.s.mean)
[1] 100.0074
> mean(y.s.median)
[1] 99.99761
> 
> median(y.s.mean)
[1] 100.0067
> median(y.s.median)
[1] 99.9983
> 
> sd(y.s.mean)
[1] 0.4483768
> sd(y.s.median)
[1] 0.5581683
> 
> mean(se.mean)
[1] 0.4475598
> median(se.mean)
[1] 0.4474105
> 
```

With increased sample size, the standard deviation of the sampling distribution for both the mean and the median is smaller than it was with the N=100 sample size. Yet, the standard error for the median is still larger than for the mean (on the order of about 25% larger).


2. Suppose our population we followed for 5 years above had only been followed for 1 year instead. Suppose further that this shortened follow-up
period culminates in a lower population recidivism rate:

```r
pop.recidivism.data <- c(rep("no",773842),rep("yes",226158))
pop.rt <- table(pop.recidivism.data)
pop.rt
pop.recidivism.rate <- pop.rt[2]/(pop.rt[1]+pop.rt[2])
pop.recidivism.rate
```

With this population in mind, evaluate the performance of the 95% confidence interval for a proportion drawing samples of size 500 from the population.
Summarize your conclusions.

Solution:

```rout
pop.recidivism.data <- c(rep("no",773842),rep("yes",226158))
pop.rt <- table(pop.recidivism.data)
pop.rt
pop.recidivism.rate <- pop.rt[2]/(pop.rt[1]+pop.rt[2])
pop.recidivism.rate

prop.rs <- vector()
nsamples <- 10000
sampsize <- 1000

for(i in 1:nsamples){
  recidivism.rs <- sample(pop.recidivism.data,size=sampsize,replace=T)
  recidivism.rs.table <- table(recidivism.rs)
  prop.rs[i] <- recidivism.rs.table[2]/(recidivism.rs.table[1]+recidivism.rs.table[2])
  }

mean(prop.rs)
sd(prop.rs)

prop.rs <- vector()
se.prop.rs <- vector()
lcl.prop.rs <- vector()
ucl.prop.rs <- vector()

lcl.multiplier <- qnorm(p=0.025,mean=0,sd=1)
lcl.multiplier

ucl.multiplier <- qnorm(p=0.975,mean=0,sd=1)
ucl.multiplier 

nsamples <- 10000
sampsize <- 1000

for(i in 1:nsamples){
  recidivism.rs.data <- sample(pop.recidivism.data,size=sampsize,replace=T)
  recidivism.rs.table <- table(recidivism.rs.data)
  prop.rs[i] <- recidivism.rs.table[2]/(recidivism.rs.table[1]+recidivism.rs.table[2])
  se.prop.rs[i] <- sqrt(prop.rs[i]*(1-prop.rs[i])/sampsize)
  lcl.prop.rs[i] <- prop.rs[i]+lcl.multiplie> pop.rt
pop.recidivism.data
    no    yes 
773842 226158 
> pop.recidivism.rate <- pop.rt[2]/(pop.rt[1]+pop.rt[2])
> pop.recidivism.rate
     yes 
0.226158 
> 
> prop.rs <- vector()
> nsamples <- 10000
> sampsize <- 1000
> 
> for(i in 1:nsamples){
+   recidivism.rs <- sample(pop.recidivism.data,size=sampsize,replace=T)
+   recidivism.rs.table <- table(recidivism.rs)
+   prop.rs[i] <- recidivism.rs.table[2]/(recidivism.rs.table[1]+recidivism.rs.table[2])
+   }

mean(prop.rs)
sd(prop.rs)

prop.rs <- vector()
se.prop.rs <- vector()
lcl.prop.rs <- vector()
ucl.prop.rs <- vector()

lcl.multiplier <- qnorm(p=0.025,mean=0,sd=1)
lcl.multiplier

ucl.multiplier <- qnorm(p=0.975,mean=0,sd=1)
ucl.multiplier 

nsamples <- 10000
sampsize <- 1000

for(i in 1:nsamples){
  recidivism.rs.data <- sample(pop.recidivism.data,size=sampsize,replace=T)
  recidivism.rs.table <- table(recidivism.rs.data)
  prop.rs[i] <- recidivism.rs.table[2]/(recidivism.rs.table[1]+recidivism.rs.table[2])
  se.prop.rs[i] <- sqrt(prop.rs[i]*(1-prop.rs[i])/sampsize)
  lcl.prop.rs[i] <- prop.rs[i]+lcl.multiplier*se.prop.rs[i]
  ucl.prop.rs[i] <- prop.rs[i]+ucl.multiplier*se.prop.rs[i]
  }

mean(prop.rs)
sd(prop.rs)
mean(se.prop.rs)
median(se.prop.rs)
pop.p.trapped <- ifelse(pop.recidivism.rate>lcl.prop.rs & pop.recidivism.rate<ucl.prop.rs,"inside","outside")
table(pop.p.trapped)
> 
> mean(prop.rs)
[1] 0.2261008
> sd(prop.rs)
[1] 0.01339391
> 
> prop.rs <- vector()
> se.prop.rs <- vector()
> lcl.prop.rs <- vector()
> ucl.prop.rs <- vector()
> 
> lcl.multiplier <- qnorm(p=0.025,mean=0,sd=1)
> lcl.multiplier
[1] -1.959964
> 
> ucl.multiplier <- qnorm(p=0.975,mean=0,sd=1)
> ucl.multiplier 
[1] 1.959964
> 
> nsamples <- 10000
> sampsize <- 1000
> 
> for(i in 1:nsamples){
+   recidivism.rs.data <- sample(pop.recidivism.data,size=sampsize,replace=T)
+   recidivism.rs.table <- table(recidivism.rs.data)
+   prop.rs[i] <- recidivism.rs.table[2]/(recidivism.rs.table[1]+recidivism.rs.table[2])
+   se.prop.rs[i] <- sqrt(prop.rs[i]*(1-prop.rs[i])/sampsize)
+   lcl.prop.rs[i] <- prop.rs[i]+lcl.multiplier*se.prop.rs[i]
+   ucl.prop.rs[i] <- prop.rs[i]+ucl.multiplier*se.prop.rs[i]
+   }
> 
> mean(prop.rs)
[1] 0.2262347
> sd(prop.rs)
[1] 0.01309429
> mean(se.prop.rs)
[1] 0.01322148
> median(se.prop.rs)
[1] 0.01322588
> pop.p.trapped <- ifelse(pop.recidivism.rate>lcl.prop.rs & pop.recidivism.rate<ucl.prop.rs,"inside","outside")
> table(pop.p.trapped)
pop.p.trapped
 inside outside 
   9527     473 
```

Note: The 95% confidence interval traps the true population parameter approximately 95% of the samples studied.
In addition, the average value of the parameter estimates is very similar to the true population parameter.
The average standard error is also close to the standard deviation of the (approximate) sampling distribution.


3. For each of the 2 data sets below, calculate Δ = p(y=1|x=1)-p(y=1|x=0). Then, calculate Δ adjusting for the effect of *z*. Check on the distribution
of *z* for different levels of *x* and *y*. Summarize your results.

Table 1

| z = 0   | x = 0   | x = 1   |
|--------:|--------:|--------:|
|  y  = 0 |  854    | 968     |  
|  y  = 1 |  372    | 298     |
| Total   |  1226    | 1266     | 


| z = 1   | x = 0   |   x = 1 | 
|--------:|--------:|--------:|
|  y  = 0 | 622     | 706     |
|  y  = 1 | 624     | 556     |
| Total   | 1246     | 1262   |

Solution: 

```rout
> py1x0 <- (372+624)/(854+372+622+624)
> py1x0
[1] 0.4029126
> py1x1 <- (298+556)/(968+298+706+556)
> py1x1
[1] 0.3378165
> py1x1-py1x0
[1] -0.06509617
> 
> py1x0z0 <- 372/(854+372)
> py1x1z0 <- 298/(968+298)
> delta.z0 <- py1x1z0-py1x0z0
> delta.z0
[1] -0.06803873
> 
> py1x0z1 <- 624/(622+624)
> py1x1z1 <- 556/(706+556)
> delta.z1 <- py1x1z1-py1x0z1
> delta.z1
[1] -0.06023205
> 
> pz0 <- (1226+1266)/(1226+1266+1246+1262)
> pz1 <- 1-pz0
> 
> delta.adj <- pz0*delta.z0+pz1*delta.z1
> delta.adj
[1] -0.0641229
> 
```

The adjusted delta is very similar to the overall delta so z is not a confounder.


Table 2

| z = 0   | x = 0   | x = 1   |
|--------:|--------:|--------:|
|  y  = 0 |  1439    | 263     |  
|  y  = 1 |  631    | 130    |
| Total   |  2070    | 393     | 


| z = 1   | x = 0   |   x = 1 | 
|--------:|--------:|--------:|
|  y  = 0 | 750     | 374     |
|  y  = 1 | 905     | 508     |
| Total   | 1655     | 882   |

Solution:

```rout
> py1x0 <- (631+905)/(1439+631+750+905)
> py1x0
[1] 0.412349
> py1x1 <- (130+508)/(263+130+374+508)
> py1x1
[1] 0.5003922
> py1x1-py1x0
[1] 0.08804316
> 
> py1x0z0 <- 631/(1439+631)
> py1x1z0 <- 130/(263+130)
> delta.z0 <- py1x1z0-py1x0z0
> delta.z0
[1] 0.02595789
> 
> py1x0z1 <- 905/(750+905)
> py1x1z1 <- 508/(374+508)
> delta.z1 <- py1x1z1-py1x0z1
> delta.z1
[1] 0.02913592
> 
> pz0 <- (2070+393)/(2070+393+1655+882)
> pz1 <- 1-pz0
> 
> delta.adj <- pz0*delta.z0+pz1*delta.z1
> delta.adj
[1] 0.02757042
> 
```

In this case, the adjusted delta is much smaller than the original delta (0.089 vs. 0.028). This suggests that
*z* is a confounder in this analysis.
