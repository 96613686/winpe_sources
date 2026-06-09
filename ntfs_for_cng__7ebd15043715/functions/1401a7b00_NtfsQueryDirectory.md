# NtfsQueryDirectory

- ea: `0x1401a7b00`
- end: `0x1401aa53e`
- name: `NtfsQueryDirectory`
- size: `10814`
- prototype: `__int64 __fastcall(__int64, IRP *, __int64, __int64, unsigned int *)`
- caller_count: `1`
- callee_count: `50`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1401a7710`

## callees

- `0x140007ea0`
- `0x1400082b0`
- `0x140009c80`
- `0x14000c290`
- `0x14000c450`
- `0x14000ea70`
- `0x140012e70`
- `0x14001e810`
- `0x140020de0`
- `0x1400210e0`
- `0x1400211b0`
- `0x140021220`
- `0x140025830`
- `0x140027f50`
- `0x140037200`
- `0x140059250`
- `0x1400592c0`
- `0x1400592e0`
- `0x1400593c0`
- `0x1400596c0`
- `0x140059be0`
- `0x1400bdc7c`
- `0x1400bddcc`
- `0x1400bde2c`
- `0x1400bde74`
- `0x1400bdebc`
- `0x1400d2000`
- `0x1400d205c`
- `0x14011f48c`
- `0x140120620`
- `0x140120960`
- `0x140121a00`
- `0x140122300`
- `0x140140660`
- `0x1401413b0`
- `0x140153910`
- `0x140153ab0`
- `0x140166514`
- `0x14017db20`
- `0x14018994c`
- `0x140196ff0`
- `0x14019f220`
- `0x1401a7b00`
- `0x1401aa550`
- `0x1401aab20`
- `0x1401be91c`
- `0x1402239ec`
- `0x14023ae10`
- `0x14023b7bc`
- `0x14023b8a0`

## import_xrefs

- `ntoskrnl!FsRtlIsNameInUnUpcasedExpression` at `0x1401a9f5a`
- `ntoskrnl!FsRtlIsNameInUnUpcasedExpression` at `0x1401a9f5a`
- `ntoskrnl!FsRtlDoesNameContainWildCards` at `0x1401a7e44`
- `ntoskrnl!FsRtlDoesNameContainWildCards` at `0x1401aa431`
- `ntoskrnl!FsRtlDoesNameContainWildCards` at `0x1401a7e44`
- `ntoskrnl!FsRtlDoesNameContainWildCards` at `0x1401aa431`
- `ntoskrnl!ExConvertExclusiveToSharedLite` at `0x1401a97f7`
- `ntoskrnl!ExConvertExclusiveToSharedLite` at `0x1401a97f7`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1401a90a6`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1401a9c64`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1401aa4af`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1402ad9c3`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1401a90a6`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1401a9c64`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1401aa4af`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1402ad9c3`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x1402ad8e4`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x1402ad8e4`
- `ntoskrnl!ExReleasePushLockEx` at `0x1401a9143`
- `ntoskrnl!ExReleasePushLockEx` at `0x1401a96db`
- `ntoskrnl!ExReleasePushLockEx` at `0x1401a984b`
- `ntoskrnl!ExReleasePushLockEx` at `0x1401a9c7f`
- `ntoskrnl!ExReleasePushLockEx` at `0x1401aa4c9`
- `ntoskrnl!ExReleasePushLockEx` at `0x1402ad9dc`
- `ntoskrnl!ExReleasePushLockEx` at `0x1401a9143`
- `ntoskrnl!ExReleasePushLockEx` at `0x1401a96db`
- `ntoskrnl!ExReleasePushLockEx` at `0x1401a984b`
- `ntoskrnl!ExReleasePushLockEx` at `0x1401a9c7f`
- `ntoskrnl!ExReleasePushLockEx` at `0x1401aa4c9`
- `ntoskrnl!ExReleasePushLockEx` at `0x1402ad9dc`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1401aa2fd`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402ad969`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1401aa2fd`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402ad969`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1401a8d98`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1401a8d98`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401aa12b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401aa50a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401aa520`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402ada5c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402ada77`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401aa12b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401aa50a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401aa520`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402ada5c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402ada77`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1401a7d60`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1401a9e7f`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1401aa0a0`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1401a7d60`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1401a9e7f`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1401aa0a0`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401a8c40`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401a976f`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402ad99a`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402cb044`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401a8c40`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401a976f`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402ad99a`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402cb044`
- `ntoskrnl!ExRaiseStatus` at `0x1401a91f0`
- `ntoskrnl!ExRaiseStatus` at `0x1401a91f0`

## pseudocode

```c
__int64 __fastcall NtfsQueryDirectory(__int64 a1, IRP *a2, __int64 a3, __int64 a4, unsigned int *a5)
{
  unsigned int *LocalIndexCcb; // rdx
  __int64 CurrentStackLocation; // r8
  struct _UNICODE_STRING *v9; // rsi
  char v10; // r14
  char v11; // bl
  bool v12; // r15
  char v13; // r12
  char v14; // r14
  int v15; // edi
  unsigned __int16 v16; // r9
  char v17; // r8
  size_t Length; // rbx
  int v19; // esi
  unsigned int v20; // r8d
  __int64 QueryFileName; // rbx
  __int64 v22; // r8
  unsigned int *v23; // r14
  __int64 v24; // rcx
  int v25; // esi
  unsigned int v26; // eax
  unsigned int v27; // eax
  __int64 v28; // rcx
  bool v29; // al
  __int64 *v30; // r10
  char v31; // r15
  _DWORD *v32; // rax
  _WORD *v33; // rbx
  __int64 v34; // r12
  signed int v35; // eax
  bool v36; // r14
  signed int v37; // ebx
  __int64 v38; // rbx
  char *v39; // r15
  __int64 v40; // rdx
  __int64 v41; // rcx
  ULONG_PTR Information; // rcx
  __int64 v43; // rdi
  SIZE_T v44; // r8
  char *v45; // rcx
  size_t v46; // rax
  void *v47; // rdx
  char *v48; // rcx
  char *v49; // r14
  KPROCESSOR_MODE v50; // r12
  __int64 v51; // r15
  int v52; // ecx
  _QWORD *v53; // rcx
  _QWORD *v54; // rcx
  int v55; // eax
  int v56; // edx
  __int64 *v57; // rax
  __int64 v58; // rdx
  _QWORD *v59; // rcx
  unsigned int v60; // r12d
  _QWORD *v61; // rcx
  _QWORD *v62; // rcx
  __int64 v63; // r12
  int v64; // r8d
  int v65; // edx
  int *v66; // rcx
  IRP *v67; // r12
  unsigned int v68; // r9d
  int v69; // eax
  PVOID v70; // r12
  KPROCESSOR_MODE v71; // dl
  int v72; // eax
  int *v73; // rcx
  __int64 v74; // r9
  signed int restarted; // eax
  signed int v76; // ebx
  _QWORD *NextParentLcb; // rax
  __int64 v78; // rdi
  BOOLEAN v79; // bl
  PVOID v80; // rax
  __int64 ShortName; // rax
  __int64 v82; // rdi
  char v83; // bl
  _BYTE *v84; // rcx
  void *v85; // rdx
  void *v86; // rcx
  int v87; // eax
  int *v88; // rcx
  char EaSize; // al
  int *v90; // rcx
  char v91; // al
  int v92; // edx
  __int64 v93; // rax
  __int64 v94; // r14
  char v95; // di
  _BYTE *v96; // rcx
  void *v97; // rdx
  void *v98; // rcx
  struct _ERESOURCE *v99; // rcx
  int v100; // ecx
  PVOID v101; // r12
  KPROCESSOR_MODE v102; // dl
  char *v103; // rdi
  PVOID v104; // r12
  KPROCESSOR_MODE v105; // dl
  int v106; // eax
  int *v107; // rcx
  char v108; // al
  int v109; // eax
  int *v110; // rcx
  __int64 v111; // rax
  __int64 v112; // r9
  char IsEqual; // al
  _QWORD *v114; // rcx
  _QWORD *v115; // rax
  char v116; // r10
  unsigned __int64 v117; // r8
  unsigned __int64 v118; // r9
  __int64 v119; // rcx
  __int64 v120; // rdx
  __int64 v121; // rbx
  int v122; // ecx
  char v123; // di
  _BYTE *v124; // rcx
  void *v125; // rdx
  void *v126; // rcx
  int v127; // eax
  int *v128; // rcx
  char v129; // al
  char v130; // di
  _BYTE *v131; // rcx
  void *v132; // rdx
  void *v133; // rcx
  unsigned __int8 v134; // al
  unsigned int *v135; // rcx
  struct _ERESOURCE *v136; // rcx
  __int64 v137; // rcx
  _WORD *v138; // rbx
  __int64 v139; // rax
  __int64 v140; // r14
  __int64 v141; // rax
  __int64 v142; // r14
  __int64 v143; // rbx
  __int64 v144; // rbx
  int v145; // edx
  char *v146; // r15
  PWSTR Buffer; // rax
  int v148; // edx
  _QWORD *v149; // rcx
  PVOID v150; // rbx
  __int64 v151; // r15
  __int64 v152; // rbx
  unsigned int v154; // eax
  unsigned int v155; // ebx
  struct _ERESOURCE *v156; // rcx
  __int64 v157; // rbx
  int v158; // [rsp+20h] [rbp-238h]
  __int64 v159; // [rsp+28h] [rbp-230h]
  __int64 v160; // [rsp+28h] [rbp-230h]
  __int64 v161; // [rsp+28h] [rbp-230h]
  KPROCESSOR_MODE RequestorMode; // [rsp+50h] [rbp-208h]
  char v163; // [rsp+52h] [rbp-206h]
  char v164; // [rsp+53h] [rbp-205h] BYREF
  char v165; // [rsp+54h] [rbp-204h]
  BOOLEAN v166; // [rsp+55h] [rbp-203h]
  char v167; // [rsp+56h] [rbp-202h] BYREF
  char v168; // [rsp+57h] [rbp-201h]
  unsigned __int8 v169; // [rsp+58h] [rbp-200h]
  char v170; // [rsp+59h] [rbp-1FFh]
  PVOID v171; // [rsp+60h] [rbp-1F8h]
  unsigned int v172; // [rsp+68h] [rbp-1F0h]
  int v173; // [rsp+6Ch] [rbp-1ECh]
  bool v174; // [rsp+70h] [rbp-1E8h]
  char v175; // [rsp+71h] [rbp-1E7h]
  bool v176; // [rsp+72h] [rbp-1E6h]
  char v177; // [rsp+73h] [rbp-1E5h]
  unsigned int Size; // [rsp+74h] [rbp-1E4h]
  char Size_4; // [rsp+78h] [rbp-1E0h]
  char Size_5; // [rsp+79h] [rbp-1DFh]
  bool Size_6; // [rsp+7Ah] [rbp-1DEh]
  __int64 v182; // [rsp+80h] [rbp-1D8h]
  IRP *v183; // [rsp+88h] [rbp-1D0h]
  __int64 v184; // [rsp+90h] [rbp-1C8h]
  int v185; // [rsp+98h] [rbp-1C0h]
  __int64 v186; // [rsp+A0h] [rbp-1B8h]
  char v187; // [rsp+A8h] [rbp-1B0h]
  char v188; // [rsp+A9h] [rbp-1AFh]
  unsigned int v189; // [rsp+ACh] [rbp-1ACh]
  PVOID Entry; // [rsp+B0h] [rbp-1A8h] BYREF
  __int64 v191; // [rsp+B8h] [rbp-1A0h]
  __int64 v192; // [rsp+C0h] [rbp-198h]
  char *v193; // [rsp+C8h] [rbp-190h]
  __int64 v194; // [rsp+D0h] [rbp-188h] BYREF
  PVOID PoolWithTag; // [rsp+D8h] [rbp-180h]
  __int64 *v196; // [rsp+E0h] [rbp-178h] BYREF
  int v197; // [rsp+E8h] [rbp-170h]
  __int64 v198; // [rsp+F0h] [rbp-168h]
  unsigned int v199; // [rsp+F8h] [rbp-160h]
  unsigned int v200; // [rsp+FCh] [rbp-15Ch]
  int v201; // [rsp+100h] [rbp-158h] BYREF
  int v202; // [rsp+104h] [rbp-154h] BYREF
  int v203; // [rsp+108h] [rbp-150h] BYREF
  int v204; // [rsp+10Ch] [rbp-14Ch]
  int v205; // [rsp+110h] [rbp-148h]
  char *v206; // [rsp+118h] [rbp-140h]
  __int64 v207; // [rsp+120h] [rbp-138h]
  PVOID P; // [rsp+128h] [rbp-130h]
  struct _UNICODE_STRING Name; // [rsp+130h] [rbp-128h] BYREF
  int v210; // [rsp+140h] [rbp-118h]
  unsigned int *v211; // [rsp+148h] [rbp-110h]
  __int64 *v212; // [rsp+150h] [rbp-108h]
  __int64 v213; // [rsp+158h] [rbp-100h]
  _QWORD *v214; // [rsp+160h] [rbp-F8h]
  __int64 v215; // [rsp+168h] [rbp-F0h]
  unsigned int *v216; // [rsp+170h] [rbp-E8h]
  __int64 v217; // [rsp+178h] [rbp-E0h]
  unsigned int *v218; // [rsp+180h] [rbp-D8h]
  _OWORD v219[2]; // [rsp+188h] [rbp-D0h] BYREF
  __int64 v220; // [rsp+1A8h] [rbp-B0h]
  _QWORD Src[12]; // [rsp+1B0h] [rbp-A8h] BYREF

  v182 = a4;
  v186 = a3;
  v183 = a2;
  v207 = a1;
  v215 = a3;
  v217 = a4;
  LocalIndexCcb = a5;
  v171 = a5;
  v216 = a5;
  Entry = 0;
  v167 = 0;
  CurrentStackLocation = (__int64)a2->Tail.Overlay.CurrentStackLocation;
  v213 = CurrentStackLocation;
  v9 = *(struct _UNICODE_STRING **)(CurrentStackLocation + 16);
  v10 = *(_BYTE *)(CurrentStackLocation + 2);
  v187 = v10 & 2;
  v11 = v10 & 0x10;
  v199 = *(_DWORD *)(CurrentStackLocation + 8);
  v185 = *(_DWORD *)(CurrentStackLocation + 24);
  v12 = v9 && v9->Length;
  if ( (*(_DWORD *)(a1 + 12) & 1) == 0 )
  {
    if ( !v11 )
      goto LABEL_540;
    if ( (v10 & 2) != 0 )
      goto LABEL_4;
    if ( !v12 || FsRtlDoesNameContainWildCards(v9) )
    {
LABEL_540:
      LOBYTE(CurrentStackLocation) = 1;
      v154 = NtfsPostRequest((char *)a1, a2, CurrentStackLocation, 0);
      v155 = v154;
      if ( NtfsStatusDebugFlags
        && v154
        && v154 != 294
        && v154 - 298 > 1
        && v154 < 0xFFFFFFED
        && v154 != -1073741608
        && v154 != -1073741802
        && v154 != -1073741807
        && v154 + 2147483643 > 1
        && v154 != 259 )
      {
        NtfsStatusTraceAndDebugInternal(0, v154, 0xD027Eu);
      }
      return v155;
    }
    LocalIndexCcb = (unsigned int *)v171;
  }
LABEL_4:
  v218 = LocalIndexCcb;
  if ( !v11 )
    goto LABEL_5;
  if ( *((_QWORD *)LocalIndexCcb + 10) )
  {
    v155 = -1072103334;
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(0, 0xC019005A, 0xD0293u);
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(a1, 0xC019005A, 0xD0294u);
    NtfsExtendedCompleteRequestInternal(a1, a2, -1072103334, a2 != 0, 0);
    return v155;
  }
  LocalIndexCcb = AllocateLocalIndexCcb((__int64)LocalIndexCcb);
  v171 = LocalIndexCcb;
  v216 = LocalIndexCcb;
LABEL_5:
  v13 = v10 & 1;
  v14 = v10 & 4;
  P = 0;
  v191 = 0;
  v192 = 0;
  PoolWithTag = 0;
  v175 = 0;
  v166 = 0;
  v177 = 0;
  v176 = 0;
  Size_6 = 0;
  if ( v199 >= 0x10000 )
    *(_DWORD *)(a1 + 4) |= 0x2000000u;
  if ( (*(_DWORD *)(*(_QWORD *)(v213 + 48) + 80LL) & 2) == 0 && !v11 )
  {
    memset(v219, 0, sizeof(v219));
    v220 = 0;
    NtfsAcquireIndexCcb(v182, LocalIndexCcb, v219);
    v177 = 1;
  }
  if ( v185 > 50 )
  {
    if ( v185 == 60 )
    {
      v172 = 88;
      goto LABEL_15;
    }
    v16 = 3;
    switch ( v185 )
    {
      case '?':
        v172 = 114;
        break;
      case 'N':
        v172 = 80;
        break;
      case 'O':
        v172 = 106;
        break;
      case 'P':
        v172 = 96;
        break;
      case 'Q':
        v172 = 122;
        break;
      default:
        goto LABEL_460;
    }
    v15 = 68;
    goto LABEL_17;
  }
  switch ( v185 )
  {
    case 50:
      v172 = 92;
      PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)(PoolType | 0x10), 0x60u, 0x6446744Eu);
      goto LABEL_15;
    case 1:
      v172 = 64;
      goto LABEL_15;
    case 2:
      v15 = 68;
      v172 = 68;
      goto LABEL_16;
    case 3:
      v172 = 94;
      goto LABEL_15;
  }
  if ( v185 != 12 )
  {
    if ( v185 == 37 )
    {
      v172 = 104;
      goto LABEL_15;
    }
    if ( v185 == 38 )
    {
      v172 = 80;
      goto LABEL_15;
    }
LABEL_460:
    v19 = -1073741821;
    if ( !NtfsStatusDebugFlags )
      goto LABEL_445;
    v20 = 852764;
    goto LABEL_444;
  }
  v172 = 12;
