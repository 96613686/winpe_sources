# MFTRACE_STRING_FROM_MET(ulong)

- ea: `0x180138c34`
- end: `0x180139378`
- name: `?MFTRACE_STRING_FROM_MET@@YAPEBDK@Z`
- size: `1860`
- prototype: `const char *__fastcall(unsigned int)`
- caller_count: `3`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180026370`
- `0x180026aa0`
- `0x180048cfc`

## callees

- `0x180138c34`

## string_xrefs

- `0x180138ed9`: `MEUpdatedStream`
- `0x180138fdd`: `MEStreamSinkFormatChanged`
- `0x180138f68`: `MEStreamSinkStarted`
- `0x180138fd5`: `MEStreamSinkStopped`
- `0x180138fcd`: `MEStreamSinkPaused`
- `0x180138fc5`: `MEStreamSinkRateChanged`
- `0x180138fb5`: `MEStreamSinkMarker`
- `0x180138fbd`: `MEStreamSinkRequestSample`
- `0x180138fad`: `MEStreamSinkPrerolled`
- `0x180138fa5`: `MEStreamSinkScrubSampleComplete`
- `0x18013900a`: `MEAudioSessionDeviceRemoved`
- `0x180139032`: `MEStreamSinkDeviceChanged`
- `0x180138d2f`: `MESessionScrubSampleComplete`
- `0x180139278`: `MEPMPTopologyCreated`
- `0x180139280`: `MEPMPRemoveStream`
- `0x180139288`: `MEPMPDropToken`
- `0x1801390b2`: `MEWMDRMLicenseBackupCompleted`
- `0x1801390a2`: `MEWMDRMLicenseRestoreCompleted`
- `0x180139144`: `MEWMDRMLicenseAcquisitionCompleted`
- `0x180138dc8`: `MELicenseAcquisitionCompleted`
- `0x18013913c`: `MEWMDRMIndividualizationCompleted`
- `0x180138db8`: `MEIndividualizationCompleted`
- `0x180138da8`: `MEEnablerCompleted`
- `0x18013912c`: `MEWMDRMProximityCompleted`
- `0x180138dfa`: `MESessionStreamSinkFormatChanged`
- `0x18013914c`: `METransformDrainComplete`
- `0x1801391bc`: `MEVideoCaptureDeviceRemoved`
- `0x1801391ac`: `MEStreamSinkFormatInvalidated`

## pseudocode

```c
const char *__fastcall MFTRACE_STRING_FROM_MET(unsigned int a1)
{
  unsigned int v1; // ecx
  unsigned int v2; // ecx
  unsigned int v3; // ecx
  unsigned int v4; // ecx
  unsigned int v5; // ecx
  unsigned int v6; // ecx
  const char *result; // rax
  unsigned int v8; // ecx
  unsigned int v9; // ecx
  unsigned int v10; // ecx
  unsigned int v11; // ecx
  unsigned int v12; // ecx
  unsigned int v13; // ecx
  unsigned int v14; // ecx
  unsigned int v15; // ecx
  unsigned int v16; // ecx
  unsigned int v17; // ecx
  unsigned int v18; // ecx
  unsigned int v19; // ecx
  unsigned int v20; // ecx
  unsigned int v21; // ecx
  unsigned int v22; // ecx
  unsigned int v23; // ecx
  unsigned int v24; // ecx
  unsigned int v25; // ecx
  unsigned int v26; // ecx
  unsigned int v27; // ecx
  unsigned int v28; // ecx
  unsigned int v29; // ecx
  unsigned int v30; // ecx
  unsigned int v31; // ecx
  unsigned int v32; // ecx
  unsigned int v33; // ecx
  unsigned int v34; // ecx
  unsigned int v35; // ecx
  unsigned int v36; // ecx
  unsigned int v37; // ecx
  unsigned int v38; // ecx
  unsigned int v39; // ecx
  unsigned int v40; // ecx
  unsigned int v41; // ecx
  unsigned int v42; // ecx
  unsigned int v43; // ecx
  unsigned int v44; // ecx
  unsigned int v45; // ecx
  unsigned int v46; // ecx
  unsigned int v47; // ecx
  unsigned int v48; // ecx
  unsigned int v49; // ecx
  unsigned int v50; // ecx
  unsigned int v51; // ecx
  unsigned int v52; // ecx
  unsigned int v53; // ecx
  unsigned int v54; // ecx
  unsigned int v55; // ecx
  unsigned int v56; // ecx
  unsigned int v57; // ecx
  unsigned int v58; // ecx
  unsigned int v59; // ecx
  unsigned int v60; // ecx
  unsigned int v61; // ecx
  unsigned int v62; // ecx
  unsigned int v63; // ecx
  unsigned int v64; // ecx
  unsigned int v65; // ecx
  unsigned int v66; // ecx
  unsigned int v67; // ecx
  unsigned int v68; // ecx
  unsigned int v69; // ecx
  unsigned int v70; // ecx
  unsigned int v71; // ecx
  unsigned int v72; // ecx
  unsigned int v73; // ecx
  unsigned int v74; // ecx
  unsigned int v75; // ecx
  unsigned int v76; // ecx
  unsigned int v77; // ecx

  if ( a1 <= 0x13C )
  {
    if ( a1 == 316 )
      return "MEAudioSessionServerShutdown";
    if ( a1 > 0xCB )
    {
      if ( a1 > 0x12D )
      {
        if ( a1 > 0x135 )
        {
          v47 = a1 - 310;
          if ( !v47 )
            return "MEStreamSinkDeviceChanged";
          v48 = v47 - 1;
          if ( !v48 )
            return "MEQualityNotify";
          v49 = v48 - 1;
          if ( !v49 )
            return "MESinkInvalidated";
          v50 = v49 - 1;
          if ( !v50 )
            return "MEAudioSessionNameChanged";
          v51 = v50 - 1;
          if ( !v51 )
            return "MEAudioSessionVolumeChanged";
          if ( v51 == 1 )
            return "MEAudioSessionDeviceRemoved";
        }
        else
        {
          if ( a1 == 309 )
            return "MEStreamSinkFormatChanged";
          v41 = a1 - 302;
          if ( !v41 )
            return "MEStreamSinkStopped";
          v42 = v41 - 1;
          if ( !v42 )
            return "MEStreamSinkPaused";
          v43 = v42 - 1;
          if ( !v43 )
            return "MEStreamSinkRateChanged";
          v44 = v43 - 1;
          if ( !v44 )
            return "MEStreamSinkRequestSample";
          v45 = v44 - 1;
          if ( !v45 )
            return "MEStreamSinkMarker";
          v46 = v45 - 1;
          if ( !v46 )
            return "MEStreamSinkPrerolled";
          if ( v46 == 1 )
            return "MEStreamSinkScrubSampleComplete";
        }
      }
      else
      {
        if ( a1 == 301 )
          return "MEStreamSinkStarted";
        if ( a1 > 0xD5 )
        {
          v34 = a1 - 214;
          if ( !v34 )
            return "MEStreamTick";
          v35 = v34 - 1;
          if ( !v35 )
            return "MEStreamThinMode";
          v36 = v35 - 1;
          if ( !v36 )
            return "MEStreamFormatChanged";
          v37 = v36 - 1;
          if ( !v37 )
            return "MESourceRateChanged";
          v38 = v37 - 1;
          if ( !v38 )
            return "MEEndOfPresentationSegment";
          v39 = v38 - 1;
          if ( !v39 )
            return "MESourceCharacteristicsChanged";
          v40 = v39 - 1;
          if ( !v40 )
            return "MESourceRateChangeRequested";
          if ( v40 == 1 )
            return "MESourceMetadataChanged";
        }
        else
        {
          if ( a1 == 213 )
            return "MEMediaSample";
          v26 = a1 - 204;
          if ( !v26 )
            return "MEStreamSeeked";
          v27 = v26 - 1;
          if ( !v27 )
            return "MENewStream";
          v28 = v27 - 1;
          if ( !v28 )
            return "MEUpdatedStream";
          v29 = v28 - 1;
          if ( !v29 )
            return "MESourceStopped";
          v30 = v29 - 1;
          if ( !v30 )
            return "MEStreamStopped";
          v31 = v30 - 1;
          if ( !v31 )
            return "MESourcePaused";
          v32 = v31 - 1;
          if ( !v32 )
            return "MEStreamPaused";
          v33 = v32 - 1;
          if ( !v33 )
            return "MEEndOfPresentation";
          if ( v33 == 1 )
            return "MEEndOfStream";
        }
      }
    }
    else
    {
      if ( a1 == 203 )
        return "MESourceSeeked";
      if ( a1 > 0x72 )
      {
        if ( a1 > 0xC9 )
          return "MEStreamStarted";
        if ( a1 == 201 )
          return "MESourceStarted";
        if ( a1 > 0x7A )
        {
          v21 = a1 - 123;
          if ( !v21 )
            return "MEBufferingStopped";
          v22 = v21 - 1;
          if ( !v22 )
            return "MEConnectStart";
          v23 = v22 - 1;
          if ( !v23 )
            return "MEConnectEnd";
          v24 = v23 - 1;
          if ( !v24 )
            return "MEReconnectStart";
          v25 = v24 - 1;
          if ( !v25 )
            return "MEReconnectEnd";
          if ( v25 == 2 )
            return "MESessionStreamSinkFormatChanged";
        }
        else
        {
          if ( a1 == 122 )
            return "MEBufferingStarted";
          v15 = a1 - 115;
          if ( !v15 )
            return "MELicenseAcquisitionCompleted";
          v16 = v15 - 1;
          if ( !v16 )
            return "MEIndividualizationStart";
          v17 = v16 - 1;
          if ( !v17 )
            return "MEIndividualizationCompleted";
          v18 = v17 - 1;
          if ( !v18 )
            return "MEEnablerProgress";
          v19 = v18 - 1;
          if ( !v19 )
            return "MEEnablerCompleted";
          v20 = v19 - 1;
          if ( !v20 )
            return "MEPolicyError";
          if ( v20 == 1 )
            return "MEPolicyReport";
        }
      }
      else
      {
        if ( a1 == 114 )
          return "MELicenseAcquisitionStart";
        if ( a1 > 0x69 )
        {
          v8 = a1 - 106;
          if ( !v8 )
            return "MESessionClosed";
          v9 = v8 - 1;
          if ( !v9 )
            return "MESessionEnded";
          v10 = v9 - 1;
          if ( !v10 )
            return "MESessionRateChanged";
          v11 = v10 - 1;
          if ( !v11 )
            return "MESessionScrubSampleComplete";
          v12 = v11 - 1;
          if ( !v12 )
            return "MESessionCapabilitiesChanged";
          v13 = v12 - 1;
          if ( !v13 )
            return "MESessionTopologyStatus";
          v14 = v13 - 1;
          if ( !v14 )
            return "MESessionNotifyPresentationTime";
          if ( v14 == 1 )
            return "MENewPresentation";
        }
        else
        {
          if ( a1 == 105 )
            return "MESessionStopped";
          if ( !a1 )
            return "MEUnknown";
          v1 = a1 - 1;
          if ( !v1 )
            return "MEError";
          v2 = v1 - 1;
          if ( !v2 )
            return "MEExtendedType";
          v3 = v2 - 1;
          if ( !v3 )
            return "MENonFatalError";
          v4 = v3 - 98;
          if ( !v4 )
            return "MESessionTopologySet";
          v5 = v4 - 1;
          if ( !v5 )
            return "MESessionTopologiesCleared";
          v6 = v5 - 1;
          if ( !v6 )
            return "MESessionStarted";
          if ( v6 == 1 )
            return "MESessionPaused";
        }
      }
    }
    return "unknown event";
  }
  if ( a1 <= 0x2527 )
  {
    if ( a1 == 9511 )
      return "MEBitPumpScrubbed";
    if ( a1 > 0x25B )
    {
      if ( a1 > 0x251F )
      {
        v72 = a1 - 9504;
        if ( !v72 )
          return "MEMediaProcessorTopologyChanged";
        v73 = v72 - 1;
        if ( !v73 )
          return "MEBitPumpStarted";
        v74 = v73 - 1;
        if ( !v74 )
          return "MEBitPumpSeeked";
        v75 = v74 - 1;
        if ( !v75 )
          return "MEBitPumpPaused";
        v76 = v75 - 1;
        if ( !v76 )
          return "MEBitPumpPrerolled";
        v77 = v76 - 1;
        if ( !v77 )
          return "MEBitPumpStopped";
        if ( v77 == 1 )
          return "MEBitPumpEndOfStream";
      }
      else
      {
        if ( a1 == 9503 )
          return "MEMediaProcessorDropRequest";
        v65 = a1 - 604;
        if ( !v65 )
          return "METransformMarker";
        v66 = v65 - 1;
        if ( !v66 )
          return "METransformInputStreamStateChanged";
        v67 = v66 - 195;
        if ( !v67 )
          return "MEVideoCaptureDeviceRemoved";
        v68 = v67 - 1;
        if ( !v68 )
          return "MEVideoCaptureDevicePreempted";
        v69 = v68 - 1;
        if ( !v69 )
          return "MEStreamSinkFormatInvalidated";
        v70 = v69 - 1;
        if ( !v70 )
          return "MEEncodingParameters";
        v71 = v70 - 8698;
        if ( !v71 )
          return "MEMediaProcessorTopologySet";
        if ( v71 == 1 )
          return "MEMediaProcessorMarkout";
      }
    }
    else
    {
      if ( a1 == 603 )
        return "METransformDrainComplete";
      if ( a1 > 0x1F7 )
      {
        v59 = a1 - 506;
        if ( !v59 )
          return "MEWMDRMLicenseAcquisitionCompleted";
        v60 = v59 - 2;
        if ( !v60 )
          return "MEWMDRMIndividualizationCompleted";
        v61 = v60 - 5;
        if ( !v61 )
          return "MEWMDRMIndividualizationProgress";
        v62 = v61 - 1;
        if ( !v62 )
          return "MEWMDRMProximityCompleted";
        v63 = v62 - 1;
        if ( !v63 )
          return "MEWMDRMLicenseStoreCleaned";
        v64 = v63 - 86;
        if ( !v64 )
          return "METransformNeedInput";
        if ( v64 == 1 )
          return "METransformHaveOutput";
      }
      else
      {
        if ( a1 == 503 )
          return "MEWMDRMLicenseRestoreProgress";
        v52 = a1 - 317;
        if ( !v52 )
          return "MEAudioSessionGroupingParamChanged";
        v53 = v52 - 1;
        if ( !v53 )
          return "MEAudioSessionIconChanged";
        v54 = v53 - 83;
        if ( !v54 )
          return "MEPolicyChanged";
        v55 = v54 - 1;
        if ( !v55 )
          return "MEContentProtectionMessage";
        v56 = v55 - 1;
        if ( !v56 )
          return "MEPolicySet";
        v57 = v56 - 97;
        if ( !v57 )
          return "MEWMDRMLicenseBackupCompleted";
        v58 = v57 - 1;
        if ( !v58 )
          return "MEWMDRMLicenseBackupProgress";
        if ( v58 == 1 )
          return "MEWMDRMLicenseRestoreCompleted";
      }
    }
    return "unknown event";
  }
  switch ( a1 )
  {
    case 0x2528u:
      result = "MEBitPumpShutdown";
      break;
    case 0x252Au:
      result = "MEBitPumpEndOfSegment";
      break;
    case 0x252Bu:
      result = "MEPMPTopologyCreated";
      break;
    case 0x252Cu:
      result = "MEPMPRemoveStream";
      break;
    case 0x252Du:
      result = "MEPMPDropToken";
      break;
    case 0x252Eu:
      result = "MENetSessionUnknown";
      break;
    case 0x252Fu:
      result = "MENetSessionAuthenticate";
      break;
    case 0x2530u:
      result = "MENetSessionAuthorize";
      break;
    case 0x2531u:
      result = "MENetSessionUrlTransform";
      break;
    case 0x2532u:
      result = "MENetSessionProfiles";
      break;
    case 0x2533u:
      result = "MENetSessionCardeaLicenseRequest";
      break;
    case 0x2534u:
      result = "MENetSessionDownload";
      break;
    case 0x2535u:
      result = "MENetSessionDescribe";
      break;
    case 0x2536u:
      result = "MENetSessionSelectStreams";
      break;
    case 0x2537u:
      result = "MENetSessionPlay";
      break;
    case 0x2538u:
      result = "MENetSessionPause";
      break;
    case 0x2539u:
      result = "MENetSessionStop";
      break;
    case 0x253Bu:
      result = "MENetSessionClose";
      break;
    case 0x253Cu:
      result = "MENetSessionLog";
      break;
    case 0x253Du:
      result = "MENetSessionEos";
      break;
    case 0x253Eu:
      result = "MENetSessionAnnounce";
      break;
    case 0x253Fu:
      result = "MENetSessionChangeProfile";
      break;
    case 0x2540u:
      result = "MENetSessionSetHDCPContext";
      break;
    case 0x2541u:
      result = "MENetSessionChangeSurfaceProtection";
      break;
    case 0x2549u:
      result = "MENetSessionIDRRequest";
      break;
    case 0x254Bu:
      result = "MENetMonitorConnectorTypeChanged";
      break;
    case 0x254Cu:
      result = "MENetSessionAudioMuted";
      break;
    case 0x254Du:
      result = "MEHDCPAuthorizationStatus";
      break;
    case 0x254Eu:
      result = "MEHDCPEncryptionPaused";
      break;
    case 0x254Fu:
      result = "MEHDCPEncryptionResumed";
      break;
    case 0x2550u:
      result = "MEHDCPReauthenticating";
      break;
    case 0x2551u:
      result = "MEHDCPType1StreamBlocked";
      break;
    case 0x2552u:
      result = "MEHDCPDownstreamTopologyChanged";
      break;
    default:
      return "unknown event";
  }
  return result;
}

