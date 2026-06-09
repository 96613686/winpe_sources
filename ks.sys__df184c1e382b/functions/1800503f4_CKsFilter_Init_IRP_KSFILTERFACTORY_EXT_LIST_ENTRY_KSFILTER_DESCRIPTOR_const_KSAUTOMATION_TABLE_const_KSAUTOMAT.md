# CKsFilter::Init(_IRP *,_KSFILTERFACTORY_EXT *,_LIST_ENTRY *,_KSFILTER_DESCRIPTOR const *,KSAUTOMATION_TABLE_ const *,KSAUTOMATION_TABLE_ * const *,KSAUTOMATION_TABLE_ * const *,ulong)

- ea: `0x1800503f4`
- end: `0x180050da4`
- name: `?Init@CKsFilter@@QEAAJPEAU_IRP@@PEAU_KSFILTERFACTORY_EXT@@PEAU_LIST_ENTRY@@PEBU_KSFILTER_DESCRIPTOR@@PEBUKSAUTOMATION_TABLE_@@PEBQEAU6@5K@Z`
- size: `2480`
- prototype: `__int64 __fastcall(CKsFilter *this, struct _IRP *, struct _KSFILTERFACTORY_EXT *, struct _LIST_ENTRY *, const struct _KSFILTER_DESCRIPTOR *, const struct KSAUTOMATION_TABLE_ *, struct KSAUTOMATION_TABLE_ *const *, struct KSAUTOMATION_TABLE_ *const *, unsigned int)`
- caller_count: `1`
- callee_count: `22`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, installer_update`

## callers

- `0x1800501b0`

## callees

- `0x1800048a0`
- `0x180005550`
- `0x180005a00`
- `0x18000a2d4`
- `0x18000a9f0`
- `0x18000aa80`
- `0x18000b7bc`
- `0x18000c630`
- `0x18000fe40`
- `0x1800110e8`
- `0x1800113ac`
- `0x1800146c8`
- `0x180019cb0`
- `0x1800332f4`
- `0x18004fea0`
- `0x1800500b0`
- `0x1800503f4`
- `0x180050db0`
- `0x180054fd0`
- `0x180057b30`
- `0x18005b4e8`
- `0x1800754e0`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x180050c52`
- `ntoskrnl!KeReleaseMutex` at `0x180050c52`
- `ntoskrnl!KeInitializeMutex` at `0x1800505a8`
- `ntoskrnl!KeInitializeMutex` at `0x18005078e`
- `ntoskrnl!KeInitializeMutex` at `0x1800505a8`
- `ntoskrnl!KeInitializeMutex` at `0x18005078e`
- `ntoskrnl!IoGetInitiatorProcess` at `0x1800507b2`
- `ntoskrnl!IoGetInitiatorProcess` at `0x1800507b2`
- `ntoskrnl!PsGetProcessId` at `0x1800507fe`
- `ntoskrnl!PsGetProcessId` at `0x1800507fe`
- `ntoskrnl!PsGetProcessSessionId` at `0x180050817`
- `ntoskrnl!PsGetProcessSessionId` at `0x180050817`
- `ntoskrnl!PsGetThreadProcess` at `0x1800507d6`
- `ntoskrnl!PsGetThreadProcess` at `0x1800507d6`
- `ntoskrnl!KeInitializeSpinLock` at `0x180050510`
- `ntoskrnl!KeInitializeSpinLock` at `0x1800505d8`
- `ntoskrnl!KeInitializeSpinLock` at `0x180050510`
- `ntoskrnl!KeInitializeSpinLock` at `0x1800505d8`
- `ntoskrnl!KeWaitForSingleObject` at `0x180050c09`
- `ntoskrnl!KeWaitForSingleObject` at `0x180050c09`

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
  __int64 *v12; // rdx
  __int64 Notification; // r15
  const KSAUTOMATION_TABLE_ *v14; // rax
  struct _KMUTANT *p_m_ControlMutex; // r12
  const KSFILTER_DESCRIPTOR *v16; // rax
  const KSFILTER_DESCRIPTOR *v17; // rsi
  IKsDevice *Device; // rcx
  _KSGATE *p_m_AndGate; // r14
  __int64 v20; // rdx
  __int64 v21; // r8
  __int64 v22; // rax
  int v23; // edi
  int v24; // r9d
  int v25; // r9d
  _EPROCESS *InitiatorProcess; // rax
  struct _KTHREAD *Thread; // rcx
  unsigned int ProcessId; // eax
  _EPROCESS *OwningProcess; // rcx
  int (__fastcall *Process)(_KSFILTER *, _KSPROCESSPIN_INDEXENTRY *); // rdx
  char v32; // al
  void **p_m_Worker; // rbp
  unsigned __int64 PinDescriptorsCount; // rcx
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
  const KSPIN_DESCRIPTOR_EX *PinDescriptors; // rbp
  struct KSAUTOMATION_TABLE_ *const *v48; // r15
  struct _LIST_ENTRY *p_m_ChildPinList; // r12
  const KSAUTOMATION_TABLE_ *v50; // rax
  ULONG Flags; // edx
  unsigned int InstancesNecessary; // ecx
  int v53; // edx
  __int64 v54; // r8
  CKsPinFactory *m_PinFactories; // rcx
  _KSPPROCESSPIN_INDEXENTRY *m_ProcessPinsIndex; // rcx
  unsigned int *m_RelatedPinFactoryIds; // rcx
  int Timeout; // [rsp+20h] [rbp-58h]
  __int64 v59; // [rsp+80h] [rbp+8h]

  v10 = a2;
  v12 = WPP_001f1e784e56319d01cbbdcd1f1acdab_Traceguids;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LOBYTE(v12) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)v12,
      1,
      15,
      (__int64)WPP_001f1e784e56319d01cbbdcd1f1acdab_Traceguids);
  }
  Notification = KspGetNotification();
  v59 = Notification;
  v14 = a6;
  this->m_Ext.ChildList.Blink = &this->m_Ext.ChildList;
  p_m_ControlMutex = &this->m_ControlMutex;
  this->m_Ext.ChildList.Flink = &this->m_Ext.ChildList;
  this->m_Ext.Parent = a3;
  this->m_Ext.ObjectType = KsObjectTypeFilter;
  this->m_Ext.Interface = this;
  this->m_Ext.Device = a3->Device;
  this->m_Ext.ParentDevice = a3->ParentDevice;
  this->m_Ext.FilterControlMutex = &this->m_ControlMutex;
  this->m_Ext.AutomationTable = v14;
  this->m_Ext.UniqueDeviceId.FilterFactory = a3->UniqueDeviceId.FilterFactory;
  this->m_Ext.UniqueDeviceId.QPCOnCreation = a3->UniqueDeviceId.QPCOnCreation;
  this->m_Ext.UniqueDeviceId.KSCategory = a3->UniqueDeviceId.KSCategory;
  this->m_Ext.IsOwnedByFrameServer = KsIsCurrentProcessFrameServer();
  this->m_Ext.IsStoppedForPrivacy = 0;
  this->m_Ext.EventList.ListEntry.Blink = &this->m_Ext.EventList.ListEntry;
  this->m_Ext.EventList.ListEntry.Flink = &this->m_Ext.EventList.ListEntry;
  KeInitializeSpinLock(&this->m_Ext.EventList.SpinLock);
  this->m_Ext.FilterVerifierContext = 0;
  v16 = (const KSFILTER_DESCRIPTOR *)KsVerifierAddFilterDispatch(
                                       a5,
                                       &this->m_Ext,
                                       this->m_Ext.ParentDevice->DeviceVerifierContext);
  this->m_Ext.Public.Descriptor = v16;
  v17 = v16;
  this->m_Ext.Public.Context = a3->Public.Context;
  Device = this->m_Ext.Device;
  this->m_Ext.Public.Bag = &this->m_ObjectBag;
  Device->InitializeObjectBag(Device, &this->m_ObjectBag, &this->m_ControlMutex);
  this->m_InputPipes.Blink = &this->m_InputPipes;
  this->m_InputPipes.Flink = &this->m_InputPipes;
  this->m_OutputPipes.Blink = &this->m_OutputPipes;
  this->m_OutputPipes.Flink = &this->m_OutputPipes;
  this->m_ProcessOnRelease = 0;
  KeInitializeMutex(&this->m_Mutex, 0);
  p_m_AndGate = &this->m_AndGate;
  this->m_AndGate.Count = 1;
  this->m_AndGate.NextGate = 0;
  this->m_CopyFrames.ListEntry.Blink = &this->m_CopyFrames.ListEntry;
  this->m_CopyFrames.ListEntry.Flink = &this->m_CopyFrames.ListEntry;
  KeInitializeSpinLock(&this->m_CopyFrames.SpinLock);
  this->m_IsVideoCameraFilter = IsVideoCameraFilter((PDEVICE_OBJECT)this->m_Ext.Parent->Public.FilterDescriptor);
  if ( !Notification )
    goto LABEL_19;
  a6 = (const struct KSAUTOMATION_TABLE_ *)(unsigned int)Feature_IsSystemPowerStateWorking__private_featureState;
  if ( (Feature_IsSystemPowerStateWorking__private_featureState & 0x10) == 0 )
  {
    LODWORD(a6) = Feature_IsSystemPowerStateWorking__private_featureState | 1;
    wil_details_FeatureReporting_ReportUsageToService(
      (__int64)Feature_IsSystemPowerStateWorking__private_descriptor,
      Feature_IsSystemPowerStateWorking__private_featureState | 1,
      3u,
      1);
    wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath(
      (unsigned __int8)a6,
      3,
      (__int64)Feature_IsSystemPowerStateWorking__private_descriptor);
  }
  if ( !this->m_IsVideoCameraFilter )
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
    LOBYTE(v20) = this->m_IsVideoCameraFilter;
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
    this->m_NodeAutomationTables = a8;
    this->m_NodesCount = a9;
    this->m_ChildNodeList.Blink = &this->m_ChildNodeList;
    this->m_ChildNodeList.Flink = &this->m_ChildNodeList;
    KeInitializeMutex(&this->m_ControlMutex, 0);
    this->m_FileObject = v10->Tail.Overlay.CurrentStackLocation->FileObject;
    this->m_FilterThermalState = KSDEVICE_THERMAL_STATE_LOW;
    InitiatorProcess = (_EPROCESS *)IoGetInitiatorProcess();
    this->m_Ext.OwningProcess = InitiatorProcess;
    if ( !InitiatorProcess )
    {
      Thread = v10->Tail.Overlay.Thread;
      if ( !Thread )
        goto LABEL_23;
      InitiatorProcess = PsGetThreadProcess(Thread);
      this->m_Ext.OwningProcess = InitiatorProcess;
    }
    this->m_Ext.ImmersiveApp = IsImmersiveApp(InitiatorProcess);
