# <>c__DisplayClass15_0::<CreateDataSource>b__0

- ea: `0x89c0`
- end: `0x89fa`
- name: `<>c__DisplayClass15_0::<CreateDataSource>b__0`
- size: `58`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x2f60`
- `0x36c0`

## pseudocode

```c

```

## disassembly

```asm
0x89c0  ldarg.0
0x89c1  ldfld    class Microsoft.Crm.Reporting.ReportingServiceProxy <>c__DisplayClass15_0::<>4__this
0x89c6  call     instance void Microsoft.Crm.Reporting.ReportingServiceProxy::SetTelemetryCustomProperties()
0x89cb  ldarg.0
0x89cc  ldfld    class Microsoft.Crm.Reporting.ReportingServiceProxy <>c__DisplayClass15_0::<>4__this
0x89d1  call     instance class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ReportingService2010 Microsoft.Crm.Reporting.ReportingServiceProxy::get_ReportingService()
0x89d6  ldarg.0
0x89d7  ldfld    string <>c__DisplayClass15_0::DataSource
0x89dc  ldarg.0
0x89dd  ldfld    string <>c__DisplayClass15_0::Parent
0x89e2  ldarg.0
0x89e3  ldfld    bool <>c__DisplayClass15_0::Overwrite
0x89e8  ldarg.0
0x89e9  ldfld    class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.DataSourceDefinition <>c__DisplayClass15_0::Definition
0x89ee  ldarg.0
0x89ef  ldfld    class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.Property[] <>c__DisplayClass15_0::Properties
0x89f4  callvirt instance class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.CatalogItem [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ReportingService2010::CreateDataSource(string, string, bool, class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.DataSourceDefinition, class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.Property[])
0x89f9  ret
```
