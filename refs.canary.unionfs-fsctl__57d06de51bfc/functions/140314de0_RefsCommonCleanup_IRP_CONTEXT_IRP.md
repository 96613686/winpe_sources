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
  __int64 v38; // r9
  PFILE_OBJECT v39; // r8
  struct _VCB *v40; // rbx
  __int64 v41; // rdx
  __int64 v42; // rcx
  __int64 v43; // r9
  _BYTE *v44; // rcx
  struct _FCB *v45; // rbx
  NTSTATUS v46; // r10d
  _BYTE *v47; // r11
  __int16 v48; // cx
  struct _FILE_OBJECT *v49; // rcx
  int *v50; // rbx
  struct _FCB *QuadPart; // rax
  struct _IRP_CONTEXT *v52; // rcx
  __int64 v53; // rax
  struct _FCB *v54; // rax
  PNON_PAGED_FCB NonPaged; // rax
  struct _IRP_CONTEXT *v56; // rcx
  int v57; // eax
  __int16 v58; // cx
  struct _KPROCESS *RequestorProcess; // rax
  __int64 v60; // rax
  char v61; // al
  char v62; // dl
  NTSTATUS v63; // edx
  char v64; // r12
  LARGE_INTEGER *p_FileSize; // rcx
  LARGE_INTEGER *v66; // rax
  __int64 v67; // rbx
  char v68; // di
  __int64 v69; // rax
  _QWORD *v70; // rdx
  __int64 v71; // r9
  unsigned int v72; // r8d
  char v73; // r12
  __int64 v74; // rcx
  int v75; // eax
  struct IndexSCB *v76; // rdi
  struct _FCB *v77; // rbx
  struct _UNICODE_STRING *v78; // rdx
  struct _FCB *v79; // rax
  PFILE_OBJECT v80; // rbx
  int v81; // eax
  struct _FCB *v82; // r10
  unsigned __int8 v83; // cl
  PFILE_OBJECT v84; // rbx
  unsigned __int8 v85; // r8
  char *v86; // rbx
  PFILE_OBJECT v87; // rbx
  PFILE_OBJECT v88; // rcx
  NTSTATUS v89; // edx
  LARGE_INTEGER AllocationSize; // rdx
  __int64 v92; // rax
  __int64 v93; // r8
  __int64 v94; // rax
  DWORD v95; // eax
  int v96; // ecx
  __int64 v97; // rax
  __int64 v98; // rax
  __int64 v99; // rcx
  struct _CC_FILE_SIZES *v100; // rdx
  NTSTATUS v101; // eax
  DWORD LowPart; // edx
  int v103; // ecx
  ULONG v104; // eax
  int v105; // ecx
  struct _IRP_CONTEXT *v106; // rcx
  __int16 v107; // ax
  int v108; // ecx
  int v109; // eax
  ULONG v110; // eax
  ULONG v111; // edx
  bool v112; // cf
  struct _IRP_CONTEXT *v113; // rcx
  const __int64 *v114; // rdx
  __int64 v115; // rax
  struct _FCB *i; // rax
  int v117; // ecx
  _DWORD *v119; // rdx
  ULONG_PTR v120; // rcx
  ULONG v121; // r8d
  __int64 v122; // rdx
  __int64 v123; // rcx
  int ActivityIdIrp; // eax
  _BYTE *v125; // rdx
  _OWORD *ActivityIdThread; // rax
  PIRP v127; // rax
  char v128; // r11
  __int64 v129; // rdi
  struct _FAST_MUTEX *v130; // rbx
  __int64 v131; // r11
  _DWORD *v132; // rdi
  unsigned int v133; // eax
  PFILE_OBJECT v134; // r14
  SECTION_OBJECT_POINTERS *v135; // rcx
  int v136; // eax
  char v137; // si
  __int64 v138; // rdi
  struct _FAST_MUTEX *v139; // rbx
  struct _UNICODE_STRING *v140; // r14
  unsigned __int8 v141; // r8
  int v142; // eax
  NTSTATUS v143; // edi
  struct _FCB *v144; // rsi
  PMRX_NET_ROOT v145; // rbx
  unsigned int v146; // ebx
  __int64 v147; // rax
  __int64 v149; // rax
  BOOLEAN WatchTree[8]; // [rsp+20h] [rbp-1F8h]
  BOOLEAN IgnoreBuffer[8]; // [rsp+28h] [rbp-1F0h]
  int CompletionFilter; // [rsp+30h] [rbp-1E8h]
  char v153; // [rsp+60h] [rbp-1B8h]
  NTSTATUS Status[2]; // [rsp+64h] [rbp-1B4h] BYREF
  char v155; // [rsp+6Ch] [rbp-1ACh]
  __int64 v156; // [rsp+70h] [rbp-1A8h]
  _BYTE *v157; // [rsp+78h] [rbp-1A0h]
  struct _FCB *v158; // [rsp+80h] [rbp-198h]
  struct _VCB *v159; // [rsp+88h] [rbp-190h]
  struct _IRP_CONTEXT *v160; // [rsp+90h] [rbp-188h]
  PVOID FsContext; // [rsp+98h] [rbp-180h]
  PFILE_OBJECT FileObject; // [rsp+A0h] [rbp-178h]
  unsigned __int8 v163; // [rsp+A8h] [rbp-170h]
  char v164; // [rsp+A9h] [rbp-16Fh]
  __int64 v165; // [rsp+B0h] [rbp-168h]
  struct _LCB *v166; // [rsp+B8h] [rbp-160h] BYREF
  char v167; // [rsp+C0h] [rbp-158h]
  bool v168; // [rsp+C1h] [rbp-157h]
  unsigned __int8 v169; // [rsp+C2h] [rbp-156h]
  char v170; // [rsp+C3h] [rbp-155h]
  char *v171; // [rsp+C8h] [rbp-150h]
  struct IndexSCB *InternalSrvOpen; // [rsp+D0h] [rbp-148h] BYREF
  struct _IRP_CONTEXT *v173; // [rsp+D8h] [rbp-140h]
  __int64 v174; // [rsp+E0h] [rbp-138h]
  struct _FCB *v175; // [rsp+E8h] [rbp-130h]
  PFILE_OBJECT v176; // [rsp+F0h] [rbp-128h]
  _DWORD *v177; // [rsp+F8h] [rbp-120h]
  unsigned __int8 v178[8]; // [rsp+100h] [rbp-118h] BYREF
  PIRP Irp; // [rsp+108h] [rbp-110h]
  _QWORD *v180; // [rsp+110h] [rbp-108h] BYREF
  int v181; // [rsp+118h] [rbp-100h]
  struct _LCB *v182; // [rsp+120h] [rbp-F8h] BYREF
  int *v183; // [rsp+128h] [rbp-F0h]
  struct _CC_FILE_SIZES *v184; // [rsp+130h] [rbp-E8h]
  _DWORD *v185; // [rsp+138h] [rbp-E0h]
  PVOID *p_FsContext; // [rsp+140h] [rbp-D8h]
  int *v187; // [rsp+148h] [rbp-D0h]
  int v188; // [rsp+150h] [rbp-C8h]
  int v189; // [rsp+154h] [rbp-C4h]
  LARGE_INTEGER *v190; // [rsp+158h] [rbp-C0h]
  struct _UNICODE_STRING v191; // [rsp+160h] [rbp-B8h]
  char *v192; // [rsp+170h] [rbp-A8h]
  struct _LCB *v193; // [rsp+178h] [rbp-A0h]
  struct _CC_FILE_SIZES v194; // [rsp+180h] [rbp-98h] BYREF
  LONGLONG *v195; // [rsp+198h] [rbp-80h]
  _QWORD *v196; // [rsp+1A0h] [rbp-78h]
  struct _UNICODE_STRING v197; // [rsp+1B0h] [rbp-68h] BYREF
  _BYTE v198[40]; // [rsp+1C0h] [rbp-58h] BYREF

  v3 = a1;
  v160 = a1;
  Irp = a2;
  Status[1] = 0;
  v166 = 0;
  InternalSrvOpen = 0;
  v4 = 0;
  v156 = 0;
  LOWORD(Status[0]) = 1;
  a2->IoStatus.Information = 2;
  v5 = a2->Tail.Overlay.CurrentStackLocation->FileObject;
  FileObject = v5;
  v176 = v5;
  p_FsContext = &v5->FsContext;
  v6 = (__int64)v5->FsContext;
  if ( v6 )
  {
    v7 = *(struct _VCB **)(v6 + 144);
    v159 = v7;
    v173 = v7;
    FsContext2 = (unsigned int *)v5->FsContext2;
    FsContext = FsContext2;
    v171 = (char *)FsContext2;
    v9 = *(struct _FCB **)(v6 + 136);
    v158 = v9;
    v175 = v9;
    if ( FsContext2 )
      v10 = *((_BYTE *)FsContext2 + 80);
    else
      v10 = 5;
  }
  else
  {
    v7 = 0;
    v159 = 0;
    v173 = 0;
    v9 = 0;
    v158 = 0;
    v175 = 0;
    FsContext2 = 0;
    FsContext = 0;
    v171 = 0;
    v10 = 1;
  }
  v163 = v10;
  if ( ((v10 - 1) & 0xFB) == 0 )
  {
    v5->Flags |= 0x4000u;
    v149 = *((_QWORD *)v3 + 1);
    if ( (v149 & 0x100000000LL) != 0 )
      *((_QWORD *)v3 + 1) = v149 | 0x200000000LL;
    else
      RefsCompleteRequest((PSECURITY_SUBJECT_CONTEXT *)v3, Irp, 0);
    return 0;
  }
  v11 = FsContext2 + 1;
  v12 = BYTE1(Status[0]) & 0xEF | (2 * (FsContext2[1] & 8));
  v153 = v12;
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
    v4 = v156;
    v7 = v159;
  }
  v185 = p_FsContext;
  *(_QWORD *)v198 = v6;
  v174 = v6;
  v184 = (struct _CC_FILE_SIZES *)v6;
  v164 = v10;
  v183 = (int *)v11;
  v13 = (_DWORD *)((char *)v7 + 24);
  v165 = (__int64)v7 + 24;
  v14 = *((_DWORD *)v7 + 6);
  if ( (v14 & 0x8000823) == 1 && (*(_DWORD *)(v6 + 300) & 0x4000) == 0 )
  {
    v15 = (CmsVolume *)*((_QWORD *)v7 + 14);
    if ( v15 )
    {
      v16 = CmsVolume::AreWritesDoomed(v15);
      v13 = (_DWORD *)v165;
      if ( !v16 )
        LOBYTE(v4) = v4 | 4;
    }
    else
    {
      v13 = (_DWORD *)v165;
    }
  }
  if ( (v14 & 0x2000020) != 0
    || (p_Resource = &v9->spacer.Resource, v157 = &v9->spacer.Resource, ((__int64)v9->Header.Resource & 0x20) != 0) )
  {
    p_Resource = &v9->spacer.Resource;
    v157 = &v9->spacer.Resource;
    v21 = 8;
  }
  else
  {
    v21 = 0;
  }
  v177 = p_Resource;
  LOBYTE(v4) = v21 | v4 & 0xF7;
  v156 = v4;
  BYTE2(Status[0]) = v4;
  v155 = v4;
  if ( (*v13 & 0x4000000) != 0 )
  {
    v12 |= 4u;
    v153 = v12;
    BYTE1(Status[0]) = v12;
  }
  RefsAcquireFcbWithPaging((__int64)v3, (__int64)v9, v6, 0x10u);
  v22 = v183;
  v23 = *v183;
  if ( *v183 < 0 )
  {
    --*(_DWORD *)(v6 + 344);
    *v22 &= ~0x80000000;
    v23 = *v22;
  }
  v187 = (int *)((char *)FsContext + 8);
  v180 = (char *)FsContext + 8;
  if ( (*((_DWORD *)FsContext + 2) & 4) != 0 || (v24 = 1, (*p_Resource & 0x800LL) != 0) )
    v24 = 9;
  LOBYTE(Status[0]) = v24;
  FcbReleases = (struct _LCB *)*((_QWORD *)FsContext + 9);
  v166 = FcbReleases;
  v193 = FcbReleases;
  v182 = FcbReleases;
  if ( !FcbReleases || (*((_DWORD *)FcbReleases + 1) & 2) != 0 )
  {
    FcbReleases = 0;
    v166 = 0;
    v182 = 0;
    *v22 = v23 & 0xFFFBFFFF;
  }
  else
  {
    InternalSrvOpen = (struct IndexSCB *)*((_QWORD *)FcbReleases + 3);
  }
  v26 = v158;
  if ( !RefsIsFileOpen(v158) && ((__int64)v158->spacer.Resource & 1) == 0 )
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
  v29 = v155;
  if ( (v155 & 4) == 0 || (v155 & 8) != 0 || ((__int64)v158->spacer.Resource & 1) != 0 )
    goto LABEL_101;
  v30 = (unsigned int)*v183;
  if ( (v30 & 0x40000) == 0 )
    goto LABEL_74;
  if ( (v30 & 2) == 0 )
  {
    if ( MmFlushImageSection((PSECTION_OBJECT_POINTERS)(*(_QWORD *)(v6 + 248) + 8LL), MmFlushForDelete) )
    {
      if ( (*(_DWORD *)(v6 + 152) & 2) == 0 )
        _InterlockedOr((volatile signed __int32 *)(v6 + 152), 2u);
      v12 |= 0x20u;
      v153 = v12;
      BYTE1(Status[0]) = v12;
    }
    goto LABEL_73;
  }
  v178[0] = 0;
  LOBYTE(v30) = !FcbReleases || (*((_DWORD *)FcbReleases + 1) & 1) == 0;
  v167 = v30;
  if ( (_BYTE)v30 )
  {
    pNetRoot = v158->pNetRoot;
    if ( !pNetRoot[2].pSrvCall && pNetRoot[2].Context )
    {
      IsLinkDeleteable = RefsIsLinkDeleteable(v3, v158, v178);
      v30 = IsLinkDeleteable;
      v167 = IsLinkDeleteable;
      v27 = v187;
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
      v168 = 0;
      if ( LODWORD(v26->VNetRoot) <= 1 )
      {
        v34 = RefsTryCloseSectionOnDelete((struct _IRP_CONTEXT *)v30, v26, (v24 & 8) != 0);
        v168 = v34;
        v24 |= 0x80u;
        LOBYTE(Status[0]) = v24;
        if ( !v34 )
          goto LABEL_63;
        if ( (v24 & 8) != 0 )
        {
          v24 |= 0x40u;
          LOBYTE(Status[0]) = v24;
          v168 = 0;
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
        v153 = v12;
        BYTE1(Status[0]) = v12;
        v35 = v26->pNetRoot;
        if ( !v35[2].pSrvCall && v35[2].Context )
          FsRtlNotifyFilterChangeDirectory(
            *((PNOTIFY_SYNC *)v159 + 108),
            (PLIST_ENTRY)v159 + 53,
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
  *v183 &= ~0x40000u;
  v26 = v158;
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
      v29 = v155;
      if ( (*(_DWORD *)(v6 + 152) & 2) != 0 && *(_DWORD *)(v6 + 160) == 1 )
      {
        v12 |= 2u;
        v153 = v12;
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
        v29 = v155;
        if ( v37 )
        {
          v24 |= 0x40u;
          LOBYTE(Status[0]) = v24;
        }
      }
      else
      {
        v29 = v155;
      }
    }
LABEL_101:
    v38 = v163;
    if ( v163 != 2 )
    {
      if ( v163 != 3 )
      {
        if ( v163 != 4 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_19f8fd460e213a7a43a7f3710d090bd3_Traceguids, v163);
          }
          KeBugCheckEx(0x149u, 0x70B4Cu, v163, 0, 0);
        }
        v39 = FileObject;
        FileObject->Flags |= 0x4000u;
        v40 = v159;
        if ( *((PFILE_OBJECT *)v159 + 110) == v39 )
        {
          v41 = *((_QWORD *)v159 + 9);
          if ( v41 )
          {
            RefsAcquireExclusiveFcb(v3, *(_QWORD *)(v41 + 136), *((_QWORD *)v159 + 9), 0);
            *((_QWORD *)v159 + 732) = 0x7FFFFFFFFFFFFFFFLL;
            *((_QWORD *)v40 + 733) = 0;
            *((_QWORD *)v40 + 110) = 0;
            RefsReleaseFcb(v3, *(struct _FCB **)(*((_QWORD *)v40 + 9) + 136LL));
            v39 = FileObject;
          }
        }
        if ( (*(_DWORD *)v165 & 2) != 0 )
        {
          v180 = (_QWORD *)((char *)v40 + 872);
          v42 = *((_QWORD *)v40 + 109);
          if ( (PFILE_OBJECT)(v42 & 0xFFFFFFFFFFFFFFFEuLL) == v39 )
          {
            if ( (v42 & 1) != 0 )
            {
              RefsSendBeginDismountEvent(
                v3,
                v159,
                v39,
                3,
                *(_QWORD *)WatchTree,
                *(_QWORD *)IgnoreBuffer,
                CompletionFilter);
              v40 = v159;
              RefsPerformDismountOnVcb((__int64)v3, (__int64)v159, 1, 0, 3, 0);
            }
            else if ( (v39->Flags & 0x1000) != 0 )
            {
              if ( (v155 & 4) != 0 && (v155 & 8) == 0 && (*v157 & 1) == 0 )
              {
                RefsReleaseScbWithPaging(v3, (struct _SCB *)v6);
                if ( RefsUseFlushVolumeParallel )
                  RefsFlushVolumeParallel(v3, v40, 12);
                else
                  RefsFlushVolumeOriginal(v3, v40, 12);
                RefsAcquireExclusiveFcb(v3, *(_QWORD *)(v6 + 136), v6, 0);
              }
              if ( *((_DWORD *)v40 + 54) == 1 && *((_DWORD *)v40 + 55) - *((_DWORD *)v40 + 57) == 1 )
              {
                RefsSendBeginDismountEvent(
                  v3,
                  v159,
                  v39,
                  3,
                  *(_QWORD *)WatchTree,
                  *(_QWORD *)IgnoreBuffer,
                  CompletionFilter);
                RefsReleaseScbWithPaging(v3, (struct _SCB *)v6);
                if ( RefsUseFlushVolumeParallel )
                  RefsFlushVolumeParallel(v3, v159, 144);
                else
                  RefsFlushVolumeOriginal(v3, v159, 144);
                RefsAcquireExclusiveFcb(v3, *(_QWORD *)(v6 + 136), v6, 0);
                v40 = v159;
                RefsPerformDismountOnVcb((__int64)v3, (__int64)v159, 1, 0, 3, 0);
                v43 = v156;
                v44 = v157;
                goto LABEL_131;
              }
            }
            v44 = v157;
            v43 = v156;
LABEL_131:
            *(_DWORD *)v165 &= 0xFFFF7FFD;
            *v180 = 0;
            LOBYTE(v43) = v43 | 1;
            v156 = v43;
            BYTE2(Status[0]) = v43;
            if ( (v43 & 4) != 0
              && (v43 & 8) == 0
              && (*v44 & 1) == 0
              && !Status[1]
              && *((_DWORD *)v40 + 301) == -1073741202 )
            {
              *((_DWORD *)v40 + 301) = 0;
              RefsPostSpecial(
                v3,
                v40,
                (void (*)(struct _IRP_CONTEXT *, void *))RefsDeleteUsnSpecial,
                (char *)v40 + 1192,
                1u,
                0);
              v165 = 4;
              v45 = v158;
              v43 = v156;
              v46 = Status[1];
              v47 = v157;
              goto LABEL_177;
            }
            v165 = 4;
            v45 = v158;
            v46 = Status[1];
            goto LABEL_176;
          }
          goto LABEL_174;
        }
        goto LABEL_340;
      }
      RefsSnapshotScb(v3, v6, 0, v163);
      v48 = *(_WORD *)(v6 + 216);
      if ( (v48 == 128 || v48 == 176) && *(_WORD *)v6 == 2053 && *(_QWORD *)(*(_QWORD *)(v6 + 144) + 72LL) != v6
        || v48 == 160
        && *(_WORD *)(v6 + 224) == 8
        && !memcmp(*(const void **)(v6 + 232), RefsFileNameIndex.Buffer, 8u)
        && (unsigned __int16)(*(_WORD *)v6 - 2051) <= 1u )
      {
        FsRtlCheckOplock((POPLOCK)(v6 + 88), Irp, 0, 0, 0);
      }
      v49 = FileObject;
      FileObject->Flags |= 0x4000u;
      v50 = v183;
      if ( (*v183 & 0x800000) != 0 )
      {
        FsRtlNotifyCleanup(*((PNOTIFY_SYNC *)v159 + 108), (PLIST_ENTRY)v159 + 53, FsContext);
        *v50 &= ~0x800000u;
        _InterlockedDecrement((volatile signed __int32 *)v159 + 354);
        v49 = FileObject;
      }
      v47 = v157;
      if ( (v155 & 4) == 0 || (v155 & 8) != 0 || (*v157 & 1) != 0 )
      {
LABEL_339:
        v45 = v158;
LABEL_342:
        v165 = 4;
        v12 = v153;
        v43 = v156;
        v46 = Status[1];
        goto LABEL_177;
      }
      RefsUpdateScbFromFileObject(v49, (struct _SCB *)v6, 1u);
      if ( *(_WORD *)v6 == 2051 )
      {
        if ( (v24 & 0x10) == 0 || (v24 & 0x40) != 0 )
        {
          if ( (*(_DWORD *)v180 & 4) != 0 )
          {
            if ( RefsHardlinksSupported(*((struct _VCB **)v3 + 8)) )
            {
              if ( FcbReleases )
              {
                v57 = *((_DWORD *)FcbReleases + 1);
                if ( (v57 & 1) != 0 && (v57 & 2) == 0 )
                {
                  v45 = v158;
                  RefsPosixDeleteLink(v3, v158, (__int64)FsContext, (__int64)InternalSrvOpen, (__int64)Status);
                  v165 = 4;
                  v43 = BYTE2(Status[0]);
                  v156 = BYTE2(Status[0]);
                  v12 = BYTE1(Status[0]);
                  v153 = BYTE1(Status[0]);
                  v24 = Status[0];
                  v46 = Status[1];
                  goto LABEL_176;
                }
              }
            }
          }
          v45 = v158;
          if ( HIDWORD(v158->spacer.PagingIoResource) == 1
            && (v24 & 1) != 0
            && *((_DWORD *)v159 + 888) <= RefsMaxDelayedCloseCount
            && (*(_DWORD *)(v6 + 152) & 0x1000000) == 0 )
          {
            v47 = v157;
            if ( (*(_DWORD *)(v6 + 152) & 0x200000) == 0 )
            {
              _InterlockedOr((volatile signed __int32 *)(v6 + 152), 0x200000u);
              v165 = 4;
              v43 = v156;
              v46 = Status[1];
              goto LABEL_177;
            }
            goto LABEL_342;
          }
          goto LABEL_341;
        }
        if ( !FcbReleases )
        {
          LODWORD(v185) = 0;
          QuadPart = (struct _FCB *)v158->Header.FileSize.QuadPart;
          v184 = (struct _CC_FILE_SIZES *)QuadPart;
          while ( QuadPart != (struct _FCB *)&v158->spacer.FileSize )
          {
            FcbReleases = (struct _LCB *)QuadPart[-1].FcbReleases;
            if ( (QuadPart[-1].FcbReleases[1] & 2) == 0 )
              goto LABEL_161;
            QuadPart = *(struct _FCB **)&QuadPart->Header.NodeTypeCode;
          }
          FcbReleases = 0;
LABEL_161:
          v166 = FcbReleases;
          if ( FcbReleases )
            InternalSrvOpen = (struct IndexSCB *)*((_QWORD *)FcbReleases + 3);
        }
        if ( RefsIsTransactionActive(v3) )
          RefsCheckpointCurrentTransaction(v52);
        if ( InternalSrvOpen )
        {
          RefsAcquireExclusiveScb(v3, InternalSrvOpen, 0);
          v53 = v156;
          LOBYTE(v53) = v156 | 0x80;
          v156 = v53;
          BYTE2(Status[0]) = v53;
        }
        RefsDeleteFile(v3, v158, InternalSrvOpen, 0, 0);
        v12 = v153;
        v47 = v157;
        if ( !Status[1] )
        {
          if ( (v153 & 0x10) == 0 )
          {
            if ( InternalSrvOpen )
              v54 = (struct _FCB *)*((_QWORD *)InternalSrvOpen + 17);
            else
              v54 = 0;
            RefsReportDirNotify(
              v159,
              v159,
              (struct _UNICODE_STRING *)FsContext + 1,
              *((unsigned __int16 *)FsContext + 16),
              0,
              0,
              2u,
              2u,
              v54);
            v12 = v153;
          }
          *v183 &= 0xFFFFFF8F;
LABEL_174:
          v165 = 4;
          v45 = v158;
          v46 = Status[1];
LABEL_175:
          v43 = v156;
LABEL_176:
          v47 = v157;
          goto LABEL_177;
        }
        goto LABEL_339;
      }
LABEL_340:
      v45 = v158;
LABEL_341:
      v47 = v157;
      goto LABEL_342;
    }
    v165 = v6 + 152;
    if ( (*(_DWORD *)(v6 + 152) & 0x20) == 0
      && (v29 & 4) != 0
      && (v29 & 8) == 0
      && (*(_BYTE *)(*(_QWORD *)(v6 + 136) + 8LL) & 1) == 0 )
    {
      RefsUpdateScbFromAttribute(v3, (struct _SCB *)v6, 0);
    }
    v185 = (_DWORD *)v165;
    RefsSnapshotScb(v3, v6, 0, v38);
    v187 = (int *)(v6 + 216);
    v58 = *(_WORD *)(v6 + 216);
    if ( (v58 == 128 || v58 == 176) && *(_WORD *)v6 == 2053 && *(_QWORD *)(*(_QWORD *)(v6 + 144) + 72LL) != v6
      || v58 == 160
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
      if ( (*(_DWORD *)v165 & 0x20) == 0 )
        goto LABEL_222;
      if ( FsRtlOplockIsFastIoPossible((POPLOCK)(v6 + 88)) )
      {
        if ( *(__int16 *)(v6 + 256) >= 0 )
        {
          v60 = *(_QWORD *)(v6 + 384);
          if ( (!v60 || !*(_BYTE *)(v60 + 16))
            && ((_DWORD)p_FsContext[3] & 0x2000000) == 0
            && (*(_BYTE *)(*(_QWORD *)(v6 + 136) + 8LL) & 0x20) == 0 )
          {
            v61 = 1;
LABEL_224:
            *(_BYTE *)(v6 + 5) = v61;
            v62 = v155;
            v47 = v157;
            if ( (v155 & 4) == 0 || (v155 & 8) != 0 || (*v157 & 1) != 0 )
            {
              v39 = FileObject;
              FileObject->Flags |= 0x4000u;
              if ( (v62 & 4) == 0 || (*v47 & 1) != 0 || (*(_DWORD *)(v6 + 300) & 0x40) != 0 )
              {
                v43 = v156;
                LOBYTE(v43) = v156 | 0x20;
                v156 = v43;
                BYTE2(Status[0]) = v43;
                v165 = 4;
                v45 = v158;
                v46 = Status[1];
              }
              else
              {
                v165 = 4;
                v45 = v158;
                v43 = v156;
                v46 = Status[1];
              }
              goto LABEL_177;
            }
            RefsUpdateScbFromFileObject(FileObject, (struct _SCB *)v6, 1u);
            v39 = FileObject;
            FileObject->Flags |= 0x4000u;
            v63 = Status[1];
            if ( Status[1] )
              goto LABEL_340;
            v170 = 0;
            if ( (v24 & 0x40) == 0
              && (!FcbReleases || (*((_DWORD *)FcbReleases + 1) & 1) != 0 && *((_DWORD *)FcbReleases + 26) == 1) )
            {
              if ( (v24 & 0x10) != 0 )
              {
                v64 = v24 & 0xFE;
                LOBYTE(Status[0]) = v64;
                if ( (*(_DWORD *)v157 & 0x8000LL) != 0 )
                {
                  RefsPostSpecial(
                    v3,
                    v159,
                    (void (*)(struct _IRP_CONTEXT *, void *))RefsDeleteUsnSpecial,
                    (char *)v159 + 1192,
                    1u,
                    0);
                  v24 = v64 & 0xEF;
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
                        v190 = (LARGE_INTEGER *)((char *)FcbReleases + 32);
                        v66 = (LARGE_INTEGER *)*((_QWORD *)FcbReleases + 4);
                        v190 = v66;
                        v195 = (LONGLONG *)v66;
                      }
                      else
                      {
                        v66 = (LARGE_INTEGER *)p_FileSize->QuadPart;
                        v196 = (_QWORD *)p_FileSize->QuadPart;
                      }
                      while ( v66 != p_FileSize )
                      {
                        FcbReleases = (struct _LCB *)&v66[-4];
                        if ( (v66[-4].HighPart & 2) == 0 )
                          goto LABEL_243;
                        v66 = (LARGE_INTEGER *)v66->QuadPart;
                      }
                      FcbReleases = 0;
LABEL_243:
                      v166 = FcbReleases;
                      if ( !FcbReleases )
                        break;
                      *((_DWORD *)FcbReleases + 1) &= 0xFFFFFFBE;
                    }
                  }
                  goto LABEL_269;
                }
                v63 = RefsCompleteFileDeletion(
                        v3,
                        v26,
                        (struct _SCB *)v6,
                        (struct _CCB *)FsContext,
                        &InternalSrvOpen,
                        &v166,
                        (struct REFS_CLEANUP_FLAGS *)Status);
                Status[1] = v63;
                FcbReleases = v166;
LABEL_246:
                v67 = BYTE2(Status[0]);
                v156 = BYTE2(Status[0]);
                v12 = BYTE1(Status[0]);
                v153 = BYTE1(Status[0]);
                v24 = Status[0];
LABEL_271:
                v180 = (_QWORD *)(v6 + 160);
                if ( *(_DWORD *)(v6 + 160) == 1 )
                {
                  v82 = v158;
                  if ( LODWORD(v158->VNetRoot) )
                  {
                    if ( !v63 )
                    {
                      v83 = 0;
                      v169 = 0;
                      if ( (v12 & 2) != 0 )
                      {
                        if ( *(_WORD *)v187 )
                        {
                          v83 = RefsDeleteResidentDataScbAndCommit(v3, (struct _SCB *)v6, (unsigned __int8)v39);
                          v169 = v83;
                          v82 = v158;
                          v63 = Status[1];
                        }
                        if ( v83 )
                        {
                          if ( !v63 )
                          {
                            v24 |= 4u;
                            LOBYTE(Status[0]) = v24;
                          }
                          LOBYTE(v67) = v67 | 0x20;
                          v156 = v67;
                          BYTE2(Status[0]) = v67;
                          RefsUpdateFileTimestampsForChange(v82, FsContext, 0x400000, 0);
                          v84 = FileObject;
                          FileObject->Flags &= ~0x4000u;
                          RefsUpdateScbFromFileObject(v84, (struct _SCB *)v6, 1u);
                          v84->Flags |= 0x4000u;
                          v86 = *(char **)(v6 + 368);
                          v190 = (LARGE_INTEGER *)v86;
                          if ( v86 )
                          {
                            v192 = v86;
                            if ( *((_DWORD *)v86 + 41) == 1 )
                              RefsDeleteResidentDataScbAndCommit(v3, (struct _SCB *)v86, v85);
                            WatchTree[0] = 0;
                            RefsDecrementCloseCounts(v3, v86, 0, 0, *(_DWORD *)WatchTree, 0);
                          }
                        }
                      }
                      else if ( *(_WORD *)v187 )
                      {
                        if ( (*v185 & 4) != 0 )
                        {
                          if ( (v12 & 0x40) == 0 && (*(_DWORD *)v157 & 0x100LL) == 0 )
                            RefsPrepareForUpdateDuplicate(v3, v158, &v182, &InternalSrvOpen, 1u, 0);
                          RefsWriteFileSizes(v3, (struct _SCB *)v6, 0, 2u, WatchTree[0]);
                          RefsCheckpointCurrentTransaction(v3);
                          v87 = FileObject;
                          FileObject->Flags &= ~0x4000u;
                          RefsUpdateScbFromFileObject(v87, (struct _SCB *)v6, 1u);
                          v87->Flags |= 0x4000u;
                        }
                        if ( (*v185 & 0x40) != 0 )
                        {
                          v165 = 4;
                          RefsWriteFileSizes(v3, (struct _SCB *)v6, 0, 4u, WatchTree[0]);
                          RefsCheckpointCurrentTransaction(v3);
                          v45 = v158;
                          v88 = FileObject;
                          v39 = (PFILE_OBJECT)v157;
                          goto LABEL_293;
                        }
                      }
                    }
                  }
                }
                v39 = (PFILE_OBJECT)v157;
                v88 = FileObject;
                v45 = v158;
                v165 = 4;
LABEL_293:
                v89 = Status[1];
                if ( !Status[1]
                  && *(_DWORD *)v180 == 1
                  && LODWORD(v45->VNetRoot)
                  && (v12 & 2) == 0
                  && v88->SectionObjectPointer == (PSECTION_OBJECT_POINTERS)(*(_QWORD *)(v6 + 248) + 8LL)
                  && *(_WORD *)v187
                  && (*v185 & 1) != 0 )
                {
                  v12 |= 0x80u;
                  v153 = v12;
                  BYTE1(Status[0]) = v12;
                  if ( (v12 & 0x40) == 0 && (*(_DWORD *)&v39->Type & 0x100LL) == 0 )
                    RefsPrepareForUpdateDuplicate(v3, v45, &v182, &InternalSrvOpen, 1u, 0);
                  if ( *(_WORD *)v6 == 2053 && *(_QWORD *)(v6 + 432) )
                  {
                    AllocationSize = v184[1].AllocationSize;
                    if ( AllocationSize.QuadPart )
                    {
                      v92 = *((unsigned int *)v159 + 136);
                      v93 = (v92 + *(_QWORD *)(v6 + 32)) >> *((_BYTE *)v159 + 552);
                      if ( (AllocationSize.QuadPart + v92) >> *((_BYTE *)v159 + 552) != v93 )
                      {
                        RefsDeleteAllocation(
                          v3,
                          (struct _SCB *)v6,
                          v93,
                          0x7FFFFFFFFFFFFFFFLL,
                          *(_WORD *)(v6 + 256) >= 0);
                        RefsCheckpointCurrentTransaction(v3);
                        *(_QWORD *)v157 |= 0x40000uLL;
                      }
                      v94 = v156;
                      LOBYTE(v94) = v156 | 0x40;
                      v156 = v94;
                      BYTE2(Status[0]) = v94;
                    }
                  }
                  else
                  {
                    v95 = (*(_DWORD *)(v6 + 32) + 7) & 0xFFFFFFF8;
                    if ( v95 < v184[1].AllocationSize.LowPart )
                    {
                      v194 = v184[1];
                      v194.AllocationSize.LowPart = v95;
                      RefsWriteFileSizes(v3, (struct _SCB *)v6, &v194, 1u, WatchTree[0]);
                      RefsCheckpointCurrentTransaction(v3);
                      v184[1].AllocationSize.LowPart = v194.AllocationSize.LowPart;
                    }
                  }
                  RefsUpdateScbFromFileObject(FileObject, (struct _SCB *)v6, 1u);
                  v89 = Status[1];
                }
                v96 = *(_DWORD *)(v6 + 156);
                if ( v96 )
                {
                  if ( *(_DWORD *)v180 == v96 + 1
                    && *(__int16 *)(v6 + 256) >= 0
                    && (*((_BYTE *)FsContext + 88) & 7) != 0 )
                  {
                    v97 = *(_QWORD *)(v6 + 248);
                    if ( *(_QWORD *)(v97 + 8) )
                    {
                      if ( !*(_QWORD *)(v97 + 24)
                        && (FileObject->Flags & 8) == 0
                        && !v89
                        && MmCanFileBeTruncated((PSECTION_OBJECT_POINTERS)(*(_QWORD *)(v6 + 248) + 8LL), 0)
                        && (*(_DWORD *)(*(_QWORD *)(v6 + 136) + 8LL) & 0x100LL) == 0
                        && (v12 & 0x40) == 0 )
                      {
                        RefsCheckpointCurrentTransaction(v3);
                        v24 |= 4u;
                        LOBYTE(Status[0]) = v24;
                        if ( (v156 & 0x80u) != 0LL )
                        {
                          RefsReleaseFcb(v3, *((struct _FCB **)InternalSrvOpen + 17));
                          v98 = v156;
                          LOBYTE(v98) = v156 & 0x7F;
                          v156 = v98;
                          BYTE2(Status[0]) = v98;
                        }
                        if ( *((_QWORD *)v3 + 6) )
                          RefsReleaseSharedResources(v3);
                        RefsFlushAndPurgeScb(v3, (struct _SCB *)v6);
                        *((_DWORD *)v3 + 4) = 0;
                      }
                    }
                  }
                }
                v46 = Status[1];
                if ( Status[1]
                  || HIDWORD(v45->spacer.PagingIoResource) != 1
                  || (v24 & 1) == 0
                  || *((_DWORD *)v159 + 888) > RefsMaxDelayedCloseCount )
                {
                  goto LABEL_175;
                }
                v47 = v157;
                if ( (*v157 & 4) != 0 || (*v185 & 0x1000000) != 0 )
                {
                  v43 = v156;
                }
                else
                {
                  v43 = v156;
                  if ( (*(_DWORD *)(v6 + 152) & 0x200000) == 0 )
                    _InterlockedOr((volatile signed __int32 *)(v6 + 152), 0x200000u);
                }
LABEL_177:
                if ( v164 == 4 )
                  goto LABEL_453;
                NonPaged = v45->NonPaged;
                if ( *((PNON_PAGED_FCB *)&v45->1 + 16) != NonPaged )
                {
                  v56 = *(struct _IRP_CONTEXT **)v47;
                  if ( (*(_QWORD *)v47 & 0x10) != 0 )
                  {
                    *((_QWORD *)&v45->1 + 16) = NonPaged;
LABEL_352:
                    *((_DWORD *)&v45->1 + 43) |= 0x20u;
                    goto LABEL_353;
                  }
                  if ( ((unsigned __int8)v56 & 1) == 0 && RefsCheckLastAccess(v56, v45) )
                  {
                    *(_QWORD *)v47 = v99 | 0x10;
                    *v183 |= 0x10000u;
                    v45 = v158;
                    goto LABEL_352;
                  }
                }
LABEL_353:
                if ( (v43 & 4) == 0 || (v43 & 8) != 0 || (*(_QWORD *)v47 & 1) != 0 )
                {
LABEL_415:
                  if ( (v43 & 0x80u) != 0LL && (v12 & 0x40) == 0 )
                  {
                    RefsReleaseFcb(v3, *((struct _FCB **)InternalSrvOpen + 17));
                    v43 = v156;
                    LOBYTE(v43) = v156 & 0x7F;
                    v156 = v43;
                    BYTE2(Status[0]) = v43;
                  }
                  if ( FileObject->PrivateCacheMap > (PVOID)1
                    || (v43 & 0x20) != 0
                    || (v43 & 0x40) != 0
                    || (v24 & 0x40) != 0 && FileObject->SectionObjectPointer )
                  {
                    v180 = 0;
                    if ( (v43 & 0x40) != 0 )
                      v180 = *(_QWORD **)(v6 + 32);
                    v114 = (const __int64 *)&v180;
                    if ( (v43 & 0x20) == 0 )
                      v114 = 0;
                    RefsUninitializeCacheMap(FileObject, v114, (struct _CACHE_UNINITIALIZE_EVENT *)v39);
                  }
                  if ( (*v157 & 1) == 0 )
                  {
                    v115 = *(_QWORD *)&v45->FcbTableEntry.Path.Length;
                    if ( v115 )
                    {
                      if ( LODWORD(v45->spacer.PagingIoResource) == 1
                        && !Status[1]
                        && (*(_DWORD *)(v115 + 104) || *((struct _FCB **)v3 + 76) == v45 && *((_DWORD *)v3 + 154)) )
                      {
                        for ( i = (struct _FCB *)v45->Header.FastMutex;
                              i != (struct _FCB *)&v45->spacer.FastMutex;
                              i = *(struct _FCB **)&i->Header.NodeTypeCode )
                        {
                          if ( (*(_BYTE *)(&i[-1].FileLock.LockRequestsInProgress + 1) & 0x20) != 0
                            && (i->Header.FileSize.LowPart & 0x40000) != 0 )
                          {
                            goto LABEL_441;
                          }
                        }
                        RefsPostUsnChange(v3, v45, 0x80000000, 0);
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
                  v117 = 0;
                  v188 = 0;
                  if ( (*(_DWORD *)(v6 + 152) & 4) != 0 )
                  {
                    if ( *(_DWORD *)(v6 + 160) == 1 )
                      v117 = 4;
                    v188 = v117;
                  }
                  if ( v12 < 0 )
                  {
                    v117 |= 1u;
                    v188 = v117;
                  }
                  if ( v117 && (v117 & *(_DWORD *)(v6 + 152)) != 0 )
                    _InterlockedAnd((volatile signed __int32 *)(v6 + 152), ~v117);
LABEL_453:
                  if ( (*v183 & 0x8000000) != 0 )
                  {
                    if ( (v156 & 4) != 0 && (v156 & 8) == 0 && *(_WORD *)v6 == 2053 && *(_QWORD *)(v6 + 432) )
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
                  v119 = FsContext;
                  *((_QWORD *)v3 + 1) &= ~0x400uLL;
                  *((_QWORD *)v3 + 1) |= 0x8000000uLL;
                  v119[1] |= 0x8000u;
                  if ( Status[1] && (v24 & 4) == 0 && ((v24 & 0x10) != 0 || (v12 & 0x40) != 0 || (v12 & 2) != 0) )
                  {
                    RefsBackoutFailedLinkRemove(v3, (__int64)Status);
                    v156 = BYTE2(Status[0]);
                    v12 = BYTE1(Status[0]);
                    v153 = BYTE1(Status[0]);
                    v24 = Status[0];
                    v119 = FsContext;
                  }
                  v120 = (unsigned __int8)v24;
                  LOBYTE(v120) = (v24 & 0x10) != 0;
                  if ( (v24 & 0x10) != 0
                    || (v12 & 0x40) != 0
                    || (v119[1] & 0x10000) != 0
                    || ((__int64)v45->spacer.Resource & 0x40000) != 0 )
                  {
                    v121 = 16;
                    v189 = 16;
                    if ( (v24 & 0x10) != 0 || (v12 & 0x40) != 0 )
                    {
                      v121 = 80;
                      v189 = 80;
                    }
                    if ( ((__int64)v45->spacer.Resource & 0x40000) != 0 )
                    {
                      v121 |= 8u;
                      v189 = v121;
                    }
                    if ( !InternalSrvOpen && v164 == 2 )
                      InternalSrvOpen = (struct IndexSCB *)v45->InternalSrvOpen;
                    if ( InternalSrvOpen )
                    {
                      FsRtlCheckOplockEx((POPLOCK)InternalSrvOpen + 11, Irp, v121, 0, 0, 0);
                      v45->Header.Resource = (PERESOURCE)((unsigned __int64)v45->Header.Resource & ~0x40000uLL);
                    }
                    v12 = v153;
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
                        v128 = v156;
                        if ( (v156 & 2) != 0 && (v12 & 0x40) == 0 )
                        {
                          RefsUpdateLcbDuplicateInfo((struct _IRP_CONTEXT *)v120, v45, v182);
                          *((_DWORD *)&v45->1 + 43) = 0;
                        }
                        if ( (v128 & 0x10) != 0 )
                        {
                          v129 = *((_QWORD *)FcbReleases + 3);
                          v130 = *(struct _FAST_MUTEX **)(v129 + 48);
                          KeEnterGuardedRegion();
                          ExAcquireFastMutexUnsafe(v130);
                          _InterlockedIncrement((volatile signed __int32 *)(v129 + 172));
                          --*((_DWORD *)FcbReleases + 18);
                          ++*(_DWORD *)(v129 + 172);
                          ExReleaseFastMutexUnsafe(*(PFAST_MUTEX *)(v129 + 48));
                          KeLeaveGuardedRegion();
                          v131 = v156;
                          LOBYTE(v131) = v156 & 0xEF;
                          v156 = v131;
                          BYTE2(Status[0]) = v131;
                        }
                        v132 = FsContext;
                        if ( (*((_DWORD *)FsContext + 1) & 8) != 0 )
                        {
                          v133 = 1;
                        }
                        else
                        {
                          v133 = 0;
                          if ( *((_BYTE *)FsContext + 80) == 4 )
                            v133 = 2;
                        }
                        v134 = FileObject;
                        RefsRemoveShareAccess(FileObject, v133, v6, v193);
                        RefsDecrementCleanupCounts(v3, (struct _SCB *)v6, v193, (v134->Flags >> 3) & 1);
                        FcbReleases = 0;
                        v166 = 0;
                        if ( (v24 & 0x10) != 0 )
                        {
                          v135 = (SECTION_OBJECT_POINTERS *)(*(_QWORD *)(v6 + 248) + 8LL);
                          if ( v135->DataSectionObject )
                            MmForceSectionClosed(v135, 1u);
                        }
                        v136 = v132[2];
                        if ( (v136 & 1) != 0 )
                        {
                          v132[2] = v136 & 0xFFFFFFFE;
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
                      v127 = Irp;
                      Irp->IoStatus.Information = 0;
                      if ( (v24 & 0x10) != 0 )
                      {
                        v127->IoStatus.Information = 4;
                        if ( (v24 & 0x20) != 0 )
                        {
                          v165 = 36;
                          v127->IoStatus.Information = 36;
                        }
                        v120 = v165;
                      }
                      else
                      {
                        v120 = 0;
                        if ( (v12 & 0x40) != 0 )
                        {
                          Irp->IoStatus.Information = 8;
                          v120 = 8;
                        }
                      }
                      if ( (v12 & 2) != 0 )
                      {
                        v120 |= 0x10uLL;
                        Irp->IoStatus.Information = v120;
                      }
                      goto LABEL_510;
                    }
                  }
                  if ( (*((_DWORD *)v159 + 1642) & 4) != 0 && (unsigned __int8)(v164 - 2) <= 1u )
                  {
                    memset(v198, 0, sizeof(v198));
                    v122 = *(_QWORD *)(v6 + 136);
                    *(_QWORD *)&v198[8] = *(_QWORD *)(*(_QWORD *)(v122 + 88) + 256LL);
                    v123 = *(_QWORD *)(*(_QWORD *)(v122 + 88) + 248LL);
                    *(_QWORD *)v198 = v123;
                    if ( Irp )
                    {
                      ActivityIdIrp = IoGetActivityIdIrp(Irp, &v198[24]);
                      v125 = &v198[24];
                      if ( ActivityIdIrp < 0 )
                        v125 = 0;
                    }
                    else
                    {
                      ActivityIdThread = (_OWORD *)IoGetActivityIdThread(v123, v122);
                      if ( ActivityIdThread )
                      {
                        *(_OWORD *)&v198[24] = *ActivityIdThread;
                        v125 = &v198[24];
                      }
                      else
                      {
                        v125 = 0;
                      }
                    }
                    *(_QWORD *)&v198[16] = v125;
                    FsRtlHeatLogIo((char *)v159 + 6564, Irp, v198, 0, v125);
                  }
LABEL_499:
                  if ( (v24 & 0x10) != 0 )
                    goto LABEL_502;
                  goto LABEL_500;
                }
                if ( (*(_QWORD *)v47 & 0x10) != 0 && !v46 )
                {
                  RefsUpdateStandardInformation(v3, v45);
                  v43 = v156;
                  v47 = v157;
                }
                v100 = (struct _CC_FILE_SIZES *)((char *)&v45->1 + 172);
                v184 = (struct _CC_FILE_SIZES *)((char *)&v45->1 + 172);
                v39 = (PFILE_OBJECT)((char *)&v45->1 + 172);
                if ( (*((_DWORD *)&v45->1 + 43) & 0xC00000FC) != 0
                  || (*v183 & 0x10000) != 0
                  || v182 && (*((_DWORD *)v182 + 19) & 0xC00000FC) != 0 )
                {
                  v101 = Status[1];
                  if ( Status[1] )
                  {
LABEL_369:
                    if ( (v12 & 0x10) != 0 || v101 )
                      goto LABEL_412;
                    v181 = 0;
                    if ( (v43 & 2) == 0 || (v12 & 0x40) != 0 )
                    {
                      LowPart = v100->AllocationSize.LowPart;
                      if ( (LowPart & 0x100) == 0 )
                        goto LABEL_391;
                    }
                    else
                    {
                      LowPart = *(_DWORD *)&v39->Type;
                    }
                    if ( v182 )
                      v103 = *((_DWORD *)v182 + 19);
                    else
                      v103 = 0;
                    if ( ((LowPart | v103) & 0x40000000) != 0 )
                    {
                      if ( v182 )
                        v104 = ((unsigned __int16)LowPart | (unsigned __int16)*((_DWORD *)v182 + 19)) & 0x1F4 | 8;
                      else
                        v104 = LowPart & 0x1F4 | 8;
                    }
                    else
                    {
                      if ( v182 )
                        v105 = *((_DWORD *)v182 + 19);
                      else
                        LOWORD(v105) = 0;
                      v104 = ((unsigned __int16)v105 | (unsigned __int16)LowPart) & 0x1FC;
                    }
                    v181 = v104;
                    if ( v104 )
                    {
                      if ( InternalSrvOpen )
                        v106 = (struct _IRP_CONTEXT *)*((_QWORD *)InternalSrvOpen + 17);
                      else
                        v106 = 0;
                      RefsReportDirNotify(
                        v106,
                        v159,
                        (struct _UNICODE_STRING *)FsContext + 1,
                        *((unsigned __int16 *)FsContext + 16),
                        0,
                        0,
                        v104,
                        3u,
                        (struct _FCB *)v106);
                      v12 = v153;
                    }
LABEL_391:
                    v184->AllocationSize.LowPart &= ~0x100u;
                    if ( *(_WORD *)(v6 + 224) && ((v107 = *(_WORD *)(v6 + 216), v107 == 128) || v107 == 176)
                      || (v12 & 2) != 0 )
                    {
                      v108 = *(_DWORD *)(v6 + 300);
                      if ( (v108 & 0xC00) != 0 )
                      {
                        v109 = *(_DWORD *)(*(_QWORD *)v198 + 152LL);
                      }
                      else
                      {
                        v109 = *(_DWORD *)(v6 + 152);
                        if ( (v109 & 0x4000) == 0 )
                        {
LABEL_410:
                          *(_DWORD *)(v6 + 300) &= 0xFFFFF1FF;
                          v12 = v153;
                          if ( (*(_DWORD *)(v6 + 152) & 0x4000) != 0 )
                            _InterlockedAnd((volatile signed __int32 *)(v6 + 152), 0xFFFFBFFF);
                          goto LABEL_412;
                        }
                      }
                      v181 = 0;
                      if ( (v108 & 0x400) != 0 )
                      {
                        v110 = 512;
                        v181 = 512;
                        v111 = 7;
                      }
                      else
                      {
                        v112 = (v109 & 0x4000) != 0;
                        v110 = 0;
                        if ( v112 )
                          v110 = 1024;
                        v181 = v110;
                        if ( (v108 & 0x800) != 0 )
                        {
                          v110 |= 0x800u;
                          v181 = v110;
                        }
                        v111 = 8;
                      }
                      if ( InternalSrvOpen )
                        v113 = (struct _IRP_CONTEXT *)*((_QWORD *)InternalSrvOpen + 17);
                      else
                        v113 = 0;
                      RefsReportDirNotify(
                        v113,
                        v159,
                        (struct _UNICODE_STRING *)FsContext + 1,
                        *((unsigned __int16 *)FsContext + 16),
                        (struct _UNICODE_STRING *)(v6 + 224),
                        0,
                        v110,
                        v111,
                        (struct _FCB *)v113);
                      goto LABEL_410;
                    }
LABEL_412:
                    if ( !Status[1] )
                    {
                      RefsCheckpointCurrentTransaction(v3);
                      v24 |= 4u;
                      LOBYTE(Status[0]) = v24;
                      v45->Header.Resource = (PERESOURCE)((unsigned __int64)v45->Header.Resource & ~0x10uLL);
                    }
                    LOBYTE(v43) = v156;
                    goto LABEL_415;
                  }
                  if ( (*(_DWORD *)v47 & 0x100LL) == 0 )
                  {
                    if ( (v12 & 0x40) == 0 )
                    {
                      RefsCheckpointCurrentTransaction(v3);
                      RefsPrepareForUpdateDuplicate(v3, v45, &v182, &InternalSrvOpen, 1u, 0);
                      RefsUpdateDuplicateInfo(v3, v45, v182, InternalSrvOpen);
                      v43 = v156;
                      v100 = v184;
                      v39 = (PFILE_OBJECT)v184;
                    }
                    LOBYTE(v43) = v43 | 2;
                    v156 = v43;
                    BYTE2(Status[0]) = v43;
                  }
                }
                v101 = Status[1];
                goto LABEL_369;
              }
              if ( !FcbReleases )
              {
LABEL_270:
                v67 = v156;
                goto LABEL_271;
              }
              v68 = v12 | 0x40;
              v153 = v68;
              BYTE1(Status[0]) = v68;
              if ( HIDWORD(v26->VNetRoot) > 1 )
              {
                RefsAcquireExclusiveScb(v3, InternalSrvOpen, 0);
                v69 = v156;
                LOBYTE(v69) = v156 | 0x80;
                v156 = v69;
                BYTE2(Status[0]) = v69;
                v70 = &v26->InternalSrvOpen->0;
                if ( v70 == (_QWORD *)InternalSrvOpen )
                  goto LABEL_253;
                v71 = 5;
                if ( (*((_DWORD *)v3 + 2) & 0x100LL) == 0 )
                  v71 = 3;
                if ( (unsigned __int8)RefsAcquireExclusiveFcb(v3, v70[17], v26->InternalSrvOpen, v71) )
                {
LABEL_253:
                  v73 = v24 & 0xFE;
                  LOBYTE(Status[0]) = v73;
                  v74 = *(_QWORD *)((char *)FcbReleases + 148);
                  v191 = 0;
                  v75 = *((_DWORD *)FcbReleases + 35);
                  LODWORD(v165) = v75 - 4;
                  v191.MaximumLength = v75 - 4;
                  v191.Length = v75 - 4;
                  v191.Buffer = (PWSTR)(v74 + 4);
                  v197 = v191;
                  v76 = InternalSrvOpen;
                  RefsRemoveLink(v3, v158, InternalSrvOpen, &v197);
                  RefsConvertToStandardInfoLinkCount(v3, v158, (unsigned int)(HIDWORD(v158->VNetRoot) - 1), 0);
                  v77 = v158;
                  RefsPostUsnChange(v3, v158, 0x80010000, (struct _LCB *)((char *)FcbReleases + 120));
                  RefsCheckpointCurrentTransaction(v3);
                  --HIDWORD(v158->VNetRoot);
                  v24 = v73 | 4;
                  LOBYTE(Status[0]) = v24;
                  RefsRemovePrefixHashEntry(FcbReleases);
                  *((_DWORD *)FcbReleases + 1) &= ~0x40u;
                  *((_DWORD *)FcbReleases + 1) |= 2u;
                  *((_DWORD *)FcbReleases + 19) = 0;
                  *(_QWORD *)v157 &= ~0x4000uLL;
                  RefsUpdateFcbTimestamps(*((_QWORD *)v76 + 17), FsContext, 2684354576LL);
                  v12 = v153;
                  if ( (v153 & 0x10) == 0 && !Status[1] )
                  {
                    if ( InternalSrvOpen )
                      v79 = (struct _FCB *)*((_QWORD *)InternalSrvOpen + 17);
                    else
                      v79 = 0;
                    RefsReportDirNotify(v159, v159, v78 + 1, v78[2].Length, 0, 0, 1u, 2u, v79);
                    v12 = v153;
                  }
                  v182 = 0;
                  if ( Status[1] >= 0 )
                    RefsUpdateFileTimestampsForChange(v77, FsContext, 0, 0);
                  v80 = FileObject;
                  FileObject->Flags &= ~0x4000u;
                  RefsUpdateScbFromFileObject(v80, (struct _SCB *)v6, 1u);
                  v80->Flags |= 0x4000u;
LABEL_269:
                  v63 = Status[1];
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
                RefsRaiseStatusInternal(v3, -1073741608, v72);
                __debugbreak();
                JUMPOUT(0x1403185AFLL);
              }
              v12 = v68 & 0xBF;
              v153 = v12;
              BYTE1(Status[0]) = v12;
              *((_DWORD *)FcbReleases + 1) |= 0x40u;
            }
            v170 = 1;
            if ( (*(_DWORD *)v180 & 4) == 0 )
              goto LABEL_270;
            if ( !RefsHardlinksSupported(*((struct _VCB **)v3 + 8)) )
              goto LABEL_270;
            if ( !FcbReleases )
              goto LABEL_270;
            v81 = *((_DWORD *)FcbReleases + 1);
            if ( (v81 & 1) == 0 || (v81 & 2) != 0 )
              goto LABEL_270;
            RefsPosixDeleteLink(v3, v26, (__int64)FsContext, (__int64)InternalSrvOpen, (__int64)Status);
            v63 = 0;
            Status[1] = 0;
            goto LABEL_246;
          }
        }
LABEL_222:
        v61 = 2;
        goto LABEL_224;
      }
    }
    v61 = 0;
    goto LABEL_224;
  }
  Irp = 0;
  v3 = 0;
  v160 = 0;
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
    RefsReleaseVcb(v3, v159);
    if ( (v156 & 1) != 0 )
    {
      RefsReleaseScbWithPaging(v3, (struct _SCB *)v6);
      FsRtlNotifyVolumeEvent(FileObject, 5u);
    }
  }
  v137 = v156;
  if ( (v156 & 0x10) != 0 )
  {
    v138 = *((_QWORD *)FcbReleases + 3);
    v139 = *(struct _FAST_MUTEX **)(v138 + 48);
    KeEnterGuardedRegion();
    ExAcquireFastMutexUnsafe(v139);
    _InterlockedIncrement((volatile signed __int32 *)(v138 + 172));
    --*((_DWORD *)FcbReleases + 18);
    ++*(_DWORD *)(v138 + 172);
    ExReleaseFastMutexUnsafe(*(PFAST_MUTEX *)(v138 + 48));
    KeLeaveGuardedRegion();
    v137 &= ~0x10u;
    v36 = Status[1];
  }
  if ( (v153 & 4) != 0 && v36 >= 0 && v36 != 871 && v164 != 4 && (v137 & 4) != 0 && (v137 & 8) == 0 )
  {
    v140 = (struct _UNICODE_STRING *)FsContext;
    if ( (v24 & 0x10) != 0 || (v153 & 2) != 0 || (v153 & 0x40) != 0 || (*((_WORD *)FsContext + 44) & 0x912) != 0 )
    {
      *((_DWORD *)v3 + 1) |= 0x400u;
      RefsCompleteRequest((PSECURITY_SUBJECT_CONTEXT *)v3, 0, v36);
      v142 = RefsIoCallSelf(v3, FileObject, v141);
      v143 = v142;
      if ( v142 != -1073741533 && v142 < 0 )
      {
        if ( (unsigned int)(v142 + 1073741662) > 1
          && v142 != -1073741643
          && (unsigned int)(v142 + 1073741806) > 2
          && v142 != -2147483626 )
        {
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
            || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
          {
            v143 = -1073700734;
          }
          else
          {
            v143 = -1073700734;
            WPP_SF_d(
              WPP_GLOBAL_Control->AttachedDevice,
              18,
              WPP_19f8fd460e213a7a43a7f3710d090bd3_Traceguids,
              3221266562LL);
          }
          if ( (_BYTE)RefsStatusDebugEnabled )
            RefsStatusDebug(-1073700734, 0, "Cleanup.c", 0xF3Fu);
        }
        v144 = v158;
        v145 = v158->pNetRoot;
        KeEnterGuardedRegion();
        ExAcquireFastMutexUnsafe((PFAST_MUTEX)&v145->pSrvCall);
        IoRaiseInformationalHardError(v143, v140 + 1, Irp->Tail.Overlay.Thread);
        ExReleaseFastMutexUnsafe((PFAST_MUTEX)&v144->pNetRoot->pSrvCall);
        KeLeaveGuardedRegion();
      }
    }
  }
  v146 = Status[1];
  if ( Status[1] != 871 )
  {
    v147 = *((_QWORD *)v3 + 1);
    if ( (v147 & 0x100000000LL) != 0 )
    {
      *((_QWORD *)v3 + 1) = v147 | 0x200000000LL;
      return v146;
    }
    RefsCompleteRequest((PSECURITY_SUBJECT_CONTEXT *)v3, Irp, Status[1]);
  }
  return v146;
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
