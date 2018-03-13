---
layout: post
title: "Hooks, hooks everywhere (II)"
tagline: "Integrate git hooks in your project with Gradle"
author: "Victor de Francisco"
---

On a previous [post]({{ site.baseurl }}/2018/02/28/git-hooks.html) we took a look on how to integrate git hooks in your project using a custom hooks folder and a little configuration magic on git config.

That maybe fits well in your team but we can go a bit ahead and carry hooks power along with [gradle][gradle] environment. That would move your hooks environment to the next level.

One of the tradeoffs of the previous environment was the need to execute the install.sh script inside the hooks folder to configure git properly and use your own hooks. That should be done by every developer almost one time in their lives.

What if we could integrate our hook environment in the project without explicit action on our part? That could be done using gradle.


### A little about gradle

Gradle works with tasks written in [groovy][groovy] language, the most important is that you can extend its behavior so you can integrate with it implementing your own tasks and integrate with its lifecycle.

In a few words, we can create a custom task in gradle that will prevent us from executing by demand our tasks. We will  use that to implement a task that adds our hooks path to git on a build or clean of the project.


If you like to know details about how gradle works, you can take a look at [gradle docs][gradle-docs].


### Take advantage of gradle integration


[gradle]: https://gradle.org
[gradle-docs]: https://docs.gradle.org/current/userguide/userguide.html
[groovy]: http://groovy-lang.org/