# HsmFltProcessStoreProperties

- ea: `0x14004a54c`
- end: `0x14004b92b`
- name: `HsmFltProcessStoreProperties`
- size: `5087`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, __int64, __int64, PFLT_CALLBACK_DATA CallbackData, __int64, int, ULONG BytesRead, int)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x14004ded0`

## callees

- `0x140003c50`
- `0x14000abb8`
- `0x14000caf0`
- `0x14000dbd0`
- `0x14004a1b4`
- `0x14004a1e8`
- `0x14004a2c4`
- `0x14004a300`
- `0x14004a54c`
- `0x14004c69c`
- `0x140058cbc`
- `0x14005cf90`
- `0x14007e3b8`

## import_xrefs

- `ntoskrnl!RtlCrc32` at `0x14004a72e`
- `ntoskrnl!RtlCrc32` at `0x14004aa7b`
- `ntoskrnl!RtlCrc32` at `0x14004a72e`
- `ntoskrnl!RtlCrc32` at `0x14004aa7b`
- `ntoskrnl!RtlCompareMemory` at `0x14004ac97`
- `ntoskrnl!RtlCompareMemory` at `0x14004b790`
- `ntoskrnl!RtlCompareMemory` at `0x14004ac97`
- `ntoskrnl!RtlCompareMemory` at `0x14004b790`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004abb1`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004abb1`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004aba5`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004aba5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004ab0a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004b0be`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004b0e1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004b0f5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004b2d9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004b91a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004ab0a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004b0be`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004b0e1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004b0f5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004b2d9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004b91a`
- `ntoskrnl!ExAllocatePool2` at `0x14004a665`
- `ntoskrnl!ExAllocatePool2` at `0x14004a926`
- `ntoskrnl!ExAllocatePool2` at `0x14004adf6`
- `ntoskrnl!ExAllocatePool2` at `0x14004b36b`
- `ntoskrnl!ExAllocatePool2` at `0x14004b649`
- `ntoskrnl!ExAllocatePool2` at `0x14004a665`
- `ntoskrnl!ExAllocatePool2` at `0x14004a926`
- `ntoskrnl!ExAllocatePool2` at `0x14004adf6`
- `ntoskrnl!ExAllocatePool2` at `0x14004b36b`
- `ntoskrnl!ExAllocatePool2` at `0x14004b649`
- `FLTMGR!FltIs32bitProcess` at `0x14004a6e0`
- `FLTMGR!FltIs32bitProcess` at `0x14004a6e0`
- `FLTMGR!FltSetInformationFile` at `0x14004aa2b`
- `FLTMGR!FltSetInformationFile` at `0x14004b85a`
- `FLTMGR!FltSetInformationFile` at `0x14004aa2b`
- `FLTMGR!FltSetInformationFile` at `0x14004b85a`
- `FLTMGR!FltWriteFile` at `0x14004aae6`
- `FLTMGR!FltWriteFile` at `0x14004ad07`
- `FLTMGR!FltWriteFile` at `0x14004ad7d`
- `FLTMGR!FltWriteFile` at `0x14004aae6`
- `FLTMGR!FltWriteFile` at `0x14004ad07`
- `FLTMGR!FltWriteFile` at `0x14004ad7d`
- `FLTMGR!FltReadFile` at `0x14004b6a8`
- `FLTMGR!FltReadFile` at `0x14004b6a8`

## pseudocode

```c
__int64 __fastcall HsmFltProcessStoreProperties(
        SIZE_T a1,
        __int64 a2,
        SIZE_T a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        PFLT_CALLBACK_DATA CallbackData,
        __int64 a9,
        unsigned int a10,
        ULONG BytesRead,
        unsigned int a12)
{
  PDEVICE_OBJECT v14; // r8
  __int64 v15; // r15
  __int64 v16; // rcx
  unsigned int v17; // r8d
  __int64 PropertyStream; // rbx
  __int64 v19; // rdx
  unsigned int i; // r12d
  __int64 v21; // r14
  unsigned int v22; // eax
  __int64 Pool2; // rax
  char *v24; // rsi
  unsigned int v25; // r8d
  PVOID *j; // rcx
  PVOID *v27; // rax
  unsigned __int64 v28; // rbx
  __int64 v29; // rdx
  __int64 v30; // r14
  int v31; // eax
  unsigned int v32; // eax
  __int64 v33; // r14
  SIZE_T v34; // r13
  __int64 v35; // r9
  __int64 v36; // rax
  PVOID *v37; // rbx
  SIZE_T v38; // rcx
  __int64 v39; // rax
  __int64 *v40; // r15
  __int64 v41; // rbx
  unsigned int v42; // edx
  int v43; // r8d
  PVOID *v44; // rcx
  unsigned int v45; // eax
  int v46; // ebx
  unsigned int v47; // r13d
  PVOID *v48; // rdx
  _QWORD *v49; // rcx
  PVOID **v50; // rcx
  unsigned int v51; // ebx
  _BYTE *v52; // rax
  unsigned int v53; // esi
  PVOID *v54; // rbx
  __int64 v55; // r15
  PVOID *v56; // rsi
  struct _FLT_INSTANCE *v57; // r15
  unsigned int v58; // ecx
  PVOID *jj; // rax
  unsigned int v60; // r13d
  void *v61; // rsi
  __int64 v62; // r8
  __int64 v63; // r15
  int v64; // edx
  int v65; // eax
  __int64 v66; // rbx
  __int64 v67; // r8
  PVOID *v68; // rsi
  _QWORD *v69; // r15
  _QWORD *v70; // rsi
  _QWORD *kk; // rcx
  _QWORD *v72; // rsi
  _DWORD *v74; // rax
  int v75; // ecx
  int v76; // eax
  _DWORD *v77; // rdx
  int v78; // r15d
  int v79; // r12d
  SIZE_T v80; // rax
  __int64 v81; // rax
  _DWORD *v82; // rdx
  __int64 v83; // r9
  __int64 ii; // rax
  _QWORD *v85; // rax
  int v86; // eax
  PDEVICE_OBJECT v87; // rcx
  __int64 v88; // rdx
  PVOID *v89; // r8
  __int64 v90; // r9
  _QWORD *v91; // rax
  _QWORD *v92; // rax
  __int64 v93; // rax
  char *v94; // rcx
  char *v95; // rdx
  char *v96; // rcx
  PVOID **v97; // rax
  PVOID *v98; // r9
  PVOID *v99; // r9
  PVOID *v100; // rax
  __int64 **v101; // rax
  __int64 *v102; // rcx
  __int64 *v103; // r9
  PVOID *n; // rcx
  __int64 v105; // rax
  _QWORD *v106; // rax
  PVOID *v107; // rcx
  int v108; // eax
  int v109; // r11d
  __int64 v110; // rcx
  __int64 StreamSize; // rbx
  int v112; // r10d
  __int64 v113; // rcx
  __int64 v114; // rcx
  PVOID *k; // rsi
  PVOID *v116; // rax
  _DWORD *v117; // rdx
  unsigned int v118; // ecx
  __int64 v119; // rax
  _DWORD *v120; // rax
  _DWORD *v121; // rcx
  char v122; // r8
  char v123; // al
  unsigned int v124; // eax
  PVOID *m; // r8
  PVOID *v126; // rcx
  unsigned int v127; // r10d
  PVOID *v128; // r11
  PVOID *v129; // r8
  int v130; // eax
  unsigned int v131; // eax
  PVOID *v132; // r8
  unsigned int v133; // r9d
  PVOID *v134; // rax
  unsigned int v135; // ecx
  PVOID *v136; // rcx
  unsigned int v137; // ecx
  unsigned int v138; // edx
  unsigned int v139; // eax
  __int64 v140; // r8
  int v141; // ecx
  __int64 v142; // rax
  __int64 v143; // r9
  SIZE_T v144; // rbx
  __int64 v145; // rbx
  int v146; // eax
  int v147; // [rsp+60h] [rbp-88h]
  __int64 v148; // [rsp+68h] [rbp-80h]
  PVOID Buffer; // [rsp+70h] [rbp-78h] BYREF
  __int64 Source1; // [rsp+78h] [rbp-70h] BYREF
  union _LARGE_INTEGER ByteOffset; // [rsp+80h] [rbp-68h] BYREF
  PFLT_INSTANCE Instance; // [rsp+88h] [rbp-60h]
  __int64 FileInformation; // [rsp+90h] [rbp-58h] BYREF
  PVOID P[10]; // [rsp+98h] [rbp-50h] BYREF
  SIZE_T v155; // [rsp+F0h] [rbp+8h] BYREF
  __int64 v156; // [rsp+F8h] [rbp+10h]
  SIZE_T v157; // [rsp+100h] [rbp+18h]

  v157 = a3;
  v156 = a2;
  v155 = a1;
  Instance = *(PFLT_INSTANCE *)(a2 + 32);
  ByteOffset.QuadPart = 0;
  BytesRead = 0;
  FileInformation = 0;
  *(_OWORD *)P = 0;
  Buffer = 0;
  Source1 = 0;
  v14 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    if ( a4 )
      v109 = *(_DWORD *)(a4 + 40);
    else
      v109 = 0;
    v110 = a5;
    if ( a5 )
      StreamSize = HsmpGetStreamSize();
    else
      StreamSize = 0;
    if ( v110 )
      v112 = *(_DWORD *)(v110 + 28);
    else
      v112 = 0;
    WPP_SF_qqLiqLiqq(v14->AttachedDevice, 25, v14, a2, v110, v112, StreamSize, a4, v109, a7, a3, CallbackData);
  }
  P[1] = P;
  P[0] = P;
  v15 = a9;
  v16 = *(unsigned int *)(a9 + 16);
  if ( (unsigned int)v16 < 0x20
    || (unsigned int)v16 > a10
    || (v17 = *(_DWORD *)(a9 + 20)) == 0
    || (a10 - (unsigned int)v16) / v17 < 0x18 )
  {
LABEL_174:
    v113 = 3221278475LL;
LABEL_175:
    LODWORD(PropertyStream) = v113;
LABEL_176:
    HsmDbgBreakOnStatus(v113);
    v33 = a6;
    goto LABEL_177;
  }
  LODWORD(PropertyStream) = 0;
  v19 = a9 + v16;
  a9 += v16;
  for ( i = 0; i < *(_DWORD *)(v15 + 20); ++i )
  {
    v21 = v19 + 24LL * i;
    if ( *(_DWORD *)v21 )
    {
      v22 = *(_DWORD *)(v21 + 16);
      if ( v22 > 0x80000 )
      {
        LODWORD(PropertyStream) = -2147430652;
        v113 = 2147536644LL;
        goto LABEL_176;
      }
      Pool2 = ExAllocatePool2(256, 2 * v22 + 88, 1917875016);
      v24 = (char *)Pool2;
      if ( !Pool2 )
      {
        v113 = 3221225626LL;
        goto LABEL_175;
      }
      *(_QWORD *)(Pool2 + 24) = v21;
      v25 = *(_DWORD *)v21;
      *(_DWORD *)(Pool2 + 16) = *(_DWORD *)v21;
      *(_DWORD *)(Pool2 + 20) = *(_DWORD *)(v21 + 16);
      *(_QWORD *)(Pool2 + 40) = Pool2 + 84;
      for ( j = P; ; j = (PVOID *)j[1] )
      {
        v27 = (PVOID *)j[1];
        if ( v27 == P )
          goto LABEL_13;
        if ( v25 >= *((_DWORD *)v27 + 4) )
          break;
      }
      if ( v25 == *((_DWORD *)v27 + 4) )
      {
        ExFreePoolWithTag(v24, 0x72507348u);
        goto LABEL_174;
      }
LABEL_13:
      if ( *v27 != j )
LABEL_93:
        __fastfail(3u);
      *(_QWORD *)v24 = j;
      *((_QWORD *)v24 + 1) = v27;
      *v27 = v24;
      j[1] = v24;
      if ( *((_DWORD *)v24 + 5) )
      {
        v28 = *(_QWORD *)(v21 + 8);
        if ( FltIs32bitProcess(CallbackData) )
          v28 = (unsigned int)v28;
        RtlCopyFromUser(*((void **)v24 + 5), (void *)v28, *((unsigned int *)v24 + 5));
        *((_DWORD *)v24 + 20) = RtlCrc32(*((_QWORD *)v24 + 5), *((unsigned int *)v24 + 5), 0);
        v29 = *((unsigned int *)v24 + 5);
        v30 = v29 + *((_QWORD *)v24 + 5);
        PropertyStream = (unsigned int)HsmiCompressBuffer(
                                         v24 + 80,
                                         (unsigned int)(v29 + 4),
                                         v30,
                                         (((_DWORD)v29 + 3) & 0xFFFFFFFC) - 4,
                                         v24 + 60,
                                         v24 + 56,
                                         v24 + 57);
        HsmDbgBreakOnStatus(PropertyStream);
        if ( (int)PropertyStream >= 0 && v24[56] )
        {
          *((_QWORD *)v24 + 6) = v30;
        }
        else
        {
          *((_QWORD *)v24 + 6) = *((_QWORD *)v24 + 5);
          *((_DWORD *)v24 + 15) = *((_DWORD *)v24 + 5);
        }
      }
      v31 = *((_DWORD *)v24 + 15);
      if ( v31 )
        v32 = (v31 + 11) & 0xFFFFFFFC;
      else
        v32 = 0;
      *((_DWORD *)v24 + 16) = v32;
      v19 = a9;
    }
  }
  v33 = a6;
  if ( P[0] == P
    || (v34 = v157,
        PropertyStream = (unsigned int)HsmpLoadPropertyStream(v156, 1),
        HsmDbgBreakOnStatus(PropertyStream),
        (int)PropertyStream < 0) )
  {
LABEL_177:
    v55 = 0;
    goto LABEL_60;
  }
  v36 = *(_QWORD *)(v33 + 224);
  v148 = v36;
  v155 = v34;
  v37 = (PVOID *)P[0];
  while ( v37 != P )
  {
    LOBYTE(v35) = 1;
    if ( (unsigned __int8)HsmiDoesBlobOperationConflictWithExistingLocks(v36, &v155, *((unsigned int *)v37 + 4), v35) )
    {
      LODWORD(PropertyStream) = -1073688806;
      v114 = 3221278490LL;
LABEL_180:
      HsmDbgBreakOnStatus(v114);
      goto LABEL_106;
    }
    v37 = (PVOID *)*v37;
    v36 = v148;
  }
  v38 = v36 + 64;
  v155 = v36 + 64;
  v39 = v36 + 64;
  while ( 1 )
  {
    v40 = (__int64 *)(v39 + 8);
    v41 = *(_QWORD *)(v39 + 8);
    if ( v41 == v38 )
      break;
    for ( k = P; ; k = (PVOID *)k[1] )
    {
      v116 = (PVOID *)k[1];
      v117 = 0;
      if ( v116 == P )
        break;
      v117 = k[1];
      v118 = *(_DWORD *)(v41 + 16);
      if ( v118 >= *((_DWORD *)v116 + 4) )
      {
        if ( v118 != *((_DWORD *)v116 + 4) )
          v117 = 0;
        break;
      }
    }
    if ( !v117 )
    {
      v119 = ExAllocatePool2(256, 88, 1917875016);
      v117 = (_DWORD *)v119;
      if ( !v119 )
        goto LABEL_179;
      *(_DWORD *)(v119 + 16) = *(_DWORD *)(v41 + 16);
      if ( *(_BYTE *)(v41 + 27) )
        v120 = (_DWORD *)(v41 + 28);
      else
        v120 = (_DWORD *)(v41 + 24);
      v121 = (_DWORD *)(v41 + 24);
      v117[5] = *v120 & 0xFFFFFF;
      v122 = *(_BYTE *)(v41 + 27);
      *((_BYTE *)v117 + 56) = v122;
      if ( *(_BYTE *)(v41 + 27) )
        v123 = *(_BYTE *)(v41 + 31);
      else
        v123 = 0;
      *((_BYTE *)v117 + 57) = v123;
      v117[15] = *v121 & 0xFFFFFF;
      if ( (*v121 & 0xFFFFFF) != 0 )
        v124 = ((*v121 & 0xFFFFFF) + 11) & 0xFFFFFFFC;
      else
        v124 = 0;
      v117[16] = v124;
      if ( !v122 )
        v117[20] = *(_DWORD *)(v41 + 28);
      v97 = (PVOID **)k[1];
      if ( *v97 != k )
        goto LABEL_93;
      *(_QWORD *)v117 = k;
      *((_QWORD *)v117 + 1) = v97;
      *v97 = (PVOID *)v117;
      k[1] = v117;
    }
    *((_QWORD *)v117 + 4) = v41;
    v117[17] = *(_DWORD *)(v41 + 20);
    v39 = *v40;
    v38 = v155;
  }
  v42 = 0;
  a12 = 0;
  v43 = 0;
  v147 = 0;
  v44 = (PVOID *)P[0];
  if ( P[0] != P )
  {
    do
    {
      if ( *((_DWORD *)v44 + 15) )
      {
        ++v42;
        if ( (*((_BYTE *)v44 + 18) & 2) != 0 )
          ++v43;
      }
      v44 = (PVOID *)*v44;
    }
    while ( v44 != P );
    v147 = v43;
    a12 = v42;
  }
  if ( v42 <= 2 )
    v45 = 2;
  else
    v45 = ((v42 - 1) & 0xFFFFFFFE) + 2;
  LODWORD(a9) = v45;
  v46 = 8 * v45;
  v47 = (8 * v45 + 19) & 0xFFFFFFFC;
  LODWORD(v155) = v47;
  v48 = P;
  v49 = P[0];
  if ( P[0] != P )
  {
    v89 = P;
    do
    {
      v90 = v49[4];
      if ( v90 && (*(_DWORD *)(v90 + 24) & 0xFFFFFF) != 0 && *(_DWORD *)(v90 + 20) >= v47 && !v49[3] )
      {
        *((_DWORD *)v49 + 18) = *((_DWORD *)v49 + 17);
        *((_BYTE *)v49 + 76) = 1;
      }
      else
      {
        if ( (PVOID *)v49[1] != v89 )
          goto LABEL_93;
        v91 = (_QWORD *)*v49;
        if ( *(_QWORD **)(*v49 + 8LL) != v49 )
          goto LABEL_93;
        *v89 = v91;
        v91[1] = v89;
        v92 = P[1];
        if ( *(PVOID **)P[1] != P )
          goto LABEL_93;
        *v49 = P;
        v49[1] = v92;
        *v92 = v49;
        P[1] = v49;
        if ( v48 == P )
          v48 = (PVOID *)v49;
        v89 = (PVOID *)v89[1];
      }
      v89 = (PVOID *)*v89;
      v49 = *v89;
    }
    while ( *v89 != v48 );
  }
  v50 = (PVOID **)P[0];
  if ( P[0] == v48 )
    goto LABEL_34;
  v100 = P;
  do
  {
    for ( m = v100; m != P; m = (PVOID *)m[1] )
    {
      if ( *((_DWORD *)v50 + 17) >= *((_DWORD *)m + 17) )
        break;
    }
    if ( m != v100 )
    {
      if ( v50[1] != v100 )
        goto LABEL_93;
      v98 = *v50;
      if ( (*v50)[1] != v50 )
        goto LABEL_93;
      *v100 = v98;
      v98[1] = v100;
      v99 = (PVOID *)*m;
      if ( *((PVOID **)*m + 1) != m )
        goto LABEL_93;
      *v50 = v99;
      v50[1] = m;
      v99[1] = v50;
      *m = v50;
      v100 = (PVOID *)v100[1];
    }
    v100 = (PVOID *)*v100;
    v50 = (PVOID **)*v100;
  }
  while ( *v100 != v48 );
