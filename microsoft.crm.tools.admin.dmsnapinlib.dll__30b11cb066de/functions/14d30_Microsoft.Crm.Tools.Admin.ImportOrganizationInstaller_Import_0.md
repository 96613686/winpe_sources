# Microsoft.Crm.Tools.Admin.ImportOrganizationInstaller::Import_0

- ea: `0x14d30`
- end: `0x1528d`
- name: `Microsoft.Crm.Tools.Admin.ImportOrganizationInstaller::Import_0`
- size: `1373`
- prototype: ``
- caller_count: `1`
- callee_count: `27`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x14c00`

## callees

- `0x22e0`
- `0x41c0`
- `0x45a0`
- `0x47e0`
- `0x4820`
- `0x55b0`
- `0x7640`
- `0x82c0`
- `0x9d30`
- `0x9e60`
- `0x10f60`
- `0x13b80`
- `0x14d30`
- `0x15290`
- `0x15350`
- `0x158c0`
- `0x158d0`
- `0x158e0`
- `0x158f0`
- `0x15900`
- `0x15910`
- `0x15920`
- `0x15930`
- `0x17000`
- `0x17a20`
- `0x17bf0`
- `0x17c90`

## string_xrefs

- `0x14f42`: `Organization.Import.UpdateOrganization`
- `0x14f7e`: `Organization.Import.UpdateOrganization`
- `0x150c4`: `Performing GrantServiceAccountAccess on SqlServerName {0} where SqlServerMachineName={1}, reportServerUrl={2}`
- `0x14e18`: `Exception occured when attempting to retrieve security groups from configDB: {0}`
- `0x14e45`: `PrivilegedUserGroupName = {0}, SqlAccessGroupName = {1}, ReportingGroupName = {2}, PrivilegedReportingGroupName = {3}`
- `0x14f6e`: `Update Organization`
- `0x14fbe`: `Verify Directory Objects failed with the following error: {0}`
- `0x15052`: `OrganizationUtility.ApplyDbUpdate`
- `0x1507b`: `Applying database updates`
- `0x150ab`: `Skipped applying database updates as indicated.`
- `0x1522c`: `Organization.Import.Rollback.Failed.Log`

## pseudocode

```c

