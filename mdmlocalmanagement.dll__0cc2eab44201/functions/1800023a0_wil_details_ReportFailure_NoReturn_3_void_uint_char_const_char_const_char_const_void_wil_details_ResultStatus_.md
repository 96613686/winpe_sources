# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x1800023a0`
- end: `0x18000261b`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `635`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18000214c`

## callees

- `0x180001fea`
- `0x1800023a0`
- `0x1800034b4`
- `0x180003cb8`
- `0x180004670`
- `0x1800054fc`
- `0x180006a90`
- `0x180007010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002442`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002442`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800025e2`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800025e2`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002552`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002552`

## string_xrefs

- `0x180002452`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x1800023a0  mov     [rsp-8+arg_10], rbx
0x1800023a5  mov     [rsp-8+arg_18], rsi
0x1800023aa  push    rbp
0x1800023ab  push    rdi
0x1800023ac  push    r12
0x1800023ae  push    r14
0x1800023b0  push    r15
0x1800023b2  lea     rbp, [rsp-13C0h]
0x1800023ba  mov     eax, 14C0h
0x1800023bf  call    _alloca_probe
0x1800023c4  sub     rsp, rax
0x1800023c7  mov     r14d, edx
0x1800023ca  mov     r15, rcx
0x1800023cd  mov     rsi, [rbp+13E0h+arg_28]
0x1800023d4  xor     edx, edx; Val
0x1800023d6  mov     r8d, 98h; Size
0x1800023dc  lea     rcx, [rsp+14E0h+var_14C0]; void *
0x1800023e1  call    memset_0
0x1800023e6  nop
0x1800023e7  xor     r12d, r12d
0x1800023ea  mov     [rbp+13E0h+OutputString], r12w
0x1800023f2  mov     [rbp+13E0h+var_1420], r12b
0x1800023f6  mov     rbx, [rbp+13E0h+arg_30]
0x1800023fd  mov     ecx, [rbx]; this
0x1800023ff  mov     [rsp+14E0h+var_14B8], ecx
0x180002403  mov     eax, [rbx+4]
0x180002406  mov     [rsp+14E0h+var_14B4], eax
0x18000240a  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000240f  mov     edi, eax
0x180002411  mov     dword ptr [rsp+14E0h+var_14C0], 3
0x180002419  mov     ecx, r12d
0x18000241c  lea     eax, [r12+8]
0x180002421  cmp     dword ptr [rbx+8], 1
0x180002425  cmovz   ecx, eax
0x180002428  mov     dword ptr [rsp+14E0h+var_14C0+4], ecx
0x18000242c  lea     ecx, [rax-7]
0x18000242f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180002437  inc     ecx
0x180002439  mov     [rsp+14E0h+var_14B0], ecx
0x18000243d  mov     [rsp+14E0h+var_14A8], r12
0x180002442  call    cs:__imp_GetCurrentThreadId
0x180002449  nop     dword ptr [rax+rax+00h]
0x18000244e  mov     [rsp+14E0h+var_14A0], eax
0x180002452  lea     rax, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180002459  mov     [rsp+14E0h+var_1488], rax
0x18000245e  mov     [rsp+14E0h+var_1480], r14d
0x180002463  mov     [rsp+14E0h+var_147C], edi
0x180002467  mov     [rsp+14E0h+var_1498], r12
0x18000246c  mov     [rsp+14E0h+var_1490], r12
0x180002471  mov     [rbp+13E0h+var_1438], rsi
0x180002475  mov     [rbp+13E0h+var_1430], r15
0x180002479  mov     [rsp+14E0h+var_1478], r12
0x18000247e  xorps   xmm0, xmm0
0x180002481  xor     eax, eax
0x180002483  movups  [rbp+13E0h+var_1458], xmm0
0x180002487  mov     [rbp+13E0h+var_1448], rax
0x18000248b  xorps   xmm1, xmm1
0x18000248e  movups  [rsp+14E0h+var_1470], xmm1
0x180002493  mov     [rbp+13E0h+var_1460], rax
0x180002497  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000249e  test    rax, rax
0x1800024a1  jz      short loc_1800024AE
0x1800024a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800024a8  mov     [rbp+13E0h+var_1440], rax
0x1800024ac  jmp     short loc_1800024B2
0x1800024ae  mov     [rbp+13E0h+var_1440], r12
0x1800024b2  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800024b9  test    rax, rax
0x1800024bc  jz      short loc_1800024C8
0x1800024be  lea     rcx, [rsp+14E0h+var_14C0]
0x1800024c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800024c8  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800024cf  test    rax, rax
0x1800024d2  jz      short loc_1800024E8
0x1800024d4  mov     r8d, 400h
0x1800024da  lea     rdx, [rbp+13E0h+var_1420]
0x1800024de  lea     rcx, [rsp+14E0h+var_14C0]
0x1800024e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800024e8  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800024ef  test    rax, rax
0x1800024f2  jz      short loc_1800024FE
0x1800024f4  lea     rcx, [rsp+14E0h+var_14C0]
0x1800024f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800024fe  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002505  test    rax, rax
0x180002508  jz      short loc_18000251B
0x18000250a  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x18000250f  jnz     short loc_18000251B
0x180002511  lea     rcx, [rsp+14E0h+var_14C0]
0x180002516  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000251b  cmp     [rsp+14E0h+var_14B8], r12d
0x180002520  jl      short loc_180002534
0x180002522  mov     ecx, 8000FFFFh; this
0x180002527  mov     [rsp+14E0h+var_14B8], ecx
0x18000252b  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180002530  mov     [rsp+14E0h+var_14B4], eax
0x180002534  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x18000253b  jnz     short loc_180002562
0x18000253d  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180002544  test    rax, rax
0x180002547  jz      short loc_180002552
0x180002549  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000254e  test    al, al
0x180002550  jmp     short loc_180002560
0x180002552  call    cs:__imp_IsDebuggerPresent
0x180002559  nop     dword ptr [rax+rax+00h]
0x18000255e  test    eax, eax
0x180002560  jz      short loc_180002569
0x180002562  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x180002567  jz      short loc_18000258F
0x180002569  mov     rax, cs:g_pfnResultLoggingCallback
0x180002570  test    rax, rax
0x180002573  jz      short loc_1800025EE
0x180002575  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18000257c  jnz     short loc_1800025EE
0x18000257e  xor     r8d, r8d
0x180002581  xor     edx, edx
0x180002583  lea     rcx, [rsp+14E0h+var_14C0]
0x180002588  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000258d  jmp     short loc_1800025EE
0x18000258f  mov     ebx, 800h
0x180002594  mov     rax, cs:g_pfnResultLoggingCallback
0x18000259b  test    rax, rax
0x18000259e  jz      short loc_1800025BD
0x1800025a0  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800025a7  jnz     short loc_1800025BD
0x1800025a9  mov     r8d, ebx
0x1800025ac  lea     rdx, [rbp+13E0h+OutputString]
0x1800025b3  lea     rcx, [rsp+14E0h+var_14C0]
0x1800025b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800025bd  cmp     [rbp+13E0h+OutputString], r12w
0x1800025c5  jnz     short loc_1800025DB
0x1800025c7  lea     r8, [rsp+14E0h+var_14C0]; unsigned __int64
0x1800025cc  mov     rdx, rbx; unsigned __int16 *
0x1800025cf  lea     rcx, [rbp+13E0h+OutputString]; this
0x1800025d6  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800025db  lea     rcx, [rbp+13E0h+OutputString]; lpOutputString
0x1800025e2  call    cs:__imp_OutputDebugStringW
0x1800025e9  nop     dword ptr [rax+rax+00h]
0x1800025ee  test    byte ptr [rsp+14E0h+var_14C0+4], 4
0x1800025f3  jnz     short loc_1800025FE
0x1800025f5  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x1800025fc  jz      short loc_180002610
0x1800025fe  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180002605  test    rax, rax
0x180002608  jz      short loc_180002610
0x18000260a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000260f  nop
0x180002610  lea     rcx, [rsp+14E0h+var_14C0]; this
0x180002615  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
