# _HResultErrorContract__lambda_f6a8150e6f06a07b5fbe280d1ddcf942____::_1_::catch$3

- ea: `0x18001fc0a`
- end: `0x18001fc51`
- name: `_HResultErrorContract__lambda_f6a8150e6f06a07b5fbe280d1ddcf942____::_1_::catch$3`
- size: `71`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180014b80`
- `0x18001fc0a`

## string_xrefs

- `0x18001fc2e`: `onecore\internal\ds\inc\private\security\ngc\inc\ec_hresult.h`

## pseudocode

```c
__int64 __fastcall HResultErrorContract__lambda_f6a8150e6f06a07b5fbe280d1ddcf942____::_1_::catch_3(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  int v4; // ecx

  v4 = *(_DWORD *)(*(_QWORD *)(a2 + 48) + 24LL);
  *(_DWORD *)(a2 + 32) = v4;
  if ( v4 >= 0 )
    wil::details::in1diag3::_FailFast_Unexpected(
      *(wil::details::in1diag3 **)(a2 + 72),
      (void *)0x2A,
      (unsigned int)"onecore\\internal\\ds\\inc\\private\\security\\ngc\\inc\\ec_hresult.h",
      a4);
  return 0;
}

```

## disassembly

```asm
0x18001fc0a  mov     [rsp+arg_8], rdx
0x18001fc0f  push    rbp
0x18001fc10  sub     rsp, 20h
0x18001fc14  mov     rbp, rdx
0x18001fc17  mov     rax, [rbp+30h]
0x18001fc1b  mov     ecx, [rax+18h]
0x18001fc1e  mov     [rbp+20h], ecx
0x18001fc21  test    ecx, ecx
0x18001fc23  setns   al
0x18001fc26  mov     rcx, [rbp+48h]; this
0x18001fc2a  test    al, al
0x18001fc2c  jz      short loc_18001FC40
0x18001fc2e  lea     r8, aOnecoreInterna_1; "onecore\\internal\\ds\\inc\\private\\se"...
0x18001fc35  mov     edx, 2Ah ; '*'; void *
0x18001fc3a  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18001fc40  mov     rax, 0
0x18001fc4a  add     rsp, 20h
0x18001fc4e  pop     rbp
0x18001fc4f  retn
```
