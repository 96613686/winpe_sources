# DriverEntry

- ea: `0x14007fd3c`
- end: `0x140080cdc`
- name: `DriverEntry`
- size: `4000`
- prototype: `NTSTATUS __stdcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `39`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x14009a010`

## callees

- `0x14001c5f0`
- `0x140023330`
- `0x140027948`
- `0x140028518`
- `0x14002b24c`
- `0x140037bb8`
- `0x14003838c`
- `0x14003b5cc`
- `0x14003b644`
- `0x14003b728`
- `0x14003b830`
- `0x14003bb78`
- `0x14003bbe8`
- `0x14003bc54`
- `0x14003c624`
- `0x14003d8dc`
- `0x140040938`
- `0x140042f6c`
- `0x14004d918`
- `0x14004de4c`
- `0x140059dc0`
- `0x14007fd3c`
- `0x140080ce4`
- `0x14008125c`
- `0x1400812f0`
- `0x1400816dc`
- `0x140081f30`
- `0x1400822b0`
- `0x140082a38`
- `0x1400841ec`
- `0x1400867c8`
- `0x140087c90`
- `0x14008cafc`
- `0x14008cfdc`
- `0x14008d154`
- `0x14008fbc0`
- `0x1400930a0`
- `0x140093fe0`
- `0x14009a078`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x14007ff72`
- `ntoskrnl!KeInitializeEvent` at `0x14007ff72`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400809b6`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400809b6`
- `ntoskrnl!KeQueryTimeIncrement` at `0x14007ff2d`
- `ntoskrnl!KeQueryTimeIncrement` at `0x140080979`
- `ntoskrnl!KeQueryTimeIncrement` at `0x14007ff2d`
- `ntoskrnl!KeQueryTimeIncrement` at `0x140080979`
- `ntoskrnl!EtwRegister` at `0x14007feba`
- `ntoskrnl!EtwRegister` at `0x14007feba`
- `ntoskrnl!KeInitializeGuardedMutex` at `0x14007fdb6`
- `ntoskrnl!KeInitializeGuardedMutex` at `0x1400800d9`
- `ntoskrnl!KeInitializeGuardedMutex` at `0x14007fdb6`
- `ntoskrnl!KeInitializeGuardedMutex` at `0x1400800d9`
- `ntoskrnl!ExInitializeRundownProtection` at `0x14007fd9c`
- `ntoskrnl!ExInitializeRundownProtection` at `0x14007fd9c`
- `ntoskrnl!PcwRegister` at `0x140080a95`
- `ntoskrnl!PcwRegister` at `0x140080a95`
- `ntoskrnl!RtlInitUnicodeString` at `0x14007ffa8`
- `ntoskrnl!RtlInitUnicodeString` at `0x14007ffbd`
- `ntoskrnl!RtlInitUnicodeString` at `0x14007ffd2`
- `ntoskrnl!RtlInitUnicodeString` at `0x14007ffe7`
- `ntoskrnl!RtlInitUnicodeString` at `0x14007fffc`
- `ntoskrnl!RtlInitUnicodeString` at `0x140080011`
- `ntoskrnl!RtlInitUnicodeString` at `0x140080026`
- `ntoskrnl!RtlInitUnicodeString` at `0x14008003b`
- `ntoskrnl!RtlInitUnicodeString` at `0x140080050`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400805ee`
- `ntoskrnl!RtlInitUnicodeString` at `0x14007ffa8`
- `ntoskrnl!RtlInitUnicodeString` at `0x14007ffbd`
- `ntoskrnl!RtlInitUnicodeString` at `0x14007ffd2`
- `ntoskrnl!RtlInitUnicodeString` at `0x14007ffe7`
- `ntoskrnl!RtlInitUnicodeString` at `0x14007fffc`
- `ntoskrnl!RtlInitUnicodeString` at `0x140080011`
- `ntoskrnl!RtlInitUnicodeString` at `0x140080026`
- `ntoskrnl!RtlInitUnicodeString` at `0x14008003b`
- `ntoskrnl!RtlInitUnicodeString` at `0x140080050`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400805ee`
- `ntoskrnl!ExAllocatePool2` at `0x140080154`
- `ntoskrnl!ExAllocatePool2` at `0x140080154`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400803b9`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140080c3a`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140095caf`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400803b9`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140080c3a`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140095caf`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14008020d`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14008020d`
- `ntoskrnl!KeQueryMaximumProcessorCountEx` at `0x140080138`
- `ntoskrnl!KeQueryMaximumProcessorCountEx` at `0x140080138`
- `ntoskrnl!ExInitializeFastResource` at `0x14008011b`
- `ntoskrnl!ExInitializeFastResource` at `0x14008011b`
- `rdbss!RxNameCacheInitializeEx` at `0x1400806f6`
- `rdbss!RxNameCacheInitializeEx` at `0x1400806f6`
- `rdbss!RxRegisterMinirdr` at `0x140080647`
- `rdbss!RxRegisterMinirdr` at `0x140080647`

## string_xrefs

- `0x14008023f`: `\Registry\Machine\Software\Policies\Microsoft\Windows\LanmanWorkstation`
- `0x1400802e3`: `\Registry\Machine\System\CurrentControlSet\Services\LanmanWorkStation\Parameters`

## pseudocode

```c
NTSTATUS __stdcall DriverEntry(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)
{
  int v3; // eax
  __int64 v4; // r9
  __int64 v5; // rdx
  __int64 v6; // rcx
  unsigned int v7; // esi
  ULONG MaximumProcessorCount; // eax
  __int64 Timer_high; // rdx
  __int64 v10; // r8
  NTSTATUS v11; // ebx
  PDEVICE_OBJECT v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // r9
  unsigned int CipherSuiteOrderPolicySetting; // ebx
  int inited; // eax
  int v17; // eax
  unsigned int v18; // ebx
  __int64 v19; // rcx
  unsigned int SigningAlgorithmOrderPolicySetting; // eax
  PDEVICE_OBJECT v21; // rcx
  unsigned int CompressionAlgorithmSuiteOrderPolicySetting; // eax
  __int64 i; // rbx
  __int64 v24; // r9
  int v25; // edx
  PDEVICE_OBJECT v26; // rcx
  __int64 v27; // rdx
  int v28; // ecx
  int v29; // r9d
  PDEVICE_OBJECT v30; // rcx
  __int64 v31; // rdx
  bool v32; // sf
  __int64 v33; // rdx
  __int64 v34; // rcx
  __int64 v35; // r8
  __int64 v36; // r9
  int DeviceName; // [rsp+20h] [rbp-308h]
  ULONG DeviceCharacteristics; // [rsp+38h] [rbp-2F0h]
  PRDBSS_DEVICE_OBJECT DeviceObject; // [rsp+60h] [rbp-2C8h] BYREF
  char v41; // [rsp+68h] [rbp-2C0h] BYREF
  char v42; // [rsp+69h] [rbp-2BFh] BYREF
  bool v43; // [rsp+6Ah] [rbp-2BEh] BYREF
  char v44; // [rsp+6Bh] [rbp-2BDh] BYREF
  char v45; // [rsp+6Ch] [rbp-2BCh] BYREF
  char v46; // [rsp+6Dh] [rbp-2BBh] BYREF
  int v47; // [rsp+70h] [rbp-2B8h]
  __int64 v48; // [rsp+78h] [rbp-2B0h] BYREF
  char *v49; // [rsp+80h] [rbp-2A8h]
  _QWORD v50[2]; // [rsp+88h] [rbp-2A0h] BYREF
  _PCW_REGISTRATION_INFORMATION Info; // [rsp+98h] [rbp-290h] BYREF
  __int64 v52; // [rsp+C8h] [rbp-260h]
  UNICODE_STRING DestinationString; // [rsp+D0h] [rbp-258h] BYREF
  char v54; // [rsp+E0h] [rbp-248h] BYREF
  _QWORD *v55; // [rsp+100h] [rbp-228h]
  __int64 v56; // [rsp+108h] [rbp-220h]
  char *v57; // [rsp+110h] [rbp-218h]
  __int64 v58; // [rsp+118h] [rbp-210h]
  char *v59; // [rsp+120h] [rbp-208h]
  __int64 v60; // [rsp+128h] [rbp-200h]
  bool *v61; // [rsp+130h] [rbp-1F8h]
  __int64 v62; // [rsp+138h] [rbp-1F0h]
  char *v63; // [rsp+140h] [rbp-1E8h]
  __int64 v64; // [rsp+148h] [rbp-1E0h]
  char *v65; // [rsp+150h] [rbp-1D8h]
  __int64 v66; // [rsp+158h] [rbp-1D0h]
  char *v67; // [rsp+160h] [rbp-1C8h]
  __int64 v68; // [rsp+168h] [rbp-1C0h]

  v50[1] = DriverObject;
  DestinationString = 0;
  DeviceObject = 0;
  wil_InitializeFeatureStaging();
  ExInitializeRundownProtection(&MRxSmbRdmaRundownProtector);
  MRxSmbRdmaRundownSrwLock = 0;
  KeInitializeGuardedMutex(&MRxSmbRdmaRundownMutex);
  *(_QWORD *)&WPP_MAIN_CB.Type = 0;
  WPP_MAIN_CB.DriverObject = (struct _DRIVER_OBJECT *)&WPP_ThisDir_CTLGUID_MrxSmbLog;
  WPP_MAIN_CB.NextDevice = 0;
  WPP_MAIN_CB.CurrentIrp = 0;
  WPP_MAIN_CB.Timer = (PIO_TIMER)1;
  WppLoadTracingSupport();
  WPP_MAIN_CB.CurrentIrp = 0;
  WppInitKm();
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qZ(
      WPP_GLOBAL_Control->AttachedDevice,
      10,
      (unsigned int)&WPP_4ff68d8e9b0a3e70c0197c268f5ae5e8_Traceguids,
      (_DWORD)DriverObject,
      (__int64)&DriverObject->DriverName);
  }
  TlgRegisterAggregateProviderEx(&dword_1400700C0);
  v3 = McGenEventRegister_EtwRegister();
  if ( v3 < 0
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 11, &WPP_4ff68d8e9b0a3e70c0197c268f5ae5e8_Traceguids, (unsigned int)v3);
  }
  v4 = 0;
  if ( !Microsoft_Windows_Networking_CorrelationHandle )
    v4 = (unsigned int)EtwRegister(
                         &Microsoft_Windows_Networking_CorrelationId,
                         Microsoft_Windows_Networking_Correlation_EtwEnableCallback,
                         0,
                         &Microsoft_Windows_Networking_CorrelationHandle);
  if ( !(_DWORD)v4 )
    Microsoft_Windows_Networking_ProviderId = (__int128)REMOTEFS_SMB;
  if ( (int)v4 < 0
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 12, &WPP_4ff68d8e9b0a3e70c0197c268f5ae5e8_Traceguids, v4);
  }
  MRxSmbLegacyPerfCtrsStartTime = MEMORY[0xFFFFF78000000014];
  MRxSmbInsecureGuestAuthEnabledEventThrottle = 0;
  qword_1400712B8 = 0x861C46800uLL / KeQueryTimeIncrement();
  FastMutex.Count = 1;
  FastMutex.Owner = 0;
  FastMutex.Contention = 0;
  KeInitializeEvent(&FastMutex.Event, SynchronizationEvent, 0);
  TlgRegisterAggregateProviderEx(&dword_140070128);
  qword_140070FA0 = 0;
  MRxSmbCipherSuiteOrderPushLock = 0;
  RtlInitUnicodeString(&::DestinationString, 0);
  RtlInitUnicodeString(&SmbCeContext, 0);
  RtlInitUnicodeString(&stru_140070F60, 0);
  RtlInitUnicodeString(&stru_140070F70, 0);
  RtlInitUnicodeString(&stru_140070F80, 0);
  RtlInitUnicodeString(&stru_140070F90, 0);
  RtlInitUnicodeString(&MRxSmbRemoteBootMachineName, 0);
  RtlInitUnicodeString(&MRxSmbRemoteBootMachineDomain, 0);
  RtlInitUnicodeString(&MRxSmbRemoteBootMachinePassword, 0);
  qword_14007D0D8 = 0;
  qword_14007D248 = 0;
  qword_14007D268 = 0;
  P = 0;
  dword_14007D0E8 = 0;
  word_14007D202 = 1;
  word_14007D22D = 0;
  qword_14007D238 = 30;
  dword_14007D220 = 1;
  dword_14007D224 = 16;
  dword_14007D228 = 0x100000;
  byte_14007D22C = 0;
  SmbCeGetConfigurationInformation();
  SmbCeGetServersWithExtendedSessTimeout();
  SmbCeCheckLMCompatibilityLevel();
  SmbCeCheckSmb2StartTypeSetting();
  SmbCeCheckWorkstationParameterSetting();
  KeInitializeGuardedMutex(&MRxSmb2ClientShareCounterSubscribersMutex);
  MRxSmbPerfCounterNetRootsPushLock = 0;
  v5 = 0;
  v6 = 0;
  do
  {
    *(_QWORD *)((char *)&WPP_MAIN_CB.DeviceType + v6) = (char *)&WPP_MAIN_CB.DeviceExtension + v6;
    *(PVOID *)((char *)&WPP_MAIN_CB.DeviceExtension + v6) = (char *)&WPP_MAIN_CB.DeviceExtension + v6;
    ++v5;
    v6 += 16;
  }
  while ( v5 != 32 );
  ExInitializeFastResource(&GlobalResource, 0, &WPP_MAIN_CB.DeviceExtension);
  v7 = 1;
  MaximumProcessorCount = KeQueryMaximumProcessorCountEx(0xFFFFu);
  MRxSmbLegacyPerfCtrs = (PVOID)ExAllocatePool2(72, MaximumProcessorCount << 8, 1834185296);
  if ( !MRxSmbLegacyPerfCtrs )
  {
    v11 = -1073741670;
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      v13 = 14;
      v14 = 3221225626LL;
LABEL_26:
      WPP_SF_d(v12->AttachedDevice, v13, &WPP_4ff68d8e9b0a3e70c0197c268f5ae5e8_Traceguids, v14);
      goto LABEL_137;
    }
    goto LABEL_137;
  }
  v11 = RxCeInitializeCryptoSupport();
  if ( v11 < 0 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      goto LABEL_137;
    Timer_high = HIDWORD(WPP_GLOBAL_Control->Timer);
    if ( (Timer_high & 1) == 0 || !BYTE1(WPP_GLOBAL_Control->Timer) )
      goto LABEL_137;
    v13 = 15;
    goto LABEL_32;
  }
  ExAcquirePushLockExclusiveEx(&MRxSmbCipherSuiteOrderPushLock, 0);
  MRxSmbInitDefaultCipherSuiteOrder(&dword_14007D19C, &word_14007D1AC);
  CipherSuiteOrderPolicySetting = SmbCryptoReadCipherSuiteOrderPolicySetting(
                                    L"\\Registry\\Machine\\Software\\Policies\\Microsoft\\Windows\\LanmanWorkstation",
                                    &dword_14007D19C,
                                    &word_14007D1AC);
  if ( (int)(CipherSuiteOrderPolicySetting + 0x80000000) >= 0 && CipherSuiteOrderPolicySetting != -1073741772 )
  {
    if ( CipherSuiteOrderPolicySetting == -1073739509 && (byte_1400712C3 & 0x10) != 0 )
      McTemplateK0z_EtwWriteTransfer();
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        16,
        &WPP_4ff68d8e9b0a3e70c0197c268f5ae5e8_Traceguids,
        CipherSuiteOrderPolicySetting);
    }
  }
  if ( CipherSuiteOrderPolicySetting == -1073741772 )
  {
    v48 = 34209792;
    v49 = &v54;
    inited = MRxSmbInitRedirectedPath(
               L"LanmanWorkStationParameters",
               L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\LanmanWorkStation\\Parameters",
               &v48);
    if ( inited >= 0 )
    {
      v17 = SmbCryptoReadCipherSuiteOrderPolicySetting(v49, &dword_14007D19C, &word_14007D1AC);
      v18 = v17;
      if ( v17 < 0 )
      {
        if ( v17 == -1073739509 && (byte_1400712C3 & 0x10) != 0 )
          McTemplateK0z_EtwWriteTransfer();
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 18, &WPP_4ff68d8e9b0a3e70c0197c268f5ae5e8_Traceguids, v18);
        }
      }
    }
    else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
           && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
           && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        17,
        &WPP_4ff68d8e9b0a3e70c0197c268f5ae5e8_Traceguids,
        (unsigned int)inited);
    }
  }
  ExReleasePushLockExclusiveEx(&MRxSmbCipherSuiteOrderPushLock, 0);
  word_14007D1F4 = 3;
  *(_DWORD *)((char *)&qword_14007D1E6 + 2) = 2;
  *(__int64 *)((char *)&qword_14007D1E6 + 6) = 1;
  SigningAlgorithmOrderPolicySetting = SmbCryptoReadSigningAlgorithmOrderPolicySetting(
                                         v19,
                                         (char *)&qword_14007D1E6 + 2,
                                         &word_14007D1F4);
  v21 = (PDEVICE_OBJECT)(SigningAlgorithmOrderPolicySetting + 0x80000000);
  if ( (int)v21 >= 0 && SigningAlgorithmOrderPolicySetting != -1073741772 )
  {
    v21 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        19,
        &WPP_4ff68d8e9b0a3e70c0197c268f5ae5e8_Traceguids,
        SigningAlgorithmOrderPolicySetting);
    }
  }
  word_14007D1C8 = 5;
  xmmword_14007D1B0 = (__int128)_mm_load_si128((const __m128i *)&_xmm);
  dword_14007D1C0 = 5;
  CompressionAlgorithmSuiteOrderPolicySetting = SmbCompressionReadCompressionAlgorithmSuiteOrderPolicySetting(
                                                  v21,
                                                  &xmmword_14007D1B0,
                                                  &word_14007D1C8);
  if ( (int)(CompressionAlgorithmSuiteOrderPolicySetting + 0x80000000) >= 0
    && CompressionAlgorithmSuiteOrderPolicySetting != -1073741772
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      20,
      &WPP_4ff68d8e9b0a3e70c0197c268f5ae5e8_Traceguids,
      CompressionAlgorithmSuiteOrderPolicySetting);
  }
  for ( i = 0; ; i = (unsigned int)(i + 1) )
  {
    v47 = i;
    if ( (unsigned int)i >= (unsigned __int16)word_14007D1C8 )
      break;
    v24 = *((unsigned int *)&xmmword_14007D1B0 + i);
    if ( (int)v24 <= 0 || (unsigned int)v24 >= 0x20 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 21, &WPP_4ff68d8e9b0a3e70c0197c268f5ae5e8_Traceguids, v24);
      }
    }
    else
    {
      v25 = 1 << (v24 - 1);
      if ( (dword_14007D1C4 & v25) != 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 22, &WPP_4ff68d8e9b0a3e70c0197c268f5ae5e8_Traceguids, v24);
        }
      }
      else
      {
        dword_14007D1C4 |= v25;
      }
    }
  }
  word_14007D200 = 2;
  dword_14007D1F8 = 1;
  dword_14007D1FC = 2;
  v11 = SmbWskProviderInitialize();
  if ( v11 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || !BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      goto LABEL_137;
    }
    v13 = 23;
    goto LABEL_32;
  }
  MRxSmbInitializeGlobalTransport();
  v7 = 3;
  RtlInitUnicodeString(&DestinationString, L"\\Device\\LanmanRedirector");
  v11 = RxRegisterMinirdr(
          &DeviceObject,
          DriverObject,
          (PMINIRDR_DISPATCH)&MRxSmbDispatch,
          byte_14007D16C != 0 ? 79522 : 79778,
          &DestinationString,
          0x600u,
          0x14u,
          0x10u);
  if ( v11 < 0 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || !BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      goto LABEL_137;
    }
    v13 = 24;
    goto LABEL_32;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      25,
      &WPP_4ff68d8e9b0a3e70c0197c268f5ae5e8_Traceguids,
      (unsigned int)DeviceObject->DeviceObject.ReferenceCount);
  }
  DeviceName = 0;
  RxNameCacheInitializeEx(&DeviceObject[1].RxNetNameTableInDeviceObject.TableLock.ActiveEntries, 8, 128);
  v7 = 4;
  LODWORD(DeviceObject[1].RxNetNameTableInDeviceObject.TableLock.SystemResourcesList.Flink) = -1;
  DeviceObject[1].RxNetNameTableInDeviceObject.TableLock.SystemResourcesList.Blink = (struct _LIST_ENTRY *)&dword_14007D104;
  MRxSmbInitializeTransportArrayInstance(DeviceObject, 0);
  DeviceObject->RxNetNameTableInDeviceObject.HashBuckets[28].Flink = (struct _LIST_ENTRY *)MRxSmbLegacyPerfCtrs;
  v11 = InitialializeSubRdrDialectTable((__int64)DeviceObject);
  if ( v11 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || !BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      goto LABEL_137;
    }
    v13 = 26;
    goto LABEL_32;
  }
  v7 = 2;
  if ( (unsigned int)dword_1400700C0 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1400700C0, 0x400000000000LL) )
  {
    v50[0] = 0x1000000;
    v55 = v50;
    v56 = 8;
    v41 = byte_14007D13C;
    v57 = &v41;
    v58 = 1;
    v42 = byte_14007D13D;
    v59 = &v42;
    v60 = 1;
    v43 = (word_14007D1CA & 2) != 0;
    v61 = &v43;
    v62 = 1;
    v44 = word_14007D1CA & 1;
    v63 = &v44;
    v64 = 1;
    v45 = byte_14007D244;
    v65 = &v45;
    v66 = 1;
    v46 = byte_14007D164;
    v67 = &v46;
    v68 = 1;
    DeviceName = 9;
    tlgWriteTransfer_EtwWriteTransfer(&dword_1400700C0, &unk_140067AC1, 0, 0);
  }
  v11 = RegisterMailslotMiniRdr(DriverObject);
  if ( v11 < 0 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || !BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      goto LABEL_137;
    }
    v13 = 27;
