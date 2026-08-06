# FullUnit Claude

### coding framework manifesto thing

You know the dil. You've been at this whole "coding" thing for awhile. Decades. Centuries. Or whatever, and now someone someplace has deemed (yay) that Claude is Shipping High Impact Typescript! Oh-meh-gerd look at that a thing that can write code! AMAZING!! And you're thinking "ew, even ORMs are better than this hot garbage" and you're right.

Now you have to deal with it. After lookin' around at the whole "ai" ecosystem, and all the weird 8-bit UIs that try to package this heck as a frickkin fantasy game or some crap, you are tired.

This, friend, is for you. You just want a stupid thing that makes the dumb "ai" do something resembling developing code. Hence, FU Claude.

This is extremely, extremely lightweight. You put in the work where you want to (planning), then the simple prompts and Projectguidelines.txt help turn the ol' Clud into a code printer. FINALLY you don't have to memorize all the macros for Visual Studio or whatever thing is your daily code dungeon. Let the dumb robot be the typist.

Far too many "frameworks" are stuffed full of crap -- "skills", "loops", "graphs", and whatever bullcrap came out of the bronet yesterday (or today). You look through dozens of files and folders and there's no code, just wishes and hopes and dreams in markdown files. Uh... They should just write code at that point. And wow there's a magical oracle that writes code sitting RIGHT THERE. But no... Some these days even come with some code and they really shouldn't. Anyone in the year 2026 who suddenly discovers DAGs has no business designing software.

So, when the c-suits want you to "use ai" and you know they couldn't do a matrix multiplication to save their life, or they can but their brains have been eaten by zombies, I humbly offer this balm, a salve that can help get crap done in a mostly not-annoying way.

# Steps to nirvana

### Follow 'em:

1. Hammer out what to build in a chat, I think using the web ui for this is best.

2. From that chat, have Claude create artifacts – javascript code, markdown files, etc that explain what to build. Look these over to ensure that it described what you want.

3. Pull that stuff into a subfolder someplace where you want to do your project and start a Claude Code session. I've put a handy folder in this repo called "references" where that can go.

4. ProjectGuidelines.txt has a short set of instructions for how to generally write code. There are two other files provided, one is status.md and the other is todo.md. Both of these start out blank. These are all in the "prototypes" subfolder.

5. Issue the planning prompt.

6. Once todo.md has all the development items in a list, issue the working prompt. Re-issue this prompt when Claude stops, you can also automate that in a loop somehow if you desire.


And that's the wole thing. No need to do /init, or install any other junk. You just copy/paste and go.

Here are the prompts referenced above. Modify them to fit your needs, but generally speaking over the last year plus change of developing this while Cludding myself to death every day for hours I've added/changed very little. The "attack surface" exposed to whatever fresh heck is spit out by Anthropic or OpenAI (maybe they will be bankrupt by the time you use this. We can only hope) when they put out their next model is very small. This has survived at least five major model "upgrades". May it live for several more. We'll visit the empty hull of a half-finished data center someplace in a year or two and pour one out for whatever that last model happens to be:

### Planning prompt

``Clear out the contents of prototypes/todo.md and create a detailed todo list of all the items that need to be worked to complete the project detailed in the prototypes/references folder. Ensure that the items can be worked in order so that none will be skipped, so carefully consider development dependencies. Do not add phases or nesting to the list, it should be “flat” with one todo item per line preceded by a text checkbox “[ ]”. Do not add any extra content such as comments, goals, emojis, or time estimates.``

### Working prompt

``Continue with development by reading .claude/ProjectGuidelines.txt then start working on the first unchecked item in the prototypes/todo.md file and work through the items. Mark off completed items in prototypes/todo.md and report all status updates, learnings, and etc in the prototypes/status.md file. Do not modify the prototypes/todo.md file other than to check off completed items. Check in changes to Github between items. Never skip any items in todo.md. If items need to be moved, move them so that they will be worked at the right point in the development process.``