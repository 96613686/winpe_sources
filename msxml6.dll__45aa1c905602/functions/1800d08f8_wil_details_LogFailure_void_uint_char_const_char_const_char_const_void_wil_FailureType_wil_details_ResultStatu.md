# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x1800d08f8`
- end: `0x1800d0c03`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `779`
- prototype: `void __fastcall(void *callerReturnAddress, unsigned int lineNumber, const char *fileName, const char *functionName, const char *code, void *returnAddress, wil::FailureType type, const wil::details::ResultStatus *resultPair, const wchar_t *message, bool debugString, wchar_t *callContextString, unsigned __int64 flags, char *failure, unsigned __int64 callerReturnAddress, wil::FailureFlags lineNumber, wil::FailureInfo *fileName)`
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x1800ceb3c`
- `0x1800cee9c`

## callees

- `0x1800cb798`
- `0x1800cea7c`
- `0x1800cff14`
- `0x1800d08f8`
- `0x1800d15a0`
- `0x1800d15c0`
- `0x1800d1684`
- `0x1800d16a4`
- `0x1800d293c`
- `0x18018c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800d0a1b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800d0a1b`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800d0b40`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800d0b40`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800d0bb8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800d0bb8`

## pseudocode

```c
void __fastcall wil::details::LogFailure(
        void *callerReturnAddress,
        unsigned int lineNumber,
        const char *fileName,
        const char *functionName,
        char *code,
        void *returnAddress,
        int type,
        const wil::details::ResultStatus *resultPair,
        const wchar_t *message,
        bool debugString,
        wchar_t *callContextString,
        unsigned __int64 flags,
        char *failure,
        unsigned __int64 callerReturnAddress_0,
        int lineNumber_0,
        wil::FailureInfo *fileName_0)
{
  int v16; // ebp
  int hr; // edi
  int v20; // eax
  const wchar_t *v21; // rax
  DWORD CurrentThreadId; // eax
  wil::details::in1diag3 *v23; // rcx
  const char *ModuleName; // rax
  bool v25; // zf
  wil::FailureFlags v26; // [rsp+38h] [rbp-40h]

  v16 = 0;
  *callContextString = 0;
  *failure = 0;
  hr = resultPair->hr;
  fileName_0->hr = resultPair->hr;
  fileName_0->status = resultPair->status;
  if ( type )
  {
    switch ( type )
    {
      case 1:
        v20 = wil::details::RecordReturn(hr);
        break;
      case 2:
        if ( hr >= 0 )
        {
          hr = -2147024228;
          wil::details::ReportFailure_Hr<2>(
            callerReturnAddress,
            lineNumber,
            fileName,
            functionName,
            code,
            returnAddress,
            -2147024228,
            v26);
          fileName_0->hr = -2147024228;
          fileName_0->status = wil::details::HrToNtStatus(-2147024228);
        }
        v20 = wil::details::RecordLog(hr);
        break;
      case 3:
        v20 = wil::details::RecordFailFast(hr);
        break;
      default:
        goto LABEL_12;
    }
  }
  else
  {
    v20 = wil::details::RecordException(hr);
  }
  v16 = v20;
LABEL_12:
  *(_DWORD *)fileName_0->flags = lineNumber_0;
  *(_DWORD *)fileName_0->type = type;
  if ( resultPair->kind == NtStatus )
    *(_DWORD *)fileName_0->flags = lineNumber_0 | 8;
  fileName_0->failureId = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v21 = message;
  if ( !message || !*message )
    v21 = 0;
  fileName_0->pszMessage = v21;
  CurrentThreadId = GetCurrentThreadId();
  fileName_0->pszFile = fileName;
  fileName_0->threadId = CurrentThreadId;
  fileName_0->uLineNumber = lineNumber;
  fileName_0->pszCode = code;
  fileName_0->returnAddress = returnAddress;
  fileName_0->callerReturnAddress = callerReturnAddress;
  fileName_0->cFailureCount = v16;
  fileName_0->pszFunction = functionName;
  fileName_0->pszCallContext = 0;
  *(_OWORD *)&fileName_0->callContextCurrent.contextId = 0;
  fileName_0->callContextCurrent.contextMessage = 0;
  *(_OWORD *)&fileName_0->callContextOriginating.contextId = 0;
  fileName_0->callContextOriginating.contextMessage = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName();
  else
    ModuleName = 0;
  fileName_0->pszModule = ModuleName;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(fileName_0);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(fileName_0, failure, 0x400u);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(fileName_0);
  if ( wil::details::g_pfnOriginateCallback && (fileName_0->flags[0] & 2) == 0 )
    wil::details::g_pfnOriginateCallback(fileName_0);
  if ( fileName_0->hr >= 0 )
  {
    if ( type != 3 )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v23);
    fileName_0->hr = -2147418113;
    fileName_0->status = wil::details::HrToNtStatus(-2147418113);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent ? (v25 = !IsDebuggerPresent()) : (v25 = !wil::g_pfnIsDebuggerPresent()), v25)
    || (fileName_0->flags[0] & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(fileName_0, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(fileName_0, callContextString, 0x800u);
    if ( !*callContextString )
      wil::GetFailureLogString(callContextString, 0x800u, fileName_0);
    OutputDebugStringW(callContextString);
  }
  if ( (fileName_0->flags[0] & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak();
  }
}

```

