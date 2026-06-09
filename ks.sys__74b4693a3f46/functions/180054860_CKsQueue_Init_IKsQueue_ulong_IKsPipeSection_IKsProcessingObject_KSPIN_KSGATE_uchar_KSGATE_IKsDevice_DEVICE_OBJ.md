# CKsQueue::Init(IKsQueue * *,ulong,IKsPipeSection *,IKsProcessingObject *,_KSPIN *,_KSGATE *,uchar,_KSGATE *,IKsDevice *,_DEVICE_OBJECT *,_DMA_ADAPTER *,ulong,ulong,uchar,uchar)

- ea: `0x180054860`
- end: `0x180054de6`
- name: `?Init@CKsQueue@@QEAAJPEAPEAUIKsQueue@@KPEAUIKsPipeSection@@PEAUIKsProcessingObject@@PEAU_KSPIN@@PEAU_KSGATE@@E4PEAUIKsDevice@@PEAU_DEVICE_OBJECT@@PEAU_DMA_ADAPTER@@KKEE@Z`
- size: `1414`
- prototype: `__int64 __usercall@<rax>(CKsQueue *__hidden this@<rcx>, struct IKsQueue **@<rdx>, unsigned int@<r8d>, struct IKsPipeSection *@<r9>, struct IKsProcessingObject *, struct _KSPIN *, struct _KSGATE *, char, struct _KSGATE *, struct IKsDevice *, struct _DEVICE_OBJECT *, struct _DMA_ADAPTER *, unsigned int, unsigned int, unsigned __int8, unsigned __int8)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180053f98`

## callees

- `0x1800047dc`
- `0x180005550`
- `0x18000b7bc`
- `0x18000db30`
- `0x18000ee54`
- `0x18000fe2c`
- `0x180016050`
- `0x180019c60`
- `0x180054860`
- `0x180054df0`

## import_xrefs

- `ntoskrnl!KeInitializeDpc` at `0x180054b66`
- `ntoskrnl!KeInitializeDpc` at `0x180054b66`
- `ntoskrnl!KeInitializeTimer` at `0x180054b79`
- `ntoskrnl!KeInitializeTimer` at `0x180054b79`
- `ntoskrnl!KeInitializeSpinLock` at `0x180054af1`
- `ntoskrnl!KeInitializeSpinLock` at `0x180054b0f`
- `ntoskrnl!KeInitializeSpinLock` at `0x180054b2d`
- `ntoskrnl!KeInitializeSpinLock` at `0x180054af1`
- `ntoskrnl!KeInitializeSpinLock` at `0x180054b0f`
- `ntoskrnl!KeInitializeSpinLock` at `0x180054b2d`
- `ntoskrnl!KeInitializeEvent` at `0x180054a4c`
- `ntoskrnl!KeInitializeEvent` at `0x180054a6c`
- `ntoskrnl!KeInitializeEvent` at `0x180054a8c`
- `ntoskrnl!KeInitializeEvent` at `0x180054a4c`
- `ntoskrnl!KeInitializeEvent` at `0x180054a6c`
- `ntoskrnl!KeInitializeEvent` at `0x180054a8c`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x180054ac5`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x180054ac5`

## pseudocode

