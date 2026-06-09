# Microsoft.Crm.DeletionService::<CleanUpOrphanedAttachments>b__14_0

- ea: `0x1040`
- end: `0x11dd`
- name: `Microsoft.Crm.DeletionService::<CleanUpOrphanedAttachments>b__14_0`
- size: `413`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callees

- `0x2e0`
- `0x640`
- `0x1040`
- `0xaf40`
- `0xaf50`

## string_xrefs

- `0x10ff`: `@numOfRecordsToBeDeleted`
- `0x1048`: `DeletionService: Inside DeletionService.CleanUpOrphanedAttachments`
- `0x1068`: `DeletionService: Inside DeletionService.CleanUpOrphanedAttachments`
- `0x10c6`: `delete top(@numOfRecordsToBeDeleted) from Attachment where AttachmentId not in (select AttachmentId from ActivityMimeAttachment)\noption (maxdop {0});`
- `0x1136`: `DeletionService: Deletion Service deleted {0} rows in {1} seconds from Attachment. Completed all Deletes : {2}`
- `0x1174`: `DeletionService: Execution of CleanUpOrphanedAttachments is completed.`
- `0x11b4`: `DeletionService: Error cleaning up Orphaned attachment records from Attachments table`

## pseudocode

```c

```

## disassembly

