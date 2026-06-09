# RefsCommonCleanup(_IRP_CONTEXT *,_IRP *)

- ea: `0x140319010`
- end: `0x14031c7df`
- name: `?RefsCommonCleanup@@YAJPEAU_IRP_CONTEXT@@PEAU_IRP@@@Z`
- size: `14287`
- prototype: `__int64 __fastcall(struct _IRP_CONTEXT *, struct _IRP *)`
- caller_count: `3`
- callee_count: `64`
- tags: `file_ops, reparse_path, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1400b9530`
- `0x1400e64e0`
- `0x140318cb0`

## callees

- `0x14000e0e0`
- `0x1400298a0`
- `0x140037820`
- `0x140037e00`
- `0x14004ffc0`
- `0x1400757c0`
- `0x140075ae0`
- `0x140076ad0`
- `0x140085570`
- `0x140085ab0`
- `0x1400862c0`
- `0x140088990`
- `0x1400889f0`
- `0x1400894e0`
- `0x14008ab70`
- `0x14008cb30`
- `0x140090470`
- `0x1400928d0`
- `0x140093bc0`
- `0x140095370`
- `0x14009df40`
- `0x1400a8498`
- `0x1400a9f3c`
- `0x1400a9f50`
- `0x1400adddc`
- `0x1400d0fd8`
- `0x1400e6524`
- `0x140114dc0`
- `0x14011af34`
- `0x1401f3fc0`
- `0x1401f4920`
- `0x14028c3d4`
- `0x14028cfa0`
- `0x14028da28`
- `0x14028debc`
- `0x14028e648`
- `0x14028e828`
- `0x14028ed0c`
- `0x140295afc`
- `0x14029764c`
- `0x14029770c`
- `0x1402977e8`
- `0x1402eaf4c`
- `0x1402eb144`
- `0x140302e10`
- `0x140304230`
- `0x140304a70`
- `0x140306290`
- `0x140319010`
- `0x14031def0`

## import_xrefs

