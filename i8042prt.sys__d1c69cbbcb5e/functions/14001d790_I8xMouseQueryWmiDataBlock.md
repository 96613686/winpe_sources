# I8xMouseQueryWmiDataBlock

- ea: `0x14001d790`
- end: `0x14001d832`
- name: `I8xMouseQueryWmiDataBlock`
- size: `162`
- prototype: `__int64 __usercall@<rax>(PDEVICE_OBJECT DeviceObject@<rcx>, PIRP Irp@<rdx>, int, __int64, int, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x14001d790`

## import_xrefs

- `WMILIB!WmiCompleteRequest` at `0x14001d81f`
- `WMILIB!WmiCompleteRequest` at `0x14001d81f`

## pseudocode

```c
NTSTATUS __fastcall I8xMouseQueryWmiDataBlock(
        PDEVICE_OBJECT DeviceObject,
        PIRP Irp,
        int a3,
        __int64 a4,
        int a5,
        _DWORD *a6,
        unsigned int a7,
        __int64 a8)
{
  NTSTATUS v8; // r8d
  _DWORD *DeviceExtension; // r8
  unsigned int v10; // kr00_4
  unsigned int v11; // eax

  if ( a3 )
  {
    v8 = -1073741163;
  }
  else if ( a7 >= 0x14 )
  {
    DeviceExtension = DeviceObject->DeviceExtension;
    v10 = DeviceExtension[148];
    v11 = *((unsigned __int16 *)DeviceExtension + 293);
    *(_DWORD *)a8 = 0;
    *(_DWORD *)(a8 + 4) = v10 / 0x18;
    v8 = 0;
    *(_DWORD *)(a8 + 8) = 0;
    *(_QWORD *)(a8 + 12) = v11;
    *a6 = 20;
  }
  else
  {
    v8 = -1073741789;
  }
  return WmiCompleteRequest(DeviceObject, Irp, v8, 0x14u, 0);
}

```

## disassembly

```asm
0x14001d790  push    rbx
0x14001d792  sub     rsp, 30h
0x14001d796  mov     r9, [rsp+38h+arg_38]
0x14001d79b  mov     r11, rdx
0x14001d79e  mov     rbx, [rsp+38h+arg_28]
0x14001d7a3  mov     r10, rcx
0x14001d7a6  test    r8d, r8d
0x14001d7a9  jz      short loc_14001D7B3
0x14001d7ab  mov     r8d, 0C0000295h
0x14001d7b1  jmp     short loc_14001D80E
0x14001d7b3  cmp     [rsp+38h+arg_30], 14h
0x14001d7b8  jnb     short loc_14001D7C2
0x14001d7ba  mov     r8d, 0C0000023h
0x14001d7c0  jmp     short loc_14001D80E
0x14001d7c2  mov     r8, [rcx+40h]
0x14001d7c6  mov     rax, 0AAAAAAAAAAAAAAABh
0x14001d7d0  mov     ecx, [r8+250h]
0x14001d7d7  mul     rcx
0x14001d7da  movzx   eax, word ptr [r8+24Ah]
0x14001d7e2  mov     dword ptr [r9], 0
0x14001d7e9  shr     rdx, 4
0x14001d7ed  mov     [r9+4], edx
0x14001d7f1  xor     r8d, r8d; Status
0x14001d7f4  mov     dword ptr [r9+8], 0
0x14001d7fc  mov     [r9+0Ch], eax
0x14001d800  mov     dword ptr [r9+10h], 0
0x14001d808  mov     dword ptr [rbx], 14h
0x14001d80e  mov     r9d, 14h; BufferUsed
0x14001d814  mov     [rsp+38h+PriorityBoost], 0; PriorityBoost
0x14001d819  mov     rdx, r11; Irp
0x14001d81c  mov     rcx, r10; DeviceObject
0x14001d81f  call    cs:__imp_WmiCompleteRequest
0x14001d826  nop     dword ptr [rax+rax+00h]
0x14001d82b  add     rsp, 30h
0x14001d82f  pop     rbx
0x14001d830  retn
```
