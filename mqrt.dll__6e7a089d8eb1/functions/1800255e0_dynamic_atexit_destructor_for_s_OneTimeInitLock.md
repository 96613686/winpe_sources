# _dynamic_atexit_destructor_for__s_OneTimeInitLock__

- ea: `0x1800255e0`
- end: `0x1800255f7`
- name: `_dynamic_atexit_destructor_for__s_OneTimeInitLock__`
- size: `23`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1800255eb`
- `KERNEL32!DeleteCriticalSection` at `0x1800255eb`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void dynamic_atexit_destructor_for__s_OneTimeInitLock__()
{
  DeleteCriticalSection(&stru_18003D1C8);
}

```

## disassembly

```asm
0x1800255e0  sub     rsp, 28h
0x1800255e4  lea     rcx, stru_18003D1C8; lpCriticalSection
0x1800255eb  call    cs:__imp_DeleteCriticalSection
0x1800255f1  nop
0x1800255f2  add     rsp, 28h
0x1800255f6  retn
```
