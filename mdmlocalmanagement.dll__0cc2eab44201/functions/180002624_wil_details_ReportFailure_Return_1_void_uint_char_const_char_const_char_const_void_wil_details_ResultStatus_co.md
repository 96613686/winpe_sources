# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180002624`
- end: `0x1800028cd`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `681`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800020f0`

## callees

- `0x180001660`
- `0x180001fea`
- `0x180002624`
- `0x1800034b4`
- `0x1800046a4`
- `0x1800054fc`
- `0x1800055d8`
- `0x180006a90`
- `0x180007010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800026cf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800026cf`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180002860`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180002860`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800027d0`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800027d0`

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
        int *a7)
{
  int v9; // ebx
  int v10; // ecx
  __int64 v11; // rdx
  const struct wil::FailureInfo *v12; // rdx
  wil::details::in1diag3 *v13; // rcx
  const struct wil::FailureInfo *v14; // r9
  bool v15; // zf
  int v16; // [rsp+20h] [rbp-E0h] BYREF
  int v17; // [rsp+24h] [rbp-DCh]
  int v18; // [rsp+28h] [rbp-D8h]
  int v19; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v20; // [rsp+30h] [rbp-D0h]
  __int64 v21; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v23; // [rsp+48h] [rbp-B8h]
  __int64 v24; // [rsp+50h] [rbp-B0h]
  const char *v25; // [rsp+58h] [rbp-A8h]
  int v26; // [rsp+60h] [rbp-A0h]
  int v27; // [rsp+64h] [rbp-9Ch]
  __int64 v28; // [rsp+68h] [rbp-98h]
  __int128 v29; // [rsp+70h] [rbp-90h]
  __int64 v30; // [rsp+80h] [rbp-80h]
  __int128 v31; // [rsp+88h] [rbp-78h]
  __int64 v32; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v34; // [rsp+A8h] [rbp-58h]
  __int64 v35; // [rsp+B0h] [rbp-50h]
  char v36[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v16, 0, 0x98u);
  OutputString[0] = 0;
  v36[0] = 0;
  v18 = *a7;
  v19 = a7[1];
  v9 = wil::details::RecordReturn((wil::details *)(unsigned int)v18, (int)a7);
  v16 = 1;
  v10 = 0;
  if ( *(_DWORD *)(v11 + 8) == 1 )
    v10 = 8;
  v17 = v10;
  v20 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v21 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v25 = "wil";
  v26 = a2;
  v27 = v9;
  v23 = 0;
  v24 = 0;
  v34 = a6;
  v35 = a1;
  v28 = 0;
  v31 = 0;
  v32 = 0;
  v29 = 0;
  v30 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v13);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v16);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v16, v36, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v16);
  if ( wil::details::g_pfnOriginateCallback && (v17 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v16);
  if ( v18 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v13);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v15 = !IsDebuggerPresent())
      : (v15 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v13) == 0),
        v15)
    || (v17 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v16, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v16, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v16, v14);
    OutputDebugStringW(OutputString);
  }
  if ( ((v17 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v13);
  if ( (v17 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v16, v12);
}

```

## disassembly

