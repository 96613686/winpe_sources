# _dynamic_atexit_destructor_for__s_csGuestSid__

- ea: `0x180030d30`
- end: `0x180030d47`
- name: `_dynamic_atexit_destructor_for__s_csGuestSid__`
- size: `23`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, broker_com_uri`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180030d3b`
- `KERNEL32!DeleteCriticalSection` at `0x180030d3b`

## pseudocode

```c
void dynamic_atexit_destructor_for__s_csGuestSid__()
{
  DeleteCriticalSection(&stru_180042D98);
}

```

## disassembly

```asm
0x180030d30  sub     rsp, 28h
0x180030d34  lea     rcx, stru_180042D98; lpCriticalSection
0x180030d3b  call    cs:__imp_DeleteCriticalSection
0x180030d41  nop
0x180030d42  add     rsp, 28h
0x180030d46  retn
```
