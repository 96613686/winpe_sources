# _dynamic_atexit_destructor_for__g_csCallback__

- ea: `0x180028390`
- end: `0x1800283a7`
- name: `_dynamic_atexit_destructor_for__g_csCallback__`
- size: `23`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18002839b`
- `KERNEL32!DeleteCriticalSection` at `0x18002839b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void dynamic_atexit_destructor_for__g_csCallback__()
{
  DeleteCriticalSection(&g_csCallback);
}

```

## disassembly

```asm
0x180028390  sub     rsp, 28h
0x180028394  lea     rcx, ?g_csCallback@@3VCCriticalSection@@A; lpCriticalSection
0x18002839b  call    cs:__imp_DeleteCriticalSection
0x1800283a1  nop
0x1800283a2  add     rsp, 28h
0x1800283a6  retn
```
