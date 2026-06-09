# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180006228`
- end: `0x180006491`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `617`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180006004`

## callees

- `0x1800054bc`
- `0x180006228`
- `0x180009a34`
- `0x18000a228`
- `0x18000ac20`
- `0x18000c3f0`
- `0x1800eeda0`
- `0x1800f8010`

## import_xrefs

- `KERNEL32!OutputDebugStringW` at `0x18000645e`
- `KERNEL32!OutputDebugStringW` at `0x18000645e`
- `KERNEL32!IsDebuggerPresent` at `0x1800063d4`
- `KERNEL32!IsDebuggerPresent` at `0x1800063d4`
- `KERNEL32!GetCurrentThreadId` at `0x1800062ca`
- `KERNEL32!GetCurrentThreadId` at `0x1800062ca`

## string_xrefs

- `0x1800062d4`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x180006228  mov     [rsp-8+arg_10], rbx
0x18000622d  mov     [rsp-8+arg_18], rsi
0x180006232  push    rbp
0x180006233  push    rdi
0x180006234  push    r12
0x180006236  push    r14
0x180006238  push    r15
0x18000623a  lea     rbp, [rsp-13C0h]
0x180006242  mov     eax, 14C0h
0x180006247  call    _alloca_probe
0x18000624c  sub     rsp, rax
0x18000624f  mov     r14d, edx
0x180006252  mov     r15, rcx
0x180006255  mov     rsi, [rbp+13E0h+arg_28]
0x18000625c  xor     edx, edx; Val
0x18000625e  mov     r8d, 98h; Size
0x180006264  lea     rcx, [rsp+14E0h+var_14C0]; void *
0x180006269  call    memset_0
0x18000626e  nop
0x18000626f  xor     r12d, r12d
0x180006272  mov     [rbp+13E0h+OutputString], r12w
0x18000627a  mov     [rbp+13E0h+var_1420], r12b
0x18000627e  mov     rbx, [rbp+13E0h+arg_30]
0x180006285  mov     ecx, [rbx]; this
0x180006287  mov     [rsp+14E0h+var_14B8], ecx
0x18000628b  mov     eax, [rbx+4]
0x18000628e  mov     [rsp+14E0h+var_14B4], eax
0x180006292  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180006297  mov     edi, eax
0x180006299  mov     dword ptr [rsp+14E0h+var_14C0], 3
0x1800062a1  mov     ecx, r12d
0x1800062a4  lea     eax, [r12+8]
0x1800062a9  cmp     dword ptr [rbx+8], 1
0x1800062ad  cmovz   ecx, eax
0x1800062b0  mov     dword ptr [rsp+14E0h+var_14C0+4], ecx
0x1800062b4  lea     ecx, [rax-7]
0x1800062b7  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800062bf  inc     ecx
0x1800062c1  mov     [rsp+14E0h+var_14B0], ecx
0x1800062c5  mov     [rsp+14E0h+var_14A8], r12
0x1800062ca  call    cs:__imp_GetCurrentThreadId
0x1800062d0  mov     [rsp+14E0h+var_14A0], eax
0x1800062d4  lea     rax, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800062db  mov     [rsp+14E0h+var_1488], rax
0x1800062e0  mov     [rsp+14E0h+var_1480], r14d
0x1800062e5  mov     [rsp+14E0h+var_147C], edi
0x1800062e9  mov     [rsp+14E0h+var_1498], r12
0x1800062ee  mov     [rsp+14E0h+var_1490], r12
0x1800062f3  mov     [rbp+13E0h+var_1438], rsi
0x1800062f7  mov     [rbp+13E0h+var_1430], r15
0x1800062fb  mov     [rsp+14E0h+var_1478], r12
0x180006300  xorps   xmm0, xmm0
0x180006303  xor     eax, eax
0x180006305  movups  [rbp+13E0h+var_1458], xmm0
0x180006309  mov     [rbp+13E0h+var_1448], rax
0x18000630d  xorps   xmm1, xmm1
0x180006310  movups  [rsp+14E0h+var_1470], xmm1
0x180006315  mov     [rbp+13E0h+var_1460], rax
0x180006319  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180006320  test    rax, rax
0x180006323  jz      short loc_180006330
0x180006325  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000632a  mov     [rbp+13E0h+var_1440], rax
0x18000632e  jmp     short loc_180006334
0x180006330  mov     [rbp+13E0h+var_1440], r12
0x180006334  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000633b  test    rax, rax
0x18000633e  jz      short loc_18000634A
0x180006340  lea     rcx, [rsp+14E0h+var_14C0]
0x180006345  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000634a  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180006351  test    rax, rax
0x180006354  jz      short loc_18000636A
0x180006356  mov     r8d, 400h
0x18000635c  lea     rdx, [rbp+13E0h+var_1420]
0x180006360  lea     rcx, [rsp+14E0h+var_14C0]
0x180006365  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000636a  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180006371  test    rax, rax
0x180006374  jz      short loc_180006380
0x180006376  lea     rcx, [rsp+14E0h+var_14C0]
0x18000637b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006380  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180006387  test    rax, rax
0x18000638a  jz      short loc_18000639D
0x18000638c  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x180006391  jnz     short loc_18000639D
0x180006393  lea     rcx, [rsp+14E0h+var_14C0]
0x180006398  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000639d  cmp     [rsp+14E0h+var_14B8], r12d
0x1800063a2  jl      short loc_1800063B6
0x1800063a4  mov     ecx, 8000FFFFh; this
0x1800063a9  mov     [rsp+14E0h+var_14B8], ecx
0x1800063ad  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800063b2  mov     [rsp+14E0h+var_14B4], eax
0x1800063b6  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x1800063bd  jnz     short loc_1800063DE
0x1800063bf  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800063c6  test    rax, rax
0x1800063c9  jz      short loc_1800063D4
0x1800063cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800063d0  test    al, al
0x1800063d2  jmp     short loc_1800063DC
0x1800063d4  call    cs:__imp_IsDebuggerPresent
0x1800063da  test    eax, eax
0x1800063dc  jz      short loc_1800063E5
0x1800063de  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x1800063e3  jz      short loc_18000640B
0x1800063e5  mov     rax, cs:g_pfnResultLoggingCallback
0x1800063ec  test    rax, rax
0x1800063ef  jz      short loc_180006464
0x1800063f1  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800063f8  jnz     short loc_180006464
0x1800063fa  xor     r8d, r8d
0x1800063fd  xor     edx, edx
0x1800063ff  lea     rcx, [rsp+14E0h+var_14C0]
0x180006404  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006409  jmp     short loc_180006464
0x18000640b  mov     ebx, 800h
0x180006410  mov     rax, cs:g_pfnResultLoggingCallback
0x180006417  test    rax, rax
0x18000641a  jz      short loc_180006439
0x18000641c  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180006423  jnz     short loc_180006439
0x180006425  mov     r8d, ebx
0x180006428  lea     rdx, [rbp+13E0h+OutputString]
0x18000642f  lea     rcx, [rsp+14E0h+var_14C0]
0x180006434  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006439  cmp     [rbp+13E0h+OutputString], r12w
0x180006441  jnz     short loc_180006457
0x180006443  lea     r8, [rsp+14E0h+var_14C0]; unsigned __int64
0x180006448  mov     rdx, rbx; unsigned __int16 *
0x18000644b  lea     rcx, [rbp+13E0h+OutputString]; this
0x180006452  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180006457  lea     rcx, [rbp+13E0h+OutputString]; lpOutputString
0x18000645e  call    cs:__imp_OutputDebugStringW
0x180006464  test    byte ptr [rsp+14E0h+var_14C0+4], 4
0x180006469  jnz     short loc_180006474
0x18000646b  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180006472  jz      short loc_180006486
0x180006474  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000647b  test    rax, rax
0x18000647e  jz      short loc_180006486
0x180006480  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006485  nop
0x180006486  lea     rcx, [rsp+14E0h+var_14C0]; this
0x18000648b  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
