# HsmpRpCommitNoLock

- ea: `0x140067e24`
- end: `0x140069829`
- name: `HsmpRpCommitNoLock`
- size: `6661`
- prototype: ``
- caller_count: `11`
- callee_count: `30`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140002aec`
- `0x14004357c`
- `0x140043c9c`
- `0x140047c20`
- `0x14005fde4`
- `0x140075998`
- `0x140075ee4`
- `0x14007b06c`
- `0x14007b72c`
- `0x14007e550`
- `0x14007fb2c`

## callees

- `0x140003c50`
- `0x140009300`
- `0x14000abb8`
- `0x14000b62c`
- `0x14000db8c`
- `0x14001aab0`
- `0x14001ab48`
- `0x14001abac`
- `0x14001ac48`
- `0x14001e1c0`
- `0x14001e300`
- `0x14001e600`
- `0x140055fb0`
- `0x140057948`
- `0x140058ddc`
- `0x14005a7dc`
- `0x140065178`
- `0x1400651c0`
- `0x140067920`
- `0x14006793c`
- `0x140067958`
- `0x140067974`
- `0x140067c70`
- `0x140067e24`
- `0x140069830`
- `0x14006987c`
- `0x140069948`
- `0x140069a40`
- `0x14006a8b0`
- `0x1400766ac`

## import_xrefs

- `ntoskrnl!RtlComputeCrc32` at `0x140068700`
- `ntoskrnl!RtlComputeCrc32` at `0x140068700`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400689ad`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400689c6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400689ad`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400689c6`
- `ntoskrnl!ExAllocatePool2` at `0x140068287`
- `ntoskrnl!ExAllocatePool2` at `0x140068287`
- `FLTMGR!FltTagFile` at `0x140069754`
- `FLTMGR!FltTagFile` at `0x140069754`
- `FLTMGR!FltTagFileEx` at `0x140068a90`
- `FLTMGR!FltTagFileEx` at `0x140068a90`
- `FLTMGR!FltUntagFile` at `0x140068b3c`
- `FLTMGR!FltUntagFile` at `0x140068b3c`
- `FLTMGR!FltQueryInformationFile` at `0x140067f12`
- `FLTMGR!FltQueryInformationFile` at `0x140067f12`
- `FLTMGR!FltReleasePushLockEx` at `0x140068469`
- `FLTMGR!FltReleasePushLockEx` at `0x140069440`
- `FLTMGR!FltReleasePushLockEx` at `0x140068469`
- `FLTMGR!FltReleasePushLockEx` at `0x140069440`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x140068448`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x140068448`

## pseudocode

