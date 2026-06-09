# PcpCreateHoldHandle

- ea: `0x14000f6d4`
- end: `0x14000f86d`
- name: `PcpCreateHoldHandle`
- size: `409`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14000b0e0`
- `0x14001dc60`

## callees

- `0x14000f6d4`

## import_xrefs

- `ntoskrnl!IoFreeWorkItem` at `0x14000f849`
- `ntoskrnl!IoFreeWorkItem` at `0x14000f849`
- `ntoskrnl!IoQueueWorkItemEx` at `0x14000f838`
- `ntoskrnl!IoQueueWorkItemEx` at `0x14000f838`
- `ntoskrnl!ZwCreateFile` at `0x14000f7c0`
- `ntoskrnl!ZwCreateFile` at `0x14000f7c0`
- `ntoskrnl!IoAllocateWorkItem` at `0x14000f71a`
- `ntoskrnl!IoAllocateWorkItem` at `0x14000f71a`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000f743`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000f743`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000f813`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000f813`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000f7dd`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000f7dd`

## pseudocode

```c
__int64 PcpCreateHoldHandle()
{
  struct _IO_WORKITEM *WorkItem; // rdi
  NTSTATUS v1; // ebx
  struct _UNICODE_STRING DestinationString; // [rsp+60h] [rbp-19h] BYREF
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+70h] [rbp-9h] BYREF
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+80h] [rbp+7h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+98h] [rbp+1Fh] BYREF
  void *FileHandle; // [rsp+E0h] [rbp+67h] BYREF

  FileHandle = 0;
  memset(&LockHandle, 0, sizeof(LockHandle));
  memset(&ObjectAttributes, 0, 44);
  DestinationString = 0;
  IoStatusBlock = 0;
  WorkItem = IoAllocateWorkItem((PDEVICE_OBJECT)WPP_MAIN_CB.Queue.ListEntry.Blink);
  if ( WorkItem )
  {
    RtlInitUnicodeString(&DestinationString, L"\\Device\\Psched");
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 576;
    ObjectAttributes.ObjectName = &DestinationString;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v1 = ZwCreateFile(&FileHandle, 0x80000000, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 7u, 1u, 0x40u, 0, 0);
    if ( v1 < 0 )
      goto LABEL_9;
    KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)&WPP_MAIN_CB.Dpc.DeferredContext, &LockHandle);
    if ( HIDWORD(WPP_MAIN_CB.Dpc.DpcData) && !*(_QWORD *)&WPP_MAIN_CB.ActiveThreadCount )
    {
      *(_QWORD *)&WPP_MAIN_CB.ActiveThreadCount = FileHandle;
      FileHandle = 0;
    }
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    if ( FileHandle )
      IoQueueWorkItemEx(WorkItem, PcpCloseHoldHandleWorkerRoutine, DelayedWorkQueue, FileHandle);
    else
