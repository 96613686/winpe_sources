# wil::details::ReportFailure_CaughtExceptionCommonNoReturnBase<3>(void *,uint,char const *,char const *,char const *,void *,ushort *,unsigned __int64,wil::SupportedExceptions)

- ea: `0x18000d7a0`
- end: `0x18000d88e`
- name: `??$ReportFailure_CaughtExceptionCommonNoReturnBase@$02@details@wil@@YA?AUResultStatus@01@PEAXIPEBD110PEAG_KW4SupportedExceptions@1@@Z`
- size: `238`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000d770`

## callees

- `0x1800068ec`
- `0x180009380`
- `0x18000d7a0`
- `0x180028010`

## string_xrefs

- `0x18000d825`: `OneCore\internal\DS\inc\private\security\ngc\inc\ec_hresult.h`
- `0x18000d859`: `OneCore\internal\DS\inc\private\security\ngc\inc\ec_hresult.h`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_CaughtExceptionCommonNoReturnBase<3>(
        __int64 a1,
        int a2,
        int a3,
        __int64 a4,
        int a5,
        int a6,
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
        (unsigned int)"OneCore\\internal\\DS\\inc\\private\\security\\ngc\\inc\\ec_hresult.h",
        v10);
  }
  wil::details::HrToNtStatus((wil::details *)0x8007023ELL, a2);
  wil::details::ReportFailure_Base<3,0>(
    a2,
    49,
    (unsigned int)"OneCore\\internal\\DS\\inc\\private\\security\\ngc\\inc\\ec_hresult.h",
    v11);
}

```

## disassembly

```asm
0x18000d7a0  mov     rax, rsp
0x18000d7a3  mov     [rax+8], rbx
0x18000d7a7  mov     [rax+10h], rsi
0x18000d7ab  mov     [rax+18h], r8d
0x18000d7af  push    rdi
0x18000d7b0  sub     rsp, 70h
0x18000d7b4  mov     rbx, [rsp+78h+arg_38]
0x18000d7bc  xor     esi, esi
0x18000d7be  mov     [rax+18h], sil
0x18000d7c2  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000d7c6  mov     rdi, rdx
0x18000d7c9  inc     rcx
0x18000d7cc  cmp     [rbx+rcx*2], si
0x18000d7d0  jnz     short loc_18000D7C9
0x18000d7d2  mov     rax, cs:g_pfnResultFromCaughtExceptionInternal
0x18000d7d9  test    rax, rax
0x18000d7dc  jz      short loc_18000D847
0x18000d7de  lea     rdx, [rbx+rcx*2]
0x18000d7e2  mov     r8d, 800h
0x18000d7e8  sub     r8, rcx
0x18000d7eb  lea     r9, [rsp+78h+arg_10]
0x18000d7f3  lea     rcx, [rsp+78h+var_18]
0x18000d7f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d7fd  movsd   xmm0, qword ptr [rax]
0x18000d801  mov     eax, [rax+8]
0x18000d804  mov     [rsp+78h+var_20], eax
0x18000d808  movd    eax, xmm0
0x18000d80c  movsd   [rsp+78h+var_28], xmm0
0x18000d812  test    eax, eax
0x18000d814  jns     short loc_18000D847
0x18000d816  lea     rax, [rsp+78h+var_28]
0x18000d81b  mov     [rsp+78h+var_40], rbx
0x18000d820  mov     [rsp+78h+var_48], rax
0x18000d825  lea     r8, aOnecoreInterna_1; "OneCore\\internal\\DS\\inc\\private\\se"...
0x18000d82c  mov     rax, [rsp+78h+arg_30]
0x18000d834  mov     edx, 31h ; '1'
0x18000d839  mov     rcx, rdi
0x18000d83c  mov     [rsp+78h+var_50], rax
0x18000d841  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x18000d847  mov     ecx, 8007023Eh; this
0x18000d84c  mov     dword ptr [rsp+78h+var_28], ecx
0x18000d850  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000d855  mov     dword ptr [rsp+78h+var_28+4], eax
0x18000d859  lea     r8, aOnecoreInterna_1; "OneCore\\internal\\DS\\inc\\private\\se"...
0x18000d860  lea     rax, [rsp+78h+var_28]
0x18000d865  mov     [rsp+78h+var_40], rbx
0x18000d86a  mov     [rsp+78h+var_48], rax
0x18000d86f  mov     edx, 31h ; '1'
0x18000d874  mov     rax, [rsp+78h+arg_30]
0x18000d87c  mov     rcx, rdi
0x18000d87f  mov     [rsp+78h+var_50], rax
0x18000d884  mov     [rsp+78h+var_20], esi
0x18000d888  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
