# CKsPin::Init(_IRP *,_KSFILTER_EXT *,_LIST_ENTRY *,KSPIN_CONNECT *,ulong,_KSPIN_DESCRIPTOR_EX const *,KSAUTOMATION_TABLE_ const *,KSAUTOMATION_TABLE_ * const *,ulong,ulong *)

- ea: `0x18005653c`
- end: `0x180056dbd`
- name: `?Init@CKsPin@@QEAAJPEAU_IRP@@PEAU_KSFILTER_EXT@@PEAU_LIST_ENTRY@@PEAUKSPIN_CONNECT@@KPEBU_KSPIN_DESCRIPTOR_EX@@PEBUKSAUTOMATION_TABLE_@@PEBQEAU7@KPEAK@Z`
- size: `2177`
- prototype: `__int64 __fastcall(CKsPin *this, struct _IRP *, struct _KSFILTER_EXT *, struct _LIST_ENTRY *, struct KSPIN_CONNECT *, unsigned int, const struct _KSPIN_DESCRIPTOR_EX *, const struct KSAUTOMATION_TABLE_ *, struct KSAUTOMATION_TABLE_ *const *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18005632c`

## callees

- `0x180005550`
- `0x18000aa80`
- `0x18000b7bc`
- `0x18000fe40`
- `0x1800157cc`
- `0x180019bd0`
- `0x180019cb0`
- `0x18003edd0`
- `0x18003fbec`
- `0x180054f90`
- `0x180054fd0`
- `0x1800558dc`
- `0x18005653c`
- `0x180057b30`
- `0x180075634`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x180056d1a`
- `ntoskrnl!ObfDereferenceObject` at `0x180056d1a`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x180056a63`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x180056a63`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x180056a7a`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x180056a7a`
- `ntoskrnl!KeInitializeMutex` at `0x18005676e`
- `ntoskrnl!KeInitializeMutex` at `0x180056798`
- `ntoskrnl!KeInitializeMutex` at `0x18005676e`
- `ntoskrnl!KeInitializeMutex` at `0x180056798`
- `ntoskrnl!IoFileObjectType` at `0x180056a22`
- `ntoskrnl!KeInitializeSpinLock` at `0x180056640`
- `ntoskrnl!KeInitializeSpinLock` at `0x1800569bb`
- `ntoskrnl!KeInitializeSpinLock` at `0x1800569d9`
- `ntoskrnl!KeInitializeSpinLock` at `0x180056640`
- `ntoskrnl!KeInitializeSpinLock` at `0x1800569bb`
- `ntoskrnl!KeInitializeSpinLock` at `0x1800569d9`
- `ntoskrnl!KeInitializeEvent` at `0x1800567b0`
- `ntoskrnl!KeInitializeEvent` at `0x18005682f`
- `ntoskrnl!KeInitializeEvent` at `0x180056a0a`
- `ntoskrnl!KeInitializeEvent` at `0x1800567b0`
- `ntoskrnl!KeInitializeEvent` at `0x18005682f`
- `ntoskrnl!KeInitializeEvent` at `0x180056a0a`

## pseudocode

```c
__int64 __fastcall CKsPin::Init(
        CKsPin *this,
        struct _IRP *a2,
        struct _KSFILTER_EXT *a3,
        struct _LIST_ENTRY *a4,
        struct KSPIN_CONNECT *a5,
        unsigned int a6,
        const struct _KSPIN_DESCRIPTOR_EX *a7,
        const struct KSAUTOMATION_TABLE_ *a8,
        struct KSAUTOMATION_TABLE_ *const *a9,
        unsigned int a10,
        unsigned int *a11)
{
  __int64 *v14; // rdx
  _KSDEVICE *v15; // rax
  __int64 v16; // rax
  _KMUTANT *FilterControlMutex; // r8
  _BYTE *v18; // r14
  _KSPIN *p_Public; // r12
  int v20; // ecx
  IKsDevice *Device; // rcx
  int v22; // edx
  int v23; // r8d
  void **p_m_Worker; // r15
  _FILE_OBJECT *FileObject; // rcx
  int v26; // ebx
  int (__fastcall *v27)(_KSPIN *); // r8
  char v28; // al
  void **p_m_ProcessingWorker; // r13
  const KSPIN_DESCRIPTOR_EX *Descriptor; // rax
  int v31; // r9d
  bool v32; // zf
  ACCESS_MASK v33; // edx
  int v34; // eax
  IKsConnection *v35; // rcx
  KSPIN_DATAFLOW DataFlow; // ebx
  int v37; // edx
  int v38; // eax
  IKsFilter *m_Parent; // rcx
  NTSTATUS v40; // eax
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rcx
  IKsConnection *m_ConnectedPinInterface; // rcx
  const char *v43; // rdx
  int Object; // [rsp+20h] [rbp-D8h]
  struct KSHANDSHAKE v47; // [rsp+68h] [rbp-90h] BYREF
  struct KSHANDSHAKE v48; // [rsp+88h] [rbp-70h] BYREF

  v14 = WPP_9505c27395793143ec5446714e36088f_Traceguids;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LOBYTE(v14) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)v14,
      1,
      18,
      (__int64)WPP_9505c27395793143ec5446714e36088f_Traceguids);
  }
  this->m_Ext.ChildList.Blink = &this->m_Ext.ChildList;
  this->m_Ext.ChildList.Flink = &this->m_Ext.ChildList;
  this->m_Ext.Parent = a3;
  this->m_Ext.ObjectType = KsObjectTypePin;
  this->m_Ext.Interface = this;
  this->m_Ext.Device = a3->Device;
  this->m_Ext.ParentDevice = a3->ParentDevice;
  this->m_Ext.FilterControlMutex = a3->FilterControlMutex;
  this->m_Ext.AutomationTable = a8;
  this->m_Ext.Reevaluator = (IKsReevaluate *)((unsigned __int64)&this->IKsReevaluate & -(__int64)(this != 0));
  this->m_Ext.EventList.ListEntry.Blink = &this->m_Ext.EventList.ListEntry;
  this->m_Ext.EventList.ListEntry.Flink = &this->m_Ext.EventList.ListEntry;
  KeInitializeSpinLock(&this->m_Ext.EventList.SpinLock);
  this->m_Ext.ProcessPin = &this->m_Process;
  v15 = a3->Device->GetStruct(a3->Device);
  v16 = KsVerifierAddPinDispatch(a7, &this->m_Ext, v15[1].Descriptor);
  FilterControlMutex = this->m_Ext.FilterControlMutex;
  v18 = (_BYTE *)v16;
  p_Public = &this->m_Ext.Public;
  this->m_Ext.Public.Descriptor = (const KSPIN_DESCRIPTOR_EX *)v16;
  this->m_Ext.Public.Context = a3->Public.Context;
  this->m_Ext.Public.Id = a5->PinId;
  v20 = *(_DWORD *)(v16 + 68);
  this->m_Ext.Public.ConnectionIsExternal = 1;
  this->m_Ext.Public.Communication = v20 & 0xFFFFFFFD;
  Device = this->m_Ext.Device;
  this->m_Ext.Public.ConnectionInterface.Set = a5->Interface.Set;
  *(&this->m_Ext.Public.ConnectionInterface.Alignment + 2) = *(&a5->Interface.Alignment + 2);
  this->m_Ext.Public.ConnectionMedium = a5->Medium;
  this->m_Ext.Public.ConnectionPriority = a5->Priority;
  this->m_Ext.Public.DeviceState = KSSTATE_STOP;
  this->m_Ext.Public.ResetState = KSRESET_END;
  this->m_Ext.Public.Bag = &this->m_ObjectBag;
  Device->InitializeObjectBag(Device, &this->m_ObjectBag, FilterControlMutex);
  this->m_Ext.UniqueDeviceId.FilterFactory = a3->UniqueDeviceId.FilterFactory;
  this->m_Ext.UniqueDeviceId.QPCOnCreation = a3->UniqueDeviceId.QPCOnCreation;
  this->m_Ext.UniqueDeviceId.KSCategory = a3->UniqueDeviceId.KSCategory;
  this->m_Ext.IsOwnedByFrameServer = a3->IsOwnedByFrameServer;
  this->m_ProcessOnRelease = 0;
  KeInitializeMutex(&this->m_Mutex, 0);
  this->m_AndGate.Count = 1;
  this->m_AndGate.NextGate = 0;
  KeInitializeMutex(&this->m_DxgFileMutex, 0);
  KeInitializeEvent(&this->m_CompletionSyncEvent, NotificationEvent, 0);
  this->m_CompletionSyncTrigger = 1;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LOBYTE(v22) = 5;
    WPP_RECORDER_SF_qqd(
      WPP_GLOBAL_Control->DeviceExtension,
      v22,
      v23,
      19,
      (__int64)WPP_9505c27395793143ec5446714e36088f_Traceguids,
      (char)this,
      (_BYTE)this - 8,
      this->m_AndGate.Count);
  }
  KsGateTurnInputOff(&this->m_AndGate);
  this->m_ActiveFrameCountPlusOne = 1;
  KeInitializeEvent(&this->m_StopEvent, SynchronizationEvent, 0);
  this->m_Process.Pin = p_Public;
  this->m_Parent = a3->Interface;
  p_m_Worker = &this->m_Worker;
  this->m_NodeAutomationTables = a9;
  this->m_NodesCount = a10;
  this->m_FilterPinCount = a11;
  this->m_ChildNodeList.Blink = &this->m_ChildNodeList;
  this->m_ChildNodeList.Flink = &this->m_ChildNodeList;
  FileObject = a2->Tail.Overlay.CurrentStackLocation->FileObject;
  this->m_FileObject = FileObject;
  this->m_Ext.FileObject = FileObject;
  this->m_WorkItem.WorkerRoutine = (PWORKER_THREAD_ROUTINE)KsWorkSinkItemWorker;
  this->m_WorkItem.List.Flink = 0;
  this->m_WorkItem.Parameter = (PVOID)((unsigned __int64)&this->IKsWorkSink & -(__int64)(this != 0));
  v26 = KsRegisterCountedWorker(HyperCriticalWorkQueue, &this->m_WorkItem, &this->m_Worker);
  if ( *(_QWORD *)v18 )
  {
    v27 = *(int (__fastcall **)(_KSPIN *))(*(_QWORD *)v18 + 16LL);
    this->m_DispatchProcess = v27;
    this->m_DispatchReset = *(void (__fastcall **)(_KSPIN *))(*(_QWORD *)v18 + 24LL);
    this->m_DispatchSetDeviceState = *(int (__fastcall **)(_KSPIN *, KSSTATE, KSSTATE))(*(_QWORD *)v18 + 40LL);
    if ( v27 )
      this->m_Ext.Device->AddPowerEntry(
        this->m_Ext.Device,
        &this->m_PowerEntry,
        (IKsPowerNotify *)((unsigned __int64)&this->IKsPowerNotify & -(__int64)(this != 0)));
  }
  v28 = ~v18[104];
  this->m_WorkQueueType = DelayedWorkQueue;
  this->m_ProcessPassive = v28 & 1;
  if ( (*((_DWORD *)v18 + 26) & 2) != 0 )
    this->m_WorkQueueType = CriticalWorkQueue;
  if ( (*((_DWORD *)v18 + 26) & 4) != 0 )
    this->m_WorkQueueType = HyperCriticalWorkQueue;
  this->m_WorkItemProcessing.List.Flink = 0;
  this->m_WorkItemProcessing.WorkerRoutine = (PWORKER_THREAD_ROUTINE)KsWorkSinkItemWorker;
  this->m_WorkItemProcessing.Parameter = &this->IKsProcessingObject;
  p_m_ProcessingWorker = &this->m_ProcessingWorker;
  KsRegisterWorker(this->m_WorkQueueType, &this->m_ProcessingWorker);
  this->m_IrpsToSend.ListEntry.Blink = &this->m_IrpsToSend.ListEntry;
  this->m_IrpsToSend.ListEntry.Flink = &this->m_IrpsToSend.ListEntry;
  KeInitializeSpinLock(&this->m_IrpsToSend.SpinLock);
  this->m_IrpsOutstanding.ListEntry.Blink = &this->m_IrpsOutstanding.ListEntry;
  this->m_IrpsOutstanding.ListEntry.Flink = &this->m_IrpsOutstanding.ListEntry;
  KeInitializeSpinLock(&this->m_IrpsOutstanding.SpinLock);
  Descriptor = p_Public->Descriptor;
  this->m_State = KSSTATE_STOP;
  this->m_Ext.Public.DataFlow = Descriptor->PinDescriptor.DataFlow;
  KeInitializeEvent(&this->m_ClockEvent, SynchronizationEvent, 0);
  if ( v26 >= 0 && a5->PinToHandle )
  {
    v32 = this->m_Ext.Public.DataFlow == KSPIN_DATAFLOW_OUT;
    v33 = 1179926;
    this->m_Ext.Public.Communication = KSPIN_COMMUNICATION_SOURCE;
    if ( !v32 )
      v33 = 1179785;
    v26 = ObReferenceObjectByHandle(
            a5->PinToHandle,
            v33,
            (POBJECT_TYPE)IoFileObjectType,
            a2->RequestorMode,
            (PVOID *)&this->m_ConnectionFileObject,
            0);
    if ( v26 >= 0 )
      this->m_ConnectionDeviceObject = IoGetRelatedDeviceObject(this->m_ConnectionFileObject);
    p_m_Worker = &this->m_Worker;
  }
  if ( !this->m_ConnectionFileObject )
  {
    if ( v26 >= 0 )
      goto LABEL_33;
LABEL_42:
    if ( *(_QWORD *)v18 && this->m_DispatchProcess )
      this->m_Ext.Device->RemovePowerEntry(this->m_Ext.Device, &this->m_PowerEntry);
    if ( *p_m_Worker )
      KsUnregisterWorker(*p_m_Worker);
    if ( *p_m_ProcessingWorker )
      KsUnregisterWorker(*p_m_ProcessingWorker);
    if ( this->m_ConnectionFileObject )
    {
      m_ConnectedPinInterface = this->m_ConnectedPinInterface;
      if ( m_ConnectedPinInterface )
      {
        m_ConnectedPinInterface->Disconnect(m_ConnectedPinInterface);
        this->m_ConnectedPinInterface->Release(this->m_ConnectedPinInterface);
        this->m_ConnectedPinInterface = 0;
      }
      ObfDereferenceObject(this->m_ConnectionFileObject);
    }
    goto LABEL_53;
  }
  v47.Argument2 = &this->m_Ext.Public;
  v47.Argument1 = &this->IKsConnection;
  v47.ProtocolId = GUID_3ef6ee41_0d41_11d2_beda_00c04f8ef457;
  memset(&v48, 0, sizeof(v48));
  v34 = CKsPin::InitiateHandshake(this, &v47, &v48);
  if ( v34 == -1073741808 )
    goto LABEL_25;
  if ( v34 < 0 )
  {
    v26 = v34;
    goto LABEL_42;
  }
  this->m_ConnectedPinInterface = (IKsConnection *)v48.Argument1;
  this->m_Ext.Public.ConnectionIsExternal = 0;
