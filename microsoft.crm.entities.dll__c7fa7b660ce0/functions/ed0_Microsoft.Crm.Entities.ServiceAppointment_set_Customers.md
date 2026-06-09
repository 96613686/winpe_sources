# Microsoft.Crm.Entities.ServiceAppointment::set_Customers

- ea: `0xed0`
- end: `0xeda`
- name: `Microsoft.Crm.Entities.ServiceAppointment::set_Customers`
- size: `10`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x350`

## pseudocode

```c

```

## disassembly

```asm
0xed0  ldarg.0
0xed1  ldc.i4.s 0xB
0xed3  ldarg.1
0xed4  call     instance void Microsoft.Crm.Entities.CommunicationActivity::SetActivityParties(valuetype Microsoft.Crm.Entities.ParticipationType participationType, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection parties)
0xed9  ret
```
