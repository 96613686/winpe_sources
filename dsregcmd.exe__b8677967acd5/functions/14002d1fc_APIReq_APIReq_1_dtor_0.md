# _APIReq::APIReq_::_1_::dtor$0

- ea: `0x14002d1fc`
- end: `0x14002d226`
- name: `_APIReq::APIReq_::_1_::dtor$0`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1400028ac`

## string_xrefs

- `0x14002d20b`: `onecore\ds\security\dsreg\win32\adal.native\APIHandle.h`

## pseudocode

```c
void __fastcall APIReq::APIReq_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  operator delete(*(void **)(a2 + 64));
}

```

## disassembly

```asm
0x14002d1fc  push    rbp
0x14002d1fe  sub     rsp, 20h
0x14002d202  mov     rbp, rdx
0x14002d205  mov     r9d, 44h ; 'D'
0x14002d20b  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\dsreg\\win32\\ad"...
0x14002d212  mov     edx, 1
0x14002d217  mov     rcx, [rbp+40h]; Block
0x14002d21b  call    ??3@YAXPEAXHPEBDH@Z; operator delete(void *,int,char const *,int)
0x14002d220  add     rsp, 20h
0x14002d224  pop     rbp
0x14002d225  retn
```
