# wil::details::ReportFailure_CaughtExceptionCommonNoReturnBase<3>(void *,uint,char const *,char const *,char const *,void *,ushort *,unsigned __int64,wil::SupportedExceptions)

- ea: `0x18000fc68`
- end: `0x18000fd56`
- name: `??$ReportFailure_CaughtExceptionCommonNoReturnBase@$02@details@wil@@YA?AUResultStatus@01@PEAXIPEBD110PEAG_KW4SupportedExceptions@1@@Z`
- size: `238`
- prototype: `void __fastcall __noreturn(__int64, int, int, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000fc38`

## callees

- `0x1800077bc`
- `0x18000ae80`
- `0x18000fc68`
- `0x180022010`

## string_xrefs

- `0x18000fced`: `onecore\internal\ds\inc\private\security\ngc\inc\ec_hresult.h`
- `0x18000fd21`: `onecore\internal\ds\inc\private\security\ngc\inc\ec_hresult.h`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_CaughtExceptionCommonNoReturnBase<3>(
        __int64 a1,
        int a2,
        int a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8)
{
  __int64 v8; // rcx
  int v10; // r9d
  int v11; // r9d
  _BYTE v12[24]; // [rsp+60h] [rbp-18h] BYREF
  int v13; // [rsp+90h] [rbp+18h] BYREF

  v13 = a3;
  LOBYTE(v13) = 0;
  v8 = -1;
  do
    ++v8;
  while ( *(_WORD *)(a8 + 2 * v8) );
  if ( g_pfnResultFromCaughtExceptionInternal )
  {
    if ( _mm_cvtsi128_si32((__m128i)*(unsigned __int64 *)g_pfnResultFromCaughtExceptionInternal(
                                                           v12,
                                                           a8 + 2 * v8,
                                                           2048 - v8,
                                                           &v13)) < 0 )
      wil::details::ReportFailure_Base<3,0>(
        a2,
        49,
        (unsigned int)"onecore\\internal\\ds\\inc\\private\\security\\ngc\\inc\\ec_hresult.h",
        v10);
  }
  wil::details::HrToNtStatus((wil::details *)0x8007023ELL, a2);
  wil::details::ReportFailure_Base<3,0>(
    a2,
    49,
    (unsigned int)"onecore\\internal\\ds\\inc\\private\\security\\ngc\\inc\\ec_hresult.h",
    v11);
}

```

## disassembly

```asm
0x18000fc68  mov     rax, rsp
0x18000fc6b  mov     [rax+8], rbx
0x18000fc6f  mov     [rax+10h], rsi
0x18000fc73  mov     [rax+18h], r8d
0x18000fc77  push    rdi
0x18000fc78  sub     rsp, 70h
0x18000fc7c  mov     rbx, [rsp+78h+arg_38]
0x18000fc84  xor     esi, esi
0x18000fc86  mov     [rax+18h], sil
0x18000fc8a  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000fc8e  mov     rdi, rdx
0x18000fc91  inc     rcx
0x18000fc94  cmp     [rbx+rcx*2], si
0x18000fc98  jnz     short loc_18000FC91
0x18000fc9a  mov     rax, cs:g_pfnResultFromCaughtExceptionInternal
0x18000fca1  test    rax, rax
0x18000fca4  jz      short loc_18000FD0F
0x18000fca6  lea     rdx, [rbx+rcx*2]
0x18000fcaa  mov     r8d, 800h
0x18000fcb0  sub     r8, rcx
0x18000fcb3  lea     r9, [rsp+78h+arg_10]
0x18000fcbb  lea     rcx, [rsp+78h+var_18]
0x18000fcc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fcc5  movsd   xmm0, qword ptr [rax]
0x18000fcc9  mov     eax, [rax+8]
0x18000fccc  mov     [rsp+78h+var_20], eax
0x18000fcd0  movd    eax, xmm0
0x18000fcd4  movsd   [rsp+78h+var_28], xmm0
0x18000fcda  test    eax, eax
0x18000fcdc  jns     short loc_18000FD0F
0x18000fcde  lea     rax, [rsp+78h+var_28]
0x18000fce3  mov     [rsp+78h+var_40], rbx
0x18000fce8  mov     [rsp+78h+var_48], rax
0x18000fced  lea     r8, aOnecoreInterna_1; "onecore\\internal\\ds\\inc\\private\\se"...
0x18000fcf4  mov     rax, [rsp+78h+arg_30]
0x18000fcfc  mov     edx, 31h ; '1'
0x18000fd01  mov     rcx, rdi
0x18000fd04  mov     [rsp+78h+var_50], rax
0x18000fd09  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x18000fd0f  mov     ecx, 8007023Eh; this
0x18000fd14  mov     dword ptr [rsp+78h+var_28], ecx
0x18000fd18  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000fd1d  mov     dword ptr [rsp+78h+var_28+4], eax
0x18000fd21  lea     r8, aOnecoreInterna_1; "onecore\\internal\\ds\\inc\\private\\se"...
0x18000fd28  lea     rax, [rsp+78h+var_28]
0x18000fd2d  mov     [rsp+78h+var_40], rbx
0x18000fd32  mov     [rsp+78h+var_48], rax
0x18000fd37  mov     edx, 31h ; '1'
0x18000fd3c  mov     rax, [rsp+78h+arg_30]
0x18000fd44  mov     rcx, rdi
0x18000fd47  mov     [rsp+78h+var_50], rax
0x18000fd4c  mov     [rsp+78h+var_20], esi
0x18000fd50  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
