# RefsOpenAttribute

- ea: `0x140304dc0`
- end: `0x140306041`
- name: `RefsOpenAttribute`
- size: `4737`
- prototype: ``
- caller_count: `5`
- callee_count: `20`
- tags: `authz_impersonation, service_task, installer_update`

## callers

- `0x140291760`
- `0x1402949ec`
- `0x140306050`
- `0x140308620`
- `0x140331170`

## callees

- `0x1400548b0`
- `0x140079d90`
- `0x140081670`
- `0x14008dbd0`
- `0x14008e1e0`
- `0x140092200`
- `0x140098120`
- `0x140099960`
- `0x1400a10e0`
- `0x1400a7a10`
- `0x1400ca788`
- `0x1400e2980`
- `0x1400e2c04`
- `0x1401ea140`
- `0x1402fec90`
- `0x1403047c0`
- `0x140304dc0`
- `0x140306630`
- `0x1403084d0`
- `0x1403321d8`

## import_xrefs

- `ntoskrnl!MmCanFileBeTruncated` at `0x1403053e6`
- `ntoskrnl!MmCanFileBeTruncated` at `0x1403053e6`
- `ntoskrnl!IoSetLinkShareAccess` at `0x140304f93`
- `ntoskrnl!IoSetLinkShareAccess` at `0x140304f93`
- `ntoskrnl!IoUpdateLinkShareAccessEx` at `0x140305557`
- `ntoskrnl!IoUpdateLinkShareAccessEx` at `0x140305557`
- `ntoskrnl!MmDoesFileHaveUserWritableReferences` at `0x1403056c6`
- `ntoskrnl!MmDoesFileHaveUserWritableReferences` at `0x140305afd`
- `ntoskrnl!MmDoesFileHaveUserWritableReferences` at `0x1403056c6`
- `ntoskrnl!MmDoesFileHaveUserWritableReferences` at `0x140305afd`
- `ntoskrnl!FsRtlOplockFsctrl` at `0x140305fd7`
- `ntoskrnl!FsRtlOplockFsctrl` at `0x14030601a`
- `ntoskrnl!FsRtlOplockFsctrl` at `0x140305fd7`
- `ntoskrnl!FsRtlOplockFsctrl` at `0x14030601a`
- `ntoskrnl!IoRemoveShareAccess` at `0x14033f312`
- `ntoskrnl!IoRemoveShareAccess` at `0x14033f312`
- `ntoskrnl!KeEnterGuardedRegion` at `0x14030505f`
- `ntoskrnl!KeEnterGuardedRegion` at `0x14030505f`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140304ffb`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1403055b0`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140304ffb`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1403055b0`
- `ntoskrnl!IoGetTransactionParameterBlock` at `0x1403050b9`
- `ntoskrnl!IoGetTransactionParameterBlock` at `0x1403050b9`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14030506f`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14030506f`
- `ntoskrnl!FsRtlOplockIsFastIoPossible` at `0x140305859`
- `ntoskrnl!FsRtlOplockIsFastIoPossible` at `0x140305859`
- `ntoskrnl!FsRtlCheckOplockEx` at `0x1403052d6`
- `ntoskrnl!FsRtlCheckOplockEx` at `0x1403052d6`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140305137`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140305137`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140305143`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140305143`
- `ntoskrnl!ExReleasePushLockEx` at `0x140305e6f`
- `ntoskrnl!ExReleasePushLockEx` at `0x140305eb7`
- `ntoskrnl!ExReleasePushLockEx` at `0x140305e6f`
- `ntoskrnl!ExReleasePushLockEx` at `0x140305eb7`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140305f01`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140305f01`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140305dff`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140305dff`

## string_xrefs

- `0x140305498`: `Create.c`
- `0x140305914`: `Create.c`
- `0x140305994`: `Create.c`
- `0x140305a12`: `Create.c`
- `0x140305aad`: `Create.c`
- `0x140305b68`: `Create.c`
- `0x140305c15`: `Create.c`
- `0x140305cc3`: `Create.c`
- `0x140305d26`: `Create.c`

## pseudocode

