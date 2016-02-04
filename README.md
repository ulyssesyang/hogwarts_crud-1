# Hogwarts CRUD Git Branch Exercise

## Greetings!

Obviously we all love the Harry Potter series, so a group of enterprising WDI students has opted to create a CRUD app to track the students of Hogwarts School of Witchcraft and Wizardy.

This exercise is a practice in merging files from other Git branches. We have a full fledged Rails app built across all branches. Your job is to merge them back together.

## Learning Objectives

- Practice pulling git branches from remote repositories
- Practice being a full fledged "merge master" with git branch commands

## Setup - DONT RUN ANY RAILS CONFIG COMMANDS

For this repository into your own Github account. Then clone it to your machine, OUTSIDE of your `wdi/pluto` repo. This app is to be tracked separately from your work. Then view all of the branches on the origin remote. **DONT RUN ANY RAILS CONFIG COMMANDS YET(db:create, migrate, etc..).**

```bash
git clone this_repo_ssh.git
git branch -a
* master
  remotes/origin/HEAD -> origin/master
  remotes/origin/alexs_assets
  remotes/origin/chris_controllers
  remotes/origin/jeselins_gems
  remotes/origin/marinas_migrations
  remotes/origin/master
  remotes/origin/mollys_models
  remotes/origin/ruths_routes
  remotes/origin/shawns_seeds
  remotes/origin/veronicas_views
  remotes/origin/yus_yml
```

## __IMPORTANT__

For each part of the hw, we'll be creating a branch on our end to catch the changes made in the origin remote repo. DO NOT PULL THE BRANCH DIRECTLY INTO MASTER i.e `git pull origin jaskars_gems`. It merges the branches automatically, which is really really really bad form that will make senior devs want to shank you cold blooded. Instead, follow the directions for part 1 for each subsequent step.

# Part 1 - Jeselin's Gems

Jeselin has added the `pry-rails` gem to the Gemfile in her branch `jeselins_gems`.

Let's create a branch of the same name on our local repository so we can catch her changes.

`git checkout -b jeselins_gems`

If you `git branch -a`, you'll see `jeselins_gems` is now green, and local to our machine. We can now inspect its changes.

Go back to master branch: `git checkout master`

Check the diff in code: `git diff jeselins_gems`

This lets you quickly check the altered code in the target branch when compared to the branch you're currently in (master).

Seeing that this is just a single line in the Gemfile, merge Jeselin's wise gem choice into master.

`git merge jeselins_gems`

Provided everything went well, you can add, commit, and push to origin.

# Part 2 - Marina's Migrations

Marina went through the trouble of writing several migration files to create the House & Student tables.
Repeat the process in Part 1 for Marina's wonderful database migrations.

# Part 3 - Shawn's Seeds.rb

Shawn wrote a cool Ruby script that hit a Harry Potter wiki and scraped all of the character names, houses, and image urls. This has been used to build your `seeds.rb` in Shawn's branch. Create your own local version of `shawns_seeds` and merge it into master.

## Hark a MERGE conflict

You might have noticed that you get a merge conflict message after merging `shawns_seeds` into `master`. Read the message and go to the file in question. Git is really good about this and has preserved both versions of the code. One section is code from HEAD in the master branch, the other is the code from Shawn's branch. If Shawn's code make sense over the HEAD branch, simply erase all of the arrow markings.

```
<<<<<<< HEAD
# code in master
=======
# shawns code - keep this
>>>>>>> shawns_seeds
```

Add/Commit/Push the triumphant code.

# Part 4 - Yu's YML

Oh no, we forgot to set the database to Postgresql!!

Not to worry, Yu has branched the code and pushed up a revised `database.yml` file that fixes this.

Merge his changes in `yus_yml` into `master` by following the same steps as previous.

# Part 5 - Chris' Controllers

While you were getting confused with the database files, Chris was calmly coding away and wrote the controllers for our app! Merge the code from `chris_controllers` into master.

# Part 6 - Molly's Models

Molly in the meantime wrote the ActiveRecord Models needed to make this app work, and promptly went back to planning her badass bangs-centric social media app. Merge her code from `mollys_models`

# Part 7 - Veronica's Views

Nica decided we needed some basic views for our site, and has whipped them up in `veronicas_views`

# Part 8 - Ruth's Routes

Ruth put together the routes for our site, using some nice rails helpers. Merge the code in from `ruths_routes`.

# Part 9 - Alex's Assets

Finally, we need some styling in our app, which Alex has graciously provided in `alexs_assets`. Merge the code in and we're good to go!

# Part 10 - Rack it All Up

Now that we're all set up, lets try running our app!

```
bundle install
rake db:create
rake db:migrate
rake db:seed

rails s
```

Doesn't all work? Sort through the errors in your code! Perhaps one of your merges was done incorrectly, or it's just plain old Ruby errors. If it continues to break google/stack overflow it!

