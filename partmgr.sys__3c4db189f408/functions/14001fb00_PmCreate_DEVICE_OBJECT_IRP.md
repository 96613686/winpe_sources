# PmCreate(_DEVICE_OBJECT *,_IRP *)

- ea: `0x14001fb00`
- end: `0x14001fb3d`
- name: `?PmCreate@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z`
- size: `61`
- prototype: `int(struct _DEVICE_OBJECT *, struct _IRP *)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14001fb28`
- `ntoskrnl!IofCompleteRequest` at `0x14001fb28`

## pseudocode

```c
__int64 __fastcall PmCreate(struct _DEVICE_OBJECT *a1, struct _IRP *a2)
{
  unsigned int v2; // ebx

  v2 = (a2->Tail.Overlay.CurrentStackLocation->Parameters.Create.Options & 1) != 0 ? 0xC0000103 : 0;
  a2->IoStatus.Status = v2;
  IofCompleteRequest(a2, 0);
  return v2;
}

```

## disassembly

```asm
0x14001fb00  push    rbx
0x14001fb02  sub     rsp, 20h
0x14001fb06  mov     rax, [rdx+0B8h]
0x14001fb0d  mov     r8, rdx
0x14001fb10  mov     ecx, [rax+10h]
0x14001fb13  and     cl, 1
0x14001fb16  neg     cl
0x14001fb18  mov     rcx, r8; Irp
0x14001fb1b  sbb     ebx, ebx
0x14001fb1d  and     ebx, 0C0000103h
0x14001fb23  mov     [rdx+30h], ebx
0x14001fb26  xor     edx, edx; PriorityBoost
0x14001fb28  call    cs:__imp_IofCompleteRequest
0x14001fb2f  nop     dword ptr [rax+rax+00h]
0x14001fb34  mov     eax, ebx
0x14001fb36  add     rsp, 20h
0x14001fb3a  pop     rbx
0x14001fb3b  retn
```
