# ClassIoCompleteAssociated

- ea: `0x140037e10`
- end: `0x1400381c1`
- name: `ClassIoCompleteAssociated`
- size: `945`
- prototype: `IO_COMPLETION_ROUTINE`
- caller_count: `0`
- callee_count: `14`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140005190`
- `0x140008360`
- `0x1400134a0`
- `0x1400157d0`
- `0x140016320`
- `0x1400176f8`
- `0x140017fa0`
- `0x140019130`
- `0x14001fbf4`
- `0x14001fc38`
- `0x14001feac`
- `0x140022668`
- `0x140026640`
- `0x140037e10`

## import_xrefs

- `ntoskrnl!IoFreeIrp` at `0x140038196`
- `ntoskrnl!IoFreeIrp` at `0x140038196`
- `ntoskrnl!IoStartNextPacket` at `0x140038155`
- `ntoskrnl!IoStartNextPacket` at `0x140038155`
- `ntoskrnl!KeLowerIrql` at `0x140038163`
- `ntoskrnl!KeLowerIrql` at `0x140038163`
- `ntoskrnl!IoSetHardErrorOrVerifyDevice` at `0x140038073`
- `ntoskrnl!IoSetHardErrorOrVerifyDevice` at `0x140038073`
- `ntoskrnl!KfRaiseIrql` at `0x140038142`
- `ntoskrnl!KfRaiseIrql` at `0x140038142`

## pseudocode

```c
NTSTATUS __stdcall ClassIoCompleteAssociated(PDEVICE_OBJECT DeviceObject, PIRP Irp, PVOID Context)
{
  __int64 v3; // r9
  struct _FUNCTIONAL_DEVICE_EXTENSION *DeviceExtension; // r13
  _IO_STACK_LOCATION *CurrentStackLocation; // r15
  _IRP *MasterIrp; // rdi
  unsigned int LowPart; // ecx
  char v11; // al
  unsigned int EaLength; // edx
  struct _SCSI_REQUEST_BLOCK *v13; // rdx
  struct _FUNCTIONAL_DEVICE_EXTENSION *v14; // rcx
  int v15; // r9d
  struct _SCSI_REQUEST_BLOCK *v16; // rdx
  struct _FUNCTIONAL_DEVICE_EXTENSION *v17; // rcx
  int v18; // edx
  _IO_STACK_LOCATION *v19; // r15
  unsigned __int32 v20; // ebx
  KIRQL v21; // bl
  __int64 Tag; // [rsp+70h] [rbp+30h] BYREF
  NTSTATUS v24; // [rsp+78h] [rbp+38h] BYREF

  DeviceExtension = (struct _FUNCTIONAL_DEVICE_EXTENSION *)DeviceObject->DeviceExtension;
  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  MasterIrp = Irp->AssociatedIrp.MasterIrp;
  v24 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_fdfccdbcc72438cfb0f431eafc7dd1cf_Traceguids);
  }
  if ( (*((_BYTE *)Context + 3) & 0x3F) == 1 )
  {
    v24 = 0;
    goto LABEL_28;
  }
  Tag = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_fdfccdbcc72438cfb0f431eafc7dd1cf_Traceguids, Irp, Context);
  }
  if ( (*((_BYTE *)Context + 3) & 0x40) != 0 )
    ClasspReleaseQueue((ULONG_PTR)DeviceObject, 0);
  if ( CurrentStackLocation->MajorFunction == 14 )
    LowPart = CurrentStackLocation->Parameters.Read.ByteOffset.LowPart;
  else
    LowPart = 0;
  LOBYTE(v3) = CurrentStackLocation->MajorFunction;
  v11 = InterpretSenseInfoWithoutHistory(
          DeviceObject,
          Irp,
          Context,
          v3,
          LowPart,
          4 - CurrentStackLocation->Parameters.Create.EaLength,
          &v24,
          &Tag);
  if ( (CurrentStackLocation->Flags & 2) != 0 && v24 == -2147483626 )
  {
    v24 = -1073741435;
  }
  else if ( !v11 )
  {
    goto LABEL_28;
  }
  EaLength = CurrentStackLocation->Parameters.Create.EaLength;
  CurrentStackLocation->Parameters.CreatePipe.Parameters = (_NAMED_PIPE_CREATE_PARAMETERS *)(EaLength - 1);
  if ( EaLength )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_fdfccdbcc72438cfb0f431eafc7dd1cf_Traceguids, Irp);
    }
    if ( PORT_ALLOCATED_SENSE(DeviceExtension, (PSCSI_REQUEST_BLOCK)Context) )
      FREE_PORT_ALLOCATED_SENSE_BUFFER(v14, v13);
    LOBYTE(v15) = 1;
    RetryRequest((_DWORD)DeviceObject, (_DWORD)Irp, (_DWORD)Context, v15, Tag);
    return -1073741802;
  }
