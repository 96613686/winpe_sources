# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x1800035f4`
- end: `0x180003856`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `610`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180003398`

## callees

- `0x180002be8`
- `0x1800035f4`
- `0x1800067f4`
- `0x180007234`
- `0x180008710`
- `0x18000c3b0`
- `0x180013ff0`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003696`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003696`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003799`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003799`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003823`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003823`

## pseudocode

```c
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
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v17, v15);
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
0x1800035f4  mov     [rsp-8+arg_18], rbx
0x1800035f9  push    rbp
0x1800035fa  push    rsi
0x1800035fb  push    rdi
0x1800035fc  push    r12
0x1800035fe  push    r13
0x180003600  push    r14
0x180003602  push    r15
0x180003604  lea     rbp, [rsp-13C0h]
0x18000360c  mov     eax, 14C0h
0x180003611  call    _alloca_probe
0x180003616  sub     rsp, rax
0x180003619  mov     r15, r8
0x18000361c  mov     r14d, edx
0x18000361f  mov     r12, rcx
0x180003622  mov     rsi, [rbp+13F0h+arg_28]
0x180003629  xor     edx, edx; Val
0x18000362b  mov     r8d, 98h; Size
0x180003631  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180003636  call    memset_0
0x18000363b  nop
0x18000363c  xor     r13d, r13d
0x18000363f  mov     [rbp+13F0h+OutputString], r13w
0x180003647  mov     [rbp+13F0h+var_1430], r13b
0x18000364b  mov     rbx, [rbp+13F0h+arg_30]
0x180003652  mov     ecx, [rbx]; this
0x180003654  mov     [rsp+14F0h+var_14C8], ecx
0x180003658  mov     eax, [rbx+4]
0x18000365b  mov     [rsp+14F0h+var_14C4], eax
0x18000365f  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180003664  mov     edi, eax
0x180003666  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x18000366e  mov     ecx, r13d
0x180003671  lea     eax, [r13+8]
0x180003675  cmp     dword ptr [rbx+8], 1
0x180003679  cmovz   ecx, eax
0x18000367c  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180003680  lea     ecx, [rax-7]
0x180003683  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000368b  inc     ecx
0x18000368d  mov     [rsp+14F0h+var_14C0], ecx
0x180003691  mov     [rsp+14F0h+var_14B8], r13
0x180003696  call    cs:__imp_GetCurrentThreadId
0x18000369c  mov     [rsp+14F0h+var_14B0], eax
0x1800036a0  mov     [rsp+14F0h+var_1498], r15
0x1800036a5  mov     [rsp+14F0h+var_1490], r14d
0x1800036aa  mov     [rsp+14F0h+var_148C], edi
0x1800036ae  mov     [rsp+14F0h+var_14A8], r13
0x1800036b3  mov     [rsp+14F0h+var_14A0], r13
0x1800036b8  mov     [rbp+13F0h+var_1448], rsi
0x1800036bc  mov     [rbp+13F0h+var_1440], r12
0x1800036c0  mov     [rsp+14F0h+var_1488], r13
0x1800036c5  xorps   xmm0, xmm0
0x1800036c8  xor     eax, eax
0x1800036ca  movups  [rbp+13F0h+var_1468], xmm0
0x1800036ce  mov     [rbp+13F0h+var_1458], rax
0x1800036d2  xorps   xmm1, xmm1
0x1800036d5  movups  [rsp+14F0h+var_1480], xmm1
0x1800036da  mov     [rbp+13F0h+var_1470], rax
0x1800036de  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800036e5  test    rax, rax
0x1800036e8  jz      short loc_1800036F5
0x1800036ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800036ef  mov     [rbp+13F0h+var_1450], rax
0x1800036f3  jmp     short loc_1800036F9
0x1800036f5  mov     [rbp+13F0h+var_1450], r13
0x1800036f9  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180003700  test    rax, rax
0x180003703  jz      short loc_18000370F
0x180003705  lea     rcx, [rsp+14F0h+var_14D0]
0x18000370a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000370f  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180003716  test    rax, rax
0x180003719  jz      short loc_18000372F
0x18000371b  mov     r8d, 400h
0x180003721  lea     rdx, [rbp+13F0h+var_1430]
0x180003725  lea     rcx, [rsp+14F0h+var_14D0]
0x18000372a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000372f  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003736  test    rax, rax
0x180003739  jz      short loc_180003745
0x18000373b  lea     rcx, [rsp+14F0h+var_14D0]
0x180003740  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003745  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000374c  test    rax, rax
0x18000374f  jz      short loc_180003762
0x180003751  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180003756  jnz     short loc_180003762
0x180003758  lea     rcx, [rsp+14F0h+var_14D0]
0x18000375d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003762  cmp     [rsp+14F0h+var_14C8], r13d
0x180003767  jl      short loc_18000377B
0x180003769  mov     ecx, 8000FFFFh; this
0x18000376e  mov     [rsp+14F0h+var_14C8], ecx
0x180003772  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180003777  mov     [rsp+14F0h+var_14C4], eax
0x18000377b  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x180003782  jnz     short loc_1800037A3
0x180003784  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000378b  test    rax, rax
0x18000378e  jz      short loc_180003799
0x180003790  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003795  test    al, al
0x180003797  jmp     short loc_1800037A1
0x180003799  call    cs:__imp_IsDebuggerPresent
0x18000379f  test    eax, eax
0x1800037a1  jz      short loc_1800037AA
0x1800037a3  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800037a8  jz      short loc_1800037D0
0x1800037aa  mov     rax, cs:g_pfnResultLoggingCallback
0x1800037b1  test    rax, rax
0x1800037b4  jz      short loc_180003829
0x1800037b6  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x1800037bd  jnz     short loc_180003829
0x1800037bf  xor     r8d, r8d
0x1800037c2  xor     edx, edx
0x1800037c4  lea     rcx, [rsp+14F0h+var_14D0]
0x1800037c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800037ce  jmp     short loc_180003829
0x1800037d0  mov     ebx, 800h
0x1800037d5  mov     rax, cs:g_pfnResultLoggingCallback
0x1800037dc  test    rax, rax
0x1800037df  jz      short loc_1800037FE
0x1800037e1  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x1800037e8  jnz     short loc_1800037FE
0x1800037ea  mov     r8d, ebx
0x1800037ed  lea     rdx, [rbp+13F0h+OutputString]
0x1800037f4  lea     rcx, [rsp+14F0h+var_14D0]
0x1800037f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800037fe  cmp     [rbp+13F0h+OutputString], r13w
0x180003806  jnz     short loc_18000381C
0x180003808  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x18000380d  mov     rdx, rbx; unsigned __int16 *
0x180003810  lea     rcx, [rbp+13F0h+OutputString]; this
0x180003817  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000381c  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180003823  call    cs:__imp_OutputDebugStringW
0x180003829  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x18000382e  jnz     short loc_180003839
0x180003830  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x180003837  jz      short loc_18000384B
0x180003839  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180003840  test    rax, rax
0x180003843  jz      short loc_18000384B
0x180003845  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000384a  nop
0x18000384b  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180003850  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
