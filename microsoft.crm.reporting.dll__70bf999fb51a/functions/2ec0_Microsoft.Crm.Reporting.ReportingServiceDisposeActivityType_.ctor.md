# Microsoft.Crm.Reporting.ReportingServiceDisposeActivityType::.ctor

- ea: `0x2ec0`
- end: `0x2ece`
- name: `Microsoft.Crm.Reporting.ReportingServiceDisposeActivityType::.ctor`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x2ec1`: `ReportingService.Dispose`

## pseudocode

```c

```

## disassembly

```asm
0x2ec0  ldarg.0
0x2ec1  ldstr    aReportingservi_26// "ReportingService.Dispose"
0x2ec6  ldc.i4.1
0x2ec7  ldc.i4.1
0x2ec8  call     instance void class [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetrySingletonActivityType`1<class Microsoft.Crm.Reporting.ReportingServiceDisposeActivityType>::.ctor(string, bool, bool)
0x2ecd  ret
```