LABEL_28:
  if ( PORT_ALLOCATED_SENSE(DeviceExtension, (PSCSI_REQUEST_BLOCK)Context) )
    FREE_PORT_ALLOCATED_SENSE_BUFFER(v17, v16);
  ClassFreeOrReuseSrb((__int64)DeviceExtension, Context);
  v18 = v24;
  Irp->IoStatus.Status = v24;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_fdfccdbcc72438cfb0f431eafc7dd1cf_Traceguids, Irp);
    v18 = v24;
  }
  v19 = MasterIrp->Tail.Overlay.CurrentStackLocation;
  if ( v18 < 0 )
  {
    MasterIrp->IoStatus.Status = v18;
    MasterIrp->IoStatus.Information = 0;
    if ( (unsigned int)(v24 + 1073741662) <= 1
      || (unsigned int)(v24 + 1073741806) <= 2
      || v24 == -2147483626
      || v24 == -1073741643 )
    {
      if ( MasterIrp->Tail.Overlay.Thread )
        IoSetHardErrorOrVerifyDevice(MasterIrp, DeviceObject);
    }
  }
  v20 = _InterlockedDecrement((volatile signed __int32 *)&v19[-1].Parameters);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_fdfccdbcc72438cfb0f431eafc7dd1cf_Traceguids, v20);
  }
  if ( !v20 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_fdfccdbcc72438cfb0f431eafc7dd1cf_Traceguids, MasterIrp);
    }
    if ( DeviceExtension->CommonExtension.DriverExtension->InitData.ClassStartIo )
    {
      ClassAcquireRemoveLockEx(DeviceObject, &Tag, "minkernel\\storage\\classpnp\\obsolete.c", 0x127u);
      ClassReleaseRemoveLock(DeviceObject, MasterIrp);
      ClassCompleteRequest(DeviceObject, MasterIrp, 1);
      v21 = KfRaiseIrql(2u);
      IoStartNextPacket(DeviceObject, 1u);
      KeLowerIrql(v21);
      ClassReleaseRemoveLock(DeviceObject, &Tag);
    }
    else
    {
      ClassReleaseRemoveLock(DeviceObject, MasterIrp);
      ClassCompleteRequest(DeviceObject, MasterIrp, 1);
    }
  }
  IoFreeIrp(Irp);
  return -1073741802;
}

