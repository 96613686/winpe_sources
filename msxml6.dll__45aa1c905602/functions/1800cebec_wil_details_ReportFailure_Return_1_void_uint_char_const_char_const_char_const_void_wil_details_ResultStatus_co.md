# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x1800cebec`
- end: `0x1800cee93`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `679`
- prototype: `void __fastcall(void *callerReturnAddress, unsigned int lineNumber, const char *returnAddress, const char *resultPair, const char *callerReturnAddress, void *lineNumber, const wil::details::ResultStatus *fileName, const wchar_t *functionName, wil::details::ReportFailureOptions code, wil::FailureFlags returnAddress)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800cb78c`

## callees

- `0x1800cc6c0`
- `0x1800cd3e4`
- `0x1800cebec`
- `0x1800cff14`
- `0x1800d16a4`
- `0x1800d2780`
- `0x1800d293c`
- `0x18017c160`
- `0x18018c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800cec96`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800cec96`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800ced97`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800ced97`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800cee27`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800cee27`

## pseudocode

```c
void __fastcall wil::details::ReportFailure_Return<1>(
        void *callerReturnAddress,
        unsigned int lineNumber,
        const char *returnAddress,
        const char *resultPair,
        const char *callerReturnAddress_0,
        void *lineNumber_0,
        const wil::details::ResultStatus *fileName)
{
  int status; // eax
  int v10; // eax
  __int64 v11; // rdx
  int v12; // ebx
  int v13; // ecx
  DWORD CurrentThreadId; // eax
  wil::details::in1diag3 *v15; // rcx
  bool v16; // zf
  wil::FailureInfo failure; // [rsp+20h] [rbp-E0h] BYREF
  char v18[1024]; // [rsp+C0h] [rbp-40h] BYREF
  wchar_t pszDest[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&failure, 0, sizeof(failure));
  pszDest[0] = 0;
  v18[0] = 0;
  status = fileName->status;
  failure.hr = fileName->hr;
  failure.status = status;
  v10 = wil::details::RecordReturn(failure.hr);
  v16 = *(_DWORD *)(v11 + 8) == 1;
  v12 = v10;
  *(_DWORD *)failure.type = 1;
  v13 = 0;
  if ( v16 )
    v13 = 8;
  *(_DWORD *)failure.flags = v13;
  failure.pszMessage = 0;
  failure.failureId = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  CurrentThreadId = GetCurrentThreadId();
  failure.uLineNumber = lineNumber;
  failure.threadId = CurrentThreadId;
  failure.cFailureCount = v12;
  failure.pszFile = "wil";
  failure.pszCode = 0;
  failure.pszFunction = 0;
  failure.returnAddress = lineNumber_0;
  failure.callerReturnAddress = callerReturnAddress;
  memset(&failure.pszCallContext, 0, 56);
  if ( wil::details::g_pfnGetModuleName )
    failure.pszModule = wil::details::g_pfnGetModuleName();
  else
    failure.pszModule = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&failure);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&failure, v18, 0x400u);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&failure);
  if ( wil::details::g_pfnOriginateCallback && (failure.flags[0] & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&failure);
  if ( failure.hr >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v15);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent ? (v16 = !IsDebuggerPresent()) : (v16 = !wil::g_pfnIsDebuggerPresent()), v16)
    || (failure.flags[0] & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&failure, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&failure, pszDest, 0x800u);
    if ( !pszDest[0] )
      wil::GetFailureLogString(pszDest, 0x800u, &failure);
    OutputDebugStringW(pszDest);
  }
  if ( ((failure.flags[0] & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak();
  if ( (failure.flags[0] & 1) != 0 )
    wil::details::WilFailFast(&failure);
}

```

## disassembly

```asm
0x1800cebec  mov     [rsp-8+arg_10], rbx
0x1800cebf1  push    rbp
0x1800cebf2  push    rsi
0x1800cebf3  push    rdi
0x1800cebf4  push    r14
0x1800cebf6  push    r15
0x1800cebf8  lea     rbp, [rsp-13D0h]
0x1800cec00  mov     eax, 14D0h
0x1800cec05  call    _alloca_probe
0x1800cec0a  sub     rsp, rax
0x1800cec0d  mov     rax, cs:__security_cookie
0x1800cec14  xor     rax, rsp
0x1800cec17  mov     [rbp+13F0h+var_30], rax
0x1800cec1e  mov     rdi, [rbp+13F0h+lineNumber_0]
0x1800cec25  mov     esi, lineNumber
0x1800cec27  mov     r14, callerReturnAddress
0x1800cec2a  xor     lineNumber, lineNumber; Val
0x1800cec2c  lea     callerReturnAddress, [rsp+14F0h+failure]; void *
0x1800cec31  mov     r8d, 98h; Size
0x1800cec37  call    memset_0
0x1800cec3c  mov     rdx, [rbp+13F0h+fileName]
0x1800cec43  xor     r15d, r15d
0x1800cec46  mov     [rbp+13F0h+pszDest], r15w
0x1800cec4e  mov     [rbp+13F0h+var_1430], r15b
0x1800cec52  mov     ecx, [rdx]; hr
0x1800cec54  mov     eax, [rdx+4]
0x1800cec57  mov     [rsp+14F0h+failure.hr], ecx
0x1800cec5b  mov     [rsp+14F0h+failure.status], eax
0x1800cec5f  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800cec64  cmp     dword ptr [rdx+8], 1
0x1800cec68  mov     ebx, eax
0x1800cec6a  lea     eax, [r15+8]
0x1800cec6e  mov     dword ptr [rsp+14F0h+failure.type], 1
0x1800cec76  mov     ecx, r15d
0x1800cec79  cmovz   ecx, eax
0x1800cec7c  mov     dword ptr [rsp+14F0h+failure.flags], ecx
0x1800cec80  lea     ecx, [rax-7]
0x1800cec83  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800cec8b  inc     ecx
0x1800cec8d  mov     [rsp+14F0h+failure.pszMessage], r15
0x1800cec92  mov     [rsp+14F0h+failure.failureId], ecx
0x1800cec96  call    cs:__imp_GetCurrentThreadId
0x1800cec9d  nop     dword ptr [rax+rax+00h]
0x1800ceca2  xorps   xmm0, xmm0
0x1800ceca5  mov     [rsp+14F0h+failure.uLineNumber], esi
0x1800ceca9  mov     [rsp+14F0h+failure.threadId], eax
0x1800cecad  xorps   xmm1, xmm1
0x1800cecb0  lea     rax, fileName; "wil"
0x1800cecb7  mov     [rsp+14F0h+failure.cFailureCount], ebx
0x1800cecbb  mov     [rsp+14F0h+failure.pszFile], rax
0x1800cecc0  xor     eax, eax
0x1800cecc2  mov     [rbp+13F0h+failure.callContextCurrent.contextMessage], rax
0x1800cecc6  mov     [rbp+13F0h+failure.callContextOriginating.contextMessage], rax
0x1800cecca  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800cecd1  mov     [rsp+14F0h+failure.pszCode], r15
0x1800cecd6  mov     [rsp+14F0h+failure.pszFunction], r15
0x1800cecdb  mov     [rbp+13F0h+failure.returnAddress], rdi
0x1800cecdf  mov     [rbp+13F0h+failure.callerReturnAddress], r14
0x1800cece3  mov     [rsp+14F0h+failure.pszCallContext], r15
0x1800cece8  movups  xmmword ptr [rbp+13F0h+failure.callContextCurrent.contextId], xmm0
0x1800cecec  movups  xmmword ptr [rsp+14F0h+failure.callContextOriginating.contextId], xmm1
0x1800cecf1  test    rax, rax
0x1800cecf4  jz      short loc_1800CED01
0x1800cecf6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cecfb  mov     [rbp+13F0h+failure.pszModule], rax
0x1800cecff  jmp     short loc_1800CED05
0x1800ced01  mov     [rbp+13F0h+failure.pszModule], r15
0x1800ced05  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800ced0c  test    rax, rax
0x1800ced0f  jz      short loc_1800CED1B
0x1800ced11  lea     callerReturnAddress, [rsp+14F0h+failure]
0x1800ced16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ced1b  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800ced22  test    rax, rax
0x1800ced25  jz      short loc_1800CED3B
0x1800ced27  mov     r8d, 400h
0x1800ced2d  lea     rdx, [rbp+13F0h+var_1430]
0x1800ced31  lea     callerReturnAddress, [rsp+14F0h+failure]
0x1800ced36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ced3b  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800ced42  test    rax, rax
0x1800ced45  jz      short loc_1800CED51
0x1800ced47  lea     callerReturnAddress, [rsp+14F0h+failure]
0x1800ced4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ced51  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800ced58  test    rax, rax
0x1800ced5b  jz      short loc_1800CED6E
0x1800ced5d  test    [rsp+14F0h+failure.flags], 2
0x1800ced62  jnz     short loc_1800CED6E
0x1800ced64  lea     callerReturnAddress, [rsp+14F0h+failure]
0x1800ced69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ced6e  cmp     [rsp+14F0h+failure.hr], r15d
0x1800ced73  jge     loc_1800CEE82
0x1800ced79  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x1800ced80  jnz     short loc_1800CEDA7
0x1800ced82  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800ced89  test    rax, rax
0x1800ced8c  jz      short loc_1800CED97
0x1800ced8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ced93  test    al, al
0x1800ced95  jmp     short loc_1800CEDA5
0x1800ced97  call    cs:__imp_IsDebuggerPresent
0x1800ced9e  nop     dword ptr [rax+rax+00h]
0x1800ceda3  test    eax, eax
0x1800ceda5  jz      short loc_1800CEDAE
0x1800ceda7  test    [rsp+14F0h+failure.flags], 2
0x1800cedac  jz      short loc_1800CEDD4
0x1800cedae  mov     rax, cs:g_pfnResultLoggingCallback
0x1800cedb5  test    rax, rax
0x1800cedb8  jz      short loc_1800CEE33
0x1800cedba  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800cedc1  jnz     short loc_1800CEE33
0x1800cedc3  xor     r8d, r8d
0x1800cedc6  lea     callerReturnAddress, [rsp+14F0h+failure]
0x1800cedcb  xor     lineNumber, lineNumber
0x1800cedcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cedd2  jmp     short loc_1800CEE33
0x1800cedd4  mov     rax, cs:g_pfnResultLoggingCallback
0x1800ceddb  mov     ebx, 800h
0x1800cede0  test    rax, rax
0x1800cede3  jz      short loc_1800CEE02
0x1800cede5  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800cedec  jnz     short loc_1800CEE02
0x1800cedee  mov     r8d, ebx
0x1800cedf1  lea     rdx, [rbp+13F0h+pszDest]
0x1800cedf8  lea     callerReturnAddress, [rsp+14F0h+failure]
0x1800cedfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cee02  cmp     [rbp+13F0h+pszDest], r15w
0x1800cee0a  jnz     short loc_1800CEE20
0x1800cee0c  lea     r8, [rsp+14F0h+failure]; failure
0x1800cee11  mov     rdx, rbx; cchDest
0x1800cee14  lea     callerReturnAddress, [rbp+13F0h+pszDest]; pszDest
0x1800cee1b  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800cee20  lea     callerReturnAddress, [rbp+13F0h+pszDest]; lpOutputString
0x1800cee27  call    cs:__imp_OutputDebugStringW
0x1800cee2e  nop     dword ptr [rax+rax+00h]
0x1800cee33  test    [rsp+14F0h+failure.flags], 4
0x1800cee38  jnz     short loc_1800CEE43
0x1800cee3a  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x1800cee41  jz      short loc_1800CEE54
0x1800cee43  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800cee4a  test    rax, rax
0x1800cee4d  jz      short loc_1800CEE54
0x1800cee4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cee54  test    [rsp+14F0h+failure.flags], 1
0x1800cee59  jnz     short loc_1800CEE88
0x1800cee5b  mov     callerReturnAddress, [rbp+13F0h+var_30]
0x1800cee62  xor     callerReturnAddress, rsp; StackCookie
0x1800cee65  call    __security_check_cookie
0x1800cee6a  mov     rbx, [rsp+14F0h+arg_10]
0x1800cee72  add     rsp, 14D0h
0x1800cee79  pop     r15
0x1800cee7b  pop     r14
0x1800cee7d  pop     rdi
0x1800cee7e  pop     rsi
0x1800cee7f  pop     rbp
0x1800cee80  retn
0x1800cee82  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800cee88  lea     callerReturnAddress, [rsp+14F0h+failure]; failure
0x1800cee8d  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
