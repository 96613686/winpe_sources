# CKsQueue::Init(IKsQueue * *,ulong,IKsPipeSection *,IKsProcessingObject *,_KSPIN *,_KSGATE *,uchar,_KSGATE *,IKsDevice *,_DEVICE_OBJECT *,_DMA_ADAPTER *,ulong,ulong,uchar,uchar)

- ea: `0x180054a00`
- end: `0x180054f86`
- name: `?Init@CKsQueue@@QEAAJPEAPEAUIKsQueue@@KPEAUIKsPipeSection@@PEAUIKsProcessingObject@@PEAU_KSPIN@@PEAU_KSGATE@@E4PEAUIKsDevice@@PEAU_DEVICE_OBJECT@@PEAU_DMA_ADAPTER@@KKEE@Z`
- size: `1414`
- prototype: `__int64 __fastcall(CKsQueue *this, CKsQueue **, int, struct IKsPipeSection *, struct IKsProcessingObject *, struct _KSPIN *, struct _KSGATE *, char, struct _KSGATE *, struct IKsDevice *, struct _DEVICE_OBJECT *, struct _DMA_ADAPTER *, unsigned int, unsigned int, unsigned __int8, unsigned __int8)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180054138`

## callees

- `0x1800047dc`
- `0x180005550`
- `0x18000b7bc`
- `0x18000db30`
- `0x18000f544`
- `0x18000fe40`
- `0x1800160a0`
- `0x180019cb0`
- `0x180054a00`
- `0x180054f90`

## import_xrefs

