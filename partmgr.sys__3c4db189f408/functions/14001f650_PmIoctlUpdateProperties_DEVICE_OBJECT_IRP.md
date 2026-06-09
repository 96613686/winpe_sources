# PmIoctlUpdateProperties(_DEVICE_OBJECT *,_IRP *)

- ea: `0x14001f650`
- end: `0x14001f6b1`
- name: `?PmIoctlUpdateProperties@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z`
- size: `97`
- prototype: `__int64 __fastcall(struct _DEVICE_OBJECT *, struct _IRP *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x1400068b0`

## callees

- `0x140007bcc`
- `0x14000cb34`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x14001f673`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001f673`
- `ntoskrnl!KeReleaseMutex` at `0x14001f697`
- `ntoskrnl!KeReleaseMutex` at `0x14001f697`

## pseudocode

```c
__int64 __fastcall PmIoctlUpdateProperties(struct _DEVICE_OBJECT *a1, struct _IRP *a2)
{
  char *DeviceExtension; // rbx

  DeviceExtension = (char *)a1->DeviceExtension;
  KeWaitForSingleObject(DeviceExtension + 56, Executive, 0, 0, 0);
  PmInvalidatePartitionTableCache((struct _DEVICE_EXTENSION *)DeviceExtension);
  PmGetDriveLayoutEx((KSPIN_LOCK *)DeviceExtension, 0);
  KeReleaseMutex((PRKMUTEX)DeviceExtension + 1, 0);
  return 0;
}

```

## disassembly

```asm
0x14001f650  mov     [rsp+arg_0], rbx
0x14001f655  push    rdi
0x14001f656  sub     rsp, 30h
0x14001f65a  mov     rbx, [rcx+40h]
0x14001f65e  xor     r9d, r9d; Alertable
0x14001f661  xor     r8d, r8d; WaitMode
0x14001f664  mov     [rsp+38h+Timeout], 0; Timeout
0x14001f66d  xor     edx, edx; WaitReason
0x14001f66f  lea     rcx, [rbx+38h]; Object
0x14001f673  call    cs:__imp_KeWaitForSingleObject
0x14001f67a  nop     dword ptr [rax+rax+00h]
0x14001f67f  mov     rcx, rbx; struct _DEVICE_EXTENSION *
0x14001f682  call    ?PmInvalidatePartitionTableCache@@YAXPEAU_DEVICE_EXTENSION@@@Z; PmInvalidatePartitionTableCache(_DEVICE_EXTENSION *)
0x14001f687  xor     edx, edx; struct _DRIVE_LAYOUT_INFORMATION_EX **
0x14001f689  mov     rcx, rbx; struct _DEVICE_EXTENSION *
0x14001f68c  call    ?PmGetDriveLayoutEx@@YAJPEAU_DEVICE_EXTENSION@@PEAPEAU_DRIVE_LAYOUT_INFORMATION_EX@@@Z; PmGetDriveLayoutEx(_DEVICE_EXTENSION *,_DRIVE_LAYOUT_INFORMATION_EX * *)
0x14001f691  xor     edx, edx; Wait
0x14001f693  lea     rcx, [rbx+38h]; Mutex
0x14001f697  call    cs:__imp_KeReleaseMutex
0x14001f69e  nop     dword ptr [rax+rax+00h]
0x14001f6a3  mov     rbx, [rsp+38h+arg_0]
0x14001f6a8  xor     eax, eax
0x14001f6aa  add     rsp, 30h
0x14001f6ae  pop     rdi
0x14001f6af  retn
```
