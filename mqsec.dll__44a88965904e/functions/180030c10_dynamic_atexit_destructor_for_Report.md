# _dynamic_atexit_destructor_for__Report__

- ea: `0x180030c10`
- end: `0x180030c27`
- name: `_dynamic_atexit_destructor_for__Report__`
- size: `23`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180030c1b`
- `KERNEL32!DeleteCriticalSection` at `0x180030c1b`

## pseudocode

```c
void dynamic_atexit_destructor_for__Report__()
{
  DeleteCriticalSection(&Report);
}

```

## disassembly

```asm
0x180030c10  sub     rsp, 28h
0x180030c14  lea     rcx, ?Report@@3VCOutputReport@@A; lpCriticalSection
0x180030c1b  call    cs:__imp_DeleteCriticalSection
0x180030c21  nop
0x180030c22  add     rsp, 28h
0x180030c26  retn
```
