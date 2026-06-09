# HidpSetWmiDataBlock

- ea: `0x180038210`
- end: `0x1800382be`
- name: `HidpSetWmiDataBlock`
- size: `174`
- prototype: `__int64 __usercall@<rax>(PDEVICE_OBJECT DeviceObject@<rcx>, PIRP Irp@<rdx>, int, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18001c1e4`
- `0x18001cfc4`
- `0x180038210`

## import_xrefs

- `WMILIB!WmiCompleteRequest` at `0x1800382a1`
- `WMILIB!WmiCompleteRequest` at `0x1800382a1`

## pseudocode

```c
NTSTATUS __fastcall HidpSetWmiDataBlock(PDEVICE_OBJECT DeviceObject, PIRP Irp, int a3, int a4, int a5, char *a6)
{
  ULONG v7; // ebx
  _BYTE *DeviceExtension; // rcx
  NTSTATUS v10; // eax
  char *v11; // rdx

  v7 = 0;
  DeviceExtension = DeviceObject->DeviceExtension;
  if ( !DeviceExtension[24] )
  {
    if ( !a3 )
    {
      v7 = 1;
      if ( a5 )
      {
        if ( !a4 )
        {
          v11 = a6;
          LOBYTE(v11) = *a6;
          v10 = HidpToggleSelSusp(DeviceExtension + 32, v11);
          return WmiCompleteRequest(DeviceObject, Irp, v10, v7, 0);
        }
        goto LABEL_11;
      }
LABEL_9:
      v10 = -1073741789;
      return WmiCompleteRequest(DeviceObject, Irp, v10, v7, 0);
    }
LABEL_7:
    v10 = -1073741163;
    return WmiCompleteRequest(DeviceObject, Irp, v10, v7, 0);
  }
  if ( a3 )
    goto LABEL_7;
  v7 = 1;
  if ( !a5 )
    goto LABEL_9;
  if ( a4 )
  {
LABEL_11:
    v10 = -1073741808;
    return WmiCompleteRequest(DeviceObject, Irp, v10, v7, 0);
  }
  v10 = HidpToggleRemoteWake((__int64)(DeviceExtension + 32), *a6);
  return WmiCompleteRequest(DeviceObject, Irp, v10, v7, 0);
}

```

## disassembly

```asm
0x180038210  mov     [rsp+arg_0], rbx
0x180038215  mov     [rsp+arg_8], rsi
0x18003821a  push    rdi
0x18003821b  sub     rsp, 30h
0x18003821f  mov     rdi, rcx
0x180038222  xor     ebx, ebx
0x180038224  mov     rcx, [rcx+40h]
0x180038228  mov     rsi, rdx
0x18003822b  cmp     [rcx+18h], bl
0x18003822e  jz      short loc_180038256
0x180038230  test    r8d, r8d
0x180038233  jnz     short loc_18003825B
0x180038235  lea     ebx, [r8+1]
0x180038239  cmp     [rsp+38h+arg_20], ebx
0x18003823d  jb      short loc_18003826D
0x18003823f  test    r9d, r9d
0x180038242  jnz     short loc_180038279
0x180038244  mov     rdx, [rsp+38h+arg_28]
0x180038249  add     rcx, 20h ; ' '
0x18003824d  mov     dl, [rdx]
0x18003824f  call    HidpToggleRemoteWake
0x180038254  jmp     short loc_180038290
0x180038256  test    r8d, r8d
0x180038259  jz      short loc_180038262
0x18003825b  mov     eax, 0C0000295h
0x180038260  jmp     short loc_180038290
0x180038262  mov     ebx, 1
0x180038267  cmp     [rsp+38h+arg_20], ebx
0x18003826b  jnb     short loc_180038274
0x18003826d  mov     eax, 0C0000023h
0x180038272  jmp     short loc_180038290
0x180038274  test    r9d, r9d
0x180038277  jz      short loc_180038280
0x180038279  mov     eax, 0C0000010h
0x18003827e  jmp     short loc_180038290
0x180038280  mov     rdx, [rsp+38h+arg_28]
0x180038285  add     rcx, 20h ; ' '
0x180038289  mov     dl, [rdx]
0x18003828b  call    HidpToggleSelSusp
0x180038290  mov     r9d, ebx; BufferUsed
0x180038293  mov     [rsp+38h+PriorityBoost], 0; PriorityBoost
0x180038298  mov     r8d, eax; Status
0x18003829b  mov     rdx, rsi; Irp
0x18003829e  mov     rcx, rdi; DeviceObject
0x1800382a1  call    cs:__imp_WmiCompleteRequest
0x1800382a8  nop     dword ptr [rax+rax+00h]
0x1800382ad  mov     rbx, [rsp+38h+arg_0]
0x1800382b2  mov     rsi, [rsp+38h+arg_8]
0x1800382b7  add     rsp, 30h
0x1800382bb  pop     rdi
0x1800382bc  retn
```
