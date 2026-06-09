# KbdHid_QueryWmiDataBlock

- ea: `0x140010c30`
- end: `0x140010ce7`
- name: `KbdHid_QueryWmiDataBlock`
- size: `183`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140010c30`

## import_xrefs

- `WMILIB!WmiCompleteRequest` at `0x140010ccf`
- `WMILIB!WmiCompleteRequest` at `0x140010ccf`

## pseudocode

```c
NTSTATUS __fastcall KbdHid_QueryWmiDataBlock(
        struct _DEVICE_OBJECT *a1,
        IRP *a2,
        int a3,
        __int64 a4,
        __int64 a5,
        ULONG *a6,
        unsigned int a7,
        __int64 a8)
{
  _DWORD *DeviceExtension; // r11
  ULONG v9; // r9d
  NTSTATUS v10; // r8d
  unsigned int v11; // eax
  int v12; // r10d
  int v13; // r11d

  DeviceExtension = a1->DeviceExtension;
  if ( !a3 )
  {
    v9 = 20;
    if ( a7 >= 0x14 )
    {
      v11 = DeviceExtension[73];
      v10 = 0;
      v12 = *((unsigned __int16 *)DeviceExtension + 142);
      v13 = *((unsigned __int16 *)DeviceExtension + 143);
      *(_DWORD *)a8 = 2;
      *(_QWORD *)(a8 + 4) = v11;
      *(_DWORD *)(a8 + 12) = v12;
      *(_DWORD *)(a8 + 16) = v13;
      goto LABEL_9;
    }
LABEL_7:
    v10 = -1073741789;
    return WmiCompleteRequest(a1, a2, v10, v9, 0);
  }
  if ( a3 == 1 )
  {
    v9 = 8;
    if ( a7 >= 8 )
    {
      v10 = 0;
      *(_QWORD *)a8 = *((_QWORD *)DeviceExtension + 43);
LABEL_9:
      *a6 = v9;
      return WmiCompleteRequest(a1, a2, v10, v9, 0);
    }
    goto LABEL_7;
  }
  v9 = 0;
  v10 = -1073741163;
  return WmiCompleteRequest(a1, a2, v10, v9, 0);
}

```

## disassembly

```asm
0x140010c30  mov     [rsp+arg_10], rbx
0x140010c35  push    rdi
0x140010c36  sub     rsp, 30h
0x140010c3a  mov     rbx, [rsp+38h+arg_28]
0x140010c3f  mov     rdi, rdx
0x140010c42  mov     rdx, [rsp+38h+arg_38]
0x140010c47  mov     r11, [rcx+40h]
0x140010c4b  test    r8d, r8d
0x140010c4e  jz      short loc_140010C80
0x140010c50  cmp     r8d, 1
0x140010c54  jz      short loc_140010C64
0x140010c56  xor     r8d, r8d
0x140010c59  mov     r9d, r8d
0x140010c5c  mov     r8d, 0C0000295h
0x140010c62  jmp     short loc_140010CC7
0x140010c64  mov     r9d, 8
0x140010c6a  cmp     [rsp+38h+arg_30], r9d
0x140010c6f  jb      short loc_140010C8D
0x140010c71  mov     rax, [r11+158h]
0x140010c78  xor     r8d, r8d
0x140010c7b  mov     [rdx], rax
0x140010c7e  jmp     short loc_140010CC4
0x140010c80  mov     r9d, 14h; BufferUsed
0x140010c86  cmp     [rsp+38h+arg_30], r9d
0x140010c8b  jnb     short loc_140010C95
0x140010c8d  mov     r8d, 0C0000023h
0x140010c93  jmp     short loc_140010CC7
0x140010c95  mov     eax, [r11+124h]
0x140010c9c  xor     r8d, r8d; Status
0x140010c9f  movzx   r10d, word ptr [r11+11Ch]
0x140010ca7  movzx   r11d, word ptr [r11+11Eh]
0x140010caf  mov     dword ptr [rdx], 2
0x140010cb5  mov     [rdx+4], eax
0x140010cb8  mov     [rdx+8], r8d
0x140010cbc  mov     [rdx+0Ch], r10d
0x140010cc0  mov     [rdx+10h], r11d
0x140010cc4  mov     [rbx], r9d
0x140010cc7  mov     rdx, rdi; Irp
0x140010cca  mov     [rsp+38h+PriorityBoost], 0; PriorityBoost
0x140010ccf  call    cs:__imp_WmiCompleteRequest
0x140010cd6  nop     dword ptr [rax+rax+00h]
0x140010cdb  mov     rbx, [rsp+38h+arg_10]
0x140010ce0  add     rsp, 30h
0x140010ce4  pop     rdi
0x140010ce5  retn
```
