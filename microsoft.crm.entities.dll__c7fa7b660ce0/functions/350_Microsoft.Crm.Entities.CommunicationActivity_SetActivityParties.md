# Microsoft.Crm.Entities.CommunicationActivity::SetActivityParties

- ea: `0x350`
- end: `0x35e`
- name: `Microsoft.Crm.Entities.CommunicationActivity::SetActivityParties`
- size: `14`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x70`
- `0x90`
- `0x120`
- `0xb80`
- `0xe40`
- `0xeb0`
- `0xed0`

## callees

- `0x360`
- `0xc60`

## pseudocode

```c

```

## disassembly

```asm
0x350  ldarg.0
0x351  ldarg.1
0x352  call     instance class Microsoft.Crm.Entities.PartyMappingItem Microsoft.Crm.Entities.CommunicationActivity::GetMappingItem(valuetype Microsoft.Crm.Entities.ParticipationType participationType)
0x357  ldarg.2
0x358  callvirt instance void Microsoft.Crm.Entities.PartyMappingItem::set_Parties(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection value)
0x35d  ret
```
