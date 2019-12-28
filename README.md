# lessMixin

> a less mixin library

## 这是一个自用的 css-less mixin 库

在你的项目里面放入`Less`文件夹即可。文件内引入：`@import url('./Less/le_index');`

## useful

- 已经定义好的样式，像函数一样传入参数就可以使用。
- 省去繁琐的浏览器前缀，`lessMixin`已经为您定义好了前缀。

## important

1. 指定参数
   - 指定参数的时候目前不支持使用`@xxx: xxx;`的形式
   - 第一个参数为空的时候，**除了特殊说明外，需要指定`none`**。
   - 第二个参数为空的时候，需要**直接省略不写**
   - 指定参数的时候，每个参数结尾最好使用`;`的形式。

## Nav

- [.le_wh](#.le_wh)
- [.le_sw](#.le_sw)
- [.le_cb](#.le_cb)
- [.le_square](#.le_square)
- [.le_square](#.le_circle)
- [.le_shadow/le_shadow_inset](#.le_shadow/le_shadow_inset)
- [.le_border](#.le_border)
- [.le_flex](#.le_flex)
- [.le_relative](#.le_relative)
- [.le_relative_tl](#.le_relative_tl)
- [.le_relative_zero](#.le_relative_zero)

## Use

### .le_wh

wh 代表`width`和`height`

**Example**

```javascript
div {
    .le_wh(100px; 100px);
}

result:

div {
    width: 100px;
    height: 100px;
}
```

如果想要只**指定一个**参数，另一个需要写成`none`

```javascript
// 指定第一个参数的情况下：
div {
    .le_wh(100px);
}

result:

div {
    width: 100px;
}

// 指定第二个参数的情况下：
div {
    .le_wh(none; 100px);
}

result:

div {
    height: 100px;
}
```

### .le_sw

sw 代表`size`和`weight`

**Example**

```javascript

div {
  .le_sw(20px; 500);
}

result:

div {
    font-size: 20px;
    font-weight: 500;
}

// 指定第一个参数

div {
    .le_sw(20px);
}

result:

div {
    font-size: 20px;
}

// 只指定第二个参数

div {
    .le_sw(none; 500);
}

result:

div {
    font-weight: 500;
}
```

### .le_cb

cb 代表`color`和`background-color`

**Example**

```javascript

div {
    .le_cb(#fff; #000);
}

result:

div {
    color: #fff;
    background-color: #000;
}

// 指定第一个参数

div {
    .le_cb(#fff);
}

result:

div {
    color: #fff;
}

// 只指定第二个参数

div {
    .le_cb(none; #000);
}

result:

div {
    background-color: #000;
}
```

- .le_zero

zero 代表`padding`和`margin`

**Example**

```javascript

div {
    .le_zero();
}

result:

div {
    margin: 0;
    padding: 0;
}

```

### .le_square

square 代表`height`和`width`。描述一个*正方形*。默认为`100px`。

**Example**

```javascript

div {
    .le_square(100px);
}

result:

div {
    width: 100px;
    height: 100px;
}

// 默认

div {
    .le_square();
}

 div {
    width: 100px;
    height: 100px;
 }
```

### .le_circle

square 代表`height`、`width`和`border-radius`。描述一个*圆形*。默认为`100px`。

**Example**

```javascript

div {
    .le_circle(100px);
}

result:

div {
    width: 100px;
    height: 100px;
}

// 默认

div {
    .le_circle();
}

 div {
    width: 100px;
    height: 100px;
 }
```

### .le_shadow/le_shadow_inset

shadow 代表 `box-shadow`，默认阴影为*外阴影*，参数为`0px 2px 4px rgba(0, 0, 0, 0.12)`。

shadow_inset 代表`box-shadow`，默认阴影为*内阴影*，参数为`inset 0px 2px 4px rgba(0, 0, 0, 0.12)`。

**Example**

```javascript
// shadow

// 默认
div {
    .le_shadow();
}

result:

div {
    box-shadow: 0px 2px 4px rgba(0, 0, 0, 0.12);
}

// 指定参数
div {
    .le_shadow(0px; 2px; 4px; rgba(0, 0, 0, 0.12));
}

result:

div {
    box-shadow: 0px 2px 4px rgba(0, 0, 0, 0.12);
}

// shadow_inset

// 默认

div {
    .le_shadow_inset();
}

result:

div {
    box-shadow: inset 0px 2px 4px rgba(0, 0, 0, 0.12);
}

// 指定参数
div {
    .le_shadow_inset( inset; 0px; 2px; 4px; rgba(0, 0, 0, 0.12)))
}

result:

div {
    box-shadow: inset 0px 2px 4px rgba(0, 0, 0, 0.12);
}


```

### .le_border

border 代表 `border`，默认参数为`1px solid rgba(0, 0, 0, .1)`。

**Example**

```javascript

// 默认

div {
    .le_border();
}

result:

div {
    border: 1px solid rgba(0, 0, 0, .1);
}


// 传入参数

div {
    .le_border(5px; dotted; #ff0000);
}

result:

div {
    border: 5px dotted #ff0000;
}

// 如果只想指定任意一个值，可以使用
// @width  代表`border-width`
// @style  代表`border-style`
// @color  代表`border-color`


// 指定`border-width`
div {
    .le_border(@width: 5px);
}

result:

div {
    border: 5px solid rgba(0, 0, 0, .1);
}

// 指定`border-style`

div {
    .le_border(@style: double);
}

result:

div {
    border: 1px double rgba(0, 0, 0, .1);
}

// 指定`border-color`

div {
    .le_border(@color: #ff0000);
}

result:

div {
    color: 1px solid #ff0000;
}
```

### .le_flex

flex 代表 `flex`，默认参数为`display: flex;`。

**Example**

```javascript
// 默认不传参

div {
    .le_flex();
}

result:

div {
    display: flex;
}

// 传入一个参数 为`flex-direction`

div {
    .le_flex(column);
}

result:

div {
    display: flex;
    flex-direction: column;
}

// 传入两个参数 为`flex-flow`
div {
    .le_flex(row; wrap);
}

result:

div {
    display: flex;
    flex-flow: row wrap;
}

// 传入三个参数 为`flex-flow justify-content`

div {
    .le_flex(column; nowrap; center);
}

result:

div {
    display: flex;
    flex-flow: column nowrap;
    justify-content: center;
}

// 传入四个参数 为`flex-flow justify-content align-items`

div {
    .le_flex(row; wrap; flex-start; center);
}

result:

div {
    display: flex;
    flex-flow: row wrap;
    justify-content: flex-start;
    align-items: center;
}
```

### .le_relative

relative 代表 `position: relative`，默认参数为`position: relative`。

**Example**

```javascript
// 默认不传参
div {
 .le_relative();
}

result:

div {
    position: relative;
}

// 传入一个参数 `top`

div {
    .le_relative(10px);
}

result:

div {
    position: relative;
    top: 10px;
}

// 传入两个参数 `top; right`

    // 两个参数全传入
div {
    .le_relative(20px; 50px);
}

result:

div {
    position: relative;
    top: 20px;
    right: 50px;
}

    // 只传入第二个参数 `right`
    // 第一个参数为`none`

div {
    .le_relative(none; 10px);
}

result:

div {
    position: relative;
    right: 10px;
}

// 传入三个参数 中间不穿参数为`none`即可

div {
    .le_relative(10px; 11px; 12px);
}

result:

div {
    position: relative;
    top: 10px;
    right: 11px;
    bottom: 12px;
}

// 传入四个参数 中间不穿参数为`none`即可

div {
    .le_relative(10px; 11px; 12px; 13px);
}

result:

div {
    position: relative;
    top: 10px;
    right: 11px;
    bottom: 12px;
    left: 13px;
}
```

### .le_relative_tl

relative_tl 代表 `position: relative; top; left;`, 没有默认参数。**不推荐第一个参数传入`none`，如果这样不如使用`le_relative(none; 10px)`**

**Example**

```javascript
// 传入两个参数 `top` `left`


div {
    .le_relative_tl(10px; 11px);
}

result:

div {
    position: relative;
    top: 10px;
    left: 11px;
}
```

### .le_relative_zero

relative_zero 代表 `position: relative; top; right; bottom ; left，默认参数都为 0。

**Example**

```javascript
// 不用传入参数
div {
    .le_relative_zero();
}

result:

div {
position: relative;
    top: 0;
    right: 0;
    bottom: 0;
    left: 0;
}
```
