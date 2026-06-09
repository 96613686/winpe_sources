# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,uint,char *,uint,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x1006edb4`
- end: `0x1006f045`
- name: `?LogFailure@details@wil@@YGXPAXIPBD110W4FailureType@2@ABUResultStatus@12@PBG_NPAGIPADIW4FailureFlags@2@PAUFailureInfo@2@@Z`
- size: `657`
- prototype: `void __userpurge(void *callerReturnAddress@<ecx>, unsigned int lineNumber@<edx>, const char *fileName, const char *functionName, const char *code, void *returnAddress, wil::FailureType type, const wil::details::ResultStatus *resultPair, const wchar_t *message, bool debugString, wchar_t *callContextString, unsigned int flags, char *failure, unsigned int callerReturnAddress@<ecx>, wil::FailureFlags lineNumber@<dl>, wil::FailureInfo *fileName)`
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x1006d1e7`
- `0x1006d239`
- `0x1006d2b6`

## callees

- `0x10067bc0`
- `0x1006d157`
- `0x1006e3af`
- `0x1006ea39`
- `0x1006edb4`
- `0x1006f89a`
- `0x1006f8c0`
- `0x1006fa00`
- `0x1006fa19`
- `0x10070d4b`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1006ee95`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1006ee95`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1006f007`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1006f007`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1006ef9a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1006ef9a`

## pseudocode

