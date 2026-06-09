# _JsonObject::AddNameToValueMapping_::_1_::dtor$0

- ea: `0x14002e840`
- end: `0x14002e86a`
- name: `_JsonObject::AddNameToValueMapping_::_1_::dtor$0`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x1400028ac`

## string_xrefs

- `0x14002e84f`: `onecore\ds\security\dsreg\win32\adal.native\json.cpp`

## pseudocode

```c
void __fastcall JsonObject::AddNameToValueMapping_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  operator delete(*(void **)(a2 + 104));
}

```

## disassembly

```asm
0x14002e840  push    rbp
0x14002e842  sub     rsp, 20h
0x14002e846  mov     rbp, rdx
0x14002e849  mov     r9d, 49h ; 'I'
0x14002e84f  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\dsreg\\win32\\ad"...
0x14002e856  mov     edx, 1
0x14002e85b  mov     rcx, [rbp+68h]; Block
0x14002e85f  call    ??3@YAXPEAXHPEBDH@Z; operator delete(void *,int,char const *,int)
0x14002e864  add     rsp, 20h
0x14002e868  pop     rbp
0x14002e869  retn
```
