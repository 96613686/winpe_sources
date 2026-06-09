# _dynamic_atexit_destructor_for__g_CriticalSection__

- ea: `0x1004f240`
- end: `0x1004f24c`
- name: `_dynamic_atexit_destructor_for__g_CriticalSection__`
- size: `12`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1004f245`
- `KERNEL32!DeleteCriticalSection` at `0x1004f245`

## pseudocode

```c
void __cdecl dynamic_atexit_destructor_for__g_CriticalSection__()
{
  DeleteCriticalSection(&g_CriticalSection);
}

```

## disassembly

```asm
0x1004f240  push    offset ?g_CriticalSection@@3VCriticalSection@@A; lpCriticalSection
0x1004f245  call    ds:__imp__DeleteCriticalSection@4; DeleteCriticalSection(x)
0x1004f24b  retn
```