- `ntoskrnl!KeBugCheckEx` at `0x14031990a`
- `ntoskrnl!KeBugCheckEx` at `0x14031990a`
- `ntoskrnl!MmCanFileBeTruncated` at `0x14031b303`
- `ntoskrnl!MmCanFileBeTruncated` at `0x14031b303`
- `ntoskrnl!MmFlushImageSection` at `0x140319679`
- `ntoskrnl!MmFlushImageSection` at `0x140319679`
- `ntoskrnl!FsRtlNotifyFilterChangeDirectory` at `0x14031965e`
- `ntoskrnl!FsRtlNotifyFilterChangeDirectory` at `0x14031965e`
- `ntoskrnl!FsRtlNotifyCleanup` at `0x140319e92`
- `ntoskrnl!FsRtlNotifyCleanup` at `0x140319e92`
- `ntoskrnl!FsRtlFastUnlockAll` at `0x14031a437`
- `ntoskrnl!FsRtlFastUnlockAll` at `0x14031a437`
- `ntoskrnl!IoGetRequestorProcess` at `0x14031a416`
- `ntoskrnl!IoGetRequestorProcess` at `0x14031a416`
- `ntoskrnl!IoGetActivityIdThread` at `0x14031c0cb`
- `ntoskrnl!IoGetActivityIdThread` at `0x14031c0cb`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14031c0af`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14031c0af`
- `ntoskrnl!FsRtlHeatLogIo` at `0x14031c123`
- `ntoskrnl!FsRtlHeatLogIo` at `0x14031c123`
- `ntoskrnl!MmForceSectionClosed` at `0x14031c2ce`
- `ntoskrnl!MmForceSectionClosed` at `0x14031c2ce`
- `ntoskrnl!FsRtlNotifyVolumeEvent` at `0x14031c3cf`
- `ntoskrnl!FsRtlNotifyVolumeEvent` at `0x1403435df`
- `ntoskrnl!FsRtlNotifyVolumeEvent` at `0x14031c3cf`
- `ntoskrnl!FsRtlNotifyVolumeEvent` at `0x1403435df`
- `ntoskrnl!IoRaiseInformationalHardError` at `0x14031c5b0`
- `ntoskrnl!IoRaiseInformationalHardError` at `0x14031c5b0`
- `ntoskrnl!KeEnterGuardedRegion` at `0x14031c1e6`
- `ntoskrnl!KeEnterGuardedRegion` at `0x14031c3ee`
- `ntoskrnl!KeEnterGuardedRegion` at `0x14031c57f`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140343610`
- `ntoskrnl!KeEnterGuardedRegion` at `0x14031c1e6`
- `ntoskrnl!KeEnterGuardedRegion` at `0x14031c3ee`
- `ntoskrnl!KeEnterGuardedRegion` at `0x14031c57f`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140343610`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14031c1f5`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14031c3fd`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14031c58f`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14034361f`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14031c1f5`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14031c3fd`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14031c58f`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14034361f`
- `ntoskrnl!FsRtlOplockIsFastIoPossible` at `0x14031a49c`
- `ntoskrnl!FsRtlOplockIsFastIoPossible` at `0x14031a49c`
- `ntoskrnl!FsRtlCheckOplock` at `0x140319e46`
- `ntoskrnl!FsRtlCheckOplock` at `0x14031a3ee`
- `ntoskrnl!FsRtlCheckOplock` at `0x140319e46`
- `ntoskrnl!FsRtlCheckOplock` at `0x14031a3ee`
- `ntoskrnl!FsRtlCheckOplockEx` at `0x140319779`
- `ntoskrnl!FsRtlCheckOplockEx` at `0x14031bfef`
- `ntoskrnl!FsRtlCheckOplockEx` at `0x140319779`
- `ntoskrnl!FsRtlCheckOplockEx` at `0x14031bfef`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14031c21e`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14031c426`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14031c5c4`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140343647`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14031c21e`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14031c426`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14031c5c4`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140343647`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x14031c22a`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x14031c432`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x14031c5d0`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140343653`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x14031c22a`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x14031c432`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x14031c5d0`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140343653`

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
  char v15; // al
  __int64 v16; // rdx
  __int64 v17; // r8
  unsigned int v18; // r8d
  _DWORD *p_Resource; // r14
  char v20; // al
  int *v21; // rbx
  int v22; // ecx
  char v23; // r12
  struct _LCB *FcbReleases; // r14
  struct _FCB *v25; // rbx
  int *v26; // rdx
  unsigned int v27; // r8d
  char v28; // r8
  __int64 v29; // rcx
  PMRX_NET_ROOT pNetRoot; // rax
  unsigned __int8 IsLinkDeleteable; // al
  int v32; // eax
  bool v33; // al
  PMRX_NET_ROOT v34; // rax
  NTSTATUS v35; // edi
  bool v36; // al
  PFILE_OBJECT v37; // r8
  struct _VCB *v38; // rbx
  __int64 v39; // rdx
  __int64 v40; // rcx
  __int64 v41; // r9
  _BYTE *v42; // rcx
  struct _FCB *v43; // rbx
  NTSTATUS v44; // r10d
  _BYTE *v45; // r11
  __int16 v46; // cx
  struct _FILE_OBJECT *v47; // rcx
  int *v48; // rbx
  struct _FCB *QuadPart; // rax
  struct _IRP_CONTEXT *v50; // rcx
  __int64 v51; // rax
  struct _FCB *v52; // rax
  PNON_PAGED_FCB NonPaged; // rax
  struct _IRP_CONTEXT *v54; // rcx
  int v55; // eax
  __int16 v56; // cx
  struct _KPROCESS *RequestorProcess; // rax
  __int64 v58; // rax
  char v59; // al
  char v60; // dl
  NTSTATUS v61; // edx
  char v62; // r12
  LARGE_INTEGER *p_FileSize; // rcx
  LARGE_INTEGER *v64; // rax
  __int64 v65; // rbx
  char v66; // di
  __int64 v67; // rax
  _QWORD *v68; // rdx
  __int64 v69; // r9
  unsigned int v70; // r8d
  char v71; // r12
  __int64 v72; // rcx
  int v73; // eax
  struct IndexSCB *v74; // rdi
  struct _FCB *v75; // rbx
  struct _UNICODE_STRING *v76; // rdx
  struct _FCB *v77; // rax
  PFILE_OBJECT v78; // rbx
  int v79; // eax
  struct _FCB *v80; // r10
  unsigned __int8 v81; // cl
  PFILE_OBJECT v82; // rbx
  unsigned __int8 v83; // r8
  char *v84; // rbx
  PFILE_OBJECT v85; // rbx
  PFILE_OBJECT v86; // rcx
  NTSTATUS v87; // edx
  LARGE_INTEGER AllocationSize; // rdx
  __int64 v90; // rax
  __int64 v91; // r8
  __int64 v92; // rax
  DWORD v93; // eax
  int v94; // ecx
  __int64 v95; // rax
  __int64 v96; // rax
  __int64 v97; // rcx
  struct _CC_FILE_SIZES *v98; // rdx
  NTSTATUS v99; // eax
  DWORD LowPart; // edx
  int v101; // ecx
  ULONG v102; // eax
  int v103; // ecx
  struct _IRP_CONTEXT *v104; // rcx
  __int16 v105; // ax
  int v106; // ecx
  int v107; // eax
  ULONG v108; // eax
  ULONG v109; // edx
  bool v110; // cf
  struct _IRP_CONTEXT *v111; // rcx
  const __int64 *v112; // rdx
  __int64 v113; // rax
  struct _FCB *i; // rax
  int v115; // ecx
  _DWORD *v117; // rdx
  ULONG_PTR v118; // rcx
  ULONG v119; // r8d
  __int64 v120; // rdx
  __int64 v121; // rcx
  int ActivityIdIrp; // eax
  _BYTE *v123; // rdx
  _OWORD *ActivityIdThread; // rax
  PIRP v125; // rax
  char v126; // r11
  __int64 v127; // rdi
  struct _FAST_MUTEX *v128; // rbx
  __int64 v129; // r11
  _DWORD *v130; // rdi
  unsigned int v131; // eax
  PFILE_OBJECT v132; // r14
  SECTION_OBJECT_POINTERS *v133; // rcx
  int v134; // eax
  char v135; // si
  __int64 v136; // rdi
  struct _FAST_MUTEX *v137; // rbx
  struct _UNICODE_STRING *v138; // r14
  unsigned __int8 v139; // r8
  int v140; // eax
  NTSTATUS v141; // edi
  struct _FCB *v142; // rsi
  PMRX_NET_ROOT v143; // rbx
  unsigned int v144; // ebx
  __int64 v145; // rax
  __int64 v147; // rax
  int WatchTree; // [rsp+20h] [rbp-1F8h]
  char v149; // [rsp+60h] [rbp-1B8h]
  NTSTATUS Status[2]; // [rsp+64h] [rbp-1B4h] BYREF
  char v151; // [rsp+6Ch] [rbp-1ACh]
  __int64 v152; // [rsp+70h] [rbp-1A8h]
  _BYTE *v153; // [rsp+78h] [rbp-1A0h]
  struct _FCB *v154; // [rsp+80h] [rbp-198h]
  struct _VCB *v155; // [rsp+88h] [rbp-190h]
  struct _IRP_CONTEXT *v156; // [rsp+90h] [rbp-188h]
  PVOID FsContext; // [rsp+98h] [rbp-180h]
  PFILE_OBJECT FileObject; // [rsp+A0h] [rbp-178h]
  unsigned __int8 v159; // [rsp+A8h] [rbp-170h]
  char v160; // [rsp+A9h] [rbp-16Fh]
  __int64 v161; // [rsp+B0h] [rbp-168h]
  struct _LCB *v162; // [rsp+B8h] [rbp-160h] BYREF
  char v163; // [rsp+C0h] [rbp-158h]
  bool v164; // [rsp+C1h] [rbp-157h]
  unsigned __int8 v165; // [rsp+C2h] [rbp-156h]
  char v166; // [rsp+C3h] [rbp-155h]
  char *v167; // [rsp+C8h] [rbp-150h]
  struct IndexSCB *InternalSrvOpen; // [rsp+D0h] [rbp-148h] BYREF
  struct _IRP_CONTEXT *v169; // [rsp+D8h] [rbp-140h]
  __int64 v170; // [rsp+E0h] [rbp-138h]
  struct _FCB *v171; // [rsp+E8h] [rbp-130h]
  PFILE_OBJECT v172; // [rsp+F0h] [rbp-128h]
  _DWORD *v173; // [rsp+F8h] [rbp-120h]
  unsigned __int8 v174[8]; // [rsp+100h] [rbp-118h] BYREF
  PIRP Irp; // [rsp+108h] [rbp-110h]
  _QWORD *v176; // [rsp+110h] [rbp-108h] BYREF
  int v177; // [rsp+118h] [rbp-100h]
  struct _LCB *v178; // [rsp+120h] [rbp-F8h] BYREF
  int *v179; // [rsp+128h] [rbp-F0h]
  struct _CC_FILE_SIZES *v180; // [rsp+130h] [rbp-E8h]
  _DWORD *v181; // [rsp+138h] [rbp-E0h]
  PVOID *p_FsContext; // [rsp+140h] [rbp-D8h]
  int *v183; // [rsp+148h] [rbp-D0h]
  int v184; // [rsp+150h] [rbp-C8h]
  int v185; // [rsp+154h] [rbp-C4h]
  LARGE_INTEGER *v186; // [rsp+158h] [rbp-C0h]
  struct _UNICODE_STRING v187; // [rsp+160h] [rbp-B8h]
  char *v188; // [rsp+170h] [rbp-A8h]
  struct _LCB *v189; // [rsp+178h] [rbp-A0h]
  struct _CC_FILE_SIZES v190; // [rsp+180h] [rbp-98h] BYREF
  LONGLONG *v191; // [rsp+198h] [rbp-80h]
  _QWORD *v192; // [rsp+1A0h] [rbp-78h]
  struct _UNICODE_STRING v193; // [rsp+1B0h] [rbp-68h] BYREF
  _BYTE v194[40]; // [rsp+1C0h] [rbp-58h] BYREF

  v3 = a1;
  v156 = a1;
  Irp = a2;
  Status[1] = 0;
  v162 = 0;
  InternalSrvOpen = 0;
  v4 = 0;
  v152 = 0;
  LOWORD(Status[0]) = 1;
  a2->IoStatus.Information = 2;
  v5 = a2->Tail.Overlay.CurrentStackLocation->FileObject;
  FileObject = v5;
  v172 = v5;
  p_FsContext = &v5->FsContext;
  v6 = (__int64)v5->FsContext;
  if ( v6 )
  {
    v7 = *(struct _VCB **)(v6 + 144);
    v155 = v7;
    v169 = v7;
    FsContext2 = (unsigned int *)v5->FsContext2;
    FsContext = FsContext2;
    v167 = (char *)FsContext2;
    v9 = *(struct _FCB **)(v6 + 136);
    v154 = v9;
    v171 = v9;
    if ( FsContext2 )
      v10 = *((_BYTE *)FsContext2 + 80);
    else
      v10 = 5;
  }
  else
  {
    v7 = 0;
    v155 = 0;
    v169 = 0;
    v9 = 0;
    v154 = 0;
    v171 = 0;
    FsContext2 = 0;
    FsContext = 0;
    v167 = 0;
    v10 = 1;
  }
  v159 = v10;
  if ( ((v10 - 1) & 0xFB) == 0 )
  {
    v5->Flags |= 0x4000u;
    v147 = *((_QWORD *)v3 + 1);
    if ( (v147 & 0x100000000LL) != 0 )
      *((_QWORD *)v3 + 1) = v147 | 0x200000000LL;
    else
      RefsCompleteRequest((PSECURITY_SUBJECT_CONTEXT *)v3, Irp, 0);
    return 0;
  }
  v11 = FsContext2 + 1;
  v12 = BYTE1(Status[0]) & 0xEF | (2 * (FsContext2[1] & 8));
  v149 = v12;
  BYTE1(Status[0]) = v12;
  *((_DWORD *)v3 + 158) = FsContext2[21];
  if ( v10 != 4 )
  {
    if ( (*((_DWORD *)v3 + 2) & 0x100LL) == 0 )
    {
      v16 = *((_QWORD *)v3 + 13);
      if ( (*(_QWORD *)(v16 + 8) & 0x20000000000LL) == 0 )
      {
        MsInitializeFastResourceOwnerEntry(v16 + 160);
        *(_QWORD *)(v16 + 8) |= v17;
      }
      if ( !(unsigned __int8)MsAcquireFastResourceSharedInternal<0>(
                               (char *)v7 + 1312,
                               v16 + 160,
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
        RefsRaiseStatusInternal(v3, -1073741608, v18);
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
    v4 = v152;
    v7 = v155;
  }
  v181 = p_FsContext;
  *(_QWORD *)v194 = v6;
  v170 = v6;
  v180 = (struct _CC_FILE_SIZES *)v6;
  v160 = v10;
  v179 = (int *)v11;
  v13 = (_DWORD *)((char *)v7 + 24);
  v161 = (__int64)v7 + 24;
  v14 = *((_DWORD *)v7 + 6);
  if ( (v14 & 0x8000823) == 1 && (*(_DWORD *)(v6 + 300) & 0x4000) == 0 )
  {
    if ( *((_QWORD *)v7 + 14) )
    {
      v15 = MsAreWritesDoomed();
      v13 = (_DWORD *)v161;
      if ( !v15 )
        LOBYTE(v4) = v4 | 4;
    }
    else
    {
      v13 = (_DWORD *)v161;
    }
  }
  if ( (v14 & 0x2000020) != 0
    || (p_Resource = &v9->spacer.Resource, v153 = &v9->spacer.Resource, ((__int64)v9->Header.Resource & 0x20) != 0) )
  {
    p_Resource = &v9->spacer.Resource;
    v153 = &v9->spacer.Resource;
    v20 = 8;
  }
  else
  {
    v20 = 0;
  }
  v173 = p_Resource;
  LOBYTE(v4) = v20 | v4 & 0xF7;
  v152 = v4;
  BYTE2(Status[0]) = v4;
  v151 = v4;
  if ( (*v13 & 0x4000000) != 0 )
  {
    v12 |= 4u;
    v149 = v12;
    BYTE1(Status[0]) = v12;
  }
  RefsAcquireFcbWithPaging((__int64)v3, (__int64)v9, v6, 0x10u);
  v21 = v179;
  v22 = *v179;
  if ( *v179 < 0 )
  {
    --*(_DWORD *)(v6 + 344);
    *v21 &= ~0x80000000;
    v22 = *v21;
  }
  v183 = (int *)((char *)FsContext + 8);
  v176 = (char *)FsContext + 8;
  if ( (*((_DWORD *)FsContext + 2) & 4) != 0 || (v23 = 1, (*p_Resource & 0x800LL) != 0) )
    v23 = 9;
  LOBYTE(Status[0]) = v23;
  FcbReleases = (struct _LCB *)*((_QWORD *)FsContext + 9);
  v162 = FcbReleases;
  v189 = FcbReleases;
  v178 = FcbReleases;
  if ( !FcbReleases || (*((_DWORD *)FcbReleases + 1) & 2) != 0 )
  {
    FcbReleases = 0;
    v162 = 0;
    v178 = 0;
    *v21 = v22 & 0xFFFBFFFF;
  }
  else
  {
    InternalSrvOpen = (struct IndexSCB *)*((_QWORD *)FcbReleases + 3);
  }
  v25 = v154;
  if ( !RefsIsFileOpen(v154) && ((__int64)v154->spacer.Resource & 1) == 0 )
  {
LABEL_581:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_08039d2264c939b1b5c93e03467edfa1_Traceguids, 3221225768LL);
    }
    if ( (_BYTE)RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741528, v3, "Cleanup.c", 0x5B8u);
    RefsRaiseStatusInternal(v3, -1073741528, v27);
    goto LABEL_588;
  }
  v28 = v151;
  if ( (v151 & 4) == 0 || (v151 & 8) != 0 || ((__int64)v154->spacer.Resource & 1) != 0 )
    goto LABEL_101;
  v29 = (unsigned int)*v179;
  if ( (v29 & 0x40000) == 0 )
    goto LABEL_74;
  if ( (v29 & 2) == 0 )
  {
    if ( MmFlushImageSection((PSECTION_OBJECT_POINTERS)(*(_QWORD *)(v6 + 248) + 8LL), MmFlushForDelete) )
    {
      if ( (*(_DWORD *)(v6 + 152) & 2) == 0 )
        _InterlockedOr((volatile signed __int32 *)(v6 + 152), 2u);
      v12 |= 0x20u;
      v149 = v12;
      BYTE1(Status[0]) = v12;
    }
    goto LABEL_73;
  }
  v174[0] = 0;
  LOBYTE(v29) = !FcbReleases || (*((_DWORD *)FcbReleases + 1) & 1) == 0;
  v163 = v29;
  if ( (_BYTE)v29 )
  {
    pNetRoot = v154->pNetRoot;
    if ( !pNetRoot[2].pSrvCall && pNetRoot[2].Context )
    {
      IsLinkDeleteable = RefsIsLinkDeleteable(v3, v154, v174);
      v29 = IsLinkDeleteable;
      v163 = IsLinkDeleteable;
      v26 = v183;
    }
    if ( (_BYTE)v29 )
    {
      v32 = *v26;
      if ( (*v26 & 8) != 0 )
      {
        v23 |= 8u;
        LOBYTE(Status[0]) = v23;
        *v26 = v32 | 4;
      }
      v33 = 0;
      v164 = 0;
      if ( LODWORD(v25->VNetRoot) <= 1 )
      {
        v33 = RefsTryCloseSectionOnDelete((struct _IRP_CONTEXT *)v29, v25, (v23 & 8) != 0);
        v164 = v33;
        v23 |= 0x80u;
        LOBYTE(Status[0]) = v23;
        if ( !v33 )
          goto LABEL_63;
        if ( (v23 & 8) != 0 )
        {
          v23 |= 0x40u;
          LOBYTE(Status[0]) = v23;
          v164 = 0;
          goto LABEL_63;
        }
      }
      if ( !v33 )
      {
LABEL_63:
        if ( FcbReleases && (*((_DWORD *)FcbReleases + 1) & 2) == 0 )
          --LODWORD(v25->VNetRoot);
        *((_DWORD *)FcbReleases + 1) |= 1u;
        v12 |= 0x20u;
        v149 = v12;
        BYTE1(Status[0]) = v12;
        v34 = v25->pNetRoot;
        if ( !v34[2].pSrvCall && v34[2].Context )
          FsRtlNotifyFilterChangeDirectory(
            *((PNOTIFY_SYNC *)v155 + 108),
            (PLIST_ENTRY)v155 + 53,
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
  *v179 &= ~0x40000u;
  v25 = v154;
LABEL_74:
  if ( (v12 & 0x20) == 0
    || ((v29 = *(unsigned __int16 *)(v6 + 216), (_WORD)v29 != 128) && (_WORD)v29 != 176
     || *(_WORD *)v6 != 2053
     || *(_QWORD *)(*(_QWORD *)(v6 + 144) + 72LL) == v6)
    && ((_WORD)v29 != 160
     || *(_WORD *)(v6 + 224) != 8
     || memcmp(*(const void **)(v6 + 232), RefsFileNameIndex.Buffer, 8u)
     || (v29 = 2051, (unsigned __int16)(*(_WORD *)v6 - 2051) > 1u))
    || (Status[1] = FsRtlCheckOplockEx(
                      (POPLOCK)(v6 + 88),
                      Irp,
                      0x20u,
                      v3,
                      RefsOplockComplete,
                      RefsCleanupOplockPrePostIrp),
        Status[1] != 259) )
  {
    if ( LODWORD(v25->VNetRoot) || LODWORD(v25->spacer.PagingIoResource) != 1 )
    {
      v28 = v151;
      if ( (*(_DWORD *)(v6 + 152) & 2) != 0 && *(_DWORD *)(v6 + 160) == 1 )
      {
        v12 |= 2u;
        v149 = v12;
        BYTE1(Status[0]) = v12;
      }
    }
    else
    {
      v23 |= 0x10u;
      LOBYTE(Status[0]) = v23;
      if ( v23 >= 0 && (v23 & 8) != 0 )
      {
        v23 |= 0x80u;
        LOBYTE(Status[0]) = v23;
        v36 = RefsTryCloseSectionOnDelete((struct _IRP_CONTEXT *)v29, v25, (v23 & 8) != 0);
        v28 = v151;
        if ( v36 )
        {
          v23 |= 0x40u;
          LOBYTE(Status[0]) = v23;
        }
      }
      else
      {
        v28 = v151;
      }
    }
LABEL_101:
    if ( v159 != 2 )
    {
      if ( v159 != 3 )
      {
        if ( v159 != 4 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_08039d2264c939b1b5c93e03467edfa1_Traceguids, v159);
          }
          KeBugCheckEx(0x149u, 0x70B4Bu, v159, 0, 0);
        }
        v37 = FileObject;
        FileObject->Flags |= 0x4000u;
        v38 = v155;
        if ( *((PFILE_OBJECT *)v155 + 110) == v37 )
        {
          v39 = *((_QWORD *)v155 + 9);
          if ( v39 )
          {
            RefsAcquireExclusiveFcb(v3, *(_QWORD *)(v39 + 136), *((_QWORD *)v155 + 9), 0);
            *((_QWORD *)v155 + 732) = 0x7FFFFFFFFFFFFFFFLL;
            *((_QWORD *)v38 + 733) = 0;
            *((_QWORD *)v38 + 110) = 0;
            RefsReleaseFcb(v3, *(struct _FCB **)(*((_QWORD *)v38 + 9) + 136LL));
            v37 = FileObject;
          }
        }
        if ( (*(_DWORD *)v161 & 2) != 0 )
        {
          v176 = (_QWORD *)((char *)v38 + 872);
          v40 = *((_QWORD *)v38 + 109);
          if ( (PFILE_OBJECT)(v40 & 0xFFFFFFFFFFFFFFFEuLL) == v37 )
          {
            if ( (v40 & 1) != 0 )
            {
              RefsSendBeginDismountEvent(v3, v155, v37, 3);
              v38 = v155;
              RefsPerformDismountOnVcb((CHAR *)v3, (unsigned __int64)v155, 1, 0, 3, 0);
            }
            else if ( (v37->Flags & 0x1000) != 0 )
            {
              if ( (v151 & 4) != 0 && (v151 & 8) == 0 && (*v153 & 1) == 0 )
              {
                RefsReleaseScbWithPaging(v3, (struct _SCB *)v6);
                if ( RefsUseFlushVolumeParallel )
                  RefsFlushVolumeParallel(v3, v38, 12);
                else
                  RefsFlushVolumeOriginal(v3, v38, 12);
                RefsAcquireExclusiveFcb(v3, *(_QWORD *)(v6 + 136), v6, 0);
              }
              if ( *((_DWORD *)v38 + 54) == 1 && *((_DWORD *)v38 + 55) - *((_DWORD *)v38 + 57) == 1 )
              {
                RefsSendBeginDismountEvent(v3, v155, v37, 3);
                RefsReleaseScbWithPaging(v3, (struct _SCB *)v6);
                if ( RefsUseFlushVolumeParallel )
                  RefsFlushVolumeParallel(v3, v155, 144);
                else
                  RefsFlushVolumeOriginal(v3, v155, 144);
                RefsAcquireExclusiveFcb(v3, *(_QWORD *)(v6 + 136), v6, 0);
                v38 = v155;
                RefsPerformDismountOnVcb((CHAR *)v3, (unsigned __int64)v155, 1, 0, 3, 0);
                v41 = v152;
                v42 = v153;
                goto LABEL_131;
              }
            }
            v42 = v153;
            v41 = v152;
LABEL_131:
            *(_DWORD *)v161 &= 0xFFFF7FFD;
            *v176 = 0;
            LOBYTE(v41) = v41 | 1;
            v152 = v41;
            BYTE2(Status[0]) = v41;
            if ( (v41 & 4) != 0
              && (v41 & 8) == 0
              && (*v42 & 1) == 0
              && !Status[1]
              && *((_DWORD *)v38 + 301) == -1073741202 )
            {
              *((_DWORD *)v38 + 301) = 0;
              RefsPostSpecial(
                v3,
                v38,
                (void (*)(struct _IRP_CONTEXT *, void *))RefsDeleteUsnSpecial,
                (char *)v38 + 1192,
                1u,
                0);
              v161 = 4;
              v43 = v154;
              v41 = v152;
              v44 = Status[1];
              v45 = v153;
              goto LABEL_177;
            }
            v161 = 4;
            v43 = v154;
            v44 = Status[1];
            goto LABEL_176;
          }
          goto LABEL_174;
        }
        goto LABEL_340;
      }
      RefsSnapshotScb(v3, v6, 0);
      v46 = *(_WORD *)(v6 + 216);
      if ( (v46 == 128 || v46 == 176) && *(_WORD *)v6 == 2053 && *(_QWORD *)(*(_QWORD *)(v6 + 144) + 72LL) != v6
        || v46 == 160
        && *(_WORD *)(v6 + 224) == 8
        && !memcmp(*(const void **)(v6 + 232), RefsFileNameIndex.Buffer, 8u)
        && (unsigned __int16)(*(_WORD *)v6 - 2051) <= 1u )
      {
        FsRtlCheckOplock((POPLOCK)(v6 + 88), Irp, 0, 0, 0);
      }
      v47 = FileObject;
      FileObject->Flags |= 0x4000u;
      v48 = v179;
      if ( (*v179 & 0x800000) != 0 )
      {
        FsRtlNotifyCleanup(*((PNOTIFY_SYNC *)v155 + 108), (PLIST_ENTRY)v155 + 53, FsContext);
        *v48 &= ~0x800000u;
        _InterlockedDecrement((volatile signed __int32 *)v155 + 354);
        v47 = FileObject;
      }
      v45 = v153;
      if ( (v151 & 4) == 0 || (v151 & 8) != 0 || (*v153 & 1) != 0 )
      {
LABEL_339:
        v43 = v154;
LABEL_342:
        v161 = 4;
        v12 = v149;
        v41 = v152;
        v44 = Status[1];
        goto LABEL_177;
      }
      RefsUpdateScbFromFileObject(v47, (struct _SCB *)v6, 1u);
      if ( *(_WORD *)v6 == 2051 )
      {
        if ( (v23 & 0x10) == 0 || (v23 & 0x40) != 0 )
        {
          if ( (*(_DWORD *)v176 & 4) != 0 )
          {
            if ( RefsHardlinksSupported(*((struct _VCB **)v3 + 8)) )
            {
              if ( FcbReleases )
              {
                v55 = *((_DWORD *)FcbReleases + 1);
                if ( (v55 & 1) != 0 && (v55 & 2) == 0 )
                {
                  v43 = v154;
                  RefsPosixDeleteLink(v3, v154, (__int64)FsContext, (__int64)InternalSrvOpen, (__int64)Status);
                  v161 = 4;
                  v41 = BYTE2(Status[0]);
                  v152 = BYTE2(Status[0]);
                  v12 = BYTE1(Status[0]);
                  v149 = BYTE1(Status[0]);
                  v23 = Status[0];
                  v44 = Status[1];
                  goto LABEL_176;
                }
              }
            }
          }
          v43 = v154;
          if ( HIDWORD(v154->spacer.PagingIoResource) == 1
            && (v23 & 1) != 0
            && *((_DWORD *)v155 + 888) <= RefsMaxDelayedCloseCount
            && (*(_DWORD *)(v6 + 152) & 0x1000000) == 0 )
          {
            v45 = v153;
            if ( (*(_DWORD *)(v6 + 152) & 0x200000) == 0 )
            {
              _InterlockedOr((volatile signed __int32 *)(v6 + 152), 0x200000u);
              v161 = 4;
              v41 = v152;
              v44 = Status[1];
              goto LABEL_177;
            }
            goto LABEL_342;
          }
          goto LABEL_341;
        }
        if ( !FcbReleases )
        {
          LODWORD(v181) = 0;
          QuadPart = (struct _FCB *)v154->Header.FileSize.QuadPart;
          v180 = (struct _CC_FILE_SIZES *)QuadPart;
          while ( QuadPart != (struct _FCB *)&v154->spacer.FileSize )
          {
            FcbReleases = (struct _LCB *)QuadPart[-1].FcbReleases;
            if ( (QuadPart[-1].FcbReleases[1] & 2) == 0 )
              goto LABEL_161;
            QuadPart = *(struct _FCB **)&QuadPart->Header.NodeTypeCode;
          }
          FcbReleases = 0;
LABEL_161:
          v162 = FcbReleases;
          if ( FcbReleases )
            InternalSrvOpen = (struct IndexSCB *)*((_QWORD *)FcbReleases + 3);
        }
        if ( RefsIsTransactionActive(v3) )
          RefsCheckpointCurrentTransaction(v50);
        if ( InternalSrvOpen )
        {
          RefsAcquireExclusiveScb(v3, InternalSrvOpen, 0);
          v51 = v152;
          LOBYTE(v51) = v152 | 0x80;
          v152 = v51;
          BYTE2(Status[0]) = v51;
        }
        RefsDeleteFile(v3, v154, InternalSrvOpen, 0, 0);
        v12 = v149;
        v45 = v153;
        if ( !Status[1] )
        {
          if ( (v149 & 0x10) == 0 )
          {
            if ( InternalSrvOpen )
              v52 = (struct _FCB *)*((_QWORD *)InternalSrvOpen + 17);
            else
              v52 = 0;
            RefsReportDirNotify(
              v155,
              v155,
              (struct _UNICODE_STRING *)FsContext + 1,
              *((unsigned __int16 *)FsContext + 16),
              0,
              0,
              2u,
              2u,
              v52);
            v12 = v149;
          }
          *v179 &= 0xFFFFFF8F;
LABEL_174:
          v161 = 4;
          v43 = v154;
          v44 = Status[1];
LABEL_175:
          v41 = v152;
LABEL_176:
          v45 = v153;
          goto LABEL_177;
        }
        goto LABEL_339;
      }
LABEL_340:
      v43 = v154;
LABEL_341:
      v45 = v153;
      goto LABEL_342;
    }
    v161 = v6 + 152;
    if ( (*(_DWORD *)(v6 + 152) & 0x20) == 0
      && (v28 & 4) != 0
      && (v28 & 8) == 0
      && (*(_BYTE *)(*(_QWORD *)(v6 + 136) + 8LL) & 1) == 0 )
    {
      RefsUpdateScbFromAttribute(v3, (struct _SCB *)v6, 0);
    }
    v181 = (_DWORD *)v161;
    RefsSnapshotScb(v3, v6, 0);
    v183 = (int *)(v6 + 216);
    v56 = *(_WORD *)(v6 + 216);
    if ( (v56 == 128 || v56 == 176) && *(_WORD *)v6 == 2053 && *(_QWORD *)(*(_QWORD *)(v6 + 144) + 72LL) != v6
      || v56 == 160
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
      if ( (*(_DWORD *)v161 & 0x20) == 0 )
        goto LABEL_222;
      if ( FsRtlOplockIsFastIoPossible((POPLOCK)(v6 + 88)) )
      {
        if ( *(__int16 *)(v6 + 256) >= 0 )
        {
          v58 = *(_QWORD *)(v6 + 384);
          if ( (!v58 || !*(_BYTE *)(v58 + 16))
            && ((_DWORD)p_FsContext[3] & 0x2000000) == 0
            && (*(_BYTE *)(*(_QWORD *)(v6 + 136) + 8LL) & 0x20) == 0 )
          {
            v59 = 1;
LABEL_224:
            *(_BYTE *)(v6 + 5) = v59;
            v60 = v151;
            v45 = v153;
            if ( (v151 & 4) == 0 || (v151 & 8) != 0 || (*v153 & 1) != 0 )
            {
              v37 = FileObject;
              FileObject->Flags |= 0x4000u;
              if ( (v60 & 4) == 0 || (*v45 & 1) != 0 || (*(_DWORD *)(v6 + 300) & 0x40) != 0 )
              {
                v41 = v152;
                LOBYTE(v41) = v152 | 0x20;
                v152 = v41;
                BYTE2(Status[0]) = v41;
                v161 = 4;
                v43 = v154;
                v44 = Status[1];
              }
              else
              {
                v161 = 4;
                v43 = v154;
                v41 = v152;
                v44 = Status[1];
              }
              goto LABEL_177;
            }
            RefsUpdateScbFromFileObject(FileObject, (struct _SCB *)v6, 1u);
            v37 = FileObject;
            FileObject->Flags |= 0x4000u;
            v61 = Status[1];
            if ( Status[1] )
              goto LABEL_340;
            v166 = 0;
            if ( (v23 & 0x40) == 0
              && (!FcbReleases || (*((_DWORD *)FcbReleases + 1) & 1) != 0 && *((_DWORD *)FcbReleases + 26) == 1) )
            {
              if ( (v23 & 0x10) != 0 )
              {
                v62 = v23 & 0xFE;
                LOBYTE(Status[0]) = v62;
                if ( (*(_DWORD *)v153 & 0x8000LL) != 0 )
                {
                  RefsPostSpecial(
                    v3,
                    v155,
                    (void (*)(struct _IRP_CONTEXT *, void *))RefsDeleteUsnSpecial,
                    (char *)v155 + 1192,
                    1u,
                    0);
                  v23 = v62 & 0xEF;
                  LOBYTE(Status[0]) = v23;
                  ++LODWORD(v25->VNetRoot);
                  if ( FcbReleases )
                  {
                    *((_DWORD *)FcbReleases + 1) &= 0xFFFFFFBE;
                  }
                  else
                  {
                    while ( 1 )
                    {
                      LODWORD(p_FsContext) = 0;
                      p_FileSize = &v25->Header.FileSize;
                      if ( FcbReleases )
                      {
                        v186 = (LARGE_INTEGER *)((char *)FcbReleases + 32);
                        v64 = (LARGE_INTEGER *)*((_QWORD *)FcbReleases + 4);
                        v186 = v64;
                        v191 = (LONGLONG *)v64;
                      }
                      else
                      {
                        v64 = (LARGE_INTEGER *)p_FileSize->QuadPart;
                        v192 = (_QWORD *)p_FileSize->QuadPart;
                      }
                      while ( v64 != p_FileSize )
                      {
                        FcbReleases = (struct _LCB *)&v64[-4];
                        if ( (v64[-4].HighPart & 2) == 0 )
                          goto LABEL_243;
                        v64 = (LARGE_INTEGER *)v64->QuadPart;
                      }
                      FcbReleases = 0;
LABEL_243:
                      v162 = FcbReleases;
                      if ( !FcbReleases )
                        break;
                      *((_DWORD *)FcbReleases + 1) &= 0xFFFFFFBE;
                    }
                  }
                  goto LABEL_269;
                }
                v61 = RefsCompleteFileDeletion(
                        v3,
                        v25,
                        (struct _SCB *)v6,
                        (struct _CCB *)FsContext,
                        &InternalSrvOpen,
                        &v162,
                        (struct REFS_CLEANUP_FLAGS *)Status);
                Status[1] = v61;
                FcbReleases = v162;
LABEL_246:
                v65 = BYTE2(Status[0]);
                v152 = BYTE2(Status[0]);
                v12 = BYTE1(Status[0]);
                v149 = BYTE1(Status[0]);
                v23 = Status[0];
LABEL_271:
                v176 = (_QWORD *)(v6 + 160);
                if ( *(_DWORD *)(v6 + 160) == 1 )
                {
                  v80 = v154;
                  if ( LODWORD(v154->VNetRoot) )
                  {
                    if ( !v61 )
                    {
                      v81 = 0;
                      v165 = 0;
                      if ( (v12 & 2) != 0 )
                      {
                        if ( *(_WORD *)v183 )
                        {
                          v81 = RefsDeleteResidentDataScbAndCommit(v3, (struct _SCB *)v6, (unsigned __int8)v37);
                          v165 = v81;
                          v80 = v154;
                          v61 = Status[1];
                        }
                        if ( v81 )
                        {
                          if ( !v61 )
                          {
                            v23 |= 4u;
                            LOBYTE(Status[0]) = v23;
                          }
                          LOBYTE(v65) = v65 | 0x20;
                          v152 = v65;
                          BYTE2(Status[0]) = v65;
                          RefsUpdateFileTimestampsForChange(v80, FsContext, 0x400000, 0);
                          v82 = FileObject;
                          FileObject->Flags &= ~0x4000u;
                          RefsUpdateScbFromFileObject(v82, (struct _SCB *)v6, 1u);
                          v82->Flags |= 0x4000u;
                          v84 = *(char **)(v6 + 368);
                          v186 = (LARGE_INTEGER *)v84;
                          if ( v84 )
                          {
                            v188 = v84;
                            if ( *((_DWORD *)v84 + 41) == 1 )
                              RefsDeleteResidentDataScbAndCommit(v3, (struct _SCB *)v84, v83);
                            LOBYTE(WatchTree) = 0;
                            RefsDecrementCloseCounts(v3, v84, 0, 0, WatchTree, 0);
                          }
                        }
                      }
                      else if ( *(_WORD *)v183 )
                      {
                        if ( (*v181 & 4) != 0 )
                        {
                          if ( (v12 & 0x40) == 0 && (*(_DWORD *)v153 & 0x100LL) == 0 )
                            RefsPrepareForUpdateDuplicate(v3, v154, &v178, &InternalSrvOpen, 1u, 0);
                          RefsWriteFileSizes(v3, (struct _SCB *)v6, 0, 2u, WatchTree);
                          RefsCheckpointCurrentTransaction(v3);
                          v85 = FileObject;
                          FileObject->Flags &= ~0x4000u;
                          RefsUpdateScbFromFileObject(v85, (struct _SCB *)v6, 1u);
                          v85->Flags |= 0x4000u;
                        }
                        if ( (*v181 & 0x40) != 0 )
                        {
                          v161 = 4;
                          RefsWriteFileSizes(v3, (struct _SCB *)v6, 0, 4u, WatchTree);
                          RefsCheckpointCurrentTransaction(v3);
                          v43 = v154;
                          v86 = FileObject;
                          v37 = (PFILE_OBJECT)v153;
                          goto LABEL_293;
                        }
                      }
                    }
                  }
                }
                v37 = (PFILE_OBJECT)v153;
                v86 = FileObject;
                v43 = v154;
                v161 = 4;
LABEL_293:
                v87 = Status[1];
                if ( !Status[1]
                  && *(_DWORD *)v176 == 1
                  && LODWORD(v43->VNetRoot)
                  && (v12 & 2) == 0
                  && v86->SectionObjectPointer == (PSECTION_OBJECT_POINTERS)(*(_QWORD *)(v6 + 248) + 8LL)
                  && *(_WORD *)v183
                  && (*v181 & 1) != 0 )
                {
                  v12 |= 0x80u;
                  v149 = v12;
                  BYTE1(Status[0]) = v12;
                  if ( (v12 & 0x40) == 0 && (*(_DWORD *)&v37->Type & 0x100LL) == 0 )
                    RefsPrepareForUpdateDuplicate(v3, v43, &v178, &InternalSrvOpen, 1u, 0);
                  if ( *(_WORD *)v6 == 2053 && *(_QWORD *)(v6 + 432) )
                  {
                    AllocationSize = v180[1].AllocationSize;
                    if ( AllocationSize.QuadPart )
                    {
                      v90 = *((unsigned int *)v155 + 136);
                      v91 = (v90 + *(_QWORD *)(v6 + 32)) >> *((_BYTE *)v155 + 552);
                      if ( (AllocationSize.QuadPart + v90) >> *((_BYTE *)v155 + 552) != v91 )
                      {
                        RefsDeleteAllocation(
                          v3,
                          (struct _SCB *)v6,
                          v91,
                          0x7FFFFFFFFFFFFFFFLL,
                          *(_WORD *)(v6 + 256) >= 0);
                        RefsCheckpointCurrentTransaction(v3);
                        *(_QWORD *)v153 |= 0x40000uLL;
                      }
                      v92 = v152;
                      LOBYTE(v92) = v152 | 0x40;
                      v152 = v92;
                      BYTE2(Status[0]) = v92;
                    }
                  }
                  else
                  {
                    v93 = (*(_DWORD *)(v6 + 32) + 7) & 0xFFFFFFF8;
                    if ( v93 < v180[1].AllocationSize.LowPart )
                    {
                      v190 = v180[1];
                      v190.AllocationSize.LowPart = v93;
                      RefsWriteFileSizes(v3, (struct _SCB *)v6, &v190, 1u, WatchTree);
                      RefsCheckpointCurrentTransaction(v3);
                      v180[1].AllocationSize.LowPart = v190.AllocationSize.LowPart;
                    }
                  }
                  RefsUpdateScbFromFileObject(FileObject, (struct _SCB *)v6, 1u);
                  v87 = Status[1];
                }
                v94 = *(_DWORD *)(v6 + 156);
                if ( v94 )
                {
                  if ( *(_DWORD *)v176 == v94 + 1
                    && *(__int16 *)(v6 + 256) >= 0
                    && (*((_BYTE *)FsContext + 88) & 7) != 0 )
                  {
                    v95 = *(_QWORD *)(v6 + 248);
                    if ( *(_QWORD *)(v95 + 8) )
                    {
                      if ( !*(_QWORD *)(v95 + 24)
                        && (FileObject->Flags & 8) == 0
                        && !v87
                        && MmCanFileBeTruncated((PSECTION_OBJECT_POINTERS)(*(_QWORD *)(v6 + 248) + 8LL), 0)
                        && (*(_DWORD *)(*(_QWORD *)(v6 + 136) + 8LL) & 0x100LL) == 0
                        && (v12 & 0x40) == 0 )
                      {
                        RefsCheckpointCurrentTransaction(v3);
                        v23 |= 4u;
                        LOBYTE(Status[0]) = v23;
                        if ( (v152 & 0x80u) != 0LL )
                        {
                          RefsReleaseFcb(v3, *((struct _FCB **)InternalSrvOpen + 17));
                          v96 = v152;
                          LOBYTE(v96) = v152 & 0x7F;
                          v152 = v96;
                          BYTE2(Status[0]) = v96;
                        }
                        if ( *((_QWORD *)v3 + 6) )
                          RefsReleaseSharedResources(v3);
                        RefsFlushAndPurgeScb(v3, (struct _SCB *)v6);
                        *((_DWORD *)v3 + 4) = 0;
                      }
                    }
                  }
                }
                v44 = Status[1];
                if ( Status[1]
                  || HIDWORD(v43->spacer.PagingIoResource) != 1
                  || (v23 & 1) == 0
                  || *((_DWORD *)v155 + 888) > RefsMaxDelayedCloseCount )
                {
                  goto LABEL_175;
                }
                v45 = v153;
                if ( (*v153 & 4) != 0 || (*v181 & 0x1000000) != 0 )
                {
                  v41 = v152;
                }
                else
                {
                  v41 = v152;
                  if ( (*(_DWORD *)(v6 + 152) & 0x200000) == 0 )
                    _InterlockedOr((volatile signed __int32 *)(v6 + 152), 0x200000u);
                }
LABEL_177:
                if ( v160 == 4 )
                  goto LABEL_453;
                NonPaged = v43->NonPaged;
                if ( *((PNON_PAGED_FCB *)&v43->1 + 16) != NonPaged )
                {
                  v54 = *(struct _IRP_CONTEXT **)v45;
                  if ( (*(_QWORD *)v45 & 0x10) != 0 )
                  {
                    *((_QWORD *)&v43->1 + 16) = NonPaged;
LABEL_352:
                    *((_DWORD *)&v43->1 + 43) |= 0x20u;
                    goto LABEL_353;
                  }
                  if ( ((unsigned __int8)v54 & 1) == 0 && RefsCheckLastAccess(v54, v43) )
                  {
                    *(_QWORD *)v45 = v97 | 0x10;
                    *v179 |= 0x10000u;
                    v43 = v154;
                    goto LABEL_352;
                  }
                }
LABEL_353:
                if ( (v41 & 4) == 0 || (v41 & 8) != 0 || (*(_QWORD *)v45 & 1) != 0 )
                {
LABEL_415:
                  if ( (v41 & 0x80u) != 0LL && (v12 & 0x40) == 0 )
                  {
                    RefsReleaseFcb(v3, *((struct _FCB **)InternalSrvOpen + 17));
                    v41 = v152;
                    LOBYTE(v41) = v152 & 0x7F;
                    v152 = v41;
                    BYTE2(Status[0]) = v41;
                  }
                  if ( FileObject->PrivateCacheMap > (PVOID)1
                    || (v41 & 0x20) != 0
                    || (v41 & 0x40) != 0
                    || (v23 & 0x40) != 0 && FileObject->SectionObjectPointer )
                  {
                    v176 = 0;
                    if ( (v41 & 0x40) != 0 )
                      v176 = *(_QWORD **)(v6 + 32);
                    v112 = (const __int64 *)&v176;
                    if ( (v41 & 0x20) == 0 )
                      v112 = 0;
                    RefsUninitializeCacheMap(FileObject, v112, (struct _CACHE_UNINITIALIZE_EVENT *)v37);
                  }
                  if ( (*v153 & 1) == 0 )
                  {
                    v113 = *(_QWORD *)&v43->FcbTableEntry.Path.Length;
                    if ( v113 )
                    {
                      if ( LODWORD(v43->spacer.PagingIoResource) == 1
                        && !Status[1]
                        && (*(_DWORD *)(v113 + 104) || *((struct _FCB **)v3 + 76) == v43 && *((_DWORD *)v3 + 154)) )
                      {
                        for ( i = (struct _FCB *)v43->Header.FastMutex;
                              i != (struct _FCB *)&v43->spacer.FastMutex;
                              i = *(struct _FCB **)&i->Header.NodeTypeCode )
                        {
                          if ( (*(_BYTE *)(&i[-1].FileLock.LockRequestsInProgress + 1) & 0x20) != 0
                            && (i->Header.FileSize.LowPart & 0x40000) != 0 )
                          {
                            goto LABEL_441;
                          }
                        }
                        RefsPostUsnChange(v3, v43, 0x80000000, 0);
                      }
                    }
                  }
LABEL_441:
                  if ( *((_QWORD *)v3 + 76) && !Status[1] )
                  {
                    RefsWriteUsnJournalChanges(v3);
                    RefsCheckpointCurrentTransaction(v3);
                    v23 |= 4u;
                    LOBYTE(Status[0]) = v23;
                  }
                  v115 = 0;
                  v184 = 0;
                  if ( (*(_DWORD *)(v6 + 152) & 4) != 0 )
                  {
                    if ( *(_DWORD *)(v6 + 160) == 1 )
                      v115 = 4;
                    v184 = v115;
                  }
                  if ( v12 < 0 )
                  {
                    v115 |= 1u;
                    v184 = v115;
                  }
                  if ( v115 && (v115 & *(_DWORD *)(v6 + 152)) != 0 )
                    _InterlockedAnd((volatile signed __int32 *)(v6 + 152), ~v115);
LABEL_453:
                  if ( (*v179 & 0x8000000) != 0 )
                  {
                    if ( (v152 & 4) != 0 && (v152 & 8) == 0 && *(_WORD *)v6 == 2053 && *(_QWORD *)(v6 + 432) )
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
                    v23 |= 4u;
                    LOBYTE(Status[0]) = v23;
                    RefsFlushForWriteThrough(v3, v6, 0);
                  }
                  v117 = FsContext;
                  *((_QWORD *)v3 + 1) &= ~0x400uLL;
                  *((_QWORD *)v3 + 1) |= 0x8000000uLL;
                  v117[1] |= 0x8000u;
                  if ( Status[1] && (v23 & 4) == 0 && ((v23 & 0x10) != 0 || (v12 & 0x40) != 0 || (v12 & 2) != 0) )
                  {
                    RefsBackoutFailedLinkRemove(v3, (__int64)Status);
                    v152 = BYTE2(Status[0]);
                    v12 = BYTE1(Status[0]);
                    v149 = BYTE1(Status[0]);
                    v23 = Status[0];
                    v117 = FsContext;
                  }
                  v118 = (unsigned __int8)v23;
                  LOBYTE(v118) = (v23 & 0x10) != 0;
                  if ( (v23 & 0x10) != 0
                    || (v12 & 0x40) != 0
                    || (v117[1] & 0x10000) != 0
                    || ((__int64)v43->spacer.Resource & 0x40000) != 0 )
                  {
                    v119 = 16;
                    v185 = 16;
                    if ( (v23 & 0x10) != 0 || (v12 & 0x40) != 0 )
                    {
                      v119 = 80;
                      v185 = 80;
                    }
                    if ( ((__int64)v43->spacer.Resource & 0x40000) != 0 )
                    {
                      v119 |= 8u;
                      v185 = v119;
                    }
                    if ( !InternalSrvOpen && v160 == 2 )
                      InternalSrvOpen = (struct IndexSCB *)v43->InternalSrvOpen;
                    if ( InternalSrvOpen )
                    {
                      FsRtlCheckOplockEx((POPLOCK)InternalSrvOpen + 11, Irp, v119, 0, 0, 0);
                      v43->Header.Resource = (PERESOURCE)((unsigned __int64)v43->Header.Resource & ~0x40000uLL);
                    }
                    v12 = v149;
                  }
                  if ( (v23 & 0x10) == 0 )
                  {
                    if ( (v12 & 0x40) == 0 )
                      goto LABEL_499;
                    if ( (v23 & 0x10) == 0 )
                    {
LABEL_500:
                      if ( (v12 & 0x40) == 0 && (v12 & 2) == 0 )
                      {
LABEL_510:
                        v126 = v152;
                        if ( (v152 & 2) != 0 && (v12 & 0x40) == 0 )
                        {
                          RefsUpdateLcbDuplicateInfo((struct _IRP_CONTEXT *)v118, v43, v178);
                          *((_DWORD *)&v43->1 + 43) = 0;
                        }
                        if ( (v126 & 0x10) != 0 )
                        {
                          v127 = *((_QWORD *)FcbReleases + 3);
                          v128 = *(struct _FAST_MUTEX **)(v127 + 48);
                          KeEnterGuardedRegion();
                          ExAcquireFastMutexUnsafe(v128);
                          _InterlockedIncrement((volatile signed __int32 *)(v127 + 172));
                          --*((_DWORD *)FcbReleases + 18);
                          ++*(_DWORD *)(v127 + 172);
                          ExReleaseFastMutexUnsafe(*(PFAST_MUTEX *)(v127 + 48));
                          KeLeaveGuardedRegion();
                          v129 = v152;
                          LOBYTE(v129) = v152 & 0xEF;
                          v152 = v129;
                          BYTE2(Status[0]) = v129;
                        }
                        v130 = FsContext;
                        if ( (*((_DWORD *)FsContext + 1) & 8) != 0 )
                        {
                          v131 = 1;
                        }
                        else
                        {
                          v131 = 0;
                          if ( *((_BYTE *)FsContext + 80) == 4 )
                            v131 = 2;
                        }
                        v132 = FileObject;
                        RefsRemoveShareAccess(FileObject, v131, v6, v189);
                        RefsDecrementCleanupCounts(v3, (struct _SCB *)v6, v189, (v132->Flags >> 3) & 1);
                        FcbReleases = 0;
                        v162 = 0;
                        if ( (v23 & 0x10) != 0 )
                        {
                          v133 = (SECTION_OBJECT_POINTERS *)(*(_QWORD *)(v6 + 248) + 8LL);
                          if ( v133->DataSectionObject )
                            MmForceSectionClosed(v133, 1u);
                        }
                        v134 = v130[2];
                        if ( (v134 & 1) != 0 )
                        {
                          v130[2] = v134 & 0xFFFFFFFE;
                          --*(_DWORD *)(v6 + 180);
                        }
                        v35 = Status[1];
                        if ( Status[1] )
                        {
                          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
                            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                          {
                            WPP_SF_d(
                              WPP_GLOBAL_Control->AttachedDevice,
                              16,
                              WPP_08039d2264c939b1b5c93e03467edfa1_Traceguids,
                              (unsigned int)Status[1]);
                          }
                          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                            && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
                          {
                            WPP_SF_d(
                              WPP_GLOBAL_Control->AttachedDevice,
                              17,
                              WPP_08039d2264c939b1b5c93e03467edfa1_Traceguids,
                              0);
                          }
                          if ( (_BYTE)RefsStatusDebugEnabled )
                            RefsStatusDebug(0, 0, "Cleanup.c", 0xE3Eu);
                          v35 = 0;
                          Status[1] = 0;
                          *((_DWORD *)v3 + 4) = 0;
                        }
                        goto LABEL_536;
                      }
LABEL_502:
                      v125 = Irp;
                      Irp->IoStatus.Information = 0;
                      if ( (v23 & 0x10) != 0 )
                      {
                        v125->IoStatus.Information = 4;
                        if ( (v23 & 0x20) != 0 )
                        {
                          v161 = 36;
                          v125->IoStatus.Information = 36;
                        }
                        v118 = v161;
                      }
                      else
                      {
                        v118 = 0;
                        if ( (v12 & 0x40) != 0 )
                        {
                          Irp->IoStatus.Information = 8;
                          v118 = 8;
                        }
                      }
                      if ( (v12 & 2) != 0 )
                      {
                        v118 |= 0x10uLL;
                        Irp->IoStatus.Information = v118;
                      }
                      goto LABEL_510;
                    }
                  }
                  if ( (*((_DWORD *)v155 + 1642) & 4) != 0 && (unsigned __int8)(v160 - 2) <= 1u )
                  {
                    memset(v194, 0, sizeof(v194));
                    v120 = *(_QWORD *)(v6 + 136);
                    *(_QWORD *)&v194[8] = *(_QWORD *)(*(_QWORD *)(v120 + 88) + 256LL);
                    v121 = *(_QWORD *)(*(_QWORD *)(v120 + 88) + 248LL);
                    *(_QWORD *)v194 = v121;
                    if ( Irp )
                    {
                      ActivityIdIrp = IoGetActivityIdIrp(Irp, &v194[24]);
                      v123 = &v194[24];
                      if ( ActivityIdIrp < 0 )
                        v123 = 0;
                    }
                    else
                    {
                      ActivityIdThread = (_OWORD *)IoGetActivityIdThread(v121, v120);
                      if ( ActivityIdThread )
                      {
                        *(_OWORD *)&v194[24] = *ActivityIdThread;
                        v123 = &v194[24];
                      }
                      else
                      {
                        v123 = 0;
                      }
                    }
                    *(_QWORD *)&v194[16] = v123;
                    FsRtlHeatLogIo((char *)v155 + 6564, Irp, v194, 0, v123);
                  }
LABEL_499:
                  if ( (v23 & 0x10) != 0 )
                    goto LABEL_502;
                  goto LABEL_500;
                }
                if ( (*(_QWORD *)v45 & 0x10) != 0 && !v44 )
                {
                  RefsUpdateStandardInformation(v3, v43);
                  v41 = v152;
                  v45 = v153;
                }
                v98 = (struct _CC_FILE_SIZES *)((char *)&v43->1 + 172);
                v180 = (struct _CC_FILE_SIZES *)((char *)&v43->1 + 172);
                v37 = (PFILE_OBJECT)((char *)&v43->1 + 172);
                if ( (*((_DWORD *)&v43->1 + 43) & 0xC00000FC) != 0
                  || (*v179 & 0x10000) != 0
                  || v178 && (*((_DWORD *)v178 + 19) & 0xC00000FC) != 0 )
                {
                  v99 = Status[1];
                  if ( Status[1] )
                  {
LABEL_369:
                    if ( (v12 & 0x10) != 0 || v99 )
                      goto LABEL_412;
                    v177 = 0;
                    if ( (v41 & 2) == 0 || (v12 & 0x40) != 0 )
                    {
                      LowPart = v98->AllocationSize.LowPart;
                      if ( (LowPart & 0x100) == 0 )
                        goto LABEL_391;
                    }
                    else
                    {
                      LowPart = *(_DWORD *)&v37->Type;
                    }
                    if ( v178 )
                      v101 = *((_DWORD *)v178 + 19);
                    else
                      v101 = 0;
                    if ( ((LowPart | v101) & 0x40000000) != 0 )
                    {
                      if ( v178 )
                        v102 = ((unsigned __int16)LowPart | (unsigned __int16)*((_DWORD *)v178 + 19)) & 0x1F4 | 8;
                      else
                        v102 = LowPart & 0x1F4 | 8;
                    }
                    else
                    {
                      if ( v178 )
                        v103 = *((_DWORD *)v178 + 19);
                      else
                        LOWORD(v103) = 0;
                      v102 = ((unsigned __int16)v103 | (unsigned __int16)LowPart) & 0x1FC;
                    }
                    v177 = v102;
                    if ( v102 )
                    {
                      if ( InternalSrvOpen )
                        v104 = (struct _IRP_CONTEXT *)*((_QWORD *)InternalSrvOpen + 17);
                      else
                        v104 = 0;
                      RefsReportDirNotify(
                        v104,
                        v155,
                        (struct _UNICODE_STRING *)FsContext + 1,
                        *((unsigned __int16 *)FsContext + 16),
                        0,
                        0,
                        v102,
                        3u,
                        (struct _FCB *)v104);
                      v12 = v149;
                    }
LABEL_391:
                    v180->AllocationSize.LowPart &= ~0x100u;
                    if ( *(_WORD *)(v6 + 224) && ((v105 = *(_WORD *)(v6 + 216), v105 == 128) || v105 == 176)
                      || (v12 & 2) != 0 )
                    {
                      v106 = *(_DWORD *)(v6 + 300);
                      if ( (v106 & 0xC00) != 0 )
                      {
                        v107 = *(_DWORD *)(*(_QWORD *)v194 + 152LL);
                      }
                      else
                      {
                        v107 = *(_DWORD *)(v6 + 152);
                        if ( (v107 & 0x4000) == 0 )
                        {
LABEL_410:
                          *(_DWORD *)(v6 + 300) &= 0xFFFFF1FF;
                          v12 = v149;
                          if ( (*(_DWORD *)(v6 + 152) & 0x4000) != 0 )
                            _InterlockedAnd((volatile signed __int32 *)(v6 + 152), 0xFFFFBFFF);
                          goto LABEL_412;
                        }
                      }
                      v177 = 0;
                      if ( (v106 & 0x400) != 0 )
                      {
                        v108 = 512;
                        v177 = 512;
                        v109 = 7;
                      }
                      else
                      {
                        v110 = (v107 & 0x4000) != 0;
                        v108 = 0;
                        if ( v110 )
                          v108 = 1024;
                        v177 = v108;
                        if ( (v106 & 0x800) != 0 )
                        {
                          v108 |= 0x800u;
                          v177 = v108;
                        }
                        v109 = 8;
                      }
                      if ( InternalSrvOpen )
                        v111 = (struct _IRP_CONTEXT *)*((_QWORD *)InternalSrvOpen + 17);
                      else
                        v111 = 0;
                      RefsReportDirNotify(
                        v111,
                        v155,
                        (struct _UNICODE_STRING *)FsContext + 1,
                        *((unsigned __int16 *)FsContext + 16),
                        (struct _UNICODE_STRING *)(v6 + 224),
                        0,
                        v108,
                        v109,
                        (struct _FCB *)v111);
                      goto LABEL_410;
                    }
LABEL_412:
                    if ( !Status[1] )
                    {
                      RefsCheckpointCurrentTransaction(v3);
                      v23 |= 4u;
                      LOBYTE(Status[0]) = v23;
                      v43->Header.Resource = (PERESOURCE)((unsigned __int64)v43->Header.Resource & ~0x10uLL);
                    }
                    LOBYTE(v41) = v152;
                    goto LABEL_415;
                  }
                  if ( (*(_DWORD *)v45 & 0x100LL) == 0 )
                  {
                    if ( (v12 & 0x40) == 0 )
                    {
                      RefsCheckpointCurrentTransaction(v3);
                      RefsPrepareForUpdateDuplicate(v3, v43, &v178, &InternalSrvOpen, 1u, 0);
                      RefsUpdateDuplicateInfo(v3, v43, v178, InternalSrvOpen);
                      v41 = v152;
                      v98 = v180;
                      v37 = (PFILE_OBJECT)v180;
                    }
                    LOBYTE(v41) = v41 | 2;
                    v152 = v41;
                    BYTE2(Status[0]) = v41;
                  }
                }
                v99 = Status[1];
                goto LABEL_369;
              }
              if ( !FcbReleases )
              {
LABEL_270:
                v65 = v152;
                goto LABEL_271;
              }
              v66 = v12 | 0x40;
              v149 = v66;
              BYTE1(Status[0]) = v66;
              if ( HIDWORD(v25->VNetRoot) > 1 )
              {
                RefsAcquireExclusiveScb(v3, InternalSrvOpen, 0);
                v67 = v152;
                LOBYTE(v67) = v152 | 0x80;
                v152 = v67;
                BYTE2(Status[0]) = v67;
                v68 = &v25->InternalSrvOpen->0;
                if ( v68 == (_QWORD *)InternalSrvOpen )
                  goto LABEL_253;
                v69 = 5;
                if ( (*((_DWORD *)v3 + 2) & 0x100LL) == 0 )
                  v69 = 3;
                if ( (unsigned __int8)RefsAcquireExclusiveFcb(v3, v68[17], v25->InternalSrvOpen, v69) )
                {
LABEL_253:
                  v71 = v23 & 0xFE;
                  LOBYTE(Status[0]) = v71;
                  v72 = *(_QWORD *)((char *)FcbReleases + 148);
                  v187 = 0;
                  v73 = *((_DWORD *)FcbReleases + 35);
                  LODWORD(v161) = v73 - 4;
                  v187.MaximumLength = v73 - 4;
                  v187.Length = v73 - 4;
                  v187.Buffer = (PWSTR)(v72 + 4);
                  v193 = v187;
                  v74 = InternalSrvOpen;
                  RefsRemoveLink(v3, v154, InternalSrvOpen, &v193);
                  RefsConvertToStandardInfoLinkCount(v3, v154, (unsigned int)(HIDWORD(v154->VNetRoot) - 1), 0);
                  v75 = v154;
                  RefsPostUsnChange(v3, v154, 0x80010000, (struct _LCB *)((char *)FcbReleases + 120));
                  RefsCheckpointCurrentTransaction(v3);
                  --HIDWORD(v154->VNetRoot);
                  v23 = v71 | 4;
                  LOBYTE(Status[0]) = v23;
                  RefsRemovePrefixHashEntry(FcbReleases);
                  *((_DWORD *)FcbReleases + 1) &= ~0x40u;
                  *((_DWORD *)FcbReleases + 1) |= 2u;
                  *((_DWORD *)FcbReleases + 19) = 0;
                  *(_QWORD *)v153 &= ~0x4000uLL;
                  RefsUpdateFcbTimestamps(*((_QWORD *)v74 + 17), FsContext, 2684354576LL);
                  v12 = v149;
                  if ( (v149 & 0x10) == 0 && !Status[1] )
                  {
                    if ( InternalSrvOpen )
                      v77 = (struct _FCB *)*((_QWORD *)InternalSrvOpen + 17);
                    else
                      v77 = 0;
                    RefsReportDirNotify(v155, v155, v76 + 1, v76[2].Length, 0, 0, 1u, 2u, v77);
                    v12 = v149;
                  }
                  v178 = 0;
                  if ( Status[1] >= 0 )
                    RefsUpdateFileTimestampsForChange(v75, FsContext, 0, 0);
                  v78 = FileObject;
                  FileObject->Flags &= ~0x4000u;
                  RefsUpdateScbFromFileObject(v78, (struct _SCB *)v6, 1u);
                  v78->Flags |= 0x4000u;
LABEL_269:
                  v61 = Status[1];
                  goto LABEL_270;
                }
LABEL_588:
                *((_QWORD *)v3 + 1) |= 0x100uLL;
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                  && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                {
                  WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_08039d2264c939b1b5c93e03467edfa1_Traceguids);
                }
                if ( (_BYTE)RefsStatusDebugEnabled )
                  RefsStatusDebug(-1073741608, v3, "Cleanup.c", 0x8D3u);
                RefsRaiseStatusInternal(v3, -1073741608, v70);
                __debugbreak();
                JUMPOUT(0x14031C7DFLL);
              }
              v12 = v66 & 0xBF;
              v149 = v12;
              BYTE1(Status[0]) = v12;
              *((_DWORD *)FcbReleases + 1) |= 0x40u;
            }
            v166 = 1;
            if ( (*(_DWORD *)v176 & 4) == 0 )
              goto LABEL_270;
            if ( !RefsHardlinksSupported(*((struct _VCB **)v3 + 8)) )
              goto LABEL_270;
            if ( !FcbReleases )
              goto LABEL_270;
            v79 = *((_DWORD *)FcbReleases + 1);
            if ( (v79 & 1) == 0 || (v79 & 2) != 0 )
              goto LABEL_270;
            RefsPosixDeleteLink(v3, v25, (__int64)FsContext, (__int64)InternalSrvOpen, (__int64)Status);
            v61 = 0;
            Status[1] = 0;
            goto LABEL_246;
          }
        }
LABEL_222:
        v59 = 2;
        goto LABEL_224;
      }
    }
    v59 = 0;
    goto LABEL_224;
  }
  Irp = 0;
  v3 = 0;
  v156 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_08039d2264c939b1b5c93e03467edfa1_Traceguids, 871);
  }
  if ( (_BYTE)RefsStatusDebugEnabled )
    RefsStatusDebug(871, 0, "Cleanup.c", 0x64Bu);
  v35 = 871;
  Status[1] = 871;
