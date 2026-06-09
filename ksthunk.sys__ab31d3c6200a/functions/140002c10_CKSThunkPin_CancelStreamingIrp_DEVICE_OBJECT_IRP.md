# CKSThunkPin::CancelStreamingIrp(_DEVICE_OBJECT *,_IRP *)

- ea: `0x140002c10`
- end: `0x140002c78`
- name: `?CancelStreamingIrp@CKSThunkPin@@CAXPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z`
- size: `104`
- prototype: `void __fastcall(struct _DEVICE_OBJECT *, struct _IRP *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140002c10`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140002c60`
- `ntoskrnl!IofCompleteRequest` at `0x140002c60`
- `ntoskrnl!IoCancelIrp` at `0x140002c33`
- `ntoskrnl!IoCancelIrp` at `0x140002c33`
- `ntoskrnl!IoFreeIrp` at `0x140002c4f`
- `ntoskrnl!IoFreeIrp` at `0x140002c4f`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140002c24`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140002c24`

## pseudocode

```c
void __fastcall CKSThunkPin::CancelStreamingIrp(struct _DEVICE_OBJECT *a1, struct _IRP *a2)
{
  struct _LIST_ENTRY *Flink; // rdi

  Flink = a2->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink;
  IoReleaseCancelSpinLock(a2->CancelIrql);
  IoCancelIrp((PIRP)Flink);
  if ( _InterlockedCompareExchange64(
         (volatile signed __int64 *)&a2->Tail.Overlay.DriverContext[2],
         (signed __int64)a2,
         0) )
  {
    IoFreeIrp((PIRP)Flink);
    IofCompleteRequest(a2, 0);
  }
}

```

## disassembly

```asm
0x140002c10  mov     [rsp+arg_0], rbx
0x140002c15  push    rdi
0x140002c16  sub     rsp, 20h
0x140002c1a  mov     cl, [rdx+45h]; Irql
0x140002c1d  mov     rbx, rdx
0x140002c20  mov     rdi, [rdx+78h]
0x140002c24  call    cs:__imp_IoReleaseCancelSpinLock
0x140002c2b  nop     dword ptr [rax+rax+00h]
0x140002c30  mov     rcx, rdi; Irp
0x140002c33  call    cs:__imp_IoCancelIrp
0x140002c3a  nop     dword ptr [rax+rax+00h]
0x140002c3f  xor     eax, eax
0x140002c41  lock cmpxchg [rbx+88h], rbx
0x140002c4a  jz      short loc_140002C6C
0x140002c4c  mov     rcx, rdi; Irp
0x140002c4f  call    cs:__imp_IoFreeIrp
0x140002c56  nop     dword ptr [rax+rax+00h]
0x140002c5b  xor     edx, edx; PriorityBoost
0x140002c5d  mov     rcx, rbx; Irp
0x140002c60  call    cs:__imp_IofCompleteRequest
0x140002c67  nop     dword ptr [rax+rax+00h]
0x140002c6c  mov     rbx, [rsp+28h+arg_0]
0x140002c71  add     rsp, 20h
0x140002c75  pop     rdi
0x140002c76  retn
```
