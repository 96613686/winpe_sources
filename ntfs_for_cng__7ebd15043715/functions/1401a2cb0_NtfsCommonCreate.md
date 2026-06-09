# NtfsCommonCreate

- ea: `0x1401a2cb0`
- end: `0x1401a5d0d`
- name: `NtfsCommonCreate`
- size: `12381`
- prototype: `__int64 __fastcall(__int64, PIRP Irp, __int64)`
- caller_count: `4`
- callee_count: `65`
- tags: `file_ops, reparse_path, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140015d10`
- `0x1401a04b0`
- `0x1401a0cc0`
- `0x1401a1dc0`

## callees

- `0x140007ea0`
- `0x1400082b0`
- `0x140009c10`
- `0x140009c80`
- `0x14000c290`
- `0x14000eaa0`
- `0x140012e70`
- `0x14001c2e0`
- `0x14001e810`
- `0x140020de0`
- `0x140021e60`
- `0x14002b350`
- `0x14003e734`
- `0x14003ee84`
- `0x14003f220`
- `0x1400444f8`
- `0x140059250`
- `0x1400593c0`
- `0x1400596c0`
- `0x140059be0`
- `0x1400cafac`
- `0x1400f59f4`
- `0x14011e54c`
- `0x140121590`
- `0x140128d50`
- `0x14012be00`
- `0x14012f930`
- `0x14013af10`
- `0x140140380`
- `0x140148f30`
- `0x140153910`
- `0x140153ab0`
- `0x1401633d0`
- `0x140164bd0`
- `0x1401822c0`
- `0x140182c30`
- `0x1401841d0`
- `0x140185c00`
- `0x14019a718`
- `0x14019f220`
- `0x14019f300`
- `0x1401a0b50`
- `0x1401a2cb0`
- `0x1401a5f00`
- `0x1401aab20`
- `0x1401d2c34`
- `0x1401e78e4`
- `0x1401ecb70`
- `0x1401efb98`
- `0x1401f1d30`

## import_xrefs

