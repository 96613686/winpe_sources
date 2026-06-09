# <>f__AnonymousType0`7::ToString

- ea: `0x230`
- end: `0x3f3`
- name: `<>f__AnonymousType0`7::ToString`
- size: `451`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x230`

## pseudocode

```c

```

## disassembly

```asm
0x230  ldnull
0x231  ldstr    aId0Status1Dura// "{{ Id = {0}, Status = {1}, Duration = {"...
0x236  ldc.i4.7
0x237  newarr   [mscorlib]System.Object
0x23c  dup
0x23d  ldc.i4.0
0x23e  ldarg.0
0x23f  ldfld    var<u1> class <>f__AnonymousType0`7<var<u1>, !!T0, var<u1>, void, var<u1>, bool, var<u1>>::<Id>i__Field
0x244  stloc.0
0x245  ldloca.s 0
0x247  ldloca.s 1
0x249  initobj  var<u1>
0x24f  ldloc.1
0x250  box      var<u1>
0x255  brtrue.s loc_26B
0x257  ldobj    var<u1>
0x25c  stloc.1
0x25d  ldloca.s 1
0x25f  ldloc.1
0x260  box      var<u1>
0x265  brtrue.s loc_26B
0x267  pop
0x268  ldnull
0x269  br.s     loc_276
0x26b  constrained. var<u1>
0x271  callvirt instance string [mscorlib]System.Object::ToString()
0x276  stelem.ref
0x277  dup
0x278  ldc.i4.1
0x279  ldarg.0
0x27a  ldfld    var<u1> class <>f__AnonymousType0`7<var<u1>, !!T0, var<u1>, void, var<u1>, bool, var<u1>>::<Status>i__Field
0x27f  stloc.2
0x280  ldloca.s 2
0x282  ldloca.s 3
0x284  initobj  var<u1>
0x28a  ldloc.3
0x28b  box      var<u1>
0x290  brtrue.s loc_2A6
0x292  ldobj    var<u1>
0x297  stloc.3
0x298  ldloca.s 3
0x29a  ldloc.3
0x29b  box      var<u1>
0x2a0  brtrue.s loc_2A6
0x2a2  pop
0x2a3  ldnull
0x2a4  br.s     loc_2B1
0x2a6  constrained. var<u1>
0x2ac  callvirt instance string [mscorlib]System.Object::ToString()
0x2b1  stelem.ref
0x2b2  dup
0x2b3  ldc.i4.2
0x2b4  ldarg.0
0x2b5  ldfld    var<u1> class <>f__AnonymousType0`7<var<u1>, !!T0, var<u1>, void, var<u1>, bool, var<u1>>::<Duration>i__Field
0x2ba  stloc.s  4
0x2bc  ldloca.s 4
0x2be  ldloca.s 5
0x2c0  initobj  var<u1>
0x2c6  ldloc.s  5
0x2c8  box      var<u1>
0x2cd  brtrue.s loc_2E5
0x2cf  ldobj    var<u1>
0x2d4  stloc.s  5
0x2d6  ldloca.s 5
0x2d8  ldloc.s  5
0x2da  box      var<u1>
0x2df  brtrue.s loc_2E5
0x2e1  pop
0x2e2  ldnull
0x2e3  br.s     loc_2F0
0x2e5  constrained. var<u1>
0x2eb  callvirt instance string [mscorlib]System.Object::ToString()
0x2f0  stelem.ref
0x2f1  dup
0x2f2  ldc.i4.3
0x2f3  ldarg.0
0x2f4  ldfld    var<u1> class <>f__AnonymousType0`7<var<u1>, !!T0, var<u1>, void, var<u1>, bool, var<u1>>::<Output>i__Field
0x2f9  stloc.s  6
0x2fb  ldloca.s 6
0x2fd  ldloca.s 7
0x2ff  initobj  var<u1>
0x305  ldloc.s  7
0x307  box      var<u1>
0x30c  brtrue.s loc_324
0x30e  ldobj    var<u1>
0x313  stloc.s  7
0x315  ldloca.s 7
0x317  ldloc.s  7
0x319  box      var<u1>
0x31e  brtrue.s loc_324
0x320  pop
0x321  ldnull
0x322  br.s     loc_32F
0x324  constrained. var<u1>
0x32a  callvirt instance string [mscorlib]System.Object::ToString()
0x32f  stelem.ref
0x330  dup
0x331  ldc.i4.4
0x332  ldarg.0
0x333  ldfld    var<u1> class <>f__AnonymousType0`7<var<u1>, !!T0, var<u1>, void, var<u1>, bool, var<u1>>::<ExceptionType>i__Field
0x338  stloc.s  8
0x33a  ldloca.s 8
0x33c  ldloca.s 9
0x33e  initobj  var<u1>
0x344  ldloc.s  9
0x346  box      var<u1>
0x34b  brtrue.s loc_363
0x34d  ldobj    var<u1>
0x352  stloc.s  9
0x354  ldloca.s 9
0x356  ldloc.s  9
0x358  box      var<u1>
0x35d  brtrue.s loc_363
0x35f  pop
0x360  ldnull
0x361  br.s     loc_36E
0x363  constrained. var<u1>
0x369  callvirt instance string [mscorlib]System.Object::ToString()
0x36e  stelem.ref
0x36f  dup
0x370  ldc.i4.5
0x371  ldarg.0
0x372  ldfld    var<u1> class <>f__AnonymousType0`7<var<u1>, !!T0, var<u1>, void, var<u1>, bool, var<u1>>::<ExceptionMessage>i__Field
0x377  stloc.s  0xA
0x379  ldloca.s 0xA
0x37b  ldloca.s 0xB
0x37d  initobj  var<u1>
0x383  ldloc.s  0xB
0x385  box      var<u1>
0x38a  brtrue.s loc_3A2
0x38c  ldobj    var<u1>
0x391  stloc.s  0xB
0x393  ldloca.s 0xB
0x395  ldloc.s  0xB
0x397  box      var<u1>
0x39c  brtrue.s loc_3A2
0x39e  pop
0x39f  ldnull
0x3a0  br.s     loc_3AD
0x3a2  constrained. var<u1>
0x3a8  callvirt instance string [mscorlib]System.Object::ToString()
0x3ad  stelem.ref
0x3ae  dup
0x3af  ldc.i4.6
0x3b0  ldarg.0
0x3b1  ldfld    var<u1> class <>f__AnonymousType0`7<var<u1>, !!T0, var<u1>, void, var<u1>, bool, var<u1>>::<Error>i__Field
0x3b6  stloc.s  0xC
0x3b8  ldloca.s 0xC
0x3ba  ldloca.s 0xD
0x3bc  initobj  var<u1>
0x3c2  ldloc.s  0xD
0x3c4  box      var<u1>
0x3c9  brtrue.s loc_3E1
0x3cb  ldobj    var<u1>
0x3d0  stloc.s  0xD
0x3d2  ldloca.s 0xD
0x3d4  ldloc.s  0xD
0x3d6  box      var<u1>
0x3db  brtrue.s loc_3E1
0x3dd  pop
0x3de  ldnull
0x3df  br.s     loc_3EC
0x3e1  constrained. var<u1>
0x3e7  callvirt instance string [mscorlib]System.Object::ToString()
0x3ec  stelem.ref
0x3ed  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x3f2  ret
```
