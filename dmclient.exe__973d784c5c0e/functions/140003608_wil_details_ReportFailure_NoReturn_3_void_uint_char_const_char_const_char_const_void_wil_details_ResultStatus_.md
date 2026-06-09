# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x140003608`
- end: `0x14000387c`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `628`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x140003320`

## callees

- `0x140003608`
- `0x140006d84`
- `0x14000764c`
- `0x14000ade0`
- `0x14000bd4c`
- `0x1400195e2`
- `0x1400196d0`
- `0x14001a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400036aa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400036aa`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140003843`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140003843`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1400037b3`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1400037b3`

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
0x140003608  mov     [rsp-8+arg_18], rbx
0x14000360d  push    rbp
0x14000360e  push    rsi
0x14000360f  push    rdi
0x140003610  push    r12
0x140003612  push    r13
0x140003614  push    r14
0x140003616  push    r15
0x140003618  lea     rbp, [rsp-13C0h]
0x140003620  mov     eax, 14C0h
0x140003625  call    _alloca_probe
0x14000362a  sub     rsp, rax
0x14000362d  mov     r15, r8
0x140003630  mov     r14d, edx
0x140003633  mov     r12, rcx
0x140003636  mov     rsi, [rbp+13F0h+arg_28]
0x14000363d  xor     edx, edx; Val
0x14000363f  mov     r8d, 98h; Size
0x140003645  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x14000364a  call    memset_0
0x14000364f  nop
0x140003650  xor     r13d, r13d
0x140003653  mov     [rbp+13F0h+OutputString], r13w
0x14000365b  mov     [rbp+13F0h+var_1430], r13b
0x14000365f  mov     rbx, [rbp+13F0h+arg_30]
0x140003666  mov     ecx, [rbx]; this
0x140003668  mov     [rsp+14F0h+var_14C8], ecx
0x14000366c  mov     eax, [rbx+4]
0x14000366f  mov     [rsp+14F0h+var_14C4], eax
0x140003673  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x140003678  mov     edi, eax
0x14000367a  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x140003682  mov     ecx, r13d
0x140003685  lea     eax, [r13+8]
0x140003689  cmp     dword ptr [rbx+8], 1
0x14000368d  cmovz   ecx, eax
0x140003690  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x140003694  lea     ecx, [rax-7]
0x140003697  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x14000369f  inc     ecx
0x1400036a1  mov     [rsp+14F0h+var_14C0], ecx
0x1400036a5  mov     [rsp+14F0h+var_14B8], r13
0x1400036aa  call    cs:__imp_GetCurrentThreadId
0x1400036b1  nop     dword ptr [rax+rax+00h]
0x1400036b6  mov     [rsp+14F0h+var_14B0], eax
0x1400036ba  mov     [rsp+14F0h+var_1498], r15
0x1400036bf  mov     [rsp+14F0h+var_1490], r14d
0x1400036c4  mov     [rsp+14F0h+var_148C], edi
0x1400036c8  mov     [rsp+14F0h+var_14A8], r13
0x1400036cd  mov     [rsp+14F0h+var_14A0], r13
0x1400036d2  mov     [rbp+13F0h+var_1448], rsi
0x1400036d6  mov     [rbp+13F0h+var_1440], r12
0x1400036da  mov     [rsp+14F0h+var_1488], r13
0x1400036df  xorps   xmm0, xmm0
0x1400036e2  xor     eax, eax
0x1400036e4  movups  [rbp+13F0h+var_1468], xmm0
0x1400036e8  mov     [rbp+13F0h+var_1458], rax
0x1400036ec  xorps   xmm1, xmm1
0x1400036ef  movups  [rsp+14F0h+var_1480], xmm1
0x1400036f4  mov     [rbp+13F0h+var_1470], rax
0x1400036f8  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1400036ff  test    rax, rax
0x140003702  jz      short loc_14000370F
0x140003704  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003709  mov     [rbp+13F0h+var_1450], rax
0x14000370d  jmp     short loc_140003713
0x14000370f  mov     [rbp+13F0h+var_1450], r13
0x140003713  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x14000371a  test    rax, rax
0x14000371d  jz      short loc_140003729
0x14000371f  lea     rcx, [rsp+14F0h+var_14D0]
0x140003724  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003729  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140003730  test    rax, rax
0x140003733  jz      short loc_140003749
0x140003735  mov     r8d, 400h
0x14000373b  lea     rdx, [rbp+13F0h+var_1430]
0x14000373f  lea     rcx, [rsp+14F0h+var_14D0]
0x140003744  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003749  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140003750  test    rax, rax
0x140003753  jz      short loc_14000375F
0x140003755  lea     rcx, [rsp+14F0h+var_14D0]
0x14000375a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000375f  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140003766  test    rax, rax
0x140003769  jz      short loc_14000377C
0x14000376b  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x140003770  jnz     short loc_14000377C
0x140003772  lea     rcx, [rsp+14F0h+var_14D0]
0x140003777  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000377c  cmp     [rsp+14F0h+var_14C8], r13d
0x140003781  jl      short loc_140003795
0x140003783  mov     ecx, 8000FFFFh; this
0x140003788  mov     [rsp+14F0h+var_14C8], ecx
0x14000378c  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140003791  mov     [rsp+14F0h+var_14C4], eax
0x140003795  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x14000379c  jnz     short loc_1400037C3
0x14000379e  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1400037a5  test    rax, rax
0x1400037a8  jz      short loc_1400037B3
0x1400037aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400037af  test    al, al
0x1400037b1  jmp     short loc_1400037C1
0x1400037b3  call    cs:__imp_IsDebuggerPresent
0x1400037ba  nop     dword ptr [rax+rax+00h]
0x1400037bf  test    eax, eax
0x1400037c1  jz      short loc_1400037CA
0x1400037c3  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1400037c8  jz      short loc_1400037F0
0x1400037ca  mov     rax, cs:g_pfnResultLoggingCallback
0x1400037d1  test    rax, rax
0x1400037d4  jz      short loc_14000384F
0x1400037d6  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x1400037dd  jnz     short loc_14000384F
0x1400037df  xor     r8d, r8d
0x1400037e2  xor     edx, edx
0x1400037e4  lea     rcx, [rsp+14F0h+var_14D0]
0x1400037e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400037ee  jmp     short loc_14000384F
0x1400037f0  mov     ebx, 800h
0x1400037f5  mov     rax, cs:g_pfnResultLoggingCallback
0x1400037fc  test    rax, rax
0x1400037ff  jz      short loc_14000381E
0x140003801  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x140003808  jnz     short loc_14000381E
0x14000380a  mov     r8d, ebx
0x14000380d  lea     rdx, [rbp+13F0h+OutputString]
0x140003814  lea     rcx, [rsp+14F0h+var_14D0]
0x140003819  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000381e  cmp     [rbp+13F0h+OutputString], r13w
0x140003826  jnz     short loc_14000383C
0x140003828  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x14000382d  mov     rdx, rbx; unsigned __int16 *
0x140003830  lea     rcx, [rbp+13F0h+OutputString]; this
0x140003837  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x14000383c  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x140003843  call    cs:__imp_OutputDebugStringW
0x14000384a  nop     dword ptr [rax+rax+00h]
0x14000384f  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x140003854  jnz     short loc_14000385F
0x140003856  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x14000385d  jz      short loc_140003871
0x14000385f  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140003866  test    rax, rax
0x140003869  jz      short loc_140003871
0x14000386b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003870  nop
0x140003871  lea     rcx, [rsp+14F0h+var_14D0]; this
0x140003876  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
