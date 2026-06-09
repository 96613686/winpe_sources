# Microsoft.Crm.Performance.Instrumentation.PerformanceContext::WriteTraceInfoToDatabase

- ea: `0x3f370`
- end: `0x3f504`
- name: `Microsoft.Crm.Performance.Instrumentation.PerformanceContext::WriteTraceInfoToDatabase`
- size: `404`
- prototype: ``
- caller_count: `0`
- callee_count: `17`
- tags: `registry_config, broker_com_uri`

## callees

- `0xd2f0`
- `0xd5f0`
- `0xdab0`
- `0x1eaa0`
- `0x1f510`
- `0x2dae0`
- `0x3f370`
- `0x3f9f0`
- `0x3fa10`
- `0x3fa30`
- `0x3fa60`
- `0x3fb20`
- `0x3fc50`
- `0x40150`
- `0x40180`
- `0x4d750`
- `0x626d0`

## string_xrefs

- `0x3f37c`: `insert into PerfTrace(Id,Timestamp,Duration,Request,PerfTest, OrganizationId,TraceXml) values(@perfTraceId,@timeStamp,@duration,@request,@perfTest,@orgId,@traceXml)`
- `0x3f482`: `@traceXml`
- `0x3f4a9`: `WriteTraceInfoToDatabase`
- `0x3f4ec`: `Exception in WriteTraceInfoToDatabase: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x3f370  ldarg.0
0x3f371  castclass Microsoft.Crm.Performance.Instrumentation.PerformanceTrace
0x3f376  stloc.0
0x3f377  ldloc.0
0x3f378  brtrue.s loc_3F37B
0x3f37a  ret
0x3f37b  nop
0x3f37c  ldstr    aInsertIntoPerf// "insert into PerfTrace(Id,Timestamp,Dura"...
0x3f381  stloc.1
0x3f382  newobj   instance void Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::.ctor()
0x3f387  stloc.2
0x3f388  ldloc.2
0x3f389  ldc.i4.1
0x3f38a  callvirt instance class Microsoft.Crm.CrmDbConnection Microsoft.Crm.SharedDatabase.DatabaseService::CreateConnection(valuetype Microsoft.Crm.SharedDatabase.ConfigScope scope)
0x3f38f  stloc.3
0x3f390  ldloc.3
0x3f391  callvirt instance void Microsoft.Crm.CrmDbConnection::Open()
0x3f396  ldloc.3
0x3f397  callvirt instance class [System.Data]System.Data.IDbCommand Microsoft.Crm.CrmDbConnection::CreateCommand()
0x3f39c  stloc.s  4
0x3f39e  ldloc.s  4
0x3f3a0  ldloc.1
0x3f3a1  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x3f3a6  ldloc.s  4
0x3f3a8  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x3f3ad  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x3f3b2  ldstr    aPerftraceid// "@perfTraceId"
0x3f3b7  call     valuetype [mscorlib]System.Guid Microsoft.Crm.SequentialGuid::CreateGuid()
0x3f3bc  box      [mscorlib]System.Guid
0x3f3c1  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x3f3c6  pop
0x3f3c7  ldloc.s  4
0x3f3c9  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x3f3ce  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x3f3d3  ldstr    aTimestamp_0// "@timeStamp"
0x3f3d8  ldloc.0
0x3f3d9  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Performance.Instrumentation.PerformanceTrace::get_Timestamp()
0x3f3de  box      [mscorlib]System.DateTime
0x3f3e3  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x3f3e8  pop
0x3f3e9  ldloc.s  4
0x3f3eb  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x3f3f0  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x3f3f5  ldstr    aDuration// "@duration"
0x3f3fa  ldloc.0
0x3f3fb  callvirt instance float32 Microsoft.Crm.Performance.Instrumentation.PerformanceTrace::get_TimeToProcess()
0x3f400  box      [mscorlib]System.Single
0x3f405  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x3f40a  pop
0x3f40b  ldloc.s  4
0x3f40d  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x3f412  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x3f417  ldstr    aRequest_0// "@request"
0x3f41c  ldloc.0
0x3f41d  callvirt instance string Microsoft.Crm.Performance.Instrumentation.PerformanceTrace::get_RequestName()
0x3f422  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x3f427  pop
0x3f428  ldloc.s  4
0x3f42a  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x3f42f  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x3f434  ldstr    aPerftest// "@perfTest"
0x3f439  ldloc.0
0x3f43a  callvirt instance string Microsoft.Crm.Performance.Instrumentation.PerformanceTrace::get_PerformanceTestName()
0x3f43f  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x3f444  pop
0x3f445  ldloc.s  4
0x3f447  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x3f44c  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x3f451  ldstr    aOrgid_2// "@orgId"
0x3f456  ldloc.0
0x3f457  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Performance.Instrumentation.PerformanceTrace::get_OrganizationId()
0x3f45c  box      [mscorlib]System.Guid
0x3f461  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x3f466  pop
0x3f467  newobj   instance void Microsoft.Crm.Performance.Instrumentation.XmlTextDumpProvider::.ctor()
0x3f46c  stloc.s  5
0x3f46e  ldloc.0
0x3f46f  ldloc.s  5
0x3f471  callvirt instance void Microsoft.Crm.Performance.Instrumentation.PerformanceTrace::DumpTrace(class Microsoft.Crm.Performance.Instrumentation.ITraceDumpProvider traceProvider)
0x3f476  ldloc.s  4
0x3f478  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x3f47d  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x3f482  ldstr    aTracexml// "@traceXml"
0x3f487  ldloc.s  5
0x3f489  callvirt instance string Microsoft.Crm.Performance.Instrumentation.XmlTextDumpProvider::get_Content()
0x3f48e  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x3f493  pop
0x3f494  leave.s  loc_3F4A2
0x3f496  ldloc.s  5
0x3f498  brfalse.s loc_3F4A1
0x3f49a  ldloc.s  5
0x3f49c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3f4a1  endfinally
0x3f4a2  ldloc.s  4
0x3f4a4  ldc.i4   0xD3
0x3f4a9  ldstr    aWritetraceinfo// "WriteTraceInfoToDatabase"
0x3f4ae  ldstr    aDA1SSrcPlatfor_24// "D:\\a\\1\\s\\src\\Platform\\Core\\Perfo"...
0x3f4b3  call     int32 Microsoft.Crm.CrmDbConnection::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand command, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0x3f4b8  pop
0x3f4b9  leave.s  loc_3F4C7
0x3f4bb  ldloc.s  4
0x3f4bd  brfalse.s loc_3F4C6
0x3f4bf  ldloc.s  4
0x3f4c1  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3f4c6  endfinally
0x3f4c7  leave.s  loc_3F4D3
0x3f4c9  ldloc.3
0x3f4ca  brfalse.s loc_3F4D2
0x3f4cc  ldloc.3
0x3f4cd  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3f4d2  endfinally
0x3f4d3  leave.s  loc_3F4DF
0x3f4d5  ldloc.2
0x3f4d6  brfalse.s loc_3F4DE
0x3f4d8  ldloc.2
0x3f4d9  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3f4de  endfinally
0x3f4df  leave.s  loc_3F503
0x3f4e1  stloc.s  6
0x3f4e3  ldloc.s  6
0x3f4e5  call     valuetype [mscorlib]System.Guid Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x3f4ea  ldc.i4.s 0x1D
0x3f4ec  ldstr    aExceptionInWri// "Exception in WriteTraceInfoToDatabase: "...
0x3f4f1  ldc.i4.1
0x3f4f2  newarr   [mscorlib]System.Object
0x3f4f7  dup
0x3f4f8  ldc.i4.0
0x3f4f9  ldloc.s  6
0x3f4fb  stelem.ref
0x3f4fc  call     void Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception ex, valuetype [mscorlib]System.Guid orgId, valuetype Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x3f501  leave.s  loc_3F503
0x3f503  ret
```
