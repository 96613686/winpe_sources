# IoctlFveWorker

- ea: `0x140068a40`
- end: `0x140069201`
- name: `IoctlFveWorker`
- size: `1985`
- prototype: `__int64 __fastcall(PIRP Irp)`
- caller_count: `0`
- callee_count: `35`
- tags: `broker_com_uri`

## callees

- `0x140008288`
- `0x140008dc0`
- `0x140008e44`
- `0x140009bf4`
- `0x14000a150`
- `0x14000aef4`
- `0x14000e514`
- `0x1400218c0`
- `0x140051480`
- `0x14006631c`
- `0x14006654c`
- `0x1400667d8`
- `0x1400668a8`
- `0x140066a34`
- `0x140066bd4`
- `0x14006722c`
- `0x1400674c8`
- `0x140067764`
- `0x140067a80`
- `0x140067d6c`
- `0x140068234`
- `0x1400688e4`
- `0x14006898c`
- `0x140068a40`
- `0x14007972c`
- `0x140079d10`
- `0x140079e64`
- `0x140079ff8`
- `0x140088fb4`
- `0x140089068`
- `0x140097aa4`
- `0x14009ad38`
- `0x14009c26c`
- `0x1400b9548`
- `0x1400dcd40`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140068b61`
- `ntoskrnl!IofCompleteRequest` at `0x1400691a3`
- `ntoskrnl!IofCompleteRequest` at `0x140068b61`
- `ntoskrnl!IofCompleteRequest` at `0x1400691a3`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x140068b06`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x140068b06`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140069176`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140069176`
- `ntoskrnl!KeUnstackDetachProcess` at `0x14006915c`
- `ntoskrnl!KeUnstackDetachProcess` at `0x14006915c`
- `ntoskrnl!KeStackAttachProcess` at `0x140068c2b`
- `ntoskrnl!KeStackAttachProcess` at `0x140068c2b`

## pseudocode

```c
void __fastcall IoctlFveWorker(PIRP Irp)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  struct _KPROCESS *Flink; // rdi
  unsigned int LowPart; // r15d
  unsigned __int64 v5; // rax
  __int64 v6; // r13
  NTSTATUS v7; // eax
  NTSTATUS v8; // ebx
  PDEVICE_OBJECT v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // rsi
  __int64 v12; // rcx
  int v13; // ebx
  struct _DEVICE_OBJECT *AttachedDevice; // rdi
  __int64 v15; // rax
  __int64 v16; // r8
  __int64 v17; // rcx
  __int64 v18; // rcx
  PDEVICE_OBJECT v19; // rcx
  __int64 v20; // rdx
  __int64 v21; // rcx
  NTSTATUS DatasetEDrv; // eax
  char v23[8]; // [rsp+40h] [rbp-39h] BYREF
  PVOID Tag; // [rsp+48h] [rbp-31h]
  PIO_REMOVE_LOCK RemoveLock; // [rsp+50h] [rbp-29h]
  struct _KAPC_STATE ApcState; // [rsp+58h] [rbp-21h] BYREF

  memset(&ApcState, 0, sizeof(ApcState));
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 121, WPP_6f5eafb572893a1aac70ee2625a5ec36_Traceguids);
  }
  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  Flink = (struct _KPROCESS *)Irp->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink;
  v23[0] = 1;
  LowPart = CurrentStackLocation->Parameters.Read.ByteOffset.LowPart;
  v5 = (unsigned __int64)CurrentStackLocation->FileObject->FsContext & 0xFFFFFFFFFFFFFFFCuLL;
  v6 = *(_QWORD *)(v5 + 200);
  Tag = *(PVOID *)(*(_QWORD *)(v5 + 8) + 200LL);
  RemoveLock = (PIO_REMOVE_LOCK)((char *)Tag + 8);
  v7 = IoAcquireRemoveLockEx((PIO_REMOVE_LOCK)((char *)Tag + 8), Tag, File, 1u, 0x20u);
  v8 = v7;
  if ( v7 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        122,
        WPP_6f5eafb572893a1aac70ee2625a5ec36_Traceguids,
        (unsigned int)v7);
    }
    Irp->IoStatus.Information = 0;
    Irp->IoStatus.Status = v8;
    IofCompleteRequest(Irp, 0);
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      v10 = 123;
LABEL_147:
      WPP_SF_d(v9->AttachedDevice, v10, WPP_6f5eafb572893a1aac70ee2625a5ec36_Traceguids, (unsigned int)v8);
      return;
    }
    return;
  }
  v11 = *(_QWORD *)Tag;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 124, WPP_6f5eafb572893a1aac70ee2625a5ec36_Traceguids, v11);
  }
  FvePerfTraceDevOp(v11, FVE_PERF_FVE_IOCTL_START, LowPart);
  if ( HIWORD(LowPart) == 21574 )
  {
    v12 = *(unsigned int *)(*(_QWORD *)(v11 + 8) + 9676LL);
    if ( (v12 & 1) == 0 )
    {
      v8 = -1073741808;
      goto LABEL_141;
    }
  }
  if ( LowPart != 1163317408 && LowPart != 1163268296 )
    KeStackAttachProcess(Flink, &ApcState);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    v13 = *(_DWORD *)(v6 + 8);
    AttachedDevice = WPP_GLOBAL_Control->AttachedDevice;
    v15 = FveIoctlToString(LowPart);
    WPP_SF_qLsq(
      (_DWORD)AttachedDevice,
      125,
      (unsigned int)WPP_6f5eafb572893a1aac70ee2625a5ec36_Traceguids,
      v11,
      v13,
      v15,
      (char)Irp);
  }
  if ( !(unsigned int)Feature_BitLockerEphemeralVolumeSupport__private_IsEnabledDeviceUsageNoInline(v12)
    || (*(_BYTE *)(v11 + 4403) & 8) == 0
    || HIWORD(LowPart) != 17750
    || LowPart == 1163268227
    || LowPart == 1163268232
    || LowPart == 1163268268
    || LowPart == 1163268296
    || LowPart == 1163268308
    || LowPart == 1163284627
    || LowPart == 1163317383
    || LowPart == 1163317408 )
  {
    v17 = *(unsigned int *)(v6 + 8);
    if ( (_DWORD)v17 )
    {
      v18 = (unsigned int)(v17 - 1);
      if ( !(_DWORD)v18 )
      {
        if ( LowPart != 1163268296 && LowPart != 1163317408 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
          {
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 130, WPP_6f5eafb572893a1aac70ee2625a5ec36_Traceguids);
          }
          v8 = -1073741808;
          goto LABEL_140;
        }
        goto LABEL_68;
      }
      if ( (_DWORD)v18 != 1 )
      {
        v19 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 5u )
        {
          goto LABEL_119;
        }
        v20 = 131;
LABEL_118:
        WPP_SF_(v19->AttachedDevice, v20, WPP_6f5eafb572893a1aac70ee2625a5ec36_Traceguids);
LABEL_119:
        v8 = -1073741808;
        goto LABEL_120;
      }
      if ( (unsigned int)Feature_BitLockerEphemeralVolumeSupport__private_IsEnabledDeviceUsageNoInline(v18) )
      {
        v21 = *(_QWORD *)(v11 + 8);
        if ( (*(_BYTE *)(v21 + 10344) & 2) != 0 || (*(_DWORD *)(v21 + 9680) & 0x200000) != 0 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
          {
            WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 128, WPP_6f5eafb572893a1aac70ee2625a5ec36_Traceguids, LowPart);
          }
          v8 = -1071579038;
LABEL_120:
          if ( LowPart == 1163317408 || LowPart == 1163268296 )
            goto LABEL_141;
LABEL_140:
          KeUnstackDetachProcess(&ApcState);
          goto LABEL_141;
        }
      }
      switch ( LowPart )
      {
        case 0x45561083u:
          DatasetEDrv = IoctlFveGetDatasetEDrv(v11, Irp);
          break;
        case 0x45561097u:
          DatasetEDrv = IoctlFveProvideVmkEDrv((PVOID)v11);
          break;
        case 0x455610C8u:
          goto LABEL_68;
        case 0x4556D087u:
          DatasetEDrv = IoctlFveSetDatasetEDrv(v11, Irp);
          break;
        case 0x4556D0A0u:
LABEL_68:
          v8 = IoctlFveAction(v11, Irp, v23);
          goto LABEL_141;
        default:
          v19 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0
            || BYTE1(WPP_GLOBAL_Control->Timer) < 5u )
          {
            goto LABEL_119;
          }
          v20 = 129;
          goto LABEL_118;
      }
