# Microsoft.Crm.Asynchronous.BackupOrganizationLogOperation::CleanupSqlBackupRestoreHistory

- ea: `0x1570`
- end: `0x15b4`
- name: `Microsoft.Crm.Asynchronous.BackupOrganizationLogOperation::CleanupSqlBackupRestoreHistory`
- size: `68`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x1570`

## string_xrefs

- `0x1571`: `organizationService`

## pseudocode

```c

```

## disassembly

```asm
0x1570  ldarg.0
0x1571  ldstr    aOrganizationse// "organizationService"
0x1576  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x157b  ldarg.1
0x157c  ldstr    aOrganizationid// "organizationId"
0x1581  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x1586  ldarg.0
0x1587  ldarg.1
0x1588  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationDBData [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.Organization.IOrganizationService::RetrieveDBInfo(valuetype [mscorlib]System.Guid)
0x158d  stloc.0
0x158e  ldloc.0
0x158f  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationDBData::get_PrimaryServer()
0x1594  ldarg.2
0x1595  call     void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.SqlUtility::CleanSqlBackupRestoreHistory(string, valuetype [mscorlib]System.DateTime)
0x159a  ldloc.0
0x159b  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationDBData::get_SecondaryServer()
0x15a0  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x15a5  brtrue.s loc_15B3
0x15a7  ldloc.0
0x15a8  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationDBData::get_SecondaryServer()
0x15ad  ldarg.2
0x15ae  call     void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.SqlUtility::CleanSqlBackupRestoreHistory(string, valuetype [mscorlib]System.DateTime)
0x15b3  ret
```
