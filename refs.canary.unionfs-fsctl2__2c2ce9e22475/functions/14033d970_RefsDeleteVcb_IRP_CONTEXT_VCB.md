# RefsDeleteVcb(_IRP_CONTEXT *,_VCB *)

- ea: `0x14033d970`
- end: `0x14033e1d2`
- name: `?RefsDeleteVcb@@YAXPEAU_IRP_CONTEXT@@PEAU_VCB@@@Z`
- size: `2146`
- prototype: `void __fastcall(struct _IRP_CONTEXT *, struct _VCB *)`
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x1400b2d58`

## callees

- `0x14000bcc0`
- `0x140072970`
- `0x140080680`
- `0x140087ea0`
- `0x14008c400`
- `0x14008e3c0`
- `0x14008fc50`
- `0x140092e30`
- `0x1400ac480`
- `0x1400b0128`
- `0x1400b4a64`
- `0x1400c61c4`
- `0x1402f9024`
- `0x1403113e4`
- `0x140311670`
- `0x140311984`
- `0x14032b830`
- `0x14033d970`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x14033e140`
- `ntoskrnl!ObfDereferenceObject` at `0x14033e140`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x14033de13`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x14033de13`
- `ntoskrnl!ExInitializeFastOwnerEntry` at `0x14033dc47`
- `ntoskrnl!ExInitializeFastOwnerEntry` at `0x14033de59`
- `ntoskrnl!ExInitializeFastOwnerEntry` at `0x14033dc47`
- `ntoskrnl!ExInitializeFastOwnerEntry` at `0x14033de59`
- `ntoskrnl!MmFreeMappingAddress` at `0x14033e0f6`
- `ntoskrnl!MmFreeMappingAddress` at `0x14033e113`
- `ntoskrnl!MmFreeMappingAddress` at `0x14033e0f6`
- `ntoskrnl!MmFreeMappingAddress` at `0x14033e113`
- `ntoskrnl!ExAcquireFastMutex` at `0x14033d9ba`
- `ntoskrnl!ExAcquireFastMutex` at `0x14033d9ba`
- `ntoskrnl!ExReleaseFastMutex` at `0x14033d9eb`
- `ntoskrnl!ExReleaseFastMutex` at `0x14033d9eb`
- `ntoskrnl!KeQueryHighestNodeNumber` at `0x14033dfc6`
- `ntoskrnl!KeQueryHighestNodeNumber` at `0x14033dfc6`
- `ntoskrnl!KeEnterGuardedRegion` at `0x14033dd0c`
- `ntoskrnl!KeEnterGuardedRegion` at `0x14033dd0c`
- `ntoskrnl!FsRtlHeatUninit` at `0x14033da70`
- `ntoskrnl!FsRtlHeatUninit` at `0x14033da70`
- `ntoskrnl!FsRtlNotifyUninitializeSync` at `0x14033df26`
- `ntoskrnl!FsRtlNotifyUninitializeSync` at `0x14033df26`
- `ntoskrnl!ExDeleteFastResource` at `0x14033dfac`
- `ntoskrnl!ExDeleteFastResource` at `0x14033e153`
- `ntoskrnl!ExDeleteFastResource` at `0x14033dfac`
- `ntoskrnl!ExDeleteFastResource` at `0x14033e153`
- `ntoskrnl!IoDeleteDevice` at `0x14033e1af`
- `ntoskrnl!IoDeleteDevice` at `0x14033e1af`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14033dd1b`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14033dd1b`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14033dd8b`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14033dd8b`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x14033dd97`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x14033dd97`
- `ntoskrnl!ExReleaseFastResource` at `0x14033dc95`
- `ntoskrnl!ExReleaseFastResource` at `0x14033dea7`
- `ntoskrnl!ExReleaseFastResource` at `0x14033dc95`
- `ntoskrnl!ExReleaseFastResource` at `0x14033dea7`
- `ntoskrnl!ExAcquireFastResourceShared` at `0x14033dc62`
- `ntoskrnl!ExAcquireFastResourceShared` at `0x14033de74`
- `ntoskrnl!ExAcquireFastResourceShared` at `0x14033dc62`
- `ntoskrnl!ExAcquireFastResourceShared` at `0x14033de74`
- `ntoskrnl!ExFreePoolWithTag` at `0x14033d9db`
- `ntoskrnl!ExFreePoolWithTag` at `0x14033da10`
- `ntoskrnl!ExFreePoolWithTag` at `0x14033da9b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14033dabf`
- `ntoskrnl!ExFreePoolWithTag` at `0x14033dae3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14033db07`
- `ntoskrnl!ExFreePoolWithTag` at `0x14033db2b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14033dee5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14033df09`
- `ntoskrnl!ExFreePoolWithTag` at `0x14033df44`
- `ntoskrnl!ExFreePoolWithTag` at `0x14033df7a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14033e052`
- `ntoskrnl!ExFreePoolWithTag` at `0x14033e06f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14033e090`
- `ntoskrnl!ExFreePoolWithTag` at `0x14033e0b1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14033e0d2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14033e12d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14033e16d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14033d9db`
- `ntoskrnl!ExFreePoolWithTag` at `0x14033da10`
- `ntoskrnl!ExFreePoolWithTag` at `0x14033da9b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14033dabf`
- `ntoskrnl!ExFreePoolWithTag` at `0x14033dae3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14033db07`
- `ntoskrnl!ExFreePoolWithTag` at `0x14033db2b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14033dee5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14033df09`
- `ntoskrnl!ExFreePoolWithTag` at `0x14033df44`
- `ntoskrnl!ExFreePoolWithTag` at `0x14033df7a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14033e052`
- `ntoskrnl!ExFreePoolWithTag` at `0x14033e06f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14033e090`
- `ntoskrnl!ExFreePoolWithTag` at `0x14033e0b1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14033e0d2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14033e12d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14033e16d`

