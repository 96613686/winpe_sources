# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180003ce8`
- end: `0x180003f8e`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `678`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18000377c`

## callees

- `0x1800024a0`
- `0x180003320`
- `0x180003ce8`
- `0x1800063c4`
- `0x180007c28`
- `0x18000a1f0`
- `0x18000a3bc`
- `0x180015650`
- `0x180018010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003dae`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003dae`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003f2d`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003f2d`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003ea3`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003ea3`

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
0x180003ce8  push    rbp
0x180003cea  push    rbx
0x180003ceb  push    rsi
0x180003cec  push    rdi
0x180003ced  push    r12
0x180003cef  push    r14
0x180003cf1  push    r15
0x180003cf3  lea     rbp, [rsp-13D0h]
0x180003cfb  mov     eax, 14D0h
0x180003d00  call    _alloca_probe
0x180003d05  sub     rsp, rax
0x180003d08  mov     rax, cs:__security_cookie
0x180003d0f  xor     rax, rsp
0x180003d12  mov     [rbp+1400h+var_40], rax
0x180003d19  mov     rsi, r8
0x180003d1c  mov     edi, edx
0x180003d1e  mov     rbx, rcx
0x180003d21  mov     r14, [rbp+1400h+arg_28]
0x180003d28  xor     edx, edx; Val
0x180003d2a  mov     r8d, 98h; Size
0x180003d30  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180003d35  call    memset_0
0x180003d3a  nop
0x180003d3b  xor     r12d, r12d
0x180003d3e  mov     [rbp+1400h+OutputString], r12w
0x180003d46  mov     [rbp+1400h+var_1440], r12b
0x180003d4a  mov     rdx, [rbp+1400h+arg_30]; int
0x180003d51  mov     ecx, [rdx]; this
0x180003d53  mov     [rsp+1500h+var_14D8], ecx
0x180003d57  mov     eax, [rdx+4]
0x180003d5a  mov     [rsp+1500h+var_14D4], eax
0x180003d5e  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180003d63  mov     r15d, eax
0x180003d66  mov     dword ptr [rsp+1500h+var_14E0], 1
0x180003d6e  mov     ecx, r12d
0x180003d71  lea     eax, [r12+8]
0x180003d76  cmp     dword ptr [rdx+8], 1
0x180003d7a  cmovz   ecx, eax
0x180003d7d  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180003d81  lea     ecx, [rax-7]
0x180003d84  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180003d8c  inc     ecx
0x180003d8e  mov     [rsp+1500h+var_14D0], ecx
0x180003d92  mov     rcx, [rbp+1400h+arg_38]
0x180003d99  test    rcx, rcx
0x180003d9c  jz      short loc_180003DA9
0x180003d9e  cmp     [rcx], r12w
0x180003da2  mov     [rsp+1500h+var_14C8], rcx
0x180003da7  jnz     short loc_180003DAE
0x180003da9  mov     [rsp+1500h+var_14C8], r12
0x180003dae  call    cs:__imp_GetCurrentThreadId
0x180003db4  mov     [rsp+1500h+var_14C0], eax
0x180003db8  mov     [rsp+1500h+var_14A8], rsi
0x180003dbd  mov     [rsp+1500h+var_14A0], edi
0x180003dc1  mov     [rsp+1500h+var_149C], r15d
0x180003dc6  mov     [rsp+1500h+var_14B8], r12
0x180003dcb  mov     [rsp+1500h+var_14B0], r12
0x180003dd0  mov     [rbp+1400h+var_1458], r14
0x180003dd4  mov     [rbp+1400h+var_1450], rbx
0x180003dd8  mov     [rsp+1500h+var_1498], r12
0x180003ddd  xorps   xmm0, xmm0
0x180003de0  xor     eax, eax
0x180003de2  movups  [rbp+1400h+var_1478], xmm0
0x180003de6  mov     [rbp+1400h+var_1468], rax
0x180003dea  xorps   xmm1, xmm1
0x180003ded  movups  [rsp+1500h+var_1490], xmm1
0x180003df2  mov     [rbp+1400h+var_1480], rax
0x180003df6  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180003dfd  test    rax, rax
0x180003e00  jz      short loc_180003E0D
0x180003e02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e07  mov     [rbp+1400h+var_1460], rax
0x180003e0b  jmp     short loc_180003E11
0x180003e0d  mov     [rbp+1400h+var_1460], r12
0x180003e11  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180003e18  test    rax, rax
0x180003e1b  jz      short loc_180003E27
0x180003e1d  lea     rcx, [rsp+1500h+var_14E0]
0x180003e22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e27  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180003e2e  test    rax, rax
0x180003e31  jz      short loc_180003E47
0x180003e33  mov     r8d, 400h
0x180003e39  lea     rdx, [rbp+1400h+var_1440]
0x180003e3d  lea     rcx, [rsp+1500h+var_14E0]
0x180003e42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e47  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003e4e  test    rax, rax
0x180003e51  jz      short loc_180003E5D
0x180003e53  lea     rcx, [rsp+1500h+var_14E0]
0x180003e58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e5d  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003e64  test    rax, rax
0x180003e67  jz      short loc_180003E7A
0x180003e69  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180003e6e  jnz     short loc_180003E7A
0x180003e70  lea     rcx, [rsp+1500h+var_14E0]
0x180003e75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e7a  cmp     [rsp+1500h+var_14D8], r12d
0x180003e7f  jge     loc_180003F88
0x180003e85  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180003e8c  jnz     short loc_180003EAD
0x180003e8e  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180003e95  test    rax, rax
0x180003e98  jz      short loc_180003EA3
0x180003e9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e9f  test    al, al
0x180003ea1  jmp     short loc_180003EAB
0x180003ea3  call    cs:__imp_IsDebuggerPresent
0x180003ea9  test    eax, eax
0x180003eab  jz      short loc_180003EB4
0x180003ead  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180003eb2  jz      short loc_180003EDA
0x180003eb4  mov     rax, cs:g_pfnResultLoggingCallback
0x180003ebb  test    rax, rax
0x180003ebe  jz      short loc_180003F33
0x180003ec0  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180003ec7  jnz     short loc_180003F33
0x180003ec9  xor     r8d, r8d
0x180003ecc  xor     edx, edx
0x180003ece  lea     rcx, [rsp+1500h+var_14E0]
0x180003ed3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ed8  jmp     short loc_180003F33
0x180003eda  mov     ebx, 800h
0x180003edf  mov     rax, cs:g_pfnResultLoggingCallback
0x180003ee6  test    rax, rax
0x180003ee9  jz      short loc_180003F08
0x180003eeb  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180003ef2  jnz     short loc_180003F08
0x180003ef4  mov     r8d, ebx
0x180003ef7  lea     rdx, [rbp+1400h+OutputString]
0x180003efe  lea     rcx, [rsp+1500h+var_14E0]
0x180003f03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f08  cmp     [rbp+1400h+OutputString], r12w
0x180003f10  jnz     short loc_180003F26
0x180003f12  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180003f17  mov     rdx, rbx; wchar_t *
0x180003f1a  lea     rcx, [rbp+1400h+OutputString]; this
0x180003f21  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x180003f26  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180003f2d  call    cs:__imp_OutputDebugStringW
0x180003f33  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180003f38  jnz     short loc_180003F43
0x180003f3a  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180003f41  jz      short loc_180003F55
0x180003f43  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180003f4a  test    rax, rax
0x180003f4d  jz      short loc_180003F55
0x180003f4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f54  nop
0x180003f55  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180003f5a  jnz     short loc_180003F7D
0x180003f5c  mov     rcx, [rbp+1400h+var_40]
0x180003f63  xor     rcx, rsp; StackCookie
0x180003f66  call    __security_check_cookie
0x180003f6b  add     rsp, 14D0h
0x180003f72  pop     r15
0x180003f74  pop     r14
0x180003f76  pop     r12
0x180003f78  pop     rdi
0x180003f79  pop     rsi
0x180003f7a  pop     rbx
0x180003f7b  pop     rbp
0x180003f7c  retn
0x180003f7d  lea     rcx, [rsp+1500h+var_14E0]; this
0x180003f82  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180003f88  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
