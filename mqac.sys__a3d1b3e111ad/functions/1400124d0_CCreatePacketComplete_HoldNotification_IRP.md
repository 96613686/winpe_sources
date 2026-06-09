# CCreatePacketComplete::HoldNotification(_IRP *)

- ea: `0x1400124d0`
- end: `0x140012556`
- name: `?HoldNotification@CCreatePacketComplete@@AEAAXPEAU_IRP@@@Z`
- size: `134`
- prototype: `void __fastcall(CCreatePacketComplete *__hidden this, struct _IRP *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140012368`

## callees

- `0x1400124d0`
- `0x14001268c`

## import_xrefs

- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140012516`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140012516`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x1400124e5`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x1400124e5`
- `ntoskrnl!IoQueueWorkItem` at `0x14001253e`
- `ntoskrnl!IoQueueWorkItem` at `0x14001253e`

## pseudocode

```c
void __fastcall CCreatePacketComplete::HoldNotification(struct _IO_WORKITEM **this, struct _IRP *a2)
{
  struct _IO_WORKITEM *v4; // rcx
  KIRQL Irql; // [rsp+30h] [rbp+8h] BYREF

  IoAcquireCancelSpinLock(&Irql);
  XList<_IRP,168>::insert(this, a2);
  _InterlockedExchange64((volatile __int64 *)&a2->CancelRoutine, (__int64)ACCancelCreatePacketNotification);
  a2->Tail.Overlay.CurrentStackLocation->Control |= 1u;
  IoReleaseCancelSpinLock(Irql);
  if ( !*((_BYTE *)this + 24) )
  {
    v4 = this[2];
    *((_BYTE *)this + 24) = 1;
    IoQueueWorkItem(v4, CCreatePacketComplete::WorkerRoutine, DelayedWorkQueue, 0);
  }
}

```

## disassembly

```asm
0x1400124d0  mov     [rsp+arg_8], rbx
0x1400124d5  push    rdi
0x1400124d6  sub     rsp, 20h
0x1400124da  mov     rdi, rcx
0x1400124dd  mov     rbx, rdx
0x1400124e0  lea     rcx, [rsp+28h+Irql]; Irql
0x1400124e5  call    cs:__imp_IoAcquireCancelSpinLock
0x1400124ec  nop     dword ptr [rax+rax+00h]
0x1400124f1  mov     rdx, rbx
0x1400124f4  mov     rcx, rdi
0x1400124f7  call    ?insert@?$XList@U_IRP@@$0KI@@@QEAAXPEAU_IRP@@@Z; XList<_IRP,168>::insert(_IRP *)
0x1400124fc  lea     rax, ?ACCancelCreatePacketNotification@@YAXPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z; ACCancelCreatePacketNotification(_DEVICE_OBJECT *,_IRP *)
0x140012503  xchg    rax, [rbx+68h]
0x140012507  mov     rdx, [rbx+0B8h]
0x14001250e  or      byte ptr [rdx+3], 1
0x140012512  mov     cl, [rsp+28h+Irql]; Irql
0x140012516  call    cs:__imp_IoReleaseCancelSpinLock
0x14001251d  nop     dword ptr [rax+rax+00h]
0x140012522  cmp     byte ptr [rdi+18h], 0
0x140012526  jnz     short loc_14001254A
0x140012528  mov     rcx, [rdi+10h]; IoWorkItem
0x14001252c  lea     rdx, ?WorkerRoutine@CCreatePacketComplete@@CAXPEAU_DEVICE_OBJECT@@PEAX@Z; WorkerRoutine
0x140012533  xor     r9d, r9d; Context
0x140012536  mov     byte ptr [rdi+18h], 1
0x14001253a  lea     r8d, [r9+1]; QueueType
0x14001253e  call    cs:__imp_IoQueueWorkItem
0x140012545  nop     dword ptr [rax+rax+00h]
0x14001254a  mov     rbx, [rsp+28h+arg_8]
0x14001254f  add     rsp, 20h
0x140012553  pop     rdi
0x140012554  retn
```
