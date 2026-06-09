# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x18000385c`
- end: `0x180003af2`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `662`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18000333c`

## callees

- `0x180002270`
- `0x180002be8`
- `0x18000385c`
- `0x1800067f4`
- `0x180008858`
- `0x18000c3b0`
- `0x18000c57c`
- `0x180013ff0`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003907`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003907`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003a02`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003a02`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003a8c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003a8c`

## pseudocode

```c
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
0x18000385c  mov     [rsp-8+arg_10], rbx
0x180003861  push    rbp
0x180003862  push    rsi
0x180003863  push    rdi
0x180003864  push    r14
0x180003866  push    r15
0x180003868  lea     rbp, [rsp-13D0h]
0x180003870  mov     eax, 14D0h
0x180003875  call    _alloca_probe
0x18000387a  sub     rsp, rax
0x18000387d  mov     rax, cs:__security_cookie
0x180003884  xor     rax, rsp
0x180003887  mov     [rbp+13F0h+var_30], rax
0x18000388e  mov     esi, edx
0x180003890  mov     r14, rcx
0x180003893  mov     rdi, [rbp+13F0h+arg_28]
0x18000389a  xor     edx, edx; Val
0x18000389c  mov     r8d, 98h; Size
0x1800038a2  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x1800038a7  call    memset_0
0x1800038ac  nop
0x1800038ad  xor     r15d, r15d
0x1800038b0  mov     [rbp+13F0h+OutputString], r15w
0x1800038b8  mov     [rbp+13F0h+var_1430], r15b
0x1800038bc  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x1800038c3  mov     ecx, [rdx]; this
0x1800038c5  mov     [rsp+14F0h+var_14C8], ecx
0x1800038c9  mov     eax, [rdx+4]
0x1800038cc  mov     [rsp+14F0h+var_14C4], eax
0x1800038d0  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800038d5  mov     ebx, eax
0x1800038d7  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x1800038df  mov     ecx, r15d
0x1800038e2  lea     eax, [r15+8]
0x1800038e6  cmp     dword ptr [rdx+8], 1
0x1800038ea  cmovz   ecx, eax
0x1800038ed  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x1800038f1  lea     ecx, [rax-7]
0x1800038f4  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800038fc  inc     ecx
0x1800038fe  mov     [rsp+14F0h+var_14C0], ecx
0x180003902  mov     [rsp+14F0h+var_14B8], r15
0x180003907  call    cs:__imp_GetCurrentThreadId
0x18000390d  mov     [rsp+14F0h+var_14B0], eax
0x180003911  lea     rax, aWil; "wil"
0x180003918  mov     [rsp+14F0h+var_1498], rax
0x18000391d  mov     [rsp+14F0h+var_1490], esi
0x180003921  mov     [rsp+14F0h+var_148C], ebx
0x180003925  mov     [rsp+14F0h+var_14A8], r15
0x18000392a  mov     [rsp+14F0h+var_14A0], r15
0x18000392f  mov     [rbp+13F0h+var_1448], rdi
0x180003933  mov     [rbp+13F0h+var_1440], r14
0x180003937  mov     [rsp+14F0h+var_1488], r15
0x18000393c  xorps   xmm0, xmm0
0x18000393f  xor     eax, eax
0x180003941  movups  [rbp+13F0h+var_1468], xmm0
0x180003945  mov     [rbp+13F0h+var_1458], rax
0x180003949  xorps   xmm1, xmm1
0x18000394c  movups  [rsp+14F0h+var_1480], xmm1
0x180003951  mov     [rbp+13F0h+var_1470], rax
0x180003955  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000395c  test    rax, rax
0x18000395f  jz      short loc_18000396C
0x180003961  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003966  mov     [rbp+13F0h+var_1450], rax
0x18000396a  jmp     short loc_180003970
0x18000396c  mov     [rbp+13F0h+var_1450], r15
0x180003970  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180003977  test    rax, rax
0x18000397a  jz      short loc_180003986
0x18000397c  lea     rcx, [rsp+14F0h+var_14D0]
0x180003981  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003986  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000398d  test    rax, rax
0x180003990  jz      short loc_1800039A6
0x180003992  mov     r8d, 400h
0x180003998  lea     rdx, [rbp+13F0h+var_1430]
0x18000399c  lea     rcx, [rsp+14F0h+var_14D0]
0x1800039a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800039a6  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800039ad  test    rax, rax
0x1800039b0  jz      short loc_1800039BC
0x1800039b2  lea     rcx, [rsp+14F0h+var_14D0]
0x1800039b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800039bc  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800039c3  test    rax, rax
0x1800039c6  jz      short loc_1800039D9
0x1800039c8  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800039cd  jnz     short loc_1800039D9
0x1800039cf  lea     rcx, [rsp+14F0h+var_14D0]
0x1800039d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800039d9  cmp     [rsp+14F0h+var_14C8], r15d
0x1800039de  jge     loc_180003AEC
0x1800039e4  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x1800039eb  jnz     short loc_180003A0C
0x1800039ed  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800039f4  test    rax, rax
0x1800039f7  jz      short loc_180003A02
0x1800039f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800039fe  test    al, al
0x180003a00  jmp     short loc_180003A0A
0x180003a02  call    cs:__imp_IsDebuggerPresent
0x180003a08  test    eax, eax
0x180003a0a  jz      short loc_180003A13
0x180003a0c  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180003a11  jz      short loc_180003A39
0x180003a13  mov     rax, cs:g_pfnResultLoggingCallback
0x180003a1a  test    rax, rax
0x180003a1d  jz      short loc_180003A92
0x180003a1f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180003a26  jnz     short loc_180003A92
0x180003a28  xor     r8d, r8d
0x180003a2b  xor     edx, edx
0x180003a2d  lea     rcx, [rsp+14F0h+var_14D0]
0x180003a32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a37  jmp     short loc_180003A92
0x180003a39  mov     ebx, 800h
0x180003a3e  mov     rax, cs:g_pfnResultLoggingCallback
0x180003a45  test    rax, rax
0x180003a48  jz      short loc_180003A67
0x180003a4a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180003a51  jnz     short loc_180003A67
0x180003a53  mov     r8d, ebx
0x180003a56  lea     rdx, [rbp+13F0h+OutputString]
0x180003a5d  lea     rcx, [rsp+14F0h+var_14D0]
0x180003a62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a67  cmp     [rbp+13F0h+OutputString], r15w
0x180003a6f  jnz     short loc_180003A85
0x180003a71  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180003a76  mov     rdx, rbx; unsigned __int16 *
0x180003a79  lea     rcx, [rbp+13F0h+OutputString]; this
0x180003a80  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180003a85  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180003a8c  call    cs:__imp_OutputDebugStringW
0x180003a92  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180003a97  jnz     short loc_180003AA2
0x180003a99  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x180003aa0  jz      short loc_180003AB4
0x180003aa2  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180003aa9  test    rax, rax
0x180003aac  jz      short loc_180003AB4
0x180003aae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ab3  nop
0x180003ab4  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x180003ab9  jnz     short loc_180003AE1
0x180003abb  mov     rcx, [rbp+13F0h+var_30]
0x180003ac2  xor     rcx, rsp; StackCookie
0x180003ac5  call    __security_check_cookie
0x180003aca  mov     rbx, [rsp+14F0h+arg_10]
0x180003ad2  add     rsp, 14D0h
0x180003ad9  pop     r15
0x180003adb  pop     r14
0x180003add  pop     rdi
0x180003ade  pop     rsi
0x180003adf  pop     rbp
0x180003ae0  retn
0x180003ae1  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180003ae6  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180003aec  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
