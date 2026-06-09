# wil::details::ReportFailure_CaughtException<1>(void *,uint,char const *,char const *,char const *,void *,wil::SupportedExceptions)

- ea: `0x180007d88`
- end: `0x180007ecf`
- name: `??$ReportFailure_CaughtException@$00@details@wil@@YAJPEAXIPEBD110W4SupportedExceptions@1@@Z`
- size: `327`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000c72c`

## callees

- `0x180002490`
- `0x180002ef8`
- `0x180003d74`
- `0x180003dd4`
- `0x180005d80`
- `0x180007d88`
- `0x18002df90`
- `0x180030010`

## string_xrefs

- `0x180007e47`: `onecore\ds\security\cfl\api\dll\entrypoints.cpp`
- `0x180007ea0`: `onecore\ds\security\cfl\api\dll\entrypoints.cpp`

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
      (unsigned int)"onecore\\ds\\security\\cfl\\api\\dll\\entrypoints.cpp",
      v10);
  }
  wil::details::ReportFailure_Base<1,0>(a1, a2, "onecore\\ds\\security\\cfl\\api\\dll\\entrypoints.cpp");
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180007d88  mov     [rsp-8+arg_10], rbx
0x180007d8d  push    rbp
0x180007d8e  push    rsi
0x180007d8f  push    rdi
0x180007d90  push    r14
0x180007d92  push    r15
0x180007d94  lea     rbp, [rsp-0F90h]
0x180007d9c  mov     eax, 1090h
0x180007da1  call    _alloca_probe
0x180007da6  sub     rsp, rax
0x180007da9  mov     rax, cs:__security_cookie
0x180007db0  xor     rax, rsp
0x180007db3  mov     [rbp+0FB0h+var_30], rax
0x180007dba  mov     rsi, [rbp+0FB0h+arg_28]
0x180007dc1  mov     edi, edx
0x180007dc3  mov     rbx, rcx
0x180007dc6  xor     edx, edx; Val
0x180007dc8  lea     rcx, [rbp+0FB0h+var_1030]; void *
0x180007dcc  mov     r8d, 1000h; Size
0x180007dd2  call    memset_0
0x180007dd7  xor     r15d, r15d
0x180007dda  lea     rax, [rbp+0FB0h+var_1030]
0x180007dde  mov     [rsp+10B0h+var_1060], r15b
0x180007de3  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180007de7  inc     rcx
0x180007dea  cmp     [rax+rcx*2], r15w
0x180007def  jnz     short loc_180007DE7
0x180007df1  mov     rax, cs:g_pfnResultFromCaughtExceptionInternal
0x180007df8  test    rax, rax
0x180007dfb  jz      loc_180007E8E
0x180007e01  mov     r8d, 800h
0x180007e07  lea     rdx, [rbp+0FB0h+var_1030]
0x180007e0b  sub     r8, rcx
0x180007e0e  lea     rdx, [rdx+rcx*2]
0x180007e12  lea     rcx, [rsp+10B0h+var_1048]
0x180007e17  lea     r9, [rsp+10B0h+var_1060]
0x180007e1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007e21  movsd   xmm0, qword ptr [rax]
0x180007e25  mov     eax, [rax+8]
0x180007e28  movd    r14d, xmm0
0x180007e2d  movsd   [rsp+10B0h+var_1058], xmm0
0x180007e33  mov     [rsp+10B0h+var_1050], eax
0x180007e37  test    r14d, r14d
0x180007e3a  jns     short loc_180007E8E
0x180007e3c  lea     rax, [rbp+0FB0h+var_1030]
0x180007e40  mov     edx, edi
0x180007e42  mov     [rsp+10B0h+var_1078], rax
0x180007e47  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cfl\\api\\dll\\e"...
0x180007e4e  lea     rax, [rsp+10B0h+var_1058]
0x180007e53  mov     rcx, rbx
0x180007e56  mov     [rsp+10B0h+var_1080], rax
0x180007e5b  mov     [rsp+10B0h+var_1088], rsi
0x180007e60  call    ??$ReportFailure_Base@$00$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<1,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x180007e65  mov     eax, r14d
0x180007e68  mov     rcx, [rbp+0FB0h+var_30]
0x180007e6f  xor     rcx, rsp; StackCookie
0x180007e72  call    __security_check_cookie
0x180007e77  mov     rbx, [rsp+10B0h+arg_10]
0x180007e7f  add     rsp, 1090h
0x180007e86  pop     r15
0x180007e88  pop     r14
0x180007e8a  pop     rdi
0x180007e8b  pop     rsi
0x180007e8c  pop     rbp
0x180007e8d  retn
0x180007e8e  mov     ecx, 8007023Eh; this
0x180007e93  mov     dword ptr [rsp+10B0h+var_1058], ecx
0x180007e97  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180007e9c  mov     dword ptr [rsp+10B0h+var_1058+4], eax
0x180007ea0  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cfl\\api\\dll\\e"...
0x180007ea7  lea     rax, [rbp+0FB0h+var_1030]
0x180007eab  mov     [rsp+10B0h+var_1050], r15d
0x180007eb0  mov     [rsp+10B0h+var_1078], rax
0x180007eb5  mov     edx, edi
0x180007eb7  lea     rax, [rsp+10B0h+var_1058]
0x180007ebc  mov     rcx, rbx
0x180007ebf  mov     [rsp+10B0h+var_1080], rax
0x180007ec4  mov     [rsp+10B0h+var_1088], rsi
0x180007ec9  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
