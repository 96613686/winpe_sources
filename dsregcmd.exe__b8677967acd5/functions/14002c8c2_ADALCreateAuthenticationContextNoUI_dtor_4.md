# ADALCreateAuthenticationContextNoUI$dtor$4

- ea: `0x14002c8c2`
- end: `0x14002c8ef`
- name: `ADALCreateAuthenticationContextNoUI$dtor$4`
- size: `45`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1400028ac`

## string_xrefs

- `0x14002c8d1`: `onecore\ds\security\dsreg\win32\adal.native\APIHandle.h`

## pseudocode

```c
void __fastcall ADALCreateAuthenticationContextNoUI_dtor_4(__int64 a1, __int64 a2)
{
  operator delete(*(void **)(a2 + 128));
}

```

## disassembly

```asm
0x14002c8c2  push    rbp
0x14002c8c4  sub     rsp, 20h
0x14002c8c8  mov     rbp, rdx
0x14002c8cb  mov     r9d, 3Fh ; '?'
0x14002c8d1  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\dsreg\\win32\\ad"...
0x14002c8d8  mov     edx, 1
0x14002c8dd  mov     rcx, [rbp+80h]; Block
0x14002c8e4  call    ??3@YAXPEAXHPEBDH@Z; operator delete(void *,int,char const *,int)
0x14002c8e9  add     rsp, 20h
0x14002c8ed  pop     rbp
0x14002c8ee  retn
```
