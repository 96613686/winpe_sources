# <>c__DisplayClass33_0::<ListExtensions>b__0

- ea: `0x8fa0`
- end: `0x8fc2`
- name: `<>c__DisplayClass33_0::<ListExtensions>b__0`
- size: `34`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x2f60`
- `0x36c0`

## pseudocode

```c

```

## disassembly

```asm
0x8fa0  ldarg.0
0x8fa1  ldfld    class Microsoft.Crm.Reporting.ReportingServiceProxy <>c__DisplayClass33_0::<>4__this
0x8fa6  call     instance void Microsoft.Crm.Reporting.ReportingServiceProxy::SetTelemetryCustomProperties()
0x8fab  ldarg.0
0x8fac  ldfld    class Microsoft.Crm.Reporting.ReportingServiceProxy <>c__DisplayClass33_0::<>4__this
0x8fb1  call     instance class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ReportingService2010 Microsoft.Crm.Reporting.ReportingServiceProxy::get_ReportingService()
0x8fb6  ldarg.0
0x8fb7  ldfld    string <>c__DisplayClass33_0::ExtensionType
0x8fbc  callvirt instance class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.Extension[] [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ReportingService2010::ListExtensions(string)
0x8fc1  ret
```
