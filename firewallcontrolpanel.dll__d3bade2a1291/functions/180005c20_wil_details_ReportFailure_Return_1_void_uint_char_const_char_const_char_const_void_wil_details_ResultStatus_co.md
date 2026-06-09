# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180005c20`
- end: `0x180005ed7`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `695`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180005910`

## callees

- `0x180005c20`
- `0x180006a24`
- `0x180007a70`
- `0x180008538`
- `0x18000875c`
- `0x180030ea0`
- `0x180030f60`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005cec`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005cec`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180005de7`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180005de7`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005e71`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005e71`

## pseudocode

```c
void __fastcall wil::details::ReportFailure_Return<1>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        unsigned __int64 *a7)
{
  unsigned int v9; // ebx
  int v10; // ecx
  __int64 v11; // r8
  const struct wil::FailureInfo *v12; // rdx
  wil::details::in1diag3 *v13; // rcx
  const struct wil::FailureInfo *v14; // r9
  bool v15; // zf
  unsigned __int64 v16[2]; // [rsp+20h] [rbp-E0h] BYREF
  __int128 v17; // [rsp+30h] [rbp-D0h]
  __int128 v18; // [rsp+40h] [rbp-C0h]
  __int128 v19; // [rsp+50h] [rbp-B0h]
  __int128 v20; // [rsp+60h] [rbp-A0h]
  __int128 v21; // [rsp+70h] [rbp-90h]
  _OWORD v22[2]; // [rsp+80h] [rbp-80h] BYREF
  __int128 v23; // [rsp+A0h] [rbp-60h]
  __int64 v24; // [rsp+B0h] [rbp-50h]
  _BYTE v25[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  *(_OWORD *)v16 = 0;
  v17 = 0;
  v18 = 0;
  v19 = 0;
  v20 = 0;
  v21 = 0;
  memset(v22, 0, sizeof(v22));
  v23 = 0;
  v24 = 0;
  OutputString[0] = 0;
  v25[0] = 0;
  v16[1] = *a7;
  v9 = wil::details::RecordReturn((wil::details *)LODWORD(v16[1]), a2);
  LODWORD(v16[0]) = 1;
  v10 = 0;
  if ( *(_DWORD *)(v11 + 8) == 1 )
    v10 = 8;
  HIDWORD(v16[0]) = v10;
  LODWORD(v17) = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  *((_QWORD *)&v17 + 1) = 0;
  LODWORD(v18) = GetCurrentThreadId();
  *((_QWORD *)&v19 + 1) = "wil";
  v20 = __PAIR64__(v9, a2);
  *((_QWORD *)&v18 + 1) = 0;
  *(_QWORD *)&v19 = 0;
  *((_QWORD *)&v23 + 1) = a6;
  v24 = a1;
  v21 = 0;
  memset(v22, 0, sizeof(v22));
  if ( wil::details::g_pfnGetModuleName )
    *(_QWORD *)&v23 = wil::details::g_pfnGetModuleName(v13);
  else
    *(_QWORD *)&v23 = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(v16);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(v16, v25, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(v16);
  if ( wil::details::g_pfnOriginateCallback && (v16[0] & 0x200000000LL) == 0 )
    wil::details::g_pfnOriginateCallback(v16);
  if ( SLODWORD(v16[1]) >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v13);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v15 = !IsDebuggerPresent())
      : (v15 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v13) == 0),
        v15)
    || (v16[0] & 0x200000000LL) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(v16, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(v16, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)v16, v14);
    OutputDebugStringW(OutputString);
  }
  if ( ((v16[0] & 0x400000000LL) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v13);
  if ( (v16[0] & 0x100000000LL) != 0 )
    wil::details::WilFailFast((wil::details *)v16, v12);
}

