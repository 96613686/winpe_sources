# _AggregatedTokenRequest::UseWindowsIntegratedAuthEnterprise_::_1_::dtor$2

- ea: `0x14002d619`
- end: `0x14002d646`
- name: `_AggregatedTokenRequest::UseWindowsIntegratedAuthEnterprise_::_1_::dtor$2`
- size: `45`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1400028ac`

## string_xrefs

- `0x14002d628`: `onecore\ds\security\dsreg\win32\adal.native\aggregatedtokenrequest.cpp`

## pseudocode

```c
void __fastcall AggregatedTokenRequest::UseWindowsIntegratedAuthEnterprise_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  operator delete(*(void **)(a2 + 224));
}

```

## disassembly

```asm
0x14002d619  push    rbp
0x14002d61b  sub     rsp, 20h
0x14002d61f  mov     rbp, rdx
0x14002d622  mov     r9d, 0DCh
0x14002d628  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\dsreg\\win32\\ad"...
0x14002d62f  mov     edx, 1
0x14002d634  mov     rcx, [rbp+0E0h]; Block
0x14002d63b  call    ??3@YAXPEAXHPEBDH@Z; operator delete(void *,int,char const *,int)
0x14002d640  add     rsp, 20h
0x14002d644  pop     rbp
0x14002d645  retn
```
