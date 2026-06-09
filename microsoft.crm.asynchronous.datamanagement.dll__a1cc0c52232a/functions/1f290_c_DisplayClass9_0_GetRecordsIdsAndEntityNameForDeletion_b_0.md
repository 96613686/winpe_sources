# <>c__DisplayClass9_0::<GetRecordsIdsAndEntityNameForDeletion>b__0

- ea: `0x1f290`
- end: `0x1f2bb`
- name: `<>c__DisplayClass9_0::<GetRecordsIdsAndEntityNameForDeletion>b__0`
- size: `43`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x1f290`

## pseudocode

```c

```

## disassembly

```asm
0x1f290  ldarg.1
0x1f291  brfalse.s loc_1F2BA
0x1f293  ldarg.1
0x1f294  ldlen
0x1f295  brfalse.s loc_1F2BA
0x1f297  ldarg.1
0x1f298  ldc.i4.0
0x1f299  ldelem.ref
0x1f29a  unbox.any [mscorlib]System.Guid
0x1f29f  stloc.0
0x1f2a0  ldarg.0
0x1f2a1  ldarg.1
0x1f2a2  ldc.i4.1
0x1f2a3  ldelem.ref
0x1f2a4  castclass [mscorlib]System.String
0x1f2a9  stfld    string <>c__DisplayClass9_0::_entityName
0x1f2ae  ldarg.0
0x1f2af  ldfld    class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> <>c__DisplayClass9_0::recList
0x1f2b4  ldloc.0
0x1f2b5  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Add(var<u1>)
0x1f2ba  ret
```
