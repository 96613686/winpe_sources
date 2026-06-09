# RxCommonFileWrite

- ea: `0x140004ac0`
- end: `0x140007708`
- name: `RxCommonFileWrite`
- size: `11336`
- prototype: `__int64 __fastcall(PRX_CONTEXT RxContext)`
- caller_count: `1`
- callee_count: `38`
- tags: `file_ops, loader_planting, installer_update, broker_com_uri`

## callers

- `0x14006f190`

## callees

- `0x140004180`
- `0x140004ac0`
- `0x140007710`
- `0x1400078b0`
- `0x140007910`
- `0x1400079b0`
- `0x140007f60`
- `0x140008030`
- `0x140008190`
- `0x140011130`
- `0x140015230`
- `0x140016a70`
- `0x140016b20`
- `0x140016d40`
- `0x140016d80`
- `0x140016e20`
- `0x140016e70`
- `0x140016ec0`
- `0x140016f40`
- `0x140017040`
- `0x140017220`
- `0x140017280`
- `0x140017370`
- `0x140017540`
- `0x140017a8c`
- `0x14001810c`
- `0x14001c5fc`
- `0x14001dc44`
- `0x14001dca8`
- `0x14001dd94`
- `0x14001e3b0`
- `0x140025c20`
- `0x140025d00`
- `0x140057660`
- `0x140065690`
- `0x140065e40`
- `0x140066280`
- `0x140069970`

## import_xrefs

- `ntoskrnl!FsRtlCheckOplock` at `0x140004e31`
- `ntoskrnl!FsRtlCheckOplock` at `0x140004e31`
- `ntoskrnl!IoGetTopLevelIrp` at `0x140004f8c`
- `ntoskrnl!IoGetTopLevelIrp` at `0x140005d96`
- `ntoskrnl!IoGetTopLevelIrp` at `0x140004f8c`
- `ntoskrnl!IoGetTopLevelIrp` at `0x140005d96`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140005e3b`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140005e3b`
- `ntoskrnl!ExReleaseResourceLite` at `0x140005548`
- `ntoskrnl!ExReleaseResourceLite` at `0x140005a51`
- `ntoskrnl!ExReleaseResourceLite` at `0x140005f16`
- `ntoskrnl!ExReleaseResourceLite` at `0x140007256`
- `ntoskrnl!ExReleaseResourceLite` at `0x140007576`
- `ntoskrnl!ExReleaseResourceLite` at `0x140005548`
- `ntoskrnl!ExReleaseResourceLite` at `0x140005a51`
- `ntoskrnl!ExReleaseResourceLite` at `0x140005f16`
- `ntoskrnl!ExReleaseResourceLite` at `0x140007256`
- `ntoskrnl!ExReleaseResourceLite` at `0x140007576`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14000651b`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14000651b`
- `ntoskrnl!CcSetFileSizes` at `0x14000544c`
- `ntoskrnl!CcSetFileSizes` at `0x14000635b`
- `ntoskrnl!CcSetFileSizes` at `0x14000544c`
- `ntoskrnl!CcSetFileSizes` at `0x14000635b`
- `ntoskrnl!CcInitializeCacheMap` at `0x140006ba3`
- `ntoskrnl!CcInitializeCacheMap` at `0x140006ba3`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x140005692`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x1400059d1`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x14000765f`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x140005692`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x1400059d1`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x14000765f`
- `ntoskrnl!CcCoherencyFlushAndPurgeCache` at `0x140005ec7`
- `ntoskrnl!CcCoherencyFlushAndPurgeCache` at `0x140005ec7`
- `ntoskrnl!ExConvertExclusiveToSharedLite` at `0x140005b29`
- `ntoskrnl!ExConvertExclusiveToSharedLite` at `0x140005b29`
- `ntoskrnl!MmIsFileSectionActive` at `0x14000659b`
- `ntoskrnl!MmIsFileSectionActive` at `0x14000659b`
- `ntoskrnl!CcCanIWrite` at `0x14000745c`
- `ntoskrnl!CcCanIWrite` at `0x14000745c`
- `ntoskrnl!CcZeroData` at `0x140006ea1`
- `ntoskrnl!CcZeroData` at `0x140006ea1`
- `ntoskrnl!CcCopyWrite` at `0x140006afb`
- `ntoskrnl!CcCopyWrite` at `0x140006afb`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x140004f13`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x140005b78`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x140004f13`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x140005b78`
- `ntoskrnl!PoSetPowerRequest` at `0x14000597c`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140004ea7`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140004ea7`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140004f3f`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140004f3f`
- `ntoskrnl!CcSetReadAheadGranularityEx` at `0x140006c92`
- `ntoskrnl!CcSetReadAheadGranularityEx` at `0x140006c92`
- `ntoskrnl!CcDeferWrite` at `0x1400075f0`
- `ntoskrnl!CcDeferWrite` at `0x1400075f0`
- `ntoskrnl!FsRtlCheckLockForWriteAccess` at `0x140004e8a`
- `ntoskrnl!FsRtlCheckLockForWriteAccess` at `0x140005054`
- `ntoskrnl!FsRtlCheckLockForWriteAccess` at `0x140004e8a`
- `ntoskrnl!FsRtlCheckLockForWriteAccess` at `0x140005054`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x1400064ed`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x1400074bb`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x140007541`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x1400064ed`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x1400074bb`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x140007541`
- `ntoskrnl!ExSetResourceOwnerPointer` at `0x14000573d`
- `ntoskrnl!ExSetResourceOwnerPointer` at `0x14000573d`

## string_xrefs

- `0x1400266c8`: `RxCommonFileWrite`

## pseudocode

