# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x1400033dc`
- end: `0x140003695`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `697`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x140002e54`

## callees

- `0x1400020b0`
- `0x140002b2c`
- `0x1400033dc`
- `0x140004b34`
- `0x1400069f4`
- `0x140008dcc`
- `0x140008f64`
- `0x14002e860`
- `0x140034010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400034a2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400034a2`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x14000362d`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x14000362d`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x14000359d`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x14000359d`

## pseudocode

```c
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
0x1400033dc  push    rbp
0x1400033de  push    rbx
0x1400033df  push    rsi
0x1400033e0  push    rdi
0x1400033e1  push    r12
0x1400033e3  push    r14
0x1400033e5  push    r15
0x1400033e7  lea     rbp, [rsp-13D0h]
0x1400033ef  mov     eax, 14D0h
0x1400033f4  call    _alloca_probe
0x1400033f9  sub     rsp, rax
0x1400033fc  mov     rax, cs:__security_cookie
0x140003403  xor     rax, rsp
0x140003406  mov     [rbp+1400h+var_40], rax
0x14000340d  mov     rsi, r8
0x140003410  mov     edi, edx
0x140003412  mov     rbx, rcx
0x140003415  mov     r14, [rbp+1400h+arg_28]
0x14000341c  xor     edx, edx; Val
0x14000341e  mov     r8d, 98h; Size
0x140003424  lea     rcx, [rsp+1500h+var_14E0]; void *
0x140003429  call    memset_0
0x14000342e  nop
0x14000342f  xor     r12d, r12d
0x140003432  mov     [rbp+1400h+OutputString], r12w
0x14000343a  mov     [rbp+1400h+var_1440], r12b
0x14000343e  mov     rdx, [rbp+1400h+arg_30]; int
0x140003445  mov     ecx, [rdx]; this
0x140003447  mov     [rsp+1500h+var_14D8], ecx
0x14000344b  mov     eax, [rdx+4]
0x14000344e  mov     [rsp+1500h+var_14D4], eax
0x140003452  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x140003457  mov     r15d, eax
0x14000345a  mov     dword ptr [rsp+1500h+var_14E0], 1
0x140003462  mov     ecx, r12d
0x140003465  lea     eax, [r12+8]
0x14000346a  cmp     dword ptr [rdx+8], 1
0x14000346e  cmovz   ecx, eax
0x140003471  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x140003475  lea     ecx, [rax-7]
0x140003478  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140003480  inc     ecx
0x140003482  mov     [rsp+1500h+var_14D0], ecx
0x140003486  mov     rcx, [rbp+1400h+arg_38]
0x14000348d  test    rcx, rcx
0x140003490  jz      short loc_14000349D
0x140003492  cmp     [rcx], r12w
0x140003496  mov     [rsp+1500h+var_14C8], rcx
0x14000349b  jnz     short loc_1400034A2
0x14000349d  mov     [rsp+1500h+var_14C8], r12
0x1400034a2  call    cs:__imp_GetCurrentThreadId
0x1400034a9  nop     dword ptr [rax+rax+00h]
0x1400034ae  mov     [rsp+1500h+var_14C0], eax
0x1400034b2  mov     [rsp+1500h+var_14A8], rsi
0x1400034b7  mov     [rsp+1500h+var_14A0], edi
0x1400034bb  mov     [rsp+1500h+var_149C], r15d
0x1400034c0  mov     [rsp+1500h+var_14B8], r12
0x1400034c5  mov     [rsp+1500h+var_14B0], r12
0x1400034ca  mov     [rbp+1400h+var_1458], r14
0x1400034ce  mov     [rbp+1400h+var_1450], rbx
0x1400034d2  mov     [rsp+1500h+var_1498], r12
0x1400034d7  xorps   xmm0, xmm0
0x1400034da  xor     eax, eax
0x1400034dc  movups  [rbp+1400h+var_1478], xmm0
0x1400034e0  mov     [rbp+1400h+var_1468], rax
0x1400034e4  xorps   xmm1, xmm1
0x1400034e7  movups  [rsp+1500h+var_1490], xmm1
0x1400034ec  mov     [rbp+1400h+var_1480], rax
0x1400034f0  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1400034f7  test    rax, rax
0x1400034fa  jz      short loc_140003507
0x1400034fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003501  mov     [rbp+1400h+var_1460], rax
0x140003505  jmp     short loc_14000350B
0x140003507  mov     [rbp+1400h+var_1460], r12
0x14000350b  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140003512  test    rax, rax
0x140003515  jz      short loc_140003521
0x140003517  lea     rcx, [rsp+1500h+var_14E0]
0x14000351c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003521  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140003528  test    rax, rax
0x14000352b  jz      short loc_140003541
0x14000352d  mov     r8d, 400h
0x140003533  lea     rdx, [rbp+1400h+var_1440]
0x140003537  lea     rcx, [rsp+1500h+var_14E0]
0x14000353c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003541  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140003548  test    rax, rax
0x14000354b  jz      short loc_140003557
0x14000354d  lea     rcx, [rsp+1500h+var_14E0]
0x140003552  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003557  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14000355e  test    rax, rax
0x140003561  jz      short loc_140003574
0x140003563  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x140003568  jnz     short loc_140003574
0x14000356a  lea     rcx, [rsp+1500h+var_14E0]
0x14000356f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003574  cmp     [rsp+1500h+var_14D8], r12d
0x140003579  jge     loc_14000368F
0x14000357f  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x140003586  jnz     short loc_1400035AD
0x140003588  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x14000358f  test    rax, rax
0x140003592  jz      short loc_14000359D
0x140003594  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003599  test    al, al
0x14000359b  jmp     short loc_1400035AB
0x14000359d  call    cs:__imp_IsDebuggerPresent
0x1400035a4  nop     dword ptr [rax+rax+00h]
0x1400035a9  test    eax, eax
0x1400035ab  jz      short loc_1400035B4
0x1400035ad  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1400035b2  jz      short loc_1400035DA
0x1400035b4  mov     rax, cs:g_pfnResultLoggingCallback
0x1400035bb  test    rax, rax
0x1400035be  jz      short loc_140003639
0x1400035c0  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1400035c7  jnz     short loc_140003639
0x1400035c9  xor     r8d, r8d
0x1400035cc  xor     edx, edx
0x1400035ce  lea     rcx, [rsp+1500h+var_14E0]
0x1400035d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400035d8  jmp     short loc_140003639
0x1400035da  mov     ebx, 800h
0x1400035df  mov     rax, cs:g_pfnResultLoggingCallback
0x1400035e6  test    rax, rax
0x1400035e9  jz      short loc_140003608
0x1400035eb  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1400035f2  jnz     short loc_140003608
0x1400035f4  mov     r8d, ebx
0x1400035f7  lea     rdx, [rbp+1400h+OutputString]
0x1400035fe  lea     rcx, [rsp+1500h+var_14E0]
0x140003603  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003608  cmp     [rbp+1400h+OutputString], r12w
0x140003610  jnz     short loc_140003626
0x140003612  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x140003617  mov     rdx, rbx; unsigned __int16 *
0x14000361a  lea     rcx, [rbp+1400h+OutputString]; this
0x140003621  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x140003626  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x14000362d  call    cs:__imp_OutputDebugStringW
0x140003634  nop     dword ptr [rax+rax+00h]
0x140003639  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x14000363e  jnz     short loc_140003649
0x140003640  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x140003647  jz      short loc_14000365B
0x140003649  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140003650  test    rax, rax
0x140003653  jz      short loc_14000365B
0x140003655  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000365a  nop
0x14000365b  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x140003660  jnz     short loc_140003684
0x140003662  mov     rcx, [rbp+1400h+var_40]
0x140003669  xor     rcx, rsp; StackCookie
0x14000366c  call    __security_check_cookie
0x140003671  add     rsp, 14D0h
0x140003678  pop     r15
0x14000367a  pop     r14
0x14000367c  pop     r12
0x14000367e  pop     rdi
0x14000367f  pop     rsi
0x140003680  pop     rbx
0x140003681  pop     rbp
0x140003682  retn
0x140003684  lea     rcx, [rsp+1500h+var_14E0]; this
0x140003689  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x14000368f  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
