# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x1800077dc`
- end: `0x180007a55`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `633`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18000754c`

## callees

- `0x180007018`
- `0x1800077dc`
- `0x180009064`
- `0x180009804`
- `0x180009e50`
- `0x18000af90`
- `0x180082e30`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007895`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007895`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180007a22`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180007a22`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180007998`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180007998`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<3>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7,
        _WORD *a8)
{
  int v11; // edx
  int v12; // r12d
  int v13; // ecx
  const struct wil::FailureInfo *v14; // rdx
  __int64 v15; // rcx
  const struct wil::FailureInfo *v16; // r9
  bool v17; // zf
  int v18; // [rsp+20h] [rbp-E0h] BYREF
  int v19; // [rsp+24h] [rbp-DCh]
  int v20; // [rsp+28h] [rbp-D8h]
  int v21; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v22; // [rsp+30h] [rbp-D0h]
  _WORD *v23; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v25; // [rsp+48h] [rbp-B8h]
  __int64 v26; // [rsp+50h] [rbp-B0h]
  __int64 v27; // [rsp+58h] [rbp-A8h]
  int v28; // [rsp+60h] [rbp-A0h]
  int v29; // [rsp+64h] [rbp-9Ch]
  __int64 v30; // [rsp+68h] [rbp-98h]
  __int128 v31; // [rsp+70h] [rbp-90h]
  __int64 v32; // [rsp+80h] [rbp-80h]
  __int128 v33; // [rsp+88h] [rbp-78h]
  __int64 v34; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v36; // [rsp+A8h] [rbp-58h]
  __int64 v37; // [rsp+B0h] [rbp-50h]
  char v38[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2072]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v18, 0, 0x98u);
  OutputString[0] = 0;
  v38[0] = 0;
  v20 = *a7;
  v21 = a7[1];
  v12 = wil::details::RecordFailFast((wil::details *)(unsigned int)v20, v11);
  v18 = 3;
  v13 = 0;
  if ( a7[2] == 1 )
    v13 = 8;
  v19 = v13;
  v22 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  if ( !a8 || (v17 = *a8 == 0, v23 = a8, v17) )
    v23 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v27 = a3;
  v28 = a2;
  v29 = v12;
  v25 = 0;
  v26 = 0;
  v36 = a6;
  v37 = a1;
  v30 = 0;
  v33 = 0;
  v34 = 0;
  v31 = 0;
  v32 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v15);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v18);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v18, v38, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v18);
  if ( wil::details::g_pfnOriginateCallback && (v19 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v18);
  if ( v20 >= 0 )
  {
    v20 = -2147418113;
    v21 = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, (int)v14);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v17 = !IsDebuggerPresent())
      : (v17 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v15) == 0),
        v17)
    || (v19 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v18, 0, 0, v16);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v18, OutputString, 2048, v16);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (__int64)&v18, v16);
    OutputDebugStringW(OutputString);
  }
  if ( (v19 & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v15);
  }
  wil::details::WilFailFast((wil::details *)&v18, v14);
}

```

## disassembly

