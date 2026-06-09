# _UserRealm::GetUserRealm_::_1_::dtor$6

- ea: `0x14002d8be`
- end: `0x14002d8e8`
- name: `_UserRealm::GetUserRealm_::_1_::dtor$6`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1400028ac`

## string_xrefs

- `0x14002d8cd`: `onecore\ds\security\dsreg\win32\adal.native\userrealm.cpp`

## pseudocode

```c
void __fastcall UserRealm::GetUserRealm_::_1_::dtor_6(__int64 a1, __int64 a2)
{
  operator delete(*(void **)(a2 + 48));
}

```

## disassembly

```asm
0x14002d8be  push    rbp
0x14002d8c0  sub     rsp, 20h
0x14002d8c4  mov     rbp, rdx
0x14002d8c7  mov     r9d, 3Bh ; ';'
0x14002d8cd  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\dsreg\\win32\\ad"...
0x14002d8d4  mov     edx, 1
0x14002d8d9  mov     rcx, [rbp+30h]; Block
0x14002d8dd  call    ??3@YAXPEAXHPEBDH@Z; operator delete(void *,int,char const *,int)
0x14002d8e2  add     rsp, 20h
0x14002d8e6  pop     rbp
0x14002d8e7  retn
```
