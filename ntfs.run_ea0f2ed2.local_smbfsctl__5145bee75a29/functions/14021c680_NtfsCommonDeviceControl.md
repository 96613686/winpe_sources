# NtfsCommonDeviceControl

- ea: `0x14021c680`
- end: `0x14021cf44`
- name: `NtfsCommonDeviceControl`
- size: `2244`
- prototype: `__int64 __fastcall(int)`
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
__int64 __fastcall NtfsCommonDeviceControl(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rbx
  volatile signed __int32 *v6; // r15
  __int64 v7; // rdx
  __int64 v8; // rax
  __int64 v9; // r8
  __int64 v10; // rax
  __int64 v11; // r14
  int v12; // ecx
  int v13; // eax
  int v14; // edi
  _QWORD *v15; // rcx
  char *StartContext; // r12
  int v18; // eax
  struct _FAST_MUTEX *v19; // rcx
  __int64 v20; // rcx
  int ActivityIdIrp; // eax
  _OWORD *ActivityIdThread; // rcx
  NTSTATUS v23; // eax
  int v24; // edx
  int v25; // ecx
  int v26; // r9d
  int v27; // eax
  int v28; // r11d
  char v29; // r10
  __int64 v30; // r9
  unsigned int v31; // eax
  unsigned __int16 v32; // cx
  __int64 v33; // r8
  __int64 v34; // r8
  __int64 v35; // rax
  __int64 v36; // rax
  __int64 v37; // rdx
  PVOID v38; // rbx
  char v39; // [rsp+50h] [rbp-E8h]
  char v40; // [rsp+51h] [rbp-E7h]
  char v41; // [rsp+52h] [rbp-E6h]
  PVOID P; // [rsp+58h] [rbp-E0h] BYREF
  int v43; // [rsp+60h] [rbp-D8h]
  int v44; // [rsp+64h] [rbp-D4h]
  int v45; // [rsp+68h] [rbp-D0h]
  _QWORD *v46; // [rsp+70h] [rbp-C8h]
  __int64 v47; // [rsp+78h] [rbp-C0h]
  char *v48; // [rsp+80h] [rbp-B8h]
  void *ThreadHandle; // [rsp+88h] [rbp-B0h] BYREF
  __int64 v50; // [rsp+90h] [rbp-A8h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+98h] [rbp-A0h] BYREF
  _QWORD v52[4]; // [rsp+C8h] [rbp-70h] BYREF
  unsigned __int16 v53; // [rsp+E8h] [rbp-50h]
  __int64 v54; // [rsp+F0h] [rbp-48h]
  int v55; // [rsp+148h] [rbp+10h] BYREF
  int v56; // [rsp+150h] [rbp+18h] BYREF
  __int64 v57; // [rsp+158h] [rbp+20h]

  v4 = a2;
  v57 = a2;
  v56 = 0;
  memset(v52, 0, sizeof(v52));
  v55 = 0;
  v6 = 0;
  P = 0;
  memset(&ObjectAttributes, 0, 44);
  ThreadHandle = 0;
  v7 = *(_QWORD *)(a2 + 184);
  v8 = *(_QWORD *)(v7 + 48);
  v9 = *(_QWORD *)(v8 + 24);
  v50 = v9;
  if ( v9 )
  {
    v10 = *(_QWORD *)(v8 + 32);
    v11 = *(_QWORD *)(v9 + 192);
    v12 = *(_DWORD *)(v11 + 4);
    if ( (v12 & 1) == 0 && (!v10 || *(_BYTE *)(v10 + 88) != 4 || (v12 & 2) == 0) )
    {
      NtfsRaiseStatusInternal(a1, -1073741202, 0, 0, 0);
      __debugbreak();
    }
    v47 = *(_QWORD *)(v9 + 192);
    if ( v10 )
      v13 = *(unsigned __int8 *)(v10 + 88);
    else
      v13 = 5;
  }
  else
  {
    v11 = 0;
    v47 = 0;
    v13 = 1;
  }
  v14 = 0;
  v15 = 0;
  v46 = 0;
  v44 = 0;
  StartContext = 0;
  v48 = 0;
  v40 = 0;
  v39 = 0;
  v41 = 0;
  if ( v13 != 4 )
  {
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(a1, 3221225485LL, 721265);
    LOBYTE(a4) = v57 != 0;
    NtfsExtendedCompleteRequestInternal(a1, v57, 3221225485LL, a4, 0);
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(0, 3221225485LL, 721266);
    return 3221225485LL;
  }
  v18 = *(_DWORD *)(v7 + 24);
  v45 = v18;
  v44 = v18;
  if ( v18 != 508004 )
  {
    if ( v18 != 5488640 )
      goto LABEL_59;
    if ( (*(_DWORD *)(a1 + 12) & 1) == 0 )
    {
      *(_DWORD *)(a1 + 4) |= 0x4000000u;
      NtfsRaiseStatusInternal(a1, -1073741608, 0, 0, 721304);
    }
    ExAcquireFastMutexUnsafe((PFAST_MUTEX)(v11 + 6520));
    while ( 1 )
    {
      v19 = (struct _FAST_MUTEX *)(v11 + 6520);
      if ( !*(_BYTE *)(v11 + 6576) )
        break;
      ExReleaseFastMutexUnsafe(v19);
      KeWaitForSingleObject((PVOID)(v11 + 6584), Executive, 0, 0, 0);
      ExAcquireFastMutexUnsafe((PFAST_MUTEX)(v11 + 6520));
    }
    *(_BYTE *)(v11 + 6576) = 1;
    ExReleaseFastMutexUnsafe(v19);
    v41 = 1;
    StartContext = (char *)ExAllocatePoolWithTag((POOL_TYPE)528, 0x38u, 0x3066744Eu);
    v48 = StartContext;
    *(_OWORD *)StartContext = 0;
    *((_OWORD *)StartContext + 1) = 0;
    *((_OWORD *)StartContext + 2) = 0;
    *((_QWORD *)StartContext + 6) = 0;
    *(_QWORD *)StartContext = v11;
    KeInitializeEvent((PRKEVENT)(StartContext + 32), NotificationEvent, 0);
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 512;
    ObjectAttributes.ObjectName = 0;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    if ( v4 )
    {
      ActivityIdIrp = IoGetActivityIdIrp(v57, StartContext + 16);
      ActivityIdThread = 0;
      if ( ActivityIdIrp >= 0 )
        ActivityIdThread = StartContext + 16;
      *((_QWORD *)StartContext + 1) = ActivityIdThread;
      v4 = v57;
    }
    else
    {
      ActivityIdThread = (_OWORD *)IoGetActivityIdThread(v20);
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
      McTemplateK0pq_EtwWriteTransfer(ActivityIdThread, WORKITEM_QUEUE, *((_QWORD *)StartContext + 1));
    v23 = PsCreateSystemThread(&ThreadHandle, 0x1FFFFFu, &ObjectAttributes, 0, 0, TxfThawRmsWorker, StartContext);
    v14 = v23;
    v43 = v23;
    if ( v23 < 0 )
    {
      if ( (Microsoft_Windows_NtfsEnableBits & 0x10000000) != 0 )
        McTemplateK0pqd_EtwWriteTransfer(v25, v24, *((_QWORD *)StartContext + 1), v26, 12, v23);
    }
    else
    {
      NtfsPurgeFileRecordCache(a1);
      *(_DWORD *)(a1 + 4) |= 0x200u;
      ZwClose(ThreadHandle);
      *(_DWORD *)(a1 + 4) &= ~0x200u;
      v40 = 1;
      TxfSeekFirstRM(v11, &P);
      while ( 1 )
      {
        v6 = (volatile signed __int32 *)P;
        if ( !P )
          break;
        ExAcquireResourceExclusiveLite((PERESOURCE)(*((_QWORD *)P + 3) + 912LL), 1u);
        _InterlockedIncrement(v6 + 16);
        _InterlockedIncrement(v6 + 11);
        v39 = 1;
        v27 = TxfFreezeRmForSnapshot(a1);
        v14 = v27;
        v43 = v27;
        if ( v27 == -1072103419 )
        {
          v14 = 0;
          v43 = 0;
        }
        else if ( v27 )
        {
          break;
        }
        TxfSeekNextRm(&P);
      }
      if ( v14 >= 0 )
      {
        v14 = NtfsCheckpointForVolumeSnapshot(a1, &v55);
        v43 = v14;
      }
    }
    KeInitializeEvent((PRKEVENT)&v52[1], NotificationEvent, 0);
    v52[0] = a1;
    v15 = v52;
    v46 = v52;
    *(_DWORD *)(a1 + 12) |= 1u;
    goto LABEL_58;
  }
  v28 = *(_DWORD *)(v11 + 4);
  if ( (v28 & 2) == 0 )
  {
    v29 = *(_BYTE *)(v7 + 2);
    if ( (v29 & 0x10) == 0 )
    {
      if ( (!a1 || (*(_DWORD *)(a1 + 16) & 0x100000) == 0)
        && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x20) != 0 )
      {
        v30 = *(_QWORD *)(v11 + 248);
        v31 = *(unsigned __int16 *)(v30 + 6);
        if ( v31 > 0x40 || (v31 & 1) != 0 )
        {
          v32 = 0;
          LODWORD(v57) = 0;
        }
        else
        {
          v32 = *(_WORD *)(v30 + 6);
          LODWORD(v57) = v32;
        }
        v53 = v32;
        v54 = v30 + 32;
        McTemplateU0ppwwdd_EtwWriteTransfer(
          v32 >> 1,
          (unsigned int)devctrl_c557,
          (unsigned int)KeGetCurrentThread(),
          v11,
          *(_WORD *)(v11 + 7872) >> 1,
          *(_QWORD *)(v11 + 7880),
          v32 >> 1,
          v30 + 32,
          v28,
          v29);
      }
      v14 = -1073741790;
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(0, 3221225506LL, 721465);
      v43 = -1073741790;
      v15 = v46;
LABEL_58:
      v9 = v50;
    }
  }
LABEL_59:
  if ( v14 >= 0 )
  {
    v35 = *(_QWORD *)(v4 + 184);
    *(_OWORD *)(v35 - 72) = *(_OWORD *)v35;
    *(_OWORD *)(v35 - 56) = *(_OWORD *)(v35 + 16);
    *(_OWORD *)(v35 - 40) = *(_OWORD *)(v35 + 32);
    *(_QWORD *)(v35 - 24) = *(_QWORD *)(v35 + 48);
    *(_BYTE *)(v35 - 69) = 0;
    v36 = *(_QWORD *)(v4 + 184);
    *(_QWORD *)(v36 - 16) = DeviceControlCompletionRoutine;
    *(_QWORD *)(v36 - 8) = v15;
    *(_BYTE *)(v36 - 69) = 0;
    *(_BYTE *)(v36 - 69) = 64;
    *(_BYTE *)(v36 - 69) = -64;
    *(_BYTE *)(v36 - 69) = -32;
    v14 = NtfsCallStorageDriver(a1, *(_QWORD *)(v11 + 224), v4, v11, v9, 0, &v56);
    v43 = v14;
    if ( v14 >= 0 )
    {
      *(_QWORD *)(a1 + 112) = 0;
      v14 = v56;
      v43 = v56;
      if ( v56 == 259 && v46 )
        KeWaitForSingleObject(v46 + 1, Executive, 0, 0, 0);
      goto LABEL_82;
    }
    if ( NtfsStatusDebugFlags
      && (unsigned int)v14 < 0xFFFFFFED
      && v14 != -1073741802
      && v14 != -1073741807
      && (unsigned int)(v14 + 2147483643) > 1
      && v14 != -1073741608 )
    {
      v33 = 721531;
      goto LABEL_67;
    }
  }
  else if ( NtfsStatusDebugFlags
         && (unsigned int)v14 < 0xFFFFFFED
         && v14 != -1073741802
         && v14 != -1073741807
         && (unsigned int)(v14 + 2147483643) > 1
         && v14 != -1073741608 )
  {
    v33 = 721484;
LABEL_67:
    NtfsStatusTraceAndDebugInternal(0, (unsigned int)v14, v33);
  }
  LOBYTE(a4) = v4 != 0;
  NtfsExtendedCompleteRequestInternal(0, v4, (unsigned int)v14, a4, 0);
  if ( a1 && *(_QWORD *)(a1 + 112) == v4 )
    *(_QWORD *)(a1 + 112) = 0;
LABEL_82:
  if ( v55 )
  {
    v37 = *(_QWORD *)(a1 + 104);
    if ( (*(_DWORD *)(v37 + 4) & 0x2000000) == 0 )
    {
      NtfsReleaseAllFiles(a1, v37, 54);
      NtfsReleaseVcb(a1, v11);
    }
  }
  if ( v45 == 5488640 )
  {
    if ( v6 )
    {
      _InterlockedDecrement(v6 + 13);
      if ( _InterlockedExchangeAdd(v6 + 16, 0xFFFFFFFF) == 1 )
        TxfDeleteTxfRmcb((char *)v6);
      P = 0;
    }
    if ( v39 )
    {
      TxfSeekFirstRM(v11, &P);
      while ( 1 )
      {
        v38 = P;
        if ( !P )
          break;
        if ( ExIsResourceAcquiredSharedLite((PERESOURCE)(*((_QWORD *)P + 3) + 912LL)) )
        {
          ExReleaseResourceLite((PERESOURCE)(*((_QWORD *)v38 + 3) + 912LL));
          _InterlockedDecrement((volatile signed __int32 *)v38 + 11);
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)v38 + 16, 0xFFFFFFFF) == 1 )
            TxfDeleteTxfRmcb((char *)v38);
        }
        TxfSeekNextRm(&P);
      }
    }
    if ( v40 )
    {
      KeSetEvent((PRKEVENT)(StartContext + 32), 0, 0);
    }
    else if ( v41 )
    {
      ExAcquireFastMutexUnsafe((PFAST_MUTEX)(v11 + 6520));
      *(_BYTE *)(v11 + 6576) = 0;
      KeSetEvent((PRKEVENT)(v11 + 6584), 0, 0);
      ExReleaseFastMutexUnsafe((PFAST_MUTEX)(v11 + 6520));
    }
    if ( StartContext && !v40 )
      ExFreePoolWithTag(StartContext, 0);
  }
  NtfsCleanupIrpContext(a1, 1u, v34);
  return (unsigned int)v14;
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
