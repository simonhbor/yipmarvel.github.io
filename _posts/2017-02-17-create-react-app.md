---
layout: post
category: coding
tags: [react, code]
title: Create React App is Too Much Black Box
---

I've got pretty good at setting up a quick "Hello World" React app using node. CDN files for Babel and React, a 5 line server file. Then I concentrate on making stuff. This week I wanted to go further and finally get modules working. So I tried out Create React App. It was very slick. I didn't like it.

I like a minimal setup: npm scripts wherever possible, native CSS most of the time, not many npm packages. But I bit the bullet and tried out Webpack with Babel to handle module loading and bundling. I followed a tutorial. Steps 1-4 worked. Step 5 not so much. I couldn't work out why.

I had two choices: bash my head against a wall; or use a setup from people smarter than me. I went with door number two and [create-react-app](https://github.com/facebookincubator/create-react-app). It literally worked perfectly first time. Server spun up, with custom terminal messages. Browser tab automatically opened with something simple but shiny on the page. Live reloading just up and running. Extensive, clear, and sensible documentation online. Cool. I can get back to making stuff right?

Probably, possibly. But I didn't. I wanted to work out what made some of the magic.

- 65mb of npm packages for a 65.1mb project. I know it gives me room to grow with Jest, Webpack, lots more, but 65mb of baggage is not a barebones boilerplate.
- the scripts that do the magic are embeddd in their npm packages, with little sign of what is going on under the hood
- the ability to change settings seems opaque - I couldn't spot a webpack.config.js or a .babelrc file. 

So I went back to bashing my head on the wall. Eventually I worked out step 5 (getting modules to load) with my ultra barebones setup (err... just 24mb of npm packages, sigh). A helpful comment on the tutorial explained what the tutorial had missed out - one babel package (who knew there were so many).

I am now back at a POC "hello world". It's less powerful than create-react-app. It's less fancy out the box. It is not, I am sure, based on best practice. But I know how it works (not that I really know what babel and webpack do under the hood). And I got there line by line.

I will keep adding to my configs--I want to push myself to learn more about website plumbing. Maybe after a few projects like this I will come back around to create-react-app. Maybe it's one of those things that works for beginners and experts but people in the middle (like me) should not skimp on the learning by doing.
