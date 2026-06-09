# FatCommonCleanup

- ea: `0x140024bd4`
- end: `0x140025a87`
- name: `FatCommonCleanup`
- size: `3763`
- prototype: `__int64 __fastcall(PVOID Entry, PIRP Irp)`
- caller_count: `2`
- callee_count: `23`
- tags: `file_ops, reparse_path, installer_update, broker_com_uri`

## callers

- `0x140025a90`
- `0x1400438e0`

## callees

- `0x140001b50`
- `0x1400031ac`
- `0x140006350`
- `0x140023ad4`
- `0x14002486c`
- `0x140024b3c`
- `0x140024bd4`
- `0x140031468`
- `0x14003172c`
- `0x140031b84`
- `0x140033270`
- `0x140033e84`
- `0x140034054`
- `0x140038eb4`
- `0x14003d880`
- `0x14003e4b4`
- `0x14003e870`
- `0x14003ea88`
- `0x140044bac`
- `0x1400465f4`
- `0x1400466c8`
- `0x1400492a4`
- `0x14004a1d4`

## import_xrefs

- `ntoskrnl!CcFlushCache` at `0x1400257ad`
- `ntoskrnl!CcFlushCache` at `0x1400257ad`
- `ntoskrnl!CcPurgeCacheSection` at `0x1400257e8`
- `ntoskrnl!CcPurgeCacheSection` at `0x1400257e8`
- `ntoskrnl!CcUninitializeCacheMap` at `0x140025819`
- `ntoskrnl!CcUninitializeCacheMap` at `0x140025819`
- `ntoskrnl!FsRtlNormalizeNtstatus` at `0x140024cb9`
- `ntoskrnl!FsRtlNormalizeNtstatus` at `0x140024f63`
- `ntoskrnl!FsRtlNormalizeNtstatus` at `0x1400259d0`
- `ntoskrnl!FsRtlNormalizeNtstatus` at `0x140024cb9`
- `ntoskrnl!FsRtlNormalizeNtstatus` at `0x140024f63`
- `ntoskrnl!FsRtlNormalizeNtstatus` at `0x1400259d0`
- `ntoskrnl!FsRtlNotifyFullChangeDirectory` at `0x140024da8`
- `ntoskrnl!FsRtlNotifyFullChangeDirectory` at `0x140024da8`
- `ntoskrnl!FsRtlNotifyCleanup` at `0x140024e6a`
- `ntoskrnl!FsRtlNotifyCleanup` at `0x140024e6a`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x14005b7ff`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x14005b87f`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x14005b8a9`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x14005b8d3`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x14005b8fd`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x14005b7ff`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x14005b87f`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x14005b8a9`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x14005b8d3`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x14005b8fd`
- `ntoskrnl!FsRtlCheckOplockEx` at `0x140024f2f`
- `ntoskrnl!FsRtlCheckOplockEx` at `0x1400252d5`
- `ntoskrnl!FsRtlCheckOplockEx` at `0x140025749`
- `ntoskrnl!FsRtlCheckOplockEx` at `0x140024f2f`
- `ntoskrnl!FsRtlCheckOplockEx` at `0x1400252d5`
- `ntoskrnl!FsRtlCheckOplockEx` at `0x140025749`
- `ntoskrnl!FsRtlNotifyFullReportChange` at `0x140025253`
- `ntoskrnl!FsRtlNotifyFullReportChange` at `0x1400256bf`
- `ntoskrnl!FsRtlNotifyFullReportChange` at `0x140025253`
- `ntoskrnl!FsRtlNotifyFullReportChange` at `0x1400256bf`
- `ntoskrnl!FsRtlFastUnlockAll` at `0x140025394`
- `ntoskrnl!FsRtlFastUnlockAll` at `0x140025394`
- `ntoskrnl!IoGetRequestorProcess` at `0x140025376`
- `ntoskrnl!IoGetRequestorProcess` at `0x140025376`
- `ntoskrnl!IoRemoveShareAccess` at `0x140025835`
- `ntoskrnl!IoRemoveShareAccess` at `0x140025835`
- `ntoskrnl!FsRtlCheckOplock` at `0x140025867`
- `ntoskrnl!FsRtlCheckOplock` at `0x140025867`
- `ntoskrnl!FsRtlOplockIsFastIoPossible` at `0x140025889`
- `ntoskrnl!FsRtlOplockIsFastIoPossible` at `0x140025889`
- `ntoskrnl!FsRtlNotifyVolumeEvent` at `0x140025a36`
- `ntoskrnl!FsRtlNotifyVolumeEvent` at `0x14005b974`
- `ntoskrnl!FsRtlNotifyVolumeEvent` at `0x140025a36`
- `ntoskrnl!FsRtlNotifyVolumeEvent` at `0x14005b974`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400251b0`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140025484`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400257c0`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400251b0`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140025484`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400257c0`
- `ntoskrnl!ExReleaseResourceLite` at `0x140024de8`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400251c3`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400254a0`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400257d0`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400259f9`
- `ntoskrnl!ExReleaseResourceLite` at `0x140025a16`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005b83c`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005b85d`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005b937`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005b958`
- `ntoskrnl!ExReleaseResourceLite` at `0x140024de8`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400251c3`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400254a0`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400257d0`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400259f9`
- `ntoskrnl!ExReleaseResourceLite` at `0x140025a16`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005b83c`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005b85d`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005b937`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005b958`
- `ntoskrnl!KeBugCheckEx` at `0x140024fc7`
- `ntoskrnl!KeBugCheckEx` at `0x140024fc7`
- `ntoskrnl!CcSetFileSizes` at `0x140025571`
- `ntoskrnl!CcSetFileSizes` at `0x140025571`
- `ntoskrnl!ExRaiseStatus` at `0x140024cc7`
- `ntoskrnl!ExRaiseStatus` at `0x140024f71`
- `ntoskrnl!ExRaiseStatus` at `0x1400259de`
- `ntoskrnl!ExRaiseStatus` at `0x140024cc7`
- `ntoskrnl!ExRaiseStatus` at `0x140024f71`
- `ntoskrnl!ExRaiseStatus` at `0x1400259de`

