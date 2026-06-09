# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x1800044c0`
- end: `0x180004739`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `633`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18000423c`

## callees

- `0x1800044c0`
- `0x180005fa4`
- `0x180006850`
- `0x180007070`
- `0x1800083c0`
- `0x180033e9a`
- `0x180033f90`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004579`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004579`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180004706`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180004706`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000467c`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000467c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<3>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7,
        _WORD *a8)
{
  int v11; // edx
  int v12; // r12d
  int v13; // ecx
  const struct wil::FailureInfo *v14; // rdx
  __int64 v15; // rcx
  const struct wil::FailureInfo *v16; // r9
  bool v17; // zf
  int v18; // [rsp+20h] [rbp-E0h] BYREF
  int v19; // [rsp+24h] [rbp-DCh]
  int v20; // [rsp+28h] [rbp-D8h]
  int v21; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v22; // [rsp+30h] [rbp-D0h]
  _WORD *v23; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v25; // [rsp+48h] [rbp-B8h]
  __int64 v26; // [rsp+50h] [rbp-B0h]
  __int64 v27; // [rsp+58h] [rbp-A8h]
  int v28; // [rsp+60h] [rbp-A0h]
  int v29; // [rsp+64h] [rbp-9Ch]
  __int64 v30; // [rsp+68h] [rbp-98h]
  __int128 v31; // [rsp+70h] [rbp-90h]
  __int64 v32; // [rsp+80h] [rbp-80h]
  __int128 v33; // [rsp+88h] [rbp-78h]
  __int64 v34; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v36; // [rsp+A8h] [rbp-58h]
  __int64 v37; // [rsp+B0h] [rbp-50h]
  char v38[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2072]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v18, 0, 0x98u);
  OutputString[0] = 0;
  v38[0] = 0;
  v20 = *a7;
  v21 = a7[1];
  v12 = wil::details::RecordFailFast((wil::details *)(unsigned int)v20, v11);
  v18 = 3;
  v13 = 0;
  if ( a7[2] == 1 )
    v13 = 8;
  v19 = v13;
  v22 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  if ( !a8 || (v17 = *a8 == 0, v23 = a8, v17) )
    v23 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v27 = a3;
  v28 = a2;
  v29 = v12;
  v25 = 0;
  v26 = 0;
  v36 = a6;
  v37 = a1;
  v30 = 0;
  v33 = 0;
  v34 = 0;
  v31 = 0;
  v32 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v15);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v18);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v18, v38, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v18);
  if ( wil::details::g_pfnOriginateCallback && (v19 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v18);
  if ( v20 >= 0 )
  {
    v20 = -2147418113;
    v21 = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, (int)v14);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v17 = !IsDebuggerPresent())
      : (v17 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v15) == 0),
        v17)
    || (v19 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v18, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v18, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v18, v16);
    OutputDebugStringW(OutputString);
  }
  if ( (v19 & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v15);
  }
  wil::details::WilFailFast((wil::details *)&v18, v14);
}

