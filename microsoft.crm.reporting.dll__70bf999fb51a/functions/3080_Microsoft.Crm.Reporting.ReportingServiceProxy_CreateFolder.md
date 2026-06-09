# Microsoft.Crm.Reporting.ReportingServiceProxy::CreateFolder

- ea: `0x3080`
- end: `0x30be`
- name: `Microsoft.Crm.Reporting.ReportingServiceProxy::CreateFolder`
- size: `62`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x8ab0`

## pseudocode

```c

```

## disassembly

```asm
0x3080  newobj   instance void <>c__DisplayClass18_0::.ctor()
0x3085  stloc.0
0x3086  ldloc.0
0x3087  ldarg.0
0x3088  stfld    class Microsoft.Crm.Reporting.ReportingServiceProxy <>c__DisplayClass18_0::<>4__this
0x308d  ldloc.0
0x308e  ldarg.1
0x308f  stfld    string <>c__DisplayClass18_0::Folder
0x3094  ldloc.0
0x3095  ldarg.2
0x3096  stfld    string <>c__DisplayClass18_0::Parent
0x309b  ldloc.0
0x309c  ldarg.3
0x309d  stfld    class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.Property[] <>c__DisplayClass18_0::Properties
0x30a2  ldsfld   class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Reporting.ReportingServiceProxy::Logger
0x30a7  call     var<u1> class [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetrySingletonActivityType`1<class Microsoft.Crm.Reporting.ReportingServiceCreateFolderActivityType>::get_Instance()
0x30ac  ldloc.0
0x30ad  ldftn    instance class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.CatalogItem <>c__DisplayClass18_0::<CreateFolder>b__0()
0x30b3  newobj   instance void class [mscorlib]System.Func`1<class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.CatalogItem>::.ctor(object, native int)
0x30b8  call     T0x2B000001
0x30bd  ret
```
