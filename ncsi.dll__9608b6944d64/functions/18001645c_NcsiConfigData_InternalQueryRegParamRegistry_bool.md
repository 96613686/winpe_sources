# NcsiConfigData::InternalQueryRegParamRegistry(bool)

- ea: `0x18001645c`
- end: `0x180017654`
- name: `?InternalQueryRegParamRegistry@NcsiConfigData@@AEAAX_N@Z`
- size: `4600`
- prototype: `void __fastcall(NcsiConfigData *__hidden this, bool)`
- caller_count: `2`
- callee_count: `34`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001572c`
- `0x1800529ac`

## callees

- `0x18000afdc`
- `0x18000b0f4`
- `0x18000e59c`
- `0x18000eea0`
- `0x180010200`
- `0x180011a58`
- `0x180013e48`
- `0x18001645c`
- `0x18001d5c8`
- `0x1800211e0`
- `0x180021e7c`
- `0x1800236b4`
- `0x18002bb64`
- `0x18002d6a0`
- `0x1800303fc`
- `0x18003e9e8`
- `0x18003f298`
- `0x18003f2b8`
- `0x180040158`
- `0x18004031c`
- `0x1800416ec`
- `0x180043da0`
- `0x180043df4`
- `0x180047240`
- `0x1800477e8`
- `0x180047f60`
- `0x180047f78`
- `0x18004b570`
- `0x18004b5c4`
- `0x1800510d4`
- `0x180051858`
- `0x1800524c0`
- `0x1800534a8`
- `0x1800618c0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800164bb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180016820`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180016efc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800164bb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180016820`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180016efc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800175d0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800175d0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001709b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001709b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001748e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001748e`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
void __fastcall NcsiConfigData::InternalQueryRegParamRegistry(NcsiConfigData *this, char a2)
{
  int v2; // r13d
  NcsiConfigData *v3; // rcx
  char IsDisableNCSIConnectivityEvaluationSet; // si
  int v5; // edx
  const WCHAR *v6; // rbx
  LPCWSTR *v7; // r8
  char v8; // r12
  NcsiConfigData *v9; // rcx
  unsigned __int8 v10; // al
  NcsiConfigData *v11; // rcx
  int v12; // ebx
  char v13; // si
  bool v14; // cl
  BOOL v15; // eax
  int v16; // r8d
  const char *v17; // r9
  __int64 v18; // rax
  const WCHAR *v19; // rdx
  unsigned int v20; // eax
  struct NCSI_DNS_PROBE_CONFIG *v21; // r14
  char *v22; // rsi
  struct _NCSI_WEB_PROBE_CONFIG *v23; // rbx
  NcsiConfigData *v24; // rcx
  struct _NCSI_WEB_PROBE_CONFIG *v25; // rdi
  NcsiConfigData *v26; // rcx
  __int64 *v27; // rcx
  __int64 v28; // rax
  int *v29; // rcx
  __int64 v30; // rax
  int v31; // eax
  __int64 *v32; // rcx
  _OWORD *v33; // rax
  __int64 v34; // rdx
  _OWORD *v35; // rax
  __int64 v36; // rdx
  struct _NCSI_WEB_PROBE_CONFIG *v37; // rdx
  __int64 v38; // rbx
  __int64 v39; // r9
  DWORD LastError; // eax
  __int32 v41; // ecx
  __int32 v42; // edx
  __int32 v43; // eax
  __int64 v44; // rcx
  char v46; // [rsp+30h] [rbp-D0h]
  __int128 v47; // [rsp+40h] [rbp-C0h] BYREF
  char v48; // [rsp+50h] [rbp-B0h]
  char v49; // [rsp+60h] [rbp-A0h]
  char v50; // [rsp+61h] [rbp-9Fh]
  _BYTE Src[1568]; // [rsp+70h] [rbp-90h] BYREF
  HKEY v52; // [rsp+690h] [rbp+590h] BYREF
  HKEY phkResult; // [rsp+698h] [rbp+598h] BYREF
  HKEY v54; // [rsp+6A0h] [rbp+5A0h] BYREF
  __int128 v55; // [rsp+6A8h] [rbp+5A8h] BYREF
  __int64 v56; // [rsp+6B8h] [rbp+5B8h]
  struct _NCSI_WEB_PROBE_CONFIG *v57; // [rsp+6C0h] [rbp+5C0h] BYREF
  char *v58; // [rsp+6C8h] [rbp+5C8h] BYREF
  struct NCSI_DNS_PROBE_CONFIG *v59; // [rsp+6D0h] [rbp+5D0h] BYREF
  union _SOCKADDR_INET v60; // [rsp+6D8h] [rbp+5D8h] BYREF
  union _SOCKADDR_INET v61; // [rsp+6F8h] [rbp+5F8h] BYREF
  _BYTE v62[64]; // [rsp+720h] [rbp+620h] BYREF
  int v63; // [rsp+760h] [rbp+660h]

  phkResult = 0;
  RegOpenKeyExW(HKEY_LOCAL_MACHINE, c_regKeyParametersConfig, 0, 0x20019u, &phkResult);
  v2 = g_ncsiConfigData;
  IsDisableNCSIConnectivityEvaluationSet = NcsiConfigData::IsDisableNCSIConnectivityEvaluationSet(v3);
  if ( !v5 )
  {
    v47 = *(_OWORD *)&c_regValuePassivePollPeriod;
    _InterlockedExchange(&dword_18009B3A8, GetDWordValue(phkResult, &v47, 15));
    v47 = *(_OWORD *)&c_regValueDisablePassivePollActiveSessionRequirement;
    _InterlockedExchange(&dword_18009B3AC, GetDWordValue(phkResult, &v47, 0));
    v47 = *(_OWORD *)&c_regValueStaleThreshold;
    _InterlockedExchange(&dword_18009B3B0, GetDWordValue(phkResult, &v47, 30));
    v47 = *(_OWORD *)&c_regValueHttpTimeout;
    _InterlockedExchange(&dword_18009B3B4, GetDWordValue(phkResult, &v47, 35));
    v47 = *(_OWORD *)&c_regValueActiveProbing;
    _InterlockedExchange((volatile __int32 *)&g_ncsiConfigData, GetDWordValue(phkResult, &v47, 0));
    v47 = *(_OWORD *)&c_regValueMaxActiveProbes;
    _InterlockedExchange(&dword_18009B3A4, GetDWordValue(phkResult, &v47, 0));
    v47 = *(_OWORD *)&c_regValueMinimumInternetHopCount;
    _InterlockedExchange(&dword_18009B3BC, GetDWordValue(phkResult, &v47, 8));
    v47 = *(_OWORD *)&c_regValueCorpLocationProbeTimeout;
    _InterlockedExchange(&dword_18009B3CC, GetDWordValue(phkResult, &v47, 35));
    v47 = *(_OWORD *)&c_regValueCorpLocationInitialRetryBackoff;
    _InterlockedExchange(&dword_18009B3D0, GetDWordValue(phkResult, &v47, 1));
    v47 = *(_OWORD *)&c_regValueCorpLocationRetryBackoffCap;
    _InterlockedExchange(&dword_18009B3D4, GetDWordValue(phkResult, &v47, 1024));
    v47 = *(_OWORD *)&c_regValueTestMode;
    _InterlockedExchange(&dword_18009B3E4, GetDWordValue(phkResult, &v47, 0));
    v47 = *(_OWORD *)&c_regValueReprobeThreshold;
    _InterlockedExchange(&dword_18009B400, GetDWordValue(phkResult, &v47, 10000));
    v47 = *(_OWORD *)&c_regValueUserActiveProbing;
    _InterlockedExchange(&dword_18009B404, GetDWordValue(phkResult, &v47, 0));
    v47 = *(_OWORD *)&c_regValueCaptivePortalTimer;
    _InterlockedExchange(&dword_18009B40C, GetDWordValue(phkResult, &v47, 0));
    v47 = *(_OWORD *)&c_regValueCaptivePortalIncrements;
    _InterlockedExchange(&dword_18009B414, GetDWordValue(phkResult, &v47, 5));
    v47 = *(_OWORD *)&c_regValueCaptivePortalTimerMax;
    _InterlockedExchange(&dword_18009B410, GetDWordValue(phkResult, &v47, 30));
    v47 = *(_OWORD *)&c_regValueDisableRetryFallbackUrl;
    _InterlockedExchange((volatile __int32 *)&dword_18009B418, GetDWordValue(phkResult, &v47, 0));
    v47 = *(_OWORD *)&c_regValueDisableNCSIConnectivityEvaluation;
    _InterlockedExchange(&dword_18009B41C, GetDWordValue(phkResult, &v47, 0));
  }
  v6 = (const WCHAR *)&g_ncsiRegistry;
  v7 = &g_ncsiRegistry;
  if ( (unsigned __int64)qword_18009AA78 > 7 )
    v7 = (LPCWSTR *)g_ncsiRegistry;
  v8 = std::_Traits_equal<std::char_traits<unsigned short>>(c_regKeyParametersConfig, 60, v7, qword_18009AA70);
  v52 = 0;
  if ( (unsigned __int64)qword_18009AA78 > 7 )
    v6 = g_ncsiRegistry;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, v6, 0, 0x20019u, &v52) && !v8 )
  {
    v47 = *(_OWORD *)&c_regValuePassivePollPeriod;
    _InterlockedExchange(&dword_18009B3A8, GetDWordValue(v52, &v47, (unsigned int)dword_18009B3A8));
    v47 = *(_OWORD *)&c_regValueDisablePassivePollActiveSessionRequirement;
    _InterlockedExchange(&dword_18009B3AC, GetDWordValue(v52, &v47, (unsigned int)dword_18009B3AC));
    v47 = *(_OWORD *)&c_regValueStaleThreshold;
    _InterlockedExchange(&dword_18009B3B0, GetDWordValue(v52, &v47, (unsigned int)dword_18009B3B0));
    v47 = *(_OWORD *)&c_regValueHttpTimeout;
    _InterlockedExchange(&dword_18009B3B4, GetDWordValue(v52, &v47, (unsigned int)dword_18009B3B4));
    v47 = *(_OWORD *)&c_regValueActiveProbing;
    _InterlockedExchange((volatile __int32 *)&g_ncsiConfigData, GetDWordValue(v52, &v47, g_ncsiConfigData));
    v47 = *(_OWORD *)&c_regValueMaxActiveProbes;
    _InterlockedExchange(&dword_18009B3A4, GetDWordValue(v52, &v47, (unsigned int)dword_18009B3A4));
    v47 = *(_OWORD *)&c_regValueMinimumInternetHopCount;
    _InterlockedExchange(&dword_18009B3BC, GetDWordValue(v52, &v47, (unsigned int)dword_18009B3BC));
    v47 = *(_OWORD *)&c_regValueCorpLocationProbeTimeout;
    _InterlockedExchange(&dword_18009B3CC, GetDWordValue(v52, &v47, (unsigned int)dword_18009B3CC));
    v47 = *(_OWORD *)&c_regValueCorpLocationInitialRetryBackoff;
    _InterlockedExchange(&dword_18009B3D0, GetDWordValue(v52, &v47, (unsigned int)dword_18009B3D0));
    v47 = *(_OWORD *)&c_regValueCorpLocationRetryBackoffCap;
    _InterlockedExchange(&dword_18009B3D4, GetDWordValue(v52, &v47, (unsigned int)dword_18009B3D4));
    v47 = *(_OWORD *)&c_regValueTestMode;
    _InterlockedExchange(&dword_18009B3E4, GetDWordValue(v52, &v47, (unsigned int)dword_18009B3E4));
    v47 = *(_OWORD *)&c_regValueReprobeThreshold;
    _InterlockedExchange(&dword_18009B400, GetDWordValue(v52, &v47, (unsigned int)dword_18009B400));
    v47 = *(_OWORD *)&c_regValueUserActiveProbing;
    _InterlockedExchange(&dword_18009B404, GetDWordValue(v52, &v47, (unsigned int)dword_18009B404));
    v47 = *(_OWORD *)&c_regValueCaptivePortalTimer;
    _InterlockedExchange(&dword_18009B40C, GetDWordValue(v52, &v47, 0));
    v47 = *(_OWORD *)&c_regValueCaptivePortalIncrements;
    _InterlockedExchange(&dword_18009B414, GetDWordValue(v52, &v47, 5));
    v47 = *(_OWORD *)&c_regValueCaptivePortalTimerMax;
    _InterlockedExchange(&dword_18009B410, GetDWordValue(v52, &v47, 30));
    v47 = *(_OWORD *)&c_regValueDisableRetryFallbackUrl;
    _InterlockedExchange((volatile __int32 *)&dword_18009B418, GetDWordValue(v52, &v47, 0));
    v47 = *(_OWORD *)&c_regValueDisableNCSIConnectivityEvaluation;
    _InterlockedExchange(&dword_18009B41C, GetDWordValue(phkResult, &v47, 0));
  }
  v10 = NcsiConfigData::IsDisableNCSIConnectivityEvaluationSet(v9);
  v12 = v10;
  if ( IsDisableNCSIConnectivityEvaluationSet == v10 )
  {
    v13 = 0;
  }
  else
  {
    v13 = 1;
    v14 = !v10 && !NcsiConfigData::IsPassivePollingDisabled(v11);
    Ncsi::PassivePoll::PassivePollManager::EnablePolling(v14);
    LODWORD(v54) = v12;
    memset_0(v62, 0, sizeof(v62));
    v63 = 8;
    std::any::operator=<_NcsiPassivePollingConfigChangeMetadata,0>((__int64)v62, &v54);
    v48 = 0;
    NlmManager::PublishDiagnosticsNotificationToNlm((struct std::any *)v62);
    std::any::reset((std::any *)v62);
  }
  if ( v2 != g_ncsiConfigData || v13 )
  {
    v15 = !g_ncsiConfigData || (_BYTE)v12;
    LODWORD(v54) = v15;
    memset_0(v62, 0, sizeof(v62));
    v63 = 4;
    std::any::operator=<_NcsiActiveProbeConfigChangeMetadata,0>((__int64)v62, &v54);
    v48 = 0;
    NlmManager::PublishDiagnosticsNotificationToNlm((struct std::any *)v62);
    std::any::reset((std::any *)v62);
  }
  LoadCacheStateFromKey(v52);
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x10) != 0
    && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 4u )
  {
    v17 = "enabled";
    if ( !dword_18009B3A4 )
      v17 = "disabled";
    WPP_SF_sd(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), (unsigned int)"disabled", v16, (_DWORD)v17, dword_18009B3A4);
  }
  if ( !dword_18009B3CC )
    ((void (*)(void))MicrosoftTelemetryAssertTriggeredNoArgs)();
  if ( !dword_18009B3D0 )
    ((void (*)(void))MicrosoftTelemetryAssertTriggeredNoArgs)();
  if ( !dword_18009B3D4 )
    ((void (*)(void))MicrosoftTelemetryAssertTriggeredNoArgs)();
  if ( !dword_18009B3CC )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x10) != 0
      && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 3u )
    {
      WPP_SF_dd(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        40,
        &WPP_5540ffa188b23fc0b8d03d8186783076_Traceguids,
        (unsigned int)dword_18009B3CC,
        35);
    }
    _InterlockedExchange(&dword_18009B3CC, 35);
  }
  if ( !dword_18009B3D0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x10) != 0
      && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 3u )
    {
      WPP_SF_dd(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        41,
        &WPP_5540ffa188b23fc0b8d03d8186783076_Traceguids,
        (unsigned int)dword_18009B3D0,
        1);
    }
    _InterlockedExchange(&dword_18009B3D0, 1);
  }
  if ( !dword_18009B3D4 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x10) != 0
      && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 3u )
    {
      WPP_SF_dd(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        42,
        &WPP_5540ffa188b23fc0b8d03d8186783076_Traceguids,
        (unsigned int)dword_18009B3D4,
        1);
    }
    _InterlockedExchange(&dword_18009B3D4, 1024);
  }
  v18 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x10) != 0 && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 5u )
    {
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        43,
        &WPP_5540ffa188b23fc0b8d03d8186783076_Traceguids,
        (unsigned int)dword_18009B3CC);
      v18 = WPP_GLOBAL_Control;
    }
    if ( (_UNKNOWN *)v18 != &WPP_GLOBAL_Control )
    {
      if ( (*(_BYTE *)(v18 + 28) & 0x10) != 0 && *(_BYTE *)(v18 + 25) >= 5u )
      {
        WPP_SF_d(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          44,
          &WPP_5540ffa188b23fc0b8d03d8186783076_Traceguids,
          (unsigned int)dword_18009B3D0);
        v18 = WPP_GLOBAL_Control;
      }
      if ( (_UNKNOWN *)v18 != &WPP_GLOBAL_Control && (*(_BYTE *)(v18 + 28) & 0x10) != 0 && *(_BYTE *)(v18 + 25) >= 5u )
        WPP_SF_d(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          45,
          &WPP_5540ffa188b23fc0b8d03d8186783076_Traceguids,
          (unsigned int)dword_18009B3D4);
    }
  }
  if ( a2 )
  {
    v54 = 0;
    v19 = (const WCHAR *)&qword_18009AA80;
    if ( (unsigned __int64)qword_18009AA98 > 7 )
      v19 = qword_18009AA80;
    v20 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v19, 0, 0x20019u, &v54);
    if ( v20 )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x10) != 0
        && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
      {
        WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 46, &WPP_5540ffa188b23fc0b8d03d8186783076_Traceguids, v20);
      }
    }
    else
    {
      LoadGatewayCache(v54);
    }
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v54);
  }
  v21 = (struct NCSI_DNS_PROBE_CONFIG *)operator new(0x224u, (const struct std::nothrow_t *)&std::nothrow);
  v59 = v21;
  v22 = (char *)operator new(0x224u, (const struct std::nothrow_t *)&std::nothrow);
  v58 = v22;
  v23 = (struct _NCSI_WEB_PROBE_CONFIG *)operator new(0x61Au, (const struct std::nothrow_t *)&std::nothrow);
  v57 = v23;
  v25 = (struct _NCSI_WEB_PROBE_CONFIG *)operator new(0x61Au, (const struct std::nothrow_t *)&std::nothrow);
  v54 = (HKEY)v25;
  v55 = 0;
  v56 = 0;
  if ( v21 && v22 )
  {
    v49 = 1;
    NcsiConfigData::LoadDnsProbeData(v24, phkResult, v21, (struct NCSI_DNS_PROBE_CONFIG *)v22);
    if ( !v8 )
      NcsiConfigData::LoadDnsProbeData(v24, v52, v21, (struct NCSI_DNS_PROBE_CONFIG *)v22);
  }
  else
  {
    v49 = 0;
  }
  if ( v23 && v25 )
  {
    v46 = 1;
    NcsiConfigData::LoadWebProbeData(v24, phkResult, v23, v25);
    if ( !v8 )
      NcsiConfigData::LoadWebProbeData(v24, v52, v23, v25);
  }
  else
  {
    v46 = 0;
  }
  v50 = NcsiConfigData::LoadManualProxies(v24, v52, &v55);
  memset(&v60, 0, sizeof(v60));
  memset(&v61, 0, sizeof(v61));
  NcsiConfigData::LoadInternetDestinationAddresses(v26, &v60, &v61);
  EnterCriticalSection(&stru_18009D378);
  *(_QWORD *)&v47 = &stru_18009D378;
  xmmword_18009B428 = (__int128)v60.Ipv4;
  *(__int128 *)((char *)&xmmword_18009B428 + 12) = *(_OWORD *)(&v60.si_family + 6);
  xmmword_18009B444 = (__int128)v61.Ipv4;
  *(__int128 *)((char *)&xmmword_18009B444 + 12) = *(_OWORD *)(&v61.si_family + 6);
  if ( v49 )
  {
    v27 = qword_18009B460;
    v28 = 4;
    do
    {
      *(_OWORD *)v27 = *(_OWORD *)v21;
      *((_OWORD *)v27 + 1) = *((_OWORD *)v21 + 1);
      *((_OWORD *)v27 + 2) = *((_OWORD *)v21 + 2);
      *((_OWORD *)v27 + 3) = *((_OWORD *)v21 + 3);
      *((_OWORD *)v27 + 4) = *((_OWORD *)v21 + 4);
      *((_OWORD *)v27 + 5) = *((_OWORD *)v21 + 5);
      *((_OWORD *)v27 + 6) = *((_OWORD *)v21 + 6);
      *((_OWORD *)v27 + 7) = *((_OWORD *)v21 + 7);
      v27 += 16;
      v21 = (struct NCSI_DNS_PROBE_CONFIG *)((char *)v21 + 128);
      --v28;
    }
    while ( v28 );
    *(_OWORD *)v27 = *(_OWORD *)v21;
    *((_OWORD *)v27 + 1) = *((_OWORD *)v21 + 1);
    *((_DWORD *)v27 + 8) = *((_DWORD *)v21 + 8);
    v29 = &dword_18009B684;
    v30 = 4;
    do
    {
      *(_OWORD *)v29 = *(_OWORD *)v22;
      *((_OWORD *)v29 + 1) = *((_OWORD *)v22 + 1);
      *((_OWORD *)v29 + 2) = *((_OWORD *)v22 + 2);
      *((_OWORD *)v29 + 3) = *((_OWORD *)v22 + 3);
      *((_OWORD *)v29 + 4) = *((_OWORD *)v22 + 4);
      *((_OWORD *)v29 + 5) = *((_OWORD *)v22 + 5);
      *((_OWORD *)v29 + 6) = *((_OWORD *)v22 + 6);
      *((_OWORD *)v29 + 7) = *((_OWORD *)v22 + 7);
      v29 += 32;
      v22 += 128;
      --v30;
    }
    while ( v30 );
    *(_OWORD *)v29 = *(_OWORD *)v22;
    *((_OWORD *)v29 + 1) = *((_OWORD *)v22 + 1);
    v31 = *((_DWORD *)v22 + 8);
  }
  else
  {
    memset_0(Src, 0, 0x224u);
    v32 = qword_18009B460;
    v33 = Src;
    v34 = 4;
    do
    {
      *(_OWORD *)v32 = *v33;
      *((_OWORD *)v32 + 1) = v33[1];
      *((_OWORD *)v32 + 2) = v33[2];
      *((_OWORD *)v32 + 3) = v33[3];
      *((_OWORD *)v32 + 4) = v33[4];
      *((_OWORD *)v32 + 5) = v33[5];
      *((_OWORD *)v32 + 6) = v33[6];
      *((_OWORD *)v32 + 7) = v33[7];
      v32 += 16;
      v33 += 8;
      --v34;
    }
    while ( v34 );
    *(_OWORD *)v32 = *v33;
    *((_OWORD *)v32 + 1) = v33[1];
    *((_DWORD *)v32 + 8) = *((_DWORD *)v33 + 8);
    memset_0(Src, 0, 0x224u);
    v29 = &dword_18009B684;
    v35 = Src;
    v36 = 4;
    do
    {
      *(_OWORD *)v29 = *v35;
      *((_OWORD *)v29 + 1) = v35[1];
      *((_OWORD *)v29 + 2) = v35[2];
      *((_OWORD *)v29 + 3) = v35[3];
      *((_OWORD *)v29 + 4) = v35[4];
      *((_OWORD *)v29 + 5) = v35[5];
      *((_OWORD *)v29 + 6) = v35[6];
      *((_OWORD *)v29 + 7) = v35[7];
      v29 += 32;
      v35 += 8;
      --v36;
    }
    while ( v36 );
    *(_OWORD *)v29 = *v35;
    *((_OWORD *)v29 + 1) = v35[1];
    v31 = *((_DWORD *)v35 + 8);
  }
  v29[8] = v31;
  if ( v46 )
  {
    memcpy_0(qword_18009B8A8, v23, 0x61Au);
    v37 = v25;
  }
  else
  {
    memset_0(Src, 0, 0x61Au);
    memcpy_0(qword_18009B8A8, Src, 0x61Au);
    memset_0(Src, 0, 0x61Au);
    v37 = (struct _NCSI_WEB_PROBE_CONFIG *)Src;
  }
  memcpy_0(word_18009BEC2, v37, 0x61Au);
  if ( v50 )
  {
    v38 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x10) != 0
      && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 5u )
    {
      v39 = v55;
      if ( (_QWORD)v55 == *((_QWORD *)&v55 + 1) )
        v39 = 0;
      WPP_SF_S(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 47, &WPP_5540ffa188b23fc0b8d03d8186783076_Traceguids, v39);
      v38 = WPP_GLOBAL_Control;
    }
    if ( (unsigned __int8)std::operator==<unsigned short,std::allocator<unsigned short>>(&v55, &qword_18009D358) )
    {
      if ( (_UNKNOWN *)v38 != &WPP_GLOBAL_Control && (*(_BYTE *)(v38 + 28) & 0x10) != 0 && *(_BYTE *)(v38 + 25) >= 4u )
        WPP_SF_(*(_QWORD *)(v38 + 16), 48, &WPP_5540ffa188b23fc0b8d03d8186783076_Traceguids);
    }
    else
    {
      std::vector<unsigned short>::operator=(&qword_18009D358, &v55);
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x10) != 0
        && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 5u )
      {
        WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 49, &WPP_5540ffa188b23fc0b8d03d8186783076_Traceguids);
      }
      if ( CheckIfClientPresent() )
      {
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x10) != 0
          && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 5u )
        {
          WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 50, &WPP_5540ffa188b23fc0b8d03d8186783076_Traceguids);
        }
        if ( !(unsigned int)NcsiThreadPoolTrySubmit((PTP_SIMPLE_CALLBACK)RespondToProxyOpportunity, (PVOID)1)
          && (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x10) != 0
          && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
        {
          LastError = GetLastError();
          WPP_SF_d(
            *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
            51,
            &WPP_5540ffa188b23fc0b8d03d8186783076_Traceguids,
            LastError);
        }
      }
    }
  }
  else
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x10) != 0
      && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
    {
      WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 52, &WPP_5540ffa188b23fc0b8d03d8186783076_Traceguids);
    }
    if ( qword_18009D358 != qword_18009D360 )
      qword_18009D360 = qword_18009D358;
  }
  if ( (dword_18009B3E4 & 1) != 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x10) != 0
      && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 5u )
    {
      WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 54, &WPP_5540ffa188b23fc0b8d03d8186783076_Traceguids);
    }
    v41 = 480000;
    v42 = 60000;
    v43 = 2000;
  }
  else
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x10) != 0
      && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 5u )
    {
      WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 53, &WPP_5540ffa188b23fc0b8d03d8186783076_Traceguids);
    }
    v41 = 7200000;
    v42 = 900000;
    v43 = 30000;
  }
  _InterlockedExchange(&dword_18009B3E8, v43);
  _InterlockedExchange(&dword_18009B3EC, 10);
  _InterlockedExchange(&dword_18009B3F0, 1);
  _InterlockedExchange(&dword_18009B3F4, v42);
  v44 = (unsigned int)_InterlockedExchange(&dword_18009B3F8, v41);
  _InterlockedExchange(&dword_18009B3FC, 2);
  if ( dword_18009B3E8 >= (unsigned int)dword_18009B3F4 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v44);
  LeaveCriticalSection(&stru_18009D378);
  std::vector<unsigned short>::_Tidy(&v55);
  std::unique_ptr<_NCSI_WEB_PROBE_CONFIG>::~unique_ptr<_NCSI_WEB_PROBE_CONFIG>(&v54);
  std::unique_ptr<_NCSI_WEB_PROBE_CONFIG>::~unique_ptr<_NCSI_WEB_PROBE_CONFIG>(&v57);
  std::unique_ptr<NCSI_DNS_PROBE_CONFIG>::~unique_ptr<NCSI_DNS_PROBE_CONFIG>(&v58);
  std::unique_ptr<NCSI_DNS_PROBE_CONFIG>::~unique_ptr<NCSI_DNS_PROBE_CONFIG>(&v59);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v52);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
}

```

