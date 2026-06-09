# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x18000317c`
- end: `0x180003409`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `653`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180002e40`

## callees

- `0x180002100`
- `0x180002b0c`
- `0x18000317c`
- `0x180003fb4`
- `0x180005240`
- `0x180005ee8`
- `0x180005fc4`
- `0x180008fb0`
- `0x18000a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000322a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000322a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000331e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000331e`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800033a8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800033a8`

## pseudocode

```c
void __fastcall wil::details::ReportFailure_Return<1>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7)
{
  int v10; // ebx
  int v11; // ecx
  __int64 v12; // rdx
  const struct wil::FailureInfo *v13; // rdx
  wil::details::in1diag3 *v14; // rcx
  const struct wil::FailureInfo *v15; // r9
  bool v16; // zf
  int v17; // [rsp+20h] [rbp-E0h] BYREF
  int v18; // [rsp+24h] [rbp-DCh]
  int v19; // [rsp+28h] [rbp-D8h]
  int v20; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v21; // [rsp+30h] [rbp-D0h]
  __int64 v22; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v24; // [rsp+48h] [rbp-B8h]
  __int64 v25; // [rsp+50h] [rbp-B0h]
  __int64 v26; // [rsp+58h] [rbp-A8h]
  int v27; // [rsp+60h] [rbp-A0h]
  int v28; // [rsp+64h] [rbp-9Ch]
  __int64 v29; // [rsp+68h] [rbp-98h]
  __int128 v30; // [rsp+70h] [rbp-90h]
  __int64 v31; // [rsp+80h] [rbp-80h]
  __int128 v32; // [rsp+88h] [rbp-78h]
  __int64 v33; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v35; // [rsp+A8h] [rbp-58h]
  __int64 v36; // [rsp+B0h] [rbp-50h]
  char v37[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v17, 0, 0x98u);
  OutputString[0] = 0;
  v37[0] = 0;
  v19 = *a7;
  v20 = a7[1];
  v10 = wil::details::RecordReturn((wil::details *)(unsigned int)v19, (int)a7);
  v17 = 1;
  v11 = 0;
  if ( *(_DWORD *)(v12 + 8) == 1 )
    v11 = 8;
  v18 = v11;
  v21 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v22 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v26 = a3;
  v27 = a2;
  v28 = v10;
  v24 = 0;
  v25 = 0;
  v35 = a6;
  v36 = a1;
  v29 = 0;
  v32 = 0;
  v33 = 0;
  v30 = 0;
  v31 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v14);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v17);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v17, v37, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v17);
  if ( wil::details::g_pfnOriginateCallback && (v18 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v17);
  if ( v19 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v14);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v16 = !IsDebuggerPresent())
      : (v16 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v14) == 0),
        v16)
    || (v18 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v17, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v17, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v17, v15);
    OutputDebugStringW(OutputString);
  }
  if ( ((v18 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v14);
  if ( (v18 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v17, v13);
}

```

## disassembly

