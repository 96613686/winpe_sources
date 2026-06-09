# sub_1801ECFB4

- ea: `0x1801ecfb4`
- end: `0x1801ee0e1`
- name: `sub_1801ECFB4`
- size: `4397`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1801eb494`

## callees

- `0x18017d1f0`
- `0x1801c8be8`
- `0x1801e36b8`
- `0x1801e955c`
- `0x1801ecfb4`

## string_xrefs

- `0x1801ed79c`: `MpDlpDetoursDllInjectionWaitIntervalInMillisec`
- `0x1801eda22`: `MpDlpCacheSettings`
- `0x1801ed9fc`: `MpDlpForceAllowPlatformUpdateSettings`
- `0x1801eda48`: `MpDlpCacheFileCloseCount`
- `0x1801ed02c`: `PendingPlatformUpdate`
- `0x1801ed266`: `MpMapsNumThreadsDss`
- `0x1801ed28c`: `MpMapsNumThreads`
- `0x1801ed2b2`: `MpSampleSubmissionHighPriNumThreads`
- `0x1801ed2d8`: `MpSampleSubmissionHighPriAgentLifeInMins`
- `0x1801ed2fe`: `MpSampleSubmissionLowPriNumThreads`
- `0x1801ed324`: `MpSampleSubmissionLowPriAgentLifeInMins`
- `0x1801ed3bc`: `MpDisableSigUpdateOnWdoStart`
- `0x1801ed454`: `MpCatchupQuickReattemptLimit`
- `0x1801ed4c6`: `MpFastSigUpdateInterval`
- `0x1801ed694`: `MpFolderGuardDispatchConfiguration`
- `0x1801eda6e`: `MpRbMPlatformServiceCrashToleranceCount`
- `0x1801edaba`: `MpRbMAutomaticEngineRollbackMode`
- `0x1801edae0`: `BmFileOpenList`
- `0x1801edb06`: `BmFileOpenByNameList`
- `0x1801edb2c`: `CAMP_BmFileOpenByFullPathList`
- `0x1801edb52`: `CAMP_MacBMFileOpenExclusions`
- `0x1801edb78`: `CAMP_BmFileOpenByNameList`
- `0x1801edbc4`: `MpRbMAutomaticPlatformRollbackMode`
- `0x1801edbea`: `MpSvcSecStripTIFromServiceDacl`
- `0x1801edc10`: `MpSvcSecHardenDefenderTokenDacl`
- `0x1801edc36`: `MpSvcSecHardenMDEProcessesTokenDacl`
- `0x1801edcce`: `MpServiceHealthMonitorConfig`
- `0x1801edcf4`: `MpSvcOSCopyAcceleratorMode`
- `0x1801edd1a`: `MpSvcOSCopyAcceleratorForceKill`
- `0x1801edd8c`: `MpSvcSecTrustLabelProtectService`
- `0x1801eddb2`: `MpRegLinkHardeningSettings`
- `0x1801ede24`: `MpSvcSecTrustLabelProtectWdFilterService`
- `0x1801edee2`: `MpSkipUnknownsCacheForBmSenseEtw`
- `0x1801edf2e`: `MpRbMPlatformServiceDeadlockToleranceCount`
- `0x1801ee076`: `HttpSigUpdate_BaseUrl_ADL`
- `0x1801ee093`: `HttpSigUpdate_BaseUrl_MOCAMP`
- `0x1801eddfe`: `MpDisableFileSequentialReadEvent`

## pseudocode

```c
__int64 __fastcall sub_1801ECFB4(__int64 a1, int a2)
{
  __int64 result; // rax
  __int64 v5; // rsi
  __int64 i; // rbp
  char v7; // al
  bool v8; // zf
  char v9; // cl
  __int64 *v10; // rax
  _QWORD *v11; // rcx
  unsigned __int64 v12; // rbp
  unsigned __int64 v13; // r14
  unsigned __int64 v14; // r8
  int v15; // eax

  if ( a2 == 4 && (unsigned __int8)sub_1801E955C(a1, off_180C28EE0, 57) )
    return 96;
  if ( !(unsigned int)sub_18017D1F0(a1, L"FfrDisable") )
  {
    if ( a2 == 1 )
      return 2;
    return 1;
  }
  if ( !(unsigned int)sub_18017D1F0(a1, L"PendingPlatformUpdate") )
  {
    if ( a2 == 1 )
      return 7;
    return 1;
  }
  if ( !(unsigned int)sub_18017D1F0(a1, L"MAPSURL") )
  {
    if ( a2 == 4 )
      return 8;
    return 1;
  }
  if ( !(unsigned int)sub_18017D1F0(a1, L"ADLERRORIGNORELIST") )
  {
    if ( a2 == 4 )
      return 9;
    return 1;
  }
  if ( !(unsigned int)sub_18017D1F0(a1, L"MpSSLOptions") )
  {
    if ( a2 == 1 )
      return 10;
    return 1;
  }
  if ( !(unsigned int)sub_18017D1F0(a1, L"EndOfLife") )
  {
    if ( a2 == 4 )
      return 11;
    return 1;
  }
  if ( !(unsigned int)sub_18017D1F0(a1, L"MpMapsWdoDetectionThrottlingInterval") )
  {
    if ( a2 == 1 )
      return 12;
    return 1;
  }
  if ( !(unsigned int)sub_18017D1F0(a1, L"MpRtpTurnOnInterval") )
  {
    if ( a2 == 1 )
      return 13;
    return 1;
  }
  if ( !(unsigned int)sub_18017D1F0(a1, L"BetaPlatform") )
  {
    if ( a2 == 1 )
      return 14;
    return 1;
  }
  if ( !(unsigned int)sub_18017D1F0(a1, L"MpAdlFallbackDelayInDays") )
  {
    if ( a2 == 1 )
      return 15;
    return 1;
  }
  if ( !(unsigned int)sub_18017D1F0(a1, L"MpUseSha1OnlyForWatsonBucketing") )
  {
    if ( a2 == 1 )
      return 16;
    return 1;
  }
  if ( !(unsigned int)sub_18017D1F0(a1, L"MpDeviceIdThrottlingDelayInHours") )
  {
    if ( a2 == 1 )
      return 19;
    return 1;
  }
  if ( !(unsigned int)sub_18017D1F0(a1, L"MpEnableBackendSamplesForRemediation") )
  {
    if ( a2 == 1 )
      return 20;
    return 1;
  }
  if ( !(unsigned int)sub_18017D1F0(a1, L"MpEnableMapsLatencyRetries") )
  {
    if ( a2 == 1 )
      return 21;
    return 1;
  }
  if ( !(unsigned int)sub_18017D1F0(a1, L"MpUseNewSpynetExtra") )
  {
    if ( a2 == 1 )
      return 17;
    return 1;
  }
  if ( !(unsigned int)sub_18017D1F0(a1, L"MpBatchSamplesBySHA") )
  {
    if ( a2 == 1 )
      return 18;
    return 1;
  }
  if ( !(unsigned int)sub_18017D1F0(a1, L"MpMapsNumThreadsDss") )
  {
    if ( a2 == 1 )
      return 22;
    return 1;
  }
  if ( !(unsigned int)sub_18017D1F0(a1, L"MpMapsNumThreads") )
  {
    if ( a2 == 1 )
      return 23;
    return 1;
  }
  if ( !(unsigned int)sub_18017D1F0(a1, L"MpSampleSubmissionHighPriNumThreads") )
  {
    if ( a2 == 1 )
      return 24;
    return 1;
  }
  if ( !(unsigned int)sub_18017D1F0(a1, L"MpSampleSubmissionHighPriAgentLifeInMins") )
  {
    if ( a2 == 1 )
      return 25;
    return 1;
  }
  if ( !(unsigned int)sub_18017D1F0(a1, L"MpSampleSubmissionLowPriNumThreads") )
  {
    if ( a2 == 1 )
      return 26;
    return 1;
  }
  if ( !(unsigned int)sub_18017D1F0(a1, L"MpSampleSubmissionLowPriAgentLifeInMins") )
  {
    if ( a2 == 1 )
      return 27;
    return 1;
  }
  if ( !(unsigned int)sub_18017D1F0(a1, L"MpSampleBlockUploadParallelism") )
  {
    if ( a2 == 1 )
      return 28;
    return 1;
  }
  if ( !(unsigned int)sub_18017D1F0(a1, L"MpRecapIntervalInDays") )
  {
    if ( a2 == 1 )
      return 29;
    return 1;
  }
  if ( !(unsigned int)sub_18017D1F0(a1, L"MpDisableSxsPassiveMode") )
  {
    if ( a2 == 1 )
      return 30;
    return 1;
  }
  if ( !(unsigned int)sub_18017D1F0(a1, L"MpDisableSigUpdateOnWdoStart") )
  {
    if ( a2 == 1 )
      return 31;
    return 1;
  }
  if ( !(unsigned int)sub_18017D1F0(a1, L"MpDisableWdoFromInboxBits") )
  {
    if ( a2 == 1 )
      return 32;
    return 1;
  }
  if ( !(unsigned int)sub_18017D1F0(a1, L"MpDisableNetworkProtection") )
  {
    if ( a2 == 1 )
      return 33;
    return 1;
  }
  if ( !(unsigned int)sub_18017D1F0(a1, L"MpCatchupQuickScanDaysDue") )
  {
    if ( a2 == 1 )
      return 34;
    return 1;
  }
  if ( !(unsigned int)sub_18017D1F0(a1, L"MpCatchupQuickReattemptLimit") )
  {
    if ( a2 == 1 )
      return 35;
    return 1;
  }
  if ( !(unsigned int)sub_18017D1F0(a1, L"MpDisableAdvancedToasts") )
  {
    if ( a2 == 1 )
      return 36;
    return 1;
  }
  if ( !(unsigned int)sub_18017D1F0(a1, L"MpDisableMapsUrlFallbackOnResponseTimeout") )
  {
    if ( a2 == 1 )
      return 37;
    return 1;
  }
  if ( !(unsigned int)sub_18017D1F0(a1, L"MpFastSigUpdateInterval") )
  {
    if ( a2 == 1 )
      return 38;
    return 1;
  }
  if ( !(unsigned int)sub_18017D1F0(a1, L"MpEnableSigReleaseHb") )
  {
    if ( a2 == 1 )
      return 39;
    return 1;
  }
  if ( !(unsigned int)sub_18017D1F0(a1, L"MpFolderGuardDefaultFolders") )
  {
    if ( a2 == 4 )
      return 40;
    return 1;
  }
  if ( (unsigned __int8)sub_1801E955C(a1, off_180C28DC0, 35) )
  {
    if ( a2 == 1 )
      return 3;
    return 1;
  }
  if ( (unsigned __int8)sub_1801E955C(a1, off_180C28C60, 44) )
  {
LABEL_351:
    result = 4;
    if ( a2 == 1 )
      return result;
    return 1;
  }
  if ( (unsigned __int8)sub_1801E955C(a1, off_180C28C50, 2) )
  {
    if ( a2 == 2 )
      return 5;
    return 1;
  }
  if ( (unsigned __int8)sub_1801E955C(a1, off_180C28B70, 27) )
  {
    if ( a2 == 4 )
      return 6;
    return 1;
  }
  if ( (unsigned __int8)sub_1801E955C(a1, off_180C28B00, 14) )
  {
    if ( a2 == 3 )
      return 95;
    return 1;
  }
  v5 = qword_181045F80;
  for ( i = *(_QWORD *)(qword_181045F80 + 8); !*(_BYTE *)(i + 25); i = *v10 )
  {
    v7 = sub_1801E36B8(i + 32, a1);
    v8 = v7 == 0;
    v9 = v7;
    v10 = (__int64 *)(i + 16);
    if ( v8 )
      v5 = i;
    if ( !v9 )
      v10 = (__int64 *)i;
  }
  if ( !*(_BYTE *)(v5 + 25) )
  {
    v11 = (_QWORD *)(v5 + 32);
    v12 = -1;
    do
      ++v12;
    while ( *(_WORD *)(a1 + 2 * v12) );
    v13 = *(_QWORD *)(v5 + 48);
    if ( *(_QWORD *)(v5 + 56) > 7u )
      v11 = (_QWORD *)*v11;
    v14 = *(_QWORD *)(v5 + 48);
    if ( v12 < v13 )
      v14 = v12;
    v15 = sub_1801C8BE8(v11, a1, v14);
    if ( v15 )
    {
      if ( v15 <= 0 )
        goto LABEL_141;
    }
    else if ( v13 <= v12 )
    {
      goto LABEL_141;
    }
  }
  v5 = qword_181045F80;
LABEL_141:
  if ( v5 != qword_181045F80 )
    goto LABEL_351;
  if ( !(unsigned int)sub_18017D1F0(a1, L"MpFolderGuardDispatchConfiguration") )
  {
    if ( a2 == 4 )
      return 41;
    return 1;
  }
  if ( !(unsigned int)sub_18017D1F0(a1, L"MpDisableNetworkFilter") )
  {
    if ( a2 == 1 )
      return 42;
    return 1;
  }
  if ( !(unsigned int)sub_18017D1F0(a1, L"MpUIHistorySize") )
  {
    if ( a2 == 2 )
      return 43;
    return 1;
  }
  if ( !(unsigned int)sub_18017D1F0(a1, L"MpDlpPrintEnforcementFlags") )
  {
    if ( a2 == 1 )
      return 44;
    return 1;
  }
  if ( !(unsigned int)sub_18017D1F0(a1, L"MpDlpEventThrotteIntervalInSec") )
  {
    if ( a2 == 1 )
      return 45;
    return 1;
  }
  if ( !(unsigned int)sub_18017D1F0(a1, L"MpDlpShowDialogs") )
  {
    if ( a2 == 1 )
      return 46;
    return 1;
  }
  if ( !(unsigned int)sub_18017D1F0(a1, L"MpDlpShowIconOverlay") )
  {
    if ( a2 == 1 )
      return 47;
    return 1;
  }
  if ( !(unsigned int)sub_18017D1F0(a1, L"MpDlpDetoursDllInjectionWaitIntervalInMillisec") )
  {
    if ( a2 == 1 )
      return 48;
    return 1;
  }
  if ( !(unsigned int)sub_18017D1F0(a1, L"MpDlpClipboardSettings") )
  {
    if ( a2 == 1 )
      return 49;
    return 1;
  }
  if ( !(unsigned int)sub_18017D1F0(a1, L"MpDlpDefaultClipboardSettings") )
  {
    if ( a2 == 1 )
      return 50;
    return 1;
  }
  if ( !(unsigned int)sub_18017D1F0(a1, L"MpDlpClipboardPasteEventThrottleIntervalInMillisec") )
  {
    if ( a2 == 1 )
      return 51;
    return 1;
  }
  if ( !(unsigned int)sub_18017D1F0(a1, L"MpDisableResourceMonitoring") )
  {
    if ( a2 == 1 )
      return 52;
    return 1;
  }
  if ( !(unsigned int)sub_18017D1F0(a1, L"MpMemoryThresholdInMb") )
  {
    if ( a2 == 1 )
      return 53;
    return 1;
  }
  if ( !(unsigned int)sub_18017D1F0(a1, L"MpCpuThreshold") )
  {
    if ( a2 == 1 )
      return 54;
    return 1;
  }
  if ( !(unsigned int)sub_18017D1F0(a1, L"MpCpuToleranceLevel") )
  {
    if ( a2 == 1 )
      return 55;
    return 1;
  }
  if ( !(unsigned int)sub_18017D1F0(a1, L"MpCpuToleranceInterval") )
  {
    if ( a2 == 1 )
      return 56;
    return 1;
  }
  if ( !(unsigned int)sub_18017D1F0(a1, L"MpDlpAppEnlightenmentSettings") )
  {
    if ( a2 == 1 )
      return 57;
    return 1;
  }
  if ( !(unsigned int)sub_18017D1F0(a1, L"MpDlpFileEvidenceSettings") )
  {
    if ( a2 == 1 )
      return 58;
    return 1;
  }
  if ( !(unsigned int)sub_18017D1F0(a1, L"MpDlpPasteToBrowserSettings") )
  {
    if ( a2 == 1 )
      return 59;
    return 1;
  }
  if ( !(unsigned int)sub_18017D1F0(a1, L"MpDlpPasteToBrowserBufferSizeSettings") )
  {
    if ( a2 == 1 )
      return 103;
    return 1;
  }
  if ( !(unsigned int)sub_18017D1F0(a1, L"MpDlpPasteToBrowserWaitIntervalInSec") )
  {
    if ( a2 == 1 )
      return 104;
    return 1;
  }
  if ( !(unsigned int)sub_18017D1F0(a1, L"MpDlpPasteToBrowserTimeoutInSec") )
  {
    if ( a2 == 1 )
      return 106;
    return 1;
  }
  if ( !(unsigned int)sub_18017D1F0(a1, L"MpDlpPasteToBrowserFallbackModeSettings") )
  {
    if ( a2 == 1 )
      return 105;
    return 1;
  }
  if ( !(unsigned int)sub_18017D1F0(a1, L"MpDlpForceAllowPlatformUpdateSettings") )
  {
    if ( a2 == 1 )
      return 60;
    return 1;
  }
  if ( !(unsigned int)sub_18017D1F0(a1, L"MpDlpCacheSettings") )
  {
    if ( a2 == 1 )
      return 61;
    return 1;
  }
  if ( !(unsigned int)sub_18017D1F0(a1, L"MpDlpCacheFileCloseCount") )
  {
    if ( a2 == 1 )
      return 107;
    return 1;
  }
  if ( !(unsigned int)sub_18017D1F0(a1, L"MpRbMPlatformServiceCrashToleranceCount") )
  {
    if ( a2 == 1 )
      return 62;
    return 1;
  }
  if ( !(unsigned int)sub_18017D1F0(a1, L"MpRbMPlatformMinimumDaysNeededToDetermineLKG") )
  {
    if ( a2 == 1 )
      return 63;
    return 1;
  }
  if ( !(unsigned int)sub_18017D1F0(a1, L"MpRbMAutomaticEngineRollbackMode") )
  {
    if ( a2 == 1 )
      return 64;
    return 1;
  }
  if ( !(unsigned int)sub_18017D1F0(a1, L"BmFileOpenList") )
  {
    if ( a2 == 4 )
      return 65;
    return 1;
  }
  if ( !(unsigned int)sub_18017D1F0(a1, L"BmFileOpenByNameList") )
  {
    if ( a2 == 4 )
      return 66;
    return 1;
  }
  if ( !(unsigned int)sub_18017D1F0(a1, L"CAMP_BmFileOpenByFullPathList") )
  {
    if ( a2 == 4 )
      return 67;
    return 1;
  }
  if ( !(unsigned int)sub_18017D1F0(a1, L"CAMP_MacBMFileOpenExclusions") )
  {
    if ( a2 == 4 )
      return 69;
    return 1;
  }
  if ( !(unsigned int)sub_18017D1F0(a1, L"CAMP_BmFileOpenByNameList") )
  {
    if ( a2 == 4 )
      return 68;
    return 1;
  }
  if ( !(unsigned int)sub_18017D1F0(a1, L"MpDisableRtpTaintNotification") )
  {
    if ( a2 == 1 )
      return 70;
    return 1;
  }
  if ( !(unsigned int)sub_18017D1F0(a1, L"MpRbMAutomaticPlatformRollbackMode") )
  {
    if ( a2 == 1 )
      return 71;
    return 1;
  }
  if ( !(unsigned int)sub_18017D1F0(a1, L"MpSvcSecStripTIFromServiceDacl") )
  {
    if ( a2 == 1 )
      return 72;
    return 1;
  }
  if ( !(unsigned int)sub_18017D1F0(a1, L"MpSvcSecHardenDefenderTokenDacl") )
  {
    if ( a2 == 1 )
      return 73;
    return 1;
  }
  if ( !(unsigned int)sub_18017D1F0(a1, L"MpSvcSecHardenMDEProcessesTokenDacl") )
  {
    if ( a2 == 1 )
      return 74;
    return 1;
  }
  if ( !(unsigned int)sub_18017D1F0(a1, L"MpDlpSpoolerEnlightenmentSettings") )
  {
    if ( a2 == 1 )
      return 76;
    return 1;
  }
  if ( !(unsigned int)sub_18017D1F0(a1, L"MpDlpNetworkEnforcementSettings") )
  {
    if ( a2 == 1 )
      return 85;
    return 1;
  }
  if ( !(unsigned int)sub_18017D1F0(a1, L"MpDlpJitEnforcementSettings") )
  {
    if ( a2 == 1 )
      return 87;
    return 1;
  }
  if ( !(unsigned int)sub_18017D1F0(a1, L"MpServiceHealthMonitorConfig") )
  {
    if ( a2 == 4 )
      return 77;
    return 1;
  }
  if ( !(unsigned int)sub_18017D1F0(a1, L"MpSvcOSCopyAcceleratorMode") )
  {
    if ( a2 == 1 )
      return 78;
    return 1;
  }
  if ( !(unsigned int)sub_18017D1F0(a1, L"MpSvcOSCopyAcceleratorForceKill") )
  {
    if ( a2 == 1 )
      return 79;
    return 1;
  }
  if ( !(unsigned int)sub_18017D1F0(a1, L"MpDlpNWShareGroupsSettings") )
  {
    if ( a2 == 1 )
      return 80;
    return 1;
  }
  if ( !(unsigned int)sub_18017D1F0(a1, L"MpDlpRemovableMediaGroupsSettings") )
  {
    if ( a2 == 1 )
      return 81;
    return 1;
  }
  if ( !(unsigned int)sub_18017D1F0(a1, L"MpSvcSecTrustLabelProtectService") )
  {
    if ( a2 == 1 )
      return 82;
    return 1;
  }
  if ( !(unsigned int)sub_18017D1F0(a1, L"MpRegLinkHardeningSettings") )
  {
    if ( a2 == 1 )
      return 83;
    return 1;
  }
  if ( !(unsigned int)sub_18017D1F0(a1, L"MpRemoteFileInformationState") )
  {
    if ( a2 == 1 )
      return 84;
    return 1;
  }
  if ( !(unsigned int)sub_18017D1F0(a1, L"MpDisableFileSequentialReadEvent") )
  {
    if ( a2 == 1 )
      return 86;
    return 1;
  }
  if ( !(unsigned int)sub_18017D1F0(a1, L"MpSvcSecTrustLabelProtectWdFilterService") )
  {
    if ( a2 == 1 )
      return 88;
    return 1;
  }
  if ( !(unsigned int)sub_18017D1F0(a1, L"MpEnableEnforceGpoRegKeyProtection") )
  {
    if ( a2 == 1 )
      return 89;
    return 1;
  }
  if ( !(unsigned int)sub_18017D1F0(a1, L"MpEfsHardeningFlags") )
  {
    if ( a2 == 1 )
      return 90;
    return 1;
  }
  if ( !(unsigned int)sub_18017D1F0(a1, L"MpDynamicFsHardeningState") )
  {
    if ( a2 == 1 )
      return 91;
    return 1;
  }
  if ( !(unsigned int)sub_18017D1F0(a1, L"MpPreventPagingFileAbuseState") )
  {
    if ( a2 == 1 )
      return 92;
    return 1;
  }
  if ( !(unsigned int)sub_18017D1F0(a1, L"MpSkipUnknownsCacheForBmSenseEtw") )
  {
    if ( a2 == 1 )
      return 93;
    return 1;
  }
  if ( !(unsigned int)sub_18017D1F0(a1, L"MpTrustLabelProtectionStatus") )
  {
    if ( a2 == 1 )
      return 94;
    return 1;
  }
  if ( !(unsigned int)sub_18017D1F0(a1, L"MpRbMPlatformServiceDeadlockToleranceCount") )
  {
    if ( a2 == 1 )
      return 102;
    return 1;
  }
  if ( !(unsigned int)sub_18017D1F0(a1, L"CAMP_GlobalPerformanceProfiles") )
  {
    if ( a2 == 4 )
      return 108;
    return 1;
  }
  if ( !(unsigned int)sub_18017D1F0(a1, L"CAMP_GlobalMuteTargets") )
  {
    if ( a2 == 4 )
      return 109;
    return 1;
  }
  if ( !(unsigned int)sub_18017D1F0(a1, L"CAMP_MacULSPredicates") )
  {
    if ( a2 == 4 )
      return 110;
    return 1;
  }
  if ( !(unsigned int)sub_18017D1F0(a1, L"AIScanSniHostNames") )
  {
    if ( a2 == 4 )
      return 97;
    return 1;
  }
  if ( !(unsigned int)sub_18017D1F0(a1, L"AIScanSkippedContentTypes") )
  {
    if ( a2 == 4 )
      return 98;
    return 1;
  }
  if ( !(unsigned int)sub_18017D1F0(a1, L"AIScanInferenceEndpoints") )
  {
    if ( a2 == 4 )
      return 99;
    return 1;
  }
  if ( !(unsigned int)sub_18017D1F0(a1, L"LocalAIProcessList") )
  {
    if ( a2 == 4 )
      return 100;
    return 1;
  }
  if ( !(unsigned int)sub_18017D1F0(a1, L"CloudAIProcessList") )
  {
    if ( a2 == 4 )
      return 101;
    return 1;
  }
  if ( !(unsigned int)sub_18017D1F0(a1, L"HttpSigUpdate_BaseUrl_ADL") )
  {
    if ( a2 == 3 )
      return 111;
    return 1;
  }
  if ( (unsigned int)sub_18017D1F0(a1, L"HttpSigUpdate_BaseUrl_MOCAMP") )
    return 0;
  result = 112;
  if ( a2 != 3 )
    return 1;
  return result;
}