LABEL_139:
      v8 = DatasetEDrv;
      goto LABEL_140;
    }
    if ( LowPart > 0x4556D0A0 )
    {
      switch ( LowPart )
      {
        case 0x4556D0A7u:
          if ( (int)IsFvePremiumInLicense(v17, 32756) < 0 )
          {
            v8 = IsFveDeviceEncryptionInLicense();
            if ( v8 < 0 )
              goto LABEL_140;
          }
          DatasetEDrv = IoctlFveBindDataVolume(v11, Irp);
          goto LABEL_139;
        case 0x4556D0ABu:
          v8 = IsFvePremiumInLicense(v17, 32756);
          if ( v8 < 0 )
            goto LABEL_140;
          DatasetEDrv = IoctlFveUnbindDataVolume(v11);
          goto LABEL_139;
        case 0x4556D0B7u:
          if ( (int)IsFvePremiumInLicense(v17, 32756) < 0 )
          {
            v8 = IsFveDeviceEncryptionInLicense();
            if ( v8 < 0 )
              goto LABEL_140;
          }
          DatasetEDrv = IoctlFveUnbindAllDataVolume(v11);
          goto LABEL_139;
        case 0x4556D0E4u:
          if ( (int)IsFvePremiumInLicense(v17, 32756) < 0 )
          {
            v8 = IsFveDeviceEncryptionInLicense();
            if ( v8 < 0 )
              goto LABEL_140;
          }
          DatasetEDrv = IoctlFveBindDataVolume2(v11, Irp);
          goto LABEL_139;
        case 0x4556D0F3u:
          DatasetEDrv = IoctlFveStdMdSet(v11, Irp);
          goto LABEL_139;
        case 0x5446D804u:
          DatasetEDrv = FveTestRwStart(v11, Irp);
          goto LABEL_139;
        case 0x5446D808u:
          DatasetEDrv = FveTestRwQuery(v11, Irp);
          goto LABEL_139;
        case 0x5446D80Cu:
          DatasetEDrv = FveTestRwStop(v11, Irp);
          goto LABEL_139;
        case 0x5446D810u:
          DatasetEDrv = FveTestIce(v11);
          goto LABEL_139;
      }
      goto LABEL_111;
    }
    if ( LowPart == 1163317408 )
      goto LABEL_68;
    if ( LowPart <= 0x455610C8 )
    {
      switch ( LowPart )
      {
        case 0x455610C8u:
          goto LABEL_68;
        case 0x45561083u:
          DatasetEDrv = IoctlFveGetDataset(v11, Irp);
          goto LABEL_139;
        case 0x45561088u:
          DatasetEDrv = IoctlFveGetStatus(v11, Irp);
          goto LABEL_139;
        case 0x45561097u:
          DatasetEDrv = IoctlFveProvideVmk((PVOID)v11);
          goto LABEL_139;
        case 0x455610ACu:
          DatasetEDrv = IoctlFveVerifyBindDataVolume(v11, Irp);
          goto LABEL_139;
        case 0x455610B0u:
          DatasetEDrv = IoctlFveCheckUnlockInfoDataVolume(v11, Irp);
          goto LABEL_139;
      }
      goto LABEL_111;
    }
    switch ( LowPart )
    {
      case 0x455610EFu:
        DatasetEDrv = IoctlFveStdMdGet(v11, Irp);
        goto LABEL_139;
      case 0x4556508Fu:
        LOBYTE(v16) = 1;
        break;
      case 0x45565093u:
        v16 = 0;
        break;
      case 0x4556D087u:
        DatasetEDrv = IoctlFveSetDataset(v11, Irp);
        goto LABEL_139;
      default:
LABEL_111:
        if ( !(unsigned int)Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline(v17)
          || LowPart != 1163317483 )
        {
          v19 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0
            || BYTE1(WPP_GLOBAL_Control->Timer) < 5u )
          {
            goto LABEL_119;
          }
          v20 = 127;
          goto LABEL_118;
        }
        DatasetEDrv = IoctlFveHardwareWrapFvek(v11, Irp);
        goto LABEL_139;
    }
    DatasetEDrv = IoctlFveGetKey(v11, Irp, v16);
    goto LABEL_139;
  }
  v8 = -1071579039;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_Dd(
      WPP_GLOBAL_Control->AttachedDevice,
      126,
      WPP_6f5eafb572893a1aac70ee2625a5ec36_Traceguids,
      3223388257LL,
      LowPart);
  }
