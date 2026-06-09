# ReadLanmanWorkStationParameters

- ea: `0x140028fec`
- end: `0x14002a8f5`
- name: `ReadLanmanWorkStationParameters`
- size: `6409`
- prototype: ``
- caller_count: `2`
- callee_count: `25`
- tags: `reparse_path, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x14008fb70`
- `0x1400926ac`

## callees

- `0x140003480`
- `0x14001c5f0`
- `0x140023330`
- `0x1400253b0`
- `0x140026978`
- `0x14002834c`
- `0x140028fec`
- `0x14002b24c`
- `0x1400377dc`
- `0x14003838c`
- `0x14003b6b8`
- `0x14003b728`
- `0x14003b788`
- `0x14003ba3c`
- `0x14004274c`
- `0x140042c14`
- `0x14004cb90`
- `0x140059dc0`
- `0x140090470`
- `0x140091d40`
- `0x140092810`
- `0x140092970`
- `0x140093050`
- `0x140093650`
- `0x140093acc`

## import_xrefs

- `ntoskrnl!ZwQueryLicenseValue` at `0x14002a653`
- `ntoskrnl!ZwQueryLicenseValue` at `0x14002a7ac`
- `ntoskrnl!ZwQueryLicenseValue` at `0x14002a653`
- `ntoskrnl!ZwQueryLicenseValue` at `0x14002a7ac`
- `ntoskrnl!ObfDereferenceObject` at `0x14002a275`
- `ntoskrnl!ObfDereferenceObject` at `0x14002a275`
- `ntoskrnl!ZwOpenKey` at `0x140029111`
- `ntoskrnl!ZwOpenKey` at `0x140029111`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002a628`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002a781`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002a628`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002a781`
- `ntoskrnl!ZwClose` at `0x14002a5cf`
- `ntoskrnl!ZwClose` at `0x14002a5cf`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14002a3f4`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14002a3f4`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14002a32a`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14002a32a`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14002a262`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14002a262`
- `rdbss!RxFindRegisteredMiniRedirByName` at `0x14002a21c`
- `rdbss!RxFindRegisteredMiniRedirByName` at `0x14002a21c`

## string_xrefs

- `0x14002a336`: `\Registry\Machine\Software\Policies\Microsoft\Windows\LanmanWorkstation`
- `0x140029049`: `\Registry\Machine\System\CurrentControlSet\Services\LanmanWorkStation\Parameters`
- `0x14002a7de`: `\Registry\Machine\System\CurrentControlSet\Services\LanmanWorkStation\Parameters`
- `0x14002a861`: `\Registry\Machine\System\CurrentControlSet\Services\LanmanWorkStation\Parameters`
- `0x1400293cf`: `EnableCompressedTraffic`
- `0x14002941c`: `DisableCompression`
- `0x14002914c`: `SmbMaxChainedWriteRequests`
- `0x14002917e`: `SmbMaxChainedWriteBytes`
- `0x1400291b0`: `DisableChainedWritesOverNetwork`
- `0x1400291d6`: `SmbDirectDataPlacementSecurity`
- `0x14002925c`: `InvalidAuthenticationCacheLifetime`
- `0x1400292c3`: `DisableDirCacheOnDiskIdOptimization`
- `0x1400292f0`: `BypassFetchNetworkOpenInfoFullStateMachine`
- `0x14002936c`: `RequireSecuritySignature`
- `0x14002949e`: `AsyncCompressionThreshold`
- `0x1400294c3`: `EnableCompressibilitySampling`
- `0x14002950a`: `CompressibilitySamplingSize`
- `0x14002954e`: `CompressibleThreshold`
- `0x140029604`: `MaxNumOfExchangesForPipelineReadWrite`
- `0x140029628`: `EnableCachingOnWriteOnlyOpens`
- `0x14002964c`: `DisableByteRangeLockingOnReadOnlyFiles`
- `0x140029670`: `FileInfoCacheLifetime`
- `0x1400296b3`: `FileNotFoundCacheLifetime`
- `0x1400296cb`: `DirectoryCacheLifetime`
- `0x140029813`: `FileInfoCacheEntriesMax`
- `0x14002985d`: `DirectoryCacheEntriesMax`
- `0x1400298ac`: `FileNotFoundCacheEntriesMax`
- `0x1400298fb`: `DirectoryCacheEntrySizeMax`
- `0x140029b5f`: `ReadAheadGranularity`
- `0x140029b96`: `RdmaReadThreshold`
- `0x140029bab`: `RdmaWriteThreshold`
- `0x140029c30`: `DormantDirectoryTimeout`
- `0x140029cc9`: `AuditSmb1Access`
- `0x14002a13c`: `EnableRestartForBatchedWrites`
- `0x14002a28b`: `IgnoreWitnessShareMoveNotifications`
- `0x14002a40a`: `VolumeFeatureSupportCacheLifetime`
- `0x14002a420`: `VolumeFeatureSupportCacheEntriesMax`
- `0x14002a478`: `FileAbeStatusCacheLifetime`

## pseudocode

