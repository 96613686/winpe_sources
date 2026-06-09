# _dynamic_atexit_destructor_for__g_CS_InitService__

- ea: `0x1800093b0`
- end: `0x1800093be`
- name: `_dynamic_atexit_destructor_for__g_CS_InitService__`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800093b7`

## pseudocode

```c
void dynamic_atexit_destructor_for__g_CS_InitService__()
{
  DeleteCriticalSection(&g_CS_InitService);
}

```

## disassembly

```asm
0x1800093b0  lea     rcx, ?g_CS_InitService@@3VCriticalSection@@A; CriticalSection g_CS_InitService
0x1800093b7  jmp     cs:__imp_DeleteCriticalSection
```
