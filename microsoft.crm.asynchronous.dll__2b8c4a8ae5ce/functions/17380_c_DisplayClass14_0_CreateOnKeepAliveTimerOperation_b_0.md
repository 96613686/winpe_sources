# <>c__DisplayClass14_0::<CreateOnKeepAliveTimerOperation>b__0

- ea: `0x17380`
- end: `0x173d0`
- name: `<>c__DisplayClass14_0::<CreateOnKeepAliveTimerOperation>b__0`
- size: `80`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x4bd0`
- `0x5a10`
- `0x17380`

## pseudocode

```c

```

## disassembly

```asm
0x17380  ldarg.0
0x17381  ldfld    class Microsoft.Crm.Asynchronous.AsyncOperationQueueManagerBase <>c__DisplayClass14_0::<>4__this
0x17386  ldstr    aKeepAlive// "Keep Alive"
0x1738b  ldsfld   class OrganizationQueueDataAccessHandler<class Microsoft.Crm.Asynchronous.IAsyncOperationQueueDataAccess> <>c::<>9__14_1
0x17390  dup
0x17391  brtrue.s loc_173AA
0x17393  pop
0x17394  ldsfld   class <>c <>c::<>9
0x17399  ldftn    instance void <>c::<CreateOnKeepAliveTimerOperation>b__14_1(class Microsoft.Crm.Asynchronous.IAsyncOperationQueueDataAccess queueDataAccess, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration orgConfig)
0x1739f  newobj   instance void class OrganizationQueueDataAccessHandler<class Microsoft.Crm.Asynchronous.IAsyncOperationQueueDataAccess>::.ctor(object, native int)
0x173a4  dup
0x173a5  stsfld   class OrganizationQueueDataAccessHandler<class Microsoft.Crm.Asynchronous.IAsyncOperationQueueDataAccess> <>c::<>9__14_1
0x173aa  ldarg.0
0x173ab  ldfld    class Microsoft.Crm.Asynchronous.AsyncOperationQueueManagerBase <>c__DisplayClass14_0::<>4__this
0x173b0  call     instance class Microsoft.Crm.Asynchronous.IAsyncOperationQueueConfiguration Microsoft.Crm.Asynchronous.AsyncOperationQueueManagerBase::get_FullConfiguration()
0x173b5  callvirt instance valuetype [mscorlib]System.TimeSpan Microsoft.Crm.Asynchronous.IAsyncOperationQueueConfiguration::get_TimeUntilLockExpires()
0x173ba  stloc.0
0x173bb  ldloca.s 0
0x173bd  call     instance float64 [mscorlib]System.TimeSpan::get_TotalSeconds()
0x173c2  conv.i8
0x173c3  ldarg.0
0x173c4  ldfld    bool <>c__DisplayClass14_0::useParallelExecution
0x173c9  call     instance class Microsoft.Crm.Asynchronous.Operations.IServiceOperation class Microsoft.Crm.Asynchronous.SynchronousQueueManager`1<class Microsoft.Crm.Asynchronous.IAsyncOperationQueueDataAccess>::ExecuteQueueManagementOperationForAllOrganizationWithMetric(string, class OrganizationQueueDataAccessHandler<var<u1>>, !!T0, int64)
0x173ce  pop
0x173cf  ret
```
