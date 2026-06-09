# _HResultErrorContract__lambda_514ebcd38fae32d194ac3c19075a19d8____::_1_::catch$3

- ea: `0x1800250a9`
- end: `0x1800250f0`
- name: `_HResultErrorContract__lambda_514ebcd38fae32d194ac3c19075a19d8____::_1_::catch$3`
- size: `71`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000c5c0`
- `0x1800250a9`

## string_xrefs

- `0x1800250cd`: `OneCore\internal\DS\inc\private\security\ngc\inc\ec_hresult.h`

## pseudocode

```c
__int64 __fastcall HResultErrorContract__lambda_514ebcd38fae32d194ac3c19075a19d8____::_1_::catch_3(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  int v4; // ecx

  v4 = *(_DWORD *)(*(_QWORD *)(a2 + 40) + 24LL);
  *(_DWORD *)(a2 + 88) = v4;
  if ( v4 >= 0 )
    wil::details::in1diag3::_FailFast_Unexpected(
      *(wil::details::in1diag3 **)(a2 + 72),
      (void *)0x2A,
      (unsigned int)"OneCore\\internal\\DS\\inc\\private\\security\\ngc\\inc\\ec_hresult.h",
      a4);
  return 0;
}

```

## disassembly

```asm
0x1800250a9  mov     [rsp+arg_8], rdx
0x1800250ae  push    rbp
0x1800250af  sub     rsp, 20h
0x1800250b3  mov     rbp, rdx
0x1800250b6  mov     rax, [rbp+28h]
0x1800250ba  mov     ecx, [rax+18h]
0x1800250bd  mov     [rbp+58h], ecx
0x1800250c0  test    ecx, ecx
0x1800250c2  setns   al
0x1800250c5  mov     rcx, [rbp+48h]; this
0x1800250c9  test    al, al
0x1800250cb  jz      short loc_1800250DF
0x1800250cd  lea     r8, aOnecoreInterna_1; "OneCore\\internal\\DS\\inc\\private\\se"...
0x1800250d4  mov     edx, 2Ah ; '*'; void *
0x1800250d9  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800250df  mov     rax, 0
0x1800250e9  add     rsp, 20h
0x1800250ed  pop     rbp
0x1800250ee  retn
```
