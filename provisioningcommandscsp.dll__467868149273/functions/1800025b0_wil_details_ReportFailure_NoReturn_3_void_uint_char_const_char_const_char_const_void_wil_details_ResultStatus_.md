# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x1800025b0`
- end: `0x18000283b`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `651`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180002318`

## callees

- `0x1800025b0`
- `0x180003814`
- `0x180004028`
- `0x180004ac0`
- `0x180005b0c`
- `0x18000cc8e`
- `0x18000cd80`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002669`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002669`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180002802`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180002802`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002772`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002772`

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
0x1800025b0  mov     [rsp-8+arg_18], rbx
0x1800025b5  push    rbp
0x1800025b6  push    rsi
0x1800025b7  push    rdi
0x1800025b8  push    r12
0x1800025ba  push    r13
0x1800025bc  push    r14
0x1800025be  push    r15
0x1800025c0  lea     rbp, [rsp-13C0h]
0x1800025c8  mov     eax, 14C0h
0x1800025cd  call    _alloca_probe
0x1800025d2  sub     rsp, rax
0x1800025d5  mov     r14, r8
0x1800025d8  mov     esi, edx
0x1800025da  mov     rdi, rcx
0x1800025dd  mov     r15, [rbp+13F0h+arg_28]
0x1800025e4  xor     edx, edx; Val
0x1800025e6  mov     r8d, 98h; Size
0x1800025ec  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x1800025f1  call    memset_0
0x1800025f6  nop
0x1800025f7  xor     r13d, r13d
0x1800025fa  mov     [rbp+13F0h+OutputString], r13w
0x180002602  mov     [rbp+13F0h+var_1430], r13b
0x180002606  mov     rbx, [rbp+13F0h+arg_30]
0x18000260d  mov     ecx, [rbx]; this
0x18000260f  mov     [rsp+14F0h+var_14C8], ecx
0x180002613  mov     eax, [rbx+4]
0x180002616  mov     [rsp+14F0h+var_14C4], eax
0x18000261a  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000261f  mov     r12d, eax
0x180002622  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x18000262a  mov     ecx, r13d
0x18000262d  lea     eax, [r13+8]
0x180002631  cmp     dword ptr [rbx+8], 1
0x180002635  cmovz   ecx, eax
0x180002638  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x18000263c  lea     ecx, [rax-7]
0x18000263f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180002647  inc     ecx
0x180002649  mov     [rsp+14F0h+var_14C0], ecx
0x18000264d  mov     rcx, [rbp+13F0h+arg_38]
0x180002654  test    rcx, rcx
0x180002657  jz      short loc_180002664
0x180002659  cmp     [rcx], r13w
0x18000265d  mov     [rsp+14F0h+var_14B8], rcx
0x180002662  jnz     short loc_180002669
0x180002664  mov     [rsp+14F0h+var_14B8], r13
0x180002669  call    cs:__imp_GetCurrentThreadId
0x180002670  nop     dword ptr [rax+rax+00h]
0x180002675  mov     [rsp+14F0h+var_14B0], eax
0x180002679  mov     [rsp+14F0h+var_1498], r14
0x18000267e  mov     [rsp+14F0h+var_1490], esi
0x180002682  mov     [rsp+14F0h+var_148C], r12d
0x180002687  mov     [rsp+14F0h+var_14A8], r13
0x18000268c  mov     [rsp+14F0h+var_14A0], r13
0x180002691  mov     [rbp+13F0h+var_1448], r15
0x180002695  mov     [rbp+13F0h+var_1440], rdi
0x180002699  mov     [rsp+14F0h+var_1488], r13
0x18000269e  xorps   xmm0, xmm0
0x1800026a1  xor     eax, eax
0x1800026a3  movups  [rbp+13F0h+var_1468], xmm0
0x1800026a7  mov     [rbp+13F0h+var_1458], rax
0x1800026ab  xorps   xmm1, xmm1
0x1800026ae  movups  [rsp+14F0h+var_1480], xmm1
0x1800026b3  mov     [rbp+13F0h+var_1470], rax
0x1800026b7  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800026be  test    rax, rax
0x1800026c1  jz      short loc_1800026CE
0x1800026c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800026c8  mov     [rbp+13F0h+var_1450], rax
0x1800026cc  jmp     short loc_1800026D2
0x1800026ce  mov     [rbp+13F0h+var_1450], r13
0x1800026d2  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800026d9  test    rax, rax
0x1800026dc  jz      short loc_1800026E8
0x1800026de  lea     rcx, [rsp+14F0h+var_14D0]
0x1800026e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800026e8  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800026ef  test    rax, rax
0x1800026f2  jz      short loc_180002708
0x1800026f4  mov     r8d, 400h
0x1800026fa  lea     rdx, [rbp+13F0h+var_1430]
0x1800026fe  lea     rcx, [rsp+14F0h+var_14D0]
0x180002703  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002708  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000270f  test    rax, rax
0x180002712  jz      short loc_18000271E
0x180002714  lea     rcx, [rsp+14F0h+var_14D0]
0x180002719  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000271e  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002725  test    rax, rax
0x180002728  jz      short loc_18000273B
0x18000272a  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000272f  jnz     short loc_18000273B
0x180002731  lea     rcx, [rsp+14F0h+var_14D0]
0x180002736  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000273b  cmp     [rsp+14F0h+var_14C8], r13d
0x180002740  jl      short loc_180002754
0x180002742  mov     ecx, 8000FFFFh; this
0x180002747  mov     [rsp+14F0h+var_14C8], ecx
0x18000274b  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180002750  mov     [rsp+14F0h+var_14C4], eax
0x180002754  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x18000275b  jnz     short loc_180002782
0x18000275d  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180002764  test    rax, rax
0x180002767  jz      short loc_180002772
0x180002769  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000276e  test    al, al
0x180002770  jmp     short loc_180002780
0x180002772  call    cs:__imp_IsDebuggerPresent
0x180002779  nop     dword ptr [rax+rax+00h]
0x18000277e  test    eax, eax
0x180002780  jz      short loc_180002789
0x180002782  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180002787  jz      short loc_1800027AF
0x180002789  mov     rax, cs:g_pfnResultLoggingCallback
0x180002790  test    rax, rax
0x180002793  jz      short loc_18000280E
0x180002795  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x18000279c  jnz     short loc_18000280E
0x18000279e  xor     r8d, r8d
0x1800027a1  xor     edx, edx
0x1800027a3  lea     rcx, [rsp+14F0h+var_14D0]
0x1800027a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800027ad  jmp     short loc_18000280E
0x1800027af  mov     ebx, 800h
0x1800027b4  mov     rax, cs:g_pfnResultLoggingCallback
0x1800027bb  test    rax, rax
0x1800027be  jz      short loc_1800027DD
0x1800027c0  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x1800027c7  jnz     short loc_1800027DD
0x1800027c9  mov     r8d, ebx
0x1800027cc  lea     rdx, [rbp+13F0h+OutputString]
0x1800027d3  lea     rcx, [rsp+14F0h+var_14D0]
0x1800027d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800027dd  cmp     [rbp+13F0h+OutputString], r13w
0x1800027e5  jnz     short loc_1800027FB
0x1800027e7  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x1800027ec  mov     rdx, rbx; unsigned __int16 *
0x1800027ef  lea     rcx, [rbp+13F0h+OutputString]; this
0x1800027f6  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800027fb  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180002802  call    cs:__imp_OutputDebugStringW
0x180002809  nop     dword ptr [rax+rax+00h]
0x18000280e  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180002813  jnz     short loc_18000281E
0x180002815  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x18000281c  jz      short loc_180002830
0x18000281e  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180002825  test    rax, rax
0x180002828  jz      short loc_180002830
0x18000282a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000282f  nop
0x180002830  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180002835  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
