# _HResultErrorContract__lambda_f6a8150e6f06a07b5fbe280d1ddcf942____::_1_::catch$4

- ea: `0x18001fc57`
- end: `0x18001fc9e`
- name: `_HResultErrorContract__lambda_f6a8150e6f06a07b5fbe280d1ddcf942____::_1_::catch$4`
- size: `71`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180014b80`
- `0x18001fc57`

## string_xrefs

- `0x18001fc7b`: `onecore\internal\ds\inc\private\security\ngc\inc\ec_hresult.h`

## pseudocode

```c
__int64 __fastcall HResultErrorContract__lambda_f6a8150e6f06a07b5fbe280d1ddcf942____::_1_::catch_4(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  int v4; // ecx

  v4 = *(_DWORD *)(*(_QWORD *)(a2 + 56) + 32LL);
  *(_DWORD *)(a2 + 32) = v4;
  if ( v4 >= 0 )
    wil::details::in1diag3::_FailFast_Unexpected(
      *(wil::details::in1diag3 **)(a2 + 72),
      (void *)0x2F,
      (unsigned int)"onecore\\internal\\ds\\inc\\private\\security\\ngc\\inc\\ec_hresult.h",
      a4);
  return 0;
}

```

## disassembly

```asm
0x18001fc57  mov     [rsp+arg_8], rdx
0x18001fc5c  push    rbp
0x18001fc5d  sub     rsp, 20h
0x18001fc61  mov     rbp, rdx
0x18001fc64  mov     rax, [rbp+38h]
0x18001fc68  mov     ecx, [rax+20h]
0x18001fc6b  mov     [rbp+20h], ecx
0x18001fc6e  test    ecx, ecx
0x18001fc70  setns   al
0x18001fc73  mov     rcx, [rbp+48h]; this
0x18001fc77  test    al, al
0x18001fc79  jz      short loc_18001FC8D
0x18001fc7b  lea     r8, aOnecoreInterna_1; "onecore\\internal\\ds\\inc\\private\\se"...
0x18001fc82  mov     edx, 2Fh ; '/'; void *
0x18001fc87  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18001fc8d  mov     rax, 0
0x18001fc97  add     rsp, 20h
0x18001fc9b  pop     rbp
0x18001fc9c  retn
```
