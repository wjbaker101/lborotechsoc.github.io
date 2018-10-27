# Loughborough Technology Society Website

[https://loughborough.tech](https://www.loughborough.tech)

Our website is built using [Jekyll](https://jekyllrb.com/) and hosted by Github Pages.

## How to Edit the Website

1. Install Ruby (with Devkit):
> https://www.ruby-lang.org/en/downloads/

2. Install Jekyll. Run the command:
> `gem install jekyll bundler`

4. Download the source code. Run the command:
> `git clone https://github.com/LboroTechSoc/lborotechsoc.github.io.git`

5. Run the website locally, at http://localhost:4000.
   
   Open a terminal in the website folder and run:
> `bundle exec jekyll serve`

6. Merge changes into the master branch of the `lborotechsoc.github.io` repository.\
   The website will update with your changes after a few moments.

## Webpages

Webpages are located in the `/pages` directory.

```
---
layout: default
title: ... # Title of the page (displayed in the browser tab)
permalink: ... # URL of the page
---
```

## Stucture

Page structures of the website can be found in `_layouts`.

This will contain html files which define what the pages should look like.

Currently there are 3 layouts:

- `default` - The default layout which all pages should inherit.
- `code-and-chill` - Layout for Code and Chill session pages. Inherits default.
- `workshop` - Layout for workshop pages. Inherits default.

### Workshops

Workshop pages inherit the `workshop` layout, and are found in the `/pages/workshops` directory.

At the top of each workshop file this front-matter should be defined:

```yaml
---
layout: workshop
title: ... # Title of the workshop
image: ... # Filename of the image to use*
categories: [ 'workshop' ] # Category so other pages can list workshops
eventDate: ... # Date of the workshop (look at previous dates for the layout)
permalink: /workshop/... # URL of the workshop
description: >
    ... # Description of the workshop, displayed in the box at the top of the page
        # This is written as HTML
---
```

*\* Images will be looked for within the `/resources/technologies`* folder.

### Code and Chill Sessions

Code and Chill session pages inherit the `code-and-chill` layout, and are found in the `/pages/code-and-chill` directory.

At the top of each session file this front-matter should be defined:

```yaml
---
layout: code-and-chill
title:  ... # Title to be displayed in the webpage's tab
heading: ... # Heading of the page (usually the name and number of the session)
categories: [ 'code-and-chill' ] # Category so other pages can list sessions
eventDate: ... # Date of the session (look at previous dates for the layout)
permalink: /session/... # URL of the session
beginners_title: ... # Title of the beginners session
beginners_image: ... # Filename of the beginners session image*
advanced_title: ... # Title of the advanced session
advanced_image: ... # Filename of the advanced session image*
---
```

*\* Images will be looked for within the `/resources/technologies`* folder.

### Components

The content of pages has been split up into individual files to allows them to be included separately. You can find these in the `/_includes` directory.

When adding one of the files into a page, use:
> `{% include file_name %}`

## Styling

Styles are written in [SASS](https://sass-lang.com/).

The `/styles` directory stores the files which are to be compiled into CSS and referenced in webpages.

Partial files can be found in `/_sass`, which contain individual styles.

## Images

Images can be found in the `/resources/images` directory.

If using any LSU media, make sure to abide by the LSU branch guidelines, which can be found [here](https://www.lsu.co.uk/services/marketingcomms/brand/).