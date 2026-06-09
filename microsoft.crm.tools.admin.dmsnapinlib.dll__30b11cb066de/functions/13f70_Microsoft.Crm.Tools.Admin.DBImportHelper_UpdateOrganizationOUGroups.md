# Microsoft.Crm.Tools.Admin.DBImportHelper::UpdateOrganizationOUGroups

- ea: `0x13f70`
- end: `0x140b9`
- name: `Microsoft.Crm.Tools.Admin.DBImportHelper::UpdateOrganizationOUGroups`
- size: `329`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x15350`
- `0x155c0`

## callees

- `0x13f70`
- `0x14170`
- `0x141b0`

## string_xrefs

- `0x14019`: ` update OrganizationBase  set  PrivilegeUserGroupId = @PrivilegeUserGroupId,  SqlAccessGroupId = @SqlAccessGroupId, SqlAccessGroupName = @SqlAccessGroupName,  ReportingGroupId = @ReportingGroupId, ReportingGroupName = @ReportingGroupName,  PrivReportingGroupId = @PrivReportingGroupId, PrivReportingGroupName = @PrivReportingGroupName `
- `0x14030`: `@PrivilegeUserGroupId`
- `0x14043`: `@SqlAccessGroupId`
- `0x14051`: `@SqlAccessGroupName`
- `0x140a8`: `UpdateOrganizationOUGroups`

## pseudocode

```c

