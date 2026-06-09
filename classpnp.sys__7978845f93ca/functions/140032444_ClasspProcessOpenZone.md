# ClasspProcessOpenZone

- ea: `0x140032444`
- end: `0x1400327a4`
- name: `ClasspProcessOpenZone`
- size: `864`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT DeviceObject, PIRP Irp, PSCSI_REQUEST_BLOCK Srb)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140019de0`
- `0x140033050`

## callees

- `0x140001130`
- `0x1400018a0`
- `0x140005190`
- `0x14000de10`
- `0x1400134a0`
- `0x140032444`
- `0x140032f1c`

## pseudocode

```c
__int64 __fastcall ClasspProcessOpenZone(PDEVICE_OBJECT DeviceObject, PIRP Irp, PSCSI_REQUEST_BLOCK Srb)
{
  _IRP *MasterIrp; // rdi
  char v7; // r9
  unsigned int v8; // ebx
  PDEVICE_OBJECT *DeviceExtension; // r14
  __int64 v11; // rcx
  char v12; // r12
  unsigned __int64 v13; // r15
  __int64 v14; // rax
  unsigned __int64 v15; // r11
  unsigned __int64 v16; // rdi
  bool v17; // zf
  unsigned int v18; // eax
  unsigned int v19; // eax
  char v20; // r10
  __int64 i; // r9
  __int64 v22; // rcx
  unsigned __int64 DataTransferLength; // r8
  __int64 v24; // rdx
  int v25; // ecx
  int v26; // ecx
  unsigned __int8 *Cdb; // rdx
  unsigned int SrbExtension; // edi
  __int64 v29; // r10
  char v30; // r11
  __int64 v31; // rcx
  unsigned __int64 v32; // r9
  __int64 v33; // r8
  int v34; // ecx
  int v35; // ecx
  unsigned __int8 *v36; // rcx
  unsigned __int8 v37; // al
  char v38; // al

  MasterIrp = Irp->AssociatedIrp.MasterIrp;
  if ( !MasterIrp || Irp->Tail.Overlay.CurrentStackLocation->Parameters.Create.Options < 0x1C )
    goto LABEL_64;
  if ( !(unsigned __int8)ClasspIsManagedZonedDevice(DeviceObject) )
    goto LABEL_4;
  DeviceExtension = (PDEVICE_OBJECT *)DeviceObject->DeviceExtension;
  if ( ProcessZoneCommandAsynchronously && !v7 && (unsigned __int8)ClasspProcessZoneCommandAsynchronously(DeviceObject) )
    return 259;
  v11 = *((unsigned int *)DeviceExtension + 143);
  if ( !(_DWORD)v11 )
  {
    if ( ClassReadDriveCapacity(DeviceExtension[1]) < 0
      || (v11 = *((unsigned int *)DeviceExtension + 143), !(_DWORD)v11) )
    {
LABEL_4:
      v8 = -1073741808;
      goto LABEL_65;
    }
  }
  if ( ((__int64)MasterIrp->MdlAddress & 1) == 0 )
  {
    v14 = *(&MasterIrp->Flags + 1);
    if ( (_DWORD)v14 && MasterIrp->AssociatedIrp.IrpCount >= 0x10u )
    {
      v12 = 0;
      v13 = *(_QWORD *)((char *)&MasterIrp->Type + v14) / v11;
      goto LABEL_17;
    }
LABEL_64:
    v8 = -1073741811;
    goto LABEL_65;
  }
  v12 = 1;
  v13 = 0;
LABEL_17:
  v15 = v13 >> 16;
  v16 = v13 >> 24;
  v17 = Srb->Function == 40;
  v18 = *((_DWORD *)DeviceExtension + 146);
  if ( Srb->Function == 40 )
  {
    LODWORD(Srb->NextSrb) = v18;
    LODWORD(Srb->SenseInfoBuffer) = 255;
    HIWORD(Srb->SenseInfoBuffer) = 32;
  }
  else
  {
    Srb->TimeOutValue = v18;
    *(_WORD *)&Srb->QueueTag = 8447;
  }
  v19 = *((_DWORD *)DeviceExtension + 148);
  if ( v17 )
  {
    v17 = Srb->TimeOutValue == 0;
    LODWORD(Srb->DataBuffer) = v19;
    if ( v17 )
    {
      v20 = 0;
      for ( i = 0; (unsigned int)i < LODWORD(Srb->SrbExtension); i = (unsigned int)(i + 1) )
      {
        v22 = *((unsigned int *)&Srb[1].SenseInfoBuffer + i);
        if ( (unsigned int)v22 >= 0x80 )
        {
          DataTransferLength = Srb->DataTransferLength;
          if ( (unsigned int)v22 < (unsigned int)DataTransferLength )
          {
            v24 = (unsigned int)v22;
            v25 = *(_DWORD *)((char *)&Srb->Length + v22) - 64;
            if ( v25 )
            {
              v26 = v25 - 1;
              if ( v26 )
              {
                if ( v26 == 1 && v24 + 40 <= DataTransferLength )
                  break;
              }
              else if ( v24 + 56 <= DataTransferLength )
              {
                v20 = 1;
                *(&Srb->CdbLength + v24) = 16;
              }
            }
            else if ( v24 + 40 <= DataTransferLength )
            {
              *(&Srb->CdbLength + v24) = 16;
              break;
            }
            if ( v20 )
              break;
          }
        }
      }
    }
  }
  else
  {
    Srb->SrbFlags = v19;
    Srb->CdbLength = 16;
  }
  if ( Srb->Function != 40 )
  {
    Cdb = Srb->Cdb;
    goto LABEL_63;
  }
  Cdb = 0;
  if ( Srb->TimeOutValue )
    goto LABEL_63;
  SrbExtension = (unsigned int)Srb->SrbExtension;
  if ( !SrbExtension )
  {
LABEL_52:
    v16 = v13 >> 24;
    goto LABEL_63;
  }
  v29 = 0;
  v30 = 0;
  while ( 1 )
  {
    v31 = *((unsigned int *)&Srb[1].SenseInfoBuffer + v29);
    if ( (unsigned int)v31 >= 0x80 )
    {
      v32 = Srb->DataTransferLength;
      if ( (unsigned int)v31 < (unsigned int)v32 )
        break;
    }
LABEL_58:
    v29 = (unsigned int)(v29 + 1);
    if ( (unsigned int)v29 >= SrbExtension )
      goto LABEL_51;
  }
  v33 = (unsigned int)v31;
  v34 = *(_DWORD *)((char *)&Srb->Length + v31) - 64;
  if ( v34 )
  {
    v35 = v34 - 1;
    if ( v35 )
    {
      if ( v35 == 1 && v33 + 40 <= v32 )
      {
        v36 = (unsigned __int8 *)&Srb->SenseInfoBuffer + v33;
        if ( !*(unsigned int *)((char *)&Srb->SrbFlags + v33) )
          v36 = Cdb;
        Cdb = v36;
LABEL_51:
        v15 = v13 >> 16;
        goto LABEL_52;
      }
    }
    else if ( v33 + 56 <= v32 )
    {
      if ( !*(&Srb->CdbLength + v33) )
        goto LABEL_51;
      v30 = 1;
      Cdb = (unsigned __int8 *)&Srb->DataBuffer + v33;
    }
    goto LABEL_57;
  }
  if ( v33 + 40 > v32 )
  {
LABEL_57:
    if ( v30 )
      goto LABEL_51;
    goto LABEL_58;
  }
  v15 = v13 >> 16;
  v16 = v13 >> 24;
  if ( *(&Srb->CdbLength + v33) )
    Cdb = (unsigned __int8 *)&Srb->DataBuffer + v33;
LABEL_63:
  v37 = Cdb[1];
  *Cdb = -108;
  Cdb[1] = v37 & 0xE0 | 3;
  v38 = Cdb[14] & 0xFE;
  Cdb[9] = v13;
  Cdb[8] = BYTE1(v13);
  Cdb[14] = v12 | v38;
  Cdb[5] = BYTE4(v13);
  Cdb[4] = BYTE5(v13);
  Cdb[3] = BYTE6(v13);
  Cdb[2] = HIBYTE(v13);
  Cdb[7] = v15;
  Cdb[6] = v16;
  v8 = ClassSendSrbSynchronous(DeviceExtension[1], Srb, 0, 0, 0);
LABEL_65:
  Irp->IoStatus.Information = 0;
  Irp->IoStatus.Status = v8;
  ClassReleaseRemoveLock(DeviceObject, Irp);
  ClassCompleteRequest(DeviceObject, Irp, 0);
  return v8;
}

