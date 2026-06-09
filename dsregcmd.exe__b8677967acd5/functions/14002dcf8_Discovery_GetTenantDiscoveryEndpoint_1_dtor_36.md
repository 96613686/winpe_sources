# _Discovery::GetTenantDiscoveryEndpoint_::_1_::dtor$36

- ea: `0x14002dcf8`
- end: `0x14002dd25`
- name: `_Discovery::GetTenantDiscoveryEndpoint_::_1_::dtor$36`
- size: `45`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1400028ac`

## string_xrefs

- `0x14002dd07`: `onecore\ds\security\dsreg\win32\adal.native\webcall.cpp`

## pseudocode

```c
void __fastcall Discovery::GetTenantDiscoveryEndpoint_::_1_::dtor_36(__int64 a1, __int64 a2)
{
  operator delete(*(void **)(a2 + 144));
}

```

## disassembly

```asm
0x14002dcf8  push    rbp
0x14002dcfa  sub     rsp, 20h
0x14002dcfe  mov     rbp, rdx
0x14002dd01  mov     r9d, 11h
0x14002dd07  lea     r8, aOnecoreDsSecur_17; "onecore\\ds\\security\\dsreg\\win32\\ad"...
0x14002dd0e  mov     edx, 1
0x14002dd13  mov     rcx, [rbp+90h]; Block
0x14002dd1a  call    ??3@YAXPEAXHPEBDH@Z; operator delete(void *,int,char const *,int)
0x14002dd1f  add     rsp, 20h
0x14002dd23  pop     rbp
0x14002dd24  retn
```
