# Microsoft.Crm.Reporting.RuntimeReportServer::ConfigureDataConnector

- ea: `0x5920`
- end: `0x594a`
- name: `Microsoft.Crm.Reporting.RuntimeReportServer::ConfigureDataConnector`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x4900`

## pseudocode

```c

```

## disassembly

```asm
0x5920  ldarg.0
0x5921  ldarg.0
0x5922  ldfld    class [Microsoft.Crm.ReportObjectModel]Microsoft.Crm.ReportObjectModel.ReportServerOrganizationContext Microsoft.Crm.Reporting.RuntimeReportServer::_organizationContext
0x5927  ldarg.1
0x5928  call     instance void Microsoft.Crm.Reporting.ReportServer::ConfigureDataConnector(class [Microsoft.Crm.ReportObjectModel]Microsoft.Crm.ReportObjectModel.ReportServerOrganizationContext organizationContext, valuetype Microsoft.Crm.Reporting.DataProviderType dataProviderType)
0x592d  ldsfld   class [mscorlib]System.Collections.Generic.IDictionary`2<string, class [mscorlib]System.Collections.Generic.IDictionary`2<valuetype Microsoft.Crm.Reporting.DataProviderType, bool>> Microsoft.Crm.Reporting.RuntimeReportServer::_isDataConnectorConfigured
0x5932  ldarg.0
0x5933  ldfld    class [Microsoft.Crm.ReportObjectModel]Microsoft.Crm.ReportObjectModel.ReportServerOrganizationContext Microsoft.Crm.Reporting.RuntimeReportServer::_organizationContext
0x5938  callvirt instance string [Microsoft.Crm.ReportObjectModel]Microsoft.Crm.ReportObjectModel.ReportServerOrganizationContext::get_OrganizationName()
0x593d  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IDictionary`2<string, class [mscorlib]System.Collections.Generic.IDictionary`2<valuetype Microsoft.Crm.Reporting.DataProviderType, bool>>::get_Item(void)
0x5942  ldarg.1
0x5943  ldc.i4.1
0x5944  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<valuetype Microsoft.Crm.Reporting.DataProviderType, bool>::set_Item(var<u1>, !!T0)
0x5949  ret
```