```

## disassembly

```asm
0x14d30  ldloca.s 0
0x14d32  initobj  Microsoft.Crm.Tools.Admin.OrganizationGroupsInfo
0x14d38  newobj   instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmConfigSettingsService::.ctor()
0x14d3d  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SecurityGroupsData [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmConfigSettingsService::GetSecurityGroups()
0x14d42  stloc.s  4
0x14d44  ldloca.s 0
0x14d46  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x14d4b  ldstr    aGuid0// "<GUID={0}>"
0x14d50  ldc.i4.1
0x14d51  newarr   [mscorlib]System.Object
0x14d56  dup
0x14d57  ldc.i4.0
0x14d58  ldloc.s  4
0x14d5a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SecurityGroupsData::get_PrivilegeUserGroupId()
0x14d5f  stloc.s  5
0x14d61  ldloca.s 5
0x14d63  ldstr    aD// "D"
0x14d68  call     instance string [mscorlib]System.Guid::ToString(string)
0x14d6d  stelem.ref
0x14d6e  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x14d73  call     instance void Microsoft.Crm.Tools.Admin.OrganizationGroupsInfo::set_PrivilegedUserGroupName(string value)
0x14d78  ldloca.s 0
0x14d7a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x14d7f  ldstr    aGuid0// "<GUID={0}>"
0x14d84  ldc.i4.1
0x14d85  newarr   [mscorlib]System.Object
0x14d8a  dup
0x14d8b  ldc.i4.0
0x14d8c  ldloc.s  4
0x14d8e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SecurityGroupsData::get_SqlAccessGroupId()
0x14d93  stloc.s  5
0x14d95  ldloca.s 5
0x14d97  ldstr    aD// "D"
0x14d9c  call     instance string [mscorlib]System.Guid::ToString(string)
0x14da1  stelem.ref
0x14da2  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x14da7  call     instance void Microsoft.Crm.Tools.Admin.OrganizationGroupsInfo::set_SqlAccessGroupName(string value)
0x14dac  ldloca.s 0
0x14dae  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x14db3  ldstr    aGuid0// "<GUID={0}>"
0x14db8  ldc.i4.1
0x14db9  newarr   [mscorlib]System.Object
0x14dbe  dup
0x14dbf  ldc.i4.0
0x14dc0  ldloc.s  4
0x14dc2  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SecurityGroupsData::get_ReportingGroupId()
0x14dc7  stloc.s  5
0x14dc9  ldloca.s 5
0x14dcb  ldstr    aD// "D"
0x14dd0  call     instance string [mscorlib]System.Guid::ToString(string)
0x14dd5  stelem.ref
0x14dd6  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x14ddb  call     instance void Microsoft.Crm.Tools.Admin.OrganizationGroupsInfo::set_ReportingGroupName(string value)
0x14de0  ldloca.s 0
0x14de2  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x14de7  ldstr    aGuid0// "<GUID={0}>"
0x14dec  ldc.i4.1
0x14ded  newarr   [mscorlib]System.Object
0x14df2  dup
0x14df3  ldc.i4.0
0x14df4  ldloc.s  4
0x14df6  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SecurityGroupsData::get_PrivilegeReportGroupId()
0x14dfb  stloc.s  5
0x14dfd  ldloca.s 5
0x14dff  ldstr    aD// "D"
0x14e04  call     instance string [mscorlib]System.Guid::ToString(string)
0x14e09  stelem.ref
0x14e0a  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x14e0f  call     instance void Microsoft.Crm.Tools.Admin.OrganizationGroupsInfo::set_PrivilegedReportingGroupName(string value)
0x14e14  leave.s  loc_14E45
0x14e16  stloc.s  6
0x14e18  ldstr    aExceptionOccur_2// "Exception occured when attempting to re"...
0x14e1d  ldc.i4.1
0x14e1e  newarr   [mscorlib]System.Object
0x14e23  dup
0x14e24  ldc.i4.0
0x14e25  ldloc.s  6
0x14e27  callvirt instance string [mscorlib]System.Exception::get_Message()
0x14e2c  stelem.ref
0x14e2d  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteErrorFormat(string, object[])
0x14e32  ldc.i4   0xC0004D0E
0x14e37  conv.u8
0x14e38  ldc.i4.0
0x14e39  newarr   [mscorlib]System.String
0x14e3e  call     void Microsoft.Crm.Tools.Admin.EventLogHelper::Write(int64 eventId, string[] parameters)
0x14e43  rethrow
0x14e45  ldstr    aPrivilegeduser// "PrivilegedUserGroupName = {0}, SqlAcces"...
0x14e4a  ldc.i4.4
0x14e4b  newarr   [mscorlib]System.Object
0x14e50  dup
0x14e51  ldc.i4.0
0x14e52  ldloca.s 0
0x14e54  call     instance string Microsoft.Crm.Tools.Admin.OrganizationGroupsInfo::get_PrivilegedUserGroupName()
0x14e59  stelem.ref
0x14e5a  dup
0x14e5b  ldc.i4.1
0x14e5c  ldloca.s 0
0x14e5e  call     instance string Microsoft.Crm.Tools.Admin.OrganizationGroupsInfo::get_SqlAccessGroupName()
0x14e63  stelem.ref
0x14e64  dup
0x14e65  ldc.i4.2
0x14e66  ldloca.s 0
0x14e68  call     instance string Microsoft.Crm.Tools.Admin.OrganizationGroupsInfo::get_ReportingGroupName()
0x14e6d  stelem.ref
0x14e6e  dup
0x14e6f  ldc.i4.3
0x14e70  ldloca.s 0
0x14e72  call     instance string Microsoft.Crm.Tools.Admin.OrganizationGroupsInfo::get_PrivilegedReportingGroupName()
0x14e77  stelem.ref
0x14e78  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfoFormat(string, object[])
0x14e7d  ldnull
0x14e7e  stloc.1
0x14e7f  ldnull
0x14e80  stloc.2
0x14e81  ldarg.0
0x14e82  ldfld    bool Microsoft.Crm.Tools.Admin.ImportOrganizationInstaller::IsOnline
0x14e87  brtrue.s loc_14EAD
0x14e89  ldarg.s  7
0x14e8b  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.User>::get_Count()
0x14e90  brtrue.s loc_14EAD
0x14e92  ldstr    aNoUserMappingI// "No user mapping information found. Crea"...
0x14e97  ldc.i4.0
0x14e98  newarr   [mscorlib]System.Object
0x14e9d  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfo(string, object[])
0x14ea2  ldarg.s  4
0x14ea4  ldarg.s  5
0x14ea6  call     class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.User> Microsoft.Crm.Tools.Admin.DBImportHelper::CreateDefaultMapping(string sqlServerName, string databaseName)
0x14eab  starg.s  7
0x14ead  leave.s  loc_14EC8
0x14eaf  stloc.s  7
0x14eb1  ldstr    aAnErrorOccurre_6// "An error occurred while creating defaul"...
0x14eb6  ldc.i4.1
0x14eb7  newarr   [mscorlib]System.Object
0x14ebc  dup
0x14ebd  ldc.i4.0
0x14ebe  ldloc.s  7
0x14ec0  stelem.ref
0x14ec1  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteErrorFormat(string, object[])
0x14ec6  rethrow
0x14ec8  call     class [mscorlib]System.Security.Principal.WindowsIdentity [mscorlib]System.Security.Principal.WindowsIdentity::GetCurrent()
0x14ecd  stloc.s  8
0x14ecf  ldloc.s  8
0x14ed1  callvirt instance string [mscorlib]System.Security.Claims.ClaimsIdentity::get_Name()
0x14ed6  stloc.3
0x14ed7  leave.s  loc_14EE5
0x14ed9  ldloc.s  8
0x14edb  brfalse.s loc_14EE4
0x14edd  ldloc.s  8
0x14edf  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x14ee4  endfinally
0x14ee5  ldarg.1
0x14ee6  ldloc.3
0x14ee7  newobj   instance void Microsoft.Crm.Tools.Admin.MetadataCacheConfigContext::.ctor(valuetype [mscorlib]System.Guid organizationId, string systemUserDomainName)
0x14eec  stloc.s  9
0x14eee  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.AutoReimpersonator::.ctor()
0x14ef3  stloc.s  0xA
0x14ef5  ldstr    aImportOrganiza// "Import Organization ({0})"
0x14efa  ldc.i4.1
0x14efb  newarr   [mscorlib]System.Object
0x14f00  dup
0x14f01  ldc.i4.0
0x14f02  ldarg.2
0x14f03  stelem.ref
0x14f04  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfoFormat(string, object[])
0x14f09  call     class [Microsoft.Crm.Core]Microsoft.Crm.LocatorService [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::get_Instance()
0x14f0e  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::Flush()
0x14f13  ldarg.s  8
0x14f15  brtrue.s loc_14F23
0x14f17  call     class Microsoft.Crm.Tools.Admin.LicenseController Microsoft.Crm.Tools.Admin.LicenseController::get_Instance()
0x14f1c  callvirt instance class Microsoft.Crm.Tools.Admin.MultipleTenancy Microsoft.Crm.Tools.Admin.LicenseController::GetMultipleTenancy()
0x14f21  starg.s  8
0x14f23  ldstr    aMultipletenanc// "multipleTenancy for the deployment is {"...
0x14f28  ldc.i4.1
0x14f29  newarr   [mscorlib]System.Object
0x14f2e  dup
0x14f2f  ldc.i4.0
0x14f30  ldarg.s  8
0x14f32  callvirt instance bool Microsoft.Crm.Tools.Admin.MultipleTenancy::get_IsMultipleTenancy()
0x14f37  box      [mscorlib]System.Boolean
0x14f3c  stelem.ref
0x14f3d  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfoFormat(string, object[])
0x14f42  ldstr    aOrganizationIm_2// "Organization.Import.UpdateOrganization"
0x14f47  ldc.i4.0
0x14f48  newarr   [mscorlib]System.Object
0x14f4d  call     string Microsoft.Crm.Tools.Admin.DMSnapInLibResource::GetString(string name, object[] args)
0x14f52  ldc.i4.s 0xA
0x14f54  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.ProgressEventArgs::.ctor(string, int32)
0x14f59  stloc.2
0x14f5a  ldarg.0
0x14f5b  call     instance class [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.IProgressEventSource Microsoft.Crm.Tools.Admin.ProgressExecution::get_OverallProgress()
0x14f60  ldarg.0
0x14f61  ldloc.2
0x14f62  callvirt instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.IProgressEventSource::RaiseProgressChanged(object, class [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.ProgressEventArgs)
0x14f67  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x14f6c  ldc.i4.s 0xA
0x14f6e  ldstr    aUpdateOrganiza_2// "Update Organization"
0x14f73  ldc.i4.0
0x14f74  newarr   [mscorlib]System.Object
0x14f79  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x14f7e  ldstr    aOrganizationIm_2// "Organization.Import.UpdateOrganization"
0x14f83  ldc.i4.0
0x14f84  newarr   [mscorlib]System.Object
0x14f89  call     string Microsoft.Crm.Tools.Admin.DMSnapInLibResource::GetString(string name, object[] args)
0x14f8e  ldc.i4.0
0x14f8f  newarr   [mscorlib]System.Object
0x14f94  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfo(string, object[])
0x14f99  ldloca.s 0
0x14f9b  call     instance string Microsoft.Crm.Tools.Admin.OrganizationGroupsInfo::get_PrivilegedUserGroupName()
0x14fa0  ldloca.s 0
0x14fa2  call     instance string Microsoft.Crm.Tools.Admin.OrganizationGroupsInfo::get_SqlAccessGroupName()
0x14fa7  ldloca.s 0
0x14fa9  call     instance string Microsoft.Crm.Tools.Admin.OrganizationGroupsInfo::get_ReportingGroupName()
0x14fae  ldloca.s 0
0x14fb0  call     instance string Microsoft.Crm.Tools.Admin.OrganizationGroupsInfo::get_PrivilegedReportingGroupName()
0x14fb5  call     void Microsoft.Crm.Tools.Admin.ActiveDirectoryHelper::VerifyDirectoryObjects(string privilegedUserGroupName, string sqlAccessGroupName, string reportingGroupName, string privilegedReportingGroupName)
0x14fba  leave.s  loc_14FD5
0x14fbc  stloc.s  0xE
0x14fbe  ldstr    aVerifyDirector// "Verify Directory Objects failed with th"...
0x14fc3  ldc.i4.1
0x14fc4  newarr   [mscorlib]System.Object
0x14fc9  dup
0x14fca  ldc.i4.0
0x14fcb  ldloc.s  0xE
0x14fcd  stelem.ref
0x14fce  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteErrorFormat(string, object[])
0x14fd3  rethrow
0x14fd5  ldarg.s  4
0x14fd7  ldarg.s  5
0x14fd9  call     string [Microsoft.Crm.DatabaseInstaller.Common]Microsoft.Crm.DatabaseInstaller.Common.SharedDatabaseUtility::GetConnectionString(string, string)
0x14fde  stloc.s  0xB
0x14fe0  newobj   instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmOrganizationService::.ctor()
0x14fe5  stloc.s  0xC
0x14fe7  ldarg.0
0x14fe8  ldfld    bool Microsoft.Crm.Tools.Admin.ImportOrganizationInstaller::IsOnline
0x14fed  brfalse.s loc_1501A
0x14fef  call     class [Microsoft.Crm.Core]Microsoft.Crm.IScaleGroupInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.ScaleGroupInfoProvider::get_Instance()
0x14ff4  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IScaleGroupInfoProvider::GetScaleGroupId()
0x14ff9  stloc.s  0xF
0x14ffb  ldloc.s  0xC
0x14ffd  ldarg.1
0x14ffe  ldc.i4.0
0x14fff  ldloc.s  0xF
0x15001  ldarg.2
0x15002  ldarg.3
0x15003  ldarg.s  4
0x15005  ldarg.s  5
0x15007  ldloc.s  0xB
0x15009  ldarg.s  6
0x1500b  callvirt instance string [System]System.Uri::get_OriginalString()
0x15010  ldc.i4.2
0x15011  ldc.i4.0
0x15012  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmOrganizationService::Create(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.OrganizationType, valuetype [mscorlib]System.Guid, string, string, string, string, string, string, valuetype [Microsoft.Crm.Core]Microsoft.Crm.OrganizationState, bool)
0x15017  stloc.1
0x15018  br.s     loc_15034
0x1501a  ldloc.s  0xC
0x1501c  ldarg.1
0x1501d  ldarg.2
0x1501e  ldarg.3
0x1501f  ldarg.s  4
0x15021  ldarg.s  5
0x15023  ldloc.s  0xB
0x15025  ldarg.s  6
0x15027  callvirt instance string [System]System.Uri::get_OriginalString()
0x1502c  ldc.i4.2
0x1502d  ldc.i4.0
0x1502e  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmOrganizationService::Create(valuetype [mscorlib]System.Guid, string, string, string, string, string, string, valuetype [Microsoft.Crm.Core]Microsoft.Crm.OrganizationState, bool)
0x15033  stloc.1
0x15034  ldarg.1
0x15035  call     void Microsoft.Crm.Tools.Admin.OrganizationOperation::SetOrgVersionInConfigDB(valuetype [mscorlib]System.Guid organizationId)
0x1503a  ldarg.1
0x1503b  ldarg.2
0x1503c  ldloc.1
0x1503d  call     void Microsoft.Crm.Tools.Admin.ImportOrganizationInstaller::ValidateOrganizationInfo(valuetype [mscorlib]System.Guid organizationId, string organizationUniqueName, class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData orgData)
0x15042  ldarg.0
0x15043  ldarg.1
0x15044  ldloc.0
0x15045  ldarg.3
0x15046  ldarg.2
0x15047  ldarg.s  6
0x15049  ldc.i4.s 0x32
0x1504b  ldarg.s  7
0x1504d  call     instance void Microsoft.Crm.Tools.Admin.ImportOrganizationInstaller::UpdateOrganizationInfo(valuetype [mscorlib]System.Guid organizationId, valuetype Microsoft.Crm.Tools.Admin.OrganizationGroupsInfo organizationInfo, string organizationFriendlyName, string organizationUniqueName, class [System]System.Uri reportServerUrl, int32 PercentUpdateOrganization, class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.User> users)
0x15052  ldstr    aOrganizationut_0// "OrganizationUtility.ApplyDbUpdate"
0x15057  ldc.i4.0
0x15058  newarr   [mscorlib]System.Object
0x1505d  call     string Microsoft.Crm.Tools.Admin.DMSnapInLibResource::GetString(string name, object[] args)
0x15062  ldc.i4.s 0x32
0x15064  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.ProgressEventArgs::.ctor(string, int32)
0x15069  stloc.2
0x1506a  ldarg.0
0x1506b  call     instance class [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.IProgressEventSource Microsoft.Crm.Tools.Admin.ProgressExecution::get_OverallProgress()
0x15070  ldarg.0
0x15071  ldloc.2
0x15072  callvirt instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.IProgressEventSource::RaiseProgressChanged(object, class [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.ProgressEventArgs)
0x15077  ldarg.s  9
0x15079  brfalse.s loc_150AB
0x1507b  ldstr    aApplyingDataba// "Applying database updates"
0x15080  ldc.i4.0
0x15081  newarr   [mscorlib]System.Object
0x15086  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfo(string, object[])
  ... truncated ...
```
