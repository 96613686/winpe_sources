# _dynamic_atexit_destructor_for__s_LocalMachineSidCS__

- ea: `0x180030d10`
- end: `0x180030d27`
- name: `_dynamic_atexit_destructor_for__s_LocalMachineSidCS__`
- size: `23`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, broker_com_uri`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180030d1b`
- `KERNEL32!DeleteCriticalSection` at `0x180030d1b`

## pseudocode

```c
void dynamic_atexit_destructor_for__s_LocalMachineSidCS__()
{
  DeleteCriticalSection(&stru_180042DC0);
}

```

## disassembly

```asm
0x180030d10  sub     rsp, 28h
0x180030d14  lea     rcx, stru_180042DC0; lpCriticalSection
0x180030d1b  call    cs:__imp_DeleteCriticalSection
0x180030d21  nop
0x180030d22  add     rsp, 28h
0x180030d26  retn
```
