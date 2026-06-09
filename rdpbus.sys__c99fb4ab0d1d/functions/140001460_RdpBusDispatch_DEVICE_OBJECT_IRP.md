# RdpBusDispatch(_DEVICE_OBJECT *,_IRP *)

- ea: `0x140001460`
- end: `0x140001bbb`
- name: `?RdpBusDispatch@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z`
- size: `1883`
- prototype: `NTSTATUS __fastcall(PDEVICE_OBJECT DeviceObject, PIRP Irp)`
- caller_count: `0`
- callee_count: `7`
- tags: `reparse_path, loader_planting, installer_update, broker_com_uri`

## callees

- `0x140001040`
- `0x140001460`
- `0x140001be0`
- `0x1400020b4`
- `0x1400020e4`
- `0x140002128`
- `0x14000890c`

## import_xrefs

- `ntoskrnl!IoRegisterDeviceInterface` at `0x140001662`
- `ntoskrnl!IoRegisterDeviceInterface` at `0x140001662`
- `ntoskrnl!IoDetachDevice` at `0x1400018ab`
- `ntoskrnl!IoDetachDevice` at `0x1400018ab`
- `ntoskrnl!PoCallDriver` at `0x140001737`
- `ntoskrnl!PoCallDriver` at `0x140001737`
- `ntoskrnl!RtlInitUnicodeString` at `0x140001640`
- `ntoskrnl!RtlInitUnicodeString` at `0x140001640`
- `ntoskrnl!IoDeleteDevice` at `0x1400018ba`
- `ntoskrnl!IoDeleteDevice` at `0x1400018ba`
- `ntoskrnl!IofCallDriver` at `0x14000180a`
- `ntoskrnl!IofCallDriver` at `0x14000189a`
- `ntoskrnl!IofCallDriver` at `0x140001b90`
- `ntoskrnl!IofCallDriver` at `0x14000180a`
- `ntoskrnl!IofCallDriver` at `0x14000189a`
- `ntoskrnl!IofCallDriver` at `0x140001b90`
- `ntoskrnl!KeInitializeEvent` at `0x1400017ad`
- `ntoskrnl!KeInitializeEvent` at `0x1400017ad`
- `ntoskrnl!IofCompleteRequest` at `0x1400015a2`
- `ntoskrnl!IofCompleteRequest` at `0x1400015c0`
- `ntoskrnl!IofCompleteRequest` at `0x1400015df`
- `ntoskrnl!IofCompleteRequest` at `0x140001685`
- `ntoskrnl!IofCompleteRequest` at `0x1400016a4`
- `ntoskrnl!IofCompleteRequest` at `0x14000184d`
- `ntoskrnl!IofCompleteRequest` at `0x140001aa7`
- `ntoskrnl!IofCompleteRequest` at `0x1400015a2`
- `ntoskrnl!IofCompleteRequest` at `0x1400015c0`
- `ntoskrnl!IofCompleteRequest` at `0x1400015df`
- `ntoskrnl!IofCompleteRequest` at `0x140001685`
- `ntoskrnl!IofCompleteRequest` at `0x1400016a4`
- `ntoskrnl!IofCompleteRequest` at `0x14000184d`
- `ntoskrnl!IofCompleteRequest` at `0x140001aa7`
- `ntoskrnl!KeWaitForSingleObject` at `0x140001836`
- `ntoskrnl!KeWaitForSingleObject` at `0x140001836`
- `ntoskrnl!PoStartNextPowerIrp` at `0x14000171a`
- `ntoskrnl!PoStartNextPowerIrp` at `0x14000171a`

## pseudocode

