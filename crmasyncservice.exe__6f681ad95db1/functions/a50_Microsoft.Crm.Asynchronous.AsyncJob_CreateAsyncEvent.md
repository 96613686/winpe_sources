# Microsoft.Crm.Asynchronous.AsyncJob::CreateAsyncEvent

- ea: `0xa50`
- end: `0xab4`
- name: `Microsoft.Crm.Asynchronous.AsyncJob::CreateAsyncEvent`
- size: `100`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x45d0`
- `0x4840`

## callees

- `0x9d0`
- `0x9e0`
- `0xa10`
- `0xa20`
- `0xa30`
- `0xa40`
- `0xa50`

## pseudocode

```c

```

## disassembly

```asm
0xa50  ldnull
0xa51  ldarg.0
0xa52  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.AsyncJob::get_OrganizationId()
0xa57  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xa5c  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xa61  ldarg.0
0xa62  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.AsyncJob::get_JobId()
0xa67  ldarg.0
0xa68  callvirt instance int32 Microsoft.Crm.Asynchronous.AsyncJob::get_OperationType()
0xa6d  ldnull
0xa6e  ldnull
0xa6f  ldnull
0xa70  ldnull
0xa71  ldnull
0xa72  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xa77  ldc.i4.0
0xa78  ldnull
0xa79  ldarg.1
0xa7a  brtrue.s loc_A7F
0xa7c  ldnull
0xa7d  br.s     loc_A85
0xa7f  ldarg.0
0xa80  callvirt instance string Microsoft.Crm.Asynchronous.AsyncJob::get_RecurrencePattern()
0xa85  ldarg.0
0xa86  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.AsyncJob::get_RecurrenceStartTime()
0xa8b  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0xa90  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MinValue
0xa95  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MinValue
0xa9a  ldnull
0xa9b  ldloca.s 0
0xa9d  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0xaa3  ldloc.0
0xaa4  ldnull
0xaa5  ldc.i4.1
0xaa6  ldarg.0
0xaa7  callvirt instance string Microsoft.Crm.Asynchronous.AsyncJob::get_JobParameters()
0xaac  ldc.i4.0
0xaad  ldnull
0xaae  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent::.ctor(class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncOperationQueueManagerBase, valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, int32, string, string, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.EntityNameReference, valuetype [mscorlib]System.Guid, int32, string, string, valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CorrelationToken, valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration, int32, string, int32, class [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmRootExecutionContext)
0xab3  ret
```
