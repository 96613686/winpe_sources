# UlCaptureHttpResponse

- ea: `0x1c00bbfe0`
- end: `0x1c00bdf84`
- name: `UlCaptureHttpResponse`
- size: `8100`
- prototype: ``
- caller_count: `3`
- callee_count: `40`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1c002fbd8`
- `0x1c00b4cf0`
- `0x1c011bcd0`

## callees

- `0x1c0001118`
- `0x1c0001ae0`
- `0x1c0002c80`
- `0x1c000b210`
- `0x1c000b280`
- `0x1c000b640`
- `0x1c00102d0`
- `0x1c0011e5c`
- `0x1c0014b1c`
- `0x1c0016148`
- `0x1c001709c`
- `0x1c001a4b0`
- `0x1c001a8ac`
- `0x1c001b610`
- `0x1c001b640`
- `0x1c001b900`
- `0x1c00351c4`
- `0x1c0047754`
- `0x1c004d2d4`
- `0x1c008f21c`
- `0x1c008f2ac`
- `0x1c008f30c`
- `0x1c008f374`
- `0x1c008f3a8`
- `0x1c008f570`
- `0x1c008fd84`
- `0x1c009ad5c`
- `0x1c009d8fc`
- `0x1c00b8520`
- `0x1c00b89b4`
- `0x1c00b8ae0`
- `0x1c00bbfe0`
- `0x1c00bdf90`
- `0x1c00be3f0`
- `0x1c00d05c0`
- `0x1c00d2320`
- `0x1c00d6070`
- `0x1c00d60c4`
- `0x1c012992c`
- `0x1c0145714`

## import_xrefs

- `ntoskrnl!IoAllocateMdl` at `0x1c00bdd8a`
- `ntoskrnl!IoAllocateMdl` at `0x1c00bdd8a`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x1c00bddda`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x1c00bddda`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c00bc570`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c00bd46c`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c00bc570`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c00bd46c`
- `ntoskrnl!_strnicmp` at `0x1c00bd844`
- `ntoskrnl!_strnicmp` at `0x1c00bd844`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x1c00bd17a`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x1c00bd17a`
- `ntoskrnl!MmUserProbeAddress` at `0x1c00bc207`
- `ntoskrnl!MmUserProbeAddress` at `0x1c00bcda6`
- `ntoskrnl!MmUserProbeAddress` at `0x1c00bcecf`
- `ntoskrnl!MmUserProbeAddress` at `0x1c00bd086`
- `ntoskrnl!ExRaiseStatus` at `0x1c00bd19d`
- `ntoskrnl!ExRaiseStatus` at `0x1c00bda35`
- `ntoskrnl!ExRaiseStatus` at `0x1c00bd19d`
- `ntoskrnl!ExRaiseStatus` at `0x1c00bda35`
- `ntoskrnl!IoIs32bitProcess` at `0x1c00bc1c3`
- `ntoskrnl!IoIs32bitProcess` at `0x1c00bc1c3`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x1c00bd42a`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x1c00bd42a`
- `ntoskrnl!ExAllocatePoolWithTagPriority` at `0x1c00bd506`
- `ntoskrnl!ExAllocatePoolWithTagPriority` at `0x1c00bd506`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c00ed613`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c00ed613`

## pseudocode

```c
__int64 __fastcall UlCaptureHttpResponse(
        __int64 a1,
        unsigned __int64 a2,
        __int64 a3,
        PIRP a4,
        unsigned __int16 a5,
        IRP *a6,
        unsigned __int8 a7,
        unsigned int a8,
        char a9,
        unsigned __int8 a10,
        int a11,
        char a12,
        char a13,
        __int16 *a14,
        _QWORD *a15)
{
  __int64 v15; // r13
  __int64 v17; // rdx
  char *PoolWithTagPriority; // rsi
  unsigned __int16 v19; // r12
  __int64 v20; // rdx
  __int16 v21; // ax
  int appended; // edi
  int v23; // eax
  unsigned __int16 v24; // bx
  unsigned int v25; // r8d
  unsigned int v26; // edx
  unsigned int v27; // ebx
  __int64 v28; // rax
  int v29; // ecx
  unsigned __int64 v30; // r12
  char v31; // di
  __int64 v32; // r9
  unsigned int v33; // r8d
  __int64 v34; // rax
  __int64 v35; // rbx
  void **v36; // r12
  unsigned int i; // eax
  char *v38; // rcx
  unsigned int v39; // edx
  __int64 v40; // rax
  unsigned int v41; // edx
  __int64 v42; // rdi
  unsigned int v43; // ebx
  unsigned __int16 v44; // r12
  __int16 v45; // ax
  __int64 v46; // rcx
  _BYTE *v47; // rbx
  char *v48; // rbx
  unsigned __int8 v49; // bl
  int v50; // ecx
  unsigned int v51; // eax
  unsigned int v52; // r12d
  unsigned __int8 *v53; // rbx
  unsigned int v54; // ecx
  const char *v55; // rbx
  char *v56; // rcx
  _DWORD *v57; // r12
  __int64 v58; // rax
  _DWORD *v59; // r12
  unsigned int v60; // ebx
  __int64 v61; // r8
  unsigned int *v62; // rcx
  __int64 v63; // rax
  size_t v64; // rcx
  char *v65; // r10
  __int64 v66; // rbx
  char *v67; // rbx
  __int64 v68; // r12
  __int64 v69; // rdx
  char *v70; // r9
  __int64 v71; // rdx
  __int64 v72; // rax
  __int64 v73; // r12
  __int64 v74; // rax
  unsigned int v75; // eax
  char *v76; // rbx
  __int64 v77; // r12
  __int64 v78; // rdx
  __int64 v79; // rcx
  int v80; // eax
  __int128 v81; // xmm0
  char *v82; // rdi
  __int128 v83; // xmm0
  __int128 v84; // xmm0
  _QWORD *v85; // rbx
  char v86; // al
  char v87; // al
  __int128 v88; // xmm0
  __int64 v89; // rsi
  USHORT CurrentNodeNumber; // ax
  __int64 v91; // r9
  unsigned int v92; // r8d
  __int64 v93; // rax
  __int64 v94; // r12
  __int64 v95; // rcx
  __int64 v96; // rbx
  char v97; // al
  char v98; // al
  char *v99; // r12
  unsigned __int16 v100; // bx
  __int64 v101; // rbx
  void *v102; // rax
  __int16 v103; // dx
  __int64 v104; // r13
  __int64 v105; // rax
  __int64 v106; // rcx
  PMDL Mdl; // rax
  __int64 v108; // rcx
  __int64 v109; // rdx
  __int64 v110; // r8
  __int64 v112; // r11
  __int64 v113; // r8
  _QWORD *v114; // rbx
  PIRP Irp; // [rsp+20h] [rbp-268h]
  __int64 v116; // [rsp+28h] [rbp-260h]
  int v117; // [rsp+38h] [rbp-250h]
  int v118; // [rsp+50h] [rbp-238h]
  int v119; // [rsp+90h] [rbp-1F8h]
  char v120; // [rsp+A0h] [rbp-1E8h]
  char v121; // [rsp+A2h] [rbp-1E6h]
  _BYTE v122[9]; // [rsp+A3h] [rbp-1E5h] BYREF
  unsigned __int16 v123; // [rsp+ACh] [rbp-1DCh]
  unsigned int v124; // [rsp+B0h] [rbp-1D8h]
  __int64 v125; // [rsp+B4h] [rbp-1D4h] BYREF
  __int16 v126; // [rsp+BCh] [rbp-1CCh]
  __int16 v127; // [rsp+C0h] [rbp-1C8h] BYREF
  __int16 v128; // [rsp+C4h] [rbp-1C4h]
  int v129; // [rsp+C8h] [rbp-1C0h]
  int v130; // [rsp+CCh] [rbp-1BCh]
  _QWORD *v131; // [rsp+D0h] [rbp-1B8h]
  size_t Size; // [rsp+D8h] [rbp-1B0h]
  unsigned int v133; // [rsp+E0h] [rbp-1A8h] BYREF
  int v134; // [rsp+E4h] [rbp-1A4h]
  char *v135; // [rsp+E8h] [rbp-1A0h]
  __int16 v136; // [rsp+F0h] [rbp-198h]
  __int16 v137; // [rsp+F4h] [rbp-194h]
  unsigned int v138; // [rsp+F8h] [rbp-190h]
  unsigned int v139; // [rsp+FCh] [rbp-18Ch]
  unsigned int v140; // [rsp+100h] [rbp-188h]
  __int64 v141; // [rsp+108h] [rbp-180h]
  PIRP v142; // [rsp+110h] [rbp-178h]
  void *Src[2]; // [rsp+118h] [rbp-170h]
  IRP *v144; // [rsp+128h] [rbp-160h]
  unsigned int v145; // [rsp+130h] [rbp-158h]
  unsigned int v146; // [rsp+134h] [rbp-154h]
  int v147; // [rsp+138h] [rbp-150h] BYREF
  int v148; // [rsp+13Ch] [rbp-14Ch] BYREF
  unsigned __int64 v149; // [rsp+140h] [rbp-148h]
  __int64 v150; // [rsp+148h] [rbp-140h] BYREF
  __int64 HkeContextFromRequest; // [rsp+150h] [rbp-138h]
  PVOID P; // [rsp+158h] [rbp-130h] BYREF
  int v153; // [rsp+160h] [rbp-128h]
  unsigned __int8 *v154; // [rsp+168h] [rbp-120h] BYREF
  char *v155; // [rsp+170h] [rbp-118h]
  __int64 v156; // [rsp+178h] [rbp-110h]
  __int64 v157; // [rsp+180h] [rbp-108h] BYREF
  size_t v158; // [rsp+188h] [rbp-100h]
  unsigned int v159; // [rsp+190h] [rbp-F8h]
  void *v160[2]; // [rsp+198h] [rbp-F0h]
  void *v161[2]; // [rsp+1A8h] [rbp-E0h]
  __int64 v162; // [rsp+1B8h] [rbp-D0h] BYREF
  __int128 v163; // [rsp+1C0h] [rbp-C8h] BYREF
  __int64 v164; // [rsp+1D0h] [rbp-B8h]
  unsigned __int8 *v165; // [rsp+1D8h] [rbp-B0h]
  void *v166; // [rsp+1E0h] [rbp-A8h]
  unsigned __int64 v167; // [rsp+1E8h] [rbp-A0h]
  __int64 v168; // [rsp+1F0h] [rbp-98h]
  PIRP v169; // [rsp+1F8h] [rbp-90h]
  __int128 v170; // [rsp+200h] [rbp-88h] BYREF
  __int64 v171; // [rsp+210h] [rbp-78h]
  __int128 v172; // [rsp+218h] [rbp-70h] BYREF
  HANDLE v173; // [rsp+228h] [rbp-60h]
  _DWORD *v174; // [rsp+230h] [rbp-58h]
  ULONG Length[4]; // [rsp+238h] [rbp-50h]

  v142 = a4;
  v15 = a3;
  v141 = a3;
  v156 = a1;
  v167 = a2;
  v168 = a3;
  v169 = a4;
  v144 = a6;
  v17 = (__int64)a15;
  v136 = 2;
  v130 = 2;
  *(_OWORD *)Length = 0;
  v157 = 0;
  v160[0] = 0;
  v160[1] = 0;
  v161[0] = 0;
  v161[1] = 0;
  v135 = 0;
  P = 0;
  v127 = 0;
  Src[0] = 0;
  Src[1] = 0;
  *(_WORD *)v122 = 0;
  *(_DWORD *)&v122[5] = 0;
  v140 = 0;
  PoolWithTagPriority = 0;
  v131 = 0;
  v149 = 0;
  LODWORD(v150) = 0;
  v139 = 0;
  v148 = 0;
  v147 = 0;
  v162 = 0;
  v121 = 0;
  v138 = 0;
  v126 = 0;
  HkeContextFromRequest = 0;
  v128 = 1000;
  v170 = 0;
  v171 = 0;
  v163 = 0;
  v164 = 0;
  v125 = 0;
  LODWORD(Size) = 0;
  v124 = 0;
  if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x100) != 0 )
  {
    if ( a3 )
      v112 = *(_QWORD *)(a3 + 64);
    else
      LOBYTE(v112) = 0;
    v120 = a13;
    v19 = a5;
    v15 = v141;
    WPP_SF_qqqiqlqlLllqllqq(
      (_DWORD)v142,
      a10,
      v156,
      a2,
      v141,
      v112,
      (char)v142,
      a5,
      (char)v144,
      a7,
      a8,
      a9,
      a10,
      a11,
      a12,
      a13,
      (char)a14,
      (char)a15);
    a4 = v142;
  }
  else
  {
    v120 = a13;
    v19 = a5;
  }
  if ( v19 >= 0x2710u )
  {
    appended = -1073741811;
    v119 = -1073741811;
    v61 = -1;
    v85 = a15;
    goto LABEL_305;
  }
  if ( a2 )
  {
    if ( !IoIs32bitProcess(a4) )
    {
      if ( (WORD2(WPP_MAIN_CB.Queue.Wcb.DmaWaitEntry.Flink) & 0x100) != 0 )
        WPP_SF_PqLc(10, v20, 568, a2);
      if ( a7 )
      {
        if ( (a2 & 7) != 0 )
          ExRaiseDatatypeMisalignment();
        if ( a2 + 568 > MmUserProbeAddress || a2 + 568 < a2 )
          *(_BYTE *)MmUserProbeAddress = 0;
      }
      else if ( (a2 & 7) != 0 )
      {
        ExRaiseStatus(-1073741115);
      }
    }
    v21 = *(_WORD *)(a2 + 8);
    v128 = v21;
    if ( a14 )
      *a14 = v21;
  }
  appended = UlpProbeHttpResponse(a2, v19, (_DWORD)v144, a11, a7);
  v119 = appended;
  if ( appended < 0 )
  {
    v61 = -1;
    v85 = a15;
    goto LABEL_305;
  }
  if ( v156 )
  {
    v23 = *(_DWORD *)(*(_QWORD *)(v156 + 8) + 276LL);
    v130 = v23;
    v24 = v23;
  }
  else
  {
    v23 = v130;
    v24 = v136;
  }
  appended = UlComputeFixedHeaderSize(v142, a10, v23, (__int64)&v125, (__int64)&v122[5]);
  v119 = appended;
  if ( appended < 0 )
  {
    v61 = -1;
    v85 = a15;
    goto LABEL_305;
  }
  if ( a9 || *(_BYTE *)(v15 + 3502) )
  {
    LODWORD(Size) = v125;
    v124 = v125;
    LODWORD(v125) = 0;
  }
  v25 = *(_DWORD *)&v122[5];
  if ( *(_DWORD *)&v122[5] )
    v139 = UlVariableHeaderSize;
  if ( v24 >= 2u )
  {
    appended = UlExtractAndAppendAuthenticationResponseInfo(v15, a2, v142, a7, 1u, &v122[1]);
    v119 = appended;
    if ( appended < 0 )
    {
      v61 = -1;
      v85 = a15;
      goto LABEL_305;
    }
    appended = UlComputeMultipleKnownHeaderSize(
                 v142,
                 (__int64)&v150,
                 (__int64)&P,
                 (__int64)&v127,
                 (__int64)v122,
                 (__int64)&v125 + 4,
                 (__int64)&v125);
    v119 = appended;
    if ( appended < 0 )
    {
      v61 = -1;
      v85 = a15;
      goto LABEL_305;
    }
    v25 = *(_DWORD *)&v122[5];
  }
  v26 = Size;
  if ( v25 && *(_BYTE *)(v15 + 3502) )
  {
    v26 = v125 + UlH3ExtraHeaderCount + Size;
    v124 = v26;
    LODWORD(v125) = 0;
  }
  if ( *(_DWORD *)(v15 + 2660) && !*(_BYTE *)(v15 + 2688) && *(_BYTE *)(v15 + 3502) )
  {
    v26 += 2;
    v124 = v26;
  }
  if ( !v25 || *(_BYTE *)(v15 + 3502) )
    v27 = v19;
  else
    v27 = v19 + 2;
  v129 = v27;
  if ( v120 )
  {
    if ( _InterlockedCompareExchange((volatile signed __int32 *)(v15 + 2192), 0, 1) == 1 )
    {
      a5 = 1;
      v27 = 1;
      v129 = 1;
    }
    else
    {
      a13 = 0;
      v27 = v129;
    }
    v26 = v124;
    PoolWithTagPriority = (char *)v131;
    v25 = *(_DWORD *)&v122[5];
  }
  a4 = (PIRP)HIDWORD(v125);
  if ( HIDWORD(v125) && !*(_BYTE *)(v15 + 3502) )
    v129 = ++v27;
  v28 = v27;
  v146 = v27;
  if ( a2 )
  {
    v29 = *(unsigned __int16 *)(a2 + 24);
    v126 = *(_WORD *)(a2 + 24);
    if ( a12 )
    {
      v138 = 24 * (v29 + 35);
      v28 = v27 + 1;
      v146 = v27 + 1;
    }
  }
  Size = 80 * v28;
  v158 = v138;
  v17 = v139 + 24LL * v26;
  v30 = 80 * v28 + v17 + v138 + (unsigned __int64)HIDWORD(v125) + v25;
  v149 = v30;
  if ( v30 > 0x7FFFFFFF )
  {
    appended = -1073741675;
    v119 = -1073741675;
    v61 = -1;
    v85 = a15;
    goto LABEL_305;
  }
  if ( !a9 )
  {
    if ( a2 )
    {
      if ( *(_BYTE *)(v15 + 1669) )
      {
        if ( *(_BYTE *)(v15 + 1664) )
        {
          if ( (a8 & 0x20) != 0 )
          {
            v88 = *(_OWORD *)(a2 + 408);
            *(_OWORD *)Src = v88;
            if ( (_WORD)v88 )
            {
              v30 += (unsigned __int16)v88 + 1LL;
              v149 = v30;
              UlProbeAnsiString(Src[1], (unsigned __int16)v88, a7);
            }
          }
        }
      }
    }
    goto LABEL_42;
  }
  if ( !a2 )
    goto LABEL_42;
  v81 = *(_OWORD *)(a2 + 408);
  *(_OWORD *)Src = v81;
  if ( (_WORD)v81 )
  {
    v30 += (unsigned __int16)v81 + 1LL;
    v149 = v30;
    v82 = (char *)Src[1];
    if ( (WORD2(WPP_MAIN_CB.Queue.Wcb.DmaWaitEntry.Flink) & 0x100) != 0 )
    {
      v86 = 85;
      if ( !a7 )
        v86 = 75;
      LOBYTE(Irp) = v86;
      WPP_SF_Hqc(v81, 75, (unsigned __int16)v81, Src[1], (_DWORD)Irp);
    }
    if ( !v82 )
      goto LABEL_258;
    if ( (WORD2(WPP_MAIN_CB.Queue.Wcb.DmaWaitEntry.Flink) & 0x100) != 0 )
    {
      v87 = 85;
      if ( !a7 )
        v87 = 75;
      LOBYTE(v116) = v87;
      LODWORD(Irp) = 1;
      WPP_SF_PqLc(10, v17, (unsigned __int16)v81, v82);
    }
    v17 = a7;
    if ( !a7 )
      goto LABEL_165;
    if ( (unsigned __int64)&v82[(unsigned __int16)v81] > MmUserProbeAddress || &v82[(unsigned __int16)v81] < v82 )
      *(_BYTE *)MmUserProbeAddress = 0;
  }
  v17 = a7;