```c
NTSTATUS __fastcall RdpBusDispatch(PDEVICE_OBJECT DeviceObject, PIRP Irp)
{
  __int64 v2; // rbx
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rsi
  struct _DEVICE_OBJECT **DeviceExtension; // rax
  struct _DEVICE_OBJECT *v8; // r14
  NTSTATUS v9; // eax
  int v10; // eax
  __int64 v11; // r8
  struct _IO_STACK_LOCATION *v12; // rax
  struct _IRP *MasterIrp; // r14
  const WCHAR *MdlAddress; // rdx
  struct _UNICODE_STRING *v15; // rbx
  NTSTATUS v16; // esi
  struct _IO_STACK_LOCATION *v17; // rax
  struct _IO_STACK_LOCATION *v18; // rax
  NTSTATUS Status; // ebx
  PDEVICE_OBJECT v20; // rcx
  __int64 v21; // rdx
  NTSTATUS v22; // ebx
  PDEVICE_OBJECT v23; // rcx
  __int64 v24; // rdx
  ULONG Length; // ecx
  ULONG v26; // ecx
  ULONG v27; // ecx
  ULONG v28; // ecx
  PDEVICE_OBJECT v29; // rcx
  __int64 v30; // rdx
  struct _KEVENT DestinationString[2]; // [rsp+30h] [rbp-38h] BYREF
  unsigned __int8 v32; // [rsp+70h] [rbp+8h] BYREF
  __int64 v33; // [rsp+78h] [rbp+10h]

  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_D(
      WPP_GLOBAL_Control->AttachedDevice,
      22,
      WPP_aa2742c9424e303f9b5b727f51c5aafc_Traceguids,
      CurrentStackLocation->MajorFunction);
  DeviceExtension = (struct _DEVICE_OBJECT **)DeviceObject->DeviceExtension;
  if ( !DeviceExtension )
  {
    Irp->IoStatus.Status = -1073741823;
    return -1073741823;
  }
  v33 = v2;
  v8 = *DeviceExtension;
  switch ( CurrentStackLocation->MajorFunction )
  {
    case 0u:
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 23, WPP_aa2742c9424e303f9b5b727f51c5aafc_Traceguids);
      if ( CurrentStackLocation->FileObject->FileName.Buffer )
      {
        v32 = 0;
        v10 = IsCallerAllowedAccess(Irp, CurrentStackLocation, &v32);
        if ( v10 >= 0 && v32 )
        {
          v9 = RDPBUS_PrepareForReparse(CurrentStackLocation->FileObject);
        }
        else
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
            WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, v32, v11, (unsigned int)v10, v32);
          v9 = -1073741790;
        }
      }
      else
      {
        v9 = 0;
      }
      Irp->IoStatus.Status = v9;
      Irp->IoStatus.Information = 0;
      IofCompleteRequest(Irp, 0);
      return Irp->IoStatus.Status;
    case 2u:
    case 0x12u:
      Irp->IoStatus.Status = 0;
      IofCompleteRequest(Irp, 0);
      return 0;
    case 3u:
    case 4u:
      Irp->IoStatus.Status = -1073741637;
      IofCompleteRequest(Irp, 0);
      return -1073741637;
    case 0xEu:
      if ( !Irp->RequestorMode
        && (v12 = Irp->Tail.Overlay.CurrentStackLocation, v12->Parameters.Read.ByteOffset.LowPart == 2230276)
        && v12->Parameters.Create.Options <= 0x18
        && (MasterIrp = Irp->AssociatedIrp.MasterIrp) != 0 )
      {
        if ( RDPDYN_PDO )
        {
          MdlAddress = (const WCHAR *)MasterIrp->MdlAddress;
          v15 = *(struct _UNICODE_STRING **)&MasterIrp->Type;
          *(_OWORD *)&DestinationString[0].Header.Lock = 0;
          RtlInitUnicodeString((PUNICODE_STRING)DestinationString, MdlAddress);
          v16 = IoRegisterDeviceInterface(RDPDYN_PDO, &InterfaceClassGuid, (PUNICODE_STRING)DestinationString, v15);
        }
        else
        {
          v16 = -1073741823;
        }
        MasterIrp->Flags = v16;
        Irp->IoStatus.Status = 0;
        IofCompleteRequest(Irp, 0);
        return 0;
      }
      else
      {
        Irp->IoStatus.Status = -1073741585;
        IofCompleteRequest(Irp, 0);
        return -1073741585;
      }
    case 0x16u:
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 25, WPP_aa2742c9424e303f9b5b727f51c5aafc_Traceguids);
      if ( CurrentStackLocation->MinorFunction == 2 )
      {
        Irp->IoStatus.Status = 0;
      }
      else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 26, WPP_aa2742c9424e303f9b5b727f51c5aafc_Traceguids);
      }
      PoStartNextPowerIrp(Irp);
      ++Irp->CurrentLocation;
      ++Irp->Tail.Overlay.CurrentStackLocation;
      return PoCallDriver(v8, Irp);
    case 0x1Bu:
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 27, WPP_aa2742c9424e303f9b5b727f51c5aafc_Traceguids);
      break;
    default:
      goto LABEL_113;
  }
  switch ( CurrentStackLocation->MinorFunction )
  {
    case 0u:
      memset(DestinationString, 0, 24);
      CleanUpExistingPorts();
      KeInitializeEvent(DestinationString, NotificationEvent, 0);
      v17 = Irp->Tail.Overlay.CurrentStackLocation;
      *(_OWORD *)&v17[-1].MajorFunction = *(_OWORD *)&v17->MajorFunction;
      *(_OWORD *)&v17[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&v17->Parameters.NotifyDirectoryEx.CompletionFilter;
      *(_OWORD *)(&v17[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&v17->Parameters.SetQuota + 6);
      v17[-1].FileObject = v17->FileObject;
      v17[-1].Control = 0;
      v18 = Irp->Tail.Overlay.CurrentStackLocation;
      v18[-1].CompletionRoutine = RdpBusDeferIrpCompletion;
      v18[-1].Context = DestinationString;
      v18[-1].Control = -32;
      Status = IofCallDriver(v8, Irp);
      if ( Status == 259 )
      {
        KeWaitForSingleObject(DestinationString, Suspended, 0, 0, 0);
        Status = Irp->IoStatus.Status;
      }
      Irp->IoStatus.Status = Status;
      IofCompleteRequest(Irp, 0);
      return Status;
    case 1u:
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 39, WPP_aa2742c9424e303f9b5b727f51c5aafc_Traceguids);
      Irp->IoStatus.Information = 0;
      goto LABEL_92;
    case 2u:
      ++Irp->CurrentLocation;
      ++Irp->Tail.Overlay.CurrentStackLocation;
      Irp->IoStatus.Status = 0;
      v22 = IofCallDriver(v8, Irp);
      IoDetachDevice(v8);
      IoDeleteDevice(DeviceObject);
      return v22;
    case 3u:
      v29 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
        goto LABEL_97;
      v30 = 41;
      goto LABEL_96;
    case 4u:
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
        goto LABEL_92;
      v21 = 28;
      goto LABEL_87;
    case 5u:
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
        goto LABEL_92;
      v21 = 38;
LABEL_87:
      WPP_SF_(v20->AttachedDevice, v21, WPP_aa2742c9424e303f9b5b727f51c5aafc_Traceguids);
LABEL_92:
      Irp->IoStatus.Status = -1073741823;
      IofCompleteRequest(Irp, 0);
      return -1073741823;
    case 6u:
      v29 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
        goto LABEL_97;
      v30 = 40;
      goto LABEL_96;
    case 7u:
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 31, WPP_aa2742c9424e303f9b5b727f51c5aafc_Traceguids);
      Length = CurrentStackLocation->Parameters.Read.Length;
      if ( !Length )
      {
        v23 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          v24 = 33;
          goto LABEL_54;
        }
        goto LABEL_113;
      }
      v26 = Length - 1;
      if ( !v26 )
      {
        v23 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          v24 = 32;
          goto LABEL_54;
        }
        goto LABEL_113;
      }
      v27 = v26 - 1;
      if ( !v27 )
      {
        v29 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
          goto LABEL_97;
        v30 = 34;
        goto LABEL_96;
      }
      v28 = v27 - 1;
      if ( !v28 )
      {
        v29 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
          goto LABEL_97;
        v30 = 35;
LABEL_96:
        WPP_SF_(v29->AttachedDevice, v30, WPP_aa2742c9424e303f9b5b727f51c5aafc_Traceguids);
LABEL_97:
        Irp->IoStatus.Status = 0;
        goto LABEL_113;
      }
      if ( v28 == 1 )
      {
        v23 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          v24 = 36;
          goto LABEL_54;
        }
      }
      else
      {
        v23 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          v24 = 37;
LABEL_54:
          WPP_SF_(v23->AttachedDevice, v24, WPP_aa2742c9424e303f9b5b727f51c5aafc_Traceguids);
        }
      }
LABEL_113:
      ++Irp->CurrentLocation;
      ++Irp->Tail.Overlay.CurrentStackLocation;
      return IofCallDriver(v8, Irp);
    case 9u:
      v23 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
        goto LABEL_113;
      v24 = 29;
      goto LABEL_54;
    case 0xDu:
      v23 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
        goto LABEL_113;
      v24 = 42;
      goto LABEL_54;
    case 0x13u:
      v23 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
        goto LABEL_113;
      v24 = 30;
      goto LABEL_54;
    case 0x14u:
      v23 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
        goto LABEL_113;
      v24 = 43;
      goto LABEL_54;
    case 0x15u:
      v23 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
        goto LABEL_113;
      v24 = 44;
      goto LABEL_54;
    default:
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
        WPP_SF_D(
          WPP_GLOBAL_Control->AttachedDevice,
          45,
          WPP_aa2742c9424e303f9b5b727f51c5aafc_Traceguids,
          CurrentStackLocation->MinorFunction);
      goto LABEL_113;
  }
}

```

