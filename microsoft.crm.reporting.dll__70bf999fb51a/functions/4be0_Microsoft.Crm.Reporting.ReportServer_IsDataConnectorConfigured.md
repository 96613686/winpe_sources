# Microsoft.Crm.Reporting.ReportServer::IsDataConnectorConfigured

- ea: `0x4be0`
- end: `0x4c13`
- name: `Microsoft.Crm.Reporting.ReportServer::IsDataConnectorConfigured`
- size: `51`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x4900`
- `0x5c60`
- `0x5c70`

## callees

- `0x4be0`
- `0x4ce0`
- `0x4ef0`
- `0x4f10`

## pseudocode

```c

```

## disassembly

```asm
0x4be0  ldarg.0
0x4be1  ldarg.2
0x4be2  call     instance string Microsoft.Crm.Reporting.ReportServer::GetSharedDataSourceName(valuetype Microsoft.Crm.Reporting.DataProviderType dataProviderType)
0x4be7  stloc.0
0x4be8  ldarg.0
0x4be9  ldarg.2
0x4bea  call     instance string Microsoft.Crm.Reporting.ReportServer::GetDataExtensionName(valuetype Microsoft.Crm.Reporting.DataProviderType dataProviderType)
0x4bef  stloc.1
0x4bf0  ldarg.0
0x4bf1  ldarg.1
0x4bf2  ldloc.0
0x4bf3  ldc.i4.1
0x4bf4  callvirt instance string [Microsoft.Crm.ReportObjectModel]Microsoft.Crm.ReportObjectModel.ReportServerOrganizationContext::GetItemPath(string, bool)
0x4bf9  ldloc.1
0x4bfa  call     instance bool Microsoft.Crm.Reporting.ReportServer::IsDataConnectorConfigured(string dataSourcePath, string extensionName)
0x4bff  brfalse.s loc_4C11
0x4c01  ldarg.0
0x4c02  ldarg.1
0x4c03  ldloc.0
0x4c04  ldc.i4.0
0x4c05  callvirt instance string [Microsoft.Crm.ReportObjectModel]Microsoft.Crm.ReportObjectModel.ReportServerOrganizationContext::GetItemPath(string, bool)
0x4c0a  ldloc.1
0x4c0b  call     instance bool Microsoft.Crm.Reporting.ReportServer::IsDataConnectorConfigured(string dataSourcePath, string extensionName)
0x4c10  ret
0x4c11  ldc.i4.0
0x4c12  ret
```
