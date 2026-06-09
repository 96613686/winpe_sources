# MountMgrDeviceControl

- ea: `0x1400147a0`
- end: `0x140014fb1`
- name: `MountMgrDeviceControl`
- size: `2065`
- prototype: `__int64 __fastcall(__int64, IRP *, __int64)`
- caller_count: `0`
- callee_count: `27`
- tags: `reparse_path, registry_config, broker_com_uri`

## callees

- `0x1400015a0`
- `0x140001960`
- `0x140001ae0`
- `0x140001ebc`
- `0x140002354`
- `0x140002924`
- `0x14000a510`
- `0x14000bcac`
- `0x14000c528`
- `0x14000c9f8`
- `0x14000cb00`
- `0x14000cc30`
- `0x14000ce84`
- `0x14000cf1c`
- `0x14000d3ac`
- `0x14000d9a0`
- `0x14000ebe4`
- `0x14000f440`
- `0x14000f518`
- `0x140013a20`
- `0x1400147a0`
- `0x140014fc0`
- `0x140015d50`
- `0x1400168b0`
- `0x140018560`
- `0x14001a190`
- `0x14001aab0`

## import_xrefs

- `ntoskrnl!PsIsHostSilo` at `0x14001481a`
- `ntoskrnl!PsIsHostSilo` at `0x14001481a`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x140014ae5`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x140014ae5`
- `ntoskrnl!KeReleaseMutex` at `0x14001484e`
- `ntoskrnl!KeReleaseMutex` at `0x1400148cb`
- `ntoskrnl!KeReleaseMutex` at `0x140014923`
- `ntoskrnl!KeReleaseMutex` at `0x140014be9`
- `ntoskrnl!KeReleaseMutex` at `0x140014c0f`
- `ntoskrnl!KeReleaseMutex` at `0x140014d35`
- `ntoskrnl!KeReleaseMutex` at `0x140014d74`
- `ntoskrnl!KeReleaseMutex` at `0x140014e2d`
- `ntoskrnl!KeReleaseMutex` at `0x140014e69`
- `ntoskrnl!KeReleaseMutex` at `0x140014e92`
- `ntoskrnl!KeReleaseMutex` at `0x140014f2d`
- `ntoskrnl!KeReleaseMutex` at `0x14001484e`
- `ntoskrnl!KeReleaseMutex` at `0x1400148cb`
- `ntoskrnl!KeReleaseMutex` at `0x140014923`
- `ntoskrnl!KeReleaseMutex` at `0x140014be9`
- `ntoskrnl!KeReleaseMutex` at `0x140014c0f`
- `ntoskrnl!KeReleaseMutex` at `0x140014d35`
- `ntoskrnl!KeReleaseMutex` at `0x140014d74`
- `ntoskrnl!KeReleaseMutex` at `0x140014e2d`
- `ntoskrnl!KeReleaseMutex` at `0x140014e69`
- `ntoskrnl!KeReleaseMutex` at `0x140014e92`
- `ntoskrnl!KeReleaseMutex` at `0x140014f2d`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x140014c2b`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x140014cc1`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x140014c2b`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x140014cc1`
- `ntoskrnl!IofCompleteRequest` at `0x140014958`
- `ntoskrnl!IofCompleteRequest` at `0x1400149f5`
- `ntoskrnl!IofCompleteRequest` at `0x140014958`
- `ntoskrnl!IofCompleteRequest` at `0x1400149f5`
- `ntoskrnl!KeWaitForSingleObject` at `0x140014807`
- `ntoskrnl!KeWaitForSingleObject` at `0x140014882`
- `ntoskrnl!KeWaitForSingleObject` at `0x140014807`
- `ntoskrnl!KeWaitForSingleObject` at `0x140014882`

## string_xrefs

