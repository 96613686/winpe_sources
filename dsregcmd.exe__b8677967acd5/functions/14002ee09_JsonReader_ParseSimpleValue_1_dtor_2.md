# _JsonReader::ParseSimpleValue_::_1_::dtor$2

- ea: `0x14002ee09`
- end: `0x14002ee33`
- name: `_JsonReader::ParseSimpleValue_::_1_::dtor$2`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x1400028ac`

## string_xrefs

- `0x14002ee18`: `onecore\ds\security\dsreg\win32\adal.native\jsonreader.cpp`

## pseudocode

```c
void __fastcall JsonReader::ParseSimpleValue_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  operator delete(*(void **)(a2 + 32));
}

```

## disassembly

```asm
0x14002ee09  push    rbp
0x14002ee0b  sub     rsp, 20h
0x14002ee0f  mov     rbp, rdx
0x14002ee12  mov     r9d, 10Dh
0x14002ee18  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\dsreg\\win32\\ad"...
0x14002ee1f  mov     edx, 1
0x14002ee24  mov     rcx, [rbp+20h]; Block
0x14002ee28  call    ??3@YAXPEAXHPEBDH@Z; operator delete(void *,int,char const *,int)
0x14002ee2d  add     rsp, 20h
0x14002ee31  pop     rbp
0x14002ee32  retn
```
