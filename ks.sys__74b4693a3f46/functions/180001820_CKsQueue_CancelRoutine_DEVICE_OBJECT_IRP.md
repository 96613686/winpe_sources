# CKsQueue::CancelRoutine(_DEVICE_OBJECT *,_IRP *)

- ea: `0x180001820`
- end: `0x18000195a`
- name: `?CancelRoutine@CKsQueue@@CAXPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z`
- size: `314`
- prototype: `static void(struct _DEVICE_OBJECT *, struct _IRP *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001120`

## callees

- `0x180001820`
- `0x1800031c8`
- `0x180003480`
- `0x1800035bc`
- `0x18000374c`
- `0x18000b7bc`
- `0x180019c60`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x1800018d2`
- `ntoskrnl!KeReleaseSpinLock` at `0x180001913`
- `ntoskrnl!KeReleaseSpinLock` at `0x1800018d2`
- `ntoskrnl!KeReleaseSpinLock` at `0x180001913`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x18000186c`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x18000186c`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x18000187a`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x18000187a`
- `ntoskrnl!IofCompleteRequest` at `0x18000194c`
- `ntoskrnl!IofCompleteRequest` at `0x18000194c`

## pseudocode

```c
void __fastcall CKsQueue::CancelRoutine(struct _DEVICE_OBJECT *a1, struct _IRP *a2)
{
  struct _IRP *v2; // rbx
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rsi
  CKsQueue *v4; // rdi
  __int64 v5; // r9
  struct _LIST_ENTRY *QuadPart; // rdx
  IKsTransport *m_TransportSink; // rcx

  v2 = a2;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)a2,
      1,
      57,
      (__int64)WPP_c705d9135b58358f87ecf40b472c5dce_Traceguids);
  }
  CurrentStackLocation = v2->Tail.Overlay.CurrentStackLocation;
  v4 = *(CKsQueue **)(CurrentStackLocation->Parameters.Read.ByteOffset.QuadPart + 24);
  KeAcquireSpinLockAtDpcLevel(&v4->m_FrameQueue.SpinLock);
  IoReleaseCancelSpinLock(2u);
  CKsQueue::CancelStreamPointers(v4, v2);
  CKsQueue::RemoveIrpFrameHeaders(v4, v2);
  v2->IoStatus.Status = -1073741536;
  if ( *(&CurrentStackLocation->Parameters.Read.Length + 1) )
  {
    KeReleaseSpinLock(&v4->m_FrameQueue.SpinLock, v2->CancelIrql);
  }
  else
  {
    LOBYTE(v5) = 1;
    v4->MdlCacheSetIrpMdlAddress(&v4->IKsMdlCache, (KSPIRP_FRAMING_ *)&CurrentStackLocation->Parameters, v2, v5);
    while ( 1 )
    {
      QuadPart = (struct _LIST_ENTRY *)CurrentStackLocation->Parameters.Read.ByteOffset.QuadPart;
      if ( !QuadPart )
        break;
      CurrentStackLocation->Parameters.Read.ByteOffset.QuadPart = (LONGLONG)QuadPart[1].Flink;
      CKsQueue::PutAvailableFrameHeader(v4, QuadPart);
    }
    KeReleaseSpinLock(&v4->m_FrameQueue.SpinLock, v2->CancelIrql);
    m_TransportSink = v4->m_TransportSink;
    if ( m_TransportSink )
      KspDiscardKsIrp(m_TransportSink, v2);
    else
      IofCompleteRequest(v2, 0);
  }
}

