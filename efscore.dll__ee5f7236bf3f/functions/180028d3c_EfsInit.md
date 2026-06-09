# EfsInit

- ea: `0x180028d3c`
- end: `0x1800293f8`
- name: `EfsInit`
- size: `1724`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180010c20`

## callees

- `0x18000b884`
- `0x18001f920`
- `0x180025fd8`
- `0x1800282b0`
- `0x180028620`
- `0x180028870`
- `0x1800289b4`
- `0x180028af4`
- `0x180028c10`
- `0x180028d3c`
- `0x180041a08`
- `0x18004207c`
- `0x1800422cc`
- `0x18004e7dc`
- `0x180053770`
- `0x180056b70`
- `0x180063698`
- `0x1800716c8`
- `0x1800837d0`
- `0x1800d86e8`
- `0x1800dc8c4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180029293`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1800292a0`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1800292f7`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180029304`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180029293`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1800292a0`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1800292f7`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180029304`
- `api-ms-win-core-heap-l1-1-0!HeapSetInformation` at `0x180028d8b`
- `api-ms-win-core-heap-l1-1-0!HeapSetInformation` at `0x180028d8b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180028d74`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180028d74`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028e9d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800291c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028e9d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800291c5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029394`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800293b1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029394`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800293b1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180028f3d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180028fa1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180028f3d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180028fa1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x180028e7e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x180028e7e`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x180028e93`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x180028e93`
- `ntdll!RtlNtStatusToDosError` at `0x180028dae`
- `ntdll!RtlNtStatusToDosError` at `0x180028eec`
- `ntdll!RtlNtStatusToDosError` at `0x180028f16`
- `ntdll!RtlNtStatusToDosError` at `0x180028dae`
- `ntdll!RtlNtStatusToDosError` at `0x180028eec`
- `ntdll!RtlNtStatusToDosError` at `0x180028f16`
- `ntdll!RtlIsMultiSessionSku` at `0x1800291b1`
- `ntdll!RtlIsMultiSessionSku` at `0x1800291b1`
- `ntdll!RtlDeleteCriticalSection` at `0x1800293d3`
- `ntdll!RtlDeleteCriticalSection` at `0x1800293d3`
- `ntdll!RtlInitializeCriticalSection` at `0x180028ed1`
- `ntdll!RtlInitializeCriticalSection` at `0x180028ed1`
- `ntdll!RtlInitializeResource` at `0x180028d9e`
- `ntdll!RtlInitializeResource` at `0x180028d9e`
- `EFSUTIL!EfsUtilParseDataRecoveryPolicy_1_1` at `0x18002903a`
- `EFSUTIL!EfsUtilParseDataRecoveryPolicy_1_1` at `0x18002903a`
- `EFSUTIL!EfsUtilApplyGroupPolicy` at `0x1800291ab`
- `EFSUTIL!EfsUtilApplyGroupPolicy` at `0x1800291ab`

## string_xrefs

- `0x180028fe7`: `feclient-EfsUserCacheLimit`

## pseudocode

