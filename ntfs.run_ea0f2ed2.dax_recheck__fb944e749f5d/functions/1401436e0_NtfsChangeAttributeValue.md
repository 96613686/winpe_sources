# NtfsChangeAttributeValue

- ea: `0x1401436e0`
- end: `0x140145163`
- name: `NtfsChangeAttributeValue`
- size: `6787`
- prototype: `__int64 __fastcall(int, int, int, int, SIZE_T Length, char, char, char, char, void *)`
- caller_count: `38`
- callee_count: `29`
- tags: `file_ops, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140024338`
- `0x140024914`
- `0x1400c22c4`
- `0x1400c8204`
- `0x1400e3340`
- `0x1401101f8`
- `0x140113fc8`
- `0x1401419ec`
- `0x140142360`
- `0x14014516c`
- `0x14014ecf0`
- `0x140156cc8`
- `0x1401580e0`
- `0x14015ab78`
- `0x14015b8b0`
- `0x14015df7c`
- `0x140180108`
- `0x1401913d4`
- `0x1401938ec`
- `0x1401c3700`
- `0x1401e7e28`
- `0x1401ea058`
- `0x1401efed8`
- `0x1401f1628`
- `0x1401f195c`
- `0x14020b5f4`
- `0x140213490`
- `0x140235e08`
- `0x14023ca60`
- `0x140242600`
- `0x14025cc9c`
- `0x14025f7f0`
- `0x140268608`
- `0x14026cc04`
- `0x14026e5e0`
- `0x1402768a8`
- `0x140278ed8`
- `0x140286f00`

## callees

