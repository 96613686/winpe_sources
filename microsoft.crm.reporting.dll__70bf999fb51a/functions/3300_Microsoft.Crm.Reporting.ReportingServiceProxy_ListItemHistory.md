# Microsoft.Crm.Reporting.ReportingServiceProxy::ListItemHistory

- ea: `0x3300`
- end: `0x3330`
- name: `Microsoft.Crm.Reporting.ReportingServiceProxy::ListItemHistory`
- size: `48`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x8e00`

## pseudocode

```c

```

## disassembly

```asm
0x3300  newobj   instance void <>c__DisplayClass28_0::.ctor()
0x3305  stloc.0
0x3306  ldloc.0
0x3307  ldarg.0
0x3308  stfld    class Microsoft.Crm.Reporting.ReportingServiceProxy <>c__DisplayClass28_0::<>4__this
0x330d  ldloc.0
0x330e  ldarg.1
0x330f  stfld    string <>c__DisplayClass28_0::ItemPath
0x3314  ldsfld   class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Reporting.ReportingServiceProxy::Logger
0x3319  call     var<u1> class [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetrySingletonActivityType`1<class Microsoft.Crm.Reporting.ReportingServiceListItemHistoryActivityType>::get_Instance()
0x331e  ldloc.0
0x331f  ldftn    instance class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ItemHistorySnapshot[] <>c__DisplayClass28_0::<ListItemHistory>b__0()
0x3325  newobj   instance void class [mscorlib]System.Func`1<class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ItemHistorySnapshot[]>::.ctor(object, native int)
0x332a  call     T0x2B000008
0x332f  ret
```
