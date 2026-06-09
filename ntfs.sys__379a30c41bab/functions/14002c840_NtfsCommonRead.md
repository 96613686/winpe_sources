# NtfsCommonRead

- ea: `0x14002c840`
- end: `0x14002ec13`
- name: `NtfsCommonRead`
- size: `9171`
- prototype: `__int64 __fastcall(int, int)`
- caller_count: `3`
- callee_count: `35`
- tags: `reparse_path, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140015540`
- `0x140015d10`
- `0x14002c760`

## callees

- `0x1400055f0`
- `0x140007ea0`
- `0x1400082b0`
- `0x140009710`
- `0x14000a230`
- `0x14000c1d0`
- `0x14000c290`
- `0x140021220`
- `0x140024070`
- `0x140024e5c`
- `0x1400256b4`
- `0x140025bd0`
- `0x140025d00`
- `0x140028890`
- `0x14002c840`
- `0x140035c48`
- `0x14003ac2c`
- `0x14004062c`
- `0x1400415b4`
- `0x1401597b8`
- `0x140163fc8`
- `0x1401751cc`
- `0x140175ad0`
- `0x140188f30`
- `0x1401be3e8`
- `0x1401be96c`
- `0x1401c0130`
- `0x1401c0ba0`
- `0x1401d1fac`
- `0x1401eb058`
- `0x140218890`
- `0x14022ef24`
- `0x140245bf8`
- `0x14024f8b8`
- `0x140285a50`

## import_xrefs

- `ntoskrnl!FsRtlCheckOplock` at `0x14002d9f4`
- `ntoskrnl!FsRtlCheckOplock` at `0x14002d9f4`
- `ntoskrnl!IoGetIoPriorityHint` at `0x14002d46f`
- `ntoskrnl!IoGetIoPriorityHint` at `0x14002d521`
- `ntoskrnl!IoGetIoPriorityHint` at `0x14002e36b`
- `ntoskrnl!IoGetIoPriorityHint` at `0x14002d46f`
- `ntoskrnl!IoGetIoPriorityHint` at `0x14002d521`
- `ntoskrnl!IoGetIoPriorityHint` at `0x14002e36b`
- `ntoskrnl!IoIrpHasFsTrackOffsetExtensionType` at `0x14002c890`
- `ntoskrnl!IoIrpHasFsTrackOffsetExtensionType` at `0x14002c890`
- `ntoskrnl!IoClearFsTrackOffsetState` at `0x14002c8a3`
- `ntoskrnl!IoClearFsTrackOffsetState` at `0x14002c8a3`
- `ntoskrnl!FsRtlOplockIsFastIoPossible` at `0x14002dacf`
- `ntoskrnl!FsRtlOplockIsFastIoPossible` at `0x14002dacf`
- `ntoskrnl!FsRtlCheckLockForReadAccess` at `0x14002db5e`
- `ntoskrnl!FsRtlCheckLockForReadAccess` at `0x14002db5e`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x14002dcd3`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x14002dcd3`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x14002dc90`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x14002dc90`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x14002d7ed`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x14002d858`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x14002d7ed`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x14002d858`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14002e6b6`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14005b4b4`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14002e6b6`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14005b4b4`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002d96f`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002df3c`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002e0fb`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002e2c2`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002e6f8`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002e74c`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005b4f1`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005b544`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002d96f`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002df3c`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002e0fb`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002e2c2`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002e6f8`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002e74c`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005b4f1`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005b544`
- `ntoskrnl!IoGetTopLevelIrp` at `0x14002d3e8`
- `ntoskrnl!IoGetTopLevelIrp` at `0x14002d811`
- `ntoskrnl!IoGetTopLevelIrp` at `0x14002ddb4`
- `ntoskrnl!IoGetTopLevelIrp` at `0x14002d3e8`
- `ntoskrnl!IoGetTopLevelIrp` at `0x14002d811`
- `ntoskrnl!IoGetTopLevelIrp` at `0x14002ddb4`
- `ntoskrnl!FsRtlNormalizeNtstatus` at `0x14002e562`
- `ntoskrnl!FsRtlNormalizeNtstatus` at `0x14002e562`
- `ntoskrnl!ExRaiseStatus` at `0x14002e570`
- `ntoskrnl!ExRaiseStatus` at `0x14002e570`
- `HAL!KeQueryPerformanceCounter` at `0x14002cf47`
- `HAL!KeQueryPerformanceCounter` at `0x14002cf47`

## pseudocode

