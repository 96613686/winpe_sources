# _dynamic_atexit_destructor_for__g_csWeirdLoadLibraryWorkaround__

- ea: `0x1800283d0`
- end: `0x1800283e7`
- name: `_dynamic_atexit_destructor_for__g_csWeirdLoadLibraryWorkaround__`
- size: `23`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1800283db`
- `KERNEL32!DeleteCriticalSection` at `0x1800283db`

## pseudocode

```c
void dynamic_atexit_destructor_for__g_csWeirdLoadLibraryWorkaround__()
{
  DeleteCriticalSection(&g_csWeirdLoadLibraryWorkaround);
}

```

## disassembly

```asm
0x1800283d0  sub     rsp, 28h
0x1800283d4  lea     rcx, ?g_csWeirdLoadLibraryWorkaround@@3VCCriticalSection@@A; lpCriticalSection
0x1800283db  call    cs:__imp_DeleteCriticalSection
0x1800283e1  nop
0x1800283e2  add     rsp, 28h
0x1800283e6  retn
```
