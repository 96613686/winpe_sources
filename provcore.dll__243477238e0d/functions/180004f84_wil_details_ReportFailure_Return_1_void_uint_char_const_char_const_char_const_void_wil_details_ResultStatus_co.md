# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180004f84`
- end: `0x18000522a`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `678`
- prototype: `void __fastcall(void *callerReturnAddress, unsigned int lineNumber, const char *fileName, const char *returnAddress, const char *resultPair, void *message, const wil::details::ResultStatus *callerReturnAddress_0, const wchar_t *lineNumber_0)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180004c08`

## callees

- `0x180002790`
- `0x1800032dc`
- `0x180004f84`
- `0x180005e84`
- `0x180006fe0`
- `0x180007bb8`
- `0x180007ce8`
- `0x180067e00`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000504a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000504a`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800051c9`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800051c9`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000513f`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000513f`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall wil::details::ReportFailure_Return<1>(
        void *callerReturnAddress,
        unsigned int lineNumber,
        const char *fileName,
        const char *returnAddress,
        const char *resultPair,
        void *message,
        const wil::details::ResultStatus *callerReturnAddress_0,
        const wchar_t *lineNumber_0)
{
  int v11; // r15d
  wil::FailureFlags v12; // ecx
  __int64 v13; // rdx
  wil::details::in1diag3 *v14; // rcx
  bool v15; // zf
  wil::FailureInfo failure; // [rsp+20h] [rbp-E0h] BYREF
  char callContextString[1024]; // [rsp+C0h] [rbp-40h] BYREF
  wchar_t debugString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&failure, 0, sizeof(failure));
  debugString[0] = 0;
  callContextString[0] = 0;
  failure.hr = callerReturnAddress_0->hr;
  failure.status = callerReturnAddress_0->status;
  v11 = wil::details::RecordReturn(failure.hr);
  failure.type = Return;
  v12 = None;
  if ( *(_DWORD *)(v13 + 8) == 1 )
    v12 = SuppressSetErrorInfo;
  failure.flags = v12;
  failure.failureId = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  if ( !lineNumber_0 || (v15 = *lineNumber_0 == 0, failure.pszMessage = lineNumber_0, v15) )
    failure.pszMessage = 0;
  failure.threadId = GetCurrentThreadId();
  failure.pszFile = fileName;
  failure.uLineNumber = lineNumber;
  failure.cFailureCount = v11;
  failure.pszCode = 0;
  failure.pszFunction = 0;
  failure.returnAddress = message;
  failure.callerReturnAddress = callerReturnAddress;
  memset(&failure.pszCallContext, 0, 56);
  if ( wil::details::g_pfnGetModuleName )
    failure.pszModule = wil::details::g_pfnGetModuleName();
  else
    failure.pszModule = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&failure);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&failure, callContextString, 0x400u);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&failure);
  if ( wil::details::g_pfnOriginateCallback && (failure.flags & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&failure);
  if ( failure.hr >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v14);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent ? (v15 = !IsDebuggerPresent()) : (v15 = !wil::g_pfnIsDebuggerPresent()), v15)
    || (failure.flags & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&failure, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&failure, debugString, 0x800u);
    if ( !debugString[0] )
      wil::GetFailureLogString(debugString, 0x800u, &failure);
    OutputDebugStringW(debugString);
  }
  if ( ((failure.flags & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak();
  if ( (failure.flags & 1) != 0 )
    wil::details::WilFailFast(&failure);
}

```

## disassembly

