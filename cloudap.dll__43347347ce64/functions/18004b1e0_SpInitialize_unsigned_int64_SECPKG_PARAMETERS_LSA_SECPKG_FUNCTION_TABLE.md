# SpInitialize(unsigned __int64,_SECPKG_PARAMETERS *,_LSA_SECPKG_FUNCTION_TABLE *)

- ea: `0x18004b1e0`
- end: `0x18004b878`
- name: `?SpInitialize@@YAJ_KPEAU_SECPKG_PARAMETERS@@PEAU_LSA_SECPKG_FUNCTION_TABLE@@@Z`
- size: `1688`
- prototype: `__int64 __fastcall(unsigned __int64, struct _SECPKG_PARAMETERS *, struct _LSA_SECPKG_FUNCTION_TABLE *)`
- caller_count: `0`
- callee_count: `16`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180007fc0`
- `0x18000a600`
- `0x180011294`
- `0x180011424`
- `0x180019e48`
- `0x18003f3b0`
- `0x18003ff84`
- `0x18004a05c`
- `0x18004a218`
- `0x18004a340`
- `0x18004a3c0`
- `0x18004a52c`
- `0x18004b1e0`
- `0x18004b9ec`
- `0x18005f84c`
- `0x180066350`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x18004b592`
- `ntdll!RtlAcquireResourceExclusive` at `0x18004b592`
- `ntdll!RtlReleaseResource` at `0x18004b85a`
- `ntdll!RtlReleaseResource` at `0x18004b85a`
- `ntdll!RtlInitializeResource` at `0x18004b2d6`
- `ntdll!RtlInitializeResource` at `0x18004b304`
- `ntdll!RtlInitializeResource` at `0x18004b32d`
- `ntdll!RtlInitializeResource` at `0x18004b356`
- `ntdll!RtlInitializeResource` at `0x18004b37f`
- `ntdll!RtlInitializeResource` at `0x18004b393`
- `ntdll!RtlInitializeResource` at `0x18004b3a7`
- `ntdll!RtlInitializeResource` at `0x18004b2d6`
- `ntdll!RtlInitializeResource` at `0x18004b304`
- `ntdll!RtlInitializeResource` at `0x18004b32d`
- `ntdll!RtlInitializeResource` at `0x18004b356`
- `ntdll!RtlInitializeResource` at `0x18004b37f`
- `ntdll!RtlInitializeResource` at `0x18004b393`
- `ntdll!RtlInitializeResource` at `0x18004b3a7`

## string_xrefs

- `0x18004b3ef`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x18004b45b`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x18004b497`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x18004b4d6`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x18004b515`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x18004b554`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x18004b5a7`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x18004b601`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x18004b620`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x18004b664`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x18004b6ab`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x18004b6f2`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x18004b739`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x18004b780`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x18004b7c7`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x18004b80b`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x18004b4b2`: `InitializeComputerName`
- `0x18004b56f`: `InitializeCloudAPCache`
- `0x18004b5c2`: `InitializePlugins`
- `0x18004b63b`: `KerbCommInitialize`

## pseudocode

