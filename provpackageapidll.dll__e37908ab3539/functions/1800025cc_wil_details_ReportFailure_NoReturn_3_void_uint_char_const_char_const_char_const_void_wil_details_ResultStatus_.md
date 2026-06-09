# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x1800025cc`
- end: `0x180002835`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `617`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180002378`

## callees

- `0x180001e66`
- `0x1800025cc`
- `0x1800039a4`
- `0x18000414c`
- `0x180004870`
- `0x180005860`
- `0x1800183e0`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000266e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000266e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002778`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002778`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180002802`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180002802`

## string_xrefs

- `0x180002678`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
  int v9; // edx
  int v10; // edi
  int v11; // ecx
  const struct wil::FailureInfo *v12; // rdx
  __int64 v13; // rcx
  const struct wil::FailureInfo *v14; // r9
  bool v15; // zf
  int v16; // [rsp+20h] [rbp-E0h] BYREF
  int v17; // [rsp+24h] [rbp-DCh]
  int v18; // [rsp+28h] [rbp-D8h]
  int v19; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v20; // [rsp+30h] [rbp-D0h]
  __int64 v21; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v23; // [rsp+48h] [rbp-B8h]
  __int64 v24; // [rsp+50h] [rbp-B0h]
  const char *v25; // [rsp+58h] [rbp-A8h]
  int v26; // [rsp+60h] [rbp-A0h]
  int v27; // [rsp+64h] [rbp-9Ch]
  __int64 v28; // [rsp+68h] [rbp-98h]
  __int128 v29; // [rsp+70h] [rbp-90h]
  __int64 v30; // [rsp+80h] [rbp-80h]
  __int128 v31; // [rsp+88h] [rbp-78h]
  __int64 v32; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v34; // [rsp+A8h] [rbp-58h]
  __int64 v35; // [rsp+B0h] [rbp-50h]
  char v36[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2064]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v16, 0, 0x98u);
  OutputString[0] = 0;
  v36[0] = 0;
  v18 = *a7;
  v19 = a7[1];
  v10 = wil::details::RecordFailFast((wil::details *)(unsigned int)v18, v9);
  v16 = 3;
  v11 = 0;
  if ( a7[2] == 1 )
    v11 = 8;
  v17 = v11;
  v20 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v21 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v25 = "onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h";
  v26 = a2;
  v27 = v10;
  v23 = 0;
  v24 = 0;
  v34 = a6;
  v35 = a1;
  v28 = 0;
  v31 = 0;
  v32 = 0;
  v29 = 0;
  v30 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v13);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v16);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v16, v36, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v16);
  if ( wil::details::g_pfnOriginateCallback && (v17 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v16);
  if ( v18 >= 0 )
  {
    v18 = -2147418113;
    v19 = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, (int)v12);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v15 = !IsDebuggerPresent())
      : (v15 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v13) == 0),
        v15)
    || (v17 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v16, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v16, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v16, v14);
    OutputDebugStringW(OutputString);
  }
  if ( (v17 & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v13);
  }
  wil::details::WilFailFast((wil::details *)&v16, v12);
}

```

## disassembly

