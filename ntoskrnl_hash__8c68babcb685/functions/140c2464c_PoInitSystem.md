# PoInitSystem

- ea: `0x140c2464c`
- end: `0x140c259fc`
- name: `PoInitSystem`
- size: `5040`
- prototype: `bool __fastcall(__int64, __int64)`
- caller_count: `3`
- callee_count: `123`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x140c52ae4`
- `0x140c53f38`
- `0x140c619c4`

## callees

- `0x1402bd880`
- `0x1402df930`
- `0x1402e00b8`
- `0x140311130`
- `0x1403111a0`
- `0x14035498c`
- `0x140355790`
- `0x140356a68`
- `0x140367c90`
- `0x14039099c`
- `0x1403ce040`
- `0x1403ce9f8`
- `0x1403e0160`
- `0x1403e01ec`
- `0x1403e02a8`
- `0x1403f1040`
- `0x1404ba5bc`
- `0x1404c0ff0`
- `0x140516b34`
- `0x140525560`
- `0x140525618`
- `0x140529870`
- `0x14058a970`
- `0x140602d5c`
- `0x140602db8`
- `0x14060967c`
- `0x140609f14`
- `0x1406dc8c0`
- `0x1406ddfc0`
- `0x1406e1000`
- `0x1406eb0e0`
- `0x1406f7380`
- `0x140733438`
- `0x140738c34`
- `0x14077e530`
- `0x14078a3e0`
- `0x14078a43c`
- `0x14078a510`
- `0x14078a550`
- `0x14078a590`
- `0x14078a5d0`
- `0x14078a610`
- `0x14078a64c`
- `0x14078a6dc`
- `0x14078a71c`
- `0x14078a75c`
- `0x14078ab68`
- `0x14078abbc`
- `0x14078b170`
- `0x14078b908`

## import_xrefs

- `ext-ms-win-kmpdc-l1-1-0!PdcTaskClientRegister` at `0x140c25589`
- `ext-ms-win-kmpdc-l1-1-0!PdcTaskClientRegister` at `0x140c25589`

## pseudocode

```c
bool __fastcall PoInitSystem(__int64 a1, __int64 a2)
{
  int TimebrokerServiceSid; // eax
  __int64 v4; // r8
  __int64 v5; // r8
  __int64 v6; // r8
  __int64 v7; // r8
  __int64 v8; // r8
  unsigned int v9; // ecx
  KSPIN_LOCK *v10; // rsi
  unsigned __int16 v11; // r14
  __int64 v12; // r12
  int RecordedStackTraceIndex; // eax
  __int64 v14; // rbx
  unsigned __int64 v15; // rsi
  __int64 v16; // rcx
  __int64 i; // r11
  __int64 v18; // rax
  __int64 v19; // r11
  __int64 j; // rcx
  __int64 v21; // rdx
  __int64 v22; // r8
  __int64 v23; // r9
  __int64 v24; // rcx
  __int64 v25; // rdx
  __int64 v26; // r8
  __int64 v27; // r9
  __int64 v28; // rdx
  __int64 v29; // rcx
  __int64 v30; // r8
  __int64 v31; // rcx
  __int64 *k; // rbx
  int IsEnabledDeviceUsageNoInline; // eax
  __int64 v34; // rdx
  __int64 v35; // rcx
  int v36; // ebx
  char v37; // si
  int v38; // eax
  __int64 v39; // rdx
  __int64 v40; // rcx
  __int64 v41; // r8
  __int64 v42; // rdx
  __int64 v43; // rcx
  __int64 v44; // r8
  __int64 v45; // r9
  __int64 v46; // rdx
  __int64 v47; // rdx
  __int64 v48; // rcx
  __int64 v49; // r8
  __int64 v50; // rdx
  __int64 v51; // rcx
  __int64 v52; // r8
  __int64 v53; // rcx
  __int64 v54; // r8
  __int64 v55; // r9
  __int64 v56; // rdx
  __int64 v57; // rdx
  __int64 v58; // rcx
  __int64 v59; // r8
  bool v60; // al
  LARGE_INTEGER PerformanceFrequency; // [rsp+40h] [rbp-89h] BYREF
  int v63; // [rsp+48h] [rbp-81h] BYREF
  _OWORD v64[2]; // [rsp+50h] [rbp-79h] BYREF
  int InputBuffer; // [rsp+70h] [rbp-59h] BYREF
  _BYTE v66[92]; // [rsp+74h] [rbp-55h] BYREF
  _OWORD *v67; // [rsp+D0h] [rbp+7h] BYREF
  void *retaddr; // [rsp+128h] [rbp+5Fh]

  PopOsInitPhase = a1;
  PerformanceFrequency.QuadPart = 0;
  v63 = 0;
  memset(v64, 0, 28);
  if ( !(_DWORD)a1 )
  {
    KeQueryPerformanceCounter(&PerformanceFrequency);
    PopQpcFrequency = PerformanceFrequency.QuadPart;
    ((void (__fastcall *)(_QWORD, _QWORD, _QWORD))PopComputeCounterShifts)(
      (LARGE_INTEGER)PerformanceFrequency.QuadPart,
      &PpmPerformanceDistributionShift,
      &PpmPerformanceCounterShift);
    PopComputeCounterShifts(10000000, &PpmHvPerformanceDistributionShift, &PpmHvPerformanceCounterShift);
    PopCsResiliencyStatsLock = 0;
    PopSleepstudyInitialize(0);
    TimebrokerServiceSid = PopPowerAggregatorInitialize(0);
    if ( TimebrokerServiceSid >= 0 )
    {
      PopIdleLoopExecuted.Header.WaitListHead.Blink = &PopIdleLoopExecuted.Header.WaitListHead;
      PopIdleLoopExecuted.Header.WaitListHead.Flink = &PopIdleLoopExecuted.Header.WaitListHead;
      qword_140EFA6B8 = (__int64)&PopIrpList;
      PopIrpList = (__int64)&PopIrpList;
      qword_140EFA6D8 = (__int64)&PopInrushIrpList;
      PopInrushIrpList = (__int64)&PopInrushIrpList;
      qword_140EF7418 = 0;
      PopPowerEventLock = 0;
      qword_140EF70F8 = 0;
      PopSystemIdleLock = 0;
      qword_140EFBFC8 = 0;
      PopCoalRegistrationListLock = 0;
      LOWORD(PopIdleLoopExecuted.Header.Lock) = 0;
      PopIdleLoopExecuted.Header.Size = 6;
      PopIdleLoopExecuted.Header.SignalState = 0;
      PopDeepSleepDisengageReasonLock = 0;
      PopIrpLock = 0;
      ExInitializeNPagedLookasideListInternal((unsigned int)&PopIrpDataLookaside, 0, 0, 512, 312, 1917415248, 0, 0);
      PopShutdownNotificationCallbackLock = 0;
      qword_140EF7018 = (__int64)&PopShutdownNotificationCallbackList;
      PopShutdownNotificationCallbackList = &PopShutdownNotificationCallbackList;
      memset_0(PopStateTransitonBlameStack, 0, 0xC18u);
      dword_140EFBD60 = -1;
      *(_OWORD *)&xmmword_140EFBD68 = 0;
      xmmword_140EFBD68 = 0;
      PopBSDiagSetTriageData(2, PopStateTransitonBlameStack, 3096);
      PopPendingPowerTransitionLock = 0;
      PopDevicePowerTransitionInProgressWorkItem.WorkerRoutine = (void (__fastcall *)(void *))PopDevicePowerTransitionInProgressWorker;
      PopDevicePowerTransitionInProgressWorkItem.Parameter = 0;
      BootStatDisableFlush = (qword_140EED038 & 4) != 0;
      PopBsdFlushInactiveEvent.Header.WaitListHead.Blink = &PopBsdFlushInactiveEvent.Header.WaitListHead;
      PopBsdFlushInactiveEvent.Header.WaitListHead.Flink = &PopBsdFlushInactiveEvent.Header.WaitListHead;
      PopDevicePowerTransitionInProgressWorkItem.List.Flink = 0;
      BootStatFileHandle = 0;
      BootStatFileHandleAcquired = 0;
      BootStatKeepHandleOpen = 0;
      BootStatDataCache = 0;
      PopBsdSkipLogging = 0;
      qword_140EFD0C8 = 0;
      PopBsdUpdateLock = 0;
      LOWORD(PopBsdFlushInactiveEvent.Header.Lock) = 1;
      PopBsdFlushInactiveEvent.Header.Size = 6;
      PopBsdFlushInactiveEvent.Header.SignalState = 1;
      PopInitializeWorkItem(PopSetUserShutdownMarkerWorkItem, PopSetUserShutdownMarkerWorker, 0);
      PopInitializeWorkItem(PopClearUserShutdownMarkerWorkItem, PopClearUserShutdownMarkerWorker, v4);
      PopInitializeWorkItem(PopBsdFlushWorkItem, PopBsdFlushWorker, v5);
      PopInitializeWorkItem(&PopBsdUpdateWorkItem, PopBsdUpdateWorker, v6);
      PopWdiCurrentScenarioInstanceId = 0;
      PopWdiCurrentScenario = (__int64)&GUID_SPM_DEFAULT;
      PopInitializeWorkItem(PopExternalMonitorUpdatedWorkItem, PopExternalMonitorUpdatedWorker, v7);
      PopInitializeWorkItem(PopRecordLidStateWorkItem, PopRecordLidStateWorker, v8);
      qword_140EF6FF8 = 0;
      qword_140EFD098 = (__int64)&PopTransitionCheckpoints;
      PopTransitionCheckpoints = &PopTransitionCheckpoints;
      PopInputSuppressionLock = 0;
      qword_140EF6FA8 = 0;
      PopPowerButtonSuppressionLock = 0;
      qword_140EFD0A8 = 0;
      PopTransitionCheckpointLock = 0;
      PopMonitorOffDueToSleep = 0;
      PpmCheckInit();
      TimebrokerServiceSid = PopInitializeIrpWorkers();
      if ( TimebrokerServiceSid >= 0 )
      {
        v9 = PopIdleScanInterval;
        qword_140EFA738 = (__int64)&qword_140EFA730;
        qword_140EFA730 = (__int64)&qword_140EFA730;
        qword_140EFA758 = (__int64)&PopIrpSerialList;
        PopIrpSerialList = (__int64)&PopIrpSerialList;
        qword_140EFA748 = (__int64)&PopRequestedIrps;
        PopRequestedIrps = (__int64)&PopRequestedIrps;
        PopTransitionLock.Header.WaitListHead.Blink = &PopTransitionLock.Header.WaitListHead;
        PopTransitionLock.Header.WaitListHead.Flink = &PopTransitionLock.Header.WaitListHead;
        qword_140EFA778 = (__int64)&PowerStateDisableReasonListHead;
        PowerStateDisableReasonListHead = (__int64)&PowerStateDisableReasonListHead;
        PopDisableSleepMutex.Event.Header.WaitListHead.Blink = &PopDisableSleepMutex.Event.Header.WaitListHead;
        PopDisableSleepMutex.Event.Header.WaitListHead.Flink = &PopDisableSleepMutex.Event.Header.WaitListHead;
        qword_140EFC808 = (__int64)&PopDisableSleepList;
        PopDisableSleepList = (__int64)&PopDisableSleepList;
        PopShutdownEvent.Header.WaitListHead.Blink = &PopShutdownEvent.Header.WaitListHead;
        PopShutdownEvent.Header.WaitListHead.Flink = &PopShutdownEvent.Header.WaitListHead;
        qword_140EFC108 = (__int64)&PopShutdownQueue;
        PopShutdownQueue = (__int64)&PopShutdownQueue;
        PopShutdownListMutex.Event.Header.WaitListHead.Blink = &PopShutdownListMutex.Event.Header.WaitListHead;
        PopShutdownListMutex.Event.Header.WaitListHead.Flink = &PopShutdownListMutex.Event.Header.WaitListHead;
        qword_140EFA788 = (__int64)&PopIdleDetectList;
        PopIdleDetectList = (__int64)&PopIdleDetectList;
        PopIrpSerialLock = 0;
        qword_140EFA7A8 = 0;
        PpmIdlePolicyLock = 0;
        PpmIdleVetoLock = 0;
        PpmParkStateLock = 0;
        qword_140E2B948 = 0;
        word_140EFA728 = 1;
        byte_140EFA72A = 6;
        dword_140EFA72C = 1;
        PopWorkerLock = 0;
        LOWORD(PopTransitionLock.Header.Lock) = 1;
        PopTransitionLock.Header.Size = 6;
        PopTransitionLock.Header.SignalState = 1;
        PopDisableSleepMutex.Count = 1;
        PopDisableSleepMutex.Owner = 0;
        PopDisableSleepMutex.Contention = 0;
        LOWORD(PopDisableSleepMutex.Event.Header.Lock) = 1;
        PopDisableSleepMutex.Event.Header.Size = 6;
        PopDisableSleepMutex.Event.Header.SignalState = 0;
        LOWORD(PopShutdownEvent.Header.Lock) = 0;
        PopShutdownEvent.Header.Size = 6;
        PopShutdownEvent.Header.SignalState = 0;
        PopShutdownThreadList = 0;
        PopShutdownListMutex.Count = 1;
        PopShutdownListMutex.Owner = 0;
        PopShutdownListMutex.Contention = 0;
        LOWORD(PopShutdownListMutex.Event.Header.Lock) = 1;
        PopShutdownListMutex.Event.Header.Size = 6;
        PopShutdownListMutex.Event.Header.SignalState = 0;
        PopShutdownListAvailable = 1;
        PopDopeGlobalLock = 0;
        if ( PopIdleScanInterval )
        {
          if ( PopIdleScanInterval == -1 )
          {
            v9 = 30;
            PopIdleScanInterval = 30;
          }
          else if ( (unsigned int)PopIdleScanInterval > 0x12C )
          {
            v9 = 300;
            PopIdleScanInterval = 300;
          }
          PopIdleBackgroundIgnoreCount = (v9 + 59) / v9;
          PopBackgroundTaskIgnoreCount = (v9 + 179) / v9;
        }
        PopWorkerSpinLock = 0;
        PopPolicyWorker.WorkerRoutine = (void (__fastcall *)(void *))PopPolicyWorkerThread;
        PopPolicyWorker.List.Flink = 0;
        PopPolicyWorker.Parameter = (void *)0x80000000LL;
        PopWorkerStatus = -1;
        if ( (unsigned __int64)&PopPolicyLock < 0xFFFF800000000000uLL || MmDeterminePoolType(&PopPolicyLock) == 256 )
          ExpTraceLogBadResourceAddress(&PopPolicyLock, retaddr);
        memset_0(&PopPolicyLock.OwnerTable, 0, 0x50u);
        PopPolicyLock.SystemResourcesList.Blink = (struct _LIST_ENTRY *)&PopPolicyLock;
        PopPolicyLock.SystemResourcesList.Flink = (struct _LIST_ENTRY *)&PopPolicyLock;
        PopPolicyLock.SharedWaiters = 0;
        PopPolicyLock.ExclusiveWaiters = 0;
        PopPolicyLock.SpinLock = 0;
        if ( (NtGlobalFlag & 0x2000) != 0 )
        {
          v10 = RtlpStackTraceDatabase;
          if ( RtlpStackTraceDatabase )
          {
            v12 = RtlStdLogStackTrace(RtlpStackTraceDatabase, 1);
            if ( v12 )
            {
              RecordedStackTraceIndex = RtlpStdGetRecordedStackTraceIndex(v10);
              v11 = RecordedStackTraceIndex;
              if ( !RecordedStackTraceIndex )
                RtlStdReleaseStackTrace(v10, v12);
            }
            else
            {
              v11 = 0;
            }
          }
          else
          {
            v11 = 0;
          }
          PopPolicyLock.CreatorBackTraceIndex = v11;
        }
        else
        {
          PopPolicyLock.CreatorBackTraceIndex = 0;
        }
        HIDWORD(PopPolicyLock.Reserved2) = -1;
        ExpAddResourceToSystemResourceList(&PopPolicyLock);
        __incgsdword(0x6498u);
        if ( (*(_DWORD *)byte_140FBEC44 & 0x20000) != 0 )
          PerfLogExecutiveResourceInitialize(65544, &PopPolicyLock, 0, 0);
        PopAwaymodeLock = 0;
        PopVolumeLock.Event.Header.WaitListHead.Blink = &PopVolumeLock.Event.Header.WaitListHead;
        PopVolumeLock.Event.Header.WaitListHead.Flink = &PopVolumeLock.Event.Header.WaitListHead;
        PopVolumeLock.Count = 1;
        PopPowerSettingCallbackReturned.Header.WaitListHead.Blink = &PopPowerSettingCallbackReturned.Header.WaitListHead;
        PopPowerSettingCallbackReturned.Header.WaitListHead.Flink = &PopPowerSettingCallbackReturned.Header.WaitListHead;
        qword_140EFA988 = (__int64)&PopVolumeDevices;
        PopVolumeDevices = (__int64)&PopVolumeDevices;
        qword_140EFA9A8 = (__int64)&PopSwitches;
        PopSwitches = (__int64)&PopSwitches;
        PopVolumeLock.Owner = 0;
        PopVolumeLock.Contention = 0;
        LOWORD(PopVolumeLock.Event.Header.Lock) = 1;
        PopVolumeLock.Event.Header.Size = 6;
        PopVolumeLock.Event.Header.SignalState = 0;
        LOWORD(PopPowerSettingCallbackReturned.Header.Lock) = 0;
        PopPowerSettingCallbackReturned.Header.Size = 6;
        PopPowerSettingCallbackReturned.Header.SignalState = 0;
        qword_140EFA998 = (__int64)&PopFans;
        PopFans = (__int64)&PopFans;
        qword_140EFA9B8 = (__int64)&PopThermal;
        PopThermal = &PopThermal;
        PopWaitingForTransitionLock = 0;
        qword_140EF96E8 = 0;
        PopUnlockAfterSleepLock = 0;
        IoAddTriageDumpDataBlock((ULONG)&PopThermal, (PVOID)0x10);
        qword_140EFA9C8 = (__int64)&PopActionWaiters;
        PopActionWaiters = (__int64)&PopActionWaiters;
        PopResetActionDefaults();
        PopPolicy = &dword_140EFAA04;
        PopDefaultPolicy();
        LODWORD(PopAdminPolicy) = 2;
        *(_QWORD *)((char *)&PopAdminPolicy + 4) = 5;
        HIDWORD(PopAdminPolicy) = -1;
        qword_140EFA9F0 = 0xFFFFFFFF00000000uLL;
        qword_140EFBF28 = (__int64)&PopSstNotificationHandlerList;
        PopSstNotificationHandlerList = &PopSstNotificationHandlerList;
        PopFullWake = 1;
        PopSstNotificationHandlerListLock = 0;
        PopCoolingMode = 0;
        dword_140E2B940 = -1;
        dword_140E2B944 = 2;
        PpmInitPolicyConfiguration();
        PpmInitIdlePolicy();
        PpmPerfInitialize();
        PpmInitCoreParkingPolicy();
        PpmInitHeteroPolicy();
        PpmIdleRegisterDefaultStates();
        PopDeepSleepInitialize(0);
        PopInitializePowerSettings();
        PopInitilizeAcDcSettings();
        qword_140EFAC68 = 0;
        PopPolicyDeviceLock = 0;
        PopBatteryInit();
        PopThermalInit();
        qword_140EF9B78 = 0;
        qword_140EF9B88 = (__int64)&PopCoolingExtensionList;
        PopCoolingExtensionList = (__int64)&PopCoolingExtensionList;
        qword_140EF9B98 = (__int64)&PopPowerLimitExtensionList;
        PopPowerLimitExtensionList = (__int64)&PopPowerLimitExtensionList;
        PopCoolingExtensionLock = 0;
        qword_140EF9BA8 = 0;
        PopPowerLimitExtensionLock = 0;
        dword_140EFA840 = 4;
        byte_140EFA844 = 0;
        qword_140EFA848 = (__int64)PopShutdownHandler;
        *(_QWORD *)&PpmWmiIdleAccountingTimer.Header.Lock = 8;
        qword_140EFBE88 = (__int64)&PopWakeInfoList;
        v14 = 0;
        PopWakeInfoList = (__int64)&PopWakeInfoList;
        PopWakeSourceAvailable.Header.WaitListHead.Blink = &PopWakeSourceAvailable.Header.WaitListHead;
        PopWakeSourceAvailable.Header.WaitListHead.Flink = &PopWakeSourceAvailable.Header.WaitListHead;
        qword_140EFBEA8 = (__int64)&PopWakeSourceWorkList;
        PopWakeSourceWorkList = &PopWakeSourceWorkList;
        PpmWmiIdleAccountingTimer.Header.WaitListHead.Blink = &PpmWmiIdleAccountingTimer.Header.WaitListHead;
        PpmWmiIdleAccountingTimer.Header.WaitListHead.Flink = &PpmWmiIdleAccountingTimer.Header.WaitListHead;
        qword_140EF6D38 = (__int64)PpmWmiIdleAccountingProcedure;
        PopUserPresentWorkItem.WorkerRoutine = (void (__fastcall *)(void *))PopUserPresentSetWorker;
        qword_140E4D880 = (__int64)&qword_140E4D878;
        qword_140E4D878 = (__int64)&qword_140E4D878;
        PopAwayModeUserPresenceTimer = 8;
        PopUserPresentCompletedEvent.Header.WaitListHead.Blink = &PopUserPresentCompletedEvent.Header.WaitListHead;
        PopUserPresentCompletedEvent.Header.WaitListHead.Flink = &PopUserPresentCompletedEvent.Header.WaitListHead;
        PopWakeInfoCount = 0;
        PopCurrentWakeInfo = 0;
        PopWakeSourceLock = 0;
        LOWORD(PopWakeSourceAvailable.Header.Lock) = 0;
        PopWakeSourceAvailable.Header.Size = 6;
        PopWakeSourceAvailable.Header.SignalState = 1;
        PopWakeSourceWorkState = 0;
        PpmWmiIdleAccountingTimer.DueTime.QuadPart = 0;
        PpmWmiIdleAccountingTimer.Period = 0;
        PpmWmiIdleAccountingTimer.Processor = 0;
        PpmWmiIdleAccountingTimer.TimerDifObjTracking = 0;
        PpmWmiIdleAccountingDpc = 275;
        qword_140EF6D40 = 0;
        qword_140EF6D58 = 0;
        qword_140EF6D30 = 0;
        PopUserPresentLock = 0;
        PopUserPresentWorkItem.Parameter = 0;
        PopUserPresentWorkItem.List.Flink = 0;
        qword_140E4D888 = 0;
        dword_140E4D8AC = 0;
        word_140E4D8A8 = 0;
        byte_140E4D8AB = 0;
        LOWORD(PopUserPresentCompletedEvent.Header.Lock) = 1;
        PopUserPresentCompletedEvent.Header.Size = 6;
        PopUserPresentCompletedEvent.Header.SignalState = 0;
        do
          PopSmartSuspendResetData(&PopSmartSuspendDecisionQueue[13 * v14++]);
        while ( v14 != 16 );
        PopSmartSuspendQueueHead = 0;
        qword_140EFC418 = (__int64)&qword_140EFC410;
        qword_140EFC410 = (__int64)&qword_140EFC410;
        PopSmartSuspendDecision = (__int64)PopSmartSuspendDecisionQueue;
        word_140EFC408 = 1;
        byte_140EFC40A = 6;
        dword_140EFC40C = 1;
        PoFxInitPowerManagement();
        dword_140EFAB0C = 0;
        qword_140EFAB10 = 100;
        qword_140EFAB18 = 100;
        dword_140EFAB20 = 100;
        PopNetInitialize(0);
        PopInitializePowerButtonHold(0);
        qword_140EF61F8 = 0;
        PopSleepReliabilityDiagLock = 0;
        v15 = 0;
        PopBlackBoxLock = 0;
        PopBootStatLock = 0;
        do
        {
          BYTE4(qword_140E0AA78[14 * v15 + 5]) = 0;
          KeRegisterBugCheckReasonCallback(
            (PKBUGCHECK_REASON_CALLBACK_RECORD)&qword_140E0AA78[14 * v15],
            PopBlackBoxBugcheckCallback,
            KbCallbackSecondaryDumpData,
            (PUCHAR)(&off_140E0AA68)[14 * v15]);
          ++v15;
        }
        while ( v15 < 0x19 );
        TimebrokerServiceSid = PopStorageBootErrorsInit();
        if ( TimebrokerServiceSid >= 0 )
        {
          v16 = *(_QWORD *)(a2 + 240);
          LOBYTE(PopFirmwareResetReason) = *(_BYTE *)(v16 + 3440);
          if ( *(_BYTE *)(v16 + 3440) )
          {
            *((_QWORD *)&PopFirmwareResetReason + 1) = *(_QWORD *)(v16 + 3448);
            xmmword_140E4D6B0 = *(_OWORD *)(v16 + 3456);
            xmmword_140E4D6C0 = *(_OWORD *)(v16 + 3472);
          }
          TimebrokerServiceSid = PopCreateTimebrokerServiceSid();
          if ( TimebrokerServiceSid >= 0 )
          {
            PopInitializeDirectedDrips(0);
            SshInitialize(0);
LABEL_107:
            TimebrokerServiceSid = 0;
            return TimebrokerServiceSid >= 0;
          }
        }
      }
    }
    return TimebrokerServiceSid >= 0;
  }
  if ( (_DWORD)a1 == 1 )
  {
    if ( (unsigned __int8)HviIsAnyHypervisorPresent(a1, a2) )
    {
      PpmExitLatencyCheckEnabled = 0;
      PpmExitLatencySamplingPercentage = 0;
    }
    qword_140EFAC78 = 0;
    PopFanLock = 0;
    dword_140EFAD4C = 0;
    PopSendFanNoiseChangeWnf(0);
    if ( (unsigned int)PopAggressiveStandbyActionsRegValue < 0x10 )
      PopAggressiveStandbyEnabledActions = PopAggressiveStandbyActionsRegValue;
    qword_140EFB110 = 0;
    qword_140EFB118 = 0;
    qword_140EFB108 = 0;
    PopSuspendResumeNotification = 0;
    SshInitialize(1);
    PopUmpoInitializeChannel();
    PopUmpoInitializeMonitorChannel();
    PoInitializePdc();
    PopEsInit(1);
    PopInitializePowerSettingCallbacks();
    TimebrokerServiceSid = PopEtInit();
    if ( TimebrokerServiceSid >= 0 )
    {
      TimebrokerServiceSid = PopPowerRequestInitialize();
      if ( TimebrokerServiceSid >= 0 )
      {
        TimebrokerServiceSid = PopPowerAggregatorInitialize(1);
        if ( TimebrokerServiceSid >= 0 )
        {
          TimebrokerServiceSid = PopInitializeHighPerfPowerRequest();
          if ( TimebrokerServiceSid >= 0 )
          {
            PopInitializeTimer(
              (unsigned int)PopCheckPowerSourceAfterRtcWakeTimer,
              (unsigned int)PopCheckPowerSourceAfterRtcWakeTimerCallback,
              0,
              (unsigned int)PopCheckPowerSourceAfterRtcWakeTimerWorker,
              0);
            LOWORD(PopCheckPowerSourceAfterRtcWakeCompleted.Header.Lock) = 0;
            PopCheckPowerSourceAfterRtcWakeCompleted.Header.WaitListHead.Blink = &PopCheckPowerSourceAfterRtcWakeCompleted.Header.WaitListHead;
            PopCheckPowerSourceAfterRtcWakeCompleted.Header.WaitListHead.Flink = &PopCheckPowerSourceAfterRtcWakeCompleted.Header.WaitListHead;
            PopCheckPowerSourceAfterRtcWakeCompleted.Header.Size = 6;
            PopCheckPowerSourceAfterRtcWakeCompleted.Header.SignalState = 1;
            PopWatchdogInit();
            PopInitializePowerButtonHold(1);
            PopBSDiagInitialize();
            for ( i = 0; i != 9; i = v19 + 1 )
            {
              v18 = PpmConvertTimeFrom(PopDripsWakeIdleAccountingBucketLimitsMs[i], 1000);
              PopDripsWakeIdleAccountingBucketLimitsQpc[v19] = v18;
            }
            qword_140FC0328 = -1;
            for ( j = 0; j != 11; ++j )
              PopDripsWakePeriodAccountingBucketLimitsMs[j] = PopDripsWakePeriodAccountingBucketLimitsHns[j] / 0x2710uLL;
            qword_140FC04A8 = -1;
            TimebrokerServiceSid = EmpProviderRegister(
                                     0,
                                     (unsigned int)&PopEmEntry,
                                     1,
                                     (unsigned int)&PopEmCallback,
                                     2,
                                     (__int64)&v67);
            if ( TimebrokerServiceSid >= 0 )
            {
              PerformanceFrequency.LowPart = 1;
              PopErrataDisablePrimaryDeviceFastResume = 0;
              EmClientQueryRuleState(&GUID_EM_RULE_DISABLE_DEVICE_FAST_RESUME, &PerformanceFrequency);
              if ( PerformanceFrequency.LowPart == 2 )
                PopErrataDisablePrimaryDeviceFastResume = 1;
              PopDetectSimulatedHeteroProcessors();
              PpmHeteroHgsDetectContainmentPresence(0, 0);
              goto LABEL_107;
            }
          }
        }
      }
    }
    return TimebrokerServiceSid >= 0;
  }
  if ( (_DWORD)a1 != 2 )
  {
    if ( (_DWORD)a1 != 3 )
      goto LABEL_107;
    TimebrokerServiceSid = PopDiagInitialize();
    if ( TimebrokerServiceSid < 0 )
      return TimebrokerServiceSid >= 0;
    SshInitialize(3);
    PopSleepstudyInitialize(3);
    LOBYTE(v31) = PopPlatformAoAcCapabilityInitialized != 0 ? PopPlatformAoAc : 0;
    PopTriggerDiagTraceAoAcCapability(v31);
    PopAcquireRwLockShared(&PopPolicyDeviceLock);
    for ( k = (__int64 *)PopFans; k != &PopFans; k = (__int64 *)*k )
      PopSqmFanEnumeration();
    PopReleaseRwLock((ULONG_PTR)&PopPolicyDeviceLock);
    PopInitializeWin32kActivator();
    if ( (Feature_UnifiedMsNotification__private_featureState & 0x10) != 0 )
      IsEnabledDeviceUsageNoInline = Feature_UnifiedMsNotification__private_featureState & 1;
    else
      IsEnabledDeviceUsageNoInline = Feature_UnifiedMsNotification__private_IsEnabledDeviceUsageNoInline();
    if ( IsEnabledDeviceUsageNoInline )
      PopModernStandbyNotificationInit();
    PopPowerAggregatorInitialize(3);
    if ( (int)PdcTaskClientRegister(120, &PopUserShutdownTaskClient) < 0 )
      PopUserShutdownTaskClient = 0;
    PopInitializeTimer(
      (unsigned int)PopUserShutdownCalloutDelayTimer,
      (unsigned int)PopUserShutdownCalloutDelayTimerCallback,
      0,
      (unsigned int)PopUserShutdownCalloutDelayTimerWorker,
      0);
    PopUserShutdownInitializeSleepstudyDiagnostics();
    v36 = 2;
    v37 = 1;
    if ( PopSkipTickPolicy )
    {
      if ( PopSkipTickPolicy != 1 )
      {
        v36 = 0;
        v38 = 0;
LABEL_76:
        PoSkipTickMode = v38;
        LOBYTE(v34) = v37;
        LOBYTE(v35) = v36 == 2;
        PopDiagTraceSkipTick(v35, v34);
        goto LABEL_77;
      }
      v37 = 0;
      if ( (int)HalGetInterruptTargetInformation(2, 0, v64) >= 0 )
      {
        PopApicMode = DWORD1(v64[1]);
        if ( DWORD1(v64[1]) == 3 )
        {
          PopApicClusterSize = DWORD2(v64[1]);
          PoSkipTickMaxOpportunisticProcessors = 8;
        }
        PoSkipTickMode = (unsigned __int8)PopCheckSkipTick() == 0;
LABEL_77:
        PpmInitIllegalThrottleLogging();
        PopCheckShutdownMarker(a2);
        PopCheckAndClearBootError();
        if ( (unsigned __int8)guard_dispatch_icall_no_overrides(v40, v39, v41)
          || (_DWORD)PoOffCrashConfigTable && DWORD1(PoOffCrashConfigTable) )
        {
          PopDiagTraceAbnormalReset(DWORD1(PoOffCrashConfigTable));
        }
        PopIdleWakeInitialize();
        PopAcquirePolicyLock(v43, v42, v44, v45);
        PopUpdateUpgradeInProgress(0);
        if ( InitIsWinPEMode )
          PopLogSleepDisabled(16, 15, 0);
        if ( byte_140EFAB74 )
          PopLogSleepDisabled(17, 7, 0);
        v46 = 0;
        if ( (*(_BYTE *)(*(_QWORD *)(a2 + 240) + 2648LL) & 8) != 0 )
        {
          PopSecureLaunched = 1;
          v46 = 4;
        }
        if ( (HvlpFlags & 2) != 0 || !VslVsmEnabled )
        {
          if ( !(_DWORD)v46 )
          {
LABEL_92:
            PopDeepSleepInitialize(3);
            PopInitializePowerPolicySimulate();
            if ( (PopSimulate & 1) != 0 )
            {
              byte_140EFAB7E = 1;
              *(_QWORD *)&xmmword_140EFAB80 = 0x19000000064LL;
              *((_QWORD *)&xmmword_140EFAB80 + 1) = 0xFFFF0000000ALL;
              dword_140EFABA0 = 4;
              dword_140EFABA8 = 2;
            }
            if ( (PopSimulate & 2) != 0 )
            {
              *(_DWORD *)&PopCapabilities = 16843009;
              word_140EFAB64 = 257;
              byte_140EFAB66 = 1;
              *(_WORD *)&byte_140EFAB71 = 257;
            }
            PopResetCurrentPolicies();
            PopInitializeAdpm();
            PopEsInit(3);
            PopInitilizeAcDcSettings();
            v63 = 1;
            PopUpdateConsoleDisplayState(1);
            ZwUpdateWnfStateData(&WNF_PO_PRIMARY_DISPLAY_VISIBLE_STATE, &v63, 4);
            PopNetInitialize(3);
            PopReleasePolicyLock(v48, v47, v49);
            PopIdleInitAoAcDozeS4Timer(v51, v50, v52);
            PerformanceFrequency.QuadPart = 0;
            memset_0(v66, 0, sizeof(v66));
            InputBuffer = 21;
            ZwPowerInformation(PowerInformationInternal, &InputBuffer, 0x60u, &PerformanceFrequency, 8u);
            *(_OWORD *)&xmmword_140EF6188 = 0;
            xmmword_140EF6188 = 0;
            PopPdcIdlePhaseWatchdogContext = PerformanceFrequency.QuadPart;
            PopInitializeSystemIdleDetection();
            PopHiberResumeXhciHandoffSkip = (*(_DWORD *)(*(_QWORD *)(a2 + 240) + 132LL) & 0x10000000) != 0;
            PopSetupHighPerfPowerRequest();
            PpmEnableWmiInterface();
            v56 = *(_QWORD *)(a2 + 240);
            if ( (*(_DWORD *)(v56 + 2648) & 0x8000LL) != 0 )
              PopFasr = 1;
            BootAppSvnInfo = *(_OWORD *)(v56 + 4416);
            PopAcquirePolicyLock(v53, v56, v54, v55);
            PopCoalescingInitialize();
            PopReleasePolicyLock(v58, v57, v59);
            PopInitializeDirectedDrips(3);
            PopDripsWatchdogInitialize();
            PopSetupAudioEventNotification();
            PopSetupMixedRealitytNotification();
            PopSetupFullScrenVideoNotification();
            PopSetupUserPresencePredictionNotification();
            PopSetupSprActiveSessionChangeNotification();
            PopSetupAirplaneModeNotification();
            PopSetupBluetoothChargingNotification();
            PopSetupMobileHotspotNotification();
            PopThermalHandlePreviousShutdown();
            PopCheckpointEfiRuntimeRedirected = (*(_DWORD *)(a2 + 264) & 2) != 0;
            TtmInit();
            if ( PopPlatformAoAcCapabilityInitialized )
            {
              if ( PopPlatformAoAc )
              {
                PerformanceFrequency.LowPart = 1;
                EmClientQueryRuleState(EM_RULE_IGNORE_INCORRECT_LID_NOTIFICATIONS, &PerformanceFrequency);
                if ( PerformanceFrequency.LowPart == 2 )
                  PopErrataReportingIncorrectLidState = 1;
              }
            }
            PopLidReliabilityInit();
            PopEvaluateInputSuppressionRequired();
            PopPowerButtonSuppressionInit();
            PopBatteryQueueWork(1);
            PopSetupKsrCallbacks();
            if ( PopEnableHibernateMemoryMapValidationOverride == -1 )
            {
              PerformanceFrequency.LowPart = 1;
              EmClientQueryRuleState(&GUID_EM_RULE_SKIP_HIBERNATE_MEMORY_MAP_VALIDATION, &PerformanceFrequency);
              v60 = PerformanceFrequency.LowPart == 2;
            }
            else
            {
              v60 = PopEnableHibernateMemoryMapValidationOverride != 0;
            }
            PopHiberSkipMemoryMapValidation = v60;
            *((_QWORD *)&v64[0] + 1) = 16;
            *(_QWORD *)&v64[0] = &GUID_EM_RULE_SKIP_MEMORY_OVERWRITE_REQUEST_CONTROL_LOCK_ACTION;
            PerformanceFrequency.LowPart = 1;
            v67 = v64;
            PopErrataSkipMemoryOverwriteRequestControlLockAction = 0;
            EmClientRuleEvaluate(
              &GUID_EM_RULE_SKIP_MEMORY_OVERWRITE_REQUEST_CONTROL_LOCK_ACTION_QUERY,
              &v67,
              1,
              &PerformanceFrequency);
            if ( PerformanceFrequency.LowPart == 2 )
              PopErrataSkipMemoryOverwriteRequestControlLockAction = 1;
            goto LABEL_107;
          }
        }
        else
        {
          v46 = 23;
        }
        PopLogSleepDisabled(21, v46, 0);
        goto LABEL_92;
      }
    }
    v38 = 2;
    goto LABEL_76;
  }
  PoFxRegisterDebugger();
  HalReportResourceUsage(1);
  PopBatteryInitPhaseTwo();
  TimebrokerServiceSid = PpmEventInitialize();
  if ( TimebrokerServiceSid >= 0 )
  {
    KeRegisterProcessorChangeCallback(PopNewProcessorCallback, 0, 0);
    PpmAcquireLock(&PpmPerfPolicyLock, v21, v22, v23);
    LOBYTE(v24) = 1;
    PopInitializeHeteroProcessors(v24, 0);
    PpmReleaseLock(&PpmPerfPolicyLock);
    if ( PpmPerfArtificialDomainSetting != -1 )
      PpmPerfArtificialDomainEnabled = PpmPerfArtificialDomainSetting != 0;
    PpmIdleRegisterDefaultStates();
    TimebrokerServiceSid = PpmParkInitialize();
    if ( TimebrokerServiceSid >= 0 )
    {
      PpmCheckInitProcessors(0, 1);
      PpmAcquireLock(&PopFxSystemLatencyLock, v25, v26, v27);
      PoFxSendSystemLatencyUpdate();
      PpmReleaseLock(&PopFxSystemLatencyLock);
      PopPdcCsCheckSystemVolumeDevice();
      v67 = (_OWORD *)WNF_EXEC_THERMAL_LIMITER_TERMINATE_BACKGROUND_TASKS;
      PerformanceFrequency.LowPart = 0;
      ZwUpdateWnfStateData(&v67, &PerformanceFrequency, 4);
      ZwUpdateWnfStateData(&WNF_PO_MULTIMEDIA_POWER_MODEL, &PpmPerfMultimediaPowerModel, 4);
      PopInitVideoWnfState(v29, v28, v30);
      goto LABEL_107;
    }
  }
  return TimebrokerServiceSid >= 0;
}

