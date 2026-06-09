# CKsQueue::ReleaseIrp(_IRP *,KSPIRP_FRAMING_ *,IKsTransport * *)

- ea: `0x180001f00`
- end: `0x1800021a9`
- name: `?ReleaseIrp@CKsQueue@@AEAAXPEAU_IRP@@PEAUKSPIRP_FRAMING_@@PEAPEAUIKsTransport@@@Z`
- size: `681`
- prototype: `void __fastcall(CKsQueue *__hidden this, struct _IRP *, struct KSPIRP_FRAMING_ *, struct IKsTransport **)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000e800`

## callees

- `0x180001f00`
- `0x180002640`
- `0x1800031c8`
- `0x180003480`
- `0x1800035bc`
- `0x18000374c`
- `0x18000b7bc`
- `0x180019cb0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x180001f58`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x180001f58`
- `ntoskrnl!KeReleaseSpinLock` at `0x180001f9d`
- `ntoskrnl!KeReleaseSpinLock` at `0x180001fe0`
- `ntoskrnl!KeReleaseSpinLock` at `0x18000203d`
- `ntoskrnl!KeReleaseSpinLock` at `0x180002113`
- `ntoskrnl!KeReleaseSpinLock` at `0x180002140`
- `ntoskrnl!KeReleaseSpinLock` at `0x180001f9d`
- `ntoskrnl!KeReleaseSpinLock` at `0x180001fe0`
- `ntoskrnl!KeReleaseSpinLock` at `0x18000203d`
- `ntoskrnl!KeReleaseSpinLock` at `0x180002113`
- `ntoskrnl!KeReleaseSpinLock` at `0x180002140`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x18000208a`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x18000208a`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x18000204d`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x18000204d`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x180002098`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x180002098`
- `ntoskrnl!IofCompleteRequest` at `0x180002198`
- `ntoskrnl!IofCompleteRequest` at `0x180002198`

## pseudocode

```c
void __fastcall CKsQueue::ReleaseIrp(
        CKsQueue *this,
        struct _IRP *a2,
        struct KSPIRP_FRAMING_ *a3,
        struct IKsTransport **a4)
{
  struct _IRP *v6; // rbx
  KIRQL v8; // al
  int RefCount; // edx
  char v10; // bp
  unsigned __int64 *p_SpinLock; // rcx
  int v12; // edx
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rsi
  CKsQueue *v14; // rdi
  struct _LIST_ENTRY *i; // rcx
  IKsTransport *m_TransportSink; // rcx

