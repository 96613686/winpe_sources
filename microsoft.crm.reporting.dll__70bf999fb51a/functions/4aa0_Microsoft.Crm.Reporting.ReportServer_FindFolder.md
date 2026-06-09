# Microsoft.Crm.Reporting.ReportServer::FindFolder

- ea: `0x4aa0`
- end: `0x4aae`
- name: `Microsoft.Crm.Reporting.ReportServer::FindFolder`
- size: `14`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x4800`
- `0x56c0`
- `0x7760`
- `0x8220`
- `0x8370`

## callees

- `0x4ab0`

## pseudocode

```c

```

## disassembly

```asm
0x4aa0  ldarg.0
0x4aa1  ldarg.1
0x4aa2  ldarg.2
0x4aa3  ldstr    aFolder// "Folder"
0x4aa8  call     instance class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.CatalogItem Microsoft.Crm.Reporting.ReportServer::FindItemByName(string searchRoot, string name, string itemType)
0x4aad  ret
```
