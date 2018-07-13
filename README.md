[![Build Status](https://travis-ci.org/zoffixznet/perl6-CoreLab-Tear.svg)](https://travis-ci.org/zoffixznet/perl6-CoreLab-Tear)

# NAME

`CoreLab::Tear` - core inclusion experiment for `.tear` listy method

# SYNOPSIS


```perl6
use CoreLab::Tear;

dd <a b c X d e X g h X i j>.tear: 'X'; # (<a b c>, <d e>, <g h>, <i j>).Seq
dd <a b c X d e X g h X i j>.tear: 'X', :keep-start; # (<a b c>, <X d e>, <X g h>, <X i j>).Seq
dd <a b c X d e X g h X i j>.tear: 'X', :keep-end;   # (<a b c X>, <d e X>, <g h X>, <i j>).Seq

# convert elements with :&as before matching
dd <a b c X d e X g h X i j>.tear: 'x', :as{.lc}; # (<a b c>, <d e>, <g h>, <i j>).Seq

# use :&with as comparator, instead of the default behaviour that's equivalent to &[===]
dd <a b c 1 d e 1 g h 1 i j>.tear: '1', :with(&[eq]); # (<a b c>, <d e>, <g h>, <i j>).Seq
```

# DESCRIPTION

The offspring of `.split` and `.rotor`, the `.tear` method tears a list of values apart into
sublists, with tears occurring on element(s) whose value matches the given argument.

## AUGMENTATIONS

Due to how augments work in Rakudo at the moment, you may need to re-compose subclasses of `List`

###

The offspring of `.split` and `.rotor`. Tears a list of values apart into sublists, with tears
occuring on element(s) whose value matches the given argument. The

----

#### REPOSITORY

Fork this module on GitHub:
https://github.com/zoffixznet/perl6-CoreLab-Tear

#### BUGS

To report bugs or request features, please use
https://github.com/zoffixznet/perl6-CoreLab-Tear/issues

#### AUTHOR

Zoffix Znet (http://perl6.party/)

#### LICENSE

You can use and distribute this module under the terms of the
The Artistic License 2.0. See the `LICENSE` file included in this
distribution for complete details.

The `META6.json` file of this distribution may be distributed and modified
without restrictions or attribution.