```c
__int64 __fastcall RefsOpenAttribute(
        struct _IRP **a1,
        __int64 a2,
        __int64 a3,
        struct _LCB *a4,
        __int64 a5,
        struct _FCB *a6,
        __int16 a7,
        __int64 a8,
        unsigned __int16 a9,
        int a10,
        char a11,
        int a12,
        int a13,
        __int64 a14,
        struct _SCB **a15,
        _QWORD *a16)
{
  struct _IRP **v16; // r13
  struct _IRP **v18; // r10
  unsigned int v19; // ebx
  char v20; // r12
  unsigned int v21; // r11d
  __int64 Scb; // rdx
  unsigned __int16 v23; // si
  int v24; // r8d
  __int64 v25; // rbx
  int v26; // ecx
  unsigned __int8 v27; // al
  unsigned int v28; // edx
  struct _SCB *v29; // r9
  char v30; // r12
  int v31; // eax
  unsigned int v32; // r10d
  unsigned int v33; // r11d
  char *v34; // rcx
  __int64 v35; // rbx
  bool v36; // cl
  PERESOURCE Resource; // rax
  char *PoolWithTag; // rsi
  PMRX_NET_ROOT pNetRoot; // rbx
  struct _SCB **v40; // rdx
  PTXN_PARAMETER_BLOCK TransactionParameterBlock; // rax
  __int64 v42; // rax
  _QWORD *v43; // rdx
  __int64 *v44; // r11
  __int64 v45; // r9
  struct _SCB *v46; // rdx
  __int64 v47; // r8
  struct _SCB *v48; // r9
  __int16 v49; // cx
  __int16 v50; // ax
  struct _SCB *v51; // rcx
  __int64 v52; // rax
  unsigned int v53; // r8d
  int v54; // ecx
  int v55; // eax
  __int64 v56; // r10
  char *v57; // rcx
  __int16 v58; // ax
  __int16 v59; // ax
  char v60; // cl
  int v61; // r8d
  __int64 v62; // r9
  struct _SCB *v63; // rbx
  __int64 v64; // rsi
  __int64 v65; // rax
  unsigned __int8 v66; // dl
  __int16 v67; // ax
  struct _SCB *v68; // rcx
  bool IsTransactionActive; // r13
  struct _IRP_CONTEXT *v70; // rcx
  __int64 v71; // rbx
  int v72; // eax
  unsigned int v74; // [rsp+48h] [rbp-A0h]
  unsigned int v75; // [rsp+50h] [rbp-98h]
  __int64 v76; // [rsp+80h] [rbp-68h]
  struct _SCB *v77; // [rsp+A0h] [rbp-48h]

  v16 = (struct _IRP **)a4;
  v18 = a1;
  v19 = 0;
  v74 = 0;
  v20 = 0;
  v21 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a2 + 8) + 8LL) + 20LL);
  v75 = v21;
  Scb = (__int64)*a15;
  v23 = a9;
  if ( !*a15 )
  {
    Scb = RefsCreateScb(a1, a6, a9, a8, 0, 0);
    *a15 = (struct _SCB *)Scb;
    v21 = v75;
    v18 = a1;
  }
  v24 = *(_DWORD *)(Scb + 152);
  if ( (v24 & 2) != 0 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
    {
      v19 = -1073741738;
    }
    else
    {
      v19 = -1073741738;
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 181, WPP_7fd866a51baf3c9804583670ee7ed8f5_Traceguids, 3221225558LL);
    }
    if ( (_BYTE)RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741738, 0, "Create.c", 0x3D3Au);
  }
  else
  {
    if ( *(_DWORD *)(Scb + 344) && (*(_DWORD *)(*(_QWORD *)(a2 + 8) + 16LL) & 6) != 0 )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
      {
        v19 = -1073741790;
      }
      else
      {
        v19 = -1073741790;
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 182, WPP_7fd866a51baf3c9804583670ee7ed8f5_Traceguids, 3221225506LL);
      }
      if ( (_BYTE)RefsStatusDebugEnabled )
        RefsStatusDebug(-1073741790, 0, "Create.c", 0x3D46u);
      return v19;
    }
    if ( a14 )
      goto LABEL_66;
    if ( (*(_DWORD *)(a2 + 16) & 0x100000) != 0 )
    {
      if ( *(_WORD *)Scb != 2053 )
      {
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
        {
          v19 = -1073741811;
        }
        else
        {
          v19 = -1073741811;
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            183,
            WPP_7fd866a51baf3c9804583670ee7ed8f5_Traceguids,
            3221225485LL);
        }
        if ( (_BYTE)RefsStatusDebugEnabled )
          RefsStatusDebug(-1073741811, 0, "Create.c", 0x3D58u);
        return v19;
      }
      if ( *(_DWORD *)(Scb + 160)
        || (*(_DWORD *)(*(_QWORD *)(a2 + 8) + 16LL) & 0xFFFFFF7F) != 0
        || (v25 = a2 + 26, (*(_BYTE *)(a2 + 26) & 7) != 7) )
      {
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
        {
          v19 = -1073741598;
        }
        else
        {
          v19 = -1073741598;
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            184,
            WPP_7fd866a51baf3c9804583670ee7ed8f5_Traceguids,
            3221225698LL);
        }
        if ( (_BYTE)RefsStatusDebugEnabled )
          RefsStatusDebug(-1073741598, 0, "Create.c", 0x3D67u);
        return v19;
      }
    }
    else
    {
      v25 = a2 + 26;
    }
    v26 = a10;
    if ( a10 != 2 )
      goto LABEL_90;
    if ( (v21 & 0x10027) != 0
      && (*(_WORD *)v25 & 2) == 0
      && MmDoesFileHaveUserWritableReferences((PSECTION_OBJECT_POINTERS)(*(_QWORD *)(Scb + 248) + 8LL)) )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
      {
        v19 = -1073741757;
      }
      else
      {
        v19 = -1073741757;
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 185, WPP_7fd866a51baf3c9804583670ee7ed8f5_Traceguids, 3221225539LL);
      }
      if ( (_BYTE)RefsStatusDebugEnabled )
        RefsStatusDebug(-1073741757, 0, "Create.c", 0x3D8Du);
      return v19;
    }
    if ( (*(_BYTE *)v25 & 1) != 0 )
    {
      v27 = 0;
LABEL_12:
      if ( !v20 || v27 )
        v28 = 0;
      else
        v28 = 0x80000000;
      v29 = *a15;
      v30 = a11;
      if ( (*(_DWORD *)(a5 + 144) & 0x40) != 0 )
      {
        v31 = 1;
      }
      else if ( a11 == 4 )
      {
        v31 = 2;
      }
      else
      {
        v31 = 0;
      }
      v32 = *(unsigned __int16 *)v25;
      v33 = v75;
      v34 = 0;
      if ( v31 && (v31 & 1) != 0 && !v16 )
      {
        if ( !*((_WORD *)v29 + 112)
          && ((v67 = *((_WORD *)v29 + 108), v67 == 128) || !v67 && (*((_DWORD *)v29 + 38) & 0x10) != 0)
          || *((_WORD *)v29 + 108) == 160 )
        {
          v33 = v75 & 0xFFFEFFFF;
          v32 |= 4u;
        }
      }
      if ( v16 )
      {
        v34 = (char *)v16 + 108;
        if ( *((_WORD *)v29 + 112)
          || (v58 = *((_WORD *)v29 + 108), v58 != 128) && (v58 || (*((_DWORD *)v29 + 38) & 0x10) == 0) )
        {
          if ( *((_WORD *)v29 + 108) != 160 )
            v28 |= 0x80u;
        }
      }
      IoSetLinkShareAccess(v33, v32, *(_QWORD *)(a2 + 48), (char *)v29 + 188, v34, v28);
      while ( 1 )
      {
        if ( *(_BYTE *)(*(_QWORD *)(a2 + 48) + 75LL) )
        {
          v68 = *a15;
          if ( (*((_DWORD *)*a15 + 75) & 0x1000) == 0 && *(_WORD *)v68 == 2053 )
          {
            if ( *((_QWORD *)v68 + 47) )
            {
              IsTransactionActive = RefsIsTransactionActive((struct _IRP_CONTEXT *)a1);
              v19 = RefsBindMinstoreTransactionNoRaise(v70);
              if ( (v19 & 0x80000000) != 0 )
                return v19;
              v71 = a3 + 784;
              ExAcquirePushLockExclusiveEx(a3 + 784, 0);
              v72 = MsAddReservationForSparseWrite(
                      a1[3],
                      *((_QWORD *)*a15 + 54),
                      (__int64)(*(unsigned int *)(a3 + 544) + *((_QWORD *)*a15 + 47)) >> *(_BYTE *)(a3 + 552));
              v74 = v72;
              if ( !IsTransactionActive )
              {
                RefsCheckpointCurrentTransaction((struct _IRP_CONTEXT *)a1);
                v72 = v74;
              }
              if ( v72 < 0 )
              {
                ExReleasePushLockEx(v71, 0);
                return v74;
              }
              *(_QWORD *)(a3 + 256) += (__int64)(*(unsigned int *)(a3 + 544) + *((_QWORD *)*a15 + 47)) >> *(_BYTE *)(a3 + 552);
              ExReleasePushLockEx(v71, 0);
            }
            *((_DWORD *)*a15 + 75) |= 0x1000u;
          }
        }
        v35 = *(_QWORD *)(a2 + 48);
        v36 = v23 == 160 || (a13 & 0x20000) != 0;
        v77 = *a15;
        Resource = a6->Header.Resource;
        if ( v36 )
        {
          if ( ((unsigned __int16)Resource & 0x400) == 0
            || (PoolWithTag = (char *)&a6[1].1 + 144, *((_WORD *)&a6[1].1 + 72)) )
          {
            PoolWithTag = (char *)ExAllocateFromLookasideListEx(&RefsCcbLookasideList);
          }
          memset(PoolWithTag, 0, 0x1E8u);
          *(_DWORD *)PoolWithTag = 31983624;
        }
        else
        {
          if ( ((unsigned __int16)Resource & 0x200) == 0
            || (PoolWithTag = (char *)&a6[1].NumberOfBufferingStateChangeWaiters,
                LOWORD(a6[1].NumberOfBufferingStateChangeWaiters)) )
          {
            if ( ((unsigned __int8)Resource & 2) != 0 )
              PoolWithTag = (char *)ExAllocatePoolWithTag((POOL_TYPE)528, 0x88u, 0x63666552u);
            else
              PoolWithTag = (char *)ExAllocateFromLookasideListEx(&RefsCcbDataLookasideList);
          }
          memset(PoolWithTag, 0, 0x88u);
          *(_DWORD *)PoolWithTag = 8914953;
        }
        *((_DWORD *)PoolWithTag + 1) = a13;
        if ( _VCB::IsSystemVolume((_VCB *)a6->Header.FileContextSupportPointer) )
        {
          if ( (Feature_ReFS_Fake_TxF__private_featureState & 0x10) == 0 )
          {
            v76 = (unsigned int)Feature_ReFS_Fake_TxF__private_featureState | 1LL;
            wil_details_FeatureReporting_ReportUsageToService(Feature_ReFS_Fake_TxF__private_descriptor, v76, 3);
            wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath(
              v76,
              3,
              Feature_ReFS_Fake_TxF__private_descriptor);
          }
          TransactionParameterBlock = IoGetTransactionParameterBlock((PFILE_OBJECT)v35);
          if ( TransactionParameterBlock && TransactionParameterBlock->TransactionObject )
            *((_DWORD *)PoolWithTag + 2) |= 0x80000000;
        }
        *((_OWORD *)PoolWithTag + 1) = *(_OWORD *)(v35 + 88);
        *((_WORD *)PoolWithTag + 16) = a7;
        *((_QWORD *)PoolWithTag + 16) = v35;
        pNetRoot = a6->pNetRoot;
        KeEnterGuardedRegion();
        ExAcquireFastMutexUnsafe((PFAST_MUTEX)&pNetRoot->pSrvCall);
        v40 = (struct _SCB **)*((_QWORD *)v77 + 34);
        if ( *v40 != (struct _SCB *)((char *)v77 + 264) )
LABEL_33:
          __fastfail(3u);
        *((_QWORD *)PoolWithTag + 5) = (char *)v77 + 264;
        *((_QWORD *)PoolWithTag + 6) = v40;
        *v40 = (struct _SCB *)(PoolWithTag + 40);
        *((_QWORD *)v77 + 34) = PoolWithTag + 40;
        if ( a4 )
        {
          v42 = _LCB::LcbChildCcbsWritable(a4);
          v43 = *(_QWORD **)(v42 + 8);
          if ( *v43 != v42 )
            goto LABEL_33;
          *((_QWORD *)PoolWithTag + 7) = v42;
          *((_QWORD *)PoolWithTag + 8) = v43;
          *v43 = PoolWithTag + 56;
          *(_QWORD *)(v42 + 8) = PoolWithTag + 56;
          *((_QWORD *)PoolWithTag + 9) = a4;
        }
        ExReleaseFastMutexUnsafe((PFAST_MUTEX)&a6->pNetRoot->pSrvCall);
        KeLeaveGuardedRegion();
        *a16 = PoolWithTag;
        RefsIncrementCloseCounts(
          *a15,
          ((__int64)a6->spacer.Resource & 4) != 0,
          *(_WORD *)(*(_QWORD *)(a2 + 48) + 75LL) == 0);
        RefsIncrementCleanupCounts(*a15, a4, (*(_DWORD *)(*(_QWORD *)(a2 + 48) + 80LL) >> 3) & 1);
        v23 = 128;
        if ( (a13 & 0x20000) != 0 )
          *((_DWORD *)*a15 + 75) |= 0x80u;
        v45 = *v44;
        v46 = *a15;
        v47 = *(_QWORD *)(a2 + 48);
        *(_QWORD *)(v47 + 24) = *a15;
        *(_QWORD *)(v47 + 32) = v45;
        *(_QWORD *)(v47 + 16) = *(_QWORD *)(*((_QWORD *)v46 + 18) + 208LL);
        *(_QWORD *)(v47 + 40) = 0;
        if ( v30 == 4 )
          *(_DWORD *)(v47 + 80) |= 0x400000u;
        if ( v45 )
          *(_BYTE *)(v45 + 80) = v30;
        if ( v30 == 3 )
        {
          if ( (*(_DWORD *)(*((_QWORD *)v46 + 17) + 8LL) & 0x2000LL) != 0 )
            *((_WORD *)v46 + 128) |= 0x4000u;
        }
        else
        {
          *(_QWORD *)(v47 + 40) = *((_QWORD *)v46 + 31) + 8LL;
        }
        if ( (*((_DWORD *)v46 + 75) & 0x100) != 0 )
          *(_DWORD *)(v47 + 80) |= 0x8000u;
        if ( a12
          || (v75 & 7) == 0
          || (*((_DWORD *)*a15 + 38) & 0x20) == 0
          || (v50 = *((_WORD *)*a15 + 108), v25 = 176, v50 != 128) && v50 != 176
          || (*(_DWORD *)(*(_QWORD *)(a2 + 48) + 80LL) & 8) == 0
          || (v51 = *a15, *((_DWORD *)*a15 + 40) != *((_DWORD *)*a15 + 39))
          || *((__int16 *)v51 + 128) < 0
          || (v52 = *((_QWORD *)v51 + 31), !*(_QWORD *)(v52 + 8))
          || *(_QWORD *)(v52 + 24)
          || !MmCanFileBeTruncated((PSECTION_OBJECT_POINTERS)(v52 + 8), 0)
          || (*(_DWORD *)(*((_QWORD *)*a15 + 17) + 8LL) & 0x100LL) != 0 )
        {
          v16 = a1;
          goto LABEL_57;
        }
        v16 = a1;
        if ( !a6->Context || (*((_DWORD *)a1 + 1) & 0x10000) != 0 || (unsigned __int8)MsIsFastResourceHeldExclusive() )
          break;
        *((_DWORD *)a1 + 1) |= 0x10000u;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            189,
            WPP_7fd866a51baf3c9804583670ee7ed8f5_Traceguids,
            3221225688LL);
        }
        if ( (_BYTE)RefsStatusDebugEnabled )
          RefsStatusDebug(-1073741608, (struct _IRP_CONTEXT *)a1, "Create.c", 0x3E78u);
        RefsRaiseStatusInternal((struct _IRP_CONTEXT *)a1, -1073741608, v53);
LABEL_90:
        v54 = v26 - 1;
        if ( v54 )
        {
          if ( v54 == 2 )
            v25 = a2 + 26;
          if ( (v21 & 0x10027) != 0 && (*(_WORD *)v25 & 2) == 0 )
          {
            if ( MmDoesFileHaveUserWritableReferences((PSECTION_OBJECT_POINTERS)(*(_QWORD *)(Scb + 248) + 8LL)) )
            {
              if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
                || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
              {
                v19 = -1073741757;
              }
              else
              {
                v19 = -1073741757;
                WPP_SF_d(
                  WPP_GLOBAL_Control->AttachedDevice,
                  187,
                  WPP_7fd866a51baf3c9804583670ee7ed8f5_Traceguids,
                  3221225539LL);
              }
              if ( (_BYTE)RefsStatusDebugEnabled )
                RefsStatusDebug(-1073741757, 0, "Create.c", 0x3DCFu);
              return v19;
            }
            v21 = v75;
            v18 = a1;
          }
          if ( (*(_BYTE *)v25 & 1) != 0 )
            goto LABEL_131;
          v66 = RefsWriteCheck((struct _IRP_CONTEXT *)v18, a6, v18[9]);
          if ( !v66 && (*(_DWORD *)(*(_QWORD *)(a2 + 48) + 80LL) & 0x2000000) != 0 )
          {
            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
              || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
            {
              v19 = -1073741790;
            }
            else
            {
              v19 = -1073741790;
              WPP_SF_d(
                WPP_GLOBAL_Control->AttachedDevice,
                188,
                WPP_7fd866a51baf3c9804583670ee7ed8f5_Traceguids,
                3221225506LL);
            }
            if ( (_BYTE)RefsStatusDebugEnabled )
              RefsStatusDebug(-1073741790, 0, "Create.c", 0x3DE3u);
            return v19;
          }
          v21 = v75;
          v61 = -2147483647;
          if ( v66 )
LABEL_131:
            v61 = 1;
          if ( (*(_DWORD *)(a5 + 144) & 0x40) != 0 )
          {
            v62 = 1;
            v30 = a11;
          }
          else
          {
            v30 = a11;
            if ( a11 == 4 )
              v62 = 2;
            else
              v62 = 0;
          }
          v19 = RefsCheckShareAccess(v21, *(unsigned __int16 *)v25, *(_QWORD *)(a2 + 48), v62, *a15, v16, v61);
          v74 = v19;
          if ( (v19 & 0x80000000) != 0 )
            return v19;
        }
        else
        {
          v30 = a11;
          if ( (*(_DWORD *)(a5 + 144) & 0x40) != 0 )
          {
            v55 = 1;
          }
          else if ( a11 == 4 )
          {
            v55 = 2;
          }
          else
          {
            v55 = 0;
          }
          v56 = *(_QWORD *)(a2 + 48);
          v57 = 0;
          if ( v55 && (v55 & 1) != 0 && !v16 )
          {
            if ( !*(_WORD *)(Scb + 224) && ((v59 = *(_WORD *)(Scb + 216), v59 == 128) || !v59 && (v24 & 0x10) != 0)
              || *(_WORD *)(Scb + 216) == 160 )
            {
              *(_BYTE *)(v56 + 76) = 0;
              *(_BYTE *)(v56 + 79) = 1;
            }
          }
          if ( v16 )
            v57 = (char *)v16 + 108;
          IoUpdateLinkShareAccessEx(v56, Scb + 188, v57);
        }
      }
      RefsFlushAndPurgeScb((struct _IRP_CONTEXT *)a1, *a15);
LABEL_57:
      v48 = *a15;
      v49 = *((_WORD *)*a15 + 108);
      if ( (v49 != 128 && v49 != 176 || *(_WORD *)v48 != 2053 || *(struct _SCB **)(*((_QWORD *)v48 + 18) + 72LL) == v48)
        && (v49 != 160
         || *((_WORD *)v48 + 112) != 8
         || **((_QWORD **)v48 + 29) != *(_QWORD *)RefsFileNameIndex.Buffer
         || (unsigned __int16)(*(_WORD *)v48 - 2051) > 1u) )
      {
        goto LABEL_128;
      }
      v19 = FsRtlCheckOplockEx((POPLOCK)v48 + 11, v16[9], 2u, 0, 0, 0);
      if ( (*(_DWORD *)(a2 + 16) & 0x10000) == 0
        || (v19 = FsRtlOplockFsctrl((POPLOCK)*a15 + 11, v16[9], *((_DWORD *)*a15 + 40)),
            v74 = v19,
            (v19 & 0x80000000) != 0) )
      {
LABEL_64:
        if ( (*(_DWORD *)(a2 + 16) & 0x100000) != 0 )
          FsRtlOplockFsctrl((POPLOCK)*a15 + 11, v16[9], 1u);
LABEL_66:
        if ( (*((_DWORD *)&a6->1 + 38) & 0x100) != 0 )
        {
          *((_DWORD *)*a15 + 75) |= 0x100u;
          *(_DWORD *)(*(_QWORD *)(a2 + 48) + 80LL) |= 0x8000u;
        }
        return v19;
      }
      v63 = *a15;
      v64 = *((_QWORD *)*a15 + 18);
      if ( (*(_DWORD *)(v64 + 24) & 0x4000005) == 1
        && *(_WORD *)v63 == 2053
        && (*((_DWORD *)v63 + 75) & 0x40) == 0
        && *(char *)(*((_QWORD *)v63 + 17) + 8LL) >= 0 )
      {
        if ( (*((_DWORD *)v63 + 38) & 0x20) == 0 )
        {
LABEL_126:
          v60 = 2;
LABEL_127:
          *((_BYTE *)*a15 + 5) = v60;
LABEL_128:
          v19 = v74;
          goto LABEL_64;
        }
        if ( FsRtlOplockIsFastIoPossible((POPLOCK)v63 + 11) )
        {
          if ( *((__int16 *)v63 + 128) >= 0 )
          {
            v65 = *((_QWORD *)v63 + 48);
            if ( (!v65 || !*(_BYTE *)(v65 + 16))
              && (*(_DWORD *)(v64 + 24) & 0x2000000) == 0
              && (*(_BYTE *)(*((_QWORD *)v63 + 17) + 8LL) & 0x20) == 0 )
            {
              *((_BYTE *)*a15 + 5) = 1;
              v19 = v74;
              goto LABEL_64;
            }
          }
          goto LABEL_126;
        }
      }
      v60 = 0;
      goto LABEL_127;
    }
    v27 = RefsWriteCheck((struct _IRP_CONTEXT *)a1, a6, a1[9]);
    v20 = 1;
    if ( v27 || (*(_DWORD *)(*(_QWORD *)(a2 + 48) + 80LL) & 0x2000000) == 0 )
      goto LABEL_12;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
    {
      v19 = -1073741790;
    }
    else
    {
      v19 = -1073741790;
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 186, WPP_7fd866a51baf3c9804583670ee7ed8f5_Traceguids, 3221225506LL);
    }
    if ( (_BYTE)RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741790, 0, "Create.c", 0x3DA3u);
  }
  return v19;
}

```

