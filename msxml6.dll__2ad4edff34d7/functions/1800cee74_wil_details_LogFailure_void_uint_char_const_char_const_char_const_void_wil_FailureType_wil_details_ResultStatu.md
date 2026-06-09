# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x1800cee74`
- end: `0x1800cf16c`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `760`
- prototype: `void __fastcall(void *callerReturnAddress, unsigned int lineNumber, const char *fileName, const char *functionName, const char *code, void *returnAddress, wil::FailureType type, const wil::details::ResultStatus *resultPair, const wchar_t *message, bool debugString, wchar_t *callContextString, unsigned __int64 flags, char *failure, unsigned __int64 callerReturnAddress, wil::FailureFlags lineNumber, wil::FailureInfo *fileName)`
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x1800cd1b8`
- `0x1800cd504`

## callees

- `0x1800c9e90`
- `0x1800cd0f8`
- `0x1800ce4f4`
- `0x1800cee74`
- `0x1800cfad8`
- `0x1800cfb00`
- `0x1800cfbbc`
- `0x1800cfbd8`
- `0x1800d0d70`
- `0x180188010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800cef97`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800cef97`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800cf0b6`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800cf0b6`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800cf128`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800cf128`

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
0x1800cee74  mov     [rsp+arg_10], rbx
0x1800cee79  mov     [rsp+arg_8], lineNumber
0x1800cee7d  mov     [rsp+arg_0], callerReturnAddress
0x1800cee82  push    rbp
0x1800cee83  push    rsi
0x1800cee84  push    rdi
0x1800cee85  push    r12
0x1800cee87  push    r13
0x1800cee89  push    r14
0x1800cee8b  push    r15
0x1800cee8d  sub     rsp, 40h
0x1800cee91  mov     r14, [rsp+78h+arg_38]
0x1800cee99  xor     eax, eax
0x1800cee9b  mov     rbx, [rsp+78h+fileName_0]
0x1800ceea3  xor     ebp, ebp
0x1800ceea5  mov     r15d, [rsp+78h+arg_30]
0x1800ceead  mov     r10, callerReturnAddress
0x1800ceeb0  mov     rsi, [rsp+78h+pszDest]
0x1800ceeb8  mov     r12, functionName
0x1800ceebb  mov     r13, fileName
0x1800ceebe  mov     ecx, r15d
0x1800ceec1  mov     [rsi], ax
0x1800ceec4  mov     rax, [rsp+78h+arg_60]
0x1800ceecc  mov     byte ptr [rax], 0
0x1800ceecf  mov     edi, [r14]
0x1800ceed2  mov     [rbx+8], edi
0x1800ceed5  mov     eax, [r14+4]
0x1800ceed9  mov     [rbx+0Ch], eax
0x1800ceedc  test    r15d, r15d
0x1800ceedf  jz      short loc_1800CEF47
0x1800ceee1  sub     ecx, 1
0x1800ceee4  jz      short loc_1800CEF3E
0x1800ceee6  sub     ecx, 1
0x1800ceee9  jz      short loc_1800CEEF9
0x1800ceeeb  cmp     ecx, 1
0x1800ceeee  jnz     short loc_1800CEF50
0x1800ceef0  mov     ecx, edi; hr
0x1800ceef2  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800ceef7  jmp     short loc_1800CEF4E
0x1800ceef9  test    edi, edi
0x1800ceefb  js      short loc_1800CEF35
0x1800ceefd  mov     rax, [rsp+78h+arg_28]
0x1800cef05  mov     edi, 8007029Ch
0x1800cef0a  mov     [rsp+78h+hr], edi; hr
0x1800cef0e  mov     callerReturnAddress, r10; callerReturnAddress
0x1800cef11  mov     [rsp+78h+var_50], rax; returnAddress
0x1800cef16  mov     rax, [rsp+78h+arg_20]
0x1800cef1e  mov     [rsp+78h+var_58], rax; code
0x1800cef23  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1800cef28  mov     ecx, edi; hr
0x1800cef2a  mov     [rbx+8], edi
0x1800cef2d  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800cef32  mov     [rbx+0Ch], eax
0x1800cef35  mov     ecx, edi; hr
0x1800cef37  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x1800cef3c  jmp     short loc_1800CEF4E
0x1800cef3e  mov     ecx, edi; hr
0x1800cef40  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800cef45  jmp     short loc_1800CEF4E
0x1800cef47  mov     ecx, edi; hr
0x1800cef49  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1800cef4e  mov     ebp, eax
0x1800cef50  mov     eax, [rsp+78h+lineNumber_0]
0x1800cef57  mov     [rbx+4], eax
0x1800cef5a  mov     [rbx], r15d
0x1800cef5d  cmp     dword ptr [r14+8], 1
0x1800cef62  jnz     short loc_1800CEF6A
0x1800cef64  or      eax, 8
0x1800cef67  mov     [rbx+4], eax
0x1800cef6a  mov     eax, 1
0x1800cef6f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800cef77  inc     eax
0x1800cef79  xor     edi, edi
0x1800cef7b  mov     [rbx+10h], eax
0x1800cef7e  mov     rax, [rsp+78h+arg_40]
0x1800cef86  test    rax, rax
0x1800cef89  jz      short loc_1800CEF90
0x1800cef8b  cmp     [rax], di
0x1800cef8e  jnz     short loc_1800CEF93
0x1800cef90  mov     rax, rdi
0x1800cef93  mov     [rbx+18h], rax
0x1800cef97  call    cs:__imp_GetCurrentThreadId
0x1800cef9d  mov     [rbx+38h], r13
0x1800cefa1  xorps   xmm0, xmm0
0x1800cefa4  mov     [rbx+20h], eax
0x1800cefa7  mov     eax, [rsp+78h+arg_8]
0x1800cefae  mov     [rbx+40h], eax
0x1800cefb1  mov     rax, [rsp+78h+arg_20]
0x1800cefb9  mov     [rbx+28h], rax
0x1800cefbd  mov     rax, [rsp+78h+arg_28]
0x1800cefc5  mov     [rbx+88h], rax
0x1800cefcc  mov     rax, [rsp+78h+arg_0]
0x1800cefd4  mov     [rbx+90h], rax
0x1800cefdb  xor     eax, eax
0x1800cefdd  mov     [rbx+44h], ebp
0x1800cefe0  mov     [rbx+30h], r12
0x1800cefe4  mov     [rbx+48h], rdi
0x1800cefe8  movups  xmmword ptr [rbx+68h], xmm0
0x1800cefec  mov     [rbx+78h], rax
0x1800ceff0  movups  xmmword ptr [rbx+50h], xmm0
0x1800ceff4  mov     [rbx+60h], rax
0x1800ceff8  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800cefff  test    rax, rax
0x1800cf002  jz      short loc_1800CF00B
0x1800cf004  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cf009  jmp     short loc_1800CF00E
0x1800cf00b  mov     rax, rdi
0x1800cf00e  mov     [rbx+80h], rax
0x1800cf015  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800cf01c  test    rax, rax
0x1800cf01f  jz      short loc_1800CF029
0x1800cf021  mov     callerReturnAddress, rbx
0x1800cf024  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cf029  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800cf030  test    rax, rax
0x1800cf033  jz      short loc_1800CF04B
0x1800cf035  mov     rdx, [rsp+78h+arg_60]
0x1800cf03d  mov     r8d, 400h
0x1800cf043  mov     callerReturnAddress, rbx
0x1800cf046  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cf04b  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800cf052  test    rax, rax
0x1800cf055  jz      short loc_1800CF05F
0x1800cf057  mov     callerReturnAddress, rbx
0x1800cf05a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cf05f  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800cf066  test    rax, rax
0x1800cf069  jz      short loc_1800CF079
0x1800cf06b  test    byte ptr [rbx+4], 2
0x1800cf06f  jnz     short loc_1800CF079
0x1800cf071  mov     callerReturnAddress, rbx
0x1800cf074  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cf079  cmp     [rbx+8], edi
0x1800cf07c  jl      short loc_1800CF098
0x1800cf07e  cmp     r15d, 3
0x1800cf082  jnz     loc_1800CF166
0x1800cf088  mov     ecx, 8000FFFFh; hr
0x1800cf08d  mov     [rbx+8], ecx
0x1800cf090  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800cf095  mov     [rbx+0Ch], eax
0x1800cf098  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x1800cf09f  jnz     short loc_1800CF0C0
0x1800cf0a1  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800cf0a8  test    rax, rax
0x1800cf0ab  jz      short loc_1800CF0B6
0x1800cf0ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cf0b2  test    al, al
0x1800cf0b4  jmp     short loc_1800CF0BE
0x1800cf0b6  call    cs:__imp_IsDebuggerPresent
0x1800cf0bc  test    eax, eax
0x1800cf0be  jz      short loc_1800CF0C6
0x1800cf0c0  test    byte ptr [rbx+4], 2
0x1800cf0c4  jz      short loc_1800CF0EA
0x1800cf0c6  mov     rax, cs:g_pfnResultLoggingCallback
0x1800cf0cd  test    rax, rax
0x1800cf0d0  jz      short loc_1800CF12E
0x1800cf0d2  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800cf0d9  jnz     short loc_1800CF12E
0x1800cf0db  xor     r8d, r8d
0x1800cf0de  xor     lineNumber, lineNumber
0x1800cf0e0  mov     callerReturnAddress, rbx
0x1800cf0e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cf0e8  jmp     short loc_1800CF12E
0x1800cf0ea  mov     rax, cs:g_pfnResultLoggingCallback
0x1800cf0f1  mov     ebp, 800h
0x1800cf0f6  test    rax, rax
0x1800cf0f9  jz      short loc_1800CF112
0x1800cf0fb  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800cf102  jnz     short loc_1800CF112
0x1800cf104  mov     r8d, ebp
0x1800cf107  mov     rdx, rsi
0x1800cf10a  mov     callerReturnAddress, rbx
0x1800cf10d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cf112  cmp     [rsi], di
0x1800cf115  jnz     short loc_1800CF125
0x1800cf117  mov     fileName, rbx; failure
0x1800cf11a  mov     rdx, rbp; cchDest
0x1800cf11d  mov     callerReturnAddress, rsi; pszDest
0x1800cf120  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800cf125  mov     callerReturnAddress, rsi; lpOutputString
0x1800cf128  call    cs:__imp_OutputDebugStringW
0x1800cf12e  test    byte ptr [rbx+4], 4
0x1800cf132  jnz     short loc_1800CF13D
0x1800cf134  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x1800cf13b  jz      short loc_1800CF14E
0x1800cf13d  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800cf144  test    rax, rax
0x1800cf147  jz      short loc_1800CF14E
0x1800cf149  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cf14e  mov     rbx, [rsp+78h+arg_10]
0x1800cf156  add     rsp, 40h
0x1800cf15a  pop     r15
0x1800cf15c  pop     r14
0x1800cf15e  pop     r13
0x1800cf160  pop     r12
0x1800cf162  pop     rdi
0x1800cf163  pop     rsi
0x1800cf164  pop     rbp
0x1800cf165  retn
0x1800cf166  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
