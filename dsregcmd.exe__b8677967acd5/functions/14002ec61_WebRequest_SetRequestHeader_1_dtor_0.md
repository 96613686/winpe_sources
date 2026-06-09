# _WebRequest::SetRequestHeader_::_1_::dtor$0

- ea: `0x14002ec61`
- end: `0x14002ec8b`
- name: `_WebRequest::SetRequestHeader_::_1_::dtor$0`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1400028ac`

## string_xrefs

- `0x14002ec70`: `onecore\ds\security\dsreg\win32\adal.native\webrequest.cpp`

## pseudocode

```c
void __fastcall WebRequest::SetRequestHeader_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  operator delete(*(void **)(a2 + 64));
}

```

## disassembly

```asm
0x14002ec61  push    rbp
0x14002ec63  sub     rsp, 20h
0x14002ec67  mov     rbp, rdx
0x14002ec6a  mov     r9d, 0DAh
0x14002ec70  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\dsreg\\win32\\ad"...
0x14002ec77  mov     edx, 1
0x14002ec7c  mov     rcx, [rbp+40h]; Block
0x14002ec80  call    ??3@YAXPEAXHPEBDH@Z; operator delete(void *,int,char const *,int)
0x14002ec85  add     rsp, 20h
0x14002ec89  pop     rbp
0x14002ec8a  retn
```
