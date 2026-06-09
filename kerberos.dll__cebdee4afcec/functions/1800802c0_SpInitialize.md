# SpInitialize

- ea: `0x1800802c0`
- end: `0x180080b89`
- name: `SpInitialize`
- size: `2249`
- prototype: ``
- caller_count: `0`
- callee_count: `35`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180012da0`
- `0x180029300`
- `0x18002ae30`
- `0x18006ba6c`
- `0x180070680`
- `0x1800740b0`
- `0x180077b58`
- `0x180078450`
- `0x1800784a0`
- `0x180078664`
- `0x18007a8ac`
- `0x18007b808`
- `0x18007d2cc`
- `0x18007e540`
- `0x180080008`
- `0x1800802c0`
- `0x18008a5b4`
- `0x18008aba0`
- `0x18008b70c`
- `0x18008fe98`
- `0x18008ffe0`
- `0x180090ff0`
- `0x180092698`
- `0x18009487c`
- `0x180099414`
- `0x1800b445c`
- `0x1800b4cc0`
- `0x1800b59b0`
- `0x1800ba464`
- `0x1800c36f8`
- `0x1800d505c`
- `0x1800d8b10`
- `0x1800dcbac`
- `0x1800dd100`
- `0x1800f1f0c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180080911`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180080911`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180080923`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800809c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180080a20`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180080923`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800809c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180080a20`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800803d9`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800803d9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800803e6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800803e6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180080365`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180080398`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180080365`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180080398`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x1800805fc`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x1800805fc`
- `ntdll!RtlInitializeGenericTable` at `0x18008049f`
- `ntdll!RtlInitializeGenericTable` at `0x18008049f`
- `ntdll!RtlInitUnicodeString` at `0x180080339`
- `ntdll!RtlInitUnicodeString` at `0x1800805bc`
- `ntdll!RtlInitUnicodeString` at `0x1800805d0`
- `ntdll!RtlInitUnicodeString` at `0x1800806bd`
- `ntdll!RtlInitUnicodeString` at `0x1800806e5`
- `ntdll!RtlInitUnicodeString` at `0x180080339`
- `ntdll!RtlInitUnicodeString` at `0x1800805bc`
- `ntdll!RtlInitUnicodeString` at `0x1800805d0`
- `ntdll!RtlInitUnicodeString` at `0x1800806bd`
- `ntdll!RtlInitUnicodeString` at `0x1800806e5`
- `ntdll!RtlInitializeCriticalSection` at `0x1800804b0`
- `ntdll!RtlInitializeCriticalSection` at `0x1800804cf`
- `ntdll!RtlInitializeCriticalSection` at `0x18008050a`
- `ntdll!RtlInitializeCriticalSection` at `0x180080638`
- `ntdll!RtlInitializeCriticalSection` at `0x18008085c`
- `ntdll!RtlInitializeCriticalSection` at `0x180080abd`
- `ntdll!RtlInitializeCriticalSection` at `0x1800804b0`
- `ntdll!RtlInitializeCriticalSection` at `0x1800804cf`
- `ntdll!RtlInitializeCriticalSection` at `0x18008050a`
- `ntdll!RtlInitializeCriticalSection` at `0x180080638`
- `ntdll!RtlInitializeCriticalSection` at `0x18008085c`
- `ntdll!RtlInitializeCriticalSection` at `0x180080abd`
- `KerbClientShared!KerbClientSharedInit` at `0x18008095a`
- `KerbClientShared!KerbClientSharedInit` at `0x18008095a`
- `CRYPTSP!SystemFunction006` at `0x1800806ae`
- `CRYPTSP!SystemFunction006` at `0x1800806ae`
- `CRYPTSP!SystemFunction007` at `0x1800806ce`
- `CRYPTSP!SystemFunction007` at `0x1800806ce`
- `LSASRV!LsaIOpenPolicyTrusted` at `0x18008066a`
- `LSASRV!LsaIOpenPolicyTrusted` at `0x18008066a`

## string_xrefs

- `0x1800803f3`: `Failed to open kerberos key: 0x%x\n`
- `0x1800804f1`: `Failed to initialize SPN cache: 0x%x`
- `0x18008051c`: `Failed to initialize kdc proxy cache lock: %#x`
- `0x18008057b`: `Failed to initialize domain cache: %#x`
- `0x18008070a`: `KerbSetComputerName failed\n`
- `0x18008079e`: `Failed to initialize network service loopback detection: 0x%x`
- `0x1800807c1`: `Failed to initialize network service session key list timer: 0x%x`
- `0x1800808a1`: `Failed to initialize ticket cache: 0x%x`
- `0x180080b38`: `Failed to initialize binding cache: 0x%x`
- `0x180080929`: `CreateEvent for g_hPolicyEvent failed - 0x%x\n`
- `0x1800809cc`: `Failed to create GP watcher: 0x%x`
- `0x180080a26`: `Failed to create parameter watcher: 0x%x`
- `0x180080b18`: `Failed to schedule background thread to start Local KDC: 0x%x`

## pseudocode

