# NtfsCommonFlushBuffers

- ea: `0x1401aae60`
- end: `0x1401abcea`
- name: `NtfsCommonFlushBuffers`
- size: `3722`
- prototype: `__int64 __fastcall(__int64, IRP *)`
- caller_count: `2`
- callee_count: `35`
- tags: `file_ops, reparse_path, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140015d10`
- `0x1401aadc0`

## callees

- `0x140007ea0`
- `0x1400082b0`
- `0x14000c1d0`
- `0x14000c290`
- `0x14000cb00`
- `0x14000d1e0`
- `0x14000d840`
- `0x1400113f0`
- `0x140012e70`
- `0x140020de0`
- `0x140021590`
- `0x14002b680`
- `0x1400596c0`
- `0x14012f39c`
- `0x14012f930`
- `0x140130550`
- `0x1401321c0`
- `0x14013af10`
- `0x14013c2d0`
- `0x140140380`
- `0x1401419ec`
- `0x140181b60`
- `0x1401aab20`
- `0x1401aae60`
- `0x1401abcf0`
- `0x1401ac080`
- `0x1401bff94`
- `0x1401c00e0`
- `0x1401d2c34`
- `0x140215680`
- `0x140218840`
- `0x14021d974`
- `0x14021db80`
- `0x140230888`
- `0x140232674`

## import_xrefs

- `ntoskrnl!CcUninitializeCacheMap` at `0x1401ab4a3`
- `ntoskrnl!CcUninitializeCacheMap` at `0x1401ab4a3`
- `ntoskrnl!KeBugCheckEx` at `0x1401abc9c`
- `ntoskrnl!KeBugCheckEx` at `0x1402adf48`
- `ntoskrnl!KeBugCheckEx` at `0x1401abc9c`
- `ntoskrnl!KeBugCheckEx` at `0x1402adf48`
- `ntoskrnl!PsGetThreadProcess` at `0x1401aafad`
- `ntoskrnl!PsGetThreadProcess` at `0x1401aafad`
- `ntoskrnl!PsUpdateDiskCounters` at `0x1401aafd1`
- `ntoskrnl!PsUpdateDiskCounters` at `0x1401aafd1`
- `ntoskrnl!IoIsSystemThread` at `0x1401aaf8a`
- `ntoskrnl!IoIsSystemThread` at `0x1401aaf8a`
- `ntoskrnl!IofCallDriver` at `0x1401ab972`
- `ntoskrnl!IofCallDriver` at `0x1402adeef`
- `ntoskrnl!IofCallDriver` at `0x1401ab972`
- `ntoskrnl!IofCallDriver` at `0x1402adeef`
- `ntoskrnl!KeGetCurrentIrql` at `0x1401ab954`
- `ntoskrnl!KeGetCurrentIrql` at `0x1401ab980`
- `ntoskrnl!KeGetCurrentIrql` at `0x1401abc69`
- `ntoskrnl!KeGetCurrentIrql` at `0x1402aded6`
- `ntoskrnl!KeGetCurrentIrql` at `0x1402adefd`
- `ntoskrnl!KeGetCurrentIrql` at `0x1402adf17`
- `ntoskrnl!KeGetCurrentIrql` at `0x1401ab954`
- `ntoskrnl!KeGetCurrentIrql` at `0x1401ab980`
- `ntoskrnl!KeGetCurrentIrql` at `0x1401abc69`
- `ntoskrnl!KeGetCurrentIrql` at `0x1402aded6`
- `ntoskrnl!KeGetCurrentIrql` at `0x1402adefd`
- `ntoskrnl!KeGetCurrentIrql` at `0x1402adf17`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401abc15`
- `ntoskrnl!RtlInitUnicodeString` at `0x1402add07`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401abc15`
- `ntoskrnl!RtlInitUnicodeString` at `0x1402add07`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1401ab8dd`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1402ade34`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1401ab8dd`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1402ade34`

## pseudocode

