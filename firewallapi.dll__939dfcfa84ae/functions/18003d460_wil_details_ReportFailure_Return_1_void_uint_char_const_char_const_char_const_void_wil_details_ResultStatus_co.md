# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x18003d460`
- end: `0x18003d72a`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `714`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180024ec0`

## callees

- `0x1800294b0`
- `0x18003d460`
- `0x18003efe4`
- `0x180040124`
- `0x180041370`
- `0x18004152c`
- `0x18005f820`
- `0x180062010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003d52c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003d52c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18003d6bd`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18003d6bd`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18003d62d`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18003d62d`

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
0x18003d460  mov     [rsp-8+arg_10], rbx
0x18003d465  push    rbp
0x18003d466  push    rsi
0x18003d467  push    rdi
0x18003d468  push    r14
0x18003d46a  push    r15
0x18003d46c  lea     rbp, [rsp-13D0h]
0x18003d474  mov     eax, 14D0h
0x18003d479  call    _alloca_probe
0x18003d47e  sub     rsp, rax
0x18003d481  mov     rax, cs:__security_cookie
0x18003d488  xor     rax, rsp
0x18003d48b  mov     [rbp+13F0h+var_30], rax
0x18003d492  mov     esi, edx
0x18003d494  mov     r14, rcx
0x18003d497  mov     rdi, [rbp+13F0h+arg_28]
0x18003d49e  xorps   xmm0, xmm0
0x18003d4a1  xor     eax, eax
0x18003d4a3  movups  xmmword ptr [rsp+14F0h+var_14D0], xmm0
0x18003d4a8  movups  [rsp+14F0h+var_14C0], xmm0
0x18003d4ad  movups  [rsp+14F0h+var_14B0], xmm0
0x18003d4b2  movups  [rsp+14F0h+var_14A0], xmm0
0x18003d4b7  movups  [rsp+14F0h+var_1490], xmm0
0x18003d4bc  movups  [rsp+14F0h+var_1480], xmm0
0x18003d4c1  movups  [rbp+13F0h+var_1470], xmm0
0x18003d4c5  movups  [rbp+13F0h+var_1460], xmm0
0x18003d4c9  movups  [rbp+13F0h+var_1450], xmm0
0x18003d4cd  mov     [rbp+13F0h+var_1440], rax
0x18003d4d1  xor     r15d, r15d
0x18003d4d4  mov     [rbp+13F0h+OutputString], r15w
0x18003d4dc  mov     [rbp+13F0h+var_1430], r15b
0x18003d4e0  mov     r8, [rbp+13F0h+arg_30]
0x18003d4e7  mov     ecx, [r8]; this
0x18003d4ea  mov     dword ptr [rsp+14F0h+var_14D0+8], ecx
0x18003d4ee  mov     eax, [r8+4]
0x18003d4f2  mov     dword ptr [rsp+14F0h+var_14D0+0Ch], eax
0x18003d4f6  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18003d4fb  mov     ebx, eax
0x18003d4fd  mov     edx, 1
0x18003d502  mov     dword ptr [rsp+14F0h+var_14D0], edx
0x18003d506  mov     ecx, r15d
0x18003d509  mov     eax, 8
0x18003d50e  cmp     [r8+8], edx
0x18003d512  cmovz   ecx, eax
0x18003d515  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x18003d519  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, edx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18003d521  inc     edx
0x18003d523  mov     dword ptr [rsp+14F0h+var_14C0], edx
0x18003d527  mov     qword ptr [rsp+14F0h+var_14C0+8], r15
0x18003d52c  call    cs:__imp_GetCurrentThreadId
0x18003d533  nop     dword ptr [rax+rax+00h]
0x18003d538  mov     dword ptr [rsp+14F0h+var_14B0], eax
0x18003d53c  lea     rax, aWil; "wil"
0x18003d543  mov     qword ptr [rsp+14F0h+var_14A0+8], rax
0x18003d548  mov     dword ptr [rsp+14F0h+var_1490], esi
0x18003d54c  mov     dword ptr [rsp+14F0h+var_1490+4], ebx
0x18003d550  mov     qword ptr [rsp+14F0h+var_14B0+8], r15
0x18003d555  mov     qword ptr [rsp+14F0h+var_14A0], r15
0x18003d55a  mov     qword ptr [rbp+13F0h+var_1450+8], rdi
0x18003d55e  mov     [rbp+13F0h+var_1440], r14
0x18003d562  mov     qword ptr [rsp+14F0h+var_1490+8], r15
0x18003d567  xorps   xmm0, xmm0
0x18003d56a  xor     eax, eax
0x18003d56c  movups  [rbp+13F0h+var_1470+8], xmm0
0x18003d570  mov     qword ptr [rbp+13F0h+var_1460+8], rax
0x18003d574  xorps   xmm1, xmm1
0x18003d577  movups  [rsp+14F0h+var_1480], xmm1
0x18003d57c  mov     qword ptr [rbp+13F0h+var_1470], rax
0x18003d580  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18003d587  test    rax, rax
0x18003d58a  jz      short loc_18003D597
0x18003d58c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d591  mov     qword ptr [rbp+13F0h+var_1450], rax
0x18003d595  jmp     short loc_18003D59B
0x18003d597  mov     qword ptr [rbp+13F0h+var_1450], r15
0x18003d59b  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18003d5a2  test    rax, rax
0x18003d5a5  jz      short loc_18003D5B1
0x18003d5a7  lea     rcx, [rsp+14F0h+var_14D0]
0x18003d5ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d5b1  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18003d5b8  test    rax, rax
0x18003d5bb  jz      short loc_18003D5D1
0x18003d5bd  mov     r8d, 400h
0x18003d5c3  lea     rdx, [rbp+13F0h+var_1430]
0x18003d5c7  lea     rcx, [rsp+14F0h+var_14D0]
0x18003d5cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d5d1  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18003d5d8  test    rax, rax
0x18003d5db  jz      short loc_18003D5E7
0x18003d5dd  lea     rcx, [rsp+14F0h+var_14D0]
0x18003d5e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d5e7  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18003d5ee  test    rax, rax
0x18003d5f1  jz      short loc_18003D604
0x18003d5f3  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18003d5f8  jnz     short loc_18003D604
0x18003d5fa  lea     rcx, [rsp+14F0h+var_14D0]
0x18003d5ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d604  cmp     dword ptr [rsp+14F0h+var_14D0+8], r15d
0x18003d609  jge     loc_18003D724
0x18003d60f  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x18003d616  jnz     short loc_18003D63D
0x18003d618  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18003d61f  test    rax, rax
0x18003d622  jz      short loc_18003D62D
0x18003d624  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d629  test    al, al
0x18003d62b  jmp     short loc_18003D63B
0x18003d62d  call    cs:__imp_IsDebuggerPresent
0x18003d634  nop     dword ptr [rax+rax+00h]
0x18003d639  test    eax, eax
0x18003d63b  jz      short loc_18003D644
0x18003d63d  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18003d642  jz      short loc_18003D66A
0x18003d644  mov     rax, cs:g_pfnResultLoggingCallback
0x18003d64b  test    rax, rax
0x18003d64e  jz      short loc_18003D6C9
0x18003d650  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18003d657  jnz     short loc_18003D6C9
0x18003d659  xor     r8d, r8d
0x18003d65c  xor     edx, edx
0x18003d65e  lea     rcx, [rsp+14F0h+var_14D0]
0x18003d663  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d668  jmp     short loc_18003D6C9
0x18003d66a  mov     rax, cs:g_pfnResultLoggingCallback
0x18003d671  test    rax, rax
0x18003d674  jz      short loc_18003D696
0x18003d676  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18003d67d  jnz     short loc_18003D696
0x18003d67f  mov     r8d, 800h
0x18003d685  lea     rdx, [rbp+13F0h+OutputString]
0x18003d68c  lea     rcx, [rsp+14F0h+var_14D0]
0x18003d691  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d696  cmp     [rbp+13F0h+OutputString], r15w
0x18003d69e  jnz     short loc_18003D6B6
0x18003d6a0  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x18003d6a5  mov     edx, 800h; unsigned __int16 *
0x18003d6aa  lea     rcx, [rbp+13F0h+OutputString]; this
0x18003d6b1  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18003d6b6  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x18003d6bd  call    cs:__imp_OutputDebugStringW
0x18003d6c4  nop     dword ptr [rax+rax+00h]
0x18003d6c9  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x18003d6ce  jnz     short loc_18003D6D9
0x18003d6d0  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x18003d6d7  jz      short loc_18003D6EB
0x18003d6d9  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18003d6e0  test    rax, rax
0x18003d6e3  jz      short loc_18003D6EB
0x18003d6e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d6ea  nop
0x18003d6eb  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x18003d6f0  jnz     short loc_18003D719
0x18003d6f2  mov     rcx, [rbp+13F0h+var_30]
0x18003d6f9  xor     rcx, rsp; StackCookie
0x18003d6fc  call    __security_check_cookie
0x18003d701  mov     rbx, [rsp+14F0h+arg_10]
0x18003d709  add     rsp, 14D0h
0x18003d710  pop     r15
0x18003d712  pop     r14
0x18003d714  pop     rdi
0x18003d715  pop     rsi
0x18003d716  pop     rbp
0x18003d717  retn
0x18003d719  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18003d71e  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18003d724  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
