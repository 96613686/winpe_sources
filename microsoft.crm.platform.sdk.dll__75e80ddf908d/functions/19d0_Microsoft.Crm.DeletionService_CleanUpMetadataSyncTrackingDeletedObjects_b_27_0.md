# Microsoft.Crm.DeletionService::<CleanUpMetadataSyncTrackingDeletedObjects>b__27_0

- ea: `0x19d0`
- end: `0x1bc5`
- name: `Microsoft.Crm.DeletionService::<CleanUpMetadataSyncTrackingDeletedObjects>b__27_0`
- size: `501`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, service_task, installer_update, broker_com_uri`

## callees

- `0x640`
- `0x19d0`
- `0xaf40`
- `0xaf50`
- `0xaff0`

## string_xrefs

- `0x1b59`: `D:\a\1\s\src\ManagedPlatform\SDK\DeletionService\DeletionService.cs`
- `0x1a72`: `@numOfRecordsToBeDeleted`
- `0x19d8`: `DeletionService: Inside DeletionService.CleanUpMetadataSyncTrackingDeletedObjects`
- `0x19f8`: `DeletionService: Inside DeletionService.CleanUpMetadataSyncTrackingDeletedObjects`
- `0x19f3`: `CleanUpMetadataSyncTrackingDeletedObjects`
- `0x1ae2`: `CleanUpMetadataSyncTrackingDeletedObjects`
- `0x1b54`: `CleanUpMetadataSyncTrackingDeletedObjects`
- `0x1b73`: `CleanUpMetadataSyncTrackingDeletedObjects`
- `0x1a4f`: `DECLARE @expireSubscriptionInDays int\nSELECT @expireSubscriptionInDays = ExpireSubscriptionsInDays FROM Organization\nDELETE TOP(@numOfRecordsToBeDeleted) FROM [MetadataSyncTrackingDeletedObject] WHERE CreatedOn < dateadd(dd, -@expireSubscriptionInDays, getutcdate())`
- `0x1aaa`: `DeletionService: Deletion Service deleted {0} rows in {1} seconds from MetadataSyncTrackingDeletedObject. Completed all Deletes : {2}`
- `0x1ae7`: `DeletionService: Execution of CleanUpMetadataSyncTrackingDeletedObjects is completed.`
- `0x1b32`: `DECLARE @expireSubscriptionInDays int\nSELECT @expireSubscriptionInDays = ExpireSubscriptionsInDays FROM Organization\nUPDATE OrganizationBase \n	SET MetadataSyncLastTimeOfNeverExpiredDeletedObjects = null\n	WHERE MetadataSyncLastTimeOfNeverExpiredDeletedObjects is not null AND MetadataSyncLastTimeOfNeverExpiredDeletedObjects <= DATEADD(dd, -@expireSubscriptionInDays, getutcdate())`
- `0x1b78`: `DeletionService:Exception occured while updating OrganizationBase `

## pseudocode

```c