```

## disassembly

```asm
0x13f70  ldarg.1
0x13f71  call     string [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.ADUtility::CreateLdapPath(string)
0x13f76  newobj   instance void [System.DirectoryServices]System.DirectoryServices.DirectoryEntry::.ctor(string)
0x13f7b  stloc.s  7
0x13f7d  ldloc.s  7
0x13f7f  callvirt instance valuetype [mscorlib]System.Guid [System.DirectoryServices]System.DirectoryServices.DirectoryEntry::get_Guid()
0x13f84  stloc.0
0x13f85  leave.s  loc_13F93
0x13f87  ldloc.s  7
0x13f89  brfalse.s loc_13F92
0x13f8b  ldloc.s  7
0x13f8d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x13f92  endfinally
0x13f93  ldarg.2
0x13f94  call     string [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.ADUtility::CreateLdapPath(string)
0x13f99  newobj   instance void [System.DirectoryServices]System.DirectoryServices.DirectoryEntry::.ctor(string)
0x13f9e  stloc.s  8
0x13fa0  ldloc.s  8
0x13fa2  callvirt instance valuetype [mscorlib]System.Guid [System.DirectoryServices]System.DirectoryServices.DirectoryEntry::get_Guid()
0x13fa7  stloc.1
0x13fa8  ldloc.s  8
0x13faa  call     string [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.ADUtility::GetGroupNameNT4Format(class [System.DirectoryServices]System.DirectoryServices.DirectoryEntry)
0x13faf  stloc.2
0x13fb0  leave.s  loc_13FBE
0x13fb2  ldloc.s  8
0x13fb4  brfalse.s loc_13FBD
0x13fb6  ldloc.s  8
0x13fb8  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x13fbd  endfinally
0x13fbe  ldarg.3
0x13fbf  call     string [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.ADUtility::CreateLdapPath(string)
0x13fc4  newobj   instance void [System.DirectoryServices]System.DirectoryServices.DirectoryEntry::.ctor(string)
0x13fc9  stloc.s  9
0x13fcb  ldloc.s  9
0x13fcd  callvirt instance valuetype [mscorlib]System.Guid [System.DirectoryServices]System.DirectoryServices.DirectoryEntry::get_Guid()
0x13fd2  stloc.3
0x13fd3  ldloc.s  9
0x13fd5  call     string [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.ADUtility::GetGroupNameNT4Format(class [System.DirectoryServices]System.DirectoryServices.DirectoryEntry)
0x13fda  stloc.s  4
0x13fdc  leave.s  loc_13FEA
0x13fde  ldloc.s  9
0x13fe0  brfalse.s loc_13FE9
0x13fe2  ldloc.s  9
0x13fe4  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x13fe9  endfinally
0x13fea  ldarg.s  4
0x13fec  call     string [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.ADUtility::CreateLdapPath(string)
0x13ff1  newobj   instance void [System.DirectoryServices]System.DirectoryServices.DirectoryEntry::.ctor(string)
0x13ff6  stloc.s  0xA
0x13ff8  ldloc.s  0xA
0x13ffa  callvirt instance valuetype [mscorlib]System.Guid [System.DirectoryServices]System.DirectoryServices.DirectoryEntry::get_Guid()
0x13fff  stloc.s  5
0x14001  ldloc.s  0xA
0x14003  call     string [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.ADUtility::GetGroupNameNT4Format(class [System.DirectoryServices]System.DirectoryServices.DirectoryEntry)
0x14008  stloc.s  6
0x1400a  leave.s  loc_14018
0x1400c  ldloc.s  0xA
0x1400e  brfalse.s loc_14017
0x14010  ldloc.s  0xA
0x14012  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x14017  endfinally
0x14018  ldarg.0
0x14019  ldstr    aUpdateOrganiza_1// " update OrganizationBase  set  Privileg"...
0x1401e  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x14023  ldarg.0
0x14024  call     void Microsoft.Crm.Tools.Admin.DBImportHelper::ClearParameters(class [System.Data]System.Data.IDbCommand command)
0x14029  ldarg.0
0x1402a  ldloc.0
0x1402b  box      [mscorlib]System.Guid
0x14030  ldstr    aPrivilegeuserg// "@PrivilegeUserGroupId"
0x14035  ldc.i4.s 9
0x14037  call     void Microsoft.Crm.Tools.Admin.DBImportHelper::AddParameter(class [System.Data]System.Data.IDbCommand command, object value, string parameterName, valuetype [System.Data]System.Data.DbType dbType)
0x1403c  ldarg.0
0x1403d  ldloc.1
0x1403e  box      [mscorlib]System.Guid
0x14043  ldstr    aSqlaccessgroup// "@SqlAccessGroupId"
0x14048  ldc.i4.s 9
0x1404a  call     void Microsoft.Crm.Tools.Admin.DBImportHelper::AddParameter(class [System.Data]System.Data.IDbCommand command, object value, string parameterName, valuetype [System.Data]System.Data.DbType dbType)
0x1404f  ldarg.0
0x14050  ldloc.2
0x14051  ldstr    aSqlaccessgroup_0// "@SqlAccessGroupName"
0x14056  ldc.i4.s 0x10
0x14058  call     void Microsoft.Crm.Tools.Admin.DBImportHelper::AddParameter(class [System.Data]System.Data.IDbCommand command, object value, string parameterName, valuetype [System.Data]System.Data.DbType dbType)
0x1405d  ldarg.0
0x1405e  ldloc.3
0x1405f  box      [mscorlib]System.Guid
0x14064  ldstr    aReportinggroup_0// "@ReportingGroupId"
0x14069  ldc.i4.s 9
0x1406b  call     void Microsoft.Crm.Tools.Admin.DBImportHelper::AddParameter(class [System.Data]System.Data.IDbCommand command, object value, string parameterName, valuetype [System.Data]System.Data.DbType dbType)
0x14070  ldarg.0
0x14071  ldloc.s  4
0x14073  ldstr    aReportinggroup_1// "@ReportingGroupName"
0x14078  ldc.i4.s 0x10
0x1407a  call     void Microsoft.Crm.Tools.Admin.DBImportHelper::AddParameter(class [System.Data]System.Data.IDbCommand command, object value, string parameterName, valuetype [System.Data]System.Data.DbType dbType)
0x1407f  ldarg.0
0x14080  ldloc.s  5
0x14082  box      [mscorlib]System.Guid
0x14087  ldstr    aPrivreportingg// "@PrivReportingGroupId"
0x1408c  ldc.i4.s 9
0x1408e  call     void Microsoft.Crm.Tools.Admin.DBImportHelper::AddParameter(class [System.Data]System.Data.IDbCommand command, object value, string parameterName, valuetype [System.Data]System.Data.DbType dbType)
0x14093  ldarg.0
0x14094  ldloc.s  6
0x14096  ldstr    aPrivreportingg_0// "@PrivReportingGroupName"
0x1409b  ldc.i4.s 0x10
0x1409d  call     void Microsoft.Crm.Tools.Admin.DBImportHelper::AddParameter(class [System.Data]System.Data.IDbCommand command, object value, string parameterName, valuetype [System.Data]System.Data.DbType dbType)
0x140a2  ldarg.0
0x140a3  ldc.i4   0x190
0x140a8  ldstr    aUpdateorganiza_0// "UpdateOrganizationOUGroups"
0x140ad  ldstr    aDDbsShDccm2110_10// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\4"...
0x140b2  call     int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand, int32, string, string)
0x140b7  pop
0x140b8  ret
```
