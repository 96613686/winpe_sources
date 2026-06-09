# CKsDevice::DispatchPnp(_DEVICE_OBJECT *,_IRP *)

- ea: `0x180048c60`
- end: `0x180049456`
- name: `?DispatchPnp@CKsDevice@@SAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z`
- size: `2038`
- prototype: `__int64 __fastcall(struct _DEVICE_OBJECT *Object, struct _IRP *)`
- caller_count: `1`
- callee_count: `21`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800481d0`

## callees

- `0x18000abec`
- `0x18000b7bc`
- `0x18000c1dc`
- `0x18000c4c8`
- `0x18000c630`
- `0x1800139f8`
- `0x180019cb0`
- `0x180047ea0`
- `0x180048c60`
- `0x18005963c`
- `0x18005b7e4`
- `0x18005b964`
- `0x18005c2e0`
- `0x18005c7b8`
- `0x18005c83c`
- `0x18005d03c`
- `0x18005ebec`
- `0x18005fca0`
- `0x180061cd0`
- `0x180066bdc`
- `0x180066cc8`

## import_xrefs

- `ntoskrnl!IofCallDriver` at `0x180048fb6`
- `ntoskrnl!IofCallDriver` at `0x180049434`
- `ntoskrnl!IofCallDriver` at `0x180048fb6`
- `ntoskrnl!IofCallDriver` at `0x180049434`
- `ntoskrnl!IoDetachDevice` at `0x180048fc7`
- `ntoskrnl!IoDetachDevice` at `0x180048fc7`
- `ntoskrnl!IoDeleteDevice` at `0x180048f19`
- `ntoskrnl!IoDeleteDevice` at `0x180048fd6`
- `ntoskrnl!IoDeleteDevice` at `0x180048f19`
- `ntoskrnl!IoDeleteDevice` at `0x180048fd6`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x180048dcc`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x1800491e6`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x180048dcc`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x1800491e6`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x180049264`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x180049264`
- `ntoskrnl!IoReleaseRemoveLockAndWaitEx` at `0x180048f4f`
- `ntoskrnl!IoReleaseRemoveLockAndWaitEx` at `0x180048f4f`
- `ntoskrnl!IofCompleteRequest` at `0x1800492b4`
- `ntoskrnl!IofCompleteRequest` at `0x1800492b4`

## pseudocode

```c
__int64 __fastcall CKsDevice::DispatchPnp(struct _DEVICE_OBJECT *Object, struct _IRP *a2)
{
  __int64 *v4; // rdx
  PVOID DeviceExtension; // rax
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rbp
  __int64 **v8; // r14
  unsigned int MinorFunction; // ecx
  struct _DEVICE_OBJECT **v10; // rsi
  unsigned int v11; // ecx
  unsigned int v12; // ecx
  unsigned int v13; // ecx
  __int64 v14; // rax
  void (__fastcall *v15)(__int64 **, struct _IRP *); // rax
  struct _KSDEVICE_HEADER_EX *DeviceHeader; // r12
  int v17; // edx
  PDEVICE_OBJECT v18; // rcx
  int v19; // r9d
  __int64 v20; // rax
  void (__fastcall *v21)(__int64 **, struct _IRP *); // rax
  __int64 **v22; // rcx
  struct _DEVICE_OBJECT *v23; // r14
  struct _DEVICE_OBJECT *v24; // rcx
  PVOID v25; // rax
  struct _DEVICE_OBJECT *v26; // rbx
  struct _DEVICE_OBJECT *v27; // rax
  int v28; // edx
  int Capabilities; // ebx
  __int64 *v30; // rax
  __int64 (__fastcall *v31)(__int64 **, struct _IRP *); // rax
  int v32; // edx
  CKsDevice *v34; // rcx
  int v35; // r8d
  __int64 *v36; // rax
  unsigned int v37; // ecx
  unsigned int v38; // ecx
  unsigned int v39; // ecx
  unsigned int v40; // ecx
  __int64 *v41; // rax
  __int64 v42; // rax
  void (__fastcall *v43)(__int64 **, struct _IRP *); // rax
  struct _KSDEVICE_HEADER_EX *v44; // r14
  int v45; // edx
  CKsDevice *v46; // rcx
  __int64 v47; // rcx
  __int64 v48; // r8
  NTSTATUS ThermalNotification; // eax
  int v50; // eax
  __int64 v51; // r8
  __int64 v52; // rax
  __int64 v53; // [rsp+30h] [rbp-58h]

  v4 = WPP_50288c75019938eedd86f8b19427641e_Traceguids;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LOBYTE(v4) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)v4,
      1,
      22,
      (__int64)WPP_50288c75019938eedd86f8b19427641e_Traceguids);
    v4 = WPP_50288c75019938eedd86f8b19427641e_Traceguids;
  }
  DeviceExtension = Object->DeviceExtension;
  if ( *(_DWORD *)DeviceExtension == 1146114891 )
    return PdoDispatchPnp(Object, a2);
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  v8 = *(__int64 ***)(*(_QWORD *)DeviceExtension + 360LL);
  MinorFunction = CurrentStackLocation->MinorFunction;
  v10 = (struct _DEVICE_OBJECT **)(v8 - 25);
  if ( MinorFunction <= 5 )
  {
    if ( MinorFunction == 5 )
    {
      ((void (__fastcall *)(__int64 **, __int64 *))(*v10)->Timer)(
        v8 - 25,
        WPP_50288c75019938eedd86f8b19427641e_Traceguids);
      a2->IoStatus.Status = 0;
      Capabilities = CKsDevice::ForwardIrpSynchronous((CKsDevice *)(v8 - 25), a2);
      if ( Capabilities >= 0 )
      {
        v36 = *v8;
        *((_BYTE *)v10 + 784) = 0;
        if ( v36 )
        {
          if ( *v36 )
          {
            v31 = *(__int64 (__fastcall **)(__int64 **, struct _IRP *))(*v36 + 24);
LABEL_59:
            if ( v31 )
              Capabilities = v31(v8, a2);
          }
        }
      }
    }
    else
    {
      if ( !CurrentStackLocation->MinorFunction )
      {
        *((_BYTE *)v10 + 784) = 0;
        Capabilities = CKsDevice::ForwardIrpSynchronous((CKsDevice *)(v8 - 25), a2);
        if ( Capabilities >= 0 )
          return (unsigned int)CKsDevice::PnpStart((CKsDevice *)(v8 - 25), a2);
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v32) = 4;
          WPP_RECORDER_SF_D(
            WPP_GLOBAL_Control->DeviceExtension,
            v32,
            1,
            23,
            (__int64)WPP_50288c75019938eedd86f8b19427641e_Traceguids,
            Capabilities);
        }
        CKsDevice::RedispatchPendingCreates((CKsDevice *)(v8 - 25));
        goto LABEL_53;
      }
      v11 = MinorFunction - 1;
      if ( v11 )
      {
        v12 = v11 - 1;
        if ( v12 )
        {
          v13 = v12 - 1;
          if ( v13 )
          {
            if ( v13 == 1 )
            {
              if ( *((_BYTE *)v8 + 48) )
              {
                CKsDevice::PnpStop((CKsDevice *)(v8 - 25), a2);
              }
              else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              {
                LOBYTE(v4) = 4;
                WPP_RECORDER_SF_(
                  WPP_GLOBAL_Control->DeviceExtension,
                  (_DWORD)v4,
                  1,
                  24,
                  (__int64)WPP_50288c75019938eedd86f8b19427641e_Traceguids);
              }
              CKsDevice::RedispatchPendingCreates((CKsDevice *)(v8 - 25));
              CKsDevice::RedispatchPendedIrps((CKsDevice *)(v8 - 25), 1);
              goto LABEL_105;
            }
LABEL_67:
            a2->Tail.Overlay.CurrentStackLocation = CurrentStackLocation + 1;
LABEL_107:
            ++a2->CurrentLocation;
            return (unsigned int)IofCallDriver((PDEVICE_OBJECT)v8[5], a2);
          }
          CKsDevice::RedispatchPendingCreates((CKsDevice *)(v8 - 25));
          if ( *v8 )
          {
            v14 = **v8;
            if ( v14 )
            {
              v15 = *(void (__fastcall **)(__int64 **, struct _IRP *))(v14 + 56);
              goto LABEL_103;
            }
          }
          goto LABEL_105;
        }
        DeviceHeader = CKsDevice::GetDeviceHeaderEx(Object);
        if ( IoAcquireRemoveLockEx(&DeviceHeader->RemoveLock, a2, File, 1u, 0x20u) )
        {
          if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            goto LABEL_29;
          v18 = WPP_GLOBAL_Control;
          if ( !LOWORD(WPP_GLOBAL_Control->DeviceType) )
            goto LABEL_29;
          v19 = 26;
        }
        else
        {
          if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            goto LABEL_29;
          v18 = WPP_GLOBAL_Control;
          if ( !LOWORD(WPP_GLOBAL_Control->DeviceType) )
            goto LABEL_29;
          v19 = 25;
        }
        LOBYTE(v17) = 5;
        WPP_RECORDER_SF_(v18->DeviceExtension, v17, 1, v19, (__int64)WPP_50288c75019938eedd86f8b19427641e_Traceguids);
LABEL_29:
        if ( *((_BYTE *)v8 + 48) )
        {
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
            && LOWORD(WPP_GLOBAL_Control->DeviceType) )
          {
            LOBYTE(v17) = 5;
            WPP_RECORDER_SF_(
              WPP_GLOBAL_Control->DeviceExtension,
              v17,
              1,
              27,
              (__int64)WPP_50288c75019938eedd86f8b19427641e_Traceguids);
          }
          CKsDevice::PnpStop((CKsDevice *)(v8 - 25), a2);
          ((void (__fastcall *)(__int64 **))(*v10)->Timer)(v8 - 25);
          KspFreeDeviceClasses(v8[3]);
          (*(void (__fastcall **)(__int64 **))&(*v10)->Flags)(v8 - 25);
        }
        CKsDevice::RedispatchPendingCreates((CKsDevice *)(v8 - 25));
        CKsDevice::RedispatchPendedIrps((CKsDevice *)(v8 - 25), 1);
        if ( *v8 )
        {
          v20 = **v8;
          if ( v20 )
          {
            v21 = *(void (__fastcall **)(__int64 **, struct _IRP *))(v20 + 64);
            if ( v21 )
              v21(v8, a2);
          }
        }
        v22 = v8 - 25;
        v23 = (struct _DEVICE_OBJECT *)v8[5];
        ((void (__fastcall *)(__int64 **))(*v10)->Timer)(v22);
        v24 = v10[140];
        if ( v24 )
        {
          do
          {
            v25 = v24->DeviceExtension;
            v26 = (struct _DEVICE_OBJECT *)*((_QWORD *)v25 + 2);
            *((_QWORD *)v25 + 2) = 0;
            *((_BYTE *)v25 + 44) = 1;
            IoDeleteDevice(v24);
            v24 = v26;
          }
          while ( v26 );
        }
        v27 = *v10;
        v10[140] = 0;
        (*(void (__fastcall **)(struct _DEVICE_OBJECT **))&v27->Flags)(v10);
        IoReleaseRemoveLockAndWaitEx(&DeviceHeader->RemoveLock, a2, 0x20u);
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
        {
          LOBYTE(v28) = 5;
          WPP_RECORDER_SF_(
            WPP_GLOBAL_Control->DeviceExtension,
            v28,
            1,
            28,
            (__int64)WPP_50288c75019938eedd86f8b19427641e_Traceguids);
        }
        KsTerminateDevice(Object);
        ++a2->CurrentLocation;
        ++a2->Tail.Overlay.CurrentStackLocation;
        a2->IoStatus.Status = 0;
        Capabilities = IofCallDriver(v23, a2);
        IoDetachDevice(v23);
        IoDeleteDevice(Object);
        return (unsigned int)Capabilities;
      }
      ((void (__fastcall *)(__int64 **, __int64 *))(*v10)->Timer)(
        v8 - 25,
        WPP_50288c75019938eedd86f8b19427641e_Traceguids);
      a2->IoStatus.Status = 0;
      Capabilities = CKsDevice::ForwardIrpSynchronous((CKsDevice *)(v8 - 25), a2);
      if ( Capabilities >= 0 )
      {
        v30 = *v8;
        *((_BYTE *)v10 + 784) = 0;
        if ( v30 )
        {
          if ( *v30 )
          {
            v31 = *(__int64 (__fastcall **)(__int64 **, struct _IRP *))(*v30 + 48);
            goto LABEL_59;
          }
        }
      }
    }
    (*(void (__fastcall **)(__int64 **))&(*v10)->Flags)(v8 - 25);
