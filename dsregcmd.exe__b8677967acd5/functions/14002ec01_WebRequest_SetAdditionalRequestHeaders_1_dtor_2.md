# _WebRequest::SetAdditionalRequestHeaders_::_1_::dtor$2

- ea: `0x14002ec01`
- end: `0x14002ec2b`
- name: `_WebRequest::SetAdditionalRequestHeaders_::_1_::dtor$2`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1400028ac`

## string_xrefs

- `0x14002ec10`: `onecore\ds\security\dsreg\win32\adal.native\webrequest.cpp`

## pseudocode

```c
void __fastcall WebRequest::SetAdditionalRequestHeaders_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  operator delete(*(void **)(a2 + 112));
}

```

## disassembly

```asm
0x14002ec01  push    rbp
0x14002ec03  sub     rsp, 20h
0x14002ec07  mov     rbp, rdx
0x14002ec0a  mov     r9d, 0F5h
0x14002ec10  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\dsreg\\win32\\ad"...
0x14002ec17  mov     edx, 1
0x14002ec1c  mov     rcx, [rbp+70h]; Block
0x14002ec20  call    ??3@YAXPEAXHPEBDH@Z; operator delete(void *,int,char const *,int)
0x14002ec25  add     rsp, 20h
0x14002ec29  pop     rbp
0x14002ec2a  retn
```
