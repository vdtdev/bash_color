# Bash Coloring

Module that allows generating/displaying strings containing multiple bash colors

## Overview

### Methods

Module has two public methods: `colorize` and `cprint`.

- `colorize` - returns input string modified to replace color id codes with bash color code strings

- `cprint` - Wraps `print`, displaying results from `colorize`

### Colors

#### Defining

Available colors are defined in Hashes structured like so:

```ruby
colors = {
    red: { # Custom name of color
        fg: 31, # foreground color
        bg: 0 # background color
    }
}
```

The 'default' color (used to reset back to the normal color) can be overridden by including a color with the name `default`.

#### Using

Within your input string, you can specify a color to change all following text to by including its id code. The ID code consists of the symbol character (defaults to `%`) followed by the color's custom name. E.g. for 'red', `'Some text %redThis is red'`.

The default/reset color's ID code is the symbol character twice (e.g. `%%`)

#### Example

```ruby

colors = {
    red: { fg: 31, bg: 0 },
    white: { fg: 1, bg: 0 },
    blue: { fg: 34, bg: 0 }
}

cprint(
    "Good old %redRed%%, %whiteWhite%% and %blueBlue%%!", colors
)
```

Prints:
- Good old <span style="color: red">Red</span>, <span style="color: gray">White</span>, and <span style="color: blue">Blue</span>!


## License

Released under [MIT](https://opensource.org/licenses/MIT) license