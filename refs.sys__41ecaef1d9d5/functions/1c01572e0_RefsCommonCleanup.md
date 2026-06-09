# RefsCommonCleanup

- ea: `0x1c01572e0`
- end: `0x1c015a485`
- name: `RefsCommonCleanup`
- size: `12709`
- prototype: `__int64 __fastcall(PVOID Context)`
- caller_count: `2`
- callee_count: `60`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x1c0002e00`
- `0x1c0008060`

## callees

- `0x1c000193c`
- `0x1c0001af8`
- `0x1c0002e44`
- `0x1c0002ef8`
- `0x1c0002f20`
- `0x1c00030b0`
- `0x1c0003280`
- `0x1c0003658`
- `0x1c0003a70`
- `0x1c0003eb4`
- `0x1c0003fb0`
- `0x1c0004300`
- `0x1c00045c4`
- `0x1c00049a0`
- `0x1c0005768`
- `0x1c0005818`
- `0x1c000f770`
- `0x1c0013f90`
- `0x1c003af60`
- `0x1c003b27c`
- `0x1c003f35c`
- `0x1c0063db0`
- `0x1c0067040`
- `0x1c0068168`
- `0x1c0068960`
- `0x1c00689d4`
- `0x1c006af80`
- `0x1c00ad438`
- `0x1c00b0cd0`
- `0x1c00b3368`
- `0x1c014d190`
- `0x1c014fe2c`
- `0x1c0151130`
- `0x1c015527c`
- `0x1c01572e0`
- `0x1c015a48c`
- `0x1c015a4cc`
- `0x1c015a550`
- `0x1c015a584`
- `0x1c015ac58`
- `0x1c015b2b8`
- `0x1c015dfe8`
- `0x1c015e134`
- `0x1c016154c`
- `0x1c01632d4`
- `0x1c01634c8`
- `0x1c0165b54`
- `0x1c0165d18`
- `0x1c0168afc`
- `0x1c016d3c4`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x1c015a055`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c015a084`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c017e7ba`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c017e7e9`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c015a055`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c015a084`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c017e7ba`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c017e7e9`
- `ntoskrnl!FsRtlOplockIsFastIoPossible` at `0x1c015867f`
- `ntoskrnl!FsRtlOplockIsFastIoPossible` at `0x1c015867f`
- `ntoskrnl!ExAcquireFastMutex` at `0x1c0159cbf`
- `ntoskrnl!ExAcquireFastMutex` at `0x1c015a25b`
- `ntoskrnl!ExAcquireFastMutex` at `0x1c0159cbf`
- `ntoskrnl!ExAcquireFastMutex` at `0x1c015a25b`
- `ntoskrnl!ExReleaseFastMutex` at `0x1c0159cfd`
- `ntoskrnl!ExReleaseFastMutex` at `0x1c015a297`
- `ntoskrnl!ExReleaseFastMutex` at `0x1c0159cfd`
- `ntoskrnl!ExReleaseFastMutex` at `0x1c015a297`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1c0159fe2`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1c017e748`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1c0159fe2`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1c017e748`
- `ntoskrnl!FsRtlCheckOplockEx` at `0x1c0157b90`
- `ntoskrnl!FsRtlCheckOplockEx` at `0x1c0159c87`
- `ntoskrnl!FsRtlCheckOplockEx` at `0x1c0157b90`
- `ntoskrnl!FsRtlCheckOplockEx` at `0x1c0159c87`
- `ntoskrnl!FsRtlCheckOplock` at `0x1c0158121`
- `ntoskrnl!FsRtlCheckOplock` at `0x1c01585f3`
- `ntoskrnl!FsRtlCheckOplock` at `0x1c0158121`
- `ntoskrnl!FsRtlCheckOplock` at `0x1c01585f3`
- `ntoskrnl!KeBugCheckEx` at `0x1c0157d17`
- `ntoskrnl!KeBugCheckEx` at `0x1c0157d17`
- `ntoskrnl!MmCanFileBeTruncated` at `0x1c015926c`
- `ntoskrnl!MmCanFileBeTruncated` at `0x1c015926c`
- `ntoskrnl!MmFlushImageSection` at `0x1c01577d5`
- `ntoskrnl!MmFlushImageSection` at `0x1c015799f`
- `ntoskrnl!MmFlushImageSection` at `0x1c01577d5`
- `ntoskrnl!MmFlushImageSection` at `0x1c015799f`
- `ntoskrnl!FsRtlNotifyFilterChangeDirectory` at `0x1c01578c5`
- `ntoskrnl!FsRtlNotifyFilterChangeDirectory` at `0x1c01578c5`
- `ntoskrnl!FsRtlNotifyCleanup` at `0x1c0158178`
- `ntoskrnl!FsRtlNotifyCleanup` at `0x1c0158178`
- `ntoskrnl!FsRtlFastUnlockAll` at `0x1c0158646`
- `ntoskrnl!FsRtlFastUnlockAll` at `0x1c0158646`
- `ntoskrnl!IoGetRequestorProcess` at `0x1c0158625`
- `ntoskrnl!IoGetRequestorProcess` at `0x1c0158625`
- `ntoskrnl!IoGetActivityIdThread` at `0x1c0159e8b`
- `ntoskrnl!IoGetActivityIdThread` at `0x1c0159e8b`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1c0159e09`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1c0159e09`
- `ntoskrnl!FsRtlHeatLogIo` at `0x1c0159e4f`
- `ntoskrnl!FsRtlHeatLogIo` at `0x1c0159e4f`
- `ntoskrnl!MmForceSectionClosed` at `0x1c0159f53`
- `ntoskrnl!MmForceSectionClosed` at `0x1c0159f53`
- `ntoskrnl!IoRemoveShareAccess` at `0x1c0159f71`
- `ntoskrnl!IoRemoveShareAccess` at `0x1c0159f71`
- `ntoskrnl!FsRtlNotifyVolumeEvent` at `0x1c015a0b3`
- `ntoskrnl!FsRtlNotifyVolumeEvent` at `0x1c017e81b`
- `ntoskrnl!FsRtlNotifyVolumeEvent` at `0x1c015a0b3`
- `ntoskrnl!FsRtlNotifyVolumeEvent` at `0x1c017e81b`
- `ntoskrnl!IoRaiseInformationalHardError` at `0x1c015a284`
- `ntoskrnl!IoRaiseInformationalHardError` at `0x1c015a284`

## pseudocode

```c
__int64 __fastcall RefsCommonCleanup(char *Context, IRP *a2)
{
  PVOID v3; // r14
  struct _FILE_OBJECT *v4; // r15
  unsigned int v5; // eax
  __int64 v6; // r8
  char v7; // bl
  __int64 v8; // rsi
  __int64 v9; // r8
  int v10; // ecx
  char v11; // bl
  char v12; // si
  int v13; // eax
  char *v14; // r15
  __int64 v15; // rbx
  __int64 v16; // rdx
  __int64 v17; // r8
  _DWORD *v18; // r9
  __int64 v19; // r8
  __int64 v20; // r13
  __int64 *v21; // rsi
  __int64 v22; // r8
  _DWORD *v23; // r9
  int v24; // eax
  int v25; // eax
  char IsLinkDeleteable; // al
  __int64 v27; // rdx
  __int64 v28; // rax
  __int64 v29; // r10
  __int64 v30; // rsi
  char v31; // bl
  int v32; // eax
  __int64 v33; // rcx
  char v34; // si
  __int64 v35; // r14
  __int64 v36; // rcx
  int v37; // ecx
  int v38; // eax
  int v39; // eax
  __int64 v40; // r9
  char v41; // si
  _WORD *v42; // r13
  struct _FILE_OBJECT *v43; // r12
  int v44; // edx
  int v45; // eax
  unsigned int v46; // ecx
  PFILE_OBJECT v47; // r12
  __int64 v48; // r13
  __int64 v49; // rdx
  int v50; // eax
  char v51; // al
  int v52; // r8d
  char v53; // al
  __int64 v54; // r8
  int v55; // ecx
  int v56; // eax
  int v57; // eax
  PFILE_OBJECT v58; // rcx
  __int64 v59; // rbx
  _DWORD *v60; // r14
  char v61; // al
  int v62; // ecx
  char *i; // rcx
  __int64 *v64; // rsi
  __int64 v65; // rcx
  _DWORD *v66; // rsi
  int v67; // ecx
  int v68; // edx
  __int64 v69; // r8
  int v70; // ecx
  int v71; // eax
  int v72; // eax
  IRP *v73; // rsi
  struct _KPROCESS *RequestorProcess; // rax
  __int64 v75; // rax
  int v76; // edx
  char v77; // al
  char v78; // si
  bool v79; // cl
  PFILE_OBJECT v80; // rcx
  __int64 v81; // r8
  __int64 v82; // rcx
  int v83; // edx
  char v84; // r13
  __int64 v85; // r8
  int v86; // r8d
  char v87; // r13
  __int64 v88; // r8
  __int64 NextParentLcb; // rax
  char *j; // rcx
  __int64 *v91; // rsi
  __int64 v92; // rcx
  _DWORD *v93; // rsi
  int v94; // eax
  _DWORD *v95; // rsi
  __int64 v96; // r8
  PFILE_OBJECT v97; // rcx
  __int64 v98; // rcx
  PFILE_OBJECT v99; // rcx
  int v100; // eax
  PFILE_OBJECT v101; // rcx
  int v102; // edx
  PFILE_OBJECT v103; // rcx
  __int64 v104; // r8
  int v105; // ecx
  __int64 v106; // rdx
  __int64 v107; // rax
  __int64 v108; // r9
  int v109; // ecx
  __int64 v110; // rbx
  __int64 v111; // rax
  int v112; // eax
  __int64 v113; // rax
  int v114; // esi
  int v115; // eax
  int v116; // r12d
  __int64 v117; // r9
  __int64 v118; // r8
  int v119; // edx
  int v120; // eax
  int v121; // edx
  int v122; // ecx
  int v123; // ecx
  int v124; // eax
  int v125; // edx
  ULONG v126; // ecx
  char v127; // r12
  __int64 v128; // rax
  __int64 v129; // rcx
  __int64 NextChildScb; // rax
  volatile signed __int32 *v131; // rcx
  _DWORD *v132; // rsi
  int v133; // eax
  PVOID *v134; // rcx
  bool v135; // r13
  ULONG v136; // r8d
  char *v137; // rbx
  bool v138; // r12
  char *v139; // rbx
  char *v140; // rbx
  int v141; // eax
  _BYTE *v142; // rax
  __int64 v143; // rax
  _OWORD *ActivityIdThread; // rax
  __int64 v145; // rbx
  SECTION_OBJECT_POINTERS *v146; // rcx
  __int64 v147; // rbx
  int v148; // eax
  __int64 v149; // rdx
  __int64 v150; // rcx
  _DWORD *v151; // r12
  __int64 v152; // rcx
  NTSTATUS v153; // esi
  char *v154; // rbx
  int WatchTree; // [rsp+20h] [rbp-318h]
  int v157; // [rsp+60h] [rbp-2D8h] BYREF
  __int16 v158; // [rsp+64h] [rbp-2D4h]
  int v159; // [rsp+68h] [rbp-2D0h]
  NTSTATUS Status; // [rsp+6Ch] [rbp-2CCh]
  char *v161; // [rsp+70h] [rbp-2C8h]
  char v162; // [rsp+78h] [rbp-2C0h] BYREF
  char v163[7]; // [rsp+79h] [rbp-2BFh] BYREF
  int v164[2]; // [rsp+80h] [rbp-2B8h]
  PFILE_OBJECT FileObject; // [rsp+88h] [rbp-2B0h]
  __int64 v166; // [rsp+90h] [rbp-2A8h] BYREF
  PIRP Irp; // [rsp+98h] [rbp-2A0h]
  PVOID FsContext; // [rsp+A0h] [rbp-298h] BYREF
  char *v169; // [rsp+A8h] [rbp-290h] BYREF
  int v170[2]; // [rsp+B0h] [rbp-288h] BYREF
  bool v171; // [rsp+B8h] [rbp-280h]
  __int16 v172; // [rsp+BCh] [rbp-27Ch]
  struct _FILE_OBJECT *v173; // [rsp+C0h] [rbp-278h]
  char *v174; // [rsp+C8h] [rbp-270h]
  __int64 *v175; // [rsp+D0h] [rbp-268h] BYREF
  char v176; // [rsp+D8h] [rbp-260h] BYREF
  char v177; // [rsp+D9h] [rbp-25Fh] BYREF
  char v178; // [rsp+DAh] [rbp-25Eh] BYREF
  unsigned int v179; // [rsp+DCh] [rbp-25Ch]
  PIRP v180; // [rsp+E0h] [rbp-258h]
  int v181; // [rsp+E8h] [rbp-250h]
  __int64 v182; // [rsp+F0h] [rbp-248h]
  __int64 v183; // [rsp+F8h] [rbp-240h] BYREF
  __int64 v184; // [rsp+100h] [rbp-238h]
  __int64 v185; // [rsp+108h] [rbp-230h] BYREF
  union _LARGE_INTEGER *v186; // [rsp+110h] [rbp-228h]
  int v187; // [rsp+118h] [rbp-220h]
  char *v188; // [rsp+120h] [rbp-218h]
  __int64 v189; // [rsp+128h] [rbp-210h] BYREF
  char *v193; // [rsp+140h] [rbp-1F8h]
  __int64 v194; // [rsp+148h] [rbp-1F0h]
  _BYTE v195[24]; // [rsp+1F0h] [rbp-148h] BYREF
  __int128 v196; // [rsp+208h] [rbp-130h] BYREF
  __int128 v197; // [rsp+218h] [rbp-120h] BYREF
  __int64 v198; // [rsp+228h] [rbp-110h]
  _BYTE v199[208]; // [rsp+230h] [rbp-108h] BYREF

  Irp = a2;
  v3 = Context;
  v161 = Context;
  v180 = a2;
  Status = 0;
  *(_QWORD *)v170 = 0;
  v169 = 0;
  v166 = 0;
  FsContext = 0;
  v175 = 0;
  v185 = 0;
  v182 = 0;
  v184 = 0;
  memset(v199, 0, sizeof(v199));
  v186 = 0;
  v189 = 0;
  v162 = 0;
  v172 = 0;
  v157 = 0;
  a2->IoStatus.Information = 2;
  v4 = a2->Tail.Overlay.CurrentStackLocation->FileObject;
  FileObject = v4;
  v173 = v4;
  v5 = RefsDecodeFileObject(
         (_DWORD)v3,
         (_DWORD)v4,
         (unsigned int)v170,
         (unsigned int)&v169,
         (__int64)&v166,
         (__int64)&FsContext,
         0);
  v179 = v5;
  if ( ((v5 - 1) & 0xFFFFFFFB) != 0 )
  {
    v7 = (BYTE1(v157) ^ (*((_DWORD *)FsContext + 1) >> 3)) & 1 ^ BYTE1(v157);
    *((_DWORD *)v3 + 50) = *((_DWORD *)FsContext + 21);
    v8 = *(_QWORD *)v170;
    *(_QWORD *)v164 = *(_QWORD *)v170;
    if ( v5 == 4 )
    {
      if ( (*(_DWORD *)(*(_QWORD *)v170 + 4LL) & 2) == 0
        || (struct _FILE_OBJECT *)(*(_QWORD *)(*(_QWORD *)v170 + 832LL) & 0xFFFFFFFFFFFFFFFEuLL) != v4 )
      {
        goto LABEL_5;
      }
    }
    else if ( (*((_DWORD *)v3 + 2) & 0x100) == 0 )
    {
LABEL_5:
      LOBYTE(v6) = 1;
      RefsAcquireSharedVcb(v3, *(_QWORD *)v170, v6, v5);
      goto LABEL_6;
    }
    LOBYTE(v6) = 1;
    RefsAcquireExclusiveVcb(v3, *(_QWORD *)v170, v6, v5);
LABEL_6:
    v10 = *(_DWORD *)(v8 + 4);
    if ( (v10 & 0x8000823) == 1 )
      v11 = v7 | 0x40;
    else
      v11 = v7 & 0xBF;
    v12 = v11 & 0x7F | ((v10 & 0x2000020) != 0 ? 0x80 : 0);
    LOBYTE(v158) = v12;
    BYTE1(v157) = v12;
    v13 = 1;
    if ( (v10 & 0x4000000) != 0 )
      v13 = 65;
    v159 = v13;
    LOBYTE(v157) = v13;
    v14 = v169;
    if ( *((_QWORD *)v169 + 13) )
    {
      LOBYTE(v9) = 1;
      RefsAcquireExclusivePagingIoSpecifyWait(v3, v169, v9);
      v15 = v166;
    }
    else
    {
      v15 = v166;
      RefsAcquireExclusiveFcb(v3, *(_QWORD *)(v166 + 120), v166, 0);
      if ( !*((_QWORD *)v14 + 13) )
        goto LABEL_18;
      RefsReleaseFcb(v3, *(_QWORD *)(v15 + 120));
      LOBYTE(v17) = 1;
      RefsAcquireExclusivePagingIoSpecifyWait(v3, v14, v17);
    }
    RefsAcquireExclusiveFcb(v3, *(_QWORD *)(v15 + 120), v15, 0);
LABEL_18:
    v18 = FsContext;
    v19 = *((unsigned int *)FsContext + 1);
    if ( (int)v19 < 0 )
    {
      --*(_DWORD *)(v15 + 320);
      v18[1] &= ~0x80000000;
      v19 = (unsigned int)v18[1];
    }
    v20 = *((_QWORD *)v18 + 9);
    v174 = (char *)v20;
    v194 = v20;
    v183 = v20;
    if ( !v20 || (*(_DWORD *)(v20 + 4) & 2) != 0 )
    {
      v20 = 0;
      v174 = 0;
      v183 = 0;
      LODWORD(v19) = v19 & 0xFFFBFFFF;
      v18[1] = v19;
    }
    else
    {
      v21 = *(__int64 **)(v20 + 24);
      v175 = v21;
      if ( v21 )
        v182 = v21[15];
      v12 = v158;
    }
    if ( !(unsigned __int8)RefsIsFileOpen(v14, v16, v19) && (*((_DWORD *)v14 + 1) & 1) == 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_a783a182122a353df40a288bafce44f2_Traceguids, 3221225768LL);
      }
      if ( RefsStatusDebugEnabled )
        RefsStatusDebug(-1073741528);
      v50 = RefsRaiseStatusInternal(v161, 3221225768LL);
      goto LABEL_546;
    }
    v24 = *((_DWORD *)v14 + 1);
    if ( (v24 & 0x20) != 0 )
    {
      v12 |= 0x80u;
      LOBYTE(v158) = v12;
      BYTE1(v157) = v12;
    }
    if ( (v12 & 0x40) == 0 || v12 < 0 || (v25 = v24 & 1, (_BYTE)v25) )
    {
LABEL_93:
      v46 = v179 - 2;
      if ( v179 != 2 )
      {
        if ( v179 != 3 )
        {
          if ( v179 != 4 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
            {
              WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_a783a182122a353df40a288bafce44f2_Traceguids, v179);
            }
            KeBugCheckEx(0x149u, 0x709BDu, (int)v179, 0, 0);
          }
          v47 = FileObject;
          FileObject->Flags |= 0x4000u;
          v48 = *(_QWORD *)v164;
          if ( *(PFILE_OBJECT *)(*(_QWORD *)v164 + 840LL) == v47 )
          {
            v49 = *(_QWORD *)(*(_QWORD *)v164 + 72LL);
            if ( v49 )
            {
              RefsAcquireExclusiveFcb(v3, *(_QWORD *)(v49 + 120), *(_QWORD *)(*(_QWORD *)v164 + 72LL), 0);
              *(_QWORD *)(*(_QWORD *)v164 + 3240LL) = 0x7FFFFFFFFFFFFFFFLL;
              *(_QWORD *)(v48 + 3248) = 0;
              *(_QWORD *)(v48 + 840) = 0;
              RefsReleaseFcb(v3, *(_QWORD *)(*(_QWORD *)(v48 + 72) + 120LL));
            }
          }
          if ( (*(_DWORD *)(v48 + 4) & 2) == 0 || (PFILE_OBJECT)(*(_QWORD *)(v48 + 832) & 0xFFFFFFFFFFFFFFFEuLL) != v47 )
            goto LABEL_125;
          v50 = *((_DWORD *)v3 + 2);
          if ( (v50 & 0x200) != 0 )
          {
            if ( *(PFILE_OBJECT *)(v48 + 832) == (PFILE_OBJECT)((char *)&v47->Type + 1) )
            {
              LOBYTE(v22) = 1;
              RefsPerformDismountOnVcb((_DWORD)v3, v48, v22, 0, 0);
            }
            else
            {
              v51 = v158;
              if ( (v47->Flags & 0x1000) == 0 )
                goto LABEL_119;
              if ( (v158 & 0x40) != 0 && (v158 & 0x80u) == 0 && (v14[4] & 1) == 0 )
              {
                RefsReleaseFcb(v3, *(_QWORD *)(v15 + 120));
                RefsFlushVolume(v3, v48, 12);
                RefsAcquireExclusiveFcb(v3, *(_QWORD *)(v15 + 120), v15, 0);
              }
              if ( *(_DWORD *)(v48 + 216) == 1 && *(_DWORD *)(v48 + 220) - *(_DWORD *)(v48 + 228) == 1 )
              {
                RefsReleaseFcb(v3, *(_QWORD *)(v15 + 120));
                RefsFlushVolume(v3, v48, 144);
                RefsAcquireExclusiveFcb(v3, *(_QWORD *)(v15 + 120), v15, 0);
                LOBYTE(v52) = 1;
                RefsPerformDismountOnVcb((_DWORD)v3, v48, v52, 0, 0);
                v51 = v158;
LABEL_119:
                *(_DWORD *)(v48 + 4) &= 0xFFFF7FFD;
                *(_QWORD *)(v48 + 832) = 0;
                v53 = v51 | 0x10;
                LOBYTE(v158) = v53;
                BYTE1(v157) = v53;
                if ( (v53 & 0x40) != 0
                  && v53 >= 0
                  && (v14[4] & 1) == 0
                  && !Status
                  && *(_DWORD *)(v48 + 1172) == -1073741202 )
                {
                  *(_DWORD *)(v48 + 1172) = 0;
                  RefsPostSpecial((_DWORD)v3, v48, (unsigned int)RefsDeleteUsnSpecial, v48 + 1160, 1, 0);
                }
LABEL_125:
                LODWORD(Irp) = 7;
LABEL_334:
                v84 = v158;
LABEL_335:
                v116 = v164[0];
LABEL_336:
                v158 = v172;
                if ( v179 == 4 )
                  goto LABEL_425;
                v117 = *((_QWORD *)v14 + 17);
                v118 = *((_QWORD *)v14 + 22);
                if ( v117 != v118 )
                {
                  v119 = *((_DWORD *)v14 + 1);
                  if ( (v119 & 0x10) != 0 )
                  {
                    *((_QWORD *)v14 + 17) = v118;
                  }
                  else
                  {
                    if ( (v119 & 1) != 0 || v117 + RefsLastAccess >= v118 && v118 >= v117 )
                      goto LABEL_345;
                    *((_DWORD *)v14 + 1) = v119 | 0x10;
                    *((_DWORD *)FsContext + 1) |= 0x10000u;
                  }
                  *((_DWORD *)v14 + 42) |= 0x20u;
                }
LABEL_345:
                if ( (v84 & 0x40) != 0 && v84 >= 0 )
                {
                  v120 = *((_DWORD *)v14 + 1);
                  if ( (v120 & 1) == 0 )
                  {
                    if ( (v120 & 0x10) != 0 && !Status )
                      RefsUpdateStandardInformation(v3, v14);
                    if ( ((*((_DWORD *)v14 + 42) & 0xC00000FC) != 0
                       || (*((_DWORD *)FsContext + 1) & 0x10000) != 0
                       || v183 && (*(_DWORD *)(v183 + 188) & 0xC00000FC) != 0)
                      && !Status
                      && (*((_DWORD *)v14 + 1) & 0x100) == 0 )
                    {
                      if ( (v84 & 4) == 0 )
                      {
                        RefsCheckpointCurrentTransaction(v3);
                        RefsPrepareForUpdateDuplicate(
                          (_DWORD)v3,
                          (_DWORD)v14,
                          (unsigned int)&v183,
                          (unsigned int)&v175,
                          1,
                          0);
                        RefsUpdateDuplicateInfo(v3, v14, v183, v175);
                      }
                      v84 |= 0x20u;
                      BYTE1(v157) = v84;
                    }
                    if ( (v84 & 1) != 0 || Status )
                      goto LABEL_394;
                    v181 = 0;
                    if ( (v84 & 0x20) != 0 && (v84 & 4) == 0 || (v121 = *((_DWORD *)v14 + 42), (v121 & 0x100) != 0) )
                    {
                      v122 = v183 ? *(_DWORD *)(v183 + 188) : 0;
                      v121 = *((_DWORD *)v14 + 42);
                      if ( ((v122 | v121) & 0x40000000) != 0 )
                      {
                        v118 = v183 ? *(unsigned int *)(v183 + 188) : 0LL;
                        v123 = ((unsigned __int16)v118 | (unsigned __int16)v121) & 0x1F4 | 8;
                      }
                      else
                      {
                        v118 = v183 ? *(unsigned int *)(v183 + 188) : 0LL;
                        v123 = ((unsigned __int16)v118 | (unsigned __int16)v121) & 0x1FC;
                      }
                      v181 = v123;
                      if ( v123 )
                      {
                        RefsReportDirNotify(
                          v123,
                          v116,
                          (_DWORD)FsContext + 16,
                          *((unsigned __int16 *)FsContext + 16),
                          0,
                          0,
                          v123,
                          3u,
                          v182);
                        v121 = *((_DWORD *)v14 + 42);
                      }
                    }
                    if ( (*((_DWORD *)v14 + 42) = v121 & 0xFFFFFEFF, *(_WORD *)(v15 + 208))
                      && ((v124 = *(_DWORD *)(v15 + 200), v124 == 128) || v124 == 176)
                      || (v159 & 0x20) != 0 )
                    {
                      v125 = *(_DWORD *)(v15 + 304);
                      if ( (v125 & 0x1400) != 0 || (*(_DWORD *)(v15 + 136) & 0x4000) != 0 )
                      {
                        v181 = 0;
                        v116 = 1024;
                        if ( (v125 & 0x400) != 0 )
                        {
                          v126 = 512;
                          v181 = 512;
                        }
                        else
                        {
                          v126 = 0;
                          if ( (*(_DWORD *)(v15 + 136) & 0x4000) != 0 )
                            v126 = 1024;
                          v181 = v126;
                          if ( (v125 & 0x1000) != 0 )
                          {
                            v126 |= 0x800u;
                            v181 = v126;
                          }
                          LODWORD(Irp) = 8;
                        }
                        RefsReportDirNotify(
                          v126,
                          v164[0],
                          (_DWORD)FsContext + 16,
                          *((unsigned __int16 *)FsContext + 16),
                          v15 + 208,
                          0,
                          v126,
                          (ULONG)Irp,
                          v182);
                        v125 = *(_DWORD *)(v15 + 304);
                      }
                      *(_DWORD *)(v15 + 304) = v125 & 0xFFFFE9FF;
                      _InterlockedAnd((volatile signed __int32 *)(v15 + 136), 0xFFFFBFFF);
                      v84 = BYTE1(v157);
                      LOBYTE(v116) = v157;
                      v159 = v116;
                      v14 = v169;
                      v15 = v166;
                      v3 = v161;
                    }
                    else
                    {
LABEL_394:
                      v116 = v159;
                    }
                    if ( !Status )
                    {
                      RefsCheckpointCurrentTransaction(v3);
                      LOBYTE(v116) = v116 | 4;
                      v159 = v116;
                      LOBYTE(v157) = v116;
                      *((_DWORD *)v14 + 1) &= ~0x10u;
                    }
                  }
                }
                if ( v162 && (v84 & 4) == 0 )
                {
                  RefsReleaseFcb(v3, v175[15]);
                  v162 = 0;
                }
                if ( FileObject->PrivateCacheMap || v186 )
                  RefsUninitializeCacheMap(FileObject, v186);
                v127 = v159;
                if ( (v159 & 2) != 0 )
                {
                  RefsCleanupAttributeContext(v3, v199);
                  v127 = v159 & 0xFD;
                  LOBYTE(v157) = v159 & 0xFD;
                }
                v128 = *((_QWORD *)v14 + 27);
                if ( v128
                  && *((_DWORD *)v14 + 6) == 1
                  && (*(_DWORD *)(v128 + 104) || *((char **)v3 + 22) == v14 && *((_DWORD *)v3 + 46)) )
                {
                  v129 = 0;
                  do
                  {
                    NextChildScb = RefsGetNextChildScb(v14, v129, v118, v117);
                    v129 = NextChildScb;
                  }
                  while ( NextChildScb
                       && ((*(_BYTE *)(NextChildScb + 4) & 0x20) == 0 || (*(_DWORD *)(NextChildScb + 136) & 0x40000) == 0) );
                  if ( !NextChildScb )
                    RefsPostUsnChangeWithOverrideOption(v3, v14, 0x80000000LL);
                }
                if ( *((_QWORD *)v3 + 22) && !Status )
                {
                  RefsWriteUsnJournalChanges(v3);
                  RefsCheckpointCurrentTransaction(v3);
                  LOBYTE(v157) = v127 | 4;
                }
                v131 = (volatile signed __int32 *)(v15 + 136);
                if ( (*(_DWORD *)(v15 + 136) & 4) != 0 && *(_DWORD *)(v15 + 144) == 1 )
                {
                  _InterlockedAnd(v131, 0xFFFFFFFB);
                  v84 = BYTE1(v157);
                  v15 = v166;
                  v3 = v161;
                }
                if ( (v84 & 8) != 0 )
                {
                  _InterlockedAnd(v131, 0xFFFFFFFE);
                  v84 = BYTE1(v157);
                  v15 = v166;
                  v3 = v161;
                }
LABEL_425:
                v132 = FsContext;
                if ( (*((_DWORD *)FsContext + 1) & 0x8000000) != 0 )
                {
                  v133 = *((_DWORD *)FsContext + 1);
                  if ( (v84 & 0x40) != 0 && v84 >= 0 && *(_WORD *)v15 == 2053 && *(_QWORD *)(v15 + 360) )
                  {
                    RefsBindMinstoreTransaction(v3);
                    MsSetContainersStationary(*((struct CmsTransactionContext **)v3 + 3), *(CmsStream **)(v15 + 360));
                    v133 = v132[1];
                  }
                  v132[1] = v133 & 0xF7FFFFFF;
                  *(_DWORD *)(v15 + 304) &= ~2u;
                }
                v14 = v161;
                if ( Status < 0 )
                {
                  v41 = v157;
                }
                else
                {
                  RefsCheckpointCurrentTransaction(v161);
                  v41 = v157 | 4;
                  LOBYTE(v157) = v157 | 4;
                  RefsFlushForWriteThrough(v161, v169);
                }
                *((_DWORD *)v161 + 2) &= ~0x400u;
                *((_DWORD *)v14 + 2) |= 0x8000000u;
                v134 = (PVOID *)FsContext;
                *((_DWORD *)FsContext + 1) |= 0x8000u;
                LODWORD(v3) = Status;
                if ( Status && (v41 & 4) == 0 && ((v41 & 0x10) != 0 || (v157 & 0x400) != 0 || (v41 & 0x20) != 0) )
                {
                  if ( (v41 & 0x10) != 0 || (v157 & 0x400) != 0 )
                    v172 = v158 - 1;
                  RefsBackoutFailedLinkRemove((_DWORD)v14, (_DWORD)v134, (_DWORD)v174, v166, (__int64)&v157);
                  v41 = v157;
                  v134 = (PVOID *)FsContext;
                }
                v135 = (v41 & 0x10) != 0;
                if ( (v41 & 0x10) != 0
                  || (v157 & 0x400) != 0
                  || (*((_DWORD *)v134 + 1) & 0x10000) != 0
                  || (*((_DWORD *)v169 + 1) & 0x40000) != 0 )
                {
                  v136 = 16;
                  v187 = 16;
                  if ( (v41 & 0x10) != 0 || (v157 & 0x400) != 0 )
                  {
                    v136 = 80;
                    v187 = 80;
                  }
                  v137 = v169;
                  if ( (*((_DWORD *)v169 + 1) & 0x40000) != 0 )
                  {
                    v136 |= 8u;
                    v187 = v136;
                  }
                  v134 = (PVOID *)v175;
                  if ( v175 )
                    goto LABEL_457;
                  if ( v179 == 2 )
                  {
                    v134 = (PVOID *)*((_QWORD *)v169 + 31);
                    v175 = (__int64 *)v134;
                  }
                  if ( v134 )
                  {
LABEL_457:
                    FsRtlCheckOplockEx(v134 + 11, v180, v136, 0, 0, 0);
                    *((_DWORD *)v137 + 1) &= ~0x40000u;
                  }
                }
                v138 = (v157 & 0x400) != 0;
                if ( (v157 & 0x400) != 0 )
                {
                  v139 = v174;
                  ExAcquireFastMutex(*(PFAST_MUTEX *)(*((_QWORD *)v174 + 3) + 48LL));
                  _InterlockedAdd((volatile signed __int32 *)(*((_QWORD *)v139 + 3) + 156LL), 1u);
                  RefsRemovePrefixSafe(v174);
                  _InterlockedAdd((volatile signed __int32 *)(*((_QWORD *)v139 + 3) + 156LL), 1u);
                  ExReleaseFastMutex(*(PFAST_MUTEX *)(*((_QWORD *)v139 + 3) + 48LL));
                  v140 = v174;
                  v141 = *((_DWORD *)v174 + 1);
                  if ( (v141 & 0x20) != 0 )
                  {
                    RefsRemoveHashEntry(
                      *(_QWORD *)(*((_QWORD *)v174 + 4) + 88LL) + 2696LL,
                      *((unsigned int *)v174 + 48),
                      v174);
                    *((_DWORD *)v140 + 48) = 0;
                    *((_DWORD *)v140 + 1) &= ~0x20u;
                    v141 = *((_DWORD *)v140 + 1);
                  }
                  *((_DWORD *)v140 + 1) = v141 | 2;
                  *((_DWORD *)v140 + 47) = 0;
                  *((_DWORD *)v140 + 43) = 0;
                  LODWORD(v3) = Status;
                  v41 = v157;
                  v14 = v161;
                }
                if ( !v135 )
                {
                  if ( v138 )
                    goto LABEL_472;
                  goto LABEL_471;
                }
                v134 = (PVOID *)*(unsigned int *)(*(_QWORD *)v170 + 3824LL);
                if ( ((unsigned __int8)v134 & 4) == 0 || v179 - 2 > 1 )
                {
LABEL_471:
                  if ( v135 )
                  {
LABEL_474:
                    v134 = (PVOID *)v180;
                    v180->IoStatus.Information = 0;
                    if ( v135 )
                    {
                      v134[7] = (PVOID)4;
                      v143 = 4;
                    }
                    else
                    {
                      v143 = 0;
                      if ( v138 )
                      {
                        v143 = 8;
                        v134[7] = (PVOID)8;
                      }
                    }
                    if ( (v41 & 0x20) != 0 )
                      v134[7] = (PVOID)(v143 | 0x10);
LABEL_483:
                    if ( (v157 & 0x2000) != 0 && !v138 )
                    {
                      RefsUpdateLcbDuplicateInfo(v169, v183);
                      *((_DWORD *)v134 + 42) = 0;
                    }
                    v43 = FileObject;
                    v145 = v166;
                    RefsDecrementCleanupCounts(v134, v166, v194, FileObject->Flags & 8);
                    v174 = 0;
                    if ( v135 )
                    {
                      v146 = (SECTION_OBJECT_POINTERS *)(*(_QWORD *)(v145 + 240) + 8LL);
                      if ( v146->DataSectionObject )
                        MmForceSectionClosed(v146, 1u);
                    }
                    v147 = v166;
                    IoRemoveShareAccess(v43, (PSHARE_ACCESS)(v166 + 172));
                    v42 = FsContext;
                    v148 = *((_DWORD *)FsContext + 2);
                    if ( (v148 & 1) != 0 )
                    {
                      *((_DWORD *)FsContext + 2) = v148 & 0xFFFFFFFE;
                      --*(_DWORD *)(v147 + 164);
                    }
                    *((_WORD *)v169 + 87) -= v172;
                    if ( !(_DWORD)v3 )
                    {
LABEL_492:
                      if ( (_DWORD)v3 != 871 )
                      {
                        if ( v41 < 0 )
                          KeReleaseGuardedMutex((PKGUARDED_MUTEX)(*(_QWORD *)v170 + 536LL));
                        if ( (v41 & 2) != 0 )
                          RefsCleanupAttributeContext(v14, v199);
                        if ( v185 )
                        {
                          v163[0] = 0;
                          RefsTeardownStructures(v14, *(_QWORD *)(v185 + 120), 0, v163);
                          if ( !v163[0] )
                          {
                            v149 = v185;
                            v150 = *(_QWORD *)(v185 + 120);
                            if ( *(_QWORD *)(v150 + 104) )
                            {
                              if ( *(_WORD *)v150 != 2050 )
                                v150 = *(_QWORD *)(v150 + 120);
                              ExReleaseResourceLite(*(PERESOURCE *)(v150 + 104));
                              v149 = v185;
                            }
                            RefsReleaseFcb(v14, *(_QWORD *)(v149 + 120));
                          }
                        }
                        ExReleaseResourceLite((PERESOURCE)(*(_QWORD *)v170 + 1424LL));
                        if ( (v157 & 0x1000) != 0 )
                        {
                          RefsReleaseFcb(v14, *(_QWORD *)(v166 + 120));
                          FsRtlNotifyVolumeEvent(v43, 5u);
                        }
                      }
                      if ( (v41 & 8) != 0 )
                      {
                        _InterlockedDecrement((volatile signed __int32 *)(v184 + 148));
                        LODWORD(v3) = Status;
                        v41 = v157;
                        v14 = v161;
                        v42 = FsContext;
                      }
                      if ( (v41 & 0x40) != 0 && (int)v3 >= 0 )
                      {
                        if ( (_DWORD)v3 == 871 )
                          return (unsigned int)v3;
                        if ( v179 != 4
                          && (v157 & 0x4000) != 0
                          && (v157 & 0x8000) == 0
                          && ((v41 & 0x30) != 0 || (v157 & 0x400) != 0 || (v42[44] & 0x912) != 0) )
                        {
                          v151 = v14 + 4;
                          *((_DWORD *)v14 + 1) |= 0x400u;
                          LODWORD(v3) = Status;
                          if ( RefsStatusDebugEnabled )
                            RefsStatusDebug(Status);
                          v14 = v161;
                          RefsExtendedCompleteRequestInternal(v161, 0, (unsigned int)v3);
                          *v151 |= 0x200u;
                          v153 = RefsIoCallSelf(v152, FileObject);
                          *v151 &= ~0x200u;
                          if ( v153 == -1073741533 )
                            v153 = 0;
                          if ( v153 < 0 )
                          {
                            if ( (unsigned int)(v153 + 1073741662) > 1
                              && v153 != -1073741643
                              && (unsigned int)(v153 + 1073741806) > 2
                              && v153 != -2147483626 )
                            {
                              if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                                || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
                                || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
                              {
                                v153 = -1073700734;
                              }
                              else
                              {
                                v153 = -1073700734;
                                WPP_SF_D(
                                  WPP_GLOBAL_Control->AttachedDevice,
                                  16,
                                  WPP_a783a182122a353df40a288bafce44f2_Traceguids,
                                  3221266562LL);
                              }
                              if ( RefsStatusDebugEnabled )
                                RefsStatusDebug(-1073700734);
                              LODWORD(v3) = Status;
                              v14 = v161;
                            }
                            v154 = v169;
                            ExAcquireFastMutex((PFAST_MUTEX)(*((_QWORD *)v169 + 12) + 8LL));
                            IoRaiseInformationalHardError(
                              v153,
                              (PUNICODE_STRING)FsContext + 1,
                              v180->Tail.Overlay.Thread);
                            ExReleaseFastMutex((PFAST_MUTEX)(*((_QWORD *)v154 + 12) + 8LL));
                          }
                        }
                      }
                      if ( (_DWORD)v3 != 871 )
                        RefsCompleteCleanupRequest(v14, v180, (unsigned int)v3, v40);
                      return (unsigned int)v3;
                    }
LABEL_553:
                    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
                      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                    {
                      WPP_SF_D(
                        WPP_GLOBAL_Control->AttachedDevice,
                        14,
                        WPP_a783a182122a353df40a288bafce44f2_Traceguids,
                        (unsigned int)v3);
                    }
                    *((_DWORD *)v14 + 4) = 0;
                    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                    {
                      WPP_SF_D(
                        WPP_GLOBAL_Control->AttachedDevice,
                        15,
                        WPP_a783a182122a353df40a288bafce44f2_Traceguids,
                        0);
                    }
                    if ( RefsStatusDebugEnabled )
                      RefsStatusDebug(0);
                    RefsRaiseStatusInternal(v161, 0);
                    __debugbreak();
                    JUMPOUT(0x1C015A485LL);
                  }
LABEL_472:
                  if ( !v138 && (v41 & 0x20) == 0 )
                    goto LABEL_483;
                  goto LABEL_474;
                }
                v196 = 0;
                memset(v195, 0, sizeof(v195));
                v196 = *(_OWORD *)(*(_QWORD *)(v166 + 120) + 8LL);
                if ( v180 )
                {
                  if ( (int)IoGetActivityIdIrp(v180, &v195[8]) < 0 )
                  {
LABEL_469:
                    v142 = 0;
                    *(_QWORD *)v195 = 0;
LABEL_470:
                    FsRtlHeatLogIo(*(_QWORD *)v170 + 3820LL, v180, &v196, 0, v142);
                    goto LABEL_471;
                  }
                }
                else
                {
                  ActivityIdThread = (_OWORD *)IoGetActivityIdThread();
                  if ( !ActivityIdThread )
                    goto LABEL_469;
                  *(_OWORD *)&v195[8] = *ActivityIdThread;
                }
                *(_QWORD *)v195 = &v195[8];
                v142 = &v195[8];
                goto LABEL_470;
              }
            }
            v51 = v158;
            goto LABEL_119;
          }
LABEL_546:
          *((_DWORD *)v3 + 2) = v50 | 0x200;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            WPP_SF_D(
              WPP_GLOBAL_Control->AttachedDevice,
              12,
              WPP_a783a182122a353df40a288bafce44f2_Traceguids,
              3221225688LL);
          }
          if ( RefsStatusDebugEnabled )
            RefsStatusDebug(-1073741608);
          RefsRaiseStatusInternal(v161, 3221225688LL);
          goto LABEL_553;
        }
        RefsSnapshotScb(v3, v15);
        if ( (unsigned int)Feature_Servicing_REFSDisallowDASDOplock__private_IsEnabledDeviceUsage() )
        {
          v55 = *(_DWORD *)(v15 + 200);
          if ( (v55 != 128 && v55 != 176 || *(_WORD *)v15 != 2053 || *(_QWORD *)(*(_QWORD *)(v15 + 128) + 72LL) == v15)
            && (v55 != 160
             || *(_WORD *)(v15 + 208) != 8
             || **(_QWORD **)(v15 + 216) != 0x30003300490024LL
             || (unsigned __int16)(*(_WORD *)v15 - 2051) > 1u) )
          {
            v56 = 0;
            goto LABEL_144;
          }
        }
        else
        {
          v57 = *(_DWORD *)(v15 + 200);
          if ( (v57 != 128 && v57 != 176 || *(_WORD *)v15 != 2053)
            && (v57 != 160
             || *(_WORD *)(v15 + 208) != 8
             || **(_QWORD **)(v15 + 216) != 0x30003300490024LL
             || (unsigned __int16)(*(_WORD *)v15 - 2051) > 1u) )
          {
LABEL_146:
            v58 = FileObject;
            FileObject->Flags |= 0x4000u;
            if ( (*((_DWORD *)FsContext + 1) & 0x800000) != 0 )
            {
              v59 = *(_QWORD *)v164;
              v60 = FsContext;
              FsRtlNotifyCleanup(
                *(PNOTIFY_SYNC *)(*(_QWORD *)v164 + 824LL),
                (PLIST_ENTRY)(*(_QWORD *)v164 + 808LL),
                FsContext);
              v60[1] &= ~0x800000u;
              _InterlockedDecrement((volatile signed __int32 *)(v59 + 1528));
              v61 = BYTE1(v157);
              LOBYTE(v158) = BYTE1(v157);
              LOBYTE(v62) = v157;
              v159 = v62;
              *(_QWORD *)v164 = *(_QWORD *)v170;
              v14 = v169;
              v15 = v166;
              v20 = (__int64)v174;
              v3 = v161;
              v58 = FileObject;
            }
            else
            {
              v61 = v158;
            }
            if ( (v61 & 0x40) != 0 && v61 >= 0 && (v14[4] & 1) == 0 && (*((_DWORD *)v14 + 1) & 1) == 0 )
            {
              LOBYTE(v54) = 1;
              RefsUpdateScbFromFileObject(v58, v15, v54);
              if ( *(_WORD *)v15 == 2051 )
              {
                if ( (v159 & 0x10) != 0 )
                {
                  if ( !v20 )
                  {
                    for ( i = (char *)*((_QWORD *)v14 + 5); ; i = *(char **)i )
                    {
                      v188 = i;
                      if ( i == v14 + 40 )
                        break;
                      v193 = i - 40;
                      if ( (*((_DWORD *)i - 9) & 2) == 0 )
                      {
                        v174 = i - 40;
                        v64 = (__int64 *)*((_QWORD *)i - 2);
                        v175 = v64;
                        if ( v64 )
                          v182 = v64[15];
                        break;
                      }
                    }
                  }
                  if ( !v175 && (*((_DWORD *)v14 + 40) & 0x10000000) == 0 )
                  {
                    v175 = (__int64 *)*((_QWORD *)v14 + 31);
                    v182 = v175[15];
                  }
                  if ( (unsigned __int8)RefsIsMinstoreTransactionActive(v3) )
                    RefsCheckpointCurrentTransaction(v65);
                  RefsDeleteFile((_DWORD)v3, (_DWORD)v14, (_DWORD)v175, 0, (__int64)&v162);
                  v172 = 1;
                  v66 = FsContext;
                  if ( !Status )
                  {
                    if ( (v158 & 1) == 0 )
                      RefsReportDirNotify(
                        v164[0],
                        v164[0],
                        (_DWORD)FsContext + 16,
                        *((unsigned __int16 *)FsContext + 16),
                        0,
                        0,
                        2u,
                        2u,
                        v182);
                    v66[1] &= 0xFFFFFF8F;
                  }
                  goto LABEL_333;
                }
                if ( *((_DWORD *)v14 + 7) == 1 && (v159 & 1) != 0 )
                {
                  v67 = dword_1C012DEF8;
                  if ( dword_1C012DEF8 <= (unsigned int)RefsMaxDelayedCloseCount )
                  {
                    _InterlockedOr((volatile signed __int32 *)(v15 + 136), 0x200000u);
                    LODWORD(Irp) = 7;
                    LOBYTE(v67) = v157;
                    v159 = v67;
                    goto LABEL_328;
                  }
                }
              }
            }
            goto LABEL_333;
          }
        }
        v56 = 1;
