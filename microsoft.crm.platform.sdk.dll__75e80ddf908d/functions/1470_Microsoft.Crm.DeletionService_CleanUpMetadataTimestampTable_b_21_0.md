# Microsoft.Crm.DeletionService::<CleanUpMetadataTimestampTable>b__21_0

- ea: `0x1470`
- end: `0x15ff`
- name: `Microsoft.Crm.DeletionService::<CleanUpMetadataTimestampTable>b__21_0`
- size: `399`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callees

- `0x2e0`
- `0x640`
- `0x1470`
- `0xaf40`
- `0xaf50`

## string_xrefs

- `0x1519`: `@numOfRecordsToBeDeleted`
- `0x1478`: `DeletionService: Inside DeletionService.CleanUpMetadataTimestampTable`
- `0x1498`: `DeletionService: Inside DeletionService.CleanUpMetadataTimestampTable`
- `0x14f6`: `DECLARE @MaxVersionNumber timestamp\nSELECT @MaxVersionNumber = max(VersionNumber) from MetadataTimestamp\nDELETE TOP(@numOfRecordsToBeDeleted) FROM MetadataTimestamp WHERE VersionNumber < @MaxVersionNumber `
- `0x1558`: `DeletionService: Deletion Service deleted {0} rows in {1} seconds from MetadataTimestamp. Completed all Deletes : {2}`
- `0x1596`: `DeletionService: Execution of CleanUpMetadataTimestampTable is completed`
- `0x15d6`: `DeletionService: Error cleaning up MetadataTimestamp Table`

## pseudocode

```c

```

## disassembly

