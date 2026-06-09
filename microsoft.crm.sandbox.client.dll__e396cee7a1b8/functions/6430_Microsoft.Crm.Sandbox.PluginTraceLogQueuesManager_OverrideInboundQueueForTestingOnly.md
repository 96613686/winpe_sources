# Microsoft.Crm.Sandbox.PluginTraceLogQueuesManager::OverrideInboundQueueForTestingOnly

- ea: `0x6430`
- end: `0x643b`
- name: `Microsoft.Crm.Sandbox.PluginTraceLogQueuesManager::OverrideInboundQueueForTestingOnly`
- size: `11`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x6430`

## pseudocode

```c

```

## disassembly

```asm
0x6430  ldarg.1
0x6431  brfalse.s loc_643A
0x6433  ldarg.0
0x6434  ldarg.1
0x6435  stfld    class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Concurrent.ConcurrentQueue`1<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.PluginTraceLogRecord>> Microsoft.Crm.Sandbox.PluginTraceLogQueuesManager::_inboundQueues
0x643a  ret
```
