# CTypedHashTable<UL_RESPONSE_CACHE,UL_RESPONSE_CACHE_ENTRY,UL_RESPONSE_CACHE_KEY *,CLKRHashTable>::_EqualKeys(unsigned __int64,unsigned __int64)

- ea: `0x180003990`
- end: `0x1800039b7`
- name: `?_EqualKeys@?$CTypedHashTable@VUL_RESPONSE_CACHE@@VUL_RESPONSE_CACHE_ENTRY@@PEAVUL_RESPONSE_CACHE_KEY@@VCLKRHashTable@@@@CA_N_K0@Z`
- size: `39`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180003990`

## import_xrefs

- `iisutil!?Equals@STRU@@QEBA_NAEBV1@@Z` at `0x1800039a2`
- `iisutil!?Equals@STRU@@QEBA_NAEBV1@@Z` at `0x1800039a2`

## pseudocode

```c
bool __fastcall CTypedHashTable<UL_RESPONSE_CACHE,UL_RESPONSE_CACHE_ENTRY,UL_RESPONSE_CACHE_KEY *,CLKRHashTable>::_EqualKeys(
        STRU *a1,
        const struct STRU *a2)
{
  return *((_DWORD *)a1 + 138) == *((_DWORD *)a2 + 138) && STRU::Equals(a1, a2);
}

```

## disassembly

```asm
0x180003990  sub     rsp, 28h
0x180003994  mov     eax, [rdx+228h]
0x18000399a  cmp     [rcx+228h], eax
0x1800039a0  jnz     short loc_1800039B3
0x1800039a2  call    cs:__imp_?Equals@STRU@@QEBA_NAEBV1@@Z; STRU::Equals(STRU const &)
0x1800039a8  test    al, al
0x1800039aa  jz      short loc_1800039B3
0x1800039ac  mov     al, 1
0x1800039ae  add     rsp, 28h
0x1800039b2  retn
0x1800039b3  xor     al, al
0x1800039b5  jmp     short loc_1800039AE
```
