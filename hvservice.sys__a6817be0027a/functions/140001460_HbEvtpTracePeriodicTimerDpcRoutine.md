# HbEvtpTracePeriodicTimerDpcRoutine

- ea: `0x140001460`
- end: `0x1400015bd`
- name: `HbEvtpTracePeriodicTimerDpcRoutine`
- size: `349`
- prototype: `void __fastcall(struct _KDPC *Dpc, PVOID DeferredContext, PVOID SystemArgument1, PVOID SystemArgument2)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x140001270`
- `0x140001460`
- `0x140001600`

## import_xrefs

- `ntoskrnl!IoAcquireRemoveLockEx` at `0x140001486`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x1400014e9`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x140001486`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x1400014e9`
- `ntoskrnl!IoAllocateWorkItem` at `0x1400014fc`
- `ntoskrnl!IoAllocateWorkItem` at `0x1400014fc`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14000153b`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1400015a5`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14000153b`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1400015a5`
- `ntoskrnl!IoQueueWorkItemEx` at `0x140001520`
- `ntoskrnl!IoQueueWorkItemEx` at `0x140001520`

## string_xrefs

- `0x140001496`: `Remove lock unavailable`
- `0x140001549`: `Failed to get remove lock`

## pseudocode

```c
void __fastcall HbEvtpTracePeriodicTimerDpcRoutine(
        struct _KDPC *Dpc,
        PVOID DeferredContext,
        PVOID SystemArgument1,
        PVOID SystemArgument2)
{
  struct _IO_WORKITEM *WorkItem; // rax

  if ( IoAcquireRemoveLockEx((PIO_REMOVE_LOCK)DeferredContext + 2, DeferredContext, File, 1u, 0x20u) >= 0 )
  {
    if ( byte_14000904A )
    {
      if ( IoAcquireRemoveLockEx((PIO_REMOVE_LOCK)DeferredContext + 2, DeferredContext, File, 1u, 0x20u) < 0 )
      {
        HbpTraceEvent(1, "HbEvtpTracePeriodicTimerDpcRoutine", 3370, "Failed to get remove lock");
      }
      else
      {
        WorkItem = IoAllocateWorkItem(*(PDEVICE_OBJECT *)DeferredContext);
        if ( WorkItem )
          IoQueueWorkItemEx(
            WorkItem,
            (PIO_WORKITEM_ROUTINE_EX)HbEvtpPeriodicGlobalSystemEventFlushWorkItemRoutine,
            DelayedWorkQueue,
            DeferredContext);
        else
          IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)DeferredContext + 2, DeferredContext, 0x20u);
      }
    }
    else
    {
      HbpTraceEvent(1, "HbEvtpTracePeriodicTimerDpcRoutine", 3375, "HbEvtpSystemGlobalLogInitialized == FALSE ");
    }
    if ( byte_140009049 )
      HbEvtpScheduleSystemDiagLogWorkItem(DeferredContext);
    IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)DeferredContext + 2, DeferredContext, 0x20u);
  }
  else
  {
    HbpTraceEvent(1, "HbEvtpTracePeriodicTimerDpcRoutine", 3341, "Remove lock unavailable");
  }
}

