# _CflApiNew::DeserializeSessionContext_::_1_::catch$51

- ea: `0x18002faa7`
- end: `0x18002fae4`
- name: `_CflApiNew::DeserializeSessionContext_::_1_::catch$51`
- size: `61`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800067c4`

## string_xrefs

- `0x18002fac1`: `onecore\ds\security\cfl\api\lib\cflapiimplnew.cpp`

## pseudocode

```c
__int64 __fastcall CflApiNew::DeserializeSessionContext_::_1_::catch_51(__int64 a1, __int64 a2)
{
  int v3; // [rsp+20h] [rbp-18h]

  wil::details::in1diag3::Return_Hr(
    *(wil::details::in1diag3 **)(a2 + 504),
    (void *)0x16E,
    (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimplnew.cpp",
    (const char *)0x80090005LL,
    v3);
  return 0;
}

```

## disassembly

```asm
0x18002faa7  mov     [rsp+arg_8], rdx
0x18002faac  push    rbp
0x18002faad  sub     rsp, 30h
0x18002fab1  mov     rbp, rdx
0x18002fab4  mov     rcx, [rbp+1F8h]; this
0x18002fabb  mov     r9d, 80090005h; char *
0x18002fac1  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x18002fac8  mov     edx, 16Eh; void *
0x18002facd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002fad2  nop
0x18002fad3  mov     rax, 0
0x18002fadd  add     rsp, 30h
0x18002fae1  pop     rbp
0x18002fae2  retn
```
