# wil::details::ReportFailure_CaughtException<1>(void *,uint,char const *,char const *,char const *,void *,wil::SupportedExceptions)

- ea: `0x1800030e4`
- end: `0x18000322b`
- name: `??$ReportFailure_CaughtException@$00@details@wil@@YAJPEAXIPEBD110W4SupportedExceptions@1@@Z`
- size: `327`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180006a14`

## callees

- `0x180001600`
- `0x180002062`
- `0x180003014`
- `0x180003074`
- `0x1800030e4`
- `0x180005f2c`
- `0x18000ce90`
- `0x18000f010`

## string_xrefs

- `0x1800031a3`: `onecore\vm\dv\net\hns\computenetwork\src\hnsclient.cpp`
- `0x1800031fc`: `onecore\vm\dv\net\hns\computenetwork\src\hnsclient.cpp`

## pseudocode

```c
__int64 __fastcall wil::details::ReportFailure_CaughtException<1>(__int64 a1, unsigned int a2)
{
  int v4; // edx
  __int64 v5; // rcx
  unsigned __int64 *v6; // rax
  __m128i v7; // xmm0
  int v8; // r14d
  int v10; // r9d
  _BYTE v11[8]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v12; // [rsp+58h] [rbp-A8h]
  int v13; // [rsp+60h] [rbp-A0h]
  _BYTE v14[24]; // [rsp+68h] [rbp-98h] BYREF
  _WORD v15[2048]; // [rsp+80h] [rbp-80h] BYREF

  memset_0(v15, 0, sizeof(v15));
  v11[0] = 0;
  v5 = -1;
  do
    ++v5;
  while ( v15[v5] );
  if ( !g_pfnResultFromCaughtExceptionInternal
    || (v6 = (unsigned __int64 *)g_pfnResultFromCaughtExceptionInternal(v14, &v15[v5], 2048 - v5, v11),
        v7 = (__m128i)*v6,
        LODWORD(v6) = *((_DWORD *)v6 + 2),
        v8 = _mm_cvtsi128_si32(v7),
        v12 = v7.m128i_i64[0],
        v13 = (int)v6,
        v8 >= 0) )
  {
    LODWORD(v12) = -2147024322;
    HIDWORD(v12) = wil::details::HrToNtStatus((wil::details *)0x8007023ELL, v4);
    v13 = 0;
    wil::details::ReportFailure_Base<3,0>(
      a1,
      a2,
      (unsigned int)"onecore\\vm\\dv\\net\\hns\\computenetwork\\src\\hnsclient.cpp",
      v10);
  }
  wil::details::ReportFailure_Base<1,0>(a1, a2, "onecore\\vm\\dv\\net\\hns\\computenetwork\\src\\hnsclient.cpp");
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800030e4  mov     [rsp-8+arg_10], rbx
0x1800030e9  push    rbp
0x1800030ea  push    rsi
0x1800030eb  push    rdi
0x1800030ec  push    r14
0x1800030ee  push    r15
0x1800030f0  lea     rbp, [rsp-0F90h]
0x1800030f8  mov     eax, 1090h
0x1800030fd  call    _alloca_probe
0x180003102  sub     rsp, rax
0x180003105  mov     rax, cs:__security_cookie
0x18000310c  xor     rax, rsp
0x18000310f  mov     [rbp+0FB0h+var_30], rax
0x180003116  mov     rsi, [rbp+0FB0h+arg_28]
0x18000311d  mov     edi, edx
0x18000311f  mov     rbx, rcx
0x180003122  xor     edx, edx; Val
0x180003124  lea     rcx, [rbp+0FB0h+var_1030]; void *
0x180003128  mov     r8d, 1000h; Size
0x18000312e  call    memset_0
0x180003133  xor     r15d, r15d
0x180003136  lea     rax, [rbp+0FB0h+var_1030]
0x18000313a  mov     [rsp+10B0h+var_1060], r15b
0x18000313f  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180003143  inc     rcx
0x180003146  cmp     [rax+rcx*2], r15w
0x18000314b  jnz     short loc_180003143
0x18000314d  mov     rax, cs:g_pfnResultFromCaughtExceptionInternal
0x180003154  test    rax, rax
0x180003157  jz      loc_1800031EA
0x18000315d  mov     r8d, 800h
0x180003163  lea     rdx, [rbp+0FB0h+var_1030]
0x180003167  sub     r8, rcx
0x18000316a  lea     rdx, [rdx+rcx*2]
0x18000316e  lea     rcx, [rsp+10B0h+var_1048]
0x180003173  lea     r9, [rsp+10B0h+var_1060]
0x180003178  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000317d  movsd   xmm0, qword ptr [rax]
0x180003181  mov     eax, [rax+8]
0x180003184  movd    r14d, xmm0
0x180003189  movsd   [rsp+10B0h+var_1058], xmm0
0x18000318f  mov     [rsp+10B0h+var_1050], eax
0x180003193  test    r14d, r14d
0x180003196  jns     short loc_1800031EA
0x180003198  lea     rax, [rbp+0FB0h+var_1030]
0x18000319c  mov     edx, edi
0x18000319e  mov     [rsp+10B0h+var_1078], rax
0x1800031a3  lea     r8, aOnecoreVmDvNet; "onecore\\vm\\dv\\net\\hns\\computenetwo"...
0x1800031aa  lea     rax, [rsp+10B0h+var_1058]
0x1800031af  mov     rcx, rbx
0x1800031b2  mov     [rsp+10B0h+var_1080], rax
0x1800031b7  mov     [rsp+10B0h+var_1088], rsi
0x1800031bc  call    ??$ReportFailure_Base@$00$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<1,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x1800031c1  mov     eax, r14d
0x1800031c4  mov     rcx, [rbp+0FB0h+var_30]
0x1800031cb  xor     rcx, rsp; StackCookie
0x1800031ce  call    __security_check_cookie
0x1800031d3  mov     rbx, [rsp+10B0h+arg_10]
0x1800031db  add     rsp, 1090h
0x1800031e2  pop     r15
0x1800031e4  pop     r14
0x1800031e6  pop     rdi
0x1800031e7  pop     rsi
0x1800031e8  pop     rbp
0x1800031e9  retn
0x1800031ea  mov     ecx, 8007023Eh; this
0x1800031ef  mov     dword ptr [rsp+10B0h+var_1058], ecx
0x1800031f3  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800031f8  mov     dword ptr [rsp+10B0h+var_1058+4], eax
0x1800031fc  lea     r8, aOnecoreVmDvNet; "onecore\\vm\\dv\\net\\hns\\computenetwo"...
0x180003203  lea     rax, [rbp+0FB0h+var_1030]
0x180003207  mov     [rsp+10B0h+var_1050], r15d
0x18000320c  mov     [rsp+10B0h+var_1078], rax
0x180003211  mov     edx, edi
0x180003213  lea     rax, [rsp+10B0h+var_1058]
0x180003218  mov     rcx, rbx
0x18000321b  mov     [rsp+10B0h+var_1080], rax
0x180003220  mov     [rsp+10B0h+var_1088], rsi
0x180003225  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
