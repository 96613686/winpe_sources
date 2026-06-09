# Microsoft.Crm.Tools.Admin.ImportOrganizationInstaller::UpdateOrganizationInfo

- ea: `0x15350`
- end: `0x155c0`
- name: `Microsoft.Crm.Tools.Admin.ImportOrganizationInstaller::UpdateOrganizationInfo`
- size: `624`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14d30`

## callees

- `0x22e0`
- `0x41c0`
- `0x13930`
- `0x13a40`
- `0x13f30`
- `0x13f70`
- `0x14140`
- `0x15350`
- `0x157b0`
- `0x158c0`
- `0x158e0`
- `0x15900`
- `0x15920`

## string_xrefs

- `0x154c4`: `Organization.Import.UpdateUsers`
- `0x154e9`: `Organization.Import.UpdateUsers`
- `0x1539d`: `PrivilegedReportingGroupName`
- `0x153ae`: `PrivilegedUserGroupName`
- `0x153d0`: `SqlAccessGroupName`

## pseudocode

```c

```

## disassembly

```asm
0x15350  ldarg.2
0x15351  box      Microsoft.Crm.Tools.Admin.OrganizationGroupsInfo
0x15356  ldstr    aOrganizationin_28// "organizationInfo"
0x1535b  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x15360  ldarg.1
0x15361  ldstr    aOrganizationid_0// "organizationId"
0x15366  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x1536b  ldarg.3
0x1536c  ldstr    aOrganizationfr_0// "organizationFriendlyName"
0x15371  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x15376  ldarg.s  4
0x15378  ldstr    aOrganizationun_1// "organizationUniqueName"
0x1537d  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x15382  ldarg.0
0x15383  ldfld    bool Microsoft.Crm.Tools.Admin.ImportOrganizationInstaller::IsOnline
0x15388  brtrue.s loc_15396
0x1538a  ldarg.s  5
0x1538c  ldstr    aReportserverur_0// "reportServerUrl"
0x15391  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x15396  ldarga.s 2
0x15398  call     instance string Microsoft.Crm.Tools.Admin.OrganizationGroupsInfo::get_PrivilegedReportingGroupName()
0x1539d  ldstr    aPrivilegedrepo// "PrivilegedReportingGroupName"
0x153a2  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x153a7  ldarga.s 2
0x153a9  call     instance string Microsoft.Crm.Tools.Admin.OrganizationGroupsInfo::get_PrivilegedUserGroupName()
0x153ae  ldstr    aPrivilegeduser_0// "PrivilegedUserGroupName"
0x153b3  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x153b8  ldarga.s 2
0x153ba  call     instance string Microsoft.Crm.Tools.Admin.OrganizationGroupsInfo::get_ReportingGroupName()
0x153bf  ldstr    aReportinggroup_2// "ReportingGroupName"
0x153c4  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x153c9  ldarga.s 2
0x153cb  call     instance string Microsoft.Crm.Tools.Admin.OrganizationGroupsInfo::get_SqlAccessGroupName()
0x153d0  ldstr    aSqlaccessgroup_1// "SqlAccessGroupName"
0x153d5  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x153da  ldarg.0
0x153db  ldarg.1
0x153dc  ldarga.s 2
0x153de  call     instance string Microsoft.Crm.Tools.Admin.OrganizationGroupsInfo::get_SqlAccessGroupName()
0x153e3  ldarga.s 2
0x153e5  call     instance string Microsoft.Crm.Tools.Admin.OrganizationGroupsInfo::get_ReportingGroupName()
0x153ea  ldarga.s 2
0x153ec  call     instance string Microsoft.Crm.Tools.Admin.OrganizationGroupsInfo::get_PrivilegedReportingGroupName()
0x153f1  call     instance void Microsoft.Crm.Tools.Admin.ImportOrganizationInstaller::GrantAccessOnCrmSecurityGroups(valuetype [mscorlib]System.Guid organizationId, string sqlAccessGroupName, string reportingGroupName, string privilegedReportingGroupName)
0x153f6  ldarg.1
0x153f7  call     int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::GetInstallConnectionTimeout()
0x153fc  ldc.i4.0
0x153fd  ldc.i4.0
0x153fe  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::.ctor(valuetype [mscorlib]System.Guid, int32, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0x15403  ldarg.1
0x15404  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection, valuetype [mscorlib]System.Guid)
0x15409  stloc.1
0x1540a  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x1540f  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x15414  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_EnableReadCommittedTransactions()
0x15419  ldloc.1
0x1541a  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1541f  brfalse.s loc_1542E
0x15421  ldloc.1
0x15422  ldc.i4   0x1000
0x15427  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnBeginRequest(valuetype [System.Data]System.Data.IsolationLevel)
0x1542c  br.s     loc_15439
0x1542e  ldloc.1
0x1542f  ldc.i4   0x100000
0x15434  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnBeginRequest(valuetype [System.Data]System.Data.IsolationLevel)
0x15439  ldloc.1
0x1543a  call     void Microsoft.Crm.Tools.Admin.DBImportHelper::PrepareMetadataCache(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x1543f  ldstr    aUpdatingOrgani// "Updating organization info"
0x15444  ldc.i4.0
0x15445  newarr   [mscorlib]System.Object
0x1544a  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfo(string, object[])
0x1544f  ldloc.1
0x15450  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x15455  ldc.i4.1
0x15456  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext::CreateSqlCommand(bool)
0x1545b  stloc.2
0x1545c  ldloc.2
0x1545d  ldc.i4   0x15180
0x15462  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandTimeout(int32)
0x15467  ldarg.0
0x15468  ldfld    bool Microsoft.Crm.Tools.Admin.ImportOrganizationInstaller::UniqueOrgId
0x1546d  brtrue.s loc_15492
0x1546f  ldstr    aUpdatingOrgani_0// "Updating Organization references"
0x15474  ldc.i4.0
0x15475  newarr   [mscorlib]System.Object
0x1547a  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfo(string, object[])
0x1547f  ldarg.1
0x15480  ldarg.3
0x15481  ldloc.1
0x15482  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x15487  castclass [Microsoft.Crm.Core]Microsoft.Crm.SqlExecutionContext
0x1548c  ldc.i4.0
0x1548d  call     void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.OrganizationManagementHelper::UpdateOrganizationReferences(valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Core]Microsoft.Crm.SqlExecutionContext, bool)
0x15492  ldstr    aUpdatingOrgani_1// "Updating Organization OU Groups"
0x15497  ldc.i4.0
0x15498  newarr   [mscorlib]System.Object
0x1549d  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfo(string, object[])
0x154a2  ldloc.2
0x154a3  ldarga.s 2
0x154a5  call     instance string Microsoft.Crm.Tools.Admin.OrganizationGroupsInfo::get_PrivilegedUserGroupName()
0x154aa  ldarga.s 2
0x154ac  call     instance string Microsoft.Crm.Tools.Admin.OrganizationGroupsInfo::get_SqlAccessGroupName()
0x154b1  ldarga.s 2
0x154b3  call     instance string Microsoft.Crm.Tools.Admin.OrganizationGroupsInfo::get_ReportingGroupName()
0x154b8  ldarga.s 2
0x154ba  call     instance string Microsoft.Crm.Tools.Admin.OrganizationGroupsInfo::get_PrivilegedReportingGroupName()
0x154bf  call     void Microsoft.Crm.Tools.Admin.DBImportHelper::UpdateOrganizationOUGroups(class [System.Data]System.Data.IDbCommand command, string ldapPrivUserGroup, string ldapSqlAccessGroup, string ldapReportingGroup, string ldapPrivReportingGroup)
0x154c4  ldstr    aOrganizationIm_0// "Organization.Import.UpdateUsers"
0x154c9  ldc.i4.0
0x154ca  newarr   [mscorlib]System.Object
0x154cf  call     string Microsoft.Crm.Tools.Admin.DMSnapInLibResource::GetString(string name, object[] args)
0x154d4  ldarg.s  6
0x154d6  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.ProgressEventArgs::.ctor(string, int32)
0x154db  stloc.0
0x154dc  ldarg.0
0x154dd  call     instance class [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.IProgressEventSource Microsoft.Crm.Tools.Admin.ProgressExecution::get_OverallProgress()
0x154e2  ldarg.0
0x154e3  ldloc.0
0x154e4  callvirt instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.IProgressEventSource::RaiseProgressChanged(object, class [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.ProgressEventArgs)
0x154e9  ldstr    aOrganizationIm_0// "Organization.Import.UpdateUsers"
0x154ee  ldc.i4.0
0x154ef  newarr   [mscorlib]System.Object
0x154f4  call     string Microsoft.Crm.Tools.Admin.DMSnapInLibResource::GetString(string name, object[] args)
0x154f9  ldc.i4.0
0x154fa  newarr   [mscorlib]System.Object
0x154ff  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfo(string, object[])
0x15504  ldarg.0
0x15505  ldfld    bool Microsoft.Crm.Tools.Admin.ImportOrganizationInstaller::IsOnline
0x1550a  brtrue.s loc_1552D
0x1550c  ldstr    aMappingUsersFo// "Mapping users for the organization"
0x15511  ldc.i4.0
0x15512  newarr   [mscorlib]System.Object
0x15517  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfo(string, object[])
0x1551c  ldarg.1
0x1551d  ldarg.s  7
0x1551f  ldarga.s 2
0x15521  call     instance string Microsoft.Crm.Tools.Admin.OrganizationGroupsInfo::get_ReportingGroupName()
0x15526  ldc.i4.0
0x15527  ldloc.1
0x15528  call     void Microsoft.Crm.Tools.Admin.DBImportHelper::MapUsers(valuetype [mscorlib]System.Guid organizationId, class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.User> users, string reportingGroupName, bool usersAlreadyInConfigDB, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x1552d  ldstr    aRePublishingRe// "Re-publishing reports"
0x15532  ldc.i4.0
0x15533  newarr   [mscorlib]System.Object
0x15538  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfo(string, object[])
0x1553d  ldstr    aRspublishactio_1// "RSPublishAction.ProgressMessage"
0x15542  ldc.i4.0
0x15543  newarr   [mscorlib]System.Object
0x15548  call     string Microsoft.Crm.Tools.Admin.DMSnapInLibResource::GetString(string name, object[] args)
0x1554d  ldarg.s  6
0x1554f  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.ProgressEventArgs::.ctor(string, int32)
0x15554  stloc.0
0x15555  ldarg.0
0x15556  call     instance class [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.IProgressEventSource Microsoft.Crm.Tools.Admin.ProgressExecution::get_OverallProgress()
0x1555b  ldarg.0
0x1555c  ldloc.0
0x1555d  callvirt instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.IProgressEventSource::RaiseProgressChanged(object, class [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.ProgressEventArgs)
0x15562  ldloc.2
0x15563  ldarg.1
0x15564  ldarg.s  4
0x15566  ldarg.s  5
0x15568  call     void Microsoft.Crm.Tools.Admin.DBImportHelper::RePublishReports(class [System.Data]System.Data.IDbCommand command, valuetype [mscorlib]System.Guid organizationId, string organizationUniqueName, class [System]System.Uri reportUrl)
0x1556d  ldstr    aUpdatingLangua// "Updating language packs"
0x15572  ldc.i4.0
0x15573  newarr   [mscorlib]System.Object
0x15578  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfo(string, object[])
0x1557d  ldloc.2
0x1557e  ldarg.1
0x1557f  call     void Microsoft.Crm.Tools.Admin.DBImportHelper::UpdateLanguagePacks(class [System.Data]System.Data.IDbCommand command, valuetype [mscorlib]System.Guid newOrganizationId)
0x15584  leave.s  loc_15590
0x15586  ldloc.2
0x15587  brfalse.s loc_1558F
0x15589  ldloc.2
0x1558a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1558f  endfinally
0x15590  ldloc.1
0x15591  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnEndRequest()
0x15596  leave.s  loc_155BF
0x15598  stloc.3
0x15599  ldstr    aErrorWhileUpda// "Error while updating organization infor"...
0x1559e  ldc.i4.1
0x1559f  newarr   [mscorlib]System.Object
0x155a4  dup
0x155a5  ldc.i4.0
0x155a6  ldloc.3
0x155a7  stelem.ref
0x155a8  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteErrorFormat(string, object[])
0x155ad  ldloc.1
0x155ae  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnErrorRequest()
0x155b3  rethrow
0x155b5  ldloc.1
0x155b6  brfalse.s loc_155BE
0x155b8  ldloc.1
0x155b9  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x155be  endfinally
0x155bf  ret
```
