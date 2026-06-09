# MouHid_QueryWmiDataBlock

- ea: `0x14000c110`
- end: `0x14000c1cc`
- name: `MouHid_QueryWmiDataBlock`
- size: `188`
- prototype: `__int64 __usercall@<rax>(PDEVICE_OBJECT DeviceObject@<rcx>, PIRP Irp@<rdx>, int, __int64, int, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x14000c110`

## import_xrefs

- `WMILIB!WmiCompleteRequest` at `0x14000c1b4`
- `WMILIB!WmiCompleteRequest` at `0x14000c1b4`

## pseudocode

```c
NTSTATUS __fastcall MouHid_QueryWmiDataBlock(
        PDEVICE_OBJECT DeviceObject,
        PIRP Irp,
        int a3,
        int a4,
        int a5,
        _DWORD *a6,
        unsigned int a7,
        __int64 a8)
{
  ULONG v9; // r9d
  NTSTATUS v11; // r8d
  unsigned int *DeviceExtension; // rcx
  __int128 v14; // [rsp+30h] [rbp-28h]

  v9 = 0;
  if ( a3 )
  {
    v11 = -1073741163;
  }
  else if ( a4 || a5 != 1 )
  {
    v11 = -1073741808;
  }
  else
  {
    v9 = 20;
    if ( a7 >= 0x14 )
    {
      DeviceExtension = (unsigned int *)DeviceObject->DeviceExtension;
      LODWORD(v14) = 2;
      v11 = 0;
      *(_QWORD *)((char *)&v14 + 4) = DeviceExtension[96];
      HIDWORD(v14) = *((unsigned __int16 *)DeviceExtension + 189);
      *(_OWORD *)a8 = v14;
      *(_DWORD *)(a8 + 16) = 0;
      *a6 = 20;
    }
    else
    {
      v11 = -1073741789;
    }
  }
  return WmiCompleteRequest(DeviceObject, Irp, v11, v9, 0);
}

```

## disassembly

```asm
0x14000c110  mov     [rsp+arg_10], rbx
0x14000c115  push    rdi
0x14000c116  sub     rsp, 50h
0x14000c11a  mov     rdi, [rsp+58h+arg_28]
0x14000c122  mov     eax, r9d
0x14000c125  mov     r11, [rsp+58h+arg_38]
0x14000c12d  xor     r9d, r9d; BufferUsed
0x14000c130  mov     rbx, rdx
0x14000c133  mov     r10, rcx
0x14000c136  test    r8d, r8d
0x14000c139  jz      short loc_14000C143
0x14000c13b  mov     r8d, 0C0000295h
0x14000c141  jmp     short loc_14000C1A9
0x14000c143  test    eax, eax
0x14000c145  jnz     short loc_14000C1A3
0x14000c147  cmp     [rsp+58h+arg_20], 1
0x14000c14f  jnz     short loc_14000C1A3
0x14000c151  lea     r9d, [rax+14h]
0x14000c155  cmp     [rsp+58h+arg_30], r9d
0x14000c15d  jnb     short loc_14000C167
0x14000c15f  mov     r8d, 0C0000023h
0x14000c165  jmp     short loc_14000C1A9
0x14000c167  mov     rcx, [rcx+40h]
0x14000c16b  xor     edx, edx
0x14000c16d  mov     dword ptr [rsp+58h+var_28], 2
0x14000c175  xor     r8d, r8d
0x14000c178  mov     dword ptr [rsp+58h+var_28+8], edx
0x14000c17c  mov     eax, [rcx+180h]
0x14000c182  mov     dword ptr [rsp+58h+var_28+4], eax
0x14000c186  movzx   eax, word ptr [rcx+17Ah]
0x14000c18d  mov     dword ptr [rsp+58h+var_28+0Ch], eax
0x14000c191  movups  xmm0, [rsp+58h+var_28]
0x14000c196  movups  xmmword ptr [r11], xmm0
0x14000c19a  mov     [r11+10h], edx
0x14000c19e  mov     [rdi], r9d
0x14000c1a1  jmp     short loc_14000C1A9
0x14000c1a3  mov     r8d, 0C0000010h; Status
0x14000c1a9  mov     rdx, rbx; Irp
0x14000c1ac  mov     [rsp+58h+PriorityBoost], 0; PriorityBoost
0x14000c1b1  mov     rcx, r10; DeviceObject
0x14000c1b4  call    cs:__imp_WmiCompleteRequest
0x14000c1bb  nop     dword ptr [rax+rax+00h]
0x14000c1c0  mov     rbx, [rsp+58h+arg_10]
0x14000c1c5  add     rsp, 50h
0x14000c1c9  pop     rdi
0x14000c1ca  retn
```
