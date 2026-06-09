# CKsFilter::Init(_IRP *,_KSFILTERFACTORY_EXT *,_LIST_ENTRY *,_KSFILTER_DESCRIPTOR const *,KSAUTOMATION_TABLE_ const *,KSAUTOMATION_TABLE_ * const *,KSAUTOMATION_TABLE_ * const *,ulong)

- ea: `0x180050254`
- end: `0x180050c04`
- name: `?Init@CKsFilter@@QEAAJPEAU_IRP@@PEAU_KSFILTERFACTORY_EXT@@PEAU_LIST_ENTRY@@PEBU_KSFILTER_DESCRIPTOR@@PEBUKSAUTOMATION_TABLE_@@PEBQEAU6@5K@Z`
- size: `2480`
- prototype: `__int64 __usercall@<rax>(CKsFilter *__hidden this@<rcx>, struct _IRP *@<rdx>, struct _KSFILTERFACTORY_EXT *@<r8>, struct _LIST_ENTRY *@<r9>, const struct _KSFILTER_DESCRIPTOR *, const struct KSAUTOMATION_TABLE_ *, struct KSAUTOMATION_TABLE_ *const *, struct KSAUTOMATION_TABLE_ *const *, unsigned int)`
- caller_count: `1`
- callee_count: `22`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, installer_update`

## callers

- `0x180050010`

## callees

- `0x1800048a0`
- `0x180005550`
- `0x180005a00`
- `0x18000a2d4`
- `0x18000a9f0`
- `0x18000aa80`
- `0x18000b7bc`
- `0x18000c630`
- `0x18000fe2c`
- `0x1800121f8`
- `0x1800124bc`
- `0x1800146c8`
- `0x180019c60`
- `0x1800332f4`
- `0x18004fd00`
- `0x18004ff10`
- `0x180050254`
- `0x180050c10`
- `0x180054e30`
- `0x180057990`
- `0x18005b348`
- `0x1800754e0`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x180050ab2`
- `ntoskrnl!KeReleaseMutex` at `0x180050ab2`
- `ntoskrnl!KeInitializeMutex` at `0x180050408`
- `ntoskrnl!KeInitializeMutex` at `0x1800505ee`
- `ntoskrnl!KeInitializeMutex` at `0x180050408`
- `ntoskrnl!KeInitializeMutex` at `0x1800505ee`
- `ntoskrnl!IoGetInitiatorProcess` at `0x180050612`
- `ntoskrnl!IoGetInitiatorProcess` at `0x180050612`
- `ntoskrnl!PsGetProcessId` at `0x18005065e`
- `ntoskrnl!PsGetProcessId` at `0x18005065e`
- `ntoskrnl!PsGetProcessSessionId` at `0x180050677`
- `ntoskrnl!PsGetProcessSessionId` at `0x180050677`
- `ntoskrnl!PsGetThreadProcess` at `0x180050636`
- `ntoskrnl!PsGetThreadProcess` at `0x180050636`
- `ntoskrnl!KeInitializeSpinLock` at `0x180050370`
- `ntoskrnl!KeInitializeSpinLock` at `0x180050438`
- `ntoskrnl!KeInitializeSpinLock` at `0x180050370`
- `ntoskrnl!KeInitializeSpinLock` at `0x180050438`
- `ntoskrnl!KeWaitForSingleObject` at `0x180050a69`
- `ntoskrnl!KeWaitForSingleObject` at `0x180050a69`

## pseudocode

