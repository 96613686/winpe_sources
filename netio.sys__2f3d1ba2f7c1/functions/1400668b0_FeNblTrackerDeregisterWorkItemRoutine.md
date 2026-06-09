# FeNblTrackerDeregisterWorkItemRoutine

- ea: `0x1400668b0`
- end: `0x1400668f3`
- name: `FeNblTrackerDeregisterWorkItemRoutine`
- size: `67`
- prototype: `IO_WORKITEM_ROUTINE`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `ntoskrnl!IoFreeWorkItem` at `0x1400668cc`
- `ntoskrnl!IoFreeWorkItem` at `0x1400668cc`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400668e0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400668e0`
- `NDIS!NdisNblTrackerDeregisterComponent` at `0x1400668bd`
- `NDIS!NdisNblTrackerDeregisterComponent` at `0x1400668bd`

## pseudocode

```c
void __fastcall FeNblTrackerDeregisterWorkItemRoutine(PDEVICE_OBJECT DeviceObject, PIO_WORKITEM *Context)
{
  NdisNblTrackerDeregisterComponent(Context[1]);
  IoFreeWorkItem(*Context);
  ExFreePoolWithTag(Context, 0x43706657u);
}

```

## disassembly

```asm
0x1400668b0  push    rbx
0x1400668b2  sub     rsp, 20h
0x1400668b6  mov     rcx, [rdx+8]
0x1400668ba  mov     rbx, rdx
0x1400668bd  call    cs:__imp_NdisNblTrackerDeregisterComponent
0x1400668c4  nop     dword ptr [rax+rax+00h]
0x1400668c9  mov     rcx, [rbx]; IoWorkItem
0x1400668cc  call    cs:__imp_IoFreeWorkItem
0x1400668d3  nop     dword ptr [rax+rax+00h]
0x1400668d8  mov     edx, 43706657h; Tag
0x1400668dd  mov     rcx, rbx; P
0x1400668e0  call    cs:__imp_ExFreePoolWithTag
0x1400668e7  nop     dword ptr [rax+rax+00h]
0x1400668ec  add     rsp, 20h
0x1400668f0  pop     rbx
0x1400668f1  retn
```
