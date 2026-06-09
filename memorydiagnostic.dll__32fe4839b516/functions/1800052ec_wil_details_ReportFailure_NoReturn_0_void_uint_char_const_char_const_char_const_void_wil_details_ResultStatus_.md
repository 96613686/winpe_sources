# wil::details::ReportFailure_NoReturn<0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x1800052ec`
- end: `0x1800055aa`
- name: `??$ReportFailure_NoReturn@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `702`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180004850`

## callees

- `0x180003374`
- `0x1800052ec`
- `0x18000d474`
- `0x18000fb50`
- `0x180014548`
- `0x180015bec`
- `0x1800162d8`
- `0x180021f90`
- `0x180024010`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x180005496`
- `KERNEL32!IsDebuggerPresent` at `0x180005496`
- `KERNEL32!OutputDebugStringW` at `0x180005538`
- `KERNEL32!OutputDebugStringW` at `0x180005538`
- `KERNEL32!GetCurrentThreadId` at `0x180005395`
- `KERNEL32!GetCurrentThreadId` at `0x180005395`

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
        int *a7)
{
  bool v10; // r12
  int v11; // ebx
  int v12; // ecx
  __int64 v13; // rdx
  const struct wil::FailureInfo *v14; // rdx
  wil::details::in1diag3 *v15; // rcx
  const struct wil::FailureInfo *v16; // r9
  bool v17; // zf
  char v18; // bl
  const struct wil::FailureInfo *v19; // rdx
  int v20; // [rsp+20h] [rbp-E0h] BYREF
  int v21; // [rsp+24h] [rbp-DCh]
  int v22; // [rsp+28h] [rbp-D8h]
  int v23; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v24; // [rsp+30h] [rbp-D0h]
  __int64 v25; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
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

  v10 = g_pfnThrowPlatformException != 0;
  memset_0(&v20, 0, 0x98u);
  OutputString[0] = 0;
  v40[0] = 0;
  v22 = *a7;
  v23 = a7[1];
  v11 = wil::details::RecordException((wil::details *)(unsigned int)v22, (int)a7);
  v20 = 0;
  v12 = 0;
  if ( *(_DWORD *)(v13 + 8) == 1 )
    v12 = 8;
  v21 = v12;
  v24 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v25 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v29 = a3;
  v30 = a2;
  v31 = v11;
  v27 = 0;
  v28 = 0;
  v38 = a6;
  v39 = a1;
  v32 = 0;
  v35 = 0;
  v36 = 0;
  v33 = 0;
  v34 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v15);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v20);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v20, v40, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v20);
  if ( wil::details::g_pfnOriginateCallback && !v10 && (v21 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v20);
  if ( v22 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v15);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v17 = !IsDebuggerPresent())
      : (v17 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v15) == 0),
        v17)
    || (v18 = 1, (v21 & 2) != 0) )
  {
    v18 = 0;
  }
  if ( v10 || v18 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v20, OutputString, 2048, v16);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (__int64)&v20, v16);
    if ( v18 )
      OutputDebugStringW(OutputString);
  }
  else if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
  {
    g_pfnResultLoggingCallback(&v20, 0, 0, v16);
  }
  if ( ((v21 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v15);
  if ( (v21 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v20, v14);
  if ( v10 )
    ((void (__fastcall *)(int *, WCHAR *))g_pfnThrowPlatformException)(&v20, OutputString);
  wil::ThrowResultException((wil *)&v20, v14);
  wil::details::WilFailFast((wil::details *)&v20, v19);
}

```

## disassembly

