# <>c__DisplayClass16_0::<GetRecordsIdsAndEntityNameForDeletionForIndependentEntities>b__0

- ea: `0x1f2e0`
- end: `0x1f326`
- name: `<>c__DisplayClass16_0::<GetRecordsIdsAndEntityNameForDeletionForIndependentEntities>b__0`
- size: `70`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x1f2e0`

## pseudocode

```c

```

## disassembly

```asm
0x1f2e0  ldarg.1
0x1f2e1  brfalse.s loc_1F325
0x1f2e3  ldarg.1
0x1f2e4  ldlen
0x1f2e5  brfalse.s loc_1F325
0x1f2e7  ldarg.0
0x1f2e8  ldc.i4.3
0x1f2e9  newarr   [mscorlib]System.Object
0x1f2ee  stfld    object[] <>c__DisplayClass16_0::row
0x1f2f3  ldarg.0
0x1f2f4  ldfld    object[] <>c__DisplayClass16_0::row
0x1f2f9  ldc.i4.0
0x1f2fa  ldarg.1
0x1f2fb  ldc.i4.0
0x1f2fc  ldelem.ref
0x1f2fd  stelem.ref
0x1f2fe  ldarg.0
0x1f2ff  ldfld    object[] <>c__DisplayClass16_0::row
0x1f304  ldc.i4.1
0x1f305  ldarg.1
0x1f306  ldc.i4.1
0x1f307  ldelem.ref
0x1f308  stelem.ref
0x1f309  ldarg.0
0x1f30a  ldfld    object[] <>c__DisplayClass16_0::row
0x1f30f  ldc.i4.2
0x1f310  ldarg.1
0x1f311  ldc.i4.2
0x1f312  ldelem.ref
0x1f313  stelem.ref
0x1f314  ldarg.0
0x1f315  ldfld    class [mscorlib]System.Collections.Generic.List`1<object[]> <>c__DisplayClass16_0::returnValue
0x1f31a  ldarg.0
0x1f31b  ldfld    object[] <>c__DisplayClass16_0::row
0x1f320  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<object[]>::Add(var<u1>)
0x1f325  ret
```
