# _dynamic_atexit_destructor_for__g_hServicePaused__

- ea: `0x14001f210`
- end: `0x14001f21c`
- name: `_dynamic_atexit_destructor_for__g_hServicePaused__`
- size: `12`
- prototype: `void()`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x140005e20`

## pseudocode

```c
void dynamic_atexit_destructor_for__g_hServicePaused__()
{
  CHandle::~CHandle(&g_hServicePaused);
}

```

## disassembly

```asm
0x14001f210  lea     rcx, ?g_hServicePaused@@3VCHandle@@A; this
0x14001f217  jmp     ??1CHandle@@QEAA@XZ; CHandle::~CHandle(void)
```
