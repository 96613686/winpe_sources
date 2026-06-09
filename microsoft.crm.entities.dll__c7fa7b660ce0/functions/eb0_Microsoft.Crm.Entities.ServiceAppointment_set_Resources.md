# Microsoft.Crm.Entities.ServiceAppointment::set_Resources

- ea: `0xeb0`
- end: `0xeba`
- name: `Microsoft.Crm.Entities.ServiceAppointment::set_Resources`
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
0xeb0  ldarg.0
0xeb1  ldc.i4.s 0xA
0xeb3  ldarg.1
0xeb4  call     instance void Microsoft.Crm.Entities.CommunicationActivity::SetActivityParties(valuetype Microsoft.Crm.Entities.ParticipationType participationType, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection parties)
0xeb9  ret
```
