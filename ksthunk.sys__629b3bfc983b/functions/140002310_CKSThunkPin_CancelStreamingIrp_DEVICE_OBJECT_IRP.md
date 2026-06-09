# CKSThunkPin::CancelStreamingIrp(_DEVICE_OBJECT *,_IRP *)

- ea: `0x140002310`
- end: `0x140002378`
- name: `?CancelStreamingIrp@CKSThunkPin@@CAXPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z`
- size: `104`
- prototype: `static void(struct _DEVICE_OBJECT *, struct _IRP *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140002310`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140002360`
- `ntoskrnl!IofCompleteRequest` at `0x140002360`
- `ntoskrnl!IoCancelIrp` at `0x140002333`
- `ntoskrnl!IoCancelIrp` at `0x140002333`
- `ntoskrnl!IoFreeIrp` at `0x14000234f`
- `ntoskrnl!IoFreeIrp` at `0x14000234f`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140002324`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140002324`

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
0x140002310  mov     [rsp+arg_0], rbx
0x140002315  push    rdi
0x140002316  sub     rsp, 20h
0x14000231a  mov     cl, [rdx+45h]; Irql
0x14000231d  mov     rbx, rdx
0x140002320  mov     rdi, [rdx+78h]
0x140002324  call    cs:__imp_IoReleaseCancelSpinLock
0x14000232b  nop     dword ptr [rax+rax+00h]
0x140002330  mov     rcx, rdi; Irp
0x140002333  call    cs:__imp_IoCancelIrp
0x14000233a  nop     dword ptr [rax+rax+00h]
0x14000233f  xor     eax, eax
0x140002341  lock cmpxchg [rbx+88h], rbx
0x14000234a  jz      short loc_14000236C
0x14000234c  mov     rcx, rdi; Irp
0x14000234f  call    cs:__imp_IoFreeIrp
0x140002356  nop     dword ptr [rax+rax+00h]
0x14000235b  xor     edx, edx; PriorityBoost
0x14000235d  mov     rcx, rbx; Irp
0x140002360  call    cs:__imp_IofCompleteRequest
0x140002367  nop     dword ptr [rax+rax+00h]
0x14000236c  mov     rbx, [rsp+28h+arg_0]
0x140002371  add     rsp, 20h
0x140002375  pop     rdi
0x140002376  retn
```
