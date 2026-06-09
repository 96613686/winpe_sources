# HsmpRpCommitNoLock

- ea: `0x140067d04`
- end: `0x140069709`
- name: `HsmpRpCommitNoLock`
- size: `6661`
- prototype: ``
- caller_count: `11`
- callee_count: `30`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140002aec`
- `0x14004348c`
- `0x140043bac`
- `0x140047b30`
- `0x14005fcc4`
- `0x140075878`
- `0x140075dc4`
- `0x14007af2c`
- `0x14007b5ec`
- `0x14007e3b8`
- `0x14007f994`

## callees

- `0x140003c50`
- `0x140009300`
- `0x14000abb8`
- `0x14000b62c`
- `0x14000db8c`
- `0x14001aa30`
- `0x14001aac8`
- `0x14001ab2c`
- `0x14001abc8`
- `0x14001e140`
- `0x14001e280`
- `0x14001e580`
- `0x140055e90`
- `0x140057828`
- `0x140058cbc`
- `0x14005a6bc`
- `0x140065058`
- `0x1400650a0`
- `0x140067800`
- `0x14006781c`
- `0x140067838`
- `0x140067854`
- `0x140067b50`
- `0x140067d04`
- `0x140069710`
- `0x14006975c`
- `0x140069828`
- `0x140069920`
- `0x14006a790`
- `0x14007658c`

## import_xrefs

- `ntoskrnl!RtlComputeCrc32` at `0x1400685e0`
- `ntoskrnl!RtlComputeCrc32` at `0x1400685e0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006888d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400688a6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006888d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400688a6`
- `ntoskrnl!ExAllocatePool2` at `0x140068167`
- `ntoskrnl!ExAllocatePool2` at `0x140068167`
- `FLTMGR!FltTagFile` at `0x140069634`
- `FLTMGR!FltTagFile` at `0x140069634`
- `FLTMGR!FltTagFileEx` at `0x140068970`
- `FLTMGR!FltTagFileEx` at `0x140068970`
- `FLTMGR!FltUntagFile` at `0x140068a1c`
- `FLTMGR!FltUntagFile` at `0x140068a1c`
- `FLTMGR!FltQueryInformationFile` at `0x140067df2`
- `FLTMGR!FltQueryInformationFile` at `0x140067df2`
- `FLTMGR!FltReleasePushLockEx` at `0x140068349`
- `FLTMGR!FltReleasePushLockEx` at `0x140069320`
- `FLTMGR!FltReleasePushLockEx` at `0x140068349`
- `FLTMGR!FltReleasePushLockEx` at `0x140069320`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x140068328`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x140068328`

## pseudocode

```c
__int64 __fastcall HsmpRpCommitNoLock(__int64 a1, __int64 a2, struct _FILE_OBJECT *a3, char a4, char a5)
{
  __int64 v5; // rbx
  __int64 v8; // r15
  unsigned __int64 RangeState; // rdi
  int v10; // eax
  PFLT_INSTANCE *v11; // rcx
  bool v12; // r13
  char v13; // r14
  __int64 v14; // rdx
  __int64 v15; // rax
  void *v16; // rax
  int v17; // r9d
  unsigned int v18; // r8d
  int v19; // r8d
  __int64 v20; // rdx
  void *v21; // rax
  int v22; // r9d
  unsigned int v23; // r8d
  int v24; // r8d
  __int64 v25; // rdx
  char v26; // bl
  char v27; // r15
  bool v28; // bl
  char v29; // r13
  char v30; // bl
  char IsBitmapCommitPending; // al
  char v32; // al
  PFILE_OBJECT v33; // r15
  unsigned int v34; // r15d
  char *v35; // r13
  void *v36; // r10
  unsigned __int64 v37; // r13
  unsigned __int16 v38; // r9
  unsigned int v39; // ecx
  int v40; // eax
  unsigned int v41; // r15d
  __int64 v42; // rax
  unsigned int v43; // r8d
  unsigned __int16 v44; // r9
  unsigned __int64 v45; // rdx
  unsigned int v46; // eax
  __int64 v47; // rcx
  unsigned int v48; // edi
  __int64 v49; // rax
  unsigned int v50; // r8d
  unsigned __int16 v51; // r9
  unsigned __int64 v52; // rdx
  unsigned int v53; // eax
  __int64 v54; // rcx
  void *v55; // r15
  unsigned __int16 v56; // cx
  _DWORD *v57; // rbx
  unsigned int *v58; // r15
  __int64 v59; // rcx
  __int64 v60; // rax
  unsigned int v61; // r9d
  int v62; // edx
  int v63; // ecx
  int v64; // r8d
  int v65; // edx
  int v66; // ecx
  int v67; // edx
  int v68; // ecx
  int v69; // edx
  int v70; // r8d
  __int64 v71; // rcx
  __int64 v72; // rax
  char *v73; // rdx
  char *v74; // rdx
  __int64 v75; // r8
  __int64 v76; // rdx
  unsigned __int16 v77; // r8
  __int64 v78; // rcx
  __int64 v79; // rax
  __int64 v80; // rdx
  __int64 LastHydrationTime; // rdx
  int v82; // r8d
  __int64 v83; // rcx
  __int64 v84; // r9
  __int64 v85; // rax
  __int64 v86; // rdx
  __int64 LastDehydrationTime; // rax
  int v88; // r8d
  __int64 v89; // r9
  __int64 v90; // rdx
  __int64 v91; // rcx
  __int64 v92; // rax
  __int64 v93; // rdx
  int LastDehydrationReason; // edx
  int v95; // r8d
  __int64 v96; // rcx
  __int64 v97; // r9
  __int64 v98; // rax
  char *v99; // rdx
  char *v100; // rdx
  __int64 v101; // rcx
  size_t v102; // r8
  __int64 v103; // rcx
  char *v104; // rcx
  unsigned int v105; // r8d
  unsigned int v106; // edx
  int v107; // r8d
  PDEVICE_OBJECT v108; // rcx
  __int64 v109; // rdx
  __int64 v110; // rax
  int v111; // eax
  __int64 v112; // rcx
  __int64 v113; // rcx
  char *v114; // rcx
  __int64 v115; // rax
  unsigned int v116; // r8d
  unsigned __int16 v117; // r9
  unsigned __int64 v118; // rdx
  unsigned int v119; // eax
  int v120; // eax
  void *v121; // r9
  void *v122; // r9
  PVOID v123; // rax
  struct _FILE_OBJECT *v125; // rdi
  ULONG v126; // r13d
  unsigned int v127; // eax
  __int64 v128; // rdx
  __int64 v129; // r8
  __int64 v130; // rbx
  PFILE_OBJECT v131; // r15
  __int64 v132; // r13
  int v133; // eax
  PDEVICE_OBJECT v134; // rcx
  __int64 v135; // rdx
  int v136; // ecx
  __int64 v137; // rax
  int v138; // ecx
  int v139; // edx
  int v140; // ecx
  int v141; // edx
  __int64 v142; // rax
  __int64 v143; // rcx
  size_t v144; // r8
  __int64 v145; // rcx
  char *v146; // rcx
  __int64 v147; // rcx
  size_t v148; // r8
  __int64 v149; // rcx
  char *v150; // rcx
  PDEVICE_OBJECT v151; // rcx
  __int64 v152; // rdx
  __int64 StreamSize; // rax
  __int64 v154; // r8
  __int64 v155; // rdx
  __int64 *v156; // rcx
  __int64 v157; // rax
  __int64 v158; // rdi
  unsigned __int64 v159; // rdx
  unsigned int v160; // eax
  unsigned int v161; // ecx
  unsigned int v162; // edx
  __int64 v163; // rdx
  __int64 v164; // r8
  int LengthReturned; // [rsp+28h] [rbp-B9h]
  char *DataBuffer; // [rsp+50h] [rbp-91h]
  char v167; // [rsp+58h] [rbp-89h]
  char v168; // [rsp+58h] [rbp-89h]
  char v169; // [rsp+59h] [rbp-88h]
  char v170; // [rsp+59h] [rbp-88h]
  char v171; // [rsp+5Ah] [rbp-87h]
  USHORT DataBufferLength[2]; // [rsp+5Ch] [rbp-85h] BYREF
  __int64 v174; // [rsp+60h] [rbp-81h]
  char v175[4]; // [rsp+68h] [rbp-79h] BYREF
  int v176; // [rsp+6Ch] [rbp-75h] BYREF
  PFLT_INSTANCE *v177; // [rsp+70h] [rbp-71h]
  PFILE_OBJECT FileObject; // [rsp+78h] [rbp-69h]
  void *v179; // [rsp+80h] [rbp-61h] BYREF
  PVOID P; // [rsp+88h] [rbp-59h]
  void *Src; // [rsp+90h] [rbp-51h] BYREF
  unsigned int v182; // [rsp+98h] [rbp-49h]
  unsigned int v183; // [rsp+9Ch] [rbp-45h]
  int v184; // [rsp+A0h] [rbp-41h]
  unsigned int v185; // [rsp+A4h] [rbp-3Dh] BYREF
  unsigned int v186; // [rsp+A8h] [rbp-39h] BYREF
  void *v187; // [rsp+B0h] [rbp-31h]
  __int64 v188; // [rsp+B8h] [rbp-29h]
  void *v189; // [rsp+C0h] [rbp-21h] BYREF
  void *v190; // [rsp+C8h] [rbp-19h] BYREF
  void *v191; // [rsp+D0h] [rbp-11h] BYREF
  __int128 FileInformation; // [rsp+D8h] [rbp-9h] BYREF
  __int64 v193; // [rsp+E8h] [rbp+7h]

  v5 = *(_QWORD *)(a2 + 16);
  v188 = a1;
  P = 0;
  v8 = *(_QWORD *)(v5 + 32);
  v179 = 0;
  DataBuffer = 0;
  v189 = 0;
  v182 = 0;
  v185 = 0;
  v190 = 0;
  v183 = 0;
  v186 = 0;
  v191 = 0;
  v184 = 0;
  v176 = 0;
  v167 = 0;
  v175[0] = 0;
  FileInformation = 0;
  v193 = 0;
  FileObject = a3;
  v174 = v5;
  RangeState = (unsigned int)HsmpValidateStreamContextNoLock(a2, a3);
  HsmDbgBreakOnStatus(RangeState);
  if ( (RangeState & 0x80000000) != 0LL )
    goto LABEL_216;
  v10 = *(_DWORD *)(a2 + 28);
  v11 = (PFLT_INSTANCE *)(a1 + 32);
  v177 = (PFLT_INSTANCE *)(a1 + 32);
  v12 = 0;
  v169 = 0;
  v171 = 0;
  v13 = 1;
  if ( (v10 & 2) != 0 )
    goto LABEL_13;
  RangeState = (unsigned int)FltQueryInformationFile(
                               *v11,
                               FileObject,
                               &FileInformation,
                               0x18u,
                               FileStandardInformation,
                               0);
  HsmDbgBreakOnStatus(RangeState);
  if ( (RangeState & 0x80000000) != 0LL )
  {
    v151 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      goto LABEL_161;
    }
    v152 = 32;
    goto LABEL_282;
  }
  v14 = *((_QWORD *)&FileInformation + 1);
  if ( (*(_DWORD *)(a2 + 28) & 4) != 0 || (v15 = HsmpGetStreamSize(a2), v14 < v15) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      StreamSize = HsmpGetStreamSize(a2);
      WPP_SF_qiqii(*(_QWORD *)(v154 + 24), v155, v154, a2, *(_QWORD *)(v5 + 32), FileObject, v155, StreamSize);
      v14 = *((_QWORD *)&FileInformation + 1);
    }
    v156 = *(__int64 **)(a2 + 160);
    v157 = *v156;
    if ( *v156 >= v14 )
      v157 = v14;
    *v156 = v157;
  }
  RangeState = (unsigned int)HsmiCompactBitmapNoLock(a2, 16964, v175);
  HsmDbgBreakOnStatus(RangeState);
  if ( (RangeState & 0x80000000) != 0LL )
  {
    v151 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      v152 = 34;
LABEL_282:
      WPP_SF_qqd(v151->AttachedDevice, v152, WPP_1b967c8d739c32210f02f2d42c5aa5c3_Traceguids, a2, v8, RangeState);
LABEL_161:
      v55 = DataBuffer;
      goto LABEL_162;
    }
