# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x18000315c`
- end: `0x1800033be`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `610`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180002f28`

## callees

- `0x18000315c`
- `0x180005554`
- `0x180005e30`
- `0x180007f90`
- `0x180009f80`
- `0x180075c5a`
- `0x180075d50`
- `0x180078010`

## import_xrefs

- `KERNEL32!OutputDebugStringW` at `0x18000338b`
- `KERNEL32!OutputDebugStringW` at `0x18000338b`
- `KERNEL32!IsDebuggerPresent` at `0x180003301`
- `KERNEL32!IsDebuggerPresent` at `0x180003301`
- `KERNEL32!GetCurrentThreadId` at `0x1800031fe`
- `KERNEL32!GetCurrentThreadId` at `0x1800031fe`

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
        int *a7)
{
  int v10; // edx
  int v11; // edi
  int v12; // ecx
  const struct wil::FailureInfo *v13; // rdx
  __int64 v14; // rcx
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
  WCHAR OutputString[2072]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v17, 0, 0x98u);
  OutputString[0] = 0;
  v37[0] = 0;
  v19 = *a7;
  v20 = a7[1];
  v11 = wil::details::RecordFailFast((wil::details *)(unsigned int)v19, v10);
  v17 = 3;
  v12 = 0;
  if ( a7[2] == 1 )
    v12 = 8;
  v18 = v12;
  v21 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v22 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v26 = a3;
  v27 = a2;
  v28 = v11;
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
  {
    v19 = -2147418113;
    v20 = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, (int)v13);
  }
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
      wil::GetFailureLogString(OutputString, (unsigned __int16 *)0x800, (__int64)&v17, v15);
    OutputDebugStringW(OutputString);
  }
  if ( (v18 & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v14);
  }
  wil::details::WilFailFast((wil::details *)&v17, v13);
}

```

## disassembly

