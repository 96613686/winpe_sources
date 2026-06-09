# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180002390`
- end: `0x1800025f0`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `608`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180002134`

## callees

- `0x180001ef0`
- `0x180002390`
- `0x1800044c4`
- `0x180004c5c`
- `0x1800058d0`
- `0x180007660`
- `0x18000f930`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002431`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002431`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800025be`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800025be`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002534`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002534`

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
0x180002390  mov     [rsp-8+arg_18], rbx
0x180002395  push    rbp
0x180002396  push    rsi
0x180002397  push    rdi
0x180002398  push    r12
0x18000239a  push    r13
0x18000239c  push    r14
0x18000239e  push    r15
0x1800023a0  lea     rbp, [rsp-13C0h]
0x1800023a8  mov     eax, 14C0h
0x1800023ad  call    _alloca_probe
0x1800023b2  sub     rsp, rax
0x1800023b5  mov     rsi, [rbp+13F0h+arg_28]
0x1800023bc  mov     r15, r8
0x1800023bf  mov     r14d, edx
0x1800023c2  mov     r12, rcx
0x1800023c5  xor     edx, edx; Val
0x1800023c7  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x1800023cc  mov     r8d, 98h; Size
0x1800023d2  call    memset_0
0x1800023d7  mov     rbx, [rbp+13F0h+arg_30]
0x1800023de  xor     r13d, r13d
0x1800023e1  mov     [rbp+13F0h+OutputString], r13w
0x1800023e9  mov     [rbp+13F0h+var_1430], r13b
0x1800023ed  mov     ecx, [rbx]; this
0x1800023ef  mov     eax, [rbx+4]
0x1800023f2  mov     [rsp+14F0h+var_14C8], ecx
0x1800023f6  mov     [rsp+14F0h+var_14C4], eax
0x1800023fa  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800023ff  cmp     dword ptr [rbx+8], 1
0x180002403  mov     edi, eax
0x180002405  lea     eax, [r13+8]
0x180002409  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x180002411  mov     ecx, r13d
0x180002414  cmovz   ecx, eax
0x180002417  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x18000241b  lea     ecx, [rax-7]
0x18000241e  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180002426  inc     ecx
0x180002428  mov     [rsp+14F0h+var_14B8], r13
0x18000242d  mov     [rsp+14F0h+var_14C0], ecx
0x180002431  call    cs:__imp_GetCurrentThreadId
0x180002437  xorps   xmm0, xmm0
0x18000243a  mov     [rsp+14F0h+var_1498], r15
0x18000243f  mov     [rsp+14F0h+var_14B0], eax
0x180002443  xorps   xmm1, xmm1
0x180002446  xor     eax, eax
0x180002448  mov     [rsp+14F0h+var_1490], r14d
0x18000244d  mov     [rbp+13F0h+var_1458], rax
0x180002451  mov     [rbp+13F0h+var_1470], rax
0x180002455  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000245c  mov     [rsp+14F0h+var_148C], edi
0x180002460  mov     [rsp+14F0h+var_14A8], r13
0x180002465  mov     [rsp+14F0h+var_14A0], r13
0x18000246a  mov     [rbp+13F0h+var_1448], rsi
0x18000246e  mov     [rbp+13F0h+var_1440], r12
0x180002472  mov     [rsp+14F0h+var_1488], r13
0x180002477  movups  [rbp+13F0h+var_1468], xmm0
0x18000247b  movups  [rsp+14F0h+var_1480], xmm1
0x180002480  test    rax, rax
0x180002483  jz      short loc_180002490
0x180002485  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000248a  mov     [rbp+13F0h+var_1450], rax
0x18000248e  jmp     short loc_180002494
0x180002490  mov     [rbp+13F0h+var_1450], r13
0x180002494  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000249b  test    rax, rax
0x18000249e  jz      short loc_1800024AA
0x1800024a0  lea     rcx, [rsp+14F0h+var_14D0]
0x1800024a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800024aa  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800024b1  test    rax, rax
0x1800024b4  jz      short loc_1800024CA
0x1800024b6  mov     r8d, 400h
0x1800024bc  lea     rdx, [rbp+13F0h+var_1430]
0x1800024c0  lea     rcx, [rsp+14F0h+var_14D0]
0x1800024c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800024ca  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800024d1  test    rax, rax
0x1800024d4  jz      short loc_1800024E0
0x1800024d6  lea     rcx, [rsp+14F0h+var_14D0]
0x1800024db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800024e0  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800024e7  test    rax, rax
0x1800024ea  jz      short loc_1800024FD
0x1800024ec  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800024f1  jnz     short loc_1800024FD
0x1800024f3  lea     rcx, [rsp+14F0h+var_14D0]
0x1800024f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800024fd  cmp     [rsp+14F0h+var_14C8], r13d
0x180002502  jl      short loc_180002516
0x180002504  mov     ecx, 8000FFFFh; this
0x180002509  mov     [rsp+14F0h+var_14C8], ecx
0x18000250d  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180002512  mov     [rsp+14F0h+var_14C4], eax
0x180002516  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x18000251d  jnz     short loc_18000253E
0x18000251f  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180002526  test    rax, rax
0x180002529  jz      short loc_180002534
0x18000252b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002530  test    al, al
0x180002532  jmp     short loc_18000253C
0x180002534  call    cs:__imp_IsDebuggerPresent
0x18000253a  test    eax, eax
0x18000253c  jz      short loc_180002545
0x18000253e  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180002543  jz      short loc_18000256B
0x180002545  mov     rax, cs:g_pfnResultLoggingCallback
0x18000254c  test    rax, rax
0x18000254f  jz      short loc_1800025C4
0x180002551  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180002558  jnz     short loc_1800025C4
0x18000255a  xor     r8d, r8d
0x18000255d  lea     rcx, [rsp+14F0h+var_14D0]
0x180002562  xor     edx, edx
0x180002564  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002569  jmp     short loc_1800025C4
0x18000256b  mov     rax, cs:g_pfnResultLoggingCallback
0x180002572  mov     ebx, 800h
0x180002577  test    rax, rax
0x18000257a  jz      short loc_180002599
0x18000257c  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180002583  jnz     short loc_180002599
0x180002585  mov     r8d, ebx
0x180002588  lea     rdx, [rbp+13F0h+OutputString]
0x18000258f  lea     rcx, [rsp+14F0h+var_14D0]
0x180002594  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002599  cmp     [rbp+13F0h+OutputString], r13w
0x1800025a1  jnz     short loc_1800025B7
0x1800025a3  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x1800025a8  mov     rdx, rbx; unsigned __int16 *
0x1800025ab  lea     rcx, [rbp+13F0h+OutputString]; this
0x1800025b2  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800025b7  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x1800025be  call    cs:__imp_OutputDebugStringW
0x1800025c4  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x1800025c9  jnz     short loc_1800025D4
0x1800025cb  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x1800025d2  jz      short loc_1800025E5
0x1800025d4  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800025db  test    rax, rax
0x1800025de  jz      short loc_1800025E5
0x1800025e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800025e5  lea     rcx, [rsp+14F0h+var_14D0]; this
0x1800025ea  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
