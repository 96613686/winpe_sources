# Microsoft.Crm.Reporting.RuntimeReportServer::SetReportCredentials

- ea: `0x5e70`
- end: `0x5ff7`
- name: `Microsoft.Crm.Reporting.RuntimeReportServer::SetReportCredentials`
- size: `391`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x200`
- `0x230`
- `0x240`
- `0x4860`
- `0x4970`
- `0x5e70`

## string_xrefs

- `0x5f0f`: `Calling ReportingService.GetDataSourceContents on: {0}.`
- `0x5ea9`: `Calling ReportingService.GetItemDataSources on: {0}.`
- `0x5fb4`: `Calling ReportingService.SetItemDataSources on: {0}.`

## pseudocode

```c

```

## disassembly

```asm
0x5e70  ldarg.1
0x5e71  ldstr    aReportnameonsr_0// "reportNameOnSrs"
0x5e76  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x5e7b  ldarg.2
0x5e7c  ldstr    aUserid// "userId"
0x5e81  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x5e86  ldarg.3
0x5e87  ldstr    aOrgid// "orgId"
0x5e8c  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x5e91  ldarg.0
0x5e92  ldfld    class [Microsoft.Crm.ReportObjectModel]Microsoft.Crm.ReportObjectModel.ReportServerOrganizationContext Microsoft.Crm.Reporting.RuntimeReportServer::_organizationContext
0x5e97  ldarg.1
0x5e98  ldarg.s  4
0x5e9a  callvirt instance string [Microsoft.Crm.ReportObjectModel]Microsoft.Crm.ReportObjectModel.ReportServerOrganizationContext::GetItemPath(string, bool)
0x5e9f  stloc.0
0x5ea0  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.AutoReimpersonator::.ctor()
0x5ea5  stloc.1
0x5ea6  ldarg.3
0x5ea7  ldc.i4.s 0x20
0x5ea9  ldstr    aCallingReporti_7// "Calling ReportingService.GetItemDataSou"...
0x5eae  ldc.i4.1
0x5eaf  newarr   [mscorlib]System.Object
0x5eb4  dup
0x5eb5  ldc.i4.0
0x5eb6  ldloc.0
0x5eb7  stelem.ref
0x5eb8  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x5ebd  ldarg.0
0x5ebe  call     instance class Microsoft.Crm.Reporting.IReportingService Microsoft.Crm.Reporting.ReportServer::get_ReportingService()
0x5ec3  ldloc.0
0x5ec4  callvirt instance class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.DataSource[] Microsoft.Crm.Reporting.IReportingService::GetItemDataSources(string ItemPath)
0x5ec9  stloc.2
0x5eca  leave.s  loc_5EDF
0x5ecc  stloc.3
0x5ecd  ldarg.0
0x5ece  ldloc.3
0x5ecf  ldstr    aGetitemdatasou// "GetItemDataSources"
0x5ed4  ldc.i4   0x80048321
0x5ed9  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmReportingException Microsoft.Crm.Reporting.ReportServer::CreateCrmReportingException(class [mscorlib]System.Exception innerException, string methodName, int32 errorCode)
0x5ede  throw
0x5edf  ldc.i4.0
0x5ee0  stloc.s  4
0x5ee2  br       loc_5FA7
0x5ee7  ldloc.2
0x5ee8  ldloc.s  4
0x5eea  ldelem.ref
0x5eeb  stloc.s  5
0x5eed  ldnull
0x5eee  stloc.s  6
0x5ef0  ldloc.s  5
0x5ef2  callvirt instance class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.DataSourceDefinitionOrReference [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.DataSource::get_Item()
0x5ef7  isinst   [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.DataSourceReference
0x5efc  brfalse.s loc_5F4E
0x5efe  ldloc.s  5
0x5f00  callvirt instance class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.DataSourceDefinitionOrReference [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.DataSource::get_Item()
0x5f05  castclass [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.DataSourceReference
0x5f0a  stloc.s  7
0x5f0c  ldarg.3
0x5f0d  ldc.i4.s 0x20
0x5f0f  ldstr    aCallingReporti_2// "Calling ReportingService.GetDataSourceC"...
0x5f14  ldc.i4.1
0x5f15  newarr   [mscorlib]System.Object
0x5f1a  dup
0x5f1b  ldc.i4.0
0x5f1c  ldloc.0
0x5f1d  stelem.ref
0x5f1e  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x5f23  ldarg.0
0x5f24  call     instance class Microsoft.Crm.Reporting.IReportingService Microsoft.Crm.Reporting.ReportServer::get_ReportingService()
0x5f29  ldloc.s  7
0x5f2b  callvirt instance string [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.DataSourceReference::get_Reference()
0x5f30  callvirt instance class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.DataSourceDefinition Microsoft.Crm.Reporting.IReportingService::GetDataSourceContents(string DataSource)
0x5f35  stloc.s  6
0x5f37  leave.s  loc_5F5C
0x5f39  stloc.s  8
0x5f3b  ldarg.0
0x5f3c  ldloc.s  8
0x5f3e  ldstr    aGetdatasourcec// "GetDataSourceContents"
0x5f43  ldc.i4   0x8004831A
0x5f48  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmReportingException Microsoft.Crm.Reporting.ReportServer::CreateCrmReportingException(class [mscorlib]System.Exception innerException, string methodName, int32 errorCode)
0x5f4d  throw
0x5f4e  ldloc.s  5
0x5f50  callvirt instance class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.DataSourceDefinitionOrReference [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.DataSource::get_Item()
0x5f55  castclass [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.DataSourceDefinition
0x5f5a  stloc.s  6
0x5f5c  ldloc.s  6
0x5f5e  ldc.i4.1
0x5f5f  callvirt instance void [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.DataSourceDefinition::set_CredentialRetrieval(valuetype [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.CredentialRetrievalEnum)
0x5f64  ldloc.s  6
0x5f66  ldarga.s 2
0x5f68  ldstr    aB// "B"
0x5f6d  call     instance string [mscorlib]System.Guid::ToString(string)
0x5f72  callvirt instance void [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.DataSourceDefinition::set_UserName(string)
0x5f77  ldloc.s  6
0x5f79  ldarga.s 3
0x5f7b  ldstr    aB// "B"
0x5f80  call     instance string [mscorlib]System.Guid::ToString(string)
0x5f85  callvirt instance void [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.DataSourceDefinition::set_Password(string)
0x5f8a  ldloc.s  6
0x5f8c  ldc.i4.0
0x5f8d  callvirt instance void [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.DataSourceDefinition::set_WindowsCredentials(bool)
0x5f92  ldloc.s  5
0x5f94  ldloc.s  6
0x5f96  callvirt instance void [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.DataSource::set_Item(class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.DataSourceDefinitionOrReference)
0x5f9b  ldloc.2
0x5f9c  ldloc.s  4
0x5f9e  ldloc.s  5
0x5fa0  stelem.ref
0x5fa1  ldloc.s  4
0x5fa3  ldc.i4.1
0x5fa4  add
0x5fa5  stloc.s  4
0x5fa7  ldloc.s  4
0x5fa9  ldloc.2
0x5faa  ldlen
0x5fab  conv.i4
0x5fac  blt      loc_5EE7
0x5fb1  ldarg.3
0x5fb2  ldc.i4.s 0x20
0x5fb4  ldstr    aCallingReporti_8// "Calling ReportingService.SetItemDataSou"...
0x5fb9  ldc.i4.1
0x5fba  newarr   [mscorlib]System.Object
0x5fbf  dup
0x5fc0  ldc.i4.0
0x5fc1  ldloc.0
0x5fc2  stelem.ref
0x5fc3  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x5fc8  ldarg.0
0x5fc9  call     instance class Microsoft.Crm.Reporting.IReportingService Microsoft.Crm.Reporting.ReportServer::get_ReportingService()
0x5fce  ldloc.0
0x5fcf  ldloc.2
0x5fd0  callvirt instance void Microsoft.Crm.Reporting.IReportingService::SetItemDataSources(string ItemPath, class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.DataSource[] DataSources)
0x5fd5  leave.s  loc_5FF6
0x5fd7  stloc.s  9
0x5fd9  ldarg.0
0x5fda  ldloc.s  9
0x5fdc  ldstr    aSetitemdatasou// "SetItemDataSources"
0x5fe1  ldc.i4   0x80048322
0x5fe6  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmReportingException Microsoft.Crm.Reporting.ReportServer::CreateCrmReportingException(class [mscorlib]System.Exception innerException, string methodName, int32 errorCode)
0x5feb  throw
0x5fec  ldloc.1
0x5fed  brfalse.s loc_5FF5
0x5fef  ldloc.1
0x5ff0  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5ff5  endfinally
0x5ff6  ret
```
