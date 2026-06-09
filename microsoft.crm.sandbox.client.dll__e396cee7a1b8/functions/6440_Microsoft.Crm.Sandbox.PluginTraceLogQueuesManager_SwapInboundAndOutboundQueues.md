# Microsoft.Crm.Sandbox.PluginTraceLogQueuesManager::SwapInboundAndOutboundQueues

- ea: `0x6440`
- end: `0x6470`
- name: `Microsoft.Crm.Sandbox.PluginTraceLogQueuesManager::SwapInboundAndOutboundQueues`
- size: `48`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x6440  ldc.i4.8
0x6441  ldc.i4.s 0xB
0x6443  newobj   instance void class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Concurrent.ConcurrentQueue`1<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.PluginTraceLogRecord>>::.ctor(int32, int32)
0x6448  stloc.0
0x6449  ldsfld   int32 Microsoft.Crm.Sandbox.PluginTraceLogQueuesManager::_totalInboundQueueRecordCount
0x644e  stloc.1
0x644f  ldarg.0
0x6450  ldflda   class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Concurrent.ConcurrentQueue`1<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.PluginTraceLogRecord>> Microsoft.Crm.Sandbox.PluginTraceLogQueuesManager::_inboundQueues
0x6455  ldloc.0
0x6456  call     T0x2B000013
0x645b  stloc.0
0x645c  ldsflda  int32 Microsoft.Crm.Sandbox.PluginTraceLogQueuesManager::_totalInboundQueueRecordCount
0x6461  ldc.i4.0
0x6462  call     int32 [mscorlib]System.Threading.Interlocked::Exchange(int32&, int32)
0x6467  pop
0x6468  ldloc.0
0x6469  ldloc.1
0x646a  newobj   instance void class [mscorlib]System.Tuple`2<class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Concurrent.ConcurrentQueue`1<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.PluginTraceLogRecord>>, int32>::.ctor(var<u1>, !!T0)
0x646f  ret
```
