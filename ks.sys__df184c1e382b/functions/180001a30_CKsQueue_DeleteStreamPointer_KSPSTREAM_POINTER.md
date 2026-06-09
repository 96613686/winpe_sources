# CKsQueue::DeleteStreamPointer(_KSPSTREAM_POINTER *)

- ea: `0x180001a30`
- end: `0x180001e21`
- name: `?DeleteStreamPointer@CKsQueue@@UEAAXPEAU_KSPSTREAM_POINTER@@@Z`
- size: `1009`
- prototype: `void __fastcall(CKsQueue *__hidden this, struct _KSPSTREAM_POINTER *)`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180001a30`
- `0x180002640`
- `0x180002d20`
- `0x1800031c8`
- `0x18000374c`
- `0x1800037e0`
- `0x180003948`
- `0x18000b7bc`
- `0x180019cb0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x180001a94`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x180001b41`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x180001a94`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x180001b41`
- `ntoskrnl!KeReleaseSpinLock` at `0x180001b1a`
- `ntoskrnl!KeReleaseSpinLock` at `0x180001b57`
- `ntoskrnl!KeReleaseSpinLock` at `0x180001b1a`
- `ntoskrnl!KeReleaseSpinLock` at `0x180001b57`
- `ntoskrnl!ExInterlockedRemoveHeadList` at `0x180001bd4`
- `ntoskrnl!ExInterlockedRemoveHeadList` at `0x180001c09`
- `ntoskrnl!ExInterlockedRemoveHeadList` at `0x180001bd4`
- `ntoskrnl!ExInterlockedRemoveHeadList` at `0x180001c09`
- `ntoskrnl!IofCompleteRequest` at `0x180001e10`
- `ntoskrnl!IofCompleteRequest` at `0x180001e10`
- `ntoskrnl!ExFreePoolWithTag` at `0x180001b92`
- `ntoskrnl!ExFreePoolWithTag` at `0x180001b92`
- `ntoskrnl!KeSetEvent` at `0x180001da6`
- `ntoskrnl!KeSetEvent` at `0x180001dc3`
- `ntoskrnl!KeSetEvent` at `0x180001da6`
- `ntoskrnl!KeSetEvent` at `0x180001dc3`

## pseudocode

