# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x1800b2280`
- end: `0x1800b2516`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `662`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18009f2ec`

## callees

- `0x1800a9d20`
- `0x1800aa9a8`
- `0x1800b2280`
- `0x1800b3314`
- `0x1800b4430`
- `0x1800b53d8`
- `0x1800b55e4`
- `0x1800dd610`
- `0x1801cb010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800b232b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800b232b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800b24b0`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800b24b0`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800b2426`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800b2426`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::ReportFailure_Return<1>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7)
{
  int v9; // ebx
  int v10; // ecx
  __int64 v11; // rdx
  const struct wil::FailureInfo *v12; // rdx
  wil::details::in1diag3 *v13; // rcx
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
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v16, 0, 0x98u);
  OutputString[0] = 0;
  v36[0] = 0;
  v18 = *a7;
  v19 = a7[1];
  v9 = wil::details::RecordReturn((wil::details *)(unsigned int)v18, (int)a7);
  v16 = 1;
  v10 = 0;
  if ( *(_DWORD *)(v11 + 8) == 1 )
    v10 = 8;
  v17 = v10;
  v20 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v21 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v25 = "wil";
  v26 = a2;
  v27 = v9;
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
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v13);
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
      wil::GetFailureLogString(OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v16, v14);
    OutputDebugStringW(OutputString);
  }
  if ( ((v17 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v13);
  if ( (v17 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v16, v12);
}

```

## disassembly

```asm
0x1800b2280  mov     [rsp-8+arg_10], rbx
0x1800b2285  push    rbp
0x1800b2286  push    rsi
0x1800b2287  push    rdi
0x1800b2288  push    r14
0x1800b228a  push    r15
0x1800b228c  lea     rbp, [rsp-13D0h]
0x1800b2294  mov     eax, 14D0h
0x1800b2299  call    _alloca_probe
0x1800b229e  sub     rsp, rax
0x1800b22a1  mov     rax, cs:__security_cookie
0x1800b22a8  xor     rax, rsp
0x1800b22ab  mov     [rbp+13F0h+var_30], rax
0x1800b22b2  mov     esi, edx
0x1800b22b4  mov     r14, rcx
0x1800b22b7  mov     rdi, [rbp+13F0h+arg_28]
0x1800b22be  xor     edx, edx; Val
0x1800b22c0  mov     r8d, 98h; Size
0x1800b22c6  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x1800b22cb  call    memset_0
0x1800b22d0  nop
0x1800b22d1  xor     r15d, r15d
0x1800b22d4  mov     [rbp+13F0h+OutputString], r15w
0x1800b22dc  mov     [rbp+13F0h+var_1430], r15b
0x1800b22e0  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x1800b22e7  mov     ecx, [rdx]; this
0x1800b22e9  mov     [rsp+14F0h+var_14C8], ecx
0x1800b22ed  mov     eax, [rdx+4]
0x1800b22f0  mov     [rsp+14F0h+var_14C4], eax
0x1800b22f4  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800b22f9  mov     ebx, eax
0x1800b22fb  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x1800b2303  mov     ecx, r15d
0x1800b2306  lea     eax, [r15+8]
0x1800b230a  cmp     dword ptr [rdx+8], 1
0x1800b230e  cmovz   ecx, eax
0x1800b2311  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x1800b2315  lea     ecx, [rax-7]
0x1800b2318  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800b2320  inc     ecx
0x1800b2322  mov     [rsp+14F0h+var_14C0], ecx
0x1800b2326  mov     [rsp+14F0h+var_14B8], r15
0x1800b232b  call    cs:__imp_GetCurrentThreadId
0x1800b2331  mov     [rsp+14F0h+var_14B0], eax
0x1800b2335  lea     rax, aWil; "wil"
0x1800b233c  mov     [rsp+14F0h+var_1498], rax
0x1800b2341  mov     [rsp+14F0h+var_1490], esi
0x1800b2345  mov     [rsp+14F0h+var_148C], ebx
0x1800b2349  mov     [rsp+14F0h+var_14A8], r15
0x1800b234e  mov     [rsp+14F0h+var_14A0], r15
0x1800b2353  mov     [rbp+13F0h+var_1448], rdi
0x1800b2357  mov     [rbp+13F0h+var_1440], r14
0x1800b235b  mov     [rsp+14F0h+var_1488], r15
0x1800b2360  xorps   xmm0, xmm0
0x1800b2363  xor     eax, eax
0x1800b2365  movups  [rbp+13F0h+var_1468], xmm0
0x1800b2369  mov     [rbp+13F0h+var_1458], rax
0x1800b236d  xorps   xmm1, xmm1
0x1800b2370  movups  [rsp+14F0h+var_1480], xmm1
0x1800b2375  mov     [rbp+13F0h+var_1470], rax
0x1800b2379  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800b2380  test    rax, rax
0x1800b2383  jz      short loc_1800B2390
0x1800b2385  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b238a  mov     [rbp+13F0h+var_1450], rax
0x1800b238e  jmp     short loc_1800B2394
0x1800b2390  mov     [rbp+13F0h+var_1450], r15
0x1800b2394  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800b239b  test    rax, rax
0x1800b239e  jz      short loc_1800B23AA
0x1800b23a0  lea     rcx, [rsp+14F0h+var_14D0]
0x1800b23a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b23aa  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800b23b1  test    rax, rax
0x1800b23b4  jz      short loc_1800B23CA
0x1800b23b6  mov     r8d, 400h
0x1800b23bc  lea     rdx, [rbp+13F0h+var_1430]
0x1800b23c0  lea     rcx, [rsp+14F0h+var_14D0]
0x1800b23c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b23ca  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800b23d1  test    rax, rax
0x1800b23d4  jz      short loc_1800B23E0
0x1800b23d6  lea     rcx, [rsp+14F0h+var_14D0]
0x1800b23db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b23e0  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800b23e7  test    rax, rax
0x1800b23ea  jz      short loc_1800B23FD
0x1800b23ec  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800b23f1  jnz     short loc_1800B23FD
0x1800b23f3  lea     rcx, [rsp+14F0h+var_14D0]
0x1800b23f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b23fd  cmp     [rsp+14F0h+var_14C8], r15d
0x1800b2402  jge     loc_1800B2510
0x1800b2408  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x1800b240f  jnz     short loc_1800B2430
0x1800b2411  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800b2418  test    rax, rax
0x1800b241b  jz      short loc_1800B2426
0x1800b241d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b2422  test    al, al
0x1800b2424  jmp     short loc_1800B242E
0x1800b2426  call    cs:__imp_IsDebuggerPresent
0x1800b242c  test    eax, eax
0x1800b242e  jz      short loc_1800B2437
0x1800b2430  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800b2435  jz      short loc_1800B245D
0x1800b2437  mov     rax, cs:g_pfnResultLoggingCallback
0x1800b243e  test    rax, rax
0x1800b2441  jz      short loc_1800B24B6
0x1800b2443  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800b244a  jnz     short loc_1800B24B6
0x1800b244c  xor     r8d, r8d
0x1800b244f  xor     edx, edx
0x1800b2451  lea     rcx, [rsp+14F0h+var_14D0]
0x1800b2456  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b245b  jmp     short loc_1800B24B6
0x1800b245d  mov     ebx, 800h
0x1800b2462  mov     rax, cs:g_pfnResultLoggingCallback
0x1800b2469  test    rax, rax
0x1800b246c  jz      short loc_1800B248B
0x1800b246e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800b2475  jnz     short loc_1800B248B
0x1800b2477  mov     r8d, ebx
0x1800b247a  lea     rdx, [rbp+13F0h+OutputString]
0x1800b2481  lea     rcx, [rsp+14F0h+var_14D0]
0x1800b2486  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b248b  cmp     [rbp+13F0h+OutputString], r15w
0x1800b2493  jnz     short loc_1800B24A9
0x1800b2495  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x1800b249a  mov     rdx, rbx; unsigned __int16 *
0x1800b249d  lea     rcx, [rbp+13F0h+OutputString]; String
0x1800b24a4  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800b24a9  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x1800b24b0  call    cs:__imp_OutputDebugStringW
0x1800b24b6  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x1800b24bb  jnz     short loc_1800B24C6
0x1800b24bd  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x1800b24c4  jz      short loc_1800B24D8
0x1800b24c6  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800b24cd  test    rax, rax
0x1800b24d0  jz      short loc_1800B24D8
0x1800b24d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b24d7  nop
0x1800b24d8  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x1800b24dd  jnz     short loc_1800B2505
0x1800b24df  mov     rcx, [rbp+13F0h+var_30]
0x1800b24e6  xor     rcx, rsp; StackCookie
0x1800b24e9  call    __security_check_cookie
0x1800b24ee  mov     rbx, [rsp+14F0h+arg_10]
0x1800b24f6  add     rsp, 14D0h
0x1800b24fd  pop     r15
0x1800b24ff  pop     r14
0x1800b2501  pop     rdi
0x1800b2502  pop     rsi
0x1800b2503  pop     rbp
0x1800b2504  retn
0x1800b2505  lea     rcx, [rsp+14F0h+var_14D0]; this
0x1800b250a  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x1800b2510  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
