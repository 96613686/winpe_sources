# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x1800032e8`
- end: `0x180003561`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `633`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, __int64, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180003058`

## callees

- `0x18000296c`
- `0x1800032e8`
- `0x1800046f4`
- `0x180004e9c`
- `0x180005600`
- `0x1800066d0`
- `0x18000d560`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800033a1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800033a1`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000352e`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000352e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800034a4`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800034a4`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<3>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
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
      g_pfnResultLoggingCallback(&v18, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v18, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v18, v16);
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
0x1800032e8  mov     [rsp-8+arg_18], rbx
0x1800032ed  push    rbp
0x1800032ee  push    rsi
0x1800032ef  push    rdi
0x1800032f0  push    r12
0x1800032f2  push    r13
0x1800032f4  push    r14
0x1800032f6  push    r15
0x1800032f8  lea     rbp, [rsp-13C0h]
0x180003300  mov     eax, 14C0h
0x180003305  call    _alloca_probe
0x18000330a  sub     rsp, rax
0x18000330d  mov     r14, r8
0x180003310  mov     esi, edx
0x180003312  mov     rdi, rcx
0x180003315  mov     r15, [rbp+13F0h+arg_28]
0x18000331c  xor     edx, edx; Val
0x18000331e  mov     r8d, 98h; Size
0x180003324  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180003329  call    memset_0
0x18000332e  nop
0x18000332f  xor     r13d, r13d
0x180003332  mov     [rbp+13F0h+OutputString], r13w
0x18000333a  mov     [rbp+13F0h+var_1430], r13b
0x18000333e  mov     rbx, [rbp+13F0h+arg_30]
0x180003345  mov     ecx, [rbx]; this
0x180003347  mov     [rsp+14F0h+var_14C8], ecx
0x18000334b  mov     eax, [rbx+4]
0x18000334e  mov     [rsp+14F0h+var_14C4], eax
0x180003352  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180003357  mov     r12d, eax
0x18000335a  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x180003362  mov     ecx, r13d
0x180003365  lea     eax, [r13+8]
0x180003369  cmp     dword ptr [rbx+8], 1
0x18000336d  cmovz   ecx, eax
0x180003370  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180003374  lea     ecx, [rax-7]
0x180003377  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000337f  inc     ecx
0x180003381  mov     [rsp+14F0h+var_14C0], ecx
0x180003385  mov     rcx, [rbp+13F0h+arg_38]
0x18000338c  test    rcx, rcx
0x18000338f  jz      short loc_18000339C
0x180003391  cmp     [rcx], r13w
0x180003395  mov     [rsp+14F0h+var_14B8], rcx
0x18000339a  jnz     short loc_1800033A1
0x18000339c  mov     [rsp+14F0h+var_14B8], r13
0x1800033a1  call    cs:__imp_GetCurrentThreadId
0x1800033a7  mov     [rsp+14F0h+var_14B0], eax
0x1800033ab  mov     [rsp+14F0h+var_1498], r14
0x1800033b0  mov     [rsp+14F0h+var_1490], esi
0x1800033b4  mov     [rsp+14F0h+var_148C], r12d
0x1800033b9  mov     [rsp+14F0h+var_14A8], r13
0x1800033be  mov     [rsp+14F0h+var_14A0], r13
0x1800033c3  mov     [rbp+13F0h+var_1448], r15
0x1800033c7  mov     [rbp+13F0h+var_1440], rdi
0x1800033cb  mov     [rsp+14F0h+var_1488], r13
0x1800033d0  xorps   xmm0, xmm0
0x1800033d3  xor     eax, eax
0x1800033d5  movups  [rbp+13F0h+var_1468], xmm0
0x1800033d9  mov     [rbp+13F0h+var_1458], rax
0x1800033dd  xorps   xmm1, xmm1
0x1800033e0  movups  [rsp+14F0h+var_1480], xmm1
0x1800033e5  mov     [rbp+13F0h+var_1470], rax
0x1800033e9  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800033f0  test    rax, rax
0x1800033f3  jz      short loc_180003400
0x1800033f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800033fa  mov     [rbp+13F0h+var_1450], rax
0x1800033fe  jmp     short loc_180003404
0x180003400  mov     [rbp+13F0h+var_1450], r13
0x180003404  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000340b  test    rax, rax
0x18000340e  jz      short loc_18000341A
0x180003410  lea     rcx, [rsp+14F0h+var_14D0]
0x180003415  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000341a  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180003421  test    rax, rax
0x180003424  jz      short loc_18000343A
0x180003426  mov     r8d, 400h
0x18000342c  lea     rdx, [rbp+13F0h+var_1430]
0x180003430  lea     rcx, [rsp+14F0h+var_14D0]
0x180003435  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000343a  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003441  test    rax, rax
0x180003444  jz      short loc_180003450
0x180003446  lea     rcx, [rsp+14F0h+var_14D0]
0x18000344b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003450  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003457  test    rax, rax
0x18000345a  jz      short loc_18000346D
0x18000345c  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180003461  jnz     short loc_18000346D
0x180003463  lea     rcx, [rsp+14F0h+var_14D0]
0x180003468  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000346d  cmp     [rsp+14F0h+var_14C8], r13d
0x180003472  jl      short loc_180003486
0x180003474  mov     ecx, 8000FFFFh; this
0x180003479  mov     [rsp+14F0h+var_14C8], ecx
0x18000347d  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180003482  mov     [rsp+14F0h+var_14C4], eax
0x180003486  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x18000348d  jnz     short loc_1800034AE
0x18000348f  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180003496  test    rax, rax
0x180003499  jz      short loc_1800034A4
0x18000349b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800034a0  test    al, al
0x1800034a2  jmp     short loc_1800034AC
0x1800034a4  call    cs:__imp_IsDebuggerPresent
0x1800034aa  test    eax, eax
0x1800034ac  jz      short loc_1800034B5
0x1800034ae  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800034b3  jz      short loc_1800034DB
0x1800034b5  mov     rax, cs:g_pfnResultLoggingCallback
0x1800034bc  test    rax, rax
0x1800034bf  jz      short loc_180003534
0x1800034c1  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x1800034c8  jnz     short loc_180003534
0x1800034ca  xor     r8d, r8d
0x1800034cd  xor     edx, edx
0x1800034cf  lea     rcx, [rsp+14F0h+var_14D0]
0x1800034d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800034d9  jmp     short loc_180003534
0x1800034db  mov     ebx, 800h
0x1800034e0  mov     rax, cs:g_pfnResultLoggingCallback
0x1800034e7  test    rax, rax
0x1800034ea  jz      short loc_180003509
0x1800034ec  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x1800034f3  jnz     short loc_180003509
0x1800034f5  mov     r8d, ebx
0x1800034f8  lea     rdx, [rbp+13F0h+OutputString]
0x1800034ff  lea     rcx, [rsp+14F0h+var_14D0]
0x180003504  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003509  cmp     [rbp+13F0h+OutputString], r13w
0x180003511  jnz     short loc_180003527
0x180003513  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180003518  mov     rdx, rbx; unsigned __int16 *
0x18000351b  lea     rcx, [rbp+13F0h+OutputString]; this
0x180003522  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180003527  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x18000352e  call    cs:__imp_OutputDebugStringW
0x180003534  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180003539  jnz     short loc_180003544
0x18000353b  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x180003542  jz      short loc_180003556
0x180003544  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000354b  test    rax, rax
0x18000354e  jz      short loc_180003556
0x180003550  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003555  nop
0x180003556  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000355b  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
