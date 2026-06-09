# ADALCreateAuthenticationContextNoUI$dtor$0

- ea: `0x14002c86b`
- end: `0x14002c898`
- name: `ADALCreateAuthenticationContextNoUI$dtor$0`
- size: `45`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1400028ac`

## string_xrefs

- `0x14002c87a`: `onecore\ds\security\dsreg\win32\adal.native\adal.cpp`

## pseudocode

```c
void __fastcall ADALCreateAuthenticationContextNoUI_dtor_0(__int64 a1, __int64 a2)
{
  operator delete(*(void **)(a2 + 128));
}

```

## disassembly

```asm
0x14002c86b  push    rbp
0x14002c86d  sub     rsp, 20h
0x14002c871  mov     rbp, rdx
0x14002c874  mov     r9d, 1Eh
0x14002c87a  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\dsreg\\win32\\ad"...
0x14002c881  mov     edx, 1
0x14002c886  mov     rcx, [rbp+80h]; Block
0x14002c88d  call    ??3@YAXPEAXHPEBDH@Z; operator delete(void *,int,char const *,int)
0x14002c892  add     rsp, 20h
0x14002c896  pop     rbp
0x14002c897  retn
```