  v6 = a2;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)a2,
      1,
      66,
      (__int64)WPP_13a31f976c1e3a0a846d2ee29290b270_Traceguids);
  }
  v8 = KeAcquireSpinLockRaiseToDpc(&this->m_FrameQueue.SpinLock);
  RefCount = a3->RefCount;
  a3->RefCount = RefCount - 1;
  if ( RefCount != 1 )
  {
    v10 = 0;
    p_SpinLock = &this->m_FrameQueue.SpinLock;
LABEL_6:
    if ( a4 )
    {
      v6->Tail.Overlay.CurrentStackLocation->Control |= 1u;
      KeReleaseSpinLock(&this->m_FrameQueue.SpinLock, v8);
LABEL_8:
      *a4 = 0;
      return;
    }
    goto LABEL_13;
  }
  v10 = 1;
  if ( a3->QueuedFrameHeaderCount )
  {
    _InterlockedExchange64((volatile __int64 *)&v6->CancelRoutine, (__int64)CKsQueue::CancelRoutine);
    if ( v6->Cancel && _InterlockedExchange64((volatile __int64 *)&v6->CancelRoutine, 0) )
    {
      KeReleaseSpinLock(&this->m_FrameQueue.SpinLock, v8);
      IoAcquireCancelSpinLock(&v6->CancelIrql);
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
      {
        LOBYTE(v12) = 5;
        WPP_RECORDER_SF_(
          WPP_GLOBAL_Control->DeviceExtension,
          v12,
          1,
          57,
          (__int64)WPP_13a31f976c1e3a0a846d2ee29290b270_Traceguids);
      }
      CurrentStackLocation = v6->Tail.Overlay.CurrentStackLocation;
      v14 = *(CKsQueue **)(CurrentStackLocation->Parameters.Read.ByteOffset.QuadPart + 24);
      KeAcquireSpinLockAtDpcLevel(&v14->m_FrameQueue.SpinLock);
      IoReleaseCancelSpinLock(2u);
      CKsQueue::CancelStreamPointers(v14, v6);
      CKsQueue::RemoveIrpFrameHeaders(v14, v6);
      v6->IoStatus.Status = -1073741536;
      if ( *(&CurrentStackLocation->Parameters.Read.Length + 1) )
      {
        KeReleaseSpinLock(&v14->m_FrameQueue.SpinLock, v6->CancelIrql);
      }
      else
      {
        v14->MdlCacheSetIrpMdlAddress(&v14->IKsMdlCache, (KSPIRP_FRAMING_ *)&CurrentStackLocation->Parameters, v6, 1u);
        for ( i = (struct _LIST_ENTRY *)CurrentStackLocation->Parameters.Read.ByteOffset.QuadPart;
              i;
              i = (struct _LIST_ENTRY *)CurrentStackLocation->Parameters.Read.ByteOffset.QuadPart )
        {
          CurrentStackLocation->Parameters.Read.ByteOffset.QuadPart = (LONGLONG)i[1].Flink;
          CKsQueue::PutAvailableFrameHeader(v14, i);
        }
        KeReleaseSpinLock(&v14->m_FrameQueue.SpinLock, v6->CancelIrql);
        m_TransportSink = v14->m_TransportSink;
        if ( m_TransportSink )
          KspDiscardKsIrp(m_TransportSink, v6);
        else
          IofCompleteRequest(v6, 0);
      }
      return;
    }
    v10 = 0;
  }
  p_SpinLock = &this->m_FrameQueue.SpinLock;
  if ( !v10 )
    goto LABEL_6;
LABEL_13:
  KeReleaseSpinLock(p_SpinLock, v8);
  if ( v10 )
  {
    CKsQueue::ForwardIrp(this, v6, a3, a4);
  }
  else if ( a4 )
  {
    goto LABEL_8;
  }
}

