# ClasspDeviceSeekPenaltyProperty

- ea: `0x14001ecc0`
- end: `0x14001f14e`
- name: `ClasspDeviceSeekPenaltyProperty`
- size: `1166`
- prototype: `NTSTATUS __fastcall(PDEVICE_OBJECT DeviceObject, PIRP Irp, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140019de0`

## callees

- `0x140005190`
- `0x1400134a0`
- `0x1400173a0`
- `0x1400175e0`
- `0x14001ecc0`
- `0x140031868`
- `0x14003e430`
- `0x14003e940`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x14001f066`
- `ntoskrnl!EtwWriteTransfer` at `0x14001f066`
- `ntoskrnl!IofCallDriver` at `0x14001f122`
- `ntoskrnl!IofCallDriver` at `0x14001f122`
- `ntoskrnl!KeGetCurrentIrql` at `0x14001ed46`
- `ntoskrnl!KeGetCurrentIrql` at `0x14001ed46`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14001f10f`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14001f10f`

## pseudocode

```c
NTSTATUS __fastcall ClasspDeviceSeekPenaltyProperty(PDEVICE_OBJECT DeviceObject, PIRP Irp, __int64 a3)
{
  struct _COMMON_DEVICE_EXTENSION *DeviceExtension; // rdi
  _IO_STACK_LOCATION *CurrentStackLocation; // rbx
  unsigned int Information; // ebp
  int v9; // ecx
  NTSTATUS BlockDeviceCharacteristicsVPDPage; // ebx
  size_t Length; // r12
  _IRP *MasterIrp; // r14
  int LowerDeviceObject_high; // ecx
  __int16 v14; // cx
  unsigned __int8 v15; // r15
  _PHYSICAL_DEVICE_EXTENSION *ChildList; // rax
  __int16 v17; // cx
  unsigned __int8 v18; // r15
  __int64 v19; // rax
  wchar_t *Buffer; // rax
  char v21; // cl
  _DWORD **v23; // r8
  signed __int32 v24; // eax
  signed __int32 v25; // ett
  char v26; // [rsp+30h] [rbp-A8h] BYREF
  unsigned int v27; // [rsp+34h] [rbp-A4h]
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+38h] [rbp-A0h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+50h] [rbp-88h] BYREF
  void *v30; // [rsp+60h] [rbp-78h]
  int v31; // [rsp+68h] [rbp-70h]
  int v32; // [rsp+6Ch] [rbp-6Ch]
  __int64 v33; // [rsp+70h] [rbp-68h]
  __int64 v34; // [rsp+78h] [rbp-60h]
  char *v35; // [rsp+80h] [rbp-58h]
  __int64 v36; // [rsp+88h] [rbp-50h]

  DeviceExtension = (struct _COMMON_DEVICE_EXTENSION *)DeviceObject->DeviceExtension;
  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  if ( DeviceObject->DeviceType == 7
    && (DeviceObject->Characteristics & 4) == 0
    && HIDWORD(DeviceExtension[2].ChildList->CommonExtension.LowerDeviceObject) != 1 )
  {
    Information = 0;
    v9 = *(_DWORD *)(&Irp->AssociatedIrp.MasterIrp->Size + 1);
    if ( v9 == 1 )
    {
      BlockDeviceCharacteristicsVPDPage = 0;
    }
    else if ( v9 )
    {
      BlockDeviceCharacteristicsVPDPage = -1073741637;
    }
    else if ( KeGetCurrentIrql() < 2u )
    {
      Length = CurrentStackLocation->Parameters.Read.Length;
      MasterIrp = Irp->AssociatedIrp.MasterIrp;
      if ( (unsigned int)Length < 0xC )
      {
        if ( (unsigned int)Length < 8 )
        {
          BlockDeviceCharacteristicsVPDPage = -1073741789;
        }
        else
        {
          Information = 8;
          *(_DWORD *)&MasterIrp->Type = 12;
          *(_DWORD *)(&MasterIrp->Size + 1) = 12;
          BlockDeviceCharacteristicsVPDPage = 0;
        }
        goto LABEL_41;
      }
      LowerDeviceObject_high = HIDWORD(DeviceExtension[2].ChildList->CommonExtension.LowerDeviceObject);
      if ( !LowerDeviceObject_high )
      {
        BlockDeviceCharacteristicsVPDPage = ClassForwardIrpSynchronous(DeviceExtension, Irp);
        if ( (unsigned __int8)ClasspLowerLayerNotSupport((unsigned int)BlockDeviceCharacteristicsVPDPage) )
        {
          BlockDeviceCharacteristicsVPDPage = ClasspDeviceGetBlockDeviceCharacteristicsVPDPage(
                                                (__int64)DeviceExtension,
                                                a3);
          ChildList = DeviceExtension[2].ChildList;
          if ( BlockDeviceCharacteristicsVPDPage < 0 )
          {
            HIDWORD(ChildList->CommonExtension.LowerDeviceObject) = 2;
          }
          else
          {
            v17 = WORD2(ChildList->CommonExtension.RemoveTrackingSpinlock);
            if ( v17 == 1 )
            {
              v18 = 0;
              BlockDeviceCharacteristicsVPDPage = 0;
            }
            else
            {
              v18 = 1;
              if ( (unsigned __int16)(v17 - 1025) > 0xFBFDu )
                BlockDeviceCharacteristicsVPDPage = -1073741823;
              else
                BlockDeviceCharacteristicsVPDPage = 0;
            }
            HIDWORD(DeviceExtension[2].ChildList->CommonExtension.LowerDeviceObject) = 2;
            if ( BlockDeviceCharacteristicsVPDPage >= 0 )
            {
              memset(MasterIrp, 0, Length);
              *(_DWORD *)&MasterIrp->Type = 12;
              Information = 12;
              *(_DWORD *)(&MasterIrp->Size + 1) = 12;
              LOBYTE(MasterIrp->MdlAddress) = v18;
              *((_DWORD *)DeviceExtension[2].DeviceName.Buffer + 180) = v18 + 1;
            }
          }
        }
        else
        {
          HIDWORD(DeviceExtension[2].ChildList->CommonExtension.LowerDeviceObject) = 1;
          Information = Irp->IoStatus.Information;
          if ( BlockDeviceCharacteristicsVPDPage < 0 || Irp->IoStatus.Information < 0xC )
            *((_DWORD *)DeviceExtension[2].DeviceName.Buffer + 180) = 0;
          else
            *((_DWORD *)DeviceExtension[2].DeviceName.Buffer + 180) = (LOBYTE(Irp->AssociatedIrp.MasterIrp->MdlAddress) != 0)
                                                                    + 1;
        }
        if ( (unsigned int)dword_14004D060 > 5
          && (qword_14004D070 & 0x400000000000LL) != 0
          && (qword_14004D078 & 0x400000000000LL) == qword_14004D078 )
        {
          v19 = DeviceExtension[2].PartitionLength.QuadPart + 4;
          v34 = 16;
          v33 = v19;
          Buffer = DeviceExtension[2].DeviceName.Buffer;
          EventDescriptor.Keyword = 0x400000000000LL;
          *(_DWORD *)&EventDescriptor.Id = 184549376;
          v21 = *((_BYTE *)Buffer + 720);
          v35 = &v26;
          *(_DWORD *)&EventDescriptor.Level = 5;
          UserData.Ptr = (unsigned __int64)EventInformation;
          v26 = v21;
          v36 = 1;
          UserData.Size = *(unsigned __int16 *)EventInformation;
          v30 = &unk_140048DF0;
          UserData.Reserved = 2;
          v31 = 61;
          v32 = 1;
          v27 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
          EtwWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 4u, &UserData);
        }
        goto LABEL_41;
      }
      BlockDeviceCharacteristicsVPDPage = -1073741823;
      if ( LowerDeviceObject_high == 2 )
      {
        BlockDeviceCharacteristicsVPDPage = ClasspDeviceGetBlockDeviceCharacteristicsVPDPage(
                                              (__int64)DeviceExtension,
                                              a3);
        if ( BlockDeviceCharacteristicsVPDPage >= 0 )
        {
          v14 = WORD2(DeviceExtension[2].ChildList->CommonExtension.RemoveTrackingSpinlock);
          if ( v14 == 1 )
          {
            v15 = 0;
          }
          else
          {
            if ( (unsigned __int16)(v14 - 1025) > 0xFBFDu )
            {
              BlockDeviceCharacteristicsVPDPage = -1073741823;
              goto LABEL_41;
            }
            v15 = 1;
          }
          BlockDeviceCharacteristicsVPDPage = 0;
          memset(MasterIrp, 0, Length);
          *(_DWORD *)&MasterIrp->Type = 12;
          Information = 12;
          *(_DWORD *)(&MasterIrp->Size + 1) = 12;
          LOBYTE(MasterIrp->MdlAddress) = v15;
          *((_DWORD *)DeviceExtension[2].DeviceName.Buffer + 180) = v15 + 1;
        }
      }
    }
    else
    {
      BlockDeviceCharacteristicsVPDPage = -1073741496;
    }
