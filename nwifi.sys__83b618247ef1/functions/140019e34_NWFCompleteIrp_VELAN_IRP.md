# NWFCompleteIrp(_VELAN *,_IRP *)

- ea: `0x140019e34`
- end: `0x140019f08`
- name: `?NWFCompleteIrp@@YAXPEAU_VELAN@@PEAU_IRP@@@Z`
- size: `212`
- prototype: `void(struct _VELAN *, struct _IRP *)`
- caller_count: `8`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400140d0`
- `0x1400337f4`
- `0x140035de0`
- `0x14003e8f0`
- `0x14003e970`
- `0x14005e1f0`
- `0x14005e694`
- `0x1400600a0`

## callees

- `0x140019e34`

## import_xrefs

- `ntoskrnl!ExQueueWorkItem` at `0x140019ed6`
- `ntoskrnl!ExQueueWorkItem` at `0x140019ed6`
- `ntoskrnl!KeReleaseSpinLock` at `0x140019eeb`
- `ntoskrnl!KeReleaseSpinLock` at `0x140019eeb`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140019e53`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140019e53`
- `ntoskrnl!IofCompleteRequest` at `0x140019e7b`
- `ntoskrnl!IofCompleteRequest` at `0x140019e7b`

## pseudocode

```c
void __fastcall NWFCompleteIrp(struct _VELAN *a1, struct _IRP *a2)
{
  _NDIS_SPIN_LOCK *p_CsqLock; // rsi
  CCHAR v5; // dl

  p_CsqLock = &a1->IoctlModule.CsqLock;
  a1->IoctlModule.CsqLock.OldIrql = KeAcquireSpinLockRaiseToDpc(&a1->IoctlModule.CsqLock.SpinLock);
  if ( (a2->Tail.Overlay.CurrentStackLocation->Control & 1) != 0 )
    v5 = 2;
  else
    v5 = 0;
  IofCompleteRequest(a2, v5);
  a1->IoctlModule.pCurrentIrp = 0;
  if ( !a1->IoctlModule.uIrpProcessingBlockCount
    && a1->IoctlModule.IrpQueue.Flink != &a1->IoctlModule.IrpQueue
    && !a1->IoctlModule.bWorkItemQueued )
  {
    a1->IoctlModule.bWorkItemQueued = 1;
    a1->IoctlModule.WorkItem.Parameter = a1;
    a1->IoctlModule.WorkItem.WorkerRoutine = (void (__fastcall *)(void *))IoctlDelayedProcessIrp;
    a1->IoctlModule.WorkItem.List.Flink = 0;
    ExQueueWorkItem(&a1->IoctlModule.WorkItem, DelayedWorkQueue);
  }
  KeReleaseSpinLock(&p_CsqLock->SpinLock, a1->IoctlModule.CsqLock.OldIrql);
}

```

## disassembly

```asm
0x140019e34  mov     [rsp+arg_0], rbx
0x140019e39  mov     [rsp+arg_8], rsi
0x140019e3e  push    rdi
0x140019e3f  sub     rsp, 20h
0x140019e43  lea     rsi, [rcx+1580h]
0x140019e4a  mov     rbx, rcx
0x140019e4d  mov     rcx, rsi; SpinLock
0x140019e50  mov     rdi, rdx
0x140019e53  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140019e5a  nop     dword ptr [rax+rax+00h]
0x140019e5f  mov     [rbx+1588h], al
0x140019e65  mov     rcx, rdi; Irp
0x140019e68  mov     rax, [rdi+0B8h]
0x140019e6f  test    byte ptr [rax+3], 1
0x140019e73  jz      short loc_140019E79
0x140019e75  mov     dl, 2
0x140019e77  jmp     short loc_140019E7B
0x140019e79  xor     edx, edx; PriorityBoost
0x140019e7b  call    cs:__imp_IofCompleteRequest
0x140019e82  nop     dword ptr [rax+rax+00h]
0x140019e87  xor     r8d, r8d
0x140019e8a  mov     [rbx+15E0h], r8
0x140019e91  cmp     [rbx+15A0h], r8d
0x140019e98  jnz     short loc_140019EE2
0x140019e9a  lea     rax, [rbx+1590h]
0x140019ea1  cmp     [rax], rax
0x140019ea4  jz      short loc_140019EE2
0x140019ea6  cmp     [rbx+15BCh], r8d
0x140019ead  jnz     short loc_140019EE2
0x140019eaf  lea     rcx, [rbx+15C0h]; WorkItem
0x140019eb6  mov     dword ptr [rbx+15BCh], 1
0x140019ec0  lea     rax, IoctlDelayedProcessIrp
0x140019ec7  mov     [rcx+18h], rbx
0x140019ecb  lea     edx, [r8+1]; QueueType
0x140019ecf  mov     [rcx+10h], rax
0x140019ed3  mov     [rcx], r8
0x140019ed6  call    cs:__imp_ExQueueWorkItem
0x140019edd  nop     dword ptr [rax+rax+00h]
0x140019ee2  mov     dl, [rbx+1588h]; NewIrql
0x140019ee8  mov     rcx, rsi; SpinLock
0x140019eeb  call    cs:__imp_KeReleaseSpinLock
0x140019ef2  nop     dword ptr [rax+rax+00h]
0x140019ef7  mov     rbx, [rsp+28h+arg_0]
0x140019efc  mov     rsi, [rsp+28h+arg_8]
0x140019f01  add     rsp, 20h
0x140019f05  pop     rdi
0x140019f06  retn
```
