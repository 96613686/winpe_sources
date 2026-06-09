# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x1400027b4`
- end: `0x140002a2d`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `633`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x140002358`

## callees

- `0x140001ebf`
- `0x1400027b4`
- `0x140005204`
- `0x140006940`
- `0x140007390`
- `0x140008510`
- `0x14000df90`
- `0x140010010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000286d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000286d`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140002970`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140002970`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1400029fa`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1400029fa`

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
0x1400027b4  mov     [rsp-8+arg_18], rbx
0x1400027b9  push    rbp
0x1400027ba  push    rsi
0x1400027bb  push    rdi
0x1400027bc  push    r12
0x1400027be  push    r13
0x1400027c0  push    r14
0x1400027c2  push    r15
0x1400027c4  lea     rbp, [rsp-13C0h]
0x1400027cc  mov     eax, 14C0h
0x1400027d1  call    _alloca_probe
0x1400027d6  sub     rsp, rax
0x1400027d9  mov     r14, r8
0x1400027dc  mov     esi, edx
0x1400027de  mov     rdi, rcx
0x1400027e1  mov     r15, [rbp+13F0h+arg_28]
0x1400027e8  xor     edx, edx; Val
0x1400027ea  mov     r8d, 98h; Size
0x1400027f0  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x1400027f5  call    memset_0
0x1400027fa  nop
0x1400027fb  xor     r13d, r13d
0x1400027fe  mov     [rbp+13F0h+OutputString], r13w
0x140002806  mov     [rbp+13F0h+var_1430], r13b
0x14000280a  mov     rbx, [rbp+13F0h+arg_30]
0x140002811  mov     ecx, [rbx]; this
0x140002813  mov     [rsp+14F0h+var_14C8], ecx
0x140002817  mov     eax, [rbx+4]
0x14000281a  mov     [rsp+14F0h+var_14C4], eax
0x14000281e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x140002823  mov     r12d, eax
0x140002826  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x14000282e  mov     ecx, r13d
0x140002831  lea     eax, [r13+8]
0x140002835  cmp     dword ptr [rbx+8], 1
0x140002839  cmovz   ecx, eax
0x14000283c  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x140002840  lea     ecx, [rax-7]
0x140002843  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x14000284b  inc     ecx
0x14000284d  mov     [rsp+14F0h+var_14C0], ecx
0x140002851  mov     rcx, [rbp+13F0h+arg_38]
0x140002858  test    rcx, rcx
0x14000285b  jz      short loc_140002868
0x14000285d  cmp     [rcx], r13w
0x140002861  mov     [rsp+14F0h+var_14B8], rcx
0x140002866  jnz     short loc_14000286D
0x140002868  mov     [rsp+14F0h+var_14B8], r13
0x14000286d  call    cs:__imp_GetCurrentThreadId
0x140002873  mov     [rsp+14F0h+var_14B0], eax
0x140002877  mov     [rsp+14F0h+var_1498], r14
0x14000287c  mov     [rsp+14F0h+var_1490], esi
0x140002880  mov     [rsp+14F0h+var_148C], r12d
0x140002885  mov     [rsp+14F0h+var_14A8], r13
0x14000288a  mov     [rsp+14F0h+var_14A0], r13
0x14000288f  mov     [rbp+13F0h+var_1448], r15
0x140002893  mov     [rbp+13F0h+var_1440], rdi
0x140002897  mov     [rsp+14F0h+var_1488], r13
0x14000289c  xorps   xmm0, xmm0
0x14000289f  xor     eax, eax
0x1400028a1  movups  [rbp+13F0h+var_1468], xmm0
0x1400028a5  mov     [rbp+13F0h+var_1458], rax
0x1400028a9  xorps   xmm1, xmm1
0x1400028ac  movups  [rsp+14F0h+var_1480], xmm1
0x1400028b1  mov     [rbp+13F0h+var_1470], rax
0x1400028b5  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1400028bc  test    rax, rax
0x1400028bf  jz      short loc_1400028CC
0x1400028c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400028c6  mov     [rbp+13F0h+var_1450], rax
0x1400028ca  jmp     short loc_1400028D0
0x1400028cc  mov     [rbp+13F0h+var_1450], r13
0x1400028d0  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1400028d7  test    rax, rax
0x1400028da  jz      short loc_1400028E6
0x1400028dc  lea     rcx, [rsp+14F0h+var_14D0]
0x1400028e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400028e6  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1400028ed  test    rax, rax
0x1400028f0  jz      short loc_140002906
0x1400028f2  mov     r8d, 400h
0x1400028f8  lea     rdx, [rbp+13F0h+var_1430]
0x1400028fc  lea     rcx, [rsp+14F0h+var_14D0]
0x140002901  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002906  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14000290d  test    rax, rax
0x140002910  jz      short loc_14000291C
0x140002912  lea     rcx, [rsp+14F0h+var_14D0]
0x140002917  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000291c  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140002923  test    rax, rax
0x140002926  jz      short loc_140002939
0x140002928  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x14000292d  jnz     short loc_140002939
0x14000292f  lea     rcx, [rsp+14F0h+var_14D0]
0x140002934  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002939  cmp     [rsp+14F0h+var_14C8], r13d
0x14000293e  jl      short loc_140002952
0x140002940  mov     ecx, 8000FFFFh; this
0x140002945  mov     [rsp+14F0h+var_14C8], ecx
0x140002949  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x14000294e  mov     [rsp+14F0h+var_14C4], eax
0x140002952  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x140002959  jnz     short loc_14000297A
0x14000295b  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140002962  test    rax, rax
0x140002965  jz      short loc_140002970
0x140002967  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000296c  test    al, al
0x14000296e  jmp     short loc_140002978
0x140002970  call    cs:__imp_IsDebuggerPresent
0x140002976  test    eax, eax
0x140002978  jz      short loc_140002981
0x14000297a  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x14000297f  jz      short loc_1400029A7
0x140002981  mov     rax, cs:g_pfnResultLoggingCallback
0x140002988  test    rax, rax
0x14000298b  jz      short loc_140002A00
0x14000298d  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x140002994  jnz     short loc_140002A00
0x140002996  xor     r8d, r8d
0x140002999  xor     edx, edx
0x14000299b  lea     rcx, [rsp+14F0h+var_14D0]
0x1400029a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400029a5  jmp     short loc_140002A00
0x1400029a7  mov     ebx, 800h
0x1400029ac  mov     rax, cs:g_pfnResultLoggingCallback
0x1400029b3  test    rax, rax
0x1400029b6  jz      short loc_1400029D5
0x1400029b8  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x1400029bf  jnz     short loc_1400029D5
0x1400029c1  mov     r8d, ebx
0x1400029c4  lea     rdx, [rbp+13F0h+OutputString]
0x1400029cb  lea     rcx, [rsp+14F0h+var_14D0]
0x1400029d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400029d5  cmp     [rbp+13F0h+OutputString], r13w
0x1400029dd  jnz     short loc_1400029F3
0x1400029df  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x1400029e4  mov     rdx, rbx; unsigned __int16 *
0x1400029e7  lea     rcx, [rbp+13F0h+OutputString]; this
0x1400029ee  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1400029f3  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x1400029fa  call    cs:__imp_OutputDebugStringW
0x140002a00  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x140002a05  jnz     short loc_140002A10
0x140002a07  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x140002a0e  jz      short loc_140002A22
0x140002a10  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140002a17  test    rax, rax
0x140002a1a  jz      short loc_140002A22
0x140002a1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002a21  nop
0x140002a22  lea     rcx, [rsp+14F0h+var_14D0]; this
0x140002a27  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
