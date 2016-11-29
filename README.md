# Introduction

This is plugin for Octopress that will obfuscate an email address by adding
an email tag to markdown.

## Usage

```
{% email address="test@example.com" style="<link|text>" %}
```

## Installation

Copy 'email.rb' to your 'plugins directory'

## How it Works

The plugin will render a small javascript block that performs an inline document.write. It renders an email address with some characters encoded and in reverse order. It then uses CSS to re-reverse the email to display to the user.

For example this markdown:

```
Please email me at: {% email address="test@example.com" style="link" %}
```

will render this html:

```html
Please email me at: 
<script type="text/javascript">
document.write('<a style="unicode-bidi:bidi-override; direction: rtl;"href="&#109;&#97;&#105;&#108;&#116;&#111;&#58;test&#64;example&#46;com">moc&#46;elpmaxe&#64;tset</a>');
</script> 
```
