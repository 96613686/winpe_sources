# Microsoft.Crm.Reporting.ReportingServiceListRolesActivityType::.ctor

- ea: `0x2de0`
- end: `0x2dee`
- name: `Microsoft.Crm.Reporting.ReportingServiceListRolesActivityType::.ctor`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x2de1`: `ReportingService.ListRoles`

## pseudocode

```c

```

## disassembly

```asm
0x2de0  ldarg.0
0x2de1  ldstr    aReportingservi_19// "ReportingService.ListRoles"
0x2de6  ldc.i4.1
0x2de7  ldc.i4.1
0x2de8  call     instance void class [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetrySingletonActivityType`1<class Microsoft.Crm.Reporting.ReportingServiceListRolesActivityType>::.ctor(string, bool, bool)
0x2ded  ret
```
