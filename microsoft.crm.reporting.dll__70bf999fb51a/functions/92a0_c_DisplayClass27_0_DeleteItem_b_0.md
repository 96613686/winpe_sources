# <>c__DisplayClass27_0::<DeleteItem>b__0

- ea: `0x92a0`
- end: `0x92b7`
- name: `<>c__DisplayClass27_0::<DeleteItem>b__0`
- size: `23`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x260`
- `0x4860`

## pseudocode

```c

```

## disassembly

```asm
0x92a0  ldarg.0
0x92a1  ldfld    class Microsoft.Crm.Reporting.ReportServer <>c__DisplayClass27_0::<>4__this
0x92a6  call     instance class Microsoft.Crm.Reporting.IReportingService Microsoft.Crm.Reporting.ReportServer::get_ReportingService()
0x92ab  ldarg.0
0x92ac  ldfld    string <>c__DisplayClass27_0::path
0x92b1  callvirt instance void Microsoft.Crm.Reporting.IReportingService::DeleteItem(string ItemPath)
0x92b6  ret
```
