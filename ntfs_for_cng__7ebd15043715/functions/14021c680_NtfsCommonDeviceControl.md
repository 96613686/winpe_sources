# NtfsCommonDeviceControl

- ea: `0x14021c680`
- end: `0x14021cf44`
- name: `NtfsCommonDeviceControl`
- size: `2244`
- prototype: `__int64 __fastcall(__int64, IRP *)`
- caller_count: `3`
- callee_count: `17`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140015d10`
- `0x14017b350`
- `0x14021c370`

## callees

- `0x1400054e8`
- `0x140007670`
- `0x140007ea0`
- `0x1400082b0`
- `0x140008740`
- `0x14000c290`
- `0x140010be0`
- `0x140020de0`
- `0x140044618`
- `0x140045208`
- `0x140196e30`
- `0x1401cf5c0`
- `0x1401d28c0`
- `0x1401d2cec`
- `0x1401dbe7c`
- `0x14021c680`
- `0x14023030c`

## import_xrefs

- `ntoskrnl!IoGetActivityIdIrp` at `0x14021c967`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14021c967`
- `ntoskrnl!KeSetEvent` at `0x14021cebb`
- `ntoskrnl!KeSetEvent` at `0x14021cefa`
- `ntoskrnl!KeSetEvent` at `0x1402b53b0`
- `ntoskrnl!KeSetEvent` at `0x1402b53ea`
- `ntoskrnl!KeSetEvent` at `0x14021cebb`
- `ntoskrnl!KeSetEvent` at `0x14021cefa`
- `ntoskrnl!KeSetEvent` at `0x1402b53b0`
- `ntoskrnl!KeSetEvent` at `0x1402b53ea`
- `ntoskrnl!ZwClose` at `0x14021ca35`
- `ntoskrnl!ZwClose` at `0x14021ca35`
- `ntoskrnl!PsCreateSystemThread` at `0x14021ca06`
- `ntoskrnl!PsCreateSystemThread` at `0x14021ca06`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x14021ce53`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x1402b5346`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x14021ce53`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x1402b5346`
- `ntoskrnl!IoGetActivityIdThread` at `0x14021c98a`
- `ntoskrnl!IoGetActivityIdThread` at `0x14021c98a`
- `ntoskrnl!KeWaitForSingleObject` at `0x14021c88c`
- `ntoskrnl!KeWaitForSingleObject` at `0x14021cdbe`
- `ntoskrnl!KeWaitForSingleObject` at `0x14021c88c`
- `ntoskrnl!KeWaitForSingleObject` at `0x14021cdbe`
- `ntoskrnl!KeInitializeEvent` at `0x14021c912`
- `ntoskrnl!KeInitializeEvent` at `0x14021cb03`
- `ntoskrnl!KeInitializeEvent` at `0x14021c912`
- `ntoskrnl!KeInitializeEvent` at `0x14021cb03`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14021c868`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14021c8b1`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14021cf09`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1402b53fd`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14021c868`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14021c8b1`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14021cf09`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1402b53fd`
- `ntoskrnl!ExFreePoolWithTag` at `0x14021cf24`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b541c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14021cf24`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b541c`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14021c8d2`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14021c8d2`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14021c84f`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14021c89b`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14021ceda`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1402b53cb`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14021c84f`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14021c89b`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14021ceda`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1402b53cb`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14021ca6f`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14021ca6f`
- `ntoskrnl!ExReleaseResourceLite` at `0x14021ce6e`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402b5361`
- `ntoskrnl!ExReleaseResourceLite` at `0x14021ce6e`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402b5361`

## pseudocode