LABEL_408:
    v55 = 0;
    goto LABEL_162;
  }
  LODWORD(RangeState) = 0;
  v16 = (void *)HsmpGetStreamSize(a2);
  v18 = *(_DWORD *)(a2 + 28);
  Src = v16;
  v19 = (v18 >> 8) & 1;
  v20 = *(_QWORD *)(*(_QWORD *)(a2 + 160) + 64LL);
  if ( v20 )
  {
    if ( (__int64)v16 > 0 )
    {
      *(_DWORD *)DataBufferLength = v17;
      RangeState = (unsigned int)HsmpBitmapGetRangeState(v20, v20, &Src, DataBufferLength);
      HsmDbgBreakOnStatus(RangeState);
      if ( (RangeState & 0x80000000) != 0LL || *(_DWORD *)DataBufferLength == 2 )
        goto LABEL_8;
      v19 = *(_DWORD *)DataBufferLength == 1;
    }
    v138 = (*(_DWORD *)(a2 + 28) >> 8) & 1;
    v12 = v138 != v19;
    v139 = *(_DWORD *)(a2 + 28) ^ ((unsigned __int16)*(_DWORD *)(a2 + 28) ^ (unsigned __int16)((_WORD)v19 << 8)) & 0x100;
    *(_DWORD *)(a2 + 28) = v139;
    if ( v138 != v19 )
      *(_DWORD *)(a2 + 28) = v139 | 0x200;
    HsmiDeleteExternalBitmap(a2, 16982);
    HsmiReleaseBitmap(a2, 16982);
  }
LABEL_8:
  HsmDbgBreakOnStatus((unsigned int)RangeState);
  if ( (RangeState & 0x80000000) != 0LL )
  {
    v151 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      v152 = 35;
      goto LABEL_282;
    }
    goto LABEL_408;
  }
  LODWORD(RangeState) = 0;
  v21 = (void *)HsmpGetStreamSize(a2);
  v23 = *(_DWORD *)(a2 + 28);
  Src = v21;
  v24 = (v23 >> 10) & 1;
  v25 = *(_QWORD *)(*(_QWORD *)(a2 + 160) + 72LL);
  if ( !v25 )
    goto LABEL_10;
  if ( (__int64)v21 > 0 )
  {
    *(_DWORD *)DataBufferLength = v22;
    RangeState = (unsigned int)HsmpBitmapGetRangeState(v25, v25, &Src, DataBufferLength);
    HsmDbgBreakOnStatus(RangeState);
    if ( (RangeState & 0x80000000) != 0LL || *(_DWORD *)DataBufferLength == 2 )
      goto LABEL_10;
    v24 = *(_DWORD *)DataBufferLength == 1;
  }
  v140 = (*(_DWORD *)(a2 + 28) >> 10) & 1;
  v171 = v140 != v24;
  v141 = *(_DWORD *)(a2 + 28) ^ ((unsigned __int16)*(_DWORD *)(a2 + 28) ^ (unsigned __int16)((_WORD)v24 << 10)) & 0x400;
  *(_DWORD *)(a2 + 28) = v141;
  if ( v140 != v24 )
    *(_DWORD *)(a2 + 28) = v141 | 0x800;
  HsmiDeleteExternalBitmap(a2, 16973);
  HsmiReleaseBitmap(a2, 16973);
LABEL_10:
  HsmDbgBreakOnStatus((unsigned int)RangeState);
  if ( (RangeState & 0x80000000) != 0LL )
  {
    v151 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      goto LABEL_161;
    }
    v152 = 36;
    goto LABEL_282;
  }
  v26 = v175[0] | ((*(_DWORD *)(a2 + 28) & 0x80) != 0);
  v27 = v26 | HsmiIsBitmapCommitPending(a2, 16964);
  v167 = v27;
  v28 = v12 || (*(_DWORD *)(a2 + 28) & 0x200) != 0;
  v29 = v28 | HsmiIsBitmapCommitPending(a2, 16982);
  v169 = v29;
  v30 = v171 | ((*(_DWORD *)(a2 + 28) & 0x800) != 0);
  IsBitmapCommitPending = HsmiIsBitmapCommitPending(a2, 16973);
  v11 = v177;
  v32 = v30 | IsBitmapCommitPending;
  v171 = v32;
  if ( a5 && !v27 && !v29 && !v32 )
  {
LABEL_216:
    v55 = 0;
    goto LABEL_162;
  }
  v5 = v174;
