# RefsCommonCleanup(_IRP_CONTEXT *,_IRP *)

- ea: `0x140314de0`
- end: `0x1403185af`
- name: `?RefsCommonCleanup@@YAJPEAU_IRP_CONTEXT@@PEAU_IRP@@@Z`
- size: `14287`
- prototype: `__int64 __fastcall(struct _IRP_CONTEXT *, struct _IRP *)`
- caller_count: `3`
- callee_count: `64`
- tags: `file_ops, reparse_path, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1400bc440`
- `0x1400e14f0`
- `0x140314a80`

## callees

- `0x140008c10`
- `0x14000a500`
- `0x14000bcc0`
- `0x14000cd70`
- `0x140021f60`
- `0x140038f80`
- `0x140041b40`
- `0x14007e870`
- `0x140080680`
- `0x140081670`
- `0x14008c400`
- `0x14008d3c0`
- `0x14008dbd0`
- `0x14008e360`
- `0x14008e3c0`
- `0x14008faf0`
- `0x140091170`
- `0x1400967f0`
- `0x140098160`
- `0x140099960`
- `0x1400a3350`
- `0x1400ad0c8`
- `0x1400ae8fc`
- `0x1400ae910`
- `0x1400b1dfc`
- `0x1400ca788`
- `0x1400e1534`
- `0x140110650`
- `0x1401159ec`
- `0x1401e9ce0`
- `0x1401ea660`
- `0x1402853d4`
- `0x140285fa0`
- `0x140286a28`
- `0x140286ebc`
- `0x140287648`
- `0x140287828`
- `0x140287d0c`
- `0x14028eb68`
- `0x1402906b8`
- `0x140290778`
- `0x140290854`
- `0x1402e6d5c`
- `0x1402e6f54`
- `0x1402fec90`
- `0x1403000b0`
- `0x1403008f0`
- `0x1403021e0`
- `0x140314de0`
- `0x14031ac80`

## import_xrefs

- `ntoskrnl!KeBugCheckEx` at `0x1403156da`
- `ntoskrnl!KeBugCheckEx` at `0x1403156da`
- `ntoskrnl!MmCanFileBeTruncated` at `0x1403170d3`
- `ntoskrnl!MmCanFileBeTruncated` at `0x1403170d3`
- `ntoskrnl!MmFlushImageSection` at `0x140315449`
- `ntoskrnl!MmFlushImageSection` at `0x140315449`
- `ntoskrnl!FsRtlNotifyFilterChangeDirectory` at `0x14031542e`
- `ntoskrnl!FsRtlNotifyFilterChangeDirectory` at `0x14031542e`
- `ntoskrnl!FsRtlNotifyCleanup` at `0x140315c62`
- `ntoskrnl!FsRtlNotifyCleanup` at `0x140315c62`
- `ntoskrnl!FsRtlFastUnlockAll` at `0x140316207`
- `ntoskrnl!FsRtlFastUnlockAll` at `0x140316207`
- `ntoskrnl!IoGetRequestorProcess` at `0x1403161e6`
- `ntoskrnl!IoGetRequestorProcess` at `0x1403161e6`
- `ntoskrnl!IoGetActivityIdThread` at `0x140317e9b`
- `ntoskrnl!IoGetActivityIdThread` at `0x140317e9b`
- `ntoskrnl!IoGetActivityIdIrp` at `0x140317e7f`
- `ntoskrnl!IoGetActivityIdIrp` at `0x140317e7f`
- `ntoskrnl!FsRtlHeatLogIo` at `0x140317ef3`
- `ntoskrnl!FsRtlHeatLogIo` at `0x140317ef3`
- `ntoskrnl!MmForceSectionClosed` at `0x14031809e`
- `ntoskrnl!MmForceSectionClosed` at `0x14031809e`
- `ntoskrnl!FsRtlNotifyVolumeEvent` at `0x14031819f`
- `ntoskrnl!FsRtlNotifyVolumeEvent` at `0x1403405cf`
- `ntoskrnl!FsRtlNotifyVolumeEvent` at `0x14031819f`
- `ntoskrnl!FsRtlNotifyVolumeEvent` at `0x1403405cf`
- `ntoskrnl!IoRaiseInformationalHardError` at `0x140318380`
- `ntoskrnl!IoRaiseInformationalHardError` at `0x140318380`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140317fb6`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1403181be`
- `ntoskrnl!KeEnterGuardedRegion` at `0x14031834f`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140340600`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140317fb6`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1403181be`
- `ntoskrnl!KeEnterGuardedRegion` at `0x14031834f`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140340600`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140317fc5`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1403181cd`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14031835f`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14034060f`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140317fc5`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1403181cd`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14031835f`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14034060f`
- `ntoskrnl!FsRtlOplockIsFastIoPossible` at `0x14031626c`
- `ntoskrnl!FsRtlOplockIsFastIoPossible` at `0x14031626c`
- `ntoskrnl!FsRtlCheckOplock` at `0x140315c16`
- `ntoskrnl!FsRtlCheckOplock` at `0x1403161be`
- `ntoskrnl!FsRtlCheckOplock` at `0x140315c16`
- `ntoskrnl!FsRtlCheckOplock` at `0x1403161be`
- `ntoskrnl!FsRtlCheckOplockEx` at `0x140315549`
- `ntoskrnl!FsRtlCheckOplockEx` at `0x140317dbf`
- `ntoskrnl!FsRtlCheckOplockEx` at `0x140315549`
- `ntoskrnl!FsRtlCheckOplockEx` at `0x140317dbf`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140317fee`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1403181f6`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140318394`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140340637`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140317fee`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1403181f6`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140318394`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140340637`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140317ffa`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140318202`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1403183a0`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140340643`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140317ffa`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140318202`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1403183a0`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140340643`

## pseudocode

