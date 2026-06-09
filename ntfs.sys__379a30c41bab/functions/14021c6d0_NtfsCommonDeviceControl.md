# NtfsCommonDeviceControl

- ea: `0x14021c6d0`
- end: `0x14021cf94`
- name: `NtfsCommonDeviceControl`
- size: `2244`
- prototype: `__int64 __fastcall(int)`
- caller_count: `3`
- callee_count: `17`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140015d10`
- `0x14017b3a0`
- `0x14021c3c0`

## callees

- `0x1400054e8`
- `0x140007670`
- `0x140007ea0`
- `0x1400082b0`
- `0x140008740`
- `0x14000c290`
- `0x140010be0`
- `0x140020de0`
- `0x140044688`
- `0x140045278`
- `0x140196e80`
- `0x1401cf610`
- `0x1401d2910`
- `0x1401d2d3c`
- `0x1401dbecc`
- `0x14021c6d0`
- `0x14023035c`

## import_xrefs

- `ntoskrnl!IoGetActivityIdIrp` at `0x14021c9b7`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14021c9b7`
- `ntoskrnl!KeSetEvent` at `0x14021cf0b`
- `ntoskrnl!KeSetEvent` at `0x14021cf4a`
- `ntoskrnl!KeSetEvent` at `0x1402b5400`
- `ntoskrnl!KeSetEvent` at `0x1402b543a`
- `ntoskrnl!KeSetEvent` at `0x14021cf0b`
- `ntoskrnl!KeSetEvent` at `0x14021cf4a`
- `ntoskrnl!KeSetEvent` at `0x1402b5400`
- `ntoskrnl!KeSetEvent` at `0x1402b543a`
- `ntoskrnl!ZwClose` at `0x14021ca85`
- `ntoskrnl!ZwClose` at `0x14021ca85`
- `ntoskrnl!PsCreateSystemThread` at `0x14021ca56`
- `ntoskrnl!PsCreateSystemThread` at `0x14021ca56`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x14021cea3`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x1402b5396`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x14021cea3`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x1402b5396`
- `ntoskrnl!IoGetActivityIdThread` at `0x14021c9da`
- `ntoskrnl!IoGetActivityIdThread` at `0x14021c9da`
- `ntoskrnl!KeWaitForSingleObject` at `0x14021c8dc`
- `ntoskrnl!KeWaitForSingleObject` at `0x14021ce0e`
- `ntoskrnl!KeWaitForSingleObject` at `0x14021c8dc`
- `ntoskrnl!KeWaitForSingleObject` at `0x14021ce0e`
- `ntoskrnl!KeInitializeEvent` at `0x14021c962`
- `ntoskrnl!KeInitializeEvent` at `0x14021cb53`
- `ntoskrnl!KeInitializeEvent` at `0x14021c962`
- `ntoskrnl!KeInitializeEvent` at `0x14021cb53`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14021c8b8`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14021c901`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14021cf59`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1402b544d`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14021c8b8`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14021c901`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14021cf59`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1402b544d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14021cf74`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b546c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14021cf74`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b546c`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14021c922`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14021c922`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14021c89f`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14021c8eb`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14021cf2a`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1402b541b`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14021c89f`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14021c8eb`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14021cf2a`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1402b541b`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14021cabf`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14021cabf`
- `ntoskrnl!ExReleaseResourceLite` at `0x14021cebe`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402b53b1`
- `ntoskrnl!ExReleaseResourceLite` at `0x14021cebe`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402b53b1`

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
0x14021c6d0  mov     rax, rsp
0x14021c6d3  mov     [rax+8], rcx
0x14021c6d7  push    rbx
0x14021c6d8  push    rsi
0x14021c6d9  push    rdi
0x14021c6da  push    r12
0x14021c6dc  push    r14
0x14021c6de  push    r15
0x14021c6e0  sub     rsp, 108h
0x14021c6e7  mov     rbx, rdx
0x14021c6ea  mov     [rax+20h], rdx
0x14021c6ee  mov     rsi, rcx
0x14021c6f1  mov     dword ptr [rax+18h], 0
0x14021c6f8  xorps   xmm0, xmm0
0x14021c6fb  movups  xmmword ptr [rax-70h], xmm0
0x14021c6ff  movups  xmmword ptr [rax-60h], xmm0
0x14021c703  mov     dword ptr [rax+10h], 0
0x14021c70a  xor     r15d, r15d
0x14021c70d  mov     [rsp+138h+P], r15
0x14021c712  xor     eax, eax
0x14021c714  movups  xmmword ptr [rsp+138h+ObjectAttributes.Length], xmm0
0x14021c71c  movups  xmmword ptr [rsp+138h+ObjectAttributes.ObjectName], xmm0
0x14021c724  movups  xmmword ptr [rsp+138h+ObjectAttributes+1Ch], xmm0
0x14021c72c  mov     [rsp+138h+ThreadHandle], rax
0x14021c734  mov     rdx, [rdx+0B8h]
0x14021c73b  mov     rax, [rdx+30h]
0x14021c73f  mov     r8, [rax+18h]
0x14021c743  mov     [rsp+138h+var_A8], r8
0x14021c74b  test    r8, r8
0x14021c74e  jz      short loc_14021C7A4
0x14021c750  mov     rax, [rax+20h]
0x14021c754  mov     r14, [r8+0C0h]
0x14021c75b  mov     ecx, [r14+4]
0x14021c75f  test    cl, 1
0x14021c762  jnz     short loc_14021C78D
0x14021c764  test    rax, rax
0x14021c767  jz      short loc_14021C774
0x14021c769  cmp     byte ptr [rax+58h], 4
0x14021c76d  jnz     short loc_14021C774
0x14021c76f  test    cl, 2
0x14021c772  jnz     short loc_14021C78D
0x14021c774  mov     [rsp+138h+Timeout], r15
0x14021c779  xor     r9d, r9d
0x14021c77c  xor     r8d, r8d
0x14021c77f  mov     edx, 0C000026Eh
0x14021c784  mov     rcx, rsi
0x14021c787  call    NtfsRaiseStatusInternal
0x14021c78c  int     3; Trap to Debugger
0x14021c78d  mov     [rsp+138h+var_C0], r14
0x14021c792  test    rax, rax
0x14021c795  jnz     short loc_14021C79E
0x14021c797  mov     eax, 5
0x14021c79c  jmp     short loc_14021C7B0
0x14021c79e  movzx   eax, byte ptr [rax+58h]
0x14021c7a2  jmp     short loc_14021C7B0
0x14021c7a4  xor     r14d, r14d
0x14021c7a7  mov     [rsp+138h+var_C0], r14
0x14021c7ac  lea     eax, [r14+1]
0x14021c7b0  xor     edi, edi
0x14021c7b2  xor     ecx, ecx
0x14021c7b4  mov     [rsp+138h+var_C8], rcx
0x14021c7b9  mov     [rsp+138h+var_D4], ecx
0x14021c7bd  xor     r12d, r12d
0x14021c7c0  mov     [rsp+138h+var_B8], r12
0x14021c7c8  mov     [rsp+138h+var_E7], cl
0x14021c7cc  mov     [rsp+138h+var_E8], cl
0x14021c7d0  mov     [rsp+138h+var_E6], cl
0x14021c7d4  cmp     eax, 4
0x14021c7d7  jz      short loc_14021C846
0x14021c7d9  mov     al, cs:NtfsStatusDebugFlags
0x14021c7df  mov     ebx, 0C000000Dh
0x14021c7e4  test    al, al
0x14021c7e6  jz      short loc_14021C7F8
0x14021c7e8  mov     r8d, 0B0171h
0x14021c7ee  mov     edx, ebx
0x14021c7f0  mov     rcx, rsi
0x14021c7f3  call    NtfsStatusTraceAndDebugInternal
0x14021c7f8  mov     rcx, [rsp+138h+arg_18]
0x14021c800  test    rcx, rcx
0x14021c803  setnz   r9b
0x14021c807  mov     dword ptr [rsp+138h+Timeout], edi
0x14021c80b  mov     r8d, ebx
0x14021c80e  mov     rdx, rcx
0x14021c811  mov     rcx, rsi
0x14021c814  call    NtfsExtendedCompleteRequestInternal
0x14021c819  mov     al, cs:NtfsStatusDebugFlags
0x14021c81f  test    al, al
0x14021c821  jz      short loc_14021C832
0x14021c823  mov     r8d, 0B0172h
0x14021c829  mov     edx, ebx
0x14021c82b  xor     ecx, ecx
0x14021c82d  call    NtfsStatusTraceAndDebugInternal
0x14021c832  mov     eax, ebx
0x14021c834  add     rsp, 108h
0x14021c83b  pop     r15
0x14021c83d  pop     r14
0x14021c83f  pop     r12
0x14021c841  pop     rdi
0x14021c842  pop     rsi
0x14021c843  pop     rbx
0x14021c844  retn
0x14021c846  mov     eax, [rdx+18h]
0x14021c849  mov     [rsp+138h+var_D0], eax
0x14021c84d  mov     [rsp+138h+var_D4], eax
0x14021c851  cmp     eax, 7C064h
0x14021c856  jz      loc_14021CB7D
0x14021c85c  cmp     eax, 53C000h
0x14021c861  jnz     loc_14021CC72
0x14021c867  mov     eax, [rsi+0Ch]
0x14021c86a  test    al, 1
0x14021c86c  jnz     short loc_14021C895
0x14021c86e  bts     dword ptr [rsi+4], 1Ah
0x14021c873  mov     al, cs:NtfsStatusDebugFlags
0x14021c879  mov     [rsp+138h+Timeout], 0B0198h
0x14021c882  xor     r9d, r9d
0x14021c885  xor     r8d, r8d
0x14021c888  mov     edx, 0C00000D8h
0x14021c88d  mov     rcx, rsi
0x14021c890  call    NtfsRaiseStatusInternal
0x14021c895  lea     rdi, [r14+1978h]
0x14021c89c  mov     rcx, rdi; FastMutex
0x14021c89f  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14021c8a6  nop     dword ptr [rax+rax+00h]
0x14021c8ab  mov     rcx, rdi; FastMutex
0x14021c8ae  cmp     byte ptr [r14+19B0h], 0
0x14021c8b6  jz      short loc_14021C8F9
0x14021c8b8  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14021c8bf  nop     dword ptr [rax+rax+00h]
0x14021c8c4  lea     rcx, [r14+19B8h]; Object
0x14021c8cb  mov     [rsp+138h+Timeout], 0; Timeout
0x14021c8d4  xor     r9d, r9d; Alertable
0x14021c8d7  xor     r8d, r8d; WaitMode
0x14021c8da  xor     edx, edx; WaitReason
0x14021c8dc  call    cs:__imp_KeWaitForSingleObject
0x14021c8e3  nop     dword ptr [rax+rax+00h]
0x14021c8e8  mov     rcx, rdi; FastMutex
0x14021c8eb  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14021c8f2  nop     dword ptr [rax+rax+00h]
0x14021c8f7  jmp     short loc_14021C8AB
0x14021c8f9  mov     byte ptr [r14+19B0h], 1
0x14021c901  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14021c908  nop     dword ptr [rax+rax+00h]
0x14021c90d  mov     [rsp+138h+var_E6], 1
0x14021c912  mov     edx, 38h ; '8'; NumberOfBytes
0x14021c917  mov     ecx, 210h; PoolType
0x14021c91c  mov     r8d, 3066744Eh; Tag
0x14021c922  call    cs:__imp_ExAllocatePoolWithTag
0x14021c929  nop     dword ptr [rax+rax+00h]
0x14021c92e  mov     r12, rax
0x14021c931  mov     [rsp+138h+var_B8], rax
0x14021c939  xorps   xmm0, xmm0
0x14021c93c  xor     eax, eax
0x14021c93e  movups  xmmword ptr [r12], xmm0
0x14021c943  movups  xmmword ptr [r12+10h], xmm0
0x14021c949  movups  xmmword ptr [r12+20h], xmm0
0x14021c94f  mov     [r12+30h], rax
0x14021c954  mov     [r12], r14
0x14021c958  lea     rcx, [r12+20h]; Event
0x14021c95d  xor     r8d, r8d; State
0x14021c960  xor     edx, edx; Type
0x14021c962  call    cs:__imp_KeInitializeEvent
0x14021c969  nop     dword ptr [rax+rax+00h]
0x14021c96e  mov     [rsp+138h+ObjectAttributes.Length], 30h ; '0'
0x14021c979  xor     edi, edi
0x14021c97b  mov     [rsp+138h+ObjectAttributes.RootDirectory], rdi
0x14021c983  mov     [rsp+138h+ObjectAttributes.Attributes], 200h
0x14021c98e  mov     [rsp+138h+ObjectAttributes.ObjectName], rdi
0x14021c996  xorps   xmm0, xmm0
0x14021c999  movdqu  xmmword ptr [rsp+138h+ObjectAttributes.SecurityDescriptor], xmm0
0x14021c9a2  test    rbx, rbx
0x14021c9a5  jz      short loc_14021C9DA
0x14021c9a7  lea     rbx, [r12+10h]
0x14021c9ac  mov     rdx, rbx
0x14021c9af  mov     rcx, [rsp+138h+arg_18]
0x14021c9b7  call    cs:__imp_IoGetActivityIdIrp
0x14021c9be  nop     dword ptr [rax+rax+00h]
0x14021c9c3  mov     ecx, edi
0x14021c9c5  test    eax, eax
0x14021c9c7  cmovns  rcx, rbx
0x14021c9cb  mov     [r12+8], rcx
0x14021c9d0  mov     rbx, [rsp+138h+arg_18]
0x14021c9d8  jmp     short loc_14021CA06
0x14021c9da  call    cs:__imp_IoGetActivityIdThread
0x14021c9e1  nop     dword ptr [rax+rax+00h]
0x14021c9e6  mov     rcx, rax
0x14021c9e9  test    rax, rax
0x14021c9ec  jz      short loc_14021CA01
0x14021c9ee  lea     rax, [r12+10h]
0x14021c9f3  movups  xmm0, xmmword ptr [rcx]
0x14021c9f6  movdqu  xmmword ptr [rax], xmm0
0x14021c9fa  mov     [r12+8], rax
0x14021c9ff  jmp     short loc_14021CA06
0x14021ca01  mov     [r12+8], rdi
0x14021ca06  test    byte ptr cs:Microsoft_Windows_NtfsEnableBits+3, 8
0x14021ca0d  jz      short loc_14021CA28
0x14021ca0f  mov     r8, [r12+8]
0x14021ca14  mov     dword ptr [rsp+138h+Timeout], 0Ch
0x14021ca1c  lea     rdx, WORKITEM_QUEUE
0x14021ca23  call    McTemplateK0pq_EtwWriteTransfer
0x14021ca28  mov     [rsp+138h+StartContext], r12; StartContext
0x14021ca2d  lea     rax, TxfThawRmsWorker
0x14021ca34  mov     [rsp+138h+StartRoutine], rax; StartRoutine
0x14021ca39  mov     [rsp+138h+Timeout], rdi; ClientId
0x14021ca3e  xor     r9d, r9d; ProcessHandle
0x14021ca41  lea     r8, [rsp+138h+ObjectAttributes]; ObjectAttributes
0x14021ca49  mov     edx, 1FFFFFh; DesiredAccess
0x14021ca4e  lea     rcx, [rsp+138h+ThreadHandle]; ThreadHandle
0x14021ca56  call    cs:__imp_PsCreateSystemThread
0x14021ca5d  nop     dword ptr [rax+rax+00h]
0x14021ca62  mov     edi, eax
0x14021ca64  mov     [rsp+138h+var_D8], eax
0x14021ca68  test    eax, eax
0x14021ca6a  js      loc_14021CB27
0x14021ca70  mov     rcx, rsi
0x14021ca73  call    NtfsPurgeFileRecordCache
0x14021ca78  bts     dword ptr [rsi+4], 9
0x14021ca7d  mov     rcx, [rsp+138h+ThreadHandle]; Handle
0x14021ca85  call    cs:__imp_ZwClose
0x14021ca8c  nop     dword ptr [rax+rax+00h]
0x14021ca91  btr     dword ptr [rsi+4], 9
0x14021ca96  mov     [rsp+138h+var_E7], 1
0x14021ca9b  lea     rdx, [rsp+138h+P]
0x14021caa0  mov     rcx, r14
0x14021caa3  call    TxfSeekFirstRM
0x14021caa8  mov     r15, [rsp+138h+P]
0x14021caad  test    r15, r15
0x14021cab0  jz      short loc_14021CB0B
0x14021cab2  mov     rcx, [r15+18h]
0x14021cab6  add     rcx, 390h; Resource
0x14021cabd  mov     dl, 1; Wait
0x14021cabf  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14021cac6  nop     dword ptr [rax+rax+00h]
0x14021cacb  lock inc dword ptr [r15+40h]
0x14021cad0  lock inc dword ptr [r15+2Ch]
0x14021cad5  mov     [rsp+138h+var_E8], 1
0x14021cada  xor     r8d, r8d
0x14021cadd  mov     rdx, r15
0x14021cae0  mov     rcx, rsi; int
0x14021cae3  call    TxfFreezeRmForSnapshot
0x14021cae8  mov     edi, eax
0x14021caea  mov     [rsp+138h+var_D8], eax
0x14021caee  cmp     eax, 0C0190005h
0x14021caf3  jnz     short loc_14021CB07
0x14021caf5  xor     edi, edi
0x14021caf7  mov     [rsp+138h+var_D8], edi
0x14021cafb  lea     rcx, [rsp+138h+P]
0x14021cb00  call    TxfSeekNextRm
0x14021cb05  jmp     short loc_14021CAA8
0x14021cb07  test    eax, eax
0x14021cb09  jz      short loc_14021CAFB
0x14021cb0b  test    edi, edi
0x14021cb0d  js      short loc_14021CB46
0x14021cb0f  lea     rdx, [rsp+138h+arg_8]
0x14021cb17  mov     rcx, rsi; int
0x14021cb1a  call    NtfsCheckpointForVolumeSnapshot
0x14021cb1f  mov     edi, eax
0x14021cb21  mov     [rsp+138h+var_D8], eax
0x14021cb25  jmp     short loc_14021CB46
0x14021cb27  test    byte ptr cs:Microsoft_Windows_NtfsEnableBits+3, 10h
0x14021cb2e  jz      short loc_14021CB46
0x14021cb30  mov     r8, [r12+8]
0x14021cb35  mov     dword ptr [rsp+138h+StartRoutine], eax
0x14021cb39  mov     dword ptr [rsp+138h+Timeout], 0Ch
0x14021cb41  call    McTemplateK0pqd_EtwWriteTransfer
0x14021cb46  xor     r8d, r8d; State
0x14021cb49  xor     edx, edx; Type
0x14021cb4b  lea     rcx, [rsp+138h+Event]; Event
0x14021cb53  call    cs:__imp_KeInitializeEvent
0x14021cb5a  nop     dword ptr [rax+rax+00h]
0x14021cb5f  mov     [rsp+138h+var_70], rsi
0x14021cb67  lea     rcx, [rsp+138h+var_70]
0x14021cb6f  mov     [rsp+138h+var_C8], rcx
0x14021cb74  or      dword ptr [rsi+0Ch], 1
0x14021cb78  jmp     loc_14021CC6A
0x14021cb7d  mov     r11d, [r14+4]
0x14021cb81  test    r11b, 2
0x14021cb85  jnz     loc_14021CC72
0x14021cb8b  movzx   r10d, byte ptr [rdx+2]
0x14021cb90  test    r10b, 10h
0x14021cb94  jnz     loc_14021CC72
0x14021cb9a  test    rsi, rsi
0x14021cb9d  jz      short loc_14021CBAD
0x14021cb9f  mov     eax, [rsi+10h]
0x14021cba2  bt      rax, 14h
0x14021cba7  jb      loc_14021CC43
0x14021cbad  mov     rax, cs:Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits
0x14021cbb4  test    al, 20h
0x14021cbb6  jz      loc_14021CC43
0x14021cbbc  mov     r9, [r14+0F8h]
0x14021cbc3  movzx   eax, word ptr [r9+6]
0x14021cbc8  cmp     eax, 40h ; '@'
0x14021cbcb  ja      short loc_14021CBDC
0x14021cbcd  test    al, 1
0x14021cbcf  jnz     short loc_14021CBDC
0x14021cbd1  mov     ecx, eax
0x14021cbd3  mov     dword ptr [rsp+138h+arg_18], eax
0x14021cbda  jmp     short loc_14021CBE5
0x14021cbdc  xor     ecx, ecx
0x14021cbde  mov     dword ptr [rsp+138h+arg_18], ecx
0x14021cbe5  mov     [rsp+138h+var_50], cx
  ... truncated ...
```
