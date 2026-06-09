# <ConstructModelProperties>d__5::<>m__Finally1

- ea: `0x53e0`
- end: `0x53fb`
- name: `<ConstructModelProperties>d__5::<>m__Finally1`
- size: `27`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x52e0`
- `0x5300`

## callees

- `0x53e0`

## pseudocode

```c

```

## disassembly

```asm
0x53e0  ldarg.0
0x53e1  ldc.i4.m1
0x53e2  stfld    int32 <ConstructModelProperties>d__5::<>1__state
0x53e7  ldarg.0
0x53e8  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [mscorlib]System.Reflection.PropertyInfo> <ConstructModelProperties>d__5::<>7__wrap1
0x53ed  brfalse.s loc_53FA
0x53ef  ldarg.0
0x53f0  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [mscorlib]System.Reflection.PropertyInfo> <ConstructModelProperties>d__5::<>7__wrap1
0x53f5  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x53fa  ret
```
