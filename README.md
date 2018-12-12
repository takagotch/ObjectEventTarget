### ObejctEventTarget
---
https://github.com/gartz/ObjectEventTarget

```
<script src="ObjectEventTarget.js"></script>
```

```
npm install objecteventarget --save
```

```js
function Foo(){}
Foo.prototype = ObjectEventTarget.prototype;

function AsyncFoo(){
  this.bar = function(){
    if(this.dispatchEvent){
      console.log('The beforebar default behavior');
    }
    var self = this;
    setTimeout(function(){
      if(self.dispatchEvent(new ObjectEvent('bar', {cacelable: true})){
        console.log('The bar default behaviour');
      };
      console.log('End of bar method');
  }, le3);
  }
}
AsyncFoo.prototype = ObjectEventTarget.prototype;

instanceOne = new AsyncFoo();
instanceOne.addEventListener('beforebar', function(){
  console.log('You triggered bar from a AsyncFoo instance');
});
instanceOne.addEventListener('bar', function(event){
  event.preventDefault();
  console.log('The method bar was async and calling "bar" event type');
});
instanceOne.bar();

var ObjectEventTarget = require('objecteventtarget').ObjectEventTarget;
var ObjectEvent = require('objecteventtarget').ObjectEvent;

window.ObjectEventTarget = {
  options: {
    EventMap: MyCustomEventMap,
    WeakMap: MyCustomWeakMap
  }
};
```