```asm
0x1800052ec  mov     [rsp-8+arg_18], rbx
0x1800052f1  push    rbp
0x1800052f2  push    rsi
0x1800052f3  push    rdi
0x1800052f4  push    r12
0x1800052f6  push    r13
0x1800052f8  push    r14
0x1800052fa  push    r15
0x1800052fc  lea     rbp, [rsp-13C0h]
0x180005304  mov     eax, 14C0h
0x180005309  call    _alloca_probe
0x18000530e  sub     rsp, rax
0x180005311  mov     r14, r8
0x180005314  mov     esi, edx
0x180005316  mov     r15, rcx
0x180005319  mov     rdi, [rbp+13F0h+arg_28]
0x180005320  xor     r13d, r13d
0x180005323  cmp     cs:g_pfnThrowPlatformException, r13
0x18000532a  setnz   r12b
0x18000532e  xor     edx, edx; Val
0x180005330  mov     r8d, 98h; Size
0x180005336  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x18000533b  call    memset_0
0x180005340  nop
0x180005341  mov     [rbp+13F0h+OutputString], r13w
0x180005349  mov     [rbp+13F0h+var_1430], r13b
0x18000534d  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x180005354  mov     ecx, [rdx]; this
0x180005356  mov     [rsp+14F0h+var_14C8], ecx
0x18000535a  mov     eax, [rdx+4]
0x18000535d  mov     [rsp+14F0h+var_14C4], eax
0x180005361  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180005366  mov     ebx, eax
0x180005368  mov     dword ptr [rsp+14F0h+var_14D0], r13d
0x18000536d  mov     ecx, r13d
0x180005370  lea     eax, [r13+8]
0x180005374  cmp     dword ptr [rdx+8], 1
0x180005378  cmovz   ecx, eax
0x18000537b  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x18000537f  lea     ecx, [rax-7]
0x180005382  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureInfo *)'::`2'::s_failureId
0x18000538a  inc     ecx
0x18000538c  mov     [rsp+14F0h+var_14C0], ecx
0x180005390  mov     [rsp+14F0h+var_14B8], r13
0x180005395  call    cs:__imp_GetCurrentThreadId
0x18000539c  nop     dword ptr [rax+rax+00h]
0x1800053a1  mov     [rsp+14F0h+var_14B0], eax
0x1800053a5  mov     [rsp+14F0h+var_1498], r14
0x1800053aa  mov     [rsp+14F0h+var_1490], esi
0x1800053ae  mov     [rsp+14F0h+var_148C], ebx
0x1800053b2  mov     [rsp+14F0h+var_14A8], r13
0x1800053b7  mov     [rsp+14F0h+var_14A0], r13
0x1800053bc  mov     [rbp+13F0h+var_1448], rdi
0x1800053c0  mov     [rbp+13F0h+var_1440], r15
0x1800053c4  mov     [rsp+14F0h+var_1488], r13
0x1800053c9  xorps   xmm0, xmm0
0x1800053cc  xor     eax, eax
0x1800053ce  movups  [rbp+13F0h+var_1468], xmm0
0x1800053d2  mov     [rbp+13F0h+var_1458], rax
0x1800053d6  xorps   xmm1, xmm1
0x1800053d9  movups  [rsp+14F0h+var_1480], xmm1
0x1800053de  mov     [rbp+13F0h+var_1470], rax
0x1800053e2  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800053e9  test    rax, rax
0x1800053ec  jz      short loc_1800053F9
0x1800053ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800053f3  mov     [rbp+13F0h+var_1450], rax
0x1800053f7  jmp     short loc_1800053FD
0x1800053f9  mov     [rbp+13F0h+var_1450], r13
0x1800053fd  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180005404  test    rax, rax
0x180005407  jz      short loc_180005413
0x180005409  lea     rcx, [rsp+14F0h+var_14D0]
0x18000540e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005413  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000541a  test    rax, rax
0x18000541d  jz      short loc_180005433
0x18000541f  mov     r8d, 400h
0x180005425  lea     rdx, [rbp+13F0h+var_1430]
0x180005429  lea     rcx, [rsp+14F0h+var_14D0]
0x18000542e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005433  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000543a  test    rax, rax
0x18000543d  jz      short loc_180005449
0x18000543f  lea     rcx, [rsp+14F0h+var_14D0]
0x180005444  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005449  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005450  test    rax, rax
0x180005453  jz      short loc_18000546B
0x180005455  test    r12b, r12b
0x180005458  jnz     short loc_18000546B
0x18000545a  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000545f  jnz     short loc_18000546B
0x180005461  lea     rcx, [rsp+14F0h+var_14D0]
0x180005466  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000546b  cmp     [rsp+14F0h+var_14C8], r13d
0x180005470  jl      short loc_180005478
0x180005472  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180005478  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x18000547f  jnz     short loc_1800054A6
0x180005481  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180005488  test    rax, rax
0x18000548b  jz      short loc_180005496
0x18000548d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005492  test    al, al
0x180005494  jmp     short loc_1800054A4
0x180005496  call    cs:__imp_IsDebuggerPresent
0x18000549d  nop     dword ptr [rax+rax+00h]
0x1800054a2  test    eax, eax
0x1800054a4  jz      short loc_1800054AF
0x1800054a6  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800054ab  mov     bl, 1
0x1800054ad  jz      short loc_1800054B2
0x1800054af  mov     bl, r13b
0x1800054b2  test    r12b, r12b
0x1800054b5  jnz     short loc_1800054E1
0x1800054b7  test    bl, bl
0x1800054b9  jnz     short loc_1800054E1
0x1800054bb  mov     rax, cs:g_pfnResultLoggingCallback
0x1800054c2  test    rax, rax
0x1800054c5  jz      short loc_180005544
0x1800054c7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x1800054ce  jnz     short loc_180005544
0x1800054d0  xor     r8d, r8d
0x1800054d3  xor     edx, edx
0x1800054d5  lea     rcx, [rsp+14F0h+var_14D0]
0x1800054da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800054df  jmp     short loc_180005544
0x1800054e1  mov     edi, 800h
0x1800054e6  mov     rax, cs:g_pfnResultLoggingCallback
0x1800054ed  test    rax, rax
0x1800054f0  jz      short loc_18000550F
0x1800054f2  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x1800054f9  jnz     short loc_18000550F
0x1800054fb  mov     r8d, edi
0x1800054fe  lea     rdx, [rbp+13F0h+OutputString]
0x180005505  lea     rcx, [rsp+14F0h+var_14D0]
0x18000550a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000550f  cmp     [rbp+13F0h+OutputString], r13w
0x180005517  jnz     short loc_18000552D
0x180005519  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x18000551e  mov     rdx, rdi; unsigned __int16 *
0x180005521  lea     rcx, [rbp+13F0h+OutputString]; this
0x180005528  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000552d  test    bl, bl
0x18000552f  jz      short loc_180005544
0x180005531  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180005538  call    cs:__imp_OutputDebugStringW
0x18000553f  nop     dword ptr [rax+rax+00h]
0x180005544  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180005549  jnz     short loc_180005554
0x18000554b  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x180005552  jz      short loc_180005566
0x180005554  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000555b  test    rax, rax
0x18000555e  jz      short loc_180005566
0x180005560  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005565  nop
0x180005566  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x18000556b  jz      short loc_180005578
0x18000556d  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180005572  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180005578  test    r12b, r12b
0x18000557b  jz      short loc_180005595
0x18000557d  lea     rdx, [rbp+13F0h+OutputString]
0x180005584  lea     rcx, [rsp+14F0h+var_14D0]
0x180005589  mov     rax, cs:g_pfnThrowPlatformException
0x180005590  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005595  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000559a  call    ?ThrowResultException@wil@@YAXAEBUFailureInfo@1@@Z; wil::ThrowResultException(wil::FailureInfo const &)
0x18000559f  lea     rcx, [rsp+14F0h+var_14D0]; this
0x1800055a4  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