LABEL_165:
  v83 = *(_OWORD *)(a2 + 56);
  *(_OWORD *)v160 = v83;
  if ( (_WORD)v83 )
  {
    v30 += (unsigned __int16)v83 + 1LL;
    v149 = v30;
    UlProbeAnsiString(v160[1], (unsigned __int16)v83, (unsigned __int8)v17);
    v17 = a7;
  }
  v84 = *(_OWORD *)(a2 + 264);
  *(_OWORD *)v161 = v84;
  if ( (_WORD)v84 )
  {
    v30 += (unsigned __int16)v84 + 1LL;
    v149 = v30;
    UlProbeAnsiString(v161[1], (unsigned __int16)v84, (unsigned __int8)v17);
  }
  if ( (*(_DWORD *)a2 & 1) != 0 )
    v121 = 1;
LABEL_42:
  if ( v30 >= 0xFFFFFFFFFFFFFC80uLL || v30 == 0 || v30 + 896 > (unsigned int)UlResponseBufferSize )
  {
    v31 = 0;
    if ( (unsigned int)v30 >= (int)v30 + 896 )
      PoolWithTagPriority = 0;
    else
      PoolWithTagPriority = (char *)ExAllocatePoolWithTagPriority(
                                      (POOL_TYPE)512,
                                      (unsigned int)v30 + 896LL,
                                      0x52496C55u,
                                      LowPoolPriority);
    v131 = PoolWithTagPriority;
    if ( !PoolWithTagPriority )
    {
      appended = -1073741670;
      v119 = -1073741670;
      v61 = -1;
      v85 = a15;
      goto LABEL_305;
    }
  }
  else
  {
    v31 = 1;
    if ( UxCompactMode )
    {
      v89 = qword_1C0074210;
      CurrentNodeNumber = KeGetCurrentNodeNumber();
      v91 = *(_QWORD *)(v89 + 32);
      v92 = CurrentNodeNumber + 1;
      v93 = (unsigned int)(*(_DWORD *)v89 - 1);
      if ( v92 < *(_DWORD *)v89 )
        v93 = v92;
      v94 = *(_QWORD *)(v91 + 8 * v93);
      if ( !*(_BYTE *)(v94 + 112) )
        PplpLazyInitializeLookasideList(v89, *(_QWORD *)(v91 + 8 * v93));
      ++*(_DWORD *)(v94 + 20);
      PoolWithTagPriority = (char *)ExpInterlockedPopEntrySList((PSLIST_HEADER)v94);
      if ( !PoolWithTagPriority )
      {
        ++*(_DWORD *)(v94 + 24);
        PoolWithTagPriority = (char *)(*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64, _DWORD, _DWORD))(v94 + 48))(
                                        *(unsigned int *)(v94 + 36),
                                        *(unsigned int *)(v94 + 44),
                                        *(unsigned int *)(v94 + 40),
                                        v94,
                                        (_DWORD)Irp,
                                        v116);
      }
      v131 = PoolWithTagPriority;
    }
    else
    {
      v32 = *(_QWORD *)(qword_1C0074210 + 32);
      v33 = HIDWORD(KeGetPcr()[1].LockArray) + 1;
      v34 = (unsigned int)(*(_DWORD *)qword_1C0074210 - 1);
      if ( v33 < *(_DWORD *)qword_1C0074210 )
        v34 = v33;
      v35 = *(_QWORD *)(v32 + 8 * v34);
      if ( !*(_BYTE *)(v35 + 112) )
        PplpLazyInitializeLookasideList(qword_1C0074210, *(_QWORD *)(v32 + 8 * v34));
      ++*(_DWORD *)(v35 + 20);
      PoolWithTagPriority = (char *)ExpInterlockedPopEntrySList((PSLIST_HEADER)v35);
      if ( !PoolWithTagPriority )
      {
        ++*(_DWORD *)(v35 + 24);
        PoolWithTagPriority = (char *)(*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64, _DWORD, _DWORD))(v35 + 48))(
                                        *(unsigned int *)(v35 + 36),
                                        *(unsigned int *)(v35 + 44),
                                        *(unsigned int *)(v35 + 40),
                                        v35,
                                        (_DWORD)Irp,
                                        v116);
      }
      v131 = PoolWithTagPriority;
      v31 = 1;
      v27 = v129;
    }
    if ( !PoolWithTagPriority )
    {
      appended = -1073741670;
      v119 = -1073741670;
      v61 = -1;
      v85 = a15;
      goto LABEL_305;
    }
  }
  v119 = 0;
  v36 = (void **)PoolWithTagPriority;
  PoolWithTagPriority[44] = v31;
  *((_DWORD *)PoolWithTagPriority + 4) = 1380543573;
  *((_QWORD *)PoolWithTagPriority + 52) = 0;
  *((_QWORD *)PoolWithTagPriority + 54) = 0;
  *((_QWORD *)PoolWithTagPriority + 56) = 0;
  *((_DWORD *)PoolWithTagPriority + 5) = 1;
  *((_DWORD *)PoolWithTagPriority + 217) = v27;
  *((_DWORD *)PoolWithTagPriority + 216) = 0;
  *((_DWORD *)PoolWithTagPriority + 218) = -1;
  *((_QWORD *)PoolWithTagPriority + 106) = 0;
  *((_QWORD *)PoolWithTagPriority + 107) = 0;
  *((_QWORD *)PoolWithTagPriority + 110) = PoolWithTagPriority + 888;
  memset(PoolWithTagPriority + 888, 0, Size);
  _InterlockedIncrement((volatile signed __int32 *)(v15 + 48));
  PoolWithTagPriority = (char *)v131;
  v131[3] = v15;
  *((_DWORD *)PoolWithTagPriority + 14) = a8;
  *((_QWORD *)PoolWithTagPriority + 4) = 0;
  PoolWithTagPriority[40] = 0;
  PoolWithTagPriority[43] = 0;
  *((_QWORD *)PoolWithTagPriority + 41) = 0;
  *((_DWORD *)PoolWithTagPriority + 96) = 0;
  *((_QWORD *)PoolWithTagPriority + 49) = 0;
  *((_QWORD *)PoolWithTagPriority + 50) = 0;
  *((_WORD *)PoolWithTagPriority + 30) = 0;
  PoolWithTagPriority[45] = a7 == 0;
  PoolWithTagPriority[46] = a10;
  PoolWithTagPriority[48] = 0;
  PoolWithTagPriority[49] = v121;
  PoolWithTagPriority[55] = 0;
  *((_QWORD *)PoolWithTagPriority + 18) = 0;
  *((_DWORD *)PoolWithTagPriority + 38) = 0;
  *((_QWORD *)PoolWithTagPriority + 20) = 0;
  *((_QWORD *)PoolWithTagPriority + 23) = 4;
  *((_QWORD *)PoolWithTagPriority + 24) = 0;
  PoolWithTagPriority[41] = 1;
  PoolWithTagPriority[42] = v122[0];
  *((_DWORD *)PoolWithTagPriority + 17) = 3;
  *((_QWORD *)PoolWithTagPriority + 40) = 0;
  *((_QWORD *)PoolWithTagPriority + 58) = 0;
  *((_QWORD *)PoolWithTagPriority + 59) = 0;
  PoolWithTagPriority[47] = UlInitializeResumeParsingFlag(v15, a8);
  *((_DWORD *)PoolWithTagPriority + 42) = 0;
  *((_QWORD *)PoolWithTagPriority + 22) = 0;
  *((_DWORD *)PoolWithTagPriority + 84) = 0;
  *(_DWORD *)(PoolWithTagPriority + 50) = 0;
  *(_QWORD *)(PoolWithTagPriority + 372) = 0;
  *((_QWORD *)PoolWithTagPriority + 43) = 0;
  *((_DWORD *)PoolWithTagPriority + 18) = 0;
  *((_QWORD *)PoolWithTagPriority + 17) = 0;
  *(_QWORD *)(PoolWithTagPriority + 116) = 0;
  *(_QWORD *)(PoolWithTagPriority + 124) = 0;
  *((_WORD *)PoolWithTagPriority + 56) = 0;
  PoolWithTagPriority[54] = v122[1];
  *((_DWORD *)PoolWithTagPriority + 33) = 0;
  memset(PoolWithTagPriority + 200, 0, 0x68u);
  *((_OWORD *)PoolWithTagPriority + 30) = 0;
  *((_OWORD *)PoolWithTagPriority + 31) = 0;
  v145 = 0;
  memset(PoolWithTagPriority + 512, 0, 0x150u);
  *((_QWORD *)PoolWithTagPriority + 65) = PoolWithTagPriority + 512;
  *((_QWORD *)PoolWithTagPriority + 64) = PoolWithTagPriority + 512;
  for ( i = 0; ; ++i )
  {
    v145 = i;
    if ( i >= 0x10 )
      break;
    v38 = &PoolWithTagPriority[16 * i + 528];
    *((_QWORD *)v38 + 1) = v38;
    *(_QWORD *)v38 = v38;
  }
  v39 = v138;
  *((_DWORD *)PoolWithTagPriority + 92) = v138;
  v40 = (__int64)&PoolWithTagPriority[80 * v146 + 888];
  *((_QWORD *)PoolWithTagPriority + 45) = v40;
  *((_QWORD *)PoolWithTagPriority + 44) = v40 + 520;
  *((_DWORD *)PoolWithTagPriority + 19) = *(_DWORD *)&v122[5];
  *((_QWORD *)PoolWithTagPriority + 11) = *((_QWORD *)PoolWithTagPriority + 45) + v39;
  *((_DWORD *)PoolWithTagPriority + 20) = HIDWORD(v125);
  *((_QWORD *)PoolWithTagPriority + 12) = *((_QWORD *)PoolWithTagPriority + 11) + *(unsigned int *)&v122[5];
  v41 = v139;
  *((_DWORD *)PoolWithTagPriority + 21) = v139;
  *((_QWORD *)PoolWithTagPriority + 13) = *((_QWORD *)PoolWithTagPriority + 12) + HIDWORD(v125);
  v42 = v41;
  v43 = v124;
  UlInitializeParsedHeaders(
    PoolWithTagPriority + 480,
    *((_QWORD *)PoolWithTagPriority + 11) + v41 + (unsigned __int64)HIDWORD(v125) + *(unsigned int *)&v122[5],
    v124);
  v153 = 24 * v43;
  *((_QWORD *)PoolWithTagPriority + 39) = *((_QWORD *)PoolWithTagPriority + 11)
                                        + 24 * v43
                                        + v42
                                        + HIDWORD(v125)
                                        + *(unsigned int *)&v122[5];
  if ( *((_DWORD *)PoolWithTagPriority + 92) )
  {
    memset(v36[45], 0, v158);
    v17 = 1;
    **((_WORD **)PoolWithTagPriority + 45) = 1;
    *(_QWORD *)(*((_QWORD *)PoolWithTagPriority + 45) + 24LL) = (char *)v36[44] + 80;
    *(_WORD *)(*((_QWORD *)PoolWithTagPriority + 45) + 32LL) = v126;
    **((_QWORD **)PoolWithTagPriority + 44) = 0;
  }
  else
  {
    v36[45] = 0;
    v36[44] = 0;
    v17 = 1;
  }
  if ( LOWORD(Src[0]) )
  {
    *((_DWORD *)PoolWithTagPriority + 38) = LOWORD(Src[0]) + 1;
    *((_QWORD *)PoolWithTagPriority + 20) = *((_QWORD *)PoolWithTagPriority + 39);
  }
  if ( LOWORD(v160[0]) )
  {
    *((_DWORD *)PoolWithTagPriority + 42) = LOWORD(v160[0]) + 1;
    *((_QWORD *)PoolWithTagPriority + 22) = *((_QWORD *)PoolWithTagPriority + 39)
                                          + *((unsigned int *)PoolWithTagPriority + 38);
  }
  v44 = (unsigned __int16)v161[0];
  if ( LOWORD(v161[0]) )
  {
    *((_DWORD *)PoolWithTagPriority + 47) = LOWORD(v161[0]) + 1;
    *((_QWORD *)PoolWithTagPriority + 24) = *((_QWORD *)PoolWithTagPriority + 39)
                                          + *((unsigned int *)PoolWithTagPriority + 38)
                                          + (unsigned __int64)*((unsigned int *)PoolWithTagPriority + 42);
  }
  if ( !a2 )
    goto LABEL_260;
  *((_DWORD *)PoolWithTagPriority + 16) = *(_DWORD *)(v15 + 1968);
  v45 = v128;
  if ( (unsigned __int16)v128 > 0x3E7u )
  {
    appended = -1073741811;
    v119 = -1073741811;
    if ( (WPP_MAIN_CB.StackSize & 0x20) == 0 )
      goto LABEL_266;
    v79 = 19;
    goto LABEL_220;
  }
  *(_WORD *)(v15 + 1676) = v128;
  *((_WORD *)PoolWithTagPriority + 30) = v45;
  v46 = *((_QWORD *)PoolWithTagPriority + 40);
  if ( v46 )
    *(_WORD *)(v46 + 120) = v45;
  v47 = *(_BYTE **)(a2 + 80);
  if ( !*(_WORD *)(a2 + 72) )
  {
    if ( v47 )
    {
      UlProbeAnsiString(*(_QWORD *)(a2 + 80), 1, a7);
      if ( !*v47 )
        *((_DWORD *)PoolWithTagPriority + 17) = 0;
    }
  }
  v123 = *(_WORD *)(a2 + 88);
  v48 = *(char **)(a2 + 96);
  v155 = v48;
  if ( !v123 && v48 )
  {
    UlProbeAnsiString(v48, 1, a7);
    if ( !*v48 )
      PoolWithTagPriority[41] = 0;
  }
  else
  {
    PoolWithTagPriority[41] = 1;
  }
  v49 = a7;
  appended = UxCaptureString(*(void **)(a2 + 240));
  v119 = appended;
  if ( appended < 0 )
  {
    v61 = -1;
    v85 = a15;
    goto LABEL_305;
  }
  v50 = (unsigned __int16)v170;
  if ( !(_WORD)v170
    || (PoolWithTagPriority[40] = 1,
        LOBYTE(a4) = 1,
        (int)HttpStringToULongLong(0, DWORD2(v170), v50, (_DWORD)a4, 10, 0, (__int64)(PoolWithTagPriority + 32)) >= 0) )
  {
    appended = UxCaptureString(*(void **)(a2 + 384));
    v119 = appended;
    if ( appended < 0 )
    {
      v61 = -1;
      v85 = a15;
      goto LABEL_305;
    }
    v51 = (unsigned __int16)v163;
    if ( !(_WORD)v163 )
    {
LABEL_96:
      v55 = *(const char **)(a2 + 160);
      LODWORD(v56) = 7;
      if ( *(_WORD *)(a2 + 152) == 7 )
      {
        UlProbeAnsiString(*(_QWORD *)(a2 + 160), 7, a7);
        if ( !_strnicmp(v55, "chunked", 7u) )
        {
          if ( PoolWithTagPriority[40] )
          {
            appended = -1073741811;
            v119 = -1073741811;
            if ( (WPP_MAIN_CB.StackSize & 0x20) != 0 )
            {
              v79 = 21;
              goto LABEL_220;
            }
LABEL_266:
            v49 = a7;
            goto LABEL_267;
          }
          PoolWithTagPriority[43] = 1;
        }
      }
      if ( !a9 )
      {
        if ( *(_BYTE *)(v15 + 1669) && *(_BYTE *)(v15 + 1664) && (a8 & 0x20) != 0 )
        {
          v99 = *(char **)(a2 + 368);
          v155 = v99;
          v100 = *(_WORD *)(a2 + 360);
          v123 = v100;
          if ( v100 )
          {
            UlProbeAnsiString(v99, v100, a7);
            if ( !(unsigned __int8)StringTimeToSystemTime(v99, v100, PoolWithTagPriority + 144) )
            {
              appended = -1073741811;
              v119 = -1073741811;
              if ( (WPP_MAIN_CB.StackSize & 0x20) == 0 )
                goto LABEL_266;
              v79 = 23;
              goto LABEL_220;
            }
          }
          if ( LOWORD(Src[0]) )
          {
            v101 = LOWORD(Src[0]);
            memmove(*((void **)PoolWithTagPriority + 20), Src[1], LOWORD(Src[0]));
            *(_BYTE *)(v101 + *((_QWORD *)PoolWithTagPriority + 20)) = 0;
          }
        }
        goto LABEL_99;
      }
      if ( LOWORD(Src[0]) )
      {
        v66 = LOWORD(Src[0]);
        memmove(*((void **)PoolWithTagPriority + 20), Src[1], LOWORD(Src[0]));
        *(_BYTE *)(v66 + *((_QWORD *)PoolWithTagPriority + 20)) = 0;
      }
      if ( LOWORD(v160[0]) )
      {
        v96 = LOWORD(v160[0]);
        memmove(*((void **)PoolWithTagPriority + 22), v160[1], LOWORD(v160[0]));
        *(_BYTE *)(v96 + *((_QWORD *)PoolWithTagPriority + 22)) = 0;
      }
      if ( v44 )
      {
        memmove(*((void **)PoolWithTagPriority + 24), v161[1], v44);
        *(_BYTE *)(v44 + *((_QWORD *)PoolWithTagPriority + 24)) = 0;
        v80 = UlParseContentEncoding(
                *((_QWORD *)PoolWithTagPriority + 24),
                v44,
                (unsigned int)&v148,
                (unsigned int)&v162,
                (__int64)&v147);
        appended = v80;
        v119 = v80;
        if ( v80 < 0 )
        {
          if ( v80 == -1073741637 )
          {
            PoolWithTagPriority[48] = 1;
            appended = 0;
            v119 = 0;
          }
          else
          {
            if ( v80 != -1073741275 )
            {
              v61 = -1;
              v85 = a15;
              goto LABEL_305;
            }
            *((_QWORD *)PoolWithTagPriority + 24) = 0;
            *((_DWORD *)PoolWithTagPriority + 47) = 0;
            appended = 0;
            v119 = 0;
          }
        }
        else
        {
          *((_QWORD *)PoolWithTagPriority + 24) = v162;
          *((_DWORD *)PoolWithTagPriority + 47) = v147;
          *((_DWORD *)PoolWithTagPriority + 46) = v148;
        }
      }
      v67 = *(char **)(a2 + 256);
      v155 = v67;
      v68 = *(unsigned __int16 *)(a2 + 248);
      v123 = v68;
      if ( (_WORD)v68 )
      {
        if ( (WORD2(WPP_MAIN_CB.Queue.Wcb.DmaWaitEntry.Flink) & 0x100) != 0 )
        {
          v97 = 85;
          if ( !a7 )
            v97 = 75;
          LOBYTE(Irp) = v97;
          WPP_SF_Hqc(75, v17, (unsigned __int16)v68, v67, (_DWORD)Irp);
        }
        if ( !v67 )
          goto LABEL_258;
        v69 = v68;
        if ( (WORD2(WPP_MAIN_CB.Queue.Wcb.DmaWaitEntry.Flink) & 0x100) != 0 )
        {
          LODWORD(Irp) = 1;
          WPP_SF_PqLc(10, v68, v68, v67);
          v69 = v68;
        }
        if ( a7 )
        {
          v56 = &v67[v69];
          if ( (unsigned __int64)&v67[v69] > MmUserProbeAddress || v56 < v67 )
            *(_BYTE *)MmUserProbeAddress = 0;
        }
        v70 = PoolWithTagPriority + 200;
        v71 = (unsigned int)v68;
        LODWORD(Size) = v68;
        if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x2000) != 0 )
        {
          WPP_SF_sLq((_DWORD)v56, v68, (_DWORD)v67, v68, (_BYTE)PoolWithTagPriority - 56);
          v71 = (unsigned int)v68;
          v70 = PoolWithTagPriority + 200;
        }
        v72 = strnchr(v67, v71, (unsigned int)v71, v70);
        v73 = v72;
        if ( v72 )
        {
          if ( v67 != (char *)v72 )
          {
            v17 = (__int64)&v67[(unsigned int)(v17 - 1)];
            if ( v72 != v17 )
            {
              v74 = v72 - (_QWORD)v67;
              if ( v74 > 32 )
                LODWORD(v74) = 32;
              *(_DWORD *)&a4->Type = v74;
              memmove(&a4->Size + 1, v67, (unsigned int)v74);
              v75 = Size - *((_DWORD *)PoolWithTagPriority + 50) - 1;
              if ( v75 > 0x40 )
                v75 = 64;
              *((_DWORD *)PoolWithTagPriority + 59) = v75;
              memmove(PoolWithTagPriority + 240, (const void *)(v73 + 1), v75);
            }
          }
        }
        if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x2000) != 0 )
          WPP_SF_(171, WPP_3afd2232e6fe39b48106b10d7c60087a_Traceguids);
      }
      v76 = *(char **)(a2 + 368);
      v155 = v76;
      v77 = *(unsigned __int16 *)(a2 + 360);
      v123 = v77;
      if ( (_WORD)v77 )
      {
        if ( (WORD2(WPP_MAIN_CB.Queue.Wcb.DmaWaitEntry.Flink) & 0x100) != 0 )
        {
          v98 = 85;
          if ( !a7 )
            v98 = 75;
          LOBYTE(Irp) = v98;
          WPP_SF_Hqc(75, v17, (unsigned __int16)v77, v76, (_DWORD)Irp);
        }
        if ( v76 )
        {
          v78 = v77;
          if ( (WORD2(WPP_MAIN_CB.Queue.Wcb.DmaWaitEntry.Flink) & 0x100) != 0 )
          {
            LODWORD(Irp) = 1;
            WPP_SF_PqLc(10, v77, v77, v76);
            v78 = v77;
          }
          if ( a7 && ((unsigned __int64)&v76[v78] > MmUserProbeAddress || &v76[v78] < v76) )
            *(_BYTE *)MmUserProbeAddress = 0;
          if ( !(unsigned __int8)StringTimeToSystemTime(v76, (unsigned __int16)v77, PoolWithTagPriority + 144) )
          {
            appended = -1073741811;
            v119 = -1073741811;
            if ( (WPP_MAIN_CB.StackSize & 0x20) == 0 )
              goto LABEL_266;
            v79 = 22;
LABEL_220:
            WPP_SF_D(v79, WPP_7cbf0d8611643fc15970b65376ef98c5_Traceguids);
            v61 = -1;
            v59 = v135;
LABEL_113:
            v49 = a7;
            goto LABEL_300;
          }
LABEL_99:
          v57 = PoolWithTagPriority + 888;
          v135 = PoolWithTagPriority + 888;
          if ( !*((_DWORD *)PoolWithTagPriority + 19) || *(_BYTE *)(v15 + 3502) )
          {
            v58 = v140;
          }
          else
          {
            *v57 = 3;
            if ( *((_DWORD *)PoolWithTagPriority + 20) )
              *((_DWORD *)PoolWithTagPriority + 262) = 3;
            else
              *((_DWORD *)PoolWithTagPriority + 242) = 3;
            v58 = 2;
            v140 = 2;
          }
          if ( *((_DWORD *)PoolWithTagPriority + 20) && !*(_BYTE *)(v15 + 3502) )
          {
            *((_DWORD *)PoolWithTagPriority + 242) = 3;
            v58 = (unsigned int)(v58 + 1);
            v140 = v58;
          }
          v59 = &v57[20 * v58];
          v135 = (char *)v59;
          if ( a13 )
          {
            HkeContextFromRequest = UlGetHkeContextFromRequest(v15, 0);
            if ( !HkeContextFromRequest )
            {
              appended = -1073741254;
              v119 = -1073741254;
              if ( (WPP_MAIN_CB.StackSize & 0x20) != 0 )
                WPP_SF_D(24, WPP_7cbf0d8611643fc15970b65376ef98c5_Traceguids);
              v61 = -1;
              goto LABEL_113;
            }
            *v59 = 4;
            *(_OWORD *)(v59 + 2) = *(_OWORD *)(v15 + 2584);
            *((_QWORD *)v59 + 3) = HkeContextFromRequest;
            HkeContextFromRequest = 0;
            a5 = 0;
          }
          v60 = 0;
          v61 = -1;
          while ( 1 )
          {
            v159 = v60;
            if ( v60 >= a5 )
              goto LABEL_112;
            a4 = v144;
            v62 = (unsigned int *)((char *)v144 + 32 * v60);
            v17 = *v62;
            if ( (_DWORD)v17 == 1 )
              break;
            if ( (_DWORD)v17 )
            {
              if ( (unsigned int)(v17 - 2) > 1 )
              {
                appended = -1073741811;
                v119 = -1073741811;
                if ( (WPP_MAIN_CB.StackSize & 0x20) == 0 )
                  goto LABEL_112;
                v106 = 28;
LABEL_290:
                WPP_SF_D(v106, WPP_7cbf0d8611643fc15970b65376ef98c5_Traceguids);
                goto LABEL_291;
              }
              if ( v62 && (_DWORD)v17 == 2 )
              {
                v102 = (void *)*((_QWORD *)v62 + 2);
                v103 = *((_WORD *)v62 + 4);
                *(_QWORD *)Length = 0;
                *(_QWORD *)&Length[2] = -1;
              }
              else
              {
                v102 = (void *)*((_QWORD *)v62 + 3);
                v103 = -4;
                *(_OWORD *)Length = *(_OWORD *)(v62 + 2);
              }
              v137 = v103;
              v166 = v102;
              appended = UlCheckoutFragmentCacheEntry(v102, a7, (__int64)&v157);
              v119 = appended;
              if ( appended < 0 )
              {
                v61 = -1;
                v85 = a15;
                goto LABEL_305;
              }
              v104 = 10LL * v60;
              v59[2 * v104] = 3;
              *(_QWORD *)&v59[2 * v104 + 4] = v157;
              if ( *(_DWORD *)(v157 + 516) )
              {
                v105 = UxCloneMdl(*(PMDL *)(v157 + 520), Length[2]);
                *(_QWORD *)&v59[20 * v60 + 2] = v105;
                if ( !v105 )
                {
                  appended = -1073741670;
                  v119 = -1073741670;
                  if ( (WPP_MAIN_CB.StackSize & 0x20) != 0 )
                  {
                    v106 = 27;
                    goto LABEL_290;
                  }
LABEL_291:
                  v61 = -1;
LABEL_112:
                  v15 = v141;
                  goto LABEL_113;
                }
              }
              goto LABEL_110;
            }
            v64 = (size_t)&v59[20 * v60];
            v158 = v64;
            v65 = (char *)v144 + 32 * v60;
            if ( !a7 )
            {
              *(_DWORD *)v64 = 3;
              Mdl = IoAllocateMdl(*((PVOID *)v65 + 1), *((_DWORD *)v65 + 4), 0, 0, 0);
              *(_QWORD *)(v158 + 8) = Mdl;
              if ( !Mdl )
              {
                appended = -1073741670;
                v119 = -1073741670;
                if ( (WPP_MAIN_CB.StackSize & 0x20) == 0 )
                  goto LABEL_291;
                v106 = 25;
                goto LABEL_290;
              }
              MmBuildMdlForNonPagedPool(*(PMDL *)&v59[20 * v60 + 2]);
LABEL_110:
              v61 = -1;
              goto LABEL_111;
            }
            *(_DWORD *)v64 = 1;
            *(_QWORD *)(v64 + 8) = *((_QWORD *)v65 + 1);
            *(_DWORD *)(v64 + 16) = *((_DWORD *)v65 + 4);
LABEL_111:
            ++v60;
          }
          v63 = 20LL * v60;
          v59[v63] = 2;
          *(_OWORD *)&v59[v63 + 2] = *(_OWORD *)(v62 + 2);
          v173 = (HANDLE)*((_QWORD *)v62 + 3);
          v174 = &v59[v63 + 6];
          appended = UxCreateFileCacheEntry(v173);
          v119 = appended;
          if ( appended < 0 )
          {
            if ( (WPP_MAIN_CB.StackSize & 0x20) == 0 )
              goto LABEL_291;
            v106 = 26;
            goto LABEL_290;
          }
          goto LABEL_110;
        }
LABEL_258:
        ExRaiseStatus(-1073741811);
      }
      PoolWithTagPriority = (char *)v131;
      v131[18] = MEMORY[0xFFFFF78000000014];
