# wil::details::ReportFailure_CaughtException<2>(void *,uint,char const *,char const *,char const *,void *,wil::SupportedExceptions)

- ea: `0x180009aa4`
- end: `0x180009bf1`
- name: `??$ReportFailure_CaughtException@$01@details@wil@@YAJPEAXIPEBD110W4SupportedExceptions@1@@Z`
- size: `333`
- prototype: `__int64 __fastcall(int, __int64, __int64, __int64, int, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000a380`

## callees

- `0x180001520`
- `0x180001f9e`
- `0x180002090`
- `0x1800020e4`
- `0x180003f24`
- `0x180009aa4`
- `0x18000a850`
- `0x18000c010`

## string_xrefs

- `0x180009b65`: `servercommon\base\securehostingservice\common\service\plugin\cimutilities.cpp`
- `0x180009bc0`: `servercommon\base\securehostingservice\common\service\plugin\cimutilities.cpp`

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
      63,
      (int)"servercommon\\base\\securehostingservice\\common\\service\\plugin\\cimutilities.cpp",
      v11,
      v12,
      a6,
      (__int64)&v14,
      (__int64)v17);
  }
  wil::details::ReportFailure_Base<2,0>(
    a1,
    63,
    (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\plugin\\cimutilities.cpp",
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
0x180009aa4  push    rbp
0x180009aa6  push    rbx
0x180009aa7  push    rsi
0x180009aa8  push    rdi
0x180009aa9  lea     rbp, [rsp-0F98h]
0x180009ab1  mov     eax, 1098h
0x180009ab6  call    _alloca_probe
0x180009abb  sub     rsp, rax
0x180009abe  mov     rax, cs:__security_cookie
0x180009ac5  xor     rax, rsp
0x180009ac8  mov     [rbp+0FB0h+var_30], rax
0x180009acf  mov     rdi, [rbp+0FB0h+arg_28]
0x180009ad6  mov     rbx, rcx
0x180009ad9  lea     rcx, [rbp+0FB0h+var_1030]; void *
0x180009add  xor     edx, edx; Val
0x180009adf  mov     r8d, 1000h; Size
0x180009ae5  call    memset_0
0x180009aea  xor     esi, esi
0x180009aec  lea     rax, [rbp+0FB0h+var_1030]
0x180009af0  mov     [rsp+10B0h+var_1060], sil
0x180009af5  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180009af9  inc     rcx
0x180009afc  cmp     [rax+rcx*2], si
0x180009b00  jnz     short loc_180009AF9
0x180009b02  mov     rax, cs:g_pfnResultFromCaughtExceptionInternal
0x180009b09  mov     [rsp+10B0h+var_1058], rsi
0x180009b0e  mov     [rsp+10B0h+var_1050], 1
0x180009b16  test    rax, rax
0x180009b19  jz      loc_180009BAE
0x180009b1f  mov     r8d, 800h
0x180009b25  lea     rdx, [rbp+0FB0h+var_1030]
0x180009b29  sub     r8, rcx
0x180009b2c  lea     rdx, [rdx+rcx*2]
0x180009b30  lea     rcx, [rsp+10B0h+var_1048]
0x180009b35  lea     r9, [rsp+10B0h+var_1060]
0x180009b3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009b3f  movsd   xmm0, qword ptr [rax]
0x180009b43  movsd   [rsp+10B0h+var_1058], xmm0
0x180009b49  mov     eax, [rax+8]
0x180009b4c  mov     [rsp+10B0h+var_1050], eax
0x180009b50  movd    eax, xmm0
0x180009b54  test    eax, eax
0x180009b56  jns     short loc_180009BAE
0x180009b58  mov     [rsp+10B0h+var_1068], esi
0x180009b5c  lea     rax, [rbp+0FB0h+var_1030]
0x180009b60  mov     [rsp+10B0h+var_1078], rax
0x180009b65  lea     r8, aServercommonBa; "servercommon\\base\\securehostingservic"...
0x180009b6c  xor     r9d, r9d
0x180009b6f  lea     rax, [rsp+10B0h+var_1058]
0x180009b74  mov     [rsp+10B0h+var_1080], rax
0x180009b79  mov     rcx, rbx
0x180009b7c  mov     [rsp+10B0h+var_1088], rdi
0x180009b81  mov     [rsp+10B0h+var_1090], rsi
0x180009b86  lea     edx, [r9+3Fh]
0x180009b8a  call    ??$ReportFailure_Base@$01$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<2,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x180009b8f  mov     eax, dword ptr [rsp+10B0h+var_1058]
0x180009b93  mov     rcx, [rbp+0FB0h+var_30]
0x180009b9a  xor     rcx, rsp; StackCookie
0x180009b9d  call    __security_check_cookie
0x180009ba2  add     rsp, 1098h
0x180009ba9  pop     rdi
0x180009baa  pop     rsi
0x180009bab  pop     rbx
0x180009bac  pop     rbp
0x180009bad  retn
0x180009bae  mov     ecx, 8007023Eh; this
0x180009bb3  mov     dword ptr [rsp+10B0h+var_1058], ecx
0x180009bb7  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180009bbc  mov     dword ptr [rsp+10B0h+var_1058+4], eax
0x180009bc0  lea     r8, aServercommonBa; "servercommon\\base\\securehostingservic"...
0x180009bc7  lea     rax, [rbp+0FB0h+var_1030]
0x180009bcb  mov     [rsp+10B0h+var_1050], esi
0x180009bcf  mov     [rsp+10B0h+var_1078], rax
0x180009bd4  mov     edx, 3Fh ; '?'
0x180009bd9  lea     rax, [rsp+10B0h+var_1058]
0x180009bde  mov     rcx, rbx
0x180009be1  mov     [rsp+10B0h+var_1080], rax
0x180009be6  mov     [rsp+10B0h+var_1088], rdi
0x180009beb  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
