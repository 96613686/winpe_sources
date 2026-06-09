# Microsoft.Crm.Platform.MetadataBusinessEntities.DBCommandExecutor::ExecuteQuery

- ea: `0x42d90`
- end: `0x42e21`
- name: `Microsoft.Crm.Platform.MetadataBusinessEntities.DBCommandExecutor::ExecuteQuery`
- size: `145`
- prototype: ``
- caller_count: `8`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x436c0`
- `0x43930`
- `0x43d60`
- `0x43e30`
- `0x46800`
- `0x46860`
- `0x468c0`
- `0x49c80`

## callees

- `0x42d90`

## string_xrefs

- `0x42d91`: `command`
- `0x42dea`: `D:\a\1\s\src\ManagedPlatform\Server\Metadata\DbCommandExecutor.cs`

## pseudocode

```c

```

## disassembly

```asm
0x42d90  ldarg.0
0x42d91  ldstr    aCommand_0// "command"
0x42d96  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x42d9b  ldarg.1
0x42d9c  ldstr    aContext// "context"
0x42da1  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x42da6  ldarg.0
0x42da7  callvirt instance class [System.Data]System.Data.IDbConnection [System.Data]System.Data.IDbCommand::get_Connection()
0x42dac  brtrue.s loc_42DBB
0x42dae  ldarg.1
0x42daf  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext::get_Connection()
0x42db4  ldarga.s 0
0x42db6  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand(class [System.Data]System.Data.IDbCommand&)
0x42dbb  ldarg.0
0x42dbc  ldarg.1
0x42dbd  callvirt instance class [System.Data]System.Data.IDbTransaction [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext::get_SqlTransaction()
0x42dc2  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::SetTransaction(class [System.Data]System.Data.IDbCommand, class [System.Data]System.Data.IDbTransaction)
0x42dc7  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x42dcc  ldc.i4.s 0x1D
0x42dce  ldstr    a0// "{0}"
0x42dd3  ldc.i4.1
0x42dd4  newarr   [mscorlib]System.Object
0x42dd9  dup
0x42dda  ldc.i4.0
0x42ddb  ldarg.0
0x42ddc  stelem.ref
0x42ddd  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x42de2  ldarg.0
0x42de3  ldc.i4.s 0x1D
0x42de5  ldstr    aExecutequery// "ExecuteQuery"
0x42dea  ldstr    aDA1SSrcManaged_8// "D:\\a\\1\\s\\src\\ManagedPlatform\\Serv"...
0x42def  call     class [System.Data]System.Data.IDataReader [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteReader(class [System.Data]System.Data.IDbCommand, int32, string, string)
0x42df4  stloc.0
0x42df5  leave.s  loc_42E1F
0x42df7  stloc.1
0x42df8  ldloc.1
0x42df9  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x42dfe  ldc.i4.s 0x1D
0x42e00  ldstr    aExceptionWhenE// "Exception when executing query: {0} Exc"...
0x42e05  ldc.i4.2
0x42e06  newarr   [mscorlib]System.Object
0x42e0b  dup
0x42e0c  ldc.i4.0
0x42e0d  ldarg.0
0x42e0e  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::GetTraceMessage(class [System.Data]System.Data.IDbCommand)
0x42e13  stelem.ref
0x42e14  dup
0x42e15  ldc.i4.1
0x42e16  ldloc.1
0x42e17  stelem.ref
0x42e18  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x42e1d  rethrow
0x42e1f  ldloc.0
0x42e20  ret
```
