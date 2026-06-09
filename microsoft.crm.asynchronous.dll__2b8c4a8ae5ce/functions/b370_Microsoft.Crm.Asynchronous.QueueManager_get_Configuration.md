# Microsoft.Crm.Asynchronous.QueueManager::get_Configuration

- ea: `0xb370`
- end: `0xb377`
- name: `Microsoft.Crm.Asynchronous.QueueManager::get_Configuration`
- size: `7`
- prototype: ``
- caller_count: `15`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## callers

- `0x36b0`
- `0x4ce0`
- `0x61a0`
- `0x8770`
- `0x9540`
- `0x9620`
- `0x9680`
- `0x9a80`
- `0x9e40`
- `0xac60`
- `0xad30`
- `0xec40`
- `0x10260`
- `0x103c0`
- `0x10450`

## pseudocode

```c

```

## disassembly

```asm
0xb370  ldarg.0
0xb371  ldfld    class Microsoft.Crm.Asynchronous.IQueueConfiguration Microsoft.Crm.Asynchronous.QueueManager::_config
0xb376  ret
```
