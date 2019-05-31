Drop down terminal forked from `zzrough/gs-extensions-drop-down-terminal`, 
add feature: 
  auto hide terminal when loss focus;
  hide when press right Alt.
  open shortcut use `Alt-T` recommended.

`terminal.js`
``` javascript
            // add by zhb
361	        window.connect("focus-out-event", function() { window.hide(); return true; });
362	        window.connect("key-press-event", (widget, event, user_data) => {
363		          let [success, keyval] = event.get_keyval(); // integer
364		          let keyname = Gdk.keyval_name(keyval); // string keyname
365	            if (keyname === "Alt_R") { window.hide(); }
366	            //if (keyname === "Escape") { window.hide(); }
367		      });
```
It is not a good idea, just make do with it!
