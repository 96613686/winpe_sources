# Microsoft.Crm.CrmLive.Provisioning.OrganizationDatabaseAccess::UpdateActiveDirectoryGroupsForOnebox

- ea: `0x1ff00`
- end: `0x2013d`
- name: `Microsoft.Crm.CrmLive.Provisioning.OrganizationDatabaseAccess::UpdateActiveDirectoryGroupsForOnebox`
- size: `573`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callees

- `0x1ff00`

## string_xrefs

- `0x1ff63`: `ConfigSettingOverride_PrivilegeReportGroupId`
- `0x1ffb2`: `update OrganizationBase set PrivReportingGroupId = @privreportgroupid where OrganizationId = @orgId;`
- `0x1ffc8`: `update OrganizationBase set PrivReportingGroupName = @privreportinggroupname where OrganizationId = @orgId;`
- `0x1ffd8`: `ConfigSettingOverride_PrivilegeUserGroupId`
- `0x1fff6`: `privilegeusergroupid`
- `0x2000f`: `update OrganizationBase set PrivilegeUserGroupId = @privilegeusergroupid where OrganizationId = @orgId;`
- `0x2001f`: `ConfigSettingOverride_SqlAccessGroupId`
- `0x2003d`: `sqlaccessgroupid`
- `0x20050`: `sqlaccessgroupname`
- `0x20057`: `\SQLAccessGroup`
- `0x2006e`: `update OrganizationBase set SqlAccessGroupId = @sqlaccessgroupid where OrganizationId = @orgId;`
- `0x20084`: `update OrganizationBase set SqlAccessGroupName = @sqlaccessgroupname where OrganizationId = @orgId;`
- `0x20094`: `ConfigSettingOverride_ReportingGroupId`
- `0x200e3`: `update OrganizationBase set ReportingGroupId = @reportinggroupid where OrganizationId = @orgId;`
- `0x200f9`: `update OrganizationBase set ReportingGroupName = @reportinggroupname where OrganizationId = @orgId;`

## pseudocode

```c

```

## disassembly

