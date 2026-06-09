# Microsoft.Crm.Sandbox.PluginTraceLogQueuesManager::.ctor

- ea: `0x6400`
- end: `0x6415`
- name: `Microsoft.Crm.Sandbox.PluginTraceLogQueuesManager::.ctor`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x65e0`

## pseudocode

```c

```

## disassembly

```asm
0x6400  ldarg.0
0x6401  ldc.i4.8
0x6402  ldc.i4.s 0xB
0x6404  newobj   instance void class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Concurrent.ConcurrentQueue`1<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.PluginTraceLogRecord>>::.ctor(int32, int32)
0x6409  stfld    class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Concurrent.ConcurrentQueue`1<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.PluginTraceLogRecord>> Microsoft.Crm.Sandbox.PluginTraceLogQueuesManager::_inboundQueues
0x640e  ldarg.0
0x640f  call     instance void [mscorlib]System.Object::.ctor()
0x6414  ret
```