LABEL_9:
      IoFreeWorkItem(WorkItem);
  }
  else
  {
    return (unsigned int)-1073741670;
  }
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x14000f6d4  mov     [rsp-8+arg_8], rbx
0x14000f6d9  mov     [rsp-8+arg_10], rdi
0x14000f6de  push    rbp
0x14000f6df  lea     rbp, [rsp-57h]
0x14000f6e4  sub     rsp, 0D0h
0x14000f6eb  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8; DeviceObject
0x14000f6f2  xorps   xmm0, xmm0
0x14000f6f5  xor     eax, eax
0x14000f6f7  xorps   xmm1, xmm1
0x14000f6fa  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x14000f6fe  mov     qword ptr [rbp+57h+LockHandle.OldIrql], rax
0x14000f702  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x14000f706  mov     [rbp+57h+FileHandle], rax
0x14000f70a  movups  xmmword ptr [rbp+57h+LockHandle.LockQueue.Next], xmm0
0x14000f70e  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x14000f712  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x14000f716  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm1
0x14000f71a  call    cs:__imp_IoAllocateWorkItem
0x14000f721  nop     dword ptr [rax+rax+00h]
0x14000f726  mov     rdi, rax
0x14000f729  test    rax, rax
0x14000f72c  jnz     short loc_14000F738
0x14000f72e  mov     ebx, 0C000009Ah
0x14000f733  jmp     loc_14000F855
0x14000f738  lea     rdx, aDevicePsched; "\\Device\\Psched"
0x14000f73f  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14000f743  call    cs:__imp_RtlInitUnicodeString
0x14000f74a  nop     dword ptr [rax+rax+00h]
0x14000f74f  mov     [rsp+0D0h+EaLength], 0; EaLength
0x14000f757  lea     rax, [rbp+57h+DestinationString]
0x14000f75b  mov     [rsp+0D0h+EaBuffer], 0; EaBuffer
0x14000f764  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x14000f768  mov     [rsp+0D0h+CreateOptions], 40h ; '@'; CreateOptions
0x14000f770  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14000f774  mov     [rsp+0D0h+CreateDisposition], 1; CreateDisposition
0x14000f77c  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x14000f780  mov     [rsp+0D0h+ShareAccess], 7; ShareAccess
0x14000f788  xorps   xmm0, xmm0
0x14000f78b  mov     [rsp+0D0h+FileAttributes], 80h; FileAttributes
0x14000f793  mov     edx, 80000000h; DesiredAccess
0x14000f798  mov     [rsp+0D0h+AllocationSize], 0; AllocationSize
0x14000f7a1  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x14000f7a8  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x14000f7b0  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x14000f7b7  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x14000f7bb  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14000f7c0  call    cs:__imp_ZwCreateFile
0x14000f7c7  nop     dword ptr [rax+rax+00h]
0x14000f7cc  mov     ebx, eax
0x14000f7ce  test    eax, eax
0x14000f7d0  js      short loc_14000F846
0x14000f7d2  lea     rdx, [rbp+57h+LockHandle]; LockHandle
0x14000f7d6  lea     rcx, WPP_MAIN_CB.Dpc.DeferredContext; SpinLock
0x14000f7dd  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14000f7e4  nop     dword ptr [rax+rax+00h]
0x14000f7e9  cmp     dword ptr cs:WPP_MAIN_CB.Dpc.DpcData+4, 0
0x14000f7f0  jz      short loc_14000F80F
0x14000f7f2  cmp     qword ptr cs:WPP_MAIN_CB.ActiveThreadCount, 0
0x14000f7fa  jnz     short loc_14000F80F
0x14000f7fc  mov     rcx, [rbp+57h+FileHandle]
0x14000f800  mov     qword ptr cs:WPP_MAIN_CB.ActiveThreadCount, rcx
0x14000f807  mov     [rbp+57h+FileHandle], 0
0x14000f80f  lea     rcx, [rbp+57h+LockHandle]; LockHandle
0x14000f813  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14000f81a  nop     dword ptr [rax+rax+00h]
0x14000f81f  mov     r9, [rbp+57h+FileHandle]; Context
0x14000f823  test    r9, r9
0x14000f826  jz      short loc_14000F846
0x14000f828  mov     r8d, 1; QueueType
0x14000f82e  lea     rdx, PcpCloseHoldHandleWorkerRoutine; WorkerRoutine
0x14000f835  mov     rcx, rdi; IoWorkItem
0x14000f838  call    cs:__imp_IoQueueWorkItemEx
0x14000f83f  nop     dword ptr [rax+rax+00h]
0x14000f844  jmp     short loc_14000F855
0x14000f846  mov     rcx, rdi; IoWorkItem
0x14000f849  call    cs:__imp_IoFreeWorkItem
0x14000f850  nop     dword ptr [rax+rax+00h]
0x14000f855  lea     r11, [rsp+0D0h+var_s0]
0x14000f85d  mov     eax, ebx
0x14000f85f  mov     rbx, [r11+18h]
0x14000f863  mov     rdi, [r11+20h]
0x14000f867  mov     rsp, r11
0x14000f86a  pop     rbp
0x14000f86b  retn
```
