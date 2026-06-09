# Microsoft.Crm.Reporting.ReportingServiceProxy::SetDataSourceContents

- ea: `0x3040`
- end: `0x3077`
- name: `Microsoft.Crm.Reporting.ReportingServiceProxy::SetDataSourceContents`
- size: `55`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x8a60`

## pseudocode

```c

```

## disassembly

```asm
0x3040  newobj   instance void <>c__DisplayClass17_0::.ctor()
0x3045  stloc.0
0x3046  ldloc.0
0x3047  ldarg.0
0x3048  stfld    class Microsoft.Crm.Reporting.ReportingServiceProxy <>c__DisplayClass17_0::<>4__this
0x304d  ldloc.0
0x304e  ldarg.1
0x304f  stfld    string <>c__DisplayClass17_0::DataSource
0x3054  ldloc.0
0x3055  ldarg.2
0x3056  stfld    class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.DataSourceDefinition <>c__DisplayClass17_0::Definition
0x305b  ldsfld   class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Reporting.ReportingServiceProxy::Logger
0x3060  call     var<u1> class [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetrySingletonActivityType`1<class Microsoft.Crm.Reporting.ReportingServiceSetDataSourceContentsActivityType>::get_Instance()
0x3065  ldloc.0
0x3066  ldftn    instance void <>c__DisplayClass17_0::<SetDataSourceContents>b__0()
0x306c  newobj   instance void [mscorlib]System.Action::.ctor(object, native int)
0x3071  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryExtensions::Execute(class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger, class [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryActivityType, class [mscorlib]System.Action)
0x3076  ret
```