```c
__int64 __fastcall NtfsCommonDeviceControl(__int64 a1, IRP *a2)
{
  IRP *v2; // rbx
  volatile signed __int32 *v4; // r15
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rdx
  PFILE_OBJECT FileObject; // rax
  unsigned __int64 FsContext; // r8
  _BYTE *FsContext2; // rax
  __int64 v9; // r14
  int v10; // ecx
  int v11; // eax
  int v12; // edi
  _QWORD *v13; // rcx
  char *StartContext; // r12
  DWORD LowPart; // eax
  struct _FAST_MUTEX *v17; // rcx
  __int64 v18; // rcx
  int ActivityIdIrp; // eax
  __int64 v20; // r9
  _OWORD *ActivityIdThread; // rcx
  NTSTATUS v22; // eax
  __int64 v23; // rdx
  __int64 v24; // rcx
  __int64 v25; // r9
  unsigned int v26; // eax
  int v27; // r11d
  int Flags; // r10d
  __int64 v29; // r9
  unsigned int v30; // eax
  unsigned __int16 v31; // cx
  unsigned int v32; // r8d
  __int64 v33; // r8
  struct _IO_STACK_LOCATION *v34; // rax
  struct _IO_STACK_LOCATION *v35; // rax
  PVOID v36; // rbx
  PLARGE_INTEGER Timeout; // [rsp+20h] [rbp-118h]
  char v38; // [rsp+50h] [rbp-E8h]
  char v39; // [rsp+51h] [rbp-E7h]
  char v40; // [rsp+52h] [rbp-E6h]
  PVOID P; // [rsp+58h] [rbp-E0h] BYREF
  unsigned int v42; // [rsp+60h] [rbp-D8h]
  DWORD v43; // [rsp+64h] [rbp-D4h]
  DWORD v44; // [rsp+68h] [rbp-D0h]
  _QWORD *v45; // [rsp+70h] [rbp-C8h]
  __int64 v46; // [rsp+78h] [rbp-C0h]
  char *v47; // [rsp+80h] [rbp-B8h]
  void *ThreadHandle; // [rsp+88h] [rbp-B0h] BYREF
  unsigned __int64 v49; // [rsp+90h] [rbp-A8h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+98h] [rbp-A0h] BYREF
  _QWORD v51[4]; // [rsp+C8h] [rbp-70h] BYREF
  unsigned __int16 v52; // [rsp+E8h] [rbp-50h]
  __int64 v53; // [rsp+F0h] [rbp-48h]
  unsigned int v54; // [rsp+150h] [rbp+18h] BYREF
  IRP *v55; // [rsp+158h] [rbp+20h]

  v2 = a2;
  v55 = a2;
  v54 = 0;
  memset(v51, 0, sizeof(v51));
  v4 = 0;
  P = 0;
  memset(&ObjectAttributes, 0, 44);
  ThreadHandle = 0;
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  FileObject = CurrentStackLocation->FileObject;
  FsContext = (unsigned __int64)FileObject->FsContext;
  v49 = FsContext;
  if ( FsContext )
  {
    FsContext2 = FileObject->FsContext2;
    v9 = *(_QWORD *)(FsContext + 192);
    v10 = *(_DWORD *)(v9 + 4);
    if ( (v10 & 1) == 0 && (!FsContext2 || FsContext2[88] != 4 || (v10 & 2) == 0) )
      NtfsRaiseStatusInternal(a1, -1073741202, 0, 0, 0);
    v46 = *(_QWORD *)(FsContext + 192);
    if ( FsContext2 )
      v11 = (unsigned __int8)FsContext2[88];
    else
      v11 = 5;
  }
  else
  {
    v9 = 0;
    v46 = 0;
    v11 = 1;
  }
  v12 = 0;
  v13 = 0;
  v45 = 0;
  v43 = 0;
  StartContext = 0;
  v47 = 0;
  v39 = 0;
  v38 = 0;
  v40 = 0;
  if ( v11 != 4 )
  {
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(a1, 0xC000000D, 0xB0171u);
    NtfsExtendedCompleteRequestInternal(a1, v55, -1073741811, v55 != 0, 0);
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(0, 0xC000000D, 0xB0172u);
    return 3221225485LL;
  }
  LowPart = CurrentStackLocation->Parameters.Read.ByteOffset.LowPart;
  v44 = LowPart;
  v43 = LowPart;
  if ( LowPart != 508004 )
  {
    if ( LowPart != 5488640 )
      goto LABEL_59;
    if ( (*(_DWORD *)(a1 + 12) & 1) == 0 )
    {
      *(_DWORD *)(a1 + 4) |= 0x4000000u;
      NtfsRaiseStatusInternal(a1, -1073741608, 0, 0, 721304);
    }
    ExAcquireFastMutexUnsafe((PFAST_MUTEX)(v9 + 6520));
    while ( 1 )
    {
      v17 = (struct _FAST_MUTEX *)(v9 + 6520);
      if ( !*(_BYTE *)(v9 + 6576) )
        break;
      ExReleaseFastMutexUnsafe(v17);
      KeWaitForSingleObject((PVOID)(v9 + 6584), Executive, 0, 0, 0);
      ExAcquireFastMutexUnsafe((PFAST_MUTEX)(v9 + 6520));
    }
    *(_BYTE *)(v9 + 6576) = 1;
    ExReleaseFastMutexUnsafe(v17);
    v40 = 1;
    StartContext = (char *)ExAllocatePoolWithTag((POOL_TYPE)528, 0x38u, 0x3066744Eu);
    v47 = StartContext;
    *(_OWORD *)StartContext = 0;
    *((_OWORD *)StartContext + 1) = 0;
    *((_OWORD *)StartContext + 2) = 0;
    *((_QWORD *)StartContext + 6) = 0;
    *(_QWORD *)StartContext = v9;
    KeInitializeEvent((PRKEVENT)(StartContext + 32), NotificationEvent, 0);
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 512;
    ObjectAttributes.ObjectName = 0;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    if ( v2 )
    {
      ActivityIdIrp = IoGetActivityIdIrp(v55, StartContext + 16);
      ActivityIdThread = 0;
      if ( ActivityIdIrp >= 0 )
        ActivityIdThread = StartContext + 16;
      *((_QWORD *)StartContext + 1) = ActivityIdThread;
      v2 = v55;
    }
    else
    {
      ActivityIdThread = (_OWORD *)IoGetActivityIdThread(v18);
      if ( ActivityIdThread )
      {
        *((_OWORD *)StartContext + 1) = *ActivityIdThread;
        *((_QWORD *)StartContext + 1) = StartContext + 16;
      }
      else
      {
        *((_QWORD *)StartContext + 1) = 0;
      }
    }
    if ( (Microsoft_Windows_NtfsEnableBits & 0x8000000) != 0 )
    {
      LODWORD(Timeout) = 12;
      McTemplateK0pq_EtwWriteTransfer(
        (__int64)ActivityIdThread,
        (const EVENT_DESCRIPTOR *)WORKITEM_QUEUE,
        *((const GUID **)StartContext + 1),
        v20,
        (__int64)Timeout);
    }
    v22 = PsCreateSystemThread(
            &ThreadHandle,
            0x1FFFFFu,
            &ObjectAttributes,
            0,
            0,
            (PKSTART_ROUTINE)TxfThawRmsWorker,
            StartContext);
    v12 = v22;
    v42 = v22;
    if ( v22 < 0 )
    {
      if ( (Microsoft_Windows_NtfsEnableBits & 0x10000000) != 0 )
        McTemplateK0pqd_EtwWriteTransfer(v24, v23, *((const GUID **)StartContext + 1), v25, 12, v22);
    }
    else
    {
      NtfsPurgeFileRecordCache(a1);
      *(_DWORD *)(a1 + 4) |= 0x200u;
      ZwClose(ThreadHandle);
      *(_DWORD *)(a1 + 4) &= ~0x200u;
      v39 = 1;
      TxfSeekFirstRM(v9, (volatile signed __int32 **)&P);
      while ( 1 )
      {
        v4 = (volatile signed __int32 *)P;
        if ( !P )
          break;
        ExAcquireResourceExclusiveLite((PERESOURCE)(*((_QWORD *)P + 3) + 912LL), 1u);
        _InterlockedIncrement(v4 + 16);
        _InterlockedIncrement(v4 + 11);
        v38 = 1;
        v26 = TxfFreezeRmForSnapshot(a1, (__int64)v4, 0);
        v12 = v26;
        v42 = v26;
        if ( v26 == -1072103419 )
        {
          v12 = 0;
          v42 = 0;
        }
        else if ( v26 )
        {
          break;
        }
        TxfSeekNextRm((volatile signed __int32 **)&P);
      }
      if ( v12 >= 0 )
      {
        v12 = NtfsCheckpointForVolumeSnapshot(a1);
        v42 = v12;
      }
    }
    KeInitializeEvent((PRKEVENT)&v51[1], NotificationEvent, 0);
    v51[0] = a1;
    v13 = v51;
    v45 = v51;
    *(_DWORD *)(a1 + 12) |= 1u;
    goto LABEL_58;
  }
  v27 = *(_DWORD *)(v9 + 4);
  if ( (v27 & 2) == 0 )
  {
    Flags = CurrentStackLocation->Flags;
    if ( (Flags & 0x10) == 0 )
    {
      if ( (!a1 || (*(_DWORD *)(a1 + 16) & 0x100000) == 0)
        && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x20) != 0 )
      {
        v29 = *(_QWORD *)(v9 + 248);
        v30 = *(unsigned __int16 *)(v29 + 6);
        if ( v30 > 0x40 || (v30 & 1) != 0 )
        {
          v31 = 0;
          LODWORD(v55) = 0;
        }
        else
        {
          v31 = *(_WORD *)(v29 + 6);
          LODWORD(v55) = v31;
        }
        v52 = v31;
        v53 = v29 + 32;
        McTemplateU0ppwwdd_EtwWriteTransfer(
          v31 >> 1,
          (const EVENT_DESCRIPTOR *)devctrl_c557,
          KeGetCurrentThread(),
          v9,
          *(unsigned __int16 *)(v9 + 7872) >> 1,
          *(_QWORD *)(v9 + 7880),
          v31 >> 1,
          v29 + 32,
          v27,
          Flags);
      }
      v12 = -1073741790;
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(0, 0xC0000022, 0xB0239u);
      v42 = -1073741790;
      v13 = v45;
LABEL_58:
      FsContext = v49;
    }
  }
LABEL_59:
  if ( v12 >= 0 )
  {
    v34 = v2->Tail.Overlay.CurrentStackLocation;
    *(_OWORD *)&v34[-1].MajorFunction = *(_OWORD *)&v34->MajorFunction;
    *(_OWORD *)&v34[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&v34->Parameters.NotifyDirectoryEx.CompletionFilter;
    *(_OWORD *)(&v34[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&v34->Parameters.SetQuota + 6);
    v34[-1].FileObject = v34->FileObject;
    v34[-1].Control = 0;
    v35 = v2->Tail.Overlay.CurrentStackLocation;
    v35[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)DeviceControlCompletionRoutine;
    v35[-1].Context = v13;
    v35[-1].Control = 0;
    v35[-1].Control = 64;
    v35[-1].Control = -64;
    v35[-1].Control = -32;
    v12 = NtfsCallStorageDriver(a1, *(struct _DEVICE_OBJECT **)(v9 + 224), v2, v9, FsContext, 0, &v54);
    v42 = v12;
    if ( v12 >= 0 )
    {
      *(_QWORD *)(a1 + 112) = 0;
      v12 = v54;
      v42 = v54;
      if ( v54 == 259 && v45 )
        KeWaitForSingleObject(v45 + 1, Executive, 0, 0, 0);
      goto LABEL_82;
    }
    if ( NtfsStatusDebugFlags
      && (unsigned int)v12 < 0xFFFFFFED
      && v12 != -1073741802
      && v12 != -1073741807
      && (unsigned int)(v12 + 2147483643) > 1
      && v12 != -1073741608 )
    {
      v32 = 721531;
      goto LABEL_67;
    }
  }
  else if ( NtfsStatusDebugFlags
         && (unsigned int)v12 < 0xFFFFFFED
         && v12 != -1073741802
         && v12 != -1073741807
         && (unsigned int)(v12 + 2147483643) > 1
         && v12 != -1073741608 )
  {
    v32 = 721484;
LABEL_67:
    NtfsStatusTraceAndDebugInternal(0, v12, v32);
  }
  NtfsExtendedCompleteRequestInternal(0, v2, v12, v2 != 0, 0);
  if ( a1 && *(IRP **)(a1 + 112) == v2 )
    *(_QWORD *)(a1 + 112) = 0;
LABEL_82:
  if ( v44 == 5488640 )
  {
    if ( v4 )
    {
      _InterlockedDecrement(v4 + 13);
      if ( _InterlockedExchangeAdd(v4 + 16, 0xFFFFFFFF) == 1 )
        TxfDeleteTxfRmcb((char *)v4);
      P = 0;
    }
    if ( v38 )
    {
      TxfSeekFirstRM(v9, (volatile signed __int32 **)&P);
      while ( 1 )
      {
        v36 = P;
        if ( !P )
          break;
        if ( ExIsResourceAcquiredSharedLite((PERESOURCE)(*((_QWORD *)P + 3) + 912LL)) )
        {
          ExReleaseResourceLite((PERESOURCE)(*((_QWORD *)v36 + 3) + 912LL));
          _InterlockedDecrement((volatile signed __int32 *)v36 + 11);
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)v36 + 16, 0xFFFFFFFF) == 1 )
            TxfDeleteTxfRmcb((char *)v36);
        }
        TxfSeekNextRm((volatile signed __int32 **)&P);
      }
    }
    if ( v39 )
    {
      KeSetEvent((PRKEVENT)(StartContext + 32), 0, 0);
    }
    else if ( v40 )
    {
      ExAcquireFastMutexUnsafe((PFAST_MUTEX)(v9 + 6520));
      *(_BYTE *)(v9 + 6576) = 0;
      KeSetEvent((PRKEVENT)(v9 + 6584), 0, 0);
      ExReleaseFastMutexUnsafe((PFAST_MUTEX)(v9 + 6520));
    }
    if ( StartContext && !v39 )
      ExFreePoolWithTag(StartContext, 0);
  }
  NtfsCleanupIrpContext(a1, 1u, v33);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x14021c680  mov     rax, rsp
0x14021c683  mov     [rax+8], rcx
0x14021c687  push    rbx
0x14021c688  push    rsi
0x14021c689  push    rdi
0x14021c68a  push    r12
0x14021c68c  push    r14
0x14021c68e  push    r15
0x14021c690  sub     rsp, 108h
0x14021c697  mov     rbx, rdx
0x14021c69a  mov     [rax+20h], rdx
0x14021c69e  mov     rsi, rcx
0x14021c6a1  mov     dword ptr [rax+18h], 0
0x14021c6a8  xorps   xmm0, xmm0
0x14021c6ab  movups  xmmword ptr [rax-70h], xmm0
0x14021c6af  movups  xmmword ptr [rax-60h], xmm0
0x14021c6b3  mov     dword ptr [rax+10h], 0
0x14021c6ba  xor     r15d, r15d
0x14021c6bd  mov     [rsp+138h+P], r15
0x14021c6c2  xor     eax, eax
0x14021c6c4  movups  xmmword ptr [rsp+138h+ObjectAttributes.Length], xmm0
0x14021c6cc  movups  xmmword ptr [rsp+138h+ObjectAttributes.ObjectName], xmm0
0x14021c6d4  movups  xmmword ptr [rsp+138h+ObjectAttributes+1Ch], xmm0
0x14021c6dc  mov     [rsp+138h+ThreadHandle], rax
0x14021c6e4  mov     rdx, [rdx+0B8h]
0x14021c6eb  mov     rax, [rdx+30h]
0x14021c6ef  mov     r8, [rax+18h]
0x14021c6f3  mov     [rsp+138h+var_A8], r8
0x14021c6fb  test    r8, r8
0x14021c6fe  jz      short loc_14021C754
0x14021c700  mov     rax, [rax+20h]
0x14021c704  mov     r14, [r8+0C0h]
0x14021c70b  mov     ecx, [r14+4]
0x14021c70f  test    cl, 1
0x14021c712  jnz     short loc_14021C73D
0x14021c714  test    rax, rax
0x14021c717  jz      short loc_14021C724
0x14021c719  cmp     byte ptr [rax+58h], 4
0x14021c71d  jnz     short loc_14021C724
0x14021c71f  test    cl, 2
0x14021c722  jnz     short loc_14021C73D
0x14021c724  mov     [rsp+138h+Timeout], r15
0x14021c729  xor     r9d, r9d
0x14021c72c  xor     r8d, r8d
0x14021c72f  mov     edx, 0C000026Eh
0x14021c734  mov     rcx, rsi
0x14021c737  call    NtfsRaiseStatusInternal
0x14021c73c  int     3; Trap to Debugger
0x14021c73d  mov     [rsp+138h+var_C0], r14
0x14021c742  test    rax, rax
0x14021c745  jnz     short loc_14021C74E
0x14021c747  mov     eax, 5
0x14021c74c  jmp     short loc_14021C760
0x14021c74e  movzx   eax, byte ptr [rax+58h]
0x14021c752  jmp     short loc_14021C760
0x14021c754  xor     r14d, r14d
0x14021c757  mov     [rsp+138h+var_C0], r14
0x14021c75c  lea     eax, [r14+1]
0x14021c760  xor     edi, edi
0x14021c762  xor     ecx, ecx
0x14021c764  mov     [rsp+138h+var_C8], rcx
0x14021c769  mov     [rsp+138h+var_D4], ecx
0x14021c76d  xor     r12d, r12d
0x14021c770  mov     [rsp+138h+var_B8], r12
0x14021c778  mov     [rsp+138h+var_E7], cl
0x14021c77c  mov     [rsp+138h+var_E8], cl
0x14021c780  mov     [rsp+138h+var_E6], cl
0x14021c784  cmp     eax, 4
0x14021c787  jz      short loc_14021C7F6
0x14021c789  mov     al, cs:NtfsStatusDebugFlags
0x14021c78f  mov     ebx, 0C000000Dh
0x14021c794  test    al, al
0x14021c796  jz      short loc_14021C7A8
0x14021c798  mov     r8d, 0B0171h
0x14021c79e  mov     edx, ebx
0x14021c7a0  mov     rcx, rsi
0x14021c7a3  call    NtfsStatusTraceAndDebugInternal
0x14021c7a8  mov     rcx, [rsp+138h+arg_18]
0x14021c7b0  test    rcx, rcx
0x14021c7b3  setnz   r9b
0x14021c7b7  mov     dword ptr [rsp+138h+Timeout], edi
0x14021c7bb  mov     r8d, ebx
0x14021c7be  mov     rdx, rcx
0x14021c7c1  mov     rcx, rsi
0x14021c7c4  call    NtfsExtendedCompleteRequestInternal
0x14021c7c9  mov     al, cs:NtfsStatusDebugFlags
0x14021c7cf  test    al, al
0x14021c7d1  jz      short loc_14021C7E2
0x14021c7d3  mov     r8d, 0B0172h
0x14021c7d9  mov     edx, ebx
0x14021c7db  xor     ecx, ecx
0x14021c7dd  call    NtfsStatusTraceAndDebugInternal
0x14021c7e2  mov     eax, ebx
0x14021c7e4  add     rsp, 108h
0x14021c7eb  pop     r15
0x14021c7ed  pop     r14
0x14021c7ef  pop     r12
0x14021c7f1  pop     rdi
0x14021c7f2  pop     rsi
0x14021c7f3  pop     rbx
0x14021c7f4  retn
0x14021c7f6  mov     eax, [rdx+18h]
0x14021c7f9  mov     [rsp+138h+var_D0], eax
0x14021c7fd  mov     [rsp+138h+var_D4], eax
0x14021c801  cmp     eax, 7C064h
0x14021c806  jz      loc_14021CB2D
0x14021c80c  cmp     eax, 53C000h
0x14021c811  jnz     loc_14021CC22
0x14021c817  mov     eax, [rsi+0Ch]
0x14021c81a  test    al, 1
0x14021c81c  jnz     short loc_14021C845
0x14021c81e  bts     dword ptr [rsi+4], 1Ah
0x14021c823  mov     al, cs:NtfsStatusDebugFlags
0x14021c829  mov     [rsp+138h+Timeout], 0B0198h
0x14021c832  xor     r9d, r9d
0x14021c835  xor     r8d, r8d
0x14021c838  mov     edx, 0C00000D8h
0x14021c83d  mov     rcx, rsi
0x14021c840  call    NtfsRaiseStatusInternal
0x14021c845  lea     rdi, [r14+1978h]
0x14021c84c  mov     rcx, rdi; FastMutex
0x14021c84f  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14021c856  nop     dword ptr [rax+rax+00h]
0x14021c85b  mov     rcx, rdi; FastMutex
0x14021c85e  cmp     byte ptr [r14+19B0h], 0
0x14021c866  jz      short loc_14021C8A9
0x14021c868  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14021c86f  nop     dword ptr [rax+rax+00h]
0x14021c874  lea     rcx, [r14+19B8h]; Object
0x14021c87b  mov     [rsp+138h+Timeout], 0; Timeout
0x14021c884  xor     r9d, r9d; Alertable
0x14021c887  xor     r8d, r8d; WaitMode
0x14021c88a  xor     edx, edx; WaitReason
0x14021c88c  call    cs:__imp_KeWaitForSingleObject
0x14021c893  nop     dword ptr [rax+rax+00h]
0x14021c898  mov     rcx, rdi; FastMutex
0x14021c89b  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14021c8a2  nop     dword ptr [rax+rax+00h]
0x14021c8a7  jmp     short loc_14021C85B
0x14021c8a9  mov     byte ptr [r14+19B0h], 1
0x14021c8b1  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14021c8b8  nop     dword ptr [rax+rax+00h]
0x14021c8bd  mov     [rsp+138h+var_E6], 1
0x14021c8c2  mov     edx, 38h ; '8'; NumberOfBytes
0x14021c8c7  mov     ecx, 210h; PoolType
0x14021c8cc  mov     r8d, 3066744Eh; Tag
0x14021c8d2  call    cs:__imp_ExAllocatePoolWithTag
0x14021c8d9  nop     dword ptr [rax+rax+00h]
0x14021c8de  mov     r12, rax
0x14021c8e1  mov     [rsp+138h+var_B8], rax
0x14021c8e9  xorps   xmm0, xmm0
0x14021c8ec  xor     eax, eax
0x14021c8ee  movups  xmmword ptr [r12], xmm0
0x14021c8f3  movups  xmmword ptr [r12+10h], xmm0
0x14021c8f9  movups  xmmword ptr [r12+20h], xmm0
0x14021c8ff  mov     [r12+30h], rax
0x14021c904  mov     [r12], r14
0x14021c908  lea     rcx, [r12+20h]; Event
0x14021c90d  xor     r8d, r8d; State
0x14021c910  xor     edx, edx; Type
0x14021c912  call    cs:__imp_KeInitializeEvent
0x14021c919  nop     dword ptr [rax+rax+00h]
0x14021c91e  mov     [rsp+138h+ObjectAttributes.Length], 30h ; '0'
0x14021c929  xor     edi, edi
0x14021c92b  mov     [rsp+138h+ObjectAttributes.RootDirectory], rdi
0x14021c933  mov     [rsp+138h+ObjectAttributes.Attributes], 200h
0x14021c93e  mov     [rsp+138h+ObjectAttributes.ObjectName], rdi
0x14021c946  xorps   xmm0, xmm0
0x14021c949  movdqu  xmmword ptr [rsp+138h+ObjectAttributes.SecurityDescriptor], xmm0
0x14021c952  test    rbx, rbx
0x14021c955  jz      short loc_14021C98A
0x14021c957  lea     rbx, [r12+10h]
0x14021c95c  mov     rdx, rbx
0x14021c95f  mov     rcx, [rsp+138h+arg_18]
0x14021c967  call    cs:__imp_IoGetActivityIdIrp
0x14021c96e  nop     dword ptr [rax+rax+00h]
0x14021c973  mov     ecx, edi
0x14021c975  test    eax, eax
0x14021c977  cmovns  rcx, rbx
0x14021c97b  mov     [r12+8], rcx
0x14021c980  mov     rbx, [rsp+138h+arg_18]
0x14021c988  jmp     short loc_14021C9B6
0x14021c98a  call    cs:__imp_IoGetActivityIdThread
0x14021c991  nop     dword ptr [rax+rax+00h]
0x14021c996  mov     rcx, rax
0x14021c999  test    rax, rax
0x14021c99c  jz      short loc_14021C9B1
0x14021c99e  lea     rax, [r12+10h]
0x14021c9a3  movups  xmm0, xmmword ptr [rcx]
0x14021c9a6  movdqu  xmmword ptr [rax], xmm0
0x14021c9aa  mov     [r12+8], rax
0x14021c9af  jmp     short loc_14021C9B6
0x14021c9b1  mov     [r12+8], rdi
0x14021c9b6  test    byte ptr cs:Microsoft_Windows_NtfsEnableBits+3, 8
0x14021c9bd  jz      short loc_14021C9D8
0x14021c9bf  mov     r8, [r12+8]
0x14021c9c4  mov     dword ptr [rsp+138h+Timeout], 0Ch
0x14021c9cc  lea     rdx, WORKITEM_QUEUE
0x14021c9d3  call    McTemplateK0pq_EtwWriteTransfer
0x14021c9d8  mov     [rsp+138h+StartContext], r12; StartContext
0x14021c9dd  lea     rax, TxfThawRmsWorker
0x14021c9e4  mov     [rsp+138h+StartRoutine], rax; StartRoutine
0x14021c9e9  mov     [rsp+138h+Timeout], rdi; ClientId
0x14021c9ee  xor     r9d, r9d; ProcessHandle
0x14021c9f1  lea     r8, [rsp+138h+ObjectAttributes]; ObjectAttributes
0x14021c9f9  mov     edx, 1FFFFFh; DesiredAccess
0x14021c9fe  lea     rcx, [rsp+138h+ThreadHandle]; ThreadHandle
0x14021ca06  call    cs:__imp_PsCreateSystemThread
0x14021ca0d  nop     dword ptr [rax+rax+00h]
0x14021ca12  mov     edi, eax
0x14021ca14  mov     [rsp+138h+var_D8], eax
0x14021ca18  test    eax, eax
0x14021ca1a  js      loc_14021CAD7
0x14021ca20  mov     rcx, rsi
0x14021ca23  call    NtfsPurgeFileRecordCache
0x14021ca28  bts     dword ptr [rsi+4], 9
0x14021ca2d  mov     rcx, [rsp+138h+ThreadHandle]; Handle
0x14021ca35  call    cs:__imp_ZwClose
0x14021ca3c  nop     dword ptr [rax+rax+00h]
0x14021ca41  btr     dword ptr [rsi+4], 9
0x14021ca46  mov     [rsp+138h+var_E7], 1
0x14021ca4b  lea     rdx, [rsp+138h+P]
0x14021ca50  mov     rcx, r14
0x14021ca53  call    TxfSeekFirstRM
0x14021ca58  mov     r15, [rsp+138h+P]
0x14021ca5d  test    r15, r15
0x14021ca60  jz      short loc_14021CABB
0x14021ca62  mov     rcx, [r15+18h]
0x14021ca66  add     rcx, 390h; Resource
0x14021ca6d  mov     dl, 1; Wait
0x14021ca6f  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14021ca76  nop     dword ptr [rax+rax+00h]
0x14021ca7b  lock inc dword ptr [r15+40h]
0x14021ca80  lock inc dword ptr [r15+2Ch]
0x14021ca85  mov     [rsp+138h+var_E8], 1
0x14021ca8a  xor     r8d, r8d
0x14021ca8d  mov     rdx, r15
0x14021ca90  mov     rcx, rsi; int
0x14021ca93  call    TxfFreezeRmForSnapshot
0x14021ca98  mov     edi, eax
0x14021ca9a  mov     [rsp+138h+var_D8], eax
0x14021ca9e  cmp     eax, 0C0190005h
0x14021caa3  jnz     short loc_14021CAB7
0x14021caa5  xor     edi, edi
0x14021caa7  mov     [rsp+138h+var_D8], edi
0x14021caab  lea     rcx, [rsp+138h+P]
0x14021cab0  call    TxfSeekNextRm
0x14021cab5  jmp     short loc_14021CA58
0x14021cab7  test    eax, eax
0x14021cab9  jz      short loc_14021CAAB
0x14021cabb  test    edi, edi
0x14021cabd  js      short loc_14021CAF6
0x14021cabf  lea     rdx, [rsp+138h+arg_8]
0x14021cac7  mov     rcx, rsi; int
0x14021caca  call    NtfsCheckpointForVolumeSnapshot
0x14021cacf  mov     edi, eax
0x14021cad1  mov     [rsp+138h+var_D8], eax
0x14021cad5  jmp     short loc_14021CAF6
0x14021cad7  test    byte ptr cs:Microsoft_Windows_NtfsEnableBits+3, 10h
0x14021cade  jz      short loc_14021CAF6
0x14021cae0  mov     r8, [r12+8]
0x14021cae5  mov     dword ptr [rsp+138h+StartRoutine], eax
0x14021cae9  mov     dword ptr [rsp+138h+Timeout], 0Ch
0x14021caf1  call    McTemplateK0pqd_EtwWriteTransfer
0x14021caf6  xor     r8d, r8d; State
0x14021caf9  xor     edx, edx; Type
0x14021cafb  lea     rcx, [rsp+138h+Event]; Event
0x14021cb03  call    cs:__imp_KeInitializeEvent
0x14021cb0a  nop     dword ptr [rax+rax+00h]
0x14021cb0f  mov     [rsp+138h+var_70], rsi
0x14021cb17  lea     rcx, [rsp+138h+var_70]
0x14021cb1f  mov     [rsp+138h+var_C8], rcx
0x14021cb24  or      dword ptr [rsi+0Ch], 1
0x14021cb28  jmp     loc_14021CC1A
0x14021cb2d  mov     r11d, [r14+4]
0x14021cb31  test    r11b, 2
0x14021cb35  jnz     loc_14021CC22
0x14021cb3b  movzx   r10d, byte ptr [rdx+2]
0x14021cb40  test    r10b, 10h
0x14021cb44  jnz     loc_14021CC22
0x14021cb4a  test    rsi, rsi
0x14021cb4d  jz      short loc_14021CB5D
0x14021cb4f  mov     eax, [rsi+10h]
0x14021cb52  bt      rax, 14h
0x14021cb57  jb      loc_14021CBF3
0x14021cb5d  mov     rax, cs:Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits
0x14021cb64  test    al, 20h
0x14021cb66  jz      loc_14021CBF3
0x14021cb6c  mov     r9, [r14+0F8h]
0x14021cb73  movzx   eax, word ptr [r9+6]
0x14021cb78  cmp     eax, 40h ; '@'
0x14021cb7b  ja      short loc_14021CB8C
0x14021cb7d  test    al, 1
0x14021cb7f  jnz     short loc_14021CB8C
0x14021cb81  mov     ecx, eax
0x14021cb83  mov     dword ptr [rsp+138h+arg_18], eax
0x14021cb8a  jmp     short loc_14021CB95
0x14021cb8c  xor     ecx, ecx
0x14021cb8e  mov     dword ptr [rsp+138h+arg_18], ecx
0x14021cb95  mov     [rsp+138h+var_50], cx
  ... truncated ...
```
