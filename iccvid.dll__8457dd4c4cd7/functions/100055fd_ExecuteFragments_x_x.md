# ExecuteFragments(x,x)

- ea: `0x100055fd`
- end: `0x10006397`
- name: `_ExecuteFragments@8`
- size: `3482`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x10006900`

## callees

- `0x100055fd`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x10006387`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x10006387`

## pseudocode

```c
int __fastcall ExecuteFragments(const void *a1, int a2)
{
  int v2; // edx
  unsigned int v3; // ecx
  unsigned __int8 *v4; // edi
  unsigned int v5; // ebx
  int result; // eax
  int v7; // esi
  int v8; // esi
  unsigned int v9; // eax
  _BYTE *v10; // esi
  unsigned __int8 *v11; // eax
  int v12; // ecx
  unsigned __int8 *v13; // eax
  unsigned __int8 *v14; // esi
  unsigned __int8 v15; // ah
  char v16; // al
  unsigned __int8 v17; // ah
  unsigned __int8 v18; // ah
  bool v19; // zf
  unsigned __int8 *v20; // eax
  unsigned __int8 v21; // ah
  char v22; // al
  unsigned __int8 v23; // ah
  unsigned __int8 *v24; // esi
  bool v25; // zf
  unsigned __int8 *v26; // eax
  unsigned __int8 v27; // al
  int v28; // edi
  int v29; // eax
  int v30; // eax
  int v31; // eax
  _BYTE *v32; // esi
  _BYTE *v33; // esi
  _BYTE *v34; // esi
  int v35; // ecx
  bool v36; // zf
  unsigned __int8 *v37; // ebx
  unsigned int v38; // ecx
  unsigned __int8 *v39; // esi
  int v40; // eax
  bool v41; // zf
  int v42; // esi
  unsigned int v43; // ebx
  bool v44; // cf
  unsigned __int8 v45; // al
  unsigned __int8 v46; // cl
  unsigned __int8 *v47; // esi
  int v48; // eax
  unsigned __int8 *v49; // esi
  unsigned __int8 v50; // al
  _BYTE *v51; // ecx
  unsigned __int8 v52; // al
  _BYTE *v53; // ecx
  _BYTE *v54; // ecx
  unsigned __int8 *v55; // esi
  unsigned __int8 v56; // al
  int v57; // edx
  unsigned __int8 v58; // al
  _BYTE *v59; // esi
  unsigned __int8 *v60; // eax
  unsigned int v61; // ebx
  unsigned __int8 *v62; // edx
  unsigned __int8 *v63; // eax
  unsigned __int8 *v64; // ecx
  int v65; // ecx
  int v66; // eax
  unsigned __int8 *v67; // edx
  unsigned int v68; // ecx
  int v69; // eax
  int v70; // ecx
  int v71; // eax
  unsigned __int8 *v72; // edx
  unsigned int v73; // ecx
  unsigned __int8 *v74; // eax
  unsigned __int8 *v75; // eax
  unsigned __int8 *v76; // eax
  _BYTE *v77; // esi
  unsigned int v78; // eax
  int v79; // ecx
  int v80; // eax
  unsigned __int8 *v81; // esi
  unsigned int v82; // ebx
  _BYTE *v83; // edx
  unsigned int v84; // ecx
  int v85; // eax
  unsigned __int8 *v86; // eax
  unsigned __int8 *v87; // eax
  unsigned __int8 *v88; // esi
  _BYTE *v89; // ecx
  unsigned int v90; // eax
  _BYTE *v91; // ecx
  int v92; // ecx
  int v93; // eax
  _BYTE *v94; // esi
  unsigned int v95; // ebx
  unsigned __int8 *v96; // edx
  unsigned __int8 *v97; // eax
  unsigned __int8 *v98; // ecx
  int v99; // ecx
  int v100; // eax
  unsigned __int8 *v101; // edi
  unsigned int v102; // ecx
  int v103; // eax
  int v104; // ecx
  int v105; // eax
  unsigned __int8 *v106; // edi
  unsigned int v107; // ecx
  unsigned __int8 *v108; // eax
  unsigned __int8 *v109; // eax
  unsigned __int8 *v110; // eax
  _DWORD v111[461]; // [esp+Ch] [ebp-80Ch] BYREF
  int v112; // [esp+740h] [ebp-D8h]
  int v113; // [esp+744h] [ebp-D4h]
  int v114; // [esp+748h] [ebp-D0h]
  int v115; // [esp+74Ch] [ebp-CCh]
  unsigned __int8 *v116; // [esp+750h] [ebp-C8h]
  int v117; // [esp+754h] [ebp-C4h]
  int v118; // [esp+758h] [ebp-C0h]
  _BYTE *v119; // [esp+75Ch] [ebp-BCh]
  unsigned __int8 *v120; // [esp+760h] [ebp-B8h]
  unsigned __int8 *v121; // [esp+764h] [ebp-B4h]
  int v122; // [esp+768h] [ebp-B0h]
  int v123; // [esp+76Ch] [ebp-ACh]
  int v124; // [esp+770h] [ebp-A8h]
  int v125; // [esp+774h] [ebp-A4h]
  int v126; // [esp+778h] [ebp-A0h]
  int v127; // [esp+77Ch] [ebp-9Ch]
  int v128; // [esp+780h] [ebp-98h]
  unsigned __int8 *v129; // [esp+784h] [ebp-94h]
  int v130; // [esp+788h] [ebp-90h]
  _BYTE *v131; // [esp+78Ch] [ebp-8Ch]
  int v132; // [esp+790h] [ebp-88h]
  int v133; // [esp+794h] [ebp-84h]
  _BYTE *v134; // [esp+798h] [ebp-80h]
  unsigned __int8 *v135; // [esp+79Ch] [ebp-7Ch]
  unsigned __int8 *v136; // [esp+7A0h] [ebp-78h]
  int v137; // [esp+7A4h] [ebp-74h]
  _BYTE *v138; // [esp+7A8h] [ebp-70h]
  __int16 v139; // [esp+7ACh] [ebp-6Ch]
  int v140; // [esp+7B0h] [ebp-68h]
  int v141; // [esp+7B4h] [ebp-64h]
  int v142; // [esp+7B8h] [ebp-60h]
  int v143; // [esp+7BCh] [ebp-5Ch]
  int v144; // [esp+7C0h] [ebp-58h]
  _BYTE *v145; // [esp+7C4h] [ebp-54h]
  int v146; // [esp+7C8h] [ebp-50h]
  unsigned __int8 *v147; // [esp+7CCh] [ebp-4Ch]
  unsigned int v148; // [esp+7D0h] [ebp-48h]
  _BYTE *v149; // [esp+7D4h] [ebp-44h]
  unsigned __int8 *v150; // [esp+7D8h] [ebp-40h]
  int v151; // [esp+7DCh] [ebp-3Ch]
  unsigned __int8 *v152; // [esp+7E0h] [ebp-38h]
  unsigned __int8 *v153; // [esp+7E4h] [ebp-34h]
  unsigned __int8 *v154; // [esp+7E8h] [ebp-30h]
  int v155; // [esp+7ECh] [ebp-2Ch]
  int v156; // [esp+7F0h] [ebp-28h]
  int v157; // [esp+7F4h] [ebp-24h]
  unsigned __int8 *v158; // [esp+7F8h] [ebp-20h]
  unsigned __int8 *v159; // [esp+7FCh] [ebp-1Ch]
  unsigned __int8 *v160; // [esp+800h] [ebp-18h]
  unsigned __int8 *v161; // [esp+804h] [ebp-14h]
  unsigned int v162; // [esp+808h] [ebp-10h]
  unsigned __int8 v163; // [esp+80Fh] [ebp-9h]
  unsigned __int8 v164; // [esp+810h] [ebp-8h]
  char v165; // [esp+811h] [ebp-7h]
  unsigned __int8 v166; // [esp+812h] [ebp-6h]
  unsigned __int8 v167; // [esp+813h] [ebp-5h]
  _BYTE *v168; // [esp+814h] [ebp-4h]

  v157 = a2;
  v2 = 0;
  v140 = 1;
  v165 = 0;
  v142 = 0;
  qmemcpy(v111, a1, sizeof(v111));
  v3 = 0;
  v168 = 0;
  v4 = 0;
  v166 = 0;
  v5 = 0;
  LOBYTE(v125) = 0;
  LOBYTE(v124) = 0;
  v148 = HIWORD(v111[4]);
  v117 = v111[11];
  v141 = 0;
  v130 = 0;
  v129 = 0;
  v146 = 0;
  v127 = 0;
  v118 = 0;
  v131 = 0;
  v119 = 0;
  v162 = 0;
  v147 = 0;
  v121 = 0;
  v158 = 0;
  v152 = 0;
  v150 = 0;
  v120 = 0;
  v144 = 0;
  v151 = 0;
  v167 = 0;
  v163 = 0;
  v164 = 0;
  v136 = 0;
  v138 = 0;
  v135 = 0;
  v161 = 0;
  v134 = 0;
  v149 = 0;
  v145 = 0;
  v154 = 0;
  v160 = 0;
  v159 = 0;
  v153 = 0;
  v143 = 0;
  v128 = 0;
  v156 = 0;
  v133 = 0;
  v155 = 0;
  v132 = 0;
  v122 = 0;
  v137 = 4 * HIWORD(v111[4]);
  v116 = (unsigned __int8 *)v111[7];
  while ( 1 )
  {
LABEL_2:
    result = (int)v168;
    while ( 2 )
    {
      v123 = v144;
      v112 = v144;
      v113 = v144;
      v114 = v144;
      v115 = v144;
      v7 = *(_DWORD *)(v157 + 4 * v2++);
      v126 = v2;
      switch ( v7 )
      {
        case 0:
          continue;
        case 1:
          v142 = v111[8];
          v151 = LOWORD(v111[6]) >> 1;
          v141 = v111[8] + 2;
          v131 = (_BYTE *)v111[0];
          v130 = v111[8] + 16;
          v8 = v111[8] + 18;
          v119 = (_BYTE *)v111[1];
          goto LABEL_5;
        case 2:
          v136 = v116;
          if ( v117 )
          {
            --v117;
            v116 += v111[3];
          }
          v134 = (_BYTE *)v3;
          v165 = 1;
          v149 = (_BYTE *)(v137 + v3);
          v145 = (_BYTE *)(v137 + v137 + v3);
          v5 = v148;
          v3 += v148;
          v161 = (unsigned __int8 *)v142;
          if ( v3 >= v111[2] + v137 )
            v3 = v111[2];
          v162 = v3;
          v144 = v111[3] - 1;
          goto LABEL_2;
        case 3:
          *v134 = (unsigned int)(v128 + 3 + v143) >> 3;
          *v145 = (unsigned int)(v132 + 3 + v155) >> 3;
          v9 = v133 + 3 + v156;
          v10 = v149;
          goto LABEL_14;
        case 4:
          --v144;
          v12 = *v136;
          v139 = *(_WORD *)(v111[12] + 4 * v12);
          v164 = *(_BYTE *)(v111[12] + 4 * v12 + 2);
          v13 = v136 + 1;
          if ( !v115 )
            v13 = v136;
          v136 = v13;
          v163 = HIBYTE(v139);
          v167 = v139;
          goto LABEL_20;
        case 5:
          v14 = v136;
          v15 = v136[1];
          v16 = v15 << 6;
          v164 = 2 * (v15 & 0xFC);
          v167 = *v136;
          v17 = v167;
          v167 *= 8;
          v18 = v16 | (v17 >> 2) & 0x38;
          --v144;
          v19 = v114 == 0;
          goto LABEL_22;
        case 6:
          v14 = v136;
          v21 = v136[1];
          v22 = 32 * v21;
          v164 = v21 & 0xF8;
          v167 = *v136;
          v23 = v167;
          v167 *= 8;
          v18 = v22 | (v23 >> 2) & 0x38;
          --v144;
          v19 = v113 == 0;
LABEL_22:
          v163 = v18;
          v20 = v14 + 2;
          if ( v19 )
            v20 = v14;
          v136 = v20;
          goto LABEL_2;
        case 7:
          v24 = v136;
          --v144;
          v25 = v112 == 0;
          v139 = *(_WORD *)v136;
          v164 = v136[2];
          v26 = v136 + 3;
          goto LABEL_27;
        case 8:
          v24 = v136;
          --v144;
          v25 = v123 == 0;
          v139 = *(_WORD *)v136;
          v164 = v136[2];
          v26 = v136 + 4;
LABEL_27:
          if ( v25 )
            v26 = v24;
          v136 = v26;
          v163 = HIBYTE(v139);
          v167 = v139;
          goto LABEL_2;
        case 9:
          v27 = (v167 + 2 * (v164 + 2 * v163) + 3 + ((v167 + 2 * (v164 + 2 * v163)) & 1u)) / 7;
          v166 = v27;
          v28 = v164 - v27;
          v3 = v162;
          v29 = (v167 - v27) / 2;
          LOBYTE(v29) = v29 + 0x80;
          v125 = v29;
          v2 = v126;
          v30 = v28 / 2;
          LOBYTE(v30) = v28 / 2 + 0x80;
          v124 = v30;
          result = (int)v168;
          goto LABEL_7;
        case 10:
          *v161 = v166;
          goto LABEL_33;
        case 11:
          v161[1] = v166;
          goto LABEL_33;
        case 12:
          v143 = (unsigned __int16)(4 * v166);
          v155 = (unsigned __int16)(4 * (unsigned __int8)v124);
          v156 = (unsigned __int16)(4 * (unsigned __int8)v125);
          goto LABEL_36;
        case 13:
          v32 = v134;
          *v134 = (v128 + 3 + (unsigned int)v166) >> 3;
          v134 = v32 + 1;
          LOWORD(v143) = 3 * v166 + v143;
          v33 = v149;
          *v149 = (v133 + 3 + (unsigned int)(unsigned __int8)v125) >> 3;
          v149 = v33 + 1;
          LOWORD(v156) = 3 * (unsigned __int8)v125 + v156;
          v34 = v145;
          *v145 = (v132 + 3 + (unsigned int)(unsigned __int8)v124) >> 3;
          v145 = v34 + 1;
          LOWORD(v155) = 3 * (unsigned __int8)v124 + v155;
          goto LABEL_2;
        case 14:
          v128 = (unsigned __int16)(v143 + 3 * v166);
          v143 = v166;
          v133 = (unsigned __int16)(v156 + 3 * (unsigned __int8)v125);
          v156 = (unsigned __int8)v125;
          v35 = (unsigned __int8)v124;
          goto LABEL_40;
        case 15:
          v165 ^= 1u;
          v161 += 16 * (v165 & 1) + 8;
          if ( !--v5 )
            goto LABEL_2;
          v31 = *(_DWORD *)(v157 + 4 * v2);
          v2 -= 49152;
          goto LABEL_37;
        case 16:
          v36 = v151 == 1;
          goto LABEL_44;
        case 17:
          result = v146;
          v37 = v147;
          v4 = v150;
          v160 = v158;
          v168 = (_BYTE *)v146;
          v154 = v147;
          v159 = v152;
          if ( v140 )
          {
            v37 = v158;
            v140 = 0;
            v154 = v158;
          }
          v121 = v37;
          if ( v151 == 1 )
            v4 = v152;
          v120 = v4;
          goto LABEL_51;
        case 18:
          result = (int)v131;
          v160 = &v158[v137];
          v168 = v131;
          v4 = &v120[v137];
          v154 = &v121[v137];
          v159 = &v152[v137];
          goto LABEL_51;
        case 19:
          result = (int)v119;
          v168 = v119;
          v154 = &v121[2 * v137];
          v160 = &v158[2 * v137];
          v159 = &v152[2 * v137];
          v4 = &v120[2 * v137];
LABEL_51:
          v5 = v148;
          v153 = v4;
          continue;
        case 20:
          v38 = *v154 + *v4 + 3 * (*v159 + 1 + *v160);
          result = (int)v168;
          ++v4;
          ++v159;
          ++v160;
          v39 = v154 + 1;
          *v168 = v38 >> 3;
          v153 = v4;
          v154 = v39;
LABEL_33:
          v3 = v162;
          continue;
        case 22:
          v19 = (result & 1) == 0;
          v40 = 1;
          if ( !v19 )
            v40 = 7;
          v168 += v40;
          goto LABEL_2;
        case 23:
          ++result;
          goto LABEL_59;
        case 24:
        case 35:
          v41 = --v5 == 0;
          goto LABEL_61;
        case 25:
          v42 = v127;
          v127 = result;
          result = v42;
          v146 = v42;
LABEL_59:
          v168 = (_BYTE *)result;
          continue;
        case 26:
          v131 = (_BYTE *)result;
          continue;
        case 27:
          v119 = (_BYTE *)result;
          continue;
        case 28:
          v41 = v151-- == 1;
LABEL_61:
          if ( !v41 )
            goto LABEL_36;
          continue;
        case 29:
          v151 = LOWORD(v111[6]) >> 2;
          v122 = v111[1] - v111[0];
          v142 = v111[8] + 4;
          v141 = v111[8] + 20;
          v131 = (_BYTE *)v111[0];
          v118 = v111[9] + 4;
          goto LABEL_6;
        case 30:
          v138 = v131;
          v135 = (unsigned __int8 *)v142;
          v149 = (_BYTE *)v3;
          v145 = (_BYTE *)(v137 + v3);
          v43 = v148;
          v3 += v148;
          v44 = v3 < v111[2] + v137;
          goto LABEL_69;
        case 31:
          *v145 = (unsigned int)(v132 + 3 + v155) >> 3;
          *v149 = (unsigned int)(v133 + 3 + v156) >> 3;
          v131 = v138;
          v142 = v141;
          v141 = (int)v135;
          v135 = (unsigned __int8 *)v142;
          goto LABEL_2;
        case 32:
          v45 = *v138;
          v46 = (v138++)[v122];
          v47 = v135;
          *v135 = v45;
          v156 = (unsigned __int16)(4 * v45);
          v155 = (unsigned __int16)(4 * v46);
          v48 = v157;
          v47[1] = v46;
          v135 = v47 + 8;
          v2 += *(_DWORD *)(v48 + 4 * v2) - 49152;
          goto LABEL_20;
        case 33:
          v49 = v135;
          v50 = *v138;
          *v135 = *v138;
          v123 = v50;
          v51 = v149++;
          *v51 = ((unsigned int)v50 + v133 + 3) >> 3;
          v156 += 3 * v123;
          v52 = v138[v122];
          v49[1] = v52;
          v123 = v52;
          v53 = v145++;
          *v53 = ((unsigned int)v52 + v132 + 3) >> 3;
          v155 += 3 * v123;
          ++v138;
          v135 = v49 + 8;
          goto LABEL_20;
        case 34:
          v54 = v138;
          v55 = v135;
          v56 = *v138;
          *v135 = *v138;
          v57 = v56;
          v133 = (unsigned __int16)(v156 + 3 * v56);
          v58 = v54[v122];
          v55[1] = v58;
          ++v138;
          v132 = (unsigned __int16)(v155 + 3 * v58);
          v156 = v57;
          v135 = v55 + 24;
          v155 = v58;
          goto LABEL_76;
        case 36:
          v59 = (_BYTE *)v118;
          v60 = v147;
          v4 = v150;
          v160 = v158;
          v168 = (_BYTE *)v118;
          v154 = v147;
          v159 = v152;
          if ( v140 )
          {
            v60 = v158;
            v140 = 0;
            v154 = v158;
          }
          v121 = v60;
          if ( v151 == 1 )
            v4 = v152;
          v61 = v148 >> 1;
          v153 = v4;
          v120 = v4;
          if ( v148 >> 1 )
          {
            v62 = v154;
            v63 = v160;
            v64 = v159;
            do
            {
              v65 = *v4 + 3 * (*v64 + 1 + *v63);
              v66 = *v62;
              v67 = v160;
              v68 = v66 + v65;
              v69 = v137;
              *v59 = v68 >> 3;
              v70 = v159[v69];
              v71 = v67[v69];
              v72 = v154;
              v73 = v154[v137] + v4[v137] + 3 * (v70 + 1 + v71);
              v74 = v160;
              v59[1] = v73 >> 3;
              v59 += 8;
              v62 = v72 + 1;
              v63 = v74 + 1;
              v154 = v62;
              v64 = v159 + 1;
              v160 = v63;
              ++v4;
              ++v159;
              --v61;
            }
            while ( v61 );
            v3 = v162;
            v2 = v126;
            v153 = v4;
            v168 = v59;
          }
          v75 = v152;
          v5 = v61 - 1;
          v118 = (int)v59;
          v152 = v147;
          v147 = v75;
          v76 = v150;
          v150 = v158;
          v158 = v76;
          goto LABEL_2;
        case 37:
          return result;
        case 38:
          v142 = v111[8];
          v151 = LOWORD(v111[6]) >> 1;
          v141 = v111[8] + 2;
          v130 = v111[8] + 16;
          v8 = v111[8] + 18;
LABEL_5:
          v129 = (unsigned __int8 *)v8;
          v146 = v111[9];
          v127 = v111[9] + 2;
          goto LABEL_6;
        case 39:
          v5 = v148;
          v134 = (_BYTE *)v3;
          v3 += v148;
          v165 = 1;
          v11 = (unsigned __int8 *)v142;
          if ( v3 >= v111[2] + 4 * v148 )
            v3 = v111[2];
          v162 = v3;
          goto LABEL_16;
        case 40:
          v9 = v128 + 3 + v143;
          v10 = v134;
LABEL_14:
          *v10 = v9 >> 3;
          v11 = (unsigned __int8 *)v141;
          v141 = v130;
          v130 = (int)v129;
          v129 = v161;
          goto LABEL_15;
        case 41:
          v143 = (unsigned __int16)(4 * *v161);
          goto LABEL_36;
        case 42:
          v77 = v134;
          v78 = (v128 + 3 + (unsigned int)*v161) >> 3;
          ++v134;
          *v77 = v78;
          LOWORD(v143) = 3 * *v161 + v143;
          goto LABEL_2;
        case 43:
          v79 = v161[1];
          v128 = (unsigned __int16)(v143 + 3 * v79);
          v143 = v79;
          goto LABEL_20;
        case 44:
          v80 = v146;
          v81 = v147;
          v4 = v150;
          v160 = v158;
          v154 = v147;
          v159 = v152;
          if ( v140 )
          {
            v81 = v158;
            v140 = 0;
            v154 = v158;
          }
          if ( v151 == 1 )
            v4 = v152;
          v82 = v148;
          v153 = v4;
          if ( v148 )
          {
            v83 = (_BYTE *)v146;
            do
            {
              v84 = (*v81++ + *v4++ + 3 * (*v159++ + 1 + (unsigned int)*v160++)) >> 3;
              v85 = 1;
              *v83 = v84;
              if ( ((unsigned __int8)v83 & 1) != 0 )
                v85 = 7;
              v83 += v85;
              --v82;
            }
            while ( v82 );
            v3 = v162;
            v146 = (int)v83;
            v2 = v126;
            v80 = v146;
            v154 = v81;
            v153 = v4;
          }
          v5 = v82 - 1;
          v36 = v151-- == 1;
          v146 = v127;
          v127 = v80;
          v86 = v147;
          v168 = (_BYTE *)v146;
          v147 = v152;
          v152 = v86;
          v87 = v158;
          v158 = v150;
          v150 = v87;
          goto LABEL_105;
        case 45:
          v151 = LOWORD(v111[6]) >> 1;
          v142 = v111[8] + 4;
          v141 = v111[8] + 20;
          v146 = v111[9] + 4;
LABEL_6:
          v3 = v111[2];
          v162 = v111[2];
          v158 = (unsigned __int8 *)v111[2];
          v140 = 1;
          v152 = (unsigned __int8 *)(v148 + v111[2]);
          v150 = (unsigned __int8 *)(v148 + v148 + v111[2]);
          v147 = &v150[v148];
LABEL_7:
          v4 = v153;
          continue;
        case 46:
          v149 = (_BYTE *)v3;
          v165 = 1;
          v145 = (_BYTE *)(v137 + v3);
          v43 = v148;
          v3 += v148;
          v44 = v3 < v111[2] + v137;
          v161 = (unsigned __int8 *)v142;
LABEL_69:
          if ( !v44 )
            v3 = v111[2];
          v162 = v3;
          v5 = v43 >> 1;
          goto LABEL_2;
        case 47:
          *v149 = (unsigned int)(v133 + 3 + v156) >> 3;
          *v145 = (unsigned int)(v132 + 3 + v155) >> 3;
          v11 = (unsigned __int8 *)v141;
          v141 = (int)v161;
LABEL_15:
          v142 = (int)v11;
LABEL_16:
          v161 = v11;
          goto LABEL_2;
        case 48:
          v156 = (unsigned __int16)(4 * *v161);
          v155 = (unsigned __int16)(4 * v161[1]);
          goto LABEL_36;
        case 49:
          v88 = v161;
          v89 = v149;
          v90 = (v133 + 3 + (unsigned int)*v161) >> 3;
          ++v149;
          *v89 = v90;
          LOWORD(v156) = 3 * *v88 + v156;
          v91 = v145;
          *v145 = (v132 + 3 + (unsigned int)v88[1]) >> 3;
          LOWORD(v90) = v88[1];
          v145 = v91 + 1;
          LOWORD(v155) = 3 * v90 + v155;
          v165 ^= 1u;
          v161 = &v88[16 * (v165 & 1) + 8];
          goto LABEL_20;
        case 50:
          v92 = *v161;
          v133 = (unsigned __int16)(v156 + 3 * v92);
          v93 = v92;
          v35 = v161[1];
          v156 = v93;
LABEL_40:
          v132 = (unsigned __int16)(v155 + 3 * v35);
          v155 = v35;
LABEL_20:
          v3 = v162;
          goto LABEL_2;
        case 51:
          v94 = (_BYTE *)v146;
          v4 = v150;
          v154 = v147;
          v168 = (_BYTE *)v146;
          v160 = v158;
          v159 = v152;
          if ( v140 )
          {
            v140 = 0;
            v154 = v158;
          }
          if ( v151 == 1 )
            v4 = v152;
          v95 = v148 >> 1;
          v153 = v4;
          if ( v148 >> 1 )
          {
            v96 = v154;
            v97 = v160;
            v98 = v159;
            do
            {
              v99 = 3 * (*v98 + 1 + *v97);
              v100 = *v4;
              v101 = v160;
              v102 = *v96 + v100 + v99;
              v103 = v137;
              *v94 = v102 >> 3;
              v104 = v159[v103];
              v105 = v101[v103];
              v106 = v153;
              v107 = v153[v137] + v96[v137] + 3 * (v104 + 1 + v105);
              v108 = v160;
              v94[1] = v107 >> 3;
              v94 += 8;
              ++v96;
              v97 = v108 + 1;
              v98 = v159 + 1;
              v4 = v106 + 1;
              v160 = v97;
              ++v159;
              v153 = v4;
              --v95;
            }
            while ( v95 );
            v3 = v162;
            v154 = v96;
            v2 = v126;
            v168 = v94;
          }
          v109 = v147;
          v5 = v95 - 1;
          v146 = (int)v94;
          v147 = v152;
          v152 = v109;
          v110 = v158;
          v158 = v150;
          v150 = v110;
          v36 = v151-- == 0;
LABEL_105:
          result = (int)v168;
LABEL_44:
          if ( !v36 )
            continue;
LABEL_36:
          v31 = *(_DWORD *)(v157 + 4 * v2) - 49152;
LABEL_37:
          v2 += v31;
          break;
        default:
          if ( (*(_DWORD *)(v157 + 4 * v2 - 4) & 0x8000) != 0 )
            continue;
          DebugBreak();
LABEL_76:
          v3 = v162;
          v2 = v126;
          break;
      }
      break;
    }
  }
}

