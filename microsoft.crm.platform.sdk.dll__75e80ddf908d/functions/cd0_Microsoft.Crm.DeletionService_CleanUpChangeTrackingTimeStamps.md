# Microsoft.Crm.DeletionService::CleanUpChangeTrackingTimeStamps

- ea: `0xcd0`
- end: `0xdbb`
- name: `Microsoft.Crm.DeletionService::CleanUpChangeTrackingTimeStamps`
- size: `235`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callers

- `0xb00`

## callees

- `0x640`
- `0xcd0`
- `0xaf40`
- `0xaf50`

## string_xrefs

- `0xce0`: `DeletionService: Inside DeletionService.CleanUpChangeTrackingTimeStamps`
- `0xd1e`: `DECLARE @versionNumberExpired bigint\nSELECT @versionNumberExpired = coalesce(min(CompletedSyncVersionNumber), @@dbts) FROM Subscription\nDELETE TOP(@numOfRecordsToBeDeleted) FROM [TimeStampDateMapping] where TimeStamp <= @versionNumberExpired`
- `0xd44`: `@numOfRecordsToBeDeleted`
- `0xd7c`: `DeletionService: Execution of CleanUpChangeTrackingTimeStamps is completed.`

## pseudocode

```c

```

## disassembly

```asm
0xcd0  call     class Microsoft.Crm.Platform.DeletionServiceEventSource Microsoft.Crm.Platform.DeletionServiceEventSource::get_Instance()
0xcd5  ldarg.0
0xcd6  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.DeletionService::_organizationId
0xcdb  ldstr    aCleanupchanget// "CleanUpChangeTrackingTimeStamps"
0xce0  ldstr    aDeletionservic_8// "DeletionService: Inside DeletionService"...
0xce5  ldc.i4.0
0xce6  ldc.i4.0
0xce7  ldsfld   bool Microsoft.Crm.DeletionService::AllowVerboseLogging
0xcec  ldsfld   int32 Microsoft.Crm.DeletionService::DeletionServiceDBConnectionTimeoutInSeconds
0xcf1  ldsfld   int32 Microsoft.Crm.DeletionService::DeletionServiceExecutionTimeoutInMinutes
0xcf6  ldsfld   int32 Microsoft.Crm.DeletionService::NumOfRecordsToBeDeletedPerExecution
0xcfb  ldc.i4.0
0xcfc  ldsfld   string [mscorlib]System.String::Empty
0xd01  callvirt instance void Microsoft.Crm.Platform.DeletionServiceEventSource::DeletionServiceInformation(valuetype [mscorlib]System.Guid organizationId, string moduleName, string message, int32 recordsDeleted, int32 durationInSecs, bool verbose, int32 deletionServiceDBConnectionTimeoutInSeconds, int32 deletionServiceExecutionTimeoutInMinutes, int32 top_numOfRecordsToBeDeleted, bool completedAllDeletes, string sqlText)
0xd06  ldarg.1
0xd07  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection)
0xd0c  stloc.0
0xd0d  ldarg.1
0xd0e  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand()
0xd13  stloc.1
0xd14  ldc.i4.m1
0xd15  stloc.2
0xd16  ldc.i4.0
0xd17  stloc.3
0xd18  ldloc.1
0xd19  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xd1e  ldstr    aDeclareVersion// "DECLARE @versionNumberExpired bigint\r"...
0xd23  ldc.i4.0
0xd24  newarr   [mscorlib]System.Object
0xd29  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xd2e  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0xd33  ldloc.1
0xd34  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0xd39  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0xd3e  dup
0xd3f  callvirt instance void [System.Data]System.Data.Common.DbParameterCollection::Clear()
0xd44  ldstr    aNumofrecordsto// "@numOfRecordsToBeDeleted"
0xd49  ldsfld   int32 Microsoft.Crm.DeletionService::NumOfRecordsToBeDeletedPerExecution
0xd4e  box      [mscorlib]System.Int32
0xd53  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0xd58  pop
0xd59  ldloc.0
0xd5a  ldloc.1
0xd5b  ldarg.0
0xd5c  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.DeletionService::_organizationId
0xd61  ldloca.s 2
0xd63  ldloca.s 3
0xd65  call     int32 Microsoft.Crm.DeletionService::ExecuteTransaction(class [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction transaction, class [System.Data]System.Data.IDbCommand command, valuetype [mscorlib]System.Guid orgId, [out] int32& durationInSecs, [out] bool& completedAllDelete)
0xd6a  stloc.s  4
0xd6c  call     class Microsoft.Crm.Platform.DeletionServiceEventSource Microsoft.Crm.Platform.DeletionServiceEventSource::get_Instance()
0xd71  ldarg.0
0xd72  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.DeletionService::_organizationId
0xd77  ldstr    aCleanupchanget// "CleanUpChangeTrackingTimeStamps"
0xd7c  ldstr    aDeletionservic_9// "DeletionService: Execution of CleanUpCh"...
0xd81  ldloc.s  4
0xd83  ldloc.2
0xd84  ldsfld   bool Microsoft.Crm.DeletionService::AllowVerboseLogging
0xd89  ldsfld   int32 Microsoft.Crm.DeletionService::DeletionServiceDBConnectionTimeoutInSeconds
0xd8e  ldsfld   int32 Microsoft.Crm.DeletionService::DeletionServiceExecutionTimeoutInMinutes
0xd93  ldsfld   int32 Microsoft.Crm.DeletionService::NumOfRecordsToBeDeletedPerExecution
0xd98  ldc.i4.1
0xd99  ldloc.1
0xd9a  callvirt instance string [System.Data]System.Data.IDbCommand::get_CommandText()
0xd9f  callvirt instance void Microsoft.Crm.Platform.DeletionServiceEventSource::DeletionServiceInformation(valuetype [mscorlib]System.Guid organizationId, string moduleName, string message, int32 recordsDeleted, int32 durationInSecs, bool verbose, int32 deletionServiceDBConnectionTimeoutInSeconds, int32 deletionServiceExecutionTimeoutInMinutes, int32 top_numOfRecordsToBeDeleted, bool completedAllDeletes, string sqlText)
0xda4  leave.s  loc_DBA
0xda6  ldloc.1
0xda7  brfalse.s loc_DAF
0xda9  ldloc.1
0xdaa  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xdaf  endfinally
0xdb0  ldloc.0
0xdb1  brfalse.s loc_DB9
0xdb3  ldloc.0
0xdb4  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xdb9  endfinally
0xdba  ret
```
