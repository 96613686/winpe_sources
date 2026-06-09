# IpTlsCleanup

- ea: `0x180042840`
- end: `0x180042b31`
- name: `IpTlsCleanup`
- size: `753`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800036d0`
- `0x18003d864`

## callees

- `0x180001ad0`
- `0x180004c54`
- `0x180013570`
- `0x180042840`
- `0x180042b38`
- `0x180042edc`
- `0x180054b58`
- `0x18005eb00`
- `0x18005f884`
- `0x1800631f4`
- `0x1800676ec`
- `0x180076e68`

## import_xrefs

- `IPHLPAPI!CancelMibChangeNotify2` at `0x1800428e3`
- `IPHLPAPI!CancelMibChangeNotify2` at `0x1800428fb`
- `IPHLPAPI!CancelMibChangeNotify2` at `0x1800428e3`
- `IPHLPAPI!CancelMibChangeNotify2` at `0x1800428fb`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18004299e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800429b1`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18004299e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800429b1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180042a2d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180042a2d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800429c4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800429c4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180042a12`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180042a12`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180042b14`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180042b14`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180042a40`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180042a40`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180042a7c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180042a7c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180042a8f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180042a8f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180042a67`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180042a67`
- `ext-ms-win-net-httpproxyext-l1-1-0!ProxyHelperClientDisconnectFromServer` at `0x180042ab2`
- `ext-ms-win-net-httpproxyext-l1-1-0!ProxyHelperClientDisconnectFromServer` at `0x180042ab2`

## pseudocode

