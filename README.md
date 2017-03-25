# jQuery Template
Incredibly simple and yet powerful javascript templating system written by a lazy programmer so he can stay lazy and yet be able to effortlessly build and manage UIs.

## Features
- [x] Supports nested templates
- [x] You can apply template multiple times to update only some values
- [x] Support for conditional classes
- [x] Support for conditional attributes (e.g. check checkbox if value is true)
- [x] Support for conditional inserting values into strings in both attributes and text contents

## Audience

It is meant for programmers dynamically building UIs on front end
using AJAX and static HTML templates.  You can keep your code clean
while allowing designers to edit HTML templates without breaking your
Javascript. Allows easy maintanance and updates of UIs.

## Example

Original HTML.

```html
<div id="example">
  <div>
      Visit <a z-var="url @href, name ., name @title" title="Home of ${name}"></a>
  </div>
  <small z-var="url ., name .">
      The code above inserts "${url}" into "href" attribute,
      name into sentance in "title" attribute and
      "${name}" as plain text of the link.
  </small>
</div>
```

Applying template.

```javascript
$("#example").template({
    'url': 'http://example.com',
    'name': 'Example Co.'
});
```

Resulting HTML.

```html
<div id="example">
  <div>
      Visit <a z-var="url @href, name ., name @title" title="Home of Example Co." href="http://example.com">Example Co.</a>
  </div>
  <small z-var="url ., name .">
      The code above inserts "http://example.com" into "href" attribute,
      name into sentance in "title" attribute and
      "Example Co." as plain text of the link.
  </small>
</div>
```

For more advanced examples and explanations see file <code>tutorial/index.html</code>.