```asm
0x180002624  mov     [rsp-8+arg_10], rbx
0x180002629  push    rbp
0x18000262a  push    rsi
0x18000262b  push    rdi
0x18000262c  push    r14
0x18000262e  push    r15
0x180002630  lea     rbp, [rsp-13D0h]
0x180002638  mov     eax, 14D0h
0x18000263d  call    _alloca_probe
0x180002642  sub     rsp, rax
0x180002645  mov     rax, cs:__security_cookie
0x18000264c  xor     rax, rsp
0x18000264f  mov     [rbp+13F0h+var_30], rax
0x180002656  mov     esi, edx
0x180002658  mov     r14, rcx
0x18000265b  mov     rdi, [rbp+13F0h+arg_28]
0x180002662  xor     edx, edx; Val
0x180002664  mov     r8d, 98h; Size
0x18000266a  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x18000266f  call    memset_0
0x180002674  nop
0x180002675  xor     r15d, r15d
0x180002678  mov     [rbp+13F0h+OutputString], r15w
0x180002680  mov     [rbp+13F0h+var_1430], r15b
0x180002684  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x18000268b  mov     ecx, [rdx]; this
0x18000268d  mov     [rsp+14F0h+var_14C8], ecx
0x180002691  mov     eax, [rdx+4]
0x180002694  mov     [rsp+14F0h+var_14C4], eax
0x180002698  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000269d  mov     ebx, eax
0x18000269f  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x1800026a7  mov     ecx, r15d
0x1800026aa  lea     eax, [r15+8]
0x1800026ae  cmp     dword ptr [rdx+8], 1
0x1800026b2  cmovz   ecx, eax
0x1800026b5  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x1800026b9  lea     ecx, [rax-7]
0x1800026bc  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800026c4  inc     ecx
0x1800026c6  mov     [rsp+14F0h+var_14C0], ecx
0x1800026ca  mov     [rsp+14F0h+var_14B8], r15
0x1800026cf  call    cs:__imp_GetCurrentThreadId
0x1800026d6  nop     dword ptr [rax+rax+00h]
0x1800026db  mov     [rsp+14F0h+var_14B0], eax
0x1800026df  lea     rax, aWil; "wil"
0x1800026e6  mov     [rsp+14F0h+var_1498], rax
0x1800026eb  mov     [rsp+14F0h+var_1490], esi
0x1800026ef  mov     [rsp+14F0h+var_148C], ebx
0x1800026f3  mov     [rsp+14F0h+var_14A8], r15
0x1800026f8  mov     [rsp+14F0h+var_14A0], r15
0x1800026fd  mov     [rbp+13F0h+var_1448], rdi
0x180002701  mov     [rbp+13F0h+var_1440], r14
0x180002705  mov     [rsp+14F0h+var_1488], r15
0x18000270a  xorps   xmm0, xmm0
0x18000270d  xor     eax, eax
0x18000270f  movups  [rbp+13F0h+var_1468], xmm0
0x180002713  mov     [rbp+13F0h+var_1458], rax
0x180002717  xorps   xmm1, xmm1
0x18000271a  movups  [rsp+14F0h+var_1480], xmm1
0x18000271f  mov     [rbp+13F0h+var_1470], rax
0x180002723  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000272a  test    rax, rax
0x18000272d  jz      short loc_18000273A
0x18000272f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002734  mov     [rbp+13F0h+var_1450], rax
0x180002738  jmp     short loc_18000273E
0x18000273a  mov     [rbp+13F0h+var_1450], r15
0x18000273e  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180002745  test    rax, rax
0x180002748  jz      short loc_180002754
0x18000274a  lea     rcx, [rsp+14F0h+var_14D0]
0x18000274f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002754  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000275b  test    rax, rax
0x18000275e  jz      short loc_180002774
0x180002760  mov     r8d, 400h
0x180002766  lea     rdx, [rbp+13F0h+var_1430]
0x18000276a  lea     rcx, [rsp+14F0h+var_14D0]
0x18000276f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002774  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000277b  test    rax, rax
0x18000277e  jz      short loc_18000278A
0x180002780  lea     rcx, [rsp+14F0h+var_14D0]
0x180002785  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000278a  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002791  test    rax, rax
0x180002794  jz      short loc_1800027A7
0x180002796  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000279b  jnz     short loc_1800027A7
0x18000279d  lea     rcx, [rsp+14F0h+var_14D0]
0x1800027a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800027a7  cmp     [rsp+14F0h+var_14C8], r15d
0x1800027ac  jge     loc_1800028C7
0x1800027b2  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x1800027b9  jnz     short loc_1800027E0
0x1800027bb  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800027c2  test    rax, rax
0x1800027c5  jz      short loc_1800027D0
0x1800027c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800027cc  test    al, al
0x1800027ce  jmp     short loc_1800027DE
0x1800027d0  call    cs:__imp_IsDebuggerPresent
0x1800027d7  nop     dword ptr [rax+rax+00h]
0x1800027dc  test    eax, eax
0x1800027de  jz      short loc_1800027E7
0x1800027e0  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800027e5  jz      short loc_18000280D
0x1800027e7  mov     rax, cs:g_pfnResultLoggingCallback
0x1800027ee  test    rax, rax
0x1800027f1  jz      short loc_18000286C
0x1800027f3  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800027fa  jnz     short loc_18000286C
0x1800027fc  xor     r8d, r8d
0x1800027ff  xor     edx, edx
0x180002801  lea     rcx, [rsp+14F0h+var_14D0]
0x180002806  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000280b  jmp     short loc_18000286C
0x18000280d  mov     ebx, 800h
0x180002812  mov     rax, cs:g_pfnResultLoggingCallback
0x180002819  test    rax, rax
0x18000281c  jz      short loc_18000283B
0x18000281e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180002825  jnz     short loc_18000283B
0x180002827  mov     r8d, ebx
0x18000282a  lea     rdx, [rbp+13F0h+OutputString]
0x180002831  lea     rcx, [rsp+14F0h+var_14D0]
0x180002836  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000283b  cmp     [rbp+13F0h+OutputString], r15w
0x180002843  jnz     short loc_180002859
0x180002845  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x18000284a  mov     rdx, rbx; unsigned __int16 *
0x18000284d  lea     rcx, [rbp+13F0h+OutputString]; this
0x180002854  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180002859  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180002860  call    cs:__imp_OutputDebugStringW
0x180002867  nop     dword ptr [rax+rax+00h]
0x18000286c  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180002871  jnz     short loc_18000287C
0x180002873  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x18000287a  jz      short loc_18000288E
0x18000287c  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180002883  test    rax, rax
0x180002886  jz      short loc_18000288E
0x180002888  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000288d  nop
0x18000288e  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x180002893  jnz     short loc_1800028BC
0x180002895  mov     rcx, [rbp+13F0h+var_30]
0x18000289c  xor     rcx, rsp; StackCookie
0x18000289f  call    __security_check_cookie
0x1800028a4  mov     rbx, [rsp+14F0h+arg_10]
0x1800028ac  add     rsp, 14D0h
0x1800028b3  pop     r15
0x1800028b5  pop     r14
0x1800028b7  pop     rdi
0x1800028b8  pop     rsi
0x1800028b9  pop     rbp
0x1800028ba  retn
0x1800028bc  lea     rcx, [rsp+14F0h+var_14D0]; this
0x1800028c1  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x1800028c7  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
