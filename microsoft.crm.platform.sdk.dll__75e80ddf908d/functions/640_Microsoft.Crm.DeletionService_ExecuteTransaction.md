# Microsoft.Crm.DeletionService::ExecuteTransaction

- ea: `0x640`
- end: `0x87a`
- name: `Microsoft.Crm.DeletionService::ExecuteTransaction`
- size: `570`
- prototype: ``
- caller_count: `12`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0xcd0`
- `0x1040`
- `0x11e0`
- `0x1470`
- `0x1600`
- `0x19d0`
- `0x1bd0`
- `0x1d40`
- `0x1ea0`
- `0x2080`
- `0x2250`
- `0x2790`

## callees

- `0x640`
- `0xaf40`
- `0xaf50`
- `0xaff0`

## string_xrefs

- `0x678`: `D:\a\1\s\src\ManagedPlatform\SDK\DeletionService\DeletionService.cs`
- `0x6ae`: `DeletionService: {0} rows have been deleted before this error for the command: {1} command timeout: {2}`
- `0x79a`: `DeletionService: Execution time for this command - {0} is {1} minutes > {2} minutes - the max time of any deletion service is allowed `
- `0x7e8`: `DeletionService: Execution time for this command - {0} is {1} minutes > {2} minutes - the max time of any deletion service is allowed `

## pseudocode

```c

