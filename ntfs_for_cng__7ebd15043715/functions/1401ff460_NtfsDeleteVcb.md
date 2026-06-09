# NtfsDeleteVcb

- ea: `0x1401ff460`
- end: `0x1401ffe55`
- name: `NtfsDeleteVcb`
- size: `2549`
- prototype: `char __fastcall(__int64, __int64 *)`
- caller_count: `1`
- callee_count: `22`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140020820`

## callees

- `0x14000d1e0`
- `0x14000ea70`
- `0x14001e810`
- `0x140036cb0`
- `0x1400372e0`
- `0x14003b8bc`
- `0x140041858`
- `0x1400c42e4`
- `0x140129500`
- `0x14012b220`
- `0x14012bb80`
- `0x1401ff460`
- `0x1401ffe5c`
- `0x1401ffec8`
- `0x140200048`
- `0x140200130`
- `0x1402001f4`
- `0x1402002a0`
- `0x1402002f4`
- `0x1402003c0`
- `0x140200460`
- `0x140200558`

## import_xrefs

- `ntoskrnl!FsRtlHeatUninit` at `0x1401ffcba`
- `ntoskrnl!FsRtlHeatUninit` at `0x1401ffcba`
- `ntoskrnl!ObfDereferenceObject` at `0x1401ff84e`
- `ntoskrnl!ObfDereferenceObject` at `0x1401ffa6b`
- `ntoskrnl!ObfDereferenceObject` at `0x1401ff84e`
- `ntoskrnl!ObfDereferenceObject` at `0x1401ffa6b`
- `ntoskrnl!CcUninitializeCacheMap` at `0x1401ff82e`
- `ntoskrnl!CcUninitializeCacheMap` at `0x1401ff82e`
- `ntoskrnl!MmFreeMappingAddress` at `0x1401ffa12`
- `ntoskrnl!MmFreeMappingAddress` at `0x1401ffa2f`
- `ntoskrnl!MmFreeMappingAddress` at `0x1401ffdb3`
- `ntoskrnl!MmFreeMappingAddress` at `0x1401ffa12`
- `ntoskrnl!MmFreeMappingAddress` at `0x1401ffa2f`
- `ntoskrnl!MmFreeMappingAddress` at `0x1401ffdb3`
- `ntoskrnl!FsRtlDeleteTunnelCache` at `0x1401ff9b6`
- `ntoskrnl!FsRtlDeleteTunnelCache` at `0x1401ff9b6`
- `ntoskrnl!ExDeleteResourceLite` at `0x1401ff8b3`
- `ntoskrnl!ExDeleteResourceLite` at `0x1401ff8c9`
- `ntoskrnl!ExDeleteResourceLite` at `0x1401ff8df`
- `ntoskrnl!ExDeleteResourceLite` at `0x1401ff8f5`
- `ntoskrnl!ExDeleteResourceLite` at `0x1401ff90b`
- `ntoskrnl!ExDeleteResourceLite` at `0x1401ff921`
- `ntoskrnl!ExDeleteResourceLite` at `0x1401ff937`
- `ntoskrnl!ExDeleteResourceLite` at `0x1401ff94d`
- `ntoskrnl!ExDeleteResourceLite` at `0x1401ff963`
- `ntoskrnl!ExDeleteResourceLite` at `0x1401ff979`
- `ntoskrnl!ExDeleteResourceLite` at `0x1401ff8b3`
- `ntoskrnl!ExDeleteResourceLite` at `0x1401ff8c9`
- `ntoskrnl!ExDeleteResourceLite` at `0x1401ff8df`
- `ntoskrnl!ExDeleteResourceLite` at `0x1401ff8f5`
- `ntoskrnl!ExDeleteResourceLite` at `0x1401ff90b`
- `ntoskrnl!ExDeleteResourceLite` at `0x1401ff921`
- `ntoskrnl!ExDeleteResourceLite` at `0x1401ff937`
- `ntoskrnl!ExDeleteResourceLite` at `0x1401ff94d`
- `ntoskrnl!ExDeleteResourceLite` at `0x1401ff963`
- `ntoskrnl!ExDeleteResourceLite` at `0x1401ff979`
- `ntoskrnl!KeFreeCalloutStack` at `0x1401ffde0`
- `ntoskrnl!KeFreeCalloutStack` at `0x1401ffde0`
- `ntoskrnl!FsRtlNotifyUninitializeSync` at `0x1401ff707`
- `ntoskrnl!FsRtlNotifyUninitializeSync` at `0x1401ff707`
- `ntoskrnl!IoDeleteDevice` at `0x1401ffb3e`
- `ntoskrnl!IoDeleteDevice` at `0x1401ffb3e`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1401ff60c`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1401ff60c`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1401ff50e`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1401ff52d`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1401ff54c`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1401ff56b`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1401ff58a`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1401ff5a9`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1401ff50e`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1401ff52d`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1401ff54c`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1401ff56b`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1401ff58a`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1401ff5a9`
- `ntoskrnl!ExReleasePushLockEx` at `0x1401ff64c`
- `ntoskrnl!ExReleasePushLockEx` at `0x1401ff64c`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1401ff7ce`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1401ff7ce`
- `ntoskrnl!FsRtlUninitializeBaseMcb` at `0x1401ff795`
- `ntoskrnl!FsRtlUninitializeBaseMcb` at `0x1401ff7f4`
- `ntoskrnl!FsRtlUninitializeBaseMcb` at `0x1401ffa81`
- `ntoskrnl!FsRtlUninitializeBaseMcb` at `0x1401ffd1b`
- `ntoskrnl!FsRtlUninitializeBaseMcb` at `0x1401ff795`
- `ntoskrnl!FsRtlUninitializeBaseMcb` at `0x1401ff7f4`
- `ntoskrnl!FsRtlUninitializeBaseMcb` at `0x1401ffa81`
- `ntoskrnl!FsRtlUninitializeBaseMcb` at `0x1401ffd1b`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1401ff69b`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1401ffba6`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1401ff69b`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1401ffba6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401ff765`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401ff996`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401ff9d3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401ff9f0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401ffa9e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401ffb73`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401ffc38`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401ffc4b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401ffceb`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401ffd79`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401ffd96`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401ffdc6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401ffe1e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401ffe31`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401ffe44`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401ff765`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401ff996`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401ff9d3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401ff9f0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401ffa9e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401ffb73`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401ffc38`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401ffc4b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401ffceb`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401ffd79`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401ffd96`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401ffdc6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401ffe1e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401ffe31`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401ffe44`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1401ff675`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1401ff675`

