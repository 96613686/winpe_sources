# Microsoft.Crm.Entities.CommunicationActivity::get_Senders

- ea: `0x110`
- end: `0x118`
- name: `Microsoft.Crm.Entities.CommunicationActivity::get_Senders`
- size: `8`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x340`

## pseudocode

```c

```

## disassembly

```asm
0x110  ldarg.0
0x111  ldc.i4.1
0x112  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.Entities.CommunicationActivity::GetActivityParties(valuetype Microsoft.Crm.Entities.ParticipationType participationType)
0x117  ret
```
