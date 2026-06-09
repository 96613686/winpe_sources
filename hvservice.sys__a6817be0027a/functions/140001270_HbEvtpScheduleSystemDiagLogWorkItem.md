# HbEvtpScheduleSystemDiagLogWorkItem

- ea: `0x140001270`
- end: `0x14000132b`
- name: `HbEvtpScheduleSystemDiagLogWorkItem`
- size: `187`
- prototype: `void __fastcall(PVOID Tag)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140001460`
- `0x140013480`

## callees

- `0x140001270`

## import_xrefs

- `ntoskrnl!IoAcquireRemoveLockEx` at `0x1400012c6`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x1400012c6`
- `ntoskrnl!IoAllocateWorkItem` at `0x1400012d9`
- `ntoskrnl!IoAllocateWorkItem` at `0x1400012d9`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14000131d`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14000131d`
- `ntoskrnl!IoQueueWorkItemEx` at `0x1400012fd`
- `ntoskrnl!IoQueueWorkItemEx` at `0x1400012fd`
- `ntoskrnl!EtwProviderEnabled` at `0x140001285`
- `ntoskrnl!EtwProviderEnabled` at `0x140001285`

## pseudocode

```c
void __fastcall HbEvtpScheduleSystemDiagLogWorkItem(PVOID Tag)
{
  struct _IO_WORKITEM *WorkItem; // rax

  if ( EtwProviderEnabled(RegHandle, 0, 0)
    && byte_140009049
    && IoAcquireRemoveLockEx((PIO_REMOVE_LOCK)Tag + 2, Tag, File, 1u, 0x20u) >= 0 )
  {
    WorkItem = IoAllocateWorkItem(*(PDEVICE_OBJECT *)Tag);
    if ( WorkItem )
      IoQueueWorkItemEx(WorkItem, HbEvtpSysDiagLogWorkItemRoutine, DelayedWorkQueue, Tag);
    else
      IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)Tag + 2, Tag, 0x20u);
  }
}

```

## disassembly

```asm
0x140001270  push    rbx
0x140001272  sub     rsp, 30h
0x140001276  mov     rbx, rcx
0x140001279  xor     r8d, r8d; Keyword
0x14000127c  mov     rcx, cs:RegHandle; RegHandle
0x140001283  xor     edx, edx; Level
0x140001285  call    cs:__imp_EtwProviderEnabled
0x14000128c  nop     dword ptr [rax+rax+00h]
0x140001291  test    al, al
0x140001293  jnz     short loc_14000129C
0x140001295  add     rsp, 30h
0x140001299  pop     rbx
0x14000129a  retn
0x14000129c  cmp     cs:byte_140009049, 0
0x1400012a3  jz      short loc_140001295
0x1400012a5  mov     r9d, 1; Line
0x1400012ab  mov     [rsp+38h+arg_0], rdi
0x1400012b0  lea     r8, File; File
0x1400012b7  mov     [rsp+38h+RemlockSize], 20h ; ' '; RemlockSize
0x1400012bf  mov     rdx, rbx; Tag
0x1400012c2  lea     rcx, [rbx+40h]; RemoveLock
0x1400012c6  call    cs:__imp_IoAcquireRemoveLockEx
0x1400012cd  nop     dword ptr [rax+rax+00h]
0x1400012d2  test    eax, eax
0x1400012d4  js      short loc_140001309
0x1400012d6  mov     rcx, [rbx]; DeviceObject
0x1400012d9  call    cs:__imp_IoAllocateWorkItem
0x1400012e0  nop     dword ptr [rax+rax+00h]
0x1400012e5  test    rax, rax
0x1400012e8  jz      short loc_140001310
0x1400012ea  mov     r9, rbx; Context
0x1400012ed  lea     rdx, HbEvtpSysDiagLogWorkItemRoutine; WorkerRoutine
0x1400012f4  mov     r8d, 1; QueueType
0x1400012fa  mov     rcx, rax; IoWorkItem
0x1400012fd  call    cs:__imp_IoQueueWorkItemEx
0x140001304  nop     dword ptr [rax+rax+00h]
0x140001309  mov     rdi, [rsp+38h+arg_0]
0x14000130e  jmp     short loc_140001295
0x140001310  mov     r8d, 20h ; ' '; RemlockSize
0x140001316  lea     rcx, [rbx+40h]; RemoveLock
0x14000131a  mov     rdx, rbx; Tag
0x14000131d  call    cs:__imp_IoReleaseRemoveLockEx
0x140001324  nop     dword ptr [rax+rax+00h]
0x140001329  jmp     short loc_140001309
```
