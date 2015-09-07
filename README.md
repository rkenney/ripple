# ripple

A Jquery Material Design Style Ripple Effect

This plugin will apply the material desgin style ripple to an element, there is no configuration needed, just add data-ripple="" to a link or button etc. and the script will detect the background color of the button and lighten or darken (if the color is to light to lighten) the color and show the ripple when clicked. If the button is transparent the script searches the elments parents for a background color to use, if nothing is found the inkDefaultColor from  options  will be used.
The script is setup so that you can swap out functions with your own and such..

I started this script based off of an example i found that was on sitepoint.

## Requirements
* [jQuery](http://jquery.com/) 1.11.2+

## Install
just add the ripple.css in the head of your document.
And add the ripple.js before the closing body tag.

## Example
The way i currently have it setup is to automatically apply to any elements with data-ripple="" appled to them.
```html
<a class="btn btn-success" data-ripple="">Some Link</a>
```

you can specify a color you want to use as the ripple by putting a color in the data attr like so:
```html
<a class="btn btn-success" data-ripple="#000000">Some Link</a>
```
By adding the color the script will now show the ripple as black instead of detecting the links bg color and lighting/darkening it.

you can specify a target elment that has a bg-color you want to use as the ripple by setting the data-ripple attr to "" and adding the data attr of data-ripple-getcolorfromid="#somid" like so:
```html
<a class="btn btn-success" data-ripple="" data-ripple-getcolorfromid="#elmentThatHasBgcolorToUse">Some Link</a>
```
By adding the ripple-getcolorfromid the script will now show the ripple as the color of that taget elment of #elmentThatHasBgcolorToUse instead of detecting the links bg color and lighting/darkening it.

## Default Options 
```js
$.fn.rippleEffect.defaults = {
        inkContainerClass: "ripple",
        inkClass: "ink",
        inkDefaultColor: "#F0F0F0", //falback color to use if using parent traversing to get a bg color.
          //to avoid a global default you can add data-ripple="#ff00ff" to the element that will have the ripple and that color will be used.
        inkColor: "", //the ink color you want the element to use, this will override any bg checks for element and parent traversing, but if the element has data-ripple="#fff" the #fff will be used above all else
       
        //if you append to a parent item that item will have the ripple span and it may block access to links and child elements
        //all i had to do was give any of the children of the appended element a z-index of 1, some i had to set position to relative.
        appendInkTo: "" //append ink to a diffrent element. will find closest element matching. i.e. .panel-body and ink will be aplied to  the panel-body parent elment of the selector.
    };
```

  
