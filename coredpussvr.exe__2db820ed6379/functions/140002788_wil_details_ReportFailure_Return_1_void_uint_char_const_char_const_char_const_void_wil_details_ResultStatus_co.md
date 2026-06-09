# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x140002788`
- end: `0x140002a31`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `681`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x140002254`

## callees

- `0x140001500`
- `0x14000215c`
- `0x140002788`
- `0x1400035e4`
- `0x1400047c4`
- `0x1400055fc`
- `0x1400056d8`
- `0x140009030`
- `0x14000a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140002833`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140002833`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1400029c4`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1400029c4`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140002934`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140002934`

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
0x140002788  mov     [rsp-8+arg_10], rbx
0x14000278d  push    rbp
0x14000278e  push    rsi
0x14000278f  push    rdi
0x140002790  push    r14
0x140002792  push    r15
0x140002794  lea     rbp, [rsp-13D0h]
0x14000279c  mov     eax, 14D0h
0x1400027a1  call    _alloca_probe
0x1400027a6  sub     rsp, rax
0x1400027a9  mov     rax, cs:__security_cookie
0x1400027b0  xor     rax, rsp
0x1400027b3  mov     [rbp+13F0h+var_30], rax
0x1400027ba  mov     esi, edx
0x1400027bc  mov     r14, rcx
0x1400027bf  mov     rdi, [rbp+13F0h+arg_28]
0x1400027c6  xor     edx, edx; Val
0x1400027c8  mov     r8d, 98h; Size
0x1400027ce  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x1400027d3  call    memset_0
0x1400027d8  nop
0x1400027d9  xor     r15d, r15d
0x1400027dc  mov     [rbp+13F0h+OutputString], r15w
0x1400027e4  mov     [rbp+13F0h+var_1430], r15b
0x1400027e8  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x1400027ef  mov     ecx, [rdx]; this
0x1400027f1  mov     [rsp+14F0h+var_14C8], ecx
0x1400027f5  mov     eax, [rdx+4]
0x1400027f8  mov     [rsp+14F0h+var_14C4], eax
0x1400027fc  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x140002801  mov     ebx, eax
0x140002803  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x14000280b  mov     ecx, r15d
0x14000280e  lea     eax, [r15+8]
0x140002812  cmp     dword ptr [rdx+8], 1
0x140002816  cmovz   ecx, eax
0x140002819  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x14000281d  lea     ecx, [rax-7]
0x140002820  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140002828  inc     ecx
0x14000282a  mov     [rsp+14F0h+var_14C0], ecx
0x14000282e  mov     [rsp+14F0h+var_14B8], r15
0x140002833  call    cs:__imp_GetCurrentThreadId
0x14000283a  nop     dword ptr [rax+rax+00h]
0x14000283f  mov     [rsp+14F0h+var_14B0], eax
0x140002843  lea     rax, aWil; "wil"
0x14000284a  mov     [rsp+14F0h+var_1498], rax
0x14000284f  mov     [rsp+14F0h+var_1490], esi
0x140002853  mov     [rsp+14F0h+var_148C], ebx
0x140002857  mov     [rsp+14F0h+var_14A8], r15
0x14000285c  mov     [rsp+14F0h+var_14A0], r15
0x140002861  mov     [rbp+13F0h+var_1448], rdi
0x140002865  mov     [rbp+13F0h+var_1440], r14
0x140002869  mov     [rsp+14F0h+var_1488], r15
0x14000286e  xorps   xmm0, xmm0
0x140002871  xor     eax, eax
0x140002873  movups  [rbp+13F0h+var_1468], xmm0
0x140002877  mov     [rbp+13F0h+var_1458], rax
0x14000287b  xorps   xmm1, xmm1
0x14000287e  movups  [rsp+14F0h+var_1480], xmm1
0x140002883  mov     [rbp+13F0h+var_1470], rax
0x140002887  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x14000288e  test    rax, rax
0x140002891  jz      short loc_14000289E
0x140002893  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002898  mov     [rbp+13F0h+var_1450], rax
0x14000289c  jmp     short loc_1400028A2
0x14000289e  mov     [rbp+13F0h+var_1450], r15
0x1400028a2  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1400028a9  test    rax, rax
0x1400028ac  jz      short loc_1400028B8
0x1400028ae  lea     rcx, [rsp+14F0h+var_14D0]
0x1400028b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400028b8  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1400028bf  test    rax, rax
0x1400028c2  jz      short loc_1400028D8
0x1400028c4  mov     r8d, 400h
0x1400028ca  lea     rdx, [rbp+13F0h+var_1430]
0x1400028ce  lea     rcx, [rsp+14F0h+var_14D0]
0x1400028d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400028d8  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1400028df  test    rax, rax
0x1400028e2  jz      short loc_1400028EE
0x1400028e4  lea     rcx, [rsp+14F0h+var_14D0]
0x1400028e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400028ee  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1400028f5  test    rax, rax
0x1400028f8  jz      short loc_14000290B
0x1400028fa  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1400028ff  jnz     short loc_14000290B
0x140002901  lea     rcx, [rsp+14F0h+var_14D0]
0x140002906  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000290b  cmp     [rsp+14F0h+var_14C8], r15d
0x140002910  jge     loc_140002A2B
0x140002916  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x14000291d  jnz     short loc_140002944
0x14000291f  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140002926  test    rax, rax
0x140002929  jz      short loc_140002934
0x14000292b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002930  test    al, al
0x140002932  jmp     short loc_140002942
0x140002934  call    cs:__imp_IsDebuggerPresent
0x14000293b  nop     dword ptr [rax+rax+00h]
0x140002940  test    eax, eax
0x140002942  jz      short loc_14000294B
0x140002944  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x140002949  jz      short loc_140002971
0x14000294b  mov     rax, cs:g_pfnResultLoggingCallback
0x140002952  test    rax, rax
0x140002955  jz      short loc_1400029D0
0x140002957  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x14000295e  jnz     short loc_1400029D0
0x140002960  xor     r8d, r8d
0x140002963  xor     edx, edx
0x140002965  lea     rcx, [rsp+14F0h+var_14D0]
0x14000296a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000296f  jmp     short loc_1400029D0
0x140002971  mov     ebx, 800h
0x140002976  mov     rax, cs:g_pfnResultLoggingCallback
0x14000297d  test    rax, rax
0x140002980  jz      short loc_14000299F
0x140002982  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x140002989  jnz     short loc_14000299F
0x14000298b  mov     r8d, ebx
0x14000298e  lea     rdx, [rbp+13F0h+OutputString]
0x140002995  lea     rcx, [rsp+14F0h+var_14D0]
0x14000299a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000299f  cmp     [rbp+13F0h+OutputString], r15w
0x1400029a7  jnz     short loc_1400029BD
0x1400029a9  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x1400029ae  mov     rdx, rbx; unsigned __int16 *
0x1400029b1  lea     rcx, [rbp+13F0h+OutputString]; this
0x1400029b8  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1400029bd  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x1400029c4  call    cs:__imp_OutputDebugStringW
0x1400029cb  nop     dword ptr [rax+rax+00h]
0x1400029d0  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x1400029d5  jnz     short loc_1400029E0
0x1400029d7  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x1400029de  jz      short loc_1400029F2
0x1400029e0  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1400029e7  test    rax, rax
0x1400029ea  jz      short loc_1400029F2
0x1400029ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400029f1  nop
0x1400029f2  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x1400029f7  jnz     short loc_140002A20
0x1400029f9  mov     rcx, [rbp+13F0h+var_30]
0x140002a00  xor     rcx, rsp; StackCookie
0x140002a03  call    __security_check_cookie
0x140002a08  mov     rbx, [rsp+14F0h+arg_10]
0x140002a10  add     rsp, 14D0h
0x140002a17  pop     r15
0x140002a19  pop     r14
0x140002a1b  pop     rdi
0x140002a1c  pop     rsi
0x140002a1d  pop     rbp
0x140002a1e  retn
0x140002a20  lea     rcx, [rsp+14F0h+var_14D0]; this
0x140002a25  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x140002a2b  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