## disassembly

```asm
0x18001645c  push    rbp
0x18001645e  push    rbx
0x18001645f  push    rsi
0x180016460  push    rdi
0x180016461  push    r12
0x180016463  push    r13
0x180016465  push    r14
0x180016467  push    r15
0x180016469  lea     rbp, [rsp-688h]
0x180016471  sub     rsp, 788h
0x180016478  mov     rax, cs:__security_cookie
0x18001647f  xor     rax, rsp
0x180016482  mov     [rbp+6C0h+var_50], rax
0x180016489  mov     [rsp+7C0h+var_790], dl
0x18001648d  mov     [rbp+6C0h+var_128], 0
0x180016498  lea     rax, [rbp+6C0h+var_128]
0x18001649f  mov     [rsp+7C0h+phkResult], rax; phkResult
0x1800164a4  mov     r9d, 20019h; samDesired
0x1800164aa  xor     r8d, r8d; ulOptions
0x1800164ad  mov     rdx, cs:?c_regKeyParametersConfig@@3V?$basic_zstring_view@G@wil@@B; lpSubKey
0x1800164b4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800164bb  call    cs:__imp_RegOpenKeyExW
0x1800164c1  mov     edx, eax
0x1800164c3  mov     r13d, cs:?g_ncsiConfigData@@3VNcsiConfigData@@A; NcsiConfigData g_ncsiConfigData
0x1800164ca  nop
0x1800164cb  call    ?IsDisableNCSIConnectivityEvaluationSet@NcsiConfigData@@QEAA_NXZ; NcsiConfigData::IsDisableNCSIConnectivityEvaluationSet(void)
0x1800164d0  mov     sil, al
0x1800164d3  mov     ebx, 1Eh
0x1800164d8  lea     edi, [rbx+5]
0x1800164db  lea     r15d, [rbx-1Dh]
0x1800164df  mov     r14d, 400h
0x1800164e5  test    edx, edx
0x1800164e7  jnz     loc_1800167B1
0x1800164ed  movups  xmm0, xmmword ptr cs:?c_regValuePassivePollPeriod@@3V?$basic_zstring_view@G@wil@@B; wil::basic_zstring_view<ushort> const c_regValuePassivePollPeriod
0x1800164f4  movdqu  [rsp+7C0h+var_780], xmm0
0x1800164fa  lea     r8d, [rbx-0Fh]
0x1800164fe  lea     rdx, [rsp+7C0h+var_780]
0x180016503  mov     rcx, [rbp+6C0h+var_128]
0x18001650a  call    GetDWordValue
0x18001650f  xchg    eax, cs:dword_18009B3A8
0x180016515  movups  xmm0, xmmword ptr cs:?c_regValueDisablePassivePollActiveSessionRequirement@@3V?$basic_zstring_view@G@wil@@B; wil::basic_zstring_view<ushort> const c_regValueDisablePassivePollActiveSessionRequirement
0x18001651c  movdqu  [rsp+7C0h+var_780], xmm0
0x180016522  xor     r8d, r8d
0x180016525  lea     rdx, [rsp+7C0h+var_780]
0x18001652a  mov     rcx, [rbp+6C0h+var_128]
0x180016531  call    GetDWordValue
0x180016536  xchg    eax, cs:dword_18009B3AC
0x18001653c  movups  xmm0, xmmword ptr cs:?c_regValueStaleThreshold@@3V?$basic_zstring_view@G@wil@@B; wil::basic_zstring_view<ushort> const c_regValueStaleThreshold
0x180016543  movdqu  [rsp+7C0h+var_780], xmm0
0x180016549  mov     r8d, ebx
0x18001654c  lea     rdx, [rsp+7C0h+var_780]
0x180016551  mov     rcx, [rbp+6C0h+var_128]
0x180016558  call    GetDWordValue
0x18001655d  xchg    eax, cs:dword_18009B3B0
0x180016563  movups  xmm0, xmmword ptr cs:?c_regValueHttpTimeout@@3V?$basic_zstring_view@G@wil@@B; wil::basic_zstring_view<ushort> const c_regValueHttpTimeout
0x18001656a  movdqu  [rsp+7C0h+var_780], xmm0
0x180016570  mov     r8d, edi
0x180016573  lea     rdx, [rsp+7C0h+var_780]
0x180016578  mov     rcx, [rbp+6C0h+var_128]
0x18001657f  call    GetDWordValue
0x180016584  xchg    eax, cs:dword_18009B3B4
0x18001658a  movups  xmm0, xmmword ptr cs:?c_regValueActiveProbing@@3V?$basic_zstring_view@G@wil@@B; wil::basic_zstring_view<ushort> const c_regValueActiveProbing
0x180016591  movdqu  [rsp+7C0h+var_780], xmm0
0x180016597  xor     r8d, r8d
0x18001659a  lea     rdx, [rsp+7C0h+var_780]
0x18001659f  mov     rcx, [rbp+6C0h+var_128]
0x1800165a6  call    GetDWordValue
0x1800165ab  xchg    eax, cs:?g_ncsiConfigData@@3VNcsiConfigData@@A; NcsiConfigData g_ncsiConfigData
0x1800165b1  movups  xmm0, xmmword ptr cs:?c_regValueMaxActiveProbes@@3V?$basic_zstring_view@G@wil@@B; wil::basic_zstring_view<ushort> const c_regValueMaxActiveProbes
0x1800165b8  movdqu  [rsp+7C0h+var_780], xmm0
0x1800165be  xor     r8d, r8d
0x1800165c1  lea     rdx, [rsp+7C0h+var_780]
0x1800165c6  mov     rcx, [rbp+6C0h+var_128]
0x1800165cd  call    GetDWordValue
0x1800165d2  xchg    eax, cs:dword_18009B3A4
0x1800165d8  movups  xmm0, xmmword ptr cs:?c_regValueMinimumInternetHopCount@@3V?$basic_zstring_view@G@wil@@B; wil::basic_zstring_view<ushort> const c_regValueMinimumInternetHopCount
0x1800165df  movdqu  [rsp+7C0h+var_780], xmm0
0x1800165e5  lea     r8d, [rbx-16h]
0x1800165e9  lea     rdx, [rsp+7C0h+var_780]
0x1800165ee  mov     rcx, [rbp+6C0h+var_128]
0x1800165f5  call    GetDWordValue
0x1800165fa  xchg    eax, cs:dword_18009B3BC
0x180016600  movups  xmm0, xmmword ptr cs:?c_regValueCorpLocationProbeTimeout@@3V?$basic_zstring_view@G@wil@@B; wil::basic_zstring_view<ushort> const c_regValueCorpLocationProbeTimeout
0x180016607  movdqu  [rsp+7C0h+var_780], xmm0
0x18001660d  mov     r8d, edi
0x180016610  lea     rdx, [rsp+7C0h+var_780]
0x180016615  mov     rcx, [rbp+6C0h+var_128]
0x18001661c  call    GetDWordValue
0x180016621  xchg    eax, cs:dword_18009B3CC
0x180016627  movups  xmm0, xmmword ptr cs:?c_regValueCorpLocationInitialRetryBackoff@@3V?$basic_zstring_view@G@wil@@B; wil::basic_zstring_view<ushort> const c_regValueCorpLocationInitialRetryBackoff
0x18001662e  movdqu  [rsp+7C0h+var_780], xmm0
0x180016634  mov     r8d, r15d
0x180016637  lea     rdx, [rsp+7C0h+var_780]
0x18001663c  mov     rcx, [rbp+6C0h+var_128]
0x180016643  call    GetDWordValue
0x180016648  xchg    eax, cs:dword_18009B3D0
0x18001664e  movups  xmm0, xmmword ptr cs:?c_regValueCorpLocationRetryBackoffCap@@3V?$basic_zstring_view@G@wil@@B; wil::basic_zstring_view<ushort> const c_regValueCorpLocationRetryBackoffCap
0x180016655  movdqu  [rsp+7C0h+var_780], xmm0
0x18001665b  mov     r8d, r14d
0x18001665e  lea     rdx, [rsp+7C0h+var_780]
0x180016663  mov     rcx, [rbp+6C0h+var_128]
0x18001666a  call    GetDWordValue
0x18001666f  xchg    eax, cs:dword_18009B3D4
0x180016675  movups  xmm0, xmmword ptr cs:?c_regValueTestMode@@3V?$basic_zstring_view@G@wil@@B; wil::basic_zstring_view<ushort> const c_regValueTestMode
0x18001667c  movdqu  [rsp+7C0h+var_780], xmm0
0x180016682  xor     r8d, r8d
0x180016685  lea     rdx, [rsp+7C0h+var_780]
0x18001668a  mov     rcx, [rbp+6C0h+var_128]
0x180016691  call    GetDWordValue
0x180016696  xchg    eax, cs:dword_18009B3E4
0x18001669c  movups  xmm0, xmmword ptr cs:?c_regValueReprobeThreshold@@3V?$basic_zstring_view@G@wil@@B; wil::basic_zstring_view<ushort> const c_regValueReprobeThreshold
0x1800166a3  movdqu  [rsp+7C0h+var_780], xmm0
0x1800166a9  mov     r8d, 2710h
0x1800166af  lea     rdx, [rsp+7C0h+var_780]
0x1800166b4  mov     rcx, [rbp+6C0h+var_128]
0x1800166bb  call    GetDWordValue
0x1800166c0  xchg    eax, cs:dword_18009B400
0x1800166c6  movups  xmm0, xmmword ptr cs:?c_regValueUserActiveProbing@@3V?$basic_zstring_view@G@wil@@B; wil::basic_zstring_view<ushort> const c_regValueUserActiveProbing
0x1800166cd  movdqu  [rsp+7C0h+var_780], xmm0
0x1800166d3  xor     r8d, r8d
0x1800166d6  lea     rdx, [rsp+7C0h+var_780]
0x1800166db  mov     rcx, [rbp+6C0h+var_128]
0x1800166e2  call    GetDWordValue
0x1800166e7  xchg    eax, cs:dword_18009B404
0x1800166ed  movups  xmm0, xmmword ptr cs:?c_regValueCaptivePortalTimer@@3V?$basic_zstring_view@G@wil@@B; wil::basic_zstring_view<ushort> const c_regValueCaptivePortalTimer
0x1800166f4  movdqu  [rsp+7C0h+var_780], xmm0
0x1800166fa  xor     r8d, r8d
0x1800166fd  lea     rdx, [rsp+7C0h+var_780]
0x180016702  mov     rcx, [rbp+6C0h+var_128]
0x180016709  call    GetDWordValue
0x18001670e  xchg    eax, cs:dword_18009B40C
0x180016714  movups  xmm0, xmmword ptr cs:?c_regValueCaptivePortalIncrements@@3V?$basic_zstring_view@G@wil@@B; wil::basic_zstring_view<ushort> const c_regValueCaptivePortalIncrements
0x18001671b  movdqu  [rsp+7C0h+var_780], xmm0
0x180016721  lea     r8d, [rbx-19h]
0x180016725  lea     rdx, [rsp+7C0h+var_780]
0x18001672a  mov     rcx, [rbp+6C0h+var_128]
0x180016731  call    GetDWordValue
0x180016736  xchg    eax, cs:dword_18009B414
0x18001673c  movups  xmm0, xmmword ptr cs:?c_regValueCaptivePortalTimerMax@@3V?$basic_zstring_view@G@wil@@B; wil::basic_zstring_view<ushort> const c_regValueCaptivePortalTimerMax
0x180016743  movdqu  [rsp+7C0h+var_780], xmm0
0x180016749  mov     r8d, ebx
0x18001674c  lea     rdx, [rsp+7C0h+var_780]
0x180016751  mov     rcx, [rbp+6C0h+var_128]
0x180016758  call    GetDWordValue
0x18001675d  xchg    eax, cs:dword_18009B410
0x180016763  movups  xmm0, xmmword ptr cs:?c_regValueDisableRetryFallbackUrl@@3V?$basic_zstring_view@G@wil@@B; wil::basic_zstring_view<ushort> const c_regValueDisableRetryFallbackUrl
0x18001676a  movdqu  [rsp+7C0h+var_780], xmm0
0x180016770  xor     r8d, r8d
0x180016773  lea     rdx, [rsp+7C0h+var_780]
0x180016778  mov     rcx, [rbp+6C0h+var_128]
0x18001677f  call    GetDWordValue
0x180016784  xchg    eax, cs:dword_18009B418
0x18001678a  movups  xmm0, xmmword ptr cs:?c_regValueDisableNCSIConnectivityEvaluation@@3V?$basic_zstring_view@G@wil@@B; wil::basic_zstring_view<ushort> const c_regValueDisableNCSIConnectivityEvaluation
0x180016791  movdqu  [rsp+7C0h+var_780], xmm0
0x180016797  xor     r8d, r8d
0x18001679a  lea     rdx, [rsp+7C0h+var_780]
0x18001679f  mov     rcx, [rbp+6C0h+var_128]
0x1800167a6  call    GetDWordValue
0x1800167ab  xchg    eax, cs:dword_18009B41C
0x1800167b1  lea     rbx, ?g_ncsiRegistry@@3VNcsiRegistry@@A; NcsiRegistry g_ncsiRegistry
0x1800167b8  mov     r8, rbx
0x1800167bb  cmp     cs:qword_18009AA78, 7
0x1800167c3  cmova   r8, cs:?g_ncsiRegistry@@3VNcsiRegistry@@A; NcsiRegistry g_ncsiRegistry
0x1800167cb  mov     r9, cs:qword_18009AA70
0x1800167d2  mov     edx, 3Ch ; '<'
0x1800167d7  mov     rcx, cs:?c_regKeyParametersConfig@@3V?$basic_zstring_view@G@wil@@B; wil::basic_zstring_view<ushort> const c_regKeyParametersConfig
0x1800167de  call    ??$_Traits_equal@U?$char_traits@G@std@@@std@@YA_NQEBG_K01@Z; std::_Traits_equal<std::char_traits<ushort>>(ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x1800167e3  mov     r12b, al
0x1800167e6  mov     [rbp+6C0h+var_130], 0
0x1800167f1  cmp     cs:qword_18009AA78, 7
0x1800167f9  cmova   rbx, cs:?g_ncsiRegistry@@3VNcsiRegistry@@A; NcsiRegistry g_ncsiRegistry
0x180016801  lea     rax, [rbp+6C0h+var_130]
0x180016808  mov     [rsp+7C0h+phkResult], rax; phkResult
0x18001680d  mov     r9d, 20019h; samDesired
0x180016813  xor     r8d, r8d; ulOptions
0x180016816  mov     rdx, rbx; lpSubKey
0x180016819  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180016820  call    cs:__imp_RegOpenKeyExW
0x180016826  test    eax, eax
0x180016828  jnz     loc_180016B3C
0x18001682e  test    r12b, r12b
0x180016831  jnz     loc_180016B3C
0x180016837  mov     r8d, cs:dword_18009B3A8
0x18001683e  nop
0x18001683f  movups  xmm0, xmmword ptr cs:?c_regValuePassivePollPeriod@@3V?$basic_zstring_view@G@wil@@B; wil::basic_zstring_view<ushort> const c_regValuePassivePollPeriod
0x180016846  movdqu  [rsp+7C0h+var_780], xmm0
0x18001684c  lea     rdx, [rsp+7C0h+var_780]
0x180016851  mov     rcx, [rbp+6C0h+var_130]
0x180016858  call    GetDWordValue
0x18001685d  xchg    eax, cs:dword_18009B3A8
0x180016863  mov     r8d, cs:dword_18009B3AC
0x18001686a  nop
0x18001686b  movups  xmm0, xmmword ptr cs:?c_regValueDisablePassivePollActiveSessionRequirement@@3V?$basic_zstring_view@G@wil@@B; wil::basic_zstring_view<ushort> const c_regValueDisablePassivePollActiveSessionRequirement
0x180016872  movdqu  [rsp+7C0h+var_780], xmm0
0x180016878  lea     rdx, [rsp+7C0h+var_780]
0x18001687d  mov     rcx, [rbp+6C0h+var_130]
0x180016884  call    GetDWordValue
0x180016889  xchg    eax, cs:dword_18009B3AC
0x18001688f  mov     r8d, cs:dword_18009B3B0
0x180016896  nop
0x180016897  movups  xmm0, xmmword ptr cs:?c_regValueStaleThreshold@@3V?$basic_zstring_view@G@wil@@B; wil::basic_zstring_view<ushort> const c_regValueStaleThreshold
0x18001689e  movdqu  [rsp+7C0h+var_780], xmm0
0x1800168a4  lea     rdx, [rsp+7C0h+var_780]
0x1800168a9  mov     rcx, [rbp+6C0h+var_130]
0x1800168b0  call    GetDWordValue
0x1800168b5  xchg    eax, cs:dword_18009B3B0
0x1800168bb  mov     r8d, cs:dword_18009B3B4
0x1800168c2  nop
0x1800168c3  movups  xmm0, xmmword ptr cs:?c_regValueHttpTimeout@@3V?$basic_zstring_view@G@wil@@B; wil::basic_zstring_view<ushort> const c_regValueHttpTimeout
0x1800168ca  movdqu  [rsp+7C0h+var_780], xmm0
0x1800168d0  lea     rdx, [rsp+7C0h+var_780]
0x1800168d5  mov     rcx, [rbp+6C0h+var_130]
0x1800168dc  call    GetDWordValue
0x1800168e1  xchg    eax, cs:dword_18009B3B4
0x1800168e7  mov     r8d, cs:?g_ncsiConfigData@@3VNcsiConfigData@@A; NcsiConfigData g_ncsiConfigData
0x1800168ee  nop
0x1800168ef  movups  xmm0, xmmword ptr cs:?c_regValueActiveProbing@@3V?$basic_zstring_view@G@wil@@B; wil::basic_zstring_view<ushort> const c_regValueActiveProbing
0x1800168f6  movdqu  [rsp+7C0h+var_780], xmm0
0x1800168fc  lea     rdx, [rsp+7C0h+var_780]
0x180016901  mov     rcx, [rbp+6C0h+var_130]
0x180016908  call    GetDWordValue
0x18001690d  xchg    eax, cs:?g_ncsiConfigData@@3VNcsiConfigData@@A; NcsiConfigData g_ncsiConfigData
0x180016913  mov     r8d, cs:dword_18009B3A4
0x18001691a  nop
0x18001691b  movups  xmm0, xmmword ptr cs:?c_regValueMaxActiveProbes@@3V?$basic_zstring_view@G@wil@@B; wil::basic_zstring_view<ushort> const c_regValueMaxActiveProbes
0x180016922  movdqu  [rsp+7C0h+var_780], xmm0
0x180016928  lea     rdx, [rsp+7C0h+var_780]
0x18001692d  mov     rcx, [rbp+6C0h+var_130]
0x180016934  call    GetDWordValue
0x180016939  xchg    eax, cs:dword_18009B3A4
0x18001693f  mov     r8d, cs:dword_18009B3BC
0x180016946  nop
0x180016947  movups  xmm0, xmmword ptr cs:?c_regValueMinimumInternetHopCount@@3V?$basic_zstring_view@G@wil@@B; wil::basic_zstring_view<ushort> const c_regValueMinimumInternetHopCount
0x18001694e  movdqu  [rsp+7C0h+var_780], xmm0
0x180016954  lea     rdx, [rsp+7C0h+var_780]
0x180016959  mov     rcx, [rbp+6C0h+var_130]
0x180016960  call    GetDWordValue
0x180016965  xchg    eax, cs:dword_18009B3BC
0x18001696b  mov     r8d, cs:dword_18009B3CC
0x180016972  nop
0x180016973  movups  xmm0, xmmword ptr cs:?c_regValueCorpLocationProbeTimeout@@3V?$basic_zstring_view@G@wil@@B; wil::basic_zstring_view<ushort> const c_regValueCorpLocationProbeTimeout
0x18001697a  movdqu  [rsp+7C0h+var_780], xmm0
0x180016980  lea     rdx, [rsp+7C0h+var_780]
0x180016985  mov     rcx, [rbp+6C0h+var_130]
0x18001698c  call    GetDWordValue
0x180016991  xchg    eax, cs:dword_18009B3CC
0x180016997  mov     r8d, cs:dword_18009B3D0
0x18001699e  nop
0x18001699f  movups  xmm0, xmmword ptr cs:?c_regValueCorpLocationInitialRetryBackoff@@3V?$basic_zstring_view@G@wil@@B; wil::basic_zstring_view<ushort> const c_regValueCorpLocationInitialRetryBackoff
0x1800169a6  movdqu  [rsp+7C0h+var_780], xmm0
0x1800169ac  lea     rdx, [rsp+7C0h+var_780]
0x1800169b1  mov     rcx, [rbp+6C0h+var_130]
0x1800169b8  call    GetDWordValue
0x1800169bd  xchg    eax, cs:dword_18009B3D0
0x1800169c3  mov     r8d, cs:dword_18009B3D4
0x1800169ca  nop
0x1800169cb  movups  xmm0, xmmword ptr cs:?c_regValueCorpLocationRetryBackoffCap@@3V?$basic_zstring_view@G@wil@@B; wil::basic_zstring_view<ushort> const c_regValueCorpLocationRetryBackoffCap
0x1800169d2  movdqu  [rsp+7C0h+var_780], xmm0
0x1800169d8  lea     rdx, [rsp+7C0h+var_780]
0x1800169dd  mov     rcx, [rbp+6C0h+var_130]
0x1800169e4  call    GetDWordValue
0x1800169e9  xchg    eax, cs:dword_18009B3D4
0x1800169ef  mov     r8d, cs:dword_18009B3E4
0x1800169f6  nop
0x1800169f7  movups  xmm0, xmmword ptr cs:?c_regValueTestMode@@3V?$basic_zstring_view@G@wil@@B; wil::basic_zstring_view<ushort> const c_regValueTestMode
0x1800169fe  movdqu  [rsp+7C0h+var_780], xmm0
0x180016a04  lea     rdx, [rsp+7C0h+var_780]
0x180016a09  mov     rcx, [rbp+6C0h+var_130]
0x180016a10  call    GetDWordValue
0x180016a15  xchg    eax, cs:dword_18009B3E4
0x180016a1b  mov     r8d, cs:dword_18009B400
0x180016a22  nop
0x180016a23  movups  xmm0, xmmword ptr cs:?c_regValueReprobeThreshold@@3V?$basic_zstring_view@G@wil@@B; wil::basic_zstring_view<ushort> const c_regValueReprobeThreshold
0x180016a2a  movdqu  [rsp+7C0h+var_780], xmm0
0x180016a30  lea     rdx, [rsp+7C0h+var_780]
0x180016a35  mov     rcx, [rbp+6C0h+var_130]
0x180016a3c  call    GetDWordValue
0x180016a41  xchg    eax, cs:dword_18009B400
0x180016a47  mov     r8d, cs:dword_18009B404
0x180016a4e  nop
0x180016a4f  movups  xmm0, xmmword ptr cs:?c_regValueUserActiveProbing@@3V?$basic_zstring_view@G@wil@@B; wil::basic_zstring_view<ushort> const c_regValueUserActiveProbing
0x180016a56  movdqu  [rsp+7C0h+var_780], xmm0
0x180016a5c  lea     rdx, [rsp+7C0h+var_780]
0x180016a61  mov     rcx, [rbp+6C0h+var_130]
0x180016a68  call    GetDWordValue
0x180016a6d  xchg    eax, cs:dword_18009B404
0x180016a73  movups  xmm0, xmmword ptr cs:?c_regValueCaptivePortalTimer@@3V?$basic_zstring_view@G@wil@@B; wil::basic_zstring_view<ushort> const c_regValueCaptivePortalTimer
0x180016a7a  movdqu  [rsp+7C0h+var_780], xmm0
0x180016a80  xor     r8d, r8d
0x180016a83  lea     rdx, [rsp+7C0h+var_780]
0x180016a88  mov     rcx, [rbp+6C0h+var_130]
0x180016a8f  call    GetDWordValue
0x180016a94  xchg    eax, cs:dword_18009B40C
0x180016a9a  movups  xmm0, xmmword ptr cs:?c_regValueCaptivePortalIncrements@@3V?$basic_zstring_view@G@wil@@B; wil::basic_zstring_view<ushort> const c_regValueCaptivePortalIncrements
0x180016aa1  movdqu  [rsp+7C0h+var_780], xmm0
0x180016aa7  mov     r8d, 5
0x180016aad  lea     rdx, [rsp+7C0h+var_780]
0x180016ab2  mov     rcx, [rbp+6C0h+var_130]
0x180016ab9  call    GetDWordValue
0x180016abe  xchg    eax, cs:dword_18009B414
  ... truncated ...
```