```c
__int64 __fastcall RefsCommonCleanup(struct _IRP_CONTEXT *a1, struct _IRP *a2)
{
  struct _IRP_CONTEXT *v3; // r15
  __int64 v4; // rdx
  PFILE_OBJECT v5; // r8
  __int64 v6; // rsi
  struct _VCB *v7; // r10
  unsigned int *FsContext2; // rcx
  struct _FCB *v9; // rbx
  char v10; // r14
  unsigned int *v11; // r12
  char v12; // di
  _DWORD *v13; // rcx
  int v14; // r8d
  CmsVolume *v15; // rcx
  unsigned __int8 v16; // al
  __int64 v17; // rdx
  __int64 v18; // r8
  unsigned int v19; // r8d
  _DWORD *p_Resource; // r14
  char v21; // al
  int *v22; // rbx
  int v23; // ecx
  char v24; // r12
  struct _LCB *FcbReleases; // r14
  struct _FCB *v26; // rbx
  int *v27; // rdx
  unsigned int v28; // r8d
  char v29; // r8
  __int64 v30; // rcx
  PMRX_NET_ROOT pNetRoot; // rax
  unsigned __int8 IsLinkDeleteable; // al
  int v33; // eax
  bool v34; // al
  PMRX_NET_ROOT v35; // rax
  NTSTATUS v36; // edi
  bool v37; // al
  PFILE_OBJECT v38; // r8
  struct _VCB *v39; // rbx
  __int64 v40; // rdx
  __int64 v41; // rcx
  __int64 v42; // r9
  _BYTE *v43; // rcx
  struct _FCB *v44; // rbx
  NTSTATUS v45; // r10d
  _BYTE *v46; // r11
  __int16 v47; // cx
  struct _FILE_OBJECT *v48; // rcx
  int *v49; // rbx
  struct _FCB *QuadPart; // rax
  struct _IRP_CONTEXT *v51; // rcx
  __int64 v52; // rax
  struct _FCB *v53; // rax
  PNON_PAGED_FCB NonPaged; // rax
  struct _IRP_CONTEXT *v55; // rcx
  int v56; // eax
  __int16 v57; // cx
  struct _KPROCESS *RequestorProcess; // rax
  __int64 v59; // rax
  char v60; // al
  char v61; // dl
  NTSTATUS v62; // edx
  char v63; // r12
  LARGE_INTEGER *p_FileSize; // rcx
  LARGE_INTEGER *v65; // rax
  __int64 v66; // rbx
  char v67; // di
  __int64 v68; // rax
  _QWORD *v69; // rdx
  __int64 v70; // r9
  unsigned int v71; // r8d
  char v72; // r12
  __int64 v73; // rcx
  int v74; // eax
  struct IndexSCB *v75; // rdi
  struct _FCB *v76; // rbx
  struct _UNICODE_STRING *v77; // rdx
  struct _FCB *v78; // rax
  PFILE_OBJECT v79; // rbx
  int v80; // eax
  struct _FCB *v81; // r10
  unsigned __int8 v82; // cl
  PFILE_OBJECT v83; // rbx
  unsigned __int8 v84; // r8
  char *v85; // rbx
  PFILE_OBJECT v86; // rbx
  PFILE_OBJECT v87; // rcx
  NTSTATUS v88; // edx
  LARGE_INTEGER AllocationSize; // rdx
  __int64 v91; // rax
  __int64 v92; // r8
  __int64 v93; // rax
  DWORD v94; // eax
  int v95; // ecx
  __int64 v96; // rax
  __int64 v97; // rax
  __int64 v98; // rcx
  struct _CC_FILE_SIZES *v99; // rdx
  NTSTATUS v100; // eax
  DWORD LowPart; // edx
  int v102; // ecx
  ULONG v103; // eax
  int v104; // ecx
  struct _IRP_CONTEXT *v105; // rcx
  __int16 v106; // ax
  int v107; // ecx
  int v108; // eax
  ULONG v109; // eax
  ULONG v110; // edx
  bool v111; // cf
  struct _IRP_CONTEXT *v112; // rcx
  const __int64 *v113; // rdx
  __int64 v114; // rax
  struct _FCB *i; // rax
  int v116; // ecx
  _DWORD *v118; // rdx
  ULONG_PTR v119; // rcx
  ULONG v120; // r8d
  __int64 v121; // rdx
  __int64 v122; // rcx
  int ActivityIdIrp; // eax
  _BYTE *v124; // rdx
  _OWORD *ActivityIdThread; // rax
  PIRP v126; // rax
  char v127; // r11
  __int64 v128; // rdi
  struct _FAST_MUTEX *v129; // rbx
  __int64 v130; // r11
  _DWORD *v131; // rdi
  unsigned int v132; // eax
  PFILE_OBJECT v133; // r14
  SECTION_OBJECT_POINTERS *v134; // rcx
  int v135; // eax
  char v136; // si
  __int64 v137; // rdi
  struct _FAST_MUTEX *v138; // rbx
  struct _UNICODE_STRING *v139; // r14
  unsigned __int8 v140; // r8
  int v141; // eax
  NTSTATUS v142; // edi
  struct _FCB *v143; // rsi
  PMRX_NET_ROOT v144; // rbx
  unsigned int v145; // ebx
  __int64 v146; // rax
  __int64 v148; // rax
  int WatchTree; // [rsp+20h] [rbp-1F8h]
  char v150; // [rsp+60h] [rbp-1B8h]
  NTSTATUS Status[2]; // [rsp+64h] [rbp-1B4h] BYREF
  char v152; // [rsp+6Ch] [rbp-1ACh]
  __int64 v153; // [rsp+70h] [rbp-1A8h]
  _BYTE *v154; // [rsp+78h] [rbp-1A0h]
  struct _FCB *v155; // [rsp+80h] [rbp-198h]
  struct _VCB *v156; // [rsp+88h] [rbp-190h]
  struct _IRP_CONTEXT *v157; // [rsp+90h] [rbp-188h]
  PVOID FsContext; // [rsp+98h] [rbp-180h]
  PFILE_OBJECT FileObject; // [rsp+A0h] [rbp-178h]
  unsigned __int8 v160; // [rsp+A8h] [rbp-170h]
  char v161; // [rsp+A9h] [rbp-16Fh]
  __int64 v162; // [rsp+B0h] [rbp-168h]
  struct _LCB *v163; // [rsp+B8h] [rbp-160h] BYREF
  char v164; // [rsp+C0h] [rbp-158h]
  bool v165; // [rsp+C1h] [rbp-157h]
  unsigned __int8 v166; // [rsp+C2h] [rbp-156h]
  char v167; // [rsp+C3h] [rbp-155h]
  char *v168; // [rsp+C8h] [rbp-150h]
  struct IndexSCB *InternalSrvOpen; // [rsp+D0h] [rbp-148h] BYREF
  struct _IRP_CONTEXT *v170; // [rsp+D8h] [rbp-140h]
  __int64 v171; // [rsp+E0h] [rbp-138h]
  struct _FCB *v172; // [rsp+E8h] [rbp-130h]
  PFILE_OBJECT v173; // [rsp+F0h] [rbp-128h]
  _DWORD *v174; // [rsp+F8h] [rbp-120h]
  unsigned __int8 v175[8]; // [rsp+100h] [rbp-118h] BYREF
  PIRP Irp; // [rsp+108h] [rbp-110h]
  _QWORD *v177; // [rsp+110h] [rbp-108h] BYREF
  int v178; // [rsp+118h] [rbp-100h]
  struct _LCB *v179; // [rsp+120h] [rbp-F8h] BYREF
  int *v180; // [rsp+128h] [rbp-F0h]
  struct _CC_FILE_SIZES *v181; // [rsp+130h] [rbp-E8h]
  _DWORD *v182; // [rsp+138h] [rbp-E0h]
  PVOID *p_FsContext; // [rsp+140h] [rbp-D8h]
  int *v184; // [rsp+148h] [rbp-D0h]
  int v185; // [rsp+150h] [rbp-C8h]
  int v186; // [rsp+154h] [rbp-C4h]
  LARGE_INTEGER *v187; // [rsp+158h] [rbp-C0h]
  struct _UNICODE_STRING v188; // [rsp+160h] [rbp-B8h]
  char *v189; // [rsp+170h] [rbp-A8h]
  struct _LCB *v190; // [rsp+178h] [rbp-A0h]
  struct _CC_FILE_SIZES v191; // [rsp+180h] [rbp-98h] BYREF
  LONGLONG *v192; // [rsp+198h] [rbp-80h]
  _QWORD *v193; // [rsp+1A0h] [rbp-78h]
  struct _UNICODE_STRING v194; // [rsp+1B0h] [rbp-68h] BYREF
  _BYTE v195[40]; // [rsp+1C0h] [rbp-58h] BYREF

  v3 = a1;
  v157 = a1;
  Irp = a2;
  Status[1] = 0;
  v163 = 0;
  InternalSrvOpen = 0;
  v4 = 0;
  v153 = 0;
  LOWORD(Status[0]) = 1;
  a2->IoStatus.Information = 2;
  v5 = a2->Tail.Overlay.CurrentStackLocation->FileObject;
  FileObject = v5;
  v173 = v5;
  p_FsContext = &v5->FsContext;
  v6 = (__int64)v5->FsContext;
  if ( v6 )
  {
    v7 = *(struct _VCB **)(v6 + 144);
    v156 = v7;
    v170 = v7;
    FsContext2 = (unsigned int *)v5->FsContext2;
    FsContext = FsContext2;
    v168 = (char *)FsContext2;
    v9 = *(struct _FCB **)(v6 + 136);
    v155 = v9;
    v172 = v9;
    if ( FsContext2 )
      v10 = *((_BYTE *)FsContext2 + 80);
    else
      v10 = 5;
  }
  else
  {
    v7 = 0;
    v156 = 0;
    v170 = 0;
    v9 = 0;
    v155 = 0;
    v172 = 0;
    FsContext2 = 0;
    FsContext = 0;
    v168 = 0;
    v10 = 1;
  }
  v160 = v10;
  if ( ((v10 - 1) & 0xFB) == 0 )
  {
    v5->Flags |= 0x4000u;
    v148 = *((_QWORD *)v3 + 1);
    if ( (v148 & 0x100000000LL) != 0 )
      *((_QWORD *)v3 + 1) = v148 | 0x200000000LL;
    else
      RefsCompleteRequest((PSECURITY_SUBJECT_CONTEXT *)v3, Irp, 0);
    return 0;
  }
  v11 = FsContext2 + 1;
  v12 = BYTE1(Status[0]) & 0xEF | (2 * (FsContext2[1] & 8));
  v150 = v12;
  BYTE1(Status[0]) = v12;
  *((_DWORD *)v3 + 158) = FsContext2[21];
  if ( v10 != 4 )
  {
    if ( (*((_DWORD *)v3 + 2) & 0x100LL) == 0 )
    {
      v17 = *((_QWORD *)v3 + 13);
      if ( (*(_QWORD *)(v17 + 8) & 0x20000000000LL) == 0 )
      {
        MsInitializeFastResourceOwnerEntry(v17 + 160);
        *(_QWORD *)(v17 + 8) |= v18;
      }
      if ( !(unsigned __int8)MsAcquireFastResourceSharedInternal<0>(
                               (char *)v7 + 1312,
                               v17 + 160,
                               *((_BYTE *)v3 + 8) & 1) )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            11,
            WPP_31376ab3b8073048edfb14e725e449b5_Traceguids,
            3221225688LL);
        }
        if ( (_BYTE)RefsStatusDebugEnabled )
          RefsStatusDebug(-1073741608, v3, "ResrcSup.c", 0x1EDu);
        RefsRaiseStatusInternal(v3, -1073741608, v19);
        goto LABEL_581;
      }
      goto LABEL_12;
    }
    goto LABEL_19;
  }
  if ( (*((_DWORD *)v7 + 6) & 2) != 0 && (PFILE_OBJECT)(*((_QWORD *)v7 + 109) & 0xFFFFFFFFFFFFFFFEuLL) == v5 )
  {
LABEL_19:
    RefsAcquireExclusiveVcb(v3, v7, 1u);
    goto LABEL_12;
  }
  if ( (*(_DWORD *)(*((_QWORD *)v3 + 13) + 8LL) & 0x800000) == 0 )
  {
    RefsAcquireSharedVcb(v3, v7, 1u);
LABEL_12:
    v4 = v153;
    v7 = v156;
  }
  v182 = p_FsContext;
  *(_QWORD *)v195 = v6;
  v171 = v6;
  v181 = (struct _CC_FILE_SIZES *)v6;
  v161 = v10;
  v180 = (int *)v11;
  v13 = (_DWORD *)((char *)v7 + 24);
  v162 = (__int64)v7 + 24;
  v14 = *((_DWORD *)v7 + 6);
  if ( (v14 & 0x8000823) == 1 && (*(_DWORD *)(v6 + 300) & 0x4000) == 0 )
  {
    v15 = (CmsVolume *)*((_QWORD *)v7 + 14);
    if ( v15 )
    {
      v16 = CmsVolume::AreWritesDoomed(v15);
      v13 = (_DWORD *)v162;
      if ( !v16 )
        LOBYTE(v4) = v4 | 4;
    }
    else
    {
      v13 = (_DWORD *)v162;
    }
  }
  if ( (v14 & 0x2000020) != 0
    || (p_Resource = &v9->spacer.Resource, v154 = &v9->spacer.Resource, ((__int64)v9->Header.Resource & 0x20) != 0) )
  {
    p_Resource = &v9->spacer.Resource;
    v154 = &v9->spacer.Resource;
    v21 = 8;
  }
  else
  {
    v21 = 0;
  }
  v174 = p_Resource;
  LOBYTE(v4) = v21 | v4 & 0xF7;
  v153 = v4;
  BYTE2(Status[0]) = v4;
  v152 = v4;
  if ( (*v13 & 0x4000000) != 0 )
  {
    v12 |= 4u;
    v150 = v12;
    BYTE1(Status[0]) = v12;
  }
  RefsAcquireFcbWithPaging((__int64)v3, (__int64)v9, v6, 0x10u);
  v22 = v180;
  v23 = *v180;
  if ( *v180 < 0 )
  {
    --*(_DWORD *)(v6 + 344);
    *v22 &= ~0x80000000;
    v23 = *v22;
  }
  v184 = (int *)((char *)FsContext + 8);
  v177 = (char *)FsContext + 8;
  if ( (*((_DWORD *)FsContext + 2) & 4) != 0 || (v24 = 1, (*p_Resource & 0x800LL) != 0) )
    v24 = 9;
  LOBYTE(Status[0]) = v24;
  FcbReleases = (struct _LCB *)*((_QWORD *)FsContext + 9);
  v163 = FcbReleases;
  v190 = FcbReleases;
  v179 = FcbReleases;
  if ( !FcbReleases || (*((_DWORD *)FcbReleases + 1) & 2) != 0 )
  {
    FcbReleases = 0;
    v163 = 0;
    v179 = 0;
    *v22 = v23 & 0xFFFBFFFF;
  }
  else
  {
    InternalSrvOpen = (struct IndexSCB *)*((_QWORD *)FcbReleases + 3);
  }
  v26 = v155;
  if ( !RefsIsFileOpen(v155) && ((__int64)v155->spacer.Resource & 1) == 0 )
  {
LABEL_581:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_19f8fd460e213a7a43a7f3710d090bd3_Traceguids, 3221225768LL);
    }
    if ( (_BYTE)RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741528, v3, "Cleanup.c", 0x5B8u);
    RefsRaiseStatusInternal(v3, -1073741528, v28);
    goto LABEL_588;
  }
  v29 = v152;
  if ( (v152 & 4) == 0 || (v152 & 8) != 0 || ((__int64)v155->spacer.Resource & 1) != 0 )
    goto LABEL_101;
  v30 = (unsigned int)*v180;
  if ( (v30 & 0x40000) == 0 )
    goto LABEL_74;
  if ( (v30 & 2) == 0 )
  {
    if ( MmFlushImageSection((PSECTION_OBJECT_POINTERS)(*(_QWORD *)(v6 + 248) + 8LL), MmFlushForDelete) )
    {
      if ( (*(_DWORD *)(v6 + 152) & 2) == 0 )
        _InterlockedOr((volatile signed __int32 *)(v6 + 152), 2u);
      v12 |= 0x20u;
      v150 = v12;
      BYTE1(Status[0]) = v12;
    }
    goto LABEL_73;
  }
  v175[0] = 0;
  LOBYTE(v30) = !FcbReleases || (*((_DWORD *)FcbReleases + 1) & 1) == 0;
  v164 = v30;
  if ( (_BYTE)v30 )
  {
    pNetRoot = v155->pNetRoot;
    if ( !pNetRoot[2].pSrvCall && pNetRoot[2].Context )
    {
      IsLinkDeleteable = RefsIsLinkDeleteable(v3, v155, v175);
      v30 = IsLinkDeleteable;
      v164 = IsLinkDeleteable;
      v27 = v184;
    }
    if ( (_BYTE)v30 )
    {
      v33 = *v27;
      if ( (*v27 & 8) != 0 )
      {
        v24 |= 8u;
        LOBYTE(Status[0]) = v24;
        *v27 = v33 | 4;
      }
      v34 = 0;
      v165 = 0;
      if ( LODWORD(v26->VNetRoot) <= 1 )
      {
        v34 = RefsTryCloseSectionOnDelete((struct _IRP_CONTEXT *)v30, v26, (v24 & 8) != 0);
        v165 = v34;
        v24 |= 0x80u;
        LOBYTE(Status[0]) = v24;
        if ( !v34 )
          goto LABEL_63;
        if ( (v24 & 8) != 0 )
        {
          v24 |= 0x40u;
          LOBYTE(Status[0]) = v24;
          v165 = 0;
          goto LABEL_63;
        }
      }
      if ( !v34 )
      {
LABEL_63:
        if ( FcbReleases && (*((_DWORD *)FcbReleases + 1) & 2) == 0 )
          --LODWORD(v26->VNetRoot);
        *((_DWORD *)FcbReleases + 1) |= 1u;
        v12 |= 0x20u;
        v150 = v12;
        BYTE1(Status[0]) = v12;
        v35 = v26->pNetRoot;
        if ( !v35[2].pSrvCall && v35[2].Context )
          FsRtlNotifyFilterChangeDirectory(
            *((PNOTIFY_SYNC *)v156 + 108),
            (PLIST_ENTRY)v156 + 53,
            *p_FsContext,
            0,
            0,
            0,
            0,
            0,
            0,
            0,
            0);
      }
    }
  }
LABEL_73:
  *v180 &= ~0x40000u;
  v26 = v155;
LABEL_74:
  if ( (v12 & 0x20) == 0
    || ((v30 = *(unsigned __int16 *)(v6 + 216), (_WORD)v30 != 128) && (_WORD)v30 != 176
     || *(_WORD *)v6 != 2053
     || *(_QWORD *)(*(_QWORD *)(v6 + 144) + 72LL) == v6)
    && ((_WORD)v30 != 160
     || *(_WORD *)(v6 + 224) != 8
     || memcmp(*(const void **)(v6 + 232), RefsFileNameIndex.Buffer, 8u)
     || (v30 = 2051, (unsigned __int16)(*(_WORD *)v6 - 2051) > 1u))
    || (Status[1] = FsRtlCheckOplockEx(
                      (POPLOCK)(v6 + 88),
                      Irp,
                      0x20u,
                      v3,
                      RefsOplockComplete,
                      RefsCleanupOplockPrePostIrp),
        Status[1] != 259) )
  {
    if ( LODWORD(v26->VNetRoot) || LODWORD(v26->spacer.PagingIoResource) != 1 )
    {
      v29 = v152;
      if ( (*(_DWORD *)(v6 + 152) & 2) != 0 && *(_DWORD *)(v6 + 160) == 1 )
      {
        v12 |= 2u;
        v150 = v12;
        BYTE1(Status[0]) = v12;
      }
    }
    else
    {
      v24 |= 0x10u;
      LOBYTE(Status[0]) = v24;
      if ( v24 >= 0 && (v24 & 8) != 0 )
      {
        v24 |= 0x80u;
        LOBYTE(Status[0]) = v24;
        v37 = RefsTryCloseSectionOnDelete((struct _IRP_CONTEXT *)v30, v26, (v24 & 8) != 0);
        v29 = v152;
        if ( v37 )
        {
          v24 |= 0x40u;
          LOBYTE(Status[0]) = v24;
        }
      }
      else
      {
        v29 = v152;
      }
    }
LABEL_101:
    if ( v160 != 2 )
    {
      if ( v160 != 3 )
      {
        if ( v160 != 4 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_19f8fd460e213a7a43a7f3710d090bd3_Traceguids, v160);
          }
          KeBugCheckEx(0x149u, 0x70B4Cu, v160, 0, 0);
        }
        v38 = FileObject;
        FileObject->Flags |= 0x4000u;
        v39 = v156;
        if ( *((PFILE_OBJECT *)v156 + 110) == v38 )
        {
          v40 = *((_QWORD *)v156 + 9);
          if ( v40 )
          {
            RefsAcquireExclusiveFcb(v3, *(_QWORD *)(v40 + 136), *((_QWORD *)v156 + 9), 0);
            *((_QWORD *)v156 + 732) = 0x7FFFFFFFFFFFFFFFLL;
            *((_QWORD *)v39 + 733) = 0;
            *((_QWORD *)v39 + 110) = 0;
            RefsReleaseFcb(v3, *(struct _FCB **)(*((_QWORD *)v39 + 9) + 136LL));
            v38 = FileObject;
          }
        }
        if ( (*(_DWORD *)v162 & 2) != 0 )
        {
          v177 = (_QWORD *)((char *)v39 + 872);
          v41 = *((_QWORD *)v39 + 109);
          if ( (PFILE_OBJECT)(v41 & 0xFFFFFFFFFFFFFFFEuLL) == v38 )
          {
            if ( (v41 & 1) != 0 )
            {
              RefsSendBeginDismountEvent(v3, v156, v38, 3);
              v39 = v156;
              RefsPerformDismountOnVcb((__int64)v3, (__int64)v156, 1, 0, 3, 0);
            }
            else if ( (v38->Flags & 0x1000) != 0 )
            {
              if ( (v152 & 4) != 0 && (v152 & 8) == 0 && (*v154 & 1) == 0 )
              {
                RefsReleaseScbWithPaging(v3, (struct _SCB *)v6);
                if ( RefsUseFlushVolumeParallel )
                  RefsFlushVolumeParallel(v3, v39, 12);
                else
                  RefsFlushVolumeOriginal(v3, v39, 12);
                RefsAcquireExclusiveFcb(v3, *(_QWORD *)(v6 + 136), v6, 0);
              }
              if ( *((_DWORD *)v39 + 54) == 1 && *((_DWORD *)v39 + 55) - *((_DWORD *)v39 + 57) == 1 )
              {
                RefsSendBeginDismountEvent(v3, v156, v38, 3);
                RefsReleaseScbWithPaging(v3, (struct _SCB *)v6);
                if ( RefsUseFlushVolumeParallel )
                  RefsFlushVolumeParallel(v3, v156, 144);
                else
                  RefsFlushVolumeOriginal(v3, v156, 144);
                RefsAcquireExclusiveFcb(v3, *(_QWORD *)(v6 + 136), v6, 0);
                v39 = v156;
                RefsPerformDismountOnVcb((__int64)v3, (__int64)v156, 1, 0, 3, 0);
                v42 = v153;
                v43 = v154;
                goto LABEL_131;
              }
            }
            v43 = v154;
            v42 = v153;
LABEL_131:
            *(_DWORD *)v162 &= 0xFFFF7FFD;
            *v177 = 0;
            LOBYTE(v42) = v42 | 1;
            v153 = v42;
            BYTE2(Status[0]) = v42;
            if ( (v42 & 4) != 0
              && (v42 & 8) == 0
              && (*v43 & 1) == 0
              && !Status[1]
              && *((_DWORD *)v39 + 301) == -1073741202 )
            {
              *((_DWORD *)v39 + 301) = 0;
              RefsPostSpecial(
                v3,
                v39,
                (void (*)(struct _IRP_CONTEXT *, void *))RefsDeleteUsnSpecial,
                (char *)v39 + 1192,
                1u,
                0);
              v162 = 4;
              v44 = v155;
              v42 = v153;
              v45 = Status[1];
              v46 = v154;
              goto LABEL_177;
            }
            v162 = 4;
            v44 = v155;
            v45 = Status[1];
            goto LABEL_176;
          }
          goto LABEL_174;
        }
        goto LABEL_340;
      }
      RefsSnapshotScb(v3, v6, 0);
      v47 = *(_WORD *)(v6 + 216);
      if ( (v47 == 128 || v47 == 176) && *(_WORD *)v6 == 2053 && *(_QWORD *)(*(_QWORD *)(v6 + 144) + 72LL) != v6
        || v47 == 160
        && *(_WORD *)(v6 + 224) == 8
        && !memcmp(*(const void **)(v6 + 232), RefsFileNameIndex.Buffer, 8u)
        && (unsigned __int16)(*(_WORD *)v6 - 2051) <= 1u )
      {
        FsRtlCheckOplock((POPLOCK)(v6 + 88), Irp, 0, 0, 0);
      }
      v48 = FileObject;
      FileObject->Flags |= 0x4000u;
      v49 = v180;
      if ( (*v180 & 0x800000) != 0 )
      {
        FsRtlNotifyCleanup(*((PNOTIFY_SYNC *)v156 + 108), (PLIST_ENTRY)v156 + 53, FsContext);
        *v49 &= ~0x800000u;
        _InterlockedDecrement((volatile signed __int32 *)v156 + 354);
        v48 = FileObject;
      }
      v46 = v154;
      if ( (v152 & 4) == 0 || (v152 & 8) != 0 || (*v154 & 1) != 0 )
      {
LABEL_339:
        v44 = v155;
LABEL_342:
        v162 = 4;
        v12 = v150;
        v42 = v153;
        v45 = Status[1];
        goto LABEL_177;
      }
      RefsUpdateScbFromFileObject(v48, (struct _SCB *)v6, 1u);
      if ( *(_WORD *)v6 == 2051 )
      {
        if ( (v24 & 0x10) == 0 || (v24 & 0x40) != 0 )
        {
          if ( (*(_DWORD *)v177 & 4) != 0 )
          {
            if ( RefsHardlinksSupported(*((struct _VCB **)v3 + 8)) )
            {
              if ( FcbReleases )
              {
                v56 = *((_DWORD *)FcbReleases + 1);
                if ( (v56 & 1) != 0 && (v56 & 2) == 0 )
                {
                  v44 = v155;
                  RefsPosixDeleteLink(v3, v155, (__int64)FsContext, (__int64)InternalSrvOpen, (__int64)Status);
                  v162 = 4;
                  v42 = BYTE2(Status[0]);
                  v153 = BYTE2(Status[0]);
                  v12 = BYTE1(Status[0]);
                  v150 = BYTE1(Status[0]);
                  v24 = Status[0];
                  v45 = Status[1];
                  goto LABEL_176;
                }
              }
            }
          }
          v44 = v155;
          if ( HIDWORD(v155->spacer.PagingIoResource) == 1
            && (v24 & 1) != 0
            && *((_DWORD *)v156 + 888) <= RefsMaxDelayedCloseCount
            && (*(_DWORD *)(v6 + 152) & 0x1000000) == 0 )
          {
            v46 = v154;
            if ( (*(_DWORD *)(v6 + 152) & 0x200000) == 0 )
            {
              _InterlockedOr((volatile signed __int32 *)(v6 + 152), 0x200000u);
              v162 = 4;
              v42 = v153;
              v45 = Status[1];
              goto LABEL_177;
            }
            goto LABEL_342;
          }
          goto LABEL_341;
        }
        if ( !FcbReleases )
        {
          LODWORD(v182) = 0;
          QuadPart = (struct _FCB *)v155->Header.FileSize.QuadPart;
          v181 = (struct _CC_FILE_SIZES *)QuadPart;
          while ( QuadPart != (struct _FCB *)&v155->spacer.FileSize )
          {
            FcbReleases = (struct _LCB *)QuadPart[-1].FcbReleases;
            if ( (QuadPart[-1].FcbReleases[1] & 2) == 0 )
              goto LABEL_161;
            QuadPart = *(struct _FCB **)&QuadPart->Header.NodeTypeCode;
          }
          FcbReleases = 0;
LABEL_161:
          v163 = FcbReleases;
          if ( FcbReleases )
            InternalSrvOpen = (struct IndexSCB *)*((_QWORD *)FcbReleases + 3);
        }
        if ( RefsIsTransactionActive(v3) )
          RefsCheckpointCurrentTransaction(v51);
        if ( InternalSrvOpen )
        {
          RefsAcquireExclusiveScb(v3, InternalSrvOpen, 0);
          v52 = v153;
          LOBYTE(v52) = v153 | 0x80;
          v153 = v52;
          BYTE2(Status[0]) = v52;
        }
        RefsDeleteFile(v3, v155, InternalSrvOpen, 0, 0);
        v12 = v150;
        v46 = v154;
        if ( !Status[1] )
        {
          if ( (v150 & 0x10) == 0 )
          {
            if ( InternalSrvOpen )
              v53 = (struct _FCB *)*((_QWORD *)InternalSrvOpen + 17);
            else
              v53 = 0;
            RefsReportDirNotify(
              v156,
              v156,
              (struct _UNICODE_STRING *)FsContext + 1,
              *((unsigned __int16 *)FsContext + 16),
              0,
              0,
              2u,
              2u,
              v53);
            v12 = v150;
          }
          *v180 &= 0xFFFFFF8F;
LABEL_174:
          v162 = 4;
          v44 = v155;
          v45 = Status[1];
LABEL_175:
          v42 = v153;
LABEL_176:
          v46 = v154;
          goto LABEL_177;
        }
        goto LABEL_339;
      }
LABEL_340:
      v44 = v155;
LABEL_341:
      v46 = v154;
      goto LABEL_342;
    }
    v162 = v6 + 152;
    if ( (*(_DWORD *)(v6 + 152) & 0x20) == 0
      && (v29 & 4) != 0
      && (v29 & 8) == 0
      && (*(_BYTE *)(*(_QWORD *)(v6 + 136) + 8LL) & 1) == 0 )
    {
      RefsUpdateScbFromAttribute(v3, (struct _SCB *)v6, 0);
    }
    v182 = (_DWORD *)v162;
    RefsSnapshotScb(v3, v6, 0);
    v184 = (int *)(v6 + 216);
    v57 = *(_WORD *)(v6 + 216);
    if ( (v57 == 128 || v57 == 176) && *(_WORD *)v6 == 2053 && *(_QWORD *)(*(_QWORD *)(v6 + 144) + 72LL) != v6
      || v57 == 160
      && *(_WORD *)(v6 + 224) == 8
      && !memcmp(*(const void **)(v6 + 232), RefsFileNameIndex.Buffer, 8u)
      && (unsigned __int16)(*(_WORD *)v6 - 2051) <= 1u )
    {
      FsRtlCheckOplock((POPLOCK)(v6 + 88), Irp, 0, 0, 0);
    }
    if ( *(_WORD *)v6 == 2053 && *(_QWORD *)(v6 + 384) )
    {
      RequestorProcess = IoGetRequestorProcess(Irp);
      FsRtlFastUnlockAll(*(PFILE_LOCK *)(v6 + 384), FileObject, RequestorProcess, 0);
    }
    p_FsContext = *(PVOID **)(v6 + 144);
    if ( ((_DWORD)p_FsContext[3] & 0x4000005) == 1
      && *(_WORD *)v6 == 2053
      && (*(_DWORD *)(v6 + 300) & 0x40) == 0
      && *(char *)(*(_QWORD *)(v6 + 136) + 8LL) >= 0 )
    {
      if ( (*(_DWORD *)v162 & 0x20) == 0 )
        goto LABEL_222;
      if ( FsRtlOplockIsFastIoPossible((POPLOCK)(v6 + 88)) )
      {
        if ( *(__int16 *)(v6 + 256) >= 0 )
        {
          v59 = *(_QWORD *)(v6 + 384);
          if ( (!v59 || !*(_BYTE *)(v59 + 16))
            && ((_DWORD)p_FsContext[3] & 0x2000000) == 0
            && (*(_BYTE *)(*(_QWORD *)(v6 + 136) + 8LL) & 0x20) == 0 )
          {
            v60 = 1;
LABEL_224:
            *(_BYTE *)(v6 + 5) = v60;
            v61 = v152;
            v46 = v154;
            if ( (v152 & 4) == 0 || (v152 & 8) != 0 || (*v154 & 1) != 0 )
            {
              v38 = FileObject;
              FileObject->Flags |= 0x4000u;
              if ( (v61 & 4) == 0 || (*v46 & 1) != 0 || (*(_DWORD *)(v6 + 300) & 0x40) != 0 )
              {
                v42 = v153;
                LOBYTE(v42) = v153 | 0x20;
                v153 = v42;
                BYTE2(Status[0]) = v42;
                v162 = 4;
                v44 = v155;
                v45 = Status[1];
              }
              else
              {
                v162 = 4;
                v44 = v155;
                v42 = v153;
                v45 = Status[1];
              }
              goto LABEL_177;
            }
            RefsUpdateScbFromFileObject(FileObject, (struct _SCB *)v6, 1u);
            v38 = FileObject;
            FileObject->Flags |= 0x4000u;
            v62 = Status[1];
            if ( Status[1] )
              goto LABEL_340;
            v167 = 0;
            if ( (v24 & 0x40) == 0
              && (!FcbReleases || (*((_DWORD *)FcbReleases + 1) & 1) != 0 && *((_DWORD *)FcbReleases + 26) == 1) )
            {
              if ( (v24 & 0x10) != 0 )
              {
                v63 = v24 & 0xFE;
                LOBYTE(Status[0]) = v63;
                if ( (*(_DWORD *)v154 & 0x8000LL) != 0 )
                {
                  RefsPostSpecial(
                    v3,
                    v156,
                    (void (*)(struct _IRP_CONTEXT *, void *))RefsDeleteUsnSpecial,
                    (char *)v156 + 1192,
                    1u,
                    0);
                  v24 = v63 & 0xEF;
                  LOBYTE(Status[0]) = v24;
                  ++LODWORD(v26->VNetRoot);
                  if ( FcbReleases )
                  {
                    *((_DWORD *)FcbReleases + 1) &= 0xFFFFFFBE;
                  }
                  else
                  {
                    while ( 1 )
                    {
                      LODWORD(p_FsContext) = 0;
                      p_FileSize = &v26->Header.FileSize;
                      if ( FcbReleases )
                      {
                        v187 = (LARGE_INTEGER *)((char *)FcbReleases + 32);
                        v65 = (LARGE_INTEGER *)*((_QWORD *)FcbReleases + 4);
                        v187 = v65;
                        v192 = (LONGLONG *)v65;
                      }
                      else
                      {
                        v65 = (LARGE_INTEGER *)p_FileSize->QuadPart;
                        v193 = (_QWORD *)p_FileSize->QuadPart;
                      }
                      while ( v65 != p_FileSize )
                      {
                        FcbReleases = (struct _LCB *)&v65[-4];
                        if ( (v65[-4].HighPart & 2) == 0 )
                          goto LABEL_243;
                        v65 = (LARGE_INTEGER *)v65->QuadPart;
                      }
                      FcbReleases = 0;
LABEL_243:
                      v163 = FcbReleases;
                      if ( !FcbReleases )
                        break;
                      *((_DWORD *)FcbReleases + 1) &= 0xFFFFFFBE;
                    }
                  }
                  goto LABEL_269;
                }
                v62 = RefsCompleteFileDeletion(
                        v3,
                        v26,
                        (struct _SCB *)v6,
                        (struct _CCB *)FsContext,
                        &InternalSrvOpen,
                        &v163,
                        (struct REFS_CLEANUP_FLAGS *)Status);
                Status[1] = v62;
                FcbReleases = v163;
LABEL_246:
                v66 = BYTE2(Status[0]);
                v153 = BYTE2(Status[0]);
                v12 = BYTE1(Status[0]);
                v150 = BYTE1(Status[0]);
                v24 = Status[0];
LABEL_271:
                v177 = (_QWORD *)(v6 + 160);
                if ( *(_DWORD *)(v6 + 160) == 1 )
                {
                  v81 = v155;
                  if ( LODWORD(v155->VNetRoot) )
                  {
                    if ( !v62 )
                    {
                      v82 = 0;
                      v166 = 0;
                      if ( (v12 & 2) != 0 )
                      {
                        if ( *(_WORD *)v184 )
                        {
                          v82 = RefsDeleteResidentDataScbAndCommit(v3, (struct _SCB *)v6, (unsigned __int8)v38);
                          v166 = v82;
                          v81 = v155;
                          v62 = Status[1];
                        }
                        if ( v82 )
                        {
                          if ( !v62 )
                          {
                            v24 |= 4u;
                            LOBYTE(Status[0]) = v24;
                          }
                          LOBYTE(v66) = v66 | 0x20;
                          v153 = v66;
                          BYTE2(Status[0]) = v66;
                          RefsUpdateFileTimestampsForChange(v81, FsContext, 0x400000, 0);
                          v83 = FileObject;
                          FileObject->Flags &= ~0x4000u;
                          RefsUpdateScbFromFileObject(v83, (struct _SCB *)v6, 1u);
                          v83->Flags |= 0x4000u;
                          v85 = *(char **)(v6 + 368);
                          v187 = (LARGE_INTEGER *)v85;
                          if ( v85 )
                          {
                            v189 = v85;
                            if ( *((_DWORD *)v85 + 41) == 1 )
                              RefsDeleteResidentDataScbAndCommit(v3, (struct _SCB *)v85, v84);
                            LOBYTE(WatchTree) = 0;
                            RefsDecrementCloseCounts(v3, v85, 0, 0, WatchTree, 0);
                          }
                        }
                      }
                      else if ( *(_WORD *)v184 )
                      {
                        if ( (*v182 & 4) != 0 )
                        {
                          if ( (v12 & 0x40) == 0 && (*(_DWORD *)v154 & 0x100LL) == 0 )
                            RefsPrepareForUpdateDuplicate(v3, v155, &v179, &InternalSrvOpen, 1u, 0);
                          RefsWriteFileSizes(v3, (struct _SCB *)v6, 0, 2u, WatchTree);
                          RefsCheckpointCurrentTransaction(v3);
                          v86 = FileObject;
                          FileObject->Flags &= ~0x4000u;
                          RefsUpdateScbFromFileObject(v86, (struct _SCB *)v6, 1u);
                          v86->Flags |= 0x4000u;
                        }
                        if ( (*v182 & 0x40) != 0 )
                        {
                          v162 = 4;
                          RefsWriteFileSizes(v3, (struct _SCB *)v6, 0, 4u, WatchTree);
                          RefsCheckpointCurrentTransaction(v3);
                          v44 = v155;
                          v87 = FileObject;
                          v38 = (PFILE_OBJECT)v154;
                          goto LABEL_293;
                        }
                      }
                    }
                  }
                }
                v38 = (PFILE_OBJECT)v154;
                v87 = FileObject;
                v44 = v155;
                v162 = 4;
LABEL_293:
                v88 = Status[1];
                if ( !Status[1]
                  && *(_DWORD *)v177 == 1
                  && LODWORD(v44->VNetRoot)
                  && (v12 & 2) == 0
                  && v87->SectionObjectPointer == (PSECTION_OBJECT_POINTERS)(*(_QWORD *)(v6 + 248) + 8LL)
                  && *(_WORD *)v184
                  && (*v182 & 1) != 0 )
                {
                  v12 |= 0x80u;
                  v150 = v12;
                  BYTE1(Status[0]) = v12;
                  if ( (v12 & 0x40) == 0 && (*(_DWORD *)&v38->Type & 0x100LL) == 0 )
                    RefsPrepareForUpdateDuplicate(v3, v44, &v179, &InternalSrvOpen, 1u, 0);
                  if ( *(_WORD *)v6 == 2053 && *(_QWORD *)(v6 + 432) )
                  {
                    AllocationSize = v181[1].AllocationSize;
                    if ( AllocationSize.QuadPart )
                    {
                      v91 = *((unsigned int *)v156 + 136);
                      v92 = (v91 + *(_QWORD *)(v6 + 32)) >> *((_BYTE *)v156 + 552);
                      if ( (AllocationSize.QuadPart + v91) >> *((_BYTE *)v156 + 552) != v92 )
                      {
                        RefsDeleteAllocation(
                          v3,
                          (struct _SCB *)v6,
                          v92,
                          0x7FFFFFFFFFFFFFFFLL,
                          *(_WORD *)(v6 + 256) >= 0);
                        RefsCheckpointCurrentTransaction(v3);
                        *(_QWORD *)v154 |= 0x40000uLL;
                      }
                      v93 = v153;
                      LOBYTE(v93) = v153 | 0x40;
                      v153 = v93;
                      BYTE2(Status[0]) = v93;
                    }
                  }
                  else
                  {
                    v94 = (*(_DWORD *)(v6 + 32) + 7) & 0xFFFFFFF8;
                    if ( v94 < v181[1].AllocationSize.LowPart )
                    {
                      v191 = v181[1];
                      v191.AllocationSize.LowPart = v94;
                      RefsWriteFileSizes(v3, (struct _SCB *)v6, &v191, 1u, WatchTree);
                      RefsCheckpointCurrentTransaction(v3);
                      v181[1].AllocationSize.LowPart = v191.AllocationSize.LowPart;
                    }
                  }
                  RefsUpdateScbFromFileObject(FileObject, (struct _SCB *)v6, 1u);
                  v88 = Status[1];
                }
                v95 = *(_DWORD *)(v6 + 156);
                if ( v95 )
                {
                  if ( *(_DWORD *)v177 == v95 + 1
                    && *(__int16 *)(v6 + 256) >= 0
                    && (*((_BYTE *)FsContext + 88) & 7) != 0 )
                  {
                    v96 = *(_QWORD *)(v6 + 248);
                    if ( *(_QWORD *)(v96 + 8) )
                    {
                      if ( !*(_QWORD *)(v96 + 24)
                        && (FileObject->Flags & 8) == 0
                        && !v88
                        && MmCanFileBeTruncated((PSECTION_OBJECT_POINTERS)(*(_QWORD *)(v6 + 248) + 8LL), 0)
                        && (*(_DWORD *)(*(_QWORD *)(v6 + 136) + 8LL) & 0x100LL) == 0
                        && (v12 & 0x40) == 0 )
                      {
                        RefsCheckpointCurrentTransaction(v3);
                        v24 |= 4u;
                        LOBYTE(Status[0]) = v24;
                        if ( (v153 & 0x80u) != 0LL )
                        {
                          RefsReleaseFcb(v3, *((struct _FCB **)InternalSrvOpen + 17));
                          v97 = v153;
                          LOBYTE(v97) = v153 & 0x7F;
                          v153 = v97;
                          BYTE2(Status[0]) = v97;
                        }
                        if ( *((_QWORD *)v3 + 6) )
                          RefsReleaseSharedResources(v3);
                        RefsFlushAndPurgeScb(v3, (struct _SCB *)v6);
                        *((_DWORD *)v3 + 4) = 0;
                      }
                    }
                  }
                }
                v45 = Status[1];
                if ( Status[1]
                  || HIDWORD(v44->spacer.PagingIoResource) != 1
                  || (v24 & 1) == 0
                  || *((_DWORD *)v156 + 888) > RefsMaxDelayedCloseCount )
                {
                  goto LABEL_175;
                }
                v46 = v154;
                if ( (*v154 & 4) != 0 || (*v182 & 0x1000000) != 0 )
                {
                  v42 = v153;
                }
                else
                {
                  v42 = v153;
                  if ( (*(_DWORD *)(v6 + 152) & 0x200000) == 0 )
                    _InterlockedOr((volatile signed __int32 *)(v6 + 152), 0x200000u);
                }
LABEL_177:
                if ( v161 == 4 )
                  goto LABEL_453;
                NonPaged = v44->NonPaged;
                if ( *((PNON_PAGED_FCB *)&v44->1 + 16) != NonPaged )
                {
                  v55 = *(struct _IRP_CONTEXT **)v46;
                  if ( (*(_QWORD *)v46 & 0x10) != 0 )
                  {
                    *((_QWORD *)&v44->1 + 16) = NonPaged;
LABEL_352:
                    *((_DWORD *)&v44->1 + 43) |= 0x20u;
                    goto LABEL_353;
                  }
                  if ( ((unsigned __int8)v55 & 1) == 0 && RefsCheckLastAccess(v55, v44) )
                  {
                    *(_QWORD *)v46 = v98 | 0x10;
                    *v180 |= 0x10000u;
                    v44 = v155;
                    goto LABEL_352;
                  }
                }
LABEL_353:
                if ( (v42 & 4) == 0 || (v42 & 8) != 0 || (*(_QWORD *)v46 & 1) != 0 )
                {
LABEL_415:
                  if ( (v42 & 0x80u) != 0LL && (v12 & 0x40) == 0 )
                  {
                    RefsReleaseFcb(v3, *((struct _FCB **)InternalSrvOpen + 17));
                    v42 = v153;
                    LOBYTE(v42) = v153 & 0x7F;
                    v153 = v42;
                    BYTE2(Status[0]) = v42;
                  }
                  if ( FileObject->PrivateCacheMap > (PVOID)1
                    || (v42 & 0x20) != 0
                    || (v42 & 0x40) != 0
                    || (v24 & 0x40) != 0 && FileObject->SectionObjectPointer )
                  {
                    v177 = 0;
                    if ( (v42 & 0x40) != 0 )
                      v177 = *(_QWORD **)(v6 + 32);
                    v113 = (const __int64 *)&v177;
                    if ( (v42 & 0x20) == 0 )
                      v113 = 0;
                    RefsUninitializeCacheMap(FileObject, v113, (struct _CACHE_UNINITIALIZE_EVENT *)v38);
                  }
                  if ( (*v154 & 1) == 0 )
                  {
                    v114 = *(_QWORD *)&v44->FcbTableEntry.Path.Length;
                    if ( v114 )
                    {
                      if ( LODWORD(v44->spacer.PagingIoResource) == 1
                        && !Status[1]
                        && (*(_DWORD *)(v114 + 104) || *((struct _FCB **)v3 + 76) == v44 && *((_DWORD *)v3 + 154)) )
                      {
                        for ( i = (struct _FCB *)v44->Header.FastMutex;
                              i != (struct _FCB *)&v44->spacer.FastMutex;
                              i = *(struct _FCB **)&i->Header.NodeTypeCode )
                        {
                          if ( (*(_BYTE *)(&i[-1].FileLock.LockRequestsInProgress + 1) & 0x20) != 0
                            && (i->Header.FileSize.LowPart & 0x40000) != 0 )
                          {
                            goto LABEL_441;
                          }
                        }
                        RefsPostUsnChange(v3, v44, 0x80000000, 0);
                      }
                    }
                  }
LABEL_441:
                  if ( *((_QWORD *)v3 + 76) && !Status[1] )
                  {
                    RefsWriteUsnJournalChanges(v3);
                    RefsCheckpointCurrentTransaction(v3);
                    v24 |= 4u;
                    LOBYTE(Status[0]) = v24;
                  }
                  v116 = 0;
                  v185 = 0;
                  if ( (*(_DWORD *)(v6 + 152) & 4) != 0 )
                  {
                    if ( *(_DWORD *)(v6 + 160) == 1 )
                      v116 = 4;
                    v185 = v116;
                  }
                  if ( v12 < 0 )
                  {
                    v116 |= 1u;
                    v185 = v116;
                  }
                  if ( v116 && (v116 & *(_DWORD *)(v6 + 152)) != 0 )
                    _InterlockedAnd((volatile signed __int32 *)(v6 + 152), ~v116);
LABEL_453:
                  if ( (*v180 & 0x8000000) != 0 )
                  {
                    if ( (v153 & 4) != 0 && (v153 & 8) == 0 && *(_WORD *)v6 == 2053 && *(_QWORD *)(v6 + 432) )
                    {
                      RefsBindMinstoreTransaction(v3);
                      MsSetContainersStationaryVolatile(
                        *((struct CmsTransactionContext **)v3 + 3),
                        *(CmsStream **)(v6 + 432));
                    }
                    *((_DWORD *)FsContext + 1) &= ~0x8000000u;
                    *(_DWORD *)(v6 + 300) &= ~2u;
                  }
                  if ( Status[1] >= 0 )
                  {
                    RefsCheckpointCurrentTransaction(v3);
                    v24 |= 4u;
                    LOBYTE(Status[0]) = v24;
                    RefsFlushForWriteThrough(v3, v6, 0);
                  }
                  v118 = FsContext;
                  *((_QWORD *)v3 + 1) &= ~0x400uLL;
                  *((_QWORD *)v3 + 1) |= 0x8000000uLL;
                  v118[1] |= 0x8000u;
                  if ( Status[1] && (v24 & 4) == 0 && ((v24 & 0x10) != 0 || (v12 & 0x40) != 0 || (v12 & 2) != 0) )
                  {
                    RefsBackoutFailedLinkRemove(v3, (__int64)Status);
                    v153 = BYTE2(Status[0]);
                    v12 = BYTE1(Status[0]);
                    v150 = BYTE1(Status[0]);
                    v24 = Status[0];
                    v118 = FsContext;
                  }
                  v119 = (unsigned __int8)v24;
                  LOBYTE(v119) = (v24 & 0x10) != 0;
                  if ( (v24 & 0x10) != 0
                    || (v12 & 0x40) != 0
                    || (v118[1] & 0x10000) != 0
                    || ((__int64)v44->spacer.Resource & 0x40000) != 0 )
                  {
                    v120 = 16;
                    v186 = 16;
                    if ( (v24 & 0x10) != 0 || (v12 & 0x40) != 0 )
                    {
                      v120 = 80;
                      v186 = 80;
                    }
                    if ( ((__int64)v44->spacer.Resource & 0x40000) != 0 )
                    {
                      v120 |= 8u;
                      v186 = v120;
                    }
                    if ( !InternalSrvOpen && v161 == 2 )
                      InternalSrvOpen = (struct IndexSCB *)v44->InternalSrvOpen;
                    if ( InternalSrvOpen )
                    {
                      FsRtlCheckOplockEx((POPLOCK)InternalSrvOpen + 11, Irp, v120, 0, 0, 0);
                      v44->Header.Resource = (PERESOURCE)((unsigned __int64)v44->Header.Resource & ~0x40000uLL);
                    }
                    v12 = v150;
                  }
                  if ( (v24 & 0x10) == 0 )
                  {
                    if ( (v12 & 0x40) == 0 )
                      goto LABEL_499;
                    if ( (v24 & 0x10) == 0 )
                    {
LABEL_500:
                      if ( (v12 & 0x40) == 0 && (v12 & 2) == 0 )
                      {
LABEL_510:
                        v127 = v153;
                        if ( (v153 & 2) != 0 && (v12 & 0x40) == 0 )
                        {
                          RefsUpdateLcbDuplicateInfo((struct _IRP_CONTEXT *)v119, v44, v179);
                          *((_DWORD *)&v44->1 + 43) = 0;
                        }
                        if ( (v127 & 0x10) != 0 )
                        {
                          v128 = *((_QWORD *)FcbReleases + 3);
                          v129 = *(struct _FAST_MUTEX **)(v128 + 48);
                          KeEnterGuardedRegion();
                          ExAcquireFastMutexUnsafe(v129);
                          _InterlockedIncrement((volatile signed __int32 *)(v128 + 172));
                          --*((_DWORD *)FcbReleases + 18);
                          ++*(_DWORD *)(v128 + 172);
                          ExReleaseFastMutexUnsafe(*(PFAST_MUTEX *)(v128 + 48));
                          KeLeaveGuardedRegion();
                          v130 = v153;
                          LOBYTE(v130) = v153 & 0xEF;
                          v153 = v130;
                          BYTE2(Status[0]) = v130;
                        }
                        v131 = FsContext;
                        if ( (*((_DWORD *)FsContext + 1) & 8) != 0 )
                        {
                          v132 = 1;
                        }
                        else
                        {
                          v132 = 0;
                          if ( *((_BYTE *)FsContext + 80) == 4 )
                            v132 = 2;
                        }
                        v133 = FileObject;
                        RefsRemoveShareAccess(FileObject, v132, v6, v190);
                        RefsDecrementCleanupCounts(v3, (struct _SCB *)v6, v190, (v133->Flags >> 3) & 1);
                        FcbReleases = 0;
                        v163 = 0;
                        if ( (v24 & 0x10) != 0 )
                        {
                          v134 = (SECTION_OBJECT_POINTERS *)(*(_QWORD *)(v6 + 248) + 8LL);
                          if ( v134->DataSectionObject )
                            MmForceSectionClosed(v134, 1u);
                        }
                        v135 = v131[2];
                        if ( (v135 & 1) != 0 )
                        {
                          v131[2] = v135 & 0xFFFFFFFE;
                          --*(_DWORD *)(v6 + 180);
                        }
                        v36 = Status[1];
                        if ( Status[1] )
                        {
                          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
                            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                          {
                            WPP_SF_d(
                              WPP_GLOBAL_Control->AttachedDevice,
                              16,
                              WPP_19f8fd460e213a7a43a7f3710d090bd3_Traceguids,
                              (unsigned int)Status[1]);
                          }
                          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                            && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
                          {
                            WPP_SF_d(
                              WPP_GLOBAL_Control->AttachedDevice,
                              17,
                              WPP_19f8fd460e213a7a43a7f3710d090bd3_Traceguids,
                              0);
                          }
                          if ( (_BYTE)RefsStatusDebugEnabled )
                            RefsStatusDebug(0, 0, "Cleanup.c", 0xE3Fu);
                          v36 = 0;
                          Status[1] = 0;
                          *((_DWORD *)v3 + 4) = 0;
                        }
                        goto LABEL_536;
                      }
LABEL_502:
                      v126 = Irp;
                      Irp->IoStatus.Information = 0;
                      if ( (v24 & 0x10) != 0 )
                      {
                        v126->IoStatus.Information = 4;
                        if ( (v24 & 0x20) != 0 )
                        {
                          v162 = 36;
                          v126->IoStatus.Information = 36;
                        }
                        v119 = v162;
                      }
                      else
                      {
                        v119 = 0;
                        if ( (v12 & 0x40) != 0 )
                        {
                          Irp->IoStatus.Information = 8;
                          v119 = 8;
                        }
                      }
                      if ( (v12 & 2) != 0 )
                      {
                        v119 |= 0x10uLL;
                        Irp->IoStatus.Information = v119;
                      }
                      goto LABEL_510;
                    }
                  }
                  if ( (*((_DWORD *)v156 + 1642) & 4) != 0 && (unsigned __int8)(v161 - 2) <= 1u )
                  {
                    memset(v195, 0, sizeof(v195));
                    v121 = *(_QWORD *)(v6 + 136);
                    *(_QWORD *)&v195[8] = *(_QWORD *)(*(_QWORD *)(v121 + 88) + 256LL);
                    v122 = *(_QWORD *)(*(_QWORD *)(v121 + 88) + 248LL);
                    *(_QWORD *)v195 = v122;
                    if ( Irp )
                    {
                      ActivityIdIrp = IoGetActivityIdIrp(Irp, &v195[24]);
                      v124 = &v195[24];
                      if ( ActivityIdIrp < 0 )
                        v124 = 0;
                    }
                    else
                    {
                      ActivityIdThread = (_OWORD *)IoGetActivityIdThread(v122, v121);
                      if ( ActivityIdThread )
                      {
                        *(_OWORD *)&v195[24] = *ActivityIdThread;
                        v124 = &v195[24];
                      }
                      else
                      {
                        v124 = 0;
                      }
                    }
                    *(_QWORD *)&v195[16] = v124;
                    FsRtlHeatLogIo((char *)v156 + 6564, Irp, v195, 0, v124);
                  }
LABEL_499:
                  if ( (v24 & 0x10) != 0 )
                    goto LABEL_502;
                  goto LABEL_500;
                }
                if ( (*(_QWORD *)v46 & 0x10) != 0 && !v45 )
                {
                  RefsUpdateStandardInformation(v3, v44);
                  v42 = v153;
                  v46 = v154;
                }
                v99 = (struct _CC_FILE_SIZES *)((char *)&v44->1 + 172);
                v181 = (struct _CC_FILE_SIZES *)((char *)&v44->1 + 172);
                v38 = (PFILE_OBJECT)((char *)&v44->1 + 172);
                if ( (*((_DWORD *)&v44->1 + 43) & 0xC00000FC) != 0
                  || (*v180 & 0x10000) != 0
                  || v179 && (*((_DWORD *)v179 + 19) & 0xC00000FC) != 0 )
                {
                  v100 = Status[1];
                  if ( Status[1] )
                  {
LABEL_369:
                    if ( (v12 & 0x10) != 0 || v100 )
                      goto LABEL_412;
                    v178 = 0;
                    if ( (v42 & 2) == 0 || (v12 & 0x40) != 0 )
                    {
                      LowPart = v99->AllocationSize.LowPart;
                      if ( (LowPart & 0x100) == 0 )
                        goto LABEL_391;
                    }
                    else
                    {
                      LowPart = *(_DWORD *)&v38->Type;
                    }
                    if ( v179 )
                      v102 = *((_DWORD *)v179 + 19);
                    else
                      v102 = 0;
                    if ( ((LowPart | v102) & 0x40000000) != 0 )
                    {
                      if ( v179 )
                        v103 = ((unsigned __int16)LowPart | (unsigned __int16)*((_DWORD *)v179 + 19)) & 0x1F4 | 8;
                      else
                        v103 = LowPart & 0x1F4 | 8;
                    }
                    else
                    {
                      if ( v179 )
                        v104 = *((_DWORD *)v179 + 19);
                      else
                        LOWORD(v104) = 0;
                      v103 = ((unsigned __int16)v104 | (unsigned __int16)LowPart) & 0x1FC;
                    }
                    v178 = v103;
                    if ( v103 )
                    {
                      if ( InternalSrvOpen )
                        v105 = (struct _IRP_CONTEXT *)*((_QWORD *)InternalSrvOpen + 17);
                      else
                        v105 = 0;
                      RefsReportDirNotify(
                        v105,
                        v156,
                        (struct _UNICODE_STRING *)FsContext + 1,
                        *((unsigned __int16 *)FsContext + 16),
                        0,
                        0,
                        v103,
                        3u,
                        (struct _FCB *)v105);
                      v12 = v150;
                    }
LABEL_391:
                    v181->AllocationSize.LowPart &= ~0x100u;
                    if ( *(_WORD *)(v6 + 224) && ((v106 = *(_WORD *)(v6 + 216), v106 == 128) || v106 == 176)
                      || (v12 & 2) != 0 )
                    {
                      v107 = *(_DWORD *)(v6 + 300);
                      if ( (v107 & 0xC00) != 0 )
                      {
                        v108 = *(_DWORD *)(*(_QWORD *)v195 + 152LL);
                      }
                      else
                      {
                        v108 = *(_DWORD *)(v6 + 152);
                        if ( (v108 & 0x4000) == 0 )
                        {
LABEL_410:
                          *(_DWORD *)(v6 + 300) &= 0xFFFFF1FF;
                          v12 = v150;
                          if ( (*(_DWORD *)(v6 + 152) & 0x4000) != 0 )
                            _InterlockedAnd((volatile signed __int32 *)(v6 + 152), 0xFFFFBFFF);
                          goto LABEL_412;
                        }
                      }
                      v178 = 0;
                      if ( (v107 & 0x400) != 0 )
                      {
                        v109 = 512;
                        v178 = 512;
                        v110 = 7;
                      }
                      else
                      {
                        v111 = (v108 & 0x4000) != 0;
                        v109 = 0;
                        if ( v111 )
                          v109 = 1024;
                        v178 = v109;
                        if ( (v107 & 0x800) != 0 )
                        {
                          v109 |= 0x800u;
                          v178 = v109;
                        }
                        v110 = 8;
                      }
                      if ( InternalSrvOpen )
                        v112 = (struct _IRP_CONTEXT *)*((_QWORD *)InternalSrvOpen + 17);
                      else
                        v112 = 0;
                      RefsReportDirNotify(
                        v112,
                        v156,
                        (struct _UNICODE_STRING *)FsContext + 1,
                        *((unsigned __int16 *)FsContext + 16),
                        (struct _UNICODE_STRING *)(v6 + 224),
                        0,
                        v109,
                        v110,
                        (struct _FCB *)v112);
                      goto LABEL_410;
                    }
LABEL_412:
                    if ( !Status[1] )
                    {
                      RefsCheckpointCurrentTransaction(v3);
                      v24 |= 4u;
                      LOBYTE(Status[0]) = v24;
                      v44->Header.Resource = (PERESOURCE)((unsigned __int64)v44->Header.Resource & ~0x10uLL);
                    }
                    LOBYTE(v42) = v153;
                    goto LABEL_415;
                  }
                  if ( (*(_DWORD *)v46 & 0x100LL) == 0 )
                  {
                    if ( (v12 & 0x40) == 0 )
                    {
                      RefsCheckpointCurrentTransaction(v3);
                      RefsPrepareForUpdateDuplicate(v3, v44, &v179, &InternalSrvOpen, 1u, 0);
                      RefsUpdateDuplicateInfo(v3, v44, v179, InternalSrvOpen);
                      v42 = v153;
                      v99 = v181;
                      v38 = (PFILE_OBJECT)v181;
                    }
                    LOBYTE(v42) = v42 | 2;
                    v153 = v42;
                    BYTE2(Status[0]) = v42;
                  }
                }
                v100 = Status[1];
                goto LABEL_369;
              }
              if ( !FcbReleases )
              {
LABEL_270:
                v66 = v153;
                goto LABEL_271;
              }
              v67 = v12 | 0x40;
              v150 = v67;
              BYTE1(Status[0]) = v67;
              if ( HIDWORD(v26->VNetRoot) > 1 )
              {
                RefsAcquireExclusiveScb(v3, InternalSrvOpen, 0);
                v68 = v153;
                LOBYTE(v68) = v153 | 0x80;
                v153 = v68;
                BYTE2(Status[0]) = v68;
                v69 = &v26->InternalSrvOpen->0;
                if ( v69 == (_QWORD *)InternalSrvOpen )
                  goto LABEL_253;
                v70 = 5;
                if ( (*((_DWORD *)v3 + 2) & 0x100LL) == 0 )
                  v70 = 3;
                if ( (unsigned __int8)RefsAcquireExclusiveFcb(v3, v69[17], v26->InternalSrvOpen, v70) )
                {
LABEL_253:
                  v72 = v24 & 0xFE;
                  LOBYTE(Status[0]) = v72;
                  v73 = *(_QWORD *)((char *)FcbReleases + 148);
                  v188 = 0;
                  v74 = *((_DWORD *)FcbReleases + 35);
                  LODWORD(v162) = v74 - 4;
                  v188.MaximumLength = v74 - 4;
                  v188.Length = v74 - 4;
                  v188.Buffer = (PWSTR)(v73 + 4);
                  v194 = v188;
                  v75 = InternalSrvOpen;
                  RefsRemoveLink(v3, v155, InternalSrvOpen, &v194);
                  RefsConvertToStandardInfoLinkCount(v3, v155, (unsigned int)(HIDWORD(v155->VNetRoot) - 1), 0);
                  v76 = v155;
                  RefsPostUsnChange(v3, v155, 0x80010000, (struct _LCB *)((char *)FcbReleases + 120));
                  RefsCheckpointCurrentTransaction(v3);
                  --HIDWORD(v155->VNetRoot);
                  v24 = v72 | 4;
                  LOBYTE(Status[0]) = v24;
                  RefsRemovePrefixHashEntry(FcbReleases);
                  *((_DWORD *)FcbReleases + 1) &= ~0x40u;
                  *((_DWORD *)FcbReleases + 1) |= 2u;
                  *((_DWORD *)FcbReleases + 19) = 0;
                  *(_QWORD *)v154 &= ~0x4000uLL;
                  RefsUpdateFcbTimestamps(*((_QWORD *)v75 + 17), FsContext, 2684354576LL);
                  v12 = v150;
                  if ( (v150 & 0x10) == 0 && !Status[1] )
                  {
                    if ( InternalSrvOpen )
                      v78 = (struct _FCB *)*((_QWORD *)InternalSrvOpen + 17);
                    else
                      v78 = 0;
                    RefsReportDirNotify(v156, v156, v77 + 1, v77[2].Length, 0, 0, 1u, 2u, v78);
                    v12 = v150;
                  }
                  v179 = 0;
                  if ( Status[1] >= 0 )
                    RefsUpdateFileTimestampsForChange(v76, FsContext, 0, 0);
                  v79 = FileObject;
                  FileObject->Flags &= ~0x4000u;
                  RefsUpdateScbFromFileObject(v79, (struct _SCB *)v6, 1u);
                  v79->Flags |= 0x4000u;
LABEL_269:
                  v62 = Status[1];
                  goto LABEL_270;
                }
LABEL_588:
                *((_QWORD *)v3 + 1) |= 0x100uLL;
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                  && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                {
                  WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_19f8fd460e213a7a43a7f3710d090bd3_Traceguids);
                }
                if ( (_BYTE)RefsStatusDebugEnabled )
                  RefsStatusDebug(-1073741608, v3, "Cleanup.c", 0x8D4u);
                RefsRaiseStatusInternal(v3, -1073741608, v71);
                __debugbreak();
                JUMPOUT(0x1403185AFLL);
              }
              v12 = v67 & 0xBF;
              v150 = v12;
              BYTE1(Status[0]) = v12;
              *((_DWORD *)FcbReleases + 1) |= 0x40u;
            }
            v167 = 1;
            if ( (*(_DWORD *)v177 & 4) == 0 )
              goto LABEL_270;
            if ( !RefsHardlinksSupported(*((struct _VCB **)v3 + 8)) )
              goto LABEL_270;
            if ( !FcbReleases )
              goto LABEL_270;
            v80 = *((_DWORD *)FcbReleases + 1);
            if ( (v80 & 1) == 0 || (v80 & 2) != 0 )
              goto LABEL_270;
            RefsPosixDeleteLink(v3, v26, (__int64)FsContext, (__int64)InternalSrvOpen, (__int64)Status);
            v62 = 0;
            Status[1] = 0;
            goto LABEL_246;
          }
        }
LABEL_222:
        v60 = 2;
        goto LABEL_224;
      }
    }
    v60 = 0;
    goto LABEL_224;
  }
  Irp = 0;
  v3 = 0;
  v157 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_19f8fd460e213a7a43a7f3710d090bd3_Traceguids, 871);
  }
  if ( (_BYTE)RefsStatusDebugEnabled )
    RefsStatusDebug(871, 0, "Cleanup.c", 0x64Bu);
  v36 = 871;
  Status[1] = 871;
LABEL_536:
  if ( v36 != 871 )
  {
    RefsReleaseVcb(v3, v156);
    if ( (v153 & 1) != 0 )
    {
      RefsReleaseScbWithPaging(v3, (struct _SCB *)v6);
      FsRtlNotifyVolumeEvent(FileObject, 5u);
    }
  }
  v136 = v153;
  if ( (v153 & 0x10) != 0 )
  {
    v137 = *((_QWORD *)FcbReleases + 3);
    v138 = *(struct _FAST_MUTEX **)(v137 + 48);
    KeEnterGuardedRegion();
    ExAcquireFastMutexUnsafe(v138);
    _InterlockedIncrement((volatile signed __int32 *)(v137 + 172));
    --*((_DWORD *)FcbReleases + 18);
    ++*(_DWORD *)(v137 + 172);
    ExReleaseFastMutexUnsafe(*(PFAST_MUTEX *)(v137 + 48));
    KeLeaveGuardedRegion();
    v136 &= ~0x10u;
    v36 = Status[1];
  }
  if ( (v150 & 4) != 0 && v36 >= 0 && v36 != 871 && v161 != 4 && (v136 & 4) != 0 && (v136 & 8) == 0 )
  {
    v139 = (struct _UNICODE_STRING *)FsContext;
    if ( (v24 & 0x10) != 0 || (v150 & 2) != 0 || (v150 & 0x40) != 0 || (*((_WORD *)FsContext + 44) & 0x912) != 0 )
    {
      *((_DWORD *)v3 + 1) |= 0x400u;
      RefsCompleteRequest((PSECURITY_SUBJECT_CONTEXT *)v3, 0, v36);
      v141 = RefsIoCallSelf(v3, FileObject, v140);
      v142 = v141;
      if ( v141 != -1073741533 && v141 < 0 )
      {
        if ( (unsigned int)(v141 + 1073741662) > 1
          && v141 != -1073741643
          && (unsigned int)(v141 + 1073741806) > 2
          && v141 != -2147483626 )
        {
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
            || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
          {
            v142 = -1073700734;
          }
          else
          {
            v142 = -1073700734;
            WPP_SF_d(
              WPP_GLOBAL_Control->AttachedDevice,
              18,
              WPP_19f8fd460e213a7a43a7f3710d090bd3_Traceguids,
              3221266562LL);
          }
          if ( (_BYTE)RefsStatusDebugEnabled )
            RefsStatusDebug(-1073700734, 0, "Cleanup.c", 0xF3Fu);
        }
        v143 = v155;
        v144 = v155->pNetRoot;
        KeEnterGuardedRegion();
        ExAcquireFastMutexUnsafe((PFAST_MUTEX)&v144->pSrvCall);
        IoRaiseInformationalHardError(v142, v139 + 1, Irp->Tail.Overlay.Thread);
        ExReleaseFastMutexUnsafe((PFAST_MUTEX)&v143->pNetRoot->pSrvCall);
        KeLeaveGuardedRegion();
      }
    }
  }
  v145 = Status[1];
  if ( Status[1] != 871 )
  {
    v146 = *((_QWORD *)v3 + 1);
    if ( (v146 & 0x100000000LL) != 0 )
    {
      *((_QWORD *)v3 + 1) = v146 | 0x200000000LL;
      return v145;
    }
    RefsCompleteRequest((PSECURITY_SUBJECT_CONTEXT *)v3, Irp, Status[1]);
  }
  return v145;
}

```

