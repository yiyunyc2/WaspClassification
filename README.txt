Since several "full examples" are too large (and/or too underspecified) for EulerX to handle, they have been processed in smaller parts (and then .gv files have been "stitched together").

Suggested improvements:
1. Allow input visualization BEFORE running reasoner

2. Make MIR-table a product (at least for some encodings), separately from PWs generation step.
=> This should allow a simple RCC-composition step to complete for larger examples
=> LeanEuler might already allow this!? (or else it should be easy to add)
=> EulerX also should do this .. (but probably harder to add)

3. Generate a new visualization product for outputs from MIR tables
=> is there already code in EulerX that does this? Probably yes ..
=> might also think about post-processing the MIR table to generate a tree-like / graph visualization
e.g. employ https://en.wikipedia.org/wiki/Transitive_reduction
but make sure that only transitive relations are reduced!
 a < b;   b < c;    a < c  => we can remove the "a<c" from the visualization (because it's implied by the other two)
 a <= b; b <= c; a < c  => we should remove the last edge (at least not without losing information)
 => as a first step: show all edges (minus the obvious ones!?)

Example why leaving out edges can add to clarity:
https://en.wikipedia.org/wiki/Lattice_(order)

Exercise: Think of this lattice: https://en.wikipedia.org/wiki/Lattice_(order)#/media/File:Lattice_of_the_divisibility_of_60.svg
as a "hierarchy" (of sorts..) and draw it differently in the "EulerX style".
More importantly: can you come up with an interpretation of this "hierarchy" that makes intuitive sense.
 

4. Work on algorithmic improvements: There are many options here, e.g.,
a) adding Parent Coverage to the RCC-composition approach
b) modular reasoning 
