#Update CSS Variables with JavaScript
A simple photo filter app that lets the user manipulate several different CSS variables with range input sliders and a color picker. 

* **declaring CSS variables** on the `:root` element so they update everywhere. The syntax for declaring variables is similar to SCSS, instead of `$`, the variable name begins with `--`.

```css
  :root {
    --base: #FC4756;
    --spacing: 10px;
    --blur: 10px;
  }
```

The syntax for using them is a little weird. The variable name goes inside of a `var()`. It looks like a function called `var` that takes the variable name as an arguement. Use that as the value to any CSS selector, and it should evaluate to the value you gave it at the `:root`.

I am using these values on the image element as the initial state, so that is what you will see at first. Since I'm passing `--base` to `blur()`, it is blurred by `10px` Pull the Blur slider to the left, and the image will come into focus.

```css
  img {
    padding: var(--spacing);
    background: var(--base);
    filter: blur(var(--blur));
  }
```

What we want to do next is chage that value on the fly, with the input's here.

___

* `this.dataset`
* appending a suffix with the `data` attribute
* `NodeList` vs. `Array`
* listening for `change` and `mousemove` events on all the inputs
* `document.documentElement.style.setProperty`