LABEL_32:
    v14 = (unsigned int)v11;
    goto LABEL_26;
  }
  v7 = 5;
  v11 = MRxSmbInitializeMm();
  if ( v11 < 0 )
    goto LABEL_137;
  v7 = 6;
  SmbCeTraceFlags = 0;
  SmbCeTicksPerSecond = 10000000;
  SmbCeTicksPerSecond = 10000000LL / KeQueryTimeIncrement();
  qword_140070DC8 = (__int64)&SmbCeCompoundingKeyList;
  SmbCeCompoundingKeyList = (__int64)&SmbCeCompoundingKeyList;
  KeInitializeSpinLock(&SmbCeCompoundingKeyListLock);
  v11 = MRxSmbInitializeConnectionEngine(DeviceObject);
  if ( v11 < 0 )
    goto LABEL_137;
  v7 = 7;
  v11 = MRxSmbInitializeExchangeEngine(DeviceObject);
  if ( v11 < 0 )
    goto LABEL_137;
  v7 = 8;
  byte_14007D0C0 &= ~1u;
  *(&Info.Version + 1) = 0;
  *(&Info.CounterCount + 1) = 0;
  v52 = 0;
  Info.Version = 512;
  Info.Name = (PCUNICODE_STRING)L"\"$";
  Info.CounterCount = 35;
  Info.Counters = (PPCW_COUNTER_DESCRIPTOR)&`MRxSmbInitRegistrationInformationShareCounters'::`2'::Descriptors;
  Info.Callback = (PPCW_CALLBACK)MRxSmb2ClientShareCountersCallback;
  Info.CallbackContext = 0;
  v11 = PcwRegister(&MRxSmbShareCounters, &Info);
  if ( v11 < 0 )
  {
    v26 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || !BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      goto LABEL_137;
    }
    v27 = 28;
    goto LABEL_119;
  }
  v7 = 9;
  LOBYTE(DeviceObject[1].RxNetNameTableInDeviceObject.TableLock.OwnerTable) |= 1u;
  LOBYTE(DeviceObject[1].RxNetNameTableInDeviceObject.TableLock.OwnerTable) |= 2u;
  LOBYTE(DeviceObject[1].RxNetNameTableInDeviceObject.TableLock.OwnerTable) |= 4u;
  LOBYTE(DeviceObject[1].RxNetNameTableInDeviceObject.TableLock.OwnerTable) |= 8u;
  LOBYTE(DeviceObject[1].RxNetNameTableInDeviceObject.TableLock.OwnerTable) |= 0x10u;
  SubscribeForEdpPolicyChanges();
  v11 = SmbCompressionInitialize();
  if ( v11 < 0 )
  {
    v26 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || !BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      goto LABEL_137;
    }
    v27 = 29;
