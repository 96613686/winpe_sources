# <>c__DisplayClass22_0::<DeleteItem>b__0

- ea: `0x8c00`
- end: `0x8c22`
- name: `<>c__DisplayClass22_0::<DeleteItem>b__0`
- size: `34`
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
0x8c00  ldarg.0
0x8c01  ldfld    class Microsoft.Crm.Reporting.ReportingServiceProxy <>c__DisplayClass22_0::<>4__this
0x8c06  call     instance void Microsoft.Crm.Reporting.ReportingServiceProxy::SetTelemetryCustomProperties()
0x8c0b  ldarg.0
0x8c0c  ldfld    class Microsoft.Crm.Reporting.ReportingServiceProxy <>c__DisplayClass22_0::<>4__this
0x8c11  call     instance class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ReportingService2010 Microsoft.Crm.Reporting.ReportingServiceProxy::get_ReportingService()
0x8c16  ldarg.0
0x8c17  ldfld    string <>c__DisplayClass22_0::ItemPath
0x8c1c  callvirt instance void [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ReportingService2010::DeleteItem(string)
0x8c21  ret
```