```asm
0x1800077dc  mov     [rsp-8+arg_18], rbx
0x1800077e1  push    rbp
0x1800077e2  push    rsi
0x1800077e3  push    rdi
0x1800077e4  push    r12
0x1800077e6  push    r13
0x1800077e8  push    r14
0x1800077ea  push    r15
0x1800077ec  lea     rbp, [rsp-13C0h]
0x1800077f4  mov     eax, 14C0h
0x1800077f9  call    _alloca_probe
0x1800077fe  sub     rsp, rax
0x180007801  mov     r14, r8
0x180007804  mov     esi, edx
0x180007806  mov     rdi, rcx
0x180007809  mov     r15, [rbp+13F0h+arg_28]
0x180007810  xor     edx, edx; Val
0x180007812  mov     r8d, 98h; Size
0x180007818  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x18000781d  call    memset_0
0x180007822  nop
0x180007823  xor     r13d, r13d
0x180007826  mov     [rbp+13F0h+OutputString], r13w
0x18000782e  mov     [rbp+13F0h+var_1430], r13b
0x180007832  mov     rbx, [rbp+13F0h+arg_30]
0x180007839  mov     ecx, [rbx]; this
0x18000783b  mov     [rsp+14F0h+var_14C8], ecx
0x18000783f  mov     eax, [rbx+4]
0x180007842  mov     [rsp+14F0h+var_14C4], eax
0x180007846  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000784b  mov     r12d, eax
0x18000784e  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x180007856  mov     ecx, r13d
0x180007859  lea     eax, [r13+8]
0x18000785d  cmp     dword ptr [rbx+8], 1
0x180007861  cmovz   ecx, eax
0x180007864  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180007868  lea     ecx, [rax-7]
0x18000786b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180007873  inc     ecx
0x180007875  mov     [rsp+14F0h+var_14C0], ecx
0x180007879  mov     rcx, [rbp+13F0h+arg_38]
0x180007880  test    rcx, rcx
0x180007883  jz      short loc_180007890
0x180007885  cmp     [rcx], r13w
0x180007889  mov     [rsp+14F0h+var_14B8], rcx
0x18000788e  jnz     short loc_180007895
0x180007890  mov     [rsp+14F0h+var_14B8], r13
0x180007895  call    cs:__imp_GetCurrentThreadId
0x18000789b  mov     [rsp+14F0h+var_14B0], eax
0x18000789f  mov     [rsp+14F0h+var_1498], r14
0x1800078a4  mov     [rsp+14F0h+var_1490], esi
0x1800078a8  mov     [rsp+14F0h+var_148C], r12d
0x1800078ad  mov     [rsp+14F0h+var_14A8], r13
0x1800078b2  mov     [rsp+14F0h+var_14A0], r13
0x1800078b7  mov     [rbp+13F0h+var_1448], r15
0x1800078bb  mov     [rbp+13F0h+var_1440], rdi
0x1800078bf  mov     [rsp+14F0h+var_1488], r13
0x1800078c4  xorps   xmm0, xmm0
0x1800078c7  xor     eax, eax
0x1800078c9  movups  [rbp+13F0h+var_1468], xmm0
0x1800078cd  mov     [rbp+13F0h+var_1458], rax
0x1800078d1  xorps   xmm1, xmm1
0x1800078d4  movups  [rsp+14F0h+var_1480], xmm1
0x1800078d9  mov     [rbp+13F0h+var_1470], rax
0x1800078dd  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800078e4  test    rax, rax
0x1800078e7  jz      short loc_1800078F4
0x1800078e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800078ee  mov     [rbp+13F0h+var_1450], rax
0x1800078f2  jmp     short loc_1800078F8
0x1800078f4  mov     [rbp+13F0h+var_1450], r13
0x1800078f8  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800078ff  test    rax, rax
0x180007902  jz      short loc_18000790E
0x180007904  lea     rcx, [rsp+14F0h+var_14D0]
0x180007909  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000790e  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180007915  test    rax, rax
0x180007918  jz      short loc_18000792E
0x18000791a  mov     r8d, 400h
0x180007920  lea     rdx, [rbp+13F0h+var_1430]
0x180007924  lea     rcx, [rsp+14F0h+var_14D0]
0x180007929  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000792e  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180007935  test    rax, rax
0x180007938  jz      short loc_180007944
0x18000793a  lea     rcx, [rsp+14F0h+var_14D0]
0x18000793f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007944  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000794b  test    rax, rax
0x18000794e  jz      short loc_180007961
0x180007950  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180007955  jnz     short loc_180007961
0x180007957  lea     rcx, [rsp+14F0h+var_14D0]
0x18000795c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007961  cmp     [rsp+14F0h+var_14C8], r13d
0x180007966  jl      short loc_18000797A
0x180007968  mov     ecx, 8000FFFFh; this
0x18000796d  mov     [rsp+14F0h+var_14C8], ecx
0x180007971  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180007976  mov     [rsp+14F0h+var_14C4], eax
0x18000797a  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x180007981  jnz     short loc_1800079A2
0x180007983  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000798a  test    rax, rax
0x18000798d  jz      short loc_180007998
0x18000798f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007994  test    al, al
0x180007996  jmp     short loc_1800079A0
0x180007998  call    cs:__imp_IsDebuggerPresent
0x18000799e  test    eax, eax
0x1800079a0  jz      short loc_1800079A9
0x1800079a2  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800079a7  jz      short loc_1800079CF
0x1800079a9  mov     rax, cs:g_pfnResultLoggingCallback
0x1800079b0  test    rax, rax
0x1800079b3  jz      short loc_180007A28
0x1800079b5  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x1800079bc  jnz     short loc_180007A28
0x1800079be  xor     r8d, r8d
0x1800079c1  xor     edx, edx
0x1800079c3  lea     rcx, [rsp+14F0h+var_14D0]
0x1800079c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800079cd  jmp     short loc_180007A28
0x1800079cf  mov     ebx, 800h
0x1800079d4  mov     rax, cs:g_pfnResultLoggingCallback
0x1800079db  test    rax, rax
0x1800079de  jz      short loc_1800079FD
0x1800079e0  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x1800079e7  jnz     short loc_1800079FD
0x1800079e9  mov     r8d, ebx
0x1800079ec  lea     rdx, [rbp+13F0h+OutputString]
0x1800079f3  lea     rcx, [rsp+14F0h+var_14D0]
0x1800079f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800079fd  cmp     [rbp+13F0h+OutputString], r13w
0x180007a05  jnz     short loc_180007A1B
0x180007a07  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180007a0c  mov     rdx, rbx; unsigned __int16 *
0x180007a0f  lea     rcx, [rbp+13F0h+OutputString]; this
0x180007a16  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180007a1b  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180007a22  call    cs:__imp_OutputDebugStringW
0x180007a28  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180007a2d  jnz     short loc_180007A38
0x180007a2f  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x180007a36  jz      short loc_180007A4A
0x180007a38  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180007a3f  test    rax, rax
0x180007a42  jz      short loc_180007A4A
0x180007a44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a49  nop
0x180007a4a  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180007a4f  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
