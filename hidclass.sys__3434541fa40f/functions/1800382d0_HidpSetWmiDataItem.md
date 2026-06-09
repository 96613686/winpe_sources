# HidpSetWmiDataItem

- ea: `0x1800382d0`
- end: `0x18003838a`
- name: `HidpSetWmiDataItem`
- size: `186`
- prototype: `__int64 __usercall@<rax>(PDEVICE_OBJECT DeviceObject@<rcx>, PIRP Irp@<rdx>, int, int, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18001c1e4`
- `0x18001cfc4`
- `0x1800382d0`

## import_xrefs

- `WMILIB!WmiCompleteRequest` at `0x18003836d`
- `WMILIB!WmiCompleteRequest` at `0x18003836d`

## pseudocode

```c
NTSTATUS __fastcall HidpSetWmiDataItem(PDEVICE_OBJECT DeviceObject, PIRP Irp, int a3, int a4, int a5, int a6, char *a7)
{
  ULONG v8; // ebx
  _BYTE *DeviceExtension; // rcx
  NTSTATUS v11; // eax
  char *v12; // rdx

  v8 = 0;
  DeviceExtension = DeviceObject->DeviceExtension;
  if ( !DeviceExtension[24] )
  {
    if ( !a3 )
    {
      v8 = 1;
      if ( a6 )
      {
        if ( a5 == 1 && !a4 )
        {
          v12 = a7;
          LOBYTE(v12) = *a7;
          v11 = HidpToggleSelSusp(DeviceExtension + 32, v12);
          return WmiCompleteRequest(DeviceObject, Irp, v11, v8, 0);
        }
LABEL_14:
        v11 = -1073741808;
        return WmiCompleteRequest(DeviceObject, Irp, v11, v8, 0);
      }
LABEL_10:
      v11 = -1073741789;
      return WmiCompleteRequest(DeviceObject, Irp, v11, v8, 0);
    }
LABEL_8:
    v11 = -1073741163;
    return WmiCompleteRequest(DeviceObject, Irp, v11, v8, 0);
  }
  if ( a3 )
    goto LABEL_8;
  v8 = 1;
  if ( !a6 )
    goto LABEL_10;
  if ( a5 != 1 || a4 )
    goto LABEL_14;
  v11 = HidpToggleRemoteWake((__int64)(DeviceExtension + 32), *a7);
  return WmiCompleteRequest(DeviceObject, Irp, v11, v8, 0);
}

```

## disassembly

```asm
0x1800382d0  mov     [rsp+arg_0], rbx
0x1800382d5  mov     [rsp+arg_8], rsi
0x1800382da  push    rdi
0x1800382db  sub     rsp, 30h
0x1800382df  mov     rdi, rcx
0x1800382e2  xor     ebx, ebx
0x1800382e4  mov     rcx, [rcx+40h]
0x1800382e8  mov     rsi, rdx
0x1800382eb  cmp     [rcx+18h], bl
0x1800382ee  jz      short loc_18003831C
0x1800382f0  test    r8d, r8d
0x1800382f3  jnz     short loc_180038321
0x1800382f5  lea     ebx, [r8+1]
0x1800382f9  cmp     [rsp+38h+arg_28], ebx
0x1800382fd  jb      short loc_180038333
0x1800382ff  cmp     [rsp+38h+arg_20], ebx
0x180038303  jnz     short loc_180038357
0x180038305  test    r9d, r9d
0x180038308  jnz     short loc_180038357
0x18003830a  mov     rdx, [rsp+38h+arg_30]
0x18003830f  add     rcx, 20h ; ' '
0x180038313  mov     dl, [rdx]
0x180038315  call    HidpToggleRemoteWake
0x18003831a  jmp     short loc_18003835C
0x18003831c  test    r8d, r8d
0x18003831f  jz      short loc_180038328
0x180038321  mov     eax, 0C0000295h
0x180038326  jmp     short loc_18003835C
0x180038328  mov     ebx, 1
0x18003832d  cmp     [rsp+38h+arg_28], ebx
0x180038331  jnb     short loc_18003833A
0x180038333  mov     eax, 0C0000023h
0x180038338  jmp     short loc_18003835C
0x18003833a  cmp     [rsp+38h+arg_20], ebx
0x18003833e  jnz     short loc_180038357
0x180038340  test    r9d, r9d
0x180038343  jnz     short loc_180038357
0x180038345  mov     rdx, [rsp+38h+arg_30]
0x18003834a  add     rcx, 20h ; ' '
0x18003834e  mov     dl, [rdx]
0x180038350  call    HidpToggleSelSusp
0x180038355  jmp     short loc_18003835C
0x180038357  mov     eax, 0C0000010h
0x18003835c  mov     r9d, ebx; BufferUsed
0x18003835f  mov     [rsp+38h+PriorityBoost], 0; PriorityBoost
0x180038364  mov     r8d, eax; Status
0x180038367  mov     rdx, rsi; Irp
0x18003836a  mov     rcx, rdi; DeviceObject
0x18003836d  call    cs:__imp_WmiCompleteRequest
0x180038374  nop     dword ptr [rax+rax+00h]
0x180038379  mov     rbx, [rsp+38h+arg_0]
0x18003837e  mov     rsi, [rsp+38h+arg_8]
0x180038383  add     rsp, 30h
0x180038387  pop     rdi
0x180038388  retn
```
