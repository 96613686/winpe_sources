# _JsonReader::ParseNameValuePair_::_1_::dtor$3

- ea: `0x14002ed7d`
- end: `0x14002eda7`
- name: `_JsonReader::ParseNameValuePair_::_1_::dtor$3`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x1400028ac`

## string_xrefs

- `0x14002ed8c`: `onecore\ds\security\dsreg\win32\adal.native\jsonreader.cpp`

## pseudocode

```c
void __fastcall JsonReader::ParseNameValuePair_::_1_::dtor_3(__int64 a1, __int64 a2)
{
  operator delete(*(void **)(a2 + 40));
}

```

## disassembly

```asm
0x14002ed7d  push    rbp
0x14002ed7f  sub     rsp, 20h
0x14002ed83  mov     rbp, rdx
0x14002ed86  mov     r9d, 0CEh
0x14002ed8c  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\dsreg\\win32\\ad"...
0x14002ed93  mov     edx, 1
0x14002ed98  mov     rcx, [rbp+28h]; Block
0x14002ed9c  call    ??3@YAXPEAXHPEBDH@Z; operator delete(void *,int,char const *,int)
0x14002eda1  add     rsp, 20h
0x14002eda5  pop     rbp
0x14002eda6  retn
```
