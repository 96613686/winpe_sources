# DiskFdoSetWmiDataItem

- ea: `0x140010be0`
- end: `0x140010cb1`
- name: `DiskFdoSetWmiDataItem`
- size: `209`
- prototype: `__int64 __usercall@<rax>(PDEVICE_OBJECT DeviceObject@<rcx>, PIRP Irp@<rdx>, int, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140005244`
- `0x1400053c8`
- `0x140010be0`

## import_xrefs

- `CLASSPNP!ClassWmiCompleteRequest` at `0x140010c99`
- `CLASSPNP!ClassWmiCompleteRequest` at `0x140010c99`

## pseudocode

```c
NTSTATUS __fastcall DiskFdoSetWmiDataItem(
        PDEVICE_OBJECT DeviceObject,
        PIRP Irp,
        __int64 a3,
        int a4,
        int a5,
        __int64 a6)
{
  unsigned int v6; // ebp
  NTSTATUS v9; // ebx

  v6 = a3;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qqddDq(WPP_GLOBAL_Control->AttachedDevice, Irp, a3, DeviceObject, Irp, a3, a4, a5, a6);
  }
  v9 = -1073741114;
  if ( v6 > 5 )
    v9 = -1073741163;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qqL(WPP_GLOBAL_Control->AttachedDevice, 43, a3, DeviceObject, Irp, v9);
  }
  return ClassWmiCompleteRequest(DeviceObject, Irp, v9, 0, 0);
}

```

## disassembly

```asm
0x140010be0  push    rbx
0x140010be2  push    rbp
0x140010be3  push    rsi
0x140010be4  push    rdi
0x140010be5  push    r14
0x140010be7  sub     rsp, 50h
0x140010beb  mov     ebp, r8d
0x140010bee  mov     rdi, rdx
0x140010bf1  mov     rsi, rcx
0x140010bf4  mov     rcx, cs:WPP_GLOBAL_Control
0x140010bfb  lea     r14, WPP_GLOBAL_Control
0x140010c02  cmp     rcx, r14
0x140010c05  jz      short loc_140010C47
0x140010c07  mov     eax, [rcx+2Ch]
0x140010c0a  test    al, 40h
0x140010c0c  jz      short loc_140010C47
0x140010c0e  cmp     byte ptr [rcx+29h], 4
0x140010c12  jb      short loc_140010C47
0x140010c14  mov     rax, [rsp+78h+arg_28]
0x140010c1c  mov     rcx, [rcx+18h]
0x140010c20  mov     [rsp+78h+var_38], rax
0x140010c25  mov     eax, [rsp+78h+arg_20]
0x140010c2c  mov     [rsp+78h+var_40], eax
0x140010c30  mov     [rsp+78h+var_48], r9d
0x140010c35  mov     r9, rsi
0x140010c38  mov     [rsp+78h+var_50], r8d
0x140010c3d  mov     qword ptr [rsp+78h+PriorityBoost], rdx
0x140010c42  call    WPP_SF_qqddDq
0x140010c47  mov     rcx, cs:WPP_GLOBAL_Control
0x140010c4e  mov     ebx, 0C00002C6h
0x140010c53  cmp     ebp, 5
0x140010c56  lea     eax, [rbx-31h]
0x140010c59  cmova   ebx, eax
0x140010c5c  cmp     rcx, r14
0x140010c5f  jz      short loc_140010C88
0x140010c61  mov     eax, [rcx+2Ch]
0x140010c64  test    al, 40h
0x140010c66  jz      short loc_140010C88
0x140010c68  cmp     byte ptr [rcx+29h], 4
0x140010c6c  jb      short loc_140010C88
0x140010c6e  mov     rcx, [rcx+18h]
0x140010c72  mov     edx, 2Bh ; '+'
0x140010c77  mov     [rsp+78h+var_50], ebx
0x140010c7b  mov     r9, rsi
0x140010c7e  mov     qword ptr [rsp+78h+PriorityBoost], rdi
0x140010c83  call    WPP_SF_qqL
0x140010c88  xor     r9d, r9d; BufferUsed
0x140010c8b  mov     [rsp+78h+PriorityBoost], 0; PriorityBoost
0x140010c90  mov     r8d, ebx; Status
0x140010c93  mov     rdx, rdi; Irp
0x140010c96  mov     rcx, rsi; DeviceObject
0x140010c99  call    cs:__imp_ClassWmiCompleteRequest
0x140010ca0  nop     dword ptr [rax+rax+00h]
0x140010ca5  add     rsp, 50h
0x140010ca9  pop     r14
0x140010cab  pop     rdi
0x140010cac  pop     rsi
0x140010cad  pop     rbp
0x140010cae  pop     rbx
0x140010caf  retn
```