- `ntoskrnl!IoGetIrpExtraCreateParameter` at `0x1401a2eb8`
- `ntoskrnl!IoGetIrpExtraCreateParameter` at `0x1401a2eb8`
- `ntoskrnl!FsRtlFindExtraCreateParameter` at `0x1401a2ef0`
- `ntoskrnl!FsRtlFindExtraCreateParameter` at `0x1401a2f26`
- `ntoskrnl!FsRtlFindExtraCreateParameter` at `0x1401a379e`
- `ntoskrnl!FsRtlFindExtraCreateParameter` at `0x1401a37df`
- `ntoskrnl!FsRtlFindExtraCreateParameter` at `0x1401a2ef0`
- `ntoskrnl!FsRtlFindExtraCreateParameter` at `0x1401a2f26`
- `ntoskrnl!FsRtlFindExtraCreateParameter` at `0x1401a379e`
- `ntoskrnl!FsRtlFindExtraCreateParameter` at `0x1401a37df`
- `ntoskrnl!FsRtlAcknowledgeEcp` at `0x1401a2f3e`
- `ntoskrnl!FsRtlAcknowledgeEcp` at `0x1401a37b6`
- `ntoskrnl!FsRtlAcknowledgeEcp` at `0x1401a2f3e`
- `ntoskrnl!FsRtlAcknowledgeEcp` at `0x1401a37b6`
- `ntoskrnl!FsRtlIsNonEmptyDirectoryReparsePointAllowed` at `0x1401a425e`
- `ntoskrnl!FsRtlIsNonEmptyDirectoryReparsePointAllowed` at `0x1401a4c0c`
- `ntoskrnl!FsRtlIsNonEmptyDirectoryReparsePointAllowed` at `0x1401a425e`
- `ntoskrnl!FsRtlIsNonEmptyDirectoryReparsePointAllowed` at `0x1401a4c0c`
- `ntoskrnl!TmIsTransactionActive` at `0x1401a5aa0`
- `ntoskrnl!TmIsTransactionActive` at `0x1401a5aa0`
- `ntoskrnl!IoGetCurrentProcess` at `0x1401a56a3`
- `ntoskrnl!IoGetCurrentProcess` at `0x1402ad23f`
- `ntoskrnl!IoGetCurrentProcess` at `0x1401a56a3`
- `ntoskrnl!IoGetCurrentProcess` at `0x1402ad23f`
- `ntoskrnl!PsGetProcessImageFileName` at `0x1401a56b2`
- `ntoskrnl!PsGetProcessImageFileName` at `0x1402ad24e`
- `ntoskrnl!PsGetProcessImageFileName` at `0x1401a56b2`
- `ntoskrnl!PsGetProcessImageFileName` at `0x1402ad24e`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1401a4e05`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1401a5379`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402aceb1`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1401a4e05`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1401a5379`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402aceb1`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1401a479a`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1401a479a`
- `ntoskrnl!KeWaitForSingleObject` at `0x1401a3938`
- `ntoskrnl!KeWaitForSingleObject` at `0x1401a3938`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401a5394`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401a54b7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401a5a2c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402acecc`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402ad040`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402ad65a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401a5394`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401a54b7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401a5a2c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402acecc`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402ad040`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402ad65a`
- `ntoskrnl!CcUnpinData` at `0x1401a4a15`
- `ntoskrnl!CcUnpinData` at `0x1401a5030`
- `ntoskrnl!CcUnpinData` at `0x1401a5341`
- `ntoskrnl!CcUnpinData` at `0x1402ace71`
- `ntoskrnl!CcUnpinData` at `0x1401a4a15`
- `ntoskrnl!CcUnpinData` at `0x1401a5030`
- `ntoskrnl!CcUnpinData` at `0x1401a5341`
- `ntoskrnl!CcUnpinData` at `0x1402ace71`
- `ntoskrnl!FsRtlCheckOplockEx` at `0x1401a5927`
- `ntoskrnl!FsRtlCheckOplockEx` at `0x1402ad53a`
- `ntoskrnl!FsRtlCheckOplockEx` at `0x1401a5927`
- `ntoskrnl!FsRtlCheckOplockEx` at `0x1402ad53a`

## pseudocode

```c
__int64 __fastcall NtfsCommonCreate(__int64 a1, PIRP Irp, __int64 a3)
{
  __int64 v3; // rdi
  PIRP v4; // r13
  __int64 v5; // rsi
  __int64 v6; // r15
  __int64 v7; // r9
  __int64 v8; // r10
  int v9; // ebx
  __int64 v10; // r8
  struct _ECP_LIST *v11; // rcx
  unsigned __int16 **v12; // r14
  unsigned __int16 *v13; // rdx
  unsigned __int16 v14; // cx
  __int16 v15; // r8
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 *v18; // rax
  int v19; // eax
  int v20; // eax
  __int64 v21; // rax
  int InformationForQueryOpen; // ebx
  unsigned __int8 v23; // r9
  IRP *v24; // rdx
  unsigned int v25; // r8d
  __int64 v26; // rax
  unsigned __int8 v27; // r9
  IRP *v28; // rdx
  int v29; // eax
  int v30; // eax
  int v31; // eax
  __int64 v32; // rax
  unsigned __int8 v33; // r9
  IRP *v34; // rdx
  __int64 v35; // rax
  unsigned __int8 v36; // r9
  IRP *v37; // rdx
  __int64 v38; // rax
  unsigned __int8 v39; // r9
  IRP *v40; // rdx
  __int64 v41; // rax
  unsigned __int8 v42; // r9
  IRP *v43; // rdx
  unsigned int v44; // r8d
  __int64 v45; // rbx
  unsigned __int8 v46; // al
  __int64 v47; // rax
  unsigned __int8 v48; // r9
  IRP *v49; // rdx
  unsigned __int16 *v51; // rcx
  int v52; // eax
  __int64 v53; // rax
  unsigned __int8 v54; // r9
  IRP *v55; // rdx
  void *v56; // rcx
  __int64 v57; // rcx
  __int64 QuadPart; // rax
  __int64 v59; // rbx
  __int64 v60; // rax
  unsigned __int8 v61; // r9
  IRP *v62; // rdx
  int v63; // eax
  __int64 v64; // rax
  unsigned __int8 v65; // r9
  IRP *v66; // rdx
  __int128 v67; // xmm0
  char v68; // r8
  int v69; // r8d
  __int64 v70; // r8
  int v71; // r9d
  unsigned int v72; // r8d
  int v73; // r14d
  __int64 v74; // rdx
  unsigned int v75; // eax
  unsigned __int16 v76; // cx
  __int64 v77; // rdx
  unsigned __int8 v78; // r10
  unsigned __int8 v79; // r9
  __int64 v80; // rcx
  int v81; // r8d
  int v82; // edx
  __int64 v83; // rdx
  __int64 v84; // rax
  __int64 v85; // rax
  __int16 v86; // cx
  __int64 *v87; // rax
  __int64 v88; // rax
  __int64 *v89; // rax
  int v90; // eax
  int v91; // r8d
  unsigned int v92; // r8d
  unsigned __int16 v93; // ax
  _WORD *v94; // rcx
  unsigned __int64 v95; // r9
  _WORD **v96; // r8
  __int64 v97; // rax
  unsigned __int64 v98; // rcx
  int v99; // edx
  unsigned int v100; // edx
  int StartingNode; // eax
  unsigned int v102; // ecx
  struct _UNICODE_STRING v103; // xmm6
  char v104; // bl
  unsigned int v105; // ecx
  unsigned int v106; // eax
  char v107; // r8
  __int64 v108; // rdx
  bool v109; // zf
  unsigned int v110; // ecx
  __int64 v111; // r8
  __int16 v112; // dx
  __int16 v113; // ax
  __int16 v114; // cx
  int ReparsePointValue; // eax
  __int16 *Scb; // r15
  __int64 v117; // rcx
  __int64 v118; // rdx
  int v119; // ecx
  int v120; // r9d
  __int64 v121; // rdx
  __int64 v122; // r8
  PVOID v123; // rdx
  _OWORD *v124; // rbx
  __int64 v125; // rax
  char v126; // al
  int v127; // ecx
  unsigned int v128; // ecx
  int v129; // r10d
  __int64 v130; // rax
  int v131; // r9d
  __int64 v132; // r14
  unsigned int v133; // eax
  int v134; // eax
  USHORT Length; // dx
  int v136; // eax
  __int64 v137; // rcx
  __int64 v138; // rax
  unsigned int CurrentFileInfo; // eax
  unsigned int v140; // eax
  unsigned int v141; // eax
  int v142; // ecx
  __int64 v143; // r14
  __int64 v144; // rax
  __int64 v145; // rdx
  __int64 v146; // rax
  signed int v147; // edx
  __int64 v148; // rax
  __int64 v149; // rdx
  __int64 v150; // rdx
  __int64 v151; // rax
  _DWORD *v152; // rcx
  __int64 v153; // rdx
  __int64 v154; // rax
  unsigned int *v155; // rcx
  __int64 v156; // r11
  __int64 v157; // r8
  __int64 v158; // rax
  unsigned __int8 v159; // r15
  PEPROCESS CurrentProcess; // rax
  __int64 ProcessImageFileName; // rax
  __int64 v162; // rdx
  __int64 v163; // rax
  __int64 v164; // rcx
  __int64 v165; // r8
  unsigned int v166; // ecx
  int v167; // r10d
  __int64 v168; // rdx
  __int64 v169; // rdx
  int v170; // eax
  __int64 v171; // r9
  __int64 v172; // rdx
  int v173; // eax
  __int64 v174; // r14
  void *v175; // rcx
  _OWORD *v176; // r15
  struct _KTRANSACTION *v177; // rcx
  struct _FILE_OBJECT *v178; // rcx
  __int64 v179; // rax
  unsigned __int8 v180; // r9
  IRP *v181; // rdx
  PLARGE_INTEGER Timeout; // [rsp+A8h] [rbp-1B8h]
  __int64 v183; // [rsp+B8h] [rbp-1A8h]
  __int64 v184; // [rsp+C8h] [rbp-198h]
  unsigned __int8 v185; // [rsp+FCh] [rbp-164h]
  char v186; // [rsp+FDh] [rbp-163h] BYREF
  char v187; // [rsp+FEh] [rbp-162h]
  __int16 v188; // [rsp+FFh] [rbp-161h] BYREF
  char v189; // [rsp+101h] [rbp-15Fh]
  __int64 v190; // [rsp+108h] [rbp-158h] BYREF
  char v191; // [rsp+110h] [rbp-150h]
  __int64 v192; // [rsp+118h] [rbp-148h]
  PVOID Entry; // [rsp+120h] [rbp-140h] BYREF
  PVOID Bcb; // [rsp+128h] [rbp-138h] BYREF
  __int64 v195; // [rsp+130h] [rbp-130h] BYREF
  int v196; // [rsp+138h] [rbp-128h] BYREF
  __int64 v197; // [rsp+140h] [rbp-120h] BYREF
  char v198; // [rsp+148h] [rbp-118h]
  int v199; // [rsp+14Ch] [rbp-114h] BYREF
  int v200; // [rsp+150h] [rbp-110h]
  struct _UNICODE_STRING v201; // [rsp+158h] [rbp-108h] BYREF
  struct _ECP_LIST *ExtraCreateParameter; // [rsp+168h] [rbp-F8h] BYREF
  __int64 v203; // [rsp+170h] [rbp-F0h]
  void *v204[2]; // [rsp+178h] [rbp-E8h] BYREF
  __int64 v205; // [rsp+188h] [rbp-D8h]
  __int64 v206; // [rsp+190h] [rbp-D0h]
  __int64 v207; // [rsp+198h] [rbp-C8h]
  __int64 v208; // [rsp+1A0h] [rbp-C0h] BYREF
  PVOID P; // [rsp+1A8h] [rbp-B8h] BYREF
  __int64 v210; // [rsp+1B0h] [rbp-B0h]
  PIRP v211; // [rsp+1B8h] [rbp-A8h]
  __int64 v212[2]; // [rsp+1C0h] [rbp-A0h] BYREF
  __int16 *v213; // [rsp+1D0h] [rbp-90h]
  POPLOCK_WAIT_COMPLETE_ROUTINE CompletionRoutine; // [rsp+1D8h] [rbp-88h]
  POPLOCK_FS_PREPOST_IRP v215; // [rsp+1E0h] [rbp-80h]
  struct _UNICODE_STRING v216; // [rsp+1E8h] [rbp-78h]
  __int64 v217[2]; // [rsp+1F8h] [rbp-68h] BYREF
  __int64 v218; // [rsp+208h] [rbp-58h]

  v3 = a3;
  v4 = Irp;
  v5 = a1;
  v205 = a1;
  v211 = Irp;
  v210 = a3;
  *(_OWORD *)v212 = 0;
  v196 = 0;
  v197 = 0;
  v190 = 0;
  LOWORD(v199) = 0;
  P = 0;
  v208 = 0;
  Bcb = 0;
  *(_OWORD *)v217 = 0;
  v218 = 0;
  v195 = 0;
  Entry = 0;
  v186 = 1;
  v201 = 0;
  *(_OWORD *)v204 = 0;
  v188 = 0;
  ExtraCreateParameter = 0;
  v6 = *(_QWORD *)(a1 + 104);
  v192 = v6;
  v207 = v6;
  v7 = *(_QWORD *)(a3 + 176);
  v8 = *(_QWORD *)(v7 + 48);
  *(_QWORD *)(a3 + 32) = v8;
  *(_DWORD *)(a3 + 40) = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v7 + 8) + 8LL) + 16LL);
  *(_DWORD *)(a3 + 44) = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v7 + 8) + 8LL) + 20LL);
  v9 = *(_DWORD *)(*(_QWORD *)(v7 + 8) + 16LL);
  *(_DWORD *)(a3 + 48) = v9;
  *(_DWORD *)(a3 + 64) = 0;
  *(_QWORD *)(a3 + 128) = 0;
  if ( (*(_DWORD *)(a1 + 16) & 0x100000) == 0 )
  {
    if ( (*(_DWORD *)(v7 + 16) & 0x2000) != 0 )
    {
      if ( (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x4000) != 0 )
        McTemplateU0pppppeddddd_EtwWriteTransfer(
          *(unsigned __int16 *)(v7 + 26),
          *(unsigned __int16 *)(v7 + 24),
          Irp,
          a1,
          v6,
          v8,
          *(_QWORD *)(v8 + 64),
          *(unsigned __int16 *)(v8 + 88),
          *(_QWORD *)(v8 + 96),
          *(_DWORD *)(v7 + 16),
          *(unsigned __int16 *)(v7 + 24),
          v9,
          *(unsigned __int16 *)(v7 + 26),
          *(_DWORD *)(v7 + 32));
    }
    else if ( (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x4000) != 0 )
    {
      McTemplateU0pppppwddddd_EtwWriteTransfer(
        *(unsigned __int16 *)(v7 + 26),
        *(unsigned __int16 *)(v7 + 24),
        Irp,
        a1,
        v6,
        v8,
        *(_QWORD *)(v8 + 64),
        *(unsigned __int16 *)(v8 + 88) >> 1,
        *(_QWORD *)(v8 + 96),
        *(_DWORD *)(v7 + 16),
        *(unsigned __int16 *)(v7 + 24),
        v9,
        *(unsigned __int16 *)(v7 + 26),
        *(_DWORD *)(v7 + 32));
    }
  }
  if ( IoGetIrpExtraCreateParameter(v4, &ExtraCreateParameter) >= 0 )
  {
    v11 = ExtraCreateParameter;
    if ( ExtraCreateParameter )
    {
      if ( !v4->RequestorMode )
      {
        if ( FsRtlFindExtraCreateParameter(ExtraCreateParameter, &ECP_TYPE_CLFS_CREATE_CONTAINER, 0, 0) >= 0 )
          *(_DWORD *)(v5 + 436) |= 0x100000u;
        v11 = ExtraCreateParameter;
      }
      v12 = (unsigned __int16 **)(v3 + 224);
      FsRtlFindExtraCreateParameter(v11, &GUID_ECP_ATOMIC_CREATE, (PVOID *)(v3 + 224), 0);
      if ( !*(_QWORD *)(v3 + 224) )
      {
LABEL_192:
        FsRtlFindExtraCreateParameter(ExtraCreateParameter, &GUID_ECP_OPEN_PARAMETERS, (PVOID *)(v3 + 232), 0);
        v56 = *(void **)(v3 + 232);
        if ( v56 )
          FsRtlAcknowledgeEcp(v56);
        FsRtlFindExtraCreateParameter(
          ExtraCreateParameter,
          &GUID_ECP_QUERY_ON_CREATE,
          (PVOID *)(v3 + 208),
          (ULONG *)(v3 + 204));
        goto LABEL_195;
      }
      FsRtlAcknowledgeEcp(*(PVOID *)(v3 + 224));
      v13 = *v12;
      v14 = **v12;
      if ( v14 >= 6u )
      {
        v15 = v13[1];
        if ( (v15 & 2) == 0 || v14 >= 0x10u )
        {
          if ( (v15 & 4) == 0 || v14 >= 0x18u && (v16 = *((_QWORD *)v13 + 2), v16 >= 0) && v16 <= *(_QWORD *)(v6 + 7776) )
          {
            if ( (v15 & 8) == 0
              || v14 >= 0x20u && (v17 = *((_QWORD *)v13 + 3), v17 >= 0) && (v15 & 4) != 0 && v17 <= *((_QWORD *)v13 + 2) )
            {
              if ( (v15 & 0x10) == 0
                || v14 >= 0x28u
                && (v18 = (__int64 *)*((_QWORD *)v13 + 4), *v18 >= -1)
                && v18[1] >= -1
                && v18[2] >= -1
                && v18[3] >= -1 )
              {
                if ( ((v15 & 0x20) == 0 || v14 >= 0x2Cu)
                  && ((v15 & 0x800) == 0 || v14 >= 0x30u && (*((_DWORD *)v13 + 11) & 0xFFFFFFF0) == 0) )
                {
                  if ( (v15 & 0x40) == 0
                    || v14 >= 0x3Cu
                    && (v19 = *((_DWORD *)v13 + 14), (v19 & 0xFF250048) == 0)
                    && ((v20 = v19 & 0x180000) == 0 || v20 == 1572864) )
                  {
                    if ( (v15 & 0x80) != 0 && (v14 < 0x44u || (*((_DWORD *)v13 + 15) & 1) != 0 && v14 < 0x58u) )
                    {
                      if ( (*(_DWORD *)(v5 + 12) & 2) != 0 || *(_QWORD *)(v3 + 136) )
                      {
                        InformationForQueryOpen = -1073741811;
                        if ( NtfsStatusDebugFlags )
                          NtfsStatusTraceAndDebugInternal(v5, 0xC000000D, 0xA6010u);
                        v23 = 1;
                        v24 = 0;
                      }
                      else
                      {
                        v21 = *(_QWORD *)(v5 + 16);
                        InformationForQueryOpen = -1073741811;
                        if ( (v21 & 1) != 0 )
                        {
                          *(_QWORD *)(v5 + 16) = v21 | 2;
                          goto LABEL_57;
                        }
                        if ( NtfsStatusDebugFlags )
                          NtfsStatusTraceAndDebugInternal(v5, 0xC000000D, 0xA6027u);
                        v23 = v4 != 0;
                        v24 = v4;
                      }
                      NtfsExtendedCompleteRequestInternal(v5, v24, -1073741811, v23, 0);
LABEL_57:
                      if ( NtfsStatusDebugFlags )
                      {
                        v25 = 658102;
LABEL_742:
                        NtfsStatusTraceAndDebugInternal(0, InformationForQueryOpen, v25);
                        return (unsigned int)InformationForQueryOpen;
                      }
                      return (unsigned int)InformationForQueryOpen;
                    }
                    if ( v15 < 0 && v14 < 0x4Cu )
                    {
                      if ( (*(_DWORD *)(v5 + 12) & 2) != 0 || *(_QWORD *)(v3 + 136) )
                      {
                        InformationForQueryOpen = -1073741811;
                        if ( NtfsStatusDebugFlags )
                          NtfsStatusTraceAndDebugInternal(v5, 0xC000000D, 0xA6010u);
                        v27 = 1;
                        v28 = 0;
                      }
                      else
                      {
                        v26 = *(_QWORD *)(v5 + 16);
                        InformationForQueryOpen = -1073741811;
                        if ( (v26 & 1) != 0 )
                        {
                          *(_QWORD *)(v5 + 16) = v26 | 2;
                          goto LABEL_72;
                        }
                        if ( NtfsStatusDebugFlags )
                          NtfsStatusTraceAndDebugInternal(v5, 0xC000000D, 0xA6027u);
                        v27 = v4 != 0;
                        v28 = v4;
                      }
                      NtfsExtendedCompleteRequestInternal(v5, v28, -1073741811, v27, 0);
LABEL_72:
                      if ( NtfsStatusDebugFlags )
                      {
                        v25 = 658117;
                        goto LABEL_742;
                      }
                      return (unsigned int)InformationForQueryOpen;
                    }
                    if ( (v15 & 0x100) == 0 )
                    {
                      v29 = (v15 & 0x80) != 0 ? *((_DWORD *)v13 + 15) : 0;
                      if ( (v29 & 0xFFFFFFFE) != 0
                        || ((v15 & 0x80) == 0 ? (LOBYTE(v30) = 0) : (v30 = *((_DWORD *)v13 + 15)),
                            (v30 & 1) == 0 ? (LOBYTE(v31) = 0) : (v31 = *((_DWORD *)v13 + 19)),
                            (v31 & 1) != 0 && (*((_DWORD *)v13 + 20) & 1) != 0 && (dword_140095AD4 & 1) == 0) )
                      {
                        if ( (*(_DWORD *)(v5 + 12) & 2) != 0 || *(_QWORD *)(v3 + 136) )
                        {
                          InformationForQueryOpen = -1073741637;
                          if ( NtfsStatusDebugFlags )
                            NtfsStatusTraceAndDebugInternal(v5, 0xC00000BB, 0xA6010u);
                          v33 = 1;
                          v34 = 0;
                        }
                        else
                        {
                          v32 = *(_QWORD *)(v5 + 16);
                          InformationForQueryOpen = -1073741637;
                          if ( (v32 & 1) != 0 )
                          {
                            *(_QWORD *)(v5 + 16) = v32 | 2;
                            goto LABEL_99;
                          }
                          if ( NtfsStatusDebugFlags )
                            NtfsStatusTraceAndDebugInternal(v5, 0xC00000BB, 0xA6027u);
                          v33 = v4 != 0;
                          v34 = v4;
                        }
                        NtfsExtendedCompleteRequestInternal(v5, v34, -1073741637, v33, 0);
LABEL_99:
                        if ( NtfsStatusDebugFlags )
                        {
                          v25 = 658146;
                          goto LABEL_742;
                        }
                        return (unsigned int)InformationForQueryOpen;
                      }
                    }
                    if ( (v15 & 0x100) == 0 && (v15 & 0x40) != 0 && (*((_DWORD *)v13 + 14) & 0xFF254048) != 0 )
                    {
                      *((_DWORD *)v13 + 14) &= 0xFF254048;
                      (*v12)[2] |= 0x40u;
                      if ( (*(_DWORD *)(v5 + 12) & 2) != 0 || *(_QWORD *)(v3 + 136) )
                      {
                        InformationForQueryOpen = -1073741637;
                        if ( NtfsStatusDebugFlags )
                          NtfsStatusTraceAndDebugInternal(v5, 0xC00000BB, 0xA6010u);
                        v36 = 1;
                        v37 = 0;
                      }
                      else
                      {
                        v35 = *(_QWORD *)(v5 + 16);
                        InformationForQueryOpen = -1073741637;
                        if ( (v35 & 1) != 0 )
                        {
                          *(_QWORD *)(v5 + 16) = v35 | 2;
                          goto LABEL_115;
                        }
                        if ( NtfsStatusDebugFlags )
                          NtfsStatusTraceAndDebugInternal(v5, 0xC00000BB, 0xA6027u);
                        v36 = v4 != 0;
                        v37 = v4;
                      }
                      NtfsExtendedCompleteRequestInternal(v5, v37, -1073741637, v36, 0);
LABEL_115:
                      if ( NtfsStatusDebugFlags )
                      {
                        v25 = 658164;
                        goto LABEL_742;
                      }
                      return (unsigned int)InformationForQueryOpen;
                    }
                    if ( (v15 & 0x40) != 0
                      && (*((_DWORD *)v13 + 14) & 0x800) != 0
                      && _bittest16((const signed __int16 *)(*(_QWORD *)(v3 + 176) + 24LL), 0xEu) )
                    {
                      if ( (*(_DWORD *)(v5 + 12) & 2) != 0 || *(_QWORD *)(v3 + 136) )
                      {
                        InformationForQueryOpen = -1073741637;
                        if ( NtfsStatusDebugFlags )
                          NtfsStatusTraceAndDebugInternal(v5, 0xC00000BB, 0xA6010u);
                        v39 = 1;
                        v40 = 0;
                      }
                      else
                      {
                        v38 = *(_QWORD *)(v5 + 16);
                        InformationForQueryOpen = -1073741637;
                        if ( (v38 & 1) != 0 )
                        {
                          *(_QWORD *)(v5 + 16) = v38 | 2;
                          goto LABEL_131;
                        }
                        if ( NtfsStatusDebugFlags )
                          NtfsStatusTraceAndDebugInternal(v5, 0xC00000BB, 0xA6027u);
                        v39 = v4 != 0;
                        v40 = v4;
                      }
                      NtfsExtendedCompleteRequestInternal(v5, v40, -1073741637, v39, 0);
LABEL_131:
                      if ( NtfsStatusDebugFlags )
                      {
                        v25 = 658176;
                        goto LABEL_742;
                      }
                      return (unsigned int)InformationForQueryOpen;
                    }
                    if ( (*(_DWORD *)(v192 + 24) & 0x40000) != 0
                      && ((v15 & 1) != 0
                       || (v15 & 0x40) != 0 && (v13[28] & *(_WORD *)(*(_QWORD *)(v3 + 176) + 24LL) & 0xA00) != 0) )
                    {
                      if ( (*(_DWORD *)(v5 + 12) & 2) != 0 || *(_QWORD *)(v3 + 136) )
                      {
                        if ( NtfsStatusDebugFlags )
                          NtfsStatusTraceAndDebugInternal(v5, 0xC000049A, 0xA6010u);
                        v42 = 1;
                        v43 = 0;
                      }
                      else
                      {
                        v41 = *(_QWORD *)(v5 + 16);
                        if ( (v41 & 1) != 0 )
                        {
                          *(_QWORD *)(v5 + 16) = v41 | 2;
                          goto LABEL_148;
                        }
                        if ( NtfsStatusDebugFlags )
                          NtfsStatusTraceAndDebugInternal(v5, 0xC000049A, 0xA6027u);
                        v42 = v4 != 0;
                        v43 = v4;
                      }
                      NtfsExtendedCompleteRequestInternal(v5, v43, -1073740646, v42, 0);
LABEL_148:
                      if ( NtfsStatusDebugFlags )
                      {
                        v44 = 658190;
LABEL_213:
                        NtfsStatusTraceAndDebugInternal(0, 0xC000049A, v44);
                        return 3221226650LL;
                      }
                      return 3221226650LL;
                    }
                    if ( (v15 & 8) != 0
                      && *((__int64 *)v13 + 3) > 0
                      && (v15 & 1) == 0
                      && ((v15 & 0x40) == 0 || (v13[28] & *(_WORD *)(*(_QWORD *)(v3 + 176) + 24LL) & 0xA00) == 0) )
                    {
                      v45 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v3 + 176) + 8LL) + 8LL);
                      v46 = NtfsEffectiveMode((__int64)v4);
                      if ( !(unsigned __int8)NtfsPrivilegeCheck(28, v45 + 32, v46) )
                      {
                        if ( (*(_DWORD *)(v5 + 12) & 2) != 0 || *(_QWORD *)(v3 + 136) )
                        {
                          if ( NtfsStatusDebugFlags )
                            NtfsStatusTraceAndDebugInternal(v5, 0xC0000061, 0xA6010u);
                          v48 = 1;
                          v49 = 0;
                        }
                        else
                        {
                          v47 = *(_QWORD *)(v5 + 16);
                          if ( (v47 & 1) != 0 )
                          {
                            *(_QWORD *)(v5 + 16) = v47 | 2;
LABEL_167:
                            if ( NtfsStatusDebugFlags )
                              NtfsStatusTraceAndDebugInternal(0, 0xC0000061, 0xA0B21u);
                            return 3221225569LL;
                          }
                          if ( NtfsStatusDebugFlags )
                            NtfsStatusTraceAndDebugInternal(v5, 0xC0000061, 0xA6027u);
                          v48 = v4 != 0;
                          v49 = v4;
                        }
                        NtfsExtendedCompleteRequestInternal(v5, v49, -1073741727, v48, 0);
                        goto LABEL_167;
                      }
                    }
                    if ( _bittest16((const signed __int16 *)*v12 + 1, 0xBu) )
                    {
                      *(_DWORD *)(v5 + 272) = *((_DWORD *)*v12 + 11);
                      (*v12)[2] |= 0x400u;
                    }
                    if ( *((char *)*v12 + 2) < 0 )
                      (*v12)[2] |= 0x80u;
                    v51 = *v12;
                    if ( *((char *)*v12 + 2) >= 0 )
                      LOBYTE(v52) = 0;
                    else
                      v52 = *((_DWORD *)v51 + 15);
                    if ( (v52 & 1) != 0 )
                    {
                      *((_DWORD *)v51 + 16) |= 1u;
                      *((_DWORD *)*v12 + 21) = 0;
                    }
                    goto LABEL_192;
                  }
                }
              }
            }
          }
        }
      }
      if ( (*(_DWORD *)(v5 + 12) & 2) != 0 || *(_QWORD *)(v3 + 136) )
      {
        InformationForQueryOpen = -1073741811;
        if ( NtfsStatusDebugFlags )
          NtfsStatusTraceAndDebugInternal(v5, 0xC000000D, 0xA6010u);
        v54 = 1;
        v55 = 0;
      }
      else
      {
        v53 = *(_QWORD *)(v5 + 16);
        InformationForQueryOpen = -1073741811;
        if ( (v53 & 1) != 0 )
        {
          *(_QWORD *)(v5 + 16) = v53 | 2;
          goto LABEL_190;
        }
        if ( NtfsStatusDebugFlags )
          NtfsStatusTraceAndDebugInternal(v5, 0xC000000D, 0xA6027u);
        v54 = v4 != 0;
        v55 = v4;
      }
      NtfsExtendedCompleteRequestInternal(v5, v55, -1073741811, v54, 0);
