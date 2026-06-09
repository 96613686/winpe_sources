# Microsoft.Crm.Sandbox.PluginTraceLogQueuesProcessor::.ctor

- ea: `0x6610`
- end: `0x664b`
- name: `Microsoft.Crm.Sandbox.PluginTraceLogQueuesProcessor::.ctor`
- size: `59`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1930`

## callees

- `0x6960`
- `0x69b0`
- `0x69e0`

## pseudocode

```c

```

## disassembly

```asm
0x6610  ldarg.0
0x6611  newobj   instance void Microsoft.Crm.Sandbox.RoundRobinIterator::.ctor()
0x6616  stfld    class Microsoft.Crm.Sandbox.RoundRobinIterator Microsoft.Crm.Sandbox.PluginTraceLogQueuesProcessor::_queueIterator
0x661b  ldarg.0
0x661c  ldc.i4.8
0x661d  ldc.i4.s 0xB
0x661f  newobj   instance void class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Concurrent.ConcurrentQueue`1<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.PluginTraceLogRecord>>::.ctor(int32, int32)
0x6624  stfld    class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Concurrent.ConcurrentQueue`1<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.PluginTraceLogRecord>> Microsoft.Crm.Sandbox.PluginTraceLogQueuesProcessor::_queues
0x6629  ldarg.0
0x662a  call     instance void [mscorlib]System.Object::.ctor()
0x662f  ldarg.0
0x6630  ldarg.1
0x6631  stfld    class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Concurrent.ConcurrentQueue`1<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.PluginTraceLogRecord>> Microsoft.Crm.Sandbox.PluginTraceLogQueuesProcessor::_queues
0x6636  ldarg.0
0x6637  ldarg.2
0x6638  call     int32 Microsoft.Crm.Sandbox.PluginTraceLogQueuesProcessor::get_PluginTraceLogMaxQueueSizeBeforeStoppingRetries()
0x663d  clt
0x663f  stfld    bool Microsoft.Crm.Sandbox.PluginTraceLogQueuesProcessor::_retryWhileProcessingQueues
0x6644  ldarg.0
0x6645  call     instance void Microsoft.Crm.Sandbox.PluginTraceLogQueuesProcessor::InitializeOrgArray()
0x664a  ret
```
