# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x140002568`
- end: `0x1400027fe`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `662`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x140001eb8`

## callees

- `0x140001460`
- `0x140001e56`
- `0x140002568`
- `0x140003784`
- `0x140004720`
- `0x1400056c0`
- `0x14000579c`
- `0x140005d00`
- `0x140006010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140002613`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140002613`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140002798`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140002798`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x14000270e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x14000270e`

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
0x140002568  mov     [rsp-8+arg_10], rbx
0x14000256d  push    rbp
0x14000256e  push    rsi
0x14000256f  push    rdi
0x140002570  push    r14
0x140002572  push    r15
0x140002574  lea     rbp, [rsp-13D0h]
0x14000257c  mov     eax, 14D0h
0x140002581  call    _alloca_probe
0x140002586  sub     rsp, rax
0x140002589  mov     rax, cs:__security_cookie
0x140002590  xor     rax, rsp
0x140002593  mov     [rbp+13F0h+var_30], rax
0x14000259a  mov     esi, edx
0x14000259c  mov     r14, rcx
0x14000259f  mov     rdi, [rbp+13F0h+arg_28]
0x1400025a6  xor     edx, edx; Val
0x1400025a8  mov     r8d, 98h; Size
0x1400025ae  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x1400025b3  call    memset_0
0x1400025b8  nop
0x1400025b9  xor     r15d, r15d
0x1400025bc  mov     [rbp+13F0h+OutputString], r15w
0x1400025c4  mov     [rbp+13F0h+var_1430], r15b
0x1400025c8  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x1400025cf  mov     ecx, [rdx]; this
0x1400025d1  mov     [rsp+14F0h+var_14C8], ecx
0x1400025d5  mov     eax, [rdx+4]
0x1400025d8  mov     [rsp+14F0h+var_14C4], eax
0x1400025dc  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1400025e1  mov     ebx, eax
0x1400025e3  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x1400025eb  mov     ecx, r15d
0x1400025ee  lea     eax, [r15+8]
0x1400025f2  cmp     dword ptr [rdx+8], 1
0x1400025f6  cmovz   ecx, eax
0x1400025f9  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x1400025fd  lea     ecx, [rax-7]
0x140002600  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140002608  inc     ecx
0x14000260a  mov     [rsp+14F0h+var_14C0], ecx
0x14000260e  mov     [rsp+14F0h+var_14B8], r15
0x140002613  call    cs:__imp_GetCurrentThreadId
0x140002619  mov     [rsp+14F0h+var_14B0], eax
0x14000261d  lea     rax, aWil; "wil"
0x140002624  mov     [rsp+14F0h+var_1498], rax
0x140002629  mov     [rsp+14F0h+var_1490], esi
0x14000262d  mov     [rsp+14F0h+var_148C], ebx
0x140002631  mov     [rsp+14F0h+var_14A8], r15
0x140002636  mov     [rsp+14F0h+var_14A0], r15
0x14000263b  mov     [rbp+13F0h+var_1448], rdi
0x14000263f  mov     [rbp+13F0h+var_1440], r14
0x140002643  mov     [rsp+14F0h+var_1488], r15
0x140002648  xorps   xmm0, xmm0
0x14000264b  xor     eax, eax
0x14000264d  movups  [rbp+13F0h+var_1468], xmm0
0x140002651  mov     [rbp+13F0h+var_1458], rax
0x140002655  xorps   xmm1, xmm1
0x140002658  movups  [rsp+14F0h+var_1480], xmm1
0x14000265d  mov     [rbp+13F0h+var_1470], rax
0x140002661  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140002668  test    rax, rax
0x14000266b  jz      short loc_140002678
0x14000266d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002672  mov     [rbp+13F0h+var_1450], rax
0x140002676  jmp     short loc_14000267C
0x140002678  mov     [rbp+13F0h+var_1450], r15
0x14000267c  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140002683  test    rax, rax
0x140002686  jz      short loc_140002692
0x140002688  lea     rcx, [rsp+14F0h+var_14D0]
0x14000268d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002692  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140002699  test    rax, rax
0x14000269c  jz      short loc_1400026B2
0x14000269e  mov     r8d, 400h
0x1400026a4  lea     rdx, [rbp+13F0h+var_1430]
0x1400026a8  lea     rcx, [rsp+14F0h+var_14D0]
0x1400026ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400026b2  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1400026b9  test    rax, rax
0x1400026bc  jz      short loc_1400026C8
0x1400026be  lea     rcx, [rsp+14F0h+var_14D0]
0x1400026c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400026c8  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1400026cf  test    rax, rax
0x1400026d2  jz      short loc_1400026E5
0x1400026d4  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1400026d9  jnz     short loc_1400026E5
0x1400026db  lea     rcx, [rsp+14F0h+var_14D0]
0x1400026e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400026e5  cmp     [rsp+14F0h+var_14C8], r15d
0x1400026ea  jge     loc_1400027F8
0x1400026f0  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x1400026f7  jnz     short loc_140002718
0x1400026f9  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140002700  test    rax, rax
0x140002703  jz      short loc_14000270E
0x140002705  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000270a  test    al, al
0x14000270c  jmp     short loc_140002716
0x14000270e  call    cs:__imp_IsDebuggerPresent
0x140002714  test    eax, eax
0x140002716  jz      short loc_14000271F
0x140002718  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x14000271d  jz      short loc_140002745
0x14000271f  mov     rax, cs:g_pfnResultLoggingCallback
0x140002726  test    rax, rax
0x140002729  jz      short loc_14000279E
0x14000272b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x140002732  jnz     short loc_14000279E
0x140002734  xor     r8d, r8d
0x140002737  xor     edx, edx
0x140002739  lea     rcx, [rsp+14F0h+var_14D0]
0x14000273e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002743  jmp     short loc_14000279E
0x140002745  mov     ebx, 800h
0x14000274a  mov     rax, cs:g_pfnResultLoggingCallback
0x140002751  test    rax, rax
0x140002754  jz      short loc_140002773
0x140002756  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x14000275d  jnz     short loc_140002773
0x14000275f  mov     r8d, ebx
0x140002762  lea     rdx, [rbp+13F0h+OutputString]
0x140002769  lea     rcx, [rsp+14F0h+var_14D0]
0x14000276e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002773  cmp     [rbp+13F0h+OutputString], r15w
0x14000277b  jnz     short loc_140002791
0x14000277d  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x140002782  mov     rdx, rbx; unsigned __int16 *
0x140002785  lea     rcx, [rbp+13F0h+OutputString]; this
0x14000278c  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x140002791  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x140002798  call    cs:__imp_OutputDebugStringW
0x14000279e  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x1400027a3  jnz     short loc_1400027AE
0x1400027a5  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x1400027ac  jz      short loc_1400027C0
0x1400027ae  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1400027b5  test    rax, rax
0x1400027b8  jz      short loc_1400027C0
0x1400027ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400027bf  nop
0x1400027c0  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x1400027c5  jnz     short loc_1400027ED
0x1400027c7  mov     rcx, [rbp+13F0h+var_30]
0x1400027ce  xor     rcx, rsp; StackCookie
0x1400027d1  call    __security_check_cookie
0x1400027d6  mov     rbx, [rsp+14F0h+arg_10]
0x1400027de  add     rsp, 14D0h
0x1400027e5  pop     r15
0x1400027e7  pop     r14
0x1400027e9  pop     rdi
0x1400027ea  pop     rsi
0x1400027eb  pop     rbp
0x1400027ec  retn
0x1400027ed  lea     rcx, [rsp+14F0h+var_14D0]; this
0x1400027f2  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x1400027f8  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
