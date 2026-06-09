# DiskFdoSetWmiDataBlock

- ea: `0x140010a70`
- end: `0x140010bcc`
- name: `DiskFdoSetWmiDataBlock`
- size: `348`
- prototype: `NTSTATUS __fastcall(PDEVICE_OBJECT DeviceObject, PIRP Irp, __int64, unsigned int, _BYTE *)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140005244`
- `0x1400052b0`
- `0x14000e200`
- `0x140010a70`

## import_xrefs

- `CLASSPNP!ClassWmiCompleteRequest` at `0x140010ba7`
- `CLASSPNP!ClassWmiCompleteRequest` at `0x140010ba7`

## pseudocode

```c
NTSTATUS __fastcall DiskFdoSetWmiDataBlock(
        PDEVICE_OBJECT DeviceObject,
        PIRP Irp,
        __int64 a3,
        unsigned int a4,
        _BYTE *a5)
{
  _QWORD *DeviceExtension; // r13
  unsigned int v7; // esi
  __int64 v10; // r12
  char v11; // al
  NTSTATUS v12; // ebx
  __int16 v14; // [rsp+40h] [rbp-10h] BYREF
  char v15; // [rsp+42h] [rbp-Eh]
  char v16; // [rsp+43h] [rbp-Dh]
  char v17; // [rsp+44h] [rbp-Ch]
  char v18; // [rsp+45h] [rbp-Bh]
  char v19; // [rsp+46h] [rbp-Ah]
  char v20; // [rsp+47h] [rbp-9h]
  char v21; // [rsp+48h] [rbp-8h]
  char v22; // [rsp+49h] [rbp-7h]
  char v23; // [rsp+4Ah] [rbp-6h]
  char v24; // [rsp+4Bh] [rbp-5h]

  DeviceExtension = DeviceObject->DeviceExtension;
  v7 = a3;
  v10 = DeviceExtension[12];
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qqdDq(WPP_GLOBAL_Control->AttachedDevice, Irp, a3, DeviceObject, Irp, a3, a4, a5);
  }
  if ( v7 == 6 )
  {
    if ( a4 < 0xC )
    {
      v12 = -1073741811;
    }
    else
    {
      v11 = a5[2] & 0xF;
      v15 = a5[1];
      v16 = v11;
      v20 = a5[4];
      v19 = a5[5];
      v18 = a5[6];
      v17 = a5[7];
      v24 = a5[8];
      v23 = a5[9];
      v22 = a5[10];
      v21 = a5[11];
      v14 = 2588;
      *(_BYTE *)(v10 + 20) = (unsigned __int8)~v15 >> 7;
      v12 = DiskSetInfoExceptionInformation((__int64)DeviceExtension, &v14);
    }
  }
  else
  {
    v12 = -1073741163;
    if ( v7 <= 5 )
      v12 = -1073741114;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qqL(WPP_GLOBAL_Control->AttachedDevice, 41, a3, DeviceObject, Irp, v12);
  }
  return ClassWmiCompleteRequest(DeviceObject, Irp, v12, 0, 0);
}

```

## disassembly

