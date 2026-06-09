# <>f__AnonymousType3`7::GetHashCode

- ea: `0x9d0`
- end: `0xa77`
- name: `<>f__AnonymousType3`7::GetHashCode`
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
0x9d0  ldc.i4   0xABD330F
0x9d5  ldc.i4   0xA5555529
0x9da  mul
0x9db  call     class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>> class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>>::get_Default()
0x9e0  ldarg.0
0x9e1  ldfld    var<u1> class <>f__AnonymousType3`7<var<u1>, !!T0, var<u1>, void, var<u1>, bool, var<u1>>::<Id>i__Field
0x9e6  callvirt instance int32 class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>>::GetHashCode(var<u1>)
0x9eb  add
0x9ec  ldc.i4   0xA5555529
0x9f1  mul
0x9f2  call     class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>> class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>>::get_Default()
0x9f7  ldarg.0
0x9f8  ldfld    var<u1> class <>f__AnonymousType3`7<var<u1>, !!T0, var<u1>, void, var<u1>, bool, var<u1>>::<Status>i__Field
0x9fd  callvirt instance int32 class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>>::GetHashCode(var<u1>)
0xa02  add
0xa03  ldc.i4   0xA5555529
0xa08  mul
0xa09  call     class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>> class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>>::get_Default()
0xa0e  ldarg.0
0xa0f  ldfld    var<u1> class <>f__AnonymousType3`7<var<u1>, !!T0, var<u1>, void, var<u1>, bool, var<u1>>::<Duration>i__Field
0xa14  callvirt instance int32 class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>>::GetHashCode(var<u1>)
0xa19  add
0xa1a  ldc.i4   0xA5555529
0xa1f  mul
0xa20  call     class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>> class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>>::get_Default()
0xa25  ldarg.0
0xa26  ldfld    var<u1> class <>f__AnonymousType3`7<var<u1>, !!T0, var<u1>, void, var<u1>, bool, var<u1>>::<OutputCount>i__Field
0xa2b  callvirt instance int32 class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>>::GetHashCode(var<u1>)
0xa30  add
0xa31  ldc.i4   0xA5555529
0xa36  mul
0xa37  call     class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>> class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>>::get_Default()
0xa3c  ldarg.0
0xa3d  ldfld    var<u1> class <>f__AnonymousType3`7<var<u1>, !!T0, var<u1>, void, var<u1>, bool, var<u1>>::<ExceptionType>i__Field
0xa42  callvirt instance int32 class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>>::GetHashCode(var<u1>)
0xa47  add
0xa48  ldc.i4   0xA5555529
0xa4d  mul
0xa4e  call     class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>> class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>>::get_Default()
0xa53  ldarg.0
0xa54  ldfld    var<u1> class <>f__AnonymousType3`7<var<u1>, !!T0, var<u1>, void, var<u1>, bool, var<u1>>::<ExceptionMessage>i__Field
0xa59  callvirt instance int32 class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>>::GetHashCode(var<u1>)
0xa5e  add
0xa5f  ldc.i4   0xA5555529
0xa64  mul
0xa65  call     class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>> class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>>::get_Default()
0xa6a  ldarg.0
0xa6b  ldfld    var<u1> class <>f__AnonymousType3`7<var<u1>, !!T0, var<u1>, void, var<u1>, bool, var<u1>>::<Error>i__Field
0xa70  callvirt instance int32 class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>>::GetHashCode(var<u1>)
0xa75  add
0xa76  ret
```
