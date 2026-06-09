# ScPolicyServiceMain

- ea: `0x18001b5c0`
- end: `0x18001b800`
- name: `ScPolicyServiceMain`
- size: `576`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800154f4`
- `0x180018f14`
- `0x18001af6c`
- `0x18001b5c0`
- `0x18001b808`
- `0x180021930`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x18001b663`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x18001b663`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001b69c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001b69c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001b6b8`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001b6b8`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18001b5f4`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18001b60a`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18001b5f4`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18001b60a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b675`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b675`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18001b6db`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18001b6db`
- `WTSAPI32!WTSEnumerateSessionsW` at `0x18001b74b`
- `WTSAPI32!WTSEnumerateSessionsW` at `0x18001b74b`
- `WTSAPI32!WTSFreeMemory` at `0x18001b79a`
- `WTSAPI32!WTSFreeMemory` at `0x18001b79a`

## pseudocode

```c
__int64 ScPolicyServiceMain()
{
  struct _TP_CLEANUP_GROUP *ThreadpoolCleanupGroup; // rax
  __int64 result; // rax
  SERVICE_STATUS_HANDLE v2; // rax
  DWORD v3; // ebx
  DWORD i; // ecx
  DWORD SessionId; // r8d
  PWTS_SESSION_INFOW ppSessionInfo; // [rsp+30h] [rbp-18h] BYREF
  DWORD pCount; // [rsp+60h] [rbp+18h] BYREF
  int v8; // [rsp+68h] [rbp+20h] BYREF

  v8 = 0;
  ppSessionInfo = 0;
  pCount = 0;
  *(_OWORD *)&g_ScPolicyStatus.dwServiceType = 0;
  *(_OWORD *)&g_ScPolicyStatus.dwWin32ExitCode = 0;
  InitializeCriticalSection(&g_csScPolicyList);
  g_fScPolicyInitListCS = 1;
  InitializeCriticalSection(&g_csInactiveScPolicyList);
  g_fInactiveScPolicyListCS = 1;
  pcbe.Version = 3;
  pcbe.Pool = 0;
  pcbe.CleanupGroup = 0;
  pcbe.CleanupGroupCancelCallback = 0;
  *(_OWORD *)&pcbe.RaceDll = 0;
  pcbe.FinalizationCallback = 0;
  pcbe.u.Flags = 0;
  pcbe.CallbackPriority = TP_CALLBACK_PRIORITY_NORMAL;
  pcbe.Size = 72;
  dword_1800315B0 = 1;
  ThreadpoolCleanupGroup = CreateThreadpoolCleanupGroup();
  ptpcg = ThreadpoolCleanupGroup;
  if ( !ThreadpoolCleanupGroup )
    goto LABEL_2;
  pcbe.CleanupGroup = ThreadpoolCleanupGroup;
  pcbe.CleanupGroupCancelCallback = 0;
  pcbe.RaceDll = (PVOID)g_hInst;
  g_hScPolicyHeap = GetProcessHeap();
  if ( !g_hScPolicyHeap )
    goto LABEL_2;
  g_hScPolicyStopEvent = CreateEventW(0, 1, 0, 0);
  if ( !g_hScPolicyStopEvent )
    goto LABEL_2;
  v2 = RegisterServiceCtrlHandlerExW(L"SCPolicySvc", ScPolicyServiceHandlerEx, 0);
  g_hScPolicyStatus = v2;
  if ( !v2 )
    goto LABEL_2;
  g_ScPolicyStatus.dwServiceType = 32;
  LODWORD(result) = CommonReportServiceStatus(&g_ScPolicyStatus, v2, 0);
  if ( (_DWORD)result )
    return ScPolicyTeardownServer((unsigned int)result);
  LODWORD(result) = ScPolicyGetPolicyOption(&v8);
  if ( (_DWORD)result || !v8 )
    return ScPolicyTeardownServer((unsigned int)result);
  if ( !WTSEnumerateSessionsW(0, 0, 1u, &ppSessionInfo, &pCount) )
  {
LABEL_2:
    LODWORD(result) = GetLastError();
    return ScPolicyTeardownServer((unsigned int)result);
  }
  v3 = 0;
  for ( i = pCount; v3 < i; ++v3 )
  {
    SessionId = ppSessionInfo[v3].SessionId;
    if ( SessionId && (ppSessionInfo[v3].State & 0xFFFFFFFB) == 0 )
    {
      ScPolicyCheckForSmartcardAuth(SessionId, 1);
      i = pCount;
    }
  }
  WTSFreeMemory(ppSessionInfo);
  LODWORD(result) = CommonRegisterStopCallback(
                      &g_hScPolicyRegisteredWait,
                      L"SCPolicySvc",
                      g_hScPolicyStopEvent,
                      ScPolicyTerminationNotify);
  if ( (_DWORD)result )
    return ScPolicyTeardownServer((unsigned int)result);
  result = CommonReportServiceStatus(&g_ScPolicyStatus, g_hScPolicyStatus, 0);
  if ( (_DWORD)result )
    return ScPolicyTeardownServer((unsigned int)result);
  return result;
}

```

