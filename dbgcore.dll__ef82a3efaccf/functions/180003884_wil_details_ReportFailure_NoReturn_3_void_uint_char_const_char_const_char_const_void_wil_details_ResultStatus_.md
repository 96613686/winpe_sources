# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180003884`
- end: `0x180003af2`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `622`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180003620`

## callees

- `0x1800021f4`
- `0x1800033d0`
- `0x180003884`
- `0x180007470`
- `0x180008000`
- `0x1800090b0`
- `0x18000baf0`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003932`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003932`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003abf`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003abf`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003a35`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003a35`

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
  __int64 v37; // [rsp+C0h] [rbp-40h]
  char v38[1024]; // [rsp+D0h] [rbp-30h] BYREF
  WCHAR OutputString[2072]; // [rsp+4D0h] [rbp+3D0h] BYREF

  v37 = -2;
  memset_0(&v17, 0, 0x98u);
  OutputString[0] = 0;
  v38[0] = 0;
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
    wil::details::g_pfnGetContextAndNotifyFailure(&v17, v38, 1024);
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
0x180003884  push    rbp
0x180003886  push    rsi
0x180003887  push    rdi
0x180003888  push    r12
0x18000388a  push    r13
0x18000388c  push    r14
0x18000388e  push    r15
0x180003890  lea     rbp, [rsp-13D0h]
0x180003898  mov     eax, 14D0h
0x18000389d  call    _alloca_probe
0x1800038a2  sub     rsp, rax
0x1800038a5  mov     [rbp+1400h+var_1440], 0FFFFFFFFFFFFFFFEh
0x1800038ad  mov     [rsp+1500h+arg_18], rbx
0x1800038b5  mov     r15, r8
0x1800038b8  mov     r14d, edx
0x1800038bb  mov     r12, rcx
0x1800038be  mov     rsi, [rbp+1400h+arg_28]
0x1800038c5  xor     edx, edx; Val
0x1800038c7  mov     r8d, 98h; Size
0x1800038cd  lea     rcx, [rsp+1500h+var_14E0]; void *
0x1800038d2  call    memset_0
0x1800038d7  nop
0x1800038d8  xor     r13d, r13d
0x1800038db  mov     [rbp+1400h+OutputString], r13w
0x1800038e3  mov     [rbp+1400h+var_1430], r13b
0x1800038e7  mov     rbx, [rbp+1400h+arg_30]
0x1800038ee  mov     ecx, [rbx]; this
0x1800038f0  mov     [rsp+1500h+var_14D8], ecx
0x1800038f4  mov     eax, [rbx+4]
0x1800038f7  mov     [rsp+1500h+var_14D4], eax
0x1800038fb  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180003900  mov     edi, eax
0x180003902  mov     dword ptr [rsp+1500h+var_14E0], 3
0x18000390a  mov     ecx, r13d
0x18000390d  lea     eax, [r13+8]
0x180003911  cmp     dword ptr [rbx+8], 1
0x180003915  cmovz   ecx, eax
0x180003918  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x18000391c  lea     ecx, [rax-7]
0x18000391f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180003927  inc     ecx
0x180003929  mov     [rsp+1500h+var_14D0], ecx
0x18000392d  mov     [rsp+1500h+var_14C8], r13
0x180003932  call    cs:__imp_GetCurrentThreadId
0x180003938  mov     [rsp+1500h+var_14C0], eax
0x18000393c  mov     [rsp+1500h+var_14A8], r15
0x180003941  mov     [rsp+1500h+var_14A0], r14d
0x180003946  mov     [rsp+1500h+var_149C], edi
0x18000394a  mov     [rsp+1500h+var_14B8], r13
0x18000394f  mov     [rsp+1500h+var_14B0], r13
0x180003954  mov     [rbp+1400h+var_1458], rsi
0x180003958  mov     [rbp+1400h+var_1450], r12
0x18000395c  mov     [rsp+1500h+var_1498], r13
0x180003961  xorps   xmm0, xmm0
0x180003964  xor     eax, eax
0x180003966  movups  [rbp+1400h+var_1478], xmm0
0x18000396a  mov     [rbp+1400h+var_1468], rax
0x18000396e  xorps   xmm1, xmm1
0x180003971  movups  [rsp+1500h+var_1490], xmm1
0x180003976  mov     [rbp+1400h+var_1480], rax
0x18000397a  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180003981  test    rax, rax
0x180003984  jz      short loc_180003991
0x180003986  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000398b  mov     [rbp+1400h+var_1460], rax
0x18000398f  jmp     short loc_180003995
0x180003991  mov     [rbp+1400h+var_1460], r13
0x180003995  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000399c  test    rax, rax
0x18000399f  jz      short loc_1800039AB
0x1800039a1  lea     rcx, [rsp+1500h+var_14E0]
0x1800039a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800039ab  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800039b2  test    rax, rax
0x1800039b5  jz      short loc_1800039CB
0x1800039b7  mov     r8d, 400h
0x1800039bd  lea     rdx, [rbp+1400h+var_1430]
0x1800039c1  lea     rcx, [rsp+1500h+var_14E0]
0x1800039c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800039cb  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800039d2  test    rax, rax
0x1800039d5  jz      short loc_1800039E1
0x1800039d7  lea     rcx, [rsp+1500h+var_14E0]
0x1800039dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800039e1  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800039e8  test    rax, rax
0x1800039eb  jz      short loc_1800039FE
0x1800039ed  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1800039f2  jnz     short loc_1800039FE
0x1800039f4  lea     rcx, [rsp+1500h+var_14E0]
0x1800039f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800039fe  cmp     [rsp+1500h+var_14D8], r13d
0x180003a03  jl      short loc_180003A17
0x180003a05  mov     ecx, 8000FFFFh; this
0x180003a0a  mov     [rsp+1500h+var_14D8], ecx
0x180003a0e  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180003a13  mov     [rsp+1500h+var_14D4], eax
0x180003a17  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x180003a1e  jnz     short loc_180003A3F
0x180003a20  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180003a27  test    rax, rax
0x180003a2a  jz      short loc_180003A35
0x180003a2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a31  test    al, al
0x180003a33  jmp     short loc_180003A3D
0x180003a35  call    cs:__imp_IsDebuggerPresent
0x180003a3b  test    eax, eax
0x180003a3d  jz      short loc_180003A46
0x180003a3f  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180003a44  jz      short loc_180003A6C
0x180003a46  mov     rax, cs:g_pfnResultLoggingCallback
0x180003a4d  test    rax, rax
0x180003a50  jz      short loc_180003AC5
0x180003a52  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180003a59  jnz     short loc_180003AC5
0x180003a5b  xor     r8d, r8d
0x180003a5e  xor     edx, edx
0x180003a60  lea     rcx, [rsp+1500h+var_14E0]
0x180003a65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a6a  jmp     short loc_180003AC5
0x180003a6c  mov     ebx, 800h
0x180003a71  mov     rax, cs:g_pfnResultLoggingCallback
0x180003a78  test    rax, rax
0x180003a7b  jz      short loc_180003A9A
0x180003a7d  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180003a84  jnz     short loc_180003A9A
0x180003a86  mov     r8d, ebx
0x180003a89  lea     rdx, [rbp+1400h+OutputString]
0x180003a90  lea     rcx, [rsp+1500h+var_14E0]
0x180003a95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a9a  cmp     [rbp+1400h+OutputString], r13w
0x180003aa2  jnz     short loc_180003AB8
0x180003aa4  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180003aa9  mov     rdx, rbx; unsigned __int16 *
0x180003aac  lea     rcx, [rbp+1400h+OutputString]; Buffer
0x180003ab3  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180003ab8  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180003abf  call    cs:__imp_OutputDebugStringW
0x180003ac5  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180003aca  jnz     short loc_180003AD5
0x180003acc  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x180003ad3  jz      short loc_180003AE7
0x180003ad5  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180003adc  test    rax, rax
0x180003adf  jz      short loc_180003AE7
0x180003ae1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ae6  nop
0x180003ae7  lea     rcx, [rsp+1500h+var_14E0]; this
0x180003aec  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
