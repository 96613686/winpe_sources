# DispatchIncomingCallConnectedCancelIrp

- ea: `0x140010900`
- end: `0x140010980`
- name: `DispatchIncomingCallConnectedCancelIrp`
- size: `128`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140002030`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140010929`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140010929`
- `ntoskrnl!IofCompleteRequest` at `0x140010963`
- `ntoskrnl!IofCompleteRequest` at `0x140010963`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140010915`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140010915`
- `ntoskrnl!KeReleaseSpinLock` at `0x140010943`
- `ntoskrnl!KeReleaseSpinLock` at `0x140010943`

## pseudocode

```c
void __fastcall DispatchIncomingCallConnectedCancelIrp(__int64 a1, IRP *a2)
{
  struct _LIST_ENTRY *Flink; // rdi
  KIRQL v4; // al

  IoReleaseCancelSpinLock(a2->CancelIrql);
  Flink = a2->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink;
  v4 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)&Flink[2]);
  Flink[4].Flink = 0;
  KeReleaseSpinLock((PKSPIN_LOCK)&Flink[2], v4);
  DereferenceRefCount(Flink);
  a2->IoStatus.Status = -1073741536;
  IofCompleteRequest(a2, 2);
}

```

## disassembly

```asm
0x140010900  mov     [rsp+arg_0], rbx
0x140010905  mov     [rsp+arg_8], rsi
0x14001090a  push    rdi
0x14001090b  sub     rsp, 20h
0x14001090f  mov     cl, [rdx+45h]; Irql
0x140010912  mov     rsi, rdx
0x140010915  call    cs:__imp_IoReleaseCancelSpinLock
0x14001091c  nop     dword ptr [rax+rax+00h]
0x140010921  mov     rdi, [rsi+78h]
0x140010925  lea     rcx, [rdi+20h]; SpinLock
0x140010929  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140010930  nop     dword ptr [rax+rax+00h]
0x140010935  lea     rcx, [rdi+20h]; SpinLock
0x140010939  mov     qword ptr [rdi+40h], 0
0x140010941  mov     dl, al; NewIrql
0x140010943  call    cs:__imp_KeReleaseSpinLock
0x14001094a  nop     dword ptr [rax+rax+00h]
0x14001094f  mov     rcx, rdi
0x140010952  call    DereferenceRefCount
0x140010957  mov     dl, 2; PriorityBoost
0x140010959  mov     dword ptr [rsi+30h], 0C0000120h
0x140010960  mov     rcx, rsi; Irp
0x140010963  call    cs:__imp_IofCompleteRequest
0x14001096a  nop     dword ptr [rax+rax+00h]
0x14001096f  mov     rbx, [rsp+28h+arg_0]
0x140010974  mov     rsi, [rsp+28h+arg_8]
0x140010979  add     rsp, 20h
0x14001097d  pop     rdi
0x14001097e  retn
```
