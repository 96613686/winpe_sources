# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180021cd0`
- end: `0x180021f30`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `608`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180021a9c`

## callees

- `0x18001b934`
- `0x18001bc44`
- `0x18001c020`
- `0x180021cd0`
- `0x180025cf4`
- `0x1800396f2`
- `0x180039800`
- `0x18003f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180021d71`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180021d71`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180021efe`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180021efe`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180021e74`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180021e74`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<3>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7)
{
  int v10; // eax
  int v11; // edx
  int v12; // eax
  int v13; // edi
  int v14; // ecx
  DWORD CurrentThreadId; // eax
  const struct wil::FailureInfo *v16; // rdx
  __int64 v17; // rcx
  const struct wil::FailureInfo *v18; // r9
  bool v19; // zf
  int v20; // [rsp+20h] [rbp-E0h] BYREF
  int v21; // [rsp+24h] [rbp-DCh]
  int v22; // [rsp+28h] [rbp-D8h]
  int v23; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v24; // [rsp+30h] [rbp-D0h]
  __int64 v25; // [rsp+38h] [rbp-C8h]
  DWORD v26; // [rsp+40h] [rbp-C0h]
  __int64 v27; // [rsp+48h] [rbp-B8h]
  __int64 v28; // [rsp+50h] [rbp-B0h]
  __int64 v29; // [rsp+58h] [rbp-A8h]
  int v30; // [rsp+60h] [rbp-A0h]
  int v31; // [rsp+64h] [rbp-9Ch]
  __int64 v32; // [rsp+68h] [rbp-98h]
  __int128 v33; // [rsp+70h] [rbp-90h]
  __int64 v34; // [rsp+80h] [rbp-80h]
  __int128 v35; // [rsp+88h] [rbp-78h]
  __int64 v36; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v38; // [rsp+A8h] [rbp-58h]
  __int64 v39; // [rsp+B0h] [rbp-50h]
  char v40[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2072]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v20, 0, 0x98u);
  OutputString[0] = 0;
  v40[0] = 0;
  v10 = a7[1];
  v22 = *a7;
  v23 = v10;
  v12 = wil::details::RecordFailFast((wil::details *)(unsigned int)v22, v11);
  v19 = a7[2] == 1;
  v13 = v12;
  v20 = 3;
  v14 = 0;
  if ( v19 )
    v14 = 8;
  v21 = v14;
  v25 = 0;
  v24 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  CurrentThreadId = GetCurrentThreadId();
  v29 = a3;
  v26 = CurrentThreadId;
  v30 = a2;
  v36 = 0;
  v34 = 0;
  v31 = v13;
  v27 = 0;
  v28 = 0;
  v38 = a6;
  v39 = a1;
  v32 = 0;
  v35 = 0;
  v33 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v17);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v20);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v20, v40, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v20);
  if ( wil::details::g_pfnOriginateCallback && (v21 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v20);
  if ( v22 >= 0 )
  {
    v22 = -2147418113;
    v23 = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, (int)v16);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v19 = !IsDebuggerPresent())
      : (v19 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v17) == 0),
        v19)
    || (v21 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v20, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v20, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (__int64)&v20, v18);
    OutputDebugStringW(OutputString);
  }
  if ( (v21 & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v17);
  }
  wil::details::WilFailFast((wil::details *)&v20, v16);
}

