# ScheduleWorkItem

- ea: `0x1400054d4`
- end: `0x1400054fe`
- name: `ScheduleWorkItem`
- size: `42`
- prototype: `__int64 __fastcall(PVOID WorkItemContext)`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x1400037c0`
- `0x140003d18`
- `0x14000e7b0`
- `0x140014d2c`
- `0x1400152f4`

## import_xrefs

- `NDIS!NdisQueueIoWorkItem` at `0x1400054ec`
- `NDIS!NdisQueueIoWorkItem` at `0x1400054ec`

## pseudocode

```c
void __fastcall ScheduleWorkItem(NDIS_HANDLE *WorkItemContext)
{
  *(_DWORD *)WorkItemContext = 1;
  NdisQueueIoWorkItem(WorkItemContext[8], (NDIS_IO_WORKITEM_ROUTINE)WorkItemExec, WorkItemContext);
}

```

## disassembly

```asm
0x1400054d4  sub     rsp, 28h
0x1400054d8  mov     dword ptr [rcx], 1
0x1400054de  lea     rdx, WorkItemExec; Routine
0x1400054e5  mov     r8, rcx; WorkItemContext
0x1400054e8  mov     rcx, [rcx+40h]; NdisIoWorkItemHandle
0x1400054ec  call    cs:__imp_NdisQueueIoWorkItem
0x1400054f3  nop     dword ptr [rax+rax+00h]
0x1400054f8  add     rsp, 28h
0x1400054fc  retn
```