```

## disassembly

```asm
0x19d0  ldarg.0
0x19d1  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.DeletionService::_organizationId
0x19d6  ldc.i4.s 0x14
0x19d8  ldstr    aDeletionservic_37// "DeletionService: Inside DeletionService"...
0x19dd  ldc.i4.0
0x19de  newarr   [mscorlib]System.Object
0x19e3  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x19e8  call     class Microsoft.Crm.Platform.DeletionServiceEventSource Microsoft.Crm.Platform.DeletionServiceEventSource::get_Instance()
0x19ed  ldarg.0
0x19ee  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.DeletionService::_organizationId
0x19f3  ldstr    aCleanupmetadat_0// "CleanUpMetadataSyncTrackingDeletedObjec"...
0x19f8  ldstr    aDeletionservic_37// "DeletionService: Inside DeletionService"...
0x19fd  ldc.i4.0
0x19fe  ldc.i4.0
0x19ff  ldsfld   bool Microsoft.Crm.DeletionService::AllowVerboseLogging
0x1a04  ldsfld   int32 Microsoft.Crm.DeletionService::DeletionServiceDBConnectionTimeoutInSeconds
0x1a09  ldsfld   int32 Microsoft.Crm.DeletionService::DeletionServiceExecutionTimeoutInMinutes
0x1a0e  ldsfld   int32 Microsoft.Crm.DeletionService::NumOfRecordsToBeDeletedPerExecution
0x1a13  ldc.i4.0
0x1a14  ldsfld   string [mscorlib]System.String::Empty
0x1a19  callvirt instance void Microsoft.Crm.Platform.DeletionServiceEventSource::DeletionServiceInformation(valuetype [mscorlib]System.Guid organizationId, string moduleName, string message, int32 recordsDeleted, int32 durationInSecs, bool verbose, int32 deletionServiceDBConnectionTimeoutInSeconds, int32 deletionServiceExecutionTimeoutInMinutes, int32 top_numOfRecordsToBeDeleted, bool completedAllDeletes, string sqlText)
0x1a1e  ldarg.0
0x1a1f  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.DeletionService::_organizationId
0x1a24  ldsfld   int32 Microsoft.Crm.DeletionService::DeletionServiceDBConnectionTimeoutInSeconds
0x1a29  ldc.i4.0
0x1a2a  ldc.i4.0
0x1a2b  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::.ctor(valuetype [mscorlib]System.Guid, int32, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0x1a30  stloc.0
0x1a31  ldloc.0
0x1a32  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Open()
0x1a37  ldloc.0
0x1a38  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection)
0x1a3d  stloc.1
0x1a3e  ldloc.0
0x1a3f  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand()
0x1a44  stloc.2
0x1a45  ldc.i4.m1
0x1a46  stloc.3
0x1a47  ldc.i4.0
0x1a48  stloc.s  4
0x1a4a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1a4f  ldstr    aDeclareExpires// "DECLARE @expireSubscriptionInDays int\r"...
0x1a54  ldc.i4.0
0x1a55  newarr   [mscorlib]System.Object
0x1a5a  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1a5f  stloc.s  5
0x1a61  ldloc.2
0x1a62  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x1a67  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x1a6c  dup
0x1a6d  callvirt instance void [System.Data]System.Data.Common.DbParameterCollection::Clear()
0x1a72  ldstr    aNumofrecordsto// "@numOfRecordsToBeDeleted"
0x1a77  ldsfld   int32 Microsoft.Crm.DeletionService::NumOfRecordsToBeDeletedPerExecution
0x1a7c  box      [mscorlib]System.Int32
0x1a81  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x1a86  pop
0x1a87  ldloc.2
0x1a88  ldloc.s  5
0x1a8a  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x1a8f  ldloc.1
0x1a90  ldloc.2
0x1a91  ldarg.0
0x1a92  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.DeletionService::_organizationId
0x1a97  ldloca.s 3
0x1a99  ldloca.s 4
0x1a9b  call     int32 Microsoft.Crm.DeletionService::ExecuteTransaction(class [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction transaction, class [System.Data]System.Data.IDbCommand command, valuetype [mscorlib]System.Guid orgId, [out] int32& durationInSecs, [out] bool& completedAllDelete)
0x1aa0  stloc.s  6
0x1aa2  ldarg.0
0x1aa3  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.DeletionService::_organizationId
0x1aa8  ldc.i4.s 0x14
0x1aaa  ldstr    aDeletionservic_38// "DeletionService: Deletion Service delet"...
0x1aaf  ldc.i4.3
0x1ab0  newarr   [mscorlib]System.Object
0x1ab5  dup
0x1ab6  ldc.i4.0
0x1ab7  ldloc.s  6
0x1ab9  box      [mscorlib]System.Int32
0x1abe  stelem.ref
0x1abf  dup
0x1ac0  ldc.i4.1
0x1ac1  ldloc.3
0x1ac2  box      [mscorlib]System.Int32
0x1ac7  stelem.ref
0x1ac8  dup
0x1ac9  ldc.i4.2
0x1aca  ldloc.s  4
0x1acc  box      [mscorlib]System.Boolean
0x1ad1  stelem.ref
0x1ad2  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1ad7  call     class Microsoft.Crm.Platform.DeletionServiceEventSource Microsoft.Crm.Platform.DeletionServiceEventSource::get_Instance()
0x1adc  ldarg.0
0x1add  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.DeletionService::_organizationId
0x1ae2  ldstr    aCleanupmetadat_0// "CleanUpMetadataSyncTrackingDeletedObjec"...
0x1ae7  ldstr    aDeletionservic_39// "DeletionService: Execution of CleanUpMe"...
0x1aec  ldloc.s  6
0x1aee  ldloc.3
0x1aef  ldsfld   bool Microsoft.Crm.DeletionService::AllowVerboseLogging
0x1af4  ldsfld   int32 Microsoft.Crm.DeletionService::DeletionServiceDBConnectionTimeoutInSeconds
0x1af9  ldsfld   int32 Microsoft.Crm.DeletionService::DeletionServiceExecutionTimeoutInMinutes
0x1afe  ldsfld   int32 Microsoft.Crm.DeletionService::NumOfRecordsToBeDeletedPerExecution
0x1b03  ldc.i4.1
0x1b04  ldloc.2
0x1b05  callvirt instance string [System.Data]System.Data.IDbCommand::get_CommandText()
0x1b0a  callvirt instance void Microsoft.Crm.Platform.DeletionServiceEventSource::DeletionServiceInformation(valuetype [mscorlib]System.Guid organizationId, string moduleName, string message, int32 recordsDeleted, int32 durationInSecs, bool verbose, int32 deletionServiceDBConnectionTimeoutInSeconds, int32 deletionServiceExecutionTimeoutInMinutes, int32 top_numOfRecordsToBeDeleted, bool completedAllDeletes, string sqlText)
0x1b0f  leave.s  loc_1B25
0x1b11  ldloc.2
0x1b12  brfalse.s loc_1B1A
0x1b14  ldloc.2
0x1b15  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1b1a  endfinally
0x1b1b  ldloc.1
0x1b1c  brfalse.s loc_1B24
0x1b1e  ldloc.1
0x1b1f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1b24  endfinally
0x1b25  ldloc.0
0x1b26  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand()
0x1b2b  stloc.s  7
0x1b2d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1b32  ldstr    aDeclareExpires_0// "DECLARE @expireSubscriptionInDays int\r"...
0x1b37  ldc.i4.0
0x1b38  newarr   [mscorlib]System.Object
0x1b3d  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1b42  stloc.s  8
0x1b44  ldloc.s  7
0x1b46  ldloc.s  8
0x1b48  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x1b4d  ldloc.s  7
0x1b4f  ldc.i4   0x3BC
0x1b54  ldstr    aCleanupmetadat_0// "CleanUpMetadataSyncTrackingDeletedObjec"...
0x1b59  ldstr    aDA1SSrcManaged// "D:\\a\\1\\s\\src\\ManagedPlatform\\SDK"...
0x1b5e  call     int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand, int32, string, string)
0x1b63  pop
0x1b64  leave.s  loc_1BC4
0x1b66  stloc.s  9
0x1b68  call     class Microsoft.Crm.Platform.DeletionServiceEventSource Microsoft.Crm.Platform.DeletionServiceEventSource::get_Instance()
0x1b6d  ldarg.0
0x1b6e  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.DeletionService::_organizationId
0x1b73  ldstr    aCleanupmetadat_0// "CleanUpMetadataSyncTrackingDeletedObjec"...
0x1b78  ldstr    aDeletionservic_40// "DeletionService:Exception occured while"...
0x1b7d  ldloc.s  9
0x1b7f  callvirt instance string [mscorlib]System.Exception::get_Message()
0x1b84  ldc.i4.0
0x1b85  ldc.i4.m1
0x1b86  call     string [mscorlib]System.Environment::get_StackTrace()
0x1b8b  ldsfld   bool Microsoft.Crm.DeletionService::AllowVerboseLogging
0x1b90  ldsfld   int32 Microsoft.Crm.DeletionService::DeletionServiceDBConnectionTimeoutInSeconds
0x1b95  ldsfld   int32 Microsoft.Crm.DeletionService::DeletionServiceExecutionTimeoutInMinutes
0x1b9a  ldsfld   int32 Microsoft.Crm.DeletionService::NumOfRecordsToBeDeletedPerExecution
0x1b9f  ldc.i4.0
0x1ba0  ldloc.s  7
0x1ba2  callvirt instance string [System.Data]System.Data.IDbCommand::get_CommandText()
0x1ba7  callvirt instance void Microsoft.Crm.Platform.DeletionServiceEventSource::DeletionServiceError(valuetype [mscorlib]System.Guid organizationId, string moduleName, string crmTraceMessage, string errorMessage, int32 recordsDeleted, int32 durationInSecs, string stackTrace, bool verbose, int32 deletionServiceDBConnectionTimeoutInSeconds, int32 deletionServiceExecutionTimeoutInMinutes, int32 top_numOfRecordsToBeDeleted, bool completedAllDeletes, string sqlText)
0x1bac  rethrow
0x1bae  ldloc.s  7
0x1bb0  brfalse.s loc_1BB9
0x1bb2  ldloc.s  7
0x1bb4  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1bb9  endfinally
0x1bba  ldloc.0
0x1bbb  brfalse.s loc_1BC3
0x1bbd  ldloc.0
0x1bbe  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1bc3  endfinally
0x1bc4  ret
```
