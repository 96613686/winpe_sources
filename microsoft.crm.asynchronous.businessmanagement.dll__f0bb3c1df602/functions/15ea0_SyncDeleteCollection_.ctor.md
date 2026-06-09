# SyncDeleteCollection::.ctor

- ea: `0x15ea0`
- end: `0x15ebd`
- name: `SyncDeleteCollection::.ctor`
- size: `29`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x62c0`
- `0x67f0`
- `0x6900`
- `0x6b70`

## pseudocode

```c

```

## disassembly

```asm
0x15ea0  ldarg.0
0x15ea1  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Data>::.ctor()
0x15ea6  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Data> SyncDeleteCollection::deleteAppointmentsByUserId
0x15eab  ldarg.0
0x15eac  newobj   instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<valuetype [mscorlib]System.Guid>::.ctor()
0x15eb1  stfld    class [mscorlib]System.Collections.ObjectModel.Collection`1<valuetype [mscorlib]System.Guid> SyncDeleteCollection::deleteMappingIds
0x15eb6  ldarg.0
0x15eb7  call     instance void [mscorlib]System.Object::.ctor()
0x15ebc  ret
```
