# Microsoft.Crm.Platform.MetadataBusinessEntities.DBCommandExecutor::ExecuteScalar

- ea: `0x42e30`
- end: `0x42ec1`
- name: `Microsoft.Crm.Platform.MetadataBusinessEntities.DBCommandExecutor::ExecuteScalar`
- size: `145`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x4a7b0`
- `0x4a840`
- `0x4a8c0`

## callees

- `0x42e30`

## string_xrefs

- `0x42e31`: `command`
- `0x42e8a`: `D:\a\1\s\src\ManagedPlatform\Server\Metadata\DbCommandExecutor.cs`

## pseudocode

```c

```

## disassembly

```asm
0x42e30  ldarg.0
0x42e31  ldstr    aCommand_0// "command"
0x42e36  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x42e3b  ldarg.1
0x42e3c  ldstr    aContext// "context"
0x42e41  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x42e46  ldarg.0
0x42e47  callvirt instance class [System.Data]System.Data.IDbConnection [System.Data]System.Data.IDbCommand::get_Connection()
0x42e4c  brtrue.s loc_42E5B
0x42e4e  ldarg.1
0x42e4f  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext::get_Connection()
0x42e54  ldarga.s 0
0x42e56  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand(class [System.Data]System.Data.IDbCommand&)
0x42e5b  ldarg.0
0x42e5c  ldarg.1
0x42e5d  callvirt instance class [System.Data]System.Data.IDbTransaction [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext::get_SqlTransaction()
0x42e62  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::SetTransaction(class [System.Data]System.Data.IDbCommand, class [System.Data]System.Data.IDbTransaction)
0x42e67  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x42e6c  ldc.i4.s 0x1D
0x42e6e  ldstr    aSqlExecutescal// "SQL ExecuteScalar: {0}"
0x42e73  ldc.i4.1
0x42e74  newarr   [mscorlib]System.Object
0x42e79  dup
0x42e7a  ldc.i4.0
0x42e7b  ldarg.0
0x42e7c  stelem.ref
0x42e7d  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x42e82  ldarg.0
0x42e83  ldc.i4.s 0x37
0x42e85  ldstr    aExecutescalar// "ExecuteScalar"
0x42e8a  ldstr    aDA1SSrcManaged_8// "D:\\a\\1\\s\\src\\ManagedPlatform\\Serv"...
0x42e8f  call     object [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteScalar(class [System.Data]System.Data.IDbCommand, int32, string, string)
0x42e94  stloc.0
0x42e95  leave.s  loc_42EBF
0x42e97  stloc.1
0x42e98  ldloc.1
0x42e99  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x42e9e  ldc.i4.s 0x1D
0x42ea0  ldstr    aExceptionWhenE_0// "Exception when executing scalar: {0} Ex"...
0x42ea5  ldc.i4.2
0x42ea6  newarr   [mscorlib]System.Object
0x42eab  dup
0x42eac  ldc.i4.0
0x42ead  ldarg.0
0x42eae  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::GetTraceMessage(class [System.Data]System.Data.IDbCommand)
0x42eb3  stelem.ref
0x42eb4  dup
0x42eb5  ldc.i4.1
0x42eb6  ldloc.1
0x42eb7  stelem.ref
0x42eb8  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x42ebd  rethrow
0x42ebf  ldloc.0
0x42ec0  ret
```
