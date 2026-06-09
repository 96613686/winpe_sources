# Microsoft.Crm.Entities.PartyMappingItem::.ctor_0

- ea: `0xc30`
- end: `0xc43`
- name: `Microsoft.Crm.Entities.PartyMappingItem::.ctor_0`
- size: `19`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0xd60`

## callees

- `0xc00`
- `0xc30`

## pseudocode

```c

```

## disassembly

```asm
0xc30  ldarg.0
0xc31  ldarg.1
0xc32  ldarg.2
0xc33  call     instance void Microsoft.Crm.Entities.PartyMappingItem::.ctor(valuetype Microsoft.Crm.Entities.ParticipationType participationType, string name)
0xc38  ldarg.3
0xc39  brfalse.s loc_C42
0xc3b  ldarg.0
0xc3c  ldarg.3
0xc3d  stfld    string[] Microsoft.Crm.Entities.PartyMappingItem::_aliasedLogicalNames
0xc42  ret
```
