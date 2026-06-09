# _dynamic_atexit_destructor_for__g_childCountAccessLock__

- ea: `0x140016290`
- end: `0x14001629e`
- name: `_dynamic_atexit_destructor_for__g_childCountAccessLock__`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140016297`

## pseudocode

```c
void dynamic_atexit_destructor_for__g_childCountAccessLock__()
{
  DeleteCriticalSection(&stru_140024310);
}

```

## disassembly

```asm
0x140016290  lea     rcx, stru_140024310
0x140016297  jmp     cs:__imp_DeleteCriticalSection
```