```c
__int64 __fastcall HsmpRpCommitNoLock(__int64 a1, __int64 a2, struct _FILE_OBJECT *a3, char a4, char a5)
{
  __int64 v5; // rbx
  __int64 v8; // r15
  int RangeState; // edi
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
  bool v26; // bl
  char v27; // r15
  bool v28; // bl
  char v29; // r13
  char v30; // bl
  bool IsBitmapCommitPending; // al
  char v32; // al
  PFILE_OBJECT v33; // r15
  unsigned int v34; // r15d
  char *v35; // r13
  void *v36; // r10
  unsigned __int64 v37; // r13
  unsigned __int16 v38; // r9
  unsigned int v39; // ecx
  int v40; // eax
  int v41; // r15d
  __int64 v42; // rax
  unsigned int v43; // r8d
  unsigned __int16 v44; // r9
  unsigned __int64 v45; // rdx
  unsigned int v46; // eax
  int v47; // ecx
  unsigned int v48; // edi
  __int64 v49; // rax
  unsigned int v50; // r8d
  unsigned __int16 v51; // r9
  unsigned __int64 v52; // rdx
  unsigned int v53; // eax
  int v54; // ecx
  void *v55; // r15
  unsigned __int16 v56; // cx
  _DWORD *v57; // rbx
  _WORD *v58; // rdi
  unsigned int *v59; // r15
  __int64 v60; // rcx
  __int64 v61; // rax
  unsigned int v62; // r9d
  int v63; // edx
  int v64; // ecx
  int v65; // r8d
  int v66; // edx
  int v67; // ecx
  int v68; // edx
  int v69; // ecx
  int v70; // edx
  int v71; // r8d
  __int64 v72; // rcx
  __int64 v73; // rax
  char *v74; // rdx
  char *v75; // rdx
  __int64 v76; // r8
  __int64 v77; // rdx
  unsigned __int16 v78; // r8
  __int64 v79; // rcx
  __int64 v80; // rax
  __int64 v81; // rdx
  __int64 LastHydrationTime; // rdx
  int v83; // r8d
  __int64 v84; // rcx
  __int64 v85; // r9
  __int64 v86; // rax
  __int64 v87; // rdx
  __int64 LastDehydrationTime; // rax
  int v89; // r8d
  __int64 v90; // r9
  __int64 v91; // rdx
  __int64 v92; // rcx
  __int64 v93; // rax
  __int64 v94; // rdx
  int LastDehydrationReason; // edx
  int v96; // r8d
  __int64 v97; // rcx
  __int64 v98; // r9
  __int64 v99; // rax
  char *v100; // rdx
  char *v101; // rdx
  __int64 v102; // rcx
  size_t v103; // r8
  __int64 v104; // rcx
  char *v105; // rcx
  unsigned int v106; // r8d
  unsigned int v107; // edx
  int v108; // r8d
  PDEVICE_OBJECT v109; // rcx
  __int64 v110; // rdx
  __int64 v111; // rax
  int v112; // eax
  __int64 v113; // rcx
  __int64 v114; // rcx
  char *v115; // rcx
  __int64 v116; // rax
  unsigned int v117; // r8d
  unsigned __int16 v118; // r9
  unsigned __int64 v119; // rdx
  unsigned int v120; // eax
  int v121; // eax
  void *v122; // r9
  void *v123; // r9
  PVOID v124; // rax
  struct _FILE_OBJECT *v126; // rdi
  ULONG v127; // r13d
  NTSTATUS v128; // eax
  __int64 v129; // rdx
  __int64 v130; // r8
  __int64 v131; // rbx
  PFILE_OBJECT v132; // r15
  __int64 v133; // r13
  int v134; // eax
  PDEVICE_OBJECT v135; // rcx
  __int64 v136; // rdx
  int v137; // ecx
  __int64 v138; // rax
  int v139; // ecx
  int v140; // edx
  int v141; // ecx
  int v142; // edx
  __int64 v143; // rax
  __int64 v144; // rcx
  size_t v145; // r8
  __int64 v146; // rcx
  char *v147; // rcx
  __int64 v148; // rcx
  size_t v149; // r8
  __int64 v150; // rcx
  char *v151; // rcx
  PDEVICE_OBJECT v152; // rcx
  __int64 v153; // rdx
  __int64 StreamSize; // rax
  __int64 v155; // r8
  __int64 v156; // rdx
  __int64 *v157; // rcx
  __int64 v158; // rax
  __int64 v159; // rdi
  unsigned __int64 v160; // rdx
  unsigned int v161; // eax
  unsigned int v162; // ecx
  unsigned int v163; // edx
  __int64 v164; // rdx
  __int64 v165; // r8
  int LengthReturned; // [rsp+28h] [rbp-B9h]
  char *DataBuffer; // [rsp+50h] [rbp-91h]
  char v168; // [rsp+58h] [rbp-89h]
  char v169; // [rsp+58h] [rbp-89h]
  char v170; // [rsp+59h] [rbp-88h]
  char v171; // [rsp+59h] [rbp-88h]
  char v172; // [rsp+5Ah] [rbp-87h]
  USHORT DataBufferLength[2]; // [rsp+5Ch] [rbp-85h] BYREF
  __int64 v175; // [rsp+60h] [rbp-81h]
  bool v176; // [rsp+68h] [rbp-79h] BYREF
  int v177; // [rsp+6Ch] [rbp-75h] BYREF
  PFLT_INSTANCE *v178; // [rsp+70h] [rbp-71h]
  PFILE_OBJECT FileObject; // [rsp+78h] [rbp-69h]
  void *v180; // [rsp+80h] [rbp-61h]
  PVOID P; // [rsp+88h] [rbp-59h]
  void *Src; // [rsp+90h] [rbp-51h] BYREF
  unsigned int v183; // [rsp+98h] [rbp-49h]
  unsigned int v184; // [rsp+9Ch] [rbp-45h]
  int v185; // [rsp+A0h] [rbp-41h]
  unsigned int v186; // [rsp+A4h] [rbp-3Dh] BYREF
  unsigned int v187; // [rsp+A8h] [rbp-39h] BYREF
  void *v188; // [rsp+B0h] [rbp-31h]
  __int64 v189; // [rsp+B8h] [rbp-29h]
  void *v190; // [rsp+C0h] [rbp-21h] BYREF
  void *v191; // [rsp+C8h] [rbp-19h] BYREF
  void *v192; // [rsp+D0h] [rbp-11h] BYREF
  __int128 FileInformation; // [rsp+D8h] [rbp-9h] BYREF
  __int64 v194; // [rsp+E8h] [rbp+7h]

  v5 = *(_QWORD *)(a2 + 16);
  v189 = a1;
  P = 0;
  v8 = *(_QWORD *)(v5 + 32);
  v180 = 0;
  DataBuffer = 0;
  v190 = 0;
  v183 = 0;
  v186 = 0;
  v191 = 0;
  v184 = 0;
  v187 = 0;
  v192 = 0;
  v185 = 0;
  v177 = 0;
  v168 = 0;
  v176 = 0;
  FileInformation = 0;
  v194 = 0;
  FileObject = a3;
  v175 = v5;
  RangeState = HsmpValidateStreamContextNoLock(a2, a3);
  HsmDbgBreakOnStatus(RangeState);
  if ( RangeState < 0 )
    goto LABEL_216;
  v10 = *(_DWORD *)(a2 + 28);
  v11 = (PFLT_INSTANCE *)(a1 + 32);
  v178 = (PFLT_INSTANCE *)(a1 + 32);
  v12 = 0;
  v170 = 0;
  v172 = 0;
  v13 = 1;
  if ( (v10 & 2) != 0 )
    goto LABEL_13;
  RangeState = FltQueryInformationFile(*v11, FileObject, &FileInformation, 0x18u, FileStandardInformation, 0);
  HsmDbgBreakOnStatus(RangeState);
  if ( RangeState < 0 )
  {
    v152 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      goto LABEL_161;
    }
    v153 = 32;
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
      WPP_SF_qiqii(*(_QWORD *)(v155 + 24), v156, v155, a2, *(_QWORD *)(v5 + 32), FileObject, v156, StreamSize);
      v14 = *((_QWORD *)&FileInformation + 1);
    }
    v157 = *(__int64 **)(a2 + 160);
    v158 = *v157;
    if ( *v157 >= v14 )
      v158 = v14;
    *v157 = v158;
  }
  RangeState = HsmiCompactBitmapNoLock(a2, 0x4244u, &v176);
  HsmDbgBreakOnStatus(RangeState);
  if ( RangeState < 0 )
  {
    v152 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      v153 = 34;
LABEL_282:
      WPP_SF_qqd(v152->AttachedDevice, v153, WPP_1b967c8d739c32210f02f2d42c5aa5c3_Traceguids, a2, v8, RangeState);
LABEL_161:
      v55 = DataBuffer;
      goto LABEL_162;
    }
LABEL_408:
    v55 = 0;
    goto LABEL_162;
  }
  RangeState = 0;
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
      RangeState = HsmpBitmapGetRangeState(v20, v20, &Src, DataBufferLength);
      HsmDbgBreakOnStatus(RangeState);
      if ( RangeState < 0 || *(_DWORD *)DataBufferLength == 2 )
        goto LABEL_8;
      v19 = *(_DWORD *)DataBufferLength == 1;
    }
    v139 = (*(_DWORD *)(a2 + 28) >> 8) & 1;
    v12 = v139 != v19;
    v140 = *(_DWORD *)(a2 + 28) ^ ((unsigned __int16)*(_DWORD *)(a2 + 28) ^ (unsigned __int16)((_WORD)v19 << 8)) & 0x100;
    *(_DWORD *)(a2 + 28) = v140;
    if ( v139 != v19 )
      *(_DWORD *)(a2 + 28) = v140 | 0x200;
    HsmiDeleteExternalBitmap(a2, 16982);
    HsmiReleaseBitmap(a2, 16982);
  }
LABEL_8:
  HsmDbgBreakOnStatus(RangeState);
  if ( RangeState < 0 )
  {
    v152 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      v153 = 35;
      goto LABEL_282;
    }
    goto LABEL_408;
  }
  RangeState = 0;
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
    RangeState = HsmpBitmapGetRangeState(v25, v25, &Src, DataBufferLength);
    HsmDbgBreakOnStatus(RangeState);
    if ( RangeState < 0 || *(_DWORD *)DataBufferLength == 2 )
      goto LABEL_10;
    v24 = *(_DWORD *)DataBufferLength == 1;
  }
  v141 = (*(_DWORD *)(a2 + 28) >> 10) & 1;
  v172 = v141 != v24;
  v142 = *(_DWORD *)(a2 + 28) ^ ((unsigned __int16)*(_DWORD *)(a2 + 28) ^ (unsigned __int16)((_WORD)v24 << 10)) & 0x400;
  *(_DWORD *)(a2 + 28) = v142;
  if ( v141 != v24 )
    *(_DWORD *)(a2 + 28) = v142 | 0x800;
  HsmiDeleteExternalBitmap(a2, 16973);
  HsmiReleaseBitmap(a2, 16973);
LABEL_10:
  HsmDbgBreakOnStatus(RangeState);
  if ( RangeState < 0 )
  {
    v152 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      goto LABEL_161;
    }
    v153 = 36;
    goto LABEL_282;
  }
  v26 = v176 || (*(_DWORD *)(a2 + 28) & 0x80) != 0;
  v27 = v26 | HsmiIsBitmapCommitPending(a2, 16964);
  v168 = v27;
  v28 = v12 || (*(_DWORD *)(a2 + 28) & 0x200) != 0;
  v29 = v28 | HsmiIsBitmapCommitPending(a2, 16982);
  v170 = v29;
  v30 = v172 | ((*(_DWORD *)(a2 + 28) & 0x800) != 0);
  IsBitmapCommitPending = HsmiIsBitmapCommitPending(a2, 16973);
  v11 = v178;
  v32 = v30 | IsBitmapCommitPending;
  v172 = v32;
  if ( a5 && !v27 && !v29 && !v32 )
  {
LABEL_216:
    v55 = 0;
    goto LABEL_162;
  }
  v5 = v175;
LABEL_13:
  v33 = FileObject;
  RangeState = HsmpRpReadBuffer(*v11, FileObject);
  HsmDbgBreakOnStatus(RangeState);
  if ( RangeState == -1073741195 )
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
    RangeState = 0;
    P = v180;
    v55 = 0;
    goto LABEL_162;
  }
  if ( RangeState < 0 )
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
    P = v180;
    goto LABEL_161;
  }
  P = v180;
  if ( (*(_DWORD *)v180 & 0xFFFF0FFF) != dword_140029670 )
  {
    RangeState = -1073688821;
    HsmDbgBreakOnStatus(-1073688821);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_qiqDDd(
        WPP_GLOBAL_Control->AttachedDevice,
        v164,
        v165,
        a2,
        *(_QWORD *)(v5 + 32),
        v33,
        dword_140029670,
        *(_DWORD *)P);
    }
    goto LABEL_161;
  }
  v34 = *((unsigned __int16 *)v180 + 2);
  v35 = (char *)v180 + 8;
  RangeState = HsmpRpValidateBuffer((char *)v180 + 8, *((unsigned __int16 *)v180 + 2));
  HsmDbgBreakOnStatus(RangeState);
  v36 = 0;
  if ( RangeState < 0 )
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
  v180 = v36;
  v188 = v36;
  Src = v36;
  if ( (v40 & 2) == 0 )
  {
    v41 = -1073741275;
    if ( v168 == (_BYTE)v36 )
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
          v47 = -1073741275;
        }
        else
        {
          if ( (_DWORD)v45 && (_WORD)v46 )
            v180 = (void *)(v45 + v37);
          else
            v180 = v36;
          v183 = v46;
          v47 = (int)v36;
        }
        HsmDbgBreakOnStatus(v47);
        v36 = 0;
      }
    }
    else
    {
      RangeState = HsmiPrepareBitmapCommit(a2, 16964, &v190, &v186);
      HsmDbgBreakOnStatus(RangeState);
      v36 = 0;
      if ( RangeState < 0 )
      {
        v109 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          v110 = 41;
          goto LABEL_283;
        }
        goto LABEL_234;
      }
      v180 = v190;
      v183 = v186;
    }
    if ( v170 == (_BYTE)v36 )
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
          v54 = -1073741275;
        }
        else
        {
          if ( (_DWORD)v52 && (_WORD)v53 )
            v188 = (void *)(v37 + v52);
          else
            v188 = v36;
          v184 = v53;
          v54 = (int)v36;
        }
        HsmDbgBreakOnStatus(v54);
        v36 = 0;
        goto LABEL_143;
      }
LABEL_142:
      v48 = *(_DWORD *)DataBufferLength;
LABEL_143:
      if ( v172 == (_BYTE)v36 )
      {
        if ( v37 )
        {
          if ( v48 >= 0x18 )
          {
            v116 = *(unsigned __int16 *)(v37 + 14);
            if ( (unsigned __int16)v116 > 6u )
            {
              v117 = *(_DWORD *)(v37 + 8);
              if ( v117 >= 0x48 )
              {
                v118 = *(_WORD *)(v37 + 64);
                if ( v118 < 0x12u )
                {
                  v119 = *(unsigned int *)(v37 + 68);
                  if ( !(_DWORD)v119 || v119 >= 8 * v116 + 16 && (unsigned int)v119 <= v117 )
                  {
                    v120 = *(unsigned __int16 *)(v37 + 66);
                    if ( v120 <= v117
                      && v120 + (unsigned int)v119 <= v117
                      && v120 + (unsigned int)v119 >= (unsigned int)v119
                      && v118 == 17 )
                    {
                      if ( (_DWORD)v119 && (_WORD)v120 )
                        Src = (void *)(v119 + v37);
                      else
                        Src = v36;
                      v185 = v120;
                      v41 = (int)v36;
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
      RangeState = HsmiPrepareBitmapCommit(a2, 16973, &v192, &v177);
      HsmDbgBreakOnStatus(RangeState);
      if ( RangeState >= 0 )
      {
        Src = v192;
        v185 = v177;
        goto LABEL_51;
      }
      v109 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_161;
      }
      v110 = 43;
LABEL_283:
      v111 = *(_QWORD *)(v5 + 32);
      goto LABEL_284;
    }
    RangeState = HsmiPrepareBitmapCommit(a2, 16982, &v191, &v187);
    HsmDbgBreakOnStatus(RangeState);
    v36 = 0;
    if ( RangeState >= 0 )
    {
      v188 = v191;
      v184 = v187;
      goto LABEL_142;
    }
    v109 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      v110 = 42;
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
    v177 = 10;
    v56 = 10;
    v57 = DataBuffer + 4;
    if ( v37 )
    {
      v56 = *(_WORD *)(v37 + 14);
      if ( v56 <= 0xAu )
        v56 = 10;
    }
    *((_DWORD *)DataBuffer + 2) = 0;
    v58 = DataBuffer + 20;
    v59 = (unsigned int *)(DataBuffer + 12);
    *((_WORD *)DataBuffer + 9) = v56;
    *v57 = 1884448070;
    *((_DWORD *)DataBuffer + 3) = 8 * v56 + 16;
    *((_WORD *)DataBuffer + 8) = 0;
    memset(DataBuffer + 20, 0, 8LL * v56);
    if ( *((_WORD *)DataBuffer + 9) )
    {
      v60 = *v59;
      if ( ((v60 + 3) & 0xFFFFFFFFFFFFFFFCuLL) + 1 > 0x3FFC )
      {
        RangeState = -1073741789;
      }
      else
      {
        v61 = ((_DWORD)v60 + 3) & 0xFFFFFFFC;
        *v59 = v61;
        if ( *v58 )
          *((_WORD *)DataBuffer + 8) |= 1u;
        *v58 = 7;
        RangeState = 0;
        *((_WORD *)DataBuffer + 11) = 1;
        *((_DWORD *)DataBuffer + 6) = v61;
        *((_BYTE *)v57 + v61) = 1;
        ++*v59;
      }
    }
    else
    {
      RangeState = -1073741811;
    }
    HsmDbgBreakOnStatus(RangeState);
    if ( RangeState < 0 )
    {
      v109 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_161;
      }
      v110 = 45;
    }
    else
    {
      v62 = *(_DWORD *)(a2 + 28);
      v63 = (v62 >> 5) & 1 | 2;
      if ( (v62 & 0x40) == 0 )
        v63 = (*(_DWORD *)(a2 + 28) >> 5) & 1;
      v64 = v63 | 4;
      if ( (v62 & 0x100) == 0 )
        v64 = v63;
      v65 = v64 | 8;
      if ( (v62 & 0x400) == 0 )
        v65 = v64;
      v66 = v65 | 0x20;
      if ( (v62 & 0x1000) == 0 )
        v66 = v65;
      v67 = v66 | 0x10;
      if ( (v62 & 2) == 0 )
        v67 = v66;
      v68 = v67 | 0x40;
      if ( (v62 & 0x2000) == 0 )
        v68 = v67;
      v69 = v68 | 0x80;
      if ( (v62 & 0x4000) == 0 )
        v69 = v68;
      v70 = v69 | 0x100;
      if ( (v62 & 0x8000) == 0 )
        v70 = v69;
      v71 = v70 | 0x200;
      if ( (v62 & 0x10000) == 0 )
        v71 = v70;
      if ( *((_WORD *)DataBuffer + 9) <= 1u )
      {
        RangeState = -1073741811;
      }
      else
      {
        v72 = *v59;
        if ( ((v72 + 3) & 0xFFFFFFFFFFFFFFFCuLL) + 4 > 0x3FFC )
        {
          RangeState = -1073741789;
        }
        else
        {
          v73 = ((_DWORD)v72 + 3) & 0xFFFFFFFC;
          *v59 = v73;
          if ( *((_WORD *)DataBuffer + 14) )
            *((_WORD *)DataBuffer + 8) |= 1u;
          *((_DWORD *)DataBuffer + 7) = 262154;
          *((_DWORD *)DataBuffer + 8) = v73;
          *(_DWORD *)((char *)v57 + v73) = v71;
          *v59 += 4;
          RangeState = 0;
        }
      }
      HsmDbgBreakOnStatus(RangeState);
      if ( RangeState < 0 )
      {
        v109 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          goto LABEL_161;
        }
        v110 = 46;
      }
      else
      {
        FltAcquirePushLockExclusiveEx(a2 + 64, 0);
        v74 = *(char **)(a2 + 48);
        RangeState = 0;
        if ( v74 )
        {
          v112 = *(_DWORD *)(a2 + 56);
          if ( v112 )
          {
            if ( *((_WORD *)DataBuffer + 9) <= 3u )
            {
              RangeState = -1073741811;
            }
            else
            {
              v113 = *v59;
              if ( (unsigned __int16)v112 + ((v113 + 3) & 0xFFFFFFFFFFFFFFFCuLL) > 0x3FFC )
              {
                RangeState = -1073741789;
              }
              else
              {
                if ( *((_WORD *)DataBuffer + 22) )
                  *((_WORD *)DataBuffer + 8) |= 1u;
                v114 = ((_DWORD)v113 + 3) & 0xFFFFFFFC;
                *v59 = v114;
                *((_DWORD *)DataBuffer + 12) = v114;
                v115 = (char *)v57 + v114;
                *((_WORD *)DataBuffer + 22) = 17;
                *((_WORD *)DataBuffer + 23) = v112;
                if ( v115 != v74 )
                  memmove(v115, v74, (unsigned __int16)v112);
                *v59 += *((unsigned __int16 *)DataBuffer + 23);
              }
            }
            HsmDbgBreakOnStatus(RangeState);
            if ( RangeState < 0 )
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
                  *(_QWORD *)(v175 + 32),
                  RangeState);
              }
              FltReleasePushLockEx(a2 + 64, 0);
              goto LABEL_161;
            }
            RangeState = 0;
          }
        }
        FltReleasePushLockEx(a2 + 64, 0);
        v76 = 2;
        if ( (*(_DWORD *)(a2 + 28) & 2) != 0 )
        {
LABEL_120:
          if ( v37 )
          {
            LOWORD(v137) = 10;
            if ( *(_WORD *)(v37 + 14) > 0xAu )
            {
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
              {
                WPP_SF_qiq(WPP_GLOBAL_Control->AttachedDevice, v75, v76, a2, *(_QWORD *)(v175 + 32), FileObject);
              }
              LOWORD(v137) = 10;
            }
            while ( 1 )
            {
              v138 = *(unsigned __int16 *)(v37 + 14);
              if ( (unsigned __int16)v137 >= (unsigned __int16)v138 )
                break;
              v159 = (unsigned __int16)v137;
              v160 = *(unsigned int *)(v37 + 8LL * (unsigned __int16)v137 + 20);
              if ( (_DWORD)v160 && v160 < 8 * v138 + 16
                || (v161 = *(_DWORD *)(v37 + 8), (unsigned int)v160 > v161)
                || (v162 = *(unsigned __int16 *)(v37 + 8LL * (unsigned __int16)v137 + 18), v162 > v161)
                || v162 + (unsigned int)v160 < (unsigned int)v160
                || v162 + (unsigned int)v160 > v161 )
              {
                RangeState = -1073688830;
                HsmDbgBreakOnStatus(-1073688830);
                v109 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
                  && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                {
                  v110 = 56;
                  goto LABEL_129;
                }
                goto LABEL_161;
              }
              v163 = *v59 + v162;
              if ( v163 < *v59 || v163 > 0x3FFC )
              {
                RangeState = -1073688829;
                HsmDbgBreakOnStatus(-1073688829);
                v109 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
                  && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                {
                  v110 = 57;
                  goto LABEL_129;
                }
                goto LABEL_161;
              }
              *(_QWORD *)&v57[2 * v159 + 4] = *(_QWORD *)(v37 + 8 * v159 + 16);
              memmove(
                (char *)v57 + *v59,
                (const void *)(v37 + *(unsigned int *)(v37 + 8 * v159 + 20)),
                *(unsigned __int16 *)(v37 + 8 * v159 + 18));
              v137 = v177;
              v57[2 * v159 + 5] = *v59;
              *v59 += HIWORD(v57[2 * v159 + 4]);
              LOWORD(v137) = v137 + 1;
              v177 = v137;
            }
          }
          v106 = *v59;
          *((_WORD *)DataBuffer + 8) |= 2u;
          v171 = 0;
          *((_DWORD *)DataBuffer + 2) = RtlComputeCrc32(0, (PUCHAR)DataBuffer + 12, v106 - 8);
          v107 = *(_DWORD *)DataBuffer & 0xFFFFFFF0 | 1;
          *(_DWORD *)DataBuffer = v107;
          v108 = (unsigned __int16)(*(_WORD *)v59 + 4);
          *(_DWORD *)DataBufferLength = v108;
          *(_DWORD *)DataBuffer = (unsigned __int16)v107 | (v108 << 16);
          v177 = v108;
          if ( (_Config & 2) != 0 )
          {
            HsmiRpCompressBuffer((UCHAR *)DataBuffer, &v177);
            *(_DWORD *)DataBufferLength = v177;
          }
          if ( (*(_DWORD *)(a2 + 28) & 0x100) == 0 )
          {
            v171 = 1;
            RangeState = HsmpToggleFileAttributesNotify(v189, (_DWORD)FileObject, a4 != 0 ? 8 : 0, 4198400, 0);
            HsmDbgBreakOnStatus(RangeState);
            if ( RangeState < 0 )
            {
              v109 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
                || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
              {
                goto LABEL_161;
              }
              v110 = 58;
              goto LABEL_129;
            }
          }
          v169 = 0;
          v126 = FileObject;
          if ( !FileObject->WriteAccess )
          {
            FileObject->WriteAccess = 1;
            v169 = 1;
          }
          v127 = dword_140029670
               | *(_DWORD *)(a2 + 28) & 0x1000
               | (2 * (*(_DWORD *)(a2 + 28) & 0x6000 | ((*(_DWORD *)(a2 + 28) & 0x40) << 6)));
          if ( *(_DWORD *)(v189 + 80) == 28
            && (unsigned int)Feature_ReFS_OneDrive_Support__private_IsEnabledDeviceUsageNoInline() )
          {
            RangeState = FltUntagFile(*v178, v126, *(_DWORD *)P, 0);
            HsmDbgBreakOnStatus(RangeState);
            if ( RangeState < 0 )
            {
              v135 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
                || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
              {
                goto LABEL_159;
              }
              v136 = 59;
              goto LABEL_239;
            }
            v128 = FltTagFile(*v178, FileObject, v127, 0, DataBuffer, DataBufferLength[0]);
          }
          else
          {
            LOWORD(LengthReturned) = DataBufferLength[0];
            v128 = FltTagFileEx(*v178, v126, v127, 0, DataBuffer, LengthReturned, *(_DWORD *)P, 0, 0);
          }
          RangeState = v128;
          HsmDbgBreakOnStatus(v128);
          if ( RangeState >= 0 )
          {
            *(_DWORD *)(a2 + 24) = v127;
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
            {
              v131 = v175;
              WPP_SF_qLiqDD(
                WPP_GLOBAL_Control->AttachedDevice,
                v129,
                v130,
                a2,
                *(_DWORD *)(a2 + 28),
                *(_QWORD *)(v175 + 32),
                DataBuffer + 4,
                *v59,
                *(_DWORD *)DataBufferLength);
            }
            else
            {
              v131 = v175;
            }
            v132 = FileObject;
            v133 = v189;
            if ( v171
              || (RangeState = HsmpToggleFileAttributesNotify(v189, (_DWORD)FileObject, a4 != 0 ? 8 : 0, 0, 4198400),
                  HsmDbgBreakOnStatus(RangeState),
                  RangeState >= 0) )
            {
              v134 = *(_DWORD *)(a2 + 28);
              if ( (v134 & 2) == 0 )
              {
                if ( (v134 & 0x20) == 0 && (v134 & 0x100) != 0 )
                  v13 = 0;
                LOBYTE(v130) = v13;
                HsmpToggleFileSparseAttribute(v133, v132, v130);
              }
              v121 = *(_DWORD *)(a2 + 28);
              if ( (v121 & 4) != 0 )
                *(_DWORD *)(a2 + 28) = v121 & 0xFFFFFFE3;
              goto LABEL_159;
            }
            v135 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
            {
              v143 = *(_QWORD *)(v131 + 32);
              v136 = 62;
              goto LABEL_244;
            }
LABEL_159:
            if ( v169 )
              FileObject->WriteAccess = 0;
            goto LABEL_161;
          }
          v135 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
            || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
          {
            goto LABEL_159;
          }
          v136 = 60;
LABEL_239:
          v143 = *(_QWORD *)(v175 + 32);
LABEL_244:
          WPP_SF_qqd(v135->AttachedDevice, v136, WPP_1b967c8d739c32210f02f2d42c5aa5c3_Traceguids, a2, v143, RangeState);
          goto LABEL_159;
        }
        v77 = HsmpGetStreamSize(a2);
        if ( v78 >= *((_WORD *)DataBuffer + 9) )
        {
          RangeState = -1073741811;
        }
        else
        {
          v79 = *v59;
          if ( ((v79 + 3) & 0xFFFFFFFFFFFFFFFCuLL) + 8 > 0x3FFC )
          {
            RangeState = -1073741789;
          }
          else
          {
            v80 = ((_DWORD)v79 + 3) & 0xFFFFFFFC;
            *v59 = v80;
            if ( *((_WORD *)DataBuffer + 18) )
              *((_WORD *)DataBuffer + 8) |= 1u;
            *((_DWORD *)DataBuffer + 9) = 524294;
            *((_DWORD *)DataBuffer + 10) = v80;
            *(_QWORD *)((char *)v57 + v80) = v77;
            *v59 += 8;
          }
        }
        HsmDbgBreakOnStatus(RangeState);
        if ( RangeState < 0 )
        {
          v109 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
            || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
          {
            goto LABEL_161;
          }
          v110 = 48;
        }
        else
        {
          LastHydrationTime = HsmpGetLastHydrationTime(a2, v81, 0);
          if ( (unsigned __int16)(v83 + 7) >= *((_WORD *)DataBuffer + 9) )
          {
            RangeState = -1073741811;
          }
          else
          {
            v84 = *v59;
            v85 = (unsigned int)(v83 + 8);
            if ( v85 + ((v84 + 3) & 0xFFFFFFFFFFFFFFFCuLL) > 0x3FFC )
            {
              RangeState = -1073741789;
            }
            else
            {
              v86 = ((_DWORD)v84 + 3) & 0xFFFFFFFC;
              *v59 = v86;
              if ( *((_WORD *)DataBuffer + 38) != (_WORD)v83 )
                *((_WORD *)DataBuffer + 8) |= 1u;
              *((_DWORD *)DataBuffer + 19) = 524294;
              RangeState = v83;
              *((_DWORD *)DataBuffer + 20) = v86;
              *(_QWORD *)((char *)v57 + v86) = LastHydrationTime;
              *v59 += v85;
            }
          }
          HsmDbgBreakOnStatus(RangeState);
          if ( RangeState < 0 )
          {
            v109 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
              || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
            {
              goto LABEL_161;
            }
            v110 = 49;
          }
          else
          {
            LastDehydrationTime = HsmpGetLastDehydrationTime(a2, v87, 0);
            v90 = (unsigned int)(v89 + 8);
            v91 = LastDehydrationTime;
            if ( (unsigned __int16)(v89 + 8) >= *((_WORD *)DataBuffer + 9) )
            {
              RangeState = -1073741811;
            }
            else
            {
              v92 = *v59;
              if ( v90 + ((v92 + 3) & 0xFFFFFFFFFFFFFFFCuLL) > 0x3FFC )
              {
                RangeState = -1073741789;
              }
              else
              {
                v93 = ((_DWORD)v92 + 3) & 0xFFFFFFFC;
                *v59 = v93;
                if ( *((_WORD *)DataBuffer + 42) != (_WORD)v89 )
                  *((_WORD *)DataBuffer + 8) |= 1u;
                *((_DWORD *)DataBuffer + 21) = 524294;
                RangeState = v89;
                *((_DWORD *)DataBuffer + 22) = v93;
                *(_QWORD *)((char *)v57 + v93) = v91;
                *v59 += v90;
              }
            }
            HsmDbgBreakOnStatus(RangeState);
            if ( RangeState < 0 )
            {
              v109 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
                || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
              {
                goto LABEL_161;
              }
              v110 = 50;
            }
            else
            {
              LastDehydrationReason = HsmpGetLastDehydrationReason(a2, v94, 0);
              if ( (unsigned __int16)(v96 + 9) >= *((_WORD *)DataBuffer + 9) )
              {
                RangeState = -1073741811;
              }
              else
              {
                v97 = *v59;
                v98 = (unsigned int)(v96 + 4);
                if ( v98 + ((v97 + 3) & 0xFFFFFFFFFFFFFFFCuLL) > 0x3FFC )
                {
                  RangeState = -1073741789;
                }
                else
                {
                  v99 = ((_DWORD)v97 + 3) & 0xFFFFFFFC;
                  *v59 = v99;
                  if ( *((_WORD *)DataBuffer + 46) != (_WORD)v96 )
                    *((_WORD *)DataBuffer + 8) |= 1u;
                  *((_DWORD *)DataBuffer + 23) = 262154;
                  RangeState = v96;
                  *((_DWORD *)DataBuffer + 24) = v99;
                  *(_DWORD *)((char *)v57 + v99) = LastDehydrationReason;
                  *v59 += v98;
                }
              }
              HsmDbgBreakOnStatus(RangeState);
              if ( RangeState < 0 )
              {
                v109 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
                  || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
                {
                  goto LABEL_161;
                }
                v110 = 51;
              }
              else
              {
                v100 = (char *)v180;
                RangeState = 0;
                if ( v180 )
                {
                  if ( *((_WORD *)DataBuffer + 9) <= 4u )
                  {
                    RangeState = -1073741811;
                  }
                  else
                  {
                    v144 = *v59;
                    v145 = (unsigned __int16)v183;
                    if ( (unsigned __int16)v183 + ((v144 + 3) & 0xFFFFFFFFFFFFFFFCuLL) > 0x3FFC )
                    {
                      RangeState = -1073741789;
                    }
                    else
                    {
                      if ( *((_WORD *)DataBuffer + 26) )
                        *((_WORD *)DataBuffer + 8) |= 1u;
                      v146 = ((_DWORD)v144 + 3) & 0xFFFFFFFC;
                      *v59 = v146;
                      *((_DWORD *)DataBuffer + 14) = v146;
                      v147 = (char *)v57 + v146;
                      *((_WORD *)DataBuffer + 26) = 17;
                      *((_WORD *)DataBuffer + 27) = v145;
                      if ( v147 != v100 )
                        memmove(v147, v100, v145);
                      *v59 += *((unsigned __int16 *)DataBuffer + 27);
                    }
                  }
                  HsmDbgBreakOnStatus(RangeState);
                  if ( RangeState < 0 )
                  {
                    v109 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
                      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
                    {
                      goto LABEL_161;
                    }
                    v110 = 52;
                    goto LABEL_129;
                  }
                  RangeState = 0;
                }
                v101 = (char *)v188;
                if ( v188 )
                {
                  if ( *((_WORD *)DataBuffer + 9) <= 5u )
                  {
                    RangeState = -1073741811;
                  }
                  else
                  {
                    v148 = *v59;
                    v149 = (unsigned __int16)v184;
                    if ( (unsigned __int16)v184 + ((v148 + 3) & 0xFFFFFFFFFFFFFFFCuLL) > 0x3FFC )
                    {
                      RangeState = -1073741789;
                    }
                    else
                    {
                      if ( *((_WORD *)DataBuffer + 30) )
                        *((_WORD *)DataBuffer + 8) |= 1u;
                      v150 = ((_DWORD)v148 + 3) & 0xFFFFFFFC;
                      *v59 = v150;
                      *((_DWORD *)DataBuffer + 16) = v150;
                      v151 = (char *)v57 + v150;
                      *((_WORD *)DataBuffer + 30) = 17;
                      *((_WORD *)DataBuffer + 31) = v149;
                      if ( v151 != v101 )
                        memmove(v151, v101, v149);
                      *v59 += *((unsigned __int16 *)DataBuffer + 31);
                    }
                  }
                  HsmDbgBreakOnStatus(RangeState);
                  if ( RangeState < 0 )
                  {
                    v109 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
                      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
                    {
                      goto LABEL_161;
                    }
                    v110 = 53;
                    goto LABEL_129;
                  }
                  RangeState = 0;
                }
                v75 = (char *)Src;
                if ( !Src )
                  goto LABEL_120;
                if ( *((_WORD *)DataBuffer + 9) <= 6u )
                {
                  RangeState = -1073741811;
                }
                else
                {
                  v102 = *v59;
                  v103 = (unsigned __int16)v185;
                  if ( (unsigned __int16)v185 + ((v102 + 3) & 0xFFFFFFFFFFFFFFFCuLL) > 0x3FFC )
                  {
                    RangeState = -1073741789;
                  }
                  else
                  {
                    if ( *((_WORD *)DataBuffer + 34) )
                      *((_WORD *)DataBuffer + 8) |= 1u;
                    v104 = ((_DWORD)v102 + 3) & 0xFFFFFFFC;
                    *v59 = v104;
                    *((_DWORD *)DataBuffer + 18) = v104;
                    v105 = (char *)v57 + v104;
                    *((_WORD *)DataBuffer + 34) = 17;
                    *((_WORD *)DataBuffer + 35) = v103;
                    if ( v105 != v75 )
                      memmove(v105, v75, v103);
                    *v59 += *((unsigned __int16 *)DataBuffer + 35);
                  }
                }
                HsmDbgBreakOnStatus(RangeState);
                if ( RangeState >= 0 )
                  goto LABEL_120;
                v109 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
                  || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
                {
                  goto LABEL_161;
                }
                v110 = 54;
              }
            }
          }
        }
      }
    }
LABEL_129:
    v111 = *(_QWORD *)(v175 + 32);
LABEL_284:
    WPP_SF_qqd(v109->AttachedDevice, v110, WPP_1b967c8d739c32210f02f2d42c5aa5c3_Traceguids, a2, v111, RangeState);
    goto LABEL_161;
  }
  RangeState = -1073741670;
  HsmDbgBreakOnStatus(-1073741670);
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
  HsmiCompleteBitmapCommit(a2, 16964, RangeState, v190);
  v122 = v191;
  *(_DWORD *)(a2 + 28) &= ~0x80u;
  HsmiCompleteBitmapCommit(a2, 16982, RangeState, v122);
  v123 = v192;
  *(_DWORD *)(a2 + 28) &= ~0x200u;
  HsmiCompleteBitmapCommit(a2, 16973, RangeState, v123);
  v124 = P;
  *(_DWORD *)(a2 + 28) &= ~0x800u;
  if ( v124 )
    ExFreePoolWithTag(v124, 0x70527348u);
  if ( v55 )
    ExFreePoolWithTag(v55, 0x70527348u);
  return (unsigned int)RangeState;
}

```