```c
void __fastcall IpTlsCleanup(__int64 a1)
{
  bool v1; // di
  LPVOID *v2; // rax
  _QWORD *v3; // rbx
  _QWORD *v4; // rax
  _QWORD *v5; // rdx
  _QWORD *v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // rax

  if ( g_IpTlsInterfaceListReferenceObject != 1 && !_InterlockedCompareExchange(&g_IpTlsCleanupRun, 1, 0) )
  {
    LOBYTE(a1) = 1;
    v1 = _InterlockedDecrement(&g_IpTlsInterfaceListReferenceObject) == 1;
    StopDaEnabledNotification(a1);
    if ( g_IpTlsNLMNetworkChangeNotification )
      DeregisterNLMNotification(&g_IpTlsNLMNetworkChangeNotification);
    if ( g_IpTlsNLMGlobalConnectivityChangeNotification )
      DeregisterNLMNotification(&g_IpTlsNLMGlobalConnectivityChangeNotification);
    DeregisterNotificationHandlers(&g_IpTlsProtocolState, &off_1800C8328, 32);
    DeregisterWmiEventNotification();
    if ( g_IpTlsIpv6AddressChangeNotification )
      CancelMibChangeNotify2(g_IpTlsIpv6AddressChangeNotification);
    if ( g_IpTlsIpInterfaceChangeNotification )
      CancelMibChangeNotify2(g_IpTlsIpInterfaceChangeNotification);
    v2 = (LPVOID *)g_IpTlsGlobalV6AddressList;
    v3 = g_IpTlsGlobalV6AddressList;
    while ( v2 != &g_IpTlsGlobalV6AddressList )
    {
      v4 = (_QWORD *)*v3;
      if ( *(_QWORD **)(*v3 + 8LL) != v3 || (v5 = (_QWORD *)v3[1], (_QWORD *)*v5 != v3) )
LABEL_26:
        __fastfail(3u);
      v6 = v3;
      *v5 = v4;
      v3 = v4;
      v4[1] = v5;
      FREE(v6);
      v2 = (LPVOID *)g_IpTlsGlobalV6AddressList;
    }
    g_IpTlsGlobalV6AddressCount = 0;
    IpTlsAcquireLock(g_IpTlsConfigChangeLock);
    if ( (__int64 *)g_IpTlsInterfaceListHead != &g_IpTlsInterfaceListHead )
    {
      IpTlsAcquireLock(g_IpTlsInterfaceListLock);
      while ( (__int64 *)g_IpTlsInterfaceListHead != &g_IpTlsInterfaceListHead )
        IpTlsDeleteInterface();
      ReleaseMutex(g_IpTlsInterfaceListLock);
    }
    ReleaseMutex(g_IpTlsConfigChangeLock);
    EnterCriticalSection(&g_IpTlsConnectedNetworkListLock);
    while ( 1 )
    {
      v7 = g_IpTlsConnectedNetworkList;
      if ( (__int64 *)g_IpTlsConnectedNetworkList == &g_IpTlsConnectedNetworkList )
        break;
      if ( *(__int64 **)(g_IpTlsConnectedNetworkList + 8) != &g_IpTlsConnectedNetworkList )
        goto LABEL_26;
      v8 = *(_QWORD *)g_IpTlsConnectedNetworkList;
      if ( *(_QWORD *)(*(_QWORD *)g_IpTlsConnectedNetworkList + 8LL) != g_IpTlsConnectedNetworkList )
        goto LABEL_26;
      g_IpTlsConnectedNetworkList = *(_QWORD *)g_IpTlsConnectedNetworkList;
      *(_QWORD *)(v8 + 8) = &g_IpTlsConnectedNetworkList;
      FREE(v7);
    }
    LeaveCriticalSection(&g_IpTlsConnectedNetworkListLock);
    if ( !v1 )
      WaitForSingleObject(g_IpTlsInterfaceListEmptyEvent, 0xFFFFFFFF);
    CloseHandle(g_IpTlsInterfaceListEmptyEvent);
    if ( g_IpTlsCorpConnectivityTimer )
    {
      g_IpTlsCorpConnectivityTimerArmed = 0;
      SetThreadpoolTimer(g_IpTlsCorpConnectivityTimer, 0, 0, 0);
      WaitForThreadpoolTimerCallbacks(g_IpTlsCorpConnectivityTimer, 1);
      CloseThreadpoolTimer(g_IpTlsCorpConnectivityTimer);
      g_IpTlsCorpConnectivityTimer = 0;
    }
    if ( g_IpTlsProxyMgrRpcHandle )
    {
      ProxyHelperClientDisconnectFromServer();
      g_IpTlsProxyMgrRpcHandle = 0;
    }
    UninitializePerfmonCounters(4);
    ShutdownHttpClient();
    ShutdownHttpServer();
    UninitializeLock(&g_IpTlsNLMNotificationLock);
    UninitializeLock(&g_IpTlsConfigChangeLock);
    UninitializeLock(&g_IpTlsInterfaceListLock);
    UninitializeLock(&g_IpTlsDeletedInterfaceListLock);
    DeleteCriticalSection(&g_IpTlsConnectedNetworkListLock);
  }
}

```

## disassembly

