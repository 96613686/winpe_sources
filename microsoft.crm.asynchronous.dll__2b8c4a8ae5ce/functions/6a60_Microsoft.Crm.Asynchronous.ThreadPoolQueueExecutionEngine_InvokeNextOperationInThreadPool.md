# Microsoft.Crm.Asynchronous.ThreadPoolQueueExecutionEngine::InvokeNextOperationInThreadPool

- ea: `0x6a60`
- end: `0x6ab2`
- name: `Microsoft.Crm.Asynchronous.ThreadPoolQueueExecutionEngine::InvokeNextOperationInThreadPool`
- size: `82`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x6a60`
- `0x6ac0`
- `0x6c10`
- `0x93d0`
- `0x15660`
- `0x15810`
- `0x15870`
- `0x17660`

## string_xrefs

- `0x6a9f`: `QueueThreadCountSemaphore`

## pseudocode

```c

```

## disassembly

```asm
0x6a60  ldc.i4.1
0x6a61  stloc.0
0x6a62  br.s     loc_6A89
0x6a64  ldloc.1
0x6a65  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.Operations.IServiceOperation::get_OrganizationId()
0x6a6a  newobj   instance void DefaultOrganizationTracer::.ctor(valuetype [mscorlib]System.Guid orgId)
0x6a6f  stloc.2
0x6a70  ldloc.1
0x6a71  callvirt instance void Microsoft.Crm.Asynchronous.Operations.IServiceOperation::Execute()
0x6a76  ldloc.1
0x6a77  callvirt instance bool Microsoft.Crm.Asynchronous.Operations.IThreadPoolOperation::get_ReuseResource()
0x6a7c  stloc.0
0x6a7d  leave.s  loc_6A89
0x6a7f  ldloc.2
0x6a80  brfalse.s loc_6A88
0x6a82  ldloc.2
0x6a83  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6a88  endfinally
0x6a89  ldloc.0
0x6a8a  brfalse.s loc_6A96
0x6a8c  ldarg.0
0x6a8d  call     instance class Microsoft.Crm.Asynchronous.Operations.IThreadPoolOperation Microsoft.Crm.Asynchronous.ThreadPoolQueueExecutionEngine::SafeDequeue()
0x6a92  dup
0x6a93  stloc.1
0x6a94  brtrue.s loc_6A64
0x6a96  ldloc.0
0x6a97  brfalse.s loc_6AB1
0x6a99  ldarg.0
0x6a9a  ldfld    class [mscorlib]System.Threading.SemaphoreSlim Microsoft.Crm.Asynchronous.ThreadPoolQueueExecutionEngine::_threadCountThrottle
0x6a9f  ldstr    aQueuethreadcou// "QueueThreadCountSemaphore"
0x6aa4  ldc.i4.1
0x6aa5  call     bool Microsoft.Crm.Asynchronous.AsyncEventSemaphoreManager::SafeReleaseSemaphore(class [mscorlib]System.Threading.SemaphoreSlim semaphore, string semaphoreName, [opt] int32 count)
0x6aaa  pop
0x6aab  ldarg.0
0x6aac  call     instance void Microsoft.Crm.Asynchronous.ThreadPoolQueueExecutionEngine::FireOnThreadUsageChangedEvent()
0x6ab1  ret
```
