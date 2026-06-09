# Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueManager::CreateTimers

- ea: `0x9f40`
- end: `0xa011`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueManager::CreateTimers`
- size: `209`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x9ec0`
- `0xa0b0`
- `0xa100`
- `0xa150`

## pseudocode

```c

```

## disassembly

```asm
0x9f40  ldarg.0
0x9f41  call     instance class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.TimerBasedExecutionEngine> [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.QueueManager::CreateTimers()
0x9f46  dup
0x9f47  ldarg.0
0x9f48  call     instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperationsFactory [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncManagerBase::get_OperationsFactory()
0x9f4d  ldarg.0
0x9f4e  call     instance string [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncManagerBase::get_InstanceName()
0x9f53  ldstr    asc_18F4A// ""
0x9f58  ldarg.0
0x9f59  ldftn    instance void Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueManager::<CreateTimers>b__14_0(class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperation operation)
0x9f5f  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.ServiceOperationAction::.ctor(object, native int)
0x9f64  callvirt instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperation [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperationsFactory::CreateQueueManagementOperation(string, string, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.ServiceOperationAction)
0x9f69  ldc.r8   0.2
0x9f72  ldarg.0
0x9f73  call     instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IQueueConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.QueueManager::get_Configuration()
0x9f78  callvirt instance valuetype [mscorlib]System.TimeSpan [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.ISharedQueueConfiguration::get_AsyncWaitingTimeout()
0x9f7d  stloc.0
0x9f7e  ldloca.s 0
0x9f80  call     instance float64 [mscorlib]System.TimeSpan::get_TotalMilliseconds()
0x9f85  mul
0x9f86  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.TimerBasedExecutionEngine::.ctor(class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperation, float64)
0x9f8b  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.TimerBasedExecutionEngine>::Add(var<u1>)
0x9f90  dup
0x9f91  ldarg.0
0x9f92  call     instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperation Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueManager::CreateOnKeepAliveTimerOperation()
0x9f97  ldc.r8   0.25
0x9fa0  ldarg.0
0x9fa1  call     instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IMailboxQueueConfiguration Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueManager::get_FullConfiguration()
0x9fa6  callvirt instance valuetype [mscorlib]System.TimeSpan [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IMailboxQueueConfiguration::get_MailboxRetryInterval()
0x9fab  stloc.0
0x9fac  ldloca.s 0
0x9fae  call     instance float64 [mscorlib]System.TimeSpan::get_TotalMilliseconds()
0x9fb3  mul
0x9fb4  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.TimerBasedExecutionEngine::.ctor(class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperation, float64)
0x9fb9  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.TimerBasedExecutionEngine>::Add(var<u1>)
0x9fbe  dup
0x9fbf  ldarg.0
0x9fc0  call     instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperation Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueManager::CreateOnTimeoutLockedTimerOperation()
0x9fc5  ldc.r8   0.75
0x9fce  ldarg.0
0x9fcf  call     instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IMailboxQueueConfiguration Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueManager::get_FullConfiguration()
0x9fd4  callvirt instance valuetype [mscorlib]System.TimeSpan [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IMailboxQueueConfiguration::get_MailboxRetryInterval()
0x9fd9  stloc.0
0x9fda  ldloca.s 0
0x9fdc  call     instance float64 [mscorlib]System.TimeSpan::get_TotalMilliseconds()
0x9fe1  mul
0x9fe2  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.TimerBasedExecutionEngine::.ctor(class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperation, float64)
0x9fe7  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.TimerBasedExecutionEngine>::Add(var<u1>)
0x9fec  dup
0x9fed  ldarg.0
0x9fee  call     instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperation Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueManager::CreateReportEventsOperation()
0x9ff3  ldarg.0
0x9ff4  call     instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IMailboxQueueConfiguration Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueManager::get_FullConfiguration()
0x9ff9  callvirt instance valuetype [mscorlib]System.TimeSpan [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IMailboxQueueConfiguration::get_MailboxReportEventInterval()
0x9ffe  stloc.0
0x9fff  ldloca.s 0
0xa001  call     instance float64 [mscorlib]System.TimeSpan::get_TotalMilliseconds()
0xa006  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.TimerBasedExecutionEngine::.ctor(class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperation, float64)
0xa00b  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.TimerBasedExecutionEngine>::Add(var<u1>)
0xa010  ret
```
