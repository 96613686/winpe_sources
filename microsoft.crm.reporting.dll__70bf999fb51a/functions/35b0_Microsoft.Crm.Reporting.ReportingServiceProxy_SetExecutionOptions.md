# Microsoft.Crm.Reporting.ReportingServiceProxy::SetExecutionOptions

- ea: `0x35b0`
- end: `0x35ee`
- name: `Microsoft.Crm.Reporting.ReportingServiceProxy::SetExecutionOptions`
- size: `62`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x9140`

## pseudocode

```c

```

## disassembly

```asm
0x35b0  newobj   instance void <>c__DisplayClass38_0::.ctor()
0x35b5  stloc.0
0x35b6  ldloc.0
0x35b7  ldarg.0
0x35b8  stfld    class Microsoft.Crm.Reporting.ReportingServiceProxy <>c__DisplayClass38_0::<>4__this
0x35bd  ldloc.0
0x35be  ldarg.1
0x35bf  stfld    string <>c__DisplayClass38_0::ItemPath
0x35c4  ldloc.0
0x35c5  ldarg.2
0x35c6  stfld    string <>c__DisplayClass38_0::ExecutionSetting
0x35cb  ldloc.0
0x35cc  ldarg.3
0x35cd  stfld    class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ScheduleDefinitionOrReference <>c__DisplayClass38_0::Item
0x35d2  ldsfld   class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Reporting.ReportingServiceProxy::Logger
0x35d7  call     var<u1> class [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetrySingletonActivityType`1<class Microsoft.Crm.Reporting.ReportingServiceSetExecutionOptionsActivityType>::get_Instance()
0x35dc  ldloc.0
0x35dd  ldftn    instance void <>c__DisplayClass38_0::<SetExecutionOptions>b__0()
0x35e3  newobj   instance void [mscorlib]System.Action::.ctor(object, native int)
0x35e8  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryExtensions::Execute(class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger, class [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryActivityType, class [mscorlib]System.Action)
0x35ed  ret
```
