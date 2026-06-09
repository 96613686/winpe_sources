# I8xCompleteSysButtonEventWorker

- ea: `0x14001d150`
- end: `0x14001d1a2`
- name: `I8xCompleteSysButtonEventWorker`
- size: `82`
- prototype: `IO_WORKITEM_ROUTINE`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x14000d128`
- `0x14001d150`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14001d18f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001d18f`
- `ntoskrnl!IoFreeWorkItem` at `0x14001d17e`
- `ntoskrnl!IoFreeWorkItem` at `0x14001d17e`

## pseudocode

```c
void __fastcall I8xCompleteSysButtonEventWorker(PDEVICE_OBJECT DeviceObject, PVOID Context, __int64 a3, int a4)
{
  IRP *v4; // rcx
  NTSTATUS v5; // r8d

  v4 = (IRP *)*((_QWORD *)Context + 2);
  v5 = 0;
  if ( v4->Cancel )
  {
    v5 = -1073741536;
    *((_DWORD *)Context + 2) = 0;
  }
  I8xCompleteSysButtonIrp(v4, *((_DWORD *)Context + 2), v5, a4);
  IoFreeWorkItem(*(PIO_WORKITEM *)Context);
  ExFreePoolWithTag(Context, 0);
}

```

## disassembly

```asm
0x14001d150  push    rbx
0x14001d152  sub     rsp, 20h
0x14001d156  mov     rcx, [rdx+10h]; Irp
0x14001d15a  xor     r8d, r8d
0x14001d15d  mov     rbx, rdx
0x14001d160  cmp     [rcx+44h], r8b
0x14001d164  jz      short loc_14001D173
0x14001d166  mov     r8d, 0C0000120h
0x14001d16c  mov     dword ptr [rdx+8], 0
0x14001d173  mov     edx, [rdx+8]
0x14001d176  call    I8xCompleteSysButtonIrp
0x14001d17b  mov     rcx, [rbx]; IoWorkItem
0x14001d17e  call    cs:__imp_IoFreeWorkItem
0x14001d185  nop     dword ptr [rax+rax+00h]
0x14001d18a  xor     edx, edx; Tag
0x14001d18c  mov     rcx, rbx; P
0x14001d18f  call    cs:__imp_ExFreePoolWithTag
0x14001d196  nop     dword ptr [rax+rax+00h]
0x14001d19b  add     rsp, 20h
0x14001d19f  pop     rbx
0x14001d1a0  retn
```