```asm
0x180042840  mov     [rsp+arg_0], rbx
0x180042845  mov     [rsp+arg_8], rbp
0x18004284a  push    rdi
0x18004284b  sub     rsp, 20h
0x18004284f  mov     eax, cs:g_IpTlsInterfaceListReferenceObject
0x180042855  mov     ebp, 1
0x18004285a  cmp     eax, ebp
0x18004285c  jz      loc_180042B20
0x180042862  xor     eax, eax
0x180042864  lock cmpxchg cs:g_IpTlsCleanupRun, ebp
0x18004286c  jnz     loc_180042B20
0x180042872  or      eax, 0FFFFFFFFh
0x180042875  lock xadd cs:g_IpTlsInterfaceListReferenceObject, eax
0x18004287d  dec     eax
0x18004287f  mov     cl, bpl
0x180042882  cmp     eax, ebp
0x180042884  setz    dil
0x180042888  call    StopDaEnabledNotification
0x18004288d  cmp     cs:g_IpTlsNLMNetworkChangeNotification, 0
0x180042895  jz      short loc_1800428A3
0x180042897  lea     rcx, g_IpTlsNLMNetworkChangeNotification
0x18004289e  call    DeregisterNLMNotification
0x1800428a3  cmp     cs:g_IpTlsNLMGlobalConnectivityChangeNotification, 0
0x1800428ab  jz      short loc_1800428B9
0x1800428ad  lea     rcx, g_IpTlsNLMGlobalConnectivityChangeNotification
0x1800428b4  call    DeregisterNLMNotification
0x1800428b9  mov     r8d, 20h ; ' '
0x1800428bf  lea     rdx, off_1800C8328
0x1800428c6  lea     rcx, g_IpTlsProtocolState
0x1800428cd  call    DeregisterNotificationHandlers
0x1800428d2  call    DeregisterWmiEventNotification
0x1800428d7  mov     rcx, cs:g_IpTlsIpv6AddressChangeNotification; NotificationHandle
0x1800428de  test    rcx, rcx
0x1800428e1  jz      short loc_1800428EF
0x1800428e3  call    cs:__imp_CancelMibChangeNotify2
0x1800428ea  nop     dword ptr [rax+rax+00h]
0x1800428ef  mov     rcx, cs:g_IpTlsIpInterfaceChangeNotification; NotificationHandle
0x1800428f6  test    rcx, rcx
0x1800428f9  jz      short loc_180042907
0x1800428fb  call    cs:__imp_CancelMibChangeNotify2
0x180042902  nop     dword ptr [rax+rax+00h]
0x180042907  mov     rax, cs:g_IpTlsGlobalV6AddressList
0x18004290e  mov     rbx, rax
0x180042911  lea     rcx, g_IpTlsGlobalV6AddressList
0x180042918  cmp     rax, rcx
0x18004291b  jz      short loc_180042952
0x18004291d  mov     rax, [rbx]
0x180042920  cmp     [rax+8], rbx
0x180042924  jnz     loc_180042A04
0x18004292a  mov     rdx, [rbx+8]
0x18004292e  cmp     [rdx], rbx
0x180042931  jnz     loc_180042A04
0x180042937  mov     rcx, rbx
0x18004293a  mov     [rdx], rax
0x18004293d  mov     rbx, rax
0x180042940  mov     [rax+8], rdx
0x180042944  call    FREE
0x180042949  mov     rax, cs:g_IpTlsGlobalV6AddressList
0x180042950  jmp     short loc_180042911
0x180042952  mov     rcx, cs:g_IpTlsConfigChangeLock
0x180042959  mov     cs:g_IpTlsGlobalV6AddressCount, 0
0x180042963  call    IpTlsAcquireLock
0x180042968  lea     rbx, g_IpTlsInterfaceListHead
0x18004296f  cmp     cs:g_IpTlsInterfaceListHead, rbx
0x180042976  jz      short loc_1800429AA
0x180042978  mov     rcx, cs:g_IpTlsInterfaceListLock
0x18004297f  call    IpTlsAcquireLock
0x180042984  mov     rcx, cs:g_IpTlsInterfaceListHead
0x18004298b  cmp     rcx, rbx
0x18004298e  jz      short loc_180042997
0x180042990  call    IpTlsDeleteInterface
0x180042995  jmp     short loc_180042984
0x180042997  mov     rcx, cs:g_IpTlsInterfaceListLock; hMutex
0x18004299e  call    cs:__imp_ReleaseMutex
0x1800429a5  nop     dword ptr [rax+rax+00h]
0x1800429aa  mov     rcx, cs:g_IpTlsConfigChangeLock; hMutex
0x1800429b1  call    cs:__imp_ReleaseMutex
0x1800429b8  nop     dword ptr [rax+rax+00h]
0x1800429bd  lea     rcx, g_IpTlsConnectedNetworkListLock; lpCriticalSection
0x1800429c4  call    cs:__imp_EnterCriticalSection
0x1800429cb  nop     dword ptr [rax+rax+00h]
0x1800429d0  lea     rbx, g_IpTlsConnectedNetworkList
0x1800429d7  mov     rcx, cs:g_IpTlsConnectedNetworkList
0x1800429de  cmp     rcx, rbx
0x1800429e1  jz      short loc_180042A0B
0x1800429e3  cmp     [rcx+8], rbx
0x1800429e7  jnz     short loc_180042A04
0x1800429e9  mov     rax, [rcx]
0x1800429ec  cmp     [rax+8], rcx
0x1800429f0  jnz     short loc_180042A04
0x1800429f2  mov     cs:g_IpTlsConnectedNetworkList, rax
0x1800429f9  mov     [rax+8], rbx
0x1800429fd  call    FREE
0x180042a02  jmp     short loc_1800429D7
0x180042a04  mov     ecx, 3
0x180042a09  int     29h; Win8: RtlFailFast(ecx)
0x180042a0b  lea     rcx, g_IpTlsConnectedNetworkListLock; lpCriticalSection
0x180042a12  call    cs:__imp_LeaveCriticalSection
0x180042a19  nop     dword ptr [rax+rax+00h]
0x180042a1e  test    dil, dil
0x180042a21  jnz     short loc_180042A39
0x180042a23  mov     rcx, cs:g_IpTlsInterfaceListEmptyEvent; hHandle
0x180042a2a  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180042a2d  call    cs:__imp_WaitForSingleObject
0x180042a34  nop     dword ptr [rax+rax+00h]
0x180042a39  mov     rcx, cs:g_IpTlsInterfaceListEmptyEvent; hObject
0x180042a40  call    cs:__imp_CloseHandle
0x180042a47  nop     dword ptr [rax+rax+00h]
0x180042a4c  mov     rcx, cs:g_IpTlsCorpConnectivityTimer; pti
0x180042a53  test    rcx, rcx
0x180042a56  jz      short loc_180042AA6
0x180042a58  xor     r9d, r9d; msWindowLength
0x180042a5b  mov     cs:g_IpTlsCorpConnectivityTimerArmed, 0
0x180042a62  xor     r8d, r8d; msPeriod
0x180042a65  xor     edx, edx; pftDueTime
0x180042a67  call    cs:__imp_SetThreadpoolTimer
0x180042a6e  nop     dword ptr [rax+rax+00h]
0x180042a73  mov     rcx, cs:g_IpTlsCorpConnectivityTimer; pti
0x180042a7a  mov     edx, ebp; fCancelPendingCallbacks
0x180042a7c  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180042a83  nop     dword ptr [rax+rax+00h]
0x180042a88  mov     rcx, cs:g_IpTlsCorpConnectivityTimer; pti
0x180042a8f  call    cs:__imp_CloseThreadpoolTimer
0x180042a96  nop     dword ptr [rax+rax+00h]
0x180042a9b  mov     cs:g_IpTlsCorpConnectivityTimer, 0
0x180042aa6  mov     rcx, cs:g_IpTlsProxyMgrRpcHandle
0x180042aad  test    rcx, rcx
0x180042ab0  jz      short loc_180042AC9
0x180042ab2  call    cs:__imp_ProxyHelperClientDisconnectFromServer
0x180042ab9  nop     dword ptr [rax+rax+00h]
0x180042abe  mov     cs:g_IpTlsProxyMgrRpcHandle, 0
0x180042ac9  mov     ecx, 4
0x180042ace  call    UninitializePerfmonCounters
0x180042ad3  call    ShutdownHttpClient
0x180042ad8  call    ShutdownHttpServer
0x180042add  lea     rcx, g_IpTlsNLMNotificationLock
0x180042ae4  call    UninitializeLock
0x180042ae9  lea     rcx, g_IpTlsConfigChangeLock
0x180042af0  call    UninitializeLock
0x180042af5  lea     rcx, g_IpTlsInterfaceListLock
0x180042afc  call    UninitializeLock
0x180042b01  lea     rcx, g_IpTlsDeletedInterfaceListLock
0x180042b08  call    UninitializeLock
0x180042b0d  lea     rcx, g_IpTlsConnectedNetworkListLock; lpCriticalSection
0x180042b14  call    cs:__imp_DeleteCriticalSection
0x180042b1b  nop     dword ptr [rax+rax+00h]
0x180042b20  mov     rbx, [rsp+28h+arg_0]
0x180042b25  mov     rbp, [rsp+28h+arg_8]
0x180042b2a  add     rsp, 20h
0x180042b2e  pop     rdi
0x180042b2f  retn
```
