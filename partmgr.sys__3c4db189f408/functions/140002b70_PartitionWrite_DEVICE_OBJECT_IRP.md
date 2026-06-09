# PartitionWrite(_DEVICE_OBJECT *,_IRP *)

- ea: `0x140002b70`
- end: `0x140002bc0`
- name: `?PartitionWrite@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z`
- size: `80`
- prototype: `__int64 __fastcall(struct _DEVICE_OBJECT *, struct _IRP *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140002b70`
- `0x140002bd0`
- `0x14000ae88`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140002bad`
- `ntoskrnl!IofCompleteRequest` at `0x140002bad`

## pseudocode

```c
__int64 __fastcall PartitionWrite(struct _DEVICE_OBJECT *a1, struct _IRP *a2)
{
  struct _IRP *v2; // rdx
  struct _DEVICE_OBJECT *v3; // r8
  IRP *v4; // r9

  if ( (ScReadNoFence((unsigned int *)a1->DeviceExtension + 10) & 8) == 0 )
    return PartitionIo(v3, v2);
  v2->IoStatus.Information = 0;
  v2->IoStatus.Status = -1073741810;
  IofCompleteRequest(v4, 0);
  return 3221225486LL;
}

```

## disassembly

```asm
0x140002b70  sub     rsp, 28h
0x140002b74  mov     r8, rcx
0x140002b77  mov     r9, rdx
0x140002b7a  mov     rcx, [rcx+40h]
0x140002b7e  add     rcx, 28h ; '('; unsigned int *
0x140002b82  call    ?ScReadNoFence@@YAKPEAK@Z; ScReadNoFence(ulong *)
0x140002b87  test    al, 8
0x140002b89  jnz     short loc_140002B99
0x140002b8b  mov     rcx, r8; struct _DEVICE_OBJECT *
0x140002b8e  call    ?PartitionIo@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z; PartitionIo(_DEVICE_OBJECT *,_IRP *)
0x140002b93  add     rsp, 28h
0x140002b97  retn
0x140002b99  mov     qword ptr [rdx+38h], 0
0x140002ba1  mov     rcx, r9; Irp
0x140002ba4  mov     dword ptr [rdx+30h], 0C000000Eh
0x140002bab  xor     edx, edx; PriorityBoost
0x140002bad  call    cs:__imp_IofCompleteRequest
0x140002bb4  nop     dword ptr [rax+rax+00h]
0x140002bb9  mov     eax, 0C000000Eh
0x140002bbe  jmp     short loc_140002B93
```