LABEL_53:
    v35 = Capabilities;
    goto LABEL_54;
  }
  v37 = MinorFunction - 6;
  if ( !v37 )
  {
    CKsDevice::RedispatchPendingCreates((CKsDevice *)(v8 - 25));
    if ( *v8 )
    {
      v52 = **v8;
      if ( v52 )
      {
        v15 = *(void (__fastcall **)(__int64 **, struct _IRP *))(v52 + 32);
LABEL_103:
        if ( v15 )
          v15(v8, a2);
      }
    }
LABEL_105:
    a2->IoStatus.Status = 0;
LABEL_106:
    ++a2->Tail.Overlay.CurrentStackLocation;
    goto LABEL_107;
  }
  v38 = v37 - 1;
  if ( !v38 )
  {
    if ( !CurrentStackLocation->Parameters.Read.Length )
    {
      ((void (__fastcall *)(__int64 **, __int64 *))(*v10)->Timer)(
        v8 - 25,
        WPP_50288c75019938eedd86f8b19427641e_Traceguids);
      CKsDevice::EnumerateChildren((CKsDevice *)(v8 - 25), a2);
      (*(void (__fastcall **)(__int64 **))&(*v10)->Flags)(v8 - 25);
    }
    goto LABEL_106;
  }
  v39 = v38 - 1;
  if ( v39 )
  {
    v40 = v39 - 1;
    if ( !v40 )
    {
      v44 = CKsDevice::GetDeviceHeaderEx(Object);
      Capabilities = IoAcquireRemoveLockEx(&v44->RemoveLock, a2, File, 1u, 0x20u);
      if ( Capabilities )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
        {
          LOBYTE(v45) = 5;
          WPP_RECORDER_SF_(
            WPP_GLOBAL_Control->DeviceExtension,
            v45,
            1,
            32,
            (__int64)WPP_50288c75019938eedd86f8b19427641e_Traceguids);
        }
        a2->IoStatus.Status = Capabilities;
        IofCompleteRequest(a2, 0);
      }
      else
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
        {
          LOBYTE(v45) = 5;
          WPP_RECORDER_SF_(
            WPP_GLOBAL_Control->DeviceExtension,
            v45,
            1,
            31,
            (__int64)WPP_50288c75019938eedd86f8b19427641e_Traceguids);
        }
        a2->IoStatus.Status = 0;
        Capabilities = CKsDevice::ForwardIrpSynchronous((CKsDevice *)v10, a2);
        if ( Capabilities >= 0 )
          Capabilities = CKsDevice::PnpQueryCapabilities((CKsDevice *)v10, a2);
        CKsDevice::CompleteIrp(v46, a2, Capabilities);
        IoReleaseRemoveLockEx(&v44->RemoveLock, a2, 0x20u);
      }
      return (unsigned int)Capabilities;
    }
    if ( v40 == 14 )
    {
      ((void (__fastcall *)(__int64 **, __int64 *))(*v10)->Timer)(
        v8 - 25,
        WPP_50288c75019938eedd86f8b19427641e_Traceguids);
      KspSetDeviceClassesState(v8[3], 0);
      KspFreeDeviceClasses(v8[3]);
      v41 = *v8;
      *(_WORD *)((char *)v10 + 787) = 256;
      if ( v41 )
      {
        v42 = *v41;
        if ( v42 )
        {
          v43 = *(void (__fastcall **)(__int64 **, struct _IRP *))(v42 + 80);
          if ( v43 )
            v43(v8, a2);
        }
      }
      CKsDevice::GenerateDeviceLostEvent((CKsDevice *)(v8 - 25));
      (*(void (__fastcall **)(__int64 **))&(*v10)->Flags)(v8 - 25);
      CKsDevice::RedispatchPendingCreates((CKsDevice *)(v8 - 25));
      CKsDevice::RedispatchPendedIrps((CKsDevice *)(v8 - 25), 1);
      goto LABEL_106;
    }
    goto LABEL_67;
  }
  if ( !IsEqualGUIDAligned(
          &CurrentStackLocation->Parameters.Create.SecurityContext->SecurityQos,
          &GUID_THERMAL_COOLING_INTERFACE) )
  {
    if ( !*((_BYTE *)v10 + 786) && !*((_BYTE *)v10 + 1088) || *((_DWORD *)*v8 + 6) < 0x100u || !*(_QWORD *)(**v8 + 104) )
      goto LABEL_106;
    if ( ((__int64)WPP_MAIN_CB.Dpc.SystemArgument1 & 1) != 0 )
      McTemplateK0ppjq_EtwWriteTransfer(v47, (const EVENT_DESCRIPTOR *)KS_QueryInterface_Start, v48, 0, 0, v47, 0);
    v50 = (*(__int64 (__fastcall **)(__int64 **, struct _IRP *))(**v8 + 104))(v8, a2);
    Capabilities = v50;
    if ( ((__int64)WPP_MAIN_CB.Dpc.SystemArgument1 & 1) != 0 )
    {
      LODWORD(v53) = v50;
      McTemplateK0ppjq_EtwWriteTransfer(
        (__int64)v34,
        (const EVENT_DESCRIPTOR *)KS_QueryInterface_Stop,
        v51,
        0,
        0,
        CurrentStackLocation->Parameters.WMI.ProviderId,
        v53);
    }
    if ( Capabilities == -1073741637 )
      goto LABEL_106;
    a2->IoStatus.Status = Capabilities;
    a2->IoStatus.Information = 0;
    goto LABEL_53;
  }
  ThermalNotification = KspCreateThermalNotification(a2, v10 + 9, v10[137], v10 + 138);
  Capabilities = ThermalNotification;
  if ( ThermalNotification < 0 )
    goto LABEL_106;
  a2->IoStatus.Status = ThermalNotification;
  v35 = ThermalNotification;
  a2->IoStatus.Information = 0;
