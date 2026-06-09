# <>f__AnonymousType0`7::GetHashCode

- ea: `0x180`
- end: `0x227`
- name: `<>f__AnonymousType0`7::GetHashCode`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c

```

## disassembly

```asm
0x180  ldc.i4   0x479A5B42
0x185  ldc.i4   0xA5555529
0x18a  mul
0x18b  call     class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>> class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>>::get_Default()
0x190  ldarg.0
0x191  ldfld    var<u1> class <>f__AnonymousType0`7<var<u1>, !!T0, var<u1>, void, var<u1>, bool, var<u1>>::<Id>i__Field
0x196  callvirt instance int32 class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>>::GetHashCode(var<u1>)
0x19b  add
0x19c  ldc.i4   0xA5555529
0x1a1  mul
0x1a2  call     class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>> class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>>::get_Default()
0x1a7  ldarg.0
0x1a8  ldfld    var<u1> class <>f__AnonymousType0`7<var<u1>, !!T0, var<u1>, void, var<u1>, bool, var<u1>>::<Status>i__Field
0x1ad  callvirt instance int32 class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>>::GetHashCode(var<u1>)
0x1b2  add
0x1b3  ldc.i4   0xA5555529
0x1b8  mul
0x1b9  call     class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>> class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>>::get_Default()
0x1be  ldarg.0
0x1bf  ldfld    var<u1> class <>f__AnonymousType0`7<var<u1>, !!T0, var<u1>, void, var<u1>, bool, var<u1>>::<Duration>i__Field
0x1c4  callvirt instance int32 class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>>::GetHashCode(var<u1>)
0x1c9  add
0x1ca  ldc.i4   0xA5555529
0x1cf  mul
0x1d0  call     class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>> class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>>::get_Default()
0x1d5  ldarg.0
0x1d6  ldfld    var<u1> class <>f__AnonymousType0`7<var<u1>, !!T0, var<u1>, void, var<u1>, bool, var<u1>>::<Output>i__Field
0x1db  callvirt instance int32 class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>>::GetHashCode(var<u1>)
0x1e0  add
0x1e1  ldc.i4   0xA5555529
0x1e6  mul
0x1e7  call     class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>> class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>>::get_Default()
0x1ec  ldarg.0
0x1ed  ldfld    var<u1> class <>f__AnonymousType0`7<var<u1>, !!T0, var<u1>, void, var<u1>, bool, var<u1>>::<ExceptionType>i__Field
0x1f2  callvirt instance int32 class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>>::GetHashCode(var<u1>)
0x1f7  add
0x1f8  ldc.i4   0xA5555529
0x1fd  mul
0x1fe  call     class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>> class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>>::get_Default()
0x203  ldarg.0
0x204  ldfld    var<u1> class <>f__AnonymousType0`7<var<u1>, !!T0, var<u1>, void, var<u1>, bool, var<u1>>::<ExceptionMessage>i__Field
0x209  callvirt instance int32 class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>>::GetHashCode(var<u1>)
0x20e  add
0x20f  ldc.i4   0xA5555529
0x214  mul
0x215  call     class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>> class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>>::get_Default()
0x21a  ldarg.0
0x21b  ldfld    var<u1> class <>f__AnonymousType0`7<var<u1>, !!T0, var<u1>, void, var<u1>, bool, var<u1>>::<Error>i__Field
0x220  callvirt instance int32 class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>>::GetHashCode(var<u1>)
0x225  add
0x226  ret
```
