# CKsPin::Init(_IRP *,_KSFILTER_EXT *,_LIST_ENTRY *,KSPIN_CONNECT *,ulong,_KSPIN_DESCRIPTOR_EX const *,KSAUTOMATION_TABLE_ const *,KSAUTOMATION_TABLE_ * const *,ulong,ulong *)

- ea: `0x18005639c`
- end: `0x180056c1d`
- name: `?Init@CKsPin@@QEAAJPEAU_IRP@@PEAU_KSFILTER_EXT@@PEAU_LIST_ENTRY@@PEAUKSPIN_CONNECT@@KPEBU_KSPIN_DESCRIPTOR_EX@@PEBUKSAUTOMATION_TABLE_@@PEBQEAU7@KPEAK@Z`
- size: `2177`
- prototype: `__int64 __fastcall(CKsPin *this, struct _IRP *, struct _KSFILTER_EXT *, struct _LIST_ENTRY *, struct KSPIN_CONNECT *, unsigned int, const struct _KSPIN_DESCRIPTOR_EX *, const struct KSAUTOMATION_TABLE_ *, struct KSAUTOMATION_TABLE_ *const *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18005618c`

## callees

- `0x180005550`
- `0x18000aa80`
- `0x18000b7bc`
- `0x18000fe2c`
- `0x18001577c`
- `0x180019b80`
- `0x180019c60`
- `0x18003ede0`
- `0x18003fbfc`
- `0x180054df0`
- `0x180054e30`
- `0x18005573c`
- `0x18005639c`
- `0x180057990`
- `0x180075634`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x180056b7a`
- `ntoskrnl!ObfDereferenceObject` at `0x180056b7a`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1800568c3`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1800568c3`
- `ntoskrnl!KeInitializeMutex` at `0x1800565ce`
- `ntoskrnl!KeInitializeMutex` at `0x1800565f8`
- `ntoskrnl!KeInitializeMutex` at `0x1800565ce`
- `ntoskrnl!KeInitializeMutex` at `0x1800565f8`
- `ntoskrnl!IoFileObjectType` at `0x180056882`
- `ntoskrnl!KeInitializeSpinLock` at `0x1800564a0`
- `ntoskrnl!KeInitializeSpinLock` at `0x18005681b`
- `ntoskrnl!KeInitializeSpinLock` at `0x180056839`
- `ntoskrnl!KeInitializeSpinLock` at `0x1800564a0`
- `ntoskrnl!KeInitializeSpinLock` at `0x18005681b`
- `ntoskrnl!KeInitializeSpinLock` at `0x180056839`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x1800568da`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x1800568da`
- `ntoskrnl!KeInitializeEvent` at `0x180056610`
- `ntoskrnl!KeInitializeEvent` at `0x18005668f`
- `ntoskrnl!KeInitializeEvent` at `0x18005686a`
- `ntoskrnl!KeInitializeEvent` at `0x180056610`
- `ntoskrnl!KeInitializeEvent` at `0x18005668f`
- `ntoskrnl!KeInitializeEvent` at `0x18005686a`

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
  NTSTATUS v26; // ebx
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

  v14 = WPP_a6ecdf8dfd443675814f995f5d4f1b17_Traceguids;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LOBYTE(v14) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)v14,
      1,
      18,
      (__int64)WPP_a6ecdf8dfd443675814f995f5d4f1b17_Traceguids);
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
      (__int64)WPP_a6ecdf8dfd443675814f995f5d4f1b17_Traceguids,
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
          (__int64)WPP_a6ecdf8dfd443675814f995f5d4f1b17_Traceguids);
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
0x18005639c  push    rbx
0x18005639e  push    rbp
0x18005639f  push    rsi
0x1800563a0  push    rdi
0x1800563a1  push    r12
0x1800563a3  push    r13
0x1800563a5  push    r14
0x1800563a7  push    r15
0x1800563a9  sub     rsp, 0B8h
0x1800563b0  mov     rax, cs:__security_cookie
0x1800563b7  xor     rax, rsp
0x1800563ba  mov     [rsp+0F8h+var_50], rax
0x1800563c2  mov     rbp, [rsp+0F8h+arg_20]
0x1800563ca  mov     r15, r8
0x1800563cd  mov     rbx, [rsp+0F8h+arg_30]
0x1800563d5  mov     rsi, rdx
0x1800563d8  mov     [rsp+0F8h+var_98], r9
0x1800563dd  mov     rdi, rcx
0x1800563e0  lea     rcx, WPP_RECORDER_INITIALIZED
0x1800563e7  xor     eax, eax
0x1800563e9  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x1800563f0  lea     rdx, WPP_a6ecdf8dfd443675814f995f5d4f1b17_Traceguids
0x1800563f7  jz      short loc_18005641E
0x1800563f9  mov     rcx, cs:WPP_GLOBAL_Control
0x180056400  cmp     [rcx+48h], ax
0x180056404  jz      short loc_18005641E
0x180056406  mov     rcx, [rcx+40h]
0x18005640a  lea     r9d, [rax+12h]
0x18005640e  mov     [rsp+0F8h+Object], rdx
0x180056413  lea     r8d, [rax+1]
0x180056417  mov     dl, 5
0x180056419  call    WPP_RECORDER_SF_
0x18005641e  lea     r14, [rdi+80h]
0x180056425  mov     [r14+8], r14
0x180056429  lea     rdx, [rdi+40h]
0x18005642d  mov     [r14], r14
0x180056430  mov     [rdi+0A8h], r15
0x180056437  mov     dword ptr [rdi+0B0h], 3
0x180056441  mov     [rdi+0B8h], rdi
0x180056448  mov     rax, [r15+48h]
0x18005644c  mov     [rdi+0C8h], rax
0x180056453  mov     rax, [r15+98h]
0x18005645a  mov     [rdi+198h], rax
0x180056461  mov     rax, [r15+58h]
0x180056465  mov     [rdi+0D8h], rax
0x18005646c  mov     rax, [rsp+0F8h+arg_38]
0x180056474  mov     [rdi+0E0h], rax
0x18005647b  mov     rax, rdi
0x18005647e  neg     rax
0x180056481  sbb     rcx, rcx
0x180056484  and     rcx, rdx
0x180056487  mov     [rdi+0D0h], rcx
0x18005648e  lea     rcx, [rdi+0E8h]
0x180056495  mov     [rcx+8], rcx
0x180056499  mov     [rcx], rcx
0x18005649c  add     rcx, 10h; SpinLock
0x1800564a0  call    cs:__imp_KeInitializeSpinLock
0x1800564a7  nop     dword ptr [rax+rax+00h]
0x1800564ac  lea     r13, [rdi+200h]
0x1800564b3  mov     [rdi+188h], r13
0x1800564ba  mov     rcx, [r15+48h]
0x1800564be  mov     rax, [rcx]
0x1800564c1  mov     rax, [rax+18h]
0x1800564c5  call    _guard_dispatch_icall
0x1800564ca  mov     rdx, r14
0x1800564cd  mov     rcx, rbx
0x1800564d0  mov     r8, [rax+40h]
0x1800564d4  call    KsVerifierAddPinDispatch
0x1800564d9  mov     r8, [rdi+0D8h]
0x1800564e0  lea     rdx, [rdi+1D8h]
0x1800564e7  mov     r14, rax
0x1800564ea  lea     r12, [rdi+100h]
0x1800564f1  mov     [r12], rax
0x1800564f5  xor     ebx, ebx
0x1800564f7  mov     rcx, [r15+90h]
0x1800564fe  mov     [rdi+110h], rcx
0x180056505  mov     ecx, [rbp+30h]
0x180056508  mov     [rdi+118h], ecx
0x18005650e  mov     ecx, [rax+44h]
0x180056511  mov     byte ptr [rdi+120h], 1
0x180056518  and     ecx, 0FFFFFFFDh
0x18005651b  mov     [rdi+11Ch], ecx
0x180056521  movups  xmm0, xmmword ptr [rbp+0]
0x180056525  mov     rcx, [rdi+0C8h]
0x18005652c  movups  xmmword ptr [rdi+128h], xmm0
0x180056533  movsd   xmm1, qword ptr [rbp+10h]
0x180056538  movsd   qword ptr [rdi+138h], xmm1
0x180056540  movups  xmm0, xmmword ptr [rbp+18h]
0x180056544  movups  xmmword ptr [rdi+140h], xmm0
0x18005654b  movsd   xmm1, qword ptr [rbp+28h]
0x180056550  movsd   qword ptr [rdi+150h], xmm1
0x180056558  mov     rax, [rbp+40h]
0x18005655c  mov     [rdi+158h], rax
0x180056563  mov     [rdi+178h], ebx
0x180056569  mov     dword ptr [rdi+17Ch], 1
0x180056573  mov     [rdi+108h], rdx
0x18005657a  mov     rax, [rcx]
0x18005657d  mov     rax, [rax+20h]
0x180056581  call    _guard_dispatch_icall
0x180056586  mov     rax, [r15+0B0h]
0x18005658d  lea     rcx, [rdi+488h]; Mutex
0x180056594  mov     [rdi+1A8h], rax
0x18005659b  xor     edx, edx; Level
0x18005659d  mov     rax, [r15+0B8h]
0x1800565a4  mov     [rdi+1B0h], rax
0x1800565ab  movups  xmm0, xmmword ptr [r15+0C0h]
0x1800565b3  movdqu  xmmword ptr [rdi+1B8h], xmm0
0x1800565bb  mov     al, [r15+0D0h]
0x1800565c2  mov     [rdi+1C8h], al
0x1800565c8  mov     [rdi+480h], ebx
0x1800565ce  call    cs:__imp_KeInitializeMutex
0x1800565d5  nop     dword ptr [rax+rax+00h]
0x1800565da  lea     rbx, [rdi+3F8h]
0x1800565e1  mov     dword ptr [rbx], 1
0x1800565e7  mov     qword ptr [rbx+8], 0
0x1800565ef  lea     rcx, [rdi+538h]; Mutex
0x1800565f6  xor     edx, edx; Level
0x1800565f8  call    cs:__imp_KeInitializeMutex
0x1800565ff  nop     dword ptr [rax+rax+00h]
0x180056604  lea     rcx, [rdi+4D8h]; Event
0x18005660b  xor     r8d, r8d; State
0x18005660e  xor     edx, edx; Type
0x180056610  call    cs:__imp_KeInitializeEvent
0x180056617  nop     dword ptr [rax+rax+00h]
0x18005661c  mov     dword ptr [rdi+4D4h], 1
0x180056626  lea     rax, WPP_RECORDER_INITIALIZED
0x18005662d  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180056634  jz      short loc_180056670
0x180056636  mov     rcx, cs:WPP_GLOBAL_Control
0x18005663d  xor     eax, eax
0x18005663f  cmp     [rcx+48h], ax
0x180056643  jz      short loc_180056670
0x180056645  mov     rcx, [rcx+40h]
0x180056649  lea     r9d, [rax+13h]
0x18005664d  mov     eax, [rbx]
0x18005664f  mov     dl, 5
0x180056651  mov     [rsp+0F8h+var_C0], eax
0x180056655  lea     rax, WPP_a6ecdf8dfd443675814f995f5d4f1b17_Traceguids
0x18005665c  mov     [rsp+0F8h+var_C8], rbx
0x180056661  mov     [rsp+0F8h+HandleInformation], rdi
0x180056666  mov     [rsp+0F8h+Object], rax
0x18005666b  call    WPP_RECORDER_SF_qqd
0x180056670  mov     rcx, rbx; Gate
0x180056673  call    KsGateTurnInputOff
0x180056678  mov     eax, 1
0x18005667d  lea     rcx, [rdi+3E0h]; Event
0x180056684  mov     edx, eax; Type
0x180056686  mov     [rdi+3D8h], eax
0x18005668c  xor     r8d, r8d; State
0x18005668f  call    cs:__imp_KeInitializeEvent
0x180056696  nop     dword ptr [rax+rax+00h]
0x18005669b  mov     [r13+0], r12
0x18005669f  lea     rdx, [rdi+2E0h]; CountedWorkItem
0x1800566a6  mov     rax, [r15+38h]
0x1800566aa  lea     r8, [rdi+18h]
0x1800566ae  mov     [rdi+288h], rax
0x1800566b5  lea     r15, [rdi+348h]
0x1800566bc  mov     rax, [rsp+0F8h+arg_40]
0x1800566c4  mov     [rdi+2A0h], rax
0x1800566cb  mov     eax, [rsp+0F8h+arg_48]
0x1800566d2  mov     [rdi+2A8h], eax
0x1800566d8  mov     rax, [rsp+0F8h+arg_50]
0x1800566e0  mov     [rdi+2B0h], rax
0x1800566e7  lea     rax, [rdi+290h]
0x1800566ee  mov     [rax+8], rax
0x1800566f2  mov     [rax], rax
0x1800566f5  mov     rax, [rsi+0B8h]
0x1800566fc  mov     rcx, [rax+30h]
0x180056700  lea     rax, KsWorkSinkItemWorker
0x180056707  mov     [rdi+350h], rcx
0x18005670e  mov     [rdi+1A0h], rcx
0x180056715  mov     [rdx+10h], rax
0x180056719  mov     rax, rdi
0x18005671c  neg     rax
0x18005671f  sbb     rcx, rcx
0x180056722  xor     r13d, r13d
0x180056725  and     rcx, r8
0x180056728  mov     [rdx], r13
0x18005672b  mov     [rdx+18h], rcx
0x18005672f  mov     r8, r15; Worker
0x180056732  lea     ecx, [r13+2]; WorkQueueType
0x180056736  call    KsRegisterCountedWorker
0x18005673b  mov     r8, [r14]
0x18005673e  mov     ebx, eax
0x180056740  test    r8, r8
0x180056743  jz      short loc_18005679B
0x180056745  mov     r8, [r8+10h]
0x180056749  mov     [rdi+458h], r8
0x180056750  mov     rcx, [r14]
0x180056753  mov     rdx, [rcx+18h]
0x180056757  mov     [rdi+460h], rdx
0x18005675e  mov     rcx, [r14]
0x180056761  mov     rdx, [rcx+28h]
0x180056765  mov     [rdi+478h], rdx
0x18005676c  test    r8, r8
0x18005676f  jz      short loc_18005679B
0x180056771  mov     rcx, [rdi+0C8h]
0x180056778  lea     rdx, [rdi+10h]
0x18005677c  mov     rax, rdi
0x18005677f  neg     rax
0x180056782  mov     r9, [rcx]
0x180056785  sbb     r8, r8
0x180056788  and     r8, rdx
0x18005678b  lea     rdx, [rdi+408h]
0x180056792  mov     rax, [r9+40h]
0x180056796  call    _guard_dispatch_icall
0x18005679b  mov     al, [r14+68h]
0x18005679f  not     al
0x1800567a1  mov     dword ptr [rdi+448h], 1
0x1800567ab  and     al, 1
0x1800567ad  mov     [rdi+420h], al
0x1800567b3  mov     eax, [r14+68h]
0x1800567b7  test    al, 2
0x1800567b9  jz      short loc_1800567C2
0x1800567bb  mov     [rdi+448h], r13d
0x1800567c2  mov     eax, [r14+68h]
0x1800567c6  test    al, 4
0x1800567c8  jz      short loc_1800567D4
0x1800567ca  mov     dword ptr [rdi+448h], 2
0x1800567d4  lea     rcx, KsWorkSinkItemWorker
0x1800567db  mov     [rdi+428h], r13
0x1800567e2  lea     rax, [rdi+8]
0x1800567e6  mov     [rdi+438h], rcx
0x1800567ed  mov     [rdi+440h], rax
0x1800567f4  lea     r13, [rdi+450h]
0x1800567fb  mov     ecx, [rdi+448h]; WorkQueueType
0x180056801  mov     rdx, r13; Worker
0x180056804  call    KsRegisterWorker
0x180056809  lea     rcx, [rdi+300h]
0x180056810  mov     [rcx+8], rcx
0x180056814  mov     [rcx], rcx
0x180056817  add     rcx, 10h; SpinLock
0x18005681b  call    cs:__imp_KeInitializeSpinLock
0x180056822  nop     dword ptr [rax+rax+00h]
0x180056827  lea     rcx, [rdi+318h]
0x18005682e  mov     [rcx+8], rcx
0x180056832  mov     [rcx], rcx
0x180056835  add     rcx, 10h; SpinLock
0x180056839  call    cs:__imp_KeInitializeSpinLock
0x180056840  nop     dword ptr [rax+rax+00h]
0x180056845  mov     rax, [r12]
0x180056849  xor     r8d, r8d; State
0x18005684c  mov     dword ptr [rdi+2CCh], 0
0x180056856  mov     ecx, [rax+40h]
0x180056859  lea     edx, [r8+1]; Type
0x18005685d  mov     [rdi+174h], ecx
0x180056863  lea     rcx, [rdi+3A8h]; Event
0x18005686a  call    cs:__imp_KeInitializeEvent
0x180056871  nop     dword ptr [rax+rax+00h]
0x180056876  xor     ecx, ecx
0x180056878  test    ebx, ebx
0x18005687a  js      short loc_1800568F6
0x18005687c  cmp     [rbp+38h], rcx
0x180056880  jz      short loc_1800568F6
0x180056882  mov     r8, cs:__imp_IoFileObjectType
0x180056889  lea     r15, [rdi+358h]
0x180056890  cmp     dword ptr [rdi+174h], 2
0x180056897  mov     edx, 120116h
0x18005689c  mov     dword ptr [rdi+11Ch], 2
0x1800568a6  mov     eax, 120089h
0x1800568ab  mov     r9b, [rsi+40h]; AccessMode
0x1800568af  cmovnz  edx, eax; DesiredAccess
0x1800568b2  mov     r8, [r8]; ObjectType
0x1800568b5  mov     [rsp+0F8h+HandleInformation], rcx; HandleInformation
0x1800568ba  mov     rcx, [rbp+38h]; Handle
0x1800568be  mov     [rsp+0F8h+Object], r15; Object
0x1800568c3  call    cs:__imp_ObReferenceObjectByHandle
0x1800568ca  nop     dword ptr [rax+rax+00h]
0x1800568cf  xor     ecx, ecx
0x1800568d1  mov     ebx, eax
0x1800568d3  test    eax, eax
0x1800568d5  js      short loc_1800568EF
0x1800568d7  mov     rcx, [r15]; FileObject
0x1800568da  call    cs:__imp_IoGetRelatedDeviceObject
0x1800568e1  nop     dword ptr [rax+rax+00h]
0x1800568e6  mov     [rdi+360h], rax
0x1800568ed  xor     ecx, ecx
0x1800568ef  lea     r15, [rdi+348h]
0x1800568f6  cmp     [rdi+358h], rcx
0x1800568fd  jz      loc_1800569E4
0x180056903  movups  xmm1, xmmword ptr cs:_GUID_3ef6ee41_0d41_11d2_beda_00c04f8ef457.Data1
0x18005690a  mov     [rsp+0F8h+var_90.Argument2], r12
0x180056912  lea     rax, [rdi+20h]
0x180056916  xorps   xmm0, xmm0
0x180056919  mov     [rsp+0F8h+var_90.Argument1], rax
0x18005691e  lea     r8, [rsp+0F8h+var_70]; struct KSHANDSHAKE *
0x180056926  mov     rcx, rdi; this
0x180056929  lea     rdx, [rsp+0F8h+var_90]; struct KSHANDSHAKE *
0x18005692e  movdqu  xmmword ptr [rsp+0F8h+var_90.ProtocolId.Data1], xmm1
0x180056934  movups  xmmword ptr [rsp+0F8h+var_70.ProtocolId.Data1], xmm0
0x18005693c  movups  xmmword ptr [rsp+0F8h+var_70.Argument1], xmm0
0x180056944  call    ?InitiateHandshake@CKsPin@@QEAAJPEAUKSHANDSHAKE@@0@Z; CKsPin::InitiateHandshake(KSHANDSHAKE *,KSHANDSHAKE *)
0x180056949  xor     r12d, r12d
0x18005694c  cmp     eax, 0C0000010h
0x180056951  jz      short loc_180056971
0x180056953  test    eax, eax
0x180056955  js      loc_1800569DD
0x18005695b  mov     rax, [rsp+0F8h+var_70.Argument1]
0x180056963  mov     [rdi+340h], rax
0x18005696a  mov     [rdi+120h], r12b
  ... truncated ...
```