LABEL_15:
  v15 = 68;
LABEL_16:
  v16 = 3;
LABEL_17:
  if ( !v11 && *((_QWORD *)v171 + 19) )
  {
    v17 = 0;
    v168 = 0;
    if ( !v12 || !v13 && !v14 )
    {
      v23 = (unsigned int *)v171;
      QueryFileName = NtfsGetQueryFileName((__int64)v171);
      v198 = QueryFileName;
      goto LABEL_41;
    }
  }
  else
  {
    v17 = 1;
    v168 = 1;
  }
  if ( v12 )
  {
    Length = v9->Length;
    if ( (unsigned __int16)Length <= 0x1FEu && NtfsIsFileNameValid(&v9->Length, 1)
      || !v17
      && (unsigned __int16)(Length - 1) <= v16
      && (Buffer = v9->Buffer, *Buffer == 46)
      && ((_WORD)Length != 4 || Buffer[1] == 46) )
    {
      v15 = Length + 66;
      v146 = (char *)ExAllocatePoolWithTag((POOL_TYPE)(PoolType | 0x10), (unsigned int)(Length + 66), 0x6446744Eu);
      v198 = (__int64)v146;
      memmove(v146 + 66, v9->Buffer, Length);
      *(_QWORD *)v146 = *(_QWORD *)(*(_QWORD *)(v182 + 184) + 8LL);
      v146[64] = Length >> 1;
      QueryFileName = (__int64)v146;
      v146[65] = 0;
      goto LABEL_32;
    }
    v19 = -1073741773;
    if ( !NtfsStatusDebugFlags )
    {
LABEL_445:
      v173 = v19;
      v30 = 0;
      v67 = v183;
      v23 = (unsigned int *)v171;
      goto LABEL_446;
    }
    v20 = 852833;
LABEL_444:
    NtfsStatusTraceAndDebugInternal(0, v19, v20);
    goto LABEL_445;
  }
  QueryFileName = (__int64)ExAllocatePoolWithTag((POOL_TYPE)(PoolType | 0x10), 0x44u, 0x6446744Eu);
  v198 = QueryFileName;
  *(_QWORD *)QueryFileName = *(_QWORD *)(*(_QWORD *)(v182 + 184) + 8LL);
  *(_DWORD *)(QueryFileName + 64) = 2752513;
