# Microsoft.Crm.Service.ObjectModel.ServiceAppointmentService::.ctor

- ea: `0x290`
- end: `0x2a7`
- name: `Microsoft.Crm.Service.ObjectModel.ServiceAppointmentService::.ctor`
- size: `23`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x291`: `ServiceAppointment`

## pseudocode

```c

```

## disassembly

```asm
0x290  ldarg.0
0x291  ldstr    aServiceappoint// "ServiceAppointment"
0x296  call     instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.CommunicationActivityServiceBase::.ctor(string)
0x29b  ldarg.0
0x29c  newobj   instance void [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.ScheduleService::.ctor()
0x2a1  stfld    class [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.ScheduleService Microsoft.Crm.Service.ObjectModel.ServiceAppointmentService::_scheduleService
0x2a6  ret
```