LABEL_54:
  CKsDevice::CompleteIrp(v34, a2, v35);
  return (unsigned int)Capabilities;
}

```

## disassembly

```asm
0x180048c60  push    rbx
0x180048c62  push    rbp
0x180048c63  push    rsi
0x180048c64  push    rdi
0x180048c65  push    r12
0x180048c67  push    r13
0x180048c69  push    r14
0x180048c6b  push    r15
0x180048c6d  sub     rsp, 48h
0x180048c71  mov     rdi, rdx
0x180048c74  mov     r15, rcx
0x180048c77  xor     r13d, r13d
0x180048c7a  lea     r12, WPP_RECORDER_INITIALIZED
0x180048c81  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x180048c88  lea     rdx, WPP_50288c75019938eedd86f8b19427641e_Traceguids
0x180048c8f  lea     ebx, [r13+1]
0x180048c93  jz      short loc_180048CC1
0x180048c95  mov     rcx, cs:WPP_GLOBAL_Control
0x180048c9c  cmp     [rcx+48h], r13w
0x180048ca1  jz      short loc_180048CC1
0x180048ca3  mov     rcx, [rcx+40h]
0x180048ca7  lea     r9d, [r13+16h]
0x180048cab  mov     qword ptr [rsp+88h+RemlockSize], rdx
0x180048cb0  mov     r8d, ebx
0x180048cb3  mov     dl, 5
0x180048cb5  call    WPP_RECORDER_SF_
0x180048cba  lea     rdx, WPP_50288c75019938eedd86f8b19427641e_Traceguids
0x180048cc1  mov     rax, [r15+40h]
0x180048cc5  cmp     dword ptr [rax], 4450534Bh
0x180048ccb  jnz     short loc_180048CDD
0x180048ccd  mov     rdx, rdi; Irp
0x180048cd0  mov     rcx, r15; Object
0x180048cd3  call    ?PdoDispatchPnp@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z; PdoDispatchPnp(_DEVICE_OBJECT *,_IRP *)
0x180048cd8  jmp     loc_180049444
0x180048cdd  mov     rax, [rax]
0x180048ce0  mov     rbp, [rdi+0B8h]
0x180048ce7  mov     r14, [rax+168h]
0x180048cee  movzx   ecx, byte ptr [rbp+1]
0x180048cf2  lea     rsi, [r14-0C8h]
0x180048cf9  cmp     ecx, 5
0x180048cfc  ja      loc_18004910E
0x180048d02  jz      loc_1800490AC
0x180048d08  test    ecx, ecx
0x180048d0a  jz      loc_180049037
0x180048d10  sub     ecx, ebx
0x180048d12  jz      loc_180048FE7
0x180048d18  sub     ecx, ebx
0x180048d1a  jz      loc_180048DA8
0x180048d20  sub     ecx, ebx
0x180048d22  jz      short loc_180048D7F
0x180048d24  cmp     ecx, ebx
0x180048d26  jnz     loc_180049134
0x180048d2c  cmp     [r14+30h], r13b
0x180048d30  jz      short loc_180048D3F
0x180048d32  mov     rdx, rdi; struct _IRP *
0x180048d35  mov     rcx, rsi; this
0x180048d38  call    ?PnpStop@CKsDevice@@QEAAXPEAU_IRP@@@Z; CKsDevice::PnpStop(_IRP *)
0x180048d3d  jmp     short loc_180048D68
0x180048d3f  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x180048d46  jz      short loc_180048D68
0x180048d48  mov     rcx, cs:WPP_GLOBAL_Control
0x180048d4f  mov     r9d, 18h
0x180048d55  mov     qword ptr [rsp+88h+RemlockSize], rdx
0x180048d5a  mov     r8d, ebx
0x180048d5d  mov     dl, 4
0x180048d5f  mov     rcx, [rcx+40h]
0x180048d63  call    WPP_RECORDER_SF_
0x180048d68  mov     rcx, rsi; this
0x180048d6b  call    ?RedispatchPendingCreates@CKsDevice@@QEAAXXZ; CKsDevice::RedispatchPendingCreates(void)
0x180048d70  mov     dl, bl; unsigned __int8
0x180048d72  mov     rcx, rsi; this
0x180048d75  call    ?RedispatchPendedIrps@CKsDevice@@AEAAXE@Z; CKsDevice::RedispatchPendedIrps(uchar)
0x180048d7a  jmp     loc_18004941E
0x180048d7f  mov     rcx, rsi; this
0x180048d82  call    ?RedispatchPendingCreates@CKsDevice@@QEAAXXZ; CKsDevice::RedispatchPendingCreates(void)
0x180048d87  mov     rax, [r14]
0x180048d8a  test    rax, rax
0x180048d8d  jz      loc_18004941E
0x180048d93  mov     rax, [rax]
0x180048d96  test    rax, rax
0x180048d99  jz      loc_18004941E
0x180048d9f  mov     rax, [rax+38h]
0x180048da3  jmp     loc_18004940E
0x180048da8  mov     rcx, r15; struct _DEVICE_OBJECT *
0x180048dab  call    ?GetDeviceHeaderEx@CKsDevice@@SAPEAU_KSDEVICE_HEADER_EX@@PEAU_DEVICE_OBJECT@@@Z; CKsDevice::GetDeviceHeaderEx(_DEVICE_OBJECT *)
0x180048db0  mov     ebp, 20h ; ' '
0x180048db5  lea     r8, File; File
0x180048dbc  mov     rcx, rax; RemoveLock
0x180048dbf  mov     [rsp+88h+RemlockSize], ebp; RemlockSize
0x180048dc3  mov     r9d, ebx; Line
0x180048dc6  mov     rdx, rdi; Tag
0x180048dc9  mov     r12, rax
0x180048dcc  call    cs:__imp_IoAcquireRemoveLockEx
0x180048dd3  nop     dword ptr [rax+rax+00h]
0x180048dd8  test    eax, eax
0x180048dda  jnz     short loc_180048E00
0x180048ddc  lea     rax, WPP_RECORDER_INITIALIZED
0x180048de3  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180048dea  jz      short loc_180048E45
0x180048dec  mov     rcx, cs:WPP_GLOBAL_Control
0x180048df3  cmp     [rcx+48h], r13w
0x180048df8  jz      short loc_180048E45
0x180048dfa  lea     r9d, [rbp-7]
0x180048dfe  jmp     short loc_180048E24
0x180048e00  lea     rax, WPP_RECORDER_INITIALIZED
0x180048e07  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180048e0e  jz      short loc_180048E45
0x180048e10  mov     rcx, cs:WPP_GLOBAL_Control
0x180048e17  cmp     [rcx+48h], r13w
0x180048e1c  jz      short loc_180048E45
0x180048e1e  mov     r9d, 1Ah
0x180048e24  mov     rcx, [rcx+40h]
0x180048e28  lea     rax, WPP_50288c75019938eedd86f8b19427641e_Traceguids
0x180048e2f  mov     r8d, ebx
0x180048e32  mov     qword ptr [rsp+88h+RemlockSize], rax
0x180048e37  mov     dl, 5
0x180048e39  call    WPP_RECORDER_SF_
0x180048e3e  lea     rax, WPP_RECORDER_INITIALIZED
0x180048e45  cmp     [r14+30h], r13b
0x180048e49  jz      short loc_180048EB4
0x180048e4b  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180048e52  jz      short loc_180048E82
0x180048e54  mov     rcx, cs:WPP_GLOBAL_Control
0x180048e5b  cmp     [rcx+48h], r13w
0x180048e60  jz      short loc_180048E82
0x180048e62  mov     rcx, [rcx+40h]
0x180048e66  lea     rax, WPP_50288c75019938eedd86f8b19427641e_Traceguids
0x180048e6d  mov     r9d, 1Bh
0x180048e73  mov     qword ptr [rsp+88h+RemlockSize], rax
0x180048e78  mov     r8d, ebx
0x180048e7b  mov     dl, 5
0x180048e7d  call    WPP_RECORDER_SF_
0x180048e82  mov     rdx, rdi; struct _IRP *
0x180048e85  mov     rcx, rsi; this
0x180048e88  call    ?PnpStop@CKsDevice@@QEAAXPEAU_IRP@@@Z; CKsDevice::PnpStop(_IRP *)
0x180048e8d  mov     rax, [rsi]
0x180048e90  mov     rcx, rsi
0x180048e93  mov     rax, [rax+28h]
0x180048e97  call    _guard_dispatch_icall
0x180048e9c  mov     rcx, [r14+18h]
0x180048ea0  call    KspFreeDeviceClasses
0x180048ea5  mov     rax, [rsi]
0x180048ea8  mov     rcx, rsi
0x180048eab  mov     rax, [rax+30h]
0x180048eaf  call    _guard_dispatch_icall
0x180048eb4  mov     rcx, rsi; this
0x180048eb7  call    ?RedispatchPendingCreates@CKsDevice@@QEAAXXZ; CKsDevice::RedispatchPendingCreates(void)
0x180048ebc  mov     dl, bl; unsigned __int8
0x180048ebe  mov     rcx, rsi; this
0x180048ec1  call    ?RedispatchPendedIrps@CKsDevice@@AEAAXE@Z; CKsDevice::RedispatchPendedIrps(uchar)
0x180048ec6  mov     rax, [r14]
0x180048ec9  test    rax, rax
0x180048ecc  jz      short loc_180048EEA
0x180048ece  mov     rax, [rax]
0x180048ed1  test    rax, rax
0x180048ed4  jz      short loc_180048EEA
0x180048ed6  mov     rax, [rax+40h]
0x180048eda  test    rax, rax
0x180048edd  jz      short loc_180048EEA
0x180048edf  mov     rdx, rdi
0x180048ee2  mov     rcx, r14
0x180048ee5  call    _guard_dispatch_icall
0x180048eea  mov     rax, [rsi]
0x180048eed  mov     rcx, rsi
0x180048ef0  mov     r14, [r14+28h]
0x180048ef4  mov     rax, [rax+28h]
0x180048ef8  call    _guard_dispatch_icall
0x180048efd  mov     rcx, [rsi+460h]; DeviceObject
0x180048f04  test    rcx, rcx
0x180048f07  jz      short loc_180048F30
0x180048f09  mov     rax, [rcx+40h]
0x180048f0d  mov     rbx, [rax+10h]
0x180048f11  mov     [rax+10h], r13
0x180048f15  mov     byte ptr [rax+2Ch], 1
0x180048f19  call    cs:__imp_IoDeleteDevice
0x180048f20  nop     dword ptr [rax+rax+00h]
0x180048f25  mov     rcx, rbx
0x180048f28  test    rbx, rbx
0x180048f2b  jnz     short loc_180048F09
0x180048f2d  lea     ebx, [rcx+1]
0x180048f30  mov     rax, [rsi]
0x180048f33  mov     rcx, rsi
0x180048f36  mov     [rsi+460h], r13
0x180048f3d  mov     rax, [rax+30h]
0x180048f41  call    _guard_dispatch_icall
0x180048f46  mov     r8d, ebp; RemlockSize
0x180048f49  mov     rdx, rdi; Tag
0x180048f4c  mov     rcx, r12; RemoveLock
0x180048f4f  call    cs:__imp_IoReleaseRemoveLockAndWaitEx
0x180048f56  nop     dword ptr [rax+rax+00h]
0x180048f5b  lea     rax, WPP_RECORDER_INITIALIZED
0x180048f62  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180048f69  jz      short loc_180048F99
0x180048f6b  mov     rcx, cs:WPP_GLOBAL_Control
0x180048f72  cmp     [rcx+48h], r13w
0x180048f77  jz      short loc_180048F99
0x180048f79  mov     rcx, [rcx+40h]
0x180048f7d  lea     rax, WPP_50288c75019938eedd86f8b19427641e_Traceguids
0x180048f84  mov     r9d, 1Ch
0x180048f8a  mov     qword ptr [rsp+88h+RemlockSize], rax
0x180048f8f  mov     r8d, ebx
0x180048f92  mov     dl, 5
0x180048f94  call    WPP_RECORDER_SF_
0x180048f99  mov     rcx, r15; DeviceObject
0x180048f9c  call    KsTerminateDevice
0x180048fa1  add     [rdi+43h], bl
0x180048fa4  mov     rdx, rdi; Irp
0x180048fa7  add     qword ptr [rdi+0B8h], 48h ; 'H'
0x180048faf  mov     rcx, r14; DeviceObject
0x180048fb2  mov     [rdi+30h], r13d
0x180048fb6  call    cs:__imp_IofCallDriver
0x180048fbd  nop     dword ptr [rax+rax+00h]
0x180048fc2  mov     rcx, r14; TargetDevice
0x180048fc5  mov     ebx, eax
0x180048fc7  call    cs:__imp_IoDetachDevice
0x180048fce  nop     dword ptr [rax+rax+00h]
0x180048fd3  mov     rcx, r15; DeviceObject
0x180048fd6  call    cs:__imp_IoDeleteDevice
0x180048fdd  nop     dword ptr [rax+rax+00h]
0x180048fe2  jmp     loc_180049442
0x180048fe7  mov     rax, [rsi]
0x180048fea  mov     rcx, rsi
0x180048fed  mov     rax, [rax+28h]
0x180048ff1  call    _guard_dispatch_icall
0x180048ff6  mov     rdx, rdi; struct _IRP *
0x180048ff9  mov     [rdi+30h], r13d
0x180048ffd  mov     rcx, rsi; this
0x180049000  call    ?ForwardIrpSynchronous@CKsDevice@@QEAAJPEAU_IRP@@@Z; CKsDevice::ForwardIrpSynchronous(_IRP *)
0x180049005  mov     ebx, eax
0x180049007  test    eax, eax
0x180049009  js      loc_1800490FD
0x18004900f  mov     rax, [r14]
0x180049012  mov     [rsi+310h], r13b
0x180049019  test    rax, rax
0x18004901c  jz      loc_1800490FD
0x180049022  mov     rcx, [rax]
0x180049025  test    rcx, rcx
0x180049028  jz      loc_1800490FD
0x18004902e  mov     rax, [rcx+30h]
0x180049032  jmp     loc_1800490EB
0x180049037  mov     rdx, rdi; struct _IRP *
0x18004903a  mov     [rsi+310h], r13b
0x180049041  mov     rcx, rsi; this
0x180049044  call    ?ForwardIrpSynchronous@CKsDevice@@QEAAJPEAU_IRP@@@Z; CKsDevice::ForwardIrpSynchronous(_IRP *)
0x180049049  mov     ebx, eax
0x18004904b  test    eax, eax
0x18004904d  js      short loc_18004905F
0x18004904f  mov     rdx, rdi; struct _IRP *
0x180049052  mov     rcx, rsi; this
0x180049055  call    ?PnpStart@CKsDevice@@QEAAJPEAU_IRP@@@Z; CKsDevice::PnpStart(_IRP *)
0x18004905a  jmp     loc_180049440
0x18004905f  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x180049066  jz      short loc_180049094
0x180049068  mov     rcx, cs:WPP_GLOBAL_Control
0x18004906f  lea     rax, WPP_50288c75019938eedd86f8b19427641e_Traceguids
0x180049076  mov     r9d, 17h
0x18004907c  mov     dword ptr [rsp+88h+var_60], ebx
0x180049080  mov     dl, 4
0x180049082  mov     qword ptr [rsp+88h+RemlockSize], rax
0x180049087  mov     rcx, [rcx+40h]
0x18004908b  lea     r8d, [r9-16h]
0x18004908f  call    WPP_RECORDER_SF_D
0x180049094  mov     rcx, rsi; this
0x180049097  call    ?RedispatchPendingCreates@CKsDevice@@QEAAXXZ; CKsDevice::RedispatchPendingCreates(void)
0x18004909c  mov     r8d, ebx; int
0x18004909f  mov     rdx, rdi; struct _IRP *
0x1800490a2  call    ?CompleteIrp@CKsDevice@@QEAAJPEAU_IRP@@J@Z; CKsDevice::CompleteIrp(_IRP *,long)
0x1800490a7  jmp     loc_180049442
0x1800490ac  mov     rax, [rsi]
0x1800490af  mov     rcx, rsi
0x1800490b2  mov     rax, [rax+28h]
0x1800490b6  call    _guard_dispatch_icall
0x1800490bb  mov     rdx, rdi; struct _IRP *
0x1800490be  mov     [rdi+30h], r13d
0x1800490c2  mov     rcx, rsi; this
0x1800490c5  call    ?ForwardIrpSynchronous@CKsDevice@@QEAAJPEAU_IRP@@@Z; CKsDevice::ForwardIrpSynchronous(_IRP *)
0x1800490ca  mov     ebx, eax
0x1800490cc  test    eax, eax
0x1800490ce  js      short loc_1800490FD
0x1800490d0  mov     rax, [r14]
0x1800490d3  mov     [rsi+310h], r13b
0x1800490da  test    rax, rax
0x1800490dd  jz      short loc_1800490FD
0x1800490df  mov     rcx, [rax]
0x1800490e2  test    rcx, rcx
0x1800490e5  jz      short loc_1800490FD
0x1800490e7  mov     rax, [rcx+18h]
0x1800490eb  test    rax, rax
0x1800490ee  jz      short loc_1800490FD
0x1800490f0  mov     rdx, rdi
0x1800490f3  mov     rcx, r14
0x1800490f6  call    _guard_dispatch_icall
0x1800490fb  mov     ebx, eax
0x1800490fd  mov     rax, [rsi]
0x180049100  mov     rcx, rsi
0x180049103  mov     rax, [rax+30h]
0x180049107  call    _guard_dispatch_icall
0x18004910c  jmp     short loc_18004909C
0x18004910e  sub     ecx, 6
0x180049111  jz      loc_1800493F2
  ... truncated ...
```