LABEL_41:
    Irp->IoStatus.Information = Information;
    Irp->IoStatus.Status = BlockDeviceCharacteristicsVPDPage;
    ClassReleaseRemoveLock(DeviceObject, Irp);
    ClassCompleteRequest(DeviceObject, Irp, 0);
    return BlockDeviceCharacteristicsVPDPage;
  }
  *(_OWORD *)&CurrentStackLocation[-1].MajorFunction = *(_OWORD *)&CurrentStackLocation->MajorFunction;
  *(_OWORD *)&CurrentStackLocation[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&CurrentStackLocation->Parameters.NotifyDirectoryEx.CompletionFilter;
  *(_OWORD *)(&CurrentStackLocation[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&CurrentStackLocation->Parameters.SetQuota
                                                                             + 6);
  CurrentStackLocation[-1].FileObject = CurrentStackLocation->FileObject;
  CurrentStackLocation[-1].Control = 0;
  v23 = (_DWORD **)DeviceObject->DeviceExtension;
  v24 = *v23[55];
  if ( v24 )
  {
    while ( 1 )
    {
      v25 = v24;
      v24 = _InterlockedCompareExchange(v23[55], v24 - 1, v24);
      if ( v25 == v24 )
        break;
      if ( !v24 )
        goto LABEL_45;
    }
  }
  else
  {
LABEL_45:
    ExReleaseRundownProtectionCacheAware((PEX_RUNDOWN_REF_CACHE_AWARE)(v23[55] + 2));
  }
  return IofCallDriver(DeviceExtension->LowerDeviceObject, Irp);
}

```

## disassembly

```asm
0x14001ecc0  push    rbx
0x14001ecc2  push    rsi
0x14001ecc3  push    rdi
0x14001ecc4  push    r13
0x14001ecc6  push    r15
0x14001ecc8  sub     rsp, 0B0h
0x14001eccf  mov     rax, cs:__security_cookie
0x14001ecd6  xor     rax, rsp
0x14001ecd9  mov     [rsp+0D8h+var_48], rax
0x14001ece1  cmp     dword ptr [rcx+48h], 7
0x14001ece5  mov     r15, r8
0x14001ece8  mov     rdi, [rcx+40h]
0x14001ecec  mov     rsi, rdx
0x14001ecef  mov     rbx, [rdx+0B8h]
0x14001ecf6  mov     r13, rcx
0x14001ecf9  jnz     loc_14001F0B0
0x14001ecff  mov     eax, [rcx+34h]
0x14001ed02  test    al, 4
0x14001ed04  jnz     loc_14001F0B0
0x14001ed0a  mov     rax, [rdi+480h]
0x14001ed11  cmp     dword ptr [rax+14h], 1
0x14001ed15  jz      loc_14001F0B0
0x14001ed1b  mov     rax, [rdx+18h]
0x14001ed1f  mov     [rsp+0D8h+arg_18], rbp
0x14001ed27  xor     ebp, ebp
0x14001ed29  mov     ecx, [rax+4]
0x14001ed2c  cmp     ecx, 1
0x14001ed2f  jnz     short loc_14001ED38
0x14001ed31  xor     ebx, ebx
0x14001ed33  jmp     loc_14001F082
0x14001ed38  test    ecx, ecx
0x14001ed3a  jz      short loc_14001ED46
0x14001ed3c  mov     ebx, 0C00000BBh
0x14001ed41  jmp     loc_14001F082
0x14001ed46  call    cs:__imp_KeGetCurrentIrql
0x14001ed4d  nop     dword ptr [rax+rax+00h]
0x14001ed52  cmp     al, 2
0x14001ed54  jb      short loc_14001ED60
0x14001ed56  mov     ebx, 0C0000148h
0x14001ed5b  jmp     loc_14001F082
0x14001ed60  mov     [rsp+0D8h+var_30], r12
0x14001ed68  mov     r12d, [rbx+8]
0x14001ed6c  mov     [rsp+0D8h+var_38], r14
0x14001ed74  mov     r14, [rsi+18h]
0x14001ed78  cmp     r12d, 0Ch
0x14001ed7c  jnb     short loc_14001EDA9
0x14001ed7e  cmp     r12d, 8
0x14001ed82  jb      short loc_14001ED9F
0x14001ed84  mov     ebp, 8
0x14001ed89  mov     dword ptr [r14], 0Ch
0x14001ed90  mov     dword ptr [r14+4], 0Ch
0x14001ed98  xor     ebx, ebx
0x14001ed9a  jmp     loc_14001F072
0x14001ed9f  mov     ebx, 0C0000023h
0x14001eda4  jmp     loc_14001F072
0x14001eda9  mov     rax, [rdi+480h]
0x14001edb0  mov     ecx, [rax+14h]
0x14001edb3  test    ecx, ecx
0x14001edb5  jz      loc_14001EE52
0x14001edbb  mov     ebx, 0C0000001h
0x14001edc0  cmp     ecx, 2
0x14001edc3  jnz     loc_14001F072
0x14001edc9  mov     rdx, r15
0x14001edcc  mov     rcx, rdi
0x14001edcf  call    ClasspDeviceGetBlockDeviceCharacteristicsVPDPage
0x14001edd4  mov     ebx, eax
0x14001edd6  test    eax, eax
0x14001edd8  js      loc_14001F072
0x14001edde  mov     rax, [rdi+480h]
0x14001ede5  movzx   ecx, word ptr [rax+4Ch]
0x14001ede9  cmp     cx, 1
0x14001eded  jnz     short loc_14001EDF4
0x14001edef  xor     r15b, r15b
0x14001edf2  jmp     short loc_14001EE09
0x14001edf4  mov     eax, 401h
0x14001edf9  sub     cx, ax
0x14001edfc  mov     eax, 0FBFDh
0x14001ee01  cmp     cx, ax
0x14001ee04  ja      short loc_14001EE48
0x14001ee06  mov     r15b, 1
0x14001ee09  mov     r8, r12; Size
0x14001ee0c  xor     edx, edx; Val
0x14001ee0e  mov     rcx, r14; void *
0x14001ee11  xor     ebx, ebx
0x14001ee13  call    memset
0x14001ee18  mov     dword ptr [r14], 0Ch
0x14001ee1f  mov     ebp, 0Ch
0x14001ee24  mov     dword ptr [r14+4], 0Ch
0x14001ee2c  mov     [r14+8], r15b
0x14001ee30  mov     rax, [rdi+478h]
0x14001ee37  movzx   ecx, r15b
0x14001ee3b  inc     ecx
0x14001ee3d  mov     [rax+2D0h], ecx
0x14001ee43  jmp     loc_14001F072
0x14001ee48  mov     ebx, 0C0000001h
0x14001ee4d  jmp     loc_14001F072
0x14001ee52  mov     rdx, rsi; Irp
0x14001ee55  mov     rcx, rdi; CommonExtension
0x14001ee58  call    ClassForwardIrpSynchronous
0x14001ee5d  mov     ecx, eax
0x14001ee5f  mov     ebx, eax
0x14001ee61  call    ClasspLowerLayerNotSupport
0x14001ee66  test    al, al
0x14001ee68  jz      loc_14001EF0E
0x14001ee6e  mov     rdx, r15
0x14001ee71  mov     rcx, rdi
0x14001ee74  call    ClasspDeviceGetBlockDeviceCharacteristicsVPDPage
0x14001ee79  mov     ebx, eax
0x14001ee7b  test    eax, eax
0x14001ee7d  mov     rax, [rdi+480h]
0x14001ee84  js      short loc_14001EF05
0x14001ee86  movzx   ecx, word ptr [rax+4Ch]
0x14001ee8a  cmp     cx, 1
0x14001ee8e  jnz     short loc_14001EE97
0x14001ee90  xor     r15b, r15b
0x14001ee93  xor     ebx, ebx
0x14001ee95  jmp     short loc_14001EEB5
0x14001ee97  mov     eax, 401h
0x14001ee9c  mov     r15b, 1
0x14001ee9f  sub     cx, ax
0x14001eea2  mov     eax, 0FBFDh
0x14001eea7  cmp     cx, ax
0x14001eeaa  ja      short loc_14001EEB0
0x14001eeac  xor     ebx, ebx
0x14001eeae  jmp     short loc_14001EEB5
0x14001eeb0  mov     ebx, 0C0000001h
0x14001eeb5  mov     rax, [rdi+480h]
0x14001eebc  mov     dword ptr [rax+14h], 2
0x14001eec3  test    ebx, ebx
0x14001eec5  js      loc_14001EF58
0x14001eecb  mov     r8, r12; Size
0x14001eece  xor     edx, edx; Val
0x14001eed0  mov     rcx, r14; void *
0x14001eed3  call    memset
0x14001eed8  mov     dword ptr [r14], 0Ch
0x14001eedf  mov     ebp, 0Ch
0x14001eee4  mov     dword ptr [r14+4], 0Ch
0x14001eeec  mov     [r14+8], r15b
0x14001eef0  mov     rax, [rdi+478h]
0x14001eef7  movzx   ecx, r15b
0x14001eefb  inc     ecx
0x14001eefd  mov     [rax+2D0h], ecx
0x14001ef03  jmp     short loc_14001EF58
0x14001ef05  mov     dword ptr [rax+14h], 2
0x14001ef0c  jmp     short loc_14001EF58
0x14001ef0e  mov     rax, [rdi+480h]
0x14001ef15  mov     dword ptr [rax+14h], 1
0x14001ef1c  mov     ebp, [rsi+38h]
0x14001ef1f  test    ebx, ebx
0x14001ef21  js      short loc_14001EF47
0x14001ef23  cmp     qword ptr [rsi+38h], 0Ch
0x14001ef28  jb      short loc_14001EF47
0x14001ef2a  mov     rax, [rsi+18h]
0x14001ef2e  xor     ecx, ecx
0x14001ef30  cmp     [rax+8], cl
0x14001ef33  mov     rax, [rdi+478h]
0x14001ef3a  setnz   cl
0x14001ef3d  inc     ecx
0x14001ef3f  mov     [rax+2D0h], ecx
0x14001ef45  jmp     short loc_14001EF58
0x14001ef47  mov     rax, [rdi+478h]
0x14001ef4e  mov     dword ptr [rax+2D0h], 0
0x14001ef58  mov     eax, cs:dword_14004D060
0x14001ef5e  cmp     eax, 5
0x14001ef61  jbe     loc_14001F072
0x14001ef67  mov     rcx, cs:qword_14004D078
0x14001ef6e  mov     rdx, 400000000000h
0x14001ef78  mov     rax, cs:qword_14004D070
0x14001ef7f  test    rdx, rax
0x14001ef82  jz      loc_14001F072
0x14001ef88  mov     rax, rcx
0x14001ef8b  and     rax, rdx
0x14001ef8e  cmp     rax, rcx
0x14001ef91  jnz     loc_14001F072
0x14001ef97  mov     rax, [rdi+490h]
0x14001ef9e  xor     r9d, r9d; RelatedActivityId
0x14001efa1  add     rax, 4
0x14001efa5  mov     [rsp+0D8h+var_60], 10h
0x14001efae  mov     [rsp+0D8h+var_68], rax
0x14001efb3  xor     r8d, r8d; ActivityId
0x14001efb6  mov     rax, [rdi+478h]
0x14001efbd  mov     [rsp+0D8h+EventDescriptor.Keyword], rdx
0x14001efc2  lea     rdx, [rsp+0D8h+EventDescriptor]; EventDescriptor
0x14001efc7  mov     dword ptr [rsp+0D8h+EventDescriptor.Id], 0B000000h
0x14001efcf  movzx   ecx, byte ptr [rax+2D0h]
0x14001efd6  lea     rax, [rsp+0D8h+var_A8]
0x14001efdb  mov     [rsp+0D8h+var_58], rax
0x14001efe3  movzx   eax, cs:word_140048DE6
0x14001efea  mov     dword ptr [rsp+0D8h+EventDescriptor.Level], eax
0x14001efee  mov     rax, cs:EventInformation
0x14001eff5  mov     [rsp+0D8h+var_88.Ptr], rax
0x14001effa  mov     [rsp+0D8h+var_A8], cl
0x14001effe  lea     rcx, _TraceLoggingMetadata
0x14001f005  mov     [rsp+0D8h+var_50], 1
0x14001f011  movzx   eax, word ptr [rax]
0x14001f014  mov     [rsp+0D8h+var_88.Size], eax
0x14001f018  lea     rax, unk_140048DF0
0x14001f01f  mov     [rsp+0D8h+var_78], rax
0x14001f024  lea     rax, _TraceLoggingMetadataEnd
0x14001f02b  sub     eax, ecx
0x14001f02d  mov     dword ptr [rsp+0D8h+var_88.___u2], 2
0x14001f035  mov     [rsp+0D8h+var_70], 3Dh ; '='
0x14001f03d  mov     [rsp+0D8h+var_6C], 1
0x14001f045  mov     [rsp+0D8h+var_A4], eax
0x14001f049  mov     eax, [rsp+0D8h+var_A4]
0x14001f04d  mov     rcx, cs:RegHandle; RegHandle
0x14001f054  lea     rax, [rsp+0D8h+var_88]
0x14001f059  mov     [rsp+0D8h+UserData], rax; UserData
0x14001f05e  mov     [rsp+0D8h+UserDataCount], 4; UserDataCount
0x14001f066  call    cs:__imp_EtwWriteTransfer
0x14001f06d  nop     dword ptr [rax+rax+00h]
0x14001f072  mov     r12, [rsp+0D8h+var_30]
0x14001f07a  mov     r14, [rsp+0D8h+var_38]
0x14001f082  mov     eax, ebp
0x14001f084  mov     rdx, rsi; Tag
0x14001f087  mov     rcx, r13; DeviceObject
0x14001f08a  mov     [rsi+38h], rax
0x14001f08e  mov     [rsi+30h], ebx
0x14001f091  call    ClassReleaseRemoveLock
0x14001f096  xor     r8d, r8d; PriorityBoost
0x14001f099  mov     rdx, rsi; Irp
0x14001f09c  mov     rcx, r13; DeviceObject
0x14001f09f  call    ClassCompleteRequest
0x14001f0a4  mov     rbp, [rsp+0D8h+arg_18]
0x14001f0ac  mov     eax, ebx
0x14001f0ae  jmp     short loc_14001F12E
0x14001f0b0  movups  xmm0, xmmword ptr [rbx]
0x14001f0b3  movups  xmmword ptr [rbx-48h], xmm0
0x14001f0b7  movups  xmm1, xmmword ptr [rbx+10h]
0x14001f0bb  movups  xmmword ptr [rbx-38h], xmm1
0x14001f0bf  movups  xmm0, xmmword ptr [rbx+20h]
0x14001f0c3  movups  xmmword ptr [rbx-28h], xmm0
0x14001f0c7  movsd   xmm1, qword ptr [rbx+30h]
0x14001f0cc  movsd   qword ptr [rbx-18h], xmm1
0x14001f0d1  mov     byte ptr [rbx-45h], 0
0x14001f0d5  mov     r8, [rcx+40h]
0x14001f0d9  mov     rax, [r8+1B8h]
0x14001f0e0  mov     eax, [rax]
0x14001f0e2  test    eax, eax
0x14001f0e4  jz      short loc_14001F104
0x14001f0e6  nop     word ptr [rax+rax+00000000h]
0x14001f0f0  mov     rcx, [r8+1B8h]
0x14001f0f7  lea     edx, [rax-1]
0x14001f0fa  lock cmpxchg [rcx], edx
0x14001f0fe  jz      short loc_14001F11B
0x14001f100  test    eax, eax
0x14001f102  jnz     short loc_14001F0F0
0x14001f104  mov     rcx, [r8+1B8h]
0x14001f10b  add     rcx, 8; RunRefCacheAware
0x14001f10f  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x14001f116  nop     dword ptr [rax+rax+00h]
0x14001f11b  mov     rcx, [rdi+10h]; DeviceObject
0x14001f11f  mov     rdx, rsi; Irp
0x14001f122  call    cs:__imp_IofCallDriver
0x14001f129  nop     dword ptr [rax+rax+00h]
0x14001f12e  mov     rcx, [rsp+0D8h+var_48]
0x14001f136  xor     rcx, rsp; StackCookie
0x14001f139  call    __security_check_cookie
0x14001f13e  add     rsp, 0B0h
0x14001f145  pop     r15
0x14001f147  pop     r13
0x14001f149  pop     rdi
0x14001f14a  pop     rsi
0x14001f14b  pop     rbx
0x14001f14c  retn
```
