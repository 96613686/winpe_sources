# Microsoft.Crm.DeletionService::TrackChangeTrackingTimestamp

- ea: `0xdc0`
- end: `0xeb4`
- name: `Microsoft.Crm.DeletionService::TrackChangeTrackingTimestamp`
- size: `244`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0xb00`

## callees

- `0xdc0`
- `0xaf40`
- `0xaf50`
- `0xaff0`

## string_xrefs

- `0xded`: `D:\a\1\s\src\ManagedPlatform\SDK\DeletionService\DeletionService.cs`
- `0xe05`: `DeletionService: Deletion Service inserted {0} rows into TimeStampDateMapping`
- `0xe2e`: `DeletionService: Deletion Service inserted {0} rows into TimeStampDateMapping`
- `0xe80`: `DeletionService: Deletion Service row insertion failed into table TimeStampDateMapping`

## pseudocode

```c

```

## disassembly

```asm
0xdc0  ldarg.1
0xdc1  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand()
0xdc6  stloc.0
0xdc7  ldloc.0
0xdc8  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xdcd  ldstr    aBeginInsertInt// "BEGIN\r\nINSERT INTO [TimeStampDateMapp"...
0xdd2  ldc.i4.0
0xdd3  newarr   [mscorlib]System.Object
0xdd8  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xddd  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0xde2  ldloc.0
0xde3  ldc.i4   0x316
0xde8  ldstr    aTrackchangetra// "TrackChangeTrackingTimestamp"
0xded  ldstr    aDA1SSrcManaged// "D:\\a\\1\\s\\src\\ManagedPlatform\\SDK"...
0xdf2  call     object [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteScalar(class [System.Data]System.Data.IDbCommand, int32, string, string)
0xdf7  unbox.any [mscorlib]System.Int32
0xdfc  stloc.1
0xdfd  ldarg.0
0xdfe  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.DeletionService::_organizationId
0xe03  ldc.i4.s 0x14
0xe05  ldstr    aDeletionservic_10// "DeletionService: Deletion Service inser"...
0xe0a  ldc.i4.1
0xe0b  newarr   [mscorlib]System.Object
0xe10  dup
0xe11  ldc.i4.0
0xe12  ldloc.1
0xe13  box      [mscorlib]System.Int32
0xe18  stelem.ref
0xe19  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xe1e  call     class Microsoft.Crm.Platform.DeletionServiceEventSource Microsoft.Crm.Platform.DeletionServiceEventSource::get_Instance()
0xe23  ldarg.0
0xe24  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.DeletionService::_organizationId
0xe29  ldstr    aTrackchangetra// "TrackChangeTrackingTimestamp"
0xe2e  ldstr    aDeletionservic_10// "DeletionService: Deletion Service inser"...
0xe33  ldloc.1
0xe34  box      [mscorlib]System.Int32
0xe39  call     string [mscorlib]System.String::Format(string, object)
0xe3e  ldc.i4.0
0xe3f  ldc.i4.m1
0xe40  ldsfld   bool Microsoft.Crm.DeletionService::AllowVerboseLogging
0xe45  ldloc.0
0xe46  callvirt instance int32 [System.Data]System.Data.IDbCommand::get_CommandTimeout()
0xe4b  ldsfld   int32 Microsoft.Crm.DeletionService::DeletionServiceExecutionTimeoutInMinutes
0xe50  ldsfld   int32 Microsoft.Crm.DeletionService::NumOfRecordsToBeDeletedPerExecution
0xe55  ldc.i4.0
0xe56  ldloc.0
0xe57  callvirt instance string [System.Data]System.Data.IDbCommand::get_CommandText()
0xe5c  callvirt instance void Microsoft.Crm.Platform.DeletionServiceEventSource::DeletionServiceInformation(valuetype [mscorlib]System.Guid organizationId, string moduleName, string message, int32 recordsDeleted, int32 durationInSecs, bool verbose, int32 deletionServiceDBConnectionTimeoutInSeconds, int32 deletionServiceExecutionTimeoutInMinutes, int32 top_numOfRecordsToBeDeleted, bool completedAllDeletes, string sqlText)
0xe61  leave.s  loc_E6D
0xe63  ldloc.0
0xe64  brfalse.s loc_E6C
0xe66  ldloc.0
0xe67  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xe6c  endfinally
0xe6d  leave.s  loc_EB3
0xe6f  stloc.2
0xe70  call     class Microsoft.Crm.Platform.DeletionServiceEventSource Microsoft.Crm.Platform.DeletionServiceEventSource::get_Instance()
0xe75  ldarg.0
0xe76  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.DeletionService::_organizationId
0xe7b  ldstr    aIschangetracki// "IsChangeTrackingEnabledForAnyEntity"
0xe80  ldstr    aDeletionservic_11// "DeletionService: Deletion Service row i"...
0xe85  ldloc.2
0xe86  callvirt instance string [mscorlib]System.Exception::get_Message()
0xe8b  ldc.i4.0
0xe8c  ldc.i4.m1
0xe8d  call     string [mscorlib]System.Environment::get_StackTrace()
0xe92  ldsfld   bool Microsoft.Crm.DeletionService::AllowVerboseLogging
0xe97  ldsfld   int32 Microsoft.Crm.DeletionService::DeletionServiceDBConnectionTimeoutInSeconds
0xe9c  ldsfld   int32 Microsoft.Crm.DeletionService::DeletionServiceExecutionTimeoutInMinutes
0xea1  ldsfld   int32 Microsoft.Crm.DeletionService::NumOfRecordsToBeDeletedPerExecution
0xea6  ldc.i4.0
0xea7  ldsfld   string [mscorlib]System.String::Empty
0xeac  callvirt instance void Microsoft.Crm.Platform.DeletionServiceEventSource::DeletionServiceError(valuetype [mscorlib]System.Guid organizationId, string moduleName, string crmTraceMessage, string errorMessage, int32 recordsDeleted, int32 durationInSecs, string stackTrace, bool verbose, int32 deletionServiceDBConnectionTimeoutInSeconds, int32 deletionServiceExecutionTimeoutInMinutes, int32 top_numOfRecordsToBeDeleted, bool completedAllDeletes, string sqlText)
0xeb1  rethrow
0xeb3  ret
```
