# Microsoft.Crm.Tools.Admin.ImportOrganizationInstaller::UpdateOUGroupsInDatabase

- ea: `0x155c0`
- end: `0x157a5`
- name: `Microsoft.Crm.Tools.Admin.ImportOrganizationInstaller::UpdateOUGroupsInDatabase`
- size: `485`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14630`

## callees

- `0x55b0`
- `0x13f70`
- `0x155c0`
- `0x157b0`
- `0x158c0`
- `0x158d0`
- `0x158e0`
- `0x158f0`
- `0x15900`
- `0x15910`
- `0x15920`
- `0x15930`

## string_xrefs

- `0x156ab`: `PrivilegedUserGroupName = {0}, SqlAccessGroupName = {1}, ReportingGroupName = {2}, PrivilegedReportingGroupName = {3}`
- `0x15707`: `Verify Directory Objects failed with the following error: {0}`
- `0x155c0`: `UpdateOUGroupsInDatabase started`
- `0x15794`: `UpdateOUGroupsInDatabase finished`

## pseudocode

```c

```

## disassembly

```asm
0x155c0  ldstr    aUpdateougroups// "UpdateOUGroupsInDatabase started"
0x155c5  ldc.i4.0
0x155c6  newarr   [mscorlib]System.Object
0x155cb  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfo(string, object[])
0x155d0  newobj   instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmConfigSettingsService::.ctor()
0x155d5  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SecurityGroupsData [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmConfigSettingsService::GetSecurityGroups()
0x155da  stloc.0
0x155db  ldloca.s 1
0x155dd  initobj  Microsoft.Crm.Tools.Admin.OrganizationGroupsInfo
0x155e3  ldloca.s 1
0x155e5  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x155ea  ldstr    aGuid0// "<GUID={0}>"
0x155ef  ldc.i4.1
0x155f0  newarr   [mscorlib]System.Object
0x155f5  dup
0x155f6  ldc.i4.0
0x155f7  ldloc.0
0x155f8  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SecurityGroupsData::get_PrivilegeUserGroupId()
0x155fd  stloc.2
0x155fe  ldloca.s 2
0x15600  ldstr    aD// "D"
0x15605  call     instance string [mscorlib]System.Guid::ToString(string)
0x1560a  stelem.ref
0x1560b  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x15610  call     instance void Microsoft.Crm.Tools.Admin.OrganizationGroupsInfo::set_PrivilegedUserGroupName(string value)
0x15615  ldloca.s 1
0x15617  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1561c  ldstr    aGuid0// "<GUID={0}>"
0x15621  ldc.i4.1
0x15622  newarr   [mscorlib]System.Object
0x15627  dup
0x15628  ldc.i4.0
0x15629  ldloc.0
0x1562a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SecurityGroupsData::get_SqlAccessGroupId()
0x1562f  stloc.2
0x15630  ldloca.s 2
0x15632  ldstr    aD// "D"
0x15637  call     instance string [mscorlib]System.Guid::ToString(string)
0x1563c  stelem.ref
0x1563d  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x15642  call     instance void Microsoft.Crm.Tools.Admin.OrganizationGroupsInfo::set_SqlAccessGroupName(string value)
0x15647  ldloca.s 1
0x15649  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1564e  ldstr    aGuid0// "<GUID={0}>"
0x15653  ldc.i4.1
0x15654  newarr   [mscorlib]System.Object
0x15659  dup
0x1565a  ldc.i4.0
0x1565b  ldloc.0
0x1565c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SecurityGroupsData::get_ReportingGroupId()
0x15661  stloc.2
0x15662  ldloca.s 2
0x15664  ldstr    aD// "D"
0x15669  call     instance string [mscorlib]System.Guid::ToString(string)
0x1566e  stelem.ref
0x1566f  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x15674  call     instance void Microsoft.Crm.Tools.Admin.OrganizationGroupsInfo::set_ReportingGroupName(string value)
0x15679  ldloca.s 1
0x1567b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x15680  ldstr    aGuid0// "<GUID={0}>"
0x15685  ldc.i4.1
0x15686  newarr   [mscorlib]System.Object
0x1568b  dup
0x1568c  ldc.i4.0
0x1568d  ldloc.0
0x1568e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SecurityGroupsData::get_PrivilegeReportGroupId()
0x15693  stloc.2
0x15694  ldloca.s 2
0x15696  ldstr    aD// "D"
0x1569b  call     instance string [mscorlib]System.Guid::ToString(string)
0x156a0  stelem.ref
0x156a1  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x156a6  call     instance void Microsoft.Crm.Tools.Admin.OrganizationGroupsInfo::set_PrivilegedReportingGroupName(string value)
0x156ab  ldstr    aPrivilegeduser// "PrivilegedUserGroupName = {0}, SqlAcces"...
0x156b0  ldc.i4.4
0x156b1  newarr   [mscorlib]System.Object
0x156b6  dup
0x156b7  ldc.i4.0
0x156b8  ldloca.s 1
0x156ba  call     instance string Microsoft.Crm.Tools.Admin.OrganizationGroupsInfo::get_PrivilegedUserGroupName()
0x156bf  stelem.ref
0x156c0  dup
0x156c1  ldc.i4.1
0x156c2  ldloca.s 1
0x156c4  call     instance string Microsoft.Crm.Tools.Admin.OrganizationGroupsInfo::get_SqlAccessGroupName()
0x156c9  stelem.ref
0x156ca  dup
0x156cb  ldc.i4.2
0x156cc  ldloca.s 1
0x156ce  call     instance string Microsoft.Crm.Tools.Admin.OrganizationGroupsInfo::get_ReportingGroupName()
0x156d3  stelem.ref
0x156d4  dup
0x156d5  ldc.i4.3
0x156d6  ldloca.s 1
0x156d8  call     instance string Microsoft.Crm.Tools.Admin.OrganizationGroupsInfo::get_PrivilegedReportingGroupName()
0x156dd  stelem.ref
0x156de  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfoFormat(string, object[])
0x156e3  ldloca.s 1
0x156e5  call     instance string Microsoft.Crm.Tools.Admin.OrganizationGroupsInfo::get_PrivilegedUserGroupName()
0x156ea  ldloca.s 1
0x156ec  call     instance string Microsoft.Crm.Tools.Admin.OrganizationGroupsInfo::get_SqlAccessGroupName()
0x156f1  ldloca.s 1
0x156f3  call     instance string Microsoft.Crm.Tools.Admin.OrganizationGroupsInfo::get_ReportingGroupName()
0x156f8  ldloca.s 1
0x156fa  call     instance string Microsoft.Crm.Tools.Admin.OrganizationGroupsInfo::get_PrivilegedReportingGroupName()
0x156ff  call     void Microsoft.Crm.Tools.Admin.ActiveDirectoryHelper::VerifyDirectoryObjects(string privilegedUserGroupName, string sqlAccessGroupName, string reportingGroupName, string privilegedReportingGroupName)
0x15704  leave.s  loc_1571D
0x15706  stloc.3
0x15707  ldstr    aVerifyDirector// "Verify Directory Objects failed with th"...
0x1570c  ldc.i4.1
0x1570d  newarr   [mscorlib]System.Object
0x15712  dup
0x15713  ldc.i4.0
0x15714  ldloc.3
0x15715  stelem.ref
0x15716  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteErrorFormat(string, object[])
0x1571b  rethrow
0x1571d  ldarg.0
0x1571e  ldarg.3
0x1571f  ldloca.s 1
0x15721  call     instance string Microsoft.Crm.Tools.Admin.OrganizationGroupsInfo::get_SqlAccessGroupName()
0x15726  ldloca.s 1
0x15728  call     instance string Microsoft.Crm.Tools.Admin.OrganizationGroupsInfo::get_ReportingGroupName()
0x1572d  ldloca.s 1
0x1572f  call     instance string Microsoft.Crm.Tools.Admin.OrganizationGroupsInfo::get_PrivilegedReportingGroupName()
0x15734  call     instance void Microsoft.Crm.Tools.Admin.ImportOrganizationInstaller::GrantAccessOnCrmSecurityGroups(valuetype [mscorlib]System.Guid organizationId, string sqlAccessGroupName, string reportingGroupName, string privilegedReportingGroupName)
0x15739  ldarg.1
0x1573a  ldarg.2
0x1573b  call     string [Microsoft.Crm.Setup.DatabaseInstaller]Microsoft.Crm.Setup.Database.Helpers::GetConnectionString(string, string)
0x15740  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDirectSqlConnection::.ctor(string)
0x15745  stloc.s  4
0x15747  ldloc.s  4
0x15749  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Open()
0x1574e  ldloc.s  4
0x15750  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand()
0x15755  stloc.s  5
0x15757  ldloc.s  5
0x15759  ldloca.s 1
0x1575b  call     instance string Microsoft.Crm.Tools.Admin.OrganizationGroupsInfo::get_PrivilegedUserGroupName()
0x15760  ldloca.s 1
0x15762  call     instance string Microsoft.Crm.Tools.Admin.OrganizationGroupsInfo::get_SqlAccessGroupName()
0x15767  ldloca.s 1
0x15769  call     instance string Microsoft.Crm.Tools.Admin.OrganizationGroupsInfo::get_ReportingGroupName()
0x1576e  ldloca.s 1
0x15770  call     instance string Microsoft.Crm.Tools.Admin.OrganizationGroupsInfo::get_PrivilegedReportingGroupName()
0x15775  call     void Microsoft.Crm.Tools.Admin.DBImportHelper::UpdateOrganizationOUGroups(class [System.Data]System.Data.IDbCommand command, string ldapPrivUserGroup, string ldapSqlAccessGroup, string ldapReportingGroup, string ldapPrivReportingGroup)
0x1577a  leave.s  loc_15794
0x1577c  ldloc.s  5
0x1577e  brfalse.s loc_15787
0x15780  ldloc.s  5
0x15782  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x15787  endfinally
0x15788  ldloc.s  4
0x1578a  brfalse.s loc_15793
0x1578c  ldloc.s  4
0x1578e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x15793  endfinally
0x15794  ldstr    aUpdateougroups_0// "UpdateOUGroupsInDatabase finished"
0x15799  ldc.i4.0
0x1579a  newarr   [mscorlib]System.Object
0x1579f  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfo(string, object[])
0x157a4  ret
```