- `0x140007ea0`
- `0x14000c290`
- `0x14000d510`
- `0x14001e810`
- `0x1400410a8`
- `0x140059234`
- `0x140059250`
- `0x1400593c0`
- `0x1400596c0`
- `0x1401250b0`
- `0x14013c2d0`
- `0x14013f374`
- `0x140140380`
- `0x1401436e0`
- `0x140150c80`
- `0x140151930`
- `0x140153070`
- `0x1401580e0`
- `0x140159768`
- `0x14015eaa0`
- `0x1401606a0`
- `0x1401620c0`
- `0x140162370`
- `0x140163f78`
- `0x14019a718`
- `0x1401e0660`
- `0x140212770`
- `0x1402447d0`
- `0x1402935b8`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14014510c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14014511c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14014512f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402a7637`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402a7681`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402a76a3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14014510c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14014511c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14014512f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402a7637`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402a7681`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402a76a3`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1401447b0`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140144a0e`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140145046`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1401447b0`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140144a0e`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140145046`
- `ntoskrnl!CcUnpinData` at `0x140144906`
- `ntoskrnl!CcUnpinData` at `0x140144a7a`
- `ntoskrnl!CcUnpinData` at `0x140144ab0`
- `ntoskrnl!CcUnpinData` at `0x140145015`
- `ntoskrnl!CcUnpinData` at `0x1402a76bc`
- `ntoskrnl!CcUnpinData` at `0x140144906`
- `ntoskrnl!CcUnpinData` at `0x140144a7a`
- `ntoskrnl!CcUnpinData` at `0x140144ab0`
- `ntoskrnl!CcUnpinData` at `0x140145015`
- `ntoskrnl!CcUnpinData` at `0x1402a76bc`
- `ntoskrnl!CcCopyWriteEx` at `0x140144677`
- `ntoskrnl!CcCopyWriteEx` at `0x140144677`
- `ntoskrnl!RtlCompareMemory` at `0x1401438e9`
- `ntoskrnl!RtlCompareMemory` at `0x1401438e9`
- `ntoskrnl!DbgPrint` at `0x140143cc2`
- `ntoskrnl!DbgPrint` at `0x140143cc2`

## pseudocode

```c
void __fastcall NtfsChangeAttributeValue(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        void *a4,
        SIZE_T Length,
        char a6,
        char a7,
        char a8,
        char a9,
        __int64 *a10)
{
  unsigned int v10; // r14d
  __int64 v13; // rbx
  unsigned int v14; // esi
  __int64 v15; // r10
  int v16; // r11d
  int v17; // r8d
  int v18; // edx
  int v19; // eax
  unsigned int v20; // ecx
  unsigned __int64 v21; // rcx
  __int64 v22; // rdx
  char v23; // cl
  __int64 v24; // r8
  _QWORD *v25; // rcx
  __int64 v26; // rax
  _QWORD *v27; // r10
  int v28; // r11d
  int v29; // r8d
  int v30; // ecx
  unsigned int v31; // r10d
  __int64 v32; // r9
  unsigned int v33; // esi
  char v34; // cl
  __int64 v35; // r8
  void *v36; // rbx
  __int64 v37; // rax
  __int64 v38; // rcx
  int v39; // eax
  unsigned int v40; // r9d
  __int64 v41; // rdx
  __int64 v42; // rax
  __int64 v43; // rcx
  char v44; // al
  bool v45; // zf
  int v46; // r9d
  __int16 *v47; // rax
  USHORT v48; // ax
  __int64 v49; // rbx
  __int64 v50; // r13
  __int64 v51; // r14
  __int64 v52; // rsi
  __int64 v53; // rax
  int v54; // edx
  unsigned int v55; // r15d
  signed __int64 v56; // r12
  _DWORD *v57; // r9
  unsigned int v58; // ecx
  unsigned int v59; // edx
  unsigned int v60; // eax
  void *v61; // rbx
  __int64 v62; // r12
  unsigned int v63; // r15d
  unsigned int v64; // eax
  __int64 v65; // r12
  unsigned int v66; // r9d
  unsigned int v67; // edx
  unsigned __int64 v68; // rcx
  char *v69; // r15
  __int64 v70; // r8
  _DWORD *v71; // r12
  int v72; // r10d
  int v73; // r11d
  __int64 v74; // rdx
  __int64 v75; // rcx
  void *v76; // rsi
  int v77; // r9d
  unsigned int v78; // eax
  unsigned int v79; // ebx
  int v80; // eax
  __int64 v81; // rdx
  __int16 v82; // ax
  USHORT v83; // ax
  unsigned int v84; // eax
  __int64 v85; // rdx
  unsigned int v86; // ebx
  unsigned int v87; // ebx
  unsigned int v88; // ebx
  char *PoolWithTag; // r15
  unsigned int v90; // r12d
  signed __int64 v91; // rdx
  signed __int64 v92; // r8
  signed __int64 v93; // r8
  signed __int64 v94; // rdx
  int v95; // r8d
  signed __int64 v96; // rdx
  signed __int64 v97; // rcx
  signed __int64 v98; // rax
  signed __int64 v99; // r9
  signed __int64 v100; // r8
  signed __int64 v101; // rdx
  __int64 v102; // rax
  __int64 v103; // rcx
  int v104; // esi
  __int64 v105; // [rsp+0h] [rbp-1E8h] BYREF
  void *v106; // [rsp+20h] [rbp-1C8h]
  __int64 v107; // [rsp+28h] [rbp-1C0h]
  char *v108; // [rsp+30h] [rbp-1B8h]
  __int64 v109; // [rsp+38h] [rbp-1B0h]
  unsigned int v110; // [rsp+40h] [rbp-1A8h]
  __int64 v111; // [rsp+48h] [rbp-1A0h]
  int v112; // [rsp+50h] [rbp-198h]
  unsigned int v113; // [rsp+58h] [rbp-190h]
  unsigned int v114; // [rsp+60h] [rbp-188h]
  bool v115; // [rsp+70h] [rbp-178h]
  char v116; // [rsp+71h] [rbp-177h]
  int v117; // [rsp+74h] [rbp-174h]
  int v118; // [rsp+78h] [rbp-170h]
  unsigned int Size; // [rsp+7Ch] [rbp-16Ch]
  __int16 Size_4; // [rsp+80h] [rbp-168h]
  char Size_6; // [rsp+82h] [rbp-166h]
  unsigned int i; // [rsp+84h] [rbp-164h]
  __int64 v123; // [rsp+88h] [rbp-160h]
  unsigned int v124; // [rsp+90h] [rbp-158h]
  char v125; // [rsp+94h] [rbp-154h]
  unsigned int v126; // [rsp+98h] [rbp-150h]
  char v127[4]; // [rsp+9Ch] [rbp-14Ch] BYREF
  PVOID Bcb; // [rsp+A0h] [rbp-148h] BYREF
  unsigned int v129; // [rsp+A8h] [rbp-140h]
  void *v130; // [rsp+B0h] [rbp-138h] BYREF
  void *Src; // [rsp+B8h] [rbp-130h]
  __int64 v132; // [rsp+C0h] [rbp-128h] BYREF
  UNICODE_STRING v133; // [rsp+C8h] [rbp-120h] BYREF
  unsigned int v134; // [rsp+D8h] [rbp-110h]
  unsigned int v135; // [rsp+E0h] [rbp-108h]
  __int64 v136; // [rsp+E8h] [rbp-100h]
  int v137; // [rsp+F0h] [rbp-F8h]
  _QWORD *v138; // [rsp+F8h] [rbp-F0h]
  unsigned int v139; // [rsp+100h] [rbp-E8h]
  __int64 v140; // [rsp+108h] [rbp-E0h]
  void *Source2; // [rsp+110h] [rbp-D8h]
  signed __int64 v142; // [rsp+118h] [rbp-D0h]
  _QWORD *v143; // [rsp+120h] [rbp-C8h]
  __int64 v144; // [rsp+128h] [rbp-C0h]
  __int64 v145; // [rsp+130h] [rbp-B8h]
  PVOID v146; // [rsp+138h] [rbp-B0h]
  int v147[2]; // [rsp+140h] [rbp-A8h]
  __int64 *v148; // [rsp+148h] [rbp-A0h]
  void *v149; // [rsp+150h] [rbp-98h]
  UNICODE_STRING v150; // [rsp+158h] [rbp-90h] BYREF
  unsigned int v151; // [rsp+168h] [rbp-80h]
  __int64 v152; // [rsp+170h] [rbp-78h]
  int v153[2]; // [rsp+178h] [rbp-70h]
  unsigned int v154; // [rsp+180h] [rbp-68h]
  __int64 *v155; // [rsp+188h] [rbp-60h]
  _BYTE v156[16]; // [rsp+190h] [rbp-58h] BYREF

  v155 = &v105;
  Source2 = a4;
  v10 = a3;
  v148 = a10;
  *(_QWORD *)v147 = a1;
  *(_QWORD *)v153 = a2;
  v134 = a3;
  Src = a4;
  v149 = a10;
  v140 = 0;
  v150 = 0;
  v124 = 0;
  v127[0] = 0;
  v130 = 0;
  Bcb = 0;
  *(_QWORD *)&v133.Length = 0;
  v133.Buffer = (PWSTR)v156;
  v140 = *a10;
  v13 = v140;
  v116 = *(_BYTE *)(v140 + 8);
  if ( v116 )
  {
    if ( *(_DWORD *)(v140 + 44) )
    {
      v104 = a2 + 8;
      NtfsAttachCorruption_BadOrOrphanFRS(a1, 2, 201177, (_DWORD)a4, a2 + 8, a2, 0);
      NtfsAttachRepairInfoPriv(a1, 256, v13, 0x32000311D9LL);
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(a1, 3221225730LL, 201177);
      NtfsRaiseStatusInternal(a1, -1073741566, v104, a2, 201177);
      __debugbreak();
    }
    v14 = *(_DWORD *)(v140 + 40);
  }
  else
  {
    v14 = *(_DWORD *)(v140 + 16);
  }
  v15 = *(_QWORD *)(a2 + 96);
  v144 = v15;
  v136 = v15;
  v16 = *(_DWORD *)v140;
  i = v16;
  v135 = v16;
  if ( a6 )
  {
    v20 = a3 + Length;
    v124 = a3 + Length;
    v17 = a3 + Length - v14;
    v117 = v10 + Length - v14;
    v18 = ((v10 + Length + 7) & 0xFFFFFFF8) - ((v14 + 7) & 0xFFFFFFF8);
    v115 = v10 + (unsigned int)Length > *(_DWORD *)(v15 + 360);
    v19 = Length;
  }
  else
  {
    v115 = 0;
    v124 = v14;
    v17 = 0;
    v117 = 0;
    v18 = 0;
    v19 = Length;
    v20 = v10 + Length;
  }
  v118 = v18;
  if ( a4 || v10 < v14 )
  {
    LODWORD(v123) = 0;
    if ( v10 > v14 )
      LODWORD(v123) = v10 - v14;
  }
  else
  {
    LODWORD(v123) = v19 + v10 - v14;
    v10 = v20;
    v134 = v20;
    LODWORD(Length) = 0;
  }
  if ( v116
    || v115
    || (v132 = a10[1], v21 = (unsigned int)(*(_DWORD *)(v132 + 28) - *(_DWORD *)(v132 + 24)), v18 > (int)v21)
    && (v21 = (unsigned int)(v17 + *(_DWORD *)(v140 + 4)), (unsigned int)v21 >= *(_DWORD *)(v15 + 344)) )
  {
    v146 = 0;
    v49 = v140;
    v150.Length = 2 * *(unsigned __int8 *)(v140 + 9);
    v150.MaximumLength = v150.Length;
    v150.Buffer = (PWSTR)(v140 + *(unsigned __int16 *)(v140 + 10));
    v108 = v127;
    v107 = 0;
    LOBYTE(v106) = 0;
    v50 = *(_QWORD *)v153;
    v51 = *(_QWORD *)v147;
    v52 = (__int64)NtfsCreateScb(*(__int64 *)v147, *(__int64 *)v153, *(_DWORD *)v140, &v150, 0, 0, v127);
    v53 = NtfsSnapshotScb(v51, v52);
    LOBYTE(v54) = 0;
    v118 = v54;
    Size_4 = 0;
    Size_6 = 0;
    LOBYTE(v53) = 0;
    v117 = v53;
    v125 = 0;
    v132 = 0;
    v142 = 0;
    if ( (*(_DWORD *)(v52 + 200) & 0x20) == 0 )
    {
      NtfsUpdateScbFromAttribute(v51, v52, v49);
      NtfsSnapshotScb(v51, v52);
      LOBYTE(v54) = v118;
    }
    v55 = v124;
    if ( a6 && v124 > *(_DWORD *)(v52 + 32) )
    {
      v54 = (unsigned __int8)v54;
      if ( v135 == 32 )
        v54 = 1;
      v118 = v54;
      LOBYTE(Size_4) = v54;
    }
    v56 = v124;
    v142 = v124;
    *(_QWORD *)v147 = v124 - *(_QWORD *)(v52 + 32);
    v132 = v134;
    if ( !*(_BYTE *)(v49 + 8) )
      goto LABEL_109;
    NtfsCreateInternalAttributeStream(v51, v52, 1, 0, (__int64)L",.", 0);
    while ( 1 )
    {
      if ( *(_DWORD *)(v49 + 44) )
      {
        v52 = v50 + 8;
        v55 = 201766;
        NtfsAttachCorruption_BadOrOrphanFRS(v51, 2, 201766, (_DWORD)v57, v50 + 8, v50, 0);
        NtfsAttachRepairInfoPriv(v51, 256, v49, 0x3500031426LL);
        if ( NtfsStatusDebugFlags )
          NtfsStatusTraceAndDebugInternal(v51, 3221225730LL, 201766);
        NtfsRaiseStatusInternal(v51, -1073741566, v50 + 8, v50, 201766);
      }
      else
      {
        v58 = *(_DWORD *)(v49 + 40);
        if ( v55 <= v58 )
        {
          v59 = *(_DWORD *)(v136 + 356);
          if ( v59 <= v58 - v55
            && (*(_DWORD *)(v52 + 256) != 32
             || v50 != *(_QWORD *)(*(_QWORD *)(v136 + 48) + 184LL) && 2 * (v59 + v55) < v58) )
          {
            HIBYTE(Size_4) = 1;
          }
          goto LABEL_79;
        }
      }
      v145 = 0;
      if ( a9 )
      {
        if ( !v133.Length )
        {
          v82 = *(unsigned __int8 *)(v49 + 9);
          if ( (_BYTE)v82 )
          {
            v83 = 2 * v82;
            v133.MaximumLength = v83;
            v133.Length = v83;
            if ( v83 > 0x10u )
            {
              v133.Buffer = (PWSTR)ExAllocatePoolWithTag((POOL_TYPE)528, v83, 0x4146744Eu);
              v83 = v133.Length;
            }
            if ( v83 )
              memmove(v133.Buffer, (const void *)(v49 + *(unsigned __int16 *)(v49 + 10)), v83);
          }
        }
        Size_6 = 1;
      }
      v84 = *(_DWORD *)(v49 + 40);
      v55 -= v84;
      v85 = v55;
      v145 = v55;
      if ( *(_DWORD *)(v52 + 256) == 32 )
      {
        if ( v84 <= 0x4000 )
        {
          if ( v84 <= 0x1000 )
            goto LABEL_162;
          v85 = v55 + 4096LL;
        }
        else
        {
          v85 = v55 + 0x2000LL;
        }
        v145 = v85;
      }
LABEL_162:
      NtfsAddAllocation(v51, (v85 + *(unsigned int *)(v136 + 480)) >> *(_BYTE *)(v136 + 488), 0, 0);
      if ( (*(_DWORD *)(v52 + 200) & 0x10) != 0 )
      {
        *(_QWORD *)(v50 + 160) = *(_QWORD *)(v52 + 472);
        *(_DWORD *)(v50 + 184) |= 0x40000000u;
      }
LABEL_79:
      v60 = Length;
      v61 = Src;
      if ( (_DWORD)Length && Src || a7 && a6 )
      {
        v62 = *(_QWORD *)(v52 + 40);
        if ( v132 >= v62 )
        {
          v63 = v132 - v62;
          v139 = v132 - v62;
          v115 = 0;
        }
        else
        {
          v63 = 0;
          v139 = 0;
          v115 = 1;
        }
        if ( a7 )
        {
          v137 = 0;
          v129 = 0;
          v64 = v62 & 0xFFF;
          i = v64;
          v126 = v64;
          v65 = (unsigned int)v62 & 0xFFFFF000;
          v123 = v65;
          while ( 1 )
          {
            v138 = (_QWORD *)v65;
            if ( !v63 )
              break;
            v86 = 4096 - v64;
            if ( 4096 - v64 > v63 )
              v86 = v63;
            Size = v86;
            if ( Bcb )
            {
              CcUnpinData(Bcb);
              Bcb = 0;
              v64 = i;
            }
            v87 = v64 + v86;
            NtfsPinStream(v51, v52, v65, v87, &Bcb, &v130);
            v130 = (char *)v130 + i;
            v114 = v87;
            v88 = Size;
            NtfsWriteLog(v51, v52, (_DWORD)Bcb, 8, 0, Size, 0, 0, 0, v65, i, 0, v114);
            memset(v130, 0, v88);
            v63 -= v88;
            v139 = v63;
            v65 = (__int64)(v138 + 512);
            v123 = (__int64)(v138 + 512);
            v64 = 0;
            i = 0;
            v126 = 0;
          }
          v123 = (unsigned int)v132 & 0xFFFFF000;
          LODWORD(v61) = v132 & 0xFFF;
          v126 = (unsigned int)v61;
          v66 = Length;
          v67 = Length;
          v129 = Length;
          if ( v115 )
          {
            LODWORD(v62) = *(_DWORD *)(v52 + 40) - v132;
            v137 = v62;
            if ( (_BYTE)v118 && (unsigned int)((_DWORD)v61 + Length) > 0x1000 )
            {
              PoolWithTag = (char *)ExAllocatePoolWithTag(
                                      (POOL_TYPE)(PoolType | 0x10),
                                      (unsigned int)Length,
                                      0x4146744Eu);
              v146 = PoolWithTag;
              memmove(PoolWithTag, Src, (unsigned int)Length);
              v68 = (unsigned __int64)PoolWithTag;
              Src = PoolWithTag;
              LOBYTE(Size_4) = 0;
              LODWORD(v61) = v126;
              v67 = v129;
              v66 = Length;
            }
            else
            {
              v68 = (unsigned __int64)Src;
            }
            if ( !a6 )
            {
              if ( (unsigned int)v62 > v66 )
                LODWORD(v62) = v66;
              v137 = v62;
            }
            goto LABEL_90;
          }
          goto LABEL_91;
        }
        if ( v63 )
        {
          NtfsCheckpointCurrentTransaction(v51);
          if ( !(unsigned __int8)NtfsZeroData(v51, v52, *(PFILE_OBJECT *)(v52 + 280), v63, 0, 0) )
            NtfsRaiseStatusInternal(v51, -1073741608, 0, 0, 202304);
          v60 = Length;
        }
        v55 = 1;
        LOBYTE(v57) = *(_BYTE *)(v51 + 12) & 1;
        if ( !(unsigned __int8)CcCopyWriteEx(*(_QWORD *)(v52 + 280), &v132, v60, v57, v61, 0) )
        {
          NtfsRaiseStatusInternal(v51, -1073741608, 0, 0, 202316);
LABEL_140:
          for ( i = v55 + (_DWORD)v61; ; i = v78 + (_DWORD)v61 )
          {
            v148 = (__int64 *)(v68 & -(__int64)(v55 != 0));
            v118 = v55 != 0 ? 8 : 0;
            if ( Bcb )
            {
              CcUnpinData(Bcb);
              Bcb = 0;
            }
            NtfsPinStream(v51, v52, v123, i, &Bcb, &v130);
            v130 = (char *)v130 + (unsigned int)v61;
            v112 = (int)v61;
            v79 = Size;
            NtfsWriteLog(v51, v52, (_DWORD)Bcb, v118, (__int64)v148, v55, 8, (__int64)v130, Size, v123, v112, 0, i);
            if ( v55 )
              memmove(v130, Src, v55);
            LODWORD(v62) = v62 - v79;
            v137 = v62;
            v67 = v129 - v55;
            v129 -= v55;
            v123 += 4096;
            LODWORD(v61) = 0;
            v126 = 0;
            v68 = (unsigned __int64)Src + v55;
            Src = (void *)v68;
LABEL_90:
            if ( !(_DWORD)v62 )
              break;
            v78 = 4096 - (_DWORD)v61;
            v55 = 4096 - (_DWORD)v61;
            if ( 4096 - (int)v61 > v67 )
              v55 = v67;
            if ( v78 >= (unsigned int)v62 )
              v78 = v62;
            Size = v78;
            if ( v78 <= v55 )
              goto LABEL_140;
          }
LABEL_91:
          v69 = (char *)Src;
          while ( v67 )
          {
            v90 = 4096 - (_DWORD)v61;
            if ( 4096 - (int)v61 > v67 )
              v90 = v67;
            if ( Bcb )
            {
              CcUnpinData(Bcb);
              Bcb = 0;
            }
            NtfsPinStream(v51, v52, v123, v90, &Bcb, &v130);
            v130 = (char *)v130 + (unsigned int)v61;
            NtfsWriteLog(v51, v52, (_DWORD)Bcb, 8, (__int64)v69, v90, 0, 0, 0, v123, (_DWORD)v61, 0, v90 + (_DWORD)v61);
            memmove(v130, v69, v90);
            v67 = v129 - v90;
            v129 -= v90;
            v123 += 4096;
            v126 = 0;
            v69 += v90;
            Src = v69;
            LODWORD(v61) = 0;
          }
          v55 = 1;
        }
        v57 = (_DWORD *)(v132 + (unsigned int)Length);
        v70 = *(_QWORD *)(v52 + 40);
        v71 = (_DWORD *)(v52 + 200);
        v72 = 512;
        if ( (__int64)v57 <= v70 )
        {
          v73 = 0x20000;
          goto LABEL_96;
        }
        if ( (*v71 & 0x200) != 0 )
          v70 = *(_QWORD *)(v52 + 40);
        if ( (*v71 & 0x20000) != 0 )
        {
          v91 = *(_QWORD *)(v52 + 464);
          if ( v91 >= (__int64)v57 )
          {
            if ( v70 <= (__int64)v57 )
              goto LABEL_126;
            if ( *(_QWORD *)(*(_QWORD *)(v52 + 288) + 16LL) )
            {
              if ( v57 == (_DWORD *)0x7FFFFFFFFFFFFFFFLL )
              {
                *(_QWORD *)(v52 + 464) = 0x7FFFFFFFFFFFFFFFLL;
              }
              else
              {
                v92 = ((unsigned __int64)v57 + 4095) & 0xFFFFFFFFFFFFF000uLL;
                if ( v92 < v91 )
                  *(_QWORD *)(v52 + 464) = v92;
              }
              goto LABEL_126;
            }
          }
          *(_QWORD *)(v52 + 464) = v57;
        }
LABEL_126:
        *(_QWORD *)(v52 + 40) = v57;
        v80 = (unsigned __int8)v117;
        if ( a7 )
          v80 = 1;
        v117 = v80;
        v125 = v80;
        SetFlagInterlocked(v52 + 200, 4);
LABEL_96:
        if ( !a6 )
        {
LABEL_97:
          v56 = v142;
          goto LABEL_98;
        }
        if ( (*v71 & v73) == 0 )
        {
LABEL_130:
          *(_QWORD *)(v52 + 40) = v57;
          goto LABEL_97;
        }
        v93 = *(_QWORD *)(v52 + 464);
        if ( v93 >= (__int64)v57 )
        {
          if ( *(_QWORD *)(v52 + 40) <= (__int64)v57 )
            goto LABEL_130;
          if ( *(_QWORD *)(*(_QWORD *)(v52 + 288) + 16LL) && v57 != (_DWORD *)0x7FFFFFFFFFFFFFFFLL )
          {
            v94 = ((unsigned __int64)v57 + 4095) & 0xFFFFFFFFFFFFF000uLL;
            if ( v94 < v93 )
              *(_QWORD *)(v52 + 464) = v94;
            goto LABEL_130;
          }
        }
        *(_QWORD *)(v52 + 464) = v57;
        goto LABEL_130;
      }
      v72 = 512;
      v73 = 0x20000;
LABEL_98:
      if ( !a6 )
        goto LABEL_99;
      v57 = (_DWORD *)(v52 + 200);
      v95 = *(_DWORD *)(v52 + 200);
      if ( (v95 & v73) != 0 && *(_QWORD *)(v52 + 32) < v56 )
      {
        v96 = *(_QWORD *)(v52 + 464);
        v97 = v96;
        if ( v56 < v96 )
          v97 = v56;
        v98 = *(_QWORD *)(v52 + 40);
        if ( v97 > v98 )
        {
          if ( (v95 & v72) != 0 )
          {
            v96 = *(_QWORD *)(v52 + 464);
            v98 = *(_QWORD *)(v52 + 40);
          }
          if ( (*v57 & v73) == 0 )
            goto LABEL_218;
          if ( v96 < v97 )
            goto LABEL_223;
          if ( v98 > v97 )
          {
            if ( *(_QWORD *)(*(_QWORD *)(v52 + 288) + 16LL) && v97 != 0x7FFFFFFFFFFFFFFFLL )
            {
              v99 = (v97 + 4095) & 0xFFFFFFFFFFFFF000uLL;
              if ( v99 < v96 )
                *(_QWORD *)(v52 + 464) = v99;
              v57 = (_DWORD *)(v52 + 200);
              goto LABEL_218;
            }
LABEL_223:
            *(_QWORD *)(v52 + 464) = v97;
          }
LABEL_218:
          *(_QWORD *)(v52 + 40) = v97;
        }
      }
      *(_QWORD *)(v52 + 32) = v56;
      if ( a7 )
      {
        if ( (*v57 & v73) != 0 )
        {
          v100 = *(_QWORD *)(v52 + 464);
          if ( v100 < v56 )
            goto LABEL_229;
          if ( *(_QWORD *)(v52 + 40) > v56 )
          {
            if ( !*(_QWORD *)(*(_QWORD *)(v52 + 288) + 16LL) || v56 == 0x7FFFFFFFFFFFFFFFLL )
            {
LABEL_229:
              *(_QWORD *)(v52 + 464) = v56;
            }
            else
            {
              v101 = (v56 + 4095) & 0xFFFFFFFFFFFFF000uLL;
              if ( v101 < v100 )
                *(_QWORD *)(v52 + 464) = v101;
            }
          }
        }
        *(_QWORD *)(v52 + 40) = v56;
      }
      v74 = v136;
      if ( v135 == 32 && *(__int64 *)v147 > 0 )
      {
        v102 = *(_QWORD *)(v136 + 104);
        if ( v102 )
        {
          if ( v50 == *(_QWORD *)(v102 + 184) )
          {
            NtfsCheckSecurityFragmentation(v51, v136);
LABEL_99:
            v74 = v136;
          }
        }
      }
      v75 = *(_QWORD *)(v52 + 40);
      if ( v75 < *(_QWORD *)(v52 + 464) && (*(_BYTE *)(v52 + 460) || (*(_DWORD *)(v52 + 512) & 1) != 0) )
        *(_QWORD *)(v52 + 464) = v75;
      if ( HIBYTE(Size_4) )
      {
        if ( *(_DWORD *)(v52 + 256) == 32 )
        {
          v56 += *(unsigned int *)(v74 + 356);
          v142 = v56;
        }
        NtfsDeleteAllocation(v51, 0x7FFFFFFFFFFFFFFFLL, 1, 0);
        if ( (*(_DWORD *)(v52 + 200) & 0x10) != 0 )
        {
          *(_QWORD *)(v50 + 160) = *(_QWORD *)(v52 + 472);
          *(_QWORD *)(v50 + 168) = *(_QWORD *)(v52 + 32);
          *(_DWORD *)(v50 + 184) |= 0x40000008u;
        }
      }
      else if ( a6 )
      {
        v81 = *(_QWORD *)(v52 + 280);
        if ( !v81 )
        {
          if ( a8 )
          {
            v81 = 0;
            v103 = *(_QWORD *)(*(_QWORD *)(v51 + 112) + 184LL);
            if ( *(_QWORD *)(*(_QWORD *)(v103 + 48) + 40LL) == *(_QWORD *)(v52 + 288) + 16LL )
              v81 = *(_QWORD *)(v103 + 48);
          }
          else
          {
            NtfsCreateInternalAttributeStream(v51, v52, 0, 0, (__int64)L".0", 0);
            v81 = *(_QWORD *)(v52 + 280);
          }
        }
        NtfsSetBothCacheSizes(v51, v81, v52 + 24);
        if ( (*(_DWORD *)(v52 + 200) & 0x10) != 0 )
        {
          *(_QWORD *)(v50 + 168) = *(_QWORD *)(v52 + 32);
          *(_DWORD *)(v50 + 184) |= 8u;
        }
        LOBYTE(v57) = v117;
        goto LABEL_135;
      }
      if ( !(_BYTE)v117 )
        goto LABEL_104;
      LOBYTE(v57) = 1;
LABEL_135:
      NtfsWriteFileSizes(v51, v52, 0, (_DWORD)v57, 1, 1);
LABEL_104:
      if ( !Size_6
        || (v76 = v149,
            NtfsCleanupAttributeContext(v75, v149),
            memset(v76, 0, 0x58u),
            v49 = v50 + 8,
            LOBYTE(v108) = 0,
            (unsigned __int8)NtfsLookupInFileRecord(v51, v50, v50 + 8, v135, &v133, 0, (_DWORD)v108, 0, 0, v76)) )
      {
        if ( v146 )
          ExFreePoolWithTag(v146, 0);
        if ( (_BYTE *)v133.Buffer != v156 )
          ExFreePoolWithTag(v133.Buffer, 0);
        if ( Bcb )
          CcUnpinData(Bcb);
        return;
      }
      v52 = 0x3600031733LL;
      NtfsAttachCorruption_BadOrOrphanFRS(v51, 2, 202547, v77, v50 + 8, v50, 0);
      NtfsAttachRepairInfoPriv(v51, 256, 0, 0x3600031733LL);
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(v51, 3221225730LL, 202547);
      NtfsRaiseStatusInternal(v51, -1073741566, v50 + 8, v50, 202547);
LABEL_109:
      NtfsConvertToNonresident(v51, v50, v49, a8, v149);
      v49 = *v148;
      v140 = *v148;
    }
  }
  Size = v14;
  if ( v18 > 0 || v17 && v16 != 128 )
  {
    v48 = 2 * *(unsigned __int8 *)(v140 + 9);
    v133.MaximumLength = v48;
    v133.Length = v48;
    if ( v48 > 0x10u )
    {
      v21 = (unsigned __int64)ExAllocatePoolWithTag((POOL_TYPE)528, v48, 0x4146744Eu);
      v133.Buffer = (PWSTR)v21;
      v48 = v133.Length;
    }
    else
    {
      v21 = (unsigned __int64)v156;
    }
    if ( v48 )
      memmove((void *)v21, (const void *)(v13 + *(unsigned __int16 *)(v13 + 10)), v48);
  }
  if ( v118 <= 0 )
  {
    v143 = a10 + 6;
    v22 = *(_QWORD *)(a2 + 96);
    v23 = *(_BYTE *)(v22 + 492);
    if ( a10[6] )
      v24 = *(unsigned int *)(a10[4] + 16);
    else
      v24 = *(unsigned int *)(a2 + 8);
    v138 = a10 + 2;
    v106 = a10 + 2;
    NtfsPinMappedData(a1, *(_QWORD *)(v22 + 48), v24 << v23);
    if ( Source2 )
    {
      LODWORD(v26) = RtlCompareMemory(
                       (const void *)(v13 + v10 + *(unsigned __int16 *)(v13 + 20)),
                       Source2,
                       (unsigned int)Length);
      Source2 = (char *)Source2 + (unsigned int)v26;
      Src = Source2;
      v10 += v26;
      v134 = v10;
      LODWORD(Length) = Length - v26;
      v25 = a10 + 6;
      LODWORD(v26) = v132;
      v27 = a10 + 2;
    }
    else
    {
      LODWORD(v26) = v132;
LABEL_44:
      v25 = a10 + 6;
      v27 = a10 + 2;
      v143 = a10 + 6;
      v138 = a10 + 2;
    }
    v28 = v13 - v26;
    v118 = v13 - v26;
    v29 = v123;
    if ( (_DWORD)v123 )
    {
      v40 = v14 + *(unsigned __int16 *)(v13 + 20);
      Size = v40;
      if ( *v25 )
        v41 = *(unsigned int *)(a10[4] + 16);
      else
        v41 = *(unsigned int *)(a2 + 8);
      v42 = NtfsWriteLog(
              a1,
              *(_QWORD *)(v144 + 48),
              *v27,
              7,
              0,
              v123,
              7,
              0,
              0,
              v41 << *(_BYTE *)(*(_QWORD *)(a2 + 96) + 492LL),
              v28,
              v40,
              *(_DWORD *)(v144 + 360));
      v43 = v132;
      *(_QWORD *)(v132 + 8) = v42;
      LOBYTE(v107) = 1;
      NtfsRestartChangeValue(v43, (unsigned int)v118, Size, 0, v123, v107);
      v29 = v123;
      v28 = v118;
    }
    v30 = v117;
    if ( !(_DWORD)Length )
    {
      if ( v29 )
        goto LABEL_27;
      if ( !v117 )
        goto LABEL_59;
    }
    v31 = v10 + *(unsigned __int16 *)(v13 + 20);
    Size = v31;
    if ( v10 < v14 )
    {
      v32 = v13 + v31;
      v152 = v32;
      if ( v117 )
        v33 = v14 - v10;
      else
        v33 = Length;
    }
    else
    {
      v32 = 0;
      v152 = 0;
      v33 = 0;
    }
    v34 = *(_BYTE *)(*(_QWORD *)(a2 + 96) + 492LL);
    if ( *v143 )
      v35 = *(unsigned int *)(a10[4] + 16);
    else
      v35 = *(unsigned int *)(a2 + 8);
    v114 = *(_DWORD *)(v144 + 360);
    v113 = v31;
    v112 = v28;
    v111 = v35 << v34;
    v110 = v33;
    v109 = v32;
    LODWORD(v108) = 7;
    LODWORD(v107) = Length;
    v36 = Source2;
    v37 = NtfsWriteLog(
            a1,
            *(_QWORD *)(v144 + 48),
            *v138,
            7,
            (__int64)Source2,
            Length,
            7,
            v32,
            v33,
            v35 << v34,
            v28,
            v31,
            v114);
    v38 = v132;
    *(_QWORD *)(v132 + 8) = v37;
    LOBYTE(v107) = v117 != 0;
    NtfsRestartChangeValue(v38, (unsigned int)v118, Size, v36, Length, v107);
    v30 = v117;
LABEL_27:
    if ( v30 )
    {
      v39 = i;
      if ( i != 128 )
      {
LABEL_51:
        v47 = NtfsCreateScb(a1, a2, v39, &v133, 1, 0, 0);
        if ( v47 )
          *((_DWORD *)v47 + 50) &= 0xFFFFFDDF;
      }
    }
    goto LABEL_59;
  }
  v44 = 1;
  while ( 1 )
  {
    if ( v44 )
      goto LABEL_42;
    NtfsCleanupAttributeContext(v21, a10);
    memset(a10, 0, 0x58u);
    LOBYTE(v108) = 0;
    if ( !(unsigned __int8)NtfsLookupInFileRecord(a1, a2, a2 + 8, i, &v133, 0, (_DWORD)v108, 0, 0, a10) )
      break;
    v13 = *a10;
    v140 = *a10;
    if ( i == 32 )
    {
      if ( *(_BYTE *)(v13 + 8) )
        goto LABEL_56;
      v14 = *(_DWORD *)(v13 + 16);
      v154 = v14;
      if ( v14 > Size )
      {
        v124 += v14 - Size;
        v10 += v14 - Size;
        v134 = v10;
        DbgPrint(
          "NtfsChangeAttributeValue: Grown %x, NewSize %x, ValueOffset %x, ValueLength %x, CurrentLength %x, ZeroLength %x\n",
          v14 - Size,
          v124,
          v10,
          Length,
          v14,
          v123);
        Size = v14;
        v151 = v14;
        if ( v124 > *(_DWORD *)(v144 + 360) )
        {
          v39 = local_unwind_0(v155, &loc_140143F20);
          goto LABEL_51;
        }
      }
    }
LABEL_42:
    v116 = 0;
    v45 = (unsigned __int8)NtfsChangeAttributeSize(
                             a1,
                             a2,
                             (*(unsigned __int16 *)(v13 + 20) + v124 + 7) & 0xFFFFFFF8,
                             a10) == 0;
    v44 = 0;
    if ( !v45 )
    {
      v26 = a10[1];
      v132 = v26;
      v13 = *a10;
      v140 = *a10;
      goto LABEL_44;
    }
  }
  NtfsAttachCorruption_BadOrOrphanFRS(a1, 2, 201341, v46, a2 + 8, a2, 0);
  NtfsAttachRepairInfoPriv(a1, 256, 0, 0x330003127DLL);
  if ( NtfsStatusDebugFlags )
    NtfsStatusTraceAndDebugInternal(a1, 3221225730LL, 201341);
  NtfsRaiseStatusInternal(a1, -1073741566, a2 + 8, a2, 201341);
LABEL_56:
  NtfsAttachCorruption_BadOrOrphanFRS(a1, 2, 201370, v46, a2 + 8, a2, 0);
  NtfsAttachRepairInfoPriv(a1, 256, 0, 0x340003129ALL);
  if ( NtfsStatusDebugFlags )
    NtfsStatusTraceAndDebugInternal(a1, 3221225730LL, 201370);
  NtfsRaiseStatusInternal(a1, -1073741566, a2 + 8, a2, 201370);
LABEL_59:
  if ( (_BYTE *)v133.Buffer != v156 )
    ExFreePoolWithTag(v133.Buffer, 0);
}

