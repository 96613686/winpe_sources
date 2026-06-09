# _JWSBuilder::JwsHeaderToJson_::_1_::dtor$11

- ea: `0x14002f7f2`
- end: `0x14002f81c`
- name: `_JWSBuilder::JwsHeaderToJson_::_1_::dtor$11`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x1400028ac`

## string_xrefs

- `0x14002f801`: `onecore\ds\security\dsreg\win32\adal.native\jwsbuilder.cpp`

## pseudocode

```c
void __fastcall JWSBuilder::JwsHeaderToJson_::_1_::dtor_11(__int64 a1, __int64 a2)
{
  operator delete(*(void **)(a2 + 40));
}

```

## disassembly

```asm
0x14002f7f2  push    rbp
0x14002f7f4  sub     rsp, 20h
0x14002f7f8  mov     rbp, rdx
0x14002f7fb  mov     r9d, 3Fh ; '?'
0x14002f801  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\dsreg\\win32\\ad"...
0x14002f808  mov     edx, 1
0x14002f80d  mov     rcx, [rbp+28h]; Block
0x14002f811  call    ??3@YAXPEAXHPEBDH@Z; operator delete(void *,int,char const *,int)
0x14002f816  add     rsp, 20h
0x14002f81a  pop     rbp
0x14002f81b  retn
```
