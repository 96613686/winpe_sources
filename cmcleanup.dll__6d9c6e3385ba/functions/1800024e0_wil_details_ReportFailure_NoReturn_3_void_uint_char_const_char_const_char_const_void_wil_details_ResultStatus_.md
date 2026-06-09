# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x1800024e0`
- end: `0x180002749`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `617`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, __int64, __int64, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18000228c`

## callees

- `0x1800020c4`
- `0x1800024e0`
- `0x180004314`
- `0x180004b64`
- `0x180005550`
- `0x180007740`
- `0x180008080`
- `0x180009010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002582`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002582`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180002716`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180002716`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000268c`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000268c`

## string_xrefs

- `0x18000258c`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<3>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
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
0x1800024e0  mov     [rsp-8+arg_10], rbx
0x1800024e5  mov     [rsp-8+arg_18], rsi
0x1800024ea  push    rbp
0x1800024eb  push    rdi
0x1800024ec  push    r12
0x1800024ee  push    r14
0x1800024f0  push    r15
0x1800024f2  lea     rbp, [rsp-13C0h]
0x1800024fa  mov     eax, 14C0h
0x1800024ff  call    _alloca_probe
0x180002504  sub     rsp, rax
0x180002507  mov     r14d, edx
0x18000250a  mov     r15, rcx
0x18000250d  mov     rsi, [rbp+13E0h+arg_28]
0x180002514  xor     edx, edx; Val
0x180002516  mov     r8d, 98h; Size
0x18000251c  lea     rcx, [rsp+14E0h+var_14C0]; void *
0x180002521  call    memset_0
0x180002526  nop
0x180002527  xor     r12d, r12d
0x18000252a  mov     [rbp+13E0h+OutputString], r12w
0x180002532  mov     [rbp+13E0h+var_1420], r12b
0x180002536  mov     rbx, [rbp+13E0h+arg_30]
0x18000253d  mov     ecx, [rbx]; this
0x18000253f  mov     [rsp+14E0h+var_14B8], ecx
0x180002543  mov     eax, [rbx+4]
0x180002546  mov     [rsp+14E0h+var_14B4], eax
0x18000254a  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000254f  mov     edi, eax
0x180002551  mov     dword ptr [rsp+14E0h+var_14C0], 3
0x180002559  mov     ecx, r12d
0x18000255c  lea     eax, [r12+8]
0x180002561  cmp     dword ptr [rbx+8], 1
0x180002565  cmovz   ecx, eax
0x180002568  mov     dword ptr [rsp+14E0h+var_14C0+4], ecx
0x18000256c  lea     ecx, [rax-7]
0x18000256f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180002577  inc     ecx
0x180002579  mov     [rsp+14E0h+var_14B0], ecx
0x18000257d  mov     [rsp+14E0h+var_14A8], r12
0x180002582  call    cs:__imp_GetCurrentThreadId
0x180002588  mov     [rsp+14E0h+var_14A0], eax
0x18000258c  lea     rax, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180002593  mov     [rsp+14E0h+var_1488], rax
0x180002598  mov     [rsp+14E0h+var_1480], r14d
0x18000259d  mov     [rsp+14E0h+var_147C], edi
0x1800025a1  mov     [rsp+14E0h+var_1498], r12
0x1800025a6  mov     [rsp+14E0h+var_1490], r12
0x1800025ab  mov     [rbp+13E0h+var_1438], rsi
0x1800025af  mov     [rbp+13E0h+var_1430], r15
0x1800025b3  mov     [rsp+14E0h+var_1478], r12
0x1800025b8  xorps   xmm0, xmm0
0x1800025bb  xor     eax, eax
0x1800025bd  movups  [rbp+13E0h+var_1458], xmm0
0x1800025c1  mov     [rbp+13E0h+var_1448], rax
0x1800025c5  xorps   xmm1, xmm1
0x1800025c8  movups  [rsp+14E0h+var_1470], xmm1
0x1800025cd  mov     [rbp+13E0h+var_1460], rax
0x1800025d1  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800025d8  test    rax, rax
0x1800025db  jz      short loc_1800025E8
0x1800025dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800025e2  mov     [rbp+13E0h+var_1440], rax
0x1800025e6  jmp     short loc_1800025EC
0x1800025e8  mov     [rbp+13E0h+var_1440], r12
0x1800025ec  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800025f3  test    rax, rax
0x1800025f6  jz      short loc_180002602
0x1800025f8  lea     rcx, [rsp+14E0h+var_14C0]
0x1800025fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002602  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180002609  test    rax, rax
0x18000260c  jz      short loc_180002622
0x18000260e  mov     r8d, 400h
0x180002614  lea     rdx, [rbp+13E0h+var_1420]
0x180002618  lea     rcx, [rsp+14E0h+var_14C0]
0x18000261d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002622  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002629  test    rax, rax
0x18000262c  jz      short loc_180002638
0x18000262e  lea     rcx, [rsp+14E0h+var_14C0]
0x180002633  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002638  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000263f  test    rax, rax
0x180002642  jz      short loc_180002655
0x180002644  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x180002649  jnz     short loc_180002655
0x18000264b  lea     rcx, [rsp+14E0h+var_14C0]
0x180002650  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002655  cmp     [rsp+14E0h+var_14B8], r12d
0x18000265a  jl      short loc_18000266E
0x18000265c  mov     ecx, 8000FFFFh; this
0x180002661  mov     [rsp+14E0h+var_14B8], ecx
0x180002665  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000266a  mov     [rsp+14E0h+var_14B4], eax
0x18000266e  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180002675  jnz     short loc_180002696
0x180002677  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000267e  test    rax, rax
0x180002681  jz      short loc_18000268C
0x180002683  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002688  test    al, al
0x18000268a  jmp     short loc_180002694
0x18000268c  call    cs:__imp_IsDebuggerPresent
0x180002692  test    eax, eax
0x180002694  jz      short loc_18000269D
0x180002696  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x18000269b  jz      short loc_1800026C3
0x18000269d  mov     rax, cs:g_pfnResultLoggingCallback
0x1800026a4  test    rax, rax
0x1800026a7  jz      short loc_18000271C
0x1800026a9  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800026b0  jnz     short loc_18000271C
0x1800026b2  xor     r8d, r8d
0x1800026b5  xor     edx, edx
0x1800026b7  lea     rcx, [rsp+14E0h+var_14C0]
0x1800026bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800026c1  jmp     short loc_18000271C
0x1800026c3  mov     ebx, 800h
0x1800026c8  mov     rax, cs:g_pfnResultLoggingCallback
0x1800026cf  test    rax, rax
0x1800026d2  jz      short loc_1800026F1
0x1800026d4  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800026db  jnz     short loc_1800026F1
0x1800026dd  mov     r8d, ebx
0x1800026e0  lea     rdx, [rbp+13E0h+OutputString]
0x1800026e7  lea     rcx, [rsp+14E0h+var_14C0]
0x1800026ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800026f1  cmp     [rbp+13E0h+OutputString], r12w
0x1800026f9  jnz     short loc_18000270F
0x1800026fb  lea     r8, [rsp+14E0h+var_14C0]; unsigned __int64
0x180002700  mov     rdx, rbx; unsigned __int16 *
0x180002703  lea     rcx, [rbp+13E0h+OutputString]; this
0x18000270a  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000270f  lea     rcx, [rbp+13E0h+OutputString]; lpOutputString
0x180002716  call    cs:__imp_OutputDebugStringW
0x18000271c  test    byte ptr [rsp+14E0h+var_14C0+4], 4
0x180002721  jnz     short loc_18000272C
0x180002723  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x18000272a  jz      short loc_18000273E
0x18000272c  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180002733  test    rax, rax
0x180002736  jz      short loc_18000273E
0x180002738  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000273d  nop
0x18000273e  lea     rcx, [rsp+14E0h+var_14C0]; this
0x180002743  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
