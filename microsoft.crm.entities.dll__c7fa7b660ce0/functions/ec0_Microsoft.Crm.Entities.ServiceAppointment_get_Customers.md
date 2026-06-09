# Microsoft.Crm.Entities.ServiceAppointment::get_Customers

- ea: `0xec0`
- end: `0xec9`
- name: `Microsoft.Crm.Entities.ServiceAppointment::get_Customers`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x340`

## pseudocode

```c

```

## disassembly

```asm
0xec0  ldarg.0
0xec1  ldc.i4.s 0xB
0xec3  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.Entities.CommunicationActivity::GetActivityParties(valuetype Microsoft.Crm.Entities.ParticipationType participationType)
0xec8  ret
```
