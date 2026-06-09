# DiskIoctlGetVolumeDiskExtents

- ea: `0x14000e010`
- end: `0x14000e15b`
- name: `DiskIoctlGetVolumeDiskExtents`
- size: `331`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1400014a0`

## callees

- `0x140004078`
- `0x14000431c`
- `0x14000e010`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x14000e037`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000e037`
- `CLASSPNP!ClassReadDriveCapacity` at `0x14000e0ec`
- `CLASSPNP!ClassReadDriveCapacity` at `0x14000e0ec`

## pseudocode

```c
__int64 __fastcall DiskIoctlGetVolumeDiskExtents(__int64 a1, _QWORD *a2)
{
  _QWORD *v2; // rbx
  __int64 v4; // rbp
  __int64 v6; // r14
  unsigned int v8; // r15d
  NTSTATUS DriveCapacity; // eax
  __int64 v10; // r8

  v2 = *(_QWORD **)(a1 + 64);
  v4 = a2[23];
  v6 = v2[12];
  if ( KeGetCurrentIrql() >= 2u )
    return 3221225800LL;
  v8 = -1073741808;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 98, WPP_0d021951613e35be7880fae860fb7f50_Traceguids, a1, a2);
  }
  if ( (*(_DWORD *)(a1 + 52) & 1) == 0 )
    return v8;
  if ( *(_DWORD *)(v4 + 8) >= 0x20u )
  {
    DriveCapacity = ClassReadDriveCapacity(*(PDEVICE_OBJECT *)(v2[3] + 8LL));
    *(_DWORD *)(v6 + 4) = DriveCapacity;
    v8 = DriveCapacity;
    if ( DriveCapacity >= 0 )
    {
      v10 = a2[3];
      *(_DWORD *)v10 = 1;
      *(_DWORD *)(v10 + 8) = *(_DWORD *)(v2[3] + 588LL);
      *(_QWORD *)(v10 + 16) = v2[19];
      *(_QWORD *)(v10 + 24) = v2[18];
      a2[7] = 32;
    }
    return v8;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 99, WPP_0d021951613e35be7880fae860fb7f50_Traceguids);
  }
  return 3221225507LL;
}

```

## disassembly

```asm
0x14000e010  mov     [rsp+arg_10], rbx
0x14000e015  mov     [rsp+arg_18], rbp
0x14000e01a  push    rsi
0x14000e01b  push    rdi
0x14000e01c  push    r14
0x14000e01e  sub     rsp, 30h
0x14000e022  mov     rbx, [rcx+40h]
0x14000e026  mov     rdi, rdx
0x14000e029  mov     rbp, [rdx+0B8h]
0x14000e030  mov     rsi, rcx
0x14000e033  mov     r14, [rbx+60h]
0x14000e037  call    cs:__imp_KeGetCurrentIrql
0x14000e03e  nop     dword ptr [rax+rax+00h]
0x14000e043  cmp     al, 2
0x14000e045  jb      short loc_14000E051
0x14000e047  mov     eax, 0C0000148h
0x14000e04c  jmp     loc_14000E147
0x14000e051  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e058  mov     [rsp+48h+arg_0], r12
0x14000e05d  lea     r12, WPP_GLOBAL_Control
0x14000e064  mov     [rsp+48h+arg_8], r15
0x14000e069  mov     r15d, 0C0000010h
0x14000e06f  cmp     rcx, r12
0x14000e072  jz      short loc_14000E09E
0x14000e074  mov     eax, [rcx+2Ch]
0x14000e077  test    al, 10h
0x14000e079  jz      short loc_14000E09E
0x14000e07b  cmp     byte ptr [rcx+29h], 4
0x14000e07f  jb      short loc_14000E09E
0x14000e081  mov     rcx, [rcx+18h]
0x14000e085  lea     r8, WPP_0d021951613e35be7880fae860fb7f50_Traceguids
0x14000e08c  mov     edx, 62h ; 'b'
0x14000e091  mov     [rsp+48h+var_28], rdi
0x14000e096  mov     r9, rsi
0x14000e099  call    WPP_SF_qq
0x14000e09e  mov     eax, [rsi+34h]
0x14000e0a1  test    al, 1
0x14000e0a3  jz      loc_14000E13A
0x14000e0a9  cmp     dword ptr [rbp+8], 20h ; ' '
0x14000e0ad  jnb     short loc_14000E0E4
0x14000e0af  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e0b6  cmp     rcx, r12
0x14000e0b9  jz      short loc_14000E0DD
0x14000e0bb  mov     eax, [rcx+2Ch]
0x14000e0be  test    al, 10h
0x14000e0c0  jz      short loc_14000E0DD
0x14000e0c2  cmp     byte ptr [rcx+29h], 2
0x14000e0c6  jb      short loc_14000E0DD
0x14000e0c8  mov     rcx, [rcx+18h]
0x14000e0cc  lea     r8, WPP_0d021951613e35be7880fae860fb7f50_Traceguids
0x14000e0d3  mov     edx, 63h ; 'c'
0x14000e0d8  call    WPP_SF_
0x14000e0dd  mov     eax, 0C0000023h
0x14000e0e2  jmp     short loc_14000E13D
0x14000e0e4  mov     rcx, [rbx+18h]
0x14000e0e8  mov     rcx, [rcx+8]; DeviceObject
0x14000e0ec  call    cs:__imp_ClassReadDriveCapacity
0x14000e0f3  nop     dword ptr [rax+rax+00h]
0x14000e0f8  mov     [r14+4], eax
0x14000e0fc  mov     r15d, eax
0x14000e0ff  test    eax, eax
0x14000e101  js      short loc_14000E13A
0x14000e103  mov     r8, [rdi+18h]
0x14000e107  mov     dword ptr [r8], 1
0x14000e10e  mov     rcx, [rbx+18h]
0x14000e112  mov     edx, [rcx+24Ch]
0x14000e118  mov     [r8+8], edx
0x14000e11c  mov     rcx, [rbx+98h]
0x14000e123  mov     [r8+10h], rcx
0x14000e127  mov     rcx, [rbx+90h]
0x14000e12e  mov     [r8+18h], rcx
0x14000e132  mov     qword ptr [rdi+38h], 20h ; ' '
0x14000e13a  mov     eax, r15d
0x14000e13d  mov     r12, [rsp+48h+arg_0]
0x14000e142  mov     r15, [rsp+48h+arg_8]
0x14000e147  mov     rbx, [rsp+48h+arg_10]
0x14000e14c  mov     rbp, [rsp+48h+arg_18]
0x14000e151  add     rsp, 30h
0x14000e155  pop     r14
0x14000e157  pop     rdi
0x14000e158  pop     rsi
0x14000e159  retn
```
