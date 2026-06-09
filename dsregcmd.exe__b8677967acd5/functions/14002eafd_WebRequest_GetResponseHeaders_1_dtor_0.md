# _WebRequest::GetResponseHeaders_::_1_::dtor$0

- ea: `0x14002eafd`
- end: `0x14002eb27`
- name: `_WebRequest::GetResponseHeaders_::_1_::dtor$0`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1400028ac`

## string_xrefs

- `0x14002eb0c`: `onecore\ds\security\dsreg\win32\adal.native\webrequest.cpp`

## pseudocode

```c
void __fastcall WebRequest::GetResponseHeaders_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  operator delete(*(void **)(a2 + 64));
}

```

## disassembly

```asm
0x14002eafd  push    rbp
0x14002eaff  sub     rsp, 20h
0x14002eb03  mov     rbp, rdx
0x14002eb06  mov     r9d, 24Fh
0x14002eb0c  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\dsreg\\win32\\ad"...
0x14002eb13  mov     edx, 1
0x14002eb18  mov     rcx, [rbp+40h]; Block
0x14002eb1c  call    ??3@YAXPEAXHPEBDH@Z; operator delete(void *,int,char const *,int)
0x14002eb21  add     rsp, 20h
0x14002eb25  pop     rbp
0x14002eb26  retn
```
