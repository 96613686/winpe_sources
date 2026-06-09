# <>f__AnonymousType2`5::Equals

- ea: `0x5f0`
- end: `0x673`
- name: `<>f__AnonymousType2`5::Equals`
- size: `131`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x5f0`

## pseudocode

```c

```

## disassembly

```asm
0x5f0  ldarg.1
0x5f1  isinst   class <>f__AnonymousType2`5<var<u1>, !!T0, var<u1>, void, var<u1>>
0x5f6  stloc.0
0x5f7  ldloc.0
0x5f8  brfalse.s loc_671
0x5fa  call     class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>> class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>>::get_Default()
0x5ff  ldarg.0
0x600  ldfld    var<u1> class <>f__AnonymousType2`5<var<u1>, !!T0, var<u1>, void, var<u1>>::<Id>i__Field
0x605  ldloc.0
0x606  ldfld    var<u1> class <>f__AnonymousType2`5<var<u1>, !!T0, var<u1>, void, var<u1>>::<Id>i__Field
0x60b  callvirt instance bool class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>>::Equals(var<u1>, !!T0)
0x610  brfalse.s loc_671
0x612  call     class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>> class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>>::get_Default()
0x617  ldarg.0
0x618  ldfld    var<u1> class <>f__AnonymousType2`5<var<u1>, !!T0, var<u1>, void, var<u1>>::<Status>i__Field
0x61d  ldloc.0
0x61e  ldfld    var<u1> class <>f__AnonymousType2`5<var<u1>, !!T0, var<u1>, void, var<u1>>::<Status>i__Field
0x623  callvirt instance bool class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>>::Equals(var<u1>, !!T0)
0x628  brfalse.s loc_671
0x62a  call     class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>> class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>>::get_Default()
0x62f  ldarg.0
0x630  ldfld    var<u1> class <>f__AnonymousType2`5<var<u1>, !!T0, var<u1>, void, var<u1>>::<Duration>i__Field
0x635  ldloc.0
0x636  ldfld    var<u1> class <>f__AnonymousType2`5<var<u1>, !!T0, var<u1>, void, var<u1>>::<Duration>i__Field
0x63b  callvirt instance bool class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>>::Equals(var<u1>, !!T0)
0x640  brfalse.s loc_671
0x642  call     class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>> class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>>::get_Default()
0x647  ldarg.0
0x648  ldfld    var<u1> class <>f__AnonymousType2`5<var<u1>, !!T0, var<u1>, void, var<u1>>::<Input>i__Field
0x64d  ldloc.0
0x64e  ldfld    var<u1> class <>f__AnonymousType2`5<var<u1>, !!T0, var<u1>, void, var<u1>>::<Input>i__Field
0x653  callvirt instance bool class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>>::Equals(var<u1>, !!T0)
0x658  brfalse.s loc_671
0x65a  call     class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>> class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>>::get_Default()
0x65f  ldarg.0
0x660  ldfld    var<u1> class <>f__AnonymousType2`5<var<u1>, !!T0, var<u1>, void, var<u1>>::<OutputCount>i__Field
0x665  ldloc.0
0x666  ldfld    var<u1> class <>f__AnonymousType2`5<var<u1>, !!T0, var<u1>, void, var<u1>>::<OutputCount>i__Field
0x66b  callvirt instance bool class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>>::Equals(var<u1>, !!T0)
0x670  ret
0x671  ldc.i4.0
0x672  ret
```
