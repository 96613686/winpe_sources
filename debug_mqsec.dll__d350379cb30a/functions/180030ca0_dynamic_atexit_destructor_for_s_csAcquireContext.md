# _dynamic_atexit_destructor_for__s_csAcquireContext__

- ea: `0x180030ca0`
- end: `0x180030cb7`
- name: `_dynamic_atexit_destructor_for__s_csAcquireContext__`
- size: `23`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180030cab`
- `KERNEL32!DeleteCriticalSection` at `0x180030cab`

## pseudocode

```c
void dynamic_atexit_destructor_for__s_csAcquireContext__()
{
  DeleteCriticalSection(&stru_180042D60);
}

```

## disassembly

```asm
0x180030ca0  sub     rsp, 28h
0x180030ca4  lea     rcx, stru_180042D60; lpCriticalSection
0x180030cab  call    cs:__imp_DeleteCriticalSection
0x180030cb1  nop
0x180030cb2  add     rsp, 28h
0x180030cb6  retn
```
