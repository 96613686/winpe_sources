# DiskFdoQueryWmiDataBlock

- ea: `0x140014200`
- end: `0x14001450b`
- name: `DiskFdoQueryWmiDataBlock`
- size: `779`
- prototype: `NTSTATUS __fastcall(PDEVICE_OBJECT DeviceObject, PIRP Irp, __int64, unsigned int, _BYTE *)`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140005244`
- `0x14000533c`
- `0x140005bf0`
- `0x140005d00`
- `0x140006000`
- `0x14000e31c`
- `0x140010e14`
- `0x140014200`
- `0x140014520`

## import_xrefs

- `CLASSPNP!ClassWmiCompleteRequest` at `0x14001428f`
- `CLASSPNP!ClassWmiCompleteRequest` at `0x14001428f`
- `CLASSPNP!ClassReadDriveCapacity` at `0x1400144d6`
- `CLASSPNP!ClassReadDriveCapacity` at `0x1400144d6`

## pseudocode

```c
NTSTATUS __fastcall DiskFdoQueryWmiDataBlock(
        PDEVICE_OBJECT DeviceObject,
        PIRP Irp,
        __int64 a3,
        unsigned int a4,
        _BYTE *a5)
{
  _QWORD *DeviceExtension; // r14
  int v7; // ebx
  __int64 v10; // r13
  NTSTATUS FailurePredictThresholds; // ebx
  ULONG v12; // esi
  int v14; // ebx
  int v15; // eax
  bool v16; // zf
  int v17; // ebx
  int v18; // ebx
  unsigned __int8 v19; // cl
  char v20; // al
  char v21; // cl
  char v22; // al
  char v23; // cl
  char v24; // al
  char v25; // cl
  NTSTATUS DriveCapacity; // eax
  __int64 v27; // [rsp+40h] [rbp-268h] BYREF
  int v28; // [rsp+48h] [rbp-260h]
  _DWORD v29[132]; // [rsp+50h] [rbp-258h] BYREF

  DeviceExtension = DeviceObject->DeviceExtension;
  v7 = a3;
  v10 = DeviceExtension[12];
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qqdLq(WPP_GLOBAL_Control->AttachedDevice, Irp, a3, DeviceObject, Irp, a3, a4, a5);
  }
  if ( v7 == 3 )
  {
    FailurePredictThresholds = 0;
LABEL_4:
    v12 = 0;
    goto LABEL_5;
  }
  if ( v7 )
  {
    v14 = v7 - 1;
    if ( !v14 )
    {
      v12 = 8;
      if ( a4 >= 8 )
      {
        memset(v29, 0, 0x204u);
        FailurePredictThresholds = DiskSendFailurePredictIoctl(DeviceExtension, v29);
        if ( FailurePredictThresholds >= 0 )
        {
          v15 = 0;
          if ( *(_DWORD *)(v10 + 16) == 3 )
            v15 = v29[1];
          v16 = v29[0] == 0;
          *(_DWORD *)a5 = v15;
          a5[4] = !v16;
        }
        goto LABEL_5;
      }
      goto LABEL_20;
    }
    v17 = v14 - 1;
    if ( v17 )
    {
      v18 = v17 - 3;
      if ( !v18 )
      {
        v12 = 512;
        if ( a4 >= 0x200 )
        {
          FailurePredictThresholds = DiskReadFailurePredictThresholds((int)DeviceExtension);
          goto LABEL_5;
        }
        goto LABEL_20;
      }
      if ( v18 != 1 )
      {
        FailurePredictThresholds = -1073741163;
        goto LABEL_4;
      }
      v12 = 12;
      v27 = 0;
      v28 = 0;
      if ( a4 < 0xC )
      {
LABEL_20:
        FailurePredictThresholds = -1073741789;
        goto LABEL_5;
      }
      FailurePredictThresholds = DiskGetInfoExceptionInformation((__int64)DeviceExtension, (__int64)&v27);
      if ( FailurePredictThresholds >= 0 )
      {
        v19 = v27;
        a5[6] = BYTE5(v27);
        a5[5] = BYTE6(v27);
        a5[4] = HIBYTE(v27);
        v20 = v28;
        *a5 = v19 >> 7;
        v21 = BYTE2(v27);
        a5[11] = v20;
        v22 = BYTE1(v28);
        a5[1] = v21;
        v23 = BYTE3(v27);
        a5[10] = v22;
        a5[9] = BYTE2(v28);
        v24 = HIBYTE(v28);
        a5[2] = v23 & 0xF;
        v25 = BYTE4(v27);
        a5[8] = v24;
        a5[3] = 0;
        a5[7] = v25;
      }
    }
    else
    {
      v12 = 516;
      if ( a4 < 0x204 )
        goto LABEL_20;
      FailurePredictThresholds = DiskSendFailurePredictIoctl(DeviceExtension, a5);
      if ( FailurePredictThresholds >= 0 )
        *(_DWORD *)a5 = 512;
    }
  }
  else
  {
    v12 = 24;
    if ( a4 < 0x18 )
      goto LABEL_20;
    if ( (DeviceObject->Characteristics & 1) == 0
      || (DriveCapacity = ClassReadDriveCapacity(*(PDEVICE_OBJECT *)(DeviceExtension[3] + 8LL)),
          *(_DWORD *)(v10 + 4) = DriveCapacity,
          FailurePredictThresholds = DriveCapacity,
          DriveCapacity >= 0) )
    {
      memmove(a5, DeviceExtension + 69, 0x18u);
      FailurePredictThresholds = 0;
    }
  }
