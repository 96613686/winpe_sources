# Microsoft.Crm.Reporting.ReportingServiceProxy::SetItemDataSources

- ea: `0x30f0`
- end: `0x3127`
- name: `Microsoft.Crm.Reporting.ReportingServiceProxy::SetItemDataSources`
- size: `55`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x8b50`

## pseudocode

```c

```

## disassembly

```asm
0x30f0  newobj   instance void <>c__DisplayClass20_0::.ctor()
0x30f5  stloc.0
0x30f6  ldloc.0
0x30f7  ldarg.0
0x30f8  stfld    class Microsoft.Crm.Reporting.ReportingServiceProxy <>c__DisplayClass20_0::<>4__this
0x30fd  ldloc.0
0x30fe  ldarg.1
0x30ff  stfld    string <>c__DisplayClass20_0::ItemPath
0x3104  ldloc.0
0x3105  ldarg.2
0x3106  stfld    class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.DataSource[] <>c__DisplayClass20_0::DataSources
0x310b  ldsfld   class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Reporting.ReportingServiceProxy::Logger
0x3110  call     var<u1> class [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetrySingletonActivityType`1<class Microsoft.Crm.Reporting.ReportingServiceSetItemDataSourcesActivityType>::get_Instance()
0x3115  ldloc.0
0x3116  ldftn    instance void <>c__DisplayClass20_0::<SetItemDataSources>b__0()
0x311c  newobj   instance void [mscorlib]System.Action::.ctor(object, native int)
0x3121  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryExtensions::Execute(class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger, class [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryActivityType, class [mscorlib]System.Action)
0x3126  ret
```