LABEL_32:
  if ( !v168 && v14 )
  {
    P = (PVOID)QueryFileName;
    v13 = 0;
    v23 = (unsigned int *)v171;
    goto LABEL_41;
  }
  Name = 0;
  v23 = (unsigned int *)v171;
  if ( !v168 )
  {
    v149 = (_QWORD *)*((_QWORD *)v171 + 19);
    if ( (*((_DWORD *)v171 + 1) & 0x1000000) != 0 )
      NtOfsFreeReadContext(v149);
    else
      ExFreePoolWithTag(v149, 0);
    *((_QWORD *)v171 + 19) = 0;
    ClearFlagInterlocked(v23 + 1, 0x1000000);
  }
  if ( (v23[1] & 0x1000000) != 0 )
    _InterlockedAnd((volatile signed __int32 *)v23 + 1, 0xFEFFFFFF);
  QueryFileName = v198;
  *((_QWORD *)v23 + 19) = v198;
  v23[36] = v15;
  Name.Length = 2 * *(unsigned __int8 *)(QueryFileName + 64);
  Name.MaximumLength = Name.Length;
  Name.Buffer = (PWSTR)(QueryFileName + 66);
  if ( (v23[1] & 0x300) != 0 )
    _InterlockedAnd((volatile signed __int32 *)v23 + 1, 0xFFFFFCFF);
  v24 = v186;
  if ( v182 != *(_QWORD *)(v186 + 32) )
  {
    if ( FsRtlDoesNameContainWildCards(&Name) )
    {
      if ( (unsigned __int8)FsRtlIsNameInUnUpcasedExpression(&Name, &word_140092198, 0, 0) )
        SetFlagInterlocked(v23 + 1, 0x300u);
      goto LABEL_41;
    }
    if ( Name.Length == word_140092198 && !memcmp(Name.Buffer, Buf2, Name.Length) )
    {
      v24 = v186;
      if ( (v23[1] & 0x300) != 0x300 )
        _InterlockedOr((volatile signed __int32 *)v23 + 1, 0x300u);
      goto LABEL_42;
    }
LABEL_41:
    v24 = v186;
  }
LABEL_42:
  v183->IoStatus.Information = 0;
  Size_4 = 0;
  if ( (*(_DWORD *)(a1 + 12) & 0x200) != 0 || *((_QWORD *)v23 + 22) )
  {
    v25 = 3932169;
  }
  else
  {
    v25 = 3932169;
    if ( (unsigned int)(v185 - 60) > 0x15 || !_bittest(&v25, v185 - 60) )
      goto LABEL_46;
  }
  LOBYTE(v22) = 1;
  NtfsAcquireSharedVcb(a1, v24, v22);
  v166 = 1;
LABEL_46:
  if ( !*((_QWORD *)v23 + 22) )
    goto LABEL_47;
  ExAcquirePushLockSharedEx(v186 + 656, 0);
  v115 = *(_QWORD **)(v186 + 1344);
  v214 = v115;
  v116 = 0;
  Size_4 = 0;
  if ( !v115 )
    goto LABEL_305;
  while ( 1 )
  {
    v117 = *(v115 - 2) & 0xFFFFFFFFFFFFLL;
    v118 = *((_QWORD *)v23 + 22) & 0xFFFFFFFFFFFFLL;
    if ( v118 >= v117 )
    {
      if ( v118 > v117 )
        goto LABEL_296;
      v119 = HIWORD(*((_QWORD *)v23 + 22));
      v120 = HIWORD(*(v115 - 2));
      if ( (unsigned __int16)v119 >= (unsigned __int16)v120 )
        break;
    }
    v114 = (_QWORD *)*v115;
LABEL_297:
    if ( !v114 )
      goto LABEL_305;
    v115 = v114;
    v214 = v114;
  }
  if ( (unsigned __int16)v119 > (unsigned __int16)v120 )
  {
LABEL_296:
    v114 = (_QWORD *)v115[1];
    goto LABEL_297;
  }
  v116 = 1;
  Size_4 = 1;
LABEL_305:
  if ( v116 )
  {
    v191 = *(v115 - 1);
    _InterlockedAdd((volatile signed __int32 *)(v191 + 28), 1u);
  }
  ExReleasePushLockEx(v186 + 656, 0);
  if ( v191 )
    NtfsAcquireSharedFcb(a1, v191, 0, 1);
  *((_QWORD *)v23 + 22) = 0;
  QueryFileName = v198;
