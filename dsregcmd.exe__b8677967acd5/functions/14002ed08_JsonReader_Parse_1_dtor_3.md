# _JsonReader::Parse_::_1_::dtor$3

- ea: `0x14002ed08`
- end: `0x14002ed35`
- name: `_JsonReader::Parse_::_1_::dtor$3`
- size: `45`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x1400028ac`

## string_xrefs

- `0x14002ed17`: `onecore\ds\security\dsreg\win32\adal.native\jsonreader.cpp`

## pseudocode

```c
void __fastcall JsonReader::Parse_::_1_::dtor_3(__int64 a1, __int64 a2)
{
  operator delete(*(void **)(a2 + 128));
}

```

## disassembly

```asm
0x14002ed08  push    rbp
0x14002ed0a  sub     rsp, 20h
0x14002ed0e  mov     rbp, rdx
0x14002ed11  mov     r9d, 33h ; '3'
0x14002ed17  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\dsreg\\win32\\ad"...
0x14002ed1e  mov     edx, 1
0x14002ed23  mov     rcx, [rbp+80h]; Block
0x14002ed2a  call    ??3@YAXPEAXHPEBDH@Z; operator delete(void *,int,char const *,int)
0x14002ed2f  add     rsp, 20h
0x14002ed33  pop     rbp
0x14002ed34  retn
```
