# Microsoft.Crm.Asynchronous.ResourceBookingSyncService::ExecuteTransaction

- ea: `0x8840`
- end: `0x88d1`
- name: `Microsoft.Crm.Asynchronous.ResourceBookingSyncService::ExecuteTransaction`
- size: `145`
- prototype: ``
- caller_count: `7`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x6510`
- `0x6a10`
- `0x7860`
- `0x7ae0`
- `0x7d00`
- `0x8080`
- `0x82b0`

## callees

- `0x8840`
- `0x16390`
- `0x163e0`
- `0x16540`

## string_xrefs

- `0x886f`: `d:\dbs\sh\dccm2\1101_190851\cmd\77\src\Core\ObjectModel\Async\Handlers\BusinessManagement\ResourceBookingSyncService.cs`

## pseudocode

```c

```

## disassembly

```asm
0x8840  ldc.i4.0
0x8841  stloc.0
0x8842  ldarg.0
0x8843  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x8848  ldstr    aMethodexecutet// "MethodExecuteTransaction"
0x884d  callvirt instance void Metrics::StartTimer(string name)
0x8852  ldarg.1
0x8853  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction::StartTransaction()
0x8858  ldarg.2
0x8859  ldarg.1
0x885a  callvirt instance class [System.Data]System.Data.IDbTransaction [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction::get_SqlTrans()
0x885f  callvirt instance void [System.Data]System.Data.IDbCommand::set_Transaction(class [System.Data]System.Data.IDbTransaction)
0x8864  ldarg.2
0x8865  ldc.i4   0x76B
0x886a  ldstr    aExecutetransac// "ExecuteTransaction"
0x886f  ldstr    aDDbsShDccm2110_1// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\7"...
0x8874  call     int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand, int32, string, string)
0x8879  stloc.0
0x887a  ldarg.1
0x887b  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction::CommitTransaction()
0x8880  leave.s  loc_88CF
0x8882  stloc.1
0x8883  ldarg.1
0x8884  ldc.i4.0
0x8885  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction::RollbackTransaction(bool)
0x888a  ldc.i4.m1
0x888b  stloc.0
0x888c  ldarg.0
0x888d  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x8892  ldstr    a0The1DatabaseT// "{0} - The {1} database transaction fail"...
0x8897  ldloc.1
0x8898  callvirt instance string [mscorlib]System.Exception::get_Message()
0x889d  ldtoken  DatabaseTransactionType
0x88a2  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x88a7  ldarg.3
0x88a8  box      DatabaseTransactionType
0x88ad  call     string [mscorlib]System.Enum::GetName(class [mscorlib]System.Type, object)
0x88b2  call     string [mscorlib]System.String::Format(string, object, object)
0x88b7  callvirt instance void Metrics::AddMessageAndTrace(string message)
0x88bc  leave.s  loc_88CF
0x88be  ldarg.0
0x88bf  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x88c4  ldstr    aMethodexecutet// "MethodExecuteTransaction"
0x88c9  callvirt instance void Metrics::StopTimer(string name)
0x88ce  endfinally
0x88cf  ldloc.0
0x88d0  ret
```
