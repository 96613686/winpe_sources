# Microsoft.Crm.Reporting.ReportingServiceProxy::GetDataSourceContents

- ea: `0x3010`
- end: `0x3040`
- name: `Microsoft.Crm.Reporting.ReportingServiceProxy::GetDataSourceContents`
- size: `48`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x8a10`

## pseudocode

```c

```

## disassembly

```asm
0x3010  newobj   instance void <>c__DisplayClass16_0::.ctor()
0x3015  stloc.0
0x3016  ldloc.0
0x3017  ldarg.0
0x3018  stfld    class Microsoft.Crm.Reporting.ReportingServiceProxy <>c__DisplayClass16_0::<>4__this
0x301d  ldloc.0
0x301e  ldarg.1
0x301f  stfld    string <>c__DisplayClass16_0::DataSource
0x3024  ldsfld   class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Reporting.ReportingServiceProxy::Logger
0x3029  call     var<u1> class [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetrySingletonActivityType`1<class Microsoft.Crm.Reporting.ReportingServiceGetDataSourceContentsActivityType>::get_Instance()
0x302e  ldloc.0
0x302f  ldftn    instance class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.DataSourceDefinition <>c__DisplayClass16_0::<GetDataSourceContents>b__0()
0x3035  newobj   instance void class [mscorlib]System.Func`1<class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.DataSourceDefinition>::.ctor(object, native int)
0x303a  call     T0x2B000002
0x303f  ret
```
