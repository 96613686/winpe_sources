# <>f__AnonymousType2`5::ToString

- ea: `0x700`
- end: `0x845`
- name: `<>f__AnonymousType2`5::ToString`
- size: `325`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x700`

## pseudocode

```c

```

## disassembly

```asm
0x700  ldnull
0x701  ldstr    aId0Status1Dura_0// "{{ Id = {0}, Status = {1}, Duration = {"...
0x706  ldc.i4.5
0x707  newarr   [mscorlib]System.Object
0x70c  dup
0x70d  ldc.i4.0
0x70e  ldarg.0
0x70f  ldfld    var<u1> class <>f__AnonymousType2`5<var<u1>, !!T0, var<u1>, void, var<u1>>::<Id>i__Field
0x714  stloc.0
0x715  ldloca.s 0
0x717  ldloca.s 1
0x719  initobj  var<u1>
0x71f  ldloc.1
0x720  box      var<u1>
0x725  brtrue.s loc_73B
0x727  ldobj    var<u1>
0x72c  stloc.1
0x72d  ldloca.s 1
0x72f  ldloc.1
0x730  box      var<u1>
0x735  brtrue.s loc_73B
0x737  pop
0x738  ldnull
0x739  br.s     loc_746
0x73b  constrained. var<u1>
0x741  callvirt instance string [mscorlib]System.Object::ToString()
0x746  stelem.ref
0x747  dup
0x748  ldc.i4.1
0x749  ldarg.0
0x74a  ldfld    var<u1> class <>f__AnonymousType2`5<var<u1>, !!T0, var<u1>, void, var<u1>>::<Status>i__Field
0x74f  stloc.2
0x750  ldloca.s 2
0x752  ldloca.s 3
0x754  initobj  var<u1>
0x75a  ldloc.3
0x75b  box      var<u1>
0x760  brtrue.s loc_776
0x762  ldobj    var<u1>
0x767  stloc.3
0x768  ldloca.s 3
0x76a  ldloc.3
0x76b  box      var<u1>
0x770  brtrue.s loc_776
0x772  pop
0x773  ldnull
0x774  br.s     loc_781
0x776  constrained. var<u1>
0x77c  callvirt instance string [mscorlib]System.Object::ToString()
0x781  stelem.ref
0x782  dup
0x783  ldc.i4.2
0x784  ldarg.0
0x785  ldfld    var<u1> class <>f__AnonymousType2`5<var<u1>, !!T0, var<u1>, void, var<u1>>::<Duration>i__Field
0x78a  stloc.s  4
0x78c  ldloca.s 4
0x78e  ldloca.s 5
0x790  initobj  var<u1>
0x796  ldloc.s  5
0x798  box      var<u1>
0x79d  brtrue.s loc_7B5
0x79f  ldobj    var<u1>
0x7a4  stloc.s  5
0x7a6  ldloca.s 5
0x7a8  ldloc.s  5
0x7aa  box      var<u1>
0x7af  brtrue.s loc_7B5
0x7b1  pop
0x7b2  ldnull
0x7b3  br.s     loc_7C0
0x7b5  constrained. var<u1>
0x7bb  callvirt instance string [mscorlib]System.Object::ToString()
0x7c0  stelem.ref
0x7c1  dup
0x7c2  ldc.i4.3
0x7c3  ldarg.0
0x7c4  ldfld    var<u1> class <>f__AnonymousType2`5<var<u1>, !!T0, var<u1>, void, var<u1>>::<Input>i__Field
0x7c9  stloc.s  6
0x7cb  ldloca.s 6
0x7cd  ldloca.s 7
0x7cf  initobj  var<u1>
0x7d5  ldloc.s  7
0x7d7  box      var<u1>
0x7dc  brtrue.s loc_7F4
0x7de  ldobj    var<u1>
0x7e3  stloc.s  7
0x7e5  ldloca.s 7
0x7e7  ldloc.s  7
0x7e9  box      var<u1>
0x7ee  brtrue.s loc_7F4
0x7f0  pop
0x7f1  ldnull
0x7f2  br.s     loc_7FF
0x7f4  constrained. var<u1>
0x7fa  callvirt instance string [mscorlib]System.Object::ToString()
0x7ff  stelem.ref
0x800  dup
0x801  ldc.i4.4
0x802  ldarg.0
0x803  ldfld    var<u1> class <>f__AnonymousType2`5<var<u1>, !!T0, var<u1>, void, var<u1>>::<OutputCount>i__Field
0x808  stloc.s  8
0x80a  ldloca.s 8
0x80c  ldloca.s 9
0x80e  initobj  var<u1>
0x814  ldloc.s  9
0x816  box      var<u1>
0x81b  brtrue.s loc_833
0x81d  ldobj    var<u1>
0x822  stloc.s  9
0x824  ldloca.s 9
0x826  ldloc.s  9
0x828  box      var<u1>
0x82d  brtrue.s loc_833
0x82f  pop
0x830  ldnull
0x831  br.s     loc_83E
0x833  constrained. var<u1>
0x839  callvirt instance string [mscorlib]System.Object::ToString()
0x83e  stelem.ref
0x83f  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x844  ret
```
