# PmIoctlDeleteSpacesMetadata(_DEVICE_OBJECT *,_IRP *)

- ea: `0x14001d830`
- end: `0x14001d88b`
- name: `?PmIoctlDeleteSpacesMetadata@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z`
- size: `91`
- prototype: `__int64 __fastcall(struct _DEVICE_OBJECT *, struct _IRP *)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1400068b0`

## callees

- `0x1400221e4`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x14001d856`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001d856`
- `ntoskrnl!KeReleaseMutex` at `0x14001d871`
- `ntoskrnl!KeReleaseMutex` at `0x14001d871`

## pseudocode

```c
__int64 __fastcall PmIoctlDeleteSpacesMetadata(struct _DEVICE_OBJECT *a1, struct _IRP *a2)
{
  char *DeviceExtension; // rbx
  int v3; // eax
  struct _KMUTANT *v4; // rcx

  DeviceExtension = (char *)a1->DeviceExtension;
  KeWaitForSingleObject(DeviceExtension + 56, Executive, 0, 0, 0);
  v3 = PmDeleteSpacesMetadata((struct _DEVICE_EXTENSION *)DeviceExtension);
  v4 = (struct _KMUTANT *)(DeviceExtension + 56);
  LODWORD(DeviceExtension) = v3;
  KeReleaseMutex(v4, 0);
  return (unsigned int)DeviceExtension;
}

```

## disassembly

```asm
0x14001d830  mov     [rsp+arg_0], rbx
0x14001d835  push    rdi
0x14001d836  sub     rsp, 30h
0x14001d83a  mov     rbx, [rcx+40h]
0x14001d83e  xor     r9d, r9d; Alertable
0x14001d841  xor     r8d, r8d; WaitMode
0x14001d844  mov     [rsp+38h+Timeout], 0; Timeout
0x14001d84d  xor     edx, edx; WaitReason
0x14001d84f  lea     rdi, [rbx+38h]
0x14001d853  mov     rcx, rdi; Object
0x14001d856  call    cs:__imp_KeWaitForSingleObject
0x14001d85d  nop     dword ptr [rax+rax+00h]
0x14001d862  mov     rcx, rbx; struct _DEVICE_EXTENSION *
0x14001d865  call    ?PmDeleteSpacesMetadata@@YAJPEAU_DEVICE_EXTENSION@@@Z; PmDeleteSpacesMetadata(_DEVICE_EXTENSION *)
0x14001d86a  xor     edx, edx; Wait
0x14001d86c  mov     rcx, rdi; Mutex
0x14001d86f  mov     ebx, eax
0x14001d871  call    cs:__imp_KeReleaseMutex
0x14001d878  nop     dword ptr [rax+rax+00h]
0x14001d87d  mov     eax, ebx
0x14001d87f  mov     rbx, [rsp+38h+arg_0]
0x14001d884  add     rsp, 30h
0x14001d888  pop     rdi
0x14001d889  retn
```
