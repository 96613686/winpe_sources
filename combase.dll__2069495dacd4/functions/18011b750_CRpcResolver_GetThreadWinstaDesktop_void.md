# CRpcResolver::GetThreadWinstaDesktop(void)

- ea: `0x18011b750`
- end: `0x18011bcf0`
- name: `?GetThreadWinstaDesktop@CRpcResolver@@QEAAJXZ`
- size: `1440`
- prototype: `HRESULT __fastcall(CRpcResolver *this)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1801ab048`

## callees

- `0x18005c640`
- `0x18008db2c`
- `0x1800a6f50`
- `0x18011b750`
- `0x18013f5a4`
- `0x1801457c0`
- `0x18014d5f4`
- `0x180179024`
- `0x180187f14`
- `0x1801999b0`
- `0x18019b674`
- `0x1801ac258`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011b7df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011b944`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011b9fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011ba84`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011baf2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011bb6e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011b7df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011b944`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011b9fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011ba84`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011baf2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011bb6e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18011ba50`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18011bb3a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18011bbfc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18011ba50`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18011bb3a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18011bbfc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18011bc6a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18011bc9a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18011bcb5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18011bc6a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18011bc9a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18011bcb5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18011b808`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18011b808`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18011b92a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18011b92a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18011b817`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18011b817`
- `api-ms-win-core-processthreads-l1-1-1!GetProcessMitigationPolicy` at `0x18011b82c`
- `api-ms-win-core-processthreads-l1-1-1!GetProcessMitigationPolicy` at `0x18011b82c`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetThreadDesktop` at `0x18011b932`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetThreadDesktop` at `0x18011b932`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetProcessWindowStation` at `0x18011b7cd`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetProcessWindowStation` at `0x18011b7cd`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetUserObjectInformationW` at `0x18011b9f0`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetUserObjectInformationW` at `0x18011ba7a`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetUserObjectInformationW` at `0x18011bae4`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetUserObjectInformationW` at `0x18011bb64`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetUserObjectInformationW` at `0x18011b9f0`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetUserObjectInformationW` at `0x18011ba7a`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetUserObjectInformationW` at `0x18011bae4`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetUserObjectInformationW` at `0x18011bb64`

## string_xrefs

- `0x18011b8c6`: `onecore\com\combase\dcomrem\resolver.cxx`
- `0x18011b90c`: `onecore\com\combase\dcomrem\resolver.cxx`
- `0x18011b98a`: `onecore\com\combase\dcomrem\resolver.cxx`
- `0x18011bbb4`: `onecore\com\combase\dcomrem\resolver.cxx`
- `0x18011bcde`: `onecore\com\combase\dcomrem\resolver.cxx`
- `0x18011b801`: `user32.dll`
- `0x18011b8bf`: `CRpcResolver::GetThreadWinstaDesktop`
- `0x18011b8fd`: `CRpcResolver::GetThreadWinstaDesktop`
- `0x18011b983`: `CRpcResolver::GetThreadWinstaDesktop`
- `0x18011bba5`: `CRpcResolver::GetThreadWinstaDesktop`
- `0x18011b96a`: `GetThreadDesktop failed, last error=%!WINERROR!`

## pseudocode

