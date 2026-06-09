# _WebRequest::SetAdditionalRequestHeaders_::_1_::dtor$0_0

- ea: `0x14002ec31`
- end: `0x14002ec5b`
- name: `_WebRequest::SetAdditionalRequestHeaders_::_1_::dtor$0_0`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1400028ac`

## string_xrefs

- `0x14002ec40`: `onecore\ds\security\dsreg\win32\adal.native\webrequest.cpp`

## pseudocode

```c
void __fastcall WebRequest::SetAdditionalRequestHeaders_::_1_::dtor_0_0(__int64 a1, __int64 a2)
{
  operator delete(*(void **)(a2 + 80));
}

```

## disassembly

```asm
0x14002ec31  push    rbp
0x14002ec33  sub     rsp, 20h
0x14002ec37  mov     rbp, rdx
0x14002ec3a  mov     r9d, 0E2h
0x14002ec40  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\dsreg\\win32\\ad"...
0x14002ec47  mov     edx, 1
0x14002ec4c  mov     rcx, [rbp+50h]; Block
0x14002ec50  call    ??3@YAXPEAXHPEBDH@Z; operator delete(void *,int,char const *,int)
0x14002ec55  add     rsp, 20h
0x14002ec59  pop     rbp
0x14002ec5a  retn
```
