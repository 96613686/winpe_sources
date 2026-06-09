# CKsQueue::UnlockStreamPointer(_KSPSTREAM_POINTER *,KSPSTREAM_POINTER_MOTION)

- ea: `0x1800021b0`
- end: `0x18000263a`
- name: `?UnlockStreamPointer@CKsQueue@@UEAAXPEAU_KSPSTREAM_POINTER@@W4KSPSTREAM_POINTER_MOTION@@@Z`
- size: `1162`
- prototype: `void __fastcall(CKsQueue *__hidden this, struct _KSPSTREAM_POINTER *, enum KSPSTREAM_POINTER_MOTION)`
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800021b0`
- `0x180002640`
- `0x180002d20`
- `0x1800031c8`
- `0x180003480`
- `0x1800035bc`
- `0x18000374c`
- `0x180005258`
- `0x18000b7bc`
- `0x180019c60`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x18000223a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x180002348`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x18000223a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x180002348`
- `ntoskrnl!KeReleaseSpinLock` at `0x180002286`
- `ntoskrnl!KeReleaseSpinLock` at `0x18000236e`
- `ntoskrnl!KeReleaseSpinLock` at `0x1800023a5`
- `ntoskrnl!KeReleaseSpinLock` at `0x180002459`
- `ntoskrnl!KeReleaseSpinLock` at `0x18000252b`
- `ntoskrnl!KeReleaseSpinLock` at `0x180002568`
- `ntoskrnl!KeReleaseSpinLock` at `0x180002286`
- `ntoskrnl!KeReleaseSpinLock` at `0x18000236e`
- `ntoskrnl!KeReleaseSpinLock` at `0x1800023a5`
- `ntoskrnl!KeReleaseSpinLock` at `0x180002459`
- `ntoskrnl!KeReleaseSpinLock` at `0x18000252b`
- `ntoskrnl!KeReleaseSpinLock` at `0x180002568`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1800024a6`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1800024a6`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x180002469`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x180002469`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x1800024b4`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x1800024b4`
- `ntoskrnl!ExInterlockedRemoveHeadList` at `0x1800022d0`
- `ntoskrnl!ExInterlockedRemoveHeadList` at `0x180002309`
- `ntoskrnl!ExInterlockedRemoveHeadList` at `0x1800022d0`
- `ntoskrnl!ExInterlockedRemoveHeadList` at `0x180002309`
- `ntoskrnl!IofCompleteRequest` at `0x180002612`
- `ntoskrnl!IofCompleteRequest` at `0x180002612`

## pseudocode

```c
void __fastcall CKsQueue::UnlockStreamPointer(
        CKsQueue *this,
        struct _KSPSTREAM_POINTER *a2,
        enum KSPSTREAM_POINTER_MOTION a3)
{
  __int64 *v6; // rdx
  _KSPFRAME_HEADER *FrameHeader; // rax
  struct _IRP *Irp; // rsi
  struct KSPIRP_FRAMING_ *IrpFraming; // r14
  INTERLOCKEDLIST_HEAD *p_m_FrameQueue; // r15
  KIRQL v11; // al
  _KSPFRAME_HEADER *v12; // r8
  KIRQL v13; // r12
  struct _KSPFRAME_HEADER *Flink; // r8
  KSPIN_LOCK *p_SpinLock; // rbx
  PLIST_ENTRY i; // rax
  int v17; // edx
  KIRQL v18; // al
  int RefCount; // edx
  char v20; // bp
  ULONG Count; // ecx
  ULONG Remaining; // eax
  int v23; // edx
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rbp
  CKsQueue *v25; // rbx
  __int64 v26; // r9
  struct _LIST_ENTRY *j; // rdx
  IKsTransport *m_TransportSink; // rcx
  struct _IRP *v29; // [rsp+68h] [rbp+10h] BYREF

