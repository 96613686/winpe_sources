# Microsoft.Crm.Reporting.RuntimeReportServer::IsDataConnectorConfigured

- ea: `0x5c60`
- end: `0x5c6e`
- name: `Microsoft.Crm.Reporting.RuntimeReportServer::IsDataConnectorConfigured`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x4be0`

## pseudocode

```c

```

## disassembly

```asm
0x5c60  ldarg.0
0x5c61  ldarg.0
0x5c62  ldfld    class [Microsoft.Crm.ReportObjectModel]Microsoft.Crm.ReportObjectModel.ReportServerOrganizationContext Microsoft.Crm.Reporting.RuntimeReportServer::_organizationContext
0x5c67  ldarg.1
0x5c68  callvirt instance bool Microsoft.Crm.Reporting.ReportServer::IsDataConnectorConfigured(class [Microsoft.Crm.ReportObjectModel]Microsoft.Crm.ReportObjectModel.ReportServerOrganizationContext organizationContext, valuetype Microsoft.Crm.Reporting.DataProviderType dataProviderType)
0x5c6d  ret
```
