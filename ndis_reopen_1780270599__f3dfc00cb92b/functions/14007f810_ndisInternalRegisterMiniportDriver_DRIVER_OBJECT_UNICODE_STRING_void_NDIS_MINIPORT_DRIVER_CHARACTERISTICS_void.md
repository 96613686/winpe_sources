# ndisInternalRegisterMiniportDriver(_DRIVER_OBJECT *,_UNICODE_STRING *,void *,_NDIS_MINIPORT_DRIVER_CHARACTERISTICS *,void * *)

- ea: `0x14007f810`
- end: `0x14007fed3`
- name: `?ndisInternalRegisterMiniportDriver@@YAHPEAU_DRIVER_OBJECT@@PEAU_UNICODE_STRING@@PEAXPEAU_NDIS_MINIPORT_DRIVER_CHARACTERISTICS@@PEAPEAX@Z`
- size: `1731`
- prototype: `__int64 __usercall@<rax>(struct _DRIVER_OBJECT *@<rcx>, struct _UNICODE_STRING *@<rdx>, void *@<r8>, struct _NDIS_MINIPORT_DRIVER_CHARACTERISTICS *@<r9>, void **)`
- caller_count: `3`
- callee_count: `18`
- tags: `loader_planting, service_task, installer_update`

## callers

- `0x14007f7f0`
- `0x140092ff0`
- `0x140095060`

## callees

- `0x1400110b0`
- `0x140011190`
- `0x140017510`
- `0x1400400d0`
- `0x140053480`
- `0x14007a840`
- `0x14007f500`
- `0x14007f810`
- `0x1400921c4`
- `0x140092d28`
- `0x1400eb460`
- `0x1400eb4c0`
- `0x1400eb7c0`
- `0x14014435c`
- `0x14016f510`
- `0x14016ff10`
- `0x1401701a0`
- `0x140171310`

## import_xrefs

- `ntoskrnl!KeInitializeMutex` at `0x14007f9fe`
- `ntoskrnl!KeInitializeMutex` at `0x14007f9fe`
- `ntoskrnl!IoAllocateDriverObjectExtension` at `0x14007f94a`
- `ntoskrnl!IoAllocateDriverObjectExtension` at `0x14007f94a`
- `ntoskrnl!MmIsDriverVerifying` at `0x14007fa80`
- `ntoskrnl!MmIsDriverVerifying` at `0x14007fa80`
- `ntoskrnl!ObfReferenceObject` at `0x14007fe07`
- `ntoskrnl!ObfReferenceObject` at `0x14007fe07`
- `ntoskrnl!MmIsDriverVerifyingByAddress` at `0x14007fa6f`
- `ntoskrnl!MmIsDriverVerifyingByAddress` at `0x14007fa6f`
- `ntoskrnl!MmUnlockPagableImageSection` at `0x14007fe30`
- `ntoskrnl!MmUnlockPagableImageSection` at `0x14007fe30`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007fca3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007fd80`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007fda1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007fdbb`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007fca3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007fd80`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007fda1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007fdbb`
- `ntoskrnl!KeInitializeEvent` at `0x14007fb9d`
- `ntoskrnl!KeInitializeEvent` at `0x14007fb9d`
- `ntoskrnl!ExAllocatePool2` at `0x14007f917`
- `ntoskrnl!ExAllocatePool2` at `0x14007f917`
- `ntoskrnl!KeReleaseSpinLock` at `0x14007fe1d`
- `ntoskrnl!KeReleaseSpinLock` at `0x14007fe1d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14007fddf`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14007fddf`

## pseudocode

```c
__int64 __fastcall ndisInternalRegisterMiniportDriver(
        struct _DRIVER_OBJECT *a1,
        struct _UNICODE_STRING *a2,
        void *a3,
        struct _NDIS_MINIPORT_DRIVER_CHARACTERISTICS *a4,
        void **a5)
{
  struct _NDIS_M_DRIVER_BLOCK *v6; // rdi
  struct _UNICODE_STRING *v7; // r13
  unsigned int v9; // r15d
  int v10; // edx
  unsigned int v11; // ebx
  _UNICODE_STRING *p_DriverName; // rdx
  ULONG v13; // ebx
  PVOID Pool2; // rax
  __int64 v15; // rdx
  unsigned int *p_Flags; // r13
  struct _UNICODE_STRING *v17; // rdx
  LOGICAL IsDriverVerifyingByAddress; // eax
  struct _NDIS_M_DRIVER_BLOCK *v19; // rax
  __int64 v20; // rcx
  int (__fastcall **MajorFunction)(_DEVICE_OBJECT *, _IRP *); // rax
  __int64 v22; // r8
  void **p_value; // r12
  int v24; // eax
  int v25; // edx
  void (__fastcall ***v26)(void *, _QWORD); // rsi
  void **v27; // rsi
  void (__fastcall ***v28)(void *, _QWORD); // rsi
  _NDIS_MINIPORT_DRIVER_CHARACTERISTICS *value; // rcx
  KIRQL v30; // bl
  PVOID v31; // rcx
  size_t Size; // [rsp+40h] [rbp-71h] BYREF
  PVOID DriverObjectExtension; // [rsp+48h] [rbp-69h] BYREF
  void **v35; // [rsp+50h] [rbp-61h]
  void *v36; // [rsp+58h] [rbp-59h] BYREF
  char v37; // [rsp+60h] [rbp-51h]
  int v38; // [rsp+70h] [rbp-41h] BYREF
  __int64 (__fastcall *v39)(void *, TriageDataArray *); // [rsp+78h] [rbp-39h]
  int v40; // [rsp+80h] [rbp-31h]
  void *v41; // [rsp+88h] [rbp-29h]
  int v42; // [rsp+90h] [rbp-21h]
  void *v43; // [rsp+98h] [rbp-19h]
  int v44; // [rsp+A0h] [rbp-11h]
  void *v45; // [rsp+A8h] [rbp-9h]
  int v46; // [rsp+B0h] [rbp-1h]
  void *v47; // [rsp+B8h] [rbp+7h]
  unsigned int v48; // [rsp+110h] [rbp+5Fh] BYREF
  struct _UNICODE_STRING *v49; // [rsp+118h] [rbp+67h]
  void *v50; // [rsp+120h] [rbp+6Fh]
  unsigned int v51; // [rsp+128h] [rbp+77h] BYREF

  v50 = a3;
  v49 = a2;
  LOBYTE(v6) = 0;
  DriverObjectExtension = 0;
  LODWORD(Size) = 0;
  v7 = a2;
  if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(a2) = 4;
    WPP_RECORDER_SF_q(
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      (int)a2,
      1,
      106,
      (struct _GUID *)&WPP_b0ad62796b5830cbf8ad07ce2f1bab24_Traceguids,
      (char)a1);
  }
  v9 = a4->Flags & 0x20;
  ndisIfEnsureNsiInitialized();
  if ( !a1 && !v9 )
  {
    v11 = -1073741823;
    goto LABEL_65;
  }
  v51 = 0;
  v48 = 0;
  p_DriverName = 0;
  if ( !v9 )
    p_DriverName = &a1->DriverName;
  v11 = ndisValidateMiniportDriverCharacteristicsHeader(a4, p_DriverName, &v51, &v48, (unsigned int *)&Size);
  if ( v11 )
    goto LABEL_65;
  v11 = ndisValidateMiniportDriverCharacteristicsEntryPoints(a4, a1, v51, v48);
  if ( v11 )
    goto LABEL_65;
  v13 = v7->Length + 1194;
  if ( v9 )
  {
    Pool2 = (PVOID)ExAllocatePool2(66, v13, 538985550);
    DriverObjectExtension = Pool2;
    if ( Pool2 )
      goto LABEL_18;
LABEL_16:
    v11 = -1073741670;
    goto LABEL_65;
  }
  v15 = 1313425732;
  if ( (a4->Flags & 1) == 0 )
    v15 = 1313687876;
  if ( IoAllocateDriverObjectExtension(a1, (PVOID)v15, v13, &DriverObjectExtension) < 0 )
    goto LABEL_16;
  Pool2 = DriverObjectExtension;