```

## disassembly

```asm
0x180005c20  mov     [rsp-8+arg_10], rbx
0x180005c25  push    rbp
0x180005c26  push    rsi
0x180005c27  push    rdi
0x180005c28  push    r14
0x180005c2a  push    r15
0x180005c2c  lea     rbp, [rsp-13D0h]
0x180005c34  mov     eax, 14D0h
0x180005c39  call    _alloca_probe
0x180005c3e  sub     rsp, rax
0x180005c41  mov     rax, cs:__security_cookie
0x180005c48  xor     rax, rsp
0x180005c4b  mov     [rbp+13F0h+var_30], rax
0x180005c52  mov     esi, edx
0x180005c54  mov     r14, rcx
0x180005c57  mov     rdi, [rbp+13F0h+arg_28]
0x180005c5e  xorps   xmm0, xmm0
0x180005c61  xor     eax, eax
0x180005c63  movups  xmmword ptr [rsp+14F0h+var_14D0], xmm0
0x180005c68  movups  [rsp+14F0h+var_14C0], xmm0
0x180005c6d  movups  [rsp+14F0h+var_14B0], xmm0
0x180005c72  movups  [rsp+14F0h+var_14A0], xmm0
0x180005c77  movups  [rsp+14F0h+var_1490], xmm0
0x180005c7c  movups  [rsp+14F0h+var_1480], xmm0
0x180005c81  movups  [rbp+13F0h+var_1470], xmm0
0x180005c85  movups  [rbp+13F0h+var_1460], xmm0
0x180005c89  movups  [rbp+13F0h+var_1450], xmm0
0x180005c8d  mov     [rbp+13F0h+var_1440], rax
0x180005c91  xor     r15d, r15d
0x180005c94  mov     [rbp+13F0h+OutputString], r15w
0x180005c9c  mov     [rbp+13F0h+var_1430], r15b
0x180005ca0  mov     r8, [rbp+13F0h+arg_30]
0x180005ca7  mov     ecx, [r8]; this
0x180005caa  mov     dword ptr [rsp+14F0h+var_14D0+8], ecx
0x180005cae  mov     eax, [r8+4]
0x180005cb2  mov     dword ptr [rsp+14F0h+var_14D0+0Ch], eax
0x180005cb6  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180005cbb  mov     ebx, eax
0x180005cbd  mov     edx, 1
0x180005cc2  mov     dword ptr [rsp+14F0h+var_14D0], edx
0x180005cc6  mov     ecx, r15d
0x180005cc9  mov     eax, 8
0x180005cce  cmp     [r8+8], edx
0x180005cd2  cmovz   ecx, eax
0x180005cd5  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180005cd9  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, edx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180005ce1  inc     edx
0x180005ce3  mov     dword ptr [rsp+14F0h+var_14C0], edx
0x180005ce7  mov     qword ptr [rsp+14F0h+var_14C0+8], r15
0x180005cec  call    cs:__imp_GetCurrentThreadId
0x180005cf2  mov     dword ptr [rsp+14F0h+var_14B0], eax
0x180005cf6  lea     rax, aWil; "wil"
0x180005cfd  mov     qword ptr [rsp+14F0h+var_14A0+8], rax
0x180005d02  mov     dword ptr [rsp+14F0h+var_1490], esi
0x180005d06  mov     dword ptr [rsp+14F0h+var_1490+4], ebx
0x180005d0a  mov     qword ptr [rsp+14F0h+var_14B0+8], r15
0x180005d0f  mov     qword ptr [rsp+14F0h+var_14A0], r15
0x180005d14  mov     qword ptr [rbp+13F0h+var_1450+8], rdi
0x180005d18  mov     [rbp+13F0h+var_1440], r14
0x180005d1c  mov     qword ptr [rsp+14F0h+var_1490+8], r15
0x180005d21  xorps   xmm0, xmm0
0x180005d24  xor     eax, eax
0x180005d26  movups  [rbp+13F0h+var_1470+8], xmm0
0x180005d2a  mov     qword ptr [rbp+13F0h+var_1460+8], rax
0x180005d2e  xorps   xmm1, xmm1
0x180005d31  movups  [rsp+14F0h+var_1480], xmm1
0x180005d36  mov     qword ptr [rbp+13F0h+var_1470], rax
0x180005d3a  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180005d41  test    rax, rax
0x180005d44  jz      short loc_180005D51
0x180005d46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d4b  mov     qword ptr [rbp+13F0h+var_1450], rax
0x180005d4f  jmp     short loc_180005D55
0x180005d51  mov     qword ptr [rbp+13F0h+var_1450], r15
0x180005d55  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180005d5c  test    rax, rax
0x180005d5f  jz      short loc_180005D6B
0x180005d61  lea     rcx, [rsp+14F0h+var_14D0]
0x180005d66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d6b  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180005d72  test    rax, rax
0x180005d75  jz      short loc_180005D8B
0x180005d77  mov     r8d, 400h
0x180005d7d  lea     rdx, [rbp+13F0h+var_1430]
0x180005d81  lea     rcx, [rsp+14F0h+var_14D0]
0x180005d86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d8b  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005d92  test    rax, rax
0x180005d95  jz      short loc_180005DA1
0x180005d97  lea     rcx, [rsp+14F0h+var_14D0]
0x180005d9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005da1  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005da8  test    rax, rax
0x180005dab  jz      short loc_180005DBE
0x180005dad  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180005db2  jnz     short loc_180005DBE
0x180005db4  lea     rcx, [rsp+14F0h+var_14D0]
0x180005db9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005dbe  cmp     dword ptr [rsp+14F0h+var_14D0+8], r15d
0x180005dc3  jge     loc_180005ED1
0x180005dc9  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x180005dd0  jnz     short loc_180005DF1
0x180005dd2  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180005dd9  test    rax, rax
0x180005ddc  jz      short loc_180005DE7
0x180005dde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005de3  test    al, al
0x180005de5  jmp     short loc_180005DEF
0x180005de7  call    cs:__imp_IsDebuggerPresent
0x180005ded  test    eax, eax
0x180005def  jz      short loc_180005DF8
0x180005df1  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180005df6  jz      short loc_180005E1E
0x180005df8  mov     rax, cs:g_pfnResultLoggingCallback
0x180005dff  test    rax, rax
0x180005e02  jz      short loc_180005E77
0x180005e04  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180005e0b  jnz     short loc_180005E77
0x180005e0d  xor     r8d, r8d
0x180005e10  xor     edx, edx
0x180005e12  lea     rcx, [rsp+14F0h+var_14D0]
0x180005e17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e1c  jmp     short loc_180005E77
0x180005e1e  mov     rax, cs:g_pfnResultLoggingCallback
0x180005e25  test    rax, rax
0x180005e28  jz      short loc_180005E4A
0x180005e2a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180005e31  jnz     short loc_180005E4A
0x180005e33  mov     r8d, 800h
0x180005e39  lea     rdx, [rbp+13F0h+OutputString]
0x180005e40  lea     rcx, [rsp+14F0h+var_14D0]
0x180005e45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e4a  cmp     [rbp+13F0h+OutputString], r15w
0x180005e52  jnz     short loc_180005E6A
0x180005e54  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180005e59  mov     edx, 800h; unsigned __int16 *
0x180005e5e  lea     rcx, [rbp+13F0h+OutputString]; this
0x180005e65  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180005e6a  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180005e71  call    cs:__imp_OutputDebugStringW
0x180005e77  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180005e7c  jnz     short loc_180005E87
0x180005e7e  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x180005e85  jz      short loc_180005E99
0x180005e87  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180005e8e  test    rax, rax
0x180005e91  jz      short loc_180005E99
0x180005e93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e98  nop
0x180005e99  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x180005e9e  jnz     short loc_180005EC6
0x180005ea0  mov     rcx, [rbp+13F0h+var_30]
0x180005ea7  xor     rcx, rsp; StackCookie
0x180005eaa  call    __security_check_cookie
0x180005eaf  mov     rbx, [rsp+14F0h+arg_10]
0x180005eb7  add     rsp, 14D0h
0x180005ebe  pop     r15
0x180005ec0  pop     r14
0x180005ec2  pop     rdi
0x180005ec3  pop     rsi
0x180005ec4  pop     rbp
0x180005ec5  retn
0x180005ec6  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180005ecb  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180005ed1  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
