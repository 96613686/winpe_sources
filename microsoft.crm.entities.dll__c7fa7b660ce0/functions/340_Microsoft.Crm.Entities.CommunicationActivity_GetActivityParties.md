# Microsoft.Crm.Entities.CommunicationActivity::GetActivityParties

- ea: `0x340`
- end: `0x34d`
- name: `Microsoft.Crm.Entities.CommunicationActivity::GetActivityParties`
- size: `13`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x60`
- `0x80`
- `0x110`
- `0xb70`
- `0xe30`
- `0xea0`
- `0xec0`

## callees

- `0x360`
- `0xc50`

## pseudocode

```c

```

## disassembly

```asm
0x340  ldarg.0
0x341  ldarg.1
0x342  call     instance class Microsoft.Crm.Entities.PartyMappingItem Microsoft.Crm.Entities.CommunicationActivity::GetMappingItem(valuetype Microsoft.Crm.Entities.ParticipationType participationType)
0x347  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.Entities.PartyMappingItem::get_Parties()
0x34c  ret
```