LABEL_190:
      if ( NtfsStatusDebugFlags )
      {
        v25 = 658084;
        goto LABEL_742;
      }
      return (unsigned int)InformationForQueryOpen;
    }
  }
LABEL_195:
  v57 = *(_QWORD *)(v3 + 176);
  if ( (*(_BYTE *)(v57 + 16) & 0x41) == 0x41
    || (QuadPart = v4->Overlay.AllocationSize.QuadPart, v59 = v192, QuadPart > *(_QWORD *)(v192 + 7776))
    || QuadPart < 0 )
  {
    if ( (*(_DWORD *)(v5 + 12) & 2) != 0 || *(_QWORD *)(v3 + 136) )
    {
      InformationForQueryOpen = -1073741811;
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(v5, 0xC000000D, 0xA6010u);
      v180 = 1;
      v181 = 0;
    }
    else
    {
      v179 = *(_QWORD *)(v5 + 16);
      InformationForQueryOpen = -1073741811;
      if ( (v179 & 1) != 0 )
      {
        *(_QWORD *)(v5 + 16) = v179 | 2;
        goto LABEL_740;
      }
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(v5, 0xC000000D, 0xA6027u);
      v180 = v4 != 0;
      v181 = v4;
    }
    NtfsExtendedCompleteRequestInternal(v5, v181, -1073741811, v180, 0);
LABEL_740:
    if ( NtfsStatusDebugFlags )
    {
      v25 = 658274;
      goto LABEL_742;
    }
    return (unsigned int)InformationForQueryOpen;
  }
  if ( (*(_DWORD *)(v192 + 24) & 0x40000) != 0 )
  {
    if ( (*(_WORD *)(v57 + 24) & 0x4000) != 0 )
    {
      if ( (*(_DWORD *)(v5 + 12) & 2) != 0 || *(_QWORD *)(v3 + 136) )
      {
        if ( NtfsStatusDebugFlags )
          NtfsStatusTraceAndDebugInternal(v5, 0xC000049A, 0xA6010u);
        v61 = 1;
        v62 = 0;
      }
      else
      {
        v60 = *(_QWORD *)(v5 + 16);
        if ( (v60 & 1) != 0 )
        {
          *(_QWORD *)(v5 + 16) = v60 | 2;
          goto LABEL_211;
        }
        if ( NtfsStatusDebugFlags )
          NtfsStatusTraceAndDebugInternal(v5, 0xC000049A, 0xA6027u);
        v61 = v4 != 0;
        v62 = v4;
      }
      NtfsExtendedCompleteRequestInternal(v5, v62, -1073740646, v61, 0);
LABEL_211:
      if ( NtfsStatusDebugFlags )
      {
        v44 = 658288;
        goto LABEL_213;
      }
      return 3221226650LL;
    }
  }
  else if ( (*(_WORD *)(v57 + 24) & 0x4000) != 0 )
  {
    *(_DWORD *)(v57 + 16) |= 0x8000u;
  }
  v63 = *(_DWORD *)(v5 + 12);
  if ( (v63 & 1) == 0 )
  {
    LOBYTE(v10) = 1;
    return NtfsPostRequest((char *)v5, v4, v10, 0);
  }
  if ( (v63 & 0x200000) != 0 )
  {
    KeWaitForSingleObject(&NtfsEncryptionPendingEvent, Executive, 0, 0, 0);
    *(_DWORD *)(v5 + 12) &= ~0x200000u;
    v63 = *(_DWORD *)(v5 + 12);
  }
  if ( !v4->Cancel )
  {
    v200 = 0;
    v185 = 0;
    v189 = 0;
    v187 = 0;
    v203 = v3;
    v206 = v3 + 16;
    LOWORD(v212[0]) = 0;
    *(_QWORD *)(v5 + 208) = v3;
    v67 = *(_OWORD *)(*(_QWORD *)(v3 + 32) + 88LL);
    *(_OWORD *)v3 = v67;
    *(_OWORD *)(v3 + 16) = v67;
    if ( (*(_BYTE *)(*(_QWORD *)(v3 + 176) + 2LL) & 2) != 0 )
    {
      *(_DWORD *)(v5 + 12) |= 0x100u;
      v68 = 1;
    }
    else
    {
      if ( !*(_BYTE *)(v59 + 8417)
        && *(_DWORD *)(v59 + 8428) + *(_DWORD *)(v59 + 8420) <= (unsigned int)NtfsThrottleCreates )
      {
LABEL_242:
        LOBYTE(v10) = 1;
        if ( (*(_DWORD *)(v5 + 12) & 0x100) != 0 )
          NtfsAcquireExclusiveVcb(v5, v59, v10);
        else
          NtfsAcquireSharedVcb(v5, v59, v10);
        *(_DWORD *)(v3 + 156) |= 0x800u;
        v69 = *(_DWORD *)(v59 + 4);
        if ( (v69 & 0x802) != 0 )
        {
          if ( (v69 & 0x800) != 0 && (*(_DWORD *)(v5 + 12) & 0x100) == 0 )
          {
            NtfsReleaseVcb(v5, v59);
            *(_DWORD *)(v3 + 156) &= ~0x800u;
            *(_DWORD *)(v5 + 12) |= 0x100u;
            LOBYTE(v70) = 1;
            NtfsAcquireExclusiveVcb(v5, v59, v70);
            *(_DWORD *)(v3 + 156) |= 0x800u;
          }
          v71 = *(_DWORD *)(v59 + 4);
          if ( (v71 & 1) != 0 )
          {
            if ( (*(_DWORD *)(v5 + 16) & 0x100000) == 0
              && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x20) != 0 )
            {
              v74 = *(_QWORD *)(v59 + 248);
              v75 = *(unsigned __int16 *)(v74 + 6);
              if ( v75 > 0x40 || (v75 & 1) != 0 )
              {
                v76 = 0;
                v199 = 0;
                LOWORD(v75) = 0;
              }
              else
              {
                v76 = *(_WORD *)(v74 + 6);
                v199 = v76;
              }
              LOWORD(CompletionRoutine) = v76;
              v215 = (POPLOCK_FS_PREPOST_IRP)(v74 + 32);
              LODWORD(v184) = v71;
              LODWORD(v183) = (unsigned __int16)v75 >> 1;
              LODWORD(Timeout) = *(unsigned __int16 *)(v59 + 7872) >> 1;
              McTemplateU0ppwwd_EtwWriteTransfer(
                (unsigned int)Timeout,
                (const EVENT_DESCRIPTOR *)create_c3106,
                KeGetCurrentThread(),
                v59,
                Timeout,
                *(_QWORD *)(v59 + 7880),
                v183,
                v74 + 32,
                v184);
            }
            InformationForQueryOpen = -1073741790;
            if ( !NtfsStatusDebugFlags )
              goto LABEL_253;
            v72 = 658477;
          }
          else
          {
            InformationForQueryOpen = -1073741202;
            if ( !NtfsStatusDebugFlags )
            {
LABEL_253:
              v73 = 8;
              goto LABEL_587;
            }
            v72 = 658462;
          }
LABEL_252:
          NtfsStatusTraceAndDebugInternal(0, InformationForQueryOpen, v72);
          goto LABEL_253;
        }
        v77 = *(_QWORD *)(v3 + 176);
        v78 = *(_BYTE *)(v77 + 19);
        v185 = v78;
        if ( *(_DWORD *)(v59 + 272)
          && ((*(_DWORD *)(*(_QWORD *)(v77 + 8) + 16LL) & 0x116) != 0
           || v78 != 1 && v78 < 6u
           || (*(_DWORD *)(v77 + 16) & 0x1000) != 0) )
        {
          InformationForQueryOpen = -1073740589;
          if ( !NtfsStatusDebugFlags )
            goto LABEL_253;
          v72 = 658506;
          goto LABEL_252;
        }
        if ( (v69 & 0x20) != 0 )
        {
          InformationForQueryOpen = -1073741431;
          if ( !NtfsStatusDebugFlags )
            goto LABEL_253;
          v72 = 658516;
          goto LABEL_252;
        }
        if ( *(char *)(v77 + 2) >= 0 )
          *(_DWORD *)(v3 + 156) |= 0x20u;
        if ( (*(_DWORD *)(v77 + 16) & 0x2000) != 0 )
          *(_DWORD *)(v3 + 156) |= 0x40u;
        if ( *(_QWORD *)(v3 + 224) )
        {
          if ( v78 == 1 )
          {
            if ( !(unsigned int)Feature_TimestampsOnCreate__private_IsEnabledDeviceUsageNoInline()
              || *(_WORD *)(*(_QWORD *)(v3 + 224) + 2LL) != 0x2000 )
            {
              InformationForQueryOpen = -1073741811;
              if ( !NtfsStatusDebugFlags )
                goto LABEL_253;
              v72 = 658559;
              goto LABEL_252;
            }
          }
          else if ( v78 != 2 )
          {
            InformationForQueryOpen = -1073741637;
            if ( !NtfsStatusDebugFlags )
              goto LABEL_253;
            v72 = 658565;
            goto LABEL_252;
          }
        }
        if ( (*(_DWORD *)(v59 + 4) & 1) == 0 || !(unsigned __int8)NtfsPingVolume(v5, v59, 0) )
        {
          *(_DWORD *)(v5 + 4) |= 0x200000u;
          NtfsRaiseStatusInternal(v5, -1073741608, 0, 0, 658585);
        }
        v79 = v185;
        if ( (v185 & 0xFA) == 0 && v185 != 1
          || (v80 = *(_QWORD *)(v3 + 176), (*(_DWORD *)(v80 + 16) & 8) != 0)
          || (v81 = *(_DWORD *)(v5 + 436), (v81 & 0x10000) != 0)
          || *(_QWORD *)(v3 + 184)
          && ((v82 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v80 + 8) + 8LL) + 16LL)
                   | *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v80 + 8) + 8LL) + 24LL),
               (v82 & 0x2000000) != 0)
           || (v81 & 6) != 0
           || (v82 & 0x10D0116) != 0) )
        {
          *(_DWORD *)(v5 + 4) |= 0x10000u;
        }
        if ( (*(_BYTE *)(*(_QWORD *)(v3 + 176) + 2LL) & 2) != 0 )
        {
          NtfsFspCloseInternal(0, v59, 1, 0, 0);
          v79 = v185;
        }
        v83 = *(_QWORD *)(v3 + 32);
        v84 = *(_QWORD *)(v83 + 64);
        if ( v84 )
        {
          *(_QWORD *)(v83 + 16) = *(_QWORD *)(v84 + 16);
          if ( *(_WORD *)v3 && **(_WORD **)(v3 + 8) == 58 && (unsigned __int8)(v79 - 2) <= 1u )
            *(_DWORD *)(v5 + 4) |= 0x10000u;
          v83 = *(_QWORD *)(v3 + 32);
          v85 = *(_QWORD *)(*(_QWORD *)(v83 + 64) + 32LL);
          if ( v85 && (*(_DWORD *)(v85 + 8) & 0x10) != 0 )
            *(_DWORD *)(v3 + 156) |= 0x400000u;
        }
        if ( (*(_DWORD *)(v3 + 156) & 0x40) != 0 )
        {
          v86 = *(_WORD *)v3;
          if ( ((*(_WORD *)v3 - 8) & 0xFFFD) != 0 )
          {
            if ( ((v86 - 16) & 0xFFFD) != 0 )
            {
              InformationForQueryOpen = -1073741811;
              if ( !NtfsStatusDebugFlags )
                goto LABEL_253;
              v72 = 658744;
              goto LABEL_252;
            }
            if ( v86 == 16 )
            {
              v87 = *(__int64 **)(v83 + 96);
              if ( !v87[1] )
              {
                v88 = *v87;
LABEL_327:
                v195 = v88;
                goto LABEL_328;
              }
            }
            if ( v86 != 18 || (v89 = *(__int64 **)(v83 + 96), *(__int64 *)((char *)v89 + 10)) )
            {
              if ( !*(_QWORD *)(v59 + 160) )
              {
                InformationForQueryOpen = -1073741811;
                if ( !NtfsStatusDebugFlags )
                  goto LABEL_253;
                v72 = 658739;
                goto LABEL_252;
              }
              if ( (int)NtfsLookupObjectId(v5) < 0 )
              {
                InformationForQueryOpen = -1073741772;
                if ( !NtfsStatusDebugFlags )
                  goto LABEL_253;
                v72 = 658732;
                goto LABEL_252;
              }
              _InterlockedIncrement((volatile signed __int32 *)(v59 + 8552));
              v83 = *(_QWORD *)(v3 + 32);
LABEL_328:
              *(_QWORD *)(v83 + 96) = 0;
              *(_WORD *)(*(_QWORD *)(v3 + 32) + 88LL) = 0;
              v90 = NtfsOpenFcbById(v5, (__int64)&NtfsEmptyString, 0, v3);
              InformationForQueryOpen = v90;
              if ( v90 != 259 && v90 != 871 )
              {
                v91 = *(_DWORD *)(v3 + 156);
                if ( (*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v3 + 176) + 8LL) + 8LL) + 12LL) & 1) != 0 )
                  v92 = v91 & 0xFFFFFFEF;
                else
                  v92 = v91 | 0x10;
                *(_DWORD *)(v3 + 156) = v92;
                *(_QWORD *)(*(_QWORD *)(v3 + 32) + 96LL) = *(_QWORD *)(v3 + 8);
                *(_WORD *)(*(_QWORD *)(v3 + 32) + 88LL) = *(_WORD *)v3;
              }
