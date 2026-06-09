# HbEvtpTraceCompletedDpcRoutine

- ea: `0x140001e20`
- end: `0x140001f64`
- name: `HbEvtpTraceCompletedDpcRoutine`
- size: `324`
- prototype: `void __fastcall(struct _KDPC *Dpc, struct _IO_REMOVE_LOCK *DeferredContext, PVOID SystemArgument1, PVOID SystemArgument2)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x140001600`
- `0x140001e20`

## import_xrefs

- `ntoskrnl!IoAcquireRemoveLockEx` at `0x140001e7b`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x140001e7b`
- `ntoskrnl!IoAllocateWorkItem` at `0x140001eda`
- `ntoskrnl!IoAllocateWorkItem` at `0x140001efb`
- `ntoskrnl!IoAllocateWorkItem` at `0x140001eda`
- `ntoskrnl!IoAllocateWorkItem` at `0x140001efb`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140001f4a`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140001f4a`
- `ntoskrnl!IoQueueWorkItemEx` at `0x140001f1c`
- `ntoskrnl!IoQueueWorkItemEx` at `0x140001f1c`
- `ntoskrnl!ExAcquireRundownProtection` at `0x140001ec3`
- `ntoskrnl!ExAcquireRundownProtection` at `0x140001ec3`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140001f2d`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140001f2d`

## string_xrefs

- `0x140001e4c`: `HbEvtpTraceCompletedDpcRoutine`
- `0x140001e98`: `HbEvtpTraceCompletedDpcRoutine`
- `0x140001e8b`: `Remove lock not available`

## pseudocode

```c
void __fastcall HbEvtpTraceCompletedDpcRoutine(
        struct _KDPC *Dpc,
        struct _IO_REMOVE_LOCK *DeferredContext,
        PVOID SystemArgument1,
        PVOID SystemArgument2)
{
  unsigned int v4; // r14d
  int v5; // edi
  char v7; // bl
  struct _IO_WORKITEM *WorkItem; // rax
  IO_WORKITEM_ROUTINE_EX *v9; // rdx

  v4 = (unsigned int)SystemArgument2;
  v5 = (int)SystemArgument1;
  HbpTraceEvent(
    3,
    "HbEvtpTraceCompletedDpcRoutine",
    4347,
    "Entering ISR DPC (eventlog %d, buffer %d)",
    (_DWORD)SystemArgument1,
    (_DWORD)SystemArgument2);
  v7 = 1;
  if ( IoAcquireRemoveLockEx(DeferredContext + 2, DeferredContext, File, 1u, 0x20u) < 0 )
  {
    HbpTraceEvent(1, "HbEvtpTraceCompletedDpcRoutine", 4357, "Remove lock not available");
    return;
  }
  if ( ExAcquireRundownProtection(&stru_1400092E8 + 18 * v5) )
  {
    if ( v5 == 1 )
    {
      WorkItem = IoAllocateWorkItem(*(PDEVICE_OBJECT *)&DeferredContext->Common.Removed);
      if ( !WorkItem )
        goto LABEL_11;
      v9 = (IO_WORKITEM_ROUTINE_EX *)HbEvtpLocalDiagEventsWorkItemRoutine;
    }
    else
    {
      if ( v5 || (WorkItem = IoAllocateWorkItem(*(PDEVICE_OBJECT *)&DeferredContext->Common.Removed)) == 0 )
      {
LABEL_11:
        ExReleaseRundownProtection(&stru_1400092E8 + 18 * v5);
        if ( !v7 )
          return;
        goto LABEL_12;
      }
      v9 = (IO_WORKITEM_ROUTINE_EX *)HbEvtpGlobalSystemEventsWorkItemRoutine;
    }
    IoQueueWorkItemEx(WorkItem, v9, DelayedWorkQueue, (PVOID)v4);
    v7 = 0;
    goto LABEL_11;
  }
LABEL_12:
  IoReleaseRemoveLockEx(DeferredContext + 2, DeferredContext, 0x20u);
}

