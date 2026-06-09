# Microsoft.Crm.Tools.Admin.UpdateOrganizationInstaller::Update_0

- ea: `0x15c80`
- end: `0x15df8`
- name: `Microsoft.Crm.Tools.Admin.UpdateOrganizationInstaller::Update_0`
- size: `376`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x15be0`

## callees

- `0x22e0`
- `0x41c0`
- `0x15c80`
- `0x15e00`
- `0x161f0`
- `0x16330`
- `0x163d0`

## string_xrefs

- `0x15cb5`: `Organization.Update.OrgAndUsersInConfigDB`
- `0x15cda`: `Organization.Update.OrgAndUsersInConfigDB`
- `0x15d01`: `Organization.Update.OrgInOrgDB`
- `0x15d2d`: `Organization.Update.OrgInOrgDB`
- `0x15d76`: `Organization.Update.Success.Log`
- `0x15da9`: `Organization.Update.Failed.Log`

## pseudocode

```c

```

## disassembly

```asm
0x15c80  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.AutoReimpersonator::.ctor()
0x15c85  stloc.1
0x15c86  ldstr    aUpdatingOrgani_2// "Updating Organization with Id=({0})"
0x15c8b  ldc.i4.1
0x15c8c  newarr   [mscorlib]System.Object
0x15c91  dup
0x15c92  ldc.i4.0
0x15c93  ldarg.1
0x15c94  box      [mscorlib]System.Guid
0x15c99  stelem.ref
0x15c9a  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfoFormat(string, object[])
0x15c9f  call     class [Microsoft.Crm.Core]Microsoft.Crm.LocatorService [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::get_Instance()
0x15ca4  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::Flush()
0x15ca9  newobj   instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmOrganizationService::.ctor()
0x15cae  ldarg.1
0x15caf  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmOrganizationService::Retrieve(valuetype [mscorlib]System.Guid)
0x15cb4  stloc.2
0x15cb5  ldstr    aOrganizationUp_0// "Organization.Update.OrgAndUsersInConfig"...
0x15cba  ldc.i4.0
0x15cbb  newarr   [mscorlib]System.Object
0x15cc0  call     string Microsoft.Crm.Tools.Admin.DMSnapInLibResource::GetString(string name, object[] args)
0x15cc5  ldc.i4.s 0x14
0x15cc7  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.ProgressEventArgs::.ctor(string, int32)
0x15ccc  stloc.0
0x15ccd  ldarg.0
0x15cce  call     instance class [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.IProgressEventSource Microsoft.Crm.Tools.Admin.ProgressExecution::get_OverallProgress()
0x15cd3  ldarg.0
0x15cd4  ldloc.0
0x15cd5  callvirt instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.IProgressEventSource::RaiseProgressChanged(object, class [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.ProgressEventArgs)
0x15cda  ldstr    aOrganizationUp_0// "Organization.Update.OrgAndUsersInConfig"...
0x15cdf  ldc.i4.0
0x15ce0  newarr   [mscorlib]System.Object
0x15ce5  call     string Microsoft.Crm.Tools.Admin.DMSnapInLibResource::GetString(string name, object[] args)
0x15cea  ldc.i4.0
0x15ceb  newarr   [mscorlib]System.Object
0x15cf0  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfoFormat(string, object[])
0x15cf5  ldarg.0
0x15cf6  ldarg.1
0x15cf7  ldloc.2
0x15cf8  ldarg.2
0x15cf9  ldarg.3
0x15cfa  ldarg.s  4
0x15cfc  call     instance void Microsoft.Crm.Tools.Admin.UpdateOrganizationInstaller::UpdateOrganizationAndUsersInConfigDB(valuetype [mscorlib]System.Guid organizationId, class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData organizationData, string friendlyName, string sqlServerName, class [System]System.Uri reportingUrl)
0x15d01  ldstr    aOrganizationUp_1// "Organization.Update.OrgInOrgDB"
0x15d06  ldc.i4.0
0x15d07  newarr   [mscorlib]System.Object
0x15d0c  call     string Microsoft.Crm.Tools.Admin.DMSnapInLibResource::GetString(string name, object[] args)
0x15d11  ldloc.0
0x15d12  callvirt instance int32 [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.ProgressEventArgs::get_Value()
0x15d17  ldc.i4.s 0x32
0x15d19  add
0x15d1a  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.ProgressEventArgs::.ctor(string, int32)
0x15d1f  stloc.0
0x15d20  ldarg.0
0x15d21  call     instance class [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.IProgressEventSource Microsoft.Crm.Tools.Admin.ProgressExecution::get_OverallProgress()
0x15d26  ldarg.0
0x15d27  ldloc.0
0x15d28  callvirt instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.IProgressEventSource::RaiseProgressChanged(object, class [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.ProgressEventArgs)
0x15d2d  ldstr    aOrganizationUp_1// "Organization.Update.OrgInOrgDB"
0x15d32  ldc.i4.0
0x15d33  newarr   [mscorlib]System.Object
0x15d38  call     string Microsoft.Crm.Tools.Admin.DMSnapInLibResource::GetString(string name, object[] args)
0x15d3d  ldc.i4.0
0x15d3e  newarr   [mscorlib]System.Object
0x15d43  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfoFormat(string, object[])
0x15d48  ldarg.0
0x15d49  ldarg.1
0x15d4a  ldloc.2
0x15d4b  ldarg.3
0x15d4c  call     instance void Microsoft.Crm.Tools.Admin.UpdateOrganizationInstaller::GrantAccessToOrgDB(valuetype [mscorlib]System.Guid organizationId, class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData organizationData, string sqlServerName)
0x15d51  ldarg.0
0x15d52  ldarg.1
0x15d53  ldarg.2
0x15d54  call     instance void Microsoft.Crm.Tools.Admin.UpdateOrganizationInstaller::UpdateOrganizationInOrgDB(valuetype [mscorlib]System.Guid organizationId, string friendlyName)
0x15d59  ldarg.0
0x15d5a  ldloc.2
0x15d5b  ldarg.s  4
0x15d5d  call     instance void Microsoft.Crm.Tools.Admin.UpdateOrganizationInstaller::RePublishOrganizationReports(class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData organizationData, class [System]System.Uri reportingUrl)
0x15d62  ldc.i4.1
0x15d63  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.ProgressEventArgs::.ctor(bool)
0x15d68  stloc.0
0x15d69  ldarg.0
0x15d6a  call     instance class [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.IProgressEventSource Microsoft.Crm.Tools.Admin.ProgressExecution::get_OverallProgress()
0x15d6f  ldarg.0
0x15d70  ldloc.0
0x15d71  callvirt instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.IProgressEventSource::RaiseProgressChanged(object, class [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.ProgressEventArgs)
0x15d76  ldstr    aOrganizationUp_2// "Organization.Update.Success.Log"
0x15d7b  ldc.i4.1
0x15d7c  newarr   [mscorlib]System.Object
0x15d81  dup
0x15d82  ldc.i4.0
0x15d83  ldarg.1
0x15d84  box      [mscorlib]System.Guid
0x15d89  stelem.ref
0x15d8a  call     string Microsoft.Crm.Tools.Admin.DMSnapInLibResource::GetString(string name, object[] args)
0x15d8f  ldc.i4.0
0x15d90  newarr   [mscorlib]System.Object
0x15d95  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfoFormat(string, object[])
0x15d9a  leave.s  loc_15DA6
0x15d9c  ldloc.1
0x15d9d  brfalse.s loc_15DA5
0x15d9f  ldloc.1
0x15da0  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x15da5  endfinally
0x15da6  leave.s  loc_15DF7
0x15da8  stloc.3
0x15da9  ldstr    aOrganizationUp_3// "Organization.Update.Failed.Log"
0x15dae  ldc.i4.2
0x15daf  newarr   [mscorlib]System.Object
0x15db4  dup
0x15db5  ldc.i4.0
0x15db6  ldarg.1
0x15db7  box      [mscorlib]System.Guid
0x15dbc  stelem.ref
0x15dbd  dup
0x15dbe  ldc.i4.1
0x15dbf  ldloc.3
0x15dc0  stelem.ref
0x15dc1  call     string Microsoft.Crm.Tools.Admin.DMSnapInLibResource::GetString(string name, object[] args)
0x15dc6  stloc.s  4
0x15dc8  ldloc.s  4
0x15dca  ldc.i4.0
0x15dcb  newarr   [mscorlib]System.Object
0x15dd0  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteError(string, object[])
0x15dd5  ldc.i4.1
0x15dd6  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.ProgressEventArgs::.ctor(bool)
0x15ddb  stloc.0
0x15ddc  ldarg.0
0x15ddd  call     instance class [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.IProgressEventSource Microsoft.Crm.Tools.Admin.ProgressExecution::get_OverallProgress()
0x15de2  ldarg.0
0x15de3  ldloc.0
0x15de4  callvirt instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.IProgressEventSource::RaiseProgressChanged(object, class [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.ProgressEventArgs)
0x15de9  ldloc.s  4
0x15deb  ldloc.3
0x15dec  ldc.i4   0x8004B001
0x15df1  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, class [mscorlib]System.Exception, int32)
0x15df6  throw
0x15df7  ret
```