LABEL_580:
              v73 = 8;
LABEL_581:
              if ( !InformationForQueryOpen )
              {
                if ( v200 <= 0 || (InformationForQueryOpen = 0, v200 == 264) )
                  InformationForQueryOpen = v200;
              }
              if ( InformationForQueryOpen == 259 || InformationForQueryOpen == 871 )
              {
                v5 = 0;
                v205 = 0;
                v4 = 0;
                v211 = 0;
                v3 = 0;
                v210 = 0;
                goto LABEL_592;
              }
LABEL_587:
              *(_DWORD *)(v3 + 156) |= 0x100u;
              v146 = *(_QWORD *)(v5 + 144);
              v147 = *(_DWORD *)(v146 + 24);
              if ( v147 < 0 )
              {
                if ( NtfsStatusDebugFlags
                  && (unsigned int)v147 < 0xFFFFFFED
                  && v147 != -1073741802
                  && (unsigned int)(v147 + 2147483643) > 1
                  && v147 != -1073741807
                  && v147 != -1073741608 )
                {
                  NtfsStatusTraceAndDebugInternal(v5, v147, 0xA12F1u);
                }
                NtfsRaiseStatusInternal(v5, *(_DWORD *)(*(_QWORD *)(v5 + 144) + 24LL), 0, 0, 660209);
              }
              if ( InformationForQueryOpen < 0 && *(_DWORD *)(v146 + 28) )
              {
                if ( NtfsStatusDebugFlags
                  && (unsigned int)InformationForQueryOpen < 0xFFFFFFED
                  && InformationForQueryOpen != -1073741802
                  && (unsigned int)(InformationForQueryOpen + 2147483643) > 1
                  && InformationForQueryOpen != -1073741807
                  && InformationForQueryOpen != -1073741608 )
                {
                  NtfsStatusTraceAndDebugInternal(v5, InformationForQueryOpen, 0xA12F1u);
                }
                NtfsRaiseStatusInternal(v5, InformationForQueryOpen, 0, 0, 660209);
              }
              NtfsCheckpointCurrentTransaction(v5);
