# Microsoft.Crm.Reporting.ReportingServiceListExtensionsActivityType::.ctor

- ea: `0x2da0`
- end: `0x2dae`
- name: `Microsoft.Crm.Reporting.ReportingServiceListExtensionsActivityType::.ctor`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, service_task, broker_com_uri`

## string_xrefs

- `0x2da1`: `ReportingService.ListExtensions`

## pseudocode

```c

```

## disassembly

```asm
0x2da0  ldarg.0
0x2da1  ldstr    aReportingservi_17// "ReportingService.ListExtensions"
0x2da6  ldc.i4.1
0x2da7  ldc.i4.1
0x2da8  call     instance void class [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetrySingletonActivityType`1<class Microsoft.Crm.Reporting.ReportingServiceListExtensionsActivityType>::.ctor(string, bool, bool)
0x2dad  ret
```
