# Microsoft.Crm.Tools.Admin.SetReadCommittedSnapshotIsolation::SetReadCommittedSnapshotIsolationForDatabase

- ea: `0xddd0`
- end: `0xde97`
- name: `Microsoft.Crm.Tools.Admin.SetReadCommittedSnapshotIsolation::SetReadCommittedSnapshotIsolationForDatabase`
- size: `199`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0xddd0`

## string_xrefs

- `0xde4c`: `d:\dbs\sh\dccm2\1101_190851\cmd\44\src\Tools2\DMSnapin\lib\Organization\BusinessConfiguration.cs`
- `0xddeb`: `AllowReadCommittedSnapshotIsolation`
- `0xde06`: `if exists(select 1 from sys.databases where name = '{1}' and is_read_committed_snapshot_on = 0)\n									begin;\n									alter database {0} set read_committed_snapshot on with rollback immediate;\n									end;`
- `0xde47`: `SetReadCommittedSnapshotIsolationForDatabase`

## pseudocode

```c

```

## disassembly

```asm
0xddd0  ldarg.0
0xddd1  call     int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::GetInstallConnectionTimeout()
0xddd6  ldc.i4.0
0xddd7  ldc.i4.0
0xddd8  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::.ctor(valuetype [mscorlib]System.Guid, int32, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0xdddd  stloc.0
0xddde  ldloc.0
0xdddf  ldarg.0
0xdde0  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.SqlExecutionContext::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection, valuetype [mscorlib]System.Guid)
0xdde5  stloc.1
0xdde6  call     class [Microsoft.Crm.Core]Microsoft.Crm.IDeploymentInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.DeploymentInfoProvider::get_Instance()
0xddeb  ldstr    aAllowreadcommi// "AllowReadCommittedSnapshotIsolation"
0xddf0  ldc.i4.0
0xddf1  callvirt T0x2B000013
0xddf6  stloc.2
0xddf7  ldloc.2
0xddf8  brtrue.s loc_DDFF
0xddfa  leave    loc_DE96
0xddff  ldloc.1
0xde00  ldc.i4.0
0xde01  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.SqlExecutionContext::OnBeginRequest(bool)
0xde06  ldstr    aIfExistsSelect_1// "if exists(select 1 from sys.databases w"...
0xde0b  stloc.3
0xde0c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xde11  ldloc.3
0xde12  ldc.i4.2
0xde13  newarr   [mscorlib]System.Object
0xde18  dup
0xde19  ldc.i4.0
0xde1a  ldloc.0
0xde1b  callvirt instance string [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::get_Database()
0xde20  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::SqlIdentifierEncode(string)
0xde25  stelem.ref
0xde26  dup
0xde27  ldc.i4.1
0xde28  ldloc.0
0xde29  callvirt instance string [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::get_Database()
0xde2e  stelem.ref
0xde2f  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xde34  stloc.s  4
0xde36  ldloc.1
0xde37  ldloc.s  4
0xde39  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.SqlExecutionContext::CreateSqlCommand(string)
0xde3e  stloc.s  5
0xde40  ldloc.s  5
0xde42  ldc.i4   0x2DA
0xde47  ldstr    aSetreadcommitt// "SetReadCommittedSnapshotIsolationForDat"...
0xde4c  ldstr    aDDbsShDccm2110_8// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\4"...
0xde51  call     int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand, int32, string, string)
0xde56  pop
0xde57  leave.s  loc_DE65
0xde59  ldloc.s  5
0xde5b  brfalse.s loc_DE64
0xde5d  ldloc.s  5
0xde5f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xde64  endfinally
0xde65  ldloc.1
0xde66  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.SqlExecutionContext::OnEndRequest()
0xde6b  call     class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationSettingsProvider [Microsoft.Crm.Core]Microsoft.Crm.OrganizationSettingsProvider::get_Instance()
0xde70  ldarg.0
0xde71  ldloc.2
0xde72  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationSettingsProvider::SetOrganizationReadCommittedSnapshotIsolation(valuetype [mscorlib]System.Guid, bool)
0xde77  leave.s  loc_DE96
0xde79  pop
0xde7a  ldloc.1
0xde7b  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.SqlExecutionContext::OnErrorRequest()
0xde80  rethrow
0xde82  ldloc.1
0xde83  brfalse.s loc_DE8B
0xde85  ldloc.1
0xde86  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xde8b  endfinally
0xde8c  ldloc.0
0xde8d  brfalse.s loc_DE95
0xde8f  ldloc.0
0xde90  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xde95  endfinally
0xde96  ret
```