```c
__int64 __fastcall NtfsCommonRead(__int64 a1, IRP *a2, __int64 a3)
{
  IRP *v4; // r13
  unsigned int v6; // edi
  __int64 v7; // rcx
  struct _IO_STACK_LOCATION *CurrentStackLocation; // r12
  struct _FILE_OBJECT *FileObject; // r8
  __int64 FsContext; // r14
  __int64 FsContext2; // rbx
  __int64 v12; // r11
  int v13; // eax
  __int64 v14; // r9
  int v15; // edx
  __int64 result; // rax
  unsigned int Status; // ebx
  __int64 v18; // r8
  ULONG Flags; // eax
  int v20; // edx
  __int64 v21; // r8
  __int64 v22; // r9
  __int64 v23; // r11
  LARGE_INTEGER ByteOffset; // r10
  __int64 Length; // r12
  char v26; // al
  int v27; // eax
  __int64 v28; // rax
  int v29; // eax
  __int64 v30; // r9
  __int64 v31; // rcx
  __int64 v32; // r9
  LARGE_INTEGER PerformanceCounter; // rax
  unsigned int v34; // r8d
  char v35; // al
  char v36; // r15
  __int64 v37; // rdx
  __int64 v38; // r8
  unsigned int v39; // eax
  __int64 v40; // rax
  __int64 v41; // rdx
  __int64 v42; // r8
  char v43; // r15
  struct _ERESOURCE *v44; // rcx
  PIRP TopLevelIrp; // rax
  char v46; // r15
  char v47; // dl
  IO_PRIORITY_HINT IoPriorityHint; // eax
  bool v49; // r12
  __int64 v50; // rax
  __int64 *v51; // r9
  unsigned __int8 v52; // al
  int v53; // edx
  __int64 v54; // rcx
  __int64 v55; // rax
  char v56; // al
  int v57; // eax
  __int64 v58; // rax
  __int64 v59; // rcx
  __int64 v60; // r8
  unsigned int v61; // eax
  __int64 v62; // r9
  __int64 v63; // rax
  __int64 v64; // rcx
  int v65; // eax
  FILE_LOCK *v66; // rcx
  __int64 v67; // r8
  __int64 v68; // rcx
  volatile signed __int32 *v69; // r12
  char v70; // di
  unsigned int v71; // eax
  ULONG v72; // edx
  ULONG_PTR Information; // rcx
  __int64 v74; // rax
  __int64 v75; // r12
  __int64 v76; // rdi
  __int64 v77; // rbx
  __int64 v78; // r8
  PIRP v79; // rax
  __int64 v80; // rcx
  __int64 v81; // rax
  int v82; // eax
  struct _ERESOURCE *v83; // rcx
  char v84; // al
  __int64 v85; // rax
  __int64 v86; // rbx
  struct _ERESOURCE *v87; // rcx
  unsigned int v88; // r12d
  struct _ERESOURCE *v89; // rcx
  signed __int64 v90; // rbx
  unsigned int v91; // ebx
  int v92; // ecx
  unsigned int v93; // ebx
  int v94; // eax
  unsigned int v95; // r8d
  bool v96; // zf
  int v97; // eax
  NTSTATUS v98; // eax
  ULONG_PTR v99; // rdx
  struct _IO_STACK_LOCATION *v100; // rcx
  __int64 v101; // r13
  char v102; // al
  volatile signed __int32 *v103; // rdi
  struct _ERESOURCE *v104; // rcx
  POPLOCK_FS_PREPOST_IRP PostIrpRoutine; // [rsp+20h] [rbp-128h]
  char v106; // [rsp+40h] [rbp-108h]
  unsigned int v107; // [rsp+44h] [rbp-104h]
  unsigned int v108; // [rsp+48h] [rbp-100h]
  int v109; // [rsp+50h] [rbp-F8h]
  char v110; // [rsp+50h] [rbp-F8h]
  ULONG v111; // [rsp+54h] [rbp-F4h]
  int v112[2]; // [rsp+60h] [rbp-E8h] BYREF
  PVOID Entry; // [rsp+68h] [rbp-E0h]
  ULONG v114; // [rsp+70h] [rbp-D8h]
  int v115; // [rsp+74h] [rbp-D4h]
  __int64 v116; // [rsp+78h] [rbp-D0h]
  __int64 v117; // [rsp+80h] [rbp-C8h]
  __int64 v118; // [rsp+88h] [rbp-C0h]
  char v119; // [rsp+90h] [rbp-B8h]
  int v120; // [rsp+94h] [rbp-B4h]
  IRP *v121; // [rsp+98h] [rbp-B0h]
  int v122; // [rsp+A0h] [rbp-A8h]
  __int64 v123; // [rsp+A8h] [rbp-A0h]
  __int64 v124; // [rsp+B0h] [rbp-98h]
  struct _FILE_OBJECT *v125; // [rsp+B8h] [rbp-90h]
  __int64 v126; // [rsp+C0h] [rbp-88h]
  struct _IO_STACK_LOCATION *v127; // [rsp+C8h] [rbp-80h]
  void *v128; // [rsp+D0h] [rbp-78h] BYREF
  __int64 v129; // [rsp+D8h] [rbp-70h]
  __int64 v130; // [rsp+E0h] [rbp-68h]
  __int64 v131; // [rsp+E8h] [rbp-60h]
  int v132; // [rsp+F0h] [rbp-58h]
  __int64 v133; // [rsp+F8h] [rbp-50h]
  __int64 v134; // [rsp+100h] [rbp-48h]
  __int128 v135; // [rsp+108h] [rbp-40h] BYREF
  __int64 v136; // [rsp+118h] [rbp-30h]
  __int64 v137; // [rsp+158h] [rbp+10h] BYREF
  int v138; // [rsp+168h] [rbp+20h] BYREF

  v4 = a2;
  v121 = a2;
  v6 = 0;
  *(_QWORD *)v112 = 0;
  Entry = 0;
  v128 = 0;
  v135 = 0;
  v136 = 0;
  v138 = 0;
  if ( (unsigned __int8)IoIrpHasFsTrackOffsetExtensionType(a2) )
    IoClearFsTrackOffsetState(v4);
  CurrentStackLocation = v4->Tail.Overlay.CurrentStackLocation;
  v127 = CurrentStackLocation;
  FileObject = CurrentStackLocation->FileObject;
  v125 = FileObject;
  FsContext = (__int64)FileObject->FsContext;
  if ( FsContext )
  {
    FsContext2 = (__int64)FileObject->FsContext2;
    v118 = FsContext2;
    v12 = *(_QWORD *)(FsContext + 192);
    v123 = v12;
    v13 = *(_DWORD *)(v12 + 4);
    if ( (v13 & 1) == 0 && (!FsContext2 || *(_BYTE *)(FsContext2 + 88) != 4 || (v13 & 2) == 0) )
    {
      NtfsRaiseStatusInternal(a1, -1073741202, 0, 0, 0);
LABEL_543:
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(a1, 3221225488LL, 1837037);
      NtfsRaiseStatusInternal(a1, -1073741808, 0, 0, 1837037);
      goto LABEL_546;
    }
    v14 = *(_QWORD *)(FsContext + 184);
    v124 = v14;
    if ( FsContext2 )
      v15 = *(unsigned __int8 *)(FsContext2 + 88);
    else
      v15 = 5;
  }
  else
  {
    v12 = 0;
    v123 = 0;
    FsContext2 = 0;
    v118 = 0;
    v14 = 0;
    v124 = 0;
    v15 = 1;
  }
  v115 = v15;
  if ( (*(_DWORD *)(FsContext + 512) & 0x1000000) != 0 )
  {
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(a1, 3221225480LL, 1835209);
    LOBYTE(v14) = v4 != 0;
    NtfsExtendedCompleteRequestInternal(a1, v4, 3221225480LL, v14, 0);
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(0, 3221225480LL, 1836054);
    return 3221225480LL;
  }
  if ( (*(_DWORD *)(v12 + 4) & 1) == 0 && v15 != 4 )
  {
    Status = -1073741202;
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(a1, 3221226094LL, 1835209);
    LOBYTE(v14) = v4 != 0;
    NtfsExtendedCompleteRequestInternal(a1, v4, 3221226094LL, v14, 0);
    if ( !NtfsStatusDebugFlags )
      return Status;
    v18 = 1836067;
    goto LABEL_24;
  }
  v109 = *(_DWORD *)(a1 + 12);
  Flags = v4->Flags;
  v20 = Flags & 2;
  v108 = v20;
  LOBYTE(v6) = v20 != 0;
  LOBYTE(Flags) = Flags & 1;
  v111 = Flags;
  v114 = FileObject->Flags;
  if ( (_BYTE)Flags && (*(_DWORD *)(FsContext + 200) & 0x1000000) != 0 )
  {
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(a1, 3221227536LL, 1835209);
    LOBYTE(v14) = v4 != 0;
    NtfsExtendedCompleteRequestInternal(a1, v4, 3221227536LL, v14, 0);
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(0, 3221227536LL, 1836090);
    return 3221227536LL;
  }
  if ( FsContext2 && (*(_DWORD *)(FsContext2 + 4) & 0x2000) != 0 && !v20 )
  {
    Status = -1073741811;
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(a1, 3221225485LL, 1835209);
    LOBYTE(v14) = v4 != 0;
    NtfsExtendedCompleteRequestInternal(a1, v4, 3221225485LL, v14, 0);
    if ( !NtfsStatusDebugFlags )
      return Status;
    v18 = 1836102;
    goto LABEL_24;
  }
  if ( (*(_DWORD *)(*(_QWORD *)(FsContext + 192) + 24LL) & 0x40000) != 0
    && (*(_DWORD *)(*(_QWORD *)(FsContext + 184) + 4LL) & 0x100) == 0
    && (*(_DWORD *)(FsContext + 512) & 0x20) == 0 )
  {
    v7 = 49407;
    if ( ((*(_WORD *)(FsContext + 460) & 0xC0FF) != 0 || (*(_DWORD *)(FsContext + 200) & 8) != 0)
      && *(_DWORD *)(FsContext + 256) == 128
      && !*(_DWORD *)(FsContext + 448) )
    {
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(a1, 3221226650LL, 1836132);
      LOBYTE(v14) = v4 != 0;
      NtfsExtendedCompleteRequestInternal(a1, v4, 3221226650LL, v14, 0);
      if ( !NtfsStatusDebugFlags )
        return 3221226650LL;
      v21 = 1836133;
LABEL_121:
      NtfsStatusTraceAndDebugInternal(0, 3221226650LL, v21);
      return 3221226650LL;
    }
  }
  if ( (*(_DWORD *)(FsContext + 200) & 0x20000) != 0 )
  {
    if ( v20 )
    {
      if ( (*(_DWORD *)(a1 + 16) & 0x100000) == 0
        && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 8) != 0 )
      {
        McTemplateU0p_EtwWriteTransfer(v7, read_c1161, FsContext);
      }
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(a1, 3221226650LL, 1836175);
      LOBYTE(v14) = v4 != 0;
      NtfsExtendedCompleteRequestInternal(a1, v4, 3221226650LL, v14, 0);
      if ( !NtfsStatusDebugFlags )
        return 3221226650LL;
      v21 = 1836176;
      goto LABEL_121;
    }
    LOBYTE(v111) = 0;
  }
  LOBYTE(FileObject) = 1;
  InternalNtfsUpdateFileTimestampsFromNonpagedFcb(v14, 0, FileObject);
  ByteOffset = CurrentStackLocation->Parameters.Read.ByteOffset;
  *(LARGE_INTEGER *)v112 = ByteOffset;
  Length = CurrentStackLocation->Parameters.Read.Length;
  v116 = Length;
  if ( (_BYTE)v111 )
  {
    v26 = BYTE1(v138);
    if ( ((ByteOffset.LowPart | (unsigned int)Length) & (*(_DWORD *)(v23 + 364) - 1)) != 0 )
      v26 = 4;
    BYTE1(v138) = v26;
  }
  else
  {
    v26 = BYTE1(v138);
  }
  v106 = v26;
  if ( FsContext2 && (*(_DWORD *)(FsContext2 + 8) & 0x80u) != 0 )
  {
    *(_QWORD *)(a1 + 16) |= 0x40uLL;
    *(_DWORD *)(a1 + 460) = *(_DWORD *)(FsContext2 + 120);
  }
  FsContext2 = Length;
  v126 = Length;
  if ( 0x7FFFFFFFFFFFFFFFLL - ByteOffset.QuadPart < Length )
  {
    Status = -1073741811;
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(a1, 3221225485LL, 1835209);
    LOBYTE(v22) = v4 != 0;
    NtfsExtendedCompleteRequestInternal(a1, v4, 3221225485LL, v22, 0);
    if ( !NtfsStatusDebugFlags )
      return Status;
    v18 = 1836254;
LABEL_24:
    NtfsStatusTraceAndDebugInternal(0, Status, v18);
    return Status;
  }
  v117 = Length + ByteOffset.QuadPart;
  if ( !(_DWORD)Length )
  {
    *(_QWORD *)(a1 + 496) = 17;
    LOBYTE(v22) = v4 != 0;
    NtfsExtendedCompleteRequestInternal(a1, v4, 0, v22, 1);
    return 0;
  }
  v110 = v109 & 1;
  if ( !v110
    && v108
    && ((*(_DWORD *)(FsContext + 512) & 8) != 0
     || (v27 = *(_DWORD *)(FsContext + 200), (v27 & 0x20000) != 0)
     || *(_DWORD *)(FsContext + 452)
     || *(_QWORD *)(FsContext + 504) && v27 >= 0
     || (*(_DWORD *)(*(_QWORD *)(a1 + 144) + 12LL) & 0x40) != 0)
    || (*(_DWORD *)(FsContext + 200) & 0x20) == 0 )
  {
    v110 = 1;
    *(_DWORD *)(a1 + 12) |= 1u;
  }
  v28 = *(_QWORD *)(FsContext + 528);
  if ( v28 && *(_DWORD *)(v28 + 4) == 128 )
  {
    v29 = NtfsDetermineTransactionType(a1, (_DWORD)v125, FsContext, v118, v6, (__int64)&v128, (__int64)&v138);
    Status = v29;
    if ( v29 < 0 )
    {
      if ( NtfsStatusDebugFlags
        && (unsigned int)v29 < 0xFFFFFFED
        && v29 != -1073741802
        && (unsigned int)(v29 + 2147483643) > 1
        && v29 != -1073741807
        && v29 != -1073741608 )
      {
        NtfsStatusTraceAndDebugInternal(a1, (unsigned int)v29, 1835209);
      }
      goto LABEL_96;
    }
    Entry = v128;
    v106 = BYTE1(v138);
    FsContext2 = Length;
  }
  v114 &= 2u;
  NtfsInitializeIoContext(a1, a3, (unsigned __int8)v6);
  v31 = *(_QWORD *)(a1 + 208);
  v129 = v31;
  v32 = v123;
  if ( *(_BYTE *)(v123 + 10496) )
  {
    PerformanceCounter = *(LARGE_INTEGER *)(a1 + 496);
    if ( PerformanceCounter.QuadPart <= 23 )
    {
      PerformanceCounter = KeQueryPerformanceCounter(0);
      v32 = v123;
    }
    *(LARGE_INTEGER *)(*(_QWORD *)(a1 + 208) + 80LL) = PerformanceCounter;
    LODWORD(v137) = 0;
    v34 = v108;
    if ( v108 || (_BYTE)v111 )
      v35 = 0;
    else
      v35 = 2;
    v36 = v110;
    LOBYTE(v6) = v110 | v35 | (4 * (v6 | 4));
    BYTE3(v137) = v6;
    **(_DWORD **)(a1 + 208) |= v137;
    v31 = v129;
  }
  else
  {
    v36 = v110;
    v34 = v108;
  }
  if ( v115 == 4 )
  {
    if ( (*(_DWORD *)(v32 + 4) & 2) != 0 || (*(_DWORD *)(v32 + 24) & 0x40000) == 0 )
    {
      v37 = *(_QWORD *)v112;
    }
    else
    {
      v37 = *(_QWORD *)v112;
      if ( *(_QWORD *)v112 )
      {
        if ( *(_QWORD *)v112 != *(_QWORD *)(v32 + 424) * *(unsigned int *)(v32 + 364) )
        {
          v38 = 3LL << *(_BYTE *)(v32 + 492);
          if ( *(_QWORD *)v112 != v38 + (*(_QWORD *)(v32 + 408) << *(_BYTE *)(v32 + 488))
            && *(_QWORD *)v112 != v38 + (*(_QWORD *)(v32 + 416) << *(_BYTE *)(v32 + 488)) )
          {
            goto LABEL_117;
          }
        }
      }
      v39 = *(_DWORD *)(v32 + 360);
      if ( v39 <= *(_DWORD *)(v32 + 364) )
        v39 = *(_DWORD *)(v32 + 364);
      if ( (unsigned int)Length > v39 )
      {
LABEL_117:
        if ( NtfsStatusDebugFlags )
          NtfsStatusTraceAndDebugInternal(a1, 3221226650LL, 1836424);
        LOBYTE(v32) = v4 != 0;
        NtfsExtendedCompleteRequestInternal(a1, v4, 3221226650LL, v32, 0);
        if ( !NtfsStatusDebugFlags )
          return 3221226650LL;
        v21 = 1836425;
        goto LABEL_121;
      }
    }
    if ( (*(_DWORD *)(v118 + 4) & 0x100) == 0 )
    {
      v40 = *(_QWORD *)(FsContext + 32);
      if ( v40 <= v37 )
      {
        LOBYTE(v32) = v4 != 0;
        NtfsExtendedCompleteRequestInternal(a1, v4, 3221225489LL, v32, 0);
        return 3221225489LL;
      }
      if ( v40 < v117 )
        LODWORD(Length) = v40 - v37;
    }
    if ( !v36 )
    {
      NtfsSetIoContextAsync(a1, FsContext, Length, v118, 0, 0);
      v37 = *(_QWORD *)v112;
    }
    Status = NtfsVolumeDasdIo(a1, (__int64)v4, FsContext, v118, v37, Length);
    if ( (Status & 0x80000000) == 0 )
      NtfsUpdateFileTimestampsForAccess(v125, v124, v118);
    if ( v114 && !v108 && (Status & 0x80000000) == 0 )
      v127->FileObject->CurrentByteOffset.QuadPart = v4->IoStatus.Information + *(_QWORD *)v112;
    if ( !v36 )
      return Status;
    if ( NtfsStatusDebugFlags
      && Status
      && Status != 294
      && Status - 298 > 1
      && Status < 0xFFFFFFED
      && Status != -1073741802
      && Status + 2147483643 > 1
      && Status != -1073741807
      && Status != 259
      && Status != -1073741608 )
    {
      NtfsStatusTraceAndDebugInternal(a1, Status, 1835209);
    }
LABEL_96:
    LOBYTE(v30) = v4 != 0;
    NtfsExtendedCompleteRequestInternal(a1, v4, Status, v30, (Status & 0x80000000) == 0);
    return Status;
  }
  v131 = FsContext;
  v107 = Length;
  v134 = v31;
  if ( v34 )
  {
    v31 = *(_QWORD *)(v32 + 808) + 704LL * (HIDWORD(KeGetPcr()[1].LockArray) % NtfsNumberProcessors);
    v41 = v124;
    if ( (*(_DWORD *)(v124 + 4) & 0x100) != 0 )
    {
      if ( FsContext == *(_QWORD *)(v32 + 64) )
      {
        ++*(_QWORD *)(v31 + 416);
        *(_QWORD *)(v31 + 424) += FsContext2;
      }
      else
      {
        ++*(_QWORD *)(v31 + 56);
        *(_QWORD *)(v31 + 64) += FsContext2;
      }
      if ( FsContext == *(_QWORD *)(v32 + 48) )
      {
        ++*(_QWORD *)(v31 + 112);
        *(_QWORD *)(v31 + 120) += FsContext2;
      }
      else if ( FsContext == *(_QWORD *)(v32 + 32) )
      {
        ++*(_QWORD *)(v31 + 224);
        *(_QWORD *)(v31 + 232) += FsContext2;
      }
      else if ( FsContext == *(_QWORD *)(v32 + 72) )
      {
        ++*(_QWORD *)(v31 + 256);
        *(_QWORD *)(v31 + 264) += FsContext2;
      }
      else if ( FsContext == *(_QWORD *)(v32 + 208) )
      {
        ++*(_QWORD *)(v31 + 320);
        *(_QWORD *)(v31 + 328) += FsContext2;
      }
    }
    else if ( *(_DWORD *)(FsContext + 256) == 128 )
    {
      ++*(_QWORD *)(v31 + 8);
      *(_QWORD *)(v31 + 16) += FsContext2;
    }
    else
    {
      ++*(_QWORD *)(v31 + 384);
      *(_QWORD *)(v31 + 392) += FsContext2;
    }
  }
  else
  {
    v41 = v124;
  }
  v96 = v34 == 0;
  v42 = v111;
  if ( !v96 || !(_BYTE)v111 )
    *(_DWORD *)(FsContext + 224) = 0;
  if ( (_BYTE)v111 && *(_DWORD *)(v41 + 8) <= 3u )
  {
    if ( a1 != *(_QWORD *)(a1 + 144) )
    {
      v6 = 255;
      v43 = v138;
      goto LABEL_174;
    }
    goto LABEL_543;
  }
  TopLevelIrp = IoGetTopLevelIrp();
  if ( HIBYTE(TopLevelIrp->Type)
    && (HIDWORD(TopLevelIrp->AssociatedIrp.MasterIrp->ThreadListEntry.Flink->Flink) & 0x200) == 0 )
  {
    LOBYTE(TopLevelIrp->Type) = 0;
  }
  if ( v108 )
  {
    if ( !*(_QWORD *)(FsContext + 16)
      || ExIsResourceAcquiredSharedLite(*(PERESOURCE *)(*(_QWORD *)(FsContext + 184) + 112LL)) )
    {
      if ( *(_DWORD *)(FsContext + 516) == 3 && *(_DWORD *)(FsContext + 256) == 128 )
      {
LABEL_573:
        if ( NtfsStatusDebugFlags )
          NtfsStatusTraceAndDebugInternal(a1, 3221226659LL, 1836991);
        NtfsRaiseStatusInternal(a1, -1073740637, 0, 0, 1836991);
        goto LABEL_576;
      }
      v6 = 255;
      v43 = v138;
      goto LABEL_277;
    }
    v59 = *(unsigned int *)(*(_QWORD *)(FsContext + 184) + 4LL);
    if ( (v59 & 0x100) != 0 )
    {
      LOBYTE(v42) = 1;
      if ( !(unsigned __int8)NtfsAcquireResourceShared(v59, FsContext, v42, v32) )
      {
LABEL_569:
        NtfsRaiseStatusInternal(a1, -1073741608, 0, 0, 1836954);
LABEL_570:
        if ( NtfsStatusDebugFlags )
          NtfsStatusTraceAndDebugInternal(a1, 3221226659LL, 1836966);
        NtfsRaiseStatusInternal(a1, -1073740637, 0, 0, 1836966);
        goto LABEL_573;
      }
      v43 = v138 | 0x10;
    }
    else
    {
      if ( IoGetTopLevelIrp()->AssociatedIrp.MasterIrp == (struct _IRP *)7 )
      {
        LOBYTE(v60) = 1;
        if ( !(unsigned __int8)NtfsAcquirePagingResourceSharedStarveExclusive(a1, FsContext, v60) )
        {
LABEL_567:
          NtfsRaiseStatusInternal(a1, -1073741608, 0, 0, 1836932);
          goto LABEL_568;
        }
      }
      else
      {
        if ( ExIsResourceAcquiredSharedLite((PERESOURCE)(*(_QWORD *)(*(_QWORD *)(FsContext + 184) + 104LL) + 64LL)) )
        {
          v43 = v138;
          goto LABEL_270;
        }
        LOBYTE(v42) = 1;
        if ( !(unsigned __int8)NtfsAcquirePagingShared(a1, FsContext, v42, 0) )
        {
LABEL_568:
          NtfsRaiseStatusInternal(a1, -1073741608, 0, 0, 1836945);
          goto LABEL_569;
        }
      }
      v43 = v138 | 1;
    }
    LOBYTE(v138) = v43;
LABEL_270:
    if ( *(_DWORD *)(FsContext + 516) == 3 && *(_DWORD *)(FsContext + 256) == 128 )
      goto LABEL_570;
    v6 = 255;
    goto LABEL_277;
  }
  v120 = 0;
  v46 = 0;
  LOBYTE(v137) = 0;
  LOBYTE(v6) = *(_BYTE *)(FsContext + 460) || (v106 & 2) != 0;
  v47 = v111;
  LOBYTE(FsContext2) = !(_BYTE)v111 || (_BYTE)v6;
  v49 = 1;
  if ( !v110 )
  {
    if ( v114
      || !(_BYTE)v111
      || (IoPriorityHint = IoGetIoPriorityHint(v4), v47 = v111, IoPriorityHint >= IoPriorityNormal) )
    {
      v49 = 0;
    }
  }
  if ( (*(_DWORD *)(a1 + 12) & 0x100) == 0
    && (!(_BYTE)FsContext2 || *(_QWORD *)(*(_QWORD *)(FsContext + 288) + 24LL))
    && (!v47 || !*(_QWORD *)(*(_QWORD *)(FsContext + 288) + 16LL) || *(_DWORD *)(FsContext + 544)) )
  {
    v50 = *(_QWORD *)(FsContext + 528);
    if ( (!v50 || (*(_DWORD *)(v50 + 24) & 0x1000) == 0)
      && ((!v47 || !(_BYTE)v6) && !Entry || *(_QWORD *)(FsContext + 280)) )
    {
      if ( !v47
        || (_BYTE)v6
        || _bittest16((const signed __int16 *)(FsContext + 460), 0xEu)
        || IoGetIoPriorityHint(v4) < IoPriorityNormal )
      {
        v51 = 0;
      }
      else
      {
        v51 = &v137;
      }
      v52 = NtfsAcquirePagingShared(a1, FsContext, v49, v51);
      v53 = v52;
      v120 = v52;
      if ( !v52
        || (!(_BYTE)FsContext2 || (v54 = *(_QWORD *)(*(_QWORD *)(FsContext + 288) + 24LL)) != 0)
        && ((v54 = v111, !(_BYTE)v111)
         || !*(_QWORD *)(*(_QWORD *)(FsContext + 288) + 16LL)
         || *(_DWORD *)(FsContext + 544))
        && ((v55 = *(_QWORD *)(FsContext + 528)) == 0 || (*(_DWORD *)(v55 + 24) & 0x1000) == 0)
        && ((!(_BYTE)v111 || !(_BYTE)v6) && !Entry || *(_QWORD *)(FsContext + 280)) )
      {
        v56 = v138;
        v46 = v137;
        goto LABEL_230;
      }
      NtfsReleasePaging(v54, v129, FsContext, (unsigned __int8)v137);
      LOBYTE(v137) = 0;
    }
  }
  v53 = (unsigned __int8)NtfsAcquirePagingResourceExclusive(a1, FsContext, v49, v32);
  v56 = v138 | 4;
  LOBYTE(v138) = v138 | 4;
  v120 = v53;
LABEL_230:
  if ( !v53 )
  {
LABEL_546:
    NtfsRaiseStatusInternal(a1, -1073741608, 0, 0, 1836694);
LABEL_547:
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(a1, 3221226659LL, 1836706);
    NtfsRaiseStatusInternal(a1, -1073740637, 0, 0, 1836706);
    goto LABEL_550;
  }
  v43 = v56 & 0xFC | 1 | (2 * (v46 & 1));
  LOBYTE(v138) = v43;
  if ( *(_DWORD *)(FsContext + 516) == 3 && *(_DWORD *)(FsContext + 256) == 128 )
    goto LABEL_547;
  v6 = 255;
  if ( (unsigned __int8)*(_WORD *)(FsContext + 460) && (*(_BYTE *)(a1 + 16) & 0x40) != 0 )
  {
LABEL_550:
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(a1, 3221226619LL, 1836721);
    v57 = NtfsRaiseStatusInternal(a1, -1073740677, 0, 0, 1836721);
    goto LABEL_553;
  }
  LODWORD(FsContext2) = v111;
  if ( (_BYTE)v111
    && *(_QWORD *)(*(_QWORD *)(FsContext + 288) + 16LL)
    && !*(_DWORD *)(FsContext + 544)
    && !(unsigned __int8)*(_WORD *)(FsContext + 460) )
  {
    v57 = NtfsCacheCoherencyFlush(a1, v53, FsContext, v112[0], v126, 0, *(_DWORD *)(FsContext + 220) == 0);
    LODWORD(FsContext2) = v57;
    if ( v57 < 0 )
    {
LABEL_553:
      if ( NtfsStatusDebugFlags
        && (unsigned int)v57 < 0xFFFFFFED
        && v57 != -1073741802
        && (unsigned int)(v57 + 2147483643) > 1
        && (_DWORD)FsContext2 != -1073741807
        && (_DWORD)FsContext2 != -1073741608 )
      {
        NtfsStatusTraceAndDebugInternal(a1, (unsigned int)FsContext2, 1836755);
      }
      NtfsRaiseStatusInternal(a1, FsContext2, 0, 0, 1836755);
LABEL_561:
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(a1, 3221225768LL, 1836798);
      NtfsRaiseStatusInternal(a1, -1073741528, 0, 0, 1836798);
      goto LABEL_564;
    }
    LODWORD(FsContext2) = v111;
  }
  v58 = *(_QWORD *)(FsContext + 528);
  if ( v58 && (*(_DWORD *)(v58 + 24) & 0x1000) != 0 )
    TxfDoPublishCommittedChangesToDefaultReaderSectionWithTryExcept(a1, FsContext, (unsigned __int8)FsContext2);
  if ( v118 && (*(_DWORD *)(v118 + 4) & 0x8000) != 0 )
    goto LABEL_561;
  if ( (*(_DWORD *)(FsContext + 512) & 0x1000000) != 0 )
  {
LABEL_564:
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(a1, 3221225480LL, 1836806);
    NtfsRaiseStatusInternal(a1, -1073741816, 0, 0, 1836806);
    goto LABEL_567;
  }
  if ( !(_BYTE)FsContext2 || !*(_BYTE *)(FsContext + 460) && (v106 & 2) == 0 )
    goto LABEL_276;
  LOBYTE(v42) = 0;
  LOBYTE(v111) = 0;
  v119 = 0;
  *(_BYTE *)(*(_QWORD *)(a1 + 208) + 3LL) |= 2u;
  if ( !*(_QWORD *)(FsContext + 280) )
  {
    NtfsLockFsRtlHeader(a1, FsContext);
    NtfsCreateInternalAttributeStream(a1, FsContext, 0, 0, 0, 0);
    NtfsUnlockFsRtlHeader(a1, FsContext);
  }
  if ( (v106 & 1) == 0 )
  {
    LODWORD(Length) = v116;
    if ( (v106 & 2) == 0 )
      v125 = *(struct _FILE_OBJECT **)(FsContext + 280);
  }
  else
  {
LABEL_276:
    LODWORD(Length) = v116;
  }
LABEL_277:
  v31 = *(unsigned int *)(FsContext + 512);
  if ( (v31 & 0x10000) != 0 )
    LODWORD(FsContext2) = -1073741202;
  else
    LODWORD(FsContext2) = (v31 & 0x1000000) != 0 ? 0xC0000008 : 0;
  if ( (v31 & 0x40) != 0 )
  {
    LODWORD(FsContext2) = -1073741533;
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(0, 3221225763LL, 1837015);
    goto LABEL_576;
  }
  if ( (int)FsContext2 < 0 )
  {
LABEL_576:
    if ( NtfsStatusDebugFlags
      && (unsigned int)FsContext2 < 0xFFFFFFED
      && (_DWORD)FsContext2 != -1073741802
      && (unsigned int)(FsContext2 + 2147483643) > 1
      && (_DWORD)FsContext2 != -1073741807
      && (_DWORD)FsContext2 != -1073741608 )
    {
      NtfsStatusTraceAndDebugInternal(a1, (unsigned int)FsContext2, 1837023);
    }
    NtfsRaiseStatusInternal(a1, FsContext2, 0, 0, 1837023);
    goto LABEL_584;
  }
LABEL_174:
  if ( (*(_DWORD *)(FsContext + 200) & 0x20) == 0 )
  {
    if ( (v43 & 0x10) == 0 )
    {
      LOBYTE(v42) = 1;
      NtfsAcquireResourceShared(v31, FsContext, v42, v32);
      v43 |= 0x18u;
      LOBYTE(v138) = v43;
    }
    NtfsUpdateScbFromAttribute(a1, FsContext, 0);
    if ( (v43 & 8) != 0 )
    {
      LODWORD(FsContext2) = 1794;
      if ( *(_WORD *)FsContext == 1794 )
        v44 = (struct _ERESOURCE *)(*(_QWORD *)(FsContext + 104) + 64LL);
      else
        v44 = *(struct _ERESOURCE **)(FsContext + 8);
      ExReleaseResourceLite(v44);
      v43 &= 0xE7u;
      LOBYTE(v138) = v43;
    }
  }
  if ( *(_DWORD *)(FsContext + 256) == 128 && (unsigned __int8)*(_WORD *)(FsContext + 460) >= 2u )
  {
LABEL_584:
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(a1, 3221225659LL, 1837067);
    NtfsRaiseStatusInternal(a1, -1073741637, 0, 0, 1837067);
    goto LABEL_587;
  }
  if ( v115 == 2 && !v108 )
  {
    if ( (v106 & 1) == 0 )
    {
      v61 = FsRtlCheckOplock((POPLOCK)(FsContext + 88), v4, (PVOID)a1, NtfsOplockComplete, NtfsPrePostIrp);
      Status = v61;
      if ( v61 )
      {
        v4 = 0;
        v121 = 0;
        a1 = 0;
        if ( NtfsStatusDebugFlags
          && (((v61 - 294) & 0xFFFFFFFA) != 0 || v61 == 295)
          && v61 < 0xFFFFFFED
          && v61 != -1073741802
          && v61 + 2147483643 > 1
          && v61 != -1073741807
          && v61 != 259
          && v61 != -1073741608 )
        {
          NtfsStatusTraceAndDebugInternal(0, v61, 1837096);
        }
        goto LABEL_323;
      }
      if ( !*(_BYTE *)(FsContext + 5) )
      {
        if ( (*(_DWORD *)(*(_QWORD *)(FsContext + 192) + 4LL) & 0x4000005) == 1
          && *(_WORD *)FsContext == 1797
          && FsRtlOplockIsFastIoPossible((POPLOCK)(FsContext + 88)) )
        {
          if ( *(_DWORD *)(FsContext + 452)
            || (v63 = *(_QWORD *)(FsContext + 584)) != 0 && *(_BYTE *)(v63 + 16)
            || (v64 = *(_QWORD *)(FsContext + 192), (*(_DWORD *)(v64 + 4) & 0x2000000) != 0)
            || (*(_DWORD *)(FsContext + 512) & 0x4000000) != 0
            || *(_QWORD *)(FsContext + 528)
            || (v65 = 1, *(_QWORD *)(v64 + 40)) )
          {
            v65 = 2;
          }
        }
        else
        {
          v65 = 0;
        }
        v115 = v65;
        *(_BYTE *)(FsContext + 5) = v65;
      }
    }
    v66 = *(FILE_LOCK **)(FsContext + 584);
    if ( v66 )
    {
      if ( !FsRtlCheckLockForReadAccess(v66, v4) )
      {
        Status = -1073741740;
        if ( NtfsStatusDebugFlags )
        {
          v67 = 1837117;
LABEL_322:
          NtfsStatusTraceAndDebugInternal(0, Status, v67);
        }
LABEL_323:
        v68 = v107;
LABEL_324:
        v69 = (volatile signed __int32 *)Entry;
        v70 = v106;
LABEL_325:
        if ( v4 )
        {
          if ( (Status & 0x80000000) == 0 && (v70 & 1) != 0 && (v43 & 0x40) == 0 )
          {
            TxfReadVersion(a1, (__int64)v4, (__int64)v125, v69, (__int64)v112, v68, (unsigned __int8)v111);
            Status = v4->IoStatus.Status;
          }
          v71 = v108;
          v72 = v114;
          if ( v108 || !v114 )
          {
            v100 = v127;
          }
          else
          {
            if ( (Status & 0xC0000000) == 0xC0000000 )
              Information = 0;
            else
              Information = v4->IoStatus.Information;
            v99 = Information + *(_QWORD *)v112;
            v100 = v127;
            v127->FileObject->CurrentByteOffset.QuadPart = v99;
            v71 = 0;
            v72 = v114;
          }
          if ( (Status & 0x80000000) == 0 && v72 && !v71 )
            NtfsUpdateFileTimestampsForAccess(v100->FileObject, *(_QWORD *)(FsContext + 184), v118);
          NtfsCleanupTransaction(a1, Status, 0);
        }
        if ( (v70 & 1) != 0 )
          _InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)v69 + 2) + 44LL));
        if ( (v43 & 0x20) != 0 )
        {
          v101 = *((_QWORD *)v69 + 2);
          if ( v101 )
            v101 = *(_QWORD *)(v101 + 64);
          v102 = 0;
          do
          {
            v103 = 0;
            if ( v101 && !v102 )
            {
              ExAcquireResourceExclusiveLite(*(PERESOURCE *)(v101 + 136), 1u);
              v102 = 1;
            }
            _InterlockedDecrement(v69 + 1);
            if ( !*((_DWORD *)v69 + 1) )
            {
              v103 = (volatile signed __int32 *)*((_QWORD *)v69 + 5);
              TxfDeleteTxfVscb((char *)v69);
              v102 = 0;
            }
            v69 = v103;
          }
          while ( v103 );
          if ( v102 && v101 )
            ExReleaseResourceLite(*(PERESOURCE *)(v101 + 136));
          v4 = v121;
        }
        if ( (v43 & 1) != 0 )
          NtfsReleasePaging(v68, v129, FsContext, (v43 & 2) != 0);
        if ( (v43 & 0x10) != 0 )
        {
          if ( *(_WORD *)FsContext == 1794 )
            v104 = (struct _ERESOURCE *)(*(_QWORD *)(FsContext + 104) + 64LL);
          else
            v104 = *(struct _ERESOURCE **)(FsContext + 8);
          ExReleaseResourceLite(v104);
        }
        if ( NtfsStatusDebugFlags
          && Status
          && Status != 294
          && Status - 298 > 1
          && Status < 0xFFFFFFED
          && Status != -1073741802
          && Status + 2147483643 > 1
          && Status != -1073741807
          && Status != 259
          && Status != -1073741608 )
        {
          NtfsStatusTraceAndDebugInternal(a1, Status, 1835209);
        }
        LOBYTE(v62) = v4 != 0;
        NtfsExtendedCompleteRequestInternal(a1, v4, Status, v62, (Status & 0x80000000) == 0);
        return Status;
      }
    }
  }
  if ( ((v106 & 1) != 0 || (v106 & 2) != 0) && !v110 )
  {
    v110 = 1;
    *(_DWORD *)(a1 + 12) |= 1u;
    *(_BYTE *)(*(_QWORD *)(a1 + 208) + 3LL) |= 1u;
  }
  if ( (*(_DWORD *)(FsContext + 512) & 0x10000000) != 0 )
  {
    *(_DWORD *)(a1 + 12) |= 0x10000000u;
    NtfsLockUserBuffer(a1, v4, 1, (unsigned int)Length);
  }
  if ( (v106 & 1) != 0 )
  {
    FsRtlAcquireHeaderMutex(FsContext + 120, FsContext + 160, v42);
    v74 = *((_QWORD *)Entry + 33);
    v137 = *(_QWORD *)(v74 + 8);
    v126 = v137;
    v75 = *(_QWORD *)(v74 + 16);
    v130 = v75;
    FsRtlReleaseHeaderMutex(FsContext + 120, FsContext + 160);
    v76 = v137;
  }
  else
  {
    NtfsGetScbFileSizes(FsContext, &v135, 0);
    v76 = *((_QWORD *)&v135 + 1);
    v126 = *((_QWORD *)&v135 + 1);
    v75 = v136;
    v130 = v136;
  }
  v77 = v76;
  v78 = v108;
  if ( v108 )
  {
    if ( *(_DWORD *)(FsContext + 256) == 128
      && *(_BYTE *)(FsContext + 460)
      && (*(_DWORD *)(FsContext + 200) & 8) == 0
      && (v106 & 1) == 0 )
    {
      v76 = -*(_DWORD *)(FsContext + 452) & (unsigned __int64)(*(_DWORD *)(FsContext + 452) - 1 + v76);
      v126 = v76;
      v77 = v76;
    }
    if ( (*(_DWORD *)(FsContext + 512) & 1) != 0 )
    {
      *(_QWORD *)v112 += *(_QWORD *)(v123 + 1952);
      v117 = *(_QWORD *)v112 + (unsigned int)v116;
      v133 = v117;
    }
    v79 = IoGetTopLevelIrp();
    v78 = v108;
    if ( v79->AssociatedIrp.MasterIrp == (struct _IRP *)2 )
      *(_DWORD *)(a1 + 12) |= 0x800u;
  }
  v80 = *(_QWORD *)v112;
  if ( *(__int64 *)v112 >= v77 )
  {
    *(_QWORD *)(*(_QWORD *)(a1 + 208) + 80LL) = 18;
    Status = -1073741807;
    goto LABEL_323;
  }
  if ( v117 <= v77 )
  {
    LODWORD(FsContext2) = v116;
  }
  else
  {
    v81 = *(_QWORD *)(FsContext + 528);
    if ( v81 && (*(_DWORD *)(v81 + 24) & 0x40) != 0 && (_DWORD)v78 )
    {
      LOBYTE(PostIrpRoutine) = 0;
      NtfsFillIrpBuffer(a1, v4, (unsigned int)(v117 - v77), (unsigned int)(v77 - v112[0]), (_DWORD)PostIrpRoutine);
      v80 = *(_QWORD *)v112;
    }
    FsContext2 = (unsigned int)(v77 - v80);
    v116 = FsContext2;
    v122 = FsContext2;
    v117 = v80 + (unsigned int)FsContext2;
    v133 = v117;
    v107 = FsContext2;
    v132 = FsContext2;
  }
  if ( (*(_DWORD *)(FsContext + 200) & 8) != 0 || (*(_DWORD *)(FsContext + 512) & 0x4000) != 0 )
  {
    if ( !(_BYTE)v111 )
      goto LABEL_497;
    if ( (v43 & 0x10) == 0 )
    {
      LOBYTE(v78) = 1;
      NtfsAcquireResourceShared(v80, FsContext, v78, v62);
      v43 |= 0x18u;
      LOBYTE(v138) = v43;
    }
    if ( (*(_DWORD *)(FsContext + 200) & 8) != 0 )
    {
      if ( (v106 & 1) == 0 || *(_QWORD *)(FsContext + 32) >= v76 )
      {
        *(_QWORD *)(*(_QWORD *)(a1 + 208) + 80LL) = 15;
        v82 = FsContext2;
        if ( (unsigned int)FsContext2 >= (__int64)(*(_QWORD *)(FsContext + 32) - *(_QWORD *)v112) )
          v82 = *(_DWORD *)(FsContext + 32) - v112[0];
        LODWORD(PostIrpRoutine) = v82;
        NtfsNonCachedResidentRead(a1, (int)v4, FsContext, v112[0], (size_t)PostIrpRoutine);
      }
      Status = 0;
      goto LABEL_323;
    }
    if ( (v43 & 8) != 0 )
    {
      if ( *(_WORD *)FsContext == 1794 )
        v83 = (struct _ERESOURCE *)(*(_QWORD *)(FsContext + 104) + 64LL);
      else
        v83 = *(struct _ERESOURCE **)(FsContext + 8);
      ExReleaseResourceLite(v83);
      v43 &= 0xE7u;
      LOBYTE(v138) = v43;
    }
  }
  if ( !(_BYTE)v111 )
  {
LABEL_497:
    v69 = (volatile signed __int32 *)Entry;
    Status = NtfsCachedRead(a1, v125, v4, FsContext, *(union _LARGE_INTEGER *)v112, FsContext2, &v138, (__int64)Entry);
    v70 = BYTE1(v138);
    v43 = v138;
    v68 = v107;
    if ( Status == 259 )
    {
      v4 = 0;
      v121 = 0;
      a1 = 0;
    }
    goto LABEL_325;
  }
  if ( (v106 & 1) != 0 || (*(_BYTE *)(FsContext + 4) & 0x20) == 0 )
  {
    v6 = v116;
    goto LABEL_386;
  }
  v6 = v116;
  if ( *(_BYTE *)(FsContext + 460) && !(unsigned __int8)NtfsReserveClusters(a1, 0) )
  {
LABEL_587:
    NtfsAllocateDiskFullContext(a1, v6, 0x27B001C0961LL);
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(a1, 3221225599LL, 1837410);
    NtfsRaiseStatusInternal(a1, -1073741697, 0, 0, 1837410);
LABEL_590:
    NtfsAllocateDiskFullContext(a1, (unsigned int)FsContext2, 0x27C001C0A52LL);
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(a1, 3221225599LL, 1837651);
    NtfsRaiseStatusInternal(a1, -1073741697, 0, 0, 1837651);
    goto LABEL_593;
  }
LABEL_386:
  if ( *(_QWORD *)(FsContext + 504)
    && *(int *)(FsContext + 200) >= 0
    && !v110
    && (_QWORD)xmmword_140095740
    && *(_DWORD *)(FsContext + 256) == 128 )
  {
    v110 = 1;
    *(_DWORD *)(a1 + 12) |= 1u;
    *(_BYTE *)(*(_QWORD *)(a1 + 208) + 3LL) |= 1u;
  }
  v84 = v106;
  if ( (v106 & 1) != 0 )
  {
    v86 = v117;
  }
  else
  {
    if ( (*(_DWORD *)(FsContext + 512) & 0x40000) == 0
      && *(_BYTE *)(FsContext + 460)
      && *(_DWORD *)(FsContext + 256) == 128 )
    {
      if ( (v43 & 0x10) == 0 )
      {
        LOBYTE(v78) = 1;
        NtfsAcquireResourceShared(v80, FsContext, v78, v62);
        v43 |= 0x18u;
        LOBYTE(v138) = v43;
      }
      v85 = *(_QWORD *)(FsContext + 464);
      v86 = v117;
      if ( v117 > v85 )
      {
        if ( v85 <= *(__int64 *)v112 )
        {
LABEL_400:
          *(_QWORD *)(*(_QWORD *)(a1 + 208) + 80LL) = 1;
          LOBYTE(PostIrpRoutine) = 0;
          NtfsFillIrpBuffer(a1, v4, v6, 0, (_DWORD)PostIrpRoutine);
          v4->IoStatus.Information = v6;
          Status = 0;
          goto LABEL_323;
        }
        v6 = v85 - v112[0];
        v122 = v85 - v112[0];
        if ( !v110 )
        {
          v110 = 1;
          *(_DWORD *)(a1 + 12) |= 1u;
        }
      }
      if ( (v43 & 8) != 0 )
      {
        if ( *(_WORD *)FsContext == 1794 )
          v87 = (struct _ERESOURCE *)(*(_QWORD *)(FsContext + 104) + 64LL);
        else
          v87 = *(struct _ERESOURCE **)(FsContext + 8);
        ExReleaseResourceLite(v87);
        v43 &= 0xE7u;
        LOBYTE(v138) = v43;
      }
    }
    else
    {
      v86 = v117;
    }
    v84 = v106;
  }
  if ( v86 <= v75 )
  {
LABEL_443:
    if ( (v106 & 1) != 0 )
    {
      v90 = *(_QWORD *)(FsContext + 40);
      if ( *(__int64 *)v112 < v90 )
      {
        if ( *(_QWORD *)v112 + v6 <= v90 )
          v91 = v6;
        else
          v91 = v90 - v112[0];
      }
      else
      {
        v91 = 0;
      }
      v92 = *(_DWORD *)(*(_QWORD *)(a1 + 104) + 364LL);
      if ( ((v92 - 1) & v112[0]) != 0 )
      {
LABEL_453:
        if ( !v91 )
        {
LABEL_486:
          Status = v4->IoStatus.Status;
          if ( (Status & 0x80000000) != 0 )
          {
            *(_DWORD *)(a1 + 24) = Status;
            if ( NtfsStatusDebugFlags
              && Status < 0xFFFFFFED
              && Status != -1073741802
              && Status + 2147483643 > 1
              && Status != -1073741807
              && Status != -1073741608 )
            {
              NtfsStatusTraceAndDebugInternal(a1, Status, 1838025);
            }
            v98 = FsRtlNormalizeNtstatus(Status, -1073741591);
            ExRaiseStatus(v98);
          }
          v68 = v107;
          v4->IoStatus.Information = v107;
          if ( v107 <= v6 )
            goto LABEL_324;
          LOBYTE(PostIrpRoutine) = 0;
          NtfsFillIrpBuffer(a1, v4, v107 - v6, v6, (_DWORD)PostIrpRoutine);
          goto LABEL_323;
        }
        if ( (*(_DWORD *)(v123 + 8204) & 1) != 0
          && (*(_DWORD *)(FsContext + 200) & 0x20000) == 0
          && IoGetIoPriorityHint(v4) > IoPriorityLow )
        {
          if ( (v94 = *(_DWORD *)(FsContext + 256), v94 == 128) && !*(_WORD *)(FsContext + 264) || v94 == 160 )
          {
            if ( ((*(_DWORD *)(v124 + 8) - 2) & 0xFFFFFFFB) != 0 )
              NtfsHeatLogIo(v4, v124);
          }
        }
        v95 = v107;
        if ( !v110 )
        {
          if ( !v108 || (v43 & 1) != 0 )
          {
            NtfsSetIoContextAsync(a1, FsContext, v107, v118, *(_QWORD *)(FsContext + 16), (v43 & 2) != 0);
          }
          else if ( (v43 & 0x10) != 0 )
          {
            NtfsSetIoContextAsync(a1, FsContext, v107, v118, *(_QWORD *)(FsContext + 8), 0);
          }
          else
          {
            NtfsSetIoContextAsync(a1, FsContext, v107, v118, 0, 0);
          }
        }
        if ( (v106 & 4) != 0 )
        {
          v96 = *(_BYTE *)(FsContext + 460) == 0;
          if ( !*(_BYTE *)(FsContext + 460) )
          {
            if ( (*(_BYTE *)(a1 + 16) & 0x40) != 0 )
            {
              Status = -1073741811;
              if ( !NtfsStatusDebugFlags )
                goto LABEL_323;
              v67 = 1837892;
              goto LABEL_322;
            }
            if ( (v106 & 1) == 0 || v91 > v95 )
              v91 = v6;
            v97 = NtfsNonCachedNonAlignedIo(a1, (_DWORD)v4, FsContext, v112[0], v91);
            goto LABEL_482;
          }
        }
        else
        {
          v96 = *(_BYTE *)(FsContext + 460) == 0;
        }
        if ( !v96 )
          v91 = v6;
        v97 = NtfsNonCachedIo(a1, v4, FsContext, *(__int64 *)v112, v91, 0);
LABEL_482:
        Status = v97;
        if ( v97 == 259 )
        {
          v43 &= 0xEEu;
          LOBYTE(v138) = v43;
          *(_QWORD *)(a1 + 208) = 0;
          v4 = 0;
          v121 = 0;
          goto LABEL_323;
        }
        if ( v97 >= 0 )
          *(_BYTE *)(*(_QWORD *)(a1 + 208) + 3LL) |= 1u;
        goto LABEL_486;
      }
      v93 = v92 + v91 - 1;
    }
    else
    {
      v92 = *(_DWORD *)(*(_QWORD *)(a1 + 104) + 364LL);
      v93 = v6 + v92 - 1;
    }
    v91 = -v92 & v93;
    goto LABEL_453;
  }
  if ( (v84 & 1) == 0 )
  {
    if ( *(_BYTE *)(FsContext + 460) )
    {
      if ( (v43 & 0x10) == 0 )
      {
        LOBYTE(v78) = 1;
        NtfsAcquireResourceShared(v80, FsContext, v78, v62);
        v43 |= 0x18u;
        LOBYTE(v138) = v43;
      }
      if ( v75 < *(_QWORD *)(FsContext + 464) )
        v75 = *(_QWORD *)(FsContext + 464);
      v130 = v75;
    }
    v84 = v106;
  }
  if ( v86 <= v75 )
  {
LABEL_438:
    if ( (v43 & 8) != 0 )
    {
      if ( *(_WORD *)FsContext == 1794 )
        v89 = (struct _ERESOURCE *)(*(_QWORD *)(FsContext + 104) + 64LL);
      else
        v89 = *(struct _ERESOURCE **)(FsContext + 8);
      ExReleaseResourceLite(v89);
      v43 &= 0xE7u;
      LOBYTE(v138) = v43;
    }
    goto LABEL_443;
  }
  if ( *(__int64 *)v112 < v75 )
  {
    v88 = v75 - v112[0];
    if ( v6 < v88 )
      v88 = v6;
    v6 = v88;
    v122 = v88;
    if ( !v110 )
    {
      v110 = 1;
      *(_DWORD *)(a1 + 12) |= 1u;
    }
    if ( (v106 & 1) != 0 )
      goto LABEL_438;
    if ( !v108 )
      goto LABEL_438;
    if ( (*(_BYTE *)(FsContext + 4) & 0x20) == 0 )
      goto LABEL_438;
    if ( (*(_WORD *)(FsContext + 460) & 0x80FF) != 0x8000 )
      goto LABEL_438;
    LODWORD(FsContext2) = v107 - v88;
    if ( (unsigned __int8)NtfsReserveClusters(a1, 0) )
      goto LABEL_438;
    goto LABEL_590;
  }
  if ( (v84 & 1) != 0
    || !v108
    || (*(_BYTE *)(FsContext + 4) & 0x20) == 0
    || (*(_WORD *)(FsContext + 460) & 0x80FF) != 0x8000
    || (unsigned __int8)NtfsReserveClusters(a1, 0) )
  {
    goto LABEL_400;
  }
LABEL_593:
  NtfsAllocateDiskFullContext(a1, v6, 0x27D001C0A6BLL);
  if ( NtfsStatusDebugFlags )
    NtfsStatusTraceAndDebugInternal(a1, 3221225599LL, 1837676);
  result = NtfsRaiseStatusInternal(a1, -1073741697, 0, 0, 1837676);
  __debugbreak();
  return result;
}

```

