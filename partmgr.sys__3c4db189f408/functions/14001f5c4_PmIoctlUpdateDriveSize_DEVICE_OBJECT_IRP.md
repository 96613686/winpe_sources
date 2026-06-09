# PmIoctlUpdateDriveSize(_DEVICE_OBJECT *,_IRP *)

- ea: `0x14001f5c4`
- end: `0x14001f649`
- name: `?PmIoctlUpdateDriveSize@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z`
- size: `133`
- prototype: `__int64 __fastcall(struct _DEVICE_OBJECT *, struct _IRP *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x1400068b0`

## callees

- `0x140007bcc`
- `0x14000cb34`
- `0x14001f5c4`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x14001f606`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001f606`
- `ntoskrnl!IoForwardIrpSynchronously` at `0x14001f5de`
- `ntoskrnl!IoForwardIrpSynchronously` at `0x14001f5de`
- `ntoskrnl!KeReleaseMutex` at `0x14001f62a`
- `ntoskrnl!KeReleaseMutex` at `0x14001f62a`

## pseudocode

```c
__int64 __fastcall PmIoctlUpdateDriveSize(struct _DEVICE_OBJECT *a1, struct _IRP *a2)
{
  char *DeviceExtension; // rsi
  NTSTATUS Status; // edi

  DeviceExtension = (char *)a1->DeviceExtension;
  IoForwardIrpSynchronously(*((PDEVICE_OBJECT *)DeviceExtension + 2), a2);
  Status = a2->IoStatus.Status;
  if ( Status >= 0 )
  {
    KeWaitForSingleObject(DeviceExtension + 56, Executive, 0, 0, 0);
    PmInvalidatePartitionTableCache((KSPIN_LOCK *)DeviceExtension);
    PmGetDriveLayoutEx((KSPIN_LOCK *)DeviceExtension, 0);
    KeReleaseMutex((PRKMUTEX)DeviceExtension + 1, 0);
  }
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x14001f5c4  mov     [rsp+arg_0], rbx
0x14001f5c9  mov     [rsp+arg_8], rsi
0x14001f5ce  push    rdi
0x14001f5cf  sub     rsp, 30h
0x14001f5d3  mov     rsi, [rcx+40h]
0x14001f5d7  mov     rbx, rdx
0x14001f5da  mov     rcx, [rsi+10h]; DeviceObject
0x14001f5de  call    cs:__imp_IoForwardIrpSynchronously
0x14001f5e5  nop     dword ptr [rax+rax+00h]
0x14001f5ea  mov     edi, [rbx+30h]
0x14001f5ed  test    edi, edi
0x14001f5ef  js      short loc_14001F636
0x14001f5f1  xor     r9d, r9d; Alertable
0x14001f5f4  mov     [rsp+38h+Timeout], 0; Timeout
0x14001f5fd  xor     r8d, r8d; WaitMode
0x14001f600  lea     rcx, [rsi+38h]; Object
0x14001f604  xor     edx, edx; WaitReason
0x14001f606  call    cs:__imp_KeWaitForSingleObject
0x14001f60d  nop     dword ptr [rax+rax+00h]
0x14001f612  mov     rcx, rsi; struct _DEVICE_EXTENSION *
0x14001f615  call    ?PmInvalidatePartitionTableCache@@YAXPEAU_DEVICE_EXTENSION@@@Z; PmInvalidatePartitionTableCache(_DEVICE_EXTENSION *)
0x14001f61a  xor     edx, edx; struct _DRIVE_LAYOUT_INFORMATION_EX **
0x14001f61c  mov     rcx, rsi; struct _DEVICE_EXTENSION *
0x14001f61f  call    ?PmGetDriveLayoutEx@@YAJPEAU_DEVICE_EXTENSION@@PEAPEAU_DRIVE_LAYOUT_INFORMATION_EX@@@Z; PmGetDriveLayoutEx(_DEVICE_EXTENSION *,_DRIVE_LAYOUT_INFORMATION_EX * *)
0x14001f624  xor     edx, edx; Wait
0x14001f626  lea     rcx, [rsi+38h]; Mutex
0x14001f62a  call    cs:__imp_KeReleaseMutex
0x14001f631  nop     dword ptr [rax+rax+00h]
0x14001f636  mov     rbx, [rsp+38h+arg_0]
0x14001f63b  mov     eax, edi
0x14001f63d  mov     rsi, [rsp+38h+arg_8]
0x14001f642  add     rsp, 30h
0x14001f646  pop     rdi
0x14001f647  retn
```
