# _dynamic_atexit_destructor_for__g_csInitFreeGlobals__

- ea: `0x1800238f0`
- end: `0x1800238fe`
- name: `_dynamic_atexit_destructor_for__g_csInitFreeGlobals__`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1800238f7`

## pseudocode

```c
void dynamic_atexit_destructor_for__g_csInitFreeGlobals__()
{
  DeleteCriticalSection(&g_csInitFreeGlobals);
}

```

## disassembly

```asm
0x1800238f0  lea     rcx, ?g_csInitFreeGlobals@@3VCCritSecHolder@@A; CCritSecHolder g_csInitFreeGlobals
0x1800238f7  jmp     cs:__imp_DeleteCriticalSection
```
