# Microsoft.Crm.Reporting.ReportServer::Dispose_0

- ea: `0x4a90`
- end: `0x4a9f`
- name: `Microsoft.Crm.Reporting.ReportServer::Dispose_0`
- size: `15`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x48f0`
- `0x6740`
- `0x7a20`

## callees

- `0x3a0`
- `0x4a90`

## pseudocode

```c

```

## disassembly

```asm
0x4a90  ldarg.1
0x4a91  brfalse.s loc_4A9E
0x4a93  ldarg.0
0x4a94  ldfld    class Microsoft.Crm.Reporting.IReportingService Microsoft.Crm.Reporting.ReportServer::_rs
0x4a99  callvirt instance void Microsoft.Crm.Reporting.IReportingService::Dispose()
0x4a9e  ret
```
