# Microsoft.Crm.Platform.MetadataBusinessEntities.DBCommandExecutor::ExecuteNonQuery

- ea: `0x42ed0`
- end: `0x42f63`
- name: `Microsoft.Crm.Platform.MetadataBusinessEntities.DBCommandExecutor::ExecuteNonQuery`
- size: `147`
- prototype: ``
- caller_count: `31`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x33150`
- `0x33260`
- `0x33370`
- `0x33470`
- `0x33780`
- `0x338f0`
- `0x33c40`
- `0x33f20`
- `0x34100`
- `0x34240`
- `0x34500`
- `0x345d0`
- `0x34730`
- `0x34930`
- `0x40050`
- `0x43930`
- `0x43b70`
- `0x43c10`
- `0x43e70`
- `0x447f0`
- `0x448f0`
- `0x44a00`
- `0x49aa0`
- `0x4ba80`
- `0x4bc30`
- `0x4bd50`
- `0x4bd80`
- `0x4bdb0`
- `0x4bde0`
- `0x4bf30`
- `0x4c270`

## callees

- `0x42ed0`

## string_xrefs

- `0x42ed1`: `command`
- `0x42f2b`: `D:\a\1\s\src\ManagedPlatform\Server\Metadata\DbCommandExecutor.cs`

## pseudocode

```c

```

## disassembly

```asm
0x42ed0  ldarg.0
0x42ed1  ldstr    aCommand_0// "command"
0x42ed6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x42edb  ldarg.1
0x42edc  ldstr    aContext// "context"
0x42ee1  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x42ee6  ldarg.0
0x42ee7  callvirt instance class [System.Data]System.Data.IDbConnection [System.Data]System.Data.IDbCommand::get_Connection()
0x42eec  brtrue.s loc_42EFB
0x42eee  ldarg.1
0x42eef  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext::get_Connection()
0x42ef4  ldarga.s 0
0x42ef6  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand(class [System.Data]System.Data.IDbCommand&)
0x42efb  ldarg.0
0x42efc  ldarg.1
0x42efd  callvirt instance class [System.Data]System.Data.IDbTransaction [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext::get_SqlTransaction()
0x42f02  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::SetTransaction(class [System.Data]System.Data.IDbCommand, class [System.Data]System.Data.IDbTransaction)
0x42f07  ldarg.1
0x42f08  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x42f0d  ldc.i4.s 0x1D
0x42f0f  ldstr    a0// "{0}"
0x42f14  ldc.i4.1
0x42f15  newarr   [mscorlib]System.Object
0x42f1a  dup
0x42f1b  ldc.i4.0
0x42f1c  ldarg.0
0x42f1d  stelem.ref
0x42f1e  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x42f23  ldarg.0
0x42f24  ldc.i4.s 0x51
0x42f26  ldstr    aExecutenonquer// "ExecuteNonQuery"
0x42f2b  ldstr    aDA1SSrcManaged_8// "D:\\a\\1\\s\\src\\ManagedPlatform\\Serv"...
0x42f30  call     int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand, int32, string, string)
0x42f35  stloc.0
0x42f36  leave.s  loc_42F61
0x42f38  stloc.1
0x42f39  ldloc.1
0x42f3a  ldarg.1
0x42f3b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x42f40  ldc.i4.s 0x1D
0x42f42  ldstr    aExceptionWhenE_1// "Exception when executing non-query: {0}"...
0x42f47  ldc.i4.2
0x42f48  newarr   [mscorlib]System.Object
0x42f4d  dup
0x42f4e  ldc.i4.0
0x42f4f  ldarg.0
0x42f50  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::GetTraceMessage(class [System.Data]System.Data.IDbCommand)
0x42f55  stelem.ref
0x42f56  dup
0x42f57  ldc.i4.1
0x42f58  ldloc.1
0x42f59  stelem.ref
0x42f5a  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x42f5f  rethrow
0x42f61  ldloc.0
0x42f62  ret
```