```c
HRESULT __fastcall CRpcResolver::GetThreadWinstaDesktop(CRpcResolver *this)
{
  HRESULT result; // eax
  CRpcResolver *v2; // rcx
  HWINSTA ProcessWindowStation; // rdi
  signed int LastError; // eax
  unsigned int v5; // edx
  signed int Failure; // ebx
  IComProcessInfo3 *CurrentProcess; // rax
  DWORD CurrentThreadId; // eax
  HDESK ThreadDesktop; // r14
  bool v10; // cc
  wchar_t *v11; // r15
  wchar_t *v12; // rsi
  const wchar_t *format; // rax
  int v14; // r8d
  __int64 v15; // rax
  __int64 v16; // rcx
  unsigned __int64 v17; // rbx
  wchar_t *v18; // rax
  unsigned int Length; // [rsp+30h] [rbp-79h] BYREF
  _PROCESS_MITIGATION_SYSTEM_CALL_DISABLE_POLICY policy; // [rsp+34h] [rbp-75h]
  wchar_t wszWinsta[32]; // [rsp+40h] [rbp-69h] BYREF
  wchar_t wszDesktop[32]; // [rsp+80h] [rbp-29h] BYREF
  void *retaddr; // [rsp+108h] [rbp+5Fh]

  Length = 0;
  if ( g_explicitWinstaDesktopString )
  {
    CRpcResolver::_pwszWinstaDesktop = g_explicitWinstaDesktopString;
    return 0;
  }
  if ( IsGetProcessWindowStationPresent() && NtCurrentPeb()->KernelCallbackTable
    || (result = CRpcResolver::ResolveProcessDesktopNoUser(v2), result == 50) )
  {
    ProcessWindowStation = GetProcessWindowStation();
    if ( !ProcessWindowStation )
    {
      LastError = GetLastError();
      v5 = LastError;
      if ( LastError > 0 )
        Failure = (unsigned __int16)LastError | 0x80070000;
      else
        Failure = LastError;
      if ( LastError == 127 )
      {
        if ( GetModuleHandleW(L"user32.dll") )
        {
          if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(ERRORS) )
            ComTraceMessageT<>(
              "onecore\\com\\combase\\dcomrem\\resolver.cxx",
              "CRpcResolver::GetThreadWinstaDesktop",
              4193,
              ERRORS,
              L"Unexpected delay load failure for GetProcessWindowStation");
        }
        else
        {
          policy.Flags = 0;
          CurrentProcess = (IComProcessInfo3 *)GetCurrentProcess();
          if ( !GetProcessMitigationPolicy(CurrentProcess, (tagBLOB *)4) )
            wil::details::in1diag3::_FailFast_Unexpected(
              retaddr,
              0x104Cu,
              "onecore\\com\\combase\\dcomrem\\resolver.cxx");
          Failure = DiagnoseUser32LoadFailure();
          _InterlockedExchange(&g_user32LoadFailure._Storage._Value, Failure);
        }
      }
      else if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(ERRORS) )
      {
        ComTraceMessageT<unsigned int>(
          "onecore\\com\\combase\\dcomrem\\resolver.cxx",
          "CRpcResolver::GetThreadWinstaDesktop",
          4198,
          ERRORS,
          L"Unknown failure from GetProcessWindowStation, last error=%!WINERROR!",
          v5);
      }
      BreakOnCoInitializeSecurityRuntimeFailureIfRequested(Failure);
      return Failure;
    }
    CurrentThreadId = GetCurrentThreadId();
    ThreadDesktop = GetThreadDesktop(CurrentThreadId);
    if ( !ThreadDesktop )
    {
      Failure = GetLastError();
      if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(ERRORS) )
        ComTraceMessageT<unsigned int>(
          "onecore\\com\\combase\\dcomrem\\resolver.cxx",
          "CRpcResolver::GetThreadWinstaDesktop",
          4209,
          ERRORS,
          L"GetThreadDesktop failed, last error=%!WINERROR!",
          Failure);
      BreakOnCoInitializeSecurityRuntimeFailureIfRequested(Failure);
      v10 = Failure <= 0;
      goto LABEL_31;
    }
    Length = 64;
    v11 = wszWinsta;
    v12 = wszDesktop;
    if ( !GetUserObjectInformationW(ProcessWindowStation, 2, wszWinsta, 0x40u, &Length) )
    {
      Failure = GetLastError();
      if ( Failure != 122 )
      {
        if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(ERRORS) )
        {
          format = L"GetUserObjectInformation(hWinsta) failed, last error=%!WINERROR!";
          v14 = 4231;
LABEL_60:
          ComTraceMessageT<unsigned int>(
            "onecore\\com\\combase\\dcomrem\\resolver.cxx",
            "CRpcResolver::GetThreadWinstaDesktop",
            v14,
            ERRORS,
            format,
            Failure);
          goto $WinstaDesktopExit;
        }
        goto $WinstaDesktopExit;
      }
      v11 = (wchar_t *)HeapAlloc(g_hHeap, 0, Length);
      if ( !v11 )
        goto LABEL_72;
      if ( !GetUserObjectInformationW(ProcessWindowStation, 2, v11, Length, &Length) )
      {
        Failure = GetLastError();
        if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(ERRORS) )
        {
          format = L"GetUserObjectInformation(hWinsta) failed, last error=%!WINERROR!";
          v14 = 4252;
          goto LABEL_60;
        }
$WinstaDesktopExit:
        if ( !Failure )
          goto LABEL_74;
        goto LABEL_73;
      }
    }
    Length = 64;
    if ( !GetUserObjectInformationW(ThreadDesktop, 2, wszDesktop, 0x40u, &Length) )
    {
      Failure = GetLastError();
      if ( Failure != 122 )
      {
        if ( !Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 && (!gfEnableTracing || !IsWppLevelEnabled(ERRORS)) )
          goto $WinstaDesktopExit;
        v14 = 4271;
        goto LABEL_59;
      }
      v12 = (wchar_t *)HeapAlloc(g_hHeap, 0, Length);
      if ( !v12 )
        goto LABEL_72;
      if ( !GetUserObjectInformationW(ThreadDesktop, 2, v12, Length, &Length) )
      {
        Failure = GetLastError();
        if ( !Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 && (!gfEnableTracing || !IsWppLevelEnabled(ERRORS)) )
          goto $WinstaDesktopExit;
        v14 = 4292;
LABEL_59:
        format = L"GetUserObjectInformation(hDesk) failed, last error=%!WINERROR!";
        goto LABEL_60;
      }
    }
    v15 = -1;
    v16 = -1;
    do
      ++v16;
    while ( v11[v16] );
    do
      ++v15;
    while ( v12[v15] );
    v17 = v16 + v15 + 2;
    v18 = (wchar_t *)HeapAlloc(g_hHeap, 0, 2 * v17);
    CRpcResolver::_pwszWinstaDesktop = v18;
    if ( v18 )
    {
      if ( StringCchCopyW(v18, v17, v11) >= 0
        && StringCchCatW(CRpcResolver::_pwszWinstaDesktop, v17, L"\\") >= 0
        && StringCchCatW(CRpcResolver::_pwszWinstaDesktop, v17, v12) >= 0 )
      {
        Failure = 0;
        goto LABEL_74;
      }
      Failure = 111;
      HeapFree(g_hHeap, 0, CRpcResolver::_pwszWinstaDesktop);
      CRpcResolver::_pwszWinstaDesktop = 0;
LABEL_73:
      BreakOnCoInitializeSecurityRuntimeFailureIfRequested(Failure);
LABEL_74:
      if ( v11 != wszWinsta )
        HeapFree(g_hHeap, 0, v11);
      if ( v12 != wszDesktop )
        HeapFree(g_hHeap, 0, v12);
      v10 = Failure <= 0;
      if ( !Failure )
      {
        if ( CRpcResolver::_pwszWinstaDesktop )
          return Failure;
        LOWORD(Failure) = 14;
        return (unsigned __int16)Failure | 0x80070000;
      }
LABEL_31:
      if ( v10 )
        return Failure;
      return (unsigned __int16)Failure | 0x80070000;
    }
LABEL_72:
    Failure = 14;
    goto LABEL_73;
  }
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18011b750  push    rbp
0x18011b752  push    rbx
0x18011b753  push    rsi
0x18011b754  push    rdi
0x18011b755  push    r12
0x18011b757  push    r14
0x18011b759  push    r15
0x18011b75b  lea     rbp, [rsp-27h]
0x18011b760  sub     rsp, 0D0h
0x18011b767  mov     rax, cs:__security_cookie
0x18011b76e  xor     rax, rsp
0x18011b771  mov     [rbp+57h+var_40], rax
0x18011b775  mov     rax, cs:?g_explicitWinstaDesktopString@@3PEAGEA; ushort * g_explicitWinstaDesktopString
0x18011b77c  xor     r12d, r12d
0x18011b77f  mov     [rbp+57h+Length], r12d
0x18011b783  test    rax, rax
0x18011b786  jz      short loc_18011B796
0x18011b788  mov     cs:?_pwszWinstaDesktop@CRpcResolver@@0PEAGEA, rax; ushort * CRpcResolver::_pwszWinstaDesktop
0x18011b78f  xor     eax, eax
0x18011b791  jmp     loc_18011B9AC
0x18011b796  call    IsGetProcessWindowStationPresent
0x18011b79b  test    al, al
0x18011b79d  jz      short loc_18011B7AE
0x18011b79f  mov     rax, gs:60h
0x18011b7a8  cmp     [rax+58h], r12
0x18011b7ac  jnz     short loc_18011B7CD
0x18011b7ae  call    ?ResolveProcessDesktopNoUser@CRpcResolver@@QEAAKXZ; CRpcResolver::ResolveProcessDesktopNoUser(void)
0x18011b7b3  cmp     eax, 32h ; '2'
0x18011b7b6  jz      short loc_18011B7CD
0x18011b7b8  test    eax, eax
0x18011b7ba  jle     loc_18011B9AC
0x18011b7c0  movzx   eax, ax
0x18011b7c3  or      eax, 80070000h
0x18011b7c8  jmp     loc_18011B9AC
0x18011b7cd  call    cs:__imp_GetProcessWindowStation
0x18011b7d3  mov     rdi, rax
0x18011b7d6  test    rax, rax
0x18011b7d9  jnz     loc_18011B92A
0x18011b7df  call    cs:__imp_GetLastError
0x18011b7e5  mov     edx, eax
0x18011b7e7  test    eax, eax
0x18011b7e9  jg      short loc_18011B7EF
0x18011b7eb  mov     ebx, eax
0x18011b7ed  jmp     short loc_18011B7F8
0x18011b7ef  movzx   ebx, dx
0x18011b7f2  or      ebx, 80070000h
0x18011b7f8  cmp     edx, 7Fh
0x18011b7fb  jnz     loc_18011B8D4
0x18011b801  lea     rcx, aUser32Dll; "user32.dll"
0x18011b808  call    cs:__imp_GetModuleHandleW
0x18011b80e  test    rax, rax
0x18011b811  jnz     short loc_18011B88C
0x18011b813  mov     dword ptr [rbp+57h+policy.___u0], r12d
0x18011b817  call    cs:__imp_GetCurrentProcess
0x18011b81d  mov     edx, 4; tagBLOB *
0x18011b822  lea     r8, [rbp+57h+policy]
0x18011b826  mov     r9d, edx
0x18011b829  mov     rcx, rax; this
0x18011b82c  call    cs:__imp_GetProcessMitigationPolicy
0x18011b832  test    eax, eax
0x18011b834  jz      loc_18011BCDA
0x18011b83a  test    byte ptr [rbp+57h+policy.___u0], 1
0x18011b83e  jz      short loc_18011B87A
0x18011b840  mov     eax, cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
0x18011b846  mov     ebx, 800704ECh
0x18011b84b  test    eax, eax
0x18011b84d  jnz     short loc_18011B86B
0x18011b84f  cmp     cs:?gfEnableTracing@@3HA, r12d; int gfEnableTracing
0x18011b856  jz      loc_18011B91E
0x18011b85c  xor     ecx, ecx; level
0x18011b85e  call    IsWppLevelEnabled
0x18011b863  test    al, al
0x18011b865  jz      loc_18011B91E
0x18011b86b  lea     rax, aCannotDetermin; "Cannot determine process window station"...
0x18011b872  mov     r8d, 1053h
0x18011b878  jmp     short loc_18011B8B7
0x18011b87a  call    ?DiagnoseUser32LoadFailure@@YAJXZ; DiagnoseUser32LoadFailure(void)
0x18011b87f  mov     ebx, eax
0x18011b881  xchg    eax, cs:?g_user32LoadFailure@@3U?$atomic@J@std@@A._Storage._Value; std::atomic<long> g_user32LoadFailure ...
0x18011b887  jmp     loc_18011B91E
0x18011b88c  mov     eax, cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
0x18011b892  test    eax, eax
0x18011b894  jnz     short loc_18011B8AA
0x18011b896  cmp     cs:?gfEnableTracing@@3HA, r12d; int gfEnableTracing
0x18011b89d  jz      short loc_18011B91E
0x18011b89f  xor     ecx, ecx; level
0x18011b8a1  call    IsWppLevelEnabled
0x18011b8a6  test    al, al
0x18011b8a8  jz      short loc_18011B91E
0x18011b8aa  lea     rax, aUnexpectedDela; "Unexpected delay load failure for GetPr"...
0x18011b8b1  mov     r8d, 1061h; line
0x18011b8b7  xor     r9d, r9d; level
0x18011b8ba  mov     [rsp+100h+format], rax; format
0x18011b8bf  lea     rdx, aCrpcresolverGe_0; "CRpcResolver::GetThreadWinstaDesktop"
0x18011b8c6  lea     rcx, aOnecoreComComb_138; "onecore\\com\\combase\\dcomrem\\resolve"...
0x18011b8cd  call    ??$ComTraceMessageT@$$V@@YAXPEBD0HW4TraceLevel@@PEBG@Z; ComTraceMessageT<>(char const *,char const *,int,TraceLevel,ushort const *)
0x18011b8d2  jmp     short loc_18011B91E
0x18011b8d4  mov     eax, cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
0x18011b8da  test    eax, eax
0x18011b8dc  jnz     short loc_18011B8F2
0x18011b8de  cmp     cs:?gfEnableTracing@@3HA, r12d; int gfEnableTracing
0x18011b8e5  jz      short loc_18011B91E
0x18011b8e7  xor     ecx, ecx; level
0x18011b8e9  call    IsWppLevelEnabled
0x18011b8ee  test    al, al
0x18011b8f0  jz      short loc_18011B91E
0x18011b8f2  mov     [rsp+100h+var_D8], edx; <args_0>
0x18011b8f6  lea     rax, aUnknownFailure; "Unknown failure from GetProcessWindowSt"...
0x18011b8fd  lea     rdx, aCrpcresolverGe_0; "CRpcResolver::GetThreadWinstaDesktop"
0x18011b904  mov     [rsp+100h+format], rax; format
0x18011b909  xor     r9d, r9d; level
0x18011b90c  lea     rcx, aOnecoreComComb_138; "onecore\\com\\combase\\dcomrem\\resolve"...
0x18011b913  mov     r8d, 1066h; line
0x18011b919  call    ??$ComTraceMessageT@I@@YAXPEBD0HW4TraceLevel@@PEBGI@Z; ComTraceMessageT<uint>(char const *,char const *,int,TraceLevel,ushort const *,uint)
0x18011b91e  mov     ecx, ebx; error
0x18011b920  call    ?BreakOnCoInitializeSecurityRuntimeFailureIfRequested@@YAXJ@Z; BreakOnCoInitializeSecurityRuntimeFailureIfRequested(long)
0x18011b925  jmp     loc_18011B9AA
0x18011b92a  call    cs:__imp_GetCurrentThreadId
0x18011b930  mov     ecx, eax; dwThreadId
0x18011b932  call    cs:__imp_GetThreadDesktop
0x18011b938  mov     r14, rax
0x18011b93b  test    rax, rax
0x18011b93e  jnz     loc_18011B9CA
0x18011b944  call    cs:__imp_GetLastError
0x18011b94a  mov     ebx, eax
0x18011b94c  mov     eax, cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
0x18011b952  test    eax, eax
0x18011b954  jnz     short loc_18011B96A
0x18011b956  cmp     cs:?gfEnableTracing@@3HA, r12d; int gfEnableTracing
0x18011b95d  jz      short loc_18011B996
0x18011b95f  xor     ecx, ecx; level
0x18011b961  call    IsWppLevelEnabled
0x18011b966  test    al, al
0x18011b968  jz      short loc_18011B996
0x18011b96a  lea     rax, aGetthreaddeskt_0; "GetThreadDesktop failed, last error=%!W"...
0x18011b971  mov     [rsp+100h+var_D8], ebx; <args_0>
0x18011b975  xor     r9d, r9d; level
0x18011b978  mov     [rsp+100h+format], rax; format
0x18011b97d  mov     r8d, 1071h; line
0x18011b983  lea     rdx, aCrpcresolverGe_0; "CRpcResolver::GetThreadWinstaDesktop"
0x18011b98a  lea     rcx, aOnecoreComComb_138; "onecore\\com\\combase\\dcomrem\\resolve"...
0x18011b991  call    ??$ComTraceMessageT@I@@YAXPEBD0HW4TraceLevel@@PEBGI@Z; ComTraceMessageT<uint>(char const *,char const *,int,TraceLevel,ushort const *,uint)
0x18011b996  mov     ecx, ebx; error
0x18011b998  call    ?BreakOnCoInitializeSecurityRuntimeFailureIfRequested@@YAXJ@Z; BreakOnCoInitializeSecurityRuntimeFailureIfRequested(long)
0x18011b99d  test    ebx, ebx
0x18011b99f  jle     short loc_18011B9AA
0x18011b9a1  movzx   ebx, bx
0x18011b9a4  or      ebx, 80070000h
0x18011b9aa  mov     eax, ebx
0x18011b9ac  mov     rcx, [rbp+57h+var_40]
0x18011b9b0  xor     rcx, rsp; StackCookie
0x18011b9b3  call    __security_check_cookie
0x18011b9b8  add     rsp, 0D0h
0x18011b9bf  pop     r15
0x18011b9c1  pop     r14
0x18011b9c3  pop     r12
0x18011b9c5  pop     rdi
0x18011b9c6  pop     rsi
0x18011b9c7  pop     rbx
0x18011b9c8  pop     rbp
0x18011b9c9  retn
0x18011b9ca  mov     ebx, 40h ; '@'
0x18011b9cf  lea     rax, [rbp+57h+Length]
0x18011b9d3  mov     r9d, ebx; nLength
0x18011b9d6  mov     [rbp+57h+Length], ebx
0x18011b9d9  lea     r8, [rbp+57h+wszWinsta]; pvInfo
0x18011b9dd  mov     [rsp+100h+format], rax; lpnLengthNeeded
0x18011b9e2  mov     rcx, rdi; hObj
0x18011b9e5  lea     r15, [rbp+57h+wszWinsta]
0x18011b9e9  lea     edx, [rbx-3Eh]; nIndex
0x18011b9ec  lea     rsi, [rbp+57h+wszDesktop]
0x18011b9f0  call    cs:__imp_GetUserObjectInformationW
0x18011b9f6  test    eax, eax
0x18011b9f8  jnz     loc_18011BAC9
0x18011b9fe  call    cs:__imp_GetLastError
0x18011ba04  mov     ebx, eax
0x18011ba06  cmp     eax, 7Ah ; 'z'
0x18011ba09  jz      short loc_18011BA43
0x18011ba0b  mov     eax, cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
0x18011ba11  test    eax, eax
0x18011ba13  jnz     short loc_18011BA31
0x18011ba15  cmp     cs:?gfEnableTracing@@3HA, r12d; int gfEnableTracing
0x18011ba1c  jz      $WinstaDesktopExit
0x18011ba22  xor     ecx, ecx; level
0x18011ba24  call    IsWppLevelEnabled
0x18011ba29  test    al, al
0x18011ba2b  jz      $WinstaDesktopExit
0x18011ba31  lea     rax, aGetuserobjecti_1; "GetUserObjectInformation(hWinsta) faile"...
0x18011ba38  mov     r8d, 1087h
0x18011ba3e  jmp     loc_18011BBA1
0x18011ba43  mov     r8d, [rbp+57h+Length]; dwBytes
0x18011ba47  xor     edx, edx; dwFlags
0x18011ba49  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x18011ba50  call    cs:__imp_HeapAlloc
0x18011ba56  mov     r15, rax
0x18011ba59  test    rax, rax
0x18011ba5c  jz      loc_18011BC79
0x18011ba62  mov     r9d, [rbp+57h+Length]; nLength
0x18011ba66  lea     rax, [rbp+57h+Length]
0x18011ba6a  mov     r8, r15; pvInfo
0x18011ba6d  mov     [rsp+100h+format], rax; lpnLengthNeeded
0x18011ba72  mov     edx, 2; nIndex
0x18011ba77  mov     rcx, rdi; hObj
0x18011ba7a  call    cs:__imp_GetUserObjectInformationW
0x18011ba80  test    eax, eax
0x18011ba82  jnz     short loc_18011BAC4
0x18011ba84  call    cs:__imp_GetLastError
0x18011ba8a  mov     ebx, eax
0x18011ba8c  mov     eax, cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
0x18011ba92  test    eax, eax
0x18011ba94  jnz     short loc_18011BAB2
0x18011ba96  cmp     cs:?gfEnableTracing@@3HA, r12d; int gfEnableTracing
0x18011ba9d  jz      $WinstaDesktopExit
0x18011baa3  xor     ecx, ecx; level
0x18011baa5  call    IsWppLevelEnabled
0x18011baaa  test    al, al
0x18011baac  jz      $WinstaDesktopExit
0x18011bab2  lea     rax, aGetuserobjecti_1; "GetUserObjectInformation(hWinsta) faile"...
0x18011bab9  mov     r8d, 109Ch
0x18011babf  jmp     loc_18011BBA1
0x18011bac4  mov     ebx, 40h ; '@'
0x18011bac9  lea     rax, [rbp+57h+Length]
0x18011bacd  mov     [rbp+57h+Length], ebx
0x18011bad0  mov     r9d, ebx; nLength
0x18011bad3  mov     [rsp+100h+format], rax; lpnLengthNeeded
0x18011bad8  lea     r8, [rbp+57h+wszDesktop]; pvInfo
0x18011badc  mov     edx, 2; nIndex
0x18011bae1  mov     rcx, r14; hObj
0x18011bae4  call    cs:__imp_GetUserObjectInformationW
0x18011baea  test    eax, eax
0x18011baec  jnz     loc_18011BBCD
0x18011baf2  call    cs:__imp_GetLastError
0x18011baf8  mov     ebx, eax
0x18011bafa  cmp     eax, 7Ah ; 'z'
0x18011bafd  jz      short loc_18011BB2D
0x18011baff  mov     eax, cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
0x18011bb05  test    eax, eax
0x18011bb07  jnz     short loc_18011BB25
0x18011bb09  cmp     cs:?gfEnableTracing@@3HA, r12d; int gfEnableTracing
0x18011bb10  jz      $WinstaDesktopExit
0x18011bb16  xor     ecx, ecx; level
0x18011bb18  call    IsWppLevelEnabled
0x18011bb1d  test    al, al
0x18011bb1f  jz      $WinstaDesktopExit
0x18011bb25  mov     r8d, 10AFh
0x18011bb2b  jmp     short loc_18011BB9A
0x18011bb2d  mov     r8d, [rbp+57h+Length]; dwBytes
0x18011bb31  xor     edx, edx; dwFlags
0x18011bb33  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x18011bb3a  call    cs:__imp_HeapAlloc
0x18011bb40  mov     rsi, rax
0x18011bb43  test    rax, rax
0x18011bb46  jz      loc_18011BC79
0x18011bb4c  mov     r9d, [rbp+57h+Length]; nLength
0x18011bb50  lea     rax, [rbp+57h+Length]
0x18011bb54  mov     r8, rsi; pvInfo
0x18011bb57  mov     [rsp+100h+format], rax; lpnLengthNeeded
0x18011bb5c  mov     edx, 2; nIndex
0x18011bb61  mov     rcx, r14; hObj
0x18011bb64  call    cs:__imp_GetUserObjectInformationW
0x18011bb6a  test    eax, eax
0x18011bb6c  jnz     short loc_18011BBCD
0x18011bb6e  call    cs:__imp_GetLastError
0x18011bb74  mov     ebx, eax
0x18011bb76  mov     eax, cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
0x18011bb7c  test    eax, eax
0x18011bb7e  jnz     short loc_18011BB94
0x18011bb80  cmp     cs:?gfEnableTracing@@3HA, r12d; int gfEnableTracing
0x18011bb87  jz      short $WinstaDesktopExit
0x18011bb89  xor     ecx, ecx; level
0x18011bb8b  call    IsWppLevelEnabled
0x18011bb90  test    al, al
0x18011bb92  jz      short $WinstaDesktopExit
0x18011bb94  mov     r8d, 10C4h; line
0x18011bb9a  lea     rax, aGetuserobjecti_0; "GetUserObjectInformation(hDesk) failed,"...
0x18011bba1  mov     [rsp+100h+var_D8], ebx; <args_0>
0x18011bba5  lea     rdx, aCrpcresolverGe_0; "CRpcResolver::GetThreadWinstaDesktop"
0x18011bbac  xor     r9d, r9d; level
0x18011bbaf  mov     [rsp+100h+format], rax; format
0x18011bbb4  lea     rcx, aOnecoreComComb_138; "onecore\\com\\combase\\dcomrem\\resolve"...
0x18011bbbb  call    ??$ComTraceMessageT@I@@YAXPEBD0HW4TraceLevel@@PEBGI@Z; ComTraceMessageT<uint>(char const *,char const *,int,TraceLevel,ushort const *,uint)
0x18011bbc0  test    ebx, ebx
0x18011bbc2  jz      loc_18011BC85
0x18011bbc8  jmp     loc_18011BC7E
0x18011bbcd  or      rax, 0FFFFFFFFFFFFFFFFh
0x18011bbd1  mov     rcx, rax
0x18011bbd4  inc     rcx
0x18011bbd7  cmp     [r15+rcx*2], r12w
0x18011bbdc  jnz     short loc_18011BBD4
0x18011bbde  inc     rax
0x18011bbe1  cmp     [rsi+rax*2], r12w
0x18011bbe6  jnz     short loc_18011BBDE
0x18011bbe8  lea     rbx, [rax+2]
0x18011bbec  xor     edx, edx; dwFlags
0x18011bbee  add     rbx, rcx
0x18011bbf1  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x18011bbf8  lea     r8, [rbx+rbx]; dwBytes
0x18011bbfc  call    cs:__imp_HeapAlloc
0x18011bc02  mov     cs:?_pwszWinstaDesktop@CRpcResolver@@0PEAGEA, rax; ushort * CRpcResolver::_pwszWinstaDesktop
0x18011bc09  test    rax, rax
  ... truncated ...
```
