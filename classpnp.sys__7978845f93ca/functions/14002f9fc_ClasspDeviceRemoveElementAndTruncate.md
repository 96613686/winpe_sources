# ClasspDeviceRemoveElementAndTruncate

- ea: `0x14002f9fc`
- end: `0x14002fd0f`
- name: `ClasspDeviceRemoveElementAndTruncate`
- size: `787`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT DeviceObject, PIRP Irp, struct _SCSI_REQUEST_BLOCK *P)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140019de0`

## callees

- `0x140005190`
- `0x140012a00`
- `0x1400134a0`
- `0x14002f9fc`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14002fcef`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002fcef`

## pseudocode

```c
__int64 __fastcall ClasspDeviceRemoveElementAndTruncate(
        PDEVICE_OBJECT DeviceObject,
        PIRP Irp,
        struct _SCSI_REQUEST_BLOCK *P)
{
  void *DeviceExtension; // r13
  struct _SCSI_REQUEST_BLOCK *v4; // rbx
  unsigned int v7; // edi
  _IRP *MasterIrp; // r11
  bool v9; // zf
  unsigned int v10; // eax
  char v11; // r10
  unsigned int v12; // r9d
  __int64 v13; // rcx
  unsigned __int64 DataTransferLength; // r8
  __int64 v15; // rdx
  int v16; // ecx
  int v17; // ecx
  unsigned __int8 Function; // r14
  unsigned __int8 *Cdb; // r8
  unsigned int SrbExtension; // ebp
  unsigned int v21; // r10d
  char v22; // di
  __int64 v23; // rcx
  unsigned __int64 v24; // r9
  __int64 v25; // rdx
  int v26; // ecx
  int v27; // ecx
  unsigned __int8 *v28; // rcx
  unsigned __int8 v29; // al
  __int64 result; // rax