```c
__int64 __fastcall CKsQueue::Init(
        CKsQueue *this,
        CKsQueue **a2,
        int a3,
        struct IKsPipeSection *a4,
        struct IKsProcessingObject *a5,
        struct _KSPIN *a6,
        struct _KSGATE *a7,
        char a8,
        struct _KSGATE *a9,
        struct IKsDevice *a10,
        struct _DEVICE_OBJECT *a11,
        struct _DMA_ADAPTER *a12,
        unsigned int a13,
        unsigned int a14,
        unsigned __int8 a15,
        unsigned __int8 a16)
{
  __int64 *v20; // rdx
  IKsProcessingObject *m_ProcessingObject; // rcx
  int v22; // ebp
  _KSGATE *v23; // rax
  _KSGATE *v24; // rax
  int v25; // r8d
  struct _KSGATE *m_StateGate; // rcx
  NTSTATUS StreamPointer; // edi
  _KSPIN *m_MasterPin; // r8
  const KSALLOCATOR_FRAMING_EX *AllocatorFraming; // rax
  _KSGATE *m_AndGate; // rdx
  int v32; // edx
  int Count; // [rsp+38h] [rbp-50h]

  v20 = WPP_c705d9135b58358f87ecf40b472c5dce_Traceguids;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LOBYTE(v20) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)v20,
      1,
      51,
      (__int64)WPP_c705d9135b58358f87ecf40b472c5dce_Traceguids);
  }
  this->m_FrameCompletionNumber = 0;
  this->m_MdlCacheComponent = 0;
  this->m_PipeSection = a4;
  ((void (__fastcall *)(struct IKsPipeSection *, __int64 *))a4->AddRef)(a4, v20);
  this->m_ProcessingObject = a5;
  a5->AddRef(a5);
  this->m_OutputData = a16;
  this->m_InputData = a15;
  this->m_WriteOperation = a15;
  m_ProcessingObject = this->m_ProcessingObject;
  this->m_ProcessPassive = (a3 & 1) == 0;
  this->m_ProcessAsynchronously = (a3 & 8) != 0;
  this->m_InitiateProcessing = (a3 & 0x10) == 0;
  this->m_ProcessOnEveryArrival = (a3 & 0x20) != 0;
  this->m_DepartInSequence = (a3 & 0x80) != 0;
  this->m_GenerateMappings = BYTE1(a3) & 1;
  v22 = a3 & 0x200;
  this->m_ZeroWindowSize = v22 == 0;
  this->m_FramesNotRequired = (a3 & 0x40) != 0;
  this->m_MinProcessingState = (a3 & 0x10000 | 0x20000u) >> 16;
  v23 = m_ProcessingObject->GetAndGate(m_ProcessingObject);
  this->m_AndGate = v23;
  if ( a7 )
  {
    this->m_FrameGateIsOr = a8;
    this->m_FrameGate = a7;
  }
  else if ( (a3 & 0x40) == 0 )
  {
    this->m_FrameGate = v23;
    this->m_FrameGateIsOr = 0;
  }
  v24 = a9;
  if ( a9 && (a3 & 0x1000000) != 0 )
    this->m_StateGateIsOr = 1;
  else
    v24 = 0;
  this->m_StateGate = v24;
  this->m_MasterPin = a6;
  this->m_FunctionalDeviceObject = a11;
  this->m_AdapterObject = a12;
  this->m_MaxMappingByteCount = a13;
  this->m_Device = a10;
  this->m_MappingTableStride = a14;
  if ( !a14 )
    this->m_MappingTableStride = 1;
  this->m_UseKsCommonBuffer = a10->UseKsCommonBuffer(a10);
  this->m_State = KSSTATE_STOP;
  this->m_StreamPointersPlusOne = 1;
  KeInitializeEvent(&this->m_DestructEvent, SynchronizationEvent, 0);
  this->m_TransportIrpsPlusOne = 1;
  KeInitializeEvent(&this->m_FlushEvent, SynchronizationEvent, 0);
  this->m_InternalReferenceCountPlusOne = 1;
  KeInitializeEvent(&this->m_InternalReferenceEvent, SynchronizationEvent, 0);
  ExInitializeNPagedLookasideList(&this->m_ChannelContextLookaside, 0, 0, 0x200u, 0x20u, 0x6341734Bu, 5u);
  this->m_StreamPointers.Blink = &this->m_StreamPointers;
  this->m_StreamPointers.Flink = &this->m_StreamPointers;
  this->m_FrameQueue.ListEntry.Blink = &this->m_FrameQueue.ListEntry;
  this->m_FrameQueue.ListEntry.Flink = &this->m_FrameQueue.ListEntry;
  KeInitializeSpinLock(&this->m_FrameQueue.SpinLock);
  this->m_FrameHeadersAvailable.ListEntry.Blink = &this->m_FrameHeadersAvailable.ListEntry;
  this->m_FrameHeadersAvailable.ListEntry.Flink = &this->m_FrameHeadersAvailable.ListEntry;
  KeInitializeSpinLock(&this->m_FrameHeadersAvailable.SpinLock);
  this->m_FrameCopyList.ListEntry.Blink = &this->m_FrameCopyList.ListEntry;
  this->m_FrameCopyList.ListEntry.Flink = &this->m_FrameCopyList.ListEntry;
  KeInitializeSpinLock(&this->m_FrameCopyList.SpinLock);
  this->m_WaitingIrps.Blink = &this->m_WaitingIrps;
  this->m_WaitingIrps.Flink = &this->m_WaitingIrps;
  this->m_TimeoutQueue.Blink = &this->m_TimeoutQueue;
  this->m_TimeoutQueue.Flink = &this->m_TimeoutQueue;
  KeInitializeDpc(&this->m_Dpc, CKsQueue::DispatchTimer, this);
  KeInitializeTimer(&this->m_Timer);
  KsGateTurnInputOff(this->m_AndGate);
  m_StateGate = this->m_StateGate;
  if ( m_StateGate && !this->m_StateGateIsOr )
    KsGateTurnInputOff(m_StateGate);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    m_AndGate = this->m_AndGate;
    Count = m_AndGate->Count;
    LOBYTE(m_AndGate) = 5;
    WPP_RECORDER_SF_qqd(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)m_AndGate,
      v25,
      52,
      (__int64)WPP_c705d9135b58358f87ecf40b472c5dce_Traceguids,
      (char)this,
      (char)this->m_AndGate,
      Count);
  }
  this->m_FlushWorkItem.Parameter = this;
  this->m_FlushWorkItem.WorkerRoutine = (PWORKER_THREAD_ROUTINE)CKsQueue::FlushWorker;
  this->m_FlushWorkItem.List.Flink = 0;
  StreamPointer = KsRegisterCountedWorker(DelayedWorkQueue, &this->m_FlushWorkItem, &this->m_FlushWorker);
  if ( StreamPointer >= 0 )
  {
    StreamPointer = CKsQueue::CreateStreamPointer(this, &this->m_Leading);
    if ( StreamPointer >= 0 )
    {
      if ( v22 )
        StreamPointer = CKsQueue::CreateStreamPointer(this, &this->m_Trailing);
    }
  }
  m_MasterPin = this->m_MasterPin;
  if ( m_MasterPin->Descriptor )
  {
    AllocatorFraming = m_MasterPin->Descriptor->AllocatorFraming;
    if ( AllocatorFraming )
    {
      if ( AllocatorFraming->CountItems )
      {
        if ( (AllocatorFraming->FramingItem[0].Flags & 0x4000) != 0 )
        {
          StreamPointer = KspCreateMdlCache(&this->m_MdlCacheComponent);
          if ( StreamPointer < 0
            && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
            && LOWORD(WPP_GLOBAL_Control->DeviceType) )
          {
            LOBYTE(v32) = 5;
            WPP_RECORDER_SF_qD(
              WPP_GLOBAL_Control->DeviceExtension,
              v32,
              1,
              53,
              (__int64)WPP_c705d9135b58358f87ecf40b472c5dce_Traceguids,
              (char)this,
              StreamPointer);
          }
        }
      }
    }
  }
  this->m_VerifierQueueEntry.Blink = &this->m_VerifierQueueEntry;
  this->m_VerifierQueueEntry.Flink = &this->m_VerifierQueueEntry;
  *(_QWORD *)&this->m_FramesReceived = 0;
  this->m_FramesCancelled = 0;
  *(_QWORD *)&this->m_Flushes = 0;
  *(_QWORD *)&this->m_FlushesWithLeadingEdgeLocked = 0;
  *(_QWORD *)&this->m_AsynchronousFlushes = 0;
  *(_QWORD *)&this->m_WasLastFlushAsynchronous = 0;
  *(_QWORD *)&this->m_AsyncFlushesInFlightDuringLastSyncFlush = 0;
  *(_QWORD *)&this->m_FramesWaitingAtLastFlush = 0;
  if ( StreamPointer >= 0 )
  {
    *a2 = this;
    this->AddRef(this);
    if ( (KsXdvExtLevel & 0x18) != 0 )
      KspQueueVerifierAddEntry(&this->m_VerifierQueueEntry);
  }
  return (unsigned int)StreamPointer;
}

```

