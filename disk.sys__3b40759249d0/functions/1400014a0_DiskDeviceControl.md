# DiskDeviceControl

- ea: `0x1400014a0`
- end: `0x1400019bb`
- name: `DiskDeviceControl`
- size: `1307`
- prototype: `NTSTATUS __fastcall(PDEVICE_OBJECT DeviceObject, PIRP Irp, __int64)`
- caller_count: `0`
- callee_count: `27`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x1400014a0`
- `0x14000372c`
- `0x1400037a8`
- `0x140003824`
- `0x140003cb0`
- `0x140003d30`
- `0x1400040ec`
- `0x140004154`
- `0x140005bf0`
- `0x14000e010`
- `0x14000e5f8`
- `0x14000e798`
- `0x14000e8b4`
- `0x14000ec08`
- `0x14000ef98`
- `0x14000f0b4`
- `0x14000f198`
- `0x140012210`
- `0x140012b30`
- `0x1400130a0`
- `0x1400131f0`
- `0x140013660`
- `0x140013750`
- `0x140013ff0`
- `0x140014630`
- `0x140014d10`
- `0x140015a90`

## import_xrefs

- `ntoskrnl!IoSetHardErrorOrVerifyDevice` at `0x1400017d8`
- `ntoskrnl!IoSetHardErrorOrVerifyDevice` at `0x1400017d8`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14000181b`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14000181b`
- `CLASSPNP!ClassDeviceControl` at `0x1400015d5`
- `CLASSPNP!ClassDeviceControl` at `0x1400015d5`
- `CLASSPNP!ClassReleaseRemoveLock` at `0x14000169c`
- `CLASSPNP!ClassReleaseRemoveLock` at `0x14000169c`
- `CLASSPNP!ClassCompleteRequest` at `0x1400016b1`
- `CLASSPNP!ClassCompleteRequest` at `0x1400016b1`

## pseudocode

```c
NTSTATUS __fastcall DiskDeviceControl(PDEVICE_OBJECT DeviceObject, PIRP Irp, __int64 a3)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rbx
  _DWORD *DeviceExtension; // rsi
  unsigned int LowPart; // edi
  __int64 v8; // rax
  int v9; // ecx
  char v10; // al
  int MediaTypes; // eax
  int v13; // ecx
  NTSTATUS v14; // ebx
  __int128 v15; // [rsp+40h] [rbp-48h] BYREF

  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  DeviceExtension = DeviceObject->DeviceExtension;
  v15 = 0;
  Irp->IoStatus.Information = 0;
  LowPart = CurrentStackLocation->Parameters.Read.ByteOffset.LowPart;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_Dqq(WPP_GLOBAL_Control->AttachedDevice, 17, a3, LowPart, DeviceObject, Irp);
  }
  if ( DiskETWEnabled )
  {
    IoGetActivityIdIrp(Irp, &v15);
    if ( (BYTE1(WPP_MAIN_CB.DeviceExtension) & 4) != 0 )
      McTemplateK0qpddd_EtwWriteTransfer(
        CurrentStackLocation->MajorFunction,
        (_DWORD)Irp,
        (unsigned int)&v15,
        DeviceExtension[147],
        (char)Irp,
        CurrentStackLocation->MajorFunction,
        CurrentStackLocation->MinorFunction,
        LowPart);
  }
  if ( !DeviceExtension
    || (v8 = *((_QWORD *)DeviceExtension + 65)) == 0
    || (((v9 = *(_DWORD *)(v8 + 28), v9 == 20) || v9 == 17)
     && (LowPart == 315440
      || LowPart == 475264
      || LowPart == 315436
      || LowPart == 508040
      || LowPart == 458892
      || LowPart == 508036)
      ? (v10 = 1)
      : (v10 = 0),
        !v10) )
  {
    if ( LowPart > 0x7C01C )
    {
      if ( LowPart > 0x7C0E4 )
      {
        switch ( LowPart )
        {
          case 0x2D0C04u:
            MediaTypes = DiskIoctlGetMediaTypesEx(DeviceObject, Irp);
            break;
          case 0x2D1100u:
            MediaTypes = DiskIoctlPredictFailure(DeviceObject);
            break;
          case 0x2D1104u:
            MediaTypes = DiskIoctlEnableFailurePrediction(DeviceObject, Irp);
            break;
          case 0x560000u:
          case 0x564000u:
            MediaTypes = DiskIoctlGetVolumeDiskExtents(DeviceObject, Irp);
            break;
          default:
            return ClassDeviceControl(DeviceObject, Irp);
        }
        goto LABEL_35;
      }
      if ( LowPart == 508132 )
      {
        MediaTypes = DiskIoctlSetCacheSetting(DeviceObject, Irp);
        goto LABEL_35;
      }
      if ( LowPart == 508036 )
      {
        MediaTypes = DiskIoctlSmartSendDriveCommand(DeviceObject, Irp);
        goto LABEL_35;
      }
      if ( LowPart != 508040 )
      {
        switch ( LowPart )
        {
          case 0x7C0A4u:
            MediaTypes = DiskIoctlReassignBlocksEx(DeviceObject, Irp);
            break;
          case 0x7C0C8u:
            MediaTypes = DiskIoctlUpdateDriveSize(DeviceObject);
            break;
          case 0x7C0D8u:
            MediaTypes = DiskIoctlSetCacheInformation(DeviceObject, Irp);
            break;
          default:
            return ClassDeviceControl(DeviceObject, Irp);
        }
        goto LABEL_35;
      }
    }
    else
    {
      if ( LowPart == 507932 )
      {
        MediaTypes = DiskIoctlReassignBlocks(DeviceObject, Irp);
        goto LABEL_35;
      }
      if ( LowPart > 0x70403 )
      {
        switch ( LowPart )
        {
          case 0x70407u:
            MediaTypes = DiskIoctlClearVerify(DeviceObject, Irp);
            break;
          case 0x7405Cu:
            MediaTypes = DiskIoctlGetLengthInfo(DeviceObject, Irp);
            break;
          case 0x74080u:
            MediaTypes = DiskIoctlSmartGetVersion(DeviceObject, Irp);
            break;
          case 0x740D4u:
            MediaTypes = DiskIoctlGetCacheInformation(DeviceObject, Irp);
            break;
          case 0x740E0u:
            MediaTypes = DiskIoctlGetCacheSetting(DeviceObject, Irp);
            break;
          default:
            return ClassDeviceControl(DeviceObject, Irp);
        }
        goto LABEL_35;
      }
      switch ( LowPart )
      {
        case 0x70403u:
          MediaTypes = DiskIoctlSetVerify(DeviceObject, Irp);
          goto LABEL_35;
        case 0x70000u:
          MediaTypes = DiskIoctlGetDriveGeometry(DeviceObject, Irp);
          goto LABEL_35;
        case 0x70014u:
          MediaTypes = DiskIoctlVerify(DeviceObject);
          goto LABEL_35;
        case 0x70024u:
          MediaTypes = DiskIoctlIsWritable(DeviceObject);
          goto LABEL_35;
      }
      if ( LowPart != 458892 )
      {
        if ( LowPart != 458912 )
          return ClassDeviceControl(DeviceObject, Irp);
        MediaTypes = DiskIoctlGetDriveGeometryEx(DeviceObject, Irp);
LABEL_35:
        v14 = MediaTypes;
        if ( MediaTypes >= 0 )
          goto LABEL_36;
        goto LABEL_60;
      }
    }
    MediaTypes = DiskIoctlSmartReceiveDriveData(DeviceObject, Irp);
    goto LABEL_35;
  }
  v14 = -1073741637;
  v13 = (int)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
