# Microsoft.Crm.Reporting.ReportingServiceProxy::DeleteItem

- ea: `0x3160`
- end: `0x3190`
- name: `Microsoft.Crm.Reporting.ReportingServiceProxy::DeleteItem`
- size: `48`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x8bf0`

## pseudocode

```c

```

## disassembly

```asm
0x3160  newobj   instance void <>c__DisplayClass22_0::.ctor()
0x3165  stloc.0
0x3166  ldloc.0
0x3167  ldarg.0
0x3168  stfld    class Microsoft.Crm.Reporting.ReportingServiceProxy <>c__DisplayClass22_0::<>4__this
0x316d  ldloc.0
0x316e  ldarg.1
0x316f  stfld    string <>c__DisplayClass22_0::ItemPath
0x3174  ldsfld   class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Reporting.ReportingServiceProxy::Logger
0x3179  call     var<u1> class [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetrySingletonActivityType`1<class Microsoft.Crm.Reporting.ReportingServiceDeleteItemActivityType>::get_Instance()
0x317e  ldloc.0
0x317f  ldftn    instance void <>c__DisplayClass22_0::<DeleteItem>b__0()
0x3185  newobj   instance void [mscorlib]System.Action::.ctor(object, native int)
0x318a  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryExtensions::Execute(class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger, class [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryActivityType, class [mscorlib]System.Action)
0x318f  ret
```