LABEL_47:
  NtfsAcquireSharedFcb(a1, *(_QWORD *)(v182 + 184), v182, 0);
  v167 = 1;
  if ( v166 && (*(_DWORD *)(a1 + 12) & 0x200) == 0 && ((unsigned int)(v185 - 60) > 0x15 || !_bittest(&v25, v185 - 60)) )
  {
    NtfsReleaseVcb(a1, v186);
    v166 = 0;
  }
  v211 = v23 + 1;
  v26 = v23[1];
  v169 = (v26 & 1) != 0 && ((v26 & 0x4000000) != 0 || (*(_DWORD *)(*(_QWORD *)(v182 + 184) + 16LL) & 0x400) == 0);
  v27 = TxfSetupTransactionContextFromCcb(a1, *(_QWORD *)(v213 + 48), 0, 0, 0);
  v19 = v27;
  v173 = v27;
  if ( v27 )
  {
    if ( NtfsStatusDebugFlags
      && (((v27 - 294) & 0xFFFFFFFA) != 0 || v27 == 295)
      && v27 < 0xFFFFFFED
      && v27 != -1073741608
      && v27 != -1073741802
      && v27 != -1073741807
      && v27 + 2147483643 > 1
      && v27 != 259 )
    {
      NtfsStatusTraceAndDebugInternal(a1, v27, 0xD0457u);
    }
    ExRaiseStatus(v19);
  }
  v28 = *((_QWORD *)v23 + 10);
  v29 = v28 && (*(_DWORD *)(v28 + 4) & 2) != 0 && *(_DWORD *)(v28 + 36);
  v176 = v29;
  Size_6 = v29;
  if ( (*(_DWORD *)(v182 + 512) & 0x10000) != 0 )
  {
    v19 = -1073741202;
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(0, 0xC000026E, 0xD0468u);
    v173 = -1073741202;
    v67 = v183;
    v30 = 0;
    goto LABEL_446;
  }
  v206 = (char *)NtfsMapUserBuffer((__int64)v183, 16);
  v30 = 0;
  if ( v183->MdlAddress )
    RequestorMode = 0;
  else
    RequestorMode = v183->RequestorMode;
  if ( v168 || v13 )
  {
    v163 = 1;
    v165 = 0;
    if ( (v23[1] & 0xC00) != 0 )
      _InterlockedAnd((volatile signed __int32 *)v23 + 1, 0xFFFFF3FF);
  }
  else
  {
    if ( !P )
    {
      v163 = 0;
      goto LABEL_200;
    }
    v163 = 1;
    v165 = 1;
    v134 = *(_BYTE *)(QueryFileName + 64);
    if ( v134 <= 2u && *(_WORD *)(QueryFileName + 66) == 46 )
    {
      if ( v134 == 1 )
      {
        ClearFlagInterlocked(v23 + 1, 2048);
        SetFlagInterlocked(v135, 0x400u);
        *(_WORD *)(QueryFileName + 66) = 42;
        goto LABEL_200;
      }
      if ( *(_WORD *)(QueryFileName + 68) == 46 )
      {
        SetFlagInterlocked(v23 + 1, 0xC00u);
        *(_DWORD *)(QueryFileName + 66) = 2752554;
LABEL_200:
        v165 = (char)v30;
      }
    }
    else
    {
      SetFlagInterlocked(v23 + 1, 0xC00u);
    }
  }
  v204 = (int)v30;
  v189 = (unsigned int)v30;
  if ( *(_WORD *)(QueryFileName + 66) == 42
    && ((v91 = *(_BYTE *)(QueryFileName + 64), v91 == 1)
     || v91 == 3 && *(_WORD *)(QueryFileName + 68) == 46 && *(_WORD *)(QueryFileName + 70) == 42) )
  {
    Size_5 = 1;
  }
  else
  {
    Size_5 = (char)v30;
  }
  while ( 2 )
  {
    while ( 2 )
    {
      while ( 2 )
      {
        v31 = v163;
LABEL_62:
        v194 = (__int64)v30;
        v212 = v30;
        v184 = (__int64)v30;
        v196 = v30;
        Size = (unsigned int)v30;
        v164 = (char)v30;
        if ( v192 )
        {
          if ( *(_WORD *)v192 == 1794 )
            v99 = (struct _ERESOURCE *)(*(_QWORD *)(v192 + 104) + 64LL);
          else
            v99 = *(struct _ERESOURCE **)(v192 + 8);
          ExReleaseResourceLite(v99);
          v30 = 0;
          v192 = 0;
        }
        v32 = PoolWithTag;
        if ( PoolWithTag )
        {
          *(_OWORD *)PoolWithTag = 0;
          v32[4] = 0;
        }
        v33 = Entry;
        if ( Entry )
        {
          if ( (*((_BYTE *)Entry + 330) & 1) != 0 )
          {
            ExReleasePushLockEx(*(_QWORD *)(a1 + 104) + 656LL, 0);
            v33[165] &= ~1u;
            v30 = 0;
          }
          v32 = PoolWithTag;
        }
        v34 = (__int64)v30;
        if ( v31 )
        {
          if ( v175 == (_BYTE)v30 )
            v74 = v198;
          else
            v74 = *((_QWORD *)v23 + 21) + 16LL;
          restarted = NtfsRestartIndexEnumeration(a1, (__int64)v23, v182, v74, v169, v165, &v194, v191, (__int64)v32);
          v36 = restarted >= 0;
          v174 = restarted >= 0;
          v30 = 0;
          v76 = 0;
          if ( restarted != -1073741275 )
            v76 = restarted;
          v163 = 0;
          v175 = 0;
          v188 = 0;
          if ( v76 < 0 )
          {
            if ( NtfsStatusDebugFlags
              && (unsigned int)v76 < 0xFFFFFFED
              && v76 != -1073741802
              && v76 != -1073741807
              && (unsigned int)(v76 + 2147483643) > 1
              && v76 != -1073741608 )
            {
              NtfsStatusTraceAndDebugInternal(0, v76, 0xD0532u);
              v30 = 0;
            }
            v19 = v76;
            v173 = v76;
            v23 = (unsigned int *)v171;
            v67 = v183;
            goto LABEL_446;
          }
        }
        else
        {
          v35 = NtfsContinueIndexEnumeration(a1, (__int64)v23, v182, v165, &v194, (__int64)v32);
          v36 = v35 >= 0;
          v174 = v35 >= 0;
          v30 = 0;
          v37 = 0;
          if ( v35 != -1073741275 )
            v37 = v35;
          if ( v37 < 0 )
          {
            if ( NtfsStatusDebugFlags
              && (unsigned int)v37 < 0xFFFFFFED
              && v37 != -1073741802
              && v37 != -1073741807
              && (unsigned int)(v37 + 2147483643) > 1
              && v37 != -1073741608 )
            {
              NtfsStatusTraceAndDebugInternal(0, v37, 0xD0545u);
              v30 = 0;
            }
            v19 = v37;
            v173 = v37;
            v23 = (unsigned int *)v171;
            v67 = v183;
            goto LABEL_446;
          }
        }
        if ( v187 && v189 )
          goto LABEL_166;
        v38 = 0;
        v196 = 0;
        v39 = (char *)NtfsDotDotName;
        v212 = NtfsDotDotName;
        v40 = *(_QWORD *)(v182 + 184);
        v184 = v40 + 128;
        v165 = 0;
        v170 = 0;
        if ( (*v211 & 0x500) == 0x100 )
        {
          Size = 2;
          v36 = 1;
          v174 = 1;
          v38 = *(_QWORD *)(v40 + 8);
          v196 = (__int64 *)v38;
          v170 = 1;
          if ( v185 == 50 )
            memset(PoolWithTag, 0, 0x60u);
          SetFlagInterlocked(v211, 0x400u);
          goto LABEL_74;
        }
        v41 = *v211 & 0xA00;
        if ( (_DWORD)v41 == 512 )
        {
          Size = 4;
          v36 = 1;
          v174 = 1;
          if ( v185 != 12 )
          {
            NextParentLcb = (_QWORD *)*((_QWORD *)v171 + 9);
            if ( NextParentLcb || (NextParentLcb = NtfsGetNextParentLcb(v41, v40, 0)) != 0 )
            {
              v78 = *(_QWORD *)(NextParentLcb[3] + 184LL);
              v79 = v166;
              if ( !NtfsAcquireResourceShared(v41, v78, v166) )
              {
                *(_DWORD *)(a1 + 12) |= 0x200u;
                NtfsRaiseStatusInternal(a1, -1073741608, 0, 0, 853407);
              }
              v192 = v78;
              if ( (*(_DWORD *)(v78 + 4) & 8) == 0 )
              {
                if ( *(_WORD *)v78 == 1794 )
                  v136 = (struct _ERESOURCE *)(*(_QWORD *)(v78 + 104) + 64LL);
                else
                  v136 = *(struct _ERESOURCE **)(v78 + 8);
                ExReleaseResourceLite(v136);
                v192 = 0;
                if ( !NtfsAcquireResourceExclusive(v137, v78, v79) )
                {
                  *(_DWORD *)(a1 + 12) |= 0x200u;
                  NtfsRaiseStatusInternal(a1, -1073741608, 0, 0, 853420);
                }
                v192 = v78;
                if ( (*(_DWORD *)(v78 + 4) & 8) == 0 )
                  NtfsUpdateFcbInfoFromDisk(a1, 1, 0, v78, 0, 0);
                ExConvertExclusiveToSharedLite((PERESOURCE)(*(_QWORD *)(v78 + 104) + 64LL));
              }
              if ( v79 )
              {
                if ( (unsigned int)(v185 - 60) > 0x15 || (v100 = 3932169, !_bittest(&v100, v185 - 60)) )
                {
                  NtfsReleaseVcb(a1, v186);
                  v166 = 0;
                  *(_DWORD *)(a1 + 12) &= ~0x200u;
                }
              }
              v38 = *(_QWORD *)(v78 + 8);
              v196 = (__int64 *)v38;
              v80 = (PVOID)(v78 + 128);
              v170 = 1;
            }
            else
            {
              v80 = VirtualAddress;
            }
            v184 = (__int64)v80;
          }
          if ( v185 == 50 )
            memset(PoolWithTag, 0, 0x60u);
          SetFlagInterlocked(v211, 0x800u);
          v30 = 0;
LABEL_74:
          LODWORD(v40) = Size;
          break;
        }
        if ( !v36 )
          goto LABEL_74;
        v38 = *(_QWORD *)v194;
        v196 = *(__int64 **)v194;
        v39 = (char *)(v194 + 16);
        v212 = (__int64 *)(v194 + 16);
        v69 = *(unsigned __int16 *)(v194 + 10);
        if ( (unsigned __int16)v69 < 0x42u
          || (v40 = 2 * (unsigned int)*(unsigned __int8 *)(v194 + 80), Size = v40, (_DWORD)v40 != v69 - 66) )
        {
          v138 = Entry;
          if ( Entry && (*((_BYTE *)Entry + 330) & 1) != 0 )
          {
            ExReleasePushLockEx(*(_QWORD *)(a1 + 104) + 656LL, 0);
            v138[165] &= ~1u;
          }
          v121 = v182;
          NtfsAttachRepairInfo_IndexOffset(
            a1,
            v40,
            (struct _LIST_ENTRY *)0x78000D061ELL,
            0,
            v158,
            v182,
            *((_QWORD *)v171 + 17),
            0,
            0,
            0);
          if ( NtfsStatusDebugFlags )
            NtfsStatusTraceAndDebugInternal(a1, 0xC0000102, 0xD061Eu);
          NtfsRaiseStatusInternal(a1, -1073741566, *(_QWORD *)(v121 + 184) + 8, *(_QWORD *)(v121 + 184), 853534);
        }
        v184 = v194 + 24;
        v165 = 1;
        if ( (unsigned int)v38 < 0x10 )
        {
LABEL_129:
          v23 = (unsigned int *)v171;
          continue;
        }
        break;
      }
      if ( !v36 )
      {
        if ( v189 == (_DWORD)v30 )
        {
          if ( v168 == (_BYTE)v30 )
          {
            v19 = -2147483642;
            v173 = -2147483642;
            v23 = (unsigned int *)v171;
            v67 = v183;
          }
          else
          {
            if ( NtfsStatusDebugFlags )
            {
              NtfsStatusTraceAndDebugInternal(0, 0xC000000F, 0xD0655u);
              v30 = 0;
            }
            v19 = -1073741809;
            v173 = -1073741809;
            v23 = (unsigned int *)v171;
            v67 = v183;
          }
        }
        else
        {
LABEL_166:
          v19 = (int)v30;
          v173 = (int)v30;
          v23 = (unsigned int *)v171;
          v67 = v183;
        }
        goto LABEL_446;
      }
      if ( (v39[65] & 3) != 2 )
      {
        v23 = (unsigned int *)v171;
        goto LABEL_78;
      }
      if ( Entry == v30 )
      {
        v103 = (char *)ExAllocateFromLookasideListEx(&NtfsIndexContextLookasideList);
        Entry = v103;
        memset(v103 + 88, 0, 0x118u);
        memset(v103, 0, 0x58u);
        *((_QWORD *)v103 + 12) = v103 + 112;
        *((_WORD *)v103 + 164) = 3;
      }
      else
      {
        NtfsReinitializeIndexContext(a1, (__int64)Entry);
      }
      v30 = 0;
      if ( Size_5 )
        goto LABEL_129;
      v34 = (__int64)v39;
      v23 = (unsigned int *)v171;
      v39 = NtfsRetrieveOtherFileName(
              a1,
              v171,
              (__int64 *)v182,
              (__int64 *)v194,
              (unsigned __int16 *)Entry,
              v191,
              &v164,
              0);
      v212 = (__int64 *)v39;
      v30 = 0;
      if ( v39 )
      {
        if ( (v23[1] & 4) != 0 )
        {
          v111 = NtfsGetQueryFileName((__int64)v23);
          LOBYTE(v112) = v169;
          IsEqual = NtfsFileNameIsInExpression(*(_QWORD *)(v186 + 784), v111, v39, v112);
        }
        else
        {
          NtfsGetQueryFileName((__int64)v23);
          IsEqual = NtfsFileNameIsEqual(*(PCWCH *)(v186 + 784));
        }
        v30 = 0;
        if ( IsEqual )
          continue;
        LODWORD(v40) = 2 * (unsigned __int8)v39[64];
        Size = v40;
LABEL_78:
        v200 = v199 - v189;
        if ( v189 && (v199 < v189 || (unsigned int)v40 + v172 > v199 - v189) )
        {
          v30 = 0;
          v19 = 0;
          v173 = 0;
          v67 = v183;
          goto LABEL_446;
        }
        Information = v183->IoStatus.Information;
        v43 = v189 + v172;
        v44 = v43 - Information;
        v45 = &v206[Information];
        if ( RequestorMode )
          RtlSetUserMemory(v45, 0, v44);
        else
          RtlSetVolatileMemory(v45, 0, v44);
        if ( v200 < Size + v172 )
          v46 = v200 - v172;
        else
          v46 = Size;
        v205 = v46;
        *(_QWORD *)&Name.Length = v46;
        v47 = v39 + 66;
        v48 = &v206[v43];
        if ( RequestorMode )
          RtlCopyToUser(v48, v47, v46);
        else
          RtlCopyVolatileMemory(v48, v47, v46);
        v49 = &v206[v189];
        v193 = v49;
        v30 = 0;
        if ( v185 <= 50 )
        {
          switch ( v185 )
          {
            case 50:
              memset(Src, 0, sizeof(Src));
              v51 = v184;
              Src[1] = *(_QWORD *)v184;
              Src[2] = *(_QWORD *)(v184 + 24);
              v122 = *(_DWORD *)(v184 + 48) & 0xDAFFB7;
              LODWORD(Src[7]) = v122;
              Src[3] = *(_QWORD *)(v184 + 8);
              Src[4] = *(_QWORD *)(v184 + 16);
              if ( v170 )
                v122 = Src[7];
              if ( (*(_DWORD *)(v184 + 48) & 0x30000000) != 0 )
              {
                v122 |= 0x10u;
                LODWORD(Src[7]) = v122;
              }
              if ( !v122 )
                v122 = 128;
              Src[7] = __PAIR64__(Size, v122);
              v60 = Size;
              Src[5] = *(_QWORD *)(v184 + 40);
              Src[6] = *(_QWORD *)(v184 + 32);
              Src[8] = __PAIR64__(HIDWORD(v196), v38);
              LODWORD(Src[11]) = *(_DWORD *)PoolWithTag;
              *(_OWORD *)&Src[9] = *(_OWORD *)((char *)PoolWithTag + 4);
              if ( RequestorMode )
                RtlCopyToUser(v49, Src, v172);
              else
                RtlCopyVolatileMemory(v49, Src, v172);
              goto LABEL_143;
            case 1:
              v51 = v184;
              goto LABEL_94;
            case 2:
              goto LABEL_89;
            case 3:
LABEL_189:
              if ( (v39[65] & 3) == 1 )
              {
                ShortName = NtfsQueryDirectoryGetShortName(
                              a1,
                              v182,
                              (__int64)v171,
                              v191,
                              v194,
                              v34,
                              &Entry,
                              (__int64)&v164);
                v82 = ShortName;
                v30 = 0;
                if ( ShortName )
                {
                  v83 = 2 * *(_BYTE *)(ShortName + 64);
                  v84 = v49 + 68;
                  v50 = RequestorMode;
                  if ( RequestorMode )
                    RtlWriteUCharToUser(v84, 2 * *(_BYTE *)(ShortName + 64));
                  else
                    *v84 = v83;
                  v85 = (void *)(v82 + 66);
                  v86 = v49 + 70;
                  if ( RequestorMode )
                    RtlCopyToUser(v86, v85, v83);
                  else
                    RtlCopyVolatileMemory(v86, v85, v83);
                  v30 = 0;
                  goto LABEL_90;
                }
                if ( v164 )
                {
                  v67 = v183;
                  if ( !v183->IoStatus.Information )
                    NtfsRaiseStatusInternal(a1, -1073741608, 0, 0, 854069);
                  v19 = 0;
                  v173 = 0;
                  v23 = (unsigned int *)v171;
                  goto LABEL_446;
                }
              }
LABEL_89:
              v50 = RequestorMode;
              goto LABEL_90;
            case 12:
              v60 = Size;
              if ( !RequestorMode )
              {
                *((_DWORD *)v49 + 2) = Size;
                v51 = v184;
LABEL_114:
                if ( v200 < v60 + v172 )
                {
                  v19 = -2147483643;
                  v173 = -2147483643;
                }
                v63 = v191;
                v23 = (unsigned int *)v171;
                if ( v191 && v51 != *(_QWORD *)(v182 + 184) + 128LL && *(_DWORD *)v194 == *((_DWORD *)v171 + 44) )
                {
                  v143 = v186;
                  ExAcquirePushLockSharedEx(v186 + 656, 0);
                  _InterlockedDecrement((volatile signed __int32 *)(v63 + 28));
                  ExReleasePushLockEx(v143 + 656, 0);
                  NtfsReleaseFcbEx(a1, v63, 0);
                  v30 = 0;
                  v191 = 0;
                }
                v64 = v189;
                v65 = v189 - v204;
                v66 = (int *)&v206[v204];
                if ( RequestorMode )
                {
                  RtlWriteULongToUser(v66, v65);
                  v64 = v189;
                  v30 = 0;
                }
                else
                {
                  *v66 = v65;
                }
                v67 = v183;
                v68 = v172;
                v183->IoStatus.Information = v172
                                           + *(_QWORD *)&Name.Length
                                           + ((v183->IoStatus.Information + 7) & 0xFFFFFFFFFFFFFFF8uLL);
                if ( v19 >= 0 )
                {
                  v204 = v64;
                  v189 = ((v68 + v205 + 7) & 0xFFFFFFF8) + v64;
                  continue;
                }
                goto LABEL_446;
              }
              RtlWriteULongToUser((_DWORD *)v49 + 2, Size);
              v51 = v184;
LABEL_143:
              v30 = 0;
              goto LABEL_114;
            case 37:
              if ( RequestorMode )
              {
                RtlWriteULong64ToUser((_QWORD *)v49 + 12, v38);
                v30 = 0;
              }
              else
              {
                *((_QWORD *)v49 + 12) = v38;
              }
              goto LABEL_189;
          }
          if ( v185 != 38 )
          {
LABEL_352:
            v19 = -1073741821;
            if ( NtfsStatusDebugFlags )
            {
              NtfsStatusTraceAndDebugInternal(0, 0xC0000003, 0xD08F2u);
              v30 = 0;
            }
            v173 = -1073741821;
            v23 = (unsigned int *)v171;
            v67 = v183;
            goto LABEL_446;
          }
          v50 = RequestorMode;
          if ( RequestorMode )
          {
            RtlWriteULong64ToUser((_QWORD *)v49 + 9, v38);
            v30 = 0;
          }
          else
          {
            *((_QWORD *)v49 + 9) = v38;
          }
LABEL_90:
          v51 = v184;
LABEL_91:
          if ( (*(_DWORD *)(v51 + 48) & 0x400) != 0 )
          {
            if ( (unsigned int)(v185 - 60) <= 0x15 )
            {
              v52 = 3932169;
              if ( _bittest(&v52, v185 - 60) )
              {
LABEL_94:
                v53 = v49 + 8;
                if ( RequestorMode )
                {
                  RtlWriteULong64ToUser(v53, *(_QWORD *)v51);
                  v30 = 0;
                }
                else
                {
                  *v53 = *(_QWORD *)v51;
                }
                v54 = v49 + 16;
                if ( RequestorMode )
                {
                  RtlWriteULong64ToUser(v54, *(_QWORD *)(v51 + 24));
                  v30 = 0;
                }
                else
                {
                  *v54 = *(_QWORD *)(v51 + 24);
                }
                v197 = 0;
                v55 = *(_DWORD *)(v51 + 48);
                v56 = v55 & 0xDAFFB7;
                v197 = v55 & 0xDAFFB7;
                if ( (v55 & 0x30000000) != 0 )
                {
                  v56 = v55 & 0xDAFFA7 | 0x10;
                  v197 = v56;
                }
                if ( !v56 )
                  v56 = 128;
                v197 = v56;
                if ( RequestorMode )
                {
                  RtlWriteULongToUser((_DWORD *)v49 + 14, v56);
                  v30 = 0;
                }
                else
                {
                  *((_DWORD *)v49 + 14) = v56;
                }
                v57 = (__int64 *)(v49 + 24);
                v58 = *(_QWORD *)(v51 + 8);
                if ( RequestorMode )
                {
                  RtlWriteULong64ToUser(v57, v58);
                  v30 = 0;
                }
                else
                {
                  *v57 = v58;
                }
                v59 = v49 + 32;
                if ( RequestorMode )
                {
                  RtlWriteULong64ToUser(v59, *(_QWORD *)(v51 + 16));
                  v30 = 0;
                }
                else
                {
                  *v59 = *(_QWORD *)(v51 + 16);
                }
                v60 = Size;
                if ( RequestorMode )
                {
                  RtlWriteULongToUser((_DWORD *)v49 + 15, Size);
                  v30 = 0;
                }
                else
                {
                  *((_DWORD *)v49 + 15) = Size;
                }
                v61 = v49 + 40;
                if ( RequestorMode )
                {
                  RtlWriteULong64ToUser(v61, *(_QWORD *)(v51 + 40));
                  v30 = 0;
                }
                else
                {
                  *v61 = *(_QWORD *)(v51 + 40);
                }
                v62 = v49 + 48;
                if ( !RequestorMode )
                {
                  *v62 = *(_QWORD *)(v51 + 32);
                  goto LABEL_114;
                }
                RtlWriteULong64ToUser(v62, *(_QWORD *)(v51 + 32));
                goto LABEL_143;
              }
            }
            v72 = *(_DWORD *)(v51 + 52);
          }
          else
          {
            v72 = *(unsigned __int16 *)(v51 + 52);
            v210 = v72;
            if ( v72 )
            {
              v92 = 4;
              if ( *(_WORD *)(v51 + 54) > 4u )
                v92 = *(unsigned __int16 *)(v51 + 54);
              v72 += v92;
              v210 = v72;
            }
          }
          v73 = (int *)(v49 + 64);
          if ( v50 )
          {
            RtlWriteULongToUser(v73, v72);
            v30 = 0;
          }
          else
          {
            *v73 = v72;
          }
          goto LABEL_94;
        }
        if ( v185 == 60 )
          goto LABEL_264;
        if ( v185 != 63 )
        {
          switch ( v185 )
          {
            case 'N':
LABEL_135:
              v70 = v171;
              goto LABEL_136;
            case 'O':
              if ( (v39[65] & 3) != 1 )
                goto LABEL_135;
              v159 = v34;
              v70 = v171;
              v93 = NtfsQueryDirectoryGetShortName(a1, v182, (__int64)v171, v191, v194, v159, &Entry, (__int64)&v164);
              v94 = v93;
              v30 = 0;
              if ( v93 )
              {
                v95 = 2 * *(_BYTE *)(v93 + 64);
                v96 = v193 + 80;
                if ( RequestorMode )
                  RtlWriteUCharToUser(v96, 2 * *(_BYTE *)(v93 + 64));
                else
                  *v96 = v95;
                v97 = (void *)(v94 + 66);
                v49 = v193;
                v98 = v193 + 82;
                if ( RequestorMode )
                  RtlCopyToUser(v98, v97, v95);
                else
                  RtlCopyVolatileMemory(v98, v97, v95);
                v30 = 0;
              }
              else
              {
                if ( v164 )
                {
                  v67 = v183;
                  if ( !v183->IoStatus.Information )
                    NtfsRaiseStatusInternal(a1, -1073741608, 0, 0, 853895);
                  v19 = 0;
                  v173 = 0;
                  v23 = (unsigned int *)v171;
                  goto LABEL_446;
                }
                v49 = v193;
              }
LABEL_136:
              v71 = RequestorMode;
              if ( RequestorMode )
              {
                RtlWriteULong64ToUser((_QWORD *)v49 + 9, v38);
                v71 = RequestorMode;
                v30 = 0;
              }
              else
              {
                *((_QWORD *)v49 + 9) = v38;
              }
              v51 = v184;
              if ( (*(_DWORD *)(v184 + 48) & 0x400) == 0
                || ((v87 = *(_DWORD *)(v184 + 52), v88 = (int *)(v49 + 68), v71)
                  ? (RtlWriteULongToUser(v88, v87), v30 = 0)
                  : (__int64 *)(*v88 = v87),
                    (*(_DWORD *)(v51 + 48) & 0x40000) == 0 || !(_DWORD)v38) )
              {
                v50 = RequestorMode;
                goto LABEL_91;
              }
              v202 = 0;
              EaSize = NtfsQueryDirectoryGetEaSize(
                         a1,
                         v186,
                         v182,
                         (__int64)v70,
                         v192,
                         &v196,
                         v51,
                         (__int64 *)&Entry,
                         &v167,
                         (unsigned int *)&v202);
              v30 = 0;
              if ( EaSize )
              {
                v90 = (int *)(v49 + 64);
                v50 = RequestorMode;
                if ( RequestorMode )
                {
                  RtlWriteULongToUser(v90, v202);
                  v30 = 0;
                }
                else
                {
                  *v90 = v202;
                }
                goto LABEL_91;
              }
              break;
            case 'P':
              goto LABEL_254;
            case 'Q':
              if ( (v39[65] & 3) == 1 )
              {
                v160 = v34;
                v101 = v171;
                v139 = NtfsQueryDirectoryGetShortName(a1, v182, (__int64)v171, v191, v194, v160, &Entry, (__int64)&v164);
                v140 = v139;
                v30 = 0;
                if ( v139 )
                {
                  v123 = 2 * *(_BYTE *)(v139 + 64);
                  v124 = v193 + 96;
                  if ( RequestorMode )
                    RtlWriteUCharToUser(v124, 2 * *(_BYTE *)(v139 + 64));
                  else
                    *v124 = v123;
                  v125 = (void *)(v140 + 66);
                  v49 = v193;
                  v126 = v193 + 98;
                  if ( RequestorMode )
                    RtlCopyToUser(v126, v125, v123);
                  else
                    RtlCopyVolatileMemory(v126, v125, v123);
                  v30 = 0;
                }
                else
                {
                  if ( v164 )
                  {
                    v67 = v183;
                    if ( !v183->IoStatus.Information )
                      NtfsRaiseStatusInternal(a1, -1073741608, 0, 0, 853978);
                    v19 = 0;
                    v173 = 0;
                    v23 = (unsigned int *)v171;
                    goto LABEL_446;
                  }
                  v49 = v193;
                }
              }
              else
              {
LABEL_254:
                v101 = v171;
              }
              v102 = RequestorMode;
              if ( RequestorMode )
              {
                RtlWriteULong64ToUser((_QWORD *)v49 + 9, v38);
                v102 = RequestorMode;
                v30 = 0;
              }
              else
              {
                *((_QWORD *)v49 + 9) = v38;
              }
              if ( v102 )
              {
                RtlWriteULong64ToUser((_QWORD *)v49 + 11, 0);
                v102 = RequestorMode;
                v30 = 0;
              }
              else
              {
                *((_QWORD *)v49 + 11) = 0;
              }
              if ( v102 )
              {
                RtlWriteULong64ToUser((_QWORD *)v49 + 10, v38);
                v102 = RequestorMode;
                v30 = 0;
              }
              else
              {
                *((_QWORD *)v49 + 10) = v38;
              }
              v51 = v184;
              if ( (*(_DWORD *)(v184 + 48) & 0x400) == 0 )
                goto LABEL_262;
              v127 = *(_DWORD *)(v184 + 52);
              v128 = (int *)(v49 + 68);
              if ( v102 )
              {
                RtlWriteULongToUser(v128, v127);
                v30 = 0;
              }
              else
              {
                *v128 = v127;
              }
              if ( (*(_DWORD *)(v51 + 48) & 0x40000) == 0 || !(_DWORD)v38 )
                goto LABEL_262;
              v203 = 0;
              v129 = NtfsQueryDirectoryGetEaSize(
                       a1,
                       v186,
                       v182,
                       (__int64)v101,
                       v192,
                       &v196,
                       v51,
                       (__int64 *)&Entry,
                       &v167,
                       (unsigned int *)&v203);
              v30 = 0;
              if ( v129 )
              {
                v109 = v203;
                goto LABEL_276;
              }
              break;
            default:
              goto LABEL_352;
          }
LABEL_439:
          v31 = 1;
          v163 = 1;
          v175 = 1;
          v188 = 1;
          v165 = 0;
          v23 = (unsigned int *)v171;
          goto LABEL_62;
        }
        if ( (v39[65] & 3) != 1 )
        {
LABEL_264:
          v104 = v171;
        }
        else
        {
          v161 = v34;
          v104 = v171;
          v141 = NtfsQueryDirectoryGetShortName(a1, v182, (__int64)v171, v191, v194, v161, &Entry, (__int64)&v164);
          v142 = v141;
          v30 = 0;
          if ( v141 )
          {
            v130 = 2 * *(_BYTE *)(v141 + 64);
            v131 = v193 + 88;
            if ( RequestorMode )
              RtlWriteUCharToUser(v131, 2 * *(_BYTE *)(v141 + 64));
            else
              *v131 = v130;
            v132 = (void *)(v142 + 66);
            v49 = v193;
            v133 = v193 + 90;
            if ( RequestorMode )
              RtlCopyToUser(v133, v132, v130);
            else
              RtlCopyVolatileMemory(v133, v132, v130);
            v30 = 0;
          }
          else
          {
            if ( v164 )
            {
              v67 = v183;
              if ( !v183->IoStatus.Information )
                NtfsRaiseStatusInternal(a1, -1073741608, 0, 0, 853813);
              v19 = 0;
              v173 = 0;
              v23 = (unsigned int *)v171;
              goto LABEL_446;
            }
            v49 = v193;
          }
        }
        v105 = RequestorMode;
        if ( RequestorMode )
        {
          RtlWriteULong64ToUser((_QWORD *)v49 + 10, 0);
          v105 = RequestorMode;
          v30 = 0;
        }
        else
        {
          *((_QWORD *)v49 + 10) = 0;
        }
        if ( v105 )
        {
          RtlWriteULong64ToUser((_QWORD *)v49 + 9, v38);
          v105 = RequestorMode;
          v30 = 0;
        }
        else
        {
          *((_QWORD *)v49 + 9) = v38;
        }
        v51 = v184;
        if ( (*(_DWORD *)(v184 + 48) & 0x400) == 0
          || ((v106 = *(_DWORD *)(v184 + 52), v107 = (int *)(v49 + 68), !v105)
            ? (__int64 *)(*v107 = v106)
            : (RtlWriteULongToUser(v107, v106), v30 = 0),
              (*(_DWORD *)(v51 + 48) & 0x40000) == 0 || !(_DWORD)v38) )
        {
LABEL_262:
          v50 = RequestorMode;
          goto LABEL_91;
        }
        v201 = 0;
        v108 = NtfsQueryDirectoryGetEaSize(
                 a1,
                 v186,
                 v182,
                 (__int64)v104,
                 v192,
                 &v196,
                 v51,
                 (__int64 *)&Entry,
                 &v167,
                 (unsigned int *)&v201);
        v30 = 0;
        if ( v108 )
        {
          v109 = v201;
LABEL_276:
          v50 = RequestorMode;
          v110 = (int *)(v49 + 64);
          if ( RequestorMode )
          {
            RtlWriteULongToUser(v110, v109);
            v30 = 0;
          }
          else
          {
            *v110 = v109;
          }
          goto LABEL_91;
        }
        goto LABEL_439;
      }
      break;
    }
    if ( !v164 )
      continue;
    break;
  }
  v67 = v183;
  if ( !v183->IoStatus.Information )
    NtfsRaiseStatusInternal(a1, -1073741608, 0, 0, 853678);
  v19 = 0;
  v173 = 0;
