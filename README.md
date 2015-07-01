#Responsive Web Design

- Discuss why there's a need for responsive design

---

###Why RWD (Responsive Web Design)
These days it is hard to find someone who doesn’t own a mobile device, or multiple, connected to the Internet. In the UK there are more mobile phones than people, and should trends continue mobile Internet usage will surpass that of desktop Internet usage within the year.

The responsive web design term itself was coined, and largely developed, by Ethan Marcotte.

---

###Responsive vs. Mobile

Responsive generally means to react quickly and positively to any change, while adaptive means to be easily modified for a new purpose or situation, such as change. 

Mobile, on the other hand, generally means to build a separate website commonly on a new domain solely for mobile users. While this does occasionally have it’s place, it normally isn’t a great idea. Mobile websites can be extremely light but they do come with the dependencies of a new code base and browser sniffing, all of which can become an obstacle for both developers and users.

---

###3 components of RWD

1. Flexible Layouts
2. Media queries
3. Flexible media

---

###Flexible Layout

Formula for flexible grid is taking width of an element and dividing by the width of it's parent element

	target / content = result

---


###Fixed Grid demo
`index.html`

```
<div class="container">
  <section>...</section>
  <aside>...</aside>
</div>
```

`css/styles.css`

```

.container {
  width: 538px;
}
section,
aside {
  margin: 10px;
}
section {
  float: left;
  width: 340px;
}
aside {
  float: right;
  width: 158px;
}
```

###Flexible Grid Demo

`index.html`

```
<h1>100% Wide Container</h1>

<div class="container">
  <section>Section</section>
  <aside>Aside</aside>
</div>

<h1>75% Wide Container</h1>

<div class="container container-75">
  <section>Section</section>
  <aside>Aside</aside>
</div>

<h1>50% Wide Container</h1>

<div class="container container-50">
  <section>Section</section>
  <aside>Aside</aside>
</div>
```

`style.css`

```
h1 {
  color: #9799a7;
  font-size: 14px;
  font-weight: bold;
  margin-bottom: 6px;
}
.container:before,
.container:after {
  content: "";
  display: table;
}
.container:after {
  clear: both;
}
.container {
  background: #eaeaed;
  margin-bottom: 24px;
  *zoom: 1;
}
.container-75 {
  width: 75%;
}
.container-50 {
  margin-bottom: 0;
  width: 50%;
}
.container,
section,
aside {
  border-radius: 6px;
}
section,
aside {
  background: #2db34a;
  color: #fff;
  margin: 1.858736059%;
  padding: 20px 0;
  text-align: center;
}
section {
  float: left;
  width: 63.197026%;
}
aside {
  float: right;
  width: 29.3680297%;
}
```
###Media queries

3 ways to use media queries are: 

```
<!-- Separate CSS File -->
<link href="styles.css" rel="stylesheet" media="all and (max-width: 1024px)">

/* @media Rule */
@media all and (max-width: 1024px) {...}

/* @import Rule */
@import url(styles.css) all and (max-width: 1024px) {...}
```

###Logical operators in media queries

Logical operators in media queries help build powerful expressions. There are three different logical operators available for use within media queries, including and, not, and only.

Using the and logical operator within a media query allows an extra condition to be added, making sure that a browser or devices does both a, b, c, and so forth. 

```
@media all and (min-width: 800px) and (max-width: 1024px) {...}
```

The not logical operator negates the query, specifying any query but the one identified. 

```
@media not screen and (color) {...}
```

The only logical operator is a new operator and is not recognized by user agents using the HTML4 algorithm, thus hiding the styles from devices or browsers that don’t support media queries. Below, the expression selects only screens in a portrait orientation that have a user agent capable of rending media queries.

```
@media only screen and (orientation: portrait) {...}
```

###Height & Width Media Features

One of the most common features revolvearound determining a height or width for a device or browser viewport. 

Height & width are based off of the viewport rendering area. 

```
@media all and (min-width: 320px) and (max-width: 780px){
	/* code */
}
```

###Using min- & max- prefix

The min and max prefixes can be used on quite a few media features. 

The min prefix: values of greater than or equal to 

The max prefix: values less than or equal to

###Orientation 

`Orientation` media feature determines if a device is in landscape or portrait mode. Landscape mode is trigger when the display is wider than taller. Portrait mode is triggered when the display is taller than wider.

```
@media all and (orientation: landscape) {...}
```

###Aspect ratio

The value for the aspect ratio feature consist of two positive integers separated by a forward slash. The first integer identifies the width in pixels while the second integer identifies the height in pixels.

```
@media all and (min-device-aspect-ratio: 16/9) {...}
```

###Mobile first 

One popular technique with using media queries is called mobile first. The mobile first approach includes using styles targeted at smaller viewports as the default styles for a website, then use media queries to add styles as the viewport grows.