  DeviceExtension = DeviceObject->DeviceExtension;
  v4 = P;
  if ( !DeviceExtension )
    goto LABEL_2;
  if ( Irp->Tail.Overlay.CurrentStackLocation->Parameters.Create.Options < 0x18
    || (MasterIrp = Irp->AssociatedIrp.MasterIrp) == 0
    || *(_DWORD *)&MasterIrp->Type != 24
    || *(_DWORD *)(&MasterIrp->Size + 1) != 24 )
  {
    v7 = -1073741811;
    goto LABEL_58;
  }
  v9 = P->Function == 40;
  if ( P->Function == 40 )
  {
    LODWORD(P->SenseInfoBuffer) = 255;
    HIWORD(P->SenseInfoBuffer) = 32;
  }
  else
  {
    *(_WORD *)&P->QueueTag = 8447;
  }
  v10 = *((_DWORD *)DeviceExtension + 148);
  if ( v9 )
  {
    LODWORD(P->DataBuffer) = v10;
    *(_QWORD *)&P->InternalStatus = 0;
    HIDWORD(P->SrbExtension) = 0;
    if ( !P->TimeOutValue )
    {
      v11 = 0;
      v12 = 0;
      if ( LODWORD(P->SrbExtension) )
      {
        do
        {
          v13 = *((unsigned int *)&v4[1].SenseInfoBuffer + v12);
          if ( (unsigned int)v13 >= 0x80 )
          {
            DataTransferLength = v4->DataTransferLength;
            if ( (unsigned int)v13 < (unsigned int)DataTransferLength )
            {
              v15 = (unsigned int)v13;
              v16 = *(_DWORD *)((char *)&v4->Length + v13) - 64;
              if ( v16 )
              {
                v17 = v16 - 1;
                if ( v17 )
                {
                  if ( v17 == 1 && v15 + 40 <= DataTransferLength )
                    break;
                }
                else if ( v15 + 56 <= DataTransferLength )
                {
                  v11 = 1;
                  *(&v4->CdbLength + v15) = 16;
                }
              }
              else if ( v15 + 40 <= DataTransferLength )
              {
                *(&v4->CdbLength + v15) = 16;
                break;
              }
              if ( v11 )
                break;
            }
          }
        }
        while ( ++v12 < LODWORD(v4->SrbExtension) );
      }
    }
  }
  else
  {
    P->SrbFlags = v10;
    P->DataBuffer = 0;
    P->DataTransferLength = 0;
    P->CdbLength = 16;
  }
  Function = v4->Function;
  if ( Function != 40 )
  {
    Cdb = v4->Cdb;
    goto LABEL_51;
  }
  Cdb = 0;
  if ( !v4->TimeOutValue )
  {
    SrbExtension = (unsigned int)v4->SrbExtension;
    if ( SrbExtension )
    {
      v21 = 0;
      v22 = 0;
      do
      {
        v23 = *((unsigned int *)&v4[1].SenseInfoBuffer + v21);
        if ( (unsigned int)v23 >= 0x80 )
        {
          v24 = v4->DataTransferLength;
          if ( (unsigned int)v23 < (unsigned int)v24 )
          {
            v25 = (unsigned int)v23;
            v26 = *(_DWORD *)((char *)&v4->Length + v23) - 64;
            if ( v26 )
            {
              v27 = v26 - 1;
              if ( v27 )
              {
                if ( v27 == 1 && v25 + 40 <= v24 )
                {
                  v28 = (unsigned __int8 *)&v4->SenseInfoBuffer + v25;
                  if ( !*(unsigned int *)((char *)&v4->SrbFlags + v25) )
                    v28 = Cdb;
                  Cdb = v28;
                  break;
                }
              }
              else if ( v25 + 56 <= v24 )
              {
                if ( !*(&v4->CdbLength + v25) )
                  break;
                v22 = 1;
                Cdb = (unsigned __int8 *)&v4->DataBuffer + v25;
              }
            }
            else if ( v25 + 40 <= v24 )
            {
              if ( *(&v4->CdbLength + v25) )
                Cdb = (unsigned __int8 *)&v4->DataBuffer + v25;
              break;
            }
            if ( v22 )
              break;
          }
        }
      }
      while ( ++v21 < SrbExtension );
    }
  }
LABEL_51:
  if ( !Cdb )
  {
LABEL_2:
    v7 = -1073741823;
LABEL_58:
    Irp->IoStatus.Information = 0;
    Irp->IoStatus.Status = v7;
    ClassReleaseRemoveLock(DeviceObject, Irp);
    ClassCompleteRequest(DeviceObject, Irp, 0);
    if ( v4 )
      ExFreePoolWithTag(v4, 0);
    return v7;
  }
  if ( Function == 40 )
    LODWORD(v4->NextSrb) = 720;
  else
    v4->TimeOutValue = 720;
  *(_OWORD *)Cdb = 0;
  v29 = Cdb[1];
  *Cdb = -98;
  Cdb[1] = v29 & 0xE0 | 0x18;
  Cdb[9] = (unsigned __int8)MasterIrp->MdlAddress;
  Cdb[8] = BYTE1(MasterIrp->MdlAddress);
  Cdb[7] = BYTE2(MasterIrp->MdlAddress);
  Cdb[6] = BYTE3(MasterIrp->MdlAddress);
  Cdb[5] = BYTE4(MasterIrp->MdlAddress);
  Cdb[4] = BYTE5(MasterIrp->MdlAddress);
  Cdb[3] = BYTE6(MasterIrp->MdlAddress);
  Cdb[2] = HIBYTE(MasterIrp->MdlAddress);
  Cdb[13] = MasterIrp->Flags;
  Cdb[12] = BYTE1(MasterIrp->Flags);
  Cdb[11] = BYTE2(MasterIrp->Flags);
  Cdb[10] = HIBYTE(MasterIrp->Flags);
  *(_QWORD *)(*((_QWORD *)DeviceExtension + 143) + 704LL) = MEMORY[0xFFFFF78000000008];
  v7 = ClassSendSrbAsynchronous(*((PDEVICE_OBJECT *)DeviceExtension + 1), v4, Irp, 0, 0, 0);
  result = 259;
  if ( v7 != 259 )
  {
    v4 = 0;
    goto LABEL_58;
  }
  return result;
}

