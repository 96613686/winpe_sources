# Microsoft.Crm.Asynchronous.AvgResourceCountPerServiceAppointmentCollector::.ctor

- ea: `0x4980`
- end: `0x498e`
- name: `Microsoft.Crm.Asynchronous.AvgResourceCountPerServiceAppointmentCollector::.ctor`
- size: `14`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x5500`

## callees

- `0x42f0`

## pseudocode

```c

```

## disassembly

```asm
0x4980  ldarg.0
0x4981  call     instance void Microsoft.Crm.Asynchronous.SqmCollectorBase::.ctor()
0x4986  ldarg.0
0x4987  ldarg.1
0x4988  stfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration Microsoft.Crm.Asynchronous.AvgResourceCountPerServiceAppointmentCollector::_configuration
0x498d  ret
```