```c
__int64 __fastcall RxCommonFileWrite(PRX_CONTEXT RxContext, IRP *a2, ULONG_PTR a3, LARGE_INTEGER *a4)
{
  char v4; // bl
  PIRP v6; // r8
  PRX_CONTEXT v7; // rsi
  struct _IO_STACK_LOCATION *CurrentStackLocation; // r14
  PNON_PAGED_FCB NonPagedFcb; // r13
  char v10; // al
  char v11; // r11
  ULONG Flags; // edx
  PVOID *p_RdbssDbgExtension; // r9
  bool v14; // zf
  int v15; // r10d
  LARGE_INTEGER ByteOffset; // rbx
  __int64 v17; // r14
  LARGE_INTEGER *v18; // r10
  LARGE_INTEGER v19; // rcx
  NTSTATUS Status; // r14d
  PIRP v21; // r13
  ULONG v22; // r8d
  NTSTATUS v23; // eax
  LARGE_INTEGER SharedCacheMap; // rdx
  int v25; // ecx
  PVOID *v26; // r8
  LONGLONG v27; // r9
  char v28; // dl
  ULONG v29; // r8d
  PFILE_OBJECT v30; // r10
  char v31; // r13
  char v32; // dl
  __int64 v33; // rax
  char v34; // dl
  char IsResourceAcquiredSharedLite; // al
  char v36; // cl
  unsigned __int8 v37; // r8
  LARGE_INTEGER v38; // rcx
  _DWORD *v39; // rcx
  ULONG v40; // ecx
  NTSTATUS v41; // eax
  __int64 v42; // rcx
  struct _FILE_OBJECT *v43; // r10
  PSECTION_OBJECT_POINTERS SectionObjectPointer; // rax
  PRX_CONTEXT v45; // r14
  bool v46; // al
  unsigned __int8 v47; // bl
  PSECTION_OBJECT_POINTERS v48; // rax
  bool v49; // r12
  LARGE_INTEGER v50; // rdx
  PIRP v51; // rcx
  struct _FILE_OBJECT *v52; // rbx
  struct _CC_FILE_SIZES *pFcb; // r13
  LARGE_INTEGER v54; // rcx
  LARGE_INTEGER FileSize; // r9
  LARGE_INTEGER v56; // r8
  ERESOURCE_THREAD v57; // r8
  unsigned __int8 v58; // bl
  IRP *CurrentIrp; // rbx
  _QWORD *p_DataSectionObject; // rax
  void *v61; // rbx
  PIRP v62; // rbx
  __int64 v63; // rcx
  __int64 (__fastcall *v64)(PRX_CONTEXT, PMRX_SRV_OPEN); // rax
  int v65; // eax
  char v66; // r8
  _QWORD *v67; // rcx
  _QWORD *i; // rax
  const CHAR *v69; // rax
  const CHAR *v70; // rcx
  bool v71; // dl
  unsigned __int8 v72; // r14
  NTSTATUS v73; // eax
  ULONG v74; // r8d
  char v75; // cl
  __int64 v76; // r8
  PFILE_OBJECT v77; // r10
  LARGE_INTEGER v78; // rcx
  char v79; // r14
  LARGE_INTEGER v80; // rax
  BOOLEAN v81; // al
  PDEVICE_OBJECT v82; // rcx
  LARGE_INTEGER *p_QuadPart; // rdx
  __int64 v84; // rcx
  __int64 v85; // r8
  int v86; // eax
  _QWORD *v87; // rax
  PIRP TopIrpIfRdbssIrp; // rax
  PVOID *v89; // rax
  const CHAR *v90; // rcx
  ERESOURCE_THREAD v91; // rbx
  BOOLEAN v92; // dl
  BOOLEAN v93; // al
  BOOLEAN v94; // r13
  BOOLEAN v95; // r9
  __int64 v96; // rcx
  struct _CC_FILE_SIZES *v97; // rdx
  __int64 v98; // r8
  __int64 v99; // rcx
  unsigned int v100; // eax
  _QWORD *v101; // rcx
  ERESOURCE_THREAD v102; // rbx
  __int64 v103; // rbx
  __int64 v105; // r9
  unsigned __int64 v106; // rcx
  LARGE_INTEGER v107; // rax
  __int64 v108; // rax
  BOOLEAN v109; // r8
  ERESOURCE_THREAD v110; // rbx
  int v111; // r12d
  BOOLEAN v112; // bl
  const char *v113; // r9
  const char *v114; // r8
  const char *v115; // rdx
  const char *v116; // rax
  const CHAR *PostIrpRoutine; // [rsp+88h] [rbp-1A8h]
  BOOLEAN Retrying[8]; // [rsp+90h] [rbp-1A0h]
  LONGLONG v119; // [rsp+98h] [rbp-198h]
  unsigned __int8 v120; // [rsp+C8h] [rbp-168h]
  unsigned __int8 v121; // [rsp+C9h] [rbp-167h]
  unsigned __int8 v122; // [rsp+CAh] [rbp-166h]
  char v123; // [rsp+D1h] [rbp-15Fh]
  char v124; // [rsp+D2h] [rbp-15Eh]
  char v125; // [rsp+D3h] [rbp-15Dh]
  char v126; // [rsp+D4h] [rbp-15Ch]
  char v127; // [rsp+D5h] [rbp-15Bh]
  char v128; // [rsp+D6h] [rbp-15Ah]
  ULONG Length; // [rsp+D8h] [rbp-158h]
  char v130; // [rsp+DEh] [rbp-152h]
  char v131; // [rsp+DFh] [rbp-151h]
  PFILE_OBJECT FileObject; // [rsp+E0h] [rbp-150h]
  LARGE_INTEGER EndOffset; // [rsp+E8h] [rbp-148h] BYREF
  char v134; // [rsp+F0h] [rbp-140h]
  char v135; // [rsp+F1h] [rbp-13Fh]
  PVOID *v136; // [rsp+F8h] [rbp-138h] BYREF
  LARGE_INTEGER v137; // [rsp+100h] [rbp-130h]
  const CHAR *QuadPart; // [rsp+108h] [rbp-128h] BYREF
  _QWORD *v139; // [rsp+110h] [rbp-120h] BYREF
  LARGE_INTEGER v140; // [rsp+118h] [rbp-118h] BYREF
  char v141; // [rsp+120h] [rbp-110h]
  PIRP Irp; // [rsp+128h] [rbp-108h]
  ULONG v143; // [rsp+130h] [rbp-100h]
  LARGE_INTEGER StartOffset; // [rsp+138h] [rbp-F8h] BYREF
  LARGE_INTEGER *v145; // [rsp+140h] [rbp-F0h]
  const CHAR *v146; // [rsp+148h] [rbp-E8h]
  LARGE_INTEGER FileOffset; // [rsp+150h] [rbp-E0h] BYREF
  PRX_CONTEXT v148; // [rsp+158h] [rbp-D8h]
  PVOID *v149; // [rsp+160h] [rbp-D0h]
  PRX_CONTEXT v150; // [rsp+168h] [rbp-C8h]
  __int64 v151; // [rsp+170h] [rbp-C0h]
  ULONG_PTR v152; // [rsp+178h] [rbp-B8h]
  LARGE_INTEGER v153; // [rsp+180h] [rbp-B0h]
  LARGE_INTEGER v154; // [rsp+188h] [rbp-A8h]
  PFILE_OBJECT v155; // [rsp+190h] [rbp-A0h]
  __int64 v156; // [rsp+198h] [rbp-98h]
  struct _IO_STATUS_BLOCK IoStatus; // [rsp+1A0h] [rbp-90h] BYREF
  LARGE_INTEGER v158; // [rsp+1B0h] [rbp-80h]
  IRP *v159; // [rsp+1B8h] [rbp-78h]
  LARGE_INTEGER *v160; // [rsp+1C0h] [rbp-70h]
  LARGE_INTEGER v161; // [rsp+1C8h] [rbp-68h]
  LARGE_INTEGER v162; // [rsp+1D0h] [rbp-60h]
  __int64 v163; // [rsp+1D8h] [rbp-58h] BYREF
  int v164; // [rsp+1E0h] [rbp-50h]
  int v165; // [rsp+1E4h] [rbp-4Ch]

  v4 = (char)a4;
  v145 = a4;
  v6 = a2;
  Irp = a2;
  v7 = RxContext;
  v148 = RxContext;
  v159 = a2;
  v152 = a3;
  v160 = a4;
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  FileObject = CurrentStackLocation->FileObject;
  NonPagedFcb = RxContext->NonPagedFcb;
  FileOffset.QuadPart = 0;
  EndOffset.QuadPart = 0;
  v140.QuadPart = 0;
  StartOffset.QuadPart = 0;
  v163 = 0;
  v164 = 0;
  LOWORD(v165) = 0;
  v151 = *(_QWORD *)(a3 + 120);
  v10 = *(_BYTE *)(v151 + 77);
  if ( !v10 || (v11 = 0, v122 = 0, v10 == 4) )
  {
    v11 = 1;
    v122 = 1;
  }
  Flags = a2->Flags;
  p_RdbssDbgExtension = &RxContext->RdbssDbgExtension;
  if ( (Flags & 2) != 0 )
  {
    v121 = 1;
    goto LABEL_7;
  }
  v121 = 0;
  v136 = &RxContext->RdbssDbgExtension;
  if ( (*(_DWORD *)p_RdbssDbgExtension & 2) != 0 )
  {
LABEL_7:
    v125 = 1;
    v136 = &RxContext->RdbssDbgExtension;
    goto LABEL_8;
  }
  v125 = 0;
LABEL_8:
  LOBYTE(Flags) = Flags & 1;
  LODWORD(QuadPart) = Flags;
  v14 = (*(_DWORD *)p_RdbssDbgExtension & 0x1000) == 0;
  v15 = *(_DWORD *)p_RdbssDbgExtension & 0x1000;
  v153.LowPart = v15;
  v120 = v14;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    v113 = "Sy";
    if ( v15 )
      v113 = "--";
    v114 = "Nc-";
    if ( !(_BYTE)Flags )
      v114 = "---";
    v115 = "Pg-";
    if ( !v121 )
      v115 = "---";
    v116 = "Wt-";
    if ( !v125 )
      v116 = "---";
    WPP_SF_qqqLissss(
      WPP_GLOBAL_Control->AttachedDevice,
      (_DWORD)v115,
      (_DWORD)v114,
      (_DWORD)RxContext,
      a3,
      v4,
      CurrentStackLocation->Parameters.Read.Length,
      CurrentStackLocation->Parameters.Read.ByteOffset.QuadPart,
      (__int64)v116,
      (__int64)v115,
      (__int64)v114,
      (__int64)v113);
    LOBYTE(Flags) = (_BYTE)QuadPart;
    v6 = Irp;
    p_RdbssDbgExtension = v136;
    v11 = v122;
  }
  LOWORD(v7->Flags) = 0;
  ByteOffset = CurrentStackLocation->Parameters.Read.ByteOffset;
  FileOffset = ByteOffset;
  EndOffset = ByteOffset;
  v17 = CurrentStackLocation->Parameters.Read.Length;
  Length = v17;
  if ( (*(_DWORD *)p_RdbssDbgExtension & 0x200) != 0 || *(_BYTE *)(a3 + 257) )
  {
    v18 = v145;
  }
  else
  {
    v105 = *(_QWORD *)&NonPagedFcb[2].AdvancedFcbHeaderMutex.Contention;
    v18 = v145;
    if ( v105 )
    {
      v106 = (unsigned __int64)HIDWORD(KeGetPcr()[1].LockArray) << 8;
      _InterlockedIncrement((volatile signed __int32 *)(v106 + v105 + 120));
      v107 = EndOffset;
      if ( EndOffset.QuadPart != v145[20].QuadPart )
      {
        _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)&NonPagedFcb[2].AdvancedFcbHeaderMutex.Contention
                                                        + v106
                                                        + 124));
        v107 = EndOffset;
      }
      v145[20].QuadPart = v17 + v107.QuadPart;
      v108 = *(_QWORD *)&NonPagedFcb[2].AdvancedFcbHeaderMutex.Contention;
      if ( v121 )
      {
        _InterlockedAdd64((volatile signed __int64 *)(v108 + v106 + 64), v17);
        p_RdbssDbgExtension = v136;
        goto LABEL_11;
      }
      if ( !(_BYTE)Flags )
      {
        _InterlockedAdd64((volatile signed __int64 *)(v108 + v106 + 80), v17);
        p_RdbssDbgExtension = v136;
        goto LABEL_11;
      }
      _InterlockedAdd64((volatile signed __int64 *)(v108 + v106 + 72), v17);
    }
    p_RdbssDbgExtension = v136;
  }
LABEL_11:
  if ( v11 && !(_DWORD)v17 )
    return 0;
  if ( !v6->UserBuffer && !v6->MdlAddress )
    return 3221225485LL;
  v149 = (PVOID *)v17;
  if ( 0x7FFFFFFFFFFFFFFFLL - EndOffset.QuadPart < v17 && ByteOffset.QuadPart != -1 )
    return 3221225485LL;
  v150 = v7;
  v156 = v151;
  v143 = v17;
  v155 = FileObject;
  if ( v18 )
    v19 = v18[4];
  else
    v19.QuadPart = 0;
  v158 = v19;
  v137 = v19;
  if ( !(_BYTE)Flags
    && (*(_DWORD *)(a3 + 164) & 2) != 0
    && (*(_DWORD *)(a3 + 160) & 0x8000000) != 0
    && (*(_DWORD *)(v19.QuadPart + 72) & 2) == 0
    && (*(_DWORD *)p_RdbssDbgExtension & 4) == 0 )
  {
    v109 = v125 && (*(_DWORD *)p_RdbssDbgExtension & 0x200) == 0;
    if ( !CcCanIWrite(FileObject, v17, v109, (*(_DWORD *)p_RdbssDbgExtension & 0x40) != 0) )
    {
      v112 = (*(_DWORD *)v136 & 0x40) != 0;
      RxPrePostIrp(v7, Irp);
      *(_DWORD *)v136 |= 0x40u;
      CcDeferWrite(FileObject, (PCC_POST_DEFERRED_WRITE)RxAddToWorkque, v7, Irp, v17, v112);
      return 259;
    }
    LOBYTE(Flags) = (_BYTE)QuadPart;
  }
  Status = -1073741811;
  v154.QuadPart = 0;
  v161.QuadPart = 0;
  v123 = 0;
  v134 = 0;
  v128 = 0;
  v127 = 0;
  v130 = 0;
  v131 = 0;
  v126 = 0;
  v135 = Flags;
  v162 = ByteOffset;
  RxInitializeLowIoContext(v7, 1u, (PLOWIO_CONTEXT)((char *)&v7->9 + 120));
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_40322347dcd53e0bf93cb1041cae84c9_Traceguids);
  }
  if ( !v121 )
  {
    v21 = Irp;
    if ( (*(_DWORD *)v136 & 2) != 0
      || (Irp->Flags & 1) == 0
      && (*(_DWORD *)(a3 + 164) & 2) != 0
      && (*(_DWORD *)(a3 + 160) & 0x8000000) != 0
      && (*(_DWORD *)(v137.QuadPart + 72) & 2) == 0 )
    {
      v22 = 2;
    }
    else
    {
      v22 = 3;
    }
    v23 = _RxAcquireFcb((PFCB)a3, v7, v22, 0, PostIrpRoutine, *(ULONG *)Retrying);
    Status = v23;
    if ( v23 == -1073741739 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 18, WPP_40322347dcd53e0bf93cb1041cae84c9_Traceguids, a3);
      }
      v123 = 1;
      v31 = (char)QuadPart;
      goto LABEL_107;
    }
    if ( v23 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_40322347dcd53e0bf93cb1041cae84c9_Traceguids, a3, v23);
      }
      goto LABEL_400;
    }
    v28 = Irp->Flags & 1;
    v29 = Irp->Flags & 2;
    LOBYTE(v25) = 0;
    LODWORD(v139) = v25;
    if ( EndOffset.QuadPart == -1 || (__int64)v149 + EndOffset.QuadPart > *(_QWORD *)(a3 + 40) )
    {
      LOBYTE(v25) = 1;
      LODWORD(v139) = v25;
    }
    if ( v28
      || (*(_DWORD *)(a3 + 164) & 2) == 0
      || (*(_DWORD *)(a3 + 160) & 0x8000000) == 0
      || (*(_DWORD *)(v137.QuadPart + 72) & 2) != 0 )
    {
      v30 = FileObject;
      v25 = (unsigned __int8)v25;
      if ( FileObject->SectionObjectPointer->DataSectionObject )
        v25 = 1;
      LODWORD(v139) = v25;
    }
    else
    {
      v30 = FileObject;
    }
    if ( !v28
      && !v29
      && (*(_DWORD *)(a3 + 164) & 2) != 0
      && (*(_DWORD *)(a3 + 160) & 0x8000000) != 0
      && (*(_DWORD *)(v137.QuadPart + 72) & 2) == 0 )
    {
      p_DataSectionObject = &v30->SectionObjectPointer->DataSectionObject;
      if ( !*p_DataSectionObject || !p_DataSectionObject[1] || !v30->PrivateCacheMap )
      {
        LOBYTE(v25) = 1;
        LODWORD(v139) = v25;
      }
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      *(_DWORD *)Retrying = *(_DWORD *)(a3 + 156);
      PostIrpRoutine = *(const CHAR **)(a3 + 40);
      WPP_SF_iiDDDd(WPP_GLOBAL_Control->AttachedDevice, 20, WPP_GLOBAL_Control, *(_QWORD *)(a3 + 32));
      LOBYTE(v25) = (_BYTE)v139;
    }
    if ( !(_BYTE)v25 || ExIsResourceAcquiredExclusiveLite(*(PERESOURCE *)(a3 + 8)) )
      goto LABEL_34;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 21, WPP_40322347dcd53e0bf93cb1041cae84c9_Traceguids);
    }
    v71 = (unsigned __int64)v7 > 0xFFFFFFFFFFFFFFFDuLL;
    v72 = *(_BYTE *)(*(_QWORD *)(a3 + 8) + 26LL) & 0x80;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_16f2bee2656c381c8186d78b34bda825_Traceguids, v72);
      v71 = (unsigned __int64)v7 > 0xFFFFFFFFFFFFFFFDuLL;
    }
    if ( v72 )
    {
      if ( v71 )
      {
LABEL_232:
        ExReleaseResourceLite(*(PERESOURCE *)(a3 + 8));
        v73 = _RxAcquireFcb((PFCB)a3, v7, 1u, 0, PostIrpRoutine, *(ULONG *)Retrying);
        Status = v73;
        if ( v73 == -1073741739 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 22, WPP_40322347dcd53e0bf93cb1041cae84c9_Traceguids, a3);
          }
          v123 = 1;
          v26 = (PVOID *)v120;
          v31 = (char)QuadPart;
          goto LABEL_107;
        }
        if ( !v73 )
        {
          v74 = v21->Flags;
          v75 = v74 & 1;
          v76 = v74 & 2;
          LOBYTE(SharedCacheMap.LowPart) = 0;
          LODWORD(v139) = SharedCacheMap.LowPart;
          if ( EndOffset.QuadPart == -1 || (__int64)v149 + EndOffset.QuadPart > *(_QWORD *)(a3 + 40) )
          {
            LOBYTE(SharedCacheMap.LowPart) = 1;
            LODWORD(v139) = SharedCacheMap.LowPart;
          }
          if ( v75
            || (*(_DWORD *)(a3 + 164) & 2) == 0
            || (*(_DWORD *)(a3 + 160) & 0x8000000) == 0
            || (*(_DWORD *)(v137.QuadPart + 72) & 2) != 0 )
          {
            v77 = FileObject;
            SharedCacheMap.LowPart = LOBYTE(SharedCacheMap.LowPart);
            if ( FileObject->SectionObjectPointer->DataSectionObject )
              SharedCacheMap.LowPart = 1;
            LODWORD(v139) = SharedCacheMap.LowPart;
          }
          else
          {
            v77 = FileObject;
          }
          if ( !v75
            && !(_DWORD)v76
            && (*(_DWORD *)(a3 + 164) & 2) != 0
            && (*(_DWORD *)(a3 + 160) & 0x8000000) != 0
            && (*(_DWORD *)(v137.QuadPart + 72) & 2) == 0 )
          {
            v87 = &v77->SectionObjectPointer->DataSectionObject;
            if ( !*v87 || !v87[1] || !v77->PrivateCacheMap )
            {
              LOBYTE(SharedCacheMap.LowPart) = 1;
              LODWORD(v139) = SharedCacheMap.LowPart;
            }
          }
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            *(_DWORD *)Retrying = *(_DWORD *)(a3 + 156);
            WPP_SF_iiDDDd(WPP_GLOBAL_Control->AttachedDevice, 24, v76, *(_QWORD *)(a3 + 32));
            LOBYTE(SharedCacheMap.LowPart) = (_BYTE)v139;
          }
          if ( !LOBYTE(SharedCacheMap.LowPart) )
            ExConvertExclusiveToSharedLite(*(PERESOURCE *)(a3 + 8));
LABEL_34:
          FsRtlCheckOplock((POPLOCK)(a3 + 88), v21, v7, 0, 0);
          if ( (__int64)v149 + EndOffset.QuadPart > *(_QWORD *)(a3 + 40) )
          {
            v86 = *(_DWORD *)(a3 + 164);
            if ( ((v86 & 0x10) != 0 || (v86 & 0x20) != 0) && (*(_DWORD *)(a3 + 160) & 0x800) != 0 )
            {
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
              {
                WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 25, WPP_40322347dcd53e0bf93cb1041cae84c9_Traceguids, a3);
              }
              *(_DWORD *)(a3 + 160) &= 0xFFBFF7FF;
            }
          }
          v31 = (char)QuadPart;
          if ( ((_BYTE)QuadPart
             || (*(_DWORD *)(a3 + 164) & 2) == 0
             || (*(_DWORD *)(a3 + 160) & 0x8000000) == 0
             || (*(_DWORD *)(v137.QuadPart + 72) & 2) != 0)
            && FileObject->SectionObjectPointer->DataSectionObject )
          {
            QuadPart = 0;
            IoStatus = 0;
            v79 = 0;
            v141 = 0;
            if ( *(_DWORD *)(a3 + 484) )
              goto LABEL_422;
            if ( ByteOffset.QuadPart == -1 )
              v80 = *(LARGE_INTEGER *)(a3 + 32);
            else
              v80 = FileOffset;
            QuadPart = (const CHAR *)v80.QuadPart;
            v81 = ExAcquireResourceExclusiveLite(*(PERESOURCE *)(a3 + 16), 1u);
            if ( v81 )
              BYTE1(v7->Flags) = 1;
            v82 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
            {
              WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 18, WPP_16f2bee2656c381c8186d78b34bda825_Traceguids, v81);
            }
            if ( (BYTE4(WPP_MAIN_CB.Dpc.DpcListEntry.Next) & 8) != 0 )
              McTemplateK0p_EtwWriteTransfer(v82, CcPurgeRequest, &v7->LowIoContext.Flags + 1, a3);
            if ( ++*(_DWORD *)(a3 + 636) > 0x10u )
            {
              LODWORD(v139) = 0;
              MmIsFileSectionActive(*(_QWORD *)(a3 + 304) + 8LL, 7, &v139);
              if ( !(_DWORD)v139
                && (*(_DWORD *)(a3 + 184) == *(_DWORD *)(a3 + 188)
                 || (*(_DWORD *)(a3 + 164) & 2) == 0
                 || (*(_DWORD *)(a3 + 160) & 0x8000000) == 0) )
              {
                v79 = 1;
                v141 = 1;
                *(_DWORD *)(a3 + 636) = 0;
              }
            }
            p_QuadPart = (LARGE_INTEGER *)&QuadPart;
            if ( v79 )
              p_QuadPart = 0;
            CcCoherencyFlushAndPurgeCache(FileObject->SectionObjectPointer, p_QuadPart, Length, &IoStatus, 0);
            if ( (BYTE4(WPP_MAIN_CB.Dpc.DpcListEntry.Next) & 8) != 0 )
              McTemplateK0p_EtwWriteTransfer(v84, CcPurgeCompletion, &v7->LowIoContext.Flags + 1, a3);
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
            {
              WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 20, WPP_16f2bee2656c381c8186d78b34bda825_Traceguids);
            }
            BYTE1(v7->Flags) = 0;
            ExReleaseResourceLite(*(PERESOURCE *)(a3 + 16));
            Status = IoStatus.Status;
            if ( IoStatus.Status < 0 )
            {
              if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
                || !BYTE1(WPP_GLOBAL_Control->Timer) )
              {
                goto LABEL_314;
              }
              WPP_SF_qD(
                WPP_GLOBAL_Control->AttachedDevice,
                26,
                WPP_40322347dcd53e0bf93cb1041cae84c9_Traceguids,
                v7,
                IoStatus.Status);
              v26 = (PVOID *)v120;
              goto LABEL_107;
            }
            if ( IoStatus.Status == 277 && *(_DWORD *)(a3 + 484) )
            {
LABEL_422:
              Status = -1073740747;
              goto LABEL_314;
            }
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
            {
              HIDWORD(v119) = v137.HighPart;
              *(_QWORD *)Retrying = a3;
              PostIrpRoutine = QuadPart;
              ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))WPP_SF_DiqqqD)(
                WPP_GLOBAL_Control->AttachedDevice,
                (LARGE_INTEGER)SharedCacheMap.QuadPart,
                v85,
                Length);
            }
          }
          if ( !FsRtlCheckLockForWriteAccess((PFILE_LOCK)(a3 + 536), Irp) )
          {
            Status = -1073741740;
            goto LABEL_314;
          }
          ExAcquirePushLockExclusiveEx(&RxPowerContext, 0);
          *(_BYTE *)(a3 + 282) |= 0x80u;
          v32 = *(_BYTE *)(a3 + 282);
          if ( (v32 & 2) == 0 )
            goto LABEL_46;
          if ( (*(_DWORD *)(*(_QWORD *)(a3 + 400) + 336LL) & 0x100) == 0 )
            goto LABEL_46;
          v33 = *(_QWORD *)(a3 + 120);
          if ( *(_BYTE *)(v33 + 77)
            || *(_WORD *)a3 == 0xEC21
            || (*(_DWORD *)(*(_QWORD *)(v33 + 32) + 96LL) & 0x80u) != 0 )
          {
            goto LABEL_46;
          }
          v124 = 2;
          v34 = v32 & 0xFD;
          *(_BYTE *)(a3 + 282) = v34;
          *(_BYTE *)(a3 + 282) = v34 | 4;
          IsResourceAcquiredSharedLite = ExIsResourceAcquiredSharedLite(*(PERESOURCE *)(a3 + 8));
          v36 = *(_BYTE *)(a3 + 283);
          if ( !IsResourceAcquiredSharedLite )
          {
            if ( !v36 )
              *(_BYTE *)(a3 + 283) = 2;
LABEL_46:
            ExReleasePushLockExclusiveEx(&RxPowerContext, 0);
            goto LABEL_47;
          }
          if ( v36 )
          {
            v66 = *(_BYTE *)(a3 + 283);
            v124 = v66;
            *(_BYTE *)(a3 + 283) = 0;
          }
          else
          {
            v66 = 2;
          }
          v67 = (_QWORD *)(a3 + 264);
          for ( i = *(_QWORD **)(a3 + 264); ; i = (_QWORD *)*i )
          {
            v139 = i;
            if ( i == v67 )
              goto LABEL_46;
            if ( *((_WORD *)i - 68) != 0xEBAA )
              break;
LABEL_222:
            ;
          }
          v69 = (const CHAR *)(i + 6);
          QuadPart = v69;
          v70 = *(const CHAR **)v69;
          while ( 1 )
          {
            v146 = v70;
            if ( v70 == v69 )
            {
              i = v139;
              v67 = (_QWORD *)(a3 + 264);
              goto LABEL_222;
            }
            if ( *((_WORD *)v70 - 56) != 0xEBAA )
              break;
LABEL_220:
            v70 = *(const CHAR **)v70;
            v66 = v124;
          }
          if ( byte_140038BD8 == 1 )
          {
            if ( v66 != 1 )
              goto LABEL_219;
          }
          else if ( byte_140038BD8 != 2 || (unsigned __int8)(v66 - 1) > 1u )
          {
            goto LABEL_219;
          }
          RxUpdatePowerRequest(PoSetPowerRequest, *((_QWORD *)v70 + 20));
          v70 = v146;
LABEL_219:
          v69 = QuadPart;
          goto LABEL_220;
        }
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 23, WPP_40322347dcd53e0bf93cb1041cae84c9_Traceguids, a3, v73);
        }
LABEL_400:
        v123 = 0;
        v26 = (PVOID *)v120;
        v31 = (char)QuadPart;
        goto LABEL_107;
      }
      if ( *(_DWORD *)(*(_QWORD *)(a3 + 304) + 296LL) && (*(_DWORD *)(a3 + 156) & 0x80000) == 0 )
      {
        if ( (unsigned __int8)RxIsSafeToProcessBufferingStateChange(v7, a3) )
          RxProcessFcbChangeBufferingStateRequestInternal((PVOID)a3);
        v71 = (unsigned __int64)v7 > 0xFFFFFFFFFFFFFFFDuLL;
      }
    }
    if ( !v71 )
      LOBYTE(v7->Flags) = 0;
    goto LABEL_232;
  }
  if ( !(unsigned __int8)ExIsResourceAcquiredSharedLite(*(PERESOURCE *)(a3 + 16)) )
  {
    v92 = (*(_DWORD *)v136 & 0x4000000) == 0;
    LODWORD(v146) = v92;
    v93 = ExAcquireResourceSharedLite(*(PERESOURCE *)(a3 + 16), v92);
    v94 = v93;
    if ( v93 )
      BYTE1(v7->Flags) = 1;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_16f2bee2656c381c8186d78b34bda825_Traceguids, v93);
    }
    if ( !v94 )
    {
      Status = -1073741740;
      v31 = (char)QuadPart;
      goto LABEL_107;
    }
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    *(_DWORD *)Retrying = *(_DWORD *)(a3 + 156);
    PostIrpRoutine = *(const CHAR **)(a3 + 40);
    ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))WPP_SF_iiDDD)(
      WPP_GLOBAL_Control->AttachedDevice,
      (LARGE_INTEGER)SharedCacheMap.QuadPart,
      v26,
      *(_QWORD *)(a3 + 32));
  }
  v31 = (char)QuadPart;
LABEL_47:
  SharedCacheMap = v137;
  if ( v31
    || (*(_DWORD *)(a3 + 164) & 2) == 0
    || (*(_DWORD *)(a3 + 160) & 0x8000000) == 0
    || (*(_DWORD *)(v137.QuadPart + 72) & 2) != 0 )
  {
    v37 = v121;
    if ( !v121 )
      goto LABEL_49;
  }
  else
  {
    v37 = v121;
  }
  if ( *(_DWORD *)(a3 + 636) )
    *(_DWORD *)(a3 + 636) = 0;
LABEL_49:
  StartOffset = *(LARGE_INTEGER *)(a3 + 40);
  v38 = *(LARGE_INTEGER *)(a3 + 32);
  v140 = v38;
  if ( v37 )
  {
    if ( EndOffset.QuadPart >= v38.QuadPart )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 28, WPP_40322347dcd53e0bf93cb1041cae84c9_Traceguids);
      }
      Status = 0;
      goto LABEL_314;
    }
    if ( (__int64)v149 > v38.QuadPart - EndOffset.QuadPart )
    {
      if ( (*(_DWORD *)(SharedCacheMap.QuadPart + 128) & 8) != 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 29, WPP_40322347dcd53e0bf93cb1041cae84c9_Traceguids);
        }
      }
      else
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 30, WPP_40322347dcd53e0bf93cb1041cae84c9_Traceguids);
          v38.LowPart = v140.LowPart;
        }
        Length = v38.LowPart - EndOffset.LowPart;
        v143 = v38.LowPart - EndOffset.LowPart;
      }
    }
  }
  if ( IoGetTopLevelIrp() != (PIRP)2 )
    goto LABEL_51;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 31, WPP_40322347dcd53e0bf93cb1041cae84c9_Traceguids);
  }
  v130 = 1;
  if ( (*(_BYTE *)(a3 + 4) & 0x20) != 0 )
  {
    v78.QuadPart = EndOffset.QuadPart + Length;
    SharedCacheMap = v140;
    if ( v78.QuadPart > StartOffset.QuadPart
      && EndOffset.QuadPart < v140.QuadPart
      && v78.QuadPart > (__int64)((StartOffset.QuadPart + 4095) & 0xFFFFFFFFFFFFF000uLL) )
    {
      Status = -1073741740;
LABEL_314:
      v26 = (PVOID *)v120;
      goto LABEL_107;
    }
  }
  else
  {
LABEL_51:
    SharedCacheMap = v140;
  }
  if ( (Irp->Flags & 0x40) == 0 )
    goto LABEL_53;
  if ( (*(_DWORD *)v136 & 0x10) != 0 )
  {
    TopIrpIfRdbssIrp = RxGetTopIrpIfRdbssIrp();
    if ( (unsigned __int64)TopIrpIfRdbssIrp < 0x10000
      || TopIrpIfRdbssIrp->Tail.Overlay.CurrentStackLocation->MajorFunction != 4 )
    {
      goto LABEL_280;
    }
    v126 = 1;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 32, WPP_40322347dcd53e0bf93cb1041cae84c9_Traceguids);
    }
LABEL_349:
    v39 = v136;
    *(_DWORD *)v136 |= 4u;
    SharedCacheMap = v140;
    goto LABEL_54;
  }
  if ( IoGetTopLevelIrp() == (PIRP)4 )
  {
    v126 = 1;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 33, WPP_40322347dcd53e0bf93cb1041cae84c9_Traceguids);
      v39 = v136;
      *(_DWORD *)v136 |= 4u;
      SharedCacheMap = v140;
      goto LABEL_54;
    }
    goto LABEL_349;
  }
LABEL_280:
  SharedCacheMap = v140;
LABEL_53:
  v39 = v136;
LABEL_54:
  if ( v130 || v126 || ByteOffset.QuadPart != -1 && EndOffset.QuadPart + Length <= StartOffset.QuadPart )
  {
    v27 = v121;
    goto LABEL_59;
  }
  if ( v153.LowPart )
  {
    v125 = 1;
    *v39 |= 2u;
    *v39 &= ~0x1000u;
    v120 = 1;
    if ( v31 )
      v127 = 1;
  }
  if ( !ExIsResourceAcquiredExclusiveLite(*(PERESOURCE *)(a3 + 8)) )
  {
    RxReleaseReadWriteResources(v7, a3);
    if ( (*(_DWORD *)v136 & 0x4000000) != 0 )
    {
      Status = _RxAcquireFcb((PFCB)a3, v7, 1u, 1u, PostIrpRoutine, *(ULONG *)Retrying);
      if ( Status == -1073741739 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 34, WPP_40322347dcd53e0bf93cb1041cae84c9_Traceguids, a3);
        }
        Status = -1073741740;
        goto LABEL_362;
      }
    }
    else
    {
      Status = _RxAcquireFcb((PFCB)a3, v7, 1u, 0, PostIrpRoutine, *(ULONG *)Retrying);
    }
    if ( Status == -1073741739 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 35, WPP_40322347dcd53e0bf93cb1041cae84c9_Traceguids, a3);
      }
      goto LABEL_138;
    }
    if ( !Status )
      goto LABEL_173;
LABEL_362:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 36, WPP_40322347dcd53e0bf93cb1041cae84c9_Traceguids, a3, Status);
    }
    goto LABEL_108;
  }
LABEL_173:
  StartOffset = *(LARGE_INTEGER *)(a3 + 40);
  SharedCacheMap = *(LARGE_INTEGER *)(a3 + 32);
  v140 = SharedCacheMap;
  if ( v127 && (*(_QWORD *)(*(_QWORD *)(a3 + 304) + 8LL) || EndOffset.QuadPart + Length > SharedCacheMap.QuadPart) )
    v127 = 0;
  v27 = v121;
  if ( v121 )
  {
    if ( EndOffset.QuadPart >= SharedCacheMap.QuadPart )
    {
      Status = 0;
      goto LABEL_107;
    }
    if ( (*(_DWORD *)(v137.QuadPart + 128) & 8) == 0 && Length > SharedCacheMap.QuadPart - EndOffset.QuadPart )
    {
      Length = SharedCacheMap.LowPart - EndOffset.LowPart;
      v143 = SharedCacheMap.LowPart - EndOffset.LowPart;
    }
  }
LABEL_59:
  v154 = SharedCacheMap;
  v161 = StartOffset;
  if ( ByteOffset.QuadPart == -1 )
  {
    EndOffset = SharedCacheMap;
    FileOffset = SharedCacheMap;
  }
  if ( (_BYTE)v27 )
    goto LABEL_223;
  if ( !FsRtlCheckLockForWriteAccess((PFILE_LOCK)(a3 + 536), Irp) )
  {
    Status = -1073741740;
    goto LABEL_107;
  }
  SharedCacheMap = v140;
  v27 = v121;
  if ( v121 )
    goto LABEL_223;
  v26 = (PVOID *)v122;
  if ( !v122 )
  {
    v40 = Length;
    v43 = FileObject;
    goto LABEL_89;
  }
  if ( EndOffset.QuadPart < 0 )
  {
LABEL_223:
    v40 = Length;
    v43 = FileObject;
    goto LABEL_88;
  }
  v40 = Length;
  v27 = EndOffset.QuadPart + Length;
  if ( v27 > v140.QuadPart )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      v119 = EndOffset.QuadPart + Length;
      *(LARGE_INTEGER *)Retrying = v140;
      PostIrpRoutine = (const CHAR *)a3;
      ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))WPP_SF_qqii)(
        WPP_GLOBAL_Control->AttachedDevice,
        (LARGE_INTEGER)v140.QuadPart,
        (LARGE_INTEGER)EndOffset.QuadPart,
        v7);
    }
    v128 = 1;
    v150->Create.PipeCompletionMode |= 2u;
    *(_DWORD *)(a3 + 160) &= 0xFFBFF7FF;
    v146 = *(const CHAR **)(a3 + 32);
    QuadPart = v146;
    v26 = *(PVOID **)(a3 + 24);
    v149 = v26;
    IoStatus.Pointer = v26;
    v153 = *(LARGE_INTEGER *)(a3 + 40);
    v139 = (_QWORD *)v153.QuadPart;
    SharedCacheMap.QuadPart = EndOffset.QuadPart + Length;
    v140 = SharedCacheMap;
    if ( SharedCacheMap.QuadPart <= (__int64)v26 )
      goto LABEL_81;
    v26 = 0;
    v136 = 0;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 38, WPP_40322347dcd53e0bf93cb1041cae84c9_Traceguids, v7);
      SharedCacheMap = v140;
      v26 = v136;
    }
    if ( v31
      || (*(_DWORD *)(a3 + 164) & 2) == 0
      || (*(_DWORD *)(a3 + 160) & 0x8000000) == 0
      || (*(_DWORD *)(v137.QuadPart + 72) & 2) != 0 )
    {
      if ( !*(_QWORD *)(v7->pFcb[2].Header.ValidDataLength.QuadPart + 400) )
      {
        Status = -1073741822;
        goto LABEL_339;
      }
      if ( ((__int64)v7->ScavengerEntry.List.Flink & 2) != 0 )
      {
        Status = -1073741536;
        goto LABEL_339;
      }
      *(_OWORD *)&v7->MRxContext[2] = 0;
      *(_OWORD *)&v7->WriteOnlyOpenRetryContext = 0;
      v7->ResumeRoutine = 0;
      v41 = (*(__int64 (__fastcall **)(PRX_CONTEXT, LARGE_INTEGER *, PVOID **))(v7->pFcb[2].Header.ValidDataLength.QuadPart
                                                                              + 400))(
              v7,
              &v140,
              &v136);
    }
    else
    {
      if ( !*(_QWORD *)(v7->pFcb[2].Header.ValidDataLength.QuadPart + 392) )
      {
        Status = -1073741822;
        goto LABEL_339;
      }
      if ( ((__int64)v7->ScavengerEntry.List.Flink & 2) != 0 )
      {
        Status = -1073741536;
LABEL_77:
        if ( Status >= 0 )
        {
          if ( SharedCacheMap.QuadPart > (__int64)v26 )
          {
            v26 = (PVOID *)SharedCacheMap.QuadPart;
            v136 = (PVOID *)SharedCacheMap.QuadPart;
          }
          *(_QWORD *)(a3 + 24) = v26;
LABEL_81:
          *(LARGE_INTEGER *)(a3 + 32) = SharedCacheMap;
          if ( SharedCacheMap.QuadPart > (__int64)v26 )
          {
            v42 = *(unsigned int *)(*(_QWORD *)(a3 + 120) + 104LL);
            *(_QWORD *)(a3 + 24) = ~(v42 - 1) & (v42 + SharedCacheMap.QuadPart);
          }
          v43 = FileObject;
          SectionObjectPointer = FileObject->SectionObjectPointer;
          if ( SectionObjectPointer )
          {
            if ( SectionObjectPointer->SharedCacheMap )
            {
              CcSetFileSizes(FileObject, (PCC_FILE_SIZES)(a3 + 24));
              v89 = v149;
              v90 = v146;
              SharedCacheMap = v153;
              v43 = FileObject;
              if ( Status )
              {
                *(_QWORD *)(a3 + 32) = v146;
                *(_QWORD *)(a3 + 24) = v89;
                *(LARGE_INTEGER *)(a3 + 40) = SharedCacheMap;
                SharedCacheMap = (LARGE_INTEGER)FileObject->SectionObjectPointer->SharedCacheMap;
                if ( SharedCacheMap.QuadPart )
                  *(_QWORD *)(SharedCacheMap.QuadPart + 8) = v90;
                goto LABEL_107;
              }
            }
          }
          v40 = Length;
          goto LABEL_87;
        }
LABEL_339:
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 39, WPP_40322347dcd53e0bf93cb1041cae84c9_Traceguids);
        }
        goto LABEL_107;
      }
      *(_OWORD *)&v7->MRxContext[2] = 0;
      *(_OWORD *)&v7->WriteOnlyOpenRetryContext = 0;
      v7->ResumeRoutine = 0;
      v41 = (*(__int64 (__fastcall **)(PRX_CONTEXT, LARGE_INTEGER *, PVOID **))(v7->pFcb[2].Header.ValidDataLength.QuadPart
                                                                              + 392))(
              v7,
              &v140,
              &v136);
    }
    v26 = v136;
    SharedCacheMap = v140;
    Status = v41;
    goto LABEL_77;
  }
  v43 = FileObject;
LABEL_87:
  v27 = 0;
LABEL_88:
  v26 = (PVOID *)v122;
LABEL_89:
  if ( v130 || v126 || ByteOffset.QuadPart != -1 && EndOffset.QuadPart + v40 <= StartOffset.QuadPart )
  {
    v45 = v150;
  }
  else
  {
    v131 = 1;
    v45 = v150;
    v150->Create.PipeCompletionMode |= 4u;
  }
  v46 = (*(_DWORD *)(a3 + 164) & 2) == 0
     || (*(_DWORD *)(a3 + 160) & 0x8000000) == 0
     || (*(_DWORD *)(v137.QuadPart + 72) & 2) != 0;
  if ( !(_BYTE)v26 || (_BYTE)v27 || v31 || v46 )
  {
    if ( v127 )
    {
      v47 = 0;
      v120 = 0;
      v100 = (__int64)v7->RdbssDbgExtension & 0xFFFFFFFD;
      LODWORD(v7->RdbssDbgExtension) = v100;
      LODWORD(v7->RdbssDbgExtension) = v100 | 0x1000;
    }
    else
    {
      v47 = v120;
    }
    *((_DWORD *)&v45->9 + 42) = v40;
    v45->Create.TransportName.Buffer = (wchar_t *)EndOffset.QuadPart;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      *(_QWORD *)Retrying = *((_QWORD *)&v45->9 + 19);
      LODWORD(PostIrpRoutine) = BYTE1(v7->Flags);
      WPP_SF_ddq(
        WPP_GLOBAL_Control->AttachedDevice,
        48,
        WPP_40322347dcd53e0bf93cb1041cae84c9_Traceguids,
        LOBYTE(v7->Flags));
    }
    if ( !v47 )
    {
      v61 = (void *)((__int64)v7->RxDeviceObject | 3);
      *((_QWORD *)&v45->9 + 23) = v61;
      if ( LOBYTE(v7->Flags) )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_16f2bee2656c381c8186d78b34bda825_Traceguids, v61);
        }
        ExSetResourceOwnerPointer(*(PERESOURCE *)(a3 + 8), v61);
        *((_BYTE *)&v45->9 + 176) = 1;
      }
      if ( BYTE1(v7->Flags) )
      {
        RxSetFcbPagingOwnerPointer(a3, *((_QWORD *)&v45->9 + 23), v26, v27);
        *((_BYTE *)&v45->9 + 177) = 1;
      }
    }
    Status = RxLowIoWriteShell(v7, Irp, (PFCB)a3);
    if ( Status == 259 )
    {
      v7 = 0;
      v148 = 0;
      Irp = 0;
    }
  }
  else
  {
    if ( !v43->PrivateCacheMap )
    {
      if ( (v43->Flags & 0x4000) != 0 )
      {
        Status = -1073741528;
        goto LABEL_107;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 40, WPP_40322347dcd53e0bf93cb1041cae84c9_Traceguids, v43, a3);
        v43 = FileObject;
      }
      v97 = (struct _CC_FILE_SIZES *)(a3 + 24);
      v98 = *(_QWORD *)(a3 + 32);
      if ( v98 > *(_QWORD *)(a3 + 24) )
      {
        v99 = *(unsigned int *)(*(_QWORD *)(a3 + 120) + 104LL);
        v97->AllocationSize.QuadPart = ~(v99 - 1) & (v99 + v98);
      }
      CcInitializeCacheMap(v43, v97, 0, &Callbacks, (PVOID)a3);
      LOWORD(v163) = 16;
      HIDWORD(v163) = *(_DWORD *)(v151 + 108);
      v164 = *(_DWORD *)(v151 + 112);
      v165 = 0;
      CcSetReadAheadGranularityEx(FileObject, &v163);
      RxSelectAndSwitchPagingFileObject(a3);
    }
    if ( (BYTE1(v7->RealDevice) & 2) == 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 41, WPP_40322347dcd53e0bf93cb1041cae84c9_Traceguids);
      }
      v62 = Irp;
      IoStatus.Pointer = RxMapUserBuffer(v7, Irp);
      if ( !IoStatus.Pointer )
      {
        Status = -1073741670;
        goto LABEL_107;
      }
      v64 = *(__int64 (__fastcall **)(PRX_CONTEXT, PMRX_SRV_OPEN))(*(_QWORD *)(a3 + 392) + 592LL);
      if ( v64 )
      {
        v65 = v64(v7, v7->pRelevantSrvOpen);
        Status = v65;
        if ( v65 != -1073741822 )
        {
          if ( v65 == -1069481981 )
            goto LABEL_138;
          if ( v65 < 0 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) )
            {
              WPP_SF_qD(
                WPP_GLOBAL_Control->AttachedDevice,
                42,
                WPP_40322347dcd53e0bf93cb1041cae84c9_Traceguids,
                v7->pRelevantSrvOpen,
                v65);
            }
            goto LABEL_107;
          }
        }
      }
      if ( EndOffset.QuadPart > StartOffset.QuadPart )
        CcZeroData(FileObject, &StartOffset, &EndOffset, 1u);
      if ( (BYTE4(WPP_MAIN_CB.Dpc.DpcListEntry.Next) & 8) != 0 )
        McTemplateK0pp_EtwWriteTransfer(v63, CcWriteRequest, &v7->LowIoContext.Flags + 1, v7, FileObject);
      v95 = (v145[9].LowPart & 8) != 0 || v125;
      if ( CcCopyWrite(FileObject, &FileOffset, Length, v95, IoStatus.Pointer) )
      {
        if ( (BYTE4(WPP_MAIN_CB.Dpc.DpcListEntry.Next) & 8) != 0 )
        {
          *(_DWORD *)Retrying = 1;
          PostIrpRoutine = (const CHAR *)FileObject;
          McTemplateK0ppq_EtwWriteTransfer(v96, CcWriteCompletion, &v7->LowIoContext.Flags + 1, v7);
        }
        v62->IoStatus.Status = 0;
        v62->IoStatus.Information = Length;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          *(LARGE_INTEGER *)Retrying = FileOffset;
          PostIrpRoutine = *(const CHAR **)(a3 + 32);
          WPP_SF_qiiL(WPP_GLOBAL_Control->AttachedDevice, 45, v26, FileObject);
        }
        Status = 0;
        goto LABEL_107;
      }
      if ( (BYTE4(WPP_MAIN_CB.Dpc.DpcListEntry.Next) & 8) != 0 )
      {
        *(_DWORD *)Retrying = 0;
        PostIrpRoutine = (const CHAR *)FileObject;
        McTemplateK0ppq_EtwWriteTransfer(v96, CcWriteCompletion, &v7->LowIoContext.Flags + 1, v7);
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 43, WPP_40322347dcd53e0bf93cb1041cae84c9_Traceguids);
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        *(LARGE_INTEGER *)Retrying = FileOffset;
        PostIrpRoutine = *(const CHAR **)(a3 + 32);
        WPP_SF_qiiL(WPP_GLOBAL_Control->AttachedDevice, 44, v26, FileObject);
      }
LABEL_138:
      if ( v128 )
      {
        LOBYTE(v26) = 1;
        RxAcquirePagingIoResource(v7, a3, v26);
        *(LARGE_INTEGER *)(a3 + 32) = v154;
        RxReleasePagingIoResource(v7, a3);
        v101 = FileObject->SectionObjectPointer->SharedCacheMap;
        if ( v101 )
          v101[1] = *(_QWORD *)(a3 + 32);
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 50, WPP_40322347dcd53e0bf93cb1041cae84c9_Traceguids);
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_16f2bee2656c381c8186d78b34bda825_Traceguids);
      }
      if ( !LOBYTE(v7->Flags) )
        goto LABEL_150;
      v57 = *((_QWORD *)&v7->9 + 23);
      if ( v57 )
      {
        _RxReleaseFcbForThread(v7, (PMRX_FCB)a3, v57, v27, PostIrpRoutine, *(ULONG *)Retrying);
        goto LABEL_150;
      }
      v58 = *(_BYTE *)(*(_QWORD *)(a3 + 8) + 26LL) & 0x80;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_16f2bee2656c381c8186d78b34bda825_Traceguids, v58);
      }
      if ( v58 )
      {
        if ( (unsigned __int64)v7 > 0xFFFFFFFFFFFFFFFDuLL )
        {
LABEL_149:
          ExReleaseResourceLite(*(PERESOURCE *)(a3 + 8));
LABEL_150:
          if ( BYTE1(v7->Flags) )
          {
            v91 = *((_QWORD *)&v7->9 + 23);
            if ( v91 )
            {
              BYTE1(v7->Flags) = 0;
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
              {
                WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 21, WPP_16f2bee2656c381c8186d78b34bda825_Traceguids, v91);
              }
              ExReleaseResourceForThreadLite(*(PERESOURCE *)(a3 + 16), v91);
            }
            else
            {
              RxReleasePagingIoResource(v7, a3);
            }
          }
          CurrentIrp = v7->CurrentIrp;
          if ( ((__int64)v7->RdbssDbgExtension & 0x200000) == 0 )
            RxPrePostIrp(v7, v7->CurrentIrp);
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            LODWORD(v119) = BYTE1(v7->RealDevice);
            *(_WORD *)Retrying = LOBYTE(v7->RealDevice);
            ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD))WPP_SF_qqhDq)(
              WPP_GLOBAL_Control->AttachedDevice,
              (LARGE_INTEGER)SharedCacheMap.QuadPart,
              LOBYTE(v7->RealDevice),
              v7->NonPagedFcb,
              CurrentIrp,
              *(_QWORD *)Retrying,
              v119,
              v7);
          }
          RxAddToWorkque(v7, CurrentIrp);
          Status = 259;
          v7 = 0;
          v148 = 0;
          goto LABEL_531;
        }
        if ( *(_DWORD *)(*(_QWORD *)(a3 + 304) + 296LL)
          && (*(_DWORD *)(a3 + 156) & 0x80000) == 0
          && (unsigned __int8)RxIsSafeToProcessBufferingStateChange(v7, a3) )
        {
          RxProcessFcbChangeBufferingStateRequestInternal((PVOID)a3);
        }
      }
      if ( (unsigned __int64)v7 <= 0xFFFFFFFFFFFFFFFDuLL )
        LOBYTE(v7->Flags) = 0;
      goto LABEL_149;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 46, WPP_40322347dcd53e0bf93cb1041cae84c9_Traceguids);
    }
    Status = -1073741637;
  }
LABEL_107:
  if ( v123 )
    goto LABEL_138;
LABEL_108:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      49,
      WPP_40322347dcd53e0bf93cb1041cae84c9_Traceguids,
      (unsigned int)Status);
  }
  if ( !v121 )
  {
    if ( Status < 0 )
      goto LABEL_531;
    if ( v120 != v121 && (FileObject->Flags & 2) != 0 )
      FileObject->CurrentByteOffset.QuadPart = EndOffset.QuadPart + Irp->IoStatus.Information;
  }
  if ( Status >= 0 && Status != 259 )
  {
    v49 = 0;
    if ( v31 )
    {
      v48 = FileObject->SectionObjectPointer;
      if ( v48 )
      {
        if ( v48->SharedCacheMap )
          v49 = 1;
      }
    }
    v50 = EndOffset;
    v51 = v7->CurrentIrp;
    v52 = v51->Tail.Overlay.CurrentStackLocation->FileObject;
    pFcb = (struct _CC_FILE_SIZES *)v7->pFcb;
    if ( !v121 )
      v52->Flags |= 0x1000u;
    if ( v128 )
      v52->Flags |= 0x2000u;
    if ( v131 )
    {
      v54.QuadPart = v50.QuadPart + v51->IoStatus.Information;
      FileSize = pFcb[1].FileSize;
      if ( FileSize.QuadPart >= v54.QuadPart )
      {
        pFcb[1].ValidDataLength = v54;
        v56 = v54;
      }
      else
      {
        pFcb[1].ValidDataLength = FileSize;
        v56 = FileSize;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD))WPP_SF_qqq)(
          WPP_GLOBAL_Control->AttachedDevice,
          14,
          WPP_40322347dcd53e0bf93cb1041cae84c9_Traceguids,
          (LARGE_INTEGER)FileSize.QuadPart,
          (LARGE_INTEGER)v56.QuadPart,
          (LARGE_INTEGER)v54.QuadPart);
      }
      if ( v49 )
        CcSetFileSizes(v52, pFcb + 1);
    }
  }
LABEL_531:
  if ( Status != 259 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_16f2bee2656c381c8186d78b34bda825_Traceguids);
    }
    if ( !LOBYTE(v7->Flags) )
      goto LABEL_542;
    v102 = *((_QWORD *)&v7->9 + 23);
    if ( v102 )
    {
      v111 = *(_DWORD *)(*(_QWORD *)(a3 + 304) + 296LL);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_qqq(
          WPP_GLOBAL_Control->AttachedDevice,
          14,
          WPP_16f2bee2656c381c8186d78b34bda825_Traceguids,
          v7,
          a3,
          *((_QWORD *)&v7->9 + 23));
      }
      if ( v111
        && ExIsResourceAcquiredExclusiveLite(*(PERESOURCE *)(a3 + 8))
        && (unsigned __int8)RxIsSafeToProcessBufferingStateChange(v7, a3) )
      {
        RxProcessFcbChangeBufferingStateRequestInternal((PVOID)a3);
      }
      LOBYTE(v7->Flags) = 0;
      ExReleaseResourceForThreadLite(*(PERESOURCE *)(a3 + 8), v102);
      goto LABEL_542;
    }
    v103 = *(_BYTE *)(*(_QWORD *)(a3 + 8) + 26LL) & 0x80;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        13,
        WPP_16f2bee2656c381c8186d78b34bda825_Traceguids,
        (unsigned __int8)v103);
    }
    if ( (_BYTE)v103 )
    {
      if ( (unsigned __int64)v7 > 0xFFFFFFFFFFFFFFFDuLL )
      {
LABEL_541:
        ExReleaseResourceLite(*(PERESOURCE *)(a3 + 8));
LABEL_542:
        if ( BYTE1(v7->Flags) )
        {
          v110 = *((_QWORD *)&v7->9 + 23);
          if ( v110 )
          {
            BYTE1(v7->Flags) = 0;
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
            {
              WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 21, WPP_16f2bee2656c381c8186d78b34bda825_Traceguids, v110);
            }
            ExReleaseResourceForThreadLite(*(PERESOURCE *)(a3 + 16), v110);
          }
          else
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
            {
              WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 20, WPP_16f2bee2656c381c8186d78b34bda825_Traceguids);
            }
            BYTE1(v7->Flags) = 0;
            ExReleaseResourceLite(*(PERESOURCE *)(a3 + 16));
          }
        }
        goto LABEL_543;
      }
      if ( *(_DWORD *)(*(_QWORD *)(a3 + 304) + 296LL)
        && (*(_DWORD *)(a3 + 156) & 0x80000) == 0
        && (unsigned __int8)RxIsSafeToProcessBufferingStateChange(v7, a3) )
      {
        RxProcessFcbChangeBufferingStateRequestInternal((PVOID)a3);
      }
    }
    if ( (unsigned __int64)v7 <= 0xFFFFFFFFFFFFFFFDuLL )
      LOBYTE(v7->Flags) = 0;
    goto LABEL_541;
  }
LABEL_543:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      51,
      WPP_40322347dcd53e0bf93cb1041cae84c9_Traceguids,
      (unsigned int)Status);
  }
  if ( Status != 259 && Status && v121 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_qqD(WPP_GLOBAL_Control->AttachedDevice, 52, WPP_40322347dcd53e0bf93cb1041cae84c9_Traceguids, a3);
    }
    _InterlockedIncrement(&LDWCount);
    WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink = (struct _LIST_ENTRY *)MEMORY[0xFFFFF78000000014];
  }
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x140004ac0  mov     r11, rsp
0x140004ac3  push    rbx
0x140004ac4  push    rsi
0x140004ac5  push    rdi
0x140004ac6  push    r12
0x140004ac8  push    r13
0x140004aca  push    r14
0x140004acc  push    r15
0x140004ace  sub     rsp, 190h
0x140004ad5  mov     rax, cs:__security_cookie
0x140004adc  xor     rax, rsp
0x140004adf  mov     [rsp+1C8h+var_48], rax
0x140004ae7  mov     rbx, r9
0x140004aea  mov     [rsp+1C8h+var_F0], rbx
0x140004af2  mov     rdi, r8
0x140004af5  mov     r8, rdx
0x140004af8  mov     [r11-108h], rdx
0x140004aff  mov     rsi, rcx
0x140004b02  mov     [r11-0D8h], rcx
0x140004b09  mov     [r11-78h], rdx
0x140004b0d  mov     [rsp+1C8h+var_B8], rdi
0x140004b15  mov     [rsp+1C8h+var_70], rbx
0x140004b1d  mov     r14, [rdx+0B8h]
0x140004b24  mov     rax, [r14+30h]
0x140004b28  mov     [rsp+1C8h+FileObject], rax
0x140004b2d  mov     r13, [rcx+50h]
0x140004b31  xor     r12d, r12d
0x140004b34  mov     [r11-0E0h], r12
0x140004b3b  mov     [r11-148h], r12
0x140004b42  mov     [r11-118h], r12
0x140004b49  mov     [r11-0F8h], r12
0x140004b50  xor     eax, eax
0x140004b52  mov     [r11-58h], rax
0x140004b56  mov     [r11-50h], eax
0x140004b5a  mov     [r11-4Ch], ax
0x140004b5f  mov     rax, [rdi+78h]
0x140004b63  mov     [rsp+1C8h+var_C0], rax
0x140004b6b  movzx   eax, byte ptr [rax+4Dh]
0x140004b6f  test    al, al
0x140004b71  jz      loc_1400074DF
0x140004b77  xor     r11b, r11b
0x140004b7a  mov     [rsp+1C8h+var_166], r11b
0x140004b7f  cmp     al, 4
0x140004b81  jz      loc_1400074DF
0x140004b87  mov     edx, [rdx+10h]
0x140004b8a  lea     r9, [rcx+78h]
0x140004b8e  test    dl, 2
0x140004b91  jnz     short loc_140004BAE
0x140004b93  mov     [rsp+1C8h+var_167], r12b
0x140004b98  mov     [rsp+1C8h+var_138], r9
0x140004ba0  mov     eax, [r9]
0x140004ba3  test    al, 2
0x140004ba5  jnz     short loc_140004BB3
0x140004ba7  mov     [rsp+1C8h+var_15D], r12b
0x140004bac  jmp     short loc_140004BC0
0x140004bae  mov     [rsp+1C8h+var_167], 1
0x140004bb3  mov     [rsp+1C8h+var_15D], 1
0x140004bb8  mov     [rsp+1C8h+var_138], r9
0x140004bc0  and     dl, 1
0x140004bc3  mov     dword ptr [rsp+1C8h+var_128], edx
0x140004bca  mov     r10d, [r9]
0x140004bcd  and     r10d, 1000h
0x140004bd4  mov     dword ptr [rsp+1C8h+var_B0], r10d
0x140004bdc  setz    [rsp+1C8h+var_168]
0x140004be1  lea     r15, WPP_GLOBAL_Control
0x140004be8  mov     rcx, cs:WPP_GLOBAL_Control
0x140004bef  cmp     rcx, r15
0x140004bf2  jnz     loc_140007347
0x140004bf8  mov     [rsi+0A8h], r12w
0x140004c00  mov     rbx, [r14+18h]
0x140004c04  mov     qword ptr [rsp+1C8h+FileOffset], rbx
0x140004c0c  mov     qword ptr [rsp+1C8h+EndOffset], rbx
0x140004c14  mov     r14d, [r14+8]
0x140004c18  mov     [rsp+1C8h+Length], r14d
0x140004c1d  test    dword ptr [r9], 200h
0x140004c24  jz      loc_1400072B3
0x140004c2a  mov     r10, [rsp+1C8h+var_F0]
0x140004c32  test    r11b, r11b
0x140004c35  jnz     loc_140007357
0x140004c3b  cmp     [r8+70h], r12
0x140004c3f  jz      loc_1400074EC
0x140004c45  mov     [rsp+1C8h+var_D0], r14
0x140004c4d  mov     rax, 7FFFFFFFFFFFFFFFh
0x140004c57  sub     rax, qword ptr [rsp+1C8h+EndOffset]
0x140004c5f  cmp     rax, r14
0x140004c62  jl      loc_140007587
0x140004c68  mov     [rsp+1C8h+var_C8], rsi
0x140004c70  mov     rax, [rsp+1C8h+var_C0]
0x140004c78  mov     [rsp+1C8h+var_98], rax
0x140004c80  mov     [rsp+1C8h+var_100], r14d
0x140004c88  mov     r13, [rsp+1C8h+FileObject]
0x140004c8d  mov     [rsp+1C8h+var_A0], r13
0x140004c95  test    r10, r10
0x140004c98  jz      loc_1400074FB
0x140004c9e  mov     rcx, [r10+20h]
0x140004ca2  mov     [rsp+1C8h+var_80], rcx
0x140004caa  mov     [rsp+1C8h+var_130], rcx
0x140004cb2  test    dl, dl
0x140004cb4  jz      loc_140007409
0x140004cba  mov     r14d, 0C000000Dh
0x140004cc0  mov     [rsp+1C8h+var_164], r14d
0x140004cc5  mov     [rsp+1C8h+var_A8], r12
0x140004ccd  mov     [rsp+1C8h+var_68], r12
0x140004cd5  xor     al, al
0x140004cd7  mov     [rsp+1C8h+var_15F], al
0x140004cdb  mov     [rsp+1C8h+var_140], al
0x140004ce2  mov     [rsp+1C8h+var_15A], al
0x140004ce6  mov     [rsp+1C8h+var_15B], al
0x140004cea  mov     [rsp+1C8h+var_152], al
0x140004cee  mov     [rsp+1C8h+var_151], al
0x140004cf2  mov     [rsp+1C8h+var_15C], al
0x140004cf6  mov     [rsp+1C8h+var_13F], dl
0x140004cfd  mov     [rsp+1C8h+var_60], rbx
0x140004d05  lea     r8, [rsi+208h]; LowIoContext
0x140004d0c  mov     edx, 1; Operation
0x140004d11  mov     rcx, rsi; RxContext
0x140004d14  call    RxInitializeLowIoContext
0x140004d19  nop
0x140004d1a  mov     rcx, cs:WPP_GLOBAL_Control
0x140004d21  cmp     rcx, r15
0x140004d24  jz      short loc_140004D31
0x140004d26  mov     eax, [rcx+2Ch]
0x140004d29  test    al, 10h
0x140004d2b  jnz     loc_14000667F
0x140004d31  cmp     [rsp+1C8h+var_167], 0
0x140004d36  jnz     loc_140005B74
0x140004d3c  mov     rcx, [rsp+1C8h+var_138]
0x140004d44  mov     eax, [rcx]
0x140004d46  mov     r13, [rsp+1C8h+Irp]
0x140004d4e  test    al, 2
0x140004d50  jz      loc_140005B3A
0x140004d56  mov     r8d, 2; Mode
0x140004d5c  xor     r9d, r9d; LineNumber
0x140004d5f  mov     rdx, rsi; RxContext
0x140004d62  mov     rcx, rdi; Fcb
0x140004d65  call    __RxAcquireFcb
0x140004d6a  mov     r14d, eax
0x140004d6d  mov     [rsp+1C8h+var_164], eax
0x140004d71  cmp     eax, 0C0000055h
0x140004d76  jz      loc_140005DC9
0x140004d7c  test    eax, eax
0x140004d7e  jnz     loc_1400065F4
0x140004d84  mov     r8d, [r13+10h]
0x140004d88  movzx   edx, r8b
0x140004d8c  and     dl, 1
0x140004d8f  and     r8d, 2
0x140004d93  xor     cl, cl
0x140004d95  mov     dword ptr [rsp+1C8h+var_120], ecx
0x140004d9c  mov     [rsp+1C8h+var_154], cl
0x140004da0  mov     rax, qword ptr [rsp+1C8h+EndOffset]
0x140004da8  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140004dac  jz      loc_1400056F3
0x140004db2  add     rax, [rsp+1C8h+var_D0]
0x140004dba  cmp     rax, [rdi+28h]
0x140004dbe  jg      loc_1400056F3
0x140004dc4  mov     r9, [rsp+1C8h+var_130]
0x140004dcc  test    dl, dl
0x140004dce  jz      loc_140005609
0x140004dd4  mov     r10, [rsp+1C8h+FileObject]
0x140004dd9  mov     rax, [r10+28h]
0x140004ddd  movzx   ecx, cl
0x140004de0  cmp     qword ptr [rax], 0
0x140004de4  mov     eax, 1
0x140004de9  cmovnz  ecx, eax
0x140004dec  mov     dword ptr [rsp+1C8h+var_120], ecx
0x140004df3  mov     [rsp+1C8h+var_154], cl
0x140004df7  test    dl, dl
0x140004df9  jz      loc_1400055A8
0x140004dff  mov     r8, cs:WPP_GLOBAL_Control
0x140004e06  cmp     r8, r15
0x140004e09  jz      short loc_140004E17
0x140004e0b  mov     eax, [r8+2Ch]
0x140004e0f  test    al, 10h
0x140004e11  jnz     loc_1400066D5
0x140004e17  test    cl, cl
0x140004e19  jnz     loc_1400059CD
0x140004e1f  lea     rcx, [rdi+58h]; Oplock
0x140004e23  mov     [rsp+1C8h+PostIrpRoutine], r12; FileName
0x140004e28  xor     r9d, r9d; CompletionRoutine
0x140004e2b  mov     r8, rsi; Context
0x140004e2e  mov     rdx, r13; Irp
0x140004e31  call    cs:__imp_FsRtlCheckOplock
0x140004e38  nop     dword ptr [rax+rax+00h]
0x140004e3d  mov     rcx, [rsp+1C8h+var_D0]
0x140004e45  add     rcx, qword ptr [rsp+1C8h+EndOffset]
0x140004e4d  cmp     rcx, [rdi+28h]
0x140004e51  jg      loc_14000604A
0x140004e57  mov     r13d, dword ptr [rsp+1C8h+var_128]
0x140004e5f  test    r13b, r13b
0x140004e62  jz      loc_14000563D
0x140004e68  mov     r10, [rsp+1C8h+FileObject]
0x140004e6d  mov     rax, [r10+28h]
0x140004e71  cmp     qword ptr [rax], 0
0x140004e75  jnz     loc_140005DF4
0x140004e7b  lea     rcx, [rdi+218h]; FileLock
0x140004e82  mov     rdx, [rsp+1C8h+Irp]; Irp
0x140004e8a  call    cs:__imp_FsRtlCheckLockForWriteAccess
0x140004e91  nop     dword ptr [rax+rax+00h]
0x140004e96  test    al, al
0x140004e98  jz      loc_14000649E
0x140004e9e  xor     edx, edx
0x140004ea0  lea     rcx, RxPowerContext
0x140004ea7  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140004eae  nop     dword ptr [rax+rax+00h]
0x140004eb3  or      byte ptr [rdi+11Ah], 80h
0x140004eba  movzx   edx, byte ptr [rdi+11Ah]
0x140004ec1  test    dl, 2
0x140004ec4  jz      short loc_140004F36
0x140004ec6  mov     rax, [rdi+190h]
0x140004ecd  test    dword ptr [rax+150h], 100h
0x140004ed7  jz      short loc_140004F36
0x140004ed9  mov     rax, [rdi+78h]
0x140004edd  cmp     byte ptr [rax+4Dh], 0
0x140004ee1  jnz     short loc_140004F36
0x140004ee3  mov     ecx, 0EC21h
0x140004ee8  cmp     [rdi], cx
0x140004eeb  jz      short loc_140004F36
0x140004eed  mov     rax, [rax+20h]
0x140004ef1  mov     ecx, [rax+60h]
0x140004ef4  test    cl, cl
0x140004ef6  js      short loc_140004F36
0x140004ef8  mov     [rsp+1C8h+var_15E], 2
0x140004efd  and     dl, 0FDh
0x140004f00  mov     [rdi+11Ah], dl
0x140004f06  or      dl, 4
0x140004f09  mov     [rdi+11Ah], dl
0x140004f0f  mov     rcx, [rdi+8]; Resource
0x140004f13  call    cs:__imp_ExIsResourceAcquiredSharedLite
0x140004f1a  nop     dword ptr [rax+rax+00h]
0x140004f1f  movzx   ecx, byte ptr [rdi+11Bh]
0x140004f26  test    al, al
0x140004f28  jnz     loc_1400058FA
0x140004f2e  test    cl, cl
0x140004f30  jz      loc_140006D95
0x140004f36  xor     edx, edx
0x140004f38  lea     rcx, RxPowerContext
0x140004f3f  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140004f46  nop     dword ptr [rax+rax+00h]
0x140004f4b  mov     rdx, [rsp+1C8h+var_130]
0x140004f53  test    r13b, r13b
0x140004f56  jz      loc_14000577A
0x140004f5c  movzx   r8d, [rsp+1C8h+var_167]
0x140004f62  test    r8b, r8b
0x140004f65  jnz     loc_1400057A9
0x140004f6b  mov     rax, [rdi+28h]
0x140004f6f  mov     qword ptr [rsp+1C8h+StartOffset], rax
0x140004f77  mov     rcx, [rdi+20h]
0x140004f7b  mov     [rsp+1C8h+var_118], rcx
0x140004f83  test    r8b, r8b
0x140004f86  jnz     loc_140005D10
0x140004f8c  call    cs:__imp_IoGetTopLevelIrp
0x140004f93  nop     dword ptr [rax+rax+00h]
0x140004f98  cmp     rax, 2
0x140004f9c  jz      loc_140005C32
0x140004fa2  mov     rdx, [rsp+1C8h+var_118]
0x140004faa  mov     rax, [rsp+1C8h+Irp]
0x140004fb2  mov     eax, [rax+10h]
0x140004fb5  test    al, 40h
0x140004fb7  jnz     loc_140005D84
0x140004fbd  mov     rcx, [rsp+1C8h+var_138]
0x140004fc5  cmp     [rsp+1C8h+var_152], 0
0x140004fca  jnz     short loc_140004FFB
0x140004fcc  cmp     [rsp+1C8h+var_15C], 0
0x140004fd1  jnz     loc_140006CB7
0x140004fd7  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x140004fdb  jz      loc_140005673
0x140004fe1  mov     eax, [rsp+1C8h+Length]
0x140004fe5  add     rax, qword ptr [rsp+1C8h+EndOffset]
0x140004fed  cmp     rax, qword ptr [rsp+1C8h+StartOffset]
0x140004ff5  jg      loc_140005673
0x140004ffb  movzx   ecx, [rsp+1C8h+var_168]
0x140005000  mov     [rsp+1C8h+var_160], cl
0x140005004  mov     [rsp+1C8h+var_168], cl
0x140005008  movzx   r9d, [rsp+1C8h+var_167]
0x14000500e  mov     [rsp+1C8h+var_A8], rdx
0x140005016  mov     rax, qword ptr [rsp+1C8h+StartOffset]
0x14000501e  mov     [rsp+1C8h+var_68], rax
0x140005026  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x14000502a  jnz     short loc_14000503C
0x14000502c  mov     qword ptr [rsp+1C8h+EndOffset], rdx
0x140005034  mov     qword ptr [rsp+1C8h+FileOffset], rdx
0x14000503c  test    r9b, r9b
0x14000503f  jnz     loc_1400059BF
0x140005045  lea     rcx, [rdi+218h]; FileLock
0x14000504c  mov     rdx, [rsp+1C8h+Irp]; Irp
0x140005054  call    cs:__imp_FsRtlCheckLockForWriteAccess
0x14000505b  nop     dword ptr [rax+rax+00h]
0x140005060  test    al, al
0x140005062  jz      loc_140005DB9
0x140005068  mov     rdx, [rsp+1C8h+var_118]
0x140005070  movzx   r9d, [rsp+1C8h+var_167]
0x140005076  test    r9b, r9b
0x140005079  jnz     loc_1400059BF
0x14000507f  movzx   r8d, [rsp+1C8h+var_166]
0x140005085  test    r8b, r8b
0x140005088  jz      loc_140006DDD
0x14000508e  mov     r8, qword ptr [rsp+1C8h+EndOffset]
0x140005096  test    r8, r8
0x140005099  js      loc_1400059BF
0x14000509f  mov     ecx, [rsp+1C8h+Length]
  ... truncated ...
```
