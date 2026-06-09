# wil::details::ReportFailure_NoReturn<0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180008a10`
- end: `0x180008cd5`
- name: `??$ReportFailure_NoReturn@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `709`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180008874`

## callees

- `0x180002b78`
- `0x180005584`
- `0x1800065b8`
- `0x180007620`
- `0x180007950`
- `0x180007a2c`
- `0x180008a10`
- `0x180030510`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008ad1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008ad1`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180008bcd`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180008bcd`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180008c69`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180008c69`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
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
0x180008a10  mov     [rsp-8+arg_18], rbx
0x180008a15  push    rbp
0x180008a16  push    rsi
0x180008a17  push    rdi
0x180008a18  push    r12
0x180008a1a  push    r13
0x180008a1c  push    r14
0x180008a1e  push    r15
0x180008a20  lea     rbp, [rsp-13C0h]
0x180008a28  mov     eax, 14C0h
0x180008a2d  call    _alloca_probe
0x180008a32  sub     rsp, rax
0x180008a35  mov     r14, r8
0x180008a38  mov     esi, edx
0x180008a3a  mov     rbx, rcx
0x180008a3d  mov     r15, [rbp+13F0h+arg_28]
0x180008a44  xor     r13d, r13d
0x180008a47  cmp     cs:g_pfnThrowPlatformException, r13
0x180008a4e  setnz   dil
0x180008a52  xor     edx, edx; Val
0x180008a54  mov     r8d, 98h; Size
0x180008a5a  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180008a5f  call    memset_0
0x180008a64  nop
0x180008a65  mov     [rbp+13F0h+OutputString], r13w
0x180008a6d  mov     [rbp+13F0h+var_1430], r13b
0x180008a71  mov     rdx, [rbp+13F0h+arg_30]; int
0x180008a78  mov     ecx, [rdx]; this
0x180008a7a  mov     [rsp+14F0h+var_14C8], ecx
0x180008a7e  mov     eax, [rdx+4]
0x180008a81  mov     [rsp+14F0h+var_14C4], eax
0x180008a85  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180008a8a  mov     r12d, eax
0x180008a8d  mov     dword ptr [rsp+14F0h+var_14D0], r13d
0x180008a92  mov     ecx, r13d
0x180008a95  lea     eax, [r13+8]
0x180008a99  cmp     dword ptr [rdx+8], 1
0x180008a9d  cmovz   ecx, eax
0x180008aa0  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180008aa4  lea     ecx, [rax-7]
0x180008aa7  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180008aaf  inc     ecx
0x180008ab1  mov     [rsp+14F0h+var_14C0], ecx
0x180008ab5  mov     rcx, [rbp+13F0h+arg_38]
0x180008abc  test    rcx, rcx
0x180008abf  jz      short loc_180008ACC
0x180008ac1  cmp     [rcx], r13w
0x180008ac5  mov     [rsp+14F0h+var_14B8], rcx
0x180008aca  jnz     short loc_180008AD1
0x180008acc  mov     [rsp+14F0h+var_14B8], r13
0x180008ad1  call    cs:__imp_GetCurrentThreadId
0x180008ad7  mov     [rsp+14F0h+var_14B0], eax
0x180008adb  mov     [rsp+14F0h+var_1498], r14
0x180008ae0  mov     [rsp+14F0h+var_1490], esi
0x180008ae4  mov     [rsp+14F0h+var_148C], r12d
0x180008ae9  mov     [rsp+14F0h+var_14A8], r13
0x180008aee  mov     [rsp+14F0h+var_14A0], r13
0x180008af3  mov     [rbp+13F0h+var_1448], r15
0x180008af7  mov     [rbp+13F0h+var_1440], rbx
0x180008afb  mov     [rsp+14F0h+var_1488], r13
0x180008b00  xorps   xmm0, xmm0
0x180008b03  xor     eax, eax
0x180008b05  movups  [rbp+13F0h+var_1468], xmm0
0x180008b09  mov     [rbp+13F0h+var_1458], rax
0x180008b0d  xorps   xmm1, xmm1
0x180008b10  movups  [rsp+14F0h+var_1480], xmm1
0x180008b15  mov     [rbp+13F0h+var_1470], rax
0x180008b19  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180008b20  test    rax, rax
0x180008b23  jz      short loc_180008B30
0x180008b25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b2a  mov     [rbp+13F0h+var_1450], rax
0x180008b2e  jmp     short loc_180008B34
0x180008b30  mov     [rbp+13F0h+var_1450], r13
0x180008b34  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180008b3b  test    rax, rax
0x180008b3e  jz      short loc_180008B4A
0x180008b40  lea     rcx, [rsp+14F0h+var_14D0]
0x180008b45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b4a  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180008b51  test    rax, rax
0x180008b54  jz      short loc_180008B6A
0x180008b56  mov     r8d, 400h
0x180008b5c  lea     rdx, [rbp+13F0h+var_1430]
0x180008b60  lea     rcx, [rsp+14F0h+var_14D0]
0x180008b65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b6a  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180008b71  test    rax, rax
0x180008b74  jz      short loc_180008B80
0x180008b76  lea     rcx, [rsp+14F0h+var_14D0]
0x180008b7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b80  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180008b87  test    rax, rax
0x180008b8a  jz      short loc_180008BA2
0x180008b8c  test    dil, dil
0x180008b8f  jnz     short loc_180008BA2
0x180008b91  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180008b96  jnz     short loc_180008BA2
0x180008b98  lea     rcx, [rsp+14F0h+var_14D0]
0x180008b9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ba2  cmp     [rsp+14F0h+var_14C8], r13d
0x180008ba7  jl      short loc_180008BAF
0x180008ba9  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180008baf  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x180008bb6  jnz     short loc_180008BD7
0x180008bb8  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180008bbf  test    rax, rax
0x180008bc2  jz      short loc_180008BCD
0x180008bc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008bc9  test    al, al
0x180008bcb  jmp     short loc_180008BD5
0x180008bcd  call    cs:__imp_IsDebuggerPresent
0x180008bd3  test    eax, eax
0x180008bd5  jz      short loc_180008BE0
0x180008bd7  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180008bdc  mov     bl, 1
0x180008bde  jz      short loc_180008BE3
0x180008be0  mov     bl, r13b
0x180008be3  test    dil, dil
0x180008be6  jnz     short loc_180008C12
0x180008be8  test    bl, bl
0x180008bea  jnz     short loc_180008C12
0x180008bec  mov     rax, cs:g_pfnResultLoggingCallback
0x180008bf3  test    rax, rax
0x180008bf6  jz      short loc_180008C6F
0x180008bf8  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180008bff  jnz     short loc_180008C6F
0x180008c01  xor     r8d, r8d
0x180008c04  xor     edx, edx
0x180008c06  lea     rcx, [rsp+14F0h+var_14D0]
0x180008c0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c10  jmp     short loc_180008C6F
0x180008c12  mov     esi, 800h
0x180008c17  mov     rax, cs:g_pfnResultLoggingCallback
0x180008c1e  test    rax, rax
0x180008c21  jz      short loc_180008C40
0x180008c23  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180008c2a  jnz     short loc_180008C40
0x180008c2c  mov     r8d, esi
0x180008c2f  lea     rdx, [rbp+13F0h+OutputString]
0x180008c36  lea     rcx, [rsp+14F0h+var_14D0]
0x180008c3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c40  cmp     [rbp+13F0h+OutputString], r13w
0x180008c48  jnz     short loc_180008C5E
0x180008c4a  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180008c4f  mov     rdx, rsi; unsigned __int16 *
0x180008c52  lea     rcx, [rbp+13F0h+OutputString]; this
0x180008c59  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180008c5e  test    bl, bl
0x180008c60  jz      short loc_180008C6F
0x180008c62  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180008c69  call    cs:__imp_OutputDebugStringW
0x180008c6f  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180008c74  jnz     short loc_180008C7F
0x180008c76  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x180008c7d  jz      short loc_180008C91
0x180008c7f  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180008c86  test    rax, rax
0x180008c89  jz      short loc_180008C91
0x180008c8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c90  nop
0x180008c91  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x180008c96  jz      short loc_180008CA3
0x180008c98  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180008c9d  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180008ca3  test    dil, dil
0x180008ca6  jz      short loc_180008CC0
0x180008ca8  lea     rdx, [rbp+13F0h+OutputString]
0x180008caf  lea     rcx, [rsp+14F0h+var_14D0]
0x180008cb4  mov     rax, cs:g_pfnThrowPlatformException
0x180008cbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008cc0  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180008cc5  call    ?ThrowResultException@wil@@YAXAEBUFailureInfo@1@@Z; wil::ThrowResultException(wil::FailureInfo const &)
0x180008cca  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180008ccf  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