LABEL_260:
      appended = v119;
      goto LABEL_99;
    }
    PoolWithTagPriority[112] = 1;
    v17 = (__int64)(PoolWithTagPriority + 113);
    v52 = v51;
    v134 = 0;
    v154 = 0;
    v133 = 0;
    v53 = (unsigned __int8 *)*((_QWORD *)&v163 + 1);
    if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x2000) != 0 )
    {
      Irp = (PIRP)(PoolWithTagPriority + 113);
      WPP_SF_qdP(178, WPP_3afd2232e6fe39b48106b10d7c60087a_Traceguids, *((_QWORD *)&v163 + 1), v51);
      v17 = (__int64)(PoolWithTagPriority + 113);
    }
    *(_BYTE *)v17 = 0;
    if ( v52 > 0xFFFE )
    {
      appended = -1073741811;
      v134 = -1073741811;
      if ( (WPP_MAIN_CB.StackSize & 0x20) == 0 )
      {
LABEL_92:
        if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x2000) != 0 )
          WPP_SF_DD(
            181,
            WPP_3afd2232e6fe39b48106b10d7c60087a_Traceguids,
            *(unsigned __int8 *)v17,
            (unsigned int)appended);
        v119 = appended;
        if ( appended < 0 )
        {
          v61 = -1;
          v85 = a15;
          goto LABEL_305;
        }
        v44 = (unsigned __int16)v161[0];
        goto LABEL_96;
      }
      v95 = 179;
    }
    else
    {
      v133 = v52;
      v165 = v53;
      while ( 1 )
      {
        v54 = v52;
        if ( !v52 )
          goto LABEL_84;
        if ( (HttpChars[*v53] & 0x20) == 0 )
          break;
        v165 = ++v53;
        --v52;
        v133 = v54 - 1;
      }
      if ( (HttpChars[*v53] & 0x200) == 0 )
      {
LABEL_84:
        v154 = v53;
        appended = 0;
        v134 = 0;
LABEL_85:
        if ( v52 == 5
          && ((*v53 - 66) & 0xDF) == 0
          && ((v53[1] - 89) & 0xDF) == 0
          && ((v53[2] - 84) & 0xDF) == 0
          && ((v53[3] - 69) & 0xDF) == 0
          && ((v53[4] - 83) & 0xDF) == 0 )
        {
          *(_BYTE *)v17 = 1;
        }
        goto LABEL_92;
      }
      appended = UlpParseLWS(v53, &v133, &v154);
      v134 = appended;
      if ( !appended )
      {
        v53 = v154;
        v52 = v133;
        v17 = (__int64)(PoolWithTagPriority + 113);
        goto LABEL_85;
      }
      appended = -1073741811;
      v134 = -1073741811;
      if ( (WPP_MAIN_CB.StackSize & 0x20) == 0 )
        goto LABEL_233;
      v95 = 180;
    }
    WPP_SF_D(v95, WPP_3afd2232e6fe39b48106b10d7c60087a_Traceguids);