LABEL_39:
    if ( DiskETWEnabled )
    {
      if ( (BYTE1(WPP_MAIN_CB.DeviceExtension) & 0x10) != 0 )
        McTemplateK0qpd_EtwWriteTransfer(v13, (_DWORD)Irp, (unsigned int)&v15, DeviceExtension[147], (char)Irp, v14);
    }
    Irp->IoStatus.Status = v14;
    ClassReleaseRemoveLock(DeviceObject, Irp);
    ClassCompleteRequest(DeviceObject, Irp, 0);
    return v14;
  }
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    WPP_SF_Dqq(WPP_GLOBAL_Control->AttachedDevice, 18, a3, LowPart, DeviceObject, Irp);
LABEL_60:
  v13 = (int)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_DqD(WPP_GLOBAL_Control->AttachedDevice, Irp, a3, LowPart, DeviceObject, v14);
  }
  if ( ((unsigned int)(v14 + 1073741662) <= 1
     || (unsigned int)(v14 + 1073741806) <= 2
     || v14 == -2147483626
     || v14 == -1073741643)
    && Irp->Tail.Overlay.Thread )
  {
    IoSetHardErrorOrVerifyDevice(Irp, DeviceObject);
  }
LABEL_36:
  if ( v14 != 259 )
    goto LABEL_39;
  return v14;
}

