### Less CSS ###

1. # What is Less

 Less -> css + preprocessor += (variables, mixins, functions) see example in Section 1.1

2. # How LESS works, runs 

 LESS need 3rd party tools that help you to compile and watch changes, LESS to CSS.Less runs inside Node, browser and Rhino (). See More in Section 2.1

3. # Purpose LESS

 to maintainable, themable and extendable

Section 1.1

What is Preprocessor  

# variables means vairable 
(e.g)

@color = #ffffff;

p {
	color: @color;
	text-align: center;
}

# Functions means function without parameters

.border {
	border-color: 1px solid #e3e3e3;
}

.box-container #box-1, #box-2 {
	color: #000;
	.border;
}

Section 2.1 

1. Using less script easiest ways

# standard output 

lessc style.less style.css

# minified Css 

lessc --clean-css style.less style.min.css

# compile by node

var less = require('less');

less.render('.class { width: (1+1) }', (e, output) => {
	console.log(output.css)
})

result: 

.class {
	width: 2;
}

Configuration 

var less = require('less');

less.render('.class { width: (1 + 1) }',
    {
      paths: ['.', './lib'],  // Specify search paths for @import directives
      filename: 'style.less', // Specify a filename, for better error messages
    },
    function (e, output) {
       console.log(output.css);
    });







