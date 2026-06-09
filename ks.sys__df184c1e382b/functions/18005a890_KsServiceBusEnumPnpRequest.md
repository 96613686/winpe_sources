# KsServiceBusEnumPnpRequest

- ea: `0x18005a890`
- end: `0x18005b222`
- name: `KsServiceBusEnumPnpRequest`
- size: `2450`
- prototype: `NTSTATUS __stdcall(PDEVICE_OBJECT DeviceObject, PIRP Irp)`
- caller_count: `0`
- callee_count: `15`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x18000b7bc`
- `0x18000c630`
- `0x18000dddc`
- `0x18001a000`
- `0x180035f68`
- `0x18003676c`
- `0x18005997c`
- `0x1800599f8`
- `0x18005a6d4`
- `0x18005a890`
- `0x18005f300`
- `0x18005f480`
- `0x18005fa1c`
- `0x180060ef0`
- `0x180064970`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x18005ab8d`
- `ntoskrnl!RtlFreeUnicodeString` at `0x18005ab8d`
- `ntoskrnl!IoSetDeviceInterfaceState` at `0x18005ab7d`
- `ntoskrnl!IoSetDeviceInterfaceState` at `0x18005ab7d`
- `ntoskrnl!IoDetachDevice` at `0x18005abc3`
- `ntoskrnl!IoDetachDevice` at `0x18005abc3`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x18005b1ae`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x18005b1ae`
- `ntoskrnl!ExReleaseFastMutex` at `0x18005a9cd`
- `ntoskrnl!ExReleaseFastMutex` at `0x18005aa56`
- `ntoskrnl!ExReleaseFastMutex` at `0x18005aaf1`
- `ntoskrnl!ExReleaseFastMutex` at `0x18005ab33`
- `ntoskrnl!ExReleaseFastMutex` at `0x18005ac9f`
- `ntoskrnl!ExReleaseFastMutex` at `0x18005ace1`
- `ntoskrnl!ExReleaseFastMutex` at `0x18005a9cd`
- `ntoskrnl!ExReleaseFastMutex` at `0x18005aa56`
- `ntoskrnl!ExReleaseFastMutex` at `0x18005aaf1`
- `ntoskrnl!ExReleaseFastMutex` at `0x18005ab33`
- `ntoskrnl!ExReleaseFastMutex` at `0x18005ac9f`
- `ntoskrnl!ExReleaseFastMutex` at `0x18005ace1`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18005b19e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18005b19e`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x18005ab52`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x18005ab65`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x18005ab52`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x18005ab65`
- `ntoskrnl!KeCancelTimer` at `0x18005aae1`
- `ntoskrnl!KeCancelTimer` at `0x18005ab24`
- `ntoskrnl!KeCancelTimer` at `0x18005ac8f`
- `ntoskrnl!KeCancelTimer` at `0x18005acd2`
- `ntoskrnl!KeCancelTimer` at `0x18005aae1`
- `ntoskrnl!KeCancelTimer` at `0x18005ab24`
- `ntoskrnl!KeCancelTimer` at `0x18005ac8f`
- `ntoskrnl!KeCancelTimer` at `0x18005acd2`
- `ntoskrnl!ExAcquireFastMutex` at `0x18005a9b6`
- `ntoskrnl!ExAcquireFastMutex` at `0x18005aa40`
- `ntoskrnl!ExAcquireFastMutex` at `0x18005aac4`
- `ntoskrnl!ExAcquireFastMutex` at `0x18005ab07`
- `ntoskrnl!ExAcquireFastMutex` at `0x18005ac72`
- `ntoskrnl!ExAcquireFastMutex` at `0x18005acb5`
- `ntoskrnl!ExAcquireFastMutex` at `0x18005a9b6`
- `ntoskrnl!ExAcquireFastMutex` at `0x18005aa40`
- `ntoskrnl!ExAcquireFastMutex` at `0x18005aac4`
- `ntoskrnl!ExAcquireFastMutex` at `0x18005ab07`
- `ntoskrnl!ExAcquireFastMutex` at `0x18005ac72`
- `ntoskrnl!ExAcquireFastMutex` at `0x18005acb5`
- `ntoskrnl!IoFreeWorkItem` at `0x18005abdb`
- `ntoskrnl!IoFreeWorkItem` at `0x18005abfa`
- `ntoskrnl!IoFreeWorkItem` at `0x18005abdb`
- `ntoskrnl!IoFreeWorkItem` at `0x18005abfa`
- `ntoskrnl!KeFlushQueuedDpcs` at `0x18005ab3f`
- `ntoskrnl!KeFlushQueuedDpcs` at `0x18005ab3f`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x18005b1db`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x18005b1db`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18005b1e7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18005b1e7`
- `ntoskrnl!ExFreePoolWithTag` at `0x18005aba2`
- `ntoskrnl!ExFreePoolWithTag` at `0x18005ac12`
- `ntoskrnl!ExFreePoolWithTag` at `0x18005aba2`
- `ntoskrnl!ExFreePoolWithTag` at `0x18005ac12`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18005b157`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18005b157`

