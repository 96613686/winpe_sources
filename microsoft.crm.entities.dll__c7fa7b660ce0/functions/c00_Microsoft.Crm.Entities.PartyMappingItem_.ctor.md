# Microsoft.Crm.Entities.PartyMappingItem::.ctor

- ea: `0xc00`
- end: `0xc21`
- name: `Microsoft.Crm.Entities.PartyMappingItem::.ctor`
- size: `33`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0xc30`
- `0xd40`

## pseudocode

```c

```

## disassembly

```asm
0xc00  ldarg.0
0xc01  call     instance void [mscorlib]System.Object::.ctor()
0xc06  ldarg.0
0xc07  ldarg.1
0xc08  stfld    valuetype Microsoft.Crm.Entities.ParticipationType Microsoft.Crm.Entities.PartyMappingItem::type
0xc0d  ldarg.0
0xc0e  ldarg.2
0xc0f  stfld    string Microsoft.Crm.Entities.PartyMappingItem::logicalName
0xc14  ldarg.0
0xc15  ldc.i4.0
0xc16  newarr   [mscorlib]System.String
0xc1b  stfld    string[] Microsoft.Crm.Entities.PartyMappingItem::_aliasedLogicalNames
0xc20  ret
```