## pseudocode

```c
__int64 __fastcall FatCommonCleanup(PVOID Entry, PIRP Irp)
{
  PFILE_OBJECT v4; // r14
  __int64 v5; // r8
  __int64 v6; // r9
  int v7; // r13d
  __int64 p_Flags; // rdx
  __int64 v9; // rcx
  NTSTATUS v10; // eax
  NTSTATUS v11; // eax
  char v12; // r14
  __int64 v13; // rbx
  _DWORD *v14; // r12
  bool v15; // zf
  __int64 v16; // r13
  __int64 v17; // r9
  __int64 v18; // r8
  __int64 v19; // r9
  int v20; // eax
  NTSTATUS v21; // eax
  NTSTATUS v22; // r14d
  NTSTATUS v23; // eax
  PFILE_OBJECT v24; // rcx
  struct _FILE_OBJECT *v25; // r14
  _DWORD *v26; // r14
  int v27; // eax
  int v28; // eax
  __int64 v29; // rcx
  __int64 v30; // r9
  _QWORD *p_DataSectionObject; // rax
  int v32; // eax
  _DWORD *v33; // r14
  int v34; // eax
  struct _KPROCESS *RequestorProcess; // rax
  __int64 v36; // rdx
  _DWORD *v37; // rcx
  unsigned int v38; // eax
  unsigned int v39; // ecx
  unsigned int v40; // r9d
  int v41; // eax
  PSECTION_OBJECT_POINTERS SectionObjectPointer; // rax
  __int64 v43; // rcx
  __int64 v44; // r8
  unsigned int *v45; // rax
  __int64 v46; // r9
  int v47; // eax
  SECTION_OBJECT_POINTERS *v48; // rcx
  union _LARGE_INTEGER *v49; // rdx
  char v50; // al
  __int64 v51; // rcx
  char v52; // al
  __int64 v53; // rcx
  __int64 v54; // rdx
  NTSTATUS v55; // eax
  char v57; // [rsp+50h] [rbp-C8h]
  char v58; // [rsp+51h] [rbp-C7h]
  PFILE_OBJECT FileObject; // [rsp+58h] [rbp-C0h]
  int v60; // [rsp+60h] [rbp-B8h]
  __int64 v61; // [rsp+68h] [rbp-B0h] BYREF
  int v62[2]; // [rsp+70h] [rbp-A8h] BYREF
  PVOID FsContext; // [rsp+78h] [rbp-A0h] BYREF
  PFILE_OBJECT v64; // [rsp+80h] [rbp-98h]
  PFILE_OBJECT v65; // [rsp+88h] [rbp-90h]
  _DWORD *v66; // [rsp+90h] [rbp-88h]
  _QWORD v67[2]; // [rsp+98h] [rbp-80h] BYREF
  PLARGE_INTEGER TruncateSize; // [rsp+A8h] [rbp-70h]
  PSHARE_ACCESS ShareAccess; // [rsp+B0h] [rbp-68h]
  __int64 v70; // [rsp+B8h] [rbp-60h] BYREF
  unsigned int *v71; // [rsp+C0h] [rbp-58h]
  _DWORD *v72; // [rsp+C8h] [rbp-50h]
  ULONG *v73; // [rsp+D0h] [rbp-48h]
  ULONG_PTR *p_Information; // [rsp+D8h] [rbp-40h]
  char v76; // [rsp+130h] [rbp+18h]
  char v77; // [rsp+138h] [rbp+20h]

  v61 = 0;
  *(_QWORD *)v62 = 0;
  FsContext = 0;
  v70 = 0;
  v4 = Irp->Tail.Overlay.CurrentStackLocation->FileObject;
  v64 = v4;
  v65 = v4;
  v7 = FatDecodeFileObject(v4, &v61, v62, &FsContext);
  v60 = v7;
  if ( v7 == 1 )
  {
LABEL_177:
    FatCompleteRequest_Real(Entry, Irp);
    return 0;
  }
  p_Flags = (__int64)&v4->Flags;
  if ( (v4->Flags & 0x4000) != 0 )
  {
    v9 = *(unsigned int *)(v61 + 200);
    if ( (v9 & 0x1000) != 0 && (v4->Flags & 0x1000) != 0 && (*(_DWORD *)(v61 + 200) & 0x4000) == 0 && v7 == 2 )
    {
      v10 = FatFlushFile(v9, *(_QWORD *)v62, 1);
      if ( v10 < 0 )
      {
        *((_DWORD *)Entry + 18) = v10;
        v11 = FsRtlNormalizeNtstatus(v10, -1073741591);
        ExRaiseStatus(v11);
      }
    }
    goto LABEL_177;
  }
  FileObject = v4;
  v73 = &v4->Flags;
  v58 = 0;
  TruncateSize = 0;
  v77 = 0;
  v12 = 0;
  v57 = 0;
  p_Information = &Irp->IoStatus.Information;
  Irp->IoStatus.Information = 2;
  v13 = *(_QWORD *)v62;
  if ( (unsigned int)(v7 - 2) > 1 )
  {
    v76 = 0;
    v16 = v61;
    v14 = FsContext;
  }
  else
  {
    FatAcquireExclusiveFcb(Entry, *(_QWORD *)v62, v5, v6);
    v76 = 1;
    v14 = FsContext;
    if ( (*((_DWORD *)FsContext + 1) & 0x400) != 0 )
    {
      *(_DWORD *)(v13 + 192) |= 1u;
      v14[1] &= ~0x400u;
      v12 = 1;
      v15 = v7 == 3;
      v16 = v61;
      if ( v15 )
        FsRtlNotifyFullChangeDirectory(
          *(PNOTIFY_SYNC *)(v61 + 816),
          (PLIST_ENTRY)(v61 + 800),
          v64->FsContext,
          0,
          0,
          0,
          0,
          0,
          0,
          0);
    }
    else
    {
      v16 = v61;
    }
    if ( *(_DWORD *)(v13 + 228) == 1
      && (*(_DWORD *)(v13 + 192) & 1) != 0
      && *(_DWORD *)(v13 + 196) != 2
      && (*(_DWORD *)(v16 + 200) & 0x4000) == 0 )
    {
      ExReleaseResourceLite(*(PERESOURCE *)(v13 + 8));
      FatAcquireExclusiveVcb_Real(Entry, v16, 0, v17);
      v77 = 1;
      FatAcquireExclusiveFcb(Entry, v13, v18, v19);
      v76 = 1;
    }
  }
  v20 = v60;
  if ( v60 == 4 )
  {
    FatAcquireExclusiveVcb_Real(Entry, v16, 0, v6);
    v77 = 1;
    v20 = 4;
  }
  if ( v20 == 3 )
    FsRtlNotifyCleanup(*(PNOTIFY_SYNC *)(v16 + 816), (PLIST_ENTRY)(v16 + 800), v14);
  if ( v13 )
    FatVerifyFcb(Entry, v13);
  if ( !v12
    || (v5 = 1282, p_Flags = 2, (unsigned __int16)(*(_WORD *)v13 - 1282) > 2u)
    || *(_WORD *)v13 == 1283 && !(unsigned __int8)FatIsDirectoryEmpty((int)Entry, v13)
    || (v21 = FsRtlCheckOplockEx((POPLOCK)(v13 + 88), Irp, 0x20u, Entry, FatOplockComplete, FatPrePostIrp),
        (v22 = v21) == 0) )
  {
    if ( v60 == 2 )
    {
      ShareAccess = (PSHARE_ACCESS)(v13 + 200);
      p_DataSectionObject = &FileObject->SectionObjectPointer->DataSectionObject;
      if ( !*p_DataSectionObject && !p_DataSectionObject[2] && *(_QWORD *)(v13 + 228) == 0x100000001LL )
      {
        v32 = *(_DWORD *)(v13 + 192);
        if ( (v32 & 5) == 0 && *(_DWORD *)(v13 + 196) == 1 )
          *(_DWORD *)(v13 + 192) = v32 | 0x800;
      }
      v33 = (_DWORD *)(v13 + 192);
      v67[1] = v13 + 192;
      v71 = (unsigned int *)(v13 + 192);
      if ( (*(_DWORD *)(v13 + 192) & 0x4000) != 0 )
      {
        v34 = v14[1];
        if ( (v34 & 0x80000) != 0 )
        {
          v14[1] = v34 & 0xFFF7FFFF;
          *v33 &= ~0x4000u;
        }
      }
      RequestorProcess = IoGetRequestorProcess(Irp);
      FsRtlFastUnlockAll((PFILE_LOCK)(v13 + 320), FileObject, RequestorProcess, 0);
      if ( *((_QWORD *)v14 + 2) )
        EfsLastCloseEncryptOnCloseFileCallback(v14 + 4, 0);
      v66 = (_DWORD *)(v13 + 228);
      if ( *(_DWORD *)(v13 + 228) == 1 && *(_QWORD *)(v13 + 152) )
      {
        LOBYTE(v36) = 1;
        EfsLastCloseEncryptOnCloseFileCallback(v13 + 152, v36);
      }
      v37 = (_DWORD *)(v16 + 204);
      if ( *(_DWORD *)(v16 + 204) == 1 && (*(_DWORD *)(v16 + 200) & 0x40) == 0 )
      {
        if ( *(_DWORD *)(v13 + 196) == 1 )
        {
          FatUpdateDirentFromFcb((int)Entry, 0);
          v37 = (_DWORD *)(v16 + 204);
        }
        if ( *v66 == 1 && *(_DWORD *)(v13 + 196) == 1 )
        {
          v72 = v37;
          v67[0] = 0;
          if ( (*v33 & 1) == 0 || (*(_DWORD *)(v16 + 200) & 0x4000) != 0 )
          {
            if ( (*v33 & 4) == 0 )
            {
              v38 = *(_DWORD *)(v13 + 32);
              v39 = *(_DWORD *)(v13 + 40);
              if ( v39 < v38 )
              {
                v40 = *(_DWORD *)(v13 + 280);
                if ( v39 >= v40 )
                  v40 = *(_DWORD *)(v13 + 40);
                if ( v40 < v38 )
                {
                  FatZeroData(Entry, v16, FileObject);
                  v41 = *(_DWORD *)(v13 + 32);
                  *(_DWORD *)(v13 + 40) = v41;
                  *(_DWORD *)(v13 + 280) = v41;
                  SectionObjectPointer = FileObject->SectionObjectPointer;
                  if ( SectionObjectPointer )
                  {
                    if ( SectionObjectPointer->SharedCacheMap )
                      CcSetFileSizes(FileObject, (PCC_FILE_SIZES)(v13 + 24));
                  }
                }
              }
            }
          }
          else
          {
            LODWORD(v67[0]) = *(_DWORD *)(v13 + 32);
            HIDWORD(v67[0]) = *(_DWORD *)(v13 + 128);
            ExAcquireResourceExclusiveLite(*(PERESOURCE *)(v13 + 16), 1u);
            *(_DWORD *)(v13 + 32) = 0;
            *(_DWORD *)(v13 + 40) = 0;
            *(_DWORD *)(v13 + 280) = 0;
            ExReleaseResourceLite(*(PERESOURCE *)(v13 + 16));
            FatSetFileSizeInDirent(Entry, v13);
            *v33 |= 2u;
          }
          v43 = *v71;
          if ( (v43 & 2) != 0 )
          {
            if ( *v72 == 1 )
            {
              if ( (v43 & 1) != 0 )
              {
                v44 = 0;
              }
              else if ( (v43 & 0x8000) != 0 )
              {
                v44 = (unsigned int)(*(_DWORD *)(v13 + 32) + *(_DWORD *)(v13 + 132));
              }
              else
              {
                v44 = *(unsigned int *)(v13 + 32);
              }
              FatTruncateFileAllocation(Entry, v13, v44);
            }
            v70 = *(_QWORD *)(v13 + 32);
            TruncateSize = (PLARGE_INTEGER)&v70;
            v45 = v71;
            *v71 &= ~2u;
            v43 = *v45;
          }
          if ( (v43 & 1) != 0 && !*(_DWORD *)(v13 + 24) )
          {
            FatTunnelFcbOrDcb(v13, v14);
            LOBYTE(v46) = 1;
            FatDeleteDirent(Entry, v13, v67, v46);
            if ( !*(_QWORD *)(v13 + 536) )
              FatSetFullFileNameInFcb((int)Entry);
            FsRtlNotifyFullReportChange(
              *(PNOTIFY_SYNC *)(v16 + 816),
              (PLIST_ENTRY)(v16 + 800),
              (PSTRING)(v13 + 528),
              *(_WORD *)(v13 + 528) - *(_WORD *)(v13 + 544),
              0,
              0,
              1u,
              2u,
              0);
          }
          if ( (*v33 & 1) != 0 )
          {
            FatRemoveNames(v43, v13);
            v57 = 1;
            FsRtlCheckOplockEx((POPLOCK)(*(_QWORD *)(v13 + 176) + 88LL), Irp, 0x50u, 0, 0, 0);
          }
        }
      }
      --*v66;
      v25 = FileObject;
      if ( (FileObject->Flags & 0x40) == 0 )
        --*(_DWORD *)(v13 + 236);
      if ( (FileObject->Flags & 0x40) != 0 )
      {
        v47 = *(_DWORD *)(v13 + 236);
        if ( v47 )
        {
          if ( v47 == *v66 )
          {
            v48 = *(SECTION_OBJECT_POINTERS **)(v13 + 120);
            if ( v48->DataSectionObject )
            {
              CcFlushCache(v48, 0, 0, 0);
              ExAcquireResourceExclusiveLite(*(PERESOURCE *)(v13 + 16), 1u);
              ExReleaseResourceLite(*(PERESOURCE *)(v13 + 16));
              CcPurgeCacheSection(*(PSECTION_OBJECT_POINTERS *)(v13 + 120), 0, 0, 0);
            }
          }
        }
      }
      v49 = &FatLargeZero;
      if ( *(_DWORD *)(v13 + 196) != 2 )
        v49 = TruncateSize;
      TruncateSize = v49;
      CcUninitializeCacheMap(FileObject, v49, 0);
    }
    else
    {
      if ( v60 == 3 )
      {
        ShareAccess = (PSHARE_ACCESS)(v13 + 200);
        v26 = (_DWORD *)(v13 + 228);
        v66 = (_DWORD *)(v13 + 228);
        if ( *(_QWORD *)(v13 + 228) == 0x100000001LL && !*(_DWORD *)(v13 + 336) )
        {
          v27 = *(_DWORD *)(v13 + 192);
          if ( (v27 & 1) == 0 && *(_DWORD *)(v13 + 196) == 1 )
            *(_DWORD *)(v13 + 192) = v27 | 0x800;
        }
        if ( (*(_DWORD *)(v13 + 192) & 0x4000) != 0 )
        {
          v28 = v14[1];
          if ( (v28 & 0x80000) != 0 )
          {
            v14[1] = v28 & 0xFFF7FFFF;
            *(_DWORD *)(v13 + 192) &= ~0x4000u;
          }
        }
        if ( *(_DWORD *)(v16 + 204) == 1 && (*(_DWORD *)(v16 + 200) & 0x40) == 0 )
        {
          FatUpdateDirentFromFcb((int)Entry, 0);
          if ( *v26 == 1
            && *(_WORD *)v13 == 1283
            && (*(_DWORD *)(v13 + 192) & 1) != 0
            && *(_DWORD *)(v13 + 196) == 1
            && (*(_DWORD *)(v16 + 200) & 0x4000) == 0 )
          {
            if ( (unsigned __int8)FatIsDirectoryEmpty((int)Entry, v13) )
            {
              FsContext = 0;
              if ( (*(_DWORD *)(v16 + 200) & 0x400000) != 0 )
                FatDeleteEfsAttributeOnDirectory((int)Entry, v13);
              LODWORD(FsContext) = *(_DWORD *)(v13 + 32);
              HIDWORD(FsContext) = *(_DWORD *)(v13 + 128);
              ExAcquireResourceExclusiveLite(*(PERESOURCE *)(v13 + 16), 1u);
              *(_DWORD *)(v13 + 32) = 0;
              ExReleaseResourceLite(*(PERESOURCE *)(v13 + 16));
              FatTruncateFileAllocation(Entry, v13, 0);
              if ( !*(_DWORD *)(v13 + 24) )
              {
                FatTunnelFcbOrDcb(v13, 0);
                LOBYTE(v30) = 1;
                FatDeleteDirent(Entry, v13, &FsContext, v30);
                if ( !*(_QWORD *)(v13 + 536) )
                  FatSetFullFileNameInFcb((int)Entry);
                FsRtlNotifyFullReportChange(
                  *(PNOTIFY_SYNC *)(v16 + 816),
                  (PLIST_ENTRY)(v16 + 800),
                  (PSTRING)(v13 + 528),
                  *(_WORD *)(v13 + 528) - *(_WORD *)(v13 + 544),
                  0,
                  0,
                  2u,
                  2u,
                  0);
              }
              FatRemoveNames(v29, v13);
              v57 = 1;
              FsRtlCheckOplockEx((POPLOCK)(*(_QWORD *)(v13 + 176) + 88LL), Irp, 0x50u, 0, 0, 0);
            }
            else
            {
              *(_DWORD *)(v13 + 192) &= ~1u;
            }
          }
        }
        --*v26;
      }
      else
      {
        if ( v60 != 4 )
        {
          if ( v60 != 5 && v60 != 6 && v60 != 7 && (unsigned int)(v60 - 8) >= 2 )
            KeBugCheckEx(0x23u, 0x40478u, v60, 0, 0);
LABEL_137:
          if ( (unsigned int)(v60 - 2) <= 1 )
          {
            FsRtlCheckOplock((POPLOCK)(v13 + 88), Irp, Entry, 0, 0);
            if ( *(_DWORD *)(v13 + 196) == 1
              && *(_WORD *)v13 == 1282
              && FsRtlOplockIsFastIoPossible((POPLOCK)(v13 + 88)) )
            {
              if ( *(_BYTE *)(v13 + 336)
                || *(_DWORD *)(*(_QWORD *)(v13 + 120) + 24LL)
                || (*(_DWORD *)(*(_QWORD *)(v13 + 184) + 200LL) & 0x4000) != 0
                || (*(_DWORD *)(v13 + 192) & 0x8000) != 0 )
              {
                v50 = 2;
              }
              else
              {
                v50 = 1;
              }
            }
            else
            {
              v50 = 0;
            }
            *(_BYTE *)(v13 + 5) = v50;
          }
          *v73 = FileObject->Flags | 0x4000;
          v22 = 0;
          if ( v57 )
            *p_Information = 4;
          FatUnpinRepinnedBcbs(Entry, p_Flags, v5, v6);
          if ( (*(_DWORD *)(v16 + 200) & 0x1000) != 0 && (*(_DWORD *)(v16 + 200) & 0x4000) == 0 )
          {
            if ( v60 == 2 && (FileObject->Flags & 0x1000) != 0 )
              v22 = FatFlushFile(v51, v13, 1);
            if ( *(_BYTE *)(v16 + 376) != 12 || (v52 = 1, byte_140017D4C >= 0) )
              v52 = 0;
            if ( v22 < 0 )
              goto LABEL_167;
            if ( v13 )
            {
              if ( !v52 && (*(_DWORD *)(v13 + 192) & 0x10) != 0 )
              {
                v22 = FatFlushFat(Entry, v16);
                if ( v22 >= 0 )
                {
                  v54 = *(_QWORD *)(v13 + 176);
                  if ( v54 )
                    v22 = FatFlushFile(v53, v54, 1);
                }
              }
            }
            if ( v22 < 0 )
            {
LABEL_167:
              *((_DWORD *)Entry + 18) = v22;
              v55 = FsRtlNormalizeNtstatus(v22, -1073741591);
              ExRaiseStatus(v55);
            }
          }
          goto LABEL_168;
        }
        if ( (v14[1] & 0x10000) != 0 )
        {
          LOBYTE(v5) = 1;
          FatCheckForDismount(Entry, v16, v5);
          v24 = FileObject;
        }
        else
        {
          v24 = FileObject;
          if ( FileObject->WriteAccess && (FileObject->Flags & 0x1000) != 0 )
          {
            FatHijackIrpAndFlushDevice(FileObject, Irp, *(_QWORD *)(v16 + 136));
            *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v16 + 192) + 16LL) + 48LL) |= 2u;
            v24 = FileObject;
          }
        }
        if ( (*(_DWORD *)(v16 + 200) & 1) != 0 && *(PFILE_OBJECT *)(v16 + 792) == v24 )
        {
          FatAutoUnlock(v24, v16);
          v58 = 1;
        }
        ShareAccess = (PSHARE_ACCESS)(v16 + 244);
      }
      v25 = FileObject;
    }
    p_Flags = (__int64)ShareAccess;
    if ( ShareAccess )
      IoRemoveShareAccess(v25, ShareAccess);
    goto LABEL_137;
  }
  if ( v21 != 259 )
  {
    *((_DWORD *)Entry + 18) = v21;
    v23 = FsRtlNormalizeNtstatus(v21, -1073741591);
    ExRaiseStatus(v23);
  }
  *((_DWORD *)Entry + 17) |= 0x2000u;
LABEL_168:
  if ( v76 )
    ExReleaseResourceLite(*(PERESOURCE *)(v13 + 8));
  if ( v77 )
    ExReleaseResourceLite((PERESOURCE)(v16 + 520));
  if ( v58 )
    FsRtlNotifyVolumeEvent(v64, 5u);
  if ( v22 != 259 )
    FatCompleteRequest_Real(Entry, Irp);
  return (unsigned int)v22;
}

```

