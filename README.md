# Notoire

⚠️ We are currently in version 0.5, meaning the plugin has reached a usable state but is far from over. Some key features are missing and there are probably some lizards lurking around.


- [Introduction](#introduction)
- [Installation](#installation)
- [Commands](#commands)
- [Setup](#setup)


## Introduction

TODO: Talk about Zettelkasten

Key features:

* Notes are stored in plain text files and interpreted as __Markdown__.
* Every note is identified by an __hexadecimal number__, incremented with each note.
* Notes are connected by __links only__. No hierarchy and no tag system.
* More to come with the following versions, check the [issue board](https://github.com/KevinBockelandt/notoire/issues) for details.


## Installation

Using [vim-plug](https://github.com/junegunn/vim-plug), add the following line in you vim-plug configuration:

```vim
Plug 'KevinBockelandt/notoire'
```

Then run :PlugInstall.


## Commands

```vim
:NotoireOpenIndex    Open the index note
:NotoireOpenLink     Open link under cursor
:NotoireCreateNote   Create a new note
:NotoireCreateLink   Create a link to a new note out of the visual selection and open that note 
:NotoireNextLink     Go to the next link in the note
:NotoirePrevLink     Go to the previous link in the note 
```

Note that `:NotoireCreateLink` will only work if you have a visual selection when you call it.

Every command that opens a new buffer also have a version to open that buffer in a split. See the [documentation]('./doc/notoire.txt') for more details.


## Setup

TODO: talk about a proper directory structure

Notoire does not provide a configuration by default, which means you __need__ to set it up. Here is a base config that you can adapt to your needs:

```vim
let g:notoire_folder = '~/Dropbox/notes/notoire/' " notes are kept in this folder

nnoremap <Leader>l :NotoireNextLink<cr>
nnoremap <Leader>h :NotoirePrevLink<cr>

nnoremap <Leader>j :NotoireOpenLink<cr>
nnoremap <Leader>sj :NotoireOpenLinkSplit<cr>
nnoremap <Leader>vj :NotoireOpenLinkVsplit<cr>

vnoremap <Leader>j :NotoireCreateLink<cr>
vnoremap <Leader>sj :NotoireCreateLinkSplit<cr>
vnoremap <Leader>vj :NotoireCreateLinkVsplit<cr>

nnoremap <Leader><Tab> :NotoireOpenIndex<cr>
nnoremap <Leader>s<Tab> :NotoireOpenIndexSplit<cr>
nnoremap <Leader>v<Tab> :NotoireOpenIndexVsplit<cr>
```

See the [documentation]('./doc/notoire.txt') for an exhaustive list of configuration options.
