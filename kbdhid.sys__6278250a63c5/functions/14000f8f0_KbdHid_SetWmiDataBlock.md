# KbdHid_SetWmiDataBlock

- ea: `0x14000f8f0`
- end: `0x14000f925`
- name: `KbdHid_SetWmiDataBlock`
- size: `53`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x14000f8f0`

## import_xrefs

- `WMILIB!WmiCompleteRequest` at `0x14000f913`
- `WMILIB!WmiCompleteRequest` at `0x14000f913`

## pseudocode

```c
NTSTATUS __fastcall KbdHid_SetWmiDataBlock(struct _DEVICE_OBJECT *a1, IRP *a2, int a3)
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
0x14000f8f0  sub     rsp, 38h
0x14000f8f4  test    r8d, r8d
0x14000f8f7  jz      short loc_14000F905
0x14000f8f9  cmp     r8d, 1
0x14000f8fd  mov     r8d, 0C0000295h
0x14000f903  jnz     short loc_14000F90B
0x14000f905  mov     r8d, 0C00002C6h; Status
0x14000f90b  xor     r9d, r9d; BufferUsed
0x14000f90e  mov     [rsp+38h+PriorityBoost], 0; PriorityBoost
0x14000f913  call    cs:__imp_WmiCompleteRequest
0x14000f91a  nop     dword ptr [rax+rax+00h]
0x14000f91f  add     rsp, 38h
0x14000f923  retn
```
