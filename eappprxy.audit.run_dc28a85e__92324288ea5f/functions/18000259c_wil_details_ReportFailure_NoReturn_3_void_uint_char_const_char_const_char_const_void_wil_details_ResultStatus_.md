# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions)

- ea: `0x18000259c`
- end: `0x180002817`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@@Z`
- size: `635`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180002348`

## callees

- `0x180002106`
- `0x18000259c`
- `0x1800037d4`
- `0x180003fd8`
- `0x1800049f0`
- `0x180005c9c`
- `0x18000dec0`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000263e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000263e`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800027de`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800027de`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000274e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000274e`

## string_xrefs

- `0x18000264e`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
      wil::GetFailureLogString((wil *)OutputString, (wchar_t *)0x800, (unsigned __int64)&v16, v14);
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
0x18000259c  mov     [rsp-8+arg_10], rbx
0x1800025a1  mov     [rsp-8+arg_18], rsi
0x1800025a6  push    rbp
0x1800025a7  push    rdi
0x1800025a8  push    r12
0x1800025aa  push    r14
0x1800025ac  push    r15
0x1800025ae  lea     rbp, [rsp-13C0h]
0x1800025b6  mov     eax, 14C0h
0x1800025bb  call    _alloca_probe
0x1800025c0  sub     rsp, rax
0x1800025c3  mov     r14d, edx
0x1800025c6  mov     r15, rcx
0x1800025c9  mov     rsi, [rbp+13E0h+arg_28]
0x1800025d0  xor     edx, edx; Val
0x1800025d2  mov     r8d, 98h; Size
0x1800025d8  lea     rcx, [rsp+14E0h+var_14C0]; void *
0x1800025dd  call    memset_0
0x1800025e2  nop
0x1800025e3  xor     r12d, r12d
0x1800025e6  mov     [rbp+13E0h+OutputString], r12w
0x1800025ee  mov     [rbp+13E0h+var_1420], r12b
0x1800025f2  mov     rbx, [rbp+13E0h+arg_30]
0x1800025f9  mov     ecx, [rbx]; this
0x1800025fb  mov     [rsp+14E0h+var_14B8], ecx
0x1800025ff  mov     eax, [rbx+4]
0x180002602  mov     [rsp+14E0h+var_14B4], eax
0x180002606  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000260b  mov     edi, eax
0x18000260d  mov     dword ptr [rsp+14E0h+var_14C0], 3
0x180002615  mov     ecx, r12d
0x180002618  lea     eax, [r12+8]
0x18000261d  cmp     dword ptr [rbx+8], 1
0x180002621  cmovz   ecx, eax
0x180002624  mov     dword ptr [rsp+14E0h+var_14C0+4], ecx
0x180002628  lea     ecx, [rax-7]
0x18000262b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180002633  inc     ecx
0x180002635  mov     [rsp+14E0h+var_14B0], ecx
0x180002639  mov     [rsp+14E0h+var_14A8], r12
0x18000263e  call    cs:__imp_GetCurrentThreadId
0x180002645  nop     dword ptr [rax+rax+00h]
0x18000264a  mov     [rsp+14E0h+var_14A0], eax
0x18000264e  lea     rax, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180002655  mov     [rsp+14E0h+var_1488], rax
0x18000265a  mov     [rsp+14E0h+var_1480], r14d
0x18000265f  mov     [rsp+14E0h+var_147C], edi
0x180002663  mov     [rsp+14E0h+var_1498], r12
0x180002668  mov     [rsp+14E0h+var_1490], r12
0x18000266d  mov     [rbp+13E0h+var_1438], rsi
0x180002671  mov     [rbp+13E0h+var_1430], r15
0x180002675  mov     [rsp+14E0h+var_1478], r12
0x18000267a  xorps   xmm0, xmm0
0x18000267d  xor     eax, eax
0x18000267f  movups  [rbp+13E0h+var_1458], xmm0
0x180002683  mov     [rbp+13E0h+var_1448], rax
0x180002687  xorps   xmm1, xmm1
0x18000268a  movups  [rsp+14E0h+var_1470], xmm1
0x18000268f  mov     [rbp+13E0h+var_1460], rax
0x180002693  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000269a  test    rax, rax
0x18000269d  jz      short loc_1800026AA
0x18000269f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800026a4  mov     [rbp+13E0h+var_1440], rax
0x1800026a8  jmp     short loc_1800026AE
0x1800026aa  mov     [rbp+13E0h+var_1440], r12
0x1800026ae  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800026b5  test    rax, rax
0x1800026b8  jz      short loc_1800026C4
0x1800026ba  lea     rcx, [rsp+14E0h+var_14C0]
0x1800026bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800026c4  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800026cb  test    rax, rax
0x1800026ce  jz      short loc_1800026E4
0x1800026d0  mov     r8d, 400h
0x1800026d6  lea     rdx, [rbp+13E0h+var_1420]
0x1800026da  lea     rcx, [rsp+14E0h+var_14C0]
0x1800026df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800026e4  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800026eb  test    rax, rax
0x1800026ee  jz      short loc_1800026FA
0x1800026f0  lea     rcx, [rsp+14E0h+var_14C0]
0x1800026f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800026fa  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002701  test    rax, rax
0x180002704  jz      short loc_180002717
0x180002706  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x18000270b  jnz     short loc_180002717
0x18000270d  lea     rcx, [rsp+14E0h+var_14C0]
0x180002712  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002717  cmp     [rsp+14E0h+var_14B8], r12d
0x18000271c  jl      short loc_180002730
0x18000271e  mov     ecx, 8000FFFFh; this
0x180002723  mov     [rsp+14E0h+var_14B8], ecx
0x180002727  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000272c  mov     [rsp+14E0h+var_14B4], eax
0x180002730  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180002737  jnz     short loc_18000275E
0x180002739  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180002740  test    rax, rax
0x180002743  jz      short loc_18000274E
0x180002745  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000274a  test    al, al
0x18000274c  jmp     short loc_18000275C
0x18000274e  call    cs:__imp_IsDebuggerPresent
0x180002755  nop     dword ptr [rax+rax+00h]
0x18000275a  test    eax, eax
0x18000275c  jz      short loc_180002765
0x18000275e  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x180002763  jz      short loc_18000278B
0x180002765  mov     rax, cs:g_pfnResultLoggingCallback
0x18000276c  test    rax, rax
0x18000276f  jz      short loc_1800027EA
0x180002771  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180002778  jnz     short loc_1800027EA
0x18000277a  xor     r8d, r8d
0x18000277d  xor     edx, edx
0x18000277f  lea     rcx, [rsp+14E0h+var_14C0]
0x180002784  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002789  jmp     short loc_1800027EA
0x18000278b  mov     ebx, 800h
0x180002790  mov     rax, cs:g_pfnResultLoggingCallback
0x180002797  test    rax, rax
0x18000279a  jz      short loc_1800027B9
0x18000279c  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800027a3  jnz     short loc_1800027B9
0x1800027a5  mov     r8d, ebx
0x1800027a8  lea     rdx, [rbp+13E0h+OutputString]
0x1800027af  lea     rcx, [rsp+14E0h+var_14C0]
0x1800027b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800027b9  cmp     [rbp+13E0h+OutputString], r12w
0x1800027c1  jnz     short loc_1800027D7
0x1800027c3  lea     r8, [rsp+14E0h+var_14C0]; unsigned __int64
0x1800027c8  mov     rdx, rbx; wchar_t *
0x1800027cb  lea     rcx, [rbp+13E0h+OutputString]; this
0x1800027d2  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x1800027d7  lea     rcx, [rbp+13E0h+OutputString]; lpOutputString
0x1800027de  call    cs:__imp_OutputDebugStringW
0x1800027e5  nop     dword ptr [rax+rax+00h]
0x1800027ea  test    byte ptr [rsp+14E0h+var_14C0+4], 4
0x1800027ef  jnz     short loc_1800027FA
0x1800027f1  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x1800027f8  jz      short loc_18000280C
0x1800027fa  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180002801  test    rax, rax
0x180002804  jz      short loc_18000280C
0x180002806  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000280b  nop
0x18000280c  lea     rcx, [rsp+14E0h+var_14C0]; this
0x180002811  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
