# ClasspWriteCacheProperty

- ea: `0x140036640`
- end: `0x140036b60`
- name: `ClasspWriteCacheProperty`
- size: `1312`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT DeviceObject, PIRP Irp, PSCSI_REQUEST_BLOCK Srb)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140019de0`

## callees

- `0x140005190`
- `0x14000de10`
- `0x1400134a0`
- `0x140017f20`
- `0x14001fbf4`
- `0x14001feac`
- `0x140036640`
- `0x14003e940`
- `0x1400578e0`
- `0x14005d950`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1400368e0`
- `ntoskrnl!ExAllocatePool2` at `0x1400368e0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140036b20`
- `ntoskrnl!ExFreePoolWithTag` at `0x140036b20`
- `ntoskrnl!KeGetCurrentIrql` at `0x140036669`
- `ntoskrnl!KeGetCurrentIrql` at `0x140036669`

## pseudocode

```c
__int64 __fastcall ClasspWriteCacheProperty(PDEVICE_OBJECT DeviceObject, PIRP Irp, PSCSI_REQUEST_BLOCK Srb)
{
  void *DeviceExtension; // r13
  _IRP *MasterIrp; // rbx
  _IO_STACK_LOCATION *CurrentStackLocation; // rsi
  int v9; // r12d
  int v10; // edi
  ULONG_PTR v11; // rbx
  int v12; // eax
  size_t Length; // rsi
  _IRP *v14; // r14
  unsigned int v15; // eax
  bool v16; // zf
  unsigned int v17; // eax
  char v18; // r10
  unsigned int i; // r9d
  __int64 v20; // rcx
  unsigned __int64 DataTransferLength; // r8
  __int64 v22; // rdx
  int v23; // ecx
  int v24; // ecx
  unsigned __int8 *Cdb; // r8
  unsigned int SrbExtension; // r11d
  unsigned int v27; // r10d
  char v28; // si
  __int64 v29; // rcx
  unsigned __int64 v30; // r9
  __int64 v31; // rdx
  int v32; // ecx
  int v33; // ecx
  void **p_SenseInfoBuffer; // r8
  char v35; // al
  CHAR *Pool2; // rax
  CHAR *v37; // rsi
  ULONG v38; // ecx
  ULONG v39; // edx
  _BYTE *ModePage; // rax
  int v41; // eax
  int v42; // r9d
  unsigned int v43; // ecx
  int v44; // r9d
  PDEVICE_OBJECT v45; // rcx
  __int64 v46; // rdx
  ULONG v47; // edx
  _BYTE *v48; // rax

  DeviceExtension = DeviceObject->DeviceExtension;
  MasterIrp = Irp->AssociatedIrp.MasterIrp;
  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  v9 = 2;
  if ( KeGetCurrentIrql() >= 2u )
  {
    v10 = -1073741496;
    v11 = 0;
    goto LABEL_104;
  }
  v12 = *(_DWORD *)(&MasterIrp->Size + 1);
  v11 = 0;
  if ( v12 == 1 )
  {
    v10 = 0;
    goto LABEL_104;
  }
  if ( v12 )
  {
    v10 = -1073741637;
    goto LABEL_104;
  }
  Length = CurrentStackLocation->Parameters.Read.Length;
  if ( (unsigned int)Length < 8 )
  {
    v10 = -1073741820;
    goto LABEL_104;
  }
  v14 = Irp->AssociatedIrp.MasterIrp;
  memset(v14, 0, Length);
  *(_DWORD *)&v14->Type = 28;
  *(_DWORD *)(&v14->Size + 1) = 28;
  if ( (unsigned int)Length < 0x1C )
  {
    v10 = 0;
    v11 = 8;
    goto LABEL_104;
  }
  BYTE2(v14->AssociatedIrp.IrpCount) = 0;
  BYTE1(v14->AssociatedIrp.MasterIrp) = (*((_WORD *)DeviceExtension + 320) & 0x10) != 0;
  v15 = 4 * *((_DWORD *)DeviceExtension + 146);
  v16 = Srb->Function == 40;
  if ( Srb->Function == 40 )
  {
    LODWORD(Srb->NextSrb) = v15;
    LODWORD(Srb->SenseInfoBuffer) = 255;
    HIWORD(Srb->SenseInfoBuffer) = 32;
  }
  else
  {
    Srb->TimeOutValue = v15;
    *(_WORD *)&Srb->QueueTag = 8447;
  }
  v17 = *((_DWORD *)DeviceExtension + 148);
  if ( v16 )
  {
    LODWORD(Srb->DataBuffer) = v17;
    if ( !Srb->TimeOutValue )
    {
      v18 = 0;
      for ( i = 0; i < LODWORD(Srb->SrbExtension); ++i )
      {
        v20 = *((unsigned int *)&Srb[1].SenseInfoBuffer + i);
        if ( (unsigned int)v20 >= 0x80 )
        {
          DataTransferLength = Srb->DataTransferLength;
          if ( (unsigned int)v20 < (unsigned int)DataTransferLength )
          {
            v22 = (unsigned int)v20;
            v23 = *(_DWORD *)((char *)&Srb->Length + v20) - 64;
            if ( v23 )
            {
              v24 = v23 - 1;
              if ( v24 )
              {
                if ( v24 == 1 && v22 + 40 <= DataTransferLength )
                  break;
              }
              else if ( v22 + 56 <= DataTransferLength )
              {
                v18 = 1;
                *(&Srb->CdbLength + v22) = 10;
              }
            }
            else if ( v22 + 40 <= DataTransferLength )
            {
              *(&Srb->CdbLength + v22) = 10;
              break;
            }
            if ( v18 )
              break;
          }
        }
      }
    }
  }
  else
  {
    Srb->SrbFlags = v17;
    Srb->CdbLength = 10;
  }
  if ( Srb->Function != 40 )
  {
    Cdb = Srb->Cdb;
    goto LABEL_55;
  }
  Cdb = 0;
  if ( !Srb->TimeOutValue )
  {
    SrbExtension = (unsigned int)Srb->SrbExtension;
    if ( SrbExtension )
    {
      v27 = 0;
      v28 = 0;
      do
      {
        v29 = *((unsigned int *)&Srb[1].SenseInfoBuffer + v27);
        if ( (unsigned int)v29 >= 0x80 )
        {
          v30 = Srb->DataTransferLength;
          if ( (unsigned int)v29 < (unsigned int)v30 )
          {
            v31 = (unsigned int)v29;
            v32 = *(_DWORD *)((char *)&Srb->Length + v29) - 64;
            if ( v32 )
            {
              v33 = v32 - 1;
              if ( v33 )
              {
                if ( v33 == 1 && v31 + 40 <= v30 )
                {
                  if ( !*(unsigned int *)((char *)&Srb->SrbFlags + v31) )
                    break;
                  p_SenseInfoBuffer = &Srb->SenseInfoBuffer;
                  goto LABEL_53;
                }
              }
              else if ( v31 + 56 <= v30 )
              {
                if ( !*(&Srb->CdbLength + v31) )
                  break;
                v28 = 1;
                Cdb = (unsigned __int8 *)&Srb->DataBuffer + v31;
              }
            }
            else if ( v31 + 40 <= v30 )
            {
              if ( !*(&Srb->CdbLength + v31) )
                break;
              p_SenseInfoBuffer = &Srb->DataBuffer;
LABEL_53:
              Cdb = (unsigned __int8 *)p_SenseInfoBuffer + v31;
              break;
            }
            if ( v28 )
              break;
          }
        }
        ++v27;
      }
      while ( v27 < SrbExtension );
    }
  }
LABEL_55:
  *Cdb = 53;
  v10 = ClassSendSrbSynchronous(DeviceObject, Srb, 0, 0, 1u);
  if ( v10 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        20,
        WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids,
        (unsigned int)v10);
    }
    v10 = 0;
    v35 = 0;
  }
  else
  {
    v35 = 1;
  }
  LOBYTE(v14->AssociatedIrp.MasterIrp) = v35;
  Pool2 = (CHAR *)ExAllocatePool2(72, 192, 1867277139);
  v37 = Pool2;
  if ( Pool2 )
  {
    v38 = ClassModeSense(DeviceObject, Pool2, 0xC0u, 8u);
    if ( v38 < 4 )
    {
      v38 = ClassModeSense(DeviceObject, v37, 0xC0u, 8u);
      if ( v38 < 4 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 22, WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids);
        }
        v10 = -1073741435;
        goto LABEL_103;
      }
    }
    v39 = (unsigned __int8)*v37 + 1;
    if ( v38 <= v39 )
      v39 = v38;
    ModePage = ClassFindModePage(v37, v39, 8u, 1u);
    if ( ModePage )
    {
      HIDWORD(v14->MdlAddress) = ((ModePage[2] & 4) != 0) + 1;
      v41 = ((unsigned __int8)ModePage[2] >> 1) & 2;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 23, WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids);
      }
      HIDWORD(v14->MdlAddress) = 0;
      v41 = 0;
    }
    LODWORD(v14->MdlAddress) = v41;
    if ( (v37[2] & 0x10) == 0 || (*((_DWORD *)DeviceExtension + 219) & 0x80u) != 0 )
      v9 = 1;
    *(&v14->Flags + 1) = v9;
    memset(v37, 0, 0xC0u);
    LOBYTE(v42) = 8;
    v43 = ClassModeSenseEx((_DWORD)DeviceObject, (_DWORD)v37, 192, v42, 1);
    if ( v43 >= 4 || (LOBYTE(v44) = 8, v43 = ClassModeSenseEx((_DWORD)DeviceObject, (_DWORD)v37, 192, v44, 1), v43 >= 4) )
    {
      v47 = (unsigned __int8)*v37 + 1;
      if ( v43 <= v47 )
        v47 = v43;
      v48 = ClassFindModePage(v37, v47, 8u, 1u);
      if ( v48 )
      {
        LODWORD(v11) = ((v48[2] & 4) != 0) + 1;
        goto LABEL_102;
      }
      v45 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
      {
        goto LABEL_102;
      }
      v46 = 25;
    }
    else
    {
      v45 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
      {
        goto LABEL_102;
      }
      v46 = 24;
    }
    WPP_SF_(v45->AttachedDevice, v46, WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids);
LABEL_102:
    v14->Flags = v11;
    v11 = 28;
LABEL_103:
    ExFreePoolWithTag(v37, 0);
    goto LABEL_104;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 21, WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids);
  }
  v10 = -1073741670;
LABEL_104:
  Irp->IoStatus.Information = v11;
  Irp->IoStatus.Status = v10;
  ClassReleaseRemoveLock(DeviceObject, Irp);
  ClassCompleteRequest(DeviceObject, Irp, 0);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x140036640  push    rbx
0x140036642  push    rbp
0x140036643  push    rsi
0x140036644  push    rdi
0x140036645  push    r12
0x140036647  push    r13
0x140036649  push    r14
0x14003664b  push    r15
0x14003664d  sub     rsp, 38h
0x140036651  mov     r13, [rcx+40h]
0x140036655  mov     rdi, r8
0x140036658  mov     rbx, [rdx+18h]
0x14003665c  mov     rbp, rdx
0x14003665f  mov     rsi, [rdx+0B8h]
0x140036666  mov     r15, rcx
0x140036669  call    cs:__imp_KeGetCurrentIrql
0x140036670  nop     dword ptr [rax+rax+00h]
0x140036675  mov     r12d, 2
0x14003667b  cmp     al, r12b
0x14003667e  jb      short loc_14003668C
0x140036680  mov     edi, 0C0000148h
0x140036685  xor     ebx, ebx
0x140036687  jmp     loc_140036B2C
0x14003668c  mov     eax, [rbx+4]
0x14003668f  xor     ebx, ebx
0x140036691  cmp     eax, 1
0x140036694  jnz     short loc_14003669D
0x140036696  mov     edi, ebx
0x140036698  jmp     loc_140036B2C
0x14003669d  test    eax, eax
0x14003669f  jz      short loc_1400366AB
0x1400366a1  mov     edi, 0C00000BBh
0x1400366a6  jmp     loc_140036B2C
0x1400366ab  mov     esi, [rsi+8]
0x1400366ae  cmp     esi, 8
0x1400366b1  jnb     short loc_1400366BD
0x1400366b3  mov     edi, 0C0000004h
0x1400366b8  jmp     loc_140036B2C
0x1400366bd  mov     r14, [rbp+18h]
0x1400366c1  mov     r8, rsi; Size
0x1400366c4  mov     rcx, r14; void *
0x1400366c7  xor     edx, edx; Val
0x1400366c9  call    memset
0x1400366ce  mov     dword ptr [r14], 1Ch
0x1400366d5  mov     dword ptr [r14+4], 1Ch
0x1400366dd  cmp     esi, 1Ch
0x1400366e0  jnb     short loc_1400366EE
0x1400366e2  mov     edi, ebx
0x1400366e4  mov     ebx, 8
0x1400366e9  jmp     loc_140036B2C
0x1400366ee  mov     [r14+1Ah], bl
0x1400366f2  mov     r11b, 28h ; '('
0x1400366f5  movzx   eax, word ptr [r13+280h]
0x1400366fd  shr     al, 4
0x140036700  and     al, 1
0x140036702  mov     [r14+19h], al
0x140036706  mov     eax, [r13+248h]
0x14003670d  shl     eax, 2
0x140036710  cmp     [rdi+2], r11b
0x140036714  jnz     short loc_140036728
0x140036716  mov     [rdi+28h], eax
0x140036719  mov     dword ptr [rdi+20h], 0FFh
0x140036720  mov     word ptr [rdi+26h], 20h ; ' '
0x140036726  jmp     short loc_140036731
0x140036728  mov     [rdi+14h], eax
0x14003672b  mov     word ptr [rdi+8], 20FFh
0x140036731  mov     eax, [r13+250h]
0x140036738  jnz     short loc_1400367B7
0x14003673a  mov     [rdi+18h], eax
0x14003673d  cmp     [rdi+14h], ebx
0x140036740  jnz     short loc_1400367BE
0x140036742  mov     r10b, bl
0x140036745  mov     r9d, ebx
0x140036748  cmp     [rdi+38h], ebx
0x14003674b  jbe     short loc_1400367BE
0x14003674d  mov     eax, r9d
0x140036750  mov     ecx, [rdi+rax*4+78h]
0x140036754  cmp     ecx, 80h
0x14003675a  jb      short loc_1400367A5
0x14003675c  mov     r8d, [rdi+10h]
0x140036760  cmp     ecx, r8d
0x140036763  jnb     short loc_1400367A5
0x140036765  mov     edx, ecx
0x140036767  mov     ecx, [rcx+rdi]
0x14003676a  sub     ecx, 40h ; '@'
0x14003676d  jz      short loc_140036797
0x14003676f  sub     ecx, 1
0x140036772  jz      short loc_140036784
0x140036774  cmp     ecx, 1
0x140036777  jnz     short loc_1400367A0
0x140036779  lea     rcx, [rdx+28h]
0x14003677d  cmp     rcx, r8
0x140036780  jbe     short loc_1400367BE
0x140036782  jmp     short loc_1400367A0
0x140036784  lea     rcx, [rdx+38h]
0x140036788  cmp     rcx, r8
0x14003678b  ja      short loc_1400367A0
0x14003678d  mov     r10b, 1
0x140036790  mov     byte ptr [rdx+rdi+0Ah], 0Ah
0x140036795  jmp     short loc_1400367A0
0x140036797  lea     rcx, [rdx+28h]
0x14003679b  cmp     rcx, r8
0x14003679e  jbe     short loc_1400367B0
0x1400367a0  test    r10b, r10b
0x1400367a3  jnz     short loc_1400367BE
0x1400367a5  inc     r9d
0x1400367a8  cmp     r9d, [rdi+38h]
0x1400367ac  jb      short loc_14003674D
0x1400367ae  jmp     short loc_1400367BE
0x1400367b0  mov     byte ptr [rdx+rdi+0Ah], 0Ah
0x1400367b5  jmp     short loc_1400367BE
0x1400367b7  mov     [rdi+0Ch], eax
0x1400367ba  mov     byte ptr [rdi+0Ah], 0Ah
0x1400367be  cmp     [rdi+2], r11b
0x1400367c2  jnz     loc_14003686A
0x1400367c8  mov     r8, rbx
0x1400367cb  cmp     [rdi+14h], ebx
0x1400367ce  jnz     loc_14003686E
0x1400367d4  mov     r11d, [rdi+38h]
0x1400367d8  test    r11d, r11d
0x1400367db  jz      loc_14003686E
0x1400367e1  mov     r10d, ebx
0x1400367e4  mov     sil, bl
0x1400367e7  mov     eax, r10d
0x1400367ea  mov     ecx, [rdi+rax*4+78h]
0x1400367ee  cmp     ecx, 80h
0x1400367f4  jb      short loc_140036851
0x1400367f6  mov     r9d, [rdi+10h]
0x1400367fa  cmp     ecx, r9d
0x1400367fd  jnb     short loc_140036851
0x1400367ff  mov     edx, ecx
0x140036801  mov     ecx, [rcx+rdi]
0x140036804  sub     ecx, 40h ; '@'
0x140036807  jz      short loc_140036843
0x140036809  sub     ecx, 1
0x14003680c  jz      short loc_140036828
0x14003680e  cmp     ecx, 1
0x140036811  jnz     short loc_14003684C
0x140036813  lea     rcx, [rdx+28h]
0x140036817  cmp     rcx, r9
0x14003681a  ja      short loc_14003684C
0x14003681c  cmp     [rdx+rdi+0Ch], ebx
0x140036820  jbe     short loc_14003686E
0x140036822  lea     r8, [rdi+20h]
0x140036826  jmp     short loc_140036865
0x140036828  lea     rcx, [rdx+38h]
0x14003682c  cmp     rcx, r9
0x14003682f  ja      short loc_14003684C
0x140036831  cmp     [rdx+rdi+0Ah], bl
0x140036835  jbe     short loc_14003686E
0x140036837  lea     r8, [rdi+18h]
0x14003683b  mov     sil, 1
0x14003683e  add     r8, rdx
0x140036841  jmp     short loc_14003684C
0x140036843  lea     rcx, [rdx+28h]
0x140036847  cmp     rcx, r9
0x14003684a  jbe     short loc_14003685B
0x14003684c  test    sil, sil
0x14003684f  jnz     short loc_14003686E
0x140036851  inc     r10d
0x140036854  cmp     r10d, r11d
0x140036857  jb      short loc_1400367E7
0x140036859  jmp     short loc_14003686E
0x14003685b  cmp     [rdx+rdi+0Ah], bl
0x14003685f  jbe     short loc_14003686E
0x140036861  lea     r8, [rdi+18h]
0x140036865  add     r8, rdx
0x140036868  jmp     short loc_14003686E
0x14003686a  lea     r8, [rdi+48h]
0x14003686e  mov     byte ptr [r8], 35h ; '5'
0x140036872  xor     r9d, r9d; BufferLength
0x140036875  xor     r8d, r8d; BufferAddress
0x140036878  mov     [rsp+78h+WriteToDevice], 1; WriteToDevice
0x14003687d  mov     rdx, rdi; Srb
0x140036880  mov     rcx, r15; DeviceObject
0x140036883  call    ClassSendSrbSynchronous
0x140036888  mov     edi, eax
0x14003688a  lea     rax, WPP_GLOBAL_Control
0x140036891  test    edi, edi
0x140036893  js      short loc_140036899
0x140036895  mov     al, 1
0x140036897  jmp     short loc_1400368CE
0x140036899  mov     rcx, cs:WPP_GLOBAL_Control
0x1400368a0  cmp     rcx, rax
0x1400368a3  jz      short loc_1400368CA
0x1400368a5  mov     eax, [rcx+2Ch]
0x1400368a8  test    al, 10h
0x1400368aa  jz      short loc_1400368CA
0x1400368ac  cmp     byte ptr [rcx+29h], 4
0x1400368b0  jb      short loc_1400368CA
0x1400368b2  mov     rcx, [rcx+18h]
0x1400368b6  lea     r8, WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids
0x1400368bd  mov     edx, 14h
0x1400368c2  mov     r9d, edi
0x1400368c5  call    WPP_SF_d
0x1400368ca  mov     edi, ebx
0x1400368cc  mov     al, bl
0x1400368ce  mov     edx, 0C0h
0x1400368d3  mov     [r14+18h], al
0x1400368d7  mov     r8d, 6F4C6353h
0x1400368dd  lea     ecx, [rdx-78h]
0x1400368e0  call    cs:__imp_ExAllocatePool2
0x1400368e7  nop     dword ptr [rax+rax+00h]
0x1400368ec  mov     rsi, rax
0x1400368ef  test    rax, rax
0x1400368f2  jnz     short loc_140036931
0x1400368f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400368fb  lea     rax, WPP_GLOBAL_Control
0x140036902  cmp     rcx, rax
0x140036905  jz      short loc_140036927
0x140036907  mov     eax, [rcx+2Ch]
0x14003690a  test    al, 10h
0x14003690c  jz      short loc_140036927
0x14003690e  cmp     byte ptr [rcx+29h], 3
0x140036912  jb      short loc_140036927
0x140036914  mov     rcx, [rcx+18h]
0x140036918  lea     edx, [rsi+15h]
0x14003691b  lea     r8, WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids
0x140036922  call    WPP_SF_
0x140036927  mov     edi, 0C000009Ah
0x14003692c  jmp     loc_140036B2C
0x140036931  mov     r9b, 8; PageMode
0x140036934  mov     r8d, 0C0h; Length
0x14003693a  mov     rdx, rsi; ModeSenseBuffer
0x14003693d  mov     rcx, r15; DeviceObject
0x140036940  call    ClassModeSense
0x140036945  mov     ecx, eax
0x140036947  cmp     eax, 4
0x14003694a  jnb     short loc_1400369A6
0x14003694c  mov     r9b, 8; PageMode
0x14003694f  mov     r8d, 0C0h; Length
0x140036955  mov     rdx, rsi; ModeSenseBuffer
0x140036958  mov     rcx, r15; DeviceObject
0x14003695b  call    ClassModeSense
0x140036960  mov     ecx, eax
0x140036962  cmp     eax, 4
0x140036965  jnb     short loc_1400369A6
0x140036967  mov     rcx, cs:WPP_GLOBAL_Control
0x14003696e  lea     rax, WPP_GLOBAL_Control
0x140036975  cmp     rcx, rax
0x140036978  jz      short loc_14003699C
0x14003697a  mov     eax, [rcx+2Ch]
0x14003697d  test    al, 10h
0x14003697f  jz      short loc_14003699C
0x140036981  cmp     byte ptr [rcx+29h], 3
0x140036985  jb      short loc_14003699C
0x140036987  mov     rcx, [rcx+18h]
0x14003698b  lea     r8, WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids
0x140036992  mov     edx, 16h
0x140036997  call    WPP_SF_
0x14003699c  mov     edi, 0C0000185h
0x1400369a1  jmp     loc_140036B1B
0x1400369a6  movzx   edx, byte ptr [rsi]
0x1400369a9  mov     r9b, 1; Use6Byte
0x1400369ac  inc     edx
0x1400369ae  mov     r8b, 8; PageMode
0x1400369b1  cmp     ecx, edx
0x1400369b3  cmovbe  edx, ecx; Length
0x1400369b6  mov     rcx, rsi; ModeSenseBuffer
0x1400369b9  call    ClassFindModePage
0x1400369be  mov     rdx, rax
0x1400369c1  test    rax, rax
0x1400369c4  jnz     short loc_140036A03
0x1400369c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400369cd  lea     rax, WPP_GLOBAL_Control
0x1400369d4  cmp     rcx, rax
0x1400369d7  jz      short loc_1400369FB
0x1400369d9  mov     eax, [rcx+2Ch]
0x1400369dc  test    al, 10h
0x1400369de  jz      short loc_1400369FB
0x1400369e0  cmp     byte ptr [rcx+29h], 4
0x1400369e4  jb      short loc_1400369FB
0x1400369e6  mov     rcx, [rcx+18h]
0x1400369ea  lea     r8, WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids
0x1400369f1  mov     edx, 17h
0x1400369f6  call    WPP_SF_
0x1400369fb  mov     [r14+0Ch], ebx
0x1400369ff  mov     eax, ebx
0x140036a01  jmp     short loc_140036A1D
0x140036a03  mov     al, [rax+2]
0x140036a06  and     al, 4
0x140036a08  neg     al
0x140036a0a  sbb     ecx, ecx
0x140036a0c  neg     ecx
0x140036a0e  inc     ecx
0x140036a10  mov     [r14+0Ch], ecx
0x140036a14  movzx   eax, byte ptr [rdx+2]
0x140036a18  shr     eax, 1
0x140036a1a  and     eax, r12d
0x140036a1d  mov     [r14+8], eax
0x140036a21  test    byte ptr [rsi+2], 10h
0x140036a25  jz      short loc_140036A32
0x140036a27  mov     eax, [r13+36Ch]
0x140036a2e  test    al, al
0x140036a30  jns     short loc_140036A38
0x140036a32  mov     r12d, 1
0x140036a38  mov     [r14+14h], r12d
0x140036a3c  xor     edx, edx; Val
0x140036a3e  mov     r12d, 0C0h
0x140036a44  mov     rcx, rsi; void *
  ... truncated ...
```
