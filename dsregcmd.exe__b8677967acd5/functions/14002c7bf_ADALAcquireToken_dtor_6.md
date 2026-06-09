# ADALAcquireToken$dtor$6

- ea: `0x14002c7bf`
- end: `0x14002c7e9`
- name: `ADALAcquireToken$dtor$6`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1400028ac`

## string_xrefs

- `0x14002c7ce`: `onecore\ds\security\dsreg\win32\adal.native\APIHandle.h`

## pseudocode

```c
void __fastcall ADALAcquireToken_dtor_6(__int64 a1, __int64 a2)
{
  operator delete(*(void **)(a2 + 48));
}

```

## disassembly

```asm
0x14002c7bf  push    rbp
0x14002c7c1  sub     rsp, 20h
0x14002c7c5  mov     rbp, rdx
0x14002c7c8  mov     r9d, 3Fh ; '?'
0x14002c7ce  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\dsreg\\win32\\ad"...
0x14002c7d5  mov     edx, 1
0x14002c7da  mov     rcx, [rbp+30h]; Block
0x14002c7de  call    ??3@YAXPEAXHPEBDH@Z; operator delete(void *,int,char const *,int)
0x14002c7e3  add     rsp, 20h
0x14002c7e7  pop     rbp
0x14002c7e8  retn
```