## pseudocode

```c
void __fastcall RefsDeleteVcb(struct _IRP_CONTEXT *a1, struct _VCB *a2)
{
  char *v2; // rbx
  struct _VCB *v3; // rbp
  void *v5; // rcx
  void *v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // r8
  SmsCheckpointContext *v11; // r14
  void *v12; // rcx
  void *v13; // rcx
  void *v14; // rcx
  void *v15; // rcx
  void *v16; // rcx
  CmsReferenced *v17; // rcx
  __int64 v18; // rcx
  CmsReferenced *v19; // rcx
  __int64 v20; // rcx
  CmsReferenced *v21; // rcx
  __int64 v22; // rcx
  CmsReferenced *v23; // rcx
  __int64 v24; // rcx
  CmsReferenced *v25; // rcx
  __int64 v26; // rcx
  __int64 v27; // rcx
  __int64 v28; // rbx
  struct _FCB *v29; // rbx
  __int64 v30; // rcx
  __int64 v31; // r8
  struct _FCB *v32; // rsi
  __int64 v33; // r8
  PFAST_MUTEX *p_FastMutex; // rbp
  __int64 p_OldIrql; // r14
  struct _FAST_MUTEX *v36; // rbx
  _QWORD *v37; // rsi
  _QWORD *v38; // rax
  _QWORD *v39; // rdi
  struct _FCB *v40; // rbx
  __int64 v41; // rcx
  struct _FCB *v42; // rsi
  LARGE_INTEGER *p_FileSize; // rdi
  __int64 v44; // rbx
  __int64 v45; // r8
  __int64 v46; // rcx
  __int64 v47; // r8
  void *v48; // rcx
  void *v49; // rcx
  PVOID *v50; // rbx
  USHORT HighestNodeNumber; // ax
  unsigned int v52; // r14d
  unsigned int v53; // r15d
  __int64 v54; // r8
  unsigned int i; // esi
  __int64 v56; // rbx
  __int64 v57; // rax
  __int64 v58; // rdx
  __int64 *v59; // rcx
  __int64 v60; // rax
  void *v61; // rcx
  void *v62; // rcx
  void *v63; // rcx
  void *v64; // rcx
  void *v65; // rcx
  void *v66; // rcx
  void *v67; // rcx
  _OWORD v68[4]; // [rsp+20h] [rbp-88h] BYREF
  __int64 v69; // [rsp+60h] [rbp-48h]
  char v70; // [rsp+B0h] [rbp+8h] BYREF
  struct _VCB *v71; // [rsp+B8h] [rbp+10h]
  struct _FCB *NextFcbTableEntry; // [rsp+C0h] [rbp+18h] BYREF

  v71 = a2;
  v2 = (char *)a2 + 10344;
  v3 = a2;
  memset(v68, 0, sizeof(v68));
  v69 = 0;
  if ( *((_QWORD *)a2 + 1293) )
  {
    ExAcquireFastMutex((PFAST_MUTEX)((char *)a2 + 10392));
    FsLibIoFailureResetTable(v2);
    v5 = (void *)_InterlockedExchange64((volatile __int64 *)v2, 0);
    if ( v5 )
      ExFreePoolWithTag(v5, 0);
    ExReleaseFastMutex((PFAST_MUTEX)(v2 + 48));
  }
  *((_WORD *)v3 + 5244) = 0;
  v6 = (void *)_InterlockedExchange64((volatile __int64 *)v3 + 1310, 0);
  if ( v6 )
    ExFreePoolWithTag(v6, 0);
  v7 = *((_QWORD *)a1 + 13);
  v8 = v7 + 160;
  if ( (*(_QWORD *)(v7 + 8) & 0x20000000000LL) == 0 )
  {
    MsInitializeFastResourceOwnerEntry(v8);
    *(_QWORD *)(v9 + 8) |= v10;
  }
  v11 = (struct _VCB *)((char *)v3 + 1312);
  MsAcquireFastResourceExclusive((char *)v3 + 1312, v8, *((_BYTE *)a1 + 8) & 1);
  if ( (*((_DWORD *)v3 + 7) & 0x20) != 0 )
    FsRtlHeatUninit((char *)v3 + 6564, (char *)v3 + 6588);
  NtOfsPurgeSecurityCache(v3, 1u);
  *((_BYTE *)v3 + 6561) = 1;
  v12 = (void *)*((_QWORD *)v3 + 788);
  if ( v12 )
    ExFreePoolWithTag(v12, 0);
  *(_OWORD *)((char *)v3 + 6296) = 0;
  v13 = (void *)*((_QWORD *)v3 + 790);
  if ( v13 )
    ExFreePoolWithTag(v13, 0);
  *(_OWORD *)((char *)v3 + 6312) = 0;
  v14 = (void *)*((_QWORD *)v3 + 792);
  if ( v14 )
    ExFreePoolWithTag(v14, 0);
  *(_OWORD *)((char *)v3 + 6328) = 0;
  v15 = (void *)*((_QWORD *)v3 + 794);
  if ( v15 )
    ExFreePoolWithTag(v15, 0);
  *(_OWORD *)((char *)v3 + 6344) = 0;
  v16 = (void *)*((_QWORD *)v3 + 770);
  if ( v16 )
    ExFreePoolWithTag(v16, 0);
  *(_OWORD *)((char *)v3 + 6152) = 0;
  v17 = (CmsReferenced *)*((_QWORD *)v3 + 1371);
  if ( v17 )
    CmsReferenced::Release(v17);
  v18 = *((_QWORD *)v3 + 1370);
  if ( v18 )
    MsReleaseTable(v18);
  v19 = (CmsReferenced *)*((_QWORD *)v3 + 1377);
  if ( v19 )
    CmsReferenced::Release(v19);
  v20 = *((_QWORD *)v3 + 1376);
  if ( v20 )
    MsReleaseTable(v20);
  v21 = (CmsReferenced *)*((_QWORD *)v3 + 1383);
  if ( v21 )
    CmsReferenced::Release(v21);
  v22 = *((_QWORD *)v3 + 1382);
  if ( v22 )
    MsReleaseTable(v22);
  v23 = (CmsReferenced *)*((_QWORD *)v3 + 1389);
  if ( v23 )
    CmsReferenced::Release(v23);
  v24 = *((_QWORD *)v3 + 1388);
  if ( v24 )
    MsReleaseTable(v24);
  v25 = (CmsReferenced *)*((_QWORD *)v3 + 1395);
  if ( v25 )
    CmsReferenced::Release(v25);
  v26 = *((_QWORD *)v3 + 1394);
  if ( v26 )
    MsReleaseTable(v26);
  v27 = *((_QWORD *)v3 + 1400);
  if ( v27 )
    MsReleaseTable(v27);
  v28 = *((_QWORD *)v3 + 25);
  if ( v28 )
  {
    v29 = *(struct _FCB **)(v28 + 48);
    RefsAcquireExclusiveFcb(a1, v29, 0, 1);
    RefsDeleteLcb(v30, *((_QWORD *)v3 + 25), 0);
    RefsReleaseFcb(a1, v29);
  }
  NextFcbTableEntry = 0;
  ExInitializeFastOwnerEntry(v68);
  LOBYTE(v31) = 1;
  ExAcquireFastResourceShared((char *)v3 + 624, v68, v31);
  NextFcbTableEntry = RefsGetNextFcbTableEntry(v3, (void **)&NextFcbTableEntry);
  v32 = NextFcbTableEntry;
  ExReleaseFastResource((char *)v3 + 624, v68);
  if ( v32 )
  {
    do
    {
      RefsAcquireExclusiveFcb(a1, v32, 0, 1);
      p_FastMutex = &v32->Header.FastMutex;
      while ( *p_FastMutex != (PFAST_MUTEX)p_FastMutex )
      {
        p_OldIrql = (__int64)&(*p_FastMutex)[-3].OldIrql;
        if ( *p_FastMutex == (PFAST_MUTEX)120 )
          break;
        if ( (unsigned __int16)(*(_WORD *)p_OldIrql - 2051) <= 1u )
        {
          v36 = *(struct _FAST_MUTEX **)(p_OldIrql + 48);
          KeEnterGuardedRegion();
          ExAcquireFastMutexUnsafe(v36);
          _InterlockedIncrement((volatile signed __int32 *)(p_OldIrql + 172));
          v37 = (_QWORD *)(p_OldIrql + 376);
          while ( 1 )
          {
            v38 = (_QWORD *)*v37;
            if ( (_QWORD *)*v37 == v37 )
              break;
            v39 = v38 - 1;
            if ( v38 == (_QWORD *)8 )
              break;
            v40 = (struct _FCB *)v39[6];
            RefsAcquireExclusiveFcb(a1, v40, 0, 1);
            RefsDeleteLcb(v41, v39, 0);
            RefsReleaseFcb(a1, v40);
          }
          ++*(_DWORD *)(p_OldIrql + 172);
          ExReleaseFastMutexUnsafe(*(PFAST_MUTEX *)(p_OldIrql + 48));
          KeLeaveGuardedRegion();
        }
        RefsDeleteScb(a1, (struct _SCB *)p_OldIrql);
      }
      v42 = NextFcbTableEntry;
      v3 = v71;
      p_FileSize = &NextFcbTableEntry->Header.FileSize;
      while ( (LARGE_INTEGER *)p_FileSize->QuadPart != p_FileSize )
      {
        v44 = p_FileSize->QuadPart - 32;
        if ( p_FileSize->QuadPart == 32 )
          break;
        RefsAcquireExclusiveFcb(a1, *(_QWORD *)(*(_QWORD *)(v44 + 24) + 136LL), 0, 1);
        LOBYTE(v45) = 1;
        RefsDeleteLcb(v46, v44, v45);
      }
      LOBYTE(v33) = 1;
      ExAcquireFastResourceExclusive((char *)v3 + 624, 0, v33);
      v70 = 0;
      v42->FcbTableEntry.HashLinks.Flink = (struct _LIST_ENTRY *)&v70;
      RefsDeleteFcb(a1, v42, (unsigned __int8 *)&NextFcbTableEntry);
      NextFcbTableEntry = 0;
      ExInitializeFastOwnerEntry(v68);
      LOBYTE(v47) = 1;
      ExAcquireFastResourceShared((char *)v3 + 624, v68, v47);
      NextFcbTableEntry = RefsGetNextFcbTableEntry(v3, (void **)&NextFcbTableEntry);
      v32 = NextFcbTableEntry;
      ExReleaseFastResource((char *)v3 + 624, v68);
    }
    while ( v32 );
    v11 = (struct _VCB *)((char *)v3 + 1312);
  }
  *((_QWORD *)v3 + 100) = 0;
  v48 = (void *)*((_QWORD *)v3 + 103);
  if ( v48 )
    ExFreePoolWithTag(v48, 0);
  *((_OWORD *)v3 + 51) = 0;
  v49 = (void *)*((_QWORD *)v3 + 1659);
  if ( v49 )
    ExFreePoolWithTag(v49, 0);
  *((_OWORD *)v3 + 829) = 0;
  FsRtlNotifyUninitializeSync((PNOTIFY_SYNC *)v3 + 108);
  if ( (*((_DWORD *)v3 + 6) & 0x400) != 0 )
  {
    ExFreePoolWithTag(*((PVOID *)v3 + 26), 0);
    *((_QWORD *)v3 + 26) = 0;
  }
  v50 = (PVOID *)((char *)v3 + 3624);
  if ( (char *)v3 + 3624 != (char *)v3 + 5672 )
  {
    do
    {
      if ( *v50 )
      {
        ExFreePoolWithTag(*v50, 0);
        *v50 = 0;
      }
      ++v50;
    }
    while ( v50 != (PVOID *)((char *)v3 + 5672) );
  }
  RefsReleaseVcb(a1, v3);
  SmsCheckpointContext::~SmsCheckpointContext(v11);
  ExDeleteFastResource((char *)v3 + 6168);
  if ( *((_QWORD *)v3 + 730) )
  {
    HighestNodeNumber = KeQueryHighestNodeNumber();
    v52 = 0;
    v53 = HighestNodeNumber + 1;
    if ( HighestNodeNumber != -1 )
    {
      do
      {
        v54 = *((_QWORD *)v3 + 730);
        if ( *(_QWORD *)(v54 + 16LL * v52 + 8) )
        {
          for ( i = 0; i < *(_DWORD *)(v54 + 16LL * v52); ++i )
          {
            v56 = 48LL * i;
            while ( 1 )
            {
              v54 = *((_QWORD *)v3 + 730);
              v57 = *(_QWORD *)(v54 + 16LL * v52 + 8);
              if ( *(_QWORD *)(v56 + v57 + 32) == v56 + v57 + 32 )
                break;
              v58 = v56 + v57 + 32;
              v59 = *(__int64 **)v58;
              if ( *(_QWORD *)(*(_QWORD *)v58 + 8LL) != v58 || (v60 = *v59, *(__int64 **)(*v59 + 8) != v59) )
                __fastfail(3u);
              *(_QWORD *)v58 = v60;
              *(_QWORD *)(v60 + 8) = v58;
              ExFreePoolWithTag(v59, 0);
            }
          }
          ExFreePoolWithTag(*(PVOID *)(v54 + 16LL * v52 + 8), 0);
        }
        ++v52;
      }
      while ( v52 < v53 );
    }
    ExFreePoolWithTag(*((PVOID *)v3 + 730), 0);
    *((_QWORD *)v3 + 730) = 0;
  }
  v61 = (void *)*((_QWORD *)v3 + 731);
  if ( v61 )
  {
    ExFreePoolWithTag(v61, 0);
    *((_QWORD *)v3 + 731) = 0;
  }
  v62 = (void *)*((_QWORD *)v3 + 101);
  if ( v62 )
  {
    ExFreePoolWithTag(v62, 0);
    *((_QWORD *)v3 + 101) = 0;
  }
  v63 = (void *)*((_QWORD *)v3 + 734);
  if ( v63 )
    MmFreeMappingAddress(v63, 0x62666552u);
  v64 = (void *)*((_QWORD *)v3 + 742);
  if ( v64 )
    MmFreeMappingAddress(v64, 0x62666552u);
  v65 = (void *)*((_QWORD *)v3 + 750);
  if ( v65 )
    ExFreePoolWithTag(v65, 0);
  ObfDereferenceObject(*((PVOID *)v3 + 24));
  ExDeleteFastResource((char *)v3 + 1208);
  v66 = (void *)*((_QWORD *)v3 + 451);
  if ( v66 )
  {
    ExFreePoolWithTag(v66, 0);
    *((_QWORD *)v3 + 451) = 0;
  }
  MsKmeDeleteReservedIoRequestsForVcb(v3);
  MsKmeDeleteReservedIoRunsForVcb(v3);
  v67 = (void *)*((_QWORD *)v3 + 1364);
  if ( v67 )
  {
    operator delete(v67);
    *((_QWORD *)v3 + 1364) = 0;
  }
  IoDeleteDevice((PDEVICE_OBJECT)((char *)v3 - 384));
}

```

