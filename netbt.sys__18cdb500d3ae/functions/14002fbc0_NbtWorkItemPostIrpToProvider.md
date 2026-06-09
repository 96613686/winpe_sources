# NbtWorkItemPostIrpToProvider

- ea: `0x14002fbc0`
- end: `0x14002fc9b`
- name: `NbtWorkItemPostIrpToProvider`
- size: `219`
- prototype: `IO_WORKITEM_ROUTINE`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x140006878`
- `0x140013184`
- `0x14002fbc0`

## import_xrefs

- `ntoskrnl!IofCallDriver` at `0x14002fc41`
- `ntoskrnl!IofCallDriver` at `0x14002fc41`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x14002fc2f`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x14002fc2f`
- `ntoskrnl!IoFreeWorkItem` at `0x14002fbd9`
- `ntoskrnl!IoFreeWorkItem` at `0x14002fbd9`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002fbec`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002fbec`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002fc20`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002fc54`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002fc20`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002fc54`

## pseudocode

```c
void __fastcall NbtWorkItemPostIrpToProvider(PDEVICE_OBJECT DeviceObject, char *Context)
{
  KSPIN_LOCK *v3; // rdi
  KIRQL v4; // al
  bool v5; // zf
  IRP *v6; // rsi
  struct _FILE_OBJECT *v7; // rbx
  struct _DEVICE_OBJECT *RelatedDeviceObject; // rax
  __int64 v9; // rdx
  __int64 v10; // r8

  IoFreeWorkItem(*((PIO_WORKITEM *)Context + 28));
  v3 = (KSPIN_LOCK *)(Context + 104);
  v4 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)Context + 13);
  v5 = *((_QWORD *)Context + 3) == 0;
  v6 = (IRP *)*((_QWORD *)Context + 27);
  *((_QWORD *)Context + 28) = 0;
  if ( v5 || *((_DWORD *)Context + 22) != 7 )
  {
    KeReleaseSpinLock((PKSPIN_LOCK)Context + 13, v4);
    v6->MdlAddress = 0;
    NbtFreeIrp(v6);
    NbtDereferenceLowerConnection((__int64)Context, v9, v10, 49, (__int64)"minio\\netbt\\sys\\nt\\tdihndlr.c");
  }
  else
  {
    v7 = (struct _FILE_OBJECT *)*((_QWORD *)Context + 6);
    KeReleaseSpinLock(v3, v4);
    RelatedDeviceObject = IoGetRelatedDeviceObject(v7);
    IofCallDriver(RelatedDeviceObject, v6);
  }
}

```

## disassembly

```asm
0x14002fbc0  mov     [rsp+arg_0], rbx
0x14002fbc5  mov     [rsp+arg_8], rsi
0x14002fbca  push    rdi
0x14002fbcb  sub     rsp, 30h
0x14002fbcf  mov     rcx, [rdx+0E0h]; IoWorkItem
0x14002fbd6  mov     rbx, rdx
0x14002fbd9  call    cs:__imp_IoFreeWorkItem
0x14002fbe0  nop     dword ptr [rax+rax+00h]
0x14002fbe5  lea     rdi, [rbx+68h]
0x14002fbe9  mov     rcx, rdi; SpinLock
0x14002fbec  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14002fbf3  nop     dword ptr [rax+rax+00h]
0x14002fbf8  cmp     qword ptr [rbx+18h], 0
0x14002fbfd  mov     rsi, [rbx+0D8h]
0x14002fc04  mov     qword ptr [rbx+0E0h], 0
0x14002fc0f  jz      short loc_14002FC4F
0x14002fc11  cmp     dword ptr [rbx+58h], 7
0x14002fc15  jnz     short loc_14002FC4F
0x14002fc17  mov     rbx, [rbx+30h]
0x14002fc1b  mov     dl, al; NewIrql
0x14002fc1d  mov     rcx, rdi; SpinLock
0x14002fc20  call    cs:__imp_KeReleaseSpinLock
0x14002fc27  nop     dword ptr [rax+rax+00h]
0x14002fc2c  mov     rcx, rbx; FileObject
0x14002fc2f  call    cs:__imp_IoGetRelatedDeviceObject
0x14002fc36  nop     dword ptr [rax+rax+00h]
0x14002fc3b  mov     rcx, rax; DeviceObject
0x14002fc3e  mov     rdx, rsi; Irp
0x14002fc41  call    cs:__imp_IofCallDriver
0x14002fc48  nop     dword ptr [rax+rax+00h]
0x14002fc4d  jmp     short loc_14002FC8A
0x14002fc4f  mov     dl, al; NewIrql
0x14002fc51  mov     rcx, rdi; SpinLock
0x14002fc54  call    cs:__imp_KeReleaseSpinLock
0x14002fc5b  nop     dword ptr [rax+rax+00h]
0x14002fc60  mov     rcx, rsi; Irp
0x14002fc63  mov     qword ptr [rsi+8], 0
0x14002fc6b  call    NbtFreeIrp
0x14002fc70  lea     rax, aMinioNetbtSysN_2; "minio\\netbt\\sys\\nt\\tdihndlr.c"
0x14002fc77  mov     r9d, 231h
0x14002fc7d  mov     rcx, rbx
0x14002fc80  mov     [rsp+38h+var_18], rax
0x14002fc85  call    NbtDereferenceLowerConnection
0x14002fc8a  mov     rbx, [rsp+38h+arg_0]
0x14002fc8f  mov     rsi, [rsp+38h+arg_8]
0x14002fc94  add     rsp, 30h
0x14002fc98  pop     rdi
0x14002fc99  retn
```