LABEL_34:
  while ( v48 != P )
  {
    v126 = (PVOID *)v48[1];
    if ( v126 == P )
      break;
    v127 = 0;
    v128 = 0;
    do
    {
      v129 = (PVOID *)v126[1];
      v130 = *((_DWORD *)v126 + 18);
      if ( v129 == P )
        v131 = v130 - v47;
      else
        v131 = v130 - *((_DWORD *)v129 + 18) - *((_DWORD *)v129 + 16);
      if ( v131 > v127 )
      {
        v127 = v131;
        v128 = v126;
      }
      v126 = (PVOID *)v126[1];
    }
    while ( v129 != P );
    if ( !v127 )
      break;
    v132 = 0;
    v133 = 0;
    v134 = v48;
    do
    {
      v135 = *((_DWORD *)v134 + 16);
      if ( v135 <= v127 && v135 > v133 )
      {
        v133 = *((_DWORD *)v134 + 16);
        v132 = v134;
      }
      v134 = (PVOID *)*v134;
    }
    while ( v134 != P );
    if ( !v133 )
      break;
    if ( v132 == v48 )
      v48 = (PVOID *)*v48;
    v101 = (__int64 **)v132[1];
    v102 = *v101;
    if ( (__int64 **)(*v101)[1] != v101 )
      goto LABEL_93;
    v103 = (__int64 *)*v102;
    if ( *(__int64 **)(*v102 + 8) != v102 )
      goto LABEL_93;
    *v101 = v103;
    v103[1] = (__int64)v101;
    for ( n = (PVOID *)v128[1];
          n != P && !*((_BYTE *)n + 76) && *((_DWORD *)v132 + 4) < *((_DWORD *)n + 4);
          n = (PVOID *)n[1] )
    {
      *((_DWORD *)n + 18) += *((_DWORD *)v132 + 16);
    }
    v106 = *n;
    if ( *((PVOID **)*n + 1) != n )
      goto LABEL_93;
    *v132 = v106;
    v132[1] = n;
    v106[1] = v132;
    *n = v132;
    v107 = (PVOID *)v132[1];
    if ( v107 == P )
      v108 = v47;
    else
      v108 = *((_DWORD *)v107 + 16) + *((_DWORD *)v107 + 18);
    *((_DWORD *)v132 + 18) = v108;
  }
  while ( v48 != P )
  {
    if ( *((_DWORD *)v48 + 15) )
    {
      v136 = (PVOID *)v48[1];
      if ( v136 == P )
        *((_DWORD *)v48 + 18) = v47;
      else
        *((_DWORD *)v48 + 18) = *((_DWORD *)v136 + 16) + *((_DWORD *)v136 + 18);
    }
    v48 = (PVOID *)*v48;
  }
  v51 = v46 + 16;
  v52 = (_BYTE *)ExAllocatePool2(256, v51, 1917875016);
  Buffer = v52;
  if ( !v52 )
  {
LABEL_179:
    v114 = 3221225626LL;
    LODWORD(PropertyStream) = -1073741670;
    goto LABEL_180;
  }
  *v52 = 2;
  *((_BYTE *)Buffer + 1) = 0;
  *((_WORD *)Buffer + 1) = v51;
  v53 = 0;
  v54 = (PVOID *)P[0];
  v55 = v148;
  while ( v54 != P )
  {
    if ( *((_DWORD *)v54 + 15) )
    {
      if ( !v54[4] )
      {
        v81 = ExAllocatePool2(256, 40, 1917875016);
        if ( !v81 )
        {
          LODWORD(PropertyStream) = -1073741670;
          HsmDbgBreakOnStatus(3221225626LL);
          goto LABEL_60;
        }
        *(_DWORD *)(v81 + 16) = *((_DWORD *)v54 + 4);
        HsmiLookupPropertyLockForBlob(v148, v81);
        v83 = v148 + 64;
        for ( ii = *(_QWORD *)(v148 + 72); ii != v148 + 64; ii = *(_QWORD *)(ii + 8) )
        {
          if ( v82[4] >= *(_DWORD *)(ii + 16) )
            break;
          v83 = ii;
        }
        v85 = *(_QWORD **)(v83 + 8);
        if ( *v85 != v83 )
          goto LABEL_93;
        *(_QWORD *)v82 = v83;
        *((_QWORD *)v82 + 1) = v85;
        *v85 = v82;
        *(_QWORD *)(v83 + 8) = v82;
        v54[4] = v82;
      }
      *((_DWORD *)Buffer + 2 * v53 + 4) = *((_DWORD *)v54 + 4);
      *((_DWORD *)Buffer + 2 * v53++ + 5) = *((_DWORD *)v54 + 18);
    }
    v54 = (PVOID *)*v54;
  }
  v56 = (PVOID *)P[0];
  v57 = Instance;
  while ( v56 != P )
  {
    if ( v56[4] )
    {
      if ( *((_DWORD *)v56 + 15) )
      {
        v86 = *((_DWORD *)v56 + 17);
        if ( v86 )
        {
          if ( *((_DWORD *)v56 + 18) != v86 && !v56[3] )
          {
            v137 = 0;
            v138 = 0;
            v139 = *(_DWORD *)(v148 + 60);
            while ( v138 < v139 )
            {
              v140 = *(_QWORD *)(v148 + 48);
              if ( *(_DWORD *)(v140 + 8LL * v138) == *((_DWORD *)v56 + 4) )
              {
                if ( v138 == v139 - 1 )
                  v141 = *(_DWORD *)(*(_QWORD *)(v148 + 40) + 8LL) + *(_DWORD *)(*(_QWORD *)(v148 + 40) + 12LL);
                else
                  v141 = *(_DWORD *)(v140 + 8LL * (v138 + 1) + 4);
                v137 = v141 - *(_DWORD *)(v140 + 8LL * v138 + 4);
                break;
              }
              ++v138;
            }
            v142 = ExAllocatePool2(256, v137, 1917875016);
            v56[6] = (PVOID)v142;
            if ( !v142 )
              goto LABEL_179;
            ByteOffset.QuadPart = *((unsigned int *)v56 + 17) + 8LL;
            PropertyStream = (unsigned int)FltReadFile(
                                             v57,
                                             *(PFILE_OBJECT *)(v148 + 24),
                                             &ByteOffset,
                                             *((_DWORD *)v56 + 15),
                                             v56[6],
                                             0,
                                             &BytesRead,
                                             0,
                                             0);
            HsmDbgBreakOnStatus(PropertyStream);
            if ( (int)PropertyStream < 0 )
            {
              v87 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
                || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
              {
                goto LABEL_106;
              }
              v88 = 26;
LABEL_263:
              v143 = v156;
LABEL_264:
              WPP_SF_qqqd(
                v87->AttachedDevice,
                v88,
                WPP_7aae8ba2065034a53a58944ee54ad7f8_Traceguids,
                v143,
                v33,
                *(_QWORD *)(v33 + 32),
                PropertyStream);
              goto LABEL_106;
            }
          }
        }
      }
    }
    v56 = (PVOID *)*v56;
  }
  v58 = 0;
  for ( jj = (PVOID *)P[1]; jj != P; jj = (PVOID *)jj[1] )
  {
    if ( jj[4] && *((_DWORD *)jj + 15) )
    {
      v58 = *((_DWORD *)jj + 16) + *((_DWORD *)jj + 18) - v47;
      break;
    }
  }
  v60 = v58 + v47;
  v61 = (void *)(v148 + 40);
  v62 = *(_QWORD *)(v148 + 40);
  v63 = v156;
  if ( (*(_BYTE *)(v62 + 1) & 1) != 0 || v60 >= *(_DWORD *)(v156 + 92) )
  {
    if ( (*(_BYTE *)(v62 + 1) & 1) == 0 )
      *(_BYTE *)(v62 + 1) |= 1u;
    v60 = -*(_DWORD *)(v63 + 84) & (*(_DWORD *)(v63 + 84) + v60 - 1);
    v64 = v155;
    v58 = v60 - v155;
  }
  else
  {
    v64 = v155;
  }
  *((_DWORD *)Buffer + 2) = v64;
  *((_DWORD *)Buffer + 3) = v58;
  if ( v60 <= *(_DWORD *)(v148 + 32) )
  {
    v55 = v148;
  }
  else
  {
    FileInformation = v60;
    PropertyStream = (unsigned int)FltSetInformationFile(
                                     Instance,
                                     *(PFILE_OBJECT *)(v148 + 24),
                                     &FileInformation,
                                     8u,
                                     FileEndOfFileInformation);
    HsmDbgBreakOnStatus(PropertyStream);
    if ( (int)PropertyStream < 0 )
    {
      v87 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_106;
      }
      v88 = 27;
      v143 = v63;
      goto LABEL_264;
    }
    v65 = FileInformation;
    v55 = v148;
    *(_DWORD *)(v148 + 32) = FileInformation;
    *(_DWORD *)(v33 + 236) = v65;
    *(_BYTE *)(v33 + 232) = 1;
  }
  *((_DWORD *)Buffer + 1) = RtlCrc32(Buffer, *((unsigned __int16 *)Buffer + 1), 0);
  if ( *((_WORD *)Buffer + 1) == *(_WORD *)(*(_QWORD *)v61 + 2LL)
    && (v144 = *((unsigned __int16 *)Buffer + 1), RtlCompareMemory(&Buffer, v61, v144) == v144) )
  {
    v66 = v148;
  }
  else
  {
    ByteOffset.QuadPart = 0;
    LODWORD(PropertyStream) = FltWriteFile(
                                Instance,
                                *(PFILE_OBJECT *)(v55 + 24),
                                &ByteOffset,
                                *((unsigned __int16 *)Buffer + 1),
                                Buffer,
                                0,
                                &BytesRead,
                                0,
                                0);
    if ( (int)PropertyStream < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_qqqd(
          WPP_GLOBAL_Control->AttachedDevice,
          28,
          WPP_7aae8ba2065034a53a58944ee54ad7f8_Traceguids,
          v156,
          v33,
          *(_QWORD *)(v33 + 32),
          PropertyStream);
      }
      goto LABEL_60;
    }
    v66 = v148;
    ExFreePoolWithTag(*(PVOID *)(v148 + 40), 0x72507348u);
    *(_QWORD *)v61 = Buffer;
    Buffer = 0;
    *(_QWORD *)(v148 + 48) = *(_QWORD *)v61 + 16LL;
    *(_DWORD *)(v148 + 56) = a9;
    *(_DWORD *)(v148 + 60) = a12;
  }
  v68 = (PVOID *)P[0];
  while ( 1 )
  {
    if ( v68 == P )
    {
      if ( v60 < *(_DWORD *)(v66 + 32) )
      {
        FileInformation = v60;
        v145 = (unsigned int)FltSetInformationFile(
                               Instance,
                               *(PFILE_OBJECT *)(v66 + 24),
                               &FileInformation,
                               8u,
                               FileEndOfFileInformation);
        HsmDbgBreakOnStatus(v145);
        if ( (int)v145 >= 0 )
        {
          v146 = FileInformation;
          v55 = v148;
          *(_DWORD *)(v148 + 32) = FileInformation;
          *(_DWORD *)(v33 + 236) = v146;
          *(_BYTE *)(v33 + 232) = 1;
          goto LABEL_57;
        }
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
        {
          WPP_SF_qqqd(
            WPP_GLOBAL_Control->AttachedDevice,
            31,
            WPP_7aae8ba2065034a53a58944ee54ad7f8_Traceguids,
            v156,
            v33,
            *(_QWORD *)(v33 + 32),
            v145);
        }
      }
      v55 = v148;
LABEL_57:
      if ( a5 )
      {
        LOBYTE(v67) = v147 != 0;
        HsmpPersistEssentialPropPresent(a5, v157, v67);
      }
      CallbackData->IoStatus.Information = 0;
      LODWORD(PropertyStream) = 0;
      goto LABEL_60;
    }
    v74 = v68[4];
    if ( v74 )
    {
      if ( (v74[6] & 0xFFFFFF) != 0 )
        break;
    }
    if ( *((_DWORD *)v68 + 15) )
      break;
LABEL_81:
    v68 = (PVOID *)*v68;
    v66 = v148;
  }
  LODWORD(Source1) = Source1 & 0xFF000000 | *((_DWORD *)v68 + 15) & 0xFFFFFF;
  v75 = *((unsigned __int8 *)v68 + 56);
  LODWORD(Source1) = Source1 & 0xFFFFFF | (v75 << 24);
  if ( v75 )
  {
    HIDWORD(Source1) = HIDWORD(Source1) & 0xFF000000 | *((_DWORD *)v68 + 5) & 0xFFFFFF;
    v76 = HIDWORD(Source1) & 0xFFFFFF | (*((unsigned __int8 *)v68 + 57) << 24);
  }
  else
  {
    v76 = *((_DWORD *)v68 + 20);
  }
  HIDWORD(Source1) = v76;
  v77 = v68[4];
  v78 = *((_DWORD *)v68 + 18);
  v79 = v77[5];
  v80 = RtlCompareMemory(&Source1, v77 + 6, 8u);
  v155 = v80;
  if ( !*((_DWORD *)v68 + 15) )
    goto LABEL_77;
  if ( v78 != v79 || v80 != 8 )
  {
    ByteOffset.QuadPart = *((unsigned int *)v68 + 18);
    PropertyStream = (unsigned int)FltWriteFile(
                                     Instance,
                                     *(PFILE_OBJECT *)(v66 + 24),
                                     &ByteOffset,
                                     8u,
                                     &Source1,
                                     0,
                                     &BytesRead,
                                     0,
                                     0);
    HsmDbgBreakOnStatus(PropertyStream);
    if ( (int)PropertyStream < 0 )
    {
      v87 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        v88 = 29;
        goto LABEL_263;
      }
      goto LABEL_106;
    }
  }
  if ( v78 == v79 && !v68[3]
    || (ByteOffset.QuadPart = *((unsigned int *)v68 + 18) + 8LL,
        PropertyStream = (unsigned int)FltWriteFile(
                                         Instance,
                                         *(PFILE_OBJECT *)(v148 + 24),
                                         &ByteOffset,
                                         *((_DWORD *)v68 + 15),
                                         v68[6],
                                         0,
                                         &BytesRead,
                                         0,
                                         0),
        HsmDbgBreakOnStatus(PropertyStream),
        (int)PropertyStream >= 0) )
  {
LABEL_77:
    if ( v78 != v79 )
      *((_DWORD *)v68[4] + 5) = *((_DWORD *)v68 + 18);
    if ( v155 != 8 )
      *((_QWORD *)v68[4] + 3) = Source1;
    goto LABEL_81;
  }
  v87 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    v88 = 30;
    goto LABEL_263;
  }
