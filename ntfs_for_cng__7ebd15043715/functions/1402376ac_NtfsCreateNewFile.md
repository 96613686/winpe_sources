# NtfsCreateNewFile

- ea: `0x1402376ac`
- end: `0x14023a09c`
- name: `NtfsCreateNewFile`
- size: `10736`
- prototype: `__int64 __fastcall(CLFS_LSN *, IRP *, __int64, unsigned __int8 *, _WORD *, const void **, __int64, int, __int64 *, __int64, __int64 *)`
- caller_count: `1`
- callee_count: `71`
- tags: `reparse_path, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1401a2cb0`

## callees

- `0x140007ea0`
- `0x14000c290`
- `0x14000cb00`
- `0x14000cb80`
- `0x14000ea70`
- `0x140012e70`
- `0x14001c8c0`
- `0x140025a40`
- `0x140029cb0`
- `0x14002fe24`
- `0x14003efc4`
- `0x14003f358`
- `0x1400410a8`
- `0x140059250`
- `0x140059370`
- `0x1400596c0`
- `0x1400e71fc`
- `0x140128d50`
- `0x14012baf8`
- `0x14012d150`
- `0x14012f930`
- `0x140130550`
- `0x14013f374`
- `0x140140380`
- `0x1401413b0`
- `0x140145af8`
- `0x14014b5a8`
- `0x14014ea40`
- `0x140153ab0`
- `0x1401548d0`
- `0x140154d10`
- `0x140156080`
- `0x140159768`
- `0x14015b440`
- `0x14015d080`
- `0x140160be0`
- `0x1401620c0`
- `0x1401633d0`
- `0x140166514`
- `0x14017ff0c`
- `0x140185c00`
- `0x140187da0`
- `0x140192470`
- `0x140193844`
- `0x1401941c0`
- `0x1401982b0`
- `0x1401990f0`
- `0x14019b330`
- `0x14019c120`
- `0x14019ca80`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1402399af`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1402b72ab`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1402399af`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1402b72ab`
- `ntoskrnl!FsRtlFindInTunnelCacheEx` at `0x140237f74`
- `ntoskrnl!FsRtlFindInTunnelCacheEx` at `0x140237f74`
- `ntoskrnl!FsRtlIsNonEmptyDirectoryReparsePointAllowed` at `0x140237ae3`
- `ntoskrnl!FsRtlIsNonEmptyDirectoryReparsePointAllowed` at `0x140237ae3`
- `ntoskrnl!RtlGetOwnerSecurityDescriptor` at `0x140237ff3`
- `ntoskrnl!RtlGetOwnerSecurityDescriptor` at `0x140237ff3`
- `ntoskrnl!FsRtlIsEcpFromUserMode` at `0x140238866`
- `ntoskrnl!FsRtlIsEcpFromUserMode` at `0x140238866`
- `ntoskrnl!RtlUpcaseUnicodeString` at `0x14023916f`
- `ntoskrnl!RtlUpcaseUnicodeString` at `0x140239190`
- `ntoskrnl!RtlUpcaseUnicodeString` at `0x14023916f`
- `ntoskrnl!RtlUpcaseUnicodeString` at `0x140239190`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14023817b`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1402381f5`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1402b7147`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14023817b`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1402381f5`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1402b7147`
- `ntoskrnl!ExReleasePushLockEx` at `0x140238191`
- `ntoskrnl!ExReleasePushLockEx` at `0x14023820b`
- `ntoskrnl!ExReleasePushLockEx` at `0x1402399d5`
- `ntoskrnl!ExReleasePushLockEx` at `0x1402b7160`
- `ntoskrnl!ExReleasePushLockEx` at `0x1402b72d2`
- `ntoskrnl!ExReleasePushLockEx` at `0x140238191`
- `ntoskrnl!ExReleasePushLockEx` at `0x14023820b`
- `ntoskrnl!ExReleasePushLockEx` at `0x1402399d5`
- `ntoskrnl!ExReleasePushLockEx` at `0x1402b7160`
- `ntoskrnl!ExReleasePushLockEx` at `0x1402b72d2`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140239927`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402b7223`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140239927`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402b7223`
- `ntoskrnl!ExFreePoolWithTag` at `0x14023863f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402398d8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b71c8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14023863f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402398d8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b71c8`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1402389a6`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1402389a6`
- `ntoskrnl!CcUnpinData` at `0x14023987a`
- `ntoskrnl!CcUnpinData` at `0x1402b70e8`
- `ntoskrnl!CcUnpinData` at `0x14023987a`
- `ntoskrnl!CcUnpinData` at `0x1402b70e8`
- `ntoskrnl!ExReleaseResourceLite` at `0x14023895c`
- `ntoskrnl!ExReleaseResourceLite` at `0x140238a0d`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402b70cf`
- `ntoskrnl!ExReleaseResourceLite` at `0x14023895c`
- `ntoskrnl!ExReleaseResourceLite` at `0x140238a0d`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402b70cf`
- `ntoskrnl!FsRtlCheckOplockEx` at `0x140239476`
- `ntoskrnl!FsRtlCheckOplockEx` at `0x140239476`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14023890b`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14023890b`

## pseudocode