```c
__int64 __fastcall SpInitialize(
        unsigned __int64 a1,
        struct _SECPKG_PARAMETERS *a2,
        struct _LSA_SECPKG_FUNCTION_TABLE *a3)
{
  unsigned int v4; // ebx
  const char *v5; // r9
  const char *v6; // r9
  const char *v7; // r9
  const char *v8; // r9
  const char *v9; // r9
  const char *v10; // r9
  const char *v11; // r9
  int v12; // eax
  const char *v13; // r9
  __int64 v15; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  int v17; // [rsp+50h] [rbp+8h]

  v17 = 0;
  g_ulpCloudAPPackageId = a1;
  g_pLsaFunctionTable = a3;
  g_CloudAPFunctionTable = a3->ImpersonateClient;
  qword_18009AFB8 = (__int64)a3->LsaProtectMemory;
  qword_18009AFC0 = (__int64)a3->LsaUnprotectMemory;
  qword_18009AFC8 = (__int64)a3->OpenTokenByLogonId;
  qword_18009AFD0 = (__int64)a3->AllocateLsaHeap;
  qword_18009AFD8 = (__int64)a3->FreeLsaHeap;
  qword_18009AFE0 = (__int64)AllocateUserInfo;
  qword_18009AFE8 = (__int64)FreeUserInfo;
  qword_18009AFF0 = (__int64)a3->DummyFunction1;
  qword_18009B000 = (__int64)a3->DummyFunction4;
  qword_18009AFF8 = (__int64)a3->DummyFunction3;
  qword_18009B008 = (__int64)SignMessageWithNgc;
  qword_18009B010 = (__int64)a3->GetCallInfo;
  g_TimeForever.QuadPart = 0x7FFFFF36D5969FFFLL;
  g_TimeNever.QuadPart = 0;
  RtlInitializeResource(&g_LogonSessionListLock);
  g_bLogonSessionListLockInitialized = 1;
  qword_18009ACE8 = (__int64)&g_LogonSessionList;
  g_LogonSessionList = (struct _LOGON_SESSION *)&g_LogonSessionList;
  RtlInitializeResource(&g_UserCacheListLock);
  g_bUserCacheListLockInitialized = 1;
  qword_18009ACD8 = (__int64)&g_UserCacheList;
  g_UserCacheList.Flink = &g_UserCacheList;
  RtlInitializeResource(&g_StaleUserCacheListLock);
  g_bStaleUserCacheListLockInitialized = 1;
  qword_18009ACC8 = (__int64)&g_StaleUserCacheList;
  g_StaleUserCacheList = (struct _USER_CACHE_ENTRY *)&g_StaleUserCacheList;
  RtlInitializeResource(&g_UserLockList_Lock);
  g_bUserLockList_LockInitialized = 1;
  qword_18009ACB8 = (__int64)&g_UserLockList;
  g_UserLockList.Flink = &g_UserLockList;
  RtlInitializeResource(&g_PackageListLock);
  g_bPackageListLockInitialized = 1;
  RtlInitializeResource(&g_LookupsCacheLock);
  g_bLookupsCacheLockInitialized = 1;
  RtlInitializeResource(&g_AadConnectMapLock);
  g_bAadConnectMapLockInitialized = 1;
  qword_18009AEE8 = (__int64)&g_MappedAccountCacheList;
  g_MappedAccountCacheList = &g_MappedAccountCacheList;
  qword_18009AED8 = (__int64)&g_MappedUserNameHashList;
  g_MappedUserNameHashList = &g_MappedUserNameHashList;
  if ( (a2->MachineState & 0x20) != 0 )
  {
    v4 = InitializeCredentialIsolation();
    if ( v4 )
    {
      v5 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v4, v5, 723, "InitializeCredentialIsolation", &Class);
      goto LABEL_24;
    }
    qword_18009B018 = (__int64)GenerateKeyBindingKeyPair;
    qword_18009B020 = (__int64)VerifyKeyBindingKeyPair;
  }
  v4 = InitializePackageGlobals();
  if ( v4 )
  {
    v6 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v4, v6, 734, "InitializePackageGlobals", &Class);
  }
  else
  {
    v4 = InitializeComputerName();
    if ( v4 )
    {
      v7 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v4, v7, 737, "InitializeComputerName", &Class);
    }
    else
    {
      v4 = InitializeCrypto();
      if ( v4 )
      {
        v8 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v4, v8, 740, "InitializeCrypto", &Class);
      }
      else
      {
        v4 = InitializeMisc();
        if ( v4 )
        {
          v9 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
          WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v4, v9, 743, "InitializeMisc", &Class);
        }
        else
        {
          v4 = InitializeCloudAPCache();
          if ( v4 )
          {
            v10 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
            WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v4, v10, 746, "InitializeCloudAPCache", &Class);
          }
          else
          {
            RtlAcquireResourceExclusive(&g_PackageListLock, 1u);
            v17 = 1;
            v4 = InitializePlugins();
            if ( v4 )
            {
              v11 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
              WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v4, v11, 755, "InitializePlugins", &Class);
            }
            else
            {
              wil::details::FeatureImpl<__WilFeatureTraits_Feature_SyncDpapiCredKeyToUserProfile>::__private_IsEnabledPreCheck(`wil::Feature<__WilFeatureTraits_Feature_SyncDpapiCredKeyToUserProfile>::GetImpl'::`2'::impl);
              if ( IsLoadAadCredKeyFromProfileEnabled() )
              {
                v12 = _CleanupAllDeferredUserCacheInfo();
                if ( v12 < 0 )
                  wil::details::in1diag3::_Log_Hr(
                    retaddr,
                    (void *)0x2F9,
                    (unsigned int)"onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp",
                    (const char *)(unsigned int)v12,
                    v15);
              }
              if ( (int)KerbCommInitialize() >= 0 )
              {
                byte_18009AC00 = 1;
                v4 = 0;
              }
              else
              {
                v4 = -1073741502;
                v13 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
                LODWORD(v15) = 767;
                WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225794LL, v13, v15, "KerbCommInitialize", &Class);
              }
            }
          }
        }
      }
    }
  }