```

## disassembly

```asm
0x140037e10  mov     [rsp-28h+arg_10], rbx
0x140037e15  mov     [rsp-28h+arg_18], rsi
0x140037e1a  push    rbp
0x140037e1b  push    rdi
0x140037e1c  push    r13
0x140037e1e  push    r14
0x140037e20  push    r15
0x140037e22  mov     rbp, rsp
0x140037e25  sub     rsp, 40h
0x140037e29  mov     r13, [rcx+40h]
0x140037e2d  mov     rbx, r8
0x140037e30  mov     r15, [rdx+0B8h]
0x140037e37  mov     r14, rdx
0x140037e3a  mov     rdi, [rdx+18h]
0x140037e3e  mov     rsi, rcx
0x140037e41  mov     [rbp+arg_8], 0
0x140037e48  mov     rcx, cs:WPP_GLOBAL_Control
0x140037e4f  lea     rdx, WPP_GLOBAL_Control
0x140037e56  cmp     rcx, rdx
0x140037e59  jz      short loc_140037E84
0x140037e5b  mov     eax, [rcx+2Ch]
0x140037e5e  test    al, 1
0x140037e60  jz      short loc_140037E84
0x140037e62  cmp     byte ptr [rcx+29h], 3
0x140037e66  jb      short loc_140037E84
0x140037e68  mov     rcx, [rcx+18h]
0x140037e6c  lea     r8, WPP_fdfccdbcc72438cfb0f431eafc7dd1cf_Traceguids
0x140037e73  mov     edx, 0Ch
0x140037e78  call    WPP_SF_
0x140037e7d  lea     rdx, WPP_GLOBAL_Control
0x140037e84  mov     al, [rbx+3]
0x140037e87  and     al, 3Fh
0x140037e89  cmp     al, 1
0x140037e8b  jz      loc_140037FBC
0x140037e91  mov     [rbp+Tag], 0
0x140037e99  mov     rcx, cs:WPP_GLOBAL_Control
0x140037ea0  cmp     rcx, rdx
0x140037ea3  jz      short loc_140037ECF
0x140037ea5  mov     eax, [rcx+2Ch]
0x140037ea8  test    al, 1
0x140037eaa  jz      short loc_140037ECF
0x140037eac  cmp     byte ptr [rcx+29h], 4
0x140037eb0  jb      short loc_140037ECF
0x140037eb2  mov     rcx, [rcx+18h]
0x140037eb6  lea     r8, WPP_fdfccdbcc72438cfb0f431eafc7dd1cf_Traceguids
0x140037ebd  mov     edx, 0Dh
0x140037ec2  mov     [rsp+40h+var_20], rbx
0x140037ec7  mov     r9, r14
0x140037eca  call    WPP_SF_qq
0x140037ecf  test    byte ptr [rbx+3], 40h
0x140037ed3  jz      short loc_140037EDF
0x140037ed5  xor     edx, edx; Irp
0x140037ed7  mov     rcx, rsi; BugCheckParameter2
0x140037eda  call    ClasspReleaseQueue
0x140037edf  mov     r9b, [r15]
0x140037ee2  cmp     r9b, 0Eh
0x140037ee6  jnz     short loc_140037EEE
0x140037ee8  mov     ecx, [r15+18h]
0x140037eec  jmp     short loc_140037EF0
0x140037eee  xor     ecx, ecx
0x140037ef0  lea     rdx, [rbp+Tag]
0x140037ef4  mov     eax, 4
0x140037ef9  sub     eax, [r15+20h]
0x140037efd  mov     r8, rbx
0x140037f00  mov     [rsp+40h+var_8], rdx
0x140037f05  lea     rdx, [rbp+arg_8]
0x140037f09  mov     [rsp+40h+var_10], rdx
0x140037f0e  mov     rdx, r14
0x140037f11  mov     [rsp+40h+var_18], eax
0x140037f15  mov     dword ptr [rsp+40h+var_20], ecx
0x140037f19  mov     rcx, rsi
0x140037f1c  call    InterpretSenseInfoWithoutHistory
0x140037f21  test    byte ptr [r15+2], 2
0x140037f26  jz      short loc_140037F3A
0x140037f28  cmp     [rbp+arg_8], 80000016h
0x140037f2f  jnz     short loc_140037F3A
0x140037f31  mov     [rbp+arg_8], 0C0000185h
0x140037f38  jmp     short loc_140037F42
0x140037f3a  test    al, al
0x140037f3c  jz      loc_140037FC3
0x140037f42  mov     edx, [r15+20h]
0x140037f46  lea     ecx, [rdx-1]
0x140037f49  mov     [r15+20h], rcx
0x140037f4d  test    edx, edx
0x140037f4f  jz      short loc_140037FC3
0x140037f51  mov     rcx, cs:WPP_GLOBAL_Control
0x140037f58  lea     rax, WPP_GLOBAL_Control
0x140037f5f  cmp     rcx, rax
0x140037f62  jz      short loc_140037F89
0x140037f64  mov     eax, [rcx+2Ch]
0x140037f67  test    al, 1
0x140037f69  jz      short loc_140037F89
0x140037f6b  cmp     byte ptr [rcx+29h], 4
0x140037f6f  jb      short loc_140037F89
0x140037f71  mov     rcx, [rcx+18h]
0x140037f75  lea     r8, WPP_fdfccdbcc72438cfb0f431eafc7dd1cf_Traceguids
0x140037f7c  mov     edx, 0Eh
0x140037f81  mov     r9, r14
0x140037f84  call    WPP_SF_q
0x140037f89  mov     rdx, rbx; Srb
0x140037f8c  mov     rcx, r13; FdoExtension
0x140037f8f  call    PORT_ALLOCATED_SENSE
0x140037f94  test    al, al
0x140037f96  jz      short loc_140037F9D
0x140037f98  call    FREE_PORT_ALLOCATED_SENSE_BUFFER
0x140037f9d  mov     rax, [rbp+Tag]
0x140037fa1  mov     r9b, 1
0x140037fa4  mov     r8, rbx
0x140037fa7  mov     [rsp+40h+var_20], rax
0x140037fac  mov     rdx, r14
0x140037faf  mov     rcx, rsi
0x140037fb2  call    RetryRequest
0x140037fb7  jmp     loc_1400381A2
0x140037fbc  mov     [rbp+arg_8], 0
0x140037fc3  mov     rdx, rbx; Srb
0x140037fc6  mov     rcx, r13; FdoExtension
0x140037fc9  call    PORT_ALLOCATED_SENSE
0x140037fce  test    al, al
0x140037fd0  jz      short loc_140037FD7
0x140037fd2  call    FREE_PORT_ALLOCATED_SENSE_BUFFER
0x140037fd7  mov     rdx, rbx
0x140037fda  mov     rcx, r13
0x140037fdd  call    ClassFreeOrReuseSrb
0x140037fe2  mov     edx, [rbp+arg_8]
0x140037fe5  mov     [r14+30h], edx
0x140037fe9  mov     rcx, cs:WPP_GLOBAL_Control
0x140037ff0  lea     rax, WPP_GLOBAL_Control
0x140037ff7  cmp     rcx, rax
0x140037ffa  jz      short loc_140038024
0x140037ffc  mov     eax, [rcx+2Ch]
0x140037fff  test    al, 1
0x140038001  jz      short loc_140038024
0x140038003  cmp     byte ptr [rcx+29h], 4
0x140038007  jb      short loc_140038024
0x140038009  mov     rcx, [rcx+18h]
0x14003800d  lea     r8, WPP_fdfccdbcc72438cfb0f431eafc7dd1cf_Traceguids
0x140038014  mov     edx, 0Fh
0x140038019  mov     r9, r14
0x14003801c  call    WPP_SF_q
0x140038021  mov     edx, [rbp+arg_8]
0x140038024  mov     r15, [rdi+0B8h]
0x14003802b  test    edx, edx
0x14003802d  jns     short loc_14003807F
0x14003802f  mov     [rdi+30h], edx
0x140038032  mov     qword ptr [rdi+38h], 0
0x14003803a  mov     ecx, [rbp+arg_8]
0x14003803d  lea     eax, [rcx+3FFFFF5Eh]
0x140038043  cmp     eax, 1
0x140038046  jbe     short loc_140038063
0x140038048  lea     eax, [rcx+3FFFFFEEh]
0x14003804e  cmp     eax, 2
0x140038051  jbe     short loc_140038063
0x140038053  cmp     ecx, 80000016h
0x140038059  jz      short loc_140038063
0x14003805b  cmp     ecx, 0C00000B5h
0x140038061  jnz     short loc_14003807F
0x140038063  cmp     qword ptr [rdi+98h], 0
0x14003806b  jz      short loc_14003807F
0x14003806d  mov     rdx, rsi; DeviceObject
0x140038070  mov     rcx, rdi; Irp
0x140038073  call    cs:__imp_IoSetHardErrorOrVerifyDevice
0x14003807a  nop     dword ptr [rax+rax+00h]
0x14003807f  or      ebx, 0FFFFFFFFh
0x140038082  lock xadd [r15-40h], ebx
0x140038088  dec     ebx
0x14003808a  mov     rcx, cs:WPP_GLOBAL_Control
0x140038091  lea     rax, WPP_GLOBAL_Control
0x140038098  cmp     rcx, rax
0x14003809b  jz      short loc_1400380C9
0x14003809d  mov     eax, [rcx+2Ch]
0x1400380a0  test    al, 1
0x1400380a2  jz      short loc_1400380C2
0x1400380a4  cmp     byte ptr [rcx+29h], 4
0x1400380a8  jb      short loc_1400380C2
0x1400380aa  mov     rcx, [rcx+18h]
0x1400380ae  lea     r8, WPP_fdfccdbcc72438cfb0f431eafc7dd1cf_Traceguids
0x1400380b5  mov     edx, 10h
0x1400380ba  mov     r9d, ebx
0x1400380bd  call    WPP_SF_d
0x1400380c2  lea     rax, WPP_GLOBAL_Control
0x1400380c9  test    ebx, ebx
0x1400380cb  jnz     loc_140038193
0x1400380d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400380d8  cmp     rcx, rax
0x1400380db  jz      short loc_140038100
0x1400380dd  mov     eax, [rcx+2Ch]
0x1400380e0  test    al, 1
0x1400380e2  jz      short loc_140038100
0x1400380e4  cmp     byte ptr [rcx+29h], 4
0x1400380e8  jb      short loc_140038100
0x1400380ea  mov     rcx, [rcx+18h]
0x1400380ee  lea     edx, [rbx+11h]
0x1400380f1  mov     r9, rdi
0x1400380f4  lea     r8, WPP_fdfccdbcc72438cfb0f431eafc7dd1cf_Traceguids
0x1400380fb  call    WPP_SF_q
0x140038100  mov     rax, [r13+20h]
0x140038104  mov     rcx, rsi; DeviceObject
0x140038107  cmp     qword ptr [rax+180h], 0
0x14003810f  jz      short loc_14003817D
0x140038111  mov     r9d, 127h; Line
0x140038117  lea     r8, aMinkernelStora_3; "minkernel\\storage\\classpnp\\obsolete."...
0x14003811e  lea     rdx, [rbp+Tag]; Tag
0x140038122  call    ClassAcquireRemoveLockEx
0x140038127  mov     rdx, rdi; Tag
0x14003812a  mov     rcx, rsi; DeviceObject
0x14003812d  call    ClassReleaseRemoveLock
0x140038132  mov     r8b, 1; PriorityBoost
0x140038135  mov     rdx, rdi; Irp
0x140038138  mov     rcx, rsi; DeviceObject
0x14003813b  call    ClassCompleteRequest
0x140038140  mov     cl, 2; NewIrql
0x140038142  call    cs:__imp_KfRaiseIrql
0x140038149  nop     dword ptr [rax+rax+00h]
0x14003814e  mov     dl, 1; Cancelable
0x140038150  mov     rcx, rsi; DeviceObject
0x140038153  mov     bl, al
0x140038155  call    cs:__imp_IoStartNextPacket
0x14003815c  nop     dword ptr [rax+rax+00h]
0x140038161  mov     cl, bl; NewIrql
0x140038163  call    cs:__imp_KeLowerIrql
0x14003816a  nop     dword ptr [rax+rax+00h]
0x14003816f  lea     rdx, [rbp+Tag]; Tag
0x140038173  mov     rcx, rsi; DeviceObject
0x140038176  call    ClassReleaseRemoveLock
0x14003817b  jmp     short loc_140038193
0x14003817d  mov     rdx, rdi; Tag
0x140038180  call    ClassReleaseRemoveLock
0x140038185  mov     r8b, 1; PriorityBoost
0x140038188  mov     rdx, rdi; Irp
0x14003818b  mov     rcx, rsi; DeviceObject
0x14003818e  call    ClassCompleteRequest
0x140038193  mov     rcx, r14; Irp
0x140038196  call    cs:__imp_IoFreeIrp
0x14003819d  nop     dword ptr [rax+rax+00h]
0x1400381a2  lea     r11, [rsp+40h+var_s0]
0x1400381a7  mov     eax, 0C0000016h
0x1400381ac  mov     rbx, [r11+40h]
0x1400381b0  mov     rsi, [r11+48h]
0x1400381b4  mov     rsp, r11
0x1400381b7  pop     r15
0x1400381b9  pop     r14
0x1400381bb  pop     r13
0x1400381bd  pop     rdi
0x1400381be  pop     rbp
0x1400381bf  retn
```
