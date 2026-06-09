# _HResultErrorContract__lambda_514ebcd38fae32d194ac3c19075a19d8____::_1_::catch$2

- ea: `0x18002504f`
- end: `0x1800250a3`
- name: `_HResultErrorContract__lambda_514ebcd38fae32d194ac3c19075a19d8____::_1_::catch$2`
- size: `84`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000c5c0`
- `0x18002504f`

## string_xrefs

- `0x180025080`: `OneCore\internal\DS\inc\private\security\ngc\inc\ec_hresult.h`

## pseudocode

```c
__int64 __fastcall HResultErrorContract__lambda_514ebcd38fae32d194ac3c19075a19d8____::_1_::catch_2(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  signed int v4; // ecx

  v4 = *(_DWORD *)(*(_QWORD *)(a2 + 32) + 24LL);
  if ( v4 > 0 )
    v4 = (unsigned __int16)v4 | 0x80070000;
  *(_DWORD *)(a2 + 88) = v4;
  if ( v4 >= 0 )
    wil::details::in1diag3::_FailFast_Unexpected(
      *(wil::details::in1diag3 **)(a2 + 72),
      (void *)0x25,
      (unsigned int)"OneCore\\internal\\DS\\inc\\private\\security\\ngc\\inc\\ec_hresult.h",
      a4);
  return 0;
}

```

## disassembly

```asm
0x18002504f  mov     [rsp+arg_8], rdx
0x180025054  push    rbp
0x180025055  sub     rsp, 20h
0x180025059  mov     rbp, rdx
0x18002505c  mov     rax, [rbp+20h]
0x180025060  mov     ecx, [rax+18h]
0x180025063  test    ecx, ecx
0x180025065  jle     short loc_180025070
0x180025067  movzx   ecx, cx
0x18002506a  or      ecx, 80070000h
0x180025070  mov     [rbp+58h], ecx
0x180025073  test    ecx, ecx
0x180025075  setns   al
0x180025078  mov     rcx, [rbp+48h]; this
0x18002507c  test    al, al
0x18002507e  jz      short loc_180025092
0x180025080  lea     r8, aOnecoreInterna_1; "OneCore\\internal\\DS\\inc\\private\\se"...
0x180025087  mov     edx, 25h ; '%'; void *
0x18002508c  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180025092  mov     rax, 0
0x18002509c  add     rsp, 20h
0x1800250a0  pop     rbp
0x1800250a1  retn
```
