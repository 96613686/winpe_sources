# _AggregatedTokenRequest::UseWindowsIntegratedAuth_::_1_::dtor$9

- ea: `0x14002d52b`
- end: `0x14002d558`
- name: `_AggregatedTokenRequest::UseWindowsIntegratedAuth_::_1_::dtor$9`
- size: `45`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1400028ac`

## string_xrefs

- `0x14002d53a`: `onecore\ds\security\dsreg\win32\adal.native\aggregatedtokenrequest.cpp`

## pseudocode

```c
void __fastcall AggregatedTokenRequest::UseWindowsIntegratedAuth_::_1_::dtor_9(__int64 a1, __int64 a2)
{
  operator delete(*(void **)(a2 + 264));
}

```

## disassembly

```asm
0x14002d52b  push    rbp
0x14002d52d  sub     rsp, 20h
0x14002d531  mov     rbp, rdx
0x14002d534  mov     r9d, 0B8h
0x14002d53a  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\dsreg\\win32\\ad"...
0x14002d541  mov     edx, 1
0x14002d546  mov     rcx, [rbp+108h]; Block
0x14002d54d  call    ??3@YAXPEAXHPEBDH@Z; operator delete(void *,int,char const *,int)
0x14002d552  add     rsp, 20h
0x14002d556  pop     rbp
0x14002d557  retn
```
