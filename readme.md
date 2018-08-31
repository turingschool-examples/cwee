# Build a Simple One-Page Static Site

### Goals

By the end of this tutorial, you will know/be able to:

* Have an understanding of how to write well constructed, semantic HTML
* Understand how to control the positioning of HTML elements on your page using CSS
* Gain clarity about how CSS is used to create and style your layout

# Overview

The front-end of the web is based on three major technologies:

* __HTML aka "STRUCTURE"__:  HyperText Markup Language (HTML) defines the structure and semantics of web pages on the web.
* __CSS aka "PRESENTATION"__:  Cascading Style Sheets (CSS) sets the look and style of a web page. CSS provides style to the structure provided by HTML.
* __JavaScript aka "BEHAVIOR"__:  JavaScript allows us to define interaction in our pages. What happens when a user clicks on a certain area?

### Today, We Will Be Building Out a Static Site

HTML and CSS are used everywhere on the web, and engaging and appealing pages can be built with a surprisingly small amount of code. In this tutorial we will build a one-page static site to help solidify our HTML and CSS fundamentals.

## Let's start with the Structure

### What is HTML?

 * HTML = HyperText Markup Language  
 * Each page contains a series of connections to other pages called links
 * HTML is made up of many Elements
 * Elements are created with either one or two tags.
 * Elements are used to hold our content and define how the browser must format and display the content.
 * Tags are created with angle brackets `<>` and are used to create elements

### Anatomy of a Tag
![Anatomy of an HTML Tag](/assets/html-tag.jpg)

Just like you wouldn't build a house without framing the walls first, it's a good idea to write up the basic HTML structure of your site before you begin to add content and style your page.

#### Example

Let's say that we had some text and we wanted to denote that this text was a paragraph.

```
This is an example paragraph. We should probably place this inside of a tag. If we place it in a tag it will be easier to access and style.
```

We'd wrap the text in paragraph tags.

```html
<p>This is an example paragraph. We should probably place this inside of a tag. If we place it in a tag it will be easier to access and style.</p>
```

We use `<p>` to signal to the browser that everything that's about to follow is part of a paragraph and `</p>` to let the browser know that this paragraph is done. When a user visits our application, the browser loads up the HTML and parses it into the elements that will eventually make up our user interface.


#### Turn and Talk

Explain HTML in your own words to the person next to you.

# Setup for Today

### Code Pen
Let's head over to [codepen.io](http://codepen.io/) for a quick tour + account setup.

Now, let's take a look at the site we want to build:

![Image of Dog Party Site](/assets/main-page.png)

From this screen grab we can see that we have the following elements:

* a primary header bar with logo and navigation
* a hero unit with a full width background image, title, and call to action (CTA) button
* three columns with sub-headers, secondary content, images, and buttons
* a footer

You can find the links to all the images that you will need to build out your site below:

**Icon**
* https://s33.postimg.cc/d8a1720db/dog-icon.png

**Dogs**
* https://s33.postimg.cc/6525rg2nj/dog1-sq.jpg
* https://s33.postimg.cc/tja53dsan/dog2-sq.jpg
* https://s33.postimg.cc/tw1j9ld5b/dog3-sq.jpg
* https://s33.postimg.cc/52rz8xmf3/dog4-sq.jpg

**Social Media Icons**
* https://s33.postimg.cc/enblvsolr/facebook.png
* https://s33.postimg.cc/9bwpb3hyn/instagram.png
* https://s33.postimg.cc/o7v8iolnj/linkedin.png
* https://s33.postimg.cc/strcr29rj/twitter.png

**Hero Image**
* https://s33.postimg.cc/w0lwaomhr/park.jpg