```

## disassembly

```asm
0x180001f00  mov     [rsp+arg_8], rbx
0x180001f05  mov     [rsp+arg_10], rsi
0x180001f0a  push    rdi
0x180001f0b  push    r12
0x180001f0d  push    r13
0x180001f0f  push    r14
0x180001f11  push    r15
0x180001f13  sub     rsp, 30h
0x180001f17  mov     rsi, r9
0x180001f1a  mov     r14, r8
0x180001f1d  mov     rbx, rdx
0x180001f20  mov     r15, rcx
0x180001f23  lea     r12, WPP_RECORDER_INITIALIZED
0x180001f2a  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x180001f31  lea     r13, WPP_13a31f976c1e3a0a846d2ee29290b270_Traceguids
0x180001f38  jz      short loc_180001F4C
0x180001f3a  mov     rcx, cs:WPP_GLOBAL_Control
0x180001f41  cmp     word ptr [rcx+48h], 0
0x180001f46  jnz     loc_180002151
0x180001f4c  lea     rcx, [r15+140h]; SpinLock
0x180001f53  mov     [rsp+58h+arg_0], rbp
0x180001f58  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x180001f5f  nop     dword ptr [rax+rax+00h]
0x180001f64  mov     edx, [r14+4]
0x180001f68  movzx   r8d, al
0x180001f6c  lea     ecx, [rdx-1]
0x180001f6f  mov     [r14+4], ecx
0x180001f73  cmp     edx, 1
0x180001f76  jz      short loc_180001FB2
0x180001f78  xor     bpl, bpl
0x180001f7b  lea     rcx, [r15+140h]
0x180001f82  test    rsi, rsi
0x180001f85  jz      short loc_180001FDC
0x180001f87  mov     rax, [rbx+0B8h]
0x180001f8e  lea     rcx, [r15+140h]; SpinLock
0x180001f95  movzx   edx, r8b; NewIrql
0x180001f99  or      byte ptr [rax+3], 1
0x180001f9d  call    cs:__imp_KeReleaseSpinLock
0x180001fa4  nop     dword ptr [rax+rax+00h]
0x180001fa9  mov     qword ptr [rsi], 0
0x180001fb0  jmp     short loc_180002002
0x180001fb2  cmp     dword ptr [r14+8], 0
0x180001fb7  mov     bpl, 1
0x180001fba  jz      short loc_180001FD0
0x180001fbc  lea     rax, ?CancelRoutine@CKsQueue@@CAXPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z; CKsQueue::CancelRoutine(_DEVICE_OBJECT *,_IRP *)
0x180001fc3  xchg    rax, [rbx+68h]
0x180001fc7  cmp     byte ptr [rbx+44h], 0
0x180001fcb  jnz     short loc_180002027
0x180001fcd  xor     bpl, bpl
0x180001fd0  lea     rcx, [r15+140h]; SpinLock
0x180001fd7  test    bpl, bpl
0x180001fda  jz      short loc_180001F82
0x180001fdc  movzx   edx, r8b; NewIrql
0x180001fe0  call    cs:__imp_KeReleaseSpinLock
0x180001fe7  nop     dword ptr [rax+rax+00h]
0x180001fec  test    bpl, bpl
0x180001fef  jz      short loc_180002020
0x180001ff1  mov     r9, rsi; struct IKsTransport **
0x180001ff4  mov     r8, r14; struct KSPIRP_FRAMING_ *
0x180001ff7  mov     rdx, rbx; struct _IRP *
0x180001ffa  mov     rcx, r15; this
0x180001ffd  call    ?ForwardIrp@CKsQueue@@AEAAXPEAU_IRP@@PEAUKSPIRP_FRAMING_@@PEAPEAUIKsTransport@@@Z; CKsQueue::ForwardIrp(_IRP *,KSPIRP_FRAMING_ *,IKsTransport * *)
0x180002002  mov     rbp, [rsp+58h+arg_0]
0x180002007  mov     rbx, [rsp+58h+arg_8]
0x18000200c  mov     rsi, [rsp+58h+arg_10]
0x180002011  add     rsp, 30h
0x180002015  pop     r15
0x180002017  pop     r14
0x180002019  pop     r13
0x18000201b  pop     r12
0x18000201d  pop     rdi
0x18000201e  retn
0x180002020  test    rsi, rsi
0x180002023  jnz     short loc_180001FA9
0x180002025  jmp     short loc_180002002
0x180002027  xor     eax, eax
0x180002029  xchg    rax, [rbx+68h]
0x18000202d  test    rax, rax
0x180002030  jz      short loc_180001FCD
0x180002032  movzx   edx, r8b; NewIrql
0x180002036  lea     rcx, [r15+140h]; SpinLock
0x18000203d  call    cs:__imp_KeReleaseSpinLock
0x180002044  nop     dword ptr [rax+rax+00h]
0x180002049  lea     rcx, [rbx+45h]; Irql
0x18000204d  call    cs:__imp_IoAcquireCancelSpinLock
0x180002054  nop     dword ptr [rax+rax+00h]
0x180002059  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x180002060  jz      short loc_180002074
0x180002062  mov     rcx, cs:WPP_GLOBAL_Control
0x180002069  cmp     word ptr [rcx+48h], 0
0x18000206e  jnz     loc_180002172
0x180002074  mov     rsi, [rbx+0B8h]
0x18000207b  mov     rax, [rsi+18h]
0x18000207f  mov     rdi, [rax+18h]
0x180002083  lea     rcx, [rdi+140h]; SpinLock
0x18000208a  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x180002091  nop     dword ptr [rax+rax+00h]
0x180002096  mov     cl, 2; Irql
0x180002098  call    cs:__imp_IoReleaseCancelSpinLock
0x18000209f  nop     dword ptr [rax+rax+00h]
0x1800020a4  mov     rdx, rbx; struct _IRP *
0x1800020a7  mov     rcx, rdi; this
0x1800020aa  call    ?CancelStreamPointers@CKsQueue@@AEAAXPEAU_IRP@@@Z; CKsQueue::CancelStreamPointers(_IRP *)
0x1800020af  mov     rdx, rbx; struct _IRP *
0x1800020b2  mov     rcx, rdi; this
0x1800020b5  call    ?RemoveIrpFrameHeaders@CKsQueue@@AEAAXPEAU_IRP@@@Z; CKsQueue::RemoveIrpFrameHeaders(_IRP *)
0x1800020ba  mov     dword ptr [rbx+30h], 0C0000120h
0x1800020c1  cmp     dword ptr [rsi+0Ch], 0
0x1800020c5  jnz     short loc_180002135
0x1800020c7  mov     rax, [rdi+8]
0x1800020cb  lea     rcx, [rdi+8]
0x1800020cf  movzx   r9d, bpl
0x1800020d3  lea     rdx, [rsi+8]
0x1800020d7  mov     r8, rbx
0x1800020da  mov     rax, [rax+38h]
0x1800020de  call    _guard_dispatch_icall
0x1800020e3  mov     rcx, [rsi+18h]
0x1800020e7  test    rcx, rcx
0x1800020ea  jz      short loc_180002108
0x1800020ec  mov     rax, [rcx+10h]
0x1800020f0  mov     rdx, rcx; ListEntry
0x1800020f3  mov     rcx, rdi; this
0x1800020f6  mov     [rsi+18h], rax
0x1800020fa  call    ?PutAvailableFrameHeader@CKsQueue@@AEAAXPEAU_KSPFRAME_HEADER@@@Z; CKsQueue::PutAvailableFrameHeader(_KSPFRAME_HEADER *)
0x1800020ff  mov     rcx, [rsi+18h]
0x180002103  test    rcx, rcx
0x180002106  jnz     short loc_1800020EC
0x180002108  movzx   edx, byte ptr [rbx+45h]; NewIrql
0x18000210c  lea     rcx, [rdi+140h]; SpinLock
0x180002113  call    cs:__imp_KeReleaseSpinLock
0x18000211a  nop     dword ptr [rax+rax+00h]
0x18000211f  mov     rcx, [rdi+50h]
0x180002123  test    rcx, rcx
0x180002126  jz      short loc_180002193
0x180002128  mov     rdx, rbx
0x18000212b  call    KspDiscardKsIrp
0x180002130  jmp     loc_180002002
0x180002135  movzx   edx, byte ptr [rbx+45h]; NewIrql
0x180002139  lea     rcx, [rdi+140h]; SpinLock
0x180002140  call    cs:__imp_KeReleaseSpinLock
0x180002147  nop     dword ptr [rax+rax+00h]
0x18000214c  jmp     loc_180002002
0x180002151  mov     rcx, [rcx+40h]
0x180002155  mov     r9d, 42h ; 'B'
0x18000215b  mov     r8d, 1
0x180002161  mov     [rsp+58h+var_38], r13
0x180002166  mov     dl, 5
0x180002168  call    WPP_RECORDER_SF_
0x18000216d  jmp     loc_180001F4C
0x180002172  mov     rcx, [rcx+40h]
0x180002176  mov     r9d, 39h ; '9'
0x18000217c  mov     r8d, 1
0x180002182  mov     [rsp+58h+var_38], r13
0x180002187  mov     dl, 5
0x180002189  call    WPP_RECORDER_SF_
0x18000218e  jmp     loc_180002074
0x180002193  xor     edx, edx; PriorityBoost
0x180002195  mov     rcx, rbx; Irp
0x180002198  call    cs:__imp_IofCompleteRequest
0x18000219f  nop     dword ptr [rax+rax+00h]
0x1800021a4  jmp     loc_180002002
```