## disassembly

```asm
0x140314de0  mov     [rsp+arg_10], rbx
0x140314de5  mov     [rsp+arg_18], rsi
0x140314dea  push    rdi
0x140314deb  push    r12
0x140314ded  push    r13
0x140314def  push    r14
0x140314df1  push    r15
0x140314df3  sub     rsp, 1F0h
0x140314dfa  mov     rax, cs:__security_cookie
0x140314e01  xor     rax, rsp
0x140314e04  mov     [rsp+218h+var_30], rax
0x140314e0c  mov     rax, rdx
0x140314e0f  mov     r15, rcx
0x140314e12  mov     [rsp+218h+var_188], rcx
0x140314e1a  mov     [rsp+218h+Irp], rdx
0x140314e22  xor     r13d, r13d
0x140314e25  mov     [rsp+218h+Status+4], r13d
0x140314e2a  mov     [rsp+218h+var_160], r13
0x140314e32  mov     [rsp+218h+var_148], r13
0x140314e3a  xor     edx, edx
0x140314e3c  mov     [rsp+218h+var_1A8], rdx
0x140314e41  mov     word ptr [rsp+218h+Status], dx
0x140314e46  mov     byte ptr [rsp+218h+Status], 1
0x140314e4b  mov     qword ptr [rax+38h], 2
0x140314e53  mov     rax, [rax+0B8h]
0x140314e5a  mov     r8, [rax+30h]
0x140314e5e  mov     [rsp+218h+FileObject], r8
0x140314e66  mov     [rsp+218h+var_128], r8
0x140314e6e  lea     rax, [r8+18h]
0x140314e72  mov     [rsp+218h+var_D8], rax
0x140314e7a  mov     rsi, [rax]
0x140314e7d  test    rsi, rsi
0x140314e80  jz      short loc_140314ED5
0x140314e82  mov     r10, [rsi+90h]
0x140314e89  mov     [rsp+218h+var_190], r10
0x140314e91  mov     [rsp+218h+var_140], r10
0x140314e99  mov     rcx, [r8+20h]
0x140314e9d  mov     [rsp+218h+FsContext], rcx
0x140314ea5  mov     [rsp+218h+var_150], rcx
0x140314ead  mov     rbx, [rsi+88h]
0x140314eb4  mov     [rsp+218h+var_198], rbx
0x140314ebc  mov     [rsp+218h+var_130], rbx
0x140314ec4  test    rcx, rcx
0x140314ec7  jnz     short loc_140314ECE
0x140314ec9  mov     r14b, 5
0x140314ecc  jmp     short loc_140314F11
0x140314ece  movzx   r14d, byte ptr [rcx+50h]
0x140314ed3  jmp     short loc_140314F11
0x140314ed5  mov     r10, r13
0x140314ed8  mov     [rsp+218h+var_190], r13
0x140314ee0  mov     [rsp+218h+var_140], r13
0x140314ee8  mov     rbx, r13
0x140314eeb  mov     [rsp+218h+var_198], rbx
0x140314ef3  mov     [rsp+218h+var_130], rbx
0x140314efb  mov     rcx, r13
0x140314efe  mov     [rsp+218h+FsContext], rcx
0x140314f06  mov     [rsp+218h+var_150], rcx
0x140314f0e  mov     r14b, 1
0x140314f11  mov     [rsp+218h+var_170], r14b
0x140314f19  lea     eax, [r14-1]
0x140314f1d  test    al, 0FBh
0x140314f1f  jz      loc_1403183EF
0x140314f25  lea     r12, [rcx+4]
0x140314f29  movzx   edi, byte ptr [r12]
0x140314f2e  and     dil, 8
0x140314f32  add     dil, dil
0x140314f35  movzx   eax, byte ptr [rsp+218h+Status+1]
0x140314f3a  and     al, 0EFh
0x140314f3c  or      dil, al
0x140314f3f  mov     [rsp+218h+var_1B8], dil
0x140314f44  mov     byte ptr [rsp+218h+Status+1], dil
0x140314f49  mov     eax, [rcx+54h]
0x140314f4c  mov     [r15+278h], eax
0x140314f53  cmp     r14b, 4
0x140314f57  jnz     loc_14031502D
0x140314f5d  mov     eax, [r10+18h]
0x140314f61  test    al, 2
0x140314f63  jz      short loc_140314F79
0x140314f65  mov     rax, [r10+368h]
0x140314f6c  and     rax, 0FFFFFFFFFFFFFFFEh
0x140314f70  cmp     rax, r8
0x140314f73  jz      loc_140315038
0x140314f79  mov     rax, [r15+68h]
0x140314f7d  mov     ecx, [rax+8]
0x140314f80  bt      rcx, 17h
0x140314f85  jb      short loc_140314FA2
0x140314f87  mov     r8b, 1; unsigned __int8
0x140314f8a  mov     rdx, r10; struct _VCB *
0x140314f8d  mov     rcx, r15; struct _IRP_CONTEXT *
0x140314f90  call    ?RefsAcquireSharedVcb@@YAEPEAU_IRP_CONTEXT@@PEAU_VCB@@E@Z; RefsAcquireSharedVcb(_IRP_CONTEXT *,_VCB *,uchar)
0x140314f95  mov     rdx, [rsp+218h+var_1A8]
0x140314f9a  mov     r10, [rsp+218h+var_190]
0x140314fa2  mov     rax, [rsp+218h+var_D8]
0x140314faa  mov     [rsp+218h+var_E0], rax
0x140314fb2  mov     qword ptr [rsp+218h+var_58], rsi
0x140314fba  mov     [rsp+218h+var_138], rsi
0x140314fc2  mov     [rsp+218h+var_E8], rsi
0x140314fca  mov     [rsp+218h+var_16F], r14b
0x140314fd2  mov     [rsp+218h+var_F0], r12
0x140314fda  lea     rcx, [r10+18h]
0x140314fde  mov     [rsp+218h+var_168], rcx
0x140314fe6  mov     r8d, [rcx]
0x140314fe9  mov     eax, r8d
0x140314fec  and     eax, 8000823h
0x140314ff1  cmp     eax, 1
0x140314ff4  jnz     loc_1403150A0
0x140314ffa  test    dword ptr [rsi+12Ch], 4000h
0x140315004  jnz     loc_1403150A0
0x14031500a  mov     rcx, [r10+70h]; this
0x14031500e  test    rcx, rcx
0x140315011  jz      loc_140315098
0x140315017  call    ?AreWritesDoomed@CmsVolume@@QEAAEXZ; CmsVolume::AreWritesDoomed(void)
0x14031501c  mov     rcx, [rsp+218h+var_168]
0x140315024  test    al, al
0x140315026  jnz     short loc_1403150A0
0x140315028  or      dl, 4
0x14031502b  jmp     short loc_1403150A0
0x14031502d  mov     eax, [r15+8]
0x140315031  bt      rax, 8
0x140315036  jnb     short loc_14031504B
0x140315038  mov     r8b, 1; unsigned __int8
0x14031503b  mov     rdx, r10; struct _VCB *
0x14031503e  mov     rcx, r15; struct _IRP_CONTEXT *
0x140315041  call    ?RefsAcquireExclusiveVcb@@YAEPEAU_IRP_CONTEXT@@PEAU_VCB@@E@Z; RefsAcquireExclusiveVcb(_IRP_CONTEXT *,_VCB *,uchar)
0x140315046  jmp     loc_140314F95
0x14031504b  mov     rdx, [r15+68h]
0x14031504f  mov     r8, 20000000000h
0x140315059  test    [rdx+8], r8
0x14031505d  jnz     short loc_14031506F
0x14031505f  lea     rcx, [rdx+0A0h]
0x140315066  call    MsInitializeFastResourceOwnerEntry
0x14031506b  or      [rdx+8], r8
0x14031506f  movzx   r8d, byte ptr [r15+8]
0x140315074  and     r8b, 1
0x140315078  lea     rcx, [r10+520h]
0x14031507f  add     rdx, 0A0h
0x140315086  call    ??$MsAcquireFastResourceSharedInternal@$0A@@@YAEPEAU_MS_FAST_RESOURCE@@PEAU_MS_FAST_RESOURCE_OWNER_ENTRY@@E@Z; MsAcquireFastResourceSharedInternal<0>(_MS_FAST_RESOURCE *,_MS_FAST_RESOURCE_OWNER_ENTRY *,uchar)
0x14031508b  test    al, al
0x14031508d  jz      loc_14031845C
0x140315093  jmp     loc_140314F95
0x140315098  mov     rcx, [rsp+218h+var_168]
0x1403150a0  test    r8d, 2000020h
0x1403150a7  jnz     short loc_1403150BD
0x1403150a9  lea     r14, [rbx+8]
0x1403150ad  mov     [rsp+218h+var_1A0], r14
0x1403150b2  mov     rax, [r14]
0x1403150b5  test    al, 20h
0x1403150b7  jnz     short loc_1403150BD
0x1403150b9  xor     al, al
0x1403150bb  jmp     short loc_1403150C8
0x1403150bd  lea     r14, [rbx+8]
0x1403150c1  mov     [rsp+218h+var_1A0], r14
0x1403150c6  mov     al, 8
0x1403150c8  mov     [rsp+218h+var_120], r14
0x1403150d0  and     dl, 0F7h
0x1403150d3  or      dl, al
0x1403150d5  mov     [rsp+218h+var_1A8], rdx
0x1403150da  mov     byte ptr [rsp+218h+Status+2], dl
0x1403150de  mov     [rsp+218h+var_1AC], dl
0x1403150e2  mov     eax, [rcx]
0x1403150e4  bt      eax, 1Ah
0x1403150e8  jnb     short loc_1403150F8
0x1403150ea  or      dil, 4
0x1403150ee  mov     [rsp+218h+var_1B8], dil
0x1403150f3  mov     byte ptr [rsp+218h+Status+1], dil
0x1403150f8  mov     r9d, 10h
0x1403150fe  mov     r8, rsi
0x140315101  mov     rdx, rbx
0x140315104  mov     rcx, r15
0x140315107  call    ?RefsAcquireFcbWithPaging@@YAEPEAU_IRP_CONTEXT@@PEAU_FCB@@PEAU_SCB@@W4_REFS_ACQUIRE_FLAGS@@@Z; RefsAcquireFcbWithPaging(_IRP_CONTEXT *,_FCB *,_SCB *,_REFS_ACQUIRE_FLAGS)
0x14031510c  mov     rbx, [rsp+218h+var_F0]
0x140315114  mov     ecx, [rbx]
0x140315116  test    ecx, ecx
0x140315118  jns     short loc_140315128
0x14031511a  dec     dword ptr [rsi+158h]
0x140315120  and     dword ptr [rbx], 7FFFFFFFh
0x140315126  mov     ecx, [rbx]
0x140315128  mov     r9, [rsp+218h+FsContext]
0x140315130  lea     rdx, [r9+8]
0x140315134  mov     [rsp+218h+var_D0], rdx
0x14031513c  mov     [rsp+218h+var_108], rdx
0x140315144  mov     eax, [rdx]
0x140315146  test    al, 4
0x140315148  jnz     short loc_140315157
0x14031514a  mov     eax, [r14]
0x14031514d  bt      rax, 0Bh
0x140315152  mov     r12b, 1
0x140315155  jnb     short loc_14031515A
0x140315157  mov     r12b, 9
0x14031515a  mov     byte ptr [rsp+218h+Status], r12b
0x14031515f  mov     r14, [r9+48h]
0x140315163  mov     [rsp+218h+var_160], r14
0x14031516b  mov     [rsp+218h+var_A0], r14
0x140315173  mov     [rsp+218h+var_F8], r14
0x14031517b  test    r14, r14
0x14031517e  jz      short loc_140315196
0x140315180  mov     eax, [r14+4]
0x140315184  test    al, 2
0x140315186  jnz     short loc_140315196
0x140315188  mov     rax, [r14+18h]
0x14031518c  mov     [rsp+218h+var_148], rax
0x140315194  jmp     short loc_1403151B2
0x140315196  mov     r14, r13
0x140315199  mov     [rsp+218h+var_160], r13
0x1403151a1  mov     [rsp+218h+var_F8], r13
0x1403151a9  btr     ecx, 12h
0x1403151ad  mov     rax, rbx
0x1403151b0  mov     [rbx], ecx
0x1403151b2  mov     rbx, [rsp+218h+var_198]
0x1403151ba  mov     rcx, rbx; struct _FCB *
0x1403151bd  call    ?RefsIsFileOpen@@YAEPEBU_FCB@@@Z; RefsIsFileOpen(_FCB const *)
0x1403151c2  test    al, al
0x1403151c4  jnz     short loc_1403151D2
0x1403151c6  movzx   eax, byte ptr [rbx+8]
0x1403151ca  test    al, 1
0x1403151cc  jz      loc_1403184CC
0x1403151d2  movzx   r8d, [rsp+218h+var_1AC]
0x1403151d8  test    r8b, 4
0x1403151dc  jz      loc_140315667
0x1403151e2  test    r8b, 8
0x1403151e6  jnz     loc_140315667
0x1403151ec  test    byte ptr [rbx+8], 1
0x1403151f0  jnz     loc_140315667
0x1403151f6  mov     rax, [rsp+218h+var_F0]
0x1403151fe  mov     ecx, [rax]
0x140315200  bt      ecx, 12h
0x140315204  jnb     loc_14031548F
0x14031520a  test    cl, 2
0x14031520d  jz      loc_14031543C
0x140315213  mov     [rsp+218h+var_118], 0
0x14031521b  test    r14, r14
0x14031521e  jz      short loc_14031522C
0x140315220  mov     eax, [r14+4]
0x140315224  test    al, 1
0x140315226  jz      short loc_14031522C
0x140315228  xor     cl, cl
0x14031522a  jmp     short loc_14031522E
0x14031522c  mov     cl, 1
0x14031522e  mov     [rsp+218h+var_158], cl
0x140315235  test    cl, cl
0x140315237  jz      loc_140315479
0x14031523d  mov     rax, [rbx+58h]
0x140315241  cmp     qword ptr [rax+0F8h], 0
0x140315249  jnz     loc_14031532A
0x14031524f  cmp     qword ptr [rax+100h], 0
0x140315257  jz      loc_14031532A
0x14031525d  lea     r8, [rsp+218h+var_118]; unsigned __int8 *
0x140315265  mov     rdx, rbx; struct _FCB *
0x140315268  mov     rcx, r15; struct _IRP_CONTEXT *
0x14031526b  call    ?RefsIsLinkDeleteable@@YAEPEAU_IRP_CONTEXT@@PEAU_FCB@@PEAE@Z; RefsIsLinkDeleteable(_IRP_CONTEXT *,_FCB *,uchar *)
0x140315270  movzx   ecx, al
0x140315273  mov     [rsp+218h+var_158], al
0x14031527a  mov     rdx, [rsp+218h+var_D0]
0x140315282  jmp     loc_14031532A
0x140315287  xor     cl, cl; struct _IRP_CONTEXT *
0x140315289  mov     [rsp+218h+var_158], cl
0x140315290  xor     r13d, r13d
0x140315293  mov     rax, [rsp+218h+var_128]
0x14031529b  mov     [rsp+218h+FileObject], rax
0x1403152a3  mov     rax, [rsp+218h+var_140]
0x1403152ab  mov     [rsp+218h+var_190], rax
0x1403152b3  mov     rbx, [rsp+218h+var_130]
0x1403152bb  mov     [rsp+218h+var_198], rbx
0x1403152c3  mov     rsi, [rsp+218h+var_138]
0x1403152cb  mov     rax, [rsp+218h+var_150]
0x1403152d3  mov     [rsp+218h+FsContext], rax
0x1403152db  mov     r14, [rsp+218h+var_160]
0x1403152e3  movzx   eax, byte ptr [rsp+218h+Status+2]
0x1403152e8  mov     [rsp+218h+var_1A8], rax
0x1403152ed  movzx   edi, byte ptr [rsp+218h+Status+1]
0x1403152f2  mov     [rsp+218h+var_1B8], dil
0x1403152f7  movzx   r12d, byte ptr [rsp+218h+Status]
0x1403152fd  mov     rax, [rsp+218h+var_120]
0x140315305  mov     [rsp+218h+var_1A0], rax
0x14031530a  mov     rax, [rsp+218h+var_E0]
0x140315312  mov     [rsp+218h+var_D8], rax
0x14031531a  mov     r15, [rsp+218h+var_188]
0x140315322  mov     rdx, [rsp+218h+var_D0]
0x14031532a  test    cl, cl
0x14031532c  jz      loc_140315479
0x140315332  mov     eax, [rdx]
0x140315334  test    al, 8
0x140315336  jz      short loc_140315346
0x140315338  or      r12b, 8
0x14031533c  mov     byte ptr [rsp+218h+Status], r12b
0x140315341  or      eax, 4
0x140315344  mov     [rdx], eax
0x140315346  xor     al, al
0x140315348  mov     [rsp+218h+var_157], al
0x14031534f  cmp     dword ptr [rbx+0B0h], 1
0x140315356  ja      short loc_140315399
0x140315358  movzx   r8d, r12b
0x14031535c  shr     r8b, 3
0x140315360  and     r8b, 1; bool
0x140315364  mov     rdx, rbx; struct _FCB *
0x140315367  call    ?RefsTryCloseSectionOnDelete@@YA_NAEAU_IRP_CONTEXT@@AEAU_FCB@@_N@Z; RefsTryCloseSectionOnDelete(_IRP_CONTEXT &,_FCB &,bool)
0x14031536c  mov     [rsp+218h+var_157], al
0x140315373  or      r12b, 80h
0x140315377  mov     byte ptr [rsp+218h+Status], r12b
0x14031537c  test    al, al
  ... truncated ...
```
