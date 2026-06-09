# PmControlDeviceControl(_DEVICE_OBJECT *,_IRP *)

- ea: `0x14000b890`
- end: `0x14000b8fc`
- name: `?PmControlDeviceControl@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z`
- size: `108`
- prototype: `__int64 __fastcall(struct _DEVICE_OBJECT *, struct _IRP *)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x14000b890`
- `0x14001e110`
- `0x14001f3d8`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14000b8e2`
- `ntoskrnl!IofCompleteRequest` at `0x14000b8e2`

## pseudocode

```c
__int64 __fastcall PmControlDeviceControl(struct _DEVICE_OBJECT *a1, struct _IRP *a2)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  DWORD LowPart; // edx
  unsigned int v5; // edi
  unsigned int SanSettings; // eax

  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  a2->IoStatus.Information = 0;
  LowPart = CurrentStackLocation->Parameters.Read.ByteOffset.LowPart;
  if ( LowPart == 475648 )
  {
    SanSettings = PmIoctlGetSanSettings(a1, a2);
    goto LABEL_6;
  }
  if ( LowPart == 508420 )
  {
    SanSettings = PmIoctlSetSanSettings(a1, a2);
LABEL_6:
    v5 = SanSettings;
    goto LABEL_7;
  }
  v5 = -1073741808;
LABEL_7:
  a2->IoStatus.Status = v5;
  IofCompleteRequest(a2, 0);
  return v5;
}

```

## disassembly

```asm
0x14000b890  mov     [rsp+arg_0], rbx
0x14000b895  push    rdi
0x14000b896  sub     rsp, 20h
0x14000b89a  mov     rax, [rdx+0B8h]
0x14000b8a1  mov     rbx, rdx
0x14000b8a4  mov     qword ptr [rdx+38h], 0
0x14000b8ac  mov     edx, [rax+18h]
0x14000b8af  cmp     edx, 74200h
0x14000b8b5  jz      short loc_14000B8D0
0x14000b8b7  cmp     edx, 7C204h
0x14000b8bd  jz      short loc_14000B8C6
0x14000b8bf  mov     edi, 0C0000010h
0x14000b8c4  jmp     short loc_14000B8DA
0x14000b8c6  mov     rdx, rbx; struct _IRP *
0x14000b8c9  call    ?PmIoctlSetSanSettings@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z; PmIoctlSetSanSettings(_DEVICE_OBJECT *,_IRP *)
0x14000b8ce  jmp     short loc_14000B8D8
0x14000b8d0  mov     rdx, rbx; struct _IRP *
0x14000b8d3  call    ?PmIoctlGetSanSettings@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z; PmIoctlGetSanSettings(_DEVICE_OBJECT *,_IRP *)
0x14000b8d8  mov     edi, eax
0x14000b8da  xor     edx, edx; PriorityBoost
0x14000b8dc  mov     [rbx+30h], edi
0x14000b8df  mov     rcx, rbx; Irp
0x14000b8e2  call    cs:__imp_IofCompleteRequest
0x14000b8e9  nop     dword ptr [rax+rax+00h]
0x14000b8ee  mov     rbx, [rsp+28h+arg_0]
0x14000b8f3  mov     eax, edi
0x14000b8f5  add     rsp, 20h
0x14000b8f9  pop     rdi
0x14000b8fa  retn
```