```

## disassembly

```asm
0x180138c34  mov     eax, 13Ch
0x180138c39  cmp     ecx, eax
0x180138c3b  ja      loc_180139042
0x180138c41  jz      loc_18013903A
0x180138c47  mov     eax, 0CBh
0x180138c4c  cmp     ecx, eax
0x180138c4e  ja      loc_180138E53
0x180138c54  jz      loc_180138E4B
0x180138c5a  cmp     ecx, 72h ; 'r'
0x180138c5d  ja      loc_180138D57
0x180138c63  jz      loc_180138D4F
0x180138c69  cmp     ecx, 69h ; 'i'
0x180138c6c  ja      short loc_180138CE3
0x180138c6e  jz      short loc_180138CDB
0x180138c70  test    ecx, ecx
0x180138c72  jz      short loc_180138CD3
0x180138c74  sub     ecx, 1
0x180138c77  jz      short loc_180138CCB
0x180138c79  sub     ecx, 1
0x180138c7c  jz      short loc_180138CC3
0x180138c7e  sub     ecx, 1
0x180138c81  jz      short loc_180138CBB
0x180138c83  sub     ecx, 62h ; 'b'
0x180138c86  jz      short loc_180138CB3
0x180138c88  sub     ecx, 1
0x180138c8b  jz      short loc_180138CAB
0x180138c8d  sub     ecx, 1
0x180138c90  jz      short loc_180138CA3
0x180138c92  cmp     ecx, 1
0x180138c95  jnz     def_180139266; jumptable 0000000180139266 default case, cases 9513,9530,9538-9544,9546
0x180138c9b  lea     rax, aMesessionpause; "MESessionPaused"
0x180138ca2  retn
0x180138ca3  lea     rax, aMesessionstart; "MESessionStarted"
0x180138caa  retn
0x180138cab  lea     rax, aMesessiontopol; "MESessionTopologiesCleared"
0x180138cb2  retn
0x180138cb3  lea     rax, aMesessiontopol_0; "MESessionTopologySet"
0x180138cba  retn
0x180138cbb  lea     rax, aMenonfatalerro; "MENonFatalError"
0x180138cc2  retn
0x180138cc3  lea     rax, aMeextendedtype; "MEExtendedType"
0x180138cca  retn
0x180138ccb  lea     rax, aMeerror; "MEError"
0x180138cd2  retn
0x180138cd3  lea     rax, aMeunknown; "MEUnknown"
0x180138cda  retn
0x180138cdb  lea     rax, aMesessionstopp; "MESessionStopped"
0x180138ce2  retn
0x180138ce3  sub     ecx, 6Ah ; 'j'
0x180138ce6  jz      short loc_180138D47
0x180138ce8  sub     ecx, 1
0x180138ceb  jz      short loc_180138D3F
0x180138ced  sub     ecx, 1
0x180138cf0  jz      short loc_180138D37
0x180138cf2  sub     ecx, 1
0x180138cf5  jz      short loc_180138D2F
0x180138cf7  sub     ecx, 1
0x180138cfa  jz      short loc_180138D27
0x180138cfc  sub     ecx, 1
0x180138cff  jz      short loc_180138D1F
0x180138d01  sub     ecx, 1
0x180138d04  jz      short loc_180138D17
0x180138d06  cmp     ecx, 1
0x180138d09  jnz     def_180139266; jumptable 0000000180139266 default case, cases 9513,9530,9538-9544,9546
0x180138d0f  lea     rax, aMenewpresentat; "MENewPresentation"
0x180138d16  retn
0x180138d17  lea     rax, aMesessionnotif; "MESessionNotifyPresentationTime"
0x180138d1e  retn
0x180138d1f  lea     rax, aMesessiontopol_1; "MESessionTopologyStatus"
0x180138d26  retn
0x180138d27  lea     rax, aMesessioncapab; "MESessionCapabilitiesChanged"
0x180138d2e  retn
0x180138d2f  lea     rax, aMesessionscrub; "MESessionScrubSampleComplete"
0x180138d36  retn
0x180138d37  lea     rax, aMesessionratec; "MESessionRateChanged"
0x180138d3e  retn
0x180138d3f  lea     rax, aMesessionended; "MESessionEnded"
0x180138d46  retn
0x180138d47  lea     rax, aMesessionclose; "MESessionClosed"
0x180138d4e  retn
0x180138d4f  lea     rax, aMelicenseacqui_0; "MELicenseAcquisitionStart"
0x180138d56  retn
0x180138d57  mov     eax, 0C9h
0x180138d5c  cmp     ecx, eax
0x180138d5e  ja      loc_180138E32
0x180138d64  jz      loc_180138E2A
0x180138d6a  cmp     ecx, 7Ah ; 'z'
0x180138d6d  ja      short loc_180138DD8
0x180138d6f  jz      short loc_180138DD0
0x180138d71  sub     ecx, 73h ; 's'
0x180138d74  jz      short loc_180138DC8
0x180138d76  sub     ecx, 1
0x180138d79  jz      short loc_180138DC0
0x180138d7b  sub     ecx, 1
0x180138d7e  jz      short loc_180138DB8
0x180138d80  sub     ecx, 1
0x180138d83  jz      short loc_180138DB0
0x180138d85  sub     ecx, 1
0x180138d88  jz      short loc_180138DA8
0x180138d8a  sub     ecx, 1
0x180138d8d  jz      short loc_180138DA0
0x180138d8f  cmp     ecx, 1
0x180138d92  jnz     def_180139266; jumptable 0000000180139266 default case, cases 9513,9530,9538-9544,9546
0x180138d98  lea     rax, aMepolicyreport; "MEPolicyReport"
0x180138d9f  retn
0x180138da0  lea     rax, aMepolicyerror; "MEPolicyError"
0x180138da7  retn
0x180138da8  lea     rax, aMeenablercompl; "MEEnablerCompleted"
0x180138daf  retn
0x180138db0  lea     rax, aMeenablerprogr; "MEEnablerProgress"
0x180138db7  retn
0x180138db8  lea     rax, aMeindividualiz; "MEIndividualizationCompleted"
0x180138dbf  retn
0x180138dc0  lea     rax, aMeindividualiz_0; "MEIndividualizationStart"
0x180138dc7  retn
0x180138dc8  lea     rax, aMelicenseacqui; "MELicenseAcquisitionCompleted"
0x180138dcf  retn
0x180138dd0  lea     rax, aMebufferingsta; "MEBufferingStarted"
0x180138dd7  retn
0x180138dd8  sub     ecx, 7Bh ; '{'
0x180138ddb  jz      short loc_180138E22
0x180138ddd  sub     ecx, 1
0x180138de0  jz      short loc_180138E1A
0x180138de2  sub     ecx, 1
0x180138de5  jz      short loc_180138E12
0x180138de7  sub     ecx, 1
0x180138dea  jz      short loc_180138E0A
0x180138dec  sub     ecx, 1
0x180138def  jz      short loc_180138E02
0x180138df1  cmp     ecx, 2
0x180138df4  jnz     def_180139266; jumptable 0000000180139266 default case, cases 9513,9530,9538-9544,9546
0x180138dfa  lea     rax, aMesessionstrea; "MESessionStreamSinkFormatChanged"
0x180138e01  retn
0x180138e02  lea     rax, aMereconnectend; "MEReconnectEnd"
0x180138e09  retn
0x180138e0a  lea     rax, aMereconnectsta; "MEReconnectStart"
0x180138e11  retn
0x180138e12  lea     rax, aMeconnectend; "MEConnectEnd"
0x180138e19  retn
0x180138e1a  lea     rax, aMeconnectstart; "MEConnectStart"
0x180138e21  retn
0x180138e22  lea     rax, aMebufferingsto; "MEBufferingStopped"
0x180138e29  retn
0x180138e2a  lea     rax, aMesourcestarte; "MESourceStarted"
0x180138e31  retn
0x180138e32  cmp     ecx, 0CAh
0x180138e38  lea     rdx, aMestreamstarte; "MEStreamStarted"
0x180138e3f  lea     rax, aUnknownEvent; "unknown event"
0x180138e46  cmovz   rax, rdx
0x180138e4a  retn
0x180138e4b  lea     rax, aMesourceseeked; "MESourceSeeked"
0x180138e52  retn
0x180138e53  mov     eax, 12Dh
0x180138e58  cmp     ecx, eax
0x180138e5a  ja      loc_180138F70
0x180138e60  jz      loc_180138F68
0x180138e66  mov     eax, 0D5h
0x180138e6b  cmp     ecx, eax
0x180138e6d  ja      loc_180138EF9
0x180138e73  jz      short loc_180138EF1
0x180138e75  sub     ecx, 0CCh
0x180138e7b  jz      short loc_180138EE9
0x180138e7d  sub     ecx, 1
0x180138e80  jz      short loc_180138EE1
0x180138e82  sub     ecx, 1
0x180138e85  jz      short loc_180138ED9
0x180138e87  sub     ecx, 1
0x180138e8a  jz      short loc_180138ED1
0x180138e8c  sub     ecx, 1
0x180138e8f  jz      short loc_180138EC9
0x180138e91  sub     ecx, 1
0x180138e94  jz      short loc_180138EC1
0x180138e96  sub     ecx, 1
0x180138e99  jz      short loc_180138EB9
0x180138e9b  sub     ecx, 1
0x180138e9e  jz      short loc_180138EB1
0x180138ea0  cmp     ecx, 1
0x180138ea3  jnz     def_180139266; jumptable 0000000180139266 default case, cases 9513,9530,9538-9544,9546
0x180138ea9  lea     rax, aMeendofstream; "MEEndOfStream"
0x180138eb0  retn
0x180138eb1  lea     rax, aMeendofpresent_0; "MEEndOfPresentation"
0x180138eb8  retn
0x180138eb9  lea     rax, aMestreampaused; "MEStreamPaused"
0x180138ec0  retn
0x180138ec1  lea     rax, aMesourcepaused; "MESourcePaused"
0x180138ec8  retn
0x180138ec9  lea     rax, aMestreamstoppe; "MEStreamStopped"
0x180138ed0  retn
0x180138ed1  lea     rax, aMesourcestoppe; "MESourceStopped"
0x180138ed8  retn
0x180138ed9  lea     rax, aMeupdatedstrea; "MEUpdatedStream"
0x180138ee0  retn
0x180138ee1  lea     rax, aMenewstream; "MENewStream"
0x180138ee8  retn
0x180138ee9  lea     rax, aMestreamseeked; "MEStreamSeeked"
0x180138ef0  retn
0x180138ef1  lea     rax, aMemediasample; "MEMediaSample"
0x180138ef8  retn
0x180138ef9  sub     ecx, 0D6h
0x180138eff  jz      short loc_180138F60
0x180138f01  sub     ecx, 1
0x180138f04  jz      short loc_180138F58
0x180138f06  sub     ecx, 1
0x180138f09  jz      short loc_180138F50
0x180138f0b  sub     ecx, 1
0x180138f0e  jz      short loc_180138F48
0x180138f10  sub     ecx, 1
0x180138f13  jz      short loc_180138F40
0x180138f15  sub     ecx, 1
0x180138f18  jz      short loc_180138F38
0x180138f1a  sub     ecx, 1
0x180138f1d  jz      short loc_180138F30
0x180138f1f  cmp     ecx, 1
0x180138f22  jnz     def_180139266; jumptable 0000000180139266 default case, cases 9513,9530,9538-9544,9546
0x180138f28  lea     rax, aMesourcemetada; "MESourceMetadataChanged"
0x180138f2f  retn
0x180138f30  lea     rax, aMesourceratech_0; "MESourceRateChangeRequested"
0x180138f37  retn
0x180138f38  lea     rax, aMesourcecharac; "MESourceCharacteristicsChanged"
0x180138f3f  retn
0x180138f40  lea     rax, aMeendofpresent; "MEEndOfPresentationSegment"
0x180138f47  retn
0x180138f48  lea     rax, aMesourceratech; "MESourceRateChanged"
0x180138f4f  retn
0x180138f50  lea     rax, aMestreamformat; "MEStreamFormatChanged"
0x180138f57  retn
0x180138f58  lea     rax, aMestreamthinmo; "MEStreamThinMode"
0x180138f5f  retn
0x180138f60  lea     rax, aMestreamtick; "MEStreamTick"
0x180138f67  retn
0x180138f68  lea     rax, aMestreamsinkst_0; "MEStreamSinkStarted"
0x180138f6f  retn
0x180138f70  mov     eax, 135h
0x180138f75  cmp     ecx, eax
0x180138f77  ja      short loc_180138FE5
0x180138f79  jz      short loc_180138FDD
0x180138f7b  sub     ecx, 12Eh
0x180138f81  jz      short loc_180138FD5
0x180138f83  sub     ecx, 1
0x180138f86  jz      short loc_180138FCD
0x180138f88  sub     ecx, 1
0x180138f8b  jz      short loc_180138FC5
0x180138f8d  sub     ecx, 1
0x180138f90  jz      short loc_180138FBD
0x180138f92  sub     ecx, 1
0x180138f95  jz      short loc_180138FB5
0x180138f97  sub     ecx, 1
0x180138f9a  jz      short loc_180138FAD
0x180138f9c  cmp     ecx, 1
0x180138f9f  jnz     def_180139266; jumptable 0000000180139266 default case, cases 9513,9530,9538-9544,9546
0x180138fa5  lea     rax, aMestreamsinksc; "MEStreamSinkScrubSampleComplete"
0x180138fac  retn
0x180138fad  lea     rax, aMestreamsinkpr; "MEStreamSinkPrerolled"
0x180138fb4  retn
0x180138fb5  lea     rax, aMestreamsinkma; "MEStreamSinkMarker"
0x180138fbc  retn
0x180138fbd  lea     rax, aMestreamsinkre; "MEStreamSinkRequestSample"
0x180138fc4  retn
0x180138fc5  lea     rax, aMestreamsinkra; "MEStreamSinkRateChanged"
0x180138fcc  retn
0x180138fcd  lea     rax, aMestreamsinkpa; "MEStreamSinkPaused"
0x180138fd4  retn
0x180138fd5  lea     rax, aMestreamsinkst; "MEStreamSinkStopped"
0x180138fdc  retn
0x180138fdd  lea     rax, aMestreamsinkfo_0; "MEStreamSinkFormatChanged"
0x180138fe4  retn
0x180138fe5  sub     ecx, 136h
0x180138feb  jz      short loc_180139032
0x180138fed  sub     ecx, 1
0x180138ff0  jz      short loc_18013902A
0x180138ff2  sub     ecx, 1
0x180138ff5  jz      short loc_180139022
0x180138ff7  sub     ecx, 1
0x180138ffa  jz      short loc_18013901A
0x180138ffc  sub     ecx, 1
0x180138fff  jz      short loc_180139012
0x180139001  cmp     ecx, 1
0x180139004  jnz     def_180139266; jumptable 0000000180139266 default case, cases 9513,9530,9538-9544,9546
0x18013900a  lea     rax, aMeaudiosession_1; "MEAudioSessionDeviceRemoved"
0x180139011  retn
0x180139012  lea     rax, aMeaudiosession; "MEAudioSessionVolumeChanged"
0x180139019  retn
0x18013901a  lea     rax, aMeaudiosession_4; "MEAudioSessionNameChanged"
0x180139021  retn
0x180139022  lea     rax, aMesinkinvalida; "MESinkInvalidated"
0x180139029  retn
0x18013902a  lea     rax, aMequalitynotif; "MEQualityNotify"
0x180139031  retn
0x180139032  lea     rax, aMestreamsinkde; "MEStreamSinkDeviceChanged"
0x180139039  retn
0x18013903a  lea     rax, aMeaudiosession_3; "MEAudioSessionServerShutdown"
0x180139041  retn
0x180139042  mov     eax, 2527h
0x180139047  cmp     ecx, eax
0x180139049  ja      loc_180139246
0x18013904f  jz      loc_18013923E
0x180139055  mov     eax, 25Bh
0x18013905a  cmp     ecx, eax
0x18013905c  ja      loc_180139154
0x180139062  jz      loc_18013914C
  ... truncated ...
```