LABEL_106:
  v55 = v148;
LABEL_60:
  if ( !v55 )
    goto LABEL_64;
  v69 = (_QWORD *)(v55 + 64);
  v70 = v69;
  for ( kk = (_QWORD *)*v69; kk != v69; kk = (_QWORD *)*v70 )
  {
    if ( (kk[3] & 0xFFFFFF) == 0 )
    {
      if ( (_QWORD *)kk[1] != v70 )
        goto LABEL_93;
      v105 = *kk;
      if ( *(_QWORD **)(*kk + 8LL) != kk )
        goto LABEL_93;
      *v70 = v105;
      *(_QWORD *)(v105 + 8) = v70;
      HsmiFreePropertyBlob();
      v70 = (_QWORD *)v70[1];
    }
    v70 = (_QWORD *)*v70;
  }
  ExReleaseResourceLite((PERESOURCE)(v33 + 120));
  KeLeaveCriticalRegion();
LABEL_64:
  while ( 1 )
  {
    v72 = P[0];
    if ( P[0] == P )
      break;
    if ( *((PVOID **)P[0] + 1) != P )
      goto LABEL_93;
    v93 = *(_QWORD *)P[0];
    if ( *(PVOID *)(*(_QWORD *)P[0] + 8LL) != P[0] )
      goto LABEL_93;
    P[0] = *(PVOID *)P[0];
    *(_QWORD *)(v93 + 8) = P;
    v94 = (char *)v72[6];
    if ( v94 )
    {
      v95 = (char *)v72[5];
      if ( !v95 || v94 != v95 && v94 != &v95[*((unsigned int *)v72 + 5)] )
        ExFreePoolWithTag(v94, 0x72507348u);
    }
    v96 = (char *)v72[5];
    if ( v96 && v96 != (char *)v72 + 84 )
      ExFreePoolWithTag(v96, 0x72507348u);
    ExFreePoolWithTag(v72, 0x72507348u);
  }
  if ( Buffer )
    ExFreePoolWithTag(Buffer, 0x72507348u);
  HsmpUnloadPropertyStream(v33);
  return (unsigned int)PropertyStream;
}

