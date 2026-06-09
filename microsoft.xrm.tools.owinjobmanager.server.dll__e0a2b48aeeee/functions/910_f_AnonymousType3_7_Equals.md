# <>f__AnonymousType3`7::Equals

- ea: `0x910`
- end: `0x9c9`
- name: `<>f__AnonymousType3`7::Equals`
- size: `185`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x910`

## pseudocode

```c

```

## disassembly

```asm
0x910  ldarg.1
0x911  isinst   class <>f__AnonymousType3`7<var<u1>, !!T0, var<u1>, void, var<u1>, bool, var<u1>>
0x916  stloc.0
0x917  ldloc.0
0x918  brfalse  loc_9C7
0x91d  call     class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>> class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>>::get_Default()
0x922  ldarg.0
0x923  ldfld    var<u1> class <>f__AnonymousType3`7<var<u1>, !!T0, var<u1>, void, var<u1>, bool, var<u1>>::<Id>i__Field
0x928  ldloc.0
0x929  ldfld    var<u1> class <>f__AnonymousType3`7<var<u1>, !!T0, var<u1>, void, var<u1>, bool, var<u1>>::<Id>i__Field
0x92e  callvirt instance bool class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>>::Equals(var<u1>, !!T0)
0x933  brfalse  loc_9C7
0x938  call     class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>> class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>>::get_Default()
0x93d  ldarg.0
0x93e  ldfld    var<u1> class <>f__AnonymousType3`7<var<u1>, !!T0, var<u1>, void, var<u1>, bool, var<u1>>::<Status>i__Field
0x943  ldloc.0
0x944  ldfld    var<u1> class <>f__AnonymousType3`7<var<u1>, !!T0, var<u1>, void, var<u1>, bool, var<u1>>::<Status>i__Field
0x949  callvirt instance bool class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>>::Equals(var<u1>, !!T0)
0x94e  brfalse.s loc_9C7
0x950  call     class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>> class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>>::get_Default()
0x955  ldarg.0
0x956  ldfld    var<u1> class <>f__AnonymousType3`7<var<u1>, !!T0, var<u1>, void, var<u1>, bool, var<u1>>::<Duration>i__Field
0x95b  ldloc.0
0x95c  ldfld    var<u1> class <>f__AnonymousType3`7<var<u1>, !!T0, var<u1>, void, var<u1>, bool, var<u1>>::<Duration>i__Field
0x961  callvirt instance bool class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>>::Equals(var<u1>, !!T0)
0x966  brfalse.s loc_9C7
0x968  call     class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>> class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>>::get_Default()
0x96d  ldarg.0
0x96e  ldfld    var<u1> class <>f__AnonymousType3`7<var<u1>, !!T0, var<u1>, void, var<u1>, bool, var<u1>>::<OutputCount>i__Field
0x973  ldloc.0
0x974  ldfld    var<u1> class <>f__AnonymousType3`7<var<u1>, !!T0, var<u1>, void, var<u1>, bool, var<u1>>::<OutputCount>i__Field
0x979  callvirt instance bool class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>>::Equals(var<u1>, !!T0)
0x97e  brfalse.s loc_9C7
0x980  call     class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>> class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>>::get_Default()
0x985  ldarg.0
0x986  ldfld    var<u1> class <>f__AnonymousType3`7<var<u1>, !!T0, var<u1>, void, var<u1>, bool, var<u1>>::<ExceptionType>i__Field
0x98b  ldloc.0
0x98c  ldfld    var<u1> class <>f__AnonymousType3`7<var<u1>, !!T0, var<u1>, void, var<u1>, bool, var<u1>>::<ExceptionType>i__Field
0x991  callvirt instance bool class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>>::Equals(var<u1>, !!T0)
0x996  brfalse.s loc_9C7
0x998  call     class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>> class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>>::get_Default()
0x99d  ldarg.0
0x99e  ldfld    var<u1> class <>f__AnonymousType3`7<var<u1>, !!T0, var<u1>, void, var<u1>, bool, var<u1>>::<ExceptionMessage>i__Field
0x9a3  ldloc.0
0x9a4  ldfld    var<u1> class <>f__AnonymousType3`7<var<u1>, !!T0, var<u1>, void, var<u1>, bool, var<u1>>::<ExceptionMessage>i__Field
0x9a9  callvirt instance bool class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>>::Equals(var<u1>, !!T0)
0x9ae  brfalse.s loc_9C7
0x9b0  call     class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>> class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>>::get_Default()
0x9b5  ldarg.0
0x9b6  ldfld    var<u1> class <>f__AnonymousType3`7<var<u1>, !!T0, var<u1>, void, var<u1>, bool, var<u1>>::<Error>i__Field
0x9bb  ldloc.0
0x9bc  ldfld    var<u1> class <>f__AnonymousType3`7<var<u1>, !!T0, var<u1>, void, var<u1>, bool, var<u1>>::<Error>i__Field
0x9c1  callvirt instance bool class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>>::Equals(var<u1>, !!T0)
0x9c6  ret
0x9c7  ldc.i4.0
0x9c8  ret
```
