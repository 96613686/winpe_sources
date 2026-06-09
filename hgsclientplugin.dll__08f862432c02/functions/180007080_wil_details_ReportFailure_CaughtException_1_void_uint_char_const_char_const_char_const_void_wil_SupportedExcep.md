# wil::details::ReportFailure_CaughtException<1>(void *,uint,char const *,char const *,char const *,void *,wil::SupportedExceptions)

- ea: `0x180007080`
- end: `0x1800071c7`
- name: `??$ReportFailure_CaughtException@$00@details@wil@@YAJPEAXIPEBD110W4SupportedExceptions@1@@Z`
- size: `327`
- prototype: `__int64 __fastcall(int, int, __int64, __int64, int, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180008288`

## callees

- `0x180001520`
- `0x180001f9e`
- `0x180002084`
- `0x1800020e4`
- `0x180003f24`
- `0x180007080`
- `0x18000a850`
- `0x18000c010`

## string_xrefs

- `0x18000713f`: `servercommon\base\securehostingservice\common\service\plugin\hgsclientplugin.cpp`
- `0x180007198`: `servercommon\base\securehostingservice\common\service\plugin\hgsclientplugin.cpp`

## pseudocode

```c
__int64 __fastcall wil::details::ReportFailure_CaughtException<1>(
        int a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6)
{
  int v8; // edx
  __int64 v9; // rcx
  unsigned __int64 *v10; // rax
  int v11; // r9d
  __m128i v12; // xmm0
  int v13; // r14d
  int v15; // r9d
  int v16; // [rsp+20h] [rbp-E0h]
  _BYTE v17[8]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v18; // [rsp+58h] [rbp-A8h] BYREF
  int v19; // [rsp+60h] [rbp-A0h]
  _BYTE v20[24]; // [rsp+68h] [rbp-98h] BYREF
  _WORD v21[2048]; // [rsp+80h] [rbp-80h] BYREF

  memset_0(v21, 0, sizeof(v21));
  v17[0] = 0;
  v9 = -1;
  do
    ++v9;
  while ( v21[v9] );
  if ( !g_pfnResultFromCaughtExceptionInternal
    || (v10 = (unsigned __int64 *)g_pfnResultFromCaughtExceptionInternal(v20, &v21[v9], 2048 - v9, v17),
        v12 = (__m128i)*v10,
        LODWORD(v10) = *((_DWORD *)v10 + 2),
        v13 = _mm_cvtsi128_si32(v12),
        v18 = v12.m128i_i64[0],
        v19 = (int)v10,
        v13 >= 0) )
  {
    LODWORD(v18) = -2147024322;
    HIDWORD(v18) = wil::details::HrToNtStatus((wil::details *)0x8007023ELL, v8);
    v19 = 0;
    wil::details::ReportFailure_Base<3,0>(
      a1,
      a2,
      (int)"servercommon\\base\\securehostingservice\\common\\service\\plugin\\hgsclientplugin.cpp",
      v15,
      v16,
      a6,
      (__int64)&v18,
      (__int64)v21);
  }
  wil::details::ReportFailure_Base<1,0>(
    a1,
    a2,
    (int)"servercommon\\base\\securehostingservice\\common\\service\\plugin\\hgsclientplugin.cpp",
    v11,
    v16,
    a6,
    (int)&v18,
    (__int64)v21);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180007080  mov     [rsp-8+arg_10], rbx
0x180007085  push    rbp
0x180007086  push    rsi
0x180007087  push    rdi
0x180007088  push    r14
0x18000708a  push    r15
0x18000708c  lea     rbp, [rsp-0F90h]
0x180007094  mov     eax, 1090h
0x180007099  call    _alloca_probe
0x18000709e  sub     rsp, rax
0x1800070a1  mov     rax, cs:__security_cookie
0x1800070a8  xor     rax, rsp
0x1800070ab  mov     [rbp+0FB0h+var_30], rax
0x1800070b2  mov     rsi, [rbp+0FB0h+arg_28]
0x1800070b9  mov     edi, edx
0x1800070bb  mov     rbx, rcx
0x1800070be  xor     edx, edx; Val
0x1800070c0  lea     rcx, [rbp+0FB0h+var_1030]; void *
0x1800070c4  mov     r8d, 1000h; Size
0x1800070ca  call    memset_0
0x1800070cf  xor     r15d, r15d
0x1800070d2  lea     rax, [rbp+0FB0h+var_1030]
0x1800070d6  mov     [rsp+10B0h+var_1060], r15b
0x1800070db  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800070df  inc     rcx
0x1800070e2  cmp     [rax+rcx*2], r15w
0x1800070e7  jnz     short loc_1800070DF
0x1800070e9  mov     rax, cs:g_pfnResultFromCaughtExceptionInternal
0x1800070f0  test    rax, rax
0x1800070f3  jz      loc_180007186
0x1800070f9  mov     r8d, 800h
0x1800070ff  lea     rdx, [rbp+0FB0h+var_1030]
0x180007103  sub     r8, rcx
0x180007106  lea     rdx, [rdx+rcx*2]
0x18000710a  lea     rcx, [rsp+10B0h+var_1048]
0x18000710f  lea     r9, [rsp+10B0h+var_1060]
0x180007114  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007119  movsd   xmm0, qword ptr [rax]
0x18000711d  mov     eax, [rax+8]
0x180007120  movd    r14d, xmm0
0x180007125  movsd   [rsp+10B0h+var_1058], xmm0
0x18000712b  mov     [rsp+10B0h+var_1050], eax
0x18000712f  test    r14d, r14d
0x180007132  jns     short loc_180007186
0x180007134  lea     rax, [rbp+0FB0h+var_1030]
0x180007138  mov     edx, edi
0x18000713a  mov     [rsp+10B0h+var_1078], rax
0x18000713f  lea     r8, aServercommonBa_1; "servercommon\\base\\securehostingservic"...
0x180007146  lea     rax, [rsp+10B0h+var_1058]
0x18000714b  mov     rcx, rbx
0x18000714e  mov     [rsp+10B0h+var_1080], rax
0x180007153  mov     [rsp+10B0h+var_1088], rsi
0x180007158  call    ??$ReportFailure_Base@$00$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<1,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x18000715d  mov     eax, r14d
0x180007160  mov     rcx, [rbp+0FB0h+var_30]
0x180007167  xor     rcx, rsp; StackCookie
0x18000716a  call    __security_check_cookie
0x18000716f  mov     rbx, [rsp+10B0h+arg_10]
0x180007177  add     rsp, 1090h
0x18000717e  pop     r15
0x180007180  pop     r14
0x180007182  pop     rdi
0x180007183  pop     rsi
0x180007184  pop     rbp
0x180007185  retn
0x180007186  mov     ecx, 8007023Eh; this
0x18000718b  mov     dword ptr [rsp+10B0h+var_1058], ecx
0x18000718f  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180007194  mov     dword ptr [rsp+10B0h+var_1058+4], eax
0x180007198  lea     r8, aServercommonBa_1; "servercommon\\base\\securehostingservic"...
0x18000719f  lea     rax, [rbp+0FB0h+var_1030]
0x1800071a3  mov     [rsp+10B0h+var_1050], r15d
0x1800071a8  mov     [rsp+10B0h+var_1078], rax
0x1800071ad  mov     edx, edi
0x1800071af  lea     rax, [rsp+10B0h+var_1058]
0x1800071b4  mov     rcx, rbx
0x1800071b7  mov     [rsp+10B0h+var_1080], rax
0x1800071bc  mov     [rsp+10B0h+var_1088], rsi
0x1800071c1  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