LABEL_592:
              if ( Bcb )
              {
                CcUnpinData(Bcb);
                Bcb = 0;
              }
              if ( Entry )
              {
                NtfsCleanupIndexContext(v5, (__int64)Entry);
                ExFreeToLookasideListEx(&NtfsIndexContextLookasideList, Entry);
              }
              if ( P )
                ExFreePoolWithTag(P, 0);
              if ( InformationForQueryOpen == 259 )
                return (unsigned int)InformationForQueryOpen;
              if ( InformationForQueryOpen == 871 )
              {
LABEL_711:
                if ( InformationForQueryOpen == 259 || InformationForQueryOpen == 871 )
                  return (unsigned int)InformationForQueryOpen;
                if ( InformationForQueryOpen < 0 )
                {
                  v177 = *(struct _KTRANSACTION **)(v3 + 184);
                  if ( v177 )
                  {
                    if ( !TmIsTransactionActive(v177) )
                    {
                      InformationForQueryOpen = -1072103421;
                      if ( NtfsStatusDebugFlags )
                        NtfsStatusTraceAndDebugInternal(0, 0xC0190003, 0xA156Cu);
                    }
                  }
                }
                if ( (*(_DWORD *)(v5 + 4) & 1) != 0 )
                {
                  if ( InformationForQueryOpen < 0 )
                    goto LABEL_728;
                  InformationForQueryOpen = NtfsCompleteLargeAllocation(
                                              v5,
                                              (__int64)v4,
                                              v190,
                                              *(_QWORD *)(v3 + 104),
                                              *(_QWORD *)(v3 + 112),
                                              *(_DWORD *)(v3 + 156));
                  if ( !InformationForQueryOpen )
                  {
                    if ( v200 > 0 && v200 != 264 )
                    {
                      InformationForQueryOpen = 0;
                      goto LABEL_726;
                    }
                    InformationForQueryOpen = v200;
                  }
                }
                if ( InformationForQueryOpen >= 0 )
                {
LABEL_726:
                  v178 = *(struct _FILE_OBJECT **)(*(_QWORD *)(v3 + 176) + 48LL);
                  if ( v178->SectionObjectPointer )
                    NtfsUpdateBackingFileObject(v178, ChangeDataControlArea);
                }
LABEL_728:
                NtfsCompleteCreateRequest(v5, v3, v4, InformationForQueryOpen);
                return (unsigned int)InformationForQueryOpen;
              }
              if ( (*(_DWORD *)(v3 + 156) & 0x400) != 0 )
              {
                v148 = *(_QWORD *)(v3 + 128);
                if ( !v148 || (v149 = *(_QWORD *)(v148 + 184), v149 == *(_QWORD *)(v3 + 96)) )
                {
                  v150 = *(_QWORD *)(v3 + 96);
                  if ( v150 )
                  {
                    NtfsReleaseFcbWithPaging(v5, v150);
                    *(_QWORD *)(v3 + 96) = 0;
                  }
                }
                else
                {
                  NtfsReleaseFcbWithPaging(v5, v149);
                }
              }
              if ( InformationForQueryOpen < 0 || InformationForQueryOpen == 260 )
              {
                if ( (*(_DWORD *)(*(_QWORD *)(v3 + 176) + 16LL) & 0x10000) != 0
                  && InformationForQueryOpen != -1073739511 )
                {
                  v169 = *(_QWORD *)(v3 + 104);
                  if ( v169 )
                  {
                    if ( (v170 = *(_DWORD *)(v169 + 256), v170 == 128) && *(_WORD *)v169 == 1797
                      || v170 == 160
                      && *(_WORD *)(v169 + 264) == 8
                      && **(_QWORD **)(v169 + 272) == 0x30003300490024LL
                      && (unsigned __int16)(*(_WORD *)v169 - 1795) <= 1u )
                    {
                      FsRtlCheckOplockEx((POPLOCK)(v169 + 88), *(PIRP *)(v5 + 112), 4u, 0, 0, 0);
                    }
                  }
                }
                if ( (*(_DWORD *)(v3 + 156) & 0x100) != 0 )
                {
                  v171 = *(_QWORD *)(v3 + 104);
                  if ( v171 )
                  {
                    if ( *(_QWORD *)(v3 + 112) )
                      NtfsBackoutFailedOpensPriv(
                        v5,
                        *(_QWORD *)(*(_QWORD *)(v3 + 176) + 48LL),
                        *(_QWORD *)(v3 + 96),
                        v171,
                        v3 + 112);
                  }
                }
                v172 = *(_QWORD *)(v3 + 96);
                if ( v172 )
                {
                  v173 = *(_DWORD *)(v172 + 8);
                  if ( v173 == 6 || !v173 )
                  {
                    NtfsReleaseFcbEx(v5, v172, 0);
                  }
                  else
                  {
                    if ( *(_QWORD *)(v3 + 104) )
                      v172 = *(_QWORD *)(v3 + 104);
                    NtfsTeardownStructures(v5, v172, v197, *(_DWORD *)(v5 + 28) != 0, 0);
                  }
                }
                if ( InformationForQueryOpen == -1073741432
                  || InformationForQueryOpen == -1073741608
                  || InformationForQueryOpen == 260 )
                {
                  *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v3 + 176) + 8LL) + 8LL) + 16LL) = *(_DWORD *)(v3 + 40);
                  *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v3 + 176) + 8LL) + 8LL) + 20LL) = *(_DWORD *)(v3 + 44);
                  *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v3 + 176) + 8LL) + 16LL) = *(_DWORD *)(v3 + 48);
                }
                v174 = v206;
                v175 = *(void **)(v206 + 8);
                v176 = (_OWORD *)v203;
                if ( v175 && *(void **)(v203 + 8) != v175 )
                {
                  ExFreePoolWithTag(v175, 0);
                  *(_QWORD *)(v174 + 8) = 0;
                }
                *(_OWORD *)(*(_QWORD *)(v3 + 32) + 88LL) = *v176;
                *(_DWORD *)(v5 + 4) &= ~1u;
                goto LABEL_708;
              }
              if ( !v187 )
              {
                v151 = *(_QWORD *)(v3 + 104);
                if ( *(_WORD *)(v151 + 264) && *(_DWORD *)(v151 + 256) == 128 && NtfsTelemetryGuard(0x200u) )
                  NtfsTelemetryNamedStreams(v192, *(_QWORD *)(*(_QWORD *)(v3 + 104) + 32LL));
                if ( NtfsTelemetryGuard(0x200u) )
                  NtfsTelemetryCreateFile(v192, v3, v185);
              }
              if ( *(_QWORD *)(v3 + 208) )
                NtfsQueryInformationForCreate(v5, (__int64)v4, v3);
              v152 = *(_DWORD **)(v203 + 8);
              if ( v152 && v152 != *(_DWORD **)(v206 + 8) && v152 != *(_DWORD **)(*(_QWORD *)(v3 + 32) + 96LL) )
                ExFreePoolWithTag(v152, 0);
              if ( *(_QWORD *)(v3 + 136) )
              {
                if ( !v187 )
                {
                  InformationForQueryOpen = NtfsQueryInformationForQueryOpen(v5, (__int64)v4, v3);
                  v168 = *(_QWORD *)(v3 + 104);
                  if ( !*(_DWORD *)(v168 + 208)
                    && !*(_DWORD *)(*(_QWORD *)(v168 + 184) + 268LL)
                    && !NtfsAddScbToFspClose(v5, (_QWORD *)v168, 1, 1, 0) )
                  {
                    NtfsTeardownStructures(v5, *(_QWORD *)(v3 + 96), v197, *(_DWORD *)(v5 + 28) != 0, 0);
                  }
                  if ( NtfsStatusDebugFlags
                    && InformationForQueryOpen
                    && InformationForQueryOpen != 294
                    && (unsigned int)(InformationForQueryOpen - 298) > 1
                    && (unsigned int)InformationForQueryOpen < 0xFFFFFFED
                    && InformationForQueryOpen != -1073741802
                    && (unsigned int)(InformationForQueryOpen + 2147483643) > 1
                    && InformationForQueryOpen != -1073741807
                    && InformationForQueryOpen != 259
                    && InformationForQueryOpen != -1073741608 )
                  {
                    NtfsStatusTraceAndDebugInternal(0, InformationForQueryOpen, 0xA14CEu);
                  }
                  v4->IoStatus.Status = InformationForQueryOpen;
                }
                goto LABEL_708;
              }
              v153 = *(_QWORD *)(*(_QWORD *)(v3 + 112) + 72LL);
              v190 = v153;
              if ( (*(_BYTE *)(*(_QWORD *)(v3 + 176) + 2LL) & 2) != 0 )
              {
                NtfsDeleteInternalAttributeStream(v5, *(_QWORD *)(v3 + 104), 1, 0);
                v153 = v190;
              }
              if ( (*(_DWORD *)(v5 + 4) & 1) != 0 )
              {
                v152 = (_DWORD *)*(unsigned int *)(*(_QWORD *)(v3 + 112) + 4LL);
                if ( ((unsigned __int8)v152 & 2) != 0 )
                {
                  if ( v153 )
                  {
                    --*(_WORD *)(*(_QWORD *)(v3 + 96) + 188LL);
                    SetFlagInterlocked((unsigned int *)(v190 + 4), 1u);
                    if ( (*(_BYTE *)(*(_QWORD *)(v190 + 192) + 65LL) & 3) != 0 )
                    {
                      v152 = *(_DWORD **)(v190 + 48);
                      v152[1] |= 0x20u;
                    }
                  }
                }
                else
                {
                  SetFlagInterlocked((unsigned int *)(*(_QWORD *)(v3 + 104) + 200LL), 2u);
                }
              }
              if ( (*(_DWORD *)(v3 + 156) & 0x20) != 0 )
                SetFlagInterlocked((unsigned int *)(*(_QWORD *)(v3 + 112) + 4LL), 1u);
              v154 = *(_QWORD *)(v3 + 232);
              if ( v154 && *(_WORD *)v154 >= 8u && (*(_DWORD *)(v154 + 4) & 8) != 0 )
                SetFlagInterlocked((unsigned int *)(*(_QWORD *)(v3 + 112) + 4LL), 0x4000000u);
              if ( (*(_DWORD *)(v3 + 156) & 0x10) != 0 )
                SetFlagInterlocked((unsigned int *)(*(_QWORD *)(v3 + 112) + 4LL), 0x80u);
              NtfsSetCcbAccessFlags(v152, v4, v3);
              if ( (*(_DWORD *)(*(_QWORD *)(v3 + 176) + 16LL) & 0x1000) != 0 )
              {
                v155 = (unsigned int *)(*(_QWORD *)(v3 + 112) + 4LL);
                v156 = v192;
                if ( (*(_BYTE *)v155 & 0xA) == 0xA )
                  goto LABEL_650;
                v157 = *(_QWORD *)(v3 + 96);
                if ( v157 == *(_QWORD *)(*(_QWORD *)(v192 + 136) + 184LL)
                  || v157 == *(_QWORD *)(*(_QWORD *)(v192 + 152) + 184LL)
                  || v157 == *(_QWORD *)(*(_QWORD *)(v192 + 160) + 184LL) )
                {
                  goto LABEL_650;
                }
                *(_DWORD *)(v3 + 156) |= 4u;
                if ( (*(_DWORD *)(v5 + 4) & 1) == 0 )
                  SetFlagInterlocked(v155, 0x40000u);
                if ( !v190 )
                  goto LABEL_650;
                v158 = *(_QWORD *)(v190 + 24);
                if ( !v158 )
                  goto LABEL_650;
                v159 = *(_BYTE *)(*(_QWORD *)(v158 + 184) + 36LL);
                if ( (unsigned __int8)(v159 - 1) > 6u )
                  goto LABEL_650;
                CurrentProcess = IoGetCurrentProcess();
                ProcessImageFileName = PsGetProcessImageFileName(CurrentProcess);
                FsLibTelemetryAddDeleteFileTableEntry(v192 + 9576, ProcessImageFileName, v159);
              }
              v156 = v192;
LABEL_650:
              v162 = *(_QWORD *)(v3 + 112);
              if ( (*(_DWORD *)(v162 + 4) & 8) == 0 )
              {
                v163 = *(_QWORD *)(v3 + 224);
                if ( !v163 || (*(_WORD *)(v163 + 2) & 0x400) == 0 )
                {
                  v164 = *(_QWORD *)(v3 + 104);
                  v165 = v164 + 264;
                  if ( *(_WORD *)(v164 + 264) )
                  {
                    if ( *(_DWORD *)(v164 + 256) == 128 )
                    {
                      v166 = *(_DWORD *)(v164 + 512);
                      if ( (v166 & 0x1A00) != 0 )
                      {
                        v167 = 512;
                        if ( (v166 & 0x200) != 0 )
                        {
                          v73 = 6;
                        }
                        else
                        {
                          v167 = (v166 >> 1) & 0x400 | 0x800;
                          if ( (v166 & 0x1000) == 0 )
                            v167 = (v166 >> 1) & 0x400;
                        }
                        NtfsReportDirNotify(
                          v5,
                          *(_QWORD *)(v162 + 72),
                          v156,
                          (unsigned __int16 *)(v162 + 16),
                          *(unsigned __int16 *)(v162 + 32),
                          v165,
                          v167,
                          v73,
                          0,
                          0);
                      }
                    }
                  }
                }
              }
              *(_DWORD *)(*(_QWORD *)(v3 + 104) + 512LL) &= 0xFFFFE1FF;