```c
__int64 __fastcall CKsFilter::Init(
        CKsFilter *this,
        struct _IRP *a2,
        struct _KSFILTERFACTORY_EXT *a3,
        struct _LIST_ENTRY *a4,
        const struct _KSFILTER_DESCRIPTOR *a5,
        const struct KSAUTOMATION_TABLE_ *a6,
        struct KSAUTOMATION_TABLE_ *const *a7,
        struct KSAUTOMATION_TABLE_ *const *a8,
        unsigned int a9)
{
  struct _IRP *v10; // r13
  CKsFilter *v11; // rbx
  __int64 *v12; // rdx
  __int64 Notification; // r15
  const struct KSAUTOMATION_TABLE_ *v14; // rax
  struct _KMUTANT *p_m_ControlMutex; // r12
  __int64 v16; // rax
  __int64 v17; // rsi
  IKsDevice *Device; // rcx
  _KSGATE *p_m_AndGate; // r14
  __int64 v20; // rdx
  __int64 v21; // r8
  __int64 v22; // rax
  NTSTATUS v23; // edi
  int v24; // r9d
  int v25; // r9d
  PEPROCESS InitiatorProcess; // rax
  struct _KTHREAD *Thread; // rcx
  unsigned int ProcessId; // eax
  _EPROCESS *OwningProcess; // rcx
  int (__fastcall *v31)(_KSFILTER *, _KSPROCESSPIN_INDEXENTRY *); // rdx
  char v32; // al
  PKSWORKER *p_m_Worker; // rbp
  unsigned __int64 v34; // rcx
  size_t v35; // rax
  CKsPinFactory *v36; // rax
  unsigned __int64 m_PinFactoriesCount; // rcx
  size_t v38; // rax
  _KSPPROCESSPIN_INDEXENTRY *v39; // rax
  unsigned __int64 v40; // rcx
  size_t v41; // rax
  unsigned int *v42; // rax
  int v43; // eax
  unsigned int v44; // r9d
  CKsPinFactory *v45; // rdi
  unsigned int v46; // r8d
  __int64 v47; // rbp
  struct KSAUTOMATION_TABLE_ *const *v48; // r15
  struct _LIST_ENTRY *p_m_ChildPinList; // r12
  const KSAUTOMATION_TABLE_ *v50; // rax
  int v51; // edx
  unsigned int v52; // ecx
  int v53; // edx
  __int64 v54; // r8
  CKsPinFactory *m_PinFactories; // rcx
  _KSPPROCESSPIN_INDEXENTRY *m_ProcessPinsIndex; // rcx
  unsigned int *m_RelatedPinFactoryIds; // rcx
  int Timeout; // [rsp+20h] [rbp-58h]
  __int64 v59; // [rsp+80h] [rbp+8h]

  v10 = a2;
  v11 = this;
  v12 = WPP_001f1e784e56319d01cbbdcd1f1acdab_Traceguids;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    this = (CKsFilter *)WPP_GLOBAL_Control;
    if ( LOWORD(WPP_GLOBAL_Control->DeviceType) )
    {
      LOBYTE(v12) = 5;
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)v12,
        1,
        15,
        (__int64)WPP_001f1e784e56319d01cbbdcd1f1acdab_Traceguids);
    }
  }
  Notification = KspGetNotification(this, v12);
  v59 = Notification;
  v14 = a6;
  v11->m_Ext.ChildList.Blink = &v11->m_Ext.ChildList;
  p_m_ControlMutex = &v11->m_ControlMutex;
  v11->m_Ext.ChildList.Flink = &v11->m_Ext.ChildList;
  v11->m_Ext.Parent = a3;
  v11->m_Ext.ObjectType = KsObjectTypeFilter;
  v11->m_Ext.Interface = v11;
  v11->m_Ext.Device = a3->Device;
  v11->m_Ext.ParentDevice = a3->ParentDevice;
  v11->m_Ext.FilterControlMutex = &v11->m_ControlMutex;
  v11->m_Ext.AutomationTable = v14;
  v11->m_Ext.UniqueDeviceId.FilterFactory = a3->UniqueDeviceId.FilterFactory;
  v11->m_Ext.UniqueDeviceId.QPCOnCreation = a3->UniqueDeviceId.QPCOnCreation;
  v11->m_Ext.UniqueDeviceId.KSCategory = a3->UniqueDeviceId.KSCategory;
  v11->m_Ext.IsOwnedByFrameServer = KsIsCurrentProcessFrameServer();
  v11->m_Ext.IsStoppedForPrivacy = 0;
  v11->m_Ext.EventList.ListEntry.Blink = &v11->m_Ext.EventList.ListEntry;
  v11->m_Ext.EventList.ListEntry.Flink = &v11->m_Ext.EventList.ListEntry;
  KeInitializeSpinLock(&v11->m_Ext.EventList.SpinLock);
  v11->m_Ext.FilterVerifierContext = 0;
  v16 = KsVerifierAddFilterDispatch(a5, &v11->m_Ext, v11->m_Ext.ParentDevice->DeviceVerifierContext);
  v11->m_Ext.Public.Descriptor = (const KSFILTER_DESCRIPTOR *)v16;
  v17 = v16;
  v11->m_Ext.Public.Context = a3->Public.Context;
  Device = v11->m_Ext.Device;
  v11->m_Ext.Public.Bag = &v11->m_ObjectBag;
  Device->InitializeObjectBag(Device, &v11->m_ObjectBag, &v11->m_ControlMutex);
  v11->m_InputPipes.Blink = &v11->m_InputPipes;
  v11->m_InputPipes.Flink = &v11->m_InputPipes;
  v11->m_OutputPipes.Blink = &v11->m_OutputPipes;
  v11->m_OutputPipes.Flink = &v11->m_OutputPipes;
  v11->m_ProcessOnRelease = 0;
  KeInitializeMutex(&v11->m_Mutex, 0);
  p_m_AndGate = &v11->m_AndGate;
  v11->m_AndGate.Count = 1;
  v11->m_AndGate.NextGate = 0;
  v11->m_CopyFrames.ListEntry.Blink = &v11->m_CopyFrames.ListEntry;
  v11->m_CopyFrames.ListEntry.Flink = &v11->m_CopyFrames.ListEntry;
  KeInitializeSpinLock(&v11->m_CopyFrames.SpinLock);
  v11->m_IsVideoCameraFilter = IsVideoCameraFilter(v11->m_Ext.Parent->Public.FilterDescriptor);
  if ( !Notification )
    goto LABEL_19;
  a6 = (const struct KSAUTOMATION_TABLE_ *)(unsigned int)Feature_IsSystemPowerStateWorking__private_featureState;
  if ( (Feature_IsSystemPowerStateWorking__private_featureState & 0x10) == 0 )
  {
    LODWORD(a6) = Feature_IsSystemPowerStateWorking__private_featureState | 1;
    wil_details_FeatureReporting_ReportUsageToService(wil_details_featureDescriptors_a, a6, 3, 1);
    wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath(a6, 3, wil_details_featureDescriptors_a);
  }
  if ( !v11->m_IsVideoCameraFilter )
    goto LABEL_16;
  v22 = *(_QWORD *)Notification;
  LODWORD(a6) = 0;
  v23 = (*(__int64 (__fastcall **)(__int64, const struct KSAUTOMATION_TABLE_ **))(v22 + 80))(Notification, &a6);
  if ( v23 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v25 = 16;
LABEL_11:
      LOBYTE(v20) = 2;
      WPP_RECORDER_SF_D(
        WPP_GLOBAL_Control->DeviceExtension,
        v20,
        1,
        v25,
        (__int64)WPP_001f1e784e56319d01cbbdcd1f1acdab_Traceguids,
        v23);
    }
    return (unsigned int)v23;
  }
  if ( (int)a6 <= 1 )
  {
LABEL_16:
    LOBYTE(v21) = 1;
    LOBYTE(v20) = v11->m_IsVideoCameraFilter;
    v23 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)Notification + 32LL))(
            Notification,
            v20,
            v21);
    if ( v23 < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        return (unsigned int)v23;
      v25 = 18;
      goto LABEL_11;
    }
LABEL_19:
    v11->m_NodeAutomationTables = a8;
    v11->m_NodesCount = a9;
    v11->m_ChildNodeList.Blink = &v11->m_ChildNodeList;
    v11->m_ChildNodeList.Flink = &v11->m_ChildNodeList;
    KeInitializeMutex(&v11->m_ControlMutex, 0);
    v11->m_FileObject = v10->Tail.Overlay.CurrentStackLocation->FileObject;
    v11->m_FilterThermalState = KSDEVICE_THERMAL_STATE_LOW;
    InitiatorProcess = (PEPROCESS)IoGetInitiatorProcess();
    v11->m_Ext.OwningProcess = InitiatorProcess;
    if ( !InitiatorProcess )
    {
      Thread = v10->Tail.Overlay.Thread;
      if ( !Thread )
        goto LABEL_23;
      InitiatorProcess = PsGetThreadProcess(Thread);
      v11->m_Ext.OwningProcess = InitiatorProcess;
    }
    v11->m_Ext.ImmersiveApp = IsImmersiveApp(InitiatorProcess);
LABEL_23:
    ProcessId = (unsigned int)PsGetProcessId(v11->m_Ext.OwningProcess);
    OwningProcess = v11->m_Ext.OwningProcess;
    v11->m_Ext.OwningProcessId = ProcessId;
    v11->m_Ext.OwningProcessSessionId = PsGetProcessSessionId(OwningProcess);
    if ( *(_QWORD *)v17 )
    {
      v31 = *(int (__fastcall **)(_KSFILTER *, _KSPROCESSPIN_INDEXENTRY *))(*(_QWORD *)v17 + 16LL);
      v11->m_DispatchProcess = v31;
      v11->m_DispatchReset = *(int (__fastcall **)(_KSFILTER *))(*(_QWORD *)v17 + 24LL);
      if ( v31 )
        v11->m_Ext.Device->AddPowerEntry(
          v11->m_Ext.Device,
          &v11->m_PowerEntry,
          (IKsPowerNotify *)((unsigned __int64)&v11->IKsPowerNotify & -(__int64)(v11 != 0)));
    }
    v32 = ~*(_BYTE *)(v17 + 20);
    v11->m_WorkQueueType = DelayedWorkQueue;
    v11->m_ProcessPassive = v32 & 1;
    if ( (*(_DWORD *)(v17 + 20) & 2) != 0 )
      v11->m_WorkQueueType = CriticalWorkQueue;
    if ( (*(_DWORD *)(v17 + 20) & 4) != 0 )
      v11->m_WorkQueueType = HyperCriticalWorkQueue;
    v11->m_ReceiveZeroLengthSamples = (*(_DWORD *)(v17 + 20) & 8) != 0;
    v11->m_WorkItem.WorkerRoutine = (PWORKER_THREAD_ROUTINE)KsWorkSinkItemWorker;
    v11->m_WorkItem.List.Flink = 0;
    v11->m_WorkItem.Parameter = (PVOID)((unsigned __int64)&v11->IKsProcessingObject & -(__int64)(v11 != 0));
    v11->m_StopStreamsWorkItem.WorkerRoutine = (PWORKER_THREAD_ROUTINE)KsStopStreamsWorker;
    v11->m_StopStreamsWorkItem.List.Flink = 0;
    v11->m_StopStreamsWorkItem.Parameter = v11;
    v11->m_AccessRefreshWorkItem.List.Flink = 0;
    p_m_Worker = &v11->m_Worker;
    v11->m_AccessRefreshWorkItem.WorkerRoutine = (PWORKER_THREAD_ROUTINE)KsRefreshAccessWorker;
    v11->m_AccessRefreshWorkItem.Parameter = v11;
    KsRegisterWorker(v11->m_WorkQueueType, &v11->m_Worker);
    v34 = *(unsigned int *)(v17 + 32);
    v11->m_PinFactoriesCount = v34;
    v11->m_PinFactoriesAllocated = *(_DWORD *)(v17 + 32);
    if ( (_DWORD)v34 )
    {
      v35 = 88 * v34;
      if ( !is_mul_ok(v34, 0x58u) )
        v35 = -1;
      v36 = (CKsPinFactory *)operator new(v35, NonPagedPoolNx, 0x6670534Bu);
      m_PinFactoriesCount = v11->m_PinFactoriesCount;
      v11->m_PinFactories = v36;
      v38 = 16 * m_PinFactoriesCount;
      if ( !is_mul_ok(m_PinFactoriesCount, 0x10u) )
        v38 = -1;
      v39 = (_KSPPROCESSPIN_INDEXENTRY *)operator new(v38, NonPagedPoolNx, 0x6970534Bu);
      v40 = v11->m_PinFactoriesCount;
      v11->m_ProcessPinsIndex = v39;
      v41 = 4 * v40;
      if ( !is_mul_ok(v40, 4u) )
        v41 = -1;
      v42 = (unsigned int *)operator new(v41, PagedPool, 0x7052734Bu);
    }
    else
    {
      v11->m_PinFactories = 0;
      v42 = 0;
      v11->m_ProcessPinsIndex = 0;
    }
    v11->m_RelatedPinFactoryIds = v42;
    v43 = CKsFilter::ConstructDefaultTopology(v11);
    v44 = 0;
    if ( v43
      && ((v45 = v11->m_PinFactories) != 0 || !v11->m_PinFactoriesCount)
      && (v11->m_ProcessPinsIndex || !v11->m_PinFactoriesCount)
      && (v11->m_RelatedPinFactoryIds || !v11->m_PinFactoriesCount) )
    {
      v46 = 0;
      v47 = *(_QWORD *)(v17 + 40);
      LODWORD(a6) = 0;
      if ( v11->m_PinFactoriesCount )
      {
        v48 = a7;
        p_m_ChildPinList = &v45->m_ChildPinList;
        do
        {
          v45->m_PinCount = v44;
          v45->m_ChildPinList.Blink = p_m_ChildPinList;
          p_m_ChildPinList->Flink = p_m_ChildPinList;
          v50 = *v48++;
          v45->m_AutomationTable = v50;
          v51 = *(_DWORD *)(v47 + 104);
          if ( (v51 & 0x40) != 0 || (v52 = *(_DWORD *)(v47 + 112)) == 0 )
          {
            if ( (v51 & 0x800000) != 0 && *(_DWORD *)(v47 + 112) != v44 )
            {
              v45->m_InstancesNecessaryForProcessing = 1;
              KsGateTurnInputOff(&v11->m_AndGate);
            }
          }
          else
          {
            v45->m_InstancesNecessaryForProcessing = v52;
            KsGateTurnInputOff(&v11->m_AndGate);
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
              && LOWORD(WPP_GLOBAL_Control->DeviceType) != (_WORD)v44 )
            {
              LOBYTE(v53) = 5;
              WPP_RECORDER_SF_qqd(
                WPP_GLOBAL_Control->DeviceExtension,
                v53,
                v46,
                19,
                (__int64)WPP_001f1e784e56319d01cbbdcd1f1acdab_Traceguids,
                (char)v11,
                (_BYTE)v11 + 88,
                p_m_AndGate->Count);
              v46 = (unsigned int)a6;
              v44 = 0;
            }
          }
          if ( (*(_DWORD *)(v47 + 104) & 0x800000) != 0 )
          {
            v45->m_FrameGate.Count = v44;
            v45->m_FrameGate.NextGate = p_m_AndGate;
            if ( v11 != (CKsFilter *)-600LL )
              KsGateTurnInputOff(&v11->m_AndGate);
            KsGateTurnInputOn(&v45->m_FrameGate);
          }
          if ( (*(_DWORD *)(v47 + 104) & 0x1000000) != 0 )
          {
            v45->m_StateGate.Count = v44;
            v45->m_StateGate.NextGate = p_m_AndGate;
            if ( v11 != (CKsFilter *)-600LL )
              KsGateTurnInputOff(&v11->m_AndGate);
            KsGateTurnInputOn(&v45->m_StateGate);
          }
          ++v46;
          v47 += *(unsigned int *)(v17 + 36);
          LODWORD(a6) = v46;
          ++v45;
          p_m_ChildPinList = (struct _LIST_ENTRY *)((char *)p_m_ChildPinList + 88);
        }
        while ( v46 < v11->m_PinFactoriesCount );
        Notification = v59;
        p_m_ControlMutex = &v11->m_ControlMutex;
        v10 = a2;
      }
      v23 = KsReferenceBusObject(*(KSDEVICE_HEADER *)v10->Tail.Overlay.CurrentStackLocation->DeviceObject->DeviceExtension);
      p_m_Worker = &v11->m_Worker;
    }
    else
    {
      m_PinFactories = v11->m_PinFactories;
      v23 = -1073741670;
      if ( m_PinFactories )
      {
        operator delete(m_PinFactories);
        v11->m_PinFactories = 0;
      }
      m_ProcessPinsIndex = v11->m_ProcessPinsIndex;
      if ( m_ProcessPinsIndex )
      {
        operator delete(m_ProcessPinsIndex);
        v11->m_ProcessPinsIndex = 0;
      }
      m_RelatedPinFactoryIds = v11->m_RelatedPinFactoryIds;
      if ( m_RelatedPinFactoryIds )
      {
        operator delete(m_RelatedPinFactoryIds);
        v11->m_RelatedPinFactoryIds = 0;
      }
    }
    v11->m_Ext.Parent->Interface->AddRef(v11->m_Ext.Parent->Interface);
    if ( v23 < 0 )
      goto LABEL_89;
    v11->AddRef(v11);
    KeWaitForSingleObject(p_m_ControlMutex, Executive, 0, 0, 0);
    v23 = KspCreate(
            (_DWORD)v10,
            2,
            (unsigned int)&off_180079BE0,
            (unsigned int)&off_1800799B0,
            0,
            (__int64)&v11->m_Ext,
            (__int64)a4);
    KeReleaseMutex(p_m_ControlMutex, 0);
    if ( v23 >= 0 )
    {
      if ( Notification && v11->m_IsVideoCameraFilter )
      {
        LOBYTE(v54) = v11->m_Ext.IsOwnedByFrameServer;
        (**(void (__fastcall ***)(__int64, __int64, __int64, _QWORD, unsigned int, __int64, _EPROCESS *))Notification)(
          Notification,
          (__int64)&v11->m_Ext.UniqueDeviceId,
          v54,
          v11->m_Ext.OwningProcessId,
          v11->m_Ext.OwningProcessSessionId,
          (__int64)&v11->m_Ext.Public,
          v11->m_Ext.OwningProcess);
      }
      return (unsigned int)v23;
    }
    if ( v10->IoStatus.Status == -1073741802 && !v10->Tail.Overlay.CurrentStackLocation->FileObject->FsContext )
    {
LABEL_89:
      if ( *(_QWORD *)v17 && v11->m_DispatchProcess )
        v11->m_Ext.Device->RemovePowerEntry(v11->m_Ext.Device, &v11->m_PowerEntry);
      if ( *p_m_Worker )
        KsUnregisterWorker(*p_m_Worker);
      v11->m_Ext.Parent->Interface->Release(v11->m_Ext.Parent->Interface);
    }
    return (unsigned int)v23;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_L(WPP_GLOBAL_Control->DeviceExtension, v20, v21, v24, Timeout, (char)a6);
  return 3221226195LL;
}

```

