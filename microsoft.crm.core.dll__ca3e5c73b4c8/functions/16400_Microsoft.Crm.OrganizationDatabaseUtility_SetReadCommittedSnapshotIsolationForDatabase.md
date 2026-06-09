# Microsoft.Crm.OrganizationDatabaseUtility::SetReadCommittedSnapshotIsolationForDatabase

- ea: `0x16400`
- end: `0x164c7`
- name: `Microsoft.Crm.OrganizationDatabaseUtility::SetReadCommittedSnapshotIsolationForDatabase`
- size: `199`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x16390`

## callees

- `0xb10`
- `0x1090`
- `0x1470`
- `0xd020`
- `0xd1a0`
- `0xdab0`
- `0xdc40`
- `0x11a10`
- `0x11be0`
- `0x11c80`
- `0x11d00`
- `0x11dd0`
- `0x16400`
- `0x368f0`

## string_xrefs

- `0x1647c`: `D:\a\1\s\src\Platform\Core\DataServices\OrganizationDatabaseUtility.cs`
- `0x1641b`: `AllowReadCommittedSnapshotIsolation`
- `0x16436`: `if exists (select 1 from sys.databases where name = '{1}' and is_read_committed_snapshot_on = 0)\n										begin;\n										alter database {0} set read_committed_snapshot on with rollback immediate;\n										end`
- `0x16477`: `SetReadCommittedSnapshotIsolationForDatabase`

## pseudocode

```c

```

## disassembly

```asm
0x16400  ldarg.1
0x16401  call     int32 Microsoft.Crm.CrmDbConnection::GetInstallConnectionTimeout()
0x16406  ldc.i4.0
0x16407  ldc.i4.0
0x16408  newobj   instance void Microsoft.Crm.CrmDbConnection::.ctor(valuetype [mscorlib]System.Guid organizationId, int32 commandTimeout, [opt] bool isReader, [opt] valuetype Microsoft.Crm.ReadPriority priority)
0x1640d  stloc.0
0x1640e  ldloc.0
0x1640f  ldarg.1
0x16410  newobj   instance void Microsoft.Crm.SqlExecutionContext::.ctor(class Microsoft.Crm.CrmDbConnection connection, valuetype [mscorlib]System.Guid organizationId)
0x16415  stloc.1
0x16416  call     class Microsoft.Crm.IDeploymentInfoProvider Microsoft.Crm.DeploymentInfoProvider::get_Instance()
0x1641b  ldstr    aAllowreadcommi// "AllowReadCommittedSnapshotIsolation"
0x16420  ldc.i4.0
0x16421  callvirt T0x2B00004A
0x16426  stloc.2
0x16427  ldloc.2
0x16428  brtrue.s loc_1642F
0x1642a  leave    loc_164C6
0x1642f  ldloc.1
0x16430  ldc.i4.0
0x16431  callvirt instance void Microsoft.Crm.SqlExecutionContext::OnBeginRequest(bool startTransaction)
0x16436  ldstr    aIfExistsSelect_0// "if exists (select 1 from sys.databases "...
0x1643b  stloc.3
0x1643c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x16441  ldloc.3
0x16442  ldc.i4.2
0x16443  newarr   [mscorlib]System.Object
0x16448  dup
0x16449  ldc.i4.0
0x1644a  ldloc.0
0x1644b  callvirt instance string Microsoft.Crm.CrmDbConnection::get_Database()
0x16450  call     string Microsoft.Crm.CrmEncodeDecode::SqlIdentifierEncode(string input)
0x16455  stelem.ref
0x16456  dup
0x16457  ldc.i4.1
0x16458  ldloc.0
0x16459  callvirt instance string Microsoft.Crm.CrmDbConnection::get_Database()
0x1645e  stelem.ref
0x1645f  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x16464  stloc.s  4
0x16466  ldloc.1
0x16467  ldloc.s  4
0x16469  callvirt instance class [System.Data]System.Data.IDbCommand Microsoft.Crm.SqlExecutionContext::CreateSqlCommand(string sqlCommand)
0x1646e  stloc.s  5
0x16470  ldloc.s  5
0x16472  ldc.i4   0x2BA
0x16477  ldstr    aSetreadcommitt_0// "SetReadCommittedSnapshotIsolationForDat"...
0x1647c  ldstr    aDA1SSrcPlatfor_10// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0x16481  call     int32 Microsoft.Crm.CrmDbConnection::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand command, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0x16486  pop
0x16487  leave.s  loc_16495
0x16489  ldloc.s  5
0x1648b  brfalse.s loc_16494
0x1648d  ldloc.s  5
0x1648f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x16494  endfinally
0x16495  ldloc.1
0x16496  callvirt instance void Microsoft.Crm.SqlExecutionContext::OnEndRequest()
0x1649b  call     class Microsoft.Crm.IOrganizationSettingsProvider Microsoft.Crm.OrganizationSettingsProvider::get_Instance()
0x164a0  ldarg.1
0x164a1  ldloc.2
0x164a2  callvirt instance void Microsoft.Crm.IOrganizationSettingsProvider::SetOrganizationReadCommittedSnapshotIsolation(valuetype [mscorlib]System.Guid organizationId, bool enable)
0x164a7  leave.s  loc_164C6
0x164a9  pop
0x164aa  ldloc.1
0x164ab  callvirt instance void Microsoft.Crm.SqlExecutionContext::OnErrorRequest()
0x164b0  rethrow
0x164b2  ldloc.1
0x164b3  brfalse.s loc_164BB
0x164b5  ldloc.1
0x164b6  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x164bb  endfinally
0x164bc  ldloc.0
0x164bd  brfalse.s loc_164C5
0x164bf  ldloc.0
0x164c0  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x164c5  endfinally
0x164c6  ret
```
