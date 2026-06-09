# ClassSendSrbAsynchronous

- ea: `0x140012a00`
- end: `0x140012e11`
- name: `ClassSendSrbAsynchronous`
- size: `1041`
- prototype: `NTSTATUS __stdcall(PDEVICE_OBJECT DeviceObject, PSCSI_REQUEST_BLOCK Srb, PIRP Irp, PVOID BufferAddress, ULONG BufferLength, BOOLEAN WriteToDevice)`
- caller_count: `5`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140019de0`
- `0x14002a47c`
- `0x14002a8d0`
- `0x14002f9fc`
- `0x1400319bc`

## callees

- `0x140005190`
- `0x140012a00`
- `0x140012e18`
- `0x1400134a0`
- `0x140015120`
- `0x140017fa0`
- `0x14001f450`

## import_xrefs

- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140012e03`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140012e03`
- `ntoskrnl!IoAllocateMdl` at `0x140012ddd`
- `ntoskrnl!IoAllocateMdl` at `0x140012ddd`
- `ntoskrnl!IofCallDriver` at `0x140012bd7`
- `ntoskrnl!IofCallDriver` at `0x140012bd7`

## pseudocode

```c
NTSTATUS __stdcall ClassSendSrbAsynchronous(
        PDEVICE_OBJECT DeviceObject,
        PSCSI_REQUEST_BLOCK Srb,
        PIRP Irp,
        PVOID BufferAddress,
        ULONG BufferLength,
        BOOLEAN WriteToDevice)
{
  struct _FUNCTIONAL_DEVICE_EXTENSION *DeviceExtension; // rsi
  UCHAR v10; // al
  void *v11; // r10
  unsigned int v12; // r11d
  __int64 v13; // r8
  __int64 v14; // rcx
  unsigned __int64 v15; // r9
  __int64 v16; // r14
  int v17; // ecx
  unsigned __int8 Function; // cl
  __int64 v19; // rax
  int v20; // edx
  unsigned int v21; // ebp
  unsigned int v22; // r8d
  __int64 v23; // rdx
  __int64 v24; // rcx
  unsigned __int64 v25; // r9
  __int64 v26; // r10
  int v27; // ecx
  bool v28; // zf
  _IO_STACK_LOCATION *CurrentStackLocation; // rax
  _IO_STACK_LOCATION *v30; // rax
  int v32; // eax
  int v33; // ecx
  int v34; // ecx
  unsigned int SrbExtension; // r11d
  __int64 v36; // rdx
  _SENSE_DATA *i; // rbp
  __int64 v38; // rcx
  unsigned __int64 DataTransferLength; // r8
  __int64 v40; // r9
  int v41; // ecx
  int v42; // ecx
  int QueueAction; // eax
  int SenseInfoBuffer_high; // eax
  unsigned int v45; // eax
  __int64 v46; // r8
  struct _MDL *MdlAddress; // rcx

  DeviceExtension = (struct _FUNCTIONAL_DEVICE_EXTENSION *)DeviceObject->DeviceExtension;
  if ( Srb->Function != 40 )
  {
    Srb->Length = 88;
    Srb->Function = 0;
    Srb->SenseInfoBuffer = DeviceExtension->SenseData;
    goto LABEL_3;
  }
  if ( !Srb->TimeOutValue )
  {
    SrbExtension = (unsigned int)Srb->SrbExtension;
    v36 = 0;
    for ( i = DeviceExtension->SenseData; (unsigned int)v36 < SrbExtension; v36 = (unsigned int)(v36 + 1) )
    {
      v38 = *((unsigned int *)&Srb[1].SenseInfoBuffer + v36);
      if ( (unsigned int)v38 >= 0x80 )
      {
        DataTransferLength = Srb->DataTransferLength;
        if ( (unsigned int)v38 < (unsigned int)DataTransferLength )
        {
          v40 = (unsigned int)v38;
          v41 = *(_DWORD *)((char *)&Srb->Length + v38);
          if ( v41 == 64 )
          {
            if ( v40 + 40 <= DataTransferLength )
              goto LABEL_64;
          }
          else
          {
            v42 = v41 - 65;
            if ( v42 )
            {
              if ( v42 == 1 && v40 + 40 <= DataTransferLength )
              {
                *(void **)((char *)&Srb->DataBuffer + v40) = i;
                break;
              }
            }
            else if ( v40 + 56 <= DataTransferLength )
            {
LABEL_64:
              *(_QWORD *)((char *)&Srb->DataTransferLength + v40) = i;
              break;
            }
          }
        }
      }
    }
  }
LABEL_3:
  v10 = GET_FDO_EXTENSON_SENSE_DATA_LENGTH(DeviceExtension);
  if ( Srb->Function == 40 )
  {
    if ( Srb->TimeOutValue )
      goto LABEL_12;
    v12 = (unsigned int)Srb->SrbExtension;
    v13 = 0;
    if ( !v12 )
      goto LABEL_12;
    while ( 1 )
    {
      v14 = *((unsigned int *)&Srb[1].SenseInfoBuffer + v13);
      if ( (unsigned int)v14 >= 0x80 )
      {
        v15 = Srb->DataTransferLength;
        if ( (unsigned int)v14 < (unsigned int)v15 )
        {
          v16 = (unsigned int)v14;
          v17 = *(_DWORD *)((char *)&Srb->Length + v14);
          if ( v17 == 64 )
          {
            if ( v16 + 40 <= v15 )
              goto LABEL_10;
          }
          else
          {
            v33 = v17 - 65;
            if ( v33 )
            {
              if ( v33 == 1 && v16 + 40 <= v15 )
              {
LABEL_10:
                *(&Srb->QueueAction + v16) = v10;
                goto LABEL_12;
              }
            }
            else if ( v16 + 56 <= v15 )
            {
              goto LABEL_10;
            }
          }
        }
      }
      v13 = (unsigned int)(v13 + 1);
      if ( (unsigned int)v13 >= v12 )
        goto LABEL_12;
    }
  }
  Srb->SenseInfoBufferLength = v10;
LABEL_12:
  Function = Srb->Function;
  if ( Function == 40 )
  {
    *(_QWORD *)&Srb->InternalStatus = v11;
    HIDWORD(Srb->SrbExtension) = BufferLength;
  }
  else
  {
    Srb->DataBuffer = v11;
    Srb->DataTransferLength = BufferLength;
  }
  v19 = 24;
  if ( Function != 40 )
    v19 = 12;
  v20 = *(_DWORD *)((char *)&Srb->Length + v19);
  v21 = v20 & 0xF0800000;
  if ( (v20 & 2) != 0 )
  {
    v32 = Function == 40 ? HIWORD(Srb->SenseInfoBuffer) : Srb->QueueAction;
    if ( v32 == 32
      || (Function != 40 ? (QueueAction = Srb->QueueAction) : (QueueAction = HIWORD(Srb->SenseInfoBuffer)),
          QueueAction == 33
       || (Function != 40
         ? (SenseInfoBuffer_high = Srb->QueueAction)
         : (SenseInfoBuffer_high = HIWORD(Srb->SenseInfoBuffer)),
           SenseInfoBuffer_high == 34)) )
    {
      v21 |= 2u;
      if ( (v20 & 0x100) != 0 )
        v21 |= 0x100u;
    }
  }
  if ( v11 )
  {
    if ( !Irp->MdlAddress )
    {
      if ( !IoAllocateMdl(v11, BufferLength, 0, 0, Irp) || (MdlAddress = Irp->MdlAddress) == 0 )
      {
        Irp->IoStatus.Status = -1073741670;
        if ( (unsigned __int8)PORT_ALLOCATED_SENSE_EX(DeviceExtension, Srb, v46) )
          FREE_PORT_ALLOCATED_SENSE_BUFFER_EX(DeviceExtension);
        ClassFreeOrReuseSrb((__int64)DeviceExtension, Srb);
        ClassReleaseRemoveLock(DeviceObject, Irp);
        ClassCompleteRequest(DeviceObject, Irp, 0);
        return -1073741670;
      }
      v21 |= 0x80000000;
      MmBuildMdlForNonPagedPool(MdlAddress);
    }
    v45 = 128;
    if ( !WriteToDevice )
      v45 = 64;
    if ( Srb->Function == 40 )
      LODWORD(Srb->DataBuffer) = v45;
    else
      Srb->SrbFlags = v45;
  }
  else if ( Function == 40 )
  {
    LODWORD(Srb->DataBuffer) = 0;
  }
  else
  {
    Srb->SrbFlags = 0;
  }
  if ( Srb->Function == 40 )
  {
    LODWORD(Srb->DataBuffer) |= v21;
    LODWORD(Srb->DataBuffer) |= 8u;
    if ( Srb->TimeOutValue )
      goto LABEL_29;
    v22 = (unsigned int)Srb->SrbExtension;
    v23 = 0;
    if ( !v22 )
      goto LABEL_29;
    while ( 1 )
    {
      v24 = *((unsigned int *)&Srb[1].SenseInfoBuffer + v23);
      if ( (unsigned int)v24 >= 0x80 )
      {
        v25 = Srb->DataTransferLength;
        if ( (unsigned int)v24 < (unsigned int)v25 )
        {
          v26 = (unsigned int)v24;
          v27 = *(_DWORD *)((char *)&Srb->Length + v24);
          if ( v27 == 64 )
          {
            if ( v26 + 40 <= v25 )
              goto LABEL_27;
          }
          else
          {
            v34 = v27 - 65;
            if ( v34 )
            {
              if ( v34 == 1 && v26 + 40 <= v25 )
              {
LABEL_27:
                *(&Srb->QueueTag + v26) = 0;
                goto LABEL_29;
              }
            }
            else if ( v26 + 56 <= v25 )
            {
              goto LABEL_27;
            }
          }
        }
      }
      v23 = (unsigned int)(v23 + 1);
      if ( (unsigned int)v23 >= v22 )
        goto LABEL_29;
    }
  }
  Srb->SrbFlags |= v21;
  Srb->SrbFlags |= 8u;
  Srb->ScsiStatus = 0;
LABEL_29:
  v28 = Srb->Function == 40;
  Srb->SrbStatus = 0;
  if ( v28 )
    Srb[1].DataBuffer = 0;
  else
    Srb->NextSrb = 0;
  Irp->Tail.Overlay.CurrentStackLocation->Parameters.CreatePipe.Parameters = (_NAMED_PIPE_CREATE_PARAMETERS *)4;
  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  CurrentStackLocation[-1].CompletionRoutine = (int (__fastcall *)(_DEVICE_OBJECT *, _IRP *, void *))ClassIoComplete;
  CurrentStackLocation[-1].Context = Srb;
  CurrentStackLocation[-1].Control = -32;
  v30 = Irp->Tail.Overlay.CurrentStackLocation;
  v30[-1].MajorFunction = 15;
  v30[-1].Parameters.WMI.ProviderId = (unsigned __int64)Srb;
  if ( Srb->Function == 40 )
    *(_QWORD *)&Srb->Cdb[8] = Irp;
  else
    Srb->OriginalRequest = Irp;
  Irp->Tail.Overlay.CurrentStackLocation->Control |= 1u;
  IofCallDriver(DeviceExtension->CommonExtension.LowerDeviceObject, Irp);
  return 259;
}

