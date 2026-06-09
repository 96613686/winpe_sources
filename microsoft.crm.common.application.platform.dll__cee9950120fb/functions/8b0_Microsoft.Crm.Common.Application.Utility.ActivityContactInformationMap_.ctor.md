# Microsoft.Crm.Common.Application.Utility.ActivityContactInformationMap::.ctor

- ea: `0x8b0`
- end: `0x8bf`
- name: `Microsoft.Crm.Common.Application.Utility.ActivityContactInformationMap::.ctor`
- size: `15`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x3f20`

## pseudocode

```c

```

## disassembly

```asm
0x8b0  ldarg.0
0x8b1  ldarg.1
0x8b2  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.EntityAttributeMapBase::.ctor(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0x8b7  ldarg.0
0x8b8  ldarg.2
0x8b9  stfld    string Microsoft.Crm.Common.Application.Utility.ActivityContactInformationMap::_contactPropertyName
0x8be  ret
```