```asm
0x140010a70  mov     r11, rsp
0x140010a73  mov     [r11+18h], rbx
0x140010a77  push    rbp
0x140010a78  push    rsi
0x140010a79  push    rdi
0x140010a7a  push    r12
0x140010a7c  push    r13
0x140010a7e  push    r14
0x140010a80  push    r15
0x140010a82  mov     rbp, rsp
0x140010a85  sub     rsp, 50h
0x140010a89  mov     r13, [rcx+40h]
0x140010a8d  mov     r15d, r9d
0x140010a90  mov     rbx, [rbp+arg_20]
0x140010a94  mov     esi, r8d
0x140010a97  mov     r14, rdx
0x140010a9a  mov     rdi, rcx
0x140010a9d  mov     r12, [r13+60h]
0x140010aa1  mov     rcx, cs:WPP_GLOBAL_Control
0x140010aa8  lea     rax, WPP_GLOBAL_Control
0x140010aaf  cmp     rcx, rax
0x140010ab2  jz      short loc_140010ADE
0x140010ab4  mov     eax, [rcx+2Ch]
0x140010ab7  test    al, 40h
0x140010ab9  jz      short loc_140010ADE
0x140010abb  cmp     byte ptr [rcx+29h], 4
0x140010abf  jb      short loc_140010ADE
0x140010ac1  mov     rcx, [rcx+18h]
0x140010ac5  mov     [r11-50h], rbx
0x140010ac9  mov     [r11-58h], r9d
0x140010acd  mov     r9, rdi
0x140010ad0  mov     [rsp+50h+var_28], r8d
0x140010ad5  mov     [r11-68h], rdx
0x140010ad9  call    WPP_SF_qqdDq
0x140010ade  cmp     esi, 6
0x140010ae1  jnz     short loc_140010B4E
0x140010ae3  cmp     r15d, 0Ch
0x140010ae7  jb      short loc_140010B47
0x140010ae9  mov     cl, [rbx+1]
0x140010aec  lea     rdx, [rbp+var_10]
0x140010af0  mov     al, [rbx+2]
0x140010af3  and     al, 0Fh
0x140010af5  mov     [rbp+var_E], cl
0x140010af8  mov     [rbp+var_D], al
0x140010afb  not     cl
0x140010afd  mov     al, [rbx+4]
0x140010b00  mov     [rbp+var_9], al
0x140010b03  mov     al, [rbx+5]
0x140010b06  mov     [rbp+var_A], al
0x140010b09  mov     al, [rbx+6]
0x140010b0c  mov     [rbp+var_B], al
0x140010b0f  mov     al, [rbx+7]
0x140010b12  mov     [rbp+var_C], al
0x140010b15  mov     al, [rbx+8]
0x140010b18  mov     [rbp+var_5], al
0x140010b1b  mov     al, [rbx+9]
0x140010b1e  mov     [rbp+var_6], al
0x140010b21  mov     al, [rbx+0Ah]
0x140010b24  mov     [rbp+var_7], al
0x140010b27  mov     al, [rbx+0Bh]
0x140010b2a  shr     cl, 7
0x140010b2d  mov     [rbp+var_8], al
0x140010b30  mov     [rbp+var_10], 0A1Ch
0x140010b36  mov     [r12+14h], cl
0x140010b3b  mov     rcx, r13
0x140010b3e  call    DiskSetInfoExceptionInformation
0x140010b43  mov     ebx, eax
0x140010b45  jmp     short loc_140010B5C
0x140010b47  mov     ebx, 0C000000Dh
0x140010b4c  jmp     short loc_140010B5C
0x140010b4e  mov     ebx, 0C0000295h
0x140010b53  cmp     esi, 5
0x140010b56  lea     eax, [rbx+31h]
0x140010b59  cmovbe  ebx, eax
0x140010b5c  mov     rcx, cs:WPP_GLOBAL_Control
0x140010b63  lea     rax, WPP_GLOBAL_Control
0x140010b6a  cmp     rcx, rax
0x140010b6d  jz      short loc_140010B96
0x140010b6f  mov     eax, [rcx+2Ch]
0x140010b72  test    al, 40h
0x140010b74  jz      short loc_140010B96
0x140010b76  cmp     byte ptr [rcx+29h], 4
0x140010b7a  jb      short loc_140010B96
0x140010b7c  mov     rcx, [rcx+18h]
0x140010b80  mov     edx, 29h ; ')'
0x140010b85  mov     [rsp+50h+var_28], ebx
0x140010b89  mov     r9, rdi
0x140010b8c  mov     qword ptr [rsp+50h+PriorityBoost], r14
0x140010b91  call    WPP_SF_qqL
0x140010b96  xor     r9d, r9d; BufferUsed
0x140010b99  mov     [rsp+50h+PriorityBoost], 0; PriorityBoost
0x140010b9e  mov     r8d, ebx; Status
0x140010ba1  mov     rdx, r14; Irp
0x140010ba4  mov     rcx, rdi; DeviceObject
0x140010ba7  call    cs:__imp_ClassWmiCompleteRequest
0x140010bae  nop     dword ptr [rax+rax+00h]
0x140010bb3  mov     rbx, [rsp+50h+arg_10]
0x140010bbb  add     rsp, 50h
0x140010bbf  pop     r15
0x140010bc1  pop     r14
0x140010bc3  pop     r13
0x140010bc5  pop     r12
0x140010bc7  pop     rdi
0x140010bc8  pop     rsi
0x140010bc9  pop     rbp
0x140010bca  retn
```