  v6 = WPP_c705d9135b58358f87ecf40b472c5dce_Traceguids;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LOBYTE(v6) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)v6,
      1,
      21,
      (__int64)WPP_c705d9135b58358f87ecf40b472c5dce_Traceguids);
    v6 = WPP_c705d9135b58358f87ecf40b472c5dce_Traceguids;
  }
  if ( a2->State == KSPSTREAM_POINTER_STATE_LOCKED )
  {
    FrameHeader = a2->FrameHeader;
    Irp = FrameHeader->Irp;
    IrpFraming = FrameHeader->IrpFraming;
    v29 = Irp;
    if ( a3 )
    {
      if ( this->m_OutputData )
      {
        if ( a2 == this->m_Leading && (a2->Public.StreamHeader->OptionsFlags & 0x200) != 0 )
          this->m_EndOfStream = 1;
        if ( !this->m_GenerateMappings )
        {
          Count = a2->Public.OffsetOut.Count;
          Remaining = a2->Public.OffsetOut.Remaining;
          if ( Remaining != Count )
            a2->Public.StreamHeader->DataUsed = Count - Remaining;
        }
      }
      p_m_FrameQueue = &this->m_FrameQueue;
      v11 = KeAcquireSpinLockRaiseToDpc(&this->m_FrameQueue.SpinLock);
      v12 = a2->FrameHeader;
      v13 = v11;
      if ( v12 )
      {
        if ( a3 == KSPSTREAM_POINTER_MOTION_CLEAR )
        {
          Flink = 0;
        }
        else
        {
          Flink = (struct _KSPFRAME_HEADER *)v12->ListEntry.Flink;
          if ( Flink == (struct _KSPFRAME_HEADER *)p_m_FrameQueue )
            Flink = 0;
        }
        CKsQueue::SetStreamPointer(this, a2, Flink, &v29);
        Irp = v29;
      }
      KeReleaseSpinLock(&this->m_FrameQueue.SpinLock, v13);
      v6 = WPP_c705d9135b58358f87ecf40b472c5dce_Traceguids;
    }
    else
    {
      p_m_FrameQueue = &this->m_FrameQueue;
    }
    a2->State = KSPSTREAM_POINTER_STATE_UNLOCKED;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
    {
      LOBYTE(v6) = 5;
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)v6,
        1,
        68,
        (__int64)WPP_c705d9135b58358f87ecf40b472c5dce_Traceguids);
    }
    p_SpinLock = &p_m_FrameQueue->SpinLock;
    for ( i = ExInterlockedRemoveHeadList(&this->m_WaitingIrps, &p_m_FrameQueue->SpinLock);
          i;
          i = ExInterlockedRemoveHeadList(&this->m_WaitingIrps, &this->m_FrameQueue.SpinLock) )
    {
      CKsQueue::ForwardIrp(this, (struct _IRP *)&i[-11].Blink, (struct KSPIRP_FRAMING_ *)&i[1].Flink->Blink, 0);
    }
    if ( !Irp )
      goto LABEL_29;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
    {
      LOBYTE(v17) = 5;
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        v17,
        1,
        66,
        (__int64)WPP_c705d9135b58358f87ecf40b472c5dce_Traceguids);
    }
    v18 = KeAcquireSpinLockRaiseToDpc(p_SpinLock);
    RefCount = IrpFraming->RefCount;
    IrpFraming->RefCount = RefCount - 1;
    if ( RefCount != 1 )
    {
      KeReleaseSpinLock(p_SpinLock, v18);
LABEL_29:
      if ( this->m_EndOfStream )
      {
        if ( a3 != KSPSTREAM_POINTER_MOTION_FLUSH )
          CKsQueue::Flush(this);
      }
      return;
    }
    v20 = 1;
    if ( IrpFraming->QueuedFrameHeaderCount )
    {
      _InterlockedExchange64((volatile __int64 *)&Irp->CancelRoutine, (__int64)CKsQueue::CancelRoutine);
      if ( Irp->Cancel && _InterlockedExchange64((volatile __int64 *)&Irp->CancelRoutine, 0) )
      {
        KeReleaseSpinLock(&this->m_FrameQueue.SpinLock, v18);
        IoAcquireCancelSpinLock(&Irp->CancelIrql);
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
        {
          LOBYTE(v23) = 5;
          WPP_RECORDER_SF_(
            WPP_GLOBAL_Control->DeviceExtension,
            v23,
            1,
            57,
            (__int64)WPP_c705d9135b58358f87ecf40b472c5dce_Traceguids);
        }
        CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
        v25 = *(CKsQueue **)(CurrentStackLocation->Parameters.Read.ByteOffset.QuadPart + 24);
        KeAcquireSpinLockAtDpcLevel(&v25->m_FrameQueue.SpinLock);
        IoReleaseCancelSpinLock(2u);
        CKsQueue::CancelStreamPointers(v25, Irp);
        CKsQueue::RemoveIrpFrameHeaders(v25, Irp);
        Irp->IoStatus.Status = -1073741536;
        if ( *(&CurrentStackLocation->Parameters.Read.Length + 1) )
        {
          KeReleaseSpinLock(&v25->m_FrameQueue.SpinLock, Irp->CancelIrql);
        }
        else
        {
          LOBYTE(v26) = 1;
          v25->MdlCacheSetIrpMdlAddress(
            &v25->IKsMdlCache,
            (KSPIRP_FRAMING_ *)&CurrentStackLocation->Parameters,
            Irp,
            v26);
          for ( j = (struct _LIST_ENTRY *)CurrentStackLocation->Parameters.Read.ByteOffset.QuadPart;
                j;
                j = (struct _LIST_ENTRY *)CurrentStackLocation->Parameters.Read.ByteOffset.QuadPart )
          {
            CurrentStackLocation->Parameters.Read.ByteOffset.QuadPart = (LONGLONG)j[1].Flink;
            CKsQueue::PutAvailableFrameHeader(v25, j);
          }
          KeReleaseSpinLock(&v25->m_FrameQueue.SpinLock, Irp->CancelIrql);
          m_TransportSink = v25->m_TransportSink;
          if ( m_TransportSink )
            KspDiscardKsIrp(m_TransportSink, Irp);
          else
            IofCompleteRequest(Irp, 0);
        }
        goto LABEL_29;
      }
      v20 = 0;
    }
    KeReleaseSpinLock(p_SpinLock, v18);
    if ( v20 )
      CKsQueue::ForwardIrp(this, Irp, IrpFraming, 0);
    goto LABEL_29;
  }
}

