# _dynamic_atexit_destructor_for__s_WhereaboutsCS__

- ea: `0x180030ab0`
- end: `0x180030ac7`
- name: `_dynamic_atexit_destructor_for__s_WhereaboutsCS__`
- size: `23`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180030abb`
- `KERNEL32!DeleteCriticalSection` at `0x180030abb`

## pseudocode

```c
void dynamic_atexit_destructor_for__s_WhereaboutsCS__()
{
  DeleteCriticalSection(&CriticalSection);
}

```

## disassembly

```asm
0x180030ab0  sub     rsp, 28h
0x180030ab4  lea     rcx, CriticalSection; lpCriticalSection
0x180030abb  call    cs:__imp_DeleteCriticalSection
0x180030ac1  nop
0x180030ac2  add     rsp, 28h
0x180030ac6  retn
```