LABEL_18:
  p_Flags = &a4->Flags;
  memset(Pool2, 0, v13);
  v6 = (struct _NDIS_M_DRIVER_BLOCK *)DriverObjectExtension;
  memset(DriverObjectExtension, 0, 0x4A8u);
  v17 = v49;
  v6->MajorNdisVersion = v51;
  v6->MinorNdisVersion = v48;
  v6->MiniportDriverContext = v50;
  v6->Header = (_NDIS_OBJECT_HEADER)78119170;
  v6->ServiceRegPath.Buffer = (wchar_t *)&v6[1].Header.Type;
  v6->ServiceRegPath.Length = v17->Length;
  v6->ServiceRegPath.MaximumLength = v17->Length + 2;
  memmove(&v6[1], v17->Buffer, v17->Length);
  ndisGetServiceNameFromRegPath(&v6->ServiceRegPath, &v6->ServiceName);
  if ( (a4->Flags & 1) != 0 )
  {
    v6->Flags |= 1u;
    KeInitializeMutex(&v6->IMStartRemoveMutex, 0xFFFFu);
  }
  if ( (*p_Flags & 4) != 0 )
    v6->Flags |= 0x20u;
  memmove(&v6->112, a4, (unsigned int)Size);
  v6->MiniportDriverCharacteristics.MajorNdisVersion = v51;
  v6->MiniportDriverCharacteristics.MinorNdisVersion = v48;
  if ( (*p_Flags & 0x10) != 0 )
    v6->Flags |= 0x40u;
  if ( (a4->Flags & 0x20) != 0 )
    v6->Flags |= 0x80u;
  v6->DriverVersion = a4->MinorDriverVersion | (a4->MajorDriverVersion << 16);
  if ( v9 )
    IsDriverVerifyingByAddress = MmIsDriverVerifyingByAddress(a4->RestartHandler);
  else
    IsDriverVerifyingByAddress = MmIsDriverVerifying(a1);
  if ( IsDriverVerifyingByAddress )
  {
    v6->Flags |= 2u;
    if ( (ndisFlags & 0x400) != 0 )
    {
      v19 = 0;
      if ( !ndisDriverTrackAlloc )
        v19 = v6;
      ndisDriverTrackAlloc = v19;
    }
  }
  v6->MiniportQueue = 0;
  if ( (a4->Flags & 0x30) == 0 )
  {
    v20 = 3;
    MajorFunction = a1->MajorFunction;
    do
    {
      *MajorFunction = (int (__fastcall *)(_DEVICE_OBJECT *, _IRP *))ndisDummyIrpHandler;
      MajorFunction[1] = (int (__fastcall *)(_DEVICE_OBJECT *, _IRP *))ndisDummyIrpHandler;
      MajorFunction[2] = (int (__fastcall *)(_DEVICE_OBJECT *, _IRP *))ndisDummyIrpHandler;
      MajorFunction += 8;
      *(MajorFunction - 5) = (int (__fastcall *)(_DEVICE_OBJECT *, _IRP *))ndisDummyIrpHandler;
      *(MajorFunction - 4) = (int (__fastcall *)(_DEVICE_OBJECT *, _IRP *))ndisDummyIrpHandler;
      *(MajorFunction - 3) = (int (__fastcall *)(_DEVICE_OBJECT *, _IRP *))ndisDummyIrpHandler;
      *(MajorFunction - 2) = (int (__fastcall *)(_DEVICE_OBJECT *, _IRP *))ndisDummyIrpHandler;
      *(MajorFunction - 1) = (int (__fastcall *)(_DEVICE_OBJECT *, _IRP *))ndisDummyIrpHandler;
      --v20;
    }
    while ( v20 );
    *MajorFunction = (int (__fastcall *)(_DEVICE_OBJECT *, _IRP *))ndisDummyIrpHandler;
    MajorFunction[1] = (int (__fastcall *)(_DEVICE_OBJECT *, _IRP *))ndisDummyIrpHandler;
    MajorFunction[2] = (int (__fastcall *)(_DEVICE_OBJECT *, _IRP *))ndisDummyIrpHandler;
    MajorFunction[3] = (int (__fastcall *)(_DEVICE_OBJECT *, _IRP *))ndisDummyIrpHandler;
    a1->DriverExtension->AddDevice = (int (__fastcall *)(_DRIVER_OBJECT *, _DEVICE_OBJECT *))ndisWdmPnPAddDevice;
    a1->DriverUnload = ndisMUnloadEx;
    a1->MajorFunction[0] = (int (__fastcall *)(_DEVICE_OBJECT *, _IRP *))ndisCreateIrpHandler;
    a1->MajorFunction[14] = (int (__fastcall *)(_DEVICE_OBJECT *, _IRP *))ndisDeviceControlIrpHandler;
    a1->MajorFunction[15] = (int (__fastcall *)(_DEVICE_OBJECT *, _IRP *))ndisDeviceInternalIrpDispatch;
    a1->MajorFunction[2] = (int (__fastcall *)(_DEVICE_OBJECT *, _IRP *))ndisCloseIrpHandler;
    a1->MajorFunction[27] = (int (__fastcall *)(_DEVICE_OBJECT *, _IRP *))ndisPnPDispatch;
    a1->MajorFunction[22] = (int (__fastcall *)(_DEVICE_OBJECT *, _IRP *))ndisPowerDispatch;
    a1->MajorFunction[23] = ndisWMIIrpDispatch;
  }
  KeInitializeEvent(&v6->MiniportsRemovedEvent, NotificationEvent, 0);
  v6->DriverObject = a1;
  v6->DeviceList.Blink = &v6->DeviceList;
  v6->DeviceList.Flink = &v6->DeviceList;
  ndisInitializeRef(&v6->Ref, 0xDu);
  p_value = (void **)&v6->Triage.__ptr_.__value_;
  if ( !(unsigned int)Feature_NdisTriageData__private_IsEnabledDeviceUsageNoInline() )
    goto LABEL_52;
  v38 = 1;
  v39 = StructSliceDataCollector<_NDIS_M_DRIVER_BLOCK,0,352>::AddTriageBlocks;
  v40 = 1;
  v41 = &StructFieldDataCollector<_NDIS_M_DRIVER_BLOCK,_UNICODE_STRING,488>::AddTriageBlocks;
  v42 = 1;
  v43 = &UnicodeStringDataCollector<_NDIS_M_DRIVER_BLOCK,488>::AddTriageBlocks;
  v44 = 1;
  v45 = &StructFieldDataCollector<_NDIS_M_DRIVER_BLOCK,_UNICODE_STRING,872>::AddTriageBlocks;
  v47 = &UnicodeStringDataCollector<_NDIS_M_DRIVER_BLOCK,872>::AddTriageBlocks;
  v46 = 1;
  v35 = (void **)&v6->Triage.__ptr_.__value_;
  v36 = 0;
  v37 = 1;
  v24 = ObjectTriageData<_NDIS_M_DRIVER_BLOCK>::Make(v6, &v38, v22, &v36);
  v11 = v24;
  if ( v24 < 0 )
  {
    if ( v24 == -1073741789 )
      v11 = -1073676266;
  }
  else if ( v24 != 259 && v24 != 1076035585 )
  {
    v11 = 0;
  }
  if ( v37 )
  {
    v25 = (int)v35;
    v26 = (void (__fastcall ***)(void *, _QWORD))*v35;
    *v35 = v36;
    if ( v26 )
    {
      (**v26)(v26, 0);
      ExFreePoolWithTag(v26, 0);
    }
  }
  if ( v11 )
  {
    if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v25) = 2;
      WPP_RECORDER_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        v25,
        1,
        107,
        (struct _GUID *)&WPP_b0ad62796b5830cbf8ad07ce2f1bab24_Traceguids,
        (char)v6,
        v11);
    }
    ndisDereferenceDriver(v6, 0, (enum _NDIS_MDRV_REFTAG)255);
  }
  else
  {
LABEL_52:
    v27 = a5;
    *a5 = v6;
    v11 = ndisMInvokeSetOptions(v6);
    if ( v11 )
    {
      ndisDereferenceDriver(v6, 0, (enum _NDIS_MDRV_REFTAG)255);
    }
    else
    {
      if ( a4->OidRequestHandler || v6->CoOidRequestHandler )
      {
        ndisReferencePackage((struct _PKG_REF *)&ndisPkgs);
        v30 = KeAcquireSpinLockRaiseToDpc(&ndisMiniDriverListLock);
        v31 = ndisDriverObject;
        v6->NextDriver = ndisMiniDriverList;
        ndisMiniDriverList = v6;
        ObfReferenceObject(v31);
        KeReleaseSpinLock(&ndisMiniDriverListLock, v30);
        MmUnlockPagableImageSection(ImageSectionHandle);
        _InterlockedDecrement((volatile signed __int32 *)&ndisPkgs);
        ndisQueryDriverImageName(&v6->ServiceName, &v6->ImageName);
        ndisWriteDriverNDISVersionToServiceKey(
          v51,
          v48,
          1,
          a4->MajorDriverVersion,
          a4->MinorDriverVersion,
          &v6->ServiceName);
        v11 = 0;
        goto LABEL_65;
      }
      ndisDereferenceDriver(v6, 0, (enum _NDIS_MDRV_REFTAG)255);
      v11 = -1073676283;
    }
    *v27 = 0;
  }
  v28 = (void (__fastcall ***)(void *, _QWORD))*p_value;
  *p_value = 0;
  if ( v28 )
  {
    (**v28)(v28, 0);
    ExFreePoolWithTag(v28, 0);
  }
  value = v6->UnhookedCharacteristics.__ptr_.__value_;
  v6->UnhookedCharacteristics.__ptr_.__value_ = 0;
  if ( value )
    ExFreePoolWithTag(value, 0);
  if ( v9 )
    ExFreePoolWithTag(v6, 0);
