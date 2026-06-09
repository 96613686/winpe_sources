# Microsoft.Crm.SharedDatabase.DatabaseService::ExecutePropertiesReader

- ea: `0x62760`
- end: `0x627d7`
- name: `Microsoft.Crm.SharedDatabase.DatabaseService::ExecutePropertiesReader`
- size: `119`
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
- `0x62760`
- `0x628a0`
- `0x63ff0`
- `0x64580`

## string_xrefs

- `0x62784`: `D:\a\1\s\src\Platform\Core\DataServices\ObjectModel\DatabaseService.cs`
- `0x6277f`: `ExecutePropertiesReader`

## pseudocode

```c

```

## disassembly

```asm
0x62760  ldarg.1
0x62761  ldstr    aConnection_2// "connection"
0x62766  call     void Microsoft.Crm.Exceptions::ThrowIfNull(object parameter, string name)
0x6276b  ldarg.2
0x6276c  brtrue.s loc_6276F
0x6276e  ret
0x6276f  nop
0x62770  ldarg.0
0x62771  ldc.i4.0
0x62772  ldarg.2
0x62773  call     instance void Microsoft.Crm.SharedDatabase.DatabaseService::InstrumentQuery(valuetype Microsoft.Crm.InstrumentationOperationType type, class [System.Data]System.Data.IDbCommand command)
0x62778  ldarg.2
0x62779  ldc.i4.1
0x6277a  ldc.i4   0x6AF
0x6277f  ldstr    aExecutepropert// "ExecutePropertiesReader"
0x62784  ldstr    aDA1SSrcPlatfor_44// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0x62789  call     class [System.Data]System.Data.IDataReader Microsoft.Crm.CrmDbConnection::ExecuteReader(class [System.Data]System.Data.IDbCommand command, bool impersonate, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0x6278e  stloc.0
0x6278f  ldarg.0
0x62790  ldarg.s  4
0x62792  ldloc.0
0x62793  ldarg.3
0x62794  call     instance void Microsoft.Crm.SharedDatabase.DatabaseService::UpdatePropertyBagCollection(class [mscorlib]System.Collections.IDictionary resultSet, class [System.Data]System.Data.IDataReader reader, string[] columns)
0x62799  leave.s  loc_627A5
0x6279b  ldloc.0
0x6279c  brfalse.s loc_627A4
0x6279e  ldloc.0
0x6279f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x627a4  endfinally
0x627a5  leave.s  loc_627D6
0x627a7  stloc.1
0x627a8  ldloc.1
0x627a9  call     valuetype [mscorlib]System.Guid Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x627ae  ldc.i4.s 0x1D
0x627b0  ldstr    aExceptionWhenE// "Exception when executing query: {0} Exc"...
0x627b5  ldc.i4.2
0x627b6  newarr   [mscorlib]System.Object
0x627bb  dup
0x627bc  ldc.i4.0
0x627bd  ldarg.2
0x627be  call     string Microsoft.Crm.CrmDbConnection::GetTraceMessage(class [System.Data]System.Data.IDbCommand command)
0x627c3  stelem.ref
0x627c4  dup
0x627c5  ldc.i4.1
0x627c6  ldloc.1
0x627c7  stelem.ref
0x627c8  call     void Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception ex, valuetype [mscorlib]System.Guid orgId, valuetype Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x627cd  ldarg.0
0x627ce  ldloc.1
0x627cf  call     instance void Microsoft.Crm.SharedDatabase.DatabaseService::LogSqlError(class [mscorlib]System.Exception exception)
0x627d4  rethrow
0x627d6  ret
```
