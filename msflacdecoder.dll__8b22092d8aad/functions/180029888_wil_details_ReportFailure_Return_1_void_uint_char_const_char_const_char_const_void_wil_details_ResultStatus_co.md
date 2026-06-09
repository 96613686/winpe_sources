# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180029888`
- end: `0x180029b1e`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `662`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18002955c`

## callees

- `0x180001e80`
- `0x1800028ac`
- `0x180016aa0`
- `0x180029888`
- `0x18002ba78`
- `0x18002e0b0`
- `0x18002f178`
- `0x18002f560`
- `0x180056010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180029933`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180029933`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180029ab8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180029ab8`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180029a2e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180029a2e`

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
0x180029888  mov     [rsp-8+arg_10], rbx
0x18002988d  push    rbp
0x18002988e  push    rsi
0x18002988f  push    rdi
0x180029890  push    r14
0x180029892  push    r15
0x180029894  lea     rbp, [rsp-13D0h]
0x18002989c  mov     eax, 14D0h
0x1800298a1  call    _alloca_probe
0x1800298a6  sub     rsp, rax
0x1800298a9  mov     rax, cs:__security_cookie
0x1800298b0  xor     rax, rsp
0x1800298b3  mov     [rbp+13F0h+var_30], rax
0x1800298ba  mov     esi, edx
0x1800298bc  mov     r14, rcx
0x1800298bf  mov     rdi, [rbp+13F0h+arg_28]
0x1800298c6  xor     edx, edx; Val
0x1800298c8  mov     r8d, 98h; Size
0x1800298ce  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x1800298d3  call    memset_0
0x1800298d8  nop
0x1800298d9  xor     r15d, r15d
0x1800298dc  mov     [rbp+13F0h+OutputString], r15w
0x1800298e4  mov     [rbp+13F0h+var_1430], r15b
0x1800298e8  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x1800298ef  mov     ecx, [rdx]; this
0x1800298f1  mov     [rsp+14F0h+var_14C8], ecx
0x1800298f5  mov     eax, [rdx+4]
0x1800298f8  mov     [rsp+14F0h+var_14C4], eax
0x1800298fc  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180029901  mov     ebx, eax
0x180029903  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x18002990b  mov     ecx, r15d
0x18002990e  lea     eax, [r15+8]
0x180029912  cmp     dword ptr [rdx+8], 1
0x180029916  cmovz   ecx, eax
0x180029919  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x18002991d  lea     ecx, [rax-7]
0x180029920  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180029928  inc     ecx
0x18002992a  mov     [rsp+14F0h+var_14C0], ecx
0x18002992e  mov     [rsp+14F0h+var_14B8], r15
0x180029933  call    cs:__imp_GetCurrentThreadId
0x180029939  mov     [rsp+14F0h+var_14B0], eax
0x18002993d  lea     rax, aWil; "wil"
0x180029944  mov     [rsp+14F0h+var_1498], rax
0x180029949  mov     [rsp+14F0h+var_1490], esi
0x18002994d  mov     [rsp+14F0h+var_148C], ebx
0x180029951  mov     [rsp+14F0h+var_14A8], r15
0x180029956  mov     [rsp+14F0h+var_14A0], r15
0x18002995b  mov     [rbp+13F0h+var_1448], rdi
0x18002995f  mov     [rbp+13F0h+var_1440], r14
0x180029963  mov     [rsp+14F0h+var_1488], r15
0x180029968  xorps   xmm0, xmm0
0x18002996b  xor     eax, eax
0x18002996d  movups  [rbp+13F0h+var_1468], xmm0
0x180029971  mov     [rbp+13F0h+var_1458], rax
0x180029975  xorps   xmm1, xmm1
0x180029978  movups  [rsp+14F0h+var_1480], xmm1
0x18002997d  mov     [rbp+13F0h+var_1470], rax
0x180029981  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180029988  test    rax, rax
0x18002998b  jz      short loc_180029998
0x18002998d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029992  mov     [rbp+13F0h+var_1450], rax
0x180029996  jmp     short loc_18002999C
0x180029998  mov     [rbp+13F0h+var_1450], r15
0x18002999c  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800299a3  test    rax, rax
0x1800299a6  jz      short loc_1800299B2
0x1800299a8  lea     rcx, [rsp+14F0h+var_14D0]
0x1800299ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800299b2  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800299b9  test    rax, rax
0x1800299bc  jz      short loc_1800299D2
0x1800299be  mov     r8d, 400h
0x1800299c4  lea     rdx, [rbp+13F0h+var_1430]
0x1800299c8  lea     rcx, [rsp+14F0h+var_14D0]
0x1800299cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800299d2  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800299d9  test    rax, rax
0x1800299dc  jz      short loc_1800299E8
0x1800299de  lea     rcx, [rsp+14F0h+var_14D0]
0x1800299e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800299e8  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800299ef  test    rax, rax
0x1800299f2  jz      short loc_180029A05
0x1800299f4  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800299f9  jnz     short loc_180029A05
0x1800299fb  lea     rcx, [rsp+14F0h+var_14D0]
0x180029a00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029a05  cmp     [rsp+14F0h+var_14C8], r15d
0x180029a0a  jge     loc_180029B18
0x180029a10  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x180029a17  jnz     short loc_180029A38
0x180029a19  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180029a20  test    rax, rax
0x180029a23  jz      short loc_180029A2E
0x180029a25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029a2a  test    al, al
0x180029a2c  jmp     short loc_180029A36
0x180029a2e  call    cs:__imp_IsDebuggerPresent
0x180029a34  test    eax, eax
0x180029a36  jz      short loc_180029A3F
0x180029a38  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180029a3d  jz      short loc_180029A65
0x180029a3f  mov     rax, cs:g_pfnResultLoggingCallback
0x180029a46  test    rax, rax
0x180029a49  jz      short loc_180029ABE
0x180029a4b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180029a52  jnz     short loc_180029ABE
0x180029a54  xor     r8d, r8d
0x180029a57  xor     edx, edx
0x180029a59  lea     rcx, [rsp+14F0h+var_14D0]
0x180029a5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029a63  jmp     short loc_180029ABE
0x180029a65  mov     ebx, 800h
0x180029a6a  mov     rax, cs:g_pfnResultLoggingCallback
0x180029a71  test    rax, rax
0x180029a74  jz      short loc_180029A93
0x180029a76  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180029a7d  jnz     short loc_180029A93
0x180029a7f  mov     r8d, ebx
0x180029a82  lea     rdx, [rbp+13F0h+OutputString]
0x180029a89  lea     rcx, [rsp+14F0h+var_14D0]
0x180029a8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029a93  cmp     [rbp+13F0h+OutputString], r15w
0x180029a9b  jnz     short loc_180029AB1
0x180029a9d  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180029aa2  mov     rdx, rbx; unsigned __int16 *
0x180029aa5  lea     rcx, [rbp+13F0h+OutputString]; this
0x180029aac  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180029ab1  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180029ab8  call    cs:__imp_OutputDebugStringW
0x180029abe  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180029ac3  jnz     short loc_180029ACE
0x180029ac5  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x180029acc  jz      short loc_180029AE0
0x180029ace  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180029ad5  test    rax, rax
0x180029ad8  jz      short loc_180029AE0
0x180029ada  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029adf  nop
0x180029ae0  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x180029ae5  jnz     short loc_180029B0D
0x180029ae7  mov     rcx, [rbp+13F0h+var_30]
0x180029aee  xor     rcx, rsp; StackCookie
0x180029af1  call    __security_check_cookie
0x180029af6  mov     rbx, [rsp+14F0h+arg_10]
0x180029afe  add     rsp, 14D0h
0x180029b05  pop     r15
0x180029b07  pop     r14
0x180029b09  pop     rdi
0x180029b0a  pop     rsi
0x180029b0b  pop     rbp
0x180029b0c  retn
0x180029b0d  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180029b12  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180029b18  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