LABEL_65:
  if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v10) = 4;
    WPP_RECORDER_SF_q(
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      v10,
      1,
      108,
      (struct _GUID *)&WPP_b0ad62796b5830cbf8ad07ce2f1bab24_Traceguids,
      (char)v6);
  }
  return v11;
}

```

## disassembly

```asm
0x14007f810  mov     [rsp-8+arg_10], r8
0x14007f815  mov     [rsp-8+arg_8], rdx
0x14007f81a  push    rbp
0x14007f81b  push    rbx
0x14007f81c  push    rsi
0x14007f81d  push    rdi
0x14007f81e  push    r12
0x14007f820  push    r13
0x14007f822  push    r14
0x14007f824  push    r15
0x14007f826  lea     rbp, [rsp-17h]
0x14007f82b  sub     rsp, 0C8h
0x14007f832  xor     ebx, ebx
0x14007f834  mov     r14, r9
0x14007f837  mov     edi, ebx
0x14007f839  mov     [rbp+4Fh+DriverObjectExtension], rbx
0x14007f83d  mov     dword ptr [rbp+4Fh+Size], ebx
0x14007f840  mov     r13, rdx
0x14007f843  mov     rsi, rcx
0x14007f846  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14007f84d  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14007f854  lea     rcx, WPP_b0ad62796b5830cbf8ad07ce2f1bab24_Traceguids
0x14007f85b  jz      short loc_14007F885
0x14007f85d  mov     [rsp+100h+var_D8], rsi; char
0x14007f862  mov     r9d, 6Ah ; 'j'; int
0x14007f868  mov     [rsp+100h+var_E0], rcx; struct _GUID *
0x14007f86d  mov     r8d, 1; int
0x14007f873  mov     rcx, cs:WPP_GLOBAL_Control
0x14007f87a  mov     dl, 4; int
0x14007f87c  mov     rcx, [rcx+40h]; int
0x14007f880  call    WPP_RECORDER_SF_q
0x14007f885  mov     r15d, [r14+8]
0x14007f889  and     r15d, 20h
0x14007f88d  call    ?ndisIfEnsureNsiInitialized@@YAJXZ; ndisIfEnsureNsiInitialized(void)
0x14007f892  test    rsi, rsi
0x14007f895  jnz     short loc_14007F8A6
0x14007f897  test    r15d, r15d
0x14007f89a  jnz     short loc_14007F8A6
0x14007f89c  mov     ebx, 0C0000001h
0x14007f8a1  jmp     loc_14007FE7D
0x14007f8a6  lea     rax, [rsi+38h]
0x14007f8aa  mov     [rbp+4Fh+arg_18], ebx
0x14007f8ad  test    r15d, r15d
0x14007f8b0  mov     [rbp+4Fh+arg_0], ebx
0x14007f8b3  mov     rdx, rbx
0x14007f8b6  lea     r9, [rbp+4Fh+arg_0]; unsigned int *
0x14007f8ba  cmovz   rdx, rax; struct _UNICODE_STRING *
0x14007f8be  lea     r8, [rbp+4Fh+arg_18]; unsigned int *
0x14007f8c2  lea     rax, [rbp+4Fh+Size]
0x14007f8c6  mov     rcx, r14; struct _NDIS_MINIPORT_DRIVER_CHARACTERISTICS *
0x14007f8c9  mov     [rsp+100h+var_E0], rax; unsigned int *
0x14007f8ce  call    ?ndisValidateMiniportDriverCharacteristicsHeader@@YAHPEBU_NDIS_MINIPORT_DRIVER_CHARACTERISTICS@@PEBU_UNICODE_STRING@@PEAK22@Z; ndisValidateMiniportDriverCharacteristicsHeader(_NDIS_MINIPORT_DRIVER_CHARACTERISTICS const *,_UNICODE_STRING const *,ulong *,ulong *,ulong *)
0x14007f8d3  mov     ebx, eax
0x14007f8d5  test    eax, eax
0x14007f8d7  jnz     loc_14007FE7D
0x14007f8dd  mov     r9d, [rbp+4Fh+arg_0]; unsigned int
0x14007f8e1  mov     rdx, rsi; struct _DRIVER_OBJECT *
0x14007f8e4  mov     r8d, [rbp+4Fh+arg_18]; unsigned int
0x14007f8e8  mov     rcx, r14; struct _NDIS_MINIPORT_DRIVER_CHARACTERISTICS *
0x14007f8eb  call    ?ndisValidateMiniportDriverCharacteristicsEntryPoints@@YAHPEAU_NDIS_MINIPORT_DRIVER_CHARACTERISTICS@@PEAU_DRIVER_OBJECT@@KK@Z; ndisValidateMiniportDriverCharacteristicsEntryPoints(_NDIS_MINIPORT_DRIVER_CHARACTERISTICS *,_DRIVER_OBJECT *,ulong,ulong)
0x14007f8f0  mov     ebx, eax
0x14007f8f2  test    eax, eax
0x14007f8f4  jnz     loc_14007FE7D
0x14007f8fa  movzx   ebx, word ptr [r13+0]
0x14007f8ff  add     ebx, 4AAh
0x14007f905  test    r15d, r15d
0x14007f908  jz      short loc_14007F92E
0x14007f90a  mov     edx, ebx
0x14007f90c  mov     ecx, 42h ; 'B'
0x14007f911  mov     r8d, 2020444Eh
0x14007f917  call    cs:__imp_ExAllocatePool2
0x14007f91e  nop     dword ptr [rax+rax+00h]
0x14007f923  mov     [rbp+4Fh+DriverObjectExtension], rax
0x14007f927  test    rax, rax
0x14007f92a  jz      short loc_14007F95A
0x14007f92c  jmp     short loc_14007F968
0x14007f92e  mov     eax, [r14+8]
0x14007f932  lea     r9, [rbp+4Fh+DriverObjectExtension]; DriverObjectExtension
0x14007f936  mov     r8d, ebx; DriverObjectExtensionSize
0x14007f939  mov     rcx, rsi; DriverObject
0x14007f93c  mov     edx, 4E494944h
0x14007f941  test    al, 1
0x14007f943  jnz     short loc_14007F94A
0x14007f945  mov     edx, 4E4D4944h; ClientIdentificationAddress
0x14007f94a  call    cs:__imp_IoAllocateDriverObjectExtension
0x14007f951  nop     dword ptr [rax+rax+00h]
0x14007f956  test    eax, eax
0x14007f958  jns     short loc_14007F964
0x14007f95a  mov     ebx, 0C000009Ah
0x14007f95f  jmp     loc_14007FE7D
0x14007f964  mov     rax, [rbp+4Fh+DriverObjectExtension]
0x14007f968  mov     r8d, ebx; Size
0x14007f96b  lea     r13, [r14+8]
0x14007f96f  xor     edx, edx; Val
0x14007f971  mov     rcx, rax; void *
0x14007f974  call    memset
0x14007f979  mov     rdi, [rbp+4Fh+DriverObjectExtension]
0x14007f97d  xor     edx, edx; Val
0x14007f97f  mov     rcx, rdi; void *
0x14007f982  mov     r8d, 4A8h; Size
0x14007f988  call    memset
0x14007f98d  mov     rdx, [rbp+4Fh+arg_8]
0x14007f991  lea     rcx, [rdi+4A8h]; void *
0x14007f998  mov     eax, [rbp+4Fh+arg_18]
0x14007f99b  mov     [rdi+18h], al
0x14007f99e  mov     eax, [rbp+4Fh+arg_0]
0x14007f9a1  mov     [rdi+19h], al
0x14007f9a4  mov     rax, [rbp+4Fh+arg_10]
0x14007f9a8  mov     [rdi+40h], rax
0x14007f9ac  mov     dword ptr [rdi], 4A80102h
0x14007f9b2  mov     [rdi+38h], rcx
0x14007f9b6  movzx   eax, word ptr [rdx]
0x14007f9b9  mov     [rdi+30h], ax
0x14007f9bd  movzx   eax, word ptr [rdx]
0x14007f9c0  add     ax, 2
0x14007f9c4  mov     [rdi+32h], ax
0x14007f9c8  movzx   r8d, word ptr [rdx]; Size
0x14007f9cc  mov     rdx, [rdx+8]; Src
0x14007f9d0  call    memmove
0x14007f9d5  lea     rdx, [rdi+1E8h]; struct _UNICODE_STRING *
0x14007f9dc  lea     rcx, [rdi+30h]; struct _UNICODE_STRING *
0x14007f9e0  call    ?ndisGetServiceNameFromRegPath@@YAXPEAU_UNICODE_STRING@@0@Z; ndisGetServiceNameFromRegPath(_UNICODE_STRING *,_UNICODE_STRING *)
0x14007f9e5  mov     eax, [r13+0]
0x14007f9e9  test    al, 1
0x14007f9eb  jz      short loc_14007FA0A
0x14007f9ed  or      word ptr [rdi+1Ah], 1
0x14007f9f2  lea     rcx, [rdi+1A0h]; Mutex
0x14007f9f9  mov     edx, 0FFFFh; Level
0x14007f9fe  call    cs:__imp_KeInitializeMutex
0x14007fa05  nop     dword ptr [rax+rax+00h]
0x14007fa0a  mov     eax, [r13+0]
0x14007fa0e  test    al, 4
0x14007fa10  jz      short loc_14007FA17
0x14007fa12  or      word ptr [rdi+1Ah], 20h
0x14007fa17  mov     r8d, dword ptr [rbp+4Fh+Size]; Size
0x14007fa1b  lea     rcx, [rdi+70h]; void *
0x14007fa1f  mov     rdx, r14; Src
0x14007fa22  call    memmove
0x14007fa27  mov     eax, [rbp+4Fh+arg_18]
0x14007fa2a  mov     [rdi+74h], al
0x14007fa2d  mov     eax, [rbp+4Fh+arg_0]
0x14007fa30  mov     [rdi+75h], al
0x14007fa33  mov     eax, [r13+0]
0x14007fa37  test    al, 10h
0x14007fa39  jz      short loc_14007FA40
0x14007fa3b  or      word ptr [rdi+1Ah], 40h
0x14007fa40  mov     eax, [r14+8]
0x14007fa44  test    al, 20h
0x14007fa46  jz      short loc_14007FA51
0x14007fa48  mov     eax, 80h
0x14007fa4d  or      [rdi+1Ah], ax
0x14007fa51  movzx   ecx, byte ptr [r14+6]
0x14007fa56  movzx   eax, byte ptr [r14+7]
0x14007fa5b  shl     ecx, 10h
0x14007fa5e  or      ecx, eax
0x14007fa60  mov     [rdi+1E0h], ecx
0x14007fa66  test    r15d, r15d
0x14007fa69  jz      short loc_14007FA7D
0x14007fa6b  mov     rcx, [r14+38h]; AddressWithinSection
0x14007fa6f  call    cs:__imp_MmIsDriverVerifyingByAddress
0x14007fa76  nop     dword ptr [rax+rax+00h]
0x14007fa7b  jmp     short loc_14007FA8C
0x14007fa7d  mov     rcx, rsi; DriverObject
0x14007fa80  call    cs:__imp_MmIsDriverVerifying
0x14007fa87  nop     dword ptr [rax+rax+00h]
0x14007fa8c  xor     r13d, r13d
0x14007fa8f  test    eax, eax
0x14007fa91  jz      short loc_14007FAB9
0x14007fa93  or      word ptr [rdi+1Ah], 2
0x14007fa98  test    cs:?ndisFlags@@3JA, 400h; long ndisFlags
0x14007faa2  jz      short loc_14007FAB9
0x14007faa4  cmp     cs:?ndisDriverTrackAlloc@@3PEAU_NDIS_M_DRIVER_BLOCK@@EA, r13; _NDIS_M_DRIVER_BLOCK * ndisDriverTrackAlloc
0x14007faab  mov     eax, r13d
0x14007faae  cmovz   rax, rdi
0x14007fab2  mov     cs:?ndisDriverTrackAlloc@@3PEAU_NDIS_M_DRIVER_BLOCK@@EA, rax; _NDIS_M_DRIVER_BLOCK * ndisDriverTrackAlloc
0x14007fab9  mov     [rdi+10h], r13
0x14007fabd  mov     eax, [r14+8]
0x14007fac1  test    al, 30h
0x14007fac3  jnz     loc_14007FB91
0x14007fac9  lea     r8, ?ndisDummyIrpHandler@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z; ndisDummyIrpHandler(_DEVICE_OBJECT *,_IRP *)
0x14007fad0  mov     ecx, 3
0x14007fad5  lea     rax, [rsi+70h]
0x14007fad9  nop     dword ptr [rax+00000000h]
0x14007fae0  mov     [rax], r8
0x14007fae3  mov     [rax+8], r8
0x14007fae7  mov     [rax+10h], r8
0x14007faeb  lea     rax, [rax+40h]
0x14007faef  mov     [rax-28h], r8
0x14007faf3  mov     [rax-20h], r8
0x14007faf7  mov     [rax-18h], r8
0x14007fafb  mov     [rax-10h], r8
0x14007faff  mov     [rax-8], r8
0x14007fb03  sub     rcx, 1
0x14007fb07  jnz     short loc_14007FAE0
0x14007fb09  mov     [rax], r8
0x14007fb0c  lea     rcx, ?ndisWdmPnPAddDevice@@YAJPEAU_DRIVER_OBJECT@@PEAU_DEVICE_OBJECT@@@Z; ndisWdmPnPAddDevice(_DRIVER_OBJECT *,_DEVICE_OBJECT *)
0x14007fb13  mov     [rax+8], r8
0x14007fb17  mov     [rax+10h], r8
0x14007fb1b  mov     [rax+18h], r8
0x14007fb1f  mov     rax, [rsi+30h]
0x14007fb23  mov     [rax+8], rcx
0x14007fb27  lea     rax, ?ndisMUnloadEx@@YAXPEAU_DRIVER_OBJECT@@@Z; ndisMUnloadEx(_DRIVER_OBJECT *)
0x14007fb2e  mov     [rsi+68h], rax
0x14007fb32  lea     rax, ?ndisCreateIrpHandler@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z; ndisCreateIrpHandler(_DEVICE_OBJECT *,_IRP *)
0x14007fb39  mov     [rsi+70h], rax
0x14007fb3d  lea     rax, ?ndisDeviceControlIrpHandler@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z; ndisDeviceControlIrpHandler(_DEVICE_OBJECT *,_IRP *)
0x14007fb44  mov     [rsi+0E0h], rax
0x14007fb4b  lea     rax, ?ndisDeviceInternalIrpDispatch@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z; ndisDeviceInternalIrpDispatch(_DEVICE_OBJECT *,_IRP *)
0x14007fb52  mov     [rsi+0E8h], rax
0x14007fb59  lea     rax, ?ndisCloseIrpHandler@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z; ndisCloseIrpHandler(_DEVICE_OBJECT *,_IRP *)
0x14007fb60  mov     [rsi+80h], rax
0x14007fb67  lea     rax, ?ndisPnPDispatch@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z; ndisPnPDispatch(_DEVICE_OBJECT *,_IRP *)
0x14007fb6e  mov     [rsi+148h], rax
0x14007fb75  lea     rax, ?ndisPowerDispatch@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z; ndisPowerDispatch(_DEVICE_OBJECT *,_IRP *)
0x14007fb7c  mov     [rsi+120h], rax
0x14007fb83  lea     rax, ?ndisWMIIrpDispatch@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z; ndisWMIIrpDispatch(_DEVICE_OBJECT *,_IRP *)
0x14007fb8a  mov     [rsi+128h], rax
0x14007fb91  lea     rcx, [rdi+170h]; Event
0x14007fb98  xor     r8d, r8d; State
0x14007fb9b  xor     edx, edx; Type
0x14007fb9d  call    cs:__imp_KeInitializeEvent
0x14007fba4  nop     dword ptr [rax+rax+00h]
0x14007fba9  lea     rax, [rdi+50h]
0x14007fbad  mov     [rdi+28h], rsi
0x14007fbb1  lea     rcx, [rdi+188h]; struct _REFERENCE_EX *
0x14007fbb8  mov     [rax+8], rax
0x14007fbbc  mov     dl, 0Dh; unsigned __int8
0x14007fbbe  mov     [rax], rax
0x14007fbc1  call    ?ndisInitializeRef@@YAXPEAU_REFERENCE_EX@@E@Z; ndisInitializeRef(_REFERENCE_EX *,uchar)
0x14007fbc6  call    Feature_NdisTriageData__private_IsEnabledDeviceUsageNoInline
0x14007fbcb  lea     r12, [rdi+4A0h]
0x14007fbd2  test    eax, eax
0x14007fbd4  jz      loc_14007FD05
0x14007fbda  lea     rax, ?AddTriageBlocks@?$StructSliceDataCollector@U_NDIS_M_DRIVER_BLOCK@@$0A@$0BGA@@@SAXPEAU_NDIS_M_DRIVER_BLOCK@@PEAVTriageDataArray@@PEBUBugcheckParameters@@@Z; StructSliceDataCollector<_NDIS_M_DRIVER_BLOCK,0,352>::AddTriageBlocks(_NDIS_M_DRIVER_BLOCK *,TriageDataArray *,BugcheckParameters const *)
0x14007fbe1  mov     [rbp+4Fh+var_90], 1
0x14007fbe8  mov     [rbp+4Fh+var_88], rax
0x14007fbec  lea     r9, [rbp+4Fh+var_A8]
0x14007fbf0  lea     rax, ?AddTriageBlocks@?$StructFieldDataCollector@U_NDIS_M_DRIVER_BLOCK@@U_UNICODE_STRING@@$0BOI@@@SAXPEAU_NDIS_M_DRIVER_BLOCK@@PEAVTriageDataArray@@PEBUBugcheckParameters@@@Z; StructFieldDataCollector<_NDIS_M_DRIVER_BLOCK,_UNICODE_STRING,488>::AddTriageBlocks(_NDIS_M_DRIVER_BLOCK *,TriageDataArray *,BugcheckParameters const *)
0x14007fbf7  mov     [rbp+4Fh+var_80], 1
0x14007fbfe  mov     [rbp+4Fh+var_78], rax
0x14007fc02  lea     rdx, [rbp+4Fh+var_90]
0x14007fc06  lea     rax, ?AddTriageBlocks@?$UnicodeStringDataCollector@U_NDIS_M_DRIVER_BLOCK@@$0BOI@@@SAXPEAU_NDIS_M_DRIVER_BLOCK@@PEAVTriageDataArray@@PEBUBugcheckParameters@@@Z; UnicodeStringDataCollector<_NDIS_M_DRIVER_BLOCK,488>::AddTriageBlocks(_NDIS_M_DRIVER_BLOCK *,TriageDataArray *,BugcheckParameters const *)
0x14007fc0d  mov     [rbp+4Fh+var_70], 1
0x14007fc14  mov     [rbp+4Fh+var_68], rax
0x14007fc18  mov     rcx, rdi
0x14007fc1b  lea     rax, ?AddTriageBlocks@?$StructFieldDataCollector@U_NDIS_M_DRIVER_BLOCK@@U_UNICODE_STRING@@$0DGI@@@SAXPEAU_NDIS_M_DRIVER_BLOCK@@PEAVTriageDataArray@@PEBUBugcheckParameters@@@Z; StructFieldDataCollector<_NDIS_M_DRIVER_BLOCK,_UNICODE_STRING,872>::AddTriageBlocks(_NDIS_M_DRIVER_BLOCK *,TriageDataArray *,BugcheckParameters const *)
0x14007fc22  mov     [rbp+4Fh+var_60], 1
0x14007fc29  mov     [rbp+4Fh+var_58], rax
0x14007fc2d  lea     rax, ?AddTriageBlocks@?$UnicodeStringDataCollector@U_NDIS_M_DRIVER_BLOCK@@$0DGI@@@SAXPEAU_NDIS_M_DRIVER_BLOCK@@PEAVTriageDataArray@@PEBUBugcheckParameters@@@Z; UnicodeStringDataCollector<_NDIS_M_DRIVER_BLOCK,872>::AddTriageBlocks(_NDIS_M_DRIVER_BLOCK *,TriageDataArray *,BugcheckParameters const *)
0x14007fc34  mov     [rbp+4Fh+var_48], rax
0x14007fc38  mov     [rbp+4Fh+var_50], 1
0x14007fc3f  mov     [rbp+4Fh+var_B0], r12
0x14007fc43  mov     [rbp+4Fh+var_A8], r13
0x14007fc47  mov     [rbp+4Fh+var_A0], 1
0x14007fc4b  call    ?Make@?$ObjectTriageData@U_NDIS_M_DRIVER_BLOCK@@@@SAJPEAU_NDIS_M_DRIVER_BLOCK@@PEBU?$TriageDataCollector@U_NDIS_M_DRIVER_BLOCK@@@@_KPEAPEAVTriageData@@@Z; ObjectTriageData<_NDIS_M_DRIVER_BLOCK>::Make(_NDIS_M_DRIVER_BLOCK *,TriageDataCollector<_NDIS_M_DRIVER_BLOCK> const *,unsigned __int64,TriageData * *)
0x14007fc50  mov     ebx, eax
0x14007fc52  test    eax, eax
0x14007fc54  js      short loc_14007FC69
0x14007fc56  cmp     eax, 103h
0x14007fc5b  jz      short loc_14007FC75
0x14007fc5d  cmp     eax, 40230001h
0x14007fc62  jz      short loc_14007FC75
0x14007fc64  mov     ebx, r13d
0x14007fc67  jmp     short loc_14007FC75
0x14007fc69  cmp     eax, 0C0000023h
0x14007fc6e  jnz     short loc_14007FC75
0x14007fc70  mov     ebx, 0C0010016h
0x14007fc75  cmp     [rbp+4Fh+var_A0], 0
0x14007fc79  jz      short loc_14007FCAF
0x14007fc7b  mov     rdx, [rbp+4Fh+var_B0]
0x14007fc7f  mov     rax, [rbp+4Fh+var_A8]
0x14007fc83  mov     rsi, [rdx]
0x14007fc86  mov     [rdx], rax
0x14007fc89  test    rsi, rsi
0x14007fc8c  jz      short loc_14007FCAF
0x14007fc8e  mov     rax, [rsi]
0x14007fc91  xor     edx, edx
0x14007fc93  mov     rcx, rsi
0x14007fc96  mov     rax, [rax]
0x14007fc99  call    _guard_dispatch_icall
0x14007fc9e  xor     edx, edx; Tag
0x14007fca0  mov     rcx, rsi; P
0x14007fca3  call    cs:__imp_ExFreePoolWithTag
0x14007fcaa  nop     dword ptr [rax+rax+00h]
0x14007fcaf  test    ebx, ebx
0x14007fcb1  jz      short loc_14007FD05
0x14007fcb3  lea     r14, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14007fcba  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14007fcc1  jz      short loc_14007FCF6
0x14007fcc3  mov     rcx, cs:WPP_GLOBAL_Control
0x14007fcca  lea     rax, WPP_b0ad62796b5830cbf8ad07ce2f1bab24_Traceguids
0x14007fcd1  mov     dword ptr [rsp+100h+var_D0], ebx; char
0x14007fcd5  mov     r9d, 6Bh ; 'k'; int
0x14007fcdb  mov     [rsp+100h+var_D8], rdi; char
0x14007fce0  mov     r8d, 1; int
0x14007fce6  mov     dl, 2; int
0x14007fce8  mov     [rsp+100h+var_E0], rax; struct _GUID *
0x14007fced  mov     rcx, [rcx+40h]; int
0x14007fcf1  call    WPP_RECORDER_SF_qD
0x14007fcf6  mov     r8b, 0FFh; enum _NDIS_MDRV_REFTAG
  ... truncated ...
```
