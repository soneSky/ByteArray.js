# ByteArray.js

#### Write and read bytes in Javascript using ByteArray.js that is equivalent to Actionscript 3's ByteArray.

#### AMF3 & AMF0 object serialization support
This library has been compared with Actionscript 3's own writeObject (Both AMF3 & AMF0) and is validated as 99% accurate. I also compared it with [ham-amf](https://www.npmjs.com/package/ham-amf) which is a great AMF3 library. We got the same results.

ByteArray.js:
age30alias    Mike    name    Mike
ham-amf:
age30alias    Mike    name

Example test:

```
package {
	import flash.display.Sprite;
	import flash.utils.ByteArray;
	
	public class Main extends Sprite {
		
		public function Main() {
			var a:ByteArray = new ByteArray();
			a.objectEncoding = 0;
			a.writeObject({name:'Mike'});
			var s:String = "";
			for (var i:uint = 0; i < a.length; i++) {
				s+=("0"+a[i].toString(16)).substr(-2,2);
			}
			trace(s);
		}
	}
}
```

## Installation

**npm i parse5 xmlserializer**