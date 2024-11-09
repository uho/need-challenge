## Attention Forth Programmers! ##

November 2024

#### THE NEED Challenge ####

We are pleased to announce **The NEED Challenge**, a unique opportunity for
Forth enthusiasts and developers to showcase their skill and creativity.

Your task is to implement the word `NEED` for the Forth system of your
choice, leveraging whatever techniques you find most suitable. Whether it’s
loading code from files, blocks on disk, or even remote repositories, this
challenge is your chance to explore and push the limits of what Forth can
accomplish.

As the saying goes, _If you’ve seen one Forth, you’ve seen one Forth_,
highlighting the diversity of Forth systems in terms of scope, functionality,
and implementation. Now is your chance to prove your adaptability and 
innovation 😀.

Here is what NEED is supposed to do:

```
NEED  ( i*x <name> -- j*x )

parse <name> and check if it is present in the dictionary; if so, do nothing. 
If <name> is not found, attempt to load a source code snippet that 
defines <name> using any system-specific method available. 
If no appropriate code snippet can be found, issue an error.
```

Your implementation will contribute to the Forth community and support the
continued evolution of this uniquely versatile language we all love.
Contribute to the future development of modular, efficient Forth programming. 
Our experience of using `NEED` shows a nice change of how we program Forth.
No longer do we think of source code and where words are defined but we 
think in terms of words, their names, and their behavior.

Submit your `NEED` ideas and implementation to **need-challenge@xlerb.de**.

Join your fellow Forth enthusiasts in an engaging and rewarding challenge
that showcases the rich versatility and depth of your favorite programming
language and system. Your contributions are highly encouraged and will be 
shared and discussed within the Forth community, offering you the opportunity
to present and publish your work.

Still wondering what `NEED` does and why it is important? Here is a very
simple example.

Suppose you are working on a Forth project that requires the word `ARRAY`, 
a defining word that consumes the size of the array and provides the element
address for a given index, i.e. `( u <name> -- )`. Each defined array will
have the stack effect `( u -- addr )` mapping indices to element addresses
within the array.
Before defining it manually in every application that you program, you can
use `NEED` to ensure it is available. If `ARRAY` is already present, the code
runs without loading anything additional. If not, `NEED` will attempt to load
the relevant definition to make it available:

```
NEED ARRAY ( This ensures ARRAY is available )

5 ARRAY testArray ( define an ARRAY )
```

To validate your `ARRAY` implementation, you can use the Hayes tester with
tests such as:

```
NEED testing   ( This ensures the Hayes tester is available )

{ 0 testArray DROP -> }  ( check stack effect ) 
{ 10  0 testArray !  20 1 testArray !  30 2 testArray ! -> } 
{ 0 testArray @  1 testArray @  2 testArray @ -> 10 20 30 } 

( and so on )
```

Show us what you can accomplish. Let the Forth be with you 🙂.