## pseudocode

```c
NTSTATUS __stdcall KsServiceBusEnumPnpRequest(PDEVICE_OBJECT DeviceObject, PIRP Irp)
{
  __int64 *DeviceExtension; // rax
  PIRP v3; // r15
  __int64 v5; // rsi
  int v7; // ecx
  NTSTATUS v8; // ebp
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rbx
  PDEVICE_OBJECT v10; // rcx
  int v11; // r9d
  __int64 Length; // rdx
  LARGE_INTEGER v14; // rbx
  int v15; // edx
  struct _IO_WORKITEM *v16; // rcx
  struct _IO_WORKITEM *v17; // rcx
  __int64 v18; // r14
  unsigned int MinorFunction; // ecx
  unsigned int v20; // ecx
  unsigned int v21; // ecx
  unsigned int v22; // ecx
  unsigned int v23; // ecx
  unsigned int v24; // ecx
  unsigned int v25; // ecx
  unsigned int v26; // ecx
  _QWORD *p_SecurityQos; // rdx
  LARGE_INTEGER ByteOffset; // rax
  PIO_SECURITY_CONTEXT SecurityContext; // r14
  __int16 SecurityQos; // di
  __int16 v31; // bx
  int SecurityQos_high; // esi
  __m128i si128; // xmm0
  int v34; // eax
  unsigned int v35; // ecx
  unsigned int v36; // ecx
  unsigned int v37; // ecx
  unsigned int v38; // ecx
  unsigned int v39; // ecx
  unsigned int v40; // ecx
  unsigned int v41; // ecx
  _QWORD *PoolWithTag; // rax
  __int64 v43; // rbx
  __int64 v44; // rdx

  DeviceExtension = (__int64 *)DeviceObject->DeviceExtension;
  v3 = Irp;
  v5 = *DeviceExtension;
  if ( !*DeviceExtension )
    return -1073741811;
  v7 = *(_DWORD *)(v5 + 16);
  v8 = -1073741637;
  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  if ( !v7 )
  {
    v18 = *(_QWORD *)(v5 + 32);
    if ( DeviceObject != *(PDEVICE_OBJECT *)(v18 + 48) )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
      {
        LOBYTE(Irp) = 5;
        WPP_RECORDER_SF_q(
          WPP_GLOBAL_Control->DeviceExtension,
          (_DWORD)Irp,
          1,
          34,
          (__int64)WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids,
          (char)DeviceObject);
      }
      return -1073741810;
    }
    MinorFunction = CurrentStackLocation->MinorFunction;
    if ( MinorFunction > 9 )
    {
      v35 = MinorFunction - 10;
      if ( !v35 || (v36 = v35 - 1) == 0 )
      {
        Irp->IoStatus.Information = 0;
        return 0;
      }
      v37 = v36 - 4;
      if ( !v37 )
        return 0;
      v38 = v37 - 1;
      if ( !v38 )
        return 0;
      v39 = v38 - 3;
      if ( v39 )
      {
        v40 = v39 - 1;
        if ( !v40 )
        {
          LODWORD(Irp->IoStatus.Information) |= 0x22u;
          v43 = *(_QWORD *)(v5 + 40);
          KeEnterCriticalRegion();
          ExAcquireFastMutexUnsafe((PFAST_MUTEX)(v43 + 24));
          if ( *(_DWORD *)(v18 + 56) == 3 )
          {
            *(_DWORD *)(v18 + 56) = 4;
            CompletePendingIo(v18, v44, 260);
          }
          ExReleaseFastMutexUnsafe((PFAST_MUTEX)(v43 + 24));
          KeLeaveCriticalRegion();
          return 0;
        }
        v41 = v40 - 1;
        if ( v41 )
        {
          if ( v41 != 2 )
            return v8;
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            v10 = WPP_GLOBAL_Control;
            if ( LOWORD(WPP_GLOBAL_Control->DeviceType) )
            {
              v11 = 39;
              goto LABEL_18;
            }
          }
        }
        else
        {
          PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)1025, 0x18u, 0x69625753u);
          if ( !PoolWithTag )
            return -1073741670;
          *(_OWORD *)PoolWithTag = 0;
          PoolWithTag[2] = 0;
          *((_DWORD *)PoolWithTag + 4) = -1;
          *(GUID *)PoolWithTag = KSMEDIUMSETID_Standard;
          v3->IoStatus.Information = (ULONG_PTR)PoolWithTag;
        }
        return 0;
      }
      return QueryId(*DeviceExtension, CurrentStackLocation->Parameters.Read.Length, &Irp->IoStatus.Information);
    }
    if ( MinorFunction == 9 )
    {
      SecurityContext = CurrentStackLocation->Parameters.Create.SecurityContext;
      SecurityQos = (__int16)SecurityContext->SecurityQos;
      v31 = WORD1(SecurityContext->SecurityQos);
      SecurityQos_high = HIDWORD(SecurityContext->SecurityQos);
      memset(SecurityContext, 0, 0x40u);
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      v34 = (HIDWORD(SecurityContext->SecurityQos) ^ SecurityQos_high) & 0x7FFFFF;
      LOWORD(SecurityContext->SecurityQos) = SecurityQos;
      WORD1(SecurityContext->SecurityQos) = v31;
      HIDWORD(SecurityContext->SecurityQos) = SecurityQos_high ^ v34;
      SecurityContext[1].FullCreateOptions = 1;
      LODWORD(SecurityContext[2].SecurityQos) = 1;
      SecurityContext->DesiredAccess = 0;
      SecurityContext->FullCreateOptions = 1;
      LODWORD(SecurityContext[1].SecurityQos) = 2;
      *(__m128i *)((char *)&SecurityContext[1].SecurityQos + 4) = si128;
      HIDWORD(SecurityContext->SecurityQos) = HIDWORD(SecurityContext->SecurityQos) & 0xFFFFFD03 | 0x2C0;
      v3->IoStatus.Information = 64;
      return 0;
    }
    if ( !CurrentStackLocation->MinorFunction )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
      {
        LOBYTE(Irp) = 5;
        WPP_RECORDER_SF_q(
          WPP_GLOBAL_Control->DeviceExtension,
          (_DWORD)Irp,
          1,
          35,
          (__int64)WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids,
          (char)DeviceObject);
      }
      return StartDevice((ULONG_PTR)DeviceObject);
    }
    v20 = MinorFunction - 1;
    if ( !v20 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
      {
        LOBYTE(Irp) = 5;
        WPP_RECORDER_SF_q(
          WPP_GLOBAL_Control->DeviceExtension,
          (_DWORD)Irp,
          1,
          37,
          (__int64)WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids,
          (char)DeviceObject);
      }
      if ( *(_DWORD *)(v5 + 48) || *(_DWORD *)(v18 + 56) == 2 )
        return -1073741436;
      return 0;
    }
    v21 = v20 - 1;
    if ( !v21 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
      {
        LOBYTE(Irp) = 5;
        WPP_RECORDER_SF_q(
          WPP_GLOBAL_Control->DeviceExtension,
          (_DWORD)Irp,
          1,
          41,
          (__int64)WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids,
          (char)DeviceObject);
      }
      return RemoveDevice(DeviceObject);
    }
    v22 = v21 - 1;
    if ( !v22 )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        return 0;
      v10 = WPP_GLOBAL_Control;
      if ( !LOWORD(WPP_GLOBAL_Control->DeviceType) )
        return 0;
      v11 = 40;
      goto LABEL_18;
    }
    v23 = v22 - 1;
    if ( !v23 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
      {
        LOBYTE(Irp) = 5;
        WPP_RECORDER_SF_q(
          WPP_GLOBAL_Control->DeviceExtension,
          (_DWORD)Irp,
          1,
          38,
          (__int64)WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids,
          (char)DeviceObject);
      }
      *(_DWORD *)(v18 + 56) = 5;
      return 0;
    }
    v24 = v23 - 1;
    if ( !v24 || (v25 = v24 - 1) == 0 )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        return 0;
      v10 = WPP_GLOBAL_Control;
      if ( !LOWORD(WPP_GLOBAL_Control->DeviceType) )
        return 0;
      v11 = 36;
      goto LABEL_18;
    }
    v26 = v25 - 1;
    if ( v26 )
    {
      if ( v26 != 1 )
        return v8;
      p_SecurityQos = &CurrentStackLocation->Parameters.Create.SecurityContext->SecurityQos;
      if ( *p_SecurityQos != *(_QWORD *)&KSMEDIUMSETID_Standard.Data1
        || p_SecurityQos[1] != *(_QWORD *)KSMEDIUMSETID_Standard.Data4
        || CurrentStackLocation->Parameters.QueryInterface.Size != 56
        || CurrentStackLocation->Parameters.QueryInterface.Version != 256 )
      {
        return v8;
      }
      ByteOffset = CurrentStackLocation->Parameters.Read.ByteOffset;
      *(_QWORD *)(ByteOffset.QuadPart + 16) = InterfaceReference;
      *(_QWORD *)(ByteOffset.QuadPart + 24) = InterfaceDereference;
      *(_QWORD *)(ByteOffset.QuadPart + 32) = ReferenceDeviceObject;
      *(_QWORD *)(ByteOffset.QuadPart + 40) = DereferenceDeviceObject;
      *(_QWORD *)(ByteOffset.QuadPart + 48) = QueryReferenceString;
      *(_DWORD *)ByteOffset.QuadPart = 16777272;
      *(_QWORD *)(ByteOffset.QuadPart + 8) = v5;
      InterfaceReference(v5);
      return 0;
    }
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
    {
      LOBYTE(Irp) = 5;
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)Irp,
        1,
        42,
        (__int64)WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids);
    }
    if ( CurrentStackLocation->Parameters.Read.Length != 4 )
      return v8;
    Length = 4;
    return QueryDeviceRelations(v5, Length, &v3->IoStatus.Information);
  }
  if ( v7 == 1 )
  {
    switch ( CurrentStackLocation->MinorFunction )
    {
      case 0u:
        return 0;
      case 1u:
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
        {
          LOBYTE(Irp) = 5;
          WPP_RECORDER_SF_q(
            WPP_GLOBAL_Control->DeviceExtension,
            (_DWORD)Irp,
            1,
            30,
            (__int64)WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids,
            (char)DeviceObject);
        }
        ExAcquireFastMutex((PFAST_MUTEX)(v5 + 120));
        *(_DWORD *)(v5 + 176) = 1;
        KeCancelTimer((PKTIMER)(v5 + 192));
        ExReleaseFastMutex((PFAST_MUTEX)(v5 + 120));
        ExAcquireFastMutex((PFAST_MUTEX)(v5 + 496));
        *(_DWORD *)(v5 + 552) = 1;
        KeCancelTimer((PKTIMER)(v5 + 568));
        ExReleaseFastMutex((PFAST_MUTEX)(v5 + 496));
        return 0;
      case 2u:
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
        {
          LOBYTE(Irp) = 5;
          WPP_RECORDER_SF_q(
            WPP_GLOBAL_Control->DeviceExtension,
            (_DWORD)Irp,
            1,
            33,
            (__int64)WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids,
            (char)DeviceObject);
        }
        ExAcquireFastMutex((PFAST_MUTEX)(v5 + 120));
        *(_DWORD *)(v5 + 176) = 1;
        KeCancelTimer((PKTIMER)(v5 + 192));
        ExReleaseFastMutex((PFAST_MUTEX)(v5 + 120));
        ExAcquireFastMutex((PFAST_MUTEX)(v5 + 496));
        *(_DWORD *)(v5 + 552) = 1;
        KeCancelTimer((PKTIMER)(v5 + 568));
        ExReleaseFastMutex((PFAST_MUTEX)(v5 + 496));
        KeFlushQueuedDpcs();
        ExWaitForRundownProtectionRelease((PEX_RUNDOWN_REF)(v5 + 184));
        ExWaitForRundownProtectionRelease((PEX_RUNDOWN_REF)(v5 + 560));
        if ( *(_QWORD *)(v5 + 88) )
        {
          IoSetDeviceInterfaceState((PUNICODE_STRING)(v5 + 80), 0);
          RtlFreeUnicodeString((PUNICODE_STRING)(v5 + 80));
        }
        ExFreePoolWithTag(*(PVOID *)(v5 + 344), 0);
        RescanUninitialize(v5);
        if ( *(_DWORD *)(v5 + 352) )
          IoDetachDevice(*(PDEVICE_OBJECT *)(v5 + 104));
        v16 = *(struct _IO_WORKITEM **)(v5 + 328);
        if ( v16 )
        {
          IoFreeWorkItem(v16);
          *(_QWORD *)(v5 + 328) = 0;
        }
        v17 = *(struct _IO_WORKITEM **)(v5 + 704);
        if ( v17 )
        {
          IoFreeWorkItem(v17);
          *(_QWORD *)(v5 + 704) = 0;
        }
        ExFreePoolWithTag((PVOID)v5, 0);
        *(_QWORD *)DeviceObject->DeviceExtension = 0;
        return 0;
      case 3u:
        v8 = 0;
        v14.QuadPart = ComputeNextSweeperPeriod(*DeviceExtension);
        ExAcquireFastMutex((PFAST_MUTEX)(v5 + 120));
        *(_DWORD *)(v5 + 176) = 0;
        ExReleaseFastMutex((PFAST_MUTEX)(v5 + 120));
        if ( v14.QuadPart )
        {
          v8 = QueueSweeperTimer(v5, v14);
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
            && LOWORD(WPP_GLOBAL_Control->DeviceType) )
          {
            LOBYTE(v15) = 5;
            WPP_RECORDER_SF_D(
              WPP_GLOBAL_Control->DeviceExtension,
              v15,
              1,
              31,
              (__int64)WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids,
              v8);
          }
          if ( v8 < 0 )
            return v8;
        }
        ExAcquireFastMutex((PFAST_MUTEX)(v5 + 496));
        *(_DWORD *)(v5 + 552) = 0;
        ExReleaseFastMutex((PFAST_MUTEX)(v5 + 496));
        if ( *(_DWORD *)(v5 + 556) != 1 )
          return v8;
        return QueueRescanTimer(v5);
      case 4u:
      case 5u:
      case 6u:
        return 0;
    }
    if ( CurrentStackLocation->MinorFunction != 7 )
    {
      if ( CurrentStackLocation->MinorFunction != 23 )
        return v8;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v10 = WPP_GLOBAL_Control;
        if ( LOWORD(WPP_GLOBAL_Control->DeviceType) )
        {
          v11 = 32;
LABEL_18:
          LOBYTE(Irp) = 5;
          WPP_RECORDER_SF_q(
            v10->DeviceExtension,
            (_DWORD)Irp,
            1,
            v11,
            (__int64)WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids,
            (char)DeviceObject);
          return 0;
        }
      }
      return 0;
    }
    Length = CurrentStackLocation->Parameters.Read.Length;
    if ( (_DWORD)Length == 4 )
      return v8;
    return QueryDeviceRelations(v5, Length, &v3->IoStatus.Information);
  }
  return -1073741808;
}

```

