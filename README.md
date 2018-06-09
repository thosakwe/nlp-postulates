# nlp?
This project aims to create a fully functional system for understanding a
naturalistic constructed language named, for the purposes of this project,
"Reggie."

More or less, it's an attempt to validate a theory of linguistics that
popped into my head last night before bed.

As complicated as this document might seem, it really is an extreme
simplification of the many, many intricacies of linguistics that I may never
understand.

I probably did not "discover" any of the things in this document, even though
they may be new to me.

# Concept Machines
Let's define a *concept machine* as any system that is capable of associating
arbitrary *attributes* with arbitrary objects.

A concept machine takes one input at a time, processes said input, and then
associates attributes described in the input to an object described in the input.

For a specific concept machine, we will define the function that processes an
input `x` and associates attributes with objects as `C(x)`. We can call this the
*understanding function*, for lack of a better name.

The return value of `C(x)` is a set of all objects in the universe *known* to the
machine, with their attributes.

Therefore, `ΔC(x)` is the *change* in the state of the known universe as a result of
`C(x)`.

A concept machine can be considered *complete* if, for every input `x` that changes
the state of the known universe to `y`, `C(x) ≡ y`.

Two concept machines, `a` and `b`, are *equivalent* if, for every input `x`, `ΔCa(x) ≡ ΔCb(x)`,
where `Ca` is `a`'s understanding function and `Cb` is `b`'s understanding function.

# The Human Brain
The human brain is a complete concept machine. We can prove this with a simple example:
An image of an apple.

Human eyes provide an input to the brain. The exact format of this unknown, but is irrelevant,
because the result is what matters. Whether seeing an image of an apple, a painting of an
apple, or a physical apple, the brain concludes that the known universe contains an apple.

This "proof," however, brings one very important consideration to attention:

**The definition of a concept machine assumes that all inputs are perfect and accurately
describe objects.**

In practice, though, this is often impossible. Which brings us to...

# Language
For a concept machine `a`, we can define its *language*, `La`, as follows:

For any input `x`, `La ≣ ΔCa(x)`, where `Ca` is `a`'s understanding function.

Therefore, a language is a specific rule set (function!) that defines the relationship between
an input, `x`, and `Δy`, the expected changes in the universe.

## First Law of Regular Languages
A language `L` is *regular* if, and only if, for any concept machine, `a`, that
*understands* `L`, the relationship between `x` and `La` (A.K.A `ΔCa(x)`) is
**linear**. 

That is to say, each input `x` can only be interpreted in one way.

This also implies that the relationship between `x` and `Ca(x)` is quadratic.

There are very few regular languages in the natural world, if any exist at all.
Ostensibly, this is because language evolved well before writing, but that's
outside the scope of this cursory document.

Computer languages, on the other hand, tend to be regular. For example, in Java,
the expression `2 * 2` has exactly one meaning, and can only be interpreted in one
possible way.

