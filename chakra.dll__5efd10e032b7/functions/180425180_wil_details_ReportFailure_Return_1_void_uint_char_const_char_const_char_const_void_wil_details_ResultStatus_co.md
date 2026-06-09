# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180425180`
- end: `0x180425462`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `738`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180424d60`

## callees

- `0x180425180`
- `0x180426d14`
- `0x1804290c8`
- `0x18042b034`
- `0x18042b28c`
- `0x1805a9e80`
- `0x1805a9eb0`
- `0x1805cd010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18042526b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18042526b`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18042536c`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18042536c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1804253fc`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1804253fc`

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
        unsigned __int64 *a7)
{
  unsigned int v9; // ebx
  int v10; // ecx
  __int64 v11; // r8
  const struct wil::FailureInfo *v12; // rdx
  wil::details::in1diag3 *v13; // rcx
  const struct wil::FailureInfo *v14; // r9
  bool v15; // zf
  unsigned __int64 v16[2]; // [rsp+20h] [rbp-E0h] BYREF
  __int128 v17; // [rsp+30h] [rbp-D0h]
  __int128 v18; // [rsp+40h] [rbp-C0h]
  __int128 v19; // [rsp+50h] [rbp-B0h]
  __int128 v20; // [rsp+60h] [rbp-A0h]
  __int128 v21; // [rsp+70h] [rbp-90h]
  _OWORD v22[2]; // [rsp+80h] [rbp-80h] BYREF
  __int128 v23; // [rsp+A0h] [rbp-60h]
  __int64 v24; // [rsp+B0h] [rbp-50h]
  __int64 v25; // [rsp+C0h] [rbp-40h]
  _BYTE v26[1024]; // [rsp+D0h] [rbp-30h] BYREF
  WCHAR OutputString[2048]; // [rsp+4D0h] [rbp+3D0h] BYREF

  v25 = -2;
  *(_OWORD *)v16 = 0;
  v17 = 0;
  v18 = 0;
  v19 = 0;
  v20 = 0;
  v21 = 0;
  memset(v22, 0, sizeof(v22));
  v23 = 0;
  v24 = 0;
  OutputString[0] = 0;
  v26[0] = 0;
  v16[1] = *a7;
  v9 = wil::details::RecordReturn((wil::details *)LODWORD(v16[1]), a2);
  LODWORD(v16[0]) = 1;
  v10 = 0;
  if ( *(_DWORD *)(v11 + 8) == 1 )
    v10 = 8;
  HIDWORD(v16[0]) = v10;
  LODWORD(v17) = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  *((_QWORD *)&v17 + 1) = 0;
  LODWORD(v18) = GetCurrentThreadId();
  *((_QWORD *)&v19 + 1) = "wil";
  v20 = __PAIR64__(v9, a2);
  *((_QWORD *)&v18 + 1) = 0;
  *(_QWORD *)&v19 = 0;
  *((_QWORD *)&v23 + 1) = a6;
  v24 = a1;
  v21 = 0;
  memset(v22, 0, sizeof(v22));
  if ( wil::details::g_pfnGetModuleName )
    *(_QWORD *)&v23 = wil::details::g_pfnGetModuleName(v13);
  else
    *(_QWORD *)&v23 = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(v16);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(v16, v26, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(v16);
  if ( wil::details::g_pfnOriginateCallback && (v16[0] & 0x200000000LL) == 0 )
    wil::details::g_pfnOriginateCallback(v16);
  if ( SLODWORD(v16[1]) >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v13);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v15 = !IsDebuggerPresent())
      : (v15 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v13) == 0),
        v15)
    || (v16[0] & 0x200000000LL) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(v16, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(v16, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)v16, v14);
    OutputDebugStringW(OutputString);
  }
  if ( ((v16[0] & 0x400000000LL) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v13);
  if ( (v16[0] & 0x100000000LL) != 0 )
    wil::details::WilFailFast((wil::details *)v16, v12);
}

