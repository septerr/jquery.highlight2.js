Requirements
=============
Requires jquery.
To use, include jquery.highlight2.js after the jquery include statement.

Credit
=======
jquery.highlight2.js is based on [Bartek Szopka's](https://github.com/bartaz/sandbox.js).
jquery.highlight2.js enhances the original plugin by adding an option for the wrapping element's attributes.

Usage
=======
You can still use all the jquery.highlight.js options - element, className, caseSensitive, wordsOnly.
In addition you can use the other_attrs option. This option should be used to specify attributes ( in {key: value} fashion) to be applied to the wrapper element.

For instance if you wanted to wrap every occurrence of the word 'Lorem' with an anchor tag that has href="#" and title="anchor yeah!", you would specify this:

 $('.content').highlight('Lorem', {element:'a', className:'awesome-tip',<br />
         other_attrs:{href: '#',<br />
             title: 'anchor yeah!'<br />
             }<br />
         }<br />
     );<br />

The JSON provided for the other_attrs parameter is applied to the wrapping element using jquery's attr method - http://api.jquery.com/attr/#attr2.
This method can take literals as well as functions for the attribute values. If a function is provided, the setting of the attribute value is delegated to the function.
So, in the prior example if you wanted to add a class 'foo' to the anchor tag without clobbering the 'awesome-tip' class, you would use a function:

  $('.content').highlight('Lorem', {element:'a', className:'awesome-tip',<br />
           other_attrs:{href: '#',<br />
               title: 'anchor yeah!',<br />
               class = function(index, attr){$(this).addClass('awesome-class')}<br />
               }
           }                                                                         <br />
       });<br />

The function is applied after the className attribute has already been applied. The function is supplied with two arguments. An index of the element's position in the jquery collection and existing value of the attribute.
The index in our case will always be 0.

Feel free to [tweet](twitter.com/septerr) me a comment.