## disassembly

```asm
0x14033d970  mov     [rsp+arg_8], rdx
0x14033d975  push    rbx
0x14033d976  push    rbp
0x14033d977  push    rsi
0x14033d978  push    rdi
0x14033d979  push    r13
0x14033d97b  push    r14
0x14033d97d  push    r15
0x14033d97f  sub     rsp, 70h
0x14033d983  xorps   xmm0, xmm0
0x14033d986  lea     rbx, [rdx+2868h]
0x14033d98d  xor     eax, eax
0x14033d98f  xor     r13d, r13d
0x14033d992  mov     rbp, rdx
0x14033d995  mov     r15, rcx
0x14033d998  movups  [rsp+0A8h+var_88], xmm0
0x14033d99d  mov     [rsp+0A8h+var_48], rax
0x14033d9a2  movups  [rsp+0A8h+var_78], xmm0
0x14033d9a7  movups  [rsp+0A8h+var_68], xmm0
0x14033d9ac  movups  [rsp+0A8h+var_58], xmm0
0x14033d9b1  cmp     [rbx], rax
0x14033d9b4  jz      short loc_14033D9F7
0x14033d9b6  lea     rcx, [rbx+30h]; FastMutex
0x14033d9ba  call    cs:__imp_ExAcquireFastMutex
0x14033d9c1  nop     dword ptr [rax+rax+00h]
0x14033d9c6  mov     rcx, rbx
0x14033d9c9  call    FsLibIoFailureResetTable
0x14033d9ce  mov     ecx, r13d
0x14033d9d1  xchg    rcx, [rbx]; P
0x14033d9d4  test    rcx, rcx
0x14033d9d7  jz      short loc_14033D9E7
0x14033d9d9  xor     edx, edx; Tag
0x14033d9db  call    cs:__imp_ExFreePoolWithTag
0x14033d9e2  nop     dword ptr [rax+rax+00h]
0x14033d9e7  lea     rcx, [rbx+30h]; FastMutex
0x14033d9eb  call    cs:__imp_ExReleaseFastMutex
0x14033d9f2  nop     dword ptr [rax+rax+00h]
0x14033d9f7  mov     rcx, r13
0x14033d9fa  mov     [rbp+28F8h], r13w
0x14033da02  xchg    rcx, [rbp+28F0h]; P
0x14033da09  test    rcx, rcx
0x14033da0c  jz      short loc_14033DA1C
0x14033da0e  xor     edx, edx; Tag
0x14033da10  call    cs:__imp_ExFreePoolWithTag
0x14033da17  nop     dword ptr [rax+rax+00h]
0x14033da1c  mov     rdx, [r15+68h]
0x14033da20  mov     r8, 20000000000h
0x14033da2a  lea     rcx, [rdx+0A0h]
0x14033da31  test    [rdx+8], r8
0x14033da35  jnz     short loc_14033DA40
0x14033da37  call    MsInitializeFastResourceOwnerEntry
0x14033da3c  or      [rdx+8], r8
0x14033da40  movzx   r8d, byte ptr [r15+8]
0x14033da45  lea     r14, [rbp+520h]
0x14033da4c  mov     rdx, rcx
0x14033da4f  and     r8b, 1
0x14033da53  mov     rcx, r14
0x14033da56  call    MsAcquireFastResourceExclusive
0x14033da5b  mov     eax, [rbp+1Ch]
0x14033da5e  test    al, 20h
0x14033da60  jz      short loc_14033DA7C
0x14033da62  lea     rdx, [rbp+19BCh]
0x14033da69  lea     rcx, [rbp+19A4h]
0x14033da70  call    cs:__imp_FsRtlHeatUninit
0x14033da77  nop     dword ptr [rax+rax+00h]
0x14033da7c  mov     dl, 1; unsigned __int8
0x14033da7e  mov     rcx, rbp; struct _VCB *
0x14033da81  call    ?NtOfsPurgeSecurityCache@@YAXPEAU_VCB@@E@Z; NtOfsPurgeSecurityCache(_VCB *,uchar)
0x14033da86  mov     byte ptr [rbp+19A1h], 1
0x14033da8d  mov     rcx, [rbp+18A0h]; P
0x14033da94  test    rcx, rcx
0x14033da97  jz      short loc_14033DAA7
0x14033da99  xor     edx, edx; Tag
0x14033da9b  call    cs:__imp_ExFreePoolWithTag
0x14033daa2  nop     dword ptr [rax+rax+00h]
0x14033daa7  xorps   xmm0, xmm0
0x14033daaa  movups  xmmword ptr [rbp+1898h], xmm0
0x14033dab1  mov     rcx, [rbp+18B0h]; P
0x14033dab8  test    rcx, rcx
0x14033dabb  jz      short loc_14033DACB
0x14033dabd  xor     edx, edx; Tag
0x14033dabf  call    cs:__imp_ExFreePoolWithTag
0x14033dac6  nop     dword ptr [rax+rax+00h]
0x14033dacb  xorps   xmm0, xmm0
0x14033dace  movups  xmmword ptr [rbp+18A8h], xmm0
0x14033dad5  mov     rcx, [rbp+18C0h]; P
0x14033dadc  test    rcx, rcx
0x14033dadf  jz      short loc_14033DAEF
0x14033dae1  xor     edx, edx; Tag
0x14033dae3  call    cs:__imp_ExFreePoolWithTag
0x14033daea  nop     dword ptr [rax+rax+00h]
0x14033daef  xorps   xmm0, xmm0
0x14033daf2  movups  xmmword ptr [rbp+18B8h], xmm0
0x14033daf9  mov     rcx, [rbp+18D0h]; P
0x14033db00  test    rcx, rcx
0x14033db03  jz      short loc_14033DB13
0x14033db05  xor     edx, edx; Tag
0x14033db07  call    cs:__imp_ExFreePoolWithTag
0x14033db0e  nop     dword ptr [rax+rax+00h]
0x14033db13  xorps   xmm0, xmm0
0x14033db16  movups  xmmword ptr [rbp+18C8h], xmm0
0x14033db1d  mov     rcx, [rbp+1810h]; P
0x14033db24  test    rcx, rcx
0x14033db27  jz      short loc_14033DB37
0x14033db29  xor     edx, edx; Tag
0x14033db2b  call    cs:__imp_ExFreePoolWithTag
0x14033db32  nop     dword ptr [rax+rax+00h]
0x14033db37  xorps   xmm0, xmm0
0x14033db3a  movups  xmmword ptr [rbp+1808h], xmm0
0x14033db41  mov     rcx, [rbp+2AD8h]; this
0x14033db48  test    rcx, rcx
0x14033db4b  jz      short loc_14033DB52
0x14033db4d  call    ?Release@CmsReferenced@@QEAAXXZ; CmsReferenced::Release(void)
0x14033db52  mov     rcx, [rbp+2AD0h]
0x14033db59  test    rcx, rcx
0x14033db5c  jz      short loc_14033DB63
0x14033db5e  call    MsReleaseTable
0x14033db63  mov     rcx, [rbp+2B08h]; this
0x14033db6a  test    rcx, rcx
0x14033db6d  jz      short loc_14033DB74
0x14033db6f  call    ?Release@CmsReferenced@@QEAAXXZ; CmsReferenced::Release(void)
0x14033db74  mov     rcx, [rbp+2B00h]
0x14033db7b  test    rcx, rcx
0x14033db7e  jz      short loc_14033DB85
0x14033db80  call    MsReleaseTable
0x14033db85  mov     rcx, [rbp+2B38h]; this
0x14033db8c  test    rcx, rcx
0x14033db8f  jz      short loc_14033DB96
0x14033db91  call    ?Release@CmsReferenced@@QEAAXXZ; CmsReferenced::Release(void)
0x14033db96  mov     rcx, [rbp+2B30h]
0x14033db9d  test    rcx, rcx
0x14033dba0  jz      short loc_14033DBA7
0x14033dba2  call    MsReleaseTable
0x14033dba7  mov     rcx, [rbp+2B68h]; this
0x14033dbae  test    rcx, rcx
0x14033dbb1  jz      short loc_14033DBB8
0x14033dbb3  call    ?Release@CmsReferenced@@QEAAXXZ; CmsReferenced::Release(void)
0x14033dbb8  mov     rcx, [rbp+2B60h]
0x14033dbbf  test    rcx, rcx
0x14033dbc2  jz      short loc_14033DBC9
0x14033dbc4  call    MsReleaseTable
0x14033dbc9  mov     rcx, [rbp+2B98h]; this
0x14033dbd0  test    rcx, rcx
0x14033dbd3  jz      short loc_14033DBDA
0x14033dbd5  call    ?Release@CmsReferenced@@QEAAXXZ; CmsReferenced::Release(void)
0x14033dbda  mov     rcx, [rbp+2B90h]
0x14033dbe1  test    rcx, rcx
0x14033dbe4  jz      short loc_14033DBEB
0x14033dbe6  call    MsReleaseTable
0x14033dbeb  mov     rcx, [rbp+2BC0h]
0x14033dbf2  test    rcx, rcx
0x14033dbf5  jz      short loc_14033DBFC
0x14033dbf7  call    MsReleaseTable
0x14033dbfc  mov     rbx, [rbp+0C8h]
0x14033dc03  test    rbx, rbx
0x14033dc06  jz      short loc_14033DC3A
0x14033dc08  mov     rbx, [rbx+30h]
0x14033dc0c  mov     r9d, 1
0x14033dc12  mov     rdx, rbx
0x14033dc15  xor     r8d, r8d
0x14033dc18  mov     rcx, r15
0x14033dc1b  call    ?RefsAcquireExclusiveFcb@@YAEPEAU_IRP_CONTEXT@@PEAU_FCB@@PEAU_SCB@@W4_REFS_ACQUIRE_FLAGS@@@Z; RefsAcquireExclusiveFcb(_IRP_CONTEXT *,_FCB *,_SCB *,_REFS_ACQUIRE_FLAGS)
0x14033dc20  mov     rdx, [rbp+0C8h]
0x14033dc27  xor     r8d, r8d
0x14033dc2a  call    ?RefsDeleteLcb@@YAXPEAU_IRP_CONTEXT@@PEAU_LCB@@W4LockParentScb@@@Z; RefsDeleteLcb(_IRP_CONTEXT *,_LCB *,LockParentScb)
0x14033dc2f  mov     rdx, rbx; struct _FCB *
0x14033dc32  mov     rcx, r15; struct _IRP_CONTEXT *
0x14033dc35  call    ?RefsReleaseFcb@@YAXPEAU_IRP_CONTEXT@@PEAU_FCB@@@Z; RefsReleaseFcb(_IRP_CONTEXT *,_FCB *)
0x14033dc3a  lea     rcx, [rsp+0A8h+var_88]
0x14033dc3f  mov     [rsp+0A8h+arg_10], r13
0x14033dc47  call    cs:__imp_ExInitializeFastOwnerEntry
0x14033dc4e  nop     dword ptr [rax+rax+00h]
0x14033dc53  mov     r8b, 1
0x14033dc56  lea     rdx, [rsp+0A8h+var_88]
0x14033dc5b  lea     rcx, [rbp+270h]
0x14033dc62  call    cs:__imp_ExAcquireFastResourceShared
0x14033dc69  nop     dword ptr [rax+rax+00h]
0x14033dc6e  lea     rdx, [rsp+0A8h+arg_10]; void **
0x14033dc76  mov     rcx, rbp; struct _VCB *
0x14033dc79  call    ?RefsGetNextFcbTableEntry@@YAPEAU_FCB@@PEAU_VCB@@PEAPEAX@Z; RefsGetNextFcbTableEntry(_VCB *,void * *)
0x14033dc7e  lea     rcx, [rbp+270h]
0x14033dc85  mov     [rsp+0A8h+arg_10], rax
0x14033dc8d  lea     rdx, [rsp+0A8h+var_88]
0x14033dc92  mov     rsi, rax
0x14033dc95  call    cs:__imp_ExReleaseFastResource
0x14033dc9c  nop     dword ptr [rax+rax+00h]
0x14033dca1  test    rsi, rsi
0x14033dca4  jz      loc_14033DED0
0x14033dcaa  mov     [rsp+0A8h+arg_18], r12
0x14033dcb2  mov     ebx, 803h
0x14033dcb7  nop     word ptr [rax+rax+00000000h]
0x14033dcc0  mov     r9d, 1
0x14033dcc6  xor     r8d, r8d
0x14033dcc9  mov     rdx, rsi
0x14033dccc  mov     rcx, r15
0x14033dccf  call    ?RefsAcquireExclusiveFcb@@YAEPEAU_IRP_CONTEXT@@PEAU_FCB@@PEAU_SCB@@W4_REFS_ACQUIRE_FLAGS@@@Z; RefsAcquireExclusiveFcb(_IRP_CONTEXT *,_FCB *,_SCB *,_REFS_ACQUIRE_FLAGS)
0x14033dcd4  lea     rbp, [rsi+30h]
0x14033dcd8  nop     dword ptr [rax+rax+00000000h]
0x14033dce0  mov     r14, [rbp+0]
0x14033dce4  cmp     r14, rbp
0x14033dce7  jz      loc_14033DDB8
0x14033dced  add     r14, 0FFFFFFFFFFFFFF88h
0x14033dcf1  jz      loc_14033DDB8
0x14033dcf7  movzx   eax, word ptr [r14]
0x14033dcfb  sub     ax, bx
0x14033dcfe  cmp     ax, 1
0x14033dd02  ja      loc_14033DDA8
0x14033dd08  mov     rbx, [r14+30h]
0x14033dd0c  call    cs:__imp_KeEnterGuardedRegion
0x14033dd13  nop     dword ptr [rax+rax+00h]
0x14033dd18  mov     rcx, rbx; FastMutex
0x14033dd1b  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14033dd22  nop     dword ptr [rax+rax+00h]
0x14033dd27  lock inc dword ptr [r14+0ACh]
0x14033dd2f  lea     rsi, [r14+178h]
0x14033dd36  mov     rax, [rsi]
0x14033dd39  cmp     rax, rsi
0x14033dd3c  jz      short loc_14033DD77
0x14033dd3e  lea     rdi, [rax-8]
0x14033dd42  test    rdi, rdi
0x14033dd45  jz      short loc_14033DD77
0x14033dd47  mov     rbx, [rdi+30h]
0x14033dd4b  mov     r9d, 1
0x14033dd51  mov     rdx, rbx
0x14033dd54  xor     r8d, r8d
0x14033dd57  mov     rcx, r15
0x14033dd5a  call    ?RefsAcquireExclusiveFcb@@YAEPEAU_IRP_CONTEXT@@PEAU_FCB@@PEAU_SCB@@W4_REFS_ACQUIRE_FLAGS@@@Z; RefsAcquireExclusiveFcb(_IRP_CONTEXT *,_FCB *,_SCB *,_REFS_ACQUIRE_FLAGS)
0x14033dd5f  xor     r8d, r8d
0x14033dd62  mov     rdx, rdi
0x14033dd65  call    ?RefsDeleteLcb@@YAXPEAU_IRP_CONTEXT@@PEAU_LCB@@W4LockParentScb@@@Z; RefsDeleteLcb(_IRP_CONTEXT *,_LCB *,LockParentScb)
0x14033dd6a  mov     rdx, rbx; struct _FCB *
0x14033dd6d  mov     rcx, r15; struct _IRP_CONTEXT *
0x14033dd70  call    ?RefsReleaseFcb@@YAXPEAU_IRP_CONTEXT@@PEAU_FCB@@@Z; RefsReleaseFcb(_IRP_CONTEXT *,_FCB *)
0x14033dd75  jmp     short loc_14033DD36
0x14033dd77  mov     eax, [r14+0ACh]
0x14033dd7e  inc     eax
0x14033dd80  mov     [r14+0ACh], eax
0x14033dd87  mov     rcx, [r14+30h]; FastMutex
0x14033dd8b  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14033dd92  nop     dword ptr [rax+rax+00h]
0x14033dd97  call    cs:__imp_KeLeaveGuardedRegion
0x14033dd9e  nop     dword ptr [rax+rax+00h]
0x14033dda3  mov     ebx, 803h
0x14033dda8  mov     rdx, r14; struct _SCB *
0x14033ddab  mov     rcx, r15; struct _IRP_CONTEXT *
0x14033ddae  call    RefsDeleteScb
0x14033ddb3  jmp     loc_14033DCE0
0x14033ddb8  mov     rsi, [rsp+0A8h+arg_10]
0x14033ddc0  mov     rbp, [rsp+0A8h+arg_8]
0x14033ddc8  lea     rdi, [rsi+20h]
0x14033ddcc  nop     dword ptr [rax+00h]
0x14033ddd0  mov     rbx, [rdi]
0x14033ddd3  cmp     rbx, rdi
0x14033ddd6  jz      short loc_14033DE07
0x14033ddd8  add     rbx, 0FFFFFFFFFFFFFFE0h
0x14033dddc  jz      short loc_14033DE07
0x14033ddde  mov     rdx, [rbx+18h]
0x14033dde2  mov     r9d, 1
0x14033dde8  xor     r8d, r8d
0x14033ddeb  mov     rcx, r15
0x14033ddee  mov     rdx, [rdx+88h]
0x14033ddf5  call    ?RefsAcquireExclusiveFcb@@YAEPEAU_IRP_CONTEXT@@PEAU_FCB@@PEAU_SCB@@W4_REFS_ACQUIRE_FLAGS@@@Z; RefsAcquireExclusiveFcb(_IRP_CONTEXT *,_FCB *,_SCB *,_REFS_ACQUIRE_FLAGS)
0x14033ddfa  mov     r8b, 1
0x14033ddfd  mov     rdx, rbx
0x14033de00  call    ?RefsDeleteLcb@@YAXPEAU_IRP_CONTEXT@@PEAU_LCB@@W4LockParentScb@@@Z; RefsDeleteLcb(_IRP_CONTEXT *,_LCB *,LockParentScb)
0x14033de05  jmp     short loc_14033DDD0
0x14033de07  mov     r8b, 1
0x14033de0a  lea     rcx, [rbp+270h]
0x14033de11  xor     edx, edx
0x14033de13  call    cs:__imp_ExAcquireFastResourceExclusive
0x14033de1a  nop     dword ptr [rax+rax+00h]
0x14033de1f  lea     rax, [rsp+0A8h+arg_0]
0x14033de27  mov     [rsp+0A8h+arg_0], 0
0x14033de2f  lea     r8, [rsp+0A8h+arg_10]; unsigned __int8 *
0x14033de37  mov     [rsi+0F8h], rax
0x14033de3e  mov     rdx, rsi; struct _FCB *
0x14033de41  mov     rcx, r15; struct _IRP_CONTEXT *
0x14033de44  call    ?RefsDeleteFcb@@YAXPEAU_IRP_CONTEXT@@PEAU_FCB@@PEAE@Z; RefsDeleteFcb(_IRP_CONTEXT *,_FCB *,uchar *)
0x14033de49  xor     r13d, r13d
0x14033de4c  lea     rcx, [rsp+0A8h+var_88]
0x14033de51  mov     [rsp+0A8h+arg_10], r13
0x14033de59  call    cs:__imp_ExInitializeFastOwnerEntry
0x14033de60  nop     dword ptr [rax+rax+00h]
0x14033de65  mov     r8b, 1
0x14033de68  lea     rdx, [rsp+0A8h+var_88]
0x14033de6d  lea     rcx, [rbp+270h]
0x14033de74  call    cs:__imp_ExAcquireFastResourceShared
0x14033de7b  nop     dword ptr [rax+rax+00h]
0x14033de80  lea     rdx, [rsp+0A8h+arg_10]; void **
0x14033de88  mov     rcx, rbp; struct _VCB *
0x14033de8b  call    ?RefsGetNextFcbTableEntry@@YAPEAU_FCB@@PEAU_VCB@@PEAPEAX@Z; RefsGetNextFcbTableEntry(_VCB *,void * *)
0x14033de90  lea     rcx, [rbp+270h]
0x14033de97  mov     [rsp+0A8h+arg_10], rax
0x14033de9f  lea     rdx, [rsp+0A8h+var_88]
0x14033dea4  mov     rsi, rax
0x14033dea7  call    cs:__imp_ExReleaseFastResource
0x14033deae  nop     dword ptr [rax+rax+00h]
0x14033deb3  mov     ebx, 803h
0x14033deb8  test    rsi, rsi
0x14033debb  jnz     loc_14033DCC0
  ... truncated ...
```
