# Microsoft.Crm.Reporting.ReportServer::IsDataConnectorInstalled

- ea: `0x47f0`
- end: `0x47fe`
- name: `Microsoft.Crm.Reporting.ReportServer::IsDataConnectorInstalled`
- size: `14`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x4900`
- `0x5600`
- `0x7660`

## callees

- `0x4f10`
- `0x4f30`

## pseudocode

```c

```

## disassembly

```asm
0x47f0  ldarg.0
0x47f1  ldarg.0
0x47f2  ldarg.1
0x47f3  call     instance string Microsoft.Crm.Reporting.ReportServer::GetDataExtensionName(valuetype Microsoft.Crm.Reporting.DataProviderType dataProviderType)
0x47f8  call     instance bool Microsoft.Crm.Reporting.ReportServer::IsDataExtensionInstalled(string extensionName)
0x47fd  ret
```