LABEL_233:
    v17 = (__int64)(PoolWithTagPriority + 113);
    goto LABEL_92;
  }
  appended = -1073741811;
  v119 = -1073741811;
  if ( (WPP_MAIN_CB.StackSize & 0x20) != 0 )
  {
    WPP_SF_D(20, WPP_7cbf0d8611643fc15970b65376ef98c5_Traceguids);
    v61 = -1;
    v59 = v135;
    goto LABEL_300;
  }
LABEL_267:
  v61 = -1;
  v59 = v135;
LABEL_300:
  if ( appended < 0 )
  {
LABEL_304:
    v85 = a15;
    goto LABEL_305;
  }
  LOWORD(v118) = v127;
  LOBYTE(v117) = a9;
  LOBYTE(Irp) = v49;
  appended = UlpPrepareHttpResponse(
               v142,
               v15,
               a2,
               PoolWithTagPriority,
               Irp,
               v130,
               a8,
               v117,
               v150,
               P,
               v118,
               *((_QWORD *)PoolWithTagPriority + 45));
  v119 = appended;
  if ( appended < 0 || (v108 = *((_QWORD *)PoolWithTagPriority + 44)) == 0 || !a2 || (a8 & 2) != 0 || a5 != 1 )
  {
    v61 = -1;
    goto LABEL_304;
  }
  v61 = -1;
  v85 = a15;
  if ( *(_DWORD *)&v144->Type == 1 )
  {
    *(_QWORD *)(v108 + 56) = v144->AssociatedIrp.MasterIrp;
    *(_QWORD *)(*((_QWORD *)PoolWithTagPriority + 44) + 64LL) = *((_QWORD *)v59 + 1);
    *(_QWORD *)(*((_QWORD *)PoolWithTagPriority + 44) + 72LL) = *((_QWORD *)v59 + 2);
  }
