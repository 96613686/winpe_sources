# _CflApi::DeserializeSessionContext_::_1_::catch$50

- ea: `0x18002f44a`
- end: `0x18002f487`
- name: `_CflApi::DeserializeSessionContext_::_1_::catch$50`
- size: `61`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800067c4`

## string_xrefs

- `0x18002f464`: `onecore\ds\security\cfl\api\lib\cflapiimpl.cpp`

## pseudocode

```c
__int64 __fastcall CflApi::DeserializeSessionContext_::_1_::catch_50(__int64 a1, __int64 a2)
{
  int v3; // [rsp+20h] [rbp-18h]

  wil::details::in1diag3::Return_Hr(
    *(wil::details::in1diag3 **)(a2 + 488),
    (void *)0x286,
    (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimpl.cpp",
    (const char *)0x80090005LL,
    v3);
  return 0;
}

```

## disassembly

```asm
0x18002f44a  mov     [rsp+arg_8], rdx
0x18002f44f  push    rbp
0x18002f450  sub     rsp, 30h
0x18002f454  mov     rbp, rdx
0x18002f457  mov     rcx, [rbp+1E8h]; this
0x18002f45e  mov     r9d, 80090005h; char *
0x18002f464  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x18002f46b  mov     edx, 286h; void *
0x18002f470  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002f475  nop
0x18002f476  mov     rax, 0
0x18002f480  add     rsp, 30h
0x18002f484  pop     rbp
0x18002f485  retn
```
