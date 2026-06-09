# Microsoft.Crm.Reporting.SetupReportServer::DeleteOrganizationFolder

- ea: `0x7fc0`
- end: `0x7fcd`
- name: `Microsoft.Crm.Reporting.SetupReportServer::DeleteOrganizationFolder`
- size: `13`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x7760`
- `0x8340`

## callees

- `0x4a20`

## pseudocode

```c

```

## disassembly

```asm
0x7fc0  ldarg.0
0x7fc1  ldarg.1
0x7fc2  callvirt instance string [Microsoft.Crm.ReportObjectModel]Microsoft.Crm.ReportObjectModel.ReportServerOrganizationContext::get_ExternalFolderPath()
0x7fc7  call     instance void Microsoft.Crm.Reporting.ReportServer::DeleteItem(string path)
0x7fcc  ret
```
