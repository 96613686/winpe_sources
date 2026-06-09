# Microsoft.Crm.Reporting.ReportingServiceProxy::GetProperties

- ea: `0x3330`
- end: `0x3367`
- name: `Microsoft.Crm.Reporting.ReportingServiceProxy::GetProperties`
- size: `55`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x8e50`

## pseudocode

```c

```

## disassembly

```asm
0x3330  newobj   instance void <>c__DisplayClass29_0::.ctor()
0x3335  stloc.0
0x3336  ldloc.0
0x3337  ldarg.0
0x3338  stfld    class Microsoft.Crm.Reporting.ReportingServiceProxy <>c__DisplayClass29_0::<>4__this
0x333d  ldloc.0
0x333e  ldarg.1
0x333f  stfld    string <>c__DisplayClass29_0::ItemPath
0x3344  ldloc.0
0x3345  ldarg.2
0x3346  stfld    class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.Property[] <>c__DisplayClass29_0::Properties
0x334b  ldsfld   class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Reporting.ReportingServiceProxy::Logger
0x3350  call     var<u1> class [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetrySingletonActivityType`1<class Microsoft.Crm.Reporting.ReportingServiceGetPropertiesActivityType>::get_Instance()
0x3355  ldloc.0
0x3356  ldftn    instance class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.Property[] <>c__DisplayClass29_0::<GetProperties>b__0()
0x335c  newobj   instance void class [mscorlib]System.Func`1<class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.Property[]>::.ctor(object, native int)
0x3361  call     T0x2B000009
0x3366  ret
```