## disassembly

```asm
0x140024bd4  mov     rax, rsp
0x140024bd7  mov     [rax+10h], rdx
0x140024bdb  mov     [rax+8], rcx
0x140024bdf  push    rbx
0x140024be0  push    rsi
0x140024be1  push    rdi
0x140024be2  push    r12
0x140024be4  push    r13
0x140024be6  push    r14
0x140024be8  push    r15
0x140024bea  sub     rsp, 0E0h
0x140024bf1  mov     rbx, rdx
0x140024bf4  mov     r15, rcx
0x140024bf7  xor     edi, edi
0x140024bf9  mov     [rsp+118h+var_B0], rdi
0x140024bfe  mov     qword ptr [rsp+118h+var_A8], rdi
0x140024c03  mov     [rsp+118h+FsContext], rdi
0x140024c08  mov     [rax-60h], rdi
0x140024c0c  mov     rax, [rdx+0B8h]
0x140024c13  mov     r14, [rax+30h]
0x140024c17  mov     [rsp+118h+var_98], r14
0x140024c1f  mov     [rsp+118h+var_90], r14
0x140024c27  lea     r9, [rsp+118h+FsContext]
0x140024c2c  lea     r8, [rsp+118h+var_A8]
0x140024c31  lea     rdx, [rsp+118h+var_B0]
0x140024c36  mov     rcx, r14
0x140024c39  call    FatDecodeFileObject
0x140024c3e  mov     r13d, eax
0x140024c41  mov     [rsp+118h+var_B8], eax
0x140024c45  lea     esi, [rdi+1]
0x140024c48  cmp     eax, esi
0x140024c4a  jz      loc_140025A63
0x140024c50  lea     rdx, [r14+50h]
0x140024c54  mov     ecx, [rdx]
0x140024c56  bt      ecx, 0Eh
0x140024c5a  jnb     short loc_140024CD4
0x140024c5c  mov     rdx, [rsp+118h+var_B0]
0x140024c61  mov     ecx, [rdx+0C8h]
0x140024c67  bt      ecx, 0Ch
0x140024c6b  jnb     loc_140025A63
0x140024c71  mov     eax, [r14+50h]
0x140024c75  bt      eax, 0Ch
0x140024c79  jnb     loc_140025A63
0x140024c7f  mov     eax, [rdx+0C8h]
0x140024c85  bt      eax, 0Eh
0x140024c89  jb      loc_140025A63
0x140024c8f  cmp     r13d, 2
0x140024c93  jnz     loc_140025A63
0x140024c99  mov     r8d, esi
0x140024c9c  mov     rdx, qword ptr [rsp+118h+var_A8]
0x140024ca1  call    FatFlushFile
0x140024ca6  test    eax, eax
0x140024ca8  jns     loc_140025A63
0x140024cae  mov     [r15+48h], eax
0x140024cb2  mov     edx, 0C00000E9h; GenericException
0x140024cb7  mov     ecx, eax; Exception
0x140024cb9  call    cs:__imp_FsRtlNormalizeNtstatus
0x140024cc0  nop     dword ptr [rax+rax+00h]
0x140024cc5  mov     ecx, eax; Status
0x140024cc7  call    cs:__imp_ExRaiseStatus
0x140024cd4  mov     [rsp+118h+FileObject], r14
0x140024cd9  mov     [rsp+118h+var_48], rdx
0x140024ce1  mov     [rsp+118h+var_B4], edi
0x140024ce5  mov     [rsp+118h+var_C7], dil
0x140024cea  mov     [rsp+118h+TruncateSize], rdi
0x140024cf2  mov     [rsp+118h+arg_18], dil
0x140024cfa  mov     r14b, dil
0x140024cfd  mov     [rsp+118h+var_C6], dil
0x140024d02  mov     [rsp+118h+var_C8], dil
0x140024d07  lea     rax, [rbx+38h]
0x140024d0b  mov     [rsp+118h+var_40], rax
0x140024d13  mov     qword ptr [rax], 2
0x140024d1a  lea     eax, [r13-2]
0x140024d1e  mov     rbx, qword ptr [rsp+118h+var_A8]
0x140024d23  cmp     eax, esi
0x140024d25  ja      loc_140024E1F
0x140024d2b  mov     rdx, rbx
0x140024d2e  mov     rcx, r15
0x140024d31  call    FatAcquireExclusiveFcb
0x140024d36  mov     [rsp+118h+arg_10], sil
0x140024d3e  mov     r12, [rsp+118h+FsContext]
0x140024d43  test    dword ptr [r12+4], 400h
0x140024d4c  jz      short loc_140024DB6
0x140024d4e  or      [rbx+0C0h], esi
0x140024d54  btr     dword ptr [r12+4], 0Ah
0x140024d5b  mov     r14b, sil
0x140024d5e  mov     [rsp+118h+var_C6], sil
0x140024d63  cmp     r13d, 3
0x140024d67  mov     r13, [rsp+118h+var_B0]
0x140024d6c  jnz     short loc_140024DBB
0x140024d6e  lea     rdx, [r13+320h]; NotifyList
0x140024d75  mov     [rsp+118h+SubjectContext], rdi; SubjectContext
0x140024d7a  mov     [rsp+118h+TraverseCallback], rdi; TraverseCallback
0x140024d7f  mov     [rsp+118h+NotifyIrp], rdi; NotifyIrp
0x140024d84  mov     [rsp+118h+CompletionFilter], edi; CompletionFilter
0x140024d88  mov     [rsp+118h+IgnoreBuffer], dil; IgnoreBuffer
0x140024d8d  mov     [rsp+118h+WatchTree], dil; WatchTree
0x140024d92  xor     r9d, r9d; FullDirectoryName
0x140024d95  mov     r8, [rsp+118h+var_98]
0x140024d9d  mov     r8, [r8+18h]; FsContext
0x140024da1  mov     rcx, [r13+330h]; NotifySync
0x140024da8  call    cs:__imp_FsRtlNotifyFullChangeDirectory
0x140024daf  nop     dword ptr [rax+rax+00h]
0x140024db4  jmp     short loc_140024DBB
0x140024db6  mov     r13, [rsp+118h+var_B0]
0x140024dbb  cmp     [rbx+0E4h], esi
0x140024dc1  jnz     short loc_140024E31
0x140024dc3  mov     eax, [rbx+0C0h]
0x140024dc9  test    sil, al
0x140024dcc  jz      short loc_140024E31
0x140024dce  cmp     dword ptr [rbx+0C4h], 2
0x140024dd5  jz      short loc_140024E31
0x140024dd7  mov     eax, [r13+0C8h]
0x140024dde  bt      eax, 0Eh
0x140024de2  jb      short loc_140024E31
0x140024de4  mov     rcx, [rbx+8]; Resource
0x140024de8  call    cs:__imp_ExReleaseResourceLite
0x140024def  nop     dword ptr [rax+rax+00h]
0x140024df4  xor     r8d, r8d
0x140024df7  mov     rdx, r13
0x140024dfa  mov     rcx, r15
0x140024dfd  call    FatAcquireExclusiveVcb_Real
0x140024e02  mov     [rsp+118h+arg_18], sil
0x140024e0a  mov     rdx, rbx
0x140024e0d  mov     rcx, r15
0x140024e10  call    FatAcquireExclusiveFcb
0x140024e15  mov     [rsp+118h+arg_10], sil
0x140024e1d  jmp     short loc_140024E31
0x140024e1f  mov     [rsp+118h+arg_10], dil
0x140024e27  mov     r13, [rsp+118h+var_B0]
0x140024e2c  mov     r12, [rsp+118h+FsContext]
0x140024e31  mov     eax, [rsp+118h+var_B8]
0x140024e35  cmp     eax, 4
0x140024e38  jnz     short loc_140024E54
0x140024e3a  xor     r8d, r8d
0x140024e3d  mov     rdx, r13
0x140024e40  mov     rcx, r15
0x140024e43  call    FatAcquireExclusiveVcb_Real
0x140024e48  mov     [rsp+118h+arg_18], sil
0x140024e50  mov     eax, [rsp+118h+var_B8]
0x140024e54  cmp     eax, 3
0x140024e57  jnz     short loc_140024E76
0x140024e59  lea     rdx, [r13+320h]; NotifyList
0x140024e60  mov     r8, r12; FsContext
0x140024e63  mov     rcx, [r13+330h]; NotifySync
0x140024e6a  call    cs:__imp_FsRtlNotifyCleanup
0x140024e71  nop     dword ptr [rax+rax+00h]
0x140024e76  test    rbx, rbx
0x140024e79  jz      short loc_140024EC2
0x140024e7b  mov     rdx, rbx
0x140024e7e  mov     rcx, r15
0x140024e81  call    FatVerifyFcb
0x140024e86  jmp     short loc_140024EC1
0x140024e88  mov     r15, [rsp+118h+arg_0]
0x140024e90  mov     dword ptr [r15+48h], 0
0x140024e98  xor     edi, edi
0x140024e9a  lea     esi, [rdi+1]
0x140024e9d  mov     r13, [rsp+118h+var_B0]
0x140024ea2  mov     rbx, qword ptr [rsp+118h+var_A8]
0x140024ea7  mov     r12, [rsp+118h+FsContext]
0x140024eac  mov     r14b, [rsp+118h+var_C6]
0x140024eb1  mov     rax, [rsp+118h+var_90]
0x140024eb9  mov     [rsp+118h+var_98], rax
0x140024ec1  nop
0x140024ec2  test    r14b, r14b
0x140024ec5  jz      loc_140024F7D
0x140024ecb  movzx   ecx, word ptr [rbx]
0x140024ece  mov     r8d, 502h
0x140024ed4  movzx   eax, cx
0x140024ed7  sub     ax, r8w
0x140024edb  mov     edx, 2
0x140024ee0  cmp     ax, dx
0x140024ee3  ja      loc_140024F7D
0x140024ee9  lea     r14d, [r8+1]
0x140024eed  cmp     cx, r14w
0x140024ef1  jnz     short loc_140024F02
0x140024ef3  mov     rdx, rbx; int
0x140024ef6  mov     rcx, r15; int
0x140024ef9  call    FatIsDirectoryEmpty
0x140024efe  test    al, al
0x140024f00  jz      short loc_140024F7D
0x140024f02  lea     rcx, [rbx+58h]; Oplock
0x140024f06  lea     rax, FatPrePostIrp
0x140024f0d  mov     qword ptr [rsp+118h+IgnoreBuffer], rax; PostIrpRoutine
0x140024f12  lea     rax, FatOplockComplete
0x140024f19  mov     qword ptr [rsp+118h+WatchTree], rax; CompletionRoutine
0x140024f1e  mov     r9, r15; Context
0x140024f21  mov     r8d, 20h ; ' '; Flags
0x140024f27  mov     rdx, [rsp+118h+Irp]; Irp
0x140024f2f  call    cs:__imp_FsRtlCheckOplockEx
0x140024f36  nop     dword ptr [rax+rax+00h]
0x140024f3b  mov     r14d, eax
0x140024f3e  mov     [rsp+118h+var_B4], eax
0x140024f42  test    eax, eax
0x140024f44  jz      short loc_140024F7D
0x140024f46  cmp     eax, 103h
0x140024f4b  jnz     short loc_140024F58
0x140024f4d  bts     dword ptr [r15+44h], 0Dh
0x140024f53  jmp     loc_1400259EB
0x140024f58  mov     [r15+48h], eax
0x140024f5c  mov     edx, 0C00000E9h; GenericException
0x140024f61  mov     ecx, eax; Exception
0x140024f63  call    cs:__imp_FsRtlNormalizeNtstatus
0x140024f6a  nop     dword ptr [rax+rax+00h]
0x140024f6f  mov     ecx, eax; Status
0x140024f71  call    cs:__imp_ExRaiseStatus
0x140024f7d  mov     ecx, [rsp+118h+var_B8]
0x140024f81  sub     ecx, 2
0x140024f84  jz      loc_1400252E6
0x140024f8a  sub     ecx, 1
0x140024f8d  jz      loc_140025081
0x140024f93  sub     ecx, 1
0x140024f96  jz      short loc_140024FDE
0x140024f98  sub     ecx, 1
0x140024f9b  jz      short loc_140024FD3
0x140024f9d  sub     ecx, 1
0x140024fa0  jz      short loc_140024FD3
0x140024fa2  sub     ecx, 1
0x140024fa5  jz      short loc_140024FD3
0x140024fa7  sub     ecx, 1
0x140024faa  jz      short loc_140024FD3
0x140024fac  cmp     ecx, 1
0x140024faf  jz      short loc_140024FD3
0x140024fb1  movsxd  r8, [rsp+118h+var_B8]; BugCheckParameter2
0x140024fb6  mov     qword ptr [rsp+118h+WatchTree], rdi; BugCheckParameter4
0x140024fbb  xor     r9d, r9d; BugCheckParameter3
0x140024fbe  mov     edx, 40478h; BugCheckParameter1
0x140024fc3  lea     ecx, [r9+23h]; BugCheckCode
0x140024fc7  call    cs:__imp_KeBugCheckEx
0x140024fd3  mov     r12d, 2
0x140024fd9  jmp     loc_140025841
0x140024fde  test    dword ptr [r12+4], 10000h
0x140024fe7  jz      short loc_14002503D
0x140024fe9  mov     r8b, sil
0x140024fec  mov     rdx, r13
0x140024fef  mov     rcx, r15
0x140024ff2  call    FatCheckForDismount
0x140024ff7  mov     rcx, [rsp+118h+FileObject]
0x140024ffc  mov     r12d, 2
0x140025002  mov     eax, [r13+0C8h]
0x140025009  test    sil, al
0x14002500c  jz      short loc_140025024
0x14002500e  cmp     [r13+318h], rcx
0x140025015  jnz     short loc_140025024
0x140025017  mov     rdx, r13
0x14002501a  call    FatAutoUnlock
0x14002501f  mov     [rsp+118h+var_C7], sil
0x140025024  lea     rax, [r13+0F4h]
0x14002502b  mov     [rsp+118h+ShareAccess], rax
0x140025033  mov     r14, [rsp+118h+FileObject]
0x140025038  jmp     loc_140025825
0x14002503d  mov     rcx, [rsp+118h+FileObject]
0x140025042  cmp     [rcx+4Bh], dil
0x140025046  jz      short loc_140024FFC
0x140025048  mov     eax, [rcx+50h]
0x14002504b  bt      eax, 0Ch
0x14002504f  jnb     short loc_140024FFC
0x140025051  mov     r8, [r13+88h]
0x140025058  mov     rdx, [rsp+118h+Irp]
0x140025060  call    FatHijackIrpAndFlushDevice
0x140025065  mov     rax, [r13+0C0h]
0x14002506c  mov     rcx, [rax+10h]
0x140025070  mov     r12d, 2
0x140025076  or      [rcx+30h], r12d
0x14002507a  mov     rcx, [rsp+118h+FileObject]
0x14002507f  jmp     short loc_140025002
0x140025081  lea     rax, [rbx+0C8h]
0x140025088  mov     [rsp+118h+ShareAccess], rax
0x140025090  lea     r14, [rbx+0E4h]
0x140025097  mov     [rsp+118h+var_88], r14
0x14002509f  cmp     [r14], esi
0x1400250a2  jnz     short loc_1400250D1
0x1400250a4  cmp     [rbx+0E8h], esi
0x1400250aa  jnz     short loc_1400250D1
0x1400250ac  cmp     [rbx+150h], edi
0x1400250b2  jnz     short loc_1400250D1
0x1400250b4  mov     eax, [rbx+0C0h]
0x1400250ba  test    sil, al
0x1400250bd  jnz     short loc_1400250D1
0x1400250bf  cmp     [rbx+0C4h], esi
0x1400250c5  jnz     short loc_1400250D1
0x1400250c7  bts     eax, 0Bh
0x1400250cb  mov     [rbx+0C0h], eax
0x1400250d1  test    dword ptr [rbx+0C0h], 4000h
0x1400250db  jz      short loc_1400250F9
0x1400250dd  mov     eax, [r12+4]
0x1400250e2  bt      eax, 13h
0x1400250e6  jnb     short loc_1400250F9
0x1400250e8  btr     eax, 13h
0x1400250ec  mov     [r12+4], eax
0x1400250f1  btr     dword ptr [rbx+0C0h], 0Eh
0x1400250f9  cmp     [r13+0CCh], esi
0x140025100  jnz     short loc_14002516A
0x140025102  mov     eax, [r13+0C8h]
0x140025109  test    al, 40h
0x14002510b  jnz     short loc_14002516A
0x14002510d  mov     [rsp+118h+WatchTree], dil; char
0x140025112  mov     r9, r12
0x140025115  mov     r8, rbx
0x140025118  mov     rdx, [rsp+118h+FileObject]
  ... truncated ...
```
