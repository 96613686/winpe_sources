# _RefreshTokenRequest::RefreshTokenRequest_::_1_::dtor$3

- ea: `0x14002e013`
- end: `0x14002e03d`
- name: `_RefreshTokenRequest::RefreshTokenRequest_::_1_::dtor$3`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1400028ac`

## string_xrefs

- `0x14002e022`: `onecore\ds\security\dsreg\win32\adal.native\refreshtokenrequest.cpp`

## pseudocode

```c
void __fastcall RefreshTokenRequest::RefreshTokenRequest_::_1_::dtor_3(__int64 a1, __int64 a2)
{
  operator delete(*(void **)(a2 + 32));
}

```

## disassembly

```asm
0x14002e013  push    rbp
0x14002e015  sub     rsp, 20h
0x14002e019  mov     rbp, rdx
0x14002e01c  mov     r9d, 1Ah
0x14002e022  lea     r8, aOnecoreDsSecur_12; "onecore\\ds\\security\\dsreg\\win32\\ad"...
0x14002e029  mov     edx, 1
0x14002e02e  mov     rcx, [rbp+20h]; Block
0x14002e032  call    ??3@YAXPEAXHPEBDH@Z; operator delete(void *,int,char const *,int)
0x14002e037  add     rsp, 20h
0x14002e03b  pop     rbp
0x14002e03c  retn
```