```c
__int64 __fastcall SpInitialize(unsigned __int64 a1, __int64 a2, struct _LSA_SECPKG_FUNCTION_TABLE *a3)
{
  int v6; // eax
  LSTATUS v7; // eax
  int v8; // ebx
  unsigned int v9; // edx
  char *v10; // rdi
  NTSTATUS v11; // eax
  int inited; // eax
  const char *v13; // r9
  __int64 v14; // r8
  struct _KERB_DOMAIN_CACHE *v15; // rcx
  NTSTATUS v16; // eax
  void *v17; // r8
  DWORD v18; // eax
  int v19; // ecx
  DWORD LastError; // eax
  unsigned int v21; // edx
  unsigned __int16 v22; // cx
  unsigned __int8 *v23; // r8
  Ntlmless::Kerberos *v24; // rcx
  PHKEY phkResult; // [rsp+20h] [rbp-79h]
  LSTATUS Key; // [rsp+50h] [rbp-49h] BYREF
  HKEY hKey[2]; // [rsp+60h] [rbp-39h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+70h] [rbp-29h] BYREF
  WCHAR Buffer[8]; // [rsp+80h] [rbp-19h] BYREF
  __int128 v31; // [rsp+90h] [rbp-9h]
  int v32; // [rsp+A0h] [rbp+7h]

  Key = 0;
  DestinationString = 0;
  McGenEventRegister_EtwEventRegister();
  v6 = (*(_DWORD *)(a2 + 4) >> 5) & 1;
  KerbGlobalKerbKdcCallInfo = 0;
  KerbGlobalIsRunningIsolated = v6;
  KerbGlobalKerbKdcCallCounter = 0;
  KerbGlobalODJState = 1;
  RtlInitUnicodeString(&KerbGlobalManagedServiceAccountPassword, L"_SA_{262E99C9-6160-4871-ACEC-4E61736B6F21}");
  v7 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\Control\\Lsa\\Kerberos\\Parameters",
         0,
         0x20019u,
         &g_hKeyParams);
  Key = v7;
  if ( v7 == 2 )
  {
    hKey[0] = 0;
    v7 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\Lsa\\Kerberos", 0, 4u, hKey);
    Key = v7;
    if ( v7 )
    {
LABEL_5:
      KerbTracerT::Log(2, "SpInitialize", 1982, "Failed to open kerberos key: 0x%x\n", v7);
      goto LABEL_6;
    }
    Key = RegCreateKeyExW(hKey[0], L"Parameters", 0, 0, 0, 0x20019u, 0, &g_hKeyParams, 0);
    RegCloseKey(hKey[0]);
    v7 = Key;
  }
  if ( v7 )
    goto LABEL_5;
LABEL_6:
  hKey[0] = (HKEY)&Key;
  lambda_184f7f8a374c2a0f4934929177526a3b_::operator()(hKey);
  if ( Key < 0 )
    return (unsigned int)Key;
  v8 = 0x400000;
  Key = KerbInitSyncObjects();
  if ( Key < 0 )
    goto LABEL_88;
  KerberosPackageId = a1;
  v8 = 272629760;
  LsaFunctions = a3;
  KerbGlobalPackageState = 1;
  v10 = (char *)operator new(0x88u);
  *((union _LARGE_INTEGER *)v10 + 9) = KerbGlobalSkewTime;
  *((_DWORD *)v10 + 20) = 1;
  v10[84] = 0;
  v10[128] = 0;
  RtlInitializeGenericTable((PRTL_GENERIC_TABLE)v10, Compare, AuthenAllocate, AuthenFree, 0);
  Authenticators = (PRTL_GENERIC_TABLE)v10;
  v11 = RtlInitializeCriticalSection((PRTL_CRITICAL_SECTION)(v10 + 88));
  if ( v11 < 0 )
  {
    Key = v11;
    goto LABEL_88;
  }
  v10[128] = 1;
  Key = v11;
  Key = RtlInitializeCriticalSection(&KerbGlobalDHParametersLock);
  if ( Key < 0 )
  {
LABEL_88:
    SpCleanup(v8, v9);
    return (unsigned int)Key;
  }
  inited = KerbInitSpnCache();
  Key = inited;
  if ( inited < 0 )
  {
    v8 = 274726912;
    v13 = "Failed to initialize SPN cache: 0x%x";
    v14 = 2048;
    goto LABEL_84;
  }
  inited = RtlInitializeCriticalSection(&KerbGlobalKdcProxyCacheLock);
  Key = inited;
  if ( inited < 0 )
  {
    v8 = 274735104;
    v13 = "Failed to initialize kdc proxy cache lock: %#x";
    v14 = 2058;
    goto LABEL_84;
  }
  KerbInitKdcProxyCache((struct _KDC_PROXY_CACHE *)&KerbGlobalKdcProxyCache, 1u);
  inited = KerbInitDnsSuffixTable((struct _KERB_DNS_SUFFIX_TABLE *)&KerbGlobalDnsSuffixTable, 1u);
  Key = inited;
  if ( inited < 0 )
  {
    v8 = 308289536;
    v13 = "Failed to initialize kdc proxy dns suffix table: %#x";
    v14 = 2073;
    goto LABEL_84;
  }
  inited = KerbInitDomainCache(v15);
  Key = inited;
  if ( inited < 0 )
  {
    v8 = 375398400;
    v13 = "Failed to initialize domain cache: %#x";
    v14 = 2085;
    goto LABEL_84;
  }
  if ( !KerbGlobalDHParametersInitialized )
  {
    KerbGlobalPreferWellknownMODPDHDomainParameters = 1;
    KerbGlobalMODPDHModulusSize = 2048;
    KerbGlobalDHParametersInitialized = 1;
  }
  RtlInitUnicodeString(&KerbPackageName, L"Kerberos");
  RtlInitUnicodeString(&HostTargetSvc, L"RestrictedKrbHost/");
  KerbGlobalSafeModeBootOptionPresent = 0;
  v32 = 0;
  *(_OWORD *)Buffer = 0;
  v31 = 0;
  if ( GetEnvironmentVariableW(L"SAFEBOOT_OPTION", Buffer, 0x12u) && !wcscmp_0(Buffer, L"MINIMAL") )
    KerbGlobalSafeModeBootOptionPresent = 1;
  v16 = 0;
  Key = 0;
  if ( KerbCallKdcDataInitialized || (v16 = RtlInitializeCriticalSection(&KerbCallKdcDataLock), v16 < 0) )
  {
    Key = v16;
    v8 = 509616129;
    if ( v16 < 0 )
      goto LABEL_88;
  }
  else
  {
    KerbCallKdcDataInitialized = 1;
    Key = v16;
  }
  v8 = 509616131;
  Key = LsaIOpenPolicyTrusted(&KerbGlobalPolicyHandle);
  if ( Key < 0 )
    goto LABEL_88;
  if ( (*(_BYTE *)(a2 + 4) & 4) != 0 )
    byte_180145455 = 1;
  KerbGlobalHasNeverTime.QuadPart = 0;
  KerbGlobalWillNeverTime.QuadPart = 0x7FFFFF36D5969FFFLL;
  Key = SystemFunction006(&word_1800FEE0E, &KerbGlobalNullLmOwfPassword);
  RtlInitUnicodeString(&DestinationString, 0);
  Key = SystemFunction007(&DestinationString, &KerbGlobalNullNtOwfPassword);
  RtlInitUnicodeString(&KerbGlobalKdcServiceName, L"krbtgt");
  KerbGlobalEnforceTime = 0;
  KerbGlobalMachineNameChanged = 0;
  Key = KerbSetComputerName();
  if ( Key >= 0 )
  {
    Key = KerbInitializeScavenger();
    if ( Key < 0 )
    {
      v8 = 509616143;
      KerbTracerT::Log(1, "SpInitialize", 2241, "KerbInitializeScavengerFailed\n");
      goto LABEL_85;
    }
    inited = KerbLoadLogonSessionTable();
    Key = inited;
    if ( inited < 0 )
    {
      v8 = 509616159;
      v13 = "Failed to initialize logon session table: 0x%x";
      v14 = 2256;
      goto LABEL_84;
    }
    inited = KerbLoadProcessTable();
    Key = inited;
    if ( inited < 0 )
    {
      v8 = 509616191;
      v13 = "Failed to initialize process table: %#x";
      v14 = 2266;
      goto LABEL_84;
    }
    inited = KerbInitLoopbackDetection();
    Key = inited;
    if ( inited < 0 )
    {
      v8 = 1046487103;
      v13 = "Failed to initialize network service loopback detection: 0x%x";
      v14 = 2276;
      goto LABEL_84;
    }
    inited = KerbCreateSKeyTimer();
    Key = inited;
    if ( inited < 0 )
    {
      v8 = 1047011391;
      v13 = "Failed to initialize network service session key list timer: 0x%x";
      v14 = 2286;
      goto LABEL_84;
    }
    inited = KerbInitGlobalVariables();
    if ( inited >= 0 )
      inited = KerbInitializeSkewState();
    Key = inited;
    if ( inited < 0 )
    {
      v8 = 1048059967;
      v13 = "Failed to initialize ticket handling: 0x%x";
      v14 = 2296;
      goto LABEL_84;
    }
    v17 = *(void **)(a2 + 16);
    v8 = 1048060031;
    *(_OWORD *)hKey = *(_OWORD *)(a2 + 56);
    Key = KerbSetDomainName(
            (struct _UNICODE_STRING *)(a2 + 24),
            (struct _UNICODE_STRING *)(a2 + 40),
            v17,
            (struct _GUID *)hKey);
    if ( Key >= 0 )
    {
      inited = KerbInitCredentialList();
      Key = inited;
      if ( inited < 0 )
      {
        v8 = 1048060287;
        v13 = "Failed to initialize credential list: 0x%x";
        v14 = 2327;
        goto LABEL_84;
      }
      v8 = 1048060799;
      Key = RtlInitializeCriticalSection(&KerbGlobalCredentialsLock);
      if ( Key >= 0 )
      {
        inited = KerbInitContextList();
        Key = inited;
        if ( inited < 0 )
        {
          v8 = 1064838015;
          v13 = "Failed to initialize context list: 0x%x";
          v14 = 2346;
          goto LABEL_84;
        }
        inited = KerbInitTicketCaching();
        Key = inited;
        if ( inited < 0 )
        {
          v8 = 1064839039;
          v13 = "Failed to initialize ticket cache: 0x%x";
          v14 = 2356;
          goto LABEL_84;
        }
        inited = _KERB_TABLE::Initialize(
                   (_KERB_TABLE *)&KerbBindingCache,
                   (int (*)(void *, struct _RTL_BALANCED_NODE *))KerbCompareBindingCacheEntry,
                   (void (*)(struct _KERB_TABLE_ENTRY *))KerbTableFreeBindingCacheEntry);
        Key = inited;
        if ( inited < 0 )
        {
          v8 = 1064841087;
          v13 = "Failed to initialize binding cache: 0x%x";
          v14 = 2366;
          goto LABEL_84;
        }
        KerberosBindingCacheInitialized = 1;
        inited = KerbInitializeMitRealmList();
        Key = inited;
        if ( inited < 0 )
        {
          v8 = 1064845183;
          v13 = "Failed to initialize MIT realm list: 0x%x";
          v14 = 2376;
          goto LABEL_84;
        }
        v8 = 1064877951;
        g_hPolicyEvent = CreateEventW(0, 0, 0, 0);
        if ( g_hPolicyEvent )
        {
          inited = KerbClientSharedInit((const struct _KerbClientConfiguration *)&qword_1800F6BC8);
          Key = inited;
          if ( inited >= 0 )
          {
            v8 = 1064894335;
            inited = KerbCreateCredIsoObj(v19);
            Key = inited;
            if ( inited >= 0 )
            {
              qword_1801454D8 = SspRegistry::RegistryWatcher::CreateCommon(
                                  0,
                                  (unsigned int (*)(void *))KerbWatchPolicy,
                                  0,
                                  0,
                                  1,
                                  1);
              if ( !qword_1801454D8 )
              {
                LastError = GetLastError();
                KerbTracerT::Log(2, "SpInitialize", 2437, "Failed to create GP watcher: 0x%x", LastError);
              }
              qword_1801454E0 = SspRegistry::RegistryWatcher::CreateCommon(
                                  g_hKeyParams,
                                  (unsigned int (*)(void *))KerbWatchPolicy,
                                  1,
                                  0,
                                  0,
                                  0);
              if ( qword_1801454E0 )
              {
                inited = KerbInitUdpStatistics();
                Key = inited;
                if ( inited >= 0 )
                {
                  inited = KerbInitializePkinit();
                  Key = inited;
                  if ( inited >= 0 )
                  {
                    inited = KerbInitializeSockets(v22, v21, v23);
                    Key = inited;
                    if ( inited >= 0 )
                    {
                      qword_180145320 = 0;
                      qword_180146808 = 0;
                      qword_180146800 = 0;
                      inited = RtlInitializeCriticalSection(&stru_180145328);
                      Key = inited;
                      if ( inited >= 0 )
                      {
                        inited = KerbRegisterForDomainChange();
                        Key = inited;
                        if ( inited >= 0 )
                        {
                          v8 = 0x7FFFFFFF;
                          if ( Ntlmless::Kerberos::IsEnabled(v24) )
                          {
                            inited = KerbBackgroundInitializeLocalKdc();
                            Key = inited;
                            if ( inited < 0 )
                            {
                              v13 = "Failed to schedule background thread to start Local KDC: 0x%x";
                              v14 = 2512;
                              goto LABEL_84;
                            }
                            v8 = -1;
                          }
                          KerbGlobalInitialized = 1;
                          goto LABEL_85;
                        }
                        v8 = 2147221503;
                        v13 = "Failed to register for domain change notification: 0x%x";
                        v14 = 2498;
                      }
                      else
                      {
                        v8 = 1073479679;
                        v13 = "Failed to initizalize kerberos loopback detection: 0x%x";
                        v14 = 2488;
                      }
                    }
                    else
                    {
                      v8 = 1073348607;
                      v13 = "Failed to initialize sockets: 0x%x";
                      v14 = 2479;
                    }
                  }
                  else
                  {
                    v8 = 1073283071;
                    v13 = "Failed to initialize PKINT: 0x%x";
                    v14 = 2465;
                  }
                }
                else
                {
                  v8 = 1073282943;
                  v13 = "Failed to initialize UdpStats: 0x%x";
                  v14 = 2455;
                }
              }
              else
              {
                Key = -1073741670;
                inited = GetLastError();
                v13 = "Failed to create parameter watcher: 0x%x";
                v14 = 2445;
              }
            }
            else
            {
              v13 = "Failed to initialize GlobalCredIsoObj: 0x%x";
              v14 = 2423;
            }
          }
          else
          {
            v13 = "Failed to initialize KerbClientShared: 0x%x";
            v14 = 2409;
          }
LABEL_84:
          LODWORD(phkResult) = inited;
          KerbTracerT::Log(1, "SpInitialize", v14, v13, phkResult);
          goto LABEL_85;
        }
        v18 = GetLastError();
        KerbTracerT::Log(2, "SpInitialize", 2395, "CreateEvent for g_hPolicyEvent failed - 0x%x\n", v18);
        Key = -1073741670;
      }
    }
    goto LABEL_88;
  }
  v8 = 509616135;
  KerbTracerT::Log(1, "SpInitialize", 2227, "KerbSetComputerName failed\n");
LABEL_85:
  if ( Key < 0 )
    goto LABEL_88;
  return (unsigned int)Key;
}

```

