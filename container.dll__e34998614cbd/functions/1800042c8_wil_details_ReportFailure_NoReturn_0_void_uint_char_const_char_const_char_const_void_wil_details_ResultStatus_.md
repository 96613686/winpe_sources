# wil::details::ReportFailure_NoReturn<0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x1800042c8`
- end: `0x18000459f`
- name: `??$ReportFailure_NoReturn@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `727`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180003d1c`

## callees

- `0x18000362c`
- `0x1800042c8`
- `0x1800070f4`
- `0x180008df0`
- `0x18000b46c`
- `0x18000bb0c`
- `0x18000bd9c`
- `0x180031e00`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004389`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004389`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000448b`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000448b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000452d`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000452d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
      g_pfnResultLoggingCallback(&v21, OutputString, 2048, v17);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (__int64)&v21, v17);
    if ( v19 )
      OutputDebugStringW(OutputString);
  }
  else if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
  {
    g_pfnResultLoggingCallback(&v21, 0, 0, v17);
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
0x1800042c8  mov     [rsp-8+arg_18], rbx
0x1800042cd  push    rbp
0x1800042ce  push    rsi
0x1800042cf  push    rdi
0x1800042d0  push    r12
0x1800042d2  push    r13
0x1800042d4  push    r14
0x1800042d6  push    r15
0x1800042d8  lea     rbp, [rsp-13C0h]
0x1800042e0  mov     eax, 14C0h
0x1800042e5  call    _alloca_probe
0x1800042ea  sub     rsp, rax
0x1800042ed  mov     r14, r8
0x1800042f0  mov     esi, edx
0x1800042f2  mov     rbx, rcx
0x1800042f5  mov     r15, [rbp+13F0h+arg_28]
0x1800042fc  xor     r13d, r13d
0x1800042ff  cmp     cs:g_pfnThrowPlatformException, r13
0x180004306  setnz   dil
0x18000430a  xor     edx, edx; Val
0x18000430c  mov     r8d, 98h; Size
0x180004312  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180004317  call    memset_0
0x18000431c  nop
0x18000431d  mov     [rbp+13F0h+OutputString], r13w
0x180004325  mov     [rbp+13F0h+var_1430], r13b
0x180004329  mov     rdx, [rbp+13F0h+arg_30]; int
0x180004330  mov     ecx, [rdx]; this
0x180004332  mov     [rsp+14F0h+var_14C8], ecx
0x180004336  mov     eax, [rdx+4]
0x180004339  mov     [rsp+14F0h+var_14C4], eax
0x18000433d  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180004342  mov     r12d, eax
0x180004345  mov     dword ptr [rsp+14F0h+var_14D0], r13d
0x18000434a  mov     ecx, r13d
0x18000434d  lea     eax, [r13+8]
0x180004351  cmp     dword ptr [rdx+8], 1
0x180004355  cmovz   ecx, eax
0x180004358  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x18000435c  lea     ecx, [rax-7]
0x18000435f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180004367  inc     ecx
0x180004369  mov     [rsp+14F0h+var_14C0], ecx
0x18000436d  mov     rcx, [rbp+13F0h+arg_38]
0x180004374  test    rcx, rcx
0x180004377  jz      short loc_180004384
0x180004379  cmp     [rcx], r13w
0x18000437d  mov     [rsp+14F0h+var_14B8], rcx
0x180004382  jnz     short loc_180004389
0x180004384  mov     [rsp+14F0h+var_14B8], r13
0x180004389  call    cs:__imp_GetCurrentThreadId
0x180004390  nop     dword ptr [rax+rax+00h]
0x180004395  mov     [rsp+14F0h+var_14B0], eax
0x180004399  mov     [rsp+14F0h+var_1498], r14
0x18000439e  mov     [rsp+14F0h+var_1490], esi
0x1800043a2  mov     [rsp+14F0h+var_148C], r12d
0x1800043a7  mov     [rsp+14F0h+var_14A8], r13
0x1800043ac  mov     [rsp+14F0h+var_14A0], r13
0x1800043b1  mov     [rbp+13F0h+var_1448], r15
0x1800043b5  mov     [rbp+13F0h+var_1440], rbx
0x1800043b9  mov     [rsp+14F0h+var_1488], r13
0x1800043be  xorps   xmm0, xmm0
0x1800043c1  xor     eax, eax
0x1800043c3  movups  [rbp+13F0h+var_1468], xmm0
0x1800043c7  mov     [rbp+13F0h+var_1458], rax
0x1800043cb  xorps   xmm1, xmm1
0x1800043ce  movups  [rsp+14F0h+var_1480], xmm1
0x1800043d3  mov     [rbp+13F0h+var_1470], rax
0x1800043d7  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800043de  test    rax, rax
0x1800043e1  jz      short loc_1800043EE
0x1800043e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800043e8  mov     [rbp+13F0h+var_1450], rax
0x1800043ec  jmp     short loc_1800043F2
0x1800043ee  mov     [rbp+13F0h+var_1450], r13
0x1800043f2  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800043f9  test    rax, rax
0x1800043fc  jz      short loc_180004408
0x1800043fe  lea     rcx, [rsp+14F0h+var_14D0]
0x180004403  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004408  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000440f  test    rax, rax
0x180004412  jz      short loc_180004428
0x180004414  mov     r8d, 400h
0x18000441a  lea     rdx, [rbp+13F0h+var_1430]
0x18000441e  lea     rcx, [rsp+14F0h+var_14D0]
0x180004423  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004428  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000442f  test    rax, rax
0x180004432  jz      short loc_18000443E
0x180004434  lea     rcx, [rsp+14F0h+var_14D0]
0x180004439  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000443e  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004445  test    rax, rax
0x180004448  jz      short loc_180004460
0x18000444a  test    dil, dil
0x18000444d  jnz     short loc_180004460
0x18000444f  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180004454  jnz     short loc_180004460
0x180004456  lea     rcx, [rsp+14F0h+var_14D0]
0x18000445b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004460  cmp     [rsp+14F0h+var_14C8], r13d
0x180004465  jl      short loc_18000446D
0x180004467  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000446d  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x180004474  jnz     short loc_18000449B
0x180004476  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000447d  test    rax, rax
0x180004480  jz      short loc_18000448B
0x180004482  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004487  test    al, al
0x180004489  jmp     short loc_180004499
0x18000448b  call    cs:__imp_IsDebuggerPresent
0x180004492  nop     dword ptr [rax+rax+00h]
0x180004497  test    eax, eax
0x180004499  jz      short loc_1800044A4
0x18000449b  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800044a0  mov     bl, 1
0x1800044a2  jz      short loc_1800044A7
0x1800044a4  mov     bl, r13b
0x1800044a7  test    dil, dil
0x1800044aa  jnz     short loc_1800044D6
0x1800044ac  test    bl, bl
0x1800044ae  jnz     short loc_1800044D6
0x1800044b0  mov     rax, cs:g_pfnResultLoggingCallback
0x1800044b7  test    rax, rax
0x1800044ba  jz      short loc_180004539
0x1800044bc  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x1800044c3  jnz     short loc_180004539
0x1800044c5  xor     r8d, r8d
0x1800044c8  xor     edx, edx
0x1800044ca  lea     rcx, [rsp+14F0h+var_14D0]
0x1800044cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800044d4  jmp     short loc_180004539
0x1800044d6  mov     esi, 800h
0x1800044db  mov     rax, cs:g_pfnResultLoggingCallback
0x1800044e2  test    rax, rax
0x1800044e5  jz      short loc_180004504
0x1800044e7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x1800044ee  jnz     short loc_180004504
0x1800044f0  mov     r8d, esi
0x1800044f3  lea     rdx, [rbp+13F0h+OutputString]
0x1800044fa  lea     rcx, [rsp+14F0h+var_14D0]
0x1800044ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004504  cmp     [rbp+13F0h+OutputString], r13w
0x18000450c  jnz     short loc_180004522
0x18000450e  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180004513  mov     rdx, rsi; unsigned __int16 *
0x180004516  lea     rcx, [rbp+13F0h+OutputString]; this
0x18000451d  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180004522  test    bl, bl
0x180004524  jz      short loc_180004539
0x180004526  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x18000452d  call    cs:__imp_OutputDebugStringW
0x180004534  nop     dword ptr [rax+rax+00h]
0x180004539  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x18000453e  jnz     short loc_180004549
0x180004540  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x180004547  jz      short loc_18000455B
0x180004549  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180004550  test    rax, rax
0x180004553  jz      short loc_18000455B
0x180004555  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000455a  nop
0x18000455b  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x180004560  jz      short loc_18000456D
0x180004562  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180004567  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18000456d  test    dil, dil
0x180004570  jz      short loc_18000458A
0x180004572  lea     rdx, [rbp+13F0h+OutputString]
0x180004579  lea     rcx, [rsp+14F0h+var_14D0]
0x18000457e  mov     rax, cs:g_pfnThrowPlatformException
0x180004585  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000458a  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000458f  call    ?ThrowResultException@wil@@YAXAEBUFailureInfo@1@@Z; wil::ThrowResultException(wil::FailureInfo const &)
0x180004594  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180004599  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
