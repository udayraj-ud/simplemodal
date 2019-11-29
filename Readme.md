# Why this fork?

TLDR; To solve the issue mentioned here https://stackoverflow.com/questions/23251036/uncaught-typeerror-cannot-read-property-focus-of-undefined

There's an annoying console error coming due to this snippet of code.

```
// focus on dialog or the first visible/enabled input element
       var input = $(':input:enabled:visible:' + p, s.d.wrap);
       setTimeout(function () {
           input.length > 0 ? input.focus() : s.d.wrap.focus();
    }, 10);
```

And as per the requirement focusing on the dialogue is not a must-have. So this fork has changed it to the following -
```

// focus on dialog or the first visible/enabled input element
	var input = $(':input:enabled:visible:' + p, s.d.wrap);
	setTimeout(function () {
		input.length > 0 ? input.focus() : (s.d.wrap ? s.d.wrap.focus() : null);
	}, 10);

```


## How to use?
Update bower.json with following line -
```
"jquery.simplemodal": "udayraj-ud/simplemodal#1.4.5.1",
```
Run bower install.


< Continuing with existing readme below >

> **NOTICE**
 
> I am no longer able to actively support or maintain SimpleModal. If you would like to become a contributor, drop me a line. Otherwise, I will be removing this project in the near future.


[SimpleModal](http://simplemodal.com/) - A modal dialog framework for jQuery
================================

* [Documentation](http://www.ericmmartin.com/projects/simplemodal/)
* [Demos](http://www.ericmmartin.com/projects/simplemodal-demos/)
* [Downloads](http://code.google.com/p/simplemodal/downloads/list)

Questions?
--------
For questions, please post them on [stackoverflow](http://stackoverflow.com/) and tag the question with "simplemodal".

For issues or feature requests, please enter them on the [issues](https://github.com/ericmmartin/simplemodal/issues) page. 


Twitter
-------
* [@ericmmartin](http://twitter.com/ericmmartin/)
* [@simplemodal](http://twitter.com/simplemodal/)


Donate
------
[Donations](http://www.ericmmartin.com/donate/) are greatly appreciated.


Building SimpleModal
--------------------

* Make sure that you have [Java](http://java.sun.com/javase/downloads/index.jsp) and [Ant](http://ant.apache.org/bindownload.cgi) installed.

In the main directory of the distribution (the one that this file is in), type the following to make all versions of SimpleModal:

    ant

The standard, uncompressed, SimpleModal code.  
Makes: `./dist/jquery.simplemodal.VERSION.js`

    ant full

Finally, you can remove all the built files using the command:
  
    ant clean
