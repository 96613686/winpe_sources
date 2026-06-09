# ndisInternalRegisterMiniportDriver(_DRIVER_OBJECT *,_UNICODE_STRING *,void *,_NDIS_MINIPORT_DRIVER_CHARACTERISTICS *,void * *)

- ea: `0x14007a070`
- end: `0x14007a733`
- name: `?ndisInternalRegisterMiniportDriver@@YAHPEAU_DRIVER_OBJECT@@PEAU_UNICODE_STRING@@PEAXPEAU_NDIS_MINIPORT_DRIVER_CHARACTERISTICS@@PEAPEAX@Z`
- size: `1731`
- prototype: `__int64 __usercall@<rax>(struct _DRIVER_OBJECT *@<rcx>, struct _UNICODE_STRING *@<rdx>, void *@<r8>, struct _NDIS_MINIPORT_DRIVER_CHARACTERISTICS *@<r9>, void **)`
- caller_count: `3`
- callee_count: `18`
- tags: `loader_planting, service_task, installer_update`

## callers

- `0x14007a050`
- `0x14008e5b0`
- `0x140090620`

## callees

- `0x14001cf50`
- `0x14001d030`
- `0x1400233b0`
- `0x14003d920`
- `0x14004e250`
- `0x140075160`
- `0x140079e30`
- `0x14007a070`
- `0x14008d784`
- `0x14008e2e8`
- `0x1400e6240`
- `0x1400e62c0`
- `0x1400e65c0`
- `0x14013d3bc`
- `0x140168620`
- `0x140169020`
- `0x1401692b0`
- `0x14016a420`

## import_xrefs