## disassembly

```asm
0x140001460  mov     [rsp+arg_18], rbp
0x140001465  push    rsi
0x140001466  push    rdi
0x140001467  push    r15
0x140001469  sub     rsp, 50h
0x14000146d  mov     rsi, [rdx+0B8h]
0x140001474  mov     rdi, rdx
0x140001477  mov     rbp, rcx
0x14000147a  mov     rcx, cs:WPP_GLOBAL_Control
0x140001481  lea     r15, WPP_GLOBAL_Control
0x140001488  cmp     rcx, r15
0x14000148b  jz      short loc_1400014AC
0x14000148d  cmp     byte ptr [rcx+29h], 4
0x140001491  jb      short loc_1400014AC
0x140001493  movzx   r9d, byte ptr [rsi]
0x140001497  lea     r8, WPP_aa2742c9424e303f9b5b727f51c5aafc_Traceguids
0x14000149e  mov     rcx, [rcx+18h]
0x1400014a2  mov     edx, 16h
0x1400014a7  call    WPP_SF_D
0x1400014ac  mov     rax, [rbp+40h]
0x1400014b0  test    rax, rax
0x1400014b3  jnz     short loc_1400014D1
0x1400014b5  mov     esi, 0C0000001h
0x1400014ba  mov     [rdi+30h], esi
0x1400014bd  mov     eax, esi
0x1400014bf  mov     rbp, [rsp+68h+arg_18]
0x1400014c7  add     rsp, 50h
0x1400014cb  pop     r15
0x1400014cd  pop     rdi
0x1400014ce  pop     rsi
0x1400014cf  retn
0x1400014d1  mov     [rsp+68h+arg_8], rbx
0x1400014d6  mov     [rsp+68h+arg_10], r14
0x1400014de  mov     r14, [rax]
0x1400014e1  movzx   eax, byte ptr [rsi]
0x1400014e4  cmp     eax, 1Bh; switch 28 cases
0x1400014e7  ja      def_140001506; jumptable 0000000140001506 default case, cases 1,5-13,15-17,19-21,23-26
0x1400014ed  lea     rbx, cs:140000000h
0x1400014f4  movzx   eax, ds:(byte_1400046F4 - 140000000h)[rbx+rax]
0x1400014fc  mov     ecx, ds:(jpt_140001506 - 140000000h)[rbx+rax*4]
0x140001503  add     rcx, rbx
0x140001506  jmp     rcx; switch jump
0x14000150c  mov     rcx, cs:WPP_GLOBAL_Control; jumptable 0000000140001506 case 0
0x140001513  cmp     rcx, r15
0x140001516  jz      short loc_140001533
0x140001518  cmp     byte ptr [rcx+29h], 4
0x14000151c  jb      short loc_140001533
0x14000151e  mov     rcx, [rcx+18h]
0x140001522  lea     r8, WPP_aa2742c9424e303f9b5b727f51c5aafc_Traceguids
0x140001529  mov     edx, 17h
0x14000152e  call    WPP_SF_
0x140001533  mov     rax, [rsi+30h]
0x140001537  xor     ebx, ebx
0x140001539  cmp     [rax+60h], rbx
0x14000153d  jnz     short loc_140001543
0x14000153f  mov     eax, ebx
0x140001541  jmp     short loc_140001596
0x140001543  lea     r8, [rsp+68h+arg_0]
0x140001548  mov     [rsp+68h+arg_0], bl
0x14000154c  mov     rdx, rsi
0x14000154f  mov     rcx, rdi
0x140001552  call    IsCallerAllowedAccess
0x140001557  movzx   edx, [rsp+68h+arg_0]
0x14000155c  mov     r9d, eax
0x14000155f  test    eax, eax
0x140001561  js      short loc_140001572
0x140001563  test    dl, dl
0x140001565  jz      short loc_140001572
0x140001567  mov     rcx, [rsi+30h]; struct _FILE_OBJECT *
0x14000156b  call    ?RDPBUS_PrepareForReparse@@YAJPEAU_FILE_OBJECT@@@Z; RDPBUS_PrepareForReparse(_FILE_OBJECT *)
0x140001570  jmp     short loc_140001596
0x140001572  mov     rcx, cs:WPP_GLOBAL_Control
0x140001579  cmp     rcx, r15
0x14000157c  jz      short loc_140001591
0x14000157e  cmp     byte ptr [rcx+29h], 4
0x140001582  jb      short loc_140001591
0x140001584  mov     rcx, [rcx+18h]
0x140001588  mov     dword ptr [rsp+68h+Timeout], edx
0x14000158c  call    WPP_SF_Dd
0x140001591  mov     eax, 0C0000022h
0x140001596  mov     [rdi+30h], eax
0x140001599  xor     edx, edx; PriorityBoost
0x14000159b  mov     rcx, rdi; Irp
0x14000159e  mov     [rdi+38h], rbx
0x1400015a2  call    cs:__imp_IofCompleteRequest
0x1400015a9  nop     dword ptr [rax+rax+00h]
0x1400015ae  mov     eax, [rdi+30h]
0x1400015b1  jmp     loc_140001B9C
0x1400015b6  xor     ebx, ebx; jumptable 0000000140001506 cases 2,18
0x1400015b8  xor     edx, edx; PriorityBoost
0x1400015ba  mov     rcx, rdi; Irp
0x1400015bd  mov     [rdi+30h], ebx
0x1400015c0  call    cs:__imp_IofCompleteRequest
0x1400015c7  nop     dword ptr [rax+rax+00h]
0x1400015cc  xor     eax, eax
0x1400015ce  jmp     loc_140001B9C
0x1400015d3  xor     edx, edx; jumptable 0000000140001506 cases 3,4
0x1400015d5  mov     dword ptr [rdi+30h], 0C00000BBh
0x1400015dc  mov     rcx, rdi; Irp
0x1400015df  call    cs:__imp_IofCompleteRequest
0x1400015e6  nop     dword ptr [rax+rax+00h]
0x1400015eb  mov     eax, 0C00000BBh
0x1400015f0  jmp     loc_140001B9C
0x1400015f5  cmp     byte ptr [rdi+40h], 0; jumptable 0000000140001506 case 14
0x1400015f9  jnz     loc_140001698
0x1400015ff  mov     rax, [rdi+0B8h]
0x140001606  cmp     dword ptr [rax+18h], 220804h
0x14000160d  jnz     loc_140001698
0x140001613  cmp     dword ptr [rax+10h], 18h
0x140001617  ja      short loc_140001698
0x140001619  mov     r14, [rdi+18h]
0x14000161d  test    r14, r14
0x140001620  jz      short loc_140001698
0x140001622  cmp     cs:?RDPDYN_PDO@@3PEAU_DEVICE_OBJECT@@EA, 0; _DEVICE_OBJECT * RDPDYN_PDO
0x14000162a  jz      short loc_140001672
0x14000162c  mov     rdx, [r14+8]; SourceString
0x140001630  lea     rcx, [rsp+68h+DestinationString]; DestinationString
0x140001635  mov     rbx, [r14]
0x140001638  xorps   xmm0, xmm0
0x14000163b  movups  xmmword ptr [rsp+68h+DestinationString.Length], xmm0
0x140001640  call    cs:__imp_RtlInitUnicodeString
0x140001647  nop     dword ptr [rax+rax+00h]
0x14000164c  mov     rcx, cs:?RDPDYN_PDO@@3PEAU_DEVICE_OBJECT@@EA; PhysicalDeviceObject
0x140001653  lea     r8, [rsp+68h+DestinationString]; ReferenceString
0x140001658  mov     r9, rbx; SymbolicLinkName
0x14000165b  lea     rdx, InterfaceClassGuid; InterfaceClassGuid
0x140001662  call    cs:__imp_IoRegisterDeviceInterface
0x140001669  nop     dword ptr [rax+rax+00h]
0x14000166e  mov     esi, eax
0x140001670  jmp     short loc_140001677
0x140001672  mov     esi, 0C0000001h
0x140001677  xor     ebx, ebx
0x140001679  mov     [r14+10h], esi
0x14000167d  xor     edx, edx; PriorityBoost
0x14000167f  mov     [rdi+30h], ebx
0x140001682  mov     rcx, rdi; Irp
0x140001685  call    cs:__imp_IofCompleteRequest
0x14000168c  nop     dword ptr [rax+rax+00h]
0x140001691  mov     eax, ebx
0x140001693  jmp     loc_140001B9C
0x140001698  xor     edx, edx; PriorityBoost
0x14000169a  mov     dword ptr [rdi+30h], 0C00000EFh
0x1400016a1  mov     rcx, rdi; Irp
0x1400016a4  call    cs:__imp_IofCompleteRequest
0x1400016ab  nop     dword ptr [rax+rax+00h]
0x1400016b0  mov     ebx, 0C00000EFh
0x1400016b5  mov     eax, ebx
0x1400016b7  jmp     loc_140001B9C
0x1400016bc  mov     rcx, cs:WPP_GLOBAL_Control; jumptable 0000000140001506 case 22
0x1400016c3  cmp     rcx, r15
0x1400016c6  jz      short loc_1400016E3
0x1400016c8  cmp     byte ptr [rcx+29h], 4
0x1400016cc  jb      short loc_1400016E3
0x1400016ce  mov     rcx, [rcx+18h]
0x1400016d2  lea     r8, WPP_aa2742c9424e303f9b5b727f51c5aafc_Traceguids
0x1400016d9  mov     edx, 19h
0x1400016de  call    WPP_SF_
0x1400016e3  cmp     byte ptr [rsi+1], 2
0x1400016e7  jz      short loc_140001712
0x1400016e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400016f0  cmp     rcx, r15
0x1400016f3  jz      short loc_140001717
0x1400016f5  cmp     byte ptr [rcx+29h], 4
0x1400016f9  jb      short loc_140001717
0x1400016fb  mov     rcx, [rcx+18h]
0x1400016ff  lea     r8, WPP_aa2742c9424e303f9b5b727f51c5aafc_Traceguids
0x140001706  mov     edx, 1Ah
0x14000170b  call    WPP_SF_
0x140001710  jmp     short loc_140001717
0x140001712  xor     ebx, ebx
0x140001714  mov     [rdi+30h], ebx
0x140001717  mov     rcx, rdi; Irp
0x14000171a  call    cs:__imp_PoStartNextPowerIrp
0x140001721  nop     dword ptr [rax+rax+00h]
0x140001726  inc     byte ptr [rdi+43h]
0x140001729  mov     rdx, rdi; Irp
0x14000172c  add     qword ptr [rdi+0B8h], 48h ; 'H'
0x140001734  mov     rcx, r14; DeviceObject
0x140001737  call    cs:__imp_PoCallDriver
0x14000173e  nop     dword ptr [rax+rax+00h]
0x140001743  jmp     loc_140001B9C
0x140001748  mov     rcx, cs:WPP_GLOBAL_Control; jumptable 0000000140001506 case 27
0x14000174f  cmp     rcx, r15
0x140001752  jz      short loc_14000176F
0x140001754  cmp     byte ptr [rcx+29h], 4
0x140001758  jb      short loc_14000176F
0x14000175a  mov     rcx, [rcx+18h]
0x14000175e  lea     r8, WPP_aa2742c9424e303f9b5b727f51c5aafc_Traceguids
0x140001765  mov     edx, 1Bh
0x14000176a  call    WPP_SF_
0x14000176f  movzx   r9d, byte ptr [rsi+1]
0x140001774  cmp     r9d, 15h; switch 22 cases
0x140001778  ja      def_140001789; jumptable 0000000140001789 default case, cases 8,10-12,14-18
0x14000177e  mov     ecx, ds:(jpt_140001789 - 140000000h)[rbx+r9*4]
0x140001786  add     rcx, rbx
0x140001789  jmp     rcx; switch jump
0x14000178f  xorps   xmm0, xmm0; jumptable 0000000140001789 case 0
0x140001792  xor     eax, eax
0x140001794  movups  xmmword ptr [rsp+68h+DestinationString.Length], xmm0
0x140001799  mov     [rsp+68h+var_28], rax
0x14000179e  call    ?CleanUpExistingPorts@@YAJXZ; CleanUpExistingPorts(void)
0x1400017a3  xor     r8d, r8d; State
0x1400017a6  lea     rcx, [rsp+68h+DestinationString]; Event
0x1400017ab  xor     edx, edx; Type
0x1400017ad  call    cs:__imp_KeInitializeEvent
0x1400017b4  nop     dword ptr [rax+rax+00h]
0x1400017b9  mov     rax, [rdi+0B8h]
0x1400017c0  lea     rcx, ?RdpBusDeferIrpCompletion@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z; RdpBusDeferIrpCompletion(_DEVICE_OBJECT *,_IRP *,void *)
0x1400017c7  mov     rdx, rdi; Irp
0x1400017ca  movups  xmm0, xmmword ptr [rax]
0x1400017cd  movups  xmmword ptr [rax-48h], xmm0
0x1400017d1  movups  xmm1, xmmword ptr [rax+10h]
0x1400017d5  movups  xmmword ptr [rax-38h], xmm1
0x1400017d9  movups  xmm0, xmmword ptr [rax+20h]
0x1400017dd  movups  xmmword ptr [rax-28h], xmm0
0x1400017e1  movsd   xmm1, qword ptr [rax+30h]
0x1400017e6  movsd   qword ptr [rax-18h], xmm1
0x1400017eb  mov     byte ptr [rax-45h], 0
0x1400017ef  mov     rax, [rdi+0B8h]
0x1400017f6  mov     [rax-10h], rcx
0x1400017fa  lea     rcx, [rsp+68h+DestinationString]
0x1400017ff  mov     [rax-8], rcx
0x140001803  mov     rcx, r14; DeviceObject
0x140001806  mov     byte ptr [rax-45h], 0E0h
0x14000180a  call    cs:__imp_IofCallDriver
0x140001811  nop     dword ptr [rax+rax+00h]
0x140001816  mov     ebx, eax
0x140001818  cmp     eax, 103h
0x14000181d  jnz     short loc_140001845
0x14000181f  xor     ebx, ebx
0x140001821  lea     rcx, [rsp+68h+DestinationString]; Object
0x140001826  xor     r9d, r9d; Alertable
0x140001829  mov     [rsp+68h+Timeout], rbx; Timeout
0x14000182e  xor     r8d, r8d; WaitMode
0x140001831  mov     edx, 5; WaitReason
0x140001836  call    cs:__imp_KeWaitForSingleObject
0x14000183d  nop     dword ptr [rax+rax+00h]
0x140001842  mov     ebx, [rdi+30h]
0x140001845  xor     edx, edx; PriorityBoost
0x140001847  mov     [rdi+30h], ebx
0x14000184a  mov     rcx, rdi; Irp
0x14000184d  call    cs:__imp_IofCompleteRequest
0x140001854  nop     dword ptr [rax+rax+00h]
0x140001859  mov     eax, ebx
0x14000185b  jmp     loc_140001B9C
0x140001860  mov     rcx, cs:WPP_GLOBAL_Control; jumptable 0000000140001789 case 4
0x140001867  cmp     rcx, r15
0x14000186a  jz      loc_140001A9A
0x140001870  cmp     byte ptr [rcx+29h], 4
0x140001874  jb      loc_140001A9A
0x14000187a  mov     edx, 1Ch
0x14000187f  jmp     loc_140001A5B
0x140001884  inc     byte ptr [rdi+43h]; jumptable 0000000140001789 case 2
0x140001887  xor     ebx, ebx
0x140001889  add     qword ptr [rdi+0B8h], 48h ; 'H'
0x140001891  mov     rdx, rdi; Irp
0x140001894  mov     rcx, r14; DeviceObject
0x140001897  mov     [rdi+30h], ebx
0x14000189a  call    cs:__imp_IofCallDriver
0x1400018a1  nop     dword ptr [rax+rax+00h]
0x1400018a6  mov     rcx, r14; TargetDevice
0x1400018a9  mov     ebx, eax
0x1400018ab  call    cs:__imp_IoDetachDevice
0x1400018b2  nop     dword ptr [rax+rax+00h]
0x1400018b7  mov     rcx, rbp; DeviceObject
0x1400018ba  call    cs:__imp_IoDeleteDevice
0x1400018c1  nop     dword ptr [rax+rax+00h]
0x1400018c6  mov     eax, ebx
0x1400018c8  jmp     loc_140001B9C
0x1400018cd  mov     rcx, cs:WPP_GLOBAL_Control; jumptable 0000000140001789 case 9
0x1400018d4  cmp     rcx, r15
0x1400018d7  jz      def_140001506; jumptable 0000000140001506 default case, cases 1,5-13,15-17,19-21,23-26
0x1400018dd  cmp     byte ptr [rcx+29h], 4
0x1400018e1  jb      def_140001506; jumptable 0000000140001506 default case, cases 1,5-13,15-17,19-21,23-26
0x1400018e7  mov     edx, 1Dh
0x1400018ec  mov     rcx, [rcx+18h]
0x1400018f0  lea     r8, WPP_aa2742c9424e303f9b5b727f51c5aafc_Traceguids
0x1400018f7  call    WPP_SF_
0x1400018fc  jmp     def_140001506; jumptable 0000000140001506 default case, cases 1,5-13,15-17,19-21,23-26
0x140001901  mov     rcx, cs:WPP_GLOBAL_Control; jumptable 0000000140001789 case 19
0x140001908  cmp     rcx, r15
0x14000190b  jz      def_140001506; jumptable 0000000140001506 default case, cases 1,5-13,15-17,19-21,23-26
0x140001911  cmp     byte ptr [rcx+29h], 4
0x140001915  jb      def_140001506; jumptable 0000000140001506 default case, cases 1,5-13,15-17,19-21,23-26
0x14000191b  mov     edx, 1Eh
0x140001920  jmp     short loc_1400018EC
0x140001922  mov     rcx, cs:WPP_GLOBAL_Control; jumptable 0000000140001789 case 7
0x140001929  cmp     rcx, r15
0x14000192c  jz      short loc_140001949
0x14000192e  cmp     byte ptr [rcx+29h], 4
0x140001932  jb      short loc_140001949
0x140001934  mov     rcx, [rcx+18h]
0x140001938  lea     r8, WPP_aa2742c9424e303f9b5b727f51c5aafc_Traceguids
0x14000193f  mov     edx, 1Fh
0x140001944  call    WPP_SF_
0x140001949  mov     ecx, [rsi+8]
0x14000194c  test    ecx, ecx
0x14000194e  jz      loc_140001A20
0x140001954  sub     ecx, 1
0x140001957  jz      loc_1400019FC
  ... truncated ...
```
