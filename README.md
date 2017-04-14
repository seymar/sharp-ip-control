# sharp-virtual-remote
A Node.JS module that controls a Sharp TV with virtual remote option.

## Usage
```javascript
var tv = new SharpVirtualRemote()
.on('available', function() {
  this.send('menu');
});
```

The module will find the TV on the network by broadcasting a query packet over UDP. The TV responds with some information like the port to be connected to.
When the response from the TV has been received the module emits an `available` event.

A fixed IP and custom port can be given, the port defaults to 4660 so is optional.
```javascript
var tv = new SharpVirtualRemote('192.168.0.111', 1234)
.on('available', function() {
  this.send('menu');
});
```

## Command Line Interface
`node sharp-virtual-remote <command>``

Where `<command>` is one of the commands in [commands.json](./commands.json)