LABEL_13:
  v33 = FileObject;
  RangeState = (unsigned int)HsmpRpReadBuffer(*v11, FileObject, (UCHAR **)&v179);
  HsmDbgBreakOnStatus(RangeState);
  if ( (_DWORD)RangeState == -1073741195 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_qqqd(
        WPP_GLOBAL_Control->AttachedDevice,
        37,
        WPP_1b967c8d739c32210f02f2d42c5aa5c3_Traceguids,
        a2,
        *(_QWORD *)(v5 + 32),
        v33,
        -1073741195);
    }
    LODWORD(RangeState) = 0;
    P = v179;
    v55 = 0;
    goto LABEL_162;
  }
  if ( (RangeState & 0x80000000) != 0LL )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_qqqd(
        WPP_GLOBAL_Control->AttachedDevice,
        38,
        WPP_1b967c8d739c32210f02f2d42c5aa5c3_Traceguids,
        a2,
        *(_QWORD *)(v5 + 32),
        v33,
        RangeState);
    }
    P = v179;
    goto LABEL_161;
  }
  P = v179;
  if ( (*(_DWORD *)v179 & 0xFFFF0FFF) != dword_140029670 )
  {
    LODWORD(RangeState) = -1073688821;
    HsmDbgBreakOnStatus(3221278475LL);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_qiqDDd(
        WPP_GLOBAL_Control->AttachedDevice,
        v163,
        v164,
        a2,
        *(_QWORD *)(v5 + 32),
        v33,
        dword_140029670,
        *(_DWORD *)P);
    }
    goto LABEL_161;
  }
  v34 = *((unsigned __int16 *)v179 + 2);
  v35 = (char *)v179 + 8;
  RangeState = (unsigned int)HsmpRpValidateBuffer((char *)v179 + 8, *((unsigned __int16 *)v179 + 2));
  HsmDbgBreakOnStatus(RangeState);
  v36 = 0;
  if ( (RangeState & 0x80000000) != 0LL )
  {
    HsmDbgBreakOnCorruption();
    if ( a4 == (_BYTE)v36 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_qqqd(
          WPP_GLOBAL_Control->AttachedDevice,
          40,
          WPP_1b967c8d739c32210f02f2d42c5aa5c3_Traceguids,
          a2,
          *(_QWORD *)(v5 + 32),
          FileObject,
          RangeState);
        goto LABEL_161;
      }
      goto LABEL_234;
    }
    v37 = (unsigned int)v36;
    v38 = (_WORD)v36 + 4;
    goto LABEL_19;
  }
  v37 = (unsigned __int64)(v35 + 4);
  v39 = v34 - 4;
  v38 = 4;
  if ( v34 <= 4 )
LABEL_19:
    v39 = (unsigned int)v36;
  v40 = *(_DWORD *)(a2 + 28);
  *(_DWORD *)DataBufferLength = v39;
  v179 = v36;
  v187 = v36;
  Src = v36;
  if ( (v40 & 2) == 0 )
  {
    v41 = -1073741275;
    if ( v167 == (_BYTE)v36 )
    {
      if ( v37 )
      {
        if ( v39 < 0x18
          || (v42 = *(unsigned __int16 *)(v37 + 14), v38 >= (unsigned __int16)v42)
          || (v43 = *(_DWORD *)(v37 + 8), v43 < 0x38)
          || (v44 = *(_WORD *)(v37 + 48), v44 >= 0x12u)
          || (v45 = *(unsigned int *)(v37 + 52), (_DWORD)v45) && (v45 < 8 * v42 + 16 || (unsigned int)v45 > v43)
          || (v46 = *(unsigned __int16 *)(v37 + 50), v46 > v43)
          || v46 + (unsigned int)v45 > v43
          || v44 != 17
          || v46 + (unsigned int)v45 < (unsigned int)v45 )
        {
          v47 = 3221226021LL;
        }
        else
        {
          if ( (_DWORD)v45 && (_WORD)v46 )
            v179 = (void *)(v45 + v37);
          else
            v179 = v36;
          v182 = v46;
          v47 = (unsigned int)v36;
        }
        HsmDbgBreakOnStatus(v47);
        v36 = 0;
      }
    }
    else
    {
      RangeState = (unsigned int)HsmiPrepareBitmapCommit(a2, 16964, &v189, &v185);
      HsmDbgBreakOnStatus(RangeState);
      v36 = 0;
      if ( (RangeState & 0x80000000) != 0LL )
      {
        v108 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          v109 = 41;
          goto LABEL_283;
        }
        goto LABEL_234;
      }
      v179 = v189;
      v182 = v185;
    }
    if ( v169 == (_BYTE)v36 )
    {
      if ( v37 )
      {
        v48 = *(_DWORD *)DataBufferLength;
        if ( *(_DWORD *)DataBufferLength < 0x18u
          || (v49 = *(unsigned __int16 *)(v37 + 14), (unsigned __int16)v49 <= 5u)
          || (v50 = *(_DWORD *)(v37 + 8), v50 < 0x40)
          || (v51 = *(_WORD *)(v37 + 56), v51 >= 0x12u)
          || (v52 = *(unsigned int *)(v37 + 60), (_DWORD)v52) && (v52 < 8 * v49 + 16 || (unsigned int)v52 > v50)
          || (v53 = *(unsigned __int16 *)(v37 + 58), v53 > v50)
          || v53 + (unsigned int)v52 > v50
          || v51 != 17
          || v53 + (unsigned int)v52 < (unsigned int)v52 )
        {
          v54 = 3221226021LL;
        }
        else
        {
          if ( (_DWORD)v52 && (_WORD)v53 )
            v187 = (void *)(v37 + v52);
          else
            v187 = v36;
          v183 = v53;
          v54 = (unsigned int)v36;
        }
        HsmDbgBreakOnStatus(v54);
        v36 = 0;
        goto LABEL_143;
      }
LABEL_142:
      v48 = *(_DWORD *)DataBufferLength;
LABEL_143:
      if ( v171 == (_BYTE)v36 )
      {
        if ( v37 )
        {
          if ( v48 >= 0x18 )
          {
            v115 = *(unsigned __int16 *)(v37 + 14);
            if ( (unsigned __int16)v115 > 6u )
            {
              v116 = *(_DWORD *)(v37 + 8);
              if ( v116 >= 0x48 )
              {
                v117 = *(_WORD *)(v37 + 64);
                if ( v117 < 0x12u )
                {
                  v118 = *(unsigned int *)(v37 + 68);
                  if ( !(_DWORD)v118 || v118 >= 8 * v115 + 16 && (unsigned int)v118 <= v116 )
                  {
                    v119 = *(unsigned __int16 *)(v37 + 66);
                    if ( v119 <= v116
                      && v119 + (unsigned int)v118 <= v116
                      && v119 + (unsigned int)v118 >= (unsigned int)v118
                      && v117 == 17 )
                    {
                      if ( (_DWORD)v118 && (_WORD)v119 )
                        Src = (void *)(v118 + v37);
                      else
                        Src = v36;
                      v184 = v119;
                      v41 = (unsigned int)v36;
                    }
                  }
                }
              }
            }
          }
          HsmDbgBreakOnStatus(v41);
        }
        goto LABEL_51;
      }
      RangeState = (unsigned int)HsmiPrepareBitmapCommit(a2, 16973, &v191, &v176);
      HsmDbgBreakOnStatus(RangeState);
      if ( (RangeState & 0x80000000) == 0LL )
      {
        Src = v191;
        v184 = v176;
        goto LABEL_51;
      }
      v108 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_161;
      }
      v109 = 43;
LABEL_283:
      v110 = *(_QWORD *)(v5 + 32);
      goto LABEL_284;
    }
    RangeState = (unsigned int)HsmiPrepareBitmapCommit(a2, 16982, &v190, &v186);
    HsmDbgBreakOnStatus(RangeState);
    v36 = 0;
    if ( (RangeState & 0x80000000) == 0LL )
    {
      v187 = v190;
      v183 = v186;
      goto LABEL_142;
    }
    v108 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      v109 = 42;
      goto LABEL_283;
    }
