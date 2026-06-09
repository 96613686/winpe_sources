# wil::details::ReportFailure_NoReturn<0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x18000a850`
- end: `0x18000ab27`
- name: `??$ReportFailure_NoReturn@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `727`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18000a570`

## callees

- `0x18000270c`
- `0x1800055c4`
- `0x180006e7c`
- `0x180008fd8`
- `0x18000974c`
- `0x180009934`
- `0x18000a850`
- `0x180034af0`
- `0x180039010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a911`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a911`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000aa13`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000aa13`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000aab5`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000aab5`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
      g_pfnResultLoggingCallback(&v21, OutputString, 2048, v17);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (__int64)&v21, v17);
    if ( v19 )
      OutputDebugStringW(OutputString);
  }
  else if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
  {
    g_pfnResultLoggingCallback(&v21, 0, 0, v17);
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
0x18000a850  mov     [rsp-8+arg_18], rbx
0x18000a855  push    rbp
0x18000a856  push    rsi
0x18000a857  push    rdi
0x18000a858  push    r12
0x18000a85a  push    r13
0x18000a85c  push    r14
0x18000a85e  push    r15
0x18000a860  lea     rbp, [rsp-13C0h]
0x18000a868  mov     eax, 14C0h
0x18000a86d  call    _alloca_probe
0x18000a872  sub     rsp, rax
0x18000a875  mov     r14, r8
0x18000a878  mov     esi, edx
0x18000a87a  mov     rbx, rcx
0x18000a87d  mov     r15, [rbp+13F0h+arg_28]
0x18000a884  xor     r13d, r13d
0x18000a887  cmp     cs:g_pfnThrowPlatformException, r13
0x18000a88e  setnz   dil
0x18000a892  xor     edx, edx; Val
0x18000a894  mov     r8d, 98h; Size
0x18000a89a  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x18000a89f  call    memset_0
0x18000a8a4  nop
0x18000a8a5  mov     [rbp+13F0h+OutputString], r13w
0x18000a8ad  mov     [rbp+13F0h+var_1430], r13b
0x18000a8b1  mov     rdx, [rbp+13F0h+arg_30]; int
0x18000a8b8  mov     ecx, [rdx]; this
0x18000a8ba  mov     [rsp+14F0h+var_14C8], ecx
0x18000a8be  mov     eax, [rdx+4]
0x18000a8c1  mov     [rsp+14F0h+var_14C4], eax
0x18000a8c5  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000a8ca  mov     r12d, eax
0x18000a8cd  mov     dword ptr [rsp+14F0h+var_14D0], r13d
0x18000a8d2  mov     ecx, r13d
0x18000a8d5  lea     eax, [r13+8]
0x18000a8d9  cmp     dword ptr [rdx+8], 1
0x18000a8dd  cmovz   ecx, eax
0x18000a8e0  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x18000a8e4  lea     ecx, [rax-7]
0x18000a8e7  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureInfo *)'::`2'::s_failureId
0x18000a8ef  inc     ecx
0x18000a8f1  mov     [rsp+14F0h+var_14C0], ecx
0x18000a8f5  mov     rcx, [rbp+13F0h+arg_38]
0x18000a8fc  test    rcx, rcx
0x18000a8ff  jz      short loc_18000A90C
0x18000a901  cmp     [rcx], r13w
0x18000a905  mov     [rsp+14F0h+var_14B8], rcx
0x18000a90a  jnz     short loc_18000A911
0x18000a90c  mov     [rsp+14F0h+var_14B8], r13
0x18000a911  call    cs:__imp_GetCurrentThreadId
0x18000a918  nop     dword ptr [rax+rax+00h]
0x18000a91d  mov     [rsp+14F0h+var_14B0], eax
0x18000a921  mov     [rsp+14F0h+var_1498], r14
0x18000a926  mov     [rsp+14F0h+var_1490], esi
0x18000a92a  mov     [rsp+14F0h+var_148C], r12d
0x18000a92f  mov     [rsp+14F0h+var_14A8], r13
0x18000a934  mov     [rsp+14F0h+var_14A0], r13
0x18000a939  mov     [rbp+13F0h+var_1448], r15
0x18000a93d  mov     [rbp+13F0h+var_1440], rbx
0x18000a941  mov     [rsp+14F0h+var_1488], r13
0x18000a946  xorps   xmm0, xmm0
0x18000a949  xor     eax, eax
0x18000a94b  movups  [rbp+13F0h+var_1468], xmm0
0x18000a94f  mov     [rbp+13F0h+var_1458], rax
0x18000a953  xorps   xmm1, xmm1
0x18000a956  movups  [rsp+14F0h+var_1480], xmm1
0x18000a95b  mov     [rbp+13F0h+var_1470], rax
0x18000a95f  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000a966  test    rax, rax
0x18000a969  jz      short loc_18000A976
0x18000a96b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a970  mov     [rbp+13F0h+var_1450], rax
0x18000a974  jmp     short loc_18000A97A
0x18000a976  mov     [rbp+13F0h+var_1450], r13
0x18000a97a  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000a981  test    rax, rax
0x18000a984  jz      short loc_18000A990
0x18000a986  lea     rcx, [rsp+14F0h+var_14D0]
0x18000a98b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a990  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000a997  test    rax, rax
0x18000a99a  jz      short loc_18000A9B0
0x18000a99c  mov     r8d, 400h
0x18000a9a2  lea     rdx, [rbp+13F0h+var_1430]
0x18000a9a6  lea     rcx, [rsp+14F0h+var_14D0]
0x18000a9ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a9b0  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000a9b7  test    rax, rax
0x18000a9ba  jz      short loc_18000A9C6
0x18000a9bc  lea     rcx, [rsp+14F0h+var_14D0]
0x18000a9c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a9c6  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000a9cd  test    rax, rax
0x18000a9d0  jz      short loc_18000A9E8
0x18000a9d2  test    dil, dil
0x18000a9d5  jnz     short loc_18000A9E8
0x18000a9d7  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000a9dc  jnz     short loc_18000A9E8
0x18000a9de  lea     rcx, [rsp+14F0h+var_14D0]
0x18000a9e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a9e8  cmp     [rsp+14F0h+var_14C8], r13d
0x18000a9ed  jl      short loc_18000A9F5
0x18000a9ef  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000a9f5  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x18000a9fc  jnz     short loc_18000AA23
0x18000a9fe  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000aa05  test    rax, rax
0x18000aa08  jz      short loc_18000AA13
0x18000aa0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aa0f  test    al, al
0x18000aa11  jmp     short loc_18000AA21
0x18000aa13  call    cs:__imp_IsDebuggerPresent
0x18000aa1a  nop     dword ptr [rax+rax+00h]
0x18000aa1f  test    eax, eax
0x18000aa21  jz      short loc_18000AA2C
0x18000aa23  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000aa28  mov     bl, 1
0x18000aa2a  jz      short loc_18000AA2F
0x18000aa2c  mov     bl, r13b
0x18000aa2f  test    dil, dil
0x18000aa32  jnz     short loc_18000AA5E
0x18000aa34  test    bl, bl
0x18000aa36  jnz     short loc_18000AA5E
0x18000aa38  mov     rax, cs:g_pfnResultLoggingCallback
0x18000aa3f  test    rax, rax
0x18000aa42  jz      short loc_18000AAC1
0x18000aa44  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x18000aa4b  jnz     short loc_18000AAC1
0x18000aa4d  xor     r8d, r8d
0x18000aa50  xor     edx, edx
0x18000aa52  lea     rcx, [rsp+14F0h+var_14D0]
0x18000aa57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aa5c  jmp     short loc_18000AAC1
0x18000aa5e  mov     esi, 800h
0x18000aa63  mov     rax, cs:g_pfnResultLoggingCallback
0x18000aa6a  test    rax, rax
0x18000aa6d  jz      short loc_18000AA8C
0x18000aa6f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x18000aa76  jnz     short loc_18000AA8C
0x18000aa78  mov     r8d, esi
0x18000aa7b  lea     rdx, [rbp+13F0h+OutputString]
0x18000aa82  lea     rcx, [rsp+14F0h+var_14D0]
0x18000aa87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aa8c  cmp     [rbp+13F0h+OutputString], r13w
0x18000aa94  jnz     short loc_18000AAAA
0x18000aa96  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x18000aa9b  mov     rdx, rsi; unsigned __int16 *
0x18000aa9e  lea     rcx, [rbp+13F0h+OutputString]; this
0x18000aaa5  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000aaaa  test    bl, bl
0x18000aaac  jz      short loc_18000AAC1
0x18000aaae  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x18000aab5  call    cs:__imp_OutputDebugStringW
0x18000aabc  nop     dword ptr [rax+rax+00h]
0x18000aac1  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x18000aac6  jnz     short loc_18000AAD1
0x18000aac8  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x18000aacf  jz      short loc_18000AAE3
0x18000aad1  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000aad8  test    rax, rax
0x18000aadb  jz      short loc_18000AAE3
0x18000aadd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aae2  nop
0x18000aae3  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x18000aae8  jz      short loc_18000AAF5
0x18000aaea  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000aaef  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18000aaf5  test    dil, dil
0x18000aaf8  jz      short loc_18000AB12
0x18000aafa  lea     rdx, [rbp+13F0h+OutputString]
0x18000ab01  lea     rcx, [rsp+14F0h+var_14D0]
0x18000ab06  mov     rax, cs:g_pfnThrowPlatformException
0x18000ab0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ab12  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000ab17  call    ?ThrowResultException@wil@@YAXAEBUFailureInfo@1@@Z; wil::ThrowResultException(wil::FailureInfo const &)
0x18000ab1c  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000ab21  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
