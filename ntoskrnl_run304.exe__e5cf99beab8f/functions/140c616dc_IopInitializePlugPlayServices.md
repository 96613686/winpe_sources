# IopInitializePlugPlayServices

- ea: `0x140c616dc`
- end: `0x140c6287d`
- name: `IopInitializePlugPlayServices`
- size: `4513`
- prototype: ``
- caller_count: `1`
- callee_count: `86`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x140c5c6f4`

## callees

- `0x1403897b8`
- `0x140389890`
- `0x14038abc0`
- `0x14038ac4c`
- `0x14038ad08`
- `0x1403f2d50`
- `0x1403fc6a0`
- `0x14043c78c`
- `0x14043cbb0`
- `0x140455b74`
- `0x1404c34bc`
- `0x14051e7d0`
- `0x14051e888`
- `0x1405b8d00`
- `0x1405dfed4`
- `0x1406d9d70`
- `0x1406daa70`
- `0x1406dac30`
- `0x1406f4880`
- `0x140732ef0`
- `0x14074acc4`
- `0x140757dc0`
- `0x14075c230`
- `0x14075c2f0`
- `0x14075c408`
- `0x140765864`
- `0x1407658a4`
- `0x140766a68`
- `0x140766ee4`
- `0x140767018`
- `0x140767138`
- `0x140767218`
- `0x140767494`
- `0x140767c00`
- `0x1407f8ed8`
- `0x14087b818`
- `0x1408b9fc8`
- `0x1408c1b40`
- `0x1408d84e4`
- `0x1408d8f9c`
- `0x1408e1d34`
- `0x1408e2820`
- `0x1408ed540`
- `0x140950b80`
- `0x14095bf44`
- `0x14096c1c0`
- `0x14097499c`
- `0x140a76f80`
- `0x140aaa968`
- `0x140abecd4`

## import_xrefs

- `ext-ms-win-ntos-ksr-l1-1-7!KsrGetFirmwareInformation` at `0x140c627a8`
- `ext-ms-win-ntos-ksr-l1-1-7!KsrGetFirmwareInformation` at `0x140c627a8`

## string_xrefs

- `0x140c61c8e`: `RollbackActive`
- `0x140c61b21`: `FindBestConfigurationTimeout`
- `0x140c61bff`: `\Registry\Machine\System\Setup`

## pseudocode

```c
NTSTATUS __fastcall IopInitializePlugPlayServices(__int64 a1, __int64 a2)
{
  NTSTATUS result; // eax
  __int64 v4; // rcx
  __int64 v5; // rax
  _QWORD *v6; // rax
  NTSTATUS CachedContextBaseKey; // ebx
  __int16 v8; // ax
  __int16 v9; // cx
  HANDLE v10; // rbx
  KSPIN_LOCK *p_Policy; // rbx
  __int64 v12; // r14
  int RecordedStackTraceIndex; // eax
  unsigned __int16 v14; // si
  KSPIN_LOCK *v15; // rbx
  __int64 v16; // r14
  int v17; // eax
  unsigned __int16 v18; // si
  KSPIN_LOCK *v19; // rbx
  __int64 v20; // r14
  int v21; // eax
  unsigned __int16 v22; // si
  struct _DEVICE_OBJECT *v23; // rsi
  PDEVICE_OBJECT v24; // rcx
  PDEVICE_OBJECT v25; // rbx
  int v26; // ebx
  int v27; // eax
  __int64 v28; // rcx
  _BYTE v29[8]; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE Handle; // [rsp+48h] [rbp-B8h] BYREF
  PVOID v31; // [rsp+50h] [rbp-B0h] BYREF
  PDEVICE_OBJECT DeviceObject; // [rsp+58h] [rbp-A8h] BYREF
  PVOID P; // [rsp+60h] [rbp-A0h]
  __int128 v34; // [rsp+68h] [rbp-98h] BYREF
  int v35; // [rsp+78h] [rbp-88h] BYREF
  HANDLE KeyHandle; // [rsp+80h] [rbp-80h] BYREF
  UNICODE_STRING GuidString; // [rsp+88h] [rbp-78h] BYREF
  ULONG Disposition; // [rsp+98h] [rbp-68h] BYREF
  __int64 v39; // [rsp+A0h] [rbp-60h] BYREF
  PVOID v40; // [rsp+A8h] [rbp-58h]
  PVOID v41; // [rsp+B0h] [rbp-50h]
  HANDLE v42; // [rsp+B8h] [rbp-48h] BYREF
  _DWORD v43[2]; // [rsp+C0h] [rbp-40h] BYREF
  const wchar_t *v44; // [rsp+C8h] [rbp-38h]
  OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+D0h] [rbp-30h] BYREF
  UNICODE_STRING v46; // [rsp+100h] [rbp+0h]
  UNICODE_STRING DestinationString; // [rsp+110h] [rbp+10h]
  _BYTE v48[64]; // [rsp+120h] [rbp+20h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+160h] [rbp+60h] BYREF
  __int64 v50; // [rsp+170h] [rbp+70h]
  __int64 v51; // [rsp+178h] [rbp+78h]
  void *retaddr; // [rsp+1B8h] [rbp+B8h]

  v42 = 0;
  Handle = 0;
  v39 = 0;
  DeviceObject = 0;
  Disposition = 0;
  v35 = 0;
  v31 = 0;
  P = 0;
  v40 = 0;
  v41 = 0;
  KeyHandle = 0;
  v43[1] = 0;
  *(_DWORD *)(&GuidString.MaximumLength + 1) = 0;
  v29[0] = 0;
  v34 = 0;
  DestinationString = 0;
  v46 = 0;
  memset(&ObjectAttributes, 0, 44);
  if ( (_DWORD)a2 )
  {
    if ( (_DWORD)a2 != 1 )
      return -1073741584;
    v26 = 0;
    v27 = McGenEventRegister_EtwRegister(
            MS_KernelPnP_Provider,
            a2,
            &MS_KernelPnP_Provider_Context,
            &MS_KernelPnP_Provider_Context);
    PnpEtwHandle = MS_KernelPnP_Provider_Context;
    if ( v27 < 0 )
      v26 = v27;
    result = EtwRegister(&MS_KernelPnP_Rundown_Provider, PnpDiagRundownRegisterCallback, 0, &PnpRundownEtwHandle);
    if ( result >= 0 )
    {
      result = v26;
      if ( v26 >= 0 )
      {
        TlgRegisterAggregateProvider(&dword_140E0A4D8);
        TlgRegisterAggregateProvider(&dword_140E0A4A0);
        TraceLoggingRegisterEx_EtwRegister_EtwSetInformation(&dword_140E0A468, 0, 0);
        result = PiDcInit(1);
        if ( result >= 0 )
        {
          result = PiUEventInit(1);
          if ( result >= 0 )
          {
            v28 = *(_QWORD *)(a1 + 240);
            *(_QWORD *)&UserData.Size = 80;
            v51 = 8;
            UserData.Ptr = v28 + 136;
            v50 = v28 + 3864;
            PnpDiagnosticTrace(&KMPnPEvt_OsLoader_Time, 2u, &UserData);
            result = PiPnpRtlInit(1);
            if ( result >= 0 )
            {
              result = PiCslInitialize();
              if ( result >= 0 )
              {
                CachedContextBaseKey = PiDmaGuardInitialize(1);
                if ( CachedContextBaseKey < 0 )
                  return CachedContextBaseKey;
                DeviceObject = 0;
                if ( (int)KsrGetFirmwareInformation(&DeviceObject) < 0 )
                {
                  PnpKsrEnabled = 0;
                }
                else
                {
                  PnpKsrEnabled = 1;
                  result = PiKsrNotifyInitialize();
                  if ( result < 0 )
                    return result;
                }
                PnpRequestDeviceAction(*((PVOID *)IopRootDeviceNode + 4), 0, 0, 0);
                LOWORD(PnpShutdownEvent.Header.Lock) = 0;
                PnpShutdownEvent.Header.WaitListHead.Blink = &PnpShutdownEvent.Header.WaitListHead;
                PnpShutdownEvent.Header.WaitListHead.Flink = &PnpShutdownEvent.Header.WaitListHead;
                PnpShutdownEvent.Header.Size = 6;
                PnpShutdownEvent.Header.SignalState = 0;
                if ( (*(_DWORD *)(*(_QWORD *)(a1 + 240) + 132LL) & 0x400) == 0 )
                  PpInitializeBootDDB(a1, 1);
                return 0;
              }
            }
          }
        }
      }
    }
  }
  else
  {
    PnPInitialized = 0;
    PnpSystemHiveLimits = 80;
    dword_140E4C50C = 90;
    CmRegisterSystemHiveLimitCallback(a1, a2, &PnpSystemHiveLimits);
    PnpSystemHiveTooLarge = 0;
    ObjectAttributes.ObjectName = (PUNICODE_STRING)&PspActiveProcessLock.WaitBlockFill11[48];
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 576;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    if ( ZwCreateKey(&KeyHandle, 0xF003Fu, &ObjectAttributes, 0, 0, 0, &Disposition) >= 0 )
    {
      IopGetRegistryValue(KeyHandle);
      ZwClose(KeyHandle);
    }
    qword_140F82F08 = 0;
    qword_140F82EC8 = (__int64)&PnpDeviceCompletionQueue;
    *(_QWORD *)&PnpDeviceCompletionQueue = &PnpDeviceCompletionQueue;
    Semaphore.Header.WaitListHead.Blink = &Semaphore.Header.WaitListHead;
    Semaphore.Header.WaitListHead.Flink = &Semaphore.Header.WaitListHead;
    qword_140F82EE0 = (__int64)&qword_140F82ED8;
    qword_140F82ED8 = (__int64)&qword_140F82ED8;
    dword_140F82ED0 = 0;
    Semaphore.Header.Type = 5;
    Semaphore.Header.Size = 8;
    Semaphore.Header.SignalState = 0;
    Semaphore.Limit = 0x7FFFFFFF;
    PiInitFirmwareResources(a1);
    if ( (*(_DWORD *)(*(_QWORD *)(a1 + 240) + 132LL) & 0x400) == 0 )
      PpInitializeBootDDB(a1, 0);
    PipInitDeviceOverrideCache();
    *(_WORD *)&IoInvalidateBusRelationsWorkerLock.WaitBlockFill11[40] = 0;
    IoInvalidateBusRelationsWorkerLock.WaitBlock[1].WaitListEntry.Blink = &IoInvalidateBusRelationsWorkerLock.WaitBlock[1].WaitListEntry;
    IoInvalidateBusRelationsWorkerLock.WaitBlock[1].WaitListEntry.Flink = &IoInvalidateBusRelationsWorkerLock.WaitBlock[1].WaitListEntry;
    IoInvalidateBusRelationsWorkerLock.WaitBlockFill5[42] = 6;
    *(_DWORD *)&IoInvalidateBusRelationsWorkerLock.WaitBlockFill11[44] = 0;
    result = PiInitCacheGroupInformation();
    if ( result >= 0 )
    {
      PpRegistrySemaphore.Header.Type = 5;
      PpRegistrySemaphore.Header.SignalState = 1;
      PpRegistrySemaphore.Header.WaitListHead.Blink = &PpRegistrySemaphore.Header.WaitListHead;
      v4 = 0;
      PpRegistrySemaphore.Header.WaitListHead.Flink = &PpRegistrySemaphore.Header.WaitListHead;
      PpRegistrySemaphore.Limit = 1;
      PpRegistrySemaphore.Header.Size = 8;
      do
      {
        v5 = 16 * v4++;
        v6 = (_QWORD *)((char *)&IopLegacyBusInformationTable + v5);
        v6[1] = v6;
        *v6 = v6;
      }
      while ( v4 != 18 );
      IopInitializeResourceMap(a1);
      IopAllocateBootResourcesRoutine = (__int64)&IopReportBootResources;
      IopInitReservedResourceList = 0;
      PnpDefaultInterfaceType = 1;
      ArbInitializeOsInaccessibleRange((unsigned int)dword_140E320B8);
      CachedContextBaseKey = ArbLibraryInitialize();
      if ( CachedContextBaseKey < 0 )
        return CachedContextBaseKey;
      CachedContextBaseKey = IopPortInitialize();
      if ( CachedContextBaseKey < 0 )
        return CachedContextBaseKey;
      CachedContextBaseKey = IopMemInitialize();
      if ( CachedContextBaseKey < 0 )
        return CachedContextBaseKey;
      CachedContextBaseKey = IopDmaInitialize();
      if ( CachedContextBaseKey < 0 )
        return CachedContextBaseKey;
      CachedContextBaseKey = IopIrqInitialize();
      if ( CachedContextBaseKey < 0 )
        return CachedContextBaseKey;
      CachedContextBaseKey = IopBusNumberInitialize();
      if ( CachedContextBaseKey < 0 )
        return CachedContextBaseKey;
      CachedContextBaseKey = PiPnpRtlInit(0);
      if ( CachedContextBaseKey < 0 )
        return CachedContextBaseKey;
      PipMigratePnpState();
      CachedContextBaseKey = PiDmInit();
      if ( CachedContextBaseKey < 0 )
        return CachedContextBaseKey;
      CachedContextBaseKey = PnpCtxGetCachedContextBaseKey(*(_QWORD *)&PiPnpRtlCtx, 4, &v39);
      if ( CachedContextBaseKey < 0 )
        return CachedContextBaseKey;
      *((_QWORD *)&v34 + 1) = L"Control\\Pnp";
      LODWORD(v34) = 1572886;
      if ( (int)IopCreateRegistryKeyEx(&Handle, v39, &v34, 983103, 0, 0) < 0 )
        goto LABEL_39;
      if ( (int)IopGetRegistryValue(Handle) >= 0 )
      {
        if ( *((_DWORD *)v40 + 1) == 4 && *((_DWORD *)v40 + 3) == 4 )
          PnpBootOptions = *(_DWORD *)((char *)v40 + *((unsigned int *)v40 + 2));
        ExFreePoolWithTag(v40, 0);
      }
      if ( (int)IopGetRegistryValue(Handle) >= 0 )
      {
        if ( *((_DWORD *)v41 + 1) == 4 && *((_DWORD *)v41 + 3) == 4 )
          PnpFindBestConfigurationTimeout = *(_DWORD *)((char *)v41 + *((unsigned int *)v41 + 2));
        ExFreePoolWithTag(v41, 0);
      }
      LODWORD(v31) = 0;
      if ( (int)PnpGetRegistryDword(Handle, L"DmaGuardTestMode", &v31) >= 0 && (_DWORD)v31 == 1 )
        PipDmaGuardTestMode = 1;
      PiUEventProcessRegistry(Handle);
      LODWORD(v31) = 0;
      if ( (int)PnpGetRegistryDword(Handle, L"KEventNotificationLong", &v31) < 0 )
      {
        v8 = 5000;
      }
      else
      {
        v8 = (__int16)v31;
        v9 = 100;
        if ( (unsigned int)v31 < 0x64 || (v9 = -5536, (unsigned int)v31 > 0xEA60) )
        {
          PiNotifyLongRunningMs = v9;
LABEL_38:
          *(_QWORD *)&IoInvalidateBusRelationsWorkerLock.Timer.Processor = PipUpdateAsyncOptionsCallback;
          IoInvalidateBusRelationsWorkerLock.WaitBlock[0].WaitListEntry.Flink = (struct _LIST_ENTRY *)Handle;
          IoInvalidateBusRelationsWorkerLock.Timer.TimerListEntry.Blink = 0;
          PipUpdateAsyncOptionsCallback(Handle);
          Handle = 0;
LABEL_39:
          LODWORD(v34) = 4063292;
          *((_QWORD *)&v34 + 1) = L"\\Registry\\Machine\\System\\Setup";
          if ( (int)IopOpenRegistryKeyEx(&Handle, 0, &v34, 131097) >= 0 )
          {
            PipUpdateSetupInProgress(Handle);
            if ( (int)IopGetRegistryValue(Handle) >= 0 )
            {
              if ( *((_DWORD *)P + 1) == 4
                && *((_DWORD *)P + 3) == 4
                && *(_DWORD *)((char *)P + *((unsigned int *)P + 2)) )
              {
                PnpSetupUpgradeInProgress = 1;
              }
              ExFreePoolWithTag(P, 0);
            }
            if ( (int)IopGetRegistryValue(Handle) >= 0 )
            {
              if ( *((_DWORD *)P + 1) == 4
                && *((_DWORD *)P + 3) == 4
                && *(_DWORD *)((char *)P + *((unsigned int *)P + 2)) )
              {
                PnpSetupRollbackActiveInProgress = 1;
              }
              ExFreePoolWithTag(P, 0);
            }
            if ( PnpSetupInProgress || PnpSetupOOBEInProgress )
            {
              IoInvalidateBusRelationsWorkerLock.RelativeTimerBias = (unsigned __int64)PipUpdateSetupInProgressCallback;
              *(_QWORD *)&IoInvalidateBusRelationsWorkerLock.Timer.Header.Lock = Handle;
              IoInvalidateBusRelationsWorkerLock.Queue = 0;
              PipUpdateSetupInProgressNotify(Handle, 0);
            }
            else
            {
              ZwClose(Handle);
            }
            Handle = 0;
          }
          CachedContextBaseKey = PipHardwareConfigInit((GUID *)(*(_QWORD *)(a1 + 240) + 2568LL));
          if ( CachedContextBaseKey < 0 )
            return CachedContextBaseKey;
          PipCheckSystemFirmwareUpdated(v29);
          CachedContextBaseKey = PiDcInit(0);
          if ( CachedContextBaseKey < 0 )
            return CachedContextBaseKey;
          memset_0(v48, 0, sizeof(v48));
          CachedContextBaseKey = PiAuCreateUserSids(v48);
          if ( CachedContextBaseKey >= 0 )
          {
            CachedContextBaseKey = PiAuCreateStandardSecurityObject(v48);
            if ( CachedContextBaseKey >= 0 )
              CachedContextBaseKey = PiAuCreateLocalSystemSecurityObject(v48);
          }
          PiAuFreeUserSids(v48);
          if ( CachedContextBaseKey < 0 )
            return CachedContextBaseKey;
          CachedContextBaseKey = PiDqInit();
          if ( CachedContextBaseKey < 0 )
            return CachedContextBaseKey;
          CachedContextBaseKey = PpDevCfgInit();
          if ( CachedContextBaseKey < 0 )
            return CachedContextBaseKey;
          PipResetDevices();
          CachedContextBaseKey = CmCreateDevice(
                                   PiPnpRtlCtx,
                                   (unsigned int)L"HTREE\\ROOT\\0",
                                   983103,
                                   (unsigned int)&v42,
                                   0,
                                   0);
          if ( CachedContextBaseKey < 0 )
            return CachedContextBaseKey;
          v10 = v42;
          CmSetDeviceRegProp(
            PiPnpRtlCtx,
            (unsigned int)L"HTREE\\ROOT\\0",
            (_DWORD)v42,
            37,
            1,
            (__int64)L"{00000000-0000-0000-FFFF-FFFFFFFFFFFF}",
            78,
            0);
          v35 = 0;
          CmSetDeviceRegProp(PiPnpRtlCtx, (unsigned int)L"HTREE\\ROOT\\0", (_DWORD)v10, 11, 4, (__int64)&v35, 4, 0);
          ZwClose(v10);
          qword_140F82F28 = (__int64)&IopPendingEjects;
          IopPendingEjects = (__int64)&IopPendingEjects;
          qword_140F82F38 = (__int64)&IopPendingSurpriseRemovals;
          IopPendingSurpriseRemovals = &IopPendingSurpriseRemovals;
          if ( (unsigned __int64)&IopDeviceTreeLock < 0xFFFF800000000000uLL
            || MmDeterminePoolType(&IopDeviceTreeLock) == 256 )
          {
            ExpTraceLogBadResourceAddress(&IopDeviceTreeLock, retaddr);
          }
          memset_0(&IopDeviceTreeLock.OwnerTable, 0, 0x50u);
          IopDeviceTreeLock.SystemResourcesList.Blink = (struct _LIST_ENTRY *)&IopDeviceTreeLock;
          IopDeviceTreeLock.SystemResourcesList.Flink = (struct _LIST_ENTRY *)&IopDeviceTreeLock;
          IopDeviceTreeLock.SharedWaiters = 0;
          IopDeviceTreeLock.ExclusiveWaiters = 0;
          IopDeviceTreeLock.SpinLock = 0;
          if ( (NtGlobalFlag & 0x2000) != 0 )
          {
            p_Policy = (KSPIN_LOCK *)&NormalizationListLock.SchedulingGroup->Policy;
            if ( NormalizationListLock.SchedulingGroup
              && (v12 = RtlStdLogStackTrace((PKSPIN_LOCK)&NormalizationListLock.SchedulingGroup->Policy)) != 0 )
            {
              RecordedStackTraceIndex = RtlpStdGetRecordedStackTraceIndex(p_Policy);
              v14 = RecordedStackTraceIndex;
              if ( !RecordedStackTraceIndex )
                RtlStdReleaseStackTrace(p_Policy, v12);
            }
            else
            {
              v14 = 0;
            }
            IopDeviceTreeLock.CreatorBackTraceIndex = v14;
          }
          else
          {
            IopDeviceTreeLock.CreatorBackTraceIndex = 0;
          }
          HIDWORD(IopDeviceTreeLock.Reserved2) = -1;
          ExpAddResourceToSystemResourceList(&IopDeviceTreeLock);
          __incgsdword(0x6498u);
          if ( (dword_140FBEC44 & 0x20000) != 0 )
            PerfLogExecutiveResourceInitialize(65544, &IopDeviceTreeLock, 0, 0);
          if ( (unsigned __int64)&IopSurpriseRemoveListLock < 0xFFFF800000000000uLL
            || MmDeterminePoolType(&IopSurpriseRemoveListLock) == 256 )
          {
            ExpTraceLogBadResourceAddress(&IopSurpriseRemoveListLock, retaddr);
          }
          memset_0(&IopSurpriseRemoveListLock.OwnerTable, 0, 0x50u);
          IopSurpriseRemoveListLock.SystemResourcesList.Blink = (struct _LIST_ENTRY *)&IopSurpriseRemoveListLock;
          IopSurpriseRemoveListLock.SystemResourcesList.Flink = (struct _LIST_ENTRY *)&IopSurpriseRemoveListLock;
          IopSurpriseRemoveListLock.SharedWaiters = 0;
          IopSurpriseRemoveListLock.ExclusiveWaiters = 0;
          IopSurpriseRemoveListLock.SpinLock = 0;
          if ( (NtGlobalFlag & 0x2000) != 0 )
          {
            v15 = (KSPIN_LOCK *)&NormalizationListLock.SchedulingGroup->Policy;
            if ( NormalizationListLock.SchedulingGroup
              && (v16 = RtlStdLogStackTrace((PKSPIN_LOCK)&NormalizationListLock.SchedulingGroup->Policy)) != 0 )
            {
              v17 = RtlpStdGetRecordedStackTraceIndex(v15);
              v18 = v17;
              if ( !v17 )
                RtlStdReleaseStackTrace(v15, v16);
            }
            else
            {
              v18 = 0;
            }
            IopSurpriseRemoveListLock.CreatorBackTraceIndex = v18;
          }
          else
          {
            IopSurpriseRemoveListLock.CreatorBackTraceIndex = 0;
          }
          HIDWORD(IopSurpriseRemoveListLock.Reserved2) = -1;
          ExpAddResourceToSystemResourceList(&IopSurpriseRemoveListLock);
          __incgsdword(0x6498u);
          if ( (dword_140FBEC44 & 0x20000) != 0 )
            PerfLogExecutiveResourceInitialize(65544, &IopSurpriseRemoveListLock, 0, 0);
          if ( (unsigned __int64)&PiEngineLock < 0xFFFF800000000000uLL || MmDeterminePoolType(&PiEngineLock) == 256 )
            ExpTraceLogBadResourceAddress(&PiEngineLock, retaddr);
          memset_0(&PiEngineLock.OwnerTable, 0, 0x50u);
          PiEngineLock.SystemResourcesList.Blink = (struct _LIST_ENTRY *)&PiEngineLock;
          PiEngineLock.SystemResourcesList.Flink = (struct _LIST_ENTRY *)&PiEngineLock;
          PiEngineLock.SharedWaiters = 0;
          PiEngineLock.ExclusiveWaiters = 0;
          PiEngineLock.SpinLock = 0;
          if ( (NtGlobalFlag & 0x2000) != 0 )
          {
            v19 = (KSPIN_LOCK *)&NormalizationListLock.SchedulingGroup->Policy;
            if ( NormalizationListLock.SchedulingGroup
              && (v20 = RtlStdLogStackTrace((PKSPIN_LOCK)&NormalizationListLock.SchedulingGroup->Policy)) != 0 )
            {
              v21 = RtlpStdGetRecordedStackTraceIndex(v19);
              v22 = v21;
              if ( !v21 )
                RtlStdReleaseStackTrace(v19, v20);
            }
            else
            {
              v22 = 0;
            }
            PiEngineLock.CreatorBackTraceIndex = v22;
          }
          else
          {
            PiEngineLock.CreatorBackTraceIndex = 0;
          }
          HIDWORD(PiEngineLock.Reserved2) = -1;
          ExpAddResourceToSystemResourceList(&PiEngineLock);
          __incgsdword(0x6498u);
          if ( (dword_140FBEC44 & 0x20000) != 0 )
            PerfLogExecutiveResourceInitialize(65544, &PiEngineLock, 0, 0);
          PnpSpinLock = 0;
          PiResourceListLock.Event.Header.WaitListHead.Blink = &PiResourceListLock.Event.Header.WaitListHead;
          PiResourceListLock.Event.Header.WaitListHead.Flink = &PiResourceListLock.Event.Header.WaitListHead;
          PnpRebuildPowerRelationsQueueLock.Event.Header.WaitListHead.Blink = &PnpRebuildPowerRelationsQueueLock.Event.Header.WaitListHead;
          PnpRebuildPowerRelationsQueueLock.Event.Header.WaitListHead.Flink = &PnpRebuildPowerRelationsQueueLock.Event.Header.WaitListHead;
          PiResourceListLock.Count = 1;
          PiResourceListLock.Owner = 0;
          PiResourceListLock.Contention = 0;
          LOWORD(PiResourceListLock.Event.Header.Lock) = 1;
          PiResourceListLock.Event.Header.Size = 6;
          PiResourceListLock.Event.Header.SignalState = 0;
          PnpRebuildPowerRelationsQueueLock.Count = 1;
          PnpRebuildPowerRelationsQueueLock.Owner = 0;
          PnpRebuildPowerRelationsQueueLock.Contention = 0;
          LOWORD(PnpRebuildPowerRelationsQueueLock.Event.Header.Lock) = 1;
          PnpRebuildPowerRelationsQueueLock.Event.Header.Size = 6;
          PnpRebuildPowerRelationsQueueLock.Event.Header.SignalState = 0;
          CachedContextBaseKey = PiDeviceDependencyInit();
          if ( CachedContextBaseKey < 0 )
            return CachedContextBaseKey;
          _InterlockedExchange64((volatile __int64 *)&PnpDeviceActionThread, 0);
          PnpEnumerationInProgress = 0;
          PnpEnumerationLock.Header.WaitListHead.Blink = &PnpEnumerationLock.Header.WaitListHead;
          PnpEnumerationLock.Header.WaitListHead.Flink = &PnpEnumerationLock.Header.WaitListHead;
          qword_140F81928 = (__int64)&PnpEnumerationRequestList;
          PnpEnumerationRequestList = (__int64)&PnpEnumerationRequestList;
          qword_140F818C8 = (__int64)&PiProfileDeviceListHead;
          PiProfileDeviceListHead = (__int64)&PiProfileDeviceListHead;
          PiProfileDeviceListLock.Event.Header.WaitListHead.Blink = &PiProfileDeviceListLock.Event.Header.WaitListHead;
          PiProfileDeviceListLock.Event.Header.WaitListHead.Flink = &PiProfileDeviceListLock.Event.Header.WaitListHead;
          PiProfileChangeSemaphore.Header.WaitListHead.Blink = &PiProfileChangeSemaphore.Header.WaitListHead;
          PiProfileChangeSemaphore.Header.WaitListHead.Flink = &PiProfileChangeSemaphore.Header.WaitListHead;
          IopWarmEjectLock.Header.WaitListHead.Blink = &IopWarmEjectLock.Header.WaitListHead;
          IopWarmEjectLock.Header.WaitListHead.Flink = &IopWarmEjectLock.Header.WaitListHead;
          *((_QWORD *)&v34 + 1) = L"\\Driver\\PnpManager";
          LOWORD(PnpEnumerationLock.Header.Lock) = 0;
          PnpEnumerationLock.Header.Size = 6;
          PnpEnumerationLock.Header.SignalState = 1;
          PiProfileDeviceListLock.Count = 1;
          PiProfileDeviceListLock.Owner = 0;
          PiProfileDeviceListLock.Contention = 0;
          LOWORD(PiProfileDeviceListLock.Event.Header.Lock) = 1;
          PiProfileDeviceListLock.Event.Header.Size = 6;
          PiProfileDeviceListLock.Event.Header.SignalState = 0;
          PiProfileDeviceCount = 0;
          PiProfileChangeSemaphore.Header.Type = 5;
          PiProfileChangeSemaphore.Header.Size = 8;
          PiProfileChangeSemaphore.Header.SignalState = 1;
          PiProfileChangeSemaphore.Limit = 1;
          IopWarmEjectPdo = 0;
          LOWORD(IopWarmEjectLock.Header.Lock) = 1;
          IopWarmEjectLock.Header.Size = 6;
          IopWarmEjectLock.Header.SignalState = 1;
          LODWORD(v34) = 2490404;
          CachedContextBaseKey = IoCreateDriver(&v34, PipPnPDriverEntry);
          if ( CachedContextBaseKey < 0 )
            return CachedContextBaseKey;
          CachedContextBaseKey = IoCreateDevice(PnpDriverObject, 0, 0, 4u, 0, 0, &DeviceObject);
          if ( CachedContextBaseKey < 0 )
            return CachedContextBaseKey;
          v23 = DeviceObject;
          v24 = DeviceObject;
          DeviceObject->Flags |= 0x1000u;
          CachedContextBaseKey = PipAllocateDeviceNode(v24, &IopRootDeviceNode);
          if ( IopRootDeviceNode )
          {
            PipSetDevNodeFlags(IopRootDeviceNode, 305);
            PipSetDevNodeUserFlags(IopRootDeviceNode, 10);
            *((_DWORD *)IopRootDeviceNode + 165) = -2;
            CachedContextBaseKey = PnpAllocateDeviceInstancePath(IopRootDeviceNode, 26);
            if ( CachedContextBaseKey >= 0 )
            {
              v44 = L"HTREE\\ROOT\\0";
              v43[0] = 1703960;
              PnpCopyDeviceInstancePath(IopRootDeviceNode, v43);
              CachedContextBaseKey = PnpMapDeviceObjectToDeviceInstance(
                                       *((_QWORD *)IopRootDeviceNode + 4),
                                       (char *)IopRootDeviceNode + 40);
              if ( CachedContextBaseKey >= 0 )
              {
                *(_DWORD *)&GuidString.Length = 5111884;
                GuidString.Buffer = L"{00000000-0000-0000-FFFF-FFFFFFFFFFFF}";
                RtlGUIDFromString(&GuidString, (GUID *)((char *)IopRootDeviceNode + 664));
                PnpQueryAndSaveDeviceNodeCapabilities(IopRootDeviceNode);
                PipSetDevNodeState(IopRootDeviceNode, 778);
LABEL_110:
                CachedContextBaseKey = CmAddDeviceToContainer(
                                         PiPnpRtlCtx,
                                         (unsigned int)L"{00000000-0000-0000-FFFF-FFFFFFFFFFFF}",
                                         (unsigned int)L"{00000000-0000-0000-FFFF-FFFFFFFFFFFF}",
                                         (unsigned int)L"HTREE\\ROOT\\0",
                                         0);
                if ( CachedContextBaseKey >= 0 )
                {
                  if ( v29[0] )
                    PiDcHandleSystemFirmwareUpdate();
                  DeviceObject = 0;
                  if ( (int)PnpOpenCCSPnpRegKey(&DeviceObject) >= 0 )
                  {
                    v25 = DeviceObject;
                    LODWORD(v31) = 0;
                    if ( (int)PnpGetRegistryDword(DeviceObject, L"WatchdogBugcheckEnabled", &v31) < 0 )
                      PnpWatchdogBugcheckConfig = 2;
                    else
                      PnpWatchdogBugcheckConfig = (_DWORD)v31 != 0;
                    PnpQueryWatchdogTimeoutConfiguration(v25);
                    ZwClose(v25);
                  }
                  CachedContextBaseKey = PnpInitializeDeviceEvents();
                  if ( CachedContextBaseKey >= 0 )
                  {
                    PnpInitializeNotification();
                    CachedContextBaseKey = PnpBusTypeGuidInitialize();
                    if ( CachedContextBaseKey >= 0 )
                    {
                      LOWORD(PnpReplaceEvent.Header.Lock) = 1;
                      PnpReplaceEvent.Header.WaitListHead.Blink = &PnpReplaceEvent.Header.WaitListHead;
                      PnpReplaceEvent.Header.WaitListHead.Flink = &PnpReplaceEvent.Header.WaitListHead;
                      PnpReplaceEvent.Header.Size = 6;
                      PnpReplaceEvent.Header.SignalState = 1;
                      CachedContextBaseKey = PiSwInit();
                      if ( CachedContextBaseKey >= 0 )
                      {
                        CachedContextBaseKey = PiUEventInit(0);
                        if ( CachedContextBaseKey >= 0 )
                        {
                          *(_QWORD *)&GuidString.Length = 2359330;
                          GuidString.Buffer = L"\\Driver\\DeviceApi";
                          CachedContextBaseKey = IoCreateDriver(&GuidString, PiDaDriverEntry);
                          if ( CachedContextBaseKey >= 0 )
                          {
                            CachedContextBaseKey = PiDmaGuardInitialize(0);
                            if ( CachedContextBaseKey >= 0 )
                            {
                              IoInvalidateBusRelationsLock = 0;
                              qword_140F839E8 = (__int64)&IoInvalidateBusRelationsQueue;
                              IoInvalidateBusRelationsQueue = (__int64)&IoInvalidateBusRelationsQueue;
                              IoInvalidateBusRelationsWorkItem.WorkerRoutine = (void (__fastcall *)(void *))IoInvalidateBusRelationsWorker;
                              *(_QWORD *)&IoInvalidateBusRelationsWorkerLock.Header.Lock = 0;
                              IoInvalidateBusRelationsWorkItem.Parameter = 0;
                              IoInvalidateBusRelationsWorkItem.List.Flink = 0;
                              if ( (int)PipProcessPendingServices() >= 0 )
                                PipProcessPendingOsExtensionResources();
                              PnpRequestDeviceAction(*((PVOID *)IopRootDeviceNode + 4), 0, 0, 0);
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
          else
          {
            IoDeleteDevice(v23);
            IoDeleteDriver(PnpDriverObject);
            if ( CachedContextBaseKey >= 0 )
              goto LABEL_110;
          }
          return CachedContextBaseKey;
        }
      }
      PiNotifyLongRunningMs = v8;
      goto LABEL_38;
    }
  }
  return result;
}

```

## disassembly

```asm
0x140c616dc  mov     [rsp-8+arg_8], rbx
0x140c616e1  mov     [rsp-8+arg_10], rsi
0x140c616e6  push    rbp
0x140c616e7  push    rdi
0x140c616e8  push    r12
0x140c616ea  push    r13
0x140c616ec  push    r14
0x140c616ee  lea     rbp, [rsp-90h]
0x140c616f6  sub     rsp, 190h
0x140c616fd  mov     rax, cs:__security_cookie
0x140c61704  xor     rax, rsp
0x140c61707  mov     [rbp+0B0h+var_30], rax
0x140c6170e  xor     r12d, r12d
0x140c61711  xorps   xmm0, xmm0
0x140c61714  xor     eax, eax
0x140c61716  mov     [rbp+0B0h+var_F8], r12
0x140c6171a  mov     [rsp+1B0h+Handle], r12
0x140c6171f  xorps   xmm1, xmm1
0x140c61722  mov     [rbp+0B0h+var_110], r12
0x140c61726  mov     rsi, rcx
0x140c61729  mov     [rsp+1B0h+DeviceObject], r12
0x140c6172e  mov     [rbp+0B0h+var_118], r12d
0x140c61732  mov     [rsp+1B0h+var_138], r12d
0x140c61737  mov     [rsp+1B0h+var_160], r12
0x140c6173c  mov     [rsp+1B0h+P], r12
0x140c61741  mov     [rbp+0B0h+var_108], r12
0x140c61745  mov     [rbp+0B0h+var_100], r12
0x140c61749  mov     [rbp+0B0h+KeyHandle], r12
0x140c6174d  mov     [rbp+0B0h+var_EC], r12d
0x140c61751  mov     dword ptr [rbp+0B0h+GuidString+4], r12d
0x140c61755  mov     [rsp+1B0h+var_170], r12b
0x140c6175a  movups  xmmword ptr [rbp+0B0h+ObjectAttributes.ObjectName], xmm0
0x140c6175e  movups  xmmword ptr [rbp+0B0h+ObjectAttributes+1Ch], xmm0
0x140c61762  movups  [rsp+1B0h+var_148], xmm0
0x140c61767  movups  xmmword ptr [rbp+0B0h+DestinationString.Length], xmm1
0x140c6176b  movups  xmmword ptr [rbp+0B0h+var_B0.Length], xmm0
0x140c6176f  movups  xmmword ptr [rbp+0B0h+ObjectAttributes.Length], xmm0
0x140c61773  test    edx, edx
0x140c61775  jnz     loc_140C62682
0x140c6177b  lea     r8, PnpSystemHiveLimits
0x140c61782  mov     cs:PnPInitialized, r12b
0x140c61789  mov     cs:PnpSystemHiveLimits, 50h ; 'P'
0x140c61793  mov     cs:dword_140E4C50C, 5Ah ; 'Z'
0x140c6179d  call    CmRegisterSystemHiveLimitCallback
0x140c617a2  lea     rax, PspActiveProcessLock.___u33+30h
0x140c617a9  mov     cs:PnpSystemHiveTooLarge, r12b
0x140c617b0  mov     [rbp+0B0h+ObjectAttributes.ObjectName], rax
0x140c617b4  lea     r8, [rbp+0B0h+ObjectAttributes]; ObjectAttributes
0x140c617b8  lea     rax, [rbp+0B0h+var_118]
0x140c617bc  mov     [rbp+0B0h+ObjectAttributes.Length], 30h ; '0'
0x140c617c3  mov     [rsp+1B0h+Disposition], rax; Disposition
0x140c617c8  lea     rcx, [rbp+0B0h+KeyHandle]; KeyHandle
0x140c617cc  xorps   xmm0, xmm0
0x140c617cf  mov     [rsp+1B0h+CreateOptions], r12d; CreateOptions
0x140c617d4  mov     r13d, 0F003Fh
0x140c617da  mov     [rsp+1B0h+Class], r12; Class
0x140c617df  xor     r9d, r9d; TitleIndex
0x140c617e2  mov     [rbp+0B0h+ObjectAttributes.RootDirectory], r12
0x140c617e6  mov     edx, r13d; DesiredAccess
0x140c617e9  mov     [rbp+0B0h+ObjectAttributes.Attributes], 240h
0x140c617f0  movdqu  xmmword ptr [rbp+0B0h+ObjectAttributes.SecurityDescriptor], xmm0
0x140c617f5  call    ZwCreateKey
0x140c617fa  test    eax, eax
0x140c617fc  js      loc_140C618A4
0x140c61802  mov     rcx, [rbp+0B0h+KeyHandle]; KeyHandle
0x140c61806  lea     r9, [rsp+1B0h+var_160]
0x140c6180b  xor     r8d, r8d
0x140c6180e  lea     rdx, aOldsystembiosd; "OldSystemBiosDate"
0x140c61815  call    IopGetRegistryValue
0x140c6181a  test    eax, eax
0x140c6181c  js      short loc_140C6189B
0x140c6181e  mov     rbx, [rsp+1B0h+var_160]
0x140c61823  test    rbx, rbx
0x140c61826  jz      short loc_140C6189B
0x140c61828  mov     rcx, [rbp+0B0h+KeyHandle]; KeyHandle
0x140c6182c  lea     r9, [rsp+1B0h+P]
0x140c61831  xor     r8d, r8d
0x140c61834  lea     rdx, aSystembiosdate; "SystemBiosDate"
0x140c6183b  call    IopGetRegistryValue
0x140c61840  test    eax, eax
0x140c61842  js      short loc_140C61891
0x140c61844  mov     rdi, [rsp+1B0h+P]
0x140c61849  test    rdi, rdi
0x140c6184c  jz      short loc_140C61891
0x140c6184e  mov     edx, [rbx+8]
0x140c61851  lea     rcx, [rbp+0B0h+DestinationString]; DestinationString
0x140c61855  add     rdx, rbx; SourceString
0x140c61858  call    RtlInitUnicodeString
0x140c6185d  mov     edx, [rdi+8]
0x140c61860  lea     rcx, [rbp+0B0h+var_B0]; DestinationString
0x140c61864  add     rdx, rdi; SourceString
0x140c61867  call    RtlInitUnicodeString
0x140c6186c  xor     r9d, r9d
0x140c6186f  mov     dword ptr [rsp+1B0h+Class], r12d
0x140c61874  mov     r8d, 4000002Ch
0x140c6187a  lea     rdx, [rbp+0B0h+var_B0]
0x140c6187e  lea     rcx, [rbp+0B0h+DestinationString]
0x140c61882  call    PnpLogEvent
0x140c61887  xor     edx, edx; Tag
0x140c61889  mov     rcx, rdi; P
0x140c6188c  call    ExFreePoolWithTag
0x140c61891  xor     edx, edx; Tag
0x140c61893  mov     rcx, rbx; P
0x140c61896  call    ExFreePoolWithTag
0x140c6189b  mov     rcx, [rbp+0B0h+KeyHandle]; Handle
0x140c6189f  call    ZwClose
0x140c618a4  lea     rax, PnpDeviceCompletionQueue
0x140c618ab  mov     cs:qword_140F82F08, r12
0x140c618b2  mov     cs:qword_140F82EC8, rax
0x140c618b9  mov     rcx, rsi
0x140c618bc  mov     cs:PnpDeviceCompletionQueue, rax
0x140c618c3  lea     rax, Semaphore.Header.WaitListHead
0x140c618ca  mov     cs:Semaphore.Header.WaitListHead.Blink, rax
0x140c618d1  mov     cs:Semaphore.Header.WaitListHead.Flink, rax
0x140c618d8  lea     rax, qword_140F82ED8
0x140c618df  mov     cs:qword_140F82EE0, rax
0x140c618e6  mov     cs:qword_140F82ED8, rax
0x140c618ed  mov     cs:dword_140F82ED0, r12d
0x140c618f4  mov     byte ptr cs:Semaphore.Header, 5
0x140c618fb  mov     byte ptr cs:Semaphore.Header+2, 8
0x140c61902  mov     cs:Semaphore.Header.SignalState, r12d
0x140c61909  mov     cs:Semaphore.Limit, 7FFFFFFFh
0x140c61913  call    PiInitFirmwareResources
0x140c61918  mov     rax, [rsi+0F0h]
0x140c6191f  test    dword ptr [rax+84h], 400h
0x140c61929  jnz     short loc_140C61935
0x140c6192b  xor     edx, edx
0x140c6192d  mov     rcx, rsi
0x140c61930  call    PpInitializeBootDDB
0x140c61935  call    PipInitDeviceOverrideCache
0x140c6193a  lea     rax, IoInvalidateBusRelationsWorkerLock.___u33+30h
0x140c61941  mov     word ptr cs:IoInvalidateBusRelationsWorkerLock.___u33+28h, r12w
0x140c61949  mov     qword ptr cs:IoInvalidateBusRelationsWorkerLock.___u33+38h, rax
0x140c61950  mov     qword ptr cs:IoInvalidateBusRelationsWorkerLock.___u33+30h, rax
0x140c61957  mov     byte ptr cs:IoInvalidateBusRelationsWorkerLock.___u33+2Ah, 6
0x140c6195e  mov     dword ptr cs:IoInvalidateBusRelationsWorkerLock.___u33+2Ch, r12d
0x140c61965  call    PiInitCacheGroupInformation
0x140c6196a  test    eax, eax
0x140c6196c  js      loc_140C62851
0x140c61972  mov     edi, 1
0x140c61977  mov     byte ptr cs:PpRegistrySemaphore.Header, 5
0x140c6197e  lea     rax, PpRegistrySemaphore.Header.WaitListHead
0x140c61985  mov     cs:PpRegistrySemaphore.Header.SignalState, edi
0x140c6198b  mov     cs:PpRegistrySemaphore.Header.WaitListHead.Blink, rax
0x140c61992  mov     rcx, r12
0x140c61995  mov     cs:PpRegistrySemaphore.Header.WaitListHead.Flink, rax
0x140c6199c  mov     cs:PpRegistrySemaphore.Limit, edi
0x140c619a2  mov     byte ptr cs:PpRegistrySemaphore.Header+2, 8
0x140c619a9  mov     rax, rcx
0x140c619ac  lea     rdx, IopLegacyBusInformationTable
0x140c619b3  shl     rax, 4
0x140c619b7  add     rcx, rdi
0x140c619ba  add     rax, rdx
0x140c619bd  mov     [rax+8], rax
0x140c619c1  mov     [rax], rax
0x140c619c4  cmp     rcx, 12h
0x140c619c8  jnz     short loc_140C619A9
0x140c619ca  mov     rcx, rsi
0x140c619cd  call    IopInitializeResourceMap
0x140c619d2  mov     ecx, cs:dword_140E320B8
0x140c619d8  lea     rax, IopReportBootResources
0x140c619df  mov     cs:IopAllocateBootResourcesRoutine, rax
0x140c619e6  mov     cs:IopInitReservedResourceList, r12
0x140c619ed  mov     cs:PnpDefaultInterfaceType, edi
0x140c619f3  call    ArbInitializeOsInaccessibleRange
0x140c619f8  call    ArbLibraryInitialize
0x140c619fd  mov     ebx, eax
0x140c619ff  test    eax, eax
0x140c61a01  js      loc_140C6284F
0x140c61a07  call    IopPortInitialize
0x140c61a0c  mov     ebx, eax
0x140c61a0e  test    eax, eax
0x140c61a10  js      loc_140C6284F
0x140c61a16  call    IopMemInitialize
0x140c61a1b  mov     ebx, eax
0x140c61a1d  test    eax, eax
0x140c61a1f  js      loc_140C6284F
0x140c61a25  call    IopDmaInitialize
0x140c61a2a  mov     ebx, eax
0x140c61a2c  test    eax, eax
0x140c61a2e  js      loc_140C6284F
0x140c61a34  call    IopIrqInitialize
0x140c61a39  mov     ebx, eax
0x140c61a3b  test    eax, eax
0x140c61a3d  js      loc_140C6284F
0x140c61a43  call    IopBusNumberInitialize
0x140c61a48  mov     ebx, eax
0x140c61a4a  test    eax, eax
0x140c61a4c  js      loc_140C6284F
0x140c61a52  xor     ecx, ecx
0x140c61a54  call    PiPnpRtlInit
0x140c61a59  mov     ebx, eax
0x140c61a5b  test    eax, eax
0x140c61a5d  js      loc_140C6284F
0x140c61a63  call    PipMigratePnpState
0x140c61a68  call    PiDmInit
0x140c61a6d  mov     ebx, eax
0x140c61a6f  test    eax, eax
0x140c61a71  js      loc_140C6284F
0x140c61a77  mov     rcx, cs:PiPnpRtlCtx
0x140c61a7e  lea     r8, [rbp+0B0h+var_110]
0x140c61a82  mov     r14d, 4
0x140c61a88  mov     edx, r14d
0x140c61a8b  call    _PnpCtxGetCachedContextBaseKey
0x140c61a90  mov     ebx, eax
0x140c61a92  test    eax, eax
0x140c61a94  js      loc_140C6284F
0x140c61a9a  mov     rdx, [rbp+0B0h+var_110]
0x140c61a9e  lea     rax, aControlPnp; "Control\\Pnp"
0x140c61aa5  mov     qword ptr [rsp+1B0h+CreateOptions], r12
0x140c61aaa  lea     r8, [rsp+1B0h+var_148]
0x140c61aaf  mov     r9d, r13d
0x140c61ab2  mov     qword ptr [rsp+1B0h+var_148+8], rax
0x140c61ab7  lea     rcx, [rsp+1B0h+Handle]
0x140c61abc  mov     dword ptr [rsp+1B0h+var_148], 180016h
0x140c61ac4  mov     dword ptr [rsp+1B0h+Class], r12d
0x140c61ac9  call    IopCreateRegistryKeyEx
0x140c61ace  test    eax, eax
0x140c61ad0  js      loc_140C61BFF
0x140c61ad6  mov     rcx, [rsp+1B0h+Handle]; KeyHandle
0x140c61adb  lea     r9, [rbp+0B0h+var_108]
0x140c61adf  xor     r8d, r8d
0x140c61ae2  lea     rdx, aBootoptions; "BootOptions"
0x140c61ae9  call    IopGetRegistryValue
0x140c61aee  test    eax, eax
0x140c61af0  js      short loc_140C61B15
0x140c61af2  mov     rcx, [rbp+0B0h+var_108]; P
0x140c61af6  cmp     [rcx+4], r14d
0x140c61afa  jnz     short loc_140C61B0E
0x140c61afc  cmp     [rcx+0Ch], r14d
0x140c61b00  jnz     short loc_140C61B0E
0x140c61b02  mov     eax, [rcx+8]
0x140c61b05  mov     edx, [rax+rcx]
0x140c61b08  mov     cs:PnpBootOptions, edx
0x140c61b0e  xor     edx, edx; Tag
0x140c61b10  call    ExFreePoolWithTag
0x140c61b15  mov     rcx, [rsp+1B0h+Handle]; KeyHandle
0x140c61b1a  lea     r9, [rbp+0B0h+var_100]
0x140c61b1e  xor     r8d, r8d
0x140c61b21  lea     rdx, aFindbestconfig; "FindBestConfigurationTimeout"
0x140c61b28  call    IopGetRegistryValue
0x140c61b2d  test    eax, eax
0x140c61b2f  js      short loc_140C61B54
0x140c61b31  mov     rcx, [rbp+0B0h+var_100]; P
0x140c61b35  cmp     [rcx+4], r14d
0x140c61b39  jnz     short loc_140C61B4D
0x140c61b3b  cmp     [rcx+0Ch], r14d
0x140c61b3f  jnz     short loc_140C61B4D
0x140c61b41  mov     eax, [rcx+8]
0x140c61b44  mov     edx, [rax+rcx]
0x140c61b47  mov     cs:PnpFindBestConfigurationTimeout, edx
0x140c61b4d  xor     edx, edx; Tag
0x140c61b4f  call    ExFreePoolWithTag
0x140c61b54  mov     rcx, [rsp+1B0h+Handle]
0x140c61b59  lea     r8, [rsp+1B0h+var_160]
0x140c61b5e  lea     rdx, aDmaguardtestmo; "DmaGuardTestMode"
0x140c61b65  mov     dword ptr [rsp+1B0h+var_160], r12d
0x140c61b6a  call    PnpGetRegistryDword
0x140c61b6f  test    eax, eax
0x140c61b71  js      short loc_140C61B80
0x140c61b73  cmp     dword ptr [rsp+1B0h+var_160], edi
0x140c61b77  jnz     short loc_140C61B80
0x140c61b79  mov     cs:PipDmaGuardTestMode, dil
0x140c61b80  mov     rcx, [rsp+1B0h+Handle]
0x140c61b85  call    PiUEventProcessRegistry
0x140c61b8a  mov     rcx, [rsp+1B0h+Handle]
0x140c61b8f  lea     r8, [rsp+1B0h+var_160]
0x140c61b94  lea     rdx, aKeventnotifica; "KEventNotificationLong"
0x140c61b9b  mov     dword ptr [rsp+1B0h+var_160], r12d
0x140c61ba0  call    PnpGetRegistryDword
0x140c61ba5  test    eax, eax
0x140c61ba7  js      short loc_140C61BC8
0x140c61ba9  mov     eax, dword ptr [rsp+1B0h+var_160]
0x140c61bad  mov     ecx, 64h ; 'd'
0x140c61bb2  cmp     eax, ecx
0x140c61bb4  jb      short loc_140C61BBF
0x140c61bb6  mov     ecx, 0EA60h
0x140c61bbb  cmp     eax, ecx
0x140c61bbd  jbe     short loc_140C61BCD
0x140c61bbf  mov     cs:PiNotifyLongRunningMs, cx
0x140c61bc6  jmp     short loc_140C61BD4
0x140c61bc8  mov     eax, 1388h
0x140c61bcd  mov     cs:PiNotifyLongRunningMs, ax
0x140c61bd4  mov     rcx, [rsp+1B0h+Handle]; Handle
0x140c61bd9  lea     rax, PipUpdateAsyncOptionsCallback
0x140c61be0  mov     qword ptr cs:IoInvalidateBusRelationsWorkerLock.Timer.Processor, rax
0x140c61be7  mov     qword ptr cs:IoInvalidateBusRelationsWorkerLock.___u33, rcx
0x140c61bee  mov     cs:IoInvalidateBusRelationsWorkerLock.Timer.TimerListEntry.Blink, r12
0x140c61bf5  call    PipUpdateAsyncOptionsCallback
0x140c61bfa  mov     [rsp+1B0h+Handle], r12
0x140c61bff  lea     rax, aRegistryMachin_223; "\\Registry\\Machine\\System\\Setup"
0x140c61c06  mov     dword ptr [rsp+1B0h+var_148], 3E003Ch
0x140c61c0e  mov     r9d, 20019h
0x140c61c14  mov     qword ptr [rsp+1B0h+var_148+8], rax
0x140c61c19  lea     r8, [rsp+1B0h+var_148]
0x140c61c1e  xor     edx, edx
0x140c61c20  lea     rcx, [rsp+1B0h+Handle]
0x140c61c25  call    IopOpenRegistryKeyEx
0x140c61c2a  test    eax, eax
0x140c61c2c  js      loc_140C61D11
  ... truncated ...
```