LABEL_234:
    v55 = v36;
    goto LABEL_162;
  }
LABEL_51:
  DataBuffer = (char *)ExAllocatePool2(256, 0x4000, 1884451656);
  v55 = DataBuffer;
  if ( DataBuffer )
  {
    v176 = 10;
    v56 = 10;
    v57 = DataBuffer + 4;
    if ( v37 )
    {
      v56 = *(_WORD *)(v37 + 14);
      if ( v56 <= 0xAu )
        v56 = 10;
    }
    *((_DWORD *)DataBuffer + 2) = 0;
    RangeState = (unsigned __int64)(DataBuffer + 20);
    v58 = (unsigned int *)(DataBuffer + 12);
    *((_WORD *)DataBuffer + 9) = v56;
    *v57 = 1884448070;
    *((_DWORD *)DataBuffer + 3) = 8 * v56 + 16;
    *((_WORD *)DataBuffer + 8) = 0;
    memset(DataBuffer + 20, 0, 8LL * v56);
    if ( *((_WORD *)DataBuffer + 9) )
    {
      v59 = *v58;
      if ( ((v59 + 3) & 0xFFFFFFFFFFFFFFFCuLL) + 1 > 0x3FFC )
      {
        LODWORD(RangeState) = -1073741789;
      }
      else
      {
        v60 = ((_DWORD)v59 + 3) & 0xFFFFFFFC;
        *v58 = v60;
        if ( *(_WORD *)RangeState )
          *((_WORD *)DataBuffer + 8) |= 1u;
        *(_WORD *)RangeState = 7;
        LODWORD(RangeState) = 0;
        *((_WORD *)DataBuffer + 11) = 1;
        *((_DWORD *)DataBuffer + 6) = v60;
        *((_BYTE *)v57 + v60) = 1;
        ++*v58;
      }
    }
    else
    {
      LODWORD(RangeState) = -1073741811;
    }
    HsmDbgBreakOnStatus((unsigned int)RangeState);
    if ( (RangeState & 0x80000000) != 0LL )
    {
      v108 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_161;
      }
      v109 = 45;
    }
    else
    {
      v61 = *(_DWORD *)(a2 + 28);
      v62 = (v61 >> 5) & 1 | 2;
      if ( (v61 & 0x40) == 0 )
        v62 = (*(_DWORD *)(a2 + 28) >> 5) & 1;
      v63 = v62 | 4;
      if ( (v61 & 0x100) == 0 )
        v63 = v62;
      v64 = v63 | 8;
      if ( (v61 & 0x400) == 0 )
        v64 = v63;
      v65 = v64 | 0x20;
      if ( (v61 & 0x1000) == 0 )
        v65 = v64;
      v66 = v65 | 0x10;
      if ( (v61 & 2) == 0 )
        v66 = v65;
      v67 = v66 | 0x40;
      if ( (v61 & 0x2000) == 0 )
        v67 = v66;
      v68 = v67 | 0x80;
      if ( (v61 & 0x4000) == 0 )
        v68 = v67;
      v69 = v68 | 0x100;
      if ( (v61 & 0x8000) == 0 )
        v69 = v68;
      v70 = v69 | 0x200;
      if ( (v61 & 0x10000) == 0 )
        v70 = v69;
      if ( *((_WORD *)DataBuffer + 9) <= 1u )
      {
        LODWORD(RangeState) = -1073741811;
      }
      else
      {
        v71 = *v58;
        if ( ((v71 + 3) & 0xFFFFFFFFFFFFFFFCuLL) + 4 > 0x3FFC )
        {
          LODWORD(RangeState) = -1073741789;
        }
        else
        {
          v72 = ((_DWORD)v71 + 3) & 0xFFFFFFFC;
          *v58 = v72;
          if ( *((_WORD *)DataBuffer + 14) )
            *((_WORD *)DataBuffer + 8) |= 1u;
          *((_DWORD *)DataBuffer + 7) = 262154;
          *((_DWORD *)DataBuffer + 8) = v72;
          *(_DWORD *)((char *)v57 + v72) = v70;
          *v58 += 4;
          LODWORD(RangeState) = 0;
        }
      }
      HsmDbgBreakOnStatus((unsigned int)RangeState);
      if ( (RangeState & 0x80000000) != 0LL )
      {
        v108 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          goto LABEL_161;
        }
        v109 = 46;
      }
      else
      {
        FltAcquirePushLockExclusiveEx(a2 + 64, 0);
        v73 = *(char **)(a2 + 48);
        LODWORD(RangeState) = 0;
        if ( v73 )
        {
          v111 = *(_DWORD *)(a2 + 56);
          if ( v111 )
          {
            if ( *((_WORD *)DataBuffer + 9) <= 3u )
            {
              LODWORD(RangeState) = -1073741811;
            }
            else
            {
              v112 = *v58;
              if ( (unsigned __int16)v111 + ((v112 + 3) & 0xFFFFFFFFFFFFFFFCuLL) > 0x3FFC )
              {
                LODWORD(RangeState) = -1073741789;
              }
              else
              {
                if ( *((_WORD *)DataBuffer + 22) )
                  *((_WORD *)DataBuffer + 8) |= 1u;
                v113 = ((_DWORD)v112 + 3) & 0xFFFFFFFC;
                *v58 = v113;
                *((_DWORD *)DataBuffer + 12) = v113;
                v114 = (char *)v57 + v113;
                *((_WORD *)DataBuffer + 22) = 17;
                *((_WORD *)DataBuffer + 23) = v111;
                if ( v114 != v73 )
                  memmove(v114, v73, (unsigned __int16)v111);
                *v58 += *((unsigned __int16 *)DataBuffer + 23);
              }
            }
            HsmDbgBreakOnStatus((unsigned int)RangeState);
            if ( (RangeState & 0x80000000) != 0LL )
            {
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
              {
                WPP_SF_qqd(
                  WPP_GLOBAL_Control->AttachedDevice,
                  47,
                  WPP_1b967c8d739c32210f02f2d42c5aa5c3_Traceguids,
                  a2,
                  *(_QWORD *)(v174 + 32),
                  RangeState);
              }
              FltReleasePushLockEx(a2 + 64, 0);
              goto LABEL_161;
            }
            LODWORD(RangeState) = 0;
          }
        }
        FltReleasePushLockEx(a2 + 64, 0);
        v75 = 2;
        if ( (*(_DWORD *)(a2 + 28) & 2) != 0 )
        {
LABEL_120:
          if ( v37 )
          {
            LOWORD(v136) = 10;
            if ( *(_WORD *)(v37 + 14) > 0xAu )
            {
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
              {
                WPP_SF_qiq(WPP_GLOBAL_Control->AttachedDevice, v74, v75, a2, *(_QWORD *)(v174 + 32), FileObject);
              }
              LOWORD(v136) = 10;
            }
            while ( 1 )
            {
              v137 = *(unsigned __int16 *)(v37 + 14);
              if ( (unsigned __int16)v136 >= (unsigned __int16)v137 )
                break;
              v158 = (unsigned __int16)v136;
              v159 = *(unsigned int *)(v37 + 8LL * (unsigned __int16)v136 + 20);
              if ( (_DWORD)v159 && v159 < 8 * v137 + 16
                || (v160 = *(_DWORD *)(v37 + 8), (unsigned int)v159 > v160)
                || (v161 = *(unsigned __int16 *)(v37 + 8LL * (unsigned __int16)v136 + 18), v161 > v160)
                || v161 + (unsigned int)v159 < (unsigned int)v159
                || v161 + (unsigned int)v159 > v160 )
              {
                LODWORD(RangeState) = -1073688830;
                HsmDbgBreakOnStatus(3221278466LL);
                v108 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
                  && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                {
                  v109 = 56;
                  goto LABEL_129;
                }
                goto LABEL_161;
              }
              v162 = *v58 + v161;
              if ( v162 < *v58 || v162 > 0x3FFC )
              {
                LODWORD(RangeState) = -1073688829;
                HsmDbgBreakOnStatus(3221278467LL);
                v108 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
                  && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                {
                  v109 = 57;
                  goto LABEL_129;
                }
                goto LABEL_161;
              }
              *(_QWORD *)&v57[2 * v158 + 4] = *(_QWORD *)(v37 + 8 * v158 + 16);
              memmove(
                (char *)v57 + *v58,
                (const void *)(v37 + *(unsigned int *)(v37 + 8 * v158 + 20)),
                *(unsigned __int16 *)(v37 + 8 * v158 + 18));
              v136 = v176;
              v57[2 * v158 + 5] = *v58;
              *v58 += HIWORD(v57[2 * v158 + 4]);
              LOWORD(v136) = v136 + 1;
              v176 = v136;
            }
          }
          v105 = *v58;
          *((_WORD *)DataBuffer + 8) |= 2u;
          v170 = 0;
          *((_DWORD *)DataBuffer + 2) = RtlComputeCrc32(0, (PUCHAR)DataBuffer + 12, v105 - 8);
          v106 = *(_DWORD *)DataBuffer & 0xFFFFFFF0 | 1;
          *(_DWORD *)DataBuffer = v106;
          v107 = (unsigned __int16)(*(_WORD *)v58 + 4);
          *(_DWORD *)DataBufferLength = v107;
          *(_DWORD *)DataBuffer = (unsigned __int16)v106 | (v107 << 16);
          v176 = v107;
          if ( (_Config & 2) != 0 )
          {
            HsmiRpCompressBuffer((UCHAR *)DataBuffer, &v176);
            *(_DWORD *)DataBufferLength = v176;
          }
          if ( (*(_DWORD *)(a2 + 28) & 0x100) == 0 )
          {
            v170 = 1;
            RangeState = (unsigned int)HsmpToggleFileAttributesNotify(
                                         v188,
                                         (_DWORD)FileObject,
                                         a4 != 0 ? 8 : 0,
                                         4198400,
                                         0);
            HsmDbgBreakOnStatus(RangeState);
            if ( (RangeState & 0x80000000) != 0LL )
            {
              v108 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
                || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
              {
                goto LABEL_161;
              }
              v109 = 58;
              goto LABEL_129;
            }
          }
          v168 = 0;
          v125 = FileObject;
          if ( !FileObject->WriteAccess )
          {
            FileObject->WriteAccess = 1;
            v168 = 1;
          }
          v126 = dword_140029670
               | *(_DWORD *)(a2 + 28) & 0x1000
               | (2 * (*(_DWORD *)(a2 + 28) & 0x6000 | ((*(_DWORD *)(a2 + 28) & 0x40) << 6)));
          if ( *(_DWORD *)(v188 + 80) == 28
            && (unsigned int)Feature_ReFS_OneDrive_Support__private_IsEnabledDeviceUsageNoInline() )
          {
            RangeState = (unsigned int)FltUntagFile(*v177, v125, *(_DWORD *)P, 0);
            HsmDbgBreakOnStatus(RangeState);
            if ( (RangeState & 0x80000000) != 0LL )
            {
              v134 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
                || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
              {
                goto LABEL_159;
              }
              v135 = 59;
              goto LABEL_239;
            }
            v127 = FltTagFile(*v177, FileObject, v126, 0, DataBuffer, DataBufferLength[0]);
          }
          else
          {
            LOWORD(LengthReturned) = DataBufferLength[0];
            v127 = FltTagFileEx(*v177, v125, v126, 0, DataBuffer, LengthReturned, *(_DWORD *)P, 0, 0);
          }
          LODWORD(RangeState) = v127;
          HsmDbgBreakOnStatus(v127);
          if ( (RangeState & 0x80000000) == 0LL )
          {
            *(_DWORD *)(a2 + 24) = v126;
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
            {
              v130 = v174;
              WPP_SF_qLiqDD(
                WPP_GLOBAL_Control->AttachedDevice,
                v128,
                v129,
                a2,
                *(_DWORD *)(a2 + 28),
                *(_QWORD *)(v174 + 32),
                DataBuffer + 4,
                *v58,
                *(_DWORD *)DataBufferLength);
            }
            else
            {
              v130 = v174;
            }
            v131 = FileObject;
            v132 = v188;
            if ( v170
              || (RangeState = (unsigned int)HsmpToggleFileAttributesNotify(
                                               v188,
                                               (_DWORD)FileObject,
                                               a4 != 0 ? 8 : 0,
                                               0,
                                               4198400),
                  HsmDbgBreakOnStatus(RangeState),
                  (RangeState & 0x80000000) == 0LL) )
            {
              v133 = *(_DWORD *)(a2 + 28);
              if ( (v133 & 2) == 0 )
              {
                if ( (v133 & 0x20) == 0 && (v133 & 0x100) != 0 )
                  v13 = 0;
                LOBYTE(v129) = v13;
                HsmpToggleFileSparseAttribute(v132, v131, v129);
              }
              v120 = *(_DWORD *)(a2 + 28);
              if ( (v120 & 4) != 0 )
                *(_DWORD *)(a2 + 28) = v120 & 0xFFFFFFE3;
              goto LABEL_159;
            }
            v134 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
            {
              v142 = *(_QWORD *)(v130 + 32);
              v135 = 62;
              goto LABEL_244;
            }
LABEL_159:
            if ( v168 )
              FileObject->WriteAccess = 0;
            goto LABEL_161;
          }
          v134 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
            || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
          {
            goto LABEL_159;
          }
          v135 = 60;
LABEL_239:
          v142 = *(_QWORD *)(v174 + 32);
LABEL_244:
          WPP_SF_qqd(v134->AttachedDevice, v135, WPP_1b967c8d739c32210f02f2d42c5aa5c3_Traceguids, a2, v142, RangeState);
          goto LABEL_159;
        }
        v76 = HsmpGetStreamSize(a2);
        if ( v77 >= *((_WORD *)DataBuffer + 9) )
        {
          LODWORD(RangeState) = -1073741811;
        }
        else
        {
          v78 = *v58;
          if ( ((v78 + 3) & 0xFFFFFFFFFFFFFFFCuLL) + 8 > 0x3FFC )
          {
            LODWORD(RangeState) = -1073741789;
          }
          else
          {
            v79 = ((_DWORD)v78 + 3) & 0xFFFFFFFC;
            *v58 = v79;
            if ( *((_WORD *)DataBuffer + 18) )
              *((_WORD *)DataBuffer + 8) |= 1u;
            *((_DWORD *)DataBuffer + 9) = 524294;
            *((_DWORD *)DataBuffer + 10) = v79;
            *(_QWORD *)((char *)v57 + v79) = v76;
            *v58 += 8;
          }
        }
        HsmDbgBreakOnStatus((unsigned int)RangeState);
        if ( (RangeState & 0x80000000) != 0LL )
        {
          v108 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
            || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
          {
            goto LABEL_161;
          }
          v109 = 48;
        }
        else
        {
          LastHydrationTime = HsmpGetLastHydrationTime(a2, v80, 0);
          if ( (unsigned __int16)(v82 + 7) >= *((_WORD *)DataBuffer + 9) )
          {
            LODWORD(RangeState) = -1073741811;
          }
          else
          {
            v83 = *v58;
            v84 = (unsigned int)(v82 + 8);
            if ( v84 + ((v83 + 3) & 0xFFFFFFFFFFFFFFFCuLL) > 0x3FFC )
            {
              LODWORD(RangeState) = -1073741789;
            }
            else
            {
              v85 = ((_DWORD)v83 + 3) & 0xFFFFFFFC;
              *v58 = v85;
              if ( *((_WORD *)DataBuffer + 38) != (_WORD)v82 )
                *((_WORD *)DataBuffer + 8) |= 1u;
              *((_DWORD *)DataBuffer + 19) = 524294;
              LODWORD(RangeState) = v82;
              *((_DWORD *)DataBuffer + 20) = v85;
              *(_QWORD *)((char *)v57 + v85) = LastHydrationTime;
              *v58 += v84;
            }
          }
          HsmDbgBreakOnStatus((unsigned int)RangeState);
          if ( (RangeState & 0x80000000) != 0LL )
          {
            v108 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
              || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
            {
              goto LABEL_161;
            }
            v109 = 49;
          }
          else
          {
            LastDehydrationTime = HsmpGetLastDehydrationTime(a2, v86, 0);
            v89 = (unsigned int)(v88 + 8);
            v90 = LastDehydrationTime;
            if ( (unsigned __int16)(v88 + 8) >= *((_WORD *)DataBuffer + 9) )
            {
              LODWORD(RangeState) = -1073741811;
            }
            else
            {
              v91 = *v58;
              if ( v89 + ((v91 + 3) & 0xFFFFFFFFFFFFFFFCuLL) > 0x3FFC )
              {
                LODWORD(RangeState) = -1073741789;
              }
              else
              {
                v92 = ((_DWORD)v91 + 3) & 0xFFFFFFFC;
                *v58 = v92;
                if ( *((_WORD *)DataBuffer + 42) != (_WORD)v88 )
                  *((_WORD *)DataBuffer + 8) |= 1u;
                *((_DWORD *)DataBuffer + 21) = 524294;
                LODWORD(RangeState) = v88;
                *((_DWORD *)DataBuffer + 22) = v92;
                *(_QWORD *)((char *)v57 + v92) = v90;
                *v58 += v89;
              }
            }
            HsmDbgBreakOnStatus((unsigned int)RangeState);
            if ( (RangeState & 0x80000000) != 0LL )
            {
              v108 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
                || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
              {
                goto LABEL_161;
              }
              v109 = 50;
            }
            else
            {
              LastDehydrationReason = HsmpGetLastDehydrationReason(a2, v93, 0);
              if ( (unsigned __int16)(v95 + 9) >= *((_WORD *)DataBuffer + 9) )
              {
                LODWORD(RangeState) = -1073741811;
              }
              else
              {
                v96 = *v58;
                v97 = (unsigned int)(v95 + 4);
                if ( v97 + ((v96 + 3) & 0xFFFFFFFFFFFFFFFCuLL) > 0x3FFC )
                {
                  LODWORD(RangeState) = -1073741789;
                }
                else
                {
                  v98 = ((_DWORD)v96 + 3) & 0xFFFFFFFC;
                  *v58 = v98;
                  if ( *((_WORD *)DataBuffer + 46) != (_WORD)v95 )
                    *((_WORD *)DataBuffer + 8) |= 1u;
                  *((_DWORD *)DataBuffer + 23) = 262154;
                  LODWORD(RangeState) = v95;
                  *((_DWORD *)DataBuffer + 24) = v98;
                  *(_DWORD *)((char *)v57 + v98) = LastDehydrationReason;
                  *v58 += v97;
                }
              }
              HsmDbgBreakOnStatus((unsigned int)RangeState);
              if ( (RangeState & 0x80000000) != 0LL )
              {
                v108 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
                  || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
                {
                  goto LABEL_161;
                }
                v109 = 51;
              }
              else
              {
                v99 = (char *)v179;
                LODWORD(RangeState) = 0;
                if ( v179 )
                {
                  if ( *((_WORD *)DataBuffer + 9) <= 4u )
                  {
                    LODWORD(RangeState) = -1073741811;
                  }
                  else
                  {
                    v143 = *v58;
                    v144 = (unsigned __int16)v182;
                    if ( (unsigned __int16)v182 + ((v143 + 3) & 0xFFFFFFFFFFFFFFFCuLL) > 0x3FFC )
                    {
                      LODWORD(RangeState) = -1073741789;
                    }
                    else
                    {
                      if ( *((_WORD *)DataBuffer + 26) )
                        *((_WORD *)DataBuffer + 8) |= 1u;
                      v145 = ((_DWORD)v143 + 3) & 0xFFFFFFFC;
                      *v58 = v145;
                      *((_DWORD *)DataBuffer + 14) = v145;
                      v146 = (char *)v57 + v145;
                      *((_WORD *)DataBuffer + 26) = 17;
                      *((_WORD *)DataBuffer + 27) = v144;
                      if ( v146 != v99 )
                        memmove(v146, v99, v144);
                      *v58 += *((unsigned __int16 *)DataBuffer + 27);
                    }
                  }
                  HsmDbgBreakOnStatus((unsigned int)RangeState);
                  if ( (RangeState & 0x80000000) != 0LL )
                  {
                    v108 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
                      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
                    {
                      goto LABEL_161;
                    }
                    v109 = 52;
                    goto LABEL_129;
                  }
                  LODWORD(RangeState) = 0;
                }
                v100 = (char *)v187;
                if ( v187 )
                {
                  if ( *((_WORD *)DataBuffer + 9) <= 5u )
                  {
                    LODWORD(RangeState) = -1073741811;
                  }
                  else
                  {
                    v147 = *v58;
                    v148 = (unsigned __int16)v183;
                    if ( (unsigned __int16)v183 + ((v147 + 3) & 0xFFFFFFFFFFFFFFFCuLL) > 0x3FFC )
                    {
                      LODWORD(RangeState) = -1073741789;
                    }
                    else
                    {
                      if ( *((_WORD *)DataBuffer + 30) )
                        *((_WORD *)DataBuffer + 8) |= 1u;
                      v149 = ((_DWORD)v147 + 3) & 0xFFFFFFFC;
                      *v58 = v149;
                      *((_DWORD *)DataBuffer + 16) = v149;
                      v150 = (char *)v57 + v149;
                      *((_WORD *)DataBuffer + 30) = 17;
                      *((_WORD *)DataBuffer + 31) = v148;
                      if ( v150 != v100 )
                        memmove(v150, v100, v148);
                      *v58 += *((unsigned __int16 *)DataBuffer + 31);
                    }
                  }
                  HsmDbgBreakOnStatus((unsigned int)RangeState);
                  if ( (RangeState & 0x80000000) != 0LL )
                  {
                    v108 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
                      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
                    {
                      goto LABEL_161;
                    }
                    v109 = 53;
                    goto LABEL_129;
                  }
                  LODWORD(RangeState) = 0;
                }
                v74 = (char *)Src;
                if ( !Src )
                  goto LABEL_120;
                if ( *((_WORD *)DataBuffer + 9) <= 6u )
                {
                  LODWORD(RangeState) = -1073741811;
                }
                else
                {
                  v101 = *v58;
                  v102 = (unsigned __int16)v184;
                  if ( (unsigned __int16)v184 + ((v101 + 3) & 0xFFFFFFFFFFFFFFFCuLL) > 0x3FFC )
                  {
                    LODWORD(RangeState) = -1073741789;
                  }
                  else
                  {
                    if ( *((_WORD *)DataBuffer + 34) )
                      *((_WORD *)DataBuffer + 8) |= 1u;
                    v103 = ((_DWORD)v101 + 3) & 0xFFFFFFFC;
                    *v58 = v103;
                    *((_DWORD *)DataBuffer + 18) = v103;
                    v104 = (char *)v57 + v103;
                    *((_WORD *)DataBuffer + 34) = 17;
                    *((_WORD *)DataBuffer + 35) = v102;
                    if ( v104 != v74 )
                      memmove(v104, v74, v102);
                    *v58 += *((unsigned __int16 *)DataBuffer + 35);
                  }
                }
                HsmDbgBreakOnStatus((unsigned int)RangeState);
                if ( (RangeState & 0x80000000) == 0LL )
                  goto LABEL_120;
                v108 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
                  || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
                {
                  goto LABEL_161;
                }
                v109 = 54;
              }
            }
          }
        }
      }
    }
