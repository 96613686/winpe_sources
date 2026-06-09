# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180058258`
- end: `0x1800584d1`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `633`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180057fec`

## callees

- `0x18000ebf4`
- `0x180058258`
- `0x180059fb4`
- `0x18005a868`
- `0x18005bab0`
- `0x18005d788`
- `0x1800f1c70`
- `0x180101010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180058311`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180058311`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180058414`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180058414`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18005849e`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18005849e`

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
0x180058258  mov     [rsp-8+arg_18], rbx
0x18005825d  push    rbp
0x18005825e  push    rsi
0x18005825f  push    rdi
0x180058260  push    r12
0x180058262  push    r13
0x180058264  push    r14
0x180058266  push    r15
0x180058268  lea     rbp, [rsp-13C0h]
0x180058270  mov     eax, 14C0h
0x180058275  call    _alloca_probe
0x18005827a  sub     rsp, rax
0x18005827d  mov     r14, r8
0x180058280  mov     esi, edx
0x180058282  mov     rdi, rcx
0x180058285  mov     r15, [rbp+13F0h+arg_28]
0x18005828c  xor     edx, edx; Val
0x18005828e  mov     r8d, 98h; Size
0x180058294  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180058299  call    memset_0
0x18005829e  nop
0x18005829f  xor     r13d, r13d
0x1800582a2  mov     [rbp+13F0h+OutputString], r13w
0x1800582aa  mov     [rbp+13F0h+var_1430], r13b
0x1800582ae  mov     rbx, [rbp+13F0h+arg_30]
0x1800582b5  mov     ecx, [rbx]; this
0x1800582b7  mov     [rsp+14F0h+var_14C8], ecx
0x1800582bb  mov     eax, [rbx+4]
0x1800582be  mov     [rsp+14F0h+var_14C4], eax
0x1800582c2  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800582c7  mov     r12d, eax
0x1800582ca  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x1800582d2  mov     ecx, r13d
0x1800582d5  lea     eax, [r13+8]
0x1800582d9  cmp     dword ptr [rbx+8], 1
0x1800582dd  cmovz   ecx, eax
0x1800582e0  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x1800582e4  lea     ecx, [rax-7]
0x1800582e7  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800582ef  inc     ecx
0x1800582f1  mov     [rsp+14F0h+var_14C0], ecx
0x1800582f5  mov     rcx, [rbp+13F0h+arg_38]
0x1800582fc  test    rcx, rcx
0x1800582ff  jz      short loc_18005830C
0x180058301  cmp     [rcx], r13w
0x180058305  mov     [rsp+14F0h+var_14B8], rcx
0x18005830a  jnz     short loc_180058311
0x18005830c  mov     [rsp+14F0h+var_14B8], r13
0x180058311  call    cs:__imp_GetCurrentThreadId
0x180058317  mov     [rsp+14F0h+var_14B0], eax
0x18005831b  mov     [rsp+14F0h+var_1498], r14
0x180058320  mov     [rsp+14F0h+var_1490], esi
0x180058324  mov     [rsp+14F0h+var_148C], r12d
0x180058329  mov     [rsp+14F0h+var_14A8], r13
0x18005832e  mov     [rsp+14F0h+var_14A0], r13
0x180058333  mov     [rbp+13F0h+var_1448], r15
0x180058337  mov     [rbp+13F0h+var_1440], rdi
0x18005833b  mov     [rsp+14F0h+var_1488], r13
0x180058340  xorps   xmm0, xmm0
0x180058343  xor     eax, eax
0x180058345  movups  [rbp+13F0h+var_1468], xmm0
0x180058349  mov     [rbp+13F0h+var_1458], rax
0x18005834d  xorps   xmm1, xmm1
0x180058350  movups  [rsp+14F0h+var_1480], xmm1
0x180058355  mov     [rbp+13F0h+var_1470], rax
0x180058359  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180058360  test    rax, rax
0x180058363  jz      short loc_180058370
0x180058365  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005836a  mov     [rbp+13F0h+var_1450], rax
0x18005836e  jmp     short loc_180058374
0x180058370  mov     [rbp+13F0h+var_1450], r13
0x180058374  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18005837b  test    rax, rax
0x18005837e  jz      short loc_18005838A
0x180058380  lea     rcx, [rsp+14F0h+var_14D0]
0x180058385  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005838a  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180058391  test    rax, rax
0x180058394  jz      short loc_1800583AA
0x180058396  mov     r8d, 400h
0x18005839c  lea     rdx, [rbp+13F0h+var_1430]
0x1800583a0  lea     rcx, [rsp+14F0h+var_14D0]
0x1800583a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800583aa  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800583b1  test    rax, rax
0x1800583b4  jz      short loc_1800583C0
0x1800583b6  lea     rcx, [rsp+14F0h+var_14D0]
0x1800583bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800583c0  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800583c7  test    rax, rax
0x1800583ca  jz      short loc_1800583DD
0x1800583cc  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800583d1  jnz     short loc_1800583DD
0x1800583d3  lea     rcx, [rsp+14F0h+var_14D0]
0x1800583d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800583dd  cmp     [rsp+14F0h+var_14C8], r13d
0x1800583e2  jl      short loc_1800583F6
0x1800583e4  mov     ecx, 8000FFFFh; this
0x1800583e9  mov     [rsp+14F0h+var_14C8], ecx
0x1800583ed  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800583f2  mov     [rsp+14F0h+var_14C4], eax
0x1800583f6  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x1800583fd  jnz     short loc_18005841E
0x1800583ff  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180058406  test    rax, rax
0x180058409  jz      short loc_180058414
0x18005840b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058410  test    al, al
0x180058412  jmp     short loc_18005841C
0x180058414  call    cs:__imp_IsDebuggerPresent
0x18005841a  test    eax, eax
0x18005841c  jz      short loc_180058425
0x18005841e  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180058423  jz      short loc_18005844B
0x180058425  mov     rax, cs:g_pfnResultLoggingCallback
0x18005842c  test    rax, rax
0x18005842f  jz      short loc_1800584A4
0x180058431  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180058438  jnz     short loc_1800584A4
0x18005843a  xor     r8d, r8d
0x18005843d  xor     edx, edx
0x18005843f  lea     rcx, [rsp+14F0h+var_14D0]
0x180058444  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058449  jmp     short loc_1800584A4
0x18005844b  mov     ebx, 800h
0x180058450  mov     rax, cs:g_pfnResultLoggingCallback
0x180058457  test    rax, rax
0x18005845a  jz      short loc_180058479
0x18005845c  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180058463  jnz     short loc_180058479
0x180058465  mov     r8d, ebx
0x180058468  lea     rdx, [rbp+13F0h+OutputString]
0x18005846f  lea     rcx, [rsp+14F0h+var_14D0]
0x180058474  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058479  cmp     [rbp+13F0h+OutputString], r13w
0x180058481  jnz     short loc_180058497
0x180058483  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180058488  mov     rdx, rbx; unsigned __int16 *
0x18005848b  lea     rcx, [rbp+13F0h+OutputString]; this
0x180058492  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180058497  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x18005849e  call    cs:__imp_OutputDebugStringW
0x1800584a4  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x1800584a9  jnz     short loc_1800584B4
0x1800584ab  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x1800584b2  jz      short loc_1800584C6
0x1800584b4  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800584bb  test    rax, rax
0x1800584be  jz      short loc_1800584C6
0x1800584c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800584c5  nop
0x1800584c6  lea     rcx, [rsp+14F0h+var_14D0]; this
0x1800584cb  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
