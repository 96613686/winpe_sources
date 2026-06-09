# Microsoft.Crm.Common.Application.Utility.ActivityPartyMap::.ctor_0

- ea: `0x950`
- end: `0x960`
- name: `Microsoft.Crm.Common.Application.Utility.ActivityPartyMap::.ctor_0`
- size: `16`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x3f20`

## callees

- `0x940`

## pseudocode

```c

```

## disassembly

```asm
0x950  ldarg.0
0x951  ldarg.1
0x952  ldarg.2
0x953  call     instance void Microsoft.Crm.Common.Application.Utility.ActivityPartyMap::.ctor(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType targetEntityType, string partyParticipationTypeName)
0x958  ldarg.0
0x959  ldarg.3
0x95a  stfld    string Microsoft.Crm.Common.Application.Utility.ActivityPartyMap::_additionalPropertyToSet
0x95f  ret
```