LABEL_536:
  if ( v35 != 871 )
  {
    RefsReleaseVcb(v3, v155);
    if ( (v152 & 1) != 0 )
    {
      RefsReleaseScbWithPaging(v3, (struct _SCB *)v6);
      FsRtlNotifyVolumeEvent(FileObject, 5u);
    }
  }
  v135 = v152;
  if ( (v152 & 0x10) != 0 )
  {
    v136 = *((_QWORD *)FcbReleases + 3);
    v137 = *(struct _FAST_MUTEX **)(v136 + 48);
    KeEnterGuardedRegion();
    ExAcquireFastMutexUnsafe(v137);
    _InterlockedIncrement((volatile signed __int32 *)(v136 + 172));
    --*((_DWORD *)FcbReleases + 18);
    ++*(_DWORD *)(v136 + 172);
    ExReleaseFastMutexUnsafe(*(PFAST_MUTEX *)(v136 + 48));
    KeLeaveGuardedRegion();
    v135 &= ~0x10u;
    v35 = Status[1];
  }
  if ( (v149 & 4) != 0 && v35 >= 0 && v35 != 871 && v160 != 4 && (v135 & 4) != 0 && (v135 & 8) == 0 )
  {
    v138 = (struct _UNICODE_STRING *)FsContext;
    if ( (v23 & 0x10) != 0 || (v149 & 2) != 0 || (v149 & 0x40) != 0 || (*((_WORD *)FsContext + 44) & 0x912) != 0 )
    {
      *((_DWORD *)v3 + 1) |= 0x400u;
      RefsCompleteRequest((PSECURITY_SUBJECT_CONTEXT *)v3, 0, v35);
      v140 = RefsIoCallSelf(v3, FileObject, v139);
      v141 = v140;
      if ( v140 != -1073741533 && v140 < 0 )
      {
        if ( (unsigned int)(v140 + 1073741662) > 1
          && v140 != -1073741643
          && (unsigned int)(v140 + 1073741806) > 2
          && v140 != -2147483626 )
        {
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
            || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
          {
            v141 = -1073700734;
          }
          else
          {
            v141 = -1073700734;
            WPP_SF_d(
              WPP_GLOBAL_Control->AttachedDevice,
              18,
              WPP_08039d2264c939b1b5c93e03467edfa1_Traceguids,
              3221266562LL);
          }
          if ( (_BYTE)RefsStatusDebugEnabled )
            RefsStatusDebug(-1073700734, 0, "Cleanup.c", 0xF3Eu);
        }
        v142 = v154;
        v143 = v154->pNetRoot;
        KeEnterGuardedRegion();
        ExAcquireFastMutexUnsafe((PFAST_MUTEX)&v143->pSrvCall);
        IoRaiseInformationalHardError(v141, v138 + 1, Irp->Tail.Overlay.Thread);
        ExReleaseFastMutexUnsafe((PFAST_MUTEX)&v142->pNetRoot->pSrvCall);
        KeLeaveGuardedRegion();
      }
    }
  }
  v144 = Status[1];
  if ( Status[1] != 871 )
  {
    v145 = *((_QWORD *)v3 + 1);
    if ( (v145 & 0x100000000LL) != 0 )
    {
      *((_QWORD *)v3 + 1) = v145 | 0x200000000LL;
      return v144;
    }
    RefsCompleteRequest((PSECURITY_SUBJECT_CONTEXT *)v3, Irp, Status[1]);
  }
  return v144;
}