```

## disassembly

```asm
0x140012a00  mov     [rsp+arg_8], rbx
0x140012a05  mov     [rsp+arg_10], rbp
0x140012a0a  push    rsi
0x140012a0b  push    rdi
0x140012a0c  push    r15
0x140012a0e  sub     rsp, 30h
0x140012a12  cmp     byte ptr [rdx+2], 28h ; '('
0x140012a16  mov     r10, r9
0x140012a19  mov     rsi, [rcx+40h]
0x140012a1d  mov     rdi, r8
0x140012a20  mov     rbx, rdx
0x140012a23  mov     r15, rcx
0x140012a26  jz      loc_140012CD9
0x140012a2c  mov     word ptr [rdx], 58h ; 'X'
0x140012a31  mov     byte ptr [rdx+2], 0
0x140012a35  mov     rax, [rsi+240h]
0x140012a3c  mov     [rdx+20h], rax
0x140012a40  mov     rcx, rsi; FdoExtension
0x140012a43  mov     [rsp+48h+arg_0], r14
0x140012a48  call    GET_FDO_EXTENSON_SENSE_DATA_LENGTH
0x140012a4d  cmp     byte ptr [rbx+2], 28h ; '('
0x140012a51  jnz     short loc_140012AA6
0x140012a53  cmp     dword ptr [rbx+14h], 0
0x140012a57  jnz     short loc_140012AA9
0x140012a59  mov     r11d, [rbx+38h]
0x140012a5d  xor     r8d, r8d
0x140012a60  test    r11d, r11d
0x140012a63  jz      short loc_140012AA9
0x140012a65  mov     ecx, [rbx+r8*4+78h]
0x140012a6a  cmp     ecx, 80h
0x140012a70  jb      loc_140012C16
0x140012a76  mov     r9d, [rbx+10h]
0x140012a7a  cmp     ecx, r9d
0x140012a7d  jnb     loc_140012C16
0x140012a83  mov     r14d, ecx
0x140012a86  mov     ecx, [rcx+rbx]
0x140012a89  cmp     ecx, 40h ; '@'
0x140012a8c  jnz     loc_140012C91
0x140012a92  lea     rcx, [r14+28h]
0x140012a96  cmp     rcx, r9
0x140012a99  ja      loc_140012C16
0x140012a9f  mov     [r14+rbx+9], al
0x140012aa4  jmp     short loc_140012AA9
0x140012aa6  mov     [rbx+0Bh], al
0x140012aa9  movzx   ecx, byte ptr [rbx+2]
0x140012aad  mov     r14, [rsp+48h+arg_0]
0x140012ab2  mov     r11d, [rsp+48h+BufferLength]
0x140012ab7  cmp     cl, 28h ; '('
0x140012aba  jnz     loc_140012C44
0x140012ac0  mov     [rbx+40h], r10
0x140012ac4  mov     [rbx+3Ch], r11d
0x140012ac8  mov     edx, 0Ch
0x140012acd  mov     eax, 18h
0x140012ad2  cmovnz  eax, edx
0x140012ad5  mov     edx, [rax+rbx]
0x140012ad8  mov     ebp, edx
0x140012ada  and     ebp, 0F0800000h
0x140012ae0  test    dl, 2
0x140012ae3  jnz     loc_140012C66
0x140012ae9  test    r10, r10
0x140012aec  jnz     loc_140012DC5
0x140012af2  cmp     cl, 28h ; '('
0x140012af5  jnz     loc_140012C5A
0x140012afb  mov     [rbx+18h], r10d
0x140012aff  cmp     byte ptr [rbx+2], 28h ; '('
0x140012b03  jnz     short loc_140012B5E
0x140012b05  or      [rbx+18h], ebp
0x140012b08  or      dword ptr [rbx+18h], 8
0x140012b0c  cmp     dword ptr [rbx+14h], 0
0x140012b10  jnz     short loc_140012B69
0x140012b12  mov     r8d, [rbx+38h]
0x140012b16  xor     edx, edx
0x140012b18  test    r8d, r8d
0x140012b1b  jz      short loc_140012B69
0x140012b1d  mov     ecx, [rbx+rdx*4+78h]
0x140012b21  cmp     ecx, 80h
0x140012b27  jb      loc_140012C34
0x140012b2d  mov     r9d, [rbx+10h]
0x140012b31  cmp     ecx, r9d
0x140012b34  jnb     loc_140012C34
0x140012b3a  mov     r10d, ecx
0x140012b3d  mov     ecx, [rcx+rbx]
0x140012b40  cmp     ecx, 40h ; '@'
0x140012b43  jnz     loc_140012CB5
0x140012b49  lea     rcx, [r10+28h]
0x140012b4d  cmp     rcx, r9
0x140012b50  ja      loc_140012C34
0x140012b56  mov     byte ptr [r10+rbx+8], 0
0x140012b5c  jmp     short loc_140012B69
0x140012b5e  or      [rbx+0Ch], ebp
0x140012b61  or      dword ptr [rbx+0Ch], 8
0x140012b65  mov     byte ptr [rbx+4], 0
0x140012b69  cmp     byte ptr [rbx+2], 28h ; '('
0x140012b6d  mov     byte ptr [rbx+3], 0
0x140012b71  jnz     loc_140012BFC
0x140012b77  mov     qword ptr [rbx+70h], 0
0x140012b7f  mov     rax, [rdi+0B8h]
0x140012b86  lea     rcx, ClassIoComplete
0x140012b8d  mov     qword ptr [rax+20h], 4
0x140012b95  mov     rax, [rdi+0B8h]
0x140012b9c  mov     [rax-10h], rcx
0x140012ba0  mov     [rax-8], rbx
0x140012ba4  mov     byte ptr [rax-45h], 0E0h
0x140012ba8  mov     rax, [rdi+0B8h]
0x140012baf  mov     byte ptr [rax-48h], 0Fh
0x140012bb3  mov     [rax-40h], rbx
0x140012bb7  cmp     byte ptr [rbx+2], 28h ; '('
0x140012bbb  jnz     loc_140012C51
0x140012bc1  mov     [rbx+50h], rdi
0x140012bc5  mov     rax, [rdi+0B8h]
0x140012bcc  mov     rdx, rdi; Irp
0x140012bcf  or      byte ptr [rax+3], 1
0x140012bd3  mov     rcx, [rsi+10h]; DeviceObject
0x140012bd7  call    cs:__imp_IofCallDriver
0x140012bde  nop     dword ptr [rax+rax+00h]
0x140012be3  mov     eax, 103h
0x140012be8  mov     rbx, [rsp+48h+arg_8]
0x140012bed  mov     rbp, [rsp+48h+arg_10]
0x140012bf2  add     rsp, 30h
0x140012bf6  pop     r15
0x140012bf8  pop     rdi
0x140012bf9  pop     rsi
0x140012bfa  retn
0x140012bfc  mov     qword ptr [rbx+28h], 0
0x140012c04  jmp     loc_140012B7F
0x140012c09  lea     rcx, [r14+38h]
0x140012c0d  cmp     rcx, r9
0x140012c10  jbe     loc_140012A9F
0x140012c16  inc     r8d
0x140012c19  cmp     r8d, r11d
0x140012c1c  jnb     loc_140012AA9
0x140012c22  jmp     loc_140012A65
0x140012c27  lea     rcx, [r10+38h]
0x140012c2b  cmp     rcx, r9
0x140012c2e  jbe     loc_140012B56
0x140012c34  inc     edx
0x140012c36  cmp     edx, r8d
0x140012c39  jnb     loc_140012B69
0x140012c3f  jmp     loc_140012B1D
0x140012c44  mov     [rbx+18h], r10
0x140012c48  mov     [rbx+10h], r11d
0x140012c4c  jmp     loc_140012AC8
0x140012c51  mov     [rbx+30h], rdi
0x140012c55  jmp     loc_140012BC5
0x140012c5a  mov     dword ptr [rbx+0Ch], 0
0x140012c61  jmp     loc_140012AFF
0x140012c66  cmp     cl, 28h ; '('
0x140012c69  jnz     loc_140012D5F
0x140012c6f  movzx   eax, word ptr [rbx+26h]
0x140012c73  cmp     eax, 20h ; ' '
0x140012c76  jnz     loc_140012D68
0x140012c7c  or      ebp, 2
0x140012c7f  mov     eax, ebp
0x140012c81  bts     eax, 8
0x140012c85  bt      edx, 8
0x140012c89  cmovb   ebp, eax
0x140012c8c  jmp     loc_140012AE9
0x140012c91  sub     ecx, 41h ; 'A'
0x140012c94  jz      loc_140012C09
0x140012c9a  cmp     ecx, 1
0x140012c9d  jnz     loc_140012C16
0x140012ca3  lea     rcx, [r14+28h]
0x140012ca7  cmp     rcx, r9
0x140012caa  jbe     loc_140012A9F
0x140012cb0  jmp     loc_140012C16
0x140012cb5  sub     ecx, 41h ; 'A'
0x140012cb8  jz      loc_140012C27
0x140012cbe  cmp     ecx, 1
0x140012cc1  jnz     loc_140012C34
0x140012cc7  lea     rcx, [r10+28h]
0x140012ccb  cmp     rcx, r9
0x140012cce  jbe     loc_140012B56
0x140012cd4  jmp     loc_140012C34
0x140012cd9  cmp     dword ptr [rdx+14h], 0
0x140012cdd  jnz     loc_140012A40
0x140012ce3  mov     r11d, [rbx+38h]
0x140012ce7  xor     edx, edx
0x140012ce9  mov     rbp, [rsi+240h]
0x140012cf0  test    r11d, r11d
0x140012cf3  jz      loc_140012A40
0x140012cf9  mov     ecx, [rbx+rdx*4+78h]
0x140012cfd  cmp     ecx, 80h
0x140012d03  jb      short loc_140012D35
0x140012d05  mov     r8d, [rbx+10h]
0x140012d09  cmp     ecx, r8d
0x140012d0c  jnb     short loc_140012D35
0x140012d0e  mov     r9d, ecx
0x140012d11  mov     ecx, [rcx+rbx]
0x140012d14  cmp     ecx, 40h ; '@'
0x140012d17  jnz     short loc_140012D42
0x140012d19  lea     rcx, [r9+28h]
0x140012d1d  cmp     rcx, r8
0x140012d20  ja      short loc_140012D35
0x140012d22  mov     [r9+rbx+10h], rbp
0x140012d27  jmp     loc_140012A40
0x140012d2c  lea     rcx, [r9+38h]
0x140012d30  cmp     rcx, r8
0x140012d33  jbe     short loc_140012D22
0x140012d35  inc     edx
0x140012d37  cmp     edx, r11d
0x140012d3a  jnb     loc_140012A40
0x140012d40  jmp     short loc_140012CF9
0x140012d42  sub     ecx, 41h ; 'A'
0x140012d45  jz      short loc_140012D2C
0x140012d47  cmp     ecx, 1
0x140012d4a  jnz     short loc_140012D35
0x140012d4c  lea     rcx, [r9+28h]
0x140012d50  cmp     rcx, r8
0x140012d53  ja      short loc_140012D35
0x140012d55  mov     [r9+rbx+18h], rbp
0x140012d5a  jmp     loc_140012A40
0x140012d5f  movzx   eax, byte ptr [rbx+9]
0x140012d63  jmp     loc_140012C73
0x140012d68  cmp     cl, 28h ; '('
0x140012d6b  jnz     short loc_140012D91
0x140012d6d  movzx   eax, word ptr [rbx+26h]
0x140012d71  cmp     eax, 21h ; '!'
0x140012d74  jz      loc_140012C7C
0x140012d7a  cmp     cl, 28h ; '('
0x140012d7d  jnz     short loc_140012D97
0x140012d7f  movzx   eax, word ptr [rbx+26h]
0x140012d83  cmp     eax, 22h ; '"'
0x140012d86  jnz     loc_140012AE9
0x140012d8c  jmp     loc_140012C7C
0x140012d91  movzx   eax, byte ptr [rbx+9]
0x140012d95  jmp     short loc_140012D71
0x140012d97  movzx   eax, byte ptr [rbx+9]
0x140012d9b  jmp     short loc_140012D83
0x140012d9d  cmp     [rsp+48h+WriteToDevice], 0
0x140012da2  mov     eax, 80h
0x140012da7  mov     ecx, 40h ; '@'
0x140012dac  cmovz   eax, ecx
0x140012daf  cmp     byte ptr [rbx+2], 28h ; '('
0x140012db3  jnz     short loc_140012DBD
0x140012db5  mov     [rbx+18h], eax
0x140012db8  jmp     loc_140012AFF
0x140012dbd  mov     [rbx+0Ch], eax
0x140012dc0  jmp     loc_140012AFF
0x140012dc5  cmp     qword ptr [rdi+8], 0
0x140012dca  jnz     short loc_140012D9D
0x140012dcc  xor     r9d, r9d; ChargeQuota
0x140012dcf  mov     [rsp+48h+Irp], rdi; Irp
0x140012dd4  xor     r8d, r8d; SecondaryBuffer
0x140012dd7  mov     edx, r11d; Length
0x140012dda  mov     rcx, r10; VirtualAddress
0x140012ddd  call    cs:__imp_IoAllocateMdl
0x140012de4  nop     dword ptr [rax+rax+00h]
0x140012de9  test    rax, rax
0x140012dec  jz      loc_1400401E2
0x140012df2  mov     rcx, [rdi+8]; MemoryDescriptorList
0x140012df6  test    rcx, rcx
0x140012df9  jz      loc_1400401E2
0x140012dff  bts     ebp, 1Fh
0x140012e03  call    cs:__imp_MmBuildMdlForNonPagedPool
0x140012e0a  nop     dword ptr [rax+rax+00h]
0x140012e0f  jmp     short loc_140012D9D
0x1400401e2  mov     rdx, rbx
0x1400401e5  mov     dword ptr [rdi+30h], 0C000009Ah
0x1400401ec  mov     rcx, rsi
0x1400401ef  call    PORT_ALLOCATED_SENSE_EX
0x1400401f4  test    al, al
0x1400401f6  jz      short loc_140040200
0x1400401f8  mov     rcx, rsi; FdoExtension
0x1400401fb  call    FREE_PORT_ALLOCATED_SENSE_BUFFER_EX
0x140040200  mov     rdx, rbx
0x140040203  mov     rcx, rsi
0x140040206  call    ClassFreeOrReuseSrb
0x14004020b  mov     rdx, rdi; Tag
0x14004020e  mov     rcx, r15; DeviceObject
0x140040211  call    ClassReleaseRemoveLock
0x140040216  xor     r8d, r8d; PriorityBoost
0x140040219  mov     rdx, rdi; Irp
0x14004021c  mov     rcx, r15; DeviceObject
0x14004021f  call    ClassCompleteRequest
0x140040224  mov     eax, 0C000009Ah
0x140040229  jmp     loc_140012BE8
```