```

## disassembly

```asm
0x140001460  mov     [rsp+arg_0], rbx
0x140001465  push    rdi
0x140001466  sub     rsp, 30h
0x14000146a  mov     r9d, 1; Line
0x140001470  mov     [rsp+38h+RemlockSize], 20h ; ' '; RemlockSize
0x140001478  lea     r8, File; File
0x14000147f  mov     rbx, rdx
0x140001482  lea     rcx, [rdx+40h]; RemoveLock
0x140001486  call    cs:__imp_IoAcquireRemoveLockEx
0x14000148d  nop     dword ptr [rax+rax+00h]
0x140001492  test    eax, eax
0x140001494  jns     short loc_1400014C0
0x140001496  lea     r9, aRemoveLockUnav; "Remove lock unavailable"
0x14000149d  mov     r8d, 0D0Dh
0x1400014a3  lea     rdx, aHbevtptraceper; "HbEvtpTracePeriodicTimerDpcRoutine"
0x1400014aa  mov     ecx, 1
0x1400014af  call    HbpTraceEvent
0x1400014b4  mov     rbx, [rsp+38h+arg_0]
0x1400014b9  add     rsp, 30h
0x1400014bd  pop     rdi
0x1400014be  retn
0x1400014c0  cmp     cs:byte_14000904A, 0
0x1400014c7  jz      loc_140001569
0x1400014cd  mov     r9d, 1; Line
0x1400014d3  mov     [rsp+38h+RemlockSize], 20h ; ' '; RemlockSize
0x1400014db  lea     r8, File; File
0x1400014e2  mov     rdx, rbx; Tag
0x1400014e5  lea     rcx, [rbx+40h]; RemoveLock
0x1400014e9  call    cs:__imp_IoAcquireRemoveLockEx
0x1400014f0  nop     dword ptr [rax+rax+00h]
0x1400014f5  test    eax, eax
0x1400014f7  js      short loc_140001549
0x1400014f9  mov     rcx, [rbx]; DeviceObject
0x1400014fc  call    cs:__imp_IoAllocateWorkItem
0x140001503  nop     dword ptr [rax+rax+00h]
0x140001508  test    rax, rax
0x14000150b  jz      short loc_14000152E
0x14000150d  mov     r9, rbx; Context
0x140001510  lea     rdx, HbEvtpPeriodicGlobalSystemEventFlushWorkItemRoutine; WorkerRoutine
0x140001517  mov     r8d, 1; QueueType
0x14000151d  mov     rcx, rax; IoWorkItem
0x140001520  call    cs:__imp_IoQueueWorkItemEx
0x140001527  nop     dword ptr [rax+rax+00h]
0x14000152c  jmp     short loc_140001587
0x14000152e  mov     r8d, 20h ; ' '; RemlockSize
0x140001534  lea     rcx, [rbx+40h]; RemoveLock
0x140001538  mov     rdx, rbx; Tag
0x14000153b  call    cs:__imp_IoReleaseRemoveLockEx
0x140001542  nop     dword ptr [rax+rax+00h]
0x140001547  jmp     short loc_140001587
0x140001549  lea     r9, aFailedToGetRem; "Failed to get remove lock"
0x140001550  mov     r8d, 0D2Ah
0x140001556  lea     rdx, aHbevtptraceper; "HbEvtpTracePeriodicTimerDpcRoutine"
0x14000155d  mov     ecx, 1
0x140001562  call    HbpTraceEvent
0x140001567  jmp     short loc_140001587
0x140001569  lea     r9, aHbevtpsystemgl; "HbEvtpSystemGlobalLogInitialized == FAL"...
0x140001570  mov     r8d, 0D2Fh
0x140001576  lea     rdx, aHbevtptraceper; "HbEvtpTracePeriodicTimerDpcRoutine"
0x14000157d  mov     ecx, 1
0x140001582  call    HbpTraceEvent
0x140001587  cmp     cs:byte_140009049, 0
0x14000158e  jz      short loc_140001598
0x140001590  mov     rcx, rbx; Tag
0x140001593  call    HbEvtpScheduleSystemDiagLogWorkItem
0x140001598  mov     r8d, 20h ; ' '; RemlockSize
0x14000159e  lea     rcx, [rbx+40h]; RemoveLock
0x1400015a2  mov     rdx, rbx; Tag
0x1400015a5  call    cs:__imp_IoReleaseRemoveLockEx
0x1400015ac  nop     dword ptr [rax+rax+00h]
0x1400015b1  mov     rbx, [rsp+38h+arg_0]
0x1400015b6  add     rsp, 30h
0x1400015ba  pop     rdi
0x1400015bb  retn
```