```asm
0x1040  ldarg.0
0x1041  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.DeletionService::_organizationId
0x1046  ldc.i4.s 0x14
0x1048  ldstr    aDeletionservic_15// "DeletionService: Inside DeletionService"...
0x104d  ldc.i4.0
0x104e  newarr   [mscorlib]System.Object
0x1053  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1058  call     class Microsoft.Crm.Platform.DeletionServiceEventSource Microsoft.Crm.Platform.DeletionServiceEventSource::get_Instance()
0x105d  ldarg.0
0x105e  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.DeletionService::_organizationId
0x1063  ldstr    aCleanuporphane// "CleanUpOrphanedAttachments"
0x1068  ldstr    aDeletionservic_15// "DeletionService: Inside DeletionService"...
0x106d  ldc.i4.0
0x106e  ldc.i4.0
0x106f  ldsfld   bool Microsoft.Crm.DeletionService::AllowVerboseLogging
0x1074  ldsfld   int32 Microsoft.Crm.DeletionService::DeletionServiceDBConnectionTimeoutInSeconds
0x1079  ldsfld   int32 Microsoft.Crm.DeletionService::DeletionServiceExecutionTimeoutInMinutes
0x107e  ldsfld   int32 Microsoft.Crm.DeletionService::NumOfRecordsToBeDeletedPerExecution
0x1083  ldc.i4.0
0x1084  ldsfld   string [mscorlib]System.String::Empty
0x1089  callvirt instance void Microsoft.Crm.Platform.DeletionServiceEventSource::DeletionServiceInformation(valuetype [mscorlib]System.Guid organizationId, string moduleName, string message, int32 recordsDeleted, int32 durationInSecs, bool verbose, int32 deletionServiceDBConnectionTimeoutInSeconds, int32 deletionServiceExecutionTimeoutInMinutes, int32 top_numOfRecordsToBeDeleted, bool completedAllDeletes, string sqlText)
0x108e  ldarg.0
0x108f  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.DeletionService::_organizationId
0x1094  ldsfld   int32 Microsoft.Crm.DeletionService::DeletionServiceDBConnectionTimeoutInSeconds
0x1099  ldc.i4.0
0x109a  ldc.i4.0
0x109b  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::.ctor(valuetype [mscorlib]System.Guid, int32, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0x10a0  stloc.0
0x10a1  ldloc.0
0x10a2  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Open()
0x10a7  ldloc.0
0x10a8  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection)
0x10ad  stloc.1
0x10ae  ldsfld   string [mscorlib]System.String::Empty
0x10b3  stloc.2
0x10b4  ldloc.0
0x10b5  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand()
0x10ba  stloc.3
0x10bb  ldc.i4.m1
0x10bc  stloc.s  4
0x10be  ldc.i4.0
0x10bf  stloc.s  5
0x10c1  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x10c6  ldstr    aDeleteTopNumof// "delete top(@numOfRecordsToBeDeleted) fr"...
0x10cb  ldc.i4.1
0x10cc  newarr   [mscorlib]System.Object
0x10d1  dup
0x10d2  ldc.i4.0
0x10d3  ldarg.0
0x10d4  ldfld    int32 Microsoft.Crm.DeletionService::_maxDop
0x10d9  box      [mscorlib]System.Int32
0x10de  stelem.ref
0x10df  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x10e4  stloc.s  6
0x10e6  ldloc.3
0x10e7  ldloc.s  6
0x10e9  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x10ee  ldloc.3
0x10ef  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x10f4  isinst   [System.Data]System.Data.SqlClient.SqlParameterCollection
0x10f9  dup
0x10fa  callvirt instance void [System.Data]System.Data.Common.DbParameterCollection::Clear()
0x10ff  ldstr    aNumofrecordsto// "@numOfRecordsToBeDeleted"
0x1104  ldsfld   int32 Microsoft.Crm.DeletionService::NumOfRecordsToBeDeletedPerExecution
0x1109  box      [mscorlib]System.Int32
0x110e  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x1113  pop
0x1114  ldloc.3
0x1115  callvirt instance string [System.Data]System.Data.IDbCommand::get_CommandText()
0x111a  stloc.2
0x111b  ldloc.1
0x111c  ldloc.3
0x111d  ldarg.0
0x111e  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.DeletionService::_organizationId
0x1123  ldloca.s 4
0x1125  ldloca.s 5
0x1127  call     int32 Microsoft.Crm.DeletionService::ExecuteTransaction(class [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction transaction, class [System.Data]System.Data.IDbCommand command, valuetype [mscorlib]System.Guid orgId, [out] int32& durationInSecs, [out] bool& completedAllDelete)
0x112c  stloc.s  7
0x112e  ldarg.0
0x112f  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.DeletionService::_organizationId
0x1134  ldc.i4.s 0x14
0x1136  ldstr    aDeletionservic_16// "DeletionService: Deletion Service delet"...
0x113b  ldc.i4.3
0x113c  newarr   [mscorlib]System.Object
0x1141  dup
0x1142  ldc.i4.0
0x1143  ldloc.s  7
0x1145  box      [mscorlib]System.Int32
0x114a  stelem.ref
0x114b  dup
0x114c  ldc.i4.1
0x114d  ldloc.s  4
0x114f  box      [mscorlib]System.Int32
0x1154  stelem.ref
0x1155  dup
0x1156  ldc.i4.2
0x1157  ldloc.s  5
0x1159  box      [mscorlib]System.Boolean
0x115e  stelem.ref
0x115f  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1164  call     class Microsoft.Crm.Platform.DeletionServiceEventSource Microsoft.Crm.Platform.DeletionServiceEventSource::get_Instance()
0x1169  ldarg.0
0x116a  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.DeletionService::_organizationId
0x116f  ldstr    aCleanuporphane// "CleanUpOrphanedAttachments"
0x1174  ldstr    aDeletionservic_17// "DeletionService: Execution of CleanUpOr"...
0x1179  ldloc.s  7
0x117b  ldloc.s  4
0x117d  ldsfld   bool Microsoft.Crm.DeletionService::AllowVerboseLogging
0x1182  ldsfld   int32 Microsoft.Crm.DeletionService::DeletionServiceDBConnectionTimeoutInSeconds
0x1187  ldsfld   int32 Microsoft.Crm.DeletionService::DeletionServiceExecutionTimeoutInMinutes
0x118c  ldsfld   int32 Microsoft.Crm.DeletionService::NumOfRecordsToBeDeletedPerExecution
0x1191  ldc.i4.1
0x1192  ldloc.3
0x1193  callvirt instance string [System.Data]System.Data.IDbCommand::get_CommandText()
0x1198  callvirt instance void Microsoft.Crm.Platform.DeletionServiceEventSource::DeletionServiceInformation(valuetype [mscorlib]System.Guid organizationId, string moduleName, string message, int32 recordsDeleted, int32 durationInSecs, bool verbose, int32 deletionServiceDBConnectionTimeoutInSeconds, int32 deletionServiceExecutionTimeoutInMinutes, int32 top_numOfRecordsToBeDeleted, bool completedAllDeletes, string sqlText)
0x119d  leave.s  loc_11A9
0x119f  ldloc.3
0x11a0  brfalse.s loc_11A8
0x11a2  ldloc.3
0x11a3  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x11a8  endfinally
0x11a9  leave.s  loc_11DC
0x11ab  stloc.s  8
0x11ad  ldarg.0
0x11ae  ldc.i4   0x80004003
0x11b3  conv.u8
0x11b4  ldstr    aDeletionservic_18// "DeletionService: Error cleaning up Orph"...
0x11b9  ldloc.s  8
0x11bb  callvirt instance string [mscorlib]System.Object::ToString()
0x11c0  ldloc.2
0x11c1  call     instance void Microsoft.Crm.DeletionService::LogCrmTraceAndEventLog(int64 logId, string crmTraceMessage, string errorMessage, string sqlText)
0x11c6  rethrow
0x11c8  ldloc.1
0x11c9  brfalse.s loc_11D1
0x11cb  ldloc.1
0x11cc  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x11d1  endfinally
0x11d2  ldloc.0
0x11d3  brfalse.s loc_11DB
0x11d5  ldloc.0
0x11d6  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x11db  endfinally
0x11dc  ret
```