```c
void __userpurge wil::details::LogFailure(
        unsigned int a1@<edx>,
        void *a2@<ecx>,
        wil::details *this,
        const char *functionName,
        const char *code,
        char *returnAddress,
        const char *type,
        const wil::details::ResultStatus *resultPair,
        const wchar_t *message,
        enum wil::FailureType a10,
        wchar_t *debugString,
        const unsigned __int16 *a12,
        char *callContextString,
        unsigned __int16 *a14,
        unsigned int flags,
        wil::FailureInfo *failure,
        unsigned int a17,
        enum wil::FailureFlags a18,
        struct wil::FailureInfo *a19)
{
  HRESULT hr; // edi
  int v20; // eax
  int v21; // edi
  const wchar_t *v22; // eax
  int v23; // eax
  _array<NodeSet *> *v24; // edi
  bool v25; // zf
  wil::details::in1diag3 *v26; // [esp+0h] [ebp-18h]

  *debugString = 0;
  *callContextString = 0;
  hr = resultPair->hr;
  failure->hr = resultPair->hr;
  failure->status = resultPair->status;
  if ( !type )
  {
    v20 = wil::details::RecordException(hr);
    goto LABEL_10;
  }
  if ( type == (const char *)1 )
  {
    v20 = wil::details::RecordReturn(hr);
    goto LABEL_10;
  }
  if ( type == (const char *)2 )
  {
    if ( hr >= 0 )
    {
      hr = -2147024228;
      wil::details::ReportFailure_Hr<2>(
        (wil::details::ReportFailureOptions)a2,
        (wil::FailureFlags)a1,
        (const char *)this,
        functionName,
        code,
        returnAddress,
        -2147024228,
        a2);
      failure->hr = -2147024228;
      failure->status = wil::details::HrToNtStatus(-2147024228);
    }
    v20 = wil::details::RecordLog(hr);
    goto LABEL_10;
  }
  if ( type == (const char *)3 )
  {
    v20 = wil::details::RecordFailFast(hr);
LABEL_10:
    v21 = v20;
    goto LABEL_13;
  }
  v21 = 0;
LABEL_13:
  *(_DWORD *)failure->type = type;
  *(_DWORD *)failure->flags = flags;
  if ( resultPair->kind == NtStatus )
    *(_DWORD *)failure->flags = flags | 8;
  failure->failureId = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v22 = message;
  if ( !message || !*message )
    v22 = 0;
  failure->pszMessage = v22;
  failure->threadId = GetCurrentThreadId();
  failure->pszFile = (const char *)this;
  failure->uLineNumber = a1;
  failure->pszCode = code;
  failure->pszFunction = functionName;
  failure->returnAddress = returnAddress;
  failure->cFailureCount = v21;
  failure->callerReturnAddress = a2;
  failure->pszCallContext = 0;
  failure->callContextCurrent.contextId = 0;
  failure->callContextCurrent.contextName = 0;
  failure->callContextCurrent.contextMessage = 0;
  failure->callContextOriginating.contextId = 0;
  failure->callContextOriginating.contextName = 0;
  failure->callContextOriginating.contextMessage = 0;
  if ( wil::details::g_pfnGetModuleName )
    v23 = ((int (__thiscall *)(_array<NodeSet *> *))wil::details::g_pfnGetModuleName)(wil::details::g_pfnGetModuleName);
  else
    v23 = 0;
  v24 = wil::details::g_pfnNotifyFailure;
  failure->pszModule = (const char *)v23;
  if ( v24 )
    ((void (__thiscall *)(_array<NodeSet *> *, wil::FailureInfo *))v24)(v24, failure);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    ((void (__thiscall *)(_array<NodeSet *> *, wil::FailureInfo *, char *, int))wil::details::g_pfnGetContextAndNotifyFailure)(
      wil::details::g_pfnGetContextAndNotifyFailure,
      failure,
      callContextString,
      1024);
  if ( wil::details::g_pfnLoggingCallback )
    ((void (__thiscall *)(_array<NodeSet *> *, wil::FailureInfo *))wil::details::g_pfnLoggingCallback)(
      wil::details::g_pfnLoggingCallback,
      failure);
  if ( wil::details::g_pfnOriginateCallback && (failure->flags[0] & 2) == 0 )
    ((void (__thiscall *)(_array<NodeSet *> *, wil::FailureInfo *))wil::details::g_pfnOriginateCallback)(
      wil::details::g_pfnOriginateCallback,
      failure);
  if ( failure->hr >= 0 )
  {
    if ( type != (const char *)3 )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v26);
    failure->hr = -2147418113;
    failure->status = wil::details::HrToNtStatus(-2147418113);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v25 = !IsDebuggerPresent())
      : (v25 = (unsigned __int8)((int (__thiscall *)(_array<NodeSet *> *))wil::g_pfnIsDebuggerPresent)(wil::g_pfnIsDebuggerPresent) == 0),
        v25)
    || (failure->flags[0] & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      ((void (__thiscall *)(_array<NodeSet *> *, wil::FailureInfo *, _DWORD, _DWORD))g_pfnResultLoggingCallback)(
        g_pfnResultLoggingCallback,
        failure,
        0,
        0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      ((void (__thiscall *)(_array<NodeSet *> *, wil::FailureInfo *, wchar_t *, int))g_pfnResultLoggingCallback)(
        g_pfnResultLoggingCallback,
        failure,
        debugString,
        2048);
    if ( !*debugString )
      wil::GetFailureLogString(debugString, 0x800u, failure);
    OutputDebugStringW(debugString);
  }
  if ( (failure->flags[0] & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      ((void (__thiscall *)(_array<NodeSet *> *))wil::details::g_pfnDebugBreak)(wil::details::g_pfnDebugBreak);
  }
}

```

## disassembly

