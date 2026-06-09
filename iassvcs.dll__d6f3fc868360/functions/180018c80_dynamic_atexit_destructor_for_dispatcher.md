# _dynamic_atexit_destructor_for__dispatcher__

- ea: `0x180018c80`
- end: `0x180018c8e`
- name: `_dynamic_atexit_destructor_for__dispatcher__`
- size: `14`
- prototype: `void()`
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180018c87`

## pseudocode

```c
void dynamic_atexit_destructor_for__dispatcher__()
{
  DeleteCriticalSection(&dispatcher);
}

```

## disassembly

```asm
0x180018c80  lea     rcx, ?dispatcher@@3VDispatcher@@A; Dispatcher dispatcher
0x180018c87  jmp     cs:__imp_DeleteCriticalSection
```