```c
int __fastcall ReadLanmanWorkStationParameters(__int16 a1)
{
  unsigned __int64 v2; // rax
  char v3; // si
  char v4; // r14
  int v5; // r8d
  int v6; // ecx
  int UlongRegistryParameter; // eax
  char v8; // dl
  __int64 v9; // rax
  int v10; // eax
  int v11; // ecx
  int v12; // eax
  int v13; // ecx
  int v14; // eax
  int v15; // ecx
  __int64 v16; // rax
  __int64 v17; // rax
  int v18; // r12d
  int v19; // r13d
  int v20; // eax
  int v21; // ecx
  int v22; // eax
  char v23; // dl
  int v24; // eax
  int v25; // ecx
  bool v26; // sf
  unsigned int v27; // ecx
  int v28; // esi
  int v29; // eax
  char v30; // dl
  int v31; // edi
  int v32; // eax
  int v33; // ecx
  int v34; // eax
  int v35; // ecx
  int v36; // eax
  int v37; // ecx
  int v38; // r8d
  __int16 v39; // cx
  int v40; // r8d
  __int16 v41; // cx
  int v42; // eax
  char v43; // dl
  unsigned int v44; // eax
  int v45; // eax
  char v46; // dl
  bool v47; // di
  char v48; // r14
  int v49; // eax
  char v50; // dl
  char v51; // al
  int v52; // eax
  int v53; // ecx
  int v54; // eax
  int v55; // ecx
  int v56; // eax
  char v57; // dl
  int v58; // eax
  char v59; // dl
  int v60; // eax
  char v61; // dl
  int v62; // eax
  char v63; // dl
  int v64; // eax
  char v65; // dl
  int v66; // eax
  char v67; // dl
  __int64 v68; // rcx
  __int64 RegisteredMiniRedirByName; // rax
  __int64 v70; // rdi
  KIRQL v71; // al
  __int64 v72; // rdx
  int v73; // eax
  char v74; // dl
  int v75; // eax
  char v76; // dl
  int v77; // eax
  char v78; // dl
  int v79; // eax
  char v80; // dl
  int CipherSuiteOrderPolicySetting; // eax
  unsigned int v82; // edi
  int v83; // eax
  int v84; // ecx
  int v85; // eax
  int v86; // eax
  char v87; // dl
  int v88; // eax
  char v89; // dl
  unsigned __int64 v90; // rdx
  int MultiSZList; // edi
  _QWORD *v92; // rbx
  int TargetServerExceptionList; // edi
  _QWORD *v94; // rbx
  unsigned int v96; // [rsp+30h] [rbp-2E8h] BYREF
  void *KeyHandle; // [rsp+38h] [rbp-2E0h] BYREF
  char v98; // [rsp+40h] [rbp-2D8h]
  char v99; // [rsp+41h] [rbp-2D7h]
  unsigned __int64 v100; // [rsp+48h] [rbp-2D0h] BYREF
  int v101; // [rsp+50h] [rbp-2C8h] BYREF
  _QWORD *v102; // [rsp+58h] [rbp-2C0h] BYREF
  __int64 v103; // [rsp+60h] [rbp-2B8h] BYREF
  char *v104; // [rsp+68h] [rbp-2B0h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+70h] [rbp-2A8h] BYREF
  UNICODE_STRING DestinationString; // [rsp+A0h] [rbp-278h] BYREF
  char v107; // [rsp+C0h] [rbp-258h] BYREF

  v103 = 34209792;
  KeyHandle = 0;
  v96 = 0;
  v104 = &v107;
  v100 = 0;
  v102 = 0;
  memset(&ObjectAttributes, 0, 44);
  LODWORD(v2) = MRxSmbInitRedirectedPath(
                  L"LanmanWorkStationParameters",
                  L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\LanmanWorkStation\\Parameters",
                  &v103);
  if ( (v2 & 0x80000000) != 0LL )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      LODWORD(v2) = WPP_SF_d(
                      WPP_GLOBAL_Control->AttachedDevice,
                      42,
                      WPP_4ff68d8e9b0a3e70c0197c268f5ae5e8_Traceguids,
                      (unsigned int)v2);
    }
    return v2;
  }
  v98 = 0;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)&v103;
  v99 = 0;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v3 = 0;
  ObjectAttributes.Attributes = 576;
  v4 = 0;
  LODWORD(v2) = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
  if ( (v2 & 0x80000000) != 0LL )
  {
    v18 = a1 & 1;
  }
  else
  {
    MRxSmbEvaluateRegistryRoutingParameters(KeyHandle);
    MRxSmbRemoveDeprecatedRegistryParameters(KeyHandle);
    if ( (int)MRxSmbGetUlongRegistryParameter(KeyHandle) >= 0 )
      dword_14007D224 = v96;
    if ( (int)MRxSmbGetUlongRegistryParameter(KeyHandle) >= 0 )
      dword_14007D228 = v96;
    if ( (int)MRxSmbGetUlongRegistryParameter(KeyHandle) >= 0 )
      byte_14007D22C = v96 != 0;
    if ( (int)MRxSmbGetUlongRegistryParameter(KeyHandle) < 0 )
    {
      dword_14007D220 = 1;
    }
    else
    {
      v6 = v96;
      if ( dword_14007D220 != v96 )
      {
        if ( (byte_1400712A4 & 4) != 0 )
        {
          McTemplateK0qq_EtwWriteTransfer(v96);
          v6 = v96;
        }
        dword_14007D220 = v6;
      }
    }
    UlongRegistryParameter = MRxSmbGetUlongRegistryParameter(KeyHandle);
    v8 = 0;
    if ( UlongRegistryParameter >= 0 )
      v8 = v96;
    byte_14007D230 = v8;
    if ( (int)MRxSmbGetUlongRegistryParameter(KeyHandle) < 0 )
      v9 = 30 * SmbCeTicksPerSecond;
    else
      v9 = SmbCeTicksPerSecond * v96;
    qword_14007D238 = v9;
    if ( (int)MRxSmbGetUlongRegistryParameter(KeyHandle) >= 0 )
      LOBYTE(word_14007D22D) = v96 != 0;
    if ( (int)MRxSmbGetUlongRegistryParameter(KeyHandle) >= 0 )
      HIBYTE(word_14007D22D) = v96 != 0;
    if ( (int)MRxSmbGetUlongRegistryParameter(KeyHandle) >= 0 )
      byte_14007D20C = v96 != 0;
    if ( (a1 & 0x40) == 0 && (int)MRxSmbGetUlongRegistryParameter(KeyHandle) >= 0 )
      byte_14007D13D = v96 != 0;
    if ( (int)MRxSmbGetUlongRegistryParameter(KeyHandle) >= 0 )
    {
      v99 = 1;
      byte_14007D13C = v96 != 0;
    }
    if ( (a1 & 0x20) == 0 )
    {
      if ( (int)MRxSmbGetUlongRegistryParameter(KeyHandle) >= 0 )
        byte_14007D244 = 1;
      byte_14007D244 = 0;
    }
    if ( (a1 & 2) == 0 && (int)MRxSmbGetUlongRegistryParameter(KeyHandle) >= 0 )
      word_14007D1CA &= ~1u;
    if ( (a1 & 4) == 0 && (int)MRxSmbGetUlongRegistryParameter(KeyHandle) >= 0 )
      word_14007D1CA &= ~2u;
    v10 = MRxSmbGetUlongRegistryParameter(KeyHandle);
    v11 = 0x10000;
    if ( v10 >= 0 )
      v11 = v96;
    dword_14007D0A4 = v11;
    v12 = MRxSmbGetUlongRegistryParameter(KeyHandle);
    v13 = 0x10000;
    if ( v12 >= 0 )
      v13 = v96;
    dword_14007D0A8 = v13;
    v14 = MRxSmbGetUlongRegistryParameter(KeyHandle);
    v15 = 0x10000;
    if ( v14 >= 0 )
      v15 = v96;
    dword_14007D0AC = v15;
    MRxSmbGetUlongRegistryParameter(KeyHandle);
    word_14007D1CA &= ~4u;
    if ( (int)MRxSmbGetUlonglongRegistryParameter2(KeyHandle) < 0 )
    {
      qword_14007D0B0 = 524288000;
    }
    else
    {
      v16 = v100;
      if ( v100 > 0x20000000000000LL )
        v16 = 0x20000000000000LL;
      qword_14007D0B0 = v16;
    }
    if ( (int)MRxSmbGetUlonglongRegistryParameter2(KeyHandle) < 0 )
    {
      qword_14007D0B8 = 104857600;
    }
    else
    {
      v17 = v100;
      if ( v100 > 0x20000000000000LL )
        v17 = 0x20000000000000LL;
      qword_14007D0B8 = v17;
    }
    v18 = a1 & 1;
    if ( (a1 & 1) == 0 && (int)MRxSmbGetUlongRegistryParameter(KeyHandle) >= 0 )
    {
      v98 = 1;
      byte_14007D164 = v96 != 0;
    }
    if ( (int)MRxSmbGetUlongRegistryParameter(KeyHandle) >= 0 )
      byte_14007D165 = v96 != 0;
    if ( (int)MRxSmbGetUlongRegistryParameter(KeyHandle) >= 0 )
      ExtendedSessTimeoutInterval = v96;
    if ( (int)MRxSmbGetUlongRegistryParameter(KeyHandle) >= 0 )
      MaxNumOfExchangesForPipelineReadWrite = v96;
    if ( (int)MRxSmbGetUlongRegistryParameter(KeyHandle) >= 0 )
      MRxSmbEnableCachingOnWriteOnlyOpens = v96;
    if ( (int)MRxSmbGetUlongRegistryParameter(KeyHandle) >= 0 )
      DisableByteRangeLockingOnReadOnlyFiles = v96;
    v19 = 10;
    if ( (int)MRxSmbGetUlongRegistryParameter(KeyHandle) < 0 )
    {
      dword_14007D110 = 10;
      byte_14007D168 = 1;
    }
    else
    {
      dword_14007D110 = v96;
      byte_14007D168 = 0;
    }
    v20 = MRxSmbGetUlongRegistryParameter(KeyHandle);
    v21 = 5;
    if ( v20 >= 0 )
      v21 = v96;
    dword_14007D114 = v21;
    if ( (int)MRxSmbGetUlongRegistryParameter(KeyHandle) < 0 )
    {
      dword_14007D118 = 10;
      byte_14007D167 = 1;
    }
    else
    {
      dword_14007D118 = v96;
      byte_14007D167 = 0;
    }
    if ( (int)MRxSmbGetUlongRegistryParameter(KeyHandle) < 0 )
      byte_14007D0C0 &= ~2u;
    else
      byte_14007D0C0 = byte_14007D0C0 & 0xFD | (2 * (v96 & 1));
    if ( (int)MRxSmbGetUlongRegistryParameter(KeyHandle) < 0 )
      byte_14007D0C0 &= ~4u;
    else
      byte_14007D0C0 = byte_14007D0C0 & 0xFB | (4 * (v96 & 1));
    v22 = MRxSmbGetUlongRegistryParameter(KeyHandle);
    v23 = 0;
    if ( v22 >= 0 )
      v23 = v96;
    byte_14007D169 = v23;
    v24 = MRxSmbGetUlongRegistryParameter(KeyHandle);
    v25 = 0;
    if ( v24 >= 0 )
      v25 = v96;
    dword_14007D090 = v25;
    v26 = (int)MRxSmbGetUlongRegistryParameter(KeyHandle) < 0;
    v27 = 1000;
    if ( !v26 )
      v27 = v96;
    dword_14007D094 = v27;
    if ( dword_14007D090 > v27 )
      dword_14007D094 = dword_14007D090;
    if ( (int)MRxSmbGetUlongRegistryParameter(KeyHandle) < 0 )
      dword_14007D11C = 1024;
    else
      dword_14007D11C = 1;
    v28 = 4096;
    if ( (int)MRxSmbGetUlongRegistryParameter(KeyHandle) < 0 )
      dword_14007D124 = 32;
    else
      dword_14007D124 = 1;
    if ( (int)MRxSmbGetUlongRegistryParameter(KeyHandle) < 0 )
      dword_14007D120 = 128;
    else
      dword_14007D120 = 1;
    if ( (int)MRxSmbGetUlongRegistryParameter(KeyHandle) < 0 )
      dword_14007D128 = 0;
    else
      dword_14007D128 = 0x10000;
    v29 = MRxSmbGetUlongRegistryParameter(KeyHandle);
    v30 = 0;
    if ( v29 >= 0 )
      v30 = v96;
    byte_14007D16A = v30;
    if ( (int)MRxSmbGetUlongRegistryParameter(KeyHandle) < 0 )
      dword_14007D098 = (unsigned int)IsServerSKU() != 0 ? 1 : 8;
    else
      dword_14007D098 = v96;
    MRxSmbGetUlongRegistryParameter(KeyHandle);
    dword_14007D140 = 1;
    if ( (int)MRxSmbGetUlongRegistryParameter(KeyHandle) < 0 )
      dword_14007D144 = 4;
    else
      dword_14007D144 = 1;
    if ( (int)MRxSmbGetUlongRegistryParameter(KeyHandle) < 0 )
      dword_14007D148 = 2;
    else
      dword_14007D148 = 1;
    if ( (int)MRxSmbGetUlongRegistryParameter(KeyHandle) < 0 )
      dword_14007D150 = 32;
    else
      dword_14007D150 = 1;
    if ( (int)MRxSmbGetUlongRegistryParameter(KeyHandle) < 0 )
      dword_14007D14C = 2;
    else
      dword_14007D14C = 1;
    v31 = 600;
    if ( (int)MRxSmbGetUlongRegistryParameter(KeyHandle) < 0 )
      dword_14007D154 = 600;
    else
      dword_14007D154 = 1;
    if ( (int)MRxSmbGetUlongRegistryParameter(KeyHandle) < 0 )
      dword_14007D12C = 0;
    else
      dword_14007D12C = v96;
    v32 = MRxSmbGetUlongRegistryParameter(KeyHandle);
    v33 = 4096;
    if ( v32 >= 0 )
      v33 = v96;
    MRxSmbConfiguration = v33;
    v34 = MRxSmbGetUlongRegistryParameter(KeyHandle);
    v35 = 4097;
    if ( v34 >= 0 )
      v35 = v96;
    dword_14007D084 = v35;
    if ( (int)MRxSmbGetUlongRegistryParameter(KeyHandle) < 0 )
      dword_14007D088 = 7168;
    else
      dword_14007D088 = 1024;
    if ( (int)MRxSmbGetUlongRegistryParameter(KeyHandle) >= 0 )
      v31 = v96;
    dword_14007D104 = v31;
    if ( (int)MRxSmbGetUlongRegistryParameter(KeyHandle) < 0 )
      dword_14007D0A0 = 50;
    else
      dword_14007D0A0 = v96;
    if ( (int)MRxSmbGetUlongRegistryParameter(KeyHandle) < 0 )
      byte_14007D0C0 &= ~8u;
    else
      byte_14007D0C0 = byte_14007D0C0 & 0xF7 | (8 * (v96 & 1));
    if ( (int)MRxSmbGetUlongRegistryParameter(KeyHandle) < 0 )
      byte_14007D0C0 |= 0x10u;
    else
      byte_14007D0C0 = byte_14007D0C0 & 0xEF | (16 * (v96 & 1));
    v36 = MRxSmbGetUlongRegistryParameter(KeyHandle);
    v37 = 20;
    if ( v36 >= 0 )
      v37 = v96;
    dword_14007D158 = v37;
    if ( (a1 & 8) == 0 )
    {
      if ( (int)MRxSmbGetUlongRegistryParameter(KeyHandle) < 0 )
      {
        word_14007D15C = -1;
      }
      else
      {
        v39 = v96;
        if ( word_14007D15C != (_WORD)v96 )
        {
          if ( (byte_1400712A3 & 8) != 0 )
          {
            McTemplateK0zdd_EtwWriteTransfer(
              v96,
              (unsigned __int16)word_14007D15C,
              v38,
              (unsigned int)L"MaxSmb2Dialect",
              word_14007D15C,
              v96);
            v39 = v96;
          }
          word_14007D15C = v39;
        }
      }
    }
    if ( (a1 & 0x10) == 0 )
    {
      if ( (int)MRxSmbGetUlongRegistryParameter(KeyHandle) < 0 )
      {
        word_14007D15E = 0;
      }
      else
      {
        v41 = v96;
        if ( word_14007D15E != (_WORD)v96 )
        {
          if ( (byte_1400712A3 & 8) != 0 )
          {
            McTemplateK0zdd_EtwWriteTransfer(
              v96,
              (unsigned __int16)word_14007D15E,
              v40,
              (unsigned int)L"MinSmb2Dialect",
              word_14007D15E,
              v96);
            v41 = v96;
          }
          word_14007D15E = v41;
        }
      }
    }
    if ( (a1 & 0x1000) == 0 )
      byte_14007D260 = (int)MRxSmbGetUlongRegistryParameter(KeyHandle) < 0;
    v42 = MRxSmbGetUlongRegistryParameter(KeyHandle);
    v43 = 0;
    if ( v42 >= 0 )
      v43 = v96;
    byte_14007D16B = v43;
    if ( (int)MRxSmbGetUlongRegistryParameter(KeyHandle) < 0 )
      dword_14007D174 = 16;
    else
      dword_14007D174 = 8;
    if ( (int)MRxSmbGetUlongRegistryParameter(KeyHandle) < 0 )
      v44 = 180 * dword_14007D174;
    else
      v44 = dword_14007D174 * v96;
    dword_14007D170 = v44 >> 3;
    v45 = MRxSmbGetUlongRegistryParameter(KeyHandle);
    v46 = 0;
    if ( v45 >= 0 )
      v46 = v96;
    byte_14007D16C = v46;
    v47 = (int)MRxSmbGetUlongRegistryParameter(KeyHandle) < 0 || v96 != 0;
    v48 = word_14007D202;
    LOBYTE(word_14007D202) = v47;
    v49 = MRxSmbGetUlongRegistryParameter(KeyHandle);
    v50 = 0;
    if ( v49 >= 0 )
      v50 = v96;
    v51 = HIBYTE(word_14007D202);
    HIBYTE(word_14007D202) = v50;
    if ( v50 != v51 || v47 != v48 )
    {
      if ( v47 )
        VctRecomputeAllMultichannelConnectionInfo();
      else
        VctDisconnectRdmaConnections();
    }
    if ( (int)MRxSmbGetUlongRegistryParameter(KeyHandle) < 0 )
      dword_14007D160 = 0;
    else
      dword_14007D160 = (v96 + 7) >> 3;
    if ( (int)MRxSmbGetUlongRegistryParameter(KeyHandle) < 0 )
      dword_14007D204 = 0;
    else
      dword_14007D204 = v96;
    v52 = MRxSmbGetUlongRegistryParameter(KeyHandle);
    v53 = 0;
    if ( v52 >= 0 )
      v53 = v96;
    dword_14007D208 = v53;
    v54 = MRxSmbGetUlongRegistryParameter(KeyHandle);
    v55 = 0;
    if ( v54 >= 0 )
      v55 = v96;
    dword_14007D210 = v55;
    if ( (int)MRxSmbGetUlongRegistryParameter(KeyHandle) < 0 )
      dword_14007D214 = 443;
    else
      dword_14007D214 = v96;
    if ( (int)MRxSmbGetUlongRegistryParameter(KeyHandle) < 0 )
      dword_14007D218 = 445;
    else
      dword_14007D218 = v96;
    if ( (int)MRxSmbGetUlongRegistryParameter(KeyHandle) < 0 )
      dword_14007D21C = 445;
    else
      dword_14007D21C = v96;
    if ( (a1 & 0x80u) == 0 )
    {
      v56 = MRxSmbGetUlongRegistryParameter(KeyHandle);
      v57 = 1;
      if ( v56 >= 0 )
        v57 = v96;
      byte_14007D25B = v57;
    }
    v58 = MRxSmbGetUlongRegistryParameter(KeyHandle);
    v59 = 0;
    if ( v58 >= 0 )
      v59 = v96;
    byte_14007D27B = v59;
    v60 = MRxSmbGetUlongRegistryParameter(KeyHandle);
    v61 = 0;
    if ( v60 >= 0 )
      v61 = v96;
    byte_14007D27C = v61;
    v62 = MRxSmbGetUlongRegistryParameter(KeyHandle);
    v63 = 1;
    if ( v62 >= 0 )
      v63 = v96;
    byte_14007D27D = v63;
    v64 = MRxSmbGetUlongRegistryParameter(KeyHandle);
    v65 = 1;
    if ( v64 >= 0 )
      v65 = v96;
    byte_14007D27F = v65;
    v66 = MRxSmbGetUlongRegistryParameter(KeyHandle);
    v67 = 0;
    if ( v66 >= 0 )
      v67 = v96;
    byte_14007D27E = v67;
    if ( (int)MRxSmbGetUlongRegistryParameter(KeyHandle) < 0 )
    {
      dword_14007D280 = 30;
    }
    else
    {
      v68 = v96;
      dword_14007D280 = 0;
    }
    Feature_SMB_Use_RDMA_As_Primary_Connection__private_IsEnabledPreCheck(v68, 30);
    if ( (int)MRxSmbGetUlongRegistryParameter(KeyHandle) >= 0 )
    {
      RegisteredMiniRedirByName = RxFindRegisteredMiniRedirByName(&qword_140061B98);
      v70 = RegisteredMiniRedirByName;
      if ( RegisteredMiniRedirByName )
      {
        v71 = SmbCeAcquireSpinLock(RegisteredMiniRedirByName);
        v72 = *(_QWORD *)(v70 + 2360);
        if ( v72 )
          *(_BYTE *)(v72 + 56) = v96 != 0;
        *(_DWORD *)(v70 + 2352) = -1;
        ExReleaseSpinLockExclusive((PEX_SPIN_LOCK)(v70 + 1920), v71);
        ObfDereferenceObject(*(PVOID *)(v70 + 344));
      }
    }
    v73 = MRxSmbGetUlongRegistryParameter(KeyHandle);
    v74 = 0;
    if ( v73 >= 0 )
      v74 = v96;
    byte_14007D27A = v74;
    v75 = MRxSmbGetUlongRegistryParameter(KeyHandle);
    v76 = 1;
    if ( v75 >= 0 )
      v76 = v96;
    byte_14007D25F = v76;
    v77 = MRxSmbGetUlongRegistryParameter(KeyHandle);
    v78 = 0;
    if ( v77 >= 0 )
      v78 = v96;
    byte_14007D22F = v78;
    v79 = MRxSmbGetUlongRegistryParameter(KeyHandle);
    v80 = 1;
    if ( v79 >= 0 )
      v80 = v96;
    byte_14007D241 = v80;
    ExAcquirePushLockExclusiveEx(&MRxSmbCipherSuiteOrderPushLock, 0);
    if ( (unsigned int)SmbCryptoIsCipherSuiteOrderPresentPolicySetting(L"\\Registry\\Machine\\Software\\Policies\\Microsoft\\Windows\\LanmanWorkstation") == -1073741772 )
    {
      CipherSuiteOrderPolicySetting = SmbCryptoReadCipherSuiteOrderPolicySetting(
                                        v104,
                                        &dword_14007D19C,
                                        &word_14007D1AC);
      v82 = CipherSuiteOrderPolicySetting;
      if ( CipherSuiteOrderPolicySetting < 0 )
      {
        if ( CipherSuiteOrderPolicySetting == -1073739509 && (byte_1400712A3 & 0x10) != 0 )
          McTemplateK0z_EtwWriteTransfer();
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 43, WPP_4ff68d8e9b0a3e70c0197c268f5ae5e8_Traceguids, v82);
        }
        dword_14007D19C = 2;
        word_14007D1AC = 4;
        dword_14007D1A4 = 4;
        dword_14007D1A0 = 1;
        dword_14007D1A8 = 3;
      }
    }
    ExReleasePushLockExclusiveEx(&MRxSmbCipherSuiteOrderPushLock, 0);
    v83 = MRxSmbGetUlongRegistryParameter(KeyHandle);
    v84 = 10;
    if ( v83 >= 0 )
      v84 = v96;
    dword_14007D130 = v84;
    if ( (int)MRxSmbGetUlongRegistryParameter(KeyHandle) < 0 )
    {
      dword_14007D134 = 32;
    }
    else
    {
      v85 = 4096;
      if ( v96 < 0x1000 )
        v85 = v96;
      if ( v85 )
      {
        if ( v96 < 0x1000 )
          v28 = v96;
        dword_14007D134 = v28;
      }
      else
      {
        dword_14007D134 = 1;
      }
    }
    if ( (int)MRxSmbGetUlongRegistryParameter(KeyHandle) >= 0 )
      v19 = v96;
    dword_14007D138 = v19;
    v86 = MRxSmbGetUlongRegistryParameter(KeyHandle);
    v87 = 1;
    if ( v86 >= 0 )
      v87 = v96;
    byte_14007D25A = v87;
    if ( (int)MRxSmbGetUlongRegistryParameter(KeyHandle) < 0 || (byte_14007D242 = 1, !v96) )
      byte_14007D242 = 0;
    if ( (int)MRxSmbGetUlongRegistryParameter(KeyHandle) < 0 || (byte_14007D243 = 0, v96) )
      byte_14007D243 = 1;
    if ( (a1 & 0x100) == 0 && (int)MRxSmbGetUlongRegistryParameter(KeyHandle) >= 0 )
      byte_14007D25C = v96 != 0;
    if ( (a1 & 0x200) == 0 && (int)MRxSmbGetUlongRegistryParameter(KeyHandle) >= 0 )
      byte_14007D25D = v96 != 0;
    if ( (a1 & 0x400) == 0 && (int)MRxSmbGetUlongRegistryParameter(KeyHandle) >= 0 )
      byte_14007D25E = v96 != 0;
    v88 = MRxSmbGetUlongRegistryParameter(KeyHandle);
    v89 = 0;
    if ( v88 >= 0 )
      v89 = v96;
    byte_14007D284 = v89;
    LODWORD(v2) = ZwClose(KeyHandle);
    v3 = v98;
    v4 = v99;
  }
  if ( !v18 && !v3 )
  {
    LODWORD(v100) = 0;
    v101 = 0;
    DestinationString = 0;
    RtlInitUnicodeString(&DestinationString, L"SMBClient-AllowInsecureGuestAuthByDefault");
    LODWORD(v2) = ZwQueryLicenseValue(&DestinationString, &v100, &v96, 4, &v101);
    if ( (v2 & 0x80000000) == 0LL )
    {
      if ( v96 )
      {
        byte_14007D164 = 1;
        goto LABEL_289;
      }
      byte_14007D164 = 0;
      goto LABEL_299;
    }
    byte_14007D164 = 1;
  }
  if ( byte_14007D164 )
  {
LABEL_289:
    v2 = _InterlockedCompareExchange64(&MRxSmbInsecureGuestAuthEnabledEventThrottle, 0, 0);
    while ( !v2 || v2 < MEMORY[0xFFFFF78000000320] && MEMORY[0xFFFFF78000000320] - v2 >= qword_140071298 )
    {
      v90 = v2;
      v2 = _InterlockedCompareExchange64(&MRxSmbInsecureGuestAuthEnabledEventThrottle, MEMORY[0xFFFFF78000000320], v2);
      if ( v2 == v90 )
      {
        if ( byte_1400712A3 < 0 )
          McTemplateK0zq_EtwWriteTransfer(
            MEMORY[0xFFFFF78000000320],
            (unsigned int)InsecureGuestAuthEnabled,
            v5,
            (unsigned int)L"AllowInsecureGuestAuth",
            byte_14007D164);
        LODWORD(v2) = dword_1400700C0;
        if ( (unsigned int)dword_1400700C0 > 5 )
        {
          LODWORD(v2) = tlgKeywordOn(&dword_1400700C0, 0x400000000000LL);
          if ( (_BYTE)v2 )
            LODWORD(v2) = tlgWriteTransfer_EtwWriteTransfer(
                            &dword_1400700C0,
                            byte_140067A91,
                            0,
                            0,
                            2,
                            &DestinationString);
        }
        break;
      }
    }
  }
LABEL_299:
  if ( !v4 )
  {
    v101 = 0;
    LODWORD(v100) = 0;
    DestinationString = 0;
    RtlInitUnicodeString(&DestinationString, L"SMBClient-RequireSigningByDefault");
    LODWORD(v2) = ZwQueryLicenseValue(&DestinationString, &v101, &v96, 4, &v100);
    if ( (v2 & 0x80000000) != 0LL || (byte_14007D13C = 1, !v96) )
      byte_14007D13C = 0;
  }
  if ( (a1 & 0x800) == 0 )
  {
    MultiSZList = RfsRegGetMultiSZList(
                    &v102,
                    L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\LanmanWorkStation\\Parameters",
                    L"BlockNTLMServerExceptionList");
    if ( MultiSZList < 0 )
      goto LABEL_310;
    v92 = v102;
    if ( !v102 )
      goto LABEL_310;
    if ( *v102 )
      MultiSZList = ReadTargetServerExceptionList(v102, &qword_14007D250, byte_14007D258, &qword_14007D248);
    LODWORD(v2) = RfsRegFreeMemory(v92);
    if ( MultiSZList < 0 || !v92 )
LABEL_310:
      LODWORD(v2) = ClearTargetServerExceptionList(&qword_14007D250, byte_14007D258, &qword_14007D248);
    v102 = 0;
  }
  if ( (a1 & 0x2000) == 0 )
  {
    TargetServerExceptionList = RfsRegGetMultiSZList(
                                  &v102,
                                  L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\LanmanWorkStation\\Parameters",
                                  L"DisabledSMBQUICServerExceptionList");
    if ( TargetServerExceptionList < 0 )
      goto LABEL_319;
    v94 = v102;
    if ( !v102 )
      goto LABEL_319;
    if ( *v102 )
      TargetServerExceptionList = ReadTargetServerExceptionList(
                                    v102,
                                    &qword_14007D270,
                                    &word_14007D278,
                                    &qword_14007D268);
    LODWORD(v2) = RfsRegFreeMemory(v94);
    if ( TargetServerExceptionList < 0 || !v94 )
LABEL_319:
      LODWORD(v2) = ClearTargetServerExceptionList(&qword_14007D270, &word_14007D278, &qword_14007D268);
  }
  return v2;
}

```