```

## disassembly

```asm
0x100055fd  mov     edi, edi
0x100055ff  push    ebp
0x10005600  mov     ebp, esp
0x10005602  sub     esp, 80Ch
0x10005608  push    ebx
0x10005609  push    esi
0x1000560a  push    edi
0x1000560b  mov     esi, ecx
0x1000560d  mov     [ebp+var_24], edx
0x10005610  xor     edx, edx
0x10005612  mov     [ebp+var_68], 1
0x10005619  mov     ecx, 1CDh
0x1000561e  mov     [ebp+var_7], dl
0x10005621  lea     edi, [ebp+var_80C]
0x10005627  mov     [ebp+var_60], edx
0x1000562a  rep movsd
0x1000562c  mov     esi, [ebp+var_7FC]
0x10005632  mov     eax, edx
0x10005634  shr     esi, 10h
0x10005637  mov     ecx, edx
0x10005639  mov     [ebp+var_4], eax
0x1000563c  mov     edi, edx
0x1000563e  mov     [ebp+var_6], al
0x10005641  mov     ebx, edx
0x10005643  mov     byte ptr [ebp+var_A4], al
0x10005649  mov     byte ptr [ebp+var_A8], al
0x1000564f  mov     eax, [ebp+var_7E0]
0x10005655  mov     [ebp+var_48], esi
0x10005658  shl     esi, 2
0x1000565b  mov     [ebp+var_C4], eax
0x10005661  mov     eax, [ebp+var_7F0]
0x10005667  mov     [ebp+var_64], edx
0x1000566a  mov     [ebp+var_90], edx
0x10005670  mov     [ebp+var_94], edx
0x10005676  mov     [ebp+var_50], edx
0x10005679  mov     [ebp+var_9C], edx
0x1000567f  mov     [ebp+var_C0], edx
0x10005685  mov     [ebp+var_8C], edx
0x1000568b  mov     [ebp+var_BC], edx
0x10005691  mov     [ebp+var_10], ecx
0x10005694  mov     [ebp+var_4C], edx
0x10005697  mov     [ebp+var_B4], edx
0x1000569d  mov     [ebp+var_20], edx
0x100056a0  mov     [ebp+var_38], edx
0x100056a3  mov     [ebp+var_40], edx
0x100056a6  mov     [ebp+var_B8], edx
0x100056ac  mov     [ebp+var_58], edx
0x100056af  mov     [ebp+var_3C], edx
0x100056b2  mov     [ebp+var_5], dl
0x100056b5  mov     [ebp+var_9], dl
0x100056b8  mov     [ebp+var_8], dl
0x100056bb  mov     [ebp+var_78], edx
0x100056be  mov     [ebp+var_70], edx
0x100056c1  mov     [ebp+var_7C], edx
0x100056c4  mov     [ebp+var_14], edx
0x100056c7  mov     [ebp+var_80], edx
0x100056ca  mov     [ebp+var_44], edx
0x100056cd  mov     [ebp+var_54], edx
0x100056d0  mov     [ebp+var_30], edx
0x100056d3  mov     [ebp+var_18], edx
0x100056d6  mov     [ebp+var_1C], edx
0x100056d9  mov     [ebp+var_34], edi
0x100056dc  mov     [ebp+var_5C], edx
0x100056df  mov     [ebp+var_98], edx
0x100056e5  mov     [ebp+var_28], edx
0x100056e8  mov     [ebp+var_84], edx
0x100056ee  mov     [ebp+var_2C], edx
0x100056f1  mov     [ebp+var_88], edx
0x100056f7  mov     [ebp+var_B0], edx
0x100056fd  mov     [ebp+var_74], esi
0x10005700  mov     [ebp+var_C8], eax
0x10005706  mov     eax, [ebp+var_4]
0x10005709  mov     esi, [ebp+var_58]; jumptable 10005740 case 0
0x1000570c  mov     [ebp+var_AC], esi
0x10005712  mov     [ebp+var_D8], esi
0x10005718  mov     [ebp+var_D4], esi
0x1000571e  mov     [ebp+var_D0], esi
0x10005724  mov     [ebp+var_CC], esi
0x1000572a  mov     esi, [ebp+var_24]
0x1000572d  mov     esi, [esi+edx*4]
0x10005730  inc     edx
0x10005731  mov     [ebp+var_A0], edx
0x10005737  cmp     esi, 33h; switch 52 cases
0x1000573a  ja      def_10005740; jumptable 10005740 default case, case 21
0x10005740  jmp     ds:jpt_10005740[esi*4]; switch jump
0x10005747  mov     esi, [ebp+var_7EC]; jumptable 10005740 case 1
0x1000574d  movzx   ecx, [ebp+var_7F4]
0x10005754  shr     ecx, 1
0x10005756  mov     [ebp+var_60], esi
0x10005759  add     esi, 2
0x1000575c  mov     [ebp+var_3C], ecx
0x1000575f  mov     ecx, [ebp+var_80C]
0x10005765  mov     [ebp+var_64], esi
0x10005768  add     esi, 0Eh
0x1000576b  mov     [ebp+var_8C], ecx
0x10005771  mov     ecx, [ebp+var_808]
0x10005777  mov     [ebp+var_90], esi
0x1000577d  add     esi, 2
0x10005780  mov     [ebp+var_BC], ecx
0x10005786  mov     [ebp+var_94], esi
0x1000578c  mov     esi, [ebp+var_7E8]
0x10005792  mov     [ebp+var_50], esi
0x10005795  add     esi, 2
0x10005798  mov     [ebp+var_9C], esi
0x1000579e  mov     ecx, [ebp+var_804]
0x100057a4  mov     esi, [ebp+var_48]
0x100057a7  mov     [ebp+var_10], ecx
0x100057aa  mov     [ebp+var_20], ecx
0x100057ad  mov     [ebp+var_68], 1
0x100057b4  lea     edi, [esi+ecx]
0x100057b7  mov     [ebp+var_38], edi
0x100057ba  add     edi, esi
0x100057bc  add     esi, edi
0x100057be  mov     [ebp+var_40], edi
0x100057c1  mov     [ebp+var_4C], esi
0x100057c4  mov     edi, [ebp+var_34]
0x100057c7  jmp     loc_10005709; jumptable 10005740 case 0
0x100057cc  mov     ebx, [ebp+var_C4]; jumptable 10005740 case 2
0x100057d2  mov     eax, [ebp+var_C8]
0x100057d8  mov     [ebp+var_78], eax
0x100057db  test    ebx, ebx
0x100057dd  jz      short loc_100057F2
0x100057df  dec     ebx
0x100057e0  add     eax, [ebp+var_800]
0x100057e6  mov     [ebp+var_C4], ebx
0x100057ec  mov     [ebp+var_C8], eax
0x100057f2  mov     eax, [ebp+var_74]
0x100057f5  mov     [ebp+var_80], ecx
0x100057f8  mov     [ebp+var_7], 1
0x100057fc  lea     ebx, [eax+ecx]
0x100057ff  mov     [ebp+var_44], ebx
0x10005802  add     ebx, eax
0x10005804  add     eax, [ebp+var_804]
0x1000580a  mov     [ebp+var_54], ebx
0x1000580d  mov     ebx, [ebp+var_48]
0x10005810  add     ecx, ebx
0x10005812  cmp     ecx, eax
0x10005814  mov     eax, [ebp+var_60]
0x10005817  mov     [ebp+var_14], eax
0x1000581a  mov     eax, [ebp+var_800]
0x10005820  cmovnb  ecx, [ebp+var_804]
0x10005827  dec     eax
0x10005828  mov     [ebp+var_10], ecx
0x1000582b  mov     [ebp+var_58], eax
0x1000582e  jmp     loc_10005706
0x10005833  mov     esi, [ebp+var_98]; jumptable 10005740 case 3
0x10005839  mov     eax, [ebp+var_5C]
0x1000583c  add     esi, 3
0x1000583f  add     eax, esi
0x10005841  mov     esi, [ebp+var_80]
0x10005844  shr     eax, 3
0x10005847  mov     [esi], al
0x10005849  mov     esi, [ebp+var_88]
0x1000584f  mov     eax, [ebp+var_2C]
0x10005852  add     esi, 3
0x10005855  add     eax, esi
0x10005857  mov     esi, [ebp+var_54]
0x1000585a  shr     eax, 3
0x1000585d  mov     [esi], al
0x1000585f  mov     esi, [ebp+var_84]
0x10005865  mov     eax, [ebp+var_28]
0x10005868  add     esi, 3
0x1000586b  add     eax, esi
0x1000586d  mov     esi, [ebp+var_44]
0x10005870  shr     eax, 3
0x10005873  mov     [esi], al
0x10005875  mov     esi, [ebp+var_90]
0x1000587b  mov     eax, [ebp+var_64]
0x1000587e  mov     [ebp+var_64], esi
0x10005881  mov     esi, [ebp+var_94]
0x10005887  mov     [ebp+var_90], esi
0x1000588d  mov     esi, [ebp+var_14]
0x10005890  mov     [ebp+var_94], esi
0x10005896  mov     [ebp+var_60], eax
0x10005899  mov     [ebp+var_14], eax
0x1000589c  jmp     loc_10005706
0x100058a1  mov     esi, [ebp+var_78]; jumptable 10005740 case 4
0x100058a4  mov     eax, [ebp+var_7DC]
0x100058aa  dec     [ebp+var_58]
0x100058ad  cmp     [ebp+var_CC], 0
0x100058b4  movzx   ecx, byte ptr [esi]
0x100058b7  mov     ax, [eax+ecx*4]
0x100058bb  mov     [ebp+var_6C], ax
0x100058bf  mov     eax, [ebp+var_7DC]
0x100058c5  mov     al, [eax+ecx*4+2]
0x100058c9  mov     [ebp+var_8], al
0x100058cc  lea     eax, [esi+1]
0x100058cf  cmovz   eax, esi
0x100058d2  mov     [ebp+var_78], eax
0x100058d5  mov     al, byte ptr [ebp+var_6C+1]
0x100058d8  mov     [ebp+var_9], al
0x100058db  mov     al, byte ptr [ebp+var_6C]
0x100058de  mov     [ebp+var_5], al
0x100058e1  mov     ecx, [ebp+var_10]
0x100058e4  jmp     loc_10005706
0x100058e9  mov     esi, [ebp+var_78]; jumptable 10005740 case 5
0x100058ec  mov     al, [esi+1]
0x100058ef  mov     ah, al
0x100058f1  shl     al, 6
0x100058f4  and     ah, 0FCh
0x100058f7  add     ah, ah
0x100058f9  mov     [ebp+var_8], ah
0x100058fc  mov     ah, [esi]
0x100058fe  mov     [ebp+var_5], ah
0x10005901  shl     [ebp+var_5], 3
0x10005905  shr     ah, 2
0x10005908  and     ah, 38h
0x1000590b  or      ah, al
0x1000590d  dec     [ebp+var_58]
0x10005910  cmp     [ebp+var_D0], 0
0x10005917  mov     [ebp+var_9], ah
0x1000591a  lea     eax, [esi+2]
0x1000591d  cmovz   eax, esi
0x10005920  mov     [ebp+var_78], eax
0x10005923  jmp     loc_10005706
0x10005928  mov     esi, [ebp+var_78]; jumptable 10005740 case 6
0x1000592b  mov     al, [esi+1]
0x1000592e  mov     ah, al
0x10005930  shl     al, 5
0x10005933  and     ah, 0F8h
0x10005936  mov     [ebp+var_8], ah
0x10005939  mov     ah, [esi]
0x1000593b  mov     [ebp+var_5], ah
0x1000593e  shl     [ebp+var_5], 3
0x10005942  shr     ah, 2
0x10005945  and     ah, 38h
0x10005948  or      ah, al
0x1000594a  dec     [ebp+var_58]
0x1000594d  cmp     [ebp+var_D4], 0
0x10005954  jmp     short loc_10005917
0x10005956  mov     esi, [ebp+var_78]; jumptable 10005740 case 7
0x10005959  dec     [ebp+var_58]
0x1000595c  cmp     [ebp+var_D8], 0
0x10005963  mov     ax, [esi]
0x10005966  mov     [ebp+var_6C], ax
0x1000596a  mov     al, [esi+2]
0x1000596d  mov     [ebp+var_8], al
0x10005970  lea     eax, [esi+3]
0x10005973  cmovz   eax, esi
0x10005976  mov     [ebp+var_78], eax
0x10005979  mov     al, byte ptr [ebp+var_6C+1]
0x1000597c  mov     [ebp+var_9], al
0x1000597f  mov     al, byte ptr [ebp+var_6C]
0x10005982  mov     [ebp+var_5], al
0x10005985  jmp     loc_10005706
0x1000598a  mov     esi, [ebp+var_78]; jumptable 10005740 case 8
0x1000598d  dec     [ebp+var_58]
0x10005990  cmp     [ebp+var_AC], 0
0x10005997  mov     ax, [esi]
0x1000599a  mov     [ebp+var_6C], ax
0x1000599e  mov     al, [esi+2]
0x100059a1  mov     [ebp+var_8], al
0x100059a4  lea     eax, [esi+4]
0x100059a7  jmp     short loc_10005973
0x100059a9  movzx   edi, [ebp+var_8]; jumptable 10005740 case 9
0x100059ad  xor     edx, edx
0x100059af  movzx   eax, [ebp+var_9]
0x100059b3  movzx   esi, [ebp+var_5]
0x100059b7  push    7
0x100059b9  lea     eax, [edi+eax*2]
0x100059bc  lea     ecx, [esi+eax*2]
0x100059bf  mov     eax, ecx
0x100059c1  add     ecx, 3
0x100059c4  and     eax, 1
0x100059c7  add     eax, ecx
0x100059c9  pop     ecx
0x100059ca  div     ecx
0x100059cc  movzx   ecx, al
0x100059cf  mov     [ebp+var_6], al
0x100059d2  sub     esi, ecx
0x100059d4  mov     eax, esi
0x100059d6  sub     edi, ecx
0x100059d8  mov     ecx, [ebp+var_10]
0x100059db  cdq
0x100059dc  sub     eax, edx
0x100059de  sar     eax, 1
0x100059e0  add     al, 80h
0x100059e2  mov     [ebp+var_A4], eax
0x100059e8  mov     eax, edi
0x100059ea  cdq
0x100059eb  sub     eax, edx
0x100059ed  mov     edx, [ebp+var_A0]
0x100059f3  sar     eax, 1
0x100059f5  add     al, 80h
0x100059f7  mov     [ebp+var_A8], eax
0x100059fd  mov     eax, [ebp+var_4]
0x10005a00  jmp     loc_100057C4
0x10005a05  mov     esi, [ebp+var_14]; jumptable 10005740 case 10
0x10005a08  mov     cl, [ebp+var_6]
0x10005a0b  mov     [esi], cl
0x10005a0d  mov     ecx, [ebp+var_10]
0x10005a10  jmp     loc_10005709; jumptable 10005740 case 0
0x10005a15  mov     esi, [ebp+var_14]; jumptable 10005740 case 11
0x10005a18  mov     cl, [ebp+var_6]
0x10005a1b  mov     [esi+1], cl
0x10005a1e  jmp     short loc_10005A0D
0x10005a20  movzx   eax, [ebp+var_6]; jumptable 10005740 case 12
0x10005a24  shl     ax, 2
0x10005a28  movzx   eax, ax
0x10005a2b  mov     [ebp+var_5C], eax
  ... truncated ...
```
