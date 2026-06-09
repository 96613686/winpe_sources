# MRxDAVContextTimerThread

- ea: `0x140004950`
- end: `0x140004af1`
- name: `MRxDAVContextTimerThread`
- size: `417`
- prototype: `void __fastcall(PVOID StartContext)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x140001188`
- `0x140004950`
- `0x140005554`

## import_xrefs

- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14000496c`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400049e2`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140004a21`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140004a84`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14000496c`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400049e2`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140004a21`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140004a84`
- `ntoskrnl!KeSetTimerEx` at `0x1400049ad`
- `ntoskrnl!KeSetTimerEx` at `0x1400049ad`
- `ntoskrnl!ExReleaseResourceLite` at `0x140004991`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400049fe`
- `ntoskrnl!ExReleaseResourceLite` at `0x140004a73`
- `ntoskrnl!ExReleaseResourceLite` at `0x140004aa0`
- `ntoskrnl!ExReleaseResourceLite` at `0x140004991`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400049fe`
- `ntoskrnl!ExReleaseResourceLite` at `0x140004a73`
- `ntoskrnl!ExReleaseResourceLite` at `0x140004aa0`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400049d1`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400049d1`
- `ntoskrnl!KeSetEvent` at `0x140004ab8`
- `ntoskrnl!KeSetEvent` at `0x140004ab8`
- `ntoskrnl!ZwClose` at `0x140004acb`
- `ntoskrnl!ZwClose` at `0x140004acb`
- `ntoskrnl!PsTerminateSystemThread` at `0x140004ad9`
- `ntoskrnl!PsTerminateSystemThread` at `0x140004ad9`
- `rdbss!RxPostToWorkerThread` at `0x140004a56`
- `rdbss!RxPostToWorkerThread` at `0x140004a56`

## pseudocode

```c
void __fastcall MRxDAVContextTimerThread(PVOID StartContext)
{
  int v1; // ebx
  LARGE_INTEGER v2; // rbx

  v1 = TimerThreadSleepTimeInSec;
  ExAcquireResourceExclusiveLite(&MRxDAVTimerThreadLock, 1u);
  if ( !TimerThreadShutDown )
  {
    v2.QuadPart = -10000000 * v1;
    do
    {
      ExReleaseResourceLite(&MRxDAVTimerThreadLock);
      KeSetTimerEx(&DavTimerObject, v2, 0, 0);
      KeWaitForSingleObject(&DavTimerObject, Executive, 0, 0, 0);
      ExAcquireResourceExclusiveLite(&MRxDAVTimerThreadLock, 1u);
      if ( TimerThreadShutDown )
        break;
      ExReleaseResourceLite(&MRxDAVTimerThreadLock);
      MRxDAVTimeOutTheContexts(0);
      MRxDAVCleanUpTheLockConflictList(0);
      ExAcquireResourceExclusiveLite(&QueueLockRefreshWorkItemLock, 1u);
      if ( QueueLockRefreshWorkItem )
      {
        RxPostToWorkerThread(
          g_MRxDAVDeviceObject,
          CriticalWorkQueue,
          &LockRefreshWorkQueueItem,
          (PRX_WORKERTHREAD_ROUTINE)MRxDAVRefreshTheServerLocks,
          0);
        QueueLockRefreshWorkItem = 0;
      }
      ExReleaseResourceLite(&QueueLockRefreshWorkItemLock);
      ExAcquireResourceExclusiveLite(&MRxDAVTimerThreadLock, 1u);
    }
    while ( !TimerThreadShutDown );
  }
  ExReleaseResourceLite(&MRxDAVTimerThreadLock);
  KeSetEvent(&TimerThreadEvent, 0, 0);
  ZwClose(TimerThreadHandle);
  PsTerminateSystemThread(0);
}

```

## disassembly

