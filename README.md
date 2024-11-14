# Dynamic-creation-and-removal-of-SetInterval
Dynamically create elements with setinterval instances and delete both when no longer required. 

In HTML  I needed the posibility to create Div elements to show content, but then that content needed to be refreshed regularly.

This is a part of the solution that shows the Javascript used to create the elements and the coresponding timer events and the creation of the function to load tha data asyncronously.

If an element in a checkbox is selected the related svg image is loaded and refrehed according to a parameter in the checkbox

<input id="Graph1" type="checkbox" checked onclick="loadIt(this, 1000)" value="sGraph">
  <label for="Graph1">Seconds</label>

the load function checks if the item is active (e.g. loaded) and if actif will removes it otherwise create it by calling another function.

Timers are created as follows:
```
 const d = document.createElement("div"); // new div
  d.setAttribute("id", value); //assign id
  d.setAttribute("class", value); //assign class
 const currentDiv = document.getElementById("images"); /get container parent
 currentDiv.appendChild(d); //add child
 var attrib = document.createAttribute("interval"); // create new attribute type interval
  attrib.value = setInterval(reLoad.bind(null,value),time); //set the attribute. value  interval,  passing the function (reLoad) and parameters to use for reloading the item
  d.setAttributeNode(attrib); attache new attribute to new div element
  
window.onload = function(){loadIt(document.getElementById("Graph1"),1000)}; // will load the first image at start up  
```
