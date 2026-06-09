# LsapInitLsa

- ea: `0x1800adbf0`
- end: `0x1800ae3cf`
- name: `LsapInitLsa`
- size: `2015`
- prototype: ``
- caller_count: `1`
- callee_count: `52`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800d20d8`

## callees

- `0x180011278`
- `0x180039f50`
- `0x180065594`
- `0x18007bc98`
- `0x180084c78`
- `0x18008b4c4`
- `0x18008d370`
- `0x18009cbc4`
- `0x18009d704`
- `0x1800a003c`
- `0x1800a0cd8`
- `0x1800ada18`
- `0x1800adbf0`
- `0x1800ae660`
- `0x1800ae700`
- `0x1800ae720`
- `0x1800aeac4`
- `0x1800b0f58`
- `0x1800b1034`
- `0x1800b1578`
- `0x1800b2658`
- `0x1800b3684`
- `0x1800b398c`
- `0x1800b3c68`
- `0x1800b43cc`
- `0x1800b4574`
- `0x1800b4780`
- `0x1800bb068`
- `0x1800bc040`
- `0x1800c4f1c`
- `0x1800c8b0c`
- `0x1800c8bc8`
- `0x1800cd3f4`
- `0x1800cd5f0`
- `0x1800db4c0`
- `0x1800dbe80`
- `0x1800de77c`
- `0x1800de82c`
- `0x1800de940`
- `0x1800ebe34`
- `0x1800ec05c`
- `0x1800ec388`
- `0x1800ececc`
- `0x1800f21e4`
- `0x1800f5600`
- `0x1800f8ad4`
- `0x1800f9a1c`
- `0x180101050`
- `0x180113c88`
- `0x180116180`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsAlloc` at `0x1800adc72`
- `api-ms-win-core-processthreads-l1-1-0!TlsAlloc` at `0x1800adc84`
- `api-ms-win-core-processthreads-l1-1-0!TlsAlloc` at `0x1800adc96`
- `api-ms-win-core-processthreads-l1-1-0!TlsAlloc` at `0x1800adca8`
- `api-ms-win-core-processthreads-l1-1-0!TlsAlloc` at `0x1800adc72`
- `api-ms-win-core-processthreads-l1-1-0!TlsAlloc` at `0x1800adc84`
- `api-ms-win-core-processthreads-l1-1-0!TlsAlloc` at `0x1800adc96`
- `api-ms-win-core-processthreads-l1-1-0!TlsAlloc` at `0x1800adca8`
- `api-ms-win-core-processthreads-l1-1-0!SetProcessShutdownParameters` at `0x1800adf6f`
- `api-ms-win-core-processthreads-l1-1-0!SetProcessShutdownParameters` at `0x1800adf6f`
- `api-ms-win-core-console-l1-1-0!SetConsoleCtrlHandler` at `0x1800adf84`
- `api-ms-win-core-console-l1-1-0!SetConsoleCtrlHandler` at `0x1800adf84`
- `ntdll!RtlInitializeSRWLock` at `0x1800ae094`
- `ntdll!RtlInitializeSRWLock` at `0x1800ae094`
- `ntdll!RtlInitializeGenericTableAvl` at `0x1800adc4c`
- `ntdll!RtlInitializeGenericTableAvl` at `0x1800adc4c`
- `ntdll!RtlNumberOfSetBitsUlongPtr` at `0x1800ae1a9`
- `ntdll!RtlNumberOfSetBitsUlongPtr` at `0x1800ae1a9`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x1800adce2`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x1800adce2`
- `ntdll!RtlInitializeCriticalSection` at `0x1800adc1b`
- `ntdll!RtlInitializeCriticalSection` at `0x1800adc66`
- `ntdll!RtlInitializeCriticalSection` at `0x1800ae20a`
- `ntdll!RtlInitializeCriticalSection` at `0x1800adc1b`
- `ntdll!RtlInitializeCriticalSection` at `0x1800adc66`
- `ntdll!RtlInitializeCriticalSection` at `0x1800ae20a`
- `bcrypt!BCryptSetAuditingInterface` at `0x1800adda6`
- `bcrypt!BCryptSetAuditingInterface` at `0x1800adda6`
- `ncrypt!NCryptSetAuditingInterface` at `0x1800addbb`
- `ncrypt!NCryptSetAuditingInterface` at `0x1800addbb`
- `CRYPTBASE!SystemFunction036` at `0x1800ae2fc`
- `CRYPTBASE!SystemFunction036` at `0x1800ae2fc`
- `ext-ms-win-netprovision-netprovfw-l1-1-0!NetpProvFreeLdapLsaDomainInfo` at `0x1800ae065`
- `ext-ms-win-netprovision-netprovfw-l1-1-0!NetpProvFreeLdapLsaDomainInfo` at `0x1800ae065`
- `ext-ms-win-netprovision-netprovfw-l1-1-0!NetpProvCheckOfflineLsaPolicyUpdate` at `0x1800ae03c`
- `ext-ms-win-netprovision-netprovfw-l1-1-0!NetpProvCheckOfflineLsaPolicyUpdate` at `0x1800ae03c`
- `ext-ms-win-security-lsaadt-l1-1-0!LsapAdtInitialize` at `0x1800adfc1`
- `ext-ms-win-security-lsaadt-l1-1-0!LsapAdtInitialize` at `0x1800adfc1`

