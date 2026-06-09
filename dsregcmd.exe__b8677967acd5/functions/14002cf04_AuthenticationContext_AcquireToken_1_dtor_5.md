# _AuthenticationContext::AcquireToken_::_1_::dtor$5

- ea: `0x14002cf04`
- end: `0x14002cf2e`
- name: `_AuthenticationContext::AcquireToken_::_1_::dtor$5`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1400028ac`

## string_xrefs

- `0x14002cf13`: `onecore\ds\security\dsreg\win32\adal.native\authenticationcontext.cpp`

## pseudocode

```c
void __fastcall AuthenticationContext::AcquireToken_::_1_::dtor_5(__int64 a1, __int64 a2)
{
  operator delete(*(void **)(a2 + 40));
}

```

## disassembly

```asm
0x14002cf04  push    rbp
0x14002cf06  sub     rsp, 20h
0x14002cf0a  mov     rbp, rdx
0x14002cf0d  mov     r9d, 0B6h
0x14002cf13  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\dsreg\\win32\\ad"...
0x14002cf1a  mov     edx, 1
0x14002cf1f  mov     rcx, [rbp+28h]; Block
0x14002cf23  call    ??3@YAXPEAXHPEBDH@Z; operator delete(void *,int,char const *,int)
0x14002cf28  add     rsp, 20h
0x14002cf2c  pop     rbp
0x14002cf2d  retn
```
