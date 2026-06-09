# Microsoft.Crm.Asynchronous.Rollups.JobSelectorDataAccess::SetupDbCommandForUpdate

- ea: `0xd5a0`
- end: `0xd619`
- name: `Microsoft.Crm.Asynchronous.Rollups.JobSelectorDataAccess::SetupDbCommandForUpdate`
- size: `121`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0xd280`
- `0xd2e0`

## callees

- `0xc870`
- `0xd620`
- `0xd660`
- `0xd670`
- `0xd6b0`

## string_xrefs

- `0xd5a6`: `UPDATE \n	TOP(@recordsToSelect) RJ\nSET \n	RJ.[StateCode] = @finalStateCode\n	{0}\n{1}\nFROM\n	[RollupJobBase] RJ\n{2}`

## pseudocode

```c

```

## disassembly

```asm
0xd5a0  ldarg.1
0xd5a1  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xd5a6  ldstr    aUpdateTopRecor// "UPDATE \r\n\tTOP(@recordsToSelect) RJ\r"...
0xd5ab  ldc.i4.3
0xd5ac  newarr   [mscorlib]System.Object
0xd5b1  dup
0xd5b2  ldc.i4.0
0xd5b3  ldarg.0
0xd5b4  call     instance string Microsoft.Crm.Asynchronous.Rollups.JobSelectorDataAccess::GetSqlForRetryCountModification()
0xd5b9  stelem.ref
0xd5ba  dup
0xd5bb  ldc.i4.1
0xd5bc  ldarg.0
0xd5bd  ldarg.2
0xd5be  call     instance string Microsoft.Crm.Asynchronous.Rollups.JobSelectorDataAccess::GetSqlForOutputClause(bool outputData)
0xd5c3  stelem.ref
0xd5c4  dup
0xd5c5  ldc.i4.2
0xd5c6  ldarg.0
0xd5c7  ldc.i4.1
0xd5c8  call     instance string Microsoft.Crm.Asynchronous.Rollups.JobSelectorDataAccess::GetSqlForWhereClause(valuetype PostponeUntilBehavior postponeUntilBehavior)
0xd5cd  stelem.ref
0xd5ce  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xd5d3  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0xd5d8  ldarg.1
0xd5d9  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0xd5de  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0xd5e3  stloc.0
0xd5e4  ldarg.0
0xd5e5  ldloc.0
0xd5e6  call     instance void Microsoft.Crm.Asynchronous.Rollups.JobSelectorDataAccess::AddParametersForWhereClause(class [System.Data]System.Data.SqlClient.SqlParameterCollection parameters)
0xd5eb  ldloc.0
0xd5ec  ldstr    aFinalstatecode// "@finalStateCode"
0xd5f1  ldarg.0
0xd5f2  ldfld    valuetype [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Types.RollupJobState Microsoft.Crm.Asynchronous.Rollups.JobSelectorDataAccess::_finalState
0xd5f7  box      [mscorlib]System.Int32
0xd5fc  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0xd601  pop
0xd602  ldloc.0
0xd603  ldstr    aRecordstoselec// "@recordsToSelect"
0xd608  call     int32 Microsoft.Crm.Asynchronous.Rollups.RollupConfiguration::get_IncrementalRollupDequeueBatchSize()
0xd60d  box      [mscorlib]System.Int32
0xd612  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0xd617  pop
0xd618  ret
```
