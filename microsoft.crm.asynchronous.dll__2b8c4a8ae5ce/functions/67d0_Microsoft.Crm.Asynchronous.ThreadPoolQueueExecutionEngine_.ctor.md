# Microsoft.Crm.Asynchronous.ThreadPoolQueueExecutionEngine::.ctor

- ea: `0x67d0`
- end: `0x68ca`
- name: `Microsoft.Crm.Asynchronous.ThreadPoolQueueExecutionEngine::.ctor`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x9540`

## callees

- `0x67d0`
- `0x6d70`
- `0x9500`
- `0x9520`
- `0xb4b0`
- `0x10100`

## pseudocode

```c

```

## disassembly

```asm
0x67d0  ldarg.0
0x67d1  call     instance void [mscorlib]System.Object::.ctor()
0x67d6  ldarg.0
0x67d7  newobj   instance void class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, bool>::.ctor()
0x67dc  stfld    class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, bool> Microsoft.Crm.Asynchronous.ThreadPoolQueueExecutionEngine::_longJobsOrgs
0x67e1  ldarg.0
0x67e2  ldarg.2
0x67e3  stfld    class Microsoft.Crm.Asynchronous.IThreadPoolThrottlingSettings Microsoft.Crm.Asynchronous.ThreadPoolQueueExecutionEngine::_settings
0x67e8  ldarg.0
0x67e9  ldarg.0
0x67ea  call     instance int32 Microsoft.Crm.Asynchronous.ThreadPoolQueueExecutionEngine::get_MaximumThreadCount()
0x67ef  stfld    int32 Microsoft.Crm.Asynchronous.ThreadPoolQueueExecutionEngine::_maxThreadCount
0x67f4  ldarg.0
0x67f5  ldarg.0
0x67f6  ldfld    int32 Microsoft.Crm.Asynchronous.ThreadPoolQueueExecutionEngine::_maxThreadCount
0x67fb  ldarg.0
0x67fc  ldfld    int32 Microsoft.Crm.Asynchronous.ThreadPoolQueueExecutionEngine::_maxThreadCount
0x6801  newobj   instance void [mscorlib]System.Threading.SemaphoreSlim::.ctor(int32, int32)
0x6806  stfld    class [mscorlib]System.Threading.SemaphoreSlim Microsoft.Crm.Asynchronous.ThreadPoolQueueExecutionEngine::_threadCountThrottle
0x680b  ldarg.0
0x680c  newobj   instance void [System.Core]System.Threading.ReaderWriterLockSlim::.ctor()
0x6811  stfld    class [System.Core]System.Threading.ReaderWriterLockSlim Microsoft.Crm.Asynchronous.ThreadPoolQueueExecutionEngine::_queueReadWriteLock
0x6816  ldarg.0
0x6817  ldarg.0
0x6818  ldfld    int32 Microsoft.Crm.Asynchronous.ThreadPoolQueueExecutionEngine::_maxThreadCount
0x681d  call     int32 Microsoft.Crm.Asynchronous.Settings::get_MaxThreadPercentForThrottledOrganizations()
0x6822  mul
0x6823  conv.r8
0x6824  ldc.r8   100.0
0x682d  div
0x682e  conv.i4
0x682f  stfld    int32 Microsoft.Crm.Asynchronous.ThreadPoolQueueExecutionEngine::_lockedDownOrgsThreadLimit
0x6834  ldarg.0
0x6835  ldarg.0
0x6836  ldfld    int32 Microsoft.Crm.Asynchronous.ThreadPoolQueueExecutionEngine::_lockedDownOrgsThreadLimit
0x683b  brfalse.s loc_6845
0x683d  ldarg.0
0x683e  ldfld    int32 Microsoft.Crm.Asynchronous.ThreadPoolQueueExecutionEngine::_lockedDownOrgsThreadLimit
0x6843  br.s     loc_6846
0x6845  ldc.i4.1
0x6846  stfld    int32 Microsoft.Crm.Asynchronous.ThreadPoolQueueExecutionEngine::_lockedDownOrgsThreadLimit
0x684b  ldarg.0
0x684c  ldarg.0
0x684d  ldfld    int32 Microsoft.Crm.Asynchronous.ThreadPoolQueueExecutionEngine::_lockedDownOrgsThreadLimit
0x6852  ldarg.0
0x6853  ldfld    int32 Microsoft.Crm.Asynchronous.ThreadPoolQueueExecutionEngine::_lockedDownOrgsThreadLimit
0x6858  newobj   instance void [mscorlib]System.Threading.SemaphoreSlim::.ctor(int32, int32)
0x685d  stfld    class [mscorlib]System.Threading.SemaphoreSlim Microsoft.Crm.Asynchronous.ThreadPoolQueueExecutionEngine::_lockedDownOrgsSemaphore
0x6862  ldarg.0
0x6863  newobj   instance void class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Threading.SemaphoreSlim>::.ctor()
0x6868  stfld    class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Threading.SemaphoreSlim> Microsoft.Crm.Asynchronous.ThreadPoolQueueExecutionEngine::_orgThreadCountThrottler
0x686d  ldarg.0
0x686e  ldarg.2
0x686f  ldarg.0
0x6870  ldfld    class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, bool> Microsoft.Crm.Asynchronous.ThreadPoolQueueExecutionEngine::_longJobsOrgs
0x6875  ldarg.3
0x6876  ldarg.0
0x6877  ldfld    class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Threading.SemaphoreSlim> Microsoft.Crm.Asynchronous.ThreadPoolQueueExecutionEngine::_orgThreadCountThrottler
0x687c  ldarg.0
0x687d  ldfld    class [mscorlib]System.Threading.SemaphoreSlim Microsoft.Crm.Asynchronous.ThreadPoolQueueExecutionEngine::_lockedDownOrgsSemaphore
0x6882  newobj   instance void Microsoft.Crm.Asynchronous.MultiOrgQueue::.ctor(class Microsoft.Crm.Asynchronous.IQueueConfiguration configuration, class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, bool> longJobsOrgs, class Microsoft.Crm.Asynchronous.IAsyncServiceTelemetryFacade asyncServiceTelemetryFacade, class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Threading.SemaphoreSlim> orgThreadCountThrottler, class [mscorlib]System.Threading.SemaphoreSlim lockedDownOrgsSemaphore)
0x6887  stfld    class Microsoft.Crm.Asynchronous.MultiOrgQueue Microsoft.Crm.Asynchronous.ThreadPoolQueueExecutionEngine::_priorityEventQueue
0x688c  ldarg.0
0x688d  ldarg.2
0x688e  ldarg.0
0x688f  ldfld    class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, bool> Microsoft.Crm.Asynchronous.ThreadPoolQueueExecutionEngine::_longJobsOrgs
0x6894  ldarg.3
0x6895  ldarg.0
0x6896  ldfld    class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Threading.SemaphoreSlim> Microsoft.Crm.Asynchronous.ThreadPoolQueueExecutionEngine::_orgThreadCountThrottler
0x689b  ldarg.0
0x689c  ldfld    class [mscorlib]System.Threading.SemaphoreSlim Microsoft.Crm.Asynchronous.ThreadPoolQueueExecutionEngine::_lockedDownOrgsSemaphore
0x68a1  newobj   instance void Microsoft.Crm.Asynchronous.MultiOrgQueue::.ctor(class Microsoft.Crm.Asynchronous.IQueueConfiguration configuration, class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, bool> longJobsOrgs, class Microsoft.Crm.Asynchronous.IAsyncServiceTelemetryFacade asyncServiceTelemetryFacade, class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Threading.SemaphoreSlim> orgThreadCountThrottler, class [mscorlib]System.Threading.SemaphoreSlim lockedDownOrgsSemaphore)
0x68a6  stfld    class Microsoft.Crm.Asynchronous.MultiOrgQueue Microsoft.Crm.Asynchronous.ThreadPoolQueueExecutionEngine::_eventQueue
0x68ab  ldarg.1
0x68ac  ldarg.0
0x68ad  ldftn    instance void Microsoft.Crm.Asynchronous.ThreadPoolQueueExecutionEngine::JobLengthTransitionPublisher_OrgJobLengthTransitioned(object sender, class Microsoft.Crm.Asynchronous.OrgJobLengthTransitionedEventArgs e)
0x68b3  newobj   instance void class [mscorlib]System.EventHandler`1<class Microsoft.Crm.Asynchronous.OrgJobLengthTransitionedEventArgs>::.ctor(object, native int)
0x68b8  callvirt instance void Microsoft.Crm.Asynchronous.IOrgJobLengthTransitionPublisher::add_OrgJobLengthTransitioned(class [mscorlib]System.EventHandler`1<class Microsoft.Crm.Asynchronous.OrgJobLengthTransitionedEventArgs> value)
0x68bd  ldarg.0
0x68be  ldarg.1
0x68bf  callvirt instance string Microsoft.Crm.Asynchronous.IOrgJobLengthTransitionPublisher::get_Name()
0x68c4  stfld    string Microsoft.Crm.Asynchronous.ThreadPoolQueueExecutionEngine::_queueName
0x68c9  ret
```
