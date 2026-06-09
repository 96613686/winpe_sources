# Microsoft.Crm.Reporting.ReportingServiceProxy::CreateRole

- ea: `0x3470`
- end: `0x34ae`
- name: `Microsoft.Crm.Reporting.ReportingServiceProxy::CreateRole`
- size: `62`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x8fe0`

## pseudocode

```c

```

## disassembly

```asm
0x3470  newobj   instance void <>c__DisplayClass34_0::.ctor()
0x3475  stloc.0
0x3476  ldloc.0
0x3477  ldarg.0
0x3478  stfld    class Microsoft.Crm.Reporting.ReportingServiceProxy <>c__DisplayClass34_0::<>4__this
0x347d  ldloc.0
0x347e  ldarg.1
0x347f  stfld    string <>c__DisplayClass34_0::Name
0x3484  ldloc.0
0x3485  ldarg.2
0x3486  stfld    string <>c__DisplayClass34_0::Description
0x348b  ldloc.0
0x348c  ldarg.3
0x348d  stfld    string[] <>c__DisplayClass34_0::TaskIDs
0x3492  ldsfld   class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Reporting.ReportingServiceProxy::Logger
0x3497  call     var<u1> class [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetrySingletonActivityType`1<class Microsoft.Crm.Reporting.ReportingServiceCreateRoleActivityType>::get_Instance()
0x349c  ldloc.0
0x349d  ldftn    instance void <>c__DisplayClass34_0::<CreateRole>b__0()
0x34a3  newobj   instance void [mscorlib]System.Action::.ctor(object, native int)
0x34a8  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryExtensions::Execute(class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger, class [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryActivityType, class [mscorlib]System.Action)
0x34ad  ret
```