```

## disassembly

```asm
0x14004a54c  mov     r11, rsp
0x14004a54f  mov     [r11+18h], r8
0x14004a553  mov     [r11+10h], rdx
0x14004a557  mov     [r11+8], rcx
0x14004a55b  push    rbx
0x14004a55c  push    rsi
0x14004a55d  push    rdi
0x14004a55e  push    r12
0x14004a560  push    r13
0x14004a562  push    r14
0x14004a564  push    r15
0x14004a566  sub     rsp, 0B0h
0x14004a56d  mov     r13, r8
0x14004a570  mov     rsi, rdx
0x14004a573  mov     rax, [rdx+20h]
0x14004a577  mov     [rsp+0E8h+Instance], rax
0x14004a57f  xor     edi, edi
0x14004a581  mov     [r11-68h], rdi
0x14004a585  mov     [r11+58h], edi
0x14004a589  mov     [r11-58h], rdi
0x14004a58d  xorps   xmm0, xmm0
0x14004a590  movups  xmmword ptr [r11-50h], xmm0
0x14004a595  mov     [r11-78h], rdi
0x14004a599  mov     [r11-70h], rdi
0x14004a59d  lea     rax, WPP_GLOBAL_Control
0x14004a5a4  mov     r8, cs:WPP_GLOBAL_Control
0x14004a5ab  cmp     r8, rax
0x14004a5ae  jnz     loc_14004B20F
0x14004a5b4  lea     rax, [rsp+0E8h+P]
0x14004a5bc  mov     [rsp+0E8h+var_48], rax
0x14004a5c4  lea     rax, [rsp+0E8h+P]
0x14004a5cc  mov     [rsp+0E8h+P], rax
0x14004a5d4  mov     r15, [rsp+0E8h+arg_40]
0x14004a5dc  mov     ecx, [r15+10h]
0x14004a5e0  cmp     ecx, 20h ; ' '
0x14004a5e3  jb      loc_14004B2E5
0x14004a5e9  mov     eax, [rsp+0E8h+arg_48]
0x14004a5f0  cmp     ecx, eax
0x14004a5f2  ja      loc_14004B2E5
0x14004a5f8  mov     r8d, [r15+14h]
0x14004a5fc  test    r8d, r8d
0x14004a5ff  jz      loc_14004B2E5
0x14004a605  sub     eax, ecx
0x14004a607  xor     edx, edx
0x14004a609  div     r8d
0x14004a60c  cmp     eax, 18h
0x14004a60f  jb      loc_14004B2E5
0x14004a615  mov     ebx, edi
0x14004a617  lea     rdx, [r15+rcx]
0x14004a61b  mov     [rsp+0E8h+arg_40], rdx
0x14004a623  mov     r12d, edi
0x14004a626  cmp     r12d, [r15+14h]
0x14004a62a  jnb     loc_14004A7C0
0x14004a630  mov     eax, r12d
0x14004a633  lea     rcx, [rax+rax*2]
0x14004a637  lea     r14, [rdx+rcx*8]
0x14004a63b  cmp     [r14], edi
0x14004a63e  jz      loc_14004A7B8
0x14004a644  mov     eax, [r14+10h]
0x14004a648  cmp     eax, 80000h
0x14004a64d  ja      loc_14004B2AD
0x14004a653  lea     edx, ds:58h[rax*2]
0x14004a65a  mov     ecx, 100h
0x14004a65f  mov     r8d, 72507348h
0x14004a665  call    cs:__imp_ExAllocatePool2
0x14004a66c  nop     dword ptr [rax+rax+00h]
0x14004a671  mov     rsi, rax
0x14004a674  test    rax, rax
0x14004a677  jz      loc_14004B2B6
0x14004a67d  mov     [rax+18h], r14
0x14004a681  mov     r8d, [r14]
0x14004a684  mov     [rax+10h], r8d
0x14004a688  mov     eax, [r14+10h]
0x14004a68c  mov     [rsi+14h], eax
0x14004a68f  lea     rax, [rsi+54h]
0x14004a693  mov     [rsi+28h], rax
0x14004a697  lea     rcx, [rsp+0E8h+P]
0x14004a69f  mov     rax, [rcx+8]
0x14004a6a3  lea     rdx, [rsp+0E8h+P]
0x14004a6ab  cmp     rax, rdx
0x14004a6ae  jnz     loc_14004B2BD
0x14004a6b4  cmp     [rax], rcx
0x14004a6b7  jnz     loc_14004AE82
0x14004a6bd  mov     [rsi], rcx
0x14004a6c0  mov     [rsi+8], rax
0x14004a6c4  mov     [rax], rsi
0x14004a6c7  mov     [rcx+8], rsi
0x14004a6cb  cmp     [rsi+14h], edi
0x14004a6ce  jz      loc_14004A79C
0x14004a6d4  mov     rbx, [r14+8]
0x14004a6d8  mov     rcx, [rsp+0E8h+CallbackData]; CallbackData
0x14004a6e0  call    cs:__imp_FltIs32bitProcess
0x14004a6e7  nop     dword ptr [rax+rax+00h]
0x14004a6ec  test    al, al
0x14004a6ee  jnz     loc_14004B301
0x14004a6f4  mov     r8d, [rsi+14h]; Size
0x14004a6f8  mov     rdx, rbx; Src
0x14004a6fb  mov     rcx, [rsi+28h]; void *
0x14004a6ff  call    RtlCopyFromUser
0x14004a704  jmp     short loc_14004A724
0x14004a706  mov     ebx, 0C00000E8h
0x14004a70b  mov     ecx, ebx
0x14004a70d  call    HsmDbgBreakOnStatus
0x14004a712  xor     edi, edi
0x14004a714  mov     r14, [rsp+0E8h+arg_28]
0x14004a71c  mov     r15d, edi
0x14004a71f  jmp     loc_14004AB89
0x14004a724  mov     edx, [rsi+14h]
0x14004a727  xor     r8d, r8d
0x14004a72a  mov     rcx, [rsi+28h]
0x14004a72e  call    cs:__imp_RtlCrc32
0x14004a735  nop     dword ptr [rax+rax+00h]
0x14004a73a  mov     [rsi+50h], eax
0x14004a73d  mov     edx, [rsi+14h]
0x14004a740  mov     r14, [rsi+28h]
0x14004a744  add     r14, rdx
0x14004a747  lea     r13, [rsi+38h]
0x14004a74b  lea     rcx, [rsi+3Ch]
0x14004a74f  lea     rax, [rsi+39h]
0x14004a753  lea     r9d, [rdx+3]
0x14004a757  and     r9d, 0FFFFFFFCh
0x14004a75b  sub     r9d, 4
0x14004a75f  add     edx, 4
0x14004a762  mov     [rsp+0E8h+BytesWritten], rax
0x14004a767  mov     qword ptr [rsp+0E8h+Flags], r13
0x14004a76c  mov     qword ptr [rsp+0E8h+FileInformationClass], rcx
0x14004a771  mov     r8, r14
0x14004a774  lea     rcx, [rsi+50h]
0x14004a778  call    HsmiCompressBuffer
0x14004a77d  mov     ebx, eax
0x14004a77f  mov     ecx, eax
0x14004a781  call    HsmDbgBreakOnStatus
0x14004a786  test    ebx, ebx
0x14004a788  jns     loc_14004AEBC
0x14004a78e  mov     rax, [rsi+28h]
0x14004a792  mov     [rsi+30h], rax
0x14004a796  mov     eax, [rsi+14h]
0x14004a799  mov     [rsi+3Ch], eax
0x14004a79c  mov     eax, [rsi+3Ch]
0x14004a79f  test    eax, eax
0x14004a7a1  jz      loc_14004AF1F
0x14004a7a7  add     eax, 0Bh
0x14004a7aa  and     eax, 0FFFFFFFCh
0x14004a7ad  mov     [rsi+40h], eax
0x14004a7b0  mov     rdx, [rsp+0E8h+arg_40]
0x14004a7b8  inc     r12d
0x14004a7bb  jmp     loc_14004A626
0x14004a7c0  lea     rax, [rsp+0E8h+P]
0x14004a7c8  mov     r14, [rsp+0E8h+arg_28]
0x14004a7d0  cmp     [rsp+0E8h+P], rax
0x14004a7d8  jz      loc_14004B2F9
0x14004a7de  mov     r12d, 1
0x14004a7e4  mov     byte ptr [rsp+0E8h+FileInformationClass], r12b; char
0x14004a7e9  mov     r9, r14
0x14004a7ec  mov     r13, [rsp+0E8h+arg_10]
0x14004a7f4  mov     r8, r13
0x14004a7f7  mov     rdx, [rsp+0E8h+arg_20]
0x14004a7ff  mov     rcx, [rsp+0E8h+arg_8]; int
0x14004a807  call    HsmpLoadPropertyStream
0x14004a80c  mov     ebx, eax
0x14004a80e  mov     ecx, eax
0x14004a810  call    HsmDbgBreakOnStatus
0x14004a815  test    ebx, ebx
0x14004a817  js      loc_14004B2F9
0x14004a81d  mov     rax, [r14+0E0h]
0x14004a824  mov     [rsp+0E8h+var_80], rax
0x14004a829  mov     [rsp+0E8h+arg_0], r13
0x14004a831  mov     rbx, [rsp+0E8h+P]
0x14004a839  lea     rcx, [rsp+0E8h+P]
0x14004a841  cmp     rbx, rcx
0x14004a844  jnz     loc_14004AF26
0x14004a84a  lea     rcx, [rax+40h]
0x14004a84e  mov     [rsp+0E8h+arg_0], rcx
0x14004a856  mov     rax, rcx
0x14004a859  lea     r15, [rax+8]
0x14004a85d  mov     rbx, [r15]
0x14004a860  cmp     rbx, rcx
0x14004a863  jnz     loc_14004B322
0x14004a869  mov     edx, edi
0x14004a86b  mov     [rsp+0E8h+arg_58], edx
0x14004a872  mov     r8d, edi
0x14004a875  mov     [rsp+0E8h+var_88], edi
0x14004a879  mov     rcx, [rsp+0E8h+P]
0x14004a881  lea     rax, [rsp+0E8h+P]
0x14004a889  cmp     rcx, rax
0x14004a88c  jnz     loc_14004B3F3
0x14004a892  cmp     edx, 2
0x14004a895  jbe     loc_14004AE89
0x14004a89b  lea     eax, [rdx-1]
0x14004a89e  and     eax, 0FFFFFFFEh
0x14004a8a1  add     eax, 2
0x14004a8a4  mov     dword ptr [rsp+0E8h+arg_40], eax
0x14004a8ab  lea     ebx, ds:0[rax*8]
0x14004a8b2  lea     r13d, [rbx+13h]
0x14004a8b6  and     r13d, 0FFFFFFFCh
0x14004a8ba  mov     dword ptr [rsp+0E8h+arg_0], r13d
0x14004a8c2  lea     rdx, [rsp+0E8h+P]
0x14004a8ca  mov     rcx, [rsp+0E8h+P]
0x14004a8d2  lea     rax, [rsp+0E8h+P]
0x14004a8da  cmp     rcx, rax
0x14004a8dd  jnz     loc_14004AFE9
0x14004a8e3  mov     rcx, [rsp+0E8h+P]
0x14004a8eb  cmp     rcx, rdx
0x14004a8ee  jnz     loc_14004B459
0x14004a8f4  lea     rax, [rsp+0E8h+P]
0x14004a8fc  cmp     rdx, rax
0x14004a8ff  jnz     loc_14004B4A5
0x14004a905  lea     rax, [rsp+0E8h+P]
0x14004a90d  cmp     rdx, rax
0x14004a910  jnz     loc_14004AF0E
0x14004a916  add     ebx, 10h
0x14004a919  mov     edx, ebx
0x14004a91b  mov     ecx, 100h
0x14004a920  mov     r8d, 72507348h
0x14004a926  call    cs:__imp_ExAllocatePool2
0x14004a92d  nop     dword ptr [rax+rax+00h]
0x14004a932  mov     [rsp+0E8h+Buffer], rax
0x14004a937  test    rax, rax
0x14004a93a  jz      loc_14004B311
0x14004a940  mov     byte ptr [rax], 2
0x14004a943  mov     rax, [rsp+0E8h+Buffer]
0x14004a948  mov     [rax+1], dil
0x14004a94c  mov     rax, [rsp+0E8h+Buffer]
0x14004a951  mov     [rax+2], bx
0x14004a955  mov     esi, edi
0x14004a957  mov     rbx, [rsp+0E8h+P]
0x14004a95f  mov     r15, [rsp+0E8h+var_80]
0x14004a964  lea     rax, [rsp+0E8h+P]
0x14004a96c  cmp     rbx, rax
0x14004a96f  jnz     loc_14004ADD7
0x14004a975  mov     rsi, [rsp+0E8h+P]
0x14004a97d  mov     r15, [rsp+0E8h+Instance]
0x14004a985  lea     rax, [rsp+0E8h+P]
0x14004a98d  cmp     rsi, rax
0x14004a990  jnz     loc_14004AECF
0x14004a996  mov     ecx, edi
0x14004a998  mov     rax, [rsp+0E8h+var_48]
0x14004a9a0  lea     rdx, [rsp+0E8h+P]
0x14004a9a8  cmp     rax, rdx
0x14004a9ab  jnz     loc_14004AE93
0x14004a9b1  add     r13d, ecx
0x14004a9b4  mov     r10, [rsp+0E8h+var_80]
0x14004a9b9  lea     rsi, [r10+28h]
0x14004a9bd  mov     r8, [rsi]
0x14004a9c0  mov     al, [r8+1]
0x14004a9c4  mov     dl, al
0x14004a9c6  and     dl, r12b
0x14004a9c9  mov     r15, [rsp+0E8h+arg_8]
0x14004a9d1  jnz     loc_14004B740
0x14004a9d7  cmp     r13d, [r15+5Ch]
0x14004a9db  jnb     loc_14004B740
0x14004a9e1  mov     edx, dword ptr [rsp+0E8h+arg_0]
0x14004a9e8  mov     rax, [rsp+0E8h+Buffer]
0x14004a9ed  mov     [rax+8], edx
0x14004a9f0  mov     rax, [rsp+0E8h+Buffer]
0x14004a9f5  mov     [rax+0Ch], ecx
0x14004a9f8  cmp     r13d, [r10+20h]
0x14004a9fc  jbe     short loc_14004AA69
0x14004a9fe  mov     eax, r13d
0x14004aa01  mov     [rsp+0E8h+FileInformation], rax
0x14004aa09  mov     [rsp+0E8h+FileInformationClass], 14h; FileInformationClass
0x14004aa11  mov     r9d, 8; Length
0x14004aa17  lea     r8, [rsp+0E8h+FileInformation]; FileInformation
0x14004aa1f  mov     rdx, [r10+18h]; FileObject
0x14004aa23  mov     rcx, [rsp+0E8h+Instance]; Instance
0x14004aa2b  call    cs:__imp_FltSetInformationFile
0x14004aa32  nop     dword ptr [rax+rax+00h]
0x14004aa37  mov     ebx, eax
0x14004aa39  mov     ecx, eax
0x14004aa3b  call    HsmDbgBreakOnStatus
0x14004aa40  test    ebx, ebx
0x14004aa42  js      loc_14004AEED
0x14004aa48  mov     rax, [rsp+0E8h+FileInformation]
0x14004aa50  mov     r15, [rsp+0E8h+var_80]
0x14004aa55  mov     [r15+20h], eax
0x14004aa59  mov     [r14+0ECh], eax
0x14004aa60  mov     [r14+0E8h], r12b
0x14004aa67  jmp     short loc_14004AA6C
0x14004aa69  mov     r15, r10
0x14004aa6c  mov     rbx, [rsp+0E8h+Buffer]
0x14004aa71  movzx   edx, word ptr [rbx+2]
0x14004aa75  xor     r8d, r8d
0x14004aa78  mov     rcx, rbx
0x14004aa7b  call    cs:__imp_RtlCrc32
0x14004aa82  nop     dword ptr [rax+rax+00h]
0x14004aa87  mov     [rbx+4], eax
0x14004aa8a  mov     rax, [rsp+0E8h+Buffer]
0x14004aa8f  movzx   ecx, word ptr [rax+2]
0x14004aa93  mov     rax, [rsi]
0x14004aa96  cmp     cx, [rax+2]
0x14004aa9a  jz      loc_14004B782
0x14004aaa0  mov     qword ptr [rsp+0E8h+ByteOffset], rdi
0x14004aaa8  mov     rax, [rsp+0E8h+Buffer]
0x14004aaad  movzx   r9d, word ptr [rax+2]; Length
0x14004aab2  mov     [rsp+0E8h+CallbackContext], rdi; CallbackContext
0x14004aab7  mov     [rsp+0E8h+CallbackRoutine], rdi; CallbackRoutine
0x14004aabc  lea     rcx, [rsp+0E8h+BytesRead]
0x14004aac4  mov     [rsp+0E8h+BytesWritten], rcx; BytesWritten
0x14004aac9  mov     [rsp+0E8h+Flags], edi; Flags
0x14004aacd  mov     qword ptr [rsp+0E8h+FileInformationClass], rax; Buffer
  ... truncated ...
```
