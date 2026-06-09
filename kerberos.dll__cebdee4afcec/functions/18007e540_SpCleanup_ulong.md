# SpCleanup(ulong)

- ea: `0x18007e540`
- end: `0x18007ea95`
- name: `?SpCleanup@@YAJK@Z`
- size: `1365`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `30`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, installer_update`

## callers

- `0x1800802c0`

## callees

- `0x1800068d0`
- `0x1800069a0`
- `0x1800069e0`
- `0x180006a2c`
- `0x180011690`
- `0x180016600`
- `0x1800246c0`
- `0x18002cea0`
- `0x18002d190`
- `0x180030b50`
- `0x180035bf0`
- `0x18006d958`
- `0x180070a50`
- `0x18007108c`
- `0x18007aa48`
- `0x18007e540`
- `0x180080040`
- `0x18008a61c`
- `0x1800908ec`
- `0x18009a6ec`
- `0x1800b4528`
- `0x1800b4630`
- `0x1800b56c4`
- `0x1800c365c`
- `0x1800d90b8`
- `0x1800dc5e0`
- `0x1800dcc98`
- `0x1800ddb24`
- `0x1800df0a0`
- `0x1800f0890`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007e6df`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007ea66`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007e6df`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007ea66`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007e948`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007e948`
- `ntdll!RtlDeleteResource` at `0x18007e60d`
- `ntdll!RtlDeleteResource` at `0x18007e671`
- `ntdll!RtlDeleteResource` at `0x18007e6c6`
- `ntdll!RtlDeleteResource` at `0x18007e8bb`
- `ntdll!RtlDeleteResource` at `0x18007ea2d`
- `ntdll!RtlDeleteResource` at `0x18007ea59`
- `ntdll!RtlDeleteResource` at `0x18007e60d`
- `ntdll!RtlDeleteResource` at `0x18007e671`
- `ntdll!RtlDeleteResource` at `0x18007e6c6`
- `ntdll!RtlDeleteResource` at `0x18007e8bb`
- `ntdll!RtlDeleteResource` at `0x18007ea2d`
- `ntdll!RtlDeleteResource` at `0x18007ea59`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x18007e5eb`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x18007e5eb`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x18007e5dc`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x18007e5dc`
- `ntdll!RtlDeleteTimerQueue` at `0x18007e689`
- `ntdll!RtlDeleteTimerQueue` at `0x18007e689`
- `ntdll!RtlReleaseResource` at `0x18007e600`
- `ntdll!RtlReleaseResource` at `0x18007e664`
- `ntdll!RtlReleaseResource` at `0x18007e600`
- `ntdll!RtlReleaseResource` at `0x18007e664`
- `ntdll!RtlAcquireResourceExclusive` at `0x18007e5bf`
- `ntdll!RtlAcquireResourceExclusive` at `0x18007e633`
- `ntdll!RtlAcquireResourceExclusive` at `0x18007e6b9`
- `ntdll!RtlAcquireResourceExclusive` at `0x18007e5bf`
- `ntdll!RtlAcquireResourceExclusive` at `0x18007e633`
- `ntdll!RtlAcquireResourceExclusive` at `0x18007e6b9`
- `ntdll!RtlDeleteCriticalSection` at `0x18007e74e`
- `ntdll!RtlDeleteCriticalSection` at `0x18007e7db`
- `ntdll!RtlDeleteCriticalSection` at `0x18007e8ec`
- `ntdll!RtlDeleteCriticalSection` at `0x18007e9a8`
- `ntdll!RtlDeleteCriticalSection` at `0x18007e9ed`
- `ntdll!RtlDeleteCriticalSection` at `0x18007ea13`
- `ntdll!RtlDeleteCriticalSection` at `0x18007ea73`
- `ntdll!RtlDeleteCriticalSection` at `0x18007e74e`
- `ntdll!RtlDeleteCriticalSection` at `0x18007e7db`
- `ntdll!RtlDeleteCriticalSection` at `0x18007e8ec`
- `ntdll!RtlDeleteCriticalSection` at `0x18007e9a8`
- `ntdll!RtlDeleteCriticalSection` at `0x18007e9ed`
- `ntdll!RtlDeleteCriticalSection` at `0x18007ea13`
- `ntdll!RtlDeleteCriticalSection` at `0x18007ea73`
- `ntdll!RtlEnterCriticalSection` at `0x18007e707`
- `ntdll!RtlEnterCriticalSection` at `0x18007e95c`
- `ntdll!RtlEnterCriticalSection` at `0x18007e707`
- `ntdll!RtlEnterCriticalSection` at `0x18007e95c`
- `ntdll!RtlLeaveCriticalSection` at `0x18007e96e`
- `ntdll!RtlLeaveCriticalSection` at `0x18007e96e`
- `KerbClientShared!KerbClientSharedCleanup` at `0x18007e8c7`
- `KerbClientShared!KerbClientSharedCleanup` at `0x18007e8c7`
- `WS2_32!__imp_WSACleanup` at `0x18007e89d`
- `WS2_32!__imp_WSACleanup` at `0x18007e89d`
- `LSASRV!LsarClose` at `0x18007e82e`
- `LSASRV!LsarClose` at `0x18007e82e`
- `LSASRV!LsaIUnregisterPolicyChangeNotificationCallback` at `0x18007e5a1`
- `LSASRV!LsaIUnregisterPolicyChangeNotificationCallback` at `0x18007e5a1`

## pseudocode

```c
__int64 __fastcall SpCleanup(int a1, unsigned int a2)
{
  struct _KERB_PROCESS_TABLE_ENTRY *v3; // rax
  struct _KERB_PROCESS_TABLE_ENTRY *v4; // rdi
  HLOCAL *i; // rdi
  struct _KERB_CREDENTIAL *v6; // rdx
  PRTL_GENERIC_TABLE v7; // rdi
  unsigned int v8; // edx
  KerbLoopback::KeyNode *v9; // rcx
  struct _RTL_CRITICAL_SECTION *v10; // rcx

  KerbGlobalInitialized = 0;
  if ( qword_1801454D8 )
  {
    SspRegistry::RegistryWatcher::`scalar deleting destructor'(qword_1801454D8, a2);
    qword_1801454D8 = 0;
  }
  if ( qword_1801454E0 )
  {
    SspRegistry::RegistryWatcher::`scalar deleting destructor'(qword_1801454E0, a2);
    qword_1801454E0 = 0;
  }
  if ( (a1 & 0x10) != 0 )
    KerbShutdownScavenger();
  if ( (a1 & 0x40000) != 0 )
    LsaIUnregisterPolicyChangeNotificationCallback(KerbDomainChangeCallback, 4);
  if ( (a1 & 0x20000000) != 0 && KerbGlobalProcessTableInitialized )
  {
    RtlAcquireResourceExclusive(&KerbGlobalProcessTableLock, 1u);
    do
    {
      v3 = (struct _KERB_PROCESS_TABLE_ENTRY *)RtlEnumerateGenericTableAvl(&KerbGlobalProcessTable, 1u);
      v4 = v3;
      if ( !v3 )
        break;
      KerbCleanupProcessTableEntry(v3);
    }
    while ( RtlDeleteElementGenericTableAvl(&KerbGlobalProcessTable, v4) );
    RtlReleaseResource(&KerbGlobalProcessTableLock);
    RtlDeleteResource(&KerbGlobalProcessTableLock);
    KerbGlobalProcessTableInitialized = 0;
  }
  if ( (a1 & 0x20) != 0 )
    KerbUnloadLogonSessionTable();
  if ( (a1 & 0x80000) != 0 && RtlAcquireResourceExclusive(&KerbSKeyLock, 1u) )
  {
    for ( i = (HLOCAL *)KerbSKeyList; i != &KerbSKeyList; i = (HLOCAL *)*i )
      KerbFreeSKeyEntry(i);
    RtlReleaseResource(&KerbSKeyLock);
    RtlDeleteResource(&KerbSKeyLock);
  }
  if ( (a1 & 0x100000) != 0 && KerbhSKeyTimerQueue )
  {
    RtlDeleteTimerQueue(KerbhSKeyTimerQueue);
    KerbhSKeyTimerQueue = 0;
  }
  if ( (a1 & 0x400) != 0 )
    KerbFreeContextList();
  if ( (a1 & 0x800) != 0 )
  {
    if ( KerberosTicketCacheInitialized )
    {
      RtlAcquireResourceExclusive(&KerberosTicketCacheLock, 1u);
      RtlDeleteResource(&KerberosTicketCacheLock);
    }
    KerberosTicketCacheInitialized = 0;
  }
  if ( g_hPolicyEvent )
  {
    CloseHandle(g_hPolicyEvent);
    g_hPolicyEvent = 0;
    KerbCleanupSearchForests();
  }
  if ( (a1 & 0x200) != 0 )
  {
    if ( KerberosCredentialsInitialized )
    {
      RtlEnterCriticalSection(&stru_180144A70);
      while ( (_UNKNOWN *)KerbCredentialList != &KerbCredentialList )
      {
        KerbReferenceListEntryNoLock2((struct _KERBEROS_LIST2 *)&KerbCredentialList, KerbCredentialList, 1u);
        KerbDereferenceCredential(v6);
      }
      KerbFreeList2((struct _KERBEROS_LIST2 *)&KerbCredentialList);
    }
    KerberosCredentialsInitialized = 0;
  }
  if ( (a1 & 0x1000000) != 0 )
    RtlDeleteCriticalSection(&KerbGlobalCredentialsLock);
  KerbFreeString((__int64)&KerbGlobalDomainName);
  KerbFreeString((__int64)&KerbGlobalDnsDomainName);
  KerbFreeString((__int64)&KerbGlobalMachineName);
  KerbFreeString((__int64)&KerbGlobalKerbMachineName);
  KerbFreeString((__int64)&KerbGlobalMachineServiceName);
  KerbFreeKdcName(&KerbGlobalMitMachineServiceName);
  if ( (a1 & 0x40) != 0 )
  {
    v7 = Authenticators;
    if ( Authenticators )
    {
      CAuthenticatorList::~CAuthenticatorList((CAuthenticatorList *)Authenticators);
      operator delete(v7, (const struct std::nothrow_t *)0x88);
      Authenticators = 0;
    }
    KerbCleanupSkewState();
  }
  if ( (a1 & 0x200000) != 0 )
    RtlDeleteCriticalSection(&KerbGlobalDHParametersLock);
  if ( KerbGlobalDHInitialized )
    KerbUnLoadDH();
  KerbFreeDHParameters((struct _CERT_X942_DH_PARAMETERS *)&KerbGlobalDHParameters);
  if ( KerbGlobalDHAlgorithm.Parameters.pbData )
    KerbFree(KerbGlobalDHAlgorithm.Parameters.pbData);
  *(_OWORD *)&KerbGlobalDHAlgorithm.pszObjId = 0;
  KerbGlobalDHAlgorithm.Parameters.pbData = 0;
  if ( KerbGlobalPolicyHandle )
  {
    LsarClose(&KerbGlobalPolicyHandle);
    KerbGlobalPolicyHandle = 0;
  }
  v9 = (KerbLoopback::KeyNode *)KerbGlobalDomainSid;
  if ( KerbGlobalDomainSid )
  {
    KerbFree(KerbGlobalDomainSid);
    KerbGlobalDomainSid = 0;
  }
  if ( KerbGlobalUPNNameHintCount )
  {
    KerbGlobalUPNNameHintCount = 0;
    KerbFree(KerbGlobalUPNNameHintStorage);
    KerbGlobalUPNNameHintStorage = 0;
    KerbFree(KerbGlobalUPNNameHints);
    KerbGlobalUPNNameHints = 0;
  }
  if ( (a1 & 0x20000) != 0 && _InterlockedDecrement(&SocketStarts) < 0 )
    WSACleanup();
  if ( (a1 & 0x80u) != 0 )
  {
    KerbUdpNextUpdate.QuadPart = 0;
    KerbUdpTimeoutEvents = 0;
    RtlDeleteResource(&KerbUdpLock);
  }
  if ( (a1 & 0x4000) != 0 )
    KerbClientSharedCleanup();
  if ( (a1 & 0x800000) != 0 )
  {
    KerberosCryptoPolicy::UninitializeCiphers();
    byte_1801454A8 = 0;
  }
  if ( (a1 & 0x40000000) != 0 )
  {
    RtlDeleteCriticalSection(&stru_180145328);
    while ( 1 )
    {
      v9 = qword_180146808;
      if ( !qword_180146808 )
        break;
      qword_180146808 = (KerbLoopback::KeyNode *)*((_QWORD *)qword_180146808 + 10);
      KerbLoopback::KeyNode::`scalar deleting destructor'(v9, v8);
    }
    qword_180146800 = 0;
    qword_180145320 = 0;
  }
  if ( (a1 & 0x8000) != 0 )
  {
    if ( qword_180146730 )
    {
      SspRegistry::RegistryWatcher::`scalar deleting destructor'(qword_180146730, v8);
      qword_180146730 = 0;
    }
    if ( hKey )
    {
      RegCloseKey(hKey);
      hKey = 0;
    }
    RtlEnterCriticalSection(&stru_180144D18);
    KerbCleanupMitRealmList();
    RtlLeaveCriticalSection(&stru_180144D18);
    KerbFreeList2((struct _KERBEROS_LIST2 *)&KerbMitRealmList);
  }
  if ( (a1 & 0x1000) != 0 )
    KerbCleanupBindingCacheEx(1u, v8);
  if ( (a1 & 0x8000000) != 0 && KerbGlobalDomainCache )
  {
    KerbCleanupDomainCache(v9);
    RtlDeleteCriticalSection(&stru_180144F18);
    memset_0(&KerbGlobalDomainCache, 0, 0x40u);
  }
  if ( (a1 & 0x4000000) != 0 )
    KerbUninitDnsSuffixTable((struct _KERB_DNS_SUFFIX_TABLE *)&KerbGlobalDnsSuffixTable);
  if ( (a1 & 0x2000000) != 0 )
  {
    KerbCleanupKdcProxyCache((struct _KDC_PROXY_CACHE *)&KerbGlobalKdcProxyCache, 0);
    RtlDeleteCriticalSection(&KerbGlobalKdcProxyCacheLock);
  }
  if ( (a1 & 0x2000) != 0 )
    KerbUninitSpnCache();
  if ( (a1 & 2) != 0 && KerbCallKdcDataInitialized )
  {
    RtlDeleteCriticalSection(&KerbCallKdcDataLock);
    KerbCallKdcDataInitialized = 0;
  }
  if ( (a1 & 0x400000) != 0 )
    RtlDeleteResource(&KerberosGlobalResource);
  if ( (a1 & 1) != 0 )
  {
    v10 = (struct _RTL_CRITICAL_SECTION *)_InterlockedExchange64((volatile __int64 *)&KerbEventLogHandle, 0);
    if ( v10 )
      NetpEventlogClose(v10);
  }
  if ( (a1 & 0x10000000) != 0 )
  {
    RtlDeleteResource(&KerbGlobalS4U2ProxyCacheLock);
    CloseHandle(KerbGlobalKerbKdcCallEvent);
    RtlDeleteCriticalSection(&KerbGlobalKerbKdcCallLock);
  }
  KerberosCryptoPolicy::UninitializeCiphers();
  KerbGlobalMaxTokenSizeInitialized = 0;
  McGenEventUnregister_EtwEventUnregister();
  return 0;
}