```asm
0x1470  ldarg.0
0x1471  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.DeletionService::_organizationId
0x1476  ldc.i4.s 0x14
0x1478  ldstr    aDeletionservic_26// "DeletionService: Inside DeletionService"...
0x147d  ldc.i4.0
0x147e  newarr   [mscorlib]System.Object
0x1483  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1488  call     class Microsoft.Crm.Platform.DeletionServiceEventSource Microsoft.Crm.Platform.DeletionServiceEventSource::get_Instance()
0x148d  ldarg.0
0x148e  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.DeletionService::_organizationId
0x1493  ldstr    aCleanupmetadat// "CleanUpMetadataTimestampTable"
0x1498  ldstr    aDeletionservic_26// "DeletionService: Inside DeletionService"...
0x149d  ldc.i4.0
0x149e  ldc.i4.0
0x149f  ldsfld   bool Microsoft.Crm.DeletionService::AllowVerboseLogging
0x14a4  ldsfld   int32 Microsoft.Crm.DeletionService::DeletionServiceDBConnectionTimeoutInSeconds
0x14a9  ldsfld   int32 Microsoft.Crm.DeletionService::DeletionServiceExecutionTimeoutInMinutes
0x14ae  ldsfld   int32 Microsoft.Crm.DeletionService::NumOfRecordsToBeDeletedPerExecution
0x14b3  ldc.i4.0
0x14b4  ldsfld   string [mscorlib]System.String::Empty
0x14b9  callvirt instance void Microsoft.Crm.Platform.DeletionServiceEventSource::DeletionServiceInformation(valuetype [mscorlib]System.Guid organizationId, string moduleName, string message, int32 recordsDeleted, int32 durationInSecs, bool verbose, int32 deletionServiceDBConnectionTimeoutInSeconds, int32 deletionServiceExecutionTimeoutInMinutes, int32 top_numOfRecordsToBeDeleted, bool completedAllDeletes, string sqlText)
0x14be  ldarg.0
0x14bf  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.DeletionService::_organizationId
0x14c4  ldsfld   int32 Microsoft.Crm.DeletionService::DeletionServiceDBConnectionTimeoutInSeconds
0x14c9  ldc.i4.0
0x14ca  ldc.i4.0
0x14cb  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::.ctor(valuetype [mscorlib]System.Guid, int32, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0x14d0  stloc.0
0x14d1  ldloc.0
0x14d2  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Open()
0x14d7  ldloc.0
0x14d8  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection)
0x14dd  stloc.1
0x14de  ldsfld   string [mscorlib]System.String::Empty
0x14e3  stloc.2
0x14e4  ldloc.0
0x14e5  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand()
0x14ea  stloc.3
0x14eb  ldc.i4.m1
0x14ec  stloc.s  4
0x14ee  ldc.i4.0
0x14ef  stloc.s  5
0x14f1  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x14f6  ldstr    aDeclareMaxvers// "DECLARE @MaxVersionNumber timestamp\r\n"...
0x14fb  ldc.i4.0
0x14fc  newarr   [mscorlib]System.Object
0x1501  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1506  stloc.s  6
0x1508  ldloc.3
0x1509  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x150e  isinst   [System.Data]System.Data.SqlClient.SqlParameterCollection
0x1513  dup
0x1514  callvirt instance void [System.Data]System.Data.Common.DbParameterCollection::Clear()
0x1519  ldstr    aNumofrecordsto// "@numOfRecordsToBeDeleted"
0x151e  ldsfld   int32 Microsoft.Crm.DeletionService::NumOfRecordsToBeDeletedPerExecution
0x1523  box      [mscorlib]System.Int32
0x1528  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x152d  pop
0x152e  ldloc.3
0x152f  ldloc.s  6
0x1531  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x1536  ldloc.3
0x1537  callvirt instance string [System.Data]System.Data.IDbCommand::get_CommandText()
0x153c  stloc.2
0x153d  ldloc.1
0x153e  ldloc.3
0x153f  ldarg.0
0x1540  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.DeletionService::_organizationId
0x1545  ldloca.s 4
0x1547  ldloca.s 5
0x1549  call     int32 Microsoft.Crm.DeletionService::ExecuteTransaction(class [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction transaction, class [System.Data]System.Data.IDbCommand command, valuetype [mscorlib]System.Guid orgId, [out] int32& durationInSecs, [out] bool& completedAllDelete)
0x154e  stloc.s  7
0x1550  ldarg.0
0x1551  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.DeletionService::_organizationId
0x1556  ldc.i4.s 0x14
0x1558  ldstr    aDeletionservic_27// "DeletionService: Deletion Service delet"...
0x155d  ldc.i4.3
0x155e  newarr   [mscorlib]System.Object
0x1563  dup
0x1564  ldc.i4.0
0x1565  ldloc.s  7
0x1567  box      [mscorlib]System.Int32
0x156c  stelem.ref
0x156d  dup
0x156e  ldc.i4.1
0x156f  ldloc.s  4
0x1571  box      [mscorlib]System.Int32
0x1576  stelem.ref
0x1577  dup
0x1578  ldc.i4.2
0x1579  ldloc.s  5
0x157b  box      [mscorlib]System.Boolean
0x1580  stelem.ref
0x1581  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1586  call     class Microsoft.Crm.Platform.DeletionServiceEventSource Microsoft.Crm.Platform.DeletionServiceEventSource::get_Instance()
0x158b  ldarg.0
0x158c  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.DeletionService::_organizationId
0x1591  ldstr    aCleanupmetadat// "CleanUpMetadataTimestampTable"
0x1596  ldstr    aDeletionservic_28// "DeletionService: Execution of CleanUpMe"...
0x159b  ldloc.s  7
0x159d  ldloc.s  4
0x159f  ldsfld   bool Microsoft.Crm.DeletionService::AllowVerboseLogging
0x15a4  ldsfld   int32 Microsoft.Crm.DeletionService::DeletionServiceDBConnectionTimeoutInSeconds
0x15a9  ldsfld   int32 Microsoft.Crm.DeletionService::DeletionServiceExecutionTimeoutInMinutes
0x15ae  ldsfld   int32 Microsoft.Crm.DeletionService::NumOfRecordsToBeDeletedPerExecution
0x15b3  ldc.i4.1
0x15b4  ldloc.3
0x15b5  callvirt instance string [System.Data]System.Data.IDbCommand::get_CommandText()
0x15ba  callvirt instance void Microsoft.Crm.Platform.DeletionServiceEventSource::DeletionServiceInformation(valuetype [mscorlib]System.Guid organizationId, string moduleName, string message, int32 recordsDeleted, int32 durationInSecs, bool verbose, int32 deletionServiceDBConnectionTimeoutInSeconds, int32 deletionServiceExecutionTimeoutInMinutes, int32 top_numOfRecordsToBeDeleted, bool completedAllDeletes, string sqlText)
0x15bf  leave.s  loc_15CB
0x15c1  ldloc.3
0x15c2  brfalse.s loc_15CA
0x15c4  ldloc.3
0x15c5  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x15ca  endfinally
0x15cb  leave.s  loc_15FE
0x15cd  stloc.s  8
0x15cf  ldarg.0
0x15d0  ldc.i4   0x80004003
0x15d5  conv.u8
0x15d6  ldstr    aDeletionservic_29// "DeletionService: Error cleaning up Meta"...
0x15db  ldloc.s  8
0x15dd  callvirt instance string [mscorlib]System.Object::ToString()
0x15e2  ldloc.2
0x15e3  call     instance void Microsoft.Crm.DeletionService::LogCrmTraceAndEventLog(int64 logId, string crmTraceMessage, string errorMessage, string sqlText)
0x15e8  rethrow
0x15ea  ldloc.1
0x15eb  brfalse.s loc_15F3
0x15ed  ldloc.1
0x15ee  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x15f3  endfinally
0x15f4  ldloc.0
0x15f5  brfalse.s loc_15FD
0x15f7  ldloc.0
0x15f8  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x15fd  endfinally
0x15fe  ret
```
