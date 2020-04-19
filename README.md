# Sullinger.us
---

**Sullinger.us** is a repository containing the static website and content posts for [my blog](https://sullinger.us). The site is powered by [Jekyll](https://jekyllrb.com) on GitHub Pages.

## Local Development

Previewing the content of the site, or developing the site, can be done locally via Bundle. To start you will need to install Bundler and then configure it to store vendor gems in the `vendor/bundle` directory. The following commands will perform this operation along with installing all of the gems required to run the site.

```
$ gem install bundler
$ bundle config set path 'vendor/bundle'
$ bundle update
```

Once done the site is ready to run locally. You can serve it using `bundle exec jekyll serve`.

> A note on dependencies. If you need to change the version of Jekyll or Jekyll-Pages make sure that you align with the supported version on [GitHub Pages](https://pages.github.com/versions/)

If you need to build a local copy of the site you can do so now running `bundle exec jekyll build`

## Creating Content

All posts go into the `_posts` directory using the naming convention of *YYYY-MM-DD-title-without-spaces.md* The top of each markdown file must begin with metadata configuring the post, including a human friendly title.

```yaml
---
layout: post
title: "Going Serverless: Part 1 - Introduction"
---
```

The rest of the content can go beneath the yaml configuration above.

Some posts will need to have any assets, such as images or downloads, linked to. In this scenarios create a folder under the `assets` directory matching the filename of the post. If the post is `_posts/2020-04-21-My-Post.md` then the assets will be placed into a folder at `assets/2020-04-21-My-Posts/my-asset.jpg` You can link to the asset using relative URLs, for example:

**Images**
```
![My Screenshot](/assets/2020-04-21-My-Posts/screenshot001.jpg)
```

**Downloads**
```
You can download [the PDF](/assets/2020-04-21-My-Posts/my-doc.pdf) and read the instructions.
```

## Posting Content

To post content to the website you will just need to commit the changes to the master branch. Be sure that you have staged both the post markdown file and all of the assets required for the post.

```
git add .
git commit -m 'Posting new blog entry: {title here}'
git push origin
```

Once the Commit is pushed to origin then GitHub Pages will start processing the document. The page will be live shortly after pushing. GitHub states that this process can take up to 10 minutes.