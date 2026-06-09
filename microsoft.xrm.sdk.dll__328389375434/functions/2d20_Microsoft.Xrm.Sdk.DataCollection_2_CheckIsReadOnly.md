# Microsoft.Xrm.Sdk.DataCollection`2::CheckIsReadOnly

- ea: `0x2d20`
- end: `0x2d34`
- name: `Microsoft.Xrm.Sdk.DataCollection`2::CheckIsReadOnly`
- size: `20`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x2d20`

## string_xrefs

- `0x2d28`: `The collection is read-only.`

## pseudocode

```c

```

## disassembly

```asm
0x2d20  ldarg.0
0x2d21  callvirt instance bool class Microsoft.Xrm.Sdk.DataCollection`2<var<u1>, !!T0>::get_IsReadOnly()
0x2d26  brfalse.s loc_2D33
0x2d28  ldstr    aTheCollectionI// "The collection is read-only."
0x2d2d  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x2d32  throw
0x2d33  ret
```
