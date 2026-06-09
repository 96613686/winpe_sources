# <>f__AnonymousType1`2::Equals

- ea: `0x450`
- end: `0x48b`
- name: `<>f__AnonymousType1`2::Equals`
- size: `59`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x450`

## pseudocode

```c

```

## disassembly

```asm
0x450  ldarg.1
0x451  isinst   class <>f__AnonymousType1`2<var<u1>, !!T0>
0x456  stloc.0
0x457  ldloc.0
0x458  brfalse.s loc_489
0x45a  call     class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>> class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>>::get_Default()
0x45f  ldarg.0
0x460  ldfld    var<u1> class <>f__AnonymousType1`2<var<u1>, !!T0>::<Id>i__Field
0x465  ldloc.0
0x466  ldfld    var<u1> class <>f__AnonymousType1`2<var<u1>, !!T0>::<Id>i__Field
0x46b  callvirt instance bool class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>>::Equals(var<u1>, !!T0)
0x470  brfalse.s loc_489
0x472  call     class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>> class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>>::get_Default()
0x477  ldarg.0
0x478  ldfld    var<u1> class <>f__AnonymousType1`2<var<u1>, !!T0>::<Status>i__Field
0x47d  ldloc.0
0x47e  ldfld    var<u1> class <>f__AnonymousType1`2<var<u1>, !!T0>::<Status>i__Field
0x483  callvirt instance bool class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>>::Equals(var<u1>, !!T0)
0x488  ret
0x489  ldc.i4.0
0x48a  ret
```