```

## disassembly

```asm
0x140001e20  push    rbx
0x140001e22  push    rbp
0x140001e23  push    rsi
0x140001e24  push    rdi
0x140001e25  push    r14
0x140001e27  push    r15
0x140001e29  sub     rsp, 38h
0x140001e2d  mov     r14, r9
0x140001e30  mov     rdi, r8
0x140001e33  mov     rsi, rdx
0x140001e36  mov     [rsp+68h+var_40], r14d
0x140001e3b  lea     r9, aEnteringIsrDpc; "Entering ISR DPC (eventlog %d, buffer %"...
0x140001e42  mov     r8d, 10FBh
0x140001e48  mov     [rsp+68h+RemlockSize], edi
0x140001e4c  lea     rdx, aHbevtptracecom; "HbEvtpTraceCompletedDpcRoutine"
0x140001e53  mov     ecx, 3
0x140001e58  call    HbpTraceEvent
0x140001e5d  mov     ebx, 1
0x140001e62  mov     [rsp+68h+RemlockSize], 20h ; ' '; RemlockSize
0x140001e6a  mov     r9d, ebx; Line
0x140001e6d  lea     r8, File; File
0x140001e74  mov     rdx, rsi; Tag
0x140001e77  lea     rcx, [rsi+40h]; RemoveLock
0x140001e7b  call    cs:__imp_IoAcquireRemoveLockEx
0x140001e82  nop     dword ptr [rax+rax+00h]
0x140001e87  test    eax, eax
0x140001e89  jns     short loc_140001EAB
0x140001e8b  lea     r9, aRemoveLockNotA; "Remove lock not available"
0x140001e92  mov     r8d, 1105h
0x140001e98  lea     rdx, aHbevtptracecom; "HbEvtpTraceCompletedDpcRoutine"
0x140001e9f  mov     ecx, ebx
0x140001ea1  call    HbpTraceEvent
0x140001ea6  jmp     loc_140001F56
0x140001eab  movsxd  rax, edi
0x140001eae  lea     rbp, [rax+rax*8]
0x140001eb2  lea     rax, stru_1400092E8
0x140001eb9  shl     rbp, 4
0x140001ebd  add     rbp, rax
0x140001ec0  mov     rcx, rbp; RunRef
0x140001ec3  call    cs:__imp_ExAcquireRundownProtection
0x140001eca  nop     dword ptr [rax+rax+00h]
0x140001ecf  test    al, al
0x140001ed1  jz      short loc_140001F3D
0x140001ed3  cmp     edi, ebx
0x140001ed5  jnz     short loc_140001EF4
0x140001ed7  mov     rcx, [rsi]; DeviceObject
0x140001eda  call    cs:__imp_IoAllocateWorkItem
0x140001ee1  nop     dword ptr [rax+rax+00h]
0x140001ee6  test    rax, rax
0x140001ee9  jz      short loc_140001F2A
0x140001eeb  lea     rdx, HbEvtpLocalDiagEventsWorkItemRoutine
0x140001ef2  jmp     short loc_140001F13
0x140001ef4  test    edi, edi
0x140001ef6  jnz     short loc_140001F2A
0x140001ef8  mov     rcx, [rsi]; DeviceObject
0x140001efb  call    cs:__imp_IoAllocateWorkItem
0x140001f02  nop     dword ptr [rax+rax+00h]
0x140001f07  test    rax, rax
0x140001f0a  jz      short loc_140001F2A
0x140001f0c  lea     rdx, HbEvtpGlobalSystemEventsWorkItemRoutine; WorkerRoutine
0x140001f13  mov     r9d, r14d; Context
0x140001f16  mov     r8d, ebx; QueueType
0x140001f19  mov     rcx, rax; IoWorkItem
0x140001f1c  call    cs:__imp_IoQueueWorkItemEx
0x140001f23  nop     dword ptr [rax+rax+00h]
0x140001f28  xor     bl, bl
0x140001f2a  mov     rcx, rbp; RunRef
0x140001f2d  call    cs:__imp_ExReleaseRundownProtection
0x140001f34  nop     dword ptr [rax+rax+00h]
0x140001f39  test    bl, bl
0x140001f3b  jz      short loc_140001F56
0x140001f3d  mov     r8d, 20h ; ' '; RemlockSize
0x140001f43  lea     rcx, [rsi+40h]; RemoveLock
0x140001f47  mov     rdx, rsi; Tag
0x140001f4a  call    cs:__imp_IoReleaseRemoveLockEx
0x140001f51  nop     dword ptr [rax+rax+00h]
0x140001f56  add     rsp, 38h
0x140001f5a  pop     r15
0x140001f5c  pop     r14
0x140001f5e  pop     rdi
0x140001f5f  pop     rsi
0x140001f60  pop     rbp
0x140001f61  pop     rbx
0x140001f62  retn
```