```

## disassembly

```asm
0x180425180  mov     [rsp-8+arg_18], r9
0x180425185  mov     [rsp-8+arg_10], r8
0x18042518a  mov     [rsp-8+arg_8], edx
0x18042518e  mov     [rsp-8+arg_0], rcx
0x180425193  push    rbp
0x180425194  push    rbx
0x180425195  push    rsi
0x180425196  push    rdi
0x180425197  push    r14
0x180425199  push    r15
0x18042519b  lea     rbp, [rsp-13E8h]
0x1804251a3  mov     eax, 14E8h
0x1804251a8  call    _alloca_probe
0x1804251ad  sub     rsp, rax
0x1804251b0  mov     [rbp+1410h+var_1450], 0FFFFFFFFFFFFFFFEh
0x1804251b8  mov     rax, cs:__security_cookie
0x1804251bf  xor     rax, rsp
0x1804251c2  mov     [rbp+1410h+var_40], rax
0x1804251c9  mov     r14, [rbp+1410h+arg_0]
0x1804251d0  mov     edi, [rbp+1410h+arg_8]
0x1804251d6  mov     rsi, [rbp+1410h+arg_28]
0x1804251dd  xorps   xmm0, xmm0
0x1804251e0  xor     eax, eax
0x1804251e2  movups  xmmword ptr [rsp+1510h+var_14F0], xmm0
0x1804251e7  movups  [rsp+1510h+var_14E0], xmm0
0x1804251ec  movups  [rsp+1510h+var_14D0], xmm0
0x1804251f1  movups  [rsp+1510h+var_14C0], xmm0
0x1804251f6  movups  [rsp+1510h+var_14B0], xmm0
0x1804251fb  movups  [rsp+1510h+var_14A0], xmm0
0x180425200  movups  [rbp+1410h+var_1490], xmm0
0x180425204  movups  [rbp+1410h+var_1480], xmm0
0x180425208  movups  [rbp+1410h+var_1470], xmm0
0x18042520c  mov     [rbp+1410h+var_1460], rax
0x180425210  xor     r15d, r15d
0x180425213  mov     [rbp+1410h+OutputString], r15w
0x18042521b  mov     [rbp+1410h+var_1440], r15b
0x18042521f  mov     r8, [rbp+1410h+arg_30]
0x180425226  mov     ecx, [r8]; this
0x180425229  mov     dword ptr [rsp+1510h+var_14F0+8], ecx
0x18042522d  mov     eax, [r8+4]
0x180425231  mov     dword ptr [rsp+1510h+var_14F0+0Ch], eax
0x180425235  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18042523a  mov     ebx, eax
0x18042523c  mov     edx, 1
0x180425241  mov     dword ptr [rsp+1510h+var_14F0], edx
0x180425245  mov     ecx, r15d
0x180425248  mov     eax, 8
0x18042524d  cmp     [r8+8], edx
0x180425251  cmovz   ecx, eax
0x180425254  mov     dword ptr [rsp+1510h+var_14F0+4], ecx
0x180425258  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, edx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180425260  inc     edx
0x180425262  mov     dword ptr [rsp+1510h+var_14E0], edx
0x180425266  mov     qword ptr [rsp+1510h+var_14E0+8], r15
0x18042526b  call    cs:__imp_GetCurrentThreadId
0x180425272  nop     dword ptr [rax+rax+00h]
0x180425277  mov     dword ptr [rsp+1510h+var_14D0], eax
0x18042527b  lea     rax, aWil; "wil"
0x180425282  mov     qword ptr [rsp+1510h+var_14C0+8], rax
0x180425287  mov     dword ptr [rsp+1510h+var_14B0], edi
0x18042528b  mov     dword ptr [rsp+1510h+var_14B0+4], ebx
0x18042528f  mov     qword ptr [rsp+1510h+var_14D0+8], r15
0x180425294  mov     qword ptr [rsp+1510h+var_14C0], r15
0x180425299  mov     qword ptr [rbp+1410h+var_1470+8], rsi
0x18042529d  mov     [rbp+1410h+var_1460], r14
0x1804252a1  mov     qword ptr [rsp+1510h+var_14B0+8], r15
0x1804252a6  xorps   xmm0, xmm0
0x1804252a9  xor     eax, eax
0x1804252ab  movups  [rbp+1410h+var_1490+8], xmm0
0x1804252af  mov     qword ptr [rbp+1410h+var_1480+8], rax
0x1804252b3  xorps   xmm1, xmm1
0x1804252b6  movups  [rsp+1510h+var_14A0], xmm1
0x1804252bb  mov     qword ptr [rbp+1410h+var_1490], rax
0x1804252bf  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1804252c6  test    rax, rax
0x1804252c9  jz      short loc_1804252D6
0x1804252cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1804252d0  mov     qword ptr [rbp+1410h+var_1470], rax
0x1804252d4  jmp     short loc_1804252DA
0x1804252d6  mov     qword ptr [rbp+1410h+var_1470], r15
0x1804252da  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1804252e1  test    rax, rax
0x1804252e4  jz      short loc_1804252F0
0x1804252e6  lea     rcx, [rsp+1510h+var_14F0]
0x1804252eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1804252f0  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1804252f7  test    rax, rax
0x1804252fa  jz      short loc_180425310
0x1804252fc  mov     r8d, 400h
0x180425302  lea     rdx, [rbp+1410h+var_1440]
0x180425306  lea     rcx, [rsp+1510h+var_14F0]
0x18042530b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180425310  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180425317  test    rax, rax
0x18042531a  jz      short loc_180425326
0x18042531c  lea     rcx, [rsp+1510h+var_14F0]
0x180425321  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180425326  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18042532d  test    rax, rax
0x180425330  jz      short loc_180425343
0x180425332  test    byte ptr [rsp+1510h+var_14F0+4], 2
0x180425337  jnz     short loc_180425343
0x180425339  lea     rcx, [rsp+1510h+var_14F0]
0x18042533e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180425343  cmp     dword ptr [rsp+1510h+var_14F0+8], r15d
0x180425348  jge     loc_18042545C
0x18042534e  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x180425355  jnz     short loc_18042537C
0x180425357  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18042535e  test    rax, rax
0x180425361  jz      short loc_18042536C
0x180425363  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180425368  test    al, al
0x18042536a  jmp     short loc_18042537A
0x18042536c  call    cs:__imp_IsDebuggerPresent
0x180425373  nop     dword ptr [rax+rax+00h]
0x180425378  test    eax, eax
0x18042537a  jz      short loc_180425383
0x18042537c  test    byte ptr [rsp+1510h+var_14F0+4], 2
0x180425381  jz      short loc_1804253A9
0x180425383  mov     rax, cs:g_pfnResultLoggingCallback
0x18042538a  test    rax, rax
0x18042538d  jz      short loc_180425408
0x18042538f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180425396  jnz     short loc_180425408
0x180425398  xor     r8d, r8d
0x18042539b  xor     edx, edx
0x18042539d  lea     rcx, [rsp+1510h+var_14F0]
0x1804253a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1804253a7  jmp     short loc_180425408
0x1804253a9  mov     rax, cs:g_pfnResultLoggingCallback
0x1804253b0  test    rax, rax
0x1804253b3  jz      short loc_1804253D5
0x1804253b5  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1804253bc  jnz     short loc_1804253D5
0x1804253be  mov     r8d, 800h
0x1804253c4  lea     rdx, [rbp+1410h+OutputString]
0x1804253cb  lea     rcx, [rsp+1510h+var_14F0]
0x1804253d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1804253d5  cmp     [rbp+1410h+OutputString], r15w
0x1804253dd  jnz     short loc_1804253F5
0x1804253df  lea     r8, [rsp+1510h+var_14F0]; unsigned __int64
0x1804253e4  mov     edx, 800h; unsigned __int16 *
0x1804253e9  lea     rcx, [rbp+1410h+OutputString]; this
0x1804253f0  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1804253f5  lea     rcx, [rbp+1410h+OutputString]; lpOutputString
0x1804253fc  call    cs:__imp_OutputDebugStringW
0x180425403  nop     dword ptr [rax+rax+00h]
0x180425408  test    byte ptr [rsp+1510h+var_14F0+4], 4
0x18042540d  jnz     short loc_180425418
0x18042540f  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x180425416  jz      short loc_18042542A
0x180425418  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18042541f  test    rax, rax
0x180425422  jz      short loc_18042542A
0x180425424  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180425429  nop
0x18042542a  test    byte ptr [rsp+1510h+var_14F0+4], 1
0x18042542f  jnz     short loc_180425451
0x180425431  mov     rcx, [rbp+1410h+var_40]
0x180425438  xor     rcx, rsp; StackCookie
0x18042543b  call    __security_check_cookie
0x180425440  add     rsp, 14E8h
0x180425447  pop     r15
0x180425449  pop     r14
0x18042544b  pop     rdi
0x18042544c  pop     rsi
0x18042544d  pop     rbx
0x18042544e  pop     rbp
0x18042544f  retn
0x180425451  lea     rcx, [rsp+1510h+var_14F0]; this
0x180425456  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18042545c  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
