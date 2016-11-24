# Bit Operators

## `~` [NOT](https://en.wikipedia.org/wiki/Bitwise_operation#NOT)
The bitwise NOT, or complement, is a unary operation that performs logical negation on each bit, forming the ones' complement of the given binary value. Bits that are 0 become 1, and those that are 1 become 0. For example:

### Truth table
| A | ~A |
| --- | --- |
| 0 | 1 |
| 1 | 0 |

## `&` [AND](https://en.wikipedia.org/wiki/Bitwise_operation#AND)
A bitwise AND takes two equal-length binary representations and performs the logical AND operation on each pair of the corresponding bits, by multiplying them. 

### Truth table
| A | B | A&B |
| --- | --- | --- |
| 0 | 0 | 0 |
| 0 | 1 | 0 |
| 1 | 0 | 0 |
| 1 | 1 | 1 |

## `|` [OR](https://en.wikipedia.org/wiki/Bitwise_operation#OR)
A bitwise OR takes two bit patterns of equal length and performs the logical inclusive OR operation on each pair of corresponding bits. The result in each position is 0 if both bits are 0, while otherwise the result is 1. For example:

### Truth table
| A | B | A|B |
| --- | --- | --- |
| 0 | 0 | 0 |
| 0 | 1 | 1 |
| 1 | 0 | 1 |
| 1 | 1 | 1 |

## `^` [XOR](https://en.wikipedia.org/wiki/Bitwise_operation#XOR)
In this we perform the comparison of two bits, being 1 if the two bits are different, and 0 if they are the same.

## Truth table
| A | B | A^B |
| --- | --- | --- |
| 0 | 0 | 0 |
| 0 | 1 | 1 |
| 1 | 0 | 1 |
| 1 | 1 | 0 |


## `<<` Shift Left

- Add `n` `0` bits to the right.
- A left arithmetic shift by `n` is equivalent to multiplying the number by `2^n`.
- For example: `10111 << 1 = 101110`

## `>>` Shift Right

- Remove `n` bits from the right (`0` or `1`).
- A right arithmetic shift by `n` is equivalent to dividing by `2^n`.
- For example: `10010111 >> 1 = 1001011`

See also Java section on [Bit Arithmetics/Operations](/java/java.md#bit-arithmeticsoperations) and Data Structures code examples [for BitSet](/basics/data-structures-code-examples.md#bitset).


## Hacks
Taken from [this StackOverflow response](http://stackoverflow.com/a/47990/2938519)

### Setting a bit
Set bit x.
```
number |= 1 << x;
```

### Clearing a bit
To clear bit x you must invert the bit string with the bitwise NOT operator (~), then AND it.
```
number &= ~(1 << x);
```

### Toggling a bit
The XOR operator (^) can be used to toggle a bit.
```
number ^= 1 << x;
```

### Checking a bit
To check a bit, shift the number x to the right, then bitwise AND it:
```
bit = (number >> x) & 1;
```

## Language Tests
- Java