The first thing we'll do is break this layout down into HTML tags to help us clarify how we want to build the page. Let's write up the skeleton HTML so we have a roadmap to follow as we work. Fork [this codepen](https://codepen.io/plovett/pen/oPBxEr?editors=1010) and we can walk through it together from the top down

First we have a `<header>` tag for our primary header. Within that we have an `<h1>` that will become our logo, and a  `<nav>` tag that's holding an unordered list that will become our primary navigation links.

Next, we have an empty `<section>` tag that will become our hero unit.

Below that, we have another `<section>` tag with three `<article>` tags. These will become our 3 columns.

And, finally, we have a `<footer>` tag.

Now that we have our roadmap, let's add a little placeholder content so we can open this page up in our browser and take a look:

```HTML
<html>
  <head>
    <title>Dog Party</title>
  </head>

  <body>
    <header>
      <h1>Dog Party!</h1>
      <nav>
        <ul>
          <li>How</li>
          <li>What</li>
          <li>Facts</li>
        </ul>
      </nav>
    </header>

    <section>
      <h2>A Site About Some Dogs</h2>
    </section>

    <section>
      <article>How</article>
      <article>What</article>
      <article>Facts</article>
    </section>

    <footer>
      <h4>footer</h4>
    </footer>
  </body>
</html>
```

It doesn't look like much yet, but we can see that the content hierarchy and structure makes sense.

![Image of Dog Party Site](/assets/road-map.png)

Looking at this raw HTML, we can see that the browser has applied default styles for us and the headers and paragraphs are different sizes and font weights. That was nice of them!


However, for our purposes here, we are going to start all of our styling from scratch by adding a `reset` file to what we are building. Although defauly styles can have their uses - there are some days (like today) where we want full control of the styling and sizing of our content. Within your codepen, go to the `Settings` gear, select the option for `CSS` and select the option to set the `CSS Base` to `Reset`. 

Notice how the default styles have been removed. Now we can truly start from scratch.
  
## But What About Our Styling?

This is where CSS comes in.

## CSS The Basics
It’s a “style sheet language” that lets you style the HTML elements on your page. CSS works _with_ HTML, but isn't HTML. CSS controls the positioning, sizing, colors, and specific fonts on your page. There is a `class` and `id` attribute available to use on __every__ html element. In addition to the plain old tag names themselves, these attributes allow you to create "targets" for your css. They are hooks so that you can manipulate the look and behavior (JavaScript) of your HTML elements.

### Anatomy of a Basic CSS Rule

# ![CSS Rule](/assets/css-rule.png)

* Can target via tag name
* Can target via class name
* Can target via id name
* Can target via a combination of above

### All the Elements are Boxes
Each element is a rectangular box. CSS leverages "the box model" to control layout and design. An HTML element is comprised of its content and the margins, borders, padding surrounding it. Boxes are "stacked" in the order they appear in your HTML. You can stack them horizontally, vertically, and in the z-plane.

# ![Box Model](/assets/box-model.jpg)

## Let's play with some basic CSS properties

* Box Model things: `width`, `height`, `border`, `padding`, `margin`
* Aesthetic things: `color`, `font-family`, `background-color`

Let's target our article tags and add a `lime` background. Let's also give our article containers a height and width, like this:

```css
article {
  background-color: lime;
  border: 1px solid black;
  height: 100px;
  width: 100px;
}
```

There are MANY properties that you can utilize to style the elements on your page. [CSS Tricks](https://css-tricks.com/almanac/properties/) is a good, visual resource for digging in further.

#### Turn and Talk
Take a moment with the person next to you and test out three new properties together.

## Box-Sizing and the CSS Box Model:

In HTML, you can visualize each element as its own rectangular box. There are a number of CSS properties that can affect the final width and height of each of these boxes. The CSS Box Model describes how the final height and width of an element is determined.

We have a `div` element that we gave a `width` of `400` and a `height` of `200`. However, we've also applied several additional properties that are affecting its size and positioning. The `padding` property is adding `20px` to the element's height and width. Now the actual *visible* dimensions of our element are `440x240`. The DevTools panel provides a handy graphic of how our div is being rendered.

This is the default behavior for the rendering of block elements in CSS and is due to the `box sizing` property having a default value of `content-box`. The `box-sizing` property allows us to override this behavior and alter how the dimensions of an element are calculated:

```css
*,
*:after,
*:before {
  box-sizing: border-box;
}
```

Setting the `box-sizing` property to `border-box` will alter the model so that the `width` and `height` properties include the content, padding and border. If we were to set `box-sizing: border-box` on our previous example, our element would be rendered at exactly the `400x200` dimensions we specified. Its `padding` and `border` properties would be included within those dimensions, making our content area slightly smaller.

## Document Flow is Important

The document flow is the model by which elements are rendered by default in the CSS specifications. In this model, elements are rendered according by their default display rule. In other words, block-level elements are displayed on a new line and inline elements on the same line. Everything is stacked in an ordered way from top to bottom. The document flow can be modified by CSS through its positioning properties.

- CSS divides HTML elements into two types: inline and block
- After block elements, browsers render a new line
- Inline elements: `img`, `a`, `br`, `em`, `strong`
- Block elements: `p`, `h1`, `ul`, `li`, almost everything else


# Let's Make a Navigation Bar

The first element we see is the header bar at the top of the page. We can see that we have a logo on the left side and three links on the right side.

We've written the html structure for this section, let's take a look at it:

```html
<header>
  <h1>Dog Party!</h1>
  <nav>
    <ul>
      <li>How</li>
      <li>What</li>
      <li>Facts</li>
    </ul>
  </nav>
</header>
```

We know that we want to have a colored header bar, let's start there. Add this to your CSS.

```CSS
header {
  background: #92E0E5;
  color: white;
  height: 50px;
  padding: 0 25px;
}
```

Great! Our header bar is teal now. Next, we know that we want the three links to be on the far right side of the header bar. They're currently still in the normal page flow, and over on the left side under the `<h1>` text. Let's go ahead and move them over to the right.  

There are several different ways to accomplish this, but we'll use a float to move the `<nav>` element holding our navigation links over to the right. This will pull the `<nav>` out of the normal page flow and push it over to the right. We want to target the `<nav>` that is within the `<header>`, and we write it like this:

```CSS
header nav {
  float: right;
}
```


Yet, we can see that something is not quite right. The `<nav>` has been pushed over to the right, but now it has been pushed down out of the header. That's weird, what's going on?

Our `<h1>` is taking up the entire width of the page. That is why the `<nav>` is being pushed down out of the header. This is happening because `<h1>` tags are *block level* elements, so by default they will fill the entire row that they are on.  

We can solve this by floating our header's h1 to the left. It won't look that different since `float: left` will keep the h1 on the left side of the screen, but the reason this helps us is because the float pulls the h1 out of the normal page flow and allows us to have two elements on the same row. Now both the h1 and the nav will be aligned nicely and inside of the header bar. Our CSS for the `<nav>` and `<h1>` looks like this:

```CSS
header h1 {
  float: left;
}

header nav {
  float: right;
}
```

Great! Now let's get those `<li>` elements to be in a row instead of stacked on top of each other. Like we found with with our h1, `<li>` is a block level element. A simple approach to make them align horizontally rather than vertically is to change the `<li>` tags from block level elements (the default) to inline elements. This will allow them to all sit next to each other on the same row. Here's the code:


```CSS
header h1 {
  float: left;
}

header nav {
  float: right;
}

nav li {
  display: inline-block;
}
```

That looks pretty close! We just need to get those `<li>` elements vertically centered in the header. We can do that by adding padding to them. The code looks like this:

```css
nav li {
  display: inline-block;
  padding: 17px 10px;
}
```

We just added 17px of padding to the top and bottom of each li, and 10px padding to the left and right sides. This centered them vertically in the header and gave them a little breathing room.

Let's add a hover to those li elements so our users get some visual feedback as they mouse over them. We'll make the background and text color on the `<li>` change on `:hover`. Here's the code:

```css
nav li {
  display: inline-block;
  padding: 17px 10px;
}

nav li:hover {
  background: #3F8DA7;
  color: white;
  cursor: pointer;
}
```
<!-- 
header h1 {
  float: left;
  text-indent: -9999px;
  background: url('../images/dog-icon.svg') no-repeat;
  height: 35px;
  width: 35px;
  margin-top: 8px;
} -->

#### Challenge Time

Take a look at your `header h1` selector that currently has a float of left. Modify it so that we can add the dog icon to what we have:

```css
header h1 {
  background: url('https://s33.postimg.cc/d8a1720db/dog-icon.png') no-repeat;
  height: 35px;
  width: 35px;
  margin-top: 8px;
}
```
However... now we have the "Dog Party" text and our image clashing. How might we move this text over without deleting the text completely? 

_Hint:Look into the [`text-indent` CSS property](https://css-tricks.com/almanac/properties/t/text-indent/)_

And that's our header!


# With a Partner: Making a Hero Unit

Next thing to tackle is the hero unit. This may sound like a strange term, but it's common way to describe a large splash section on a landing page. It basically just means that this section is the first one people will see, so it needs to make a great first impression -- it's a hero.

Let's go through what our hero unit layout needs before we start styling. We'll need a full width background image, a page header, a primary image, and a call to action (also referred to as a "CTA") button.

As a first step, let's add an `id` of "hero" to the `<section>` that will be wrapping our hero unit. This will let us target that specific section with our styles, and since it's unique to this section we can use an `id` because we know we won't have another hero unit.

```html
<body>
  <header>
    <h1>Dog Party!</h1>
    <nav>
      <ul>
        <li>How</li>
        <li>What</li>
        <li>Facts</li>
      </ul>
    </nav>
  </header>

  <section id="hero">
    <h2>A Site About Some Dogs</h2>
  </section>

  <section>
    <article>How</article>
    <article>What</article>
    <article>Facts</article>
  </section>

  <footer>
    <h4>footer</h4>
  </footer>
</body>
```

We'll also need to add the additional content to our `#hero` section.

```html
<section id="hero">
  <h2>A Site About Some Dogs</h2>
  <img src="https://s33.postimg.cc/6525rg2nj/dog1-sq.jpg" alt="hero dog"/>
  <a href="http://corgis-in-space.tumblr.com/" target="_blank">What are Dogs</a>
</section>
```

It shouldn't look great to start. But now that we have our content in our HTML, we can start styling it. The first thing to tackle is the full width background image, and because we put our logo into the header as a background image we're familiar with the syntax. Let's do that first:

```css
#hero {
  background: url('https://s33.postimg.cc/w0lwaomhr/park.jpg') no-repeat;
  background-size: cover;
  text-align: center;
  padding: 50px 0;
  margin-bottom: 50px;
}
```

That looks much better! But what is this CSS doing? On the first line we set our background image to be `park.jpg` and say that it should not repeat (by default, background images repeat, or tile, from left to right, top to bottom).  

On the next line `background-size: cover` tells the image to fully fill the space available automatically, which means that you won't get awkward white space on the sides or bottom as you move between large and small screen sizes.  

`text-align: center` centers all the content inside of our `#hero` section, including text *and* images, so our content will be neatly aligned in the center of the page.  

And finally, `padding: 50px 0` sets internal padding of 50px at the top and bottom of the `#hero` section so the content inside has some breathing room and doesn't feel too crowded, and a `margin-bottom` of 50px gives the content below our hero unit some space.

Hmm. Something isn't right. Why are the primary image and CTA link on the same line? Looks like we are running into issues with the `<img>` and `<a>` tags being inline elements by default. We can easily fix this by setting the `<img>` to `display: block`.

```css
#hero img {
  display: block;
}
```

Now that the image and the CTA link are on different rows, we can style the image. We'll need to re-center it, add a border-radius to make it a circle, and add a colored border. Here's the code:

```css
#hero img {
  display: block;
  margin: auto;
  border-radius: 50%;
  border: 5px solid #3F8DA7;
}
```

Now, let's make the `<h2>` a bit larger so it looks more like a title:

```css
#hero h2 {
  font-size: 30px;
}
```

We could use some margin on the bottom of the `<h2>` and the primary image. Let's add that.

```css
#hero img {
  display: block;
  margin: auto;
  margin-bottom: 25px;
  border-radius: 50%;
  border: 5px solid #3F8DA7;
}

#hero h2 {
  font-size: 30px;
  margin-bottom: 25px;
}
```

All that's left is styling our CTA link:

```css
#hero a {
  background: white;
  border: 5px solid #3F8DA7;
  color: #3F8DA7;
  padding: 5px 10px;
  text-decoration: none;
}

#hero a:hover {
  padding: 5px 10px;
  background: #3F8DA7;
  color: white;
}
```

Now our hero unit is complete. 🎉

# On Your Own: Making 3 Columns

![Three Column Section](/assets/three-cols.png)

In this content section, we have three columns that sit side by side. If we look at them, we see that they all have the same structure, style, and content organization. They consist of a title, an image, a block of text, and a button. We know that each column will have the same structure with different content, so we will use the same base HTML and styles for all three and then simply plug in the unique content for each. This lets us keep our code DRY and avoid duplication, and gives us the flexibility to easily reuse these styles elsewhere in our site down the road.  

Note that we use the class `three-col` on all three of the columns: we do this because we want to apply specific styles that will make these blocks of content into three columns, and we want to use *the same styles* to accomplish that on all three. We don't apply the styles directly to the `<article>` tag because it's very likely that at some point in the future our site could have other `<article>` tags that are not in a three column grid. We might also want to use a different tag in a three column grid down the road -- we could just as easily put this class on a `<section>`, `<div>`, or other tag and get the same three column layout results. It is good practice to consider long-term flexibility as you write your HTML and CSS.

Let's update our HTML structure so all three columns are the same:

```html
  <section>
    <article class="three-col">
      <h3>How</h3>
      <img src="" alt="first image"/>
      <p></p>
      <a href=""></a>
    </article>

    <article class="three-col">
      <h3>What</h3>
      <img src="" alt="second image"/>
      <p></p>
      <a href=""></a>
    </article>

    <article class="three-col">
      <h3>Facts</h3>
      <img src="" alt="third image"/>
      <p></p>
      <a href=""></a>
    </article>
  </section>
```

Not a whole lot has changed. Time to put in content! Let's add images and text. We can grab a few lines of placeholder text from a [lorem ipsum text generator](http://www.meettheipsums.com/).

```html
  <section>
    <article class="three-col">
      <h3>How</h3>
      <img src="https://s33.postimg.cc/tja53dsan/dog2-sq.jpg" alt="first image"/>
      <p>
        Nap all day Gate keepers of hell yet stares at human while pushing stuff off a table. Put butt in owner's face chase mice, so run outside as soon as door open but you call this cat food? stare at the wall, play with food and get confused by dust.
      </p>
      <a href="https://en.wikipedia.org/wiki/Dog">Link One</a>
    </article>

    <article class="three-col">
      <h3>What</h3>
      <img src="https://s33.postimg.cc/tw1j9ld5b/dog3-sq.jpg" alt="second image"/>
      <p>
        Soft kitty warm kitty little ball of furr. Hunt anything that moves meowing non stop for food stand in front of the computer screen knock dish off table head butt cant eat out of my own dish, then cats take over the world hide when guests come over.
      </p>
      <a href="http://www.dog-adoption-and-training-guide.com/about-dogs.html">Link Two</a>
    </article>

    <article class="three-col">
      <h3>Facts</h3>
      <img src="https://s33.postimg.cc/52rz8xmf3/dog4-sq.jpg" alt="third image"/>
      <p>
        Destroy the blinds chase imaginary bugs, so lie on your belly and purr when you are asleep. Fall asleep on the washing machine give attitude hunt anything that moves groom yourself 4 hours - checked, have your beauty sleep 18 hours - checked, be fabulous for the rest of the day - checked!
      </p>
      <a href="http://www.livescience.com/13305-facts-dog-breeds-genetics-pets.html">Link Three</a>
    </article>
  </section>
```

Now we see that we have all our content, but it's looking pretty rough. The three articles are stacked on top of each other, all the content is left justified, and our paragraph text is stretching the full width of the screen. Let's start fixing this. We'll start by making our columns actually be columns. Time to utilize our `three-col` class on the opening article tags -- we can add positioning styles, and have flexibility if we at some point want to have other elements on the page be in a three column layout. In our CSS we'll write the following:

```css
.three-col {
  width: 30%;
  display: inline-block;
}
```

Now we have our content in columns, but it would be nice if all the columns were level. Turns out there is a simple way to do just that, with the [`vertical-align` property](https://developer.mozilla.org/en-US/docs/Web/CSS/vertical-align). While we're at it, let's go ahead and center the content and give our columns some right and left margin, too.

```css
.three-col {
  width: 30%;
  display: inline-block;
  text-align: center;
  vertical-align: top;
  margin: 0 10px;
}
```

Let's get the images to be a consistent size, put that fancy border radius on them to make them circles, give them a teal border, and add some margin to top and the bottom so the images have some breathing room.

```css
.three-col img {
  border-radius: 50%;
  border: 3px solid #3F8DA7;
  height: 200px;
  width: 200px;
  margin: 25px 0;
}
```

Now all that's left on our columns is to get our `<a>` tag styled as a button. Hmm. Didn't we already style an `<a>` tag like a button in our hero unit? Why write the same CSS twice, let's just reuse what we already have.

To make our existing styles be applied to all our `<a>` tags instead of just the `<a>` tag in our `#hero` section, our [selectors](https://developer.mozilla.org/en-US/docs/Web/Guide/CSS/Getting_started/Selectors) will change from this:

```css
#hero a {
  background: white;
  border: 5px solid #3F8DA7;
  color: #3F8DA7;
  padding: 5px 10px;
  text-decoration: none;
}

#hero a:hover {
  padding: 5px 10px;
  background: #3F8DA7;
  color: white;
}
```

To this:


```css
a {
  background: white;
  border: 5px solid #3F8DA7;
  color: #3F8DA7;
  padding: 5px 10px;
  text-decoration: none;
}

a:hover {
  padding: 5px 10px;
  background: #3F8DA7;
  color: white;
}
```

In your CSS, try removing `#hero` from your current `<a>` styles. You should see that all the `<a>` tags have the same styles now! We can also see that our buttons are really crowding the paragraph text. Let's go ahead and add a margin-bottom to the `<p>` tags in our columns.

```css
.three-col p {
  margin-bottom: 40px;
}
```

# Almost there: Making The Footer

![The Footer](/assets/footer.png)

The last thing to style is our footer. Let's start by building the HTML structure for this final grouping of content. We see that we have three blocks of information: a subhead, a collection of social media icons, and a link back to the repo.

```html
<footer>
  <h4></h4>
  <ul>
    <li></li>
    <li></li>
    <li></li>
    <li></li>
  </ul>
  <a href="" target="_blank"></a>
</footer>
```

This structure should look familiar. We have an `<h4>` level header as our subhead, we'll put our social media icons in `<li>` within an unordered list the same way we made our main navigation links in our header, and we have an anchor tag for our link.

Let's add our content:


```html
<footer>
  <h4>Learn About Dogs Online</h4>
  <ul>
    <li><img src="https://s33.postimg.cc/enblvsolr/facebook.png"/></li>
    <li><img src="https://s33.postimg.cc/strcr29rj/twitter.png"/></li>
    <li><img src="https://s33.postimg.cc/9bwpb3hyn/instagram.png"/></li>
    <li><img src="https://s33.postimg.cc/o7v8iolnj/linkedin.png"/></li>
  </ul>
  <a href="https://github.com/turingschool-examples/cwee" target="_blank">See this on GitHub</a>
</footer>
```


Let's start styling:

```css
footer {
    background: #3F8DA7;
    color: white;
    margin-top: 40px;
    padding: 20px 0;
    text-align: center;
}
```

We can see that we changed our background color, made our text white, tidied up spacing with a top margin and internal top and bottom padding, and centered all of the footer content.

Next, let's get our social media icons positioned in a row.

```css
footer ul {
  margin: 40px 0;
}

footer li {
  display: inline-block;
  margin: 0 25px;
}
```

We're almost done, but our link has the CTA button styles because we applied them to all `<a>` tags. We don't want our link styled that way here in our footer. A better, more reusable solution would be to apply CTA button styles to a class. This will allow us to put that class on `<a>` tags that we want to be styled as buttons, and have another class for basic link styles that we can use in our footer.

Let's do a little refactoring of our CSS.

Our current `<a>` tag styles that create our CTA button look will change from this:

(Old CSS)
```css
a {
  background: white;
  border: 5px solid #3F8DA7;
  color: #3F8DA7;
  padding: 5px 10px;
  text-decoration: none;
}

a:hover {
  padding: 5px 10px;
  background: #3F8DA7;
  color: white;
}
```

To this:  

(New CSS)
```css
.btn {
  background: white;
  border: 5px solid #3F8DA7;
  color: #3F8DA7;
  padding: 5px 10px;
  text-decoration: none;
}

.btn:hover {
  background: #3F8DA7;
  color: white;
  padding: 5px 10px;
}
```

Make sure to remove the styles associated with the `<a>` tags in your `.css` file, and add `class="btn"` to the `<a>` tags in our hero unit and columns. Here's what the `<a>` tag in our hero unit will look like:

```html
<section id="hero">
  <h2>A Site About Some Dogs</h2>
  <img src="https://s33.postimg.cc/6525rg2nj/dog1-sq.jpg" alt="hero dog"/>
  <a href="http://corgis-in-space.tumblr.com/" target="_blank" class="btn">What are Dogs</a>
</section>
```

Go ahead and add `class="btn"` to the `<a>` tags in our three columns and refresh your page to confirm that our CTA button styles are looking as expected.

Back in our footer, our `<a>` is looking closer to what we want. Let's add `class="link"` to our footer's anchor tag and then define this is in our `css` for basic link styles:

```html
<footer>
  <h4>Learn About Dogs Online</h4>
  <ul>
    <li><img src="https://s33.postimg.cc/enblvsolr/facebook.png"/></li>
    <li><img src="https://s33.postimg.cc/strcr29rj/twitter.png"/></li>
    <li><img src="https://s33.postimg.cc/9bwpb3hyn/instagram.png"/></li>
    <li><img src="https://s33.postimg.cc/o7v8iolnj/linkedin.png"/></li>
  </ul>
  <a href="" target="_blank" class="link">See this on GitHub</a>
</footer>
```

The CSS for our basic link styles will look like this:

```css
.link {
  color: white
}

.link:hover {
  color: #92E0E5;
}
```


## The Extra Mile: Tightening Up The Page

Our page is more or less done, but we can go back and polish it up a little bit. Let's see what we have:

![Image of Dog Party Site](/assets/full-layout.png)

A few things we can do now to tighten our layout up:

* have the main navigation in the header link to the appropriate columns of content in the page
* update the color and size of the headers in the columns
* Add a thin, darker teal bottom border to the header bar
* There are few visual inconsistencies between our site and the original comp. Work on making adjustments so our site looks the same as the comp.

Take a crack at these final layout tweaks, and give yourself a big pat on the back! You just made a page from scratch with HTML and CSS.