```

## disassembly

```asm
0x1400014a0  mov     [rsp+arg_10], rbx
0x1400014a5  push    rbp
0x1400014a6  push    rsi
0x1400014a7  push    rdi
0x1400014a8  push    r14
0x1400014aa  push    r15
0x1400014ac  sub     rsp, 60h
0x1400014b0  mov     rax, cs:__security_cookie
0x1400014b7  xor     rax, rsp
0x1400014ba  mov     [rsp+88h+var_38], rax
0x1400014bf  mov     rbx, [rdx+0B8h]
0x1400014c6  xorps   xmm0, xmm0
0x1400014c9  mov     rsi, [rcx+40h]
0x1400014cd  mov     rbp, rdx
0x1400014d0  movups  [rsp+88h+var_48], xmm0
0x1400014d5  mov     qword ptr [rdx+38h], 0
0x1400014dd  mov     r14, rcx
0x1400014e0  mov     edi, [rbx+18h]
0x1400014e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400014ea  lea     r15, WPP_GLOBAL_Control
0x1400014f1  cmp     rcx, r15
0x1400014f4  jz      short loc_140001501
0x1400014f6  mov     eax, [rcx+2Ch]
0x1400014f9  test    al, 10h
0x1400014fb  jnz     loc_1400017E9
0x140001501  cmp     cs:DiskETWEnabled, 0
0x140001508  jnz     loc_140001813
0x14000150e  test    rsi, rsi
0x140001511  jz      short loc_14000157E
0x140001513  mov     rax, [rsi+208h]
0x14000151a  test    rax, rax
0x14000151d  jz      short loc_14000157E
0x14000151f  mov     ecx, [rax+1Ch]
0x140001522  cmp     ecx, 14h
0x140001525  jz      short loc_14000152C
0x140001527  cmp     ecx, 11h
0x14000152a  jnz     short loc_140001574
0x14000152c  cmp     edi, 4D030h
0x140001532  jz      loc_14000164B
0x140001538  cmp     edi, 74080h
0x14000153e  jz      loc_14000164B
0x140001544  cmp     edi, 4D02Ch
0x14000154a  jz      loc_14000164B
0x140001550  cmp     edi, 7C088h
0x140001556  jz      loc_14000164B
0x14000155c  cmp     edi, 7008Ch
0x140001562  jz      loc_14000164B
0x140001568  cmp     edi, 7C084h
0x14000156e  jz      loc_14000164B
0x140001574  xor     al, al
0x140001576  test    al, al
0x140001578  jnz     loc_140001671
0x14000157e  cmp     edi, 7C01Ch
0x140001584  ja      short loc_140001603
0x140001586  jz      loc_1400018CC
0x14000158c  cmp     edi, 70403h
0x140001592  ja      loc_1400016C4
0x140001598  jz      loc_1400018AC
0x14000159e  mov     eax, edi
0x1400015a0  sub     eax, 70000h
0x1400015a5  jz      loc_140001652
0x1400015ab  sub     eax, 14h
0x1400015ae  jz      loc_14000189C
0x1400015b4  sub     eax, 10h
0x1400015b7  jz      loc_1400016E8
0x1400015bd  sub     eax, 68h ; 'h'
0x1400015c0  jz      loc_14000173A
0x1400015c6  cmp     eax, 14h
0x1400015c9  jz      loc_14000188C
0x1400015cf  mov     rdx, rbp; Irp
0x1400015d2  mov     rcx, r14; DeviceObject
0x1400015d5  call    cs:__imp_ClassDeviceControl
0x1400015dc  nop     dword ptr [rax+rax+00h]
0x1400015e1  mov     rcx, [rsp+88h+var_38]
0x1400015e6  xor     rcx, rsp; StackCookie
0x1400015e9  call    __security_check_cookie
0x1400015ee  mov     rbx, [rsp+88h+arg_10]
0x1400015f6  add     rsp, 60h
0x1400015fa  pop     r15
0x1400015fc  pop     r14
0x1400015fe  pop     rdi
0x1400015ff  pop     rsi
0x140001600  pop     rbp
0x140001601  retn
0x140001603  cmp     edi, 7C0E4h
0x140001609  jbe     loc_140001722
0x14000160f  mov     eax, edi
0x140001611  sub     eax, 2D0C04h
0x140001616  jz      loc_140001773
0x14000161c  sub     eax, 4FCh
0x140001621  jz      loc_140001712
0x140001627  sub     eax, 4
0x14000162a  jz      loc_14000192F
0x140001630  sub     eax, 28EEFCh
0x140001635  jz      short loc_14000163E
0x140001637  cmp     eax, 4000h
0x14000163c  jnz     short loc_1400015CF
0x14000163e  mov     rdx, rbp
0x140001641  mov     rcx, r14
0x140001644  call    DiskIoctlGetVolumeDiskExtents
0x140001649  jmp     short loc_14000165D
0x14000164b  mov     al, 1
0x14000164d  jmp     loc_140001576
0x140001652  mov     rdx, rbp
0x140001655  mov     rcx, r14
0x140001658  call    DiskIoctlGetDriveGeometry
0x14000165d  mov     ebx, eax
0x14000165f  test    eax, eax
0x140001661  js      loc_14000179E
0x140001667  cmp     ebx, 103h
0x14000166d  jz      short loc_1400016BD
0x14000166f  jmp     short loc_140001686
0x140001671  mov     ebx, 0C00000BBh
0x140001676  mov     rcx, cs:WPP_GLOBAL_Control
0x14000167d  cmp     rcx, r15
0x140001680  jnz     loc_140001793
0x140001686  cmp     cs:DiskETWEnabled, 0
0x14000168d  jnz     loc_14000198F
0x140001693  mov     rdx, rbp; Tag
0x140001696  mov     [rbp+30h], ebx
0x140001699  mov     rcx, r14; DeviceObject
0x14000169c  call    cs:__imp_ClassReleaseRemoveLock
0x1400016a3  nop     dword ptr [rax+rax+00h]
0x1400016a8  xor     r8d, r8d; PriorityBoost
0x1400016ab  mov     rdx, rbp; Irp
0x1400016ae  mov     rcx, r14; DeviceObject
0x1400016b1  call    cs:__imp_ClassCompleteRequest
0x1400016b8  nop     dword ptr [rax+rax+00h]
0x1400016bd  mov     eax, ebx
0x1400016bf  jmp     loc_1400015E1
0x1400016c4  mov     eax, edi
0x1400016c6  sub     eax, 70407h
0x1400016cb  jz      loc_1400018BC
0x1400016d1  sub     eax, 3C55h
0x1400016d6  jnz     short loc_1400016F8
0x1400016d8  mov     rdx, rbp
0x1400016db  mov     rcx, r14
0x1400016de  call    DiskIoctlGetLengthInfo
0x1400016e3  jmp     loc_14000165D
0x1400016e8  mov     rdx, rbp
0x1400016eb  mov     rcx, r14; DeviceObject
0x1400016ee  call    DiskIoctlIsWritable
0x1400016f3  jmp     loc_14000165D
0x1400016f8  sub     eax, 24h ; '$'
0x1400016fb  jz      short loc_140001763
0x1400016fd  sub     eax, 54h ; 'T'
0x140001700  jnz     short loc_14000174A
0x140001702  mov     rdx, rbp
0x140001705  mov     rcx, r14
0x140001708  call    DiskIoctlGetCacheInformation
0x14000170d  jmp     loc_14000165D
0x140001712  mov     rdx, rbp
0x140001715  mov     rcx, r14; DeviceObject
0x140001718  call    DiskIoctlPredictFailure
0x14000171d  jmp     loc_14000165D
0x140001722  jz      loc_14000191F
0x140001728  mov     eax, edi
0x14000172a  sub     eax, 7C084h
0x14000172f  jz      short loc_140001783
0x140001731  sub     eax, 4
0x140001734  jnz     loc_1400018DC
0x14000173a  mov     rdx, rbp
0x14000173d  mov     rcx, r14
0x140001740  call    DiskIoctlSmartReceiveDriveData
0x140001745  jmp     loc_14000165D
0x14000174a  cmp     eax, 0Ch
0x14000174d  jnz     loc_1400015CF
0x140001753  mov     rdx, rbp
0x140001756  mov     rcx, r14
0x140001759  call    DiskIoctlGetCacheSetting
0x14000175e  jmp     loc_14000165D
0x140001763  mov     rdx, rbp
0x140001766  mov     rcx, r14
0x140001769  call    DiskIoctlSmartGetVersion
0x14000176e  jmp     loc_14000165D
0x140001773  mov     rdx, rbp; Irp
0x140001776  mov     rcx, r14; DeviceObject
0x140001779  call    DiskIoctlGetMediaTypesEx
0x14000177e  jmp     loc_14000165D
0x140001783  mov     rdx, rbp
0x140001786  mov     rcx, r14
0x140001789  call    DiskIoctlSmartSendDriveCommand
0x14000178e  jmp     loc_14000165D
0x140001793  mov     eax, [rcx+2Ch]
0x140001796  test    al, 10h
0x140001798  jnz     loc_140001862
0x14000179e  mov     rcx, cs:WPP_GLOBAL_Control
0x1400017a5  cmp     rcx, r15
0x1400017a8  jz      short loc_1400017B5
0x1400017aa  mov     eax, [rcx+2Ch]
0x1400017ad  test    al, 10h
0x1400017af  jnz     loc_14000193F
0x1400017b5  lea     eax, [rbx+3FFFFF5Eh]
0x1400017bb  cmp     eax, 1
0x1400017be  ja      loc_140001963
0x1400017c4  cmp     qword ptr [rbp+98h], 0
0x1400017cc  jz      loc_140001667
0x1400017d2  mov     rdx, r14; DeviceObject
0x1400017d5  mov     rcx, rbp; Irp
0x1400017d8  call    cs:__imp_IoSetHardErrorOrVerifyDevice
0x1400017df  nop     dword ptr [rax+rax+00h]
0x1400017e4  jmp     loc_140001667
0x1400017e9  cmp     byte ptr [rcx+29h], 5
0x1400017ed  jb      loc_140001501
0x1400017f3  mov     rcx, [rcx+18h]
0x1400017f7  mov     edx, 11h
0x1400017fc  mov     [rsp+88h+var_60], rbp
0x140001801  mov     r9d, edi
0x140001804  mov     [rsp+88h+var_68], r14
0x140001809  call    WPP_SF_Dqq
0x14000180e  jmp     loc_140001501
0x140001813  lea     rdx, [rsp+88h+var_48]
0x140001818  mov     rcx, rbp
0x14000181b  call    cs:__imp_IoGetActivityIdIrp
0x140001822  nop     dword ptr [rax+rax+00h]
0x140001827  test    byte ptr cs:WPP_MAIN_CB.DeviceExtension+1, 4
0x14000182e  jz      loc_14000150E
0x140001834  movzx   eax, byte ptr [rbx+1]
0x140001838  lea     r8, [rsp+88h+var_48]
0x14000183d  movzx   ecx, byte ptr [rbx]
0x140001840  mov     r9d, [rsi+24Ch]
0x140001847  mov     [rsp+88h+var_50], edi
0x14000184b  mov     [rsp+88h+var_58], eax
0x14000184f  mov     dword ptr [rsp+88h+var_60], ecx
0x140001853  mov     [rsp+88h+var_68], rbp
0x140001858  call    McTemplateK0qpddd_EtwWriteTransfer
0x14000185d  jmp     loc_14000150E
0x140001862  cmp     byte ptr [rcx+29h], 5
0x140001866  jb      loc_14000179E
0x14000186c  mov     rcx, [rcx+18h]
0x140001870  mov     edx, 12h
0x140001875  mov     [rsp+88h+var_60], rbp
0x14000187a  mov     r9d, edi
0x14000187d  mov     [rsp+88h+var_68], r14
0x140001882  call    WPP_SF_Dqq
0x140001887  jmp     loc_14000179E
0x14000188c  mov     rdx, rbp
0x14000188f  mov     rcx, r14
0x140001892  call    DiskIoctlGetDriveGeometryEx
0x140001897  jmp     loc_14000165D
0x14000189c  mov     rdx, rbp
0x14000189f  mov     rcx, r14; DeviceObject
0x1400018a2  call    DiskIoctlVerify
0x1400018a7  jmp     loc_14000165D
0x1400018ac  mov     rdx, rbp
0x1400018af  mov     rcx, r14
0x1400018b2  call    DiskIoctlSetVerify
0x1400018b7  jmp     loc_14000165D
0x1400018bc  mov     rdx, rbp
0x1400018bf  mov     rcx, r14
0x1400018c2  call    DiskIoctlClearVerify
0x1400018c7  jmp     loc_14000165D
0x1400018cc  mov     rdx, rbp; Irp
0x1400018cf  mov     rcx, r14; DeviceObject
0x1400018d2  call    DiskIoctlReassignBlocks
0x1400018d7  jmp     loc_14000165D
0x1400018dc  sub     eax, 1Ch
0x1400018df  jz      short loc_14000190F
0x1400018e1  sub     eax, 24h ; '$'
0x1400018e4  jz      short loc_1400018FF
0x1400018e6  cmp     eax, 10h
0x1400018e9  jnz     loc_1400015CF
0x1400018ef  mov     rdx, rbp
0x1400018f2  mov     rcx, r14
0x1400018f5  call    DiskIoctlSetCacheInformation
0x1400018fa  jmp     loc_14000165D
0x1400018ff  mov     rdx, rbp
0x140001902  mov     rcx, r14; DeviceObject
0x140001905  call    DiskIoctlUpdateDriveSize
0x14000190a  jmp     loc_14000165D
0x14000190f  mov     rdx, rbp; Irp
0x140001912  mov     rcx, r14; DeviceObject
0x140001915  call    DiskIoctlReassignBlocksEx
0x14000191a  jmp     loc_14000165D
0x14000191f  mov     rdx, rbp
0x140001922  mov     rcx, r14
0x140001925  call    DiskIoctlSetCacheSetting
0x14000192a  jmp     loc_14000165D
0x14000192f  mov     rdx, rbp
0x140001932  mov     rcx, r14
0x140001935  call    DiskIoctlEnableFailurePrediction
0x14000193a  jmp     loc_14000165D
0x14000193f  cmp     byte ptr [rcx+29h], 2
0x140001943  jb      loc_1400017B5
0x140001949  mov     rcx, [rcx+18h]
0x14000194d  mov     r9d, edi
0x140001950  mov     dword ptr [rsp+88h+var_60], ebx
0x140001954  mov     [rsp+88h+var_68], r14
0x140001959  call    WPP_SF_DqD
0x14000195e  jmp     loc_1400017B5
0x140001963  lea     eax, [rbx+3FFFFFEEh]
0x140001969  cmp     eax, 2
0x14000196c  jbe     loc_1400017C4
0x140001972  cmp     ebx, 80000016h
0x140001978  jz      loc_1400017C4
0x14000197e  cmp     ebx, 0C00000B5h
0x140001984  jnz     loc_140001667
0x14000198a  jmp     loc_1400017C4
0x14000198f  test    byte ptr cs:WPP_MAIN_CB.DeviceExtension+1, 10h
0x140001996  jz      loc_140001693
  ... truncated ...
```
