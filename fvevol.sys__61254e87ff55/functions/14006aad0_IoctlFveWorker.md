# IoctlFveWorker

- ea: `0x14006aad0`
- end: `0x14006b291`
- name: `IoctlFveWorker`
- size: `1985`
- prototype: `void __fastcall(PIRP Irp)`
- caller_count: `0`
- callee_count: `35`
- tags: `broker_com_uri`

## callees

- `0x140008348`
- `0x140008e80`
- `0x140008f04`
- `0x140009cb4`
- `0x14000a210`
- `0x14000afb4`
- `0x14000e6fc`
- `0x140022bf0`
- `0x140053480`
- `0x1400683ac`
- `0x1400685dc`
- `0x140068868`
- `0x140068938`
- `0x140068ac4`
- `0x140068c64`
- `0x1400692bc`
- `0x140069558`
- `0x1400697f4`
- `0x140069b10`
- `0x140069dfc`
- `0x14006a2c4`
- `0x14006a974`
- `0x14006aa1c`
- `0x14006aad0`
- `0x14007b75c`
- `0x14007bdb4`
- `0x14007bf08`
- `0x14007c09c`
- `0x14008b054`
- `0x14008b108`
- `0x140099b54`
- `0x14009cdf0`
- `0x14009e26c`
- `0x1400bb614`
- `0x1400dfc40`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14006abf1`
- `ntoskrnl!IofCompleteRequest` at `0x14006b233`
- `ntoskrnl!IofCompleteRequest` at `0x14006abf1`
- `ntoskrnl!IofCompleteRequest` at `0x14006b233`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x14006ab96`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x14006ab96`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14006b206`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14006b206`
- `ntoskrnl!KeUnstackDetachProcess` at `0x14006b1ec`
- `ntoskrnl!KeUnstackDetachProcess` at `0x14006b1ec`
- `ntoskrnl!KeStackAttachProcess` at `0x14006acbb`
- `ntoskrnl!KeStackAttachProcess` at `0x14006acbb`

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
  int v12; // ebx
  struct _DEVICE_OBJECT *AttachedDevice; // rdi
  __int64 v14; // rax
  __int64 v15; // r8
  __int64 v16; // rcx
  __int64 v17; // rcx
  PDEVICE_OBJECT v18; // rcx
  __int64 v19; // rdx
  __int64 v20; // rcx
  NTSTATUS DatasetEDrv; // eax
  char v22[8]; // [rsp+40h] [rbp-39h] BYREF
  PVOID Tag; // [rsp+48h] [rbp-31h]
  PIO_REMOVE_LOCK RemoveLock; // [rsp+50h] [rbp-29h]
  struct _KAPC_STATE ApcState; // [rsp+58h] [rbp-21h] BYREF

  memset(&ApcState, 0, sizeof(ApcState));
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 121, WPP_41f10b29aed5302dc99000bce2319ea3_Traceguids);
  }
  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  Flink = (struct _KPROCESS *)Irp->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink;
  v22[0] = 1;
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
        WPP_41f10b29aed5302dc99000bce2319ea3_Traceguids,
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
LABEL_146:
      WPP_SF_d(v9->AttachedDevice, v10, WPP_41f10b29aed5302dc99000bce2319ea3_Traceguids, (unsigned int)v8);
      return;
    }
    return;
  }
  v11 = *(_QWORD *)Tag;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 124, WPP_41f10b29aed5302dc99000bce2319ea3_Traceguids, v11);
  }
  FvePerfTraceDevOp(v11, FVE_PERF_FVE_IOCTL_START, LowPart);
  if ( HIWORD(LowPart) == 21574 && (*(_DWORD *)(*(_QWORD *)(v11 + 8) + 9924LL) & 1) == 0 )
  {
    v8 = -1073741808;
    goto LABEL_140;
  }
  if ( LowPart != 1163317408 && LowPart != 1163268296 )
    KeStackAttachProcess(Flink, &ApcState);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    v12 = *(_DWORD *)(v6 + 8);
    AttachedDevice = WPP_GLOBAL_Control->AttachedDevice;
    v14 = FveIoctlToString(LowPart);
    WPP_SF_qLsq(
      (_DWORD)AttachedDevice,
      125,
      (unsigned int)WPP_41f10b29aed5302dc99000bce2319ea3_Traceguids,
      v11,
      v12,
      v14,
      (char)Irp);
  }
  if ( !(unsigned int)((__int64 (*)(void))Feature_BitLockerEphemeralVolumeSupport__private_IsEnabledDeviceUsageNoInline)()
    || (*(_BYTE *)(v11 + 4419) & 8) == 0
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
    v16 = *(unsigned int *)(v6 + 8);
    if ( (_DWORD)v16 )
    {
      v17 = (unsigned int)(v16 - 1);
      if ( !(_DWORD)v17 )
      {
        if ( LowPart != 1163268296 && LowPart != 1163317408 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
          {
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 130, WPP_41f10b29aed5302dc99000bce2319ea3_Traceguids);
          }
          v8 = -1073741808;
          goto LABEL_139;
        }
        goto LABEL_67;
      }
      if ( (_DWORD)v17 != 1 )
      {
        v18 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 5u )
        {
          goto LABEL_118;
        }
        v19 = 131;
LABEL_117:
        WPP_SF_(v18->AttachedDevice, v19, WPP_41f10b29aed5302dc99000bce2319ea3_Traceguids);
LABEL_118:
        v8 = -1073741808;
        goto LABEL_119;
      }
      if ( (unsigned int)Feature_BitLockerEphemeralVolumeSupport__private_IsEnabledDeviceUsageNoInline(v17, 32756) )
      {
        v20 = *(_QWORD *)(v11 + 8);
        if ( (*(_BYTE *)(v20 + 10592) & 2) != 0 || (*(_DWORD *)(v20 + 9928) & 0x200000) != 0 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
          {
            WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 128, WPP_41f10b29aed5302dc99000bce2319ea3_Traceguids, LowPart);
          }
          v8 = -1071579038;
LABEL_119:
          if ( LowPart == 1163317408 || LowPart == 1163268296 )
            goto LABEL_140;
LABEL_139:
          KeUnstackDetachProcess(&ApcState);
          goto LABEL_140;
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
          goto LABEL_67;
        case 0x4556D087u:
          DatasetEDrv = IoctlFveSetDatasetEDrv(v11, Irp);
          break;
        case 0x4556D0A0u:
LABEL_67:
          v8 = IoctlFveAction(v11, Irp, v22);
          goto LABEL_140;
        default:
          v18 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0
            || BYTE1(WPP_GLOBAL_Control->Timer) < 5u )
          {
            goto LABEL_118;
          }
          v19 = 129;
          goto LABEL_117;
      }
LABEL_138:
      v8 = DatasetEDrv;
      goto LABEL_139;
    }
    if ( LowPart > 0x4556D0A0 )
    {
      switch ( LowPart )
      {
        case 0x4556D0A7u:
          if ( (int)IsFvePremiumInLicense(v16, 32756) < 0 )
          {
            v8 = IsFveDeviceEncryptionInLicense();
            if ( v8 < 0 )
              goto LABEL_139;
          }
          DatasetEDrv = IoctlFveBindDataVolume(v11, Irp);
          goto LABEL_138;
        case 0x4556D0ABu:
          v8 = IsFvePremiumInLicense(v16, 32756);
          if ( v8 < 0 )
            goto LABEL_139;
          DatasetEDrv = IoctlFveUnbindDataVolume(v11);
          goto LABEL_138;
        case 0x4556D0B7u:
          if ( (int)IsFvePremiumInLicense(v16, 32756) < 0 )
          {
            v8 = IsFveDeviceEncryptionInLicense();
            if ( v8 < 0 )
              goto LABEL_139;
          }
          DatasetEDrv = IoctlFveUnbindAllDataVolume(v11);
          goto LABEL_138;
        case 0x4556D0E4u:
          if ( (int)IsFvePremiumInLicense(v16, 32756) < 0 )
          {
            v8 = IsFveDeviceEncryptionInLicense();
            if ( v8 < 0 )
              goto LABEL_139;
          }
          DatasetEDrv = IoctlFveBindDataVolume2(v11, Irp);
          goto LABEL_138;
        case 0x4556D0F3u:
          DatasetEDrv = IoctlFveStdMdSet(v11, Irp);
          goto LABEL_138;
        case 0x5446D804u:
          DatasetEDrv = FveTestRwStart(v11, Irp);
          goto LABEL_138;
        case 0x5446D808u:
          DatasetEDrv = FveTestRwQuery(v11, Irp);
          goto LABEL_138;
        case 0x5446D80Cu:
          DatasetEDrv = FveTestRwStop(v11, Irp);
          goto LABEL_138;
        case 0x5446D810u:
          DatasetEDrv = FveTestIce(v11);
          goto LABEL_138;
      }
      goto LABEL_110;
    }
    if ( LowPart == 1163317408 )
      goto LABEL_67;
    if ( LowPart <= 0x455610C8 )
    {
      switch ( LowPart )
      {
        case 0x455610C8u:
          goto LABEL_67;
        case 0x45561083u:
          DatasetEDrv = IoctlFveGetDataset(v11, Irp);
          goto LABEL_138;
        case 0x45561088u:
          DatasetEDrv = IoctlFveGetStatus(v11, Irp);
          goto LABEL_138;
        case 0x45561097u:
          DatasetEDrv = IoctlFveProvideVmk((PVOID)v11);
          goto LABEL_138;
        case 0x455610ACu:
          DatasetEDrv = IoctlFveVerifyBindDataVolume(v11, Irp);
          goto LABEL_138;
        case 0x455610B0u:
          DatasetEDrv = IoctlFveCheckUnlockInfoDataVolume(v11, Irp);
          goto LABEL_138;
      }
      goto LABEL_110;
    }
    switch ( LowPart )
    {
      case 0x455610EFu:
        DatasetEDrv = IoctlFveStdMdGet(v11, Irp);
        goto LABEL_138;
      case 0x4556508Fu:
        LOBYTE(v15) = 1;
        break;
      case 0x45565093u:
        v15 = 0;
        break;
      case 0x4556D087u:
        DatasetEDrv = IoctlFveSetDataset(v11, Irp);
        goto LABEL_138;
      default:
LABEL_110:
        if ( !(unsigned int)Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline(v16, 32756)
          || LowPart != 1163317483 )
        {
          v18 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0
            || BYTE1(WPP_GLOBAL_Control->Timer) < 5u )
          {
            goto LABEL_118;
          }
          v19 = 127;
          goto LABEL_117;
        }
        DatasetEDrv = IoctlFveHardwareWrapFvek(v11, Irp);
        goto LABEL_138;
    }
    DatasetEDrv = IoctlFveGetKey(v11, Irp, v15);
    goto LABEL_138;
  }
  v8 = -1071579039;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_Dd(
      WPP_GLOBAL_Control->AttachedDevice,
      126,
      WPP_41f10b29aed5302dc99000bce2319ea3_Traceguids,
      3223388257LL,
      LowPart);
  }
LABEL_140:
  IoReleaseRemoveLockEx(RemoveLock, Tag, 0x20u);
  FvePerfTraceDevOp(v11, FVE_PERF_FVE_IOCTL_STOP, LowPart);
  if ( v22[0] )
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
    goto LABEL_146;
  }
}

```

