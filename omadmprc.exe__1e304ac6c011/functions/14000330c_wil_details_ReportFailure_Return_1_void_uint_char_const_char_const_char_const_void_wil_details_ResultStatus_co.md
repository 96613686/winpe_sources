# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x14000330c`
- end: `0x1400035ac`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `672`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x140002dcc`

## callees

- `0x14000271f`
- `0x14000330c`
- `0x140005604`
- `0x1400073d8`
- `0x140009b3c`
- `0x140009e10`
- `0x140015690`
- `0x140015750`
- `0x140017010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400033ba`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400033ba`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1400034b4`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1400034b4`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140003544`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140003544`

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
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (__int64)&v17, v15);
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
0x14000330c  push    rbp
0x14000330e  push    rbx
0x14000330f  push    rsi
0x140003310  push    rdi
0x140003311  push    r12
0x140003313  push    r14
0x140003315  push    r15
0x140003317  lea     rbp, [rsp-13D0h]
0x14000331f  mov     eax, 14D0h
0x140003324  call    _alloca_probe
0x140003329  sub     rsp, rax
0x14000332c  mov     rax, cs:__security_cookie
0x140003333  xor     rax, rsp
0x140003336  mov     [rbp+1400h+var_40], rax
0x14000333d  mov     r14, r8
0x140003340  mov     esi, edx
0x140003342  mov     r15, rcx
0x140003345  mov     rdi, [rbp+1400h+arg_28]
0x14000334c  xor     edx, edx; Val
0x14000334e  mov     r8d, 98h; Size
0x140003354  lea     rcx, [rsp+1500h+var_14E0]; void *
0x140003359  call    memset_0
0x14000335e  nop
0x14000335f  xor     r12d, r12d
0x140003362  mov     [rbp+1400h+OutputString], r12w
0x14000336a  mov     [rbp+1400h+var_1440], r12b
0x14000336e  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x140003375  mov     ecx, [rdx]; this
0x140003377  mov     [rsp+1500h+var_14D8], ecx
0x14000337b  mov     eax, [rdx+4]
0x14000337e  mov     [rsp+1500h+var_14D4], eax
0x140003382  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x140003387  mov     ebx, eax
0x140003389  mov     dword ptr [rsp+1500h+var_14E0], 1
0x140003391  mov     ecx, r12d
0x140003394  lea     eax, [r12+8]
0x140003399  cmp     dword ptr [rdx+8], 1
0x14000339d  cmovz   ecx, eax
0x1400033a0  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x1400033a4  lea     ecx, [rax-7]
0x1400033a7  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1400033af  inc     ecx
0x1400033b1  mov     [rsp+1500h+var_14D0], ecx
0x1400033b5  mov     [rsp+1500h+var_14C8], r12
0x1400033ba  call    cs:__imp_GetCurrentThreadId
0x1400033c1  nop     dword ptr [rax+rax+00h]
0x1400033c6  mov     [rsp+1500h+var_14C0], eax
0x1400033ca  mov     [rsp+1500h+var_14A8], r14
0x1400033cf  mov     [rsp+1500h+var_14A0], esi
0x1400033d3  mov     [rsp+1500h+var_149C], ebx
0x1400033d7  mov     [rsp+1500h+var_14B8], r12
0x1400033dc  mov     [rsp+1500h+var_14B0], r12
0x1400033e1  mov     [rbp+1400h+var_1458], rdi
0x1400033e5  mov     [rbp+1400h+var_1450], r15
0x1400033e9  mov     [rsp+1500h+var_1498], r12
0x1400033ee  xorps   xmm0, xmm0
0x1400033f1  xor     eax, eax
0x1400033f3  movups  [rbp+1400h+var_1478], xmm0
0x1400033f7  mov     [rbp+1400h+var_1468], rax
0x1400033fb  xorps   xmm1, xmm1
0x1400033fe  movups  [rsp+1500h+var_1490], xmm1
0x140003403  mov     [rbp+1400h+var_1480], rax
0x140003407  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x14000340e  test    rax, rax
0x140003411  jz      short loc_14000341E
0x140003413  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003418  mov     [rbp+1400h+var_1460], rax
0x14000341c  jmp     short loc_140003422
0x14000341e  mov     [rbp+1400h+var_1460], r12
0x140003422  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140003429  test    rax, rax
0x14000342c  jz      short loc_140003438
0x14000342e  lea     rcx, [rsp+1500h+var_14E0]
0x140003433  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003438  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x14000343f  test    rax, rax
0x140003442  jz      short loc_140003458
0x140003444  mov     r8d, 400h
0x14000344a  lea     rdx, [rbp+1400h+var_1440]
0x14000344e  lea     rcx, [rsp+1500h+var_14E0]
0x140003453  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003458  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14000345f  test    rax, rax
0x140003462  jz      short loc_14000346E
0x140003464  lea     rcx, [rsp+1500h+var_14E0]
0x140003469  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000346e  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140003475  test    rax, rax
0x140003478  jz      short loc_14000348B
0x14000347a  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x14000347f  jnz     short loc_14000348B
0x140003481  lea     rcx, [rsp+1500h+var_14E0]
0x140003486  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000348b  cmp     [rsp+1500h+var_14D8], r12d
0x140003490  jge     loc_1400035A6
0x140003496  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x14000349d  jnz     short loc_1400034C4
0x14000349f  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1400034a6  test    rax, rax
0x1400034a9  jz      short loc_1400034B4
0x1400034ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400034b0  test    al, al
0x1400034b2  jmp     short loc_1400034C2
0x1400034b4  call    cs:__imp_IsDebuggerPresent
0x1400034bb  nop     dword ptr [rax+rax+00h]
0x1400034c0  test    eax, eax
0x1400034c2  jz      short loc_1400034CB
0x1400034c4  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1400034c9  jz      short loc_1400034F1
0x1400034cb  mov     rax, cs:g_pfnResultLoggingCallback
0x1400034d2  test    rax, rax
0x1400034d5  jz      short loc_140003550
0x1400034d7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1400034de  jnz     short loc_140003550
0x1400034e0  xor     r8d, r8d
0x1400034e3  xor     edx, edx
0x1400034e5  lea     rcx, [rsp+1500h+var_14E0]
0x1400034ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400034ef  jmp     short loc_140003550
0x1400034f1  mov     ebx, 800h
0x1400034f6  mov     rax, cs:g_pfnResultLoggingCallback
0x1400034fd  test    rax, rax
0x140003500  jz      short loc_14000351F
0x140003502  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x140003509  jnz     short loc_14000351F
0x14000350b  mov     r8d, ebx
0x14000350e  lea     rdx, [rbp+1400h+OutputString]
0x140003515  lea     rcx, [rsp+1500h+var_14E0]
0x14000351a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000351f  cmp     [rbp+1400h+OutputString], r12w
0x140003527  jnz     short loc_14000353D
0x140003529  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x14000352e  mov     rdx, rbx; unsigned __int16 *
0x140003531  lea     rcx, [rbp+1400h+OutputString]; this
0x140003538  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x14000353d  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x140003544  call    cs:__imp_OutputDebugStringW
0x14000354b  nop     dword ptr [rax+rax+00h]
0x140003550  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x140003555  jnz     short loc_140003560
0x140003557  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x14000355e  jz      short loc_140003572
0x140003560  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140003567  test    rax, rax
0x14000356a  jz      short loc_140003572
0x14000356c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003571  nop
0x140003572  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x140003577  jnz     short loc_14000359B
0x140003579  mov     rcx, [rbp+1400h+var_40]
0x140003580  xor     rcx, rsp; StackCookie
0x140003583  call    __security_check_cookie
0x140003588  add     rsp, 14D0h
0x14000358f  pop     r15
0x140003591  pop     r14
0x140003593  pop     r12
0x140003595  pop     rdi
0x140003596  pop     rsi
0x140003597  pop     rbx
0x140003598  pop     rbp
0x140003599  retn
0x14000359b  lea     rcx, [rsp+1500h+var_14E0]; this
0x1400035a0  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x1400035a6  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
