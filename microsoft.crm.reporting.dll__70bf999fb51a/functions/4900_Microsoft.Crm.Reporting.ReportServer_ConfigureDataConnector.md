# Microsoft.Crm.Reporting.ReportServer::ConfigureDataConnector

- ea: `0x4900`
- end: `0x4958`
- name: `Microsoft.Crm.Reporting.ReportServer::ConfigureDataConnector`
- size: `88`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x5920`
- `0x7660`

## callees

- `0x47f0`
- `0x4900`
- `0x4be0`
- `0x4d00`
- `0x4ef0`
- `0x4f10`

## pseudocode

```c

```

## disassembly

```asm
0x4900  ldarg.0
0x4901  ldarg.2
0x4902  callvirt instance bool Microsoft.Crm.Reporting.ReportServer::IsDataConnectorInstalled(valuetype Microsoft.Crm.Reporting.DataProviderType dataProviderType)
0x4907  brtrue.s loc_491A
0x4909  ldc.i4   0x80040492
0x490e  ldc.i4.0
0x490f  newarr   [mscorlib]System.Object
0x4914  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x4919  throw
0x491a  ldarg.0
0x491b  ldarg.1
0x491c  ldarg.2
0x491d  callvirt instance bool Microsoft.Crm.Reporting.ReportServer::IsDataConnectorConfigured(class [Microsoft.Crm.ReportObjectModel]Microsoft.Crm.ReportObjectModel.ReportServerOrganizationContext organizationContext, valuetype Microsoft.Crm.Reporting.DataProviderType dataProviderType)
0x4922  brfalse.s loc_4925
0x4924  ret
0x4925  ldarg.0
0x4926  ldarg.2
0x4927  call     instance string Microsoft.Crm.Reporting.ReportServer::GetSharedDataSourceName(valuetype Microsoft.Crm.Reporting.DataProviderType dataProviderType)
0x492c  stloc.0
0x492d  ldarg.0
0x492e  ldarg.2
0x492f  call     instance string Microsoft.Crm.Reporting.ReportServer::GetDataExtensionName(valuetype Microsoft.Crm.Reporting.DataProviderType dataProviderType)
0x4934  stloc.1
0x4935  ldarg.1
0x4936  ldloc.0
0x4937  ldc.i4.1
0x4938  callvirt instance string [Microsoft.Crm.ReportObjectModel]Microsoft.Crm.ReportObjectModel.ReportServerOrganizationContext::GetItemPath(string, bool)
0x493d  stloc.2
0x493e  ldarg.0
0x493f  ldloc.2
0x4940  ldloc.1
0x4941  call     instance void Microsoft.Crm.Reporting.ReportServer::SetDataSourceDefinition(string dataSourcePath, string extensionName)
0x4946  ldarg.1
0x4947  ldloc.0
0x4948  ldc.i4.0
0x4949  callvirt instance string [Microsoft.Crm.ReportObjectModel]Microsoft.Crm.ReportObjectModel.ReportServerOrganizationContext::GetItemPath(string, bool)
0x494e  stloc.3
0x494f  ldarg.0
0x4950  ldloc.3
0x4951  ldloc.1
0x4952  call     instance void Microsoft.Crm.Reporting.ReportServer::SetDataSourceDefinition(string dataSourcePath, string extensionName)
0x4957  ret
```
