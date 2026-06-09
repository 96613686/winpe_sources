# _dynamic_atexit_destructor_for__g_csGetDtcDispenser__

- ea: `0x1800283f0`
- end: `0x180028407`
- name: `_dynamic_atexit_destructor_for__g_csGetDtcDispenser__`
- size: `23`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1800283fb`
- `KERNEL32!DeleteCriticalSection` at `0x1800283fb`

## pseudocode

```c
void dynamic_atexit_destructor_for__g_csGetDtcDispenser__()
{
  DeleteCriticalSection(&g_csGetDtcDispenser);
}

```

## disassembly

```asm
0x1800283f0  sub     rsp, 28h
0x1800283f4  lea     rcx, ?g_csGetDtcDispenser@@3VCCriticalSection@@A; lpCriticalSection
0x1800283fb  call    cs:__imp_DeleteCriticalSection
0x180028401  nop
0x180028402  add     rsp, 28h
0x180028406  retn
```
