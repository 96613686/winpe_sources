# _WSTrustTokenRequest::GetWSTrustResponse_::_1_::dtor$13

- ea: `0x14002e268`
- end: `0x14002e292`
- name: `_WSTrustTokenRequest::GetWSTrustResponse_::_1_::dtor$13`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1400028ac`

## string_xrefs

- `0x14002e277`: `onecore\ds\security\dsreg\win32\adal.native\wstrusttokenrequest.cpp`

## pseudocode

```c
void __fastcall WSTrustTokenRequest::GetWSTrustResponse_::_1_::dtor_13(__int64 a1, __int64 a2)
{
  operator delete(*(void **)(a2 + 64));
}

```

## disassembly

```asm
0x14002e268  push    rbp
0x14002e26a  sub     rsp, 20h
0x14002e26e  mov     rbp, rdx
0x14002e271  mov     r9d, 0A2h
0x14002e277  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\dsreg\\win32\\ad"...
0x14002e27e  mov     edx, 1
0x14002e283  mov     rcx, [rbp+40h]; Block
0x14002e287  call    ??3@YAXPEAXHPEBDH@Z; operator delete(void *,int,char const *,int)
0x14002e28c  add     rsp, 20h
0x14002e290  pop     rbp
0x14002e291  retn
```
