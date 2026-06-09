# Microsoft.Crm.Tools.Admin.InstallDatabaseUpdatesAction::SetReadCommittedSnapshotIsolationForDatabase

- ea: `0x100a0`
- end: `0x10167`
- name: `Microsoft.Crm.Tools.Admin.InstallDatabaseUpdatesAction::SetReadCommittedSnapshotIsolationForDatabase`
- size: `199`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x100a0`

## string_xrefs

- `0x1011c`: `d:\dbs\sh\dccm2\1101_190851\cmd\44\src\Tools2\DMSnapin\lib\Organization\BusinessConfiguration.cs`
- `0x100bb`: `AllowReadCommittedSnapshotIsolation`
- `0x100d6`: `if exists(select 1 from sys.databases where name = '{1}' and is_read_committed_snapshot_on = 0)\n									begin;\n									alter database {0} set read_committed_snapshot on with rollback immediate;\n									end;`
- `0x10117`: `SetReadCommittedSnapshotIsolationForDatabase`

## pseudocode

```c

```

## disassembly

```asm
0x100a0  ldarg.0
0x100a1  call     int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::GetInstallConnectionTimeout()
0x100a6  ldc.i4.0
0x100a7  ldc.i4.0
0x100a8  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::.ctor(valuetype [mscorlib]System.Guid, int32, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0x100ad  stloc.0
0x100ae  ldloc.0
0x100af  ldarg.0
0x100b0  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.SqlExecutionContext::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection, valuetype [mscorlib]System.Guid)
0x100b5  stloc.1
0x100b6  call     class [Microsoft.Crm.Core]Microsoft.Crm.IDeploymentInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.DeploymentInfoProvider::get_Instance()
0x100bb  ldstr    aAllowreadcommi// "AllowReadCommittedSnapshotIsolation"
0x100c0  ldc.i4.0
0x100c1  callvirt T0x2B000013
0x100c6  stloc.2
0x100c7  ldloc.2
0x100c8  brtrue.s loc_100CF
0x100ca  leave    loc_10166
0x100cf  ldloc.1
0x100d0  ldc.i4.0
0x100d1  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.SqlExecutionContext::OnBeginRequest(bool)
0x100d6  ldstr    aIfExistsSelect_1// "if exists(select 1 from sys.databases w"...
0x100db  stloc.3
0x100dc  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x100e1  ldloc.3
0x100e2  ldc.i4.2
0x100e3  newarr   [mscorlib]System.Object
0x100e8  dup
0x100e9  ldc.i4.0
0x100ea  ldloc.0
0x100eb  callvirt instance string [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::get_Database()
0x100f0  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::SqlIdentifierEncode(string)
0x100f5  stelem.ref
0x100f6  dup
0x100f7  ldc.i4.1
0x100f8  ldloc.0
0x100f9  callvirt instance string [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::get_Database()
0x100fe  stelem.ref
0x100ff  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x10104  stloc.s  4
0x10106  ldloc.1
0x10107  ldloc.s  4
0x10109  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.SqlExecutionContext::CreateSqlCommand(string)
0x1010e  stloc.s  5
0x10110  ldloc.s  5
0x10112  ldc.i4   0xA80
0x10117  ldstr    aSetreadcommitt// "SetReadCommittedSnapshotIsolationForDat"...
0x1011c  ldstr    aDDbsShDccm2110_8// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\4"...
0x10121  call     int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand, int32, string, string)
0x10126  pop
0x10127  leave.s  loc_10135
0x10129  ldloc.s  5
0x1012b  brfalse.s loc_10134
0x1012d  ldloc.s  5
0x1012f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x10134  endfinally
0x10135  ldloc.1
0x10136  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.SqlExecutionContext::OnEndRequest()
0x1013b  call     class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationSettingsProvider [Microsoft.Crm.Core]Microsoft.Crm.OrganizationSettingsProvider::get_Instance()
0x10140  ldarg.0
0x10141  ldloc.2
0x10142  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationSettingsProvider::SetOrganizationReadCommittedSnapshotIsolation(valuetype [mscorlib]System.Guid, bool)
0x10147  leave.s  loc_10166
0x10149  pop
0x1014a  ldloc.1
0x1014b  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.SqlExecutionContext::OnErrorRequest()
0x10150  rethrow
0x10152  ldloc.1
0x10153  brfalse.s loc_1015B
0x10155  ldloc.1
0x10156  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1015b  endfinally
0x1015c  ldloc.0
0x1015d  brfalse.s loc_10165
0x1015f  ldloc.0
0x10160  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x10165  endfinally
0x10166  ret
```
