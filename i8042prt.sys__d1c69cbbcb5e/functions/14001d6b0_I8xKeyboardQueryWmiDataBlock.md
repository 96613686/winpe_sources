# I8xKeyboardQueryWmiDataBlock

- ea: `0x14001d6b0`
- end: `0x14001d788`
- name: `I8xKeyboardQueryWmiDataBlock`
- size: `216`
- prototype: `__int64 __usercall@<rax>(PDEVICE_OBJECT DeviceObject@<rcx>, PIRP Irp@<rdx>, int, __int64, int, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x14001d6b0`

## import_xrefs

- `WMILIB!WmiCompleteRequest` at `0x14001d76b`
- `WMILIB!WmiCompleteRequest` at `0x14001d76b`

## pseudocode

```c
NTSTATUS __fastcall I8xKeyboardQueryWmiDataBlock(
        PDEVICE_OBJECT DeviceObject,
        PIRP Irp,
        int a3,
        __int64 a4,
        int a5,
        ULONG *a6,
        unsigned int a7,
        __int64 a8)
{
  unsigned __int16 *DeviceExtension; // r11
  ULONG v9; // r9d
  NTSTATUS v10; // r8d
  int v11; // r8d
  unsigned int v12; // kr00_4
  int v13; // eax

  DeviceExtension = (unsigned __int16 *)DeviceObject->DeviceExtension;
  if ( !a3 )
  {
    v9 = 20;
    if ( a7 >= 0x14 )
    {
      v11 = DeviceExtension[347];
      v12 = *((_DWORD *)DeviceExtension + 175);
      v13 = DeviceExtension[346];
      *(_DWORD *)a8 = 0;
      *(_QWORD *)(a8 + 4) = v12 / 0xC;
      *(_DWORD *)(a8 + 12) = v13;
      *(_DWORD *)(a8 + 16) = v11;
      goto LABEL_9;
    }
LABEL_7:
    v10 = -1073741789;
    return WmiCompleteRequest(DeviceObject, Irp, v10, v9, 0);
  }
  if ( a3 == 1 )
  {
    v9 = 8;
    if ( a7 >= 8 )
    {
      *(_QWORD *)a8 = *(_QWORD *)(DeviceExtension + 358);
LABEL_9:
      v10 = 0;
      *a6 = v9;
      return WmiCompleteRequest(DeviceObject, Irp, v10, v9, 0);
    }
    goto LABEL_7;
  }
  v9 = 0;
  v10 = -1073741163;
  return WmiCompleteRequest(DeviceObject, Irp, v10, v9, 0);
}

```

## disassembly

```asm
0x14001d6b0  mov     [rsp+arg_10], rbx
0x14001d6b5  mov     [rsp+arg_18], rsi
0x14001d6ba  push    rdi
0x14001d6bb  sub     rsp, 30h
0x14001d6bf  mov     r10, [rsp+38h+arg_38]
0x14001d6c4  mov     rsi, rdx
0x14001d6c7  mov     rbx, [rsp+38h+arg_28]
0x14001d6cc  mov     rdi, rcx
0x14001d6cf  mov     r11, [rcx+40h]
0x14001d6d3  test    r8d, r8d
0x14001d6d6  jz      short loc_14001D702
0x14001d6d8  cmp     r8d, 1
0x14001d6dc  jz      short loc_14001D6E9
0x14001d6de  xor     r9d, r9d
0x14001d6e1  mov     r8d, 0C0000295h
0x14001d6e7  jmp     short loc_14001D760
0x14001d6e9  mov     r9d, 8
0x14001d6ef  cmp     [rsp+38h+arg_30], r9d
0x14001d6f4  jb      short loc_14001D70F
0x14001d6f6  mov     rax, [r11+2CCh]
0x14001d6fd  mov     [r10], rax
0x14001d700  jmp     short loc_14001D75A
0x14001d702  mov     r9d, 14h; BufferUsed
0x14001d708  cmp     [rsp+38h+arg_30], r9d
0x14001d70d  jnb     short loc_14001D717
0x14001d70f  mov     r8d, 0C0000023h
0x14001d715  jmp     short loc_14001D760
0x14001d717  mov     ecx, [r11+2BCh]
0x14001d71e  mov     rax, 0AAAAAAAAAAAAAAABh
0x14001d728  movzx   r8d, word ptr [r11+2B6h]
0x14001d730  mul     rcx
0x14001d733  movzx   eax, word ptr [r11+2B4h]
0x14001d73b  mov     dword ptr [r10], 0
0x14001d742  shr     rdx, 3
0x14001d746  mov     [r10+4], edx
0x14001d74a  mov     dword ptr [r10+8], 0
0x14001d752  mov     [r10+0Ch], eax
0x14001d756  mov     [r10+10h], r8d
0x14001d75a  xor     r8d, r8d; Status
0x14001d75d  mov     [rbx], r9d
0x14001d760  mov     rdx, rsi; Irp
0x14001d763  mov     [rsp+38h+PriorityBoost], 0; PriorityBoost
0x14001d768  mov     rcx, rdi; DeviceObject
0x14001d76b  call    cs:__imp_WmiCompleteRequest
0x14001d772  nop     dword ptr [rax+rax+00h]
0x14001d777  mov     rbx, [rsp+38h+arg_10]
0x14001d77c  mov     rsi, [rsp+38h+arg_18]
0x14001d781  add     rsp, 30h
0x14001d785  pop     rdi
0x14001d786  retn
```
