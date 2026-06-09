# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180003048`
- end: `0x1800032d3`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `651`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180002da0`

## callees

- `0x18000270c`
- `0x180003048`
- `0x1800055c4`
- `0x180005de4`
- `0x180006ea0`
- `0x18000974c`
- `0x180034af0`
- `0x180039010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003101`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003101`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000320a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000320a`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000329a`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000329a`

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
      g_pfnResultLoggingCallback(&v18, 0, 0, v16);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v18, OutputString, 2048, v16);
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
0x180003048  mov     [rsp-8+arg_18], rbx
0x18000304d  push    rbp
0x18000304e  push    rsi
0x18000304f  push    rdi
0x180003050  push    r12
0x180003052  push    r13
0x180003054  push    r14
0x180003056  push    r15
0x180003058  lea     rbp, [rsp-13C0h]
0x180003060  mov     eax, 14C0h
0x180003065  call    _alloca_probe
0x18000306a  sub     rsp, rax
0x18000306d  mov     r14, r8
0x180003070  mov     esi, edx
0x180003072  mov     rdi, rcx
0x180003075  mov     r15, [rbp+13F0h+arg_28]
0x18000307c  xor     edx, edx; Val
0x18000307e  mov     r8d, 98h; Size
0x180003084  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180003089  call    memset_0
0x18000308e  nop
0x18000308f  xor     r13d, r13d
0x180003092  mov     [rbp+13F0h+OutputString], r13w
0x18000309a  mov     [rbp+13F0h+var_1430], r13b
0x18000309e  mov     rbx, [rbp+13F0h+arg_30]
0x1800030a5  mov     ecx, [rbx]; this
0x1800030a7  mov     [rsp+14F0h+var_14C8], ecx
0x1800030ab  mov     eax, [rbx+4]
0x1800030ae  mov     [rsp+14F0h+var_14C4], eax
0x1800030b2  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800030b7  mov     r12d, eax
0x1800030ba  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x1800030c2  mov     ecx, r13d
0x1800030c5  lea     eax, [r13+8]
0x1800030c9  cmp     dword ptr [rbx+8], 1
0x1800030cd  cmovz   ecx, eax
0x1800030d0  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x1800030d4  lea     ecx, [rax-7]
0x1800030d7  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureInfo *)'::`2'::s_failureId
0x1800030df  inc     ecx
0x1800030e1  mov     [rsp+14F0h+var_14C0], ecx
0x1800030e5  mov     rcx, [rbp+13F0h+arg_38]
0x1800030ec  test    rcx, rcx
0x1800030ef  jz      short loc_1800030FC
0x1800030f1  cmp     [rcx], r13w
0x1800030f5  mov     [rsp+14F0h+var_14B8], rcx
0x1800030fa  jnz     short loc_180003101
0x1800030fc  mov     [rsp+14F0h+var_14B8], r13
0x180003101  call    cs:__imp_GetCurrentThreadId
0x180003108  nop     dword ptr [rax+rax+00h]
0x18000310d  mov     [rsp+14F0h+var_14B0], eax
0x180003111  mov     [rsp+14F0h+var_1498], r14
0x180003116  mov     [rsp+14F0h+var_1490], esi
0x18000311a  mov     [rsp+14F0h+var_148C], r12d
0x18000311f  mov     [rsp+14F0h+var_14A8], r13
0x180003124  mov     [rsp+14F0h+var_14A0], r13
0x180003129  mov     [rbp+13F0h+var_1448], r15
0x18000312d  mov     [rbp+13F0h+var_1440], rdi
0x180003131  mov     [rsp+14F0h+var_1488], r13
0x180003136  xorps   xmm0, xmm0
0x180003139  xor     eax, eax
0x18000313b  movups  [rbp+13F0h+var_1468], xmm0
0x18000313f  mov     [rbp+13F0h+var_1458], rax
0x180003143  xorps   xmm1, xmm1
0x180003146  movups  [rsp+14F0h+var_1480], xmm1
0x18000314b  mov     [rbp+13F0h+var_1470], rax
0x18000314f  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180003156  test    rax, rax
0x180003159  jz      short loc_180003166
0x18000315b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003160  mov     [rbp+13F0h+var_1450], rax
0x180003164  jmp     short loc_18000316A
0x180003166  mov     [rbp+13F0h+var_1450], r13
0x18000316a  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180003171  test    rax, rax
0x180003174  jz      short loc_180003180
0x180003176  lea     rcx, [rsp+14F0h+var_14D0]
0x18000317b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003180  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180003187  test    rax, rax
0x18000318a  jz      short loc_1800031A0
0x18000318c  mov     r8d, 400h
0x180003192  lea     rdx, [rbp+13F0h+var_1430]
0x180003196  lea     rcx, [rsp+14F0h+var_14D0]
0x18000319b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031a0  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800031a7  test    rax, rax
0x1800031aa  jz      short loc_1800031B6
0x1800031ac  lea     rcx, [rsp+14F0h+var_14D0]
0x1800031b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031b6  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800031bd  test    rax, rax
0x1800031c0  jz      short loc_1800031D3
0x1800031c2  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800031c7  jnz     short loc_1800031D3
0x1800031c9  lea     rcx, [rsp+14F0h+var_14D0]
0x1800031ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031d3  cmp     [rsp+14F0h+var_14C8], r13d
0x1800031d8  jl      short loc_1800031EC
0x1800031da  mov     ecx, 8000FFFFh; this
0x1800031df  mov     [rsp+14F0h+var_14C8], ecx
0x1800031e3  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800031e8  mov     [rsp+14F0h+var_14C4], eax
0x1800031ec  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x1800031f3  jnz     short loc_18000321A
0x1800031f5  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800031fc  test    rax, rax
0x1800031ff  jz      short loc_18000320A
0x180003201  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003206  test    al, al
0x180003208  jmp     short loc_180003218
0x18000320a  call    cs:__imp_IsDebuggerPresent
0x180003211  nop     dword ptr [rax+rax+00h]
0x180003216  test    eax, eax
0x180003218  jz      short loc_180003221
0x18000321a  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000321f  jz      short loc_180003247
0x180003221  mov     rax, cs:g_pfnResultLoggingCallback
0x180003228  test    rax, rax
0x18000322b  jz      short loc_1800032A6
0x18000322d  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180003234  jnz     short loc_1800032A6
0x180003236  xor     r8d, r8d
0x180003239  xor     edx, edx
0x18000323b  lea     rcx, [rsp+14F0h+var_14D0]
0x180003240  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003245  jmp     short loc_1800032A6
0x180003247  mov     ebx, 800h
0x18000324c  mov     rax, cs:g_pfnResultLoggingCallback
0x180003253  test    rax, rax
0x180003256  jz      short loc_180003275
0x180003258  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x18000325f  jnz     short loc_180003275
0x180003261  mov     r8d, ebx
0x180003264  lea     rdx, [rbp+13F0h+OutputString]
0x18000326b  lea     rcx, [rsp+14F0h+var_14D0]
0x180003270  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003275  cmp     [rbp+13F0h+OutputString], r13w
0x18000327d  jnz     short loc_180003293
0x18000327f  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180003284  mov     rdx, rbx; unsigned __int16 *
0x180003287  lea     rcx, [rbp+13F0h+OutputString]; this
0x18000328e  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180003293  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x18000329a  call    cs:__imp_OutputDebugStringW
0x1800032a1  nop     dword ptr [rax+rax+00h]
0x1800032a6  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x1800032ab  jnz     short loc_1800032B6
0x1800032ad  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x1800032b4  jz      short loc_1800032C8
0x1800032b6  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800032bd  test    rax, rax
0x1800032c0  jz      short loc_1800032C8
0x1800032c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800032c7  nop
0x1800032c8  lea     rcx, [rsp+14F0h+var_14D0]; this
0x1800032cd  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
