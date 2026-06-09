# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x18001b800`
- end: `0x18001ba72`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `626`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18001b58c`

## callees

- `0x18001b800`
- `0x18001d9d4`
- `0x18001e1e8`
- `0x180023c70`
- `0x18002619c`
- `0x18003100e`
- `0x180031100`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001b8a1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001b8a1`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18001b9aa`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18001b9aa`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001ba3a`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001ba3a`

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
0x18001b800  mov     [rsp-8+arg_18], rbx
0x18001b805  push    rbp
0x18001b806  push    rsi
0x18001b807  push    rdi
0x18001b808  push    r12
0x18001b80a  push    r13
0x18001b80c  push    r14
0x18001b80e  push    r15
0x18001b810  lea     rbp, [rsp-13C0h]
0x18001b818  mov     eax, 14C0h
0x18001b81d  call    _alloca_probe
0x18001b822  sub     rsp, rax
0x18001b825  mov     rsi, [rbp+13F0h+arg_28]
0x18001b82c  mov     r15, r8
0x18001b82f  mov     r14d, edx
0x18001b832  mov     r12, rcx
0x18001b835  xor     edx, edx; Val
0x18001b837  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x18001b83c  mov     r8d, 98h; Size
0x18001b842  call    memset_0
0x18001b847  mov     rbx, [rbp+13F0h+arg_30]
0x18001b84e  xor     r13d, r13d
0x18001b851  mov     [rbp+13F0h+OutputString], r13w
0x18001b859  mov     [rbp+13F0h+var_1430], r13b
0x18001b85d  mov     ecx, [rbx]; this
0x18001b85f  mov     eax, [rbx+4]
0x18001b862  mov     [rsp+14F0h+var_14C8], ecx
0x18001b866  mov     [rsp+14F0h+var_14C4], eax
0x18001b86a  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18001b86f  cmp     dword ptr [rbx+8], 1
0x18001b873  mov     edi, eax
0x18001b875  lea     eax, [r13+8]
0x18001b879  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x18001b881  mov     ecx, r13d
0x18001b884  cmovz   ecx, eax
0x18001b887  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x18001b88b  lea     ecx, [rax-7]
0x18001b88e  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureInfo *)'::`2'::s_failureId
0x18001b896  inc     ecx
0x18001b898  mov     [rsp+14F0h+var_14B8], r13
0x18001b89d  mov     [rsp+14F0h+var_14C0], ecx
0x18001b8a1  call    cs:__imp_GetCurrentThreadId
0x18001b8a8  nop     dword ptr [rax+rax+00h]
0x18001b8ad  xorps   xmm0, xmm0
0x18001b8b0  mov     [rsp+14F0h+var_1498], r15
0x18001b8b5  mov     [rsp+14F0h+var_14B0], eax
0x18001b8b9  xorps   xmm1, xmm1
0x18001b8bc  xor     eax, eax
0x18001b8be  mov     [rsp+14F0h+var_1490], r14d
0x18001b8c3  mov     [rbp+13F0h+var_1458], rax
0x18001b8c7  mov     [rbp+13F0h+var_1470], rax
0x18001b8cb  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18001b8d2  mov     [rsp+14F0h+var_148C], edi
0x18001b8d6  mov     [rsp+14F0h+var_14A8], r13
0x18001b8db  mov     [rsp+14F0h+var_14A0], r13
0x18001b8e0  mov     [rbp+13F0h+var_1448], rsi
0x18001b8e4  mov     [rbp+13F0h+var_1440], r12
0x18001b8e8  mov     [rsp+14F0h+var_1488], r13
0x18001b8ed  movups  [rbp+13F0h+var_1468], xmm0
0x18001b8f1  movups  [rsp+14F0h+var_1480], xmm1
0x18001b8f6  test    rax, rax
0x18001b8f9  jz      short loc_18001B906
0x18001b8fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b900  mov     [rbp+13F0h+var_1450], rax
0x18001b904  jmp     short loc_18001B90A
0x18001b906  mov     [rbp+13F0h+var_1450], r13
0x18001b90a  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18001b911  test    rax, rax
0x18001b914  jz      short loc_18001B920
0x18001b916  lea     rcx, [rsp+14F0h+var_14D0]
0x18001b91b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b920  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18001b927  test    rax, rax
0x18001b92a  jz      short loc_18001B940
0x18001b92c  mov     r8d, 400h
0x18001b932  lea     rdx, [rbp+13F0h+var_1430]
0x18001b936  lea     rcx, [rsp+14F0h+var_14D0]
0x18001b93b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b940  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18001b947  test    rax, rax
0x18001b94a  jz      short loc_18001B956
0x18001b94c  lea     rcx, [rsp+14F0h+var_14D0]
0x18001b951  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b956  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18001b95d  test    rax, rax
0x18001b960  jz      short loc_18001B973
0x18001b962  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18001b967  jnz     short loc_18001B973
0x18001b969  lea     rcx, [rsp+14F0h+var_14D0]
0x18001b96e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b973  cmp     [rsp+14F0h+var_14C8], r13d
0x18001b978  jl      short loc_18001B98C
0x18001b97a  mov     ecx, 8000FFFFh; this
0x18001b97f  mov     [rsp+14F0h+var_14C8], ecx
0x18001b983  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18001b988  mov     [rsp+14F0h+var_14C4], eax
0x18001b98c  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x18001b993  jnz     short loc_18001B9BA
0x18001b995  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18001b99c  test    rax, rax
0x18001b99f  jz      short loc_18001B9AA
0x18001b9a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b9a6  test    al, al
0x18001b9a8  jmp     short loc_18001B9B8
0x18001b9aa  call    cs:__imp_IsDebuggerPresent
0x18001b9b1  nop     dword ptr [rax+rax+00h]
0x18001b9b6  test    eax, eax
0x18001b9b8  jz      short loc_18001B9C1
0x18001b9ba  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18001b9bf  jz      short loc_18001B9E7
0x18001b9c1  mov     rax, cs:g_pfnResultLoggingCallback
0x18001b9c8  test    rax, rax
0x18001b9cb  jz      short loc_18001BA46
0x18001b9cd  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x18001b9d4  jnz     short loc_18001BA46
0x18001b9d6  xor     r8d, r8d
0x18001b9d9  lea     rcx, [rsp+14F0h+var_14D0]
0x18001b9de  xor     edx, edx
0x18001b9e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b9e5  jmp     short loc_18001BA46
0x18001b9e7  mov     rax, cs:g_pfnResultLoggingCallback
0x18001b9ee  mov     ebx, 800h
0x18001b9f3  test    rax, rax
0x18001b9f6  jz      short loc_18001BA15
0x18001b9f8  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x18001b9ff  jnz     short loc_18001BA15
0x18001ba01  mov     r8d, ebx
0x18001ba04  lea     rdx, [rbp+13F0h+OutputString]
0x18001ba0b  lea     rcx, [rsp+14F0h+var_14D0]
0x18001ba10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ba15  cmp     [rbp+13F0h+OutputString], r13w
0x18001ba1d  jnz     short loc_18001BA33
0x18001ba1f  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x18001ba24  mov     rdx, rbx; unsigned __int16 *
0x18001ba27  lea     rcx, [rbp+13F0h+OutputString]; this
0x18001ba2e  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18001ba33  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x18001ba3a  call    cs:__imp_OutputDebugStringW
0x18001ba41  nop     dword ptr [rax+rax+00h]
0x18001ba46  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x18001ba4b  jnz     short loc_18001BA56
0x18001ba4d  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x18001ba54  jz      short loc_18001BA67
0x18001ba56  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18001ba5d  test    rax, rax
0x18001ba60  jz      short loc_18001BA67
0x18001ba62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ba67  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18001ba6c  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
