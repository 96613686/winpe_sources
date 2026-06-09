# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180009120`
- end: `0x1800093ab`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `651`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180008d38`

## callees

- `0x180003db8`
- `0x180005304`
- `0x180005708`
- `0x180005ac0`
- `0x180009120`
- `0x180013b14`
- `0x1800229a0`
- `0x180024010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800091d9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800091d9`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180009372`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180009372`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800092e2`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800092e2`

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
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (__int64)&v18, v16);
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
0x180009120  mov     [rsp-8+arg_18], rbx
0x180009125  push    rbp
0x180009126  push    rsi
0x180009127  push    rdi
0x180009128  push    r12
0x18000912a  push    r13
0x18000912c  push    r14
0x18000912e  push    r15
0x180009130  lea     rbp, [rsp-13C0h]
0x180009138  mov     eax, 14C0h
0x18000913d  call    _alloca_probe
0x180009142  sub     rsp, rax
0x180009145  mov     r14, r8
0x180009148  mov     esi, edx
0x18000914a  mov     rdi, rcx
0x18000914d  mov     r15, [rbp+13F0h+arg_28]
0x180009154  xor     edx, edx; Val
0x180009156  mov     r8d, 98h; Size
0x18000915c  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180009161  call    memset_0
0x180009166  nop
0x180009167  xor     r13d, r13d
0x18000916a  mov     [rbp+13F0h+OutputString], r13w
0x180009172  mov     [rbp+13F0h+var_1430], r13b
0x180009176  mov     rbx, [rbp+13F0h+arg_30]
0x18000917d  mov     ecx, [rbx]; this
0x18000917f  mov     [rsp+14F0h+var_14C8], ecx
0x180009183  mov     eax, [rbx+4]
0x180009186  mov     [rsp+14F0h+var_14C4], eax
0x18000918a  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000918f  mov     r12d, eax
0x180009192  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x18000919a  mov     ecx, r13d
0x18000919d  lea     eax, [r13+8]
0x1800091a1  cmp     dword ptr [rbx+8], 1
0x1800091a5  cmovz   ecx, eax
0x1800091a8  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x1800091ac  lea     ecx, [rax-7]
0x1800091af  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800091b7  inc     ecx
0x1800091b9  mov     [rsp+14F0h+var_14C0], ecx
0x1800091bd  mov     rcx, [rbp+13F0h+arg_38]
0x1800091c4  test    rcx, rcx
0x1800091c7  jz      short loc_1800091D4
0x1800091c9  cmp     [rcx], r13w
0x1800091cd  mov     [rsp+14F0h+var_14B8], rcx
0x1800091d2  jnz     short loc_1800091D9
0x1800091d4  mov     [rsp+14F0h+var_14B8], r13
0x1800091d9  call    cs:__imp_GetCurrentThreadId
0x1800091e0  nop     dword ptr [rax+rax+00h]
0x1800091e5  mov     [rsp+14F0h+var_14B0], eax
0x1800091e9  mov     [rsp+14F0h+var_1498], r14
0x1800091ee  mov     [rsp+14F0h+var_1490], esi
0x1800091f2  mov     [rsp+14F0h+var_148C], r12d
0x1800091f7  mov     [rsp+14F0h+var_14A8], r13
0x1800091fc  mov     [rsp+14F0h+var_14A0], r13
0x180009201  mov     [rbp+13F0h+var_1448], r15
0x180009205  mov     [rbp+13F0h+var_1440], rdi
0x180009209  mov     [rsp+14F0h+var_1488], r13
0x18000920e  xorps   xmm0, xmm0
0x180009211  xor     eax, eax
0x180009213  movups  [rbp+13F0h+var_1468], xmm0
0x180009217  mov     [rbp+13F0h+var_1458], rax
0x18000921b  xorps   xmm1, xmm1
0x18000921e  movups  [rsp+14F0h+var_1480], xmm1
0x180009223  mov     [rbp+13F0h+var_1470], rax
0x180009227  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000922e  test    rax, rax
0x180009231  jz      short loc_18000923E
0x180009233  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009238  mov     [rbp+13F0h+var_1450], rax
0x18000923c  jmp     short loc_180009242
0x18000923e  mov     [rbp+13F0h+var_1450], r13
0x180009242  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180009249  test    rax, rax
0x18000924c  jz      short loc_180009258
0x18000924e  lea     rcx, [rsp+14F0h+var_14D0]
0x180009253  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009258  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000925f  test    rax, rax
0x180009262  jz      short loc_180009278
0x180009264  mov     r8d, 400h
0x18000926a  lea     rdx, [rbp+13F0h+var_1430]
0x18000926e  lea     rcx, [rsp+14F0h+var_14D0]
0x180009273  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009278  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000927f  test    rax, rax
0x180009282  jz      short loc_18000928E
0x180009284  lea     rcx, [rsp+14F0h+var_14D0]
0x180009289  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000928e  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180009295  test    rax, rax
0x180009298  jz      short loc_1800092AB
0x18000929a  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000929f  jnz     short loc_1800092AB
0x1800092a1  lea     rcx, [rsp+14F0h+var_14D0]
0x1800092a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800092ab  cmp     [rsp+14F0h+var_14C8], r13d
0x1800092b0  jl      short loc_1800092C4
0x1800092b2  mov     ecx, 8000FFFFh; this
0x1800092b7  mov     [rsp+14F0h+var_14C8], ecx
0x1800092bb  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800092c0  mov     [rsp+14F0h+var_14C4], eax
0x1800092c4  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x1800092cb  jnz     short loc_1800092F2
0x1800092cd  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800092d4  test    rax, rax
0x1800092d7  jz      short loc_1800092E2
0x1800092d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800092de  test    al, al
0x1800092e0  jmp     short loc_1800092F0
0x1800092e2  call    cs:__imp_IsDebuggerPresent
0x1800092e9  nop     dword ptr [rax+rax+00h]
0x1800092ee  test    eax, eax
0x1800092f0  jz      short loc_1800092F9
0x1800092f2  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800092f7  jz      short loc_18000931F
0x1800092f9  mov     rax, cs:g_pfnResultLoggingCallback
0x180009300  test    rax, rax
0x180009303  jz      short loc_18000937E
0x180009305  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x18000930c  jnz     short loc_18000937E
0x18000930e  xor     r8d, r8d
0x180009311  xor     edx, edx
0x180009313  lea     rcx, [rsp+14F0h+var_14D0]
0x180009318  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000931d  jmp     short loc_18000937E
0x18000931f  mov     ebx, 800h
0x180009324  mov     rax, cs:g_pfnResultLoggingCallback
0x18000932b  test    rax, rax
0x18000932e  jz      short loc_18000934D
0x180009330  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180009337  jnz     short loc_18000934D
0x180009339  mov     r8d, ebx
0x18000933c  lea     rdx, [rbp+13F0h+OutputString]
0x180009343  lea     rcx, [rsp+14F0h+var_14D0]
0x180009348  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000934d  cmp     [rbp+13F0h+OutputString], r13w
0x180009355  jnz     short loc_18000936B
0x180009357  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x18000935c  mov     rdx, rbx; unsigned __int16 *
0x18000935f  lea     rcx, [rbp+13F0h+OutputString]; this
0x180009366  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000936b  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180009372  call    cs:__imp_OutputDebugStringW
0x180009379  nop     dword ptr [rax+rax+00h]
0x18000937e  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180009383  jnz     short loc_18000938E
0x180009385  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x18000938c  jz      short loc_1800093A0
0x18000938e  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180009395  test    rax, rax
0x180009398  jz      short loc_1800093A0
0x18000939a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000939f  nop
0x1800093a0  lea     rcx, [rsp+14F0h+var_14D0]; this
0x1800093a5  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
