# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x18000e2b8`
- end: `0x18000e54e`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `662`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18000df80`

## callees

- `0x180002f50`
- `0x180003c14`
- `0x18000e2b8`
- `0x18000fba4`
- `0x18001152c`
- `0x180012c08`
- `0x180012e14`
- `0x1800acfe0`
- `0x1800b5010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e363`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e363`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000e45e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000e45e`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000e4e8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000e4e8`

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
      wil::GetFailureLogString((wil *)OutputString, (wchar_t *)0x800, (unsigned __int64)&v16, v14);
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
0x18000e2b8  mov     [rsp-8+arg_10], rbx
0x18000e2bd  push    rbp
0x18000e2be  push    rsi
0x18000e2bf  push    rdi
0x18000e2c0  push    r14
0x18000e2c2  push    r15
0x18000e2c4  lea     rbp, [rsp-13D0h]
0x18000e2cc  mov     eax, 14D0h
0x18000e2d1  call    _alloca_probe
0x18000e2d6  sub     rsp, rax
0x18000e2d9  mov     rax, cs:__security_cookie
0x18000e2e0  xor     rax, rsp
0x18000e2e3  mov     [rbp+13F0h+var_30], rax
0x18000e2ea  mov     esi, edx
0x18000e2ec  mov     r14, rcx
0x18000e2ef  mov     rdi, [rbp+13F0h+arg_28]
0x18000e2f6  xor     edx, edx; Val
0x18000e2f8  mov     r8d, 98h; Size
0x18000e2fe  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x18000e303  call    memset_0
0x18000e308  nop
0x18000e309  xor     r15d, r15d
0x18000e30c  mov     [rbp+13F0h+OutputString], r15w
0x18000e314  mov     [rbp+13F0h+var_1430], r15b
0x18000e318  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x18000e31f  mov     ecx, [rdx]; this
0x18000e321  mov     [rsp+14F0h+var_14C8], ecx
0x18000e325  mov     eax, [rdx+4]
0x18000e328  mov     [rsp+14F0h+var_14C4], eax
0x18000e32c  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000e331  mov     ebx, eax
0x18000e333  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x18000e33b  mov     ecx, r15d
0x18000e33e  lea     eax, [r15+8]
0x18000e342  cmp     dword ptr [rdx+8], 1
0x18000e346  cmovz   ecx, eax
0x18000e349  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x18000e34d  lea     ecx, [rax-7]
0x18000e350  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000e358  inc     ecx
0x18000e35a  mov     [rsp+14F0h+var_14C0], ecx
0x18000e35e  mov     [rsp+14F0h+var_14B8], r15
0x18000e363  call    cs:__imp_GetCurrentThreadId
0x18000e369  mov     [rsp+14F0h+var_14B0], eax
0x18000e36d  lea     rax, aWil; "wil"
0x18000e374  mov     [rsp+14F0h+var_1498], rax
0x18000e379  mov     [rsp+14F0h+var_1490], esi
0x18000e37d  mov     [rsp+14F0h+var_148C], ebx
0x18000e381  mov     [rsp+14F0h+var_14A8], r15
0x18000e386  mov     [rsp+14F0h+var_14A0], r15
0x18000e38b  mov     [rbp+13F0h+var_1448], rdi
0x18000e38f  mov     [rbp+13F0h+var_1440], r14
0x18000e393  mov     [rsp+14F0h+var_1488], r15
0x18000e398  xorps   xmm0, xmm0
0x18000e39b  xor     eax, eax
0x18000e39d  movups  [rbp+13F0h+var_1468], xmm0
0x18000e3a1  mov     [rbp+13F0h+var_1458], rax
0x18000e3a5  xorps   xmm1, xmm1
0x18000e3a8  movups  [rsp+14F0h+var_1480], xmm1
0x18000e3ad  mov     [rbp+13F0h+var_1470], rax
0x18000e3b1  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000e3b8  test    rax, rax
0x18000e3bb  jz      short loc_18000E3C8
0x18000e3bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e3c2  mov     [rbp+13F0h+var_1450], rax
0x18000e3c6  jmp     short loc_18000E3CC
0x18000e3c8  mov     [rbp+13F0h+var_1450], r15
0x18000e3cc  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000e3d3  test    rax, rax
0x18000e3d6  jz      short loc_18000E3E2
0x18000e3d8  lea     rcx, [rsp+14F0h+var_14D0]
0x18000e3dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e3e2  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000e3e9  test    rax, rax
0x18000e3ec  jz      short loc_18000E402
0x18000e3ee  mov     r8d, 400h
0x18000e3f4  lea     rdx, [rbp+13F0h+var_1430]
0x18000e3f8  lea     rcx, [rsp+14F0h+var_14D0]
0x18000e3fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e402  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000e409  test    rax, rax
0x18000e40c  jz      short loc_18000E418
0x18000e40e  lea     rcx, [rsp+14F0h+var_14D0]
0x18000e413  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e418  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000e41f  test    rax, rax
0x18000e422  jz      short loc_18000E435
0x18000e424  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000e429  jnz     short loc_18000E435
0x18000e42b  lea     rcx, [rsp+14F0h+var_14D0]
0x18000e430  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e435  cmp     [rsp+14F0h+var_14C8], r15d
0x18000e43a  jge     loc_18000E548
0x18000e440  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x18000e447  jnz     short loc_18000E468
0x18000e449  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000e450  test    rax, rax
0x18000e453  jz      short loc_18000E45E
0x18000e455  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e45a  test    al, al
0x18000e45c  jmp     short loc_18000E466
0x18000e45e  call    cs:__imp_IsDebuggerPresent
0x18000e464  test    eax, eax
0x18000e466  jz      short loc_18000E46F
0x18000e468  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000e46d  jz      short loc_18000E495
0x18000e46f  mov     rax, cs:g_pfnResultLoggingCallback
0x18000e476  test    rax, rax
0x18000e479  jz      short loc_18000E4EE
0x18000e47b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000e482  jnz     short loc_18000E4EE
0x18000e484  xor     r8d, r8d
0x18000e487  xor     edx, edx
0x18000e489  lea     rcx, [rsp+14F0h+var_14D0]
0x18000e48e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e493  jmp     short loc_18000E4EE
0x18000e495  mov     ebx, 800h
0x18000e49a  mov     rax, cs:g_pfnResultLoggingCallback
0x18000e4a1  test    rax, rax
0x18000e4a4  jz      short loc_18000E4C3
0x18000e4a6  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000e4ad  jnz     short loc_18000E4C3
0x18000e4af  mov     r8d, ebx
0x18000e4b2  lea     rdx, [rbp+13F0h+OutputString]
0x18000e4b9  lea     rcx, [rsp+14F0h+var_14D0]
0x18000e4be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e4c3  cmp     [rbp+13F0h+OutputString], r15w
0x18000e4cb  jnz     short loc_18000E4E1
0x18000e4cd  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x18000e4d2  mov     rdx, rbx; wchar_t *
0x18000e4d5  lea     rcx, [rbp+13F0h+OutputString]; this
0x18000e4dc  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x18000e4e1  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x18000e4e8  call    cs:__imp_OutputDebugStringW
0x18000e4ee  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x18000e4f3  jnz     short loc_18000E4FE
0x18000e4f5  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x18000e4fc  jz      short loc_18000E510
0x18000e4fe  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000e505  test    rax, rax
0x18000e508  jz      short loc_18000E510
0x18000e50a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e50f  nop
0x18000e510  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x18000e515  jnz     short loc_18000E53D
0x18000e517  mov     rcx, [rbp+13F0h+var_30]
0x18000e51e  xor     rcx, rsp; StackCookie
0x18000e521  call    __security_check_cookie
0x18000e526  mov     rbx, [rsp+14F0h+arg_10]
0x18000e52e  add     rsp, 14D0h
0x18000e535  pop     r15
0x18000e537  pop     r14
0x18000e539  pop     rdi
0x18000e53a  pop     rsi
0x18000e53b  pop     rbp
0x18000e53c  retn
0x18000e53d  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000e542  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18000e548  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