LABEL_141:
  IoReleaseRemoveLockEx(RemoveLock, Tag, 0x20u);
  FvePerfTraceDevOp(v11, FVE_PERF_FVE_IOCTL_STOP, LowPart);
  if ( v23[0] )
  {
    Irp->IoStatus.Status = v8;
    IofCompleteRequest(Irp, 0);
  }
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    v10 = 132;
    goto LABEL_147;
  }
}

```

## disassembly

```asm
0x140068a40  push    rbp
0x140068a42  push    rbx
0x140068a43  push    rsi
0x140068a44  push    rdi
0x140068a45  push    r12
0x140068a47  push    r13
0x140068a49  push    r14
0x140068a4b  push    r15
0x140068a4d  lea     rbp, [rsp-1Fh]
0x140068a52  sub     rsp, 98h
0x140068a59  mov     rax, cs:__security_cookie
0x140068a60  xor     rax, rsp
0x140068a63  mov     [rbp+57h+var_48], rax
0x140068a67  xorps   xmm0, xmm0
0x140068a6a  mov     r14, rcx
0x140068a6d  movups  xmmword ptr [rbp+57h+ApcState.ApcListHead.Flink], xmm0
0x140068a71  movups  xmmword ptr [rbp+57h+ApcState.ApcListHead.Flink+10h], xmm0
0x140068a75  movups  xmmword ptr [rbp+57h+ApcState.Process], xmm0
0x140068a79  mov     rcx, cs:WPP_GLOBAL_Control
0x140068a80  lea     r12, WPP_GLOBAL_Control
0x140068a87  cmp     rcx, r12
0x140068a8a  jz      short loc_140068AAE
0x140068a8c  mov     eax, [rcx+2Ch]
0x140068a8f  test    al, 10h
0x140068a91  jz      short loc_140068AAE
0x140068a93  cmp     byte ptr [rcx+29h], 5
0x140068a97  jb      short loc_140068AAE
0x140068a99  mov     rcx, [rcx+18h]
0x140068a9d  lea     r8, WPP_6f5eafb572893a1aac70ee2625a5ec36_Traceguids
0x140068aa4  mov     edx, 79h ; 'y'
0x140068aa9  call    WPP_SF_
0x140068aae  mov     rax, [r14+0B8h]
0x140068ab5  lea     r8, File; File
0x140068abc  mov     rdi, [r14+78h]
0x140068ac0  mov     r9d, 1; Line
0x140068ac6  mov     [rbp+57h+var_90], 1
0x140068aca  mov     [rsp+0D0h+RemlockSize], 20h ; ' '; RemlockSize
0x140068ad2  mov     r15d, [rax+18h]
0x140068ad6  mov     rax, [rax+30h]
0x140068ada  mov     rax, [rax+18h]
0x140068ade  and     rax, 0FFFFFFFFFFFFFFFCh
0x140068ae2  mov     r13, [rax+0C8h]
0x140068ae9  mov     rax, [rax+8]
0x140068aed  mov     rsi, [rax+0C8h]
0x140068af4  mov     rdx, rsi; Tag
0x140068af7  mov     [rbp+57h+Tag], rsi
0x140068afb  lea     rax, [rsi+8]
0x140068aff  mov     rcx, rax; RemoveLock
0x140068b02  mov     [rbp+57h+RemoveLock], rax
0x140068b06  call    cs:__imp_IoAcquireRemoveLockEx
0x140068b0d  nop     dword ptr [rax+rax+00h]
0x140068b12  mov     ebx, eax
0x140068b14  test    eax, eax
0x140068b16  jns     loc_140068B9C
0x140068b1c  mov     r10, cs:WPP_GLOBAL_Control
0x140068b23  cmp     r10, r12
0x140068b26  jz      short loc_140068B50
0x140068b28  mov     ecx, [r10+2Ch]
0x140068b2c  test    cl, 10h
0x140068b2f  jz      short loc_140068B50
0x140068b31  cmp     byte ptr [r10+29h], 2
0x140068b36  jb      short loc_140068B50
0x140068b38  mov     rcx, [r10+18h]
0x140068b3c  lea     r8, WPP_6f5eafb572893a1aac70ee2625a5ec36_Traceguids
0x140068b43  mov     edx, 7Ah ; 'z'
0x140068b48  mov     r9d, eax
0x140068b4b  call    WPP_SF_d
0x140068b50  xor     edx, edx; PriorityBoost
0x140068b52  mov     qword ptr [r14+38h], 0
0x140068b5a  mov     rcx, r14; Irp
0x140068b5d  mov     [r14+30h], ebx
0x140068b61  call    cs:__imp_IofCompleteRequest
0x140068b68  nop     dword ptr [rax+rax+00h]
0x140068b6d  mov     rcx, cs:WPP_GLOBAL_Control
0x140068b74  cmp     rcx, r12
0x140068b77  jz      loc_1400691E0
0x140068b7d  mov     eax, [rcx+2Ch]
0x140068b80  test    al, 10h
0x140068b82  jz      loc_1400691E0
0x140068b88  cmp     byte ptr [rcx+29h], 5
0x140068b8c  jb      loc_1400691E0
0x140068b92  mov     edx, 7Bh ; '{'
0x140068b97  jmp     loc_1400691CD
0x140068b9c  mov     rsi, [rsi]
0x140068b9f  mov     rcx, cs:WPP_GLOBAL_Control
0x140068ba6  cmp     rcx, r12
0x140068ba9  jz      short loc_140068BD0
0x140068bab  mov     eax, [rcx+2Ch]
0x140068bae  test    al, 10h
0x140068bb0  jz      short loc_140068BD0
0x140068bb2  cmp     byte ptr [rcx+29h], 4
0x140068bb6  jb      short loc_140068BD0
0x140068bb8  mov     rcx, [rcx+18h]
0x140068bbc  lea     r8, WPP_6f5eafb572893a1aac70ee2625a5ec36_Traceguids
0x140068bc3  mov     edx, 7Ch ; '|'
0x140068bc8  mov     r9, rsi
0x140068bcb  call    WPP_SF_q
0x140068bd0  mov     r8d, r15d
0x140068bd3  lea     rdx, FVE_PERF_FVE_IOCTL_START
0x140068bda  mov     rcx, rsi
0x140068bdd  call    FvePerfTraceDevOp
0x140068be2  mov     r12d, r15d
0x140068be5  shr     r12d, 10h
0x140068be9  cmp     r12d, 5446h
0x140068bf0  jnz     short loc_140068C12
0x140068bf2  mov     rax, [rsi+8]
0x140068bf6  mov     ecx, [rax+25CCh]
0x140068bfc  test    cl, 1
0x140068bff  jnz     short loc_140068C12
0x140068c01  mov     ebx, 0C0000010h
0x140068c06  lea     rdi, WPP_GLOBAL_Control
0x140068c0d  jmp     loc_140069168
0x140068c12  cmp     r15d, 4556D0A0h
0x140068c19  jz      short loc_140068C37
0x140068c1b  cmp     r15d, 455610C8h
0x140068c22  jz      short loc_140068C37
0x140068c24  lea     rdx, [rbp+57h+ApcState]; ApcState
0x140068c28  mov     rcx, rdi; PROCESS
0x140068c2b  call    cs:__imp_KeStackAttachProcess
0x140068c32  nop     dword ptr [rax+rax+00h]
0x140068c37  mov     rdi, cs:WPP_GLOBAL_Control
0x140068c3e  lea     rax, WPP_GLOBAL_Control
0x140068c45  cmp     rdi, rax
0x140068c48  jz      short loc_140068C8C
0x140068c4a  mov     eax, [rdi+2Ch]
0x140068c4d  test    al, 10h
0x140068c4f  jz      short loc_140068C8C
0x140068c51  cmp     byte ptr [rdi+29h], 5
0x140068c55  jb      short loc_140068C8C
0x140068c57  mov     ebx, [r13+8]
0x140068c5b  mov     ecx, r15d
0x140068c5e  mov     rdi, [rdi+18h]
0x140068c62  call    FveIoctlToString
0x140068c67  mov     [rsp+0D0h+var_A0], r14
0x140068c6c  lea     r8, WPP_6f5eafb572893a1aac70ee2625a5ec36_Traceguids
0x140068c73  mov     [rsp+0D0h+var_A8], rax
0x140068c78  mov     edx, 7Dh ; '}'
0x140068c7d  mov     r9, rsi
0x140068c80  mov     [rsp+0D0h+RemlockSize], ebx
0x140068c84  mov     rcx, rdi
0x140068c87  call    WPP_SF_qLsq
0x140068c8c  call    Feature_BitLockerEphemeralVolumeSupport__private_IsEnabledDeviceUsageNoInline
0x140068c91  mov     ebx, 45561083h
0x140068c96  mov     edx, 7FF4h
0x140068c9b  test    eax, eax
0x140068c9d  jz      loc_140068D37
0x140068ca3  test    byte ptr [rsi+1133h], 8
0x140068caa  jz      loc_140068D37
0x140068cb0  cmp     r12d, 4556h
0x140068cb7  jnz     short loc_140068D37
0x140068cb9  mov     eax, r15d
0x140068cbc  sub     eax, ebx
0x140068cbe  jz      short loc_140068D37
0x140068cc0  sub     eax, 5
0x140068cc3  jz      short loc_140068D37
0x140068cc5  sub     eax, 24h ; '$'
0x140068cc8  jz      short loc_140068D37
0x140068cca  sub     eax, 1Ch
0x140068ccd  jz      short loc_140068D37
0x140068ccf  sub     eax, 0Ch
0x140068cd2  jz      short loc_140068D37
0x140068cd4  sub     eax, 3FBFh
0x140068cd9  jz      short loc_140068D37
0x140068cdb  sub     eax, edx
0x140068cdd  jz      short loc_140068D37
0x140068cdf  cmp     eax, 19h
0x140068ce2  jz      short loc_140068D37
0x140068ce4  mov     ebx, 0C0210061h
0x140068ce9  mov     rcx, cs:WPP_GLOBAL_Control
0x140068cf0  lea     rdi, WPP_GLOBAL_Control
0x140068cf7  cmp     rcx, rdi
0x140068cfa  jz      loc_140069168
0x140068d00  mov     eax, [rcx+2Ch]
0x140068d03  test    al, 10h
0x140068d05  jz      loc_140069168
0x140068d0b  cmp     byte ptr [rcx+29h], 2
0x140068d0f  jb      loc_140069168
0x140068d15  mov     rcx, [rcx+18h]
0x140068d19  lea     r8, WPP_6f5eafb572893a1aac70ee2625a5ec36_Traceguids
0x140068d20  mov     edx, 7Eh ; '~'
0x140068d25  mov     [rsp+0D0h+RemlockSize], r15d
0x140068d2a  mov     r9d, ebx
0x140068d2d  call    WPP_SF_Dd
0x140068d32  jmp     loc_140069168
0x140068d37  mov     ecx, [r13+8]
0x140068d3b  test    ecx, ecx
0x140068d3d  jz      loc_140068ED9
0x140068d43  sub     ecx, 1
0x140068d46  jz      loc_140068E88
0x140068d4c  cmp     ecx, 1
0x140068d4f  jz      short loc_140068D87
0x140068d51  mov     rcx, cs:WPP_GLOBAL_Control
0x140068d58  lea     rdi, WPP_GLOBAL_Control
0x140068d5f  cmp     rcx, rdi
0x140068d62  jz      loc_14006906B
0x140068d68  mov     eax, [rcx+2Ch]
0x140068d6b  test    al, 10h
0x140068d6d  jz      loc_14006906B
0x140068d73  cmp     byte ptr [rcx+29h], 5
0x140068d77  jb      loc_14006906B
0x140068d7d  mov     edx, 83h
0x140068d82  jmp     loc_14006905B
0x140068d87  call    Feature_BitLockerEphemeralVolumeSupport__private_IsEnabledDeviceUsageNoInline
0x140068d8c  test    eax, eax
0x140068d8e  jz      short loc_140068DEB
0x140068d90  mov     rcx, [rsi+8]
0x140068d94  test    byte ptr [rcx+2868h], 2
0x140068d9b  jnz     short loc_140068DA9
0x140068d9d  test    dword ptr [rcx+25D0h], 200000h
0x140068da7  jz      short loc_140068DEB
0x140068da9  mov     rcx, cs:WPP_GLOBAL_Control
0x140068db0  lea     rdi, WPP_GLOBAL_Control
0x140068db7  cmp     rcx, rdi
0x140068dba  jz      short loc_140068DE1
0x140068dbc  mov     eax, [rcx+2Ch]
0x140068dbf  test    al, 1
0x140068dc1  jz      short loc_140068DE1
0x140068dc3  cmp     byte ptr [rcx+29h], 5
0x140068dc7  jb      short loc_140068DE1
0x140068dc9  mov     rcx, [rcx+18h]
0x140068dcd  lea     r8, WPP_6f5eafb572893a1aac70ee2625a5ec36_Traceguids
0x140068dd4  mov     edx, 80h
0x140068dd9  mov     r9d, r15d
0x140068ddc  call    WPP_SF_d
0x140068de1  mov     ebx, 0C0210062h
0x140068de6  jmp     loc_140069070
0x140068deb  mov     eax, r15d
0x140068dee  sub     eax, ebx
0x140068df0  jz      loc_140068E78
0x140068df6  sub     eax, 14h
0x140068df9  jz      short loc_140068E68
0x140068dfb  sub     eax, 31h ; '1'
0x140068dfe  jz      short loc_140068E42
0x140068e00  sub     eax, 0BFBFh
0x140068e05  jz      short loc_140068E58
0x140068e07  cmp     eax, 19h
0x140068e0a  jz      short loc_140068E42
0x140068e0c  mov     rcx, cs:WPP_GLOBAL_Control
0x140068e13  lea     rdi, WPP_GLOBAL_Control
0x140068e1a  cmp     rcx, rdi
0x140068e1d  jz      loc_14006906B
0x140068e23  mov     eax, [rcx+2Ch]
0x140068e26  test    al, 10h
0x140068e28  jz      loc_14006906B
0x140068e2e  cmp     byte ptr [rcx+29h], 5
0x140068e32  jb      loc_14006906B
0x140068e38  mov     edx, 81h
0x140068e3d  jmp     loc_14006905B
0x140068e42  lea     r8, [rbp+57h+var_90]
0x140068e46  mov     rdx, r14
0x140068e49  mov     rcx, rsi
0x140068e4c  call    IoctlFveAction
0x140068e51  mov     ebx, eax
0x140068e53  jmp     loc_140068C06
0x140068e58  mov     rdx, r14
0x140068e5b  mov     rcx, rsi
0x140068e5e  call    IoctlFveSetDatasetEDrv
0x140068e63  jmp     loc_14006914F
0x140068e68  mov     rdx, r14
0x140068e6b  mov     rcx, rsi
0x140068e6e  call    IoctlFveProvideVmkEDrv
0x140068e73  jmp     loc_14006914F
0x140068e78  mov     rdx, r14
0x140068e7b  mov     rcx, rsi
0x140068e7e  call    IoctlFveGetDatasetEDrv
0x140068e83  jmp     loc_14006914F
0x140068e88  cmp     r15d, 455610C8h
0x140068e8f  jz      short loc_140068E42
0x140068e91  cmp     r15d, 4556D0A0h
0x140068e98  jz      short loc_140068E42
0x140068e9a  mov     rcx, cs:WPP_GLOBAL_Control
0x140068ea1  lea     rdi, WPP_GLOBAL_Control
0x140068ea8  cmp     rcx, rdi
0x140068eab  jz      short loc_140068ECF
0x140068ead  mov     eax, [rcx+2Ch]
0x140068eb0  test    al, 10h
0x140068eb2  jz      short loc_140068ECF
0x140068eb4  cmp     byte ptr [rcx+29h], 5
0x140068eb8  jb      short loc_140068ECF
0x140068eba  mov     rcx, [rcx+18h]
0x140068ebe  lea     r8, WPP_6f5eafb572893a1aac70ee2625a5ec36_Traceguids
0x140068ec5  mov     edx, 82h
0x140068eca  call    WPP_SF_
0x140068ecf  mov     ebx, 0C0000010h
0x140068ed4  jmp     loc_140069158
0x140068ed9  cmp     r15d, 4556D0A0h
0x140068ee0  ja      loc_140068FC0
0x140068ee6  jz      loc_140068E42
0x140068eec  cmp     r15d, 455610C8h
0x140068ef3  ja      short loc_140068F6A
0x140068ef5  jz      loc_140068E42
0x140068efb  mov     eax, r15d
0x140068efe  sub     eax, ebx
0x140068f00  jz      short loc_140068F5A
0x140068f02  sub     eax, 5
0x140068f05  jz      short loc_140068F4A
0x140068f07  sub     eax, 0Fh
0x140068f0a  jz      short loc_140068F3A
0x140068f0c  sub     eax, 15h
0x140068f0f  jz      short loc_140068F2A
  ... truncated ...
```
