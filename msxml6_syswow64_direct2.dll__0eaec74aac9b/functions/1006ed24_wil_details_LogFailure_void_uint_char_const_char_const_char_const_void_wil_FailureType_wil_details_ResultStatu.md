# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,uint,char *,uint,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x1006ed24`
- end: `0x1006efb5`
- name: `?LogFailure@details@wil@@YGXPAXIPBD110W4FailureType@2@ABUResultStatus@12@PBG_NPAGIPADIW4FailureFlags@2@PAUFailureInfo@2@@Z`
- size: `657`
- prototype: `void __userpurge(void *callerReturnAddress@<ecx>, unsigned int lineNumber@<edx>, const char *fileName, const char *functionName, const char *code, void *returnAddress, wil::FailureType type, const wil::details::ResultStatus *resultPair, const wchar_t *message, bool debugString, wchar_t *callContextString, unsigned int flags, char *failure, unsigned int callerReturnAddress@<ecx>, wil::FailureFlags lineNumber@<dl>, wil::FailureInfo *fileName)`
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x1006d157`
- `0x1006d1a9`
- `0x1006d226`

## callees

- `0x10067b20`
- `0x1006d0c7`
- `0x1006e31f`
- `0x1006e9a9`
- `0x1006ed24`
- `0x1006f80a`
- `0x1006f830`
- `0x1006f970`
- `0x1006f989`
- `0x10070cbb`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1006ee05`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1006ee05`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1006ef77`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1006ef77`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1006ef0a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1006ef0a`

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
0x1006ed24  mov     edi, edi
0x1006ed26  push    ebp
0x1006ed27  mov     ebp, esp
0x1006ed29  and     esp, 0FFFFFFF8h
0x1006ed2c  sub     esp, 0Ch
0x1006ed2f  push    ebx
0x1006ed30  mov     ebx, [ebp+debugString]
0x1006ed33  xor     eax, eax
0x1006ed35  push    esi
0x1006ed36  mov     esi, [ebp+failure]
0x1006ed39  push    edi; this
0x1006ed3a  mov     [ebx], ax
0x1006ed3d  mov     eax, [ebp+callContextString]
0x1006ed40  mov     [esp+18h+var_8], lineNumber
0x1006ed44  mov     [esp+18h+var_4], callerReturnAddress
0x1006ed48  mov     [esp+18h+var_C], 0
0x1006ed50  mov     byte ptr [eax], 0
0x1006ed53  mov     eax, [ebp+resultPair]
0x1006ed56  mov     edi, [eax]
0x1006ed58  mov     [esi+8], edi
0x1006ed5b  mov     eax, [eax+4]
0x1006ed5e  mov     [esi+0Ch], eax
0x1006ed61  mov     eax, [ebp+type]
0x1006ed64  sub     eax, 0
0x1006ed67  jz      short loc_1006EDBD
0x1006ed69  sub     eax, 1
0x1006ed6c  jz      short loc_1006EDB2
0x1006ed6e  sub     eax, 1
0x1006ed71  jz      short loc_1006ED80
0x1006ed73  sub     eax, 1
0x1006ed76  jnz     short loc_1006EDC6
0x1006ed78  push    edi; hr
0x1006ed79  call    ?RecordFailFast@details@wil@@YGHJ@Z; wil::details::RecordFailFast(long)
0x1006ed7e  jmp     short loc_1006EDB9
0x1006ed80  test    edi, edi
0x1006ed82  js      short loc_1006EDA9
0x1006ed84  push    callerReturnAddress
0x1006ed85  mov     edi, 8007029Ch
0x1006ed8a  push    edi; hr
0x1006ed8b  push    [ebp+returnAddress]; returnAddress
0x1006ed8e  push    [ebp+code]; code
0x1006ed91  push    [ebp+functionName]; functionName
0x1006ed94  push    [ebp+fileName]; fileName
0x1006ed97  call    ??$ReportFailure_Hr@$01@details@wil@@YGXPAXIPBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1006ed9c  mov     callerReturnAddress, edi; hr
0x1006ed9e  mov     [esi+8], edi
0x1006eda1  call    ?HrToNtStatus@details@wil@@YGJJ@Z; wil::details::HrToNtStatus(long)
0x1006eda6  mov     [esi+0Ch], eax
0x1006eda9  mov     callerReturnAddress, edi; hr
0x1006edab  call    ?RecordLog@details@wil@@YGHJ@Z; wil::details::RecordLog(long)
0x1006edb0  jmp     short loc_1006EDB9
0x1006edb2  mov     callerReturnAddress, edi; hr
0x1006edb4  call    ?RecordReturn@details@wil@@YGHJ@Z; wil::details::RecordReturn(long)
0x1006edb9  mov     edi, eax
0x1006edbb  jmp     short loc_1006EDCA
0x1006edbd  mov     callerReturnAddress, edi; hr
0x1006edbf  call    ?RecordException@details@wil@@YGHJ@Z; wil::details::RecordException(long)
0x1006edc4  jmp     short loc_1006EDB9
0x1006edc6  mov     edi, [esp+18h+var_C]
0x1006edca  mov     eax, [ebp+type]
0x1006edcd  mov     lineNumber, [ebp+resultPair]
0x1006edd0  mov     callerReturnAddress, [ebp+flags]
0x1006edd3  mov     [esi], eax
0x1006edd5  xor     eax, eax
0x1006edd7  inc     eax
0x1006edd8  mov     [esi+4], callerReturnAddress
0x1006eddb  cmp     [lineNumber+8], eax
0x1006edde  jnz     short loc_1006EDE6
0x1006ede0  or      callerReturnAddress, 8
0x1006ede3  mov     [esi+4], callerReturnAddress
0x1006ede6  lock xadd ?s_failureId@?1??LogFailure@details@wil@@YGXPAXIPBD110W4FailureType@3@ABUResultStatus@23@PBG_NPAGIPADIW4FailureFlags@3@PAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,uint,char *,uint,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1006edee  inc     eax
0x1006edef  mov     [esi+10h], eax
0x1006edf2  mov     eax, [ebp+message]
0x1006edf5  test    eax, eax
0x1006edf7  jz      short loc_1006EE00
0x1006edf9  xor     callerReturnAddress, callerReturnAddress
0x1006edfb  cmp     [eax], cx
0x1006edfe  jnz     short loc_1006EE02
0x1006ee00  xor     eax, eax
0x1006ee02  mov     [esi+14h], eax
0x1006ee05  call    ds:__imp__GetCurrentThreadId@0; GetCurrentThreadId()
0x1006ee0b  mov     [esi+18h], eax
0x1006ee0e  xor     callerReturnAddress, callerReturnAddress
0x1006ee10  mov     eax, [ebp+fileName]
0x1006ee13  mov     [esi+24h], eax
0x1006ee16  mov     eax, [esp+18h+var_8]
0x1006ee1a  mov     [esi+28h], eax
0x1006ee1d  mov     eax, [ebp+code]
0x1006ee20  mov     [esi+1Ch], eax
0x1006ee23  mov     eax, [ebp+functionName]
0x1006ee26  mov     [esi+20h], eax
0x1006ee29  mov     eax, [ebp+returnAddress]
0x1006ee2c  mov     [esi+50h], eax
0x1006ee2f  mov     eax, [esp+18h+var_4]
0x1006ee33  mov     [esi+2Ch], edi
0x1006ee36  lea     edi, [esi+40h]
0x1006ee39  mov     [esi+54h], eax
0x1006ee3c  xor     eax, eax
0x1006ee3e  mov     [esi+30h], callerReturnAddress
0x1006ee41  stosd
0x1006ee42  stosd
0x1006ee43  stosd
0x1006ee44  xor     eax, eax
0x1006ee46  lea     edi, [esi+34h]
0x1006ee49  stosd
0x1006ee4a  stosd
0x1006ee4b  stosd
0x1006ee4c  mov     edi, ?g_pfnGetModuleName@details@wil@@3P6GPBDX_EA
0x1006ee52  test    edi, edi
0x1006ee54  jz      short loc_1006EE62
0x1006ee56  mov     callerReturnAddress, edi; this
0x1006ee58  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1006ee5e  call    edi ; ?g_pfnGetModuleName@details@wil@@3P6GPBDX_EA
0x1006ee60  jmp     short loc_1006EE64
0x1006ee62  mov     eax, callerReturnAddress
0x1006ee64  mov     edi, ?g_pfnNotifyFailure@details@wil@@3P6GXPAUFailureInfo@2@@_EA
0x1006ee6a  mov     [esi+4Ch], eax
0x1006ee6d  test    edi, edi
0x1006ee6f  jz      short loc_1006EE7C
0x1006ee71  push    esi
0x1006ee72  mov     callerReturnAddress, edi; this
0x1006ee74  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1006ee7a  call    edi ; ?g_pfnNotifyFailure@details@wil@@3P6GXPAUFailureInfo@2@@_EA
0x1006ee7c  mov     edi, ?g_pfnGetContextAndNotifyFailure@details@wil@@3P6GXPAUFailureInfo@2@PADI@_EA
0x1006ee82  test    edi, edi
0x1006ee84  jz      short loc_1006EE99
0x1006ee86  push    400h
0x1006ee8b  push    [ebp+callContextString]
0x1006ee8e  mov     callerReturnAddress, edi; this
0x1006ee90  push    esi
0x1006ee91  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1006ee97  call    edi ; ?g_pfnGetContextAndNotifyFailure@details@wil@@3P6GXPAUFailureInfo@2@PADI@_EA
0x1006ee99  mov     edi, ?g_pfnLoggingCallback@details@wil@@3P6GXABUFailureInfo@2@@_EA
0x1006ee9f  test    edi, edi
0x1006eea1  jz      short loc_1006EEAE
0x1006eea3  push    esi
0x1006eea4  mov     callerReturnAddress, edi; this
0x1006eea6  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1006eeac  call    edi ; ?g_pfnLoggingCallback@details@wil@@3P6GXABUFailureInfo@2@@_EA
0x1006eeae  mov     edi, ?g_pfnOriginateCallback@details@wil@@3P6GXABUFailureInfo@2@@_EA
0x1006eeb4  test    edi, edi
0x1006eeb6  jz      short loc_1006EEC9
0x1006eeb8  test    byte ptr [esi+4], 2
0x1006eebc  jnz     short loc_1006EEC9
0x1006eebe  push    esi
0x1006eebf  mov     callerReturnAddress, edi; this
0x1006eec1  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1006eec7  call    edi ; ?g_pfnOriginateCallback@details@wil@@3P6GXABUFailureInfo@2@@_EA
0x1006eec9  cmp     dword ptr [esi+8], 0
0x1006eecd  jl      short loc_1006EEE9
0x1006eecf  cmp     [ebp+type], 3
0x1006eed3  jnz     loc_1006EFA9
0x1006eed9  mov     callerReturnAddress, 8000FFFFh; hr
0x1006eede  mov     [esi+8], callerReturnAddress
0x1006eee1  call    ?HrToNtStatus@details@wil@@YGJJ@Z; wil::details::HrToNtStatus(long)
0x1006eee6  mov     [esi+0Ch], eax
0x1006eee9  cmp     ?g_fIsDebuggerPresent@wil@@3_NA, 0; bool wil::g_fIsDebuggerPresent
0x1006eef0  jnz     short loc_1006EF14
0x1006eef2  mov     edi, ?g_pfnIsDebuggerPresent@wil@@3P6G_NX_EA
0x1006eef8  test    edi, edi
0x1006eefa  jz      short loc_1006EF0A
0x1006eefc  mov     callerReturnAddress, edi; this
0x1006eefe  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1006ef04  call    edi ; ?g_pfnIsDebuggerPresent@wil@@3P6G_NX_EA
0x1006ef06  test    al, al
0x1006ef08  jmp     short loc_1006EF12
0x1006ef0a  call    ds:__imp__IsDebuggerPresent@0; IsDebuggerPresent()
0x1006ef10  test    eax, eax
0x1006ef12  jz      short loc_1006EF1A
0x1006ef14  test    byte ptr [esi+4], 2
0x1006ef18  jz      short loc_1006EF3E
0x1006ef1a  mov     edi, _g_pfnResultLoggingCallback
0x1006ef20  test    edi, edi
0x1006ef22  jz      short loc_1006EF7D
0x1006ef24  cmp     ?g_resultMessageCallbackSet@details@wil@@3_NA, 0; bool wil::details::g_resultMessageCallbackSet
0x1006ef2b  jnz     short loc_1006EF7D
0x1006ef2d  xor     eax, eax
0x1006ef2f  mov     callerReturnAddress, edi; this
0x1006ef31  push    eax
0x1006ef32  push    eax
0x1006ef33  push    esi
0x1006ef34  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1006ef3a  call    edi ; _g_pfnResultLoggingCallback
0x1006ef3c  jmp     short loc_1006EF7D
0x1006ef3e  mov     edi, _g_pfnResultLoggingCallback
0x1006ef44  test    edi, edi
0x1006ef46  jz      short loc_1006EF62
0x1006ef48  cmp     ?g_resultMessageCallbackSet@details@wil@@3_NA, 0; bool wil::details::g_resultMessageCallbackSet
0x1006ef4f  jnz     short loc_1006EF62
0x1006ef51  push    800h
0x1006ef56  push    ebx
0x1006ef57  push    esi
0x1006ef58  mov     callerReturnAddress, edi; this
0x1006ef5a  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1006ef60  call    edi ; _g_pfnResultLoggingCallback
0x1006ef62  xor     eax, eax
0x1006ef64  cmp     [ebx], ax
0x1006ef67  jnz     short loc_1006EF76
0x1006ef69  push    esi; failure
0x1006ef6a  mov     lineNumber, 800h; cchDest
0x1006ef6f  mov     callerReturnAddress, ebx; pszDest
0x1006ef71  call    ?GetFailureLogString@wil@@YGJPAGIABUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,uint,wil::FailureInfo const &)
0x1006ef76  push    ebx; lpOutputString
0x1006ef77  call    ds:__imp__OutputDebugStringW@4; OutputDebugStringW(x)
0x1006ef7d  test    byte ptr [esi+4], 4
0x1006ef81  jnz     short loc_1006EF8C
0x1006ef83  cmp     ?g_fBreakOnFailure@wil@@3_NA, 0; bool wil::g_fBreakOnFailure
0x1006ef8a  jz      short loc_1006EFA0
0x1006ef8c  mov     esi, ?g_pfnDebugBreak@details@wil@@3P6GXX_EA
0x1006ef92  test    esi, esi
0x1006ef94  jz      short loc_1006EFA0
0x1006ef96  mov     callerReturnAddress, esi; this
0x1006ef98  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1006ef9e  call    esi ; ?g_pfnDebugBreak@details@wil@@3P6GXX_EA
0x1006efa0  pop     edi
0x1006efa1  pop     esi
0x1006efa2  pop     ebx
0x1006efa3  mov     esp, ebp
0x1006efa5  pop     ebp
0x1006efa6  retn    38h ; '8'
0x1006efa9  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YGXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