```asm
0x1006edb4  mov     edi, edi
0x1006edb6  push    ebp
0x1006edb7  mov     ebp, esp
0x1006edb9  and     esp, 0FFFFFFF8h
0x1006edbc  sub     esp, 0Ch
0x1006edbf  push    ebx
0x1006edc0  mov     ebx, [ebp+debugString]
0x1006edc3  xor     eax, eax
0x1006edc5  push    esi
0x1006edc6  mov     esi, [ebp+failure]
0x1006edc9  push    edi; this
0x1006edca  mov     [ebx], ax
0x1006edcd  mov     eax, [ebp+callContextString]
0x1006edd0  mov     [esp+18h+var_8], lineNumber
0x1006edd4  mov     [esp+18h+var_4], callerReturnAddress
0x1006edd8  mov     [esp+18h+var_C], 0
0x1006ede0  mov     byte ptr [eax], 0
0x1006ede3  mov     eax, [ebp+resultPair]
0x1006ede6  mov     edi, [eax]
0x1006ede8  mov     [esi+8], edi
0x1006edeb  mov     eax, [eax+4]
0x1006edee  mov     [esi+0Ch], eax
0x1006edf1  mov     eax, [ebp+type]
0x1006edf4  sub     eax, 0
0x1006edf7  jz      short loc_1006EE4D
0x1006edf9  sub     eax, 1
0x1006edfc  jz      short loc_1006EE42
0x1006edfe  sub     eax, 1
0x1006ee01  jz      short loc_1006EE10
0x1006ee03  sub     eax, 1
0x1006ee06  jnz     short loc_1006EE56
0x1006ee08  push    edi; hr
0x1006ee09  call    ?RecordFailFast@details@wil@@YGHJ@Z; wil::details::RecordFailFast(long)
0x1006ee0e  jmp     short loc_1006EE49
0x1006ee10  test    edi, edi
0x1006ee12  js      short loc_1006EE39
0x1006ee14  push    callerReturnAddress
0x1006ee15  mov     edi, 8007029Ch
0x1006ee1a  push    edi; hr
0x1006ee1b  push    [ebp+returnAddress]; returnAddress
0x1006ee1e  push    [ebp+code]; code
0x1006ee21  push    [ebp+functionName]; functionName
0x1006ee24  push    [ebp+fileName]; fileName
0x1006ee27  call    ??$ReportFailure_Hr@$01@details@wil@@YGXPAXIPBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1006ee2c  mov     callerReturnAddress, edi; hr
0x1006ee2e  mov     [esi+8], edi
0x1006ee31  call    ?HrToNtStatus@details@wil@@YGJJ@Z; wil::details::HrToNtStatus(long)
0x1006ee36  mov     [esi+0Ch], eax
0x1006ee39  mov     callerReturnAddress, edi; hr
0x1006ee3b  call    ?RecordLog@details@wil@@YGHJ@Z; wil::details::RecordLog(long)
0x1006ee40  jmp     short loc_1006EE49
0x1006ee42  mov     callerReturnAddress, edi; hr
0x1006ee44  call    ?RecordReturn@details@wil@@YGHJ@Z; wil::details::RecordReturn(long)
0x1006ee49  mov     edi, eax
0x1006ee4b  jmp     short loc_1006EE5A
0x1006ee4d  mov     callerReturnAddress, edi; hr
0x1006ee4f  call    ?RecordException@details@wil@@YGHJ@Z; wil::details::RecordException(long)
0x1006ee54  jmp     short loc_1006EE49
0x1006ee56  mov     edi, [esp+18h+var_C]
0x1006ee5a  mov     eax, [ebp+type]
0x1006ee5d  mov     lineNumber, [ebp+resultPair]
0x1006ee60  mov     callerReturnAddress, [ebp+flags]
0x1006ee63  mov     [esi], eax
0x1006ee65  xor     eax, eax
0x1006ee67  inc     eax
0x1006ee68  mov     [esi+4], callerReturnAddress
0x1006ee6b  cmp     [lineNumber+8], eax
0x1006ee6e  jnz     short loc_1006EE76
0x1006ee70  or      callerReturnAddress, 8
0x1006ee73  mov     [esi+4], callerReturnAddress
0x1006ee76  lock xadd ?s_failureId@?1??LogFailure@details@wil@@YGXPAXIPBD110W4FailureType@3@ABUResultStatus@23@PBG_NPAGIPADIW4FailureFlags@3@PAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,uint,char *,uint,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1006ee7e  inc     eax
0x1006ee7f  mov     [esi+10h], eax
0x1006ee82  mov     eax, [ebp+message]
0x1006ee85  test    eax, eax
0x1006ee87  jz      short loc_1006EE90
0x1006ee89  xor     callerReturnAddress, callerReturnAddress
0x1006ee8b  cmp     [eax], cx
0x1006ee8e  jnz     short loc_1006EE92
0x1006ee90  xor     eax, eax
0x1006ee92  mov     [esi+14h], eax
0x1006ee95  call    ds:__imp__GetCurrentThreadId@0; GetCurrentThreadId()
0x1006ee9b  mov     [esi+18h], eax
0x1006ee9e  xor     callerReturnAddress, callerReturnAddress
0x1006eea0  mov     eax, [ebp+fileName]
0x1006eea3  mov     [esi+24h], eax
0x1006eea6  mov     eax, [esp+18h+var_8]
0x1006eeaa  mov     [esi+28h], eax
0x1006eead  mov     eax, [ebp+code]
0x1006eeb0  mov     [esi+1Ch], eax
0x1006eeb3  mov     eax, [ebp+functionName]
0x1006eeb6  mov     [esi+20h], eax
0x1006eeb9  mov     eax, [ebp+returnAddress]
0x1006eebc  mov     [esi+50h], eax
0x1006eebf  mov     eax, [esp+18h+var_4]
0x1006eec3  mov     [esi+2Ch], edi
0x1006eec6  lea     edi, [esi+40h]
0x1006eec9  mov     [esi+54h], eax
0x1006eecc  xor     eax, eax
0x1006eece  mov     [esi+30h], callerReturnAddress
0x1006eed1  stosd
0x1006eed2  stosd
0x1006eed3  stosd
0x1006eed4  xor     eax, eax
0x1006eed6  lea     edi, [esi+34h]
0x1006eed9  stosd
0x1006eeda  stosd
0x1006eedb  stosd
0x1006eedc  mov     edi, ?g_pfnGetModuleName@details@wil@@3P6GPBDX_EA
0x1006eee2  test    edi, edi
0x1006eee4  jz      short loc_1006EEF2
0x1006eee6  mov     callerReturnAddress, edi; this
0x1006eee8  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1006eeee  call    edi ; ?g_pfnGetModuleName@details@wil@@3P6GPBDX_EA
0x1006eef0  jmp     short loc_1006EEF4
0x1006eef2  mov     eax, callerReturnAddress
0x1006eef4  mov     edi, ?g_pfnNotifyFailure@details@wil@@3P6GXPAUFailureInfo@2@@_EA
0x1006eefa  mov     [esi+4Ch], eax
0x1006eefd  test    edi, edi
0x1006eeff  jz      short loc_1006EF0C
0x1006ef01  push    esi
0x1006ef02  mov     callerReturnAddress, edi; this
0x1006ef04  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1006ef0a  call    edi ; ?g_pfnNotifyFailure@details@wil@@3P6GXPAUFailureInfo@2@@_EA
0x1006ef0c  mov     edi, ?g_pfnGetContextAndNotifyFailure@details@wil@@3P6GXPAUFailureInfo@2@PADI@_EA
0x1006ef12  test    edi, edi
0x1006ef14  jz      short loc_1006EF29
0x1006ef16  push    400h
0x1006ef1b  push    [ebp+callContextString]
0x1006ef1e  mov     callerReturnAddress, edi; this
0x1006ef20  push    esi
0x1006ef21  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1006ef27  call    edi ; ?g_pfnGetContextAndNotifyFailure@details@wil@@3P6GXPAUFailureInfo@2@PADI@_EA
0x1006ef29  mov     edi, ?g_pfnLoggingCallback@details@wil@@3P6GXABUFailureInfo@2@@_EA
0x1006ef2f  test    edi, edi
0x1006ef31  jz      short loc_1006EF3E
0x1006ef33  push    esi
0x1006ef34  mov     callerReturnAddress, edi; this
0x1006ef36  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1006ef3c  call    edi ; ?g_pfnLoggingCallback@details@wil@@3P6GXABUFailureInfo@2@@_EA
0x1006ef3e  mov     edi, ?g_pfnOriginateCallback@details@wil@@3P6GXABUFailureInfo@2@@_EA
0x1006ef44  test    edi, edi
0x1006ef46  jz      short loc_1006EF59
0x1006ef48  test    byte ptr [esi+4], 2
0x1006ef4c  jnz     short loc_1006EF59
0x1006ef4e  push    esi
0x1006ef4f  mov     callerReturnAddress, edi; this
0x1006ef51  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1006ef57  call    edi ; ?g_pfnOriginateCallback@details@wil@@3P6GXABUFailureInfo@2@@_EA
0x1006ef59  cmp     dword ptr [esi+8], 0
0x1006ef5d  jl      short loc_1006EF79
0x1006ef5f  cmp     [ebp+type], 3
0x1006ef63  jnz     loc_1006F039
0x1006ef69  mov     callerReturnAddress, 8000FFFFh; hr
0x1006ef6e  mov     [esi+8], callerReturnAddress
0x1006ef71  call    ?HrToNtStatus@details@wil@@YGJJ@Z; wil::details::HrToNtStatus(long)
0x1006ef76  mov     [esi+0Ch], eax
0x1006ef79  cmp     ?g_fIsDebuggerPresent@wil@@3_NA, 0; bool wil::g_fIsDebuggerPresent
0x1006ef80  jnz     short loc_1006EFA4
0x1006ef82  mov     edi, ?g_pfnIsDebuggerPresent@wil@@3P6G_NX_EA
0x1006ef88  test    edi, edi
0x1006ef8a  jz      short loc_1006EF9A
0x1006ef8c  mov     callerReturnAddress, edi; this
0x1006ef8e  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1006ef94  call    edi ; ?g_pfnIsDebuggerPresent@wil@@3P6G_NX_EA
0x1006ef96  test    al, al
0x1006ef98  jmp     short loc_1006EFA2
0x1006ef9a  call    ds:__imp__IsDebuggerPresent@0; IsDebuggerPresent()
0x1006efa0  test    eax, eax
0x1006efa2  jz      short loc_1006EFAA
0x1006efa4  test    byte ptr [esi+4], 2
0x1006efa8  jz      short loc_1006EFCE
0x1006efaa  mov     edi, _g_pfnResultLoggingCallback
0x1006efb0  test    edi, edi
0x1006efb2  jz      short loc_1006F00D
0x1006efb4  cmp     ?g_resultMessageCallbackSet@details@wil@@3_NA, 0; bool wil::details::g_resultMessageCallbackSet
0x1006efbb  jnz     short loc_1006F00D
0x1006efbd  xor     eax, eax
0x1006efbf  mov     callerReturnAddress, edi; this
0x1006efc1  push    eax
0x1006efc2  push    eax
0x1006efc3  push    esi
0x1006efc4  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1006efca  call    edi ; _g_pfnResultLoggingCallback
0x1006efcc  jmp     short loc_1006F00D
0x1006efce  mov     edi, _g_pfnResultLoggingCallback
0x1006efd4  test    edi, edi
0x1006efd6  jz      short loc_1006EFF2
0x1006efd8  cmp     ?g_resultMessageCallbackSet@details@wil@@3_NA, 0; bool wil::details::g_resultMessageCallbackSet
0x1006efdf  jnz     short loc_1006EFF2
0x1006efe1  push    800h
0x1006efe6  push    ebx
0x1006efe7  push    esi
0x1006efe8  mov     callerReturnAddress, edi; this
0x1006efea  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1006eff0  call    edi ; _g_pfnResultLoggingCallback
0x1006eff2  xor     eax, eax
0x1006eff4  cmp     [ebx], ax
0x1006eff7  jnz     short loc_1006F006
0x1006eff9  push    esi; failure
0x1006effa  mov     lineNumber, 800h; cchDest
0x1006efff  mov     callerReturnAddress, ebx; pszDest
0x1006f001  call    ?GetFailureLogString@wil@@YGJPAGIABUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,uint,wil::FailureInfo const &)
0x1006f006  push    ebx; lpOutputString
0x1006f007  call    ds:__imp__OutputDebugStringW@4; OutputDebugStringW(x)
0x1006f00d  test    byte ptr [esi+4], 4
0x1006f011  jnz     short loc_1006F01C
0x1006f013  cmp     ?g_fBreakOnFailure@wil@@3_NA, 0; bool wil::g_fBreakOnFailure
0x1006f01a  jz      short loc_1006F030
0x1006f01c  mov     esi, ?g_pfnDebugBreak@details@wil@@3P6GXX_EA
0x1006f022  test    esi, esi
0x1006f024  jz      short loc_1006F030
0x1006f026  mov     callerReturnAddress, esi; this
0x1006f028  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1006f02e  call    esi ; ?g_pfnDebugBreak@details@wil@@3P6GXX_EA
0x1006f030  pop     edi
0x1006f031  pop     esi
0x1006f032  pop     ebx
0x1006f033  mov     esp, ebp
0x1006f035  pop     ebp
0x1006f036  retn    38h ; '8'
0x1006f039  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YGXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
