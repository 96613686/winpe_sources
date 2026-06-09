# Microsoft.Crm.Asynchronous.JobManager::get_Configuration

- ea: `0x4a50`
- end: `0x4a57`
- name: `Microsoft.Crm.Asynchronous.JobManager::get_Configuration`
- size: `7`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## callers

- `0x2dc0`
- `0x3290`

## pseudocode

```c

```

## disassembly

```asm
0x4a50  ldarg.0
0x4a51  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IJobConfiguration Microsoft.Crm.Asynchronous.JobManager::_config
0x4a56  ret
```
