# CKsRequestor::Init(IKsPipeSection *,IKsPin *,_FILE_OBJECT *,IKsRetireFrame *,IKsIrpCompletion *)

- ea: `0x1800430dc`
- end: `0x180043479`
- name: `?Init@CKsRequestor@@QEAAJPEAUIKsPipeSection@@PEAUIKsPin@@PEAU_FILE_OBJECT@@PEAUIKsRetireFrame@@PEAUIKsIrpCompletion@@@Z`
- size: `925`
- prototype: `__int64 __fastcall(CKsRequestor *this, struct IKsPipeSection *, struct IKsPin *, struct _FILE_OBJECT *, struct IKsRetireFrame *, IKsIrpCompletion *BytesReturned)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800439fc`

## callees

- `0x18000b7bc`
- `0x18000f544`
- `0x180014778`
- `0x1800179dc`
- `0x180019cb0`
- `0x1800430dc`
- `0x180051360`
- `0x180054f90`

## import_xrefs

- `ntoskrnl!ObfReferenceObject` at `0x180043437`
- `ntoskrnl!ObfReferenceObject` at `0x180043437`
- `ntoskrnl!KeInitializeSpinLock` at `0x180043221`
- `ntoskrnl!KeInitializeSpinLock` at `0x18004323f`
- `ntoskrnl!KeInitializeSpinLock` at `0x18004325d`
- `ntoskrnl!KeInitializeSpinLock` at `0x180043221`
- `ntoskrnl!KeInitializeSpinLock` at `0x18004323f`
- `ntoskrnl!KeInitializeSpinLock` at `0x18004325d`
- `ntoskrnl!KeInitializeEvent` at `0x180043203`
- `ntoskrnl!KeInitializeEvent` at `0x180043203`

## pseudocode