LABEL_708:
              if ( (*(_DWORD *)(v3 + 156) & 0x800) != 0 && (*(_BYTE *)(v5 + 16) & 0x20) == 0 )
              {
                NtfsReleaseVcb(v5, v192);
                *(_DWORD *)(v3 + 156) &= ~0x800u;
              }
              goto LABEL_711;
            }
          }
          else
          {
            v89 = *(__int64 **)(v83 + 96);
            if ( v86 == 8 )
            {
              v88 = *v89;
              goto LABEL_327;
            }
          }
          v88 = *(__int64 *)((char *)v89 + 2);
          goto LABEL_327;
        }
        v93 = *(_WORD *)(v83 + 88);
        if ( v93 > 2u )
        {
          v94 = *(_WORD **)(v83 + 96);
          if ( v94[1] == 92 && *v94 == 92 )
          {
            *(_WORD *)(v83 + 88) = v93 - 2;
            memmove(
              *(void **)(*(_QWORD *)(v3 + 32) + 96LL),
              (const void *)(*(_QWORD *)(*(_QWORD *)(v3 + 32) + 96LL) + 2LL),
              *(unsigned __int16 *)(*(_QWORD *)(v3 + 32) + 88LL));
            v83 = *(_QWORD *)(v3 + 32);
            if ( *(_WORD *)(v83 + 88) > 2u && *(_WORD *)(*(_QWORD *)(v83 + 96) + 2LL) == 92 )
            {
              InformationForQueryOpen = -1073741773;
              if ( !NtfsStatusDebugFlags )
                goto LABEL_253;
              v72 = 658814;
              goto LABEL_252;
            }
          }
        }
        v95 = *(unsigned __int16 *)(v83 + 88);
        if ( (_WORD)v95 )
        {
          v96 = (_WORD **)(v83 + 96);
          if ( *(_QWORD *)(v83 + 64) && **v96 == 92 )
          {
            InformationForQueryOpen = -1073741811;
            if ( !NtfsStatusDebugFlags )
              goto LABEL_253;
            v72 = 658828;
            goto LABEL_252;
          }
          if ( (*v96)[(v95 >> 1) - 1] == 92 && (unsigned int)v95 > 2 )
          {
            *(_DWORD *)(v3 + 156) |= 8u;
            *(_WORD *)(v83 + 88) -= 2;
            v97 = *(_QWORD *)(v3 + 32);
            v98 = *(unsigned __int16 *)(v97 + 88);
            if ( (_WORD)v98 )
            {
              if ( *(_WORD *)(*(_QWORD *)(v97 + 96) + 2 * (v98 >> 1) - 2) == 92 )
              {
                InformationForQueryOpen = -1073741773;
                if ( !NtfsStatusDebugFlags )
                  goto LABEL_253;
                v72 = 658850;
                goto LABEL_252;
              }
            }
          }
        }
        v99 = *(_DWORD *)(v3 + 156);
        if ( (*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v3 + 176) + 8LL) + 8LL) + 12LL) & 1) != 0 )
          v100 = v99 & 0xFFFFFFEF;
        else
          v100 = v99 | 0x10;
        *(_DWORD *)(v3 + 156) = v100;
        StartingNode = NtfsFindStartingNode(v5, (__int64)v4, &v201, v212, &v196, &v190, &v197, (unsigned __int16 *)v3);
        InformationForQueryOpen = StartingNode;
        if ( StartingNode < 0 || StartingNode == 259 || StartingNode == 871 )
        {
          v73 = 8;
          goto LABEL_581;
        }
        if ( !v201.Length )
        {
          v73 = 8;
          goto LABEL_581;
        }
        v200 = StartingNode;
        v102 = *(_DWORD *)(v3 + 156) | 0x2000;
        *(_DWORD *)(v3 + 156) = v102;
        while ( 1 )
        {
          v103 = 0;
          if ( (v102 & 0x80000) != 0
            || (v102 & 0x200) != 0
            && (TxfGetCurrentFileInfo(v5, *(_QWORD *)(v3 + 96), 1, 1, *(_QWORD *)(v3 + 184)) & 0x400) != 0 )
          {
            break;
          }
LABEL_404:
          if ( (*(_DWORD *)(*(_QWORD *)(v3 + 96) + 176LL) & 0x10000000) == 0 )
          {
            InformationForQueryOpen = -1073741766;
            if ( NtfsStatusDebugFlags )
              NtfsStatusTraceAndDebugInternal(0, 0xC000003A, 0xA0F13u);
            v73 = 8;
            goto LABEL_581;
          }
          InformationForQueryOpen = NtfsDissectName(&v201, (struct _UNICODE_STRING *)v204, &v201);
          if ( InformationForQueryOpen < 0 )
          {
            v73 = 8;
            goto LABEL_581;
          }
          if ( LOWORD(v204[0]) > 0x1FEu )
          {
            if ( v201.Length )
            {
              InformationForQueryOpen = -1073741766;
              if ( NtfsStatusDebugFlags )
                NtfsStatusTraceAndDebugInternal(0, 0xC000003A, 0xA0F31u);
              v73 = 8;
            }
            else
            {
              InformationForQueryOpen = -1073741773;
              if ( NtfsStatusDebugFlags )
                NtfsStatusTraceAndDebugInternal(0, 0xC0000033, 0xA0F2Du);
              v73 = 8;
            }
            goto LABEL_581;
          }
          if ( LOWORD(v204[0]) == 2 && *(_WORD *)v204[1] == 46 )
          {
            if ( v201.Length )
            {
              InformationForQueryOpen = -1073741766;
              if ( NtfsStatusDebugFlags )
                NtfsStatusTraceAndDebugInternal(0, 0xC000003A, 0xA0F3Fu);
              v73 = 8;
            }
            else
            {
              InformationForQueryOpen = -1073741773;
              if ( NtfsStatusDebugFlags )
                NtfsStatusTraceAndDebugInternal(0, 0xC0000033, 0xA0F47u);
              v73 = 8;
            }
            goto LABEL_581;
          }
          Scb = NtfsCreateScb(v5, *(_QWORD *)(v3 + 96), 160, &NtfsFileNameIndex, 0, 0, 0);
          v213 = Scb;
          if ( (*(_DWORD *)(*((_QWORD *)Scb + 23) + 16LL) & 0x400) != 0 )
          {
            v117 = *(_QWORD *)(v3 + 232);
            if ( v117 && *(_WORD *)v117 >= 8u && (*(_DWORD *)(v117 + 4) & 0x10) != 0 )
            {
              InformationForQueryOpen = -1073740614;
              if ( NtfsStatusDebugFlags )
                NtfsStatusTraceAndDebugInternal(0, 0xC00004BA, 0xA0F72u);
              v73 = 8;
              goto LABEL_581;
            }
            *(_DWORD *)(v3 + 156) |= 0x1000u;
          }
          v118 = *(_QWORD *)(v3 + 128);
          if ( v118 && !Scb[328] && *(_WORD *)(v118 + 656) )
            NtfsUpdateNormalizedName(v5, v118, (__int64)Scb, 0, 0);
          if ( v190 )
          {
            if ( (*(_DWORD *)(*(_QWORD *)(v190 + 48) + 4LL) & 0x20100) == 0 )
            {
              v119 = *(_DWORD *)(v3 + 156);
              if ( (v119 & 0x201000) == 0 )
              {
                v120 = *(_DWORD *)(v3 + 84);
                if ( v120 )
                {
                  if ( !v201.Length
                    && (*(_DWORD *)(v190 + 4) & 0x20) == 0
                    && (v119 & 1) == 0
                    && (*(_BYTE *)(*(_QWORD *)(v190 + 192) + 65LL) & 3) != 2 )
                  {
                    NtfsInsertPrefixHashEntry(v5, v192 + 4968, v190, v120, *(_DWORD *)(v3 + 80));
                  }
                }
              }
            }
          }
          v121 = *(_QWORD *)(v3 + 128);
          if ( v121 )
            *(_DWORD *)(v3 + 156) &= ~0x400u;
          if ( (*(_DWORD *)(v3 + 156) & 0x2000) == 0 )
          {
            NtfsReleaseFcbWithPaging(v5, *(_QWORD *)(v121 + 184));
            *(_QWORD *)(v3 + 128) = 0;
          }
          if ( (*(_DWORD *)(v3 + 156) & 0x10) != 0 )
            NtfsAccessCheck(v5, v3, *(_QWORD **)(v3 + 96), 0, (__int64)v4, 32, 1, 0, 1);
          if ( !NtfsIsFileNameValid((unsigned __int16 *)v204, 0) )
          {
            InformationForQueryOpen = -1073741773;
            if ( NtfsStatusDebugFlags )
              NtfsStatusTraceAndDebugInternal(0, 0xC0000033, 0xA0FD9u);
            v73 = 8;
            goto LABEL_581;
          }
          v123 = Entry;
          if ( !Entry )
          {
            v124 = ExAllocateFromLookasideListEx(&NtfsIndexContextLookasideList);
            Entry = v124;
            memset((char *)v124 + 88, 0, 0x118u);
            *v124 = 0;
            v124[1] = 0;
            v124[2] = 0;
            v124[3] = 0;
            v124[4] = 0;
            *((_QWORD *)v124 + 10) = 0;
            *((_QWORD *)v124 + 12) = v124 + 7;
            *((_WORD *)v124 + 164) = 3;
            v123 = Entry;
          }
          LOBYTE(v122) = (*(_DWORD *)(v3 + 156) & 0x20) != 0
                      && ((v125 = *(_QWORD *)(v3 + 232)) != 0
                       && *(_WORD *)v125 >= 8u
                       && (*(_DWORD *)(v125 + 4) & 8) != 0
                       || (*(_DWORD *)(*((_QWORD *)Scb + 23) + 16LL) & 0x400) == 0);
          v126 = NtfsLookupEntry(
                   v5,
                   (__int64)Scb,
                   v122,
                   (unsigned __int16 *)v204,
                   &P,
                   &v199,
                   (__int64)v217,
                   (__int64)&v208,
                   (__int64)&Bcb,
                   (__int64)v123);
          v127 = *(_DWORD *)(v3 + 156);
          if ( v126 )
            v128 = v127 | 0x4000;
          else
            v128 = v127 & 0xFFFFBFFF;
          *(_DWORD *)(v3 + 156) = v128;
          if ( *(_DWORD *)(v5 + 28) )
          {
            NtfsCheckpointCurrentTransaction(v5);
            NtfsReleaseSharedResources(v5);
          }
          v129 = *(_DWORD *)(v3 + 156);
          *(_DWORD *)(v3 + 156) = v129 & 0xFFEFFFFF;
          if ( !*((_QWORD *)Scb + 66) )
            goto LABEL_495;
          v131 = 0;
          if ( (v129 & 0x20) != 0
            && ((v130 = *(_QWORD *)(v3 + 232)) != 0 && *(_WORD *)v130 >= 8u && (*(_DWORD *)(v130 + 4) & 8) != 0
             || (*(_DWORD *)(*((_QWORD *)Scb + 23) + 16LL) & 0x400) == 0) )
          {
            v131 = 1;
          }
          InformationForQueryOpen = TxfCheckPathComponent(
                                      v5,
                                      v3,
                                      (__int64)Scb,
                                      (unsigned __int16 *)v204,
                                      v129 & 0x4000,
                                      v201.Length == 0,
                                      v185,
                                      *(_BYTE *)(*(_QWORD *)(v3 + 176) + 2LL) & 4,
                                      v129 & 0x400000,
                                      v131,
                                      &v195,
                                      (_BYTE *)&v188 + 1,
                                      &v188);
          if ( (_BYTE)v188 )
            *(_DWORD *)(v3 + 156) |= 0x200000u;
          if ( InformationForQueryOpen )
          {
            if ( InformationForQueryOpen != -1 )
            {
              v73 = 8;
              goto LABEL_581;
            }
            if ( HIBYTE(v188) )
              *(_DWORD *)(v3 + 156) |= 0x400000u;
            *(_DWORD *)(v3 + 156) |= 0x4000u;
            HIDWORD(v217[0]) = 0;
            NtfsRemoveFromFileRecordCache(v5, *(_DWORD *)(*((_QWORD *)Scb + 23) + 8LL));
            if ( Bcb )
            {
              CcUnpinData(Bcb);
              Bcb = 0;
            }
            v132 = 0;
            v208 = 0;
            NtfsReleaseFcbWithPaging(v5, *(_QWORD *)(v3 + 96));
            *(_QWORD *)(v3 + 96) = 0;
            Scb = 0;
            v213 = 0;
            v133 = *(_DWORD *)(v3 + 156) & 0xFFFFFBFF;
            *(_DWORD *)(v3 + 156) = v133;
            v134 = v133 | 0x100000;
            *(_DWORD *)(v3 + 156) = v134;
            Length = v201.Length;
            if ( !v201.Length )
            {
              *(_DWORD *)(v3 + 156) = v134 | 0x40;
              v136 = NtfsOpenFcbById(v5, (__int64)v212, 0, v3);
              InformationForQueryOpen = v136;
              if ( v136 == 259 || v136 == 871 || (v137 = *(_QWORD *)(v3 + 112)) == 0 )
              {
                v73 = 8;
              }
              else
              {
                v73 = 8;
                SetFlagInterlocked((unsigned int *)(v137 + 8), 8u);
              }
              goto LABEL_581;
            }
          }
          else
          {
LABEL_495:
            v132 = v208;
            Length = v201.Length;
          }
          v102 = *(_DWORD *)(v3 + 156);
          if ( (v102 & 0x4000) != 0 )
          {
            if ( (v102 & 0xA0000) == 0x80000 )
              goto LABEL_498;
            if ( (v102 & 0x100020) == 0x20
              && ((v138 = *(_QWORD *)(v3 + 232)) != 0 && *(_WORD *)v138 >= 8u && (*(_DWORD *)(v138 + 4) & 8) != 0
               || (*(_DWORD *)(*((_QWORD *)Scb + 23) + 16LL) & 0x400) == 0) )
            {
              memmove(v204[1], (const void *)(v132 + 82), LOWORD(v204[0]));
            }
LABEL_524:
            v140 = *(_DWORD *)(v3 + 156) & 0xFFF7FFFF;
            *(_DWORD *)(v3 + 156) = v140;
            if ( !v201.Length )
            {
              if ( (v140 & 0x4000) != 0 )
              {
                NtfsCleanupIndexContext(v5, (__int64)Entry);
                ExFreeToLookasideListEx(&NtfsIndexContextLookasideList, Entry);
                Entry = 0;
                *(_QWORD *)(v3 + 128) = Scb;
                if ( *(_QWORD *)(v3 + 136) )
                {
                  v141 = *(_DWORD *)(v3 + 152) - 68;
                  if ( v141 <= 9 )
                  {
                    v142 = 517;
                    if ( _bittest(&v142, v141) )
                    {
                      if ( !*(_QWORD *)(v3 + 208) )
                        v186 = 0;
                    }
                  }
                }
                InformationForQueryOpen = NtfsOpenFile(
                                            v5,
                                            (__int64)&Bcb,
                                            (__int64)v204,
                                            (int)v212,
                                            v196,
                                            (__int64)v217,
                                            v3,
                                            (__int64)&v197,
                                            (__int64)&v186);
                if ( InformationForQueryOpen == -1073741792 )
                {
                  InformationForQueryOpen = NtfsFillStatInfoFromMftRecord(v5, *(_DWORD *)(v3 + 152), v132);
                  if ( InformationForQueryOpen < 0 )
                  {
                    v186 = 1;
                    InformationForQueryOpen = NtfsOpenFile(
                                                v5,
                                                (__int64)&Bcb,
                                                (__int64)v204,
                                                (int)v212,
                                                v196,
                                                (__int64)v217,
                                                v3,
                                                (__int64)&v197,
                                                (__int64)&v186);
                  }
                  else
                  {
                    v187 = 1;
                    if ( NtfsStatusDebugFlags
                      && InformationForQueryOpen
                      && InformationForQueryOpen != 294
                      && (unsigned int)(InformationForQueryOpen - 298) > 1
                      && InformationForQueryOpen != 259 )
                    {
                      NtfsStatusTraceAndDebugInternal(0, InformationForQueryOpen, 0xA129Fu);
                    }
                    v4->IoStatus.Status = InformationForQueryOpen;
                    v4->IoStatus.Information = **(unsigned int **)(v3 + 144);
                  }
                }
              }
              else
              {
                *(_QWORD *)(v3 + 128) = Scb;
                if ( *(_QWORD *)(v3 + 136) )
                {
                  InformationForQueryOpen = -1073741772;
                  if ( NtfsStatusDebugFlags )
                    NtfsStatusTraceAndDebugInternal(0, 0xC0000034, 0xA1238u);
                  *(_DWORD *)(v3 + 156) |= 2u;
                }
                else
                {
                  InformationForQueryOpen = NtfsCreateNewFile(
                                              v5,
                                              v206,
                                              (__int64)v204,
                                              (__int64)v212,
                                              v196,
                                              (__int64)&Entry,
                                              v3,
                                              (__int64)&v197);
                  *(_DWORD *)(v3 + 156) |= 2u;
                }
              }
              v143 = v192;
              if ( InformationForQueryOpen >= 0 && *(_QWORD *)(v3 + 184) && NtfsTelemetryGuard(0x200u) )
                NtfsTelemetryTxf(v143);
              goto LABEL_580;
            }
            if ( (v140 & 0x100000) == 0 )
            {
              NtfsRemoveFromFileRecordCache(v5, *(_DWORD *)(*((_QWORD *)Scb + 23) + 8LL));
              v195 = *(_QWORD *)v132;
              v189 = *(_BYTE *)(v132 + 81);
              v198 = v189;
              if ( Bcb )
              {
                CcUnpinData(Bcb);
                Bcb = 0;
              }
              v208 = 0;
            }
            NtfsReinitializeIndexContext(v5, (__int64)Entry);
            *(_QWORD *)(v3 + 128) = Scb;
            v144 = NtfsOpenSubdirectory(v5, v189, v3, (__int64)&v197);
            v190 = v144;
            *(_DWORD *)(v3 + 156) |= 0x200u;
            if ( (v144
               && ((*(_DWORD *)(v144 + 4) & 1) != 0
                || (*(_BYTE *)(*(_QWORD *)(v144 + 192) + 65LL) & 3) != 0
                && (*(_DWORD *)(*(_QWORD *)(v144 + 48) + 4LL) & 0x20) != 0)
               || !*(_WORD *)(*(_QWORD *)(v3 + 96) + 188LL))
              && !(unsigned __int8)TxfCheckOpenThroughDeletedComponent(v5, v3, *(_QWORD *)(v3 + 96)) )
            {
              InformationForQueryOpen = -1073741738;
              if ( NtfsStatusDebugFlags )
                NtfsStatusTraceAndDebugInternal(0, 0xC0000056, 0xA11E8u);
              v73 = 8;
              goto LABEL_581;
            }
            v145 = v190;
            if ( v190 )
            {
              if ( (*(_DWORD *)(*(_QWORD *)(v190 + 48) + 4LL) & 0x20100) == 0 && (*(_DWORD *)(v3 + 156) & 0x200000) == 0 )
              {
                NtfsInsertPrefix();
                v145 = v190;
              }
              *(_OWORD *)(v145 + 152) = *(_OWORD *)v217;
              *(_QWORD *)(v145 + 168) = v218;
              if ( (*(_BYTE *)(*(_QWORD *)(v190 + 192) + 65LL) & 3) == 2 )
                *(_DWORD *)(v3 + 156) |= 1u;
              v102 = *(_DWORD *)(v3 + 156) & 0xFFFFDFFF;
            }
            else
            {
              v102 = *(_DWORD *)(v3 + 156) | 0x2000;
            }
            *(_DWORD *)(v3 + 156) = v102;
          }
          else
          {
            if ( (v102 & 0xC0000) != 0x80000 )
            {
              if ( Length || (*(_BYTE *)(*(_QWORD *)(v3 + 176) + 2LL) & 4) != 0 )
              {
                InformationForQueryOpen = -1073741766;
                if ( NtfsStatusDebugFlags )
                  NtfsStatusTraceAndDebugInternal(0, 0xC000003A, 0xA1156u);
                v73 = 8;
                goto LABEL_581;
              }
              if ( (TxfGetCurrentFileInfo(v5, *(_QWORD *)(v3 + 96), 1, 1, *(_QWORD *)(v3 + 184)) & 0x400) != 0 )
              {
                CurrentFileInfo = TxfGetCurrentFileInfo(v5, *(_QWORD *)(v3 + 96), 0, 1, *(_QWORD *)(v3 + 184));
                if ( !(unsigned __int8)FsRtlIsNonEmptyDirectoryReparsePointAllowed(CurrentFileInfo) )
                {
                  InformationForQueryOpen = -1073741183;
                  if ( NtfsStatusDebugFlags )
                    NtfsStatusTraceAndDebugInternal(0, 0xC0000281, 0xA116Cu);
                  v73 = 8;
                  goto LABEL_581;
                }
              }
              if ( v185 == 1 || v185 == 4 )
              {
                InformationForQueryOpen = -1073741772;
                if ( NtfsStatusDebugFlags )
                  NtfsStatusTraceAndDebugInternal(0, 0xC0000034, 0xA1171u);
                v73 = 8;
                goto LABEL_581;
              }
              if ( (*(_DWORD *)(*(_QWORD *)(v3 + 176) + 16LL) & 1) != 0 && v185 == 5 )
              {
                InformationForQueryOpen = -1073741773;
                if ( NtfsStatusDebugFlags )
                  NtfsStatusTraceAndDebugInternal(0, 0xC0000033, 0xA1179u);
                v73 = 8;
                goto LABEL_581;
              }
              if ( (*(_DWORD *)(v192 + 4) & 0x2000000) != 0 )
              {
                InformationForQueryOpen = -1073741662;
                if ( NtfsStatusDebugFlags )
                  NtfsStatusTraceAndDebugInternal(0, 0xC00000A2, 0xA117Eu);
                v73 = 8;
                goto LABEL_581;
              }
              goto LABEL_524;
            }
LABEL_498:
            v201 = v103;
          }
        }
        v104 = 1;
        v191 = 1;
        v105 = *(_DWORD *)(v3 + 156);
        if ( (v105 & 0x80000) != 0 )
        {
LABEL_386:
          if ( v104 )
          {
            if ( (v105 & 0x10) != 0 )
            {
              v111 = *(_QWORD *)(v3 + 96);
              if ( (*(_DWORD *)(v111 + 176) & 0x10000000) != 0 )
                NtfsAccessCheck(v5, v3, (_QWORD *)v111, 0, (__int64)v4, 32, 1, 0, 1);
              else
                NtfsAccessCheck(v5, v3, (_QWORD *)v111, 0, (__int64)v4, 1179785, 1, 0, 0);
            }
            if ( *(_QWORD *)(v3 + 136) )
            {
              if ( NtfsStatusDebugFlags )
                NtfsStatusTraceAndDebugInternal(0, 0x104u, 0xA0ED8u);
              InformationForQueryOpen = 260;
              v73 = 8;
              goto LABEL_581;
            }
            v112 = *(_WORD *)(v3 + 64);
            v113 = *(_WORD *)(v3 + 66);
            v114 = v112 + v113;
            if ( v113 )
            {
              v114 += 4;
            }
            else if ( v112 )
            {
              v114 += 2;
            }
            if ( v201.Length )
              v114 += 2;
            ReparsePointValue = NtfsGetReparsePointValue(v5, v201.Length + v114, 0);
            InformationForQueryOpen = ReparsePointValue;
            if ( ReparsePointValue < 0 || ReparsePointValue == 260 )
            {
              v73 = 8;
              goto LABEL_581;
            }
          }
          goto LABEL_404;
        }
        v106 = TxfGetCurrentFileInfo(v5, *(_QWORD *)(v3 + 96), 0, 1, *(_QWORD *)(v3 + 184));
        NtfsLookupOpenReparseEcp(v5, v3, v106, 0);
        if ( (*(_DWORD *)(*(_QWORD *)(v3 + 96) + 176LL) & 0x10000000) != 0
          && (unsigned __int8)FsRtlIsNonEmptyDirectoryReparsePointAllowed(*(unsigned int *)(v3 + 200)) )
        {
          v107 = 1;
          v108 = *(_QWORD *)(v3 + 216);
          if ( !v108 )
          {
LABEL_373:
            v110 = *(_DWORD *)(v3 + 156) | 0x20000;
            goto LABEL_375;
          }
          v109 = (*(_DWORD *)(v108 + 20) & 2) == 0;
        }
        else
        {
          v107 = 0;
          v108 = *(_QWORD *)(v3 + 216);
          if ( !v108 )
            goto LABEL_374;
          v109 = (*(_DWORD *)(v108 + 20) & 0x10) == 0;
        }
        if ( v109 )
          goto LABEL_373;
