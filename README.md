jquery.topics

A jQuery plugin that implements a lightweight Publish/Subscribe mechanism.

# About
To do.

# Usage
## Example
Subscribe a function to `myTopic`:
>```javascript
var myFunction = function( data ) {
    // do something with 'data'
    alert( data );
};
var topic = $.Topic("myTopic").subscribe( myFunction );
```

Publish something a topic:
>```javascript
$.Topic("myTopic").publish( something );
// or
topic.publish( something );
```

Unsubscribe a function:
>```javascript
$.Topic("myTopic").unsubscribe( myFunction );
```

Check if the topic is already been used:
Unsubscribe `myFunction`:
>```javascript
alert( $.Topic("myTopic").used() );
```

Remove all subscriptions from a topic:
>```javascript
$.Topic("myTopic").empty();
```

## Code
>
```javascript
$.Topic( id, flags )
```
>> Returns an either new or existent `Topic` object depending on `id`.
- `id (String|Integer)`: The name of the target topic. If omitted, a one-way
topic is created (which is not very useful).
- `flags (String)`: The flags for the internally used `$.Callbacks()` object
passed in a string of space-separated values. They are only used when a topic is
newly created. For more details on the flags and `$.Callbacks()`, see
http://api.jquery.com/jQuery.Callbacks/.

### The `Topic` object
> The following wrapper functions around the internal `$.Callbacks` object are
provided by a `Topic`:  
- `subscribe >> $.Callbacks().add`
- `unsubscribe >> $.Callbacks().remove`
- `publish >> $.Callbacks().fire`
- `used >> $.Callbacks().fired`
- `empty >> $.Callbacks().empty`

> For details on this methods, see
http://api.jquery.com/category/callbacks-object/.

# Development

- Source hosted at [GitHub](https://github.com/riga/jquery.topics)
- Report issues, questions, feature requests on
[GitHub Issues](https://github.com/riga/jquery.topics/issues)

# Authors

Marcel R. ([riga](https://github.com/riga))