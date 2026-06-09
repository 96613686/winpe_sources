# HidpCreateRemoteWakeIrpWorker

- ea: `0x1800381b0`
- end: `0x180038207`
- name: `HidpCreateRemoteWakeIrpWorker`
- size: `87`
- prototype: `IO_WORKITEM_ROUTINE`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180038090`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1800381f4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800381f4`
- `ntoskrnl!IoFreeWorkItem` at `0x1800381e3`
- `ntoskrnl!IoFreeWorkItem` at `0x1800381e3`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1800381d3`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1800381d3`

## pseudocode

```c
void __fastcall HidpCreateRemoteWakeIrpWorker(PDEVICE_OBJECT DeviceObject, PVOID Context)
{
  HidpCreateRemoteWakeIrp(*((PVOID *)Context + 1));
  IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(*((_QWORD *)Context + 1) + 16LL), Context, 0x20u);
  IoFreeWorkItem(*((PIO_WORKITEM *)Context + 2));
  ExFreePoolWithTag(Context, 0);
}

```

## disassembly

```asm
0x1800381b0  push    rbx
0x1800381b2  sub     rsp, 20h
0x1800381b6  mov     rcx, [rdx+8]; Context
0x1800381ba  mov     rbx, rdx
0x1800381bd  call    HidpCreateRemoteWakeIrp
0x1800381c2  mov     rcx, [rbx+8]
0x1800381c6  mov     r8d, 20h ; ' '; RemlockSize
0x1800381cc  add     rcx, 10h; RemoveLock
0x1800381d0  mov     rdx, rbx; Tag
0x1800381d3  call    cs:__imp_IoReleaseRemoveLockEx
0x1800381da  nop     dword ptr [rax+rax+00h]
0x1800381df  mov     rcx, [rbx+10h]; IoWorkItem
0x1800381e3  call    cs:__imp_IoFreeWorkItem
0x1800381ea  nop     dword ptr [rax+rax+00h]
0x1800381ef  xor     edx, edx; Tag
0x1800381f1  mov     rcx, rbx; P
0x1800381f4  call    cs:__imp_ExFreePoolWithTag
0x1800381fb  nop     dword ptr [rax+rax+00h]
0x180038200  add     rsp, 20h
0x180038204  pop     rbx
0x180038205  retn
```
