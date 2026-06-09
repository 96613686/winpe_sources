# Microsoft.Crm.SharedDatabase.DatabaseService::ExecuteBaseReader

- ea: `0x626e0`
- end: `0x62760`
- name: `Microsoft.Crm.SharedDatabase.DatabaseService::ExecuteBaseReader`
- size: `128`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x61780`

## callees

- `0xdb00`
- `0xdc50`
- `0x1be80`
- `0x1eaa0`
- `0x1f510`
- `0x626e0`
- `0x627e0`
- `0x63ff0`
- `0x64580`

## string_xrefs

- `0x626ec`: `command`
- `0x6270a`: `D:\a\1\s\src\Platform\Core\DataServices\ObjectModel\DatabaseService.cs`
- `0x62705`: `ExecuteBaseReader`

## pseudocode

```c

```

## disassembly

```asm
0x626e0  ldarg.1
0x626e1  ldstr    aConnection_2// "connection"
0x626e6  call     void Microsoft.Crm.Exceptions::ThrowIfNull(object parameter, string name)
0x626eb  ldarg.2
0x626ec  ldstr    aCommand// "command"
0x626f1  call     void Microsoft.Crm.Exceptions::ThrowIfNull(object parameter, string name)
0x626f6  ldarg.0
0x626f7  ldc.i4.0
0x626f8  ldarg.2
0x626f9  call     instance void Microsoft.Crm.SharedDatabase.DatabaseService::InstrumentQuery(valuetype Microsoft.Crm.InstrumentationOperationType type, class [System.Data]System.Data.IDbCommand command)
0x626fe  ldarg.2
0x626ff  ldc.i4.1
0x62700  ldc.i4   0x686
0x62705  ldstr    aExecutebaserea// "ExecuteBaseReader"
0x6270a  ldstr    aDA1SSrcPlatfor_44// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0x6270f  call     class [System.Data]System.Data.IDataReader Microsoft.Crm.CrmDbConnection::ExecuteReader(class [System.Data]System.Data.IDbCommand command, bool impersonate, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0x62714  stloc.0
0x62715  ldarg.0
0x62716  ldloc.0
0x62717  ldarg.3
0x62718  ldarg.s  4
0x6271a  call     instance void Microsoft.Crm.SharedDatabase.DatabaseService::CreatePropertyBagCollectionFromReader(class [System.Data]System.Data.IDataReader reader, string[] columns, class [mscorlib]System.Collections.IDictionary collectionToFill)
0x6271f  leave.s  loc_6272B
0x62721  ldloc.0
0x62722  brfalse.s loc_6272A
0x62724  ldloc.0
0x62725  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6272a  endfinally
0x6272b  leave.s  loc_6275F
0x6272d  pop
0x6272e  rethrow
0x62730  stloc.1
0x62731  ldloc.1
0x62732  call     valuetype [mscorlib]System.Guid Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x62737  ldc.i4.s 0x1D
0x62739  ldstr    aExceptionWhenE// "Exception when executing query: {0} Exc"...
0x6273e  ldc.i4.2
0x6273f  newarr   [mscorlib]System.Object
0x62744  dup
0x62745  ldc.i4.0
0x62746  ldarg.2
0x62747  call     string Microsoft.Crm.CrmDbConnection::GetTraceMessage(class [System.Data]System.Data.IDbCommand command)
0x6274c  stelem.ref
0x6274d  dup
0x6274e  ldc.i4.1
0x6274f  ldloc.1
0x62750  stelem.ref
0x62751  call     void Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception ex, valuetype [mscorlib]System.Guid orgId, valuetype Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x62756  ldarg.0
0x62757  ldloc.1
0x62758  call     instance void Microsoft.Crm.SharedDatabase.DatabaseService::LogSqlError(class [mscorlib]System.Exception exception)
0x6275d  rethrow
0x6275f  ret
```