## disassembly

```asm
0x18005a890  push    rbx
0x18005a892  push    rbp
0x18005a893  push    rsi
0x18005a894  push    rdi
0x18005a895  push    r12
0x18005a897  push    r14
0x18005a899  push    r15
0x18005a89b  sub     rsp, 30h
0x18005a89f  mov     rax, [rcx+40h]
0x18005a8a3  xor     r12d, r12d
0x18005a8a6  mov     r15, rdx
0x18005a8a9  mov     rdi, rcx
0x18005a8ac  mov     rsi, [rax]
0x18005a8af  test    rsi, rsi
0x18005a8b2  jnz     short loc_18005A8BE
0x18005a8b4  mov     eax, 0C000000Dh
0x18005a8b9  jmp     loc_18005B212
0x18005a8be  mov     ecx, [rsi+10h]
0x18005a8c1  mov     ebp, 0C00000BBh
0x18005a8c6  mov     rbx, [rdx+0B8h]
0x18005a8cd  test    ecx, ecx
0x18005a8cf  jz      loc_18005ACF2
0x18005a8d5  cmp     ecx, 1
0x18005a8d8  jz      short loc_18005A8E4
0x18005a8da  mov     ebp, 0C0000010h
0x18005a8df  jmp     loc_18005B210
0x18005a8e4  movzx   ecx, byte ptr [rbx+1]
0x18005a8e8  test    ecx, ecx
0x18005a8ea  jz      loc_18005B20D
0x18005a8f0  sub     ecx, 1
0x18005a8f3  jz      loc_18005AC2A
0x18005a8f9  sub     ecx, 1
0x18005a8fc  jz      loc_18005AA7C
0x18005a902  sub     ecx, 1
0x18005a905  jz      loc_18005A9A4
0x18005a90b  sub     ecx, 1
0x18005a90e  jz      loc_18005B20D
0x18005a914  sub     ecx, 1
0x18005a917  jz      loc_18005B20D
0x18005a91d  sub     ecx, 1
0x18005a920  jz      loc_18005B20D
0x18005a926  sub     ecx, 1
0x18005a929  jz      short loc_18005A987
0x18005a92b  cmp     ecx, 10h
0x18005a92e  jnz     loc_18005B210
0x18005a934  lea     rax, WPP_RECORDER_INITIALIZED
0x18005a93b  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18005a942  jz      loc_18005B20D
0x18005a948  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a94f  cmp     [rcx+48h], r12w
0x18005a954  jz      loc_18005B20D
0x18005a95a  mov     r9d, 20h ; ' '
0x18005a960  mov     rcx, [rcx+40h]
0x18005a964  lea     rax, WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids
0x18005a96b  mov     [rsp+68h+var_40], rdi
0x18005a970  mov     r8d, 1
0x18005a976  mov     dl, 5
0x18005a978  mov     [rsp+68h+var_48], rax
0x18005a97d  call    WPP_RECORDER_SF_q
0x18005a982  jmp     loc_18005B20D
0x18005a987  mov     edx, [rbx+8]
0x18005a98a  cmp     edx, 4
0x18005a98d  jz      loc_18005B210
0x18005a993  lea     r8, [r15+38h]
0x18005a997  mov     rcx, rsi
0x18005a99a  call    QueryDeviceRelations
0x18005a99f  jmp     loc_18005B044
0x18005a9a4  mov     rcx, rsi
0x18005a9a7  mov     ebp, r12d
0x18005a9aa  call    ComputeNextSweeperPeriod
0x18005a9af  lea     rcx, [rsi+78h]; FastMutex
0x18005a9b3  mov     rbx, rax
0x18005a9b6  call    cs:__imp_ExAcquireFastMutex
0x18005a9bd  nop     dword ptr [rax+rax+00h]
0x18005a9c2  lea     rcx, [rsi+78h]; FastMutex
0x18005a9c6  mov     [rsi+0B0h], r12d
0x18005a9cd  call    cs:__imp_ExReleaseFastMutex
0x18005a9d4  nop     dword ptr [rax+rax+00h]
0x18005a9d9  test    rbx, rbx
0x18005a9dc  jz      short loc_18005AA36
0x18005a9de  mov     rdx, rbx
0x18005a9e1  mov     rcx, rsi
0x18005a9e4  call    QueueSweeperTimer
0x18005a9e9  mov     ebp, eax
0x18005a9eb  lea     rax, WPP_RECORDER_INITIALIZED
0x18005a9f2  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18005a9f9  jz      short loc_18005AA2E
0x18005a9fb  mov     rcx, cs:WPP_GLOBAL_Control
0x18005aa02  cmp     [rcx+48h], r12w
0x18005aa07  jz      short loc_18005AA2E
0x18005aa09  mov     rcx, [rcx+40h]
0x18005aa0d  lea     rax, WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids
0x18005aa14  mov     r9d, 1Fh
0x18005aa1a  mov     dword ptr [rsp+68h+var_40], ebp
0x18005aa1e  mov     dl, 5
0x18005aa20  mov     [rsp+68h+var_48], rax
0x18005aa25  lea     r8d, [r9-1Eh]
0x18005aa29  call    WPP_RECORDER_SF_D
0x18005aa2e  test    ebp, ebp
0x18005aa30  js      loc_18005B210
0x18005aa36  lea     rbx, [rsi+1F0h]
0x18005aa3d  mov     rcx, rbx; FastMutex
0x18005aa40  call    cs:__imp_ExAcquireFastMutex
0x18005aa47  nop     dword ptr [rax+rax+00h]
0x18005aa4c  mov     rcx, rbx; FastMutex
0x18005aa4f  mov     [rsi+228h], r12d
0x18005aa56  call    cs:__imp_ExReleaseFastMutex
0x18005aa5d  nop     dword ptr [rax+rax+00h]
0x18005aa62  cmp     dword ptr [rsi+22Ch], 1
0x18005aa69  jnz     loc_18005B210
0x18005aa6f  mov     rcx, rsi
0x18005aa72  call    QueueRescanTimer
0x18005aa77  jmp     loc_18005B044
0x18005aa7c  lea     rax, WPP_RECORDER_INITIALIZED
0x18005aa83  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18005aa8a  jz      short loc_18005AAC0
0x18005aa8c  mov     rcx, cs:WPP_GLOBAL_Control
0x18005aa93  cmp     [rcx+48h], r12w
0x18005aa98  jz      short loc_18005AAC0
0x18005aa9a  mov     rcx, [rcx+40h]
0x18005aa9e  lea     rax, WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids
0x18005aaa5  mov     r9d, 21h ; '!'
0x18005aaab  mov     [rsp+68h+var_40], rdi
0x18005aab0  mov     dl, 5
0x18005aab2  mov     [rsp+68h+var_48], rax
0x18005aab7  lea     r8d, [r9-20h]
0x18005aabb  call    WPP_RECORDER_SF_q
0x18005aac0  lea     rcx, [rsi+78h]; FastMutex
0x18005aac4  call    cs:__imp_ExAcquireFastMutex
0x18005aacb  nop     dword ptr [rax+rax+00h]
0x18005aad0  lea     rcx, [rsi+0C0h]; PKTIMER
0x18005aad7  mov     dword ptr [rsi+0B0h], 1
0x18005aae1  call    cs:__imp_KeCancelTimer
0x18005aae8  nop     dword ptr [rax+rax+00h]
0x18005aaed  lea     rcx, [rsi+78h]; FastMutex
0x18005aaf1  call    cs:__imp_ExReleaseFastMutex
0x18005aaf8  nop     dword ptr [rax+rax+00h]
0x18005aafd  lea     rbx, [rsi+1F0h]
0x18005ab04  mov     rcx, rbx; FastMutex
0x18005ab07  call    cs:__imp_ExAcquireFastMutex
0x18005ab0e  nop     dword ptr [rax+rax+00h]
0x18005ab13  lea     rcx, [rsi+238h]; PKTIMER
0x18005ab1a  mov     dword ptr [rsi+228h], 1
0x18005ab24  call    cs:__imp_KeCancelTimer
0x18005ab2b  nop     dword ptr [rax+rax+00h]
0x18005ab30  mov     rcx, rbx; FastMutex
0x18005ab33  call    cs:__imp_ExReleaseFastMutex
0x18005ab3a  nop     dword ptr [rax+rax+00h]
0x18005ab3f  call    cs:__imp_KeFlushQueuedDpcs
0x18005ab46  nop     dword ptr [rax+rax+00h]
0x18005ab4b  lea     rcx, [rsi+0B8h]; RunRef
0x18005ab52  call    cs:__imp_ExWaitForRundownProtectionRelease
0x18005ab59  nop     dword ptr [rax+rax+00h]
0x18005ab5e  lea     rcx, [rsi+230h]; RunRef
0x18005ab65  call    cs:__imp_ExWaitForRundownProtectionRelease
0x18005ab6c  nop     dword ptr [rax+rax+00h]
0x18005ab71  cmp     [rsi+58h], r12
0x18005ab75  jz      short loc_18005AB99
0x18005ab77  xor     edx, edx; Enable
0x18005ab79  lea     rcx, [rsi+50h]; SymbolicLinkName
0x18005ab7d  call    cs:__imp_IoSetDeviceInterfaceState
0x18005ab84  nop     dword ptr [rax+rax+00h]
0x18005ab89  lea     rcx, [rsi+50h]; UnicodeString
0x18005ab8d  call    cs:__imp_RtlFreeUnicodeString
0x18005ab94  nop     dword ptr [rax+rax+00h]
0x18005ab99  mov     rcx, [rsi+158h]; P
0x18005aba0  xor     edx, edx; Tag
0x18005aba2  call    cs:__imp_ExFreePoolWithTag
0x18005aba9  nop     dword ptr [rax+rax+00h]
0x18005abae  mov     rcx, rsi
0x18005abb1  call    RescanUninitialize
0x18005abb6  cmp     [rsi+160h], r12d
0x18005abbd  jz      short loc_18005ABCF
0x18005abbf  mov     rcx, [rsi+68h]; TargetDevice
0x18005abc3  call    cs:__imp_IoDetachDevice
0x18005abca  nop     dword ptr [rax+rax+00h]
0x18005abcf  mov     rcx, [rsi+148h]; IoWorkItem
0x18005abd6  test    rcx, rcx
0x18005abd9  jz      short loc_18005ABEE
0x18005abdb  call    cs:__imp_IoFreeWorkItem
0x18005abe2  nop     dword ptr [rax+rax+00h]
0x18005abe7  mov     [rsi+148h], r12
0x18005abee  mov     rcx, [rsi+2C0h]; IoWorkItem
0x18005abf5  test    rcx, rcx
0x18005abf8  jz      short loc_18005AC0D
0x18005abfa  call    cs:__imp_IoFreeWorkItem
0x18005ac01  nop     dword ptr [rax+rax+00h]
0x18005ac06  mov     [rsi+2C0h], r12
0x18005ac0d  xor     edx, edx; Tag
0x18005ac0f  mov     rcx, rsi; P
0x18005ac12  call    cs:__imp_ExFreePoolWithTag
0x18005ac19  nop     dword ptr [rax+rax+00h]
0x18005ac1e  mov     rax, [rdi+40h]
0x18005ac22  mov     [rax], r12
0x18005ac25  jmp     loc_18005B20D
0x18005ac2a  lea     rax, WPP_RECORDER_INITIALIZED
0x18005ac31  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18005ac38  jz      short loc_18005AC6E
0x18005ac3a  mov     rcx, cs:WPP_GLOBAL_Control
0x18005ac41  cmp     [rcx+48h], r12w
0x18005ac46  jz      short loc_18005AC6E
0x18005ac48  mov     rcx, [rcx+40h]
0x18005ac4c  lea     rax, WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids
0x18005ac53  mov     r9d, 1Eh
0x18005ac59  mov     [rsp+68h+var_40], rdi
0x18005ac5e  mov     dl, 5
0x18005ac60  mov     [rsp+68h+var_48], rax
0x18005ac65  lea     r8d, [r9-1Dh]
0x18005ac69  call    WPP_RECORDER_SF_q
0x18005ac6e  lea     rcx, [rsi+78h]; FastMutex
0x18005ac72  call    cs:__imp_ExAcquireFastMutex
0x18005ac79  nop     dword ptr [rax+rax+00h]
0x18005ac7e  lea     rcx, [rsi+0C0h]; PKTIMER
0x18005ac85  mov     dword ptr [rsi+0B0h], 1
0x18005ac8f  call    cs:__imp_KeCancelTimer
0x18005ac96  nop     dword ptr [rax+rax+00h]
0x18005ac9b  lea     rcx, [rsi+78h]; FastMutex
0x18005ac9f  call    cs:__imp_ExReleaseFastMutex
0x18005aca6  nop     dword ptr [rax+rax+00h]
0x18005acab  lea     rbx, [rsi+1F0h]
0x18005acb2  mov     rcx, rbx; FastMutex
0x18005acb5  call    cs:__imp_ExAcquireFastMutex
0x18005acbc  nop     dword ptr [rax+rax+00h]
0x18005acc1  lea     rcx, [rsi+238h]; PKTIMER
0x18005acc8  mov     dword ptr [rsi+228h], 1
0x18005acd2  call    cs:__imp_KeCancelTimer
0x18005acd9  nop     dword ptr [rax+rax+00h]
0x18005acde  mov     rcx, rbx; FastMutex
0x18005ace1  call    cs:__imp_ExReleaseFastMutex
0x18005ace8  nop     dword ptr [rax+rax+00h]
0x18005aced  jmp     loc_18005B20D
0x18005acf2  mov     r14, [rsi+20h]
0x18005acf6  cmp     rdi, [r14+30h]
0x18005acfa  jz      short loc_18005AD4A
0x18005acfc  lea     rax, WPP_RECORDER_INITIALIZED
0x18005ad03  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18005ad0a  jz      short loc_18005AD40
0x18005ad0c  mov     rcx, cs:WPP_GLOBAL_Control
0x18005ad13  cmp     [rcx+48h], r12w
0x18005ad18  jz      short loc_18005AD40
0x18005ad1a  mov     rcx, [rcx+40h]
0x18005ad1e  lea     rax, WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids
0x18005ad25  mov     r9d, 22h ; '"'
0x18005ad2b  mov     [rsp+68h+var_40], rdi
0x18005ad30  mov     dl, 5
0x18005ad32  mov     [rsp+68h+var_48], rax
0x18005ad37  lea     r8d, [r9-21h]
0x18005ad3b  call    WPP_RECORDER_SF_q
0x18005ad40  mov     ebp, 0C000000Eh
0x18005ad45  jmp     loc_18005B210
0x18005ad4a  movzx   ecx, byte ptr [rbx+1]
0x18005ad4e  cmp     ecx, 9
0x18005ad51  ja      loc_18005B0D2
0x18005ad57  jz      loc_18005B04B
0x18005ad5d  test    ecx, ecx
0x18005ad5f  jz      loc_18005AFF8
0x18005ad65  sub     ecx, 1
0x18005ad68  jz      loc_18005AF99
0x18005ad6e  sub     ecx, 1
0x18005ad71  jz      loc_18005AF48
0x18005ad77  sub     ecx, 1
0x18005ad7a  jz      loc_18005AF17
0x18005ad80  sub     ecx, 1
0x18005ad83  jz      loc_18005AEC6
0x18005ad89  sub     ecx, 1
0x18005ad8c  jz      loc_18005AE95
0x18005ad92  sub     ecx, 1
0x18005ad95  jz      loc_18005AE95
0x18005ad9b  sub     ecx, 1
0x18005ad9e  jz      loc_18005AE42
0x18005ada4  cmp     ecx, 1
0x18005ada7  jnz     loc_18005B210
0x18005adad  mov     rdx, [rbx+8]
0x18005adb1  mov     rcx, [rdx]
0x18005adb4  cmp     rcx, qword ptr cs:KSMEDIUMSETID_Standard.Data1
0x18005adbb  jnz     loc_18005B210
0x18005adc1  mov     rcx, [rdx+8]
0x18005adc5  cmp     rcx, qword ptr cs:KSMEDIUMSETID_Standard.Data4
0x18005adcc  jnz     loc_18005B210
0x18005add2  mov     ecx, 38h ; '8'
0x18005add7  cmp     [rbx+10h], cx
0x18005addb  jnz     loc_18005B210
0x18005ade1  mov     edx, 100h
0x18005ade6  cmp     [rbx+12h], dx
0x18005adea  jnz     loc_18005B210
0x18005adf0  mov     rax, [rbx+18h]
0x18005adf4  lea     rcx, InterfaceReference
0x18005adfb  mov     [rax+10h], rcx
0x18005adff  lea     rcx, InterfaceDereference
0x18005ae06  mov     [rax+18h], rcx
0x18005ae0a  lea     rcx, ReferenceDeviceObject
0x18005ae11  mov     [rax+20h], rcx
0x18005ae15  lea     rcx, DereferenceDeviceObject
0x18005ae1c  mov     [rax+28h], rcx
0x18005ae20  lea     rcx, QueryReferenceString
0x18005ae27  mov     [rax+30h], rcx
0x18005ae2b  mov     rcx, rsi
0x18005ae2e  mov     dword ptr [rax], 1000038h
0x18005ae34  mov     [rax+8], rsi
0x18005ae38  call    InterfaceReference
  ... truncated ...
```