## disassembly

```asm
0x140304dc0  mov     [rsp+arg_18], r9
0x140304dc5  mov     [rsp+arg_10], r8
0x140304dca  mov     [rsp+arg_8], rdx
0x140304dcf  mov     [rsp+arg_0], rcx
0x140304dd4  push    rbx
0x140304dd5  push    rsi
0x140304dd6  push    rdi
0x140304dd7  push    r12
0x140304dd9  push    r13
0x140304ddb  push    r14
0x140304ddd  push    r15
0x140304ddf  sub     rsp, 0B0h
0x140304de6  mov     r13, r9
0x140304de9  mov     rdi, rdx
0x140304dec  mov     r10, rcx
0x140304def  xor     ebx, ebx
0x140304df1  mov     [rsp+0E8h+var_A0], ebx
0x140304df5  mov     [rsp+0E8h+var_A8], bl
0x140304df9  xor     r12b, r12b
0x140304dfc  mov     rax, [rdx+8]
0x140304e00  mov     rdx, [rax+8]
0x140304e04  mov     r11d, [rdx+14h]
0x140304e08  mov     [rsp+0E8h+var_98], r11d
0x140304e0d  mov     r14, [rsp+0E8h+arg_70]
0x140304e15  mov     rdx, [r14]
0x140304e18  movzx   esi, [rsp+0E8h+arg_40]
0x140304e20  mov     r15, [rsp+0E8h+arg_28]
0x140304e28  test    rdx, rdx
0x140304e2b  jnz     short loc_140304E5D
0x140304e2d  mov     [rsp+0E8h+PostIrpRoutine], rdx
0x140304e32  mov     dword ptr [rsp+0E8h+CompletionRoutine], edx
0x140304e36  mov     r9, [rsp+0E8h+arg_38]
0x140304e3e  movzx   r8d, si
0x140304e42  mov     rdx, r15
0x140304e45  call    ?RefsCreateScb@@YAPEAU_SCB@@PEAU_IRP_CONTEXT@@PEAU_FCB@@W4_REFS_ATTRIBUTE_TYPE_CODE@@PEBU_UNICODE_STRING@@W4REFS_CREATE_SCB_INFLAGS@@PEAE@Z; RefsCreateScb(_IRP_CONTEXT *,_FCB *,_REFS_ATTRIBUTE_TYPE_CODE,_UNICODE_STRING const *,REFS_CREATE_SCB_INFLAGS,uchar *)
0x140304e4a  mov     rdx, rax
0x140304e4d  mov     [r14], rax
0x140304e50  mov     r11d, [rsp+0E8h+var_98]
0x140304e55  mov     r10, [rsp+0E8h+arg_0]
0x140304e5d  mov     r8d, [rdx+98h]
0x140304e64  mov     eax, r8d
0x140304e67  and     eax, 2
0x140304e6a  jnz     loc_1403058BD
0x140304e70  cmp     [rdx+158h], eax
0x140304e76  jnz     loc_14030592D
0x140304e7c  cmp     [rsp+0E8h+arg_68], 0
0x140304e85  jnz     loc_140305302
0x140304e8b  test    dword ptr [rdi+10h], 100000h
0x140304e92  jnz     loc_1403059AD
0x140304e98  lea     rbx, [rdi+1Ah]
0x140304e9c  mov     ecx, [rsp+0E8h+arg_48]
0x140304ea3  cmp     ecx, 2
0x140304ea6  jnz     loc_1403054B9
0x140304eac  test    r11d, 10027h
0x140304eb3  setnz   cl
0x140304eb6  mov     r8d, 1
0x140304ebc  movzx   eax, word ptr [rbx]
0x140304ebf  bt      ax, r8w
0x140304ec4  setnb   al
0x140304ec7  test    al, cl
0x140304ec9  jnz     loc_1403056BB
0x140304ecf  test    byte ptr [rbx], 1
0x140304ed2  jz      loc_140305CDC
0x140304ed8  xor     al, al
0x140304eda  test    r12b, r12b
0x140304edd  jnz     loc_140305D3F
0x140304ee3  xor     edx, edx
0x140304ee5  mov     r9, [r14]
0x140304ee8  mov     rax, [rsp+0E8h+arg_20]
0x140304ef0  mov     ecx, [rax+90h]
0x140304ef6  movzx   r12d, [rsp+0E8h+arg_50]
0x140304eff  test    cl, 40h
0x140304f02  jnz     loc_140305658
0x140304f08  cmp     r12b, 4
0x140304f0c  jnz     loc_140305D51
0x140304f12  mov     eax, 2
0x140304f17  mov     r8, [rdi+30h]
0x140304f1b  movzx   r10d, word ptr [rbx]
0x140304f1f  mov     [rsp+0E8h+var_70], edx
0x140304f23  mov     [rsp+0E8h+var_78], r10d
0x140304f28  mov     r11d, [rsp+0E8h+var_98]
0x140304f2d  mov     [rsp+0E8h+var_80], r11d
0x140304f32  xor     ecx, ecx
0x140304f34  mov     [rsp+0E8h+var_50], rcx
0x140304f3c  test    eax, eax
0x140304f3e  jnz     loc_14030566C
0x140304f44  mov     ebx, 0A0h
0x140304f49  test    r13, r13
0x140304f4c  jz      short loc_140304F7D
0x140304f4e  lea     rcx, [r13+6Ch]
0x140304f52  mov     [rsp+0E8h+var_50], rcx
0x140304f5a  mov     r13d, 80h
0x140304f60  cmp     word ptr [r9+0E0h], 0
0x140304f69  jz      loc_1403055C1
0x140304f6f  cmp     [r9+0D8h], bx
0x140304f77  jnz     loc_140305D8C
0x140304f7d  add     r9, 0BCh
0x140304f84  mov     dword ptr [rsp+0E8h+PostIrpRoutine], edx
0x140304f88  mov     [rsp+0E8h+CompletionRoutine], rcx
0x140304f8d  mov     edx, r10d
0x140304f90  mov     ecx, r11d
0x140304f93  call    cs:__imp_IoSetLinkShareAccess
0x140304f9a  nop     dword ptr [rax+rax+00h]
0x140304f9f  mov     edx, 0A0h
0x140304fa4  mov     [rsp+0E8h+var_A8], 1
0x140304fa9  mov     rax, [rdi+30h]
0x140304fad  cmp     byte ptr [rax+4Bh], 0
0x140304fb1  jnz     loc_140305D98
0x140304fb7  mov     rbx, [rdi+30h]
0x140304fbb  mov     [rsp+0E8h+var_60], rbx
0x140304fc3  mov     r13d, [rsp+0E8h+arg_60]
0x140304fcb  cmp     si, dx
0x140304fce  jnz     loc_140305EDA
0x140304fd4  mov     cl, 1
0x140304fd6  mov     rax, [r14]
0x140304fd9  mov     [rsp+0E8h+var_48], rax
0x140304fe1  mov     rax, [r15+8]
0x140304fe5  test    cl, cl
0x140304fe7  jz      loc_140305568
0x140304fed  bt      rax, 0Ah
0x140304ff2  jb      short loc_14030500C
0x140304ff4  lea     rcx, ?RefsCcbLookasideList@@3U_LOOKASIDE_LIST_EX@@A; Lookaside
0x140304ffb  call    cs:__imp_ExAllocateFromLookasideListEx
0x140305002  nop     dword ptr [rax+rax+00h]
0x140305007  mov     rsi, rax
0x14030500a  jmp     short loc_140305019
0x14030500c  lea     rsi, [r15+320h]
0x140305013  cmp     word ptr [rsi], 0
0x140305017  jnz     short loc_140304FF4
0x140305019  xor     edx, edx; Val
0x14030501b  mov     r8d, 1E8h; Size
0x140305021  mov     rcx, rsi; void *
0x140305024  call    memset
0x140305029  mov     dword ptr [rsi], 1E80808h
0x14030502f  mov     [rsi+4], r13d
0x140305033  mov     rcx, [r15+50h]; this
0x140305037  call    ?IsSystemVolume@_VCB@@QEBA_NXZ; _VCB::IsSystemVolume(void)
0x14030503c  test    al, al
0x14030503e  jnz     short loc_14030509A
0x140305040  movups  xmm0, xmmword ptr [rbx+58h]
0x140305044  movups  xmmword ptr [rsi+10h], xmm0
0x140305048  movzx   eax, [rsp+0E8h+arg_30]
0x140305050  mov     [rsi+20h], ax
0x140305054  mov     [rsi+80h], rbx
0x14030505b  mov     rbx, [r15+58h]
0x14030505f  call    cs:__imp_KeEnterGuardedRegion
0x140305066  nop     dword ptr [rax+rax+00h]
0x14030506b  lea     rcx, [rbx+8]; FastMutex
0x14030506f  call    cs:__imp_ExAcquireFastMutexUnsafe
0x140305076  nop     dword ptr [rax+rax+00h]
0x14030507b  mov     rcx, [rsp+0E8h+var_48]
0x140305083  add     rcx, 108h
0x14030508a  mov     rdx, [rcx+8]
0x14030508e  cmp     [rdx], rcx
0x140305091  jz      short loc_1403050E5
0x140305093  mov     ecx, 3
0x140305098  int     29h; Win8: RtlFailFast(ecx)
0x14030509a  mov     [rsp+0E8h+var_90], 0
0x1403050a3  mov     ecx, cs:Feature_ReFS_Fake_TxF__private_featureState
0x1403050a9  mov     dword ptr [rsp+0E8h+var_90], ecx
0x1403050ad  test    cl, 10h
0x1403050b0  jz      loc_140305F15
0x1403050b6  mov     rcx, rbx; FileObject
0x1403050b9  call    cs:__imp_IoGetTransactionParameterBlock
0x1403050c0  nop     dword ptr [rax+rax+00h]
0x1403050c5  test    rax, rax
0x1403050c8  jz      loc_140305040
0x1403050ce  cmp     qword ptr [rax+8], 0
0x1403050d3  jz      loc_140305040
0x1403050d9  or      dword ptr [rsi+8], 80000000h
0x1403050e0  jmp     loc_140305040
0x1403050e5  lea     rax, [rsi+28h]
0x1403050e9  mov     [rax], rcx
0x1403050ec  mov     [rax+8], rdx
0x1403050f0  mov     [rdx], rax
0x1403050f3  mov     [rcx+8], rax
0x1403050f7  mov     rbx, [rsp+0E8h+arg_18]
0x1403050ff  test    rbx, rbx
0x140305102  jz      short loc_14030512F
0x140305104  mov     rcx, rbx
0x140305107  call    ?LcbChildCcbsWritable@_LCB@@QEAAAEAU?$ListHead@U_CCB@@$0DI@@@XZ; _LCB::LcbChildCcbsWritable(void)
0x14030510c  mov     rdx, [rax+8]
0x140305110  cmp     [rdx], rax
0x140305113  jnz     loc_140305093
0x140305119  lea     rcx, [rsi+38h]
0x14030511d  mov     [rcx], rax
0x140305120  mov     [rcx+8], rdx
0x140305124  mov     [rdx], rcx
0x140305127  mov     [rax+8], rcx
0x14030512b  mov     [rsi+48h], rbx
0x14030512f  mov     rcx, [r15+58h]
0x140305133  add     rcx, 8; FastMutex
0x140305137  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14030513e  nop     dword ptr [rax+rax+00h]
0x140305143  call    cs:__imp_KeLeaveGuardedRegion
0x14030514a  nop     dword ptr [rax+rax+00h]
0x14030514f  mov     r11, [rsp+0E8h+arg_78]
0x140305157  mov     [r11], rsi
0x14030515a  mov     [rsp+0E8h+var_A8], 0
0x14030515f  mov     rax, [rdi+30h]
0x140305163  movzx   ecx, byte ptr [rax+4Bh]
0x140305167  movzx   eax, byte ptr [rax+4Ch]
0x14030516b  or      al, cl
0x14030516d  setz    r8b; unsigned __int8
0x140305171  movzx   edx, byte ptr [r15+8]
0x140305176  shr     dl, 2
0x140305179  and     dl, 1; unsigned __int8
0x14030517c  mov     rcx, [r14]; struct _SCB *
0x14030517f  call    ?RefsIncrementCloseCounts@@YAXAEAU_SCB@@EE@Z; RefsIncrementCloseCounts(_SCB &,uchar,uchar)
0x140305184  mov     r8, [rdi+30h]
0x140305188  mov     r8d, [r8+50h]
0x14030518c  shr     r8d, 3
0x140305190  and     r8d, 1; unsigned int
0x140305194  mov     rdx, rbx; struct _LCB *
0x140305197  mov     rcx, [r14]; struct _SCB *
0x14030519a  call    ?RefsIncrementCleanupCounts@@YAXAEAU_SCB@@PEAU_LCB@@K@Z; RefsIncrementCleanupCounts(_SCB &,_LCB *,ulong)
0x14030519f  mov     esi, 80h
0x1403051a4  bt      r13d, 11h
0x1403051a9  jb      loc_140305F6C
0x1403051af  mov     r9, [r11]
0x1403051b2  mov     rdx, [r14]
0x1403051b5  mov     r8, [rdi+30h]
0x1403051b9  mov     [r8+18h], rdx
0x1403051bd  mov     [r8+20h], r9
0x1403051c1  mov     rax, [rdx+90h]
0x1403051c8  mov     rcx, [rax+0D0h]
0x1403051cf  mov     [r8+10h], rcx
0x1403051d3  xor     r10d, r10d
0x1403051d6  mov     [r8+28h], r10
0x1403051da  cmp     r12b, 4
0x1403051de  jz      loc_14030536D
0x1403051e4  test    r9, r9
0x1403051e7  jz      short loc_1403051ED
0x1403051e9  mov     [r9+50h], r12b
0x1403051ed  cmp     r12b, 3
0x1403051f1  jnz     loc_140305359
0x1403051f7  mov     rax, [rdx+88h]
0x1403051fe  mov     ecx, [rax+8]
0x140305201  bt      rcx, 0Dh
0x140305206  jb      loc_140305F7A
0x14030520c  test    dword ptr [rdx+12Ch], 100h
0x140305216  jnz     loc_140305F8B
0x14030521c  cmp     [rsp+0E8h+arg_58], r10d
0x140305224  jnz     short loc_14030523E
0x140305226  test    byte ptr [rsp+0E8h+var_98], 7
0x14030522b  jz      short loc_14030523E
0x14030522d  mov     rcx, [r14]
0x140305230  mov     eax, [rcx+98h]
0x140305236  test    al, 20h
0x140305238  jnz     loc_14030537E
0x14030523e  mov     ebx, 0B0h
0x140305243  mov     r13, [rsp+0E8h+arg_0]
0x14030524b  mov     r9, [r14]
0x14030524e  movzx   ecx, word ptr [r9+0D8h]
0x140305256  cmp     cx, si
0x140305259  jz      loc_140305333
0x14030525f  cmp     cx, bx
0x140305262  jz      loc_140305333
0x140305268  mov     r12d, 805h
0x14030526e  mov     ebx, 0A0h
0x140305273  cmp     cx, bx
0x140305276  jnz     loc_140305732
0x14030527c  cmp     word ptr [r9+0E0h], 8
0x140305285  jnz     loc_140305732
0x14030528b  mov     rax, [r9+0E8h]
0x140305292  mov     rcx, cs:?RefsFileNameIndex@@3U_UNICODE_STRING@@B.Buffer; _UNICODE_STRING const RefsFileNameIndex ...
0x140305299  mov     rdx, [rax]
0x14030529c  cmp     rdx, [rcx]
0x14030529f  jnz     loc_140305732
0x1403052a5  mov     ecx, 803h
0x1403052aa  movzx   eax, word ptr [r9]
0x1403052ae  sub     ax, cx
0x1403052b1  cmp     ax, 1
0x1403052b5  ja      loc_140305732
0x1403052bb  lea     rcx, [r9+58h]; Oplock
0x1403052bf  mov     [rsp+0E8h+PostIrpRoutine], r10; PostIrpRoutine
0x1403052c4  mov     [rsp+0E8h+CompletionRoutine], r10; CompletionRoutine
0x1403052c9  xor     r9d, r9d; Context
0x1403052cc  mov     r8d, 2; Flags
0x1403052d2  mov     rdx, [r13+48h]; Irp
0x1403052d6  call    cs:__imp_FsRtlCheckOplockEx
0x1403052dd  nop     dword ptr [rax+rax+00h]
0x1403052e2  mov     ebx, eax
0x1403052e4  mov     [rsp+0E8h+var_A4], eax
0x1403052e8  test    dword ptr [rdi+10h], 10000h
0x1403052ef  jnz     loc_140305FC5
0x1403052f5  test    dword ptr [rdi+10h], 100000h
0x1403052fc  jnz     loc_140306009
0x140305302  test    dword ptr [r15+98h], 100h
0x14030530d  jz      loc_14030602B
0x140305313  mov     rax, [r14]
0x140305316  or      dword ptr [rax+12Ch], 100h
0x140305320  mov     rcx, [rdi+30h]
0x140305324  mov     eax, [rcx+50h]
0x140305327  bts     eax, 0Fh
0x14030532b  mov     [rcx+50h], eax
0x14030532e  jmp     loc_14030602B
0x140305333  mov     r12d, 805h
0x140305339  cmp     [r9], r12w
0x14030533d  jnz     loc_14030526E
  ... truncated ...
```