LABEL_144:
        if ( v56 )
          FsRtlCheckOplock((POPLOCK)(v15 + 88), Irp, 0, 0, 0);
        goto LABEL_146;
      }
      if ( (*(_DWORD *)(v15 + 136) & 0x20) != 0
        || (v158 & 0x40) == 0
        || (v158 & 0x80u) != 0
        || (*(_BYTE *)(*(_QWORD *)(v15 + 120) + 4LL) & 1) != 0 )
      {
        v68 = v164[0];
      }
      else
      {
        RefsUpdateScbFromAttribute(v3, v15, 0);
        v68 = v164[0];
      }
      RefsClearSfioReservation(v46, (_DWORD)Irp, (_DWORD)FileObject, v68, WatchTree, (__int64)FsContext);
      RefsSnapshotScb(v3, v15);
      if ( (unsigned int)Feature_Servicing_REFSDisallowDASDOplock__private_IsEnabledDeviceUsage() )
      {
        v70 = *(_DWORD *)(v15 + 200);
        if ( (v70 != 128 && v70 != 176 || *(_WORD *)v15 != 2053 || *(_QWORD *)(*(_QWORD *)(v15 + 128) + 72LL) == v15)
          && (v70 != 160
           || *(_WORD *)(v15 + 208) != 8
           || **(_QWORD **)(v15 + 216) != 0x30003300490024LL
           || (unsigned __int16)(*(_WORD *)v15 - 2051) > 1u) )
        {
          v71 = 0;
          goto LABEL_199;
        }
      }
      else
      {
        v72 = *(_DWORD *)(v15 + 200);
        if ( (v72 != 128 && v72 != 176 || *(_WORD *)v15 != 2053)
          && (v72 != 160
           || *(_WORD *)(v15 + 208) != 8
           || **(_QWORD **)(v15 + 216) != 0x30003300490024LL
           || (unsigned __int16)(*(_WORD *)v15 - 2051) > 1u) )
        {
          v73 = Irp;
          goto LABEL_202;
        }
      }
      v71 = 1;