## disassembly

```asm
0x14006aad0  push    rbp
0x14006aad2  push    rbx
0x14006aad3  push    rsi
0x14006aad4  push    rdi
0x14006aad5  push    r12
0x14006aad7  push    r13
0x14006aad9  push    r14
0x14006aadb  push    r15
0x14006aadd  lea     rbp, [rsp-1Fh]
0x14006aae2  sub     rsp, 98h
0x14006aae9  mov     rax, cs:__security_cookie
0x14006aaf0  xor     rax, rsp
0x14006aaf3  mov     [rbp+57h+var_48], rax
0x14006aaf7  xorps   xmm0, xmm0
0x14006aafa  mov     r14, rcx
0x14006aafd  movups  xmmword ptr [rbp+57h+ApcState.ApcListHead.Flink], xmm0
0x14006ab01  movups  xmmword ptr [rbp+57h+ApcState.ApcListHead.Flink+10h], xmm0
0x14006ab05  movups  xmmword ptr [rbp+57h+ApcState.Process], xmm0
0x14006ab09  mov     rcx, cs:WPP_GLOBAL_Control
0x14006ab10  lea     r12, WPP_GLOBAL_Control
0x14006ab17  cmp     rcx, r12
0x14006ab1a  jz      short loc_14006AB3E
0x14006ab1c  mov     eax, [rcx+2Ch]
0x14006ab1f  test    al, 10h
0x14006ab21  jz      short loc_14006AB3E
0x14006ab23  cmp     byte ptr [rcx+29h], 5
0x14006ab27  jb      short loc_14006AB3E
0x14006ab29  mov     rcx, [rcx+18h]
0x14006ab2d  lea     r8, WPP_41f10b29aed5302dc99000bce2319ea3_Traceguids
0x14006ab34  mov     edx, 79h ; 'y'
0x14006ab39  call    WPP_SF_
0x14006ab3e  mov     rax, [r14+0B8h]
0x14006ab45  lea     r8, File; File
0x14006ab4c  mov     rdi, [r14+78h]
0x14006ab50  mov     r9d, 1; Line
0x14006ab56  mov     [rbp+57h+var_90], 1
0x14006ab5a  mov     [rsp+0D0h+RemlockSize], 20h ; ' '; RemlockSize
0x14006ab62  mov     r15d, [rax+18h]
0x14006ab66  mov     rax, [rax+30h]
0x14006ab6a  mov     rax, [rax+18h]
0x14006ab6e  and     rax, 0FFFFFFFFFFFFFFFCh
0x14006ab72  mov     r13, [rax+0C8h]
0x14006ab79  mov     rax, [rax+8]
0x14006ab7d  mov     rsi, [rax+0C8h]
0x14006ab84  mov     rdx, rsi; Tag
0x14006ab87  mov     [rbp+57h+Tag], rsi
0x14006ab8b  lea     rax, [rsi+8]
0x14006ab8f  mov     rcx, rax; RemoveLock
0x14006ab92  mov     [rbp+57h+RemoveLock], rax
0x14006ab96  call    cs:__imp_IoAcquireRemoveLockEx
0x14006ab9d  nop     dword ptr [rax+rax+00h]
0x14006aba2  mov     ebx, eax
0x14006aba4  test    eax, eax
0x14006aba6  jns     loc_14006AC2C
0x14006abac  mov     r10, cs:WPP_GLOBAL_Control
0x14006abb3  cmp     r10, r12
0x14006abb6  jz      short loc_14006ABE0
0x14006abb8  mov     ecx, [r10+2Ch]
0x14006abbc  test    cl, 10h
0x14006abbf  jz      short loc_14006ABE0
0x14006abc1  cmp     byte ptr [r10+29h], 2
0x14006abc6  jb      short loc_14006ABE0
0x14006abc8  mov     rcx, [r10+18h]
0x14006abcc  lea     r8, WPP_41f10b29aed5302dc99000bce2319ea3_Traceguids
0x14006abd3  mov     edx, 7Ah ; 'z'
0x14006abd8  mov     r9d, eax
0x14006abdb  call    WPP_SF_d
0x14006abe0  xor     edx, edx; PriorityBoost
0x14006abe2  mov     qword ptr [r14+38h], 0
0x14006abea  mov     rcx, r14; Irp
0x14006abed  mov     [r14+30h], ebx
0x14006abf1  call    cs:__imp_IofCompleteRequest
0x14006abf8  nop     dword ptr [rax+rax+00h]
0x14006abfd  mov     rcx, cs:WPP_GLOBAL_Control
0x14006ac04  cmp     rcx, r12
0x14006ac07  jz      loc_14006B270
0x14006ac0d  mov     eax, [rcx+2Ch]
0x14006ac10  test    al, 10h
0x14006ac12  jz      loc_14006B270
0x14006ac18  cmp     byte ptr [rcx+29h], 5
0x14006ac1c  jb      loc_14006B270
0x14006ac22  mov     edx, 7Bh ; '{'
0x14006ac27  jmp     loc_14006B25D
0x14006ac2c  mov     rsi, [rsi]
0x14006ac2f  mov     rcx, cs:WPP_GLOBAL_Control
0x14006ac36  cmp     rcx, r12
0x14006ac39  jz      short loc_14006AC60
0x14006ac3b  mov     eax, [rcx+2Ch]
0x14006ac3e  test    al, 10h
0x14006ac40  jz      short loc_14006AC60
0x14006ac42  cmp     byte ptr [rcx+29h], 4
0x14006ac46  jb      short loc_14006AC60
0x14006ac48  mov     rcx, [rcx+18h]
0x14006ac4c  lea     r8, WPP_41f10b29aed5302dc99000bce2319ea3_Traceguids
0x14006ac53  mov     edx, 7Ch ; '|'
0x14006ac58  mov     r9, rsi
0x14006ac5b  call    WPP_SF_q
0x14006ac60  mov     r8d, r15d
0x14006ac63  lea     rdx, FVE_PERF_FVE_IOCTL_START
0x14006ac6a  mov     rcx, rsi
0x14006ac6d  call    FvePerfTraceDevOp
0x14006ac72  mov     r12d, r15d
0x14006ac75  shr     r12d, 10h
0x14006ac79  cmp     r12d, 5446h
0x14006ac80  jnz     short loc_14006ACA2
0x14006ac82  mov     rax, [rsi+8]
0x14006ac86  mov     ecx, [rax+26C4h]
0x14006ac8c  test    cl, 1
0x14006ac8f  jnz     short loc_14006ACA2
0x14006ac91  mov     ebx, 0C0000010h
0x14006ac96  lea     rdi, WPP_GLOBAL_Control
0x14006ac9d  jmp     loc_14006B1F8
0x14006aca2  cmp     r15d, 4556D0A0h
0x14006aca9  jz      short loc_14006ACC7
0x14006acab  cmp     r15d, 455610C8h
0x14006acb2  jz      short loc_14006ACC7
0x14006acb4  lea     rdx, [rbp+57h+ApcState]; ApcState
0x14006acb8  mov     rcx, rdi; PROCESS
0x14006acbb  call    cs:__imp_KeStackAttachProcess
0x14006acc2  nop     dword ptr [rax+rax+00h]
0x14006acc7  mov     rdi, cs:WPP_GLOBAL_Control
0x14006acce  lea     rax, WPP_GLOBAL_Control
0x14006acd5  cmp     rdi, rax
0x14006acd8  jz      short loc_14006AD1C
0x14006acda  mov     eax, [rdi+2Ch]
0x14006acdd  test    al, 10h
0x14006acdf  jz      short loc_14006AD1C
0x14006ace1  cmp     byte ptr [rdi+29h], 5
0x14006ace5  jb      short loc_14006AD1C
0x14006ace7  mov     ebx, [r13+8]
0x14006aceb  mov     ecx, r15d
0x14006acee  mov     rdi, [rdi+18h]
0x14006acf2  call    FveIoctlToString
0x14006acf7  mov     [rsp+0D0h+var_A0], r14
0x14006acfc  lea     r8, WPP_41f10b29aed5302dc99000bce2319ea3_Traceguids
0x14006ad03  mov     [rsp+0D0h+var_A8], rax
0x14006ad08  mov     edx, 7Dh ; '}'
0x14006ad0d  mov     r9, rsi
0x14006ad10  mov     [rsp+0D0h+RemlockSize], ebx
0x14006ad14  mov     rcx, rdi
0x14006ad17  call    WPP_SF_qLsq
0x14006ad1c  call    Feature_BitLockerEphemeralVolumeSupport__private_IsEnabledDeviceUsageNoInline
0x14006ad21  mov     ebx, 45561083h
0x14006ad26  mov     edx, 7FF4h
0x14006ad2b  test    eax, eax
0x14006ad2d  jz      loc_14006ADC7
0x14006ad33  test    byte ptr [rsi+1143h], 8
0x14006ad3a  jz      loc_14006ADC7
0x14006ad40  cmp     r12d, 4556h
0x14006ad47  jnz     short loc_14006ADC7
0x14006ad49  mov     eax, r15d
0x14006ad4c  sub     eax, ebx
0x14006ad4e  jz      short loc_14006ADC7
0x14006ad50  sub     eax, 5
0x14006ad53  jz      short loc_14006ADC7
0x14006ad55  sub     eax, 24h ; '$'
0x14006ad58  jz      short loc_14006ADC7
0x14006ad5a  sub     eax, 1Ch
0x14006ad5d  jz      short loc_14006ADC7
0x14006ad5f  sub     eax, 0Ch
0x14006ad62  jz      short loc_14006ADC7
0x14006ad64  sub     eax, 3FBFh
0x14006ad69  jz      short loc_14006ADC7
0x14006ad6b  sub     eax, edx
0x14006ad6d  jz      short loc_14006ADC7
0x14006ad6f  cmp     eax, 19h
0x14006ad72  jz      short loc_14006ADC7
0x14006ad74  mov     ebx, 0C0210061h
0x14006ad79  mov     rcx, cs:WPP_GLOBAL_Control
0x14006ad80  lea     rdi, WPP_GLOBAL_Control
0x14006ad87  cmp     rcx, rdi
0x14006ad8a  jz      loc_14006B1F8
0x14006ad90  mov     eax, [rcx+2Ch]
0x14006ad93  test    al, 10h
0x14006ad95  jz      loc_14006B1F8
0x14006ad9b  cmp     byte ptr [rcx+29h], 2
0x14006ad9f  jb      loc_14006B1F8
0x14006ada5  mov     rcx, [rcx+18h]
0x14006ada9  lea     r8, WPP_41f10b29aed5302dc99000bce2319ea3_Traceguids
0x14006adb0  mov     edx, 7Eh ; '~'
0x14006adb5  mov     [rsp+0D0h+RemlockSize], r15d
0x14006adba  mov     r9d, ebx
0x14006adbd  call    WPP_SF_Dd
0x14006adc2  jmp     loc_14006B1F8
0x14006adc7  mov     ecx, [r13+8]
0x14006adcb  test    ecx, ecx
0x14006adcd  jz      loc_14006AF69
0x14006add3  sub     ecx, 1
0x14006add6  jz      loc_14006AF18
0x14006addc  cmp     ecx, 1
0x14006addf  jz      short loc_14006AE17
0x14006ade1  mov     rcx, cs:WPP_GLOBAL_Control
0x14006ade8  lea     rdi, WPP_GLOBAL_Control
0x14006adef  cmp     rcx, rdi
0x14006adf2  jz      loc_14006B0FB
0x14006adf8  mov     eax, [rcx+2Ch]
0x14006adfb  test    al, 10h
0x14006adfd  jz      loc_14006B0FB
0x14006ae03  cmp     byte ptr [rcx+29h], 5
0x14006ae07  jb      loc_14006B0FB
0x14006ae0d  mov     edx, 83h
0x14006ae12  jmp     loc_14006B0EB
0x14006ae17  call    Feature_BitLockerEphemeralVolumeSupport__private_IsEnabledDeviceUsageNoInline
0x14006ae1c  test    eax, eax
0x14006ae1e  jz      short loc_14006AE7B
0x14006ae20  mov     rcx, [rsi+8]
0x14006ae24  test    byte ptr [rcx+2960h], 2
0x14006ae2b  jnz     short loc_14006AE39
0x14006ae2d  test    dword ptr [rcx+26C8h], 200000h
0x14006ae37  jz      short loc_14006AE7B
0x14006ae39  mov     rcx, cs:WPP_GLOBAL_Control
0x14006ae40  lea     rdi, WPP_GLOBAL_Control
0x14006ae47  cmp     rcx, rdi
0x14006ae4a  jz      short loc_14006AE71
0x14006ae4c  mov     eax, [rcx+2Ch]
0x14006ae4f  test    al, 1
0x14006ae51  jz      short loc_14006AE71
0x14006ae53  cmp     byte ptr [rcx+29h], 5
0x14006ae57  jb      short loc_14006AE71
0x14006ae59  mov     rcx, [rcx+18h]
0x14006ae5d  lea     r8, WPP_41f10b29aed5302dc99000bce2319ea3_Traceguids
0x14006ae64  mov     edx, 80h
0x14006ae69  mov     r9d, r15d
0x14006ae6c  call    WPP_SF_d
0x14006ae71  mov     ebx, 0C0210062h
0x14006ae76  jmp     loc_14006B100
0x14006ae7b  mov     eax, r15d
0x14006ae7e  sub     eax, ebx
0x14006ae80  jz      loc_14006AF08
0x14006ae86  sub     eax, 14h
0x14006ae89  jz      short loc_14006AEF8
0x14006ae8b  sub     eax, 31h ; '1'
0x14006ae8e  jz      short loc_14006AED2
0x14006ae90  sub     eax, 0BFBFh
0x14006ae95  jz      short loc_14006AEE8
0x14006ae97  cmp     eax, 19h
0x14006ae9a  jz      short loc_14006AED2
0x14006ae9c  mov     rcx, cs:WPP_GLOBAL_Control
0x14006aea3  lea     rdi, WPP_GLOBAL_Control
0x14006aeaa  cmp     rcx, rdi
0x14006aead  jz      loc_14006B0FB
0x14006aeb3  mov     eax, [rcx+2Ch]
0x14006aeb6  test    al, 10h
0x14006aeb8  jz      loc_14006B0FB
0x14006aebe  cmp     byte ptr [rcx+29h], 5
0x14006aec2  jb      loc_14006B0FB
0x14006aec8  mov     edx, 81h
0x14006aecd  jmp     loc_14006B0EB
0x14006aed2  lea     r8, [rbp+57h+var_90]
0x14006aed6  mov     rdx, r14
0x14006aed9  mov     rcx, rsi
0x14006aedc  call    IoctlFveAction
0x14006aee1  mov     ebx, eax
0x14006aee3  jmp     loc_14006AC96
0x14006aee8  mov     rdx, r14
0x14006aeeb  mov     rcx, rsi
0x14006aeee  call    IoctlFveSetDatasetEDrv
0x14006aef3  jmp     loc_14006B1DF
0x14006aef8  mov     rdx, r14
0x14006aefb  mov     rcx, rsi
0x14006aefe  call    IoctlFveProvideVmkEDrv
0x14006af03  jmp     loc_14006B1DF
0x14006af08  mov     rdx, r14
0x14006af0b  mov     rcx, rsi
0x14006af0e  call    IoctlFveGetDatasetEDrv
0x14006af13  jmp     loc_14006B1DF
0x14006af18  cmp     r15d, 455610C8h
0x14006af1f  jz      short loc_14006AED2
0x14006af21  cmp     r15d, 4556D0A0h
0x14006af28  jz      short loc_14006AED2
0x14006af2a  mov     rcx, cs:WPP_GLOBAL_Control
0x14006af31  lea     rdi, WPP_GLOBAL_Control
0x14006af38  cmp     rcx, rdi
0x14006af3b  jz      short loc_14006AF5F
0x14006af3d  mov     eax, [rcx+2Ch]
0x14006af40  test    al, 10h
0x14006af42  jz      short loc_14006AF5F
0x14006af44  cmp     byte ptr [rcx+29h], 5
0x14006af48  jb      short loc_14006AF5F
0x14006af4a  mov     rcx, [rcx+18h]
0x14006af4e  lea     r8, WPP_41f10b29aed5302dc99000bce2319ea3_Traceguids
0x14006af55  mov     edx, 82h
0x14006af5a  call    WPP_SF_
0x14006af5f  mov     ebx, 0C0000010h
0x14006af64  jmp     loc_14006B1E8
0x14006af69  cmp     r15d, 4556D0A0h
0x14006af70  ja      loc_14006B050
0x14006af76  jz      loc_14006AED2
0x14006af7c  cmp     r15d, 455610C8h
0x14006af83  ja      short loc_14006AFFA
0x14006af85  jz      loc_14006AED2
0x14006af8b  mov     eax, r15d
0x14006af8e  sub     eax, ebx
0x14006af90  jz      short loc_14006AFEA
0x14006af92  sub     eax, 5
0x14006af95  jz      short loc_14006AFDA
0x14006af97  sub     eax, 0Fh
0x14006af9a  jz      short loc_14006AFCA
0x14006af9c  sub     eax, 15h
0x14006af9f  jz      short loc_14006AFBA
  ... truncated ...
```