## disassembly

```asm
0x14002c840  mov     r11, rsp
0x14002c843  mov     [r11+8], rbx
0x14002c847  mov     [r11+18h], rsi
0x14002c84b  push    rdi
0x14002c84c  push    r12
0x14002c84e  push    r13
0x14002c850  push    r14
0x14002c852  push    r15
0x14002c854  sub     rsp, 120h
0x14002c85b  mov     r15, r8
0x14002c85e  mov     r13, rdx
0x14002c861  mov     [r11-0B0h], rdx
0x14002c868  mov     rsi, rcx
0x14002c86b  xor     edi, edi
0x14002c86d  mov     qword ptr [rsp+148h+var_E8], rdi
0x14002c872  mov     eax, edi
0x14002c874  mov     [rsp+148h+Entry], rax
0x14002c879  mov     [r11-78h], rax
0x14002c87d  xorps   xmm0, xmm0
0x14002c880  movups  xmmword ptr [r11-40h], xmm0
0x14002c885  mov     [r11-30h], rax
0x14002c889  mov     [r11+20h], edi
0x14002c88d  mov     rcx, rdx
0x14002c890  call    cs:__imp_IoIrpHasFsTrackOffsetExtensionType
0x14002c897  nop     dword ptr [rax+rax+00h]
0x14002c89c  test    al, al
0x14002c89e  jz      short loc_14002C8AF
0x14002c8a0  mov     rcx, r13
0x14002c8a3  call    cs:__imp_IoClearFsTrackOffsetState
0x14002c8aa  nop     dword ptr [rax+rax+00h]
0x14002c8af  mov     r12, [r13+0B8h]
0x14002c8b6  mov     [rsp+148h+var_80], r12
0x14002c8be  mov     r8, [r12+30h]
0x14002c8c3  mov     [rsp+148h+var_90], r8
0x14002c8cb  mov     r14, [r8+18h]
0x14002c8cf  test    r14, r14
0x14002c8d2  jz      short loc_14002C933
0x14002c8d4  mov     rbx, [r8+20h]
0x14002c8d8  mov     [rsp+148h+var_C0], rbx
0x14002c8e0  mov     r11, [r14+0C0h]
0x14002c8e7  mov     [rsp+148h+var_A0], r11
0x14002c8ef  mov     eax, [r11+4]
0x14002c8f3  test    al, 1
0x14002c8f5  jnz     short loc_14002C912
0x14002c8f7  test    rbx, rbx
0x14002c8fa  jz      loc_14002E7DF
0x14002c900  cmp     byte ptr [rbx+58h], 4
0x14002c904  jnz     loc_14002E7DF
0x14002c90a  test    al, 2
0x14002c90c  jz      loc_14002E7DF
0x14002c912  mov     r9, [r14+0B8h]
0x14002c919  mov     [rsp+148h+var_98], r9
0x14002c921  test    rbx, rbx
0x14002c924  jnz     short loc_14002C92D
0x14002c926  mov     edx, 5
0x14002c92b  jmp     short loc_14002C959
0x14002c92d  movzx   edx, byte ptr [rbx+58h]
0x14002c931  jmp     short loc_14002C959
0x14002c933  mov     r11, rdi
0x14002c936  mov     [rsp+148h+var_A0], rdi
0x14002c93e  mov     rbx, rdi
0x14002c941  mov     [rsp+148h+var_C0], rbx
0x14002c949  mov     r9, rdi
0x14002c94c  mov     [rsp+148h+var_98], rdi
0x14002c954  mov     edx, 1
0x14002c959  mov     [rsp+148h+var_D4], edx
0x14002c95d  mov     eax, [r14+200h]
0x14002c964  bt      eax, 18h
0x14002c968  jnb     short loc_14002C9CB
0x14002c96a  movzx   eax, cs:NtfsStatusDebugFlags
0x14002c971  test    al, al
0x14002c973  jz      short loc_14002C988
0x14002c975  mov     edx, 0C0000008h
0x14002c97a  mov     r8d, 1C00C9h
0x14002c980  mov     rcx, rsi
0x14002c983  call    NtfsStatusTraceAndDebugInternal
0x14002c988  test    r13, r13
0x14002c98b  setnz   r9b
0x14002c98f  mov     dword ptr [rsp+148h+PostIrpRoutine], edi
0x14002c993  mov     r8d, 0C0000008h
0x14002c999  mov     rdx, r13
0x14002c99c  mov     rcx, rsi
0x14002c99f  call    NtfsExtendedCompleteRequestInternal
0x14002c9a4  movzx   ecx, cs:NtfsStatusDebugFlags
0x14002c9ab  test    cl, cl
0x14002c9ad  jz      short loc_14002C9C1
0x14002c9af  mov     edx, 0C0000008h
0x14002c9b4  xor     ecx, ecx
0x14002c9b6  mov     r8d, 1C0416h
0x14002c9bc  call    NtfsStatusTraceAndDebugInternal
0x14002c9c1  mov     eax, 0C0000008h
0x14002c9c6  jmp     loc_14002EBF6
0x14002c9cb  mov     eax, [r11+4]
0x14002c9cf  test    al, 1
0x14002c9d1  jnz     short loc_14002CA33
0x14002c9d3  cmp     edx, 4
0x14002c9d6  jz      short loc_14002CA33
0x14002c9d8  movzx   eax, cs:NtfsStatusDebugFlags
0x14002c9df  mov     ebx, 0C000026Eh
0x14002c9e4  test    al, al
0x14002c9e6  jz      short loc_14002C9F8
0x14002c9e8  mov     r8d, 1C00C9h
0x14002c9ee  mov     edx, ebx
0x14002c9f0  mov     rcx, rsi
0x14002c9f3  call    NtfsStatusTraceAndDebugInternal
0x14002c9f8  test    r13, r13
0x14002c9fb  setnz   r9b
0x14002c9ff  mov     dword ptr [rsp+148h+PostIrpRoutine], edi
0x14002ca03  mov     r8d, ebx
0x14002ca06  mov     rdx, r13
0x14002ca09  mov     rcx, rsi
0x14002ca0c  call    NtfsExtendedCompleteRequestInternal
0x14002ca11  movzx   eax, cs:NtfsStatusDebugFlags
0x14002ca18  test    al, al
0x14002ca1a  jz      short loc_14002CA2B
0x14002ca1c  mov     r8d, 1C0423h
0x14002ca22  mov     edx, ebx
0x14002ca24  xor     ecx, ecx
0x14002ca26  call    NtfsStatusTraceAndDebugInternal
0x14002ca2b  mov     eax, ebx
0x14002ca2d  jmp     loc_14002EBF6
0x14002ca33  mov     eax, [rsi+0Ch]
0x14002ca36  mov     [rsp+148h+var_F8], eax
0x14002ca3a  mov     eax, [r13+10h]
0x14002ca3e  mov     edx, eax
0x14002ca40  and     edx, 2
0x14002ca43  mov     [rsp+148h+var_100], edx
0x14002ca47  setnz   dil
0x14002ca4b  and     al, 1
0x14002ca4d  mov     [rsp+148h+var_F4], eax
0x14002ca51  mov     eax, [r8+50h]
0x14002ca55  mov     [rsp+148h+var_D8], eax
0x14002ca59  jz      short loc_14002CACD
0x14002ca5b  test    dword ptr [r14+0C8h], 1000000h
0x14002ca66  jz      short loc_14002CACD
0x14002ca68  movzx   eax, cs:NtfsStatusDebugFlags
0x14002ca6f  test    al, al
0x14002ca71  jz      short loc_14002CA86
0x14002ca73  mov     edx, 0C0000810h
0x14002ca78  mov     r8d, 1C00C9h
0x14002ca7e  mov     rcx, rsi
0x14002ca81  call    NtfsStatusTraceAndDebugInternal
0x14002ca86  test    r13, r13
0x14002ca89  setnz   r9b
0x14002ca8d  mov     dword ptr [rsp+148h+PostIrpRoutine], 0
0x14002ca95  mov     r8d, 0C0000810h
0x14002ca9b  mov     rdx, r13
0x14002ca9e  mov     rcx, rsi
0x14002caa1  call    NtfsExtendedCompleteRequestInternal
0x14002caa6  movzx   ecx, cs:NtfsStatusDebugFlags
0x14002caad  test    cl, cl
0x14002caaf  jz      short loc_14002CAC3
0x14002cab1  mov     edx, 0C0000810h
0x14002cab6  xor     ecx, ecx
0x14002cab8  mov     r8d, 1C043Ah
0x14002cabe  call    NtfsStatusTraceAndDebugInternal
0x14002cac3  mov     eax, 0C0000810h
0x14002cac8  jmp     loc_14002EBF6
0x14002cacd  test    rbx, rbx
0x14002cad0  jz      short loc_14002CB36
0x14002cad2  test    dword ptr [rbx+4], 2000h
0x14002cad9  jz      short loc_14002CB36
0x14002cadb  test    edx, edx
0x14002cadd  jnz     short loc_14002CB36
0x14002cadf  movzx   eax, cs:NtfsStatusDebugFlags
0x14002cae6  mov     ebx, 0C000000Dh
0x14002caeb  test    al, al
0x14002caed  jz      short loc_14002CAFF
0x14002caef  mov     r8d, 1C00C9h
0x14002caf5  mov     edx, ebx
0x14002caf7  mov     rcx, rsi
0x14002cafa  call    NtfsStatusTraceAndDebugInternal
0x14002caff  test    r13, r13
0x14002cb02  setnz   r9b
0x14002cb06  mov     dword ptr [rsp+148h+PostIrpRoutine], 0
0x14002cb0e  mov     r8d, ebx
0x14002cb11  mov     rdx, r13
0x14002cb14  mov     rcx, rsi
0x14002cb17  call    NtfsExtendedCompleteRequestInternal
0x14002cb1c  movzx   eax, cs:NtfsStatusDebugFlags
0x14002cb23  test    al, al
0x14002cb25  jz      loc_14002CA2B
0x14002cb2b  mov     r8d, 1C0446h
0x14002cb31  jmp     loc_14002CA22
0x14002cb36  mov     rax, [r14+0C0h]
0x14002cb3d  test    dword ptr [rax+18h], 40000h
0x14002cb44  jz      loc_14002CBF6
0x14002cb4a  mov     rax, [r14+0B8h]
0x14002cb51  test    dword ptr [rax+4], 100h
0x14002cb58  jnz     loc_14002CBF6
0x14002cb5e  mov     eax, [r14+200h]
0x14002cb65  test    al, 20h
0x14002cb67  jnz     loc_14002CBF6
0x14002cb6d  mov     ecx, 0C0FFh
0x14002cb72  test    [r14+1CCh], cx
0x14002cb7a  jnz     short loc_14002CB87
0x14002cb7c  mov     eax, [r14+0C8h]
0x14002cb83  test    al, 8
0x14002cb85  jz      short loc_14002CBF6
0x14002cb87  cmp     dword ptr [r14+100h], 80h
0x14002cb92  jnz     short loc_14002CBF6
0x14002cb94  cmp     dword ptr [r14+1C0h], 0
0x14002cb9c  jnz     short loc_14002CBF6
0x14002cb9e  movzx   eax, cs:NtfsStatusDebugFlags
0x14002cba5  test    al, al
0x14002cba7  jz      short loc_14002CBBC
0x14002cba9  mov     edx, 0C000049Ah
0x14002cbae  mov     r8d, 1C0464h
0x14002cbb4  mov     rcx, rsi
0x14002cbb7  call    NtfsStatusTraceAndDebugInternal
0x14002cbbc  test    r13, r13
0x14002cbbf  setnz   r9b
0x14002cbc3  mov     dword ptr [rsp+148h+PostIrpRoutine], 0
0x14002cbcb  mov     r8d, 0C000049Ah
0x14002cbd1  mov     rdx, r13
0x14002cbd4  mov     rcx, rsi
0x14002cbd7  call    NtfsExtendedCompleteRequestInternal
0x14002cbdc  movzx   eax, cs:NtfsStatusDebugFlags
0x14002cbe3  test    al, al
0x14002cbe5  jz      loc_14002D0BD
0x14002cbeb  mov     r8d, 1C0465h
0x14002cbf1  jmp     loc_14002D0B1
0x14002cbf6  mov     eax, [r14+0C8h]
0x14002cbfd  bt      eax, 11h
0x14002cc01  jnb     loc_14002CC8A
0x14002cc07  test    edx, edx
0x14002cc09  jz      short loc_14002CC85
0x14002cc0b  mov     eax, [rsi+10h]
0x14002cc0e  bt      rax, 14h
0x14002cc13  jb      short loc_14002CC2D
0x14002cc15  test    byte ptr cs:Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits, 8
0x14002cc1c  jz      short loc_14002CC2D
0x14002cc1e  mov     r8, r14
0x14002cc21  lea     rdx, read_c1161
0x14002cc28  call    McTemplateU0p_EtwWriteTransfer
0x14002cc2d  movzx   eax, cs:NtfsStatusDebugFlags
0x14002cc34  test    al, al
0x14002cc36  jz      short loc_14002CC4B
0x14002cc38  mov     edx, 0C000049Ah
0x14002cc3d  mov     r8d, 1C048Fh
0x14002cc43  mov     rcx, rsi
0x14002cc46  call    NtfsStatusTraceAndDebugInternal
0x14002cc4b  test    r13, r13
0x14002cc4e  setnz   r9b
0x14002cc52  mov     dword ptr [rsp+148h+PostIrpRoutine], 0
0x14002cc5a  mov     r8d, 0C000049Ah
0x14002cc60  mov     rdx, r13
0x14002cc63  mov     rcx, rsi
0x14002cc66  call    NtfsExtendedCompleteRequestInternal
0x14002cc6b  movzx   eax, cs:NtfsStatusDebugFlags
0x14002cc72  test    al, al
0x14002cc74  jz      loc_14002D0BD
0x14002cc7a  mov     r8d, 1C0490h
0x14002cc80  jmp     loc_14002D0B1
0x14002cc85  mov     byte ptr [rsp+148h+var_F4], 0
0x14002cc8a  mov     r8b, 1
0x14002cc8d  xor     edx, edx
0x14002cc8f  mov     rcx, r9
0x14002cc92  call    InternalNtfsUpdateFileTimestampsFromNonpagedFcb
0x14002cc97  mov     r10, [r12+18h]
0x14002cc9c  mov     qword ptr [rsp+148h+var_E8], r10
0x14002cca1  mov     r12d, [r12+8]
0x14002cca6  mov     [rsp+148h+var_D0], r12
0x14002ccab  cmp     byte ptr [rsp+148h+var_F4], 0
0x14002ccb0  jz      short loc_14002CCDC
0x14002ccb2  mov     ecx, r12d
0x14002ccb5  or      ecx, r10d
0x14002ccb8  mov     eax, [r11+16Ch]
0x14002ccbf  dec     eax
0x14002ccc1  test    eax, ecx
0x14002ccc3  movzx   eax, [rsp+148h+arg_19]
0x14002cccb  mov     ecx, 4
0x14002ccd0  cmovnz  eax, ecx
0x14002ccd3  mov     [rsp+148h+arg_19], al
0x14002ccda  jmp     short loc_14002CCE4
0x14002ccdc  movzx   eax, [rsp+148h+arg_19]
0x14002cce4  mov     [rsp+148h+var_108], eax
0x14002cce8  test    rbx, rbx
0x14002cceb  jz      short loc_14002CD02
0x14002cced  mov     eax, [rbx+8]
0x14002ccf0  test    al, al
0x14002ccf2  jns     short loc_14002CD02
0x14002ccf4  or      qword ptr [rsi+10h], 40h
0x14002ccf9  mov     eax, [rbx+78h]
0x14002ccfc  mov     [rsi+1CCh], eax
0x14002cd02  mov     rbx, r12
0x14002cd05  mov     [rsp+148h+var_88], rbx
0x14002cd0d  mov     rax, 7FFFFFFFFFFFFFFFh
0x14002cd17  sub     rax, r10
0x14002cd1a  cmp     rax, r12
0x14002cd1d  jge     short loc_14002CD76
0x14002cd1f  movzx   eax, cs:NtfsStatusDebugFlags
0x14002cd26  mov     ebx, 0C000000Dh
0x14002cd2b  test    al, al
0x14002cd2d  jz      short loc_14002CD3F
0x14002cd2f  mov     r8d, 1C00C9h
0x14002cd35  mov     edx, ebx
0x14002cd37  mov     rcx, rsi
0x14002cd3a  call    NtfsStatusTraceAndDebugInternal
0x14002cd3f  test    r13, r13
  ... truncated ...
```
