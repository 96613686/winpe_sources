# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180004740`
- end: `0x1800049e6`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `678`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800041dc`

## callees

- `0x180004740`
- `0x180005fa4`
- `0x1800070a0`
- `0x1800083c0`
- `0x18000863c`
- `0x180033e9a`
- `0x180033ed0`
- `0x180033f90`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004806`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004806`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180004985`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180004985`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800048fb`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800048fb`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall wil::details::ReportFailure_Return<1>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7,
        _WORD *a8)
{
  int v11; // r15d
  int v12; // ecx
  __int64 v13; // rdx
  const struct wil::FailureInfo *v14; // rdx
  wil::details::in1diag3 *v15; // rcx
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
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v18, 0, 0x98u);
  OutputString[0] = 0;
  v38[0] = 0;
  v20 = *a7;
  v21 = a7[1];
  v11 = wil::details::RecordReturn((wil::details *)(unsigned int)v20, (int)a7);
  v18 = 1;
  v12 = 0;
  if ( *(_DWORD *)(v13 + 8) == 1 )
    v12 = 8;
  v19 = v12;
  v22 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  if ( !a8 || (v17 = *a8 == 0, v23 = a8, v17) )
    v23 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v27 = a3;
  v28 = a2;
  v29 = v11;
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
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v15);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v17 = !IsDebuggerPresent())
      : (v17 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v15) == 0),
        v17)
    || (v19 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v18, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v18, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v18, v16);
    OutputDebugStringW(OutputString);
  }
  if ( ((v19 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v15);
  if ( (v19 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v18, v14);
}

```

## disassembly