## Second Law of Regular Languages
As a rule of thumb, if the rules of a language `L` can be **exhaustively** expressed as
a [context-free grammar](https://en.wikipedia.org/wiki/Context-free_grammar),
then said language `L` is regular.

# Composition
Those familiar with computer science likely have already noticed the inherent similarities
between concept machines and Turing machines.

In practice, both Turing-complete machines and complete concept machines need to be
able to "learn" the meanings of previously-unseen constructs. Otherwise, every
possible input and output must be manually programmed into the machine, which is both
tedious and error-prone.

As with any mathematical function, understanding functions can be composed of
other functions.

Therefore, for understanding functions `f` and `g`, the composite understanding
function `f ∘ g` produces, for any input `x`, the result of computing
`f(g(x))`.

Take, for example, the English sentence `The man is tall and strong.`.
In this sentence, the adjectives `tall` and `strong` can both be considered understanding
functions that apply a single attribute to an arbitrary object. That is to say,
if there is a `tall tree` and a `tall man` in a universe, then both the `tall tree` and
`tall man` share the common attribute of being `tall`.

Then, `tall and strong` can be considered a composite understanding function that
applies both `tall` and `strong` to an input `x`, which in this example is `man`.

If there were a word, `tall-strong` that translated exactly to `tall and strong`,
then saying `The man is tall-strong` would communicate the exact same meaning.

Composition of understanding functions is the key to building complete
machines that can grow indefinitely.

# Primitives
However, there is an inherent weakness of all languages. If understanding functions
can be compositions of other understanding functions, then there **must** be at least
one understanding function that is *primitive*, and not the composition of anything else.

## Third Law
For a language `L`, a concept machine `a` can only be complete for `L` if
`a` can accurately and exactly produce the state changes defined by all primitives
of `L`.

The inverse of this is, that for a concept machine `a` and language `L`, if
`a` can reproduce all primitives of `L`, then `a` is complete for `L`.

# Vocabulary
A language's *vocabulary* is the set of all understanding functions, primitive or
composite, that can produce a change in the state of a concept machine's known universe.
Because understanding functions can be composite, all vocabularies are infinite in size,
and grow by powers of 2.

By virtue of the [third law](#third-law), a concept machine only needs to handle
primitives of a language to be complete for said language (easier said than done!).

The definition of vocabulary is a problem for most languages interpreted by the human
brain. Because the human brain can only handle so many concepts at a time, composite
functions quickly become hard to follow and nearly impossible to parse.

Imagine that when having to introduce yourself to new people, you had to explain every
word as a composition of other words!

```
Hello! My name is Tobe, and I have a height exceeding 6 feet, which is 6 times one foot,
which is 12 inches, which is <this exact length>, and I am was born in Nigeria, which
means that when I entered in the world, the state of universe involved me being located
in Nigeria, which is a country, which is a group of states...
```

Therefore, most languages have some sort of mechanism to define aliases, which
are short names to refer to some known, other function.

For example, in the C programming language, calling `pow(x, y)` always refers to the
same unit of code, defined in `<math.h>`, which multiplies `x` by itself `y` times.

The fundamental challenge of vocabulary is that to understand a sentence, `s` in
a language `L`, a
concept machine `a` has to know the meaning of every word in `s`, or to say better,
every word in `s` must be one of:
 * A primitive of `L`
 * A composite understanding function of `L`
 * An alias referring to a primitive or composite function of `L`
 
Programming languages can `import` and `include` other vocabularies. Otherwise,
compilers throw errors about undefined symbols.

Human brains read dictionaries to learn the meanings of new words. Without understanding
every word, we can't understand a sentence, though we might understand some aspects of
it.

# Compilers and Brains
Compilers and human brains can be considered complete concept machines, because they
satisfy the above definitions.

Compiler development and linguistics overlap so often because they truly are
applications of the same concepts.

# Natural Language Processing
Ultimately, a computer system that understands a language `L` must not only
understand all of its primitives, but also be provided with a sufficient dictionary,
or some mechanism that lets it auto-generate a sufficient dictionary as it goes along.

Users do not want to have to teach language processors new words. It's tedious,
annoying, and error-prone.

A system that performs *true* NLP, beyond just mere chatbots, has a vast dictionary
that likely spans terabytes, petabytes, or even larger.

Natural languages are both irregular and verbose, because writing did not evolve
until many years after humans had been speaking. There is a reason why babies
can't speak until they've already been on the Earth for multiple years, and why it still
takes humans until their teen and adult years to be fully capable of expression
of emotions and ideas through language. And even still, we are always learning, until their
death.

A conversational NLP system would need to be able to read and draw conclusions on its own,
to understand the state of a complex universe to the same level as a human. Doing so in
less than 18 years, and on commodity hardware, without taking multiple hours just to
compute one sentence, would be a true computational feat, and likely may not
happen for many years.

Not only would such a system need to *truly* understand languages, but for it
to ever be successful in the real world, it would need to be fast enough
to both understand text, but also query the state of the known universe AND
express it as text in the same language, in sub-second time.

# Conclusion
Computers *can* understand natural language, just as humans can. However,
it will take a very long time to do so, and it will likely not be very efficient.

Language is extremely complicated, and oftentimes extremely inefficient. Whereas
computer languages are simple enough to be learned in a day and compiled in milliseconds,
natural languages have hundreds upon hundreds of rules, and that's not even to mention
misspellings, grammatical errors, and proper nouns!!!