```c
__int64 EfsInit()
{
  HANDLE ProcessHeap; // rax
  unsigned int v1; // esi
  unsigned int v2; // r8d
  int v3; // eax
  int v4; // r8d
  int (*v5)(const unsigned __int16 *, int *, unsigned __int16 **, int *); // rdx
  int (*v6)(const unsigned __int16 *, const unsigned __int16 *); // rcx
  unsigned int (*v7)(unsigned int *, unsigned __int8 **); // r8
  int (*v8)(void *, int *); // r9
  int v9; // eax
  char v10; // r14
  __int64 *v11; // rdx
  unsigned int v12; // eax
  struct _EFS_SID_INFORMATION *v13; // rcx
  unsigned int LastError; // eax
  int v15; // eax
  unsigned int *v16; // rdx
  void **v17; // rcx
  unsigned int *v18; // r8
  NTSTATUS inited; // eax
  HLOCAL v20; // rax
  HLOCAL v21; // rax
  HRESULT v22; // eax
  unsigned int v23; // eax
  unsigned int v24; // eax
  int v25; // eax
  DWORD v26; // eax
  unsigned __int64 v27; // rsi
  PRTL_CRITICAL_SECTION v28; // rax
  unsigned int v29; // eax
  int v30; // eax
  int v31; // eax
  char v33; // [rsp+20h] [rbp-58h]
  int v34; // [rsp+40h] [rbp-38h]
  DWORD pdwValue; // [rsp+80h] [rbp+8h] BYREF
  int HeapInformation; // [rsp+88h] [rbp+10h] BYREF
  DWORD nSize; // [rsp+90h] [rbp+18h] BYREF

  nSize = 16;
  HeapInformation = 2;
  pdwValue = 0;
  CACHE_CERT_VALID_TIME = 864000000000LL;
  ProcessHeap = GetProcessHeap();
  HeapSetInformation(ProcessHeap, HeapCompatibilityInformation, &HeapInformation, 4u);
  SafeAllocaInitialize();
  RtlInitializeResource(&RecoveryPolicyResource);
  EfsInitializeDecryptionProcessing();
  v9 = EdpCredSvcInitialize(v6, v5, v7, v8);
  if ( v9 < 0 )
  {
    v1 = (unsigned __int16)v9;
    if ( (v9 & 0x1FFF0000) != 0x70000 )
      v1 = 31;
    v10 = -51;
LABEL_10:
    v2 = v1;
LABEL_11:
    v11 = (__int64 *)&EFS_API_ERROR;
    goto LABEL_4;
  }
  v12 = EfsRegisterCallTables();
  v1 = v12;
  if ( v12 )
  {
    v10 = -46;
    v2 = v12;
    goto LABEL_11;
  }
  LastError = EfspPopulateSIDInformation(v13);
  v1 = LastError;
  if ( LastError )
  {
    v10 = -41;
    v11 = EFS_SERVICE_INIT_SIDINFO_ERROR;
    goto LABEL_3;
  }
  GetSystemInfo(&g_si);
  if ( !GetComputerNameW(&EfsComputerName, &nSize) )
  {
    LastError = GetLastError();
    v10 = -33;
    v11 = EFS_SERVICE_INIT_COMPNAME_ERROR;
LABEL_2:
    v1 = LastError;
LABEL_3:
    v2 = LastError;
LABEL_4:
    v3 = fnEfsLogTrace1(g_hPublisher, (_DWORD)v11, v2, 15, v10);
    v33 = v10;
    v4 = v3;
LABEL_5:
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v4, 15, v33);
    goto LABEL_58;
  }
  qword_180117160 = (__int64)&UserCacheList;
  UserCacheList.Flink = &UserCacheList;
  v15 = RtlInitializeCriticalSection(&GuardCacheListLock);
  v34 = v15;
  if ( v15 < 0 )
  {
    LastError = RtlNtStatusToDosError(v15);
    v10 = -14;
    v11 = (__int64 *)&EFS_SERVICE_INIT_CACHELOCK_ERROR;
    goto LABEL_2;
  }
  bGuardCacheListLockInitialized = 1;
  inited = EfspServerInit_BCrypt(v17, v16, v18);
  if ( inited < 0 )
  {
    LastError = RtlNtStatusToDosError(inited);
    v10 = 1;
    v11 = EFS_SERVICE_INIT_BCRYPT_ERROR;
    goto LABEL_2;
  }
  v20 = LocalAlloc(0x40u, 8u);
  TemplateName = v20;
  if ( !v20 )
  {
    v33 = 7;
LABEL_24:
    v1 = 8;
    v4 = 8;
    goto LABEL_5;
  }
  if ( StringCchCopyW((unsigned __int16 *)v20, 4u, L"EFS") < 0 )
  {
    v33 = 13;
LABEL_27:
    v4 = 111;
    v1 = 111;
    goto LABEL_5;
  }
  v21 = LocalAlloc(0x40u, 0x14u);
  SuiteBAlgorithm = v21;
  if ( !v21 )
  {
    v33 = 19;
    goto LABEL_24;
  }
  if ( StringCchCopyW((unsigned __int16 *)v21, 0xAu, L"ECDH_P256") < 0 )
  {
    v33 = 25;
    goto LABEL_27;
  }
  v22 = SLGetWindowsInformationDWORD(L"feclient-EfsUserCacheLimit", &pdwValue);
  if ( v22 >= 0 )
    UserCacheListLimit = pdwValue;
  else
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_SERVICE_INIT_SL_ERROR, v22, 15, 42);
  EfsSetupEfsOptionsFromRegistry();
  EfsUtilParseDataRecoveryPolicy_1_1(0, &CurrentRecoveryPolicy);
  EfspRoleChangeCallback_ThreadProc(0, 0);
  EfsOptions = EfspInDomain != 0 ? 22 : 1046;
  DWORD2(xmmword_180117210) = 4;
  *(_QWORD *)&xmmword_180117210 = EfspRoleChangeCallback_ThreadProc;
  v23 = EfspSetupLSANotification(&EfsRoleChangeContext);
  if ( v23 )
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_SERVICE_INIT_LSANOTIFY_ERROR, v23, 15, 90);
  qword_1801171C8 = (__int64)&EfsDisabled;
  qword_1801171D0 = (__int64)&EfsOptions;
  qword_1801171F0 = (__int64)&RsaKeyLength;
  qword_1801171F8 = (__int64)&CacheTimeout;
  qword_1801171D8 = (__int64)&TemplateName;
  qword_1801171E0 = (__int64)&SuiteBAlgorithm;
  qword_1801171E8 = (__int64)&SuiteBPolicy;
  qword_1801171C0 = (__int64)EfspGPCallback_ThreadProc;
  v24 = EfspSetupGPNotification(&EfsGPContext);
  if ( v24 )
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_SERVICE_INIT_GPNOTIFY_ERROR, v24, 15, 117);
  v25 = EfsProcessRecoveryPolicy();
  if ( v25 )
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_SERVICE_INIT_PROCESSRECPOLICY_ERROR, v25, 15, 133);
  EfsUtilApplyGroupPolicy(
    &EfspInDomain,
    &EfsDisabled,
    &EfsOptions,
    &RsaKeyLength,
    &CacheTimeout,
    &TemplateName,
    &SuiteBAlgorithm,
    &SuiteBPolicy,
    v34);
  RtlIsMultiSessionSku();
  EfsMdmCheckEdpPolicyCached();
  if ( (unsigned int)EfsMdmSetupHandler() )
  {
    v26 = GetLastError();
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_SERVICE_INIT_LOCK_ERROR, v26, 15, 168);
  }
  v27 = 0;
  v28 = pEfsMdmContext;
  while ( v28 && v27 < 3 )
  {
    if ( !*((_QWORD *)&v28[3].LockSemaphore + v27) )
    {
      fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_SERVICE_INIT_WNF_ERROR, v27, 15, 179);
      v28 = pEfsMdmContext;
    }
    ++v27;
  }
  v29 = EfspProcessUserSessions();
  if ( v29 )
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_SERVICE_INIT_PROCESSUSERSESSIONS_ERROR, v29, 15, 198);
  v30 = EfspInitializeFileEncryptionQueue();
  if ( v30 < 0 )
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_SERVICE_EDP_FEQ_INITIALIZATION_ERROR, v30, 15, 210);
  InitializeSRWLock(&g_AppInfoCacheLock);
  InitializeSRWLock(&g_AuditAppWorkLock);
  qword_180116F90 = (__int64)&g_AppInfoCache;
  g_AppInfoCache.Flink = &g_AppInfoCache;
  qword_180116F80 = (__int64)&g_AuditAppWork;
  g_AuditAppWork.Flink = &g_AuditAppWork;
  g_AppInfoCacheItem = 0;
  g_AuditAppWorkItem = 0;
  EdpInitModeSpecific();
  g_WorkQueueInitialized = 1;
  InitializeSRWLock(&g_AuditSiteWorkLock);
  InitializeSRWLock(&g_SiteInfoCacheLock);
  qword_180116EE0 = (__int64)&g_AuditSiteWork;
  g_AuditSiteWork.Flink = &g_AuditSiteWork;
  qword_180116EC8 = (__int64)&g_SiteInfoCache;
  g_SiteInfoCache.Flink = &g_SiteInfoCache;
  g_SiteInfoCacheItem = 0;
  g_AuditSiteWorkItem = 0;
  g_SiteWorkQueueInitialized = 1;
  v31 = OefsInitialize();
  if ( v31 < 0 )
  {
    v1 = (unsigned __int16)v31;
    if ( (v31 & 0x1FFF0000) != 0x70000 )
      v1 = 31;
    v10 = -33;
    goto LABEL_10;
  }
  EfsDllInitialized = 1;
  v1 = 0;
LABEL_58:
  if ( v1 )
  {
    if ( TemplateName )
    {
      LocalFree(TemplateName);
      TemplateName = 0;
    }
    if ( SuiteBAlgorithm )
    {
      LocalFree(SuiteBAlgorithm);
      SuiteBAlgorithm = 0;
    }
    if ( bGuardCacheListLockInitialized )
    {
      RtlDeleteCriticalSection(&GuardCacheListLock);
      bGuardCacheListLockInitialized = 0;
    }
  }
  return v1;
}

```

