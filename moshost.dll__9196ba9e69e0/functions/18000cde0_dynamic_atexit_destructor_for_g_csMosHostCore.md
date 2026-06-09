# _dynamic_atexit_destructor_for__g_csMosHostCore__

- ea: `0x18000cde0`
- end: `0x18000cdee`
- name: `_dynamic_atexit_destructor_for__g_csMosHostCore__`
- size: `14`
- prototype: `void()`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000cde7`

## pseudocode

```c
void dynamic_atexit_destructor_for__g_csMosHostCore__()
{
  DeleteCriticalSection(&stru_1800186B0);
}

```

## disassembly

```asm
0x18000cde0  lea     rcx, stru_1800186B0
0x18000cde7  jmp     cs:__imp_DeleteCriticalSection
```