```asm
0x18000317c  push    rbp
0x18000317e  push    rbx
0x18000317f  push    rsi
0x180003180  push    rdi
0x180003181  push    r12
0x180003183  push    r14
0x180003185  push    r15
0x180003187  lea     rbp, [rsp-13D0h]
0x18000318f  mov     eax, 14D0h
0x180003194  call    _alloca_probe
0x180003199  sub     rsp, rax
0x18000319c  mov     rax, cs:__security_cookie
0x1800031a3  xor     rax, rsp
0x1800031a6  mov     [rbp+1400h+var_40], rax
0x1800031ad  mov     r14, r8
0x1800031b0  mov     esi, edx
0x1800031b2  mov     r15, rcx
0x1800031b5  mov     rdi, [rbp+1400h+arg_28]
0x1800031bc  xor     edx, edx; Val
0x1800031be  mov     r8d, 98h; Size
0x1800031c4  lea     rcx, [rsp+1500h+var_14E0]; void *
0x1800031c9  call    memset_0
0x1800031ce  nop
0x1800031cf  xor     r12d, r12d
0x1800031d2  mov     [rbp+1400h+OutputString], r12w
0x1800031da  mov     [rbp+1400h+var_1440], r12b
0x1800031de  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x1800031e5  mov     ecx, [rdx]; this
0x1800031e7  mov     [rsp+1500h+var_14D8], ecx
0x1800031eb  mov     eax, [rdx+4]
0x1800031ee  mov     [rsp+1500h+var_14D4], eax
0x1800031f2  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800031f7  mov     ebx, eax
0x1800031f9  mov     dword ptr [rsp+1500h+var_14E0], 1
0x180003201  mov     ecx, r12d
0x180003204  lea     eax, [r12+8]
0x180003209  cmp     dword ptr [rdx+8], 1
0x18000320d  cmovz   ecx, eax
0x180003210  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180003214  lea     ecx, [rax-7]
0x180003217  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000321f  inc     ecx
0x180003221  mov     [rsp+1500h+var_14D0], ecx
0x180003225  mov     [rsp+1500h+var_14C8], r12
0x18000322a  call    cs:__imp_GetCurrentThreadId
0x180003230  mov     [rsp+1500h+var_14C0], eax
0x180003234  mov     [rsp+1500h+var_14A8], r14
0x180003239  mov     [rsp+1500h+var_14A0], esi
0x18000323d  mov     [rsp+1500h+var_149C], ebx
0x180003241  mov     [rsp+1500h+var_14B8], r12
0x180003246  mov     [rsp+1500h+var_14B0], r12
0x18000324b  mov     [rbp+1400h+var_1458], rdi
0x18000324f  mov     [rbp+1400h+var_1450], r15
0x180003253  mov     [rsp+1500h+var_1498], r12
0x180003258  xorps   xmm0, xmm0
0x18000325b  xor     eax, eax
0x18000325d  movups  [rbp+1400h+var_1478], xmm0
0x180003261  mov     [rbp+1400h+var_1468], rax
0x180003265  xorps   xmm1, xmm1
0x180003268  movups  [rsp+1500h+var_1490], xmm1
0x18000326d  mov     [rbp+1400h+var_1480], rax
0x180003271  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180003278  test    rax, rax
0x18000327b  jz      short loc_180003288
0x18000327d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003282  mov     [rbp+1400h+var_1460], rax
0x180003286  jmp     short loc_18000328C
0x180003288  mov     [rbp+1400h+var_1460], r12
0x18000328c  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180003293  test    rax, rax
0x180003296  jz      short loc_1800032A2
0x180003298  lea     rcx, [rsp+1500h+var_14E0]
0x18000329d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800032a2  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800032a9  test    rax, rax
0x1800032ac  jz      short loc_1800032C2
0x1800032ae  mov     r8d, 400h
0x1800032b4  lea     rdx, [rbp+1400h+var_1440]
0x1800032b8  lea     rcx, [rsp+1500h+var_14E0]
0x1800032bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800032c2  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800032c9  test    rax, rax
0x1800032cc  jz      short loc_1800032D8
0x1800032ce  lea     rcx, [rsp+1500h+var_14E0]
0x1800032d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800032d8  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800032df  test    rax, rax
0x1800032e2  jz      short loc_1800032F5
0x1800032e4  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1800032e9  jnz     short loc_1800032F5
0x1800032eb  lea     rcx, [rsp+1500h+var_14E0]
0x1800032f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800032f5  cmp     [rsp+1500h+var_14D8], r12d
0x1800032fa  jge     loc_180003403
0x180003300  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180003307  jnz     short loc_180003328
0x180003309  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180003310  test    rax, rax
0x180003313  jz      short loc_18000331E
0x180003315  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000331a  test    al, al
0x18000331c  jmp     short loc_180003326
0x18000331e  call    cs:__imp_IsDebuggerPresent
0x180003324  test    eax, eax
0x180003326  jz      short loc_18000332F
0x180003328  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18000332d  jz      short loc_180003355
0x18000332f  mov     rax, cs:g_pfnResultLoggingCallback
0x180003336  test    rax, rax
0x180003339  jz      short loc_1800033AE
0x18000333b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180003342  jnz     short loc_1800033AE
0x180003344  xor     r8d, r8d
0x180003347  xor     edx, edx
0x180003349  lea     rcx, [rsp+1500h+var_14E0]
0x18000334e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003353  jmp     short loc_1800033AE
0x180003355  mov     ebx, 800h
0x18000335a  mov     rax, cs:g_pfnResultLoggingCallback
0x180003361  test    rax, rax
0x180003364  jz      short loc_180003383
0x180003366  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18000336d  jnz     short loc_180003383
0x18000336f  mov     r8d, ebx
0x180003372  lea     rdx, [rbp+1400h+OutputString]
0x180003379  lea     rcx, [rsp+1500h+var_14E0]
0x18000337e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003383  cmp     [rbp+1400h+OutputString], r12w
0x18000338b  jnz     short loc_1800033A1
0x18000338d  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180003392  mov     rdx, rbx; unsigned __int16 *
0x180003395  lea     rcx, [rbp+1400h+OutputString]; this
0x18000339c  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800033a1  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x1800033a8  call    cs:__imp_OutputDebugStringW
0x1800033ae  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x1800033b3  jnz     short loc_1800033BE
0x1800033b5  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x1800033bc  jz      short loc_1800033D0
0x1800033be  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800033c5  test    rax, rax
0x1800033c8  jz      short loc_1800033D0
0x1800033ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800033cf  nop
0x1800033d0  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x1800033d5  jnz     short loc_1800033F8
0x1800033d7  mov     rcx, [rbp+1400h+var_40]
0x1800033de  xor     rcx, rsp; StackCookie
0x1800033e1  call    __security_check_cookie
0x1800033e6  add     rsp, 14D0h
0x1800033ed  pop     r15
0x1800033ef  pop     r14
0x1800033f1  pop     r12
0x1800033f3  pop     rdi
0x1800033f4  pop     rsi
0x1800033f5  pop     rbx
0x1800033f6  pop     rbp
0x1800033f7  retn
0x1800033f8  lea     rcx, [rsp+1500h+var_14E0]; this
0x1800033fd  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180003403  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