LABEL_199:
      v73 = Irp;
      if ( v71 )
        FsRtlCheckOplock((POPLOCK)(v15 + 88), Irp, 0, 0, 0);
LABEL_202:
      if ( *(_WORD *)v15 == 2053 && *(_QWORD *)(v15 + 336) )
      {
        RequestorProcess = IoGetRequestorProcess(v73);
        FsRtlFastUnlockAll(*(PFILE_LOCK *)(v15 + 336), FileObject, RequestorProcess, 0);
      }
      if ( (*(_DWORD *)(*(_QWORD *)(v15 + 128) + 4LL) & 0x4000005) == 1
        && *(_WORD *)v15 == 2053
        && (*(_DWORD *)(v15 + 304) & 0x40) == 0
        && FsRtlOplockIsFastIoPossible((POPLOCK)(v15 + 88)) )
      {
        if ( *(_DWORD *)(v15 + 248)
          || (v75 = *(_QWORD *)(v15 + 336)) != 0 && *(_BYTE *)(v75 + 16)
          || (v76 = *(_DWORD *)(*(_QWORD *)(v15 + 128) + 4LL), (v76 & 0x2000000) != 0)
          || (*(_DWORD *)(*(_QWORD *)(v15 + 120) + 4LL) & 0x20) != 0
          || (v76 & 0x80000) != 0 )
        {
          v77 = 2;
        }
        else
        {
          v77 = 1;
        }
      }
      else
      {
        v77 = 0;
      }
      *(_BYTE *)(v15 + 5) = v77;
      v78 = v158;
      v79 = (v158 & 0x40) != 0;
      if ( (v158 & 0x40) == 0 || (v158 & 0x80u) != 0 || (v14[4] & 1) != 0 )
      {
        FileObject->Flags |= 0x4000u;
        if ( !v79 || (v14[4] & 1) != 0 || (*(_DWORD *)(v15 + 304) & 0x40) != 0 )
          v186 = &RefsLarge0;
        goto LABEL_333;
      }
      v80 = FileObject;
      if ( (*((_BYTE *)FsContext + 88) & 0x20) != 0 )
        FileObject->Flags |= 0x80000u;
      LOBYTE(v69) = 1;
      RefsUpdateScbFromFileObject(v80, v15, v69);
      *(_DWORD *)(v82 + 80) |= 0x4000u;
      if ( Status )
      {
LABEL_333:
        LODWORD(Irp) = 7;
        goto LABEL_334;
      }
      if ( !v20 || (*(_DWORD *)(v20 + 4) & 1) != 0 && *(_DWORD *)(v20 + 196) == 1 )
      {
        v83 = v159;
        if ( (v159 & 0x10) == 0 || (*((_DWORD *)v14 + 1) & 0x8000) == 0 )
        {
          if ( (v159 & 0x10) != 0 )
          {
            if ( !v20 )
            {
              for ( j = (char *)*((_QWORD *)v14 + 5); ; j = *(char **)j )
              {
                v188 = j;
                if ( j == v14 + 40 )
                {
                  v83 = v159;
                  goto LABEL_256;
                }
                v193 = j - 40;
                if ( (*((_DWORD *)j - 9) & 2) == 0 )
                  break;
              }
              v174 = j - 40;
              v91 = (__int64 *)*((_QWORD *)j - 2);
              v175 = v91;
              v83 = v159;
              if ( v91 )
                v182 = v91[15];
            }
LABEL_256:
            if ( !v175 && (*((_DWORD *)v14 + 40) & 0x10000000) == 0 )
            {
              v175 = (__int64 *)*((_QWORD *)v14 + 31);
              v182 = v175[15];
            }
            LOBYTE(v83) = v83 & 0xFE;
            v159 = v83;
            LOBYTE(v157) = v83;
            if ( (unsigned __int8)RefsIsMinstoreTransactionActive(v3) )
              RefsCheckpointCurrentTransaction(v92);
            RefsDeleteFile((_DWORD)v3, (_DWORD)v14, (_DWORD)v175, (unsigned int)&v185, (__int64)&v162);
            v172 = 1;
            v93 = FsContext;
            if ( (v158 & 1) == 0 )
              RefsReportDirNotify(
                v164[0],
                v164[0],
                (_DWORD)FsContext + 16,
                *((unsigned __int16 *)FsContext + 16),
                0,
                0,
                1u,
                2u,
                v182);
            v93[1] &= 0xFFFFFF8F;
            v186 = &RefsLarge0;
            LOBYTE(v83) = v159;
          }
          else if ( v20 )
          {
            LOBYTE(v158) = v78 | 4;
            BYTE1(v157) = v78 | 4;
            if ( *((_WORD *)v14 + 87) <= 1u )
            {
              v84 = v158 & 0xFB;
              BYTE1(v157) = v158 & 0xFB;
            }
            else
            {
              RefsAcquireExclusiveScbWithFlags(v3, v175, 0);
              v162 = 1;
              v94 = v159;
              LOBYTE(v94) = v159 & 0xFE;
              v159 = v94;
              LOBYTE(v157) = v94;
              RefsPostUsnChangeWithOverrideOption(v3, v14, 0x10000);
              RefsRemoveLink(v3, v14, v175);
              v172 = 1;
              *((_DWORD *)v14 + 1) &= ~0x4000u;
              v95 = FsContext;
              RefsUpdateFcb(v182, FsContext, 2684354576LL);
              v84 = v158;
              if ( (v158 & 1) == 0 && !Status )
                RefsReportDirNotify(
                  v164[0],
                  v164[0],
                  (_DWORD)v95 + 16,
                  *((unsigned __int16 *)v95 + 16),
                  0,
                  0,
                  1u,
                  2u,
                  v182);
              v183 = 0;
              v95[1] |= 0x200000u;
              v97 = FileObject;
              FileObject->Flags &= ~0x4000u;
              LOBYTE(v96) = 1;
              RefsUpdateScbFromFileObject(v97, v15, v96);
              *(_DWORD *)(v98 + 80) |= 0x4000u;
              LOBYTE(v83) = v159;
            }
            goto LABEL_229;
          }
LABEL_228:
          v84 = v158;
LABEL_229:
          if ( *(_DWORD *)(v15 + 144) != 1 || !*((_WORD *)v14 + 86) || Status )
            goto LABEL_283;
          if ( (v83 & 0x20) != 0 )
          {
            if ( *(_DWORD *)(v15 + 200) )
            {
              if ( (v159 & 2) != 0 )
                RefsCleanupAttributeContext(v3, v199);
              RefsInitializeAttributeContext(v199);
              LOBYTE(v157) = v159 | 2;
              RefsLookupAttributeForScb(v3, v15, v85, v199);
              LODWORD(Irp) = 7;
              do
                RefsDeleteAttributeRecord(v3, v14, 7, v199);
              while ( (unsigned __int8)RefsLookupInFileRecord(
                                         (_DWORD)v3,
                                         *(_QWORD *)(v15 + 120),
                                         v86,
                                         *(_DWORD *)(v15 + 200),
                                         v15 + 208) );
              RefsCleanupAttributeContext(v3, v199);
              v87 = v159 & 0xFD;
              LOBYTE(v157) = v159 & 0xFD;
              if ( *(__int16 *)(v15 + 252) >= 0 || (unsigned __int8)RefsIsSparseStreamRemaining(v3, v14) )
              {
                v88 = 0x200000;
              }
              else
              {
                *((_DWORD *)v14 + 40) &= ~0x200u;
                *((_DWORD *)v14 + 42) |= 4u;
                v88 = 2129920;
              }
              RefsPostUsnChangeWithOverrideOption(v3, v14, v88);
            }
            else
            {
              LODWORD(Irp) = 7;
              v87 = v159;
            }
            if ( !Status )
            {
              RefsCheckpointCurrentTransaction(v3);
              LOBYTE(v157) = v87 | 4;
            }
            v99 = FileObject;
            *(_QWORD *)(v15 + 24) = 0;
            *(_QWORD *)(v15 + 32) = 0;
            *(_QWORD *)(v15 + 40) = 0;
            *(_DWORD *)(v15 + 200) = 0;
            *(_DWORD *)(v15 + 304) |= 0x440u;
            v100 = *(_DWORD *)(v15 + 304);
            v186 = &RefsLarge0;
            *(_DWORD *)(v15 + 304) = v100 & 0xFFFFEDFF;
            _InterlockedAnd((volatile signed __int32 *)(v15 + 136), 0xFFFFBFFF);
            *((_DWORD *)FsContext + 1) |= 0x600000u;
            v99->Flags &= ~0x4000u;
            LOBYTE(v81) = 1;
            v15 = v166;
            RefsUpdateScbFromFileObject(v99, v166, v81);
            v101->Flags |= 0x4000u;
            v84 = BYTE1(v157);
            LOBYTE(v102) = v157;
            v159 = v102;
            *(_QWORD *)v164 = *(_QWORD *)v170;
            v14 = v169;
            v3 = v161;
            goto LABEL_285;
          }
          if ( *(_DWORD *)(v15 + 200) && (*(_DWORD *)(v15 + 136) & 4) != 0 )
          {
            if ( (v84 & 4) == 0 && (*((_DWORD *)v14 + 1) & 0x100) == 0 )
              RefsPrepareForUpdateDuplicate((_DWORD)v3, (_DWORD)v14, (unsigned int)&v183, (unsigned int)&v175, 1, 0);
            RefsWriteFileSizes(v3, v15, 0, 2);
            v103 = FileObject;
            FileObject->Flags &= ~0x4000u;
            LOBYTE(v104) = 1;
            RefsUpdateScbFromFileObject(v103, v15, v104);
            v101->Flags |= 0x4000u;
          }
          else
          {
LABEL_283:
            v101 = FileObject;
          }
          LOBYTE(v102) = v159;
          LODWORD(Irp) = 7;
LABEL_285:
          if ( !Status && *(_DWORD *)(v15 + 144) == 1 )
          {
            if ( *((_WORD *)v14 + 86) )
            {
              if ( (v102 & 0x20) == 0
                && v101->SectionObjectPointer == (PSECTION_OBJECT_POINTERS)(*(_QWORD *)(v15 + 240) + 8LL) )
              {
                if ( *(_DWORD *)(v15 + 200) )
                {
                  v105 = *(_DWORD *)(v15 + 136);
                  if ( (v105 & 1) != 0 )
                  {
                    v84 |= 8u;
                    BYTE1(v157) = v84;
                    if ( (v84 & 4) == 0 && (*((_DWORD *)v14 + 1) & 0x100) == 0 )
                    {
                      RefsPrepareForUpdateDuplicate(
                        (_DWORD)v3,
                        (_DWORD)v14,
                        (unsigned int)&v183,
                        (unsigned int)&v175,
                        1,
                        0);
                      v105 = *(_DWORD *)(v15 + 136);
                      LOBYTE(v102) = v159;
                    }
                    if ( (v105 & 8) != 0 )
                    {
                      v109 = *(_DWORD *)(v15 + 32);
                      if ( ((v109 + 7) & 0xFFFFFFF8) < *(_DWORD *)(v15 + 24) )
                      {
                        v197 = *(_OWORD *)(v15 + 24);
                        v198 = *(_QWORD *)(v15 + 40);
                        if ( (v102 & 2) != 0 )
                        {
                          RefsCleanupAttributeContext(v3, v199);
                          v109 = *(_DWORD *)(v15 + 32);
                        }
                        LODWORD(v197) = (v109 + 7) & 0xFFFFFFF8;
                        _InterlockedExchange64((volatile __int64 *)(v15 + 264), (unsigned int)v197);
                        v110 = v166;
                        RefsWriteFileSizes(v161, v166, &v197, 17);
                        *(_DWORD *)(v110 + 24) = v197;
                        v111 = _InterlockedExchange64((volatile __int64 *)(v110 + 264), *(_QWORD *)(v110 + 24));
                        v84 = BYTE1(v157);
                        LOBYTE(v111) = v157;
                        v159 = v111;
                        *(_QWORD *)v164 = *(_QWORD *)v170;
                        v14 = v169;
                        v15 = v166;
                        v3 = v161;
                      }
                    }
                    else
                    {
                      v106 = *(_QWORD *)(v15 + 24);
                      if ( v106 )
                      {
                        v107 = *(unsigned int *)(*(_QWORD *)v164 + 456LL);
                        v108 = (v107 + *(_QWORD *)(v15 + 32)) >> *(_BYTE *)(*(_QWORD *)v164 + 464LL);
                        if ( (v106 + v107) >> *(_BYTE *)(*(_QWORD *)v164 + 464LL) != v108 )
                        {
                          RefsDeleteAllocation(
                            (_DWORD)v3,
                            (_DWORD)FileObject,
                            v15,
                            v108,
                            0x7FFFFFFFFFFFFFFFLL,
                            *(_WORD *)(v15 + 252) >= 0);
                          *((_DWORD *)v14 + 1) |= 0x40000u;
                        }
                        v189 = *(_QWORD *)(v15 + 32);
                        v186 = (union _LARGE_INTEGER *)&v189;
                      }
                    }
                    LOBYTE(v81) = 1;
                    RefsUpdateScbFromFileObject(FileObject, v15, v81);
                  }
                }
              }
            }
          }
          v112 = *(_DWORD *)(v15 + 140);
          if ( !v112
            || *(_DWORD *)(v15 + 144) != v112 + 1
            || *(_DWORD *)(v15 + 248)
            || (*((_BYTE *)FsContext + 88) & 7) == 0
            || (v113 = *(_QWORD *)(v15 + 240), !*(_QWORD *)(v113 + 8))
            || *(_QWORD *)(v113 + 24)
            || (FileObject->Flags & 8) != 0
            || Status
            || !MmCanFileBeTruncated((PSECTION_OBJECT_POINTERS)(v113 + 8), 0)
            || (*(_DWORD *)(*(_QWORD *)(v15 + 120) + 4LL) & 0x100) != 0
            || (v84 & 4) != 0 )
          {
            LOBYTE(v114) = v159;
          }
          else
          {
            RefsCheckpointCurrentTransaction(v3);
            v114 = v159;
            LOBYTE(v114) = v159 | 4;
            v159 = v114;
            LOBYTE(v157) = v114;
            if ( v162 )
            {
              RefsReleaseFcb(v3, v175[15]);
              v162 = 0;
            }
            if ( *((_QWORD *)v3 + 6) )
              RefsReleaseSharedResources(v3);
            RefsFlushAndPurgeScb(v3, v15);
            *((_DWORD *)v3 + 4) = 0;
          }
          if ( *((_DWORD *)v14 + 7) != 1 )
            goto LABEL_335;
          if ( (v114 & 1) == 0 )
            goto LABEL_335;
          if ( dword_1C012DEF8 > (unsigned int)RefsMaxDelayedCloseCount )
            goto LABEL_335;
          if ( Status )
            goto LABEL_335;
          v115 = *((_DWORD *)v14 + 1);
          if ( (v115 & 4) != 0 )
            goto LABEL_335;
          _InterlockedOr((volatile signed __int32 *)(v15 + 136), 0x200000u);
          LOBYTE(v115) = v157;
          v159 = v115;
LABEL_328:
          v84 = BYTE1(v157);
          v116 = v170[0];
          *(_QWORD *)v164 = *(_QWORD *)v170;
          v14 = v169;
          v15 = v166;
          v3 = v161;
          goto LABEL_336;
        }
        RefsPostSpecial((_DWORD)v3, v164[0], (unsigned int)RefsDeleteUsnSpecial, v164[0] + 1160, 1, 0);
        v83 = v159;
        LOBYTE(v83) = v159 & 0xEF;
        v159 = v83;
        LOBYTE(v157) = v83;
        ++*((_WORD *)v14 + 86);
        if ( v20 )
        {
          *(_DWORD *)(v20 + 4) &= ~1u;
          goto LABEL_228;
        }
        while ( 1 )
        {
          NextParentLcb = RefsGetNextParentLcb(v14, v20);
          v20 = NextParentLcb;
          v174 = (char *)NextParentLcb;
          if ( !NextParentLcb )
            break;
          *(_DWORD *)(NextParentLcb + 4) &= ~1u;
        }
      }
      LOBYTE(v83) = v159;
      goto LABEL_228;
    }
    if ( (v22 & 0x40000) != 0 )
    {
      if ( (v22 & 2) != 0 )
      {
        v177 = 0;
        v178 = 0;
        v176 = 0;
        v171 = 1;
        v171 = (*(_BYTE *)(v20 + 4) & 1) == 0;
        IsLinkDeleteable = v171;
        if ( v171 && !*((_QWORD *)v14 + 1) )
        {
          IsLinkDeleteable = RefsIsLinkDeleteable(
                               (_DWORD)v3,
                               (_DWORD)v14,
                               (unsigned int)&v178,
                               (unsigned int)&v177,
                               (__int64)&v176);
          v171 = IsLinkDeleteable;
          v23 = FsContext;
        }
        if ( IsLinkDeleteable )
        {
          v27 = 0;
          v184 = 0;
          v22 = 8;
          while ( 1 )
          {
            v28 = RefsGetNextChildScb(v14, v27, v22, v23);
            v30 = v28;
            v184 = v28;
            if ( !v28 )
              break;
            _InterlockedAdd((volatile signed __int32 *)(v28 + 148), 1u);
            v31 = v22 | v157;
            LOBYTE(v157) = v22 | v157;
            v32 = *(_DWORD *)(v184 + 200);
            if ( (v32 == 128 || v32 == 176) && (*(_DWORD *)(v184 + 304) & 0x1000040) == 0 )
            {
              v33 = *(_QWORD *)(v184 + 240);
              if ( *(_QWORD *)(v33 + 24) )
              {
                if ( !MmFlushImageSection((PSECTION_OBJECT_POINTERS)(v33 + 8), MmFlushForDelete) )
                {
                  _InterlockedDecrement((volatile signed __int32 *)(v30 + 148));
                  LOBYTE(v23) = v31 & 0xF7;
                  v159 = (int)v23;
                  LOBYTE(v157) = v31 & 0xF7;
                  LOBYTE(v158) = BYTE1(v157);
                  v29 = *(_QWORD *)v170;
                  *(_QWORD *)v164 = *(_QWORD *)v170;
                  v14 = v169;
                  v15 = v166;
                  v20 = (__int64)v174;
                  v30 = v184;
                  v3 = v161;
                  LODWORD(v22) = (_DWORD)v180;
                  Irp = v180;
                  break;
                }
                v22 = 8;
              }
            }
            _InterlockedDecrement((volatile signed __int32 *)(v30 + 148));
            LOBYTE(v23) = v31 & 0xF7;
            v159 = (int)v23;
            LOBYTE(v157) = v31 & 0xF7;
            LOBYTE(v158) = BYTE1(v157);
            *(_QWORD *)v164 = *(_QWORD *)v170;
            v14 = v169;
            v15 = v166;
            v20 = (__int64)v174;
            v27 = v184;
            v3 = v161;
            Irp = v180;
          }
          if ( v30 )
          {
            v12 = v158;
          }
          else
          {
            --*((_WORD *)v14 + 86);
            *(_DWORD *)(v20 + 4) |= 1u;
            v12 = v158 | 2;
            LOBYTE(v158) = v12;
            BYTE1(v157) = v12;
            if ( (*((_DWORD *)v14 + 40) & 0x10000000) != 0 )
              FsRtlNotifyFilterChangeDirectory(
                *(PNOTIFY_SYNC *)(v29 + 824),
                (PLIST_ENTRY)(v29 + 808),
                FileObject->FsContext,
                0,
                0,
                0,
                0,
                0,
                0,
                0,
                0);
          }
          v23 = FsContext;
        }
      }
      else
      {
        v184 = v15;
        _InterlockedAdd((volatile signed __int32 *)(v15 + 148), 1u);
        v34 = v157 | 8;
        LOBYTE(v157) = v157 | 8;
        v35 = v166;
        v36 = *(_QWORD *)(v166 + 240);
        if ( !*(_QWORD *)(v36 + 24) || MmFlushImageSection((PSECTION_OBJECT_POINTERS)(v36 + 8), MmFlushForDelete) )
        {
          _InterlockedOr((volatile signed __int32 *)(v35 + 136), 2u);
          BYTE1(v157) |= 2u;
        }
        _InterlockedDecrement((volatile signed __int32 *)(v15 + 148));
        LOBYTE(v25) = v34 & 0xF7;
        v159 = v25;
        LOBYTE(v157) = v34 & 0xF7;
        v12 = BYTE1(v157);
        LOBYTE(v158) = BYTE1(v157);
        *(_QWORD *)v164 = *(_QWORD *)v170;
        v14 = v169;
        v15 = v166;
        v20 = (__int64)v174;
        v3 = v161;
        Irp = v180;
        v23 = FsContext;
      }
      v23[1] &= ~0x40000u;
    }
    if ( (v12 & 2) != 0 )
    {
      if ( (unsigned int)Feature_Servicing_REFSDisallowDASDOplock__private_IsEnabledDeviceUsage() )
      {
        v37 = *(_DWORD *)(v15 + 200);
        if ( (v37 != 128 && v37 != 176 || *(_WORD *)v15 != 2053 || *(_QWORD *)(*(_QWORD *)(v15 + 128) + 72LL) == v15)
          && (v37 != 160
           || *(_WORD *)(v15 + 208) != 8
           || **(_QWORD **)(v15 + 216) != 0x30003300490024LL
           || (unsigned __int16)(*(_WORD *)v15 - 2051) > 1u) )
        {
          v38 = 0;
LABEL_78:
          if ( v38 )
          {
            Status = FsRtlCheckOplockEx(
                       (POPLOCK)(v15 + 88),
                       Irp,
                       0x20u,
                       v3,
                       RefsOplockComplete,
                       RefsCleanupOplockPrePostIrp);
            if ( Status == 259 )
            {
              v180 = 0;
              v161 = 0;
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
              {
                WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_a783a182122a353df40a288bafce44f2_Traceguids, 871);
              }
              if ( RefsStatusDebugEnabled )
                RefsStatusDebug(871);
              LODWORD(v3) = 871;
              Status = 871;
              v41 = v157;
              v14 = v161;
              v42 = FsContext;
              v43 = FileObject;
              goto LABEL_492;
            }
          }
          goto LABEL_87;
        }
LABEL_77:
        v38 = 1;
        goto LABEL_78;
      }
      v39 = *(_DWORD *)(v15 + 200);
      if ( (v39 == 128 || v39 == 176) && *(_WORD *)v15 == 2053
        || v39 == 160
        && *(_WORD *)(v15 + 208) == 8
        && **(_QWORD **)(v15 + 216) == 0x30003300490024LL
        && (unsigned __int16)(*(_WORD *)v15 - 2051) <= 1u )
      {
        goto LABEL_77;
      }
    }