```

## disassembly

```asm
0x180001820  push    rbx
0x180001822  push    rbp
0x180001823  push    rsi
0x180001824  push    rdi
0x180001825  push    r14
0x180001827  sub     rsp, 30h
0x18000182b  mov     rbx, rdx
0x18000182e  lea     rax, WPP_RECORDER_INITIALIZED
0x180001835  xor     r14d, r14d
0x180001838  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18000183f  jz      short loc_180001853
0x180001841  mov     rcx, cs:WPP_GLOBAL_Control
0x180001848  cmp     [rcx+48h], r14w
0x18000184d  jnz     loc_180001921
0x180001853  mov     rsi, [rbx+0B8h]
0x18000185a  mov     rax, [rsi+18h]
0x18000185e  mov     rdi, [rax+18h]
0x180001862  lea     rbp, [rdi+140h]
0x180001869  mov     rcx, rbp; SpinLock
0x18000186c  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x180001873  nop     dword ptr [rax+rax+00h]
0x180001878  mov     cl, 2; Irql
0x18000187a  call    cs:__imp_IoReleaseCancelSpinLock
0x180001881  nop     dword ptr [rax+rax+00h]
0x180001886  mov     rdx, rbx; struct _IRP *
0x180001889  mov     rcx, rdi; this
0x18000188c  call    ?CancelStreamPointers@CKsQueue@@AEAAXPEAU_IRP@@@Z; CKsQueue::CancelStreamPointers(_IRP *)
0x180001891  mov     rdx, rbx; struct _IRP *
0x180001894  mov     rcx, rdi; this
0x180001897  call    ?RemoveIrpFrameHeaders@CKsQueue@@AEAAXPEAU_IRP@@@Z; CKsQueue::RemoveIrpFrameHeaders(_IRP *)
0x18000189c  mov     dword ptr [rbx+30h], 0C0000120h
0x1800018a3  cmp     [rsi+0Ch], r14d
0x1800018a7  jnz     short loc_18000190D
0x1800018a9  lea     rcx, [rdi+8]
0x1800018ad  mov     r9b, 1
0x1800018b0  mov     rax, [rcx]
0x1800018b3  lea     rdx, [rsi+8]
0x1800018b7  mov     r8, rbx
0x1800018ba  mov     rax, [rax+38h]
0x1800018be  call    _guard_dispatch_icall
0x1800018c3  mov     rdx, [rsi+18h]; ListEntry
0x1800018c7  test    rdx, rdx
0x1800018ca  jnz     short loc_1800018FB
0x1800018cc  mov     dl, [rbx+45h]; NewIrql
0x1800018cf  mov     rcx, rbp; SpinLock
0x1800018d2  call    cs:__imp_KeReleaseSpinLock
0x1800018d9  nop     dword ptr [rax+rax+00h]
0x1800018de  mov     rcx, [rdi+50h]
0x1800018e2  test    rcx, rcx
0x1800018e5  jz      short loc_180001947
0x1800018e7  mov     rdx, rbx
0x1800018ea  call    KspDiscardKsIrp
0x1800018ef  add     rsp, 30h
0x1800018f3  pop     r14
0x1800018f5  pop     rdi
0x1800018f6  pop     rsi
0x1800018f7  pop     rbp
0x1800018f8  pop     rbx
0x1800018f9  retn
0x1800018fb  mov     rax, [rdx+10h]
0x1800018ff  mov     rcx, rdi; this
0x180001902  mov     [rsi+18h], rax
0x180001906  call    ?PutAvailableFrameHeader@CKsQueue@@AEAAXPEAU_KSPFRAME_HEADER@@@Z; CKsQueue::PutAvailableFrameHeader(_KSPFRAME_HEADER *)
0x18000190b  jmp     short loc_1800018C3
0x18000190d  mov     dl, [rbx+45h]; NewIrql
0x180001910  mov     rcx, rbp; SpinLock
0x180001913  call    cs:__imp_KeReleaseSpinLock
0x18000191a  nop     dword ptr [rax+rax+00h]
0x18000191f  jmp     short loc_1800018EF
0x180001921  mov     rcx, [rcx+40h]
0x180001925  lea     rax, WPP_c705d9135b58358f87ecf40b472c5dce_Traceguids
0x18000192c  mov     r9d, 39h ; '9'
0x180001932  mov     [rsp+58h+var_38], rax
0x180001937  mov     dl, 5
0x180001939  lea     r8d, [r9-38h]
0x18000193d  call    WPP_RECORDER_SF_
0x180001942  jmp     loc_180001853
0x180001947  xor     edx, edx; PriorityBoost
0x180001949  mov     rcx, rbx; Irp
0x18000194c  call    cs:__imp_IofCompleteRequest
0x180001953  nop     dword ptr [rax+rax+00h]
0x180001958  jmp     short loc_1800018EF
```