```asm
0x18000315c  mov     [rsp-8+arg_18], rbx
0x180003161  push    rbp
0x180003162  push    rsi
0x180003163  push    rdi
0x180003164  push    r12
0x180003166  push    r13
0x180003168  push    r14
0x18000316a  push    r15
0x18000316c  lea     rbp, [rsp-13C0h]
0x180003174  mov     eax, 14C0h
0x180003179  call    _alloca_probe
0x18000317e  sub     rsp, rax
0x180003181  mov     r15, r8
0x180003184  mov     r14d, edx
0x180003187  mov     r12, rcx
0x18000318a  mov     rsi, [rbp+13F0h+arg_28]
0x180003191  xor     edx, edx; Val
0x180003193  mov     r8d, 98h; Size
0x180003199  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x18000319e  call    memset_0
0x1800031a3  nop
0x1800031a4  xor     r13d, r13d
0x1800031a7  mov     [rbp+13F0h+OutputString], r13w
0x1800031af  mov     [rbp+13F0h+var_1430], r13b
0x1800031b3  mov     rbx, [rbp+13F0h+arg_30]
0x1800031ba  mov     ecx, [rbx]; this
0x1800031bc  mov     [rsp+14F0h+var_14C8], ecx
0x1800031c0  mov     eax, [rbx+4]
0x1800031c3  mov     [rsp+14F0h+var_14C4], eax
0x1800031c7  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800031cc  mov     edi, eax
0x1800031ce  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x1800031d6  mov     ecx, r13d
0x1800031d9  lea     eax, [r13+8]
0x1800031dd  cmp     dword ptr [rbx+8], 1
0x1800031e1  cmovz   ecx, eax
0x1800031e4  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x1800031e8  lea     ecx, [rax-7]
0x1800031eb  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800031f3  inc     ecx
0x1800031f5  mov     [rsp+14F0h+var_14C0], ecx
0x1800031f9  mov     [rsp+14F0h+var_14B8], r13
0x1800031fe  call    cs:__imp_GetCurrentThreadId
0x180003204  mov     [rsp+14F0h+var_14B0], eax
0x180003208  mov     [rsp+14F0h+var_1498], r15
0x18000320d  mov     [rsp+14F0h+var_1490], r14d
0x180003212  mov     [rsp+14F0h+var_148C], edi
0x180003216  mov     [rsp+14F0h+var_14A8], r13
0x18000321b  mov     [rsp+14F0h+var_14A0], r13
0x180003220  mov     [rbp+13F0h+var_1448], rsi
0x180003224  mov     [rbp+13F0h+var_1440], r12
0x180003228  mov     [rsp+14F0h+var_1488], r13
0x18000322d  xorps   xmm0, xmm0
0x180003230  xor     eax, eax
0x180003232  movups  [rbp+13F0h+var_1468], xmm0
0x180003236  mov     [rbp+13F0h+var_1458], rax
0x18000323a  xorps   xmm1, xmm1
0x18000323d  movups  [rsp+14F0h+var_1480], xmm1
0x180003242  mov     [rbp+13F0h+var_1470], rax
0x180003246  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000324d  test    rax, rax
0x180003250  jz      short loc_18000325D
0x180003252  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003257  mov     [rbp+13F0h+var_1450], rax
0x18000325b  jmp     short loc_180003261
0x18000325d  mov     [rbp+13F0h+var_1450], r13
0x180003261  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180003268  test    rax, rax
0x18000326b  jz      short loc_180003277
0x18000326d  lea     rcx, [rsp+14F0h+var_14D0]
0x180003272  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003277  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000327e  test    rax, rax
0x180003281  jz      short loc_180003297
0x180003283  mov     r8d, 400h
0x180003289  lea     rdx, [rbp+13F0h+var_1430]
0x18000328d  lea     rcx, [rsp+14F0h+var_14D0]
0x180003292  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003297  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000329e  test    rax, rax
0x1800032a1  jz      short loc_1800032AD
0x1800032a3  lea     rcx, [rsp+14F0h+var_14D0]
0x1800032a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800032ad  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800032b4  test    rax, rax
0x1800032b7  jz      short loc_1800032CA
0x1800032b9  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800032be  jnz     short loc_1800032CA
0x1800032c0  lea     rcx, [rsp+14F0h+var_14D0]
0x1800032c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800032ca  cmp     [rsp+14F0h+var_14C8], r13d
0x1800032cf  jl      short loc_1800032E3
0x1800032d1  mov     ecx, 8000FFFFh; this
0x1800032d6  mov     [rsp+14F0h+var_14C8], ecx
0x1800032da  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800032df  mov     [rsp+14F0h+var_14C4], eax
0x1800032e3  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x1800032ea  jnz     short loc_18000330B
0x1800032ec  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800032f3  test    rax, rax
0x1800032f6  jz      short loc_180003301
0x1800032f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800032fd  test    al, al
0x1800032ff  jmp     short loc_180003309
0x180003301  call    cs:__imp_IsDebuggerPresent
0x180003307  test    eax, eax
0x180003309  jz      short loc_180003312
0x18000330b  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180003310  jz      short loc_180003338
0x180003312  mov     rax, cs:g_pfnResultLoggingCallback
0x180003319  test    rax, rax
0x18000331c  jz      short loc_180003391
0x18000331e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180003325  jnz     short loc_180003391
0x180003327  xor     r8d, r8d
0x18000332a  xor     edx, edx
0x18000332c  lea     rcx, [rsp+14F0h+var_14D0]
0x180003331  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003336  jmp     short loc_180003391
0x180003338  mov     ebx, 800h
0x18000333d  mov     rax, cs:g_pfnResultLoggingCallback
0x180003344  test    rax, rax
0x180003347  jz      short loc_180003366
0x180003349  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180003350  jnz     short loc_180003366
0x180003352  mov     r8d, ebx
0x180003355  lea     rdx, [rbp+13F0h+OutputString]
0x18000335c  lea     rcx, [rsp+14F0h+var_14D0]
0x180003361  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003366  cmp     [rbp+13F0h+OutputString], r13w
0x18000336e  jnz     short loc_180003384
0x180003370  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180003375  mov     rdx, rbx; unsigned __int16 *
0x180003378  lea     rcx, [rbp+13F0h+OutputString]; lpString
0x18000337f  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180003384  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x18000338b  call    cs:__imp_OutputDebugStringW
0x180003391  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180003396  jnz     short loc_1800033A1
0x180003398  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x18000339f  jz      short loc_1800033B3
0x1800033a1  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800033a8  test    rax, rax
0x1800033ab  jz      short loc_1800033B3
0x1800033ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800033b2  nop
0x1800033b3  lea     rcx, [rsp+14F0h+var_14D0]; this
0x1800033b8  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
