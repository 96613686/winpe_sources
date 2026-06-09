# wil::details::ReportFailure_CaughtException<1>(void *,uint,char const *,char const *,char const *,void *,wil::SupportedExceptions)

- ea: `0x140002324`
- end: `0x14000246f`
- name: `??$ReportFailure_CaughtException@$00@details@wil@@YAJPEAXIPEBD110W4SupportedExceptions@1@@Z`
- size: `331`
- prototype: `__int64 __fastcall(int, __int64, __int64, __int64, int, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task`

## callers

- `0x140005984`

## callees

- `0x140001470`
- `0x140001f0e`
- `0x140002264`
- `0x1400022c0`
- `0x140002324`
- `0x140004e3c`
- `0x140007880`
- `0x140008010`

## string_xrefs

- `0x1400023e4`: `onecoreuap\net\dusm\task\dusmtask.cpp`
- `0x14000243d`: `onecoreuap\net\dusm\task\dusmtask.cpp`

## pseudocode

```c
__int64 __fastcall wil::details::ReportFailure_CaughtException<1>(
        int a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6)
{
  int v7; // edx
  __int64 v8; // rcx
  unsigned __int64 *v9; // rax
  int v10; // r9d
  __m128i v11; // xmm0
  int v12; // esi
  int v14; // r9d
  int v15; // [rsp+20h] [rbp-E0h]
  __int64 v16; // [rsp+50h] [rbp-B0h] BYREF
  int v17; // [rsp+58h] [rbp-A8h]
  _BYTE v18[16]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v19[16]; // [rsp+70h] [rbp-90h] BYREF
  _WORD v20[2048]; // [rsp+80h] [rbp-80h] BYREF

  memset_0(v20, 0, sizeof(v20));
  v19[0] = 0;
  v8 = -1;
  do
    ++v8;
  while ( v20[v8] );
  if ( !g_pfnResultFromCaughtExceptionInternal
    || (v9 = (unsigned __int64 *)g_pfnResultFromCaughtExceptionInternal(v18, &v20[v8], 2048 - v8, v19),
        v11 = (__m128i)*v9,
        LODWORD(v9) = *((_DWORD *)v9 + 2),
        v12 = _mm_cvtsi128_si32(v11),
        v16 = v11.m128i_i64[0],
        v17 = (int)v9,
        v12 >= 0) )
  {
    LODWORD(v16) = -2147024322;
    HIDWORD(v16) = wil::details::HrToNtStatus((wil::details *)0x8007023ELL, v7);
    v17 = 0;
    wil::details::ReportFailure_Base<3,0>(
      a1,
      215,
      (int)"onecoreuap\\net\\dusm\\task\\dusmtask.cpp",
      v14,
      v15,
      a6,
      (__int64)&v16,
      (__int64)v20);
  }
  wil::details::ReportFailure_Base<1,0>(
    a1,
    215,
    (int)"onecoreuap\\net\\dusm\\task\\dusmtask.cpp",
    v10,
    v15,
    a6,
    (int)&v16,
    (__int64)v20);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x140002324  mov     [rsp-8+arg_8], rbx
0x140002329  mov     [rsp-8+arg_10], rsi
0x14000232e  push    rbp
0x14000232f  push    rdi
0x140002330  push    r14
0x140002332  lea     rbp, [rsp-0F90h]
0x14000233a  mov     eax, 1090h
0x14000233f  call    _alloca_probe
0x140002344  sub     rsp, rax
0x140002347  mov     rax, cs:__security_cookie
0x14000234e  xor     rax, rsp
0x140002351  mov     [rbp+0FA0h+var_20], rax
0x140002358  mov     rdi, [rbp+0FA0h+arg_28]
0x14000235f  mov     rbx, rcx
0x140002362  lea     rcx, [rbp+0FA0h+var_1020]; void *
0x140002366  xor     edx, edx; Val
0x140002368  mov     r8d, 1000h; Size
0x14000236e  call    memset_0
0x140002373  xor     r14d, r14d
0x140002376  lea     rax, [rbp+0FA0h+var_1020]
0x14000237a  mov     [rsp+10A0h+var_1030], r14b
0x14000237f  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140002383  inc     rcx
0x140002386  cmp     [rax+rcx*2], r14w
0x14000238b  jnz     short loc_140002383
0x14000238d  mov     rax, cs:g_pfnResultFromCaughtExceptionInternal
0x140002394  test    rax, rax
0x140002397  jz      loc_14000242B
0x14000239d  mov     r8d, 800h
0x1400023a3  lea     rdx, [rbp+0FA0h+var_1020]
0x1400023a7  sub     r8, rcx
0x1400023aa  lea     rdx, [rdx+rcx*2]
0x1400023ae  lea     rcx, [rsp+10A0h+var_1040]
0x1400023b3  lea     r9, [rsp+10A0h+var_1030]
0x1400023b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400023bd  movsd   xmm0, qword ptr [rax]
0x1400023c1  mov     eax, [rax+8]
0x1400023c4  movd    esi, xmm0
0x1400023c8  movsd   [rsp+10A0h+var_1050], xmm0
0x1400023ce  mov     [rsp+10A0h+var_1048], eax
0x1400023d2  test    esi, esi
0x1400023d4  jns     short loc_14000242B
0x1400023d6  lea     rax, [rbp+0FA0h+var_1020]
0x1400023da  mov     edx, 0D7h
0x1400023df  mov     [rsp+10A0h+var_1068], rax
0x1400023e4  lea     r8, aOnecoreuapNetD; "onecoreuap\\net\\dusm\\task\\dusmtask.c"...
0x1400023eb  lea     rax, [rsp+10A0h+var_1050]
0x1400023f0  mov     rcx, rbx
0x1400023f3  mov     [rsp+10A0h+var_1070], rax
0x1400023f8  mov     [rsp+10A0h+var_1078], rdi
0x1400023fd  call    ??$ReportFailure_Base@$00$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<1,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x140002402  mov     eax, esi
0x140002404  mov     rcx, [rbp+0FA0h+var_20]
0x14000240b  xor     rcx, rsp; StackCookie
0x14000240e  call    __security_check_cookie
0x140002413  lea     r11, [rsp+10A0h+var_10]
0x14000241b  mov     rbx, [r11+28h]
0x14000241f  mov     rsi, [r11+30h]
0x140002423  mov     rsp, r11
0x140002426  pop     r14
0x140002428  pop     rdi
0x140002429  pop     rbp
0x14000242a  retn
0x14000242b  mov     ecx, 8007023Eh; this
0x140002430  mov     dword ptr [rsp+10A0h+var_1050], ecx
0x140002434  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140002439  mov     dword ptr [rsp+10A0h+var_1050+4], eax
0x14000243d  lea     r8, aOnecoreuapNetD; "onecoreuap\\net\\dusm\\task\\dusmtask.c"...
0x140002444  lea     rax, [rbp+0FA0h+var_1020]
0x140002448  mov     [rsp+10A0h+var_1048], r14d
0x14000244d  mov     [rsp+10A0h+var_1068], rax
0x140002452  mov     edx, 0D7h
0x140002457  lea     rax, [rsp+10A0h+var_1050]
0x14000245c  mov     rcx, rbx
0x14000245f  mov     [rsp+10A0h+var_1070], rax
0x140002464  mov     [rsp+10A0h+var_1078], rdi
0x140002469  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
