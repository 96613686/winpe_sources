# Microsoft.Crm.Asynchronous.AsyncOperationQueueManagerBase::CreateCommonTimers

- ea: `0x4c20`
- end: `0x4c70`
- name: `Microsoft.Crm.Asynchronous.AsyncOperationQueueManagerBase::CreateCommonTimers`
- size: `80`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x4a00`
- `0xec00`

## callees

- `0x4bd0`
- `0x4c70`
- `0x4cb0`
- `0x4d70`
- `0x59a0`
- `0x59c0`
- `0x6e60`

## pseudocode

```c

```

## disassembly

```asm
0x4c20  ldarg.1
0x4c21  ldarg.0
0x4c22  call     instance class Microsoft.Crm.Asynchronous.Operations.IServiceOperation Microsoft.Crm.Asynchronous.AsyncOperationQueueManagerBase::CreateOnDatabaseOperationTimerOperation()
0x4c27  ldarg.0
0x4c28  call     instance class Microsoft.Crm.Asynchronous.IAsyncOperationQueueConfiguration Microsoft.Crm.Asynchronous.AsyncOperationQueueManagerBase::get_FullConfiguration()
0x4c2d  callvirt instance valuetype [mscorlib]System.TimeSpan Microsoft.Crm.Asynchronous.IAsyncOperationQueueConfiguration::get_StateStatusUpdateInterval()
0x4c32  stloc.0
0x4c33  ldloca.s 0
0x4c35  call     instance float64 [mscorlib]System.TimeSpan::get_TotalMilliseconds()
0x4c3a  newobj   instance void Microsoft.Crm.Asynchronous.TimerBasedExecutionEngine::.ctor(class Microsoft.Crm.Asynchronous.Operations.IServiceOperation operation, float64 interval)
0x4c3f  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.Crm.Asynchronous.TimerBasedExecutionEngine>::Add(var<u1>)
0x4c44  ldarg.1
0x4c45  ldarg.0
0x4c46  call     instance class Microsoft.Crm.Asynchronous.Operations.IServiceOperation Microsoft.Crm.Asynchronous.AsyncOperationQueueManagerBase::CreateOnKeepAliveTimerOperation()
0x4c4b  ldarg.0
0x4c4c  call     instance class Microsoft.Crm.Asynchronous.IAsyncOperationQueueConfiguration Microsoft.Crm.Asynchronous.AsyncOperationQueueManagerBase::get_FullConfiguration()
0x4c51  callvirt instance valuetype [mscorlib]System.TimeSpan Microsoft.Crm.Asynchronous.IAsyncOperationQueueConfiguration::get_KeepAliveInterval()
0x4c56  stloc.0
0x4c57  ldloca.s 0
0x4c59  call     instance float64 [mscorlib]System.TimeSpan::get_TotalMilliseconds()
0x4c5e  newobj   instance void Microsoft.Crm.Asynchronous.TimerBasedExecutionEngine::.ctor(class Microsoft.Crm.Asynchronous.Operations.IServiceOperation operation, float64 interval)
0x4c63  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.Crm.Asynchronous.TimerBasedExecutionEngine>::Add(var<u1>)
0x4c68  ldarg.0
0x4c69  ldarg.1
0x4c6a  call     instance void Microsoft.Crm.Asynchronous.AsyncOperationQueueManagerBase::CreateLostJobDetectionTimer(class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.Crm.Asynchronous.TimerBasedExecutionEngine> timers)
0x4c6f  ret
```
