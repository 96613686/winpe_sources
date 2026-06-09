# MouHid_SetWmiDataItem

- ea: `0x14000c210`
- end: `0x14000c23f`
- name: `MouHid_SetWmiDataItem`
- size: `47`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `WMILIB!WmiCompleteRequest` at `0x14000c22d`
- `WMILIB!WmiCompleteRequest` at `0x14000c22d`

## pseudocode

```c
NTSTATUS __fastcall MouHid_SetWmiDataItem(struct _DEVICE_OBJECT *a1, IRP *a2, int a3)
{
  return WmiCompleteRequest(a1, a2, a3 != 0 ? -1073741163 : -1073741114, 0, 0);
}

```

## disassembly

```asm
0x14000c210  sub     rsp, 38h
0x14000c214  neg     r8d
0x14000c217  mov     [rsp+38h+PriorityBoost], 0; PriorityBoost
0x14000c21c  sbb     r8d, r8d
0x14000c21f  xor     r9d, r9d; BufferUsed
0x14000c222  and     r8d, 0FFFFFFCFh
0x14000c226  add     r8d, 0C00002C6h; Status
0x14000c22d  call    cs:__imp_WmiCompleteRequest
0x14000c234  nop     dword ptr [rax+rax+00h]
0x14000c239  add     rsp, 38h
0x14000c23d  retn
```
