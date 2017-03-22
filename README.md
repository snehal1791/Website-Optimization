# Website Performance Optimization


## Optimized a given Portfolio Website and a Pizza Shop Website


### About


This a Neighborhood Map project in *[Udacity Frontend Nanodegree Program](https://www.udacity.com/course/front-end-web-developer-nanodegree--nd001)*.
The project aimed at optimizing an online portfolio for PageSpeed Insight score to 90 or more; and to optimize Pizza Website so that the page can render at consistent frame-rate of 60fps when scrolling, using the techniques taught in the [Critical Rendering Path Course](https://www.udacity.com/course/website-performance-optimization--ud884).

#### **The website can be accesed by:**
- Clone or download repository by visiting this [GitHub](https://github.com/snehal1791/Website-Optimization) Account
- If downloading, then extract all the files.
- Open index.html on the web browser for PageSpeed of online portfolio
- Open views/pizza.html to see page render at consistent frame-rate of 60fps.

### Outlines for Optimization:
#### PageSpeed Insights Score for index.html:
- Minify and inline print.css
- Minify and inline style.css
- Optimize profilepic.jpg and pizzeria.jpg images
- Minify perfmatters.js
- Add async attribute to Google Analytics script tag
- Load google font using WebFont Loader

#### Consistent frame-rate of 60fps for views/pizza.html
- Make changes in views/js/main.js
- Changes in updatePositions()
 - Store document.body.scrollTop / 1250 in a seperate variable
 - Create empty phase array outside of for loop
 - Push Math.sin(scrollConstant + (i % 5)) in phase array
 - Reduced sliding pizzas count to 48
 - replace querySelector with getElementById
- Changes in resizePizzas()
 - Replace all document.querySelector("#pizzaSize") with document.getElementById("pizzaSize")
- Changes in changePizzaSizes()
 - Create new variable for document.querySelectorAll(".randomPizzaContainer") and replace querySelectorAll with getElementByClassName
 - Inside for loop remove variables dx and newwidth.
 - Add switch case to get newwidth value depending on the size variable
 - Inside for loop add that newwidth to randomPizza[i].style.width as percentage ratehr than pixel
- Remove sizeSwitcher() and determineDx() as no longer needed
- At Line 458: Craete variable and replace querySelector with getElementById for randomPizzas.
- At line 460: Create another variable named fragment that could generate pizzas in for loop.
- At line 466: Outside for loop append all fragments to pizzasDiv.


Gruntfile is being used to generate minified javascript and css files.
    - Grunt is managed via npm the Node.js package manager. Install this (here)[https://nodejs.org/en/].
    - Install grunt from [here](https://gruntjs.com/installing-grunt).
    - Configuration of Grunt can be found [here](https://gruntjs.com/configuring-tasks).
    - Next, task creation, click [here](https://gruntjs.com/creating-tasks).
    - Instruction on **_grunt-contrib-uglify_** can be found [here](https://github.com/gruntjs/grunt-contrib-uglify).

### Optimization Tips and Tricks Can be Obtained at:
* [Optimizing Performance](https://developers.google.com/web/fundamentals/performance/ "web performance")
* [Analyzing the Critical Rendering Path](https://developers.google.com/web/fundamentals/performance/critical-rendering-path/analyzing-crp.html "analyzing crp")
* [Optimizing the Critical Rendering Path](https://developers.google.com/web/fundamentals/performance/critical-rendering-path/optimizing-critical-rendering-path.html "optimize the crp!")
* [Avoiding Rendering Blocking CSS](https://developers.google.com/web/fundamentals/performance/critical-rendering-path/render-blocking-css.html "render blocking css")
* [Optimizing JavaScript](https://developers.google.com/web/fundamentals/performance/critical-rendering-path/adding-interactivity-with-javascript.html "javascript")
* [Measuring with Navigation Timing](https://developers.google.com/web/fundamentals/performance/critical-rendering-path/measure-crp.html "nav timing api"). We didn't cover the Navigation Timing API in the first two lessons but it's an incredibly useful tool for automated page profiling. I highly recommend reading.
* <a href="https://developers.google.com/web/fundamentals/performance/optimizing-content-efficiency/eliminate-downloads.html">The fewer the downloads, the better</a>
* <a href="https://developers.google.com/web/fundamentals/performance/optimizing-content-efficiency/optimize-encoding-and-transfer.html">Reduce the size of text</a>
* <a href="https://developers.google.com/web/fundamentals/performance/optimizing-content-efficiency/image-optimization.html">Optimize images</a>
* <a href="https://developers.google.com/web/fundamentals/performance/optimizing-content-efficiency/http-caching.html">HTTP caching</a>