```

## disassembly

```asm
0x140319010  mov     [rsp+arg_10], rbx
0x140319015  mov     [rsp+arg_18], rsi
0x14031901a  push    rdi
0x14031901b  push    r12
0x14031901d  push    r13
0x14031901f  push    r14
0x140319021  push    r15
0x140319023  sub     rsp, 1F0h
0x14031902a  mov     rax, cs:__security_cookie
0x140319031  xor     rax, rsp
0x140319034  mov     [rsp+218h+var_30], rax
0x14031903c  mov     rax, rdx
0x14031903f  mov     r15, rcx
0x140319042  mov     [rsp+218h+var_188], rcx
0x14031904a  mov     [rsp+218h+Irp], rdx
0x140319052  xor     r13d, r13d
0x140319055  mov     [rsp+218h+Status+4], r13d
0x14031905a  mov     [rsp+218h+var_160], r13
0x140319062  mov     [rsp+218h+var_148], r13
0x14031906a  xor     edx, edx
0x14031906c  mov     [rsp+218h+var_1A8], rdx
0x140319071  mov     word ptr [rsp+218h+Status], dx
0x140319076  mov     byte ptr [rsp+218h+Status], 1
0x14031907b  mov     qword ptr [rax+38h], 2
0x140319083  mov     rax, [rax+0B8h]
0x14031908a  mov     r8, [rax+30h]
0x14031908e  mov     [rsp+218h+FileObject], r8
0x140319096  mov     [rsp+218h+var_128], r8
0x14031909e  lea     rax, [r8+18h]
0x1403190a2  mov     [rsp+218h+var_D8], rax
0x1403190aa  mov     rsi, [rax]
0x1403190ad  test    rsi, rsi
0x1403190b0  jz      short loc_140319105
0x1403190b2  mov     r10, [rsi+90h]
0x1403190b9  mov     [rsp+218h+var_190], r10
0x1403190c1  mov     [rsp+218h+var_140], r10
0x1403190c9  mov     rcx, [r8+20h]
0x1403190cd  mov     [rsp+218h+FsContext], rcx
0x1403190d5  mov     [rsp+218h+var_150], rcx
0x1403190dd  mov     rbx, [rsi+88h]
0x1403190e4  mov     [rsp+218h+var_198], rbx
0x1403190ec  mov     [rsp+218h+var_130], rbx
0x1403190f4  test    rcx, rcx
0x1403190f7  jnz     short loc_1403190FE
0x1403190f9  mov     r14b, 5
0x1403190fc  jmp     short loc_140319141
0x1403190fe  movzx   r14d, byte ptr [rcx+50h]
0x140319103  jmp     short loc_140319141
0x140319105  mov     r10, r13
0x140319108  mov     [rsp+218h+var_190], r13
0x140319110  mov     [rsp+218h+var_140], r13
0x140319118  mov     rbx, r13
0x14031911b  mov     [rsp+218h+var_198], rbx
0x140319123  mov     [rsp+218h+var_130], rbx
0x14031912b  mov     rcx, r13
0x14031912e  mov     [rsp+218h+FsContext], rcx
0x140319136  mov     [rsp+218h+var_150], rcx
0x14031913e  mov     r14b, 1
0x140319141  mov     [rsp+218h+var_170], r14b
0x140319149  lea     eax, [r14-1]
0x14031914d  test    al, 0FBh
0x14031914f  jz      loc_14031C61F
0x140319155  lea     r12, [rcx+4]
0x140319159  movzx   edi, byte ptr [r12]
0x14031915e  and     dil, 8
0x140319162  add     dil, dil
0x140319165  movzx   eax, byte ptr [rsp+218h+Status+1]
0x14031916a  and     al, 0EFh
0x14031916c  or      dil, al
0x14031916f  mov     [rsp+218h+var_1B8], dil
0x140319174  mov     byte ptr [rsp+218h+Status+1], dil
0x140319179  mov     eax, [rcx+54h]
0x14031917c  mov     [r15+278h], eax
0x140319183  cmp     r14b, 4
0x140319187  jnz     loc_14031925D
0x14031918d  mov     eax, [r10+18h]
0x140319191  test    al, 2
0x140319193  jz      short loc_1403191A9
0x140319195  mov     rax, [r10+368h]
0x14031919c  and     rax, 0FFFFFFFFFFFFFFFEh
0x1403191a0  cmp     rax, r8
0x1403191a3  jz      loc_140319268
0x1403191a9  mov     rax, [r15+68h]
0x1403191ad  mov     ecx, [rax+8]
0x1403191b0  bt      rcx, 17h
0x1403191b5  jb      short loc_1403191D2
0x1403191b7  mov     r8b, 1; unsigned __int8
0x1403191ba  mov     rdx, r10; struct _VCB *
0x1403191bd  mov     rcx, r15; struct _IRP_CONTEXT *
0x1403191c0  call    ?RefsAcquireSharedVcb@@YAEPEAU_IRP_CONTEXT@@PEAU_VCB@@E@Z; RefsAcquireSharedVcb(_IRP_CONTEXT *,_VCB *,uchar)
0x1403191c5  mov     rdx, [rsp+218h+var_1A8]
0x1403191ca  mov     r10, [rsp+218h+var_190]
0x1403191d2  mov     rax, [rsp+218h+var_D8]
0x1403191da  mov     [rsp+218h+var_E0], rax
0x1403191e2  mov     qword ptr [rsp+218h+var_58], rsi
0x1403191ea  mov     [rsp+218h+var_138], rsi
0x1403191f2  mov     [rsp+218h+var_E8], rsi
0x1403191fa  mov     [rsp+218h+var_16F], r14b
0x140319202  mov     [rsp+218h+var_F0], r12
0x14031920a  lea     rcx, [r10+18h]
0x14031920e  mov     [rsp+218h+var_168], rcx
0x140319216  mov     r8d, [rcx]
0x140319219  mov     eax, r8d
0x14031921c  and     eax, 8000823h
0x140319221  cmp     eax, 1
0x140319224  jnz     loc_1403192D0
0x14031922a  test    dword ptr [rsi+12Ch], 4000h
0x140319234  jnz     loc_1403192D0
0x14031923a  mov     rcx, [r10+70h]
0x14031923e  test    rcx, rcx
0x140319241  jz      loc_1403192C8
0x140319247  call    MsAreWritesDoomed
0x14031924c  mov     rcx, [rsp+218h+var_168]
0x140319254  test    al, al
0x140319256  jnz     short loc_1403192D0
0x140319258  or      dl, 4
0x14031925b  jmp     short loc_1403192D0
0x14031925d  mov     eax, [r15+8]
0x140319261  bt      rax, 8
0x140319266  jnb     short loc_14031927B
0x140319268  mov     r8b, 1; unsigned __int8
0x14031926b  mov     rdx, r10; struct _VCB *
0x14031926e  mov     rcx, r15; struct _IRP_CONTEXT *
0x140319271  call    ?RefsAcquireExclusiveVcb@@YAEPEAU_IRP_CONTEXT@@PEAU_VCB@@E@Z; RefsAcquireExclusiveVcb(_IRP_CONTEXT *,_VCB *,uchar)
0x140319276  jmp     loc_1403191C5
0x14031927b  mov     rdx, [r15+68h]
0x14031927f  mov     r8, 20000000000h
0x140319289  test    [rdx+8], r8
0x14031928d  jnz     short loc_14031929F
0x14031928f  lea     rcx, [rdx+0A0h]
0x140319296  call    MsInitializeFastResourceOwnerEntry
0x14031929b  or      [rdx+8], r8
0x14031929f  movzx   r8d, byte ptr [r15+8]
0x1403192a4  and     r8b, 1
0x1403192a8  lea     rcx, [r10+520h]
0x1403192af  add     rdx, 0A0h
0x1403192b6  call    ??$MsAcquireFastResourceSharedInternal@$0A@@@YAEPEAU_MS_FAST_RESOURCE@@PEAU_MS_FAST_RESOURCE_OWNER_ENTRY@@E@Z; MsAcquireFastResourceSharedInternal<0>(_MS_FAST_RESOURCE *,_MS_FAST_RESOURCE_OWNER_ENTRY *,uchar)
0x1403192bb  test    al, al
0x1403192bd  jz      loc_14031C68C
0x1403192c3  jmp     loc_1403191C5
0x1403192c8  mov     rcx, [rsp+218h+var_168]
0x1403192d0  test    r8d, 2000020h
0x1403192d7  jnz     short loc_1403192ED
0x1403192d9  lea     r14, [rbx+8]
0x1403192dd  mov     [rsp+218h+var_1A0], r14
0x1403192e2  mov     rax, [r14]
0x1403192e5  test    al, 20h
0x1403192e7  jnz     short loc_1403192ED
0x1403192e9  xor     al, al
0x1403192eb  jmp     short loc_1403192F8
0x1403192ed  lea     r14, [rbx+8]
0x1403192f1  mov     [rsp+218h+var_1A0], r14
0x1403192f6  mov     al, 8
0x1403192f8  mov     [rsp+218h+var_120], r14
0x140319300  and     dl, 0F7h
0x140319303  or      dl, al
0x140319305  mov     [rsp+218h+var_1A8], rdx
0x14031930a  mov     byte ptr [rsp+218h+Status+2], dl
0x14031930e  mov     [rsp+218h+var_1AC], dl
0x140319312  mov     eax, [rcx]
0x140319314  bt      eax, 1Ah
0x140319318  jnb     short loc_140319328
0x14031931a  or      dil, 4
0x14031931e  mov     [rsp+218h+var_1B8], dil
0x140319323  mov     byte ptr [rsp+218h+Status+1], dil
0x140319328  mov     r9d, 10h
0x14031932e  mov     r8, rsi
0x140319331  mov     rdx, rbx
0x140319334  mov     rcx, r15
0x140319337  call    ?RefsAcquireFcbWithPaging@@YAEPEAU_IRP_CONTEXT@@PEAU_FCB@@PEAU_SCB@@W4_REFS_ACQUIRE_FLAGS@@@Z; RefsAcquireFcbWithPaging(_IRP_CONTEXT *,_FCB *,_SCB *,_REFS_ACQUIRE_FLAGS)
0x14031933c  mov     rbx, [rsp+218h+var_F0]
0x140319344  mov     ecx, [rbx]
0x140319346  test    ecx, ecx
0x140319348  jns     short loc_140319358
0x14031934a  dec     dword ptr [rsi+158h]
0x140319350  and     dword ptr [rbx], 7FFFFFFFh
0x140319356  mov     ecx, [rbx]
0x140319358  mov     r9, [rsp+218h+FsContext]
0x140319360  lea     rdx, [r9+8]
0x140319364  mov     [rsp+218h+var_D0], rdx
0x14031936c  mov     [rsp+218h+var_108], rdx
0x140319374  mov     eax, [rdx]
0x140319376  test    al, 4
0x140319378  jnz     short loc_140319387
0x14031937a  mov     eax, [r14]
0x14031937d  bt      rax, 0Bh
0x140319382  mov     r12b, 1
0x140319385  jnb     short loc_14031938A
0x140319387  mov     r12b, 9
0x14031938a  mov     byte ptr [rsp+218h+Status], r12b
0x14031938f  mov     r14, [r9+48h]
0x140319393  mov     [rsp+218h+var_160], r14
0x14031939b  mov     [rsp+218h+var_A0], r14
0x1403193a3  mov     [rsp+218h+var_F8], r14
0x1403193ab  test    r14, r14
0x1403193ae  jz      short loc_1403193C6
0x1403193b0  mov     eax, [r14+4]
0x1403193b4  test    al, 2
0x1403193b6  jnz     short loc_1403193C6
0x1403193b8  mov     rax, [r14+18h]
0x1403193bc  mov     [rsp+218h+var_148], rax
0x1403193c4  jmp     short loc_1403193E2
0x1403193c6  mov     r14, r13
0x1403193c9  mov     [rsp+218h+var_160], r13
0x1403193d1  mov     [rsp+218h+var_F8], r13
0x1403193d9  btr     ecx, 12h
0x1403193dd  mov     rax, rbx
0x1403193e0  mov     [rbx], ecx
0x1403193e2  mov     rbx, [rsp+218h+var_198]
0x1403193ea  mov     rcx, rbx; struct _FCB *
0x1403193ed  call    ?RefsIsFileOpen@@YAEPEBU_FCB@@@Z; RefsIsFileOpen(_FCB const *)
0x1403193f2  test    al, al
0x1403193f4  jnz     short loc_140319402
0x1403193f6  movzx   eax, byte ptr [rbx+8]
0x1403193fa  test    al, 1
0x1403193fc  jz      loc_14031C6FC
0x140319402  movzx   r8d, [rsp+218h+var_1AC]
0x140319408  test    r8b, 4
0x14031940c  jz      loc_140319897
0x140319412  test    r8b, 8
0x140319416  jnz     loc_140319897
0x14031941c  test    byte ptr [rbx+8], 1
0x140319420  jnz     loc_140319897
0x140319426  mov     rax, [rsp+218h+var_F0]
0x14031942e  mov     ecx, [rax]
0x140319430  bt      ecx, 12h
0x140319434  jnb     loc_1403196BF
0x14031943a  test    cl, 2
0x14031943d  jz      loc_14031966C
0x140319443  mov     [rsp+218h+var_118], 0
0x14031944b  test    r14, r14
0x14031944e  jz      short loc_14031945C
0x140319450  mov     eax, [r14+4]
0x140319454  test    al, 1
0x140319456  jz      short loc_14031945C
0x140319458  xor     cl, cl
0x14031945a  jmp     short loc_14031945E
0x14031945c  mov     cl, 1
0x14031945e  mov     [rsp+218h+var_158], cl
0x140319465  test    cl, cl
0x140319467  jz      loc_1403196A9
0x14031946d  mov     rax, [rbx+58h]
0x140319471  cmp     qword ptr [rax+0F8h], 0
0x140319479  jnz     loc_14031955A
0x14031947f  cmp     qword ptr [rax+100h], 0
0x140319487  jz      loc_14031955A
0x14031948d  lea     r8, [rsp+218h+var_118]; unsigned __int8 *
0x140319495  mov     rdx, rbx; struct _FCB *
0x140319498  mov     rcx, r15; struct _IRP_CONTEXT *
0x14031949b  call    ?RefsIsLinkDeleteable@@YAEPEAU_IRP_CONTEXT@@PEAU_FCB@@PEAE@Z; RefsIsLinkDeleteable(_IRP_CONTEXT *,_FCB *,uchar *)
0x1403194a0  movzx   ecx, al
0x1403194a3  mov     [rsp+218h+var_158], al
0x1403194aa  mov     rdx, [rsp+218h+var_D0]
0x1403194b2  jmp     loc_14031955A
0x1403194b7  xor     cl, cl; struct _IRP_CONTEXT *
0x1403194b9  mov     [rsp+218h+var_158], cl
0x1403194c0  xor     r13d, r13d
0x1403194c3  mov     rax, [rsp+218h+var_128]
0x1403194cb  mov     [rsp+218h+FileObject], rax
0x1403194d3  mov     rax, [rsp+218h+var_140]
0x1403194db  mov     [rsp+218h+var_190], rax
0x1403194e3  mov     rbx, [rsp+218h+var_130]
0x1403194eb  mov     [rsp+218h+var_198], rbx
0x1403194f3  mov     rsi, [rsp+218h+var_138]
0x1403194fb  mov     rax, [rsp+218h+var_150]
0x140319503  mov     [rsp+218h+FsContext], rax
0x14031950b  mov     r14, [rsp+218h+var_160]
0x140319513  movzx   eax, byte ptr [rsp+218h+Status+2]
0x140319518  mov     [rsp+218h+var_1A8], rax
0x14031951d  movzx   edi, byte ptr [rsp+218h+Status+1]
0x140319522  mov     [rsp+218h+var_1B8], dil
0x140319527  movzx   r12d, byte ptr [rsp+218h+Status]
0x14031952d  mov     rax, [rsp+218h+var_120]
0x140319535  mov     [rsp+218h+var_1A0], rax
0x14031953a  mov     rax, [rsp+218h+var_E0]
0x140319542  mov     [rsp+218h+var_D8], rax
0x14031954a  mov     r15, [rsp+218h+var_188]
0x140319552  mov     rdx, [rsp+218h+var_D0]
0x14031955a  test    cl, cl
0x14031955c  jz      loc_1403196A9
0x140319562  mov     eax, [rdx]
0x140319564  test    al, 8
0x140319566  jz      short loc_140319576
0x140319568  or      r12b, 8
0x14031956c  mov     byte ptr [rsp+218h+Status], r12b
0x140319571  or      eax, 4
0x140319574  mov     [rdx], eax
0x140319576  xor     al, al
0x140319578  mov     [rsp+218h+var_157], al
0x14031957f  cmp     dword ptr [rbx+0B0h], 1
0x140319586  ja      short loc_1403195C9
0x140319588  movzx   r8d, r12b
0x14031958c  shr     r8b, 3
0x140319590  and     r8b, 1; bool
0x140319594  mov     rdx, rbx; struct _FCB *
0x140319597  call    ?RefsTryCloseSectionOnDelete@@YA_NAEAU_IRP_CONTEXT@@AEAU_FCB@@_N@Z; RefsTryCloseSectionOnDelete(_IRP_CONTEXT &,_FCB &,bool)
0x14031959c  mov     [rsp+218h+var_157], al
0x1403195a3  or      r12b, 80h
0x1403195a7  mov     byte ptr [rsp+218h+Status], r12b
0x1403195ac  test    al, al
  ... truncated ...
```
