P标签是默认是自动换行的，因此设置好宽度之后，能够较好的实现效果，但是最近的项目中发现，使用ajax加载数据之后，p标签内的内容没有换行，导致布局错乱，于是尝试着使用换行样式，虽然解决了问题，但是并没有发现本质原因，本质在于，我当时获取的数据是一长串的数字，浏览器应该是对数字和英文单词处理方式相近，不会截断。 
先给出各种方式，再具体介绍每一个属性。 
强制不换行 
p { white-space:nowrap; }

自动换行 
p { word-wrap:break-word; }

强制英文单词断行 
p { word-break:break-all; }

*注意：设置强制将英文单词断行，需要将行内元素设置为块级元素。

超出显示省略号 
p{text-overflow:ellipsis;overflow:hidden;}

white-space: normal|pre|nowrap|pre-wrap|pre-line|inherit; 
white-space 属性设置如何处理元素内的空白 
normal 默认。空白会被浏览器忽略。 
pre 空白会被浏览器保留。其行为方式类似 HTML 中的 pre 标签。 
nowrap 文本不会换行，文本会在在同一行上继续，直到遇到 br 标签为止。 
pre-wrap 保留空白符序列，但是正常地进行换行。 
pre-line 合并空白符序列，但是保留换行符。 
inherit 规定应该从父元素继承 white-space 属性的值。

word-wrap: normal|break-word; 
word-wrap 属性用来标明是否允许浏览器在单词内进行断句，这是为了防止当一个字符串太长而找不到它的自然断句点时产生溢出现象。 
normal: 只在允许的断字点换行(浏览器保持默认处理) 
break-word:在长单词或URL地址内部进行换行 
word-break: normal|break-all|keep-all;

word-break 属性用来标明怎么样进行单词内的断句。 
normal：使用浏览器默认的换行规则。 
break-all:允许再单词内换行 
keep-all:只能在半角空格或连字符处换行