# Xp10BuildAndWriteHuffmanTables

- ea: `0x180121da4`
- end: `0x180122754`
- name: `Xp10BuildAndWriteHuffmanTables`
- size: `2480`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180150f0c`

## callees

- `0x180112c2c`
- `0x180121da4`
- `0x180162810`
- `0x18016f030`

## pseudocode

```c
__int64 __fastcall Xp10BuildAndWriteHuffmanTables(int a1, __int64 a2, unsigned int a3, __int64 *a4)
{
  int v8; // r12d
  unsigned __int16 v9; // cx
  int v10; // r9d
  int v11; // edx
  int v12; // r8d
  int v13; // eax
  unsigned __int16 v14; // dx
  unsigned int v15; // r8d
  __int64 v16; // r15
  unsigned int v17; // r14d
  unsigned int v18; // r10d
  unsigned int v19; // edi
  __int64 v20; // rsi
  unsigned int v21; // eax
  unsigned int v22; // ecx
  unsigned int v23; // r8d
  unsigned int v24; // eax
  unsigned int v25; // r10d
  __int64 v26; // rdx
  _BYTE *v27; // r9
  unsigned int v28; // r11d
  int v29; // r10d
  unsigned __int64 v30; // r9
  unsigned int v31; // r8d
  __int64 v32; // rax
  char v33; // dl
  unsigned int v34; // eax
  __int64 v35; // rdx
  unsigned int v36; // r10d
  _BYTE *v37; // r8
  __int64 v38; // rsi
  unsigned int v39; // eax
  unsigned int v40; // r8d
  int v41; // ecx
  unsigned __int64 v42; // r11
  unsigned int v43; // r9d
  unsigned int v44; // r8d
  unsigned int v45; // r10d
  __int64 v46; // rax
  char v47; // dl
  unsigned int v48; // eax
  unsigned int v49; // r10d
  __int64 v50; // rdx
  _BYTE *v51; // r9
  __int64 v52; // rax
  char v53; // dl
  unsigned int v54; // eax
  unsigned int v55; // r13d
  unsigned __int16 v56; // r15
  int v57; // ecx
  int v58; // edx
  int v59; // eax
  int v60; // esi
  unsigned int v61; // r11d
  unsigned int v62; // r11d
  __int64 v63; // r9
  unsigned int v64; // edi
  int v65; // esi
  unsigned __int64 v66; // r10
  unsigned int v67; // r8d
  __int64 v68; // rax
  char v69; // dl
  unsigned int v70; // eax
  unsigned int v71; // edi
  __int64 v72; // rdx
  _BYTE *v73; // r8
  unsigned __int16 v74; // r11
  int v75; // r14d
  int v76; // ecx
  unsigned int v77; // edi
  unsigned int v78; // edi
  __int64 v79; // r9
  int v80; // ecx
  unsigned int v81; // esi
  unsigned int v82; // r8d
  unsigned __int64 v83; // r10
  __int64 v84; // rax
  char v85; // dl
  unsigned int v86; // eax
  unsigned int v87; // esi
  __int64 v88; // rdx
  _BYTE *v89; // r8
  unsigned int v90; // esi
  int v91; // r14d
  int v92; // ecx
  unsigned int v93; // r11d
  unsigned int v94; // r11d
  __int64 v95; // r9
  int v96; // ecx
  unsigned int v97; // edi
  unsigned int v98; // r8d
  unsigned __int64 v99; // r10
  __int64 v100; // rax
  char v101; // dl
  unsigned int v102; // eax
  unsigned int v103; // edi
  __int64 v104; // rdx
  _BYTE *v105; // r8
  unsigned int v106; // ecx
  unsigned int v107; // r11d
  unsigned int v108; // r11d
  __int64 v109; // r9
  int v110; // ecx
  unsigned int v111; // edi
  unsigned __int64 v112; // r10
  unsigned int v113; // r8d
  __int64 v114; // rax
  char v115; // dl
  unsigned int v116; // eax
  unsigned int v117; // edi
  __int64 v118; // rdx
  _BYTE *v119; // r8
  unsigned int v120; // r8d
  unsigned int v121; // r11d
  __int64 v122; // rsi
  unsigned int v123; // eax
  int v124; // r10d
  unsigned __int64 v125; // rdi
  unsigned int v126; // r9d
  unsigned int v127; // r8d
  __int64 v128; // rax
  char v129; // dl
  unsigned int v130; // eax
  unsigned int v131; // r11d
  __int64 v132; // rdx
  _BYTE *v133; // r9
  unsigned int v134; // r8d
  __int64 v135; // rax
  char v136; // dl
  unsigned int v137; // eax
  unsigned int v138; // r10d
  __int64 v139; // rdx
  _BYTE *v140; // r9
  unsigned int v141; // r11d
  unsigned int v142; // edi
  __int64 v143; // r9
  unsigned __int64 v144; // r10
  int v145; // ecx
  unsigned __int64 v146; // r10
  unsigned int v147; // r8d
  __int64 v148; // rax
  char v149; // dl
  unsigned int v150; // eax
  unsigned int v151; // esi
  __int64 v152; // rdx
  _BYTE *v153; // r8
  int v154; // ecx
  unsigned int v155; // edi
  unsigned int v156; // edi
  __int64 v157; // r9
  int v158; // ecx
  unsigned __int64 v159; // r10
  unsigned int v160; // r8d
  __int64 v161; // rax
  char v162; // dl
  unsigned int v163; // eax
  unsigned int v164; // r11d
  __int64 v165; // rdx
  _BYTE *v166; // r8
  int v169; // [rsp+34h] [rbp-CCh]
  _DWORD v171[28]; // [rsp+40h] [rbp-C0h] BYREF
  int v172; // [rsp+B0h] [rbp-50h]
  int v173; // [rsp+B4h] [rbp-4Ch]
  _DWORD v174[28]; // [rsp+D0h] [rbp-30h] BYREF
  unsigned int v175; // [rsp+140h] [rbp+40h]
  unsigned int v176; // [rsp+144h] [rbp+44h]

  memset_thunk_772440563353939046(v171, 0, 0x84u);
  memset_thunk_772440563353939046(v174, 0, 0x84u);
  v8 = 8;
  v9 = 0;
  v10 = 8;
  while ( v9 < a3 )
  {
    v11 = *(_DWORD *)(a2 + 4LL * v9) & 0x1F;
    if ( v11 )
    {
      if ( v11 == v10 )
      {
        v12 = 30;
      }
      else
      {
        v12 = *(_DWORD *)(a2 + 4LL * v9) & 0x1F;
        if ( v9 >= 0x10u )
        {
          v13 = *(_DWORD *)(a2 + 4LL * v9 - 64) & 0x1F;
          if ( v11 == v13 )
          {
            v12 = 31;
          }
          else if ( v11 == v13 + 1 )
          {
            v12 = 32;
          }
        }
        v10 = *(_DWORD *)(a2 + 4LL * v9) & 0x1F;
      }
      ++v171[v12];
      ++v9;
    }
    else
    {
      v14 = v9;
      while ( v9 < a3 && (*(_BYTE *)(a2 + 4LL * v9) & 0x1F) == 0 )
        ++v9;
      while ( (unsigned __int16)(v14 ^ v9) >= 0x10u )
      {
        ++v172;
        v14 = (v14 & 0xFFF0) + 16;
      }
      v15 = v9 - v14;
      if ( v9 != v14 )
      {
        if ( v15 >= 5 )
          ++v173;
        else
          v171[0] += v15;
      }
    }
  }
  Xp10BuildHuffmanEncodings(a1, (unsigned int)v171, 33, 8, (__int64)v174);
  v16 = 0;
  v17 = 4;
  do
  {
    v18 = *((_DWORD *)a4 + 2);
    v19 = v174[v16] & 0x1F;
    v20 = *a4;
    v21 = *((_DWORD *)a4 + 3);
    v22 = v18 + 1;
    if ( v19 != v17 )
    {
      v28 = 1;
      if ( v22 <= v21 || (v28 = v21 - v18, v21 != v18) )
      {
        v29 = a4[1] & 7;
        v30 = (unsigned __int64)*((unsigned int *)a4 + 2) >> 3;
        v31 = 8 - v29;
        v32 = (unsigned int)(8 - v29);
        if ( 8 - v29 >= v28 )
          v32 = v28;
        v33 = byte_180183300[4 * v32];
        v34 = v28;
        *(_BYTE *)(v30 + v20) |= (v33 & 1) << v29;
        if ( v31 < v28 )
          v34 = 8 - v29;
        v35 = v28 - v34;
        v36 = 1u >> v31;
        v37 = (_BYTE *)(v30 + v20 + 1);
        while ( (unsigned int)v35 >= 8 )
        {
          *v37 = v36;
          v35 = (unsigned int)(v35 - 8);
          v36 >>= 8;
          ++v37;
        }
        if ( (_DWORD)v35 )
          *v37 |= (unsigned __int8)v36 & byte_180183300[4 * v35];
        v18 = v28 + *((_DWORD *)a4 + 2);
        *((_DWORD *)a4 + 2) = v18;
      }
      v38 = *a4;
      v39 = v18 + 3;
      v40 = *((_DWORD *)a4 + 3);
      v41 = v18 & 7;
      v42 = (unsigned __int64)v18 >> 3;
      v43 = 8 - v41;
      if ( v19 <= v17 )
      {
        if ( v39 <= v40 )
        {
          v44 = 3;
        }
        else
        {
          v44 = v40 - v18;
          if ( !v44 )
            goto LABEL_75;
        }
        v52 = v44;
        if ( v43 < v44 )
          v52 = v43;
        v53 = byte_180183300[4 * v52];
        v54 = v44;
        *(_BYTE *)(v38 + v42) |= ((unsigned __int8)v19 & (unsigned __int8)v53) << v41;
        if ( v43 < v44 )
          v54 = 8 - v41;
        v49 = v19 >> v43;
        v50 = v44 - v54;
        v51 = (_BYTE *)(v42 + v38 + 1);
        while ( (unsigned int)v50 >= 8 )
        {
          *v51 = v49;
          v50 = (unsigned int)(v50 - 8);
          v49 >>= 8;
          ++v51;
        }
      }
      else
      {
        if ( v39 <= v40 )
        {
          v44 = 3;
        }
        else
        {
          v44 = v40 - v18;
          if ( !v44 )
          {
LABEL_75:
            v17 = v19;
            goto LABEL_76;
          }
        }
        v45 = v19 - 1;
        v46 = v44;
        if ( v43 < v44 )
          v46 = v43;
        v47 = byte_180183300[4 * v46];
        v48 = v44;
        *(_BYTE *)(v38 + v42) |= ((unsigned __int8)v45 & (unsigned __int8)v47) << v41;
        if ( v43 < v44 )
          v48 = 8 - v41;
        v49 = v45 >> v43;
        v50 = v44 - v48;
        v51 = (_BYTE *)(v42 + v38 + 1);
        while ( (unsigned int)v50 >= 8 )
        {
          *v51 = v49;
          v50 = (unsigned int)(v50 - 8);
          v49 >>= 8;
          ++v51;
        }
      }
      if ( (_DWORD)v50 )
        *v51 |= (unsigned __int8)v49 & byte_180183300[4 * v50];
      *((_DWORD *)a4 + 2) += v44;
      goto LABEL_75;
    }
    v23 = 1;
    if ( v22 <= v21 || (v23 = v21 - v18, v21 != v18) )
    {
      v24 = 8 - (a4[1] & 7);
      if ( v24 >= v23 )
        v24 = v23;
      v25 = 0;
      v26 = v23 - v24;
      v27 = (_BYTE *)(v20 + ((unsigned __int64)*((unsigned int *)a4 + 2) >> 3) + 1);
      while ( (unsigned int)v26 >= 8 )
      {
        *v27 = v25;
        v26 = (unsigned int)(v26 - 8);
        v25 >>= 8;
        ++v27;
      }
      if ( (_DWORD)v26 )
        *v27 |= (unsigned __int8)v25 & byte_180183300[4 * v26];
      *((_DWORD *)a4 + 2) += v23;
    }
LABEL_76:
    ++v16;
  }
  while ( v16 != 33 );
  v55 = a3;
  if ( a3 )
  {
    v169 = 8;
    v56 = 0;
    do
    {
      v57 = *(_DWORD *)(a2 + 4LL * v56) & 0x1F;
      if ( v57 )
      {
        if ( v57 == v8 )
        {
          v58 = 30;
        }
        else
        {
          v58 = *(_DWORD *)(a2 + 4LL * v56) & 0x1F;
          if ( v56 >= 0x10u )
          {
            v59 = *(_DWORD *)(a2 + 4LL * v56 - 64) & 0x1F;
            if ( v57 == v59 )
            {
              v58 = 31;
            }
            else if ( v57 == v59 + 1 )
            {
              v58 = 32;
            }
          }
          v8 = *(_DWORD *)(a2 + 4LL * v56) & 0x1F;
          v169 = v8;
        }
        v60 = *((_DWORD *)a4 + 2);
        v61 = *((_DWORD *)a4 + 3);
        if ( v60 + (v174[v58] & 0x1Fu) <= v61 )
        {
          v62 = v174[v58] & 0x1F;
        }
        else
        {
          v62 = v61 - v60;
          if ( !v62 )
          {
LABEL_102:
            ++v56;
            continue;
          }
        }
        v63 = *a4;
        v64 = v174[v58] >> 5;
        v65 = a4[1] & 7;
        v66 = (unsigned __int64)*((unsigned int *)a4 + 2) >> 3;
        v67 = 8 - v65;
        v68 = (unsigned int)(8 - v65);
        if ( 8 - v65 >= v62 )
          v68 = v62;
        v69 = byte_180183300[4 * v68];
        v70 = v62;
        *(_BYTE *)(v66 + v63) |= ((unsigned __int8)v64 & (unsigned __int8)v69) << v65;
        if ( v67 < v62 )
          v70 = 8 - v65;
        v71 = v64 >> v67;
        v72 = v62 - v70;
        v73 = (_BYTE *)(v66 + v63 + 1);
        while ( (unsigned int)v72 >= 8 )
        {
          *v73 = v71;
          v72 = (unsigned int)(v72 - 8);
          v71 >>= 8;
          ++v73;
        }
        if ( (_DWORD)v72 )
          *v73 |= (unsigned __int8)v71 & byte_180183300[4 * v72];
        *((_DWORD *)a4 + 2) += v62;
        goto LABEL_102;
      }
      v74 = v56;
      while ( v56 < v55 && (*(_BYTE *)(a2 + 4LL * v56) & 0x1F) == 0 )
        ++v56;
      if ( (unsigned __int16)(v74 ^ v56) >= 0x10u )
      {
        v75 = v175 & 0x1F;
        while ( 1 )
        {
          v76 = *((_DWORD *)a4 + 2);
          v77 = *((_DWORD *)a4 + 3);
          if ( v76 + v75 <= v77 )
            break;
          v78 = v77 - v76;
          if ( v78 )
            goto LABEL_113;
LABEL_123:
          v74 = (v74 & 0xFFF0) + 16;
          if ( (unsigned __int16)(v74 ^ v56) < 0x10u )
          {
            v8 = v169;
            v55 = a3;
            goto LABEL_125;
          }
        }
        v78 = v75;
LABEL_113:
        v79 = *a4;
        v80 = a4[1] & 7;
        v81 = v175 >> 5;
        v82 = 8 - v80;
        v83 = (unsigned __int64)*((unsigned int *)a4 + 2) >> 3;
        v84 = (unsigned int)(8 - v80);
        if ( 8 - v80 >= v78 )
          v84 = v78;
        v85 = byte_180183300[4 * v84];
        v86 = v78;
        *(_BYTE *)(v83 + v79) |= ((unsigned __int8)v81 & (unsigned __int8)v85) << v80;
        if ( v82 < v78 )
          v86 = 8 - v80;
        v87 = v81 >> v82;
        v88 = v78 - v86;
        v89 = (_BYTE *)(v83 + v79 + 1);
        while ( (unsigned int)v88 >= 8 )
        {
          *v89 = v87;
          v88 = (unsigned int)(v88 - 8);
          v87 >>= 8;
          ++v89;
        }
        if ( (_DWORD)v88 )
          *v89 |= (unsigned __int8)v87 & byte_180183300[4 * v88];
        *((_DWORD *)a4 + 2) += v78;
        goto LABEL_123;
      }
LABEL_125:
      v90 = v56 - v74;
      if ( v56 == v74 )
        continue;
      if ( v90 < 5 )
      {
        v91 = v174[0] & 0x1F;
        while ( 1 )
        {
          v92 = *((_DWORD *)a4 + 2);
          v93 = *((_DWORD *)a4 + 3);
          if ( v91 + v92 <= v93 )
            break;
          v94 = v93 - v92;
          if ( v94 )
            goto LABEL_132;
LABEL_142:
          if ( !--v90 )
          {
            v55 = a3;
            goto LABEL_216;
          }
        }
        v94 = v91;
LABEL_132:
        v95 = *a4;
        v96 = a4[1] & 7;
        v97 = v174[0] >> 5;
        v98 = 8 - v96;
        v99 = (unsigned __int64)*((unsigned int *)a4 + 2) >> 3;
        v100 = (unsigned int)(8 - v96);
        if ( 8 - v96 >= v94 )
          v100 = v94;
        v101 = byte_180183300[4 * v100];
        v102 = v94;
        *(_BYTE *)(v99 + v95) |= ((unsigned __int8)v97 & (unsigned __int8)v101) << v96;
        if ( v98 < v94 )
          v102 = 8 - v96;
        v103 = v97 >> v98;
        v104 = v94 - v102;
        v105 = (_BYTE *)(v99 + v95 + 1);
        while ( (unsigned int)v104 >= 8 )
        {
          *v105 = v103;
          v104 = (unsigned int)(v104 - 8);
          v103 >>= 8;
          ++v105;
        }
        if ( (_DWORD)v104 )
          *v105 |= (unsigned __int8)v103 & byte_180183300[4 * v104];
        *((_DWORD *)a4 + 2) += v94;
        goto LABEL_142;
      }
      v106 = *((_DWORD *)a4 + 2);
      v107 = *((_DWORD *)a4 + 3);
      if ( v106 + (v176 & 0x1F) <= v107 )
      {
        v108 = v176 & 0x1F;
      }
      else
      {
        v108 = v107 - v106;
        if ( !v108 )
          goto LABEL_158;
      }
      v109 = *a4;
      v110 = a4[1] & 7;
      v111 = v176 >> 5;
      v112 = (unsigned __int64)*((unsigned int *)a4 + 2) >> 3;
      v113 = 8 - v110;
      v114 = (unsigned int)(8 - v110);
      if ( 8 - v110 >= v108 )
        v114 = v108;
      v115 = byte_180183300[4 * v114];
      v116 = v108;
      *(_BYTE *)(v112 + v109) |= ((unsigned __int8)v111 & (unsigned __int8)v115) << v110;
      if ( v113 < v108 )
        v116 = 8 - v110;
      v117 = v111 >> v113;
      v118 = v108 - v116;
      v119 = (_BYTE *)(v112 + v109 + 1);
      while ( (unsigned int)v118 >= 8 )
      {
        *v119 = v117;
        v118 = (unsigned int)(v118 - 8);
        v117 >>= 8;
        ++v119;
      }
      if ( (_DWORD)v118 )
        *v119 |= (unsigned __int8)v117 & byte_180183300[4 * v118];
      v106 = v108 + *((_DWORD *)a4 + 2);
      *((_DWORD *)a4 + 2) = v106;
LABEL_158:
      v120 = *((_DWORD *)a4 + 3);
      v121 = v90 - 5;
      v122 = *a4;
      v123 = v106 + 2;
      v124 = v106 & 7;
      v125 = (unsigned __int64)v106 >> 3;
      v126 = 8 - v124;
      if ( v121 >= 3 )
      {
        if ( v123 <= v120 )
        {
          v134 = 2;
        }
        else
        {
          v134 = v120 - v106;
          if ( !v134 )
          {
LABEL_187:
            v141 = v121 - 3;
            if ( v141 >= 7 )
            {
              do
              {
                v142 = 3;
                if ( v106 + 3 <= *((_DWORD *)a4 + 3) || (v142 = *((_DWORD *)a4 + 3) - v106) != 0 )
                {
                  v143 = *a4;
                  v144 = v106;
                  v145 = v106 & 7;
                  v146 = v144 >> 3;
                  v147 = 8 - v145;
                  v148 = (unsigned int)(8 - v145);
                  if ( 8 - v145 >= v142 )
                    v148 = v142;
                  v149 = byte_180183300[4 * v148];
                  v150 = v142;
                  *(_BYTE *)(v146 + v143) |= (v149 & 7) << v145;
                  if ( v147 < v142 )
                    v150 = 8 - v145;
                  v151 = 7u >> v147;
                  v152 = v142 - v150;
                  v153 = (_BYTE *)(v146 + v143 + 1);
                  while ( (unsigned int)v152 >= 8 )
                  {
                    *v153 = v151;
                    v152 = (unsigned int)(v152 - 8);
                    v151 >>= 8;
                    ++v153;
                  }
                  if ( (_DWORD)v152 )
                    *v153 |= (unsigned __int8)v151 & byte_180183300[4 * v152];
                  v106 = v142 + *((_DWORD *)a4 + 2);
                  *((_DWORD *)a4 + 2) = v106;
                }
                v141 -= 7;
              }
              while ( v141 >= 7 );
              v55 = a3;
            }
            v154 = *((_DWORD *)a4 + 2);
            v155 = *((_DWORD *)a4 + 3);
            if ( v154 + 3 <= v155 )
            {
              v156 = 3;
LABEL_206:
              v157 = *a4;
              v158 = a4[1] & 7;
              v159 = (unsigned __int64)*((unsigned int *)a4 + 2) >> 3;
              v160 = 8 - v158;
              v161 = (unsigned int)(8 - v158);
              if ( 8 - v158 >= v156 )
                v161 = v156;
              v162 = byte_180183300[4 * v161];
              v163 = v156;
              *(_BYTE *)(v159 + v157) |= ((unsigned __int8)v141 & (unsigned __int8)v162) << v158;
              if ( v160 < v156 )
                v163 = 8 - v158;
              v164 = v141 >> v160;
              v165 = v156 - v163;
              v166 = (_BYTE *)(v159 + v157 + 1);
              while ( (unsigned int)v165 >= 8 )
              {
                *v166 = v164;
                v165 = (unsigned int)(v165 - 8);
                v164 >>= 8;
                ++v166;
              }
              if ( (_DWORD)v165 )
                *v166 |= (unsigned __int8)v164 & byte_180183300[4 * v165];
              *((_DWORD *)a4 + 2) += v156;
              continue;
            }
            v156 = v155 - v154;
            if ( v156 )
              goto LABEL_206;
            continue;
          }
        }
        v135 = v134;
        if ( v126 < v134 )
          v135 = v126;
        v136 = byte_180183300[4 * v135];
        v137 = v134;
        *(_BYTE *)(v122 + v125) |= (v136 & 3) << v124;
        if ( v126 < v134 )
          v137 = 8 - v124;
        v138 = 3u >> v126;
        v139 = v134 - v137;
        v140 = (_BYTE *)(v125 + v122 + 1);
        while ( (unsigned int)v139 >= 8 )
        {
          *v140 = v138;
          v139 = (unsigned int)(v139 - 8);
          v138 >>= 8;
          ++v140;
        }
        if ( (_DWORD)v139 )
          *v140 |= (unsigned __int8)v138 & byte_180183300[4 * v139];
        v106 = v134 + *((_DWORD *)a4 + 2);
        *((_DWORD *)a4 + 2) = v106;
        goto LABEL_187;
      }
      if ( v123 <= v120 )
      {
        v127 = 2;
LABEL_163:
        v128 = v127;
        if ( v126 < v127 )
          v128 = v126;
        v129 = byte_180183300[4 * v128];
        v130 = v127;
        *(_BYTE *)(v122 + v125) |= ((unsigned __int8)v121 & (unsigned __int8)v129) << v124;
        if ( v126 < v127 )
          v130 = 8 - v124;
        v131 = v121 >> v126;
        v132 = v127 - v130;
        v133 = (_BYTE *)(v125 + v122 + 1);
        while ( (unsigned int)v132 >= 8 )
        {
          *v133 = v131;
          v132 = (unsigned int)(v132 - 8);
          v131 >>= 8;
          ++v133;
        }
        if ( (_DWORD)v132 )
          *v133 |= (unsigned __int8)v131 & byte_180183300[4 * v132];
        *((_DWORD *)a4 + 2) += v127;
        continue;
      }
      v127 = v120 - v106;
      if ( v127 )
        goto LABEL_163;
LABEL_216:
      ;
    }
    while ( v56 < v55 );
  }
  return 0;
}

