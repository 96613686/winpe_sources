# Microsoft.Crm.OrganizationDatabaseUtility::IsSnapshotIsolationAndRcsiEnabledInDb

- ea: `0x160c0`
- end: `0x1620b`
- name: `Microsoft.Crm.OrganizationDatabaseUtility::IsSnapshotIsolationAndRcsiEnabledInDb`
- size: `331`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x15fc0`
- `0x16040`

## callees

- `0x4640`
- `0x4790`
- `0xd5f0`
- `0xdaf0`
- `0x11410`
- `0x160c0`
- `0x1be80`
- `0x1eaa0`
- `0x1f4d0`
- `0x444f0`

## string_xrefs

- `0x16162`: `D:\a\1\s\src\Platform\Core\DataServices\OrganizationDatabaseUtility.cs`
- `0x1611c`: `ReadCommittedSnapshotIsolation`
- `0x16199`: `ReadCommittedSnapshotIsolation`
- `0x161f4`: `ReadCommittedSnapshotIsolation`
- `0x16127`: `select snapshot_isolation_state, is_read_committed_snapshot_on from sys.databases where name = @dbName;`
- `0x161a0`: `is_read_committed_snapshot_on`
- `0x161d3`: `Snapshot isolation state in DB: {0}, ReadCommittedSnapshotIsolation state in DB: {1}`

## pseudocode

```c

```

## disassembly

```asm
0x160c0  ldarg.1
0x160c1  ldstr    aIsqlexecutionc// "ISqlExecutionContext cannot be null"
0x160c6  call     void Microsoft.Crm.Exceptions::ThrowIfNull(object parameter, string name)
0x160cb  ldarg.1
0x160cc  callvirt instance class Microsoft.Crm.CrmDbConnection Microsoft.Crm.ISqlExecutionContext::get_Connection()
0x160d1  ldstr    aConnectionCann// "connection cannot be null"
0x160d6  call     void Microsoft.Crm.Exceptions::ThrowIfNull(object parameter, string name)
0x160db  call     class Microsoft.Crm.LocatorService Microsoft.Crm.LocatorService::get_Instance()
0x160e0  ldarg.0
0x160e1  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.OrganizationDatabaseUtility::_organizationId
0x160e6  ldc.i4.1
0x160e7  newarr   [mscorlib]System.String
0x160ec  dup
0x160ed  ldc.i4.0
0x160ee  ldstr    aDatabasename// "DatabaseName"
0x160f3  stelem.ref
0x160f4  callvirt instance class Microsoft.Crm.Data.PropertyBag Microsoft.Crm.LocatorService::GetOrganization(valuetype [mscorlib]System.Guid organizationId, string[] columns)
0x160f9  ldstr    aDatabasename// "DatabaseName"
0x160fe  callvirt instance object Microsoft.Crm.Data.PropertyBag::get_Item(string propertyName)
0x16103  castclass [mscorlib]System.String
0x16108  stloc.0
0x16109  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, bool>::.ctor()
0x1610e  stloc.1
0x1610f  ldloc.1
0x16110  ldstr    aSnapshotisolat_0// "SnapshotIsolation"
0x16115  ldc.i4.0
0x16116  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, bool>::Add(var<u1>, !!T0)
0x1611b  ldloc.1
0x1611c  ldstr    aReadcommitteds_0// "ReadCommittedSnapshotIsolation"
0x16121  ldc.i4.0
0x16122  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, bool>::Add(var<u1>, !!T0)
0x16127  ldstr    aSelectSnapshot// "select snapshot_isolation_state, is_rea"...
0x1612c  stloc.2
0x1612d  ldarg.1
0x1612e  callvirt instance class Microsoft.Crm.CrmDbConnection Microsoft.Crm.ISqlExecutionContext::get_Connection()
0x16133  callvirt instance class [System.Data]System.Data.IDbCommand Microsoft.Crm.CrmDbConnection::CreateCommand()
0x16138  stloc.3
0x16139  ldloc.3
0x1613a  ldloc.2
0x1613b  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x16140  ldloc.3
0x16141  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x16146  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x1614b  ldstr    aDbname// "@dbName"
0x16150  ldloc.0
0x16151  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x16156  pop
0x16157  ldloc.3
0x16158  ldc.i4   0x240
0x1615d  ldstr    aIssnapshotisol// "IsSnapshotIsolationAndRcsiEnabledInDb"
0x16162  ldstr    aDA1SSrcPlatfor_10// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0x16167  call     class [System.Data]System.Data.IDataReader Microsoft.Crm.CrmDbConnection::ExecuteReader(class [System.Data]System.Data.IDbCommand command, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0x1616c  stloc.s  4
0x1616e  ldloc.s  4
0x16170  callvirt instance bool [System.Data]System.Data.IDataReader::Read()
0x16175  brfalse.s loc_161B4
0x16177  ldloc.1
0x16178  ldstr    aSnapshotisolat_0// "SnapshotIsolation"
0x1617d  ldloc.s  4
0x1617f  ldstr    aSnapshotIsolat// "snapshot_isolation_state"
0x16184  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x16189  unbox.any [mscorlib]System.Byte
0x1618e  call     bool [mscorlib]System.Convert::ToBoolean(unsigned int8)
0x16193  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, bool>::set_Item(var<u1>, !!T0)
0x16198  ldloc.1
0x16199  ldstr    aReadcommitteds_0// "ReadCommittedSnapshotIsolation"
0x1619e  ldloc.s  4
0x161a0  ldstr    aIsReadCommitte// "is_read_committed_snapshot_on"
0x161a5  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x161aa  unbox.any [mscorlib]System.Boolean
0x161af  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, bool>::set_Item(var<u1>, !!T0)
0x161b4  leave.s  loc_161CC
0x161b6  ldloc.s  4
0x161b8  brfalse.s loc_161C1
0x161ba  ldloc.s  4
0x161bc  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x161c1  endfinally
0x161c2  ldloc.3
0x161c3  brfalse.s loc_161CB
0x161c5  ldloc.3
0x161c6  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x161cb  endfinally
0x161cc  call     valuetype [mscorlib]System.Guid Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x161d1  ldc.i4.s 0x14
0x161d3  ldstr    aSnapshotIsolat_0// "Snapshot isolation state in DB: {0}, Re"...
0x161d8  ldc.i4.2
0x161d9  newarr   [mscorlib]System.Object
0x161de  dup
0x161df  ldc.i4.0
0x161e0  ldloc.1
0x161e1  ldstr    aSnapshotisolat_0// "SnapshotIsolation"
0x161e6  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, bool>::get_Item(void)
0x161eb  box      [mscorlib]System.Boolean
0x161f0  stelem.ref
0x161f1  dup
0x161f2  ldc.i4.1
0x161f3  ldloc.1
0x161f4  ldstr    aReadcommitteds_0// "ReadCommittedSnapshotIsolation"
0x161f9  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, bool>::get_Item(void)
0x161fe  box      [mscorlib]System.Boolean
0x16203  stelem.ref
0x16204  call     void Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid orgId, valuetype Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x16209  ldloc.1
0x1620a  ret
```
