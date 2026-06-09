# <>f__AnonymousType1`2::GetHashCode

- ea: `0x490`
- end: `0x4c4`
- name: `<>f__AnonymousType1`2::GetHashCode`
- size: `52`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c

```

## disassembly

```asm
0x490  ldc.i4   0xAACBB04D
0x495  ldc.i4   0xA5555529
0x49a  mul
0x49b  call     class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>> class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>>::get_Default()
0x4a0  ldarg.0
0x4a1  ldfld    var<u1> class <>f__AnonymousType1`2<var<u1>, !!T0>::<Id>i__Field
0x4a6  callvirt instance int32 class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>>::GetHashCode(var<u1>)
0x4ab  add
0x4ac  ldc.i4   0xA5555529
0x4b1  mul
0x4b2  call     class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>> class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>>::get_Default()
0x4b7  ldarg.0
0x4b8  ldfld    var<u1> class <>f__AnonymousType1`2<var<u1>, !!T0>::<Status>i__Field
0x4bd  callvirt instance int32 class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>>::GetHashCode(var<u1>)
0x4c2  add
0x4c3  ret
```
