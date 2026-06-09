# CddCreateClose(_DEVICE_OBJECT *,_IRP *)

- ea: `0x140029d90`
- end: `0x140029dbc`
- name: `?CddCreateClose@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z`
- size: `44`
- prototype: `int(struct _DEVICE_OBJECT *, struct _IRP *)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140029da8`
- `ntoskrnl!IofCompleteRequest` at `0x140029da8`

## pseudocode

```c
__int64 __fastcall CddCreateClose(struct _DEVICE_OBJECT *a1, struct _IRP *a2)
{
  a2->IoStatus.Information = 0;
  a2->IoStatus.Status = 0;
  IofCompleteRequest(a2, 0);
  return 0;
}

```

## disassembly

```asm
0x140029d90  sub     rsp, 28h
0x140029d94  mov     rcx, rdx; Irp
0x140029d97  mov     qword ptr [rdx+38h], 0
0x140029d9f  mov     dword ptr [rdx+30h], 0
0x140029da6  xor     edx, edx; PriorityBoost
0x140029da8  call    cs:__imp_IofCompleteRequest
0x140029daf  nop     dword ptr [rax+rax+00h]
0x140029db4  xor     eax, eax
0x140029db6  add     rsp, 28h
0x140029dba  retn
```