LABEL_305:
  if ( appended < 0 )
  {
    if ( PoolWithTagPriority )
    {
      v61 = (unsigned int)_InterlockedExchangeAdd((volatile signed __int32 *)PoolWithTagPriority + 5, 0xFFFFFFFF);
      if ( (_DWORD)v61 == 1 )
      {
        v113 = *(_QWORD *)(*(_QWORD *)(v131[3] + 24LL) + 952LL);
        v114 = v131 + 52;
        v172 = 0;
        if ( v131[52] || v131[54] || v131[56] )
          UlBugCheckEx(1u, (ULONG_PTR)(v131 + 52), (ULONG_PTR)"minio\\http\\sys\\sendresponse.h", 0x317u);
        if ( KeGetCurrentIrql() )
        {
          LODWORD(v116) = -1;
          LOBYTE(a4) = 1;
          UlThreadPoolEnqueueWorkItem(0, v131 + 52, UlDestroyCapturedResponse, a4, v113, v116);
        }
        else
        {
          UxPodAttachThread(v113, &v172);
          UlDestroyCapturedResponse(v114);
          UxPodDetachThread(&v172);
        }
        v85 = a15;
      }
      PoolWithTagPriority = 0;
      appended = v119;
    }
    if ( HkeContextFromRequest )
      UlHkeDereferenceCalloutContext(HkeContextFromRequest, v17, v61);
  }
  if ( P )
  {
    ExFreePoolWithTag(P, 0);
    P = 0;
  }
  UxFreeCapturedAnsiString(&v170, v17, v61);
  UxFreeCapturedAnsiString(&v163, v109, v110);
  *v85 = PoolWithTagPriority;
  if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x100) != 0 )
    WPP_SF_qD(29, WPP_7cbf0d8611643fc15970b65376ef98c5_Traceguids, PoolWithTagPriority, (unsigned int)appended);
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x1c00bbfe0  mov     r11, rsp
0x1c00bbfe3  push    rbx
0x1c00bbfe4  push    rsi
0x1c00bbfe5  push    rdi
0x1c00bbfe6  push    r12
0x1c00bbfe8  push    r13
0x1c00bbfea  push    r14
0x1c00bbfec  push    r15
0x1c00bbfee  sub     rsp, 250h
0x1c00bbff5  mov     rax, cs:__security_cookie
0x1c00bbffc  xor     rax, rsp
0x1c00bbfff  mov     [rsp+288h+var_40], rax
0x1c00bc007  mov     [rsp+288h+var_178], r9
0x1c00bc00f  mov     r13, r8
0x1c00bc012  mov     [rsp+288h+var_180], r8
0x1c00bc01a  mov     r15, rdx
0x1c00bc01d  mov     [rsp+288h+var_110], rcx
0x1c00bc025  mov     [rsp+288h+var_A0], rdx
0x1c00bc02d  mov     [rsp+288h+var_98], r8
0x1c00bc035  mov     [rsp+288h+var_90], r9
0x1c00bc03d  mov     rax, [rsp+288h+arg_28]
0x1c00bc045  mov     [rsp+288h+var_160], rax
0x1c00bc04d  mov     rdi, [rsp+288h+arg_50]
0x1c00bc055  mov     rbx, [rsp+288h+arg_68]
0x1c00bc05d  mov     rdx, [rsp+288h+arg_70]
0x1c00bc065  mov     [rsp+288h+var_1F0], rdx
0x1c00bc06d  mov     eax, 2
0x1c00bc072  mov     [rsp+288h+var_198], ax
0x1c00bc07a  mov     [rsp+288h+var_1BC], eax
0x1c00bc081  xor     r14d, r14d
0x1c00bc084  xorps   xmm0, xmm0
0x1c00bc087  movups  xmmword ptr [r11-50h], xmm0
0x1c00bc08c  mov     [r11-108h], r14
0x1c00bc093  xor     eax, eax
0x1c00bc095  mov     [r11-0F0h], rax
0x1c00bc09c  mov     [r11-0E8h], r14
0x1c00bc0a3  mov     [r11-0E0h], rax
0x1c00bc0aa  mov     [r11-0D8h], r14
0x1c00bc0b1  mov     [r11-1A0h], r14
0x1c00bc0b8  mov     [r11-130h], r14
0x1c00bc0bf  mov     [r11-1C8h], r14w
0x1c00bc0c7  mov     [r11-170h], rax
0x1c00bc0ce  mov     [r11-168h], r14
0x1c00bc0d5  mov     [rsp+288h+var_1E5], al
0x1c00bc0dc  mov     [r11-1E0h], r14d
0x1c00bc0e3  mov     [r11-1D0h], r14d
0x1c00bc0ea  mov     [r11-188h], r14d
0x1c00bc0f1  mov     esi, r14d
0x1c00bc0f4  mov     [r11-1B8h], r14
0x1c00bc0fb  mov     [r11-148h], r14
0x1c00bc102  mov     [r11-140h], r14d
0x1c00bc109  mov     [r11-18Ch], r14d
0x1c00bc110  mov     [r11-14Ch], r14d
0x1c00bc117  mov     [r11-150h], r14d
0x1c00bc11e  mov     [r11-0D0h], r14
0x1c00bc125  mov     [rsp+288h+var_1E6], al
0x1c00bc12c  mov     [r11-190h], r14d
0x1c00bc133  mov     [r11-1CCh], r14w
0x1c00bc13b  mov     [r11-138h], r14
0x1c00bc142  mov     [rsp+288h+var_1E5+1], al
0x1c00bc149  mov     eax, 3E8h
0x1c00bc14e  mov     word ptr [rsp+288h+var_1C8+4], ax
0x1c00bc156  xor     eax, eax
0x1c00bc158  movups  [rsp+288h+var_88], xmm0
0x1c00bc160  mov     [r11-78h], rax
0x1c00bc164  xorps   xmm1, xmm1
0x1c00bc167  movups  [rsp+288h+var_C8], xmm1
0x1c00bc16f  mov     [r11-0B8h], rax
0x1c00bc176  mov     [r11-1D4h], r14d
0x1c00bc17d  mov     dword ptr [rsp+288h+Size], eax
0x1c00bc184  mov     [rsp+288h+var_1D8], eax
0x1c00bc18b  test    dword ptr cs:WPP_MAIN_CB.Queue, 100h
0x1c00bc195  jnz     loc_1C00ED3CC
0x1c00bc19b  movzx   eax, byte ptr [r11+68h]
0x1c00bc1a0  mov     [rsp+288h+var_1E8], al
0x1c00bc1a7  movzx   r12d, word ptr [r11+28h]
0x1c00bc1ac  mov     eax, 2710h
0x1c00bc1b1  cmp     r12w, ax
0x1c00bc1b5  jnb     loc_1C00BD11E
0x1c00bc1bb  test    r15, r15
0x1c00bc1be  jz      short loc_1C00BC238
0x1c00bc1c0  mov     rcx, r9; Irp
0x1c00bc1c3  call    cs:__imp_IoIs32bitProcess
0x1c00bc1ca  nop     dword ptr [rax+rax+00h]
0x1c00bc1cf  test    al, al
0x1c00bc1d1  jnz     short loc_1C00BC223
0x1c00bc1d3  test    dword ptr cs:WPP_MAIN_CB.Queue+4, 100h
0x1c00bc1dd  jnz     loc_1C00BD141
0x1c00bc1e3  mov     rax, r15
0x1c00bc1e6  and     eax, 7
0x1c00bc1e9  cmp     [rsp+288h+arg_30], 0
0x1c00bc1f1  jz      loc_1C00BD18F
0x1c00bc1f7  test    rax, rax
0x1c00bc1fa  jnz     loc_1C00BD17A
0x1c00bc200  lea     rcx, [r15+238h]
0x1c00bc207  mov     rax, cs:MmUserProbeAddress
0x1c00bc20e  mov     rdx, [rax]
0x1c00bc211  cmp     rcx, rdx
0x1c00bc214  ja      loc_1C00BD187
0x1c00bc21a  cmp     rcx, r15
0x1c00bc21d  jb      loc_1C00BD187
0x1c00bc223  movzx   eax, word ptr [r15+8]
0x1c00bc228  mov     word ptr [rsp+288h+var_1C8+4], ax
0x1c00bc230  test    rbx, rbx
0x1c00bc233  jz      short loc_1C00BC238
0x1c00bc235  mov     [rbx], ax
0x1c00bc238  movzx   eax, [rsp+288h+arg_30]
0x1c00bc240  mov     byte ptr [rsp+288h+Irp], al
0x1c00bc244  mov     r9, rdi
0x1c00bc247  mov     r8, [rsp+288h+var_160]
0x1c00bc24f  movzx   edx, r12w
0x1c00bc253  mov     rcx, r15
0x1c00bc256  call    UlpProbeHttpResponse
0x1c00bc25b  mov     edi, eax
0x1c00bc25d  mov     [rsp+288h+var_1F8], eax
0x1c00bc264  test    eax, eax
0x1c00bc266  js      loc_1C00BD1AA
0x1c00bc26c  mov     rax, [rsp+288h+var_110]
0x1c00bc274  test    rax, rax
0x1c00bc277  jz      loc_1C00BD1C1
0x1c00bc27d  mov     rax, [rax+8]
0x1c00bc281  mov     eax, [rax+114h]
0x1c00bc287  mov     [rsp+288h+var_1BC], eax
0x1c00bc28e  movzx   ebx, word ptr [rsp+288h+var_1BC]
0x1c00bc296  lea     rcx, [rsp+288h+var_1E5+5]
0x1c00bc29e  mov     [rsp+288h+var_250], rcx; __int64
0x1c00bc2a3  lea     rcx, [rsp+288h+var_1D4]
0x1c00bc2ab  mov     [rsp+288h+var_258], rcx; __int64
0x1c00bc2b0  mov     dword ptr [rsp+288h+var_260], eax; int
0x1c00bc2b4  movzx   eax, [rsp+288h+arg_48]
0x1c00bc2bc  mov     byte ptr [rsp+288h+Irp], al; char
0x1c00bc2c0  movzx   r9d, [rsp+288h+arg_30]
0x1c00bc2c9  mov     r8, r15
0x1c00bc2cc  mov     rdx, r13
0x1c00bc2cf  mov     rcx, [rsp+288h+var_178]; Irp
0x1c00bc2d7  call    UlComputeFixedHeaderSize
0x1c00bc2dc  mov     edi, eax
0x1c00bc2de  mov     [rsp+288h+var_1F8], eax
0x1c00bc2e5  test    eax, eax
0x1c00bc2e7  js      loc_1C00BD1D5
0x1c00bc2ed  cmp     [rsp+288h+arg_40], 0
0x1c00bc2f5  jnz     loc_1C00BCFEA
0x1c00bc2fb  cmp     byte ptr [r13+0DAEh], 0
0x1c00bc303  jnz     loc_1C00BCFEA
0x1c00bc309  mov     r8d, dword ptr [rsp+288h+var_1E5+5]
0x1c00bc311  test    r8d, r8d
0x1c00bc314  jz      short loc_1C00BC323
0x1c00bc316  mov     eax, cs:UlVariableHeaderSize
0x1c00bc31c  mov     [rsp+288h+var_18C], eax
0x1c00bc323  cmp     bx, 2
0x1c00bc327  jb      loc_1C00BC3ED
0x1c00bc32d  lea     rax, [rsp+288h+var_1E5+1]
0x1c00bc335  mov     [rsp+288h+var_260], rax
0x1c00bc33a  mov     byte ptr [rsp+288h+Irp], 1
0x1c00bc33f  movzx   ebx, [rsp+288h+arg_30]
0x1c00bc347  movzx   r9d, bl
0x1c00bc34b  mov     r8, [rsp+288h+var_178]
0x1c00bc353  mov     rdx, r15
0x1c00bc356  mov     rcx, r13
0x1c00bc359  call    UlExtractAndAppendAuthenticationResponseInfo
0x1c00bc35e  mov     edi, eax
0x1c00bc360  mov     [rsp+288h+var_1F8], eax
0x1c00bc367  test    eax, eax
0x1c00bc369  js      loc_1C00BD1EC
0x1c00bc36f  lea     rax, [rsp+288h+var_1D4]
0x1c00bc377  mov     [rsp+288h+var_240], rax; __int64
0x1c00bc37c  lea     rax, [rsp+288h+var_1D4+4]
0x1c00bc384  mov     [rsp+288h+var_248], rax; __int64
0x1c00bc389  lea     rax, [rsp+288h+var_1E5]
0x1c00bc391  mov     [rsp+288h+var_250], rax; __int64
0x1c00bc396  lea     rax, [rsp+288h+var_1C8]
0x1c00bc39e  mov     [rsp+288h+var_258], rax; __int64
0x1c00bc3a3  lea     rax, [rsp+288h+P]
0x1c00bc3ab  mov     [rsp+288h+var_260], rax; __int64
0x1c00bc3b0  lea     rax, [rsp+288h+var_140]
0x1c00bc3b8  mov     [rsp+288h+Irp], rax; __int64
0x1c00bc3bd  movzx   r9d, bl
0x1c00bc3c1  mov     r8, r15
0x1c00bc3c4  mov     rdx, r13
0x1c00bc3c7  mov     rcx, [rsp+288h+var_178]; Irp
0x1c00bc3cf  call    UlComputeMultipleKnownHeaderSize
0x1c00bc3d4  mov     edi, eax
0x1c00bc3d6  mov     [rsp+288h+var_1F8], eax
0x1c00bc3dd  test    eax, eax
0x1c00bc3df  js      loc_1C00BD203
0x1c00bc3e5  mov     r8d, dword ptr [rsp+288h+var_1E5+5]
0x1c00bc3ed  mov     edx, dword ptr [rsp+288h+Size]
0x1c00bc3f4  test    r8d, r8d
0x1c00bc3f7  jz      short loc_1C00BC407
0x1c00bc3f9  cmp     byte ptr [r13+0DAEh], 0
0x1c00bc401  jnz     loc_1C00BD21A
0x1c00bc407  cmp     dword ptr [r13+0A64h], 0
0x1c00bc40f  jnz     loc_1C00BD23D
0x1c00bc415  test    r8d, r8d
0x1c00bc418  jz      loc_1C00BD268
0x1c00bc41e  cmp     byte ptr [r13+0DAEh], 0
0x1c00bc426  jnz     loc_1C00BD268
0x1c00bc42c  movzx   ebx, r12w
0x1c00bc430  add     ebx, 2
0x1c00bc433  mov     [rsp+288h+var_1C0], ebx
0x1c00bc43a  cmp     [rsp+288h+var_1E8], 0
0x1c00bc442  jnz     loc_1C00BD271
0x1c00bc448  mov     r9d, dword ptr [rsp+288h+var_1D4+4]
0x1c00bc450  test    r9d, r9d
0x1c00bc453  jnz     loc_1C00BD2C1
0x1c00bc459  mov     eax, ebx
0x1c00bc45b  mov     [rsp+288h+var_154], eax
0x1c00bc462  test    r15, r15
0x1c00bc465  jz      short loc_1C00BC482
0x1c00bc467  movzx   ecx, word ptr [r15+18h]
0x1c00bc46c  mov     [rsp+288h+var_1CC], cx
0x1c00bc474  cmp     [rsp+288h+arg_58], 0
0x1c00bc47c  jnz     loc_1C00BD2DD
0x1c00bc482  lea     r10, [rax+rax*4]
0x1c00bc486  shl     r10, 4
0x1c00bc48a  mov     [rsp+288h+Size], r10
0x1c00bc492  mov     r11d, [rsp+288h+var_190]
0x1c00bc49a  mov     [rsp+288h+var_100], r11
0x1c00bc4a2  mov     eax, edx
0x1c00bc4a4  lea     rcx, [rax+rax*2]
0x1c00bc4a8  mov     eax, [rsp+288h+var_18C]
0x1c00bc4af  lea     rdx, [rax+rcx*8]
0x1c00bc4b3  lea     rcx, [r11+r9]
0x1c00bc4b7  mov     r12d, r8d
0x1c00bc4ba  add     rcx, rdx
0x1c00bc4bd  add     r12, rcx
0x1c00bc4c0  add     r12, r10
0x1c00bc4c3  mov     [rsp+288h+var_148], r12
0x1c00bc4cb  cmp     r12, 7FFFFFFFh
0x1c00bc4d2  ja      loc_1C00BD2FC
0x1c00bc4d8  cmp     [rsp+288h+arg_40], 0
0x1c00bc4e0  jnz     loc_1C00BD00C
0x1c00bc4e6  test    r15, r15
0x1c00bc4e9  jz      short loc_1C00BC4F9
0x1c00bc4eb  cmp     byte ptr [r13+685h], 0
0x1c00bc4f3  jnz     loc_1C00BD3BA
0x1c00bc4f9  lea     rcx, [r12+380h]
0x1c00bc501  cmp     rcx, 380h
0x1c00bc508  jbe     loc_1C00BD4D6
0x1c00bc50e  mov     eax, cs:UlResponseBufferSize
0x1c00bc514  cmp     rcx, rax
0x1c00bc517  ja      loc_1C00BD4D6
0x1c00bc51d  mov     dil, 1
0x1c00bc520  mov     [rsp+288h+var_1E7], dil
0x1c00bc528  cmp     cs:UxCompactMode, 0
0x1c00bc52f  jnz     loc_1C00BD423
0x1c00bc535  mov     eax, gs:1A4h
0x1c00bc53d  mov     rcx, cs:qword_1C0074210
0x1c00bc544  mov     r9, [rcx+20h]
0x1c00bc548  lea     r8d, [rax+1]
0x1c00bc54c  mov     edx, [rcx]
0x1c00bc54e  lea     eax, [rdx-1]
0x1c00bc551  cmp     r8d, edx
0x1c00bc554  cmovb   eax, r8d
0x1c00bc558  mov     rbx, [r9+rax*8]
0x1c00bc55c  cmp     byte ptr [rbx+70h], 0
0x1c00bc560  jnz     short loc_1C00BC56A
0x1c00bc562  mov     rdx, rbx
0x1c00bc565  call    PplpLazyInitializeLookasideList
0x1c00bc56a  inc     dword ptr [rbx+14h]
0x1c00bc56d  mov     rcx, rbx; ListHead
0x1c00bc570  call    cs:__imp_ExpInterlockedPopEntrySList
0x1c00bc577  nop     dword ptr [rax+rax+00h]
0x1c00bc57c  mov     rsi, rax
0x1c00bc57f  test    rax, rax
0x1c00bc582  jnz     short loc_1C00BC5A1
0x1c00bc584  inc     dword ptr [rbx+18h]
0x1c00bc587  mov     edx, [rbx+2Ch]
0x1c00bc58a  mov     rax, [rbx+30h]
0x1c00bc58e  mov     r9, rbx
0x1c00bc591  mov     r8d, [rbx+28h]
0x1c00bc595  mov     ecx, [rbx+24h]
0x1c00bc598  call    cs:__guard_dispatch_icall_fptr
0x1c00bc59e  mov     rsi, rax
0x1c00bc5a1  mov     [rsp+288h+var_1B8], rsi
0x1c00bc5a9  movzx   edi, [rsp+288h+var_1E7]
0x1c00bc5b1  mov     ebx, [rsp+288h+var_1C0]
0x1c00bc5b8  test    rsi, rsi
0x1c00bc5bb  jz      loc_1C00BD4B2
0x1c00bc5c1  mov     [rsp+288h+var_1F8], r14d
0x1c00bc5c9  lea     r12, [rsi]
0x1c00bc5cc  mov     [rsi+2Ch], dil
0x1c00bc5d0  mov     dword ptr [rsi+10h], 52496C55h
0x1c00bc5d7  mov     [rsi+1A0h], r14
0x1c00bc5de  mov     [rsi+1B0h], r14
0x1c00bc5e5  mov     [rsi+1C0h], r14
0x1c00bc5ec  mov     dword ptr [rsi+14h], 1
0x1c00bc5f3  mov     [rsi+364h], ebx
0x1c00bc5f9  mov     [rsi+360h], r14d
0x1c00bc600  mov     dword ptr [rsi+368h], 0FFFFFFFFh
0x1c00bc60a  mov     [rsi+350h], r14
0x1c00bc611  mov     [rsi+358h], r14
0x1c00bc618  lea     rcx, [rsi+378h]; void *
0x1c00bc61f  mov     [rsi+370h], rcx
0x1c00bc626  mov     r8, [rsp+288h+Size]; Size
0x1c00bc62e  xor     edx, edx; Val
0x1c00bc630  call    memset
0x1c00bc635  lock inc dword ptr [r13+30h]
0x1c00bc63a  mov     rsi, [rsp+288h+var_1B8]
0x1c00bc642  mov     [rsi+18h], r13
  ... truncated ...
```
