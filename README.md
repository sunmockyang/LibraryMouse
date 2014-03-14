LibraryMouse
============

JavaScript library to handle mouse events and calculate mouse coordinates relative to a HTML element.

Online demo: http://sunmock.com/projects/LibraryMouse/demo/

##Events

The types of events that can be used on an element are:

*"click", "leftclick", "rightclick"
"mousedown", "leftmousedown", "middlemousedown", "rightmousedown"
"mouseup", "leftmouseup", "middlemouseup", "rightmouseup"
"doubleclick"
"mousewheel"
"mouseover", "mouseout", "mousemove"*

##Usage
###Initialization
```javascript
var obj = new LibraryMouse(element);
```
Initialize the library and give it the element you'd like to bind event listeners to.

###Adding/Removing Events
```javascript
obj.addEventListener(eventType, callback);
```
Used to bind an event type mentioned above to a callback.

```javascript
obj.removeEventListener(eventType);
```
Used to remove an event type mentioned above that has already been bound.

```javascript
obj.addEventContainer(obj);
```
You can pass in an object that has attribute functions with the same names as the event types and it will automatically bind them to their respective events. (ie. obj.doubleclick will be bound to the "doubleclick" callback).

###Manual update
```javascript
obj.update();
```
Manually refresh the mouse coordinates. Is automatically called whenever there is an event.

###Get Mouse Coordinates/Status
```javascript
obj.x;
obj.y;
```
The mouse coordinates relative to the element position. Updates with every event fired.

```javascript
obj.mouseover;
```
Whether or not the mouse is over the bound element. Needs "mouseover", "mouseout" events to be bound in order to function properly. Return a boolean.

```javascript
obj.clicked;
obj.LClicked;
obj.MClicked;
obj.RClicked;
```
Whether or not the mouse buttons are currently clicked. Needs at least mousedown, mouseup/mouseclick events to be bound in order to function properly. LClicked will only be toggled if the corresponding left mouse button events are bound, same with RClicked, and MClicked (middle mouse). Return a boolean.

```javascript
obj.wheelDir;
```
The last direction the mousewheel had turned. Returns -1 and 1. Needs "mousewheel" event to be bound in order to function properly.
