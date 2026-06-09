# RasEapGetIdentity

- ea: `0x180002f20`
- end: `0x1800031f6`
- name: `RasEapGetIdentity`
- size: `726`
- prototype: `DWORD __stdcall(DWORD dwEapTypeId, HWND hwndParent, DWORD dwFlags, const WCHAR *pwszPhonebook, const WCHAR *pwszEntry, BYTE *pConnectionDataIn, DWORD dwSizeOfConnectionDataIn, BYTE *pUserDataIn, DWORD dwSizeOfUserDataIn, BYTE **ppUserDataOut, DWORD *pdwSizeOfUserDataOut, WCHAR **ppwszIdentityOut)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180001210`
- `0x180002f20`
- `0x180003200`
- `0x180003bd0`
- `0x1800047a0`
- `0x180006a20`
- `0x18000ee48`
- `0x180016280`

## import_xrefs

- `ntdll!NtQueryInformationToken` at `0x180002fb2`
- `ntdll!NtQueryInformationToken` at `0x180002fb2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800030f5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800031b9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800030f5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800031b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002fca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002fca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002fda`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002fda`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002ff6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800031b0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002ff6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800031b0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002f51`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000316e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002f51`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000316e`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180002f89`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180002f89`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180002f76`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180002f76`
- `rtutils!TraceDeregisterExA` at `0x180003199`
- `rtutils!TraceDeregisterExA` at `0x180003199`

## pseudocode

```c
DWORD __stdcall RasEapGetIdentity(
        DWORD dwEapTypeId,
        HWND hwndParent,
        DWORD dwFlags,
        const WCHAR *pwszPhonebook,
        const WCHAR *pwszEntry,
        BYTE *pConnectionDataIn,
        DWORD dwSizeOfConnectionDataIn,
        BYTE *pUserDataIn,
        DWORD dwSizeOfUserDataIn,
        BYTE **ppUserDataOut,
        DWORD *pdwSizeOfUserDataOut,
        WCHAR **ppwszIdentityOut)
{
  BYTE *v12; // rdi
  BOOL v15; // esi
  HANDLE CurrentProcess; // rax
  DWORD ProperiesAndPossibleIdentity; // eax
  DWORD v18; // ebx
  _QWORD *v19; // rcx
  __int64 v20; // rdx
  __int64 v21; // r9
  DWORD v22; // eax
  int v23; // eax
  int TokenInformation; // [rsp+50h] [rbp-68h] BYREF
  int v26; // [rsp+54h] [rbp-64h] BYREF
  ULONG ReturnLength; // [rsp+58h] [rbp-60h] BYREF
  void *TokenHandle; // [rsp+60h] [rbp-58h] BYREF
  _QWORD v29[10]; // [rsp+68h] [rbp-50h] BYREF

  v26 = 1;
  v29[0] = 0;
  v12 = 0;
  EnterCriticalSection(&g_criticalSection);
  if ( !g_dwDebuggingRefCount )
  {
    TokenHandle = 0;
    v15 = 0;
    ReturnLength = 0;
    TokenInformation = 0;
    CurrentProcess = GetCurrentProcess();
    if ( OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
    {
      if ( NtQueryInformationToken(TokenHandle, TokenIsAppContainer, &TokenInformation, 4u, &ReturnLength) >= 0 )
        v15 = TokenInformation != 0;
    }
    else
    {
      GetLastError();
    }
    if ( TokenHandle )
      CloseHandle(TokenHandle);
    if ( !v15 )
      DebugInitEx();
  }
  ++g_dwDebuggingRefCount;
  LeaveCriticalSection(&g_criticalSection);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 181, &WPP_9b8b2f5616a63040265c7a7536bda72e_Traceguids);
  *ppUserDataOut = 0;
  ProperiesAndPossibleIdentity = EapMsChapv2GetProperiesAndPossibleIdentity(
                                   dwFlags,
                                   pConnectionDataIn,
                                   dwSizeOfConnectionDataIn,
                                   pUserDataIn,
                                   dwSizeOfUserDataIn,
                                   ppUserDataOut,
                                   pdwSizeOfUserDataOut,
                                   ppwszIdentityOut,
                                   &v26);
  v18 = ProperiesAndPossibleIdentity;
  if ( ProperiesAndPossibleIdentity )
  {
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      goto LABEL_29;
    v20 = 182;
    goto LABEL_15;
  }
  if ( v26 )
  {
    v12 = *ppUserDataOut;
    *ppUserDataOut = 0;
    *pdwSizeOfUserDataOut = 0;
    ProperiesAndPossibleIdentity = EapMSChapv2GetUserCredentials(hwndParent, v12, v29);
    v18 = ProperiesAndPossibleIdentity;
    if ( ProperiesAndPossibleIdentity )
    {
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      {
        v20 = 183;
LABEL_15:
        v21 = ProperiesAndPossibleIdentity;
LABEL_16:
        WPP_SF_d(v19[2], v20, &WPP_9b8b2f5616a63040265c7a7536bda72e_Traceguids, v21);
      }
    }
    else
    {
      LocalFree(v12);
      v12 = (BYTE *)v29[0];
      if ( ppwszIdentityOut
        && (ProperiesAndPossibleIdentity = GetIdentityFromUserName((LPCCH)(v29[0] + 12LL), (LPCCH)(v29[0] + 526LL)),
            (v18 = ProperiesAndPossibleIdentity) != 0) )
      {
        v19 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
        {
          v20 = 184;
          goto LABEL_15;
        }
      }
      else
      {
        v22 = MschapV2UserPropBuffSize(v12);
        if ( v22 )
        {
          *ppUserDataOut = v12;
          v12 = 0;
          *pdwSizeOfUserDataOut = v22;
        }
        else
        {
          v18 = 534;
          v19 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
          {
            v20 = 185;
            v21 = 534;
            goto LABEL_16;
          }
        }
      }
    }
  }
LABEL_29:
  EnterCriticalSection(&g_criticalSection);
  v23 = g_dwDebuggingRefCount;
  if ( !g_dwDebuggingRefCount || (--g_dwDebuggingRefCount, v23 == 1) )
  {
    if ( g_dwTraceId != -1 )
    {
      TraceDeregisterExA(g_dwTraceId, 4u);
      g_dwTraceId = -1;
    }
  }
  LeaveCriticalSection(&g_criticalSection);
  LocalFree(v12);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 186, &WPP_9b8b2f5616a63040265c7a7536bda72e_Traceguids, v18);
  return v18;
}

```

