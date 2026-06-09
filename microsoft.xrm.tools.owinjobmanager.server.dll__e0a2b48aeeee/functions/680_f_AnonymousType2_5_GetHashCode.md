# <>f__AnonymousType2`5::GetHashCode

- ea: `0x680`
- end: `0x6f9`
- name: `<>f__AnonymousType2`5::GetHashCode`
- size: `121`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c

```

## disassembly

```asm
0x680  ldc.i4   0x970FC308
0x685  ldc.i4   0xA5555529
0x68a  mul
0x68b  call     class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>> class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>>::get_Default()
0x690  ldarg.0
0x691  ldfld    var<u1> class <>f__AnonymousType2`5<var<u1>, !!T0, var<u1>, void, var<u1>>::<Id>i__Field
0x696  callvirt instance int32 class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>>::GetHashCode(var<u1>)
0x69b  add
0x69c  ldc.i4   0xA5555529
0x6a1  mul
0x6a2  call     class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>> class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>>::get_Default()
0x6a7  ldarg.0
0x6a8  ldfld    var<u1> class <>f__AnonymousType2`5<var<u1>, !!T0, var<u1>, void, var<u1>>::<Status>i__Field
0x6ad  callvirt instance int32 class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>>::GetHashCode(var<u1>)
0x6b2  add
0x6b3  ldc.i4   0xA5555529
0x6b8  mul
0x6b9  call     class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>> class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>>::get_Default()
0x6be  ldarg.0
0x6bf  ldfld    var<u1> class <>f__AnonymousType2`5<var<u1>, !!T0, var<u1>, void, var<u1>>::<Duration>i__Field
0x6c4  callvirt instance int32 class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>>::GetHashCode(var<u1>)
0x6c9  add
0x6ca  ldc.i4   0xA5555529
0x6cf  mul
0x6d0  call     class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>> class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>>::get_Default()
0x6d5  ldarg.0
0x6d6  ldfld    var<u1> class <>f__AnonymousType2`5<var<u1>, !!T0, var<u1>, void, var<u1>>::<Input>i__Field
0x6db  callvirt instance int32 class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>>::GetHashCode(var<u1>)
0x6e0  add
0x6e1  ldc.i4   0xA5555529
0x6e6  mul
0x6e7  call     class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>> class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>>::get_Default()
0x6ec  ldarg.0
0x6ed  ldfld    var<u1> class <>f__AnonymousType2`5<var<u1>, !!T0, var<u1>, void, var<u1>>::<OutputCount>i__Field
0x6f2  callvirt instance int32 class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>>::GetHashCode(var<u1>)
0x6f7  add
0x6f8  ret
```