```

## disassembly

```asm
0x180121da4  mov     [rsp-8+arg_10], rbx
0x180121da9  push    rbp
0x180121daa  push    rsi
0x180121dab  push    rdi
0x180121dac  push    r12
0x180121dae  push    r13
0x180121db0  push    r14
0x180121db2  push    r15
0x180121db4  lea     rbp, [rsp-70h]
0x180121db9  sub     rsp, 170h
0x180121dc0  mov     rax, cs:__security_cookie
0x180121dc7  xor     rax, rsp
0x180121dca  mov     [rbp+0A0h+var_40], rax
0x180121dce  mov     r13d, r8d
0x180121dd1  mov     [rsp+1A0h+var_170], r8d
0x180121dd6  mov     rsi, rdx
0x180121dd9  mov     [rsp+1A0h+var_168], rdx
0x180121dde  mov     rdi, rcx
0x180121de1  mov     r14d, 84h
0x180121de7  mov     r8d, r14d; Size
0x180121dea  lea     rcx, [rsp+1A0h+var_160]; void *
0x180121def  xor     edx, edx; Val
0x180121df1  mov     rbx, r9
0x180121df4  call    memset$thunk$772440563353939046
0x180121df9  mov     r8d, r14d; Size
0x180121dfc  lea     rcx, [rbp+0A0h+var_D0]; void *
0x180121e00  xor     edx, edx; Val
0x180121e02  call    memset$thunk$772440563353939046
0x180121e07  lea     r12d, [r14-7Ch]
0x180121e0b  xor     ecx, ecx
0x180121e0d  lea     r11d, [r14-65h]
0x180121e11  mov     r9d, r12d
0x180121e14  lea     r15d, [r12+18h]
0x180121e19  mov     r14w, 10h
0x180121e1e  lea     r10d, [r12-7]
0x180121e23  mov     r8d, 0FFF0h
0x180121e29  test    r13d, r13d
0x180121e2c  jz      loc_180121EDF
0x180121e32  movzx   eax, cx
0x180121e35  mov     edx, [rsi+rax*4]
0x180121e38  and     edx, r11d
0x180121e3b  jz      short loc_180121E7C
0x180121e3d  cmp     edx, r9d
0x180121e40  jnz     short loc_180121E4A
0x180121e42  mov     r8d, 1Eh
0x180121e48  jmp     short loc_180121E6E
0x180121e4a  mov     r8d, edx
0x180121e4d  cmp     cx, r14w
0x180121e51  jb      short loc_180121E6B
0x180121e53  mov     eax, [rsi+rax*4-40h]
0x180121e57  and     eax, r11d
0x180121e5a  cmp     edx, eax
0x180121e5c  jnz     short loc_180121E63
0x180121e5e  mov     r8d, r11d
0x180121e61  jmp     short loc_180121E6B
0x180121e63  inc     eax
0x180121e65  cmp     edx, eax
0x180121e67  cmovz   r8d, r15d
0x180121e6b  mov     r9d, edx
0x180121e6e  mov     eax, r8d
0x180121e71  add     [rsp+rax*4+1A0h+var_160], r10d
0x180121e76  add     cx, r10w
0x180121e7a  jmp     short loc_180121ECD
0x180121e7c  movzx   edx, cx
0x180121e7f  jmp     short loc_180121E8E
0x180121e81  movzx   eax, cx
0x180121e84  test    [rsi+rax*4], r11b
0x180121e88  jnz     short loc_180121EA4
0x180121e8a  add     cx, r10w
0x180121e8e  movzx   eax, cx
0x180121e91  cmp     eax, r13d
0x180121e94  jb      short loc_180121E81
0x180121e96  jmp     short loc_180121EA4
0x180121e98  add     [rbp+0A0h+var_F0], r10d
0x180121e9c  and     dx, r8w
0x180121ea0  add     dx, r14w
0x180121ea4  movzx   eax, cx
0x180121ea7  xor     ax, dx
0x180121eaa  cmp     ax, r14w
0x180121eae  jnb     short loc_180121E98
0x180121eb0  movzx   r8d, cx
0x180121eb4  movzx   eax, dx
0x180121eb7  sub     r8d, eax
0x180121eba  jz      short loc_180121ECD
0x180121ebc  cmp     r8d, 5
0x180121ec0  jnb     short loc_180121EC9
0x180121ec2  add     [rsp+1A0h+var_160], r8d
0x180121ec7  jmp     short loc_180121ECD
0x180121ec9  add     [rbp+0A0h+var_EC], r10d
0x180121ecd  movzx   eax, cx
0x180121ed0  mov     r8d, 0FFF0h
0x180121ed6  cmp     eax, r13d
0x180121ed9  jb      loc_180121E32
0x180121edf  lea     rax, [rbp+0A0h+var_D0]
0x180121ee3  mov     r9d, r12d
0x180121ee6  mov     r8d, 21h ; '!'
0x180121eec  mov     [rsp+1A0h+var_180], rax
0x180121ef1  lea     rdx, [rsp+1A0h+var_160]
0x180121ef6  mov     rcx, rdi
0x180121ef9  call    Xp10BuildHuffmanEncodings
0x180121efe  xor     r15d, r15d
0x180121f01  lea     r13, byte_180183300
0x180121f08  mov     r14d, 4
0x180121f0e  mov     edi, [rbp+r15*4+0A0h+var_D0]
0x180121f13  mov     r10d, [rbx+8]
0x180121f17  and     edi, 1Fh
0x180121f1a  mov     rsi, [rbx]
0x180121f1d  mov     eax, [rbx+0Ch]
0x180121f20  lea     ecx, [r10+1]
0x180121f24  cmp     edi, r14d
0x180121f27  jnz     short loc_180121F93
0x180121f29  mov     edi, 1
0x180121f2e  mov     r8d, edi
0x180121f31  cmp     ecx, eax
0x180121f33  jbe     short loc_180121F41
0x180121f35  mov     r8d, eax
0x180121f38  sub     r8d, r10d
0x180121f3b  jz      loc_180122121
0x180121f41  mov     r9, r10
0x180121f44  mov     eax, r12d
0x180121f47  and     r10d, 7
0x180121f4b  shr     r9, 3
0x180121f4f  sub     eax, r10d
0x180121f52  mov     edx, r8d
0x180121f55  cmp     eax, r8d
0x180121f58  cmovnb  eax, r8d
0x180121f5c  xor     r10d, r10d
0x180121f5f  sub     edx, eax
0x180121f61  inc     r9
0x180121f64  add     r9, rsi
0x180121f67  jmp     short loc_180121F76
0x180121f69  mov     [r9], r10b
0x180121f6c  add     edx, 0FFFFFFF8h
0x180121f6f  shr     r10d, 8
0x180121f73  add     r9, rdi
0x180121f76  cmp     edx, r12d
0x180121f79  jnb     short loc_180121F69
0x180121f7b  test    edx, edx
0x180121f7d  jz      short loc_180121F8A
0x180121f7f  mov     cl, [r13+rdx*4+0]
0x180121f84  and     cl, r10b
0x180121f87  or      [r9], cl
0x180121f8a  add     [rbx+8], r8d
0x180121f8e  jmp     loc_180122121
0x180121f93  mov     r11d, 1
0x180121f99  cmp     ecx, eax
0x180121f9b  jbe     short loc_180121FA5
0x180121f9d  mov     r11d, eax
0x180121fa0  sub     r11d, r10d
0x180121fa3  jz      short loc_180122023
0x180121fa5  mov     r9, r10
0x180121fa8  mov     r8d, r12d
0x180121fab  and     r10d, 7
0x180121faf  shr     r9, 3
0x180121fb3  sub     r8d, r10d
0x180121fb6  mov     ecx, r10d
0x180121fb9  mov     eax, r8d
0x180121fbc  cmp     r8d, r11d
0x180121fbf  cmovnb  eax, r11d
0x180121fc3  mov     dl, [r13+rax*4+0]
0x180121fc8  mov     eax, r11d
0x180121fcb  and     dl, 1
0x180121fce  shl     dl, cl
0x180121fd0  mov     ecx, r8d
0x180121fd3  or      [r9+rsi], dl
0x180121fd7  mov     edx, r11d
0x180121fda  cmp     r8d, r11d
0x180121fdd  cmovb   eax, r8d
0x180121fe1  lea     r8, [rsi+1]
0x180121fe5  sub     edx, eax
0x180121fe7  mov     eax, 1
0x180121fec  mov     r10d, eax
0x180121fef  shr     r10d, cl
0x180121ff2  add     r8, r9
0x180121ff5  jmp     short loc_180122004
0x180121ff7  mov     [r8], r10b
0x180121ffa  add     edx, 0FFFFFFF8h
0x180121ffd  shr     r10d, 8
0x180122001  add     r8, rax
0x180122004  cmp     edx, r12d
0x180122007  jnb     short loc_180121FF7
0x180122009  test    edx, edx
0x18012200b  jz      short loc_180122018
0x18012200d  mov     cl, [r13+rdx*4+0]
0x180122012  and     cl, r10b
0x180122015  or      [r8], cl
0x180122018  mov     r10d, [rbx+8]
0x18012201c  add     r10d, r11d
0x18012201f  mov     [rbx+8], r10d
0x180122023  mov     rsi, [rbx]
0x180122026  lea     eax, [r10+3]
0x18012202a  mov     r8d, [rbx+0Ch]
0x18012202e  mov     ecx, r10d
0x180122031  and     ecx, 7
0x180122034  mov     r11d, r10d
0x180122037  mov     r9d, r12d
0x18012203a  shr     r11, 3
0x18012203e  sub     r9d, ecx
0x180122041  cmp     edi, r14d
0x180122044  jbe     short loc_1801220A9
0x180122046  cmp     eax, r8d
0x180122049  jbe     short loc_180122055
0x18012204b  sub     r8d, r10d
0x18012204e  jnz     short loc_18012205B
0x180122050  jmp     loc_180122119
0x180122055  mov     r8d, 3
0x18012205b  cmp     r9d, r8d
0x18012205e  lea     r10d, [rdi-1]
0x180122062  mov     eax, r8d
0x180122065  cmovb   eax, r9d
0x180122069  mov     dl, [r13+rax*4+0]
0x18012206e  mov     eax, r8d
0x180122071  and     dl, r10b
0x180122074  shl     dl, cl
0x180122076  mov     ecx, r9d
0x180122079  or      [rsi+r11], dl
0x18012207d  mov     edx, r8d
0x180122080  cmp     r9d, r8d
0x180122083  cmovb   eax, r9d
0x180122087  shr     r10d, cl
0x18012208a  sub     edx, eax
0x18012208c  lea     r9, [rsi+1]
0x180122090  add     r9, r11
0x180122093  jmp     short loc_1801220A2
0x180122095  mov     [r9], r10b
0x180122098  add     edx, 0FFFFFFF8h
0x18012209b  shr     r10d, 8
0x18012209f  inc     r9
0x1801220a2  cmp     edx, r12d
0x1801220a5  jnb     short loc_180122095
0x1801220a7  jmp     short loc_180122106
0x1801220a9  cmp     eax, r8d
0x1801220ac  jbe     short loc_1801220B5
0x1801220ae  sub     r8d, r10d
0x1801220b1  jnz     short loc_1801220BB
0x1801220b3  jmp     short loc_180122119
0x1801220b5  mov     r8d, 3
0x1801220bb  cmp     r9d, r8d
0x1801220be  mov     eax, r8d
0x1801220c1  mov     r10d, edi
0x1801220c4  cmovb   eax, r9d
0x1801220c8  mov     dl, [r13+rax*4+0]
0x1801220cd  mov     eax, r8d
0x1801220d0  and     dl, dil
0x1801220d3  shl     dl, cl
0x1801220d5  mov     ecx, r9d
0x1801220d8  or      [rsi+r11], dl
0x1801220dc  mov     edx, r8d
0x1801220df  cmp     r9d, r8d
0x1801220e2  cmovb   eax, r9d
0x1801220e6  shr     r10d, cl
0x1801220e9  sub     edx, eax
0x1801220eb  lea     r9, [rsi+1]
0x1801220ef  add     r9, r11
0x1801220f2  jmp     short loc_180122101
0x1801220f4  mov     [r9], r10b
0x1801220f7  add     edx, 0FFFFFFF8h
0x1801220fa  shr     r10d, 8
0x1801220fe  inc     r9
0x180122101  cmp     edx, r12d
0x180122104  jnb     short loc_1801220F4
0x180122106  test    edx, edx
0x180122108  jz      short loc_180122115
0x18012210a  mov     cl, [r13+rdx*4+0]
0x18012210f  and     cl, r10b
0x180122112  or      [r9], cl
0x180122115  add     [rbx+8], r8d
0x180122119  mov     r14d, edi
0x18012211c  mov     edi, 1
0x180122121  inc     r15
0x180122124  cmp     r15, 21h ; '!'
0x180122128  jnz     loc_180121F0E
0x18012212e  mov     r13d, [rsp+1A0h+var_170]
0x180122133  test    r13d, r13d
0x180122136  jz      loc_18012272A
0x18012213c  mov     r14d, r12d
0x18012213f  mov     [rsp+1A0h+var_16C], r12d
0x180122144  xor     r15d, r15d
0x180122147  mov     r8, [rsp+1A0h+var_168]
0x18012214c  movzx   eax, r15w
0x180122150  mov     ecx, [r8+rax*4]
0x180122154  and     ecx, 1Fh
0x180122157  jz      loc_180122245
0x18012215d  cmp     ecx, r12d
0x180122160  jnz     short loc_180122169
0x180122162  mov     edx, 1Eh
0x180122167  jmp     short loc_180122198
0x180122169  mov     edx, ecx
0x18012216b  cmp     r15w, 10h
0x180122170  jb      short loc_180122191
0x180122172  mov     eax, [r8+rax*4-40h]
0x180122177  and     eax, 1Fh
0x18012217a  cmp     ecx, eax
0x18012217c  jnz     short loc_180122185
0x18012217e  mov     edx, 1Fh
0x180122183  jmp     short loc_180122191
0x180122185  inc     eax
0x180122187  cmp     ecx, eax
0x180122189  mov     eax, 20h ; ' '
0x18012218e  cmovz   edx, eax
  ... truncated ...
```
