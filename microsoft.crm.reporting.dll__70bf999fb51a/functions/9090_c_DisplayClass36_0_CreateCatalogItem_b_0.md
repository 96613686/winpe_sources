# <>c__DisplayClass36_0::<CreateCatalogItem>b__0

- ea: `0x9090`
- end: `0x90dc`
- name: `<>c__DisplayClass36_0::<CreateCatalogItem>b__0`
- size: `76`
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
0x9090  ldarg.0
0x9091  ldfld    class Microsoft.Crm.Reporting.ReportingServiceProxy <>c__DisplayClass36_0::<>4__this
0x9096  call     instance void Microsoft.Crm.Reporting.ReportingServiceProxy::SetTelemetryCustomProperties()
0x909b  ldarg.0
0x909c  ldarg.0
0x909d  ldfld    class Microsoft.Crm.Reporting.ReportingServiceProxy <>c__DisplayClass36_0::<>4__this
0x90a2  call     instance class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ReportingService2010 Microsoft.Crm.Reporting.ReportingServiceProxy::get_ReportingService()
0x90a7  ldarg.0
0x90a8  ldfld    string <>c__DisplayClass36_0::ItemType
0x90ad  ldarg.0
0x90ae  ldfld    string <>c__DisplayClass36_0::Name
0x90b3  ldarg.0
0x90b4  ldfld    string <>c__DisplayClass36_0::Parent
0x90b9  ldarg.0
0x90ba  ldfld    bool <>c__DisplayClass36_0::Overwrite
0x90bf  ldarg.0
0x90c0  ldfld    unsigned int8[] <>c__DisplayClass36_0::Definition
0x90c5  ldarg.0
0x90c6  ldfld    class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.Property[] <>c__DisplayClass36_0::Properties
0x90cb  ldarg.0
0x90cc  ldflda   class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.Warning[] <>c__DisplayClass36_0::warningsList
0x90d1  callvirt instance class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.CatalogItem [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ReportingService2010::CreateCatalogItem(string, string, string, bool, unsigned int8[], class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.Property[], class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.Warning[]&)
0x90d6  stfld    class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.CatalogItem <>c__DisplayClass36_0::catalogItem
0x90db  ret
```
