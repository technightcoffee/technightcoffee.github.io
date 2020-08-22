---
title: Cleanup your project's Git history like a Pro
date: 2020-08-22 21:04:17
tags: git, git history, project, legacy, code, software, ai, machine learning, cutting-edge, professional, tech leadership, thinkfluencer, asserting dominance in the workplace
---

During the 12 years I have been working in the IT industry as a software engineer, tech lead, international thinkfluencer and accredited Kubernetes systems architect, I never found anything more unnerving than an **effed up Git history**.

You know exactly, what I'm talking about: You join a new project and as you start refactoring and bringing critical, best practices to the code base, you start to learn more about how and why features have been implemented by reading your colleagues' comments in the Git history. Problem is, their commit messages are convoluted, hard to understand and **make absolutely no sense** whatsoever!

So how do you work through this pile of useless "project documentation" and get rid of that mess moving forward? In this article I will share my battle-tested expertise on how you can **clean up any project's Git history**, so you can really focus on what you have been brought into the project for: moving fast and breaking things.

## The Problem

But first, let's look at the actual problem at hand. What did your colleagues do wrong to turn your project's Git history into a living nightmare? There are two main reasons for this awful situation.

### Your colleagues commit way too often

The **more commit messages** your team mates add to the project history, the **worse the messiness** gets.

It's very easy to see that after months or years working on the code base the Git history starts to blow up. And especially in regards to ancient commits, it's really hard to even understand what Mike, who left the company 3 years ago, really did in that commit titled "update(application): secure against CORS violations". This piece of information is useless at best, and just straight up distracting at worst.

Some say that you should follow certain rules to make a commit message descriptive, so it still adds value to the history, including arbitrary guidelines such as writing a 50-73 character summary line and a more verbose message body. But what happens if everyone on your team started doing that on a daily basis? You don't want to have all that backlog of messages piled up in your history, do you?

Yeah. Don’t do that.

### They are scared of changing public history

Many devs are too afraid of cleaning up the mess they make in their Git history and **refuse to change public history**. This becomes a huge issue, because, as you can see in your projects over time, Git history will get messy and if you don't do some spring cleaning on a regular basis, that messiness will get you into serious trouble.

It's critical to let go of the idea, that already published commits are etched in diamond for all eternity. They are not. There is a reason why Git allows you to rewrite public history.

## The Best Solution

I could write another, lengthy article on a plethora of strategies you can employ to clean up your project's Git history and make you productive again. But this strategy I want to share with you today is the most efficient of all of them.

It's quick, easy and lets you move on with your life as fast as possible. It also has the best outcome for your team and all the other developers that will follow your footsteps on working on the code base long after you have left the company. Embrace this practice anytime you start a new project, to set yourself up for success and never worry about history again.

In the project directory, run

```bash
git reset --soft HEAD~<NUM>
```

where <NUM> is the order of the first commit in your project counted backwards from the current one. In a project with 180 commits, <NUM> would be 179.

Now that you have the changes ready, you can clean up the entire project's history with these two commands:

```bash
git commit -m 'Legacy code base'
git push origin main -f
```

where `main` is the name of your main project branch.

Now that you have rebase-squashed the messiness out of your Git history, give yourself a pat on the back and collect your praise from the #dev channel on your company Slack. You and your colleagues will thank you for it!
