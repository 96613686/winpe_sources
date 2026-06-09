# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x1800031ec`
- end: `0x180003480`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `660`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180002ec0`

## callees

- `0x1800031ec`
- `0x180004284`
- `0x180005620`
- `0x180006e78`
- `0x180007074`
- `0x18001abfa`
- `0x18001ac90`
- `0x18001acc0`
- `0x18001c010`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x180003391`
- `KERNEL32!IsDebuggerPresent` at `0x180003391`
- `KERNEL32!GetCurrentThreadId` at `0x180003296`
- `KERNEL32!GetCurrentThreadId` at `0x180003296`
- `KERNEL32!OutputDebugStringW` at `0x18000341b`
- `KERNEL32!OutputDebugStringW` at `0x18000341b`

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
  int v9; // eax
  int v10; // eax
  __int64 v11; // rdx
  int v12; // ebx
  int v13; // ecx
  DWORD CurrentThreadId; // eax
  const struct wil::FailureInfo *v15; // rdx
  wil::details::in1diag3 *v16; // rcx
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
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v19, 0, 0x98u);
  OutputString[0] = 0;
  v39[0] = 0;
  v9 = a7[1];
  v21 = *a7;
  v22 = v9;
  v10 = wil::details::RecordReturn((wil::details *)(unsigned int)v21, (int)a7);
  v18 = *(_DWORD *)(v11 + 8) == 1;
  v12 = v10;
  v19 = 1;
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
  v28 = "wil";
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
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v16);
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
  if ( ((v20 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v16);
  if ( (v20 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v19, v15);
}

```

## disassembly

```asm
0x1800031ec  mov     [rsp-8+arg_10], rbx
0x1800031f1  push    rbp
0x1800031f2  push    rsi
0x1800031f3  push    rdi
0x1800031f4  push    r14
0x1800031f6  push    r15
0x1800031f8  lea     rbp, [rsp-13D0h]
0x180003200  mov     eax, 14D0h
0x180003205  call    _alloca_probe
0x18000320a  sub     rsp, rax
0x18000320d  mov     rax, cs:__security_cookie
0x180003214  xor     rax, rsp
0x180003217  mov     [rbp+13F0h+var_30], rax
0x18000321e  mov     rdi, [rbp+13F0h+arg_28]
0x180003225  mov     esi, edx
0x180003227  mov     r14, rcx
0x18000322a  xor     edx, edx; Val
0x18000322c  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180003231  mov     r8d, 98h; Size
0x180003237  call    memset_0
0x18000323c  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x180003243  xor     r15d, r15d
0x180003246  mov     [rbp+13F0h+OutputString], r15w
0x18000324e  mov     [rbp+13F0h+var_1430], r15b
0x180003252  mov     ecx, [rdx]; this
0x180003254  mov     eax, [rdx+4]
0x180003257  mov     [rsp+14F0h+var_14C8], ecx
0x18000325b  mov     [rsp+14F0h+var_14C4], eax
0x18000325f  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180003264  cmp     dword ptr [rdx+8], 1
0x180003268  mov     ebx, eax
0x18000326a  lea     eax, [r15+8]
0x18000326e  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x180003276  mov     ecx, r15d
0x180003279  cmovz   ecx, eax
0x18000327c  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180003280  lea     ecx, [rax-7]
0x180003283  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000328b  inc     ecx
0x18000328d  mov     [rsp+14F0h+var_14B8], r15
0x180003292  mov     [rsp+14F0h+var_14C0], ecx
0x180003296  call    cs:__imp_GetCurrentThreadId
0x18000329c  xorps   xmm0, xmm0
0x18000329f  mov     [rsp+14F0h+var_1490], esi
0x1800032a3  mov     [rsp+14F0h+var_14B0], eax
0x1800032a7  xorps   xmm1, xmm1
0x1800032aa  lea     rax, aWil; "wil"
0x1800032b1  mov     [rsp+14F0h+var_148C], ebx
0x1800032b5  mov     [rsp+14F0h+var_1498], rax
0x1800032ba  xor     eax, eax
0x1800032bc  mov     [rbp+13F0h+var_1458], rax
0x1800032c0  mov     [rbp+13F0h+var_1470], rax
0x1800032c4  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800032cb  mov     [rsp+14F0h+var_14A8], r15
0x1800032d0  mov     [rsp+14F0h+var_14A0], r15
0x1800032d5  mov     [rbp+13F0h+var_1448], rdi
0x1800032d9  mov     [rbp+13F0h+var_1440], r14
0x1800032dd  mov     [rsp+14F0h+var_1488], r15
0x1800032e2  movups  [rbp+13F0h+var_1468], xmm0
0x1800032e6  movups  [rsp+14F0h+var_1480], xmm1
0x1800032eb  test    rax, rax
0x1800032ee  jz      short loc_1800032FB
0x1800032f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800032f5  mov     [rbp+13F0h+var_1450], rax
0x1800032f9  jmp     short loc_1800032FF
0x1800032fb  mov     [rbp+13F0h+var_1450], r15
0x1800032ff  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180003306  test    rax, rax
0x180003309  jz      short loc_180003315
0x18000330b  lea     rcx, [rsp+14F0h+var_14D0]
0x180003310  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003315  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000331c  test    rax, rax
0x18000331f  jz      short loc_180003335
0x180003321  mov     r8d, 400h
0x180003327  lea     rdx, [rbp+13F0h+var_1430]
0x18000332b  lea     rcx, [rsp+14F0h+var_14D0]
0x180003330  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003335  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000333c  test    rax, rax
0x18000333f  jz      short loc_18000334B
0x180003341  lea     rcx, [rsp+14F0h+var_14D0]
0x180003346  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000334b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003352  test    rax, rax
0x180003355  jz      short loc_180003368
0x180003357  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000335c  jnz     short loc_180003368
0x18000335e  lea     rcx, [rsp+14F0h+var_14D0]
0x180003363  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003368  cmp     [rsp+14F0h+var_14C8], r15d
0x18000336d  jge     loc_18000346F
0x180003373  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x18000337a  jnz     short loc_18000339B
0x18000337c  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180003383  test    rax, rax
0x180003386  jz      short loc_180003391
0x180003388  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000338d  test    al, al
0x18000338f  jmp     short loc_180003399
0x180003391  call    cs:__imp_IsDebuggerPresent
0x180003397  test    eax, eax
0x180003399  jz      short loc_1800033A2
0x18000339b  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800033a0  jz      short loc_1800033C8
0x1800033a2  mov     rax, cs:g_pfnResultLoggingCallback
0x1800033a9  test    rax, rax
0x1800033ac  jz      short loc_180003421
0x1800033ae  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800033b5  jnz     short loc_180003421
0x1800033b7  xor     r8d, r8d
0x1800033ba  lea     rcx, [rsp+14F0h+var_14D0]
0x1800033bf  xor     edx, edx
0x1800033c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800033c6  jmp     short loc_180003421
0x1800033c8  mov     rax, cs:g_pfnResultLoggingCallback
0x1800033cf  mov     ebx, 800h
0x1800033d4  test    rax, rax
0x1800033d7  jz      short loc_1800033F6
0x1800033d9  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800033e0  jnz     short loc_1800033F6
0x1800033e2  mov     r8d, ebx
0x1800033e5  lea     rdx, [rbp+13F0h+OutputString]
0x1800033ec  lea     rcx, [rsp+14F0h+var_14D0]
0x1800033f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800033f6  cmp     [rbp+13F0h+OutputString], r15w
0x1800033fe  jnz     short loc_180003414
0x180003400  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180003405  mov     rdx, rbx; unsigned __int16 *
0x180003408  lea     rcx, [rbp+13F0h+OutputString]; this
0x18000340f  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180003414  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x18000341b  call    cs:__imp_OutputDebugStringW
0x180003421  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180003426  jnz     short loc_180003431
0x180003428  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x18000342f  jz      short loc_180003442
0x180003431  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180003438  test    rax, rax
0x18000343b  jz      short loc_180003442
0x18000343d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003442  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x180003447  jnz     short loc_180003475
0x180003449  mov     rcx, [rbp+13F0h+var_30]
0x180003450  xor     rcx, rsp; StackCookie
0x180003453  call    __security_check_cookie
0x180003458  mov     rbx, [rsp+14F0h+arg_10]
0x180003460  add     rsp, 14D0h
0x180003467  pop     r15
0x180003469  pop     r14
0x18000346b  pop     rdi
0x18000346c  pop     rsi
0x18000346d  pop     rbp
0x18000346e  retn
0x18000346f  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180003475  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000347a  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