- `ntoskrnl!KeInitializeMutex` at `0x14007a25e`
- `ntoskrnl!KeInitializeMutex` at `0x14007a25e`
- `ntoskrnl!IoAllocateDriverObjectExtension` at `0x14007a1aa`
- `ntoskrnl!IoAllocateDriverObjectExtension` at `0x14007a1aa`
- `ntoskrnl!MmIsDriverVerifying` at `0x14007a2e0`
- `ntoskrnl!MmIsDriverVerifying` at `0x14007a2e0`
- `ntoskrnl!ObfReferenceObject` at `0x14007a667`
- `ntoskrnl!ObfReferenceObject` at `0x14007a667`
- `ntoskrnl!MmIsDriverVerifyingByAddress` at `0x14007a2cf`
- `ntoskrnl!MmIsDriverVerifyingByAddress` at `0x14007a2cf`
- `ntoskrnl!MmUnlockPagableImageSection` at `0x14007a690`
- `ntoskrnl!MmUnlockPagableImageSection` at `0x14007a690`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007a503`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007a5e0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007a601`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007a61b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007a503`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007a5e0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007a601`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007a61b`
- `ntoskrnl!KeInitializeEvent` at `0x14007a3fd`
- `ntoskrnl!KeInitializeEvent` at `0x14007a3fd`
- `ntoskrnl!ExAllocatePool2` at `0x14007a177`
- `ntoskrnl!ExAllocatePool2` at `0x14007a177`
- `ntoskrnl!KeReleaseSpinLock` at `0x14007a67d`
- `ntoskrnl!KeReleaseSpinLock` at `0x14007a67d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14007a63f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14007a63f`

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
    a1->MajorFunction[23] = (int (__fastcall *)(_DEVICE_OBJECT *, _IRP *))ndisWMIIrpDispatch;
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
0x14007a070  mov     [rsp-8+arg_10], r8
0x14007a075  mov     [rsp-8+arg_8], rdx
0x14007a07a  push    rbp
0x14007a07b  push    rbx
0x14007a07c  push    rsi
0x14007a07d  push    rdi
0x14007a07e  push    r12
0x14007a080  push    r13
0x14007a082  push    r14
0x14007a084  push    r15
0x14007a086  lea     rbp, [rsp-17h]
0x14007a08b  sub     rsp, 0C8h
0x14007a092  xor     ebx, ebx
0x14007a094  mov     r14, r9
0x14007a097  mov     edi, ebx
0x14007a099  mov     [rbp+4Fh+DriverObjectExtension], rbx
0x14007a09d  mov     dword ptr [rbp+4Fh+Size], ebx
0x14007a0a0  mov     r13, rdx
0x14007a0a3  mov     rsi, rcx
0x14007a0a6  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14007a0ad  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14007a0b4  lea     rcx, WPP_b0ad62796b5830cbf8ad07ce2f1bab24_Traceguids
0x14007a0bb  jz      short loc_14007A0E5
0x14007a0bd  mov     [rsp+100h+var_D8], rsi; char
0x14007a0c2  mov     r9d, 6Ah ; 'j'; int
0x14007a0c8  mov     [rsp+100h+var_E0], rcx; struct _GUID *
0x14007a0cd  mov     r8d, 1; int
0x14007a0d3  mov     rcx, cs:WPP_GLOBAL_Control
0x14007a0da  mov     dl, 4; int
0x14007a0dc  mov     rcx, [rcx+40h]; int
0x14007a0e0  call    WPP_RECORDER_SF_q
0x14007a0e5  mov     r15d, [r14+8]
0x14007a0e9  and     r15d, 20h
0x14007a0ed  call    ?ndisIfEnsureNsiInitialized@@YAJXZ; ndisIfEnsureNsiInitialized(void)
0x14007a0f2  test    rsi, rsi
0x14007a0f5  jnz     short loc_14007A106
0x14007a0f7  test    r15d, r15d
0x14007a0fa  jnz     short loc_14007A106
0x14007a0fc  mov     ebx, 0C0000001h
0x14007a101  jmp     loc_14007A6DD
0x14007a106  lea     rax, [rsi+38h]
0x14007a10a  mov     [rbp+4Fh+arg_18], ebx
0x14007a10d  test    r15d, r15d
0x14007a110  mov     [rbp+4Fh+arg_0], ebx
0x14007a113  mov     rdx, rbx
0x14007a116  lea     r9, [rbp+4Fh+arg_0]; unsigned int *
0x14007a11a  cmovz   rdx, rax; struct _UNICODE_STRING *
0x14007a11e  lea     r8, [rbp+4Fh+arg_18]; unsigned int *
0x14007a122  lea     rax, [rbp+4Fh+Size]
0x14007a126  mov     rcx, r14; struct _NDIS_MINIPORT_DRIVER_CHARACTERISTICS *
0x14007a129  mov     [rsp+100h+var_E0], rax; unsigned int *
0x14007a12e  call    ?ndisValidateMiniportDriverCharacteristicsHeader@@YAHPEBU_NDIS_MINIPORT_DRIVER_CHARACTERISTICS@@PEBU_UNICODE_STRING@@PEAK22@Z; ndisValidateMiniportDriverCharacteristicsHeader(_NDIS_MINIPORT_DRIVER_CHARACTERISTICS const *,_UNICODE_STRING const *,ulong *,ulong *,ulong *)
0x14007a133  mov     ebx, eax
0x14007a135  test    eax, eax
0x14007a137  jnz     loc_14007A6DD
0x14007a13d  mov     r9d, [rbp+4Fh+arg_0]; unsigned int
0x14007a141  mov     rdx, rsi; struct _DRIVER_OBJECT *
0x14007a144  mov     r8d, [rbp+4Fh+arg_18]; unsigned int
0x14007a148  mov     rcx, r14; struct _NDIS_MINIPORT_DRIVER_CHARACTERISTICS *
0x14007a14b  call    ?ndisValidateMiniportDriverCharacteristicsEntryPoints@@YAHPEAU_NDIS_MINIPORT_DRIVER_CHARACTERISTICS@@PEAU_DRIVER_OBJECT@@KK@Z; ndisValidateMiniportDriverCharacteristicsEntryPoints(_NDIS_MINIPORT_DRIVER_CHARACTERISTICS *,_DRIVER_OBJECT *,ulong,ulong)
0x14007a150  mov     ebx, eax
0x14007a152  test    eax, eax
0x14007a154  jnz     loc_14007A6DD
0x14007a15a  movzx   ebx, word ptr [r13+0]
0x14007a15f  add     ebx, 4AAh
0x14007a165  test    r15d, r15d
0x14007a168  jz      short loc_14007A18E
0x14007a16a  mov     edx, ebx
0x14007a16c  mov     ecx, 42h ; 'B'
0x14007a171  mov     r8d, 2020444Eh
0x14007a177  call    cs:__imp_ExAllocatePool2
0x14007a17e  nop     dword ptr [rax+rax+00h]
0x14007a183  mov     [rbp+4Fh+DriverObjectExtension], rax
0x14007a187  test    rax, rax
0x14007a18a  jz      short loc_14007A1BA
0x14007a18c  jmp     short loc_14007A1C8
0x14007a18e  mov     eax, [r14+8]
0x14007a192  lea     r9, [rbp+4Fh+DriverObjectExtension]; DriverObjectExtension
0x14007a196  mov     r8d, ebx; DriverObjectExtensionSize
0x14007a199  mov     rcx, rsi; DriverObject
0x14007a19c  mov     edx, 4E494944h
0x14007a1a1  test    al, 1
0x14007a1a3  jnz     short loc_14007A1AA
0x14007a1a5  mov     edx, 4E4D4944h; ClientIdentificationAddress
0x14007a1aa  call    cs:__imp_IoAllocateDriverObjectExtension
0x14007a1b1  nop     dword ptr [rax+rax+00h]
0x14007a1b6  test    eax, eax
0x14007a1b8  jns     short loc_14007A1C4
0x14007a1ba  mov     ebx, 0C000009Ah
0x14007a1bf  jmp     loc_14007A6DD
0x14007a1c4  mov     rax, [rbp+4Fh+DriverObjectExtension]
0x14007a1c8  mov     r8d, ebx; Size
0x14007a1cb  lea     r13, [r14+8]
0x14007a1cf  xor     edx, edx; Val
0x14007a1d1  mov     rcx, rax; void *
0x14007a1d4  call    memset
0x14007a1d9  mov     rdi, [rbp+4Fh+DriverObjectExtension]
0x14007a1dd  xor     edx, edx; Val
0x14007a1df  mov     rcx, rdi; void *
0x14007a1e2  mov     r8d, 4A8h; Size
0x14007a1e8  call    memset
0x14007a1ed  mov     rdx, [rbp+4Fh+arg_8]
0x14007a1f1  lea     rcx, [rdi+4A8h]; void *
0x14007a1f8  mov     eax, [rbp+4Fh+arg_18]
0x14007a1fb  mov     [rdi+18h], al
0x14007a1fe  mov     eax, [rbp+4Fh+arg_0]
0x14007a201  mov     [rdi+19h], al
0x14007a204  mov     rax, [rbp+4Fh+arg_10]
0x14007a208  mov     [rdi+40h], rax
0x14007a20c  mov     dword ptr [rdi], 4A80102h
0x14007a212  mov     [rdi+38h], rcx
0x14007a216  movzx   eax, word ptr [rdx]
0x14007a219  mov     [rdi+30h], ax
0x14007a21d  movzx   eax, word ptr [rdx]
0x14007a220  add     ax, 2
0x14007a224  mov     [rdi+32h], ax
0x14007a228  movzx   r8d, word ptr [rdx]; Size
0x14007a22c  mov     rdx, [rdx+8]; Src
0x14007a230  call    memmove
0x14007a235  lea     rdx, [rdi+1E8h]; struct _UNICODE_STRING *
0x14007a23c  lea     rcx, [rdi+30h]; struct _UNICODE_STRING *
0x14007a240  call    ?ndisGetServiceNameFromRegPath@@YAXPEAU_UNICODE_STRING@@0@Z; ndisGetServiceNameFromRegPath(_UNICODE_STRING *,_UNICODE_STRING *)
0x14007a245  mov     eax, [r13+0]
0x14007a249  test    al, 1
0x14007a24b  jz      short loc_14007A26A
0x14007a24d  or      word ptr [rdi+1Ah], 1
0x14007a252  lea     rcx, [rdi+1A0h]; Mutex
0x14007a259  mov     edx, 0FFFFh; Level
0x14007a25e  call    cs:__imp_KeInitializeMutex
0x14007a265  nop     dword ptr [rax+rax+00h]
0x14007a26a  mov     eax, [r13+0]
0x14007a26e  test    al, 4
0x14007a270  jz      short loc_14007A277
0x14007a272  or      word ptr [rdi+1Ah], 20h
0x14007a277  mov     r8d, dword ptr [rbp+4Fh+Size]; Size
0x14007a27b  lea     rcx, [rdi+70h]; void *
0x14007a27f  mov     rdx, r14; Src
0x14007a282  call    memmove
0x14007a287  mov     eax, [rbp+4Fh+arg_18]
0x14007a28a  mov     [rdi+74h], al
0x14007a28d  mov     eax, [rbp+4Fh+arg_0]
0x14007a290  mov     [rdi+75h], al
0x14007a293  mov     eax, [r13+0]
0x14007a297  test    al, 10h
0x14007a299  jz      short loc_14007A2A0
0x14007a29b  or      word ptr [rdi+1Ah], 40h
0x14007a2a0  mov     eax, [r14+8]
0x14007a2a4  test    al, 20h
0x14007a2a6  jz      short loc_14007A2B1
0x14007a2a8  mov     eax, 80h
0x14007a2ad  or      [rdi+1Ah], ax
0x14007a2b1  movzx   ecx, byte ptr [r14+6]
0x14007a2b6  movzx   eax, byte ptr [r14+7]
0x14007a2bb  shl     ecx, 10h
0x14007a2be  or      ecx, eax
0x14007a2c0  mov     [rdi+1E0h], ecx
0x14007a2c6  test    r15d, r15d
0x14007a2c9  jz      short loc_14007A2DD
0x14007a2cb  mov     rcx, [r14+38h]; AddressWithinSection
0x14007a2cf  call    cs:__imp_MmIsDriverVerifyingByAddress
0x14007a2d6  nop     dword ptr [rax+rax+00h]
0x14007a2db  jmp     short loc_14007A2EC
0x14007a2dd  mov     rcx, rsi; DriverObject
0x14007a2e0  call    cs:__imp_MmIsDriverVerifying
0x14007a2e7  nop     dword ptr [rax+rax+00h]
0x14007a2ec  xor     r13d, r13d
0x14007a2ef  test    eax, eax
0x14007a2f1  jz      short loc_14007A319
0x14007a2f3  or      word ptr [rdi+1Ah], 2
0x14007a2f8  test    cs:?ndisFlags@@3JA, 400h; long ndisFlags
0x14007a302  jz      short loc_14007A319
0x14007a304  cmp     cs:?ndisDriverTrackAlloc@@3PEAU_NDIS_M_DRIVER_BLOCK@@EA, r13; _NDIS_M_DRIVER_BLOCK * ndisDriverTrackAlloc
0x14007a30b  mov     eax, r13d
0x14007a30e  cmovz   rax, rdi
0x14007a312  mov     cs:?ndisDriverTrackAlloc@@3PEAU_NDIS_M_DRIVER_BLOCK@@EA, rax; _NDIS_M_DRIVER_BLOCK * ndisDriverTrackAlloc
0x14007a319  mov     [rdi+10h], r13
0x14007a31d  mov     eax, [r14+8]
0x14007a321  test    al, 30h
0x14007a323  jnz     loc_14007A3F1
0x14007a329  lea     r8, ?ndisDummyIrpHandler@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z; ndisDummyIrpHandler(_DEVICE_OBJECT *,_IRP *)
0x14007a330  mov     ecx, 3
0x14007a335  lea     rax, [rsi+70h]
0x14007a339  nop     dword ptr [rax+00000000h]
0x14007a340  mov     [rax], r8
0x14007a343  mov     [rax+8], r8
0x14007a347  mov     [rax+10h], r8
0x14007a34b  lea     rax, [rax+40h]
0x14007a34f  mov     [rax-28h], r8
0x14007a353  mov     [rax-20h], r8
0x14007a357  mov     [rax-18h], r8
0x14007a35b  mov     [rax-10h], r8
0x14007a35f  mov     [rax-8], r8
0x14007a363  sub     rcx, 1
0x14007a367  jnz     short loc_14007A340
0x14007a369  mov     [rax], r8
0x14007a36c  lea     rcx, ?ndisWdmPnPAddDevice@@YAJPEAU_DRIVER_OBJECT@@PEAU_DEVICE_OBJECT@@@Z; ndisWdmPnPAddDevice(_DRIVER_OBJECT *,_DEVICE_OBJECT *)
0x14007a373  mov     [rax+8], r8
0x14007a377  mov     [rax+10h], r8
0x14007a37b  mov     [rax+18h], r8
0x14007a37f  mov     rax, [rsi+30h]
0x14007a383  mov     [rax+8], rcx
0x14007a387  lea     rax, ?ndisMUnloadEx@@YAXPEAU_DRIVER_OBJECT@@@Z; ndisMUnloadEx(_DRIVER_OBJECT *)
0x14007a38e  mov     [rsi+68h], rax
0x14007a392  lea     rax, ?ndisCreateIrpHandler@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z; ndisCreateIrpHandler(_DEVICE_OBJECT *,_IRP *)
0x14007a399  mov     [rsi+70h], rax
0x14007a39d  lea     rax, ?ndisDeviceControlIrpHandler@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z; ndisDeviceControlIrpHandler(_DEVICE_OBJECT *,_IRP *)
0x14007a3a4  mov     [rsi+0E0h], rax
0x14007a3ab  lea     rax, ?ndisDeviceInternalIrpDispatch@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z; ndisDeviceInternalIrpDispatch(_DEVICE_OBJECT *,_IRP *)
0x14007a3b2  mov     [rsi+0E8h], rax
0x14007a3b9  lea     rax, ?ndisCloseIrpHandler@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z; ndisCloseIrpHandler(_DEVICE_OBJECT *,_IRP *)
0x14007a3c0  mov     [rsi+80h], rax
0x14007a3c7  lea     rax, ?ndisPnPDispatch@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z; ndisPnPDispatch(_DEVICE_OBJECT *,_IRP *)
0x14007a3ce  mov     [rsi+148h], rax
0x14007a3d5  lea     rax, ?ndisPowerDispatch@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z; ndisPowerDispatch(_DEVICE_OBJECT *,_IRP *)
0x14007a3dc  mov     [rsi+120h], rax
0x14007a3e3  lea     rax, ?ndisWMIIrpDispatch@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z; ndisWMIIrpDispatch(_DEVICE_OBJECT *,_IRP *)
0x14007a3ea  mov     [rsi+128h], rax
0x14007a3f1  lea     rcx, [rdi+170h]; Event
0x14007a3f8  xor     r8d, r8d; State
0x14007a3fb  xor     edx, edx; Type
0x14007a3fd  call    cs:__imp_KeInitializeEvent
0x14007a404  nop     dword ptr [rax+rax+00h]
0x14007a409  lea     rax, [rdi+50h]
0x14007a40d  mov     [rdi+28h], rsi
0x14007a411  lea     rcx, [rdi+188h]; struct _REFERENCE_EX *
0x14007a418  mov     [rax+8], rax
0x14007a41c  mov     dl, 0Dh; unsigned __int8
0x14007a41e  mov     [rax], rax
0x14007a421  call    ?ndisInitializeRef@@YAXPEAU_REFERENCE_EX@@E@Z; ndisInitializeRef(_REFERENCE_EX *,uchar)
0x14007a426  call    Feature_NdisTriageData__private_IsEnabledDeviceUsageNoInline
0x14007a42b  lea     r12, [rdi+4A0h]
0x14007a432  test    eax, eax
0x14007a434  jz      loc_14007A565
0x14007a43a  lea     rax, ?AddTriageBlocks@?$StructSliceDataCollector@U_NDIS_M_DRIVER_BLOCK@@$0A@$0BGA@@@SAXPEAU_NDIS_M_DRIVER_BLOCK@@PEAVTriageDataArray@@PEBUBugcheckParameters@@@Z; StructSliceDataCollector<_NDIS_M_DRIVER_BLOCK,0,352>::AddTriageBlocks(_NDIS_M_DRIVER_BLOCK *,TriageDataArray *,BugcheckParameters const *)
0x14007a441  mov     [rbp+4Fh+var_90], 1
0x14007a448  mov     [rbp+4Fh+var_88], rax
0x14007a44c  lea     r9, [rbp+4Fh+var_A8]
0x14007a450  lea     rax, ?AddTriageBlocks@?$StructFieldDataCollector@U_NDIS_M_DRIVER_BLOCK@@U_UNICODE_STRING@@$0BOI@@@SAXPEAU_NDIS_M_DRIVER_BLOCK@@PEAVTriageDataArray@@PEBUBugcheckParameters@@@Z; StructFieldDataCollector<_NDIS_M_DRIVER_BLOCK,_UNICODE_STRING,488>::AddTriageBlocks(_NDIS_M_DRIVER_BLOCK *,TriageDataArray *,BugcheckParameters const *)
0x14007a457  mov     [rbp+4Fh+var_80], 1
0x14007a45e  mov     [rbp+4Fh+var_78], rax
0x14007a462  lea     rdx, [rbp+4Fh+var_90]
0x14007a466  lea     rax, ?AddTriageBlocks@?$UnicodeStringDataCollector@U_NDIS_M_DRIVER_BLOCK@@$0BOI@@@SAXPEAU_NDIS_M_DRIVER_BLOCK@@PEAVTriageDataArray@@PEBUBugcheckParameters@@@Z; UnicodeStringDataCollector<_NDIS_M_DRIVER_BLOCK,488>::AddTriageBlocks(_NDIS_M_DRIVER_BLOCK *,TriageDataArray *,BugcheckParameters const *)
0x14007a46d  mov     [rbp+4Fh+var_70], 1
0x14007a474  mov     [rbp+4Fh+var_68], rax
0x14007a478  mov     rcx, rdi
0x14007a47b  lea     rax, ?AddTriageBlocks@?$StructFieldDataCollector@U_NDIS_M_DRIVER_BLOCK@@U_UNICODE_STRING@@$0DGI@@@SAXPEAU_NDIS_M_DRIVER_BLOCK@@PEAVTriageDataArray@@PEBUBugcheckParameters@@@Z; StructFieldDataCollector<_NDIS_M_DRIVER_BLOCK,_UNICODE_STRING,872>::AddTriageBlocks(_NDIS_M_DRIVER_BLOCK *,TriageDataArray *,BugcheckParameters const *)
0x14007a482  mov     [rbp+4Fh+var_60], 1
0x14007a489  mov     [rbp+4Fh+var_58], rax
0x14007a48d  lea     rax, ?AddTriageBlocks@?$UnicodeStringDataCollector@U_NDIS_M_DRIVER_BLOCK@@$0DGI@@@SAXPEAU_NDIS_M_DRIVER_BLOCK@@PEAVTriageDataArray@@PEBUBugcheckParameters@@@Z; UnicodeStringDataCollector<_NDIS_M_DRIVER_BLOCK,872>::AddTriageBlocks(_NDIS_M_DRIVER_BLOCK *,TriageDataArray *,BugcheckParameters const *)
0x14007a494  mov     [rbp+4Fh+var_48], rax
0x14007a498  mov     [rbp+4Fh+var_50], 1
0x14007a49f  mov     [rbp+4Fh+var_B0], r12
0x14007a4a3  mov     [rbp+4Fh+var_A8], r13
0x14007a4a7  mov     [rbp+4Fh+var_A0], 1
0x14007a4ab  call    ?Make@?$ObjectTriageData@U_NDIS_M_DRIVER_BLOCK@@@@SAJPEAU_NDIS_M_DRIVER_BLOCK@@PEBU?$TriageDataCollector@U_NDIS_M_DRIVER_BLOCK@@@@_KPEAPEAVTriageData@@@Z; ObjectTriageData<_NDIS_M_DRIVER_BLOCK>::Make(_NDIS_M_DRIVER_BLOCK *,TriageDataCollector<_NDIS_M_DRIVER_BLOCK> const *,unsigned __int64,TriageData * *)
0x14007a4b0  mov     ebx, eax
0x14007a4b2  test    eax, eax
0x14007a4b4  js      short loc_14007A4C9
0x14007a4b6  cmp     eax, 103h
0x14007a4bb  jz      short loc_14007A4D5
0x14007a4bd  cmp     eax, 40230001h
0x14007a4c2  jz      short loc_14007A4D5
0x14007a4c4  mov     ebx, r13d
0x14007a4c7  jmp     short loc_14007A4D5
0x14007a4c9  cmp     eax, 0C0000023h
0x14007a4ce  jnz     short loc_14007A4D5
0x14007a4d0  mov     ebx, 0C0010016h
0x14007a4d5  cmp     [rbp+4Fh+var_A0], 0
0x14007a4d9  jz      short loc_14007A50F
0x14007a4db  mov     rdx, [rbp+4Fh+var_B0]
0x14007a4df  mov     rax, [rbp+4Fh+var_A8]
0x14007a4e3  mov     rsi, [rdx]
0x14007a4e6  mov     [rdx], rax
0x14007a4e9  test    rsi, rsi
0x14007a4ec  jz      short loc_14007A50F
0x14007a4ee  mov     rax, [rsi]
0x14007a4f1  xor     edx, edx
0x14007a4f3  mov     rcx, rsi
0x14007a4f6  mov     rax, [rax]
0x14007a4f9  call    _guard_dispatch_icall
0x14007a4fe  xor     edx, edx; Tag
0x14007a500  mov     rcx, rsi; P
0x14007a503  call    cs:__imp_ExFreePoolWithTag
0x14007a50a  nop     dword ptr [rax+rax+00h]
0x14007a50f  test    ebx, ebx
0x14007a511  jz      short loc_14007A565
0x14007a513  lea     r14, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14007a51a  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14007a521  jz      short loc_14007A556
0x14007a523  mov     rcx, cs:WPP_GLOBAL_Control
0x14007a52a  lea     rax, WPP_b0ad62796b5830cbf8ad07ce2f1bab24_Traceguids
0x14007a531  mov     dword ptr [rsp+100h+var_D0], ebx; char
0x14007a535  mov     r9d, 6Bh ; 'k'; int
0x14007a53b  mov     [rsp+100h+var_D8], rdi; char
0x14007a540  mov     r8d, 1; int
0x14007a546  mov     dl, 2; int
0x14007a548  mov     [rsp+100h+var_E0], rax; struct _GUID *
0x14007a54d  mov     rcx, [rcx+40h]; int
0x14007a551  call    WPP_RECORDER_SF_qD
0x14007a556  mov     r8b, 0FFh; enum _NDIS_MDRV_REFTAG
  ... truncated ...
```
