# PmIoctlDeleteDriveLayout(_DEVICE_OBJECT *,_IRP *)

- ea: `0x14001d7cc`
- end: `0x14001d829`
- name: `?PmIoctlDeleteDriveLayout@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z`
- size: `93`
- prototype: `__int64 __fastcall(struct _DEVICE_OBJECT *, struct _IRP *)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1400068b0`

## callees

- `0x1400208c8`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x14001d7f2`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001d7f2`
- `ntoskrnl!KeReleaseMutex` at `0x14001d80f`
- `ntoskrnl!KeReleaseMutex` at `0x14001d80f`

## pseudocode

```c
__int64 __fastcall PmIoctlDeleteDriveLayout(struct _DEVICE_OBJECT *a1, struct _IRP *a2)
{
  char *DeviceExtension; // rbx
  int Disk; // eax
  struct _KMUTANT *v4; // rcx

  DeviceExtension = (char *)a1->DeviceExtension;
  KeWaitForSingleObject(DeviceExtension + 56, Executive, 0, 0, 0);
  Disk = PmCreateDisk((struct _DEVICE_EXTENSION *)DeviceExtension, 0);
  v4 = (struct _KMUTANT *)(DeviceExtension + 56);
  LODWORD(DeviceExtension) = Disk;
  KeReleaseMutex(v4, 0);
  return (unsigned int)DeviceExtension;
}

```

## disassembly

```asm
0x14001d7cc  mov     [rsp+arg_0], rbx
0x14001d7d1  push    rdi
0x14001d7d2  sub     rsp, 30h
0x14001d7d6  mov     rbx, [rcx+40h]
0x14001d7da  xor     r9d, r9d; Alertable
0x14001d7dd  xor     r8d, r8d; WaitMode
0x14001d7e0  mov     [rsp+38h+Timeout], 0; Timeout
0x14001d7e9  xor     edx, edx; WaitReason
0x14001d7eb  lea     rdi, [rbx+38h]
0x14001d7ef  mov     rcx, rdi; Object
0x14001d7f2  call    cs:__imp_KeWaitForSingleObject
0x14001d7f9  nop     dword ptr [rax+rax+00h]
0x14001d7fe  xor     edx, edx; struct _CREATE_DISK *
0x14001d800  mov     rcx, rbx; struct _DEVICE_EXTENSION *
0x14001d803  call    ?PmCreateDisk@@YAJPEAU_DEVICE_EXTENSION@@PEAU_CREATE_DISK@@@Z; PmCreateDisk(_DEVICE_EXTENSION *,_CREATE_DISK *)
0x14001d808  xor     edx, edx; Wait
0x14001d80a  mov     rcx, rdi; Mutex
0x14001d80d  mov     ebx, eax
0x14001d80f  call    cs:__imp_KeReleaseMutex
0x14001d816  nop     dword ptr [rax+rax+00h]
0x14001d81b  mov     eax, ebx
0x14001d81d  mov     rbx, [rsp+38h+arg_0]
0x14001d822  add     rsp, 30h
0x14001d826  pop     rdi
0x14001d827  retn
```