## string_xrefs

- `0x1800adcf9`: `LsapCacheProcessToken failed`
- `0x1800ae020`: `LsapApplyCAPsUpdate failed`
- `0x1800ae0ba`: `LsapInitIdProvExtension failed`
- `0x1800ae166`: `LsapAccountCacheInitialize failed`
- `0x1800ae1bf`: `LsapInitializeLocalSystemAccess failed`
- `0x1800ae382`: `LsapDbInitSidCache failed`
- `0x1800ae247`: `LsapInitializeSidNameMappingCache failed`
- `0x1800ae295`: `LsapInitializePerUserIdentityCache failed`
- `0x1800ae368`: `ApiLogCreateForSpmMessages failed`

## pseudocode

```c
__int64 LsapInitLsa()
{
  int v0; // eax
  unsigned int v1; // ebx
  __int64 v2; // rcx
  const wchar_t *v3; // rdx
  int Parameters; // eax
  __int64 v5; // rcx
  int v6; // ebx
  __int64 v7; // rcx
  int v8; // eax
  __int64 v9; // rcx
  int v10; // eax
  int v11; // eax
  unsigned int inited; // eax
  unsigned __int16 **v13; // rdx
  const unsigned __int16 *v14; // r8
  const unsigned __int16 *v15; // r9
  int Packages; // eax
  LsaHandleCache *v17; // rcx
  __int64 v18; // rdx
  struct LsaAccountCache **v19; // rcx
  struct LSAAConfigTable **v20; // rcx
  int v21; // eax
  NTSTATUS v22; // eax
  int v23; // eax
  int v24; // eax
  int v25; // eax
  struct _CNG_AUDIT_FUNCTION_TABLE *v27; // [rsp+40h] [rbp+8h] BYREF
  __int64 v28; // [rsp+48h] [rbp+10h] BYREF

  v28 = 0;
  LoadDebugParameters();
  BreakOnError(1u);
  RtlInitializeCriticalSection(&stru_1801A1110);
  RtlInitializeGenericTableAvl(&Table, compareLists, allocateEvntlogMap, freeEvntlogMap, 0);
  byte_1801A11A0 = 1;
  RtlInitializeCriticalSection(&g_RegistrationHandleCS);
  dwSession = TlsAlloc();
  dwExceptionInfo = TlsAlloc();
  dwCallInfo = TlsAlloc();
  dwThreadPackage = TlsAlloc();
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_LsaHandleCache_Improvements>::__private_IsEnabled((wil::details *)`wil::Feature<__WilFeatureTraits_Feature_Servicing_LsaHandleCache_Improvements>::GetImpl'::`2'::impl);
  SafeAllocaInitialize();
  LsapGlobalBootState = LsapGetBootState();
  RtlGetDeviceFamilyInfoEnum(0, &LsapPlatformId, 0);
  v0 = LsapCacheProcessToken();
  v1 = v0;
  if ( v0 >= 0 )
  {
    if ( !(unsigned int)LsapPerfInitialize() )
    {
      if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_e5da1992a0263c0d539144257ad05029_Traceguids);
      v2 = 3221225701LL;
      v3 = L"LsapPerfInitialize failed";
      v1 = -1073741595;
      goto LABEL_102;
    }
    v27 = 0;
    if ( (int)GetCngAuditFunctions(&v27) >= 0 && (int)BCryptSetAuditingInterface(v27) >= 0 )
      NCryptSetAuditingInterface(v27);
    SpmpThreadStartupEx();
    if ( !(unsigned int)InitSessionManager() )
    {
      if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_e5da1992a0263c0d539144257ad05029_Traceguids);
      v2 = 3221225701LL;
      v3 = L"InitSessionManager failed";
      v1 = -1073741595;
      goto LABEL_102;
    }
    qword_18019E448 = (__int64)pDefaultSession;
    qword_18019E450 = 0;
    qword_18019E470 = 999;
    dword_18019E480 = 1;
    dword_18019E48C = 18;
    if ( !(unsigned int)LsapInitializeScavenger() )
    {
      if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_e5da1992a0263c0d539144257ad05029_Traceguids);
      v2 = 3221225701LL;
      v3 = L"LsapInitializeScavenger failed";
      v1 = -1073741595;
      goto LABEL_102;
    }
    Parameters = LoadParameters(3);
    v1 = Parameters;
    if ( Parameters < 0 )
    {
      v3 = L"LoadParameters failed";
LABEL_101:
      v2 = (unsigned int)Parameters;
      goto LABEL_102;
    }
    Parameters = LsapInitializeShadowAdmin();
    v1 = Parameters;
    if ( Parameters < 0 )
    {
      v3 = L"LsapInitializeShadowAdmin failed";
      goto LABEL_101;
    }
    if ( (unsigned int)LsapIsCredentialIsolationLicensed() )
    {
      Parameters = LsapWaitForTrustletStartup();
      v1 = Parameters;
      if ( Parameters < 0 )
      {
        v3 = L"LsapWaitForTrustletStartup failed";
        goto LABEL_101;
      }
    }
    LsapGlobalMachineIsSecureByDefault = 0;
    LODWORD(v27) = 0;
    LsapCredGuardOnByDefaultChecks(v5, &v27);
    if ( (unsigned int)LsapCheckSecureMode() )
    {
      LsapGlobalMachineIsSecureByDefault = 1;
      v6 = 1;
    }
    else
    {
      v6 = (int)v27;
    }
    if ( (unsigned int)LsapIsCredentialIsolationLicensed() )
    {
      v8 = LsapSetLsaIsoState(v7, v6);
      if ( v8 < 0 )
        LsapSetErrorInfo((unsigned int)v8, L"LsapSetLsaIsoState failed");
    }
    Parameters = LsapDbInitializeWellKnownSids(&WellKnownSids);
    v1 = Parameters;
    if ( Parameters < 0 )
    {
      v3 = L"LsapDbInitializeWellKnownValues failed";
      goto LABEL_101;
    }
    LsapTcbPrivilege = (struct _LUID)7LL;
    SetupPhase = SpmpIsSetupPass();
    SetProcessShutdownParameters(0xD0u, 1u);
    SetConsoleCtrlHandler(SpConsoleHandler, 1);
    v1 = LsapInitializeMandatoryLabels();
    if ( (v1 & 0x80000000) != 0 )
      return v1;
    Parameters = LsapDbInitializeServer(1u);
    v1 = Parameters;
    if ( Parameters < 0 )
    {
      v3 = L"LsapDbInitializeServer(1) failed";
      goto LABEL_101;
    }
    if ( (unsigned __int8)IsLsapAdtInitializeCrashOnAuditFailPresent(v9) )
    {
      Parameters = LsapAdtInitialize();
      v1 = Parameters;
      if ( Parameters < 0 )
      {
        v3 = L"LsapAdtInitialize failed";
        goto LABEL_101;
      }
    }
    AdtpLocalSystemSid = *((_QWORD *)WellKnownSids + 90);
    AdtpNullSid = 257;
    v10 = LsapInitializeCAPs();
    if ( v10 < 0 )
      LsapSetErrorInfo((unsigned int)v10, L"LsapInitializeCAPs failed");
    v11 = LsapApplyCAPsUpdate(1u);
    if ( v11 < 0 )
      LsapSetErrorInfo((unsigned int)v11, L"LsapApplyCAPsUpdate failed");
    if ( (unsigned __int8)IsNetpProvCheckOfflineLsaPolicyUpdatePresent()
      && !(unsigned int)NetpProvCheckOfflineLsaPolicyUpdate(&v28) )
    {
      LsarSetInformationPolicy(LsapPolicyHandle);
      NetpProvFreeLdapLsaDomainInfo(&v28);
    }
    if ( !LsapLogonSessionInitialize() )
    {
      v2 = 3221225701LL;
      v3 = L"LsapLogonSessionInitialize failed";
      v1 = -1073741595;
LABEL_102:
      LsapSetErrorInfo(v2, v3);
      return v1;
    }
    RtlInitializeSRWLock(&ProviderLock);
    inited = LsapInitIdProvExtension();
    v1 = inited;
    if ( (int)(inited + 0x80000000) >= 0 && inited != -1073741637 )
    {
      v3 = L"LsapInitIdProvExtension failed";
LABEL_55:
      v2 = v1;
      goto LABEL_102;
    }
    Packages = LoadPackages((unsigned __int16 **const)0x80000000LL, v13, v14, v15);
    v1 = Packages;
    if ( Packages < 0 )
    {
      LsapSetErrorInfo((unsigned int)Packages, L"LoadPackages failed");
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        return v1;
      v18 = 14;
      goto LABEL_60;
    }
    Parameters = CredpInitialize();
    v1 = Parameters;
    if ( Parameters < 0 )
    {
      v3 = L"CredpInitialize failed";
      goto LABEL_101;
    }
    if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_LocalSystemAccessRights>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_Servicing_LocalSystemAccessRights>::GetImpl'::`2'::impl) )
    {
      if ( gpLsaAccountCache )
      {
        v1 = -1073741595;
LABEL_67:
        v3 = L"LsapAccountCacheInitialize failed";
        goto LABEL_55;
      }
      v1 = LsaAccountCache::StaticCreate(v19);
      if ( (v1 & 0x80000000) != 0 )
        goto LABEL_67;
      v21 = LSAAConfigTable::StaticCreate(v20);
      v1 = v21;
      if ( v21 < 0 )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 12),
            55,
            &WPP_4f6ab1b6c995309645dc077809c6c64b_Traceguids,
            (unsigned int)v21);
        goto LABEL_73;
      }
      if ( (unsigned int)RtlNumberOfSetBitsUlongPtr(4087) != 11 )
      {
        v1 = -1073741595;
LABEL_73:
        v3 = L"LsapInitializeLocalSystemAccess failed";
        goto LABEL_55;
      }
    }
    InitSystemLogon();
    Parameters = LsapRPCInit();
    v1 = Parameters;
    if ( Parameters < 0 )
    {
      v3 = L"LsapRPCInit failed";
      goto LABEL_101;
    }
    if ( !LsapAuInit() )
    {
      v2 = 3221225701LL;
      v3 = L"LsapAuInit failed";
      v1 = -1073741595;
      goto LABEL_102;
    }
    v22 = RtlInitializeCriticalSection(&LsapSidCacheLock);
    v1 = v22;
    if ( v22 < 0 )
    {
      LsapSetErrorInfo((unsigned int)v22, L"LsapDbInitSidCache failed");
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        return v1;
      v18 = 15;
    }
    else
    {
      LsapSidCacheReadParameters(0);
      LsapUpdateConfigSettings();
      LsaLookupPerfCounterAddAmount(0xFu, LsapSidCacheMaxSize);
      v23 = LsapInitializeSidNameMappingCache();
      v1 = v23;
      if ( v23 < 0 )
      {
        LsapSetErrorInfo((unsigned int)v23, L"LsapInitializeSidNameMappingCache failed");
        v17 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        {
          return v1;
        }
        v18 = 16;
        goto LABEL_60;
      }
      BreakOnError(2u);
      v24 = LsapInitializePerUserIdentityCache();
      v1 = v24;
      if ( v24 < 0 )
      {
        LsapSetErrorInfo((unsigned int)v24, L"LsapInitializePerUserIdentityCache failed");
        v17 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        {
          return v1;
        }
        v18 = 17;
        goto LABEL_60;
      }
      BreakOnError(2u);
      LsapInitializeIsolatedNameCache();
      BreakOnError(2u);
      if ( (unsigned int)IsUacBypassAllowed() )
      {
        if ( !SystemFunction036(&LsapGlobalPerBootMachineID, 0x20u) )
          return (unsigned int)-1073741823;
        goto LABEL_94;
      }
      v25 = LsapPopulateMachineId();
      v1 = v25;
      if ( v25 >= 0 )
      {
LABEL_94:
        LpcApiLog = ApiLogCreate();
        if ( LpcApiLog )
        {
          v1 = 0;
          LsapInitMachineNamesRegCache();
          LsapInitRNGAuxiliarySeed();
          return v1;
        }
        v1 = -1073741801;
        v3 = L"ApiLogCreateForSpmMessages failed";
        goto LABEL_55;
      }
      LsapSetErrorInfo((unsigned int)v25, L"LsapPopulateMachineId failed");
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        return v1;
      v18 = 18;
    }