```asm
0x1ff00  ldarg.1
0x1ff01  ldc.i4.0
0x1ff02  ldc.i4.0
0x1ff03  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::.ctor(valuetype [mscorlib]System.Guid, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0x1ff08  stloc.0
0x1ff09  ldloc.0
0x1ff0a  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Open()
0x1ff0f  ldloc.0
0x1ff10  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand()
0x1ff15  stloc.1
0x1ff16  ldloc.1
0x1ff17  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x1ff1c  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x1ff21  stloc.2
0x1ff22  ldsfld   class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.Registry::LocalMachine
0x1ff27  ldstr    aSoftwareMicros// "Software\\Microsoft\\MSCRM"
0x1ff2c  callvirt instance class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.RegistryKey::OpenSubKey(string)
0x1ff31  stloc.3
0x1ff32  ldloc.3
0x1ff33  brfalse  loc_2011C
0x1ff38  call     string [mscorlib]System.Environment::get_UserDomainName()
0x1ff3d  stloc.s  5
0x1ff3f  ldloc.2
0x1ff40  callvirt instance void [System.Data]System.Data.Common.DbParameterCollection::Clear()
0x1ff45  ldloc.1
0x1ff46  ldstr    asc_361CC// ""
0x1ff4b  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x1ff50  ldloc.2
0x1ff51  ldstr    aOrgid// "orgId"
0x1ff56  ldarg.1
0x1ff57  box      [mscorlib]System.Guid
0x1ff5c  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x1ff61  pop
0x1ff62  ldloc.3
0x1ff63  ldstr    aConfigsettingo// "ConfigSettingOverride_PrivilegeReportGr"...
0x1ff68  ldsfld   string [mscorlib]System.String::Empty
0x1ff6d  callvirt instance object [mscorlib]Microsoft.Win32.RegistryKey::GetValue(string, object)
0x1ff72  castclass [mscorlib]System.String
0x1ff77  ldloca.s 4
0x1ff79  call     bool [mscorlib]System.Guid::TryParse(string, valuetype [mscorlib]System.Guid&)
0x1ff7e  brfalse.s loc_1FFD7
0x1ff80  ldloc.2
0x1ff81  ldstr    aPrivreportgrou// "privreportgroupid"
0x1ff86  ldloc.s  4
0x1ff88  box      [mscorlib]System.Guid
0x1ff8d  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x1ff92  pop
0x1ff93  ldloc.2
0x1ff94  ldstr    aPrivreportingg_0// "privreportinggroupname"
0x1ff99  ldloc.s  5
0x1ff9b  ldstr    aPrivreportingg_1// "\\PrivReportingGroup"
0x1ffa0  call     string [mscorlib]System.String::Concat(string, string)
0x1ffa5  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x1ffaa  pop
0x1ffab  ldloc.1
0x1ffac  dup
0x1ffad  callvirt instance string [System.Data]System.Data.IDbCommand::get_CommandText()
0x1ffb2  ldstr    aUpdateOrganiza_1// "update OrganizationBase set PrivReporti"...
0x1ffb7  call     string [mscorlib]System.String::Concat(string, string)
0x1ffbc  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x1ffc1  ldloc.1
0x1ffc2  dup
0x1ffc3  callvirt instance string [System.Data]System.Data.IDbCommand::get_CommandText()
0x1ffc8  ldstr    aUpdateOrganiza_2// "update OrganizationBase set PrivReporti"...
0x1ffcd  call     string [mscorlib]System.String::Concat(string, string)
0x1ffd2  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x1ffd7  ldloc.3
0x1ffd8  ldstr    aConfigsettingo_0// "ConfigSettingOverride_PrivilegeUserGrou"...
0x1ffdd  ldsfld   string [mscorlib]System.String::Empty
0x1ffe2  callvirt instance object [mscorlib]Microsoft.Win32.RegistryKey::GetValue(string, object)
0x1ffe7  castclass [mscorlib]System.String
0x1ffec  ldloca.s 4
0x1ffee  call     bool [mscorlib]System.Guid::TryParse(string, valuetype [mscorlib]System.Guid&)
0x1fff3  brfalse.s loc_2001E
0x1fff5  ldloc.2
0x1fff6  ldstr    aPrivilegeuserg// "privilegeusergroupid"
0x1fffb  ldloc.s  4
0x1fffd  box      [mscorlib]System.Guid
0x20002  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x20007  pop
0x20008  ldloc.1
0x20009  dup
0x2000a  callvirt instance string [System.Data]System.Data.IDbCommand::get_CommandText()
0x2000f  ldstr    aUpdateOrganiza_3// "update OrganizationBase set PrivilegeUs"...
0x20014  call     string [mscorlib]System.String::Concat(string, string)
0x20019  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x2001e  ldloc.3
0x2001f  ldstr    aConfigsettingo_1// "ConfigSettingOverride_SqlAccessGroupId"
0x20024  ldsfld   string [mscorlib]System.String::Empty
0x20029  callvirt instance object [mscorlib]Microsoft.Win32.RegistryKey::GetValue(string, object)
0x2002e  castclass [mscorlib]System.String
0x20033  ldloca.s 4
0x20035  call     bool [mscorlib]System.Guid::TryParse(string, valuetype [mscorlib]System.Guid&)
0x2003a  brfalse.s loc_20093
0x2003c  ldloc.2
0x2003d  ldstr    aSqlaccessgroup_0// "sqlaccessgroupid"
0x20042  ldloc.s  4
0x20044  box      [mscorlib]System.Guid
0x20049  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x2004e  pop
0x2004f  ldloc.2
0x20050  ldstr    aSqlaccessgroup_1// "sqlaccessgroupname"
0x20055  ldloc.s  5
0x20057  ldstr    aSqlaccessgroup_2// "\\SQLAccessGroup"
0x2005c  call     string [mscorlib]System.String::Concat(string, string)
0x20061  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x20066  pop
0x20067  ldloc.1
0x20068  dup
0x20069  callvirt instance string [System.Data]System.Data.IDbCommand::get_CommandText()
0x2006e  ldstr    aUpdateOrganiza_4// "update OrganizationBase set SqlAccessGr"...
0x20073  call     string [mscorlib]System.String::Concat(string, string)
0x20078  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x2007d  ldloc.1
0x2007e  dup
0x2007f  callvirt instance string [System.Data]System.Data.IDbCommand::get_CommandText()
0x20084  ldstr    aUpdateOrganiza_5// "update OrganizationBase set SqlAccessGr"...
0x20089  call     string [mscorlib]System.String::Concat(string, string)
0x2008e  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x20093  ldloc.3
0x20094  ldstr    aConfigsettingo_2// "ConfigSettingOverride_ReportingGroupId"
0x20099  ldsfld   string [mscorlib]System.String::Empty
0x2009e  callvirt instance object [mscorlib]Microsoft.Win32.RegistryKey::GetValue(string, object)
0x200a3  castclass [mscorlib]System.String
0x200a8  ldloca.s 4
0x200aa  call     bool [mscorlib]System.Guid::TryParse(string, valuetype [mscorlib]System.Guid&)
0x200af  brfalse.s loc_20108
0x200b1  ldloc.2
0x200b2  ldstr    aReportinggroup_0// "reportinggroupid"
0x200b7  ldloc.s  4
0x200b9  box      [mscorlib]System.Guid
0x200be  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x200c3  pop
0x200c4  ldloc.2
0x200c5  ldstr    aReportinggroup_1// "reportinggroupname"
0x200ca  ldloc.s  5
0x200cc  ldstr    aReportinggroup_2// "\\ReportingGroup"
0x200d1  call     string [mscorlib]System.String::Concat(string, string)
0x200d6  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x200db  pop
0x200dc  ldloc.1
0x200dd  dup
0x200de  callvirt instance string [System.Data]System.Data.IDbCommand::get_CommandText()
0x200e3  ldstr    aUpdateOrganiza_6// "update OrganizationBase set ReportingGr"...
0x200e8  call     string [mscorlib]System.String::Concat(string, string)
0x200ed  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x200f2  ldloc.1
0x200f3  dup
0x200f4  callvirt instance string [System.Data]System.Data.IDbCommand::get_CommandText()
0x200f9  ldstr    aUpdateOrganiza_7// "update OrganizationBase set ReportingGr"...
0x200fe  call     string [mscorlib]System.String::Concat(string, string)
0x20103  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x20108  ldloc.1
0x20109  callvirt instance string [System.Data]System.Data.IDbCommand::get_CommandText()
0x2010e  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x20113  brtrue.s loc_2011C
0x20115  ldloc.1
0x20116  callvirt instance int32 [System.Data]System.Data.IDbCommand::ExecuteNonQuery()
0x2011b  pop
0x2011c  leave.s  loc_2013C
0x2011e  ldloc.3
0x2011f  brfalse.s loc_20127
0x20121  ldloc.3
0x20122  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x20127  endfinally
0x20128  ldloc.1
0x20129  brfalse.s loc_20131
0x2012b  ldloc.1
0x2012c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x20131  endfinally
0x20132  ldloc.0
0x20133  brfalse.s loc_2013B
0x20135  ldloc.0
0x20136  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2013b  endfinally
0x2013c  ret
```
