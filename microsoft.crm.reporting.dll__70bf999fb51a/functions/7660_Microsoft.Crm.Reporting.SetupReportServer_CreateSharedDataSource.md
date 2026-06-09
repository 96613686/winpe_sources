# Microsoft.Crm.Reporting.SetupReportServer::CreateSharedDataSource

- ea: `0x7660`
- end: `0x7708`
- name: `Microsoft.Crm.Reporting.SetupReportServer::CreateSharedDataSource`
- size: `168`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callees

- `0x47f0`
- `0x4900`
- `0x7660`
- `0x7fd0`
- `0x8000`

## pseudocode

```c

```

## disassembly

```asm
0x7660  ldarg.1
0x7661  ldstr    aOrganizationna// "organizationName"
0x7666  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x766b  ldarg.1
0x766c  newobj   instance void [Microsoft.Crm.ReportObjectModel]Microsoft.Crm.ReportObjectModel.ReportServerOrganizationContext::.ctor(string)
0x7671  stloc.0
0x7672  ldarg.3
0x7673  brfalse.s loc_769C
0x7675  ldarg.2
0x7676  ldstr    aConnectionstri// "connectionString"
0x767b  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x7680  ldarg.0
0x7681  ldloc.0
0x7682  callvirt instance string [Microsoft.Crm.ReportObjectModel]Microsoft.Crm.ReportObjectModel.ReportServerOrganizationContext::get_ExternalFolderPath()
0x7687  ldarg.2
0x7688  ldc.i4.0
0x7689  call     instance void Microsoft.Crm.Reporting.SetupReportServer::EnsureExternalDataSourceExists(string path, string connectString, valuetype Microsoft.Crm.Reporting.DataProviderType dataProviderType)
0x768e  ldarg.0
0x768f  ldloc.0
0x7690  callvirt instance string [Microsoft.Crm.ReportObjectModel]Microsoft.Crm.ReportObjectModel.ReportServerOrganizationContext::get_ExternalFolderPath()
0x7695  ldarg.1
0x7696  ldc.i4.1
0x7697  call     instance void Microsoft.Crm.Reporting.SetupReportServer::EnsureExternalDataSourceExists(string path, string connectString, valuetype Microsoft.Crm.Reporting.DataProviderType dataProviderType)
0x769c  ldarg.2
0x769d  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x76a2  brtrue.s loc_76A7
0x76a4  ldarg.2
0x76a5  br.s     loc_76AC
0x76a7  ldstr    aDataSource3e5e// "data source={3E5EA418-FCD5-429c-BA95-0E"...
0x76ac  stloc.1
0x76ad  ldarg.0
0x76ae  ldloc.0
0x76af  callvirt instance string [Microsoft.Crm.ReportObjectModel]Microsoft.Crm.ReportObjectModel.ReportServerOrganizationContext::get_InternalFolderPath()
0x76b4  ldloc.1
0x76b5  ldc.i4.0
0x76b6  call     instance void Microsoft.Crm.Reporting.SetupReportServer::EnsureDataSourceExists(string path, string connectString, valuetype Microsoft.Crm.Reporting.DataProviderType dataProviderType)
0x76bb  ldarg.0
0x76bc  ldloc.0
0x76bd  callvirt instance string [Microsoft.Crm.ReportObjectModel]Microsoft.Crm.ReportObjectModel.ReportServerOrganizationContext::get_InternalFolderPath()
0x76c2  ldarg.1
0x76c3  ldc.i4.1
0x76c4  call     instance void Microsoft.Crm.Reporting.SetupReportServer::EnsureDataSourceExists(string path, string connectString, valuetype Microsoft.Crm.Reporting.DataProviderType dataProviderType)
0x76c9  ldarg.0
0x76ca  ldloc.0
0x76cb  callvirt instance string [Microsoft.Crm.ReportObjectModel]Microsoft.Crm.ReportObjectModel.ReportServerOrganizationContext::get_CommonFolderPath()
0x76d0  ldloc.1
0x76d1  ldc.i4.0
0x76d2  call     instance void Microsoft.Crm.Reporting.SetupReportServer::EnsureDataSourceExists(string path, string connectString, valuetype Microsoft.Crm.Reporting.DataProviderType dataProviderType)
0x76d7  ldarg.0
0x76d8  ldloc.0
0x76d9  callvirt instance string [Microsoft.Crm.ReportObjectModel]Microsoft.Crm.ReportObjectModel.ReportServerOrganizationContext::get_CommonFolderPath()
0x76de  ldarg.1
0x76df  ldc.i4.1
0x76e0  call     instance void Microsoft.Crm.Reporting.SetupReportServer::EnsureDataSourceExists(string path, string connectString, valuetype Microsoft.Crm.Reporting.DataProviderType dataProviderType)
0x76e5  ldarg.0
0x76e6  ldc.i4.0
0x76e7  callvirt instance bool Microsoft.Crm.Reporting.ReportServer::IsDataConnectorInstalled(valuetype Microsoft.Crm.Reporting.DataProviderType dataProviderType)
0x76ec  brfalse.s loc_76F6
0x76ee  ldarg.0
0x76ef  ldloc.0
0x76f0  ldc.i4.0
0x76f1  call     instance void Microsoft.Crm.Reporting.ReportServer::ConfigureDataConnector(class [Microsoft.Crm.ReportObjectModel]Microsoft.Crm.ReportObjectModel.ReportServerOrganizationContext organizationContext, valuetype Microsoft.Crm.Reporting.DataProviderType dataProviderType)
0x76f6  ldarg.0
0x76f7  ldc.i4.1
0x76f8  callvirt instance bool Microsoft.Crm.Reporting.ReportServer::IsDataConnectorInstalled(valuetype Microsoft.Crm.Reporting.DataProviderType dataProviderType)
0x76fd  brfalse.s loc_7707
0x76ff  ldarg.0
0x7700  ldloc.0
0x7701  ldc.i4.1
0x7702  call     instance void Microsoft.Crm.Reporting.ReportServer::ConfigureDataConnector(class [Microsoft.Crm.ReportObjectModel]Microsoft.Crm.ReportObjectModel.ReportServerOrganizationContext organizationContext, valuetype Microsoft.Crm.Reporting.DataProviderType dataProviderType)
0x7707  ret
```
