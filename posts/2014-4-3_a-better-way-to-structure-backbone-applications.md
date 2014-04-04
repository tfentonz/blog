A lot has been written about how painful it is to maintain large scale JavaScript applications or how Backbone isn't opinionated enough. Today I call 'bs' on all the rants and whinging, there are several ways that a good developer can use to create a clean and easily maintainable architacture for large JavaScript applications. Today I'm going to share with you what I think is a better way for creating large scale JavaScript applications using Backbone.js and Require.js.

Creating large scale JavaSCript applications can be very challenging especially to less experienced developers. I have been actively building JavaScript heavy application several years and my framework of choice is Backbone.js and I use require.js for module loading.

### Why Backbone and Require.js?
I love backbone.js for its minimalist code base, you only have 4 concepts that yoyu have to learn in order to master it - Models, Views, Collections and Events. Backbone conforms to standard JavaSCript principles, it is very easy to dive into the source code and modify it to fit your use case. Extending Backbone is also very easy as demonstrated by the large array of extensions available.

Require.js is a very mature module loading library built on Common.js standards. It is reliable and can map module dependency and compile scrips into a single file.

# My Approach
My approach to building large scale JavsScript application starts with creating my directory structure.
Here is how my root directory looks like: views, tmpl, models, collections and libs.

## Views
The views directory contains all the views required for our applications. If a view has subviews then we a nested directory containing those sub-views. The nesting continues until we reach the last child in the tree.

## tmpl
The tmpl contains all out html templates, since backbone applications come with underscore we create all templates as underscore templates. Loading templates require the text plugin for require.js. Structuring templates works the same way as structuring views, if a template has nested views, we create a directory.

## models
Models are the data structures required to display content for out application. The parent container for models is located in the collections directory. Nesting models is not a good idea, rather break them down if possible.

## collections
