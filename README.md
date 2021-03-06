ssgn
==========

Super Simple Git Notes for Vim.

Why another notes plugin?
------------
I was unable to find a basic notes plugin to fit my workflow. This simple plugin creates a .txt file for each git repo. The file is stored in a location seperate from your git repo. SSGN looks to see if your current file is a part of a git repo, if so, it will open or create a new .txt file for taking notes about the repo.

Aside from git repos, there is also a 'main' note that you can access at anytime via :SSGNEditMainNote.

Installation
------------
1. add ```Plug 'wcascades/ssgn'``` to you vimrc.
2. run ```:PlugInstall``` in ex mode.

Recommnded use
------------
add the following to your vimrc
```
map <leader>tn :SSGNEditGitNote <CR>
map <leader>tm :SSGNEditMainNote <CR>
```

Configuration
------------
* Set a custom location for the main note

       let g:SSGNMainNoteLocation = "~/todo.txt" 
 
* Set a custom location for the notes directory. The directory must end in with a slash as seen below.

       let g:SSGNNoteDirectory = "~/Notes/" 

Comments
------------
The default directory used for the notes is ".../plugged/ssgn/data".
SSGN uses ```git remote get-url origin``` for naming the notes files. This makes it easy to identify the files while still maintaing a degree of uniqueness. This also lets us move, remove and clone repos, while keeping our notes. However, this means that git repos without a remote origin will not be able to maintain a SSGN git note.
