# <>c__DisplayClass26_0::<SetItemParameters>b__0

- ea: `0x8d60`
- end: `0x8d88`
- name: `<>c__DisplayClass26_0::<SetItemParameters>b__0`
- size: `40`
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
0x8d60  ldarg.0
0x8d61  ldfld    class Microsoft.Crm.Reporting.ReportingServiceProxy <>c__DisplayClass26_0::<>4__this
0x8d66  call     instance void Microsoft.Crm.Reporting.ReportingServiceProxy::SetTelemetryCustomProperties()
0x8d6b  ldarg.0
0x8d6c  ldfld    class Microsoft.Crm.Reporting.ReportingServiceProxy <>c__DisplayClass26_0::<>4__this
0x8d71  call     instance class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ReportingService2010 Microsoft.Crm.Reporting.ReportingServiceProxy::get_ReportingService()
0x8d76  ldarg.0
0x8d77  ldfld    string <>c__DisplayClass26_0::ItemPath
0x8d7c  ldarg.0
0x8d7d  ldfld    class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ItemParameter[] <>c__DisplayClass26_0::Parameters
0x8d82  callvirt instance void [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ReportingService2010::SetItemParameters(string, class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ItemParameter[])
0x8d87  ret
```
