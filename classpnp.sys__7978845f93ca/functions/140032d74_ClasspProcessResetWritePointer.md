# ClasspProcessResetWritePointer

- ea: `0x140032d74`
- end: `0x140032f13`
- name: `ClasspProcessResetWritePointer`
- size: `415`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT DeviceObject, PIRP Irp)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140019de0`

## callees

- `0x140001130`
- `0x1400018a0`
- `0x140005190`
- `0x1400134a0`
- `0x140015bf0`
- `0x14002f0dc`
- `0x140032d74`
- `0x1400371a0`
- `0x14003e430`

## import_xrefs

- `ntoskrnl!KeQueryUnbiasedInterruptTimePrecise` at `0x140032e5b`
- `ntoskrnl!KeQueryUnbiasedInterruptTimePrecise` at `0x140032e5b`
- `ntoskrnl!IoGetActivityIdIrp` at `0x140032dc3`
- `ntoskrnl!IoGetActivityIdIrp` at `0x140032dc3`

## pseudocode

```c
__int64 __fastcall ClasspProcessResetWritePointer(PDEVICE_OBJECT DeviceObject, PIRP Irp, __int64 a3)
{
  PDEVICE_OBJECT *DeviceExtension; // rsi
  _IO_STACK_LOCATION *CurrentStackLocation; // rbp
  _IRP *MasterIrp; // rbx
  __int64 v9; // r8
  unsigned int v10; // ebx
  __int64 v11; // rcx
  unsigned __int8 v12; // bp
  __int64 v13; // r14
  __int64 v14; // rax
  __int64 v15; // r8
  char v16; // al
  int v17; // edx
  unsigned __int64 QpcTimeStamp; // [rsp+50h] [rbp-58h] BYREF
  __int128 v20; // [rsp+58h] [rbp-50h] BYREF

  DeviceExtension = (PDEVICE_OBJECT *)DeviceObject->DeviceExtension;
  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  MasterIrp = Irp->AssociatedIrp.MasterIrp;
  QpcTimeStamp = 0;
  v20 = 0;
  IoGetActivityIdIrp(Irp, &v20);
  if ( !MasterIrp || CurrentStackLocation->Parameters.Create.Options < 0x1C )
    goto LABEL_18;
  if ( !(unsigned __int8)ClasspIsManagedZonedDevice(DeviceObject)
    || (v11 = *((unsigned int *)DeviceExtension + 143), !(_DWORD)v11)
    && (ClassReadDriveCapacity(DeviceExtension[1]) < 0 || (v11 = *((unsigned int *)DeviceExtension + 143), !(_DWORD)v11)) )
  {
    v10 = -1073741808;
    goto LABEL_19;
  }
  v12 = 1;
  if ( ((__int64)MasterIrp->MdlAddress & 1) == 0 )
  {
    v14 = *(&MasterIrp->Flags + 1);
    if ( (_DWORD)v14 && MasterIrp->AssociatedIrp.IrpCount >= 0x10u )
    {
      v12 = 0;
      v13 = *(_QWORD *)((char *)&MasterIrp->Type + v14) / v11;
      goto LABEL_13;
    }
LABEL_18:
    v10 = -1073741811;
    goto LABEL_19;
  }
  v13 = 0;
LABEL_13:
  if ( ClassPnPETWEnabled )
    QpcTimeStamp = KeQueryUnbiasedInterruptTimePrecise(&QpcTimeStamp);
  LOBYTE(v9) = v12;
  v10 = ClasspDeviceIssueResetWritePointerCommand(DeviceExtension, a3, v9, v13);
  if ( ClassPnPETWEnabled )
  {
    v16 = ClasspCalculateTimeDifferenceIn100ns(QpcTimeStamp, 0, v15);
    if ( (BYTE3(WPP_MAIN_CB.Queue.Wcb.CurrentIrp) & 2) != 0 )
      McTemplateK0qxpdtx_EtwWriteTransfer(
        v12,
        v17,
        (unsigned int)&v20,
        *((_DWORD *)DeviceExtension + 147),
        v16,
        (char)Irp,
        v10,
        v12,
        v13);
  }
LABEL_19:
  Irp->IoStatus.Information = 0;
  Irp->IoStatus.Status = v10;
  ClassReleaseRemoveLock(DeviceObject, Irp);
  ClassCompleteRequest(DeviceObject, Irp, 0);
  return v10;
}

