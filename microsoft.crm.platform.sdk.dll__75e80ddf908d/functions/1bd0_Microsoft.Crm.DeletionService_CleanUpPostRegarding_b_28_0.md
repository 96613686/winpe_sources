# Microsoft.Crm.DeletionService::<CleanUpPostRegarding>b__28_0

- ea: `0x1bd0`
- end: `0x1d3a`
- name: `Microsoft.Crm.DeletionService::<CleanUpPostRegarding>b__28_0`
- size: `362`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callees

- `0x640`
- `0x1bd0`
- `0xaf40`
- `0xaf50`

## string_xrefs

- `0x1c84`: `@numOfRecordsToBeDeleted`
- `0x1bd8`: `DeletionService: Inside DeletionService.CleanUpPostRegarding`
- `0x1bf8`: `DeletionService: Inside DeletionService.CleanUpPostRegarding`
- `0x1c50`: `delete top(@numOfRecordsToBeDeleted) from PostRegardingBase \nwhere PostRegardingId in\n(\n	select PostRegardingId from PostRegardingBase\n	except\n	select distinct Pr.PostRegardingId\n	from PostRegardingBase PR\n		inner join PostRoleBase PRB on PR.RegardingObjectId = PRB.RegardingObjectId\n			and PR.RegardingObjectTypeCode = PRB.RegardingObjectTypeCode\n)\noption (maxdop {0});`
- `0x1cb4`: `DeletionService: Deletion Service deleted {0} rows in {1} seconds from PostRegardingBase. Completed all Deletes : {2}`
- `0x1cf1`: `DeletionService: Execution of CleanUpPostRegarding is completed.`

## pseudocode

```c

```

## disassembly

