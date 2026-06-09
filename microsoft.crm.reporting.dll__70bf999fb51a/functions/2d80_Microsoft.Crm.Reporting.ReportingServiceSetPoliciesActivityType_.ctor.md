# Microsoft.Crm.Reporting.ReportingServiceSetPoliciesActivityType::.ctor

- ea: `0x2d80`
- end: `0x2d8e`
- name: `Microsoft.Crm.Reporting.ReportingServiceSetPoliciesActivityType::.ctor`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x2d81`: `ReportingService.SetPolicies`

## pseudocode

```c

```

## disassembly

```asm
0x2d80  ldarg.0
0x2d81  ldstr    aReportingservi_16// "ReportingService.SetPolicies"
0x2d86  ldc.i4.1
0x2d87  ldc.i4.1
0x2d88  call     instance void class [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetrySingletonActivityType`1<class Microsoft.Crm.Reporting.ReportingServiceSetPoliciesActivityType>::.ctor(string, bool, bool)
0x2d8d  ret
```
