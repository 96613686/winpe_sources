# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180002750`
- end: `0x1800029dd`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `653`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180002230`

## callees

- `0x180001510`
- `0x1800020c4`
- `0x180002750`
- `0x180004314`
- `0x180005580`
- `0x180007740`
- `0x1800078b4`
- `0x180008080`
- `0x180009010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800027fe`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800027fe`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000297c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000297c`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800028f2`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800028f2`

## pseudocode

```c
void __fastcall wil::details::ReportFailure_Return<1>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7)
{
  int v10; // ebx
  int v11; // ecx
  __int64 v12; // rdx
  const struct wil::FailureInfo *v13; // rdx
  wil::details::in1diag3 *v14; // rcx
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
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v17, 0, 0x98u);
  OutputString[0] = 0;
  v37[0] = 0;
  v19 = *a7;
  v20 = a7[1];
  v10 = wil::details::RecordReturn((wil::details *)(unsigned int)v19, (int)a7);
  v17 = 1;
  v11 = 0;
  if ( *(_DWORD *)(v12 + 8) == 1 )
    v11 = 8;
  v18 = v11;
  v21 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v22 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v26 = a3;
  v27 = a2;
  v28 = v10;
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
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v14);
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
  if ( ((v18 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v14);
  if ( (v18 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v17, v13);
}

```

## disassembly

```asm
0x180002750  push    rbp
0x180002752  push    rbx
0x180002753  push    rsi
0x180002754  push    rdi
0x180002755  push    r12
0x180002757  push    r14
0x180002759  push    r15
0x18000275b  lea     rbp, [rsp-13D0h]
0x180002763  mov     eax, 14D0h
0x180002768  call    _alloca_probe
0x18000276d  sub     rsp, rax
0x180002770  mov     rax, cs:__security_cookie
0x180002777  xor     rax, rsp
0x18000277a  mov     [rbp+1400h+var_40], rax
0x180002781  mov     r14, r8
0x180002784  mov     esi, edx
0x180002786  mov     r15, rcx
0x180002789  mov     rdi, [rbp+1400h+arg_28]
0x180002790  xor     edx, edx; Val
0x180002792  mov     r8d, 98h; Size
0x180002798  lea     rcx, [rsp+1500h+var_14E0]; void *
0x18000279d  call    memset_0
0x1800027a2  nop
0x1800027a3  xor     r12d, r12d
0x1800027a6  mov     [rbp+1400h+OutputString], r12w
0x1800027ae  mov     [rbp+1400h+var_1440], r12b
0x1800027b2  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x1800027b9  mov     ecx, [rdx]; this
0x1800027bb  mov     [rsp+1500h+var_14D8], ecx
0x1800027bf  mov     eax, [rdx+4]
0x1800027c2  mov     [rsp+1500h+var_14D4], eax
0x1800027c6  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800027cb  mov     ebx, eax
0x1800027cd  mov     dword ptr [rsp+1500h+var_14E0], 1
0x1800027d5  mov     ecx, r12d
0x1800027d8  lea     eax, [r12+8]
0x1800027dd  cmp     dword ptr [rdx+8], 1
0x1800027e1  cmovz   ecx, eax
0x1800027e4  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x1800027e8  lea     ecx, [rax-7]
0x1800027eb  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800027f3  inc     ecx
0x1800027f5  mov     [rsp+1500h+var_14D0], ecx
0x1800027f9  mov     [rsp+1500h+var_14C8], r12
0x1800027fe  call    cs:__imp_GetCurrentThreadId
0x180002804  mov     [rsp+1500h+var_14C0], eax
0x180002808  mov     [rsp+1500h+var_14A8], r14
0x18000280d  mov     [rsp+1500h+var_14A0], esi
0x180002811  mov     [rsp+1500h+var_149C], ebx
0x180002815  mov     [rsp+1500h+var_14B8], r12
0x18000281a  mov     [rsp+1500h+var_14B0], r12
0x18000281f  mov     [rbp+1400h+var_1458], rdi
0x180002823  mov     [rbp+1400h+var_1450], r15
0x180002827  mov     [rsp+1500h+var_1498], r12
0x18000282c  xorps   xmm0, xmm0
0x18000282f  xor     eax, eax
0x180002831  movups  [rbp+1400h+var_1478], xmm0
0x180002835  mov     [rbp+1400h+var_1468], rax
0x180002839  xorps   xmm1, xmm1
0x18000283c  movups  [rsp+1500h+var_1490], xmm1
0x180002841  mov     [rbp+1400h+var_1480], rax
0x180002845  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000284c  test    rax, rax
0x18000284f  jz      short loc_18000285C
0x180002851  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002856  mov     [rbp+1400h+var_1460], rax
0x18000285a  jmp     short loc_180002860
0x18000285c  mov     [rbp+1400h+var_1460], r12
0x180002860  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180002867  test    rax, rax
0x18000286a  jz      short loc_180002876
0x18000286c  lea     rcx, [rsp+1500h+var_14E0]
0x180002871  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002876  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000287d  test    rax, rax
0x180002880  jz      short loc_180002896
0x180002882  mov     r8d, 400h
0x180002888  lea     rdx, [rbp+1400h+var_1440]
0x18000288c  lea     rcx, [rsp+1500h+var_14E0]
0x180002891  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002896  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000289d  test    rax, rax
0x1800028a0  jz      short loc_1800028AC
0x1800028a2  lea     rcx, [rsp+1500h+var_14E0]
0x1800028a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800028ac  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800028b3  test    rax, rax
0x1800028b6  jz      short loc_1800028C9
0x1800028b8  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1800028bd  jnz     short loc_1800028C9
0x1800028bf  lea     rcx, [rsp+1500h+var_14E0]
0x1800028c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800028c9  cmp     [rsp+1500h+var_14D8], r12d
0x1800028ce  jge     loc_1800029D7
0x1800028d4  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x1800028db  jnz     short loc_1800028FC
0x1800028dd  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800028e4  test    rax, rax
0x1800028e7  jz      short loc_1800028F2
0x1800028e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800028ee  test    al, al
0x1800028f0  jmp     short loc_1800028FA
0x1800028f2  call    cs:__imp_IsDebuggerPresent
0x1800028f8  test    eax, eax
0x1800028fa  jz      short loc_180002903
0x1800028fc  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180002901  jz      short loc_180002929
0x180002903  mov     rax, cs:g_pfnResultLoggingCallback
0x18000290a  test    rax, rax
0x18000290d  jz      short loc_180002982
0x18000290f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180002916  jnz     short loc_180002982
0x180002918  xor     r8d, r8d
0x18000291b  xor     edx, edx
0x18000291d  lea     rcx, [rsp+1500h+var_14E0]
0x180002922  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002927  jmp     short loc_180002982
0x180002929  mov     ebx, 800h
0x18000292e  mov     rax, cs:g_pfnResultLoggingCallback
0x180002935  test    rax, rax
0x180002938  jz      short loc_180002957
0x18000293a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180002941  jnz     short loc_180002957
0x180002943  mov     r8d, ebx
0x180002946  lea     rdx, [rbp+1400h+OutputString]
0x18000294d  lea     rcx, [rsp+1500h+var_14E0]
0x180002952  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002957  cmp     [rbp+1400h+OutputString], r12w
0x18000295f  jnz     short loc_180002975
0x180002961  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180002966  mov     rdx, rbx; unsigned __int16 *
0x180002969  lea     rcx, [rbp+1400h+OutputString]; this
0x180002970  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180002975  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x18000297c  call    cs:__imp_OutputDebugStringW
0x180002982  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180002987  jnz     short loc_180002992
0x180002989  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180002990  jz      short loc_1800029A4
0x180002992  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180002999  test    rax, rax
0x18000299c  jz      short loc_1800029A4
0x18000299e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800029a3  nop
0x1800029a4  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x1800029a9  jnz     short loc_1800029CC
0x1800029ab  mov     rcx, [rbp+1400h+var_40]
0x1800029b2  xor     rcx, rsp; StackCookie
0x1800029b5  call    __security_check_cookie
0x1800029ba  add     rsp, 14D0h
0x1800029c1  pop     r15
0x1800029c3  pop     r14
0x1800029c5  pop     r12
0x1800029c7  pop     rdi
0x1800029c8  pop     rsi
0x1800029c9  pop     rbx
0x1800029ca  pop     rbp
0x1800029cb  retn
0x1800029cc  lea     rcx, [rsp+1500h+var_14E0]; this
0x1800029d1  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x1800029d7  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
