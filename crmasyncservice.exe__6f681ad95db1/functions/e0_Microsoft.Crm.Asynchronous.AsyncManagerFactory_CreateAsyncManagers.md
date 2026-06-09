# Microsoft.Crm.Asynchronous.AsyncManagerFactory::CreateAsyncManagers

- ea: `0xe0`
- end: `0x17c`
- name: `Microsoft.Crm.Asynchronous.AsyncManagerFactory::CreateAsyncManagers`
- size: `156`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0xe0`
- `0x180`
- `0xc40`
- `0xc70`
- `0xca0`
- `0xcb0`
- `0xcc0`
- `0x1910`
- `0x21b0`
- `0x40b0`

## pseudocode

```c

```

## disassembly

```asm
0xe0  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncManager>::.ctor()
0xe5  stloc.0
0xe6  ldarg.0
0xe7  ldfld    class Microsoft.Crm.Asynchronous.AsyncService Microsoft.Crm.Asynchronous.AsyncManagerFactory::_asyncService
0xec  callvirt instance valuetype [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncServiceContext Microsoft.Crm.Asynchronous.AsyncService::get_Context()
0xf1  stloc.1
0xf2  ldloc.1
0xf3  switch   loc_168, loc_10A, loc_17A, loc_168
0x108  br.s     loc_17A
0x10a  ldloc.0
0x10b  ldarg.0
0x10c  ldfld    class Microsoft.Crm.Asynchronous.AsyncService Microsoft.Crm.Asynchronous.AsyncManagerFactory::_asyncService
0x111  callvirt instance string [System.ServiceProcess]System.ServiceProcess.ServiceBase::get_ServiceName()
0x116  ldarg.0
0x117  ldfld    class Microsoft.Crm.Asynchronous.AsyncService Microsoft.Crm.Asynchronous.AsyncManagerFactory::_asyncService
0x11c  callvirt instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperationsFactory Microsoft.Crm.Asynchronous.AsyncService::get_OperationsFactory()
0x121  ldarg.0
0x122  ldfld    class Microsoft.Crm.Asynchronous.AsyncService Microsoft.Crm.Asynchronous.AsyncManagerFactory::_asyncService
0x127  callvirt instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncServicePerformanceCounters Microsoft.Crm.Asynchronous.AsyncService::get_PerformanceCounters()
0x12c  ldstr    aAsyncoperation// "AsyncOperationQueue"
0x131  callvirt instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IQueuePerformanceCounters [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncServicePerformanceCounters::GetQueuePerformanceCounters(string)
0x136  ldarg.0
0x137  ldfld    class Microsoft.Crm.Asynchronous.AsyncService Microsoft.Crm.Asynchronous.AsyncManagerFactory::_asyncService
0x13c  callvirt instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IConfiguration Microsoft.Crm.Asynchronous.AsyncService::get_Configuration()
0x141  newobj   instance void Microsoft.Crm.Asynchronous.JobDataAccessFactory::.ctor()
0x146  ldarg.0
0x147  ldfld    class Microsoft.Crm.Asynchronous.AsyncService Microsoft.Crm.Asynchronous.AsyncManagerFactory::_asyncService
0x14c  callvirt instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.ErrorHandler Microsoft.Crm.Asynchronous.AsyncService::get_ErrorHandler()
0x151  ldarg.0
0x152  ldfld    class Microsoft.Crm.Asynchronous.AsyncService Microsoft.Crm.Asynchronous.AsyncManagerFactory::_asyncService
0x157  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ICrmEventLog Microsoft.Crm.Asynchronous.AsyncService::get_CrmEventLog()
0x15c  newobj   instance void Microsoft.Crm.Asynchronous.JobManager::.ctor(string instanceName, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperationsFactory operationsFactory, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IQueuePerformanceCounters counters, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IJobConfiguration config, class Microsoft.Crm.Asynchronous.IJobDataAccessFactory dataAccessFactory, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.ErrorHandler errorHandler, class [Microsoft.Crm.Core]Microsoft.Crm.ICrmEventLog eventLog)
0x161  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncManager>::Add(var<u1>)
0x166  br.s     loc_17A
0x168  ldarg.0
0x169  ldloc.0
0x16a  ldarg.0
0x16b  ldfld    class Microsoft.Crm.Asynchronous.AsyncService Microsoft.Crm.Asynchronous.AsyncManagerFactory::_asyncService
0x170  callvirt instance valuetype [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncServiceContext Microsoft.Crm.Asynchronous.AsyncService::get_Context()
0x175  call     instance void Microsoft.Crm.Asynchronous.AsyncManagerFactory::AddAsyncManagersForServer(class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncManager> asyncManagers, valuetype [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncServiceContext context)
0x17a  ldloc.0
0x17b  ret
```