## disassembly

```asm
0x1800d08f8  mov     [rsp+arg_10], rbx
0x1800d08fd  mov     [rsp+arg_8], lineNumber
0x1800d0901  mov     [rsp+arg_0], callerReturnAddress
0x1800d0906  push    rbp
0x1800d0907  push    rsi
0x1800d0908  push    rdi
0x1800d0909  push    r12
0x1800d090b  push    r13
0x1800d090d  push    r14
0x1800d090f  push    r15
0x1800d0911  sub     rsp, 40h
0x1800d0915  mov     r14, [rsp+78h+arg_38]
0x1800d091d  xor     eax, eax
0x1800d091f  mov     rbx, [rsp+78h+fileName_0]
0x1800d0927  xor     ebp, ebp
0x1800d0929  mov     r15d, [rsp+78h+arg_30]
0x1800d0931  mov     r10, callerReturnAddress
0x1800d0934  mov     rsi, [rsp+78h+pszDest]
0x1800d093c  mov     r12, functionName
0x1800d093f  mov     r13, fileName
0x1800d0942  mov     ecx, r15d
0x1800d0945  mov     [rsi], ax
0x1800d0948  mov     rax, [rsp+78h+arg_60]
0x1800d0950  mov     byte ptr [rax], 0
0x1800d0953  mov     edi, [r14]
0x1800d0956  mov     [rbx+8], edi
0x1800d0959  mov     eax, [r14+4]
0x1800d095d  mov     [rbx+0Ch], eax
0x1800d0960  test    r15d, r15d
0x1800d0963  jz      short loc_1800D09CB
0x1800d0965  sub     ecx, 1
0x1800d0968  jz      short loc_1800D09C2
0x1800d096a  sub     ecx, 1
0x1800d096d  jz      short loc_1800D097D
0x1800d096f  cmp     ecx, 1
0x1800d0972  jnz     short loc_1800D09D4
0x1800d0974  mov     ecx, edi; hr
0x1800d0976  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800d097b  jmp     short loc_1800D09D2
0x1800d097d  test    edi, edi
0x1800d097f  js      short loc_1800D09B9
0x1800d0981  mov     rax, [rsp+78h+arg_28]
0x1800d0989  mov     edi, 8007029Ch
0x1800d098e  mov     [rsp+78h+hr], edi; hr
0x1800d0992  mov     callerReturnAddress, r10; callerReturnAddress
0x1800d0995  mov     [rsp+78h+var_50], rax; returnAddress
0x1800d099a  mov     rax, [rsp+78h+arg_20]
0x1800d09a2  mov     [rsp+78h+var_58], rax; code
0x1800d09a7  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1800d09ac  mov     ecx, edi; hr
0x1800d09ae  mov     [rbx+8], edi
0x1800d09b1  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800d09b6  mov     [rbx+0Ch], eax
0x1800d09b9  mov     ecx, edi; hr
0x1800d09bb  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x1800d09c0  jmp     short loc_1800D09D2
0x1800d09c2  mov     ecx, edi; hr
0x1800d09c4  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800d09c9  jmp     short loc_1800D09D2
0x1800d09cb  mov     ecx, edi; hr
0x1800d09cd  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1800d09d2  mov     ebp, eax
0x1800d09d4  mov     eax, [rsp+78h+lineNumber_0]
0x1800d09db  mov     [rbx+4], eax
0x1800d09de  mov     [rbx], r15d
0x1800d09e1  cmp     dword ptr [r14+8], 1
0x1800d09e6  jnz     short loc_1800D09EE
0x1800d09e8  or      eax, 8
0x1800d09eb  mov     [rbx+4], eax
0x1800d09ee  mov     eax, 1
0x1800d09f3  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800d09fb  inc     eax
0x1800d09fd  xor     edi, edi
0x1800d09ff  mov     [rbx+10h], eax
0x1800d0a02  mov     rax, [rsp+78h+arg_40]
0x1800d0a0a  test    rax, rax
0x1800d0a0d  jz      short loc_1800D0A14
0x1800d0a0f  cmp     [rax], di
0x1800d0a12  jnz     short loc_1800D0A17
0x1800d0a14  mov     rax, rdi
0x1800d0a17  mov     [rbx+18h], rax
0x1800d0a1b  call    cs:__imp_GetCurrentThreadId
0x1800d0a22  nop     dword ptr [rax+rax+00h]
0x1800d0a27  mov     [rbx+38h], r13
0x1800d0a2b  xorps   xmm0, xmm0
0x1800d0a2e  mov     [rbx+20h], eax
0x1800d0a31  mov     eax, [rsp+78h+arg_8]
0x1800d0a38  mov     [rbx+40h], eax
0x1800d0a3b  mov     rax, [rsp+78h+arg_20]
0x1800d0a43  mov     [rbx+28h], rax
0x1800d0a47  mov     rax, [rsp+78h+arg_28]
0x1800d0a4f  mov     [rbx+88h], rax
0x1800d0a56  mov     rax, [rsp+78h+arg_0]
0x1800d0a5e  mov     [rbx+90h], rax
0x1800d0a65  xor     eax, eax
0x1800d0a67  mov     [rbx+44h], ebp
0x1800d0a6a  mov     [rbx+30h], r12
0x1800d0a6e  mov     [rbx+48h], rdi
0x1800d0a72  movups  xmmword ptr [rbx+68h], xmm0
0x1800d0a76  mov     [rbx+78h], rax
0x1800d0a7a  movups  xmmword ptr [rbx+50h], xmm0
0x1800d0a7e  mov     [rbx+60h], rax
0x1800d0a82  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800d0a89  test    rax, rax
0x1800d0a8c  jz      short loc_1800D0A95
0x1800d0a8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d0a93  jmp     short loc_1800D0A98
0x1800d0a95  mov     rax, rdi
0x1800d0a98  mov     [rbx+80h], rax
0x1800d0a9f  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800d0aa6  test    rax, rax
0x1800d0aa9  jz      short loc_1800D0AB3
0x1800d0aab  mov     callerReturnAddress, rbx
0x1800d0aae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d0ab3  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800d0aba  test    rax, rax
0x1800d0abd  jz      short loc_1800D0AD5
0x1800d0abf  mov     rdx, [rsp+78h+arg_60]
0x1800d0ac7  mov     r8d, 400h
0x1800d0acd  mov     callerReturnAddress, rbx
0x1800d0ad0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d0ad5  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800d0adc  test    rax, rax
0x1800d0adf  jz      short loc_1800D0AE9
0x1800d0ae1  mov     callerReturnAddress, rbx
0x1800d0ae4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d0ae9  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800d0af0  test    rax, rax
0x1800d0af3  jz      short loc_1800D0B03
0x1800d0af5  test    byte ptr [rbx+4], 2
0x1800d0af9  jnz     short loc_1800D0B03
0x1800d0afb  mov     callerReturnAddress, rbx
0x1800d0afe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d0b03  cmp     [rbx+8], edi
0x1800d0b06  jl      short loc_1800D0B22
0x1800d0b08  cmp     r15d, 3
0x1800d0b0c  jnz     loc_1800D0BFD
0x1800d0b12  mov     ecx, 8000FFFFh; hr
0x1800d0b17  mov     [rbx+8], ecx
0x1800d0b1a  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800d0b1f  mov     [rbx+0Ch], eax
0x1800d0b22  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x1800d0b29  jnz     short loc_1800D0B50
0x1800d0b2b  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800d0b32  test    rax, rax
0x1800d0b35  jz      short loc_1800D0B40
0x1800d0b37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d0b3c  test    al, al
0x1800d0b3e  jmp     short loc_1800D0B4E
0x1800d0b40  call    cs:__imp_IsDebuggerPresent
0x1800d0b47  nop     dword ptr [rax+rax+00h]
0x1800d0b4c  test    eax, eax
0x1800d0b4e  jz      short loc_1800D0B56
0x1800d0b50  test    byte ptr [rbx+4], 2
0x1800d0b54  jz      short loc_1800D0B7A
0x1800d0b56  mov     rax, cs:g_pfnResultLoggingCallback
0x1800d0b5d  test    rax, rax
0x1800d0b60  jz      short loc_1800D0BC4
0x1800d0b62  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800d0b69  jnz     short loc_1800D0BC4
0x1800d0b6b  xor     r8d, r8d
0x1800d0b6e  xor     lineNumber, lineNumber
0x1800d0b70  mov     callerReturnAddress, rbx
0x1800d0b73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d0b78  jmp     short loc_1800D0BC4
0x1800d0b7a  mov     rax, cs:g_pfnResultLoggingCallback
0x1800d0b81  mov     ebp, 800h
0x1800d0b86  test    rax, rax
0x1800d0b89  jz      short loc_1800D0BA2
0x1800d0b8b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800d0b92  jnz     short loc_1800D0BA2
0x1800d0b94  mov     r8d, ebp
0x1800d0b97  mov     rdx, rsi
0x1800d0b9a  mov     callerReturnAddress, rbx
0x1800d0b9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d0ba2  cmp     [rsi], di
0x1800d0ba5  jnz     short loc_1800D0BB5
0x1800d0ba7  mov     fileName, rbx; failure
0x1800d0baa  mov     rdx, rbp; cchDest
0x1800d0bad  mov     callerReturnAddress, rsi; pszDest
0x1800d0bb0  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800d0bb5  mov     callerReturnAddress, rsi; lpOutputString
0x1800d0bb8  call    cs:__imp_OutputDebugStringW
0x1800d0bbf  nop     dword ptr [rax+rax+00h]
0x1800d0bc4  test    byte ptr [rbx+4], 4
0x1800d0bc8  jnz     short loc_1800D0BD3
0x1800d0bca  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x1800d0bd1  jz      short loc_1800D0BE4
0x1800d0bd3  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800d0bda  test    rax, rax
0x1800d0bdd  jz      short loc_1800D0BE4
0x1800d0bdf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d0be4  mov     rbx, [rsp+78h+arg_10]
0x1800d0bec  add     rsp, 40h
0x1800d0bf0  pop     r15
0x1800d0bf2  pop     r14
0x1800d0bf4  pop     r13
0x1800d0bf6  pop     r12
0x1800d0bf8  pop     rdi
0x1800d0bf9  pop     rsi
0x1800d0bfa  pop     rbp
0x1800d0bfb  retn
0x1800d0bfd  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
