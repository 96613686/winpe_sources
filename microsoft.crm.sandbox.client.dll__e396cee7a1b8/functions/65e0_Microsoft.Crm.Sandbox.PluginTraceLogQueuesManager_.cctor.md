# Microsoft.Crm.Sandbox.PluginTraceLogQueuesManager::.cctor

- ea: `0x65e0`
- end: `0x65f1`
- name: `Microsoft.Crm.Sandbox.PluginTraceLogQueuesManager::.cctor`
- size: `17`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x6400`

## pseudocode

```c

```

## disassembly

```asm
0x65e0  ldc.i4.0
0x65e1  stsfld   int32 Microsoft.Crm.Sandbox.PluginTraceLogQueuesManager::_totalInboundQueueRecordCount
0x65e6  newobj   instance void Microsoft.Crm.Sandbox.PluginTraceLogQueuesManager::.ctor()
0x65eb  stsfld   class Microsoft.Crm.Sandbox.IPluginTraceLogQueuesManager Microsoft.Crm.Sandbox.PluginTraceLogQueuesManager::_instance
0x65f0  ret
```
