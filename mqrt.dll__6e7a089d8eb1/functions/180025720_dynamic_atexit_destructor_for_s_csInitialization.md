# _dynamic_atexit_destructor_for__s_csInitialization__

- ea: `0x180025720`
- end: `0x180025737`
- name: `_dynamic_atexit_destructor_for__s_csInitialization__`
- size: `23`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18002572b`
- `KERNEL32!DeleteCriticalSection` at `0x18002572b`

## pseudocode

```c
void dynamic_atexit_destructor_for__s_csInitialization__()
{
  DeleteCriticalSection(&s_csInitialization);
}

```

## disassembly

```asm
0x180025720  sub     rsp, 28h
0x180025724  lea     rcx, ?s_csInitialization@@3VCCriticalSection@@A; lpCriticalSection
0x18002572b  call    cs:__imp_DeleteCriticalSection
0x180025731  nop
0x180025732  add     rsp, 28h
0x180025736  retn
```
