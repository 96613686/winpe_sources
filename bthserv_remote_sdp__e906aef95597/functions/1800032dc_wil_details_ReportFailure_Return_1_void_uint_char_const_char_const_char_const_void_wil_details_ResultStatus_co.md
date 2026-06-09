# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x1800032dc`
- end: `0x180003595`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `697`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180002d4c`

## callees

- `0x1800017a0`
- `0x18000270c`
- `0x1800032dc`
- `0x1800055c4`
- `0x180007020`
- `0x18000974c`
- `0x180009934`
- `0x180034af0`
- `0x180039010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800033a2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800033a2`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000349d`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000349d`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000352d`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000352d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
  if ( ((v19 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v15);
  if ( (v19 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v18, v14);
}

```

## disassembly

```asm
0x1800032dc  push    rbp
0x1800032de  push    rbx
0x1800032df  push    rsi
0x1800032e0  push    rdi
0x1800032e1  push    r12
0x1800032e3  push    r14
0x1800032e5  push    r15
0x1800032e7  lea     rbp, [rsp-13D0h]
0x1800032ef  mov     eax, 14D0h
0x1800032f4  call    _alloca_probe
0x1800032f9  sub     rsp, rax
0x1800032fc  mov     rax, cs:__security_cookie
0x180003303  xor     rax, rsp
0x180003306  mov     [rbp+1400h+var_40], rax
0x18000330d  mov     rsi, r8
0x180003310  mov     edi, edx
0x180003312  mov     rbx, rcx
0x180003315  mov     r14, [rbp+1400h+arg_28]
0x18000331c  xor     edx, edx; Val
0x18000331e  mov     r8d, 98h; Size
0x180003324  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180003329  call    memset_0
0x18000332e  nop
0x18000332f  xor     r12d, r12d
0x180003332  mov     [rbp+1400h+OutputString], r12w
0x18000333a  mov     [rbp+1400h+var_1440], r12b
0x18000333e  mov     rdx, [rbp+1400h+arg_30]; int
0x180003345  mov     ecx, [rdx]; this
0x180003347  mov     [rsp+1500h+var_14D8], ecx
0x18000334b  mov     eax, [rdx+4]
0x18000334e  mov     [rsp+1500h+var_14D4], eax
0x180003352  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180003357  mov     r15d, eax
0x18000335a  mov     dword ptr [rsp+1500h+var_14E0], 1
0x180003362  mov     ecx, r12d
0x180003365  lea     eax, [r12+8]
0x18000336a  cmp     dword ptr [rdx+8], 1
0x18000336e  cmovz   ecx, eax
0x180003371  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180003375  lea     ecx, [rax-7]
0x180003378  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureInfo *)'::`2'::s_failureId
0x180003380  inc     ecx
0x180003382  mov     [rsp+1500h+var_14D0], ecx
0x180003386  mov     rcx, [rbp+1400h+arg_38]
0x18000338d  test    rcx, rcx
0x180003390  jz      short loc_18000339D
0x180003392  cmp     [rcx], r12w
0x180003396  mov     [rsp+1500h+var_14C8], rcx
0x18000339b  jnz     short loc_1800033A2
0x18000339d  mov     [rsp+1500h+var_14C8], r12
0x1800033a2  call    cs:__imp_GetCurrentThreadId
0x1800033a9  nop     dword ptr [rax+rax+00h]
0x1800033ae  mov     [rsp+1500h+var_14C0], eax
0x1800033b2  mov     [rsp+1500h+var_14A8], rsi
0x1800033b7  mov     [rsp+1500h+var_14A0], edi
0x1800033bb  mov     [rsp+1500h+var_149C], r15d
0x1800033c0  mov     [rsp+1500h+var_14B8], r12
0x1800033c5  mov     [rsp+1500h+var_14B0], r12
0x1800033ca  mov     [rbp+1400h+var_1458], r14
0x1800033ce  mov     [rbp+1400h+var_1450], rbx
0x1800033d2  mov     [rsp+1500h+var_1498], r12
0x1800033d7  xorps   xmm0, xmm0
0x1800033da  xor     eax, eax
0x1800033dc  movups  [rbp+1400h+var_1478], xmm0
0x1800033e0  mov     [rbp+1400h+var_1468], rax
0x1800033e4  xorps   xmm1, xmm1
0x1800033e7  movups  [rsp+1500h+var_1490], xmm1
0x1800033ec  mov     [rbp+1400h+var_1480], rax
0x1800033f0  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800033f7  test    rax, rax
0x1800033fa  jz      short loc_180003407
0x1800033fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003401  mov     [rbp+1400h+var_1460], rax
0x180003405  jmp     short loc_18000340B
0x180003407  mov     [rbp+1400h+var_1460], r12
0x18000340b  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180003412  test    rax, rax
0x180003415  jz      short loc_180003421
0x180003417  lea     rcx, [rsp+1500h+var_14E0]
0x18000341c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003421  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180003428  test    rax, rax
0x18000342b  jz      short loc_180003441
0x18000342d  mov     r8d, 400h
0x180003433  lea     rdx, [rbp+1400h+var_1440]
0x180003437  lea     rcx, [rsp+1500h+var_14E0]
0x18000343c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003441  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003448  test    rax, rax
0x18000344b  jz      short loc_180003457
0x18000344d  lea     rcx, [rsp+1500h+var_14E0]
0x180003452  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003457  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000345e  test    rax, rax
0x180003461  jz      short loc_180003474
0x180003463  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180003468  jnz     short loc_180003474
0x18000346a  lea     rcx, [rsp+1500h+var_14E0]
0x18000346f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003474  cmp     [rsp+1500h+var_14D8], r12d
0x180003479  jge     loc_18000358F
0x18000347f  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180003486  jnz     short loc_1800034AD
0x180003488  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000348f  test    rax, rax
0x180003492  jz      short loc_18000349D
0x180003494  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003499  test    al, al
0x18000349b  jmp     short loc_1800034AB
0x18000349d  call    cs:__imp_IsDebuggerPresent
0x1800034a4  nop     dword ptr [rax+rax+00h]
0x1800034a9  test    eax, eax
0x1800034ab  jz      short loc_1800034B4
0x1800034ad  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1800034b2  jz      short loc_1800034DA
0x1800034b4  mov     rax, cs:g_pfnResultLoggingCallback
0x1800034bb  test    rax, rax
0x1800034be  jz      short loc_180003539
0x1800034c0  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800034c7  jnz     short loc_180003539
0x1800034c9  xor     r8d, r8d
0x1800034cc  xor     edx, edx
0x1800034ce  lea     rcx, [rsp+1500h+var_14E0]
0x1800034d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800034d8  jmp     short loc_180003539
0x1800034da  mov     ebx, 800h
0x1800034df  mov     rax, cs:g_pfnResultLoggingCallback
0x1800034e6  test    rax, rax
0x1800034e9  jz      short loc_180003508
0x1800034eb  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800034f2  jnz     short loc_180003508
0x1800034f4  mov     r8d, ebx
0x1800034f7  lea     rdx, [rbp+1400h+OutputString]
0x1800034fe  lea     rcx, [rsp+1500h+var_14E0]
0x180003503  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003508  cmp     [rbp+1400h+OutputString], r12w
0x180003510  jnz     short loc_180003526
0x180003512  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180003517  mov     rdx, rbx; unsigned __int16 *
0x18000351a  lea     rcx, [rbp+1400h+OutputString]; this
0x180003521  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180003526  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x18000352d  call    cs:__imp_OutputDebugStringW
0x180003534  nop     dword ptr [rax+rax+00h]
0x180003539  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x18000353e  jnz     short loc_180003549
0x180003540  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180003547  jz      short loc_18000355B
0x180003549  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180003550  test    rax, rax
0x180003553  jz      short loc_18000355B
0x180003555  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000355a  nop
0x18000355b  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180003560  jnz     short loc_180003584
0x180003562  mov     rcx, [rbp+1400h+var_40]
0x180003569  xor     rcx, rsp; StackCookie
0x18000356c  call    __security_check_cookie
0x180003571  add     rsp, 14D0h
0x180003578  pop     r15
0x18000357a  pop     r14
0x18000357c  pop     r12
0x18000357e  pop     rdi
0x18000357f  pop     rsi
0x180003580  pop     rbx
0x180003581  pop     rbp
0x180003582  retn
0x180003584  lea     rcx, [rsp+1500h+var_14E0]; this
0x180003589  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18000358f  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