```asm
0x180004740  push    rbp
0x180004742  push    rbx
0x180004743  push    rsi
0x180004744  push    rdi
0x180004745  push    r12
0x180004747  push    r14
0x180004749  push    r15
0x18000474b  lea     rbp, [rsp-13D0h]
0x180004753  mov     eax, 14D0h
0x180004758  call    _alloca_probe
0x18000475d  sub     rsp, rax
0x180004760  mov     rax, cs:__security_cookie
0x180004767  xor     rax, rsp
0x18000476a  mov     [rbp+1400h+var_40], rax
0x180004771  mov     rsi, r8
0x180004774  mov     edi, edx
0x180004776  mov     rbx, rcx
0x180004779  mov     r14, [rbp+1400h+arg_28]
0x180004780  xor     edx, edx; Val
0x180004782  mov     r8d, 98h; Size
0x180004788  lea     rcx, [rsp+1500h+var_14E0]; void *
0x18000478d  call    memset_0
0x180004792  nop
0x180004793  xor     r12d, r12d
0x180004796  mov     [rbp+1400h+OutputString], r12w
0x18000479e  mov     [rbp+1400h+var_1440], r12b
0x1800047a2  mov     rdx, [rbp+1400h+arg_30]; int
0x1800047a9  mov     ecx, [rdx]; this
0x1800047ab  mov     [rsp+1500h+var_14D8], ecx
0x1800047af  mov     eax, [rdx+4]
0x1800047b2  mov     [rsp+1500h+var_14D4], eax
0x1800047b6  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800047bb  mov     r15d, eax
0x1800047be  mov     dword ptr [rsp+1500h+var_14E0], 1
0x1800047c6  mov     ecx, r12d
0x1800047c9  lea     eax, [r12+8]
0x1800047ce  cmp     dword ptr [rdx+8], 1
0x1800047d2  cmovz   ecx, eax
0x1800047d5  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x1800047d9  lea     ecx, [rax-7]
0x1800047dc  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800047e4  inc     ecx
0x1800047e6  mov     [rsp+1500h+var_14D0], ecx
0x1800047ea  mov     rcx, [rbp+1400h+arg_38]
0x1800047f1  test    rcx, rcx
0x1800047f4  jz      short loc_180004801
0x1800047f6  cmp     [rcx], r12w
0x1800047fa  mov     [rsp+1500h+var_14C8], rcx
0x1800047ff  jnz     short loc_180004806
0x180004801  mov     [rsp+1500h+var_14C8], r12
0x180004806  call    cs:__imp_GetCurrentThreadId
0x18000480c  mov     [rsp+1500h+var_14C0], eax
0x180004810  mov     [rsp+1500h+var_14A8], rsi
0x180004815  mov     [rsp+1500h+var_14A0], edi
0x180004819  mov     [rsp+1500h+var_149C], r15d
0x18000481e  mov     [rsp+1500h+var_14B8], r12
0x180004823  mov     [rsp+1500h+var_14B0], r12
0x180004828  mov     [rbp+1400h+var_1458], r14
0x18000482c  mov     [rbp+1400h+var_1450], rbx
0x180004830  mov     [rsp+1500h+var_1498], r12
0x180004835  xorps   xmm0, xmm0
0x180004838  xor     eax, eax
0x18000483a  movups  [rbp+1400h+var_1478], xmm0
0x18000483e  mov     [rbp+1400h+var_1468], rax
0x180004842  xorps   xmm1, xmm1
0x180004845  movups  [rsp+1500h+var_1490], xmm1
0x18000484a  mov     [rbp+1400h+var_1480], rax
0x18000484e  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180004855  test    rax, rax
0x180004858  jz      short loc_180004865
0x18000485a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000485f  mov     [rbp+1400h+var_1460], rax
0x180004863  jmp     short loc_180004869
0x180004865  mov     [rbp+1400h+var_1460], r12
0x180004869  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180004870  test    rax, rax
0x180004873  jz      short loc_18000487F
0x180004875  lea     rcx, [rsp+1500h+var_14E0]
0x18000487a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000487f  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180004886  test    rax, rax
0x180004889  jz      short loc_18000489F
0x18000488b  mov     r8d, 400h
0x180004891  lea     rdx, [rbp+1400h+var_1440]
0x180004895  lea     rcx, [rsp+1500h+var_14E0]
0x18000489a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000489f  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800048a6  test    rax, rax
0x1800048a9  jz      short loc_1800048B5
0x1800048ab  lea     rcx, [rsp+1500h+var_14E0]
0x1800048b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800048b5  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800048bc  test    rax, rax
0x1800048bf  jz      short loc_1800048D2
0x1800048c1  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1800048c6  jnz     short loc_1800048D2
0x1800048c8  lea     rcx, [rsp+1500h+var_14E0]
0x1800048cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800048d2  cmp     [rsp+1500h+var_14D8], r12d
0x1800048d7  jge     loc_1800049E0
0x1800048dd  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x1800048e4  jnz     short loc_180004905
0x1800048e6  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800048ed  test    rax, rax
0x1800048f0  jz      short loc_1800048FB
0x1800048f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800048f7  test    al, al
0x1800048f9  jmp     short loc_180004903
0x1800048fb  call    cs:__imp_IsDebuggerPresent
0x180004901  test    eax, eax
0x180004903  jz      short loc_18000490C
0x180004905  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18000490a  jz      short loc_180004932
0x18000490c  mov     rax, cs:g_pfnResultLoggingCallback
0x180004913  test    rax, rax
0x180004916  jz      short loc_18000498B
0x180004918  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18000491f  jnz     short loc_18000498B
0x180004921  xor     r8d, r8d
0x180004924  xor     edx, edx
0x180004926  lea     rcx, [rsp+1500h+var_14E0]
0x18000492b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004930  jmp     short loc_18000498B
0x180004932  mov     ebx, 800h
0x180004937  mov     rax, cs:g_pfnResultLoggingCallback
0x18000493e  test    rax, rax
0x180004941  jz      short loc_180004960
0x180004943  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18000494a  jnz     short loc_180004960
0x18000494c  mov     r8d, ebx
0x18000494f  lea     rdx, [rbp+1400h+OutputString]
0x180004956  lea     rcx, [rsp+1500h+var_14E0]
0x18000495b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004960  cmp     [rbp+1400h+OutputString], r12w
0x180004968  jnz     short loc_18000497E
0x18000496a  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x18000496f  mov     rdx, rbx; unsigned __int16 *
0x180004972  lea     rcx, [rbp+1400h+OutputString]; this
0x180004979  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000497e  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180004985  call    cs:__imp_OutputDebugStringW
0x18000498b  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180004990  jnz     short loc_18000499B
0x180004992  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180004999  jz      short loc_1800049AD
0x18000499b  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800049a2  test    rax, rax
0x1800049a5  jz      short loc_1800049AD
0x1800049a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800049ac  nop
0x1800049ad  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x1800049b2  jnz     short loc_1800049D5
0x1800049b4  mov     rcx, [rbp+1400h+var_40]
0x1800049bb  xor     rcx, rsp; StackCookie
0x1800049be  call    __security_check_cookie
0x1800049c3  add     rsp, 14D0h
0x1800049ca  pop     r15
0x1800049cc  pop     r14
0x1800049ce  pop     r12
0x1800049d0  pop     rdi
0x1800049d1  pop     rsi
0x1800049d2  pop     rbx
0x1800049d3  pop     rbp
0x1800049d4  retn
0x1800049d5  lea     rcx, [rsp+1500h+var_14E0]; this
0x1800049da  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x1800049e0  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
