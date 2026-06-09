# PmIoctlCreateDisk(_DEVICE_OBJECT *,_IRP *)

- ea: `0x14001d6a4`
- end: `0x14001d73c`
- name: `?PmIoctlCreateDisk@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z`
- size: `152`
- prototype: `__int64 __fastcall(struct _DEVICE_OBJECT *, struct _IRP *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1400068b0`

## callees

- `0x14001d6a4`
- `0x1400208c8`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x14001d705`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001d705`
- `ntoskrnl!IoForwardIrpSynchronously` at `0x14001d6cc`
- `ntoskrnl!IoForwardIrpSynchronously` at `0x14001d6cc`
- `ntoskrnl!KeReleaseMutex` at `0x14001d724`
- `ntoskrnl!KeReleaseMutex` at `0x14001d724`

## pseudocode

```c
__int64 __fastcall PmIoctlCreateDisk(struct _DEVICE_OBJECT *a1, struct _IRP *a2)
{
  char *DeviceExtension; // rsi
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rbp
  NTSTATUS Disk; // ebx
  struct _IRP *MasterIrp; // rbx

  DeviceExtension = (char *)a1->DeviceExtension;
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  if ( *(_DWORD *)(*((_QWORD *)DeviceExtension + 29) + 28LL) != 18
    || (IoForwardIrpSynchronously(*((PDEVICE_OBJECT *)DeviceExtension + 2), a2), Disk = a2->IoStatus.Status, Disk >= 0) )
  {
    if ( CurrentStackLocation->Parameters.Create.Options >= 0x18 )
    {
      MasterIrp = a2->AssociatedIrp.MasterIrp;
      KeWaitForSingleObject(DeviceExtension + 56, Executive, 0, 0, 0);
      Disk = PmCreateDisk((struct _DEVICE_EXTENSION *)DeviceExtension, (struct _CREATE_DISK *)MasterIrp);
      KeReleaseMutex((PRKMUTEX)DeviceExtension + 1, 0);
    }
    else
    {
      return (unsigned int)-1073741820;
    }
  }
  return (unsigned int)Disk;
}

```

## disassembly

```asm
0x14001d6a4  push    rbx
0x14001d6a6  push    rbp
0x14001d6a7  push    rsi
0x14001d6a8  push    rdi
0x14001d6a9  sub     rsp, 38h
0x14001d6ad  mov     rsi, [rcx+40h]
0x14001d6b1  mov     rdi, rdx
0x14001d6b4  mov     rbp, [rdx+0B8h]
0x14001d6bb  mov     rax, [rsi+0E8h]
0x14001d6c2  cmp     dword ptr [rax+1Ch], 12h
0x14001d6c6  jnz     short loc_14001D6DF
0x14001d6c8  mov     rcx, [rsi+10h]; DeviceObject
0x14001d6cc  call    cs:__imp_IoForwardIrpSynchronously
0x14001d6d3  nop     dword ptr [rax+rax+00h]
0x14001d6d8  mov     ebx, [rdi+30h]
0x14001d6db  test    ebx, ebx
0x14001d6dd  js      short loc_14001D730
0x14001d6df  cmp     dword ptr [rbp+10h], 18h
0x14001d6e3  jnb     short loc_14001D6EC
0x14001d6e5  mov     ebx, 0C0000004h
0x14001d6ea  jmp     short loc_14001D730
0x14001d6ec  mov     rbx, [rdi+18h]
0x14001d6f0  lea     rcx, [rsi+38h]; Object
0x14001d6f4  xor     r9d, r9d; Alertable
0x14001d6f7  mov     [rsp+58h+Timeout], 0; Timeout
0x14001d700  xor     r8d, r8d; WaitMode
0x14001d703  xor     edx, edx; WaitReason
0x14001d705  call    cs:__imp_KeWaitForSingleObject
0x14001d70c  nop     dword ptr [rax+rax+00h]
0x14001d711  mov     rdx, rbx; struct _CREATE_DISK *
0x14001d714  mov     rcx, rsi; struct _DEVICE_EXTENSION *
0x14001d717  call    ?PmCreateDisk@@YAJPEAU_DEVICE_EXTENSION@@PEAU_CREATE_DISK@@@Z; PmCreateDisk(_DEVICE_EXTENSION *,_CREATE_DISK *)
0x14001d71c  xor     edx, edx; Wait
0x14001d71e  lea     rcx, [rsi+38h]; Mutex
0x14001d722  mov     ebx, eax
0x14001d724  call    cs:__imp_KeReleaseMutex
0x14001d72b  nop     dword ptr [rax+rax+00h]
0x14001d730  mov     eax, ebx
0x14001d732  add     rsp, 38h
0x14001d736  pop     rdi
0x14001d737  pop     rsi
0x14001d738  pop     rbp
0x14001d739  pop     rbx
0x14001d73a  retn
```
