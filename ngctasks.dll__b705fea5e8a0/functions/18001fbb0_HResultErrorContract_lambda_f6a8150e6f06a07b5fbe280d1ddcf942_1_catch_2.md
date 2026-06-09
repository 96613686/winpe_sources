# _HResultErrorContract__lambda_f6a8150e6f06a07b5fbe280d1ddcf942____::_1_::catch$2

- ea: `0x18001fbb0`
- end: `0x18001fc04`
- name: `_HResultErrorContract__lambda_f6a8150e6f06a07b5fbe280d1ddcf942____::_1_::catch$2`
- size: `84`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180014b80`
- `0x18001fbb0`

## string_xrefs

- `0x18001fbe1`: `onecore\internal\ds\inc\private\security\ngc\inc\ec_hresult.h`

## pseudocode

```c
__int64 __fastcall HResultErrorContract__lambda_f6a8150e6f06a07b5fbe280d1ddcf942____::_1_::catch_2(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  signed int v4; // ecx

  v4 = *(_DWORD *)(*(_QWORD *)(a2 + 40) + 24LL);
  if ( v4 > 0 )
    v4 = (unsigned __int16)v4 | 0x80070000;
  *(_DWORD *)(a2 + 32) = v4;
  if ( v4 >= 0 )
    wil::details::in1diag3::_FailFast_Unexpected(
      *(wil::details::in1diag3 **)(a2 + 72),
      (void *)0x25,
      (unsigned int)"onecore\\internal\\ds\\inc\\private\\security\\ngc\\inc\\ec_hresult.h",
      a4);
  return 0;
}

```

## disassembly

```asm
0x18001fbb0  mov     [rsp+arg_8], rdx
0x18001fbb5  push    rbp
0x18001fbb6  sub     rsp, 20h
0x18001fbba  mov     rbp, rdx
0x18001fbbd  mov     rax, [rbp+28h]
0x18001fbc1  mov     ecx, [rax+18h]
0x18001fbc4  test    ecx, ecx
0x18001fbc6  jle     short loc_18001FBD1
0x18001fbc8  movzx   ecx, cx
0x18001fbcb  or      ecx, 80070000h
0x18001fbd1  mov     [rbp+20h], ecx
0x18001fbd4  test    ecx, ecx
0x18001fbd6  setns   al
0x18001fbd9  mov     rcx, [rbp+48h]; this
0x18001fbdd  test    al, al
0x18001fbdf  jz      short loc_18001FBF3
0x18001fbe1  lea     r8, aOnecoreInterna_1; "onecore\\internal\\ds\\inc\\private\\se"...
0x18001fbe8  mov     edx, 25h ; '%'; void *
0x18001fbed  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18001fbf3  mov     rax, 0
0x18001fbfd  add     rsp, 20h
0x18001fc01  pop     rbp
0x18001fc02  retn
```