LABEL_25:
  if ( v26 < 0 )
    goto LABEL_42;
  v35 = this->m_ConnectedPinInterface;
  if ( v35 )
  {
    DataFlow = this->m_Ext.Public.DataFlow;
    if ( v35->GetDataFlow(v35) == DataFlow )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v37) = 4;
        WPP_RECORDER_SF_(
          WPP_GLOBAL_Control->DeviceExtension,
          v37,
          1,
          20,
          (__int64)WPP_9505c27395793143ec5446714e36088f_Traceguids);
      }
      v26 = -1073741811;
      goto LABEL_42;
    }
  }
LABEL_33:
  v26 = CKsPin::SetDataFormat(this, (union KSDATAFORMAT *)&a5[1], a6);
  if ( v26 < 0 )
    goto LABEL_42;
  ++*this->m_FilterPinCount;
  this->AddRef(this);
  v38 = KspCreate(
          (_DWORD)a2,
          3,
          (unsigned int)&off_180079D30,
          (unsigned int)&off_180079960,
          1,
          (__int64)&this->m_Ext,
          (__int64)a4);
  v26 = v38;
  if ( v38 >= 0 )
  {
    if ( v38 == 259 )
      goto LABEL_53;
    m_Parent = this->m_Parent;
    this->m_Header = *(_KSIOBJECT_HEADER **)this->m_FileObject->FsContext;
    v40 = m_Parent->AddProcessPin(m_Parent, &this->m_Process, this);
    v26 = v40;
    if ( v40 >= 0 )
    {
      this->m_AddedProcessPin = 1;
      goto LABEL_53;
    }
    CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
    a2->IoStatus.Status = v40;
    if ( CKsPin::DispatchClose(CurrentStackLocation->DeviceObject, a2) == 259 )
    {
      v26 = 259;
      goto LABEL_53;
    }
  }
  if ( a2->IoStatus.Status == -1073741802 && !a2->Tail.Overlay.CurrentStackLocation->FileObject->FsContext )
    goto LABEL_42;
