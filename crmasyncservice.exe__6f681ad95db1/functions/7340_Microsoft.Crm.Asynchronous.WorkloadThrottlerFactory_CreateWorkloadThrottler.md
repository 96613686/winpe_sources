# Microsoft.Crm.Asynchronous.WorkloadThrottlerFactory::CreateWorkloadThrottler

- ea: `0x7340`
- end: `0x73ec`
- name: `Microsoft.Crm.Asynchronous.WorkloadThrottlerFactory::CreateWorkloadThrottler`
- size: `172`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x5da0`
- `0x5ea0`
- `0x7340`

## pseudocode

```c

```

## disassembly

```asm
0x7340  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x7345  ldstr    a01Onselect// "{0}_{1}_OnSelect"
0x734a  ldc.i4.2
0x734b  newarr   [mscorlib]System.Object
0x7350  dup
0x7351  ldc.i4.0
0x7352  ldarg.2
0x7353  stelem.ref
0x7354  dup
0x7355  ldc.i4.1
0x7356  ldarg.1
0x7357  stelem.ref
0x7358  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x735d  stloc.0
0x735e  ldarg.1
0x735f  ldstr    aActivityqueue// "ActivityQueue"
0x7364  call     bool [mscorlib]System.String::op_Equality(string, string)
0x7369  brtrue.s loc_7394
0x736b  ldarg.1
0x736c  ldstr    aMailboxqueue// "MailboxQueue"
0x7371  call     bool [mscorlib]System.String::op_Equality(string, string)
0x7376  brtrue.s loc_7394
0x7378  ldarg.1
0x7379  ldstr    aAsyncoperation// "AsyncOperationQueue"
0x737e  call     bool [mscorlib]System.String::op_Equality(string, string)
0x7383  brtrue.s loc_73A3
0x7385  ldarg.1
0x7386  ldstr    aPriorityasynco// "PriorityAsyncOperationQueue"
0x738b  call     bool [mscorlib]System.String::op_Equality(string, string)
0x7390  brtrue.s loc_73CE
0x7392  br.s     loc_73DD
0x7394  ldloc.0
0x7395  ldarg.3
0x7396  ldarg.s  4
0x7398  ldarg.s  5
0x739a  ldarg.s  6
0x739c  ldarg.1
0x739d  newobj   instance void Microsoft.Crm.Asynchronous.OutstandingOperationAwareWorkloadThrottler::.ctor(string name, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.ISynchronousQueueConfiguration configuration, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperationsFactory operationsFactory, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IQueuePerformanceCounters counters, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AcceptWork acceptWorkHandler, string queueName)
0x73a2  ret
0x73a3  ldarg.3
0x73a4  castclass [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncOperationQueueConfiguration
0x73a9  callvirt instance bool [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncOperationQueueConfiguration::get_UseDefaultWorkloadThrottler()
0x73ae  brfalse.s loc_73BF
0x73b0  ldloc.0
0x73b1  ldarg.3
0x73b2  ldarg.s  4
0x73b4  ldarg.s  5
0x73b6  ldarg.s  6
0x73b8  ldarg.1
0x73b9  newobj   instance void Microsoft.Crm.Asynchronous.DefaultWorkloadThrottler::.ctor(string name, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.ISynchronousQueueConfiguration configuration, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperationsFactory operationsFactory, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IQueuePerformanceCounters counters, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AcceptWork acceptWorkHandler, string queueName)
0x73be  ret
0x73bf  ldloc.0
0x73c0  ldarg.3
0x73c1  ldarg.s  4
0x73c3  ldarg.s  5
0x73c5  ldarg.s  6
0x73c7  ldarg.1
0x73c8  newobj   instance void Microsoft.Crm.Asynchronous.OutstandingOperationAwareWorkloadThrottler::.ctor(string name, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.ISynchronousQueueConfiguration configuration, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperationsFactory operationsFactory, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IQueuePerformanceCounters counters, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AcceptWork acceptWorkHandler, string queueName)
0x73cd  ret
0x73ce  ldloc.0
0x73cf  ldarg.3
0x73d0  ldarg.s  4
0x73d2  ldarg.s  5
0x73d4  ldarg.s  6
0x73d6  ldarg.1
0x73d7  newobj   instance void Microsoft.Crm.Asynchronous.OutstandingOperationAwareWorkloadThrottler::.ctor(string name, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.ISynchronousQueueConfiguration configuration, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperationsFactory operationsFactory, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IQueuePerformanceCounters counters, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AcceptWork acceptWorkHandler, string queueName)
0x73dc  ret
0x73dd  ldloc.0
0x73de  ldarg.3
0x73df  ldarg.s  4
0x73e1  ldarg.s  5
0x73e3  ldarg.s  6
0x73e5  ldarg.1
0x73e6  newobj   instance void Microsoft.Crm.Asynchronous.DefaultWorkloadThrottler::.ctor(string name, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.ISynchronousQueueConfiguration configuration, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperationsFactory operationsFactory, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IQueuePerformanceCounters counters, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AcceptWork acceptWorkHandler, string queueName)
0x73eb  ret
```
