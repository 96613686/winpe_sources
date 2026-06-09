# wil::details::ReportFailure_CaughtException<1>(void *,uint,char const *,char const *,char const *,void *,wil::SupportedExceptions)

- ea: `0x14000377c`
- end: `0x1400038c7`
- name: `??$ReportFailure_CaughtException@$00@details@wil@@YAJPEAXIPEBD110W4SupportedExceptions@1@@Z`
- size: `331`
- prototype: `__int64 __fastcall(int, __int64, __int64, __int64, int, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x14000c894`

## callees

- `0x1400022a0`
- `0x140002d4c`
- `0x1400036b8`
- `0x140003718`
- `0x14000377c`
- `0x140009b94`
- `0x1400113b0`
- `0x140012010`

## string_xrefs

- `0x14000383c`: `onecoreuap\windows\directx\dxg\dxgi\adaptercache\exe\main.cpp`
- `0x140003895`: `onecoreuap\windows\directx\dxg\dxgi\adaptercache\exe\main.cpp`

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
  _BYTE v16[8]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v17; // [rsp+58h] [rbp-A8h] BYREF
  int v18; // [rsp+60h] [rbp-A0h]
  _BYTE v19[24]; // [rsp+68h] [rbp-98h] BYREF
  _WORD v20[2048]; // [rsp+80h] [rbp-80h] BYREF

  memset_0(v20, 0, sizeof(v20));
  v16[0] = 0;
  v8 = -1;
  do
    ++v8;
  while ( v20[v8] );
  if ( !g_pfnResultFromCaughtExceptionInternal
    || (v9 = (unsigned __int64 *)g_pfnResultFromCaughtExceptionInternal(v19, &v20[v8], 2048 - v8, v16),
        v11 = (__m128i)*v9,
        LODWORD(v9) = *((_DWORD *)v9 + 2),
        v12 = _mm_cvtsi128_si32(v11),
        v17 = v11.m128i_i64[0],
        v18 = (int)v9,
        v12 >= 0) )
  {
    LODWORD(v17) = -2147024322;
    HIDWORD(v17) = wil::details::HrToNtStatus((wil::details *)0x8007023ELL, v7);
    v18 = 0;
    wil::details::ReportFailure_Base<3,0>(
      a1,
      1073,
      (int)"onecoreuap\\windows\\directx\\dxg\\dxgi\\adaptercache\\exe\\main.cpp",
      v14,
      v15,
      a6,
      (__int64)&v17,
      (__int64)v20);
  }
  wil::details::ReportFailure_Base<1,0>(
    a1,
    1073,
    (int)"onecoreuap\\windows\\directx\\dxg\\dxgi\\adaptercache\\exe\\main.cpp",
    v10,
    v15,
    a6,
    (int)&v17,
    (__int64)v20);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x14000377c  mov     [rsp-8+arg_8], rbx
0x140003781  mov     [rsp-8+arg_10], rsi
0x140003786  push    rbp
0x140003787  push    rdi
0x140003788  push    r14
0x14000378a  lea     rbp, [rsp-0F90h]
0x140003792  mov     eax, 1090h
0x140003797  call    _alloca_probe
0x14000379c  sub     rsp, rax
0x14000379f  mov     rax, cs:__security_cookie
0x1400037a6  xor     rax, rsp
0x1400037a9  mov     [rbp+0FA0h+var_20], rax
0x1400037b0  mov     rdi, [rbp+0FA0h+arg_28]
0x1400037b7  mov     rbx, rcx
0x1400037ba  lea     rcx, [rbp+0FA0h+var_1020]; void *
0x1400037be  xor     edx, edx; Val
0x1400037c0  mov     r8d, 1000h; Size
0x1400037c6  call    memset_0
0x1400037cb  xor     r14d, r14d
0x1400037ce  lea     rax, [rbp+0FA0h+var_1020]
0x1400037d2  mov     [rsp+10A0h+var_1050], r14b
0x1400037d7  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1400037db  inc     rcx
0x1400037de  cmp     [rax+rcx*2], r14w
0x1400037e3  jnz     short loc_1400037DB
0x1400037e5  mov     rax, cs:g_pfnResultFromCaughtExceptionInternal
0x1400037ec  test    rax, rax
0x1400037ef  jz      loc_140003883
0x1400037f5  mov     r8d, 800h
0x1400037fb  lea     rdx, [rbp+0FA0h+var_1020]
0x1400037ff  sub     r8, rcx
0x140003802  lea     rdx, [rdx+rcx*2]
0x140003806  lea     rcx, [rsp+10A0h+var_1038]
0x14000380b  lea     r9, [rsp+10A0h+var_1050]
0x140003810  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003815  movsd   xmm0, qword ptr [rax]
0x140003819  mov     eax, [rax+8]
0x14000381c  movd    esi, xmm0
0x140003820  movsd   [rsp+10A0h+var_1048], xmm0
0x140003826  mov     [rsp+10A0h+var_1040], eax
0x14000382a  test    esi, esi
0x14000382c  jns     short loc_140003883
0x14000382e  lea     rax, [rbp+0FA0h+var_1020]
0x140003832  mov     edx, 431h
0x140003837  mov     [rsp+10A0h+var_1068], rax
0x14000383c  lea     r8, aOnecoreuapWind; "onecoreuap\\windows\\directx\\dxg\\dxgi"...
0x140003843  lea     rax, [rsp+10A0h+var_1048]
0x140003848  mov     rcx, rbx
0x14000384b  mov     [rsp+10A0h+var_1070], rax
0x140003850  mov     [rsp+10A0h+var_1078], rdi
0x140003855  call    ??$ReportFailure_Base@$00$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<1,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x14000385a  mov     eax, esi
0x14000385c  mov     rcx, [rbp+0FA0h+var_20]
0x140003863  xor     rcx, rsp; StackCookie
0x140003866  call    __security_check_cookie
0x14000386b  lea     r11, [rsp+10A0h+var_10]
0x140003873  mov     rbx, [r11+28h]
0x140003877  mov     rsi, [r11+30h]
0x14000387b  mov     rsp, r11
0x14000387e  pop     r14
0x140003880  pop     rdi
0x140003881  pop     rbp
0x140003882  retn
0x140003883  mov     ecx, 8007023Eh; this
0x140003888  mov     dword ptr [rsp+10A0h+var_1048], ecx
0x14000388c  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140003891  mov     dword ptr [rsp+10A0h+var_1048+4], eax
0x140003895  lea     r8, aOnecoreuapWind; "onecoreuap\\windows\\directx\\dxg\\dxgi"...
0x14000389c  lea     rax, [rbp+0FA0h+var_1020]
0x1400038a0  mov     [rsp+10A0h+var_1040], r14d
0x1400038a5  mov     [rsp+10A0h+var_1068], rax
0x1400038aa  mov     edx, 431h
0x1400038af  lea     rax, [rsp+10A0h+var_1048]
0x1400038b4  mov     rcx, rbx
0x1400038b7  mov     [rsp+10A0h+var_1070], rax
0x1400038bc  mov     [rsp+10A0h+var_1078], rdi
0x1400038c1  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
