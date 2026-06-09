# _dynamic_atexit_destructor_for__g_cs__

- ea: `0x1800148f0`
- end: `0x1800148fe`
- name: `_dynamic_atexit_destructor_for__g_cs__`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800148f7`

## pseudocode

```c
void dynamic_atexit_destructor_for__g_cs__()
{
  DeleteCriticalSection((LPCRITICAL_SECTION)qword_18001D860);
}

```

## disassembly

```asm
0x1800148f0  lea     rcx, qword_18001D860
0x1800148f7  jmp     cs:__imp_DeleteCriticalSection
```
