# Microsoft.Crm.Reporting.ReportingServiceProxy::GetItemHistoryLimit

- ea: `0x32a0`
- end: `0x32fb`
- name: `Microsoft.Crm.Reporting.ReportingServiceProxy::GetItemHistoryLimit`
- size: `91`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x8da0`

## pseudocode

```c

```

## disassembly

```asm
0x32a0  newobj   instance void <>c__DisplayClass27_0::.ctor()
0x32a5  stloc.0
0x32a6  ldloc.0
0x32a7  ldarg.0
0x32a8  stfld    class Microsoft.Crm.Reporting.ReportingServiceProxy <>c__DisplayClass27_0::<>4__this
0x32ad  ldloc.0
0x32ae  ldarg.1
0x32af  stfld    string <>c__DisplayClass27_0::ItemPath
0x32b4  ldloc.0
0x32b5  ldc.i4.0
0x32b6  stfld    bool <>c__DisplayClass27_0::isSystem
0x32bb  ldloc.0
0x32bc  ldc.i4.0
0x32bd  stfld    int32 <>c__DisplayClass27_0::systemLimit
0x32c2  ldloc.0
0x32c3  ldc.i4.0
0x32c4  stfld    int32 <>c__DisplayClass27_0::historyLimit
0x32c9  ldsfld   class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Reporting.ReportingServiceProxy::Logger
0x32ce  call     var<u1> class [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetrySingletonActivityType`1<class Microsoft.Crm.Reporting.ReportingServiceGetItemHistoryLimitActivityType>::get_Instance()
0x32d3  ldloc.0
0x32d4  ldftn    instance void <>c__DisplayClass27_0::<GetItemHistoryLimit>b__0()
0x32da  newobj   instance void [mscorlib]System.Action::.ctor(object, native int)
0x32df  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryExtensions::Execute(class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger, class [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryActivityType, class [mscorlib]System.Action)
0x32e4  ldarg.2
0x32e5  ldloc.0
0x32e6  ldfld    bool <>c__DisplayClass27_0::isSystem
0x32eb  stind.i1
0x32ec  ldarg.3
0x32ed  ldloc.0
0x32ee  ldfld    int32 <>c__DisplayClass27_0::systemLimit
0x32f3  stind.i4
0x32f4  ldloc.0
0x32f5  ldfld    int32 <>c__DisplayClass27_0::historyLimit
0x32fa  ret
```
