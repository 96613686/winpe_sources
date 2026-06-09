# _dynamic_atexit_destructor_for__g_serviceCallbacks__

- ea: `0x18000ce30`
- end: `0x18000ce3c`
- name: `_dynamic_atexit_destructor_for__g_serviceCallbacks__`
- size: `12`
- prototype: `void()`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000a3e4`

## pseudocode

```c
void dynamic_atexit_destructor_for__g_serviceCallbacks__()
{
  ServiceCallbacks::~ServiceCallbacks((ServiceCallbacks *)off_1800180A0);
}

```

## disassembly

```asm
0x18000ce30  lea     rcx, off_1800180A0; this
0x18000ce37  jmp     ??1ServiceCallbacks@@QEAA@XZ; ServiceCallbacks::~ServiceCallbacks(void)
```