- `0x14001490c`: `IOCTL_MOUNTMGR_QUERY_DOS_VOLUME_PATH`
- `0x140014b8c`: `IOCTL_MOUNTMGR_QUERY_DOS_VOLUME_PATH`
- `0x1400149ee`: `IOCTL_MOUNTMGR_CHECK_UNPROCESSED_VOLUMES`
- `0x140014a19`: `IOCTL_MOUNTMGR_QUERY_POINTS`
- `0x140014ba5`: `IOCTL_MOUNTMGR_QUERY_POINTS`
- `0x140014a90`: `IOCTL_MOUNTMGR_QUERY_DOS_VOLUME_PATHS`
- `0x140014b73`: `IOCTL_MOUNTMGR_QUERY_DOS_VOLUME_PATHS`
- `0x140014aa7`: `IOCTL_MOUNTMGR_CHANGE_NOTIFY`
- `0x140014c52`: `IOCTL_MOUNTMGR_CREATE_POINT`
- `0x140014d95`: `IOCTL_MOUNTMGR_CREATE_POINT`
- `0x140014c93`: `IOCTL_MOUNTMGR_NEXT_DRIVE_LETTER`
- `0x140014e09`: `IOCTL_MOUNTMGR_NEXT_DRIVE_LETTER`
- `0x140014be2`: `IOCTL_MOUNTMGR_VOLUME_REMOVAL_NOTIFICATION`
- `0x140014d2e`: `IOCTL_MOUNTMGR_VOLUME_REMOVAL_NOTIFICATION`
- `0x140014c08`: `IOCTL_MOUNTMGR_VOLUME_ARRIVAL_NOTIFICATION`
- `0x140014d6d`: `IOCTL_MOUNTMGR_VOLUME_ARRIVAL_NOTIFICATION`
- `0x140014b41`: `IOCTL_MOUNTMGR_QUERY_POINTS_ADMIN`
- `0x140014ce5`: `IOCTL_MOUNTMGR_QUERY_POINTS_ADMIN`
- `0x140014b5a`: `IOCTL_MOUNTMGR_QUERY_AUTO_MOUNT`
- `0x140014cfc`: `IOCTL_MOUNTMGR_QUERY_AUTO_MOUNT`
- `0x140014c3f`: `IOCTL_MOUNTMGR_TRACELOG_CACHE`
- `0x140014d56`: `IOCTL_MOUNTMGR_TRACELOG_CACHE`
- `0x140014ddb`: `IOCTL_MOUNTMGR_DELETE_POINTS`
- `0x140014df2`: `IOCTL_MOUNTMGR_DELETE_POINTS_DBONLY`
- `0x140014e23`: `IOCTL_MOUNTMGR_AUTO_DL_ASSIGNMENTS`
- `0x140014e48`: `IOCTL_MOUNTMGR_BOOT_DL_ASSIGNMENT`
- `0x140014e62`: `IOCTL_MOUNTMGR_VOLUME_MOUNT_POINT_CREATED`
- `0x140014e8b`: `IOCTL_MOUNTMGR_VOLUME_MOUNT_POINT_DELETED`
- `0x140014eb1`: `IOCTL_MOUNTMGR_KEEP_LINKS_WHEN_OFFLINE`
- `0x140014ec8`: `IOCTL_MOUNTMGR_SCRUB_REGISTRY`
- `0x140014edc`: `IOCTL_MOUNTMGR_SET_AUTO_MOUNT`
- `0x140014ef3`: `IOCTL_MOUNTMGR_PREPARE_VOLUME_REMOVAL`
- `0x140014f0a`: `IOCTL_MOUNTMGR_SILO_ARRIVAL`

## pseudocode

