# Disrcete Mathematics

- [Lecture 0 Introduction to propositional logic](#Lecture0)
- [Lecture 1 First order logic, start of proofs](#Lecture1)
- [Lecture 2 All proof techniques except induction](#Lecture2)
- [Lecture 3 Induction proofs](#Lecture3)
- [Lecture 4 Set theory - basic notations](#Lecture4)

## <a name=Lecture0></a> Lecture 0 6/9/22 Intro, propositional logic (Book/Lecture Notes: 1.1, 1.2, 1.3)
### Integers
- Whole numbers
- Symbol: ℤ

### Natural Numbers
- All integers greater then 1
- 0 is not a natural number (in this course atleast)
- Symbol: ℕ

### Rational Numbers
- Any number that can be written as a/b where a and b are both integers and b is not equal to 0.
- Symbol: Q

### Real Numbers
- Basicly all numbers. 
- Every possible number.
- Symbol: ℝ

### Divisibility
- m is divisible by k if there is an integer n such that mInduction proofs = k * n

### Odd numbers
- Any integer not divisble by 2
- n is odd if you can write it as n = 2m + 1

### Even numbers
- Any integer divisibl by 2
- n is even if you van write it as n = 2 * m
- 0 is an even number

### Perfect Square
- A product of an integer with itself

### Prime numbers
- Any natural number greather or equal to 2, which is oly divisible by itself and 1

### Statements
- Either true or false


### Proposition
#### Negation(NOT)
- not
- the negation for propostion p is not p

#### Conjunction(AND)
- and
- p AND q is true if both p and q are true.
- if one of them is false the statement is false

#### Disjunction(OR)
- or
- p OR q is true whenever p or q is true.
- p OR q is only false when both p and q are false.

#### Compound propositions
- p means "2 is an odd number" (FALSE)
- q means "37 is a prime number" (TRUE)
- r means "Maastricht is in Lumburg" (TRUE)

So:
- p and q or r  = TRUE
- (p and q) or r = TRUE
- p and (q or r) = FALSE

### Truth tables
- Truth tables allow us to systematially understand when a proposition is true or false

- [insert immages for truthtables for TRUE, FALSE, AND and OR]
#### Tautology
- This happens when the whole truth table turns out TRUE

#### Contradiction
-This happens when the whole truth table turns out FALSE

#### Conditional statements
##### Conditional
- if p then q
- if --> q
- "p implies q"
- if p exists then q does so
- this statement is only false is p is true and q is false
- Use the drinking beer example

##### Biconditional
- p if and only if q
- p <--> q
- p iff q
- p only excists when q excists
- This statement is only TRUE when both are TRUE or FALSE

## <a name=Lecture1></a> Lecture 1 7/9/22 First order logic, start of proofs (Book/Lecture Notes: 1.4, 1.5)

### Quaintifiers
- For all symbol: ∀
- There exists: ∃
**Examples:**
- (∀ elephants)(elephants has trunk) TRUE
- (∀ students)(students likes banana) FALSE
- (∃ even prime number)(number bigger than 2) FALSE
- (∀ balls in box)(balls are red) TRUE (if there are no balls in box)
- (∃ ball in box)(ball is red) FALSE (if there are no balls in box)

- To disprove a statement you have to prove the negation of that statement.

**Some other examples**
"All integers are bigger than 5", can also be written as:
- (∀ integers)(integer > 5)
- (∀x ∈ ℤ)(x > 5)
- ∀x ∈ ℤ : x > 5

"Some realnumber is smaller than 3", can also be written as:
- (∃ realnumber)(realnumber < 3)
- (∃x ∈ ℝ)(x < 3)
- ∃x ∈ ℝ : x < 3

**Now try and write the oppisite:**
P: (∀ elephants)(elephant has trunk):
- ¬P : ¬[(∀ elephants)(elephant has trunk)]
- ¬P : (∃ elephant)(elephant has no trunk)

Conlusion: To negate, you flip the quantifier and you negate the body.

### Higher depth quantifiers

**Example**
(∃ tree t)(∀ monkeys m)(m climbs t) FALSE  
because:<br>
<img src="imgs/MonkeyTree1.png"  width=25% height=25%>

(∀ monkeys m)(∃ trees t)(m climbs t) TRUE  
because:<br>
<img src="imgs/MonkeyTree2.png"  width=25% height=25%>


**Negation of example:**
P: (∃ tree t)(∀ monkeys m)(m climbs t):
- ¬P: [(∃ tree t)(∀ monkeys m)(m climbs t)]
- ¬P: (∀ trees t)(∃ monkey m)(m does not climb t)

### Direct proof
**Example 1**  
(∀x ∈ ℤ)(∃y ∈ ℤ)(3x + y <= 4) which is TRUE<br>
*proof by direct proof:*  <br>
<ins>let</ins> x ∈ ℤ <ins>take</ins> y = 3-3x  
(y ∈ ℤ because x = ℤ)  
<ins>then</ins> 3x+y=3x+(3-3x) = 3 <= 4 which completes the proof.

**Example 2**  
(∃x ∈ ℤ)(∀y ∈ ℤ)(3x + y <= 4) which is FALSE<br>
*proof by direct proof:*<br>
first we negate the proposition (WHY?) Sometimes to prove a proposition you have to disprove the negation of that proposition. In this case we have to disprove the propositio, so we are gonna prove the negation of the proposition.  
(∀x ∈ ℤ)(∃x ∈ ℤ)(3x + y > 4)  
<ins>let</ins> x ∈ ℤ <ins>take</ins> y = 5-3x
<ins>then</ins> 3x + (5-3x) > 4 = 5 > 4 is TRUE, which means that the orignal proposition is FALSE  
which completes the proof.

### Proof by Counter Example
**Example 1**  
(∀x ∈ ℤ)(∃y ∈ ℕ)(3x + y > 4)  TRUE <br>
*disprove by counter example:* <br>
<ins>Take</ins> x = 5  
<ins>Then</ins> for all natural numbers y we have 3x + y >= 15 + 1 (because y is ℕ) = 16 > 4 wich completes the prove.

**Example 2** 
(∀x ∈ ℝ)(∃y ∈ ℤ)(3x + y <= 4)<br> 
*disprove by counter example*<br>
<ins>let</ins> x ∈ ℝ: <ins>take</ins> y = ⌊3-3x⌋ (This is a flooring function, this roundsdown the function and will always be smaller then 3-3x. We have to do this because y cant by in ℤ because x is in ℝ)   
<ins>then</ins> 3x + y = 3x + ⌊3-3x⌋   
<= 3x + 3 - 3x = 3 <= 4 Whih is TRUE and completes the proof.

## <a name=Lecture2></a> Lecture 2 8/9/22 All proof techniques except induction (Book/Lecture Notes: 1.5)
### Proof by contradiction 
If we prove by contradiction you try to prove ¬P = FALSE instead of p = TRUE.<br>
You can do thi by assuming ¬P = TRUE and applying logical consequences to arrive at a contradiction.<br>

**Example 1**
*Prove that there is an infinite number of primes*<br>
<ins>First</ins> try to prove the negation of the propisition.<br> 
<ins>Assuming</ins>there is an infinite number of primes <br>
<ins>Then</ins> the contradiction is thath there is a biggest prime.<br>
<ins>let</ins> n ∈ Primes such that prime n = biggest prime.<br> 
{p1, p2,p3,.....} = {2,3,5,..,pn}<br>
consider the following number: <br>
N = p1 · p2 · p3 · . . . ·pn + 1 = 2 · 3 · 5 · . . . · pn + 1<br>
So N is the product of all prime numbers + 1.<br>
Then N is not divisible by 2, 3, 5, 7, and eventually pn.<br>
This means N is not divisble by any prime number.<br>
Since every natural number >= 2 that is not a prime can be written as a product of prime factors, N is a prime number itself.<br>
This however contradicts the assumption that pn is the biggest prime number because N is much bigger.<br>
*Conclusion:*<br>
So the propisition we tried to prove is FALSE, which means that there are infinite prime numbers thus the proof completes.

**Example 2**
Prove that there is no biggest number smaller then 1.<br>
Negation = there is a biggest number x smaller then 1.<br>
<img src="imgs/BigNumSmal1.png"  width=25% height=25%><br>
<ins>let</ins> x < 1 <ins>take</ins>y=(x+1)/2<br>
<ins>then</ins> y > (x+x)/2 = 2x/2 = x, So y > x<br>
This already tells us there is a bigger number then x, but we still have to prove y is smaller then 1.<br>
y < (1 + 1)/2 = 1, So y is smaller then 1<br>
x < y < 1. This proves that there is a biggest number than the biggest number we thought was te biggesst number. <br>
So it disproves our assumption and proves the initial proposition. Which completes the proof.

### Proof by contrapositive
- Trying to prove a proposition by contra positive looks like: p => q = ¬q => ¬p

**Example 1**
Prove -2 < x < 2 => x^2 + x -6 < 0 <br>
- contra positive is x > 2 or x < -2 and x^2 + x - 6 => 0
- x^2 + x - 6 => 0 = x > 2 or x < -2
- <ins>let</ins> x ∈ ℝ <ins>such that</ins> x^2 + x - 6 >= 0 (We try to prove LHS because we can calculate x)
- x^2 + x - 6 = (x+3)(x-2)
- x = -3 or x = 2
- Both need to be equal or be bigger then zero, so x >= either - 3 or 2
- So in this case only x >= 2 holds, but that is enough to prove the statement because of the OR operator.

**Example 2**
Prove ∀x ∈ ℤ : x^2 != 3
- contra positive: x^2 = 3 => x !∈ ℤ
- √x = √3 or -√3
- both are not an Integer.

### Biconditional Proof
- To prove a biconditional proposition such as, p <=> q, we have to prove two conditions at ones: p => q and q => p

**Example 1** <br>
Prove (x^2 + 5x - 6 = 0) <=> (x=-6 or x=1)
- First prove (x^2 + 5x - 6 = 0) => (x=-6 or x=1)
  - x^2 + 5x - 6 = 0 
  - (x - 1)(x + 6) = 0
  - So x = 1 or x = -6 TRUE
- Secondly prove (x=-6 or x=1) => (x^2 + 5x - 6 = 0)
  - (-6^2) + (5 * -6) - 6 = 0
  - 36 - 30 - 6 = 0 = 0 TRUE

**Example 2** <br>
Prove For all Natural numbers m and n: x >= y + 1 <=> x^2 >= y^2 + 3 (in this case we have two variables, bit different answer)
- First prove x >= y +1 => x^2 >= y^2 + 3
  - <ins>let</ins> x >= y + 1 this implies x^2 = (y + 1)^2
  - x^2 ≥ (y + 1)(y + 1)
  - x^2 ≥ y^2 + 2y + 1
  - x^2 ≥ y^2 + (2 * 1) + 1 (because y ≥ 1)
  - x^2 ≥ y^2 + 3 TRUE
- Secondly prove x^2 ≥ y^2 + 3 => x ≥ y + 1 
  - <ins>Let</ins> x2 ≥ y2 +3 <ins>then</ins> x must be bigger then y.
  - Since they are both natural numbers that implies x ≥ y + 1. TRUE

## <a name=Lecture3></a> Lecture 3 13/9/22 Induction proofs (Book/Lecture Notes: 1.6)
### Mathematical Induction
- Prove that for all numbers n >= ℕ where n is constant.  
  - First you start of by proving the <ins>base case</ins>: P(n=1)
  - Secondly you prove that for every n >= N <ins>Inductive step</ins>: P(n) => P(n+1) 

**Example 1**<br>
We have a country that has two types of coins: 3c and 7c.<br>
Now prove that you can make all sums of money >= 12 with these types of coins.<br>
- Prove by induction:
- Base case:
  - Does P(12) hold?
  - (3+3+3+3=12) TRUE
- Induction step: 
  - We need to prove the following: For al n >= 12, P(n) => P(n+1)
  - <ins>let</ins> n be an arbitrary natural number >= 12.
  - <ins>assume</ins> P(n) holds. Our goal is to prove P(n + 1)
  - Consider several cases:
  - **Case 1:**
    - we use at least two 7c coins to make n cents. 
    - <img src="imgs/cents1.png" width=25% height=25%>
    - p(n+1) holds
  - **Case 2:**
    - we use atleast two 3c coins to make n cents.
    - <img src="imgs/cents2.png" width=25% height=25%>
    - p(n+1) holds
  - Note that atleast one of case 1 and 2 must hold. If neither hold, we would at most have one 7c coin and one 3c coin.
  - So n >= 7 + 3 = 10. But this contradicts n >= 12. So whichever case hold we are good, P(n+1) holds.

**Example 2:**<br>
Prove by induction that for all Natural numbers n, the following holds: n&i=1∑i = (n/2)(n+1) P(n):  
- Prove by induction:
- Base case:
  - Does P(1) hold?
  - This means is it true that: 1&i=1n∑i = 1/2(1+1)
  - which is 1 = 1 TRUE
- Induction step:
  - We need to prove that for all Natural numbers n, P(n) = P(n+1)
  - Our goal is to prove P(n+1)(when P(n) is holding)
  - We need to prove this n+1&i=1n∑i (LHS) =((n+1)/2)((n+1)+1) P(n+1) ()
  - <ins>let</ins> n be an arbitrary number.
  - <ins>assume</ins> P(n) holds.
  - <ins>consider</ins> LHS = RHS + (n + 1)         (N+1 is universally true by algebra)
  - LHS = n/2(n + 1) + (n + 1)
  - LHS = (n + 1)((n/2) + 1)
  - LHS = (n + 1)((n+2)/2) = 1/2(n + 1)(n + 2)
  - 1/2(n + 1)(n + 2) = ((n + 1)/2)((n + 1) + 1) = RHS, So TRUE

**Example 3**<br>
Prove that 4^n - 1 is divisible by 3, for all natural n.
- Base Case:
  - Does P(n=1) hold
  - 4^1 - 1 = 3 which is divisible by 3.
- Inducion Step:
  - <ins>let</ins> n be an arbitrary natural number.
  - <ins>assume</ins> P(n) holds.
  - We want to prove P(n+1)
  - Such that 4^(n+1) - 1 is divisible by 3
  - 4^(n+1)- 1 = 4 * 4^n - 1
  - = 4 * 4^n - 4 + 3
  - = 4(4^n-1) + 3
  - we know that 4^n-1 is divisible by 3. Multiplied by for is also still divisible by 3. And 3 by itself is aswell divisible by 3.
  - which means the whole expression is divisible by 3, thus P(n+1) holds.

**Example 4**<br>
Prove by induction that for all natural numbers n >= 3 such that n^2 > 2n + 1
- Base case:
  - P(3) => 3^3 > 2 * 3 + 1
  - 9 > 7, P(3) Holds
- Inductive step:
  - <ins>let</ins> n be an arbitrary natural number >= 3
  - <ins>assume</ins> that P(n) holds.
  - We need to prove P(n+1) holds. We do this by checking the growth between the old and new
  - (n+1)^2 > 2(n+1) + 1
  - Note that (n+1)^2 - n^2 > 2n + 1 (by algebra)
  - new LHS - old LHS > old RHS (by algebra)
  - new RHS = 2(n+1) + 1, old RHS = 2n + 1
  - new RHS - old RHS = (2(n+1) + 1) - (2n + 1) = 2, So the increase of the inequality in RHS is 2
  - If we can show the increase in LHS >= increase in RHS we have proven P(n + 1)
  - new LHS - old LHS = (n+1)^2 - n^2 = n^2 + 2n + 1 - n^2 = 2n + 1
  - 2n + 1 >= 2 because n >= 3, So TRUE

## <a name=Lecture4></a> Lecture 4 14/9/22 Set theory - basic notations (Book/Lecture Notes: 2.1, 2.2)
### Set Theory
- Good examples of infinite sets are ℤ and ℕ.
- Examples of finite sets:
  - {1,2,3,4}
  - {spaghetti, rice, patatoes, bread}
  - {1,2, pi, cricket} 

- Sets are UNORDERD.
  - {1,2,3,4} = {2,1,4,3} 
- Sets have NO DUPLICATES
  - {1,2,3,3} = {1,2,3}
- Sets are allowed to be empty.
  - The empty set: Φ or {}
- Sets can be finite or infinite.

### Cardinality
- We denote the size of a set A as |A|
- "formally | cardinality"
- eg. cardinality of |{1,2,3,4}| = 4 and the cardinality of |{1,2,3,3}| = 3

### Some symbols
- Is in a set: ∈
- Is not in a set: ∉

- A = {1,{2,3}} |A|=2
  - 1 ∈ A
  - {2,3} ∈ A
  - {1} ∉ A
  - 2 ∉ A
  - 3 ∉ A
  - Φ ∉ A

<img src="imgs/set.png" width=15% height=15%>

### Describing elements of a set
<ins>Let</ins> p be the set of prime numbers or,
- p = {x:n is a prime number}
- p = {x ∈ ℕ ^ is prime}
- p = {x:x ∈ ℕ ^ is prime}

### Subsets
- A = {x : x is student}
- B = {x : x is a student at DACS}
- Clearly B is "inside" A
- "Formally we say B is a subset of A."
- Symbol: B ⊆ A 
- not the same as ∈

#### Formal Definition 
- B ⊆ A
- Also means: for all x ∈ B , x ∈ A
- But also: (∀x ∈ B)(∀x ∈ A)
- But also: if x ∈ B  then x ∈ A

- is A ⊆ A TRUE (motivation: let x b an arbitrary element A, we need to show x ∈ A)
- is Φ ⊆ A TRUE (because there is nothing to prove in Φ, so the ∀ quantifier is empty <-> vacuous truth)
- is Φ ⊆ Φ TRUE

**A = {1,2} **<br>
- 1 ∈ A TRUE
- 1 ⊆ A FALSE (works only for sets)
- {1} ⊆ A TRUE 
- {1,2} ⊆ A TRUE
- {1,3} ⊆ A FALSE
- Φ ⊆ A TRUE (Always!)
- Φ ∈ A FALSE
- {1} ∈ A FALSE

**Some other examples: **<br>
- A = {1,2,{3}}
  - {1} ∈ A TRUE
  - {1} ⊆ A TRUE
- Some facts with Φ
  - - Φ = {Φ} FALSE
  - |Φ| = 0
  - |{Φ}| = 1
- A = {1,2,{3}}
  - {1,2,3} ⊆ A FALSE
- B = {1,2,Φ}
  - Φ ⊆ B TRUE
  - Φ ∈ B TRUE
  - Φ ∈ Φ FALSE

#### Set equality
- {-1,1,2} = {-1,2,1}
- {2,1,-1,-2} = {a ∈ ℝ: x^2 = 4 v x^2 = 1} <br>
So what ds A = B mean?<br>

**Definition A=B**
- A = B <=> (A⊆B)^(B⊆A)
- A = B <=> ((x∈A => x∈B) ^ (x∈B => x∈A))
- To prove that A=B, you can prove A⊆B and then also that B⊆A!

**Alternative definition: **<br>
- A = B <=> (x∈A <=> x∈B)

**Union**<br>



