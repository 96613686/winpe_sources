# Microsoft.Crm.SQLLogger::Log

- ea: `0x2dba0`
- end: `0x2dcc7`
- name: `Microsoft.Crm.SQLLogger::Log`
- size: `295`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x5af20`

## callees

- `0x1eaa0`
- `0x1f510`
- `0x2db80`
- `0x2dba0`
- `0x34790`

## string_xrefs

- `0x2dbaa`: `configdb`
- `0x2dbc5`: `	IF NOT EXISTS(SELECT * FROM Sys.Objects where Name = 'DebugSqlTrace')\n									BEGIN\n										CREATE TABLE DebugSqlTrace (Id uniqueidentifier, DatabaseLog nvarchar(max), TraceMessage nvarchar(max),\n										CreatedOn datetime, StackTrace nvarchar(max),ExecutionSeconds nvarchar(50), ThreadId int, ProcessName nvarchar(512),\n										ConnectionString nvarchar(1024))\n									END\n									\n									INSERT INTO DebugSqlTrace VALUES\n										(NEWID(), @DatabaseLog, @TraceMessage, `
- `0x2dc34`: `@ThreadId`

## pseudocode

```c

```

## disassembly

```asm
0x2dba0  call     bool Microsoft.Crm.SQLLogger::get_IsEnabled()
0x2dba5  brfalse  loc_2DC9E
0x2dbaa  ldstr    aConfigdb// "configdb"
0x2dbaf  call     object Microsoft.Crm.RegistryCache::GetValue(string key)
0x2dbb4  isinst   [mscorlib]System.String
0x2dbb9  newobj   instance void [System.Data]System.Data.SqlClient.SqlConnection::.ctor(string)
0x2dbbe  stloc.0
0x2dbbf  ldloc.0
0x2dbc0  callvirt instance void [System.Data]System.Data.Common.DbConnection::Open()
0x2dbc5  ldstr    aIfNotExistsSel// "\tIF NOT EXISTS(SELECT * FROM Sys.Objec"...
0x2dbca  ldloc.0
0x2dbcb  newobj   instance void [System.Data]System.Data.SqlClient.SqlCommand::.ctor(string, class [System.Data]System.Data.SqlClient.SqlConnection)
0x2dbd0  stloc.1
0x2dbd1  ldloc.1
0x2dbd2  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection [System.Data]System.Data.SqlClient.SqlCommand::get_Parameters()
0x2dbd7  dup
0x2dbd8  ldstr    aDatabaselog// "@DatabaseLog"
0x2dbdd  ldarg.0
0x2dbde  newobj   instance void [System.Data]System.Data.SqlClient.SqlParameter::.ctor(string, object)
0x2dbe3  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(class [System.Data]System.Data.SqlClient.SqlParameter)
0x2dbe8  pop
0x2dbe9  dup
0x2dbea  ldstr    aTracemessage// "@TraceMessage"
0x2dbef  ldarg.2
0x2dbf0  newobj   instance void [System.Data]System.Data.SqlClient.SqlParameter::.ctor(string, object)
0x2dbf5  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(class [System.Data]System.Data.SqlClient.SqlParameter)
0x2dbfa  pop
0x2dbfb  dup
0x2dbfc  ldstr    aStacktrace_0// "@StackTrace"
0x2dc01  call     string [mscorlib]System.Environment::get_StackTrace()
0x2dc06  newobj   instance void [System.Data]System.Data.SqlClient.SqlParameter::.ctor(string, object)
0x2dc0b  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(class [System.Data]System.Data.SqlClient.SqlParameter)
0x2dc10  pop
0x2dc11  dup
0x2dc12  ldstr    aExecutionsecon// "@ExecutionSeconds"
0x2dc17  ldarga.s 1
0x2dc19  ldstr    aF1// "F1"
0x2dc1e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2dc23  call     instance string [mscorlib]System.Double::ToString(string, class [mscorlib]System.IFormatProvider)
0x2dc28  newobj   instance void [System.Data]System.Data.SqlClient.SqlParameter::.ctor(string, object)
0x2dc2d  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(class [System.Data]System.Data.SqlClient.SqlParameter)
0x2dc32  pop
0x2dc33  dup
0x2dc34  ldstr    aThreadid// "@ThreadId"
0x2dc39  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0x2dc3e  callvirt instance int32 [mscorlib]System.Threading.Thread::get_ManagedThreadId()
0x2dc43  box      [mscorlib]System.Int32
0x2dc48  newobj   instance void [System.Data]System.Data.SqlClient.SqlParameter::.ctor(string, object)
0x2dc4d  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(class [System.Data]System.Data.SqlClient.SqlParameter)
0x2dc52  pop
0x2dc53  dup
0x2dc54  ldstr    aProcessname// "@ProcessName"
0x2dc59  call     class [System]System.Diagnostics.Process [System]System.Diagnostics.Process::GetCurrentProcess()
0x2dc5e  callvirt instance string [System]System.Diagnostics.Process::get_ProcessName()
0x2dc63  newobj   instance void [System.Data]System.Data.SqlClient.SqlParameter::.ctor(string, object)
0x2dc68  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(class [System.Data]System.Data.SqlClient.SqlParameter)
0x2dc6d  pop
0x2dc6e  ldstr    aConnectionstri_4// "@ConnectionString"
0x2dc73  ldarg.3
0x2dc74  newobj   instance void [System.Data]System.Data.SqlClient.SqlParameter::.ctor(string, object)
0x2dc79  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(class [System.Data]System.Data.SqlClient.SqlParameter)
0x2dc7e  pop
0x2dc7f  ldloc.1
0x2dc80  callvirt instance int32 [System.Data]System.Data.Common.DbCommand::ExecuteNonQuery()
0x2dc85  pop
0x2dc86  leave.s  loc_2DC92
0x2dc88  ldloc.1
0x2dc89  brfalse.s loc_2DC91
0x2dc8b  ldloc.1
0x2dc8c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2dc91  endfinally
0x2dc92  leave.s  loc_2DC9E
0x2dc94  ldloc.0
0x2dc95  brfalse.s loc_2DC9D
0x2dc97  ldloc.0
0x2dc98  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2dc9d  endfinally
0x2dc9e  leave.s  loc_2DCC6
0x2dca0  stloc.2
0x2dca1  ldloc.2
0x2dca2  call     valuetype [mscorlib]System.Guid Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x2dca7  ldc.i4.s 0x1D
0x2dca9  ldstr    aNotAbleToPerfo// "Not able to perform extended SQL loggin"...
0x2dcae  ldloc.2
0x2dcaf  callvirt instance string [mscorlib]System.Object::ToString()
0x2dcb4  call     string [mscorlib]System.String::Concat(string, string)
0x2dcb9  ldc.i4.0
0x2dcba  newarr   [mscorlib]System.Object
0x2dcbf  call     void Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception ex, valuetype [mscorlib]System.Guid orgId, valuetype Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x2dcc4  leave.s  loc_2DCC6
0x2dcc6  ret
```
