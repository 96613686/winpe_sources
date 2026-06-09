# Microsoft.Crm.Reporting.ReportingServiceProxy::CreateDataSource

- ea: `0x2fc0`
- end: `0x300e`
- name: `Microsoft.Crm.Reporting.ReportingServiceProxy::CreateDataSource`
- size: `78`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x89b0`

## pseudocode

```c

```

## disassembly

```asm
0x2fc0  newobj   instance void <>c__DisplayClass15_0::.ctor()
0x2fc5  stloc.0
0x2fc6  ldloc.0
0x2fc7  ldarg.0
0x2fc8  stfld    class Microsoft.Crm.Reporting.ReportingServiceProxy <>c__DisplayClass15_0::<>4__this
0x2fcd  ldloc.0
0x2fce  ldarg.1
0x2fcf  stfld    string <>c__DisplayClass15_0::DataSource
0x2fd4  ldloc.0
0x2fd5  ldarg.2
0x2fd6  stfld    string <>c__DisplayClass15_0::Parent
0x2fdb  ldloc.0
0x2fdc  ldarg.3
0x2fdd  stfld    bool <>c__DisplayClass15_0::Overwrite
0x2fe2  ldloc.0
0x2fe3  ldarg.s  4
0x2fe5  stfld    class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.DataSourceDefinition <>c__DisplayClass15_0::Definition
0x2fea  ldloc.0
0x2feb  ldarg.s  5
0x2fed  stfld    class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.Property[] <>c__DisplayClass15_0::Properties
0x2ff2  ldsfld   class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Reporting.ReportingServiceProxy::Logger
0x2ff7  call     var<u1> class [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetrySingletonActivityType`1<class Microsoft.Crm.Reporting.ReportingServiceCreateDataSourceActivityType>::get_Instance()
0x2ffc  ldloc.0
0x2ffd  ldftn    instance class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.CatalogItem <>c__DisplayClass15_0::<CreateDataSource>b__0()
0x3003  newobj   instance void class [mscorlib]System.Func`1<class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.CatalogItem>::.ctor(object, native int)
0x3008  call     T0x2B000001
0x300d  ret
```
