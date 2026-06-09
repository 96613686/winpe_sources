# _dynamic_atexit_destructor_for__s_DTC_CS__

- ea: `0x180030a90`
- end: `0x180030aa7`
- name: `_dynamic_atexit_destructor_for__s_DTC_CS__`
- size: `23`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180030a9b`
- `KERNEL32!DeleteCriticalSection` at `0x180030a9b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void dynamic_atexit_destructor_for__s_DTC_CS__()
{
  DeleteCriticalSection(&stru_180042510);
}

```

## disassembly

```asm
0x180030a90  sub     rsp, 28h
0x180030a94  lea     rcx, stru_180042510; lpCriticalSection
0x180030a9b  call    cs:__imp_DeleteCriticalSection
0x180030aa1  nop
0x180030aa2  add     rsp, 28h
0x180030aa6  retn
```
