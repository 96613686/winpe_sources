# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x18001180c`
- end: `0x180011ab2`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `678`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18000f590`

## callees

- `0x18000db5c`
- `0x18000fcd0`
- `0x180010b2c`
- `0x18001180c`
- `0x180012da4`
- `0x1800141e8`
- `0x18001566c`
- `0x180024dc0`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800118d2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800118d2`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800119c7`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800119c7`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180011a51`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180011a51`

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
0x18001180c  push    rbp
0x18001180e  push    rbx
0x18001180f  push    rsi
0x180011810  push    rdi
0x180011811  push    r12
0x180011813  push    r14
0x180011815  push    r15
0x180011817  lea     rbp, [rsp-13D0h]
0x18001181f  mov     eax, 14D0h
0x180011824  call    _alloca_probe
0x180011829  sub     rsp, rax
0x18001182c  mov     rax, cs:__security_cookie
0x180011833  xor     rax, rsp
0x180011836  mov     [rbp+1400h+var_40], rax
0x18001183d  mov     rsi, r8
0x180011840  mov     edi, edx
0x180011842  mov     rbx, rcx
0x180011845  mov     r14, [rbp+1400h+arg_28]
0x18001184c  xor     edx, edx; Val
0x18001184e  mov     r8d, 98h; Size
0x180011854  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180011859  call    memset_0
0x18001185e  nop
0x18001185f  xor     r12d, r12d
0x180011862  mov     [rbp+1400h+OutputString], r12w
0x18001186a  mov     [rbp+1400h+var_1440], r12b
0x18001186e  mov     rdx, [rbp+1400h+arg_30]; int
0x180011875  mov     ecx, [rdx]; this
0x180011877  mov     [rsp+1500h+var_14D8], ecx
0x18001187b  mov     eax, [rdx+4]
0x18001187e  mov     [rsp+1500h+var_14D4], eax
0x180011882  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180011887  mov     r15d, eax
0x18001188a  mov     dword ptr [rsp+1500h+var_14E0], 1
0x180011892  mov     ecx, r12d
0x180011895  lea     eax, [r12+8]
0x18001189a  cmp     dword ptr [rdx+8], 1
0x18001189e  cmovz   ecx, eax
0x1800118a1  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x1800118a5  lea     ecx, [rax-7]
0x1800118a8  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800118b0  inc     ecx
0x1800118b2  mov     [rsp+1500h+var_14D0], ecx
0x1800118b6  mov     rcx, [rbp+1400h+arg_38]
0x1800118bd  test    rcx, rcx
0x1800118c0  jz      short loc_1800118CD
0x1800118c2  cmp     [rcx], r12w
0x1800118c6  mov     [rsp+1500h+var_14C8], rcx
0x1800118cb  jnz     short loc_1800118D2
0x1800118cd  mov     [rsp+1500h+var_14C8], r12
0x1800118d2  call    cs:__imp_GetCurrentThreadId
0x1800118d8  mov     [rsp+1500h+var_14C0], eax
0x1800118dc  mov     [rsp+1500h+var_14A8], rsi
0x1800118e1  mov     [rsp+1500h+var_14A0], edi
0x1800118e5  mov     [rsp+1500h+var_149C], r15d
0x1800118ea  mov     [rsp+1500h+var_14B8], r12
0x1800118ef  mov     [rsp+1500h+var_14B0], r12
0x1800118f4  mov     [rbp+1400h+var_1458], r14
0x1800118f8  mov     [rbp+1400h+var_1450], rbx
0x1800118fc  mov     [rsp+1500h+var_1498], r12
0x180011901  xorps   xmm0, xmm0
0x180011904  xor     eax, eax
0x180011906  movups  [rbp+1400h+var_1478], xmm0
0x18001190a  mov     [rbp+1400h+var_1468], rax
0x18001190e  xorps   xmm1, xmm1
0x180011911  movups  [rsp+1500h+var_1490], xmm1
0x180011916  mov     [rbp+1400h+var_1480], rax
0x18001191a  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180011921  test    rax, rax
0x180011924  jz      short loc_180011931
0x180011926  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001192b  mov     [rbp+1400h+var_1460], rax
0x18001192f  jmp     short loc_180011935
0x180011931  mov     [rbp+1400h+var_1460], r12
0x180011935  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18001193c  test    rax, rax
0x18001193f  jz      short loc_18001194B
0x180011941  lea     rcx, [rsp+1500h+var_14E0]
0x180011946  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001194b  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180011952  test    rax, rax
0x180011955  jz      short loc_18001196B
0x180011957  mov     r8d, 400h
0x18001195d  lea     rdx, [rbp+1400h+var_1440]
0x180011961  lea     rcx, [rsp+1500h+var_14E0]
0x180011966  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001196b  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180011972  test    rax, rax
0x180011975  jz      short loc_180011981
0x180011977  lea     rcx, [rsp+1500h+var_14E0]
0x18001197c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011981  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180011988  test    rax, rax
0x18001198b  jz      short loc_18001199E
0x18001198d  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180011992  jnz     short loc_18001199E
0x180011994  lea     rcx, [rsp+1500h+var_14E0]
0x180011999  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001199e  cmp     [rsp+1500h+var_14D8], r12d
0x1800119a3  jge     loc_180011AAC
0x1800119a9  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x1800119b0  jnz     short loc_1800119D1
0x1800119b2  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800119b9  test    rax, rax
0x1800119bc  jz      short loc_1800119C7
0x1800119be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800119c3  test    al, al
0x1800119c5  jmp     short loc_1800119CF
0x1800119c7  call    cs:__imp_IsDebuggerPresent
0x1800119cd  test    eax, eax
0x1800119cf  jz      short loc_1800119D8
0x1800119d1  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1800119d6  jz      short loc_1800119FE
0x1800119d8  mov     rax, cs:g_pfnResultLoggingCallback
0x1800119df  test    rax, rax
0x1800119e2  jz      short loc_180011A57
0x1800119e4  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800119eb  jnz     short loc_180011A57
0x1800119ed  xor     r8d, r8d
0x1800119f0  xor     edx, edx
0x1800119f2  lea     rcx, [rsp+1500h+var_14E0]
0x1800119f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800119fc  jmp     short loc_180011A57
0x1800119fe  mov     ebx, 800h
0x180011a03  mov     rax, cs:g_pfnResultLoggingCallback
0x180011a0a  test    rax, rax
0x180011a0d  jz      short loc_180011A2C
0x180011a0f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180011a16  jnz     short loc_180011A2C
0x180011a18  mov     r8d, ebx
0x180011a1b  lea     rdx, [rbp+1400h+OutputString]
0x180011a22  lea     rcx, [rsp+1500h+var_14E0]
0x180011a27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011a2c  cmp     [rbp+1400h+OutputString], r12w
0x180011a34  jnz     short loc_180011A4A
0x180011a36  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180011a3b  mov     rdx, rbx; wchar_t *
0x180011a3e  lea     rcx, [rbp+1400h+OutputString]; this
0x180011a45  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x180011a4a  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180011a51  call    cs:__imp_OutputDebugStringW
0x180011a57  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180011a5c  jnz     short loc_180011A67
0x180011a5e  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180011a65  jz      short loc_180011A79
0x180011a67  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180011a6e  test    rax, rax
0x180011a71  jz      short loc_180011A79
0x180011a73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011a78  nop
0x180011a79  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180011a7e  jnz     short loc_180011AA1
0x180011a80  mov     rcx, [rbp+1400h+var_40]
0x180011a87  xor     rcx, rsp; StackCookie
0x180011a8a  call    __security_check_cookie
0x180011a8f  add     rsp, 14D0h
0x180011a96  pop     r15
0x180011a98  pop     r14
0x180011a9a  pop     r12
0x180011a9c  pop     rdi
0x180011a9d  pop     rsi
0x180011a9e  pop     rbx
0x180011a9f  pop     rbp
0x180011aa0  retn
0x180011aa1  lea     rcx, [rsp+1500h+var_14E0]; this
0x180011aa6  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180011aac  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