LABEL_129:
    v110 = *(_QWORD *)(v174 + 32);
LABEL_284:
    WPP_SF_qqd(v108->AttachedDevice, v109, WPP_1b967c8d739c32210f02f2d42c5aa5c3_Traceguids, a2, v110, RangeState);
    goto LABEL_161;
  }
  LODWORD(RangeState) = -1073741670;
  HsmDbgBreakOnStatus(3221225626LL);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_qqd(
      WPP_GLOBAL_Control->AttachedDevice,
      44,
      WPP_1b967c8d739c32210f02f2d42c5aa5c3_Traceguids,
      a2,
      *(_QWORD *)(v5 + 32),
      -1073741670);
  }
LABEL_162:
  HsmiCompleteBitmapCommit(a2, 16964, (unsigned int)RangeState, v189);
  v121 = v190;
  *(_DWORD *)(a2 + 28) &= ~0x80u;
  HsmiCompleteBitmapCommit(a2, 16982, (unsigned int)RangeState, v121);
  v122 = v191;
  *(_DWORD *)(a2 + 28) &= ~0x200u;
  HsmiCompleteBitmapCommit(a2, 16973, (unsigned int)RangeState, v122);
  v123 = P;
  *(_DWORD *)(a2 + 28) &= ~0x800u;
  if ( v123 )
    ExFreePoolWithTag(v123, 0x70527348u);
  if ( v55 )
    ExFreePoolWithTag(v55, 0x70527348u);
  return (unsigned int)RangeState;
}

