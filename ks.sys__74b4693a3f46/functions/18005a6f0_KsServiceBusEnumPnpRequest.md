# KsServiceBusEnumPnpRequest

- ea: `0x18005a6f0`
- end: `0x18005b082`
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
- `0x180019fc0`
- `0x180035e58`
- `0x18003665c`
- `0x1800597dc`
- `0x180059858`
- `0x18005a534`
- `0x18005a6f0`
- `0x18005f160`
- `0x18005f2e0`
- `0x18005f87c`
- `0x180060d50`
- `0x1800647d0`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x18005a9ed`
- `ntoskrnl!RtlFreeUnicodeString` at `0x18005a9ed`
- `ntoskrnl!IoSetDeviceInterfaceState` at `0x18005a9dd`
- `ntoskrnl!IoSetDeviceInterfaceState` at `0x18005a9dd`
- `ntoskrnl!IoDetachDevice` at `0x18005aa23`
- `ntoskrnl!IoDetachDevice` at `0x18005aa23`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x18005b00e`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x18005b00e`
- `ntoskrnl!ExReleaseFastMutex` at `0x18005a82d`
- `ntoskrnl!ExReleaseFastMutex` at `0x18005a8b6`
- `ntoskrnl!ExReleaseFastMutex` at `0x18005a951`
- `ntoskrnl!ExReleaseFastMutex` at `0x18005a993`
- `ntoskrnl!ExReleaseFastMutex` at `0x18005aaff`
- `ntoskrnl!ExReleaseFastMutex` at `0x18005ab41`
- `ntoskrnl!ExReleaseFastMutex` at `0x18005a82d`
- `ntoskrnl!ExReleaseFastMutex` at `0x18005a8b6`
- `ntoskrnl!ExReleaseFastMutex` at `0x18005a951`
- `ntoskrnl!ExReleaseFastMutex` at `0x18005a993`
- `ntoskrnl!ExReleaseFastMutex` at `0x18005aaff`
- `ntoskrnl!ExReleaseFastMutex` at `0x18005ab41`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18005affe`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18005affe`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x18005a9b2`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x18005a9c5`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x18005a9b2`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x18005a9c5`
- `ntoskrnl!KeCancelTimer` at `0x18005a941`
- `ntoskrnl!KeCancelTimer` at `0x18005a984`
- `ntoskrnl!KeCancelTimer` at `0x18005aaef`
- `ntoskrnl!KeCancelTimer` at `0x18005ab32`
- `ntoskrnl!KeCancelTimer` at `0x18005a941`
- `ntoskrnl!KeCancelTimer` at `0x18005a984`
- `ntoskrnl!KeCancelTimer` at `0x18005aaef`
- `ntoskrnl!KeCancelTimer` at `0x18005ab32`
- `ntoskrnl!ExAcquireFastMutex` at `0x18005a816`
- `ntoskrnl!ExAcquireFastMutex` at `0x18005a8a0`
- `ntoskrnl!ExAcquireFastMutex` at `0x18005a924`
- `ntoskrnl!ExAcquireFastMutex` at `0x18005a967`
- `ntoskrnl!ExAcquireFastMutex` at `0x18005aad2`
- `ntoskrnl!ExAcquireFastMutex` at `0x18005ab15`
- `ntoskrnl!ExAcquireFastMutex` at `0x18005a816`
- `ntoskrnl!ExAcquireFastMutex` at `0x18005a8a0`
- `ntoskrnl!ExAcquireFastMutex` at `0x18005a924`
- `ntoskrnl!ExAcquireFastMutex` at `0x18005a967`
- `ntoskrnl!ExAcquireFastMutex` at `0x18005aad2`
- `ntoskrnl!ExAcquireFastMutex` at `0x18005ab15`
- `ntoskrnl!IoFreeWorkItem` at `0x18005aa3b`
- `ntoskrnl!IoFreeWorkItem` at `0x18005aa5a`
- `ntoskrnl!IoFreeWorkItem` at `0x18005aa3b`
- `ntoskrnl!IoFreeWorkItem` at `0x18005aa5a`
- `ntoskrnl!KeFlushQueuedDpcs` at `0x18005a99f`
- `ntoskrnl!KeFlushQueuedDpcs` at `0x18005a99f`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x18005b03b`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x18005b03b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18005b047`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18005b047`
- `ntoskrnl!ExFreePoolWithTag` at `0x18005aa02`
- `ntoskrnl!ExFreePoolWithTag` at `0x18005aa72`
- `ntoskrnl!ExFreePoolWithTag` at `0x18005aa02`
- `ntoskrnl!ExFreePoolWithTag` at `0x18005aa72`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18005afb7`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18005afb7`

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
  __int64 SweeperPeriod; // rbx
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
        SweeperPeriod = ComputeNextSweeperPeriod(*DeviceExtension);
        ExAcquireFastMutex((PFAST_MUTEX)(v5 + 120));
        *(_DWORD *)(v5 + 176) = 0;
        ExReleaseFastMutex((PFAST_MUTEX)(v5 + 120));
        if ( SweeperPeriod )
        {
          v8 = QueueSweeperTimer(v5, SweeperPeriod);
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
0x18005a6f0  push    rbx
0x18005a6f2  push    rbp
0x18005a6f3  push    rsi
0x18005a6f4  push    rdi
0x18005a6f5  push    r12
0x18005a6f7  push    r14
0x18005a6f9  push    r15
0x18005a6fb  sub     rsp, 30h
0x18005a6ff  mov     rax, [rcx+40h]
0x18005a703  xor     r12d, r12d
0x18005a706  mov     r15, rdx
0x18005a709  mov     rdi, rcx
0x18005a70c  mov     rsi, [rax]
0x18005a70f  test    rsi, rsi
0x18005a712  jnz     short loc_18005A71E
0x18005a714  mov     eax, 0C000000Dh
0x18005a719  jmp     loc_18005B072
0x18005a71e  mov     ecx, [rsi+10h]
0x18005a721  mov     ebp, 0C00000BBh
0x18005a726  mov     rbx, [rdx+0B8h]
0x18005a72d  test    ecx, ecx
0x18005a72f  jz      loc_18005AB52
0x18005a735  cmp     ecx, 1
0x18005a738  jz      short loc_18005A744
0x18005a73a  mov     ebp, 0C0000010h
0x18005a73f  jmp     loc_18005B070
0x18005a744  movzx   ecx, byte ptr [rbx+1]
0x18005a748  test    ecx, ecx
0x18005a74a  jz      loc_18005B06D
0x18005a750  sub     ecx, 1
0x18005a753  jz      loc_18005AA8A
0x18005a759  sub     ecx, 1
0x18005a75c  jz      loc_18005A8DC
0x18005a762  sub     ecx, 1
0x18005a765  jz      loc_18005A804
0x18005a76b  sub     ecx, 1
0x18005a76e  jz      loc_18005B06D
0x18005a774  sub     ecx, 1
0x18005a777  jz      loc_18005B06D
0x18005a77d  sub     ecx, 1
0x18005a780  jz      loc_18005B06D
0x18005a786  sub     ecx, 1
0x18005a789  jz      short loc_18005A7E7
0x18005a78b  cmp     ecx, 10h
0x18005a78e  jnz     loc_18005B070
0x18005a794  lea     rax, WPP_RECORDER_INITIALIZED
0x18005a79b  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18005a7a2  jz      loc_18005B06D
0x18005a7a8  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a7af  cmp     [rcx+48h], r12w
0x18005a7b4  jz      loc_18005B06D
0x18005a7ba  mov     r9d, 20h ; ' '
0x18005a7c0  mov     rcx, [rcx+40h]
0x18005a7c4  lea     rax, WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids
0x18005a7cb  mov     [rsp+68h+var_40], rdi
0x18005a7d0  mov     r8d, 1
0x18005a7d6  mov     dl, 5
0x18005a7d8  mov     [rsp+68h+var_48], rax
0x18005a7dd  call    WPP_RECORDER_SF_q
0x18005a7e2  jmp     loc_18005B06D
0x18005a7e7  mov     edx, [rbx+8]
0x18005a7ea  cmp     edx, 4
0x18005a7ed  jz      loc_18005B070
0x18005a7f3  lea     r8, [r15+38h]
0x18005a7f7  mov     rcx, rsi
0x18005a7fa  call    QueryDeviceRelations
0x18005a7ff  jmp     loc_18005AEA4
0x18005a804  mov     rcx, rsi
0x18005a807  mov     ebp, r12d
0x18005a80a  call    ComputeNextSweeperPeriod
0x18005a80f  lea     rcx, [rsi+78h]; FastMutex
0x18005a813  mov     rbx, rax
0x18005a816  call    cs:__imp_ExAcquireFastMutex
0x18005a81d  nop     dword ptr [rax+rax+00h]
0x18005a822  lea     rcx, [rsi+78h]; FastMutex
0x18005a826  mov     [rsi+0B0h], r12d
0x18005a82d  call    cs:__imp_ExReleaseFastMutex
0x18005a834  nop     dword ptr [rax+rax+00h]
0x18005a839  test    rbx, rbx
0x18005a83c  jz      short loc_18005A896
0x18005a83e  mov     rdx, rbx
0x18005a841  mov     rcx, rsi
0x18005a844  call    QueueSweeperTimer
0x18005a849  mov     ebp, eax
0x18005a84b  lea     rax, WPP_RECORDER_INITIALIZED
0x18005a852  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18005a859  jz      short loc_18005A88E
0x18005a85b  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a862  cmp     [rcx+48h], r12w
0x18005a867  jz      short loc_18005A88E
0x18005a869  mov     rcx, [rcx+40h]
0x18005a86d  lea     rax, WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids
0x18005a874  mov     r9d, 1Fh
0x18005a87a  mov     dword ptr [rsp+68h+var_40], ebp
0x18005a87e  mov     dl, 5
0x18005a880  mov     [rsp+68h+var_48], rax
0x18005a885  lea     r8d, [r9-1Eh]
0x18005a889  call    WPP_RECORDER_SF_D
0x18005a88e  test    ebp, ebp
0x18005a890  js      loc_18005B070
0x18005a896  lea     rbx, [rsi+1F0h]
0x18005a89d  mov     rcx, rbx; FastMutex
0x18005a8a0  call    cs:__imp_ExAcquireFastMutex
0x18005a8a7  nop     dword ptr [rax+rax+00h]
0x18005a8ac  mov     rcx, rbx; FastMutex
0x18005a8af  mov     [rsi+228h], r12d
0x18005a8b6  call    cs:__imp_ExReleaseFastMutex
0x18005a8bd  nop     dword ptr [rax+rax+00h]
0x18005a8c2  cmp     dword ptr [rsi+22Ch], 1
0x18005a8c9  jnz     loc_18005B070
0x18005a8cf  mov     rcx, rsi
0x18005a8d2  call    QueueRescanTimer
0x18005a8d7  jmp     loc_18005AEA4
0x18005a8dc  lea     rax, WPP_RECORDER_INITIALIZED
0x18005a8e3  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18005a8ea  jz      short loc_18005A920
0x18005a8ec  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a8f3  cmp     [rcx+48h], r12w
0x18005a8f8  jz      short loc_18005A920
0x18005a8fa  mov     rcx, [rcx+40h]
0x18005a8fe  lea     rax, WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids
0x18005a905  mov     r9d, 21h ; '!'
0x18005a90b  mov     [rsp+68h+var_40], rdi
0x18005a910  mov     dl, 5
0x18005a912  mov     [rsp+68h+var_48], rax
0x18005a917  lea     r8d, [r9-20h]
0x18005a91b  call    WPP_RECORDER_SF_q
0x18005a920  lea     rcx, [rsi+78h]; FastMutex
0x18005a924  call    cs:__imp_ExAcquireFastMutex
0x18005a92b  nop     dword ptr [rax+rax+00h]
0x18005a930  lea     rcx, [rsi+0C0h]; PKTIMER
0x18005a937  mov     dword ptr [rsi+0B0h], 1
0x18005a941  call    cs:__imp_KeCancelTimer
0x18005a948  nop     dword ptr [rax+rax+00h]
0x18005a94d  lea     rcx, [rsi+78h]; FastMutex
0x18005a951  call    cs:__imp_ExReleaseFastMutex
0x18005a958  nop     dword ptr [rax+rax+00h]
0x18005a95d  lea     rbx, [rsi+1F0h]
0x18005a964  mov     rcx, rbx; FastMutex
0x18005a967  call    cs:__imp_ExAcquireFastMutex
0x18005a96e  nop     dword ptr [rax+rax+00h]
0x18005a973  lea     rcx, [rsi+238h]; PKTIMER
0x18005a97a  mov     dword ptr [rsi+228h], 1
0x18005a984  call    cs:__imp_KeCancelTimer
0x18005a98b  nop     dword ptr [rax+rax+00h]
0x18005a990  mov     rcx, rbx; FastMutex
0x18005a993  call    cs:__imp_ExReleaseFastMutex
0x18005a99a  nop     dword ptr [rax+rax+00h]
0x18005a99f  call    cs:__imp_KeFlushQueuedDpcs
0x18005a9a6  nop     dword ptr [rax+rax+00h]
0x18005a9ab  lea     rcx, [rsi+0B8h]; RunRef
0x18005a9b2  call    cs:__imp_ExWaitForRundownProtectionRelease
0x18005a9b9  nop     dword ptr [rax+rax+00h]
0x18005a9be  lea     rcx, [rsi+230h]; RunRef
0x18005a9c5  call    cs:__imp_ExWaitForRundownProtectionRelease
0x18005a9cc  nop     dword ptr [rax+rax+00h]
0x18005a9d1  cmp     [rsi+58h], r12
0x18005a9d5  jz      short loc_18005A9F9
0x18005a9d7  xor     edx, edx; Enable
0x18005a9d9  lea     rcx, [rsi+50h]; SymbolicLinkName
0x18005a9dd  call    cs:__imp_IoSetDeviceInterfaceState
0x18005a9e4  nop     dword ptr [rax+rax+00h]
0x18005a9e9  lea     rcx, [rsi+50h]; UnicodeString
0x18005a9ed  call    cs:__imp_RtlFreeUnicodeString
0x18005a9f4  nop     dword ptr [rax+rax+00h]
0x18005a9f9  mov     rcx, [rsi+158h]; P
0x18005aa00  xor     edx, edx; Tag
0x18005aa02  call    cs:__imp_ExFreePoolWithTag
0x18005aa09  nop     dword ptr [rax+rax+00h]
0x18005aa0e  mov     rcx, rsi
0x18005aa11  call    RescanUninitialize
0x18005aa16  cmp     [rsi+160h], r12d
0x18005aa1d  jz      short loc_18005AA2F
0x18005aa1f  mov     rcx, [rsi+68h]; TargetDevice
0x18005aa23  call    cs:__imp_IoDetachDevice
0x18005aa2a  nop     dword ptr [rax+rax+00h]
0x18005aa2f  mov     rcx, [rsi+148h]; IoWorkItem
0x18005aa36  test    rcx, rcx
0x18005aa39  jz      short loc_18005AA4E
0x18005aa3b  call    cs:__imp_IoFreeWorkItem
0x18005aa42  nop     dword ptr [rax+rax+00h]
0x18005aa47  mov     [rsi+148h], r12
0x18005aa4e  mov     rcx, [rsi+2C0h]; IoWorkItem
0x18005aa55  test    rcx, rcx
0x18005aa58  jz      short loc_18005AA6D
0x18005aa5a  call    cs:__imp_IoFreeWorkItem
0x18005aa61  nop     dword ptr [rax+rax+00h]
0x18005aa66  mov     [rsi+2C0h], r12
0x18005aa6d  xor     edx, edx; Tag
0x18005aa6f  mov     rcx, rsi; P
0x18005aa72  call    cs:__imp_ExFreePoolWithTag
0x18005aa79  nop     dword ptr [rax+rax+00h]
0x18005aa7e  mov     rax, [rdi+40h]
0x18005aa82  mov     [rax], r12
0x18005aa85  jmp     loc_18005B06D
0x18005aa8a  lea     rax, WPP_RECORDER_INITIALIZED
0x18005aa91  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18005aa98  jz      short loc_18005AACE
0x18005aa9a  mov     rcx, cs:WPP_GLOBAL_Control
0x18005aaa1  cmp     [rcx+48h], r12w
0x18005aaa6  jz      short loc_18005AACE
0x18005aaa8  mov     rcx, [rcx+40h]
0x18005aaac  lea     rax, WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids
0x18005aab3  mov     r9d, 1Eh
0x18005aab9  mov     [rsp+68h+var_40], rdi
0x18005aabe  mov     dl, 5
0x18005aac0  mov     [rsp+68h+var_48], rax
0x18005aac5  lea     r8d, [r9-1Dh]
0x18005aac9  call    WPP_RECORDER_SF_q
0x18005aace  lea     rcx, [rsi+78h]; FastMutex
0x18005aad2  call    cs:__imp_ExAcquireFastMutex
0x18005aad9  nop     dword ptr [rax+rax+00h]
0x18005aade  lea     rcx, [rsi+0C0h]; PKTIMER
0x18005aae5  mov     dword ptr [rsi+0B0h], 1
0x18005aaef  call    cs:__imp_KeCancelTimer
0x18005aaf6  nop     dword ptr [rax+rax+00h]
0x18005aafb  lea     rcx, [rsi+78h]; FastMutex
0x18005aaff  call    cs:__imp_ExReleaseFastMutex
0x18005ab06  nop     dword ptr [rax+rax+00h]
0x18005ab0b  lea     rbx, [rsi+1F0h]
0x18005ab12  mov     rcx, rbx; FastMutex
0x18005ab15  call    cs:__imp_ExAcquireFastMutex
0x18005ab1c  nop     dword ptr [rax+rax+00h]
0x18005ab21  lea     rcx, [rsi+238h]; PKTIMER
0x18005ab28  mov     dword ptr [rsi+228h], 1
0x18005ab32  call    cs:__imp_KeCancelTimer
0x18005ab39  nop     dword ptr [rax+rax+00h]
0x18005ab3e  mov     rcx, rbx; FastMutex
0x18005ab41  call    cs:__imp_ExReleaseFastMutex
0x18005ab48  nop     dword ptr [rax+rax+00h]
0x18005ab4d  jmp     loc_18005B06D
0x18005ab52  mov     r14, [rsi+20h]
0x18005ab56  cmp     rdi, [r14+30h]
0x18005ab5a  jz      short loc_18005ABAA
0x18005ab5c  lea     rax, WPP_RECORDER_INITIALIZED
0x18005ab63  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18005ab6a  jz      short loc_18005ABA0
0x18005ab6c  mov     rcx, cs:WPP_GLOBAL_Control
0x18005ab73  cmp     [rcx+48h], r12w
0x18005ab78  jz      short loc_18005ABA0
0x18005ab7a  mov     rcx, [rcx+40h]
0x18005ab7e  lea     rax, WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids
0x18005ab85  mov     r9d, 22h ; '"'
0x18005ab8b  mov     [rsp+68h+var_40], rdi
0x18005ab90  mov     dl, 5
0x18005ab92  mov     [rsp+68h+var_48], rax
0x18005ab97  lea     r8d, [r9-21h]
0x18005ab9b  call    WPP_RECORDER_SF_q
0x18005aba0  mov     ebp, 0C000000Eh
0x18005aba5  jmp     loc_18005B070
0x18005abaa  movzx   ecx, byte ptr [rbx+1]
0x18005abae  cmp     ecx, 9
0x18005abb1  ja      loc_18005AF32
0x18005abb7  jz      loc_18005AEAB
0x18005abbd  test    ecx, ecx
0x18005abbf  jz      loc_18005AE58
0x18005abc5  sub     ecx, 1
0x18005abc8  jz      loc_18005ADF9
0x18005abce  sub     ecx, 1
0x18005abd1  jz      loc_18005ADA8
0x18005abd7  sub     ecx, 1
0x18005abda  jz      loc_18005AD77
0x18005abe0  sub     ecx, 1
0x18005abe3  jz      loc_18005AD26
0x18005abe9  sub     ecx, 1
0x18005abec  jz      loc_18005ACF5
0x18005abf2  sub     ecx, 1
0x18005abf5  jz      loc_18005ACF5
0x18005abfb  sub     ecx, 1
0x18005abfe  jz      loc_18005ACA2
0x18005ac04  cmp     ecx, 1
0x18005ac07  jnz     loc_18005B070
0x18005ac0d  mov     rdx, [rbx+8]
0x18005ac11  mov     rcx, [rdx]
0x18005ac14  cmp     rcx, qword ptr cs:KSMEDIUMSETID_Standard.Data1
0x18005ac1b  jnz     loc_18005B070
0x18005ac21  mov     rcx, [rdx+8]
0x18005ac25  cmp     rcx, qword ptr cs:KSMEDIUMSETID_Standard.Data4
0x18005ac2c  jnz     loc_18005B070
0x18005ac32  mov     ecx, 38h ; '8'
0x18005ac37  cmp     [rbx+10h], cx
0x18005ac3b  jnz     loc_18005B070
0x18005ac41  mov     edx, 100h
0x18005ac46  cmp     [rbx+12h], dx
0x18005ac4a  jnz     loc_18005B070
0x18005ac50  mov     rax, [rbx+18h]
0x18005ac54  lea     rcx, InterfaceReference
0x18005ac5b  mov     [rax+10h], rcx
0x18005ac5f  lea     rcx, InterfaceDereference
0x18005ac66  mov     [rax+18h], rcx
0x18005ac6a  lea     rcx, ReferenceDeviceObject
0x18005ac71  mov     [rax+20h], rcx
0x18005ac75  lea     rcx, DereferenceDeviceObject
0x18005ac7c  mov     [rax+28h], rcx
0x18005ac80  lea     rcx, QueryReferenceString
0x18005ac87  mov     [rax+30h], rcx
0x18005ac8b  mov     rcx, rsi
0x18005ac8e  mov     dword ptr [rax], 1000038h
0x18005ac94  mov     [rax+8], rsi
0x18005ac98  call    InterfaceReference
  ... truncated ...
```
