# _AggregatedTokenRequest::UseWindowsIntegratedAuth_::_1_::dtor$1

- ea: `0x14002d49e`
- end: `0x14002d4cb`
- name: `_AggregatedTokenRequest::UseWindowsIntegratedAuth_::_1_::dtor$1`
- size: `45`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1400028ac`

## string_xrefs

- `0x14002d4ad`: `onecore\ds\security\dsreg\win32\adal.native\aggregatedtokenrequest.cpp`

## pseudocode

```c
void __fastcall AggregatedTokenRequest::UseWindowsIntegratedAuth_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  operator delete(*(void **)(a2 + 256));
}

```

## disassembly

```asm
0x14002d49e  push    rbp
0x14002d4a0  sub     rsp, 20h
0x14002d4a4  mov     rbp, rdx
0x14002d4a7  mov     r9d, 0B0h
0x14002d4ad  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\dsreg\\win32\\ad"...
0x14002d4b4  mov     edx, 1
0x14002d4b9  mov     rcx, [rbp+100h]; Block
0x14002d4c0  call    ??3@YAXPEAXHPEBDH@Z; operator delete(void *,int,char const *,int)
0x14002d4c5  add     rsp, 20h
0x14002d4c9  pop     rbp
0x14002d4ca  retn
```
