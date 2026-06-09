# _AggregatedTokenRequest::AcquireToken_::_1_::dtor$1

- ea: `0x14002d23e`
- end: `0x14002d268`
- name: `_AggregatedTokenRequest::AcquireToken_::_1_::dtor$1`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1400028ac`

## string_xrefs

- `0x14002d24d`: `onecore\ds\security\dsreg\win32\adal.native\aggregatedtokenrequest.cpp`

## pseudocode

```c
void __fastcall AggregatedTokenRequest::AcquireToken_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  operator delete(*(void **)(a2 + 104));
}

```

## disassembly

```asm
0x14002d23e  push    rbp
0x14002d240  sub     rsp, 20h
0x14002d244  mov     rbp, rdx
0x14002d247  mov     r9d, 2Ah ; '*'
0x14002d24d  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\dsreg\\win32\\ad"...
0x14002d254  mov     edx, 1
0x14002d259  mov     rcx, [rbp+68h]; Block
0x14002d25d  call    ??3@YAXPEAXHPEBDH@Z; operator delete(void *,int,char const *,int)
0x14002d262  add     rsp, 20h
0x14002d266  pop     rbp
0x14002d267  retn
```
