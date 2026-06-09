# _dynamic_atexit_destructor_for__s_csIsDC__

- ea: `0x180030d50`
- end: `0x180030d67`
- name: `_dynamic_atexit_destructor_for__s_csIsDC__`
- size: `23`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180030d5b`
- `KERNEL32!DeleteCriticalSection` at `0x180030d5b`

## pseudocode

```c
void dynamic_atexit_destructor_for__s_csIsDC__()
{
  DeleteCriticalSection(&stru_180042DE8);
}

```

## disassembly

```asm
0x180030d50  sub     rsp, 28h
0x180030d54  lea     rcx, stru_180042DE8; lpCriticalSection
0x180030d5b  call    cs:__imp_DeleteCriticalSection
0x180030d61  nop
0x180030d62  add     rsp, 28h
0x180030d66  retn
```