## disassembly

```asm
0x180054860  push    rbx
0x180054862  push    rbp
0x180054863  push    rsi
0x180054864  push    rdi
0x180054865  push    r12
0x180054867  push    r13
0x180054869  push    r14
0x18005486b  push    r15
0x18005486d  sub     rsp, 48h
0x180054871  mov     rsi, r9
0x180054874  mov     edi, r8d
0x180054877  mov     r14, rdx
0x18005487a  mov     rbx, rcx
0x18005487d  xor     r12d, r12d
0x180054880  lea     rax, WPP_RECORDER_INITIALIZED
0x180054887  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18005488e  lea     rdx, WPP_c705d9135b58358f87ecf40b472c5dce_Traceguids
0x180054895  lea     r13d, [r12+1]
0x18005489a  jz      short loc_1800548AE
0x18005489c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800548a3  cmp     [rcx+48h], r12w
0x1800548a8  jnz     loc_180054D82
0x1800548ae  mov     [rbx+240h], r12
0x1800548b5  lea     r15, [rbx+248h]
0x1800548bc  mov     [r15], r12
0x1800548bf  mov     rcx, rsi
0x1800548c2  mov     [rbx+40h], rsi
0x1800548c6  mov     rax, [rsi]
0x1800548c9  mov     rax, [rax+8]
0x1800548cd  call    _guard_dispatch_icall
0x1800548d2  mov     rcx, [rsp+88h+arg_20]
0x1800548da  mov     [rbx+48h], rcx
0x1800548de  mov     rax, [rcx]
0x1800548e1  mov     rax, [rax+8]
0x1800548e5  call    _guard_dispatch_icall
0x1800548ea  mov     al, [rsp+88h+arg_78]
0x1800548f1  mov     ebp, edi
0x1800548f3  mov     cl, [rsp+88h+arg_70]
0x1800548fa  mov     esi, edi
0x1800548fc  mov     [rbx+73h], al
0x1800548ff  mov     al, dil
0x180054902  not     al
0x180054904  mov     [rbx+72h], cl
0x180054907  and     al, r13b
0x18005490a  mov     [rbx+74h], cl
0x18005490d  mov     rcx, [rbx+48h]
0x180054911  mov     [rbx+78h], al
0x180054914  mov     eax, edi
0x180054916  shr     eax, 3
0x180054919  and     al, r13b
0x18005491c  mov     [rbx+79h], al
0x18005491f  mov     eax, edi
0x180054921  shr     eax, 4
0x180054924  not     al
0x180054926  and     al, r13b
0x180054929  mov     [rbx+7Ah], al
0x18005492c  mov     eax, edi
0x18005492e  shr     eax, 5
0x180054931  and     al, r13b
0x180054934  mov     [rbx+7Bh], al
0x180054937  mov     eax, edi
0x180054939  shr     eax, 7
0x18005493c  and     al, r13b
0x18005493f  mov     [rbx+7Ch], al
0x180054942  mov     eax, edi
0x180054944  shr     eax, 8
0x180054947  and     al, r13b
0x18005494a  mov     [rbx+75h], al
0x18005494d  and     ebp, 200h
0x180054953  setz    al
0x180054956  and     esi, 40h
0x180054959  mov     [rbx+77h], al
0x18005495c  setnz   al
0x18005495f  mov     [rbx+7Dh], al
0x180054962  mov     eax, edi
0x180054964  and     eax, 10000h
0x180054969  bts     eax, 11h
0x18005496d  shr     eax, 10h
0x180054970  mov     [rbx+68h], eax
0x180054973  mov     rax, [rcx]
0x180054976  mov     rax, [rax+20h]
0x18005497a  call    _guard_dispatch_icall
0x18005497f  mov     rcx, [rsp+88h+arg_30]
0x180054987  mov     [rbx+0A8h], rax
0x18005498e  test    rcx, rcx
0x180054991  jnz     loc_180054DA0
0x180054997  test    esi, esi
0x180054999  jnz     short loc_1800549A9
0x18005499b  mov     [rbx+0B0h], rax
0x1800549a2  mov     [rbx+0B8h], r12b
0x1800549a9  mov     rax, [rsp+88h+arg_40]
0x1800549b1  test    rax, rax
0x1800549b4  jnz     loc_180054DB9
0x1800549ba  mov     rax, r12
0x1800549bd  mov     rcx, [rsp+88h+arg_48]
0x1800549c5  mov     [rbx+0C0h], rax
0x1800549cc  mov     rax, [rsp+88h+arg_28]
0x1800549d4  mov     [rbx+80h], rax
0x1800549db  mov     rax, [rsp+88h+arg_50]
0x1800549e3  mov     [rbx+90h], rax
0x1800549ea  mov     rax, [rsp+88h+arg_58]
0x1800549f2  mov     [rbx+98h], rax
0x1800549f9  mov     eax, [rsp+88h+arg_60]
0x180054a00  mov     [rbx+0A0h], eax
0x180054a06  mov     eax, [rsp+88h+arg_68]
0x180054a0d  mov     [rbx+88h], rcx
0x180054a14  mov     [rbx+0A4h], eax
0x180054a1a  test    eax, eax
0x180054a1c  jnz     short loc_180054A25
0x180054a1e  mov     [rbx+0A4h], r13d
0x180054a25  mov     rax, [rcx]
0x180054a28  mov     rax, [rax+58h]
0x180054a2c  call    _guard_dispatch_icall
0x180054a31  lea     rcx, [rbx+188h]; Event
0x180054a38  mov     [rbx+76h], al
0x180054a3b  xor     r8d, r8d; State
0x180054a3e  mov     [rbx+64h], r12d
0x180054a42  mov     edx, r13d; Type
0x180054a45  mov     [rbx+0D8h], r13d
0x180054a4c  call    cs:__imp_KeInitializeEvent
0x180054a53  nop     dword ptr [rax+rax+00h]
0x180054a58  lea     rcx, [rbx+270h]; Event
0x180054a5f  mov     [rbx+268h], r13d
0x180054a66  xor     r8d, r8d; State
0x180054a69  mov     edx, r13d; Type
0x180054a6c  call    cs:__imp_KeInitializeEvent
0x180054a73  nop     dword ptr [rax+rax+00h]
0x180054a78  lea     rcx, [rbx+290h]; Event
0x180054a7f  mov     [rbx+288h], r13d
0x180054a86  xor     r8d, r8d; State
0x180054a89  mov     edx, r13d; Type
0x180054a8c  call    cs:__imp_KeInitializeEvent
0x180054a93  nop     dword ptr [rax+rax+00h]
0x180054a98  mov     esi, 5
0x180054a9d  lea     rcx, [rbx+2C0h]; Lookaside
0x180054aa4  mov     [rsp+88h+Depth], si; Depth
0x180054aa9  mov     r9d, 200h; Flags
0x180054aaf  mov     [rsp+88h+Tag], 6341734Bh; Tag
0x180054ab7  xor     r8d, r8d; Free
0x180054aba  xor     edx, edx; Allocate
0x180054abc  mov     [rsp+88h+Size], 20h ; ' '; Size
0x180054ac5  call    cs:__imp_ExInitializeNPagedLookasideList
0x180054acc  nop     dword ptr [rax+rax+00h]
0x180054ad1  lea     rax, [rbx+120h]
0x180054ad8  lea     rcx, [rbx+130h]
0x180054adf  mov     [rax+8], rax
0x180054ae3  mov     [rax], rax
0x180054ae6  mov     [rcx+8], rcx
0x180054aea  mov     [rcx], rcx
0x180054aed  add     rcx, 10h; SpinLock
0x180054af1  call    cs:__imp_KeInitializeSpinLock
0x180054af8  nop     dword ptr [rax+rax+00h]
0x180054afd  lea     rcx, [rbx+148h]
0x180054b04  mov     [rcx+8], rcx
0x180054b08  mov     [rcx], rcx
0x180054b0b  add     rcx, 10h; SpinLock
0x180054b0f  call    cs:__imp_KeInitializeSpinLock
0x180054b16  nop     dword ptr [rax+rax+00h]
0x180054b1b  lea     rcx, [rbx+160h]
0x180054b22  mov     [rcx+8], rcx
0x180054b26  mov     [rcx], rcx
0x180054b29  add     rcx, 10h; SpinLock
0x180054b2d  call    cs:__imp_KeInitializeSpinLock
0x180054b34  nop     dword ptr [rax+rax+00h]
0x180054b39  lea     rax, [rbx+178h]
0x180054b40  mov     r8, rbx; DeferredContext
0x180054b43  mov     [rax+8], rax
0x180054b47  lea     rcx, [rbx+1A0h]; Dpc
0x180054b4e  mov     [rax], rax
0x180054b51  lea     rdx, ?DispatchTimer@CKsQueue@@CAXPEAU_KDPC@@PEAX11@Z; DeferredRoutine
0x180054b58  lea     rax, [rbx+220h]
0x180054b5f  mov     [rax+8], rax
0x180054b63  mov     [rax], rax
0x180054b66  call    cs:__imp_KeInitializeDpc
0x180054b6d  nop     dword ptr [rax+rax+00h]
0x180054b72  lea     rcx, [rbx+1E0h]; Timer
0x180054b79  call    cs:__imp_KeInitializeTimer
0x180054b80  nop     dword ptr [rax+rax+00h]
0x180054b85  mov     rcx, [rbx+0A8h]; Gate
0x180054b8c  call    KsGateTurnInputOff
0x180054b91  mov     rcx, [rbx+0C0h]; Gate
0x180054b98  test    rcx, rcx
0x180054b9b  jnz     loc_180054DCF
0x180054ba1  lea     rax, WPP_RECORDER_INITIALIZED
0x180054ba8  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180054baf  jnz     loc_180054C6F
0x180054bb5  lea     rdx, [rbx+340h]; CountedWorkItem
0x180054bbc  mov     ecx, r13d; WorkQueueType
0x180054bbf  lea     rax, ?FlushWorker@CKsQueue@@CAXPEAX@Z; CKsQueue::FlushWorker(void *)
0x180054bc6  mov     [rdx+18h], rbx
0x180054bca  lea     r8, [rbx+360h]; Worker
0x180054bd1  mov     [rdx+10h], rax
0x180054bd5  mov     [rdx], r12
0x180054bd8  call    KsRegisterCountedWorker
0x180054bdd  mov     edi, eax
0x180054bdf  test    eax, eax
0x180054be1  jns     loc_180054CE4
0x180054be7  mov     r8, [rbx+80h]
0x180054bee  mov     rax, [r8]
0x180054bf1  test    rax, rax
0x180054bf4  jz      short loc_180054C11
0x180054bf6  mov     rax, [rax+78h]
0x180054bfa  test    rax, rax
0x180054bfd  jz      short loc_180054C11
0x180054bff  cmp     [rax], r12d
0x180054c02  jbe     short loc_180054C11
0x180054c04  test    dword ptr [rax+40h], 4000h
0x180054c0b  jnz     loc_180054D1B
0x180054c11  lea     rsi, [rbx+370h]
0x180054c18  mov     [rsi+8], rsi
0x180054c1c  mov     [rsi], rsi
0x180054c1f  mov     [rbx+0CCh], r12
0x180054c26  mov     [rbx+0D4h], r12d
0x180054c2d  mov     [rbx+0DCh], r12
0x180054c34  mov     [rbx+0E4h], r12
0x180054c3b  mov     [rbx+0ECh], r12
0x180054c42  mov     [rbx+0F4h], r12
0x180054c49  mov     [rbx+0FCh], r12
0x180054c50  mov     [rbx+104h], r12
0x180054c57  test    edi, edi
0x180054c59  jns     short loc_180054CBB
0x180054c5b  mov     eax, edi
0x180054c5d  add     rsp, 48h
0x180054c61  pop     r15
0x180054c63  pop     r14
0x180054c65  pop     r13
0x180054c67  pop     r12
0x180054c69  pop     rdi
0x180054c6a  pop     rsi
0x180054c6b  pop     rbp
0x180054c6c  pop     rbx
0x180054c6d  retn
0x180054c6f  mov     rcx, cs:WPP_GLOBAL_Control
0x180054c76  cmp     [rcx+48h], r12w
0x180054c7b  jz      loc_180054BB5
0x180054c81  mov     rdx, [rbx+0A8h]
0x180054c88  mov     r9d, 34h ; '4'
0x180054c8e  mov     rcx, [rcx+40h]
0x180054c92  mov     eax, [rdx]
0x180054c94  mov     [rsp+88h+var_50], eax
0x180054c98  lea     rax, WPP_c705d9135b58358f87ecf40b472c5dce_Traceguids
0x180054c9f  mov     qword ptr [rsp+88h+Depth], rdx
0x180054ca4  mov     dl, sil
0x180054ca7  mov     qword ptr [rsp+88h+Tag], rbx
0x180054cac  mov     [rsp+88h+Size], rax
0x180054cb1  call    WPP_RECORDER_SF_qqd
0x180054cb6  jmp     loc_180054BB5
0x180054cbb  mov     [r14], rbx
0x180054cbe  mov     rcx, rbx
0x180054cc1  mov     rax, [rbx]
0x180054cc4  mov     rax, [rax+8]
0x180054cc8  call    _guard_dispatch_icall
0x180054ccd  mov     eax, cs:KsXdvExtLevel
0x180054cd3  test    al, 18h
0x180054cd5  jz      short loc_180054C5B
0x180054cd7  mov     rcx, rsi; ListEntry
0x180054cda  call    ?KspQueueVerifierAddEntry@@YAXPEAU_LIST_ENTRY@@@Z; KspQueueVerifierAddEntry(_LIST_ENTRY *)
0x180054cdf  jmp     loc_180054C5B
0x180054ce4  lea     rdx, [rbx+250h]; struct _KSPSTREAM_POINTER **
0x180054ceb  mov     rcx, rbx; this
0x180054cee  call    ?CreateStreamPointer@CKsQueue@@AEAAJPEAPEAU_KSPSTREAM_POINTER@@@Z; CKsQueue::CreateStreamPointer(_KSPSTREAM_POINTER * *)
0x180054cf3  mov     edi, eax
0x180054cf5  test    eax, eax
0x180054cf7  js      loc_180054BE7
0x180054cfd  test    ebp, ebp
0x180054cff  jz      loc_180054BE7
0x180054d05  lea     rdx, [rbx+258h]; struct _KSPSTREAM_POINTER **
0x180054d0c  mov     rcx, rbx; this
0x180054d0f  call    ?CreateStreamPointer@CKsQueue@@AEAAJPEAPEAU_KSPSTREAM_POINTER@@@Z; CKsQueue::CreateStreamPointer(_KSPSTREAM_POINTER * *)
0x180054d14  mov     edi, eax
0x180054d16  jmp     loc_180054BE7
0x180054d1b  mov     rcx, r15; struct IKsMdlCache **
0x180054d1e  call    KspCreateMdlCache
0x180054d23  mov     edi, eax
0x180054d25  test    eax, eax
0x180054d27  jns     loc_180054C11
0x180054d2d  lea     rax, WPP_RECORDER_INITIALIZED
0x180054d34  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180054d3b  jz      loc_180054C11
0x180054d41  mov     rcx, cs:WPP_GLOBAL_Control
0x180054d48  cmp     [rcx+48h], r12w
0x180054d4d  jz      loc_180054C11
0x180054d53  mov     rcx, [rcx+40h]
0x180054d57  lea     rax, WPP_c705d9135b58358f87ecf40b472c5dce_Traceguids
0x180054d5e  mov     dword ptr [rsp+88h+Depth], edi
0x180054d62  mov     r9d, 35h ; '5'
0x180054d68  mov     qword ptr [rsp+88h+Tag], rbx
0x180054d6d  mov     r8d, r13d
0x180054d70  mov     dl, sil
0x180054d73  mov     [rsp+88h+Size], rax
0x180054d78  call    WPP_RECORDER_SF_qD
0x180054d7d  jmp     loc_180054C11
0x180054d82  mov     rcx, [rcx+40h]
0x180054d86  mov     r9d, 33h ; '3'
0x180054d8c  mov     [rsp+88h+Size], rdx
0x180054d91  mov     r8d, r13d
0x180054d94  mov     dl, 5
0x180054d96  call    WPP_RECORDER_SF_
0x180054d9b  jmp     loc_1800548AE
0x180054da0  mov     al, [rsp+88h+arg_38]
  ... truncated ...
```