```asm
0x140004950  mov     [rsp+arg_0], rbx
0x140004955  push    rsi
0x140004956  sub     rsp, 30h
0x14000495a  mov     ebx, cs:TimerThreadSleepTimeInSec
0x140004960  lea     rsi, MRxDAVTimerThreadLock
0x140004967  mov     rcx, rsi; Resource
0x14000496a  mov     dl, 1; Wait
0x14000496c  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140004973  nop     dword ptr [rax+rax+00h]
0x140004978  cmp     cs:TimerThreadShutDown, 0
0x14000497f  jnz     loc_140004A9D
0x140004985  imul    eax, ebx, 0FF676980h
0x14000498b  movsxd  rbx, eax
0x14000498e  mov     rcx, rsi; Resource
0x140004991  call    cs:__imp_ExReleaseResourceLite
0x140004998  nop     dword ptr [rax+rax+00h]
0x14000499d  xor     r9d, r9d; Dpc
0x1400049a0  lea     rcx, DavTimerObject; Timer
0x1400049a7  xor     r8d, r8d; Period
0x1400049aa  mov     rdx, rbx; DueTime
0x1400049ad  call    cs:__imp_KeSetTimerEx
0x1400049b4  nop     dword ptr [rax+rax+00h]
0x1400049b9  xor     r9d, r9d; Alertable
0x1400049bc  mov     [rsp+38h+Timeout], 0; Timeout
0x1400049c5  xor     r8d, r8d; WaitMode
0x1400049c8  lea     rcx, DavTimerObject; Object
0x1400049cf  xor     edx, edx; WaitReason
0x1400049d1  call    cs:__imp_KeWaitForSingleObject
0x1400049d8  nop     dword ptr [rax+rax+00h]
0x1400049dd  mov     dl, 1; Wait
0x1400049df  mov     rcx, rsi; Resource
0x1400049e2  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1400049e9  nop     dword ptr [rax+rax+00h]
0x1400049ee  cmp     cs:TimerThreadShutDown, 0
0x1400049f5  jnz     loc_140004A9D
0x1400049fb  mov     rcx, rsi; Resource
0x1400049fe  call    cs:__imp_ExReleaseResourceLite
0x140004a05  nop     dword ptr [rax+rax+00h]
0x140004a0a  xor     ecx, ecx
0x140004a0c  call    MRxDAVTimeOutTheContexts
0x140004a11  xor     ecx, ecx
0x140004a13  call    MRxDAVCleanUpTheLockConflictList
0x140004a18  mov     dl, 1; Wait
0x140004a1a  lea     rcx, QueueLockRefreshWorkItemLock; Resource
0x140004a21  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140004a28  nop     dword ptr [rax+rax+00h]
0x140004a2d  cmp     cs:QueueLockRefreshWorkItem, 0
0x140004a34  jz      short loc_140004A6C
0x140004a36  mov     rcx, cs:g_MRxDAVDeviceObject; pMRxDeviceObject
0x140004a3d  lea     r9, MRxDAVRefreshTheServerLocks; Routine
0x140004a44  lea     r8, LockRefreshWorkQueueItem; pWorkQueueItem
0x140004a4b  mov     [rsp+38h+Timeout], 0; pContext
0x140004a54  xor     edx, edx; WorkQueueType
0x140004a56  call    cs:__imp_RxPostToWorkerThread
0x140004a5d  nop     dword ptr [rax+rax+00h]
0x140004a62  mov     cs:QueueLockRefreshWorkItem, 0
0x140004a6c  lea     rcx, QueueLockRefreshWorkItemLock; Resource
0x140004a73  call    cs:__imp_ExReleaseResourceLite
0x140004a7a  nop     dword ptr [rax+rax+00h]
0x140004a7f  mov     dl, 1; Wait
0x140004a81  mov     rcx, rsi; Resource
0x140004a84  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140004a8b  nop     dword ptr [rax+rax+00h]
0x140004a90  cmp     cs:TimerThreadShutDown, 0
0x140004a97  jz      loc_14000498E
0x140004a9d  mov     rcx, rsi; Resource
0x140004aa0  call    cs:__imp_ExReleaseResourceLite
0x140004aa7  nop     dword ptr [rax+rax+00h]
0x140004aac  xor     r8d, r8d; Wait
0x140004aaf  lea     rcx, TimerThreadEvent; Event
0x140004ab6  xor     edx, edx; Increment
0x140004ab8  call    cs:__imp_KeSetEvent
0x140004abf  nop     dword ptr [rax+rax+00h]
0x140004ac4  mov     rcx, cs:TimerThreadHandle; Handle
0x140004acb  call    cs:__imp_ZwClose
0x140004ad2  nop     dword ptr [rax+rax+00h]
0x140004ad7  xor     ecx, ecx; ExitStatus
0x140004ad9  call    cs:__imp_PsTerminateSystemThread
0x140004ae0  nop     dword ptr [rax+rax+00h]
0x140004ae5  mov     rbx, [rsp+38h+arg_0]
0x140004aea  add     rsp, 30h
0x140004aee  pop     rsi
0x140004aef  retn
```