- `ntoskrnl!KeInitializeDpc` at `0x180054d06`
- `ntoskrnl!KeInitializeDpc` at `0x180054d06`
- `ntoskrnl!KeInitializeTimer` at `0x180054d19`
- `ntoskrnl!KeInitializeTimer` at `0x180054d19`
- `ntoskrnl!KeInitializeSpinLock` at `0x180054c91`
- `ntoskrnl!KeInitializeSpinLock` at `0x180054caf`
- `ntoskrnl!KeInitializeSpinLock` at `0x180054ccd`
- `ntoskrnl!KeInitializeSpinLock` at `0x180054c91`
- `ntoskrnl!KeInitializeSpinLock` at `0x180054caf`
- `ntoskrnl!KeInitializeSpinLock` at `0x180054ccd`
- `ntoskrnl!KeInitializeEvent` at `0x180054bec`
- `ntoskrnl!KeInitializeEvent` at `0x180054c0c`
- `ntoskrnl!KeInitializeEvent` at `0x180054c2c`
- `ntoskrnl!KeInitializeEvent` at `0x180054bec`
- `ntoskrnl!KeInitializeEvent` at `0x180054c0c`
- `ntoskrnl!KeInitializeEvent` at `0x180054c2c`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x180054c65`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x180054c65`

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
  __int64 v27; // rdx
  int StreamPointer; // edi
  struct _KSPIN *m_MasterPin; // r8
  const KSALLOCATOR_FRAMING_EX *AllocatorFraming; // rax
  _KSGATE *m_AndGate; // rdx
  int v33; // edx
  int Count; // [rsp+38h] [rbp-50h]

  v20 = WPP_13a31f976c1e3a0a846d2ee29290b270_Traceguids;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LOBYTE(v20) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)v20,
      1,
      51,
      (__int64)WPP_13a31f976c1e3a0a846d2ee29290b270_Traceguids);
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
  KeInitializeDpc(&this->m_Dpc, (PKDEFERRED_ROUTINE)CKsQueue::DispatchTimer, this);
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
      (__int64)WPP_13a31f976c1e3a0a846d2ee29290b270_Traceguids,
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
          StreamPointer = KspCreateMdlCache(&this->m_MdlCacheComponent, v27, m_MasterPin);
          if ( StreamPointer < 0
            && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
            && LOWORD(WPP_GLOBAL_Control->DeviceType) )
          {
            LOBYTE(v33) = 5;
            WPP_RECORDER_SF_qD(
              WPP_GLOBAL_Control->DeviceExtension,
              v33,
              1,
              53,
              (__int64)WPP_13a31f976c1e3a0a846d2ee29290b270_Traceguids,
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
0x180054a00  push    rbx
0x180054a02  push    rbp
0x180054a03  push    rsi
0x180054a04  push    rdi
0x180054a05  push    r12
0x180054a07  push    r13
0x180054a09  push    r14
0x180054a0b  push    r15
0x180054a0d  sub     rsp, 48h
0x180054a11  mov     rsi, r9
0x180054a14  mov     edi, r8d
0x180054a17  mov     r14, rdx
0x180054a1a  mov     rbx, rcx
0x180054a1d  xor     r12d, r12d
0x180054a20  lea     rax, WPP_RECORDER_INITIALIZED
0x180054a27  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180054a2e  lea     rdx, WPP_13a31f976c1e3a0a846d2ee29290b270_Traceguids
0x180054a35  lea     r13d, [r12+1]
0x180054a3a  jz      short loc_180054A4E
0x180054a3c  mov     rcx, cs:WPP_GLOBAL_Control
0x180054a43  cmp     [rcx+48h], r12w
0x180054a48  jnz     loc_180054F22
0x180054a4e  mov     [rbx+240h], r12
0x180054a55  lea     r15, [rbx+248h]
0x180054a5c  mov     [r15], r12
0x180054a5f  mov     rcx, rsi
0x180054a62  mov     [rbx+40h], rsi
0x180054a66  mov     rax, [rsi]
0x180054a69  mov     rax, [rax+8]
0x180054a6d  call    _guard_dispatch_icall
0x180054a72  mov     rcx, [rsp+88h+arg_20]
0x180054a7a  mov     [rbx+48h], rcx
0x180054a7e  mov     rax, [rcx]
0x180054a81  mov     rax, [rax+8]
0x180054a85  call    _guard_dispatch_icall
0x180054a8a  mov     al, [rsp+88h+arg_78]
0x180054a91  mov     ebp, edi
0x180054a93  mov     cl, [rsp+88h+arg_70]
0x180054a9a  mov     esi, edi
0x180054a9c  mov     [rbx+73h], al
0x180054a9f  mov     al, dil
0x180054aa2  not     al
0x180054aa4  mov     [rbx+72h], cl
0x180054aa7  and     al, r13b
0x180054aaa  mov     [rbx+74h], cl
0x180054aad  mov     rcx, [rbx+48h]
0x180054ab1  mov     [rbx+78h], al
0x180054ab4  mov     eax, edi
0x180054ab6  shr     eax, 3
0x180054ab9  and     al, r13b
0x180054abc  mov     [rbx+79h], al
0x180054abf  mov     eax, edi
0x180054ac1  shr     eax, 4
0x180054ac4  not     al
0x180054ac6  and     al, r13b
0x180054ac9  mov     [rbx+7Ah], al
0x180054acc  mov     eax, edi
0x180054ace  shr     eax, 5
0x180054ad1  and     al, r13b
0x180054ad4  mov     [rbx+7Bh], al
0x180054ad7  mov     eax, edi
0x180054ad9  shr     eax, 7
0x180054adc  and     al, r13b
0x180054adf  mov     [rbx+7Ch], al
0x180054ae2  mov     eax, edi
0x180054ae4  shr     eax, 8
0x180054ae7  and     al, r13b
0x180054aea  mov     [rbx+75h], al
0x180054aed  and     ebp, 200h
0x180054af3  setz    al
0x180054af6  and     esi, 40h
0x180054af9  mov     [rbx+77h], al
0x180054afc  setnz   al
0x180054aff  mov     [rbx+7Dh], al
0x180054b02  mov     eax, edi
0x180054b04  and     eax, 10000h
0x180054b09  bts     eax, 11h
0x180054b0d  shr     eax, 10h
0x180054b10  mov     [rbx+68h], eax
0x180054b13  mov     rax, [rcx]
0x180054b16  mov     rax, [rax+20h]
0x180054b1a  call    _guard_dispatch_icall
0x180054b1f  mov     rcx, [rsp+88h+arg_30]
0x180054b27  mov     [rbx+0A8h], rax
0x180054b2e  test    rcx, rcx
0x180054b31  jnz     loc_180054F40
0x180054b37  test    esi, esi
0x180054b39  jnz     short loc_180054B49
0x180054b3b  mov     [rbx+0B0h], rax
0x180054b42  mov     [rbx+0B8h], r12b
0x180054b49  mov     rax, [rsp+88h+arg_40]
0x180054b51  test    rax, rax
0x180054b54  jnz     loc_180054F59
0x180054b5a  mov     rax, r12
0x180054b5d  mov     rcx, [rsp+88h+arg_48]
0x180054b65  mov     [rbx+0C0h], rax
0x180054b6c  mov     rax, [rsp+88h+arg_28]
0x180054b74  mov     [rbx+80h], rax
0x180054b7b  mov     rax, [rsp+88h+arg_50]
0x180054b83  mov     [rbx+90h], rax
0x180054b8a  mov     rax, [rsp+88h+arg_58]
0x180054b92  mov     [rbx+98h], rax
0x180054b99  mov     eax, [rsp+88h+arg_60]
0x180054ba0  mov     [rbx+0A0h], eax
0x180054ba6  mov     eax, [rsp+88h+arg_68]
0x180054bad  mov     [rbx+88h], rcx
0x180054bb4  mov     [rbx+0A4h], eax
0x180054bba  test    eax, eax
0x180054bbc  jnz     short loc_180054BC5
0x180054bbe  mov     [rbx+0A4h], r13d
0x180054bc5  mov     rax, [rcx]
0x180054bc8  mov     rax, [rax+58h]
0x180054bcc  call    _guard_dispatch_icall
0x180054bd1  lea     rcx, [rbx+188h]; Event
0x180054bd8  mov     [rbx+76h], al
0x180054bdb  xor     r8d, r8d; State
0x180054bde  mov     [rbx+64h], r12d
0x180054be2  mov     edx, r13d; Type
0x180054be5  mov     [rbx+0D8h], r13d
0x180054bec  call    cs:__imp_KeInitializeEvent
0x180054bf3  nop     dword ptr [rax+rax+00h]
0x180054bf8  lea     rcx, [rbx+270h]; Event
0x180054bff  mov     [rbx+268h], r13d
0x180054c06  xor     r8d, r8d; State
0x180054c09  mov     edx, r13d; Type
0x180054c0c  call    cs:__imp_KeInitializeEvent
0x180054c13  nop     dword ptr [rax+rax+00h]
0x180054c18  lea     rcx, [rbx+290h]; Event
0x180054c1f  mov     [rbx+288h], r13d
0x180054c26  xor     r8d, r8d; State
0x180054c29  mov     edx, r13d; Type
0x180054c2c  call    cs:__imp_KeInitializeEvent
0x180054c33  nop     dword ptr [rax+rax+00h]
0x180054c38  mov     esi, 5
0x180054c3d  lea     rcx, [rbx+2C0h]; Lookaside
0x180054c44  mov     [rsp+88h+Depth], si; Depth
0x180054c49  mov     r9d, 200h; Flags
0x180054c4f  mov     [rsp+88h+Tag], 6341734Bh; Tag
0x180054c57  xor     r8d, r8d; Free
0x180054c5a  xor     edx, edx; Allocate
0x180054c5c  mov     [rsp+88h+Size], 20h ; ' '; Size
0x180054c65  call    cs:__imp_ExInitializeNPagedLookasideList
0x180054c6c  nop     dword ptr [rax+rax+00h]
0x180054c71  lea     rax, [rbx+120h]
0x180054c78  lea     rcx, [rbx+130h]
0x180054c7f  mov     [rax+8], rax
0x180054c83  mov     [rax], rax
0x180054c86  mov     [rcx+8], rcx
0x180054c8a  mov     [rcx], rcx
0x180054c8d  add     rcx, 10h; SpinLock
0x180054c91  call    cs:__imp_KeInitializeSpinLock
0x180054c98  nop     dword ptr [rax+rax+00h]
0x180054c9d  lea     rcx, [rbx+148h]
0x180054ca4  mov     [rcx+8], rcx
0x180054ca8  mov     [rcx], rcx
0x180054cab  add     rcx, 10h; SpinLock
0x180054caf  call    cs:__imp_KeInitializeSpinLock
0x180054cb6  nop     dword ptr [rax+rax+00h]
0x180054cbb  lea     rcx, [rbx+160h]
0x180054cc2  mov     [rcx+8], rcx
0x180054cc6  mov     [rcx], rcx
0x180054cc9  add     rcx, 10h; SpinLock
0x180054ccd  call    cs:__imp_KeInitializeSpinLock
0x180054cd4  nop     dword ptr [rax+rax+00h]
0x180054cd9  lea     rax, [rbx+178h]
0x180054ce0  mov     r8, rbx; DeferredContext
0x180054ce3  mov     [rax+8], rax
0x180054ce7  lea     rcx, [rbx+1A0h]; Dpc
0x180054cee  mov     [rax], rax
0x180054cf1  lea     rdx, ?DispatchTimer@CKsQueue@@CAXPEAU_KDPC@@PEAX11@Z; DeferredRoutine
0x180054cf8  lea     rax, [rbx+220h]
0x180054cff  mov     [rax+8], rax
0x180054d03  mov     [rax], rax
0x180054d06  call    cs:__imp_KeInitializeDpc
0x180054d0d  nop     dword ptr [rax+rax+00h]
0x180054d12  lea     rcx, [rbx+1E0h]; Timer
0x180054d19  call    cs:__imp_KeInitializeTimer
0x180054d20  nop     dword ptr [rax+rax+00h]
0x180054d25  mov     rcx, [rbx+0A8h]; Gate
0x180054d2c  call    KsGateTurnInputOff
0x180054d31  mov     rcx, [rbx+0C0h]; Gate
0x180054d38  test    rcx, rcx
0x180054d3b  jnz     loc_180054F6F
0x180054d41  lea     rax, WPP_RECORDER_INITIALIZED
0x180054d48  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180054d4f  jnz     loc_180054E0F
0x180054d55  lea     rdx, [rbx+340h]; CountedWorkItem
0x180054d5c  mov     ecx, r13d; WorkQueueType
0x180054d5f  lea     rax, ?FlushWorker@CKsQueue@@CAXPEAX@Z; CKsQueue::FlushWorker(void *)
0x180054d66  mov     [rdx+18h], rbx
0x180054d6a  lea     r8, [rbx+360h]; Worker
0x180054d71  mov     [rdx+10h], rax
0x180054d75  mov     [rdx], r12
0x180054d78  call    KsRegisterCountedWorker
0x180054d7d  mov     edi, eax
0x180054d7f  test    eax, eax
0x180054d81  jns     loc_180054E84
0x180054d87  mov     r8, [rbx+80h]
0x180054d8e  mov     rax, [r8]
0x180054d91  test    rax, rax
0x180054d94  jz      short loc_180054DB1
0x180054d96  mov     rax, [rax+78h]
0x180054d9a  test    rax, rax
0x180054d9d  jz      short loc_180054DB1
0x180054d9f  cmp     [rax], r12d
0x180054da2  jbe     short loc_180054DB1
0x180054da4  test    dword ptr [rax+40h], 4000h
0x180054dab  jnz     loc_180054EBB
0x180054db1  lea     rsi, [rbx+370h]
0x180054db8  mov     [rsi+8], rsi
0x180054dbc  mov     [rsi], rsi
0x180054dbf  mov     [rbx+0CCh], r12
0x180054dc6  mov     [rbx+0D4h], r12d
0x180054dcd  mov     [rbx+0DCh], r12
0x180054dd4  mov     [rbx+0E4h], r12
0x180054ddb  mov     [rbx+0ECh], r12
0x180054de2  mov     [rbx+0F4h], r12
0x180054de9  mov     [rbx+0FCh], r12
0x180054df0  mov     [rbx+104h], r12
0x180054df7  test    edi, edi
0x180054df9  jns     short loc_180054E5B
0x180054dfb  mov     eax, edi
0x180054dfd  add     rsp, 48h
0x180054e01  pop     r15
0x180054e03  pop     r14
0x180054e05  pop     r13
0x180054e07  pop     r12
0x180054e09  pop     rdi
0x180054e0a  pop     rsi
0x180054e0b  pop     rbp
0x180054e0c  pop     rbx
0x180054e0d  retn
0x180054e0f  mov     rcx, cs:WPP_GLOBAL_Control
0x180054e16  cmp     [rcx+48h], r12w
0x180054e1b  jz      loc_180054D55
0x180054e21  mov     rdx, [rbx+0A8h]
0x180054e28  mov     r9d, 34h ; '4'
0x180054e2e  mov     rcx, [rcx+40h]
0x180054e32  mov     eax, [rdx]
0x180054e34  mov     [rsp+88h+var_50], eax
0x180054e38  lea     rax, WPP_13a31f976c1e3a0a846d2ee29290b270_Traceguids
0x180054e3f  mov     qword ptr [rsp+88h+Depth], rdx
0x180054e44  mov     dl, sil
0x180054e47  mov     qword ptr [rsp+88h+Tag], rbx
0x180054e4c  mov     [rsp+88h+Size], rax
0x180054e51  call    WPP_RECORDER_SF_qqd
0x180054e56  jmp     loc_180054D55
0x180054e5b  mov     [r14], rbx
0x180054e5e  mov     rcx, rbx
0x180054e61  mov     rax, [rbx]
0x180054e64  mov     rax, [rax+8]
0x180054e68  call    _guard_dispatch_icall
0x180054e6d  mov     eax, cs:KsXdvExtLevel
0x180054e73  test    al, 18h
0x180054e75  jz      short loc_180054DFB
0x180054e77  mov     rcx, rsi; ListEntry
0x180054e7a  call    ?KspQueueVerifierAddEntry@@YAXPEAU_LIST_ENTRY@@@Z; KspQueueVerifierAddEntry(_LIST_ENTRY *)
0x180054e7f  jmp     loc_180054DFB
0x180054e84  lea     rdx, [rbx+250h]; struct _KSPSTREAM_POINTER **
0x180054e8b  mov     rcx, rbx; this
0x180054e8e  call    ?CreateStreamPointer@CKsQueue@@AEAAJPEAPEAU_KSPSTREAM_POINTER@@@Z; CKsQueue::CreateStreamPointer(_KSPSTREAM_POINTER * *)
0x180054e93  mov     edi, eax
0x180054e95  test    eax, eax
0x180054e97  js      loc_180054D87
0x180054e9d  test    ebp, ebp
0x180054e9f  jz      loc_180054D87
0x180054ea5  lea     rdx, [rbx+258h]; struct _KSPSTREAM_POINTER **
0x180054eac  mov     rcx, rbx; this
0x180054eaf  call    ?CreateStreamPointer@CKsQueue@@AEAAJPEAPEAU_KSPSTREAM_POINTER@@@Z; CKsQueue::CreateStreamPointer(_KSPSTREAM_POINTER * *)
0x180054eb4  mov     edi, eax
0x180054eb6  jmp     loc_180054D87
0x180054ebb  mov     rcx, r15; struct IKsMdlCache **
0x180054ebe  call    KspCreateMdlCache
0x180054ec3  mov     edi, eax
0x180054ec5  test    eax, eax
0x180054ec7  jns     loc_180054DB1
0x180054ecd  lea     rax, WPP_RECORDER_INITIALIZED
0x180054ed4  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180054edb  jz      loc_180054DB1
0x180054ee1  mov     rcx, cs:WPP_GLOBAL_Control
0x180054ee8  cmp     [rcx+48h], r12w
0x180054eed  jz      loc_180054DB1
0x180054ef3  mov     rcx, [rcx+40h]
0x180054ef7  lea     rax, WPP_13a31f976c1e3a0a846d2ee29290b270_Traceguids
0x180054efe  mov     dword ptr [rsp+88h+Depth], edi
0x180054f02  mov     r9d, 35h ; '5'
0x180054f08  mov     qword ptr [rsp+88h+Tag], rbx
0x180054f0d  mov     r8d, r13d
0x180054f10  mov     dl, sil
0x180054f13  mov     [rsp+88h+Size], rax
0x180054f18  call    WPP_RECORDER_SF_qD
0x180054f1d  jmp     loc_180054DB1
0x180054f22  mov     rcx, [rcx+40h]
0x180054f26  mov     r9d, 33h ; '3'
0x180054f2c  mov     [rsp+88h+Size], rdx
0x180054f31  mov     r8d, r13d
0x180054f34  mov     dl, 5
0x180054f36  call    WPP_RECORDER_SF_
0x180054f3b  jmp     loc_180054A4E
0x180054f40  mov     al, [rsp+88h+arg_38]
  ... truncated ...
```
