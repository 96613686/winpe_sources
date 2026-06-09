# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180006844`
- end: `0x180006b3d`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: `void __fastcall(void *callerReturnAddress, unsigned int lineNumber, const char *fileName, const char *functionName, const char *code, void *returnAddress, wil::FailureType type, const wil::details::ResultStatus *resultPair, const wchar_t *message, bool debugString, wchar_t *callContextString, unsigned __int64 flags, char *failure, unsigned __int64 callerReturnAddress, wil::FailureFlags lineNumber, wil::FailureInfo *fileName)`
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x180004ec4`
- `0x180005230`
- `0x180023ea8`

## callees

- `0x180004dfc`
- `0x180005e84`
- `0x180006680`
- `0x180006844`
- `0x180006f88`
- `0x180006fb0`
- `0x180006fc4`
- `0x180006fe0`
- `0x180007ce8`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006967`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006967`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180006af8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180006af8`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180006a86`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180006a86`

## pseudocode

```c
void __fastcall wil::details::LogFailure(
        void *callerReturnAddress,
        unsigned int lineNumber,
        const char *fileName,
        const char *functionName,
        char *code,
        void *returnAddress,
        wil::FailureType type,
        const wil::details::ResultStatus *resultPair,
        const wchar_t *message,
        bool debugString,
        wchar_t *callContextString,
        unsigned __int64 flags,
        char *failure,
        unsigned __int64 callerReturnAddress_0,
        wil::FailureFlags lineNumber_0,
        wil::FailureInfo *fileName_0)
{
  int hr; // edi
  int v19; // ebp
  int v20; // eax
  const wchar_t *v21; // rax
  wil::details::in1diag3 *v22; // rcx
  const char *ModuleName; // rax
  bool v24; // zf
  wil::FailureFlags v25; // [rsp+38h] [rbp-40h]

  *callContextString = 0;
  *failure = 0;
  hr = resultPair->hr;
  fileName_0->hr = resultPair->hr;
  fileName_0->status = resultPair->status;
  v19 = 0;
  if ( type )
  {
    switch ( type )
    {
      case Return:
        v20 = wil::details::RecordReturn(hr);
        break;
      case Log:
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
            v25);
          fileName_0->hr = -2147024228;
          fileName_0->status = wil::details::HrToNtStatus(-2147024228);
        }
        v20 = wil::details::RecordLog(hr);
        break;
      case FailFast:
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
  v19 = v20;
LABEL_12:
  fileName_0->type = type;
  fileName_0->flags = lineNumber_0;
  if ( resultPair->kind == NtStatus )
    fileName_0->flags = lineNumber_0 | 8;
  fileName_0->failureId = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v21 = message;
  if ( !message || !*message )
    v21 = 0;
  fileName_0->pszMessage = v21;
  fileName_0->threadId = GetCurrentThreadId();
  fileName_0->pszFile = fileName;
  fileName_0->uLineNumber = lineNumber;
  fileName_0->cFailureCount = v19;
  fileName_0->pszCode = code;
  fileName_0->pszFunction = functionName;
  fileName_0->returnAddress = returnAddress;
  fileName_0->callerReturnAddress = callerReturnAddress;
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
  if ( wil::details::g_pfnOriginateCallback && (fileName_0->flags & 2) == 0 )
    wil::details::g_pfnOriginateCallback(fileName_0);
  if ( fileName_0->hr >= 0 )
  {
    if ( type != FailFast )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v22);
    fileName_0->hr = -2147418113;
    fileName_0->status = wil::details::HrToNtStatus(-2147418113);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent ? (v24 = !IsDebuggerPresent()) : (v24 = !wil::g_pfnIsDebuggerPresent()), v24)
    || (fileName_0->flags & 2) != 0 )
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
  if ( (fileName_0->flags & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak();
  }
}

```

## disassembly

