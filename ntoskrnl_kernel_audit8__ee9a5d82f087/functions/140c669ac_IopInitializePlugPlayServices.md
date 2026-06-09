# IopInitializePlugPlayServices

- ea: `0x140c669ac`
- end: `0x140c67b4d`
- name: `IopInitializePlugPlayServices`
- size: `4513`
- prototype: ``
- caller_count: `1`
- callee_count: `86`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x140c619c4`

## callees

- `0x1402df930`
- `0x1402e00b8`
- `0x1403ce2d0`
- `0x1403e0160`
- `0x1403e01ec`
- `0x1403e02a8`
- `0x140403380`
- `0x1404519bc`
- `0x140451de0`
- `0x1404671c4`
- `0x1404d2e3c`
- `0x140525560`
- `0x140525618`
- `0x1405bf9f0`
- `0x1405e6ab4`
- `0x1406dc8c0`
- `0x1406dd5c0`
- `0x1406dd780`
- `0x1406f7380`
- `0x1407376b0`
- `0x14074f1c4`
- `0x14075c230`
- `0x1407606a0`
- `0x140760760`
- `0x140760878`
- `0x140769cd4`
- `0x140769d14`
- `0x14076aed8`
- `0x14076b354`
- `0x14076b488`
- `0x14076b5a8`
- `0x14076b688`
- `0x14076b904`
- `0x14076c070`
- `0x1407fbcd8`
- `0x14086a27c`
- `0x14087852c`
- `0x1408eeed8`
- `0x1408f6a50`
- `0x14090d2c4`
- `0x14090dd7c`
- `0x140916af4`
- `0x1409175e0`
- `0x140949670`
- `0x140979f10`
- `0x14097a6d0`
- `0x140a47be8`
- `0x140a4b070`
- `0x140a7dbf4`
- `0x140a95b68`

## import_xrefs

- `ext-ms-win-ntos-ksr-l1-1-7!KsrGetFirmwareInformation` at `0x140c67a78`
- `ext-ms-win-ntos-ksr-l1-1-7!KsrGetFirmwareInformation` at `0x140c67a78`

## string_xrefs

- `0x140c66df1`: `FindBestConfigurationTimeout`
- `0x140c66ecf`: `\Registry\Machine\System\Setup`
- `0x140c66f5e`: `RollbackActive`

## pseudocode

```c
int __fastcall IopInitializePlugPlayServices(__int64 a1, __int64 a2)
{
  int result; // eax
  __int64 v4; // rcx
  __int64 v5; // rax
  __int64 *v6; // rax
  NTSTATUS CachedContextBaseKey; // ebx
  __int16 v8; // ax
  __int16 v9; // cx
  HANDLE v10; // rbx
  KSPIN_LOCK *v11; // rbx
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
        TlgRegisterAggregateProvider(&dword_140E0A4A0);
        TlgRegisterAggregateProvider(&dword_140E0A468);
        TraceLoggingRegisterEx_EtwRegister_EtwSetInformation(&dword_140E0A4D8, 0, 0);
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
    dword_140E4C4AC = 90;
    CmRegisterSystemHiveLimitCallback(a1, a2, &PnpSystemHiveLimits);
    PnpSystemHiveTooLarge = 0;
    ObjectAttributes.ObjectName = &CmRegistryMachineHardwareDescriptionSystemName;
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 576;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    if ( ZwCreateKey(&KeyHandle, 0xF003Fu, &ObjectAttributes, 0, 0, 0, &Disposition) >= 0 )
    {
      IopGetRegistryValue(KeyHandle);
      ZwClose(KeyHandle);
    }
    qword_140F82CA8 = 0;
    qword_140F82C68 = (__int64)&PnpDeviceCompletionQueue;
    *(_QWORD *)&PnpDeviceCompletionQueue = &PnpDeviceCompletionQueue;
    Semaphore.Header.WaitListHead.Blink = &Semaphore.Header.WaitListHead;
    Semaphore.Header.WaitListHead.Flink = &Semaphore.Header.WaitListHead;
    qword_140F82C80 = (__int64)&qword_140F82C78;
    qword_140F82C78 = (__int64)&qword_140F82C78;
    dword_140F82C70 = 0;
    Semaphore.Header.Type = 5;
    Semaphore.Header.Size = 8;
    Semaphore.Header.SignalState = 0;
    Semaphore.Limit = 0x7FFFFFFF;
    PiInitFirmwareResources(a1);
    if ( (*(_DWORD *)(*(_QWORD *)(a1 + 240) + 132LL) & 0x400) == 0 )
      PpInitializeBootDDB(a1, 0);
    PipInitDeviceOverrideCache();
    LOWORD(PnpSystemDeviceEnumerationComplete.Header.Lock) = 0;
    PnpSystemDeviceEnumerationComplete.Header.WaitListHead.Blink = &PnpSystemDeviceEnumerationComplete.Header.WaitListHead;
    PnpSystemDeviceEnumerationComplete.Header.WaitListHead.Flink = &PnpSystemDeviceEnumerationComplete.Header.WaitListHead;
    PnpSystemDeviceEnumerationComplete.Header.Size = 6;
    PnpSystemDeviceEnumerationComplete.Header.SignalState = 0;
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
        v5 = 2 * v4++;
        v6 = &IopLegacyBusInformationTable[v5];
        v6[1] = (__int64)v6;
        *v6 = (__int64)v6;
      }
      while ( v4 != 18 );
      IopInitializeResourceMap(a1);
      IopAllocateBootResourcesRoutine = (__int64)&IopReportBootResources;
      IopInitReservedResourceList = 0;
      PnpDefaultInterfaceType = 1;
      ArbInitializeOsInaccessibleRange((unsigned int)dword_140E32078);
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
          qword_140F838B0 = (__int64)PipUpdateAsyncOptionsCallback;
          qword_140F838B8 = (__int64)Handle;
          *(_QWORD *)PnpAsyncOptionsWorkItem = 0;
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
              qword_140F83870 = (__int64)PipUpdateSetupInProgressCallback;
              qword_140F83878 = (__int64)Handle;
              *(_QWORD *)PnpSetupWorkItem = 0;
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
          qword_140F82E88 = (__int64)&IopPendingEjects;
          IopPendingEjects = (__int64)&IopPendingEjects;
          qword_140F82F18 = (__int64)&IopPendingSurpriseRemovals;
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
            v11 = RtlpStackTraceDatabase;
            if ( RtlpStackTraceDatabase && (v12 = RtlStdLogStackTrace(RtlpStackTraceDatabase)) != 0 )
            {
              RecordedStackTraceIndex = RtlpStdGetRecordedStackTraceIndex(v11);
              v14 = RecordedStackTraceIndex;
              if ( !RecordedStackTraceIndex )
                RtlStdReleaseStackTrace(v11, v12);
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
          if ( (*(_DWORD *)byte_140FBEC44 & 0x20000) != 0 )
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
            v15 = RtlpStackTraceDatabase;
            if ( RtlpStackTraceDatabase && (v16 = RtlStdLogStackTrace(RtlpStackTraceDatabase)) != 0 )
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
          if ( (*(_DWORD *)byte_140FBEC44 & 0x20000) != 0 )
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
            v19 = RtlpStackTraceDatabase;
            if ( RtlpStackTraceDatabase && (v20 = RtlStdLogStackTrace(RtlpStackTraceDatabase)) != 0 )
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
          if ( (*(_DWORD *)byte_140FBEC44 & 0x20000) != 0 )
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
          qword_140F816D8 = (__int64)&PnpEnumerationRequestList;
          PnpEnumerationRequestList = (__int64)&PnpEnumerationRequestList;
          qword_140F815E8 = (__int64)&PiProfileDeviceListHead;
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
                              qword_140F83798 = (__int64)&IoInvalidateBusRelationsQueue;
                              IoInvalidateBusRelationsQueue = (__int64)&IoInvalidateBusRelationsQueue;
                              IoInvalidateBusRelationsWorkItem.WorkerRoutine = (void (__fastcall *)(void *))IoInvalidateBusRelationsWorker;
                              IoInvalidateBusRelationsWorkerLock = 0;
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
0x140c669ac  mov     [rsp-8+arg_8], rbx
0x140c669b1  mov     [rsp-8+arg_10], rsi
0x140c669b6  push    rbp
0x140c669b7  push    rdi
0x140c669b8  push    r12
0x140c669ba  push    r13
0x140c669bc  push    r14
0x140c669be  lea     rbp, [rsp-90h]
0x140c669c6  sub     rsp, 190h
0x140c669cd  mov     rax, cs:__security_cookie
0x140c669d4  xor     rax, rsp
0x140c669d7  mov     [rbp+0B0h+var_30], rax
0x140c669de  xor     r12d, r12d
0x140c669e1  xorps   xmm0, xmm0
0x140c669e4  xor     eax, eax
0x140c669e6  mov     [rbp+0B0h+var_F8], r12
0x140c669ea  mov     [rsp+1B0h+Handle], r12
0x140c669ef  xorps   xmm1, xmm1
0x140c669f2  mov     [rbp+0B0h+var_110], r12
0x140c669f6  mov     rsi, rcx
0x140c669f9  mov     [rsp+1B0h+DeviceObject], r12
0x140c669fe  mov     [rbp+0B0h+var_118], r12d
0x140c66a02  mov     [rsp+1B0h+var_138], r12d
0x140c66a07  mov     [rsp+1B0h+var_160], r12
0x140c66a0c  mov     [rsp+1B0h+P], r12
0x140c66a11  mov     [rbp+0B0h+var_108], r12
0x140c66a15  mov     [rbp+0B0h+var_100], r12
0x140c66a19  mov     [rbp+0B0h+KeyHandle], r12
0x140c66a1d  mov     [rbp+0B0h+var_EC], r12d
0x140c66a21  mov     dword ptr [rbp+0B0h+GuidString+4], r12d
0x140c66a25  mov     [rsp+1B0h+var_170], r12b
0x140c66a2a  movups  xmmword ptr [rbp+0B0h+ObjectAttributes.ObjectName], xmm0
0x140c66a2e  movups  xmmword ptr [rbp+0B0h+ObjectAttributes+1Ch], xmm0
0x140c66a32  movups  [rsp+1B0h+var_148], xmm0
0x140c66a37  movups  xmmword ptr [rbp+0B0h+DestinationString.Length], xmm1
0x140c66a3b  movups  xmmword ptr [rbp+0B0h+var_B0.Length], xmm0
0x140c66a3f  movups  xmmword ptr [rbp+0B0h+ObjectAttributes.Length], xmm0
0x140c66a43  test    edx, edx
0x140c66a45  jnz     loc_140C67952
0x140c66a4b  lea     r8, PnpSystemHiveLimits
0x140c66a52  mov     cs:PnPInitialized, r12b
0x140c66a59  mov     cs:PnpSystemHiveLimits, 50h ; 'P'
0x140c66a63  mov     cs:dword_140E4C4AC, 5Ah ; 'Z'
0x140c66a6d  call    CmRegisterSystemHiveLimitCallback
0x140c66a72  lea     rax, CmRegistryMachineHardwareDescriptionSystemName
0x140c66a79  mov     cs:PnpSystemHiveTooLarge, r12b
0x140c66a80  mov     [rbp+0B0h+ObjectAttributes.ObjectName], rax
0x140c66a84  lea     r8, [rbp+0B0h+ObjectAttributes]; ObjectAttributes
0x140c66a88  lea     rax, [rbp+0B0h+var_118]
0x140c66a8c  mov     [rbp+0B0h+ObjectAttributes.Length], 30h ; '0'
0x140c66a93  mov     [rsp+1B0h+Disposition], rax; Disposition
0x140c66a98  lea     rcx, [rbp+0B0h+KeyHandle]; KeyHandle
0x140c66a9c  xorps   xmm0, xmm0
0x140c66a9f  mov     [rsp+1B0h+CreateOptions], r12d; CreateOptions
0x140c66aa4  mov     r13d, 0F003Fh
0x140c66aaa  mov     [rsp+1B0h+Class], r12; Class
0x140c66aaf  xor     r9d, r9d; TitleIndex
0x140c66ab2  mov     [rbp+0B0h+ObjectAttributes.RootDirectory], r12
0x140c66ab6  mov     edx, r13d; DesiredAccess
0x140c66ab9  mov     [rbp+0B0h+ObjectAttributes.Attributes], 240h
0x140c66ac0  movdqu  xmmword ptr [rbp+0B0h+ObjectAttributes.SecurityDescriptor], xmm0
0x140c66ac5  call    ZwCreateKey
0x140c66aca  test    eax, eax
0x140c66acc  js      loc_140C66B74
0x140c66ad2  mov     rcx, [rbp+0B0h+KeyHandle]; KeyHandle
0x140c66ad6  lea     r9, [rsp+1B0h+var_160]
0x140c66adb  xor     r8d, r8d
0x140c66ade  lea     rdx, aOldsystembiosd; "OldSystemBiosDate"
0x140c66ae5  call    IopGetRegistryValue
0x140c66aea  test    eax, eax
0x140c66aec  js      short loc_140C66B6B
0x140c66aee  mov     rbx, [rsp+1B0h+var_160]
0x140c66af3  test    rbx, rbx
0x140c66af6  jz      short loc_140C66B6B
0x140c66af8  mov     rcx, [rbp+0B0h+KeyHandle]; KeyHandle
0x140c66afc  lea     r9, [rsp+1B0h+P]
0x140c66b01  xor     r8d, r8d
0x140c66b04  lea     rdx, aSystembiosdate; "SystemBiosDate"
0x140c66b0b  call    IopGetRegistryValue
0x140c66b10  test    eax, eax
0x140c66b12  js      short loc_140C66B61
0x140c66b14  mov     rdi, [rsp+1B0h+P]
0x140c66b19  test    rdi, rdi
0x140c66b1c  jz      short loc_140C66B61
0x140c66b1e  mov     edx, [rbx+8]
0x140c66b21  lea     rcx, [rbp+0B0h+DestinationString]; DestinationString
0x140c66b25  add     rdx, rbx; SourceString
0x140c66b28  call    RtlInitUnicodeString
0x140c66b2d  mov     edx, [rdi+8]
0x140c66b30  lea     rcx, [rbp+0B0h+var_B0]; DestinationString
0x140c66b34  add     rdx, rdi; SourceString
0x140c66b37  call    RtlInitUnicodeString
0x140c66b3c  xor     r9d, r9d
0x140c66b3f  mov     dword ptr [rsp+1B0h+Class], r12d
0x140c66b44  mov     r8d, 4000002Ch
0x140c66b4a  lea     rdx, [rbp+0B0h+var_B0]
0x140c66b4e  lea     rcx, [rbp+0B0h+DestinationString]
0x140c66b52  call    PnpLogEvent
0x140c66b57  xor     edx, edx; Tag
0x140c66b59  mov     rcx, rdi; P
0x140c66b5c  call    ExFreePoolWithTag
0x140c66b61  xor     edx, edx; Tag
0x140c66b63  mov     rcx, rbx; P
0x140c66b66  call    ExFreePoolWithTag
0x140c66b6b  mov     rcx, [rbp+0B0h+KeyHandle]; Handle
0x140c66b6f  call    ZwClose
0x140c66b74  lea     rax, PnpDeviceCompletionQueue
0x140c66b7b  mov     cs:qword_140F82CA8, r12
0x140c66b82  mov     cs:qword_140F82C68, rax
0x140c66b89  mov     rcx, rsi
0x140c66b8c  mov     cs:PnpDeviceCompletionQueue, rax
0x140c66b93  lea     rax, Semaphore.Header.WaitListHead
0x140c66b9a  mov     cs:Semaphore.Header.WaitListHead.Blink, rax
0x140c66ba1  mov     cs:Semaphore.Header.WaitListHead.Flink, rax
0x140c66ba8  lea     rax, qword_140F82C78
0x140c66baf  mov     cs:qword_140F82C80, rax
0x140c66bb6  mov     cs:qword_140F82C78, rax
0x140c66bbd  mov     cs:dword_140F82C70, r12d
0x140c66bc4  mov     byte ptr cs:Semaphore.Header, 5
0x140c66bcb  mov     byte ptr cs:Semaphore.Header+2, 8
0x140c66bd2  mov     cs:Semaphore.Header.SignalState, r12d
0x140c66bd9  mov     cs:Semaphore.Limit, 7FFFFFFFh
0x140c66be3  call    PiInitFirmwareResources
0x140c66be8  mov     rax, [rsi+0F0h]
0x140c66bef  test    dword ptr [rax+84h], 400h
0x140c66bf9  jnz     short loc_140C66C05
0x140c66bfb  xor     edx, edx
0x140c66bfd  mov     rcx, rsi
0x140c66c00  call    PpInitializeBootDDB
0x140c66c05  call    PipInitDeviceOverrideCache
0x140c66c0a  lea     rax, PnpSystemDeviceEnumerationComplete.Header.WaitListHead
0x140c66c11  mov     word ptr cs:PnpSystemDeviceEnumerationComplete.Header, r12w
0x140c66c19  mov     cs:PnpSystemDeviceEnumerationComplete.Header.WaitListHead.Blink, rax
0x140c66c20  mov     cs:PnpSystemDeviceEnumerationComplete.Header.WaitListHead.Flink, rax
0x140c66c27  mov     byte ptr cs:PnpSystemDeviceEnumerationComplete.Header+2, 6
0x140c66c2e  mov     cs:PnpSystemDeviceEnumerationComplete.Header.SignalState, r12d
0x140c66c35  call    PiInitCacheGroupInformation
0x140c66c3a  test    eax, eax
0x140c66c3c  js      loc_140C67B21
0x140c66c42  mov     edi, 1
0x140c66c47  mov     byte ptr cs:PpRegistrySemaphore.Header, 5
0x140c66c4e  lea     rax, PpRegistrySemaphore.Header.WaitListHead
0x140c66c55  mov     cs:PpRegistrySemaphore.Header.SignalState, edi
0x140c66c5b  mov     cs:PpRegistrySemaphore.Header.WaitListHead.Blink, rax
0x140c66c62  mov     rcx, r12
0x140c66c65  mov     cs:PpRegistrySemaphore.Header.WaitListHead.Flink, rax
0x140c66c6c  mov     cs:PpRegistrySemaphore.Limit, edi
0x140c66c72  mov     byte ptr cs:PpRegistrySemaphore.Header+2, 8
0x140c66c79  mov     rax, rcx
0x140c66c7c  lea     rdx, IopLegacyBusInformationTable
0x140c66c83  shl     rax, 4
0x140c66c87  add     rcx, rdi
0x140c66c8a  add     rax, rdx
0x140c66c8d  mov     [rax+8], rax
0x140c66c91  mov     [rax], rax
0x140c66c94  cmp     rcx, 12h
0x140c66c98  jnz     short loc_140C66C79
0x140c66c9a  mov     rcx, rsi
0x140c66c9d  call    IopInitializeResourceMap
0x140c66ca2  mov     ecx, cs:dword_140E32078
0x140c66ca8  lea     rax, IopReportBootResources
0x140c66caf  mov     cs:IopAllocateBootResourcesRoutine, rax
0x140c66cb6  mov     cs:IopInitReservedResourceList, r12
0x140c66cbd  mov     cs:PnpDefaultInterfaceType, edi
0x140c66cc3  call    ArbInitializeOsInaccessibleRange
0x140c66cc8  call    ArbLibraryInitialize
0x140c66ccd  mov     ebx, eax
0x140c66ccf  test    eax, eax
0x140c66cd1  js      loc_140C67B1F
0x140c66cd7  call    IopPortInitialize
0x140c66cdc  mov     ebx, eax
0x140c66cde  test    eax, eax
0x140c66ce0  js      loc_140C67B1F
0x140c66ce6  call    IopMemInitialize
0x140c66ceb  mov     ebx, eax
0x140c66ced  test    eax, eax
0x140c66cef  js      loc_140C67B1F
0x140c66cf5  call    IopDmaInitialize
0x140c66cfa  mov     ebx, eax
0x140c66cfc  test    eax, eax
0x140c66cfe  js      loc_140C67B1F
0x140c66d04  call    IopIrqInitialize
0x140c66d09  mov     ebx, eax
0x140c66d0b  test    eax, eax
0x140c66d0d  js      loc_140C67B1F
0x140c66d13  call    IopBusNumberInitialize
0x140c66d18  mov     ebx, eax
0x140c66d1a  test    eax, eax
0x140c66d1c  js      loc_140C67B1F
0x140c66d22  xor     ecx, ecx
0x140c66d24  call    PiPnpRtlInit
0x140c66d29  mov     ebx, eax
0x140c66d2b  test    eax, eax
0x140c66d2d  js      loc_140C67B1F
0x140c66d33  call    PipMigratePnpState
0x140c66d38  call    PiDmInit
0x140c66d3d  mov     ebx, eax
0x140c66d3f  test    eax, eax
0x140c66d41  js      loc_140C67B1F
0x140c66d47  mov     rcx, cs:PiPnpRtlCtx
0x140c66d4e  lea     r8, [rbp+0B0h+var_110]
0x140c66d52  mov     r14d, 4
0x140c66d58  mov     edx, r14d
0x140c66d5b  call    _PnpCtxGetCachedContextBaseKey
0x140c66d60  mov     ebx, eax
0x140c66d62  test    eax, eax
0x140c66d64  js      loc_140C67B1F
0x140c66d6a  mov     rdx, [rbp+0B0h+var_110]
0x140c66d6e  lea     rax, aControlPnp; "Control\\Pnp"
0x140c66d75  mov     qword ptr [rsp+1B0h+CreateOptions], r12
0x140c66d7a  lea     r8, [rsp+1B0h+var_148]
0x140c66d7f  mov     r9d, r13d
0x140c66d82  mov     qword ptr [rsp+1B0h+var_148+8], rax
0x140c66d87  lea     rcx, [rsp+1B0h+Handle]
0x140c66d8c  mov     dword ptr [rsp+1B0h+var_148], 180016h
0x140c66d94  mov     dword ptr [rsp+1B0h+Class], r12d
0x140c66d99  call    IopCreateRegistryKeyEx
0x140c66d9e  test    eax, eax
0x140c66da0  js      loc_140C66ECF
0x140c66da6  mov     rcx, [rsp+1B0h+Handle]; KeyHandle
0x140c66dab  lea     r9, [rbp+0B0h+var_108]
0x140c66daf  xor     r8d, r8d
0x140c66db2  lea     rdx, aBootoptions; "BootOptions"
0x140c66db9  call    IopGetRegistryValue
0x140c66dbe  test    eax, eax
0x140c66dc0  js      short loc_140C66DE5
0x140c66dc2  mov     rcx, [rbp+0B0h+var_108]; P
0x140c66dc6  cmp     [rcx+4], r14d
0x140c66dca  jnz     short loc_140C66DDE
0x140c66dcc  cmp     [rcx+0Ch], r14d
0x140c66dd0  jnz     short loc_140C66DDE
0x140c66dd2  mov     eax, [rcx+8]
0x140c66dd5  mov     edx, [rax+rcx]
0x140c66dd8  mov     cs:PnpBootOptions, edx
0x140c66dde  xor     edx, edx; Tag
0x140c66de0  call    ExFreePoolWithTag
0x140c66de5  mov     rcx, [rsp+1B0h+Handle]; KeyHandle
0x140c66dea  lea     r9, [rbp+0B0h+var_100]
0x140c66dee  xor     r8d, r8d
0x140c66df1  lea     rdx, aFindbestconfig; "FindBestConfigurationTimeout"
0x140c66df8  call    IopGetRegistryValue
0x140c66dfd  test    eax, eax
0x140c66dff  js      short loc_140C66E24
0x140c66e01  mov     rcx, [rbp+0B0h+var_100]; P
0x140c66e05  cmp     [rcx+4], r14d
0x140c66e09  jnz     short loc_140C66E1D
0x140c66e0b  cmp     [rcx+0Ch], r14d
0x140c66e0f  jnz     short loc_140C66E1D
0x140c66e11  mov     eax, [rcx+8]
0x140c66e14  mov     edx, [rax+rcx]
0x140c66e17  mov     cs:PnpFindBestConfigurationTimeout, edx
0x140c66e1d  xor     edx, edx; Tag
0x140c66e1f  call    ExFreePoolWithTag
0x140c66e24  mov     rcx, [rsp+1B0h+Handle]
0x140c66e29  lea     r8, [rsp+1B0h+var_160]
0x140c66e2e  lea     rdx, aDmaguardtestmo; "DmaGuardTestMode"
0x140c66e35  mov     dword ptr [rsp+1B0h+var_160], r12d
0x140c66e3a  call    PnpGetRegistryDword
0x140c66e3f  test    eax, eax
0x140c66e41  js      short loc_140C66E50
0x140c66e43  cmp     dword ptr [rsp+1B0h+var_160], edi
0x140c66e47  jnz     short loc_140C66E50
0x140c66e49  mov     cs:PipDmaGuardTestMode, dil
0x140c66e50  mov     rcx, [rsp+1B0h+Handle]
0x140c66e55  call    PiUEventProcessRegistry
0x140c66e5a  mov     rcx, [rsp+1B0h+Handle]
0x140c66e5f  lea     r8, [rsp+1B0h+var_160]
0x140c66e64  lea     rdx, aKeventnotifica; "KEventNotificationLong"
0x140c66e6b  mov     dword ptr [rsp+1B0h+var_160], r12d
0x140c66e70  call    PnpGetRegistryDword
0x140c66e75  test    eax, eax
0x140c66e77  js      short loc_140C66E98
0x140c66e79  mov     eax, dword ptr [rsp+1B0h+var_160]
0x140c66e7d  mov     ecx, 64h ; 'd'
0x140c66e82  cmp     eax, ecx
0x140c66e84  jb      short loc_140C66E8F
0x140c66e86  mov     ecx, 0EA60h
0x140c66e8b  cmp     eax, ecx
0x140c66e8d  jbe     short loc_140C66E9D
0x140c66e8f  mov     cs:PiNotifyLongRunningMs, cx
0x140c66e96  jmp     short loc_140C66EA4
0x140c66e98  mov     eax, 1388h
0x140c66e9d  mov     cs:PiNotifyLongRunningMs, ax
0x140c66ea4  mov     rcx, [rsp+1B0h+Handle]; Handle
0x140c66ea9  lea     rax, PipUpdateAsyncOptionsCallback
0x140c66eb0  mov     cs:qword_140F838B0, rax
0x140c66eb7  mov     cs:qword_140F838B8, rcx
0x140c66ebe  mov     cs:PnpAsyncOptionsWorkItem, r12
0x140c66ec5  call    PipUpdateAsyncOptionsCallback
0x140c66eca  mov     [rsp+1B0h+Handle], r12
0x140c66ecf  lea     rax, aRegistryMachin_222; "\\Registry\\Machine\\System\\Setup"
0x140c66ed6  mov     dword ptr [rsp+1B0h+var_148], 3E003Ch
0x140c66ede  mov     r9d, 20019h
0x140c66ee4  mov     qword ptr [rsp+1B0h+var_148+8], rax
0x140c66ee9  lea     r8, [rsp+1B0h+var_148]
0x140c66eee  xor     edx, edx
0x140c66ef0  lea     rcx, [rsp+1B0h+Handle]
0x140c66ef5  call    IopOpenRegistryKeyEx
0x140c66efa  test    eax, eax
0x140c66efc  js      loc_140C66FE1
  ... truncated ...
```