LABEL_53:
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    v43 = "IN";
    if ( this->m_Ext.Public.DataFlow != KSPIN_DATAFLOW_IN )
      v43 = "OUT";
    WPP_RECORDER_SF_qDdsqq(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)v43,
      (unsigned int)"OUT",
      v31,
      Object,
      (char)this,
      v26,
      this->m_Ext.Public.Id,
      (__int64)v43,
      (char)this->m_ConnectionFileObject,
      (char)this->m_ConnectedPinInterface);
  }
  return (unsigned int)v26;
}

```

## disassembly

```asm
0x18005653c  push    rbx
0x18005653e  push    rbp
0x18005653f  push    rsi
0x180056540  push    rdi
0x180056541  push    r12
0x180056543  push    r13
0x180056545  push    r14
0x180056547  push    r15
0x180056549  sub     rsp, 0B8h
0x180056550  mov     rax, cs:__security_cookie
0x180056557  xor     rax, rsp
0x18005655a  mov     [rsp+0F8h+var_50], rax
0x180056562  mov     rbp, [rsp+0F8h+arg_20]
0x18005656a  mov     r15, r8
0x18005656d  mov     rbx, [rsp+0F8h+arg_30]
0x180056575  mov     rsi, rdx
0x180056578  mov     [rsp+0F8h+var_98], r9
0x18005657d  mov     rdi, rcx
0x180056580  lea     rcx, WPP_RECORDER_INITIALIZED
0x180056587  xor     eax, eax
0x180056589  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x180056590  lea     rdx, WPP_9505c27395793143ec5446714e36088f_Traceguids
0x180056597  jz      short loc_1800565BE
0x180056599  mov     rcx, cs:WPP_GLOBAL_Control
0x1800565a0  cmp     [rcx+48h], ax
0x1800565a4  jz      short loc_1800565BE
0x1800565a6  mov     rcx, [rcx+40h]
0x1800565aa  lea     r9d, [rax+12h]
0x1800565ae  mov     [rsp+0F8h+Object], rdx
0x1800565b3  lea     r8d, [rax+1]
0x1800565b7  mov     dl, 5
0x1800565b9  call    WPP_RECORDER_SF_
0x1800565be  lea     r14, [rdi+80h]
0x1800565c5  mov     [r14+8], r14
0x1800565c9  lea     rdx, [rdi+40h]
0x1800565cd  mov     [r14], r14
0x1800565d0  mov     [rdi+0A8h], r15
0x1800565d7  mov     dword ptr [rdi+0B0h], 3
0x1800565e1  mov     [rdi+0B8h], rdi
0x1800565e8  mov     rax, [r15+48h]
0x1800565ec  mov     [rdi+0C8h], rax
0x1800565f3  mov     rax, [r15+98h]
0x1800565fa  mov     [rdi+198h], rax
0x180056601  mov     rax, [r15+58h]
0x180056605  mov     [rdi+0D8h], rax
0x18005660c  mov     rax, [rsp+0F8h+arg_38]
0x180056614  mov     [rdi+0E0h], rax
0x18005661b  mov     rax, rdi
0x18005661e  neg     rax
0x180056621  sbb     rcx, rcx
0x180056624  and     rcx, rdx
0x180056627  mov     [rdi+0D0h], rcx
0x18005662e  lea     rcx, [rdi+0E8h]
0x180056635  mov     [rcx+8], rcx
0x180056639  mov     [rcx], rcx
0x18005663c  add     rcx, 10h; SpinLock
0x180056640  call    cs:__imp_KeInitializeSpinLock
0x180056647  nop     dword ptr [rax+rax+00h]
0x18005664c  lea     r13, [rdi+200h]
0x180056653  mov     [rdi+188h], r13
0x18005665a  mov     rcx, [r15+48h]
0x18005665e  mov     rax, [rcx]
0x180056661  mov     rax, [rax+18h]
0x180056665  call    _guard_dispatch_icall
0x18005666a  mov     rdx, r14
0x18005666d  mov     rcx, rbx
0x180056670  mov     r8, [rax+40h]
0x180056674  call    KsVerifierAddPinDispatch
0x180056679  mov     r8, [rdi+0D8h]
0x180056680  lea     rdx, [rdi+1D8h]
0x180056687  mov     r14, rax
0x18005668a  lea     r12, [rdi+100h]
0x180056691  mov     [r12], rax
0x180056695  xor     ebx, ebx
0x180056697  mov     rcx, [r15+90h]
0x18005669e  mov     [rdi+110h], rcx
0x1800566a5  mov     ecx, [rbp+30h]
0x1800566a8  mov     [rdi+118h], ecx
0x1800566ae  mov     ecx, [rax+44h]
0x1800566b1  mov     byte ptr [rdi+120h], 1
0x1800566b8  and     ecx, 0FFFFFFFDh
0x1800566bb  mov     [rdi+11Ch], ecx
0x1800566c1  movups  xmm0, xmmword ptr [rbp+0]
0x1800566c5  mov     rcx, [rdi+0C8h]
0x1800566cc  movups  xmmword ptr [rdi+128h], xmm0
0x1800566d3  movsd   xmm1, qword ptr [rbp+10h]
0x1800566d8  movsd   qword ptr [rdi+138h], xmm1
0x1800566e0  movups  xmm0, xmmword ptr [rbp+18h]
0x1800566e4  movups  xmmword ptr [rdi+140h], xmm0
0x1800566eb  movsd   xmm1, qword ptr [rbp+28h]
0x1800566f0  movsd   qword ptr [rdi+150h], xmm1
0x1800566f8  mov     rax, [rbp+40h]
0x1800566fc  mov     [rdi+158h], rax
0x180056703  mov     [rdi+178h], ebx
0x180056709  mov     dword ptr [rdi+17Ch], 1
0x180056713  mov     [rdi+108h], rdx
0x18005671a  mov     rax, [rcx]
0x18005671d  mov     rax, [rax+20h]
0x180056721  call    _guard_dispatch_icall
0x180056726  mov     rax, [r15+0B0h]
0x18005672d  lea     rcx, [rdi+488h]; Mutex
0x180056734  mov     [rdi+1A8h], rax
0x18005673b  xor     edx, edx; Level
0x18005673d  mov     rax, [r15+0B8h]
0x180056744  mov     [rdi+1B0h], rax
0x18005674b  movups  xmm0, xmmword ptr [r15+0C0h]
0x180056753  movdqu  xmmword ptr [rdi+1B8h], xmm0
0x18005675b  mov     al, [r15+0D0h]
0x180056762  mov     [rdi+1C8h], al
0x180056768  mov     [rdi+480h], ebx
0x18005676e  call    cs:__imp_KeInitializeMutex
0x180056775  nop     dword ptr [rax+rax+00h]
0x18005677a  lea     rbx, [rdi+3F8h]
0x180056781  mov     dword ptr [rbx], 1
0x180056787  mov     qword ptr [rbx+8], 0
0x18005678f  lea     rcx, [rdi+538h]; Mutex
0x180056796  xor     edx, edx; Level
0x180056798  call    cs:__imp_KeInitializeMutex
0x18005679f  nop     dword ptr [rax+rax+00h]
0x1800567a4  lea     rcx, [rdi+4D8h]; Event
0x1800567ab  xor     r8d, r8d; State
0x1800567ae  xor     edx, edx; Type
0x1800567b0  call    cs:__imp_KeInitializeEvent
0x1800567b7  nop     dword ptr [rax+rax+00h]
0x1800567bc  mov     dword ptr [rdi+4D4h], 1
0x1800567c6  lea     rax, WPP_RECORDER_INITIALIZED
0x1800567cd  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1800567d4  jz      short loc_180056810
0x1800567d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800567dd  xor     eax, eax
0x1800567df  cmp     [rcx+48h], ax
0x1800567e3  jz      short loc_180056810
0x1800567e5  mov     rcx, [rcx+40h]
0x1800567e9  lea     r9d, [rax+13h]
0x1800567ed  mov     eax, [rbx]
0x1800567ef  mov     dl, 5
0x1800567f1  mov     [rsp+0F8h+var_C0], eax
0x1800567f5  lea     rax, WPP_9505c27395793143ec5446714e36088f_Traceguids
0x1800567fc  mov     [rsp+0F8h+var_C8], rbx
0x180056801  mov     [rsp+0F8h+HandleInformation], rdi
0x180056806  mov     [rsp+0F8h+Object], rax
0x18005680b  call    WPP_RECORDER_SF_qqd
0x180056810  mov     rcx, rbx; Gate
0x180056813  call    KsGateTurnInputOff
0x180056818  mov     eax, 1
0x18005681d  lea     rcx, [rdi+3E0h]; Event
0x180056824  mov     edx, eax; Type
0x180056826  mov     [rdi+3D8h], eax
0x18005682c  xor     r8d, r8d; State
0x18005682f  call    cs:__imp_KeInitializeEvent
0x180056836  nop     dword ptr [rax+rax+00h]
0x18005683b  mov     [r13+0], r12
0x18005683f  lea     rdx, [rdi+2E0h]; CountedWorkItem
0x180056846  mov     rax, [r15+38h]
0x18005684a  lea     r8, [rdi+18h]
0x18005684e  mov     [rdi+288h], rax
0x180056855  lea     r15, [rdi+348h]
0x18005685c  mov     rax, [rsp+0F8h+arg_40]
0x180056864  mov     [rdi+2A0h], rax
0x18005686b  mov     eax, [rsp+0F8h+arg_48]
0x180056872  mov     [rdi+2A8h], eax
0x180056878  mov     rax, [rsp+0F8h+arg_50]
0x180056880  mov     [rdi+2B0h], rax
0x180056887  lea     rax, [rdi+290h]
0x18005688e  mov     [rax+8], rax
0x180056892  mov     [rax], rax
0x180056895  mov     rax, [rsi+0B8h]
0x18005689c  mov     rcx, [rax+30h]
0x1800568a0  lea     rax, KsWorkSinkItemWorker
0x1800568a7  mov     [rdi+350h], rcx
0x1800568ae  mov     [rdi+1A0h], rcx
0x1800568b5  mov     [rdx+10h], rax
0x1800568b9  mov     rax, rdi
0x1800568bc  neg     rax
0x1800568bf  sbb     rcx, rcx
0x1800568c2  xor     r13d, r13d
0x1800568c5  and     rcx, r8
0x1800568c8  mov     [rdx], r13
0x1800568cb  mov     [rdx+18h], rcx
0x1800568cf  mov     r8, r15; Worker
0x1800568d2  lea     ecx, [r13+2]; WorkQueueType
0x1800568d6  call    KsRegisterCountedWorker
0x1800568db  mov     r8, [r14]
0x1800568de  mov     ebx, eax
0x1800568e0  test    r8, r8
0x1800568e3  jz      short loc_18005693B
0x1800568e5  mov     r8, [r8+10h]
0x1800568e9  mov     [rdi+458h], r8
0x1800568f0  mov     rcx, [r14]
0x1800568f3  mov     rdx, [rcx+18h]
0x1800568f7  mov     [rdi+460h], rdx
0x1800568fe  mov     rcx, [r14]
0x180056901  mov     rdx, [rcx+28h]
0x180056905  mov     [rdi+478h], rdx
0x18005690c  test    r8, r8
0x18005690f  jz      short loc_18005693B
0x180056911  mov     rcx, [rdi+0C8h]
0x180056918  lea     rdx, [rdi+10h]
0x18005691c  mov     rax, rdi
0x18005691f  neg     rax
0x180056922  mov     r9, [rcx]
0x180056925  sbb     r8, r8
0x180056928  and     r8, rdx
0x18005692b  lea     rdx, [rdi+408h]
0x180056932  mov     rax, [r9+40h]
0x180056936  call    _guard_dispatch_icall
0x18005693b  mov     al, [r14+68h]
0x18005693f  not     al
0x180056941  mov     dword ptr [rdi+448h], 1
0x18005694b  and     al, 1
0x18005694d  mov     [rdi+420h], al
0x180056953  mov     eax, [r14+68h]
0x180056957  test    al, 2
0x180056959  jz      short loc_180056962
0x18005695b  mov     [rdi+448h], r13d
0x180056962  mov     eax, [r14+68h]
0x180056966  test    al, 4
0x180056968  jz      short loc_180056974
0x18005696a  mov     dword ptr [rdi+448h], 2
0x180056974  lea     rcx, KsWorkSinkItemWorker
0x18005697b  mov     [rdi+428h], r13
0x180056982  lea     rax, [rdi+8]
0x180056986  mov     [rdi+438h], rcx
0x18005698d  mov     [rdi+440h], rax
0x180056994  lea     r13, [rdi+450h]
0x18005699b  mov     ecx, [rdi+448h]; WorkQueueType
0x1800569a1  mov     rdx, r13; Worker
0x1800569a4  call    KsRegisterWorker
0x1800569a9  lea     rcx, [rdi+300h]
0x1800569b0  mov     [rcx+8], rcx
0x1800569b4  mov     [rcx], rcx
0x1800569b7  add     rcx, 10h; SpinLock
0x1800569bb  call    cs:__imp_KeInitializeSpinLock
0x1800569c2  nop     dword ptr [rax+rax+00h]
0x1800569c7  lea     rcx, [rdi+318h]
0x1800569ce  mov     [rcx+8], rcx
0x1800569d2  mov     [rcx], rcx
0x1800569d5  add     rcx, 10h; SpinLock
0x1800569d9  call    cs:__imp_KeInitializeSpinLock
0x1800569e0  nop     dword ptr [rax+rax+00h]
0x1800569e5  mov     rax, [r12]
0x1800569e9  xor     r8d, r8d; State
0x1800569ec  mov     dword ptr [rdi+2CCh], 0
0x1800569f6  mov     ecx, [rax+40h]
0x1800569f9  lea     edx, [r8+1]; Type
0x1800569fd  mov     [rdi+174h], ecx
0x180056a03  lea     rcx, [rdi+3A8h]; Event
0x180056a0a  call    cs:__imp_KeInitializeEvent
0x180056a11  nop     dword ptr [rax+rax+00h]
0x180056a16  xor     ecx, ecx
0x180056a18  test    ebx, ebx
0x180056a1a  js      short loc_180056A96
0x180056a1c  cmp     [rbp+38h], rcx
0x180056a20  jz      short loc_180056A96
0x180056a22  mov     r8, cs:__imp_IoFileObjectType
0x180056a29  lea     r15, [rdi+358h]
0x180056a30  cmp     dword ptr [rdi+174h], 2
0x180056a37  mov     edx, 120116h
0x180056a3c  mov     dword ptr [rdi+11Ch], 2
0x180056a46  mov     eax, 120089h
0x180056a4b  mov     r9b, [rsi+40h]; AccessMode
0x180056a4f  cmovnz  edx, eax; DesiredAccess
0x180056a52  mov     r8, [r8]; ObjectType
0x180056a55  mov     [rsp+0F8h+HandleInformation], rcx; HandleInformation
0x180056a5a  mov     rcx, [rbp+38h]; Handle
0x180056a5e  mov     [rsp+0F8h+Object], r15; Object
0x180056a63  call    cs:__imp_ObReferenceObjectByHandle
0x180056a6a  nop     dword ptr [rax+rax+00h]
0x180056a6f  xor     ecx, ecx
0x180056a71  mov     ebx, eax
0x180056a73  test    eax, eax
0x180056a75  js      short loc_180056A8F
0x180056a77  mov     rcx, [r15]; FileObject
0x180056a7a  call    cs:__imp_IoGetRelatedDeviceObject
0x180056a81  nop     dword ptr [rax+rax+00h]
0x180056a86  mov     [rdi+360h], rax
0x180056a8d  xor     ecx, ecx
0x180056a8f  lea     r15, [rdi+348h]
0x180056a96  cmp     [rdi+358h], rcx
0x180056a9d  jz      loc_180056B84
0x180056aa3  movups  xmm1, xmmword ptr cs:_GUID_3ef6ee41_0d41_11d2_beda_00c04f8ef457.Data1
0x180056aaa  mov     [rsp+0F8h+var_90.Argument2], r12
0x180056ab2  lea     rax, [rdi+20h]
0x180056ab6  xorps   xmm0, xmm0
0x180056ab9  mov     [rsp+0F8h+var_90.Argument1], rax
0x180056abe  lea     r8, [rsp+0F8h+var_70]; struct KSHANDSHAKE *
0x180056ac6  mov     rcx, rdi; this
0x180056ac9  lea     rdx, [rsp+0F8h+var_90]; struct KSHANDSHAKE *
0x180056ace  movdqu  xmmword ptr [rsp+0F8h+var_90.ProtocolId.Data1], xmm1
0x180056ad4  movups  xmmword ptr [rsp+0F8h+var_70.ProtocolId.Data1], xmm0
0x180056adc  movups  xmmword ptr [rsp+0F8h+var_70.Argument1], xmm0
0x180056ae4  call    ?InitiateHandshake@CKsPin@@QEAAJPEAUKSHANDSHAKE@@0@Z; CKsPin::InitiateHandshake(KSHANDSHAKE *,KSHANDSHAKE *)
0x180056ae9  xor     r12d, r12d
0x180056aec  cmp     eax, 0C0000010h
0x180056af1  jz      short loc_180056B11
0x180056af3  test    eax, eax
0x180056af5  js      loc_180056B7D
0x180056afb  mov     rax, [rsp+0F8h+var_70.Argument1]
0x180056b03  mov     [rdi+340h], rax
0x180056b0a  mov     [rdi+120h], r12b
  ... truncated ...
```
