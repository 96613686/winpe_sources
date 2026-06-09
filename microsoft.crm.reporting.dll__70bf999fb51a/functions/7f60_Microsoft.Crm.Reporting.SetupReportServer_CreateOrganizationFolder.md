# Microsoft.Crm.Reporting.SetupReportServer::CreateOrganizationFolder

- ea: `0x7f60`
- end: `0x7f87`
- name: `Microsoft.Crm.Reporting.SetupReportServer::CreateOrganizationFolder`
- size: `39`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x7b80`
- `0x8340`

## callees

- `0x8160`

## pseudocode

```c

```

## disassembly

```asm
0x7f60  ldarg.0
0x7f61  ldstr    asc_C3C6// "/"
0x7f66  ldarg.1
0x7f67  callvirt instance string [Microsoft.Crm.ReportObjectModel]Microsoft.Crm.ReportObjectModel.ReportServerOrganizationContext::get_ExternalFolderName()
0x7f6c  ldc.i4.0
0x7f6d  call     instance bool Microsoft.Crm.Reporting.SetupReportServer::EnsureFolderExists(string parentFolder, string folderName, bool hidden)
0x7f72  pop
0x7f73  ldarg.0
0x7f74  ldarg.1
0x7f75  callvirt instance string [Microsoft.Crm.ReportObjectModel]Microsoft.Crm.ReportObjectModel.ReportServerOrganizationContext::get_ExternalFolderPath()
0x7f7a  ldstr    aCustomreports// "CustomReports"
0x7f7f  ldc.i4.1
0x7f80  call     instance bool Microsoft.Crm.Reporting.SetupReportServer::EnsureFolderExists(string parentFolder, string folderName, bool hidden)
0x7f85  pop
0x7f86  ret
```
