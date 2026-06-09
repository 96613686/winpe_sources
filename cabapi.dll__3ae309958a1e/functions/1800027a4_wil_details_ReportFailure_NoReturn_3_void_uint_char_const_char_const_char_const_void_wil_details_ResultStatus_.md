# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions)

- ea: `0x1800027a4`
- end: `0x180002a12`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@@Z`
- size: `622`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180002538`

## callees

- `0x180001fd6`
- `0x1800027a4`
- `0x1800043c4`
- `0x180004ba8`
- `0x180005320`
- `0x1800065b0`
- `0x180013d80`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002853`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002853`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800029df`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800029df`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002955`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002955`

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
  int v17; // [rsp+30h] [rbp-D0h] BYREF
  int v18; // [rsp+34h] [rbp-CCh]
  int v19; // [rsp+38h] [rbp-C8h]
  int v20; // [rsp+3Ch] [rbp-C4h]
  signed __int32 v21; // [rsp+40h] [rbp-C0h]
  __int64 v22; // [rsp+48h] [rbp-B8h]
  DWORD CurrentThreadId; // [rsp+50h] [rbp-B0h]
  __int64 v24; // [rsp+58h] [rbp-A8h]
  __int64 v25; // [rsp+60h] [rbp-A0h]
  __int64 v26; // [rsp+68h] [rbp-98h]
  int v27; // [rsp+70h] [rbp-90h]
  int v28; // [rsp+74h] [rbp-8Ch]
  __int64 v29; // [rsp+78h] [rbp-88h]
  __int128 v30; // [rsp+80h] [rbp-80h]
  __int64 v31; // [rsp+90h] [rbp-70h]
  __int128 v32; // [rsp+98h] [rbp-68h]
  __int64 v33; // [rsp+A8h] [rbp-58h]
  __int64 ModuleName; // [rsp+B0h] [rbp-50h]
  __int64 v35; // [rsp+B8h] [rbp-48h]
  __int64 v36; // [rsp+C0h] [rbp-40h]
  char v37[1024]; // [rsp+D0h] [rbp-30h] BYREF
  WCHAR OutputString[2072]; // [rsp+4D0h] [rbp+3D0h] BYREF

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
      wil::GetFailureLogString((wil *)OutputString, (wchar_t *)0x800, (unsigned __int64)&v17, v15);
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
0x1800027a4  push    rbp
0x1800027a6  push    rsi
0x1800027a7  push    rdi
0x1800027a8  push    r12
0x1800027aa  push    r13
0x1800027ac  push    r14
0x1800027ae  push    r15
0x1800027b0  lea     rbp, [rsp-13D0h]
0x1800027b8  mov     eax, 14D0h
0x1800027bd  call    _alloca_probe
0x1800027c2  sub     rsp, rax
0x1800027c5  mov     [rsp+1500h+var_14E0], 0FFFFFFFFFFFFFFFEh
0x1800027ce  mov     [rsp+1500h+arg_18], rbx
0x1800027d6  mov     r15, r8
0x1800027d9  mov     r14d, edx
0x1800027dc  mov     r12, rcx
0x1800027df  mov     rsi, [rbp+1400h+arg_28]
0x1800027e6  xor     edx, edx; Val
0x1800027e8  mov     r8d, 98h; Size
0x1800027ee  lea     rcx, [rsp+1500h+var_14D0]; void *
0x1800027f3  call    memset_0
0x1800027f8  nop
0x1800027f9  xor     r13d, r13d
0x1800027fc  mov     [rbp+1400h+OutputString], r13w
0x180002804  mov     [rbp+1400h+var_1430], r13b
0x180002808  mov     rbx, [rbp+1400h+arg_30]
0x18000280f  mov     ecx, [rbx]; this
0x180002811  mov     [rsp+1500h+var_14C8], ecx
0x180002815  mov     eax, [rbx+4]
0x180002818  mov     [rsp+1500h+var_14C4], eax
0x18000281c  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180002821  mov     edi, eax
0x180002823  mov     dword ptr [rsp+1500h+var_14D0], 3
0x18000282b  mov     ecx, r13d
0x18000282e  lea     eax, [r13+8]
0x180002832  cmp     dword ptr [rbx+8], 1
0x180002836  cmovz   ecx, eax
0x180002839  mov     dword ptr [rsp+1500h+var_14D0+4], ecx
0x18000283d  lea     ecx, [rax-7]
0x180002840  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180002848  inc     ecx
0x18000284a  mov     [rsp+1500h+var_14C0], ecx
0x18000284e  mov     [rsp+1500h+var_14B8], r13
0x180002853  call    cs:__imp_GetCurrentThreadId
0x180002859  mov     [rsp+1500h+var_14B0], eax
0x18000285d  mov     [rsp+1500h+var_1498], r15
0x180002862  mov     [rsp+1500h+var_1490], r14d
0x180002867  mov     [rsp+1500h+var_148C], edi
0x18000286b  mov     [rsp+1500h+var_14A8], r13
0x180002870  mov     [rsp+1500h+var_14A0], r13
0x180002875  mov     [rbp+1400h+var_1448], rsi
0x180002879  mov     [rbp+1400h+var_1440], r12
0x18000287d  mov     [rsp+1500h+var_1488], r13
0x180002882  xorps   xmm0, xmm0
0x180002885  xor     eax, eax
0x180002887  movups  [rbp+1400h+var_1468], xmm0
0x18000288b  mov     [rbp+1400h+var_1458], rax
0x18000288f  xorps   xmm1, xmm1
0x180002892  movups  [rbp+1400h+var_1480], xmm1
0x180002896  mov     [rbp+1400h+var_1470], rax
0x18000289a  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800028a1  test    rax, rax
0x1800028a4  jz      short loc_1800028B1
0x1800028a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800028ab  mov     [rbp+1400h+var_1450], rax
0x1800028af  jmp     short loc_1800028B5
0x1800028b1  mov     [rbp+1400h+var_1450], r13
0x1800028b5  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800028bc  test    rax, rax
0x1800028bf  jz      short loc_1800028CB
0x1800028c1  lea     rcx, [rsp+1500h+var_14D0]
0x1800028c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800028cb  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800028d2  test    rax, rax
0x1800028d5  jz      short loc_1800028EB
0x1800028d7  mov     r8d, 400h
0x1800028dd  lea     rdx, [rbp+1400h+var_1430]
0x1800028e1  lea     rcx, [rsp+1500h+var_14D0]
0x1800028e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800028eb  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800028f2  test    rax, rax
0x1800028f5  jz      short loc_180002901
0x1800028f7  lea     rcx, [rsp+1500h+var_14D0]
0x1800028fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002901  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002908  test    rax, rax
0x18000290b  jz      short loc_18000291E
0x18000290d  test    byte ptr [rsp+1500h+var_14D0+4], 2
0x180002912  jnz     short loc_18000291E
0x180002914  lea     rcx, [rsp+1500h+var_14D0]
0x180002919  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000291e  cmp     [rsp+1500h+var_14C8], r13d
0x180002923  jl      short loc_180002937
0x180002925  mov     ecx, 8000FFFFh; this
0x18000292a  mov     [rsp+1500h+var_14C8], ecx
0x18000292e  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180002933  mov     [rsp+1500h+var_14C4], eax
0x180002937  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x18000293e  jnz     short loc_18000295F
0x180002940  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180002947  test    rax, rax
0x18000294a  jz      short loc_180002955
0x18000294c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002951  test    al, al
0x180002953  jmp     short loc_18000295D
0x180002955  call    cs:__imp_IsDebuggerPresent
0x18000295b  test    eax, eax
0x18000295d  jz      short loc_180002966
0x18000295f  test    byte ptr [rsp+1500h+var_14D0+4], 2
0x180002964  jz      short loc_18000298C
0x180002966  mov     rax, cs:g_pfnResultLoggingCallback
0x18000296d  test    rax, rax
0x180002970  jz      short loc_1800029E5
0x180002972  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180002979  jnz     short loc_1800029E5
0x18000297b  xor     r8d, r8d
0x18000297e  xor     edx, edx
0x180002980  lea     rcx, [rsp+1500h+var_14D0]
0x180002985  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000298a  jmp     short loc_1800029E5
0x18000298c  mov     ebx, 800h
0x180002991  mov     rax, cs:g_pfnResultLoggingCallback
0x180002998  test    rax, rax
0x18000299b  jz      short loc_1800029BA
0x18000299d  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x1800029a4  jnz     short loc_1800029BA
0x1800029a6  mov     r8d, ebx
0x1800029a9  lea     rdx, [rbp+1400h+OutputString]
0x1800029b0  lea     rcx, [rsp+1500h+var_14D0]
0x1800029b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800029ba  cmp     [rbp+1400h+OutputString], r13w
0x1800029c2  jnz     short loc_1800029D8
0x1800029c4  lea     r8, [rsp+1500h+var_14D0]; unsigned __int64
0x1800029c9  mov     rdx, rbx; wchar_t *
0x1800029cc  lea     rcx, [rbp+1400h+OutputString]; this
0x1800029d3  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x1800029d8  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x1800029df  call    cs:__imp_OutputDebugStringW
0x1800029e5  test    byte ptr [rsp+1500h+var_14D0+4], 4
0x1800029ea  jnz     short loc_1800029F5
0x1800029ec  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x1800029f3  jz      short loc_180002A07
0x1800029f5  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800029fc  test    rax, rax
0x1800029ff  jz      short loc_180002A07
0x180002a01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a06  nop
0x180002a07  lea     rcx, [rsp+1500h+var_14D0]; this
0x180002a0c  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
