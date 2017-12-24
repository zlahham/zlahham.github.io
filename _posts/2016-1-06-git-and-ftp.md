---
layout: post
title: How to set up git for FTP
intro: A tutorial on how to use git as a complement to the annoying FTP, converting this to a Heroku-like solution!
tags:
  - git
  - github
  - ftp
comments: true
---

### Learning from my mistakes
I ran into a certain issue a few months back when I inherited [warwickCoding](http://warwickcoding.com)'s website.

I found the hosting pissue that was already prepaid for to be not ideal, this is because I had to mainly rely on File Transfer Protocol (FTP) to upload the website assets and code to the servers. Being used to Heroku-like solutions, I found this a bit limiting, but due to time constraints, I had to deliver the new website before the new year.

I would like to point you to the tutorial that helped me wire up FTP and git together. I found the tutorial over at the tuts+ website. You can follow the tutorial all the way until he connects the service through the Github webhooks settings. That is where I found it to be a bit outdated. I'm going to try to fill in the blanks that the tutorial didn't provide.

[![Tutorial Video](http://img.youtube.com/vi/mNsrA6Smzro/0.jpg)](http://www.youtube.com/watch?v=mNsrA6Smzro)

In all cases, here is the link to the [tutorial](http://code.tutsplus.com/tutorials/how-to-use-git-with-ftp--net-27610). Follow it through to when he's setting up the project settings on DeplyHQ. At that point refer to the following:

### Next Steps
So, after you connect your Github account to the Deploy service and you choose the repo in question, fill in the details of that project. When you get to the part where you need to fill in the "Path on server", you can leave this blank if you are just using a simple static site, or you can default it to `public_html/`. The username and password are the same ones that you used to access cPanel from your hosting provider. The username will usually be quite obvious.

### Github Deploy Hooks
- After you fill in the settings for the project and you save them, you should edit the project from this screen:
![Edit DeployHQ settings](../../../../../assets/post1/edit-deployhq.png)

- After you get on the edit page, you should copy the following URL marked in the red box:
![DeployHQ auto](../../../../../assets/post1/auto-deployhq.png)

- Go back to Github.com and go to your repo's settings, look for the "Webhooks & services" tab. Select "Add webhook" like shown:
![Add webhook](../../../../../assets/post1/add-webhook.png)

- Then paste the URL that you copied from DeployHQ into the following field:
![Add Payload URL](../../../../../assets/post1/add-url.png)

- I then left the other fields blank and then pressed "Add webhook"

- Make a change to the repo, add, commit, and then push it to GH.

- Give it a few seconds and then check go your website's URL and your changes should have taken place


There you have it! You are now free from the shackles of FTP and you should just treat your master branch as your production.
I hope this helps. If you have any questions, feel free to reach me on [Twitter](https://twitter.com/zlahham).



