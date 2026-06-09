# _OAuthResponse::ParseIdTokenResponse_::_1_::dtor$0

- ea: `0x14002ef17`
- end: `0x14002ef41`
- name: `_OAuthResponse::ParseIdTokenResponse_::_1_::dtor$0`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1400028ac`

## string_xrefs

- `0x14002ef26`: `onecore\ds\security\dsreg\win32\adal.native\oauthtokenresponse.cpp`

## pseudocode

```c
void __fastcall OAuthResponse::ParseIdTokenResponse_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  operator delete(*(void **)(a2 + 56));
}

```

## disassembly

```asm
0x14002ef17  push    rbp
0x14002ef19  sub     rsp, 20h
0x14002ef1d  mov     rbp, rdx
0x14002ef20  mov     r9d, 95h
0x14002ef26  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\dsreg\\win32\\ad"...
0x14002ef2d  mov     edx, 1
0x14002ef32  mov     rcx, [rbp+38h]; Block
0x14002ef36  call    ??3@YAXPEAXHPEBDH@Z; operator delete(void *,int,char const *,int)
0x14002ef3b  add     rsp, 20h
0x14002ef3f  pop     rbp
0x14002ef40  retn
```
