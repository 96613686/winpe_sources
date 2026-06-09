# DiskIoctlVerifyThread

- ea: `0x14000f330`
- end: `0x14000f74a`
- name: `DiskIoctlVerifyThread`
- size: `1050`
- prototype: `IO_WORKITEM_ROUTINE`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140004078`
- `0x140006000`
- `0x14000f330`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x14000f3f4`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000f3f4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f4dd`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f4f1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f716`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f72c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f4dd`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f4f1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f716`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f72c`
- `ntoskrnl!IoFreeWorkItem` at `0x14000f36c`
- `ntoskrnl!IoFreeWorkItem` at `0x14000f36c`
- `ntoskrnl!KeReleaseMutex` at `0x14000f6cd`
- `ntoskrnl!KeReleaseMutex` at `0x14000f6cd`
- `ntoskrnl!IoGetIoPriorityHint` at `0x14000f440`
- `ntoskrnl!IoGetIoPriorityHint` at `0x14000f440`
- `CLASSPNP!ClassReleaseRemoveLock` at `0x14000f6eb`
- `CLASSPNP!ClassReleaseRemoveLock` at `0x14000f6eb`
- `CLASSPNP!ClassCompleteRequest` at `0x14000f700`
- `CLASSPNP!ClassCompleteRequest` at `0x14000f700`
- `CLASSPNP!ClassSendSrbSynchronous` at `0x14000f67c`
- `CLASSPNP!ClassSendSrbSynchronous` at `0x14000f67c`

## pseudocode

```c
void __fastcall DiskIoctlVerifyThread(PDEVICE_OBJECT DeviceObject, PVOID Context)
{
  _QWORD *DeviceExtension; // rbp
  struct _DEVICE_OBJECT *v3; // r15
  IRP *v4; // r13
  __int64 v6; // rdi
  struct _KMUTANT *v7; // r12
  __int64 v8; // rsi
  struct _KMUTANT *v9; // rax
  __int64 v10; // rbx
  NTSTATUS v11; // r12d
  __int16 IoPriorityHint; // ax
  _BYTE *v13; // rsi
  __int64 v14; // r10
  __int16 v15; // dx
  PVOID v16; // r14
  unsigned int v17; // r13d
  unsigned __int16 v18; // r15
  unsigned int v19; // ecx
  __int64 v20; // [rsp+30h] [rbp-68h]
  __int64 v21; // [rsp+38h] [rbp-60h]
  IRP *v22; // [rsp+40h] [rbp-58h]
  struct _KMUTANT *Mutex; // [rsp+48h] [rbp-50h]
  char v26; // [rsp+B0h] [rbp+18h]
  unsigned int v27; // [rsp+B8h] [rbp+20h]

  DeviceExtension = DeviceObject->DeviceExtension;
  v3 = DeviceObject;
  v4 = *(IRP **)Context;
  v6 = *((_QWORD *)Context + 1);
  v7 = (struct _KMUTANT *)DeviceExtension[12];
  v8 = *(_QWORD *)(*(_QWORD *)Context + 24LL);
  v22 = *(IRP **)Context;
  IoFreeWorkItem(*((PIO_WORKITEM *)Context + 2));
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 41, WPP_0d021951613e35be7880fae860fb7f50_Traceguids);
  }
  v26 = *((_BYTE *)DeviceExtension + 642);
  v27 = *(_DWORD *)(v8 + 8);
  v9 = v7 + 1;
  v10 = (__int64)(*(_QWORD *)v8 + DeviceExtension[19]) >> v26;
  v11 = 0;
  Mutex = v9;
  KeWaitForSingleObject(v9, Executive, 0, 0, 0);
  if ( *(_BYTE *)(DeviceExtension[66] + 30LL) != 1 )
  {
    v21 = 0;
    v20 = 0;
    memset((void *)(v6 + 3), 0, 0x55u);
    *(_WORD *)v6 = 88;
    *(_BYTE *)(v6 + 2) = 0;
    v13 = (_BYTE *)(v6 + 72);
    v14 = 0;
    if ( (DeviceExtension[80] & 0x20) != 0 )
    {
      *(_BYTE *)(v6 + 10) = 16;
      *v13 = -113;
    }
    else
    {
      *(_BYTE *)(v6 + 10) = 10;
      *v13 = 47;
    }
LABEL_14:
    v17 = v27 >> v26;
    do
    {
      if ( !v17 )
        break;
      v18 = v17 >= 0x100 ? 256 : v17;
      v19 = ((unsigned int)v18 + 127) >> 7;
      if ( *(_BYTE *)(DeviceExtension[66] + 30LL) == 1 )
      {
        *(_BYTE *)(v14 + 3) = 0;
        *(_BYTE *)(v21 + 8) = 0;
        *(_DWORD *)(v14 + 40) = *((_DWORD *)DeviceExtension + 146) * v19;
      }
      else
      {
        *(_WORD *)(v6 + 3) = 0;
        *(_DWORD *)(v6 + 20) = *((_DWORD *)DeviceExtension + 146) * v19;
      }
      if ( (DeviceExtension[80] & 0x20) != 0 )
      {
        v13[8] = BYTE1(v10);
        v13[7] = BYTE2(v10);
        v13[6] = BYTE3(v10);
        v13[5] = BYTE4(v10);
        v13[4] = BYTE5(v10);
        v13[3] = BYTE6(v10);
        v13[2] = HIBYTE(v10);
        v13[12] = HIBYTE(v18);
        v13[9] = v10;
        v13[13] = v18;
      }
      else
      {
        v13[2] = BYTE3(v10);
        v13[3] = BYTE2(v10);
        v13[4] = BYTE1(v10);
        v13[7] = HIBYTE(v18);
        v13[5] = v10;
        v13[8] = v18;
      }
      v17 -= v18;
      v11 = ClassSendSrbSynchronous(DeviceObject, (PSCSI_REQUEST_BLOCK)v6, 0, 0, 0);
      v14 = v20;
      v10 += v18;
    }
    while ( v11 >= 0 );
    v16 = Context;
    v4 = v22;
    v3 = DeviceObject;
    goto LABEL_27;
  }
  memset((void *)v6, 0, 0xB8u);
  *(_WORD *)v6 = 8;
  *(_BYTE *)(v6 + 2) = 40;
  *(_DWORD *)(v6 + 8) = 1397899864;
  *(_DWORD *)(v6 + 12) = 1;
  *(_DWORD *)(v6 + 16) = 184;
  IoPriorityHint = IoGetIoPriorityHint(v4);
  *(_DWORD *)(v6 + 52) = 128;
  *(_DWORD *)(v6 + 56) = 1;
  *(_WORD *)(v6 + 36) = IoPriorityHint;
  *(_WORD *)(v6 + 128) = 1;
  *(_DWORD *)(v6 + 132) = 4;
  *(_DWORD *)(v6 + 120) = 144;
  if ( *(_DWORD *)(v6 + 16) >= 0xB8u )
  {
    v20 = v6;
    *(_DWORD *)(v6 + 144) = 64;
    *(_DWORD *)(v6 + 148) = 32;
    v13 = (_BYTE *)(v6 + 168);
    v14 = v6;
    v15 = DeviceExtension[80] & 0x20;
    v21 = v6 + 144;
    *(_BYTE *)(v6 + 154) = v15 != 0 ? 16 : 10;
    *(_BYTE *)(v6 + 168) = v15 != 0 ? -113 : 47;
    goto LABEL_14;
  }
  if ( v6 )
  {
    ExFreePoolWithTag((PVOID)v6, 0);
    v6 = 0;
  }
  ExFreePoolWithTag(Context, 0);
  v16 = 0;
  v11 = -1073741595;