```

## disassembly

```asm
0x140067d04  mov     [rsp-8+arg_18], rbx
0x140067d09  push    rbp
0x140067d0a  push    rsi
0x140067d0b  push    rdi
0x140067d0c  push    r12
0x140067d0e  push    r13
0x140067d10  push    r14
0x140067d12  push    r15
0x140067d14  lea     rbp, [rsp-1Fh]
0x140067d19  sub     rsp, 100h
0x140067d20  mov     rax, cs:__security_cookie
0x140067d27  xor     rax, rsp
0x140067d2a  mov     [rbp+4Fh+var_40], rax
0x140067d2e  mov     rbx, [rdx+10h]
0x140067d32  mov     r14, rcx
0x140067d35  mov     [rbp+4Fh+var_78], rcx
0x140067d39  mov     rsi, rdx
0x140067d3c  xor     ecx, ecx
0x140067d3e  mov     [rsp+130h+var_D5], r9b
0x140067d43  xorps   xmm0, xmm0
0x140067d46  mov     [rbp+4Fh+P], rcx
0x140067d4a  mov     r15, [rbx+20h]
0x140067d4e  xor     eax, eax
0x140067d50  mov     [rbp+4Fh+var_B0], rcx
0x140067d54  mov     rdx, r8
0x140067d57  mov     [rsp+130h+DataBuffer], rcx
0x140067d5c  mov     [rbp+4Fh+var_70], rcx
0x140067d60  mov     [rbp+4Fh+var_98], ecx
0x140067d63  mov     [rbp+4Fh+var_8C], ecx
0x140067d66  mov     [rbp+4Fh+var_68], rcx
0x140067d6a  mov     [rbp+4Fh+var_94], ecx
0x140067d6d  mov     [rbp+4Fh+var_88], ecx
0x140067d70  mov     [rbp+4Fh+var_60], rcx
0x140067d74  mov     [rbp+4Fh+var_90], ecx
0x140067d77  mov     [rbp+4Fh+var_C4], ecx
0x140067d7a  mov     [rsp+130h+var_D8], cl
0x140067d7e  mov     [rbp+4Fh+var_C8], cl
0x140067d81  mov     rcx, rsi
0x140067d84  movups  [rbp+4Fh+FileInformation], xmm0
0x140067d88  mov     [rbp+4Fh+var_48], rax
0x140067d8c  mov     [rbp+4Fh+FileObject], r8
0x140067d90  mov     [rsp+130h+var_D0], rbx
0x140067d95  call    HsmpValidateStreamContextNoLock
0x140067d9a  mov     ecx, eax
0x140067d9c  mov     edi, eax
0x140067d9e  call    HsmDbgBreakOnStatus
0x140067da3  xor     edx, edx
0x140067da5  test    edi, edi
0x140067da7  js      loc_140068C58
0x140067dad  mov     eax, [rsi+1Ch]
0x140067db0  lea     rcx, [r14+20h]
0x140067db4  mov     [rbp+4Fh+var_C0], rcx
0x140067db8  mov     r13b, dl
0x140067dbb  mov     [rsp+130h+var_D7], dl
0x140067dbf  lea     r12, WPP_GLOBAL_Control
0x140067dc6  mov     [rsp+130h+var_D6], dl
0x140067dca  lea     r14d, [rdx+1]
0x140067dce  test    al, 2
0x140067dd0  jnz     loc_140067F57
0x140067dd6  mov     rcx, [rcx]; Instance
0x140067dd9  lea     r9d, [rdx+18h]; Length
0x140067ddd  mov     [rsp+130h+LengthReturned], rdx; LengthReturned
0x140067de2  lea     r8, [rbp+4Fh+FileInformation]; FileInformation
0x140067de6  mov     rdx, [rbp+4Fh+FileObject]; FileObject
0x140067dea  mov     [rsp+130h+FileInformationClass], 5; FileInformationClass
0x140067df2  call    cs:__imp_FltQueryInformationFile
0x140067df9  nop     dword ptr [rax+rax+00h]
0x140067dfe  mov     ecx, eax
0x140067e00  mov     edi, eax
0x140067e02  call    HsmDbgBreakOnStatus
0x140067e07  test    edi, edi
0x140067e09  js      loc_140068F3A
0x140067e0f  mov     eax, [rsi+1Ch]
0x140067e12  mov     rdx, qword ptr [rbp+4Fh+FileInformation+8]
0x140067e16  test    al, 4
0x140067e18  jnz     loc_140068FA8
0x140067e1e  mov     rcx, rsi
0x140067e21  call    HsmpGetStreamSize
0x140067e26  cmp     rdx, rax
0x140067e29  jl      loc_140068FA8
0x140067e2f  lea     r8, [rbp+4Fh+var_C8]
0x140067e33  mov     edx, 4244h
0x140067e38  mov     rcx, rsi
0x140067e3b  call    HsmiCompactBitmapNoLock
0x140067e40  mov     ecx, eax
0x140067e42  mov     edi, eax
0x140067e44  call    HsmDbgBreakOnStatus
0x140067e49  xor     r9d, r9d
0x140067e4c  test    edi, edi
0x140067e4e  js      loc_140069011
0x140067e54  mov     rcx, rsi
0x140067e57  mov     edi, r9d
0x140067e5a  call    HsmpGetStreamSize
0x140067e5f  mov     r8d, [rsi+1Ch]
0x140067e63  mov     rcx, rax
0x140067e66  mov     [rbp+4Fh+Src], rax
0x140067e6a  mov     rax, [rsi+0A0h]
0x140067e71  shr     r8d, 8
0x140067e75  and     r8d, r14d
0x140067e78  mov     rdx, [rax+40h]
0x140067e7c  test    rdx, rdx
0x140067e7f  jnz     loc_140068AA3
0x140067e85  mov     ecx, edi
0x140067e87  call    HsmDbgBreakOnStatus
0x140067e8c  xor     r9d, r9d
0x140067e8f  test    edi, edi
0x140067e91  js      loc_140069041
0x140067e97  mov     rcx, rsi
0x140067e9a  mov     edi, r9d
0x140067e9d  call    HsmpGetStreamSize
0x140067ea2  mov     r8d, [rsi+1Ch]
0x140067ea6  mov     rcx, rax
0x140067ea9  mov     [rbp+4Fh+Src], rax
0x140067ead  mov     rax, [rsi+0A0h]
0x140067eb4  shr     r8d, 0Ah
0x140067eb8  and     r8d, r14d
0x140067ebb  mov     rdx, [rax+48h]
0x140067ebf  test    rdx, rdx
0x140067ec2  jnz     loc_140068B37
0x140067ec8  mov     ecx, edi
0x140067eca  call    HsmDbgBreakOnStatus
0x140067ecf  test    edi, edi
0x140067ed1  js      loc_140069071
0x140067ed7  mov     ebx, [rsi+1Ch]
0x140067eda  mov     edx, 4244h
0x140067edf  shr     ebx, 7
0x140067ee2  mov     rcx, rsi
0x140067ee5  and     bl, r14b
0x140067ee8  or      bl, [rbp+4Fh+var_C8]
0x140067eeb  call    HsmiIsBitmapCommitPending
0x140067ef0  mov     r15b, al
0x140067ef3  mov     edx, 4256h
0x140067ef8  or      r15b, bl
0x140067efb  mov     rcx, rsi
0x140067efe  mov     ebx, [rsi+1Ch]
0x140067f01  shr     ebx, 9
0x140067f04  and     bl, r14b
0x140067f07  mov     [rsp+130h+var_D8], r15b
0x140067f0c  or      bl, r13b
0x140067f0f  call    HsmiIsBitmapCommitPending
0x140067f14  mov     r13b, al
0x140067f17  mov     edx, 424Dh
0x140067f1c  or      r13b, bl
0x140067f1f  mov     rcx, rsi
0x140067f22  mov     ebx, [rsi+1Ch]
0x140067f25  shr     ebx, 0Bh
0x140067f28  and     bl, r14b
0x140067f2b  mov     [rsp+130h+var_D7], r13b
0x140067f30  or      bl, [rsp+130h+var_D6]
0x140067f34  call    HsmiIsBitmapCommitPending
0x140067f39  mov     rcx, [rbp+4Fh+var_C0]
0x140067f3d  or      al, bl
0x140067f3f  xor     edx, edx
0x140067f41  mov     [rsp+130h+var_D6], al
0x140067f45  mov     [rbp+4Fh+var_C0], rcx
0x140067f49  cmp     [rbp+4Fh+arg_20], dl
0x140067f4c  jnz     loc_140068C3E
0x140067f52  mov     rbx, [rsp+130h+var_D0]
0x140067f57  mov     r15, [rbp+4Fh+FileObject]
0x140067f5b  lea     r8, [rbp+4Fh+var_B0]
0x140067f5f  mov     rcx, [rcx]; Instance
0x140067f62  mov     rdx, r15; FileObject
0x140067f65  call    HsmpRpReadBuffer
0x140067f6a  mov     ecx, eax
0x140067f6c  mov     edi, eax
0x140067f6e  call    HsmDbgBreakOnStatus
0x140067f73  mov     r8d, 0C0000275h
0x140067f79  cmp     edi, r8d
0x140067f7c  jz      loc_14006909C
0x140067f82  test    edi, edi
0x140067f84  js      loc_1400690F3
0x140067f8a  mov     rcx, [rbp+4Fh+var_B0]
0x140067f8e  mov     [rbp+4Fh+P], rcx
0x140067f92  mov     eax, [rcx]
0x140067f94  and     eax, 0FFFF0FFFh
0x140067f99  cmp     eax, cs:dword_140029670
0x140067f9f  jnz     loc_14006969C
0x140067fa5  movzx   r15d, word ptr [rcx+4]
0x140067faa  lea     r13, [rcx+8]
0x140067fae  mov     edx, r15d
0x140067fb1  mov     rcx, r13
0x140067fb4  call    HsmpRpValidateBuffer
0x140067fb9  mov     ecx, eax
0x140067fbb  mov     edi, eax
0x140067fbd  call    HsmDbgBreakOnStatus
0x140067fc2  xor     r10d, r10d
0x140067fc5  test    edi, edi
0x140067fc7  jns     loc_140068107
0x140067fcd  call    HsmDbgBreakOnCorruption
0x140067fd2  cmp     [rsp+130h+var_D5], r10b
0x140067fd7  jz      loc_140069144
0x140067fdd  mov     r13d, r10d
0x140067fe0  lea     r9d, [r10+4]
0x140067fe4  mov     ecx, r10d
0x140067fe7  mov     eax, [rsi+1Ch]
0x140067fea  mov     r11d, 11h
0x140067ff0  mov     dword ptr [rsp+130h+DataBufferLength], ecx
0x140067ff4  mov     [rbp+4Fh+var_B0], r10
0x140067ff8  mov     [rbp+4Fh+var_80], r10
0x140067ffc  mov     [rbp+4Fh+Src], r10
0x140068000  test    al, 2
0x140068002  jnz     loc_140068157
0x140068008  mov     r15d, 0C0000225h
0x14006800e  cmp     [rsp+130h+var_D8], r10b
0x140068013  jnz     loc_140068BCD
0x140068019  test    r13, r13
0x14006801c  jz      short loc_140068085
0x14006801e  cmp     ecx, 18h
0x140068021  jb      short loc_140068074
0x140068023  movzx   eax, word ptr [r13+0Eh]
0x140068028  cmp     r9w, ax
0x14006802c  jnb     short loc_140068074
0x14006802e  mov     r8d, [r13+8]
0x140068032  cmp     r8d, 38h ; '8'
0x140068036  jb      short loc_140068074
0x140068038  movzx   r9d, word ptr [r13+30h]
0x14006803d  cmp     r9w, 12h
0x140068042  jnb     short loc_140068074
0x140068044  mov     edx, [r13+34h]
0x140068048  test    edx, edx
0x14006804a  jz      short loc_14006805E
0x14006804c  lea     rcx, ds:10h[rax*8]
0x140068054  cmp     rdx, rcx
0x140068057  jb      short loc_140068074
0x140068059  cmp     edx, r8d
0x14006805c  ja      short loc_140068074
0x14006805e  movzx   eax, word ptr [r13+32h]
0x140068063  cmp     eax, r8d
0x140068066  ja      short loc_140068074
0x140068068  lea     ecx, [rax+rdx]
0x14006806b  cmp     ecx, r8d
0x14006806e  jbe     loc_140068C60
0x140068074  mov     ecx, r15d
0x140068077  call    HsmDbgBreakOnStatus
0x14006807c  xor     r10d, r10d
0x14006807f  mov     r11d, 11h
0x140068085  cmp     [rsp+130h+var_D7], r10b
0x14006808a  jnz     loc_140068746
0x140068090  test    r13, r13
0x140068093  jz      loc_14006877D
0x140068099  mov     edi, dword ptr [rsp+130h+DataBufferLength]
0x14006809d  cmp     edi, 18h
0x1400680a0  jb      short loc_1400680F7
0x1400680a2  movzx   eax, word ptr [r13+0Eh]
0x1400680a7  mov     ecx, 5
0x1400680ac  cmp     cx, ax
0x1400680af  jnb     short loc_1400680F7
0x1400680b1  mov     r8d, [r13+8]
0x1400680b5  cmp     r8d, 40h ; '@'
0x1400680b9  jb      short loc_1400680F7
0x1400680bb  movzx   r9d, word ptr [r13+38h]
0x1400680c0  cmp     r9w, 12h
0x1400680c5  jnb     short loc_1400680F7
0x1400680c7  mov     edx, [r13+3Ch]
0x1400680cb  test    edx, edx
0x1400680cd  jz      short loc_1400680E1
0x1400680cf  lea     rcx, ds:10h[rax*8]
0x1400680d7  cmp     rdx, rcx
0x1400680da  jb      short loc_1400680F7
0x1400680dc  cmp     edx, r8d
0x1400680df  ja      short loc_1400680F7
0x1400680e1  movzx   eax, word ptr [r13+3Ah]
0x1400680e6  cmp     eax, r8d
0x1400680e9  ja      short loc_1400680F7
0x1400680eb  lea     ecx, [rax+rdx]
0x1400680ee  cmp     ecx, r8d
0x1400680f1  jbe     loc_140068C09
0x1400680f7  mov     ecx, r15d
0x1400680fa  call    HsmDbgBreakOnStatus
0x1400680ff  xor     r10d, r10d
0x140068102  jmp     loc_140068781
0x140068107  add     r13, 4
0x14006810b  lea     ecx, [r15-4]
0x14006810f  mov     r9d, 4
0x140068115  cmp     r15d, r9d
0x140068118  ja      loc_140067FE7
0x14006811e  jmp     loc_140067FE4
0x140068123  lea     r9, [rbp+4Fh+var_C4]
0x140068127  mov     edx, 424Dh
0x14006812c  lea     r8, [rbp+4Fh+var_60]
0x140068130  mov     rcx, rsi
0x140068133  call    HsmiPrepareBitmapCommit
0x140068138  mov     ecx, eax
0x14006813a  mov     edi, eax
0x14006813c  call    HsmDbgBreakOnStatus
0x140068141  test    edi, edi
0x140068143  js      loc_140068CD1
0x140068149  mov     r8, [rbp+4Fh+var_60]
0x14006814d  mov     eax, [rbp+4Fh+var_C4]
0x140068150  mov     [rbp+4Fh+Src], r8
0x140068154  mov     [rbp+4Fh+var_90], eax
0x140068157  mov     edx, 4000h
0x14006815c  mov     ecx, 100h
0x140068161  mov     r8d, 70527348h
0x140068167  call    cs:__imp_ExAllocatePool2
0x14006816e  nop     dword ptr [rax+rax+00h]
0x140068173  xor     edx, edx; Val
0x140068175  mov     [rsp+130h+DataBuffer], rax
0x14006817a  mov     r15, rax
0x14006817d  test    rax, rax
  ... truncated ...
```