```

## disassembly

```asm
0x140032444  mov     [rsp+arg_10], rbx
0x140032449  push    rbp
0x14003244a  push    rsi
0x14003244b  push    rdi
0x14003244c  push    r12
0x14003244e  push    r13
0x140032450  push    r14
0x140032452  push    r15
0x140032454  sub     rsp, 50h
0x140032458  mov     rdi, [rdx+18h]
0x14003245c  mov     rbx, r8
0x14003245f  mov     rsi, rdx
0x140032462  mov     rbp, rcx
0x140032465  test    rdi, rdi
0x140032468  jz      loc_140032760
0x14003246e  mov     rax, [rdx+0B8h]
0x140032475  cmp     dword ptr [rax+10h], 1Ch
0x140032479  jb      loc_140032760
0x14003247f  call    ClasspIsManagedZonedDevice
0x140032484  test    al, al
0x140032486  jnz     short loc_140032492
0x140032488  mov     ebx, 0C0000010h
0x14003248d  jmp     loc_140032765
0x140032492  cmp     cs:ProcessZoneCommandAsynchronously, 0
0x140032499  mov     r14, [rbp+40h]
0x14003249d  jz      short loc_1400324C3
0x14003249f  test    r9b, r9b
0x1400324a2  jnz     short loc_1400324C3
0x1400324a4  mov     r9d, 80000014h
0x1400324aa  mov     rdx, rsi
0x1400324ad  mov     rcx, rbp; DeviceObject
0x1400324b0  call    ClasspProcessZoneCommandAsynchronously
0x1400324b5  test    al, al
0x1400324b7  jz      short loc_1400324C3
0x1400324b9  mov     eax, 103h
0x1400324be  jmp     loc_14003278B
0x1400324c3  mov     ecx, [r14+23Ch]
0x1400324ca  test    ecx, ecx
0x1400324cc  jnz     short loc_1400324E6
0x1400324ce  mov     rcx, [r14+8]; DeviceObject
0x1400324d2  call    ClassReadDriveCapacity
0x1400324d7  test    eax, eax
0x1400324d9  js      short loc_140032488
0x1400324db  mov     ecx, [r14+23Ch]
0x1400324e2  test    ecx, ecx
0x1400324e4  jz      short loc_140032488
0x1400324e6  mov     eax, [rdi+8]
0x1400324e9  test    al, 1
0x1400324eb  jz      short loc_1400324F5
0x1400324ed  mov     r12b, 1
0x1400324f0  xor     r15d, r15d
0x1400324f3  jmp     short loc_140032519
0x1400324f5  mov     eax, [rdi+14h]
0x1400324f8  test    eax, eax
0x1400324fa  jz      loc_140032760
0x140032500  cmp     dword ptr [rdi+18h], 10h
0x140032504  jb      loc_140032760
0x14003250a  mov     rax, [rax+rdi]
0x14003250e  xor     r12b, r12b
0x140032511  cqo
0x140032513  idiv    rcx
0x140032516  mov     r15, rax
0x140032519  mov     rax, r15
0x14003251c  mov     r13, r15
0x14003251f  shr     rax, 20h
0x140032523  mov     r11, r15
0x140032526  mov     [rsp+88h+var_58], rax
0x14003252b  mov     rdi, r15
0x14003252e  shr     r11, 10h
0x140032532  mov     rax, r15
0x140032535  shr     rax, 28h
0x140032539  mov     [rsp+88h+var_50], rax
0x14003253e  mov     rax, r15
0x140032541  shr     rax, 30h
0x140032545  mov     [rsp+88h+var_48], rax
0x14003254a  mov     rax, r15
0x14003254d  shr     rax, 38h
0x140032551  shr     rdi, 18h
0x140032555  shr     r13, 8
0x140032559  cmp     byte ptr [rbx+2], 28h ; '('
0x14003255d  mov     [rsp+88h+var_40], rax
0x140032562  mov     eax, [r14+248h]
0x140032569  mov     [rsp+88h+arg_8], r11
0x140032571  mov     [rsp+88h+arg_0], rdi
0x140032579  jnz     short loc_14003258D
0x14003257b  mov     [rbx+28h], eax
0x14003257e  mov     dword ptr [rbx+20h], 0FFh
0x140032585  mov     word ptr [rbx+26h], 20h ; ' '
0x14003258b  jmp     short loc_140032596
0x14003258d  mov     [rbx+14h], eax
0x140032590  mov     word ptr [rbx+8], 20FFh
0x140032596  mov     eax, [r14+250h]
0x14003259d  jnz     short loc_14003261C
0x14003259f  cmp     dword ptr [rbx+14h], 0
0x1400325a3  mov     [rbx+18h], eax
0x1400325a6  jnz     short loc_140032623
0x1400325a8  xor     r10b, r10b
0x1400325ab  xor     r9d, r9d
0x1400325ae  cmp     [rbx+38h], r9d
0x1400325b2  jbe     short loc_140032623
0x1400325b4  mov     ecx, [rbx+r9*4+78h]
0x1400325b9  cmp     ecx, 80h
0x1400325bf  jb      short loc_14003260A
0x1400325c1  mov     r8d, [rbx+10h]
0x1400325c5  cmp     ecx, r8d
0x1400325c8  jnb     short loc_14003260A
0x1400325ca  mov     edx, ecx
0x1400325cc  mov     ecx, [rcx+rbx]
0x1400325cf  sub     ecx, 40h ; '@'
0x1400325d2  jz      short loc_1400325FC
0x1400325d4  sub     ecx, 1
0x1400325d7  jz      short loc_1400325E9
0x1400325d9  cmp     ecx, 1
0x1400325dc  jnz     short loc_140032605
0x1400325de  lea     rcx, [rdx+28h]
0x1400325e2  cmp     rcx, r8
0x1400325e5  jbe     short loc_140032623
0x1400325e7  jmp     short loc_140032605
0x1400325e9  lea     rcx, [rdx+38h]
0x1400325ed  cmp     rcx, r8
0x1400325f0  ja      short loc_140032605
0x1400325f2  mov     r10b, 1
0x1400325f5  mov     byte ptr [rdx+rbx+0Ah], 10h
0x1400325fa  jmp     short loc_140032605
0x1400325fc  lea     rcx, [rdx+28h]
0x140032600  cmp     rcx, r8
0x140032603  jbe     short loc_140032615
0x140032605  test    r10b, r10b
0x140032608  jnz     short loc_140032623
0x14003260a  inc     r9d
0x14003260d  cmp     r9d, [rbx+38h]
0x140032611  jb      short loc_1400325B4
0x140032613  jmp     short loc_140032623
0x140032615  mov     byte ptr [rdx+rbx+0Ah], 10h
0x14003261a  jmp     short loc_140032623
0x14003261c  mov     [rbx+0Ch], eax
0x14003261f  mov     byte ptr [rbx+0Ah], 10h
0x140032623  cmp     byte ptr [rbx+2], 28h ; '('
0x140032627  jnz     loc_1400326F9
0x14003262d  xor     edx, edx
0x14003262f  cmp     [rbx+14h], edx
0x140032632  jnz     loc_1400326FD
0x140032638  mov     edi, [rbx+38h]
0x14003263b  test    edi, edi
0x14003263d  jz      short loc_140032695
0x14003263f  xor     r10d, r10d
0x140032642  xor     r11b, r11b
0x140032645  mov     ecx, [rbx+r10*4+78h]
0x14003264a  cmp     ecx, 80h
0x140032650  jb      short loc_1400326CA
0x140032652  mov     r9d, [rbx+10h]
0x140032656  cmp     ecx, r9d
0x140032659  jnb     short loc_1400326CA
0x14003265b  mov     r8d, ecx
0x14003265e  mov     ecx, [rcx+rbx]
0x140032661  sub     ecx, 40h ; '@'
0x140032664  jz      short loc_1400326BC
0x140032666  sub     ecx, 1
0x140032669  jz      short loc_14003269F
0x14003266b  cmp     ecx, 1
0x14003266e  jnz     short loc_1400326C5
0x140032670  lea     rcx, [r8+28h]
0x140032674  cmp     rcx, r9
0x140032677  ja      short loc_1400326C5
0x140032679  lea     rcx, [rbx+20h]
0x14003267d  add     rcx, r8
0x140032680  cmp     dword ptr [r8+rbx+0Ch], 0
0x140032686  cmovz   rcx, rdx
0x14003268a  mov     rdx, rcx
0x14003268d  mov     r11, [rsp+88h+arg_8]
0x140032695  mov     rdi, [rsp+88h+arg_0]
0x14003269d  jmp     short loc_1400326FD
0x14003269f  lea     rcx, [r8+38h]
0x1400326a3  cmp     rcx, r9
0x1400326a6  ja      short loc_1400326C5
0x1400326a8  cmp     byte ptr [r8+rbx+0Ah], 0
0x1400326ae  jbe     short loc_14003268D
0x1400326b0  lea     rdx, [rbx+18h]
0x1400326b4  mov     r11b, 1
0x1400326b7  add     rdx, r8
0x1400326ba  jmp     short loc_1400326C5
0x1400326bc  lea     rcx, [r8+28h]
0x1400326c0  cmp     rcx, r9
0x1400326c3  jbe     short loc_1400326D8
0x1400326c5  test    r11b, r11b
0x1400326c8  jnz     short loc_14003268D
0x1400326ca  inc     r10d
0x1400326cd  cmp     r10d, edi
0x1400326d0  jb      loc_140032645
0x1400326d6  jmp     short loc_14003268D
0x1400326d8  cmp     byte ptr [r8+rbx+0Ah], 0
0x1400326de  mov     r11, [rsp+88h+arg_8]
0x1400326e6  mov     rdi, [rsp+88h+arg_0]
0x1400326ee  jbe     short loc_1400326FD
0x1400326f0  lea     rdx, [rbx+18h]
0x1400326f4  add     rdx, r8
0x1400326f7  jmp     short loc_1400326FD
0x1400326f9  lea     rdx, [rbx+48h]
0x1400326fd  mov     al, [rdx+1]
0x140032700  xor     r9d, r9d; BufferLength
0x140032703  mov     byte ptr [rdx], 94h
0x140032706  and     al, 0E3h
0x140032708  or      al, 3
0x14003270a  mov     [rsp+88h+WriteToDevice], 0; WriteToDevice
0x14003270f  mov     [rdx+1], al
0x140032712  xor     r8d, r8d; BufferAddress
0x140032715  mov     al, [rdx+0Eh]
0x140032718  and     al, 0FEh
0x14003271a  mov     [rdx+9], r15b
0x14003271e  or      al, r12b
0x140032721  mov     [rdx+8], r13b
0x140032725  mov     [rdx+0Eh], al
0x140032728  mov     rax, [rsp+88h+var_58]
0x14003272d  mov     [rdx+5], al
0x140032730  mov     rax, [rsp+88h+var_50]
0x140032735  mov     [rdx+4], al
0x140032738  mov     rax, [rsp+88h+var_48]
0x14003273d  mov     [rdx+3], al
0x140032740  mov     rax, [rsp+88h+var_40]
0x140032745  mov     [rdx+2], al
0x140032748  mov     [rdx+7], r11b
0x14003274c  mov     [rdx+6], dil
0x140032750  mov     rdx, rbx; Srb
0x140032753  mov     rcx, [r14+8]; DeviceObject
0x140032757  call    ClassSendSrbSynchronous
0x14003275c  mov     ebx, eax
0x14003275e  jmp     short loc_140032765
0x140032760  mov     ebx, 0C000000Dh
0x140032765  mov     rdx, rsi; Tag
0x140032768  mov     qword ptr [rsi+38h], 0
0x140032770  mov     rcx, rbp; DeviceObject
0x140032773  mov     [rsi+30h], ebx
0x140032776  call    ClassReleaseRemoveLock
0x14003277b  xor     r8d, r8d; PriorityBoost
0x14003277e  mov     rdx, rsi; Irp
0x140032781  mov     rcx, rbp; DeviceObject
0x140032784  call    ClassCompleteRequest
0x140032789  mov     eax, ebx
0x14003278b  mov     rbx, [rsp+88h+arg_10]
0x140032793  add     rsp, 50h
0x140032797  pop     r15
0x140032799  pop     r14
0x14003279b  pop     r13
0x14003279d  pop     r12
0x14003279f  pop     rdi
0x1400327a0  pop     rsi
0x1400327a1  pop     rbp
0x1400327a2  retn
```