LABEL_374:
        v110 = *(_DWORD *)(v3 + 156) & 0xFFFDFFFF;
LABEL_375:
        *(_DWORD *)(v3 + 156) = v110;
        if ( v107 )
        {
          if ( !v108 || (*(_DWORD *)(v108 + 20) & 4) == 0 )
            goto LABEL_382;
        }
        else if ( v108 && (*(_DWORD *)(v108 + 20) & 0x10) == 0 )
        {
LABEL_382:
          v105 = v110 | 0x40000;
          goto LABEL_383;
        }
        v105 = v110 & 0xFFFBFFFF;
LABEL_383:
        *(_DWORD *)(v3 + 156) = v105;
        if ( (v105 & 0x60000) != 0 )
        {
          v104 = 0;
          v191 = 0;
          if ( (v105 & 0x60000) != 0x60000 )
          {
            v105 |= 0x80000u;
            *(_DWORD *)(v3 + 156) = v105;
            v103 = v201;
            v216 = v201;
          }
        }
        goto LABEL_386;
      }
      v68 = 0;
    }
    NtfsFspCloseInternal(0, v59, v68, 0, 0);
    goto LABEL_242;
  }
  if ( (v63 & 2) != 0 || *(_QWORD *)(v3 + 136) )
  {
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(v5, 0xC0000120, 0xA6010u);
    v65 = 1;
    v66 = 0;
    goto LABEL_232;
  }
  v64 = *(_QWORD *)(v5 + 16);
  if ( (v64 & 1) == 0 )
  {
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(v5, 0xC0000120, 0xA6027u);
    v65 = v4 != 0;
    v66 = v4;
LABEL_232:
    NtfsExtendedCompleteRequestInternal(v5, v66, -1073741536, v65, 0);
    goto LABEL_233;
  }
  *(_QWORD *)(v5 + 16) = v64 | 2;
LABEL_233:
  if ( NtfsStatusDebugFlags )
    NtfsStatusTraceAndDebugInternal(0, 0xC0000120, 0xA0BB3u);
  return 3221225760LL;
}