```c
__int64 __fastcall NtfsCreateNewFile(
        CLFS_LSN *a1,
        IRP *a2,
        __int64 a3,
        unsigned __int8 *a4,
        _WORD *a5,
        const void **a6,
        __int64 a7,
        int a8,
        __int64 *a9,
        __int64 a10,
        __int64 *a11)
{
  __int64 v13; // rsi
  int v14; // ebx
  __int64 v15; // r14
  __int64 result; // rax
  int v17; // eax
  int v18; // eax
  __int16 v19; // dx
  unsigned int v20; // r8d
  __int64 v21; // rax
  __int16 v22; // cx
  __int64 v23; // rcx
  int v24; // eax
  int v25; // eax
  __int64 v26; // rcx
  __int64 v27; // rdx
  unsigned int CurrentFileInfo; // eax
  __int64 v29; // rcx
  __int64 v30; // r11
  __int64 v31; // rbx
  __int64 v32; // rdx
  unsigned __int16 v33; // ax
  signed int v34; // ebx
  int OwnerId; // r12d
  _DWORD *v36; // rbx
  int v37; // ecx
  int v38; // edx
  int v39; // eax
  int v40; // eax
  const void **v41; // rbx
  unsigned int v42; // edx
  void *ullOffset; // rdx
  __int64 v44; // r8
  int v45; // ebx
  __int64 v46; // rax
  int v47; // eax
  NTSTATUS OwnerSecurityDescriptor; // ebx
  __int64 v49; // rax
  __int64 v50; // r8
  __int64 v51; // r14
  __int64 v52; // rbx
  __int64 v53; // r9
  __int64 v54; // r15
  int v55; // r11d
  __int64 v56; // r10
  __int64 v57; // r9
  int v58; // eax
  unsigned int v59; // r8d
  volatile signed __int32 *v60; // rcx
  PVOID *v61; // rcx
  __int64 v62; // r9
  __int64 v63; // rcx
  __int64 v64; // rax
  __int16 v65; // cx
  __int64 v66; // rdx
  __int64 v67; // rcx
  int v68; // eax
  int v69; // ebx
  __int64 v70; // rcx
  __int16 v71; // ax
  __int64 v72; // rcx
  int v73; // r11d
  __int64 v74; // r8
  __int16 v75; // cx
  __int64 v76; // r9
  __int64 v77; // rdx
  int v78; // eax
  __int16 v79; // cx
  BOOLEAN IsEcpFromUserMode; // al
  int v81; // ecx
  __int64 v82; // rcx
  int v83; // eax
  char v84; // bl
  int v85; // ebx
  unsigned int v86; // r15d
  __int64 v87; // r15
  struct _ERESOURCE *v88; // r12
  __int64 v89; // rdx
  unsigned int v90; // r15d
  struct _ERESOURCE *v91; // r12
  int v92; // eax
  __int64 v93; // rcx
  _QWORD *v94; // r15
  int v95; // eax
  int v96; // eax
  unsigned int v97; // ebx
  __int64 v98; // rcx
  int v99; // eax
  __int64 v100; // rcx
  __int64 v101; // rcx
  int v102; // eax
  int v103; // ebx
  __int64 v104; // rcx
  _QWORD *Lcb; // r10
  int v106; // ecx
  int v107; // r8d
  __int16 v108; // dx
  int v109; // eax
  int v110; // ecx
  __int64 v111; // rcx
  __int64 v112; // r15
  __int64 v113; // rcx
  char v114; // r8
  __int64 v115; // rbx
  __int64 v116; // rax
  int v117; // ecx
  bool v118; // cf
  __int64 v119; // rdx
  unsigned __int8 v120; // cl
  UNICODE_STRING *v121; // rdx
  union _LARGE_INTEGER v122; // r12
  PIRP v123; // rbx
  union _LARGE_INTEGER *v124; // rbx
  __int64 v125; // r12
  __int64 v126; // rdx
  int v127; // ebx
  __int64 v128; // rax
  struct _IRP *MasterIrp; // r9
  __int64 v130; // rax
  __int64 v131; // rbx
  __int64 v132; // r9
  int v133; // r8d
  IRP *v134; // r15
  __int64 v135; // rax
  __int64 v136; // r12
  __int64 v137; // rax
  _WORD *v138; // r8
  __int64 v139; // rcx
  __int64 v140; // rcx
  __int64 v141; // rax
  PVOID *v142; // r12
  __int64 v143; // r9
  _QWORD *NextChildScb; // rdx
  signed __int64 v145; // rcx
  signed __int64 v146; // r10
  signed __int64 v147; // r9
  __int64 v148; // r8
  __int64 v149; // rax
  __int64 v150; // r11
  __int64 v151; // r10
  unsigned __int16 v152; // ax
  unsigned __int16 v153; // cx
  __int64 v154; // rdx
  __int64 v155; // rcx
  POPLOCK_WAIT_COMPLETE_ROUTINE CompletionRoutine; // [rsp+20h] [rbp-328h]
  POPLOCK_WAIT_COMPLETE_ROUTINE CompletionRoutinea; // [rsp+20h] [rbp-328h]
  POPLOCK_WAIT_COMPLETE_ROUTINE CompletionRoutineb; // [rsp+20h] [rbp-328h]
  POPLOCK_WAIT_COMPLETE_ROUTINE CompletionRoutinec; // [rsp+20h] [rbp-328h]
  POPLOCK_WAIT_COMPLETE_ROUTINE CompletionRoutined; // [rsp+20h] [rbp-328h]
  union _LARGE_INTEGER FileOffset; // [rsp+30h] [rbp-318h]
  union _LARGE_INTEGER FileOffseta; // [rsp+30h] [rbp-318h]
  union _LARGE_INTEGER FileOffsetb; // [rsp+30h] [rbp-318h]
  int v164; // [rsp+48h] [rbp-300h]
  __int64 QuadPart; // [rsp+48h] [rbp-300h]
  __int64 v166; // [rsp+50h] [rbp-2F8h]
  __int64 v167; // [rsp+58h] [rbp-2F0h]
  bool v168; // [rsp+80h] [rbp-2C8h] BYREF
  char v169; // [rsp+81h] [rbp-2C7h] BYREF
  char v170; // [rsp+82h] [rbp-2C6h]
  __int16 v171; // [rsp+83h] [rbp-2C5h]
  char v172; // [rsp+85h] [rbp-2C3h] BYREF
  unsigned __int8 v173; // [rsp+86h] [rbp-2C2h]
  char v174; // [rsp+87h] [rbp-2C1h] BYREF
  char v175; // [rsp+88h] [rbp-2C0h]
  __int64 v176; // [rsp+90h] [rbp-2B8h]
  char v177; // [rsp+98h] [rbp-2B0h] BYREF
  char v178; // [rsp+99h] [rbp-2AFh]
  int v179; // [rsp+9Ch] [rbp-2ACh] BYREF
  NTSTATUS v180; // [rsp+A0h] [rbp-2A8h]
  unsigned __int8 OwnerDefaulted[4]; // [rsp+A4h] [rbp-2A4h] BYREF
  unsigned int v182; // [rsp+A8h] [rbp-2A0h] BYREF
  int v183; // [rsp+ACh] [rbp-29Ch]
  int v184; // [rsp+B0h] [rbp-298h]
  int v185[2]; // [rsp+B8h] [rbp-290h] BYREF
  PIRP Irp; // [rsp+C0h] [rbp-288h]
  __int16 v187[2]; // [rsp+C8h] [rbp-280h]
  int v188; // [rsp+CCh] [rbp-27Ch]
  _QWORD *v189; // [rsp+D0h] [rbp-278h]
  PVOID Bcb; // [rsp+D8h] [rbp-270h] BYREF
  volatile signed __int32 *v191; // [rsp+E0h] [rbp-268h] BYREF
  char v192; // [rsp+E8h] [rbp-260h]
  PVOID v193; // [rsp+F0h] [rbp-258h] BYREF
  PVOID *v194; // [rsp+F8h] [rbp-250h] BYREF
  const void **v195; // [rsp+100h] [rbp-248h]
  int v196; // [rsp+108h] [rbp-240h]
  int v197; // [rsp+10Ch] [rbp-23Ch] BYREF
  int v198; // [rsp+110h] [rbp-238h] BYREF
  __int64 v199; // [rsp+118h] [rbp-230h]
  unsigned __int8 *v200; // [rsp+120h] [rbp-228h]
  __int64 v201; // [rsp+128h] [rbp-220h]
  _QWORD *v202; // [rsp+130h] [rbp-218h] BYREF
  _QWORD *v203; // [rsp+138h] [rbp-210h]
  PVOID P[2]; // [rsp+140h] [rbp-208h] BYREF
  PSID Owner; // [rsp+150h] [rbp-1F8h] BYREF
  _WORD *v206; // [rsp+158h] [rbp-1F0h]
  __int64 v207; // [rsp+160h] [rbp-1E8h] BYREF
  union _LARGE_INTEGER v208; // [rsp+168h] [rbp-1E0h] BYREF
  __int64 v209; // [rsp+170h] [rbp-1D8h] BYREF
  __int64 *v210; // [rsp+178h] [rbp-1D0h]
  __int64 v211; // [rsp+180h] [rbp-1C8h]
  CLFS_LSN *v212; // [rsp+188h] [rbp-1C0h]
  __int64 v213[2]; // [rsp+190h] [rbp-1B8h] BYREF
  __int64 v214; // [rsp+1A0h] [rbp-1A8h] BYREF
  __int64 *v215; // [rsp+1A8h] [rbp-1A0h]
  __int64 v216; // [rsp+1B0h] [rbp-198h]
  __int64 v217; // [rsp+1B8h] [rbp-190h]
  __int64 v218; // [rsp+1C0h] [rbp-188h]
  __int64 v219; // [rsp+1C8h] [rbp-180h]
  PVOID v220[12]; // [rsp+1D0h] [rbp-178h] BYREF
  _QWORD v221[14]; // [rsp+230h] [rbp-118h] BYREF
  __int64 v222[10]; // [rsp+2A0h] [rbp-A8h] BYREF
  char v223; // [rsp+2F0h] [rbp-58h] BYREF

  v200 = a4;
  Irp = a2;
  v13 = a10;
  v206 = a5;
  v195 = a6;
  v212 = a1;
  v218 = a3;
  v207 = a7;
  v210 = a9;
  v217 = (__int64)a9;
  v211 = a10;
  v215 = a11;
  v219 = (__int64)a11;
  v14 = 0;
  Bcb = 0;
  v208.QuadPart = 0;
  *(_QWORD *)v185 = 0;
  v193 = 0;
  v198 = 0;
  v197 = 0;
  v194 = 0;
  v191 = 0;
  Owner = 0;
  *(_OWORD *)v213 = 0;
  v214 = 0;
  v209 = 0;
  v172 = 0;
  v168 = 0;
  v169 = 0;
  OwnerDefaulted[0] = 0;
  v174 = 0;
  memset(v221, 0, sizeof(v221));
  memset(v222, 0, sizeof(v222));
  memset(v220, 0, 0x58u);
  v15 = *(_QWORD *)(a3 + 192);
  v176 = v15;
  if ( (*(_DWORD *)(v15 + 4) & 0x2000000) != 0 )
  {
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(0, 0xC00000A2, 0xA2780u);
    return 3221225634LL;
  }
  v17 = *(_DWORD *)(a3 + 512);
  if ( (v17 & 0x4000000) != 0 )
  {
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(0, 0xC0000189, 0xA278Eu);
    return 3221225865LL;
  }
  if ( (v17 & 0x10000) != 0 )
  {
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(0, 0xC000026E, 0xA2793u);
    return 3221226094LL;
  }
  a1[63].offset.idxRecord = 28;
  v221[1] = &v221[4];
  v221[3] = &v221[7];
  LODWORD(v221[0]) = 1572864;
  LODWORD(v221[2]) = 3407872;
  v18 = *(_DWORD *)(v13 + 156);
  if ( (v18 & 1) != 0 )
    v14 = 0x20000;
  v179 = v14;
  result = NtfsCheckValidAttributeAccess((__int64)a1, *(_QWORD *)(v13 + 176), v15, 0, &v207, &a8, v18, &v179, &v168);
  v180 = result;
  if ( (int)result >= 0 )
  {
    if ( v168 )
    {
      v19 = *(_WORD *)(*(_QWORD *)(v13 + 176) + 24LL);
      if ( (v19 & 0x100) != 0 )
      {
        if ( NtfsStatusDebugFlags )
        {
          v20 = 665557;
LABEL_37:
          NtfsStatusTraceAndDebugInternal(0, 0xC000000D, v20);
          return 3221225485LL;
        }
        return 3221225485LL;
      }
      v21 = *(_QWORD *)(v13 + 224);
      if ( v21 )
      {
        v22 = *(_WORD *)(v21 + 2);
        if ( (v22 & 0xD) != 0
          || (v22 & 0x40) != 0 && _bittest((const signed __int32 *)(v21 + 56), 9u) && (v19 & 0x200) != 0 )
        {
          if ( NtfsStatusDebugFlags )
          {
            v20 = 665573;
            goto LABEL_37;
          }
          return 3221225485LL;
        }
      }
    }
    else
    {
      v23 = *(_QWORD *)(v13 + 224);
      if ( v23 )
      {
        if ( *(char *)(v23 + 2) >= 0 )
          LOBYTE(v24) = 0;
        else
          v24 = *(_DWORD *)(v23 + 60);
        if ( (v24 & 1) != 0 )
          v25 = *(_DWORD *)(v23 + 76);
        else
          LOBYTE(v25) = 0;
        if ( (v25 & 1) != 0 )
        {
          if ( NtfsStatusDebugFlags )
          {
            v20 = 665586;
            goto LABEL_37;
          }
          return 3221225485LL;
        }
      }
    }
    v26 = *(_QWORD *)(v13 + 176);
    if ( (*(_DWORD *)(v26 + 16) & 0x1000) != 0 && (*(_BYTE *)(v26 + 24) & 1) != 0 && (*(_BYTE *)(v26 + 2) & 0x40) == 0 )
    {
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(0, 0xC0000121, 0xA27FEu);
      return 3221225761LL;
    }
    v27 = *(_QWORD *)(a3 + 184);
    if ( (*(_DWORD *)(v27 + 176) & 0x10000000) != 0
      && (TxfGetCurrentFileInfo((__int64)a1, v27, 1, 1, *(_QWORD *)(v13 + 184)) & 0x400) != 0 )
    {
      CurrentFileInfo = TxfGetCurrentFileInfo((__int64)a1, *(_QWORD *)(v13 + 96), 0, 1, *(_QWORD *)(v13 + 184));
      if ( !(unsigned __int8)FsRtlIsNonEmptyDirectoryReparsePointAllowed(CurrentFileInfo) )
      {
        if ( NtfsStatusDebugFlags )
          NtfsStatusTraceAndDebugInternal(0, 0xC0000281, 0xA2813u);
        return 3221226113LL;
      }
    }
    v29 = *(_QWORD *)(a3 + 184);
    if ( ((*(_DWORD *)(v29 + 4) & 0x100) != 0 && a3 != *(_QWORD *)(v15 + 32) || ((a8 - 128) & 0xFFFFFFDF) != 0)
      && (*(int *)(v29 + 176) >= 0
       || _InterlockedCompareExchange((volatile signed __int32 *)(*(_QWORD *)(v29 + 320) + 132LL), 4, 4)
       || (int)TxfConvertMungedNameToTxfFileId(0, (__int64)a6, 0) < 0) )
    {
      if ( (a1[2].offset.idxRecord & 0x100000) == 0
        && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x20) != 0 )
      {
        v30 = *(_QWORD *)(a3 + 184);
        v31 = *(_QWORD *)(v30 + 96);
        v32 = *(_QWORD *)(v31 + 248);
        v33 = *(_WORD *)(v32 + 6);
        if ( v33 > 0x40u || (v33 & 1) != 0 )
          v33 = 0;
        FileOffset.LowPart = v33 >> 1;
        LODWORD(CompletionRoutine) = *(unsigned __int16 *)(v31 + 7872) >> 1;
        McTemplateU0ppwwpiddd_EtwWriteTransfer(
          *(_QWORD *)(v30 + 320),
          (const EVENT_DESCRIPTOR *)create_c10289,
          KeGetCurrentThread(),
          v31,
          CompletionRoutine,
          *(_QWORD *)(v31 + 7880),
          FileOffset.QuadPart,
          v32 + 32,
          v30,
          *(_QWORD *)(v30 + 8),
          *(_DWORD *)(v30 + 4),
          *(_DWORD *)(*(_QWORD *)(v30 + 320) + 132LL),
          a8);
      }
      v34 = -1073741790;
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(0, 0xC0000022, 0xA2841u);
      return (unsigned int)v34;
    }
    v201 = v15;
    v189 = 0;
    v203 = 0;
    v199 = 0;
    OwnerId = 0;
    *(_DWORD *)v187 = 0;
    v178 = 0;
    v175 = 0;
    v170 = 0;
    v173 = 0;
    LOBYTE(v184) = 0;
    v171 = 0;
    v202 = 0;
    if ( (*(_DWORD *)(v15 + 24) & 0x40000) != 0 && (*(_WORD *)(a3 + 460) & 0x40FF) != 0 )
    {
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(0, 0xC000049A, 0xA284Fu);
      return 3221226650LL;
    }
    *(_DWORD *)(v13 + 196) |= 0x100u;
    v36 = *(_DWORD **)(*(_QWORD *)(*(_QWORD *)(v13 + 176) + 8LL) + 8LL);
    v37 = v168 ? 4 : 2;
    v196 = v37;
    v38 = v36[4];
    if ( (v38 & 0x1000000) != 0 )
    {
      v37 |= 0x1000000u;
      v196 = v37;
    }
    if ( (v36[3] & 4) != 0 )
    {
      v36[5] |= v38 & 0xFEFFFFFF;
      v36[4] = v38 & ~v36[5];
      v37 = 0;
      v196 = 0;
    }
    NtfsAccessCheck((__int64)a1, v13, *(_QWORD **)(a3 + 184), 0, (__int64)Irp, v37, 1, 1, 0);
    v36[5] |= v36[4];
    v39 = v36[5];
    if ( (v39 & 0x2000000) != 0 )
    {
      v40 = v39 | 0x1F01FF;
      v36[5] = v40;
      v36[5] = v40 & 0xFDFFFFFF;
    }
    v36[4] = 0;
    v191 = (volatile signed __int32 *)NtfsCacheSharedSecurityForCreate((__int64)a1, *(_QWORD *)(a3 + 184));
    if ( !*(_WORD *)(a3 + 656) )
      NtfsBuildNormalizedNameWithTxfIsolation((__int64)a1, *(_QWORD *)(a3 + 184), a3, 0, 0, 0, (_QWORD *)(a3 + 656));
    v41 = v195;
    v42 = *(unsigned __int16 *)v195 + *(unsigned __int16 *)(a3 + 656);
    if ( a3 != *(_QWORD *)(v15 + 32) )
      v42 += 2;
    if ( v42 > 0xFFFE )
    {
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal((__int64)a1, 0xC0000106, 0xA28DAu);
      NtfsRaiseStatusInternal((__int64)a1, -1073741562, 0, 0, 665818);
    }
    TxfSetupTransactionContextForCreate((__int64)a1, v13, 1, *(_QWORD *)(a3 + 184));
    if ( (*(_DWORD *)(v13 + 156) & 0x400000) != 0 )
    {
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal((__int64)a1, 0xC0190001, 0xA28EBu);
      NtfsRaiseStatusInternal((__int64)a1, -1072103423, 0, 0, 665835);
    }
    ullOffset = (void *)a1[50].ullOffset;
    if ( ullOffset )
    {
      v44 = *(_QWORD *)(a3 + 184);
      v45 = *(_DWORD *)(v44 + 4);
      TxfPrepareFileForTxfLogging((__int64)a1, ullOffset, v44, 0, v13, 0, 1, 0);
      if ( (v45 & 0x40000) == 0 )
        NtfsRaiseStatusInternal((__int64)a1, -1073741608, 0, 0, 665870);
      v41 = v195;
    }
    a1[54].offset.cidContainer |= 6u;
    if ( !v168 && *(int *)(v15 + 4) >= 0 && (*(_DWORD *)(v13 + 156) & 0x20) != 0 )
    {
      v197 = 80;
      v46 = *(_QWORD *)(v13 + 232);
      if ( v46 && *(_WORD *)v46 >= 8u && (*(_DWORD *)(v46 + 4) & 8) != 0
        || (v47 = 1, (*(_DWORD *)(*(_QWORD *)(a3 + 184) + 16LL) & 0x400) == 0) )
      {
        v47 = 0;
      }
      if ( (unsigned __int8)FsRtlFindInTunnelCacheEx(
                              v15 + 4720,
                              *(_QWORD *)(*(_QWORD *)(a3 + 184) + 8LL),
                              v41,
                              v221,
                              &v221[2],
                              v47,
                              &v197,
                              v222) )
      {
        v170 = 1;
        v192 = 1;
        if ( LOBYTE(v222[9]) )
        {
          NtfsAcquireExclusiveScbEx((__int64)a1, *(_QWORD *)(v15 + 160), 0);
          *(_DWORD *)(v13 + 156) |= 0x80u;
          *(_DWORD *)(v13 + 196) |= 0x80000u;
        }
      }
    }
    if ( (*(_DWORD *)(v15 + 4504) & 0x10) != 0 )
    {
      OwnerSecurityDescriptor = RtlGetOwnerSecurityDescriptor((PSECURITY_DESCRIPTOR)(v191 + 7), &Owner, OwnerDefaulted);
      v180 = OwnerSecurityDescriptor;
      if ( OwnerSecurityDescriptor < 0 )
      {
        if ( NtfsStatusDebugFlags
          && (unsigned int)OwnerSecurityDescriptor < 0xFFFFFFED
          && OwnerSecurityDescriptor != -1073741802
          && (unsigned int)(OwnerSecurityDescriptor + 2147483643) > 1
          && OwnerSecurityDescriptor != -1073741807
          && OwnerSecurityDescriptor != -1073741608 )
        {
          NtfsStatusTraceAndDebugInternal((__int64)a1, OwnerSecurityDescriptor, 0xA296Bu);
        }
        NtfsRaiseStatusInternal((__int64)a1, OwnerSecurityDescriptor, 0, 0, 665963);
      }
      if ( !Owner )
      {
        if ( NtfsStatusDebugFlags )
          NtfsStatusTraceAndDebugInternal((__int64)a1, 0xC000005A, 0xA2970u);
        NtfsRaiseStatusInternal((__int64)a1, -1073741734, 0, 0, 665968);
      }
      OwnerId = NtfsGetOwnerId(a1, Owner, 1, 0);
      v194 = (PVOID *)NtfsInitializeQuotaControlBlock(v15, OwnerId);
      NtfsAcquireQuotaControl((__int64)a1, (__int64)v194);
    }
    *(_QWORD *)v185 = NtfsAllocateMftRecord((__int64)a1, v15, 0);
    NtfsPinMftRecord((__int64)a1, v15, v185, 1, &Bcb, &v193, (union _LARGE_INTEGER)&v208);
    HIWORD(v185[1]) = *((_WORD *)v193 + 8);
    if ( !HIWORD(v185[1]) )
      HIWORD(v185[1]) = 1;
    v49 = *(_QWORD *)(a3 + 184);
    v50 = *(_QWORD *)(v49 + 320);
    if ( !v50 )
      v50 = *(_QWORD *)(*(_QWORD *)(v49 + 96) + 6248LL);
    LODWORD(CompletionRoutinea) = (v168 ? 2 : 0) | (((*(_BYTE *)(*(_QWORD *)(v13 + 176) + 2LL) & 2) != 0) + 36);
    v51 = NtfsCreateFcb((__int64)a1, v15, v50, *(_QWORD *)v185, CompletionRoutinea, &v198);
    v199 = v51;
    HIBYTE(v171) = (v198 & 4) != 0;
    if ( (v198 & 2) != 0 )
      NtfsRaiseStatusInternal((__int64)a1, -1073741608, 0, 0, 666048);
    v52 = v176 + 656;
    if ( (v198 & 1) != 0 )
    {
      ExAcquirePushLockSharedEx(v176 + 656, 0);
      _InterlockedDecrement((volatile signed __int32 *)(v51 + 28));
      ExReleasePushLockEx(v52, 0);
      HIBYTE(v171) = 0;
      v199 = 0;
      if ( (a1[3].offset.idxRecord & 0x80000000) != 0 )
      {
        NtfsAttachCorruption_BadOrOrphanFRS((__int64)a1, 2, 666080, v53, v185, 0, 0);
        NtfsAttachRepairInfoPriv((__int64)a1, 256, 0, (struct _LIST_ENTRY *)0x1A8000A29E0LL);
        if ( NtfsStatusDebugFlags )
          NtfsStatusTraceAndDebugInternal((__int64)a1, 0xC0000102, 0xA29E0u);
        NtfsRaiseStatusInternal((__int64)a1, -1073741566, (int)v185, 0, 666080);
      }
      NtfsAttachCorruption_BadOrOrphanFRS((__int64)a1, 2, 666096, v53, v185, 0, 0);
      NtfsAttachRepairInfoPriv((__int64)a1, 256, 0, (struct _LIST_ENTRY *)0x170000A29F0LL);
      NtfsPostAsyncRepairRequest((__int64)a1);
      a1[2].ullOffset |= 0x10000000uLL;
      NtfsRaiseStatusInternal((__int64)a1, -1073741608, 0, 0, 666101);
    }
    a1->offset.cidContainer |= 0x10000u;
    NtfsAcquireFcbWithPaging((__int64)a1, v51, 0, 4);
    ExAcquirePushLockSharedEx(v52, 0);
    _InterlockedDecrement((volatile signed __int32 *)(v51 + 28));
    ExReleasePushLockEx(v52, 0);
    HIBYTE(v171) = 0;
    LOBYTE(CompletionRoutineb) = 0;
    NtfsVerifyFileRecordIsNotInUse((__int64)a1, v51, (__int64)v193, (__int64 *)v185, (__int64)CompletionRoutineb);
    v54 = v176;
    NtfsInitializeMftRecord((__int64)a1, v176, (__int64)v185, (__int64)v193, Bcb, v168);
    *((_WORD *)v193 + 11) |= 1u;
    _InterlockedAdd((volatile signed __int32 *)(v51 + 24), 1u);
    v178 = 1;
    if ( Irp->AssociatedIrp.MasterIrp )
    {
      if ( *(_QWORD *)(v13 + 184) )
      {
        v34 = -1073741745;
        if ( !NtfsStatusDebugFlags )
          goto LABEL_123;
        v59 = 666186;
LABEL_122:
        NtfsStatusTraceAndDebugInternal(0, v34, v59);
LABEL_123:
        v180 = v34;
        goto LABEL_368;
      }
      v55 = *(_DWORD *)(*(_QWORD *)(v13 + 176) + 16LL);
      if ( (v55 & 0x200) != 0 || (v179 & 2) == 0 )
      {
        if ( (a1[2].offset.idxRecord & 0x100000) != 0
          || (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x20) == 0 )
        {
          v54 = v176;
        }
        else
        {
          v56 = *(_QWORD *)(v51 + 96);
          v57 = *(_QWORD *)(v56 + 248);
          v58 = *(unsigned __int16 *)(v57 + 6);
          if ( (unsigned __int16)v58 > 0x40u || (v58 & 1) != 0 )
            v58 = 0;
          v188 = v58;
          LOWORD(P[0]) = v58;
          P[1] = (PVOID)(v57 + 32);
          FileOffseta.LowPart = (unsigned __int16)v58 >> 1;
          LODWORD(CompletionRoutinec) = *(unsigned __int16 *)(v56 + 7872) >> 1;
          v54 = v176;
          McTemplateU0ppwwpidd_EtwWriteTransfer(
            FileOffseta.LowPart,
            (const EVENT_DESCRIPTOR *)create_c10805,
            KeGetCurrentThread(),
            v176,
            CompletionRoutinec,
            *(_QWORD *)(v56 + 7880),
            FileOffseta.QuadPart,
            v57 + 32,
            v51,
            *(_QWORD *)(v51 + 8),
            v55,
            v179);
        }
        v34 = -1073741790;
        if ( !NtfsStatusDebugFlags )
          goto LABEL_123;
        v59 = 666180;
        goto LABEL_122;
      }
    }
    if ( *(_QWORD *)(*(_QWORD *)(v51 + 96) + 104LL) )
    {
      v60 = v191;
      *(_DWORD *)(v51 + 280) = *((_DWORD *)v191 + 3);
      *(_QWORD *)(v51 + 208) = v60;
      v191 = 0;
    }
    v61 = v194;
    if ( v194 )
    {
      *(_DWORD *)(v51 + 264) = OwnerId;
      *(_QWORD *)(v51 + 120) = v61;
      v194 = 0;
    }
    v62 = *(_QWORD *)(a3 + 184);
    if ( (*(_DWORD *)(v62 + 4) & 8) == 0 )
      NtfsUpdateFcbInfoFromDisk((__int64)a1, 0, 0, v62, 0, 0);
    *(_QWORD *)(v51 + 232) = *(_QWORD *)(*(_QWORD *)(a3 + 184) + 232LL);
    v63 = *(_QWORD *)(v13 + 224);
    if ( (!v63 || (*(_BYTE *)(v63 + 2) & 0x40) == 0 || (*(_DWORD *)(v63 + 56) & 0x20) == 0) && !v168 )
      *(_WORD *)(*(_QWORD *)(v13 + 176) + 24LL) |= 0x20u;
    v64 = *(_QWORD *)(v13 + 224);
    if ( v64
      && ((v65 = *(_WORD *)(v64 + 2), (v65 & 1) != 0)
       || (v65 & 0x40) != 0
       && (*(_DWORD *)(v64 + 56) & 0x200) != 0
       && (*(_WORD *)(*(_QWORD *)(v13 + 176) + 24LL) & 0x200) != 0) )
    {
      *(_WORD *)(*(_QWORD *)(v13 + 176) + 24LL) |= 0x200u;
      v188 = 1;
    }
    else
    {
      *(_WORD *)(*(_QWORD *)(v13 + 176) + 24LL) &= ~0x200u;
      v188 = 0;
    }
    v66 = *(_QWORD *)(v13 + 176);
    if ( (*(_DWORD *)(v66 + 16) & 0x8000) == 0 && (*(_BYTE *)(v66 + 2) & 2) == 0 && (dword_1400956B8 & 0x400) == 0 )
    {
      v67 = *(_QWORD *)(v13 + 224);
      if ( v67 && (*(_BYTE *)(v67 + 2) & 0x40) != 0 && (*(_DWORD *)(v67 + 56) & 0x800) != 0 )
        v68 = *(_WORD *)(v66 + 24) & 0x800;
      else
        v68 = (unsigned __int8)*(_WORD *)(a3 + 460);
      if ( v68 )
      {
        v177 = 0;
        if ( (dword_1400956B8 & 0x80u) != 0 )
        {
          if ( *((_QWORD *)&xmmword_140095770 + 1) )
          {
            if ( a8 != 160 )
            {
              if ( byte_1400957C0 )
              {
                *(_OWORD *)P = 0;
                NtfsBuildNormalizedNameWithTxfIsolation((__int64)a1, *(_QWORD *)(v13 + 96), 0, 0, 0, 0, P);
                if ( P[1] )
                {
                  v69 = (*((__int64 (__fastcall **)(_QWORD, PIRP, _QWORD, PVOID *, char *))&xmmword_140095770 + 1))(
                          *(_QWORD *)(v13 + 176),
                          Irp,
                          0,
                          P,
                          &v177);
                  ExFreePoolWithTag(P[1], 0);
                  if ( v69 < 0 )
                  {
                    if ( NtfsStatusDebugFlags
                      && (unsigned int)v69 < 0xFFFFFFED
                      && v69 != -1073741802
                      && (unsigned int)(v69 + 2147483643) > 1
                      && v69 != -1073741807
                      && v69 != -1073741608 )
                    {
                      NtfsStatusTraceAndDebugInternal((__int64)a1, v69, 0xA2AF1u);
                    }
                    NtfsRaiseStatusInternal((__int64)a1, v69, 0, 0, 666353);
                  }
                }
              }
            }
          }
        }
        if ( v177 )
          *(_DWORD *)(*(_QWORD *)(v13 + 176) + 16LL) |= 0x8000u;
        else
          v173 = 1;
      }
    }
    v70 = *(_QWORD *)(v13 + 176);
    v71 = *(_WORD *)(v70 + 24);
    if ( v173 )
    {
      *(_WORD *)(v70 + 24) = v71 | 0x800;
      if ( (unsigned __int8)*(_WORD *)(a3 + 460) )
        v187[0] = (unsigned __int8)*(_WORD *)(a3 + 460);
      else
        v187[0] = 1;
    }
    else
    {
      *(_WORD *)(v70 + 24) = v71 & 0xF7FF;
    }
    v72 = *(_QWORD *)(v13 + 224);
    if ( !v72 || (*(_BYTE *)(v72 + 2) & 0x40) == 0 || (*(_DWORD *)(v72 + 56) & 0x2000) == 0 )
    {
      *(_WORD *)(*(_QWORD *)(v13 + 176) + 24LL) &= ~0x2000u;
      *(_WORD *)(*(_QWORD *)(v13 + 176) + 24LL) |= *(_WORD *)(*(_QWORD *)(a3 + 184) + 176LL) & 0x2000;
    }
    v73 = *(unsigned __int16 *)(*(_QWORD *)(v13 + 176) + 24LL);
    v183 = v73;
    v74 = *(_QWORD *)(v13 + 224);
    if ( v74 && (v75 = *(_WORD *)(v74 + 2), (v75 & 0x40) != 0) && (*(_DWORD *)(v74 + 56) & 0x20000) != 0 )
    {
      v76 = *(_QWORD *)(v13 + 224);
      v77 = v76;
      if ( (v75 & 0x20) != 0 )
      {
        if ( (*(_DWORD *)(v74 + 40) & 0x20000) != 0 )
        {
          v78 = 1;
          goto LABEL_180;
        }
        v77 = *(_QWORD *)(v13 + 224);
      }
      v78 = 0;
    }
    else
    {
      v78 = *(_DWORD *)(*(_QWORD *)(a3 + 184) + 176LL) & 0x20000;
      v76 = *(_QWORD *)(v13 + 224);
      v77 = v76;
    }
LABEL_180:
    if ( v78 )
    {
      v73 |= *(_DWORD *)(*(_QWORD *)(a3 + 184) + 176LL) & 0x20000;
      v183 = v73;
    }
    if ( v74 )
    {
      v79 = *(_WORD *)(v74 + 2);
      if ( (v79 & 0x20) != 0 && (v76 = v77, (*(_DWORD *)(v77 + 40) & 0x180000) != 0)
        || (v77 = v76, (v79 & 0x40) != 0) && (*(_DWORD *)(v76 + 56) & 0x180000) != 0 )
      {
        if ( (v79 & 0x20) != 0 )
        {
          v73 |= *(_DWORD *)(v76 + 40) & 0x180000;
LABEL_193:
          v183 = v73;
          goto LABEL_194;
        }
        goto LABEL_194;
      }
    }
    else
    {
      v77 = v76;
    }
    if ( v168 || (*(_DWORD *)(*(_QWORD *)(a3 + 184) + 176LL) & 0x180000) != 0x100000 )
    {
      v73 |= *(_DWORD *)(*(_QWORD *)(a3 + 184) + 176LL) & 0x180000;
      goto LABEL_193;
    }
LABEL_194:
    if ( v77 && (*(_BYTE *)(v77 + 2) & 0x20) != 0 )
    {
      v183 = *(_DWORD *)(v77 + 40) & 0x400000 | v73;
      IsEcpFromUserMode = FsRtlIsEcpFromUserMode((PVOID)v77);
      v81 = (unsigned __int8)v184;
      if ( !IsEcpFromUserMode )
        v81 = 1;
      v184 = v81;
    }
    if ( v168 && (dword_140095AD4 & 1) != 0 && (v82 = *(_QWORD *)(a3 + 184), (*(_DWORD *)(v82 + 16) & 0x400) != 0) )
    {
      v83 = 1;
    }
    else
    {
      v83 = 0;
      v82 = *(_QWORD *)(a3 + 184);
    }
    v182 = v83;
    if ( v168 )
      v84 = *(_BYTE *)(v82 + 36);
    else
      v84 = 0;
    v85 = v83 ^ ((unsigned __int8)v83 ^ (unsigned __int8)(2 * v84)) & 0xE;
    v182 = v85;
    v86 = v85;
    if ( *(_BYTE *)(v82 + 38) )
    {
      v87 = v176;
      v88 = (struct _ERESOURCE *)(v176 + 10688);
      ExAcquireResourceSharedLite((PERESOURCE)(v176 + 10688), 1u);
      LOBYTE(v171) = 1;
      v89 = *(unsigned __int8 *)(*(_QWORD *)(a3 + 184) + 38LL);
      if ( (*(_DWORD *)(*(_QWORD *)(v87 + 8 * v89 + 10904) + 4LL) & 2) == 0 )
      {
        v85 ^= ((unsigned __int16)v85 ^ (unsigned __int16)((_WORD)v89 << 8)) & 0xF00;
        v182 = v85;
      }
      v86 = v85;
      ExReleaseResourceLite(v88);
      LOBYTE(v171) = 0;
    }
    v90 = (v86 >> 8) & 0xF;
    if ( v90 && (*(_DWORD *)(v176 + 10896) & 1) != 0 )
    {
      v91 = (struct _ERESOURCE *)(v176 + 10688);
      ExAcquireResourceExclusiveLite((PERESOURCE)(v176 + 10688), 1u);
      LOBYTE(v171) = 1;
      if ( (*(_DWORD *)(v176 + 10896) & 1) != 0
        && (*(_QWORD *)(v51 + 8) & 0xFFFFFFFFFFFFuLL) < *(_QWORD *)(v176 + 11528) )
      {
        v92 = *(unsigned __int16 *)(v176 + 11524);
        if ( _bittest(&v92, v90) )
        {
          if ( *(int *)(v176 + 11520) >= 0 )
            *(_DWORD *)(v176 + 11520) = -1073740624;
        }
      }
      ExReleaseResourceLite(v91);
      LOBYTE(v171) = 0;
    }
    v93 = *(_QWORD *)(v13 + 224);
    if ( v93 && (*(_BYTE *)(v93 + 2) & 0x10) != 0 )
      v94 = *(_QWORD **)(v93 + 32);
    else
      v94 = v202;
    if ( v93 )
    {
      if ( *(char *)(v93 + 2) >= 0 )
        LOBYTE(v95) = 0;
      else
        v95 = *(_DWORD *)(v93 + 60);
      if ( (v95 & 1) != 0 )
        v96 = *(_DWORD *)(v93 + 76);
      else
        LOBYTE(v96) = 0;
      if ( (v96 & 1) != 0 )
      {
        if ( (*(_DWORD *)(v93 + 80) & 1) != 0 )
        {
          if ( (dword_140095AD4 & 1) == 0 )
            goto LABEL_236;
          v97 = v85 | 1;
        }
        else
        {
          v97 = v85 & 0xFFFFFFFE;
        }
        v182 = v97;
      }
    }
LABEL_236:
    NtfsInitializeFcbAndStdInfo(
      (__int64)a1,
      v51,
      v168,
      0,
      v173,
      v188,
      v183,
      &v182,
      v184,
      v164,
      (unsigned __int64)v222 & -(__int64)(v170 != 0),
      v94);
    v34 = TxfOpenFileProcessing(
            (__int64)a1,
            v51,
            0,
            0,
            *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v13 + 176) + 8LL) + 8LL) + 20LL) | 2u,
            0,
            *(_QWORD *)(*(_QWORD *)(v13 + 176) + 48LL),
            v13,
            0);
    v180 = v34;
    if ( !v34 )
    {
      v98 = *(_QWORD *)(v13 + 224);
      if ( v98 )
      {
        if ( (*(_BYTE *)(v98 + 2) & 0x10) != 0 )
        {
          v99 = v179;
          if ( v94[1] == -1 )
          {
            v99 = v179 | 0x40;
            v179 |= 0x40u;
          }
          if ( v94[2] == -1 )
          {
            v99 |= 0x10u;
            v179 = v99;
          }
          if ( v94[3] == -1 )
            v179 = v99 | 0x20;
          *(_WORD *)(v98 + 4) |= 0x10u;
        }
        v100 = *(_QWORD *)(v13 + 224);
        if ( (*(_BYTE *)(v100 + 2) & 0x20) != 0 )
          *(_WORD *)(v100 + 4) |= 0x20u;
        if ( (v182 & 1) != 0 )
        {
          v101 = *(_QWORD *)(v13 + 224);
          if ( *(char *)(v101 + 2) >= 0 )
            LOBYTE(v102) = 0;
          else
            v102 = *(_DWORD *)(v101 + 60);
          if ( (v102 & 1) != 0 )
            *(_DWORD *)(v101 + 84) |= 1u;
        }
      }
      if ( v168 )
      {
        v54 = v176;
        NtfsCreateIndex(a1, v51, 48, 1, *(_DWORD *)(v176 + 352), *(_BYTE *)(v176 + 348), 0, v187[0], 1, 0);
        v103 = v179;
      }
      else
      {
        v103 = v179;
        if ( (v179 & 2) == 0 )
        {
          v202 = (_QWORD *)*(int *)(*(_QWORD *)(v51 + 96) + 360LL);
          NtfsConditionallyUpdateQuota((__int64)a1, v51, (__int64)&v202, 0, 1);
          memset(v220, 0, 0x58u);
          v175 = 1;
          NtfsCreateAttributeWithValue(a1, v51, 0x80u, 0, 0, 0, v187[0], 0, 0, v220);
          NtfsCleanupAttributeContext(v104, v220);
          v175 = 0;
          *(_QWORD *)(v51 + 160) = 0;
          *(_QWORD *)(v51 + 168) = 0;
          *(_DWORD *)(v13 + 196) |= 0x200000u;
        }
        v54 = v176;
      }
      Lcb = NtfsCreateLcb((__int64)a1, a3, v51, v195, 0, 0);
      v189 = Lcb;
      v203 = Lcb;
      v106 = *(_DWORD *)(v13 + 156) & 0x40;
      if ( a8 == 160 )
      {
        v107 = v103;
        if ( v106 )
        {
          v107 = v103 | 8;
          v108 = 0;
        }
        else
        {
          v108 = *v206 - *(_WORD *)v195;
        }
        v109 = NtfsOpenAttribute(
                 (__int64)a1,
                 *(_QWORD *)(v13 + 176),
                 v54,
                 (__int64)Lcb,
                 v51,
                 v108,
                 &NtfsFileNameIndex,
                 160,
                 2,
                 3,
                 1,
                 v107,
                 0,
                 (__int64 *)(v13 + 104),
                 v13,
                 (__int64 *)(v13 + 112));
      }
      else
      {
        if ( v106 )
          v110 = 0;
        else
          v110 = (unsigned __int16)*v206 - *(unsigned __int16 *)v195;
        v109 = NtfsOpenNewAttr(
                 (__int64)a1,
                 (__int64)Irp,
                 (__int64)Lcb,
                 v51,
                 v110,
                 (const UNICODE_STRING *)v207,
                 a8,
                 1,
                 v103,
                 &v169,
                 v13);
      }
      v180 = v109;
      v34 = v109;
      if ( v109 >= 0 )
      {
        v111 = *(_QWORD *)(v13 + 224);
        if ( v111 && (*(_BYTE *)(v111 + 2) & 0x40) != 0 )
        {
          *(_DWORD *)(v111 + 56) &= 0xFF254048;
          *(_WORD *)(*(_QWORD *)(v13 + 224) + 4LL) |= 0x40u;
        }
        v112 = *(_QWORD *)(v13 + 104);
        if ( !v168 )
        {
          if ( (*(_DWORD *)(v112 + 200) & 0x20) == 0 )
            NtfsUpdateScbFromAttribute((__int64)a1, *(_QWORD *)(v13 + 104), 0);
          v113 = *(_QWORD *)(v13 + 176);
          if ( (*(_DWORD *)(v113 + 16) & 8) == 0 )
            *(_DWORD *)(*(_QWORD *)(v113 + 48) + 80LL) |= 0x40u;
          if ( (*(_DWORD *)(v112 + 200) & 0x10) != 0 )
          {
            *(_QWORD *)(v51 + 160) = *(_QWORD *)(v112 + 472);
            *(_QWORD *)(v51 + 168) = *(_QWORD *)(v112 + 32);
          }
        }
        if ( a1[50].ullOffset )
        {
          WORD1(v213[0]) = 24;
          v213[1] = (__int64)&v223;
        }
        if ( *(int *)(*(_QWORD *)(a3 + 184) + 176LL) < 0
          && ((int)TxfConvertMungedNameToTxfFileId(0, (__int64)v195, 0) < 0
           || (a1[54].offset.cidContainer & 0x80008) == 0
           && _InterlockedCompareExchange(
                (volatile signed __int32 *)(*(_QWORD *)(*(_QWORD *)(a3 + 184) + 320LL) + 132LL),
                4,
                4)) )
        {
          if ( (a1[2].offset.idxRecord & 0x100000) == 0
            && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x20) != 0 )
          {
            v150 = *(_QWORD *)(a3 + 192);
            v151 = *(_QWORD *)(v150 + 248);
            v152 = *(_WORD *)(v151 + 6);
            if ( v152 > 0x40u || (v152 & 1) != 0 )
            {
              v153 = 0;
              v184 = 0;
            }
            else
            {
              v153 = *(_WORD *)(v151 + 6);
              v184 = v153;
            }
            LOWORD(v215) = v153;
            v216 = v151 + 32;
            v154 = *(_QWORD *)(a3 + 184);
            v155 = v153 >> 1;
            LODWORD(v167) = *(_DWORD *)(*(_QWORD *)(v154 + 320) + 132LL);
            LODWORD(v166) = *(_DWORD *)(v154 + 4);
            FileOffsetb.LowPart = v155;
            LODWORD(CompletionRoutined) = *(unsigned __int16 *)(v150 + 7872) >> 1;
            McTemplateU0ppwwpidd_EtwWriteTransfer(
              v155,
              (const EVENT_DESCRIPTOR *)create_c11501,
              KeGetCurrentThread(),
              v150,
              CompletionRoutined,
              *(_QWORD *)(v150 + 7880),
              FileOffsetb.QuadPart,
              v151 + 32,
              v154,
              *(_QWORD *)(v154 + 8),
              v166,
              v167);
          }
          if ( NtfsStatusDebugFlags )
            NtfsStatusTraceAndDebugInternal((__int64)a1, 0xC0000022, 0xA2CFCu);
          NtfsRaiseStatusInternal((__int64)a1, -1073741790, 0, 0, 666876);
        }
        v114 = BYTE1(v222[9]);
        if ( !v170 )
          v114 = 0;
        v115 = (__int64)v189;
        NtfsAddLink(
          (__int64)a1,
          (unsigned __int8)~*(_BYTE *)(*(_QWORD *)(v13 + 176) + 2LL) >> 7,
          v114,
          a3,
          v51,
          (__int64)v200,
          &v169,
          &v174,
          (__int64)(v189 + 19),
          (unsigned __int64)v213 & -(__int64)(a1[50].ullOffset != 0),
          (unsigned __int64)v221 & -(__int64)(v170 != 0),
          *v210);
        if ( a1[50].ullOffset )
        {
          v117 = 0;
          if ( (*(_DWORD *)(v13 + 156) & 0x20) != 0
            && ((v116 = *(_QWORD *)(v13 + 232)) != 0 && *(_WORD *)v116 >= 8u && (*(_DWORD *)(v116 + 4) & 8) != 0
             || (*(_DWORD *)(*(_QWORD *)(a3 + 184) + 16LL) & 0x400) == 0) )
          {
            v117 = 1;
          }
          v118 = v170 != 0;
          v170 = -v170;
          TxfNewFileCreate(
            a1,
            (_QWORD *)a3,
            (__int64)v200,
            v174,
            (unsigned __int64)v221 & -(__int64)v118,
            (unsigned __int16 *)v213,
            v117,
            v112,
            (__int64)&v169);
        }
        else
        {
          v119 = *(_QWORD *)(v51 + 320);
          if ( v119 != *(_QWORD *)(*(_QWORD *)(v119 + 16) + 6248LL) )
            TxfAddTxfDataAttribute((int)a1, v119, v51, (__int64)&v169, 0, 0, 0);
        }
        v120 = v174;
        *(_BYTE *)(*(_QWORD *)(v115 + 192) + 65LL) = v174;
        v200[65] = v120;
        if ( v120 == 2 )
        {
          RtlUpcaseUnicodeString((PUNICODE_STRING)(v115 + 72), (PCUNICODE_STRING)(v115 + 72), 0);
          v121 = (UNICODE_STRING *)(*(_QWORD *)(*(_QWORD *)(v13 + 176) + 48LL) + 88LL);
          RtlUpcaseUnicodeString(v121, v121, 0);
        }
        *(_DWORD *)(v51 + 184) = 0;
        *(_DWORD *)(v51 + 4) &= ~0x10u;
        *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v13 + 176) + 48LL) + 80LL) &= 0xFFF7CFFF;
        ClearFlagInterlocked((unsigned int *)(*(_QWORD *)(v13 + 112) + 4LL), 40894464);
        v122 = v208;
        v123 = Irp;
        NtfsAssignSecurity(
          a1,
          *(_QWORD *)(a3 + 184),
          (__int64)Irp,
          v51,
          (union _LARGE_INTEGER *)v193,
          Bcb,
          v208.QuadPart,
          &v169);
        if ( v169 )
        {
          v125 = v176;
        }
        else
        {
          v124 = (union _LARGE_INTEGER *)v193;
          QuadPart = v122.QuadPart;
          v125 = v176;
          v124[1] = NtfsWriteLog(
                      (__int64)a1,
                      *(_QWORD *)(v176 + 48),
                      Bcb,
                      2,
                      (__int64 *)v193,
                      *((_DWORD *)v193 + 6),
                      0,
                      0,
                      0,
                      QuadPart,
                      0,
                      0,
                      *(_DWORD *)(v176 + 360));
          v169 = 1;
          v123 = Irp;
        }
        v126 = *(_QWORD *)(v13 + 224);
        if ( v126 && (*(_BYTE *)(v126 + 2) & 2) != 0 )
        {
          v127 = NtfsSetReparsePointInternal(
                   (__int64)a1,
                   (__int64)v123,
                   v112,
                   *(_QWORD *)(v13 + 112),
                   0,
                   0,
                   0,
                   *(unsigned __int16 *)(v126 + 6),
                   *(PREPARSE_DATA_BUFFER *)(v126 + 8));
          v180 = v127;
          v128 = *(_QWORD *)(v13 + 224);
          if ( v127 < 0 )
          {
            if ( !_bittest16((const signed __int16 *)(v128 + 2), 8u) )
            {
              if ( NtfsStatusDebugFlags
                && (unsigned int)v127 < 0xFFFFFFED
                && v127 != -1073741802
                && (unsigned int)(v127 + 2147483643) > 1
                && v127 != -1073741807
                && v127 != -1073741608 )
              {
                NtfsStatusTraceAndDebugInternal((__int64)a1, v127, 0xA2DA9u);
              }
              NtfsRaiseStatusInternal((__int64)a1, v127, 0, 0, 667049);
            }
          }
          else
          {
            *(_WORD *)(v128 + 4) |= 2u;
            *(_DWORD *)(v13 + 196) |= 0x100000u;
          }
        }
        MasterIrp = Irp->AssociatedIrp.MasterIrp;
        if ( MasterIrp )
          NtfsAddEa(
            (__int64)a1,
            v125,
            v51,
            (struct _FILE_FULL_EA_INFORMATION *)MasterIrp,
            *(_DWORD *)(*(_QWORD *)(v13 + 176) + 32LL),
            (__int64)&Irp->IoStatus);
        v130 = *(_QWORD *)(v13 + 224);
        if ( !v130 || !_bittest16((const signed __int16 *)(v130 + 2), 9u) )
          NtfsUpdateFcbTimestamps(*(_QWORD *)(a3 + 184), -1610612720);
        if ( (*(_DWORD *)(v51 + 4) & 4) != 0 )
        {
          v131 = *(__int64 *)(v112 + 24) >> *(_DWORD *)(*(_QWORD *)(v112 + 192) + 488LL);
          NtfsPreloadAllocationInternal((__int64)a1, v112, 0, 0, v131, 0);
          if ( !NtfsLookupLastNtfsMcbEntry(v112 + 400, &v209, &v214) || v209 + 1 != v131 )
          {
            NtfsAttachCorruption_BadOrOrphanFRS((__int64)a1, 2, 667107, v132, (_DWORD *)(v51 + 8), v51, 0);
            NtfsAttachRepairInfoPriv((__int64)a1, 256, 0, (struct _LIST_ENTRY *)0x6A000A2DE3LL);
            if ( NtfsStatusDebugFlags )
              NtfsStatusTraceAndDebugInternal((__int64)a1, 0xC0000102, 0xA2DE3u);
            NtfsRaiseStatusInternal((__int64)a1, -1073741566, v51 + 8, v51, 667107);
          }
          v133 = v112;
          v134 = Irp;
          NtfsPrepareForCriticalIo((_DWORD)a1, (_DWORD)Irp, v133, 0, *(_QWORD *)(v125 + 7776), 3);
        }
        else
        {
          v134 = Irp;
        }
        v34 = FsRtlCheckOplockEx((POPLOCK)(a3 + 88), v134, 0x10u, 0, 0, 0);
        v180 = v34;
        if ( v34 < 0 )
        {
          if ( NtfsStatusDebugFlags
            && (unsigned int)v34 < 0xFFFFFFED
            && v34 != -1073741802
            && (unsigned int)(v34 + 2147483643) > 1
            && v34 != -1073741807
            && v34 != -1073741608 )
          {
            NtfsStatusTraceAndDebugInternal(0, v34, 0xA2E04u);
          }
          goto LABEL_327;
        }
        *(_QWORD *)(v13 + 96) = v51;
        NtfsEncryptionCreateCallback(
          (__int64)a1,
          (__int64)v134,
          *(_QWORD *)(v13 + 104),
          *(_QWORD *)(v13 + 112),
          *(_QWORD *)(a3 + 184),
          v13,
          1);
        *(_QWORD *)(v13 + 96) = 0;
        if ( *(_BYTE *)(v51 + 232) && (int)NtfsSetDesiredStorageClass((__int64)a1, v51, v51 + 232) >= 0 )
          *(_DWORD *)(v13 + 196) |= 0x1000000u;
        v135 = *(_QWORD *)(v13 + 224);
        v136 = (__int64)v189;
        if ( v135 && _bittest16((const signed __int16 *)(v135 + 2), 0xCu) )
        {
          NtfsUpdateDuplicateInfo((__int64)a1, v51, (__int64)v189, a3);
          *(_DWORD *)(v13 + 196) |= 0x80000000;
        }
        NtfsPostUsnChangeWithOverrideOption((__int64)a1, *(_QWORD *)(v13 + 104), *(_DWORD *)(v13 + 196), 0, 0, 0, 0);
        v137 = *(_QWORD *)(v13 + 224);
        if ( v137 && *(int *)(v13 + 196) < 0 )
          *(_WORD *)(v137 + 4) |= 0x800u;
        v138 = *(_WORD **)(v13 + 104);
        if ( *v138 == 1795 && !v138[328] && *(_WORD *)(a3 + 656) )
          NtfsUpdateNormalizedName((__int64)a1, a3, (__int64)v138, v200, 0);
        if ( a1[30].ullOffset )
        {
          NtfsWriteUsnJournalChanges((__int64)a1);
          NtfsCheckpointCurrentTransaction((__int64)a1);
        }
        v139 = *(_QWORD *)(v13 + 224);
        if ( v139 )
        {
          if ( (*(_BYTE *)(v139 + 2) & 0x10) != 0 )
          {
            **(_QWORD **)(v139 + 32) = *(_QWORD *)(v51 + 128);
            *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v13 + 224) + 32LL) + 8LL) = *(_QWORD *)(v51 + 152);
            *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v13 + 224) + 32LL) + 16LL) = *(_QWORD *)(v51 + 136);
            *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v13 + 224) + 32LL) + 24LL) = *(_QWORD *)(v51 + 144);
            *(_WORD *)(*(_QWORD *)(v13 + 224) + 4LL) |= 0x100u;
          }
          v140 = *(_QWORD *)(v13 + 224);
          if ( *(_WORD *)v140 >= 0x2Cu )
          {
            *(_DWORD *)(v140 + 40) = *(_DWORD *)(v51 + 176);
            *(_WORD *)(*(_QWORD *)(v13 + 224) + 4LL) |= 0x200u;
          }
          v139 = *(_QWORD *)(v13 + 224);
          if ( *(_WORD *)v139 >= 0x38u )
          {
            *(_QWORD *)(v139 + 48) = *(_QWORD *)(v51 + 288);
            v139 = 4096;
            *(_WORD *)(*(_QWORD *)(v13 + 224) + 4LL) |= 0x1000u;
          }
        }
        if ( (*(_DWORD *)(v13 + 156) & 0x40) == 0 )
        {
          v141 = *(_QWORD *)(v13 + 224);
          if ( !v141 || !_bittest16((const signed __int16 *)(v141 + 2), 0xAu) )
            NtfsReportDirNotify(
              (__int64)a1,
              *(_QWORD *)(*(_QWORD *)(v13 + 112) + 72LL),
              *(_QWORD *)(v51 + 96),
              (unsigned __int16 *)(*(_QWORD *)(v13 + 112) + 16LL),
              *(unsigned __int16 *)(*(_QWORD *)(v13 + 112) + 32LL),
              0,
              v168 + 1,
              1,
              *(_QWORD *)(a3 + 184),
              0);
        }
        if ( *(int *)(v13 + 196) < 0 )
        {
          *(_DWORD *)(v51 + 184) = 0;
          *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v13 + 176) + 48LL) + 80LL) &= 0xFFF7CFFF;
          ClearFlagInterlocked((unsigned int *)(*(_QWORD *)(v13 + 112) + 4LL), 40894464);
        }
        if ( !*(_DWORD *)(v13 + 76)
          || (*(_DWORD *)(v13 + 156) & 0x201000) != 0
          || (v179 & 0x20000) != 0
          || (LOBYTE(v139) = *(_BYTE *)(*(_QWORD *)(v136 + 192) + 65LL) & 3, (_BYTE)v139 == 2)
          || a1[50].ullOffset )
        {
          v54 = v176;
        }
        else
        {
          if ( (*(_DWORD *)(v136 + 4) & 0x20) != 0 )
          {
            NtfsRemoveHashEntry(
              (__int64)a1,
              (_DWORD *)(*(_QWORD *)(*(_QWORD *)(v136 + 48) + 96LL) + 4968LL),
              *(_DWORD *)(v136 + 184),
              v136);
            *(_DWORD *)(v136 + 184) = 0;
            ClearFlagInterlocked((unsigned int *)(v136 + 4), 32);
          }
          v54 = v176;
          NtfsInsertPrefixHashEntry(
            (__int64)a1,
            (_DWORD *)(v176 + 4968),
            v136,
            *(_DWORD *)(v13 + 76),
            *(_DWORD *)(v13 + 72));
        }
        if ( !*(_QWORD *)(v13 + 184) )
          NtfsInsertPrefix(v139, v136);
        Irp->IoStatus.Information = 2;
      }
LABEL_368:
      if ( Bcb )
      {
        CcUnpinData(Bcb);
        Bcb = 0;
      }
      NtfsDecrementFcbCloseCount(v51);
      if ( (*(_DWORD *)(v13 + 156) & 0x80u) != 0 )
      {
        NtfsReleaseFcbEx((__int64)a1, *(_QWORD *)(*(_QWORD *)(v54 + 160) + 184LL), 0);
        *(_DWORD *)(v13 + 156) &= ~0x80u;
      }
      if ( (_QWORD *)v221[3] != &v221[7] )
        ExFreePoolWithTag((PVOID)v221[3], 0);
      if ( v191 )
        NtfsDereferenceSharedSecurity(&v191);
      if ( v34 >= 0 )
        goto LABEL_419;
      v142 = (PVOID *)v210;
      if ( *v210 )
      {
        NtfsCleanupIndexContext((__int64)a1, *v210);
        ExFreeToLookasideListEx(&NtfsIndexContextLookasideList, *v142);
        *v142 = 0;
      }
      v143 = *(_QWORD *)(v13 + 104);
      if ( v143 && *(_QWORD *)(v13 + 112) )
        NtfsBackoutFailedOpensPriv(
          (__int64)a1,
          *(_QWORD *)(*(_QWORD *)(v13 + 176) + 48LL),
          v51,
          v143,
          (__int16 **)(v13 + 112));
      if ( v194 )
        NtfsDereferenceQuotaControlBlock(v54, &v194, 0);
      if ( v51 )
      {
        *(_DWORD *)(v51 + 4) &= ~8u;
        ExAcquirePushLockExclusiveEx(a1[13].ullOffset + 656, 0);
        *(_DWORD *)(v51 + 4) |= 0x2000001u;
        ExReleasePushLockEx(a1[13].ullOffset + 656, 0);
        a1[2].ullOffset |= 0x20uLL;
        NextChildScb = NtfsGetNextChildScb(v51, 0, 1);
        if ( NextChildScb )
        {
          while ( 1 )
          {
            if ( *((_BYTE *)NextChildScb + 460) || (NextChildScb[64] & 1) != 0 )
              NextChildScb[58] = 0;
            if ( (NextChildScb[25] & 0x20000) != 0 && (__int64)NextChildScb[3] > 0 && (__int64)NextChildScb[58] > 0 )
              NextChildScb[58] = 0;
            NextChildScb[3] = 0;
            if ( (NextChildScb[25] & 0x20000) == 0 || (__int64)NextChildScb[4] >= 0 )
              goto LABEL_406;
            v145 = 0;
            if ( (__int64)NextChildScb[58] <= 0 )
              v145 = NextChildScb[58];
            if ( v145 <= NextChildScb[5] )
              goto LABEL_406;
            if ( (NextChildScb[25] & 0x20000) != 0 )
            {
              v146 = NextChildScb[58];
              if ( v146 < v145 )
                goto LABEL_409;
              if ( NextChildScb[5] > v145 )
                break;
            }
LABEL_405:
            NextChildScb[5] = v145;
LABEL_406:
            NextChildScb[4] = 0;
            *((_DWORD *)NextChildScb + 50) = *((_DWORD *)NextChildScb + 50);
            if ( (NextChildScb[25] & 0x20000) != 0 )
            {
              v148 = NextChildScb[58];
              if ( v148 < 0 || (__int64)NextChildScb[5] > 0 && (!*(_QWORD *)(NextChildScb[36] + 16LL) || v148 > 0) )
                NextChildScb[58] = 0;
            }
            NextChildScb[5] = 0;
            *((_DWORD *)NextChildScb + 128) |= 0x40u;
            NextChildScb = NtfsGetNextChildScb(v51, (__int64)NextChildScb, 1);
            if ( !NextChildScb )
              goto LABEL_415;
          }
          if ( *(_QWORD *)(NextChildScb[36] + 16LL) && v145 != 0x7FFFFFFFFFFFFFFFLL )
          {
            v147 = (v145 + 4095) & 0xFFFFFFFFFFFFF000uLL;
            if ( v147 < v146 )
              NextChildScb[58] = v147;
            goto LABEL_405;
          }
LABEL_409:
          NextChildScb[58] = v145;
          goto LABEL_405;
        }
LABEL_415:
        *(_QWORD *)(v13 + 104) = 0;
        _InterlockedIncrement((volatile signed __int32 *)(a3 + 208));
        NtfsTeardownStructures((__int64)a1, v51, 0, v169, &v172);
        if ( v172 )
        {
          v51 = 0;
          v149 = 0;
        }
        else
        {
          v149 = (__int64)v189;
        }
        _InterlockedDecrement((volatile signed __int32 *)(a3 + 208));
      }
      else
      {
LABEL_419:
        v149 = (__int64)v189;
      }
      if ( v51 && v149 )
      {
        *v215 = v149;
        *(_QWORD *)(v13 + 96) = v51;
      }
      return (unsigned int)v34;
    }
LABEL_327:
    v54 = v176;
    goto LABEL_368;
  }
  return result;
}

```

