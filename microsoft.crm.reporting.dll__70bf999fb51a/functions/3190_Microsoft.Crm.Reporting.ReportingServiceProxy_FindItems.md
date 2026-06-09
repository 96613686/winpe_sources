# Microsoft.Crm.Reporting.ReportingServiceProxy::FindItems

- ea: `0x3190`
- end: `0x31d6`
- name: `Microsoft.Crm.Reporting.ReportingServiceProxy::FindItems`
- size: `70`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x8c40`

## pseudocode

```c

```

## disassembly

```asm
0x3190  newobj   instance void <>c__DisplayClass23_0::.ctor()
0x3195  stloc.0
0x3196  ldloc.0
0x3197  ldarg.0
0x3198  stfld    class Microsoft.Crm.Reporting.ReportingServiceProxy <>c__DisplayClass23_0::<>4__this
0x319d  ldloc.0
0x319e  ldarg.1
0x319f  stfld    string <>c__DisplayClass23_0::Folder
0x31a4  ldloc.0
0x31a5  ldarg.2
0x31a6  stfld    valuetype [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.BooleanOperatorEnum <>c__DisplayClass23_0::BooleanOperator
0x31ab  ldloc.0
0x31ac  ldarg.3
0x31ad  stfld    class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.Property[] <>c__DisplayClass23_0::SearchOptions
0x31b2  ldloc.0
0x31b3  ldarg.s  4
0x31b5  stfld    class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.SearchCondition[] <>c__DisplayClass23_0::SearchConditions
0x31ba  ldsfld   class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Reporting.ReportingServiceProxy::Logger
0x31bf  call     var<u1> class [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetrySingletonActivityType`1<class Microsoft.Crm.Reporting.ReportingServiceFindItemsActivityType>::get_Instance()
0x31c4  ldloc.0
0x31c5  ldftn    instance class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.CatalogItem[] <>c__DisplayClass23_0::<FindItems>b__0()
0x31cb  newobj   instance void class [mscorlib]System.Func`1<class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.CatalogItem[]>::.ctor(object, native int)
0x31d0  call     T0x2B000005
0x31d5  ret
```