```asm
0x180004f84  push    rbp
0x180004f86  push    rbx
0x180004f87  push    rsi
0x180004f88  push    rdi
0x180004f89  push    r12
0x180004f8b  push    r14
0x180004f8d  push    r15
0x180004f8f  lea     rbp, [rsp-13D0h]
0x180004f97  mov     eax, 14D0h
0x180004f9c  call    _alloca_probe
0x180004fa1  sub     rsp, rax
0x180004fa4  mov     rax, cs:__security_cookie
0x180004fab  xor     rax, rsp
0x180004fae  mov     [rbp+1400h+var_40], rax
0x180004fb5  mov     rsi, fileName
0x180004fb8  mov     edi, lineNumber
0x180004fba  mov     rbx, callerReturnAddress
0x180004fbd  mov     r14, [rbp+1400h+arg_28]
0x180004fc4  xor     lineNumber, lineNumber; Val
0x180004fc6  mov     r8d, 98h; Size
0x180004fcc  lea     callerReturnAddress, [rsp+1500h+failure]; void *
0x180004fd1  call    memset_0
0x180004fd6  nop
0x180004fd7  xor     r12d, r12d
0x180004fda  mov     [rbp+1400h+debugString], r12w
0x180004fe2  mov     [rbp+1400h+callContextString], r12b
0x180004fe6  mov     rdx, [rbp+1400h+callerReturnAddress_0]
0x180004fed  mov     ecx, [rdx]; hr
0x180004fef  mov     [rsp+1500h+failure.hr], ecx
0x180004ff3  mov     eax, [rdx+4]
0x180004ff6  mov     [rsp+1500h+failure.status], eax
0x180004ffa  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180004fff  mov     r15d, eax
0x180005002  mov     [rsp+1500h+failure.type], 1
0x18000500a  mov     ecx, r12d
0x18000500d  lea     eax, [r12+8]
0x180005012  cmp     dword ptr [rdx+8], 1
0x180005016  cmovz   ecx, eax
0x180005019  mov     [rsp+1500h+failure.flags], ecx
0x18000501d  lea     ecx, [rax-7]
0x180005020  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180005028  inc     ecx
0x18000502a  mov     [rsp+1500h+failure.failureId], ecx
0x18000502e  mov     callerReturnAddress, [rbp+1400h+lineNumber_0]
0x180005035  test    callerReturnAddress, callerReturnAddress
0x180005038  jz      short loc_180005045
0x18000503a  cmp     [callerReturnAddress], r12w
0x18000503e  mov     [rsp+1500h+failure.pszMessage], callerReturnAddress
0x180005043  jnz     short loc_18000504A
0x180005045  mov     [rsp+1500h+failure.pszMessage], r12
0x18000504a  call    cs:__imp_GetCurrentThreadId
0x180005050  mov     [rsp+1500h+failure.threadId], eax
0x180005054  mov     [rsp+1500h+failure.pszFile], rsi
0x180005059  mov     [rsp+1500h+failure.uLineNumber], edi
0x18000505d  mov     [rsp+1500h+failure.cFailureCount], r15d
0x180005062  mov     [rsp+1500h+failure.pszCode], r12
0x180005067  mov     [rsp+1500h+failure.pszFunction], r12
0x18000506c  mov     [rbp+1400h+failure.returnAddress], r14
0x180005070  mov     [rbp+1400h+failure.callerReturnAddress], rbx
0x180005074  mov     [rsp+1500h+failure.pszCallContext], r12
0x180005079  xorps   xmm0, xmm0
0x18000507c  xor     eax, eax
0x18000507e  movups  xmmword ptr [rbp+1400h+failure.callContextCurrent.contextId], xmm0
0x180005082  mov     [rbp+1400h+failure.callContextCurrent.contextMessage], rax
0x180005086  xorps   xmm1, xmm1
0x180005089  movups  xmmword ptr [rsp+1500h+failure.callContextOriginating.contextId], xmm1
0x18000508e  mov     [rbp+1400h+failure.callContextOriginating.contextMessage], rax
0x180005092  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180005099  test    rax, rax
0x18000509c  jz      short loc_1800050A9
0x18000509e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800050a3  mov     [rbp+1400h+failure.pszModule], rax
0x1800050a7  jmp     short loc_1800050AD
0x1800050a9  mov     [rbp+1400h+failure.pszModule], r12
0x1800050ad  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800050b4  test    rax, rax
0x1800050b7  jz      short loc_1800050C3
0x1800050b9  lea     callerReturnAddress, [rsp+1500h+failure]
0x1800050be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800050c3  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800050ca  test    rax, rax
0x1800050cd  jz      short loc_1800050E3
0x1800050cf  mov     r8d, 400h
0x1800050d5  lea     rdx, [rbp+1400h+callContextString]
0x1800050d9  lea     callerReturnAddress, [rsp+1500h+failure]
0x1800050de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800050e3  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800050ea  test    rax, rax
0x1800050ed  jz      short loc_1800050F9
0x1800050ef  lea     callerReturnAddress, [rsp+1500h+failure]
0x1800050f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800050f9  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005100  test    rax, rax
0x180005103  jz      short loc_180005116
0x180005105  test    byte ptr [rsp+1500h+failure.flags], 2
0x18000510a  jnz     short loc_180005116
0x18000510c  lea     callerReturnAddress, [rsp+1500h+failure]
0x180005111  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005116  cmp     [rsp+1500h+failure.hr], r12d
0x18000511b  jge     loc_180005224
0x180005121  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180005128  jnz     short loc_180005149
0x18000512a  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180005131  test    rax, rax
0x180005134  jz      short loc_18000513F
0x180005136  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000513b  test    al, al
0x18000513d  jmp     short loc_180005147
0x18000513f  call    cs:__imp_IsDebuggerPresent
0x180005145  test    eax, eax
0x180005147  jz      short loc_180005150
0x180005149  test    byte ptr [rsp+1500h+failure.flags], 2
0x18000514e  jz      short loc_180005176
0x180005150  mov     rax, cs:g_pfnResultLoggingCallback
0x180005157  test    rax, rax
0x18000515a  jz      short loc_1800051CF
0x18000515c  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180005163  jnz     short loc_1800051CF
0x180005165  xor     r8d, r8d
0x180005168  xor     lineNumber, lineNumber
0x18000516a  lea     callerReturnAddress, [rsp+1500h+failure]
0x18000516f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005174  jmp     short loc_1800051CF
0x180005176  mov     ebx, 800h
0x18000517b  mov     rax, cs:g_pfnResultLoggingCallback
0x180005182  test    rax, rax
0x180005185  jz      short loc_1800051A4
0x180005187  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18000518e  jnz     short loc_1800051A4
0x180005190  mov     r8d, ebx
0x180005193  lea     rdx, [rbp+1400h+debugString]
0x18000519a  lea     callerReturnAddress, [rsp+1500h+failure]
0x18000519f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800051a4  cmp     [rbp+1400h+debugString], r12w
0x1800051ac  jnz     short loc_1800051C2
0x1800051ae  lea     fileName, [rsp+1500h+failure]; failure
0x1800051b3  mov     rdx, rbx; cchDest
0x1800051b6  lea     callerReturnAddress, [rbp+1400h+debugString]; pszDest
0x1800051bd  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800051c2  lea     callerReturnAddress, [rbp+1400h+debugString]; lpOutputString
0x1800051c9  call    cs:__imp_OutputDebugStringW
0x1800051cf  test    byte ptr [rsp+1500h+failure.flags], 4
0x1800051d4  jnz     short loc_1800051DF
0x1800051d6  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x1800051dd  jz      short loc_1800051F1
0x1800051df  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800051e6  test    rax, rax
0x1800051e9  jz      short loc_1800051F1
0x1800051eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800051f0  nop
0x1800051f1  test    byte ptr [rsp+1500h+failure.flags], 1
0x1800051f6  jnz     short loc_180005219
0x1800051f8  mov     callerReturnAddress, [rbp+1400h+var_40]
0x1800051ff  xor     callerReturnAddress, rsp; StackCookie
0x180005202  call    __security_check_cookie
0x180005207  add     rsp, 14D0h
0x18000520e  pop     r15
0x180005210  pop     r14
0x180005212  pop     r12
0x180005214  pop     rdi
0x180005215  pop     rsi
0x180005216  pop     rbx
0x180005217  pop     rbp
0x180005218  retn
0x180005219  lea     callerReturnAddress, [rsp+1500h+failure]; failure
0x18000521e  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180005224  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
