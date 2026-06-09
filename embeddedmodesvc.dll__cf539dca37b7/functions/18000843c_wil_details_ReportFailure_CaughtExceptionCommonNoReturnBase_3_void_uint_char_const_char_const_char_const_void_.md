# wil::details::ReportFailure_CaughtExceptionCommonNoReturnBase<3>(void *,uint,char const *,char const *,char const *,void *,ushort *,unsigned __int64,wil::SupportedExceptions)

- ea: `0x18000843c`
- end: `0x18000851e`
- name: `??$ReportFailure_CaughtExceptionCommonNoReturnBase@$02@details@wil@@YA?AUResultStatus@01@PEAXIPEBD110PEAG_KW4SupportedExceptions@1@@Z`
- size: `226`
- prototype: `void __fastcall __noreturn(__int64, int, int, int, __int64, __int64, __int64, __int64, __int64, char)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000840c`

## callees

- `0x180003a28`
- `0x1800053cc`
- `0x18000843c`
- `0x18001b010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall __noreturn wil::details::ReportFailure_CaughtExceptionCommonNoReturnBase<3>(
        __int64 a1,
        int a2,
        int a3,
        int a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        char a10)
{
  __int64 v10; // rcx
  int v14; // r9d
  int v15; // r9d
  _BYTE v16[56]; // [rsp+60h] [rbp-38h] BYREF

  a10 = 0;
  v10 = -1;
  do
    ++v10;
  while ( *(_WORD *)(a8 + 2 * v10) );
  if ( g_pfnResultFromCaughtExceptionInternal )
  {
    if ( _mm_cvtsi128_si32((__m128i)*(unsigned __int64 *)g_pfnResultFromCaughtExceptionInternal(
                                                           v16,
                                                           a8 + 2 * v10,
                                                           2048 - v10,
                                                           &a10)) < 0 )
      wil::details::ReportFailure_Base<3,0>(a2, a3, a4, v14);
  }
  wil::details::HrToNtStatus((wil::details *)0x8007023ELL, a2);
  wil::details::ReportFailure_Base<3,0>(a2, a3, a4, v15);
}

```

## disassembly

```asm
0x18000843c  mov     rax, rsp
0x18000843f  push    rbx
0x180008440  push    rbp
0x180008441  push    rsi
0x180008442  push    rdi
0x180008443  push    r14
0x180008445  sub     rsp, 70h
0x180008449  mov     rbx, [rsp+98h+arg_38]
0x180008451  xor     r14d, r14d
0x180008454  mov     [rax+50h], r14b
0x180008458  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000845c  mov     rdi, r9
0x18000845f  mov     esi, r8d
0x180008462  mov     rbp, rdx
0x180008465  inc     rcx
0x180008468  cmp     [rbx+rcx*2], r14w
0x18000846d  jnz     short loc_180008465
0x18000846f  mov     rax, cs:g_pfnResultFromCaughtExceptionInternal
0x180008476  test    rax, rax
0x180008479  jz      short loc_1800084DD
0x18000847b  lea     rdx, [rbx+rcx*2]
0x18000847f  mov     r8d, 800h
0x180008485  sub     r8, rcx
0x180008488  lea     r9, [rsp+98h+arg_48]
0x180008490  lea     rcx, [rsp+98h+var_38]
0x180008495  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000849a  movsd   xmm0, qword ptr [rax]
0x18000849e  mov     eax, [rax+8]
0x1800084a1  mov     [rsp+98h+var_40], eax
0x1800084a5  movd    eax, xmm0
0x1800084a9  movsd   [rsp+98h+var_48], xmm0
0x1800084af  test    eax, eax
0x1800084b1  jns     short loc_1800084DD
0x1800084b3  lea     rax, [rsp+98h+var_48]
0x1800084b8  mov     [rsp+98h+var_60], rbx
0x1800084bd  mov     [rsp+98h+var_68], rax
0x1800084c2  mov     r8, rdi
0x1800084c5  mov     rax, [rsp+98h+arg_30]
0x1800084cd  mov     edx, esi
0x1800084cf  mov     rcx, rbp
0x1800084d2  mov     [rsp+98h+var_70], rax
0x1800084d7  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x1800084dd  mov     ecx, 8007023Eh; this
0x1800084e2  mov     dword ptr [rsp+98h+var_48], ecx
0x1800084e6  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800084eb  mov     dword ptr [rsp+98h+var_48+4], eax
0x1800084ef  mov     r8, rdi
0x1800084f2  lea     rax, [rsp+98h+var_48]
0x1800084f7  mov     [rsp+98h+var_60], rbx
0x1800084fc  mov     [rsp+98h+var_68], rax
0x180008501  mov     edx, esi
0x180008503  mov     rax, [rsp+98h+arg_30]
0x18000850b  mov     rcx, rbp
0x18000850e  mov     [rsp+98h+var_70], rax
0x180008513  mov     [rsp+98h+var_40], r14d
0x180008518  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
