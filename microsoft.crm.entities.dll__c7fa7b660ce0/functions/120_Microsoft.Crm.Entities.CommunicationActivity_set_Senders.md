# Microsoft.Crm.Entities.CommunicationActivity::set_Senders

- ea: `0x120`
- end: `0x129`
- name: `Microsoft.Crm.Entities.CommunicationActivity::set_Senders`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x350`

## pseudocode

```c

```

## disassembly

```asm
0x120  ldarg.0
0x121  ldc.i4.1
0x122  ldarg.1
0x123  call     instance void Microsoft.Crm.Entities.CommunicationActivity::SetActivityParties(valuetype Microsoft.Crm.Entities.ParticipationType participationType, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection parties)
0x128  ret
```
