# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x1800087e4`
- end: `0x180008a4b`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `615`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180008598`

## callees

- `0x180002b20`
- `0x1800087e4`
- `0x1800098cc`
- `0x180009f38`
- `0x18000b128`
- `0x18000c392`
- `0x18000c450`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000898f`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000898f`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180008a19`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180008a19`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008885`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008885`

## string_xrefs

- `0x18000889a`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
  int v9; // eax
  int v10; // edx
  int v11; // eax
  int v12; // edi
  int v13; // ecx
  DWORD CurrentThreadId; // eax
  const struct wil::FailureInfo *v15; // rdx
  __int64 v16; // rcx
  const struct wil::FailureInfo *v17; // r9
  bool v18; // zf
  int v19; // [rsp+20h] [rbp-E0h] BYREF
  int v20; // [rsp+24h] [rbp-DCh]
  int v21; // [rsp+28h] [rbp-D8h]
  int v22; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v23; // [rsp+30h] [rbp-D0h]
  __int64 v24; // [rsp+38h] [rbp-C8h]
  DWORD v25; // [rsp+40h] [rbp-C0h]
  __int64 v26; // [rsp+48h] [rbp-B8h]
  __int64 v27; // [rsp+50h] [rbp-B0h]
  const char *v28; // [rsp+58h] [rbp-A8h]
  int v29; // [rsp+60h] [rbp-A0h]
  int v30; // [rsp+64h] [rbp-9Ch]
  __int64 v31; // [rsp+68h] [rbp-98h]
  __int128 v32; // [rsp+70h] [rbp-90h]
  __int64 v33; // [rsp+80h] [rbp-80h]
  __int128 v34; // [rsp+88h] [rbp-78h]
  __int64 v35; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v37; // [rsp+A8h] [rbp-58h]
  __int64 v38; // [rsp+B0h] [rbp-50h]
  char v39[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2064]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v19, 0, 0x98u);
  OutputString[0] = 0;
  v39[0] = 0;
  v9 = a7[1];
  v21 = *a7;
  v22 = v9;
  v11 = wil::details::RecordFailFast((wil::details *)(unsigned int)v21, v10);
  v18 = a7[2] == 1;
  v12 = v11;
  v19 = 3;
  v13 = 0;
  if ( v18 )
    v13 = 8;
  v20 = v13;
  v24 = 0;
  v23 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  CurrentThreadId = GetCurrentThreadId();
  v29 = a2;
  v25 = CurrentThreadId;
  v30 = v12;
  v28 = "onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h";
  v35 = 0;
  v33 = 0;
  v26 = 0;
  v27 = 0;
  v37 = a6;
  v38 = a1;
  v31 = 0;
  v34 = 0;
  v32 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v16);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v19);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v19, v39, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v19);
  if ( wil::details::g_pfnOriginateCallback && (v20 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v19);
  if ( v21 >= 0 )
  {
    v21 = -2147418113;
    v22 = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, (int)v15);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v18 = !IsDebuggerPresent())
      : (v18 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v16) == 0),
        v18)
    || (v20 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v19, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v19, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v19, v17);
    OutputDebugStringW(OutputString);
  }
  if ( (v20 & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v16);
  }
  wil::details::WilFailFast((wil::details *)&v19, v15);
}

```

## disassembly

