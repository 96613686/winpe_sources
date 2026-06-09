# Microsoft.Crm.DeletionService::<CleanUpTraceRegarding>b__29_0

- ea: `0x1d40`
- end: `0x1e9c`
- name: `Microsoft.Crm.DeletionService::<CleanUpTraceRegarding>b__29_0`
- size: `348`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callees

- `0x640`
- `0x1d40`
- `0xaf40`
- `0xaf50`

## string_xrefs

- `0x1de6`: `@numOfRecordsToBeDeleted`
- `0x1d48`: `DeletionService: Inside DeletionService.CleanUpTraceRegarding`
- `0x1d68`: `DeletionService: Inside DeletionService.CleanUpTraceRegarding`
- `0x1dc0`: `DELETE TOP(@numOfRecordsToBeDeleted) TraceRegardingBase \n	FROM TraceRegardingBase trb\n	LEFT JOIN TraceLogBase tlb on tlb.TraceRegardingId = trb.TraceRegardingId\n	WHERE tlb.TraceRegardingId is null`
- `0x1e16`: `DeletionService: Deletion Service deleted {0} rows in {1} seconds from TraceRegardingBase. Completed all Deletes : {2}`
- `0x1e53`: `DeletionService: Execution of TraceRegardingBase is completed.`

## pseudocode

```c

```

## disassembly