## pseudocode

```c
char __fastcall NtfsDeleteVcb(__int64 a1, __int64 *a2)
{
  char v3; // bl
  __int64 v5; // r15
  __int64 v6; // rdx
  unsigned int *v7; // rcx
  struct _FILE_OBJECT *v8; // rcx
  __int64 v9; // rax
  struct _ERESOURCE *v10; // rcx
  __int64 v11; // rcx
  __int64 v12; // rcx
  void **v13; // rax
  char *v14; // rbx
  __int64 v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // rsi
  _QWORD *v18; // rax
  _QWORD *v19; // rcx
  __int64 v20; // rcx
  __int64 v21; // rcx
  void *v22; // rcx
  void *v23; // rcx
  char *v24; // rcx
  void *v25; // rcx
  _QWORD **v26; // rax
  _QWORD *v27; // rcx
  __int64 v28; // rax
  _QWORD *v29; // rdx
  void **v30; // rcx
  void *v31; // rcx
  void *v32; // rcx
  void *v33; // rcx
  void *v34; // rcx
  void *v35; // rcx
  void *v36; // rcx
  void *v37; // rcx
  void *v38; // rcx
  __int64 v39; // rcx
  __int64 *v40; // rcx
  void *v41; // rcx
  void *v42; // rcx
  void *v44; // rcx
  _QWORD *v45; // rbx
  _QWORD *v46; // rax
  _QWORD *v47; // r14
  _QWORD *v48; // rbx
  __int64 v49; // rdx
  __int64 v50; // rbx
  char v51; // [rsp+68h] [rbp+10h] BYREF
  _QWORD *v52; // [rsp+70h] [rbp+18h] BYREF
  __int64 v53; // [rsp+78h] [rbp+20h] BYREF

  v3 = 0;
  NtfsSynchronizeWithRepairThread(*a2);
  v5 = *a2;
  IoPerfFreeEntityData((struct _IO_PERF_ENTITY_DATA *)(*a2 + 10496));
  NtfsDeletePerVolumeTelemetry(*a2);
  if ( *(_QWORD *)(*a2 + 11784) )
    NtfsBypassIoDismountCleanup(*a2);
  v6 = 2048;
  v7 = (unsigned int *)(*a2 + 24);
  if ( (*v7 & 0x800) != 0 )
  {
    ClearFlagInterlocked(v7, 2048);
    FsRtlHeatUninit(*a2 + 8200, *a2 + 8212);
  }
  LOBYTE(v6) = 1;
  NtOfsPurgeSecurityCache(*a2, v6);
  v8 = *(struct _FILE_OBJECT **)(*a2 + 216);
  if ( v8 && (*(_DWORD *)(*a2 + 572) & 8) == 0 )
  {
    CcUninitializeCacheMap(v8, &NtfsLarge0, 0);
    *(_DWORD *)(*a2 + 572) |= 8u;
    ObfDereferenceObject(*(PVOID *)(*a2 + 216));
  }
  v9 = *a2;
  if ( *(_QWORD *)(*a2 + 216) )
    return v3;
  v10 = *(struct _ERESOURCE **)(v9 + 4920);
  if ( v10 && v10 != (struct _ERESOURCE *)(v9 + 832) )
  {
    NtfsFreeRestartTable(v10);
    ExFreePoolWithTag(*(PVOID *)(*a2 + 4920), 0);
    *(_QWORD *)(*a2 + 4920) = 0;
  }
  if ( *(_QWORD *)(*a2 + 6672) )
    RtlFreeUnicodeString((PUNICODE_STRING)(*a2 + 6664));
  if ( *(_QWORD *)(*a2 + 6688) )
    RtlFreeUnicodeString((PUNICODE_STRING)(*a2 + 6680));
  if ( *(_QWORD *)(*a2 + 6704) )
    RtlFreeUnicodeString((PUNICODE_STRING)(*a2 + 6696));
  if ( *(_QWORD *)(*a2 + 6720) )
    RtlFreeUnicodeString((PUNICODE_STRING)(*a2 + 6712));
  if ( *(_QWORD *)(*a2 + 6736) )
    RtlFreeUnicodeString((PUNICODE_STRING)(*a2 + 6728));
  if ( *(_QWORD *)(*a2 + 7880) )
    RtlFreeUnicodeString((PUNICODE_STRING)(*a2 + 7872));
  v11 = *a2;
  if ( !*(_QWORD *)(*a2 + 1624) && (*(_DWORD *)(v11 + 1680) & 2) == 0 )
  {
    FsRtlUninitializeBaseMcb((PBASE_MCB)(v11 + 1640));
    *(_DWORD *)(*a2 + 1680) |= 2u;
  }
  v12 = *a2;
  if ( !*(_QWORD *)(*a2 + 1688) && (*(_DWORD *)(v12 + 1744) & 2) == 0 )
  {
    FsRtlUninitializeBaseMcb((PBASE_MCB)(v12 + 1704));
    *(_DWORD *)(*a2 + 1744) |= 2u;
  }
  while ( 1 )
  {
    v13 = (void **)(*a2 + 1608);
    v14 = (char *)*v13;
    if ( *v13 == v13 )
      break;
    if ( *((void ***)v14 + 1) != v13 || (v30 = *(void ***)v14, *(char **)(*(_QWORD *)v14 + 8LL) != v14) )
LABEL_50:
      __fastfail(3u);
    *v13 = v30;
    v30[1] = v13;
    FsRtlUninitializeBaseMcb((PBASE_MCB)(v14 + 16));
    if ( v14 != (char *)(*a2 + 1688) && v14 != (char *)(*a2 + 1624) )
      ExFreeToLookasideListEx(&NtfsDeallocatedClustersLookasideList, v14);
  }
  v15 = *(_QWORD *)(*a2 + 240);
  if ( v15 )
  {
    ClearFlagInterlocked((unsigned int *)(v15 + 4), 4);
    NtfsFullDeleteLcb(a1, 0, (__int64 *)(*a2 + 240));
    *(_QWORD *)(*a2 + 240) = 0;
  }
  while ( 1 )
  {
    v16 = *a2 + 656;
    v51 = 0;
    ExAcquirePushLockSharedEx(v16, 0);
    v17 = 0;
    v18 = *(_QWORD **)(*a2 + 1344);
    if ( v18 )
    {
      do
      {
        v19 = v18;
        v18 = (_QWORD *)*v18;
      }
      while ( v18 );
      v17 = *(v19 - 1);
    }
    v20 = *a2 + 656;
    v53 = v17;
    ExReleasePushLockEx(v20, 0);
    if ( !v17 )
      break;
    NtfsAcquireExclusiveFcb(a1, v17, 0, 1);
    v45 = (_QWORD *)(v17 + 64);
    while ( 1 )
    {
      v46 = (_QWORD *)*v45;
      if ( (_QWORD *)*v45 == v45 )
        break;
      v52 = v46 - 21;
      if ( v46 == (_QWORD *)168 )
        goto LABEL_86;
      NtfsDeleteScb(a1, (__int64 *)&v52);
    }
    v52 = 0;
LABEL_86:
    v47 = (_QWORD *)(v17 + 48);
    while ( 1 )
    {
      v48 = (_QWORD *)*v47;
      if ( (_QWORD *)*v47 == v47 )
        break;
      v49 = *(v48 - 4);
      v50 = (__int64)(v48 - 7);
      v52 = (_QWORD *)v50;
      NtfsAcquireExclusiveFcb(a1, *(_QWORD *)(v49 + 184), 0, 1);
      NtfsFullDeleteLcb(0, *(_QWORD *)(v50 + 24), (__int64 *)&v52);
    }
    v51 = 0;
    *(_QWORD *)(v17 + 304) = &v51;
    NtfsDeleteFcb(a1, &v53, 0);
  }
  if ( (*(_DWORD *)(*a2 + 6436) & 2) == 0 )
  {
LABEL_32:
    v22 = *(void **)(*a2 + 784);
    if ( v22 && v22 != Source1 )
      ExFreePoolWithTag(v22, 0);
    *(_QWORD *)(*a2 + 784) = 0;
    v23 = *(void **)(*a2 + 800);
    if ( v23 )
    {
      ExFreePoolWithTag(v23, 0);
      *(_QWORD *)(*a2 + 800) = 0;
    }
    v24 = *(char **)(*a2 + 4704);
    if ( v24 && v24 != L"$STANDARD_INFORMATION" )
    {
      ExFreePoolWithTag(v24, 0);
      *(_QWORD *)(*a2 + 4704) = 0;
    }
    v25 = *(void **)(*a2 + 7864);
    if ( v25 )
    {
      ExFreePoolWithTag(v25, 0);
      *(_QWORD *)(*a2 + 7864) = 0;
    }
    FsRtlNotifyUninitializeSync((PNOTIFY_SYNC *)(*a2 + 1464));
    LfsDeleteLogHandle(*(PVOID *)(*a2 + 232));
    *(_QWORD *)(*a2 + 232) = 0;
    while ( 1 )
    {
      v26 = (_QWORD **)(*a2 + 4928);
      v27 = *v26;
      if ( *v26 == v26 )
        break;
      v28 = *v27;
      if ( *(_QWORD **)(*v27 + 8LL) != v27 )
        goto LABEL_50;
      v29 = (_QWORD *)v27[1];
      if ( (_QWORD *)*v29 != v27 )
        goto LABEL_50;
      *v29 = v28;
      *(_QWORD *)(v28 + 8) = v29;
      ExFreePoolWithTag(v27, 0);
    }
    NtfsFreeRestartTable((PERESOURCE)(*a2 + 832));
    NtfsFreeRestartTable((PERESOURCE)(*a2 + 1064));
    if ( (*(_DWORD *)(*a2 + 4) & 0x400) != 0 )
    {
      v44 = *(void **)(*a2 + 248);
      if ( v44 )
      {
        ExFreePoolWithTag(v44, 0);
        *(_QWORD *)(*a2 + 248) = 0;
      }
    }
    NtfsUninitializeHashTable(*a2 + 4968);
    NtfsTeardownCorruptionLru(*a2);
    NtfsTeardownTornWriteLru(*a2);
    ExDeleteResourceLite((PERESOURCE)(*a2 + 2160));
    ExDeleteResourceLite((PERESOURCE)(*a2 + 2328));
    ExDeleteResourceLite((PERESOURCE)(*a2 + 6800));
    ExDeleteResourceLite((PERESOURCE)(*a2 + 6936));
    ExDeleteResourceLite((PERESOURCE)(*a2 + 11664));
    ExDeleteResourceLite((PERESOURCE)(*a2 + 7888));
    ExDeleteResourceLite((PERESOURCE)(*a2 + 8032));
    ExDeleteResourceLite((PERESOURCE)(*a2 + 10792));
    ExDeleteResourceLite((PERESOURCE)(*a2 + 10688));
    ExDeleteResourceLite((PERESOURCE)(*a2 + 11416));
    v31 = *(void **)(*a2 + 808);
    if ( v31 )
    {
      ExFreePoolWithTag(v31, 0);
      *(_QWORD *)(*a2 + 808) = 0;
    }
    FsRtlDeleteTunnelCache((TUNNEL *)(*a2 + 4720));
    v32 = *(void **)(*a2 + 5656);
    if ( v32 )
      ExFreePoolWithTag(v32, 0);
    v33 = *(void **)(*a2 + 5664);
    if ( v33 )
      ExFreePoolWithTag(v33, 0);
    v34 = *(void **)(*a2 + 5384);
    if ( v34 )
      MmFreeMappingAddress(v34, 0x6266744Eu);
    v35 = *(void **)(*a2 + 5448);
    if ( v35 )
      MmFreeMappingAddress(v35, 0x6266744Eu);
    v36 = *(void **)(*a2 + 5680);
    if ( v36 )
      MmFreeMappingAddress(v36, 0x6266744Eu);
    v37 = *(void **)(*a2 + 5672);
    if ( v37 )
      ExFreePoolWithTag(v37, 0);
    ObfDereferenceObject(*(PVOID *)(*a2 + 224));
    FsRtlUninitializeBaseMcb((PBASE_MCB)(*a2 + 1864));
    v38 = *(void **)(*a2 + 4912);
    if ( v38 )
    {
      ExFreePoolWithTag(v38, 0);
      *(_QWORD *)(*a2 + 4912) = 0;
    }
    v39 = *(_QWORD *)(*a2 + 6608);
    if ( v39 != NtfsReserveStackTxfFlush && v39 )
      KeFreeCalloutStack(v39);
    *(_QWORD *)(*a2 + 6608) = 0;
    v40 = *(__int64 **)(*a2 + 5512);
    if ( v40 != qword_1400959D8 && v40 )
    {
      NtfsDeleteReservedBuffer((__int64)(v40 + 16));
      NtfsDeleteReservedHeader(*(char **)(*a2 + 5512));
      ExFreePoolWithTag(*(PVOID *)(*a2 + 5512), 0);
    }
    NtfsFreeMftViewCounts(*a2);
    v41 = *(void **)(*a2 + 8144);
    if ( v41 )
      ExFreePoolWithTag(v41, 0);
    NtfsCleanupTieringInfo(*a2 + 512);
    NtfsDeleteDaxVcb(a1, *a2);
    v42 = *(void **)(*a2 + 10904);
    if ( v42 )
      ExFreePoolWithTag(v42, 0);
    IoDeleteDevice((PDEVICE_OBJECT)(v5 - 384));
    *a2 = 0;
    return 1;
  }
  ExAcquireFastMutexUnsafe((PFAST_MUTEX)(*a2 + 6256));
  v21 = *a2;
  if ( *(_QWORD *)(*a2 + 5744) == *a2 + 5744 )
  {
    ExReleaseFastMutexUnsafe((PFAST_MUTEX)(v21 + 6256));
    goto LABEL_32;
  }
  SetFlagInterlocked((unsigned int *)(v21 + 4), 0x40000000u);
  ExReleaseFastMutexUnsafe((PFAST_MUTEX)(*a2 + 6256));
  return 0;
}

```

