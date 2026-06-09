# _dynamic_atexit_destructor_for__g_cServiceStatus__

- ea: `0x140009a20`
- end: `0x140009a2e`
- name: `_dynamic_atexit_destructor_for__g_cServiceStatus__`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x140009a27`

## pseudocode

```c
void dynamic_atexit_destructor_for__g_cServiceStatus__()
{
  DeleteCriticalSection(&g_cServiceStatus);
}

```

## disassembly

```asm
0x140009a20  lea     rcx, ?g_cServiceStatus@@3VServiceStatus@@A; ServiceStatus g_cServiceStatus
0x140009a27  jmp     cs:__imp_DeleteCriticalSection
```
