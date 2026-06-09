# _dynamic_atexit_destructor_for__g_csComplexInit__

- ea: `0x1800283b0`
- end: `0x1800283c7`
- name: `_dynamic_atexit_destructor_for__g_csComplexInit__`
- size: `23`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1800283bb`
- `KERNEL32!DeleteCriticalSection` at `0x1800283bb`

## pseudocode

```c
void dynamic_atexit_destructor_for__g_csComplexInit__()
{
  DeleteCriticalSection(&g_csComplexInit);
}

```

## disassembly

```asm
0x1800283b0  sub     rsp, 28h
0x1800283b4  lea     rcx, ?g_csComplexInit@@3VCCriticalSection@@A; lpCriticalSection
0x1800283bb  call    cs:__imp_DeleteCriticalSection
0x1800283c1  nop
0x1800283c2  add     rsp, 28h
0x1800283c6  retn
```
