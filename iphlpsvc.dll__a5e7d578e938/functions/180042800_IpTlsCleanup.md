# IpTlsCleanup

- ea: `0x180042800`
- end: `0x180042af1`
- name: `IpTlsCleanup`
- size: `753`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800036e0`
- `0x18003d874`

## callees

- `0x180001ae0`
- `0x180004c64`
- `0x180013580`
- `0x180042800`
- `0x180042af8`
- `0x180042e9c`
- `0x180054b78`
- `0x18005eb20`
- `0x18005f8a4`
- `0x180063214`
- `0x18006770c`
- `0x180076e88`

## import_xrefs

- `IPHLPAPI!CancelMibChangeNotify2` at `0x1800428a3`
- `IPHLPAPI!CancelMibChangeNotify2` at `0x1800428bb`
- `IPHLPAPI!CancelMibChangeNotify2` at `0x1800428a3`
- `IPHLPAPI!CancelMibChangeNotify2` at `0x1800428bb`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18004295e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180042971`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18004295e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180042971`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800429ed`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800429ed`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180042984`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180042984`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800429d2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800429d2`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180042ad4`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180042ad4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180042a00`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180042a00`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180042a3c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180042a3c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180042a4f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180042a4f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180042a27`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180042a27`
- `ext-ms-win-net-httpproxyext-l1-1-0!ProxyHelperClientDisconnectFromServer` at `0x180042a72`
- `ext-ms-win-net-httpproxyext-l1-1-0!ProxyHelperClientDisconnectFromServer` at `0x180042a72`

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
0x180042800  mov     [rsp+arg_0], rbx
0x180042805  mov     [rsp+arg_8], rbp
0x18004280a  push    rdi
0x18004280b  sub     rsp, 20h
0x18004280f  mov     eax, cs:g_IpTlsInterfaceListReferenceObject
0x180042815  mov     ebp, 1
0x18004281a  cmp     eax, ebp
0x18004281c  jz      loc_180042AE0
0x180042822  xor     eax, eax
0x180042824  lock cmpxchg cs:g_IpTlsCleanupRun, ebp
0x18004282c  jnz     loc_180042AE0
0x180042832  or      eax, 0FFFFFFFFh
0x180042835  lock xadd cs:g_IpTlsInterfaceListReferenceObject, eax
0x18004283d  dec     eax
0x18004283f  mov     cl, bpl
0x180042842  cmp     eax, ebp
0x180042844  setz    dil
0x180042848  call    StopDaEnabledNotification
0x18004284d  cmp     cs:g_IpTlsNLMNetworkChangeNotification, 0
0x180042855  jz      short loc_180042863
0x180042857  lea     rcx, g_IpTlsNLMNetworkChangeNotification
0x18004285e  call    DeregisterNLMNotification
0x180042863  cmp     cs:g_IpTlsNLMGlobalConnectivityChangeNotification, 0
0x18004286b  jz      short loc_180042879
0x18004286d  lea     rcx, g_IpTlsNLMGlobalConnectivityChangeNotification
0x180042874  call    DeregisterNLMNotification
0x180042879  mov     r8d, 20h ; ' '
0x18004287f  lea     rdx, off_1800C8328
0x180042886  lea     rcx, g_IpTlsProtocolState
0x18004288d  call    DeregisterNotificationHandlers
0x180042892  call    DeregisterWmiEventNotification
0x180042897  mov     rcx, cs:g_IpTlsIpv6AddressChangeNotification; NotificationHandle
0x18004289e  test    rcx, rcx
0x1800428a1  jz      short loc_1800428AF
0x1800428a3  call    cs:__imp_CancelMibChangeNotify2
0x1800428aa  nop     dword ptr [rax+rax+00h]
0x1800428af  mov     rcx, cs:g_IpTlsIpInterfaceChangeNotification; NotificationHandle
0x1800428b6  test    rcx, rcx
0x1800428b9  jz      short loc_1800428C7
0x1800428bb  call    cs:__imp_CancelMibChangeNotify2
0x1800428c2  nop     dword ptr [rax+rax+00h]
0x1800428c7  mov     rax, cs:g_IpTlsGlobalV6AddressList
0x1800428ce  mov     rbx, rax
0x1800428d1  lea     rcx, g_IpTlsGlobalV6AddressList
0x1800428d8  cmp     rax, rcx
0x1800428db  jz      short loc_180042912
0x1800428dd  mov     rax, [rbx]
0x1800428e0  cmp     [rax+8], rbx
0x1800428e4  jnz     loc_1800429C4
0x1800428ea  mov     rdx, [rbx+8]
0x1800428ee  cmp     [rdx], rbx
0x1800428f1  jnz     loc_1800429C4
0x1800428f7  mov     rcx, rbx
0x1800428fa  mov     [rdx], rax
0x1800428fd  mov     rbx, rax
0x180042900  mov     [rax+8], rdx
0x180042904  call    FREE
0x180042909  mov     rax, cs:g_IpTlsGlobalV6AddressList
0x180042910  jmp     short loc_1800428D1
0x180042912  mov     rcx, cs:g_IpTlsConfigChangeLock
0x180042919  mov     cs:g_IpTlsGlobalV6AddressCount, 0
0x180042923  call    IpTlsAcquireLock
0x180042928  lea     rbx, g_IpTlsInterfaceListHead
0x18004292f  cmp     cs:g_IpTlsInterfaceListHead, rbx
0x180042936  jz      short loc_18004296A
0x180042938  mov     rcx, cs:g_IpTlsInterfaceListLock
0x18004293f  call    IpTlsAcquireLock
0x180042944  mov     rcx, cs:g_IpTlsInterfaceListHead
0x18004294b  cmp     rcx, rbx
0x18004294e  jz      short loc_180042957
0x180042950  call    IpTlsDeleteInterface
0x180042955  jmp     short loc_180042944
0x180042957  mov     rcx, cs:g_IpTlsInterfaceListLock; hMutex
0x18004295e  call    cs:__imp_ReleaseMutex
0x180042965  nop     dword ptr [rax+rax+00h]
0x18004296a  mov     rcx, cs:g_IpTlsConfigChangeLock; hMutex
0x180042971  call    cs:__imp_ReleaseMutex
0x180042978  nop     dword ptr [rax+rax+00h]
0x18004297d  lea     rcx, g_IpTlsConnectedNetworkListLock; lpCriticalSection
0x180042984  call    cs:__imp_EnterCriticalSection
0x18004298b  nop     dword ptr [rax+rax+00h]
0x180042990  lea     rbx, g_IpTlsConnectedNetworkList
0x180042997  mov     rcx, cs:g_IpTlsConnectedNetworkList
0x18004299e  cmp     rcx, rbx
0x1800429a1  jz      short loc_1800429CB
0x1800429a3  cmp     [rcx+8], rbx
0x1800429a7  jnz     short loc_1800429C4
0x1800429a9  mov     rax, [rcx]
0x1800429ac  cmp     [rax+8], rcx
0x1800429b0  jnz     short loc_1800429C4
0x1800429b2  mov     cs:g_IpTlsConnectedNetworkList, rax
0x1800429b9  mov     [rax+8], rbx
0x1800429bd  call    FREE
0x1800429c2  jmp     short loc_180042997
0x1800429c4  mov     ecx, 3
0x1800429c9  int     29h; Win8: RtlFailFast(ecx)
0x1800429cb  lea     rcx, g_IpTlsConnectedNetworkListLock; lpCriticalSection
0x1800429d2  call    cs:__imp_LeaveCriticalSection
0x1800429d9  nop     dword ptr [rax+rax+00h]
0x1800429de  test    dil, dil
0x1800429e1  jnz     short loc_1800429F9
0x1800429e3  mov     rcx, cs:g_IpTlsInterfaceListEmptyEvent; hHandle
0x1800429ea  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800429ed  call    cs:__imp_WaitForSingleObject
0x1800429f4  nop     dword ptr [rax+rax+00h]
0x1800429f9  mov     rcx, cs:g_IpTlsInterfaceListEmptyEvent; hObject
0x180042a00  call    cs:__imp_CloseHandle
0x180042a07  nop     dword ptr [rax+rax+00h]
0x180042a0c  mov     rcx, cs:g_IpTlsCorpConnectivityTimer; pti
0x180042a13  test    rcx, rcx
0x180042a16  jz      short loc_180042A66
0x180042a18  xor     r9d, r9d; msWindowLength
0x180042a1b  mov     cs:g_IpTlsCorpConnectivityTimerArmed, 0
0x180042a22  xor     r8d, r8d; msPeriod
0x180042a25  xor     edx, edx; pftDueTime
0x180042a27  call    cs:__imp_SetThreadpoolTimer
0x180042a2e  nop     dword ptr [rax+rax+00h]
0x180042a33  mov     rcx, cs:g_IpTlsCorpConnectivityTimer; pti
0x180042a3a  mov     edx, ebp; fCancelPendingCallbacks
0x180042a3c  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180042a43  nop     dword ptr [rax+rax+00h]
0x180042a48  mov     rcx, cs:g_IpTlsCorpConnectivityTimer; pti
0x180042a4f  call    cs:__imp_CloseThreadpoolTimer
0x180042a56  nop     dword ptr [rax+rax+00h]
0x180042a5b  mov     cs:g_IpTlsCorpConnectivityTimer, 0
0x180042a66  mov     rcx, cs:g_IpTlsProxyMgrRpcHandle
0x180042a6d  test    rcx, rcx
0x180042a70  jz      short loc_180042A89
0x180042a72  call    cs:__imp_ProxyHelperClientDisconnectFromServer
0x180042a79  nop     dword ptr [rax+rax+00h]
0x180042a7e  mov     cs:g_IpTlsProxyMgrRpcHandle, 0
0x180042a89  mov     ecx, 4
0x180042a8e  call    UninitializePerfmonCounters
0x180042a93  call    ShutdownHttpClient
0x180042a98  call    ShutdownHttpServer
0x180042a9d  lea     rcx, g_IpTlsNLMNotificationLock
0x180042aa4  call    UninitializeLock
0x180042aa9  lea     rcx, g_IpTlsConfigChangeLock
0x180042ab0  call    UninitializeLock
0x180042ab5  lea     rcx, g_IpTlsInterfaceListLock
0x180042abc  call    UninitializeLock
0x180042ac1  lea     rcx, g_IpTlsDeletedInterfaceListLock
0x180042ac8  call    UninitializeLock
0x180042acd  lea     rcx, g_IpTlsConnectedNetworkListLock; lpCriticalSection
0x180042ad4  call    cs:__imp_DeleteCriticalSection
0x180042adb  nop     dword ptr [rax+rax+00h]
0x180042ae0  mov     rbx, [rsp+28h+arg_0]
0x180042ae5  mov     rbp, [rsp+28h+arg_8]
0x180042aea  add     rsp, 20h
0x180042aee  pop     rdi
0x180042aef  retn
```
