# CStorageComplete::HoldNotification(_IRP *)

- ea: `0x1400213f8`
- end: `0x14002147e`
- name: `?HoldNotification@CStorageComplete@@QEAAXPEAU_IRP@@@Z`
- size: `134`
- prototype: `void __fastcall(CStorageComplete *__hidden this, struct _IRP *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000a3b0`

## callees

- `0x14001268c`
- `0x1400213f8`

## import_xrefs

- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14002143e`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14002143e`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14002140d`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14002140d`
- `ntoskrnl!IoQueueWorkItem` at `0x140021466`
- `ntoskrnl!IoQueueWorkItem` at `0x140021466`

## pseudocode

```c
void __fastcall CStorageComplete::HoldNotification(struct _IO_WORKITEM **this, struct _IRP *a2)
{
  struct _IO_WORKITEM *v4; // rcx
  KIRQL Irql; // [rsp+30h] [rbp+8h] BYREF

  IoAcquireCancelSpinLock(&Irql);
  XList<_IRP,168>::insert(this, a2);
  _InterlockedExchange64((volatile __int64 *)&a2->CancelRoutine, (__int64)ACCancelNotification);
  a2->Tail.Overlay.CurrentStackLocation->Control |= 1u;
  IoReleaseCancelSpinLock(Irql);
  if ( !*((_BYTE *)this + 24) )
  {
    v4 = this[2];
    *((_BYTE *)this + 24) = 1;
    IoQueueWorkItem(v4, CStorageComplete::WorkerRoutine, DelayedWorkQueue, 0);
  }
}

```

## disassembly

```asm
0x1400213f8  mov     [rsp+arg_8], rbx
0x1400213fd  push    rdi
0x1400213fe  sub     rsp, 20h
0x140021402  mov     rdi, rcx
0x140021405  mov     rbx, rdx
0x140021408  lea     rcx, [rsp+28h+Irql]; Irql
0x14002140d  call    cs:__imp_IoAcquireCancelSpinLock
0x140021414  nop     dword ptr [rax+rax+00h]
0x140021419  mov     rdx, rbx
0x14002141c  mov     rcx, rdi
0x14002141f  call    ?insert@?$XList@U_IRP@@$0KI@@@QEAAXPEAU_IRP@@@Z; XList<_IRP,168>::insert(_IRP *)
0x140021424  lea     rax, ?ACCancelNotification@@YAXPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z; ACCancelNotification(_DEVICE_OBJECT *,_IRP *)
0x14002142b  xchg    rax, [rbx+68h]
0x14002142f  mov     rdx, [rbx+0B8h]
0x140021436  or      byte ptr [rdx+3], 1
0x14002143a  mov     cl, [rsp+28h+Irql]; Irql
0x14002143e  call    cs:__imp_IoReleaseCancelSpinLock
0x140021445  nop     dword ptr [rax+rax+00h]
0x14002144a  cmp     byte ptr [rdi+18h], 0
0x14002144e  jnz     short loc_140021472
0x140021450  mov     rcx, [rdi+10h]; IoWorkItem
0x140021454  lea     rdx, ?WorkerRoutine@CStorageComplete@@CAXPEAU_DEVICE_OBJECT@@PEAX@Z; WorkerRoutine
0x14002145b  xor     r9d, r9d; Context
0x14002145e  mov     byte ptr [rdi+18h], 1
0x140021462  lea     r8d, [r9+1]; QueueType
0x140021466  call    cs:__imp_IoQueueWorkItem
0x14002146d  nop     dword ptr [rax+rax+00h]
0x140021472  mov     rbx, [rsp+28h+arg_8]
0x140021477  add     rsp, 20h
0x14002147b  pop     rdi
0x14002147c  retn
```
