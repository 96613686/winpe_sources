# wil::details::ReportFailure_NoReturn<0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions)

- ea: `0x180007de4`
- end: `0x1800080ca`
- name: `??$ReportFailure_NoReturn@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@@Z`
- size: `742`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, __int64, __int64, int *, _WORD *, char)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180007c30`

## callees

- `0x1800021f0`
- `0x180005054`
- `0x180006030`
- `0x180006474`
- `0x180006f30`
- `0x180007260`
- `0x18000733c`
- `0x180007de4`
- `0x1800151e0`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007eb8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007eb8`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180007fb8`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180007fb8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180008055`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180008055`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<0>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        int *a7,
        _WORD *a8,
        char a9)
{
  bool v12; // di
  _WORD *v13; // r8
  int v14; // r13d
  int v15; // ecx
  __int64 v16; // rdx
  const struct wil::FailureInfo *v17; // rdx
  wil::details::in1diag3 *v18; // rcx
  const struct wil::FailureInfo *v19; // r9
  bool v20; // zf
  char v21; // bl
  const struct wil::FailureInfo *v22; // rdx
  int v23; // [rsp+20h] [rbp-E0h] BYREF
  int v24; // [rsp+24h] [rbp-DCh]
  int v25; // [rsp+28h] [rbp-D8h]
  int v26; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v27; // [rsp+30h] [rbp-D0h]
  _WORD *v28; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v30; // [rsp+48h] [rbp-B8h]
  __int64 v31; // [rsp+50h] [rbp-B0h]
  __int64 v32; // [rsp+58h] [rbp-A8h]
  int v33; // [rsp+60h] [rbp-A0h]
  int v34; // [rsp+64h] [rbp-9Ch]
  __int64 v35; // [rsp+68h] [rbp-98h]
  __int128 v36; // [rsp+70h] [rbp-90h]
  __int64 v37; // [rsp+80h] [rbp-80h]
  __int128 v38; // [rsp+88h] [rbp-78h]
  __int64 v39; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v41; // [rsp+A8h] [rbp-58h]
  __int64 v42; // [rsp+B0h] [rbp-50h]
  char v43[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2072]; // [rsp+4C0h] [rbp+3C0h] BYREF

  v12 = (a9 & 2) == 0 && g_pfnThrowPlatformException;
  memset_0(&v23, 0, 0x98u);
  OutputString[0] = 0;
  v43[0] = 0;
  v25 = *a7;
  v26 = a7[1];
  v14 = wil::details::RecordException((wil::details *)(unsigned int)v25, (int)a7);
  v23 = (int)v13;
  v15 = (int)v13;
  if ( *(_DWORD *)(v16 + 8) == 1 )
    v15 = (_DWORD)v13 + 8;
  v24 = v15;
  v27 = _InterlockedExchangeAdd(&`wil::details::LogFailure'::`2'::s_failureId, (_DWORD)v13 + 1) + 1;
  if ( !a8 || (v20 = *a8 == (unsigned __int16)v13, v28 = a8, v20) )
    v28 = v13;
  CurrentThreadId = GetCurrentThreadId();
  v32 = a3;
  v33 = a2;
  v34 = v14;
  v30 = 0;
  v31 = 0;
  v41 = a6;
  v42 = a1;
  v35 = 0;
  v38 = 0;
  v39 = 0;
  v36 = 0;
  v37 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v18);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v23);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v23, v43, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v23);
  if ( wil::details::g_pfnOriginateCallback && !v12 && (v24 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v23);
  if ( v25 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v18);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v20 = !IsDebuggerPresent())
      : (v20 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v18) == 0),
        v20)
    || (v21 = 1, (v24 & 2) != 0) )
  {
    v21 = 0;
  }
  if ( v12 || v21 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v23, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (wchar_t *)0x800, (unsigned __int64)&v23, v19);
    if ( v21 )
      OutputDebugStringW(OutputString);
  }
  else if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
  {
    g_pfnResultLoggingCallback(&v23, 0, 0);
  }
  if ( ((v24 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v18);
  if ( (v24 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v23, v17);
  if ( v12 )
    ((void (__fastcall *)(int *, WCHAR *))g_pfnThrowPlatformException)(&v23, OutputString);
  if ( (a9 & 2) != 0 )
    wil::RethrowCaughtException(v18);
  wil::ThrowResultException((wil *)&v23, v17);
  wil::details::WilFailFast((wil::details *)&v23, v22);
}

```

## disassembly

```asm
0x180007de4  mov     [rsp-8+arg_18], rbx
0x180007de9  push    rbp
0x180007dea  push    rsi
0x180007deb  push    rdi
0x180007dec  push    r12
0x180007dee  push    r13
0x180007df0  push    r14
0x180007df2  push    r15
0x180007df4  lea     rbp, [rsp-13C0h]
0x180007dfc  mov     eax, 14C0h
0x180007e01  call    _alloca_probe
0x180007e06  sub     rsp, rax
0x180007e09  mov     r15, r8
0x180007e0c  mov     r14d, edx
0x180007e0f  mov     rbx, rcx
0x180007e12  mov     r12, [rbp+13F0h+arg_28]
0x180007e19  mov     esi, [rbp+13F0h+arg_40]
0x180007e1f  and     esi, 2
0x180007e22  jnz     short loc_180007E33
0x180007e24  cmp     cs:g_pfnThrowPlatformException, 0
0x180007e2c  jz      short loc_180007E33
0x180007e2e  mov     dil, 1
0x180007e31  jmp     short loc_180007E36
0x180007e33  xor     dil, dil
0x180007e36  xor     edx, edx; Val
0x180007e38  mov     r8d, 98h; Size
0x180007e3e  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180007e43  call    memset_0
0x180007e48  nop
0x180007e49  xor     r8d, r8d
0x180007e4c  mov     [rbp+13F0h+OutputString], r8w
0x180007e54  mov     [rbp+13F0h+var_1430], r8b
0x180007e58  mov     rdx, [rbp+13F0h+arg_30]; int
0x180007e5f  mov     ecx, [rdx]; this
0x180007e61  mov     [rsp+14F0h+var_14C8], ecx
0x180007e65  mov     eax, [rdx+4]
0x180007e68  mov     [rsp+14F0h+var_14C4], eax
0x180007e6c  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180007e71  mov     r13d, eax
0x180007e74  mov     dword ptr [rsp+14F0h+var_14D0], r8d
0x180007e79  mov     ecx, r8d
0x180007e7c  lea     eax, [r8+8]
0x180007e80  cmp     dword ptr [rdx+8], 1
0x180007e84  cmovz   ecx, eax
0x180007e87  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180007e8b  lea     ecx, [rax-7]
0x180007e8e  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180007e96  inc     ecx
0x180007e98  mov     [rsp+14F0h+var_14C0], ecx
0x180007e9c  mov     rcx, [rbp+13F0h+arg_38]
0x180007ea3  test    rcx, rcx
0x180007ea6  jz      short loc_180007EB3
0x180007ea8  cmp     [rcx], r8w
0x180007eac  mov     [rsp+14F0h+var_14B8], rcx
0x180007eb1  jnz     short loc_180007EB8
0x180007eb3  mov     [rsp+14F0h+var_14B8], r8
0x180007eb8  call    cs:__imp_GetCurrentThreadId
0x180007ebe  mov     [rsp+14F0h+var_14B0], eax
0x180007ec2  mov     [rsp+14F0h+var_1498], r15
0x180007ec7  mov     [rsp+14F0h+var_1490], r14d
0x180007ecc  mov     [rsp+14F0h+var_148C], r13d
0x180007ed1  xor     r14d, r14d
0x180007ed4  mov     [rsp+14F0h+var_14A8], r14
0x180007ed9  mov     [rsp+14F0h+var_14A0], r14
0x180007ede  mov     [rbp+13F0h+var_1448], r12
0x180007ee2  mov     [rbp+13F0h+var_1440], rbx
0x180007ee6  mov     [rsp+14F0h+var_1488], r14
0x180007eeb  xorps   xmm0, xmm0
0x180007eee  xor     eax, eax
0x180007ef0  movups  [rbp+13F0h+var_1468], xmm0
0x180007ef4  mov     [rbp+13F0h+var_1458], rax
0x180007ef8  xorps   xmm1, xmm1
0x180007efb  movups  [rsp+14F0h+var_1480], xmm1
0x180007f00  mov     [rbp+13F0h+var_1470], rax
0x180007f04  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180007f0b  test    rax, rax
0x180007f0e  jz      short loc_180007F1B
0x180007f10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f15  mov     [rbp+13F0h+var_1450], rax
0x180007f19  jmp     short loc_180007F1F
0x180007f1b  mov     [rbp+13F0h+var_1450], r14
0x180007f1f  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180007f26  test    rax, rax
0x180007f29  jz      short loc_180007F35
0x180007f2b  lea     rcx, [rsp+14F0h+var_14D0]
0x180007f30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f35  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180007f3c  test    rax, rax
0x180007f3f  jz      short loc_180007F55
0x180007f41  mov     r8d, 400h
0x180007f47  lea     rdx, [rbp+13F0h+var_1430]
0x180007f4b  lea     rcx, [rsp+14F0h+var_14D0]
0x180007f50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f55  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180007f5c  test    rax, rax
0x180007f5f  jz      short loc_180007F6B
0x180007f61  lea     rcx, [rsp+14F0h+var_14D0]
0x180007f66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f6b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180007f72  test    rax, rax
0x180007f75  jz      short loc_180007F8D
0x180007f77  test    dil, dil
0x180007f7a  jnz     short loc_180007F8D
0x180007f7c  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180007f81  jnz     short loc_180007F8D
0x180007f83  lea     rcx, [rsp+14F0h+var_14D0]
0x180007f88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f8d  cmp     [rsp+14F0h+var_14C8], r14d
0x180007f92  jl      short loc_180007F9A
0x180007f94  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180007f9a  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r14b; bool wil::g_fIsDebuggerPresent
0x180007fa1  jnz     short loc_180007FC2
0x180007fa3  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180007faa  test    rax, rax
0x180007fad  jz      short loc_180007FB8
0x180007faf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007fb4  test    al, al
0x180007fb6  jmp     short loc_180007FC0
0x180007fb8  call    cs:__imp_IsDebuggerPresent
0x180007fbe  test    eax, eax
0x180007fc0  jz      short loc_180007FCB
0x180007fc2  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180007fc7  mov     bl, 1
0x180007fc9  jz      short loc_180007FCE
0x180007fcb  mov     bl, r14b
0x180007fce  test    dil, dil
0x180007fd1  jnz     short loc_180007FFD
0x180007fd3  test    bl, bl
0x180007fd5  jnz     short loc_180007FFD
0x180007fd7  mov     rax, cs:g_pfnResultLoggingCallback
0x180007fde  test    rax, rax
0x180007fe1  jz      short loc_18000805B
0x180007fe3  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r14b; bool wil::details::g_resultMessageCallbackSet
0x180007fea  jnz     short loc_18000805B
0x180007fec  xor     r8d, r8d
0x180007fef  xor     edx, edx
0x180007ff1  lea     rcx, [rsp+14F0h+var_14D0]
0x180007ff6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ffb  jmp     short loc_18000805B
0x180007ffd  mov     r15d, 800h
0x180008003  mov     rax, cs:g_pfnResultLoggingCallback
0x18000800a  test    rax, rax
0x18000800d  jz      short loc_18000802C
0x18000800f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r14b; bool wil::details::g_resultMessageCallbackSet
0x180008016  jnz     short loc_18000802C
0x180008018  mov     r8d, r15d
0x18000801b  lea     rdx, [rbp+13F0h+OutputString]
0x180008022  lea     rcx, [rsp+14F0h+var_14D0]
0x180008027  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000802c  cmp     [rbp+13F0h+OutputString], r14w
0x180008034  jnz     short loc_18000804A
0x180008036  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x18000803b  mov     rdx, r15; wchar_t *
0x18000803e  lea     rcx, [rbp+13F0h+OutputString]; this
0x180008045  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x18000804a  test    bl, bl
0x18000804c  jz      short loc_18000805B
0x18000804e  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180008055  call    cs:__imp_OutputDebugStringW
0x18000805b  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180008060  jnz     short loc_18000806B
0x180008062  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r14b; bool wil::g_fBreakOnFailure
0x180008069  jz      short loc_18000807D
0x18000806b  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180008072  test    rax, rax
0x180008075  jz      short loc_18000807D
0x180008077  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000807c  nop
0x18000807d  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x180008082  jz      short loc_18000808F
0x180008084  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180008089  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18000808f  test    dil, dil
0x180008092  jz      short loc_1800080AC
0x180008094  lea     rdx, [rbp+13F0h+OutputString]
0x18000809b  lea     rcx, [rsp+14F0h+var_14D0]
0x1800080a0  mov     rax, cs:g_pfnThrowPlatformException
0x1800080a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800080ac  test    esi, esi
0x1800080ae  jz      short loc_1800080B5
0x1800080b0  call    ?RethrowCaughtException@wil@@YAXXZ; wil::RethrowCaughtException(void)
0x1800080b5  lea     rcx, [rsp+14F0h+var_14D0]; this
0x1800080ba  call    ?ThrowResultException@wil@@YAXAEBUFailureInfo@1@@Z; wil::ThrowResultException(wil::FailureInfo const &)
0x1800080bf  lea     rcx, [rsp+14F0h+var_14D0]; this
0x1800080c4  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
