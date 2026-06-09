# _dynamic_atexit_destructor_for__s_csInitialization__

- ea: `0x180030dc0`
- end: `0x180030dd7`
- name: `_dynamic_atexit_destructor_for__s_csInitialization__`
- size: `23`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180030dcb`
- `KERNEL32!DeleteCriticalSection` at `0x180030dcb`

## pseudocode

```c
void dynamic_atexit_destructor_for__s_csInitialization__()
{
  DeleteCriticalSection(&s_csInitialization);
}

```

## disassembly

```asm
0x180030dc0  sub     rsp, 28h
0x180030dc4  lea     rcx, ?s_csInitialization@@3VCCriticalSection@@A; lpCriticalSection
0x180030dcb  call    cs:__imp_DeleteCriticalSection
0x180030dd1  nop
0x180030dd2  add     rsp, 28h
0x180030dd6  retn
```
