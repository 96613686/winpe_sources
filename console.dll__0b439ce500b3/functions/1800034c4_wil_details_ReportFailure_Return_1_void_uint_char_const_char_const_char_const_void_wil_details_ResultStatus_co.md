# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x1800034c4`
- end: `0x18000377d`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `697`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180003148`

## callees

- `0x1800015b0`
- `0x180002088`
- `0x1800034c4`
- `0x1800043c4`
- `0x180005594`
- `0x180006260`
- `0x18000633c`
- `0x180018ca0`
- `0x18001a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000358a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000358a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003685`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003685`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003715`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003715`

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
      g_pfnResultLoggingCallback(&v18, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v18, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (wchar_t *)0x800, (unsigned __int64)&v18, v16);
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
0x1800034c4  push    rbp
0x1800034c6  push    rbx
0x1800034c7  push    rsi
0x1800034c8  push    rdi
0x1800034c9  push    r12
0x1800034cb  push    r14
0x1800034cd  push    r15
0x1800034cf  lea     rbp, [rsp-13D0h]
0x1800034d7  mov     eax, 14D0h
0x1800034dc  call    _alloca_probe
0x1800034e1  sub     rsp, rax
0x1800034e4  mov     rax, cs:__security_cookie
0x1800034eb  xor     rax, rsp
0x1800034ee  mov     [rbp+1400h+var_40], rax
0x1800034f5  mov     rsi, r8
0x1800034f8  mov     edi, edx
0x1800034fa  mov     rbx, rcx
0x1800034fd  mov     r14, [rbp+1400h+arg_28]
0x180003504  xor     edx, edx; Val
0x180003506  mov     r8d, 98h; Size
0x18000350c  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180003511  call    memset_0
0x180003516  nop
0x180003517  xor     r12d, r12d
0x18000351a  mov     [rbp+1400h+OutputString], r12w
0x180003522  mov     [rbp+1400h+var_1440], r12b
0x180003526  mov     rdx, [rbp+1400h+arg_30]; int
0x18000352d  mov     ecx, [rdx]; this
0x18000352f  mov     [rsp+1500h+var_14D8], ecx
0x180003533  mov     eax, [rdx+4]
0x180003536  mov     [rsp+1500h+var_14D4], eax
0x18000353a  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000353f  mov     r15d, eax
0x180003542  mov     dword ptr [rsp+1500h+var_14E0], 1
0x18000354a  mov     ecx, r12d
0x18000354d  lea     eax, [r12+8]
0x180003552  cmp     dword ptr [rdx+8], 1
0x180003556  cmovz   ecx, eax
0x180003559  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x18000355d  lea     ecx, [rax-7]
0x180003560  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180003568  inc     ecx
0x18000356a  mov     [rsp+1500h+var_14D0], ecx
0x18000356e  mov     rcx, [rbp+1400h+arg_38]
0x180003575  test    rcx, rcx
0x180003578  jz      short loc_180003585
0x18000357a  cmp     [rcx], r12w
0x18000357e  mov     [rsp+1500h+var_14C8], rcx
0x180003583  jnz     short loc_18000358A
0x180003585  mov     [rsp+1500h+var_14C8], r12
0x18000358a  call    cs:__imp_GetCurrentThreadId
0x180003591  nop     dword ptr [rax+rax+00h]
0x180003596  mov     [rsp+1500h+var_14C0], eax
0x18000359a  mov     [rsp+1500h+var_14A8], rsi
0x18000359f  mov     [rsp+1500h+var_14A0], edi
0x1800035a3  mov     [rsp+1500h+var_149C], r15d
0x1800035a8  mov     [rsp+1500h+var_14B8], r12
0x1800035ad  mov     [rsp+1500h+var_14B0], r12
0x1800035b2  mov     [rbp+1400h+var_1458], r14
0x1800035b6  mov     [rbp+1400h+var_1450], rbx
0x1800035ba  mov     [rsp+1500h+var_1498], r12
0x1800035bf  xorps   xmm0, xmm0
0x1800035c2  xor     eax, eax
0x1800035c4  movups  [rbp+1400h+var_1478], xmm0
0x1800035c8  mov     [rbp+1400h+var_1468], rax
0x1800035cc  xorps   xmm1, xmm1
0x1800035cf  movups  [rsp+1500h+var_1490], xmm1
0x1800035d4  mov     [rbp+1400h+var_1480], rax
0x1800035d8  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800035df  test    rax, rax
0x1800035e2  jz      short loc_1800035EF
0x1800035e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800035e9  mov     [rbp+1400h+var_1460], rax
0x1800035ed  jmp     short loc_1800035F3
0x1800035ef  mov     [rbp+1400h+var_1460], r12
0x1800035f3  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800035fa  test    rax, rax
0x1800035fd  jz      short loc_180003609
0x1800035ff  lea     rcx, [rsp+1500h+var_14E0]
0x180003604  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003609  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180003610  test    rax, rax
0x180003613  jz      short loc_180003629
0x180003615  mov     r8d, 400h
0x18000361b  lea     rdx, [rbp+1400h+var_1440]
0x18000361f  lea     rcx, [rsp+1500h+var_14E0]
0x180003624  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003629  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003630  test    rax, rax
0x180003633  jz      short loc_18000363F
0x180003635  lea     rcx, [rsp+1500h+var_14E0]
0x18000363a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000363f  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003646  test    rax, rax
0x180003649  jz      short loc_18000365C
0x18000364b  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180003650  jnz     short loc_18000365C
0x180003652  lea     rcx, [rsp+1500h+var_14E0]
0x180003657  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000365c  cmp     [rsp+1500h+var_14D8], r12d
0x180003661  jge     loc_180003777
0x180003667  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x18000366e  jnz     short loc_180003695
0x180003670  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180003677  test    rax, rax
0x18000367a  jz      short loc_180003685
0x18000367c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003681  test    al, al
0x180003683  jmp     short loc_180003693
0x180003685  call    cs:__imp_IsDebuggerPresent
0x18000368c  nop     dword ptr [rax+rax+00h]
0x180003691  test    eax, eax
0x180003693  jz      short loc_18000369C
0x180003695  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18000369a  jz      short loc_1800036C2
0x18000369c  mov     rax, cs:g_pfnResultLoggingCallback
0x1800036a3  test    rax, rax
0x1800036a6  jz      short loc_180003721
0x1800036a8  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800036af  jnz     short loc_180003721
0x1800036b1  xor     r8d, r8d
0x1800036b4  xor     edx, edx
0x1800036b6  lea     rcx, [rsp+1500h+var_14E0]
0x1800036bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800036c0  jmp     short loc_180003721
0x1800036c2  mov     ebx, 800h
0x1800036c7  mov     rax, cs:g_pfnResultLoggingCallback
0x1800036ce  test    rax, rax
0x1800036d1  jz      short loc_1800036F0
0x1800036d3  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800036da  jnz     short loc_1800036F0
0x1800036dc  mov     r8d, ebx
0x1800036df  lea     rdx, [rbp+1400h+OutputString]
0x1800036e6  lea     rcx, [rsp+1500h+var_14E0]
0x1800036eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800036f0  cmp     [rbp+1400h+OutputString], r12w
0x1800036f8  jnz     short loc_18000370E
0x1800036fa  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x1800036ff  mov     rdx, rbx; wchar_t *
0x180003702  lea     rcx, [rbp+1400h+OutputString]; this
0x180003709  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x18000370e  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180003715  call    cs:__imp_OutputDebugStringW
0x18000371c  nop     dword ptr [rax+rax+00h]
0x180003721  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180003726  jnz     short loc_180003731
0x180003728  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x18000372f  jz      short loc_180003743
0x180003731  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180003738  test    rax, rax
0x18000373b  jz      short loc_180003743
0x18000373d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003742  nop
0x180003743  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180003748  jnz     short loc_18000376C
0x18000374a  mov     rcx, [rbp+1400h+var_40]
0x180003751  xor     rcx, rsp; StackCookie
0x180003754  call    __security_check_cookie
0x180003759  add     rsp, 14D0h
0x180003760  pop     r15
0x180003762  pop     r14
0x180003764  pop     r12
0x180003766  pop     rdi
0x180003767  pop     rsi
0x180003768  pop     rbx
0x180003769  pop     rbp
0x18000376a  retn
0x18000376c  lea     rcx, [rsp+1500h+var_14E0]; this
0x180003771  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180003777  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
