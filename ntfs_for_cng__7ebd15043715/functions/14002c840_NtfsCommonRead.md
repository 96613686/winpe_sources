# NtfsCommonRead

- ea: `0x14002c840`
- end: `0x14002ec13`
- name: `NtfsCommonRead`
- size: `9171`
- prototype: `__int64 __fastcall(__int64, IRP *, _OWORD *)`
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
- `0x140159768`
- `0x140163f78`
- `0x14017517c`
- `0x140175a80`
- `0x140188ee0`
- `0x1401be398`
- `0x1401be91c`
- `0x1401c00e0`
- `0x1401c0b50`
- `0x1401d1f5c`
- `0x1401eb008`
- `0x140218840`
- `0x14022eed4`
- `0x140245ba8`
- `0x14024f868`
- `0x140285a00`

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
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14005b434`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14002e6b6`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14005b434`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002d96f`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002df3c`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002e0fb`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002e2c2`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002e6f8`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002e74c`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005b471`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005b4c4`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002d96f`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002df3c`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002e0fb`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002e2c2`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002e6f8`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002e74c`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005b471`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005b4c4`
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
__int64 __fastcall NtfsCommonRead(__int64 a1, IRP *a2, _OWORD *a3)
{
  IRP *v4; // r13
  __int64 v6; // rcx
  struct _IO_STACK_LOCATION *CurrentStackLocation; // r12
  struct _FILE_OBJECT *FileObject; // r8
  __int64 FsContext; // r14
  __int64 FsContext2; // rbx
  __int64 v11; // r11
  int v12; // eax
  __int64 v13; // r9
  int v14; // edx
  int Status; // ebx
  unsigned int v17; // r8d
  ULONG Flags; // eax
  int v19; // edx
  char v20; // di
  unsigned int v21; // r8d
  __int64 v22; // r11
  LARGE_INTEGER ByteOffset; // r10
  __int64 Length; // r12
  char v25; // al
  __int64 v26; // rbx
  int v27; // eax
  __int64 v28; // rax
  signed int v29; // eax
  __int64 v30; // rcx
  __int64 v31; // r9
  LARGE_INTEGER PerformanceCounter; // rax
  int v33; // r8d
  char v34; // al
  char v35; // r15
  __int64 v36; // rdx
  __int64 v37; // r8
  unsigned int v38; // eax
  __int64 v39; // rax
  __int64 v40; // rdx
  char v41; // r15
  struct _ERESOURCE *v42; // rcx
  PIRP TopLevelIrp; // rax
  char v44; // r15
  bool v45; // di
  char v46; // dl
  bool v47; // bl
  IO_PRIORITY_HINT IoPriorityHint; // eax
  bool v49; // r12
  __int64 v50; // rax
  __int64 *v51; // r9
  unsigned __int8 v52; // al
  int v53; // edx
  __int64 v54; // rcx
  __int64 v55; // rax
  char v56; // al
  unsigned __int8 v57; // bl
  signed int v58; // eax
  int v59; // ebx
  __int64 v60; // rax
  __int64 v61; // rcx
  __int64 v62; // r8
  __int64 v63; // r8
  signed int v64; // ebx
  unsigned int v65; // eax
  __int64 v66; // rax
  __int64 v67; // rcx
  int v68; // eax
  FILE_LOCK *v69; // rcx
  unsigned int v70; // r8d
  __int64 v71; // rcx
  PVOID v72; // r12
  char v73; // di
  int v74; // eax
  ULONG v75; // edx
  ULONG_PTR Information; // rcx
  __int64 v77; // rax
  __int64 v78; // r12
  __int64 v79; // rdi
  __int64 v80; // rbx
  int v81; // r8d
  PIRP v82; // rax
  __int64 v83; // rcx
  __int64 v84; // rax
  __int64 v85; // rbx
  int v86; // eax
  struct _ERESOURCE *v87; // rcx
  unsigned int v88; // edi
  char v89; // al
  __int64 v90; // rax
  __int64 v91; // rbx
  struct _ERESOURCE *v92; // rcx
  unsigned int v93; // r12d
  struct _ERESOURCE *v94; // rcx
  signed __int64 v95; // rbx
  unsigned int v96; // ebx
  int v97; // ecx
  unsigned int v98; // ebx
  int v99; // eax
  unsigned int v100; // r8d
  bool v101; // zf
  int v102; // eax
  NTSTATUS v103; // eax
  ULONG_PTR v104; // rdx
  struct _IO_STACK_LOCATION *v105; // rcx
  __int64 v106; // r13
  char v107; // al
  void *v108; // rdi
  struct _ERESOURCE *v109; // rcx
  POPLOCK_FS_PREPOST_IRP PostIrpRoutine; // [rsp+20h] [rbp-128h]
  char v111; // [rsp+40h] [rbp-108h]
  unsigned int v112; // [rsp+44h] [rbp-104h]
  int v113; // [rsp+48h] [rbp-100h]
  int v114; // [rsp+50h] [rbp-F8h]
  char v115; // [rsp+50h] [rbp-F8h]
  ULONG v116; // [rsp+54h] [rbp-F4h]
  int v117[2]; // [rsp+60h] [rbp-E8h] BYREF
  PVOID Entry; // [rsp+68h] [rbp-E0h]
  ULONG v119; // [rsp+70h] [rbp-D8h]
  int v120; // [rsp+74h] [rbp-D4h]
  __int64 v121; // [rsp+78h] [rbp-D0h]
  __int64 v122; // [rsp+80h] [rbp-C8h]
  __int64 v123; // [rsp+88h] [rbp-C0h]
  char v124; // [rsp+90h] [rbp-B8h]
  int v125; // [rsp+94h] [rbp-B4h]
  IRP *v126; // [rsp+98h] [rbp-B0h]
  unsigned int v127; // [rsp+A0h] [rbp-A8h]
  __int64 v128; // [rsp+A8h] [rbp-A0h]
  __int64 v129; // [rsp+B0h] [rbp-98h]
  struct _FILE_OBJECT *v130; // [rsp+B8h] [rbp-90h]
  __int64 v131; // [rsp+C0h] [rbp-88h]
  struct _IO_STACK_LOCATION *v132; // [rsp+C8h] [rbp-80h]
  void *v133; // [rsp+D0h] [rbp-78h] BYREF
  _DWORD *v134; // [rsp+D8h] [rbp-70h]
  __int64 v135; // [rsp+E0h] [rbp-68h]
  __int64 v136; // [rsp+E8h] [rbp-60h]
  int v137; // [rsp+F0h] [rbp-58h]
  __int64 v138; // [rsp+F8h] [rbp-50h]
  __int64 v139; // [rsp+100h] [rbp-48h]
  __int128 v140; // [rsp+108h] [rbp-40h] BYREF
  __int64 v141; // [rsp+118h] [rbp-30h]
  __int64 v142; // [rsp+158h] [rbp+10h] BYREF
  int v143; // [rsp+168h] [rbp+20h] BYREF

  v4 = a2;
  v126 = a2;
  *(_QWORD *)v117 = 0;
  Entry = 0;
  v133 = 0;
  v140 = 0;
  v141 = 0;
  v143 = 0;
  if ( (unsigned __int8)IoIrpHasFsTrackOffsetExtensionType(a2) )
    IoClearFsTrackOffsetState(v4);
  CurrentStackLocation = v4->Tail.Overlay.CurrentStackLocation;
  v132 = CurrentStackLocation;
  FileObject = CurrentStackLocation->FileObject;
  v130 = FileObject;
  FsContext = (__int64)FileObject->FsContext;
  if ( FsContext )
  {
    FsContext2 = (__int64)FileObject->FsContext2;
    v123 = FsContext2;
    v11 = *(_QWORD *)(FsContext + 192);
    v128 = v11;
    v12 = *(_DWORD *)(v11 + 4);
    if ( (v12 & 1) == 0 && (!FsContext2 || *(_BYTE *)(FsContext2 + 88) != 4 || (v12 & 2) == 0) )
      NtfsRaiseStatusInternal(a1, -1073741202, 0, 0, 0);
    v13 = *(_QWORD *)(FsContext + 184);
    v129 = v13;
    if ( FsContext2 )
      v14 = *(unsigned __int8 *)(FsContext2 + 88);
    else
      v14 = 5;
  }
  else
  {
    v11 = 0;
    v128 = 0;
    FsContext2 = 0;
    v123 = 0;
    v13 = 0;
    v129 = 0;
    v14 = 1;
  }
  v120 = v14;
  if ( (*(_DWORD *)(FsContext + 512) & 0x1000000) != 0 )
  {
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(a1, 0xC0000008, 0x1C00C9u);
    NtfsExtendedCompleteRequestInternal(a1, v4, -1073741816, v4 != 0, 0);
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(0, 0xC0000008, 0x1C0416u);
    return 3221225480LL;
  }
  if ( (*(_DWORD *)(v11 + 4) & 1) == 0 && v14 != 4 )
  {
    Status = -1073741202;
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(a1, 0xC000026E, 0x1C00C9u);
    NtfsExtendedCompleteRequestInternal(a1, v4, -1073741202, v4 != 0, 0);
    if ( !NtfsStatusDebugFlags )
      return (unsigned int)Status;
    v17 = 1836067;
    goto LABEL_24;
  }
  v114 = *(_DWORD *)(a1 + 12);
  Flags = v4->Flags;
  v19 = Flags & 2;
  v113 = v19;
  v20 = v19 != 0;
  LOBYTE(Flags) = Flags & 1;
  v116 = Flags;
  v119 = FileObject->Flags;
  if ( !(_BYTE)Flags || (*(_DWORD *)(FsContext + 200) & 0x1000000) == 0 )
  {
    if ( FsContext2 && (*(_DWORD *)(FsContext2 + 4) & 0x2000) != 0 && !v19 )
    {
      Status = -1073741811;
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(a1, 0xC000000D, 0x1C00C9u);
      NtfsExtendedCompleteRequestInternal(a1, v4, -1073741811, v4 != 0, 0);
      if ( !NtfsStatusDebugFlags )
        return (unsigned int)Status;
      v17 = 1836102;
      goto LABEL_24;
    }
    if ( (*(_DWORD *)(*(_QWORD *)(FsContext + 192) + 24LL) & 0x40000) != 0
      && (*(_DWORD *)(*(_QWORD *)(FsContext + 184) + 4LL) & 0x100) == 0
      && (*(_DWORD *)(FsContext + 512) & 0x20) == 0 )
    {
      v6 = 49407;
      if ( ((*(_WORD *)(FsContext + 460) & 0xC0FF) != 0 || (*(_DWORD *)(FsContext + 200) & 8) != 0)
        && *(_DWORD *)(FsContext + 256) == 128
        && !*(_DWORD *)(FsContext + 448) )
      {
        if ( NtfsStatusDebugFlags )
          NtfsStatusTraceAndDebugInternal(a1, 0xC000049A, 0x1C0464u);
        NtfsExtendedCompleteRequestInternal(a1, v4, -1073740646, v4 != 0, 0);
        if ( !NtfsStatusDebugFlags )
          return 3221226650LL;
        v21 = 1836133;
LABEL_121:
        NtfsStatusTraceAndDebugInternal(0, 0xC000049A, v21);
        return 3221226650LL;
      }
    }
    if ( (*(_DWORD *)(FsContext + 200) & 0x20000) != 0 )
    {
      if ( v19 )
      {
        if ( (*(_DWORD *)(a1 + 16) & 0x100000) == 0
          && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 8) != 0 )
        {
          McTemplateU0p_EtwWriteTransfer(v6, read_c1161, FsContext);
        }
        if ( NtfsStatusDebugFlags )
          NtfsStatusTraceAndDebugInternal(a1, 0xC000049A, 0x1C048Fu);
        NtfsExtendedCompleteRequestInternal(a1, v4, -1073740646, v4 != 0, 0);
        if ( !NtfsStatusDebugFlags )
          return 3221226650LL;
        v21 = 1836176;
        goto LABEL_121;
      }
      LOBYTE(v116) = 0;
    }
    LOBYTE(FileObject) = 1;
    InternalNtfsUpdateFileTimestampsFromNonpagedFcb(v13, 0, FileObject);
    ByteOffset = CurrentStackLocation->Parameters.Read.ByteOffset;
    *(LARGE_INTEGER *)v117 = ByteOffset;
    Length = CurrentStackLocation->Parameters.Read.Length;
    v121 = Length;
    if ( (_BYTE)v116 )
    {
      v25 = BYTE1(v143);
      if ( ((ByteOffset.LowPart | (unsigned int)Length) & (*(_DWORD *)(v22 + 364) - 1)) != 0 )
        v25 = 4;
      BYTE1(v143) = v25;
    }
    else
    {
      v25 = BYTE1(v143);
    }
    v111 = v25;
    if ( FsContext2 && (*(_DWORD *)(FsContext2 + 8) & 0x80u) != 0 )
    {
      *(_QWORD *)(a1 + 16) |= 0x40uLL;
      *(_DWORD *)(a1 + 460) = *(_DWORD *)(FsContext2 + 120);
    }
    v26 = Length;
    v131 = Length;
    if ( 0x7FFFFFFFFFFFFFFFLL - ByteOffset.QuadPart < Length )
    {
      Status = -1073741811;
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(a1, 0xC000000D, 0x1C00C9u);
      NtfsExtendedCompleteRequestInternal(a1, v4, -1073741811, v4 != 0, 0);
      if ( !NtfsStatusDebugFlags )
        return (unsigned int)Status;
      v17 = 1836254;
LABEL_24:
      NtfsStatusTraceAndDebugInternal(0, Status, v17);
      return (unsigned int)Status;
    }
    v122 = Length + ByteOffset.QuadPart;
    if ( !(_DWORD)Length )
    {
      *(_QWORD *)(a1 + 496) = 17;
      NtfsExtendedCompleteRequestInternal(a1, v4, 0, v4 != 0, 1);
      return 0;
    }
    v115 = v114 & 1;
    if ( !v115
      && v113
      && ((*(_DWORD *)(FsContext + 512) & 8) != 0
       || (v27 = *(_DWORD *)(FsContext + 200), (v27 & 0x20000) != 0)
       || *(_DWORD *)(FsContext + 452)
       || *(_QWORD *)(FsContext + 504) && v27 >= 0
       || (*(_DWORD *)(*(_QWORD *)(a1 + 144) + 12LL) & 0x40) != 0)
      || (*(_DWORD *)(FsContext + 200) & 0x20) == 0 )
    {
      v115 = 1;
      *(_DWORD *)(a1 + 12) |= 1u;
    }
    v28 = *(_QWORD *)(FsContext + 528);
    if ( v28 && *(_DWORD *)(v28 + 4) == 128 )
    {
      v29 = NtfsDetermineTransactionType(a1, (_DWORD)v130, FsContext, v123, v20, (__int64)&v133, (__int64)&v143);
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
          NtfsStatusTraceAndDebugInternal(a1, v29, 0x1C00C9u);
        }
        goto LABEL_96;
      }
      Entry = v133;
      v111 = BYTE1(v143);
      v26 = Length;
    }
    v119 &= 2u;
    NtfsInitializeIoContext(a1, a3, v20);
    v30 = *(_QWORD *)(a1 + 208);
    v134 = (_DWORD *)v30;
    v31 = v128;
    if ( *(_BYTE *)(v128 + 10496) )
    {
      PerformanceCounter = *(LARGE_INTEGER *)(a1 + 496);
      if ( PerformanceCounter.QuadPart <= 23 )
      {
        PerformanceCounter = KeQueryPerformanceCounter(0);
        v31 = v128;
      }
      *(LARGE_INTEGER *)(*(_QWORD *)(a1 + 208) + 80LL) = PerformanceCounter;
      LODWORD(v142) = 0;
      v33 = v113;
      if ( v113 || (_BYTE)v116 )
        v34 = 0;
      else
        v34 = 2;
      v35 = v115;
      BYTE3(v142) = v115 | v34 | (4 * (v20 | 4));
      **(_DWORD **)(a1 + 208) |= v142;
      v30 = (__int64)v134;
    }
    else
    {
      v35 = v115;
      v33 = v113;
    }
    if ( v120 == 4 )
    {
      if ( (*(_DWORD *)(v31 + 4) & 2) != 0 || (*(_DWORD *)(v31 + 24) & 0x40000) == 0 )
      {
        v36 = *(_QWORD *)v117;
      }
      else
      {
        v36 = *(_QWORD *)v117;
        if ( *(_QWORD *)v117 )
        {
          if ( *(_QWORD *)v117 != *(_QWORD *)(v31 + 424) * *(unsigned int *)(v31 + 364) )
          {
            v37 = 3LL << *(_BYTE *)(v31 + 492);
            if ( *(_QWORD *)v117 != v37 + (*(_QWORD *)(v31 + 408) << *(_BYTE *)(v31 + 488))
              && *(_QWORD *)v117 != v37 + (*(_QWORD *)(v31 + 416) << *(_BYTE *)(v31 + 488)) )
            {
              goto LABEL_117;
            }
          }
        }
        v38 = *(_DWORD *)(v31 + 360);
        if ( v38 <= *(_DWORD *)(v31 + 364) )
          v38 = *(_DWORD *)(v31 + 364);
        if ( (unsigned int)Length > v38 )
        {
LABEL_117:
          if ( NtfsStatusDebugFlags )
            NtfsStatusTraceAndDebugInternal(a1, 0xC000049A, 0x1C0588u);
          NtfsExtendedCompleteRequestInternal(a1, v4, -1073740646, v4 != 0, 0);
          if ( !NtfsStatusDebugFlags )
            return 3221226650LL;
          v21 = 1836425;
          goto LABEL_121;
        }
      }
      if ( (*(_DWORD *)(v123 + 4) & 0x100) == 0 )
      {
        v39 = *(_QWORD *)(FsContext + 32);
        if ( v39 <= v36 )
        {
          NtfsExtendedCompleteRequestInternal(a1, v4, -1073741807, v4 != 0, 0);
          return 3221225489LL;
        }
        if ( v39 < v122 )
          LODWORD(Length) = v39 - v36;
      }
      if ( !v35 )
      {
        NtfsSetIoContextAsync(a1, FsContext, Length, v123, 0, 0);
        v36 = *(_QWORD *)v117;
      }
      Status = NtfsVolumeDasdIo(a1, v36, Length);
      if ( Status >= 0 )
        NtfsUpdateFileTimestampsForAccess(v130, v129, v123);
      if ( v119 && !v113 && Status >= 0 )
        v132->FileObject->CurrentByteOffset.QuadPart = v4->IoStatus.Information + *(_QWORD *)v117;
      if ( !v35 )
        return (unsigned int)Status;
      if ( NtfsStatusDebugFlags
        && Status
        && Status != 294
        && (unsigned int)(Status - 298) > 1
        && (unsigned int)Status < 0xFFFFFFED
        && Status != -1073741802
        && (unsigned int)(Status + 2147483643) > 1
        && Status != -1073741807
        && Status != 259
        && Status != -1073741608 )
      {
        NtfsStatusTraceAndDebugInternal(a1, Status, 0x1C00C9u);
      }
LABEL_96:
      NtfsExtendedCompleteRequestInternal(a1, v4, Status, v4 != 0, Status >= 0);
      return (unsigned int)Status;
    }
    v136 = FsContext;
    v112 = Length;
    v139 = v30;
    if ( v33 )
    {
      v30 = *(_QWORD *)(v31 + 808) + 704LL * (HIDWORD(KeGetPcr()[1].LockArray) % NtfsNumberProcessors);
      v40 = v129;
      if ( (*(_DWORD *)(v129 + 4) & 0x100) != 0 )
      {
        if ( FsContext == *(_QWORD *)(v31 + 64) )
        {
          ++*(_QWORD *)(v30 + 416);
          *(_QWORD *)(v30 + 424) += v26;
        }
        else
        {
          ++*(_QWORD *)(v30 + 56);
          *(_QWORD *)(v30 + 64) += v26;
        }
        if ( FsContext == *(_QWORD *)(v31 + 48) )
        {
          ++*(_QWORD *)(v30 + 112);
          *(_QWORD *)(v30 + 120) += v26;
        }
        else if ( FsContext == *(_QWORD *)(v31 + 32) )
        {
          ++*(_QWORD *)(v30 + 224);
          *(_QWORD *)(v30 + 232) += v26;
        }
        else if ( FsContext == *(_QWORD *)(v31 + 72) )
        {
          ++*(_QWORD *)(v30 + 256);
          *(_QWORD *)(v30 + 264) += v26;
        }
        else if ( FsContext == *(_QWORD *)(v31 + 208) )
        {
          ++*(_QWORD *)(v30 + 320);
          *(_QWORD *)(v30 + 328) += v26;
        }
      }
      else if ( *(_DWORD *)(FsContext + 256) == 128 )
      {
        ++*(_QWORD *)(v30 + 8);
        *(_QWORD *)(v30 + 16) += v26;
      }
      else
      {
        ++*(_QWORD *)(v30 + 384);
        *(_QWORD *)(v30 + 392) += v26;
      }
    }
    else
    {
      v40 = v129;
    }
    if ( v33 || !(_BYTE)v116 )
      *(_DWORD *)(FsContext + 224) = 0;
    if ( (_BYTE)v116 && *(_DWORD *)(v40 + 8) <= 3u )
    {
      if ( a1 == *(_QWORD *)(a1 + 144) )
      {
        if ( NtfsStatusDebugFlags )
          NtfsStatusTraceAndDebugInternal(a1, 0xC0000010, 0x1C07EDu);
        NtfsRaiseStatusInternal(a1, -1073741808, 0, 0, 1837037);
      }
      v41 = v143;
      goto LABEL_174;
    }
    TopLevelIrp = IoGetTopLevelIrp();
    if ( HIBYTE(TopLevelIrp->Type)
      && (HIDWORD(TopLevelIrp->AssociatedIrp.MasterIrp->ThreadListEntry.Flink->Flink) & 0x200) == 0 )
    {
      LOBYTE(TopLevelIrp->Type) = 0;
    }
    if ( !v113 )
    {
      v125 = 0;
      v44 = 0;
      LOBYTE(v142) = 0;
      v45 = *(_BYTE *)(FsContext + 460) || (v111 & 2) != 0;
      v46 = v116;
      v47 = !(_BYTE)v116 || v45;
      v49 = 1;
      if ( !v115 )
      {
        if ( v119
          || !(_BYTE)v116
          || (IoPriorityHint = IoGetIoPriorityHint(v4), v46 = v116, IoPriorityHint >= IoPriorityNormal) )
        {
          v49 = 0;
        }
      }
      if ( (*(_DWORD *)(a1 + 12) & 0x100) == 0
        && (!v47 || *(_QWORD *)(*(_QWORD *)(FsContext + 288) + 24LL))
        && (!v46 || !*(_QWORD *)(*(_QWORD *)(FsContext + 288) + 16LL) || *(_DWORD *)(FsContext + 544)) )
      {
        v50 = *(_QWORD *)(FsContext + 528);
        if ( (!v50 || (*(_DWORD *)(v50 + 24) & 0x1000) == 0)
          && ((!v46 || !v45) && !Entry || *(_QWORD *)(FsContext + 280)) )
        {
          if ( !v46
            || v45
            || _bittest16((const signed __int16 *)(FsContext + 460), 0xEu)
            || IoGetIoPriorityHint(v4) < IoPriorityNormal )
          {
            v51 = 0;
          }
          else
          {
            v51 = &v142;
          }
          v52 = NtfsAcquirePagingShared(a1, FsContext, v49, v51);
          v53 = v52;
          v125 = v52;
          if ( !v52
            || (!v47 || (v54 = *(_QWORD *)(*(_QWORD *)(FsContext + 288) + 24LL)) != 0)
            && ((v54 = v116, !(_BYTE)v116)
             || !*(_QWORD *)(*(_QWORD *)(FsContext + 288) + 16LL)
             || *(_DWORD *)(FsContext + 544))
            && ((v55 = *(_QWORD *)(FsContext + 528)) == 0 || (*(_DWORD *)(v55 + 24) & 0x1000) == 0)
            && ((!(_BYTE)v116 || !v45) && !Entry || *(_QWORD *)(FsContext + 280)) )
          {
            v56 = v143;
            v44 = v142;
            goto LABEL_230;
          }
          NtfsReleasePaging(v54, v134, FsContext, v142);
          LOBYTE(v142) = 0;
        }
      }
      v53 = (unsigned __int8)NtfsAcquirePagingResourceExclusive(a1, FsContext, v49);
      v56 = v143 | 4;
      LOBYTE(v143) = v143 | 4;
      v125 = v53;
LABEL_230:
      if ( !v53 )
        NtfsRaiseStatusInternal(a1, -1073741608, 0, 0, 1836694);
      v41 = v56 & 0xFC | 1 | (2 * (v44 & 1));
      LOBYTE(v143) = v41;
      if ( *(_DWORD *)(FsContext + 516) == 3 && *(_DWORD *)(FsContext + 256) == 128 )
      {
        if ( NtfsStatusDebugFlags )
          NtfsStatusTraceAndDebugInternal(a1, 0xC00004A3, 0x1C06A2u);
        NtfsRaiseStatusInternal(a1, -1073740637, 0, 0, 1836706);
      }
      if ( (unsigned __int8)*(_WORD *)(FsContext + 460) && (*(_BYTE *)(a1 + 16) & 0x40) != 0 )
      {
        if ( NtfsStatusDebugFlags )
          NtfsStatusTraceAndDebugInternal(a1, 0xC000047B, 0x1C06B1u);
        NtfsRaiseStatusInternal(a1, -1073740677, 0, 0, 1836721);
      }
      v57 = v116;
      if ( (_BYTE)v116
        && *(_QWORD *)(*(_QWORD *)(FsContext + 288) + 16LL)
        && !*(_DWORD *)(FsContext + 544)
        && !(unsigned __int8)*(_WORD *)(FsContext + 460) )
      {
        v58 = NtfsCacheCoherencyFlush(a1, v53, FsContext, v117[0], v131, 0, *(_DWORD *)(FsContext + 220) == 0);
        v59 = v58;
        if ( v58 < 0 )
        {
          if ( NtfsStatusDebugFlags
            && (unsigned int)v58 < 0xFFFFFFED
            && v58 != -1073741802
            && (unsigned int)(v58 + 2147483643) > 1
            && v58 != -1073741807
            && v58 != -1073741608 )
          {
            NtfsStatusTraceAndDebugInternal(a1, v58, 0x1C06D3u);
          }
          NtfsRaiseStatusInternal(a1, v59, 0, 0, 1836755);
        }
        v57 = v116;
      }
      v60 = *(_QWORD *)(FsContext + 528);
      if ( v60 && (*(_DWORD *)(v60 + 24) & 0x1000) != 0 )
        TxfDoPublishCommittedChangesToDefaultReaderSectionWithTryExcept(a1, FsContext, v57);
      if ( v123 && (*(_DWORD *)(v123 + 4) & 0x8000) != 0 )
      {
        if ( NtfsStatusDebugFlags )
          NtfsStatusTraceAndDebugInternal(a1, 0xC0000128, 0x1C06FEu);
        NtfsRaiseStatusInternal(a1, -1073741528, 0, 0, 1836798);
      }
      if ( (*(_DWORD *)(FsContext + 512) & 0x1000000) != 0 )
      {
        if ( NtfsStatusDebugFlags )
          NtfsStatusTraceAndDebugInternal(a1, 0xC0000008, 0x1C0706u);
        NtfsRaiseStatusInternal(a1, -1073741816, 0, 0, 1836806);
      }
      if ( !v57 || !*(_BYTE *)(FsContext + 460) && (v111 & 2) == 0 )
        goto LABEL_276;
      LOBYTE(v116) = 0;
      v124 = 0;
      *(_BYTE *)(*(_QWORD *)(a1 + 208) + 3LL) |= 2u;
      if ( !*(_QWORD *)(FsContext + 280) )
      {
        NtfsLockFsRtlHeader(a1, FsContext);
        NtfsCreateInternalAttributeStream(a1, FsContext, 0, 0, 0, 0);
        NtfsUnlockFsRtlHeader(a1, FsContext);
      }
      if ( (v111 & 1) == 0 )
      {
        LODWORD(Length) = v121;
        if ( (v111 & 2) == 0 )
          v130 = *(struct _FILE_OBJECT **)(FsContext + 280);
      }
      else
      {
LABEL_276:
        LODWORD(Length) = v121;
      }
      goto LABEL_277;
    }
    if ( !*(_QWORD *)(FsContext + 16)
      || ExIsResourceAcquiredSharedLite(*(PERESOURCE *)(*(_QWORD *)(FsContext + 184) + 112LL)) )
    {
      if ( *(_DWORD *)(FsContext + 516) == 3 && *(_DWORD *)(FsContext + 256) == 128 )
      {
        if ( NtfsStatusDebugFlags )
          NtfsStatusTraceAndDebugInternal(a1, 0xC00004A3, 0x1C07BFu);
        NtfsRaiseStatusInternal(a1, -1073740637, 0, 0, 1836991);
      }
      v41 = v143;
LABEL_277:
      v30 = *(unsigned int *)(FsContext + 512);
      if ( (v30 & 0x10000) != 0 )
        v64 = -1073741202;
      else
        v64 = (v30 & 0x1000000) != 0 ? 0xC0000008 : 0;
      if ( (v30 & 0x40) != 0 )
      {
        v64 = -1073741533;
        if ( NtfsStatusDebugFlags )
          NtfsStatusTraceAndDebugInternal(0, 0xC0000123, 0x1C07D7u);
      }
      else if ( v64 >= 0 )
      {
LABEL_174:
        if ( (*(_DWORD *)(FsContext + 200) & 0x20) == 0 )
        {
          if ( (v41 & 0x10) == 0 )
          {
            NtfsAcquireResourceShared(v30, FsContext, 1u);
            v41 |= 0x18u;
            LOBYTE(v143) = v41;
          }
          NtfsUpdateScbFromAttribute(a1, FsContext, 0);
          if ( (v41 & 8) != 0 )
          {
            if ( *(_WORD *)FsContext == 1794 )
              v42 = (struct _ERESOURCE *)(*(_QWORD *)(FsContext + 104) + 64LL);
            else
              v42 = *(struct _ERESOURCE **)(FsContext + 8);
            ExReleaseResourceLite(v42);
            v41 &= 0xE7u;
            LOBYTE(v143) = v41;
          }
        }
        if ( *(_DWORD *)(FsContext + 256) == 128 && (unsigned __int8)*(_WORD *)(FsContext + 460) >= 2u )
        {
          if ( NtfsStatusDebugFlags )
            NtfsStatusTraceAndDebugInternal(a1, 0xC00000BB, 0x1C080Bu);
          NtfsRaiseStatusInternal(a1, -1073741637, 0, 0, 1837067);
        }
        if ( v120 == 2 && !v113 )
        {
          if ( (v111 & 1) == 0 )
          {
            v65 = FsRtlCheckOplock(
                    (POPLOCK)(FsContext + 88),
                    v4,
                    (PVOID)a1,
                    NtfsOplockComplete,
                    (POPLOCK_FS_PREPOST_IRP)NtfsPrePostIrp);
            Status = v65;
            if ( v65 )
            {
              v4 = 0;
              v126 = 0;
              a1 = 0;
              if ( NtfsStatusDebugFlags
                && (((v65 - 294) & 0xFFFFFFFA) != 0 || v65 == 295)
                && v65 < 0xFFFFFFED
                && v65 != -1073741802
                && v65 + 2147483643 > 1
                && v65 != -1073741807
                && v65 != 259
                && v65 != -1073741608 )
              {
                NtfsStatusTraceAndDebugInternal(0, v65, 0x1C0828u);
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
                  || (v66 = *(_QWORD *)(FsContext + 584)) != 0 && *(_BYTE *)(v66 + 16)
                  || (v67 = *(_QWORD *)(FsContext + 192), (*(_DWORD *)(v67 + 4) & 0x2000000) != 0)
                  || (*(_DWORD *)(FsContext + 512) & 0x4000000) != 0
                  || *(_QWORD *)(FsContext + 528)
                  || (v68 = 1, *(_QWORD *)(v67 + 40)) )
                {
                  v68 = 2;
                }
              }
              else
              {
                v68 = 0;
              }
              v120 = v68;
              *(_BYTE *)(FsContext + 5) = v68;
            }
          }
          v69 = *(FILE_LOCK **)(FsContext + 584);
          if ( v69 )
          {
            if ( !FsRtlCheckLockForReadAccess(v69, v4) )
            {
              Status = -1073741740;
              if ( NtfsStatusDebugFlags )
              {
                v70 = 1837117;
LABEL_322:
                NtfsStatusTraceAndDebugInternal(0, Status, v70);
              }
LABEL_323:
              v71 = v112;
LABEL_324:
              v72 = Entry;
              v73 = v111;
LABEL_325:
              if ( v4 )
              {
                if ( Status >= 0 && (v73 & 1) != 0 && (v41 & 0x40) == 0 )
                {
                  TxfReadVersion(a1, (_DWORD)v4, (_DWORD)v130, (_DWORD)v72, (__int64)v117, v71, (unsigned __int8)v116);
                  Status = v4->IoStatus.Status;
                }
                v74 = v113;
                v75 = v119;
                if ( v113 || !v119 )
                {
                  v105 = v132;
                }
                else
                {
                  if ( (Status & 0xC0000000) == 0xC0000000 )
                    Information = 0;
                  else
                    Information = v4->IoStatus.Information;
                  v104 = Information + *(_QWORD *)v117;
                  v105 = v132;
                  v132->FileObject->CurrentByteOffset.QuadPart = v104;
                  v74 = 0;
                  v75 = v119;
                }
                if ( Status >= 0 && v75 && !v74 )
                  NtfsUpdateFileTimestampsForAccess(v105->FileObject, *(_QWORD *)(FsContext + 184), v123);
                NtfsCleanupTransaction(a1, Status, 0);
              }
              if ( (v73 & 1) != 0 )
                _InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)v72 + 2) + 44LL));
              if ( (v41 & 0x20) != 0 )
              {
                v106 = *((_QWORD *)v72 + 2);
                if ( v106 )
                  v106 = *(_QWORD *)(v106 + 64);
                v107 = 0;
                do
                {
                  v108 = 0;
                  if ( v106 && !v107 )
                  {
                    ExAcquireResourceExclusiveLite(*(PERESOURCE *)(v106 + 136), 1u);
                    v107 = 1;
                  }
                  _InterlockedDecrement((volatile signed __int32 *)v72 + 1);
                  if ( !*((_DWORD *)v72 + 1) )
                  {
                    v108 = (void *)*((_QWORD *)v72 + 5);
                    TxfDeleteTxfVscb(v72);
                    v107 = 0;
                  }
                  v72 = v108;
                }
                while ( v108 );
                if ( v107 && v106 )
                  ExReleaseResourceLite(*(PERESOURCE *)(v106 + 136));
                v4 = v126;
              }
              if ( (v41 & 1) != 0 )
                NtfsReleasePaging(v71, v134, FsContext, (v41 & 2) != 0);
              if ( (v41 & 0x10) != 0 )
              {
                if ( *(_WORD *)FsContext == 1794 )
                  v109 = (struct _ERESOURCE *)(*(_QWORD *)(FsContext + 104) + 64LL);
                else
                  v109 = *(struct _ERESOURCE **)(FsContext + 8);
                ExReleaseResourceLite(v109);
              }
              if ( NtfsStatusDebugFlags
                && Status
                && Status != 294
                && (unsigned int)(Status - 298) > 1
                && (unsigned int)Status < 0xFFFFFFED
                && Status != -1073741802
                && (unsigned int)(Status + 2147483643) > 1
                && Status != -1073741807
                && Status != 259
                && Status != -1073741608 )
              {
                NtfsStatusTraceAndDebugInternal(a1, Status, 0x1C00C9u);
              }
              NtfsExtendedCompleteRequestInternal(a1, v4, Status, v4 != 0, Status >= 0);
              return (unsigned int)Status;
            }
          }
        }
        if ( ((v111 & 1) != 0 || (v111 & 2) != 0) && !v115 )
        {
          v115 = 1;
          *(_DWORD *)(a1 + 12) |= 1u;
          *(_BYTE *)(*(_QWORD *)(a1 + 208) + 3LL) |= 1u;
        }
        if ( (*(_DWORD *)(FsContext + 512) & 0x10000000) != 0 )
        {
          *(_DWORD *)(a1 + 12) |= 0x10000000u;
          NtfsLockUserBuffer(a1, v4, IoWriteAccess, Length);
        }
        if ( (v111 & 1) != 0 )
        {
          FsRtlAcquireHeaderMutex(FsContext + 120, FsContext + 160);
          v77 = *((_QWORD *)Entry + 33);
          v142 = *(_QWORD *)(v77 + 8);
          v131 = v142;
          v78 = *(_QWORD *)(v77 + 16);
          v135 = v78;
          FsRtlReleaseHeaderMutex(FsContext + 120, FsContext + 160);
          v79 = v142;
        }
        else
        {
          NtfsGetScbFileSizes(FsContext, &v140, 0);
          v79 = *((_QWORD *)&v140 + 1);
          v131 = *((_QWORD *)&v140 + 1);
          v78 = v141;
          v135 = v141;
        }
        v80 = v79;
        v81 = v113;
        if ( v113 )
        {
          if ( *(_DWORD *)(FsContext + 256) == 128
            && *(_BYTE *)(FsContext + 460)
            && (*(_DWORD *)(FsContext + 200) & 8) == 0
            && (v111 & 1) == 0 )
          {
            v79 = -*(_DWORD *)(FsContext + 452) & (unsigned __int64)(*(_DWORD *)(FsContext + 452) - 1 + v79);
            v131 = v79;
            v80 = v79;
          }
          if ( (*(_DWORD *)(FsContext + 512) & 1) != 0 )
          {
            *(_QWORD *)v117 += *(_QWORD *)(v128 + 1952);
            v122 = *(_QWORD *)v117 + (unsigned int)v121;
            v138 = v122;
          }
          v82 = IoGetTopLevelIrp();
          v81 = v113;
          if ( v82->AssociatedIrp.MasterIrp == (struct _IRP *)2 )
            *(_DWORD *)(a1 + 12) |= 0x800u;
        }
        v83 = *(_QWORD *)v117;
        if ( *(__int64 *)v117 >= v80 )
        {
          *(_QWORD *)(*(_QWORD *)(a1 + 208) + 80LL) = 18;
          Status = -1073741807;
          goto LABEL_323;
        }
        if ( v122 <= v80 )
        {
          LODWORD(v85) = v121;
        }
        else
        {
          v84 = *(_QWORD *)(FsContext + 528);
          if ( v84 && (*(_DWORD *)(v84 + 24) & 0x40) != 0 && v81 )
          {
            NtfsFillIrpBuffer(a1, (__int64)v4, v122 - v80, v80 - v117[0], 0);
            v83 = *(_QWORD *)v117;
          }
          v85 = (unsigned int)(v80 - v83);
          v121 = v85;
          v127 = v85;
          v122 = v83 + (unsigned int)v85;
          v138 = v122;
          v112 = v85;
          v137 = v85;
        }
        if ( (*(_DWORD *)(FsContext + 200) & 8) != 0 || (*(_DWORD *)(FsContext + 512) & 0x4000) != 0 )
        {
          if ( !(_BYTE)v116 )
            goto LABEL_497;
          if ( (v41 & 0x10) == 0 )
          {
            NtfsAcquireResourceShared(v83, FsContext, 1u);
            v41 |= 0x18u;
            LOBYTE(v143) = v41;
          }
          if ( (*(_DWORD *)(FsContext + 200) & 8) != 0 )
          {
            if ( (v111 & 1) == 0 || *(_QWORD *)(FsContext + 32) >= v79 )
            {
              *(_QWORD *)(*(_QWORD *)(a1 + 208) + 80LL) = 15;
              v86 = v85;
              if ( (unsigned int)v85 >= (__int64)(*(_QWORD *)(FsContext + 32) - *(_QWORD *)v117) )
                v86 = *(_DWORD *)(FsContext + 32) - v117[0];
              LODWORD(PostIrpRoutine) = v86;
              NtfsNonCachedResidentRead(a1, (__int64)v4, FsContext, v117[0], (size_t)PostIrpRoutine);
            }
            Status = 0;
            goto LABEL_323;
          }
          if ( (v41 & 8) != 0 )
          {
            if ( *(_WORD *)FsContext == 1794 )
              v87 = (struct _ERESOURCE *)(*(_QWORD *)(FsContext + 104) + 64LL);
            else
              v87 = *(struct _ERESOURCE **)(FsContext + 8);
            ExReleaseResourceLite(v87);
            v41 &= 0xE7u;
            LOBYTE(v143) = v41;
          }
        }
        if ( (_BYTE)v116 )
        {
          if ( (v111 & 1) != 0 || (*(_BYTE *)(FsContext + 4) & 0x20) == 0 )
          {
            v88 = v121;
          }
          else
          {
            v88 = v121;
            if ( *(_BYTE *)(FsContext + 460) && !(unsigned __int8)NtfsReserveClusters(a1, 0) )
            {
              NtfsAllocateDiskFullContext(a1, (unsigned int)v121, 0x27B001C0961LL);
              if ( NtfsStatusDebugFlags )
                NtfsStatusTraceAndDebugInternal(a1, 0xC000007F, 0x1C0962u);
              NtfsRaiseStatusInternal(a1, -1073741697, 0, 0, 1837410);
            }
          }
          if ( *(_QWORD *)(FsContext + 504)
            && *(int *)(FsContext + 200) >= 0
            && !v115
            && (_QWORD)xmmword_140095740
            && *(_DWORD *)(FsContext + 256) == 128 )
          {
            v115 = 1;
            *(_DWORD *)(a1 + 12) |= 1u;
            *(_BYTE *)(*(_QWORD *)(a1 + 208) + 3LL) |= 1u;
          }
          v89 = v111;
          if ( (v111 & 1) != 0 )
          {
            v91 = v122;
          }
          else
          {
            if ( (*(_DWORD *)(FsContext + 512) & 0x40000) == 0
              && *(_BYTE *)(FsContext + 460)
              && *(_DWORD *)(FsContext + 256) == 128 )
            {
              if ( (v41 & 0x10) == 0 )
              {
                NtfsAcquireResourceShared(v83, FsContext, 1u);
                v41 |= 0x18u;
                LOBYTE(v143) = v41;
              }
              v90 = *(_QWORD *)(FsContext + 464);
              v91 = v122;
              if ( v122 > v90 )
              {
                if ( v90 <= *(__int64 *)v117 )
                {
LABEL_400:
                  *(_QWORD *)(*(_QWORD *)(a1 + 208) + 80LL) = 1;
                  NtfsFillIrpBuffer(a1, (__int64)v4, v88, 0, 0);
                  v4->IoStatus.Information = v88;
                  Status = 0;
                  goto LABEL_323;
                }
                v88 = v90 - v117[0];
                v127 = v90 - v117[0];
                if ( !v115 )
                {
                  v115 = 1;
                  *(_DWORD *)(a1 + 12) |= 1u;
                }
              }
              if ( (v41 & 8) != 0 )
              {
                if ( *(_WORD *)FsContext == 1794 )
                  v92 = (struct _ERESOURCE *)(*(_QWORD *)(FsContext + 104) + 64LL);
                else
                  v92 = *(struct _ERESOURCE **)(FsContext + 8);
                ExReleaseResourceLite(v92);
                v41 &= 0xE7u;
                LOBYTE(v143) = v41;
              }
            }
            else
            {
              v91 = v122;
            }
            v89 = v111;
          }
          if ( v91 > v78 )
          {
            if ( (v89 & 1) == 0 )
            {
              if ( *(_BYTE *)(FsContext + 460) )
              {
                if ( (v41 & 0x10) == 0 )
                {
                  NtfsAcquireResourceShared(v83, FsContext, 1u);
                  v41 |= 0x18u;
                  LOBYTE(v143) = v41;
                }
                if ( v78 < *(_QWORD *)(FsContext + 464) )
                  v78 = *(_QWORD *)(FsContext + 464);
                v135 = v78;
              }
              v89 = v111;
            }
            if ( v91 > v78 )
            {
              if ( *(__int64 *)v117 >= v78 )
              {
                if ( (v89 & 1) == 0
                  && v113
                  && (*(_BYTE *)(FsContext + 4) & 0x20) != 0
                  && (*(_WORD *)(FsContext + 460) & 0x80FF) == 0x8000
                  && !(unsigned __int8)NtfsReserveClusters(a1, 0) )
                {
                  NtfsAllocateDiskFullContext(a1, v88, 0x27D001C0A6BLL);
                  if ( NtfsStatusDebugFlags )
                    NtfsStatusTraceAndDebugInternal(a1, 0xC000007F, 0x1C0A6Cu);
                  NtfsRaiseStatusInternal(a1, -1073741697, 0, 0, 1837676);
                }
                goto LABEL_400;
              }
              v93 = v78 - v117[0];
              if ( v88 < v93 )
                v93 = v88;
              v88 = v93;
              v127 = v93;
              if ( !v115 )
              {
                v115 = 1;
                *(_DWORD *)(a1 + 12) |= 1u;
              }
              if ( (v111 & 1) == 0
                && v113
                && (*(_BYTE *)(FsContext + 4) & 0x20) != 0
                && (*(_WORD *)(FsContext + 460) & 0x80FF) == 0x8000
                && !(unsigned __int8)NtfsReserveClusters(a1, 0) )
              {
                NtfsAllocateDiskFullContext(a1, v112 - v93, 0x27C001C0A52LL);
                if ( NtfsStatusDebugFlags )
                  NtfsStatusTraceAndDebugInternal(a1, 0xC000007F, 0x1C0A53u);
                NtfsRaiseStatusInternal(a1, -1073741697, 0, 0, 1837651);
              }
            }
            if ( (v41 & 8) != 0 )
            {
              if ( *(_WORD *)FsContext == 1794 )
                v94 = (struct _ERESOURCE *)(*(_QWORD *)(FsContext + 104) + 64LL);
              else
                v94 = *(struct _ERESOURCE **)(FsContext + 8);
              ExReleaseResourceLite(v94);
              v41 &= 0xE7u;
              LOBYTE(v143) = v41;
            }
          }
          if ( (v111 & 1) != 0 )
          {
            v95 = *(_QWORD *)(FsContext + 40);
            if ( *(__int64 *)v117 < v95 )
            {
              if ( *(_QWORD *)v117 + v88 <= v95 )
                v96 = v88;
              else
                v96 = v95 - v117[0];
            }
            else
            {
              v96 = 0;
            }
            v97 = *(_DWORD *)(*(_QWORD *)(a1 + 104) + 364LL);
            if ( ((v97 - 1) & v117[0]) != 0 )
            {
LABEL_453:
              if ( !v96 )
              {
LABEL_486:
                Status = v4->IoStatus.Status;
                if ( Status < 0 )
                {
                  *(_DWORD *)(a1 + 24) = Status;
                  if ( NtfsStatusDebugFlags
                    && (unsigned int)Status < 0xFFFFFFED
                    && Status != -1073741802
                    && (unsigned int)(Status + 2147483643) > 1
                    && Status != -1073741807
                    && Status != -1073741608 )
                  {
                    NtfsStatusTraceAndDebugInternal(a1, Status, 0x1C0BC9u);
                  }
                  v103 = FsRtlNormalizeNtstatus(Status, -1073741591);
                  ExRaiseStatus(v103);
                }
                v71 = v112;
                v4->IoStatus.Information = v112;
                if ( v112 <= v88 )
                  goto LABEL_324;
                NtfsFillIrpBuffer(a1, (__int64)v4, v112 - v88, v88, 0);
                goto LABEL_323;
              }
              if ( (*(_DWORD *)(v128 + 8204) & 1) != 0
                && (*(_DWORD *)(FsContext + 200) & 0x20000) == 0
                && IoGetIoPriorityHint(v4) > IoPriorityLow )
              {
                if ( (v99 = *(_DWORD *)(FsContext + 256), v99 == 128) && !*(_WORD *)(FsContext + 264) || v99 == 160 )
                {
                  if ( ((*(_DWORD *)(v129 + 8) - 2) & 0xFFFFFFFB) != 0 )
                    NtfsHeatLogIo(v4, v129);
                }
              }
              v100 = v112;
              if ( !v115 )
              {
                if ( !v113 || (v41 & 1) != 0 )
                {
                  NtfsSetIoContextAsync(
                    a1,
                    FsContext,
                    v112,
                    v123,
                    *(struct _KTHREAD **)(FsContext + 16),
                    (v41 & 2) != 0);
                }
                else if ( (v41 & 0x10) != 0 )
                {
                  NtfsSetIoContextAsync(a1, FsContext, v112, v123, *(struct _KTHREAD **)(FsContext + 8), 0);
                }
                else
                {
                  NtfsSetIoContextAsync(a1, FsContext, v112, v123, 0, 0);
                }
              }
              if ( (v111 & 4) != 0 )
              {
                v101 = *(_BYTE *)(FsContext + 460) == 0;
                if ( !*(_BYTE *)(FsContext + 460) )
                {
                  if ( (*(_BYTE *)(a1 + 16) & 0x40) != 0 )
                  {
                    Status = -1073741811;
                    if ( !NtfsStatusDebugFlags )
                      goto LABEL_323;
                    v70 = 1837892;
                    goto LABEL_322;
                  }
                  if ( (v111 & 1) == 0 || v96 > v100 )
                    v96 = v88;
                  v102 = NtfsNonCachedNonAlignedIo(a1, (_DWORD)v4, FsContext, v117[0], v96);
                  goto LABEL_482;
                }
              }
              else
              {
                v101 = *(_BYTE *)(FsContext + 460) == 0;
              }
              if ( !v101 )
                v96 = v88;
              v102 = NtfsNonCachedIo(a1, v4, v96, 0);
LABEL_482:
              Status = v102;
              if ( v102 == 259 )
              {
                v41 &= 0xEEu;
                LOBYTE(v143) = v41;
                *(_QWORD *)(a1 + 208) = 0;
                v4 = 0;
                v126 = 0;
                goto LABEL_323;
              }
              if ( v102 >= 0 )
                *(_BYTE *)(*(_QWORD *)(a1 + 208) + 3LL) |= 1u;
              goto LABEL_486;
            }
            v98 = v97 + v96 - 1;
          }
          else
          {
            v97 = *(_DWORD *)(*(_QWORD *)(a1 + 104) + 364LL);
            v98 = v88 + v97 - 1;
          }
          v96 = -v97 & v98;
          goto LABEL_453;
        }
LABEL_497:
        v72 = Entry;
        Status = NtfsCachedRead(a1, v130, (__int64)v4, FsContext, *(union _LARGE_INTEGER *)v117, v85, &v143, Entry);
        v73 = BYTE1(v143);
        v41 = v143;
        v71 = v112;
        if ( Status == 259 )
        {
          v4 = 0;
          v126 = 0;
          a1 = 0;
        }
        goto LABEL_325;
      }
      if ( NtfsStatusDebugFlags && (unsigned int)(v64 + 2147483643) > 1 )
        NtfsStatusTraceAndDebugInternal(a1, v64, 0x1C07DFu);
      NtfsRaiseStatusInternal(a1, v64, 0, 0, 1837023);
    }
    v61 = *(unsigned int *)(*(_QWORD *)(FsContext + 184) + 4LL);
    if ( (v61 & 0x100) != 0 )
    {
      if ( !NtfsAcquireResourceShared(v61, FsContext, 1u) )
        NtfsRaiseStatusInternal(a1, -1073741608, 0, 0, 1836954);
      v41 = v143 | 0x10;
    }
    else
    {
      if ( IoGetTopLevelIrp()->AssociatedIrp.MasterIrp == (struct _IRP *)7 )
      {
        LOBYTE(v62) = 1;
        if ( !(unsigned __int8)NtfsAcquirePagingResourceSharedStarveExclusive(a1, FsContext, v62) )
          NtfsRaiseStatusInternal(a1, -1073741608, 0, 0, 1836932);
      }
      else
      {
        if ( ExIsResourceAcquiredSharedLite((PERESOURCE)(*(_QWORD *)(*(_QWORD *)(FsContext + 184) + 104LL) + 64LL)) )
        {
          v41 = v143;
LABEL_270:
          if ( *(_DWORD *)(FsContext + 516) == 3 && *(_DWORD *)(FsContext + 256) == 128 )
          {
            if ( NtfsStatusDebugFlags )
              NtfsStatusTraceAndDebugInternal(a1, 0xC00004A3, 0x1C07A6u);
            NtfsRaiseStatusInternal(a1, -1073740637, 0, 0, 1836966);
          }
          goto LABEL_277;
        }
        LOBYTE(v63) = 1;
        if ( !(unsigned __int8)NtfsAcquirePagingShared(a1, FsContext, v63, 0) )
          NtfsRaiseStatusInternal(a1, -1073741608, 0, 0, 1836945);
      }
      v41 = v143 | 1;
    }
    LOBYTE(v143) = v41;
    goto LABEL_270;
  }
  if ( NtfsStatusDebugFlags )
    NtfsStatusTraceAndDebugInternal(a1, 0xC0000810, 0x1C00C9u);
  NtfsExtendedCompleteRequestInternal(a1, v4, -1073739760, v4 != 0, 0);
  if ( NtfsStatusDebugFlags )
    NtfsStatusTraceAndDebugInternal(0, 0xC0000810, 0x1C043Au);
  return 3221227536LL;
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
