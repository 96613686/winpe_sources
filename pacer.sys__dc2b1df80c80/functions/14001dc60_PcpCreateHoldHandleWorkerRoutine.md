# PcpCreateHoldHandleWorkerRoutine

- ea: `0x14001dc60`
- end: `0x14001dc84`
- name: `PcpCreateHoldHandleWorkerRoutine`
- size: `36`
- prototype: `IO_WORKITEM_ROUTINE_EX`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x14000f6d4`

## import_xrefs

- `ntoskrnl!IoFreeWorkItem` at `0x14001dc71`
- `ntoskrnl!IoFreeWorkItem` at `0x14001dc71`

## pseudocode

```c
void __fastcall PcpCreateHoldHandleWorkerRoutine(PVOID IoObject, PVOID Context, PIO_WORKITEM IoWorkItem)
{
  PcpCreateHoldHandle();
  IoFreeWorkItem(IoWorkItem);
}

```

## disassembly

```asm
0x14001dc60  push    rbx
0x14001dc62  sub     rsp, 20h
0x14001dc66  mov     rbx, r8
0x14001dc69  call    PcpCreateHoldHandle
0x14001dc6e  mov     rcx, rbx; IoWorkItem
0x14001dc71  call    cs:__imp_IoFreeWorkItem
0x14001dc78  nop     dword ptr [rax+rax+00h]
0x14001dc7d  add     rsp, 20h
0x14001dc81  pop     rbx
0x14001dc82  retn
```
