# wil::details::ReportFailure_CaughtExceptionCommonNoReturnBase<0>(void *,uint,char const *,char const *,char const *,void *,wchar_t *,unsigned __int64,wil::SupportedExceptions)

- ea: `0x18000b620`
- end: `0x18000b70c`
- name: `??$ReportFailure_CaughtExceptionCommonNoReturnBase@$0A@@details@wil@@YA?AUResultStatus@01@PEAXIPEBD110PEA_W_KW4SupportedExceptions@1@@Z`
- size: `236`
- prototype: `void __fastcall __noreturn(__int64, int, int, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000b5f0`

## callees

- `0x1800032c4`
- `0x1800057f4`
- `0x180007c30`
- `0x18000b620`
- `0x180017010`

## string_xrefs

- `0x18000b6b7`: `servercommon\base\securehostingservice\common\service\lib\hgservicecontroller.cpp`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_CaughtExceptionCommonNoReturnBase<0>(
        __int64 a1,
        int a2,
        int a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8)
{
  __int64 v8; // rdi
  __int64 v9; // rcx
  int v10; // esi
  int v11; // ebx
  unsigned __int64 *v12; // rax
  int v13; // r9d
  __m128i v14; // xmm0
  char v15; // dl
  int v16; // [rsp+20h] [rbp-50h]
  __int64 v17; // [rsp+50h] [rbp-20h] BYREF
  int v18; // [rsp+58h] [rbp-18h]
  _BYTE v19[16]; // [rsp+60h] [rbp-10h] BYREF
  int v20; // [rsp+A0h] [rbp+30h] BYREF

  v20 = a3;
  v8 = a8;
  LOBYTE(v20) = 0;
  v9 = -1;
  v10 = a2;
  do
    ++v9;
  while ( *(_WORD *)(a8 + 2 * v9) );
  v11 = 1;
  if ( g_pfnResultFromCaughtExceptionInternal
    && (v12 = (unsigned __int64 *)g_pfnResultFromCaughtExceptionInternal(v19, a8 + 2 * v9, 2048 - v9, &v20),
        v14 = (__m128i)*v12,
        v18 = *((_DWORD *)v12 + 2),
        v17 = v14.m128i_i64[0],
        _mm_cvtsi128_si32(v14) < 0) )
  {
    v15 = 1;
  }
  else
  {
    LOBYTE(a2) = 0;
    LODWORD(v17) = -2147024322;
    HIDWORD(v17) = wil::details::HrToNtStatus((wil::details *)0x8007023ELL, a2);
    v18 = 0;
  }
  if ( (_BYTE)v20 )
    v11 = 3;
  if ( v15 )
    wil::details::ReportFailure_Base<0,0>(
      v10,
      630,
      (int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\hgservicecontroller.cpp",
      v13,
      v16,
      a7,
      (__int64)&v17,
      v8,
      v11);
  wil::details::ReportFailure_Base<3,0>(
    v10,
    630,
    (int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\hgservicecontroller.cpp",
    v13,
    v16,
    a7,
    (__int64)&v17,
    v8);
}

```

## disassembly

```asm
0x18000b620  mov     [rsp-18h+arg_0], rbx
0x18000b625  mov     [rsp-18h+arg_8], rsi
0x18000b62a  mov     [rsp-18h+arg_10], r8d
0x18000b62f  push    rbp
0x18000b630  push    rdi
0x18000b631  push    r14
0x18000b633  mov     rbp, rsp
0x18000b636  sub     rsp, 70h
0x18000b63a  mov     rdi, [rbp+arg_38]
0x18000b63e  xor     r14d, r14d
0x18000b641  mov     byte ptr [rbp+arg_10], r14b
0x18000b645  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000b649  mov     rsi, rdx
0x18000b64c  inc     rcx
0x18000b64f  cmp     [rdi+rcx*2], r14w
0x18000b654  jnz     short loc_18000B64C
0x18000b656  mov     rax, cs:g_pfnResultFromCaughtExceptionInternal
0x18000b65d  mov     ebx, 1
0x18000b662  test    rax, rax
0x18000b665  jz      short loc_18000B69C
0x18000b667  lea     rdx, [rdi+rcx*2]
0x18000b66b  mov     r8d, 800h
0x18000b671  sub     r8, rcx
0x18000b674  lea     r9, [rbp+arg_10]
0x18000b678  lea     rcx, [rbp+var_10]
0x18000b67c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b681  movsd   xmm0, qword ptr [rax]
0x18000b685  mov     eax, [rax+8]
0x18000b688  mov     [rbp+var_18], eax
0x18000b68b  movd    eax, xmm0
0x18000b68f  movsd   [rbp+var_20], xmm0
0x18000b694  test    eax, eax
0x18000b696  jns     short loc_18000B69C
0x18000b698  mov     dl, bl
0x18000b69a  jmp     short loc_18000B6B3
0x18000b69c  mov     ecx, 8007023Eh; this
0x18000b6a1  mov     dl, r14b; int
0x18000b6a4  mov     dword ptr [rbp+var_20], ecx
0x18000b6a7  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000b6ac  mov     dword ptr [rbp+var_20+4], eax
0x18000b6af  mov     [rbp+var_18], r14d
0x18000b6b3  cmp     byte ptr [rbp+arg_10], r14b
0x18000b6b7  lea     r8, aServercommonBa_1; "servercommon\\base\\securehostingservic"...
0x18000b6be  mov     eax, 3
0x18000b6c3  mov     rcx, rsi
0x18000b6c6  cmovnz  ebx, eax
0x18000b6c9  test    dl, dl
0x18000b6cb  mov     edx, 276h
0x18000b6d0  lea     rax, [rbp+var_20]
0x18000b6d4  jz      short loc_18000B6F3
0x18000b6d6  mov     [rsp+70h+var_30], ebx
0x18000b6da  mov     [rsp+70h+var_38], rdi
0x18000b6df  mov     [rsp+70h+var_40], rax
0x18000b6e4  mov     rax, [rbp+arg_30]
0x18000b6e8  mov     [rsp+70h+var_48], rax
0x18000b6ed  call    ??$ReportFailure_Base@$0A@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<0,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x18000b6f3  mov     [rsp+70h+var_38], rdi
0x18000b6f8  mov     [rsp+70h+var_40], rax
0x18000b6fd  mov     rax, [rbp+arg_30]
0x18000b701  mov     [rsp+70h+var_48], rax
0x18000b706  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
