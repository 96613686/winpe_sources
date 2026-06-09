# Microsoft.Crm.Asynchronous.AsyncService::get_ErrorHandler

- ea: `0xcb0`
- end: `0xcb7`
- name: `Microsoft.Crm.Asynchronous.AsyncService::get_ErrorHandler`
- size: `7`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0xe0`
- `0x180`

## pseudocode

```c

```

## disassembly

```asm
0xcb0  ldarg.0
0xcb1  ldfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.ErrorHandler Microsoft.Crm.Asynchronous.AsyncService::_errorHandler
0xcb6  ret
```
