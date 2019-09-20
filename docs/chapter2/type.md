# 基础类型

TypeScript 支持与 JavaScript 几乎相同的数据类型，此外还提供了实用的枚举类型方便我们使用。


## 布尔值

最基本的数据类型就是简单的 true/false 值，在JavaScript 和 TypeScript 里叫做 boolean（其它语言中也一样）。

``` ts
let isDone: boolean = false
```

## 数字

和 JavaScript 一样，TypeScript 里的所有数字都是浮点数。 这些浮点数的类型是 number。 除了支持十进制和十六进制字面量，TypeScript 还支持 ECMAScript 2015中引入的二进制和八进制字面量。

``` ts
let decLiteral: number = 20
let hexLiteral: number = 0x14
let binaryLiteral: number = 0b10100
let octalLiteral: number = 0o24
```

## 字符串

JavaScript 程序的另一项基本操作是处理网页或服务器端的文本数据。 像其它语言里一样，我们使用 string 表示文本数据类型。 和 JavaScript 一样，可以使用双引号（"）或单引号（'）表示字符串。

``` ts
let name: string = 'bob'
name = 'smith'
```

你还可以使用模版字符串，它可以定义多行文本和内嵌表达式。 这种字符串是被反引号包围（ `），并且以 ${ expr } 这种形式嵌入表达式

``` ts
let name: string = `Yee`
let age: number = 37
let sentence: string = `Hello, my name is ${ name }.

I'll be ${ age + 1 } years old next month.`
```



## 数组

TypeScript 像 JavaScript 一样可以操作数组元素。 有两种方式可以定义数组。 第一种，可以在元素类型后面接上 []，表示由此类型元素组成的一个数组：

``` ts
let list: number[] = [1, 2, 3]
```

第二种方式是使用数组泛型，Array<元素类型>:

``` ts
let list: Array<number> = [1, 2, 3]
```



## 元祖 Tuple

元组类型允许表示一个已知元素数量和类型的数组，各元素的类型不必相同。 比如，你可以定义一对值分别为 string 和 number 类型的元组。

``` ts
let x:[string, number]
x = ['hello', 10] // OK
x = [10, 'hello'] // Error
```

当访问一个已知索引的元素，会得到正确的类型：
``` ts
console.log(x[0].substr(1)) // OK
console.log(x[1].substr(1)) // // Error, 'number' 不存在 'substr' 方法
```


## 枚举

1

``` ts
```


## any

有时候，我们会想要为那些在编程阶段还不清楚类型的变量指定一个类型。 这些值可能来自于动态的内容，比如来自用户输入或第三方代码库。 这种情况下，我们不希望类型检查器对这些值进行检查而是直接让它们通过编译阶段的检查。 那么我们可以使用 any 类型来标记这些变量：

``` ts
let noSure: any = 4
noSure = 'maybe a string instead'
noSure = false // 也可以是个 boolean
```

在对现有代码进行改写的时候，any 类型是十分有用的，它允许你在编译时可选择地包含或移除类型检查。并且当你只知道一部分数据的类型时，any 类型也是有用的。 比如，你有一个数组，它包含了不同的类型的数据：

``` ts
let list: any[] = [1, true, 'free']  

list[1] = 100
```


## 空值 void

1

``` ts
```


## void

1

``` ts
```


## null 和 undefined

1

``` ts
```

## never

1

``` ts
```

## object

1

``` ts
```

## 类型断言

有时候你会遇到这样的情况，你会比 TypeScript 更了解某个值的详细信息。 通常这会发生在你清楚地知道一个实体具有比它现有类型更确切的类型。

通过类型断言这种方式可以告诉编译器，“相信我，我知道自己在干什么”。 类型断言好比其它语言里的类型转换，但是不进行特殊的数据检查和解构。 它没有运行时的影响，只是在编译阶段起作用。 TypeScript 会假设你，程序员，已经进行了必须的检查。

类型断言有两种形式。 其一是“尖括号”语法：

``` ts
let someValue: any = 'this is a string'

let strLength: number = (<string>someValue).length
```

另一个为 as 语法：

``` ts
let someValue: any = 'this is a string'

let strLength: number = (someValue as string).length
```