```

## disassembly

```asm
0x640  ldarg.3
0x641  ldc.i4.m1
0x642  stind.i4
0x643  ldarg.s  4
0x645  ldc.i4.0
0x646  stind.i1
0x647  ldc.i4.0
0x648  stloc.0
0x649  newobj   instance void [System]System.Diagnostics.Stopwatch::.ctor()
0x64e  stloc.1
0x64f  ldloc.1
0x650  callvirt instance void [System]System.Diagnostics.Stopwatch::Start()
0x655  br       loc_739
0x65a  nop
0x65b  ldarg.0
0x65c  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction::StartTransaction()
0x661  ldarg.1
0x662  ldarg.0
0x663  callvirt instance class [System.Data]System.Data.IDbTransaction [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction::get_SqlTrans()
0x668  callvirt instance void [System.Data]System.Data.IDbCommand::set_Transaction(class [System.Data]System.Data.IDbTransaction)
0x66d  ldarg.1
0x66e  ldc.i4   0xD7
0x673  ldstr    aExecutetransac// "ExecuteTransaction"
0x678  ldstr    aDA1SSrcManaged// "D:\\a\\1\\s\\src\\ManagedPlatform\\SDK"...
0x67d  call     int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand, int32, string, string)
0x682  stloc.2
0x683  ldarg.0
0x684  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction::CommitTransaction()
0x689  ldloc.0
0x68a  ldloc.2
0x68b  add
0x68c  stloc.0
0x68d  ldloc.2
0x68e  ldc.i4.1
0x68f  bge.s    loc_696
0x691  leave    loc_753
0x696  leave    loc_739
0x69b  stloc.3
0x69c  ldloc.1
0x69d  callvirt instance void [System]System.Diagnostics.Stopwatch::Stop()
0x6a2  ldarg.0
0x6a3  ldc.i4.0
0x6a4  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction::RollbackTransaction(bool)
0x6a9  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x6ae  ldstr    aDeletionservic_2// "DeletionService: {0} rows have been del"...
0x6b3  ldc.i4.3
0x6b4  newarr   [mscorlib]System.Object
0x6b9  dup
0x6ba  ldc.i4.0
0x6bb  ldloc.0
0x6bc  box      [mscorlib]System.Int32
0x6c1  stelem.ref
0x6c2  dup
0x6c3  ldc.i4.1
0x6c4  ldarg.1
0x6c5  callvirt instance string [System.Data]System.Data.IDbCommand::get_CommandText()
0x6ca  stelem.ref
0x6cb  dup
0x6cc  ldc.i4.2
0x6cd  ldarg.1
0x6ce  callvirt instance int32 [System.Data]System.Data.IDbCommand::get_CommandTimeout()
0x6d3  box      [mscorlib]System.Int32
0x6d8  stelem.ref
0x6d9  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x6de  ldloc.3
0x6df  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, class [mscorlib]System.Exception)
0x6e4  stloc.s  4
0x6e6  call     class Microsoft.Crm.Platform.DeletionServiceEventSource Microsoft.Crm.Platform.DeletionServiceEventSource::get_Instance()
0x6eb  ldarg.2
0x6ec  ldstr    aExecutetransac// "ExecuteTransaction"
0x6f1  ldsfld   string [mscorlib]System.String::Empty
0x6f6  ldloc.s  4
0x6f8  callvirt instance string [mscorlib]System.Object::ToString()
0x6fd  ldloc.0
0x6fe  ldloc.1
0x6ff  callvirt instance valuetype [mscorlib]System.TimeSpan [System]System.Diagnostics.Stopwatch::get_Elapsed()
0x704  stloc.s  5
0x706  ldloca.s 5
0x708  call     instance float64 [mscorlib]System.TimeSpan::get_TotalSeconds()
0x70d  conv.i4
0x70e  call     string [mscorlib]System.Environment::get_StackTrace()
0x713  ldsfld   bool Microsoft.Crm.DeletionService::AllowVerboseLogging
0x718  ldarg.1
0x719  callvirt instance int32 [System.Data]System.Data.IDbCommand::get_CommandTimeout()
0x71e  ldsfld   int32 Microsoft.Crm.DeletionService::DeletionServiceExecutionTimeoutInMinutes
0x723  ldsfld   int32 Microsoft.Crm.DeletionService::NumOfRecordsToBeDeletedPerExecution
0x728  ldarg.s  4
0x72a  ldind.u1
0x72b  ldarg.1
0x72c  callvirt instance string [System.Data]System.Data.IDbCommand::get_CommandText()
0x731  callvirt instance void Microsoft.Crm.Platform.DeletionServiceEventSource::DeletionServiceError(valuetype [mscorlib]System.Guid organizationId, string moduleName, string crmTraceMessage, string errorMessage, int32 recordsDeleted, int32 durationInSecs, string stackTrace, bool verbose, int32 deletionServiceDBConnectionTimeoutInSeconds, int32 deletionServiceExecutionTimeoutInMinutes, int32 top_numOfRecordsToBeDeleted, bool completedAllDeletes, string sqlText)
0x736  ldloc.s  4
0x738  throw
0x739  ldloc.1
0x73a  callvirt instance valuetype [mscorlib]System.TimeSpan [System]System.Diagnostics.Stopwatch::get_Elapsed()
0x73f  stloc.s  5
0x741  ldloca.s 5
0x743  call     instance float64 [mscorlib]System.TimeSpan::get_TotalMinutes()
0x748  ldsfld   int32 Microsoft.Crm.DeletionService::DeletionServiceExecutionTimeoutInMinutes
0x74d  conv.r8
0x74e  ble      loc_65A
0x753  ldloc.1
0x754  callvirt instance void [System]System.Diagnostics.Stopwatch::Stop()
0x759  ldarg.3
0x75a  ldloc.1
0x75b  callvirt instance valuetype [mscorlib]System.TimeSpan [System]System.Diagnostics.Stopwatch::get_Elapsed()
0x760  stloc.s  5
0x762  ldloca.s 5
0x764  call     instance float64 [mscorlib]System.TimeSpan::get_TotalSeconds()
0x769  conv.i4
0x76a  stind.i4
0x76b  ldloc.1
0x76c  callvirt instance valuetype [mscorlib]System.TimeSpan [System]System.Diagnostics.Stopwatch::get_Elapsed()
0x771  stloc.s  5
0x773  ldloca.s 5
0x775  call     instance float64 [mscorlib]System.TimeSpan::get_TotalMinutes()
0x77a  ldsfld   int32 Microsoft.Crm.DeletionService::DeletionServiceExecutionTimeoutInMinutes
0x77f  conv.r8
0x780  ble.un   loc_83E
0x785  ldarg.2
0x786  ldc.i4.s 0x14
0x788  ldstr    a0// "{0}"
0x78d  ldc.i4.1
0x78e  newarr   [mscorlib]System.Object
0x793  dup
0x794  ldc.i4.0
0x795  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x79a  ldstr    aDeletionservic_3// "DeletionService: Execution time for thi"...
0x79f  ldc.i4.3
0x7a0  newarr   [mscorlib]System.Object
0x7a5  dup
0x7a6  ldc.i4.0
0x7a7  ldarg.1
0x7a8  callvirt instance string [System.Data]System.Data.IDbCommand::get_CommandText()
0x7ad  stelem.ref
0x7ae  dup
0x7af  ldc.i4.1
0x7b0  ldloc.1
0x7b1  callvirt instance valuetype [mscorlib]System.TimeSpan [System]System.Diagnostics.Stopwatch::get_Elapsed()
0x7b6  stloc.s  5
0x7b8  ldloca.s 5
0x7ba  call     instance float64 [mscorlib]System.TimeSpan::get_TotalMinutes()
0x7bf  box      [mscorlib]System.Double
0x7c4  stelem.ref
0x7c5  dup
0x7c6  ldc.i4.2
0x7c7  ldsfld   int32 Microsoft.Crm.DeletionService::DeletionServiceExecutionTimeoutInMinutes
0x7cc  box      [mscorlib]System.Int32
0x7d1  stelem.ref
0x7d2  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x7d7  stelem.ref
0x7d8  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x7dd  call     class Microsoft.Crm.Platform.DeletionServiceEventSource Microsoft.Crm.Platform.DeletionServiceEventSource::get_Instance()
0x7e2  ldarg.2
0x7e3  ldstr    aExecutetransac// "ExecuteTransaction"
0x7e8  ldstr    aDeletionservic_3// "DeletionService: Execution time for thi"...
0x7ed  ldarg.1
0x7ee  callvirt instance string [System.Data]System.Data.IDbCommand::get_CommandText()
0x7f3  ldloc.1
0x7f4  callvirt instance valuetype [mscorlib]System.TimeSpan [System]System.Diagnostics.Stopwatch::get_Elapsed()
0x7f9  stloc.s  5
0x7fb  ldloca.s 5
0x7fd  call     instance float64 [mscorlib]System.TimeSpan::get_TotalMinutes()
0x802  box      [mscorlib]System.Double
0x807  ldsfld   int32 Microsoft.Crm.DeletionService::DeletionServiceExecutionTimeoutInMinutes
0x80c  box      [mscorlib]System.Int32
0x811  call     string [mscorlib]System.String::Format(string, object, object, object)
0x816  ldloc.0
0x817  ldarg.3
0x818  ldind.i4
0x819  ldsfld   bool Microsoft.Crm.DeletionService::AllowVerboseLogging
0x81e  ldarg.1
0x81f  callvirt instance int32 [System.Data]System.Data.IDbCommand::get_CommandTimeout()
0x824  ldsfld   int32 Microsoft.Crm.DeletionService::DeletionServiceExecutionTimeoutInMinutes
0x829  ldsfld   int32 Microsoft.Crm.DeletionService::NumOfRecordsToBeDeletedPerExecution
0x82e  ldarg.s  4
0x830  ldind.u1
0x831  ldarg.1
0x832  callvirt instance string [System.Data]System.Data.IDbCommand::get_CommandText()
0x837  callvirt instance void Microsoft.Crm.Platform.DeletionServiceEventSource::DeletionServiceInformation(valuetype [mscorlib]System.Guid organizationId, string moduleName, string message, int32 recordsDeleted, int32 durationInSecs, bool verbose, int32 deletionServiceDBConnectionTimeoutInSeconds, int32 deletionServiceExecutionTimeoutInMinutes, int32 top_numOfRecordsToBeDeleted, bool completedAllDeletes, string sqlText)
0x83c  br.s     loc_842
0x83e  ldarg.s  4
0x840  ldc.i4.1
0x841  stind.i1
0x842  call     class Microsoft.Crm.Platform.DeletionServiceEventSource Microsoft.Crm.Platform.DeletionServiceEventSource::get_Instance()
0x847  ldarg.2
0x848  ldstr    aExecutetransac// "ExecuteTransaction"
0x84d  ldsfld   string [mscorlib]System.String::Empty
0x852  ldloc.0
0x853  ldarg.3
0x854  ldind.i4
0x855  ldsfld   bool Microsoft.Crm.DeletionService::AllowVerboseLogging
0x85a  ldarg.1
0x85b  callvirt instance int32 [System.Data]System.Data.IDbCommand::get_CommandTimeout()
0x860  ldsfld   int32 Microsoft.Crm.DeletionService::DeletionServiceExecutionTimeoutInMinutes
0x865  ldsfld   int32 Microsoft.Crm.DeletionService::NumOfRecordsToBeDeletedPerExecution
0x86a  ldarg.s  4
0x86c  ldind.u1
0x86d  ldarg.1
0x86e  callvirt instance string [System.Data]System.Data.IDbCommand::get_CommandText()
0x873  callvirt instance void Microsoft.Crm.Platform.DeletionServiceEventSource::DeletionServiceInformation(valuetype [mscorlib]System.Guid organizationId, string moduleName, string message, int32 recordsDeleted, int32 durationInSecs, bool verbose, int32 deletionServiceDBConnectionTimeoutInSeconds, int32 deletionServiceExecutionTimeoutInMinutes, int32 top_numOfRecordsToBeDeleted, bool completedAllDeletes, string sqlText)
0x878  ldloc.0
0x879  ret
```