```asm
0x180006844  mov     [rsp+arg_10], rbx
0x180006849  mov     [rsp+arg_8], lineNumber
0x18000684d  mov     [rsp+arg_0], callerReturnAddress
0x180006852  push    rbp
0x180006853  push    rsi
0x180006854  push    rdi
0x180006855  push    r12
0x180006857  push    r13
0x180006859  push    r14
0x18000685b  push    r15
0x18000685d  sub     rsp, 40h
0x180006861  mov     r12, functionName
0x180006864  mov     r13, fileName
0x180006867  mov     r10, callerReturnAddress
0x18000686a  xor     eax, eax
0x18000686c  mov     rsi, [rsp+78h+pszDest]
0x180006874  mov     [rsi], ax
0x180006877  mov     rax, [rsp+78h+arg_60]
0x18000687f  mov     byte ptr [rax], 0
0x180006882  mov     r14, [rsp+78h+arg_38]
0x18000688a  mov     edi, [r14]
0x18000688d  mov     rbx, [rsp+78h+fileName_0]
0x180006895  mov     [rbx+8], edi
0x180006898  mov     eax, [r14+4]
0x18000689c  mov     [rbx+0Ch], eax
0x18000689f  xor     ebp, ebp
0x1800068a1  mov     r15d, [rsp+78h+arg_30]
0x1800068a9  mov     ecx, r15d
0x1800068ac  test    r15d, r15d
0x1800068af  jz      short loc_180006917
0x1800068b1  sub     ecx, 1
0x1800068b4  jz      short loc_18000690E
0x1800068b6  sub     ecx, 1
0x1800068b9  jz      short loc_1800068C9
0x1800068bb  cmp     ecx, 1
0x1800068be  jnz     short loc_180006920
0x1800068c0  mov     ecx, edi; hr
0x1800068c2  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800068c7  jmp     short loc_18000691E
0x1800068c9  test    edi, edi
0x1800068cb  js      short loc_180006905
0x1800068cd  mov     edi, 8007029Ch
0x1800068d2  mov     [rsp+78h+hr], edi; hr
0x1800068d6  mov     rax, [rsp+78h+arg_28]
0x1800068de  mov     [rsp+78h+var_50], rax; returnAddress
0x1800068e3  mov     rax, [rsp+78h+arg_20]
0x1800068eb  mov     [rsp+78h+var_58], rax; code
0x1800068f0  mov     callerReturnAddress, r10; callerReturnAddress
0x1800068f3  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1800068f8  mov     [rbx+8], edi
0x1800068fb  mov     ecx, edi; hr
0x1800068fd  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180006902  mov     [rbx+0Ch], eax
0x180006905  mov     ecx, edi; hr
0x180006907  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18000690c  jmp     short loc_18000691E
0x18000690e  mov     ecx, edi; hr
0x180006910  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180006915  jmp     short loc_18000691E
0x180006917  mov     ecx, edi; hr
0x180006919  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000691e  mov     ebp, eax
0x180006920  mov     [rbx], r15d
0x180006923  mov     eax, [rsp+78h+lineNumber_0]
0x18000692a  mov     [rbx+4], eax
0x18000692d  cmp     dword ptr [r14+8], 1
0x180006932  jnz     short loc_18000693A
0x180006934  or      eax, 8
0x180006937  mov     [rbx+4], eax
0x18000693a  mov     eax, 1
0x18000693f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180006947  inc     eax
0x180006949  mov     [rbx+10h], eax
0x18000694c  mov     rax, [rsp+78h+arg_40]
0x180006954  xor     edi, edi
0x180006956  test    rax, rax
0x180006959  jz      short loc_180006960
0x18000695b  cmp     [rax], di
0x18000695e  jnz     short loc_180006963
0x180006960  mov     rax, rdi
0x180006963  mov     [rbx+18h], rax
0x180006967  call    cs:__imp_GetCurrentThreadId
0x18000696d  mov     [rbx+20h], eax
0x180006970  mov     [rbx+38h], r13
0x180006974  mov     eax, [rsp+78h+arg_8]
0x18000697b  mov     [rbx+40h], eax
0x18000697e  mov     [rbx+44h], ebp
0x180006981  mov     rax, [rsp+78h+arg_20]
0x180006989  mov     [rbx+28h], rax
0x18000698d  mov     [rbx+30h], r12
0x180006991  mov     rax, [rsp+78h+arg_28]
0x180006999  mov     [rbx+88h], rax
0x1800069a0  mov     rax, [rsp+78h+arg_0]
0x1800069a8  mov     [rbx+90h], rax
0x1800069af  mov     [rbx+48h], rdi
0x1800069b3  xorps   xmm0, xmm0
0x1800069b6  xor     eax, eax
0x1800069b8  movups  xmmword ptr [rbx+68h], xmm0
0x1800069bc  mov     [rbx+78h], rax
0x1800069c0  movups  xmmword ptr [rbx+50h], xmm0
0x1800069c4  mov     [rbx+60h], rax
0x1800069c8  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800069cf  test    rax, rax
0x1800069d2  jz      short loc_1800069DB
0x1800069d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800069d9  jmp     short loc_1800069DE
0x1800069db  mov     rax, rdi
0x1800069de  mov     [rbx+80h], rax
0x1800069e5  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800069ec  test    rax, rax
0x1800069ef  jz      short loc_1800069F9
0x1800069f1  mov     callerReturnAddress, rbx
0x1800069f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800069f9  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180006a00  test    rax, rax
0x180006a03  jz      short loc_180006A1B
0x180006a05  mov     r8d, 400h
0x180006a0b  mov     rdx, [rsp+78h+arg_60]
0x180006a13  mov     callerReturnAddress, rbx
0x180006a16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a1b  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180006a22  test    rax, rax
0x180006a25  jz      short loc_180006A2F
0x180006a27  mov     callerReturnAddress, rbx
0x180006a2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a2f  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180006a36  test    rax, rax
0x180006a39  jz      short loc_180006A49
0x180006a3b  test    byte ptr [rbx+4], 2
0x180006a3f  jnz     short loc_180006A49
0x180006a41  mov     callerReturnAddress, rbx
0x180006a44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a49  cmp     [rbx+8], edi
0x180006a4c  jl      short loc_180006A68
0x180006a4e  cmp     r15d, 3
0x180006a52  jnz     loc_180006B37
0x180006a58  mov     ecx, 8000FFFFh; hr
0x180006a5d  mov     [rbx+8], ecx
0x180006a60  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180006a65  mov     [rbx+0Ch], eax
0x180006a68  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180006a6f  jnz     short loc_180006A90
0x180006a71  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180006a78  test    rax, rax
0x180006a7b  jz      short loc_180006A86
0x180006a7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a82  test    al, al
0x180006a84  jmp     short loc_180006A8E
0x180006a86  call    cs:__imp_IsDebuggerPresent
0x180006a8c  test    eax, eax
0x180006a8e  jz      short loc_180006A96
0x180006a90  test    byte ptr [rbx+4], 2
0x180006a94  jz      short loc_180006ABA
0x180006a96  mov     rax, cs:g_pfnResultLoggingCallback
0x180006a9d  test    rax, rax
0x180006aa0  jz      short loc_180006AFE
0x180006aa2  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180006aa9  jnz     short loc_180006AFE
0x180006aab  xor     r8d, r8d
0x180006aae  xor     lineNumber, lineNumber
0x180006ab0  mov     callerReturnAddress, rbx
0x180006ab3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ab8  jmp     short loc_180006AFE
0x180006aba  mov     ebp, 800h
0x180006abf  mov     rax, cs:g_pfnResultLoggingCallback
0x180006ac6  test    rax, rax
0x180006ac9  jz      short loc_180006AE2
0x180006acb  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180006ad2  jnz     short loc_180006AE2
0x180006ad4  mov     r8d, ebp
0x180006ad7  mov     rdx, rsi
0x180006ada  mov     callerReturnAddress, rbx
0x180006add  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ae2  cmp     [rsi], di
0x180006ae5  jnz     short loc_180006AF5
0x180006ae7  mov     fileName, rbx; failure
0x180006aea  mov     rdx, rbp; cchDest
0x180006aed  mov     callerReturnAddress, rsi; pszDest
0x180006af0  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180006af5  mov     callerReturnAddress, rsi; lpOutputString
0x180006af8  call    cs:__imp_OutputDebugStringW
0x180006afe  test    byte ptr [rbx+4], 4
0x180006b02  jnz     short loc_180006B0D
0x180006b04  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180006b0b  jz      short loc_180006B1F
0x180006b0d  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180006b14  test    rax, rax
0x180006b17  jz      short loc_180006B1F
0x180006b19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b1e  nop
0x180006b1f  mov     rbx, [rsp+78h+arg_10]
0x180006b27  add     rsp, 40h
0x180006b2b  pop     r15
0x180006b2d  pop     r14
0x180006b2f  pop     r13
0x180006b31  pop     r12
0x180006b33  pop     rdi
0x180006b34  pop     rsi
0x180006b35  pop     rbp
0x180006b36  retn
0x180006b37  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