```

## disassembly

```asm
0x14002f9fc  push    rbx
0x14002f9fe  push    rbp
0x14002f9ff  push    rsi
0x14002fa00  push    rdi
0x14002fa01  push    r12
0x14002fa03  push    r13
0x14002fa05  push    r14
0x14002fa07  push    r15
0x14002fa09  sub     rsp, 38h
0x14002fa0d  mov     r13, [rcx+40h]
0x14002fa11  xor     r12d, r12d
0x14002fa14  mov     rbx, r8
0x14002fa17  mov     rsi, rdx
0x14002fa1a  mov     r15, rcx
0x14002fa1d  test    r13, r13
0x14002fa20  jnz     short loc_14002FA2C
0x14002fa22  mov     edi, 0C0000001h
0x14002fa27  jmp     loc_14002FCC5
0x14002fa2c  mov     rax, [rdx+0B8h]
0x14002fa33  cmp     dword ptr [rax+10h], 18h
0x14002fa37  jb      loc_14002FCC0
0x14002fa3d  mov     r11, [rdx+18h]
0x14002fa41  test    r11, r11
0x14002fa44  jz      loc_14002FCC0
0x14002fa4a  cmp     dword ptr [r11], 18h
0x14002fa4e  jnz     loc_14002FCC0
0x14002fa54  cmp     dword ptr [r11+4], 18h
0x14002fa59  jnz     loc_14002FCC0
0x14002fa5f  cmp     byte ptr [r8+2], 28h ; '('
0x14002fa64  jnz     short loc_14002FA77
0x14002fa66  mov     dword ptr [r8+20h], 0FFh
0x14002fa6e  mov     word ptr [r8+26h], 20h ; ' '
0x14002fa75  jmp     short loc_14002FA7E
0x14002fa77  mov     word ptr [r8+8], 20FFh
0x14002fa7e  mov     eax, [r13+250h]
0x14002fa85  jnz     loc_14002FB17
0x14002fa8b  mov     [r8+18h], eax
0x14002fa8f  mov     [r8+40h], r12
0x14002fa93  mov     [r8+3Ch], r12d
0x14002fa97  cmp     [r8+14h], r12d
0x14002fa9b  jnz     loc_14002FB28
0x14002faa1  mov     r10b, r12b
0x14002faa4  mov     r9d, r12d
0x14002faa7  cmp     [r8+38h], r12d
0x14002faab  jbe     short loc_14002FB28
0x14002faad  mov     eax, r9d
0x14002fab0  mov     ecx, [rbx+rax*4+78h]
0x14002fab4  cmp     ecx, 80h
0x14002faba  jb      short loc_14002FB05
0x14002fabc  mov     r8d, [rbx+10h]
0x14002fac0  cmp     ecx, r8d
0x14002fac3  jnb     short loc_14002FB05
0x14002fac5  mov     edx, ecx
0x14002fac7  mov     ecx, [rcx+rbx]
0x14002faca  sub     ecx, 40h ; '@'
0x14002facd  jz      short loc_14002FAF7
0x14002facf  sub     ecx, 1
0x14002fad2  jz      short loc_14002FAE4
0x14002fad4  cmp     ecx, 1
0x14002fad7  jnz     short loc_14002FB00
0x14002fad9  lea     rcx, [rdx+28h]
0x14002fadd  cmp     rcx, r8
0x14002fae0  jbe     short loc_14002FB28
0x14002fae2  jmp     short loc_14002FB00
0x14002fae4  lea     rcx, [rdx+38h]
0x14002fae8  cmp     rcx, r8
0x14002faeb  ja      short loc_14002FB00
0x14002faed  mov     r10b, 1
0x14002faf0  mov     byte ptr [rdx+rbx+0Ah], 10h
0x14002faf5  jmp     short loc_14002FB00
0x14002faf7  lea     rcx, [rdx+28h]
0x14002fafb  cmp     rcx, r8
0x14002fafe  jbe     short loc_14002FB10
0x14002fb00  test    r10b, r10b
0x14002fb03  jnz     short loc_14002FB28
0x14002fb05  inc     r9d
0x14002fb08  cmp     r9d, [rbx+38h]
0x14002fb0c  jb      short loc_14002FAAD
0x14002fb0e  jmp     short loc_14002FB28
0x14002fb10  mov     byte ptr [rdx+rbx+0Ah], 10h
0x14002fb15  jmp     short loc_14002FB28
0x14002fb17  mov     [r8+0Ch], eax
0x14002fb1b  mov     [r8+18h], r12
0x14002fb1f  mov     [r8+10h], r12d
0x14002fb23  mov     byte ptr [r8+0Ah], 10h
0x14002fb28  mov     r14b, [rbx+2]
0x14002fb2c  cmp     r14b, 28h ; '('
0x14002fb30  jnz     loc_14002FBE2
0x14002fb36  mov     r8, r12
0x14002fb39  cmp     [rbx+14h], r12d
0x14002fb3d  jnz     loc_14002FBE6
0x14002fb43  mov     ebp, [rbx+38h]
0x14002fb46  test    ebp, ebp
0x14002fb48  jz      loc_14002FBE6
0x14002fb4e  mov     r10d, r12d
0x14002fb51  mov     dil, r12b
0x14002fb54  mov     eax, r10d
0x14002fb57  mov     ecx, [rbx+rax*4+78h]
0x14002fb5b  cmp     ecx, 80h
0x14002fb61  jb      short loc_14002FBC8
0x14002fb63  mov     r9d, [rbx+10h]
0x14002fb67  cmp     ecx, r9d
0x14002fb6a  jnb     short loc_14002FBC8
0x14002fb6c  mov     edx, ecx
0x14002fb6e  mov     ecx, [rcx+rbx]
0x14002fb71  sub     ecx, 40h ; '@'
0x14002fb74  jz      short loc_14002FBBA
0x14002fb76  sub     ecx, 1
0x14002fb79  jz      short loc_14002FB9E
0x14002fb7b  cmp     ecx, 1
0x14002fb7e  jnz     short loc_14002FBC3
0x14002fb80  lea     rcx, [rdx+28h]
0x14002fb84  cmp     rcx, r9
0x14002fb87  ja      short loc_14002FBC3
0x14002fb89  lea     rcx, [rbx+20h]
0x14002fb8d  add     rcx, rdx
0x14002fb90  cmp     [rdx+rbx+0Ch], r12d
0x14002fb95  cmovz   rcx, r8
0x14002fb99  mov     r8, rcx
0x14002fb9c  jmp     short loc_14002FBE6
0x14002fb9e  lea     rcx, [rdx+38h]
0x14002fba2  cmp     rcx, r9
0x14002fba5  ja      short loc_14002FBC3
0x14002fba7  cmp     [rdx+rbx+0Ah], r12b
0x14002fbac  jbe     short loc_14002FBE6
0x14002fbae  lea     r8, [rbx+18h]
0x14002fbb2  mov     dil, 1
0x14002fbb5  add     r8, rdx
0x14002fbb8  jmp     short loc_14002FBC3
0x14002fbba  lea     rcx, [rdx+28h]
0x14002fbbe  cmp     rcx, r9
0x14002fbc1  jbe     short loc_14002FBD2
0x14002fbc3  test    dil, dil
0x14002fbc6  jnz     short loc_14002FBE6
0x14002fbc8  inc     r10d
0x14002fbcb  cmp     r10d, ebp
0x14002fbce  jb      short loc_14002FB54
0x14002fbd0  jmp     short loc_14002FBE6
0x14002fbd2  cmp     [rdx+rbx+0Ah], r12b
0x14002fbd7  jbe     short loc_14002FBE6
0x14002fbd9  lea     r8, [rbx+18h]
0x14002fbdd  add     r8, rdx
0x14002fbe0  jmp     short loc_14002FBE6
0x14002fbe2  lea     r8, [rbx+48h]
0x14002fbe6  test    r8, r8
0x14002fbe9  jz      loc_14002FA22
0x14002fbef  cmp     r14b, 28h ; '('
0x14002fbf3  jnz     short loc_14002FBFE
0x14002fbf5  mov     dword ptr [rbx+28h], 2D0h
0x14002fbfc  jmp     short loc_14002FC05
0x14002fbfe  mov     dword ptr [rbx+14h], 2D0h
0x14002fc05  xorps   xmm0, xmm0
0x14002fc08  mov     [rsp+78h+WriteToDevice], r12b; WriteToDevice
0x14002fc0d  movups  xmmword ptr [r8], xmm0
0x14002fc11  mov     al, [r8+1]
0x14002fc15  xor     r9d, r9d; BufferAddress
0x14002fc18  mov     byte ptr [r8], 9Eh
0x14002fc1c  and     al, 0F8h
0x14002fc1e  or      al, 18h
0x14002fc20  mov     [rsp+78h+BufferLength], r12d; BufferLength
0x14002fc25  mov     [r8+1], al
0x14002fc29  mov     al, [r11+8]
0x14002fc2d  mov     [r8+9], al
0x14002fc31  mov     al, [r11+9]
0x14002fc35  mov     [r8+8], al
0x14002fc39  mov     al, [r11+0Ah]
0x14002fc3d  mov     [r8+7], al
0x14002fc41  mov     al, [r11+0Bh]
0x14002fc45  mov     [r8+6], al
0x14002fc49  mov     al, [r11+0Ch]
0x14002fc4d  mov     [r8+5], al
0x14002fc51  mov     al, [r11+0Dh]
0x14002fc55  mov     [r8+4], al
0x14002fc59  mov     al, [r11+0Eh]
0x14002fc5d  mov     [r8+3], al
0x14002fc61  mov     al, [r11+0Fh]
0x14002fc65  mov     [r8+2], al
0x14002fc69  mov     al, [r11+10h]
0x14002fc6d  mov     [r8+0Dh], al
0x14002fc71  mov     al, [r11+11h]
0x14002fc75  mov     [r8+0Ch], al
0x14002fc79  mov     al, [r11+12h]
0x14002fc7d  mov     [r8+0Bh], al
0x14002fc81  mov     al, [r11+13h]
0x14002fc85  mov     [r8+0Ah], al
0x14002fc89  mov     r8, rsi; Irp
0x14002fc8c  mov     rdx, [r13+478h]
0x14002fc93  mov     rax, ds:0FFFFF78000000008h
0x14002fc9d  mov     [rdx+2C0h], rax
0x14002fca4  mov     rdx, rbx; Srb
0x14002fca7  mov     rcx, [r13+8]; DeviceObject
0x14002fcab  call    ClassSendSrbAsynchronous
0x14002fcb0  mov     edi, eax
0x14002fcb2  mov     eax, 103h
0x14002fcb7  cmp     edi, eax
0x14002fcb9  jz      short loc_14002FCFD
0x14002fcbb  mov     rbx, r12
0x14002fcbe  jmp     short loc_14002FCC5
0x14002fcc0  mov     edi, 0C000000Dh
0x14002fcc5  mov     rdx, rsi; Tag
0x14002fcc8  mov     [rsi+38h], r12
0x14002fccc  mov     rcx, r15; DeviceObject
0x14002fccf  mov     [rsi+30h], edi
0x14002fcd2  call    ClassReleaseRemoveLock
0x14002fcd7  xor     r8d, r8d; PriorityBoost
0x14002fcda  mov     rdx, rsi; Irp
0x14002fcdd  mov     rcx, r15; DeviceObject
0x14002fce0  call    ClassCompleteRequest
0x14002fce5  test    rbx, rbx
0x14002fce8  jz      short loc_14002FCFB
0x14002fcea  xor     edx, edx; Tag
0x14002fcec  mov     rcx, rbx; P
0x14002fcef  call    cs:__imp_ExFreePoolWithTag
0x14002fcf6  nop     dword ptr [rax+rax+00h]
0x14002fcfb  mov     eax, edi
0x14002fcfd  add     rsp, 38h
0x14002fd01  pop     r15
0x14002fd03  pop     r14
0x14002fd05  pop     r13
0x14002fd07  pop     r12
0x14002fd09  pop     rdi
0x14002fd0a  pop     rsi
0x14002fd0b  pop     rbp
0x14002fd0c  pop     rbx
0x14002fd0d  retn
```
