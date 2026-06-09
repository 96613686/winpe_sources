# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180006d64`
- end: `0x18000700a`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `678`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800066b0`

## callees

- `0x180004494`
- `0x1800057d0`
- `0x180006d64`
- `0x180009694`
- `0x18000ad08`
- `0x18004371a`
- `0x180043750`
- `0x180043810`
- `0x180047010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006e2a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006e2a`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180006fa9`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180006fa9`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180006f1f`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180006f1f`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
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
0x180006d64  push    rbp
0x180006d66  push    rbx
0x180006d67  push    rsi
0x180006d68  push    rdi
0x180006d69  push    r12
0x180006d6b  push    r14
0x180006d6d  push    r15
0x180006d6f  lea     rbp, [rsp-13D0h]
0x180006d77  mov     eax, 14D0h
0x180006d7c  call    _alloca_probe
0x180006d81  sub     rsp, rax
0x180006d84  mov     rax, cs:__security_cookie
0x180006d8b  xor     rax, rsp
0x180006d8e  mov     [rbp+1400h+var_40], rax
0x180006d95  mov     rsi, r8
0x180006d98  mov     edi, edx
0x180006d9a  mov     rbx, rcx
0x180006d9d  mov     r14, [rbp+1400h+arg_28]
0x180006da4  xor     edx, edx; Val
0x180006da6  mov     r8d, 98h; Size
0x180006dac  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180006db1  call    memset_0
0x180006db6  nop
0x180006db7  xor     r12d, r12d
0x180006dba  mov     [rbp+1400h+OutputString], r12w
0x180006dc2  mov     [rbp+1400h+var_1440], r12b
0x180006dc6  mov     rdx, [rbp+1400h+arg_30]; int
0x180006dcd  mov     ecx, [rdx]; this
0x180006dcf  mov     [rsp+1500h+var_14D8], ecx
0x180006dd3  mov     eax, [rdx+4]
0x180006dd6  mov     [rsp+1500h+var_14D4], eax
0x180006dda  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180006ddf  mov     r15d, eax
0x180006de2  mov     dword ptr [rsp+1500h+var_14E0], 1
0x180006dea  mov     ecx, r12d
0x180006ded  lea     eax, [r12+8]
0x180006df2  cmp     dword ptr [rdx+8], 1
0x180006df6  cmovz   ecx, eax
0x180006df9  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180006dfd  lea     ecx, [rax-7]
0x180006e00  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180006e08  inc     ecx
0x180006e0a  mov     [rsp+1500h+var_14D0], ecx
0x180006e0e  mov     rcx, [rbp+1400h+arg_38]
0x180006e15  test    rcx, rcx
0x180006e18  jz      short loc_180006E25
0x180006e1a  cmp     [rcx], r12w
0x180006e1e  mov     [rsp+1500h+var_14C8], rcx
0x180006e23  jnz     short loc_180006E2A
0x180006e25  mov     [rsp+1500h+var_14C8], r12
0x180006e2a  call    cs:__imp_GetCurrentThreadId
0x180006e30  mov     [rsp+1500h+var_14C0], eax
0x180006e34  mov     [rsp+1500h+var_14A8], rsi
0x180006e39  mov     [rsp+1500h+var_14A0], edi
0x180006e3d  mov     [rsp+1500h+var_149C], r15d
0x180006e42  mov     [rsp+1500h+var_14B8], r12
0x180006e47  mov     [rsp+1500h+var_14B0], r12
0x180006e4c  mov     [rbp+1400h+var_1458], r14
0x180006e50  mov     [rbp+1400h+var_1450], rbx
0x180006e54  mov     [rsp+1500h+var_1498], r12
0x180006e59  xorps   xmm0, xmm0
0x180006e5c  xor     eax, eax
0x180006e5e  movups  [rbp+1400h+var_1478], xmm0
0x180006e62  mov     [rbp+1400h+var_1468], rax
0x180006e66  xorps   xmm1, xmm1
0x180006e69  movups  [rsp+1500h+var_1490], xmm1
0x180006e6e  mov     [rbp+1400h+var_1480], rax
0x180006e72  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180006e79  test    rax, rax
0x180006e7c  jz      short loc_180006E89
0x180006e7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e83  mov     [rbp+1400h+var_1460], rax
0x180006e87  jmp     short loc_180006E8D
0x180006e89  mov     [rbp+1400h+var_1460], r12
0x180006e8d  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180006e94  test    rax, rax
0x180006e97  jz      short loc_180006EA3
0x180006e99  lea     rcx, [rsp+1500h+var_14E0]
0x180006e9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ea3  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180006eaa  test    rax, rax
0x180006ead  jz      short loc_180006EC3
0x180006eaf  mov     r8d, 400h
0x180006eb5  lea     rdx, [rbp+1400h+var_1440]
0x180006eb9  lea     rcx, [rsp+1500h+var_14E0]
0x180006ebe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ec3  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180006eca  test    rax, rax
0x180006ecd  jz      short loc_180006ED9
0x180006ecf  lea     rcx, [rsp+1500h+var_14E0]
0x180006ed4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ed9  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180006ee0  test    rax, rax
0x180006ee3  jz      short loc_180006EF6
0x180006ee5  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180006eea  jnz     short loc_180006EF6
0x180006eec  lea     rcx, [rsp+1500h+var_14E0]
0x180006ef1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ef6  cmp     [rsp+1500h+var_14D8], r12d
0x180006efb  jge     loc_180007004
0x180006f01  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180006f08  jnz     short loc_180006F29
0x180006f0a  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180006f11  test    rax, rax
0x180006f14  jz      short loc_180006F1F
0x180006f16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f1b  test    al, al
0x180006f1d  jmp     short loc_180006F27
0x180006f1f  call    cs:__imp_IsDebuggerPresent
0x180006f25  test    eax, eax
0x180006f27  jz      short loc_180006F30
0x180006f29  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180006f2e  jz      short loc_180006F56
0x180006f30  mov     rax, cs:g_pfnResultLoggingCallback
0x180006f37  test    rax, rax
0x180006f3a  jz      short loc_180006FAF
0x180006f3c  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180006f43  jnz     short loc_180006FAF
0x180006f45  xor     r8d, r8d
0x180006f48  xor     edx, edx
0x180006f4a  lea     rcx, [rsp+1500h+var_14E0]
0x180006f4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f54  jmp     short loc_180006FAF
0x180006f56  mov     ebx, 800h
0x180006f5b  mov     rax, cs:g_pfnResultLoggingCallback
0x180006f62  test    rax, rax
0x180006f65  jz      short loc_180006F84
0x180006f67  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180006f6e  jnz     short loc_180006F84
0x180006f70  mov     r8d, ebx
0x180006f73  lea     rdx, [rbp+1400h+OutputString]
0x180006f7a  lea     rcx, [rsp+1500h+var_14E0]
0x180006f7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f84  cmp     [rbp+1400h+OutputString], r12w
0x180006f8c  jnz     short loc_180006FA2
0x180006f8e  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180006f93  mov     rdx, rbx; unsigned __int16 *
0x180006f96  lea     rcx, [rbp+1400h+OutputString]; this
0x180006f9d  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180006fa2  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180006fa9  call    cs:__imp_OutputDebugStringW
0x180006faf  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180006fb4  jnz     short loc_180006FBF
0x180006fb6  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180006fbd  jz      short loc_180006FD1
0x180006fbf  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180006fc6  test    rax, rax
0x180006fc9  jz      short loc_180006FD1
0x180006fcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006fd0  nop
0x180006fd1  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180006fd6  jnz     short loc_180006FF9
0x180006fd8  mov     rcx, [rbp+1400h+var_40]
0x180006fdf  xor     rcx, rsp; StackCookie
0x180006fe2  call    __security_check_cookie
0x180006fe7  add     rsp, 14D0h
0x180006fee  pop     r15
0x180006ff0  pop     r14
0x180006ff2  pop     r12
0x180006ff4  pop     rdi
0x180006ff5  pop     rsi
0x180006ff6  pop     rbx
0x180006ff7  pop     rbp
0x180006ff8  retn
0x180006ff9  lea     rcx, [rsp+1500h+var_14E0]; this
0x180006ffe  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180007004  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