LABEL_446:
  v144 = *(_QWORD *)(a1 + 144);
  if ( a1 != v144 && *(_BYTE *)(a1 + 32) == 3 )
    v144 = a1;
  v145 = *(_DWORD *)(v144 + 24);
  if ( v145 < 0 )
    NtfsRaiseStatusInternal(a1, v145, 0, 0, (__int64)v30);
  if ( v19 < 0 && *(_DWORD *)(v144 + 28) != (_DWORD)v30 )
    NtfsRaiseStatusInternal(a1, v19, 0, 0, (__int64)v30);
  if ( *(_DWORD *)(a1 + 256) != (_DWORD)v30 || *(_DWORD *)(a1 + 260) != (_DWORD)v30 )
  {
    NtfsWriteUsnJournalChanges(a1);
    NtfsCommitCurrentTransaction(a1);
    v148 = *(_DWORD *)(v144 + 24);
    LOBYTE(v30) = 0;
    if ( v148 < 0 )
      NtfsRaiseStatusInternal(a1, v148, 0, 0, 0);
  }
  if ( v19 >= 0 || (unsigned int)(v19 + 2147483643) <= 1 || v19 == -1073741809 )
  {
    NtfsUpdateFileTimestampsForAccess(*(_QWORD *)(v213 + 48), *(_QWORD *)(v182 + 184), v23);
    LOBYTE(v30) = 0;
  }
  if ( v166 != (_BYTE)v30 )
  {
    NtfsReleaseVcb(a1, v186);
    *(_DWORD *)(a1 + 12) &= ~0x200u;
    LOBYTE(v30) = 0;
  }
  v150 = Entry;
  if ( Entry )
  {
    NtfsCleanupIndexContext(a1, (__int64)Entry);
    ExFreeToLookasideListEx(&NtfsIndexContextLookasideList, v150);
    LOBYTE(v30) = 0;
  }
  if ( v192 )
  {
    if ( *(_WORD *)v192 == 1794 )
      v156 = (struct _ERESOURCE *)(*(_QWORD *)(v192 + 104) + 64LL);
    else
      v156 = *(struct _ERESOURCE **)(v192 + 8);
    ExReleaseResourceLite(v156);
    LOBYTE(v30) = 0;
  }
  v151 = v191;
  if ( v191 )
  {
    v157 = v186;
    ExAcquirePushLockSharedEx(v186 + 656, 0);
    _InterlockedDecrement((volatile signed __int32 *)(v151 + 28));
    ExReleasePushLockEx(v157 + 656, 0);
    NtfsReleaseFcbEx(a1, v151, 0);
    LOBYTE(v30) = 0;
  }
  v152 = v182;
  if ( v167 != (_BYTE)v30 )
    NtfsReleaseFcbEx(a1, *(_QWORD *)(v182 + 184), 0);
  NtfsCleanupAfterEnumeration(a1, v23);
  if ( v176 )
    TxfDereferenceForDefaultReader((__int64)v23);
  if ( v177 )
    NtfsReleaseIndexCcb(v152, v23);
  if ( P )
    ExFreePoolWithTag(P, 0);
  if ( PoolWithTag )
    ExFreePoolWithTag(PoolWithTag, 0);
  if ( v23 != v218 )
    DeallocateLocalIndexCcb(v23);
  if ( NtfsStatusDebugFlags
    && v19
    && v19 != 294
    && (unsigned int)(v19 - 298) > 1
    && (unsigned int)v19 < 0xFFFFFFED
    && v19 != -1073741608
    && v19 != -1073741802
    && v19 != -1073741807
    && (unsigned int)(v19 + 2147483643) > 1
    && v19 != 259 )
  {
    NtfsStatusTraceAndDebugInternal(a1, v19, 0xD09BBu);
  }
  NtfsExtendedCompleteRequestInternal(a1, v67, v19, v67 != 0, v19 >= 0);
  return (unsigned int)v19;
}

