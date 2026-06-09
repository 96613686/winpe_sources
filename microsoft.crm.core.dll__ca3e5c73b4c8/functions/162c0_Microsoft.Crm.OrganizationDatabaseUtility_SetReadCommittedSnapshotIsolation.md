# Microsoft.Crm.OrganizationDatabaseUtility::SetReadCommittedSnapshotIsolation

- ea: `0x162c0`
- end: `0x1638f`
- name: `Microsoft.Crm.OrganizationDatabaseUtility::SetReadCommittedSnapshotIsolation`
- size: `207`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0xd020`
- `0xd180`
- `0xd2f0`
- `0xd5f0`
- `0xdab0`
- `0x162c0`
- `0x1a880`
- `0x368f0`

## string_xrefs

- `0x1636b`: `D:\a\1\s\src\Platform\Core\DataServices\OrganizationDatabaseUtility.cs`
- `0x162dc`: `Invalid Read Committed Snapshot Isolation State. Allowed values are ON or OFF`
- `0x162ec`: `if exists (select 1 from sys.databases where name = '{3}' and is_read_committed_snapshot_on = {2})\n								begin;\n								alter database {0} set read_committed_snapshot {1} with rollback immediate;\n								end`
- `0x16366`: `SetReadCommittedSnapshotIsolation`

## pseudocode

```c

```

## disassembly

```asm
0x162c0  ldarg.1
0x162c1  ldstr    aOn// "on"
0x162c6  ldc.i4.5
0x162c7  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x162cc  brfalse.s loc_162EC
0x162ce  ldarg.1
0x162cf  ldstr    aOff// "off"
0x162d4  ldc.i4.5
0x162d5  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x162da  brfalse.s loc_162EC
0x162dc  ldstr    aInvalidReadCom// "Invalid Read Committed Snapshot Isolati"...
0x162e1  ldc.i4   0x80040216
0x162e6  newobj   instance void Microsoft.Crm.CrmException::.ctor(string message, int32 errorCode)
0x162eb  throw
0x162ec  ldstr    aIfExistsSelect// "if exists (select 1 from sys.databases "...
0x162f1  stloc.0
0x162f2  ldarg.0
0x162f3  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.OrganizationDatabaseUtility::_organizationId
0x162f8  ldc.i4.0
0x162f9  ldc.i4.0
0x162fa  newobj   instance void Microsoft.Crm.CrmDbConnection::.ctor(valuetype [mscorlib]System.Guid organizationId, [opt] bool isReader, [opt] valuetype Microsoft.Crm.ReadPriority priority)
0x162ff  stloc.1
0x16300  ldloc.1
0x16301  callvirt instance void Microsoft.Crm.CrmDbConnection::Open()
0x16306  ldarg.1
0x16307  ldstr    aOn// "on"
0x1630c  ldc.i4.5
0x1630d  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x16312  brfalse.s loc_16317
0x16314  ldc.i4.1
0x16315  br.s     loc_16318
0x16317  ldc.i4.0
0x16318  stloc.2
0x16319  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1631e  ldloc.0
0x1631f  ldc.i4.4
0x16320  newarr   [mscorlib]System.Object
0x16325  dup
0x16326  ldc.i4.0
0x16327  ldloc.1
0x16328  callvirt instance string Microsoft.Crm.CrmDbConnection::get_Database()
0x1632d  call     string Microsoft.Crm.CrmEncodeDecode::SqlIdentifierEncode(string input)
0x16332  stelem.ref
0x16333  dup
0x16334  ldc.i4.1
0x16335  ldarg.1
0x16336  stelem.ref
0x16337  dup
0x16338  ldc.i4.2
0x16339  ldloc.2
0x1633a  box      [mscorlib]System.Int32
0x1633f  stelem.ref
0x16340  dup
0x16341  ldc.i4.3
0x16342  ldloc.1
0x16343  callvirt instance string Microsoft.Crm.CrmDbConnection::get_Database()
0x16348  stelem.ref
0x16349  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1634e  stloc.3
0x1634f  ldloc.1
0x16350  callvirt instance class [System.Data]System.Data.IDbCommand Microsoft.Crm.CrmDbConnection::CreateCommand()
0x16355  stloc.s  4
0x16357  ldloc.s  4
0x16359  ldloc.3
0x1635a  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x1635f  ldloc.s  4
0x16361  ldc.i4   0x282
0x16366  ldstr    aSetreadcommitt// "SetReadCommittedSnapshotIsolation"
0x1636b  ldstr    aDA1SSrcPlatfor_10// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0x16370  call     int32 Microsoft.Crm.CrmDbConnection::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand command, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0x16375  pop
0x16376  leave.s  loc_1638E
0x16378  ldloc.s  4
0x1637a  brfalse.s loc_16383
0x1637c  ldloc.s  4
0x1637e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x16383  endfinally
0x16384  ldloc.1
0x16385  brfalse.s loc_1638D
0x16387  ldloc.1
0x16388  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1638d  endfinally
0x1638e  ret
```
