# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x1400035c0`
- end: `0x140003822`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `610`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1400032e0`

## callees

- `0x1400035c0`
- `0x140006c94`
- `0x1400074e4`
- `0x14000ab50`
- `0x14000b9b0`
- `0x1400187b2`
- `0x1400188a0`
- `0x140019010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140003662`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140003662`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1400037ef`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1400037ef`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140003765`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140003765`

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
0x1400035c0  mov     [rsp-8+arg_18], rbx
0x1400035c5  push    rbp
0x1400035c6  push    rsi
0x1400035c7  push    rdi
0x1400035c8  push    r12
0x1400035ca  push    r13
0x1400035cc  push    r14
0x1400035ce  push    r15
0x1400035d0  lea     rbp, [rsp-13C0h]
0x1400035d8  mov     eax, 14C0h
0x1400035dd  call    _alloca_probe
0x1400035e2  sub     rsp, rax
0x1400035e5  mov     r15, r8
0x1400035e8  mov     r14d, edx
0x1400035eb  mov     r12, rcx
0x1400035ee  mov     rsi, [rbp+13F0h+arg_28]
0x1400035f5  xor     edx, edx; Val
0x1400035f7  mov     r8d, 98h; Size
0x1400035fd  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x140003602  call    memset_0
0x140003607  nop
0x140003608  xor     r13d, r13d
0x14000360b  mov     [rbp+13F0h+OutputString], r13w
0x140003613  mov     [rbp+13F0h+var_1430], r13b
0x140003617  mov     rbx, [rbp+13F0h+arg_30]
0x14000361e  mov     ecx, [rbx]; this
0x140003620  mov     [rsp+14F0h+var_14C8], ecx
0x140003624  mov     eax, [rbx+4]
0x140003627  mov     [rsp+14F0h+var_14C4], eax
0x14000362b  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x140003630  mov     edi, eax
0x140003632  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x14000363a  mov     ecx, r13d
0x14000363d  lea     eax, [r13+8]
0x140003641  cmp     dword ptr [rbx+8], 1
0x140003645  cmovz   ecx, eax
0x140003648  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x14000364c  lea     ecx, [rax-7]
0x14000364f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140003657  inc     ecx
0x140003659  mov     [rsp+14F0h+var_14C0], ecx
0x14000365d  mov     [rsp+14F0h+var_14B8], r13
0x140003662  call    cs:__imp_GetCurrentThreadId
0x140003668  mov     [rsp+14F0h+var_14B0], eax
0x14000366c  mov     [rsp+14F0h+var_1498], r15
0x140003671  mov     [rsp+14F0h+var_1490], r14d
0x140003676  mov     [rsp+14F0h+var_148C], edi
0x14000367a  mov     [rsp+14F0h+var_14A8], r13
0x14000367f  mov     [rsp+14F0h+var_14A0], r13
0x140003684  mov     [rbp+13F0h+var_1448], rsi
0x140003688  mov     [rbp+13F0h+var_1440], r12
0x14000368c  mov     [rsp+14F0h+var_1488], r13
0x140003691  xorps   xmm0, xmm0
0x140003694  xor     eax, eax
0x140003696  movups  [rbp+13F0h+var_1468], xmm0
0x14000369a  mov     [rbp+13F0h+var_1458], rax
0x14000369e  xorps   xmm1, xmm1
0x1400036a1  movups  [rsp+14F0h+var_1480], xmm1
0x1400036a6  mov     [rbp+13F0h+var_1470], rax
0x1400036aa  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1400036b1  test    rax, rax
0x1400036b4  jz      short loc_1400036C1
0x1400036b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400036bb  mov     [rbp+13F0h+var_1450], rax
0x1400036bf  jmp     short loc_1400036C5
0x1400036c1  mov     [rbp+13F0h+var_1450], r13
0x1400036c5  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1400036cc  test    rax, rax
0x1400036cf  jz      short loc_1400036DB
0x1400036d1  lea     rcx, [rsp+14F0h+var_14D0]
0x1400036d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400036db  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1400036e2  test    rax, rax
0x1400036e5  jz      short loc_1400036FB
0x1400036e7  mov     r8d, 400h
0x1400036ed  lea     rdx, [rbp+13F0h+var_1430]
0x1400036f1  lea     rcx, [rsp+14F0h+var_14D0]
0x1400036f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400036fb  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140003702  test    rax, rax
0x140003705  jz      short loc_140003711
0x140003707  lea     rcx, [rsp+14F0h+var_14D0]
0x14000370c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003711  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140003718  test    rax, rax
0x14000371b  jz      short loc_14000372E
0x14000371d  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x140003722  jnz     short loc_14000372E
0x140003724  lea     rcx, [rsp+14F0h+var_14D0]
0x140003729  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000372e  cmp     [rsp+14F0h+var_14C8], r13d
0x140003733  jl      short loc_140003747
0x140003735  mov     ecx, 8000FFFFh; this
0x14000373a  mov     [rsp+14F0h+var_14C8], ecx
0x14000373e  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140003743  mov     [rsp+14F0h+var_14C4], eax
0x140003747  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x14000374e  jnz     short loc_14000376F
0x140003750  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140003757  test    rax, rax
0x14000375a  jz      short loc_140003765
0x14000375c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003761  test    al, al
0x140003763  jmp     short loc_14000376D
0x140003765  call    cs:__imp_IsDebuggerPresent
0x14000376b  test    eax, eax
0x14000376d  jz      short loc_140003776
0x14000376f  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x140003774  jz      short loc_14000379C
0x140003776  mov     rax, cs:g_pfnResultLoggingCallback
0x14000377d  test    rax, rax
0x140003780  jz      short loc_1400037F5
0x140003782  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x140003789  jnz     short loc_1400037F5
0x14000378b  xor     r8d, r8d
0x14000378e  xor     edx, edx
0x140003790  lea     rcx, [rsp+14F0h+var_14D0]
0x140003795  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000379a  jmp     short loc_1400037F5
0x14000379c  mov     ebx, 800h
0x1400037a1  mov     rax, cs:g_pfnResultLoggingCallback
0x1400037a8  test    rax, rax
0x1400037ab  jz      short loc_1400037CA
0x1400037ad  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x1400037b4  jnz     short loc_1400037CA
0x1400037b6  mov     r8d, ebx
0x1400037b9  lea     rdx, [rbp+13F0h+OutputString]
0x1400037c0  lea     rcx, [rsp+14F0h+var_14D0]
0x1400037c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400037ca  cmp     [rbp+13F0h+OutputString], r13w
0x1400037d2  jnz     short loc_1400037E8
0x1400037d4  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x1400037d9  mov     rdx, rbx; unsigned __int16 *
0x1400037dc  lea     rcx, [rbp+13F0h+OutputString]; this
0x1400037e3  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1400037e8  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x1400037ef  call    cs:__imp_OutputDebugStringW
0x1400037f5  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x1400037fa  jnz     short loc_140003805
0x1400037fc  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x140003803  jz      short loc_140003817
0x140003805  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x14000380c  test    rax, rax
0x14000380f  jz      short loc_140003817
0x140003811  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003816  nop
0x140003817  lea     rcx, [rsp+14F0h+var_14D0]; this
0x14000381c  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