## disassembly

```asm
0x180028d3c  mov     rax, rsp
0x180028d3f  mov     [rax+20h], rsi
0x180028d43  push    rdi
0x180028d44  push    r12
0x180028d46  push    r13
0x180028d48  push    r14
0x180028d4a  push    r15
0x180028d4c  sub     rsp, 50h
0x180028d50  xor     edi, edi
0x180028d52  mov     dword ptr [rax+18h], 10h
0x180028d59  mov     dword ptr [rax+10h], 2
0x180028d60  mov     [rax+8], edi
0x180028d63  mov     rax, 0C92A69C000h
0x180028d6d  mov     cs:?CACHE_CERT_VALID_TIME@@3_JA, rax; __int64 CACHE_CERT_VALID_TIME
0x180028d74  call    cs:__imp_GetProcessHeap
0x180028d7a  mov     rcx, rax; HeapHandle
0x180028d7d  lea     r9d, [rdi+4]; HeapInformationLength
0x180028d81  lea     r8, [rsp+78h+HeapInformation]; HeapInformation
0x180028d89  xor     edx, edx; HeapInformationClass
0x180028d8b  call    cs:__imp_HeapSetInformation
0x180028d91  call    SafeAllocaInitialize
0x180028d96  nop
0x180028d97  lea     rcx, ?RecoveryPolicyResource@@3U_RTL_RESOURCE@@A; Resource
0x180028d9e  call    cs:__imp_RtlInitializeResource
0x180028da4  jmp     short loc_180028DA8
0x180028da6  mov     edi, eax
0x180028da8  test    edi, edi
0x180028daa  jns     short loc_180028E02
0x180028dac  mov     ecx, edi; Status
0x180028dae  call    cs:__imp_RtlNtStatusToDosError
0x180028db4  mov     r14d, 0C0h
0x180028dba  lea     rdx, EFS_SERVICE_INIT_RECPOLRESOURCE_ERROR
0x180028dc1  mov     esi, eax
0x180028dc3  mov     edi, 0Fh
0x180028dc8  mov     r8d, eax
0x180028dcb  mov     dword ptr [rsp+78h+var_58], r14d
0x180028dd0  mov     r9d, edi
0x180028dd3  mov     rcx, cs:g_hPublisher
0x180028dda  call    fnEfsLogTrace1
0x180028ddf  mov     dword ptr [rsp+78h+var_58], r14d
0x180028de4  mov     r9d, edi
0x180028de7  mov     r8d, eax
0x180028dea  lea     rdx, EFS_TRACE_ERROR
0x180028df1  mov     rcx, cs:g_hPublisher
0x180028df8  call    fnEfsLogTrace1
0x180028dfd  jmp     loc_180029384
0x180028e02  call    ?EfsInitializeDecryptionProcessing@@YAXXZ; EfsInitializeDecryptionProcessing(void)
0x180028e07  call    ?EdpCredSvcInitialize@@YAJP6AJPEBG0@ZP6AJ0PEAHPEAPEAG2@ZP6AKPEAKPEAPEAE@ZP6AJPEAX2@Z@Z; EdpCredSvcInitialize(long (*)(ushort const *,ushort const *),long (*)(ushort const *,int *,ushort * *,int *),ulong (*)(ulong *,uchar * *),long (*)(void *,int *))
0x180028e0c  test    eax, eax
0x180028e0e  jns     short loc_180028E3F
0x180028e10  mov     ecx, eax
0x180028e12  and     ecx, 1FFF0000h
0x180028e18  cmp     ecx, 70000h
0x180028e1e  movzx   esi, ax
0x180028e21  jz      short loc_180028E28
0x180028e23  mov     esi, 1Fh
0x180028e28  mov     r14d, 0CDh
0x180028e2e  mov     edi, 0Fh
0x180028e33  mov     r8d, esi
0x180028e36  lea     rdx, EFS_API_ERROR
0x180028e3d  jmp     short loc_180028DCB
0x180028e3f  call    ?EfsRegisterCallTables@@YAKXZ; EfsRegisterCallTables(void)
0x180028e44  mov     esi, eax
0x180028e46  test    eax, eax
0x180028e48  jz      short loc_180028E5A
0x180028e4a  mov     r14d, 0D2h
0x180028e50  mov     edi, 0Fh
0x180028e55  mov     r8d, eax
0x180028e58  jmp     short loc_180028E36
0x180028e5a  call    ?EfspPopulateSIDInformation@@YAKPEAU_EFS_SID_INFORMATION@@@Z; EfspPopulateSIDInformation(_EFS_SID_INFORMATION *)
0x180028e5f  mov     esi, eax
0x180028e61  test    eax, eax
0x180028e63  jz      short loc_180028E77
0x180028e65  mov     r14d, 0D7h
0x180028e6b  lea     rdx, EFS_SERVICE_INIT_SIDINFO_ERROR
0x180028e72  jmp     loc_180028DC3
0x180028e77  lea     rcx, ?g_si@@3U_SYSTEM_INFO@@A; lpSystemInfo
0x180028e7e  call    cs:__imp_GetSystemInfo
0x180028e84  lea     rdx, [rsp+78h+nSize]; nSize
0x180028e8c  lea     rcx, ?EfsComputerName@@3PAGA; lpBuffer
0x180028e93  call    cs:__imp_GetComputerNameW
0x180028e99  test    eax, eax
0x180028e9b  jnz     short loc_180028EB5
0x180028e9d  call    cs:__imp_GetLastError
0x180028ea3  mov     r14d, 0DFh
0x180028ea9  lea     rdx, EFS_SERVICE_INIT_COMPNAME_ERROR
0x180028eb0  jmp     loc_180028DC1
0x180028eb5  lea     rax, ?UserCacheList@@3U_LIST_ENTRY@@A; _LIST_ENTRY UserCacheList
0x180028ebc  mov     cs:qword_180117160, rax
0x180028ec3  mov     cs:?UserCacheList@@3U_LIST_ENTRY@@A, rax; _LIST_ENTRY UserCacheList
0x180028eca  lea     rcx, ?GuardCacheListLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x180028ed1  call    cs:__imp_RtlInitializeCriticalSection
0x180028ed7  mov     [rsp+78h+var_38], eax
0x180028edb  jmp     short loc_180028EE6
0x180028edd  mov     eax, 0C0000017h
0x180028ee2  mov     [rsp+78h+var_38], eax
0x180028ee6  test    eax, eax
0x180028ee8  jns     short loc_180028F04
0x180028eea  mov     ecx, eax; Status
0x180028eec  call    cs:__imp_RtlNtStatusToDosError
0x180028ef2  mov     r14d, 0F2h
0x180028ef8  lea     rdx, EFS_SERVICE_INIT_CACHELOCK_ERROR; unsigned int *
0x180028eff  jmp     loc_180028DC1
0x180028f04  mov     cs:?bGuardCacheListLockInitialized@@3EC, 1; uchar volatile bGuardCacheListLockInitialized
0x180028f0b  call    ?EfspServerInit_BCrypt@@YAJPEAPEAXPEAK1@Z; EfspServerInit_BCrypt(void * *,ulong *,ulong *)
0x180028f10  test    eax, eax
0x180028f12  jns     short loc_180028F2E
0x180028f14  mov     ecx, eax; Status
0x180028f16  call    cs:__imp_RtlNtStatusToDosError
0x180028f1c  mov     r14d, 101h
0x180028f22  lea     rdx, EFS_SERVICE_INIT_BCRYPT_ERROR
0x180028f29  jmp     loc_180028DC1
0x180028f2e  mov     r14d, 8
0x180028f34  mov     edx, r14d; uBytes
0x180028f37  lea     edi, [r14+38h]
0x180028f3b  mov     ecx, edi; uFlags
0x180028f3d  call    cs:__imp_LocalAlloc
0x180028f43  mov     cs:?TemplateName@@3PEAGEA, rax; ushort * TemplateName
0x180028f4a  test    rax, rax
0x180028f4d  jnz     short loc_180028F68
0x180028f4f  mov     dword ptr [rsp+78h+var_58], 107h
0x180028f57  mov     esi, r14d
0x180028f5a  mov     r9d, 0Fh
0x180028f60  mov     r8d, r14d
0x180028f63  jmp     loc_180028DEA
0x180028f68  lea     r8, aEfs; "EFS"
0x180028f6f  mov     edx, 4; unsigned __int64
0x180028f74  mov     rcx, rax; unsigned __int16 *
0x180028f77  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180028f7c  test    eax, eax
0x180028f7e  jns     short loc_180028F9A
0x180028f80  mov     dword ptr [rsp+78h+var_58], 10Dh
0x180028f88  mov     r8d, 6Fh ; 'o'
0x180028f8e  mov     esi, r8d
0x180028f91  lea     r9d, [r8-60h]
0x180028f95  jmp     loc_180028DEA
0x180028f9a  mov     edx, 14h; uBytes
0x180028f9f  mov     ecx, edi; uFlags
0x180028fa1  call    cs:__imp_LocalAlloc
0x180028fa7  mov     cs:?SuiteBAlgorithm@@3PEAGEA, rax; ushort * SuiteBAlgorithm
0x180028fae  test    rax, rax
0x180028fb1  jnz     short loc_180028FBD
0x180028fb3  mov     dword ptr [rsp+78h+var_58], 113h
0x180028fbb  jmp     short loc_180028F57
0x180028fbd  lea     r8, aEcdhP256; "ECDH_P256"
0x180028fc4  mov     edx, 0Ah; unsigned __int64
0x180028fc9  mov     rcx, rax; unsigned __int16 *
0x180028fcc  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180028fd1  test    eax, eax
0x180028fd3  jns     short loc_180028FDF
0x180028fd5  mov     dword ptr [rsp+78h+var_58], 119h
0x180028fdd  jmp     short loc_180028F88
0x180028fdf  lea     rdx, [rsp+78h+pdwValue]; pdwValue
0x180028fe7  lea     rcx, pwszValueName; "feclient-EfsUserCacheLimit"
0x180028fee  call    SLGetWindowsInformationDWORD
0x180028ff3  mov     edi, 0Fh
0x180028ff8  test    eax, eax
0x180028ffa  jns     short loc_18002901F
0x180028ffc  mov     dword ptr [rsp+78h+var_58], 12Ah
0x180029004  mov     r9d, edi
0x180029007  mov     r8d, eax
0x18002900a  lea     rdx, EFS_SERVICE_INIT_SL_ERROR
0x180029011  mov     rcx, cs:g_hPublisher
0x180029018  call    fnEfsLogTrace1
0x18002901d  jmp     short loc_18002902C
0x18002901f  mov     eax, [rsp+78h+pdwValue]
0x180029026  mov     cs:?UserCacheListLimit@@3JA, eax; long UserCacheListLimit
0x18002902c  call    EfsSetupEfsOptionsFromRegistry
0x180029031  lea     rdx, ?CurrentRecoveryPolicy@@3U_CURRENT_RECOVERY_POLICY@@A; _CURRENT_RECOVERY_POLICY CurrentRecoveryPolicy
0x180029038  xor     ecx, ecx
0x18002903a  call    cs:__imp_EfsUtilParseDataRecoveryPolicy_1_1
0x180029040  xor     edx, edx; unsigned __int8
0x180029042  xor     ecx, ecx; Context
0x180029044  call    ?EfspRoleChangeCallback_ThreadProc@@YAXPEAXE@Z; EfspRoleChangeCallback_ThreadProc(void *,uchar)
0x180029049  mov     al, cs:?EfspInDomain@@3EA; uchar EfspInDomain
0x18002904f  neg     al
0x180029051  sbb     ecx, ecx
0x180029053  and     ecx, 0FFFFFC00h
0x180029059  add     ecx, 416h
0x18002905f  mov     cs:?EfsOptions@@3KA, ecx; ulong EfsOptions
0x180029065  mov     dword ptr cs:xmmword_180117210+8, 4
0x18002906f  lea     rax, ?EfspRoleChangeCallback_ThreadProc@@YAXPEAXE@Z; EfspRoleChangeCallback_ThreadProc(void *,uchar)
0x180029076  mov     qword ptr cs:xmmword_180117210, rax
0x18002907d  lea     rcx, ?EfsRoleChangeContext@@3U_EFS_LSA_NOTIFICATION_CONTEXT@@A; Context
0x180029084  call    ?EfspSetupLSANotification@@YAKPEAU_EFS_LSA_NOTIFICATION_CONTEXT@@@Z; EfspSetupLSANotification(_EFS_LSA_NOTIFICATION_CONTEXT *)
0x180029089  test    eax, eax
0x18002908b  jz      short loc_1800290AE
0x18002908d  mov     dword ptr [rsp+78h+var_58], 15Ah
0x180029095  mov     r9d, edi
0x180029098  mov     r8d, eax
0x18002909b  lea     rdx, EFS_SERVICE_INIT_LSANOTIFY_ERROR
0x1800290a2  mov     rcx, cs:g_hPublisher
0x1800290a9  call    fnEfsLogTrace1
0x1800290ae  lea     rsi, ?EfsDisabled@@3EA; uchar EfsDisabled
0x1800290b5  mov     cs:qword_1801171C8, rsi
0x1800290bc  lea     r14, ?EfsOptions@@3KA; ulong EfsOptions
0x1800290c3  mov     cs:qword_1801171D0, r14
0x1800290ca  lea     r15, ?RsaKeyLength@@3KA; ulong RsaKeyLength
0x1800290d1  mov     cs:qword_1801171F0, r15
0x1800290d8  lea     rax, ?CacheTimeout@@3KA; ulong CacheTimeout
0x1800290df  mov     cs:qword_1801171F8, rax
0x1800290e6  lea     rax, ?TemplateName@@3PEAGEA; ushort * TemplateName
0x1800290ed  mov     cs:qword_1801171D8, rax
0x1800290f4  lea     r13, ?SuiteBAlgorithm@@3PEAGEA; ushort * SuiteBAlgorithm
0x1800290fb  mov     cs:qword_1801171E0, r13
0x180029102  lea     r12, ?SuiteBPolicy@@3W4EFS_SUITE_B_POLICY@@A; EFS_SUITE_B_POLICY SuiteBPolicy
0x180029109  mov     cs:qword_1801171E8, r12
0x180029110  lea     rax, ?EfspGPCallback_ThreadProc@@YAXPEAXE@Z; EfspGPCallback_ThreadProc(void *,uchar)
0x180029117  mov     cs:qword_1801171C0, rax
0x18002911e  lea     rcx, ?EfsGPContext@@3U_EFS_GP_NOTIFICATION_CONTEXT@@A; Context
0x180029125  call    ?EfspSetupGPNotification@@YAKPEAU_EFS_GP_NOTIFICATION_CONTEXT@@@Z; EfspSetupGPNotification(_EFS_GP_NOTIFICATION_CONTEXT *)
0x18002912a  test    eax, eax
0x18002912c  jz      short loc_18002914F
0x18002912e  mov     dword ptr [rsp+78h+var_58], 175h
0x180029136  mov     r9d, edi
0x180029139  mov     r8d, eax
0x18002913c  lea     rdx, EFS_SERVICE_INIT_GPNOTIFY_ERROR
0x180029143  mov     rcx, cs:g_hPublisher
0x18002914a  call    fnEfsLogTrace1
0x18002914f  call    EfsProcessRecoveryPolicy
0x180029154  test    eax, eax
0x180029156  jz      short loc_180029179
0x180029158  mov     dword ptr [rsp+78h+var_58], 185h
0x180029160  mov     r9d, edi
0x180029163  mov     r8d, eax
0x180029166  lea     rdx, EFS_SERVICE_INIT_PROCESSRECPOLICY_ERROR
0x18002916d  mov     rcx, cs:g_hPublisher
0x180029174  call    fnEfsLogTrace1
0x180029179  mov     [rsp+78h+var_40], r12
0x18002917e  mov     [rsp+78h+var_48], r13
0x180029183  lea     rax, ?TemplateName@@3PEAGEA; ushort * TemplateName
0x18002918a  mov     [rsp+78h+var_50], rax
0x18002918f  lea     rax, ?CacheTimeout@@3KA; ulong CacheTimeout
0x180029196  mov     [rsp+78h+var_58], rax
0x18002919b  mov     r9, r15
0x18002919e  mov     r8, r14
0x1800291a1  mov     rdx, rsi
0x1800291a4  lea     rcx, ?EfspInDomain@@3EA; uchar EfspInDomain
0x1800291ab  call    cs:__imp_EfsUtilApplyGroupPolicy
0x1800291b1  call    cs:__imp_RtlIsMultiSessionSku
0x1800291b7  call    EfsMdmCheckEdpPolicyCached
0x1800291bc  call    EfsMdmSetupHandler
0x1800291c1  test    eax, eax
0x1800291c3  jz      short loc_1800291EC
0x1800291c5  call    cs:__imp_GetLastError
0x1800291cb  mov     dword ptr [rsp+78h+var_58], 1A8h
0x1800291d3  mov     r9d, edi
0x1800291d6  mov     r8d, eax
0x1800291d9  lea     rdx, EFS_SERVICE_INIT_LOCK_ERROR
0x1800291e0  mov     rcx, cs:g_hPublisher
0x1800291e7  call    fnEfsLogTrace1
0x1800291ec  xor     esi, esi
0x1800291ee  mov     rax, cs:pEfsMdmContext
0x1800291f5  jmp     short loc_180029233
0x1800291f7  cmp     rsi, 3
0x1800291fb  jnb     short loc_180029238
0x1800291fd  cmp     qword ptr [rax+rsi*8+90h], 0
0x180029206  jnz     short loc_180029230
0x180029208  mov     r8d, esi
0x18002920b  mov     dword ptr [rsp+78h+var_58], 1B3h
0x180029213  mov     r9d, edi
0x180029216  lea     rdx, EFS_SERVICE_INIT_WNF_ERROR
0x18002921d  mov     rcx, cs:g_hPublisher
0x180029224  call    fnEfsLogTrace1
0x180029229  mov     rax, cs:pEfsMdmContext
0x180029230  inc     rsi
0x180029233  test    rax, rax
0x180029236  jnz     short loc_1800291F7
0x180029238  call    ?EfspProcessUserSessions@@YAKXZ; EfspProcessUserSessions(void)
0x18002923d  test    eax, eax
0x18002923f  jz      short loc_180029262
0x180029241  mov     dword ptr [rsp+78h+var_58], 1C6h
0x180029249  mov     r9d, edi
0x18002924c  mov     r8d, eax
0x18002924f  lea     rdx, EFS_SERVICE_INIT_PROCESSUSERSESSIONS_ERROR
0x180029256  mov     rcx, cs:g_hPublisher
0x18002925d  call    fnEfsLogTrace1
0x180029262  call    ?EfspInitializeFileEncryptionQueue@@YAJXZ; EfspInitializeFileEncryptionQueue(void)
0x180029267  test    eax, eax
0x180029269  jns     short loc_18002928C
0x18002926b  mov     dword ptr [rsp+78h+var_58], 1D2h
0x180029273  mov     r9d, edi
0x180029276  mov     r8d, eax
0x180029279  lea     rdx, EFS_SERVICE_EDP_FEQ_INITIALIZATION_ERROR
0x180029280  mov     rcx, cs:g_hPublisher
0x180029287  call    fnEfsLogTrace1
0x18002928c  lea     rcx, ?g_AppInfoCacheLock@@3U_RTL_SRWLOCK@@A; SRWLock
0x180029293  call    cs:__imp_InitializeSRWLock
0x180029299  lea     rcx, ?g_AuditAppWorkLock@@3U_RTL_SRWLOCK@@A; SRWLock
0x1800292a0  call    cs:__imp_InitializeSRWLock
0x1800292a6  lea     rax, ?g_AppInfoCache@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_AppInfoCache
0x1800292ad  mov     cs:qword_180116F90, rax
0x1800292b4  mov     cs:?g_AppInfoCache@@3U_LIST_ENTRY@@A, rax; _LIST_ENTRY g_AppInfoCache
0x1800292bb  lea     rax, ?g_AuditAppWork@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_AuditAppWork
0x1800292c2  mov     cs:qword_180116F80, rax
0x1800292c9  mov     cs:?g_AuditAppWork@@3U_LIST_ENTRY@@A, rax; _LIST_ENTRY g_AuditAppWork
0x1800292d0  mov     cs:?g_AppInfoCacheItem@@3KA, 0; ulong g_AppInfoCacheItem
0x1800292da  mov     cs:?g_AuditAppWorkItem@@3KA, 0; ulong g_AuditAppWorkItem
0x1800292e4  call    EdpInitModeSpecific
0x1800292e9  mov     cs:?g_WorkQueueInitialized@@3EA, 1; uchar g_WorkQueueInitialized
  ... truncated ...
```