LABEL_24:
  if ( v17 )
    RtlReleaseResource(&g_PackageListLock);
  if ( (v4 & 0x80000000) != 0 )
    GlobalCleanup(0);
  return v4;
}

```

## disassembly

```asm
0x18004b1e0  mov     [rsp+arg_8], rbx
0x18004b1e5  push    rdi
0x18004b1e6  sub     rsp, 40h
0x18004b1ea  mov     rbx, rdx
0x18004b1ed  mov     [rsp+48h+arg_0], 0
0x18004b1f5  mov     cs:?g_ulpCloudAPPackageId@@3_KA, rcx; unsigned __int64 g_ulpCloudAPPackageId
0x18004b1fc  mov     cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA, r8; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x18004b203  mov     rax, [r8+58h]
0x18004b207  mov     cs:?g_CloudAPFunctionTable@@3U_CLOUDAP_SECPKG_FUNCTION_TABLE@@A, rax; _CLOUDAP_SECPKG_FUNCTION_TABLE g_CloudAPFunctionTable
0x18004b20e  mov     rax, [r8+160h]
0x18004b215  mov     cs:qword_18009AFB8, rax
0x18004b21c  mov     rax, [r8+168h]
0x18004b223  mov     cs:qword_18009AFC0, rax
0x18004b22a  mov     rax, [r8+170h]
0x18004b231  mov     cs:qword_18009AFC8, rax
0x18004b238  mov     rax, [r8+28h]
0x18004b23c  mov     cs:qword_18009AFD0, rax
0x18004b243  mov     rax, [r8+30h]
0x18004b247  mov     cs:qword_18009AFD8, rax
0x18004b24e  lea     rax, ?AllocateUserInfo@@YAJKPEAXKPEAPEAXPEBG2222PEAU_APPLUGIN_SSO_USER_INFO@@PEAU_APPLUGIN_PWD_EXPIRY_INFO@@PEAU_APPLUGIN_PUBLIC_CACHED_INFO@@KPEAPEAU_APPLUGIN_USER_INFO@@@Z; AllocateUserInfo(ulong,void *,ulong,void * *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,_APPLUGIN_SSO_USER_INFO *,_APPLUGIN_PWD_EXPIRY_INFO *,_APPLUGIN_PUBLIC_CACHED_INFO *,ulong,_APPLUGIN_USER_INFO * *)
0x18004b255  mov     cs:qword_18009AFE0, rax
0x18004b25c  lea     rax, ?FreeUserInfo@@YAXPEAU_APPLUGIN_USER_INFO@@@Z; FreeUserInfo(_APPLUGIN_USER_INFO *)
0x18004b263  mov     cs:qword_18009AFE8, rax
0x18004b26a  mov     rax, [r8+148h]
0x18004b271  mov     cs:qword_18009AFF0, rax
0x18004b278  mov     rax, [r8+198h]
0x18004b27f  mov     cs:qword_18009B000, rax
0x18004b286  mov     rax, [r8+158h]
0x18004b28d  mov     cs:qword_18009AFF8, rax
0x18004b294  lea     rax, ?SignMessageWithNgc@@YAJPEAEGPEAUHWND__@@0KPEAPEAEPEAK@Z; SignMessageWithNgc(uchar *,ushort,HWND__ *,uchar *,ulong,uchar * *,ulong *)
0x18004b29b  mov     cs:qword_18009B008, rax
0x18004b2a2  mov     rax, [r8+0C0h]
0x18004b2a9  mov     cs:qword_18009B010, rax
0x18004b2b0  mov     dword ptr cs:?g_TimeForever@@3T_LARGE_INTEGER@@A+4, 7FFFFF36h; _LARGE_INTEGER g_TimeForever
0x18004b2ba  mov     dword ptr cs:?g_TimeForever@@3T_LARGE_INTEGER@@A, 0D5969FFFh; _LARGE_INTEGER g_TimeForever
0x18004b2c4  mov     cs:?g_TimeNever@@3T_LARGE_INTEGER@@A, 0; _LARGE_INTEGER g_TimeNever
0x18004b2cf  lea     rcx, ?g_LogonSessionListLock@@3U_RTL_RESOURCE@@A; Resource
0x18004b2d6  call    cs:__imp_RtlInitializeResource
0x18004b2dc  nop
0x18004b2dd  mov     edi, 1
0x18004b2e2  mov     cs:?g_bLogonSessionListLockInitialized@@3HA, edi; int g_bLogonSessionListLockInitialized
0x18004b2e8  lea     rax, ?g_LogonSessionList@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_LogonSessionList
0x18004b2ef  mov     cs:qword_18009ACE8, rax
0x18004b2f6  mov     cs:?g_LogonSessionList@@3U_LIST_ENTRY@@A, rax; _LIST_ENTRY g_LogonSessionList
0x18004b2fd  lea     rcx, ?g_UserCacheListLock@@3U_RTL_RESOURCE@@A; Resource
0x18004b304  call    cs:__imp_RtlInitializeResource
0x18004b30a  nop
0x18004b30b  mov     cs:?g_bUserCacheListLockInitialized@@3HA, edi; int g_bUserCacheListLockInitialized
0x18004b311  lea     rax, ?g_UserCacheList@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_UserCacheList
0x18004b318  mov     cs:qword_18009ACD8, rax
0x18004b31f  mov     cs:?g_UserCacheList@@3U_LIST_ENTRY@@A, rax; _LIST_ENTRY g_UserCacheList
0x18004b326  lea     rcx, ?g_StaleUserCacheListLock@@3U_RTL_RESOURCE@@A; Resource
0x18004b32d  call    cs:__imp_RtlInitializeResource
0x18004b333  nop
0x18004b334  mov     cs:?g_bStaleUserCacheListLockInitialized@@3HA, edi; int g_bStaleUserCacheListLockInitialized
0x18004b33a  lea     rax, ?g_StaleUserCacheList@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_StaleUserCacheList
0x18004b341  mov     cs:qword_18009ACC8, rax
0x18004b348  mov     cs:?g_StaleUserCacheList@@3U_LIST_ENTRY@@A, rax; _LIST_ENTRY g_StaleUserCacheList
0x18004b34f  lea     rcx, ?g_UserLockList_Lock@@3U_RTL_RESOURCE@@A; Resource
0x18004b356  call    cs:__imp_RtlInitializeResource
0x18004b35c  nop
0x18004b35d  mov     cs:?g_bUserLockList_LockInitialized@@3HA, edi; int g_bUserLockList_LockInitialized
0x18004b363  lea     rax, ?g_UserLockList@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_UserLockList
0x18004b36a  mov     cs:qword_18009ACB8, rax
0x18004b371  mov     cs:?g_UserLockList@@3U_LIST_ENTRY@@A, rax; _LIST_ENTRY g_UserLockList
0x18004b378  lea     rcx, ?g_PackageListLock@@3U_RTL_RESOURCE@@A; Resource
0x18004b37f  call    cs:__imp_RtlInitializeResource
0x18004b385  nop
0x18004b386  mov     cs:?g_bPackageListLockInitialized@@3HA, edi; int g_bPackageListLockInitialized
0x18004b38c  lea     rcx, ?g_LookupsCacheLock@@3U_RTL_RESOURCE@@A; Resource
0x18004b393  call    cs:__imp_RtlInitializeResource
0x18004b399  nop
0x18004b39a  mov     cs:?g_bLookupsCacheLockInitialized@@3HA, edi; int g_bLookupsCacheLockInitialized
0x18004b3a0  lea     rcx, ?g_AadConnectMapLock@@3U_RTL_RESOURCE@@A; Resource
0x18004b3a7  call    cs:__imp_RtlInitializeResource
0x18004b3ad  nop
0x18004b3ae  mov     cs:?g_bAadConnectMapLockInitialized@@3HA, edi; int g_bAadConnectMapLockInitialized
0x18004b3b4  lea     rax, ?g_MappedAccountCacheList@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_MappedAccountCacheList
0x18004b3bb  mov     cs:qword_18009AEE8, rax
0x18004b3c2  mov     cs:?g_MappedAccountCacheList@@3U_LIST_ENTRY@@A, rax; _LIST_ENTRY g_MappedAccountCacheList
0x18004b3c9  lea     rax, ?g_MappedUserNameHashList@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_MappedUserNameHashList
0x18004b3d0  mov     cs:qword_18009AED8, rax
0x18004b3d7  mov     cs:?g_MappedUserNameHashList@@3U_LIST_ENTRY@@A, rax; _LIST_ENTRY g_MappedUserNameHashList
0x18004b3de  test    byte ptr [rbx+4], 20h
0x18004b3e2  jz      short loc_18004B450
0x18004b3e4  call    ?InitializeCredentialIsolation@@YAJXZ; InitializeCredentialIsolation(void)
0x18004b3e9  mov     ebx, eax
0x18004b3eb  test    eax, eax
0x18004b3ed  jz      short loc_18004B434
0x18004b3ef  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x18004b3f6  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18004b3fb  mov     r9, rax
0x18004b3fe  lea     rax, Class
0x18004b405  mov     [rsp+48h+var_18], rax
0x18004b40a  lea     rax, aInitializecred; "InitializeCredentialIsolation"
0x18004b411  mov     [rsp+48h+var_20], rax
0x18004b416  mov     dword ptr [rsp+48h+var_28], 2D3h
0x18004b41e  mov     r8d, ebx
0x18004b421  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18004b428  xor     ecx, ecx
0x18004b42a  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18004b42f  jmp     loc_18004B84C
0x18004b434  lea     rax, ?GenerateKeyBindingKeyPair@@YAJPEAPEAEPEAK01@Z; GenerateKeyBindingKeyPair(uchar * *,ulong *,uchar * *,ulong *)
0x18004b43b  mov     cs:qword_18009B018, rax
0x18004b442  lea     rax, ?VerifyKeyBindingKeyPair@@YAHPEAEK0K@Z; VerifyKeyBindingKeyPair(uchar *,ulong,uchar *,ulong)
0x18004b449  mov     cs:qword_18009B020, rax
0x18004b450  call    ?InitializePackageGlobals@@YAJXZ; InitializePackageGlobals(void)
0x18004b455  mov     ebx, eax
0x18004b457  test    eax, eax
0x18004b459  jz      short loc_18004B48C
0x18004b45b  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x18004b462  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18004b467  mov     r9, rax
0x18004b46a  lea     rax, Class
0x18004b471  mov     [rsp+48h+var_18], rax
0x18004b476  lea     rax, aInitializepack; "InitializePackageGlobals"
0x18004b47d  mov     [rsp+48h+var_20], rax
0x18004b482  mov     dword ptr [rsp+48h+var_28], 2DEh
0x18004b48a  jmp     short loc_18004B41E
0x18004b48c  call    ?InitializeComputerName@@YAJXZ; InitializeComputerName(void)
0x18004b491  mov     ebx, eax
0x18004b493  test    eax, eax
0x18004b495  jz      short loc_18004B4CB
0x18004b497  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x18004b49e  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18004b4a3  mov     r9, rax
0x18004b4a6  lea     rax, Class
0x18004b4ad  mov     [rsp+48h+var_18], rax
0x18004b4b2  lea     rax, aInitializecomp; "InitializeComputerName"
0x18004b4b9  mov     [rsp+48h+var_20], rax
0x18004b4be  mov     dword ptr [rsp+48h+var_28], 2E1h
0x18004b4c6  jmp     loc_18004B41E
0x18004b4cb  call    ?InitializeCrypto@@YAJXZ; InitializeCrypto(void)
0x18004b4d0  mov     ebx, eax
0x18004b4d2  test    eax, eax
0x18004b4d4  jz      short loc_18004B50A
0x18004b4d6  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x18004b4dd  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18004b4e2  mov     r9, rax
0x18004b4e5  lea     rax, Class
0x18004b4ec  mov     [rsp+48h+var_18], rax
0x18004b4f1  lea     rax, aInitializecryp; "InitializeCrypto"
0x18004b4f8  mov     [rsp+48h+var_20], rax
0x18004b4fd  mov     dword ptr [rsp+48h+var_28], 2E4h
0x18004b505  jmp     loc_18004B41E
0x18004b50a  call    ?InitializeMisc@@YAJXZ; InitializeMisc(void)
0x18004b50f  mov     ebx, eax
0x18004b511  test    eax, eax
0x18004b513  jz      short loc_18004B549
0x18004b515  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x18004b51c  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18004b521  mov     r9, rax
0x18004b524  lea     rax, Class
0x18004b52b  mov     [rsp+48h+var_18], rax
0x18004b530  lea     rax, aInitializemisc; "InitializeMisc"
0x18004b537  mov     [rsp+48h+var_20], rax
0x18004b53c  mov     dword ptr [rsp+48h+var_28], 2E7h
0x18004b544  jmp     loc_18004B41E
0x18004b549  call    ?InitializeCloudAPCache@@YAJXZ; InitializeCloudAPCache(void)
0x18004b54e  mov     ebx, eax
0x18004b550  test    eax, eax
0x18004b552  jz      short loc_18004B588
0x18004b554  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x18004b55b  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18004b560  mov     r9, rax
0x18004b563  lea     rax, Class
0x18004b56a  mov     [rsp+48h+var_18], rax
0x18004b56f  lea     rax, aInitializeclou; "InitializeCloudAPCache"
0x18004b576  mov     [rsp+48h+var_20], rax
0x18004b57b  mov     dword ptr [rsp+48h+var_28], 2EAh
0x18004b583  jmp     loc_18004B41E
0x18004b588  mov     dl, dil; Wait
0x18004b58b  lea     rcx, ?g_PackageListLock@@3U_RTL_RESOURCE@@A; Resource
0x18004b592  call    cs:__imp_RtlAcquireResourceExclusive
0x18004b598  mov     [rsp+48h+arg_0], edi
0x18004b59c  call    ?InitializePlugins@@YAJXZ; InitializePlugins(void)
0x18004b5a1  mov     ebx, eax
0x18004b5a3  test    eax, eax
0x18004b5a5  jz      short loc_18004B5DB
0x18004b5a7  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x18004b5ae  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18004b5b3  mov     r9, rax
0x18004b5b6  lea     rax, Class
0x18004b5bd  mov     [rsp+48h+var_18], rax
0x18004b5c2  lea     rax, aInitializeplug; "InitializePlugins"
0x18004b5c9  mov     [rsp+48h+var_20], rax
0x18004b5ce  mov     dword ptr [rsp+48h+var_28], 2F3h
0x18004b5d6  jmp     loc_18004B41E
0x18004b5db  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SyncDpapiCredKeyToUserProfile@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SyncDpapiCredKeyToUserProfile@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SyncDpapiCredKeyToUserProfile> `wil::Feature<__WilFeatureTraits_Feature_SyncDpapiCredKeyToUserProfile>::GetImpl(void)'::`2'::impl
0x18004b5e2  call    ?__private_IsEnabledPreCheck@?$FeatureImpl@U__WilFeatureTraits_Feature_SyncDpapiCredKeyToUserProfile@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SyncDpapiCredKeyToUserProfile>::__private_IsEnabledPreCheck(wil::ReportingKind)
0x18004b5e7  call    ?IsLoadAadCredKeyFromProfileEnabled@@YA_NXZ; IsLoadAadCredKeyFromProfileEnabled(void)
0x18004b5ec  test    al, al
0x18004b5ee  jz      short loc_18004B612
0x18004b5f0  call    ?_CleanupAllDeferredUserCacheInfo@@YAJXZ; _CleanupAllDeferredUserCacheInfo(void)
0x18004b5f5  test    eax, eax
0x18004b5f7  jns     short loc_18004B612
0x18004b5f9  mov     rcx, [rsp+48h]; this
0x18004b5fe  mov     r9d, eax; char *
0x18004b601  lea     r8, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x18004b608  mov     edx, 2F9h; void *
0x18004b60d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004b612  call    KerbCommInitialize
0x18004b617  test    eax, eax
0x18004b619  jns     short loc_18004B654
0x18004b61b  mov     ebx, 0C0000142h
0x18004b620  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x18004b627  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18004b62c  mov     r9, rax
0x18004b62f  lea     rax, Class
0x18004b636  mov     [rsp+48h+var_18], rax
0x18004b63b  lea     rax, aKerbcomminitia; "KerbCommInitialize"
0x18004b642  mov     [rsp+48h+var_20], rax
0x18004b647  mov     dword ptr [rsp+48h+var_28], 2FFh
0x18004b64f  jmp     loc_18004B41E
0x18004b654  mov     cs:byte_18009AC00, dil
0x18004b65b  xor     ebx, ebx
0x18004b65d  jmp     loc_18004B84C
0x18004b662  mov     ebx, eax
0x18004b664  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x18004b66b  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18004b670  mov     r9, rax
0x18004b673  lea     rax, Class
0x18004b67a  mov     [rsp+48h+var_18], rax
0x18004b67f  lea     rax, aRtlinitializer; "RtlInitializeResource"
0x18004b686  mov     [rsp+48h+var_20], rax
0x18004b68b  mov     dword ptr [rsp+48h+var_28], 2C9h
0x18004b693  mov     r8d, ebx
0x18004b696  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18004b69d  xor     ecx, ecx
0x18004b69f  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18004b6a4  jmp     loc_18004B84C
0x18004b6a9  mov     ebx, eax
0x18004b6ab  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x18004b6b2  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18004b6b7  mov     r9, rax
0x18004b6ba  lea     rax, Class
0x18004b6c1  mov     [rsp+48h+var_18], rax
0x18004b6c6  lea     rax, aRtlinitializer; "RtlInitializeResource"
0x18004b6cd  mov     [rsp+48h+var_20], rax
0x18004b6d2  mov     dword ptr [rsp+48h+var_28], 2BEh
0x18004b6da  mov     r8d, ebx
0x18004b6dd  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18004b6e4  xor     ecx, ecx
0x18004b6e6  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18004b6eb  jmp     loc_18004B84C
0x18004b6f0  mov     ebx, eax
0x18004b6f2  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x18004b6f9  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18004b6fe  mov     r9, rax
0x18004b701  lea     rax, Class
0x18004b708  mov     [rsp+48h+var_18], rax
0x18004b70d  lea     rax, aRtlinitializer; "RtlInitializeResource"
0x18004b714  mov     [rsp+48h+var_20], rax
0x18004b719  mov     dword ptr [rsp+48h+var_28], 2B3h
0x18004b721  mov     r8d, ebx
0x18004b724  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18004b72b  xor     ecx, ecx
0x18004b72d  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18004b732  jmp     loc_18004B84C
0x18004b737  mov     ebx, eax
0x18004b739  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x18004b740  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18004b745  mov     r9, rax
0x18004b748  lea     rax, Class
0x18004b74f  mov     [rsp+48h+var_18], rax
0x18004b754  lea     rax, aRtlinitializer; "RtlInitializeResource"
0x18004b75b  mov     [rsp+48h+var_20], rax
0x18004b760  mov     dword ptr [rsp+48h+var_28], 2A7h
0x18004b768  mov     r8d, ebx
0x18004b76b  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18004b772  xor     ecx, ecx
0x18004b774  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18004b779  jmp     loc_18004B84C
0x18004b77e  mov     ebx, eax
0x18004b780  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x18004b787  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18004b78c  mov     r9, rax
0x18004b78f  lea     rax, Class
0x18004b796  mov     [rsp+48h+var_18], rax
0x18004b79b  lea     rax, aRtlinitializer; "RtlInitializeResource"
0x18004b7a2  mov     [rsp+48h+var_20], rax
0x18004b7a7  mov     dword ptr [rsp+48h+var_28], 29Bh
0x18004b7af  mov     r8d, ebx
0x18004b7b2  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18004b7b9  xor     ecx, ecx
0x18004b7bb  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18004b7c0  jmp     loc_18004B84C
0x18004b7c5  mov     ebx, eax
0x18004b7c7  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x18004b7ce  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18004b7d3  mov     r9, rax
0x18004b7d6  lea     rax, Class
0x18004b7dd  mov     [rsp+48h+var_18], rax
0x18004b7e2  lea     rax, aRtlinitializer; "RtlInitializeResource"
0x18004b7e9  mov     [rsp+48h+var_20], rax
0x18004b7ee  mov     dword ptr [rsp+48h+var_28], 28Fh
0x18004b7f6  mov     r8d, ebx
0x18004b7f9  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18004b800  xor     ecx, ecx
0x18004b802  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
  ... truncated ...
```