```c
void __fastcall CKsQueue::DeleteStreamPointer(CKsQueue *this, struct _KSPSTREAM_POINTER *a2)
{
  struct _KSPSTREAM_POINTER *v2; // rbx
  int v4; // edx
  KIRQL v5; // si
  struct _LIST_ENTRY *Flink; // rcx
  _LIST_ENTRY *p_TimeoutListEntry; // rax
  KSPSTREAM_POINTER_STATE State; // eax
  IRP *Irp; // r14
  struct _LIST_ENTRY *v10; // rax
  struct _LIST_ENTRY *v11; // rcx
  int v12; // edx
  int v13; // edx
  PLIST_ENTRY j; // rax
  struct _LIST_ENTRY *Blink; // rdx
  __int64 Time; // rax
  KSPIRP_FRAMING_ *IrpFraming; // r15
  int RefCount; // ecx
  _KSPFRAME_HEADER *FrameHeader; // rax
  IKsMdlCache *m_MdlCacheComponent; // rcx
  struct _LIST_ENTRY *i; // rcx
  IKsTransport *m_TransportSink; // rcx

  v2 = a2;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)a2,
      1,
      12,
      (__int64)WPP_13a31f976c1e3a0a846d2ee29290b270_Traceguids);
  }
  if ( KeGetCurrentThread() == this->m_LockContext )
  {
    v2->State = KSPSTREAM_POINTER_STATE_DELETED;
    return;
  }
  v5 = KeAcquireSpinLockRaiseToDpc(&this->m_FrameQueue.SpinLock);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LOBYTE(v4) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      v4,
      1,
      30,
      (__int64)WPP_13a31f976c1e3a0a846d2ee29290b270_Traceguids);
  }
  Flink = v2->TimeoutListEntry.Flink;
  p_TimeoutListEntry = &v2->TimeoutListEntry;
  if ( Flink )
  {
    if ( Flink->Blink != p_TimeoutListEntry )
      goto LABEL_29;
    Blink = v2->TimeoutListEntry.Blink;
    if ( Blink->Flink != p_TimeoutListEntry )
      goto LABEL_29;
    Blink->Flink = Flink;
    Flink->Blink = Blink;
    p_TimeoutListEntry->Flink = 0;
    Time = CKsQueue::GetTime(this, 0);
    CKsQueue::SetTimerUnsafe(this, Time);
  }
  State = v2->State;
  Irp = 0;
  if ( State == KSPSTREAM_POINTER_STATE_CANCEL_PENDING )
  {
    IrpFraming = v2->FrameHeader->IrpFraming;
    RefCount = IrpFraming->RefCount;
    IrpFraming->RefCount = RefCount - 1;
    if ( RefCount == 1 )
    {
      FrameHeader = v2->FrameHeader;
      m_MdlCacheComponent = this->m_MdlCacheComponent;
      Irp = FrameHeader->Irp;
      if ( m_MdlCacheComponent )
        m_MdlCacheComponent->MdlCacheSetIrpMdlAddress(m_MdlCacheComponent, IrpFraming, FrameHeader->Irp, 0);
      for ( i = &IrpFraming->FrameHeaders->ListEntry; i; i = &IrpFraming->FrameHeaders->ListEntry )
      {
        IrpFraming->FrameHeaders = (_KSPFRAME_HEADER *)i[1].Flink;
        CKsQueue::PutAvailableFrameHeader(this, i);
      }
    }
    goto LABEL_15;
  }
  if ( State != KSPSTREAM_POINTER_STATE_DEAD )
  {
    v10 = v2->ListEntry.Flink;
    if ( (struct _KSPSTREAM_POINTER *)v2->ListEntry.Flink->Blink == v2 )
    {
      v11 = v2->ListEntry.Blink;
      if ( (struct _KSPSTREAM_POINTER *)v11->Flink == v2 )
      {
        v11->Flink = v10;
        v10->Blink = v11;
        if ( v2->State == KSPSTREAM_POINTER_STATE_LOCKED )
        {
          KeReleaseSpinLock(&this->m_FrameQueue.SpinLock, v5);
          this->UnlockStreamPointer(this, v2, KSPSTREAM_POINTER_MOTION_CLEAR);
          v5 = KeAcquireSpinLockRaiseToDpc(&this->m_FrameQueue.SpinLock);
        }
        else if ( v2->FrameHeader )
        {
          CKsQueue::SetStreamPointer(this, v2, 0, 0);
        }
        goto LABEL_15;
      }
    }
LABEL_29:
    __fastfail(3u);
  }
LABEL_15:
  KeReleaseSpinLock(&this->m_FrameQueue.SpinLock, v5);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LOBYTE(v12) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      v12,
      1,
      13,
      (__int64)WPP_13a31f976c1e3a0a846d2ee29290b270_Traceguids);
  }
  if ( v2->Type == KSPSTREAM_POINTER_TYPE_INTERNAL
    && _InterlockedExchangeAdd(&this->m_InternalReferenceCountPlusOne, 0xFFFFFFFF) == 1 )
  {
    KeSetEvent(&this->m_InternalReferenceEvent, 0, 0);
  }
  ExFreePoolWithTag(v2, 0);
  if ( _InterlockedExchangeAdd(&this->m_StreamPointersPlusOne, 0xFFFFFFFF) == 1 )
    KeSetEvent(&this->m_DestructEvent, 0, 0);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LOBYTE(v13) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      v13,
      1,
      68,
      (__int64)WPP_13a31f976c1e3a0a846d2ee29290b270_Traceguids);
  }
  for ( j = ExInterlockedRemoveHeadList(&this->m_WaitingIrps, &this->m_FrameQueue.SpinLock);
        j;
        j = ExInterlockedRemoveHeadList(&this->m_WaitingIrps, &this->m_FrameQueue.SpinLock) )
  {
    CKsQueue::ForwardIrp(this, (struct _IRP *)&j[-11].Blink, (struct KSPIRP_FRAMING_ *)&j[1].Flink->Blink, 0);
  }
  if ( Irp )
  {
    m_TransportSink = this->m_TransportSink;
    if ( m_TransportSink )
      KspDiscardKsIrp(m_TransportSink, Irp);
    else
      IofCompleteRequest(Irp, 0);
  }
}

```

## disassembly

