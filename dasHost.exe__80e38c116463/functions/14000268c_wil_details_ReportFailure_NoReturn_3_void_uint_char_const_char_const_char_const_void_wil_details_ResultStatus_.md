# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x14000268c`
- end: `0x140002905`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `633`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1400023f8`

## callees

- `0x1400020d0`
- `0x14000268c`
- `0x140004c14`
- `0x1400053bc`
- `0x140005ce0`
- `0x1400081e0`
- `0x14001a7d0`
- `0x14001c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140002745`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140002745`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1400028d2`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1400028d2`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140002848`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140002848`

## pseudocode

```c
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
0x14000268c  mov     [rsp-8+arg_18], rbx
0x140002691  push    rbp
0x140002692  push    rsi
0x140002693  push    rdi
0x140002694  push    r12
0x140002696  push    r13
0x140002698  push    r14
0x14000269a  push    r15
0x14000269c  lea     rbp, [rsp-13C0h]
0x1400026a4  mov     eax, 14C0h
0x1400026a9  call    _alloca_probe
0x1400026ae  sub     rsp, rax
0x1400026b1  mov     r14, r8
0x1400026b4  mov     esi, edx
0x1400026b6  mov     rdi, rcx
0x1400026b9  mov     r15, [rbp+13F0h+arg_28]
0x1400026c0  xor     edx, edx; Val
0x1400026c2  mov     r8d, 98h; Size
0x1400026c8  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x1400026cd  call    memset_0
0x1400026d2  nop
0x1400026d3  xor     r13d, r13d
0x1400026d6  mov     [rbp+13F0h+OutputString], r13w
0x1400026de  mov     [rbp+13F0h+var_1430], r13b
0x1400026e2  mov     rbx, [rbp+13F0h+arg_30]
0x1400026e9  mov     ecx, [rbx]; this
0x1400026eb  mov     [rsp+14F0h+var_14C8], ecx
0x1400026ef  mov     eax, [rbx+4]
0x1400026f2  mov     [rsp+14F0h+var_14C4], eax
0x1400026f6  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1400026fb  mov     r12d, eax
0x1400026fe  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x140002706  mov     ecx, r13d
0x140002709  lea     eax, [r13+8]
0x14000270d  cmp     dword ptr [rbx+8], 1
0x140002711  cmovz   ecx, eax
0x140002714  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x140002718  lea     ecx, [rax-7]
0x14000271b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140002723  inc     ecx
0x140002725  mov     [rsp+14F0h+var_14C0], ecx
0x140002729  mov     rcx, [rbp+13F0h+arg_38]
0x140002730  test    rcx, rcx
0x140002733  jz      short loc_140002740
0x140002735  cmp     [rcx], r13w
0x140002739  mov     [rsp+14F0h+var_14B8], rcx
0x14000273e  jnz     short loc_140002745
0x140002740  mov     [rsp+14F0h+var_14B8], r13
0x140002745  call    cs:__imp_GetCurrentThreadId
0x14000274b  mov     [rsp+14F0h+var_14B0], eax
0x14000274f  mov     [rsp+14F0h+var_1498], r14
0x140002754  mov     [rsp+14F0h+var_1490], esi
0x140002758  mov     [rsp+14F0h+var_148C], r12d
0x14000275d  mov     [rsp+14F0h+var_14A8], r13
0x140002762  mov     [rsp+14F0h+var_14A0], r13
0x140002767  mov     [rbp+13F0h+var_1448], r15
0x14000276b  mov     [rbp+13F0h+var_1440], rdi
0x14000276f  mov     [rsp+14F0h+var_1488], r13
0x140002774  xorps   xmm0, xmm0
0x140002777  xor     eax, eax
0x140002779  movups  [rbp+13F0h+var_1468], xmm0
0x14000277d  mov     [rbp+13F0h+var_1458], rax
0x140002781  xorps   xmm1, xmm1
0x140002784  movups  [rsp+14F0h+var_1480], xmm1
0x140002789  mov     [rbp+13F0h+var_1470], rax
0x14000278d  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140002794  test    rax, rax
0x140002797  jz      short loc_1400027A4
0x140002799  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000279e  mov     [rbp+13F0h+var_1450], rax
0x1400027a2  jmp     short loc_1400027A8
0x1400027a4  mov     [rbp+13F0h+var_1450], r13
0x1400027a8  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1400027af  test    rax, rax
0x1400027b2  jz      short loc_1400027BE
0x1400027b4  lea     rcx, [rsp+14F0h+var_14D0]
0x1400027b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400027be  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1400027c5  test    rax, rax
0x1400027c8  jz      short loc_1400027DE
0x1400027ca  mov     r8d, 400h
0x1400027d0  lea     rdx, [rbp+13F0h+var_1430]
0x1400027d4  lea     rcx, [rsp+14F0h+var_14D0]
0x1400027d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400027de  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1400027e5  test    rax, rax
0x1400027e8  jz      short loc_1400027F4
0x1400027ea  lea     rcx, [rsp+14F0h+var_14D0]
0x1400027ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400027f4  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1400027fb  test    rax, rax
0x1400027fe  jz      short loc_140002811
0x140002800  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x140002805  jnz     short loc_140002811
0x140002807  lea     rcx, [rsp+14F0h+var_14D0]
0x14000280c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002811  cmp     [rsp+14F0h+var_14C8], r13d
0x140002816  jl      short loc_14000282A
0x140002818  mov     ecx, 8000FFFFh; this
0x14000281d  mov     [rsp+14F0h+var_14C8], ecx
0x140002821  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140002826  mov     [rsp+14F0h+var_14C4], eax
0x14000282a  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x140002831  jnz     short loc_140002852
0x140002833  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x14000283a  test    rax, rax
0x14000283d  jz      short loc_140002848
0x14000283f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002844  test    al, al
0x140002846  jmp     short loc_140002850
0x140002848  call    cs:__imp_IsDebuggerPresent
0x14000284e  test    eax, eax
0x140002850  jz      short loc_140002859
0x140002852  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x140002857  jz      short loc_14000287F
0x140002859  mov     rax, cs:g_pfnResultLoggingCallback
0x140002860  test    rax, rax
0x140002863  jz      short loc_1400028D8
0x140002865  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x14000286c  jnz     short loc_1400028D8
0x14000286e  xor     r8d, r8d
0x140002871  xor     edx, edx
0x140002873  lea     rcx, [rsp+14F0h+var_14D0]
0x140002878  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000287d  jmp     short loc_1400028D8
0x14000287f  mov     ebx, 800h
0x140002884  mov     rax, cs:g_pfnResultLoggingCallback
0x14000288b  test    rax, rax
0x14000288e  jz      short loc_1400028AD
0x140002890  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x140002897  jnz     short loc_1400028AD
0x140002899  mov     r8d, ebx
0x14000289c  lea     rdx, [rbp+13F0h+OutputString]
0x1400028a3  lea     rcx, [rsp+14F0h+var_14D0]
0x1400028a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400028ad  cmp     [rbp+13F0h+OutputString], r13w
0x1400028b5  jnz     short loc_1400028CB
0x1400028b7  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x1400028bc  mov     rdx, rbx; unsigned __int16 *
0x1400028bf  lea     rcx, [rbp+13F0h+OutputString]; this
0x1400028c6  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1400028cb  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x1400028d2  call    cs:__imp_OutputDebugStringW
0x1400028d8  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x1400028dd  jnz     short loc_1400028E8
0x1400028df  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x1400028e6  jz      short loc_1400028FA
0x1400028e8  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1400028ef  test    rax, rax
0x1400028f2  jz      short loc_1400028FA
0x1400028f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400028f9  nop
0x1400028fa  lea     rcx, [rsp+14F0h+var_14D0]; this
0x1400028ff  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
