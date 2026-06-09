# wil::details::ReportFailure_CaughtExceptionCommonNoReturnBase<3>(void *,uint,char const *,char const *,char const *,void *,ushort *,unsigned __int64,wil::SupportedExceptions)

- ea: `0x18001bfdc`
- end: `0x18001c0be`
- name: `??$ReportFailure_CaughtExceptionCommonNoReturnBase@$02@details@wil@@YA?AUResultStatus@01@PEAXIPEBD110PEAG_KW4SupportedExceptions@1@@Z`
- size: `226`
- prototype: `void __fastcall __noreturn(__int64, int, int, int, int, int, __int64, __int64, int, char)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001bf78`

## callees

- `0x18001bf40`
- `0x18001bfdc`
- `0x18001cd8c`
- `0x180026010`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_CaughtExceptionCommonNoReturnBase<3>(
        __int64 a1,
        int a2,
        int a3,
        int a4,
        int a5,
        int a6,
        __int64 a7,
        __int64 a8,
        int a9,
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
0x18001bfdc  mov     rax, rsp
0x18001bfdf  push    rbx
0x18001bfe0  push    rbp
0x18001bfe1  push    rsi
0x18001bfe2  push    rdi
0x18001bfe3  push    r14
0x18001bfe5  sub     rsp, 70h
0x18001bfe9  mov     rbx, [rsp+98h+arg_38]
0x18001bff1  xor     r14d, r14d
0x18001bff4  mov     [rax+50h], r14b
0x18001bff8  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18001bffc  mov     rdi, r9
0x18001bfff  mov     esi, r8d
0x18001c002  mov     rbp, rdx
0x18001c005  inc     rcx
0x18001c008  cmp     [rbx+rcx*2], r14w
0x18001c00d  jnz     short loc_18001C005
0x18001c00f  mov     rax, cs:g_pfnResultFromCaughtExceptionInternal
0x18001c016  test    rax, rax
0x18001c019  jz      short loc_18001C07D
0x18001c01b  lea     rdx, [rbx+rcx*2]
0x18001c01f  mov     r8d, 800h
0x18001c025  sub     r8, rcx
0x18001c028  lea     r9, [rsp+98h+arg_48]
0x18001c030  lea     rcx, [rsp+98h+var_38]
0x18001c035  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c03a  movsd   xmm0, qword ptr [rax]
0x18001c03e  mov     eax, [rax+8]
0x18001c041  mov     [rsp+98h+var_40], eax
0x18001c045  movd    eax, xmm0
0x18001c049  movsd   [rsp+98h+var_48], xmm0
0x18001c04f  test    eax, eax
0x18001c051  jns     short loc_18001C07D
0x18001c053  lea     rax, [rsp+98h+var_48]
0x18001c058  mov     [rsp+98h+var_60], rbx
0x18001c05d  mov     [rsp+98h+var_68], rax
0x18001c062  mov     r8, rdi
0x18001c065  mov     rax, [rsp+98h+arg_30]
0x18001c06d  mov     edx, esi
0x18001c06f  mov     rcx, rbp
0x18001c072  mov     [rsp+98h+var_70], rax
0x18001c077  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x18001c07d  mov     ecx, 8007023Eh; this
0x18001c082  mov     dword ptr [rsp+98h+var_48], ecx
0x18001c086  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18001c08b  mov     dword ptr [rsp+98h+var_48+4], eax
0x18001c08f  mov     r8, rdi
0x18001c092  lea     rax, [rsp+98h+var_48]
0x18001c097  mov     [rsp+98h+var_60], rbx
0x18001c09c  mov     [rsp+98h+var_68], rax
0x18001c0a1  mov     edx, esi
0x18001c0a3  mov     rax, [rsp+98h+arg_30]
0x18001c0ab  mov     rcx, rbp
0x18001c0ae  mov     [rsp+98h+var_70], rax
0x18001c0b3  mov     [rsp+98h+var_40], r14d
0x18001c0b8  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
