# _JsonReader::ParseArrayValue_::_1_::dtor$1

- ea: `0x14002ed3b`
- end: `0x14002ed65`
- name: `_JsonReader::ParseArrayValue_::_1_::dtor$1`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x1400028ac`

## string_xrefs

- `0x14002ed4a`: `onecore\ds\security\dsreg\win32\adal.native\jsonreader.cpp`

## pseudocode

```c
void __fastcall JsonReader::ParseArrayValue_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  operator delete(*(void **)(a2 + 72));
}

```

## disassembly

```asm
0x14002ed3b  push    rbp
0x14002ed3d  sub     rsp, 20h
0x14002ed41  mov     rbp, rdx
0x14002ed44  mov     r9d, 0F4h
0x14002ed4a  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\dsreg\\win32\\ad"...
0x14002ed51  mov     edx, 1
0x14002ed56  mov     rcx, [rbp+48h]; Block
0x14002ed5a  call    ??3@YAXPEAXHPEBDH@Z; operator delete(void *,int,char const *,int)
0x14002ed5f  add     rsp, 20h
0x14002ed63  pop     rbp
0x14002ed64  retn
```
