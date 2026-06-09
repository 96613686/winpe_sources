# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180004064`
- end: `0x1800042dd`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `633`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180003dd4`

## callees

- `0x180002ef8`
- `0x180004064`
- `0x180005534`
- `0x180005d80`
- `0x1800064e0`
- `0x180007610`
- `0x18002df90`
- `0x180030010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000411d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000411d`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800042aa`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800042aa`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180004220`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180004220`

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
0x180004064  mov     [rsp-8+arg_18], rbx
0x180004069  push    rbp
0x18000406a  push    rsi
0x18000406b  push    rdi
0x18000406c  push    r12
0x18000406e  push    r13
0x180004070  push    r14
0x180004072  push    r15
0x180004074  lea     rbp, [rsp-13C0h]
0x18000407c  mov     eax, 14C0h
0x180004081  call    _alloca_probe
0x180004086  sub     rsp, rax
0x180004089  mov     r14, r8
0x18000408c  mov     esi, edx
0x18000408e  mov     rdi, rcx
0x180004091  mov     r15, [rbp+13F0h+arg_28]
0x180004098  xor     edx, edx; Val
0x18000409a  mov     r8d, 98h; Size
0x1800040a0  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x1800040a5  call    memset_0
0x1800040aa  nop
0x1800040ab  xor     r13d, r13d
0x1800040ae  mov     [rbp+13F0h+OutputString], r13w
0x1800040b6  mov     [rbp+13F0h+var_1430], r13b
0x1800040ba  mov     rbx, [rbp+13F0h+arg_30]
0x1800040c1  mov     ecx, [rbx]; this
0x1800040c3  mov     [rsp+14F0h+var_14C8], ecx
0x1800040c7  mov     eax, [rbx+4]
0x1800040ca  mov     [rsp+14F0h+var_14C4], eax
0x1800040ce  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800040d3  mov     r12d, eax
0x1800040d6  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x1800040de  mov     ecx, r13d
0x1800040e1  lea     eax, [r13+8]
0x1800040e5  cmp     dword ptr [rbx+8], 1
0x1800040e9  cmovz   ecx, eax
0x1800040ec  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x1800040f0  lea     ecx, [rax-7]
0x1800040f3  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800040fb  inc     ecx
0x1800040fd  mov     [rsp+14F0h+var_14C0], ecx
0x180004101  mov     rcx, [rbp+13F0h+arg_38]
0x180004108  test    rcx, rcx
0x18000410b  jz      short loc_180004118
0x18000410d  cmp     [rcx], r13w
0x180004111  mov     [rsp+14F0h+var_14B8], rcx
0x180004116  jnz     short loc_18000411D
0x180004118  mov     [rsp+14F0h+var_14B8], r13
0x18000411d  call    cs:__imp_GetCurrentThreadId
0x180004123  mov     [rsp+14F0h+var_14B0], eax
0x180004127  mov     [rsp+14F0h+var_1498], r14
0x18000412c  mov     [rsp+14F0h+var_1490], esi
0x180004130  mov     [rsp+14F0h+var_148C], r12d
0x180004135  mov     [rsp+14F0h+var_14A8], r13
0x18000413a  mov     [rsp+14F0h+var_14A0], r13
0x18000413f  mov     [rbp+13F0h+var_1448], r15
0x180004143  mov     [rbp+13F0h+var_1440], rdi
0x180004147  mov     [rsp+14F0h+var_1488], r13
0x18000414c  xorps   xmm0, xmm0
0x18000414f  xor     eax, eax
0x180004151  movups  [rbp+13F0h+var_1468], xmm0
0x180004155  mov     [rbp+13F0h+var_1458], rax
0x180004159  xorps   xmm1, xmm1
0x18000415c  movups  [rsp+14F0h+var_1480], xmm1
0x180004161  mov     [rbp+13F0h+var_1470], rax
0x180004165  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000416c  test    rax, rax
0x18000416f  jz      short loc_18000417C
0x180004171  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004176  mov     [rbp+13F0h+var_1450], rax
0x18000417a  jmp     short loc_180004180
0x18000417c  mov     [rbp+13F0h+var_1450], r13
0x180004180  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180004187  test    rax, rax
0x18000418a  jz      short loc_180004196
0x18000418c  lea     rcx, [rsp+14F0h+var_14D0]
0x180004191  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004196  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000419d  test    rax, rax
0x1800041a0  jz      short loc_1800041B6
0x1800041a2  mov     r8d, 400h
0x1800041a8  lea     rdx, [rbp+13F0h+var_1430]
0x1800041ac  lea     rcx, [rsp+14F0h+var_14D0]
0x1800041b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800041b6  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800041bd  test    rax, rax
0x1800041c0  jz      short loc_1800041CC
0x1800041c2  lea     rcx, [rsp+14F0h+var_14D0]
0x1800041c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800041cc  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800041d3  test    rax, rax
0x1800041d6  jz      short loc_1800041E9
0x1800041d8  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800041dd  jnz     short loc_1800041E9
0x1800041df  lea     rcx, [rsp+14F0h+var_14D0]
0x1800041e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800041e9  cmp     [rsp+14F0h+var_14C8], r13d
0x1800041ee  jl      short loc_180004202
0x1800041f0  mov     ecx, 8000FFFFh; this
0x1800041f5  mov     [rsp+14F0h+var_14C8], ecx
0x1800041f9  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800041fe  mov     [rsp+14F0h+var_14C4], eax
0x180004202  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x180004209  jnz     short loc_18000422A
0x18000420b  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180004212  test    rax, rax
0x180004215  jz      short loc_180004220
0x180004217  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000421c  test    al, al
0x18000421e  jmp     short loc_180004228
0x180004220  call    cs:__imp_IsDebuggerPresent
0x180004226  test    eax, eax
0x180004228  jz      short loc_180004231
0x18000422a  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000422f  jz      short loc_180004257
0x180004231  mov     rax, cs:g_pfnResultLoggingCallback
0x180004238  test    rax, rax
0x18000423b  jz      short loc_1800042B0
0x18000423d  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180004244  jnz     short loc_1800042B0
0x180004246  xor     r8d, r8d
0x180004249  xor     edx, edx
0x18000424b  lea     rcx, [rsp+14F0h+var_14D0]
0x180004250  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004255  jmp     short loc_1800042B0
0x180004257  mov     ebx, 800h
0x18000425c  mov     rax, cs:g_pfnResultLoggingCallback
0x180004263  test    rax, rax
0x180004266  jz      short loc_180004285
0x180004268  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x18000426f  jnz     short loc_180004285
0x180004271  mov     r8d, ebx
0x180004274  lea     rdx, [rbp+13F0h+OutputString]
0x18000427b  lea     rcx, [rsp+14F0h+var_14D0]
0x180004280  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004285  cmp     [rbp+13F0h+OutputString], r13w
0x18000428d  jnz     short loc_1800042A3
0x18000428f  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180004294  mov     rdx, rbx; unsigned __int16 *
0x180004297  lea     rcx, [rbp+13F0h+OutputString]; this
0x18000429e  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800042a3  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x1800042aa  call    cs:__imp_OutputDebugStringW
0x1800042b0  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x1800042b5  jnz     short loc_1800042C0
0x1800042b7  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x1800042be  jz      short loc_1800042D2
0x1800042c0  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800042c7  test    rax, rax
0x1800042ca  jz      short loc_1800042D2
0x1800042cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800042d1  nop
0x1800042d2  lea     rcx, [rsp+14F0h+var_14D0]; this
0x1800042d7  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
