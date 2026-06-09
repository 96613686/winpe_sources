# ADALAcquireToken$dtor$4

- ea: `0x14002c77d`
- end: `0x14002c7a7`
- name: `ADALAcquireToken$dtor$4`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1400028ac`

## string_xrefs

- `0x14002c78c`: `onecore\ds\security\dsreg\win32\adal.native\apireq.cpp`

## pseudocode

```c
void __fastcall ADALAcquireToken_dtor_4(__int64 a1, __int64 a2)
{
  operator delete(*(void **)(a2 + 40));
}

```

## disassembly

```asm
0x14002c77d  push    rbp
0x14002c77f  sub     rsp, 20h
0x14002c783  mov     rbp, rdx
0x14002c786  mov     r9d, 32h ; '2'
0x14002c78c  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\dsreg\\win32\\ad"...
0x14002c793  mov     edx, 1
0x14002c798  mov     rcx, [rbp+28h]; Block
0x14002c79c  call    ??3@YAXPEAXHPEBDH@Z; operator delete(void *,int,char const *,int)
0x14002c7a1  add     rsp, 20h
0x14002c7a5  pop     rbp
0x14002c7a6  retn
```
