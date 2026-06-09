# _dynamic_atexit_destructor_for__s_csInitProviderTable__

- ea: `0x180030da0`
- end: `0x180030db7`
- name: `_dynamic_atexit_destructor_for__s_csInitProviderTable__`
- size: `23`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180030dab`
- `KERNEL32!DeleteCriticalSection` at `0x180030dab`

## pseudocode

```c
void dynamic_atexit_destructor_for__s_csInitProviderTable__()
{
  DeleteCriticalSection(&stru_180042E10);
}

```

## disassembly

```asm
0x180030da0  sub     rsp, 28h
0x180030da4  lea     rcx, stru_180042E10; lpCriticalSection
0x180030dab  call    cs:__imp_DeleteCriticalSection
0x180030db1  nop
0x180030db2  add     rsp, 28h
0x180030db6  retn
```