```

## disassembly

```asm
0x180021cd0  mov     [rsp-8+arg_18], rbx
0x180021cd5  push    rbp
0x180021cd6  push    rsi
0x180021cd7  push    rdi
0x180021cd8  push    r12
0x180021cda  push    r13
0x180021cdc  push    r14
0x180021cde  push    r15
0x180021ce0  lea     rbp, [rsp-13C0h]
0x180021ce8  mov     eax, 14C0h
0x180021ced  call    _alloca_probe
0x180021cf2  sub     rsp, rax
0x180021cf5  mov     rsi, [rbp+13F0h+arg_28]
0x180021cfc  mov     r15, r8
0x180021cff  mov     r14d, edx
0x180021d02  mov     r12, rcx
0x180021d05  xor     edx, edx; Val
0x180021d07  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180021d0c  mov     r8d, 98h; Size
0x180021d12  call    memset_0
0x180021d17  mov     rbx, [rbp+13F0h+arg_30]
0x180021d1e  xor     r13d, r13d
0x180021d21  mov     [rbp+13F0h+OutputString], r13w
0x180021d29  mov     [rbp+13F0h+var_1430], r13b
0x180021d2d  mov     ecx, [rbx]; this
0x180021d2f  mov     eax, [rbx+4]
0x180021d32  mov     [rsp+14F0h+var_14C8], ecx
0x180021d36  mov     [rsp+14F0h+var_14C4], eax
0x180021d3a  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180021d3f  cmp     dword ptr [rbx+8], 1
0x180021d43  mov     edi, eax
0x180021d45  lea     eax, [r13+8]
0x180021d49  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x180021d51  mov     ecx, r13d
0x180021d54  cmovz   ecx, eax
0x180021d57  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180021d5b  lea     ecx, [rax-7]
0x180021d5e  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180021d66  inc     ecx
0x180021d68  mov     [rsp+14F0h+var_14B8], r13
0x180021d6d  mov     [rsp+14F0h+var_14C0], ecx
0x180021d71  call    cs:__imp_GetCurrentThreadId
0x180021d77  xorps   xmm0, xmm0
0x180021d7a  mov     [rsp+14F0h+var_1498], r15
0x180021d7f  mov     [rsp+14F0h+var_14B0], eax
0x180021d83  xorps   xmm1, xmm1
0x180021d86  xor     eax, eax
0x180021d88  mov     [rsp+14F0h+var_1490], r14d
0x180021d8d  mov     [rbp+13F0h+var_1458], rax
0x180021d91  mov     [rbp+13F0h+var_1470], rax
0x180021d95  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180021d9c  mov     [rsp+14F0h+var_148C], edi
0x180021da0  mov     [rsp+14F0h+var_14A8], r13
0x180021da5  mov     [rsp+14F0h+var_14A0], r13
0x180021daa  mov     [rbp+13F0h+var_1448], rsi
0x180021dae  mov     [rbp+13F0h+var_1440], r12
0x180021db2  mov     [rsp+14F0h+var_1488], r13
0x180021db7  movups  [rbp+13F0h+var_1468], xmm0
0x180021dbb  movups  [rsp+14F0h+var_1480], xmm1
0x180021dc0  test    rax, rax
0x180021dc3  jz      short loc_180021DD0
0x180021dc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021dca  mov     [rbp+13F0h+var_1450], rax
0x180021dce  jmp     short loc_180021DD4
0x180021dd0  mov     [rbp+13F0h+var_1450], r13
0x180021dd4  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180021ddb  test    rax, rax
0x180021dde  jz      short loc_180021DEA
0x180021de0  lea     rcx, [rsp+14F0h+var_14D0]
0x180021de5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021dea  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180021df1  test    rax, rax
0x180021df4  jz      short loc_180021E0A
0x180021df6  mov     r8d, 400h
0x180021dfc  lea     rdx, [rbp+13F0h+var_1430]
0x180021e00  lea     rcx, [rsp+14F0h+var_14D0]
0x180021e05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021e0a  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180021e11  test    rax, rax
0x180021e14  jz      short loc_180021E20
0x180021e16  lea     rcx, [rsp+14F0h+var_14D0]
0x180021e1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021e20  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180021e27  test    rax, rax
0x180021e2a  jz      short loc_180021E3D
0x180021e2c  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180021e31  jnz     short loc_180021E3D
0x180021e33  lea     rcx, [rsp+14F0h+var_14D0]
0x180021e38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021e3d  cmp     [rsp+14F0h+var_14C8], r13d
0x180021e42  jl      short loc_180021E56
0x180021e44  mov     ecx, 8000FFFFh; this
0x180021e49  mov     [rsp+14F0h+var_14C8], ecx
0x180021e4d  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180021e52  mov     [rsp+14F0h+var_14C4], eax
0x180021e56  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x180021e5d  jnz     short loc_180021E7E
0x180021e5f  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180021e66  test    rax, rax
0x180021e69  jz      short loc_180021E74
0x180021e6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021e70  test    al, al
0x180021e72  jmp     short loc_180021E7C
0x180021e74  call    cs:__imp_IsDebuggerPresent
0x180021e7a  test    eax, eax
0x180021e7c  jz      short loc_180021E85
0x180021e7e  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180021e83  jz      short loc_180021EAB
0x180021e85  mov     rax, cs:g_pfnResultLoggingCallback
0x180021e8c  test    rax, rax
0x180021e8f  jz      short loc_180021F04
0x180021e91  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180021e98  jnz     short loc_180021F04
0x180021e9a  xor     r8d, r8d
0x180021e9d  lea     rcx, [rsp+14F0h+var_14D0]
0x180021ea2  xor     edx, edx
0x180021ea4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021ea9  jmp     short loc_180021F04
0x180021eab  mov     rax, cs:g_pfnResultLoggingCallback
0x180021eb2  mov     ebx, 800h
0x180021eb7  test    rax, rax
0x180021eba  jz      short loc_180021ED9
0x180021ebc  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180021ec3  jnz     short loc_180021ED9
0x180021ec5  mov     r8d, ebx
0x180021ec8  lea     rdx, [rbp+13F0h+OutputString]
0x180021ecf  lea     rcx, [rsp+14F0h+var_14D0]
0x180021ed4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021ed9  cmp     [rbp+13F0h+OutputString], r13w
0x180021ee1  jnz     short loc_180021EF7
0x180021ee3  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180021ee8  mov     rdx, rbx; unsigned __int16 *
0x180021eeb  lea     rcx, [rbp+13F0h+OutputString]; this
0x180021ef2  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180021ef7  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180021efe  call    cs:__imp_OutputDebugStringW
0x180021f04  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180021f09  jnz     short loc_180021F14
0x180021f0b  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x180021f12  jz      short loc_180021F25
0x180021f14  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180021f1b  test    rax, rax
0x180021f1e  jz      short loc_180021F25
0x180021f20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021f25  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180021f2a  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