LABEL_60:
    WPP_SF_d(*((_QWORD *)v17 + 2), v18, WPP_e5da1992a0263c0d539144257ad05029_Traceguids, v1);
    return v1;
  }
  LsapSetErrorInfo((unsigned int)v0, L"LsapCacheProcessToken failed");
  if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_e5da1992a0263c0d539144257ad05029_Traceguids);
  return v1;
}

```

## disassembly

```asm
0x1800adbf0  mov     [rsp+arg_10], rbx
0x1800adbf5  push    rsi
0x1800adbf6  sub     rsp, 30h
0x1800adbfa  mov     [rsp+38h+arg_8], 0
0x1800adc03  call    ?LoadDebugParameters@@YAXXZ; LoadDebugParameters(void)
0x1800adc08  mov     esi, 1
0x1800adc0d  mov     ecx, esi; unsigned int
0x1800adc0f  call    ?BreakOnError@@YAXI@Z; BreakOnError(uint)
0x1800adc14  lea     rcx, stru_1801A1110; CriticalSection
0x1800adc1b  call    cs:__imp_RtlInitializeCriticalSection
0x1800adc22  nop     dword ptr [rax+rax+00h]
0x1800adc27  lea     r9, freeEvntlogMap; FreeRoutine
0x1800adc2e  mov     [rsp+38h+TableContext], 0; TableContext
0x1800adc37  lea     r8, allocateEvntlogMap; AllocateRoutine
0x1800adc3e  lea     rdx, compareLists; CompareRoutine
0x1800adc45  lea     rcx, Table; Table
0x1800adc4c  call    cs:__imp_RtlInitializeGenericTableAvl
0x1800adc53  nop     dword ptr [rax+rax+00h]
0x1800adc58  lea     rcx, ?g_RegistrationHandleCS@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x1800adc5f  mov     cs:byte_1801A11A0, sil
0x1800adc66  call    cs:__imp_RtlInitializeCriticalSection
0x1800adc6d  nop     dword ptr [rax+rax+00h]
0x1800adc72  call    cs:__imp_TlsAlloc
0x1800adc79  nop     dword ptr [rax+rax+00h]
0x1800adc7e  mov     cs:?dwSession@@3KA, eax; ulong dwSession
0x1800adc84  call    cs:__imp_TlsAlloc
0x1800adc8b  nop     dword ptr [rax+rax+00h]
0x1800adc90  mov     cs:?dwExceptionInfo@@3KA, eax; ulong dwExceptionInfo
0x1800adc96  call    cs:__imp_TlsAlloc
0x1800adc9d  nop     dword ptr [rax+rax+00h]
0x1800adca2  mov     cs:?dwCallInfo@@3KA, eax; ulong dwCallInfo
0x1800adca8  call    cs:__imp_TlsAlloc
0x1800adcaf  nop     dword ptr [rax+rax+00h]
0x1800adcb4  mov     cs:?dwThreadPackage@@3KA, eax; ulong dwThreadPackage
0x1800adcba  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_LsaHandleCache_Improvements@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_LsaHandleCache_Improvements@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_LsaHandleCache_Improvements> `wil::Feature<__WilFeatureTraits_Feature_Servicing_LsaHandleCache_Improvements>::GetImpl(void)'::`2'::impl
0x1800adcc1  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_LsaHandleCache_Improvements@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_LsaHandleCache_Improvements>::__private_IsEnabled(void)
0x1800adcc6  call    SafeAllocaInitialize
0x1800adccb  call    ?LsapGetBootState@@YA?AW4_LSAP_BOOT_STATE@@XZ; LsapGetBootState(void)
0x1800adcd0  xor     r8d, r8d
0x1800adcd3  mov     cs:?LsapGlobalBootState@@3KA, eax; ulong LsapGlobalBootState
0x1800adcd9  lea     rdx, ?LsapPlatformId@@3KA; ulong LsapPlatformId
0x1800adce0  xor     ecx, ecx
0x1800adce2  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x1800adce9  nop     dword ptr [rax+rax+00h]
0x1800adcee  call    ?LsapCacheProcessToken@@YAJXZ; LsapCacheProcessToken(void)
0x1800adcf3  mov     ebx, eax
0x1800adcf5  test    eax, eax
0x1800adcf7  jns     short loc_1800ADD40
0x1800adcf9  lea     rdx, aLsapcacheproce; "LsapCacheProcessToken failed"
0x1800add00  mov     ecx, eax
0x1800add02  call    LsapSetErrorInfo
0x1800add07  mov     rcx, cs:WPP_GLOBAL_Control
0x1800add0e  lea     rax, WPP_GLOBAL_Control
0x1800add15  cmp     rcx, rax
0x1800add18  jz      loc_1800AE3C1
0x1800add1e  test    [rcx+1Ch], sil
0x1800add22  jz      loc_1800AE3C1
0x1800add28  mov     rcx, [rcx+10h]
0x1800add2c  lea     edx, [rsi+9]
0x1800add2f  lea     r8, WPP_e5da1992a0263c0d539144257ad05029_Traceguids
0x1800add36  call    WPP_SF_
0x1800add3b  jmp     loc_1800AE3C1
0x1800add40  call    ?LsapPerfInitialize@@YAHXZ; LsapPerfInitialize(void)
0x1800add45  test    eax, eax
0x1800add47  jnz     short loc_1800ADD8A
0x1800add49  mov     rcx, cs:WPP_GLOBAL_Control
0x1800add50  lea     rax, WPP_GLOBAL_Control
0x1800add57  cmp     rcx, rax
0x1800add5a  jz      short loc_1800ADD77
0x1800add5c  test    [rcx+1Ch], sil
0x1800add60  jz      short loc_1800ADD77
0x1800add62  mov     rcx, [rcx+10h]
0x1800add66  lea     r8, WPP_e5da1992a0263c0d539144257ad05029_Traceguids
0x1800add6d  mov     edx, 0Bh
0x1800add72  call    WPP_SF_
0x1800add77  mov     ecx, 0C00000E5h
0x1800add7c  lea     rdx, aLsapperfinitia; "LsapPerfInitialize failed"
0x1800add83  mov     ebx, ecx
0x1800add85  jmp     loc_1800AE3BC
0x1800add8a  lea     rcx, [rsp+38h+arg_0]; struct _CNG_AUDIT_FUNCTION_TABLE **
0x1800add8f  mov     [rsp+38h+arg_0], 0
0x1800add98  call    ?GetCngAuditFunctions@@YAJPEAPEAU_CNG_AUDIT_FUNCTION_TABLE@@@Z; GetCngAuditFunctions(_CNG_AUDIT_FUNCTION_TABLE * *)
0x1800add9d  test    eax, eax
0x1800add9f  js      short loc_1800ADDC7
0x1800adda1  mov     rcx, [rsp+38h+arg_0]
0x1800adda6  call    cs:__imp_BCryptSetAuditingInterface
0x1800addad  nop     dword ptr [rax+rax+00h]
0x1800addb2  test    eax, eax
0x1800addb4  js      short loc_1800ADDC7
0x1800addb6  mov     rcx, [rsp+38h+arg_0]
0x1800addbb  call    cs:__imp_NCryptSetAuditingInterface
0x1800addc2  nop     dword ptr [rax+rax+00h]
0x1800addc7  call    ?SpmpThreadStartupEx@@YAXXZ; SpmpThreadStartupEx(void)
0x1800addcc  call    ?InitSessionManager@@YAHXZ; InitSessionManager(void)
0x1800addd1  test    eax, eax
0x1800addd3  jnz     short loc_1800ADE16
0x1800addd5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800adddc  lea     rax, WPP_GLOBAL_Control
0x1800adde3  cmp     rcx, rax
0x1800adde6  jz      short loc_1800ADE03
0x1800adde8  test    [rcx+1Ch], sil
0x1800addec  jz      short loc_1800ADE03
0x1800addee  mov     rcx, [rcx+10h]
0x1800addf2  lea     r8, WPP_e5da1992a0263c0d539144257ad05029_Traceguids
0x1800addf9  mov     edx, 0Ch
0x1800addfe  call    WPP_SF_
0x1800ade03  mov     ecx, 0C00000E5h
0x1800ade08  lea     rdx, aInitsessionman; "InitSessionManager failed"
0x1800ade0f  mov     ebx, ecx
0x1800ade11  jmp     loc_1800AE3BC
0x1800ade16  mov     rax, cs:?pDefaultSession@@3PEAU_Session@@EA; _Session * pDefaultSession
0x1800ade1d  mov     cs:qword_18019E448, rax
0x1800ade24  mov     cs:qword_18019E450, 0
0x1800ade2f  mov     cs:qword_18019E470, 3E7h
0x1800ade3a  mov     cs:dword_18019E480, esi
0x1800ade40  mov     cs:dword_18019E48C, 12h
0x1800ade4a  call    ?LsapInitializeScavenger@@YAHXZ; LsapInitializeScavenger(void)
0x1800ade4f  test    eax, eax
0x1800ade51  jnz     short loc_1800ADE94
0x1800ade53  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ade5a  lea     rax, WPP_GLOBAL_Control
0x1800ade61  cmp     rcx, rax
0x1800ade64  jz      short loc_1800ADE81
0x1800ade66  test    [rcx+1Ch], sil
0x1800ade6a  jz      short loc_1800ADE81
0x1800ade6c  mov     rcx, [rcx+10h]
0x1800ade70  lea     r8, WPP_e5da1992a0263c0d539144257ad05029_Traceguids
0x1800ade77  mov     edx, 0Dh
0x1800ade7c  call    WPP_SF_
0x1800ade81  mov     ecx, 0C00000E5h
0x1800ade86  lea     rdx, aLsapinitialize_8; "LsapInitializeScavenger failed"
0x1800ade8d  mov     ebx, ecx
0x1800ade8f  jmp     loc_1800AE3BC
0x1800ade94  mov     ecx, 3; unsigned int
0x1800ade99  call    ?LoadParameters@@YAJK@Z; LoadParameters(ulong)
0x1800ade9e  mov     ebx, eax
0x1800adea0  test    eax, eax
0x1800adea2  jns     short loc_1800ADEB0
0x1800adea4  lea     rdx, aLoadparameters; "LoadParameters failed"
0x1800adeab  jmp     loc_1800AE3BA
0x1800adeb0  call    ?LsapInitializeShadowAdmin@@YAJXZ; LsapInitializeShadowAdmin(void)
0x1800adeb5  mov     ebx, eax
0x1800adeb7  test    eax, eax
0x1800adeb9  jns     short loc_1800ADEC7
0x1800adebb  lea     rdx, aLsapinitialize_7; "LsapInitializeShadowAdmin failed"
0x1800adec2  jmp     loc_1800AE3BA
0x1800adec7  call    LsapIsCredentialIsolationLicensed
0x1800adecc  test    eax, eax
0x1800adece  jz      short loc_1800ADEE7
0x1800aded0  call    LsapWaitForTrustletStartup
0x1800aded5  mov     ebx, eax
0x1800aded7  test    eax, eax
0x1800aded9  jns     short loc_1800ADEE7
0x1800adedb  lea     rdx, aLsapwaitfortru; "LsapWaitForTrustletStartup failed"
0x1800adee2  jmp     loc_1800AE3BA
0x1800adee7  lea     rdx, [rsp+38h+arg_0]
0x1800adeec  mov     cs:?LsapGlobalMachineIsSecureByDefault@@3HA, 0; int LsapGlobalMachineIsSecureByDefault
0x1800adef6  mov     dword ptr [rsp+38h+arg_0], 0
0x1800adefe  call    LsapCredGuardOnByDefaultChecks
0x1800adf03  call    ?LsapCheckSecureMode@@YAHXZ; LsapCheckSecureMode(void)
0x1800adf08  test    eax, eax
0x1800adf0a  jz      short loc_1800ADF16
0x1800adf0c  mov     cs:?LsapGlobalMachineIsSecureByDefault@@3HA, esi; int LsapGlobalMachineIsSecureByDefault
0x1800adf12  mov     ebx, esi
0x1800adf14  jmp     short loc_1800ADF1A
0x1800adf16  mov     ebx, dword ptr [rsp+38h+arg_0]
0x1800adf1a  call    LsapIsCredentialIsolationLicensed
0x1800adf1f  test    eax, eax
0x1800adf21  jz      short loc_1800ADF3C
0x1800adf23  mov     edx, ebx
0x1800adf25  call    LsapSetLsaIsoState
0x1800adf2a  test    eax, eax
0x1800adf2c  jns     short loc_1800ADF3C
0x1800adf2e  lea     rdx, aLsapsetlsaisos; "LsapSetLsaIsoState failed"
0x1800adf35  mov     ecx, eax
0x1800adf37  call    LsapSetErrorInfo
0x1800adf3c  lea     rcx, ?WellKnownSids@@3PEAU_LSAP_WELL_KNOWN_SID_ENTRY@@EA; struct _LSAP_WELL_KNOWN_SID_ENTRY **
0x1800adf43  call    ?LsapDbInitializeWellKnownSids@@YAJPEAPEAU_LSAP_WELL_KNOWN_SID_ENTRY@@@Z; LsapDbInitializeWellKnownSids(_LSAP_WELL_KNOWN_SID_ENTRY * *)
0x1800adf48  mov     ebx, eax
0x1800adf4a  test    eax, eax
0x1800adf4c  js      loc_1800AE3B3
0x1800adf52  mov     cs:?LsapTcbPrivilege@@3U_LUID@@A, 7; _LUID LsapTcbPrivilege
0x1800adf5d  call    ?SpmpIsSetupPass@@YAEXZ; SpmpIsSetupPass(void)
0x1800adf62  mov     edx, esi; dwFlags
0x1800adf64  mov     cs:?SetupPhase@@3EA, al; uchar SetupPhase
0x1800adf6a  mov     ecx, 0D0h; dwLevel
0x1800adf6f  call    cs:__imp_SetProcessShutdownParameters
0x1800adf76  nop     dword ptr [rax+rax+00h]
0x1800adf7b  mov     edx, esi; Add
0x1800adf7d  lea     rcx, ?SpConsoleHandler@@YAHK@Z; HandlerRoutine
0x1800adf84  call    cs:__imp_SetConsoleCtrlHandler
0x1800adf8b  nop     dword ptr [rax+rax+00h]
0x1800adf90  call    ?LsapInitializeMandatoryLabels@@YAJXZ; LsapInitializeMandatoryLabels(void)
0x1800adf95  mov     ebx, eax
0x1800adf97  test    eax, eax
0x1800adf99  js      loc_1800AE3C1
0x1800adf9f  mov     ecx, esi; unsigned int
0x1800adfa1  call    ?LsapDbInitializeServer@@YAJK@Z; LsapDbInitializeServer(ulong)
0x1800adfa6  mov     ebx, eax
0x1800adfa8  test    eax, eax
0x1800adfaa  jns     short loc_1800ADFB8
0x1800adfac  lea     rdx, aLsapdbinitiali_0; "LsapDbInitializeServer(1) failed"
0x1800adfb3  jmp     loc_1800AE3BA
0x1800adfb8  call    IsLsapAdtInitializeCrashOnAuditFailPresent
0x1800adfbd  test    al, al
0x1800adfbf  jz      short loc_1800ADFDF
0x1800adfc1  call    cs:__imp_LsapAdtInitialize
0x1800adfc8  nop     dword ptr [rax+rax+00h]
0x1800adfcd  mov     ebx, eax
0x1800adfcf  test    eax, eax
0x1800adfd1  jns     short loc_1800ADFDF
0x1800adfd3  lea     rdx, aLsapadtinitial_2; "LsapAdtInitialize failed"
0x1800adfda  jmp     loc_1800AE3BA
0x1800adfdf  mov     rax, cs:?WellKnownSids@@3PEAU_LSAP_WELL_KNOWN_SID_ENTRY@@EA; _LSAP_WELL_KNOWN_SID_ENTRY * WellKnownSids
0x1800adfe6  mov     rcx, [rax+2D0h]
0x1800adfed  mov     cs:AdtpLocalSystemSid, rcx
0x1800adff4  mov     cs:AdtpNullSid, 101h
0x1800adffd  call    ?LsapInitializeCAPs@@YAJXZ; LsapInitializeCAPs(void)
0x1800ae002  test    eax, eax
0x1800ae004  jns     short loc_1800AE014
0x1800ae006  lea     rdx, aLsapinitialize_6; "LsapInitializeCAPs failed"
0x1800ae00d  mov     ecx, eax
0x1800ae00f  call    LsapSetErrorInfo
0x1800ae014  mov     cl, sil; unsigned __int8
0x1800ae017  call    ?LsapApplyCAPsUpdate@@YAJE@Z; LsapApplyCAPsUpdate(uchar)
0x1800ae01c  test    eax, eax
0x1800ae01e  jns     short loc_1800AE02E
0x1800ae020  lea     rdx, aLsapapplycapsu; "LsapApplyCAPsUpdate failed"
0x1800ae027  mov     ecx, eax
0x1800ae029  call    LsapSetErrorInfo
0x1800ae02e  call    IsNetpProvCheckOfflineLsaPolicyUpdatePresent
0x1800ae033  test    al, al
0x1800ae035  jz      short loc_1800AE071
0x1800ae037  lea     rcx, [rsp+38h+arg_8]
0x1800ae03c  call    cs:__imp_NetpProvCheckOfflineLsaPolicyUpdate
0x1800ae043  nop     dword ptr [rax+rax+00h]
0x1800ae048  test    eax, eax
0x1800ae04a  jnz     short loc_1800AE071
0x1800ae04c  mov     r8, [rsp+38h+arg_8]
0x1800ae051  lea     edx, [rax+0Ch]
0x1800ae054  mov     rcx, cs:?LsapPolicyHandle@@3PEAXEA; void *
0x1800ae05b  call    LsarSetInformationPolicy
0x1800ae060  lea     rcx, [rsp+38h+arg_8]
0x1800ae065  call    cs:__imp_NetpProvFreeLdapLsaDomainInfo
0x1800ae06c  nop     dword ptr [rax+rax+00h]
0x1800ae071  call    ?LsapLogonSessionInitialize@@YAEXZ; LsapLogonSessionInitialize(void)
0x1800ae076  test    al, al
0x1800ae078  jnz     short loc_1800AE08D
0x1800ae07a  mov     ecx, 0C00000E5h
0x1800ae07f  lea     rdx, aLsaplogonsessi; "LsapLogonSessionInitialize failed"
0x1800ae086  mov     ebx, ecx
0x1800ae088  jmp     loc_1800AE3BC
0x1800ae08d  lea     rcx, ?ProviderLock@@3U_RTL_SRWLOCK@@A; _RTL_SRWLOCK ProviderLock
0x1800ae094  call    cs:__imp_RtlInitializeSRWLock
0x1800ae09b  nop     dword ptr [rax+rax+00h]
0x1800ae0a0  call    ?LsapInitIdProvExtension@@YAJXZ; LsapInitIdProvExtension(void)
0x1800ae0a5  mov     ecx, 80000000h; unsigned __int16 **
0x1800ae0aa  mov     ebx, eax
0x1800ae0ac  add     eax, ecx
0x1800ae0ae  test    ecx, eax
0x1800ae0b0  jnz     short loc_1800AE0C8
0x1800ae0b2  cmp     ebx, 0C00000BBh
0x1800ae0b8  jz      short loc_1800AE0C8
0x1800ae0ba  lea     rdx, aLsapinitidprov; "LsapInitIdProvExtension failed"
0x1800ae0c1  mov     ecx, ebx
0x1800ae0c3  jmp     loc_1800AE3BC
0x1800ae0c8  call    ?LoadPackages@@YAJQEAPEAG0PEBG1@Z; LoadPackages(ushort * * const,ushort * * const,ushort const *,ushort const *)
0x1800ae0cd  mov     ebx, eax
0x1800ae0cf  test    eax, eax
0x1800ae0d1  jns     short loc_1800AE11F
0x1800ae0d3  lea     rdx, aLoadpackagesFa; "LoadPackages failed"
0x1800ae0da  mov     ecx, eax
0x1800ae0dc  call    LsapSetErrorInfo
0x1800ae0e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ae0e8  lea     rax, WPP_GLOBAL_Control
0x1800ae0ef  cmp     rcx, rax
0x1800ae0f2  jz      loc_1800AE3C1
0x1800ae0f8  test    [rcx+1Ch], sil
0x1800ae0fc  jz      loc_1800AE3C1
0x1800ae102  mov     edx, 0Eh
0x1800ae107  mov     rcx, [rcx+10h]
0x1800ae10b  lea     r8, WPP_e5da1992a0263c0d539144257ad05029_Traceguids
0x1800ae112  mov     r9d, ebx
0x1800ae115  call    WPP_SF_d
0x1800ae11a  jmp     loc_1800AE3C1
0x1800ae11f  call    ?CredpInitialize@@YAJXZ; CredpInitialize(void)
0x1800ae124  mov     ebx, eax
0x1800ae126  test    eax, eax
0x1800ae128  jns     short loc_1800AE136
0x1800ae12a  lea     rdx, aCredpinitializ; "CredpInitialize failed"
0x1800ae131  jmp     loc_1800AE3BA
0x1800ae136  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_LocalSystemAccessRights@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_LocalSystemAccessRights@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_LocalSystemAccessRights> `wil::Feature<__WilFeatureTraits_Feature_Servicing_LocalSystemAccessRights>::GetImpl(void)'::`2'::impl
0x1800ae13d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_LocalSystemAccessRights@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_LocalSystemAccessRights>::__private_IsEnabled(void)
0x1800ae142  test    al, al
0x1800ae144  jz      loc_1800AE1CB
0x1800ae14a  cmp     cs:?gpLsaAccountCache@@3PEAVLsaAccountCache@@EA, 0; LsaAccountCache * gpLsaAccountCache
0x1800ae152  jz      short loc_1800AE15B
0x1800ae154  mov     ebx, 0C00000E5h
0x1800ae159  jmp     short loc_1800AE166
0x1800ae15b  call    ?StaticCreate@LsaAccountCache@@SAJPEAPEAV1@@Z; LsaAccountCache::StaticCreate(LsaAccountCache * *)
  ... truncated ...
```
