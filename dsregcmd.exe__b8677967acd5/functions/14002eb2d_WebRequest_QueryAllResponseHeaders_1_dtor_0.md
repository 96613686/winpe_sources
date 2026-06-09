# _WebRequest::QueryAllResponseHeaders_::_1_::dtor$0

- ea: `0x14002eb2d`
- end: `0x14002eb57`
- name: `_WebRequest::QueryAllResponseHeaders_::_1_::dtor$0`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1400028ac`

## string_xrefs

- `0x14002eb3c`: `onecore\ds\security\dsreg\win32\adal.native\webrequest.cpp`

## pseudocode

```c
void __fastcall WebRequest::QueryAllResponseHeaders_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  operator delete(*(void **)(a2 + 80));
}

```

## disassembly

```asm
0x14002eb2d  push    rbp
0x14002eb2f  sub     rsp, 20h
0x14002eb33  mov     rbp, rdx
0x14002eb36  mov     r9d, 1F3h
0x14002eb3c  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\dsreg\\win32\\ad"...
0x14002eb43  mov     edx, 1
0x14002eb48  mov     rcx, [rbp+50h]; Block
0x14002eb4c  call    ??3@YAXPEAXHPEBDH@Z; operator delete(void *,int,char const *,int)
0x14002eb51  add     rsp, 20h
0x14002eb55  pop     rbp
0x14002eb56  retn
```
