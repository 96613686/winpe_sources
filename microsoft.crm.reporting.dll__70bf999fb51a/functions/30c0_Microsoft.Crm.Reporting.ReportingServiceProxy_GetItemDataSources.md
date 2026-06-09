# Microsoft.Crm.Reporting.ReportingServiceProxy::GetItemDataSources

- ea: `0x30c0`
- end: `0x30f0`
- name: `Microsoft.Crm.Reporting.ReportingServiceProxy::GetItemDataSources`
- size: `48`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x8b00`

## pseudocode

```c

```

## disassembly

```asm
0x30c0  newobj   instance void <>c__DisplayClass19_0::.ctor()
0x30c5  stloc.0
0x30c6  ldloc.0
0x30c7  ldarg.0
0x30c8  stfld    class Microsoft.Crm.Reporting.ReportingServiceProxy <>c__DisplayClass19_0::<>4__this
0x30cd  ldloc.0
0x30ce  ldarg.1
0x30cf  stfld    string <>c__DisplayClass19_0::ItemPath
0x30d4  ldsfld   class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Reporting.ReportingServiceProxy::Logger
0x30d9  call     var<u1> class [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetrySingletonActivityType`1<class Microsoft.Crm.Reporting.ReportingServiceGetItemDataSourcesActivityType>::get_Instance()
0x30de  ldloc.0
0x30df  ldftn    instance class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.DataSource[] <>c__DisplayClass19_0::<GetItemDataSources>b__0()
0x30e5  newobj   instance void class [mscorlib]System.Func`1<class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.DataSource[]>::.ctor(object, native int)
0x30ea  call     T0x2B000003
0x30ef  ret
```
