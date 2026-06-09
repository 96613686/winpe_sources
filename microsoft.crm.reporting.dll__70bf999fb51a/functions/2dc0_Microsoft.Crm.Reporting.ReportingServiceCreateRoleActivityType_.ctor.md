# Microsoft.Crm.Reporting.ReportingServiceCreateRoleActivityType::.ctor

- ea: `0x2dc0`
- end: `0x2dce`
- name: `Microsoft.Crm.Reporting.ReportingServiceCreateRoleActivityType::.ctor`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x2dc1`: `ReportingService.CreateRole`

## pseudocode

```c

```

## disassembly

```asm
0x2dc0  ldarg.0
0x2dc1  ldstr    aReportingservi_18// "ReportingService.CreateRole"
0x2dc6  ldc.i4.1
0x2dc7  ldc.i4.1
0x2dc8  call     instance void class [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetrySingletonActivityType`1<class Microsoft.Crm.Reporting.ReportingServiceCreateRoleActivityType>::.ctor(string, bool, bool)
0x2dcd  ret
```