## disassembly

```asm
0x18001b5c0  mov     rax, rsp
0x18001b5c3  mov     [rax+8], rbx
0x18001b5c7  mov     [rax+10h], rsi
0x18001b5cb  push    rdi
0x18001b5cc  sub     rsp, 40h
0x18001b5d0  xor     edi, edi
0x18001b5d2  mov     [rax+20h], edi
0x18001b5d5  mov     [rax-18h], rdi
0x18001b5d9  mov     [rax+18h], edi
0x18001b5dc  xorps   xmm0, xmm0
0x18001b5df  movups  xmmword ptr cs:g_ScPolicyStatus.dwServiceType, xmm0
0x18001b5e6  movups  xmmword ptr cs:g_ScPolicyStatus.dwWin32ExitCode, xmm0
0x18001b5ed  lea     rcx, g_csScPolicyList; lpCriticalSection
0x18001b5f4  call    cs:__imp_InitializeCriticalSection
0x18001b5fa  lea     esi, [rdi+1]
0x18001b5fd  mov     cs:g_fScPolicyInitListCS, esi
0x18001b603  lea     rcx, g_csInactiveScPolicyList; lpCriticalSection
0x18001b60a  call    cs:__imp_InitializeCriticalSection
0x18001b610  mov     cs:g_fInactiveScPolicyListCS, esi
0x18001b616  mov     cs:pcbe.Version, 3
0x18001b620  mov     cs:pcbe.Pool, rdi
0x18001b627  mov     cs:pcbe.CleanupGroup, rdi
0x18001b62e  mov     cs:pcbe.CleanupGroupCancelCallback, rdi
0x18001b635  xorps   xmm0, xmm0
0x18001b638  movdqa  xmmword ptr cs:pcbe.RaceDll, xmm0
0x18001b640  mov     cs:pcbe.FinalizationCallback, rdi
0x18001b647  mov     dword ptr cs:pcbe.u, edi
0x18001b64d  mov     cs:pcbe.CallbackPriority, esi
0x18001b653  mov     cs:pcbe.Size, 48h ; 'H'
0x18001b65d  mov     cs:dword_1800315B0, esi
0x18001b663  call    cs:__imp_CreateThreadpoolCleanupGroup
0x18001b669  mov     cs:ptpcg, rax
0x18001b670  test    rax, rax
0x18001b673  jnz     short loc_18001B680
0x18001b675  call    cs:__imp_GetLastError
0x18001b67b  jmp     loc_18001B7E9
0x18001b680  mov     cs:pcbe.CleanupGroup, rax
0x18001b687  mov     cs:pcbe.CleanupGroupCancelCallback, rdi
0x18001b68e  mov     rax, cs:g_hInst
0x18001b695  mov     cs:pcbe.RaceDll, rax
0x18001b69c  call    cs:__imp_GetProcessHeap
0x18001b6a2  mov     cs:g_hScPolicyHeap, rax
0x18001b6a9  test    rax, rax
0x18001b6ac  jz      short loc_18001B675
0x18001b6ae  xor     r9d, r9d; lpName
0x18001b6b1  xor     r8d, r8d; bInitialState
0x18001b6b4  mov     edx, esi; bManualReset
0x18001b6b6  xor     ecx, ecx; lpEventAttributes
0x18001b6b8  call    cs:__imp_CreateEventW
0x18001b6be  mov     cs:g_hScPolicyStopEvent, rax
0x18001b6c5  test    rax, rax
0x18001b6c8  jz      short loc_18001B675
0x18001b6ca  xor     r8d, r8d; lpContext
0x18001b6cd  lea     rdx, ScPolicyServiceHandlerEx; lpHandlerProc
0x18001b6d4  lea     rcx, aScpolicysvc; "SCPolicySvc"
0x18001b6db  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x18001b6e1  mov     cs:g_hScPolicyStatus, rax
0x18001b6e8  test    rax, rax
0x18001b6eb  jz      short loc_18001B675
0x18001b6ed  mov     cs:g_ScPolicyStatus.dwServiceType, 20h ; ' '
0x18001b6f7  mov     dword ptr [rsp+48h+pCount], edi; int
0x18001b6fb  xor     r9d, r9d
0x18001b6fe  lea     r8d, [r9+2]
0x18001b702  mov     rdx, rax; hServiceStatus
0x18001b705  lea     rcx, g_ScPolicyStatus; lpServiceStatus
0x18001b70c  call    CommonReportServiceStatus
0x18001b711  test    eax, eax
0x18001b713  jnz     loc_18001B7E9
0x18001b719  lea     rcx, [rsp+48h+arg_18]
0x18001b71e  call    ScPolicyGetPolicyOption
0x18001b723  test    eax, eax
0x18001b725  jnz     loc_18001B7E9
0x18001b72b  cmp     [rsp+48h+arg_18], edi
0x18001b72f  jz      loc_18001B7E9
0x18001b735  lea     rax, [rsp+48h+arg_10]
0x18001b73a  mov     [rsp+48h+pCount], rax; pCount
0x18001b73f  lea     r9, [rsp+48h+ppSessionInfo]; ppSessionInfo
0x18001b744  mov     r8d, esi; Version
0x18001b747  xor     edx, edx; Reserved
0x18001b749  xor     ecx, ecx; hServer
0x18001b74b  call    cs:__imp_WTSEnumerateSessionsW
0x18001b751  test    eax, eax
0x18001b753  jz      loc_18001B675
0x18001b759  mov     ebx, edi
0x18001b75b  mov     ecx, [rsp+48h+arg_10]
0x18001b75f  test    ecx, ecx
0x18001b761  jz      short loc_18001B795
0x18001b763  mov     eax, ebx
0x18001b765  lea     rdx, [rax+rax*2]
0x18001b769  mov     rax, [rsp+48h+ppSessionInfo]
0x18001b76e  mov     r8d, [rax+rdx*8]
0x18001b772  test    r8d, r8d
0x18001b775  jz      short loc_18001B78F
0x18001b777  test    dword ptr [rax+rdx*8+10h], 0FFFFFFFBh
0x18001b77f  jnz     short loc_18001B78F
0x18001b781  mov     edx, esi
0x18001b783  mov     ecx, r8d
0x18001b786  call    ScPolicyCheckForSmartcardAuth
0x18001b78b  mov     ecx, [rsp+48h+arg_10]
0x18001b78f  add     ebx, esi
0x18001b791  cmp     ebx, ecx
0x18001b793  jb      short loc_18001B763
0x18001b795  mov     rcx, [rsp+48h+ppSessionInfo]; pMemory
0x18001b79a  call    cs:__imp_WTSFreeMemory
0x18001b7a0  lea     r9, ScPolicyTerminationNotify
0x18001b7a7  mov     r8, cs:g_hScPolicyStopEvent
0x18001b7ae  lea     rdx, aScpolicysvc; "SCPolicySvc"
0x18001b7b5  lea     rcx, g_hScPolicyRegisteredWait
0x18001b7bc  call    CommonRegisterStopCallback
0x18001b7c1  test    eax, eax
0x18001b7c3  jnz     short loc_18001B7E9
0x18001b7c5  mov     dword ptr [rsp+48h+pCount], edi; int
0x18001b7c9  xor     r9d, r9d
0x18001b7cc  lea     r8d, [rax+4]
0x18001b7d0  mov     rdx, cs:g_hScPolicyStatus; hServiceStatus
0x18001b7d7  lea     rcx, g_ScPolicyStatus; lpServiceStatus
0x18001b7de  call    CommonReportServiceStatus
0x18001b7e3  test    eax, eax
0x18001b7e5  jnz     short loc_18001B7E9
0x18001b7e7  jmp     short loc_18001B7F0
0x18001b7e9  mov     ecx, eax
0x18001b7eb  call    ScPolicyTeardownServer
0x18001b7f0  mov     rbx, [rsp+48h+arg_0]
0x18001b7f5  mov     rsi, [rsp+48h+arg_8]
0x18001b7fa  add     rsp, 40h
0x18001b7fe  pop     rdi
0x18001b7ff  retn
```