```asm
0x1bd0  ldarg.0
0x1bd1  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.DeletionService::_organizationId
0x1bd6  ldc.i4.s 0x14
0x1bd8  ldstr    aDeletionservic_41// "DeletionService: Inside DeletionService"...
0x1bdd  ldc.i4.0
0x1bde  newarr   [mscorlib]System.Object
0x1be3  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1be8  call     class Microsoft.Crm.Platform.DeletionServiceEventSource Microsoft.Crm.Platform.DeletionServiceEventSource::get_Instance()
0x1bed  ldarg.0
0x1bee  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.DeletionService::_organizationId
0x1bf3  ldstr    aCleanuppostreg// "CleanUpPostRegarding"
0x1bf8  ldstr    aDeletionservic_41// "DeletionService: Inside DeletionService"...
0x1bfd  ldc.i4.0
0x1bfe  ldc.i4.0
0x1bff  ldsfld   bool Microsoft.Crm.DeletionService::AllowVerboseLogging
0x1c04  ldsfld   int32 Microsoft.Crm.DeletionService::DeletionServiceDBConnectionTimeoutInSeconds
0x1c09  ldsfld   int32 Microsoft.Crm.DeletionService::DeletionServiceExecutionTimeoutInMinutes
0x1c0e  ldsfld   int32 Microsoft.Crm.DeletionService::NumOfRecordsToBeDeletedPerExecution
0x1c13  ldc.i4.0
0x1c14  ldsfld   string [mscorlib]System.String::Empty
0x1c19  callvirt instance void Microsoft.Crm.Platform.DeletionServiceEventSource::DeletionServiceInformation(valuetype [mscorlib]System.Guid organizationId, string moduleName, string message, int32 recordsDeleted, int32 durationInSecs, bool verbose, int32 deletionServiceDBConnectionTimeoutInSeconds, int32 deletionServiceExecutionTimeoutInMinutes, int32 top_numOfRecordsToBeDeleted, bool completedAllDeletes, string sqlText)
0x1c1e  ldarg.0
0x1c1f  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.DeletionService::_organizationId
0x1c24  ldsfld   int32 Microsoft.Crm.DeletionService::DeletionServiceDBConnectionTimeoutInSeconds
0x1c29  ldc.i4.0
0x1c2a  ldc.i4.0
0x1c2b  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::.ctor(valuetype [mscorlib]System.Guid, int32, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0x1c30  stloc.0
0x1c31  ldloc.0
0x1c32  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Open()
0x1c37  ldloc.0
0x1c38  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand()
0x1c3d  stloc.1
0x1c3e  ldloc.0
0x1c3f  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection)
0x1c44  stloc.2
0x1c45  ldc.i4.m1
0x1c46  stloc.3
0x1c47  ldc.i4.0
0x1c48  stloc.s  4
0x1c4a  ldloc.1
0x1c4b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1c50  ldstr    aDeleteTopNumof_2// "delete top(@numOfRecordsToBeDeleted) fr"...
0x1c55  ldc.i4.1
0x1c56  newarr   [mscorlib]System.Object
0x1c5b  dup
0x1c5c  ldc.i4.0
0x1c5d  ldarg.0
0x1c5e  ldfld    int32 Microsoft.Crm.DeletionService::_maxDop
0x1c63  box      [mscorlib]System.Int32
0x1c68  stelem.ref
0x1c69  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1c6e  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x1c73  ldloc.1
0x1c74  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x1c79  isinst   [System.Data]System.Data.SqlClient.SqlParameterCollection
0x1c7e  dup
0x1c7f  callvirt instance void [System.Data]System.Data.Common.DbParameterCollection::Clear()
0x1c84  ldstr    aNumofrecordsto// "@numOfRecordsToBeDeleted"
0x1c89  ldsfld   int32 Microsoft.Crm.DeletionService::NumOfRecordsToBeDeletedPerExecution
0x1c8e  box      [mscorlib]System.Int32
0x1c93  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x1c98  pop
0x1c99  ldloc.2
0x1c9a  ldloc.1
0x1c9b  ldarg.0
0x1c9c  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.DeletionService::_organizationId
0x1ca1  ldloca.s 3
0x1ca3  ldloca.s 4
0x1ca5  call     int32 Microsoft.Crm.DeletionService::ExecuteTransaction(class [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction transaction, class [System.Data]System.Data.IDbCommand command, valuetype [mscorlib]System.Guid orgId, [out] int32& durationInSecs, [out] bool& completedAllDelete)
0x1caa  stloc.s  5
0x1cac  ldarg.0
0x1cad  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.DeletionService::_organizationId
0x1cb2  ldc.i4.s 0x14
0x1cb4  ldstr    aDeletionservic_42// "DeletionService: Deletion Service delet"...
0x1cb9  ldc.i4.3
0x1cba  newarr   [mscorlib]System.Object
0x1cbf  dup
0x1cc0  ldc.i4.0
0x1cc1  ldloc.s  5
0x1cc3  box      [mscorlib]System.Int32
0x1cc8  stelem.ref
0x1cc9  dup
0x1cca  ldc.i4.1
0x1ccb  ldloc.3
0x1ccc  box      [mscorlib]System.Int32
0x1cd1  stelem.ref
0x1cd2  dup
0x1cd3  ldc.i4.2
0x1cd4  ldloc.s  4
0x1cd6  box      [mscorlib]System.Boolean
0x1cdb  stelem.ref
0x1cdc  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1ce1  call     class Microsoft.Crm.Platform.DeletionServiceEventSource Microsoft.Crm.Platform.DeletionServiceEventSource::get_Instance()
0x1ce6  ldarg.0
0x1ce7  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.DeletionService::_organizationId
0x1cec  ldstr    aCleanuppostreg// "CleanUpPostRegarding"
0x1cf1  ldstr    aDeletionservic_43// "DeletionService: Execution of CleanUpPo"...
0x1cf6  ldloc.s  5
0x1cf8  ldloc.3
0x1cf9  ldsfld   bool Microsoft.Crm.DeletionService::AllowVerboseLogging
0x1cfe  ldsfld   int32 Microsoft.Crm.DeletionService::DeletionServiceDBConnectionTimeoutInSeconds
0x1d03  ldsfld   int32 Microsoft.Crm.DeletionService::DeletionServiceExecutionTimeoutInMinutes
0x1d08  ldsfld   int32 Microsoft.Crm.DeletionService::NumOfRecordsToBeDeletedPerExecution
0x1d0d  ldc.i4.1
0x1d0e  ldloc.1
0x1d0f  callvirt instance string [System.Data]System.Data.IDbCommand::get_CommandText()
0x1d14  callvirt instance void Microsoft.Crm.Platform.DeletionServiceEventSource::DeletionServiceInformation(valuetype [mscorlib]System.Guid organizationId, string moduleName, string message, int32 recordsDeleted, int32 durationInSecs, bool verbose, int32 deletionServiceDBConnectionTimeoutInSeconds, int32 deletionServiceExecutionTimeoutInMinutes, int32 top_numOfRecordsToBeDeleted, bool completedAllDeletes, string sqlText)
0x1d19  leave.s  loc_1D39
0x1d1b  ldloc.2
0x1d1c  brfalse.s loc_1D24
0x1d1e  ldloc.2
0x1d1f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1d24  endfinally
0x1d25  ldloc.1
0x1d26  brfalse.s loc_1D2E
0x1d28  ldloc.1
0x1d29  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1d2e  endfinally
0x1d2f  ldloc.0
0x1d30  brfalse.s loc_1D38
0x1d32  ldloc.0
0x1d33  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1d38  endfinally
0x1d39  ret
```
