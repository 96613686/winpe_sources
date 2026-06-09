# HidpQueryWmiDataBlock

- ea: `0x18003fa50`
- end: `0x18003fb19`
- name: `HidpQueryWmiDataBlock`
- size: `201`
- prototype: `__int64 __usercall@<rax>(PDEVICE_OBJECT DeviceObject@<rcx>, PIRP Irp@<rdx>, int, __int64, int, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180018220`
- `0x18003fa50`

## import_xrefs

- `WMILIB!WmiCompleteRequest` at `0x18003fab7`
- `WMILIB!WmiCompleteRequest` at `0x18003fab7`

## pseudocode

```c
NTSTATUS __fastcall HidpQueryWmiDataBlock(
        PDEVICE_OBJECT DeviceObject,
        PIRP Irp,
        int a3,
        int a4,
        int a5,
        _DWORD *a6,
        int a7,
        bool *a8)
{
  ULONG v9; // edi
  _BYTE *DeviceExtension; // rcx
  NTSTATUS v12; // r8d

  v9 = 0;
  DeviceExtension = DeviceObject->DeviceExtension;
  if ( DeviceExtension[24] )
  {
    if ( !a3 )
    {
      if ( !a4 && a5 == 1 )
      {
        v9 = 1;
        if ( a7 )
        {
          *a8 = HidpCheckRemoteWakeEnabled(DeviceExtension + 32);
          goto LABEL_7;
        }
LABEL_10:
        v12 = -1073741789;
        return WmiCompleteRequest(DeviceObject, Irp, v12, v9, 0);
      }
LABEL_11:
      v12 = -1073741808;
      return WmiCompleteRequest(DeviceObject, Irp, v12, v9, 0);
    }
LABEL_9:
    v12 = -1073741163;
    return WmiCompleteRequest(DeviceObject, Irp, v12, v9, 0);
  }
  if ( a3 )
    goto LABEL_9;
  if ( a4 || a5 != 1 )
    goto LABEL_11;
  v9 = 1;
  if ( !a7 )
    goto LABEL_10;
  *a8 = (*((_DWORD *)DeviceExtension + 447) & 8) != 0;
LABEL_7:
  v12 = 0;
  *a6 = 1;
  return WmiCompleteRequest(DeviceObject, Irp, v12, v9, 0);
}

```

## disassembly

```asm
0x18003fa50  mov     [rsp+arg_0], rbp
0x18003fa55  mov     [rsp+arg_8], rsi
0x18003fa5a  push    rdi
0x18003fa5b  sub     rsp, 30h
0x18003fa5f  mov     rsi, rcx
0x18003fa62  xor     edi, edi
0x18003fa64  mov     rcx, [rcx+40h]
0x18003fa68  mov     rbp, rdx
0x18003fa6b  cmp     [rcx+18h], dil
0x18003fa6f  jnz     short loc_18003FAEC
0x18003fa71  test    r8d, r8d
0x18003fa74  jnz     short loc_18003FAD4
0x18003fa76  test    r9d, r9d
0x18003fa79  jnz     short loc_18003FAE4
0x18003fa7b  cmp     [rsp+38h+arg_20], 1
0x18003fa80  jnz     short loc_18003FAE4
0x18003fa82  lea     edi, [r8+1]
0x18003fa86  cmp     [rsp+38h+arg_30], edi
0x18003fa8a  jb      short loc_18003FADC
0x18003fa8c  mov     ecx, [rcx+6FCh]
0x18003fa92  mov     rax, [rsp+38h+arg_38]
0x18003fa97  shr     ecx, 3
0x18003fa9a  and     cl, dil
0x18003fa9d  mov     [rax], cl
0x18003fa9f  mov     rax, [rsp+38h+arg_28]
0x18003faa4  xor     r8d, r8d; Status
0x18003faa7  mov     [rax], edi
0x18003faa9  mov     r9d, edi; BufferUsed
0x18003faac  mov     [rsp+38h+PriorityBoost], 0; PriorityBoost
0x18003fab1  mov     rdx, rbp; Irp
0x18003fab4  mov     rcx, rsi; DeviceObject
0x18003fab7  call    cs:__imp_WmiCompleteRequest
0x18003fabe  nop     dword ptr [rax+rax+00h]
0x18003fac3  mov     rbp, [rsp+38h+arg_0]
0x18003fac8  mov     rsi, [rsp+38h+arg_8]
0x18003facd  add     rsp, 30h
0x18003fad1  pop     rdi
0x18003fad2  retn
0x18003fad4  mov     r8d, 0C0000295h
0x18003fada  jmp     short loc_18003FAA9
0x18003fadc  mov     r8d, 0C0000023h
0x18003fae2  jmp     short loc_18003FAA9
0x18003fae4  mov     r8d, 0C0000010h
0x18003faea  jmp     short loc_18003FAA9
0x18003faec  test    r8d, r8d
0x18003faef  jnz     short loc_18003FAD4
0x18003faf1  test    r9d, r9d
0x18003faf4  jnz     short loc_18003FAE4
0x18003faf6  cmp     [rsp+38h+arg_20], 1
0x18003fafb  jnz     short loc_18003FAE4
0x18003fafd  lea     edi, [r8+1]
0x18003fb01  cmp     [rsp+38h+arg_30], edi
0x18003fb05  jb      short loc_18003FADC
0x18003fb07  add     rcx, 20h ; ' '
0x18003fb0b  call    HidpCheckRemoteWakeEnabled
0x18003fb10  mov     rcx, [rsp+38h+arg_38]
0x18003fb15  mov     [rcx], al
0x18003fb17  jmp     short loc_18003FA9F
```
