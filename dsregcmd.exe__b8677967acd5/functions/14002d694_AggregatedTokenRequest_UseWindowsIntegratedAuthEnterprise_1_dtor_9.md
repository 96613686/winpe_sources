# _AggregatedTokenRequest::UseWindowsIntegratedAuthEnterprise_::_1_::dtor$9

- ea: `0x14002d694`
- end: `0x14002d6c1`
- name: `_AggregatedTokenRequest::UseWindowsIntegratedAuthEnterprise_::_1_::dtor$9`
- size: `45`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1400028ac`

## string_xrefs

- `0x14002d6a3`: `onecore\ds\security\dsreg\win32\adal.native\aggregatedtokenrequest.cpp`

## pseudocode

```c
void __fastcall AggregatedTokenRequest::UseWindowsIntegratedAuthEnterprise_::_1_::dtor_9(__int64 a1, __int64 a2)
{
  operator delete(*(void **)(a2 + 232));
}

```

## disassembly

```asm
0x14002d694  push    rbp
0x14002d696  sub     rsp, 20h
0x14002d69a  mov     rbp, rdx
0x14002d69d  mov     r9d, 0E2h
0x14002d6a3  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\dsreg\\win32\\ad"...
0x14002d6aa  mov     edx, 1
0x14002d6af  mov     rcx, [rbp+0E8h]; Block
0x14002d6b6  call    ??3@YAXPEAXHPEBDH@Z; operator delete(void *,int,char const *,int)
0x14002d6bb  add     rsp, 20h
0x14002d6bf  pop     rbp
0x14002d6c0  retn
```