```

## disassembly

```asm
0x1801ecfb4  mov     [rsp+arg_8], rbx
0x1801ecfb9  mov     [rsp+arg_10], rbp
0x1801ecfbe  mov     [rsp+arg_18], rsi
0x1801ecfc3  push    rdi
0x1801ecfc4  push    r12
0x1801ecfc6  push    r13
0x1801ecfc8  push    r14
0x1801ecfca  push    r15
0x1801ecfcc  sub     rsp, 40h
0x1801ecfd0  xor     r12d, r12d
0x1801ecfd3  mov     ebx, edx
0x1801ecfd5  mov     rdi, rcx
0x1801ecfd8  lea     r13d, [r12+4]
0x1801ecfdd  cmp     edx, r13d
0x1801ecfe0  jnz     short loc_1801ED001
0x1801ecfe2  lea     r8d, [r12+39h]
0x1801ecfe7  lea     rdx, off_180C28EE0; "MpDlpPrintEnforcementFlags"
0x1801ecfee  call    sub_1801E955C
0x1801ecff3  test    al, al
0x1801ecff5  jz      short loc_1801ED001
0x1801ecff7  lea     eax, [r12+60h]
0x1801ecffc  jmp     loc_1801EE0C3
0x1801ed001  lea     rdx, aFfrdisable; "FfrDisable"
0x1801ed008  mov     rcx, rdi
0x1801ed00b  call    sub_18017D1F0
0x1801ed010  mov     r15d, 1
0x1801ed016  test    eax, eax
0x1801ed018  jnz     short loc_1801ED02C
0x1801ed01a  cmp     ebx, r15d
0x1801ed01d  jnz     loc_1801EE0C0
0x1801ed023  lea     eax, [r15+1]
0x1801ed027  jmp     loc_1801EE0C3
0x1801ed02c  lea     rdx, aPendingplatfor; "PendingPlatformUpdate"
0x1801ed033  mov     rcx, rdi
0x1801ed036  call    sub_18017D1F0
0x1801ed03b  test    eax, eax
0x1801ed03d  jnz     short loc_1801ED052
0x1801ed03f  cmp     ebx, r15d
0x1801ed042  jnz     loc_1801EE0C0
0x1801ed048  mov     eax, 7
0x1801ed04d  jmp     loc_1801EE0C3
0x1801ed052  lea     rdx, aMapsurl; "MAPSURL"
0x1801ed059  mov     rcx, rdi
0x1801ed05c  call    sub_18017D1F0
0x1801ed061  test    eax, eax
0x1801ed063  jnz     short loc_1801ED078
0x1801ed065  cmp     ebx, r13d
0x1801ed068  jnz     loc_1801EE0C0
0x1801ed06e  mov     eax, 8
0x1801ed073  jmp     loc_1801EE0C3
0x1801ed078  lea     rdx, aAdlerrorignore; "ADLERRORIGNORELIST"
0x1801ed07f  mov     rcx, rdi
0x1801ed082  call    sub_18017D1F0
0x1801ed087  test    eax, eax
0x1801ed089  jnz     short loc_1801ED09E
0x1801ed08b  cmp     ebx, r13d
0x1801ed08e  jnz     loc_1801EE0C0
0x1801ed094  mov     eax, 9
0x1801ed099  jmp     loc_1801EE0C3
0x1801ed09e  lea     rdx, aMpssloptions; "MpSSLOptions"
0x1801ed0a5  mov     rcx, rdi
0x1801ed0a8  call    sub_18017D1F0
0x1801ed0ad  test    eax, eax
0x1801ed0af  jnz     short loc_1801ED0C4
0x1801ed0b1  cmp     ebx, r15d
0x1801ed0b4  jnz     loc_1801EE0C0
0x1801ed0ba  mov     eax, 0Ah
0x1801ed0bf  jmp     loc_1801EE0C3
0x1801ed0c4  lea     rdx, aEndoflife; "EndOfLife"
0x1801ed0cb  mov     rcx, rdi
0x1801ed0ce  call    sub_18017D1F0
0x1801ed0d3  test    eax, eax
0x1801ed0d5  jnz     short loc_1801ED0EA
0x1801ed0d7  cmp     ebx, r13d
0x1801ed0da  jnz     loc_1801EE0C0
0x1801ed0e0  mov     eax, 0Bh
0x1801ed0e5  jmp     loc_1801EE0C3
0x1801ed0ea  lea     rdx, aMpmapswdodetec; "MpMapsWdoDetectionThrottlingInterval"
0x1801ed0f1  mov     rcx, rdi
0x1801ed0f4  call    sub_18017D1F0
0x1801ed0f9  test    eax, eax
0x1801ed0fb  jnz     short loc_1801ED110
0x1801ed0fd  cmp     ebx, r15d
0x1801ed100  jnz     loc_1801EE0C0
0x1801ed106  mov     eax, 0Ch
0x1801ed10b  jmp     loc_1801EE0C3
0x1801ed110  lea     rdx, aMprtpturnonint; "MpRtpTurnOnInterval"
0x1801ed117  mov     rcx, rdi
0x1801ed11a  call    sub_18017D1F0
0x1801ed11f  test    eax, eax
0x1801ed121  jnz     short loc_1801ED136
0x1801ed123  cmp     ebx, r15d
0x1801ed126  jnz     loc_1801EE0C0
0x1801ed12c  mov     eax, 0Dh
0x1801ed131  jmp     loc_1801EE0C3
0x1801ed136  lea     rdx, aBetaplatform; "BetaPlatform"
0x1801ed13d  mov     rcx, rdi
0x1801ed140  call    sub_18017D1F0
0x1801ed145  test    eax, eax
0x1801ed147  jnz     short loc_1801ED15C
0x1801ed149  cmp     ebx, r15d
0x1801ed14c  jnz     loc_1801EE0C0
0x1801ed152  mov     eax, 0Eh
0x1801ed157  jmp     loc_1801EE0C3
0x1801ed15c  lea     rdx, aMpadlfallbackd; "MpAdlFallbackDelayInDays"
0x1801ed163  mov     rcx, rdi
0x1801ed166  call    sub_18017D1F0
0x1801ed16b  test    eax, eax
0x1801ed16d  jnz     short loc_1801ED182
0x1801ed16f  cmp     ebx, r15d
0x1801ed172  jnz     loc_1801EE0C0
0x1801ed178  mov     eax, 0Fh
0x1801ed17d  jmp     loc_1801EE0C3
0x1801ed182  lea     rdx, aMpusesha1onlyf; "MpUseSha1OnlyForWatsonBucketing"
0x1801ed189  mov     rcx, rdi
0x1801ed18c  call    sub_18017D1F0
0x1801ed191  test    eax, eax
0x1801ed193  jnz     short loc_1801ED1A8
0x1801ed195  cmp     ebx, r15d
0x1801ed198  jnz     loc_1801EE0C0
0x1801ed19e  mov     eax, 10h
0x1801ed1a3  jmp     loc_1801EE0C3
0x1801ed1a8  lea     rdx, aMpdeviceidthro; "MpDeviceIdThrottlingDelayInHours"
0x1801ed1af  mov     rcx, rdi
0x1801ed1b2  call    sub_18017D1F0
0x1801ed1b7  test    eax, eax
0x1801ed1b9  jnz     short loc_1801ED1CE
0x1801ed1bb  cmp     ebx, r15d
0x1801ed1be  jnz     loc_1801EE0C0
0x1801ed1c4  mov     eax, 13h
0x1801ed1c9  jmp     loc_1801EE0C3
0x1801ed1ce  lea     rdx, aMpenablebacken; "MpEnableBackendSamplesForRemediation"
0x1801ed1d5  mov     rcx, rdi
0x1801ed1d8  call    sub_18017D1F0
0x1801ed1dd  test    eax, eax
0x1801ed1df  jnz     short loc_1801ED1F4
0x1801ed1e1  cmp     ebx, r15d
0x1801ed1e4  jnz     loc_1801EE0C0
0x1801ed1ea  mov     eax, 14h
0x1801ed1ef  jmp     loc_1801EE0C3
0x1801ed1f4  lea     rdx, aMpenablemapsla; "MpEnableMapsLatencyRetries"
0x1801ed1fb  mov     rcx, rdi
0x1801ed1fe  call    sub_18017D1F0
0x1801ed203  test    eax, eax
0x1801ed205  jnz     short loc_1801ED21A
0x1801ed207  cmp     ebx, r15d
0x1801ed20a  jnz     loc_1801EE0C0
0x1801ed210  mov     eax, 15h
0x1801ed215  jmp     loc_1801EE0C3
0x1801ed21a  lea     rdx, aMpusenewspynet; "MpUseNewSpynetExtra"
0x1801ed221  mov     rcx, rdi
0x1801ed224  call    sub_18017D1F0
0x1801ed229  test    eax, eax
0x1801ed22b  jnz     short loc_1801ED240
0x1801ed22d  cmp     ebx, r15d
0x1801ed230  jnz     loc_1801EE0C0
0x1801ed236  mov     eax, 11h
0x1801ed23b  jmp     loc_1801EE0C3
0x1801ed240  lea     rdx, aMpbatchsamples; "MpBatchSamplesBySHA"
0x1801ed247  mov     rcx, rdi
0x1801ed24a  call    sub_18017D1F0
0x1801ed24f  test    eax, eax
0x1801ed251  jnz     short loc_1801ED266
0x1801ed253  cmp     ebx, r15d
0x1801ed256  jnz     loc_1801EE0C0
0x1801ed25c  mov     eax, 12h
0x1801ed261  jmp     loc_1801EE0C3
0x1801ed266  lea     rdx, aMpmapsnumthrea; "MpMapsNumThreadsDss"
0x1801ed26d  mov     rcx, rdi
0x1801ed270  call    sub_18017D1F0
0x1801ed275  test    eax, eax
0x1801ed277  jnz     short loc_1801ED28C
0x1801ed279  cmp     ebx, r15d
0x1801ed27c  jnz     loc_1801EE0C0
0x1801ed282  mov     eax, 16h
0x1801ed287  jmp     loc_1801EE0C3
0x1801ed28c  lea     rdx, aMpmapsnumthrea_0; "MpMapsNumThreads"
0x1801ed293  mov     rcx, rdi
0x1801ed296  call    sub_18017D1F0
0x1801ed29b  test    eax, eax
0x1801ed29d  jnz     short loc_1801ED2B2
0x1801ed29f  cmp     ebx, r15d
0x1801ed2a2  jnz     loc_1801EE0C0
0x1801ed2a8  mov     eax, 17h
0x1801ed2ad  jmp     loc_1801EE0C3
0x1801ed2b2  lea     rdx, aMpsamplesubmis; "MpSampleSubmissionHighPriNumThreads"
0x1801ed2b9  mov     rcx, rdi
0x1801ed2bc  call    sub_18017D1F0
0x1801ed2c1  test    eax, eax
0x1801ed2c3  jnz     short loc_1801ED2D8
0x1801ed2c5  cmp     ebx, r15d
0x1801ed2c8  jnz     loc_1801EE0C0
0x1801ed2ce  mov     eax, 18h
0x1801ed2d3  jmp     loc_1801EE0C3
0x1801ed2d8  lea     rdx, aMpsamplesubmis_0; "MpSampleSubmissionHighPriAgentLifeInMin"...
0x1801ed2df  mov     rcx, rdi
0x1801ed2e2  call    sub_18017D1F0
0x1801ed2e7  test    eax, eax
0x1801ed2e9  jnz     short loc_1801ED2FE
0x1801ed2eb  cmp     ebx, r15d
0x1801ed2ee  jnz     loc_1801EE0C0
0x1801ed2f4  mov     eax, 19h
0x1801ed2f9  jmp     loc_1801EE0C3
0x1801ed2fe  lea     rdx, aMpsamplesubmis_1; "MpSampleSubmissionLowPriNumThreads"
0x1801ed305  mov     rcx, rdi
0x1801ed308  call    sub_18017D1F0
0x1801ed30d  test    eax, eax
0x1801ed30f  jnz     short loc_1801ED324
0x1801ed311  cmp     ebx, r15d
0x1801ed314  jnz     loc_1801EE0C0
0x1801ed31a  mov     eax, 1Ah
0x1801ed31f  jmp     loc_1801EE0C3
0x1801ed324  lea     rdx, aMpsamplesubmis_2; "MpSampleSubmissionLowPriAgentLifeInMins"
0x1801ed32b  mov     rcx, rdi
0x1801ed32e  call    sub_18017D1F0
0x1801ed333  test    eax, eax
0x1801ed335  jnz     short loc_1801ED34A
0x1801ed337  cmp     ebx, r15d
0x1801ed33a  jnz     loc_1801EE0C0
0x1801ed340  mov     eax, 1Bh
0x1801ed345  jmp     loc_1801EE0C3
0x1801ed34a  lea     rdx, aMpsampleblocku; "MpSampleBlockUploadParallelism"
0x1801ed351  mov     rcx, rdi
0x1801ed354  call    sub_18017D1F0
0x1801ed359  test    eax, eax
0x1801ed35b  jnz     short loc_1801ED370
0x1801ed35d  cmp     ebx, r15d
0x1801ed360  jnz     loc_1801EE0C0
0x1801ed366  mov     eax, 1Ch
0x1801ed36b  jmp     loc_1801EE0C3
0x1801ed370  lea     rdx, aMprecapinterva; "MpRecapIntervalInDays"
0x1801ed377  mov     rcx, rdi
0x1801ed37a  call    sub_18017D1F0
0x1801ed37f  test    eax, eax
0x1801ed381  jnz     short loc_1801ED396
0x1801ed383  cmp     ebx, r15d
0x1801ed386  jnz     loc_1801EE0C0
0x1801ed38c  mov     eax, 1Dh
0x1801ed391  jmp     loc_1801EE0C3
0x1801ed396  lea     rdx, aMpdisablesxspa; "MpDisableSxsPassiveMode"
0x1801ed39d  mov     rcx, rdi
0x1801ed3a0  call    sub_18017D1F0
0x1801ed3a5  test    eax, eax
0x1801ed3a7  jnz     short loc_1801ED3BC
0x1801ed3a9  cmp     ebx, r15d
0x1801ed3ac  jnz     loc_1801EE0C0
0x1801ed3b2  mov     eax, 1Eh
0x1801ed3b7  jmp     loc_1801EE0C3
0x1801ed3bc  lea     rdx, aMpdisablesigup; "MpDisableSigUpdateOnWdoStart"
0x1801ed3c3  mov     rcx, rdi
0x1801ed3c6  call    sub_18017D1F0
0x1801ed3cb  test    eax, eax
0x1801ed3cd  jnz     short loc_1801ED3E2
0x1801ed3cf  cmp     ebx, r15d
0x1801ed3d2  jnz     loc_1801EE0C0
0x1801ed3d8  mov     eax, 1Fh
0x1801ed3dd  jmp     loc_1801EE0C3
0x1801ed3e2  lea     rdx, aMpdisablewdofr; "MpDisableWdoFromInboxBits"
0x1801ed3e9  mov     rcx, rdi
0x1801ed3ec  call    sub_18017D1F0
0x1801ed3f1  test    eax, eax
0x1801ed3f3  jnz     short loc_1801ED408
0x1801ed3f5  cmp     ebx, r15d
0x1801ed3f8  jnz     loc_1801EE0C0
0x1801ed3fe  mov     eax, 20h ; ' '
0x1801ed403  jmp     loc_1801EE0C3
0x1801ed408  lea     rdx, aMpdisablenetwo; "MpDisableNetworkProtection"
0x1801ed40f  mov     rcx, rdi
0x1801ed412  call    sub_18017D1F0
0x1801ed417  test    eax, eax
0x1801ed419  jnz     short loc_1801ED42E
0x1801ed41b  cmp     ebx, r15d
0x1801ed41e  jnz     loc_1801EE0C0
0x1801ed424  mov     eax, 21h ; '!'
0x1801ed429  jmp     loc_1801EE0C3
0x1801ed42e  lea     rdx, aMpcatchupquick; "MpCatchupQuickScanDaysDue"
0x1801ed435  mov     rcx, rdi
0x1801ed438  call    sub_18017D1F0
0x1801ed43d  test    eax, eax
0x1801ed43f  jnz     short loc_1801ED454
0x1801ed441  cmp     ebx, r15d
0x1801ed444  jnz     loc_1801EE0C0
0x1801ed44a  mov     eax, 22h ; '"'
0x1801ed44f  jmp     loc_1801EE0C3
0x1801ed454  lea     rdx, aMpcatchupquick_0; "MpCatchupQuickReattemptLimit"
0x1801ed45b  mov     rcx, rdi
0x1801ed45e  call    sub_18017D1F0
0x1801ed463  test    eax, eax
0x1801ed465  jnz     short loc_1801ED47A
0x1801ed467  cmp     ebx, r15d
0x1801ed46a  jnz     loc_1801EE0C0
0x1801ed470  mov     eax, 23h ; '#'
0x1801ed475  jmp     loc_1801EE0C3
0x1801ed47a  lea     rdx, aMpdisableadvan; "MpDisableAdvancedToasts"
0x1801ed481  mov     rcx, rdi
0x1801ed484  call    sub_18017D1F0
0x1801ed489  test    eax, eax
0x1801ed48b  jnz     short loc_1801ED4A0
0x1801ed48d  cmp     ebx, r15d
0x1801ed490  jnz     loc_1801EE0C0
  ... truncated ...
```
