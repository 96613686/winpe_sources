# _dynamic_atexit_destructor_for__s_csServerCredHandle__

- ea: `0x180030c80`
- end: `0x180030c97`
- name: `_dynamic_atexit_destructor_for__s_csServerCredHandle__`
- size: `23`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180030c8b`
- `KERNEL32!DeleteCriticalSection` at `0x180030c8b`

## pseudocode

```c
void dynamic_atexit_destructor_for__s_csServerCredHandle__()
{
  DeleteCriticalSection(&stru_180042D38);
}

```

## disassembly

```asm
0x180030c80  sub     rsp, 28h
0x180030c84  lea     rcx, stru_180042D38; lpCriticalSection
0x180030c8b  call    cs:__imp_DeleteCriticalSection
0x180030c91  nop
0x180030c92  add     rsp, 28h
0x180030c96  retn
```
