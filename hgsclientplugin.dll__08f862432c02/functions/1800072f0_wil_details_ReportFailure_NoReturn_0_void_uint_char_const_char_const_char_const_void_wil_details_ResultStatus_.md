# wil::details::ReportFailure_NoReturn<0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions)

- ea: `0x1800072f0`
- end: `0x1800075b5`
- name: `??$ReportFailure_NoReturn@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@@Z`
- size: `709`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180007048`

## callees

- `0x180001f9e`
- `0x180003784`
- `0x180004674`
- `0x18000540c`
- `0x180005740`
- `0x18000581c`
- `0x1800072f0`
- `0x18000a850`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800073b1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800073b1`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180007549`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180007549`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800074ad`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800074ad`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<0>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7,
        _WORD *a8)
{
  bool v11; // di
  int v12; // r12d
  int v13; // ecx
  __int64 v14; // rdx
  const struct wil::FailureInfo *v15; // rdx
  wil::details::in1diag3 *v16; // rcx
  const struct wil::FailureInfo *v17; // r9
  bool v18; // zf
  char v19; // bl
  const struct wil::FailureInfo *v20; // rdx
  int v21; // [rsp+20h] [rbp-E0h] BYREF
  int v22; // [rsp+24h] [rbp-DCh]
  int v23; // [rsp+28h] [rbp-D8h]
  int v24; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v25; // [rsp+30h] [rbp-D0h]
  _WORD *v26; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v28; // [rsp+48h] [rbp-B8h]
  __int64 v29; // [rsp+50h] [rbp-B0h]
  __int64 v30; // [rsp+58h] [rbp-A8h]
  int v31; // [rsp+60h] [rbp-A0h]
  int v32; // [rsp+64h] [rbp-9Ch]
  __int64 v33; // [rsp+68h] [rbp-98h]
  __int128 v34; // [rsp+70h] [rbp-90h]
  __int64 v35; // [rsp+80h] [rbp-80h]
  __int128 v36; // [rsp+88h] [rbp-78h]
  __int64 v37; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v39; // [rsp+A8h] [rbp-58h]
  __int64 v40; // [rsp+B0h] [rbp-50h]
  char v41[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2072]; // [rsp+4C0h] [rbp+3C0h] BYREF

  v11 = g_pfnThrowPlatformException != 0;
  memset_0(&v21, 0, 0x98u);
  OutputString[0] = 0;
  v41[0] = 0;
  v23 = *a7;
  v24 = a7[1];
  v12 = wil::details::RecordException((wil::details *)(unsigned int)v23, (int)a7);
  v21 = 0;
  v13 = 0;
  if ( *(_DWORD *)(v14 + 8) == 1 )
    v13 = 8;
  v22 = v13;
  v25 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  if ( !a8 || (v18 = *a8 == 0, v26 = a8, v18) )
    v26 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v30 = a3;
  v31 = a2;
  v32 = v12;
  v28 = 0;
  v29 = 0;
  v39 = a6;
  v40 = a1;
  v33 = 0;
  v36 = 0;
  v37 = 0;
  v34 = 0;
  v35 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v16);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v21);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v21, v41, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v21);
  if ( wil::details::g_pfnOriginateCallback && !v11 && (v22 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v21);
  if ( v23 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v16);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v18 = !IsDebuggerPresent())
      : (v18 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v16) == 0),
        v18)
    || (v19 = 1, (v22 & 2) != 0) )
  {
    v19 = 0;
  }
  if ( v11 || v19 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v21, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (wchar_t *)0x800, (unsigned __int64)&v21, v17);
    if ( v19 )
      OutputDebugStringW(OutputString);
  }
  else if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
  {
    g_pfnResultLoggingCallback(&v21, 0, 0);
  }
  if ( ((v22 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v16);
  if ( (v22 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v21, v15);
  if ( v11 )
    ((void (__fastcall *)(int *, WCHAR *))g_pfnThrowPlatformException)(&v21, OutputString);
  wil::ThrowResultException((wil *)&v21, v15);
  wil::details::WilFailFast((wil::details *)&v21, v20);
}

```

## disassembly

```asm
0x1800072f0  mov     [rsp-8+arg_18], rbx
0x1800072f5  push    rbp
0x1800072f6  push    rsi
0x1800072f7  push    rdi
0x1800072f8  push    r12
0x1800072fa  push    r13
0x1800072fc  push    r14
0x1800072fe  push    r15
0x180007300  lea     rbp, [rsp-13C0h]
0x180007308  mov     eax, 14C0h
0x18000730d  call    _alloca_probe
0x180007312  sub     rsp, rax
0x180007315  mov     r14, r8
0x180007318  mov     esi, edx
0x18000731a  mov     rbx, rcx
0x18000731d  mov     r15, [rbp+13F0h+arg_28]
0x180007324  xor     r13d, r13d
0x180007327  cmp     cs:g_pfnThrowPlatformException, r13
0x18000732e  setnz   dil
0x180007332  xor     edx, edx; Val
0x180007334  mov     r8d, 98h; Size
0x18000733a  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x18000733f  call    memset_0
0x180007344  nop
0x180007345  mov     [rbp+13F0h+OutputString], r13w
0x18000734d  mov     [rbp+13F0h+var_1430], r13b
0x180007351  mov     rdx, [rbp+13F0h+arg_30]; int
0x180007358  mov     ecx, [rdx]; this
0x18000735a  mov     [rsp+14F0h+var_14C8], ecx
0x18000735e  mov     eax, [rdx+4]
0x180007361  mov     [rsp+14F0h+var_14C4], eax
0x180007365  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000736a  mov     r12d, eax
0x18000736d  mov     dword ptr [rsp+14F0h+var_14D0], r13d
0x180007372  mov     ecx, r13d
0x180007375  lea     eax, [r13+8]
0x180007379  cmp     dword ptr [rdx+8], 1
0x18000737d  cmovz   ecx, eax
0x180007380  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180007384  lea     ecx, [rax-7]
0x180007387  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000738f  inc     ecx
0x180007391  mov     [rsp+14F0h+var_14C0], ecx
0x180007395  mov     rcx, [rbp+13F0h+arg_38]
0x18000739c  test    rcx, rcx
0x18000739f  jz      short loc_1800073AC
0x1800073a1  cmp     [rcx], r13w
0x1800073a5  mov     [rsp+14F0h+var_14B8], rcx
0x1800073aa  jnz     short loc_1800073B1
0x1800073ac  mov     [rsp+14F0h+var_14B8], r13
0x1800073b1  call    cs:__imp_GetCurrentThreadId
0x1800073b7  mov     [rsp+14F0h+var_14B0], eax
0x1800073bb  mov     [rsp+14F0h+var_1498], r14
0x1800073c0  mov     [rsp+14F0h+var_1490], esi
0x1800073c4  mov     [rsp+14F0h+var_148C], r12d
0x1800073c9  mov     [rsp+14F0h+var_14A8], r13
0x1800073ce  mov     [rsp+14F0h+var_14A0], r13
0x1800073d3  mov     [rbp+13F0h+var_1448], r15
0x1800073d7  mov     [rbp+13F0h+var_1440], rbx
0x1800073db  mov     [rsp+14F0h+var_1488], r13
0x1800073e0  xorps   xmm0, xmm0
0x1800073e3  xor     eax, eax
0x1800073e5  movups  [rbp+13F0h+var_1468], xmm0
0x1800073e9  mov     [rbp+13F0h+var_1458], rax
0x1800073ed  xorps   xmm1, xmm1
0x1800073f0  movups  [rsp+14F0h+var_1480], xmm1
0x1800073f5  mov     [rbp+13F0h+var_1470], rax
0x1800073f9  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180007400  test    rax, rax
0x180007403  jz      short loc_180007410
0x180007405  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000740a  mov     [rbp+13F0h+var_1450], rax
0x18000740e  jmp     short loc_180007414
0x180007410  mov     [rbp+13F0h+var_1450], r13
0x180007414  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000741b  test    rax, rax
0x18000741e  jz      short loc_18000742A
0x180007420  lea     rcx, [rsp+14F0h+var_14D0]
0x180007425  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000742a  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180007431  test    rax, rax
0x180007434  jz      short loc_18000744A
0x180007436  mov     r8d, 400h
0x18000743c  lea     rdx, [rbp+13F0h+var_1430]
0x180007440  lea     rcx, [rsp+14F0h+var_14D0]
0x180007445  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000744a  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180007451  test    rax, rax
0x180007454  jz      short loc_180007460
0x180007456  lea     rcx, [rsp+14F0h+var_14D0]
0x18000745b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007460  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180007467  test    rax, rax
0x18000746a  jz      short loc_180007482
0x18000746c  test    dil, dil
0x18000746f  jnz     short loc_180007482
0x180007471  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180007476  jnz     short loc_180007482
0x180007478  lea     rcx, [rsp+14F0h+var_14D0]
0x18000747d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007482  cmp     [rsp+14F0h+var_14C8], r13d
0x180007487  jl      short loc_18000748F
0x180007489  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000748f  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x180007496  jnz     short loc_1800074B7
0x180007498  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000749f  test    rax, rax
0x1800074a2  jz      short loc_1800074AD
0x1800074a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800074a9  test    al, al
0x1800074ab  jmp     short loc_1800074B5
0x1800074ad  call    cs:__imp_IsDebuggerPresent
0x1800074b3  test    eax, eax
0x1800074b5  jz      short loc_1800074C0
0x1800074b7  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800074bc  mov     bl, 1
0x1800074be  jz      short loc_1800074C3
0x1800074c0  mov     bl, r13b
0x1800074c3  test    dil, dil
0x1800074c6  jnz     short loc_1800074F2
0x1800074c8  test    bl, bl
0x1800074ca  jnz     short loc_1800074F2
0x1800074cc  mov     rax, cs:g_pfnResultLoggingCallback
0x1800074d3  test    rax, rax
0x1800074d6  jz      short loc_18000754F
0x1800074d8  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x1800074df  jnz     short loc_18000754F
0x1800074e1  xor     r8d, r8d
0x1800074e4  xor     edx, edx
0x1800074e6  lea     rcx, [rsp+14F0h+var_14D0]
0x1800074eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800074f0  jmp     short loc_18000754F
0x1800074f2  mov     esi, 800h
0x1800074f7  mov     rax, cs:g_pfnResultLoggingCallback
0x1800074fe  test    rax, rax
0x180007501  jz      short loc_180007520
0x180007503  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x18000750a  jnz     short loc_180007520
0x18000750c  mov     r8d, esi
0x18000750f  lea     rdx, [rbp+13F0h+OutputString]
0x180007516  lea     rcx, [rsp+14F0h+var_14D0]
0x18000751b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007520  cmp     [rbp+13F0h+OutputString], r13w
0x180007528  jnz     short loc_18000753E
0x18000752a  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x18000752f  mov     rdx, rsi; wchar_t *
0x180007532  lea     rcx, [rbp+13F0h+OutputString]; this
0x180007539  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x18000753e  test    bl, bl
0x180007540  jz      short loc_18000754F
0x180007542  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180007549  call    cs:__imp_OutputDebugStringW
0x18000754f  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180007554  jnz     short loc_18000755F
0x180007556  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x18000755d  jz      short loc_180007571
0x18000755f  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180007566  test    rax, rax
0x180007569  jz      short loc_180007571
0x18000756b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007570  nop
0x180007571  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x180007576  jz      short loc_180007583
0x180007578  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000757d  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180007583  test    dil, dil
0x180007586  jz      short loc_1800075A0
0x180007588  lea     rdx, [rbp+13F0h+OutputString]
0x18000758f  lea     rcx, [rsp+14F0h+var_14D0]
0x180007594  mov     rax, cs:g_pfnThrowPlatformException
0x18000759b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800075a0  lea     rcx, [rsp+14F0h+var_14D0]; this
0x1800075a5  call    ?ThrowResultException@wil@@YAXAEBUFailureInfo@1@@Z; wil::ThrowResultException(wil::FailureInfo const &)
0x1800075aa  lea     rcx, [rsp+14F0h+var_14D0]; this
0x1800075af  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
