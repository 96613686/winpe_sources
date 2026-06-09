# Microsoft.Crm.Asynchronous.AsyncService::get_Configuration

- ea: `0xc70`
- end: `0xc77`
- name: `Microsoft.Crm.Asynchronous.AsyncService::get_Configuration`
- size: `7`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0xe0`
- `0x180`
- `0x620`
- `0x18d0`

## pseudocode

```c

```

## disassembly

```asm
0xc70  ldarg.0
0xc71  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IConfiguration Microsoft.Crm.Asynchronous.AsyncService::_config
0xc76  ret
```
