# Thomas J. Leeper

This is the git repository for my webpage, which is hosted with [GitHub Pages](http://pages.github.com/). I'm still experimenting with it, since I moved from a static hosting service (after a period of hosting on Dropbox). GitHub Pages offers support for [Jekyll](http://jekyllrb.com/), but I haven't started migrating my old HTML into Jekyll yet. Maybe soon.

Some things I learned setting up my custom domain redirect (from [thomasleeper.com](http://www.thomasleeper.com)), which weren't very well documented on the GitHub Pages [help files ](https://help.github.com/articles/setting-up-a-custom-domain-with-pages) are as follows. If you set up the redirect according to the instructions, it still may not work. My domain is registered with [mydomain](http://www.mydomain.com/) and I had to do the following configurations to get the redirect to work and to avoid an infinite looping redirect between mydomain and GH pages:
* Make a `CNAME` file containing the domain in your gh-pages repository.
* At your domain registrar, setup an **A record** pointing to the gh-pages address: `204.232.175.78`.
* At mydomain, I had to setup:
  * a "standard pointer" (not stealth) to `leeper.github.io`.
  * a CNAME Alias for www.thomasleeper.com pointing to `leeper.github.io`.
  * an A record for www.thomasleeper.com pointing to `204.232.175.78`.
  * an A record for @.thomasleeper.com pointing to `204.232.175.78`.

This is based on some advice from [this StackOverflow question](http://stackoverflow.com/questions/9082499/custom-domain-for-github-project-pages), which was pretty helpful. It was really frustrating getting this setup but once those settings were in place everything started working almost immediately. Hopefully this is helpful for anyone else experiencing similar problems. 
  