## disassembly

```asm
0x1401ff460  push    rbx
0x1401ff462  push    rbp
0x1401ff463  push    rsi
0x1401ff464  push    rdi
0x1401ff465  push    r12
0x1401ff467  push    r14
0x1401ff469  push    r15
0x1401ff46b  sub     rsp, 20h
0x1401ff46f  mov     rbp, rcx
0x1401ff472  xor     r12d, r12d
0x1401ff475  mov     rcx, [rdx]
0x1401ff478  mov     bl, r12b
0x1401ff47b  mov     rdi, rdx
0x1401ff47e  call    NtfsSynchronizeWithRepairThread
0x1401ff483  mov     r15, [rdi]
0x1401ff486  lea     rcx, [r15+2900h]; struct _IO_PERF_ENTITY_DATA *
0x1401ff48d  call    IoPerfFreeEntityData
0x1401ff492  mov     rcx, [rdi]
0x1401ff495  call    NtfsDeletePerVolumeTelemetry
0x1401ff49a  mov     rcx, [rdi]
0x1401ff49d  cmp     [rcx+2E08h], r12
0x1401ff4a4  jnz     loc_1401FFC9A
0x1401ff4aa  mov     rcx, [rdi]
0x1401ff4ad  mov     edx, 800h
0x1401ff4b2  add     rcx, 18h
0x1401ff4b6  test    [rcx], edx
0x1401ff4b8  jnz     loc_1401FFCA4
0x1401ff4be  mov     rcx, [rdi]
0x1401ff4c1  mov     dl, 1
0x1401ff4c3  call    NtOfsPurgeSecurityCache
0x1401ff4c8  mov     rax, [rdi]
0x1401ff4cb  mov     rcx, [rax+0D8h]; FileObject
0x1401ff4d2  test    rcx, rcx
0x1401ff4d5  jnz     loc_1401FF816
0x1401ff4db  mov     rax, [rdi]
0x1401ff4de  cmp     [rax+0D8h], r12
0x1401ff4e5  jnz     loc_1401FFB4F
0x1401ff4eb  mov     rcx, [rax+1338h]; Resource
0x1401ff4f2  test    rcx, rcx
0x1401ff4f5  jnz     loc_1401FFCCB
0x1401ff4fb  mov     rcx, [rdi]
0x1401ff4fe  cmp     [rcx+1A10h], r12
0x1401ff505  jz      short loc_1401FF51A
0x1401ff507  add     rcx, 1A08h; UnicodeString
0x1401ff50e  call    cs:__imp_RtlFreeUnicodeString
0x1401ff515  nop     dword ptr [rax+rax+00h]
0x1401ff51a  mov     rcx, [rdi]
0x1401ff51d  cmp     [rcx+1A20h], r12
0x1401ff524  jz      short loc_1401FF539
0x1401ff526  add     rcx, 1A18h; UnicodeString
0x1401ff52d  call    cs:__imp_RtlFreeUnicodeString
0x1401ff534  nop     dword ptr [rax+rax+00h]
0x1401ff539  mov     rcx, [rdi]
0x1401ff53c  cmp     [rcx+1A30h], r12
0x1401ff543  jz      short loc_1401FF558
0x1401ff545  add     rcx, 1A28h; UnicodeString
0x1401ff54c  call    cs:__imp_RtlFreeUnicodeString
0x1401ff553  nop     dword ptr [rax+rax+00h]
0x1401ff558  mov     rcx, [rdi]
0x1401ff55b  cmp     [rcx+1A40h], r12
0x1401ff562  jz      short loc_1401FF577
0x1401ff564  add     rcx, 1A38h; UnicodeString
0x1401ff56b  call    cs:__imp_RtlFreeUnicodeString
0x1401ff572  nop     dword ptr [rax+rax+00h]
0x1401ff577  mov     rcx, [rdi]
0x1401ff57a  cmp     [rcx+1A50h], r12
0x1401ff581  jz      short loc_1401FF596
0x1401ff583  add     rcx, 1A48h; UnicodeString
0x1401ff58a  call    cs:__imp_RtlFreeUnicodeString
0x1401ff591  nop     dword ptr [rax+rax+00h]
0x1401ff596  mov     rcx, [rdi]
0x1401ff599  cmp     [rcx+1EC8h], r12
0x1401ff5a0  jz      short loc_1401FF5B5
0x1401ff5a2  add     rcx, 1EC0h; UnicodeString
0x1401ff5a9  call    cs:__imp_RtlFreeUnicodeString
0x1401ff5b0  nop     dword ptr [rax+rax+00h]
0x1401ff5b5  mov     rcx, [rdi]
0x1401ff5b8  cmp     [rcx+658h], r12
0x1401ff5bf  jz      loc_1401FFD06
0x1401ff5c5  mov     rcx, [rdi]
0x1401ff5c8  cmp     [rcx+698h], r12
0x1401ff5cf  jz      loc_1401FF7DF
0x1401ff5d5  mov     rcx, [rdi]
0x1401ff5d8  lea     rax, [rcx+648h]
0x1401ff5df  mov     rbx, [rax]
0x1401ff5e2  cmp     rbx, rax
0x1401ff5e5  jnz     loc_1401FF773
0x1401ff5eb  mov     rcx, [rcx+0F0h]
0x1401ff5f2  test    rcx, rcx
0x1401ff5f5  jnz     loc_1401FFD36
0x1401ff5fb  mov     rcx, [rdi]
0x1401ff5fe  xor     edx, edx
0x1401ff600  add     rcx, 290h
0x1401ff607  mov     [rsp+58h+arg_8], r12b
0x1401ff60c  call    cs:__imp_ExAcquirePushLockSharedEx
0x1401ff613  nop     dword ptr [rax+rax+00h]
0x1401ff618  mov     rdx, [rdi]
0x1401ff61b  mov     rsi, r12
0x1401ff61e  mov     rax, [rdx+540h]
0x1401ff625  test    rax, rax
0x1401ff628  jz      short loc_1401FF63E
0x1401ff62a  mov     rcx, rax
0x1401ff62d  mov     rax, [rax]
0x1401ff630  test    rax, rax
0x1401ff633  jnz     short loc_1401FF62A
0x1401ff635  test    rcx, rcx
0x1401ff638  jz      short loc_1401FF63E
0x1401ff63a  mov     rsi, [rcx-8]
0x1401ff63e  lea     rcx, [rdx+290h]
0x1401ff645  mov     [rsp+58h+arg_18], rsi
0x1401ff64a  xor     edx, edx
0x1401ff64c  call    cs:__imp_ExReleasePushLockEx
0x1401ff653  nop     dword ptr [rax+rax+00h]
0x1401ff658  test    rsi, rsi
0x1401ff65b  jnz     loc_1401FFBB6
0x1401ff661  mov     rcx, [rdi]
0x1401ff664  mov     eax, [rcx+1924h]
0x1401ff66a  test    al, 2
0x1401ff66c  jz      short loc_1401FF6A7
0x1401ff66e  add     rcx, 1870h; FastMutex
0x1401ff675  call    cs:__imp_ExAcquireFastMutexUnsafe
0x1401ff67c  nop     dword ptr [rax+rax+00h]
0x1401ff681  mov     rcx, [rdi]
0x1401ff684  lea     rax, [rcx+1670h]
0x1401ff68b  cmp     [rax], rax
0x1401ff68e  jnz     loc_1401FFB8E
0x1401ff694  add     rcx, 1870h; FastMutex
0x1401ff69b  call    cs:__imp_ExReleaseFastMutexUnsafe
0x1401ff6a2  nop     dword ptr [rax+rax+00h]
0x1401ff6a7  mov     rax, [rdi]
0x1401ff6aa  mov     rcx, [rax+310h]; P
0x1401ff6b1  test    rcx, rcx
0x1401ff6b4  jnz     loc_1401FFC29
0x1401ff6ba  mov     rax, [rdi]
0x1401ff6bd  mov     [rax+310h], r12
0x1401ff6c4  mov     rax, [rdi]
0x1401ff6c7  mov     rcx, [rax+320h]; P
0x1401ff6ce  test    rcx, rcx
0x1401ff6d1  jnz     loc_1401FFC49
0x1401ff6d7  mov     rax, [rdi]
0x1401ff6da  mov     rcx, [rax+1260h]; P
0x1401ff6e1  test    rcx, rcx
0x1401ff6e4  jnz     loc_1401FFD67
0x1401ff6ea  mov     rax, [rdi]
0x1401ff6ed  mov     rcx, [rax+1EB8h]; P
0x1401ff6f4  test    rcx, rcx
0x1401ff6f7  jnz     loc_1401FFD94
0x1401ff6fd  mov     rcx, [rdi]
0x1401ff700  add     rcx, 5B8h; NotifySync
0x1401ff707  call    cs:__imp_FsRtlNotifyUninitializeSync
0x1401ff70e  nop     dword ptr [rax+rax+00h]
0x1401ff713  mov     rcx, [rdi]
0x1401ff716  mov     rcx, [rcx+0E8h]; P
0x1401ff71d  call    LfsDeleteLogHandle
0x1401ff722  mov     rax, [rdi]
0x1401ff725  mov     [rax+0E8h], r12
0x1401ff72c  mov     rdx, [rdi]
0x1401ff72f  lea     rax, [rdx+1340h]
0x1401ff736  mov     rcx, [rax]; P
0x1401ff739  cmp     rcx, rax
0x1401ff73c  jz      loc_1401FF85F
0x1401ff742  mov     rax, [rcx]
0x1401ff745  cmp     [rax+8], rcx
0x1401ff749  jnz     loc_1401FF80F
0x1401ff74f  mov     rdx, [rcx+8]
0x1401ff753  cmp     [rdx], rcx
0x1401ff756  jnz     loc_1401FF80F
0x1401ff75c  mov     [rdx], rax
0x1401ff75f  mov     [rax+8], rdx
0x1401ff763  xor     edx, edx; Tag
0x1401ff765  call    cs:__imp_ExFreePoolWithTag
0x1401ff76c  nop     dword ptr [rax+rax+00h]
0x1401ff771  jmp     short loc_1401FF72C
0x1401ff773  cmp     [rbx+8], rax
0x1401ff777  jnz     loc_1401FF80F
0x1401ff77d  mov     rcx, [rbx]
0x1401ff780  cmp     [rcx+8], rbx
0x1401ff784  jnz     loc_1401FF80F
0x1401ff78a  mov     [rax], rcx
0x1401ff78d  mov     [rcx+8], rax
0x1401ff791  lea     rcx, [rbx+10h]; Mcb
0x1401ff795  call    cs:__imp_FsRtlUninitializeBaseMcb
0x1401ff79c  nop     dword ptr [rax+rax+00h]
0x1401ff7a1  mov     rcx, [rdi]
0x1401ff7a4  lea     rax, [rcx+698h]
0x1401ff7ab  cmp     rbx, rax
0x1401ff7ae  jz      loc_1401FF5D5
0x1401ff7b4  lea     rax, [rcx+658h]
0x1401ff7bb  cmp     rbx, rax
0x1401ff7be  jz      loc_1401FF5D5
0x1401ff7c4  mov     rdx, rbx; Entry
0x1401ff7c7  lea     rcx, NtfsDeallocatedClustersLookasideList; Lookaside
0x1401ff7ce  call    cs:__imp_ExFreeToLookasideListEx
0x1401ff7d5  nop     dword ptr [rax+rax+00h]
0x1401ff7da  jmp     loc_1401FF5D5
0x1401ff7df  mov     eax, [rcx+6D0h]
0x1401ff7e5  test    al, 2
0x1401ff7e7  jnz     loc_1401FF5D5
0x1401ff7ed  add     rcx, 6A8h; Mcb
0x1401ff7f4  call    cs:__imp_FsRtlUninitializeBaseMcb
0x1401ff7fb  nop     dword ptr [rax+rax+00h]
0x1401ff800  mov     rax, [rdi]
0x1401ff803  or      dword ptr [rax+6D0h], 2
0x1401ff80a  jmp     loc_1401FF5D5
0x1401ff80f  mov     ecx, 3
0x1401ff814  int     29h; Win8: RtlFailFast(ecx)
0x1401ff816  mov     eax, [rax+23Ch]
0x1401ff81c  test    al, 8
0x1401ff81e  jnz     loc_1401FF4DB
0x1401ff824  xor     r8d, r8d; UninitializeEvent
0x1401ff827  lea     rdx, NtfsLarge0; TruncateSize
0x1401ff82e  call    cs:__imp_CcUninitializeCacheMap
0x1401ff835  nop     dword ptr [rax+rax+00h]
0x1401ff83a  mov     rax, [rdi]
0x1401ff83d  or      dword ptr [rax+23Ch], 8
0x1401ff844  mov     rcx, [rdi]
0x1401ff847  mov     rcx, [rcx+0D8h]; Object
0x1401ff84e  call    cs:__imp_ObfDereferenceObject
0x1401ff855  nop     dword ptr [rax+rax+00h]
0x1401ff85a  jmp     loc_1401FF4DB
0x1401ff85f  lea     rcx, [rdx+340h]; Resource
0x1401ff866  call    NtfsFreeRestartTable
0x1401ff86b  mov     rcx, [rdi]
0x1401ff86e  add     rcx, 428h; Resource
0x1401ff875  call    NtfsFreeRestartTable
0x1401ff87a  mov     rcx, [rdi]
0x1401ff87d  test    dword ptr [rcx+4], 400h
0x1401ff884  jnz     loc_1401FFB61
0x1401ff88a  mov     rcx, [rdi]
0x1401ff88d  add     rcx, 1368h
0x1401ff894  call    NtfsUninitializeHashTable
0x1401ff899  mov     rcx, [rdi]
0x1401ff89c  call    NtfsTeardownCorruptionLru
0x1401ff8a1  mov     rcx, [rdi]
0x1401ff8a4  call    NtfsTeardownTornWriteLru
0x1401ff8a9  mov     rcx, [rdi]
0x1401ff8ac  add     rcx, 870h; Resource
0x1401ff8b3  call    cs:__imp_ExDeleteResourceLite
0x1401ff8ba  nop     dword ptr [rax+rax+00h]
0x1401ff8bf  mov     rcx, [rdi]
0x1401ff8c2  add     rcx, 918h; Resource
0x1401ff8c9  call    cs:__imp_ExDeleteResourceLite
0x1401ff8d0  nop     dword ptr [rax+rax+00h]
0x1401ff8d5  mov     rcx, [rdi]
0x1401ff8d8  add     rcx, 1A90h; Resource
0x1401ff8df  call    cs:__imp_ExDeleteResourceLite
0x1401ff8e6  nop     dword ptr [rax+rax+00h]
0x1401ff8eb  mov     rcx, [rdi]
0x1401ff8ee  add     rcx, 1B18h; Resource
0x1401ff8f5  call    cs:__imp_ExDeleteResourceLite
0x1401ff8fc  nop     dword ptr [rax+rax+00h]
0x1401ff901  mov     rcx, [rdi]
0x1401ff904  add     rcx, 2D90h; Resource
0x1401ff90b  call    cs:__imp_ExDeleteResourceLite
0x1401ff912  nop     dword ptr [rax+rax+00h]
0x1401ff917  mov     rcx, [rdi]
0x1401ff91a  add     rcx, 1ED0h; Resource
0x1401ff921  call    cs:__imp_ExDeleteResourceLite
0x1401ff928  nop     dword ptr [rax+rax+00h]
0x1401ff92d  mov     rcx, [rdi]
0x1401ff930  add     rcx, 1F60h; Resource
0x1401ff937  call    cs:__imp_ExDeleteResourceLite
0x1401ff93e  nop     dword ptr [rax+rax+00h]
0x1401ff943  mov     rcx, [rdi]
0x1401ff946  add     rcx, 2A28h; Resource
0x1401ff94d  call    cs:__imp_ExDeleteResourceLite
0x1401ff954  nop     dword ptr [rax+rax+00h]
0x1401ff959  mov     rcx, [rdi]
0x1401ff95c  add     rcx, 29C0h; Resource
0x1401ff963  call    cs:__imp_ExDeleteResourceLite
0x1401ff96a  nop     dword ptr [rax+rax+00h]
0x1401ff96f  mov     rcx, [rdi]
0x1401ff972  add     rcx, 2C98h; Resource
0x1401ff979  call    cs:__imp_ExDeleteResourceLite
0x1401ff980  nop     dword ptr [rax+rax+00h]
0x1401ff985  mov     rax, [rdi]
0x1401ff988  mov     rcx, [rax+328h]; P
0x1401ff98f  test    rcx, rcx
0x1401ff992  jz      short loc_1401FF9AC
0x1401ff994  xor     edx, edx; Tag
0x1401ff996  call    cs:__imp_ExFreePoolWithTag
0x1401ff99d  nop     dword ptr [rax+rax+00h]
0x1401ff9a2  mov     rax, [rdi]
0x1401ff9a5  mov     [rax+328h], r12
0x1401ff9ac  mov     rcx, [rdi]
0x1401ff9af  add     rcx, 1270h; Cache
0x1401ff9b6  call    cs:__imp_FsRtlDeleteTunnelCache
0x1401ff9bd  nop     dword ptr [rax+rax+00h]
0x1401ff9c2  mov     rax, [rdi]
0x1401ff9c5  mov     rcx, [rax+1618h]; P
0x1401ff9cc  test    rcx, rcx
0x1401ff9cf  jz      short loc_1401FF9DF
0x1401ff9d1  xor     edx, edx; Tag
0x1401ff9d3  call    cs:__imp_ExFreePoolWithTag
0x1401ff9da  nop     dword ptr [rax+rax+00h]
0x1401ff9df  mov     rax, [rdi]
0x1401ff9e2  mov     rcx, [rax+1620h]; P
0x1401ff9e9  test    rcx, rcx
0x1401ff9ec  jz      short loc_1401FF9FC
0x1401ff9ee  xor     edx, edx; Tag
  ... truncated ...
```