LABEL_27:
  KeReleaseMutex(Mutex, 0);
  v4->IoStatus.Status = v11;
  v4->IoStatus.Information = 0;
  ClassReleaseRemoveLock(v3, v4);
  ClassCompleteRequest(v3, v4, 0);
  if ( v6 )
    ExFreePoolWithTag((PVOID)v6, 0);
  if ( v16 )
    ExFreePoolWithTag(v16, 0);
}

```

## disassembly

```asm
0x14000f330  mov     [rsp+arg_8], rdx
0x14000f335  mov     [rsp+DeviceObject], rcx
0x14000f33a  push    rbx
0x14000f33b  push    rbp
0x14000f33c  push    rsi
0x14000f33d  push    rdi
0x14000f33e  push    r12
0x14000f340  push    r13
0x14000f342  push    r14
0x14000f344  push    r15
0x14000f346  sub     rsp, 58h
0x14000f34a  mov     rbp, [rcx+40h]
0x14000f34e  mov     r15, rcx
0x14000f351  mov     r13, [rdx]
0x14000f354  mov     r14, rdx
0x14000f357  mov     rcx, [rdx+10h]; IoWorkItem
0x14000f35b  mov     rdi, [rdx+8]
0x14000f35f  mov     r12, [rbp+60h]
0x14000f363  mov     rsi, [r13+18h]
0x14000f367  mov     [rsp+98h+var_58], r13
0x14000f36c  call    cs:__imp_IoFreeWorkItem
0x14000f373  nop     dword ptr [rax+rax+00h]
0x14000f378  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f37f  lea     rax, WPP_GLOBAL_Control
0x14000f386  cmp     rcx, rax
0x14000f389  jz      short loc_14000F3AD
0x14000f38b  mov     eax, [rcx+2Ch]
0x14000f38e  test    al, 10h
0x14000f390  jz      short loc_14000F3AD
0x14000f392  cmp     byte ptr [rcx+29h], 4
0x14000f396  jb      short loc_14000F3AD
0x14000f398  mov     rcx, [rcx+18h]
0x14000f39c  lea     r8, WPP_0d021951613e35be7880fae860fb7f50_Traceguids
0x14000f3a3  mov     edx, 29h ; ')'
0x14000f3a8  call    WPP_SF_
0x14000f3ad  mov     cl, [rbp+282h]
0x14000f3b3  xor     r9d, r9d; Alertable
0x14000f3b6  mov     al, [rbp+282h]
0x14000f3bc  xor     r8d, r8d; WaitMode
0x14000f3bf  mov     rbx, [rbp+98h]
0x14000f3c6  xor     edx, edx; WaitReason
0x14000f3c8  add     rbx, [rsi]
0x14000f3cb  mov     byte ptr [rsp+98h+arg_10], al
0x14000f3d2  mov     eax, [rsi+8]
0x14000f3d5  mov     [rsp+98h+arg_18], eax
0x14000f3dc  lea     rax, [r12+38h]
0x14000f3e1  sar     rbx, cl
0x14000f3e4  xor     r12d, r12d
0x14000f3e7  mov     rcx, rax; Object
0x14000f3ea  mov     [rsp+98h+Timeout], r12; Timeout
0x14000f3ef  mov     [rsp+98h+Mutex], rax
0x14000f3f4  call    cs:__imp_KeWaitForSingleObject
0x14000f3fb  nop     dword ptr [rax+rax+00h]
0x14000f400  mov     rax, [rbp+210h]
0x14000f407  xor     edx, edx; Val
0x14000f409  cmp     byte ptr [rax+1Eh], 1
0x14000f40d  jnz     loc_14000F50B
0x14000f413  mov     esi, 0B8h
0x14000f418  mov     rcx, rdi; void *
0x14000f41b  mov     r8d, esi; Size
0x14000f41e  call    memset
0x14000f423  mov     rcx, r13; Irp
0x14000f426  mov     word ptr [rdi], 8
0x14000f42b  mov     byte ptr [rdi+2], 28h ; '('
0x14000f42f  mov     dword ptr [rdi+8], 53524258h
0x14000f436  mov     dword ptr [rdi+0Ch], 1
0x14000f43d  mov     [rdi+10h], esi
0x14000f440  call    cs:__imp_IoGetIoPriorityHint
0x14000f447  nop     dword ptr [rax+rax+00h]
0x14000f44c  mov     dword ptr [rdi+34h], 80h
0x14000f453  lea     r11d, [r12+1]
0x14000f458  mov     [rdi+38h], r11d
0x14000f45c  mov     [rdi+24h], ax
0x14000f460  mov     [rdi+80h], r11w
0x14000f468  mov     dword ptr [rdi+84h], 4
0x14000f472  mov     dword ptr [rdi+78h], 90h
0x14000f479  cmp     [rdi+10h], esi
0x14000f47c  jb      short loc_14000F4D3
0x14000f47e  lea     r8, [rdi+90h]
0x14000f485  mov     [rsp+98h+var_68], rdi
0x14000f48a  mov     dword ptr [r8], 40h ; '@'
0x14000f491  lea     r9d, [r12+20h]
0x14000f496  mov     [r8+4], r9d
0x14000f49a  lea     rsi, [r8+18h]
0x14000f49e  movzx   edx, word ptr [rbp+280h]
0x14000f4a5  mov     r10, rdi
0x14000f4a8  and     dx, r9w
0x14000f4ac  mov     [rsp+98h+var_60], r8
0x14000f4b1  movzx   eax, dx
0x14000f4b4  neg     ax
0x14000f4b7  sbb     cl, cl
0x14000f4b9  and     cl, 6
0x14000f4bc  add     cl, 0Ah
0x14000f4bf  neg     dx
0x14000f4c2  mov     [r8+0Ah], cl
0x14000f4c6  sbb     al, al
0x14000f4c8  and     al, 60h
0x14000f4ca  add     al, 2Fh ; '/'
0x14000f4cc  mov     [rsi], al
0x14000f4ce  jmp     loc_14000F55A
0x14000f4d3  test    rdi, rdi
0x14000f4d6  jz      short loc_14000F4EC
0x14000f4d8  xor     edx, edx; Tag
0x14000f4da  mov     rcx, rdi; P
0x14000f4dd  call    cs:__imp_ExFreePoolWithTag
0x14000f4e4  nop     dword ptr [rax+rax+00h]
0x14000f4e9  mov     rdi, r12
0x14000f4ec  xor     edx, edx; Tag
0x14000f4ee  mov     rcx, r14; P
0x14000f4f1  call    cs:__imp_ExFreePoolWithTag
0x14000f4f8  nop     dword ptr [rax+rax+00h]
0x14000f4fd  mov     r14, r12
0x14000f500  mov     r12d, 0C00000E5h
0x14000f506  jmp     loc_14000F6C6
0x14000f50b  lea     rcx, [rdi+3]; void *
0x14000f50f  mov     [rsp+98h+var_60], r12
0x14000f514  mov     r8d, 55h ; 'U'; Size
0x14000f51a  mov     [rsp+98h+var_68], r12
0x14000f51f  call    memset
0x14000f524  mov     r9d, 20h ; ' '
0x14000f52a  mov     word ptr [rdi], 58h ; 'X'
0x14000f52f  mov     [rdi+2], r12b
0x14000f533  lea     rsi, [rdi+48h]
0x14000f537  movzx   eax, word ptr [rbp+280h]
0x14000f53e  mov     r10, r12
0x14000f541  lea     r11d, [r9-1Fh]
0x14000f545  test    r9b, al
0x14000f548  jz      short loc_14000F553
0x14000f54a  mov     byte ptr [rdi+0Ah], 10h
0x14000f54e  mov     byte ptr [rsi], 8Fh
0x14000f551  jmp     short loc_14000F55A
0x14000f553  mov     byte ptr [rdi+0Ah], 0Ah
0x14000f557  mov     byte ptr [rsi], 2Fh ; '/'
0x14000f55a  mov     cl, byte ptr [rsp+98h+arg_10]
0x14000f561  mov     r13d, [rsp+98h+arg_18]
0x14000f569  mov     r14, [rsp+98h+var_60]
0x14000f56e  shr     r13d, cl
0x14000f571  xor     edx, edx
0x14000f573  test    r13d, r13d
0x14000f576  jz      loc_14000F6B1
0x14000f57c  cmp     r13d, 100h
0x14000f583  jnb     short loc_14000F58B
0x14000f585  movzx   r15d, r13w
0x14000f589  jmp     short loc_14000F591
0x14000f58b  mov     r15d, 100h
0x14000f591  movzx   eax, r15w
0x14000f595  mov     [rsp+98h+arg_10], eax
0x14000f59c  lea     ecx, [rax+7Fh]
0x14000f59f  mov     rax, [rbp+210h]
0x14000f5a6  shr     ecx, 7
0x14000f5a9  cmp     [rax+1Eh], r11b
0x14000f5ad  jnz     short loc_14000F5C4
0x14000f5af  mov     [r10+3], dl
0x14000f5b3  mov     [r14+8], dl
0x14000f5b7  imul    ecx, [rbp+248h]
0x14000f5be  mov     [r10+28h], ecx
0x14000f5c2  jmp     short loc_14000F5D4
0x14000f5c4  mov     word ptr [rdi+3], 0
0x14000f5ca  imul    ecx, [rbp+248h]
0x14000f5d1  mov     [rdi+14h], ecx
0x14000f5d4  movzx   eax, word ptr [rbp+280h]
0x14000f5db  test    r9b, al
0x14000f5de  mov     rax, rbx
0x14000f5e1  jz      short loc_14000F63A
0x14000f5e3  shr     rax, 8
0x14000f5e7  mov     [rsi+8], al
0x14000f5ea  mov     rax, rbx
0x14000f5ed  shr     rax, 10h
0x14000f5f1  mov     [rsi+7], al
0x14000f5f4  mov     rax, rbx
0x14000f5f7  shr     rax, 18h
0x14000f5fb  mov     [rsi+6], al
0x14000f5fe  mov     rax, rbx
0x14000f601  shr     rax, 20h
0x14000f605  mov     [rsi+5], al
0x14000f608  mov     rax, rbx
0x14000f60b  shr     rax, 28h
0x14000f60f  mov     [rsi+4], al
0x14000f612  mov     rax, rbx
0x14000f615  shr     rax, 30h
0x14000f619  mov     [rsi+3], al
0x14000f61c  mov     rax, rbx
0x14000f61f  shr     rax, 38h
0x14000f623  mov     [rsi+2], al
0x14000f626  movzx   eax, r15w
0x14000f62a  shr     ax, 8
0x14000f62e  mov     [rsi+0Ch], al
0x14000f631  mov     [rsi+9], bl
0x14000f634  mov     [rsi+0Dh], r15b
0x14000f638  jmp     short loc_14000F667
0x14000f63a  shr     rax, 18h
0x14000f63e  mov     [rsi+2], al
0x14000f641  mov     rax, rbx
0x14000f644  shr     rax, 10h
0x14000f648  mov     [rsi+3], al
0x14000f64b  mov     rax, rbx
0x14000f64e  shr     rax, 8
0x14000f652  mov     [rsi+4], al
0x14000f655  movzx   eax, r15w
0x14000f659  shr     ax, 8
0x14000f65d  mov     [rsi+7], al
0x14000f660  mov     [rsi+5], bl
0x14000f663  mov     [rsi+8], r15b
0x14000f667  mov     rcx, [rsp+98h+DeviceObject]; DeviceObject
0x14000f66f  xor     r9d, r9d; BufferLength
0x14000f672  mov     byte ptr [rsp+98h+Timeout], dl; WriteToDevice
0x14000f676  xor     r8d, r8d; BufferAddress
0x14000f679  mov     rdx, rdi; Srb
0x14000f67c  call    cs:__imp_ClassSendSrbSynchronous
0x14000f683  nop     dword ptr [rax+rax+00h]
0x14000f688  sub     r13d, [rsp+98h+arg_10]
0x14000f690  mov     r12d, eax
0x14000f693  mov     r10, [rsp+98h+var_68]
0x14000f698  movzx   edx, r15w
0x14000f69c  add     rbx, rdx
0x14000f69f  xor     edx, edx
0x14000f6a1  lea     r9d, [rdx+20h]
0x14000f6a5  lea     r11d, [rdx+1]
0x14000f6a9  test    eax, eax
0x14000f6ab  jns     loc_14000F573
0x14000f6b1  mov     r14, [rsp+98h+arg_8]
0x14000f6b9  mov     r13, [rsp+98h+var_58]
0x14000f6be  mov     r15, [rsp+98h+DeviceObject]
0x14000f6c6  mov     rcx, [rsp+98h+Mutex]; Mutex
0x14000f6cb  xor     edx, edx; Wait
0x14000f6cd  call    cs:__imp_KeReleaseMutex
0x14000f6d4  nop     dword ptr [rax+rax+00h]
0x14000f6d9  mov     rdx, r13; Tag
0x14000f6dc  mov     [r13+30h], r12d
0x14000f6e0  mov     rcx, r15; DeviceObject
0x14000f6e3  mov     qword ptr [r13+38h], 0
0x14000f6eb  call    cs:__imp_ClassReleaseRemoveLock
0x14000f6f2  nop     dword ptr [rax+rax+00h]
0x14000f6f7  xor     r8d, r8d; PriorityBoost
0x14000f6fa  mov     rdx, r13; Irp
0x14000f6fd  mov     rcx, r15; DeviceObject
0x14000f700  call    cs:__imp_ClassCompleteRequest
0x14000f707  nop     dword ptr [rax+rax+00h]
0x14000f70c  test    rdi, rdi
0x14000f70f  jz      short loc_14000F722
0x14000f711  xor     edx, edx; Tag
0x14000f713  mov     rcx, rdi; P
0x14000f716  call    cs:__imp_ExFreePoolWithTag
0x14000f71d  nop     dword ptr [rax+rax+00h]
0x14000f722  test    r14, r14
0x14000f725  jz      short loc_14000F738
0x14000f727  xor     edx, edx; Tag
0x14000f729  mov     rcx, r14; P
0x14000f72c  call    cs:__imp_ExFreePoolWithTag
0x14000f733  nop     dword ptr [rax+rax+00h]
0x14000f738  add     rsp, 58h
0x14000f73c  pop     r15
0x14000f73e  pop     r14
0x14000f740  pop     r13
0x14000f742  pop     r12
0x14000f744  pop     rdi
0x14000f745  pop     rsi
0x14000f746  pop     rbp
0x14000f747  pop     rbx
0x14000f748  retn
```