```asm
0x1800025cc  mov     [rsp-8+arg_10], rbx
0x1800025d1  mov     [rsp-8+arg_18], rsi
0x1800025d6  push    rbp
0x1800025d7  push    rdi
0x1800025d8  push    r12
0x1800025da  push    r14
0x1800025dc  push    r15
0x1800025de  lea     rbp, [rsp-13C0h]
0x1800025e6  mov     eax, 14C0h
0x1800025eb  call    _alloca_probe
0x1800025f0  sub     rsp, rax
0x1800025f3  mov     r14d, edx
0x1800025f6  mov     r15, rcx
0x1800025f9  mov     rsi, [rbp+13E0h+arg_28]
0x180002600  xor     edx, edx; Val
0x180002602  mov     r8d, 98h; Size
0x180002608  lea     rcx, [rsp+14E0h+var_14C0]; void *
0x18000260d  call    memset_0
0x180002612  nop
0x180002613  xor     r12d, r12d
0x180002616  mov     [rbp+13E0h+OutputString], r12w
0x18000261e  mov     [rbp+13E0h+var_1420], r12b
0x180002622  mov     rbx, [rbp+13E0h+arg_30]
0x180002629  mov     ecx, [rbx]; this
0x18000262b  mov     [rsp+14E0h+var_14B8], ecx
0x18000262f  mov     eax, [rbx+4]
0x180002632  mov     [rsp+14E0h+var_14B4], eax
0x180002636  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000263b  mov     edi, eax
0x18000263d  mov     dword ptr [rsp+14E0h+var_14C0], 3
0x180002645  mov     ecx, r12d
0x180002648  lea     eax, [r12+8]
0x18000264d  cmp     dword ptr [rbx+8], 1
0x180002651  cmovz   ecx, eax
0x180002654  mov     dword ptr [rsp+14E0h+var_14C0+4], ecx
0x180002658  lea     ecx, [rax-7]
0x18000265b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180002663  inc     ecx
0x180002665  mov     [rsp+14E0h+var_14B0], ecx
0x180002669  mov     [rsp+14E0h+var_14A8], r12
0x18000266e  call    cs:__imp_GetCurrentThreadId
0x180002674  mov     [rsp+14E0h+var_14A0], eax
0x180002678  lea     rax, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000267f  mov     [rsp+14E0h+var_1488], rax
0x180002684  mov     [rsp+14E0h+var_1480], r14d
0x180002689  mov     [rsp+14E0h+var_147C], edi
0x18000268d  mov     [rsp+14E0h+var_1498], r12
0x180002692  mov     [rsp+14E0h+var_1490], r12
0x180002697  mov     [rbp+13E0h+var_1438], rsi
0x18000269b  mov     [rbp+13E0h+var_1430], r15
0x18000269f  mov     [rsp+14E0h+var_1478], r12
0x1800026a4  xorps   xmm0, xmm0
0x1800026a7  xor     eax, eax
0x1800026a9  movups  [rbp+13E0h+var_1458], xmm0
0x1800026ad  mov     [rbp+13E0h+var_1448], rax
0x1800026b1  xorps   xmm1, xmm1
0x1800026b4  movups  [rsp+14E0h+var_1470], xmm1
0x1800026b9  mov     [rbp+13E0h+var_1460], rax
0x1800026bd  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800026c4  test    rax, rax
0x1800026c7  jz      short loc_1800026D4
0x1800026c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800026ce  mov     [rbp+13E0h+var_1440], rax
0x1800026d2  jmp     short loc_1800026D8
0x1800026d4  mov     [rbp+13E0h+var_1440], r12
0x1800026d8  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800026df  test    rax, rax
0x1800026e2  jz      short loc_1800026EE
0x1800026e4  lea     rcx, [rsp+14E0h+var_14C0]
0x1800026e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800026ee  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800026f5  test    rax, rax
0x1800026f8  jz      short loc_18000270E
0x1800026fa  mov     r8d, 400h
0x180002700  lea     rdx, [rbp+13E0h+var_1420]
0x180002704  lea     rcx, [rsp+14E0h+var_14C0]
0x180002709  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000270e  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002715  test    rax, rax
0x180002718  jz      short loc_180002724
0x18000271a  lea     rcx, [rsp+14E0h+var_14C0]
0x18000271f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002724  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000272b  test    rax, rax
0x18000272e  jz      short loc_180002741
0x180002730  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x180002735  jnz     short loc_180002741
0x180002737  lea     rcx, [rsp+14E0h+var_14C0]
0x18000273c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002741  cmp     [rsp+14E0h+var_14B8], r12d
0x180002746  jl      short loc_18000275A
0x180002748  mov     ecx, 8000FFFFh; this
0x18000274d  mov     [rsp+14E0h+var_14B8], ecx
0x180002751  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180002756  mov     [rsp+14E0h+var_14B4], eax
0x18000275a  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180002761  jnz     short loc_180002782
0x180002763  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000276a  test    rax, rax
0x18000276d  jz      short loc_180002778
0x18000276f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002774  test    al, al
0x180002776  jmp     short loc_180002780
0x180002778  call    cs:__imp_IsDebuggerPresent
0x18000277e  test    eax, eax
0x180002780  jz      short loc_180002789
0x180002782  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x180002787  jz      short loc_1800027AF
0x180002789  mov     rax, cs:g_pfnResultLoggingCallback
0x180002790  test    rax, rax
0x180002793  jz      short loc_180002808
0x180002795  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18000279c  jnz     short loc_180002808
0x18000279e  xor     r8d, r8d
0x1800027a1  xor     edx, edx
0x1800027a3  lea     rcx, [rsp+14E0h+var_14C0]
0x1800027a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800027ad  jmp     short loc_180002808
0x1800027af  mov     ebx, 800h
0x1800027b4  mov     rax, cs:g_pfnResultLoggingCallback
0x1800027bb  test    rax, rax
0x1800027be  jz      short loc_1800027DD
0x1800027c0  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800027c7  jnz     short loc_1800027DD
0x1800027c9  mov     r8d, ebx
0x1800027cc  lea     rdx, [rbp+13E0h+OutputString]
0x1800027d3  lea     rcx, [rsp+14E0h+var_14C0]
0x1800027d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800027dd  cmp     [rbp+13E0h+OutputString], r12w
0x1800027e5  jnz     short loc_1800027FB
0x1800027e7  lea     r8, [rsp+14E0h+var_14C0]; unsigned __int64
0x1800027ec  mov     rdx, rbx; unsigned __int16 *
0x1800027ef  lea     rcx, [rbp+13E0h+OutputString]; this
0x1800027f6  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800027fb  lea     rcx, [rbp+13E0h+OutputString]; lpOutputString
0x180002802  call    cs:__imp_OutputDebugStringW
0x180002808  test    byte ptr [rsp+14E0h+var_14C0+4], 4
0x18000280d  jnz     short loc_180002818
0x18000280f  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180002816  jz      short loc_18000282A
0x180002818  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000281f  test    rax, rax
0x180002822  jz      short loc_18000282A
0x180002824  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002829  nop
0x18000282a  lea     rcx, [rsp+14E0h+var_14C0]; this
0x18000282f  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
