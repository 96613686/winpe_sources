# _WebRequestFactory::CreateBasicConnection_::_1_::dtor$0

- ea: `0x14002e8f2`
- end: `0x14002e91c`
- name: `_WebRequestFactory::CreateBasicConnection_::_1_::dtor$0`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1400028ac`

## string_xrefs

- `0x14002e901`: `onecore\ds\security\dsreg\win32\adal.native\webrequestfactory.cpp`

## pseudocode

```c
void __fastcall WebRequestFactory::CreateBasicConnection_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  operator delete(*(void **)(a2 + 96));
}

```

## disassembly

```asm
0x14002e8f2  push    rbp
0x14002e8f4  sub     rsp, 20h
0x14002e8f8  mov     rbp, rdx
0x14002e8fb  mov     r9d, 3Bh ; ';'
0x14002e901  lea     r8, aOnecoreDsSecur_16; "onecore\\ds\\security\\dsreg\\win32\\ad"...
0x14002e908  mov     edx, 1
0x14002e90d  mov     rcx, [rbp+60h]; Block
0x14002e911  call    ??3@YAXPEAXHPEBDH@Z; operator delete(void *,int,char const *,int)
0x14002e916  add     rsp, 20h
0x14002e91a  pop     rbp
0x14002e91b  retn
```