## disassembly

```asm
0x1402376ac  mov     r11, rsp
0x1402376af  push    rbx
0x1402376b0  push    rsi
0x1402376b1  push    rdi
0x1402376b2  push    r12
0x1402376b4  push    r13
0x1402376b6  push    r14
0x1402376b8  push    r15
0x1402376ba  sub     rsp, 310h
0x1402376c1  mov     rax, cs:__security_cookie
0x1402376c8  xor     rax, rsp
0x1402376cb  mov     [rsp+348h+var_40], rax
0x1402376d3  mov     [rsp+348h+var_228], r9
0x1402376db  mov     r13, r8
0x1402376de  mov     [rsp+348h+Irp], rdx
0x1402376e6  mov     rdi, rcx
0x1402376e9  mov     rsi, [rsp+348h+arg_48]
0x1402376f1  mov     rax, [rsp+348h+arg_20]
0x1402376f9  mov     [rsp+348h+var_1F0], rax
0x140237701  mov     r12, [rsp+348h+arg_28]
0x140237709  mov     [rsp+348h+var_248], r12
0x140237711  mov     [rsp+348h+var_1C0], rcx
0x140237719  mov     [rsp+348h+var_188], r8
0x140237721  mov     rax, [rsp+348h+arg_30]
0x140237729  mov     [r11-1E8h], rax
0x140237730  mov     rax, [rsp+348h+arg_40]
0x140237738  mov     [rsp+348h+var_1D0], rax
0x140237740  mov     [rsp+348h+var_190], rax
0x140237748  mov     [rsp+348h+var_1C8], rsi
0x140237750  mov     rax, [rsp+348h+arg_50]
0x140237758  mov     [rsp+348h+var_1A0], rax
0x140237760  mov     [rsp+348h+var_180], rax
0x140237768  xor     r15d, r15d
0x14023776b  mov     ebx, r15d
0x14023776e  mov     [r11-270h], r15
0x140237775  mov     [r11-1E0h], r15
0x14023777c  mov     [r11-290h], r15
0x140237783  mov     [r11-258h], r15
0x14023778a  mov     [r11-238h], r15d
0x140237791  mov     [r11-23Ch], r15d
0x140237798  mov     [r11-250h], r15
0x14023779f  mov     [r11-268h], r15
0x1402377a6  mov     [r11-1F8h], r15
0x1402377ad  xorps   xmm0, xmm0
0x1402377b0  movups  xmmword ptr [rsp+348h+var_1B8], xmm0
0x1402377b8  mov     [r11-1A8h], r15
0x1402377bf  mov     [r11-1D8h], r15
0x1402377c6  mov     [r11-2C3h], r15b
0x1402377cd  mov     [r11-2C8h], r15b
0x1402377d4  mov     [r11-2C7h], r15b
0x1402377db  mov     [r11-2A4h], r15b
0x1402377e2  mov     [r11-2C1h], r15b
0x1402377e9  xor     edx, edx; Val
0x1402377eb  lea     r8d, [r15+70h]; Size
0x1402377ef  lea     rcx, [r11-118h]; void *
0x1402377f6  call    memset
0x1402377fb  xor     edx, edx; Val
0x1402377fd  lea     r8d, [r15+50h]; Size
0x140237801  lea     rcx, [rsp+348h+var_A8]; void *
0x140237809  call    memset
0x14023780e  xor     edx, edx; Val
0x140237810  lea     r8d, [r15+58h]; Size
0x140237814  lea     rcx, [rsp+348h+var_178]; void *
0x14023781c  call    memset
0x140237821  mov     r14, [r13+0C0h]
0x140237828  mov     [rsp+348h+var_2B8], r14
0x140237830  test    dword ptr [r14+4], 2000000h
0x140237838  jz      short loc_140237861
0x14023783a  mov     al, cs:NtfsStatusDebugFlags
0x140237840  test    al, al
0x140237842  jz      short loc_140237856
0x140237844  mov     edx, 0C00000A2h
0x140237849  xor     ecx, ecx
0x14023784b  mov     r8d, 0A2780h
0x140237851  call    NtfsStatusTraceAndDebugInternal
0x140237856  mov     eax, 0C00000A2h
0x14023785b  jmp     loc_14023A079
0x140237861  mov     eax, [r13+200h]
0x140237868  bt      eax, 1Ah
0x14023786c  jnb     short loc_140237894
0x14023786e  mov     al, cs:NtfsStatusDebugFlags
0x140237874  test    al, al
0x140237876  jz      short loc_14023788A
0x140237878  mov     edx, 0C0000189h
0x14023787d  xor     ecx, ecx
0x14023787f  mov     r8d, 0A278Eh
0x140237885  call    NtfsStatusTraceAndDebugInternal
0x14023788a  mov     eax, 0C0000189h
0x14023788f  jmp     loc_14023A079
0x140237894  bt      eax, 10h
0x140237898  jnb     short loc_1402378C0
0x14023789a  mov     al, cs:NtfsStatusDebugFlags
0x1402378a0  test    al, al
0x1402378a2  jz      short loc_1402378B6
0x1402378a4  mov     edx, 0C000026Eh
0x1402378a9  xor     ecx, ecx
0x1402378ab  mov     r8d, 0A2793h
0x1402378b1  call    NtfsStatusTraceAndDebugInternal
0x1402378b6  mov     eax, 0C000026Eh
0x1402378bb  jmp     loc_14023A079
0x1402378c0  mov     dword ptr [rdi+1F8h], 1Ch
0x1402378ca  lea     rax, [rsp+348h+var_F8]
0x1402378d2  mov     [rsp+348h+var_110], rax
0x1402378da  lea     rax, [rsp+348h+var_E0]
0x1402378e2  mov     [rsp+348h+var_100], rax
0x1402378ea  mov     [rsp+348h+var_118], 180000h
0x1402378f5  mov     [rsp+348h+var_108], 340000h
0x140237900  mov     eax, [rsi+9Ch]
0x140237906  test    al, 1
0x140237908  mov     ecx, 20000h
0x14023790d  cmovnz  ebx, ecx
0x140237910  mov     [rsp+348h+var_2AC], ebx
0x140237917  lea     rcx, [rsp+348h+var_2C8]
0x14023791f  mov     [rsp+348h+ReparseBuffer], rcx
0x140237924  lea     rcx, [rsp+348h+var_2AC]
0x14023792c  mov     qword ptr [rsp+348h+BufferLength], rcx
0x140237931  mov     dword ptr [rsp+348h+FileOffset], eax
0x140237935  lea     rax, [rsp+348h+arg_38]
0x14023793d  mov     [rsp+348h+PostIrpRoutine], rax
0x140237942  lea     rax, [rsp+348h+var_1E8]
0x14023794a  mov     [rsp+348h+CompletionRoutine], rax
0x14023794f  xor     r9d, r9d
0x140237952  mov     r8, r14
0x140237955  mov     rdx, [rsi+0B0h]
0x14023795c  mov     rcx, rdi
0x14023795f  call    NtfsCheckValidAttributeAccess
0x140237964  mov     [rsp+348h+var_2A8], eax
0x14023796b  test    eax, eax
0x14023796d  js      loc_14023A079
0x140237973  cmp     [rsp+348h+var_2C8], r15b
0x14023797b  jz      short loc_1402379EC
0x14023797d  mov     rax, [rsi+0B0h]
0x140237984  movzx   edx, word ptr [rax+18h]
0x140237988  mov     ebx, 100h
0x14023798d  test    bx, dx
0x140237990  jz      short loc_1402379A8
0x140237992  mov     al, cs:NtfsStatusDebugFlags
0x140237998  test    al, al
0x14023799a  jz      loc_140237A33
0x1402379a0  mov     r8d, 0A27D5h
0x1402379a6  jmp     short loc_140237A27
0x1402379a8  mov     rax, [rsi+0E0h]
0x1402379af  test    rax, rax
0x1402379b2  jz      loc_140237A42
0x1402379b8  movzx   ecx, word ptr [rax+2]
0x1402379bc  test    cl, 0Dh
0x1402379bf  jnz     short loc_1402379DA
0x1402379c1  mov     r15d, 40h ; '@'
0x1402379c7  test    r15b, cl
0x1402379ca  jz      short loc_140237A48
0x1402379cc  bt      dword ptr [rax+38h], 9
0x1402379d1  jnb     short loc_140237A48
0x1402379d3  bt      dx, 9
0x1402379d8  jnb     short loc_140237A48
0x1402379da  mov     al, cs:NtfsStatusDebugFlags
0x1402379e0  test    al, al
0x1402379e2  jz      short loc_140237A33
0x1402379e4  mov     r8d, 0A27E5h
0x1402379ea  jmp     short loc_140237A27
0x1402379ec  mov     rcx, [rsi+0E0h]
0x1402379f3  test    rcx, rcx
0x1402379f6  jz      short loc_140237A3D
0x1402379f8  mov     al, [rcx+2]
0x1402379fb  test    al, al
0x1402379fd  jns     short loc_140237A04
0x1402379ff  mov     eax, [rcx+3Ch]
0x140237a02  jmp     short loc_140237A07
0x140237a04  mov     eax, r15d
0x140237a07  test    al, 1
0x140237a09  jz      short loc_140237A10
0x140237a0b  mov     eax, [rcx+4Ch]
0x140237a0e  jmp     short loc_140237A13
0x140237a10  mov     eax, r15d
0x140237a13  test    al, 1
0x140237a15  jz      short loc_140237A3D
0x140237a17  mov     al, cs:NtfsStatusDebugFlags
0x140237a1d  test    al, al
0x140237a1f  jz      short loc_140237A33
0x140237a21  mov     r8d, 0A27F2h
0x140237a27  mov     edx, 0C000000Dh
0x140237a2c  xor     ecx, ecx
0x140237a2e  call    NtfsStatusTraceAndDebugInternal
0x140237a33  mov     eax, 0C000000Dh
0x140237a38  jmp     loc_14023A079
0x140237a3d  mov     ebx, 100h
0x140237a42  mov     r15d, 40h ; '@'
0x140237a48  mov     rcx, [rsi+0B0h]
0x140237a4f  test    dword ptr [rcx+10h], 1000h
0x140237a56  jz      short loc_140237A8A
0x140237a58  test    byte ptr [rcx+18h], 1
0x140237a5c  jz      short loc_140237A8A
0x140237a5e  test    [rcx+2], r15b
0x140237a62  jnz     short loc_140237A8A
0x140237a64  mov     al, cs:NtfsStatusDebugFlags
0x140237a6a  test    al, al
0x140237a6c  jz      short loc_140237A80
0x140237a6e  mov     edx, 0C0000121h
0x140237a73  xor     ecx, ecx
0x140237a75  mov     r8d, 0A27FEh
0x140237a7b  call    NtfsStatusTraceAndDebugInternal
0x140237a80  mov     eax, 0C0000121h
0x140237a85  jmp     loc_14023A079
0x140237a8a  mov     rdx, [r13+0B8h]
0x140237a91  test    dword ptr [rdx+0B0h], 10000000h
0x140237a9b  jz      short loc_140237B1C
0x140237a9d  mov     rax, [rsi+0B8h]
0x140237aa4  mov     [rsp+348h+CompletionRoutine], rax
0x140237aa9  mov     r9d, 1
0x140237aaf  mov     r8d, r9d
0x140237ab2  mov     rcx, rdi
0x140237ab5  call    TxfGetCurrentFileInfo
0x140237aba  bt      eax, 0Ah
0x140237abe  jnb     short loc_140237B1C
0x140237ac0  mov     rax, [rsi+0B8h]
0x140237ac7  mov     [rsp+348h+CompletionRoutine], rax
0x140237acc  mov     r9d, 1
0x140237ad2  xor     r8d, r8d
0x140237ad5  mov     rdx, [rsi+60h]
0x140237ad9  mov     rcx, rdi
0x140237adc  call    TxfGetCurrentFileInfo
0x140237ae1  mov     ecx, eax
0x140237ae3  call    cs:__imp_FsRtlIsNonEmptyDirectoryReparsePointAllowed
0x140237aea  nop     dword ptr [rax+rax+00h]
0x140237aef  xor     r9d, r9d
0x140237af2  test    al, al
0x140237af4  jnz     short loc_140237B1F
0x140237af6  mov     al, cs:NtfsStatusDebugFlags
0x140237afc  test    al, al
0x140237afe  jz      short loc_140237B12
0x140237b00  mov     edx, 0C0000281h
0x140237b05  xor     ecx, ecx
0x140237b07  mov     r8d, 0A2813h
0x140237b0d  call    NtfsStatusTraceAndDebugInternal
0x140237b12  mov     eax, 0C0000281h
0x140237b17  jmp     loc_14023A079
0x140237b1c  xor     r9d, r9d
0x140237b1f  mov     rcx, [r13+0B8h]
0x140237b26  test    [rcx+4], ebx
0x140237b29  jz      short loc_140237B31
0x140237b2b  cmp     r13, [r14+20h]
0x140237b2f  jnz     short loc_140237B46
0x140237b31  mov     eax, [rsp+348h+arg_38]
0x140237b38  add     eax, 0FFFFFF80h
0x140237b3b  test    eax, 0FFFFFFDFh
0x140237b40  jz      loc_140237C61
0x140237b46  cmp     [rcx+0B0h], r9d
0x140237b4d  jge     short loc_140237B81
0x140237b4f  mov     rcx, [rcx+140h]
0x140237b56  mov     edx, 4
0x140237b5b  mov     eax, edx
0x140237b5d  lock cmpxchg [rcx+84h], edx
0x140237b65  test    eax, eax
0x140237b67  jnz     short loc_140237B81
0x140237b69  xor     r8d, r8d
0x140237b6c  mov     rdx, r12
0x140237b6f  xor     ecx, ecx
0x140237b71  call    TxfConvertMungedNameToTxfFileId
0x140237b76  xor     r9d, r9d
0x140237b79  test    eax, eax
0x140237b7b  jns     loc_140237C61
0x140237b81  mov     eax, [rdi+10h]
0x140237b84  bt      rax, 14h
0x140237b89  jb      loc_140237C3C
0x140237b8f  mov     rax, cs:Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits
0x140237b96  test    al, 20h
0x140237b98  jz      loc_140237C3C
0x140237b9e  mov     r11, [r13+0B8h]
0x140237ba5  mov     rbx, [r11+60h]
0x140237ba9  mov     rdx, [rbx+0F8h]
0x140237bb0  movzx   eax, word ptr [rdx+6]
0x140237bb4  cmp     ax, r15w
0x140237bb8  ja      short loc_140237BBE
0x140237bba  test    al, 1
0x140237bbc  jz      short loc_140237BC1
0x140237bbe  mov     eax, r9d
0x140237bc1  mov     rcx, [r11+140h]
0x140237bc8  add     rdx, 20h ; ' '
0x140237bcc  movzx   r9d, ax
0x140237bd0  shr     r9d, 1
0x140237bd3  movzx   r10d, word ptr [rbx+1EC0h]
0x140237bdb  shr     r10d, 1
0x140237bde  mov     r8, gs:188h
0x140237be7  mov     eax, [rsp+348h+arg_38]
0x140237bee  mov     dword ptr [rsp+348h+var_2E8], eax
0x140237bf2  mov     eax, [rcx+84h]
0x140237bf8  mov     dword ptr [rsp+348h+var_2F0], eax
0x140237bfc  mov     eax, [r11+4]
0x140237c00  mov     dword ptr [rsp+348h+var_2F8], eax
0x140237c04  mov     rax, [r11+8]
0x140237c08  mov     qword ptr [rsp+348h+var_300], rax
0x140237c0d  mov     [rsp+348h+ReparseBuffer], r11
0x140237c12  mov     qword ptr [rsp+348h+BufferLength], rdx
0x140237c17  mov     dword ptr [rsp+348h+FileOffset], r9d
0x140237c1c  mov     rax, [rbx+1EC8h]
0x140237c23  mov     [rsp+348h+PostIrpRoutine], rax
0x140237c28  mov     dword ptr [rsp+348h+CompletionRoutine], r10d
0x140237c2d  mov     r9, rbx
0x140237c30  lea     rdx, create_c10289
0x140237c37  call    McTemplateU0ppwwpiddd_EtwWriteTransfer
0x140237c3c  mov     al, cs:NtfsStatusDebugFlags
  ... truncated ...
```