LABEL_5:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qqL(WPP_GLOBAL_Control->AttachedDevice, 39, a3, DeviceObject, Irp, FailurePredictThresholds);
  }
  return ClassWmiCompleteRequest(DeviceObject, Irp, FailurePredictThresholds, v12, 0);
}

```

## disassembly

```asm
0x140014200  mov     [rsp+arg_10], rbx
0x140014205  push    rbp
0x140014206  push    rsi
0x140014207  push    rdi
0x140014208  push    r12
0x14001420a  push    r13
0x14001420c  push    r14
0x14001420e  push    r15
0x140014210  sub     rsp, 270h
0x140014217  mov     rax, cs:__security_cookie
0x14001421e  xor     rax, rsp
0x140014221  mov     [rsp+2A8h+var_48], rax
0x140014229  mov     r14, [rcx+40h]
0x14001422d  mov     r15d, r9d
0x140014230  mov     r12, [rsp+2A8h+arg_20]
0x140014238  mov     ebx, r8d
0x14001423b  mov     rbp, rdx
0x14001423e  mov     rdi, rcx
0x140014241  mov     r13, [r14+60h]
0x140014245  mov     rcx, cs:WPP_GLOBAL_Control
0x14001424c  lea     rsi, WPP_GLOBAL_Control
0x140014253  cmp     rcx, rsi
0x140014256  jnz     short loc_1400142C7
0x140014258  cmp     ebx, 3
0x14001425b  jnz     loc_1400142F8
0x140014261  xor     eax, eax
0x140014263  mov     ebx, eax
0x140014265  mov     esi, eax
0x140014267  mov     rcx, cs:WPP_GLOBAL_Control
0x14001426e  lea     rax, WPP_GLOBAL_Control
0x140014275  cmp     rcx, rax
0x140014278  jnz     loc_14001435E
0x14001427e  mov     r9d, esi; BufferUsed
0x140014281  mov     [rsp+2A8h+PriorityBoost], 0; PriorityBoost
0x140014286  mov     r8d, ebx; Status
0x140014289  mov     rdx, rbp; Irp
0x14001428c  mov     rcx, rdi; DeviceObject
0x14001428f  call    cs:__imp_ClassWmiCompleteRequest
0x140014296  nop     dword ptr [rax+rax+00h]
0x14001429b  mov     rcx, [rsp+2A8h+var_48]
0x1400142a3  xor     rcx, rsp; StackCookie
0x1400142a6  call    __security_check_cookie
0x1400142ab  mov     rbx, [rsp+2A8h+arg_10]
0x1400142b3  add     rsp, 270h
0x1400142ba  pop     r15
0x1400142bc  pop     r14
0x1400142be  pop     r13
0x1400142c0  pop     r12
0x1400142c2  pop     rdi
0x1400142c3  pop     rsi
0x1400142c4  pop     rbp
0x1400142c5  retn
0x1400142c7  mov     eax, [rcx+2Ch]
0x1400142ca  test    al, 40h
0x1400142cc  jz      short loc_140014258
0x1400142ce  cmp     byte ptr [rcx+29h], 4
0x1400142d2  jb      short loc_140014258
0x1400142d4  mov     rcx, [rcx+18h]
0x1400142d8  mov     r9, rdi
0x1400142db  mov     [rsp+2A8h+var_270], r12
0x1400142e0  mov     [rsp+2A8h+var_278], r15d
0x1400142e5  mov     [rsp+2A8h+var_280], ebx
0x1400142e9  mov     qword ptr [rsp+2A8h+PriorityBoost], rbp
0x1400142ee  call    WPP_SF_qqdLq
0x1400142f3  jmp     loc_140014258
0x1400142f8  test    ebx, ebx
0x1400142fa  jz      loc_1400144B9
0x140014300  sub     ebx, 1
0x140014303  jnz     loc_14001439C
0x140014309  mov     esi, 8
0x14001430e  cmp     r15d, esi
0x140014311  jb      short loc_140014392
0x140014313  xor     edx, edx; Val
0x140014315  lea     rcx, [rsp+2A8h+var_258]; void *
0x14001431a  mov     r8d, 204h; Size
0x140014320  call    memset
0x140014325  lea     rdx, [rsp+2A8h+var_258]
0x14001432a  mov     rcx, r14
0x14001432d  call    DiskSendFailurePredictIoctl
0x140014332  mov     ebx, eax
0x140014334  test    eax, eax
0x140014336  js      loc_140014267
0x14001433c  xor     eax, eax
0x14001433e  cmp     dword ptr [r13+10h], 3
0x140014343  cmovz   eax, [rsp+2A8h+var_254]
0x140014348  cmp     [rsp+2A8h+var_258], 0
0x14001434d  mov     [r12], eax
0x140014351  setnz   al
0x140014354  mov     [r12+4], al
0x140014359  jmp     loc_140014267
0x14001435e  mov     eax, [rcx+2Ch]
0x140014361  test    al, 40h
0x140014363  jz      loc_14001427E
0x140014369  cmp     byte ptr [rcx+29h], 4
0x14001436d  jb      loc_14001427E
0x140014373  mov     rcx, [rcx+18h]
0x140014377  mov     edx, 27h ; '''
0x14001437c  mov     [rsp+2A8h+var_280], ebx
0x140014380  mov     r9, rdi
0x140014383  mov     qword ptr [rsp+2A8h+PriorityBoost], rbp
0x140014388  call    WPP_SF_qqL
0x14001438d  jmp     loc_14001427E
0x140014392  mov     ebx, 0C0000023h
0x140014397  jmp     loc_140014267
0x14001439c  sub     ebx, 1
0x14001439f  jz      loc_140014489
0x1400143a5  sub     ebx, 3
0x1400143a8  jz      loc_140014469
0x1400143ae  cmp     ebx, 1
0x1400143b1  jz      short loc_1400143BF
0x1400143b3  xor     eax, eax
0x1400143b5  mov     ebx, 0C0000295h
0x1400143ba  jmp     loc_140014265
0x1400143bf  xor     eax, eax
0x1400143c1  mov     esi, 0Ch
0x1400143c6  mov     [rsp+2A8h+var_268], rax
0x1400143cb  mov     [rsp+2A8h+var_260], eax
0x1400143cf  cmp     r15d, esi
0x1400143d2  jb      short loc_140014392
0x1400143d4  lea     rdx, [rsp+2A8h+var_268]
0x1400143d9  mov     rcx, r14
0x1400143dc  call    DiskGetInfoExceptionInformation
0x1400143e1  mov     ebx, eax
0x1400143e3  test    eax, eax
0x1400143e5  js      loc_140014267
0x1400143eb  movzx   eax, byte ptr [rsp+2A8h+var_268+5]
0x1400143f0  movzx   ecx, byte ptr [rsp+2A8h+var_268]
0x1400143f5  mov     [r12+6], al
0x1400143fa  movzx   eax, byte ptr [rsp+2A8h+var_268+6]
0x1400143ff  mov     [r12+5], al
0x140014404  movzx   eax, byte ptr [rsp+2A8h+var_268+7]
0x140014409  shr     cl, 7
0x14001440c  mov     [r12+4], al
0x140014411  movzx   eax, byte ptr [rsp+2A8h+var_260]
0x140014416  mov     [r12], cl
0x14001441a  movzx   ecx, byte ptr [rsp+2A8h+var_268+2]
0x14001441f  mov     [r12+0Bh], al
0x140014424  movzx   eax, byte ptr [rsp+2A8h+var_260+1]
0x140014429  mov     [r12+1], cl
0x14001442e  movzx   ecx, byte ptr [rsp+2A8h+var_268+3]
0x140014433  mov     [r12+0Ah], al
0x140014438  and     cl, 0Fh
0x14001443b  movzx   eax, byte ptr [rsp+2A8h+var_260+2]
0x140014440  mov     [r12+9], al
0x140014445  movzx   eax, byte ptr [rsp+2A8h+var_260+3]
0x14001444a  mov     [r12+2], cl
0x14001444f  movzx   ecx, byte ptr [rsp+2A8h+var_268+4]
0x140014454  mov     [r12+8], al
0x140014459  mov     byte ptr [r12+3], 0
0x14001445f  mov     [r12+7], cl
0x140014464  jmp     loc_140014267
0x140014469  mov     esi, 200h
0x14001446e  cmp     r15d, esi
0x140014471  jb      loc_140014392
0x140014477  mov     rdx, r12
0x14001447a  mov     rcx, r14; int
0x14001447d  call    DiskReadFailurePredictThresholds
0x140014482  mov     ebx, eax
0x140014484  jmp     loc_140014267
0x140014489  mov     esi, 204h
0x14001448e  cmp     r15d, esi
0x140014491  jb      loc_140014392
0x140014497  mov     rdx, r12
0x14001449a  mov     rcx, r14
0x14001449d  call    DiskSendFailurePredictIoctl
0x1400144a2  mov     ebx, eax
0x1400144a4  test    eax, eax
0x1400144a6  js      loc_140014267
0x1400144ac  mov     dword ptr [r12], 200h
0x1400144b4  jmp     loc_140014267
0x1400144b9  mov     esi, 18h
0x1400144be  cmp     r15d, esi
0x1400144c1  jb      loc_140014392
0x1400144c7  mov     eax, [rdi+34h]
0x1400144ca  test    al, 1
0x1400144cc  jz      short loc_1400144F0
0x1400144ce  mov     rcx, [r14+18h]
0x1400144d2  mov     rcx, [rcx+8]; DeviceObject
0x1400144d6  call    cs:__imp_ClassReadDriveCapacity
0x1400144dd  nop     dword ptr [rax+rax+00h]
0x1400144e2  mov     [r13+4], eax
0x1400144e6  mov     ebx, eax
0x1400144e8  test    eax, eax
0x1400144ea  js      loc_140014267
0x1400144f0  lea     rdx, [r14+228h]; Src
0x1400144f7  mov     r8, rsi; Size
0x1400144fa  mov     rcx, r12; void *
0x1400144fd  call    memmove
0x140014502  xor     eax, eax
0x140014504  mov     ebx, eax
0x140014506  jmp     loc_140014267
```
