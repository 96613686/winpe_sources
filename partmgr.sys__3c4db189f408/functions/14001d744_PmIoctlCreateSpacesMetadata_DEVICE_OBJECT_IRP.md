# PmIoctlCreateSpacesMetadata(_DEVICE_OBJECT *,_IRP *)

- ea: `0x14001d744`
- end: `0x14001d7c5`
- name: `?PmIoctlCreateSpacesMetadata@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z`
- size: `129`
- prototype: `__int64 __fastcall(struct _DEVICE_OBJECT *, struct _IRP *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1400068b0`

## callees

- `0x14001d744`
- `0x14002208c`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x14001d787`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001d787`
- `ntoskrnl!KeReleaseMutex` at `0x14001d7a6`
- `ntoskrnl!KeReleaseMutex` at `0x14001d7a6`

## pseudocode

```c
__int64 __fastcall PmIoctlCreateSpacesMetadata(struct _DEVICE_OBJECT *a1, struct _IRP *a2)
{
  unsigned int SpacesMetadata; // ebx
  char *DeviceExtension; // rdi
  struct _DISK_SPACES_METADATA *MasterIrp; // rbx

  if ( a2->Tail.Overlay.CurrentStackLocation->Parameters.Create.Options >= 0x260 )
  {
    DeviceExtension = (char *)a1->DeviceExtension;
    MasterIrp = (struct _DISK_SPACES_METADATA *)a2->AssociatedIrp.MasterIrp;
    KeWaitForSingleObject(DeviceExtension + 56, Executive, 0, 0, 0);
    SpacesMetadata = PmCreateSpacesMetadata((struct _DEVICE_EXTENSION *)DeviceExtension, MasterIrp);
    KeReleaseMutex((PRKMUTEX)DeviceExtension + 1, 0);
  }
  else
  {
    return (unsigned int)-1073741820;
  }
  return SpacesMetadata;
}

```

## disassembly

```asm
0x14001d744  mov     [rsp+arg_0], rbx
0x14001d749  mov     [rsp+arg_8], rsi
0x14001d74e  push    rdi
0x14001d74f  sub     rsp, 30h
0x14001d753  mov     rax, [rdx+0B8h]
0x14001d75a  cmp     dword ptr [rax+10h], 260h
0x14001d761  jnb     short loc_14001D76A
0x14001d763  mov     ebx, 0C0000004h
0x14001d768  jmp     short loc_14001D7B2
0x14001d76a  mov     rdi, [rcx+40h]
0x14001d76e  xor     r9d, r9d; Alertable
0x14001d771  mov     rbx, [rdx+18h]
0x14001d775  xor     r8d, r8d; WaitMode
0x14001d778  xor     edx, edx; WaitReason
0x14001d77a  mov     [rsp+38h+Timeout], 0; Timeout
0x14001d783  lea     rcx, [rdi+38h]; Object
0x14001d787  call    cs:__imp_KeWaitForSingleObject
0x14001d78e  nop     dword ptr [rax+rax+00h]
0x14001d793  mov     rdx, rbx; struct _DISK_SPACES_METADATA *
0x14001d796  mov     rcx, rdi; struct _DEVICE_EXTENSION *
0x14001d799  call    ?PmCreateSpacesMetadata@@YAJPEAU_DEVICE_EXTENSION@@PEAU_DISK_SPACES_METADATA@@@Z; PmCreateSpacesMetadata(_DEVICE_EXTENSION *,_DISK_SPACES_METADATA *)
0x14001d79e  xor     edx, edx; Wait
0x14001d7a0  lea     rcx, [rdi+38h]; Mutex
0x14001d7a4  mov     ebx, eax
0x14001d7a6  call    cs:__imp_KeReleaseMutex
0x14001d7ad  nop     dword ptr [rax+rax+00h]
0x14001d7b2  mov     rsi, [rsp+38h+arg_8]
0x14001d7b7  mov     eax, ebx
0x14001d7b9  mov     rbx, [rsp+38h+arg_0]
0x14001d7be  add     rsp, 30h
0x14001d7c2  pop     rdi
0x14001d7c3  retn
```
