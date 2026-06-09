# Microsoft.Crm.Reporting.ReportingServiceProxy::SetProperties

- ea: `0x3370`
- end: `0x33a7`
- name: `Microsoft.Crm.Reporting.ReportingServiceProxy::SetProperties`
- size: `55`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x8ea0`

## pseudocode

```c

```

## disassembly

```asm
0x3370  newobj   instance void <>c__DisplayClass30_0::.ctor()
0x3375  stloc.0
0x3376  ldloc.0
0x3377  ldarg.0
0x3378  stfld    class Microsoft.Crm.Reporting.ReportingServiceProxy <>c__DisplayClass30_0::<>4__this
0x337d  ldloc.0
0x337e  ldarg.1
0x337f  stfld    string <>c__DisplayClass30_0::ItemPath
0x3384  ldloc.0
0x3385  ldarg.2
0x3386  stfld    class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.Property[] <>c__DisplayClass30_0::Properties
0x338b  ldsfld   class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Reporting.ReportingServiceProxy::Logger
0x3390  call     var<u1> class [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetrySingletonActivityType`1<class Microsoft.Crm.Reporting.ReportingServiceSetPropertiesActivityType>::get_Instance()
0x3395  ldloc.0
0x3396  ldftn    instance void <>c__DisplayClass30_0::<SetProperties>b__0()
0x339c  newobj   instance void [mscorlib]System.Action::.ctor(object, native int)
0x33a1  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryExtensions::Execute(class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger, class [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryActivityType, class [mscorlib]System.Action)
0x33a6  ret
```