```

## disassembly

```asm
0x1800044c0  mov     [rsp-8+arg_18], rbx
0x1800044c5  push    rbp
0x1800044c6  push    rsi
0x1800044c7  push    rdi
0x1800044c8  push    r12
0x1800044ca  push    r13
0x1800044cc  push    r14
0x1800044ce  push    r15
0x1800044d0  lea     rbp, [rsp-13C0h]
0x1800044d8  mov     eax, 14C0h
0x1800044dd  call    _alloca_probe
0x1800044e2  sub     rsp, rax
0x1800044e5  mov     r14, r8
0x1800044e8  mov     esi, edx
0x1800044ea  mov     rdi, rcx
0x1800044ed  mov     r15, [rbp+13F0h+arg_28]
0x1800044f4  xor     edx, edx; Val
0x1800044f6  mov     r8d, 98h; Size
0x1800044fc  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180004501  call    memset_0
0x180004506  nop
0x180004507  xor     r13d, r13d
0x18000450a  mov     [rbp+13F0h+OutputString], r13w
0x180004512  mov     [rbp+13F0h+var_1430], r13b
0x180004516  mov     rbx, [rbp+13F0h+arg_30]
0x18000451d  mov     ecx, [rbx]; this
0x18000451f  mov     [rsp+14F0h+var_14C8], ecx
0x180004523  mov     eax, [rbx+4]
0x180004526  mov     [rsp+14F0h+var_14C4], eax
0x18000452a  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000452f  mov     r12d, eax
0x180004532  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x18000453a  mov     ecx, r13d
0x18000453d  lea     eax, [r13+8]
0x180004541  cmp     dword ptr [rbx+8], 1
0x180004545  cmovz   ecx, eax
0x180004548  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x18000454c  lea     ecx, [rax-7]
0x18000454f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180004557  inc     ecx
0x180004559  mov     [rsp+14F0h+var_14C0], ecx
0x18000455d  mov     rcx, [rbp+13F0h+arg_38]
0x180004564  test    rcx, rcx
0x180004567  jz      short loc_180004574
0x180004569  cmp     [rcx], r13w
0x18000456d  mov     [rsp+14F0h+var_14B8], rcx
0x180004572  jnz     short loc_180004579
0x180004574  mov     [rsp+14F0h+var_14B8], r13
0x180004579  call    cs:__imp_GetCurrentThreadId
0x18000457f  mov     [rsp+14F0h+var_14B0], eax
0x180004583  mov     [rsp+14F0h+var_1498], r14
0x180004588  mov     [rsp+14F0h+var_1490], esi
0x18000458c  mov     [rsp+14F0h+var_148C], r12d
0x180004591  mov     [rsp+14F0h+var_14A8], r13
0x180004596  mov     [rsp+14F0h+var_14A0], r13
0x18000459b  mov     [rbp+13F0h+var_1448], r15
0x18000459f  mov     [rbp+13F0h+var_1440], rdi
0x1800045a3  mov     [rsp+14F0h+var_1488], r13
0x1800045a8  xorps   xmm0, xmm0
0x1800045ab  xor     eax, eax
0x1800045ad  movups  [rbp+13F0h+var_1468], xmm0
0x1800045b1  mov     [rbp+13F0h+var_1458], rax
0x1800045b5  xorps   xmm1, xmm1
0x1800045b8  movups  [rsp+14F0h+var_1480], xmm1
0x1800045bd  mov     [rbp+13F0h+var_1470], rax
0x1800045c1  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800045c8  test    rax, rax
0x1800045cb  jz      short loc_1800045D8
0x1800045cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800045d2  mov     [rbp+13F0h+var_1450], rax
0x1800045d6  jmp     short loc_1800045DC
0x1800045d8  mov     [rbp+13F0h+var_1450], r13
0x1800045dc  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800045e3  test    rax, rax
0x1800045e6  jz      short loc_1800045F2
0x1800045e8  lea     rcx, [rsp+14F0h+var_14D0]
0x1800045ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800045f2  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800045f9  test    rax, rax
0x1800045fc  jz      short loc_180004612
0x1800045fe  mov     r8d, 400h
0x180004604  lea     rdx, [rbp+13F0h+var_1430]
0x180004608  lea     rcx, [rsp+14F0h+var_14D0]
0x18000460d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004612  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004619  test    rax, rax
0x18000461c  jz      short loc_180004628
0x18000461e  lea     rcx, [rsp+14F0h+var_14D0]
0x180004623  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004628  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000462f  test    rax, rax
0x180004632  jz      short loc_180004645
0x180004634  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180004639  jnz     short loc_180004645
0x18000463b  lea     rcx, [rsp+14F0h+var_14D0]
0x180004640  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004645  cmp     [rsp+14F0h+var_14C8], r13d
0x18000464a  jl      short loc_18000465E
0x18000464c  mov     ecx, 8000FFFFh; this
0x180004651  mov     [rsp+14F0h+var_14C8], ecx
0x180004655  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000465a  mov     [rsp+14F0h+var_14C4], eax
0x18000465e  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x180004665  jnz     short loc_180004686
0x180004667  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000466e  test    rax, rax
0x180004671  jz      short loc_18000467C
0x180004673  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004678  test    al, al
0x18000467a  jmp     short loc_180004684
0x18000467c  call    cs:__imp_IsDebuggerPresent
0x180004682  test    eax, eax
0x180004684  jz      short loc_18000468D
0x180004686  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000468b  jz      short loc_1800046B3
0x18000468d  mov     rax, cs:g_pfnResultLoggingCallback
0x180004694  test    rax, rax
0x180004697  jz      short loc_18000470C
0x180004699  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x1800046a0  jnz     short loc_18000470C
0x1800046a2  xor     r8d, r8d
0x1800046a5  xor     edx, edx
0x1800046a7  lea     rcx, [rsp+14F0h+var_14D0]
0x1800046ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800046b1  jmp     short loc_18000470C
0x1800046b3  mov     ebx, 800h
0x1800046b8  mov     rax, cs:g_pfnResultLoggingCallback
0x1800046bf  test    rax, rax
0x1800046c2  jz      short loc_1800046E1
0x1800046c4  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x1800046cb  jnz     short loc_1800046E1
0x1800046cd  mov     r8d, ebx
0x1800046d0  lea     rdx, [rbp+13F0h+OutputString]
0x1800046d7  lea     rcx, [rsp+14F0h+var_14D0]
0x1800046dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800046e1  cmp     [rbp+13F0h+OutputString], r13w
0x1800046e9  jnz     short loc_1800046FF
0x1800046eb  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x1800046f0  mov     rdx, rbx; unsigned __int16 *
0x1800046f3  lea     rcx, [rbp+13F0h+OutputString]; this
0x1800046fa  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800046ff  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180004706  call    cs:__imp_OutputDebugStringW
0x18000470c  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180004711  jnz     short loc_18000471C
0x180004713  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x18000471a  jz      short loc_18000472E
0x18000471c  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180004723  test    rax, rax
0x180004726  jz      short loc_18000472E
0x180004728  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000472d  nop
0x18000472e  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180004733  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
