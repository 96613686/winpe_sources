# HbHvpWithdrawMemory

- ea: `0x14000ea28`
- end: `0x14000eaa7`
- name: `HbHvpWithdrawMemory`
- size: `127`
- prototype: `void __fastcall(PVOID Context)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000e6fc`

## callees

- `0x14000ea28`
- `0x14000eab0`

## import_xrefs

- `ntoskrnl!IoAcquireRemoveLockEx` at `0x14000ea4d`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x14000ea4d`
- `ntoskrnl!IoAllocateWorkItem` at `0x14000ea60`
- `ntoskrnl!IoAllocateWorkItem` at `0x14000ea60`
- `ntoskrnl!IoQueueWorkItemEx` at `0x14000ea84`
- `ntoskrnl!IoQueueWorkItemEx` at `0x14000ea84`

## pseudocode

```c
void __fastcall HbHvpWithdrawMemory(PVOID Context)
{
  struct _IO_WORKITEM *WorkItem; // rax

  if ( IoAcquireRemoveLockEx((PIO_REMOVE_LOCK)Context + 2, Context, File, 1u, 0x20u) >= 0 )
  {
    WorkItem = IoAllocateWorkItem(*(PDEVICE_OBJECT *)Context);
    if ( WorkItem )
      IoQueueWorkItemEx(WorkItem, HbHvpWithdrawMemoryWorker, DelayedWorkQueue, Context);
    else
      HbHvpWithdrawMemoryWorker(*(PVOID *)Context, Context, 0);
  }
}

```

## disassembly

```asm
0x14000ea28  push    rbx
0x14000ea2a  sub     rsp, 30h
0x14000ea2e  mov     rbx, rcx
0x14000ea31  mov     [rsp+38h+RemlockSize], 20h ; ' '; RemlockSize
0x14000ea39  mov     rdx, rbx; Tag
0x14000ea3c  lea     r8, File; File
0x14000ea43  add     rcx, 40h ; '@'; RemoveLock
0x14000ea47  mov     r9d, 1; Line
0x14000ea4d  call    cs:__imp_IoAcquireRemoveLockEx
0x14000ea54  nop     dword ptr [rax+rax+00h]
0x14000ea59  test    eax, eax
0x14000ea5b  js      short loc_14000EAA0
0x14000ea5d  mov     rcx, [rbx]; DeviceObject
0x14000ea60  call    cs:__imp_IoAllocateWorkItem
0x14000ea67  nop     dword ptr [rax+rax+00h]
0x14000ea6c  test    rax, rax
0x14000ea6f  jz      short loc_14000EA92
0x14000ea71  mov     r9, rbx; Context
0x14000ea74  lea     rdx, HbHvpWithdrawMemoryWorker; WorkerRoutine
0x14000ea7b  mov     r8d, 1; QueueType
0x14000ea81  mov     rcx, rax; IoWorkItem
0x14000ea84  call    cs:__imp_IoQueueWorkItemEx
0x14000ea8b  nop     dword ptr [rax+rax+00h]
0x14000ea90  jmp     short loc_14000EAA0
0x14000ea92  mov     rcx, [rbx]; IoObject
0x14000ea95  xor     r8d, r8d; IoWorkItem
0x14000ea98  mov     rdx, rbx; Context
0x14000ea9b  call    HbHvpWithdrawMemoryWorker
0x14000eaa0  add     rsp, 30h
0x14000eaa4  pop     rbx
0x14000eaa5  retn
```