```c
__int64 __fastcall CKsRequestor::Init(
        CKsRequestor *this,
        struct IKsPipeSection *a2,
        struct IKsPin *a3,
        struct _FILE_OBJECT *a4,
        struct IKsRetireFrame *a5,
        IKsIrpCompletion *BytesReturned)
{
  IKsPipeSection *v8; // rdi
  _KSPIN *v10; // rax
  const KSALLOCATOR_FRAMING_EX *AllocatorFraming; // rdx
  unsigned int MaxFrameSize; // edx
  unsigned int Frames; // eax
  NTSTATUS v14; // edi
  struct _FILE_OBJECT *m_AllocatorFileObject; // rcx
  int v16; // edx
  int v17; // r9d
  __int64 PoolType; // r9
  __int64 FrameSize; // rdx
  __int64 v20; // r8
  int InSize; // [rsp+20h] [rbp-98h]
  char OutSize; // [rsp+30h] [rbp-88h]
  GUID InBuffer; // [rsp+50h] [rbp-68h] BYREF
  int v25; // [rsp+60h] [rbp-58h]
  int v26; // [rsp+64h] [rbp-54h]

  v8 = a2;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)a2,
      1,
      11,
      (__int64)WPP_01e97eabb7fe30ad0eb84e4d86b22be6_Traceguids);
  }
  this->m_PipeSection = v8;
  v8->AddRef(v8);
  this->m_Pin = a3;
  if ( a4 == (struct _FILE_OBJECT *)-1LL )
  {
    a4 = 0;
    v10 = a3->GetStruct(a3);
    AllocatorFraming = v10->Descriptor->AllocatorFraming;
    if ( AllocatorFraming )
    {
      MaxFrameSize = AllocatorFraming->FramingItem[0].FramingRange.Range.MaxFrameSize;
      this->m_FrameSize = MaxFrameSize;
      Frames = v10->Descriptor->AllocatorFraming->FramingItem[0].Frames;
      this->m_FrameCount = Frames;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        OutSize = MaxFrameSize;
        LOBYTE(MaxFrameSize) = 4;
        WPP_RECORDER_SF_qdd(
          WPP_GLOBAL_Control->DeviceExtension,
          MaxFrameSize,
          1,
          12,
          (__int64)WPP_01e97eabb7fe30ad0eb84e4d86b22be6_Traceguids,
          (char)this,
          OutSize,
          Frames);
      }
    }
  }
  this->m_IrpCompletion = BytesReturned;
  this->m_AllocatorFileObject = a4;
  *(_WORD *)&this->m_CloneFrameHeader = 1;
  this->m_State = KSSTATE_STOP;
  this->m_EndOfStream = 0;
  this->m_ActiveFrameCountPlusOne = 1;
  KeInitializeEvent(&this->m_StopEvent, SynchronizationEvent, 0);
  this->m_IrpsAvailable.ListEntry.Blink = &this->m_IrpsAvailable.ListEntry;
  this->m_IrpsAvailable.ListEntry.Flink = &this->m_IrpsAvailable.ListEntry;
  KeInitializeSpinLock(&this->m_IrpsAvailable.SpinLock);
  this->m_FrameHeadersAvailable.ListEntry.Blink = &this->m_FrameHeadersAvailable.ListEntry;
  this->m_FrameHeadersAvailable.ListEntry.Flink = &this->m_FrameHeadersAvailable.ListEntry;
  KeInitializeSpinLock(&this->m_FrameHeadersAvailable.SpinLock);
  this->m_FrameHeadersToRetire.ListEntry.Blink = &this->m_FrameHeadersToRetire.ListEntry;
  this->m_FrameHeadersToRetire.ListEntry.Flink = &this->m_FrameHeadersToRetire.ListEntry;
  KeInitializeSpinLock(&this->m_FrameHeadersToRetire.SpinLock);
  this->m_WorkItem.List.Flink = 0;
  this->m_WorkItem.WorkerRoutine = (PWORKER_THREAD_ROUTINE)KsWorkSinkItemWorker;
  this->m_WorkItem.Parameter = (PVOID)((unsigned __int64)&this->IKsWorkSink & -(__int64)(this != 0));
  v14 = KsRegisterCountedWorker(DelayedWorkQueue, &this->m_WorkItem, &this->m_Worker);
  if ( v14 >= 0 )
  {
    m_AllocatorFileObject = this->m_AllocatorFileObject;
    if ( m_AllocatorFileObject )
    {
      v25 = 0;
      v26 = 1;
      LODWORD(BytesReturned) = 0;
      InBuffer = GUID_cf6e4342_ec87_11cf_a130_0020afd156e4;
      v14 = KsSynchronousIoControlDevice(
              m_AllocatorFileObject,
              0,
              0x2F0003u,
              &InBuffer,
              0x18u,
              &this->m_AllocatorFunctionTable,
              0x10u,
              (PULONG)&BytesReturned);
      if ( v14 < 0 )
      {
LABEL_13:
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
LABEL_16:
          this->m_AllocatorFileObject = 0;
          return (unsigned int)v14;
        }
        v17 = 15;
LABEL_15:
        LOBYTE(v16) = 4;
        WPP_RECORDER_SF_qD(
          WPP_GLOBAL_Control->DeviceExtension,
          v16,
          1,
          v17,
          (__int64)WPP_01e97eabb7fe30ad0eb84e4d86b22be6_Traceguids,
          (char)this,
          v14);
        goto LABEL_16;
      }
      if ( (_DWORD)BytesReturned != 16 )
      {
        v14 = -1073741306;
        goto LABEL_13;
      }
      v25 = 1;
      v14 = KsSynchronousIoControlDevice(
              this->m_AllocatorFileObject,
              0,
              0x2F0003u,
              &InBuffer,
              0x18u,
              &this->m_AllocatorStatus,
              0x20u,
              (PULONG)&BytesReturned);
      if ( v14 < 0 )
      {
LABEL_20:
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_16;
        v17 = 14;
        goto LABEL_15;
      }
      if ( (_DWORD)BytesReturned != 32 )
      {
        v14 = -1073741306;
        goto LABEL_20;
      }
      PoolType = (unsigned int)this->m_AllocatorStatus.Framing.PoolType;
      FrameSize = this->m_AllocatorStatus.Framing.FrameSize;
      v20 = this->m_AllocatorStatus.Framing.Frames;
      this->m_PassiveLevelRetire = (_DWORD)PoolType == 1;
      this->m_FrameSize = FrameSize;
      this->m_FrameCount = v20;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
        WPP_RECORDER_SF_qqddd((__int64)WPP_GLOBAL_Control->DeviceExtension, FrameSize, v20, PoolType, InSize);
      ObfReferenceObject(this->m_AllocatorFileObject);
    }
    else if ( a5 )
    {
      this->m_RetireFrame = a5;
      a5->AddRef(a5);
    }
  }
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x1800430dc  push    rbx
0x1800430de  push    rbp
0x1800430df  push    rsi
0x1800430e0  push    rdi
0x1800430e1  push    r12
0x1800430e3  push    r13
0x1800430e5  push    r14
0x1800430e7  push    r15
0x1800430e9  sub     rsp, 78h
0x1800430ed  mov     rbp, r9
0x1800430f0  mov     rsi, r8
0x1800430f3  mov     rdi, rdx
0x1800430f6  mov     rbx, rcx
0x1800430f9  xor     r14d, r14d
0x1800430fc  lea     r12, WPP_RECORDER_INITIALIZED
0x180043103  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18004310a  lea     r13, WPP_01e97eabb7fe30ad0eb84e4d86b22be6_Traceguids
0x180043111  lea     r15d, [r14+1]
0x180043115  jz      short loc_18004313C
0x180043117  mov     rcx, cs:WPP_GLOBAL_Control
0x18004311e  cmp     [rcx+48h], r14w
0x180043123  jz      short loc_18004313C
0x180043125  mov     rcx, [rcx+40h]
0x180043129  lea     r9d, [r14+0Bh]
0x18004312d  mov     r8d, r15d
0x180043130  mov     qword ptr [rsp+0B8h+InSize], r13
0x180043135  mov     dl, 5
0x180043137  call    WPP_RECORDER_SF_
0x18004313c  mov     [rbx+50h], rdi
0x180043140  mov     rcx, rdi
0x180043143  mov     rax, [rdi]
0x180043146  mov     rax, [rax+8]
0x18004314a  call    _guard_dispatch_icall
0x18004314f  mov     [rbx+58h], rsi
0x180043153  cmp     rbp, 0FFFFFFFFFFFFFFFFh
0x180043157  jnz     short loc_1800431C6
0x180043159  mov     rax, [rsi]
0x18004315c  mov     rcx, rsi
0x18004315f  mov     rbp, r14
0x180043162  mov     rax, [rax+58h]
0x180043166  call    _guard_dispatch_icall
0x18004316b  mov     rcx, [rax]
0x18004316e  mov     rdx, [rcx+78h]
0x180043172  test    rdx, rdx
0x180043175  jz      short loc_1800431C6
0x180043177  mov     edx, [rdx+60h]
0x18004317a  mov     [rbx+0A0h], edx
0x180043180  mov     rax, [rax]
0x180043183  mov     rcx, [rax+78h]
0x180043187  mov     eax, [rcx+44h]
0x18004318a  mov     [rbx+0A4h], eax
0x180043190  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x180043197  jz      short loc_1800431C6
0x180043199  mov     rcx, cs:WPP_GLOBAL_Control
0x1800431a0  mov     r9d, 0Ch
0x1800431a6  mov     dword ptr [rsp+0B8h+BytesReturned], eax
0x1800431aa  mov     r8d, r15d
0x1800431ad  mov     [rsp+0B8h+OutSize], edx
0x1800431b1  mov     dl, 4
0x1800431b3  mov     [rsp+0B8h+OutBuffer], rbx
0x1800431b8  mov     rcx, [rcx+40h]
0x1800431bc  mov     qword ptr [rsp+0B8h+InSize], r13
0x1800431c1  call    WPP_RECORDER_SF_qdd
0x1800431c6  mov     rax, [rsp+0B8h+arg_28]
0x1800431ce  lea     rcx, [rbx+0B8h]; Event
0x1800431d5  xor     r8d, r8d; State
0x1800431d8  mov     [rbx+148h], rax
0x1800431df  mov     edx, r15d; Type
0x1800431e2  mov     [rbx+60h], rbp
0x1800431e6  mov     [rbx+0ACh], r15w
0x1800431ee  mov     [rbx+0B0h], r14d
0x1800431f5  mov     [rbx+0AEh], r14b
0x1800431fc  mov     [rbx+0A8h], r15d
0x180043203  call    cs:__imp_KeInitializeEvent
0x18004320a  nop     dword ptr [rax+rax+00h]
0x18004320f  lea     rcx, [rbx+0D0h]
0x180043216  mov     [rcx+8], rcx
0x18004321a  mov     [rcx], rcx
0x18004321d  add     rcx, 10h; SpinLock
0x180043221  call    cs:__imp_KeInitializeSpinLock
0x180043228  nop     dword ptr [rax+rax+00h]
0x18004322d  lea     rcx, [rbx+0E8h]
0x180043234  mov     [rcx+8], rcx
0x180043238  mov     [rcx], rcx
0x18004323b  add     rcx, 10h; SpinLock
0x18004323f  call    cs:__imp_KeInitializeSpinLock
0x180043246  nop     dword ptr [rax+rax+00h]
0x18004324b  lea     rcx, [rbx+100h]
0x180043252  mov     [rcx+8], rcx
0x180043256  mov     [rcx], rcx
0x180043259  add     rcx, 10h; SpinLock
0x18004325d  call    cs:__imp_KeInitializeSpinLock
0x180043264  nop     dword ptr [rax+rax+00h]
0x180043269  lea     rdx, [rbx+118h]; CountedWorkItem
0x180043270  lea     rax, KsWorkSinkItemWorker
0x180043277  mov     [rdx], r14
0x18004327a  mov     [rdx+10h], rax
0x18004327e  lea     r8, [rbx+8]
0x180043282  mov     rax, rbx
0x180043285  neg     rax
0x180043288  sbb     rcx, rcx
0x18004328b  and     rcx, r8
0x18004328e  lea     r8, [rbx+138h]; Worker
0x180043295  mov     [rdx+18h], rcx
0x180043299  mov     ecx, r15d; WorkQueueType
0x18004329c  call    KsRegisterCountedWorker
0x1800432a1  mov     edi, eax
0x1800432a3  test    eax, eax
0x1800432a5  js      loc_180043465
0x1800432ab  mov     rcx, [rbx+60h]; FileObject
0x1800432af  test    rcx, rcx
0x1800432b2  jz      loc_180043445
0x1800432b8  movups  xmm0, xmmword ptr cs:_GUID_cf6e4342_ec87_11cf_a130_0020afd156e4.Data1
0x1800432bf  lea     rdx, [rsp+0B8h+arg_28]
0x1800432c7  mov     [rsp+0B8h+var_58], r14d
0x1800432cc  mov     [rsp+0B8h+BytesReturned], rdx; BytesReturned
0x1800432d1  lea     rax, [rbx+68h]
0x1800432d5  mov     [rsp+0B8h+OutSize], 10h; OutSize
0x1800432dd  lea     r9, [rsp+0B8h+InBuffer]; InBuffer
0x1800432e2  mov     [rsp+0B8h+OutBuffer], rax; OutBuffer
0x1800432e7  mov     ebp, 2F0003h
0x1800432ec  mov     esi, 18h
0x1800432f1  mov     [rsp+0B8h+var_54], r15d
0x1800432f6  mov     r8d, ebp; IoControl
0x1800432f9  mov     [rsp+0B8h+InSize], esi; InSize
0x1800432fd  xor     edx, edx; RequestorMode
0x1800432ff  mov     dword ptr [rsp+0B8h+arg_28], r14d
0x180043307  movdqu  [rsp+0B8h+InBuffer], xmm0
0x18004330d  call    KsSynchronousIoControlDevice
0x180043312  mov     edi, eax
0x180043314  test    eax, eax
0x180043316  js      short loc_180043327
0x180043318  cmp     dword ptr [rsp+0B8h+arg_28], 10h
0x180043320  jz      short loc_18004336A
0x180043322  mov     edi, 0C0000206h
0x180043327  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18004332e  jz      short loc_180043361
0x180043330  mov     r9d, 0Fh
0x180043336  mov     rcx, cs:WPP_GLOBAL_Control
0x18004333d  mov     r8d, r15d
0x180043340  mov     [rsp+0B8h+OutSize], edi
0x180043344  mov     dl, 4
0x180043346  mov     [rsp+0B8h+OutBuffer], rbx
0x18004334b  mov     qword ptr [rsp+0B8h+InSize], r13
0x180043350  mov     rcx, [rcx+40h]
0x180043354  call    WPP_RECORDER_SF_qD
0x180043359  test    edi, edi
0x18004335b  jns     loc_180043465
0x180043361  mov     [rbx+60h], r14
0x180043365  jmp     loc_180043465
0x18004336a  lea     rcx, [rsp+0B8h+arg_28]
0x180043372  mov     [rsp+0B8h+var_58], r15d
0x180043377  mov     [rsp+0B8h+BytesReturned], rcx; BytesReturned
0x18004337c  lea     rax, [rbx+78h]
0x180043380  mov     rcx, [rbx+60h]; FileObject
0x180043384  lea     r9, [rsp+0B8h+InBuffer]; InBuffer
0x180043389  mov     [rsp+0B8h+OutSize], 20h ; ' '; OutSize
0x180043391  mov     r8d, ebp; IoControl
0x180043394  mov     [rsp+0B8h+OutBuffer], rax; OutBuffer
0x180043399  xor     edx, edx; RequestorMode
0x18004339b  mov     [rsp+0B8h+InSize], esi; InSize
0x18004339f  call    KsSynchronousIoControlDevice
0x1800433a4  mov     edi, eax
0x1800433a6  test    eax, eax
0x1800433a8  js      short loc_1800433B9
0x1800433aa  cmp     dword ptr [rsp+0B8h+arg_28], 20h ; ' '
0x1800433b2  jz      short loc_1800433CD
0x1800433b4  mov     edi, 0C0000206h
0x1800433b9  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1800433c0  jz      short loc_180043361
0x1800433c2  mov     r9d, 0Eh
0x1800433c8  jmp     loc_180043336
0x1800433cd  mov     r9d, [rbx+7Ch]
0x1800433d1  cmp     r9d, r15d
0x1800433d4  mov     edx, [rbx+84h]
0x1800433da  mov     r8d, [rbx+80h]
0x1800433e1  setz    al
0x1800433e4  mov     [rbx+0AFh], al
0x1800433ea  mov     [rbx+0A0h], edx
0x1800433f0  mov     [rbx+0A4h], r8d
0x1800433f7  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1800433fe  jz      short loc_180043433
0x180043400  mov     rcx, cs:WPP_GLOBAL_Control
0x180043407  cmp     [rcx+48h], r14w
0x18004340c  jz      short loc_180043433
0x18004340e  mov     rax, [rbx+60h]
0x180043412  mov     rcx, [rcx+40h]
0x180043416  mov     [rsp+0B8h+var_70], r9d
0x18004341b  mov     [rsp+0B8h+var_78], r8d
0x180043420  mov     dword ptr [rsp+0B8h+BytesReturned], edx
0x180043424  mov     qword ptr [rsp+0B8h+OutSize], rax
0x180043429  mov     [rsp+0B8h+OutBuffer], rbx
0x18004342e  call    WPP_RECORDER_SF_qqddd
0x180043433  mov     rcx, [rbx+60h]; Object
0x180043437  call    cs:__imp_ObfReferenceObject
0x18004343e  nop     dword ptr [rax+rax+00h]
0x180043443  jmp     short loc_180043465
0x180043445  mov     rcx, [rsp+0B8h+arg_20]
0x18004344d  test    rcx, rcx
0x180043450  jz      short loc_180043465
0x180043452  mov     [rbx+140h], rcx
0x180043459  mov     rax, [rcx]
0x18004345c  mov     rax, [rax+8]
0x180043460  call    _guard_dispatch_icall
0x180043465  mov     eax, edi
0x180043467  add     rsp, 78h
0x18004346b  pop     r15
0x18004346d  pop     r14
0x18004346f  pop     r13
0x180043471  pop     r12
0x180043473  pop     rdi
0x180043474  pop     rsi
0x180043475  pop     rbp
0x180043476  pop     rbx
0x180043477  retn
```
