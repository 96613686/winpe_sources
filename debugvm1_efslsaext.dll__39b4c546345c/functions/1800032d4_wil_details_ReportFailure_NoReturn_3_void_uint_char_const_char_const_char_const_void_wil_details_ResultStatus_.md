# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x1800032d4`
- end: `0x180003534`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `608`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180003078`

## callees

- `0x180002b90`
- `0x1800032d4`
- `0x18000459c`
- `0x180004c24`
- `0x180006210`
- `0x18001200e`
- `0x1800120d0`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003502`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003502`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003478`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003478`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003375`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003375`

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
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v20, v18);
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
0x1800032d4  mov     [rsp-8+arg_18], rbx
0x1800032d9  push    rbp
0x1800032da  push    rsi
0x1800032db  push    rdi
0x1800032dc  push    r12
0x1800032de  push    r13
0x1800032e0  push    r14
0x1800032e2  push    r15
0x1800032e4  lea     rbp, [rsp-13C0h]
0x1800032ec  mov     eax, 14C0h
0x1800032f1  call    _alloca_probe
0x1800032f6  sub     rsp, rax
0x1800032f9  mov     rsi, [rbp+13F0h+arg_28]
0x180003300  mov     r15, r8
0x180003303  mov     r14d, edx
0x180003306  mov     r12, rcx
0x180003309  xor     edx, edx; Val
0x18000330b  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180003310  mov     r8d, 98h; Size
0x180003316  call    memset_0
0x18000331b  mov     rbx, [rbp+13F0h+arg_30]
0x180003322  xor     r13d, r13d
0x180003325  mov     [rbp+13F0h+OutputString], r13w
0x18000332d  mov     [rbp+13F0h+var_1430], r13b
0x180003331  mov     ecx, [rbx]; this
0x180003333  mov     eax, [rbx+4]
0x180003336  mov     [rsp+14F0h+var_14C8], ecx
0x18000333a  mov     [rsp+14F0h+var_14C4], eax
0x18000333e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180003343  cmp     dword ptr [rbx+8], 1
0x180003347  mov     edi, eax
0x180003349  lea     eax, [r13+8]
0x18000334d  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x180003355  mov     ecx, r13d
0x180003358  cmovz   ecx, eax
0x18000335b  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x18000335f  lea     ecx, [rax-7]
0x180003362  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000336a  inc     ecx
0x18000336c  mov     [rsp+14F0h+var_14B8], r13
0x180003371  mov     [rsp+14F0h+var_14C0], ecx
0x180003375  call    cs:__imp_GetCurrentThreadId
0x18000337b  xorps   xmm0, xmm0
0x18000337e  mov     [rsp+14F0h+var_1498], r15
0x180003383  mov     [rsp+14F0h+var_14B0], eax
0x180003387  xorps   xmm1, xmm1
0x18000338a  xor     eax, eax
0x18000338c  mov     [rsp+14F0h+var_1490], r14d
0x180003391  mov     [rbp+13F0h+var_1458], rax
0x180003395  mov     [rbp+13F0h+var_1470], rax
0x180003399  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800033a0  mov     [rsp+14F0h+var_148C], edi
0x1800033a4  mov     [rsp+14F0h+var_14A8], r13
0x1800033a9  mov     [rsp+14F0h+var_14A0], r13
0x1800033ae  mov     [rbp+13F0h+var_1448], rsi
0x1800033b2  mov     [rbp+13F0h+var_1440], r12
0x1800033b6  mov     [rsp+14F0h+var_1488], r13
0x1800033bb  movups  [rbp+13F0h+var_1468], xmm0
0x1800033bf  movups  [rsp+14F0h+var_1480], xmm1
0x1800033c4  test    rax, rax
0x1800033c7  jz      short loc_1800033D4
0x1800033c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800033ce  mov     [rbp+13F0h+var_1450], rax
0x1800033d2  jmp     short loc_1800033D8
0x1800033d4  mov     [rbp+13F0h+var_1450], r13
0x1800033d8  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800033df  test    rax, rax
0x1800033e2  jz      short loc_1800033EE
0x1800033e4  lea     rcx, [rsp+14F0h+var_14D0]
0x1800033e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800033ee  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800033f5  test    rax, rax
0x1800033f8  jz      short loc_18000340E
0x1800033fa  mov     r8d, 400h
0x180003400  lea     rdx, [rbp+13F0h+var_1430]
0x180003404  lea     rcx, [rsp+14F0h+var_14D0]
0x180003409  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000340e  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003415  test    rax, rax
0x180003418  jz      short loc_180003424
0x18000341a  lea     rcx, [rsp+14F0h+var_14D0]
0x18000341f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003424  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000342b  test    rax, rax
0x18000342e  jz      short loc_180003441
0x180003430  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180003435  jnz     short loc_180003441
0x180003437  lea     rcx, [rsp+14F0h+var_14D0]
0x18000343c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003441  cmp     [rsp+14F0h+var_14C8], r13d
0x180003446  jl      short loc_18000345A
0x180003448  mov     ecx, 8000FFFFh; this
0x18000344d  mov     [rsp+14F0h+var_14C8], ecx
0x180003451  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180003456  mov     [rsp+14F0h+var_14C4], eax
0x18000345a  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x180003461  jnz     short loc_180003482
0x180003463  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000346a  test    rax, rax
0x18000346d  jz      short loc_180003478
0x18000346f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003474  test    al, al
0x180003476  jmp     short loc_180003480
0x180003478  call    cs:__imp_IsDebuggerPresent
0x18000347e  test    eax, eax
0x180003480  jz      short loc_180003489
0x180003482  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180003487  jz      short loc_1800034AF
0x180003489  mov     rax, cs:g_pfnResultLoggingCallback
0x180003490  test    rax, rax
0x180003493  jz      short loc_180003508
0x180003495  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x18000349c  jnz     short loc_180003508
0x18000349e  xor     r8d, r8d
0x1800034a1  lea     rcx, [rsp+14F0h+var_14D0]
0x1800034a6  xor     edx, edx
0x1800034a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800034ad  jmp     short loc_180003508
0x1800034af  mov     rax, cs:g_pfnResultLoggingCallback
0x1800034b6  mov     ebx, 800h
0x1800034bb  test    rax, rax
0x1800034be  jz      short loc_1800034DD
0x1800034c0  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x1800034c7  jnz     short loc_1800034DD
0x1800034c9  mov     r8d, ebx
0x1800034cc  lea     rdx, [rbp+13F0h+OutputString]
0x1800034d3  lea     rcx, [rsp+14F0h+var_14D0]
0x1800034d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800034dd  cmp     [rbp+13F0h+OutputString], r13w
0x1800034e5  jnz     short loc_1800034FB
0x1800034e7  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x1800034ec  mov     rdx, rbx; unsigned __int16 *
0x1800034ef  lea     rcx, [rbp+13F0h+OutputString]; this
0x1800034f6  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800034fb  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180003502  call    cs:__imp_OutputDebugStringW
0x180003508  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x18000350d  jnz     short loc_180003518
0x18000350f  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x180003516  jz      short loc_180003529
0x180003518  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000351f  test    rax, rax
0x180003522  jz      short loc_180003529
0x180003524  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003529  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000352e  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