```

## disassembly

```asm
0x1401436e0  mov     r11, rsp
0x1401436e3  push    rbx
0x1401436e4  push    rsi
0x1401436e5  push    rdi
0x1401436e6  push    r12
0x1401436e8  push    r13
0x1401436ea  push    r14
0x1401436ec  push    r15
0x1401436ee  sub     rsp, 1B0h
0x1401436f5  mov     rax, cs:__security_cookie
0x1401436fc  xor     rax, rsp
0x1401436ff  mov     [rsp+1E8h+var_48], rax
0x140143707  mov     [rsp+1E8h+var_60], rsp
0x14014370f  mov     [r11-0D8h], r9
0x140143716  mov     r14d, r8d
0x140143719  mov     r15, rdx
0x14014371c  mov     r12, rcx
0x14014371f  mov     r13, [rsp+1E8h+arg_48]
0x140143727  mov     [rsp+1E8h+var_A0], r13
0x14014372f  mov     qword ptr [rsp+1E8h+var_A8], rcx
0x140143737  mov     qword ptr [rsp+1E8h+var_70], rdx
0x14014373f  mov     [r11-110h], r8d
0x140143746  mov     [r11-130h], r9
0x14014374d  mov     [rsp+1E8h+var_98], r13
0x140143755  xor     edi, edi
0x140143757  mov     [r11-0E0h], rdi
0x14014375e  xorps   xmm0, xmm0
0x140143761  movups  [rsp+1E8h+var_90], xmm0
0x140143769  mov     [rsp+1E8h+var_158], edi
0x140143770  mov     [rsp+1E8h+var_14C], dil
0x140143778  mov     [r11-138h], rdi
0x14014377f  mov     [r11-148h], rdi
0x140143786  mov     [r11-120h], rdi
0x14014378d  lea     rax, [r11-58h]
0x140143791  mov     [r11-118h], rax
0x140143798  mov     rbx, [r13+0]
0x14014379c  mov     [r11-0E0h], rbx
0x1401437a3  mov     al, [rbx+8]
0x1401437a6  mov     [rsp+1E8h+var_177], al
0x1401437aa  test    al, al
0x1401437ac  jnz     loc_140143F0F
0x1401437b2  mov     esi, [rbx+10h]
0x1401437b5  mov     r10, [rdx+60h]
0x1401437b9  mov     [rsp+1E8h+var_C0], r10
0x1401437c1  mov     [rsp+1E8h+var_100], r10
0x1401437c9  mov     r11d, [rbx]
0x1401437cc  mov     [rsp+1E8h+var_164], r11d
0x1401437d4  mov     [rsp+1E8h+var_108], r11d
0x1401437dc  cmp     [rsp+1E8h+arg_28], dil
0x1401437e4  jnz     loc_140143E82
0x1401437ea  mov     [rsp+1E8h+var_178], dil
0x1401437ef  mov     [rsp+1E8h+var_158], esi
0x1401437f6  mov     r8d, edi
0x1401437f9  mov     [rsp+1E8h+var_174], edi
0x1401437fd  mov     edx, edi
0x1401437ff  mov     eax, dword ptr [rsp+1E8h+Length]
0x140143806  lea     ecx, [r14+rax]
0x14014380a  mov     [rsp+1E8h+var_170], edx
0x14014380e  test    r9, r9
0x140143811  jz      loc_140143E55
0x140143817  mov     dword ptr [rsp+1E8h+var_160], edi
0x14014381e  cmp     r14d, esi
0x140143821  ja      loc_1401450E1
0x140143827  cmp     [rsp+1E8h+var_177], dil
0x14014382c  jnz     loc_140143F20
0x140143832  cmp     [rsp+1E8h+var_178], dil
0x140143837  jnz     loc_140143F20
0x14014383d  mov     rcx, [r13+8]
0x140143841  mov     [rsp+1E8h+var_128], rcx
0x140143849  mov     eax, [rcx+18h]
0x14014384c  mov     ecx, [rcx+1Ch]
0x14014384f  sub     ecx, eax
0x140143851  cmp     edx, ecx
0x140143853  jg      loc_1401450F2
0x140143859  mov     dword ptr [rsp+1E8h+Size], esi
0x14014385d  test    edx, edx
0x14014385f  jg      loc_140143EC4
0x140143865  test    r8d, r8d
0x140143868  jnz     loc_140145026
0x14014386e  cmp     [rsp+1E8h+var_170], edi
0x140143872  jg      loc_140143B71
0x140143878  lea     rax, [r13+30h]
0x14014387c  mov     [rsp+1E8h+var_C8], rax
0x140143884  mov     rdx, [r15+60h]
0x140143888  mov     cl, [rdx+1ECh]
0x14014388e  cmp     [rax], rdi
0x140143891  jz      loc_140143A6B
0x140143897  mov     rax, [r13+20h]
0x14014389b  mov     r8d, [rax+10h]
0x14014389f  shl     r8, cl
0x1401438a2  lea     rax, [r13+10h]
0x1401438a6  mov     [rsp+1E8h+var_F0], rax
0x1401438ae  mov     [rsp+1E8h+var_1C8], rax
0x1401438b3  mov     r9d, [rdx+168h]
0x1401438ba  mov     rdx, [rdx+30h]
0x1401438be  mov     rcx, r12
0x1401438c1  call    NtfsPinMappedData
0x1401438c6  mov     rdx, [rsp+1E8h+Source2]; Source2
0x1401438ce  test    rdx, rdx
0x1401438d1  jz      loc_140143B67
0x1401438d7  mov     r8d, dword ptr [rsp+1E8h+Length]; Length
0x1401438df  movzx   ecx, word ptr [rbx+14h]
0x1401438e3  add     ecx, r14d
0x1401438e6  add     rcx, rbx; Source1
0x1401438e9  call    cs:__imp_RtlCompareMemory
0x1401438f0  nop     dword ptr [rax+rax+00h]
0x1401438f5  mov     ecx, eax
0x1401438f7  mov     rdx, [rsp+1E8h+Source2]
0x1401438ff  add     rdx, rcx
0x140143902  mov     [rsp+1E8h+Source2], rdx
0x14014390a  mov     [rsp+1E8h+Src], rdx
0x140143912  add     r14d, eax
0x140143915  mov     [rsp+1E8h+var_110], r14d
0x14014391d  sub     dword ptr [rsp+1E8h+Length], eax
0x140143924  lea     rcx, [r13+30h]
0x140143928  mov     rax, [rsp+1E8h+var_128]
0x140143930  lea     r10, [r13+10h]
0x140143934  mov     r11d, ebx
0x140143937  sub     r11d, eax
0x14014393a  mov     [rsp+1E8h+var_170], r11d
0x14014393f  mov     r8d, dword ptr [rsp+1E8h+var_160]
0x140143947  test    r8d, r8d
0x14014394a  jnz     loc_140143A9E
0x140143950  mov     edx, dword ptr [rsp+1E8h+Length]
0x140143957  mov     ecx, [rsp+1E8h+var_174]
0x14014395b  test    edx, edx
0x14014395d  jnz     short loc_140143970
0x14014395f  test    r8d, r8d
0x140143962  jnz     loc_140143A4C
0x140143968  test    ecx, ecx
0x14014396a  jz      loc_140143E36
0x140143970  movzx   r10d, word ptr [rbx+14h]
0x140143975  add     r10d, r14d
0x140143978  mov     dword ptr [rsp+1E8h+Size], r10d
0x14014397d  cmp     r14d, esi
0x140143980  jb      loc_140143A74
0x140143986  mov     r9, rdi
0x140143989  mov     [rsp+1E8h+var_78], rdi
0x140143991  mov     esi, edi
0x140143993  mov     rax, [rsp+1E8h+var_C8]
0x14014399b  mov     rcx, [r15+60h]
0x14014399f  mov     cl, [rcx+1ECh]
0x1401439a5  cmp     [rax], rdi
0x1401439a8  jnz     loc_140143A91
0x1401439ae  mov     r8d, [r15+8]
0x1401439b2  shl     r8, cl
0x1401439b5  mov     rcx, [rsp+1E8h+var_C0]
0x1401439bd  mov     eax, [rcx+168h]
0x1401439c3  mov     [rsp+1E8h+var_188], eax
0x1401439c7  mov     [rsp+1E8h+var_190], r10d
0x1401439cc  mov     [rsp+1E8h+var_198], r11d
0x1401439d1  mov     [rsp+1E8h+var_1A0], r8
0x1401439d6  mov     [rsp+1E8h+var_1A8], esi
0x1401439da  mov     [rsp+1E8h+var_1B0], r9
0x1401439df  mov     dword ptr [rsp+1E8h+var_1B8], 7
0x1401439e7  mov     dword ptr [rsp+1E8h+var_1C0], edx
0x1401439eb  mov     rbx, [rsp+1E8h+Source2]
0x1401439f3  mov     [rsp+1E8h+var_1C8], rbx
0x1401439f8  mov     r9d, 7
0x1401439fe  mov     rax, [rsp+1E8h+var_F0]
0x140143a06  mov     r8, [rax]
0x140143a09  mov     rdx, [rcx+30h]
0x140143a0d  mov     rcx, r12
0x140143a10  call    NtfsWriteLog
0x140143a15  mov     rcx, [rsp+1E8h+var_128]
0x140143a1d  mov     [rcx+8], rax
0x140143a21  cmp     [rsp+1E8h+var_174], edi
0x140143a25  setnz   al
0x140143a28  mov     byte ptr [rsp+1E8h+var_1C0], al
0x140143a2c  mov     eax, dword ptr [rsp+1E8h+Length]
0x140143a33  mov     dword ptr [rsp+1E8h+var_1C8], eax
0x140143a37  mov     r9, rbx
0x140143a3a  mov     r8d, dword ptr [rsp+1E8h+Size]
0x140143a3f  mov     edx, [rsp+1E8h+var_170]
0x140143a43  call    NtfsRestartChangeValue
0x140143a48  mov     ecx, [rsp+1E8h+var_174]
0x140143a4c  test    ecx, ecx
0x140143a4e  jz      loc_140143E36
0x140143a54  mov     eax, [rsp+1E8h+var_164]
0x140143a5b  cmp     eax, 80h
0x140143a60  jnz     loc_140143D0A
0x140143a66  jmp     loc_140143E36
0x140143a6b  mov     r8d, [r15+8]
0x140143a6f  jmp     loc_14014389F
0x140143a74  mov     r9d, r10d
0x140143a77  add     r9, rbx
0x140143a7a  mov     [rsp+1E8h+var_78], r9
0x140143a82  test    ecx, ecx
0x140143a84  jnz     loc_140143B5F
0x140143a8a  mov     esi, edx
0x140143a8c  jmp     loc_140143993
0x140143a91  mov     rax, [r13+20h]
0x140143a95  mov     r8d, [rax+10h]
0x140143a99  jmp     loc_1401439B2
0x140143a9e  movzx   r9d, word ptr [rbx+14h]
0x140143aa3  add     r9d, esi
0x140143aa6  mov     dword ptr [rsp+1E8h+Size], r9d
0x140143aab  cmp     [rcx], rdi
0x140143aae  mov     rcx, [r15+60h]
0x140143ab2  mov     cl, [rcx+1ECh]
0x140143ab8  jnz     loc_140143B53
0x140143abe  mov     edx, [r15+8]
0x140143ac2  shl     rdx, cl
0x140143ac5  mov     rcx, [rsp+1E8h+var_C0]
0x140143acd  mov     eax, [rcx+168h]
0x140143ad3  mov     [rsp+1E8h+var_188], eax
0x140143ad7  mov     [rsp+1E8h+var_190], r9d
0x140143adc  mov     [rsp+1E8h+var_198], r11d
0x140143ae1  mov     [rsp+1E8h+var_1A0], rdx
0x140143ae6  mov     [rsp+1E8h+var_1A8], edi
0x140143aea  mov     [rsp+1E8h+var_1B0], rdi
0x140143aef  mov     eax, 7
0x140143af4  mov     dword ptr [rsp+1E8h+var_1B8], eax
0x140143af8  mov     dword ptr [rsp+1E8h+var_1C0], r8d
0x140143afd  mov     [rsp+1E8h+var_1C8], rdi
0x140143b02  mov     r9d, eax
0x140143b05  mov     r8, [r10]
0x140143b08  mov     rdx, [rcx+30h]
0x140143b0c  mov     rcx, r12
0x140143b0f  call    NtfsWriteLog
0x140143b14  mov     rcx, [rsp+1E8h+var_128]
0x140143b1c  mov     [rcx+8], rax
0x140143b20  mov     byte ptr [rsp+1E8h+var_1C0], 1
0x140143b25  mov     eax, dword ptr [rsp+1E8h+var_160]
0x140143b2c  mov     dword ptr [rsp+1E8h+var_1C8], eax
0x140143b30  xor     r9d, r9d
0x140143b33  mov     r8d, dword ptr [rsp+1E8h+Size]
0x140143b38  mov     edx, [rsp+1E8h+var_170]
0x140143b3c  call    NtfsRestartChangeValue
0x140143b41  mov     r8d, dword ptr [rsp+1E8h+var_160]
0x140143b49  mov     r11d, [rsp+1E8h+var_170]
0x140143b4e  jmp     loc_140143950
0x140143b53  mov     rax, [r13+20h]
0x140143b57  mov     edx, [rax+10h]
0x140143b5a  jmp     loc_140143AC2
0x140143b5f  sub     esi, r14d
0x140143b62  jmp     loc_140143993
0x140143b67  mov     rax, [rsp+1E8h+var_128]
0x140143b6f  jmp     short loc_140143BC0
0x140143b71  mov     al, 1
0x140143b73  test    al, al
0x140143b75  jz      short loc_140143BDD
0x140143b77  mov     [rsp+1E8h+var_177], dil
0x140143b7c  movzx   eax, word ptr [rbx+14h]
0x140143b80  mov     r8d, [rsp+1E8h+var_158]
0x140143b88  add     r8d, 7
0x140143b8c  add     r8d, eax
0x140143b8f  and     r8d, 0FFFFFFF8h
0x140143b93  mov     r9, r13
0x140143b96  mov     rdx, r15
0x140143b99  mov     rcx, r12
0x140143b9c  call    NtfsChangeAttributeSize
0x140143ba1  test    al, al
0x140143ba3  mov     al, dil
0x140143ba6  jz      short loc_140143B73
0x140143ba8  mov     rax, [r13+8]
0x140143bac  mov     [rsp+1E8h+var_128], rax
0x140143bb4  mov     rbx, [r13+0]
0x140143bb8  mov     [rsp+1E8h+var_E0], rbx
0x140143bc0  lea     rcx, [r13+30h]
0x140143bc4  lea     r10, [r13+10h]
0x140143bc8  mov     [rsp+1E8h+var_C8], rcx
0x140143bd0  mov     [rsp+1E8h+var_F0], r10
0x140143bd8  jmp     loc_140143934
0x140143bdd  mov     rdx, r13
0x140143be0  call    NtfsCleanupAttributeContext
0x140143be5  xor     edx, edx; Val
0x140143be7  lea     r8d, [rdx+58h]; Size
0x140143beb  mov     rcx, r13; void *
0x140143bee  call    memset
0x140143bf3  lea     rbx, [r15+8]
0x140143bf7  mov     [rsp+1E8h+var_1A0], r13
0x140143bfc  mov     [rsp+1E8h+var_1A8], edi
0x140143c00  mov     [rsp+1E8h+var_1B0], rdi
0x140143c05  mov     byte ptr [rsp+1E8h+var_1B8], dil
0x140143c0a  mov     [rsp+1E8h+var_1C0], rdi
0x140143c0f  lea     rax, [rsp+1E8h+var_120]
0x140143c17  mov     [rsp+1E8h+var_1C8], rax
0x140143c1c  mov     r9d, [rsp+1E8h+var_164]
0x140143c24  mov     r8, rbx
0x140143c27  mov     rdx, r15
0x140143c2a  mov     rcx, r12
0x140143c2d  call    NtfsLookupInFileRecord
0x140143c32  test    al, al
0x140143c34  jz      loc_140143D47
0x140143c3a  mov     rbx, [r13+0]
0x140143c3e  mov     [rsp+1E8h+var_E0], rbx
0x140143c46  cmp     [rsp+1E8h+var_164], 20h ; ' '
0x140143c4e  jnz     loc_140143B77
0x140143c54  cmp     [rbx+8], dil
0x140143c58  jnz     loc_140143DBC
0x140143c5e  mov     esi, [rbx+10h]
0x140143c61  mov     [rsp+1E8h+var_68], esi
0x140143c68  mov     r8d, dword ptr [rsp+1E8h+Size]
0x140143c6d  cmp     esi, r8d
0x140143c70  jbe     loc_140143B77
0x140143c76  mov     edx, esi
0x140143c78  sub     edx, r8d
0x140143c7b  mov     ecx, [rsp+1E8h+var_158]
0x140143c82  add     ecx, edx
  ... truncated ...
```
