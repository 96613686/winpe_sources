# Microsoft.Crm.Entities.ServiceAppointment::get_Resources

- ea: `0xea0`
- end: `0xea9`
- name: `Microsoft.Crm.Entities.ServiceAppointment::get_Resources`
- size: `9`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xee0`

## callees

- `0x340`

## pseudocode

```c

```

## disassembly

```asm
0xea0  ldarg.0
0xea1  ldc.i4.s 0xA
0xea3  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.Entities.CommunicationActivity::GetActivityParties(valuetype Microsoft.Crm.Entities.ParticipationType participationType)
0xea8  ret
```
