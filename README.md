# Schedule Template for Hugo

## DEVELOPMENT / SETUP

* `Ubuntu 16.04`

```bash
hugo version
Hugo Static Site Generator v0.53/extended linux/amd64 BuildDate: 2018-12-24T12:58:46Z

```

## BACKGROUND

I have been working with Hugo for a while now and experiment by starting projects from `scratch` and building test cases.
This is one such experiment.

My goal here is to integrate this [Codyhouse Schedule  Template](https://codyhouse.co/gem/schedule-template) into future Hugo projects.  This is a free (MIT) Template that you can download and open `index.html` in a browser to see what it is suppose to look like.  Select an event to get a pop-up that displays `event-info`.

## APPROACH

Here is my [Github Repo showing my attempt](https://github.com/theadle/cal).

First I created a new hugo project:

```bash
hugo new site cal
```

[Original Method] ~~Then I parsed out `Codyhouse-Template` by putting all the **HTML** files under `/layouts` and the remaining files under `/static`.~~

```bash
.
├── archetypes
│   └── default.md
├── config.toml
├── content
├── layouts
│   ├── event-abs-circuit.html
│   ├── event-restorative-yoga.html
│   ├── event-rowing-workout.html
│   ├── event-yoga-1.html
│   └── index.html
├── README.md
├── resources
│   └── _gen
│       ├── assets
│       └── images
└── static
    ├── css
    │   ├── reset.css
    │   └── style.css
    ├── js
    │   ├── jquery-3.0.0.min.js
    │   ├── main.js
    │   └── modernizr.js
    ├── partials
    │   ├── _layout.scss
    │   ├── _mixins.scss
    │   └── _variables.scss
    └── scss
        └── style.scss
```

## RESULT OF MY ATTEMPT

`[Fixed: Jan 9, 2019]`
~~This approach mostly works except the modal window will not display the `"event-info"`.`~~  

**By moving the "`event-*.html`" files from /layouts to `/static`, the modal boxes will now display correctly.**

```bash
.
├── archetypes
│   └── default.md
├── config.toml
├── content
│   └── empty.md
├── layouts
│   └── index.html
├── my-modal.png
├── normal_modal.png
├── README.md
├── resources
│   └── _gen
│       ├── assets
│       └── images
├── static
│   ├── css
│   │   ├── reset.css
│   │   └── style.css
│   ├── event-abs-circuit.html
│   ├── event-restorative-yoga.html
│   ├── event-rowing-workout.html
│   ├── event-yoga-1.html
│   ├── js
│   │   ├── jquery-3.0.0.min.js
│   │   ├── main.js
│   │   └── modernizr.js
│   ├── partials
│   │   ├── _layout.scss
│   │   ├── _mixins.scss
│   │   └── _variables.scss
│   └── scss
│       └── style.scss
└── top.png

```

~~## QUESTIONS~~

~~1. Any general advice on how one would port this so you could essentially drop this into an existing Hugo project?  I doubt my approach is optimal.~~

~~2. If you download and run my Github project, you will quickly see my problem.  I have tried to move those style sheets and javascript files around into other Hugo folders and also change path's inside of the index.html.  Can anyone offer advice as to why the event-info doesn't show up in the modal box?~~

### Attribution

Thanks to `pointyfar` at [Hugo Support](https://discourse.gohugo.io/) for support.  

**TOPIC:**  `Advice needed porting specific html/css based template`

## SCREENSHOTS

* This is an example of what you initially see:

![Main Screen](top.png?raw=true "Main Screen")

* This is what I am trying to achieve:

![Normal Modal](normal_modal.png?raw=true "Normal Modal Content")

* `[Fixed: Jan 9, 2019]` ~~This is my result showing the missing content~~

![My Modal](my-modal.png?raw=true "Missing Modal Content")