LABEL_23:
    ProcessId = (unsigned int)PsGetProcessId(this->m_Ext.OwningProcess);
    OwningProcess = this->m_Ext.OwningProcess;
    this->m_Ext.OwningProcessId = ProcessId;
    this->m_Ext.OwningProcessSessionId = PsGetProcessSessionId(OwningProcess);
    if ( v17->Dispatch )
    {
      Process = (int (__fastcall *)(_KSFILTER *, _KSPROCESSPIN_INDEXENTRY *))v17->Dispatch->Process;
      this->m_DispatchProcess = Process;
      this->m_DispatchReset = (int (__fastcall *)(_KSFILTER *))v17->Dispatch->Reset;
      if ( Process )
        this->m_Ext.Device->AddPowerEntry(
          this->m_Ext.Device,
          &this->m_PowerEntry,
          (IKsPowerNotify *)((unsigned __int64)&this->IKsPowerNotify & -(__int64)(this != 0)));
    }
    v32 = ~LOBYTE(v17->Flags);
    this->m_WorkQueueType = DelayedWorkQueue;
    this->m_ProcessPassive = v32 & 1;
    if ( (v17->Flags & 2) != 0 )
      this->m_WorkQueueType = CriticalWorkQueue;
    if ( (v17->Flags & 4) != 0 )
      this->m_WorkQueueType = HyperCriticalWorkQueue;
    this->m_ReceiveZeroLengthSamples = (v17->Flags & 8) != 0;
    this->m_WorkItem.WorkerRoutine = (PWORKER_THREAD_ROUTINE)KsWorkSinkItemWorker;
    this->m_WorkItem.List.Flink = 0;
    this->m_WorkItem.Parameter = (PVOID)((unsigned __int64)&this->IKsProcessingObject & -(__int64)(this != 0));
    this->m_StopStreamsWorkItem.WorkerRoutine = (PWORKER_THREAD_ROUTINE)KsStopStreamsWorker;
    this->m_StopStreamsWorkItem.List.Flink = 0;
    this->m_StopStreamsWorkItem.Parameter = this;
    this->m_AccessRefreshWorkItem.List.Flink = 0;
    p_m_Worker = &this->m_Worker;
    this->m_AccessRefreshWorkItem.WorkerRoutine = (PWORKER_THREAD_ROUTINE)KsRefreshAccessWorker;
    this->m_AccessRefreshWorkItem.Parameter = this;
    KsRegisterWorker(this->m_WorkQueueType, &this->m_Worker);
    PinDescriptorsCount = v17->PinDescriptorsCount;
    this->m_PinFactoriesCount = PinDescriptorsCount;
    this->m_PinFactoriesAllocated = v17->PinDescriptorsCount;
    if ( (_DWORD)PinDescriptorsCount )
    {
      v35 = 88 * PinDescriptorsCount;
      if ( !is_mul_ok(PinDescriptorsCount, 0x58u) )
        v35 = -1;
      v36 = (CKsPinFactory *)operator new(v35, NonPagedPoolNx, 0x6670534Bu);
      m_PinFactoriesCount = this->m_PinFactoriesCount;
      this->m_PinFactories = v36;
      v38 = 16 * m_PinFactoriesCount;
      if ( !is_mul_ok(m_PinFactoriesCount, 0x10u) )
        v38 = -1;
      v39 = (_KSPPROCESSPIN_INDEXENTRY *)operator new(v38, NonPagedPoolNx, 0x6970534Bu);
      v40 = this->m_PinFactoriesCount;
      this->m_ProcessPinsIndex = v39;
      v41 = 4 * v40;
      if ( !is_mul_ok(v40, 4u) )
        v41 = -1;
      v42 = (unsigned int *)operator new(v41, PagedPool, 0x7052734Bu);
    }
    else
    {
      this->m_PinFactories = 0;
      v42 = 0;
      this->m_ProcessPinsIndex = 0;
    }
    this->m_RelatedPinFactoryIds = v42;
    v43 = CKsFilter::ConstructDefaultTopology(this);
    v44 = 0;
    if ( v43
      && ((v45 = this->m_PinFactories) != 0 || !this->m_PinFactoriesCount)
      && (this->m_ProcessPinsIndex || !this->m_PinFactoriesCount)
      && (this->m_RelatedPinFactoryIds || !this->m_PinFactoriesCount) )
    {
      v46 = 0;
      PinDescriptors = v17->PinDescriptors;
      LODWORD(a6) = 0;
      if ( this->m_PinFactoriesCount )
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
          Flags = PinDescriptors->Flags;
          if ( (Flags & 0x40) != 0 || (InstancesNecessary = PinDescriptors->InstancesNecessary) == 0 )
          {
            if ( (Flags & 0x800000) != 0 && PinDescriptors->InstancesNecessary != v44 )
            {
              v45->m_InstancesNecessaryForProcessing = 1;
              KsGateTurnInputOff(&this->m_AndGate);
            }
          }
          else
          {
            v45->m_InstancesNecessaryForProcessing = InstancesNecessary;
            KsGateTurnInputOff(&this->m_AndGate);
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
                (char)this,
                (_BYTE)this + 88,
                p_m_AndGate->Count);
              v46 = (unsigned int)a6;
              v44 = 0;
            }
          }
          if ( (PinDescriptors->Flags & 0x800000) != 0 )
          {
            v45->m_FrameGate.Count = v44;
            v45->m_FrameGate.NextGate = p_m_AndGate;
            if ( this != (CKsFilter *)-600LL )
              KsGateTurnInputOff(&this->m_AndGate);
            KsGateTurnInputOn(&v45->m_FrameGate);
          }
          if ( (PinDescriptors->Flags & 0x1000000) != 0 )
          {
            v45->m_StateGate.Count = v44;
            v45->m_StateGate.NextGate = p_m_AndGate;
            if ( this != (CKsFilter *)-600LL )
              KsGateTurnInputOff(&this->m_AndGate);
            KsGateTurnInputOn(&v45->m_StateGate);
          }
          ++v46;
          PinDescriptors = (const KSPIN_DESCRIPTOR_EX *)((char *)PinDescriptors + v17->PinDescriptorSize);
          LODWORD(a6) = v46;
          ++v45;
          p_m_ChildPinList = (struct _LIST_ENTRY *)((char *)p_m_ChildPinList + 88);
        }
        while ( v46 < this->m_PinFactoriesCount );
        Notification = v59;
        p_m_ControlMutex = &this->m_ControlMutex;
        v10 = a2;
      }
      v23 = KsReferenceBusObject(*(KSDEVICE_HEADER *)v10->Tail.Overlay.CurrentStackLocation->DeviceObject->DeviceExtension);
      p_m_Worker = &this->m_Worker;
    }
    else
    {
      m_PinFactories = this->m_PinFactories;
      v23 = -1073741670;
      if ( m_PinFactories )
      {
        operator delete(m_PinFactories);
        this->m_PinFactories = 0;
      }
      m_ProcessPinsIndex = this->m_ProcessPinsIndex;
      if ( m_ProcessPinsIndex )
      {
        operator delete(m_ProcessPinsIndex);
        this->m_ProcessPinsIndex = 0;
      }
      m_RelatedPinFactoryIds = this->m_RelatedPinFactoryIds;
      if ( m_RelatedPinFactoryIds )
      {
        operator delete(m_RelatedPinFactoryIds);
        this->m_RelatedPinFactoryIds = 0;
      }
    }
    this->m_Ext.Parent->Interface->AddRef(this->m_Ext.Parent->Interface);
    if ( v23 < 0 )
      goto LABEL_89;
    this->AddRef(this);
    KeWaitForSingleObject(p_m_ControlMutex, Executive, 0, 0, 0);
    v23 = KspCreate(
            (__int64)v10,
            2,
            (__int64)&off_180079BE0,
            (__int64)&off_1800799B0,
            0,
            (__int64)&this->m_Ext,
            (__int64)a4);
    KeReleaseMutex(p_m_ControlMutex, 0);
    if ( v23 >= 0 )
    {
      if ( Notification && this->m_IsVideoCameraFilter )
      {
        LOBYTE(v54) = this->m_Ext.IsOwnedByFrameServer;
        (**(void (__fastcall ***)(__int64, _KSCAMERA_FRAMESERVER_UNIQUEID *, __int64, _QWORD, unsigned int, _KSFILTER *, _EPROCESS *))Notification)(
          Notification,
          &this->m_Ext.UniqueDeviceId,
          v54,
          this->m_Ext.OwningProcessId,
          this->m_Ext.OwningProcessSessionId,
          &this->m_Ext.Public,
          this->m_Ext.OwningProcess);
      }
      return (unsigned int)v23;
    }
    if ( v10->IoStatus.Status == -1073741802 && !v10->Tail.Overlay.CurrentStackLocation->FileObject->FsContext )
    {
LABEL_89:
      if ( v17->Dispatch && this->m_DispatchProcess )
        this->m_Ext.Device->RemovePowerEntry(this->m_Ext.Device, &this->m_PowerEntry);
      if ( *p_m_Worker )
        KsUnregisterWorker(*p_m_Worker);
      this->m_Ext.Parent->Interface->Release(this->m_Ext.Parent->Interface);
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
0x1800503f4  mov     r11, rsp
0x1800503f7  mov     [r11+18h], rbx
0x1800503fb  mov     [r11+20h], r9
0x1800503ff  mov     [r11+10h], rdx
0x180050403  push    rbp
0x180050404  push    rsi
0x180050405  push    rdi
0x180050406  push    r12
0x180050408  push    r13
0x18005040a  push    r14
0x18005040c  push    r15
0x18005040e  sub     rsp, 40h
0x180050412  mov     rdi, r8
0x180050415  mov     r13, rdx
0x180050418  mov     rbx, rcx
0x18005041b  lea     rax, WPP_RECORDER_INITIALIZED
0x180050422  xor     ebp, ebp
0x180050424  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18005042b  lea     rdx, WPP_001f1e784e56319d01cbbdcd1f1acdab_Traceguids
0x180050432  jz      short loc_180050458
0x180050434  mov     rcx, cs:WPP_GLOBAL_Control
0x18005043b  cmp     [rcx+48h], bp
0x18005043f  jz      short loc_180050458
0x180050441  mov     rcx, [rcx+40h]
0x180050445  lea     r9d, [rbp+0Fh]
0x180050449  mov     [r11-58h], rdx
0x18005044d  lea     r8d, [rbp+1]
0x180050451  mov     dl, 5
0x180050453  call    WPP_RECORDER_SF_
0x180050458  call    KspGetNotification
0x18005045d  mov     r15, rax
0x180050460  mov     [rsp+78h+arg_0], rax
0x180050468  mov     rax, [rsp+78h+arg_28]
0x180050470  lea     rsi, [rbx+58h]
0x180050474  mov     [rsi+8], rsi
0x180050478  lea     r12, [rbx+190h]
0x18005047f  mov     [rsi], rsi
0x180050482  mov     [rbx+80h], rdi
0x180050489  mov     dword ptr [rbx+88h], 2
0x180050493  mov     [rbx+90h], rbx
0x18005049a  mov     rcx, [rdi+48h]
0x18005049e  mov     [rbx+0A0h], rcx
0x1800504a5  mov     rcx, [rdi+98h]
0x1800504ac  mov     [rbx+0F0h], rcx
0x1800504b3  mov     [rbx+0B0h], r12
0x1800504ba  mov     [rbx+0B8h], rax
0x1800504c1  mov     rax, [rdi+0A0h]
0x1800504c8  mov     [rbx+108h], rax
0x1800504cf  mov     rax, [rdi+0A8h]
0x1800504d6  mov     [rbx+110h], rax
0x1800504dd  movups  xmm0, xmmword ptr [rdi+0B0h]
0x1800504e4  movdqu  xmmword ptr [rbx+118h], xmm0
0x1800504ec  call    KsIsCurrentProcessFrameServer
0x1800504f1  lea     rcx, [rbx+0C0h]
0x1800504f8  mov     [rbx+128h], al
0x1800504fe  mov     [rbx+140h], bpl
0x180050505  mov     [rcx+8], rcx
0x180050509  mov     [rcx], rcx
0x18005050c  add     rcx, 10h; SpinLock
0x180050510  call    cs:__imp_KeInitializeSpinLock
0x180050517  nop     dword ptr [rax+rax+00h]
0x18005051c  mov     rcx, [rsp+78h+arg_20]
0x180050524  mov     rdx, rsi
0x180050527  mov     [rbx+130h], rbp
0x18005052e  mov     r8, [rbx+0F0h]
0x180050535  mov     r8, [r8+0C0h]
0x18005053c  call    KsVerifierAddFilterDispatch
0x180050541  mov     [rbx+0D8h], rax
0x180050548  lea     rdx, [rbx+148h]
0x18005054f  mov     rcx, [rdi+90h]
0x180050556  mov     rsi, rax
0x180050559  mov     [rbx+0E8h], rcx
0x180050560  mov     rcx, [rbx+0A0h]
0x180050567  mov     [rbx+0E0h], rdx
0x18005056e  mov     r8, [rcx]
0x180050571  mov     rax, [r8+20h]
0x180050575  mov     r8, r12
0x180050578  call    _guard_dispatch_icall
0x18005057d  lea     rax, [rbx+1D8h]
0x180050584  xor     edx, edx; Level
0x180050586  mov     [rax+8], rax
0x18005058a  lea     rcx, [rbx+290h]; Mutex
0x180050591  mov     [rax], rax
0x180050594  lea     rax, [rbx+1E8h]
0x18005059b  mov     [rax+8], rax
0x18005059f  mov     [rax], rax
0x1800505a2  mov     [rbx+280h], ebp
0x1800505a8  call    cs:__imp_KeInitializeMutex
0x1800505af  nop     dword ptr [rax+rax+00h]
0x1800505b4  lea     rcx, [rbx+2E0h]
0x1800505bb  lea     r14, [rbx+258h]
0x1800505c2  mov     dword ptr [r14], 1
0x1800505c9  mov     [r14+8], rbp
0x1800505cd  mov     [rcx+8], rcx
0x1800505d1  mov     [rcx], rcx
0x1800505d4  add     rcx, 10h; SpinLock
0x1800505d8  call    cs:__imp_KeInitializeSpinLock
0x1800505df  nop     dword ptr [rax+rax+00h]
0x1800505e4  mov     rcx, [rbx+80h]
0x1800505eb  mov     rcx, [rcx+80h]
0x1800505f2  call    IsVideoCameraFilter
0x1800505f7  mov     [rbx+300h], al
0x1800505fd  test    r15, r15
0x180050600  jz      loc_18005075F
0x180050606  mov     ecx, cs:Feature_IsSystemPowerStateWorking__private_featureState
0x18005060c  mov     [rsp+78h+arg_28], rbp
0x180050614  mov     dword ptr [rsp+78h+arg_28], ecx
0x18005061b  test    cl, 10h
0x18005061e  jnz     short loc_180050670
0x180050620  mov     rax, [rsp+78h+arg_28]
0x180050628  or      ecx, 1
0x18005062b  mov     [rsp+78h+arg_28], rax
0x180050633  mov     edi, 3
0x180050638  mov     dword ptr [rsp+78h+arg_28], ecx
0x18005063f  mov     r8d, edi
0x180050642  mov     rdx, [rsp+78h+arg_28]
0x18005064a  lea     rcx, Feature_IsSystemPowerStateWorking__private_descriptor
0x180050651  lea     r9d, [rdi-2]
0x180050655  call    wil_details_FeatureReporting_ReportUsageToService
0x18005065a  mov     rcx, [rsp+78h+arg_28]
0x180050662  lea     r8, Feature_IsSystemPowerStateWorking__private_descriptor
0x180050669  mov     edx, edi
0x18005066b  call    wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath
0x180050670  cmp     [rbx+300h], bpl
0x180050677  jz      loc_180050722
0x18005067d  mov     rax, [r15]
0x180050680  lea     rdx, [rsp+78h+arg_28]
0x180050688  mov     rcx, r15
0x18005068b  mov     dword ptr [rsp+78h+arg_28], ebp
0x180050692  mov     rax, [rax+50h]
0x180050696  call    _guard_dispatch_icall
0x18005069b  mov     edi, eax
0x18005069d  test    eax, eax
0x18005069f  jns     short loc_1800506E8
0x1800506a1  lea     rcx, WPP_RECORDER_INITIALIZED
0x1800506a8  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x1800506af  jz      loc_180050CCE
0x1800506b5  mov     r9d, 10h
0x1800506bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800506c2  lea     rax, WPP_001f1e784e56319d01cbbdcd1f1acdab_Traceguids
0x1800506c9  mov     dword ptr [rsp+78h+var_50], edi
0x1800506cd  mov     r8d, 1
0x1800506d3  mov     dl, 2
0x1800506d5  mov     [rsp+78h+Timeout], rax
0x1800506da  mov     rcx, [rcx+40h]
0x1800506de  call    WPP_RECORDER_SF_D
0x1800506e3  jmp     loc_180050CCE
0x1800506e8  mov     eax, dword ptr [rsp+78h+arg_28]
0x1800506ef  cmp     eax, 1
0x1800506f2  jle     short loc_180050722
0x1800506f4  lea     rcx, WPP_RECORDER_INITIALIZED
0x1800506fb  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x180050702  jz      short loc_180050718
0x180050704  mov     rcx, cs:WPP_GLOBAL_Control
0x18005070b  mov     dword ptr [rsp+78h+var_50], eax
0x18005070f  mov     rcx, [rcx+40h]
0x180050713  call    WPP_RECORDER_SF_L
0x180050718  mov     eax, 0C00002D3h
0x18005071d  jmp     loc_180050CD0
0x180050722  mov     rax, [r15]
0x180050725  mov     r8b, 1
0x180050728  mov     dl, [rbx+300h]
0x18005072e  mov     rcx, r15
0x180050731  mov     rax, [rax+20h]
0x180050735  call    _guard_dispatch_icall
0x18005073a  mov     edi, eax
0x18005073c  test    eax, eax
0x18005073e  jns     short loc_18005075F
0x180050740  lea     rcx, WPP_RECORDER_INITIALIZED
0x180050747  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x18005074e  jz      loc_180050CCE
0x180050754  mov     r9d, 12h
0x18005075a  jmp     loc_1800506BB
0x18005075f  mov     rax, [rsp+78h+arg_38]
0x180050767  xor     edx, edx; Level
0x180050769  mov     [rbx+170h], rax
0x180050770  mov     rcx, r12; Mutex
0x180050773  mov     eax, [rsp+78h+arg_40]
0x18005077a  mov     [rbx+178h], eax
0x180050780  lea     rax, [rbx+180h]
0x180050787  mov     [rax+8], rax
0x18005078b  mov     [rax], rax
0x18005078e  call    cs:__imp_KeInitializeMutex
0x180050795  nop     dword ptr [rax+rax+00h]
0x18005079a  mov     rax, [r13+0B8h]
0x1800507a1  mov     rcx, [rax+30h]
0x1800507a5  mov     [rbx+2C8h], rcx
0x1800507ac  mov     [rbx+304h], ebp
0x1800507b2  call    cs:__imp_IoGetInitiatorProcess
0x1800507b9  nop     dword ptr [rax+rax+00h]
0x1800507be  mov     [rbx+100h], rax
0x1800507c5  test    rax, rax
0x1800507c8  jnz     short loc_1800507E9
0x1800507ca  mov     rcx, [r13+98h]; Thread
0x1800507d1  test    rcx, rcx
0x1800507d4  jz      short loc_1800507F7
0x1800507d6  call    cs:__imp_PsGetThreadProcess
0x1800507dd  nop     dword ptr [rax+rax+00h]
0x1800507e2  mov     [rbx+100h], rax
0x1800507e9  mov     rcx, rax
0x1800507ec  call    IsImmersiveApp
0x1800507f1  mov     [rbx+0F8h], al
0x1800507f7  mov     rcx, [rbx+100h]; Process
0x1800507fe  call    cs:__imp_PsGetProcessId
0x180050805  nop     dword ptr [rax+rax+00h]
0x18005080a  mov     rcx, [rbx+100h]
0x180050811  mov     [rbx+138h], eax
0x180050817  call    cs:__imp_PsGetProcessSessionId
0x18005081e  nop     dword ptr [rax+rax+00h]
0x180050823  mov     [rbx+13Ch], eax
0x180050829  mov     rdx, [rsi]
0x18005082c  test    rdx, rdx
0x18005082f  jz      short loc_180050879
0x180050831  mov     rdx, [rdx+10h]
0x180050835  mov     [rbx+230h], rdx
0x18005083c  mov     rax, [rsi]
0x18005083f  mov     rcx, [rax+18h]
0x180050843  mov     [rbx+238h], rcx
0x18005084a  test    rdx, rdx
0x18005084d  jz      short loc_180050879
0x18005084f  mov     rcx, [rbx+0A0h]
0x180050856  lea     rdx, [rbx+10h]
0x18005085a  mov     rax, rbx
0x18005085d  neg     rax
0x180050860  mov     r9, [rcx]
0x180050863  sbb     r8, r8
0x180050866  and     r8, rdx
0x180050869  lea     rdx, [rbx+268h]
0x180050870  mov     rax, [r9+40h]
0x180050874  call    _guard_dispatch_icall
0x180050879  mov     al, [rsi+14h]
0x18005087c  not     al
0x18005087e  mov     dword ptr [rbx+220h], 1
0x180050888  and     al, 1
0x18005088a  mov     [rbx+250h], al
0x180050890  mov     eax, [rsi+14h]
0x180050893  test    al, 2
0x180050895  jz      short loc_18005089D
0x180050897  mov     [rbx+220h], ebp
0x18005089d  mov     eax, [rsi+14h]
0x1800508a0  test    al, 4
0x1800508a2  jz      short loc_1800508AE
0x1800508a4  mov     dword ptr [rbx+220h], 2
0x1800508ae  mov     eax, [rsi+14h]
0x1800508b1  lea     rdx, [rbx+8]
0x1800508b5  shr     eax, 3
0x1800508b8  and     al, 1
0x1800508ba  mov     [rbx+251h], al
0x1800508c0  lea     rax, KsWorkSinkItemWorker
0x1800508c7  mov     [rbx+210h], rax
0x1800508ce  mov     rax, rbx
0x1800508d1  mov     [rbx+200h], rbp
0x1800508d8  neg     rax
0x1800508db  lea     rax, KsStopStreamsWorker
0x1800508e2  sbb     rcx, rcx
0x1800508e5  and     rcx, rdx
0x1800508e8  mov     [rbx+218h], rcx
0x1800508ef  mov     [rbx+318h], rax
0x1800508f6  lea     rax, KsRefreshAccessWorker
0x1800508fd  mov     [rbx+308h], rbp
0x180050904  mov     [rbx+320h], rbx
0x18005090b  mov     [rbx+328h], rbp
0x180050912  lea     rbp, [rbx+228h]
0x180050919  mov     [rbx+338h], rax
0x180050920  mov     rdx, rbp; Worker
0x180050923  mov     [rbx+340h], rbx
0x18005092a  mov     ecx, [rbx+220h]; WorkQueueType
0x180050930  call    KsRegisterWorker
0x180050935  mov     ecx, [rsi+20h]
0x180050938  mov     [rbx+1C8h], ecx
0x18005093e  mov     eax, [rsi+20h]
0x180050941  mov     [rbx+1CCh], eax
0x180050947  test    ecx, ecx
0x180050949  jz      loc_1800509DA
0x18005094f  mov     eax, 58h ; 'X'
0x180050954  mov     edi, 200h
0x180050959  mul     rcx
0x18005095c  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180050963  mov     r8d, 6670534Bh; unsigned int
0x180050969  mov     edx, edi; PoolType
0x18005096b  cmovb   rax, rcx
0x18005096f  mov     rcx, rax; Size
0x180050972  call    ??2@YAPEAX_KW4_POOL_TYPE@@K@Z; operator new(unsigned __int64,_POOL_TYPE,ulong)
0x180050977  mov     ecx, [rbx+1C8h]
0x18005097d  mov     r8d, 6970534Bh; unsigned int
0x180050983  mov     [rbx+1D0h], rax
0x18005098a  mov     eax, 10h
0x18005098f  mul     rcx
0x180050992  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180050999  mov     edx, edi; PoolType
0x18005099b  cmovb   rax, rcx
0x18005099f  mov     rcx, rax; Size
0x1800509a2  call    ??2@YAPEAX_KW4_POOL_TYPE@@K@Z; operator new(unsigned __int64,_POOL_TYPE,ulong)
0x1800509a7  mov     ecx, [rbx+1C8h]
0x1800509ad  mov     r8d, 7052734Bh; unsigned int
0x1800509b3  mov     [rbx+1F8h], rax
0x1800509ba  mov     eax, 4
0x1800509bf  mul     rcx
0x1800509c2  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800509c9  cmovb   rax, rcx
  ... truncated ...
```
