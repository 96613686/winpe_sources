# mp3SideInfoRead(CBitStream &,MP3SI &,MPEG_INFO const &)

- ea: `0x18000a590`
- end: `0x18000b823`
- name: `?mp3SideInfoRead@@YA_NAEAVCBitStream@@AEAUMP3SI@@AEBUMPEG_INFO@@@Z`
- size: `4755`
- prototype: `bool __fastcall(struct CBitStream *, struct MP3SI *, const struct MPEG_INFO *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x1800045d0`

## callees

- `0x180005630`
- `0x18000a590`
- `0x180010bc0`

## pseudocode

```c
char __fastcall mp3SideInfoRead(struct CBitStream *a1, struct MP3SI *a2, const struct MPEG_INFO *a3)
{
  int v3; // ebp
  const struct MPEG_INFO *v4; // r13
  int i; // r9d
  char v8; // cl
  int v9; // edx
  __int64 v10; // r8
  __int64 v11; // rax
  char *v12; // rcx
  int v13; // esi
  int v14; // eax
  int v15; // ecx
  unsigned int v16; // edi
  int v17; // esi
  int v18; // eax
  int v19; // ecx
  unsigned int v20; // edx
  int v21; // esi
  int v22; // edi
  unsigned __int16 v23; // r9
  _DWORD *v24; // rdi
  int v25; // ebp
  unsigned __int16 v26; // r9
  int v27; // r15d
  unsigned __int16 v28; // r9
  int v29; // ebp
  unsigned __int16 v30; // r9
  unsigned int v31; // edx
  int j; // r12d
  _DWORD *v33; // r9
  __int64 v34; // r15
  int v35; // esi
  __int64 v36; // r11
  unsigned __int16 v37; // r10
  unsigned int v38; // ecx
  _DWORD *v39; // rdi
  _DWORD *v40; // r13
  int v41; // esi
  __int64 v42; // r11
  unsigned __int16 v43; // r10
  unsigned int v44; // ecx
  int v45; // esi
  __int64 v46; // r11
  unsigned __int16 v47; // r10
  unsigned int v48; // ecx
  unsigned int v49; // r11d
  int v50; // esi
  __int64 v51; // r10
  unsigned __int16 v52; // r9
  __int64 v53; // rdi
  int v54; // r11d
  unsigned __int16 v55; // r9
  int v56; // eax
  int v57; // r8d
  int v58; // r15d
  __int64 v59; // rdi
  char v60; // cl
  __int64 v61; // rsi
  unsigned int v62; // r10d
  unsigned __int16 v63; // ax
  _DWORD *v64; // r9
  unsigned __int16 v65; // r8
  int v66; // edi
  unsigned __int16 v67; // r10
  int v68; // r15d
  __int64 v69; // r11
  unsigned __int16 v70; // r10
  unsigned int v71; // ecx
  int v72; // r13d
  __int64 v73; // r11
  unsigned __int16 v74; // r10
  unsigned int v75; // ecx
  int v76; // r11d
  __int64 v77; // r10
  unsigned __int16 v78; // r9
  unsigned int v79; // ecx
  int v80; // r11d
  __int64 v81; // r10
  unsigned __int16 v82; // r9
  unsigned int v83; // ecx
  int v84; // r11d
  __int64 v85; // r9
  unsigned __int16 v86; // r10
  unsigned int v87; // ecx
  int v88; // edx
  int v89; // r8d
  int v90; // r9d
  __int64 v91; // rdx
  char *v92; // rax
  _DWORD *v93; // r11
  unsigned __int16 v94; // r9
  int v95; // esi
  __int64 v96; // r10
  unsigned __int16 v97; // r9
  unsigned int v98; // ecx
  int v99; // esi
  __int64 v100; // r10
  unsigned __int16 v101; // r9
  unsigned int v102; // ecx
  int v103; // esi
  __int64 v104; // r10
  unsigned __int16 v105; // r9
  unsigned int v106; // ecx
  int v107; // r11d
  __int64 v108; // r10
  unsigned __int16 v109; // r9
  unsigned int v110; // ecx
  int v111; // ecx
  int v112; // edi
  unsigned __int16 v113; // r10
  int v114; // ecx
  int v115; // edi
  unsigned __int16 v116; // r10
  int v117; // edi
  unsigned __int16 v118; // r10
  int v119; // ecx
  __int64 v120; // rax
  int v121; // edx
  int k; // ecx
  __int64 v123; // rax
  __int64 v124; // rcx
  int m; // r9d
  int v126; // edx
  __int64 v127; // rax
  __int64 v128; // rcx
  __int64 v131; // [rsp+78h] [rbp+20h]

  v3 = 0;
  v4 = a3;
  for ( i = 0; ; ++i )
  {
    v8 = *((_BYTE *)v4 + 32);
    if ( i >= (v8 != 0) + 1 )
      break;
    v9 = 0;
    if ( *(int *)v4 > 0 )
    {
      v10 = 108LL * i;
      do
      {
        v11 = v9++;
        v12 = (char *)a2 + 232 * v11;
        *(_QWORD *)&v12[v10 + 96] = 0;
        *(_QWORD *)&v12[v10 + 104] = 0;
        *(_QWORD *)&v12[v10 + 112] = 0;
        *(_QWORD *)&v12[v10 + 120] = 0;
        *(_DWORD *)&v12[v10 + 128] = 0;
      }
      while ( v9 < *(_DWORD *)v4 );
    }
  }
  if ( *((_DWORD *)v4 + 7) )
  {
    v13 = 17;
    if ( *(_DWORD *)v4 == 1 )
    {
      if ( !v8 )
        v13 = 9;
    }
    else if ( v8 )
    {
      v13 = 32;
    }
    v14 = *((_DWORD *)a1 + 5);
    v15 = *((_DWORD *)a1 + 9) - 32;
    *((_DWORD *)a1 + 8) -= 32;
    *((_DWORD *)a1 + 6) += 32;
    *((_DWORD *)a1 + 9) = (v14 - 1) & v15;
    v16 = CalcCrc(a1, 16, 0xFFFFu);
    CBitStream::GetBits(a1, 0x10u);
    v17 = 8 * v13;
    CalcCrc(a1, v17, v16);
    v18 = *((_DWORD *)a1 + 5);
    v19 = *((_DWORD *)a1 + 9) - v17;
    *((_DWORD *)a1 + 8) -= v17;
    *((_DWORD *)a1 + 6) += v17;
    *((_DWORD *)a1 + 9) = (v18 - 1) & v19;
  }
  if ( *((_BYTE *)v4 + 32) )
  {
    *(_DWORD *)a2 = CBitStream::GetBits(a1, 9u);
    v20 = 5;
    if ( *(_DWORD *)v4 != 1 )
      v20 = 3;
    *((_DWORD *)a2 + 1) = CBitStream::GetBits(a1, v20);
    v21 = 0;
    if ( *(int *)v4 > 0 )
    {
      do
      {
        v22 = *((_DWORD *)a1 + 9);
        v23 = (*(unsigned __int8 *)(((v22 >> 3) & 0xFFFFFFFE) + 1 + *((_QWORD *)a1 + 6))
             | (unsigned __int16)(*(unsigned __int8 *)(((v22 >> 3) & 0xFFFFFFFE) + *((_QWORD *)a1 + 6)) << 8)) << (*((_BYTE *)a1 + 36) & 0xF);
        ++*((_DWORD *)a1 + 8);
        --*((_DWORD *)a1 + 6);
        *((_DWORD *)a1 + 9) = (v22 + 1) & (*((_DWORD *)a1 + 5) - 1);
        v24 = (_DWORD *)((char *)a2 + 232 * v21);
        v24[2] = v23 >> 15;
        v25 = *((_DWORD *)a1 + 9);
        v26 = (*(unsigned __int8 *)(((v25 >> 3) & 0xFFFFFFFE) + 1 + *((_QWORD *)a1 + 6))
             | (unsigned __int16)(*(unsigned __int8 *)(((v25 >> 3) & 0xFFFFFFFE) + *((_QWORD *)a1 + 6)) << 8)) << (*((_BYTE *)a1 + 36) & 0xF);
        *((_DWORD *)a1 + 9) = (*((_DWORD *)a1 + 5) - 1) & (v25 + 1);
        ++*((_DWORD *)a1 + 8);
        --*((_DWORD *)a1 + 6);
        v24[3] = v26 >> 15;
        v27 = *((_DWORD *)a1 + 9);
        v28 = (*(unsigned __int8 *)(((v27 >> 3) & 0xFFFFFFFE) + 1 + *((_QWORD *)a1 + 6))
             | (unsigned __int16)(*(unsigned __int8 *)(*((_QWORD *)a1 + 6) + ((v27 >> 3) & 0xFFFFFFFE)) << 8)) << (*((_BYTE *)a1 + 36) & 0xF);
        *((_DWORD *)a1 + 9) = (v27 + 1) & (*((_DWORD *)a1 + 5) - 1);
        ++*((_DWORD *)a1 + 8);
        --*((_DWORD *)a1 + 6);
        v24[4] = v28 >> 15;
        v29 = *((_DWORD *)a1 + 9);
        v30 = (*(unsigned __int8 *)(((v29 >> 3) & 0xFFFFFFFE) + 1 + *((_QWORD *)a1 + 6))
             | (unsigned __int16)(*(unsigned __int8 *)(((v29 >> 3) & 0xFFFFFFFE) + *((_QWORD *)a1 + 6)) << 8)) << (*((_BYTE *)a1 + 36) & 0xF);
        ++v21;
        *((_DWORD *)a1 + 9) = (*((_DWORD *)a1 + 5) - 1) & (v29 + 1);
        ++*((_DWORD *)a1 + 8);
        --*((_DWORD *)a1 + 6);
        v24[5] = v30 >> 15;
      }
      while ( v21 < *(_DWORD *)v4 );
      v3 = 0;
    }
  }
  else
  {
    *(_DWORD *)a2 = CBitStream::GetBits(a1, 8u);
    v31 = 1;
    if ( *(_DWORD *)v4 != 1 )
      v31 = 2;
    *((_DWORD *)a2 + 1) = CBitStream::GetBits(a1, v31);
  }
  for ( j = 0; ; ++j )
  {
    if ( j >= (*((_BYTE *)v4 + 32) != 0) + 1 )
      return 1;
    if ( *(int *)v4 > 0 )
      break;
LABEL_73:
    v3 = 0;
  }
  v33 = (_DWORD *)((char *)a1 + 16);
  v34 = 108LL * j;
  v131 = v34;
  while ( 1 )
  {
    v35 = *((_DWORD *)a1 + 9);
    v36 = *((_QWORD *)a1 + 6);
    v37 = (*(unsigned __int8 *)(((v35 >> 3) & 0xFFFFFFFE) + 1 + v36)
         | (unsigned __int16)(*(unsigned __int8 *)(((v35 >> 3) & 0xFFFFFFFE) + v36) << 8)) << (*((_BYTE *)a1 + 36) & 0xF);
    v38 = 16 - (v35 & 0xF);
    if ( v38 >= 0xC )
    {
      v39 = v33;
    }
    else
    {
      v39 = (_DWORD *)((char *)a1 + 16);
      v37 |= (unsigned __int16)(*(unsigned __int8 *)(((*v33 - 1) & (((v35 >> 3) & 0xFFFFFFFE) + 2)) + 1 + v36)
                              | (*(unsigned __int8 *)(((*v33 - 1) & (((v35 >> 3) & 0xFFFFFFFE) + 2)) + v36) << 8)) >> v38;
    }
    *((_DWORD *)a1 + 8) += 12;
    *((_DWORD *)a1 + 6) -= 12;
    *((_DWORD *)a1 + 9) = (*((_DWORD *)a1 + 5) - 1) & (v35 + 12);
    v40 = (_DWORD *)((char *)a2 + 232 * v3 + v34);
    v40[6] = v37 >> 4;
    v41 = *((_DWORD *)a1 + 9);
    v42 = *((_QWORD *)a1 + 6);
    v43 = (*(unsigned __int8 *)(((v41 >> 3) & 0xFFFFFFFE) + 1 + v42)
         | (unsigned __int16)(*(unsigned __int8 *)(((v41 >> 3) & 0xFFFFFFFE) + v42) << 8)) << (*((_BYTE *)a1 + 36) & 0xF);
    v44 = 16 - (v41 & 0xF);
    if ( v44 < 9 )
      v43 |= (unsigned __int16)(*(unsigned __int8 *)(((*v33 - 1) & (((v41 >> 3) & 0xFFFFFFFE) + 2)) + 1 + v42)
                              | (*(unsigned __int8 *)(((*v33 - 1) & (((v41 >> 3) & 0xFFFFFFFE) + 2)) + v42) << 8)) >> v44;
    *((_DWORD *)a1 + 8) += 9;
    *((_DWORD *)a1 + 6) -= 9;
    *((_DWORD *)a1 + 9) = (v41 + 9) & (*((_DWORD *)a1 + 5) - 1);
    v40[7] = v43 >> 7;
    v45 = *((_DWORD *)a1 + 9);
    v46 = *((_QWORD *)a1 + 6);
    v47 = (*(unsigned __int8 *)(((v45 >> 3) & 0xFFFFFFFE) + 1 + v46)
         | (unsigned __int16)(*(unsigned __int8 *)(((v45 >> 3) & 0xFFFFFFFE) + v46) << 8)) << (*((_BYTE *)a1 + 36) & 0xF);
    v48 = 16 - (v45 & 0xF);
    if ( v48 < 8 )
      v47 |= (unsigned __int16)(*(unsigned __int8 *)(((*v33 - 1) & (((v45 >> 3) & 0xFFFFFFFE) + 2)) + 1 + v46)
                              | (*(unsigned __int8 *)(((*v33 - 1) & (((v45 >> 3) & 0xFFFFFFFE) + 2)) + v46) << 8)) >> v48;
    *((_DWORD *)a1 + 8) += 8;
    *((_DWORD *)a1 + 6) -= 8;
    v49 = 4;
    *((_DWORD *)a1 + 9) = (*((_DWORD *)a1 + 5) - 1) & (v45 + 8);
    v40[8] = HIBYTE(v47);
    v50 = *((_DWORD *)a1 + 9);
    v51 = *((_QWORD *)a1 + 6);
    v4 = a3;
    if ( !*((_BYTE *)a3 + 32) )
      v49 = 9;
    v52 = (*(unsigned __int8 *)(((v50 >> 3) & 0xFFFFFFFE) + 1 + v51)
         | (unsigned __int16)(*(unsigned __int8 *)(((v50 >> 3) & 0xFFFFFFFE) + v51) << 8)) << (v50 & 0xF);
    if ( v49 > 16 - (v50 & 0xFu) )
      v52 |= (unsigned __int16)(*(unsigned __int8 *)(((((v50 >> 3) & 0xFFFFFFFE) + 2) & (*v39 - 1)) + 1 + v51)
                              | (*(unsigned __int8 *)(((((v50 >> 3) & 0xFFFFFFFE) + 2) & (*v39 - 1)) + v51) << 8)) >> (16 - (v50 & 0xF));
    *((_DWORD *)a1 + 8) += v49;
    *((_DWORD *)a1 + 6) -= v49;
    *((_DWORD *)a1 + 9) = (*((_DWORD *)a1 + 5) - 1) & (v49 + v50);
    v53 = v131 + 232LL * v3;
    *(_DWORD *)((char *)a2 + v53 + 36) = v52 >> (16 - v49);
    v54 = *((_DWORD *)a1 + 9);
    v55 = (*(unsigned __int8 *)(((v54 >> 3) & 0xFFFFFFFE) + 1 + *((_QWORD *)a1 + 6))
         | (unsigned __int16)(*(unsigned __int8 *)(((v54 >> 3) & 0xFFFFFFFE) + *((_QWORD *)a1 + 6)) << 8)) << (*((_BYTE *)a1 + 36) & 0xF);
    v56 = *((_DWORD *)a1 + 5);
    ++*((_DWORD *)a1 + 8);
    --*((_DWORD *)a1 + 6);
    *((_DWORD *)a1 + 9) = (v56 - 1) & (v54 + 1);
    v57 = v55 >> 15;
    *(_DWORD *)((char *)a2 + v53 + 40) = v57;
    if ( *(int *)((char *)a2 + v53 + 28) > 288 )
    {
      *(_DWORD *)((char *)a2 + v53 + 36) = 0;
      *((_DWORD *)a2 + 58 * v3 + 27 * j + 7) = 0;
      *((_DWORD *)a2 + 58 * v3 + 27 * j + 6) = 0;
    }
    v58 = *((_DWORD *)a1 + 9);
    v59 = *((_QWORD *)a1 + 6);
    v60 = v58 & 0xF;
    v61 = (v58 >> 3) & 0xFFFFFFFE;
    v62 = 16 - (v58 & 0xF);
    v63 = *(unsigned __int8 *)((unsigned int)(v61 + 1) + v59);
    if ( !v57 )
    {
      v93 = (_DWORD *)((char *)a1 + 16);
      v94 = (v63 | (unsigned __int16)(*(unsigned __int8 *)(v61 + v59) << 8)) << v60;
      if ( v62 < 5 )
        v94 |= (unsigned __int16)(*(unsigned __int8 *)((((_DWORD)v61 + 2) & (unsigned int)(*v93 - 1)) + 1 + v59)
                                | (*(unsigned __int8 *)((((_DWORD)v61 + 2) & (unsigned int)(*v93 - 1)) + v59) << 8)) >> v62;
      *((_DWORD *)a1 + 8) += 5;
      *((_DWORD *)a1 + 6) -= 5;
      *((_DWORD *)a1 + 9) = (v58 + 5) & (*((_DWORD *)a1 + 5) - 1);
      *((_DWORD *)a2 + 58 * v3 + 27 * j + 13) = v94 >> 11;
      v95 = *((_DWORD *)a1 + 9);
      v96 = *((_QWORD *)a1 + 6);
      v97 = (*(unsigned __int8 *)(((v95 >> 3) & 0xFFFFFFFE) + 1 + v96)
           | (unsigned __int16)(*(unsigned __int8 *)(((v95 >> 3) & 0xFFFFFFFE) + v96) << 8)) << (*((_BYTE *)a1 + 36)
                                                                                               & 0xF);
      v98 = 16 - (v95 & 0xF);
      if ( v98 < 5 )
        v97 |= (unsigned __int16)(*(unsigned __int8 *)(((*v93 - 1) & (((v95 >> 3) & 0xFFFFFFFE) + 2)) + 1 + v96)
                                | (*(unsigned __int8 *)(((*v93 - 1) & (((v95 >> 3) & 0xFFFFFFFE) + 2)) + v96) << 8)) >> v98;
      *((_DWORD *)a1 + 9) = (v95 + 5) & (*((_DWORD *)a1 + 5) - 1);
      *((_DWORD *)a1 + 8) += 5;
      *((_DWORD *)a1 + 6) -= 5;
      *((_DWORD *)a2 + 58 * v3 + 27 * j + 14) = v97 >> 11;
      v99 = *((_DWORD *)a1 + 9);
      v100 = *((_QWORD *)a1 + 6);
      v101 = (*(unsigned __int8 *)(((v99 >> 3) & 0xFFFFFFFE) + 1 + v100)
            | (unsigned __int16)(*(unsigned __int8 *)(((v99 >> 3) & 0xFFFFFFFE) + v100) << 8)) << (*((_BYTE *)a1 + 36)
                                                                                                 & 0xF);
      v102 = 16 - (v99 & 0xF);
      if ( v102 < 5 )
        v101 |= (unsigned __int16)(*(unsigned __int8 *)(((*v93 - 1) & (((v99 >> 3) & 0xFFFFFFFE) + 2)) + 1 + v100)
                                 | (*(unsigned __int8 *)(((*v93 - 1) & (((v99 >> 3) & 0xFFFFFFFE) + 2)) + v100) << 8)) >> v102;
      *((_DWORD *)a1 + 9) = (v99 + 5) & (*((_DWORD *)a1 + 5) - 1);
      *((_DWORD *)a1 + 8) += 5;
      *((_DWORD *)a1 + 6) -= 5;
      *((_DWORD *)a2 + 58 * v3 + 27 * j + 15) = v101 >> 11;
      v103 = *((_DWORD *)a1 + 9);
      v104 = *((_QWORD *)a1 + 6);
      v105 = (*(unsigned __int8 *)(((v103 >> 3) & 0xFFFFFFFE) + 1 + v104)
            | (unsigned __int16)(*(unsigned __int8 *)(((v103 >> 3) & 0xFFFFFFFE) + v104) << 8)) << (*((_BYTE *)a1 + 36)
                                                                                                  & 0xF);
      v106 = 16 - (v103 & 0xF);
      if ( v106 < 4 )
        v105 |= (unsigned __int16)(*(unsigned __int8 *)(((*v93 - 1) & (((v103 >> 3) & 0xFFFFFFFE) + 2)) + 1 + v104)
                                 | (*(unsigned __int8 *)(((*v93 - 1) & (((v103 >> 3) & 0xFFFFFFFE) + 2)) + v104) << 8)) >> v106;
      *((_DWORD *)a1 + 8) += 4;
      *((_DWORD *)a1 + 6) -= 4;
      *((_DWORD *)a1 + 9) = (v103 + 4) & (*((_DWORD *)a1 + 5) - 1);
      *((_DWORD *)a2 + 58 * v3 + 27 * j + 19) = v105 >> 12;
      v107 = *((_DWORD *)a1 + 9);
      v108 = *((_QWORD *)a1 + 6);
      v109 = (*(unsigned __int8 *)(((v107 >> 3) & 0xFFFFFFFE) + 1 + v108)
            | (unsigned __int16)(*(unsigned __int8 *)(((v107 >> 3) & 0xFFFFFFFE) + v108) << 8)) << (*((_BYTE *)a1 + 36)
                                                                                                  & 0xF);
      v110 = 16 - (v107 & 0xF);
      if ( v110 < 3 )
        v109 |= (unsigned __int16)(*(unsigned __int8 *)(((*((_DWORD *)a1 + 4) - 1) & (((v107 >> 3) & 0xFFFFFFFE) + 2))
                                                      + 1
                                                      + v108)
                                 | (*(unsigned __int8 *)(((*((_DWORD *)a1 + 4) - 1) & (((v107 >> 3) & 0xFFFFFFFE) + 2))
                                                       + v108) << 8)) >> v110;
      v111 = *((_DWORD *)a1 + 5);
      *((_DWORD *)a1 + 8) += 3;
      *((_DWORD *)a1 + 6) -= 3;
      *((_DWORD *)a1 + 9) = (v107 + 3) & (v111 - 1);
      v90 = v109 >> 13;
      *((_DWORD *)a2 + 58 * v3 + 27 * j + 11) = 0;
      v91 = 108LL * j;
      v92 = (char *)a2 + 232 * v3;
      goto LABEL_70;
    }
    v64 = (_DWORD *)((char *)a1 + 16);
    v65 = (v63 | (unsigned __int16)(*(unsigned __int8 *)(v61 + v59) << 8)) << v60;
    if ( v62 < 2 )
      v65 |= (unsigned __int16)(*(unsigned __int8 *)((((_DWORD)v61 + 2) & (unsigned int)(*v64 - 1)) + 1 + v59)
                              | (*(unsigned __int8 *)((((_DWORD)v61 + 2) & (unsigned int)(*v64 - 1)) + v59) << 8)) >> v62;
    *((_DWORD *)a1 + 8) += 2;
    *((_DWORD *)a1 + 6) -= 2;
    *((_DWORD *)a1 + 9) = (v58 + 2) & (*((_DWORD *)a1 + 5) - 1);
    *((_DWORD *)a2 + 58 * v3 + 27 * j + 11) = v65 >> 14;
    v66 = *((_DWORD *)a1 + 9);
    v67 = (*(unsigned __int8 *)(((v66 >> 3) & 0xFFFFFFFE) + 1 + *((_QWORD *)a1 + 6))
         | (unsigned __int16)(*(unsigned __int8 *)(((v66 >> 3) & 0xFFFFFFFE) + *((_QWORD *)a1 + 6)) << 8)) << (*((_BYTE *)a1 + 36) & 0xF);
    ++*((_DWORD *)a1 + 8);
    --*((_DWORD *)a1 + 6);
    *((_DWORD *)a1 + 9) = (v66 + 1) & (*((_DWORD *)a1 + 5) - 1);
    *((_DWORD *)a2 + 58 * v3 + 27 * j + 12) = v67 >> 15;
    v68 = *((_DWORD *)a1 + 9);
    v69 = *((_QWORD *)a1 + 6);
    v70 = (*(unsigned __int8 *)(((v68 >> 3) & 0xFFFFFFFE) + 1 + v69)
         | (unsigned __int16)(*(unsigned __int8 *)(((v68 >> 3) & 0xFFFFFFFE) + v69) << 8)) << (*((_BYTE *)a1 + 36) & 0xF);
    v71 = 16 - (v68 & 0xF);
    if ( v71 < 5 )
      v70 |= (unsigned __int16)(*(unsigned __int8 *)(((*v64 - 1) & (((v68 >> 3) & 0xFFFFFFFE) + 2)) + 1 + v69)
                              | (*(unsigned __int8 *)(((*v64 - 1) & (((v68 >> 3) & 0xFFFFFFFE) + 2)) + v69) << 8)) >> v71;
    *((_DWORD *)a1 + 8) += 5;
    *((_DWORD *)a1 + 6) -= 5;
    *((_DWORD *)a1 + 9) = (v68 + 5) & (*((_DWORD *)a1 + 5) - 1);
    *((_DWORD *)a2 + 58 * v3 + 27 * j + 13) = v70 >> 11;
    v72 = *((_DWORD *)a1 + 9);
    v73 = *((_QWORD *)a1 + 6);
    v74 = (*(unsigned __int8 *)(((v72 >> 3) & 0xFFFFFFFE) + 1 + v73)
         | (unsigned __int16)(*(unsigned __int8 *)(((v72 >> 3) & 0xFFFFFFFE) + v73) << 8)) << (*((_BYTE *)a1 + 36) & 0xF);
    v75 = 16 - (v72 & 0xF);
    if ( v75 < 5 )
      v74 |= (unsigned __int16)(*(unsigned __int8 *)(((*v64 - 1) & (((v72 >> 3) & 0xFFFFFFFE) + 2)) + 1 + v73)
                              | (*(unsigned __int8 *)(((*v64 - 1) & (((v72 >> 3) & 0xFFFFFFFE) + 2)) + v73) << 8)) >> v75;
    *((_DWORD *)a1 + 9) = (v72 + 5) & (*((_DWORD *)a1 + 5) - 1);
    *((_DWORD *)a1 + 8) += 5;
    *((_DWORD *)a1 + 6) -= 5;
    *((_DWORD *)a2 + 58 * v3 + 27 * j + 14) = v74 >> 11;
    *((_DWORD *)a2 + 58 * v3 + 27 * j + 15) = 0;
    v76 = *((_DWORD *)a1 + 9);
    v77 = *((_QWORD *)a1 + 6);
    v78 = (*(unsigned __int8 *)(((v76 >> 3) & 0xFFFFFFFE) + 1 + v77)
         | (unsigned __int16)(*(unsigned __int8 *)(((v76 >> 3) & 0xFFFFFFFE) + v77) << 8)) << (*((_BYTE *)a1 + 36) & 0xF);
    v79 = 16 - (v76 & 0xF);
    if ( v79 < 3 )
      v78 |= (unsigned __int16)(*(unsigned __int8 *)(((*((_DWORD *)a1 + 4) - 1) & (((v76 >> 3) & 0xFFFFFFFE) + 2))
                                                   + 1
                                                   + v77)
                              | (*(unsigned __int8 *)(((*((_DWORD *)a1 + 4) - 1) & (((v76 >> 3) & 0xFFFFFFFE) + 2)) + v77) << 8)) >> v79;
    *((_DWORD *)a1 + 8) += 3;
    *((_DWORD *)a1 + 6) -= 3;
    *((_DWORD *)a1 + 9) = (v76 + 3) & (*((_DWORD *)a1 + 5) - 1);
    *((_DWORD *)a2 + 58 * v3 + 27 * j + 16) = v78 >> 13;
    v80 = *((_DWORD *)a1 + 9);
    v81 = *((_QWORD *)a1 + 6);
    v82 = (*(unsigned __int8 *)(((v80 >> 3) & 0xFFFFFFFE) + 1 + v81)
         | (unsigned __int16)(*(unsigned __int8 *)(((v80 >> 3) & 0xFFFFFFFE) + v81) << 8)) << (*((_BYTE *)a1 + 36) & 0xF);
    v83 = 16 - (v80 & 0xF);
    if ( v83 < 3 )
      v82 |= (unsigned __int16)(*(unsigned __int8 *)(((((v80 >> 3) & 0xFFFFFFFE) + 2) & (*((_DWORD *)a1 + 4) - 1))
                                                   + 1
                                                   + v81)
                              | (*(unsigned __int8 *)(((((v80 >> 3) & 0xFFFFFFFE) + 2) & (*((_DWORD *)a1 + 4) - 1)) + v81) << 8)) >> v83;
    *((_DWORD *)a1 + 9) = (v80 + 3) & (*((_DWORD *)a1 + 5) - 1);
    *((_DWORD *)a1 + 8) += 3;
    *((_DWORD *)a1 + 6) -= 3;
    *((_DWORD *)a2 + 58 * v3 + 27 * j + 17) = v82 >> 13;
    v84 = *((_DWORD *)a1 + 9);
    v85 = *((_QWORD *)a1 + 6);
    v86 = (*(unsigned __int8 *)(((v84 >> 3) & 0xFFFFFFFE) + 1 + v85)
         | (unsigned __int16)(*(unsigned __int8 *)(((v84 >> 3) & 0xFFFFFFFE) + v85) << 8)) << (*((_BYTE *)a1 + 36) & 0xF);
    v87 = 16 - (v84 & 0xF);
    if ( v87 < 3 )
      v86 |= (unsigned __int16)(*(unsigned __int8 *)(((*((_DWORD *)a1 + 4) - 1) & (((v84 >> 3) & 0xFFFFFFFE) + 2))
                                                   + 1
                                                   + v85)
                              | (*(unsigned __int8 *)(((*((_DWORD *)a1 + 4) - 1) & (((v84 >> 3) & 0xFFFFFFFE) + 2)) + v85) << 8)) >> v87;
    *((_DWORD *)a1 + 9) = (v84 + 3) & (*((_DWORD *)a1 + 5) - 1);
    *((_DWORD *)a1 + 8) += 3;
    *((_DWORD *)a1 + 6) -= 3;
    *((_DWORD *)a2 + 58 * v3 + 27 * j + 18) = v86 >> 13;
    v88 = *((_DWORD *)a2 + 58 * v3 + 27 * j + 11);
    if ( !v88 )
      break;
    if ( v88 != 2 || (v89 = 8, *((_DWORD *)a2 + 58 * v3 + 27 * j + 12)) )
      v89 = 7;
    v90 = 20 - v89;
    *((_DWORD *)a2 + 58 * v3 + 27 * j + 19) = v89;
    v4 = a3;
    v91 = 108LL * j;
    v92 = (char *)a2 + 232 * v3;
LABEL_70:
    *(_DWORD *)&v92[v91 + 80] = v90;
    if ( *((_BYTE *)v4 + 32) )
    {
      v112 = *((_DWORD *)a1 + 9);
      v113 = (*(unsigned __int8 *)(((v112 >> 3) & 0xFFFFFFFE) + 1 + *((_QWORD *)a1 + 6))
            | (unsigned __int16)(*(unsigned __int8 *)(((v112 >> 3) & 0xFFFFFFFE) + *((_QWORD *)a1 + 6)) << 8)) << (*((_BYTE *)a1 + 36) & 0xF);
      v114 = *((_DWORD *)a1 + 5);
      ++*((_DWORD *)a1 + 8);
      --*((_DWORD *)a1 + 6);
      *((_DWORD *)a1 + 9) = (v112 + 1) & (v114 - 1);
      *((_DWORD *)a2 + 58 * v3 + 27 * j + 21) = v113 >> 15;
    }
    v115 = *((_DWORD *)a1 + 9);
    v116 = (*(unsigned __int8 *)(((v115 >> 3) & 0xFFFFFFFE) + 1 + *((_QWORD *)a1 + 6))
          | (unsigned __int16)(*(unsigned __int8 *)(((v115 >> 3) & 0xFFFFFFFE) + *((_QWORD *)a1 + 6)) << 8)) << (*((_BYTE *)a1 + 36) & 0xF);
    v33 = (_DWORD *)((char *)a1 + 16);
    ++*((_DWORD *)a1 + 8);
    --*((_DWORD *)a1 + 6);
    *((_DWORD *)a1 + 9) = (v115 + 1) & (*((_DWORD *)a1 + 5) - 1);
    *((_DWORD *)a2 + 58 * v3 + 27 * j + 22) = v116 >> 15;
    v117 = *((_DWORD *)a1 + 9);
    v118 = (*(unsigned __int8 *)(((v117 >> 3) & 0xFFFFFFFE) + 1 + *((_QWORD *)a1 + 6))
          | (unsigned __int16)(*(unsigned __int8 *)(((v117 >> 3) & 0xFFFFFFFE) + *((_QWORD *)a1 + 6)) << 8)) << (*((_BYTE *)a1 + 36) & 0xF);
    v119 = *((_DWORD *)a1 + 5);
    ++*((_DWORD *)a1 + 8);
    --*((_DWORD *)a1 + 6);
    v34 = 108LL * j;
    v120 = v3++;
    *((_DWORD *)a1 + 9) = (v117 + 1) & (v119 - 1);
    *(_DWORD *)((char *)a2 + 232 * v120 + v34 + 92) = v118 >> 15;
    if ( v3 >= *(_DWORD *)v4 )
      goto LABEL_73;
  }
  v121 = 0;
  *(_DWORD *)a2 = 0;
  for ( k = *(_DWORD *)a3; v121 < *(_DWORD *)a3; k = *(_DWORD *)a3 )
  {
    v123 = v121++;
    v124 = 232 * v123;
    *(_QWORD *)((char *)a2 + v124 + 8) = 0;
    *(_QWORD *)((char *)a2 + v124 + 16) = 0;
  }
  for ( m = 0; m < (*((_BYTE *)a3 + 32) != 0) + 1; ++m )
  {
    v126 = 0;
    if ( k > 0 )
    {
      do
      {
        v127 = v126++;
        v128 = 108LL * m + 232 * v127;
        *(_QWORD *)((char *)a2 + v128 + 24) = 0;
        *(_QWORD *)((char *)a2 + v128 + 36) = 0;
        *(_QWORD *)((char *)a2 + v128 + 44) = 0;
        *(_QWORD *)((char *)a2 + v128 + 52) = 0;
        *(_QWORD *)((char *)a2 + v128 + 60) = 0;
        *(_QWORD *)((char *)a2 + v128 + 68) = 0;
        *(_QWORD *)((char *)a2 + v128 + 76) = 0;
        *(_QWORD *)((char *)a2 + v128 + 84) = 0;
        *(_DWORD *)((char *)a2 + v128 + 92) = 0;
        k = *(_DWORD *)a3;
      }
      while ( v126 < *(_DWORD *)a3 );
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000a590  mov     [rsp+arg_0], rbx
0x18000a595  mov     [rsp+arg_10], r8
0x18000a59a  push    rbp
0x18000a59b  push    rsi
0x18000a59c  push    rdi
0x18000a59d  push    r12
0x18000a59f  push    r13
0x18000a5a1  push    r14
0x18000a5a3  push    r15
0x18000a5a5  sub     rsp, 20h
0x18000a5a9  xor     ebp, ebp
0x18000a5ab  mov     r13, r8
0x18000a5ae  mov     r9d, ebp
0x18000a5b1  mov     r14, rdx
0x18000a5b4  mov     rbx, rcx
0x18000a5b7  nop     word ptr [rax+rax+00000000h]
0x18000a5c0  movzx   ecx, byte ptr [r13+20h]
0x18000a5c5  mov     eax, ebp
0x18000a5c7  test    cl, cl
0x18000a5c9  setnz   al
0x18000a5cc  inc     eax
0x18000a5ce  cmp     r9d, eax
0x18000a5d1  jge     short loc_18000A626
0x18000a5d3  mov     edx, ebp
0x18000a5d5  cmp     [r13+0], ebp
0x18000a5d9  jle     short loc_18000A621
0x18000a5db  movsxd  rax, r9d
0x18000a5de  imul    r8, rax, 6Ch ; 'l'
0x18000a5e2  nop     dword ptr [rax+00h]
0x18000a5e6  nop     word ptr [rax+rax+00000000h]
0x18000a5f0  movsxd  rax, edx
0x18000a5f3  inc     edx
0x18000a5f5  imul    rcx, rax, 0E8h
0x18000a5fc  add     rcx, r14
0x18000a5ff  mov     [rcx+r8+60h], rbp
0x18000a604  mov     [rcx+r8+68h], rbp
0x18000a609  mov     [rcx+r8+70h], rbp
0x18000a60e  mov     [rcx+r8+78h], rbp
0x18000a613  mov     [rcx+r8+80h], ebp
0x18000a61b  cmp     edx, [r13+0]
0x18000a61f  jl      short loc_18000A5F0
0x18000a621  inc     r9d
0x18000a624  jmp     short loc_18000A5C0
0x18000a626  mov     eax, 9
0x18000a62b  cmp     [r13+1Ch], ebp
0x18000a62f  jz      loc_18000A6BA
0x18000a635  cmp     dword ptr [r13+0], 1
0x18000a63a  mov     esi, 11h
0x18000a63f  jnz     short loc_18000A648
0x18000a641  test    cl, cl
0x18000a643  cmovz   esi, eax
0x18000a646  jmp     short loc_18000A652
0x18000a648  test    cl, cl
0x18000a64a  mov     eax, 20h ; ' '
0x18000a64f  cmovnz  esi, eax
0x18000a652  mov     ecx, [rbx+24h]
0x18000a655  mov     edx, 10h; int
0x18000a65a  mov     eax, [rbx+14h]
0x18000a65d  sub     ecx, 20h ; ' '
0x18000a660  add     dword ptr [rbx+20h], 0FFFFFFE0h
0x18000a664  dec     eax
0x18000a666  add     dword ptr [rbx+18h], 20h ; ' '
0x18000a66a  and     ecx, eax
0x18000a66c  mov     [rbx+24h], ecx
0x18000a66f  mov     r8d, 0FFFFh; unsigned int
0x18000a675  mov     rcx, rbx; struct CBitStream *
0x18000a678  call    ?CalcCrc@@YAIAEAVCBitStream@@HI@Z; CalcCrc(CBitStream &,int,uint)
0x18000a67d  mov     edx, 10h; unsigned int
0x18000a682  mov     rcx, rbx; this
0x18000a685  mov     edi, eax
0x18000a687  call    ?GetBits@CBitStream@@QEAAII@Z; CBitStream::GetBits(uint)
0x18000a68c  lea     esi, ds:0[rsi*8]
0x18000a693  mov     r8d, edi; unsigned int
0x18000a696  mov     edx, esi; int
0x18000a698  mov     rcx, rbx; struct CBitStream *
0x18000a69b  call    ?CalcCrc@@YAIAEAVCBitStream@@HI@Z; CalcCrc(CBitStream &,int,uint)
0x18000a6a0  mov     ecx, [rbx+24h]
0x18000a6a3  mov     eax, [rbx+14h]
0x18000a6a6  sub     ecx, esi
0x18000a6a8  sub     [rbx+20h], esi
0x18000a6ab  dec     eax
0x18000a6ad  add     [rbx+18h], esi
0x18000a6b0  and     ecx, eax
0x18000a6b2  mov     eax, 9
0x18000a6b7  mov     [rbx+24h], ecx
0x18000a6ba  mov     rcx, rbx; this
0x18000a6bd  cmp     [r13+20h], bpl
0x18000a6c1  jz      loc_18000A945
0x18000a6c7  mov     edx, eax; unsigned int
0x18000a6c9  call    ?GetBits@CBitStream@@QEAAII@Z; CBitStream::GetBits(uint)
0x18000a6ce  mov     [r14], eax
0x18000a6d1  mov     edx, 5
0x18000a6d6  cmp     dword ptr [r13+0], 1
0x18000a6db  mov     eax, 3
0x18000a6e0  mov     rcx, rbx; this
0x18000a6e3  cmovnz  edx, eax; unsigned int
0x18000a6e6  call    ?GetBits@CBitStream@@QEAAII@Z; CBitStream::GetBits(uint)
0x18000a6eb  mov     [r14+4], eax
0x18000a6ef  mov     esi, ebp
0x18000a6f1  cmp     [r13+0], ebp
0x18000a6f5  jle     loc_18000A96F
0x18000a6fb  lea     r10, [rbx+10h]
0x18000a6ff  nop
0x18000a700  mov     edi, [rbx+24h]
0x18000a703  mov     eax, edi
0x18000a705  mov     r11, [rbx+30h]
0x18000a709  mov     edx, edi
0x18000a70b  sar     eax, 3
0x18000a70e  and     edx, 0Fh
0x18000a711  and     eax, 0FFFFFFFEh
0x18000a714  mov     ecx, edx
0x18000a716  mov     r8d, eax
0x18000a719  movzx   r9d, byte ptr [rax+r11]
0x18000a71e  inc     eax
0x18000a720  shl     r9w, 8
0x18000a725  movzx   eax, byte ptr [rax+r11]
0x18000a72a  or      r9w, ax
0x18000a72e  shl     r9w, cl
0x18000a732  mov     ecx, 10h
0x18000a737  sub     ecx, edx
0x18000a739  cmp     ecx, 1
0x18000a73c  jnb     short loc_18000A768
0x18000a73e  mov     eax, [r10]
0x18000a741  lea     edx, [r8+2]
0x18000a745  dec     eax
0x18000a747  and     edx, eax
0x18000a749  mov     eax, edx
0x18000a74b  movzx   r8d, byte ptr [rdx+r11]
0x18000a750  shl     r8w, 8
0x18000a755  inc     eax
0x18000a757  movzx   eax, byte ptr [rax+r11]
0x18000a75c  or      r8w, ax
0x18000a760  shr     r8w, cl
0x18000a764  or      r9w, r8w
0x18000a768  inc     dword ptr [rbx+20h]
0x18000a76b  lea     eax, [rdi+1]
0x18000a76e  dec     dword ptr [rbx+18h]
0x18000a771  mov     ecx, [rbx+14h]
0x18000a774  dec     ecx
0x18000a776  and     ecx, eax
0x18000a778  movsxd  rax, esi
0x18000a77b  imul    rdi, rax, 0E8h
0x18000a782  mov     [rbx+24h], ecx
0x18000a785  movzx   eax, r9w
0x18000a789  add     rdi, r14
0x18000a78c  shr     eax, 0Fh
0x18000a78f  mov     [rdi+8], eax
0x18000a792  mov     ebp, [rbx+24h]
0x18000a795  mov     eax, ebp
0x18000a797  mov     r11, [rbx+30h]
0x18000a79b  mov     edx, ebp
0x18000a79d  sar     eax, 3
0x18000a7a0  and     edx, 0Fh
0x18000a7a3  and     eax, 0FFFFFFFEh
0x18000a7a6  mov     ecx, edx
0x18000a7a8  mov     r8d, eax
0x18000a7ab  movzx   r9d, byte ptr [rax+r11]
0x18000a7b0  inc     eax
0x18000a7b2  shl     r9w, 8
0x18000a7b7  movzx   eax, byte ptr [rax+r11]
0x18000a7bc  or      r9w, ax
0x18000a7c0  shl     r9w, cl
0x18000a7c4  mov     ecx, 10h
0x18000a7c9  sub     ecx, edx
0x18000a7cb  cmp     ecx, 1
0x18000a7ce  jnb     short loc_18000A7FF
0x18000a7d0  mov     eax, [r10]
0x18000a7d3  lea     edx, [r8+2]
0x18000a7d7  dec     eax
0x18000a7d9  and     edx, eax
0x18000a7db  mov     eax, edx
0x18000a7dd  movzx   r8d, byte ptr [rdx+r11]
0x18000a7e2  shl     r8w, 8
0x18000a7e7  inc     eax
0x18000a7e9  movzx   eax, byte ptr [rax+r11]
0x18000a7ee  or      r8w, ax
0x18000a7f2  shr     r8w, cl
0x18000a7f6  or      r9w, r8w
0x18000a7fa  mov     r8, r10
0x18000a7fd  jmp     short loc_18000A803
0x18000a7ff  lea     r8, [rbx+10h]
0x18000a803  mov     eax, [rbx+14h]
0x18000a806  lea     ecx, [rbp+1]
0x18000a809  dec     eax
0x18000a80b  and     ecx, eax
0x18000a80d  movzx   eax, r9w
0x18000a811  mov     [rbx+24h], ecx
0x18000a814  inc     dword ptr [rbx+20h]
0x18000a817  dec     dword ptr [rbx+18h]
0x18000a81a  shr     eax, 0Fh
0x18000a81d  mov     [rdi+0Ch], eax
0x18000a820  mov     r15d, [rbx+24h]
0x18000a824  mov     eax, r15d
0x18000a827  mov     r11, [rbx+30h]
0x18000a82b  mov     edx, r15d
0x18000a82e  sar     eax, 3
0x18000a831  and     edx, 0Fh
0x18000a834  and     eax, 0FFFFFFFEh
0x18000a837  mov     ecx, edx
0x18000a839  mov     ebp, eax
0x18000a83b  movzx   r9d, byte ptr [r11+rax]
0x18000a840  inc     eax
0x18000a842  shl     r9w, 8
0x18000a847  movzx   eax, byte ptr [rax+r11]
0x18000a84c  or      r9w, ax
0x18000a850  shl     r9w, cl
0x18000a854  mov     ecx, 10h
0x18000a859  sub     ecx, edx
0x18000a85b  cmp     ecx, 1
0x18000a85e  jnb     short loc_18000A88C
0x18000a860  mov     eax, [r10]
0x18000a863  lea     edx, [rbp+2]
0x18000a866  dec     eax
0x18000a868  and     edx, eax
0x18000a86a  mov     eax, edx
0x18000a86c  movzx   r8d, byte ptr [rdx+r11]
0x18000a871  shl     r8w, 8
0x18000a876  inc     eax
0x18000a878  movzx   eax, byte ptr [rax+r11]
0x18000a87d  or      r8w, ax
0x18000a881  shr     r8w, cl
0x18000a885  or      r9w, r8w
0x18000a889  mov     r8, r10
0x18000a88c  mov     ecx, [rbx+14h]
0x18000a88f  lea     eax, [r15+1]
0x18000a893  dec     ecx
0x18000a895  and     ecx, eax
0x18000a897  movzx   eax, r9w
0x18000a89b  mov     [rbx+24h], ecx
0x18000a89e  inc     dword ptr [rbx+20h]
0x18000a8a1  dec     dword ptr [rbx+18h]
0x18000a8a4  shr     eax, 0Fh
0x18000a8a7  mov     [rdi+10h], eax
0x18000a8aa  mov     ebp, [rbx+24h]
0x18000a8ad  mov     eax, ebp
0x18000a8af  mov     r11, [rbx+30h]
0x18000a8b3  mov     edx, ebp
0x18000a8b5  sar     eax, 3
0x18000a8b8  and     edx, 0Fh
0x18000a8bb  and     eax, 0FFFFFFFEh
0x18000a8be  mov     ecx, edx
0x18000a8c0  mov     r15d, eax
0x18000a8c3  movzx   r9d, byte ptr [rax+r11]
0x18000a8c8  inc     eax
0x18000a8ca  shl     r9w, 8
0x18000a8cf  movzx   eax, byte ptr [rax+r11]
0x18000a8d4  or      r9w, ax
0x18000a8d8  shl     r9w, cl
0x18000a8dc  mov     ecx, 10h
0x18000a8e1  sub     ecx, edx
0x18000a8e3  cmp     ecx, 1
0x18000a8e6  jnb     short loc_18000A915
0x18000a8e8  mov     eax, [r10]
0x18000a8eb  lea     edx, [r15+2]
0x18000a8ef  dec     eax
0x18000a8f1  and     edx, eax
0x18000a8f3  mov     eax, edx
0x18000a8f5  movzx   r8d, byte ptr [rdx+r11]
0x18000a8fa  shl     r8w, 8
0x18000a8ff  inc     eax
0x18000a901  movzx   eax, byte ptr [rax+r11]
0x18000a906  or      r8w, ax
0x18000a90a  shr     r8w, cl
0x18000a90e  or      r9w, r8w
0x18000a912  mov     r8, r10
0x18000a915  mov     eax, [rbx+14h]
0x18000a918  lea     ecx, [rbp+1]
0x18000a91b  dec     eax
0x18000a91d  inc     esi
0x18000a91f  and     ecx, eax
0x18000a921  mov     r10, r8
0x18000a924  mov     [rbx+24h], ecx
0x18000a927  inc     dword ptr [rbx+20h]
0x18000a92a  dec     dword ptr [rbx+18h]
0x18000a92d  movzx   eax, r9w
0x18000a931  shr     eax, 0Fh
0x18000a934  mov     [rdi+14h], eax
0x18000a937  cmp     esi, [r13+0]
0x18000a93b  jl      loc_18000A700
0x18000a941  xor     ebp, ebp
0x18000a943  jmp     short loc_18000A96F
0x18000a945  mov     edx, 8; unsigned int
0x18000a94a  call    ?GetBits@CBitStream@@QEAAII@Z; CBitStream::GetBits(uint)
0x18000a94f  mov     [r14], eax
0x18000a952  mov     rcx, rbx; this
0x18000a955  cmp     dword ptr [r13+0], 1
0x18000a95a  mov     edx, 1
0x18000a95f  jz      short loc_18000A966
0x18000a961  mov     edx, 2; unsigned int
0x18000a966  call    ?GetBits@CBitStream@@QEAAII@Z; CBitStream::GetBits(uint)
0x18000a96b  mov     [r14+4], eax
0x18000a96f  mov     r12d, ebp
0x18000a972  nop     dword ptr [rax+00h]
0x18000a976  nop     word ptr [rax+rax+00000000h]
0x18000a980  cmp     byte ptr [r13+20h], 0
0x18000a985  mov     eax, ebp
0x18000a987  setnz   al
0x18000a98a  inc     eax
0x18000a98c  cmp     r12d, eax
0x18000a98f  jge     loc_18000B80C
  ... truncated ...
```