LABEL_119:
    WPP_SF_d(v26->AttachedDevice, v27, &WPP_4ff68d8e9b0a3e70c0197c268f5ae5e8_Traceguids, (unsigned int)v11);
    goto LABEL_137;
  }
  RdrPerfBlockLookasideList = (PVOID)PplCreateLookasideList(
                                       v28,
                                       Timer_high,
                                       v10,
                                       v29,
                                       DeviceName,
                                       0x1F8u,
                                       0x6D537250u,
                                       DeviceCharacteristics,
                                       0x6D537250u);
  if ( !RdrPerfBlockLookasideList )
  {
    v11 = -1073741670;
    v30 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || !BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      goto LABEL_137;
    }
    v31 = 30;
LABEL_130:
    WPP_SF_d(v30->AttachedDevice, v31, &WPP_4ff68d8e9b0a3e70c0197c268f5ae5e8_Traceguids, 3221225626LL);
    goto LABEL_137;
  }
  if ( (unsigned __int8)RxSmbdInitializeAsyncSendContextPpll() )
  {
    v7 = 10;
    goto LABEL_137;
  }
  v11 = -1073741670;
  v30 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    v31 = 31;
    goto LABEL_130;
  }
LABEL_137:
  v32 = v11 < 0;
  if ( v11 )
  {
    MRxSmbInitUnwind(DriverObject, v7);
    wil_UninitializeFeatureStaging();
    v32 = v11 < 0;
  }
  if ( !v32 )
  {
    memset64(DriverObject->MajorFunction, (unsigned __int64)MRxSmbFsdDispatch, 0x1Cu);
    DriverObject->DriverUnload = (PDRIVER_UNLOAD)MRxSmbUnload;
    g_MRxSmbIsLoadedAsDriver = 1;
    MRxSmbDeviceObject = DeviceObject;
    v36 = (unsigned int)((unsigned int)MRxSmbIsRdmaUsageAllowedByLicense(0, Timer_high, v10) != 0) + 2;
    if ( (byte_1400712C3 & 8) != 0 )
      McTemplateK0dd_EtwWriteTransfer(v34, v33, v35, v36);
  }
  return v11;
}