```c
__int64 __fastcall NtfsCommonFlushBuffers(__int64 a1, IRP *a2)
{
  ULONG_PTR v4; // rbx
  struct _IO_STACK_LOCATION *CurrentStackLocation; // r9
  struct _FILE_OBJECT *v6; // rax
  unsigned __int16 *FsContext; // r13
  _BYTE *FsContext2; // r8
  __int64 v9; // rdx
  int v10; // eax
  __int64 v11; // r12
  int v12; // r15d
  UCHAR MinorFunction; // cl
  int v14; // esi
  struct _KTHREAD *Thread; // rcx
  struct _KTHREAD *CurrentThread; // rcx
  PEPROCESS ThreadProcess; // rax
  int v18; // r15d
  __int64 v19; // r15
  __int64 v20; // rcx
  __int64 v21; // r8
  int v22; // eax
  __int64 v23; // rax
  PFILE_OBJECT v24; // r15
  char v25; // r15
  char v26; // r15
  __int64 v27; // r15
  int v28; // edx
  int v29; // edx
  int v30; // r15d
  int v31; // r15d
  int v32; // eax
  _BYTE *v33; // r15
  __int64 i; // rax
  __int64 v35; // rcx
  __int64 j; // rax
  NTSTATUS v37; // ecx
  __int64 v38; // rcx
  __int64 v39; // rax
  __int64 v40; // rcx
  __int64 v41; // rax
  int v42; // edx
  __int64 v43; // rax
  __int64 v44; // rax
  unsigned int v45; // r8d
  __int64 v46; // r8
  __int64 v47; // r15
  int v48; // r12d
  __int64 v49; // r13
  struct _IO_STACK_LOCATION *v50; // rax
  _DWORD *v51; // rax
  _DWORD *v52; // rdi
  __int64 v53; // r15
  struct _IO_STACK_LOCATION *v54; // rax
  int CurrentIrql; // edi
  unsigned int v56; // ebx
  int v58; // eax
  struct _IO_STACK_LOCATION *v59; // rcx
  unsigned int v60; // ebx
  unsigned int v61; // r8d
  __int64 k; // rax
  ULONG_PTR v63; // rbx
  KIRQL v64; // al
  int BugCheckParameter4; // [rsp+98h] [rbp-E8h]
  char v66; // [rsp+C8h] [rbp-B8h]
  char v67; // [rsp+C9h] [rbp-B7h]
  char v68; // [rsp+CAh] [rbp-B6h]
  char v69; // [rsp+CBh] [rbp-B5h]
  char v70; // [rsp+CCh] [rbp-B4h]
  NTSTATUS v71; // [rsp+D4h] [rbp-ACh]
  __int64 v72; // [rsp+D8h] [rbp-A8h]
  __int64 v73; // [rsp+E0h] [rbp-A0h]
  __int64 v74; // [rsp+E8h] [rbp-98h] BYREF
  _BYTE *v75; // [rsp+F0h] [rbp-90h]
  int v76; // [rsp+F8h] [rbp-88h]
  int v77; // [rsp+FCh] [rbp-84h]
  __int64 v78; // [rsp+100h] [rbp-80h]
  ULONG_PTR v79; // [rsp+108h] [rbp-78h] BYREF
  PFILE_OBJECT FileObject; // [rsp+110h] [rbp-70h]
  __int64 v81; // [rsp+118h] [rbp-68h]
  unsigned __int16 *v82; // [rsp+120h] [rbp-60h]
  struct _IO_STACK_LOCATION *v83; // [rsp+128h] [rbp-58h]
  struct _UNICODE_STRING DestinationString; // [rsp+130h] [rbp-50h] BYREF
  __int64 v86; // [rsp+198h] [rbp+18h] BYREF

  v74 = 0;
  v4 = 0;
  v79 = 0;
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  v72 = (__int64)CurrentStackLocation;
  v6 = CurrentStackLocation->FileObject;
  FileObject = v6;
  FsContext = (unsigned __int16 *)v6->FsContext;
  if ( FsContext )
  {
    FsContext2 = v6->FsContext2;
    v75 = FsContext2;
    v9 = *((_QWORD *)FsContext + 24);
    v73 = v9;
    v10 = *(_DWORD *)(v9 + 4);
    if ( (v10 & 1) == 0 && (!FsContext2 || FsContext2[88] != 4 || (v10 & 2) == 0) )
      NtfsRaiseStatusInternal(a1, -1073741202, 0, 0, 0);
    v78 = *((_QWORD *)FsContext + 24);
    v11 = *((_QWORD *)FsContext + 23);
    v81 = v11;
    if ( FsContext2 )
      v12 = (unsigned __int8)FsContext2[88];
    else
      v12 = 5;
  }
  else
  {
    v9 = 0;
    v73 = 0;
    v78 = 0;
    FsContext2 = 0;
    v75 = 0;
    v11 = 0;
    v81 = 0;
    v12 = 1;
  }
  if ( v12 == 1 )
  {
    v60 = -1073741811;
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(a1, 0xC000000D, 0x11031Eu);
    NtfsExtendedCompleteRequestInternal(a1, a2, -1073741811, a2 != 0, 0);
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(0, 0xC000000D, 0x11031Fu);
    return v60;
  }
  MinorFunction = CurrentStackLocation->MinorFunction;
  if ( MinorFunction != 1 && (*(_DWORD *)(v9 + 4) & 0x2000000) != 0 )
  {
    v60 = -1073741662;
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(0, 0xC00000A2, 0x11033Bu);
    if ( !NtfsStatusDebugFlags )
      goto LABEL_177;
    v61 = 1114940;
    goto LABEL_176;
  }
  if ( MinorFunction == 2
    && (v12 != 2 || (*(_DWORD *)(v11 + 4) & 0x20100) != 0 || (*((_DWORD *)FsContext2 + 1) & 0x10000) != 0) )
  {
    v60 = -1073741811;
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(0, 0xC000000D, 0x11035Au);
    if ( !NtfsStatusDebugFlags )
      goto LABEL_177;
    v61 = 1114971;
LABEL_176:
    NtfsStatusTraceAndDebugInternal(a1, v60, v61);
LABEL_177:
    NtfsExtendedCompleteRequestInternal(a1, a2, v60, a2 != 0, 0);
    return v60;
  }
  v83 = CurrentStackLocation;
  v69 = 0;
  v67 = 0;
  v66 = 0;
  v68 = 0;
  LOBYTE(v86) = 1;
  v70 = 0;
  v82 = FsContext;
  if ( v12 == 2 )
  {
    v58 = *(_DWORD *)(v11 + 4);
    if ( (v58 & 0x100) != 0 || (v58 & 0x20000) != 0 )
      v12 = 4;
  }
  v71 = 0;
  v14 = 0;
  if ( NtfsDiskAccountingEnabled )
  {
    Thread = a2->Tail.Overlay.Thread;
    if ( !Thread || IoIsSystemThread(Thread) )
      CurrentThread = KeGetCurrentThread();
    else
      CurrentThread = a2->Tail.Overlay.Thread;
    ThreadProcess = PsGetThreadProcess(CurrentThread);
    PsUpdateDiskCounters(ThreadProcess, 0, 0, 0, 0, 1);
  }
  v18 = v12 - 2;
  if ( !v18 )
  {
    *(_DWORD *)(a1 + 504) = 23;
    v19 = v73;
    NtfsAcquireSharedVcb(a1, v73, 1);
    v69 = 1;
    if ( (*(_DWORD *)(v73 + 4) & 1) == 0 )
    {
      v14 = -1073741202;
      if ( !NtfsStatusDebugFlags )
        goto LABEL_145;
      v45 = 1115046;
      goto LABEL_124;
    }
    v22 = *((_DWORD *)FsContext + 64);
    if ( (v22 & 0xFFFFF000) == 0 && v22 != 128 )
    {
      NtfsAcquireExclusiveFcb(a1, v11, (__int64)FsContext, 1);
      v67 = 1;
      goto LABEL_39;
    }
    v20 = v72;
    if ( *(_BYTE *)(v72 + 1) != 1 )
    {
      v23 = *((_QWORD *)FsContext + 36);
      if ( !*(_QWORD *)(v23 + 16)
        && !*(_QWORD *)(v23 + 24)
        && (*(_DWORD *)(a1 + 436) & 0x80008) == 0
        && (*((_DWORD *)FsContext + 50) & 8) == 0
        && !*((_BYTE *)FsContext + 460) )
      {
        if ( (*((_DWORD *)FsContext + 50) & 0x10) == 0
          || (v38 = *((_QWORD *)FsContext + 23), (v39 = *(_QWORD *)(v38 + 328)) != 0) && *(_QWORD *)(v39 + 24)
          || (*(_DWORD *)(v38 + 4) & 0x20020100) != 0x20000000 )
        {
          if ( (*((_DWORD *)v75 + 1) & 0x10000) == 0 && !*((_QWORD *)FsContext + 63) && !*((_QWORD *)FsContext + 66) )
          {
            if ( (LOBYTE(v21) = 1,
                  NtfsAcquirePagingResourceSharedStarveExclusive(a1, v11, v21),
                  v68 = 1,
                  v41 = *((_QWORD *)FsContext + 36),
                  *(_QWORD *)(v41 + 16))
              || *(_QWORD *)(v41 + 24)
              || (*((_DWORD *)FsContext + 50) & 8) != 0
              || *((_BYTE *)FsContext + 460)
              || (v42 = *(_DWORD *)(*((_QWORD *)FsContext + 23) + 4LL), (*((_DWORD *)FsContext + 50) & 0x10) != 0)
              && ((v40 = *((_QWORD *)FsContext + 23), (v43 = *(_QWORD *)(v40 + 328)) == 0) || !*(_QWORD *)(v43 + 24))
              && (v42 & 0x20100) == 0
              && ((v42 & 0x20000000) != 0 || (v42 & 0x10000000) == 0 && NtfsGetPurgeKernelEAState(v40))
              || (*((_DWORD *)v75 + 1) & 0x10000) != 0
              || *((_QWORD *)FsContext + 63) && *((int *)FsContext + 50) >= 0
              || *((_QWORD *)FsContext + 66) )
            {
              NtfsReleasePagingResourcePriv(v40, v11);
              v68 = 0;
            }
          }
        }
        v20 = v72;
      }
    }
    if ( v68 )
    {
      LOBYTE(v20) = 0;
    }
    else
    {
      if ( *(_BYTE *)(v20 + 1) != 1 && !*((_BYTE *)FsContext + 460) )
        NtfsPerformOptimisticFlush(a1, FsContext);
      LOBYTE(v21) = 1;
      if ( (unsigned __int8)NtfsAcquirePagingResourceExclusive(a1, v11, v21) )
      {
        v76 = 0;
        for ( i = 0; ; i = (unsigned int)(i + 1) )
        {
          v76 = i;
          if ( (unsigned int)i >= 2 )
            break;
          v20 = *(_QWORD *)(a1 + 8 * i + 48);
          if ( !v20 || v20 == v11 )
          {
            *(_QWORD *)(a1 + 8 * i + 48) = v11;
            break;
          }
        }
      }
      LOBYTE(v20) = 1;
      v66 = 1;
    }
    if ( (*((_DWORD *)FsContext + 128) & 0x1000000) == 0 )
    {
      if ( *(_BYTE *)(v72 + 1) == 1 )
      {
        NtfsAcquireExclusiveScbEx(a1, (__int64)FsContext, 0);
        v67 = 1;
        v37 = NtfsFlushAndPurgeScb(a1, FsContext);
        v71 = v37;
        if ( v37 && v37 != 277 )
        {
          a2->IoStatus.Status = v37;
          v71 = 0;
        }
        v24 = FileObject;
        CcUninitializeCacheMap(FileObject, 0, 0);
      }
      else
      {
        if ( (_BYTE)v20 )
        {
          LOBYTE(BugCheckParameter4) = 0;
          a2->IoStatus.Status = NtfsFlushUserStream(a1, FsContext, 0, 0, BugCheckParameter4);
        }
        else
        {
          a2->IoStatus.Status = 0;
        }
        NtfsNormalizeAndCleanupTransaction(a1, (NTSTATUS *)&a2->IoStatus.0);
        v24 = FileObject;
      }
      if ( !v67 )
      {
        NtfsAcquireExclusiveScbEx(a1, (__int64)FsContext, 0);
        v67 = 1;
      }
      if ( (*((_DWORD *)FsContext + 50) & 0x200) != 0 && v66 )
        NtfsWriteFileSizes(a1, (__int64)FsContext, 0, 1, 1, 1);
      NtfsUpdateScbFromFileObject((__int64)v24, (__int64)FsContext, 1);
      if ( *(_BYTE *)(v72 + 1) == 4 )
        v25 = (*(_DWORD *)(v11 + 184) & 0x5FFFFF8F) != 0 ? v86 : 0;
      else
        v25 = v86;
      if ( v25 && (*(_DWORD *)(v11 + 4) & 0x10) != 0 )
        NtfsUpdateStandardInformation(a1, v11, 0);
      if ( (*((_DWORD *)FsContext + 50) & 8) != 0 )
        v14 = NtfsFlushFcbFileRecords(a1, *((_QWORD *)FsContext + 23));
      if ( v25 )
      {
        if ( (*(_DWORD *)(v11 + 184) & 0xD00000FC) != 0 )
        {
          v86 = *((_QWORD *)v75 + 9);
          NtfsPrepareForUpdateDuplicate(a1, v11, &v86, &v74, 1, 0);
          v27 = v86;
          if ( !NtfsUpdateDuplicateInfo(a1, v11, v86, v74) )
          {
            if ( v74 )
            {
              v28 = *(_DWORD *)(v11 + 184);
              if ( (v28 & 0xD00000FC) != 0 && (*((_DWORD *)v75 + 1) & 8) == 0 )
              {
                v29 = (v28 & 0x40000000) != 0 ? *(_DWORD *)(v11 + 184) & 0x1F4 | 8 : *(_DWORD *)(v11 + 184) & 0x1FC;
                if ( v29 )
                  NtfsReportDirNotify(
                    a1,
                    v27,
                    *(_QWORD *)(v11 + 96),
                    (unsigned __int16 *)v75 + 8,
                    *((unsigned __int16 *)v75 + 16),
                    0,
                    v29,
                    3,
                    *(_QWORD *)(v74 + 184),
                    0);
              }
            }
            if ( *(_WORD *)(v11 + 190) <= 1u )
              *(_DWORD *)(v11 + 184) &= 0x2FFFFE03u;
            NtfsUpdateLcbDuplicateInfo(v11, v27);
          }
        }
      }
      v26 = v66;
      if ( v66 )
      {
        v33 = v75;
        if ( (*((_DWORD *)v75 + 1) & 0x10000) != 0 && v14 >= 0 )
        {
          NtfsCheckpointCurrentTransaction(a1);
          NtfsReleaseAllResources(a1);
          v66 = 0;
          v67 = 0;
          if ( !v74 )
          {
            v44 = *((_QWORD *)v33 + 9);
            if ( v44 )
              v74 = *(_QWORD *)(v44 + 24);
          }
          v14 = NtfsFlushBootCritical(a1);
        }
        v26 = v66;
      }
      if ( v14 >= 0 )
      {
        NtfsCleanupTransaction(a1, v14, 0);
        NtfsCheckpointCurrentTransaction(a1);
        if ( v26 )
        {
          NtfsReleasePagingResourcePriv(v35, v11);
          if ( a1 )
          {
            v77 = 0;
            for ( j = 0; ; j = (unsigned int)(j + 1) )
            {
              v77 = j;
              if ( (unsigned int)j >= 2 )
                break;
              if ( *(_QWORD *)(a1 + 8 * j + 48) == v11 )
                *(_QWORD *)(a1 + 8 * j + 48) = 0;
            }
          }
          v66 = 0;
        }
        else if ( v68 )
        {
          NtfsReleasePagingResourcePriv(v35, (__int64)FsContext);
          v68 = 0;
        }
        if ( v67 )
        {
          NtfsReleaseFcbEx(a1, *((_QWORD *)FsContext + 23), 0);
          v67 = 0;
        }
      }
      goto LABEL_38;
    }
    v14 = -1073741816;
    if ( NtfsStatusDebugFlags )
    {
      v45 = 1115207;
      goto LABEL_124;
    }
    goto LABEL_145;
  }
  v30 = v18 - 1;
  if ( v30 )
  {
    v31 = v30 - 1;
    if ( !v31 )
      goto LABEL_134;
    if ( v31 != 2 )
      goto LABEL_38;
  }
  v32 = FsContext ? *FsContext : 0;
  if ( v32 != 1796 )
  {
LABEL_38:
    v19 = v73;
    goto LABEL_39;
  }
LABEL_134:
  *(_DWORD *)(a1 + 504) = 22;
  v19 = v73;
  NtfsFspCloseInternal(0, v73, 1, 0, 0);
  LOBYTE(v46) = 1;
  NtfsAcquireExclusiveVcb(a1, v73, v46);
  v69 = 1;
  if ( (*(_DWORD *)(v73 + 4) & 1) != 0 )
  {
    NtfsFlushVolume(a1);
LABEL_39:
    NtfsCleanupTransaction(a1, v14, 0);
    if ( *(_BYTE *)(v72 + 1) != 2 )
    {
      LfsFlushToLsnWithoutDiskCacheFlush(*(_QWORD *)(v19 + 232), NtfsLargeMax, 0, &v79);
      v70 = 1;
      v4 = v79;
    }
    goto LABEL_145;
  }
  v14 = -1073741202;
  if ( NtfsStatusDebugFlags )
  {
    v45 = 1115535;
LABEL_124:
    NtfsStatusTraceAndDebugInternal(0, v14, v45);
  }
LABEL_145:
  if ( NtfsDebugDiskFlush )
  {
    DestinationString = 0;
    RtlInitUnicodeString(&DestinationString, L"<unavailable>");
  }
  if ( v69 )
    NtfsReleaseVcb(a1, v19);
  if ( v68 )
    NtfsReleasePagingResourcePriv(v20, (__int64)FsContext);
  if ( v66 )
  {
    NtfsReleasePagingResourcePriv(v20, v11);
    if ( a1 )
    {
      for ( k = 0; k != 2; ++k )
      {
        if ( *(_QWORD *)(a1 + 8 * k + 48) == v11 )
          *(_QWORD *)(a1 + 8 * k + 48) = 0;
      }
    }
  }
  if ( v67 )
    NtfsReleaseFcbEx(a1, *((_QWORD *)FsContext + 23), 0);
  if ( (unsigned __int8)(*(_BYTE *)(v72 + 1) - 2) <= 1u )
  {
    if ( *(_BYTE *)(v19 + 10496) )
      NtfsIoPerfCollectFlushData(v19, (__int64)a2, *(_QWORD *)(a1 + 512), *(_DWORD *)(a1 + 504), *(_QWORD *)(a1 + 496));
    if ( NtfsStatusDebugFlags
      && v14
      && v14 != 294
      && (unsigned int)(v14 - 298) > 1
      && (unsigned int)v14 < 0xFFFFFFED
      && v14 != -1073741608
      && v14 != -1073741802
      && v14 != -1073741807
      && (unsigned int)(v14 + 2147483643) > 1
      && v14 != 259 )
    {
      NtfsStatusTraceAndDebugInternal(a1, v14, 0x1106D6u);
    }
    NtfsExtendedCompleteRequestInternal(a1, a2, v14, a2 != 0, v14 >= 0);
  }
  else
  {
    v47 = *(_QWORD *)(a1 + 512);
    v48 = *(_DWORD *)(a1 + 504);
    v49 = *(_QWORD *)(a1 + 496);
    NtfsExtendedCompleteRequestInternal(a1, 0, 0, 1u, 1);
    v50 = a2->Tail.Overlay.CurrentStackLocation;
    *(_OWORD *)&v50[-1].MajorFunction = *(_OWORD *)v72;
    *(_OWORD *)&v50[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)(v72 + 16);
    *(_OWORD *)(&v50[-1].Parameters.SetQuota + 6) = *(_OWORD *)(v72 + 32);
    *(_OWORD *)&v50[-1].FileObject = *(_OWORD *)(v72 + 48);
    v50[-1].Context = *(PVOID *)(v72 + 64);
    v51 = ExAllocateFromLookasideListEx(&NtfsDiskFlushContextLookasideList);
    v52 = v51;
    if ( v51 )
    {
      memset(v51, 0, 0x58u);
      v52[8] = v71;
      *((_QWORD *)v52 + 10) = v47;
      *((_QWORD *)v52 + 8) = v49;
      v52[18] = v48;
      v53 = v73;
      if ( v70 )
      {
        _InterlockedAdd((volatile signed __int32 *)(v73 + 284), 1u);
        *((_QWORD *)v52 + 2) = v73;
        *((_QWORD *)v52 + 3) = v4;
      }
      v54 = a2->Tail.Overlay.CurrentStackLocation;
      v54[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)NtfsFlushCompletionRoutine;
      v54[-1].Context = v52;
      v54[-1].Control = -32;
    }
    else
    {
      v59 = a2->Tail.Overlay.CurrentStackLocation;
      v59[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)NtfsFlushCompletionRoutine;
      v59[-1].Context = (PVOID)v71;
      v59[-1].Control = -32;
      v53 = v73;
    }
    CurrentIrql = KeGetCurrentIrql();
    v56 = IofCallDriver(*(PDEVICE_OBJECT *)(v53 + 224), a2);
    if ( KeGetCurrentIrql() != CurrentIrql )
    {
      v63 = *(_QWORD *)(v53 + 224);
      v64 = KeGetCurrentIrql();
      KeBugCheckEx(0xC8u, (unsigned int)(CurrentIrql << 8) | ((unsigned __int64)v64 << 16) | 0x10, v63, 0, 0);
    }
    if ( v56 == -1073741808 )
      return (unsigned int)v14;
    return v56;
  }
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x1401aae60  mov     rax, rsp
0x1401aae63  mov     [rax+10h], rdx
0x1401aae67  mov     [rax+8], rcx
0x1401aae6b  push    rbx
0x1401aae6c  push    rsi
0x1401aae6d  push    rdi
0x1401aae6e  push    r12
0x1401aae70  push    r13
0x1401aae72  push    r14
0x1401aae74  push    r15
0x1401aae76  sub     rsp, 0D0h
0x1401aae7d  mov     rsi, rdx
0x1401aae80  mov     rdi, rcx
0x1401aae83  mov     [rsp+108h+var_98], 0
0x1401aae8c  xor     ebx, ebx
0x1401aae8e  mov     [rax-78h], rbx
0x1401aae92  mov     r9, [rdx+0B8h]
0x1401aae99  mov     [rsp+108h+var_A8], r9
0x1401aae9e  mov     rax, [r9+30h]
0x1401aaea2  mov     [rsp+108h+FileObject], rax
0x1401aaeaa  mov     r13, [rax+18h]
0x1401aaeae  lea     r14d, [rbx+1]
0x1401aaeb2  test    r13, r13
0x1401aaeb5  jz      loc_1401ABAB9
0x1401aaebb  mov     r8, [rax+20h]
0x1401aaebf  mov     [rsp+108h+var_90], r8
0x1401aaec4  mov     rdx, [r13+0C0h]
0x1401aaecb  mov     [rsp+108h+var_A0], rdx
0x1401aaed0  mov     eax, [rdx+4]
0x1401aaed3  test    r14b, al
0x1401aaed6  jz      loc_1401ABA8F
0x1401aaedc  mov     [rsp+108h+var_80], rdx
0x1401aaee4  mov     r12, [r13+0B8h]
0x1401aaeeb  mov     [rsp+108h+var_68], r12
0x1401aaef3  test    r8, r8
0x1401aaef6  jz      loc_1401ABA09
0x1401aaefc  movzx   r15d, byte ptr [r8+58h]
0x1401aaf01  cmp     r15d, r14d
0x1401aaf04  jz      loc_1401ABAE3
0x1401aaf0a  mov     cl, [r9+1]
0x1401aaf0e  cmp     cl, r14b
0x1401aaf11  jz      short loc_1401AAF20
0x1401aaf13  test    dword ptr [rdx+4], 2000000h
0x1401aaf1a  jnz     loc_1401ABB3E
0x1401aaf20  cmp     cl, 2
0x1401aaf23  jz      loc_1401ABA14
0x1401aaf29  mov     [rsp+108h+var_58], r9
0x1401aaf31  mov     [rsp+108h+var_B5], bl
0x1401aaf35  mov     [rsp+108h+var_B7], bl
0x1401aaf39  mov     [rsp+108h+var_B8], bl
0x1401aaf3d  mov     [rsp+108h+var_B6], bl
0x1401aaf41  mov     byte ptr [rsp+108h+arg_10], r14b
0x1401aaf49  mov     [rsp+108h+var_B4], bl
0x1401aaf4d  mov     [rsp+108h+var_60], r13
0x1401aaf55  cmp     r15d, 2
0x1401aaf59  jz      loc_1401AB9B8
0x1401aaf5f  mov     [rsp+108h+var_AC], ebx
0x1401aaf63  xor     esi, esi
0x1401aaf65  mov     [rsp+108h+var_B0], esi
0x1401aaf69  cmp     cs:NtfsDiskAccountingEnabled, sil
0x1401aaf70  jz      short loc_1401AAFDD
0x1401aaf72  mov     rax, [rsp+108h+Irp]
0x1401aaf7a  mov     rcx, [rax+98h]; Thread
0x1401aaf81  test    rcx, rcx
0x1401aaf84  jz      loc_1401AB459
0x1401aaf8a  call    cs:__imp_IoIsSystemThread
0x1401aaf91  nop     dword ptr [rax+rax+00h]
0x1401aaf96  test    al, al
0x1401aaf98  jnz     loc_1401AB459
0x1401aaf9e  mov     rax, [rsp+108h+Irp]
0x1401aafa6  mov     rcx, [rax+98h]; Thread
0x1401aafad  call    cs:__imp_PsGetThreadProcess
0x1401aafb4  nop     dword ptr [rax+rax+00h]
0x1401aafb9  mov     rcx, rax
0x1401aafbc  mov     dword ptr [rsp+108h+var_E0], r14d
0x1401aafc1  mov     dword ptr [rsp+108h+BugCheckParameter4], 0
0x1401aafc9  xor     r9d, r9d
0x1401aafcc  xor     r8d, r8d
0x1401aafcf  xor     edx, edx
0x1401aafd1  call    cs:__imp_PsUpdateDiskCounters
0x1401aafd8  nop     dword ptr [rax+rax+00h]
0x1401aafdd  sub     r15d, 2
0x1401aafe1  jnz     loc_1401AB299
0x1401aafe7  mov     dword ptr [rdi+1F8h], 17h
0x1401aaff1  mov     r8b, r14b
0x1401aaff4  mov     r15, [rsp+108h+var_A0]
0x1401aaff9  mov     rdx, r15
0x1401aaffc  mov     rcx, rdi
0x1401aafff  call    NtfsAcquireSharedVcb
0x1401ab004  mov     [rsp+108h+var_B5], r14b
0x1401ab009  mov     eax, [r15+4]
0x1401ab00d  test    r14b, al
0x1401ab010  jz      loc_1401AB703
0x1401ab016  mov     eax, [r13+100h]
0x1401ab01d  test    eax, 0FFFFF000h
0x1401ab022  jz      loc_1401AB2C6
0x1401ab028  mov     rcx, [rsp+108h+var_A8]
0x1401ab02d  cmp     [rcx+1], r14b
0x1401ab031  jz      short loc_1401AB046
0x1401ab033  mov     rax, [r13+120h]
0x1401ab03a  xor     edx, edx
0x1401ab03c  cmp     [rax+10h], rdx
0x1401ab040  jz      loc_1401AB4CF
0x1401ab046  cmp     [rsp+108h+var_B6], 0
0x1401ab04b  jz      loc_1401AB36C
0x1401ab051  mov     cl, [rsp+108h+var_B8]
0x1401ab055  test    dword ptr [r13+200h], 1000000h
0x1401ab060  jnz     loc_1401AB71A
0x1401ab066  mov     rax, [rsp+108h+var_A8]
0x1401ab06b  cmp     [rax+1], r14b
0x1401ab06f  jz      loc_1401AB467
0x1401ab075  mov     r15, [rsp+108h+Irp]
0x1401ab07d  test    cl, cl
0x1401ab07f  jz      loc_1401AB4C2
0x1401ab085  mov     byte ptr [rsp+108h+BugCheckParameter4], 0
0x1401ab08a  xor     r9d, r9d
0x1401ab08d  xor     r8d, r8d
0x1401ab090  mov     rdx, r13
0x1401ab093  mov     rcx, rdi
0x1401ab096  call    NtfsFlushUserStream
0x1401ab09b  mov     [r15+30h], eax
0x1401ab09f  lea     rdx, [r15+30h]
0x1401ab0a3  mov     rcx, rdi
0x1401ab0a6  call    NtfsNormalizeAndCleanupTransaction
0x1401ab0ab  mov     r15, [rsp+108h+FileObject]
0x1401ab0b3  cmp     [rsp+108h+var_B7], 0
0x1401ab0b8  jz      loc_1401AB2EC
0x1401ab0be  test    dword ptr [r13+0C8h], 200h
0x1401ab0c9  jnz     loc_1401AB324
0x1401ab0cf  mov     r8b, r14b
0x1401ab0d2  mov     rdx, r13
0x1401ab0d5  mov     rcx, r15
0x1401ab0d8  call    NtfsUpdateScbFromFileObject
0x1401ab0dd  mov     rax, [rsp+108h+var_A8]
0x1401ab0e2  cmp     byte ptr [rax+1], 4
0x1401ab0e6  jz      loc_1401AB7F5
0x1401ab0ec  mov     r15b, byte ptr [rsp+108h+arg_10]
0x1401ab0f4  test    r15b, r15b
0x1401ab0f7  jnz     loc_1401AB304
0x1401ab0fd  mov     eax, [r13+0C8h]
0x1401ab104  test    al, 8
0x1401ab106  jz      short loc_1401AB120
0x1401ab108  mov     r8d, r14d
0x1401ab10b  mov     rdx, [r13+0B8h]; int
0x1401ab112  mov     rcx, rdi; int
0x1401ab115  call    NtfsFlushFcbFileRecords
0x1401ab11a  mov     esi, eax
0x1401ab11c  mov     [rsp+108h+var_B0], eax
0x1401ab120  test    r15b, r15b
0x1401ab123  jnz     short loc_1401AB18C
0x1401ab125  mov     r15b, [rsp+108h+var_B8]
0x1401ab12a  test    r15b, r15b
0x1401ab12d  jnz     loc_1401AB34F
0x1401ab133  test    esi, esi
0x1401ab135  jns     loc_1401AB3D1
0x1401ab13b  mov     r15, [rsp+108h+var_A0]
0x1401ab140  xor     r8d, r8d
0x1401ab143  mov     edx, esi
0x1401ab145  mov     rcx, rdi
0x1401ab148  call    NtfsCleanupTransaction
0x1401ab14d  mov     rax, [rsp+108h+var_A8]
0x1401ab152  cmp     byte ptr [rax+1], 2
0x1401ab156  jz      loc_1401AB815
0x1401ab15c  lea     r9, [rsp+108h+var_78]
0x1401ab164  xor     r8d, r8d
0x1401ab167  mov     rdx, cs:NtfsLargeMax
0x1401ab16e  mov     rcx, [r15+0E8h]
0x1401ab175  call    LfsFlushToLsnWithoutDiskCacheFlush
0x1401ab17a  mov     [rsp+108h+var_B4], r14b
0x1401ab17f  mov     rbx, [rsp+108h+var_78]
0x1401ab187  jmp     loc_1401AB815
0x1401ab18c  test    dword ptr [r12+0B8h], 0D00000FCh
0x1401ab198  jz      short loc_1401AB125
0x1401ab19a  mov     rax, [rsp+108h+var_90]
0x1401ab19f  mov     rcx, [rax+48h]
0x1401ab1a3  mov     [rsp+108h+arg_10], rcx
0x1401ab1ab  mov     byte ptr [rsp+108h+var_E0], 0
0x1401ab1b0  mov     byte ptr [rsp+108h+BugCheckParameter4], r14b
0x1401ab1b5  lea     r9, [rsp+108h+var_98]
0x1401ab1ba  lea     r8, [rsp+108h+arg_10]
0x1401ab1c2  mov     rdx, r12
0x1401ab1c5  mov     rcx, rdi
0x1401ab1c8  call    NtfsPrepareForUpdateDuplicate
0x1401ab1cd  mov     r9, [rsp+108h+var_98]
0x1401ab1d2  mov     r15, [rsp+108h+arg_10]
0x1401ab1da  mov     r8, r15
0x1401ab1dd  mov     rdx, r12; int
0x1401ab1e0  mov     rcx, rdi; int
0x1401ab1e3  call    NtfsUpdateDuplicateInfo
0x1401ab1e8  test    al, al
0x1401ab1ea  jnz     loc_1401AB125
0x1401ab1f0  mov     r10, [rsp+108h+var_98]
0x1401ab1f5  test    r10, r10
0x1401ab1f8  jz      short loc_1401AB272
0x1401ab1fa  mov     edx, [r12+0B8h]
0x1401ab202  test    edx, 0D00000FCh
0x1401ab208  jz      short loc_1401AB272
0x1401ab20a  mov     r8, [rsp+108h+var_90]
0x1401ab20f  mov     eax, [r8+4]
0x1401ab213  test    al, 8
0x1401ab215  jnz     short loc_1401AB272
0x1401ab217  bt      edx, 1Eh
0x1401ab21b  jb      loc_1401AB4B4
0x1401ab221  and     edx, 1FCh
0x1401ab227  test    edx, edx
0x1401ab229  jz      short loc_1401AB272
0x1401ab22b  movzx   ecx, word ptr [r8+20h]
0x1401ab230  lea     r9, [r8+10h]
0x1401ab234  mov     [rsp+108h+var_C0], 0
0x1401ab23d  mov     rax, [r10+0B8h]
0x1401ab244  mov     [rsp+108h+var_C8], rax
0x1401ab249  mov     [rsp+108h+var_D0], 3
0x1401ab251  mov     [rsp+108h+var_D8], edx
0x1401ab255  mov     [rsp+108h+var_E0], 0
0x1401ab25e  mov     dword ptr [rsp+108h+BugCheckParameter4], ecx
0x1401ab262  mov     r8, [r12+60h]
0x1401ab267  mov     rdx, r15
0x1401ab26a  mov     rcx, rdi
0x1401ab26d  call    NtfsReportDirNotify
0x1401ab272  cmp     [r12+0BEh], r14w
0x1401ab27b  ja      short loc_1401AB289
0x1401ab27d  and     dword ptr [r12+0B8h], 2FFFFE03h
0x1401ab289  mov     rdx, r15
0x1401ab28c  mov     rcx, r12
0x1401ab28f  call    NtfsUpdateLcbDuplicateInfo
0x1401ab294  jmp     loc_1401AB125
0x1401ab299  sub     r15d, 1
0x1401ab29d  jz      short loc_1401AB2B3
0x1401ab29f  sub     r15d, 1
0x1401ab2a3  jz      loc_1401AB738
0x1401ab2a9  cmp     r15d, 2
0x1401ab2ad  jnz     loc_1401AB13B
0x1401ab2b3  test    r13, r13
0x1401ab2b6  jz      loc_1401AB72B
0x1401ab2bc  movzx   eax, word ptr [r13+0]
0x1401ab2c1  jmp     loc_1401AB72D
0x1401ab2c6  cmp     eax, 80h
0x1401ab2cb  jz      loc_1401AB028
0x1401ab2d1  mov     r9d, r14d
0x1401ab2d4  mov     r8, r13
0x1401ab2d7  mov     rdx, r12
0x1401ab2da  mov     rcx, rdi
0x1401ab2dd  call    NtfsAcquireExclusiveFcb
0x1401ab2e2  mov     [rsp+108h+var_B7], r14b
0x1401ab2e7  jmp     loc_1401AB140
0x1401ab2ec  xor     r8d, r8d
0x1401ab2ef  mov     rdx, r13
0x1401ab2f2  mov     rcx, rdi
0x1401ab2f5  call    NtfsAcquireExclusiveScbEx
0x1401ab2fa  mov     [rsp+108h+var_B7], r14b
0x1401ab2ff  jmp     loc_1401AB0BE
0x1401ab304  mov     eax, [r12+4]
0x1401ab309  test    al, 10h
0x1401ab30b  jz      loc_1401AB0FD
0x1401ab311  xor     r8d, r8d
0x1401ab314  mov     rdx, r12
0x1401ab317  mov     rcx, rdi
0x1401ab31a  call    NtfsUpdateStandardInformation
0x1401ab31f  jmp     loc_1401AB0FD
0x1401ab324  cmp     [rsp+108h+var_B8], 0
0x1401ab329  jz      loc_1401AB0CF
0x1401ab32f  mov     byte ptr [rsp+108h+var_E0], r14b
0x1401ab334  mov     byte ptr [rsp+108h+BugCheckParameter4], r14b
0x1401ab339  mov     r9b, r14b
0x1401ab33c  xor     r8d, r8d
0x1401ab33f  mov     rdx, r13
0x1401ab342  mov     rcx, rdi
0x1401ab345  call    NtfsWriteFileSizes
0x1401ab34a  jmp     loc_1401AB0CF
0x1401ab34f  mov     r15, [rsp+108h+var_90]
0x1401ab354  test    dword ptr [r15+4], 10000h
0x1401ab35c  jnz     loc_1401AB638
0x1401ab362  mov     r15b, [rsp+108h+var_B8]
0x1401ab367  jmp     loc_1401AB133
0x1401ab36c  cmp     [rcx+1], r14b
0x1401ab370  jz      short loc_1401AB387
0x1401ab372  cmp     byte ptr [r13+1CCh], 0
0x1401ab37a  jnz     short loc_1401AB387
0x1401ab37c  mov     rdx, r13
0x1401ab37f  mov     rcx, rdi
0x1401ab382  call    NtfsPerformOptimisticFlush
0x1401ab387  mov     r8b, r14b
0x1401ab38a  mov     rdx, r12
0x1401ab38d  mov     rcx, rdi
0x1401ab390  call    NtfsAcquirePagingResourceExclusive
0x1401ab395  test    al, al
0x1401ab397  jz      short loc_1401AB3C5
0x1401ab399  mov     [rsp+108h+var_88], 0
0x1401ab3a4  xor     eax, eax
0x1401ab3a6  mov     [rsp+108h+var_88], eax
0x1401ab3ad  cmp     eax, 2
0x1401ab3b0  jnb     short loc_1401AB3C5
0x1401ab3b2  mov     rcx, [rdi+rax*8+30h]
0x1401ab3b7  test    rcx, rcx
0x1401ab3ba  jnz     loc_1401AB6B1
0x1401ab3c0  mov     [rdi+rax*8+30h], r12
0x1401ab3c5  mov     cl, r14b
0x1401ab3c8  mov     [rsp+108h+var_B8], cl
0x1401ab3cc  jmp     loc_1401AB055
0x1401ab3d1  xor     r8d, r8d
  ... truncated ...
```
