# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x1800034f0`
- end: `0x180003769`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `633`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180003074`

## callees

- `0x180002062`
- `0x1800034f0`
- `0x180004e44`
- `0x180005f2c`
- `0x180006690`
- `0x1800077d0`
- `0x18000ce90`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800035a9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800035a9`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003736`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003736`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800036ac`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800036ac`

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
0x1800034f0  mov     [rsp-8+arg_18], rbx
0x1800034f5  push    rbp
0x1800034f6  push    rsi
0x1800034f7  push    rdi
0x1800034f8  push    r12
0x1800034fa  push    r13
0x1800034fc  push    r14
0x1800034fe  push    r15
0x180003500  lea     rbp, [rsp-13C0h]
0x180003508  mov     eax, 14C0h
0x18000350d  call    _alloca_probe
0x180003512  sub     rsp, rax
0x180003515  mov     r14, r8
0x180003518  mov     esi, edx
0x18000351a  mov     rdi, rcx
0x18000351d  mov     r15, [rbp+13F0h+arg_28]
0x180003524  xor     edx, edx; Val
0x180003526  mov     r8d, 98h; Size
0x18000352c  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180003531  call    memset_0
0x180003536  nop
0x180003537  xor     r13d, r13d
0x18000353a  mov     [rbp+13F0h+OutputString], r13w
0x180003542  mov     [rbp+13F0h+var_1430], r13b
0x180003546  mov     rbx, [rbp+13F0h+arg_30]
0x18000354d  mov     ecx, [rbx]; this
0x18000354f  mov     [rsp+14F0h+var_14C8], ecx
0x180003553  mov     eax, [rbx+4]
0x180003556  mov     [rsp+14F0h+var_14C4], eax
0x18000355a  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000355f  mov     r12d, eax
0x180003562  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x18000356a  mov     ecx, r13d
0x18000356d  lea     eax, [r13+8]
0x180003571  cmp     dword ptr [rbx+8], 1
0x180003575  cmovz   ecx, eax
0x180003578  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x18000357c  lea     ecx, [rax-7]
0x18000357f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180003587  inc     ecx
0x180003589  mov     [rsp+14F0h+var_14C0], ecx
0x18000358d  mov     rcx, [rbp+13F0h+arg_38]
0x180003594  test    rcx, rcx
0x180003597  jz      short loc_1800035A4
0x180003599  cmp     [rcx], r13w
0x18000359d  mov     [rsp+14F0h+var_14B8], rcx
0x1800035a2  jnz     short loc_1800035A9
0x1800035a4  mov     [rsp+14F0h+var_14B8], r13
0x1800035a9  call    cs:__imp_GetCurrentThreadId
0x1800035af  mov     [rsp+14F0h+var_14B0], eax
0x1800035b3  mov     [rsp+14F0h+var_1498], r14
0x1800035b8  mov     [rsp+14F0h+var_1490], esi
0x1800035bc  mov     [rsp+14F0h+var_148C], r12d
0x1800035c1  mov     [rsp+14F0h+var_14A8], r13
0x1800035c6  mov     [rsp+14F0h+var_14A0], r13
0x1800035cb  mov     [rbp+13F0h+var_1448], r15
0x1800035cf  mov     [rbp+13F0h+var_1440], rdi
0x1800035d3  mov     [rsp+14F0h+var_1488], r13
0x1800035d8  xorps   xmm0, xmm0
0x1800035db  xor     eax, eax
0x1800035dd  movups  [rbp+13F0h+var_1468], xmm0
0x1800035e1  mov     [rbp+13F0h+var_1458], rax
0x1800035e5  xorps   xmm1, xmm1
0x1800035e8  movups  [rsp+14F0h+var_1480], xmm1
0x1800035ed  mov     [rbp+13F0h+var_1470], rax
0x1800035f1  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800035f8  test    rax, rax
0x1800035fb  jz      short loc_180003608
0x1800035fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003602  mov     [rbp+13F0h+var_1450], rax
0x180003606  jmp     short loc_18000360C
0x180003608  mov     [rbp+13F0h+var_1450], r13
0x18000360c  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180003613  test    rax, rax
0x180003616  jz      short loc_180003622
0x180003618  lea     rcx, [rsp+14F0h+var_14D0]
0x18000361d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003622  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180003629  test    rax, rax
0x18000362c  jz      short loc_180003642
0x18000362e  mov     r8d, 400h
0x180003634  lea     rdx, [rbp+13F0h+var_1430]
0x180003638  lea     rcx, [rsp+14F0h+var_14D0]
0x18000363d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003642  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003649  test    rax, rax
0x18000364c  jz      short loc_180003658
0x18000364e  lea     rcx, [rsp+14F0h+var_14D0]
0x180003653  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003658  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000365f  test    rax, rax
0x180003662  jz      short loc_180003675
0x180003664  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180003669  jnz     short loc_180003675
0x18000366b  lea     rcx, [rsp+14F0h+var_14D0]
0x180003670  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003675  cmp     [rsp+14F0h+var_14C8], r13d
0x18000367a  jl      short loc_18000368E
0x18000367c  mov     ecx, 8000FFFFh; this
0x180003681  mov     [rsp+14F0h+var_14C8], ecx
0x180003685  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000368a  mov     [rsp+14F0h+var_14C4], eax
0x18000368e  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x180003695  jnz     short loc_1800036B6
0x180003697  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000369e  test    rax, rax
0x1800036a1  jz      short loc_1800036AC
0x1800036a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800036a8  test    al, al
0x1800036aa  jmp     short loc_1800036B4
0x1800036ac  call    cs:__imp_IsDebuggerPresent
0x1800036b2  test    eax, eax
0x1800036b4  jz      short loc_1800036BD
0x1800036b6  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800036bb  jz      short loc_1800036E3
0x1800036bd  mov     rax, cs:g_pfnResultLoggingCallback
0x1800036c4  test    rax, rax
0x1800036c7  jz      short loc_18000373C
0x1800036c9  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x1800036d0  jnz     short loc_18000373C
0x1800036d2  xor     r8d, r8d
0x1800036d5  xor     edx, edx
0x1800036d7  lea     rcx, [rsp+14F0h+var_14D0]
0x1800036dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800036e1  jmp     short loc_18000373C
0x1800036e3  mov     ebx, 800h
0x1800036e8  mov     rax, cs:g_pfnResultLoggingCallback
0x1800036ef  test    rax, rax
0x1800036f2  jz      short loc_180003711
0x1800036f4  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x1800036fb  jnz     short loc_180003711
0x1800036fd  mov     r8d, ebx
0x180003700  lea     rdx, [rbp+13F0h+OutputString]
0x180003707  lea     rcx, [rsp+14F0h+var_14D0]
0x18000370c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003711  cmp     [rbp+13F0h+OutputString], r13w
0x180003719  jnz     short loc_18000372F
0x18000371b  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180003720  mov     rdx, rbx; unsigned __int16 *
0x180003723  lea     rcx, [rbp+13F0h+OutputString]; this
0x18000372a  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000372f  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180003736  call    cs:__imp_OutputDebugStringW
0x18000373c  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180003741  jnz     short loc_18000374C
0x180003743  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x18000374a  jz      short loc_18000375E
0x18000374c  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180003753  test    rax, rax
0x180003756  jz      short loc_18000375E
0x180003758  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000375d  nop
0x18000375e  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180003763  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
