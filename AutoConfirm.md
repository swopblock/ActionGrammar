**Intentions:**

![Intentions](diagram/Intentions.svg)

```
Intentions
         ::= User Ordering
           | Auto ( Invoicing | Changing | Confirming ) '.'
```

**Auto:**

![Auto](diagram/Auto.svg)

```
Auto     ::= 'We are '
```

referenced by:

* Intentions

**Confirming:**

![Confirming](diagram/Confirming.svg)

```
Confirming
         ::= ( Expensing | Receipting ) Experiation Signature
```

referenced by:

* Intentions

**Expensing:**

![Expensing](diagram/Expensing.svg)

```
Expensing
         ::= 'confirming the expense ' Expense ' paying for ' Receipt
```

referenced by:

* Confirming

**Receipting:**

![Receipting](diagram/Receipting.svg)

```
Receipting
         ::= 'confirming the receipt ' Receipt ' cashing for ' Expense
```

referenced by:

* Confirming

**Execution:**

![Execution](diagram/Execution.svg)

```
Execution
         ::= ' and the order was executed when the market volume reached ' ExactAmount
```

**Signature:**

![Signature](diagram/Signature.svg)

```
Signature
         ::= ' using the signature ' AlphaNumeric
```

referenced by:

* Confirming

**Expense:**

![Expense](diagram/Expense.svg)

```
Expense  ::= ExactAmount ' using ' Address
```

referenced by:

* Expensing
* Receipting

**Receipt:**

![Receipt](diagram/Receipt.svg)

```
Receipt  ::= ExactAmount ' using ' Address
```

referenced by:

* Expensing
* Receipting

**ExactAmount:**

![ExactAmount](diagram/ExactAmount.svg)

```
ExactAmount
         ::= ' exactly ' Numeric Units
```

referenced by:

* Execution
* Expense
* Receipt

**Address:**

![Address](diagram/Address.svg)

```
Address  ::= ' the ' Units ' address ' AlphaNumeric
```

referenced by:

* Expense
* Receipt

**Units:**

![Units](diagram/Units.svg)

```
Units    ::= 'BTC'
           | 'ETH'
           | 'SWOBL'
```

referenced by:

* Address
* ExactAmount

## 
![rr-2.0](diagram/rr-2.0.svg) <sup>generated by [RR - Railroad Diagram Generator][RR]</sup>

[RR]: http://bottlecaps.de/rr/ui