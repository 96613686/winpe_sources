# wil::details::ReportFailure_NoReturn<0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180005bec`
- end: `0x180005ec3`
- name: `??$ReportFailure_NoReturn@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `727`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18000524c`

## callees

- `0x1800032b8`
- `0x180005bec`
- `0x18000b004`
- `0x18000dc68`
- `0x18001276c`
- `0x180012f2c`
- `0x180013490`
- `0x180042f60`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005cad`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005cad`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005e51`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005e51`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180005daf`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180005daf`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<0>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7,
        _WORD *a8)
{
  bool v11; // di
  int v12; // r12d
  int v13; // ecx
  __int64 v14; // rdx
  const struct wil::FailureInfo *v15; // rdx
  wil::details::in1diag3 *v16; // rcx
  const struct wil::FailureInfo *v17; // r9
  bool v18; // zf
  char v19; // bl
  const struct wil::FailureInfo *v20; // rdx
  int v21; // [rsp+20h] [rbp-E0h] BYREF
  int v22; // [rsp+24h] [rbp-DCh]
  int v23; // [rsp+28h] [rbp-D8h]
  int v24; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v25; // [rsp+30h] [rbp-D0h]
  _WORD *v26; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v28; // [rsp+48h] [rbp-B8h]
  __int64 v29; // [rsp+50h] [rbp-B0h]
  __int64 v30; // [rsp+58h] [rbp-A8h]
  int v31; // [rsp+60h] [rbp-A0h]
  int v32; // [rsp+64h] [rbp-9Ch]
  __int64 v33; // [rsp+68h] [rbp-98h]
  __int128 v34; // [rsp+70h] [rbp-90h]
  __int64 v35; // [rsp+80h] [rbp-80h]
  __int128 v36; // [rsp+88h] [rbp-78h]
  __int64 v37; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v39; // [rsp+A8h] [rbp-58h]
  __int64 v40; // [rsp+B0h] [rbp-50h]
  char v41[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2072]; // [rsp+4C0h] [rbp+3C0h] BYREF

  v11 = g_pfnThrowPlatformException != 0;
  memset_0(&v21, 0, 0x98u);
  OutputString[0] = 0;
  v41[0] = 0;
  v23 = *a7;
  v24 = a7[1];
  v12 = wil::details::RecordException((wil::details *)(unsigned int)v23, (int)a7);
  v21 = 0;
  v13 = 0;
  if ( *(_DWORD *)(v14 + 8) == 1 )
    v13 = 8;
  v22 = v13;
  v25 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  if ( !a8 || (v18 = *a8 == 0, v26 = a8, v18) )
    v26 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v30 = a3;
  v31 = a2;
  v32 = v12;
  v28 = 0;
  v29 = 0;
  v39 = a6;
  v40 = a1;
  v33 = 0;
  v36 = 0;
  v37 = 0;
  v34 = 0;
  v35 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v16);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v21);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v21, v41, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v21);
  if ( wil::details::g_pfnOriginateCallback && !v11 && (v22 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v21);
  if ( v23 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v16);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v18 = !IsDebuggerPresent())
      : (v18 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v16) == 0),
        v18)
    || (v19 = 1, (v22 & 2) != 0) )
  {
    v19 = 0;
  }
  if ( v11 || v19 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v21, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v21, v17);
    if ( v19 )
      OutputDebugStringW(OutputString);
  }
  else if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
  {
    g_pfnResultLoggingCallback(&v21, 0, 0);
  }
  if ( ((v22 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v16);
  if ( (v22 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v21, v15);
  if ( v11 )
    ((void (__fastcall *)(int *, WCHAR *))g_pfnThrowPlatformException)(&v21, OutputString);
  wil::ThrowResultException((wil *)&v21, v15);
  wil::details::WilFailFast((wil::details *)&v21, v20);
}

```

## disassembly

```asm
0x180005bec  mov     [rsp-8+arg_18], rbx
0x180005bf1  push    rbp
0x180005bf2  push    rsi
0x180005bf3  push    rdi
0x180005bf4  push    r12
0x180005bf6  push    r13
0x180005bf8  push    r14
0x180005bfa  push    r15
0x180005bfc  lea     rbp, [rsp-13C0h]
0x180005c04  mov     eax, 14C0h
0x180005c09  call    _alloca_probe
0x180005c0e  sub     rsp, rax
0x180005c11  mov     r14, r8
0x180005c14  mov     esi, edx
0x180005c16  mov     rbx, rcx
0x180005c19  mov     r15, [rbp+13F0h+arg_28]
0x180005c20  xor     r13d, r13d
0x180005c23  cmp     cs:g_pfnThrowPlatformException, r13
0x180005c2a  setnz   dil
0x180005c2e  xor     edx, edx; Val
0x180005c30  mov     r8d, 98h; Size
0x180005c36  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180005c3b  call    memset_0
0x180005c40  nop
0x180005c41  mov     [rbp+13F0h+OutputString], r13w
0x180005c49  mov     [rbp+13F0h+var_1430], r13b
0x180005c4d  mov     rdx, [rbp+13F0h+arg_30]; int
0x180005c54  mov     ecx, [rdx]; this
0x180005c56  mov     [rsp+14F0h+var_14C8], ecx
0x180005c5a  mov     eax, [rdx+4]
0x180005c5d  mov     [rsp+14F0h+var_14C4], eax
0x180005c61  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180005c66  mov     r12d, eax
0x180005c69  mov     dword ptr [rsp+14F0h+var_14D0], r13d
0x180005c6e  mov     ecx, r13d
0x180005c71  lea     eax, [r13+8]
0x180005c75  cmp     dword ptr [rdx+8], 1
0x180005c79  cmovz   ecx, eax
0x180005c7c  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180005c80  lea     ecx, [rax-7]
0x180005c83  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180005c8b  inc     ecx
0x180005c8d  mov     [rsp+14F0h+var_14C0], ecx
0x180005c91  mov     rcx, [rbp+13F0h+arg_38]
0x180005c98  test    rcx, rcx
0x180005c9b  jz      short loc_180005CA8
0x180005c9d  cmp     [rcx], r13w
0x180005ca1  mov     [rsp+14F0h+var_14B8], rcx
0x180005ca6  jnz     short loc_180005CAD
0x180005ca8  mov     [rsp+14F0h+var_14B8], r13
0x180005cad  call    cs:__imp_GetCurrentThreadId
0x180005cb4  nop     dword ptr [rax+rax+00h]
0x180005cb9  mov     [rsp+14F0h+var_14B0], eax
0x180005cbd  mov     [rsp+14F0h+var_1498], r14
0x180005cc2  mov     [rsp+14F0h+var_1490], esi
0x180005cc6  mov     [rsp+14F0h+var_148C], r12d
0x180005ccb  mov     [rsp+14F0h+var_14A8], r13
0x180005cd0  mov     [rsp+14F0h+var_14A0], r13
0x180005cd5  mov     [rbp+13F0h+var_1448], r15
0x180005cd9  mov     [rbp+13F0h+var_1440], rbx
0x180005cdd  mov     [rsp+14F0h+var_1488], r13
0x180005ce2  xorps   xmm0, xmm0
0x180005ce5  xor     eax, eax
0x180005ce7  movups  [rbp+13F0h+var_1468], xmm0
0x180005ceb  mov     [rbp+13F0h+var_1458], rax
0x180005cef  xorps   xmm1, xmm1
0x180005cf2  movups  [rsp+14F0h+var_1480], xmm1
0x180005cf7  mov     [rbp+13F0h+var_1470], rax
0x180005cfb  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180005d02  test    rax, rax
0x180005d05  jz      short loc_180005D12
0x180005d07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d0c  mov     [rbp+13F0h+var_1450], rax
0x180005d10  jmp     short loc_180005D16
0x180005d12  mov     [rbp+13F0h+var_1450], r13
0x180005d16  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180005d1d  test    rax, rax
0x180005d20  jz      short loc_180005D2C
0x180005d22  lea     rcx, [rsp+14F0h+var_14D0]
0x180005d27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d2c  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180005d33  test    rax, rax
0x180005d36  jz      short loc_180005D4C
0x180005d38  mov     r8d, 400h
0x180005d3e  lea     rdx, [rbp+13F0h+var_1430]
0x180005d42  lea     rcx, [rsp+14F0h+var_14D0]
0x180005d47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d4c  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005d53  test    rax, rax
0x180005d56  jz      short loc_180005D62
0x180005d58  lea     rcx, [rsp+14F0h+var_14D0]
0x180005d5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d62  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005d69  test    rax, rax
0x180005d6c  jz      short loc_180005D84
0x180005d6e  test    dil, dil
0x180005d71  jnz     short loc_180005D84
0x180005d73  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180005d78  jnz     short loc_180005D84
0x180005d7a  lea     rcx, [rsp+14F0h+var_14D0]
0x180005d7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d84  cmp     [rsp+14F0h+var_14C8], r13d
0x180005d89  jl      short loc_180005D91
0x180005d8b  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180005d91  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x180005d98  jnz     short loc_180005DBF
0x180005d9a  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180005da1  test    rax, rax
0x180005da4  jz      short loc_180005DAF
0x180005da6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005dab  test    al, al
0x180005dad  jmp     short loc_180005DBD
0x180005daf  call    cs:__imp_IsDebuggerPresent
0x180005db6  nop     dword ptr [rax+rax+00h]
0x180005dbb  test    eax, eax
0x180005dbd  jz      short loc_180005DC8
0x180005dbf  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180005dc4  mov     bl, 1
0x180005dc6  jz      short loc_180005DCB
0x180005dc8  mov     bl, r13b
0x180005dcb  test    dil, dil
0x180005dce  jnz     short loc_180005DFA
0x180005dd0  test    bl, bl
0x180005dd2  jnz     short loc_180005DFA
0x180005dd4  mov     rax, cs:g_pfnResultLoggingCallback
0x180005ddb  test    rax, rax
0x180005dde  jz      short loc_180005E5D
0x180005de0  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180005de7  jnz     short loc_180005E5D
0x180005de9  xor     r8d, r8d
0x180005dec  xor     edx, edx
0x180005dee  lea     rcx, [rsp+14F0h+var_14D0]
0x180005df3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005df8  jmp     short loc_180005E5D
0x180005dfa  mov     esi, 800h
0x180005dff  mov     rax, cs:g_pfnResultLoggingCallback
0x180005e06  test    rax, rax
0x180005e09  jz      short loc_180005E28
0x180005e0b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180005e12  jnz     short loc_180005E28
0x180005e14  mov     r8d, esi
0x180005e17  lea     rdx, [rbp+13F0h+OutputString]
0x180005e1e  lea     rcx, [rsp+14F0h+var_14D0]
0x180005e23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e28  cmp     [rbp+13F0h+OutputString], r13w
0x180005e30  jnz     short loc_180005E46
0x180005e32  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180005e37  mov     rdx, rsi; unsigned __int16 *
0x180005e3a  lea     rcx, [rbp+13F0h+OutputString]; this
0x180005e41  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180005e46  test    bl, bl
0x180005e48  jz      short loc_180005E5D
0x180005e4a  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180005e51  call    cs:__imp_OutputDebugStringW
0x180005e58  nop     dword ptr [rax+rax+00h]
0x180005e5d  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180005e62  jnz     short loc_180005E6D
0x180005e64  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x180005e6b  jz      short loc_180005E7F
0x180005e6d  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180005e74  test    rax, rax
0x180005e77  jz      short loc_180005E7F
0x180005e79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e7e  nop
0x180005e7f  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x180005e84  jz      short loc_180005E91
0x180005e86  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180005e8b  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180005e91  test    dil, dil
0x180005e94  jz      short loc_180005EAE
0x180005e96  lea     rdx, [rbp+13F0h+OutputString]
0x180005e9d  lea     rcx, [rsp+14F0h+var_14D0]
0x180005ea2  mov     rax, cs:g_pfnThrowPlatformException
0x180005ea9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005eae  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180005eb3  call    ?ThrowResultException@wil@@YAXAEBUFailureInfo@1@@Z; wil::ThrowResultException(wil::FailureInfo const &)
0x180005eb8  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180005ebd  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