```

## disassembly

```asm
0x140032d74  push    rbx
0x140032d76  push    rbp
0x140032d77  push    rsi
0x140032d78  push    rdi
0x140032d79  push    r12
0x140032d7b  push    r14
0x140032d7d  push    r15
0x140032d7f  sub     rsp, 70h
0x140032d83  mov     rax, cs:__security_cookie
0x140032d8a  xor     rax, rsp
0x140032d8d  mov     [rsp+0A8h+var_40], rax
0x140032d92  mov     rsi, [rcx+40h]
0x140032d96  mov     rdi, rdx
0x140032d99  mov     rbp, [rdx+0B8h]
0x140032da0  mov     r15, rcx
0x140032da3  mov     rbx, [rdx+18h]
0x140032da7  xorps   xmm0, xmm0
0x140032daa  mov     rcx, rdi
0x140032dad  mov     [rsp+0A8h+QpcTimeStamp], 0
0x140032db6  lea     rdx, [rsp+0A8h+var_50]
0x140032dbb  mov     r12, r8
0x140032dbe  movups  [rsp+0A8h+var_50], xmm0
0x140032dc3  call    cs:__imp_IoGetActivityIdIrp
0x140032dca  nop     dword ptr [rax+rax+00h]
0x140032dcf  test    rbx, rbx
0x140032dd2  jz      loc_140032ECB
0x140032dd8  cmp     dword ptr [rbp+10h], 1Ch
0x140032ddc  jb      loc_140032ECB
0x140032de2  mov     rcx, r15
0x140032de5  call    ClasspIsManagedZonedDevice
0x140032dea  test    al, al
0x140032dec  jnz     short loc_140032DF8
0x140032dee  mov     ebx, 0C0000010h
0x140032df3  jmp     loc_140032ED0
0x140032df8  mov     ecx, [rsi+23Ch]
0x140032dfe  test    ecx, ecx
0x140032e00  jnz     short loc_140032E19
0x140032e02  mov     rcx, [rsi+8]; DeviceObject
0x140032e06  call    ClassReadDriveCapacity
0x140032e0b  test    eax, eax
0x140032e0d  js      short loc_140032DEE
0x140032e0f  mov     ecx, [rsi+23Ch]
0x140032e15  test    ecx, ecx
0x140032e17  jz      short loc_140032DEE
0x140032e19  mov     eax, [rbx+8]
0x140032e1c  mov     bpl, 1
0x140032e1f  test    bpl, al
0x140032e22  jz      short loc_140032E29
0x140032e24  xor     r14d, r14d
0x140032e27  jmp     short loc_140032E4D
0x140032e29  mov     eax, [rbx+14h]
0x140032e2c  test    eax, eax
0x140032e2e  jz      loc_140032ECB
0x140032e34  cmp     dword ptr [rbx+18h], 10h
0x140032e38  jb      loc_140032ECB
0x140032e3e  mov     rax, [rax+rbx]
0x140032e42  cqo
0x140032e44  idiv    rcx
0x140032e47  xor     bpl, bpl
0x140032e4a  mov     r14, rax
0x140032e4d  cmp     cs:ClassPnPETWEnabled, 0
0x140032e54  jz      short loc_140032E6C
0x140032e56  lea     rcx, [rsp+0A8h+QpcTimeStamp]; QpcTimeStamp
0x140032e5b  call    cs:__imp_KeQueryUnbiasedInterruptTimePrecise
0x140032e62  nop     dword ptr [rax+rax+00h]
0x140032e67  mov     [rsp+0A8h+QpcTimeStamp], rax
0x140032e6c  mov     r9, r14
0x140032e6f  mov     r8b, bpl
0x140032e72  mov     rdx, r12
0x140032e75  mov     rcx, rsi
0x140032e78  call    ClasspDeviceIssueResetWritePointerCommand
0x140032e7d  cmp     cs:ClassPnPETWEnabled, 0
0x140032e84  mov     ebx, eax
0x140032e86  jz      short loc_140032ED0
0x140032e88  mov     rcx, [rsp+0A8h+QpcTimeStamp]
0x140032e8d  xor     edx, edx
0x140032e8f  call    ClasspCalculateTimeDifferenceIn100ns
0x140032e94  test    byte ptr cs:WPP_MAIN_CB.Queue+3Bh, 2
0x140032e9b  jz      short loc_140032ED0
0x140032e9d  mov     r9d, [rsi+24Ch]
0x140032ea4  lea     r8, [rsp+0A8h+var_50]
0x140032ea9  mov     [rsp+0A8h+var_68], r14
0x140032eae  movzx   ecx, bpl
0x140032eb2  mov     [rsp+0A8h+var_70], ecx
0x140032eb6  mov     [rsp+0A8h+var_78], ebx
0x140032eba  mov     [rsp+0A8h+var_80], rdi
0x140032ebf  mov     [rsp+0A8h+var_88], rax
0x140032ec4  call    McTemplateK0qxpdtx_EtwWriteTransfer
0x140032ec9  jmp     short loc_140032ED0
0x140032ecb  mov     ebx, 0C000000Dh
0x140032ed0  mov     rdx, rdi; Tag
0x140032ed3  mov     qword ptr [rdi+38h], 0
0x140032edb  mov     rcx, r15; DeviceObject
0x140032ede  mov     [rdi+30h], ebx
0x140032ee1  call    ClassReleaseRemoveLock
0x140032ee6  xor     r8d, r8d; PriorityBoost
0x140032ee9  mov     rdx, rdi; Irp
0x140032eec  mov     rcx, r15; DeviceObject
0x140032eef  call    ClassCompleteRequest
0x140032ef4  mov     eax, ebx
0x140032ef6  mov     rcx, [rsp+0A8h+var_40]
0x140032efb  xor     rcx, rsp; StackCookie
0x140032efe  call    __security_check_cookie
0x140032f03  add     rsp, 70h
0x140032f07  pop     r15
0x140032f09  pop     r14
0x140032f0b  pop     r12
0x140032f0d  pop     rdi
0x140032f0e  pop     rsi
0x140032f0f  pop     rbp
0x140032f10  pop     rbx
0x140032f11  retn
```