```

## disassembly

```asm
0x18007e540  push    rbx
0x18007e542  push    rsi
0x18007e543  push    rdi
0x18007e544  push    r14
0x18007e546  sub     rsp, 28h
0x18007e54a  xor     esi, esi
0x18007e54c  mov     ebx, ecx
0x18007e54e  mov     rcx, cs:qword_1801454D8; this
0x18007e555  mov     cs:?KerbGlobalInitialized@@3EA, sil; uchar KerbGlobalInitialized
0x18007e55c  test    rcx, rcx
0x18007e55f  jz      short loc_18007E56D
0x18007e561  call    ??_GRegistryWatcher@SspRegistry@@QEAAPEAXI@Z; SspRegistry::RegistryWatcher::`scalar deleting destructor'(uint)
0x18007e566  mov     cs:qword_1801454D8, rsi
0x18007e56d  mov     rcx, cs:qword_1801454E0; this
0x18007e574  test    rcx, rcx
0x18007e577  jz      short loc_18007E585
0x18007e579  call    ??_GRegistryWatcher@SspRegistry@@QEAAPEAXI@Z; SspRegistry::RegistryWatcher::`scalar deleting destructor'(uint)
0x18007e57e  mov     cs:qword_1801454E0, rsi
0x18007e585  test    bl, 10h
0x18007e588  jz      short loc_18007E58F
0x18007e58a  call    KerbShutdownScavenger
0x18007e58f  bt      ebx, 12h
0x18007e593  jnb     short loc_18007E5A7
0x18007e595  mov     edx, 4
0x18007e59a  lea     rcx, ?KerbDomainChangeCallback@@YAXW4_POLICY_NOTIFICATION_INFORMATION_CLASS@@@Z; KerbDomainChangeCallback(_POLICY_NOTIFICATION_INFORMATION_CLASS)
0x18007e5a1  call    cs:__imp_LsaIUnregisterPolicyChangeNotificationCallback
0x18007e5a7  bt      ebx, 1Dh
0x18007e5ab  jnb     short loc_18007E61A
0x18007e5ad  cmp     cs:?KerbGlobalProcessTableInitialized@@3EA, sil; uchar KerbGlobalProcessTableInitialized
0x18007e5b4  jz      short loc_18007E61A
0x18007e5b6  mov     dl, 1; Wait
0x18007e5b8  lea     rcx, ?KerbGlobalProcessTableLock@@3U_RTL_RESOURCE@@A; Resource
0x18007e5bf  call    cs:__imp_RtlAcquireResourceExclusive
0x18007e5c5  lea     r14, ?KerbGlobalProcessTable@@3U_RTL_AVL_TABLE@@A; _RTL_AVL_TABLE KerbGlobalProcessTable
0x18007e5cc  jmp     short loc_18007E5E6
0x18007e5ce  mov     rcx, rdi; struct _KERB_PROCESS_TABLE_ENTRY *
0x18007e5d1  call    ?KerbCleanupProcessTableEntry@@YAXPEAU_KERB_PROCESS_TABLE_ENTRY@@@Z; KerbCleanupProcessTableEntry(_KERB_PROCESS_TABLE_ENTRY *)
0x18007e5d6  mov     rdx, rdi; Buffer
0x18007e5d9  mov     rcx, r14; Table
0x18007e5dc  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x18007e5e2  test    al, al
0x18007e5e4  jz      short loc_18007E5F9
0x18007e5e6  mov     dl, 1; Restart
0x18007e5e8  mov     rcx, r14; Table
0x18007e5eb  call    cs:__imp_RtlEnumerateGenericTableAvl
0x18007e5f1  mov     rdi, rax
0x18007e5f4  test    rax, rax
0x18007e5f7  jnz     short loc_18007E5CE
0x18007e5f9  lea     rcx, ?KerbGlobalProcessTableLock@@3U_RTL_RESOURCE@@A; Resource
0x18007e600  call    cs:__imp_RtlReleaseResource
0x18007e606  lea     rcx, ?KerbGlobalProcessTableLock@@3U_RTL_RESOURCE@@A; Resource
0x18007e60d  call    cs:__imp_RtlDeleteResource
0x18007e613  mov     cs:?KerbGlobalProcessTableInitialized@@3EA, sil; uchar KerbGlobalProcessTableInitialized
0x18007e61a  test    bl, 20h
0x18007e61d  jz      short loc_18007E624
0x18007e61f  call    ?KerbUnloadLogonSessionTable@@YAXXZ; KerbUnloadLogonSessionTable(void)
0x18007e624  bt      ebx, 13h
0x18007e628  jnb     short loc_18007E677
0x18007e62a  mov     dl, 1; Wait
0x18007e62c  lea     rcx, ?KerbSKeyLock@@3U_RTL_RESOURCE@@A; Resource
0x18007e633  call    cs:__imp_RtlAcquireResourceExclusive
0x18007e639  test    al, al
0x18007e63b  jz      short loc_18007E677
0x18007e63d  mov     rdi, cs:?KerbSKeyList@@3U_LIST_ENTRY@@A; _LIST_ENTRY KerbSKeyList
0x18007e644  lea     r14, ?KerbSKeyList@@3U_LIST_ENTRY@@A; _LIST_ENTRY KerbSKeyList
0x18007e64b  jmp     short loc_18007E658
0x18007e64d  mov     rcx, rdi; hMem
0x18007e650  call    ?KerbFreeSKeyEntry@@YAXPEAU_KERB_SESSION_KEY_ENTRY@@@Z; KerbFreeSKeyEntry(_KERB_SESSION_KEY_ENTRY *)
0x18007e655  mov     rdi, [rdi]
0x18007e658  cmp     rdi, r14
0x18007e65b  jnz     short loc_18007E64D
0x18007e65d  lea     rcx, ?KerbSKeyLock@@3U_RTL_RESOURCE@@A; Resource
0x18007e664  call    cs:__imp_RtlReleaseResource
0x18007e66a  lea     rcx, ?KerbSKeyLock@@3U_RTL_RESOURCE@@A; Resource
0x18007e671  call    cs:__imp_RtlDeleteResource
0x18007e677  bt      ebx, 14h
0x18007e67b  jnb     short loc_18007E696
0x18007e67d  mov     rcx, cs:?KerbhSKeyTimerQueue@@3PEAXEA; TimerQueue
0x18007e684  test    rcx, rcx
0x18007e687  jz      short loc_18007E696
0x18007e689  call    cs:__imp_RtlDeleteTimerQueue
0x18007e68f  mov     cs:?KerbhSKeyTimerQueue@@3PEAXEA, rsi; void * KerbhSKeyTimerQueue
0x18007e696  bt      ebx, 0Ah
0x18007e69a  jnb     short loc_18007E6A1
0x18007e69c  call    ?KerbFreeContextList@@YAXXZ; KerbFreeContextList(void)
0x18007e6a1  bt      ebx, 0Bh
0x18007e6a5  jnb     short loc_18007E6D3
0x18007e6a7  cmp     cs:?KerberosTicketCacheInitialized@@3EA, sil; uchar KerberosTicketCacheInitialized
0x18007e6ae  jz      short loc_18007E6CC
0x18007e6b0  mov     dl, 1; Wait
0x18007e6b2  lea     rcx, ?KerberosTicketCacheLock@@3U_RTL_RESOURCE@@A; Resource
0x18007e6b9  call    cs:__imp_RtlAcquireResourceExclusive
0x18007e6bf  lea     rcx, ?KerberosTicketCacheLock@@3U_RTL_RESOURCE@@A; Resource
0x18007e6c6  call    cs:__imp_RtlDeleteResource
0x18007e6cc  mov     cs:?KerberosTicketCacheInitialized@@3EA, sil; uchar KerberosTicketCacheInitialized
0x18007e6d3  mov     rcx, cs:?g_hPolicyEvent@@3PEAXEA; hObject
0x18007e6da  test    rcx, rcx
0x18007e6dd  jz      short loc_18007E6F1
0x18007e6df  call    cs:__imp_CloseHandle
0x18007e6e5  mov     cs:?g_hPolicyEvent@@3PEAXEA, rsi; void * g_hPolicyEvent
0x18007e6ec  call    ?KerbCleanupSearchForests@@YAXXZ; KerbCleanupSearchForests(void)
0x18007e6f1  bt      ebx, 9
0x18007e6f5  jnb     short loc_18007E741
0x18007e6f7  cmp     cs:?KerberosCredentialsInitialized@@3EA, sil; uchar KerberosCredentialsInitialized
0x18007e6fe  jz      short loc_18007E73A
0x18007e700  lea     rcx, stru_180144A70; CriticalSection
0x18007e707  call    cs:__imp_RtlEnterCriticalSection
0x18007e70d  lea     rdi, ?KerbCredentialList@@3U_KERBEROS_LIST2@@A; _KERBEROS_LIST2 KerbCredentialList
0x18007e714  mov     rdx, cs:?KerbCredentialList@@3U_KERBEROS_LIST2@@A; struct _KERBEROS_LIST_ENTRY *
0x18007e71b  mov     rcx, rdi; struct _KERBEROS_LIST2 *
0x18007e71e  cmp     rdx, rdi
0x18007e721  jz      short loc_18007E735
0x18007e723  mov     r8b, 1; unsigned __int8
0x18007e726  call    ?KerbReferenceListEntryNoLock2@@YAXPEAU_KERBEROS_LIST2@@PEAU_KERBEROS_LIST_ENTRY@@E@Z; KerbReferenceListEntryNoLock2(_KERBEROS_LIST2 *,_KERBEROS_LIST_ENTRY *,uchar)
0x18007e72b  mov     rcx, rdx; struct _KERB_CREDENTIAL *
0x18007e72e  call    ?KerbDereferenceCredential@@YAXPEAU_KERB_CREDENTIAL@@@Z; KerbDereferenceCredential(_KERB_CREDENTIAL *)
0x18007e733  jmp     short loc_18007E714
0x18007e735  call    ?KerbFreeList2@@YAXPEAU_KERBEROS_LIST2@@@Z; KerbFreeList2(_KERBEROS_LIST2 *)
0x18007e73a  mov     cs:?KerberosCredentialsInitialized@@3EA, sil; uchar KerberosCredentialsInitialized
0x18007e741  bt      ebx, 18h
0x18007e745  jnb     short loc_18007E754
0x18007e747  lea     rcx, ?KerbGlobalCredentialsLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x18007e74e  call    cs:__imp_RtlDeleteCriticalSection
0x18007e754  lea     rcx, ?KerbGlobalDomainName@@3U_UNICODE_STRING@@A; _UNICODE_STRING KerbGlobalDomainName
0x18007e75b  call    KerbFreeString
0x18007e760  lea     rcx, ?KerbGlobalDnsDomainName@@3U_UNICODE_STRING@@A; _UNICODE_STRING KerbGlobalDnsDomainName
0x18007e767  call    KerbFreeString
0x18007e76c  lea     rcx, ?KerbGlobalMachineName@@3U_UNICODE_STRING@@A; _UNICODE_STRING KerbGlobalMachineName
0x18007e773  call    KerbFreeString
0x18007e778  lea     rcx, ?KerbGlobalKerbMachineName@@3U_STRING@@A; _STRING KerbGlobalKerbMachineName
0x18007e77f  call    KerbFreeString
0x18007e784  lea     rcx, ?KerbGlobalMachineServiceName@@3U_UNICODE_STRING@@A; _UNICODE_STRING KerbGlobalMachineServiceName
0x18007e78b  call    KerbFreeString
0x18007e790  lea     rcx, ?KerbGlobalMitMachineServiceName@@3PEAU_KERB_INTERNAL_NAME@@EA; struct _KERB_INTERNAL_NAME **
0x18007e797  call    ?KerbFreeKdcName@@YAXPEAPEAU_KERB_INTERNAL_NAME@@@Z; KerbFreeKdcName(_KERB_INTERNAL_NAME * *)
0x18007e79c  test    bl, 40h
0x18007e79f  jz      short loc_18007E7CE
0x18007e7a1  mov     rdi, cs:?Authenticators@@3PEAVCAuthenticatorList@@EA; CAuthenticatorList * Authenticators
0x18007e7a8  test    rdi, rdi
0x18007e7ab  jz      short loc_18007E7C9
0x18007e7ad  mov     rcx, rdi; this
0x18007e7b0  call    ??1CAuthenticatorList@@QEAA@XZ; CAuthenticatorList::~CAuthenticatorList(void)
0x18007e7b5  mov     edx, 88h; struct std::nothrow_t *
0x18007e7ba  mov     rcx, rdi; void *
0x18007e7bd  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18007e7c2  mov     cs:?Authenticators@@3PEAVCAuthenticatorList@@EA, rsi; CAuthenticatorList * Authenticators
0x18007e7c9  call    ?KerbCleanupSkewState@@YAXXZ; KerbCleanupSkewState(void)
0x18007e7ce  bt      ebx, 15h
0x18007e7d2  jnb     short loc_18007E7E1
0x18007e7d4  lea     rcx, ?KerbGlobalDHParametersLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x18007e7db  call    cs:__imp_RtlDeleteCriticalSection
0x18007e7e1  cmp     cs:?KerbGlobalDHInitialized@@3HA, esi; int KerbGlobalDHInitialized
0x18007e7e7  jz      short loc_18007E7EE
0x18007e7e9  call    ?KerbUnLoadDH@@YAXXZ; KerbUnLoadDH(void)
0x18007e7ee  lea     rcx, ?KerbGlobalDHParameters@@3U_CERT_X942_DH_PARAMETERS@@A; struct _CERT_X942_DH_PARAMETERS *
0x18007e7f5  call    ?KerbFreeDHParameters@@YAXPEAU_CERT_X942_DH_PARAMETERS@@@Z; KerbFreeDHParameters(_CERT_X942_DH_PARAMETERS *)
0x18007e7fa  mov     rcx, cs:?KerbGlobalDHAlgorithm@@3U_CRYPT_ALGORITHM_IDENTIFIER@@A.Parameters.pbData; _CRYPT_ALGORITHM_IDENTIFIER KerbGlobalDHAlgorithm ...
0x18007e801  test    rcx, rcx
0x18007e804  jz      short loc_18007E80B
0x18007e806  call    KerbFree
0x18007e80b  xor     eax, eax
0x18007e80d  xorps   xmm0, xmm0
0x18007e810  cmp     cs:?KerbGlobalPolicyHandle@@3PEAXEA, rsi; void * KerbGlobalPolicyHandle
0x18007e817  movups  xmmword ptr cs:?KerbGlobalDHAlgorithm@@3U_CRYPT_ALGORITHM_IDENTIFIER@@A.pszObjId, xmm0; _CRYPT_ALGORITHM_IDENTIFIER KerbGlobalDHAlgorithm ...
0x18007e81e  mov     cs:?KerbGlobalDHAlgorithm@@3U_CRYPT_ALGORITHM_IDENTIFIER@@A.Parameters.pbData, rax; _CRYPT_ALGORITHM_IDENTIFIER KerbGlobalDHAlgorithm ...
0x18007e825  jz      short loc_18007E83B
0x18007e827  lea     rcx, ?KerbGlobalPolicyHandle@@3PEAXEA; void * KerbGlobalPolicyHandle
0x18007e82e  call    cs:__imp_LsarClose
0x18007e834  mov     cs:?KerbGlobalPolicyHandle@@3PEAXEA, rsi; void * KerbGlobalPolicyHandle
0x18007e83b  mov     rcx, cs:?KerbGlobalDomainSid@@3PEAXEA; void * KerbGlobalDomainSid
0x18007e842  test    rcx, rcx
0x18007e845  jz      short loc_18007E853
0x18007e847  call    KerbFree
0x18007e84c  mov     cs:?KerbGlobalDomainSid@@3PEAXEA, rsi; void * KerbGlobalDomainSid
0x18007e853  cmp     cs:?KerbGlobalUPNNameHintCount@@3KA, esi; ulong KerbGlobalUPNNameHintCount
0x18007e859  jz      short loc_18007E887
0x18007e85b  mov     rcx, cs:?KerbGlobalUPNNameHintStorage@@3PEAXEA; void * KerbGlobalUPNNameHintStorage
0x18007e862  mov     cs:?KerbGlobalUPNNameHintCount@@3KA, esi; ulong KerbGlobalUPNNameHintCount
0x18007e868  call    KerbFree
0x18007e86d  mov     rcx, cs:?KerbGlobalUPNNameHints@@3PEAU_UNICODE_STRING@@EA; _UNICODE_STRING * KerbGlobalUPNNameHints
0x18007e874  mov     cs:?KerbGlobalUPNNameHintStorage@@3PEAXEA, rsi; void * KerbGlobalUPNNameHintStorage
0x18007e87b  call    KerbFree
0x18007e880  mov     cs:?KerbGlobalUPNNameHints@@3PEAU_UNICODE_STRING@@EA, rsi; _UNICODE_STRING * KerbGlobalUPNNameHints
0x18007e887  bt      ebx, 11h
0x18007e88b  jnb     short loc_18007E8A3
0x18007e88d  or      eax, 0FFFFFFFFh
0x18007e890  lock xadd cs:?SocketStarts@@3JA, eax; long SocketStarts
0x18007e898  cmp     eax, 1
0x18007e89b  jns     short loc_18007E8A3
0x18007e89d  call    cs:__imp_WSACleanup
0x18007e8a3  test    bl, bl
0x18007e8a5  jns     short loc_18007E8C1
0x18007e8a7  lea     rcx, ?KerbUdpLock@@3U_RTL_RESOURCE@@A; Resource
0x18007e8ae  mov     cs:?KerbUdpNextUpdate@@3T_LARGE_INTEGER@@A, rsi; _LARGE_INTEGER KerbUdpNextUpdate
0x18007e8b5  mov     cs:?KerbUdpTimeoutEvents@@3JA, esi; long KerbUdpTimeoutEvents
0x18007e8bb  call    cs:__imp_RtlDeleteResource
0x18007e8c1  bt      ebx, 0Eh
0x18007e8c5  jnb     short loc_18007E8CD
0x18007e8c7  call    cs:__imp_?KerbClientSharedCleanup@@YAXXZ; KerbClientSharedCleanup(void)
0x18007e8cd  bt      ebx, 17h
0x18007e8d1  jnb     short loc_18007E8DF
0x18007e8d3  call    ?UninitializeCiphers@KerberosCryptoPolicy@@SAXW4Kerb3961PolicyType@@@Z; KerberosCryptoPolicy::UninitializeCiphers(Kerb3961PolicyType)
0x18007e8d8  mov     cs:byte_1801454A8, sil
0x18007e8df  bt      ebx, 1Eh
0x18007e8e3  jnb     short loc_18007E91E
0x18007e8e5  lea     rcx, stru_180145328; CriticalSection
0x18007e8ec  call    cs:__imp_RtlDeleteCriticalSection
0x18007e8f2  jmp     short loc_18007E904
0x18007e8f4  mov     rax, [rcx+50h]
0x18007e8f8  mov     cs:qword_180146808, rax
0x18007e8ff  call    ??_GKeyNode@KerbLoopback@@QEAAPEAXI@Z; KerbLoopback::KeyNode::`scalar deleting destructor'(uint)
0x18007e904  mov     rcx, cs:qword_180146808; this
0x18007e90b  test    rcx, rcx
0x18007e90e  jnz     short loc_18007E8F4
0x18007e910  mov     cs:qword_180146800, rsi
0x18007e917  mov     cs:qword_180145320, rsi
0x18007e91e  bt      ebx, 0Fh
0x18007e922  jnb     short loc_18007E980
0x18007e924  mov     rcx, cs:qword_180146730; this
0x18007e92b  test    rcx, rcx
0x18007e92e  jz      short loc_18007E93C
0x18007e930  call    ??_GRegistryWatcher@SspRegistry@@QEAAPEAXI@Z; SspRegistry::RegistryWatcher::`scalar deleting destructor'(uint)
0x18007e935  mov     cs:qword_180146730, rsi
0x18007e93c  mov     rcx, cs:hKey; hKey
0x18007e943  test    rcx, rcx
0x18007e946  jz      short loc_18007E955
0x18007e948  call    cs:__imp_RegCloseKey
0x18007e94e  mov     cs:hKey, rsi
0x18007e955  lea     rcx, stru_180144D18; CriticalSection
0x18007e95c  call    cs:__imp_RtlEnterCriticalSection
0x18007e962  call    ?KerbCleanupMitRealmList@@YAXXZ; KerbCleanupMitRealmList(void)
0x18007e967  lea     rcx, stru_180144D18; CriticalSection
0x18007e96e  call    cs:__imp_RtlLeaveCriticalSection
0x18007e974  lea     rcx, ?KerbMitRealmList@@3U_KERBEROS_LIST@@A; struct _KERBEROS_LIST2 *
0x18007e97b  call    ?KerbFreeList2@@YAXPEAU_KERBEROS_LIST2@@@Z; KerbFreeList2(_KERBEROS_LIST2 *)
0x18007e980  bt      ebx, 0Ch
0x18007e984  jnb     short loc_18007E98D
0x18007e986  mov     cl, 1; unsigned __int8
0x18007e988  call    ?KerbCleanupBindingCacheEx@@YAXEE@Z; KerbCleanupBindingCacheEx(uchar,uchar)
0x18007e98d  bt      ebx, 1Bh
0x18007e991  jnb     short loc_18007E9C0
0x18007e993  cmp     cs:?KerbGlobalDomainCache@@3U_KERB_DOMAIN_CACHE@@A, sil; _KERB_DOMAIN_CACHE KerbGlobalDomainCache
0x18007e99a  jz      short loc_18007E9C0
0x18007e99c  call    ?KerbCleanupDomainCache@@YAXPEAU_KERB_DOMAIN_CACHE@@@Z; KerbCleanupDomainCache(_KERB_DOMAIN_CACHE *)
0x18007e9a1  lea     rcx, stru_180144F18; CriticalSection
0x18007e9a8  call    cs:__imp_RtlDeleteCriticalSection
0x18007e9ae  xor     edx, edx; Val
0x18007e9b0  lea     rcx, ?KerbGlobalDomainCache@@3U_KERB_DOMAIN_CACHE@@A; void *
0x18007e9b7  lea     r8d, [rdx+40h]; Size
0x18007e9bb  call    memset_0
0x18007e9c0  bt      ebx, 1Ah
0x18007e9c4  jnb     short loc_18007E9D2
0x18007e9c6  lea     rcx, ?KerbGlobalDnsSuffixTable@@3U_KERB_DNS_SUFFIX_TABLE@@A; struct _KERB_DNS_SUFFIX_TABLE *
0x18007e9cd  call    ?KerbUninitDnsSuffixTable@@YAXPEAU_KERB_DNS_SUFFIX_TABLE@@@Z; KerbUninitDnsSuffixTable(_KERB_DNS_SUFFIX_TABLE *)
0x18007e9d2  bt      ebx, 19h
0x18007e9d6  jnb     short loc_18007E9F3
0x18007e9d8  xor     edx, edx; unsigned __int8
0x18007e9da  lea     rcx, ?KerbGlobalKdcProxyCache@@3U_KDC_PROXY_CACHE@@A; struct _KDC_PROXY_CACHE *
0x18007e9e1  call    ?KerbCleanupKdcProxyCache@@YAXPEAU_KDC_PROXY_CACHE@@E@Z; KerbCleanupKdcProxyCache(_KDC_PROXY_CACHE *,uchar)
0x18007e9e6  lea     rcx, ?KerbGlobalKdcProxyCacheLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x18007e9ed  call    cs:__imp_RtlDeleteCriticalSection
0x18007e9f3  bt      ebx, 0Dh
0x18007e9f7  jnb     short loc_18007E9FE
0x18007e9f9  call    ?KerbUninitSpnCache@@YAXXZ; KerbUninitSpnCache(void)
0x18007e9fe  test    bl, 2
0x18007ea01  jz      short loc_18007EA20
0x18007ea03  cmp     cs:?KerbCallKdcDataInitialized@@3EA, sil; uchar KerbCallKdcDataInitialized
0x18007ea0a  jz      short loc_18007EA20
0x18007ea0c  lea     rcx, ?KerbCallKdcDataLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x18007ea13  call    cs:__imp_RtlDeleteCriticalSection
0x18007ea19  mov     cs:?KerbCallKdcDataInitialized@@3EA, sil; uchar KerbCallKdcDataInitialized
0x18007ea20  bt      ebx, 16h
0x18007ea24  jnb     short loc_18007EA33
0x18007ea26  lea     rcx, ?KerberosGlobalResource@@3U_RTL_RESOURCE@@A; Resource
0x18007ea2d  call    cs:__imp_RtlDeleteResource
0x18007ea33  test    bl, 1
0x18007ea36  jz      short loc_18007EA4C
0x18007ea38  mov     rcx, rsi
0x18007ea3b  xchg    rcx, cs:?KerbEventLogHandle@@3PEAXEA; lpCriticalSection
0x18007ea42  test    rcx, rcx
0x18007ea45  jz      short loc_18007EA4C
0x18007ea47  call    NetpEventlogClose
0x18007ea4c  bt      ebx, 1Ch
0x18007ea50  jnb     short loc_18007EA79
0x18007ea52  lea     rcx, ?KerbGlobalS4U2ProxyCacheLock@@3U_RTL_RESOURCE@@A; Resource
0x18007ea59  call    cs:__imp_RtlDeleteResource
0x18007ea5f  mov     rcx, cs:?KerbGlobalKerbKdcCallEvent@@3PEAXEA; hObject
0x18007ea66  call    cs:__imp_CloseHandle
0x18007ea6c  lea     rcx, ?KerbGlobalKerbKdcCallLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x18007ea73  call    cs:__imp_RtlDeleteCriticalSection
0x18007ea79  call    ?UninitializeCiphers@KerberosCryptoPolicy@@SAXW4Kerb3961PolicyType@@@Z; KerberosCryptoPolicy::UninitializeCiphers(Kerb3961PolicyType)
0x18007ea7e  mov     cs:?KerbGlobalMaxTokenSizeInitialized@@3HA, esi; int KerbGlobalMaxTokenSizeInitialized
0x18007ea84  call    McGenEventUnregister_EtwEventUnregister
0x18007ea89  xor     eax, eax
0x18007ea8b  add     rsp, 28h
0x18007ea8f  pop     r14
0x18007ea91  pop     rdi
0x18007ea92  pop     rsi
0x18007ea93  pop     rbx
0x18007ea94  retn
  ... truncated ...
```
