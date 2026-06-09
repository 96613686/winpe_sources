# <>f__AnonymousType0`7::Equals

- ea: `0xc0`
- end: `0x179`
- name: `<>f__AnonymousType0`7::Equals`
- size: `185`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0xc0`

## pseudocode

```c

```

## disassembly

```asm
0xc0  ldarg.1
0xc1  isinst   class <>f__AnonymousType0`7<var<u1>, !!T0, var<u1>, void, var<u1>, bool, var<u1>>
0xc6  stloc.0
0xc7  ldloc.0
0xc8  brfalse  loc_177
0xcd  call     class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>> class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>>::get_Default()
0xd2  ldarg.0
0xd3  ldfld    var<u1> class <>f__AnonymousType0`7<var<u1>, !!T0, var<u1>, void, var<u1>, bool, var<u1>>::<Id>i__Field
0xd8  ldloc.0
0xd9  ldfld    var<u1> class <>f__AnonymousType0`7<var<u1>, !!T0, var<u1>, void, var<u1>, bool, var<u1>>::<Id>i__Field
0xde  callvirt instance bool class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>>::Equals(var<u1>, !!T0)
0xe3  brfalse  loc_177
0xe8  call     class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>> class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>>::get_Default()
0xed  ldarg.0
0xee  ldfld    var<u1> class <>f__AnonymousType0`7<var<u1>, !!T0, var<u1>, void, var<u1>, bool, var<u1>>::<Status>i__Field
0xf3  ldloc.0
0xf4  ldfld    var<u1> class <>f__AnonymousType0`7<var<u1>, !!T0, var<u1>, void, var<u1>, bool, var<u1>>::<Status>i__Field
0xf9  callvirt instance bool class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>>::Equals(var<u1>, !!T0)
0xfe  brfalse.s loc_177
0x100  call     class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>> class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>>::get_Default()
0x105  ldarg.0
0x106  ldfld    var<u1> class <>f__AnonymousType0`7<var<u1>, !!T0, var<u1>, void, var<u1>, bool, var<u1>>::<Duration>i__Field
0x10b  ldloc.0
0x10c  ldfld    var<u1> class <>f__AnonymousType0`7<var<u1>, !!T0, var<u1>, void, var<u1>, bool, var<u1>>::<Duration>i__Field
0x111  callvirt instance bool class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>>::Equals(var<u1>, !!T0)
0x116  brfalse.s loc_177
0x118  call     class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>> class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>>::get_Default()
0x11d  ldarg.0
0x11e  ldfld    var<u1> class <>f__AnonymousType0`7<var<u1>, !!T0, var<u1>, void, var<u1>, bool, var<u1>>::<Output>i__Field
0x123  ldloc.0
0x124  ldfld    var<u1> class <>f__AnonymousType0`7<var<u1>, !!T0, var<u1>, void, var<u1>, bool, var<u1>>::<Output>i__Field
0x129  callvirt instance bool class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>>::Equals(var<u1>, !!T0)
0x12e  brfalse.s loc_177
0x130  call     class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>> class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>>::get_Default()
0x135  ldarg.0
0x136  ldfld    var<u1> class <>f__AnonymousType0`7<var<u1>, !!T0, var<u1>, void, var<u1>, bool, var<u1>>::<ExceptionType>i__Field
0x13b  ldloc.0
0x13c  ldfld    var<u1> class <>f__AnonymousType0`7<var<u1>, !!T0, var<u1>, void, var<u1>, bool, var<u1>>::<ExceptionType>i__Field
0x141  callvirt instance bool class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>>::Equals(var<u1>, !!T0)
0x146  brfalse.s loc_177
0x148  call     class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>> class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>>::get_Default()
0x14d  ldarg.0
0x14e  ldfld    var<u1> class <>f__AnonymousType0`7<var<u1>, !!T0, var<u1>, void, var<u1>, bool, var<u1>>::<ExceptionMessage>i__Field
0x153  ldloc.0
0x154  ldfld    var<u1> class <>f__AnonymousType0`7<var<u1>, !!T0, var<u1>, void, var<u1>, bool, var<u1>>::<ExceptionMessage>i__Field
0x159  callvirt instance bool class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>>::Equals(var<u1>, !!T0)
0x15e  brfalse.s loc_177
0x160  call     class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>> class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>>::get_Default()
0x165  ldarg.0
0x166  ldfld    var<u1> class <>f__AnonymousType0`7<var<u1>, !!T0, var<u1>, void, var<u1>, bool, var<u1>>::<Error>i__Field
0x16b  ldloc.0
0x16c  ldfld    var<u1> class <>f__AnonymousType0`7<var<u1>, !!T0, var<u1>, void, var<u1>, bool, var<u1>>::<Error>i__Field
0x171  callvirt instance bool class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>>::Equals(var<u1>, !!T0)
0x176  ret
0x177  ldc.i4.0
0x178  ret
```
