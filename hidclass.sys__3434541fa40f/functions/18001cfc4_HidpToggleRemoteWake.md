# HidpToggleRemoteWake

- ea: `0x18001cfc4`
- end: `0x18001d0e4`
- name: `HidpToggleRemoteWake`
- size: `288`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18001ccc0`
- `0x180038210`
- `0x1800382d0`

## callees

- `0x18001cfc4`
- `0x18001d0f0`

## import_xrefs

- `ntoskrnl!IoQueueWorkItem` at `0x18001d0b0`
- `ntoskrnl!IoQueueWorkItem` at `0x18001d0b0`
- `ntoskrnl!ExFreePoolWithTag` at `0x18001d068`
- `ntoskrnl!ExFreePoolWithTag` at `0x18001d068`
- `ntoskrnl!ExAllocatePool2` at `0x18001d01c`
- `ntoskrnl!ExAllocatePool2` at `0x18001d01c`
- `ntoskrnl!KeGetCurrentIrql` at `0x18001d07e`
- `ntoskrnl!KeGetCurrentIrql` at `0x18001d07e`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x18001d057`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x18001d0ca`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x18001d057`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x18001d0ca`
- `ntoskrnl!IoAllocateWorkItem` at `0x18001d038`
- `ntoskrnl!IoAllocateWorkItem` at `0x18001d038`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x18001cffa`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x18001cffa`

## pseudocode

```c
NTSTATUS __fastcall HidpToggleRemoteWake(__int64 a1, char a2)
{
  struct _IO_REMOVE_LOCK *v2; // rsi
  NTSTATUS result; // eax
  __int64 Pool2; // rbx
  PIO_WORKITEM WorkItem; // rax

  v2 = (struct _IO_REMOVE_LOCK *)(a1 + 16);
  result = IoAcquireRemoveLockEx((PIO_REMOVE_LOCK)(a1 + 16), (PVOID)0x54575752, File, 1u, 0x20u);
  if ( result >= 0 )
  {
    Pool2 = ExAllocatePool2(64, 32, 1130654024);
    if ( Pool2 )
    {
      WorkItem = IoAllocateWorkItem(*(PDEVICE_OBJECT *)(a1 + 48));
      *(_QWORD *)(Pool2 + 16) = WorkItem;
      if ( WorkItem )
      {
        *(_QWORD *)(Pool2 + 8) = a1;
        *(_BYTE *)(Pool2 + 24) = a2;
        if ( KeGetCurrentIrql() )
          IoQueueWorkItem(*(PIO_WORKITEM *)(Pool2 + 16), HidpToggleRemoteWakeWorker, DelayedWorkQueue, (PVOID)Pool2);
        else
          HidpToggleRemoteWakeWorker(*(PDEVICE_OBJECT *)(a1 + 48), (PVOID)Pool2);
      }
      else
      {
        IoReleaseRemoveLockEx(v2, (PVOID)0x54575752, 0x20u);
        ExFreePoolWithTag((PVOID)Pool2, 0);
      }
    }
    else
    {
      IoReleaseRemoveLockEx(v2, (PVOID)0x54575752, 0x20u);
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18001cfc4  push    rbx
0x18001cfc6  push    rbp
0x18001cfc7  push    rsi
0x18001cfc8  push    rdi
0x18001cfc9  push    r15
0x18001cfcb  sub     rsp, 30h
0x18001cfcf  lea     rsi, [rcx+10h]
0x18001cfd3  mov     [rsp+58h+RemlockSize], 20h ; ' '; RemlockSize
0x18001cfdb  mov     bpl, dl
0x18001cfde  lea     r8, File; File
0x18001cfe5  mov     rdi, rcx
0x18001cfe8  mov     r15d, 54575752h
0x18001cfee  mov     edx, r15d; Tag
0x18001cff1  mov     rcx, rsi; RemoveLock
0x18001cff4  mov     r9d, 1; Line
0x18001cffa  call    cs:__imp_IoAcquireRemoveLockEx
0x18001d001  nop     dword ptr [rax+rax+00h]
0x18001d006  test    eax, eax
0x18001d008  js      loc_18001D0D8
0x18001d00e  mov     edx, 20h ; ' '
0x18001d013  mov     r8d, 43646948h
0x18001d019  lea     ecx, [rdx+20h]
0x18001d01c  call    cs:__imp_ExAllocatePool2
0x18001d023  nop     dword ptr [rax+rax+00h]
0x18001d028  mov     rbx, rax
0x18001d02b  test    rax, rax
0x18001d02e  jz      loc_18001D0BE
0x18001d034  mov     rcx, [rdi+30h]; DeviceObject
0x18001d038  call    cs:__imp_IoAllocateWorkItem
0x18001d03f  nop     dword ptr [rax+rax+00h]
0x18001d044  mov     [rbx+10h], rax
0x18001d048  test    rax, rax
0x18001d04b  jnz     short loc_18001D076
0x18001d04d  lea     r8d, [rax+20h]; RemlockSize
0x18001d051  mov     edx, r15d; Tag
0x18001d054  mov     rcx, rsi; RemoveLock
0x18001d057  call    cs:__imp_IoReleaseRemoveLockEx
0x18001d05e  nop     dword ptr [rax+rax+00h]
0x18001d063  xor     edx, edx; Tag
0x18001d065  mov     rcx, rbx; P
0x18001d068  call    cs:__imp_ExFreePoolWithTag
0x18001d06f  nop     dword ptr [rax+rax+00h]
0x18001d074  jmp     short loc_18001D0D6
0x18001d076  mov     [rbx+8], rdi
0x18001d07a  mov     [rbx+18h], bpl
0x18001d07e  call    cs:__imp_KeGetCurrentIrql
0x18001d085  nop     dword ptr [rax+rax+00h]
0x18001d08a  test    al, al
0x18001d08c  jnz     short loc_18001D09C
0x18001d08e  mov     rcx, [rdi+30h]; DeviceObject
0x18001d092  mov     rdx, rbx; Context
0x18001d095  call    HidpToggleRemoteWakeWorker
0x18001d09a  jmp     short loc_18001D0D6
0x18001d09c  mov     rcx, [rbx+10h]; IoWorkItem
0x18001d0a0  lea     rdx, HidpToggleRemoteWakeWorker; WorkerRoutine
0x18001d0a7  mov     r9, rbx; Context
0x18001d0aa  mov     r8d, 1; QueueType
0x18001d0b0  call    cs:__imp_IoQueueWorkItem
0x18001d0b7  nop     dword ptr [rax+rax+00h]
0x18001d0bc  jmp     short loc_18001D0D6
0x18001d0be  mov     r8d, 20h ; ' '; RemlockSize
0x18001d0c4  mov     rdx, r15; Tag
0x18001d0c7  mov     rcx, rsi; RemoveLock
0x18001d0ca  call    cs:__imp_IoReleaseRemoveLockEx
0x18001d0d1  nop     dword ptr [rax+rax+00h]
0x18001d0d6  xor     eax, eax
0x18001d0d8  add     rsp, 30h
0x18001d0dc  pop     r15
0x18001d0de  pop     rdi
0x18001d0df  pop     rsi
0x18001d0e0  pop     rbp
0x18001d0e1  pop     rbx
0x18001d0e2  retn
```