```

## disassembly

```asm
0x1401a7b00  push    rbx
0x1401a7b02  push    rsi
0x1401a7b03  push    rdi
0x1401a7b04  push    r12
0x1401a7b06  push    r13
0x1401a7b08  push    r14
0x1401a7b0a  push    r15
0x1401a7b0c  sub     rsp, 220h
0x1401a7b13  mov     rax, cs:__security_cookie
0x1401a7b1a  xor     rax, rsp
0x1401a7b1d  mov     [rsp+258h+var_48], rax
0x1401a7b25  mov     rax, r9
0x1401a7b28  mov     [rsp+258h+var_1D8], rax
0x1401a7b30  mov     [rsp+258h+var_1B8], r8
0x1401a7b38  mov     r12, rdx
0x1401a7b3b  mov     [rsp+258h+var_1D0], rdx
0x1401a7b43  mov     r13, rcx
0x1401a7b46  mov     [rsp+258h+var_138], rcx
0x1401a7b4e  mov     [rsp+258h+var_F0], r8
0x1401a7b56  mov     [rsp+258h+var_E0], rax
0x1401a7b5e  mov     rdx, [rsp+258h+arg_20]
0x1401a7b66  mov     [rsp+258h+var_1F8], rdx
0x1401a7b6b  mov     [rsp+258h+var_E8], rdx
0x1401a7b73  xor     r10d, r10d
0x1401a7b76  mov     [rsp+258h+Entry], r10
0x1401a7b7e  mov     byte ptr [rsp+258h+var_205+3], r10b
0x1401a7b83  mov     r8, [r12+0B8h]
0x1401a7b8b  mov     [rsp+258h+var_100], r8
0x1401a7b93  mov     rsi, [r8+10h]
0x1401a7b97  mov     r14b, [r8+2]
0x1401a7b9b  mov     cl, r14b
0x1401a7b9e  and     cl, 2
0x1401a7ba1  mov     [rsp+258h+var_1B0], cl
0x1401a7ba8  mov     bl, r14b
0x1401a7bab  and     bl, 10h
0x1401a7bae  mov     eax, [r8+8]
0x1401a7bb2  mov     [rsp+258h+var_160], eax
0x1401a7bb9  mov     eax, [r8+18h]
0x1401a7bbd  mov     [rsp+258h+var_1C0], eax
0x1401a7bc4  test    rsi, rsi
0x1401a7bc7  jnz     loc_1401AA311
0x1401a7bcd  mov     r15b, r10b
0x1401a7bd0  mov     edi, 1
0x1401a7bd5  mov     eax, [r13+0Ch]
0x1401a7bd9  test    dil, al
0x1401a7bdc  jz      loc_1401AA415
0x1401a7be2  mov     [rsp+258h+var_D8], rdx
0x1401a7bea  test    bl, bl
0x1401a7bec  jnz     loc_1401AA452
0x1401a7bf2  mov     r12b, r14b
0x1401a7bf5  and     r12b, dil
0x1401a7bf8  and     r14b, 4
0x1401a7bfc  mov     [rsp+258h+P], r10
0x1401a7c04  mov     [rsp+258h+var_1A0], r10
0x1401a7c0c  mov     [rsp+258h+var_198], r10
0x1401a7c14  mov     [rsp+258h+var_180], r10
0x1401a7c1c  mov     [rsp+258h+var_207], r10b
0x1401a7c21  mov     [rsp+258h+var_1E7], r10b
0x1401a7c26  mov     byte ptr [rsp+258h+var_205+2], r10b
0x1401a7c2b  mov     [rsp+258h+var_1E5], r10b
0x1401a7c30  mov     al, r10b
0x1401a7c33  mov     [rsp+258h+var_1E6], al
0x1401a7c37  mov     byte ptr [rsp+258h+Size+6], al
0x1401a7c3b  cmp     [rsp+258h+var_160], 10000h
0x1401a7c46  jnb     loc_1401AA47C
0x1401a7c4c  mov     rax, [rsp+258h+var_100]
0x1401a7c54  mov     rax, [rax+30h]
0x1401a7c58  mov     ecx, [rax+50h]
0x1401a7c5b  test    cl, 2
0x1401a7c5e  jz      loc_1401AA040
0x1401a7c64  mov     ecx, [rsp+258h+var_1C0]
0x1401a7c6b  cmp     ecx, 32h ; '2'
0x1401a7c6e  jg      loc_1401A7D12
0x1401a7c74  jz      loc_1401AA084
0x1401a7c7a  sub     ecx, 1
0x1401a7c7d  jz      loc_1401A9F98
0x1401a7c83  sub     ecx, 1
0x1401a7c86  jz      loc_1401A9F8A
0x1401a7c8c  sub     ecx, 1
0x1401a7c8f  jz      loc_1401A9ECF
0x1401a7c95  sub     ecx, 9
0x1401a7c98  jnz     loc_1401A9DF3
0x1401a7c9e  mov     dword ptr [rsp+258h+var_1F0], 0Ch
0x1401a7ca6  mov     edi, 44h ; 'D'
0x1401a7cab  mov     r9d, 3
0x1401a7cb1  test    bl, bl
0x1401a7cb3  jnz     short loc_1401A7CC8
0x1401a7cb5  mov     r8, [rsp+258h+var_1F8]
0x1401a7cba  cmp     qword ptr [r8+98h], 0
0x1401a7cc2  jnz     loc_1401A9EFD
0x1401a7cc8  mov     r8b, 1
0x1401a7ccb  mov     byte ptr [rsp+258h+var_205+4], r8b
0x1401a7cd0  test    r15b, r15b
0x1401a7cd3  jz      short loc_1401A7D4E
0x1401a7cd5  movzx   ebx, word ptr [rsi]
0x1401a7cd8  mov     eax, 1FEh
0x1401a7cdd  mov     edi, 1
0x1401a7ce2  cmp     bx, ax
0x1401a7ce5  jbe     loc_1401A9E58
0x1401a7ceb  test    r8b, r8b
0x1401a7cee  jz      loc_1401A9FB2
0x1401a7cf4  mov     al, cs:NtfsStatusDebugFlags
0x1401a7cfa  mov     esi, 0C0000033h
0x1401a7cff  test    al, al
0x1401a7d01  jz      loc_1401A9D57
0x1401a7d07  mov     r8d, 0D0361h
0x1401a7d0d  jmp     loc_1401A9D4E
0x1401a7d12  sub     ecx, 3Ch ; '<'
0x1401a7d15  jz      loc_1401A9FA5
0x1401a7d1b  mov     r9d, 3
0x1401a7d21  sub     ecx, r9d
0x1401a7d24  jz      loc_1401AA0D3
0x1401a7d2a  sub     ecx, 0Fh
0x1401a7d2d  jz      loc_1401A9EDC
0x1401a7d33  sub     ecx, 1
0x1401a7d36  jnz     loc_1401A9E0E
0x1401a7d3c  mov     dword ptr [rsp+258h+var_1F0], 6Ah ; 'j'
0x1401a7d44  mov     edi, 44h ; 'D'
0x1401a7d49  jmp     loc_1401A7CB1
0x1401a7d4e  mov     ecx, cs:PoolType
0x1401a7d54  or      ecx, 10h; PoolType
0x1401a7d57  mov     r8d, 6446744Eh; Tag
0x1401a7d5d  mov     rdx, rdi; NumberOfBytes
0x1401a7d60  call    cs:__imp_ExAllocatePoolWithTag
0x1401a7d67  nop     dword ptr [rax+rax+00h]
0x1401a7d6c  mov     rbx, rax
0x1401a7d6f  mov     [rsp+258h+var_168], rax
0x1401a7d77  mov     rax, [rsp+258h+var_1D8]
0x1401a7d7f  mov     rax, [rax+0B8h]
0x1401a7d86  mov     rcx, [rax+8]
0x1401a7d8a  mov     [rbx], rcx
0x1401a7d8d  mov     dword ptr [rbx+40h], 2A0001h
0x1401a7d94  mov     r15d, 2Ah ; '*'
0x1401a7d9a  mov     r8b, byte ptr [rsp+258h+var_205+4]
0x1401a7d9f  test    r8b, r8b
0x1401a7da2  jz      loc_1401AA0F7
0x1401a7da8  xorps   xmm0, xmm0
0x1401a7dab  movups  xmmword ptr [rsp+258h+Name.Length], xmm0
0x1401a7db3  mov     r14, [rsp+258h+var_1F8]
0x1401a7db8  mov     ebx, 1000000h
0x1401a7dbd  test    r8b, r8b
0x1401a7dc0  jz      loc_1401AA115
0x1401a7dc6  lea     rsi, [r14+4]
0x1401a7dca  mov     eax, [rsi]
0x1401a7dcc  test    ebx, eax
0x1401a7dce  jz      short loc_1401A7DD7
0x1401a7dd0  lock and dword ptr [rsi], 0FEFFFFFFh
0x1401a7dd7  mov     rbx, [rsp+258h+var_168]
0x1401a7ddf  mov     [r14+98h], rbx
0x1401a7de6  mov     [r14+90h], edi
0x1401a7ded  movzx   eax, byte ptr [rbx+40h]
0x1401a7df1  add     ax, ax
0x1401a7df4  mov     [rsp+258h+Name.Length], ax
0x1401a7dfc  mov     [rsp+258h+Name.MaximumLength], ax
0x1401a7e04  lea     rax, [rbx+42h]
0x1401a7e08  mov     [rsp+258h+Name.Buffer], rax
0x1401a7e10  mov     eax, [r14+4]
0x1401a7e14  mov     edi, 300h
0x1401a7e19  test    edi, eax
0x1401a7e1b  jz      short loc_1401A7E26
0x1401a7e1d  lock and dword ptr [r14+4], 0FFFFFCFFh
0x1401a7e26  mov     rax, [rsp+258h+var_1D8]
0x1401a7e2e  mov     rcx, [rsp+258h+var_1B8]
0x1401a7e36  cmp     rax, [rcx+20h]
0x1401a7e3a  jz      short loc_1401A7E75
0x1401a7e3c  lea     rcx, [rsp+258h+Name]; Name
0x1401a7e44  call    cs:__imp_FsRtlDoesNameContainWildCards
0x1401a7e4b  nop     dword ptr [rax+rax+00h]
0x1401a7e50  test    al, al
0x1401a7e52  jnz     loc_1401A9F45
0x1401a7e58  movzx   eax, [rsp+258h+Name.Length]
0x1401a7e60  cmp     ax, cs:word_140092198
0x1401a7e67  jz      loc_1401AA152
0x1401a7e6d  mov     rcx, [rsp+258h+var_1B8]
0x1401a7e75  mov     rax, [rsp+258h+var_1D0]
0x1401a7e7d  mov     qword ptr [rax+38h], 0
0x1401a7e85  mov     byte ptr [rsp+258h+Size+4], 0
0x1401a7e8a  test    dword ptr [r13+0Ch], 200h
0x1401a7e92  jnz     short loc_1401A7EA2
0x1401a7e94  cmp     qword ptr [r14+0B0h], 0
0x1401a7e9c  jz      loc_1401A8B32
0x1401a7ea2  mov     esi, 3C0009h
0x1401a7ea7  mov     edi, 1
0x1401a7eac  mov     r8b, dil
0x1401a7eaf  mov     rdx, rcx
0x1401a7eb2  mov     rcx, r13
0x1401a7eb5  call    NtfsAcquireSharedVcb
0x1401a7eba  mov     byte ptr [rsp+258h+var_205+2], dil
0x1401a7ebf  cmp     qword ptr [r14+0B0h], 0
0x1401a7ec7  jnz     loc_1401A9095
0x1401a7ecd  xor     r9d, r9d
0x1401a7ed0  mov     rax, [rsp+258h+var_1D8]
0x1401a7ed8  mov     r8, rax
0x1401a7edb  mov     rdx, [rax+0B8h]
0x1401a7ee2  mov     rcx, r13
0x1401a7ee5  call    NtfsAcquireSharedFcb
0x1401a7eea  mov     byte ptr [rsp+258h+var_205+3], dil
0x1401a7eef  cmp     byte ptr [rsp+258h+var_205+2], 0
0x1401a7ef4  jnz     loc_1401A885F
0x1401a7efa  lea     rax, [r14+4]
0x1401a7efe  mov     [rsp+258h+var_110], rax
0x1401a7f06  mov     eax, [rax]
0x1401a7f08  test    dil, al
0x1401a7f0b  jnz     loc_1401A8719
0x1401a7f11  mov     byte ptr [rsp+258h+var_205+5], 0
0x1401a7f16  mov     [rsp+258h+var_238], 0
0x1401a7f1f  xor     r9d, r9d
0x1401a7f22  xor     r8d, r8d
0x1401a7f25  mov     rax, [rsp+258h+var_100]
0x1401a7f2d  mov     rdx, [rax+30h]
0x1401a7f31  mov     rcx, r13
0x1401a7f34  call    TxfSetupTransactionContextFromCcb
0x1401a7f39  mov     esi, eax
0x1401a7f3b  mov     dword ptr [rsp+258h+var_1F0+4], eax
0x1401a7f3f  test    eax, eax
0x1401a7f41  jnz     loc_1401A9194
0x1401a7f47  mov     rcx, [r14+50h]
0x1401a7f4b  test    rcx, rcx
0x1401a7f4e  jnz     loc_1401A9617
0x1401a7f54  xor     al, al
0x1401a7f56  mov     [rsp+258h+var_1E6], al
0x1401a7f5a  mov     byte ptr [rsp+258h+Size+6], al
0x1401a7f5e  mov     rax, [rsp+258h+var_1D8]
0x1401a7f66  test    dword ptr [rax+200h], 10000h
0x1401a7f70  jnz     loc_1401A91FC
0x1401a7f76  mov     edx, 10h
0x1401a7f7b  mov     rcx, [rsp+258h+var_1D0]
0x1401a7f83  call    NtfsMapUserBuffer
0x1401a7f88  mov     [rsp+258h+var_140], rax
0x1401a7f90  mov     rax, [rsp+258h+var_1D0]
0x1401a7f98  xor     r10d, r10d
0x1401a7f9b  cmp     [rax+8], r10
0x1401a7f9f  jnz     loc_1401A9634
0x1401a7fa5  mov     al, [rax+40h]
0x1401a7fa8  mov     [rsp+258h+var_208], al
0x1401a7fac  cmp     byte ptr [rsp+258h+var_205+4], r10b
0x1401a7fb1  jz      loc_1401A8966
0x1401a7fb7  mov     [rsp+258h+var_206], dil
0x1401a7fbc  mov     byte ptr [rsp+258h+var_205+1], r10b
0x1401a7fc1  mov     eax, [r14+4]
0x1401a7fc5  test    eax, 0C00h
0x1401a7fca  jz      short loc_1401A7FD5
0x1401a7fcc  lock and dword ptr [r14+4], 0FFFFF3FFh
0x1401a7fd5  mov     [rsp+258h+var_14C], r10d
0x1401a7fdd  mov     [rsp+258h+var_1AC], r10d
0x1401a7fe5  cmp     [rbx+42h], r15w
0x1401a7fea  jz      loc_1401A8AAD
0x1401a7ff0  mov     byte ptr [rsp+258h+Size+5], r10b
0x1401a7ff5  mov     r15b, [rsp+258h+var_206]
0x1401a7ffa  mov     r12d, 0FFFEh
0x1401a8000  mov     ecx, 702h
0x1401a8005  mov     [rsp+258h+var_188], r10
0x1401a800d  mov     [rsp+258h+var_108], r10
0x1401a8015  mov     [rsp+258h+var_1C8], r10
0x1401a801d  mov     [rsp+258h+var_178], r10
0x1401a8025  mov     dword ptr [rsp+258h+Size], r10d
0x1401a802a  mov     byte ptr [rsp+258h+var_205], r10b
0x1401a802f  mov     rax, [rsp+258h+var_198]
0x1401a8037  test    rax, rax
0x1401a803a  jnz     loc_1401A8C2F
0x1401a8040  mov     rax, [rsp+258h+var_180]
0x1401a8048  test    rax, rax
0x1401a804b  jnz     loc_1401A96BE
0x1401a8051  mov     rbx, [rsp+258h+Entry]
0x1401a8059  test    rbx, rbx
0x1401a805c  jnz     loc_1401A85D4
0x1401a8062  mov     r12, r10
0x1401a8065  test    r15b, r15b
0x1401a8068  jnz     loc_1401A8659
0x1401a806e  mov     [rsp+258h+var_230], rax
0x1401a8073  lea     rax, [rsp+258h+var_188]
0x1401a807b  mov     [rsp+258h+var_238], rax; int
0x1401a8080  mov     r9b, byte ptr [rsp+258h+var_205+1]
0x1401a8085  mov     r8, [rsp+258h+var_1D8]
0x1401a808d  mov     rdx, r14
0x1401a8090  mov     rcx, r13
0x1401a8093  call    NtfsContinueIndexEnumeration
0x1401a8098  mov     ecx, eax
0x1401a809a  shr     ecx, 1Fh
0x1401a809d  xor     cl, dil
0x1401a80a0  mov     r14b, cl
0x1401a80a3  mov     [rsp+258h+var_1E8], cl
0x1401a80a7  xor     r10d, r10d
0x1401a80aa  mov     ebx, r10d
0x1401a80ad  cmp     eax, 0C0000225h
0x1401a80b2  cmovnz  ebx, eax
0x1401a80b5  test    ebx, ebx
0x1401a80b7  js      loc_1401A9295
0x1401a80bd  cmp     [rsp+258h+var_1B0], r10b
0x1401a80c5  jnz     loc_1401A8561
0x1401a80cb  mov     rbx, r10
0x1401a80ce  mov     [rsp+258h+var_178], rbx
0x1401a80d6  lea     r15, NtfsDotDotName
0x1401a80dd  mov     [rsp+258h+var_108], r15
0x1401a80e5  mov     rax, [rsp+258h+var_1D8]
0x1401a80ed  mov     rdx, [rax+0B8h]
0x1401a80f4  lea     r8, [rdx+80h]
0x1401a80fb  mov     [rsp+258h+var_1C8], r8
0x1401a8103  mov     byte ptr [rsp+258h+var_205+1], r10b
0x1401a8108  mov     byte ptr [rsp+258h+var_205+6], r10b
  ... truncated ...
```
