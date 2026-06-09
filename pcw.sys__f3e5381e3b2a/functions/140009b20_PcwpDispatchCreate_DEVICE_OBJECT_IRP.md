# PcwpDispatchCreate(_DEVICE_OBJECT *,_IRP *)

- ea: `0x140009b20`
- end: `0x140009b4c`
- name: `?PcwpDispatchCreate@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z`
- size: `44`
- prototype: `int(struct _DEVICE_OBJECT *, struct _IRP *)`
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140009b38`
- `ntoskrnl!IofCompleteRequest` at `0x140009b38`

## pseudocode

```c
__int64 __fastcall PcwpDispatchCreate(struct _DEVICE_OBJECT *a1, struct _IRP *a2)
{
  a2->IoStatus.Status = 0;
  a2->IoStatus.Information = 0;
  IofCompleteRequest(a2, 0);
  return 0;
}

```

## disassembly

```asm
0x140009b20  sub     rsp, 28h
0x140009b24  mov     rcx, rdx; Irp
0x140009b27  mov     dword ptr [rdx+30h], 0
0x140009b2e  mov     qword ptr [rdx+38h], 0
0x140009b36  xor     edx, edx; PriorityBoost
0x140009b38  call    cs:__imp_IofCompleteRequest
0x140009b3f  nop     dword ptr [rax+rax+00h]
0x140009b44  xor     eax, eax
0x140009b46  add     rsp, 28h
0x140009b4a  retn
```