## disassembly

```asm
0x140067e24  mov     [rsp-8+arg_18], rbx
0x140067e29  push    rbp
0x140067e2a  push    rsi
0x140067e2b  push    rdi
0x140067e2c  push    r12
0x140067e2e  push    r13
0x140067e30  push    r14
0x140067e32  push    r15
0x140067e34  lea     rbp, [rsp-1Fh]
0x140067e39  sub     rsp, 100h
0x140067e40  mov     rax, cs:__security_cookie
0x140067e47  xor     rax, rsp
0x140067e4a  mov     [rbp+4Fh+var_40], rax
0x140067e4e  mov     rbx, [rdx+10h]
0x140067e52  mov     r14, rcx
0x140067e55  mov     [rbp+4Fh+var_78], rcx
0x140067e59  mov     rsi, rdx
0x140067e5c  xor     ecx, ecx
0x140067e5e  mov     [rsp+130h+var_D5], r9b
0x140067e63  xorps   xmm0, xmm0
0x140067e66  mov     [rbp+4Fh+P], rcx
0x140067e6a  mov     r15, [rbx+20h]
0x140067e6e  xor     eax, eax
0x140067e70  mov     [rbp+4Fh+var_B0], rcx
0x140067e74  mov     rdx, r8
0x140067e77  mov     [rsp+130h+DataBuffer], rcx
0x140067e7c  mov     [rbp+4Fh+var_70], rcx
0x140067e80  mov     [rbp+4Fh+var_98], ecx
0x140067e83  mov     [rbp+4Fh+var_8C], ecx
0x140067e86  mov     [rbp+4Fh+var_68], rcx
0x140067e8a  mov     [rbp+4Fh+var_94], ecx
0x140067e8d  mov     [rbp+4Fh+var_88], ecx
0x140067e90  mov     [rbp+4Fh+var_60], rcx
0x140067e94  mov     [rbp+4Fh+var_90], ecx
0x140067e97  mov     [rbp+4Fh+var_C4], ecx
0x140067e9a  mov     [rsp+130h+var_D8], cl
0x140067e9e  mov     [rbp+4Fh+var_C8], cl
0x140067ea1  mov     rcx, rsi
0x140067ea4  movups  [rbp+4Fh+FileInformation], xmm0
0x140067ea8  mov     [rbp+4Fh+var_48], rax
0x140067eac  mov     [rbp+4Fh+FileObject], r8
0x140067eb0  mov     [rsp+130h+var_D0], rbx
0x140067eb5  call    HsmpValidateStreamContextNoLock
0x140067eba  mov     ecx, eax
0x140067ebc  mov     edi, eax
0x140067ebe  call    HsmDbgBreakOnStatus
0x140067ec3  xor     edx, edx
0x140067ec5  test    edi, edi
0x140067ec7  js      loc_140068D78
0x140067ecd  mov     eax, [rsi+1Ch]
0x140067ed0  lea     rcx, [r14+20h]
0x140067ed4  mov     [rbp+4Fh+var_C0], rcx
0x140067ed8  mov     r13b, dl
0x140067edb  mov     [rsp+130h+var_D7], dl
0x140067edf  lea     r12, WPP_GLOBAL_Control
0x140067ee6  mov     [rsp+130h+var_D6], dl
0x140067eea  lea     r14d, [rdx+1]
0x140067eee  test    al, 2
0x140067ef0  jnz     loc_140068077
0x140067ef6  mov     rcx, [rcx]; Instance
0x140067ef9  lea     r9d, [rdx+18h]; Length
0x140067efd  mov     [rsp+130h+LengthReturned], rdx; LengthReturned
0x140067f02  lea     r8, [rbp+4Fh+FileInformation]; FileInformation
0x140067f06  mov     rdx, [rbp+4Fh+FileObject]; FileObject
0x140067f0a  mov     [rsp+130h+FileInformationClass], 5; FileInformationClass
0x140067f12  call    cs:__imp_FltQueryInformationFile
0x140067f19  nop     dword ptr [rax+rax+00h]
0x140067f1e  mov     ecx, eax
0x140067f20  mov     edi, eax
0x140067f22  call    HsmDbgBreakOnStatus
0x140067f27  test    edi, edi
0x140067f29  js      loc_14006905A
0x140067f2f  mov     eax, [rsi+1Ch]
0x140067f32  mov     rdx, qword ptr [rbp+4Fh+FileInformation+8]
0x140067f36  test    al, 4
0x140067f38  jnz     loc_1400690C8
0x140067f3e  mov     rcx, rsi
0x140067f41  call    HsmpGetStreamSize
0x140067f46  cmp     rdx, rax
0x140067f49  jl      loc_1400690C8
0x140067f4f  lea     r8, [rbp+4Fh+var_C8]
0x140067f53  mov     edx, 4244h
0x140067f58  mov     rcx, rsi
0x140067f5b  call    HsmiCompactBitmapNoLock
0x140067f60  mov     ecx, eax
0x140067f62  mov     edi, eax
0x140067f64  call    HsmDbgBreakOnStatus
0x140067f69  xor     r9d, r9d
0x140067f6c  test    edi, edi
0x140067f6e  js      loc_140069131
0x140067f74  mov     rcx, rsi
0x140067f77  mov     edi, r9d
0x140067f7a  call    HsmpGetStreamSize
0x140067f7f  mov     r8d, [rsi+1Ch]
0x140067f83  mov     rcx, rax
0x140067f86  mov     [rbp+4Fh+Src], rax
0x140067f8a  mov     rax, [rsi+0A0h]
0x140067f91  shr     r8d, 8
0x140067f95  and     r8d, r14d
0x140067f98  mov     rdx, [rax+40h]
0x140067f9c  test    rdx, rdx
0x140067f9f  jnz     loc_140068BC3
0x140067fa5  mov     ecx, edi
0x140067fa7  call    HsmDbgBreakOnStatus
0x140067fac  xor     r9d, r9d
0x140067faf  test    edi, edi
0x140067fb1  js      loc_140069161
0x140067fb7  mov     rcx, rsi
0x140067fba  mov     edi, r9d
0x140067fbd  call    HsmpGetStreamSize
0x140067fc2  mov     r8d, [rsi+1Ch]
0x140067fc6  mov     rcx, rax
0x140067fc9  mov     [rbp+4Fh+Src], rax
0x140067fcd  mov     rax, [rsi+0A0h]
0x140067fd4  shr     r8d, 0Ah
0x140067fd8  and     r8d, r14d
0x140067fdb  mov     rdx, [rax+48h]
0x140067fdf  test    rdx, rdx
0x140067fe2  jnz     loc_140068C57
0x140067fe8  mov     ecx, edi
0x140067fea  call    HsmDbgBreakOnStatus
0x140067fef  test    edi, edi
0x140067ff1  js      loc_140069191
0x140067ff7  mov     ebx, [rsi+1Ch]
0x140067ffa  mov     edx, 4244h
0x140067fff  shr     ebx, 7
0x140068002  mov     rcx, rsi
0x140068005  and     bl, r14b
0x140068008  or      bl, [rbp+4Fh+var_C8]
0x14006800b  call    HsmiIsBitmapCommitPending
0x140068010  mov     r15b, al
0x140068013  mov     edx, 4256h
0x140068018  or      r15b, bl
0x14006801b  mov     rcx, rsi
0x14006801e  mov     ebx, [rsi+1Ch]
0x140068021  shr     ebx, 9
0x140068024  and     bl, r14b
0x140068027  mov     [rsp+130h+var_D8], r15b
0x14006802c  or      bl, r13b
0x14006802f  call    HsmiIsBitmapCommitPending
0x140068034  mov     r13b, al
0x140068037  mov     edx, 424Dh
0x14006803c  or      r13b, bl
0x14006803f  mov     rcx, rsi
0x140068042  mov     ebx, [rsi+1Ch]
0x140068045  shr     ebx, 0Bh
0x140068048  and     bl, r14b
0x14006804b  mov     [rsp+130h+var_D7], r13b
0x140068050  or      bl, [rsp+130h+var_D6]
0x140068054  call    HsmiIsBitmapCommitPending
0x140068059  mov     rcx, [rbp+4Fh+var_C0]
0x14006805d  or      al, bl
0x14006805f  xor     edx, edx
0x140068061  mov     [rsp+130h+var_D6], al
0x140068065  mov     [rbp+4Fh+var_C0], rcx
0x140068069  cmp     [rbp+4Fh+arg_20], dl
0x14006806c  jnz     loc_140068D5E
0x140068072  mov     rbx, [rsp+130h+var_D0]
0x140068077  mov     r15, [rbp+4Fh+FileObject]
0x14006807b  lea     r8, [rbp+4Fh+var_B0]
0x14006807f  mov     rcx, [rcx]; Instance
0x140068082  mov     rdx, r15; FileObject
0x140068085  call    HsmpRpReadBuffer
0x14006808a  mov     ecx, eax
0x14006808c  mov     edi, eax
0x14006808e  call    HsmDbgBreakOnStatus
0x140068093  mov     r8d, 0C0000275h
0x140068099  cmp     edi, r8d
0x14006809c  jz      loc_1400691BC
0x1400680a2  test    edi, edi
0x1400680a4  js      loc_140069213
0x1400680aa  mov     rcx, [rbp+4Fh+var_B0]
0x1400680ae  mov     [rbp+4Fh+P], rcx
0x1400680b2  mov     eax, [rcx]
0x1400680b4  and     eax, 0FFFF0FFFh
0x1400680b9  cmp     eax, cs:dword_140029670
0x1400680bf  jnz     loc_1400697BC
0x1400680c5  movzx   r15d, word ptr [rcx+4]
0x1400680ca  lea     r13, [rcx+8]
0x1400680ce  mov     edx, r15d
0x1400680d1  mov     rcx, r13
0x1400680d4  call    HsmpRpValidateBuffer
0x1400680d9  mov     ecx, eax
0x1400680db  mov     edi, eax
0x1400680dd  call    HsmDbgBreakOnStatus
0x1400680e2  xor     r10d, r10d
0x1400680e5  test    edi, edi
0x1400680e7  jns     loc_140068227
0x1400680ed  call    HsmDbgBreakOnCorruption
0x1400680f2  cmp     [rsp+130h+var_D5], r10b
0x1400680f7  jz      loc_140069264
0x1400680fd  mov     r13d, r10d
0x140068100  lea     r9d, [r10+4]
0x140068104  mov     ecx, r10d
0x140068107  mov     eax, [rsi+1Ch]
0x14006810a  mov     r11d, 11h
0x140068110  mov     dword ptr [rsp+130h+DataBufferLength], ecx
0x140068114  mov     [rbp+4Fh+var_B0], r10
0x140068118  mov     [rbp+4Fh+var_80], r10
0x14006811c  mov     [rbp+4Fh+Src], r10
0x140068120  test    al, 2
0x140068122  jnz     loc_140068277
0x140068128  mov     r15d, 0C0000225h
0x14006812e  cmp     [rsp+130h+var_D8], r10b
0x140068133  jnz     loc_140068CED
0x140068139  test    r13, r13
0x14006813c  jz      short loc_1400681A5
0x14006813e  cmp     ecx, 18h
0x140068141  jb      short loc_140068194
0x140068143  movzx   eax, word ptr [r13+0Eh]
0x140068148  cmp     r9w, ax
0x14006814c  jnb     short loc_140068194
0x14006814e  mov     r8d, [r13+8]
0x140068152  cmp     r8d, 38h ; '8'
0x140068156  jb      short loc_140068194
0x140068158  movzx   r9d, word ptr [r13+30h]
0x14006815d  cmp     r9w, 12h
0x140068162  jnb     short loc_140068194
0x140068164  mov     edx, [r13+34h]
0x140068168  test    edx, edx
0x14006816a  jz      short loc_14006817E
0x14006816c  lea     rcx, ds:10h[rax*8]
0x140068174  cmp     rdx, rcx
0x140068177  jb      short loc_140068194
0x140068179  cmp     edx, r8d
0x14006817c  ja      short loc_140068194
0x14006817e  movzx   eax, word ptr [r13+32h]
0x140068183  cmp     eax, r8d
0x140068186  ja      short loc_140068194
0x140068188  lea     ecx, [rax+rdx]
0x14006818b  cmp     ecx, r8d
0x14006818e  jbe     loc_140068D80
0x140068194  mov     ecx, r15d
0x140068197  call    HsmDbgBreakOnStatus
0x14006819c  xor     r10d, r10d
0x14006819f  mov     r11d, 11h
0x1400681a5  cmp     [rsp+130h+var_D7], r10b
0x1400681aa  jnz     loc_140068866
0x1400681b0  test    r13, r13
0x1400681b3  jz      loc_14006889D
0x1400681b9  mov     edi, dword ptr [rsp+130h+DataBufferLength]
0x1400681bd  cmp     edi, 18h
0x1400681c0  jb      short loc_140068217
0x1400681c2  movzx   eax, word ptr [r13+0Eh]
0x1400681c7  mov     ecx, 5
0x1400681cc  cmp     cx, ax
0x1400681cf  jnb     short loc_140068217
0x1400681d1  mov     r8d, [r13+8]
0x1400681d5  cmp     r8d, 40h ; '@'
0x1400681d9  jb      short loc_140068217
0x1400681db  movzx   r9d, word ptr [r13+38h]
0x1400681e0  cmp     r9w, 12h
0x1400681e5  jnb     short loc_140068217
0x1400681e7  mov     edx, [r13+3Ch]
0x1400681eb  test    edx, edx
0x1400681ed  jz      short loc_140068201
0x1400681ef  lea     rcx, ds:10h[rax*8]
0x1400681f7  cmp     rdx, rcx
0x1400681fa  jb      short loc_140068217
0x1400681fc  cmp     edx, r8d
0x1400681ff  ja      short loc_140068217
0x140068201  movzx   eax, word ptr [r13+3Ah]
0x140068206  cmp     eax, r8d
0x140068209  ja      short loc_140068217
0x14006820b  lea     ecx, [rax+rdx]
0x14006820e  cmp     ecx, r8d
0x140068211  jbe     loc_140068D29
0x140068217  mov     ecx, r15d
0x14006821a  call    HsmDbgBreakOnStatus
0x14006821f  xor     r10d, r10d
0x140068222  jmp     loc_1400688A1
0x140068227  add     r13, 4
0x14006822b  lea     ecx, [r15-4]
0x14006822f  mov     r9d, 4
0x140068235  cmp     r15d, r9d
0x140068238  ja      loc_140068107
0x14006823e  jmp     loc_140068104
0x140068243  lea     r9, [rbp+4Fh+var_C4]
0x140068247  mov     edx, 424Dh
0x14006824c  lea     r8, [rbp+4Fh+var_60]
0x140068250  mov     rcx, rsi
0x140068253  call    HsmiPrepareBitmapCommit
0x140068258  mov     ecx, eax
0x14006825a  mov     edi, eax
0x14006825c  call    HsmDbgBreakOnStatus
0x140068261  test    edi, edi
0x140068263  js      loc_140068DF1
0x140068269  mov     r8, [rbp+4Fh+var_60]
0x14006826d  mov     eax, [rbp+4Fh+var_C4]
0x140068270  mov     [rbp+4Fh+Src], r8
0x140068274  mov     [rbp+4Fh+var_90], eax
0x140068277  mov     edx, 4000h
0x14006827c  mov     ecx, 100h
0x140068281  mov     r8d, 70527348h
0x140068287  call    cs:__imp_ExAllocatePool2
0x14006828e  nop     dword ptr [rax+rax+00h]
0x140068293  xor     edx, edx; Val
0x140068295  mov     [rsp+130h+DataBuffer], rax
0x14006829a  mov     r15, rax
0x14006829d  test    rax, rax
  ... truncated ...
```
