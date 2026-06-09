# PmSurpriseRemoval(_DEVICE_OBJECT *,_IRP *)

- ea: `0x14002579c`
- end: `0x1400257f1`
- name: `?PmSurpriseRemoval@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z`
- size: `85`
- prototype: `int(struct _DEVICE_OBJECT *, struct _IRP *)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140022800`

## callees

- `0x14000743c`

## import_xrefs

- `ntoskrnl!IoForwardIrpSynchronously` at `0x1400257b6`
- `ntoskrnl!IoForwardIrpSynchronously` at `0x1400257b6`
- `ntoskrnl!IofCompleteRequest` at `0x1400257d2`
- `ntoskrnl!IofCompleteRequest` at `0x1400257d2`

## pseudocode

```c
__int64 __fastcall PmSurpriseRemoval(struct _DEVICE_OBJECT *a1, struct _IRP *a2)
{
  PDEVICE_OBJECT *DeviceExtension; // rbx
  unsigned int Status; // edi

  DeviceExtension = (PDEVICE_OBJECT *)a1->DeviceExtension;
  IoForwardIrpSynchronously(DeviceExtension[2], a2);
  Status = a2->IoStatus.Status;
  PmRemoveHelper((struct _DEVICE_EXTENSION *)DeviceExtension);
  IofCompleteRequest(a2, 0);
  return Status;
}

```

## disassembly

```asm
0x14002579c  mov     [rsp+arg_0], rbx
0x1400257a1  mov     [rsp+arg_8], rsi
0x1400257a6  push    rdi
0x1400257a7  sub     rsp, 20h
0x1400257ab  mov     rbx, [rcx+40h]
0x1400257af  mov     rsi, rdx
0x1400257b2  mov     rcx, [rbx+10h]; DeviceObject
0x1400257b6  call    cs:__imp_IoForwardIrpSynchronously
0x1400257bd  nop     dword ptr [rax+rax+00h]
0x1400257c2  mov     edi, [rsi+30h]
0x1400257c5  mov     rcx, rbx; struct _DEVICE_EXTENSION *
0x1400257c8  call    ?PmRemoveHelper@@YAXPEAU_DEVICE_EXTENSION@@@Z; PmRemoveHelper(_DEVICE_EXTENSION *)
0x1400257cd  xor     edx, edx; PriorityBoost
0x1400257cf  mov     rcx, rsi; Irp
0x1400257d2  call    cs:__imp_IofCompleteRequest
0x1400257d9  nop     dword ptr [rax+rax+00h]
0x1400257de  mov     rbx, [rsp+28h+arg_0]
0x1400257e3  mov     eax, edi
0x1400257e5  mov     rsi, [rsp+28h+arg_8]
0x1400257ea  add     rsp, 20h
0x1400257ee  pop     rdi
0x1400257ef  retn
```