```c
__int64 __fastcall MountMgrDeviceControl(__int64 a1, IRP *a2, __int64 a3)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  struct _KMUTANT *v4; // rbp
  unsigned int LowPart; // r13d
  __int64 v7; // rcx
  int DriveLetter; // esi
  PVOID *p_Blink; // rcx
  unsigned __int8 *v10; // rbx
  const char *v11; // rdi
  int DosVolumePath; // eax
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v16; // rax
  int v17; // edi
  __int64 v18; // r14
  int v19; // eax
  PVOID P; // [rsp+30h] [rbp-38h] BYREF
  PVOID *p_P; // [rsp+38h] [rbp-30h]

  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  v4 = *(struct _KMUTANT **)(a1 + 64);
  a2->IoStatus.Information = 0;
  LowPart = CurrentStackLocation->Parameters.Read.ByteOffset.LowPart;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 345, a3, LowPart);
  }
  KeWaitForSingleObject(&v4[1], Executive, 0, 0, 0);
  if ( !(unsigned __int8)PsIsHostSilo(v4[6].MutantListEntry.Blink) )
  {
    v11 = 0;
    v18 = PsAttachSiloToCurrentThread(v4[6].MutantListEntry.Blink);
    if ( LowPart > 0x6DC000 )
    {
      switch ( LowPart )
      {
        case 0x6DC004u:
        case 0x6DC00Cu:
        case 0x6DC040u:
        case 0x6DC044u:
        case 0x6DC04Cu:
        case 0x6DC050u:
        case 0x6DC054u:
          DriveLetter = -1073741637;
          break;
        case 0x6DC010u:
          v11 = "IOCTL_MOUNTMGR_NEXT_DRIVE_LETTER";
          DriveLetter = MountMgrNextDriveLetter(v4);
          break;
        case 0x6DC014u:
        case 0x6DC018u:
        case 0x6DC01Cu:
        case 0x6DC024u:
        case 0x6DC038u:
          goto LABEL_65;
        default:
          goto LABEL_66;
      }
      goto LABEL_67;
    }
    if ( LowPart == 7192576 )
    {
      v11 = "IOCTL_MOUNTMGR_CREATE_POINT";
      DriveLetter = MountMgrCreatePoint(v4);
      goto LABEL_67;
    }
    if ( LowPart > 0x6D4020 )
    {
      if ( LowPart != 7159848 )
      {
        switch ( LowPart )
        {
          case 0x6D402Cu:
            v11 = "IOCTL_MOUNTMGR_VOLUME_ARRIVAL_NOTIFICATION";
            KeReleaseMutex(v4 + 1, 0);
            v19 = MountMgrVolumeArrivalNotification(v4, a2);
            break;
          case 0x6D4048u:
            v11 = "IOCTL_MOUNTMGR_TRACELOG_CACHE";
            DriveLetter = MountMgrTracelogCache(v4);
            goto LABEL_67;
          case 0x6D4058u:
            v11 = "IOCTL_MOUNTMGR_VOLUME_REMOVAL_NOTIFICATION";
            KeReleaseMutex(v4 + 1, 0);
            v19 = MountMgrVolumeRemovalNotification(v4, a2);
            break;
          default:
            goto LABEL_66;
        }
        DriveLetter = v19;
        PsDetachSiloFromCurrentThread(v18);
        goto LABEL_18;
      }
    }
    else if ( LowPart != 7159840 )
    {
      switch ( LowPart )
      {
        case 0x6D0008u:
          v11 = "IOCTL_MOUNTMGR_QUERY_POINTS";
          DriveLetter = MountMgrQueryPoints((int)v4, (int)a2);
          goto LABEL_67;
        case 0x6D0030u:
          v11 = "IOCTL_MOUNTMGR_QUERY_DOS_VOLUME_PATH";
          DriveLetter = MountMgrQueryDosVolumePath(v4, a2);
          goto LABEL_67;
        case 0x6D0034u:
          v11 = "IOCTL_MOUNTMGR_QUERY_DOS_VOLUME_PATHS";
          DriveLetter = MountMgrQueryDosVolumePaths(v4, a2);
          goto LABEL_67;
        case 0x6D003Cu:
          v11 = "IOCTL_MOUNTMGR_QUERY_AUTO_MOUNT";
          DriveLetter = MountMgrQueryAutoMount(v4, a2);
          goto LABEL_67;
        case 0x6D4008u:
          v11 = "IOCTL_MOUNTMGR_QUERY_POINTS_ADMIN";
          DriveLetter = MountMgrQueryPoints((int)v4, (int)a2);
LABEL_67:
          PsDetachSiloFromCurrentThread(v18);
LABEL_14:
          KeReleaseMutex(v4 + 1, 0);
          if ( DriveLetter == -1 )
          {
            if ( &MountMgrDeviceControl == (_UNKNOWN *)gBreakOnFunction )
            {
              if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                goto LABEL_17;
              if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
                WPP_SF_qL(WPP_GLOBAL_Control->AttachedDevice);
            }
          }
          else if ( DriveLetter >= 0 )
          {
            goto LABEL_16;
          }
LABEL_27:
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          {
            WPP_SF_LL(WPP_GLOBAL_Control->AttachedDevice, v13, v14, LowPart, DriveLetter);
          }
LABEL_16:
          if ( DriveLetter == 259 )
            goto LABEL_18;
LABEL_17:
          a2->IoStatus.Status = DriveLetter;
          IofCompleteRequest(a2, 0);
          goto LABEL_18;
      }
LABEL_66:
      v11 = "IOCTL UNKNOWN";
      DriveLetter = -1073741808;
      goto LABEL_67;
    }
LABEL_65:
    DriveLetter = 0;
    goto LABEL_67;
  }
  if ( LowPart == 7143472 )
  {
    v11 = "IOCTL_MOUNTMGR_QUERY_DOS_VOLUME_PATH";
    DosVolumePath = MountMgrQueryDosVolumePath(v4, a2);
    goto LABEL_13;
  }
  if ( LowPart != 7159848 )
  {
    if ( LowPart != 7143432 )
    {
      if ( LowPart > 0x6DC000 )
      {
        switch ( LowPart )
        {
          case 0x6DC004u:
            v11 = "IOCTL_MOUNTMGR_DELETE_POINTS";
            DosVolumePath = MountMgrDeletePoints(v4, a2);
            goto LABEL_13;
          case 0x6DC00Cu:
            v11 = "IOCTL_MOUNTMGR_DELETE_POINTS_DBONLY";
            DosVolumePath = MountMgrDeletePointsDbOnly(v4, a2);
            goto LABEL_13;
          case 0x6DC010u:
            v11 = "IOCTL_MOUNTMGR_NEXT_DRIVE_LETTER";
            DosVolumePath = MountMgrNextDriveLetter(v4);
            goto LABEL_13;
          case 0x6DC014u:
            v11 = "IOCTL_MOUNTMGR_AUTO_DL_ASSIGNMENTS";
            DriveLetter = 0;
            KeReleaseMutex(v4 + 1, 0);
            goto LABEL_17;
          case 0x6DC018u:
            v11 = "IOCTL_MOUNTMGR_VOLUME_MOUNT_POINT_CREATED";
            KeReleaseMutex(v4 + 1, 0);
            DosVolumePath = MountMgrVolumeMountPointCreatedIoctl((int)v4, (int)a2);
            goto LABEL_13;
          case 0x6DC01Cu:
            v11 = "IOCTL_MOUNTMGR_VOLUME_MOUNT_POINT_DELETED";
            KeReleaseMutex(v4 + 1, 0);
            DosVolumePath = MountMgrVolumeMountPointDeletedIoctl((int)v4, (int)a2);
            goto LABEL_13;
          case 0x6DC024u:
            v11 = "IOCTL_MOUNTMGR_KEEP_LINKS_WHEN_OFFLINE";
            DosVolumePath = MountMgrKeepLinksWhenOffline(v4, a2);
            goto LABEL_13;
          case 0x6DC038u:
            v11 = "IOCTL_MOUNTMGR_SCRUB_REGISTRY";
            DosVolumePath = MountMgrScrubRegistry(v4);
            goto LABEL_13;
          case 0x6DC040u:
            v11 = "IOCTL_MOUNTMGR_SET_AUTO_MOUNT";
            DosVolumePath = MountMgrSetAutoMount(v4, a2);
            goto LABEL_13;
          case 0x6DC044u:
            v11 = "IOCTL_MOUNTMGR_BOOT_DL_ASSIGNMENT";
            DosVolumePath = MountMgrBootDriveLetterAssignment(v4, a2);
            goto LABEL_13;
          case 0x6DC04Cu:
          case 0x6DC050u:
            v11 = "IOCTL_MOUNTMGR_PREPARE_VOLUME_REMOVAL";
            DosVolumePath = MountMgrPrepareVolumeDelete(v4, a2);
            goto LABEL_13;
          case 0x6DC054u:
            v11 = "IOCTL_MOUNTMGR_SILO_ARRIVAL";
            DosVolumePath = MountMgrSiloArrival(v7, a2);
            goto LABEL_13;
          default:
            goto LABEL_92;
        }
      }
      if ( LowPart == 7192576 )
      {
        v11 = "IOCTL_MOUNTMGR_CREATE_POINT";
        DosVolumePath = MountMgrCreatePoint(v4);
        goto LABEL_13;
      }
      if ( LowPart == 7159840 )
      {
        v11 = "IOCTL_MOUNTMGR_CHANGE_NOTIFY";
        DosVolumePath = MountMgrChangeNotify(v4, a2);
        goto LABEL_13;
      }
      if ( LowPart > 0x6D4020 )
      {
        switch ( LowPart )
        {
          case 0x6D402Cu:
            v11 = "IOCTL_MOUNTMGR_VOLUME_ARRIVAL_NOTIFICATION";
            KeReleaseMutex(v4 + 1, 0);
            DriveLetter = MountMgrVolumeArrivalNotification(v4, a2);
            goto LABEL_18;
          case 0x6D4048u:
            v11 = "IOCTL_MOUNTMGR_TRACELOG_CACHE";
            DosVolumePath = MountMgrTracelogCache(v4);
            goto LABEL_13;
          case 0x6D4058u:
            v11 = "IOCTL_MOUNTMGR_VOLUME_REMOVAL_NOTIFICATION";
            KeReleaseMutex(v4 + 1, 0);
            DriveLetter = MountMgrVolumeRemovalNotification(v4, a2);
            goto LABEL_18;
        }
      }
      else
      {
        switch ( LowPart )
        {
          case 0x6D0034u:
            v11 = "IOCTL_MOUNTMGR_QUERY_DOS_VOLUME_PATHS";
            DosVolumePath = MountMgrQueryDosVolumePaths(v4, a2);
            goto LABEL_13;
          case 0x6D003Cu:
            v11 = "IOCTL_MOUNTMGR_QUERY_AUTO_MOUNT";
            DosVolumePath = MountMgrQueryAutoMount(v4, a2);
            goto LABEL_13;
          case 0x6D4008u:
            v11 = "IOCTL_MOUNTMGR_QUERY_POINTS_ADMIN";
            DosVolumePath = MountMgrQueryPoints((int)v4, (int)a2);
            goto LABEL_13;
        }
      }
LABEL_92:
      v11 = "IOCTL UNKNOWN";
      DriveLetter = -1073741808;
      KeReleaseMutex(v4 + 1, 0);
      goto LABEL_27;
    }
    v11 = "IOCTL_MOUNTMGR_QUERY_POINTS";
    DosVolumePath = MountMgrQueryPoints((int)v4, (int)a2);
LABEL_13:
    DriveLetter = DosVolumePath;
    goto LABEL_14;
  }
  KeReleaseMutex(v4 + 1, 0);
  p_P = &P;
  P = &P;
  DriveLetter = 0;
  KeWaitForSingleObject(&v4[1], Executive, 0, 0, 0);
  p_Blink = (PVOID *)&v4->MutantListEntry.Blink;
  if ( *p_Blink != p_Blink )
  {
    P = *p_Blink;
    p_P = (PVOID *)v4->OwnerThread;
    *p_P = &P;
    *((_QWORD *)P + 1) = &P;
    v4->OwnerThread = (struct _KTHREAD *)&v4->MutantListEntry.Blink;
    *p_Blink = p_Blink;
  }
  KeReleaseMutex(v4 + 1, 0);
  while ( 1 )
  {
    v10 = (unsigned __int8 *)P;
    if ( P == &P )
      break;
    if ( *((PVOID **)P + 1) != &P || (v16 = *(_QWORD *)P, *(PVOID *)(*(_QWORD *)P + 8LL) != P) )
      __fastfail(3u);
    P = *(PVOID *)P;
    *(_QWORD *)(v16 + 8) = &P;
    v17 = MountMgrMountedDeviceArrival(v4, v10 + 64, v10[129]);
    MountMgrFreeDeadDeviceInfo(v10);
    if ( DriveLetter >= 0 )
      DriveLetter = v17;
  }
  a2->IoStatus.Status = DriveLetter;
  v11 = "IOCTL_MOUNTMGR_CHECK_UNPROCESSED_VOLUMES";
  IofCompleteRequest(a2, 0);
LABEL_18:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_LsL(WPP_GLOBAL_Control->AttachedDevice, v13, v14, LowPart, (__int64)v11, DriveLetter);
  }
  return (unsigned int)DriveLetter;
}

```