```

## disassembly

```asm
0x1800021b0  push    rbx
0x1800021b2  push    rdi
0x1800021b3  push    r12
0x1800021b5  push    r13
0x1800021b7  sub     rsp, 38h
0x1800021bb  mov     r13d, r8d
0x1800021be  mov     rbx, rdx
0x1800021c1  mov     rdi, rcx
0x1800021c4  lea     r12, WPP_RECORDER_INITIALIZED
0x1800021cb  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1800021d2  lea     rdx, WPP_c705d9135b58358f87ecf40b472c5dce_Traceguids
0x1800021d9  jz      short loc_1800021ED
0x1800021db  mov     rcx, cs:WPP_GLOBAL_Control
0x1800021e2  cmp     word ptr [rcx+48h], 0
0x1800021e7  jnz     loc_180002579
0x1800021ed  cmp     dword ptr [rbx+38h], 1
0x1800021f1  jnz     loc_1800023E5
0x1800021f7  mov     rax, [rbx+50h]
0x1800021fb  mov     [rsp+58h+arg_0], rbp
0x180002200  mov     [rsp+58h+arg_10], rsi
0x180002205  mov     [rsp+58h+arg_18], r14
0x18000220a  mov     rsi, [rax+30h]
0x18000220e  mov     r14, [rax+38h]
0x180002212  mov     [rsp+58h+arg_8], rsi
0x180002217  mov     [rsp+58h+var_28], r15
0x18000221c  test    r13d, r13d
0x18000221f  jz      loc_180002551
0x180002225  cmp     byte ptr [rdi+73h], 0
0x180002229  jnz     loc_1800023F1
0x18000222f  lea     r15, [rdi+130h]
0x180002236  lea     rcx, [r15+10h]; SpinLock
0x18000223a  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x180002241  nop     dword ptr [rax+rax+00h]
0x180002246  mov     r8, [rbx+50h]
0x18000224a  movzx   r12d, al
0x18000224e  test    r8, r8
0x180002251  jz      short loc_18000227E
0x180002253  lea     r9, [rsp+58h+arg_8]; struct _IRP **
0x180002258  mov     rdx, rbx; struct _KSPSTREAM_POINTER *
0x18000225b  mov     rcx, rdi; this
0x18000225e  cmp     r13d, 2
0x180002262  jz      loc_180002437
0x180002268  mov     r8, [r8]
0x18000226b  xor     eax, eax
0x18000226d  cmp     r8, r15
0x180002270  cmovz   r8, rax; struct _KSPFRAME_HEADER *
0x180002274  call    ?SetStreamPointer@CKsQueue@@AEAAXPEAU_KSPSTREAM_POINTER@@PEAU_KSPFRAME_HEADER@@PEAPEAU_IRP@@@Z; CKsQueue::SetStreamPointer(_KSPSTREAM_POINTER *,_KSPFRAME_HEADER *,_IRP * *)
0x180002279  mov     rsi, [rsp+58h+arg_8]
0x18000227e  movzx   edx, r12b; NewIrql
0x180002282  lea     rcx, [r15+10h]; SpinLock
0x180002286  call    cs:__imp_KeReleaseSpinLock
0x18000228d  nop     dword ptr [rax+rax+00h]
0x180002292  lea     rdx, WPP_c705d9135b58358f87ecf40b472c5dce_Traceguids
0x180002299  lea     r12, WPP_RECORDER_INITIALIZED
0x1800022a0  mov     dword ptr [rbx+38h], 0
0x1800022a7  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1800022ae  jz      short loc_1800022C2
0x1800022b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800022b7  cmp     word ptr [rcx+48h], 0
0x1800022bc  jnz     loc_1800025AA
0x1800022c2  lea     rbx, [r15+10h]
0x1800022c6  mov     rdx, rbx; Lock
0x1800022c9  lea     rcx, [rdi+178h]; ListHead
0x1800022d0  call    cs:__imp_ExInterlockedRemoveHeadList
0x1800022d7  nop     dword ptr [rax+rax+00h]
0x1800022dc  test    rax, rax
0x1800022df  jz      short loc_18000231A
0x1800022e1  mov     r8, [rax+10h]
0x1800022e5  lea     rdx, [rax-0A8h]; struct _IRP *
0x1800022ec  add     r8, 8; struct KSPIRP_FRAMING_ *
0x1800022f0  xor     r9d, r9d; struct IKsTransport **
0x1800022f3  mov     rcx, rdi; this
0x1800022f6  call    ?ForwardIrp@CKsQueue@@AEAAXPEAU_IRP@@PEAUKSPIRP_FRAMING_@@PEAPEAUIKsTransport@@@Z; CKsQueue::ForwardIrp(_IRP *,KSPIRP_FRAMING_ *,IKsTransport * *)
0x1800022fb  lea     rdx, [rdi+140h]; Lock
0x180002302  lea     rcx, [rdi+178h]; ListHead
0x180002309  call    cs:__imp_ExInterlockedRemoveHeadList
0x180002310  nop     dword ptr [rax+rax+00h]
0x180002315  test    rax, rax
0x180002318  jnz     short loc_1800022E1
0x18000231a  test    rsi, rsi
0x18000231d  jz      loc_1800023C7
0x180002323  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18000232a  lea     r15, WPP_c705d9135b58358f87ecf40b472c5dce_Traceguids
0x180002331  jz      short loc_180002345
0x180002333  mov     rcx, cs:WPP_GLOBAL_Control
0x18000233a  cmp     word ptr [rcx+48h], 0
0x18000233f  jnz     loc_1800025CB
0x180002345  mov     rcx, rbx; SpinLock
0x180002348  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x18000234f  nop     dword ptr [rax+rax+00h]
0x180002354  mov     edx, [r14+4]
0x180002358  movzx   r8d, al
0x18000235c  lea     ecx, [rdx-1]
0x18000235f  mov     [r14+4], ecx
0x180002363  cmp     edx, 1
0x180002366  jz      short loc_18000237C
0x180002368  movzx   edx, al; NewIrql
0x18000236b  mov     rcx, rbx; SpinLock
0x18000236e  call    cs:__imp_KeReleaseSpinLock
0x180002375  nop     dword ptr [rax+rax+00h]
0x18000237a  jmp     short loc_1800023C7
0x18000237c  cmp     dword ptr [r14+8], 0
0x180002381  mov     bpl, 1
0x180002384  jz      short loc_18000239E
0x180002386  lea     rax, ?CancelRoutine@CKsQueue@@CAXPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z; CKsQueue::CancelRoutine(_DEVICE_OBJECT *,_IRP *)
0x18000238d  xchg    rax, [rsi+68h]
0x180002391  cmp     byte ptr [rsi+44h], 0
0x180002395  jnz     loc_18000243F
0x18000239b  xor     bpl, bpl
0x18000239e  movzx   edx, r8b; NewIrql
0x1800023a2  mov     rcx, rbx; SpinLock
0x1800023a5  call    cs:__imp_KeReleaseSpinLock
0x1800023ac  nop     dword ptr [rax+rax+00h]
0x1800023b1  test    bpl, bpl
0x1800023b4  jz      short loc_1800023C7
0x1800023b6  xor     r9d, r9d; struct IKsTransport **
0x1800023b9  mov     r8, r14; struct KSPIRP_FRAMING_ *
0x1800023bc  mov     rdx, rsi; struct _IRP *
0x1800023bf  mov     rcx, rdi; this
0x1800023c2  call    ?ForwardIrp@CKsQueue@@AEAAXPEAU_IRP@@PEAUKSPIRP_FRAMING_@@PEAPEAUIKsTransport@@@Z; CKsQueue::ForwardIrp(_IRP *,KSPIRP_FRAMING_ *,IKsTransport * *)
0x1800023c7  cmp     byte ptr [rdi+61h], 0
0x1800023cb  mov     r15, [rsp+58h+var_28]
0x1800023d0  mov     r14, [rsp+58h+arg_18]
0x1800023d5  mov     rsi, [rsp+58h+arg_10]
0x1800023da  mov     rbp, [rsp+58h+arg_0]
0x1800023df  jnz     loc_180002623
0x1800023e5  add     rsp, 38h
0x1800023e9  pop     r13
0x1800023eb  pop     r12
0x1800023ed  pop     rdi
0x1800023ee  pop     rbx
0x1800023ef  retn
0x1800023f1  cmp     rbx, [rdi+250h]
0x1800023f8  jnz     short loc_18000240B
0x1800023fa  mov     rax, [rbx+70h]
0x1800023fe  test    dword ptr [rax+30h], 200h
0x180002405  jnz     loc_1800025A1
0x18000240b  cmp     byte ptr [rdi+75h], 0
0x18000240f  jnz     loc_18000222F
0x180002415  mov     ecx, [rbx+98h]
0x18000241b  mov     eax, [rbx+9Ch]
0x180002421  cmp     eax, ecx
0x180002423  jz      loc_18000222F
0x180002429  sub     ecx, eax
0x18000242b  mov     rax, [rbx+70h]
0x18000242f  mov     [rax+24h], ecx
0x180002432  jmp     loc_18000222F
0x180002437  xor     r8d, r8d
0x18000243a  jmp     loc_180002274
0x18000243f  xor     eax, eax
0x180002441  xchg    rax, [rsi+68h]
0x180002445  test    rax, rax
0x180002448  jz      loc_18000239B
0x18000244e  lea     rcx, [rdi+140h]; SpinLock
0x180002455  movzx   edx, r8b; NewIrql
0x180002459  call    cs:__imp_KeReleaseSpinLock
0x180002460  nop     dword ptr [rax+rax+00h]
0x180002465  lea     rcx, [rsi+45h]; Irql
0x180002469  call    cs:__imp_IoAcquireCancelSpinLock
0x180002470  nop     dword ptr [rax+rax+00h]
0x180002475  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18000247c  jz      short loc_180002490
0x18000247e  mov     rcx, cs:WPP_GLOBAL_Control
0x180002485  cmp     word ptr [rcx+48h], 0
0x18000248a  jnz     loc_1800025EC
0x180002490  mov     rbp, [rsi+0B8h]
0x180002497  mov     rax, [rbp+18h]
0x18000249b  mov     rbx, [rax+18h]
0x18000249f  lea     rcx, [rbx+140h]; SpinLock
0x1800024a6  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x1800024ad  nop     dword ptr [rax+rax+00h]
0x1800024b2  mov     cl, 2; Irql
0x1800024b4  call    cs:__imp_IoReleaseCancelSpinLock
0x1800024bb  nop     dword ptr [rax+rax+00h]
0x1800024c0  mov     rdx, rsi; struct _IRP *
0x1800024c3  mov     rcx, rbx; this
0x1800024c6  call    ?CancelStreamPointers@CKsQueue@@AEAAXPEAU_IRP@@@Z; CKsQueue::CancelStreamPointers(_IRP *)
0x1800024cb  mov     rdx, rsi; struct _IRP *
0x1800024ce  mov     rcx, rbx; this
0x1800024d1  call    ?RemoveIrpFrameHeaders@CKsQueue@@AEAAXPEAU_IRP@@@Z; CKsQueue::RemoveIrpFrameHeaders(_IRP *)
0x1800024d6  mov     dword ptr [rsi+30h], 0C0000120h
0x1800024dd  cmp     dword ptr [rbp+0Ch], 0
0x1800024e1  jnz     short loc_18000255D
0x1800024e3  mov     rax, [rbx+8]
0x1800024e7  lea     rcx, [rbx+8]
0x1800024eb  mov     r9b, 1
0x1800024ee  lea     rdx, [rbp+8]
0x1800024f2  mov     r8, rsi
0x1800024f5  mov     rax, [rax+38h]
0x1800024f9  call    _guard_dispatch_icall
0x1800024fe  mov     rdx, [rbp+18h]; ListEntry
0x180002502  test    rdx, rdx
0x180002505  jz      short loc_180002520
0x180002507  mov     rax, [rdx+10h]
0x18000250b  mov     rcx, rbx; this
0x18000250e  mov     [rbp+18h], rax
0x180002512  call    ?PutAvailableFrameHeader@CKsQueue@@AEAAXPEAU_KSPFRAME_HEADER@@@Z; CKsQueue::PutAvailableFrameHeader(_KSPFRAME_HEADER *)
0x180002517  mov     rdx, [rbp+18h]
0x18000251b  test    rdx, rdx
0x18000251e  jnz     short loc_180002507
0x180002520  movzx   edx, byte ptr [rsi+45h]; NewIrql
0x180002524  lea     rcx, [rbx+140h]; SpinLock
0x18000252b  call    cs:__imp_KeReleaseSpinLock
0x180002532  nop     dword ptr [rax+rax+00h]
0x180002537  mov     rcx, [rbx+50h]
0x18000253b  test    rcx, rcx
0x18000253e  jz      loc_18000260D
0x180002544  mov     rdx, rsi
0x180002547  call    KspDiscardKsIrp
0x18000254c  jmp     loc_1800023C7
0x180002551  lea     r15, [rdi+130h]
0x180002558  jmp     loc_1800022A0
0x18000255d  movzx   edx, byte ptr [rsi+45h]; NewIrql
0x180002561  lea     rcx, [rbx+140h]; SpinLock
0x180002568  call    cs:__imp_KeReleaseSpinLock
0x18000256f  nop     dword ptr [rax+rax+00h]
0x180002574  jmp     loc_1800023C7
0x180002579  mov     rcx, [rcx+40h]
0x18000257d  mov     r9d, 15h
0x180002583  mov     [rsp+58h+var_38], rdx
0x180002588  mov     r8d, 1
0x18000258e  mov     dl, 5
0x180002590  call    WPP_RECORDER_SF_
0x180002595  lea     rdx, WPP_c705d9135b58358f87ecf40b472c5dce_Traceguids
0x18000259c  jmp     loc_1800021ED
0x1800025a1  mov     byte ptr [rdi+61h], 1
0x1800025a5  jmp     loc_18000240B
0x1800025aa  mov     rcx, [rcx+40h]
0x1800025ae  mov     r9d, 44h ; 'D'
0x1800025b4  mov     [rsp+58h+var_38], rdx
0x1800025b9  mov     r8d, 1
0x1800025bf  mov     dl, 5
0x1800025c1  call    WPP_RECORDER_SF_
0x1800025c6  jmp     loc_1800022C2
0x1800025cb  mov     rcx, [rcx+40h]
0x1800025cf  mov     r9d, 42h ; 'B'
0x1800025d5  mov     r8d, 1
0x1800025db  mov     [rsp+58h+var_38], r15
0x1800025e0  mov     dl, 5
0x1800025e2  call    WPP_RECORDER_SF_
0x1800025e7  jmp     loc_180002345
0x1800025ec  mov     rcx, [rcx+40h]
0x1800025f0  mov     r9d, 39h ; '9'
0x1800025f6  mov     r8d, 1
0x1800025fc  mov     [rsp+58h+var_38], r15
0x180002601  mov     dl, 5
0x180002603  call    WPP_RECORDER_SF_
0x180002608  jmp     loc_180002490
0x18000260d  xor     edx, edx; PriorityBoost
0x18000260f  mov     rcx, rsi; Irp
0x180002612  call    cs:__imp_IofCompleteRequest
0x180002619  nop     dword ptr [rax+rax+00h]
0x18000261e  jmp     loc_1800023C7
0x180002623  cmp     r13d, 3
0x180002627  jz      loc_1800023E5
0x18000262d  mov     rcx, rdi; this
0x180002630  call    ?Flush@CKsQueue@@AEAAXXZ; CKsQueue::Flush(void)
0x180002635  jmp     loc_1800023E5
```