## disassembly

```asm
0x1800802c0  push    rbp
0x1800802c2  push    rbx
0x1800802c3  push    rsi
0x1800802c4  push    rdi
0x1800802c5  push    r12
0x1800802c7  push    r13
0x1800802c9  push    r14
0x1800802cb  push    r15
0x1800802cd  lea     rbp, [rsp-1Fh]
0x1800802d2  sub     rsp, 0B8h
0x1800802d9  mov     rax, cs:__security_cookie
0x1800802e0  xor     rax, rsp
0x1800802e3  mov     [rbp+57h+var_48], rax
0x1800802e7  xorps   xmm0, xmm0
0x1800802ea  xor     r15d, r15d
0x1800802ed  mov     [rbp+57h+var_A0], r15d
0x1800802f1  mov     rdi, r8
0x1800802f4  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1800802f8  mov     rsi, rdx
0x1800802fb  mov     r14, rcx
0x1800802fe  call    McGenEventRegister_EtwEventRegister
0x180080303  mov     eax, [rsi+4]
0x180080306  lea     r12d, [r15+1]
0x18008030a  shr     eax, 5
0x18008030d  lea     rdx, aSa262e99c96160; "_SA_{262E99C9-6160-4871-ACEC-4E61736B6F"...
0x180080314  and     eax, r12d
0x180080317  mov     cs:?KerbGlobalKerbKdcCallInfo@@3PEAU_KERB_KDC_CALL_INFO@@EA, r15; _KERB_KDC_CALL_INFO * KerbGlobalKerbKdcCallInfo
0x18008031e  lea     rcx, ?KerbGlobalManagedServiceAccountPassword@@3U_UNICODE_STRING@@A; DestinationString
0x180080325  mov     cs:?KerbGlobalIsRunningIsolated@@3HA, eax; int KerbGlobalIsRunningIsolated
0x18008032b  mov     cs:?KerbGlobalKerbKdcCallCounter@@3KA, r15d; ulong KerbGlobalKerbKdcCallCounter
0x180080332  mov     cs:?KerbGlobalODJState@@3KA, r12d; ulong KerbGlobalODJState
0x180080339  call    cs:__imp_RtlInitUnicodeString
0x18008033f  lea     rax, ?g_hKeyParams@@3PEAUHKEY__@@EA; HKEY__ * g_hKeyParams
0x180080346  mov     rbx, 0FFFFFFFF80000002h
0x18008034d  mov     rcx, rbx; hKey
0x180080350  mov     [rsp+0F0h+phkResult], rax; phkResult
0x180080355  mov     r9d, 20019h; samDesired
0x18008035b  lea     rdx, SubKey; "System\\CurrentControlSet\\Control\\Lsa"...
0x180080362  xor     r8d, r8d; ulOptions
0x180080365  call    cs:__imp_RegOpenKeyExW
0x18008036b  mov     [rbp+57h+var_A0], eax
0x18008036e  lea     r13, aSpinitialize_0; "SpInitialize"
0x180080375  cmp     eax, 2
0x180080378  jnz     short loc_1800803EF
0x18008037a  lea     rax, [rbp+57h+hKey]
0x18008037e  mov     [rbp+57h+hKey], r15
0x180080382  lea     r9d, [r15+4]; samDesired
0x180080386  mov     [rsp+0F0h+phkResult], rax; phkResult
0x18008038b  xor     r8d, r8d; ulOptions
0x18008038e  lea     rdx, aSystemCurrentc_1; "System\\CurrentControlSet\\Control\\Lsa"...
0x180080395  mov     rcx, rbx; hKey
0x180080398  call    cs:__imp_RegOpenKeyExW
0x18008039e  mov     [rbp+57h+var_A0], eax
0x1800803a1  test    eax, eax
0x1800803a3  jnz     short loc_1800803F3
0x1800803a5  mov     rcx, [rbp+57h+hKey]; hKey
0x1800803a9  lea     rax, ?g_hKeyParams@@3PEAUHKEY__@@EA; HKEY__ * g_hKeyParams
0x1800803b0  mov     [rsp+0F0h+lpdwDisposition], r15; lpdwDisposition
0x1800803b5  lea     rdx, aParameters; "Parameters"
0x1800803bc  mov     [rsp+0F0h+var_B8], rax; phkResult
0x1800803c1  xor     r9d, r9d; lpClass
0x1800803c4  mov     [rsp+0F0h+lpSecurityAttributes], r15; lpSecurityAttributes
0x1800803c9  xor     r8d, r8d; Reserved
0x1800803cc  mov     [rsp+0F0h+samDesired], 20019h; samDesired
0x1800803d4  mov     dword ptr [rsp+0F0h+phkResult], r15d; dwOptions
0x1800803d9  call    cs:__imp_RegCreateKeyExW
0x1800803df  mov     rcx, [rbp+57h+hKey]; hKey
0x1800803e3  mov     [rbp+57h+var_A0], eax
0x1800803e6  call    cs:__imp_RegCloseKey
0x1800803ec  mov     eax, [rbp+57h+var_A0]
0x1800803ef  test    eax, eax
0x1800803f1  jz      short loc_180080411
0x1800803f3  lea     r9, aFailedToOpenKe_1; "Failed to open kerberos key: 0x%x\n"
0x1800803fa  mov     dword ptr [rsp+0F0h+phkResult], eax
0x1800803fe  mov     r8d, 7BEh
0x180080404  mov     rdx, r13
0x180080407  mov     ecx, 2
0x18008040c  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x180080411  lea     rax, [rbp+57h+var_A0]
0x180080415  lea     rcx, [rbp+57h+hKey]
0x180080419  mov     [rbp+57h+hKey], rax
0x18008041d  call    _lambda_184f7f8a374c2a0f4934929177526a3b___operator__
0x180080422  cmp     [rbp+57h+var_A0], r15d
0x180080426  jl      loc_180080B66
0x18008042c  mov     ebx, 400000h
0x180080431  call    ?KerbInitSyncObjects@@YAJXZ; KerbInitSyncObjects(void)
0x180080436  mov     [rbp+57h+var_A0], eax
0x180080439  test    eax, eax
0x18008043b  js      loc_180080B5F
0x180080441  mov     ecx, 88h; Size
0x180080446  mov     cs:?KerberosPackageId@@3_KA, r14; unsigned __int64 KerberosPackageId
0x18008044d  mov     ebx, 10400000h
0x180080452  mov     cs:?LsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA, rdi; _LSA_SECPKG_FUNCTION_TABLE * LsaFunctions
0x180080459  mov     cs:?KerbGlobalPackageState@@3W4KerberosState@@A, r12d; KerberosState KerbGlobalPackageState
0x180080460  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180080465  mov     rcx, qword ptr cs:?KerbGlobalSkewTime@@3T_LARGE_INTEGER@@A; _LARGE_INTEGER KerbGlobalSkewTime ...
0x18008046c  lea     r9, ?AuthenFree@@YAXPEAU_RTL_GENERIC_TABLE@@PEAX@Z; FreeRoutine
0x180080473  lea     r8, ?AuthenAllocate@@YAPEAXPEAU_RTL_GENERIC_TABLE@@K@Z; AllocateRoutine
0x18008047a  mov     [rsp+0F0h+phkResult], r15; TableContext
0x18008047f  lea     rdx, ?Compare@@YA?AW4_RTL_GENERIC_COMPARE_RESULTS@@PEAU_RTL_GENERIC_TABLE@@PEAX1@Z; CompareRoutine
0x180080486  mov     rdi, rax
0x180080489  mov     [rax+48h], rcx
0x18008048d  mov     rcx, rax; Table
0x180080490  mov     [rax+50h], r12d
0x180080494  mov     [rax+54h], r15b
0x180080498  mov     [rax+80h], r15b
0x18008049f  call    cs:__imp_RtlInitializeGenericTable
0x1800804a5  lea     rcx, [rdi+58h]; CriticalSection
0x1800804a9  mov     cs:?Authenticators@@3PEAVCAuthenticatorList@@EA, rdi; CAuthenticatorList * Authenticators
0x1800804b0  call    cs:__imp_RtlInitializeCriticalSection
0x1800804b6  test    eax, eax
0x1800804b8  js      loc_180080B5C
0x1800804be  mov     [rdi+80h], r12b
0x1800804c5  lea     rcx, ?KerbGlobalDHParametersLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x1800804cc  mov     [rbp+57h+var_A0], eax
0x1800804cf  call    cs:__imp_RtlInitializeCriticalSection
0x1800804d5  mov     [rbp+57h+var_A0], eax
0x1800804d8  test    eax, eax
0x1800804da  js      loc_180080B5F
0x1800804e0  call    ?KerbInitSpnCache@@YAJXZ; KerbInitSpnCache(void)
0x1800804e5  mov     [rbp+57h+var_A0], eax
0x1800804e8  test    eax, eax
0x1800804ea  jns     short loc_180080503
0x1800804ec  mov     ebx, 10600000h
0x1800804f1  lea     r9, aFailedToInitia_22; "Failed to initialize SPN cache: 0x%x"
0x1800804f8  mov     r8d, 800h
0x1800804fe  jmp     loc_180080B45
0x180080503  lea     rcx, ?KerbGlobalKdcProxyCacheLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x18008050a  call    cs:__imp_RtlInitializeCriticalSection
0x180080510  mov     [rbp+57h+var_A0], eax
0x180080513  test    eax, eax
0x180080515  jns     short loc_18008052E
0x180080517  mov     ebx, 10602000h
0x18008051c  lea     r9, aFailedToInitia_9; "Failed to initialize kdc proxy cache lo"...
0x180080523  mov     r8d, 80Ah
0x180080529  jmp     loc_180080B45
0x18008052e  mov     dl, r12b; unsigned __int8
0x180080531  lea     rcx, ?KerbGlobalKdcProxyCache@@3U_KDC_PROXY_CACHE@@A; struct _KDC_PROXY_CACHE *
0x180080538  call    ?KerbInitKdcProxyCache@@YAJPEAU_KDC_PROXY_CACHE@@E@Z; KerbInitKdcProxyCache(_KDC_PROXY_CACHE *,uchar)
0x18008053d  mov     dl, r12b; unsigned __int8
0x180080540  lea     rcx, ?KerbGlobalDnsSuffixTable@@3U_KERB_DNS_SUFFIX_TABLE@@A; struct _KERB_DNS_SUFFIX_TABLE *
0x180080547  call    ?KerbInitDnsSuffixTable@@YAJPEAU_KERB_DNS_SUFFIX_TABLE@@E@Z; KerbInitDnsSuffixTable(_KERB_DNS_SUFFIX_TABLE *,uchar)
0x18008054c  mov     [rbp+57h+var_A0], eax
0x18008054f  test    eax, eax
0x180080551  jns     short loc_18008056A
0x180080553  mov     ebx, 12602000h
0x180080558  lea     r9, aFailedToInitia_0; "Failed to initialize kdc proxy dns suff"...
0x18008055f  mov     r8d, 819h
0x180080565  jmp     loc_180080B45
0x18008056a  call    ?KerbInitDomainCache@@YAJPEAU_KERB_DOMAIN_CACHE@@@Z; KerbInitDomainCache(_KERB_DOMAIN_CACHE *)
0x18008056f  mov     [rbp+57h+var_A0], eax
0x180080572  test    eax, eax
0x180080574  jns     short loc_18008058D
0x180080576  mov     ebx, 16602000h
0x18008057b  lea     r9, aFailedToInitia_8; "Failed to initialize domain cache: %#x"
0x180080582  mov     r8d, 825h
0x180080588  jmp     loc_180080B45
0x18008058d  cmp     cs:?KerbGlobalDHParametersInitialized@@3HA, r15d; int KerbGlobalDHParametersInitialized
0x180080594  jnz     short loc_1800805AE
0x180080596  mov     cs:?KerbGlobalPreferWellknownMODPDHDomainParameters@@3KA, r12d; ulong KerbGlobalPreferWellknownMODPDHDomainParameters
0x18008059d  mov     cs:?KerbGlobalMODPDHModulusSize@@3KA, 800h; ulong KerbGlobalMODPDHModulusSize
0x1800805a7  mov     cs:?KerbGlobalDHParametersInitialized@@3HA, r12d; int KerbGlobalDHParametersInitialized
0x1800805ae  lea     rdx, pszPackageName; "Kerberos"
0x1800805b5  lea     rcx, ?KerbPackageName@@3U_UNICODE_STRING@@A; DestinationString
0x1800805bc  call    cs:__imp_RtlInitUnicodeString
0x1800805c2  lea     rdx, aRestrictedkrbh; "RestrictedKrbHost/"
0x1800805c9  lea     rcx, ?HostTargetSvc@@3U_UNICODE_STRING@@A; DestinationString
0x1800805d0  call    cs:__imp_RtlInitUnicodeString
0x1800805d6  xor     eax, eax
0x1800805d8  mov     cs:?KerbGlobalSafeModeBootOptionPresent@@3EA, r15b; uchar KerbGlobalSafeModeBootOptionPresent
0x1800805df  xorps   xmm0, xmm0
0x1800805e2  mov     [rbp+57h+var_50], eax
0x1800805e5  lea     rdx, [rbp+57h+Buffer]; lpBuffer
0x1800805e9  lea     rcx, Name; "SAFEBOOT_OPTION"
0x1800805f0  lea     r8d, [rax+12h]; nSize
0x1800805f4  movups  xmmword ptr [rbp+57h+Buffer], xmm0
0x1800805f8  movups  [rbp+57h+var_60], xmm0
0x1800805fc  call    cs:__imp_GetEnvironmentVariableW
0x180080602  test    eax, eax
0x180080604  jz      short loc_180080621
0x180080606  lea     rdx, aMinimal; "MINIMAL"
0x18008060d  lea     rcx, [rbp+57h+Buffer]; String1
0x180080611  call    wcscmp_0
0x180080616  test    eax, eax
0x180080618  jnz     short loc_180080621
0x18008061a  mov     cs:?KerbGlobalSafeModeBootOptionPresent@@3EA, r12b; uchar KerbGlobalSafeModeBootOptionPresent
0x180080621  cmp     cs:?KerbCallKdcDataInitialized@@3EA, r15b; uchar KerbCallKdcDataInitialized
0x180080628  mov     eax, r15d
0x18008062b  mov     [rbp+57h+var_A0], r15d
0x18008062f  jnz     short loc_18008064E
0x180080631  lea     rcx, ?KerbCallKdcDataLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x180080638  call    cs:__imp_RtlInitializeCriticalSection
0x18008063e  test    eax, eax
0x180080640  js      short loc_18008064E
0x180080642  mov     cs:?KerbCallKdcDataInitialized@@3EA, r12b; uchar KerbCallKdcDataInitialized
0x180080649  mov     [rbp+57h+var_A0], eax
0x18008064c  jmp     short loc_18008065E
0x18008064e  mov     [rbp+57h+var_A0], eax
0x180080651  mov     ebx, 1E602001h
0x180080656  test    eax, eax
0x180080658  js      loc_180080B5F
0x18008065e  lea     rcx, ?KerbGlobalPolicyHandle@@3PEAXEA; void * KerbGlobalPolicyHandle
0x180080665  mov     ebx, 1E602003h
0x18008066a  call    cs:__imp_LsaIOpenPolicyTrusted
0x180080670  mov     [rbp+57h+var_A0], eax
0x180080673  test    eax, eax
0x180080675  js      loc_180080B5F
0x18008067b  test    byte ptr [rsi+4], 4
0x18008067f  jz      short loc_180080688
0x180080681  mov     cs:byte_180145455, r12b
0x180080688  mov     rax, 7FFFFF36D5969FFFh
0x180080692  mov     cs:?KerbGlobalHasNeverTime@@3T_LARGE_INTEGER@@A, r15; _LARGE_INTEGER KerbGlobalHasNeverTime
0x180080699  lea     rdx, ?KerbGlobalNullLmOwfPassword@@3U_LM_OWF_PASSWORD@@A; _LM_OWF_PASSWORD KerbGlobalNullLmOwfPassword
0x1800806a0  mov     cs:?KerbGlobalWillNeverTime@@3T_LARGE_INTEGER@@A, rax; _LARGE_INTEGER KerbGlobalWillNeverTime
0x1800806a7  lea     rcx, word_1800FEE0E
0x1800806ae  call    cs:__imp_SystemFunction006
0x1800806b4  xor     edx, edx; SourceString
0x1800806b6  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1800806ba  mov     [rbp+57h+var_A0], eax
0x1800806bd  call    cs:__imp_RtlInitUnicodeString
0x1800806c3  lea     rdx, ?KerbGlobalNullNtOwfPassword@@3U_LM_OWF_PASSWORD@@A; _LM_OWF_PASSWORD KerbGlobalNullNtOwfPassword
0x1800806ca  lea     rcx, [rbp+57h+DestinationString]
0x1800806ce  call    cs:__imp_SystemFunction007
0x1800806d4  lea     rdx, aKrbtgt; "krbtgt"
0x1800806db  mov     [rbp+57h+var_A0], eax
0x1800806de  lea     rcx, ?KerbGlobalKdcServiceName@@3U_UNICODE_STRING@@A; DestinationString
0x1800806e5  call    cs:__imp_RtlInitUnicodeString
0x1800806eb  mov     cs:?KerbGlobalEnforceTime@@3EA, r15b; uchar KerbGlobalEnforceTime
0x1800806f2  mov     cs:?KerbGlobalMachineNameChanged@@3EA, r15b; uchar KerbGlobalMachineNameChanged
0x1800806f9  call    ?KerbSetComputerName@@YAJXZ; KerbSetComputerName(void)
0x1800806fe  mov     [rbp+57h+var_A0], eax
0x180080701  test    eax, eax
0x180080703  jns     short loc_180080727
0x180080705  mov     ebx, 1E602007h
0x18008070a  lea     r9, aKerbsetcompute; "KerbSetComputerName failed\n"
0x180080711  mov     r8d, 8B3h
0x180080717  mov     rdx, r13
0x18008071a  mov     ecx, r12d
0x18008071d  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x180080722  jmp     loc_180080B54
0x180080727  call    KerbInitializeScavenger
0x18008072c  mov     [rbp+57h+var_A0], eax
0x18008072f  test    eax, eax
0x180080731  jns     short loc_180080747
0x180080733  mov     ebx, 1E60200Fh
0x180080738  lea     r9, aKerbinitialize_3; "KerbInitializeScavengerFailed\n"
0x18008073f  mov     r8d, 8C1h
0x180080745  jmp     short loc_180080717
0x180080747  call    ?KerbLoadLogonSessionTable@@YAJXZ; KerbLoadLogonSessionTable(void)
0x18008074c  mov     [rbp+57h+var_A0], eax
0x18008074f  test    eax, eax
0x180080751  jns     short loc_18008076A
0x180080753  mov     ebx, 1E60201Fh
0x180080758  lea     r9, aFailedToInitia_20; "Failed to initialize logon session tabl"...
0x18008075f  mov     r8d, 8D0h
0x180080765  jmp     loc_180080B45
0x18008076a  call    ?KerbLoadProcessTable@@YAJXZ; KerbLoadProcessTable(void)
0x18008076f  mov     [rbp+57h+var_A0], eax
0x180080772  test    eax, eax
0x180080774  jns     short loc_18008078D
0x180080776  mov     ebx, 1E60203Fh
0x18008077b  lea     r9, aFailedToInitia_21; "Failed to initialize process table: %#x"
0x180080782  mov     r8d, 8DAh
0x180080788  jmp     loc_180080B45
0x18008078d  call    ?KerbInitLoopbackDetection@@YAJXZ; KerbInitLoopbackDetection(void)
0x180080792  mov     [rbp+57h+var_A0], eax
0x180080795  test    eax, eax
0x180080797  jns     short loc_1800807B0
0x180080799  mov     ebx, 3E60203Fh
0x18008079e  lea     r9, aFailedToInitia_19; "Failed to initialize network service lo"...
0x1800807a5  mov     r8d, 8E4h
0x1800807ab  jmp     loc_180080B45
0x1800807b0  call    ?KerbCreateSKeyTimer@@YAJXZ; KerbCreateSKeyTimer(void)
0x1800807b5  mov     [rbp+57h+var_A0], eax
0x1800807b8  test    eax, eax
0x1800807ba  jns     short loc_1800807D3
0x1800807bc  mov     ebx, 3E68203Fh
0x1800807c1  lea     r9, aFailedToInitia_15; "Failed to initialize network service se"...
0x1800807c8  mov     r8d, 8EEh
0x1800807ce  jmp     loc_180080B45
0x1800807d3  call    ?KerbInitGlobalVariables@@YAJXZ; KerbInitGlobalVariables(void)
0x1800807d8  test    eax, eax
0x1800807da  js      short loc_1800807E1
0x1800807dc  call    ?KerbInitializeSkewState@@YAJXZ; KerbInitializeSkewState(void)
0x1800807e1  mov     [rbp+57h+var_A0], eax
0x1800807e4  test    eax, eax
0x1800807e6  jns     short loc_1800807FF
0x1800807e8  mov     ebx, 3E78203Fh
0x1800807ed  lea     r9, aFailedToInitia_7; "Failed to initialize ticket handling: 0"...
0x1800807f4  mov     r8d, 8F8h
0x1800807fa  jmp     loc_180080B45
0x1800807ff  movups  xmm0, xmmword ptr [rsi+38h]
0x180080803  mov     r8, [rsi+10h]; void *
0x180080807  lea     rdx, [rsi+28h]; struct _UNICODE_STRING *
0x18008080b  lea     rcx, [rsi+18h]; struct _UNICODE_STRING *
0x18008080f  mov     ebx, 3E78207Fh
0x180080814  lea     r9, [rbp+57h+hKey]; struct _GUID
0x180080818  movdqu  xmmword ptr [rbp+57h+hKey], xmm0
0x18008081d  call    ?KerbSetDomainName@@YAJPEAU_UNICODE_STRING@@0PEAXU_GUID@@@Z; KerbSetDomainName(_UNICODE_STRING *,_UNICODE_STRING *,void *,_GUID)
0x180080822  mov     [rbp+57h+var_A0], eax
  ... truncated ...
```