```asm
0x1d40  ldarg.0
0x1d41  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.DeletionService::_organizationId
0x1d46  ldc.i4.s 0x14
0x1d48  ldstr    aDeletionservic_44// "DeletionService: Inside DeletionService"...
0x1d4d  ldc.i4.0
0x1d4e  newarr   [mscorlib]System.Object
0x1d53  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1d58  call     class Microsoft.Crm.Platform.DeletionServiceEventSource Microsoft.Crm.Platform.DeletionServiceEventSource::get_Instance()
0x1d5d  ldarg.0
0x1d5e  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.DeletionService::_organizationId
0x1d63  ldstr    aCleanuptracere// "CleanUpTraceRegarding"
0x1d68  ldstr    aDeletionservic_44// "DeletionService: Inside DeletionService"...
0x1d6d  ldc.i4.0
0x1d6e  ldc.i4.0
0x1d6f  ldsfld   bool Microsoft.Crm.DeletionService::AllowVerboseLogging
0x1d74  ldsfld   int32 Microsoft.Crm.DeletionService::DeletionServiceDBConnectionTimeoutInSeconds
0x1d79  ldsfld   int32 Microsoft.Crm.DeletionService::DeletionServiceExecutionTimeoutInMinutes
0x1d7e  ldsfld   int32 Microsoft.Crm.DeletionService::NumOfRecordsToBeDeletedPerExecution
0x1d83  ldc.i4.0
0x1d84  ldsfld   string [mscorlib]System.String::Empty
0x1d89  callvirt instance void Microsoft.Crm.Platform.DeletionServiceEventSource::DeletionServiceInformation(valuetype [mscorlib]System.Guid organizationId, string moduleName, string message, int32 recordsDeleted, int32 durationInSecs, bool verbose, int32 deletionServiceDBConnectionTimeoutInSeconds, int32 deletionServiceExecutionTimeoutInMinutes, int32 top_numOfRecordsToBeDeleted, bool completedAllDeletes, string sqlText)
0x1d8e  ldarg.0
0x1d8f  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.DeletionService::_organizationId
0x1d94  ldsfld   int32 Microsoft.Crm.DeletionService::DeletionServiceDBConnectionTimeoutInSeconds
0x1d99  ldc.i4.0
0x1d9a  ldc.i4.0
0x1d9b  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::.ctor(valuetype [mscorlib]System.Guid, int32, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0x1da0  stloc.0
0x1da1  ldloc.0
0x1da2  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Open()
0x1da7  ldloc.0
0x1da8  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection)
0x1dad  stloc.1
0x1dae  ldloc.0
0x1daf  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand()
0x1db4  stloc.2
0x1db5  ldc.i4.m1
0x1db6  stloc.3
0x1db7  ldc.i4.0
0x1db8  stloc.s  4
0x1dba  ldloc.2
0x1dbb  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1dc0  ldstr    aDeleteTopNumof_3// "DELETE TOP(@numOfRecordsToBeDeleted) Tr"...
0x1dc5  ldc.i4.0
0x1dc6  newarr   [mscorlib]System.Object
0x1dcb  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1dd0  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x1dd5  ldloc.2
0x1dd6  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x1ddb  isinst   [System.Data]System.Data.SqlClient.SqlParameterCollection
0x1de0  dup
0x1de1  callvirt instance void [System.Data]System.Data.Common.DbParameterCollection::Clear()
0x1de6  ldstr    aNumofrecordsto// "@numOfRecordsToBeDeleted"
0x1deb  ldsfld   int32 Microsoft.Crm.DeletionService::NumOfRecordsToBeDeletedPerExecution
0x1df0  box      [mscorlib]System.Int32
0x1df5  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x1dfa  pop
0x1dfb  ldloc.1
0x1dfc  ldloc.2
0x1dfd  ldarg.0
0x1dfe  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.DeletionService::_organizationId
0x1e03  ldloca.s 3
0x1e05  ldloca.s 4
0x1e07  call     int32 Microsoft.Crm.DeletionService::ExecuteTransaction(class [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction transaction, class [System.Data]System.Data.IDbCommand command, valuetype [mscorlib]System.Guid orgId, [out] int32& durationInSecs, [out] bool& completedAllDelete)
0x1e0c  stloc.s  5
0x1e0e  ldarg.0
0x1e0f  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.DeletionService::_organizationId
0x1e14  ldc.i4.s 0x14
0x1e16  ldstr    aDeletionservic_45// "DeletionService: Deletion Service delet"...
0x1e1b  ldc.i4.3
0x1e1c  newarr   [mscorlib]System.Object
0x1e21  dup
0x1e22  ldc.i4.0
0x1e23  ldloc.s  5
0x1e25  box      [mscorlib]System.Int32
0x1e2a  stelem.ref
0x1e2b  dup
0x1e2c  ldc.i4.1
0x1e2d  ldloc.3
0x1e2e  box      [mscorlib]System.Int32
0x1e33  stelem.ref
0x1e34  dup
0x1e35  ldc.i4.2
0x1e36  ldloc.s  4
0x1e38  box      [mscorlib]System.Boolean
0x1e3d  stelem.ref
0x1e3e  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1e43  call     class Microsoft.Crm.Platform.DeletionServiceEventSource Microsoft.Crm.Platform.DeletionServiceEventSource::get_Instance()
0x1e48  ldarg.0
0x1e49  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.DeletionService::_organizationId
0x1e4e  ldstr    aTraceregarding// "TraceRegardingBase"
0x1e53  ldstr    aDeletionservic_46// "DeletionService: Execution of TraceRega"...
0x1e58  ldloc.s  5
0x1e5a  ldloc.3
0x1e5b  ldsfld   bool Microsoft.Crm.DeletionService::AllowVerboseLogging
0x1e60  ldsfld   int32 Microsoft.Crm.DeletionService::DeletionServiceDBConnectionTimeoutInSeconds
0x1e65  ldsfld   int32 Microsoft.Crm.DeletionService::DeletionServiceExecutionTimeoutInMinutes
0x1e6a  ldsfld   int32 Microsoft.Crm.DeletionService::NumOfRecordsToBeDeletedPerExecution
0x1e6f  ldc.i4.1
0x1e70  ldloc.2
0x1e71  callvirt instance string [System.Data]System.Data.IDbCommand::get_CommandText()
0x1e76  callvirt instance void Microsoft.Crm.Platform.DeletionServiceEventSource::DeletionServiceInformation(valuetype [mscorlib]System.Guid organizationId, string moduleName, string message, int32 recordsDeleted, int32 durationInSecs, bool verbose, int32 deletionServiceDBConnectionTimeoutInSeconds, int32 deletionServiceExecutionTimeoutInMinutes, int32 top_numOfRecordsToBeDeleted, bool completedAllDeletes, string sqlText)
0x1e7b  leave.s  loc_1E9B
0x1e7d  ldloc.2
0x1e7e  brfalse.s loc_1E86
0x1e80  ldloc.2
0x1e81  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1e86  endfinally
0x1e87  ldloc.1
0x1e88  brfalse.s loc_1E90
0x1e8a  ldloc.1
0x1e8b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1e90  endfinally
0x1e91  ldloc.0
0x1e92  brfalse.s loc_1E9A
0x1e94  ldloc.0
0x1e95  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1e9a  endfinally
0x1e9b  ret
```
