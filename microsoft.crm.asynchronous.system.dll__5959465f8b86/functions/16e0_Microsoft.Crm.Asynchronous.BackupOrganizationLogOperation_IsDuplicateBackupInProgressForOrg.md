# Microsoft.Crm.Asynchronous.BackupOrganizationLogOperation::IsDuplicateBackupInProgressForOrg

- ea: `0x16e0`
- end: `0x17a7`
- name: `Microsoft.Crm.Asynchronous.BackupOrganizationLogOperation::IsDuplicateBackupInProgressForOrg`
- size: `199`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xb80`

## callees

- `0x16e0`

## string_xrefs

- `0x16f0`: `\n			use msdb\n			Select TOP 1 r.status,s.host_name,r.start_time\n			FROM sys.dm_exec_requests r \n			INNER JOIN sys.dm_exec_sessions s ON s.session_id = r.session_id\n			WHERE \n				r.command = 'BACKUP DATABASE' and \n				r.database_id = DB_ID(@OrgDbName) and \n				s.host_name is not null and\n				s.host_name like '%CrmAsyncService'`
- `0x1725`: `There is already a full backup in progress for DB {0}. Host: {1}, Status {2}, Start Time: {3}`

## pseudocode

```c

```

## disassembly

```asm
0x16e0  ldnull
0x16e1  stloc.0
0x16e2  ldarg.1
0x16e3  call     class [Microsoft.Crm.Core]Microsoft.Crm.CrmDirectSqlConnection [Microsoft.Crm.Core]Microsoft.Crm.CrmDirectSqlConnection::CreateMasterConnection(string)
0x16e8  stloc.1
0x16e9  ldloc.1
0x16ea  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Open()
0x16ef  ldloc.1
0x16f0  ldstr    aUseMsdbSelectT// "\r\n\t\t\tuse msdb\r\n\t\t\tSelect TOP "...
0x16f5  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand(string)
0x16fa  stloc.2
0x16fb  ldloc.2
0x16fc  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x1701  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x1706  ldstr    aOrgdbname// "@OrgDbName"
0x170b  ldarg.0
0x170c  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_DatabaseName()
0x1711  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x1716  pop
0x1717  ldloc.2
0x1718  callvirt instance class [System.Data]System.Data.IDataReader [System.Data]System.Data.IDbCommand::ExecuteReader()
0x171d  stloc.3
0x171e  br.s     loc_177D
0x1720  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1725  ldstr    aThereIsAlready// "There is already a full backup in progr"...
0x172a  ldc.i4.4
0x172b  newarr   [mscorlib]System.Object
0x1730  dup
0x1731  ldc.i4.0
0x1732  ldarg.0
0x1733  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_DatabaseName()
0x1738  stelem.ref
0x1739  dup
0x173a  ldc.i4.1
0x173b  ldloc.3
0x173c  ldstr    aHostName// "host_name"
0x1741  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x1746  castclass [mscorlib]System.String
0x174b  stelem.ref
0x174c  dup
0x174d  ldc.i4.2
0x174e  ldloc.3
0x174f  ldstr    aStatus// "status"
0x1754  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x1759  castclass [mscorlib]System.String
0x175e  stelem.ref
0x175f  dup
0x1760  ldc.i4.3
0x1761  ldloc.3
0x1762  ldstr    aStartTime// "start_time"
0x1767  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x176c  unbox.any [mscorlib]System.DateTime
0x1771  box      [mscorlib]System.DateTime
0x1776  stelem.ref
0x1777  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x177c  stloc.0
0x177d  ldloc.3
0x177e  callvirt instance bool [System.Data]System.Data.IDataReader::Read()
0x1783  brtrue.s loc_1720
0x1785  leave.s  loc_17A5
0x1787  ldloc.3
0x1788  brfalse.s loc_1790
0x178a  ldloc.3
0x178b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1790  endfinally
0x1791  ldloc.2
0x1792  brfalse.s loc_179A
0x1794  ldloc.2
0x1795  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x179a  endfinally
0x179b  ldloc.1
0x179c  brfalse.s loc_17A4
0x179e  ldloc.1
0x179f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x17a4  endfinally
0x17a5  ldloc.0
0x17a6  ret
```