```asm
0x1800087e4  mov     [rsp-8+arg_10], rbx
0x1800087e9  mov     [rsp-8+arg_18], rsi
0x1800087ee  push    rbp
0x1800087ef  push    rdi
0x1800087f0  push    r12
0x1800087f2  push    r14
0x1800087f4  push    r15
0x1800087f6  lea     rbp, [rsp-13C0h]
0x1800087fe  mov     eax, 14C0h
0x180008803  call    _alloca_probe
0x180008808  sub     rsp, rax
0x18000880b  mov     rsi, [rbp+13E0h+arg_28]
0x180008812  mov     r14d, edx
0x180008815  mov     r15, rcx
0x180008818  xor     edx, edx; Val
0x18000881a  lea     rcx, [rsp+14E0h+var_14C0]; void *
0x18000881f  mov     r8d, 98h; Size
0x180008825  call    memset_0
0x18000882a  mov     rbx, [rbp+13E0h+arg_30]
0x180008831  xor     r12d, r12d
0x180008834  mov     [rbp+13E0h+OutputString], r12w
0x18000883c  mov     [rbp+13E0h+var_1420], r12b
0x180008840  mov     ecx, [rbx]; this
0x180008842  mov     eax, [rbx+4]
0x180008845  mov     [rsp+14E0h+var_14B8], ecx
0x180008849  mov     [rsp+14E0h+var_14B4], eax
0x18000884d  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180008852  cmp     dword ptr [rbx+8], 1
0x180008856  mov     edi, eax
0x180008858  lea     eax, [r12+8]
0x18000885d  mov     dword ptr [rsp+14E0h+var_14C0], 3
0x180008865  mov     ecx, r12d
0x180008868  cmovz   ecx, eax
0x18000886b  mov     dword ptr [rsp+14E0h+var_14C0+4], ecx
0x18000886f  lea     ecx, [rax-7]
0x180008872  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000887a  inc     ecx
0x18000887c  mov     [rsp+14E0h+var_14A8], r12
0x180008881  mov     [rsp+14E0h+var_14B0], ecx
0x180008885  call    cs:__imp_GetCurrentThreadId
0x18000888b  xorps   xmm0, xmm0
0x18000888e  mov     [rsp+14E0h+var_1480], r14d
0x180008893  mov     [rsp+14E0h+var_14A0], eax
0x180008897  xorps   xmm1, xmm1
0x18000889a  lea     rax, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800088a1  mov     [rsp+14E0h+var_147C], edi
0x1800088a5  mov     [rsp+14E0h+var_1488], rax
0x1800088aa  xor     eax, eax
0x1800088ac  mov     [rbp+13E0h+var_1448], rax
0x1800088b0  mov     [rbp+13E0h+var_1460], rax
0x1800088b4  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800088bb  mov     [rsp+14E0h+var_1498], r12
0x1800088c0  mov     [rsp+14E0h+var_1490], r12
0x1800088c5  mov     [rbp+13E0h+var_1438], rsi
0x1800088c9  mov     [rbp+13E0h+var_1430], r15
0x1800088cd  mov     [rsp+14E0h+var_1478], r12
0x1800088d2  movups  [rbp+13E0h+var_1458], xmm0
0x1800088d6  movups  [rsp+14E0h+var_1470], xmm1
0x1800088db  test    rax, rax
0x1800088de  jz      short loc_1800088EB
0x1800088e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800088e5  mov     [rbp+13E0h+var_1440], rax
0x1800088e9  jmp     short loc_1800088EF
0x1800088eb  mov     [rbp+13E0h+var_1440], r12
0x1800088ef  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800088f6  test    rax, rax
0x1800088f9  jz      short loc_180008905
0x1800088fb  lea     rcx, [rsp+14E0h+var_14C0]
0x180008900  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008905  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000890c  test    rax, rax
0x18000890f  jz      short loc_180008925
0x180008911  mov     r8d, 400h
0x180008917  lea     rdx, [rbp+13E0h+var_1420]
0x18000891b  lea     rcx, [rsp+14E0h+var_14C0]
0x180008920  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008925  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000892c  test    rax, rax
0x18000892f  jz      short loc_18000893B
0x180008931  lea     rcx, [rsp+14E0h+var_14C0]
0x180008936  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000893b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180008942  test    rax, rax
0x180008945  jz      short loc_180008958
0x180008947  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x18000894c  jnz     short loc_180008958
0x18000894e  lea     rcx, [rsp+14E0h+var_14C0]
0x180008953  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008958  cmp     [rsp+14E0h+var_14B8], r12d
0x18000895d  jl      short loc_180008971
0x18000895f  mov     ecx, 8000FFFFh; this
0x180008964  mov     [rsp+14E0h+var_14B8], ecx
0x180008968  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000896d  mov     [rsp+14E0h+var_14B4], eax
0x180008971  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180008978  jnz     short loc_180008999
0x18000897a  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180008981  test    rax, rax
0x180008984  jz      short loc_18000898F
0x180008986  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000898b  test    al, al
0x18000898d  jmp     short loc_180008997
0x18000898f  call    cs:__imp_IsDebuggerPresent
0x180008995  test    eax, eax
0x180008997  jz      short loc_1800089A0
0x180008999  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x18000899e  jz      short loc_1800089C6
0x1800089a0  mov     rax, cs:g_pfnResultLoggingCallback
0x1800089a7  test    rax, rax
0x1800089aa  jz      short loc_180008A1F
0x1800089ac  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800089b3  jnz     short loc_180008A1F
0x1800089b5  xor     r8d, r8d
0x1800089b8  lea     rcx, [rsp+14E0h+var_14C0]
0x1800089bd  xor     edx, edx
0x1800089bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800089c4  jmp     short loc_180008A1F
0x1800089c6  mov     rax, cs:g_pfnResultLoggingCallback
0x1800089cd  mov     ebx, 800h
0x1800089d2  test    rax, rax
0x1800089d5  jz      short loc_1800089F4
0x1800089d7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800089de  jnz     short loc_1800089F4
0x1800089e0  mov     r8d, ebx
0x1800089e3  lea     rdx, [rbp+13E0h+OutputString]
0x1800089ea  lea     rcx, [rsp+14E0h+var_14C0]
0x1800089ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800089f4  cmp     [rbp+13E0h+OutputString], r12w
0x1800089fc  jnz     short loc_180008A12
0x1800089fe  lea     r8, [rsp+14E0h+var_14C0]; unsigned __int64
0x180008a03  mov     rdx, rbx; unsigned __int16 *
0x180008a06  lea     rcx, [rbp+13E0h+OutputString]; this
0x180008a0d  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180008a12  lea     rcx, [rbp+13E0h+OutputString]; lpOutputString
0x180008a19  call    cs:__imp_OutputDebugStringW
0x180008a1f  test    byte ptr [rsp+14E0h+var_14C0+4], 4
0x180008a24  jnz     short loc_180008A2F
0x180008a26  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180008a2d  jz      short loc_180008A40
0x180008a2f  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180008a36  test    rax, rax
0x180008a39  jz      short loc_180008A40
0x180008a3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a40  lea     rcx, [rsp+14E0h+var_14C0]; this
0x180008a45  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
