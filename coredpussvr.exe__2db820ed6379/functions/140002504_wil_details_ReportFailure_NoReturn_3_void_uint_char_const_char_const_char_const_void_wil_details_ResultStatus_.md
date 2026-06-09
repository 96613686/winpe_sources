# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x140002504`
- end: `0x14000277f`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `635`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1400022b0`

## callees

- `0x14000215c`
- `0x140002504`
- `0x1400035e4`
- `0x140003de8`
- `0x140004790`
- `0x1400055fc`
- `0x140009030`
- `0x14000a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400025a6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400025a6`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140002746`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140002746`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1400026b6`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1400026b6`

## string_xrefs

- `0x1400025b6`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x140002504  mov     [rsp-8+arg_10], rbx
0x140002509  mov     [rsp-8+arg_18], rsi
0x14000250e  push    rbp
0x14000250f  push    rdi
0x140002510  push    r12
0x140002512  push    r14
0x140002514  push    r15
0x140002516  lea     rbp, [rsp-13C0h]
0x14000251e  mov     eax, 14C0h
0x140002523  call    _alloca_probe
0x140002528  sub     rsp, rax
0x14000252b  mov     r14d, edx
0x14000252e  mov     r15, rcx
0x140002531  mov     rsi, [rbp+13E0h+arg_28]
0x140002538  xor     edx, edx; Val
0x14000253a  mov     r8d, 98h; Size
0x140002540  lea     rcx, [rsp+14E0h+var_14C0]; void *
0x140002545  call    memset_0
0x14000254a  nop
0x14000254b  xor     r12d, r12d
0x14000254e  mov     [rbp+13E0h+OutputString], r12w
0x140002556  mov     [rbp+13E0h+var_1420], r12b
0x14000255a  mov     rbx, [rbp+13E0h+arg_30]
0x140002561  mov     ecx, [rbx]; this
0x140002563  mov     [rsp+14E0h+var_14B8], ecx
0x140002567  mov     eax, [rbx+4]
0x14000256a  mov     [rsp+14E0h+var_14B4], eax
0x14000256e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x140002573  mov     edi, eax
0x140002575  mov     dword ptr [rsp+14E0h+var_14C0], 3
0x14000257d  mov     ecx, r12d
0x140002580  lea     eax, [r12+8]
0x140002585  cmp     dword ptr [rbx+8], 1
0x140002589  cmovz   ecx, eax
0x14000258c  mov     dword ptr [rsp+14E0h+var_14C0+4], ecx
0x140002590  lea     ecx, [rax-7]
0x140002593  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x14000259b  inc     ecx
0x14000259d  mov     [rsp+14E0h+var_14B0], ecx
0x1400025a1  mov     [rsp+14E0h+var_14A8], r12
0x1400025a6  call    cs:__imp_GetCurrentThreadId
0x1400025ad  nop     dword ptr [rax+rax+00h]
0x1400025b2  mov     [rsp+14E0h+var_14A0], eax
0x1400025b6  lea     rax, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1400025bd  mov     [rsp+14E0h+var_1488], rax
0x1400025c2  mov     [rsp+14E0h+var_1480], r14d
0x1400025c7  mov     [rsp+14E0h+var_147C], edi
0x1400025cb  mov     [rsp+14E0h+var_1498], r12
0x1400025d0  mov     [rsp+14E0h+var_1490], r12
0x1400025d5  mov     [rbp+13E0h+var_1438], rsi
0x1400025d9  mov     [rbp+13E0h+var_1430], r15
0x1400025dd  mov     [rsp+14E0h+var_1478], r12
0x1400025e2  xorps   xmm0, xmm0
0x1400025e5  xor     eax, eax
0x1400025e7  movups  [rbp+13E0h+var_1458], xmm0
0x1400025eb  mov     [rbp+13E0h+var_1448], rax
0x1400025ef  xorps   xmm1, xmm1
0x1400025f2  movups  [rsp+14E0h+var_1470], xmm1
0x1400025f7  mov     [rbp+13E0h+var_1460], rax
0x1400025fb  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140002602  test    rax, rax
0x140002605  jz      short loc_140002612
0x140002607  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000260c  mov     [rbp+13E0h+var_1440], rax
0x140002610  jmp     short loc_140002616
0x140002612  mov     [rbp+13E0h+var_1440], r12
0x140002616  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x14000261d  test    rax, rax
0x140002620  jz      short loc_14000262C
0x140002622  lea     rcx, [rsp+14E0h+var_14C0]
0x140002627  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000262c  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140002633  test    rax, rax
0x140002636  jz      short loc_14000264C
0x140002638  mov     r8d, 400h
0x14000263e  lea     rdx, [rbp+13E0h+var_1420]
0x140002642  lea     rcx, [rsp+14E0h+var_14C0]
0x140002647  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000264c  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140002653  test    rax, rax
0x140002656  jz      short loc_140002662
0x140002658  lea     rcx, [rsp+14E0h+var_14C0]
0x14000265d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002662  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140002669  test    rax, rax
0x14000266c  jz      short loc_14000267F
0x14000266e  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x140002673  jnz     short loc_14000267F
0x140002675  lea     rcx, [rsp+14E0h+var_14C0]
0x14000267a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000267f  cmp     [rsp+14E0h+var_14B8], r12d
0x140002684  jl      short loc_140002698
0x140002686  mov     ecx, 8000FFFFh; this
0x14000268b  mov     [rsp+14E0h+var_14B8], ecx
0x14000268f  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140002694  mov     [rsp+14E0h+var_14B4], eax
0x140002698  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x14000269f  jnz     short loc_1400026C6
0x1400026a1  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1400026a8  test    rax, rax
0x1400026ab  jz      short loc_1400026B6
0x1400026ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400026b2  test    al, al
0x1400026b4  jmp     short loc_1400026C4
0x1400026b6  call    cs:__imp_IsDebuggerPresent
0x1400026bd  nop     dword ptr [rax+rax+00h]
0x1400026c2  test    eax, eax
0x1400026c4  jz      short loc_1400026CD
0x1400026c6  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x1400026cb  jz      short loc_1400026F3
0x1400026cd  mov     rax, cs:g_pfnResultLoggingCallback
0x1400026d4  test    rax, rax
0x1400026d7  jz      short loc_140002752
0x1400026d9  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1400026e0  jnz     short loc_140002752
0x1400026e2  xor     r8d, r8d
0x1400026e5  xor     edx, edx
0x1400026e7  lea     rcx, [rsp+14E0h+var_14C0]
0x1400026ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400026f1  jmp     short loc_140002752
0x1400026f3  mov     ebx, 800h
0x1400026f8  mov     rax, cs:g_pfnResultLoggingCallback
0x1400026ff  test    rax, rax
0x140002702  jz      short loc_140002721
0x140002704  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x14000270b  jnz     short loc_140002721
0x14000270d  mov     r8d, ebx
0x140002710  lea     rdx, [rbp+13E0h+OutputString]
0x140002717  lea     rcx, [rsp+14E0h+var_14C0]
0x14000271c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002721  cmp     [rbp+13E0h+OutputString], r12w
0x140002729  jnz     short loc_14000273F
0x14000272b  lea     r8, [rsp+14E0h+var_14C0]; unsigned __int64
0x140002730  mov     rdx, rbx; unsigned __int16 *
0x140002733  lea     rcx, [rbp+13E0h+OutputString]; this
0x14000273a  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x14000273f  lea     rcx, [rbp+13E0h+OutputString]; lpOutputString
0x140002746  call    cs:__imp_OutputDebugStringW
0x14000274d  nop     dword ptr [rax+rax+00h]
0x140002752  test    byte ptr [rsp+14E0h+var_14C0+4], 4
0x140002757  jnz     short loc_140002762
0x140002759  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x140002760  jz      short loc_140002774
0x140002762  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140002769  test    rax, rax
0x14000276c  jz      short loc_140002774
0x14000276e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002773  nop
0x140002774  lea     rcx, [rsp+14E0h+var_14C0]; this
0x140002779  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