```

## disassembly

```asm
0x1401a2cb0  mov     r11, rsp
0x1401a2cb3  push    rbx
0x1401a2cb4  push    rsi
0x1401a2cb5  push    rdi
0x1401a2cb6  push    r12
0x1401a2cb8  push    r13
0x1401a2cba  push    r14
0x1401a2cbc  push    r15
0x1401a2cbe  sub     rsp, 1A0h
0x1401a2cc5  movaps  xmmword ptr [r11-48h], xmm6
0x1401a2cca  mov     rax, cs:__security_cookie
0x1401a2cd1  xor     rax, rsp
0x1401a2cd4  mov     [rsp+1D8h+var_50], rax
0x1401a2cdc  mov     rdi, r8
0x1401a2cdf  mov     r13, rdx
0x1401a2ce2  mov     rsi, rcx
0x1401a2ce5  mov     [r11-0D8h], rcx
0x1401a2cec  mov     [r11-0A8h], rdx
0x1401a2cf3  mov     [r11-0B0h], r8
0x1401a2cfa  xorps   xmm0, xmm0
0x1401a2cfd  movups  xmmword ptr [rsp+1D8h+var_A0], xmm0
0x1401a2d05  xor     r12d, r12d
0x1401a2d08  mov     [r11-128h], r12d
0x1401a2d0f  mov     [r11-120h], r12
0x1401a2d16  mov     [r11-158h], r12
0x1401a2d1d  mov     [r11-114h], r12w
0x1401a2d25  mov     [r11-0B8h], r12
0x1401a2d2c  mov     [r11-0C0h], r12
0x1401a2d33  mov     [r11-138h], r12
0x1401a2d3a  xor     eax, eax
0x1401a2d3c  movups  xmmword ptr [r11-68h], xmm0
0x1401a2d41  mov     [r11-58h], rax
0x1401a2d45  mov     [r11-130h], r12
0x1401a2d4c  mov     [r11-140h], r12
0x1401a2d53  mov     byte ptr [rsp+1D8h+var_163+3], al
0x1401a2d57  mov     byte ptr [rsp+1D8h+var_163], 1
0x1401a2d5c  movups  [rsp+1D8h+var_108], xmm0
0x1401a2d64  xorps   xmm1, xmm1
0x1401a2d67  movups  xmmword ptr [rsp+1D8h+var_E8], xmm1
0x1401a2d6f  mov     byte ptr [rsp+1D8h+var_163+2], al
0x1401a2d73  mov     [r11-0F8h], r12
0x1401a2d7a  mov     r15, [rcx+68h]
0x1401a2d7e  mov     [rsp+1D8h+var_148], r15
0x1401a2d86  mov     [rsp+1D8h+var_C8], r15
0x1401a2d8e  mov     r9, [r8+0B0h]
0x1401a2d95  mov     r10, [r9+30h]
0x1401a2d99  mov     [r8+20h], r10
0x1401a2d9d  mov     rax, [r9+8]
0x1401a2da1  mov     rcx, [rax+8]
0x1401a2da5  mov     eax, [rcx+10h]
0x1401a2da8  mov     [r8+28h], eax
0x1401a2dac  mov     rax, [r9+8]
0x1401a2db0  mov     rcx, [rax+8]
0x1401a2db4  mov     eax, [rcx+14h]
0x1401a2db7  mov     [r8+2Ch], eax
0x1401a2dbb  mov     rax, [r9+8]
0x1401a2dbf  mov     ebx, [rax+10h]
0x1401a2dc2  mov     [r8+30h], ebx
0x1401a2dc6  mov     [r8+40h], r12d
0x1401a2dca  mov     [r8+80h], r12
0x1401a2dd1  mov     eax, [rsi+10h]
0x1401a2dd4  bt      rax, 14h
0x1401a2dd9  jb      loc_1401A2EAD
0x1401a2ddf  mov     r11d, [r9+10h]
0x1401a2de3  bt      r11d, 0Dh
0x1401a2de8  jnb     short loc_1401A2E4D
0x1401a2dea  test    byte ptr cs:Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits+1, 40h
0x1401a2df1  jz      loc_1401A2EAD
0x1401a2df7  movzx   ecx, word ptr [r9+1Ah]
0x1401a2dfc  movzx   edx, word ptr [r9+18h]
0x1401a2e01  movzx   r8d, word ptr [r10+58h]
0x1401a2e06  mov     eax, [r9+20h]
0x1401a2e0a  mov     [rsp+1D8h+var_170], eax
0x1401a2e0e  mov     dword ptr [rsp+1D8h+var_178], ecx
0x1401a2e12  mov     dword ptr [rsp+1D8h+var_180], ebx
0x1401a2e16  mov     dword ptr [rsp+1D8h+var_188], edx
0x1401a2e1a  mov     dword ptr [rsp+1D8h+var_190], r11d
0x1401a2e1f  mov     rax, [r10+60h]
0x1401a2e23  mov     [rsp+1D8h+var_198], rax
0x1401a2e28  mov     [rsp+1D8h+var_1A0], r8d
0x1401a2e2d  mov     rax, [r10+40h]
0x1401a2e31  mov     [rsp+1D8h+var_1A8], rax
0x1401a2e36  mov     [rsp+1D8h+PostIrpRoutine], r10
0x1401a2e3b  mov     [rsp+1D8h+Timeout], r15
0x1401a2e40  mov     r9, rsi
0x1401a2e43  mov     r8, r13
0x1401a2e46  call    McTemplateU0pppppeddddd_EtwWriteTransfer
0x1401a2e4b  jmp     short loc_1401A2EAD
0x1401a2e4d  test    byte ptr cs:Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits+1, 40h
0x1401a2e54  jz      short loc_1401A2EAD
0x1401a2e56  movzx   ecx, word ptr [r9+1Ah]
0x1401a2e5b  movzx   edx, word ptr [r9+18h]
0x1401a2e60  movzx   r8d, word ptr [r10+58h]
0x1401a2e65  shr     r8d, 1
0x1401a2e68  mov     eax, [r9+20h]
0x1401a2e6c  mov     [rsp+1D8h+var_170], eax
0x1401a2e70  mov     dword ptr [rsp+1D8h+var_178], ecx
0x1401a2e74  mov     dword ptr [rsp+1D8h+var_180], ebx
0x1401a2e78  mov     dword ptr [rsp+1D8h+var_188], edx
0x1401a2e7c  mov     dword ptr [rsp+1D8h+var_190], r11d
0x1401a2e81  mov     rax, [r10+60h]
0x1401a2e85  mov     [rsp+1D8h+var_198], rax
0x1401a2e8a  mov     [rsp+1D8h+var_1A0], r8d
0x1401a2e8f  mov     rax, [r10+40h]
0x1401a2e93  mov     [rsp+1D8h+var_1A8], rax
0x1401a2e98  mov     [rsp+1D8h+PostIrpRoutine], r10
0x1401a2e9d  mov     [rsp+1D8h+Timeout], r15
0x1401a2ea2  mov     r9, rsi
0x1401a2ea5  mov     r8, r13
0x1401a2ea8  call    McTemplateU0pppppwddddd_EtwWriteTransfer
0x1401a2ead  lea     rdx, [rsp+1D8h+ExtraCreateParameter]; ExtraCreateParameter
0x1401a2eb5  mov     rcx, r13; Irp
0x1401a2eb8  call    cs:__imp_IoGetIrpExtraCreateParameter
0x1401a2ebf  nop     dword ptr [rax+rax+00h]
0x1401a2ec4  test    eax, eax
0x1401a2ec6  js      loc_1401A37ED
0x1401a2ecc  mov     rcx, [rsp+1D8h+ExtraCreateParameter]; EcpList
0x1401a2ed4  test    rcx, rcx
0x1401a2ed7  jz      loc_1401A37ED
0x1401a2edd  cmp     [r13+40h], r12b
0x1401a2ee1  jnz     short loc_1401A2F12
0x1401a2ee3  xor     r9d, r9d; EcpContextSize
0x1401a2ee6  xor     r8d, r8d; EcpContext
0x1401a2ee9  lea     rdx, ECP_TYPE_CLFS_CREATE_CONTAINER; EcpType
0x1401a2ef0  call    cs:__imp_FsRtlFindExtraCreateParameter
0x1401a2ef7  nop     dword ptr [rax+rax+00h]
0x1401a2efc  test    eax, eax
0x1401a2efe  js      short loc_1401A2F0A
0x1401a2f00  or      dword ptr [rsi+1B4h], 100000h
0x1401a2f0a  mov     rcx, [rsp+1D8h+ExtraCreateParameter]; EcpList
0x1401a2f12  lea     r14, [rdi+0E0h]
0x1401a2f19  xor     r9d, r9d; EcpContextSize
0x1401a2f1c  mov     r8, r14; EcpContext
0x1401a2f1f  lea     rdx, GUID_ECP_ATOMIC_CREATE; EcpType
0x1401a2f26  call    cs:__imp_FsRtlFindExtraCreateParameter
0x1401a2f2d  nop     dword ptr [rax+rax+00h]
0x1401a2f32  mov     rcx, [r14]; EcpContext
0x1401a2f35  test    rcx, rcx
0x1401a2f38  jz      loc_1401A3779
0x1401a2f3e  call    cs:__imp_FsRtlAcknowledgeEcp
0x1401a2f45  nop     dword ptr [rax+rax+00h]
0x1401a2f4a  mov     rdx, [r14]
0x1401a2f4d  movzx   ecx, word ptr [rdx]
0x1401a2f50  cmp     cx, 6
0x1401a2f54  jb      loc_1401A36DC
0x1401a2f5a  movzx   r8d, word ptr [rdx+2]
0x1401a2f5f  test    r8b, 2
0x1401a2f63  jz      short loc_1401A2F6F
0x1401a2f65  cmp     cx, 10h
0x1401a2f69  jb      loc_1401A36DC
0x1401a2f6f  movzx   r9d, r8w
0x1401a2f73  and     r9w, 4
0x1401a2f78  jz      short loc_1401A2F9E
0x1401a2f7a  cmp     cx, 18h
0x1401a2f7e  jb      loc_1401A36DC
0x1401a2f84  mov     rax, [rdx+10h]
0x1401a2f88  test    rax, rax
0x1401a2f8b  js      loc_1401A36DC
0x1401a2f91  cmp     rax, [r15+1E60h]
0x1401a2f98  jg      loc_1401A36DC
0x1401a2f9e  movzx   r15d, r8w
0x1401a2fa2  and     r15w, 8
0x1401a2fa7  jz      short loc_1401A2FD4
0x1401a2fa9  cmp     cx, 20h ; ' '
0x1401a2fad  jb      loc_1401A36DC
0x1401a2fb3  mov     rax, [rdx+18h]
0x1401a2fb7  test    rax, rax
0x1401a2fba  js      loc_1401A36DC
0x1401a2fc0  test    r9w, r9w
0x1401a2fc4  jz      loc_1401A36DC
0x1401a2fca  cmp     rax, [rdx+10h]
0x1401a2fce  jg      loc_1401A36DC
0x1401a2fd4  test    r8b, 10h
0x1401a2fd8  jz      short loc_1401A3013
0x1401a2fda  cmp     cx, 28h ; '('
0x1401a2fde  jb      loc_1401A36DC
0x1401a2fe4  mov     rax, [rdx+20h]
0x1401a2fe8  cmp     qword ptr [rax], 0FFFFFFFFFFFFFFFFh
0x1401a2fec  jl      loc_1401A36DC
0x1401a2ff2  cmp     qword ptr [rax+8], 0FFFFFFFFFFFFFFFFh
0x1401a2ff7  jl      loc_1401A36DC
0x1401a2ffd  cmp     qword ptr [rax+10h], 0FFFFFFFFFFFFFFFFh
0x1401a3002  jl      loc_1401A36DC
0x1401a3008  cmp     qword ptr [rax+18h], 0FFFFFFFFFFFFFFFFh
0x1401a300d  jl      loc_1401A36DC
0x1401a3013  test    r8b, 20h
0x1401a3017  jz      short loc_1401A3023
0x1401a3019  cmp     cx, 2Ch ; ','
0x1401a301d  jb      loc_1401A36DC
0x1401a3023  bt      r8w, 0Bh
0x1401a3029  jnb     short loc_1401A3042
0x1401a302b  cmp     cx, 30h ; '0'
0x1401a302f  jb      loc_1401A36DC
0x1401a3035  test    dword ptr [rdx+2Ch], 0FFFFFFF0h
0x1401a303c  jnz     loc_1401A36DC
0x1401a3042  movzx   r9d, r8w
0x1401a3046  and     r9w, 40h
0x1401a304b  movzx   ebx, r9w
0x1401a304f  jz      short loc_1401A307B
0x1401a3051  cmp     cx, 3Ch ; '<'
0x1401a3055  jb      loc_1401A36DC
0x1401a305b  mov     eax, [rdx+38h]
0x1401a305e  test    eax, 0FF250048h
0x1401a3063  jnz     loc_1401A36DC
0x1401a3069  and     eax, 180000h
0x1401a306e  jz      short loc_1401A307B
0x1401a3070  cmp     eax, 180000h
0x1401a3075  jnz     loc_1401A36DC
0x1401a307b  mov     eax, 80h
0x1401a3080  movzx   r10d, r8w
0x1401a3084  and     r10w, ax
0x1401a3088  jz      loc_1401A3146
0x1401a308e  cmp     cx, 44h ; 'D'
0x1401a3092  jb      short loc_1401A30A9
0x1401a3094  mov     eax, [rdx+3Ch]
0x1401a3097  test    al, 1
0x1401a3099  jz      loc_1401A3146
0x1401a309f  cmp     cx, 58h ; 'X'
0x1401a30a3  jnb     loc_1401A3146
0x1401a30a9  mov     eax, [rsi+0Ch]
0x1401a30ac  test    al, 2
0x1401a30ae  jnz     short loc_1401A30F7
0x1401a30b0  cmp     [rdi+88h], r12
0x1401a30b7  jnz     short loc_1401A30F7
0x1401a30b9  mov     rax, [rsi+10h]
0x1401a30bd  mov     ebx, 0C000000Dh
0x1401a30c2  test    al, 1
0x1401a30c4  jz      short loc_1401A30D0
0x1401a30c6  or      rax, 2
0x1401a30ca  mov     [rsi+10h], rax
0x1401a30ce  jmp     short loc_1401A312C
0x1401a30d0  movzx   eax, cs:NtfsStatusDebugFlags
0x1401a30d7  test    al, al
0x1401a30d9  jz      short loc_1401A30EB
0x1401a30db  mov     r8d, 0A6027h
0x1401a30e1  mov     edx, ebx
0x1401a30e3  mov     rcx, rsi
0x1401a30e6  call    NtfsStatusTraceAndDebugInternal
0x1401a30eb  test    r13, r13
0x1401a30ee  setnz   r9b
0x1401a30f2  mov     rdx, r13
0x1401a30f5  jmp     short loc_1401A311C
0x1401a30f7  movzx   eax, cs:NtfsStatusDebugFlags
0x1401a30fe  mov     ebx, 0C000000Dh
0x1401a3103  test    al, al
0x1401a3105  jz      short loc_1401A3117
0x1401a3107  mov     r8d, 0A6010h
0x1401a310d  mov     edx, ebx
0x1401a310f  mov     rcx, rsi
0x1401a3112  call    NtfsStatusTraceAndDebugInternal
0x1401a3117  mov     r9b, 1
0x1401a311a  xor     edx, edx
0x1401a311c  mov     dword ptr [rsp+1D8h+Timeout], r12d
0x1401a3121  mov     r8d, ebx
0x1401a3124  mov     rcx, rsi
0x1401a3127  call    NtfsExtendedCompleteRequestInternal
0x1401a312c  movzx   eax, cs:NtfsStatusDebugFlags
0x1401a3133  test    al, al
0x1401a3135  jz      loc_1401A5BF5
0x1401a313b  mov     r8d, 0A0AB6h
0x1401a3141  jmp     loc_1401A5BEC
0x1401a3146  test    r8w, r8w
0x1401a314a  jns     loc_1401A31F7
0x1401a3150  cmp     cx, 4Ch ; 'L'
0x1401a3154  jnb     loc_1401A31F7
0x1401a315a  mov     eax, [rsi+0Ch]
0x1401a315d  test    al, 2
0x1401a315f  jnz     short loc_1401A31A8
0x1401a3161  cmp     [rdi+88h], r12
0x1401a3168  jnz     short loc_1401A31A8
0x1401a316a  mov     rax, [rsi+10h]
0x1401a316e  mov     ebx, 0C000000Dh
0x1401a3173  test    al, 1
0x1401a3175  jz      short loc_1401A3181
0x1401a3177  or      rax, 2
0x1401a317b  mov     [rsi+10h], rax
0x1401a317f  jmp     short loc_1401A31DD
0x1401a3181  movzx   eax, cs:NtfsStatusDebugFlags
0x1401a3188  test    al, al
0x1401a318a  jz      short loc_1401A319C
0x1401a318c  mov     r8d, 0A6027h
0x1401a3192  mov     edx, ebx
0x1401a3194  mov     rcx, rsi
0x1401a3197  call    NtfsStatusTraceAndDebugInternal
0x1401a319c  test    r13, r13
0x1401a319f  setnz   r9b
0x1401a31a3  mov     rdx, r13
0x1401a31a6  jmp     short loc_1401A31CD
0x1401a31a8  movzx   eax, cs:NtfsStatusDebugFlags
0x1401a31af  mov     ebx, 0C000000Dh
0x1401a31b4  test    al, al
0x1401a31b6  jz      short loc_1401A31C8
0x1401a31b8  mov     r8d, 0A6010h
0x1401a31be  mov     edx, ebx
0x1401a31c0  mov     rcx, rsi
0x1401a31c3  call    NtfsStatusTraceAndDebugInternal
0x1401a31c8  mov     r9b, 1
0x1401a31cb  xor     edx, edx
0x1401a31cd  mov     dword ptr [rsp+1D8h+Timeout], r12d
0x1401a31d2  mov     r8d, ebx
  ... truncated ...
```
