# AynchronousReadCompletionWorker

- ea: `0x18001ff70`
- end: `0x18001ffb3`
- name: `AynchronousReadCompletionWorker`
- size: `67`
- prototype: `IO_WORKITEM_ROUTINE`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x18001ff7f`
- `ntoskrnl!IofCompleteRequest` at `0x18001ff7f`
- `ntoskrnl!ExFreePoolWithTag` at `0x18001ffa0`
- `ntoskrnl!ExFreePoolWithTag` at `0x18001ffa0`
- `ntoskrnl!IoFreeWorkItem` at `0x18001ff8f`
- `ntoskrnl!IoFreeWorkItem` at `0x18001ff8f`

## pseudocode

```c
void __fastcall AynchronousReadCompletionWorker(PDEVICE_OBJECT DeviceObject, PVOID Context)
{
  IofCompleteRequest(*((PIRP *)Context + 2), 0);
  IoFreeWorkItem(*((PIO_WORKITEM *)Context + 1));
  ExFreePoolWithTag(Context, 0);
}

```

## disassembly

```asm
0x18001ff70  push    rbx
0x18001ff72  sub     rsp, 20h
0x18001ff76  mov     rbx, rdx
0x18001ff79  xor     edx, edx; PriorityBoost
0x18001ff7b  mov     rcx, [rbx+10h]; Irp
0x18001ff7f  call    cs:__imp_IofCompleteRequest
0x18001ff86  nop     dword ptr [rax+rax+00h]
0x18001ff8b  mov     rcx, [rbx+8]; IoWorkItem
0x18001ff8f  call    cs:__imp_IoFreeWorkItem
0x18001ff96  nop     dword ptr [rax+rax+00h]
0x18001ff9b  xor     edx, edx; Tag
0x18001ff9d  mov     rcx, rbx; P
0x18001ffa0  call    cs:__imp_ExFreePoolWithTag
0x18001ffa7  nop     dword ptr [rax+rax+00h]
0x18001ffac  add     rsp, 20h
0x18001ffb0  pop     rbx
0x18001ffb1  retn
```