```

## disassembly

```asm
0x14007fd3c  mov     [rsp+arg_8], rbx
0x14007fd41  mov     [rsp+arg_10], rsi
0x14007fd46  push    rdi
0x14007fd47  push    r12
0x14007fd49  push    r13
0x14007fd4b  push    r14
0x14007fd4d  push    r15
0x14007fd4f  sub     rsp, 300h
0x14007fd56  mov     rax, cs:__security_cookie
0x14007fd5d  xor     rax, rsp
0x14007fd60  mov     [rsp+328h+var_38], rax
0x14007fd68  mov     r13, rcx
0x14007fd6b  mov     [rsp+328h+var_298], rcx
0x14007fd73  xor     ebx, ebx
0x14007fd75  mov     [rsp+328h+var_2D0], ebx
0x14007fd79  xorps   xmm0, xmm0
0x14007fd7c  movups  xmmword ptr [rsp+328h+DestinationString.Length], xmm0
0x14007fd84  mov     [rsp+328h+DeviceObject], rbx
0x14007fd89  mov     r12b, bl
0x14007fd8c  mov     [rsp+328h+var_2D4], bl
0x14007fd90  call    wil_InitializeFeatureStaging
0x14007fd95  lea     rcx, MRxSmbRdmaRundownProtector; RunRef
0x14007fd9c  call    cs:__imp_ExInitializeRundownProtection
0x14007fda3  nop     dword ptr [rax+rax+00h]
0x14007fda8  mov     cs:MRxSmbRdmaRundownSrwLock, rbx
0x14007fdaf  lea     rcx, MRxSmbRdmaRundownMutex; Mutex
0x14007fdb6  call    cs:__imp_KeInitializeGuardedMutex
0x14007fdbd  nop     dword ptr [rax+rax+00h]
0x14007fdc2  mov     qword ptr cs:WPP_MAIN_CB.Type, rbx
0x14007fdc9  lea     rax, WPP_ThisDir_CTLGUID_MrxSmbLog
0x14007fdd0  mov     cs:WPP_MAIN_CB.DriverObject, rax
0x14007fdd7  mov     cs:WPP_MAIN_CB.NextDevice, rbx
0x14007fdde  mov     cs:WPP_MAIN_CB.CurrentIrp, rbx
0x14007fde5  lea     r15d, [rbx+1]
0x14007fde9  mov     cs:WPP_MAIN_CB.Timer, r15
0x14007fdf0  call    WppLoadTracingSupport
0x14007fdf5  mov     cs:WPP_MAIN_CB.CurrentIrp, rbx; __annotation("TMC:", "f818ebb3-fbc4-4191-96d6-4e5c37c8a237", "MrxSmbLog", "MRXSMB_TRACE_TYPE_ERROR", "MRXSMB_TRACE_TYPE_MISC", "MRXSMB_TRACE_TYPE_NETWORK", "MRXSMB_TRACE_TYPE_SECURITY", "MRXSMB_TRACE_TYPE_EXCHANGE", "MRXSMB_TRACE_TYPE_COMPOUNDING", "MRXSMB_TRACE_TYPE_CONNECTION_OBJECT", "MRXSMB_TRACE_TYPE_MID_WINDOW", "MRXSMB_TRACE_TYPE_MULTICHANNEL", "MRXSMB_TRACE_TYPE_VMBUS", "MRXSMB_TRACE_TYPE_TURBOIO", "MRXSMB_TRACE_TYPE_CERTIFICATE", "MRXSMB_TRACE_TYPE_COMPRESSION", "MRXSMB_TRACE_TYPE_TRANSPORT_MANAGEMENT", "PUBLIC_TMF:")
0x14007fdfc  call    WppInitKm
0x14007fe01  lea     rsi, WPP_GLOBAL_Control; __annotation("TMF:",
0x14007fe08  mov     rcx, cs:WPP_GLOBAL_Control
0x14007fe0f  lea     r14d, [rbx+2]
0x14007fe13  cmp     rcx, rsi
0x14007fe16  jz      short loc_14007FE4A
0x14007fe18  mov     eax, [rcx+2Ch]
0x14007fe1b  test    r14b, al
0x14007fe1e  jz      short loc_14007FE4A
0x14007fe20  lea     rdi, WPP_4ff68d8e9b0a3e70c0197c268f5ae5e8_Traceguids
0x14007fe27  cmp     byte ptr [rcx+29h], 4
0x14007fe2b  jb      short loc_14007FE51
0x14007fe2d  lea     rax, [r13+38h]
0x14007fe31  lea     edx, [rbx+0Ah]
0x14007fe34  mov     [rsp+328h+DeviceName], rax
0x14007fe39  mov     r9, r13
0x14007fe3c  mov     r8, rdi
0x14007fe3f  mov     rcx, [rcx+18h]
0x14007fe43  call    WPP_SF_qZ
0x14007fe48  jmp     short loc_14007FE51
0x14007fe4a  lea     rdi, WPP_4ff68d8e9b0a3e70c0197c268f5ae5e8_Traceguids
0x14007fe51  xor     edx, edx
0x14007fe53  lea     rcx, dword_1400700C0; CallbackContext
0x14007fe5a  call    TlgRegisterAggregateProviderEx
0x14007fe5f  call    McGenEventRegister_EtwRegister
0x14007fe64  test    eax, eax
0x14007fe66  jns     short loc_14007FE96
0x14007fe68  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14007fe6f  cmp     rcx, rsi
0x14007fe72  jz      short loc_14007FE96
0x14007fe74  mov     edx, [rcx+2Ch]
0x14007fe77  test    r15b, dl
0x14007fe7a  jz      short loc_14007FE96
0x14007fe7c  cmp     [rcx+29h], r15b
0x14007fe80  jb      short loc_14007FE96
0x14007fe82  mov     edx, 0Bh
0x14007fe87  mov     r9d, eax
0x14007fe8a  mov     r8, rdi
0x14007fe8d  mov     rcx, [rcx+18h]
0x14007fe91  call    WPP_SF_d
0x14007fe96  mov     r9d, ebx
0x14007fe99  cmp     cs:Microsoft_Windows_Networking_CorrelationHandle, rbx
0x14007fea0  jnz     short loc_14007FEC9
0x14007fea2  lea     r9, Microsoft_Windows_Networking_CorrelationHandle; RegHandle
0x14007fea9  xor     r8d, r8d; CallbackContext
0x14007feac  lea     rdx, Microsoft_Windows_Networking_Correlation_EtwEnableCallback; EnableCallback
0x14007feb3  lea     rcx, Microsoft_Windows_Networking_CorrelationId; ProviderId
0x14007feba  call    cs:__imp_EtwRegister
0x14007fec1  nop     dword ptr [rax+rax+00h]
0x14007fec6  mov     r9d, eax
0x14007fec9  test    r9d, r9d
0x14007fecc  jnz     short loc_14007FEDD
0x14007fece  movups  xmm0, xmmword ptr cs:REMOTEFS_SMB.Data1
0x14007fed5  movdqu  cs:Microsoft_Windows_Networking_ProviderId, xmm0
0x14007fedd  mov     [rsp+328h+var_2D8], r9d
0x14007fee2  test    r9d, r9d
0x14007fee5  jns     short loc_14007FF12
0x14007fee7  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14007feee  cmp     rcx, rsi
0x14007fef1  jz      short loc_14007FF12
0x14007fef3  mov     eax, [rcx+2Ch]
0x14007fef6  test    r15b, al
0x14007fef9  jz      short loc_14007FF12
0x14007fefb  cmp     [rcx+29h], r15b
0x14007feff  jb      short loc_14007FF12
0x14007ff01  mov     edx, 0Ch
0x14007ff06  mov     r8, rdi
0x14007ff09  mov     rcx, [rcx+18h]
0x14007ff0d  call    WPP_SF_d
0x14007ff12  mov     rax, 0FFFFF78000000014h
0x14007ff1c  mov     rax, [rax]
0x14007ff1f  mov     cs:MRxSmbLegacyPerfCtrsStartTime, rax
0x14007ff26  mov     cs:MRxSmbInsecureGuestAuthEnabledEventThrottle, rbx
0x14007ff2d  call    cs:__imp_KeQueryTimeIncrement
0x14007ff34  nop     dword ptr [rax+rax+00h]
0x14007ff39  mov     ecx, eax
0x14007ff3b  xor     edx, edx
0x14007ff3d  mov     rax, 861C46800h
0x14007ff47  div     rcx
0x14007ff4a  mov     cs:qword_1400712B8, rax
0x14007ff51  mov     cs:FastMutex.Count, r15d
0x14007ff58  mov     cs:FastMutex.Owner, rbx
0x14007ff5f  mov     cs:FastMutex.Contention, ebx
0x14007ff65  xor     r8d, r8d; State
0x14007ff68  mov     edx, r15d; Type
0x14007ff6b  lea     rcx, FastMutex.Event; Event
0x14007ff72  call    cs:__imp_KeInitializeEvent
0x14007ff79  nop     dword ptr [rax+rax+00h]
0x14007ff7e  lea     rdx, EEL_EtwEventHandler
0x14007ff85  lea     rcx, dword_140070128; CallbackContext
0x14007ff8c  call    TlgRegisterAggregateProviderEx
0x14007ff91  mov     cs:qword_140070FA0, rbx
0x14007ff98  mov     cs:MRxSmbCipherSuiteOrderPushLock, rbx
0x14007ff9f  xor     edx, edx; SourceString
0x14007ffa1  lea     rcx, DestinationString; DestinationString
0x14007ffa8  call    cs:__imp_RtlInitUnicodeString
0x14007ffaf  nop     dword ptr [rax+rax+00h]
0x14007ffb4  xor     edx, edx; SourceString
0x14007ffb6  lea     rcx, SmbCeContext; DestinationString
0x14007ffbd  call    cs:__imp_RtlInitUnicodeString
0x14007ffc4  nop     dword ptr [rax+rax+00h]
0x14007ffc9  xor     edx, edx; SourceString
0x14007ffcb  lea     rcx, stru_140070F60; DestinationString
0x14007ffd2  call    cs:__imp_RtlInitUnicodeString
0x14007ffd9  nop     dword ptr [rax+rax+00h]
0x14007ffde  xor     edx, edx; SourceString
0x14007ffe0  lea     rcx, stru_140070F70; DestinationString
0x14007ffe7  call    cs:__imp_RtlInitUnicodeString
0x14007ffee  nop     dword ptr [rax+rax+00h]
0x14007fff3  xor     edx, edx; SourceString
0x14007fff5  lea     rcx, stru_140070F80; DestinationString
0x14007fffc  call    cs:__imp_RtlInitUnicodeString
0x140080003  nop     dword ptr [rax+rax+00h]
0x140080008  xor     edx, edx; SourceString
0x14008000a  lea     rcx, stru_140070F90; DestinationString
0x140080011  call    cs:__imp_RtlInitUnicodeString
0x140080018  nop     dword ptr [rax+rax+00h]
0x14008001d  xor     edx, edx; SourceString
0x14008001f  lea     rcx, MRxSmbRemoteBootMachineName; DestinationString
0x140080026  call    cs:__imp_RtlInitUnicodeString
0x14008002d  nop     dword ptr [rax+rax+00h]
0x140080032  xor     edx, edx; SourceString
0x140080034  lea     rcx, MRxSmbRemoteBootMachineDomain; DestinationString
0x14008003b  call    cs:__imp_RtlInitUnicodeString
0x140080042  nop     dword ptr [rax+rax+00h]
0x140080047  xor     edx, edx; SourceString
0x140080049  lea     rcx, MRxSmbRemoteBootMachinePassword; DestinationString
0x140080050  call    cs:__imp_RtlInitUnicodeString
0x140080057  nop     dword ptr [rax+rax+00h]
0x14008005c  mov     cs:qword_14007D0D8, rbx
0x140080063  mov     cs:qword_14007D248, rbx
0x14008006a  mov     cs:qword_14007D268, rbx
0x140080071  mov     cs:P, rbx
0x140080078  mov     cs:dword_14007D0E8, ebx
0x14008007e  mov     cs:word_14007D202, r15w
0x140080086  mov     cs:word_14007D22D, bx
0x14008008d  mov     cs:qword_14007D238, 1Eh
0x140080098  mov     cs:dword_14007D220, r15d
0x14008009f  mov     cs:dword_14007D224, 10h
0x1400800a9  mov     cs:dword_14007D228, 100000h
0x1400800b3  mov     cs:byte_14007D22C, bl
0x1400800b9  call    SmbCeGetConfigurationInformation
0x1400800be  call    SmbCeGetServersWithExtendedSessTimeout
0x1400800c3  call    SmbCeCheckLMCompatibilityLevel
0x1400800c8  call    SmbCeCheckSmb2StartTypeSetting
0x1400800cd  call    SmbCeCheckWorkstationParameterSetting
0x1400800d2  lea     rcx, MRxSmb2ClientShareCounterSubscribersMutex; Mutex
0x1400800d9  call    cs:__imp_KeInitializeGuardedMutex
0x1400800e0  nop     dword ptr [rax+rax+00h]
0x1400800e5  mov     cs:MRxSmbPerfCounterNetRootsPushLock, rbx
0x1400800ec  mov     rdx, rbx
0x1400800ef  mov     rcx, rbx
0x1400800f2  lea     r8, WPP_MAIN_CB.DeviceExtension
0x1400800f9  lea     rax, [rcx+r8]
0x1400800fd  mov     [rcx+r8+8], rax
0x140080102  mov     [rax], rax
0x140080105  add     rdx, r15
0x140080108  lea     rcx, [rcx+10h]
0x14008010c  cmp     rdx, 20h ; ' '
0x140080110  jnz     short loc_1400800F9
0x140080112  xor     edx, edx
0x140080114  lea     rcx, ?GlobalResource@@3U_FAST_ERESOURCE@@A; _FAST_ERESOURCE GlobalResource
0x14008011b  call    cs:__imp_ExInitializeFastResource
0x140080122  nop     dword ptr [rax+rax+00h]
0x140080127  mov     [rsp+328h+var_2D8], ebx
0x14008012b  mov     esi, r15d
0x14008012e  mov     [rsp+328h+var_2D0], r15d
0x140080133  mov     ecx, 0FFFFh; GroupNumber
0x140080138  call    cs:__imp_KeQueryMaximumProcessorCountEx
0x14008013f  nop     dword ptr [rax+rax+00h]
0x140080144  shl     eax, 8
0x140080147  mov     edx, eax
0x140080149  mov     ecx, 48h ; 'H'
0x14008014e  mov     r8d, 6D537250h
0x140080154  call    cs:__imp_ExAllocatePool2
0x14008015b  nop     dword ptr [rax+rax+00h]
0x140080160  mov     cs:MRxSmbLegacyPerfCtrs, rax
0x140080167  test    rax, rax
0x14008016a  jnz     short loc_1400801BE
0x14008016c  mov     ebx, 0C000009Ah
0x140080171  mov     [rsp+328h+var_2D8], ebx
0x140080175  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14008017c  lea     rax, WPP_GLOBAL_Control
0x140080183  cmp     rcx, rax
0x140080186  jz      loc_140080C2C
0x14008018c  mov     eax, [rcx+2Ch]
0x14008018f  test    r15b, al
0x140080192  jz      loc_140080C2C
0x140080198  cmp     [rcx+29h], r15b
0x14008019c  jb      loc_140080C2C
0x1400801a2  mov     edx, 0Eh
0x1400801a7  mov     r9d, 0C000009Ah
0x1400801ad  mov     r8, rdi
0x1400801b0  mov     rcx, [rcx+18h]
0x1400801b4  call    WPP_SF_d
0x1400801b9  jmp     loc_140080C2C
0x1400801be  call    RxCeInitializeCryptoSupport
0x1400801c3  mov     ebx, eax
0x1400801c5  mov     [rsp+328h+var_2D8], eax
0x1400801c9  test    eax, eax
0x1400801cb  jns     short loc_140080204
0x1400801cd  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400801d4  lea     rax, WPP_GLOBAL_Control
0x1400801db  cmp     rcx, rax
0x1400801de  jz      loc_140080C2C
0x1400801e4  mov     edx, [rcx+2Ch]
0x1400801e7  test    r15b, dl
0x1400801ea  jz      loc_140080C2C
0x1400801f0  cmp     [rcx+29h], r15b
0x1400801f4  jb      loc_140080C2C
0x1400801fa  mov     edx, 0Fh
0x1400801ff  mov     r9d, ebx
0x140080202  jmp     short loc_1400801AD
0x140080204  xor     edx, edx
0x140080206  lea     rcx, MRxSmbCipherSuiteOrderPushLock
0x14008020d  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140080214  nop     dword ptr [rax+rax+00h]
0x140080219  mov     [rsp+328h+var_2D4], r15b
0x14008021e  lea     rdx, word_14007D1AC
0x140080225  lea     rcx, dword_14007D19C
0x14008022c  call    MRxSmbInitDefaultCipherSuiteOrder
0x140080231  lea     r8, word_14007D1AC
0x140080238  lea     rdx, dword_14007D19C
0x14008023f  lea     rcx, aRegistryMachin_13; "\\Registry\\Machine\\Software\\Policies"...
0x140080246  call    SmbCryptoReadCipherSuiteOrderPolicySetting
0x14008024b  mov     ebx, eax
0x14008024d  mov     [rsp+328h+var_2D8], eax
0x140080251  mov     eax, 80000000h
0x140080256  lea     ecx, [rbx+rax]
0x140080259  mov     r15d, 0C0000034h
0x14008025f  test    eax, ecx
0x140080261  jnz     short loc_1400802B5
0x140080263  cmp     ebx, r15d
0x140080266  jz      short loc_1400802B5
0x140080268  cmp     ebx, 0C000090Bh
0x14008026e  jnz     short loc_14008027E
0x140080270  test    cs:byte_1400712C3, 10h
0x140080277  jz      short loc_14008027E
0x140080279  call    McTemplateK0z_EtwWriteTransfer
0x14008027e  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140080285  lea     r12, WPP_GLOBAL_Control
0x14008028c  cmp     rcx, r12
0x14008028f  jz      short loc_1400802BC
0x140080291  mov     eax, [rcx+2Ch]
0x140080294  test    sil, al
0x140080297  jz      short loc_1400802BC
0x140080299  cmp     [rcx+29h], r14b
0x14008029d  jb      short loc_1400802BC
0x14008029f  mov     edx, 10h
0x1400802a4  mov     r9d, ebx
0x1400802a7  mov     r8, rdi
0x1400802aa  mov     rcx, [rcx+18h]
0x1400802ae  call    WPP_SF_d
0x1400802b3  jmp     short loc_1400802BC
0x1400802b5  lea     r12, WPP_GLOBAL_Control
0x1400802bc  cmp     ebx, r15d
0x1400802bf  jnz     loc_1400803A9
0x1400802c5  mov     [rsp+328h+var_2B0], 20A0000h
0x1400802ce  lea     rax, [rsp+328h+var_248]
0x1400802d6  mov     [rsp+328h+var_2A8], rax
0x1400802de  lea     r8, [rsp+328h+var_2B0]
0x1400802e3  lea     rdx, aRegistryMachin_5; "\\Registry\\Machine\\System\\CurrentCon"...
0x1400802ea  lea     rcx, aLanmanworkstat; "LanmanWorkStationParameters"
  ... truncated ...
```
