# _JsonReader::ParseSimpleValue_::_1_::dtor$0

- ea: `0x14002edad`
- end: `0x14002edd7`
- name: `_JsonReader::ParseSimpleValue_::_1_::dtor$0`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x1400028ac`

## string_xrefs

- `0x14002edbc`: `onecore\ds\security\dsreg\win32\adal.native\jsonreader.cpp`

## pseudocode

```c
void __fastcall JsonReader::ParseSimpleValue_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  operator delete(*(void **)(a2 + 32));
}

```

## disassembly

```asm
0x14002edad  push    rbp
0x14002edaf  sub     rsp, 20h
0x14002edb3  mov     rbp, rdx
0x14002edb6  mov     r9d, 108h
0x14002edbc  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\dsreg\\win32\\ad"...
0x14002edc3  mov     edx, 1
0x14002edc8  mov     rcx, [rbp+20h]; Block
0x14002edcc  call    ??3@YAXPEAXHPEBDH@Z; operator delete(void *,int,char const *,int)
0x14002edd1  add     rsp, 20h
0x14002edd5  pop     rbp
0x14002edd6  retn
```