```asm
0x180001a30  push    rbx
0x180001a32  push    rdi
0x180001a33  push    r12
0x180001a35  push    r13
0x180001a37  sub     rsp, 38h
0x180001a3b  mov     rbx, rdx
0x180001a3e  mov     rdi, rcx
0x180001a41  lea     r12, WPP_RECORDER_INITIALIZED
0x180001a48  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x180001a4f  lea     r13, WPP_13a31f976c1e3a0a846d2ee29290b270_Traceguids
0x180001a56  jz      short loc_180001A6A
0x180001a58  mov     rcx, cs:WPP_GLOBAL_Control
0x180001a5f  cmp     word ptr [rcx+48h], 0
0x180001a64  jnz     loc_180001CAF
0x180001a6a  mov     rax, gs:188h
0x180001a73  cmp     rax, [rdi+368h]
0x180001a7a  jz      loc_180001C3E
0x180001a80  mov     [rsp+58h+arg_0], rbp
0x180001a85  lea     rbp, [rdi+140h]
0x180001a8c  mov     rcx, rbp; SpinLock
0x180001a8f  mov     [rsp+58h+arg_8], rsi
0x180001a94  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x180001a9b  nop     dword ptr [rax+rax+00h]
0x180001aa0  movzx   esi, al
0x180001aa3  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x180001aaa  jz      short loc_180001ABE
0x180001aac  mov     rcx, cs:WPP_GLOBAL_Control
0x180001ab3  cmp     word ptr [rcx+48h], 0
0x180001ab8  jnz     loc_180001CD0
0x180001abe  mov     rcx, [rbx+10h]
0x180001ac2  lea     rax, [rbx+10h]
0x180001ac6  mov     [rsp+58h+arg_10], r14
0x180001acb  test    rcx, rcx
0x180001ace  jnz     loc_180001C78
0x180001ad4  mov     eax, [rbx+38h]
0x180001ad7  xor     r14d, r14d
0x180001ada  cmp     eax, 4
0x180001add  jz      loc_180001CF1
0x180001ae3  cmp     eax, 5
0x180001ae6  jz      short loc_180001B50
0x180001ae8  mov     rax, [rbx]
0x180001aeb  cmp     [rax+8], rbx
0x180001aef  jnz     loc_180001C51
0x180001af5  mov     rcx, [rbx+8]
0x180001af9  cmp     [rcx], rbx
0x180001afc  jnz     loc_180001C51
0x180001b02  mov     [rcx], rax
0x180001b05  mov     [rax+8], rcx
0x180001b09  cmp     dword ptr [rbx+38h], 1
0x180001b0d  jnz     loc_180001C58
0x180001b13  movzx   edx, sil; NewIrql
0x180001b17  mov     rcx, rbp; SpinLock
0x180001b1a  call    cs:__imp_KeReleaseSpinLock
0x180001b21  nop     dword ptr [rax+rax+00h]
0x180001b26  mov     rax, [rdi]
0x180001b29  mov     r8d, 2
0x180001b2f  mov     rdx, rbx
0x180001b32  mov     rcx, rdi
0x180001b35  mov     rax, [rax+70h]
0x180001b39  call    _guard_dispatch_icall
0x180001b3e  mov     rcx, rbp; SpinLock
0x180001b41  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x180001b48  nop     dword ptr [rax+rax+00h]
0x180001b4d  movzx   esi, al
0x180001b50  movzx   edx, sil; NewIrql
0x180001b54  mov     rcx, rbp; SpinLock
0x180001b57  call    cs:__imp_KeReleaseSpinLock
0x180001b5e  nop     dword ptr [rax+rax+00h]
0x180001b63  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x180001b6a  jz      short loc_180001B7E
0x180001b6c  mov     rcx, cs:WPP_GLOBAL_Control
0x180001b73  cmp     word ptr [rcx+48h], 0
0x180001b78  jnz     loc_180001D66
0x180001b7e  cmp     dword ptr [rbx+3Ch], 1
0x180001b82  mov     esi, 0FFFFFFFFh
0x180001b87  jz      loc_180001D87
0x180001b8d  xor     edx, edx; Tag
0x180001b8f  mov     rcx, rbx; P
0x180001b92  call    cs:__imp_ExFreePoolWithTag
0x180001b99  nop     dword ptr [rax+rax+00h]
0x180001b9e  lock xadd [rdi+0D8h], esi
0x180001ba6  cmp     esi, 1
0x180001ba9  jz      loc_180001DB7
0x180001baf  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x180001bb6  jz      short loc_180001BCA
0x180001bb8  mov     rcx, cs:WPP_GLOBAL_Control
0x180001bbf  cmp     word ptr [rcx+48h], 0
0x180001bc4  jnz     loc_180001DD4
0x180001bca  mov     rdx, rbp; Lock
0x180001bcd  lea     rcx, [rdi+178h]; ListHead
0x180001bd4  call    cs:__imp_ExInterlockedRemoveHeadList
0x180001bdb  nop     dword ptr [rax+rax+00h]
0x180001be0  test    rax, rax
0x180001be3  jz      short loc_180001C1A
0x180001be5  mov     r8, [rax+10h]
0x180001be9  lea     rdx, [rax-0A8h]; struct _IRP *
0x180001bf0  add     r8, 8; struct KSPIRP_FRAMING_ *
0x180001bf4  xor     r9d, r9d; struct IKsTransport **
0x180001bf7  mov     rcx, rdi; this
0x180001bfa  call    ?ForwardIrp@CKsQueue@@AEAAXPEAU_IRP@@PEAUKSPIRP_FRAMING_@@PEAPEAUIKsTransport@@@Z; CKsQueue::ForwardIrp(_IRP *,KSPIRP_FRAMING_ *,IKsTransport * *)
0x180001bff  mov     rdx, rbp; Lock
0x180001c02  lea     rcx, [rdi+178h]; ListHead
0x180001c09  call    cs:__imp_ExInterlockedRemoveHeadList
0x180001c10  nop     dword ptr [rax+rax+00h]
0x180001c15  test    rax, rax
0x180001c18  jnz     short loc_180001BE5
0x180001c1a  test    r14, r14
0x180001c1d  jnz     loc_180001DF5
0x180001c23  mov     r14, [rsp+58h+arg_10]
0x180001c28  mov     rbp, [rsp+58h+arg_0]
0x180001c2d  mov     rsi, [rsp+58h+arg_8]
0x180001c32  add     rsp, 38h
0x180001c36  pop     r13
0x180001c38  pop     r12
0x180001c3a  pop     rdi
0x180001c3b  pop     rbx
0x180001c3c  retn
0x180001c3e  mov     dword ptr [rbx+38h], 3
0x180001c45  add     rsp, 38h
0x180001c49  pop     r13
0x180001c4b  pop     r12
0x180001c4d  pop     rdi
0x180001c4e  pop     rbx
0x180001c4f  retn
0x180001c51  mov     ecx, 3
0x180001c56  int     29h; Win8: RtlFailFast(ecx)
0x180001c58  cmp     [rbx+50h], r14
0x180001c5c  jz      loc_180001B50
0x180001c62  xor     r9d, r9d; struct _IRP **
0x180001c65  xor     r8d, r8d; struct _KSPFRAME_HEADER *
0x180001c68  mov     rdx, rbx; struct _KSPSTREAM_POINTER *
0x180001c6b  mov     rcx, rdi; this
0x180001c6e  call    ?SetStreamPointer@CKsQueue@@AEAAXPEAU_KSPSTREAM_POINTER@@PEAU_KSPFRAME_HEADER@@PEAPEAU_IRP@@@Z; CKsQueue::SetStreamPointer(_KSPSTREAM_POINTER *,_KSPFRAME_HEADER *,_IRP * *)
0x180001c73  jmp     loc_180001B50
0x180001c78  cmp     [rcx+8], rax
0x180001c7c  jnz     short loc_180001C51
0x180001c7e  mov     rdx, [rax+8]
0x180001c82  cmp     [rdx], rax
0x180001c85  jnz     short loc_180001C51
0x180001c87  mov     [rdx], rcx
0x180001c8a  mov     [rcx+8], rdx
0x180001c8e  xor     edx, edx; unsigned __int8
0x180001c90  mov     rcx, rdi; this
0x180001c93  mov     qword ptr [rax], 0
0x180001c9a  call    ?GetTime@CKsQueue@@AEAA_JE@Z; CKsQueue::GetTime(uchar)
0x180001c9f  mov     rdx, rax; __int64
0x180001ca2  mov     rcx, rdi; this
0x180001ca5  call    ?SetTimerUnsafe@CKsQueue@@AEAAX_J@Z; CKsQueue::SetTimerUnsafe(__int64)
0x180001caa  jmp     loc_180001AD4
0x180001caf  mov     rcx, [rcx+40h]
0x180001cb3  mov     r9d, 0Ch
0x180001cb9  mov     r8d, 1
0x180001cbf  mov     [rsp+58h+var_38], r13
0x180001cc4  mov     dl, 5
0x180001cc6  call    WPP_RECORDER_SF_
0x180001ccb  jmp     loc_180001A6A
0x180001cd0  mov     rcx, [rcx+40h]
0x180001cd4  mov     r9d, 1Eh
0x180001cda  mov     r8d, 1
0x180001ce0  mov     [rsp+58h+var_38], r13
0x180001ce5  mov     dl, 5
0x180001ce7  call    WPP_RECORDER_SF_
0x180001cec  jmp     loc_180001ABE
0x180001cf1  mov     rax, [rbx+50h]
0x180001cf5  mov     [rsp+58h+var_28], r15
0x180001cfa  mov     r15, [rax+38h]
0x180001cfe  mov     ecx, [r15+4]
0x180001d02  lea     eax, [rcx-1]
0x180001d05  mov     [r15+4], eax
0x180001d09  cmp     ecx, 1
0x180001d0c  jnz     short loc_180001D5C
0x180001d0e  mov     rax, [rbx+50h]
0x180001d12  mov     rcx, [rdi+248h]
0x180001d19  mov     r14, [rax+30h]
0x180001d1d  test    rcx, rcx
0x180001d20  jz      short loc_180001D37
0x180001d22  mov     rax, [rcx]
0x180001d25  xor     r9d, r9d
0x180001d28  mov     r8, r14
0x180001d2b  mov     rdx, r15
0x180001d2e  mov     rax, [rax+38h]
0x180001d32  call    _guard_dispatch_icall
0x180001d37  mov     rcx, [r15+10h]
0x180001d3b  test    rcx, rcx
0x180001d3e  jz      short loc_180001D5C
0x180001d40  mov     rax, [rcx+10h]
0x180001d44  mov     rdx, rcx; ListEntry
0x180001d47  mov     rcx, rdi; this
0x180001d4a  mov     [r15+10h], rax
0x180001d4e  call    ?PutAvailableFrameHeader@CKsQueue@@AEAAXPEAU_KSPFRAME_HEADER@@@Z; CKsQueue::PutAvailableFrameHeader(_KSPFRAME_HEADER *)
0x180001d53  mov     rcx, [r15+10h]
0x180001d57  test    rcx, rcx
0x180001d5a  jnz     short loc_180001D40
0x180001d5c  mov     r15, [rsp+58h+var_28]
0x180001d61  jmp     loc_180001B50
0x180001d66  mov     rcx, [rcx+40h]
0x180001d6a  mov     r9d, 0Dh
0x180001d70  mov     r8d, 1
0x180001d76  mov     [rsp+58h+var_38], r13
0x180001d7b  mov     dl, 5
0x180001d7d  call    WPP_RECORDER_SF_
0x180001d82  jmp     loc_180001B7E
0x180001d87  mov     eax, esi
0x180001d89  lock xadd [rdi+288h], eax
0x180001d91  cmp     eax, 1
0x180001d94  jnz     loc_180001B8D
0x180001d9a  lea     rcx, [rdi+290h]; Event
0x180001da1  xor     r8d, r8d; Wait
0x180001da4  xor     edx, edx; Increment
0x180001da6  call    cs:__imp_KeSetEvent
0x180001dad  nop     dword ptr [rax+rax+00h]
0x180001db2  jmp     loc_180001B8D
0x180001db7  lea     rcx, [rdi+188h]; Event
0x180001dbe  xor     r8d, r8d; Wait
0x180001dc1  xor     edx, edx; Increment
0x180001dc3  call    cs:__imp_KeSetEvent
0x180001dca  nop     dword ptr [rax+rax+00h]
0x180001dcf  jmp     loc_180001BAF
0x180001dd4  mov     rcx, [rcx+40h]
0x180001dd8  mov     r9d, 44h ; 'D'
0x180001dde  mov     r8d, 1
0x180001de4  mov     [rsp+58h+var_38], r13
0x180001de9  mov     dl, 5
0x180001deb  call    WPP_RECORDER_SF_
0x180001df0  jmp     loc_180001BCA
0x180001df5  mov     rcx, [rdi+50h]
0x180001df9  test    rcx, rcx
0x180001dfc  jz      short loc_180001E0B
0x180001dfe  mov     rdx, r14
0x180001e01  call    KspDiscardKsIrp
0x180001e06  jmp     loc_180001C23
0x180001e0b  xor     edx, edx; PriorityBoost
0x180001e0d  mov     rcx, r14; Irp
0x180001e10  call    cs:__imp_IofCompleteRequest
0x180001e17  nop     dword ptr [rax+rax+00h]
0x180001e1c  jmp     loc_180001C23
```