## disassembly

```asm
0x180002f20  push    rbx
0x180002f22  push    rbp
0x180002f23  push    rsi
0x180002f24  push    rdi
0x180002f25  push    r12
0x180002f27  push    r13
0x180002f29  push    r14
0x180002f2b  push    r15
0x180002f2d  sub     rsp, 78h
0x180002f31  xor     r12d, r12d
0x180002f34  mov     [rsp+0B8h+var_64], 1
0x180002f3c  lea     rcx, g_criticalSection; lpCriticalSection
0x180002f43  mov     [rsp+0B8h+var_50], r12
0x180002f48  mov     edi, r12d
0x180002f4b  mov     ebx, r8d
0x180002f4e  mov     r15, rdx
0x180002f51  call    cs:__imp_EnterCriticalSection
0x180002f57  cmp     cs:g_dwDebuggingRefCount, r12d
0x180002f5e  jnz     loc_180002FE9
0x180002f64  mov     [rsp+0B8h+TokenHandle], r12
0x180002f69  mov     esi, r12d
0x180002f6c  mov     [rsp+0B8h+var_60], r12d
0x180002f71  mov     [rsp+0B8h+TokenInformation], r12d
0x180002f76  call    cs:__imp_GetCurrentProcess
0x180002f7c  lea     r8, [rsp+0B8h+TokenHandle]; TokenHandle
0x180002f81  mov     edx, 8; DesiredAccess
0x180002f86  mov     rcx, rax; ProcessHandle
0x180002f89  call    cs:__imp_OpenProcessToken
0x180002f8f  test    eax, eax
0x180002f91  jz      short loc_180002FCA
0x180002f93  mov     rcx, [rsp+0B8h+TokenHandle]; TokenHandle
0x180002f98  lea     rax, [rsp+0B8h+var_60]
0x180002f9d  mov     r9d, 4; TokenInformationLength
0x180002fa3  mov     [rsp+0B8h+ReturnLength], rax; ReturnLength
0x180002fa8  lea     r8, [rsp+0B8h+TokenInformation]; TokenInformation
0x180002fad  mov     edx, 1Dh; TokenInformationClass
0x180002fb2  call    cs:__imp_NtQueryInformationToken
0x180002fb8  test    eax, eax
0x180002fba  js      short loc_180002FD0
0x180002fbc  cmp     [rsp+0B8h+TokenInformation], r12d
0x180002fc1  jz      short loc_180002FD0
0x180002fc3  mov     esi, 1
0x180002fc8  jmp     short loc_180002FD0
0x180002fca  call    cs:__imp_GetLastError
0x180002fd0  mov     rcx, [rsp+0B8h+TokenHandle]; hObject
0x180002fd5  test    rcx, rcx
0x180002fd8  jz      short loc_180002FE0
0x180002fda  call    cs:__imp_CloseHandle
0x180002fe0  test    esi, esi
0x180002fe2  jnz     short loc_180002FE9
0x180002fe4  call    DebugInitEx
0x180002fe9  inc     cs:g_dwDebuggingRefCount
0x180002fef  lea     rcx, g_criticalSection; lpCriticalSection
0x180002ff6  call    cs:__imp_LeaveCriticalSection
0x180002ffc  mov     rcx, cs:WPP_GLOBAL_Control
0x180003003  lea     r13, WPP_GLOBAL_Control
0x18000300a  cmp     rcx, r13
0x18000300d  jz      short loc_180003024
0x18000300f  mov     rcx, [rcx+10h]
0x180003013  lea     r8, WPP_9b8b2f5616a63040265c7a7536bda72e_Traceguids
0x18000301a  mov     edx, 0B5h
0x18000301f  call    WPP_SF_
0x180003024  mov     rsi, [rsp+0B8h+ppUserDataOut]
0x18000302c  lea     rax, [rsp+0B8h+var_64]
0x180003031  mov     rbp, [rsp+0B8h+ppwszIdentityOut]
0x180003039  mov     ecx, ebx
0x18000303b  mov     r14, [rsp+0B8h+pdwSizeOfUserDataOut]
0x180003043  mov     r9, [rsp+0B8h+pUserDataIn]
0x18000304b  mov     r8d, [rsp+0B8h+dwSizeOfConnectionDataIn]
0x180003053  mov     rdx, [rsp+0B8h+pConnectionDataIn]
0x18000305b  mov     [rsp+0B8h+var_78], rax
0x180003060  mov     eax, [rsp+0B8h+dwSizeOfUserDataIn]
0x180003067  mov     [rsp+0B8h+var_80], rbp
0x18000306c  mov     [rsp+0B8h+var_88], r14
0x180003071  mov     [rsp+0B8h+var_90], rsi
0x180003076  mov     dword ptr [rsp+0B8h+ReturnLength], eax
0x18000307a  mov     [rsi], r12
0x18000307d  call    EapMsChapv2GetProperiesAndPossibleIdentity
0x180003082  mov     ebx, eax
0x180003084  test    eax, eax
0x180003086  jz      short loc_1800030B5
0x180003088  mov     rcx, cs:WPP_GLOBAL_Control
0x18000308f  cmp     rcx, r13
0x180003092  jz      loc_180003167
0x180003098  mov     edx, 0B6h
0x18000309d  mov     r9d, eax
0x1800030a0  mov     rcx, [rcx+10h]
0x1800030a4  lea     r8, WPP_9b8b2f5616a63040265c7a7536bda72e_Traceguids
0x1800030ab  call    WPP_SF_d
0x1800030b0  jmp     loc_180003167
0x1800030b5  cmp     [rsp+0B8h+var_64], r12d
0x1800030ba  jz      loc_180003167
0x1800030c0  mov     rdi, [rsi]
0x1800030c3  lea     r8, [rsp+0B8h+var_50]
0x1800030c8  mov     [rsi], r12
0x1800030cb  mov     rdx, rdi
0x1800030ce  mov     rcx, r15
0x1800030d1  mov     [r14], r12d
0x1800030d4  call    EapMSChapv2GetUserCredentials
0x1800030d9  mov     ebx, eax
0x1800030db  test    eax, eax
0x1800030dd  jz      short loc_1800030F2
0x1800030df  mov     rcx, cs:WPP_GLOBAL_Control
0x1800030e6  cmp     rcx, r13
0x1800030e9  jz      short loc_180003167
0x1800030eb  mov     edx, 0B7h
0x1800030f0  jmp     short loc_18000309D
0x1800030f2  mov     rcx, rdi; hMem
0x1800030f5  call    cs:__imp_LocalFree
0x1800030fb  mov     rdi, [rsp+0B8h+var_50]
0x180003100  test    rbp, rbp
0x180003103  jz      short loc_180003134
0x180003105  lea     rdx, [rdi+20Eh]; LPCCH
0x18000310c  mov     r8, rbp
0x18000310f  lea     rcx, [rdi+0Ch]; lpMultiByteStr
0x180003113  call    GetIdentityFromUserName
0x180003118  mov     ebx, eax
0x18000311a  test    eax, eax
0x18000311c  jz      short loc_180003134
0x18000311e  mov     rcx, cs:WPP_GLOBAL_Control
0x180003125  cmp     rcx, r13
0x180003128  jz      short loc_180003167
0x18000312a  mov     edx, 0B8h
0x18000312f  jmp     loc_18000309D
0x180003134  mov     rcx, rdi
0x180003137  call    MschapV2UserPropBuffSize
0x18000313c  test    eax, eax
0x18000313e  jnz     short loc_18000315E
0x180003140  mov     ebx, 216h
0x180003145  mov     rcx, cs:WPP_GLOBAL_Control
0x18000314c  cmp     rcx, r13
0x18000314f  jz      short loc_180003167
0x180003151  mov     edx, 0B9h
0x180003156  mov     r9d, ebx
0x180003159  jmp     loc_1800030A0
0x18000315e  mov     [rsi], rdi
0x180003161  mov     rdi, r12
0x180003164  mov     [r14], eax
0x180003167  lea     rcx, g_criticalSection; lpCriticalSection
0x18000316e  call    cs:__imp_EnterCriticalSection
0x180003174  mov     eax, cs:g_dwDebuggingRefCount
0x18000317a  test    eax, eax
0x18000317c  jz      short loc_180003189
0x18000317e  add     eax, 0FFFFFFFFh
0x180003181  mov     cs:g_dwDebuggingRefCount, eax
0x180003187  jnz     short loc_1800031A9
0x180003189  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18000318f  cmp     ecx, 0FFFFFFFFh
0x180003192  jz      short loc_1800031A9
0x180003194  mov     edx, 4; dwFlags
0x180003199  call    cs:__imp_TraceDeregisterExA
0x18000319f  mov     cs:g_dwTraceId, 0FFFFFFFFh
0x1800031a9  lea     rcx, g_criticalSection; lpCriticalSection
0x1800031b0  call    cs:__imp_LeaveCriticalSection
0x1800031b6  mov     rcx, rdi; hMem
0x1800031b9  call    cs:__imp_LocalFree
0x1800031bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800031c6  cmp     rcx, r13
0x1800031c9  jz      short loc_1800031E3
0x1800031cb  mov     rcx, [rcx+10h]
0x1800031cf  lea     r8, WPP_9b8b2f5616a63040265c7a7536bda72e_Traceguids
0x1800031d6  mov     edx, 0BAh
0x1800031db  mov     r9d, ebx
0x1800031de  call    WPP_SF_d
0x1800031e3  mov     eax, ebx
0x1800031e5  add     rsp, 78h
0x1800031e9  pop     r15
0x1800031eb  pop     r14
0x1800031ed  pop     r13
0x1800031ef  pop     r12
0x1800031f1  pop     rdi
0x1800031f2  pop     rsi
0x1800031f3  pop     rbp
0x1800031f4  pop     rbx
0x1800031f5  retn
```
