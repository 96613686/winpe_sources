# _dynamic_atexit_destructor_for__s_WhereaboutsCS__

- ea: `0x1800256c0`
- end: `0x1800256d7`
- name: `_dynamic_atexit_destructor_for__s_WhereaboutsCS__`
- size: `23`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1800256cb`
- `KERNEL32!DeleteCriticalSection` at `0x1800256cb`

## pseudocode

```c
void dynamic_atexit_destructor_for__s_WhereaboutsCS__()
{
  DeleteCriticalSection(&stru_18003D290);
}

```

## disassembly

```asm
0x1800256c0  sub     rsp, 28h
0x1800256c4  lea     rcx, stru_18003D290; lpCriticalSection
0x1800256cb  call    cs:__imp_DeleteCriticalSection
0x1800256d1  nop
0x1800256d2  add     rsp, 28h
0x1800256d6  retn
```