```

## disassembly

```asm
0x140c2464c  push    rbp
0x140c2464e  push    rbx
0x140c2464f  push    rsi
0x140c24650  push    rdi
0x140c24651  push    r12
0x140c24653  push    r13
0x140c24655  push    r14
0x140c24657  push    r15
0x140c24659  lea     rbp, [rsp-1Fh]
0x140c2465e  sub     rsp, 0E8h
0x140c24665  mov     rax, cs:__security_cookie
0x140c2466c  xor     rax, rsp
0x140c2466f  mov     [rbp+57h+var_48], rax
0x140c24673  xor     r13d, r13d
0x140c24676  mov     cs:PopOsInitPhase, ecx
0x140c2467c  mov     qword ptr [rsp+120h+PerformanceFrequency], r13
0x140c24681  xorps   xmm0, xmm0
0x140c24684  mov     [rsp+120h+var_D8], r13d
0x140c24689  mov     r15, rdx
0x140c2468c  movups  [rbp+57h+var_D0], xmm0
0x140c24690  lea     r14d, [r13+1]
0x140c24694  movups  [rbp+57h+var_D0+0Ch], xmm0
0x140c24698  test    ecx, ecx
0x140c2469a  jnz     loc_140C251C1
0x140c246a0  lea     rcx, [rsp+120h+PerformanceFrequency]; PerformanceFrequency
0x140c246a5  call    KeQueryPerformanceCounter
0x140c246aa  mov     rcx, qword ptr [rsp+120h+PerformanceFrequency]
0x140c246af  lea     r8, PpmPerformanceCounterShift
0x140c246b6  lea     rdx, PpmPerformanceDistributionShift
0x140c246bd  mov     cs:PopQpcFrequency, rcx
0x140c246c4  call    PopComputeCounterShifts
0x140c246c9  mov     ecx, 989680h
0x140c246ce  lea     r8, PpmHvPerformanceCounterShift
0x140c246d5  lea     rdx, PpmHvPerformanceDistributionShift
0x140c246dc  call    PopComputeCounterShifts
0x140c246e1  xor     ecx, ecx
0x140c246e3  mov     cs:PopCsResiliencyStatsLock, r13
0x140c246ea  call    PopSleepstudyInitialize
0x140c246ef  xor     ecx, ecx
0x140c246f1  call    PopPowerAggregatorInitialize
0x140c246f6  test    eax, eax
0x140c246f8  js      loc_140C259D5
0x140c246fe  lea     rax, PopIdleLoopExecuted.Header.WaitListHead
0x140c24705  mov     [rsp+120h+var_E8], r13d
0x140c2470a  mov     cs:PopIdleLoopExecuted.Header.WaitListHead.Blink, rax
0x140c24711  lea     rcx, PopIrpDataLookaside
0x140c24718  mov     cs:PopIdleLoopExecuted.Header.WaitListHead.Flink, rax
0x140c2471f  mov     r9d, 200h
0x140c24725  lea     rax, PopIrpList
0x140c2472c  mov     word ptr [rsp+120h+var_F0], r13w
0x140c24732  mov     cs:qword_140EFA6B8, rax
0x140c24739  xor     r8d, r8d
0x140c2473c  mov     cs:PopIrpList, rax
0x140c24743  xor     edx, edx
0x140c24745  lea     rax, PopInrushIrpList
0x140c2474c  mov     dword ptr [rsp+120h+var_F8], 72496F50h
0x140c24754  mov     cs:qword_140EFA6D8, rax
0x140c2475b  mov     cs:PopInrushIrpList, rax
0x140c24762  mov     cs:qword_140EF7418, r13
0x140c24769  mov     cs:PopPowerEventLock, r13
0x140c24770  mov     cs:qword_140EF70F8, r13
0x140c24777  mov     cs:PopSystemIdleLock, r13
0x140c2477e  mov     cs:qword_140EFBFC8, r13
0x140c24785  mov     cs:PopCoalRegistrationListLock, r13
0x140c2478c  mov     word ptr cs:PopIdleLoopExecuted.Header, r13w
0x140c24794  mov     byte ptr cs:PopIdleLoopExecuted.Header+2, 6
0x140c2479b  mov     cs:PopIdleLoopExecuted.Header.SignalState, r13d
0x140c247a2  mov     cs:PopDeepSleepDisengageReasonLock, r13
0x140c247a9  mov     cs:PopIrpLock, r13
0x140c247b0  mov     qword ptr [rsp+120h+OutputBufferLength], 138h
0x140c247b9  call    ExInitializeNPagedLookasideListInternal
0x140c247be  lea     rax, PopShutdownNotificationCallbackList
0x140c247c5  mov     cs:PopShutdownNotificationCallbackLock, r13
0x140c247cc  mov     ebx, 0C18h
0x140c247d1  mov     cs:qword_140EF7018, rax
0x140c247d8  mov     r8d, ebx; Size
0x140c247db  mov     cs:PopShutdownNotificationCallbackList, rax
0x140c247e2  xor     edx, edx; Val
0x140c247e4  lea     rcx, PopStateTransitonBlameStack; void *
0x140c247eb  call    memset_0
0x140c247f0  xorps   xmm0, xmm0
0x140c247f3  mov     cs:dword_140EFBD60, 0FFFFFFFFh
0x140c247fd  movups  cs:xmmword_140EFBD68, xmm0
0x140c24804  lea     edi, [r13+2]
0x140c24808  mov     qword ptr cs:xmmword_140EFBD68, r13
0x140c2480f  mov     r8d, ebx
0x140c24812  lea     rdx, PopStateTransitonBlameStack
0x140c24819  mov     ecx, edi
0x140c2481b  call    PopBSDiagSetTriageData
0x140c24820  lea     rax, PopDevicePowerTransitionInProgressWorker
0x140c24827  mov     cs:PopPendingPowerTransitionLock, r13
0x140c2482e  mov     cs:PopDevicePowerTransitionInProgressWorkItem.WorkerRoutine, rax
0x140c24835  lea     rdx, PopSetUserShutdownMarkerWorker
0x140c2483c  mov     al, byte ptr cs:qword_140EED038
0x140c24842  lea     rcx, PopSetUserShutdownMarkerWorkItem
0x140c24849  shr     al, 2
0x140c2484c  xor     r8d, r8d
0x140c2484f  and     al, r14b
0x140c24852  mov     cs:PopDevicePowerTransitionInProgressWorkItem.Parameter, r13
0x140c24859  mov     cs:BootStatDisableFlush, al
0x140c2485f  lea     rax, PopBsdFlushInactiveEvent.Header.WaitListHead
0x140c24866  mov     cs:PopBsdFlushInactiveEvent.Header.WaitListHead.Blink, rax
0x140c2486d  mov     cs:PopBsdFlushInactiveEvent.Header.WaitListHead.Flink, rax
0x140c24874  mov     cs:PopDevicePowerTransitionInProgressWorkItem.List.Flink, r13
0x140c2487b  mov     cs:BootStatFileHandle, r13
0x140c24882  mov     cs:BootStatFileHandleAcquired, r13b
0x140c24889  mov     cs:BootStatKeepHandleOpen, r13b
0x140c24890  mov     cs:BootStatDataCache, r13
0x140c24897  mov     cs:PopBsdSkipLogging, r13b
0x140c2489e  mov     cs:qword_140EFD0C8, r13
0x140c248a5  mov     cs:PopBsdUpdateLock, r13
0x140c248ac  mov     word ptr cs:PopBsdFlushInactiveEvent.Header, r14w
0x140c248b4  mov     byte ptr cs:PopBsdFlushInactiveEvent.Header+2, 6
0x140c248bb  mov     cs:PopBsdFlushInactiveEvent.Header.SignalState, r14d
0x140c248c2  call    PopInitializeWorkItem
0x140c248c7  lea     rdx, PopClearUserShutdownMarkerWorker
0x140c248ce  lea     rcx, PopClearUserShutdownMarkerWorkItem
0x140c248d5  call    PopInitializeWorkItem
0x140c248da  lea     rdx, PopBsdFlushWorker
0x140c248e1  lea     rcx, PopBsdFlushWorkItem
0x140c248e8  call    PopInitializeWorkItem
0x140c248ed  lea     rdx, PopBsdUpdateWorker
0x140c248f4  lea     rcx, PopBsdUpdateWorkItem
0x140c248fb  call    PopInitializeWorkItem
0x140c24900  lea     rcx, GUID_SPM_DEFAULT
0x140c24907  mov     cs:PopWdiCurrentScenarioInstanceId, r13
0x140c2490e  mov     cs:PopWdiCurrentScenario, rcx
0x140c24915  lea     rdx, PopExternalMonitorUpdatedWorker
0x140c2491c  lea     rcx, PopExternalMonitorUpdatedWorkItem
0x140c24923  call    PopInitializeWorkItem
0x140c24928  lea     rdx, PopRecordLidStateWorker
0x140c2492f  lea     rcx, PopRecordLidStateWorkItem
0x140c24936  call    PopInitializeWorkItem
0x140c2493b  lea     rax, PopTransitionCheckpoints
0x140c24942  mov     cs:qword_140EF6FF8, r13
0x140c24949  mov     cs:qword_140EFD098, rax
0x140c24950  mov     cs:PopTransitionCheckpoints, rax
0x140c24957  mov     cs:PopInputSuppressionLock, r13
0x140c2495e  mov     cs:qword_140EF6FA8, r13
0x140c24965  mov     cs:PopPowerButtonSuppressionLock, r13
0x140c2496c  mov     cs:qword_140EFD0A8, r13
0x140c24973  mov     cs:PopTransitionCheckpointLock, r13
0x140c2497a  mov     cs:PopMonitorOffDueToSleep, r13b
0x140c24981  call    PpmCheckInit
0x140c24986  call    PopInitializeIrpWorkers
0x140c2498b  test    eax, eax
0x140c2498d  js      loc_140C259D5
0x140c24993  mov     ecx, cs:PopIdleScanInterval
0x140c24999  lea     rax, qword_140EFA730
0x140c249a0  mov     cs:qword_140EFA738, rax
0x140c249a7  or      ebx, 0FFFFFFFFh
0x140c249aa  mov     cs:qword_140EFA730, rax
0x140c249b1  lea     rax, PopIrpSerialList
0x140c249b8  mov     cs:qword_140EFA758, rax
0x140c249bf  mov     cs:PopIrpSerialList, rax
0x140c249c6  lea     rax, PopRequestedIrps
0x140c249cd  mov     cs:qword_140EFA748, rax
0x140c249d4  mov     cs:PopRequestedIrps, rax
0x140c249db  lea     rax, PopTransitionLock.Header.WaitListHead
0x140c249e2  mov     cs:PopTransitionLock.Header.WaitListHead.Blink, rax
0x140c249e9  mov     cs:PopTransitionLock.Header.WaitListHead.Flink, rax
0x140c249f0  lea     rax, PowerStateDisableReasonListHead
0x140c249f7  mov     cs:qword_140EFA778, rax
0x140c249fe  mov     cs:PowerStateDisableReasonListHead, rax
0x140c24a05  lea     rax, PopDisableSleepMutex.Event.Header.WaitListHead
0x140c24a0c  mov     cs:PopDisableSleepMutex.Event.Header.WaitListHead.Blink, rax
0x140c24a13  mov     cs:PopDisableSleepMutex.Event.Header.WaitListHead.Flink, rax
0x140c24a1a  lea     rax, PopDisableSleepList
0x140c24a21  mov     cs:qword_140EFC808, rax
0x140c24a28  mov     cs:PopDisableSleepList, rax
0x140c24a2f  lea     rax, PopShutdownEvent.Header.WaitListHead
0x140c24a36  mov     cs:PopShutdownEvent.Header.WaitListHead.Blink, rax
0x140c24a3d  mov     cs:PopShutdownEvent.Header.WaitListHead.Flink, rax
0x140c24a44  lea     rax, PopShutdownQueue
0x140c24a4b  mov     cs:qword_140EFC108, rax
0x140c24a52  mov     cs:PopShutdownQueue, rax
0x140c24a59  lea     rax, PopShutdownListMutex.Event.Header.WaitListHead
0x140c24a60  mov     cs:PopShutdownListMutex.Event.Header.WaitListHead.Blink, rax
0x140c24a67  mov     cs:PopShutdownListMutex.Event.Header.WaitListHead.Flink, rax
0x140c24a6e  lea     rax, PopIdleDetectList
0x140c24a75  mov     cs:qword_140EFA788, rax
0x140c24a7c  mov     cs:PopIdleDetectList, rax
0x140c24a83  mov     cs:PopIrpSerialLock, r13
0x140c24a8a  mov     cs:qword_140EFA7A8, r13
0x140c24a91  mov     cs:PpmIdlePolicyLock, r13
0x140c24a98  mov     cs:PpmIdleVetoLock, r13
0x140c24a9f  mov     cs:PpmParkStateLock, r13
0x140c24aa6  mov     cs:qword_140E2B948, r13
0x140c24aad  mov     cs:word_140EFA728, r14w
0x140c24ab5  mov     cs:byte_140EFA72A, 6
0x140c24abc  mov     cs:dword_140EFA72C, r14d
0x140c24ac3  mov     cs:PopWorkerLock, r13
0x140c24aca  mov     word ptr cs:PopTransitionLock.Header, r14w
0x140c24ad2  mov     byte ptr cs:PopTransitionLock.Header+2, 6
0x140c24ad9  mov     cs:PopTransitionLock.Header.SignalState, r14d
0x140c24ae0  mov     cs:PopDisableSleepMutex.Count, r14d
0x140c24ae7  mov     cs:PopDisableSleepMutex.Owner, r13
0x140c24aee  mov     cs:PopDisableSleepMutex.Contention, r13d
0x140c24af5  mov     word ptr cs:PopDisableSleepMutex.Event.Header, r14w
0x140c24afd  mov     byte ptr cs:PopDisableSleepMutex.Event.Header+2, 6
0x140c24b04  mov     cs:PopDisableSleepMutex.Event.Header.SignalState, r13d
0x140c24b0b  mov     word ptr cs:PopShutdownEvent.Header, r13w
0x140c24b13  mov     byte ptr cs:PopShutdownEvent.Header+2, 6
0x140c24b1a  mov     cs:PopShutdownEvent.Header.SignalState, r13d
0x140c24b21  mov     cs:PopShutdownThreadList, r13
0x140c24b28  mov     cs:PopShutdownListMutex.Count, r14d
0x140c24b2f  mov     cs:PopShutdownListMutex.Owner, r13
0x140c24b36  mov     cs:PopShutdownListMutex.Contention, r13d
0x140c24b3d  mov     word ptr cs:PopShutdownListMutex.Event.Header, r14w
0x140c24b45  mov     byte ptr cs:PopShutdownListMutex.Event.Header+2, 6
0x140c24b4c  mov     cs:PopShutdownListMutex.Event.Header.SignalState, r13d
0x140c24b53  mov     cs:PopShutdownListAvailable, r14b
0x140c24b5a  mov     cs:PopDopeGlobalLock, r13
0x140c24b61  test    ecx, ecx
0x140c24b63  jz      short loc_140C24BA2
0x140c24b65  cmp     ecx, ebx
0x140c24b67  jnz     short loc_140C24B74
0x140c24b69  lea     ecx, [rdi+1Ch]
0x140c24b6c  mov     cs:PopIdleScanInterval, ecx
0x140c24b72  jmp     short loc_140C24B85
0x140c24b74  mov     eax, 12Ch
0x140c24b79  cmp     ecx, eax
0x140c24b7b  jbe     short loc_140C24B85
0x140c24b7d  mov     ecx, eax
0x140c24b7f  mov     cs:PopIdleScanInterval, eax
0x140c24b85  xor     edx, edx
0x140c24b87  lea     eax, [rcx+3Bh]
0x140c24b8a  div     ecx
0x140c24b8c  xor     edx, edx
0x140c24b8e  mov     cs:PopIdleBackgroundIgnoreCount, eax
0x140c24b94  lea     eax, [rcx+0B3h]
0x140c24b9a  div     ecx
0x140c24b9c  mov     cs:PopBackgroundTaskIgnoreCount, eax
0x140c24ba2  lea     rax, PopPolicyWorkerThread
0x140c24ba9  mov     cs:PopWorkerSpinLock, r13
0x140c24bb0  mov     cs:PopPolicyWorker.WorkerRoutine, rax
0x140c24bb7  lea     r12, PopPolicyLock
0x140c24bbe  mov     eax, 80000000h
0x140c24bc3  mov     cs:PopPolicyWorker.List.Flink, r13
0x140c24bca  mov     cs:PopPolicyWorker.Parameter, rax
0x140c24bd1  mov     rax, 0FFFF800000000000h
0x140c24bdb  mov     cs:PopWorkerStatus, ebx
0x140c24be1  cmp     r12, rax
0x140c24be4  jb      short loc_140C24BF6
0x140c24be6  mov     rcx, r12
0x140c24be9  call    MmDeterminePoolType
0x140c24bee  cmp     rax, 100h
0x140c24bf4  jnz     short loc_140C24C02
0x140c24bf6  mov     rdx, [rbp+5Fh]
0x140c24bfa  mov     rcx, r12
0x140c24bfd  call    ExpTraceLogBadResourceAddress
0x140c24c02  xor     edx, edx; Val
0x140c24c04  lea     rcx, PopPolicyLock.OwnerTable; void *
0x140c24c0b  lea     r8d, [rdx+50h]; Size
0x140c24c0f  call    memset_0
0x140c24c14  xor     eax, eax
0x140c24c16  mov     cs:PopPolicyLock.SystemResourcesList.Blink, r12
0x140c24c1d  test    cs:NtGlobalFlag, 2000h
0x140c24c27  mov     cs:PopPolicyLock.SystemResourcesList.Flink, r12
0x140c24c2e  mov     cs:PopPolicyLock.SharedWaiters, rax
0x140c24c35  mov     cs:PopPolicyLock.ExclusiveWaiters, rax
0x140c24c3c  mov     cs:PopPolicyLock.SpinLock, r13
0x140c24c43  jz      short loc_140C24CA5
0x140c24c45  mov     rsi, cs:RtlpStackTraceDatabase
0x140c24c4c  test    rsi, rsi
0x140c24c4f  jnz     short loc_140C24C56
0x140c24c51  mov     r14d, r13d
0x140c24c54  jmp     short loc_140C24C92
0x140c24c56  mov     edx, r14d
0x140c24c59  mov     rcx, rsi; SpinLock
0x140c24c5c  call    RtlStdLogStackTrace
0x140c24c61  mov     r12, rax
0x140c24c64  test    rax, rax
0x140c24c67  jz      short loc_140C24C88
0x140c24c69  mov     rdx, rax
0x140c24c6c  mov     rcx, rsi; SpinLock
0x140c24c6f  call    RtlpStdGetRecordedStackTraceIndex
0x140c24c74  mov     r14d, eax
0x140c24c77  test    eax, eax
0x140c24c79  jnz     short loc_140C24C8B
0x140c24c7b  mov     rdx, r12
0x140c24c7e  mov     rcx, rsi
0x140c24c81  call    RtlStdReleaseStackTrace
0x140c24c86  jmp     short loc_140C24C8B
0x140c24c88  mov     r14d, r13d
0x140c24c8b  lea     r12, PopPolicyLock
0x140c24c92  movzx   eax, r14w
0x140c24c96  mov     r14d, 1
0x140c24c9c  mov     qword ptr cs:PopPolicyLock.58h, rax
0x140c24ca3  jmp     short loc_140C24CAC
0x140c24ca5  mov     qword ptr cs:PopPolicyLock.58h, r13
0x140c24cac  mov     rcx, r12
0x140c24caf  mov     dword ptr cs:PopPolicyLock.Reserved2+4, ebx
0x140c24cb5  call    ExpAddResourceToSystemResourceList
0x140c24cba  inc     dword ptr gs:6498h
0x140c24cc2  mov     eax, dword ptr cs:byte_140FBEC44
0x140c24cc8  bt      eax, 11h
0x140c24ccc  jnb     short loc_140C24CE1
0x140c24cce  xor     r9d, r9d
0x140c24cd1  xor     r8d, r8d
  ... truncated ...
```
