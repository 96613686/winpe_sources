# wil::details::ReportFailure_CaughtException<2>(void *,uint,char const *,char const *,char const *,void *,wil::SupportedExceptions)

- ea: `0x1400038d0`
- end: `0x140003a1e`
- name: `??$ReportFailure_CaughtException@$01@details@wil@@YAJPEAXIPEBD110W4SupportedExceptions@1@@Z`
- size: `334`
- prototype: `__int64 __fastcall(int, __int64, __int64, __int64, int, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x14000a260`

## callees

- `0x1400022a0`
- `0x140002d4c`
- `0x1400036c4`
- `0x140003718`
- `0x1400038d0`
- `0x140009b94`
- `0x1400113b0`
- `0x140012010`

## string_xrefs

- `0x140003991`: `onecoreuap\windows\directx\dxg\dxgi\adaptercache\exe\main.cpp`
- `0x1400039ed`: `onecoreuap\windows\directx\dxg\dxgi\adaptercache\exe\main.cpp`

## pseudocode

```c
__int64 __fastcall wil::details::ReportFailure_CaughtException<2>(
        int a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6)
{
  int v7; // edx
  __int64 v8; // rcx
  __int64 v9; // rax
  int v11; // r9d
  int v12; // [rsp+20h] [rbp-E0h]
  _BYTE v13[8]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int64 v14; // [rsp+58h] [rbp-A8h] BYREF
  int v15; // [rsp+60h] [rbp-A0h]
  _BYTE v16[24]; // [rsp+68h] [rbp-98h] BYREF
  _WORD v17[2048]; // [rsp+80h] [rbp-80h] BYREF

  memset_0(v17, 0, sizeof(v17));
  v13[0] = 0;
  v8 = -1;
  do
    ++v8;
  while ( v17[v8] );
  v14 = 0;
  v15 = 1;
  if ( !g_pfnResultFromCaughtExceptionInternal
    || (v9 = g_pfnResultFromCaughtExceptionInternal(v16, &v17[v8], 2048 - v8, v13),
        v14 = *(_QWORD *)v9,
        v15 = *(_DWORD *)(v9 + 8),
        _mm_cvtsi128_si32((__m128i)v14) >= 0) )
  {
    LODWORD(v14) = -2147024322;
    HIDWORD(v14) = wil::details::HrToNtStatus((wil::details *)0x8007023ELL, v7);
    v15 = 0;
    wil::details::ReportFailure_Base<3,0>(
      a1,
      769,
      (int)"onecoreuap\\windows\\directx\\dxg\\dxgi\\adaptercache\\exe\\main.cpp",
      v11,
      v12,
      a6,
      (__int64)&v14,
      (__int64)v17);
  }
  wil::details::ReportFailure_Base<2,0>(
    a1,
    769,
    (unsigned int)"onecoreuap\\windows\\directx\\dxg\\dxgi\\adaptercache\\exe\\main.cpp",
    0,
    0,
    a6,
    (__int64)&v14,
    (__int64)v17);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x1400038d0  push    rbp
0x1400038d2  push    rbx
0x1400038d3  push    rsi
0x1400038d4  push    rdi
0x1400038d5  lea     rbp, [rsp-0F98h]
0x1400038dd  mov     eax, 1098h
0x1400038e2  call    _alloca_probe
0x1400038e7  sub     rsp, rax
0x1400038ea  mov     rax, cs:__security_cookie
0x1400038f1  xor     rax, rsp
0x1400038f4  mov     [rbp+0FB0h+var_30], rax
0x1400038fb  mov     rdi, [rbp+0FB0h+arg_28]
0x140003902  mov     rbx, rcx
0x140003905  lea     rcx, [rbp+0FB0h+var_1030]; void *
0x140003909  xor     edx, edx; Val
0x14000390b  mov     r8d, 1000h; Size
0x140003911  call    memset_0
0x140003916  xor     esi, esi
0x140003918  lea     rax, [rbp+0FB0h+var_1030]
0x14000391c  mov     [rsp+10B0h+var_1060], sil
0x140003921  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140003925  inc     rcx
0x140003928  cmp     [rax+rcx*2], si
0x14000392c  jnz     short loc_140003925
0x14000392e  mov     rax, cs:g_pfnResultFromCaughtExceptionInternal
0x140003935  mov     [rsp+10B0h+var_1058], rsi
0x14000393a  mov     [rsp+10B0h+var_1050], 1
0x140003942  test    rax, rax
0x140003945  jz      loc_1400039DB
0x14000394b  mov     r8d, 800h
0x140003951  lea     rdx, [rbp+0FB0h+var_1030]
0x140003955  sub     r8, rcx
0x140003958  lea     rdx, [rdx+rcx*2]
0x14000395c  lea     rcx, [rsp+10B0h+var_1048]
0x140003961  lea     r9, [rsp+10B0h+var_1060]
0x140003966  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000396b  movsd   xmm0, qword ptr [rax]
0x14000396f  movsd   [rsp+10B0h+var_1058], xmm0
0x140003975  mov     eax, [rax+8]
0x140003978  mov     [rsp+10B0h+var_1050], eax
0x14000397c  movd    eax, xmm0
0x140003980  test    eax, eax
0x140003982  jns     short loc_1400039DB
0x140003984  mov     [rsp+10B0h+var_1068], esi
0x140003988  lea     rax, [rbp+0FB0h+var_1030]
0x14000398c  mov     [rsp+10B0h+var_1078], rax
0x140003991  lea     r8, aOnecoreuapWind; "onecoreuap\\windows\\directx\\dxg\\dxgi"...
0x140003998  lea     rax, [rsp+10B0h+var_1058]
0x14000399d  xor     r9d, r9d
0x1400039a0  mov     [rsp+10B0h+var_1080], rax
0x1400039a5  mov     edx, 301h
0x1400039aa  mov     [rsp+10B0h+var_1088], rdi
0x1400039af  mov     rcx, rbx
0x1400039b2  mov     [rsp+10B0h+var_1090], rsi
0x1400039b7  call    ??$ReportFailure_Base@$01$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<2,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x1400039bc  mov     eax, dword ptr [rsp+10B0h+var_1058]
0x1400039c0  mov     rcx, [rbp+0FB0h+var_30]
0x1400039c7  xor     rcx, rsp; StackCookie
0x1400039ca  call    __security_check_cookie
0x1400039cf  add     rsp, 1098h
0x1400039d6  pop     rdi
0x1400039d7  pop     rsi
0x1400039d8  pop     rbx
0x1400039d9  pop     rbp
0x1400039da  retn
0x1400039db  mov     ecx, 8007023Eh; this
0x1400039e0  mov     dword ptr [rsp+10B0h+var_1058], ecx
0x1400039e4  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1400039e9  mov     dword ptr [rsp+10B0h+var_1058+4], eax
0x1400039ed  lea     r8, aOnecoreuapWind; "onecoreuap\\windows\\directx\\dxg\\dxgi"...
0x1400039f4  lea     rax, [rbp+0FB0h+var_1030]
0x1400039f8  mov     [rsp+10B0h+var_1050], esi
0x1400039fc  mov     [rsp+10B0h+var_1078], rax
0x140003a01  mov     edx, 301h
0x140003a06  lea     rax, [rsp+10B0h+var_1058]
0x140003a0b  mov     rcx, rbx
0x140003a0e  mov     [rsp+10B0h+var_1080], rax
0x140003a13  mov     [rsp+10B0h+var_1088], rdi
0x140003a18  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
