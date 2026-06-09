# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x18000a22c`
- end: `0x18000a4d2`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `678`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180009eb8`

## callees

- `0x180007c90`
- `0x180008704`
- `0x18000a22c`
- `0x18000b114`
- `0x18000c250`
- `0x18000cea8`
- `0x18000cfd8`
- `0x1800440a0`
- `0x18004b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a2f2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a2f2`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000a3e7`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000a3e7`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000a471`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000a471`

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
0x18000a22c  push    rbp
0x18000a22e  push    rbx
0x18000a22f  push    rsi
0x18000a230  push    rdi
0x18000a231  push    r12
0x18000a233  push    r14
0x18000a235  push    r15
0x18000a237  lea     rbp, [rsp-13D0h]
0x18000a23f  mov     eax, 14D0h
0x18000a244  call    _alloca_probe
0x18000a249  sub     rsp, rax
0x18000a24c  mov     rax, cs:__security_cookie
0x18000a253  xor     rax, rsp
0x18000a256  mov     [rbp+1400h+var_40], rax
0x18000a25d  mov     rsi, r8
0x18000a260  mov     edi, edx
0x18000a262  mov     rbx, rcx
0x18000a265  mov     r14, [rbp+1400h+arg_28]
0x18000a26c  xor     edx, edx; Val
0x18000a26e  mov     r8d, 98h; Size
0x18000a274  lea     rcx, [rsp+1500h+var_14E0]; void *
0x18000a279  call    memset_0
0x18000a27e  nop
0x18000a27f  xor     r12d, r12d
0x18000a282  mov     [rbp+1400h+OutputString], r12w
0x18000a28a  mov     [rbp+1400h+var_1440], r12b
0x18000a28e  mov     rdx, [rbp+1400h+arg_30]; int
0x18000a295  mov     ecx, [rdx]; this
0x18000a297  mov     [rsp+1500h+var_14D8], ecx
0x18000a29b  mov     eax, [rdx+4]
0x18000a29e  mov     [rsp+1500h+var_14D4], eax
0x18000a2a2  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000a2a7  mov     r15d, eax
0x18000a2aa  mov     dword ptr [rsp+1500h+var_14E0], 1
0x18000a2b2  mov     ecx, r12d
0x18000a2b5  lea     eax, [r12+8]
0x18000a2ba  cmp     dword ptr [rdx+8], 1
0x18000a2be  cmovz   ecx, eax
0x18000a2c1  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x18000a2c5  lea     ecx, [rax-7]
0x18000a2c8  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000a2d0  inc     ecx
0x18000a2d2  mov     [rsp+1500h+var_14D0], ecx
0x18000a2d6  mov     rcx, [rbp+1400h+arg_38]
0x18000a2dd  test    rcx, rcx
0x18000a2e0  jz      short loc_18000A2ED
0x18000a2e2  cmp     [rcx], r12w
0x18000a2e6  mov     [rsp+1500h+var_14C8], rcx
0x18000a2eb  jnz     short loc_18000A2F2
0x18000a2ed  mov     [rsp+1500h+var_14C8], r12
0x18000a2f2  call    cs:__imp_GetCurrentThreadId
0x18000a2f8  mov     [rsp+1500h+var_14C0], eax
0x18000a2fc  mov     [rsp+1500h+var_14A8], rsi
0x18000a301  mov     [rsp+1500h+var_14A0], edi
0x18000a305  mov     [rsp+1500h+var_149C], r15d
0x18000a30a  mov     [rsp+1500h+var_14B8], r12
0x18000a30f  mov     [rsp+1500h+var_14B0], r12
0x18000a314  mov     [rbp+1400h+var_1458], r14
0x18000a318  mov     [rbp+1400h+var_1450], rbx
0x18000a31c  mov     [rsp+1500h+var_1498], r12
0x18000a321  xorps   xmm0, xmm0
0x18000a324  xor     eax, eax
0x18000a326  movups  [rbp+1400h+var_1478], xmm0
0x18000a32a  mov     [rbp+1400h+var_1468], rax
0x18000a32e  xorps   xmm1, xmm1
0x18000a331  movups  [rsp+1500h+var_1490], xmm1
0x18000a336  mov     [rbp+1400h+var_1480], rax
0x18000a33a  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000a341  test    rax, rax
0x18000a344  jz      short loc_18000A351
0x18000a346  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a34b  mov     [rbp+1400h+var_1460], rax
0x18000a34f  jmp     short loc_18000A355
0x18000a351  mov     [rbp+1400h+var_1460], r12
0x18000a355  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000a35c  test    rax, rax
0x18000a35f  jz      short loc_18000A36B
0x18000a361  lea     rcx, [rsp+1500h+var_14E0]
0x18000a366  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a36b  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000a372  test    rax, rax
0x18000a375  jz      short loc_18000A38B
0x18000a377  mov     r8d, 400h
0x18000a37d  lea     rdx, [rbp+1400h+var_1440]
0x18000a381  lea     rcx, [rsp+1500h+var_14E0]
0x18000a386  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a38b  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000a392  test    rax, rax
0x18000a395  jz      short loc_18000A3A1
0x18000a397  lea     rcx, [rsp+1500h+var_14E0]
0x18000a39c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a3a1  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000a3a8  test    rax, rax
0x18000a3ab  jz      short loc_18000A3BE
0x18000a3ad  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18000a3b2  jnz     short loc_18000A3BE
0x18000a3b4  lea     rcx, [rsp+1500h+var_14E0]
0x18000a3b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a3be  cmp     [rsp+1500h+var_14D8], r12d
0x18000a3c3  jge     loc_18000A4CC
0x18000a3c9  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x18000a3d0  jnz     short loc_18000A3F1
0x18000a3d2  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000a3d9  test    rax, rax
0x18000a3dc  jz      short loc_18000A3E7
0x18000a3de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a3e3  test    al, al
0x18000a3e5  jmp     short loc_18000A3EF
0x18000a3e7  call    cs:__imp_IsDebuggerPresent
0x18000a3ed  test    eax, eax
0x18000a3ef  jz      short loc_18000A3F8
0x18000a3f1  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18000a3f6  jz      short loc_18000A41E
0x18000a3f8  mov     rax, cs:g_pfnResultLoggingCallback
0x18000a3ff  test    rax, rax
0x18000a402  jz      short loc_18000A477
0x18000a404  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18000a40b  jnz     short loc_18000A477
0x18000a40d  xor     r8d, r8d
0x18000a410  xor     edx, edx
0x18000a412  lea     rcx, [rsp+1500h+var_14E0]
0x18000a417  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a41c  jmp     short loc_18000A477
0x18000a41e  mov     ebx, 800h
0x18000a423  mov     rax, cs:g_pfnResultLoggingCallback
0x18000a42a  test    rax, rax
0x18000a42d  jz      short loc_18000A44C
0x18000a42f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18000a436  jnz     short loc_18000A44C
0x18000a438  mov     r8d, ebx
0x18000a43b  lea     rdx, [rbp+1400h+OutputString]
0x18000a442  lea     rcx, [rsp+1500h+var_14E0]
0x18000a447  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a44c  cmp     [rbp+1400h+OutputString], r12w
0x18000a454  jnz     short loc_18000A46A
0x18000a456  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x18000a45b  mov     rdx, rbx; wchar_t *
0x18000a45e  lea     rcx, [rbp+1400h+OutputString]; this
0x18000a465  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x18000a46a  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x18000a471  call    cs:__imp_OutputDebugStringW
0x18000a477  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x18000a47c  jnz     short loc_18000A487
0x18000a47e  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x18000a485  jz      short loc_18000A499
0x18000a487  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000a48e  test    rax, rax
0x18000a491  jz      short loc_18000A499
0x18000a493  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a498  nop
0x18000a499  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x18000a49e  jnz     short loc_18000A4C1
0x18000a4a0  mov     rcx, [rbp+1400h+var_40]
0x18000a4a7  xor     rcx, rsp; StackCookie
0x18000a4aa  call    __security_check_cookie
0x18000a4af  add     rsp, 14D0h
0x18000a4b6  pop     r15
0x18000a4b8  pop     r14
0x18000a4ba  pop     r12
0x18000a4bc  pop     rdi
0x18000a4bd  pop     rsi
0x18000a4be  pop     rbx
0x18000a4bf  pop     rbp
0x18000a4c0  retn
0x18000a4c1  lea     rcx, [rsp+1500h+var_14E0]; this
0x18000a4c6  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18000a4cc  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