LABEL_87:
    if ( *((_WORD *)v14 + 86) || *((_DWORD *)v14 + 6) != 1 )
    {
      if ( (*(_DWORD *)(v15 + 136) & 2) != 0 && *(_DWORD *)(v15 + 144) == 1 )
      {
        v45 = v159;
        LOBYTE(v45) = v159 | 0x20;
        v159 = v45;
        LOBYTE(v157) = v45;
      }
    }
    else
    {
      v44 = v159;
      LOBYTE(v44) = v159 | 0x10;
      v159 = v44;
      LOBYTE(v157) = v44;
    }
    goto LABEL_93;
  }
  v4->Flags |= 0x4000u;
  RefsCompleteCleanupRequest(v3, a2, 0, v5);
  return 0;
}

```

## disassembly

```asm
0x1c01572e0  mov     r11, rsp
0x1c01572e3  mov     [r11+18h], rbx
0x1c01572e7  mov     [r11+20h], rsi
0x1c01572eb  push    rdi
0x1c01572ec  push    r12
0x1c01572ee  push    r13
0x1c01572f0  push    r14
0x1c01572f2  push    r15
0x1c01572f4  sub     rsp, 310h
0x1c01572fb  mov     rax, cs:__security_cookie
0x1c0157302  xor     rax, rsp
0x1c0157305  mov     [rsp+338h+var_38], rax
0x1c015730d  mov     rbx, rdx
0x1c0157310  mov     [r11-2A0h], rdx
0x1c0157317  mov     r14, rcx
0x1c015731a  mov     [rsp+338h+var_2C8], rcx
0x1c015731f  mov     [r11-258h], rdx
0x1c0157326  xor     edi, edi
0x1c0157328  mov     [rsp+338h+Status], edi
0x1c015732c  mov     [r11-288h], rdi
0x1c0157333  mov     [r11-290h], rdi
0x1c015733a  mov     [r11-2A8h], rdi
0x1c0157341  mov     [r11-298h], rdi
0x1c0157348  mov     [r11-268h], rdi
0x1c015734f  mov     [r11-230h], rdi
0x1c0157356  mov     [r11-248h], rdi
0x1c015735d  mov     [r11-238h], rdi
0x1c0157364  xor     edx, edx; Val
0x1c0157366  mov     r8d, 0D0h; Size
0x1c015736c  lea     rcx, [r11-108h]; void *
0x1c0157373  call    memset
0x1c0157378  mov     [rsp+338h+var_228], rdi
0x1c0157380  mov     [rsp+338h+var_210], rdi
0x1c0157388  mov     [rsp+338h+var_2C0], dil
0x1c015738d  mov     [rsp+338h+var_27C], di
0x1c0157395  mov     [rsp+338h+var_2D8], edi
0x1c0157399  lea     r12d, [rdi+1]
0x1c015739d  mov     qword ptr [rbx+38h], 2
0x1c01573a5  mov     rax, [rbx+0B8h]
0x1c01573ac  mov     r15, [rax+30h]
0x1c01573b0  mov     [rsp+338h+FileObject], r15
0x1c01573b8  mov     [rsp+338h+var_278], r15
0x1c01573c0  mov     byte ptr [rsp+338h+CompletionFilter], dil
0x1c01573c5  lea     rax, [rsp+338h+FsContext]
0x1c01573cd  mov     qword ptr [rsp+338h+IgnoreBuffer], rax
0x1c01573d2  lea     rax, [rsp+338h+var_2A8]
0x1c01573da  mov     qword ptr [rsp+338h+WatchTree], rax
0x1c01573df  lea     r9, [rsp+338h+var_290]
0x1c01573e7  lea     r8, [rsp+338h+var_288]
0x1c01573ef  mov     rdx, r15
0x1c01573f2  mov     rcx, r14
0x1c01573f5  call    RefsDecodeFileObject
0x1c01573fa  mov     r9d, eax
0x1c01573fd  mov     [rsp+338h+var_25C], eax
0x1c0157404  lea     ecx, [rax-1]
0x1c0157407  test    ecx, 0FFFFFFFBh
0x1c015740d  jz      loc_1C015A2C4
0x1c0157413  mov     rax, [rsp+338h+FsContext]
0x1c015741b  mov     ecx, [rax+4]
0x1c015741e  shr     ecx, 3
0x1c0157421  mov     bl, byte ptr [rsp+338h+var_2D8+1]
0x1c0157425  xor     cl, bl
0x1c0157427  and     cl, r12b
0x1c015742a  xor     bl, cl
0x1c015742c  mov     eax, [rax+54h]
0x1c015742f  mov     [r14+0C8h], eax
0x1c0157436  mov     rsi, qword ptr [rsp+338h+var_288]
0x1c015743e  mov     qword ptr [rsp+338h+var_2B8], rsi
0x1c0157446  cmp     r9d, 4
0x1c015744a  jnz     short loc_1C0157485
0x1c015744c  mov     eax, [rsi+4]
0x1c015744f  test    al, 2
0x1c0157451  jz      short loc_1C0157463
0x1c0157453  mov     rax, [rsi+340h]
0x1c015745a  and     rax, 0FFFFFFFFFFFFFFFEh
0x1c015745e  cmp     rax, r15
0x1c0157461  jz      short loc_1C015748F
0x1c0157463  mov     r8b, r12b
0x1c0157466  mov     rdx, rsi
0x1c0157469  mov     rcx, r14
0x1c015746c  call    RefsAcquireSharedVcb
0x1c0157471  mov     ecx, [rsi+4]
0x1c0157474  mov     eax, ecx
0x1c0157476  and     eax, 8000823h
0x1c015747b  cmp     eax, r12d
0x1c015747e  jnz     short loc_1C015749F
0x1c0157480  or      bl, 40h
0x1c0157483  jmp     short loc_1C01574A2
0x1c0157485  test    dword ptr [r14+8], 100h
0x1c015748d  jz      short loc_1C0157463
0x1c015748f  mov     r8b, r12b
0x1c0157492  mov     rdx, rsi
0x1c0157495  mov     rcx, r14
0x1c0157498  call    RefsAcquireExclusiveVcb
0x1c015749d  jmp     short loc_1C0157471
0x1c015749f  and     bl, 0BFh
0x1c01574a2  mov     eax, ecx
0x1c01574a4  and     eax, 2000020h
0x1c01574a9  neg     eax
0x1c01574ab  sbb     sil, sil
0x1c01574ae  and     sil, 80h
0x1c01574b2  and     bl, 7Fh
0x1c01574b5  or      sil, bl
0x1c01574b8  mov     byte ptr [rsp+338h+var_2D4], sil
0x1c01574bd  mov     byte ptr [rsp+338h+var_2D8+1], sil
0x1c01574c2  bt      ecx, 1Ah
0x1c01574c6  movzx   eax, r12b
0x1c01574ca  mov     ecx, 41h ; 'A'
0x1c01574cf  cmovb   eax, ecx
0x1c01574d2  mov     [rsp+338h+var_2D0], eax
0x1c01574d6  mov     byte ptr [rsp+338h+var_2D8], al
0x1c01574da  mov     r15, [rsp+338h+var_290]
0x1c01574e2  mov     rcx, r14
0x1c01574e5  cmp     [r15+68h], rdi
0x1c01574e9  jz      short loc_1C0157500
0x1c01574eb  mov     r8b, r12b
0x1c01574ee  mov     rdx, r15
0x1c01574f1  call    RefsAcquireExclusivePagingIoSpecifyWait
0x1c01574f6  mov     rbx, [rsp+338h+var_2A8]
0x1c01574fe  jmp     short loc_1C0157537
0x1c0157500  mov     rbx, [rsp+338h+var_2A8]
0x1c0157508  xor     r9d, r9d
0x1c015750b  mov     r8, rbx
0x1c015750e  mov     rdx, [rbx+78h]
0x1c0157512  call    RefsAcquireExclusiveFcb
0x1c0157517  cmp     [r15+68h], rdi
0x1c015751b  jz      short loc_1C0157549
0x1c015751d  mov     rdx, [rbx+78h]
0x1c0157521  mov     rcx, r14
0x1c0157524  call    RefsReleaseFcb
0x1c0157529  mov     r8b, r12b
0x1c015752c  mov     rdx, r15
0x1c015752f  mov     rcx, r14
0x1c0157532  call    RefsAcquireExclusivePagingIoSpecifyWait
0x1c0157537  xor     r9d, r9d
0x1c015753a  mov     r8, rbx
0x1c015753d  mov     rdx, [rbx+78h]
0x1c0157541  mov     rcx, r14
0x1c0157544  call    RefsAcquireExclusiveFcb
0x1c0157549  mov     r9, [rsp+338h+FsContext]
0x1c0157551  mov     r8d, [r9+4]
0x1c0157555  test    r8d, r8d
0x1c0157558  jns     short loc_1C015756A
0x1c015755a  dec     dword ptr [rbx+140h]
0x1c0157560  btr     dword ptr [r9+4], 1Fh
0x1c0157566  mov     r8d, [r9+4]
0x1c015756a  mov     r13, [r9+48h]
0x1c015756e  mov     [rsp+338h+var_270], r13
0x1c0157576  mov     [rsp+338h+var_1F0], r13
0x1c015757e  mov     [rsp+338h+var_240], r13
0x1c0157586  test    r13, r13
0x1c0157589  jz      short loc_1C01575B7
0x1c015758b  mov     eax, [r13+4]
0x1c015758f  test    al, 2
0x1c0157591  jnz     short loc_1C01575B7
0x1c0157593  mov     rsi, [r13+18h]
0x1c0157597  mov     [rsp+338h+var_268], rsi
0x1c015759f  test    rsi, rsi
0x1c01575a2  jz      short loc_1C01575B0
0x1c01575a4  mov     rax, [rsi+78h]
0x1c01575a8  mov     [rsp+338h+var_248], rax
0x1c01575b0  mov     sil, byte ptr [rsp+338h+var_2D4]
0x1c01575b5  jmp     short loc_1C01575D3
0x1c01575b7  mov     r13, rdi
0x1c01575ba  mov     [rsp+338h+var_270], rdi
0x1c01575c2  mov     [rsp+338h+var_240], rdi
0x1c01575ca  btr     r8d, 12h
0x1c01575cf  mov     [r9+4], r8d
0x1c01575d3  mov     rcx, r15
0x1c01575d6  call    RefsIsFileOpen
0x1c01575db  test    al, al
0x1c01575dd  jnz     short loc_1C01575EC
0x1c01575df  mov     eax, [r15+4]
0x1c01575e3  test    r12b, al
0x1c01575e6  jz      loc_1C015A308
0x1c01575ec  mov     eax, [r15+4]
0x1c01575f0  test    al, 20h
0x1c01575f2  jz      short loc_1C0157602
0x1c01575f4  or      sil, 80h
0x1c01575f8  mov     byte ptr [rsp+338h+var_2D4], sil
0x1c01575fd  mov     byte ptr [rsp+338h+var_2D8+1], sil
0x1c0157602  test    sil, 40h
0x1c0157606  jz      loc_1C0157C97
0x1c015760c  test    sil, sil
0x1c015760f  js      loc_1C0157C97
0x1c0157615  and     eax, r12d
0x1c0157618  test    al, al
0x1c015761a  jnz     loc_1C0157C97
0x1c0157620  test    eax, eax
0x1c0157622  jnz     loc_1C0157C97
0x1c0157628  bt      r8d, 12h
0x1c015762d  jnb     loc_1C0157A27
0x1c0157633  test    r8b, 2
0x1c0157637  jz      loc_1C0157962
0x1c015763d  mov     [rsp+338h+var_25F], dil
0x1c0157645  mov     [rsp+338h+var_25E], dil
0x1c015764d  mov     [rsp+338h+var_260], dil
0x1c0157655  mov     [rsp+338h+var_280], r12b
0x1c015765d  test    [r13+4], r12b
0x1c0157661  movzx   eax, r12b
0x1c0157665  cmovnz  eax, edi
0x1c0157668  mov     [rsp+338h+var_280], al
0x1c015766f  test    al, al
0x1c0157671  jz      loc_1C015773D
0x1c0157677  cmp     [r15+8], rdi
0x1c015767b  jnz     loc_1C015773D
0x1c0157681  lea     rax, [rsp+338h+var_260]
0x1c0157689  mov     qword ptr [rsp+338h+WatchTree], rax
0x1c015768e  lea     r9, [rsp+338h+var_25F]
0x1c0157696  lea     r8, [rsp+338h+var_25E]
0x1c015769e  mov     rdx, r15
0x1c01576a1  mov     rcx, r14
0x1c01576a4  call    RefsIsLinkDeleteable
0x1c01576a9  mov     [rsp+338h+var_280], al
0x1c01576b0  mov     r10, qword ptr [rsp+338h+var_2B8]
0x1c01576b8  mov     r9, [rsp+338h+FsContext]
0x1c01576c0  jmp     loc_1C0157745
0x1c01576c5  xor     al, al
0x1c01576c7  mov     [rsp+338h+var_280], al
0x1c01576ce  xor     edi, edi
0x1c01576d0  lea     r12d, [rdi+1]
0x1c01576d4  mov     rcx, [rsp+338h+var_278]
0x1c01576dc  mov     [rsp+338h+FileObject], rcx
0x1c01576e4  mov     sil, byte ptr [rsp+338h+var_2D8+1]
0x1c01576e9  mov     byte ptr [rsp+338h+var_2D4], sil
0x1c01576ee  mov     cl, byte ptr [rsp+338h+var_2D8]
0x1c01576f2  mov     [rsp+338h+var_2D0], ecx
0x1c01576f6  mov     r10, qword ptr [rsp+338h+var_288]
0x1c01576fe  mov     qword ptr [rsp+338h+var_2B8], r10
0x1c0157706  mov     r15, [rsp+338h+var_290]
0x1c015770e  mov     rbx, [rsp+338h+var_2A8]
0x1c0157716  mov     r13, [rsp+338h+var_270]
0x1c015771e  mov     r14, [rsp+338h+var_2C8]
0x1c0157723  mov     r8, [rsp+338h+var_258]
0x1c015772b  mov     [rsp+338h+Irp], r8
0x1c0157733  mov     r9, [rsp+338h+FsContext]
0x1c015773b  jmp     short loc_1C0157745
0x1c015773d  mov     r10, qword ptr [rsp+338h+var_2B8]
0x1c0157745  test    al, al
0x1c0157747  jz      loc_1C01578D9
0x1c015774d  mov     rdx, rdi
0x1c0157750  mov     [rsp+338h+var_238], rdx
0x1c0157758  mov     r8d, 8
0x1c015775e  mov     rcx, r15
0x1c0157761  call    RefsGetNextChildScb
0x1c0157766  mov     rsi, rax
0x1c0157769  mov     [rsp+338h+var_238], rax
0x1c0157771  test    rax, rax
0x1c0157774  jz      loc_1C015784C
0x1c015777a  lock add [rax+94h], r12d
0x1c0157782  mov     bl, byte ptr [rsp+338h+var_2D8]
0x1c0157786  or      bl, r8b
0x1c0157789  mov     byte ptr [rsp+338h+var_2D8], bl
0x1c015778d  mov     rcx, [rsp+338h+var_238]
0x1c0157795  mov     eax, [rcx+0C8h]
0x1c015779b  cmp     eax, 80h
0x1c01577a0  jz      short loc_1C01577AD
0x1c01577a2  cmp     eax, 0B0h
0x1c01577a7  jnz     loc_1C01578F0
0x1c01577ad  mov     eax, [rcx+130h]
0x1c01577b3  test    eax, 1000040h
0x1c01577b8  jnz     loc_1C01578F0
0x1c01577be  mov     rcx, [rcx+0F0h]
0x1c01577c5  cmp     [rcx+18h], rdi
0x1c01577c9  jz      loc_1C01578F0
0x1c01577cf  add     rcx, 8; SectionObjectPointer
0x1c01577d3  xor     edx, edx; FlushType
0x1c01577d5  call    cs:__imp_MmFlushImageSection
0x1c01577dc  nop     dword ptr [rax+rax+00h]
0x1c01577e1  test    al, al
0x1c01577e3  jnz     loc_1C01578EA
0x1c01577e9  lock dec dword ptr [rsi+94h]
0x1c01577f0  and     bl, 0F7h
0x1c01577f3  mov     r9b, bl
0x1c01577f6  mov     [rsp+338h+var_2D0], r9d
0x1c01577fb  mov     byte ptr [rsp+338h+var_2D8], bl
0x1c01577ff  mov     al, byte ptr [rsp+338h+var_2D8+1]
0x1c0157803  mov     byte ptr [rsp+338h+var_2D4], al
0x1c0157807  mov     r10, qword ptr [rsp+338h+var_288]
0x1c015780f  mov     qword ptr [rsp+338h+var_2B8], r10
0x1c0157817  mov     r15, [rsp+338h+var_290]
0x1c015781f  mov     rbx, [rsp+338h+var_2A8]
0x1c0157827  mov     r13, [rsp+338h+var_270]
0x1c015782f  mov     rsi, [rsp+338h+var_238]
0x1c0157837  mov     r14, [rsp+338h+var_2C8]
0x1c015783c  mov     r8, [rsp+338h+var_258]
0x1c0157844  mov     [rsp+338h+Irp], r8
0x1c015784c  test    rsi, rsi
0x1c015784f  jnz     loc_1C0157958
0x1c0157855  mov     eax, 0FFFFh
0x1c015785a  add     [r15+0ACh], ax
0x1c0157862  or      [r13+4], r12d
0x1c0157866  mov     sil, byte ptr [rsp+338h+var_2D4]
0x1c015786b  or      sil, 2
0x1c015786f  mov     byte ptr [rsp+338h+var_2D4], sil
0x1c0157874  mov     byte ptr [rsp+338h+var_2D8+1], sil
0x1c0157879  mov     eax, [r15+0A0h]
0x1c0157880  bt      eax, 1Ch
0x1c0157884  jnb     short loc_1C01578D1
0x1c0157886  lea     rdx, [r10+328h]; NotifyList
  ... truncated ...
```
