# _AuthenticationContext::AcquireToken_::_1_::dtor$2

- ea: `0x14002ce90`
- end: `0x14002ceba`
- name: `_AuthenticationContext::AcquireToken_::_1_::dtor$2`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1400028ac`

## string_xrefs

- `0x14002ce9f`: `onecore\ds\security\dsreg\win32\adal.native\authenticationcontext.cpp`

## pseudocode

```c
void __fastcall AuthenticationContext::AcquireToken_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  operator delete(*(void **)(a2 + 40));
}

```

## disassembly

```asm
0x14002ce90  push    rbp
0x14002ce92  sub     rsp, 20h
0x14002ce96  mov     rbp, rdx
0x14002ce99  mov     r9d, 0A7h
0x14002ce9f  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\dsreg\\win32\\ad"...
0x14002cea6  mov     edx, 1
0x14002ceab  mov     rcx, [rbp+28h]; Block
0x14002ceaf  call    ??3@YAXPEAXHPEBDH@Z; operator delete(void *,int,char const *,int)
0x14002ceb4  add     rsp, 20h
0x14002ceb8  pop     rbp
0x14002ceb9  retn
```
