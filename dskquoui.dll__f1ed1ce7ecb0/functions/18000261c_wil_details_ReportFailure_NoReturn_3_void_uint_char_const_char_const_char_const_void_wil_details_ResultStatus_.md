# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x18000261c`
- end: `0x180002885`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `617`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1800023d0`

## callees

- `0x1800022b4`
- `0x18000261c`
- `0x1800039b4`
- `0x180004150`
- `0x180004870`
- `0x180005810`
- `0x18001cde0`
- `0x18001f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800026be`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800026be`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800027c8`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800027c8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180002852`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180002852`

## string_xrefs

- `0x1800026c8`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x18000261c  mov     [rsp-8+arg_10], rbx
0x180002621  mov     [rsp-8+arg_18], rsi
0x180002626  push    rbp
0x180002627  push    rdi
0x180002628  push    r12
0x18000262a  push    r14
0x18000262c  push    r15
0x18000262e  lea     rbp, [rsp-13C0h]
0x180002636  mov     eax, 14C0h
0x18000263b  call    _alloca_probe
0x180002640  sub     rsp, rax
0x180002643  mov     r14d, edx
0x180002646  mov     r15, rcx
0x180002649  mov     rsi, [rbp+13E0h+arg_28]
0x180002650  xor     edx, edx; Val
0x180002652  mov     r8d, 98h; Size
0x180002658  lea     rcx, [rsp+14E0h+var_14C0]; void *
0x18000265d  call    memset_0
0x180002662  nop
0x180002663  xor     r12d, r12d
0x180002666  mov     [rbp+13E0h+OutputString], r12w
0x18000266e  mov     [rbp+13E0h+var_1420], r12b
0x180002672  mov     rbx, [rbp+13E0h+arg_30]
0x180002679  mov     ecx, [rbx]; this
0x18000267b  mov     [rsp+14E0h+var_14B8], ecx
0x18000267f  mov     eax, [rbx+4]
0x180002682  mov     [rsp+14E0h+var_14B4], eax
0x180002686  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000268b  mov     edi, eax
0x18000268d  mov     dword ptr [rsp+14E0h+var_14C0], 3
0x180002695  mov     ecx, r12d
0x180002698  lea     eax, [r12+8]
0x18000269d  cmp     dword ptr [rbx+8], 1
0x1800026a1  cmovz   ecx, eax
0x1800026a4  mov     dword ptr [rsp+14E0h+var_14C0+4], ecx
0x1800026a8  lea     ecx, [rax-7]
0x1800026ab  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800026b3  inc     ecx
0x1800026b5  mov     [rsp+14E0h+var_14B0], ecx
0x1800026b9  mov     [rsp+14E0h+var_14A8], r12
0x1800026be  call    cs:__imp_GetCurrentThreadId
0x1800026c4  mov     [rsp+14E0h+var_14A0], eax
0x1800026c8  lea     rax, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800026cf  mov     [rsp+14E0h+var_1488], rax
0x1800026d4  mov     [rsp+14E0h+var_1480], r14d
0x1800026d9  mov     [rsp+14E0h+var_147C], edi
0x1800026dd  mov     [rsp+14E0h+var_1498], r12
0x1800026e2  mov     [rsp+14E0h+var_1490], r12
0x1800026e7  mov     [rbp+13E0h+var_1438], rsi
0x1800026eb  mov     [rbp+13E0h+var_1430], r15
0x1800026ef  mov     [rsp+14E0h+var_1478], r12
0x1800026f4  xorps   xmm0, xmm0
0x1800026f7  xor     eax, eax
0x1800026f9  movups  [rbp+13E0h+var_1458], xmm0
0x1800026fd  mov     [rbp+13E0h+var_1448], rax
0x180002701  xorps   xmm1, xmm1
0x180002704  movups  [rsp+14E0h+var_1470], xmm1
0x180002709  mov     [rbp+13E0h+var_1460], rax
0x18000270d  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180002714  test    rax, rax
0x180002717  jz      short loc_180002724
0x180002719  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000271e  mov     [rbp+13E0h+var_1440], rax
0x180002722  jmp     short loc_180002728
0x180002724  mov     [rbp+13E0h+var_1440], r12
0x180002728  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000272f  test    rax, rax
0x180002732  jz      short loc_18000273E
0x180002734  lea     rcx, [rsp+14E0h+var_14C0]
0x180002739  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000273e  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180002745  test    rax, rax
0x180002748  jz      short loc_18000275E
0x18000274a  mov     r8d, 400h
0x180002750  lea     rdx, [rbp+13E0h+var_1420]
0x180002754  lea     rcx, [rsp+14E0h+var_14C0]
0x180002759  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000275e  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002765  test    rax, rax
0x180002768  jz      short loc_180002774
0x18000276a  lea     rcx, [rsp+14E0h+var_14C0]
0x18000276f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002774  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000277b  test    rax, rax
0x18000277e  jz      short loc_180002791
0x180002780  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x180002785  jnz     short loc_180002791
0x180002787  lea     rcx, [rsp+14E0h+var_14C0]
0x18000278c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002791  cmp     [rsp+14E0h+var_14B8], r12d
0x180002796  jl      short loc_1800027AA
0x180002798  mov     ecx, 8000FFFFh; this
0x18000279d  mov     [rsp+14E0h+var_14B8], ecx
0x1800027a1  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800027a6  mov     [rsp+14E0h+var_14B4], eax
0x1800027aa  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x1800027b1  jnz     short loc_1800027D2
0x1800027b3  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800027ba  test    rax, rax
0x1800027bd  jz      short loc_1800027C8
0x1800027bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800027c4  test    al, al
0x1800027c6  jmp     short loc_1800027D0
0x1800027c8  call    cs:__imp_IsDebuggerPresent
0x1800027ce  test    eax, eax
0x1800027d0  jz      short loc_1800027D9
0x1800027d2  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x1800027d7  jz      short loc_1800027FF
0x1800027d9  mov     rax, cs:g_pfnResultLoggingCallback
0x1800027e0  test    rax, rax
0x1800027e3  jz      short loc_180002858
0x1800027e5  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800027ec  jnz     short loc_180002858
0x1800027ee  xor     r8d, r8d
0x1800027f1  xor     edx, edx
0x1800027f3  lea     rcx, [rsp+14E0h+var_14C0]
0x1800027f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800027fd  jmp     short loc_180002858
0x1800027ff  mov     ebx, 800h
0x180002804  mov     rax, cs:g_pfnResultLoggingCallback
0x18000280b  test    rax, rax
0x18000280e  jz      short loc_18000282D
0x180002810  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180002817  jnz     short loc_18000282D
0x180002819  mov     r8d, ebx
0x18000281c  lea     rdx, [rbp+13E0h+OutputString]
0x180002823  lea     rcx, [rsp+14E0h+var_14C0]
0x180002828  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000282d  cmp     [rbp+13E0h+OutputString], r12w
0x180002835  jnz     short loc_18000284B
0x180002837  lea     r8, [rsp+14E0h+var_14C0]; unsigned __int64
0x18000283c  mov     rdx, rbx; unsigned __int16 *
0x18000283f  lea     rcx, [rbp+13E0h+OutputString]; this
0x180002846  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000284b  lea     rcx, [rbp+13E0h+OutputString]; lpOutputString
0x180002852  call    cs:__imp_OutputDebugStringW
0x180002858  test    byte ptr [rsp+14E0h+var_14C0+4], 4
0x18000285d  jnz     short loc_180002868
0x18000285f  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180002866  jz      short loc_18000287A
0x180002868  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000286f  test    rax, rax
0x180002872  jz      short loc_18000287A
0x180002874  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002879  nop
0x18000287a  lea     rcx, [rsp+14E0h+var_14C0]; this
0x18000287f  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
