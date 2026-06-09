# AddFolderToCabinet

- ea: `0x1800039b8`
- end: `0x180004639`
- name: `AddFolderToCabinet`
- size: `3201`
- prototype: `__int64 __fastcall(__int64, __int64, int, unsigned int (__fastcall *)(__int64, _QWORD, size_t), __int64 (__fastcall *)(__int64, _QWORD, _QWORD, size_t), size_t)`
- caller_count: `3`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x180001b40`
- `0x180002830`
- `0x180016c00`

## callees

- `0x180001674`
- `0x1800018e4`
- `0x1800019d0`
- `0x180001bd8`
- `0x180002978`
- `0x180002a28`
- `0x180002d7c`
- `0x1800039b8`
- `0x180004640`
- `0x1800046c4`
- `0x180005140`
- `0x180011324`
- `0x180014dc0`
- `0x18001562a`
- `0x18001c010`

## pseudocode

```c
__int64 __fastcall AddFolderToCabinet(
        __int64 a1,
        __int64 a2,
        int a3,
        unsigned int (__fastcall *a4)(__int64, _QWORD, size_t),
        __int64 (__fastcall *a5)(__int64, _QWORD, _QWORD, size_t),
        size_t a6)
{
  __int64 (__fastcall *v6)(__int64, _QWORD, _QWORD, size_t); // r13
  _WORD *v7; // rbx
  _DWORD *v10; // r12
  size_t v11; // r8
  int v12; // edx
  unsigned int v13; // ebx
  int v14; // eax
  __int64 v15; // rcx
  int v16; // r13d
  int v17; // eax
  char v18; // r11
  int v19; // r13d
  STRSAFE_LPSTR v20; // r10
  __int64 v21; // rdx
  _DWORD *v22; // r12
  _OWORD *v23; // rcx
  _OWORD *v24; // rax
  __int128 v25; // xmm1
  __int128 v26; // xmm0
  __int128 v27; // xmm1
  __int128 v28; // xmm0
  __int128 v29; // xmm1
  __int128 v30; // xmm0
  __int128 v31; // xmm1
  __int128 v32; // xmm0
  __int128 v33; // xmm1
  int v34; // eax
  unsigned int (__fastcall *v35)(__int64, _QWORD, size_t); // rax
  STRSAFE_PCNZCH v36; // r10
  const char *v37; // r11
  int v38; // r13d
  __int64 v39; // rcx
  unsigned int (__fastcall *v40)(__int64, _QWORD, _QWORD, int *, size_t); // rax
  _QWORD *v41; // rbx
  __int64 *v42; // r12
  unsigned int v43; // r10d
  unsigned __int16 *v44; // rcx
  int v45; // r9d
  int v46; // r8d
  int v47; // r12d
  unsigned int v48; // eax
  unsigned __int16 *v49; // rbx
  __int64 v50; // rax
  __int64 v52; // rdx
  _BYTE *v53; // rax
  int v54; // r11d
  __int64 v55; // rcx
  unsigned int (__fastcall *v56)(__int64, _QWORD, _QWORD, int *, size_t); // rax
  __int16 v57; // cx
  __int64 v58; // r9
  __int64 v59; // rdx
  _OWORD *v60; // rax
  _OWORD *v61; // rcx
  __int128 v62; // xmm1
  __int128 v63; // xmm0
  __int128 v64; // xmm1
  __int128 v65; // xmm0
  __int128 v66; // xmm1
  __int128 v67; // xmm0
  __int128 v68; // xmm1
  __int128 v69; // xmm0
  _OWORD *v70; // rcx
  __int64 v71; // rdx
  _OWORD *v72; // rax
  __int128 v73; // xmm1
  __int128 v74; // xmm0
  __int128 v75; // xmm1
  __int128 v76; // xmm0
  __int128 v77; // xmm1
  __int128 v78; // xmm0
  __int128 v79; // xmm1
  int v80; // ecx
  __int64 v81; // rdx
  _OWORD *v82; // rcx
  _OWORD *v83; // rax
  __int128 v84; // xmm1
  __int128 v85; // xmm0
  __int128 v86; // xmm1
  __int128 v87; // xmm0
  __int128 v88; // xmm1
  __int128 v89; // xmm0
  __int128 v90; // xmm1
  __int128 v91; // xmm0
  __int128 v92; // xmm1
  int v93; // eax
  _WORD *v94; // rdx
  unsigned int v95; // r9d
  _WORD *v96; // rbx
  unsigned int v97; // eax
  int v98; // eax
  int v99; // edx
  int v100; // edx
  __int64 v101; // rdx
  __int64 v102; // rax
  _DWORD *v103; // rcx
  int v104; // eax
  _WORD *v105; // [rsp+40h] [rbp-C0h]
  int v106; // [rsp+48h] [rbp-B8h] BYREF
  void *v107; // [rsp+50h] [rbp-B0h]
  unsigned int v108; // [rsp+58h] [rbp-A8h]
  int v109; // [rsp+5Ch] [rbp-A4h] BYREF
  size_t v110; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v111; // [rsp+68h] [rbp-98h]
  size_t pcbLength; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v113; // [rsp+78h] [rbp-88h]
  int v114; // [rsp+7Ch] [rbp-84h]
  int v115; // [rsp+80h] [rbp-80h]
  int v116; // [rsp+84h] [rbp-7Ch]
  _QWORD *v117; // [rsp+88h] [rbp-78h]
  void *v118; // [rsp+90h] [rbp-70h]
  int v119[2]; // [rsp+98h] [rbp-68h]
  unsigned int (__fastcall *v120)(__int64, _QWORD, size_t); // [rsp+A0h] [rbp-60h]
  _BYTE v121[272]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v122[272]; // [rsp+1C0h] [rbp+C0h] BYREF

  v6 = a5;
  v7 = 0;
  *(_BYTE *)(a1 + 3629) = 0;
  *(_BYTE *)(a1 + 3886) = 0;
  v116 = a3;
  v120 = a4;
  *(_QWORD *)v119 = a5;
  pcbLength = 0;
  v110 = 0;
  v106 = 0;
  v109 = 0;
  if ( !(unsigned int)FolderFlush(a2, a5, a6) )
    return 0;
  v10 = (_DWORD *)(a2 + 96);
  if ( !(*(_DWORD *)(a2 + 368) + *(_DWORD *)(a2 + 96)) )
    return 1;
  v107 = (void *)(*(__int64 (__fastcall **)(_QWORD))(a1 + 24))(*(unsigned int *)(a1 + 2848));
  if ( !v107 )
    return 0;
  v118 = (void *)(*(__int64 (__fastcall **)(_QWORD))(a1 + 24))(*(unsigned int *)(a1 + 2848));
  if ( !v118
    || (v105 = (_WORD *)(*(__int64 (__fastcall **)(_QWORD))(a1 + 24))(*(unsigned int *)(a1 + 2844)), (v7 = v105) == 0) )
  {
LABEL_46:
    (*(void (__fastcall **)(void *))(a1 + 32))(v107);
    if ( v118 )
      (*(void (__fastcall **)(void *))(a1 + 32))(v118);
    if ( v7 )
      (*(void (__fastcall **)(_WORD *))(a1 + 32))(v7);
    return 0;
  }
  v11 = *(unsigned int *)(a1 + 2848);
  v111 = 0;
  memset_0(v107, 0, v11);
  memset_0(v118, 0, *(unsigned int *)(a1 + 2848));
  memset_0(v105, 0, *(unsigned int *)(a1 + 2844));
  while ( 1 )
  {
    v12 = *v10 + *(_DWORD *)(a2 + 368);
    if ( !v12 )
      break;
    v13 = *(_DWORD *)(a1 + 2844)
        + v12
        + *(_DWORD *)(a1 + 104)
        + *(_DWORD *)(a1 + 376)
        + *(_DWORD *)(a1 + 648)
        + *(_DWORD *)(a1 + 2840);
    if ( *(_BYTE *)(a1 + 3115) )
    {
      if ( StringCbLengthA((STRSAFE_PCNZCH)(a1 + 3115), 0x101u, &pcbLength) < 0
        || StringCbLengthA((STRSAFE_PCNZCH)(a1 + 3372), 0x101u, &v110) < 0 )
      {
        return 0;
      }
      v13 += pcbLength + v110 + 2;
    }
    if ( *(_BYTE *)(a1 + 4143) )
    {
      v52 = 257;
      v53 = (_BYTE *)(a1 + 4143);
      do
      {
        if ( !*v53 )
          break;
        ++v53;
        --v52;
      }
      while ( v52 );
      if ( !v52 )
        return 0;
      pcbLength = (257 - v52) & -(__int64)(v52 != 0);
      if ( StringCbLengthA((STRSAFE_PCNZCH)(a1 + 4400), 0x101u, &v110) < 0 )
        return 0;
      v13 += v54 + v110 + 2;
    }
    v109 = 0;
    v14 = v6(1, 0, v13, a6);
    v15 = *(_QWORD *)(a1 + 88);
    if ( v14 == -1 )
    {
      *(_QWORD *)v15 = 7;
      *(_DWORD *)(v15 + 8) = 1;
LABEL_45:
      v7 = v105;
      goto LABEL_46;
    }
    v16 = *(_DWORD *)(a1 + 920);
    v17 = CrTempFiles(
            (unsigned int)v121,
            2,
            *(_QWORD *)(a1 + 40),
            *(_QWORD *)(a1 + 64),
            *(_QWORD *)(a1 + 80),
            *(_QWORD *)(a1 + 16),
            v15,
            a6);
    v18 = 0;
    if ( !v17 )
      goto LABEL_45;
    v19 = v16 - v13;
    v115 = v13;
    if ( v19 < 0 || v116 )
    {
      if ( !*(_BYTE *)(a1 + 3629) )
      {
        StringCchCopyA((STRSAFE_LPSTR)(a1 + 3886), 0x101u, (STRSAFE_LPCSTR)(a1 + 954));
        StringCchCopyA(v20, 0x101u, (STRSAFE_LPCSTR)(a1 + 1210));
      }
      if ( *(_BYTE *)(a1 + 4143) != v18 )
      {
        if ( StringCbLengthA((STRSAFE_PCNZCH)(a1 + 4143), 0x101u, &pcbLength) < 0
          || StringCbLengthA((STRSAFE_PCNZCH)(a1 + 4400), 0x101u, &v110) < 0 )
        {
          return 0;
        }
        v13 += -2 - pcbLength - v110;
      }
      v21 = 6;
      v22 = (_DWORD *)(a1 + 1724);
      v23 = (_OWORD *)(a1 + 1724);
      v24 = (_OWORD *)(a1 + 920);
      do
      {
        v25 = v24[1];
        *v23 = *v24;
        v26 = v24[2];
        v23[1] = v25;
        v27 = v24[3];
        v23[2] = v26;
        v28 = v24[4];
        v23[3] = v27;
        v29 = v24[5];
        v23[4] = v28;
        v30 = v24[6];
        v23[5] = v29;
        v31 = v24[7];
        v24 += 8;
        v23[6] = v30;
        v23[7] = v31;
        v23 += 8;
        --v21;
      }
      while ( v21 );
      v32 = *v24;
      v33 = v24[1];
      v34 = *((_DWORD *)v24 + 8);
      *v23 = v32;
      *(_DWORD *)(a1 + 96) = v13;
      v23[1] = v33;
      *((_DWORD *)v23 + 8) = v34;
      v35 = v120;
      ++*(_DWORD *)(a1 + 1744);
      if ( v35(a1 + 1724, v13, a6) == -1 )
      {
LABEL_34:
        v50 = *(_QWORD *)(a1 + 88);
        *(_QWORD *)v50 = 7;
LABEL_100:
        *(_DWORD *)(v50 + 8) = 1;
        goto LABEL_45;
      }
      StringCchCopyA((STRSAFE_LPSTR)(a1 + 4143), 0x101u, (STRSAFE_LPCSTR)(a1 + 2014));
      StringCchCopyA((STRSAFE_LPSTR)(a1 + 4400), 0x101u, (STRSAFE_LPCSTR)(a1 + 1758));
      if ( StringCbLengthA(v36, 0x100u, &pcbLength) < 0 || StringCbLengthA(v37, 0x100u, &v110) < 0 )
        return 0;
      v38 = *(_DWORD *)(a1 + 920) - pcbLength - v110 - v13;
      v114 = 1;
      v19 = v38 - 2;
      if ( !*v22 )
        *v22 = 0x7FFFFFFF;
    }
    else
    {
      v114 = 0;
    }
    v7 = v105;
    v105[3] = *(_WORD *)(a2 + 676);
    v105[2] = 0;
    *(_DWORD *)v105 = *(_DWORD *)(a1 + 104);
    v39 = *(_QWORD *)(a2 + 104);
    v40 = *(unsigned int (__fastcall **)(__int64, _QWORD, _QWORD, int *, size_t))(a1 + 72);
    v106 = 0;
    if ( v40(v39, 0, 0, &v106, a6) == -1 )
      goto LABEL_102;
    v41 = (_QWORD *)(a2 + 688);
    v113 = 0;
    v117 = (_QWORD *)(a2 + 688);
    v42 = (__int64 *)(a1 + 56);
    v106 = 0;
    while ( (unsigned int)ReadCFDATAEntry(a1, (_DWORD)v107, a2, a6, (__int64)&v106) )
    {
      v43 = v113;
      v44 = (unsigned __int16 *)v107;
      v45 = *(_DWORD *)(a2 + 96);
      v46 = *(_DWORD *)(a1 + 2848);
      v108 = 0;
      v113 += v46 + *((unsigned __int16 *)v107 + 2);
      if ( v113 >= v45 + v19 )
      {
        if ( v46 + v43 >= v45 + v19 )
        {
          if ( !(unsigned int)WriteCount((unsigned int)v121, (_DWORD)v107, v46, *v42, *(_QWORD *)(a2 + 88), a6) )
            goto LABEL_45;
          v101 = *v41;
        }
        else
        {
          v94 = v118;
          v95 = v45 - v46 - v43;
          v96 = (char *)v118 + 4;
          ++v105[2];
          v108 = v95 + v19;
          v94[3] = 0;
          *v96 = v95 + v19;
          v97 = CSUMCompute(*v117, v95 + v19, 0);
          v98 = CSUMCompute(v96, (unsigned int)(*(_DWORD *)(a1 + 2848) - 4), v97);
          v99 = (int)v118;
          *(_DWORD *)v118 = v98;
          if ( !(unsigned int)WriteCount((int)a1 + 104, v99, *(_DWORD *)(a1 + 2848), *v42, *(_QWORD *)(a1 + 88), a6) )
            goto LABEL_45;
          v41 = v117;
          if ( !(unsigned int)WriteCount((int)a1 + 104, *v117, v108, *v42, *(_QWORD *)(a1 + 88), a6) )
            goto LABEL_45;
          v100 = (int)v107;
          *((_WORD *)v107 + 2) -= v108;
          if ( !(unsigned int)WriteCount(
                                (unsigned int)v121,
                                v100,
                                *(_DWORD *)(a1 + 2848),
                                *v42,
                                *(_QWORD *)(a2 + 88),
                                a6) )
            goto LABEL_45;
          v101 = *v41 + v108;
        }
        if ( !(unsigned int)WriteCount(
                              (unsigned int)v121,
                              v101,
                              *((unsigned __int16 *)v107 + 2),
                              *v42,
                              *(_QWORD *)(a2 + 88),
                              a6) )
          goto LABEL_45;
      }
      else
      {
        v47 = *((unsigned __int16 *)v107 + 3);
        ++v105[2];
        v48 = CSUMCompute(*(_QWORD *)(a2 + 688), v44[2], 0);
        v49 = (unsigned __int16 *)v107;
        *(_DWORD *)v49 = CSUMCompute((char *)v107 + 4, (unsigned int)(*(_DWORD *)(a1 + 2848) - 4), v48);
        if ( !(unsigned int)WriteCount(
                              (int)a1 + 104,
                              (_DWORD)v49,
                              *(_DWORD *)(a1 + 2848),
                              *(_QWORD *)(a1 + 56),
                              *(_QWORD *)(a1 + 88),
                              a6)
          || !(unsigned int)WriteCount(
                              (int)a1 + 104,
                              *(_QWORD *)(a2 + 688),
                              v49[2],
                              *(_QWORD *)(a1 + 56),
                              *(_QWORD *)(a1 + 88),
                              a6) )
        {
          goto LABEL_45;
        }
        v111 += v47;
        v41 = (_QWORD *)(a2 + 688);
        v42 = (__int64 *)(a1 + 56);
      }
      v117 = v41;
      v109 += v108 + *((unsigned __int16 *)v107 + 2);
      if ( (*(unsigned int (__fastcall **)(__int64, _QWORD, _QWORD, size_t))v119)(
             1,
             (unsigned int)v109,
             (unsigned int)v115,
             a6) == -1 )
        goto LABEL_34;
    }
    if ( v106 )
      goto LABEL_45;
    ++*(_WORD *)(a1 + 2554);
    v7 = v105;
    if ( *(_WORD *)(a1 + 2554) > 0xFFFCu )
    {
      v102 = *(_QWORD *)(a2 + 88);
      *(_QWORD *)v102 = 9;
      *(_DWORD *)(v102 + 8) = 1;
      goto LABEL_46;
    }
    if ( !(unsigned int)WriteCount((int)a1 + 648, (_DWORD)v105, *(_DWORD *)(a1 + 2844), *v42, *(_QWORD *)(a1 + 88), a6) )
      goto LABEL_46;
    v55 = *(_QWORD *)(a2 + 376);
    v56 = *(unsigned int (__fastcall **)(__int64, _QWORD, _QWORD, int *, size_t))(a1 + 72);
    v106 = 0;
    if ( v56(v55, 0, 0, &v106, a6) == -1 )
    {
LABEL_102:
      v103 = *(_DWORD **)(a1 + 88);
      v104 = v106;
      *v103 = 4;
      v103[1] = v104;
      v103[2] = 1;
      goto LABEL_46;
    }
    v106 = 0;
    while ( (unsigned int)ReadCFFILEEntry(a1, a2, a6, &v106) )
    {
      if ( (*(unsigned int (__fastcall **)(__int64, __int64, _QWORD, bool, size_t))(a1 + 8))(
             a1 + 920,
             a1 + 2858,
             *(unsigned int *)(a1 + 2564),
             (*(_WORD *)(a1 + 2572) & 0xFFFD) == 0xFFFD,
             a6) == -1 )
        goto LABEL_34;
      v57 = *(_WORD *)(a1 + 2572);
      if ( (v57 & 0xFFFD) != 0xFFFD )
      {
        v57 = *(_WORD *)(a1 + 2852);
        *(_WORD *)(a1 + 2572) = v57;
      }
      if ( *(_DWORD *)(a1 + 2564) + *(_DWORD *)(a1 + 2568) > v111 )
      {
        if ( (v57 & 0xFFFD) == 0xFFFD )
          *(_WORD *)(a1 + 2572) = -1;
        else
          *(_WORD *)(a1 + 2572) = -2;
      }
      if ( !(unsigned int)WriteCount((int)a1 + 376, (int)a1 + 2564, 16, *v42, *(_QWORD *)(a1 + 88), a6)
        || !(unsigned int)WritePszTmp((int)a1 + 376, (int)a1 + 2858, *v42, *(_QWORD *)(a1 + 88), a6) )
      {
        goto LABEL_45;
      }
      if ( !++*(_WORD *)(a1 + 2556) )
      {
        v50 = *(_QWORD *)(a2 + 88);
        *(_QWORD *)v50 = 9;
        goto LABEL_100;
      }
      if ( (*(_WORD *)(a1 + 2572) & 0xFFFE) == 0xFFFE )
      {
        v58 = *v42;
        *(_WORD *)(a1 + 2572) = -3;
        if ( !(unsigned int)WriteCount((unsigned int)v122, (int)a1 + 2564, 16, v58, *(_QWORD *)(a2 + 88), a6)
          || !(unsigned int)WritePszTmp((unsigned int)v122, (int)a1 + 2858, *v42, *(_QWORD *)(a2 + 88), a6) )
        {
          goto LABEL_45;
        }
      }
    }
    if ( v106 )
      goto LABEL_45;
    v10 = (_DWORD *)(a2 + 96);
    if ( !(unsigned int)DeleteTempFiles(
                          (int)a2 + 96,
                          2,
                          *(_QWORD *)(a2 + 56),
                          *(_QWORD *)(a2 + 72),
                          *(_QWORD *)(a2 + 88),
                          a6) )
      goto LABEL_45;
    v59 = 2;
    v60 = (_OWORD *)(a2 + 96);
    v61 = v121;
    do
    {
      v62 = v61[1];
      *v60 = *v61;
      v63 = v61[2];
      v60[1] = v62;
      v64 = v61[3];
      v60[2] = v63;
      v65 = v61[4];
      v60[3] = v64;
      v66 = v61[5];
      v60[4] = v65;
      v67 = v61[6];
      v60[5] = v66;
      v68 = v61[7];
      v61 += 8;
      v60[6] = v67;
      v60[7] = v68;
      v60 += 8;
      --v59;
    }
    while ( v59 );
    v69 = *v61;
    v70 = v122;
    v71 = 2;
    *v60 = v69;
    v72 = (_OWORD *)(a2 + 368);
    do
    {
      v73 = v70[1];
      *v72 = *v70;
      v74 = v70[2];
      v72[1] = v73;
      v75 = v70[3];
      v72[2] = v74;
      v76 = v70[4];
      v72[3] = v75;
      v77 = v70[5];
      v72[4] = v76;
      v78 = v70[6];
      v72[5] = v77;
      v79 = v70[7];
      v70 += 8;
      v72[6] = v78;
      v72[7] = v79;
      v72 += 8;
      --v71;
    }
    while ( v71 );
    v7 = v105;
    v6 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, size_t))v119;
    *v72 = *v70;
    if ( v114 )
    {
      if ( !(unsigned int)FlushCab(a1, (int)v6, (int)&v109, v115, a6) )
        goto LABEL_46;
      v80 = *(_DWORD *)(a1 + 920);
      if ( v80 && *(_DWORD *)(a1 + 944) == *(_DWORD *)(a1 + 1748) )
        *(_DWORD *)(a1 + 1724) = v80;
      v81 = 6;
      v82 = (_OWORD *)(a1 + 920);
      v83 = (_OWORD *)(a1 + 1724);
      do
      {
        v84 = v83[1];
        *v82 = *v83;
        v85 = v83[2];
        v82[1] = v84;
        v86 = v83[3];
        v82[2] = v85;
        v87 = v83[4];
        v82[3] = v86;
        v88 = v83[5];
        v82[4] = v87;
        v89 = v83[6];
        v82[5] = v88;
        v90 = v83[7];
        v83 += 8;
        v82[6] = v89;
        v82[7] = v90;
        v82 += 8;
        --v81;
      }
      while ( v81 );
      v91 = *v83;
      v92 = v83[1];
      v93 = *((_DWORD *)v83 + 8);
      *v82 = v91;
      v82[1] = v92;
      *((_DWORD *)v82 + 8) = v93;
      *(_WORD *)(a1 + 2852) = 0;
    }
  }
  if ( !v116 )
    ++*(_WORD *)(a1 + 2852);
  (*(void (__fastcall **)(void *))(a1 + 32))(v107);
  (*(void (__fastcall **)(void *))(a1 + 32))(v118);
  (*(void (__fastcall **)(_WORD *))(a1 + 32))(v7);
  return 1;
}