## disassembly

```asm
0x180050254  mov     r11, rsp
0x180050257  mov     [r11+18h], rbx
0x18005025b  mov     [r11+20h], r9
0x18005025f  mov     [r11+10h], rdx
0x180050263  push    rbp
0x180050264  push    rsi
0x180050265  push    rdi
0x180050266  push    r12
0x180050268  push    r13
0x18005026a  push    r14
0x18005026c  push    r15
0x18005026e  sub     rsp, 40h
0x180050272  mov     rdi, r8
0x180050275  mov     r13, rdx
0x180050278  mov     rbx, rcx
0x18005027b  lea     rax, WPP_RECORDER_INITIALIZED
0x180050282  xor     ebp, ebp
0x180050284  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18005028b  lea     rdx, WPP_001f1e784e56319d01cbbdcd1f1acdab_Traceguids
0x180050292  jz      short loc_1800502B8
0x180050294  mov     rcx, cs:WPP_GLOBAL_Control
0x18005029b  cmp     [rcx+48h], bp
0x18005029f  jz      short loc_1800502B8
0x1800502a1  mov     rcx, [rcx+40h]
0x1800502a5  lea     r9d, [rbp+0Fh]
0x1800502a9  mov     [r11-58h], rdx
0x1800502ad  lea     r8d, [rbp+1]
0x1800502b1  mov     dl, 5
0x1800502b3  call    WPP_RECORDER_SF_
0x1800502b8  call    KspGetNotification
0x1800502bd  mov     r15, rax
0x1800502c0  mov     [rsp+78h+arg_0], rax
0x1800502c8  mov     rax, [rsp+78h+arg_28]
0x1800502d0  lea     rsi, [rbx+58h]
0x1800502d4  mov     [rsi+8], rsi
0x1800502d8  lea     r12, [rbx+190h]
0x1800502df  mov     [rsi], rsi
0x1800502e2  mov     [rbx+80h], rdi
0x1800502e9  mov     dword ptr [rbx+88h], 2
0x1800502f3  mov     [rbx+90h], rbx
0x1800502fa  mov     rcx, [rdi+48h]
0x1800502fe  mov     [rbx+0A0h], rcx
0x180050305  mov     rcx, [rdi+98h]
0x18005030c  mov     [rbx+0F0h], rcx
0x180050313  mov     [rbx+0B0h], r12
0x18005031a  mov     [rbx+0B8h], rax
0x180050321  mov     rax, [rdi+0A0h]
0x180050328  mov     [rbx+108h], rax
0x18005032f  mov     rax, [rdi+0A8h]
0x180050336  mov     [rbx+110h], rax
0x18005033d  movups  xmm0, xmmword ptr [rdi+0B0h]
0x180050344  movdqu  xmmword ptr [rbx+118h], xmm0
0x18005034c  call    KsIsCurrentProcessFrameServer
0x180050351  lea     rcx, [rbx+0C0h]
0x180050358  mov     [rbx+128h], al
0x18005035e  mov     [rbx+140h], bpl
0x180050365  mov     [rcx+8], rcx
0x180050369  mov     [rcx], rcx
0x18005036c  add     rcx, 10h; SpinLock
0x180050370  call    cs:__imp_KeInitializeSpinLock
0x180050377  nop     dword ptr [rax+rax+00h]
0x18005037c  mov     rcx, [rsp+78h+arg_20]
0x180050384  mov     rdx, rsi
0x180050387  mov     [rbx+130h], rbp
0x18005038e  mov     r8, [rbx+0F0h]
0x180050395  mov     r8, [r8+0C0h]
0x18005039c  call    KsVerifierAddFilterDispatch
0x1800503a1  mov     [rbx+0D8h], rax
0x1800503a8  lea     rdx, [rbx+148h]
0x1800503af  mov     rcx, [rdi+90h]
0x1800503b6  mov     rsi, rax
0x1800503b9  mov     [rbx+0E8h], rcx
0x1800503c0  mov     rcx, [rbx+0A0h]
0x1800503c7  mov     [rbx+0E0h], rdx
0x1800503ce  mov     r8, [rcx]
0x1800503d1  mov     rax, [r8+20h]
0x1800503d5  mov     r8, r12
0x1800503d8  call    _guard_dispatch_icall
0x1800503dd  lea     rax, [rbx+1D8h]
0x1800503e4  xor     edx, edx; Level
0x1800503e6  mov     [rax+8], rax
0x1800503ea  lea     rcx, [rbx+290h]; Mutex
0x1800503f1  mov     [rax], rax
0x1800503f4  lea     rax, [rbx+1E8h]
0x1800503fb  mov     [rax+8], rax
0x1800503ff  mov     [rax], rax
0x180050402  mov     [rbx+280h], ebp
0x180050408  call    cs:__imp_KeInitializeMutex
0x18005040f  nop     dword ptr [rax+rax+00h]
0x180050414  lea     rcx, [rbx+2E0h]
0x18005041b  lea     r14, [rbx+258h]
0x180050422  mov     dword ptr [r14], 1
0x180050429  mov     [r14+8], rbp
0x18005042d  mov     [rcx+8], rcx
0x180050431  mov     [rcx], rcx
0x180050434  add     rcx, 10h; SpinLock
0x180050438  call    cs:__imp_KeInitializeSpinLock
0x18005043f  nop     dword ptr [rax+rax+00h]
0x180050444  mov     rcx, [rbx+80h]
0x18005044b  mov     rcx, [rcx+80h]
0x180050452  call    IsVideoCameraFilter
0x180050457  mov     [rbx+300h], al
0x18005045d  test    r15, r15
0x180050460  jz      loc_1800505BF
0x180050466  mov     ecx, cs:Feature_IsSystemPowerStateWorking__private_featureState
0x18005046c  mov     [rsp+78h+arg_28], rbp
0x180050474  mov     dword ptr [rsp+78h+arg_28], ecx
0x18005047b  test    cl, 10h
0x18005047e  jnz     short loc_1800504D0
0x180050480  mov     rax, [rsp+78h+arg_28]
0x180050488  or      ecx, 1
0x18005048b  mov     [rsp+78h+arg_28], rax
0x180050493  mov     edi, 3
0x180050498  mov     dword ptr [rsp+78h+arg_28], ecx
0x18005049f  mov     r8d, edi
0x1800504a2  mov     rdx, [rsp+78h+arg_28]
0x1800504aa  lea     rcx, wil_details_featureDescriptors_a
0x1800504b1  lea     r9d, [rdi-2]
0x1800504b5  call    wil_details_FeatureReporting_ReportUsageToService
0x1800504ba  mov     rcx, [rsp+78h+arg_28]
0x1800504c2  lea     r8, wil_details_featureDescriptors_a
0x1800504c9  mov     edx, edi
0x1800504cb  call    wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath
0x1800504d0  cmp     [rbx+300h], bpl
0x1800504d7  jz      loc_180050582
0x1800504dd  mov     rax, [r15]
0x1800504e0  lea     rdx, [rsp+78h+arg_28]
0x1800504e8  mov     rcx, r15
0x1800504eb  mov     dword ptr [rsp+78h+arg_28], ebp
0x1800504f2  mov     rax, [rax+50h]
0x1800504f6  call    _guard_dispatch_icall
0x1800504fb  mov     edi, eax
0x1800504fd  test    eax, eax
0x1800504ff  jns     short loc_180050548
0x180050501  lea     rcx, WPP_RECORDER_INITIALIZED
0x180050508  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x18005050f  jz      loc_180050B2E
0x180050515  mov     r9d, 10h
0x18005051b  mov     rcx, cs:WPP_GLOBAL_Control
0x180050522  lea     rax, WPP_001f1e784e56319d01cbbdcd1f1acdab_Traceguids
0x180050529  mov     dword ptr [rsp+78h+var_50], edi
0x18005052d  mov     r8d, 1
0x180050533  mov     dl, 2
0x180050535  mov     [rsp+78h+Timeout], rax
0x18005053a  mov     rcx, [rcx+40h]
0x18005053e  call    WPP_RECORDER_SF_D
0x180050543  jmp     loc_180050B2E
0x180050548  mov     eax, dword ptr [rsp+78h+arg_28]
0x18005054f  cmp     eax, 1
0x180050552  jle     short loc_180050582
0x180050554  lea     rcx, WPP_RECORDER_INITIALIZED
0x18005055b  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x180050562  jz      short loc_180050578
0x180050564  mov     rcx, cs:WPP_GLOBAL_Control
0x18005056b  mov     dword ptr [rsp+78h+var_50], eax
0x18005056f  mov     rcx, [rcx+40h]
0x180050573  call    WPP_RECORDER_SF_L
0x180050578  mov     eax, 0C00002D3h
0x18005057d  jmp     loc_180050B30
0x180050582  mov     rax, [r15]
0x180050585  mov     r8b, 1
0x180050588  mov     dl, [rbx+300h]
0x18005058e  mov     rcx, r15
0x180050591  mov     rax, [rax+20h]
0x180050595  call    _guard_dispatch_icall
0x18005059a  mov     edi, eax
0x18005059c  test    eax, eax
0x18005059e  jns     short loc_1800505BF
0x1800505a0  lea     rcx, WPP_RECORDER_INITIALIZED
0x1800505a7  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x1800505ae  jz      loc_180050B2E
0x1800505b4  mov     r9d, 12h
0x1800505ba  jmp     loc_18005051B
0x1800505bf  mov     rax, [rsp+78h+arg_38]
0x1800505c7  xor     edx, edx; Level
0x1800505c9  mov     [rbx+170h], rax
0x1800505d0  mov     rcx, r12; Mutex
0x1800505d3  mov     eax, [rsp+78h+arg_40]
0x1800505da  mov     [rbx+178h], eax
0x1800505e0  lea     rax, [rbx+180h]
0x1800505e7  mov     [rax+8], rax
0x1800505eb  mov     [rax], rax
0x1800505ee  call    cs:__imp_KeInitializeMutex
0x1800505f5  nop     dword ptr [rax+rax+00h]
0x1800505fa  mov     rax, [r13+0B8h]
0x180050601  mov     rcx, [rax+30h]
0x180050605  mov     [rbx+2C8h], rcx
0x18005060c  mov     [rbx+304h], ebp
0x180050612  call    cs:__imp_IoGetInitiatorProcess
0x180050619  nop     dword ptr [rax+rax+00h]
0x18005061e  mov     [rbx+100h], rax
0x180050625  test    rax, rax
0x180050628  jnz     short loc_180050649
0x18005062a  mov     rcx, [r13+98h]; Thread
0x180050631  test    rcx, rcx
0x180050634  jz      short loc_180050657
0x180050636  call    cs:__imp_PsGetThreadProcess
0x18005063d  nop     dword ptr [rax+rax+00h]
0x180050642  mov     [rbx+100h], rax
0x180050649  mov     rcx, rax
0x18005064c  call    IsImmersiveApp
0x180050651  mov     [rbx+0F8h], al
0x180050657  mov     rcx, [rbx+100h]; Process
0x18005065e  call    cs:__imp_PsGetProcessId
0x180050665  nop     dword ptr [rax+rax+00h]
0x18005066a  mov     rcx, [rbx+100h]
0x180050671  mov     [rbx+138h], eax
0x180050677  call    cs:__imp_PsGetProcessSessionId
0x18005067e  nop     dword ptr [rax+rax+00h]
0x180050683  mov     [rbx+13Ch], eax
0x180050689  mov     rdx, [rsi]
0x18005068c  test    rdx, rdx
0x18005068f  jz      short loc_1800506D9
0x180050691  mov     rdx, [rdx+10h]
0x180050695  mov     [rbx+230h], rdx
0x18005069c  mov     rax, [rsi]
0x18005069f  mov     rcx, [rax+18h]
0x1800506a3  mov     [rbx+238h], rcx
0x1800506aa  test    rdx, rdx
0x1800506ad  jz      short loc_1800506D9
0x1800506af  mov     rcx, [rbx+0A0h]
0x1800506b6  lea     rdx, [rbx+10h]
0x1800506ba  mov     rax, rbx
0x1800506bd  neg     rax
0x1800506c0  mov     r9, [rcx]
0x1800506c3  sbb     r8, r8
0x1800506c6  and     r8, rdx
0x1800506c9  lea     rdx, [rbx+268h]
0x1800506d0  mov     rax, [r9+40h]
0x1800506d4  call    _guard_dispatch_icall
0x1800506d9  mov     al, [rsi+14h]
0x1800506dc  not     al
0x1800506de  mov     dword ptr [rbx+220h], 1
0x1800506e8  and     al, 1
0x1800506ea  mov     [rbx+250h], al
0x1800506f0  mov     eax, [rsi+14h]
0x1800506f3  test    al, 2
0x1800506f5  jz      short loc_1800506FD
0x1800506f7  mov     [rbx+220h], ebp
0x1800506fd  mov     eax, [rsi+14h]
0x180050700  test    al, 4
0x180050702  jz      short loc_18005070E
0x180050704  mov     dword ptr [rbx+220h], 2
0x18005070e  mov     eax, [rsi+14h]
0x180050711  lea     rdx, [rbx+8]
0x180050715  shr     eax, 3
0x180050718  and     al, 1
0x18005071a  mov     [rbx+251h], al
0x180050720  lea     rax, KsWorkSinkItemWorker
0x180050727  mov     [rbx+210h], rax
0x18005072e  mov     rax, rbx
0x180050731  mov     [rbx+200h], rbp
0x180050738  neg     rax
0x18005073b  lea     rax, KsStopStreamsWorker
0x180050742  sbb     rcx, rcx
0x180050745  and     rcx, rdx
0x180050748  mov     [rbx+218h], rcx
0x18005074f  mov     [rbx+318h], rax
0x180050756  lea     rax, KsRefreshAccessWorker
0x18005075d  mov     [rbx+308h], rbp
0x180050764  mov     [rbx+320h], rbx
0x18005076b  mov     [rbx+328h], rbp
0x180050772  lea     rbp, [rbx+228h]
0x180050779  mov     [rbx+338h], rax
0x180050780  mov     rdx, rbp; Worker
0x180050783  mov     [rbx+340h], rbx
0x18005078a  mov     ecx, [rbx+220h]; WorkQueueType
0x180050790  call    KsRegisterWorker
0x180050795  mov     ecx, [rsi+20h]
0x180050798  mov     [rbx+1C8h], ecx
0x18005079e  mov     eax, [rsi+20h]
0x1800507a1  mov     [rbx+1CCh], eax
0x1800507a7  test    ecx, ecx
0x1800507a9  jz      loc_18005083A
0x1800507af  mov     eax, 58h ; 'X'
0x1800507b4  mov     edi, 200h
0x1800507b9  mul     rcx
0x1800507bc  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800507c3  mov     r8d, 6670534Bh; unsigned int
0x1800507c9  mov     edx, edi; PoolType
0x1800507cb  cmovb   rax, rcx
0x1800507cf  mov     rcx, rax; Size
0x1800507d2  call    ??2@YAPEAX_KW4_POOL_TYPE@@K@Z; operator new(unsigned __int64,_POOL_TYPE,ulong)
0x1800507d7  mov     ecx, [rbx+1C8h]
0x1800507dd  mov     r8d, 6970534Bh; unsigned int
0x1800507e3  mov     [rbx+1D0h], rax
0x1800507ea  mov     eax, 10h
0x1800507ef  mul     rcx
0x1800507f2  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800507f9  mov     edx, edi; PoolType
0x1800507fb  cmovb   rax, rcx
0x1800507ff  mov     rcx, rax; Size
0x180050802  call    ??2@YAPEAX_KW4_POOL_TYPE@@K@Z; operator new(unsigned __int64,_POOL_TYPE,ulong)
0x180050807  mov     ecx, [rbx+1C8h]
0x18005080d  mov     r8d, 7052734Bh; unsigned int
0x180050813  mov     [rbx+1F8h], rax
0x18005081a  mov     eax, 4
0x18005081f  mul     rcx
0x180050822  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180050829  cmovb   rax, rcx
  ... truncated ...
```
