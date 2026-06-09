# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x140003090`
- end: `0x140003304`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `628`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x140002e28`

## callees

- `0x14000271f`
- `0x140003090`
- `0x140005604`
- `0x140005e1c`
- `0x140007270`
- `0x140009b3c`
- `0x140015750`
- `0x140017010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140003132`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140003132`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x14000323b`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x14000323b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1400032cb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1400032cb`

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
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (__int64)&v17, v15);
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
0x140003090  mov     [rsp-8+arg_18], rbx
0x140003095  push    rbp
0x140003096  push    rsi
0x140003097  push    rdi
0x140003098  push    r12
0x14000309a  push    r13
0x14000309c  push    r14
0x14000309e  push    r15
0x1400030a0  lea     rbp, [rsp-13C0h]
0x1400030a8  mov     eax, 14C0h
0x1400030ad  call    _alloca_probe
0x1400030b2  sub     rsp, rax
0x1400030b5  mov     r15, r8
0x1400030b8  mov     r14d, edx
0x1400030bb  mov     r12, rcx
0x1400030be  mov     rsi, [rbp+13F0h+arg_28]
0x1400030c5  xor     edx, edx; Val
0x1400030c7  mov     r8d, 98h; Size
0x1400030cd  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x1400030d2  call    memset_0
0x1400030d7  nop
0x1400030d8  xor     r13d, r13d
0x1400030db  mov     [rbp+13F0h+OutputString], r13w
0x1400030e3  mov     [rbp+13F0h+var_1430], r13b
0x1400030e7  mov     rbx, [rbp+13F0h+arg_30]
0x1400030ee  mov     ecx, [rbx]; this
0x1400030f0  mov     [rsp+14F0h+var_14C8], ecx
0x1400030f4  mov     eax, [rbx+4]
0x1400030f7  mov     [rsp+14F0h+var_14C4], eax
0x1400030fb  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x140003100  mov     edi, eax
0x140003102  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x14000310a  mov     ecx, r13d
0x14000310d  lea     eax, [r13+8]
0x140003111  cmp     dword ptr [rbx+8], 1
0x140003115  cmovz   ecx, eax
0x140003118  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x14000311c  lea     ecx, [rax-7]
0x14000311f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140003127  inc     ecx
0x140003129  mov     [rsp+14F0h+var_14C0], ecx
0x14000312d  mov     [rsp+14F0h+var_14B8], r13
0x140003132  call    cs:__imp_GetCurrentThreadId
0x140003139  nop     dword ptr [rax+rax+00h]
0x14000313e  mov     [rsp+14F0h+var_14B0], eax
0x140003142  mov     [rsp+14F0h+var_1498], r15
0x140003147  mov     [rsp+14F0h+var_1490], r14d
0x14000314c  mov     [rsp+14F0h+var_148C], edi
0x140003150  mov     [rsp+14F0h+var_14A8], r13
0x140003155  mov     [rsp+14F0h+var_14A0], r13
0x14000315a  mov     [rbp+13F0h+var_1448], rsi
0x14000315e  mov     [rbp+13F0h+var_1440], r12
0x140003162  mov     [rsp+14F0h+var_1488], r13
0x140003167  xorps   xmm0, xmm0
0x14000316a  xor     eax, eax
0x14000316c  movups  [rbp+13F0h+var_1468], xmm0
0x140003170  mov     [rbp+13F0h+var_1458], rax
0x140003174  xorps   xmm1, xmm1
0x140003177  movups  [rsp+14F0h+var_1480], xmm1
0x14000317c  mov     [rbp+13F0h+var_1470], rax
0x140003180  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140003187  test    rax, rax
0x14000318a  jz      short loc_140003197
0x14000318c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003191  mov     [rbp+13F0h+var_1450], rax
0x140003195  jmp     short loc_14000319B
0x140003197  mov     [rbp+13F0h+var_1450], r13
0x14000319b  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1400031a2  test    rax, rax
0x1400031a5  jz      short loc_1400031B1
0x1400031a7  lea     rcx, [rsp+14F0h+var_14D0]
0x1400031ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400031b1  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1400031b8  test    rax, rax
0x1400031bb  jz      short loc_1400031D1
0x1400031bd  mov     r8d, 400h
0x1400031c3  lea     rdx, [rbp+13F0h+var_1430]
0x1400031c7  lea     rcx, [rsp+14F0h+var_14D0]
0x1400031cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400031d1  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1400031d8  test    rax, rax
0x1400031db  jz      short loc_1400031E7
0x1400031dd  lea     rcx, [rsp+14F0h+var_14D0]
0x1400031e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400031e7  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1400031ee  test    rax, rax
0x1400031f1  jz      short loc_140003204
0x1400031f3  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1400031f8  jnz     short loc_140003204
0x1400031fa  lea     rcx, [rsp+14F0h+var_14D0]
0x1400031ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003204  cmp     [rsp+14F0h+var_14C8], r13d
0x140003209  jl      short loc_14000321D
0x14000320b  mov     ecx, 8000FFFFh; this
0x140003210  mov     [rsp+14F0h+var_14C8], ecx
0x140003214  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140003219  mov     [rsp+14F0h+var_14C4], eax
0x14000321d  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x140003224  jnz     short loc_14000324B
0x140003226  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x14000322d  test    rax, rax
0x140003230  jz      short loc_14000323B
0x140003232  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003237  test    al, al
0x140003239  jmp     short loc_140003249
0x14000323b  call    cs:__imp_IsDebuggerPresent
0x140003242  nop     dword ptr [rax+rax+00h]
0x140003247  test    eax, eax
0x140003249  jz      short loc_140003252
0x14000324b  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x140003250  jz      short loc_140003278
0x140003252  mov     rax, cs:g_pfnResultLoggingCallback
0x140003259  test    rax, rax
0x14000325c  jz      short loc_1400032D7
0x14000325e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x140003265  jnz     short loc_1400032D7
0x140003267  xor     r8d, r8d
0x14000326a  xor     edx, edx
0x14000326c  lea     rcx, [rsp+14F0h+var_14D0]
0x140003271  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003276  jmp     short loc_1400032D7
0x140003278  mov     ebx, 800h
0x14000327d  mov     rax, cs:g_pfnResultLoggingCallback
0x140003284  test    rax, rax
0x140003287  jz      short loc_1400032A6
0x140003289  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x140003290  jnz     short loc_1400032A6
0x140003292  mov     r8d, ebx
0x140003295  lea     rdx, [rbp+13F0h+OutputString]
0x14000329c  lea     rcx, [rsp+14F0h+var_14D0]
0x1400032a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400032a6  cmp     [rbp+13F0h+OutputString], r13w
0x1400032ae  jnz     short loc_1400032C4
0x1400032b0  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x1400032b5  mov     rdx, rbx; unsigned __int16 *
0x1400032b8  lea     rcx, [rbp+13F0h+OutputString]; this
0x1400032bf  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1400032c4  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x1400032cb  call    cs:__imp_OutputDebugStringW
0x1400032d2  nop     dword ptr [rax+rax+00h]
0x1400032d7  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x1400032dc  jnz     short loc_1400032E7
0x1400032de  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x1400032e5  jz      short loc_1400032F9
0x1400032e7  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1400032ee  test    rax, rax
0x1400032f1  jz      short loc_1400032F9
0x1400032f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400032f8  nop
0x1400032f9  lea     rcx, [rsp+14F0h+var_14D0]; this
0x1400032fe  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
