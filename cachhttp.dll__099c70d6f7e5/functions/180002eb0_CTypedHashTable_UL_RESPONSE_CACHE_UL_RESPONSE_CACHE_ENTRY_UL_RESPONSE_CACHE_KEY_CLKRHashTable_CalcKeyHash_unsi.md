# CTypedHashTable<UL_RESPONSE_CACHE,UL_RESPONSE_CACHE_ENTRY,UL_RESPONSE_CACHE_KEY *,CLKRHashTable>::_CalcKeyHash(unsigned __int64)

- ea: `0x180002eb0`
- end: `0x180002ed3`
- name: `?_CalcKeyHash@?$CTypedHashTable@VUL_RESPONSE_CACHE@@VUL_RESPONSE_CACHE_ENTRY@@PEAVUL_RESPONSE_CACHE_KEY@@VCLKRHashTable@@@@CAK_K@Z`
- size: `35`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180002ee0`

## import_xrefs

- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180002eb9`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180002eb9`

## pseudocode

```c
__int64 __fastcall CTypedHashTable<UL_RESPONSE_CACHE,UL_RESPONSE_CACHE_ENTRY,UL_RESPONSE_CACHE_KEY *,CLKRHashTable>::_CalcKeyHash(
        STRU *a1)
{
  const unsigned __int16 *Str; // rax
  unsigned int v3; // edx

  Str = STRU::QueryStr(a1);
  return *((_DWORD *)a1 + 138) ^ HashString(Str, v3);
}

```

## disassembly

```asm
0x180002eb0  push    rbx
0x180002eb2  sub     rsp, 20h
0x180002eb6  mov     rbx, rcx
0x180002eb9  call    cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ; STRU::QueryStr(void)
0x180002ebf  mov     rcx, rax; unsigned __int16 *
0x180002ec2  call    ?HashString@@YAKPEBGK@Z; HashString(ushort const *,ulong)
0x180002ec7  xor     eax, [rbx+228h]
0x180002ecd  add     rsp, 20h
0x180002ed1  pop     rbx
0x180002ed2  retn
```
