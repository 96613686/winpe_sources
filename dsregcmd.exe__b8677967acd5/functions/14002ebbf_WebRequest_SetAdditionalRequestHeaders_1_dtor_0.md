# _WebRequest::SetAdditionalRequestHeaders_::_1_::dtor$0

- ea: `0x14002ebbf`
- end: `0x14002ebe9`
- name: `_WebRequest::SetAdditionalRequestHeaders_::_1_::dtor$0`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1400028ac`

## string_xrefs

- `0x14002ebce`: `onecore\ds\security\dsreg\win32\adal.native\webrequest.cpp`

## pseudocode

```c
void __fastcall WebRequest::SetAdditionalRequestHeaders_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  operator delete(*(void **)(a2 + 104));
}

```

## disassembly

```asm
0x14002ebbf  push    rbp
0x14002ebc1  sub     rsp, 20h
0x14002ebc5  mov     rbp, rdx
0x14002ebc8  mov     r9d, 0F0h
0x14002ebce  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\dsreg\\win32\\ad"...
0x14002ebd5  mov     edx, 1
0x14002ebda  mov     rcx, [rbp+68h]; Block
0x14002ebde  call    ??3@YAXPEAXHPEBDH@Z; operator delete(void *,int,char const *,int)
0x14002ebe3  add     rsp, 20h
0x14002ebe7  pop     rbp
0x14002ebe8  retn
```
