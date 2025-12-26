# Typora Print Themes

Print-optimized Typora themes for minimal paper usage and professional output.

> **Note:** Designed and tested on macOS. Not fully tested, but should work for Windows/Linux.

## Themes

| Theme | File | Paper Format |
|-------|------|--------------|
| Print | `print.css` | DIN A4 (210 × 297 mm) |
| Print Letter | `print-letter.css` | US Letter (8.5" × 11") |

## Features

- **Compact font size** (10.5px/9pt) for minimal paper usage
- **Page break control**: Headings stay with following content
- **Orphan/widow control**: No single lines at page start/end
- **ASCII diagram optimized**: Very small monospace font (6pt) for wide code blocks
- **No border/background** on code blocks for clean printing
- **Minimal page margins** (10mm) for maximum text width
- **Cross-platform**: Specific styles for macOS, Windows, and Linux

## Installation

Copy theme files to the Typora themes folder:

**macOS:**
```bash
cp print.css print-letter.css ~/Library/Application\ Support/abnerworks.Typora/themes/
```

**Windows:**
```
%APPDATA%\Typora\themes\
```

**Linux:**
```
~/.config/Typora/themes/
```

Restart Typora after copying. The themes will appear under `Themes` → `Print` or `Print Letter`.

## Customization

The themes use CSS variables for easy customization:

```css
:root {
    /* Colors */
    --text-color: #1a1a1a;
    --heading-color: #000000;
    --link-color: #0066cc;

    /* Spacing */
    --paragraph-spacing: 0.5em;
    --heading-margin-top: 1em;
    --list-indent: 1.5em;

    /* Fonts */
    --font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", ...;
    --mono-font: "SF Mono", "Fira Code", Menlo, Consolas, ...;
}
```

### Adjusting Font Size

**Screen:**
```css
html {
    font-size: 10.5px; /* Increase for larger font */
}
```

**Print:**
```css
@media print {
    html {
        font-size: 9pt; /* Increase for larger font */
    }
}
```

**Code blocks (print):**
```css
@media print {
    pre, .md-fences {
        font-size: 6pt !important; /* Increase if ASCII diagrams are too small */
    }
}
```

## Page Break Behavior

The themes prevent unwanted page breaks:

- Headings stay with following paragraph/table
- Code blocks are not split
- Tables are not split (when possible)
- Minimum 3 lines at page end (orphans) and page start (widows)

## Platform Compatibility

The themes include platform-specific styles:

### macOS
- `.mac-seamless-mode` - Seamless window mode
- `.mac-os` - Caret color (AccentColor)
- `.html-for-mac` - Context menu

### Windows
- `.os-windows` - Source mode font
- `.os-windows-7` - Font weight fix for bold text

### Linux
- `.typora-node` - Sidebar, scrollbar, file list, task lists
- Webkit scrollbar styling

## License

MIT License


Copyright (c) 2025 Christian Schwarzenberger

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