## disassembly

```asm
0x1400147a0  push    rbx
0x1400147a2  push    rbp
0x1400147a3  push    r12
0x1400147a5  push    r13
0x1400147a7  push    r15
0x1400147a9  sub     rsp, 40h
0x1400147ad  mov     rax, [rdx+0B8h]
0x1400147b4  xor     r12d, r12d
0x1400147b7  mov     rbp, [rcx+40h]
0x1400147bb  mov     r15, rdx
0x1400147be  mov     [rdx+38h], r12
0x1400147c2  mov     r13d, [rax+18h]
0x1400147c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400147cd  lea     rax, WPP_GLOBAL_Control
0x1400147d4  cmp     rcx, rax
0x1400147d7  jz      short loc_1400147E4
0x1400147d9  mov     eax, [rcx+2Ch]
0x1400147dc  test    al, 2
0x1400147de  jnz     loc_140014ABB
0x1400147e4  mov     [rsp+68h+arg_0], rsi
0x1400147e9  lea     rcx, [rbp+38h]; Object
0x1400147ed  mov     [rsp+68h+arg_8], rdi
0x1400147f2  xor     r9d, r9d; Alertable
0x1400147f5  xor     r8d, r8d; WaitMode
0x1400147f8  mov     [rsp+68h+arg_10], r14
0x140014800  xor     edx, edx; WaitReason
0x140014802  mov     [rsp+68h+Timeout], r12; Timeout
0x140014807  call    cs:__imp_KeWaitForSingleObject
0x14001480e  nop     dword ptr [rax+rax+00h]
0x140014813  mov     rcx, [rbp+170h]
0x14001481a  call    cs:__imp_PsIsHostSilo
0x140014821  nop     dword ptr [rax+rax+00h]
0x140014826  test    al, al
0x140014828  jz      loc_140014ADB
0x14001482e  cmp     r13d, 6D0030h
0x140014835  jz      loc_140014909
0x14001483b  cmp     r13d, 6D4028h
0x140014842  jnz     loc_140014A0D
0x140014848  xor     edx, edx; Wait
0x14001484a  lea     rcx, [rbp+38h]; Mutex
0x14001484e  call    cs:__imp_KeReleaseMutex
0x140014855  nop     dword ptr [rax+rax+00h]
0x14001485a  lea     rax, [rsp+68h+P]
0x14001485f  mov     [rsp+68h+Timeout], r12; Timeout
0x140014864  mov     [rsp+68h+var_30], rax
0x140014869  lea     rcx, [rbp+38h]; Object
0x14001486d  lea     rax, [rsp+68h+P]
0x140014872  xor     r9d, r9d; Alertable
0x140014875  xor     r8d, r8d; WaitMode
0x140014878  mov     [rsp+68h+P], rax
0x14001487d  xor     edx, edx; WaitReason
0x14001487f  mov     esi, r12d
0x140014882  call    cs:__imp_KeWaitForSingleObject
0x140014889  nop     dword ptr [rax+rax+00h]
0x14001488e  lea     rcx, [rbp+20h]
0x140014892  cmp     [rcx], rcx
0x140014895  jz      short loc_1400148C5
0x140014897  mov     rax, [rcx]
0x14001489a  lea     rdx, [rsp+68h+P]
0x14001489f  mov     [rsp+68h+P], rax
0x1400148a4  mov     rax, [rcx+8]
0x1400148a8  mov     [rsp+68h+var_30], rax
0x1400148ad  mov     [rax], rdx
0x1400148b0  lea     rdx, [rsp+68h+P]
0x1400148b5  mov     rax, [rsp+68h+P]
0x1400148ba  mov     [rax+8], rdx
0x1400148be  mov     [rcx+8], rcx
0x1400148c2  mov     [rcx], rcx
0x1400148c5  xor     edx, edx; Wait
0x1400148c7  lea     rcx, [rbp+38h]; Mutex
0x1400148cb  call    cs:__imp_KeReleaseMutex
0x1400148d2  nop     dword ptr [rax+rax+00h]
0x1400148d7  nop     word ptr [rax+rax+00000000h]
0x1400148e0  mov     rbx, [rsp+68h+P]
0x1400148e5  lea     rax, [rsp+68h+P]
0x1400148ea  cmp     rbx, rax
0x1400148ed  jz      loc_1400149E5
0x1400148f3  lea     rax, [rsp+68h+P]
0x1400148f8  cmp     [rbx+8], rax
0x1400148fc  jz      loc_14001499D
0x140014902  mov     ecx, 3
0x140014907  int     29h; Win8: RtlFailFast(ecx)
0x140014909  mov     rdx, r15
0x14001490c  lea     rdi, aIoctlMountmgrQ_3; "IOCTL_MOUNTMGR_QUERY_DOS_VOLUME_PATH"
0x140014913  mov     rcx, rbp
0x140014916  call    MountMgrQueryDosVolumePath
0x14001491b  mov     esi, eax
0x14001491d  xor     edx, edx; Wait
0x14001491f  lea     rcx, [rbp+38h]; Mutex
0x140014923  call    cs:__imp_KeReleaseMutex
0x14001492a  nop     dword ptr [rax+rax+00h]
0x14001492f  cmp     esi, 0FFFFFFFFh
0x140014932  jz      loc_140014F45
0x140014938  lea     rbx, WPP_GLOBAL_Control
0x14001493f  test    esi, esi
0x140014941  js      loc_140014A2D
0x140014947  cmp     esi, 103h
0x14001494d  jz      short loc_140014964
0x14001494f  xor     edx, edx; PriorityBoost
0x140014951  mov     [r15+30h], esi
0x140014955  mov     rcx, r15; Irp
0x140014958  call    cs:__imp_IofCompleteRequest
0x14001495f  nop     dword ptr [rax+rax+00h]
0x140014964  mov     rcx, cs:WPP_GLOBAL_Control
0x14001496b  cmp     rcx, rbx
0x14001496e  jz      short loc_14001497B
0x140014970  mov     eax, [rcx+2Ch]
0x140014973  test    al, 2
0x140014975  jnz     loc_140014F8D
0x14001497b  mov     r14, [rsp+68h+arg_10]
0x140014983  mov     eax, esi
0x140014985  mov     rsi, [rsp+68h+arg_0]
0x14001498a  mov     rdi, [rsp+68h+arg_8]
0x14001498f  add     rsp, 40h
0x140014993  pop     r15
0x140014995  pop     r13
0x140014997  pop     r12
0x140014999  pop     rbp
0x14001499a  pop     rbx
0x14001499b  retn
0x14001499d  mov     rax, [rbx]
0x1400149a0  cmp     [rax+8], rbx
0x1400149a4  jnz     loc_140014902
0x1400149aa  mov     [rsp+68h+P], rax
0x1400149af  lea     rcx, [rsp+68h+P]
0x1400149b4  mov     [rax+8], rcx
0x1400149b8  lea     rdx, [rbx+40h]
0x1400149bc  movzx   r8d, byte ptr [rbx+81h]
0x1400149c4  mov     rcx, rbp
0x1400149c7  call    MountMgrMountedDeviceArrival
0x1400149cc  mov     rcx, rbx; P
0x1400149cf  mov     edi, eax
0x1400149d1  call    MountMgrFreeDeadDeviceInfo
0x1400149d6  test    esi, esi
0x1400149d8  js      loc_1400148E0
0x1400149de  mov     esi, edi
0x1400149e0  jmp     loc_1400148E0
0x1400149e5  xor     edx, edx; PriorityBoost
0x1400149e7  mov     [r15+30h], esi
0x1400149eb  mov     rcx, r15; Irp
0x1400149ee  lea     rdi, aIoctlMountmgrC; "IOCTL_MOUNTMGR_CHECK_UNPROCESSED_VOLUME"...
0x1400149f5  call    cs:__imp_IofCompleteRequest
0x1400149fc  nop     dword ptr [rax+rax+00h]
0x140014a01  lea     rbx, WPP_GLOBAL_Control
0x140014a08  jmp     loc_140014964
0x140014a0d  cmp     r13d, 6D0008h
0x140014a14  jnz     short loc_140014A5D
0x140014a16  mov     rdx, r15; int
0x140014a19  lea     rdi, aIoctlMountmgrQ_0; "IOCTL_MOUNTMGR_QUERY_POINTS"
0x140014a20  mov     rcx, rbp; int
0x140014a23  call    MountMgrQueryPoints
0x140014a28  jmp     loc_14001491B
0x140014a2d  mov     rcx, cs:WPP_GLOBAL_Control
0x140014a34  cmp     rcx, rbx
0x140014a37  jz      loc_140014947
0x140014a3d  mov     eax, [rcx+2Ch]
0x140014a40  test    al, 1
0x140014a42  jz      loc_140014947
0x140014a48  mov     rcx, [rcx+18h]
0x140014a4c  mov     r9d, r13d
0x140014a4f  mov     dword ptr [rsp+68h+Timeout], esi
0x140014a53  call    WPP_SF_LL
0x140014a58  jmp     loc_140014947
0x140014a5d  cmp     r13d, 6DC000h
0x140014a64  ja      loc_140014DA9
0x140014a6a  jz      loc_140014D92
0x140014a70  cmp     r13d, 6D4020h
0x140014a77  jz      short loc_140014AA4
0x140014a79  ja      loc_140014D10
0x140014a7f  mov     eax, r13d
0x140014a82  sub     eax, 6D0034h
0x140014a87  jnz     loc_140014CD2
0x140014a8d  mov     rdx, r15
0x140014a90  lea     rdi, aIoctlMountmgrQ; "IOCTL_MOUNTMGR_QUERY_DOS_VOLUME_PATHS"
0x140014a97  mov     rcx, rbp
0x140014a9a  call    MountMgrQueryDosVolumePaths
0x140014a9f  jmp     loc_14001491B
0x140014aa4  mov     rdx, r15
0x140014aa7  lea     rdi, aIoctlMountmgrC_1; "IOCTL_MOUNTMGR_CHANGE_NOTIFY"
0x140014aae  mov     rcx, rbp
0x140014ab1  call    MountMgrChangeNotify
0x140014ab6  jmp     loc_14001491B
0x140014abb  cmp     byte ptr [rcx+29h], 2
0x140014abf  jb      loc_1400147E4
0x140014ac5  mov     rcx, [rcx+18h]
0x140014ac9  mov     edx, 159h
0x140014ace  mov     r9d, r13d
0x140014ad1  call    WPP_SF_L
0x140014ad6  jmp     loc_1400147E4
0x140014adb  mov     rcx, [rbp+170h]
0x140014ae2  mov     rdi, r12
0x140014ae5  call    cs:__imp_PsAttachSiloToCurrentThread
0x140014aec  nop     dword ptr [rax+rax+00h]
0x140014af1  mov     r14, rax
0x140014af4  cmp     r13d, 6DC000h
0x140014afb  ja      loc_140014C65
0x140014b01  jz      loc_140014C4F
0x140014b07  cmp     r13d, 6D4020h
0x140014b0e  ja      loc_140014BBB
0x140014b14  jz      loc_140014CAD; jumptable 0000000140014C8A cases 7192596,7192600,7192604,7192612,7192632
0x140014b1a  mov     eax, r13d
0x140014b1d  sub     eax, 6D0008h
0x140014b22  jz      short loc_140014BA2
0x140014b24  sub     eax, 28h ; '('
0x140014b27  jz      short loc_140014B89
0x140014b29  sub     eax, 4
0x140014b2c  jz      short loc_140014B70
0x140014b2e  sub     eax, 8
0x140014b31  jz      short loc_140014B57
0x140014b33  cmp     eax, 3FCCh
0x140014b38  jnz     def_140014C8A; jumptable 0000000140014C8A default case, cases 7192581-7192587,7192589-7192591,7192593-7192595,7192597-7192599,7192601-7192603,7192605-7192611,7192613-7192631,7192633-7192639,7192641-7192643,7192645-7192651,7192653-7192655,7192657-7192659
0x140014b3e  mov     rdx, r15; int
0x140014b41  lea     rdi, aIoctlMountmgrQ_2; "IOCTL_MOUNTMGR_QUERY_POINTS_ADMIN"
0x140014b48  mov     rcx, rbp; int
0x140014b4b  call    MountMgrQueryPoints
0x140014b50  mov     esi, eax
0x140014b52  jmp     loc_140014CBE
0x140014b57  mov     rdx, r15
0x140014b5a  lea     rdi, aIoctlMountmgrQ_1; "IOCTL_MOUNTMGR_QUERY_AUTO_MOUNT"
0x140014b61  mov     rcx, rbp
0x140014b64  call    MountMgrQueryAutoMount
0x140014b69  mov     esi, eax
0x140014b6b  jmp     loc_140014CBE
0x140014b70  mov     rdx, r15
0x140014b73  lea     rdi, aIoctlMountmgrQ; "IOCTL_MOUNTMGR_QUERY_DOS_VOLUME_PATHS"
0x140014b7a  mov     rcx, rbp
0x140014b7d  call    MountMgrQueryDosVolumePaths
0x140014b82  mov     esi, eax
0x140014b84  jmp     loc_140014CBE
0x140014b89  mov     rdx, r15
0x140014b8c  lea     rdi, aIoctlMountmgrQ_3; "IOCTL_MOUNTMGR_QUERY_DOS_VOLUME_PATH"
0x140014b93  mov     rcx, rbp
0x140014b96  call    MountMgrQueryDosVolumePath
0x140014b9b  mov     esi, eax
0x140014b9d  jmp     loc_140014CBE
0x140014ba2  mov     rdx, r15; int
0x140014ba5  lea     rdi, aIoctlMountmgrQ_0; "IOCTL_MOUNTMGR_QUERY_POINTS"
0x140014bac  mov     rcx, rbp; int
0x140014baf  call    MountMgrQueryPoints
0x140014bb4  mov     esi, eax
0x140014bb6  jmp     loc_140014CBE
0x140014bbb  mov     eax, r13d
0x140014bbe  sub     eax, 6D4028h
0x140014bc3  jz      loc_140014CAD; jumptable 0000000140014C8A cases 7192596,7192600,7192604,7192612,7192632
0x140014bc9  sub     eax, 4
0x140014bcc  jz      short loc_140014C02
0x140014bce  sub     eax, 1Ch
0x140014bd1  jz      short loc_140014C3C
0x140014bd3  cmp     eax, 10h
0x140014bd6  jnz     def_140014C8A; jumptable 0000000140014C8A default case, cases 7192581-7192587,7192589-7192591,7192593-7192595,7192597-7192599,7192601-7192603,7192605-7192611,7192613-7192631,7192633-7192639,7192641-7192643,7192645-7192651,7192653-7192655,7192657-7192659
0x140014bdc  xor     edx, edx; Wait
0x140014bde  lea     rcx, [rbp+38h]; Mutex
0x140014be2  lea     rdi, aIoctlMountmgrV_2; "IOCTL_MOUNTMGR_VOLUME_REMOVAL_NOTIFICAT"...
0x140014be9  call    cs:__imp_KeReleaseMutex
0x140014bf0  nop     dword ptr [rax+rax+00h]
0x140014bf5  mov     rdx, r15
0x140014bf8  mov     rcx, rbp
0x140014bfb  call    MountMgrVolumeRemovalNotification
0x140014c00  jmp     short loc_140014C26
0x140014c02  xor     edx, edx; Wait
0x140014c04  lea     rcx, [rbp+38h]; Mutex
0x140014c08  lea     rdi, aIoctlMountmgrV_0; "IOCTL_MOUNTMGR_VOLUME_ARRIVAL_NOTIFICAT"...
0x140014c0f  call    cs:__imp_KeReleaseMutex
0x140014c16  nop     dword ptr [rax+rax+00h]
0x140014c1b  mov     rdx, r15
0x140014c1e  mov     rcx, rbp
0x140014c21  call    MountMgrVolumeArrivalNotification
0x140014c26  mov     rcx, r14
0x140014c29  mov     esi, eax
0x140014c2b  call    cs:__imp_PsDetachSiloFromCurrentThread
0x140014c32  nop     dword ptr [rax+rax+00h]
0x140014c37  jmp     loc_140014A01
0x140014c3c  mov     rcx, rbp
0x140014c3f  lea     rdi, aIoctlMountmgrT; "IOCTL_MOUNTMGR_TRACELOG_CACHE"
0x140014c46  call    MountMgrTracelogCache
0x140014c4b  mov     esi, eax
0x140014c4d  jmp     short loc_140014CBE
0x140014c4f  mov     rdx, r15
0x140014c52  lea     rdi, aIoctlMountmgrC_0; "IOCTL_MOUNTMGR_CREATE_POINT"
0x140014c59  mov     rcx, rbp; Context
0x140014c5c  call    MountMgrCreatePoint
0x140014c61  mov     esi, eax
0x140014c63  jmp     short loc_140014CBE
0x140014c65  lea     eax, [r13-6DC004h]; switch 81 cases
0x140014c6c  cmp     eax, 50h
0x140014c6f  ja      short def_140014C8A; jumptable 0000000140014C8A default case, cases 7192581-7192587,7192589-7192591,7192593-7192595,7192597-7192599,7192601-7192603,7192605-7192611,7192613-7192631,7192633-7192639,7192641-7192643,7192645-7192651,7192653-7192655,7192657-7192659
0x140014c71  lea     rdx, cs:140000000h
0x140014c78  movzx   eax, ds:(byte_140005B90 - 140000000h)[rdx+rax]
0x140014c80  mov     ecx, ds:(jpt_140014C8A - 140000000h)[rdx+rax*4]
0x140014c87  add     rcx, rdx
0x140014c8a  jmp     rcx; switch jump
0x140014c90  mov     rdx, r15; jumptable 0000000140014C8A case 7192592
0x140014c93  lea     rdi, aIoctlMountmgrN; "IOCTL_MOUNTMGR_NEXT_DRIVE_LETTER"
0x140014c9a  mov     rcx, rbp; Context
0x140014c9d  call    MountMgrNextDriveLetter
0x140014ca2  mov     esi, eax
0x140014ca4  jmp     short loc_140014CBE
0x140014ca6  mov     esi, 0C00000BBh; jumptable 0000000140014C8A cases 7192580,7192588,7192640,7192644,7192652,7192656,7192660
0x140014cab  jmp     short loc_140014CBE
0x140014cad  mov     esi, r12d; jumptable 0000000140014C8A cases 7192596,7192600,7192604,7192612,7192632
  ... truncated ...
```
