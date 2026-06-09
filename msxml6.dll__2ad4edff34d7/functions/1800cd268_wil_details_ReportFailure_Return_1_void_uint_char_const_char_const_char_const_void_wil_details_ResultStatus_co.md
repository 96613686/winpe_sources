# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x1800cd268`
- end: `0x1800cd4fc`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `660`
- prototype: `void __fastcall(void *callerReturnAddress, unsigned int lineNumber, const char *returnAddress, const char *resultPair, const char *callerReturnAddress, void *lineNumber, const wil::details::ResultStatus *fileName, const wchar_t *functionName, wil::details::ReportFailureOptions code, wil::FailureFlags returnAddress)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800c9e84`

## callees

- `0x1800cada0`
- `0x1800cba94`
- `0x1800cd268`
- `0x1800ce4f4`
- `0x1800cfbd8`
- `0x1800d0bb8`
- `0x1800d0d70`
- `0x1801784b0`
- `0x180188010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800cd312`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800cd312`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800cd40d`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800cd40d`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800cd497`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800cd497`

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
0x1800cd268  mov     [rsp-8+arg_10], rbx
0x1800cd26d  push    rbp
0x1800cd26e  push    rsi
0x1800cd26f  push    rdi
0x1800cd270  push    r14
0x1800cd272  push    r15
0x1800cd274  lea     rbp, [rsp-13D0h]
0x1800cd27c  mov     eax, 14D0h
0x1800cd281  call    _alloca_probe
0x1800cd286  sub     rsp, rax
0x1800cd289  mov     rax, cs:__security_cookie
0x1800cd290  xor     rax, rsp
0x1800cd293  mov     [rbp+13F0h+var_30], rax
0x1800cd29a  mov     rdi, [rbp+13F0h+lineNumber_0]
0x1800cd2a1  mov     esi, lineNumber
0x1800cd2a3  mov     r14, callerReturnAddress
0x1800cd2a6  xor     lineNumber, lineNumber; Val
0x1800cd2a8  lea     callerReturnAddress, [rsp+14F0h+failure]; void *
0x1800cd2ad  mov     r8d, 98h; Size
0x1800cd2b3  call    memset_0
0x1800cd2b8  mov     rdx, [rbp+13F0h+fileName]
0x1800cd2bf  xor     r15d, r15d
0x1800cd2c2  mov     [rbp+13F0h+pszDest], r15w
0x1800cd2ca  mov     [rbp+13F0h+var_1430], r15b
0x1800cd2ce  mov     ecx, [rdx]; hr
0x1800cd2d0  mov     eax, [rdx+4]
0x1800cd2d3  mov     [rsp+14F0h+failure.hr], ecx
0x1800cd2d7  mov     [rsp+14F0h+failure.status], eax
0x1800cd2db  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800cd2e0  cmp     dword ptr [rdx+8], 1
0x1800cd2e4  mov     ebx, eax
0x1800cd2e6  lea     eax, [r15+8]
0x1800cd2ea  mov     dword ptr [rsp+14F0h+failure.type], 1
0x1800cd2f2  mov     ecx, r15d
0x1800cd2f5  cmovz   ecx, eax
0x1800cd2f8  mov     dword ptr [rsp+14F0h+failure.flags], ecx
0x1800cd2fc  lea     ecx, [rax-7]
0x1800cd2ff  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800cd307  inc     ecx
0x1800cd309  mov     [rsp+14F0h+failure.pszMessage], r15
0x1800cd30e  mov     [rsp+14F0h+failure.failureId], ecx
0x1800cd312  call    cs:__imp_GetCurrentThreadId
0x1800cd318  xorps   xmm0, xmm0
0x1800cd31b  mov     [rsp+14F0h+failure.uLineNumber], esi
0x1800cd31f  mov     [rsp+14F0h+failure.threadId], eax
0x1800cd323  xorps   xmm1, xmm1
0x1800cd326  lea     rax, fileName; "wil"
0x1800cd32d  mov     [rsp+14F0h+failure.cFailureCount], ebx
0x1800cd331  mov     [rsp+14F0h+failure.pszFile], rax
0x1800cd336  xor     eax, eax
0x1800cd338  mov     [rbp+13F0h+failure.callContextCurrent.contextMessage], rax
0x1800cd33c  mov     [rbp+13F0h+failure.callContextOriginating.contextMessage], rax
0x1800cd340  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800cd347  mov     [rsp+14F0h+failure.pszCode], r15
0x1800cd34c  mov     [rsp+14F0h+failure.pszFunction], r15
0x1800cd351  mov     [rbp+13F0h+failure.returnAddress], rdi
0x1800cd355  mov     [rbp+13F0h+failure.callerReturnAddress], r14
0x1800cd359  mov     [rsp+14F0h+failure.pszCallContext], r15
0x1800cd35e  movups  xmmword ptr [rbp+13F0h+failure.callContextCurrent.contextId], xmm0
0x1800cd362  movups  xmmword ptr [rsp+14F0h+failure.callContextOriginating.contextId], xmm1
0x1800cd367  test    rax, rax
0x1800cd36a  jz      short loc_1800CD377
0x1800cd36c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cd371  mov     [rbp+13F0h+failure.pszModule], rax
0x1800cd375  jmp     short loc_1800CD37B
0x1800cd377  mov     [rbp+13F0h+failure.pszModule], r15
0x1800cd37b  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800cd382  test    rax, rax
0x1800cd385  jz      short loc_1800CD391
0x1800cd387  lea     callerReturnAddress, [rsp+14F0h+failure]
0x1800cd38c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cd391  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800cd398  test    rax, rax
0x1800cd39b  jz      short loc_1800CD3B1
0x1800cd39d  mov     r8d, 400h
0x1800cd3a3  lea     rdx, [rbp+13F0h+var_1430]
0x1800cd3a7  lea     callerReturnAddress, [rsp+14F0h+failure]
0x1800cd3ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cd3b1  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800cd3b8  test    rax, rax
0x1800cd3bb  jz      short loc_1800CD3C7
0x1800cd3bd  lea     callerReturnAddress, [rsp+14F0h+failure]
0x1800cd3c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cd3c7  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800cd3ce  test    rax, rax
0x1800cd3d1  jz      short loc_1800CD3E4
0x1800cd3d3  test    [rsp+14F0h+failure.flags], 2
0x1800cd3d8  jnz     short loc_1800CD3E4
0x1800cd3da  lea     callerReturnAddress, [rsp+14F0h+failure]
0x1800cd3df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cd3e4  cmp     [rsp+14F0h+failure.hr], r15d
0x1800cd3e9  jge     loc_1800CD4EB
0x1800cd3ef  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x1800cd3f6  jnz     short loc_1800CD417
0x1800cd3f8  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800cd3ff  test    rax, rax
0x1800cd402  jz      short loc_1800CD40D
0x1800cd404  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cd409  test    al, al
0x1800cd40b  jmp     short loc_1800CD415
0x1800cd40d  call    cs:__imp_IsDebuggerPresent
0x1800cd413  test    eax, eax
0x1800cd415  jz      short loc_1800CD41E
0x1800cd417  test    [rsp+14F0h+failure.flags], 2
0x1800cd41c  jz      short loc_1800CD444
0x1800cd41e  mov     rax, cs:g_pfnResultLoggingCallback
0x1800cd425  test    rax, rax
0x1800cd428  jz      short loc_1800CD49D
0x1800cd42a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800cd431  jnz     short loc_1800CD49D
0x1800cd433  xor     r8d, r8d
0x1800cd436  lea     callerReturnAddress, [rsp+14F0h+failure]
0x1800cd43b  xor     lineNumber, lineNumber
0x1800cd43d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cd442  jmp     short loc_1800CD49D
0x1800cd444  mov     rax, cs:g_pfnResultLoggingCallback
0x1800cd44b  mov     ebx, 800h
0x1800cd450  test    rax, rax
0x1800cd453  jz      short loc_1800CD472
0x1800cd455  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800cd45c  jnz     short loc_1800CD472
0x1800cd45e  mov     r8d, ebx
0x1800cd461  lea     rdx, [rbp+13F0h+pszDest]
0x1800cd468  lea     callerReturnAddress, [rsp+14F0h+failure]
0x1800cd46d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cd472  cmp     [rbp+13F0h+pszDest], r15w
0x1800cd47a  jnz     short loc_1800CD490
0x1800cd47c  lea     r8, [rsp+14F0h+failure]; failure
0x1800cd481  mov     rdx, rbx; cchDest
0x1800cd484  lea     callerReturnAddress, [rbp+13F0h+pszDest]; pszDest
0x1800cd48b  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800cd490  lea     callerReturnAddress, [rbp+13F0h+pszDest]; lpOutputString
0x1800cd497  call    cs:__imp_OutputDebugStringW
0x1800cd49d  test    [rsp+14F0h+failure.flags], 4
0x1800cd4a2  jnz     short loc_1800CD4AD
0x1800cd4a4  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x1800cd4ab  jz      short loc_1800CD4BE
0x1800cd4ad  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800cd4b4  test    rax, rax
0x1800cd4b7  jz      short loc_1800CD4BE
0x1800cd4b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cd4be  test    [rsp+14F0h+failure.flags], 1
0x1800cd4c3  jnz     short loc_1800CD4F1
0x1800cd4c5  mov     callerReturnAddress, [rbp+13F0h+var_30]
0x1800cd4cc  xor     callerReturnAddress, rsp; StackCookie
0x1800cd4cf  call    __security_check_cookie
0x1800cd4d4  mov     rbx, [rsp+14F0h+arg_10]
0x1800cd4dc  add     rsp, 14D0h
0x1800cd4e3  pop     r15
0x1800cd4e5  pop     r14
0x1800cd4e7  pop     rdi
0x1800cd4e8  pop     rsi
0x1800cd4e9  pop     rbp
0x1800cd4ea  retn
0x1800cd4eb  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800cd4f1  lea     callerReturnAddress, [rsp+14F0h+failure]; failure
0x1800cd4f6  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