```

## disassembly

```asm
0x1800039b8  mov     [rsp-8+arg_10], rbx
0x1800039bd  push    rbp
0x1800039be  push    rsi
0x1800039bf  push    rdi
0x1800039c0  push    r12
0x1800039c2  push    r13
0x1800039c4  push    r14
0x1800039c6  push    r15
0x1800039c8  lea     rbp, [rsp-1E0h]
0x1800039d0  sub     rsp, 2E0h
0x1800039d7  mov     rax, cs:__security_cookie
0x1800039de  xor     rax, rsp
0x1800039e1  mov     [rbp+210h+var_40], rax
0x1800039e8  mov     r13, [rbp+210h+arg_20]
0x1800039ef  xor     ebx, ebx
0x1800039f1  mov     r15, [rbp+210h+arg_28]
0x1800039f8  mov     r14, rdx
0x1800039fb  mov     [rcx+0E2Dh], bl
0x180003a01  mov     rdi, rcx
0x180003a04  mov     [rcx+0F2Eh], bl
0x180003a0a  mov     rdx, r13
0x180003a0d  mov     [rbp+210h+var_28C], r8d
0x180003a11  mov     rcx, r14
0x180003a14  mov     r8, r15
0x180003a17  mov     [rbp+210h+var_270], r9
0x180003a1b  mov     qword ptr [rbp+210h+var_278], r13
0x180003a1f  mov     [rsp+310h+pcbLength], rbx
0x180003a24  mov     [rsp+310h+var_2B0], rbx
0x180003a29  mov     [rsp+310h+var_2C8], ebx
0x180003a2d  mov     [rsp+310h+var_2B4], ebx
0x180003a31  call    FolderFlush
0x180003a36  test    eax, eax
0x180003a38  jz      loc_180004008
0x180003a3e  lea     r12, [r14+60h]
0x180003a42  mov     eax, [r12]
0x180003a46  add     eax, [r14+170h]
0x180003a4d  jz      loc_180003FD5
0x180003a53  mov     ecx, [rdi+0B20h]
0x180003a59  mov     rax, [rdi+18h]
0x180003a5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a62  mov     [rsp+310h+var_2C0], rax
0x180003a67  test    rax, rax
0x180003a6a  jz      loc_180004008
0x180003a70  mov     ecx, [rdi+0B20h]
0x180003a76  mov     rax, [rdi+18h]
0x180003a7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a7f  mov     [rbp+210h+var_280], rax
0x180003a83  test    rax, rax
0x180003a86  jz      loc_180003FE4
0x180003a8c  mov     ecx, [rdi+0B1Ch]
0x180003a92  mov     rax, [rdi+18h]
0x180003a96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a9b  mov     [rsp+310h+var_2D0], rax
0x180003aa0  mov     rbx, rax
0x180003aa3  test    rax, rax
0x180003aa6  jz      loc_180003FE4
0x180003aac  mov     r8d, [rdi+0B20h]; Size
0x180003ab3  xor     edx, edx; Val
0x180003ab5  mov     rcx, [rsp+310h+var_2C0]; void *
0x180003aba  mov     [rsp+310h+var_2A8], 0
0x180003ac2  call    memset_0
0x180003ac7  mov     r8d, [rdi+0B20h]; Size
0x180003ace  xor     edx, edx; Val
0x180003ad0  mov     rcx, [rbp+210h+var_280]; void *
0x180003ad4  call    memset_0
0x180003ad9  mov     r8d, [rdi+0B1Ch]; Size
0x180003ae0  xor     edx, edx; Val
0x180003ae2  mov     rcx, rbx; void *
0x180003ae5  call    memset_0
0x180003aea  mov     esi, 1
0x180003aef  mov     edx, [r14+170h]
0x180003af6  add     edx, [r12]
0x180003afa  jz      loc_180003F1A
0x180003b00  mov     ebx, [rdi+0B18h]
0x180003b06  lea     rcx, [rdi+0C2Bh]; psz
0x180003b0d  add     ebx, [rdi+288h]
0x180003b13  add     ebx, [rdi+178h]
0x180003b19  add     ebx, [rdi+68h]
0x180003b1c  add     ebx, edx
0x180003b1e  add     ebx, [rdi+0B1Ch]
0x180003b24  cmp     byte ptr [rcx], 0
0x180003b27  jnz     loc_1800043E6
0x180003b2d  lea     r12, [rdi+102Fh]
0x180003b34  cmp     byte ptr [r12], 0
0x180003b39  jnz     loc_180003F77
0x180003b3f  mov     r9, r15
0x180003b42  mov     [rsp+310h+var_2B4], 0
0x180003b4a  mov     r8d, ebx
0x180003b4d  xor     edx, edx
0x180003b4f  mov     ecx, esi
0x180003b51  mov     rax, r13
0x180003b54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b59  mov     rcx, [rdi+58h]
0x180003b5d  cmp     eax, 0FFFFFFFFh
0x180003b60  jz      loc_1800045FC
0x180003b66  mov     rax, [rdi+10h]
0x180003b6a  mov     edx, 2
0x180003b6f  mov     r9, [rdi+40h]
0x180003b73  mov     r8, [rdi+28h]
0x180003b77  mov     r13d, [rdi+398h]
0x180003b7e  mov     [rsp+310h+var_2D8], r15
0x180003b83  mov     [rsp+310h+var_2E0], rcx
0x180003b88  lea     rcx, [rbp+210h+var_260]
0x180003b8c  mov     [rsp+310h+var_2E8], rax
0x180003b91  mov     rax, [rdi+50h]
0x180003b95  mov     [rsp+310h+var_2F0], rax
0x180003b9a  call    CrTempFiles
0x180003b9f  xor     r11d, r11d
0x180003ba2  test    eax, eax
0x180003ba4  jz      loc_180003FDF
0x180003baa  sub     r13d, ebx
0x180003bad  mov     [rbp+210h+var_290], ebx
0x180003bb0  jns     loc_18000442F
0x180003bb6  lea     r10, [rdi+0E2Dh]
0x180003bbd  mov     r13d, 101h
0x180003bc3  cmp     [r10], r11b
0x180003bc6  jnz     short loc_180003BF0
0x180003bc8  lea     r8, [rdi+3BAh]; pszSrc
0x180003bcf  mov     edx, r13d; cchDest
0x180003bd2  lea     rcx, [rdi+0F2Eh]; pszDest
0x180003bd9  call    StringCchCopyA
0x180003bde  lea     r8, [rdi+4BAh]; pszSrc
0x180003be5  mov     edx, r13d; cchDest
0x180003be8  mov     rcx, r10; pszDest
0x180003beb  call    StringCchCopyA
0x180003bf0  cmp     [r12], r11b
0x180003bf4  jz      short loc_180003C39
0x180003bf6  lea     r8, [rsp+310h+pcbLength]; pcbLength
0x180003bfb  mov     rdx, r13; cbMax
0x180003bfe  mov     rcx, r12; psz
0x180003c01  call    StringCbLengthA
0x180003c06  test    eax, eax
0x180003c08  js      loc_180004008
0x180003c0e  lea     rcx, [rdi+1130h]; psz
0x180003c15  mov     rdx, r13; cbMax
0x180003c18  lea     r8, [rsp+310h+var_2B0]; pcbLength
0x180003c1d  call    StringCbLengthA
0x180003c22  test    eax, eax
0x180003c24  js      loc_180004008
0x180003c2a  mov     eax, 0FFFFFFFEh
0x180003c2f  sub     eax, dword ptr [rsp+310h+pcbLength]
0x180003c33  sub     eax, dword ptr [rsp+310h+var_2B0]
0x180003c37  add     ebx, eax
0x180003c39  mov     edx, 6
0x180003c3e  lea     r12, [rdi+6BCh]
0x180003c45  mov     rcx, r12
0x180003c48  lea     rax, [rdi+398h]
0x180003c4f  lea     r8d, [rdx+7Ah]
0x180003c53  movups  xmm0, xmmword ptr [rax]
0x180003c56  movups  xmm1, xmmword ptr [rax+10h]
0x180003c5a  movups  xmmword ptr [rcx], xmm0
0x180003c5d  movups  xmm0, xmmword ptr [rax+20h]
0x180003c61  movups  xmmword ptr [rcx+10h], xmm1
0x180003c65  movups  xmm1, xmmword ptr [rax+30h]
0x180003c69  movups  xmmword ptr [rcx+20h], xmm0
0x180003c6d  movups  xmm0, xmmword ptr [rax+40h]
0x180003c71  movups  xmmword ptr [rcx+30h], xmm1
0x180003c75  movups  xmm1, xmmword ptr [rax+50h]
0x180003c79  movups  xmmword ptr [rcx+40h], xmm0
0x180003c7d  movups  xmm0, xmmword ptr [rax+60h]
0x180003c81  movups  xmmword ptr [rcx+50h], xmm1
0x180003c85  movups  xmm1, xmmword ptr [rax+70h]
0x180003c89  add     rax, r8
0x180003c8c  movups  xmmword ptr [rcx+60h], xmm0
0x180003c90  movups  xmmword ptr [rcx+70h], xmm1
0x180003c94  add     rcx, r8
0x180003c97  sub     rdx, rsi
0x180003c9a  jnz     short loc_180003C53
0x180003c9c  movups  xmm0, xmmword ptr [rax]
0x180003c9f  mov     r8, r15
0x180003ca2  mov     edx, ebx
0x180003ca4  movups  xmm1, xmmword ptr [rax+10h]
0x180003ca8  mov     eax, [rax+20h]
0x180003cab  movups  xmmword ptr [rcx], xmm0
0x180003cae  mov     [rdi+60h], ebx
0x180003cb1  movups  xmmword ptr [rcx+10h], xmm1
0x180003cb5  mov     [rcx+20h], eax
0x180003cb8  mov     rcx, r12
0x180003cbb  mov     rax, [rbp+210h+var_270]
0x180003cbf  add     [rdi+6D0h], esi
0x180003cc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003cca  cmp     eax, 0FFFFFFFFh
0x180003ccd  jz      loc_180003F0A
0x180003cd3  lea     r10, [rdi+7DEh]
0x180003cda  mov     rdx, r13; cchDest
0x180003cdd  mov     r8, r10; pszSrc
0x180003ce0  lea     rcx, [rdi+102Fh]; pszDest
0x180003ce7  call    StringCchCopyA
0x180003cec  lea     r11, [rdi+6DEh]
0x180003cf3  mov     rdx, r13; cchDest
0x180003cf6  mov     r8, r11; pszSrc
0x180003cf9  lea     rcx, [rdi+1130h]; pszDest
0x180003d00  call    StringCchCopyA
0x180003d05  mov     r13d, 100h
0x180003d0b  lea     r8, [rsp+310h+pcbLength]; pcbLength
0x180003d10  mov     edx, r13d; cbMax
0x180003d13  mov     rcx, r10; psz
0x180003d16  call    StringCbLengthA
0x180003d1b  test    eax, eax
0x180003d1d  js      loc_180004008
0x180003d23  lea     r8, [rsp+310h+var_2B0]; pcbLength
0x180003d28  mov     edx, r13d; cbMax
0x180003d2b  mov     rcx, r11; psz
0x180003d2e  call    StringCbLengthA
0x180003d33  xor     r11d, r11d
0x180003d36  test    eax, eax
0x180003d38  js      loc_180004008
0x180003d3e  mov     r13d, [rdi+398h]
0x180003d45  sub     r13d, dword ptr [rsp+310h+pcbLength]
0x180003d4a  sub     r13d, dword ptr [rsp+310h+var_2B0]
0x180003d4f  sub     r13d, ebx
0x180003d52  mov     [rsp+310h+var_294], esi
0x180003d56  sub     r13d, 2
0x180003d5a  cmp     [r12], r11d
0x180003d5e  jnz     short loc_180003D68
0x180003d60  mov     dword ptr [r12], 7FFFFFFFh
0x180003d68  movzx   eax, word ptr [r14+2A4h]
0x180003d70  lea     r9, [rsp+310h+var_2C8]
0x180003d75  mov     rbx, [rsp+310h+var_2D0]
0x180003d7a  xor     r8d, r8d
0x180003d7d  xor     edx, edx
0x180003d7f  mov     [rsp+310h+var_2F0], r15
0x180003d84  mov     [rbx+6], ax
0x180003d88  mov     [rbx+4], r11w
0x180003d8d  mov     eax, [rdi+68h]
0x180003d90  mov     [rbx], eax
0x180003d92  mov     rcx, [r14+68h]
0x180003d96  mov     rax, [rdi+48h]
0x180003d9a  mov     [rsp+310h+var_2C8], r11d
0x180003d9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003da4  cmp     eax, 0FFFFFFFFh
0x180003da7  jz      loc_1800045E3
0x180003dad  lea     rbx, [r14+2B0h]
0x180003db4  mov     [rsp+310h+var_298], 0
0x180003dbc  mov     [rbp+210h+var_288], rbx
0x180003dc0  lea     r12, [rdi+38h]
0x180003dc4  mov     [rsp+310h+var_2C8], 0
0x180003dcc  mov     rdx, [rsp+310h+var_2C0]
0x180003dd1  lea     rax, [rsp+310h+var_2C8]
0x180003dd6  mov     r9, r15
0x180003dd9  mov     [rsp+310h+var_2F0], rax
0x180003dde  mov     r8, r14
0x180003de1  mov     rcx, rdi
0x180003de4  call    ReadCFDATAEntry
0x180003de9  xor     edx, edx
0x180003deb  test    eax, eax
0x180003ded  jz      loc_18000400F
0x180003df3  mov     r11d, [rsp+310h+var_298]
0x180003df8  mov     r10d, r11d
0x180003dfb  mov     rcx, [rsp+310h+var_2C0]
0x180003e00  mov     r9d, [r14+60h]
0x180003e04  mov     r8d, [rdi+0B20h]
0x180003e0b  mov     [rsp+310h+var_2B8], edx
0x180003e0f  movzx   eax, word ptr [rcx+4]
0x180003e13  add     eax, r8d
0x180003e16  lea     edx, [r9+r13]
0x180003e1a  add     r11d, eax
0x180003e1d  mov     [rsp+310h+var_298], r11d
0x180003e22  cmp     r11d, edx
0x180003e25  jnb     loc_180004443
0x180003e2b  movzx   r12d, word ptr [rcx+6]
0x180003e30  xor     r8d, r8d
0x180003e33  mov     rax, [rsp+310h+var_2D0]
0x180003e38  add     [rax+4], si
0x180003e3c  movzx   edx, word ptr [rcx+4]
0x180003e40  mov     rcx, [r14+2B0h]
0x180003e47  call    CSUMCompute
0x180003e4c  mov     edx, [rdi+0B20h]
0x180003e52  mov     r8d, eax
0x180003e55  mov     rbx, [rsp+310h+var_2C0]
0x180003e5a  sub     edx, 4
0x180003e5d  lea     rcx, [rbx+4]
0x180003e61  call    CSUMCompute
0x180003e66  mov     [rbx], eax
0x180003e68  lea     rcx, [rdi+68h]
0x180003e6c  mov     rax, [rdi+58h]
0x180003e70  mov     rdx, rbx
0x180003e73  mov     r9, [rdi+38h]
0x180003e77  mov     r8d, [rdi+0B20h]
0x180003e7e  mov     [rsp+310h+var_2E8], r15
0x180003e83  mov     [rsp+310h+var_2F0], rax
0x180003e88  call    WriteCount
0x180003e8d  test    eax, eax
0x180003e8f  jz      loc_180003FDF
0x180003e95  mov     rax, [rdi+58h]
0x180003e99  lea     rcx, [rdi+68h]
0x180003e9d  movzx   r8d, word ptr [rbx+4]
0x180003ea2  mov     r9, [rdi+38h]
0x180003ea6  mov     rdx, [r14+2B0h]
0x180003ead  mov     [rsp+310h+var_2E8], r15
0x180003eb2  mov     [rsp+310h+var_2F0], rax
0x180003eb7  call    WriteCount
0x180003ebc  test    eax, eax
0x180003ebe  jz      loc_180003FDF
0x180003ec4  add     [rsp+310h+var_2A8], r12d
0x180003ec9  lea     rbx, [r14+2B0h]
0x180003ed0  lea     r12, [rdi+38h]
0x180003ed4  mov     edx, [rsp+310h+var_2B4]
0x180003ed8  mov     r9, r15
0x180003edb  mov     rax, [rsp+310h+var_2C0]
  ... truncated ...
```