## disassembly

```asm
0x140028fec  push    rbx
0x140028fee  push    rsi
0x140028fef  push    rdi
0x140028ff0  push    r12
0x140028ff2  push    r13
0x140028ff4  push    r14
0x140028ff6  push    r15
0x140028ff8  sub     rsp, 2E0h
0x140028fff  mov     rax, cs:__security_cookie
0x140029006  xor     rax, rsp
0x140029009  mov     [rsp+318h+var_48], rax
0x140029011  xorps   xmm0, xmm0
0x140029014  mov     [rsp+318h+var_2B8], 20A0000h
0x14002901d  xor     r13d, r13d
0x140029020  lea     r8, [rsp+318h+var_2B8]
0x140029025  xor     eax, eax
0x140029027  mov     [rsp+318h+KeyHandle], r13
0x14002902c  lea     rax, [rsp+318h+var_258]
0x140029034  mov     [rsp+318h+var_2E8], r13d
0x140029039  mov     r15d, ecx
0x14002903c  mov     [rsp+318h+var_2B0], rax
0x140029041  movups  xmmword ptr [rsp+318h+ObjectAttributes.ObjectName], xmm0
0x140029049  lea     rdx, aRegistryMachin_5; "\\Registry\\Machine\\System\\CurrentCon"...
0x140029050  mov     [rsp+318h+var_2D0], r13
0x140029055  lea     rcx, aLanmanworkstat; "LanmanWorkStationParameters"
0x14002905c  mov     [rsp+318h+var_2C0], r13
0x140029061  movups  xmmword ptr [rsp+318h+ObjectAttributes.Length], xmm0
0x140029066  movups  xmmword ptr [rsp+318h+ObjectAttributes+1Ch], xmm0
0x14002906e  call    MRxSmbInitRedirectedPath
0x140029073  test    eax, eax
0x140029075  jns     short loc_1400290C1
0x140029077  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002907e  lea     rdx, WPP_GLOBAL_Control
0x140029085  cmp     rcx, rdx
0x140029088  jz      loc_14002A8D1
0x14002908e  mov     edx, [rcx+2Ch]
0x140029091  lea     ebx, [r13+1]
0x140029095  test    bl, dl
0x140029097  jz      loc_14002A8D1
0x14002909d  cmp     [rcx+29h], bl
0x1400290a0  jb      loc_14002A8D1
0x1400290a6  mov     rcx, [rcx+18h]
0x1400290aa  lea     edx, [rbx+29h]
0x1400290ad  mov     r9d, eax
0x1400290b0  lea     r8, WPP_4ff68d8e9b0a3e70c0197c268f5ae5e8_Traceguids
0x1400290b7  call    WPP_SF_d
0x1400290bc  jmp     loc_14002A8D1
0x1400290c1  lea     rax, [rsp+318h+var_2B8]
0x1400290c6  mov     [rsp+318h+var_2D8], r13b
0x1400290cb  xorps   xmm0, xmm0
0x1400290ce  mov     [rsp+318h+ObjectAttributes.ObjectName], rax
0x1400290d6  lea     r8, [rsp+318h+ObjectAttributes]; ObjectAttributes
0x1400290db  mov     [rsp+318h+var_2D7], r13b
0x1400290e0  mov     edx, 20019h; DesiredAccess
0x1400290e5  mov     [rsp+318h+ObjectAttributes.Length], 30h ; '0'
0x1400290ed  lea     rcx, [rsp+318h+KeyHandle]; KeyHandle
0x1400290f2  mov     [rsp+318h+ObjectAttributes.RootDirectory], r13
0x1400290f7  movdqu  xmmword ptr [rsp+318h+ObjectAttributes.SecurityDescriptor], xmm0
0x140029100  mov     sil, r13b
0x140029103  mov     [rsp+318h+ObjectAttributes.Attributes], 240h
0x14002910e  mov     r14b, r13b
0x140029111  call    cs:__imp_ZwOpenKey
0x140029118  nop     dword ptr [rax+rax+00h]
0x14002911d  mov     edi, 4
0x140029122  lea     r12d, [rdi-2]
0x140029126  test    eax, eax
0x140029128  js      loc_14002A5E7
0x14002912e  mov     rcx, [rsp+318h+KeyHandle]
0x140029133  call    MRxSmbEvaluateRegistryRoutingParameters
0x140029138  mov     rcx, [rsp+318h+KeyHandle]; KeyHandle
0x14002913d  call    MRxSmbRemoveDeprecatedRegistryParameters
0x140029142  mov     rcx, [rsp+318h+KeyHandle]; KeyHandle
0x140029147  lea     r8, [rsp+318h+var_2E8]
0x14002914c  lea     rdx, aSmbmaxchainedw_0; "SmbMaxChainedWriteRequests"
0x140029153  call    MRxSmbGetUlongRegistryParameter
0x140029158  test    eax, eax
0x14002915a  js      short loc_140029174
0x14002915c  movzx   eax, word ptr [rsp+318h+var_2E8]
0x140029161  mov     word ptr cs:dword_14007D224, ax
0x140029168  movzx   eax, word ptr [rsp+318h+var_2E8+2]
0x14002916d  mov     word ptr cs:dword_14007D224+2, ax
0x140029174  mov     rcx, [rsp+318h+KeyHandle]; KeyHandle
0x140029179  lea     r8, [rsp+318h+var_2E8]
0x14002917e  lea     rdx, aSmbmaxchainedw; "SmbMaxChainedWriteBytes"
0x140029185  call    MRxSmbGetUlongRegistryParameter
0x14002918a  test    eax, eax
0x14002918c  js      short loc_1400291A6
0x14002918e  movzx   eax, word ptr [rsp+318h+var_2E8]
0x140029193  mov     word ptr cs:dword_14007D228, ax
0x14002919a  movzx   eax, word ptr [rsp+318h+var_2E8+2]
0x14002919f  mov     word ptr cs:dword_14007D228+2, ax
0x1400291a6  mov     rcx, [rsp+318h+KeyHandle]; KeyHandle
0x1400291ab  lea     r8, [rsp+318h+var_2E8]
0x1400291b0  lea     rdx, aDisablechained; "DisableChainedWritesOverNetwork"
0x1400291b7  call    MRxSmbGetUlongRegistryParameter
0x1400291bc  test    eax, eax
0x1400291be  js      short loc_1400291CC
0x1400291c0  cmp     [rsp+318h+var_2E8], r13d
0x1400291c5  setnz   cs:byte_14007D22C
0x1400291cc  mov     rcx, [rsp+318h+KeyHandle]; KeyHandle
0x1400291d1  lea     r8, [rsp+318h+var_2E8]
0x1400291d6  lea     rdx, aSmbdirectdatap; "SmbDirectDataPlacementSecurity"
0x1400291dd  call    MRxSmbGetUlongRegistryParameter
0x1400291e2  mov     ebx, 1
0x1400291e7  test    eax, eax
0x1400291e9  js      short loc_140029223
0x1400291eb  mov     ecx, [rsp+318h+var_2E8]
0x1400291ef  mov     eax, ecx
0x1400291f1  test    ecx, ecx
0x1400291f3  jz      loc_140029284
0x1400291f9  sub     eax, ebx
0x1400291fb  jz      loc_140029284
0x140029201  cmp     eax, ebx
0x140029203  jz      short loc_140029284
0x140029205  mov     r9d, cs:dword_14007D220
0x14002920c  cmp     r9d, ebx
0x14002920f  jz      short loc_140029229
0x140029211  test    cs:byte_1400712A4, dil
0x140029218  jz      short loc_140029223
0x14002921a  mov     dword ptr [rsp+318h+var_2F8], ecx
0x14002921e  call    McTemplateK0qq_EtwWriteTransfer
0x140029223  mov     cs:dword_14007D220, ebx
0x140029229  mov     rcx, [rsp+318h+KeyHandle]; KeyHandle
0x14002922e  lea     r8, [rsp+318h+var_2E8]
0x140029233  lea     rdx, aDisablenotific; "DisableNotifications"
0x14002923a  call    MRxSmbGetUlongRegistryParameter
0x14002923f  movzx   ecx, byte ptr [rsp+318h+var_2E8]
0x140029244  lea     r8, [rsp+318h+var_2E8]
0x140029249  test    eax, eax
0x14002924b  mov     edx, r13d
0x14002924e  cmovns  edx, ecx
0x140029251  mov     rcx, [rsp+318h+KeyHandle]; KeyHandle
0x140029256  mov     cs:byte_14007D230, dl
0x14002925c  lea     rdx, aInvalidauthent; "InvalidAuthenticationCacheLifetime"
0x140029263  call    MRxSmbGetUlongRegistryParameter
0x140029268  test    eax, eax
0x14002926a  js      short loc_1400292B1
0x14002926c  mov     eax, 3Ch ; '<'
0x140029271  cmp     [rsp+318h+var_2E8], eax
0x140029275  cmovb   eax, [rsp+318h+var_2E8]
0x14002927a  imul    rax, cs:SmbCeTicksPerSecond
0x140029282  jmp     short loc_1400292B9
0x140029284  mov     r9d, cs:dword_14007D220
0x14002928b  cmp     r9d, ecx
0x14002928e  jz      short loc_140029229
0x140029290  test    cs:byte_1400712A4, dil
0x140029297  jz      short loc_1400292A6
0x140029299  mov     dword ptr [rsp+318h+var_2F8], ecx
0x14002929d  call    McTemplateK0qq_EtwWriteTransfer
0x1400292a2  mov     ecx, [rsp+318h+var_2E8]
0x1400292a6  mov     cs:dword_14007D220, ecx
0x1400292ac  jmp     loc_140029229
0x1400292b1  imul    rax, cs:SmbCeTicksPerSecond, 1Eh
0x1400292b9  mov     rcx, [rsp+318h+KeyHandle]; KeyHandle
0x1400292be  lea     r8, [rsp+318h+var_2E8]
0x1400292c3  lea     rdx, aDisabledircach; "DisableDirCacheOnDiskIdOptimization"
0x1400292ca  mov     cs:qword_14007D238, rax
0x1400292d1  call    MRxSmbGetUlongRegistryParameter
0x1400292d6  test    eax, eax
0x1400292d8  js      short loc_1400292E6
0x1400292da  cmp     [rsp+318h+var_2E8], r13d
0x1400292df  setnz   byte ptr cs:word_14007D22D
0x1400292e6  mov     rcx, [rsp+318h+KeyHandle]; KeyHandle
0x1400292eb  lea     r8, [rsp+318h+var_2E8]
0x1400292f0  lea     rdx, aBypassfetchnet; "BypassFetchNetworkOpenInfoFullStateMach"...
0x1400292f7  call    MRxSmbGetUlongRegistryParameter
0x1400292fc  test    eax, eax
0x1400292fe  js      short loc_14002930C
0x140029300  cmp     [rsp+318h+var_2E8], r13d
0x140029305  setnz   byte ptr cs:word_14007D22D+1
0x14002930c  mov     rcx, [rsp+318h+KeyHandle]; KeyHandle
0x140029311  lea     r8, [rsp+318h+var_2E8]
0x140029316  lea     rdx, aForcesmbencryp; "ForceSMBEncryptionOverQuic"
0x14002931d  call    MRxSmbGetUlongRegistryParameter
0x140029322  test    eax, eax
0x140029324  js      short loc_140029332
0x140029326  cmp     [rsp+318h+var_2E8], r13d
0x14002932b  setnz   cs:byte_14007D20C
0x140029332  mov     edi, 40h ; '@'
0x140029337  test    dil, r15b
0x14002933a  jnz     short loc_140029362
0x14002933c  mov     rcx, [rsp+318h+KeyHandle]; KeyHandle
0x140029341  lea     r8, [rsp+318h+var_2E8]
0x140029346  lea     rdx, aRequireencrypt; "RequireEncryption"
0x14002934d  call    MRxSmbGetUlongRegistryParameter
0x140029352  test    eax, eax
0x140029354  js      short loc_140029362
0x140029356  cmp     [rsp+318h+var_2E8], r13d
0x14002935b  setnz   cs:byte_14007D13D
0x140029362  mov     rcx, [rsp+318h+KeyHandle]; KeyHandle
0x140029367  lea     r8, [rsp+318h+var_2E8]
0x14002936c  lea     rdx, aRequiresecurit; "RequireSecuritySignature"
0x140029373  call    MRxSmbGetUlongRegistryParameter
0x140029378  test    eax, eax
0x14002937a  js      short loc_14002938C
0x14002937c  cmp     [rsp+318h+var_2E8], r13d
0x140029381  mov     [rsp+318h+var_2D7], bl
0x140029385  setnz   cs:byte_14007D13C
0x14002938c  test    r15b, 20h
0x140029390  jnz     short loc_1400293C0
0x140029392  mov     rcx, [rsp+318h+KeyHandle]; KeyHandle
0x140029397  lea     r8, [rsp+318h+var_2E8]
0x14002939c  lea     rdx, aBlockntlm; "BlockNTLM"
0x1400293a3  call    MRxSmbGetUlongRegistryParameter
0x1400293a8  test    eax, eax
0x1400293aa  js      short loc_1400293B9
0x1400293ac  mov     cs:byte_14007D244, bl
0x1400293b2  cmp     [rsp+318h+var_2E8], r13d
0x1400293b7  jnz     short loc_1400293C0
0x1400293b9  mov     cs:byte_14007D244, r13b
0x1400293c0  test    r12b, r15b
0x1400293c3  jnz     short loc_140029407
0x1400293c5  mov     rcx, [rsp+318h+KeyHandle]; KeyHandle
0x1400293ca  lea     r8, [rsp+318h+var_2E8]
0x1400293cf  lea     rdx, aEnablecompress; "EnableCompressedTraffic"
0x1400293d6  call    MRxSmbGetUlongRegistryParameter
0x1400293db  test    eax, eax
0x1400293dd  js      short loc_140029407
0x1400293df  cmp     [rsp+318h+var_2E8], r13d
0x1400293e4  jz      short loc_1400293EB
0x1400293e6  movzx   ecx, bx
0x1400293e9  jmp     short loc_1400293EE
0x1400293eb  mov     ecx, r13d
0x1400293ee  movzx   eax, cs:word_14007D1CA
0x1400293f5  mov     edx, 0FFFEh
0x1400293fa  and     ax, dx
0x1400293fd  or      ax, cx
0x140029400  mov     cs:word_14007D1CA, ax
0x140029407  mov     r14d, 4
0x14002940d  test    r14b, r15b
0x140029410  jnz     short loc_140029455
0x140029412  mov     rcx, [rsp+318h+KeyHandle]; KeyHandle
0x140029417  lea     r8, [rsp+318h+var_2E8]
0x14002941c  lea     rdx, aDisablecompres; "DisableCompression"
0x140029423  call    MRxSmbGetUlongRegistryParameter
0x140029428  test    eax, eax
0x14002942a  js      short loc_140029455
0x14002942c  cmp     [rsp+318h+var_2E8], r13d
0x140029431  jz      short loc_140029439
0x140029433  movzx   ecx, r12w
0x140029437  jmp     short loc_14002943C
0x140029439  mov     ecx, r13d
0x14002943c  movzx   eax, cs:word_14007D1CA
0x140029443  mov     edx, 0FFFDh
0x140029448  and     ax, dx
0x14002944b  or      ax, cx
0x14002944e  mov     cs:word_14007D1CA, ax
0x140029455  mov     rcx, [rsp+318h+KeyHandle]; KeyHandle
0x14002945a  lea     r8, [rsp+318h+var_2E8]
0x14002945f  lea     rdx, aAsyncdecryptio; "AsyncDecryptionThreshold"
0x140029466  call    MRxSmbGetUlongRegistryParameter
0x14002946b  test    eax, eax
0x14002946d  lea     r8, [rsp+318h+var_2E8]
0x140029472  mov     esi, 10000h
0x140029477  lea     rdx, aAsyncencryptio; "AsyncEncryptionThreshold"
0x14002947e  mov     ecx, esi
0x140029480  cmovns  ecx, [rsp+318h+var_2E8]
0x140029485  mov     cs:dword_14007D0A4, ecx
0x14002948b  mov     rcx, [rsp+318h+KeyHandle]; KeyHandle
0x140029490  call    MRxSmbGetUlongRegistryParameter
0x140029495  test    eax, eax
0x140029497  lea     r8, [rsp+318h+var_2E8]
0x14002949c  mov     ecx, esi
0x14002949e  lea     rdx, aAsynccompressi; "AsyncCompressionThreshold"
0x1400294a5  cmovns  ecx, [rsp+318h+var_2E8]
0x1400294aa  mov     cs:dword_14007D0A8, ecx
0x1400294b0  mov     rcx, [rsp+318h+KeyHandle]; KeyHandle
0x1400294b5  call    MRxSmbGetUlongRegistryParameter
0x1400294ba  test    eax, eax
0x1400294bc  lea     r8, [rsp+318h+var_2E8]
0x1400294c1  mov     ecx, esi
0x1400294c3  lea     rdx, aEnablecompress_0; "EnableCompressibilitySampling"
0x1400294ca  cmovns  ecx, [rsp+318h+var_2E8]
0x1400294cf  mov     cs:dword_14007D0AC, ecx
0x1400294d5  mov     rcx, [rsp+318h+KeyHandle]; KeyHandle
0x1400294da  call    MRxSmbGetUlongRegistryParameter
0x1400294df  test    eax, eax
0x1400294e1  js      short loc_1400294F4
0x1400294e3  cmp     [rsp+318h+var_2E8], r13d
0x1400294e8  jz      short loc_1400294F4
0x1400294ea  or      cs:word_14007D1CA, r14w
0x1400294f2  jmp     short loc_140029500
0x1400294f4  mov     eax, 0FFFBh
0x1400294f9  and     cs:word_14007D1CA, ax
0x140029500  mov     rcx, [rsp+318h+KeyHandle]; KeyHandle
0x140029505  lea     r8, [rsp+318h+var_2D0]
0x14002950a  lea     rdx, aCompressibilit; "CompressibilitySamplingSize"
0x140029511  call    MRxSmbGetUlonglongRegistryParameter2
0x140029516  mov     r14, 20000000000000h
0x140029520  test    eax, eax
0x140029522  js      short loc_140029539
0x140029524  mov     rax, [rsp+318h+var_2D0]
0x140029529  cmp     rax, r14
0x14002952c  cmova   rax, r14
0x140029530  mov     cs:qword_14007D0B0, rax
0x140029537  jmp     short loc_140029544
0x140029539  mov     cs:qword_14007D0B0, 1F400000h
0x140029544  mov     rcx, [rsp+318h+KeyHandle]; KeyHandle
0x140029549  lea     r8, [rsp+318h+var_2D0]
0x14002954e  lea     rdx, aCompressibleth; "CompressibleThreshold"
  ... truncated ...
```
