# I8xSetWmiDataItem

- ea: `0x14001d870`
- end: `0x14001d8a5`
- name: `I8xSetWmiDataItem`
- size: `53`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x14001d870`

## import_xrefs

- `WMILIB!WmiCompleteRequest` at `0x14001d893`
- `WMILIB!WmiCompleteRequest` at `0x14001d893`

## pseudocode

```c
NTSTATUS __fastcall I8xSetWmiDataItem(struct _DEVICE_OBJECT *a1, IRP *a2, int a3)
{
  bool v3; // zf
  NTSTATUS v4; // r8d

  if ( !a3 || (v3 = a3 == 1, v4 = -1073741163, v3) )
    v4 = -1073741114;
  return WmiCompleteRequest(a1, a2, v4, 0, 0);
}

```

## disassembly

```asm
0x14001d870  sub     rsp, 38h
0x14001d874  test    r8d, r8d
0x14001d877  jz      short loc_14001D885
0x14001d879  cmp     r8d, 1
0x14001d87d  mov     r8d, 0C0000295h
0x14001d883  jnz     short loc_14001D88B
0x14001d885  mov     r8d, 0C00002C6h; Status
0x14001d88b  xor     r9d, r9d; BufferUsed
0x14001d88e  mov     [rsp+38h+PriorityBoost], 0; PriorityBoost
0x14001d893  call    cs:__imp_WmiCompleteRequest
0x14001d89a  nop     dword ptr [rax+rax+00h]
0x14001d89f  add     rsp, 38h
0x14001d8a3  retn
```
