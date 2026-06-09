# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180021db0`
- end: `0x180022067`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `695`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180021870`

## callees

- `0x18001e1d0`
- `0x180021db0`
- `0x180024540`
- `0x1800267a0`
- `0x1800290f0`
- `0x180029310`
- `0x18002f5f0`
- `0x180030010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180021e7c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180021e7c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180022001`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180022001`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180021f77`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180021f77`

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
0x180021db0  mov     [rsp-8+arg_10], rbx
0x180021db5  push    rbp
0x180021db6  push    rsi
0x180021db7  push    rdi
0x180021db8  push    r14
0x180021dba  push    r15
0x180021dbc  lea     rbp, [rsp-13D0h]
0x180021dc4  mov     eax, 14D0h
0x180021dc9  call    _alloca_probe
0x180021dce  sub     rsp, rax
0x180021dd1  mov     rax, cs:__security_cookie
0x180021dd8  xor     rax, rsp
0x180021ddb  mov     [rbp+13F0h+var_30], rax
0x180021de2  mov     esi, edx
0x180021de4  mov     r14, rcx
0x180021de7  mov     rdi, [rbp+13F0h+arg_28]
0x180021dee  xorps   xmm0, xmm0
0x180021df1  xor     eax, eax
0x180021df3  movups  xmmword ptr [rsp+14F0h+var_14D0], xmm0
0x180021df8  movups  [rsp+14F0h+var_14C0], xmm0
0x180021dfd  movups  [rsp+14F0h+var_14B0], xmm0
0x180021e02  movups  [rsp+14F0h+var_14A0], xmm0
0x180021e07  movups  [rsp+14F0h+var_1490], xmm0
0x180021e0c  movups  [rsp+14F0h+var_1480], xmm0
0x180021e11  movups  [rbp+13F0h+var_1470], xmm0
0x180021e15  movups  [rbp+13F0h+var_1460], xmm0
0x180021e19  movups  [rbp+13F0h+var_1450], xmm0
0x180021e1d  mov     [rbp+13F0h+var_1440], rax
0x180021e21  xor     r15d, r15d
0x180021e24  mov     [rbp+13F0h+OutputString], r15w
0x180021e2c  mov     [rbp+13F0h+var_1430], r15b
0x180021e30  mov     r8, [rbp+13F0h+arg_30]
0x180021e37  mov     ecx, [r8]; this
0x180021e3a  mov     dword ptr [rsp+14F0h+var_14D0+8], ecx
0x180021e3e  mov     eax, [r8+4]
0x180021e42  mov     dword ptr [rsp+14F0h+var_14D0+0Ch], eax
0x180021e46  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180021e4b  mov     ebx, eax
0x180021e4d  mov     edx, 1
0x180021e52  mov     dword ptr [rsp+14F0h+var_14D0], edx
0x180021e56  mov     ecx, r15d
0x180021e59  mov     eax, 8
0x180021e5e  cmp     [r8+8], edx
0x180021e62  cmovz   ecx, eax
0x180021e65  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180021e69  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, edx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180021e71  inc     edx
0x180021e73  mov     dword ptr [rsp+14F0h+var_14C0], edx
0x180021e77  mov     qword ptr [rsp+14F0h+var_14C0+8], r15
0x180021e7c  call    cs:__imp_GetCurrentThreadId
0x180021e82  mov     dword ptr [rsp+14F0h+var_14B0], eax
0x180021e86  lea     rax, aWil; "wil"
0x180021e8d  mov     qword ptr [rsp+14F0h+var_14A0+8], rax
0x180021e92  mov     dword ptr [rsp+14F0h+var_1490], esi
0x180021e96  mov     dword ptr [rsp+14F0h+var_1490+4], ebx
0x180021e9a  mov     qword ptr [rsp+14F0h+var_14B0+8], r15
0x180021e9f  mov     qword ptr [rsp+14F0h+var_14A0], r15
0x180021ea4  mov     qword ptr [rbp+13F0h+var_1450+8], rdi
0x180021ea8  mov     [rbp+13F0h+var_1440], r14
0x180021eac  mov     qword ptr [rsp+14F0h+var_1490+8], r15
0x180021eb1  xorps   xmm0, xmm0
0x180021eb4  xor     eax, eax
0x180021eb6  movups  [rbp+13F0h+var_1470+8], xmm0
0x180021eba  mov     qword ptr [rbp+13F0h+var_1460+8], rax
0x180021ebe  xorps   xmm1, xmm1
0x180021ec1  movups  [rsp+14F0h+var_1480], xmm1
0x180021ec6  mov     qword ptr [rbp+13F0h+var_1470], rax
0x180021eca  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180021ed1  test    rax, rax
0x180021ed4  jz      short loc_180021EE1
0x180021ed6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021edb  mov     qword ptr [rbp+13F0h+var_1450], rax
0x180021edf  jmp     short loc_180021EE5
0x180021ee1  mov     qword ptr [rbp+13F0h+var_1450], r15
0x180021ee5  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180021eec  test    rax, rax
0x180021eef  jz      short loc_180021EFB
0x180021ef1  lea     rcx, [rsp+14F0h+var_14D0]
0x180021ef6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021efb  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180021f02  test    rax, rax
0x180021f05  jz      short loc_180021F1B
0x180021f07  mov     r8d, 400h
0x180021f0d  lea     rdx, [rbp+13F0h+var_1430]
0x180021f11  lea     rcx, [rsp+14F0h+var_14D0]
0x180021f16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021f1b  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180021f22  test    rax, rax
0x180021f25  jz      short loc_180021F31
0x180021f27  lea     rcx, [rsp+14F0h+var_14D0]
0x180021f2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021f31  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180021f38  test    rax, rax
0x180021f3b  jz      short loc_180021F4E
0x180021f3d  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180021f42  jnz     short loc_180021F4E
0x180021f44  lea     rcx, [rsp+14F0h+var_14D0]
0x180021f49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021f4e  cmp     dword ptr [rsp+14F0h+var_14D0+8], r15d
0x180021f53  jge     loc_180022061
0x180021f59  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x180021f60  jnz     short loc_180021F81
0x180021f62  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180021f69  test    rax, rax
0x180021f6c  jz      short loc_180021F77
0x180021f6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021f73  test    al, al
0x180021f75  jmp     short loc_180021F7F
0x180021f77  call    cs:__imp_IsDebuggerPresent
0x180021f7d  test    eax, eax
0x180021f7f  jz      short loc_180021F88
0x180021f81  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180021f86  jz      short loc_180021FAE
0x180021f88  mov     rax, cs:g_pfnResultLoggingCallback
0x180021f8f  test    rax, rax
0x180021f92  jz      short loc_180022007
0x180021f94  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180021f9b  jnz     short loc_180022007
0x180021f9d  xor     r8d, r8d
0x180021fa0  xor     edx, edx
0x180021fa2  lea     rcx, [rsp+14F0h+var_14D0]
0x180021fa7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021fac  jmp     short loc_180022007
0x180021fae  mov     rax, cs:g_pfnResultLoggingCallback
0x180021fb5  test    rax, rax
0x180021fb8  jz      short loc_180021FDA
0x180021fba  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180021fc1  jnz     short loc_180021FDA
0x180021fc3  mov     r8d, 800h
0x180021fc9  lea     rdx, [rbp+13F0h+OutputString]
0x180021fd0  lea     rcx, [rsp+14F0h+var_14D0]
0x180021fd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021fda  cmp     [rbp+13F0h+OutputString], r15w
0x180021fe2  jnz     short loc_180021FFA
0x180021fe4  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180021fe9  mov     edx, 800h; unsigned __int16 *
0x180021fee  lea     rcx, [rbp+13F0h+OutputString]; this
0x180021ff5  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180021ffa  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180022001  call    cs:__imp_OutputDebugStringW
0x180022007  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x18002200c  jnz     short loc_180022017
0x18002200e  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x180022015  jz      short loc_180022029
0x180022017  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18002201e  test    rax, rax
0x180022021  jz      short loc_180022029
0x180022023  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022028  nop
0x180022029  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x18002202e  jnz     short loc_180022056
0x180022030  mov     rcx, [rbp+13F0h+var_30]
0x180022037  xor     rcx, rsp; StackCookie
0x18002203a  call    __security_check_cookie
0x18002203f  mov     rbx, [rsp+14F0h+arg_10]
0x180022047  add     rsp, 14D0h
0x18002204e  pop     r15
0x180022050  pop     r14
0x180022052  pop     rdi
0x180022053  pop     rsi
0x180022054  pop     rbp
0x180022055  retn
0x180022056  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18002205b  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180022061  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
