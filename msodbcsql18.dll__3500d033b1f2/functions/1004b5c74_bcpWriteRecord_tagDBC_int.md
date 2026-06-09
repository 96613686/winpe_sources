# bcpWriteRecord(tagDBC *,int *)

- ea: `0x1004b5c74`
- end: `0x1004b8295`
- name: `?bcpWriteRecord@@YAFPEAUtagDBC@@PEAH@Z`
- size: `9761`
- prototype: `__int16 __fastcall(struct tagDBC *, int *)`
- caller_count: `1`
- callee_count: `39`
- tags: ``

## callers

- `0x1004affe4`

## callees

- `0x100493378`
- `0x100498bb0`
- `0x1004a12e4`
- `0x1004a16b0`
- `0x1004a1984`
- `0x1004a1cd0`
- `0x1004a28f0`
- `0x1004a3090`
- `0x1004a3bf0`
- `0x1004a4400`
- `0x1004a5010`
- `0x1004a5710`
- `0x1004a5e20`
- `0x1004a7050`
- `0x1004a7aa0`
- `0x1004ac014`
- `0x1004ad33c`
- `0x1004aeae4`
- `0x1004b5b5c`
- `0x1004b5c74`
- `0x1004b829c`
- `0x1004c3974`
- `0x1004e2e7c`
- `0x1004f87c4`
- `0x1004f8958`
- `0x1004fa384`
- `0x10051fc98`
- `0x10051ff30`
- `0x100520028`
- `0x100520370`
- `0x10052120c`
- `0x1005212b4`
- `0x100522824`
- `0x100525dbc`
- `0x100538c74`
- `0x100546a24`
- `0x100546a7c`
- `0x100548210`
- `0x1005495d0`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x1004b6544`
- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x1004b6563`
- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x1004b6544`
- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x1004b6563`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall bcpWriteRecord(struct tagDBC *a1, int *a2)
{
  int *v2; // r15
  __int64 v4; // rsi
  unsigned __int16 v5; // di
  unsigned int *v6; // rcx
  unsigned __int16 BatchCtxOrRecover; // bx
  __int64 v8; // rcx
  unsigned __int64 v9; // r8
  unsigned __int64 v10; // rax
  __int64 v11; // rcx
  __int64 v12; // rdx
  unsigned int v13; // r11d
  struct tagBCPFLD *v14; // rdi
  __int64 v15; // rax
  unsigned __int16 v16; // r11
  __int64 v17; // rdx
  __int64 v18; // rcx
  char v19; // r10
  char v20; // r8
  char v21; // r12
  __int64 v22; // r15
  _OWORD *v23; // rcx
  _OWORD *v24; // rax
  __int64 v25; // rdx
  __int64 v26; // r8
  struct tagBCPFLD *v27; // rsi
  __int64 v28; // rdx
  __int64 v29; // rdx
  struct tagBCPFLD *v30; // rax
  struct tagBCPFLD *v31; // rcx
  __int64 v32; // rdx
  BATCHCTX **v33; // r14
  struct tagCOLUMN_INFO *ColInfoByOrdinal; // rax
  __int64 v35; // rdi
  __int16 ColData; // ax
  unsigned int v37; // ecx
  unsigned int VariantBaseTypeInfo; // eax
  unsigned int v39; // eax
  unsigned int v40; // ecx
  int v41; // edx
  int v42; // ecx
  BOOL v43; // edx
  int v44; // edx
  int v45; // eax
  BOOL v46; // eax
  unsigned int v47; // r9d
  struct tagDBC *v48; // rcx
  struct tagBCPFLD *v49; // rdi
  unsigned __int8 v50; // r8
  unsigned int v51; // r12d
  int v52; // ecx
  __int64 v53; // r9
  int v54; // eax
  unsigned int v55; // ebx
  unsigned int v56; // edi
  unsigned __int8 *v57; // rax
  const unsigned __int8 *v58; // r14
  struct tagBCPFLD *v59; // r12
  unsigned __int16 v60; // di
  unsigned int v61; // r9d
  __int16 v62; // ax
  _BYTE *v63; // r15
  _BYTE *v64; // rdx
  __int16 v65; // bx
  int v66; // eax
  rsize_t v67; // r14
  BATCHCTX **v68; // rsi
  struct tagCOLUMN_INFO *v69; // rdi
  __int16 v70; // ax
  BOOL v71; // edx
  unsigned __int16 v72; // ax
  __int64 v73; // rcx
  unsigned int v74; // ecx
  unsigned int v75; // eax
  unsigned int v76; // eax
  unsigned int v77; // ecx
  int v78; // edx
  int v79; // ecx
  int v80; // r8d
  int v81; // eax
  BOOL v82; // eax
  unsigned int v83; // r9d
  struct tagDBC *v84; // rcx
  unsigned __int16 v85; // bx
  __int64 v86; // rdx
  int v87; // esi
  __int64 v88; // rdx
  __int64 v89; // r8
  rsize_t v90; // r15
  __int64 v91; // r8
  unsigned __int8 *v92; // r9
  unsigned __int64 v93; // rax
  __int64 v94; // rdx
  int v95; // r8d
  int v96; // r8d
  int v97; // r8d
  __int64 v98; // rax
  __int64 v99; // rdi
  struct tagBCPFLD *v100; // rax
  __int64 v101; // r8
  unsigned __int8 *v102; // rax
  const unsigned __int8 *v103; // r9
  struct BCPFILE *v104; // rsi
  __int64 v105; // r15
  __int64 v106; // r9
  __int16 v107; // ax
  __int16 v108; // bx
  BATCHCTX **v109; // rsi
  struct tagCOLUMN_INFO *v110; // rdi
  __int16 v111; // ax
  BOOL v112; // edx
  unsigned __int16 v113; // ax
  __int64 v114; // rcx
  unsigned int v115; // ecx
  unsigned int v116; // eax
  unsigned int v117; // eax
  unsigned int v118; // ecx
  int v119; // edx
  int v120; // ecx
  int v121; // r8d
  int v122; // eax
  BOOL v123; // eax
  unsigned int v124; // r9d
  struct tagDBC *v125; // rcx
  __int64 v126; // r15
  int v127; // edi
  __int64 v128; // rsi
  struct tagBCPFLD *v129; // r15
  unsigned int v130; // edi
  __int64 v131; // r8
  __int16 v132; // dx
  int v133; // eax
  const unsigned __int8 *v134; // r14
  unsigned __int64 v135; // rdi
  unsigned __int64 v136; // rsi
  struct BCPFILE *v137; // r15
  int v138; // edi
  __int16 v139; // ax
  char v140; // al
  __int64 v142; // [rsp+38h] [rbp-D0h]
  __int64 v143; // [rsp+40h] [rbp-C8h]
  unsigned __int16 v144; // [rsp+68h] [rbp-A0h]
  int v145; // [rsp+6Ch] [rbp-9Ch]
  char v146; // [rsp+70h] [rbp-98h]
  __int64 v147; // [rsp+78h] [rbp-90h] BYREF
  __int64 v148; // [rsp+80h] [rbp-88h] BYREF
  char v149; // [rsp+88h] [rbp-80h]
  int *v150; // [rsp+90h] [rbp-78h]
  unsigned __int8 v151[8]; // [rsp+98h] [rbp-70h] BYREF
  __int16 v152; // [rsp+A0h] [rbp-68h]
  struct tagBCPFLD *v153; // [rsp+A8h] [rbp-60h]
  struct BCPFILE *v154; // [rsp+B0h] [rbp-58h]
  rsize_t v155; // [rsp+B8h] [rbp-50h]
  __int64 v156; // [rsp+C0h] [rbp-48h]
  __int64 v157; // [rsp+C8h] [rbp-40h]
  unsigned __int16 v158[2]; // [rsp+D0h] [rbp-38h] BYREF
  unsigned int v159; // [rsp+D4h] [rbp-34h]
  __int64 v160; // [rsp+D8h] [rbp-30h]
  unsigned __int8 v161[8]; // [rsp+E0h] [rbp-28h] BYREF
  __int64 v162; // [rsp+E8h] [rbp-20h]
  unsigned int v163[2]; // [rsp+F0h] [rbp-18h] BYREF
  int v164; // [rsp+F8h] [rbp-10h]
  __int64 v165; // [rsp+100h] [rbp-8h]
  unsigned int Source; // [rsp+108h] [rbp+0h] BYREF
  int v167; // [rsp+10Ch] [rbp+4h]
  unsigned __int64 v168; // [rsp+110h] [rbp+8h]
  __int64 v169; // [rsp+118h] [rbp+10h]
  unsigned __int8 v170[4]; // [rsp+120h] [rbp+18h] BYREF
  int v171; // [rsp+124h] [rbp+1Ch] BYREF
  unsigned __int8 v172[8]; // [rsp+128h] [rbp+20h] BYREF
  __int64 v173; // [rsp+130h] [rbp+28h]
  __int64 v174; // [rsp+138h] [rbp+30h]
  __int64 v175; // [rsp+140h] [rbp+38h]
  unsigned __int8 *v176; // [rsp+148h] [rbp+40h]
  __int64 v177; // [rsp+150h] [rbp+48h]
  __int64 v178; // [rsp+158h] [rbp+50h]
  __int64 v179; // [rsp+160h] [rbp+58h]
  __int128 v180; // [rsp+168h] [rbp+60h] BYREF
  __int64 v181; // [rsp+178h] [rbp+70h]
  unsigned __int64 v182; // [rsp+180h] [rbp+78h] BYREF
  _BYTE v183[192]; // [rsp+188h] [rbp+80h] BYREF
  __int64 v184; // [rsp+248h] [rbp+140h] BYREF
  char v185; // [rsp+250h] [rbp+148h]
  char v186[1024]; // [rsp+258h] [rbp+150h] BYREF

  v181 = -2;
  v2 = a2;
  v150 = a2;
  v4 = *((_QWORD *)a1 + 15);
  v162 = v4;
  v167 = *((_DWORD *)a1 + 608);
  v5 = *(_WORD *)(*((_QWORD *)a1 + 12) + 268LL);
  v180 = 0;
  v154 = (struct BCPFILE *)(v4 + 1680);
  v179 = *(_QWORD *)(v4 + 1728);
  *a2 = 0;
  v6 = (unsigned int *)*((_QWORD *)a1 + 12);
  v174 = 1;
  BatchCtxOrRecover = GetBatchCtxOrRecover((struct tagSTMT *)v6, (struct CAutoBatchCtx_ODBC *)&v180, 0, v6[377], 0, 1u);
  v8 = *((_QWORD *)a1 + 12);
  v173 = *(_QWORD *)(v8 + 1128);
  if ( (BatchCtxOrRecover & 0xFFFE) != 0 )
  {
    if ( (bidGblFlags & 2) != 0 )
      bidTraceMark(0, 7371785);
    goto LABEL_479;
  }
  if ( *(_WORD *)(v8 + 290) )
  {
    v9 = *(unsigned __int16 *)(v8 + 290);
    v10 = 1;
    v11 = *(_QWORD *)(v8 + 200);
    if ( v11 )
    {
      while ( 1 )
      {
        if ( v10 >= v9 )
          goto LABEL_10;
        if ( !*(_QWORD *)(v11 + 24) )
          break;
        v11 = *(_QWORD *)(v11 + 24);
        ++v10;
      }
      if ( v11 )
      {
LABEL_10:
        if ( *(unsigned __int16 *)(v11 + 38) == v9 )
        {
          v5 = *(_WORD *)(v11 + 32);
          goto LABEL_12;
        }
      }
    }
    BatchCtxOrRecover = -1;
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_481;
    v12 = 7379977;
    goto LABEL_17;
  }
LABEL_12:
  if ( *(_DWORD *)(v4 + 20) > (unsigned int)v5 )
  {
    BatchCtxOrRecover = -1;
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_481;
    v12 = 7389193;
LABEL_17:
    bidTraceMark(0, v12);
    goto LABEL_481;
  }
  v13 = 0;
  v145 = 0;
  v175 = 4;
  if ( !*(_DWORD *)(v4 + 20) )
  {
LABEL_433:
    if ( v13 != *(unsigned __int16 *)(v4 + 24) )
      goto LABEL_479;
    goto LABEL_434;
  }
  while ( 1 )
  {
    v14 = (struct tagBCPFLD *)(*(_QWORD *)v4 + 448LL * v13);
    v153 = v14;
    v15 = *((unsigned __int16 *)v14 + 24);
    v152 = v15;
    v16 = v13 + 1;
    v144 = v16;
    LODWORD(v156) = 0;
    if ( (_WORD)v15 )
      break;
LABEL_432:
    v13 = v145 + 1;
    v145 = v13;
    if ( v13 >= *(_DWORD *)(v4 + 20) )
      goto LABEL_433;
  }
  v17 = 616 * v15 - 616 + *(_QWORD *)(v4 + 8);
  v157 = v17;
  v178 = *(_QWORD *)(v4 + 1728);
  v164 = 0;
  v168 = 0;
  v160 = 0;
  v18 = 0;
  v148 = 0;
  v147 = 0;
  v159 = 0;
  LODWORD(v155) = 0;
  v19 = *(_BYTE *)(v17 + 36);
  v146 = v19;
  v20 = v19;
  v149 = v19;
  v21 = *((_BYTE *)v14 + 100);
  if ( v19 == 98 )
  {
    v184 = 0;
    v185 = 0;
    v22 = *(_QWORD *)(v17 + 48);
    v169 = v22;
    v23 = (_OWORD *)v22;
    v24 = (_OWORD *)v17;
    v25 = 4;
    v26 = 128;
    do
    {
      *v23 = *v24;
      v23[1] = v24[1];
      v23[2] = v24[2];
      v23[3] = v24[3];
      v23[4] = v24[4];
      v23[5] = v24[5];
      v23[6] = v24[6];
      v23 += 8;
      *(v23 - 1) = v24[7];
      v24 += 8;
      --v25;
    }
    while ( v25 );
    *v23 = *v24;
    v23[1] = v24[1];
    v23[2] = v24[2];
    v23[3] = v24[3];
    v23[4] = v24[4];
    v23[5] = v24[5];
    *((_QWORD *)v23 + 12) = *((_QWORD *)v24 + 12);
    *(_DWORD *)(v22 + 56) = 0;
    *(_QWORD *)(v22 + 48) = 0;
    if ( v21 == 98 )
    {
      v27 = (struct tagBCPFLD *)*((_QWORD *)v14 + 18);
      if ( !v27 )
      {
        v27 = (struct tagBCPFLD *)SQLAllocateMemoryEx(a1, 0x1C0u, 1);
        *((_QWORD *)v14 + 18) = v27;
        if ( !v27 )
        {
          BatchCtxOrRecover = -1;
          if ( (bidGblFlags & 2) == 0 )
            goto LABEL_480;
          v86 = 7453705;
          goto LABEL_442;
        }
      }
      if ( *((_QWORD *)v27 + 15) )
      {
        v28 = *((_QWORD *)v27 + 9);
        if ( v28 )
        {
          ((void (__fastcall *)(struct IMalloc *, __int64, __int64))g_pMO->lpVtbl->Free)(g_pMO, v28, v26);
          *((_QWORD *)v27 + 9) = 0;
        }
      }
      v29 = *((_QWORD *)v27 + 13);
      if ( v29 && v29 != *((_QWORD *)v14 + 13) )
      {
        ((void (__fastcall *)(struct IMalloc *, __int64, __int64))g_pMO->lpVtbl->Free)(g_pMO, v29, v26);
        *((_QWORD *)v27 + 13) = 0;
      }
      v30 = v27;
      v31 = v14;
      v32 = 3;
      do
      {
        *(_OWORD *)v30 = *(_OWORD *)v31;
        *((_OWORD *)v30 + 1) = *((_OWORD *)v31 + 1);
        *((_OWORD *)v30 + 2) = *((_OWORD *)v31 + 2);
        *((_OWORD *)v30 + 3) = *((_OWORD *)v31 + 3);
        *((_OWORD *)v30 + 4) = *((_OWORD *)v31 + 4);
        *((_OWORD *)v30 + 5) = *((_OWORD *)v31 + 5);
        *((_OWORD *)v30 + 6) = *((_OWORD *)v31 + 6);
        v30 = (struct tagBCPFLD *)((char *)v30 + 128);
        *((_OWORD *)v30 - 1) = *((_OWORD *)v31 + 7);
        v31 = (struct tagBCPFLD *)((char *)v31 + 128);
        --v32;
      }
      while ( v32 );
      *(_OWORD *)v30 = *(_OWORD *)v31;
      *((_OWORD *)v30 + 1) = *((_OWORD *)v31 + 1);
      *((_OWORD *)v30 + 2) = *((_OWORD *)v31 + 2);
      *((_OWORD *)v30 + 3) = *((_OWORD *)v31 + 3);
      *((_QWORD *)v27 + 13) = 0;
      *((_DWORD *)v27 + 28) = 0;
      *((_DWORD *)v27 + 38) = 0;
      *((_QWORD *)v27 + 18) = 0;
      v16 = v144;
    }
    else
    {
      v27 = v14;
    }
    v33 = (BATCHCTX **)*((_QWORD *)a1 + 12);
    ColInfoByOrdinal = IRDTag::GetColInfoByOrdinal((IRDTag *)(v33 + 7), v16);
    v35 = (__int64)ColInfoByOrdinal;
    if ( *((_WORD *)ColInfoByOrdinal + 80) == 0xFFFE )
    {
      LOWORD(v143) = v144;
      LOWORD(v142) = -2;
      ColData = (*((__int64 (__fastcall **)(BATCHCTX **, struct tagCOLUMN_INFO *, char *, _QWORD, __int64 *, __int64 *, _DWORD, _DWORD, int, _DWORD, _DWORD))ColInfoByOrdinal
                 + 23))(
                  v33,
                  ColInfoByOrdinal,
                  v186,
                  0,
                  &v148,
                  &v147,
                  v142,
                  v143,
                  -1,
                  0,
                  0);
LABEL_65:
      if ( ColData == -1 )
      {
        BatchCtxOrRecover = -1;
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_480;
        v86 = 7511049;
        goto LABEL_442;
      }
      if ( v147 == -1 )
      {
        v49 = v153;
        if ( !*((_WORD *)v27 + 25) )
        {
          *(_DWORD *)v170 = 0;
          if ( (unsigned __int16)bcpWrite(a1, v154, *((int *)v153 + 24), v170) == 0xFFFF )
          {
            BatchCtxOrRecover = -1;
            if ( (bidGblFlags & 2) == 0 )
              goto LABEL_480;
            v86 = 7525385;
            goto LABEL_442;
          }
          if ( *((_DWORD *)v27 + 24) )
            *((_DWORD *)v27 + 24) = 0;
        }
        if ( v21 == 98 )
        {
          *((_QWORD *)v27 + 13) = *((_QWORD *)v49 + 13);
          *((_DWORD *)v27 + 28) = *((_DWORD *)v49 + 28);
        }
        v14 = v27;
        v153 = v27;
        v20 = v149;
        v19 = v149;
        goto LABEL_74;
      }
      Source = 0;
      v163[0] = 0;
      GetVariantHdrFromColInfo(a1, v144, (struct VariantHdr *)&v184, (struct tagCOLUMN_INFO *)v183, v163);
      v20 = v184;
      v149 = v184;
      v14 = v153;
      if ( *((_WORD *)v153 + 25) || *((_BYTE *)v153 + 100) != 98 )
      {
        v19 = 98;
LABEL_74:
        v18 = v148;
        v16 = v144;
        v4 = v162;
        v17 = v157;
        goto LABEL_97;
      }
      *(_DWORD *)(v157 + 56) = 1;
      LODWORD(v155) = 1;
      *((_DWORD *)v14 + 38) = 1;
      BatchCtxOrRecover = bcpGetColumnMetadata(a1, (struct tagBCPCOL *)v22, (struct tagCOLUMN_INFO *)v183, &v182);
      if ( BatchCtxOrRecover == 0xFFFF )
      {
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_480;
        v86 = 7565321;
        goto LABEL_442;
      }
      v50 = *(_BYTE *)(v22 + 36);
      v51 = v163[0];
      if ( *(_BYTE *)(v162 + 48) >= 0x64u || (unsigned __int8)(v50 - 40) > 3u )
      {
        v52 = -1;
      }
      else
      {
        v50 = -25;
        v52 = v163[0];
      }
      if ( !BCP_colfmt(
              a1,
              v145 + 1,
              v50,
              -1,
              v52,
              *((const unsigned __int8 **)v14 + 13),
              *((_DWORD *)v14 + 28),
              v145 + 1) )
      {
        BatchCtxOrRecover = -1;
        goto LABEL_480;
      }
      v54 = v159;
      if ( ((*(_BYTE *)(v22 + 36) - 106) & 0xFD) == 0 )
        v54 = 2;
      v159 = v54;
      if ( *((_DWORD *)v27 + 24) )
        *((_DWORD *)v27 + 24) = 0;
      *((_DWORD *)v27 + 40) = *(_DWORD *)(v22 + 88);
      *((_BYTE *)v27 + 164) = *(_BYTE *)(v22 + 92);
      if ( !(_BYTE)v184 )
        goto LABEL_92;
      v55 = BYTE1(v184) + 2;
      v56 = v55 + *((_DWORD *)v14 + 24);
      if ( v56 >= v55 )
      {
        v57 = (unsigned __int8 *)SQLAllocateMemoryEx(a1, v56, 1);
        v58 = v57;
        if ( !v57 )
        {
          BatchCtxOrRecover = -1;
          if ( (bidGblFlags & 2) == 0 )
            goto LABEL_480;
          v86 = 7625737;
          goto LABEL_442;
        }
        Source = v51 + v55;
        v59 = v153;
        memcpy_s(v57, v56, &Source, *((int *)v153 + 24));
        memcpy_s((void *const)&v58[*((int *)v59 + 24)], v56 - *((_DWORD *)v59 + 24), &v184, v55);
        v60 = bcpWrite(a1, v154, v56, v58);
        ((void (__fastcall *)(struct IMalloc *, const unsigned __int8 *))g_pMO->lpVtbl->Free)(g_pMO, v58);
        BatchCtxOrRecover = v60;
        if ( v60 == 0xFFFF )
        {
          if ( (bidGblFlags & 2) == 0 )
            goto LABEL_480;
          v86 = 7641097;
          goto LABEL_442;
        }
        v22 = v169;
        v14 = v59;
LABEL_92:
        *(_DWORD *)(v157 + 56) = 0;
        *((_DWORD *)v14 + 38) = 0;
        v157 = v22;
        v14 = v27;
        v153 = v27;
        *((_DWORD *)a1 + 608) = *((_DWORD *)IRDTag::GetColInfoByOrdinal((IRDTag *)(*((_QWORD *)a1 + 12) + 56LL), v144)
                                + 30);
        v18 = v148;
        v20 = v149;
        v19 = 98;
        v16 = v144;
        v4 = v162;
        v17 = v22;
        goto LABEL_97;
      }
      v140 = bidGblFlags;
      if ( (bidGblFlags & 2) != 0 )
      {
        bidTraceHR(0, 7619593, 2147942934LL, v53);
        v140 = bidGblFlags;
      }
      BatchCtxOrRecover = -1;
      if ( (v140 & 2) == 0 )
        goto LABEL_480;
      v86 = 7620617;
LABEL_442:
      bidTraceMark(0, v86);
      goto LABEL_480;
    }
    *((_OWORD *)ColInfoByOrdinal + 10) = 0;
    *((_OWORD *)ColInfoByOrdinal + 11) = 0;
    v37 = *((__int16 *)ColInfoByOrdinal + 8);
    if ( v37 == 13 )
    {
      VariantBaseTypeInfo = GetVariantBaseTypeInfo(v33, v144, 0xFFFFFFFF, ColInfoByOrdinal);
      if ( VariantBaseTypeInfo )
      {
        ColData = ColDataRetriever<FixedLengthOutput,0,1>::HandleError(v33, 0xFFFFFFFFLL, VariantBaseTypeInfo);
        goto LABEL_65;
      }
      LOWORD(v39) = Srv2SqlType(*(_BYTE *)(v35 + 72), *(_QWORD *)(v35 + 80));
      v40 = (__int16)v39 + 10;
      v43 = 0;
      if ( v40 > 0x19 || (v41 = 54526659, !_bittest(&v41, v40)) )
      {
        LOWORD(v39) = v39 + 8;
        if ( (unsigned __int16)v39 > 0x1Bu || (v42 = 134218305, !_bittest(&v42, v39)) )
          v43 = 1;
      }
    }
    else
    {
      v43 = 0;
      if ( v37 + 10 > 0x19 || (v44 = 54526659, !_bittest(&v44, v37 + 10)) )
      {
        LOWORD(v37) = v37 + 8;
        if ( (unsigned __int16)v37 > 0x1Bu || (v45 = 134218305, !_bittest(&v45, v37)) )
          v43 = 1;
      }
      *(_WORD *)(v35 + 160) = -2;
    }
    v46 = (*(_BYTE *)(v35 + 72) & 0x30) == 0x20 || ((*(_BYTE *)(v35 + 72) + 15) & 0xFB) == 0;
    *(_DWORD *)(v35 + 176) = v46;
    v47 = *(_DWORD *)(v35 + 120);
    v48 = v33[14];
    if ( v43 )
    {
      if ( (unsigned int)FIsConversionNeeded(v48, (struct tagCOLUMN_INFO *)v35, -2, v47, 1) )
      {
        *(_QWORD *)(v35 + 184) = ColDataRetriever<BinaryOutputWithFixedLengthSqlType,1,1>::InternalGetColData;
        ColData = ColDataRetriever<BinaryOutputWithFixedLengthSqlType,1,1>::InternalGetColData(
                    (char *)v33,
                    v35,
                    (unsigned __int8 *)v186,
                    0,
                    (unsigned __int64 *)&v148,
                    &v147,
                    65534,
                    v144,
                    0xFFFFFFFF,
                    0,
                    0);
      }
      else
      {
        *(_QWORD *)(v35 + 184) = ColDataRetriever<BinaryOutputWithFixedLengthSqlType,0,1>::InternalGetColData;
        ColData = ColDataRetriever<BinaryOutputWithFixedLengthSqlType,0,1>::InternalGetColData(
                    v33,
                    (__int64)&v148,
                    (__int64)&v147,
                    -2,
                    v144,
                    0xFFFFFFFF,
                    0,
                    0);
      }
    }
    else if ( (unsigned int)FIsConversionNeeded(v48, (struct tagCOLUMN_INFO *)v35, -2, v47, 1) )
    {
      *(_QWORD *)(v35 + 184) = ColDataRetriever<BinaryOutputWithVaribleSqlType,1,0>::InternalGetColData;
      ColData = ColDataRetriever<BinaryOutputWithVaribleSqlType,1,0>::InternalGetColData(
                  (char *)v33,
                  (struct tagCOLUMN_INFO *)v35,
                  v186,
                  0,
                  (__int64)&v148,
                  &v147,
                  65534,
                  v144,
                  0xFFFFFFFF,
                  0,
                  0);
    }
    else
    {
      *(_QWORD *)(v35 + 184) = ColDataRetriever<BinaryOutputWithVaribleSqlType,0,0>::InternalGetColData;
      ColData = ColDataRetriever<BinaryOutputWithVaribleSqlType,0,0>::InternalGetColData(
                  v33,
                  (__int64)&v148,
                  (__int64)&v147,
                  -2,
                  v144,
                  0xFFFFFFFF,
                  0,
                  0);
    }
    goto LABEL_65;
  }
  if ( *(_BYTE *)(v4 + 48) < 0x64u && *((_DWORD *)v14 + 38) )
  {
    v14 = (struct tagBCPFLD *)*((_QWORD *)v14 + 18);
    v153 = v14;
  }
LABEL_97:
  v61 = 1022;
  v163[0] = 1022;
  v62 = *((_WORD *)v14 + 25);
  v63 = (char *)v14 + 100;
  if ( v62 == 2 )
  {
    v186[0] = *(_BYTE *)v17;
    v186[1] = *(_BYTE *)(v17 + 18);
    goto LABEL_112;
  }
  if ( v62 == -12 )
  {
    if ( *v63 != 122 )
    {
      v64 = (char *)v14 + 100;
      goto LABEL_102;
    }
LABEL_119:
    v61 = 4;
    goto LABEL_110;
  }
  v64 = (char *)v14 + 100;
  if ( v62 == -23 && *v63 == 58 )
    goto LABEL_119;
LABEL_102:
  v63 = v64;
  if ( v62 != (_WORD)v174 )
    goto LABEL_111;
  if ( (unsigned __int16)(v175 + *(_WORD *)(v157 + 16)) > 2u && *(_WORD *)(v157 + 16) != 14 )
  {
    v63 = v64;
    if ( v19 != 98 || (((v20 - 37) & 0x77) != 0 || v20 == -91) && v20 != -91 )
      goto LABEL_111;
  }
  v61 = 1021;
  v63 = v64;
LABEL_110:
  v163[0] = v61;
LABEL_111:
  v17 = v157;
LABEL_112:
  v165 = 0;
  if ( BatchCtxOrRecover )
    goto LABEL_199;
  v165 = 0;
  if ( v147 == -1 )
  {
LABEL_200:
    v18 = 0;
    v148 = 0;
LABEL_201:
    v87 = v145;
    goto LABEL_202;
  }
  if ( *v63 == 41 )
  {
    v65 = -31;
  }
  else if ( *v63 == 43 )
  {
    v65 = -32;
  }
  else
  {
    v65 = *((_WORD *)v14 + 25);
  }
  if ( *(_DWORD *)(v17 + 88) || *(_BYTE *)(v17 + 92) || *((_DWORD *)v14 + 40) || *((_BYTE *)v14 + 164) )
  {
    v66 = *((_DWORD *)v14 + 39);
    if ( *((_DWORD *)a1 + 608) != v66 )
      *((_DWORD *)a1 + 608) = v66;
  }
  v67 = v61;
  v68 = (BATCHCTX **)*((_QWORD *)a1 + 12);
  v69 = IRDTag::GetColInfoByOrdinal((IRDTag *)(v68 + 7), v16);
  v70 = *((_WORD *)v69 + 80);
  v71 = 0;
  if ( v70 != v65 || !v70 )
  {
    *((_OWORD *)v69 + 10) = 0;
    *((_OWORD *)v69 + 11) = 0;
    if ( v65 == 99 )
    {
      v73 = *((__int16 *)v69 + 8);
      if ( (*((_BYTE *)v68[14] + 2488) & 0x24) != 0 )
        v65 = word_1005ACF56[v73];
      else
        v65 = word_1005ACF16[v73];
    }
    v74 = *((__int16 *)v69 + 8);
    if ( v74 == 13 )
    {
      v75 = GetVariantBaseTypeInfo(v68, v144, 0xFFFFFFFF, v69);
      if ( v75 )
      {
        v72 = ColDataRetriever<FixedLengthOutput,0,1>::HandleError(v68, 0xFFFFFFFFLL, v75);
        goto LABEL_182;
      }
      LOWORD(v76) = Srv2SqlType(*((_BYTE *)v69 + 72), *((_QWORD *)v69 + 10));
      v77 = (__int16)v76 + 10;
      v71 = 0;
      if ( v77 > 0x19 || (v78 = 54526659, !_bittest(&v78, v77)) )
      {
        LOWORD(v76) = v76 + 8;
        if ( (unsigned __int16)v76 > 0x1Bu || (v79 = 134218305, !_bittest(&v79, v76)) )
          v71 = 1;
      }
    }
    else
    {
      if ( v74 + 10 > 0x19 || (v80 = 54526659, !_bittest(&v80, v74 + 10)) )
      {
        LOWORD(v74) = v74 + 8;
        if ( (unsigned __int16)v74 > 0x1Bu || (v81 = 134218305, !_bittest(&v81, v74)) )
          v71 = 1;
      }
      *((_WORD *)v69 + 80) = v65;
    }
    v82 = (*((_BYTE *)v69 + 72) & 0x30) == 0x20 || ((*((_BYTE *)v69 + 72) + 15) & 0xFB) == 0;
    *((_DWORD *)v69 + 44) = v82;
    v83 = *((_DWORD *)v69 + 30);
    v84 = v68[14];
    if ( v71 )
    {
      if ( !(unsigned int)FIsConversionNeeded(v84, v69, v65, v83, 1) )
      {
        if ( v65 == -2 )
        {
          *((_QWORD *)v69 + 23) = ColDataRetriever<BinaryOutputWithFixedLengthSqlType,0,1>::InternalGetColData;
          v72 = ColDataRetriever<BinaryOutputWithFixedLengthSqlType,0,1>::InternalGetColData(
                  v68,
                  (__int64)&v148,
                  (__int64)&v147,
                  -2,
                  v144,
                  0xFFFFFFFF,
                  0,
                  0);
        }
        else if ( v65 == 1 || v65 == -8 )
        {
          *((_QWORD *)v69 + 23) = ColDataRetriever<StringhOutput,0,1>::InternalGetColData;
          v72 = ColDataRetriever<StringhOutput,0,1>::InternalGetColData(
                  (char *)v68,
                  (__int64)v69,
                  v186,
                  v67,
                  (__int64)&v148,
                  &v147,
                  v65,
                  v144,
                  0xFFFFFFFF,
                  0,
                  0);
        }
        else
        {
          *((_QWORD *)v69 + 23) = ColDataRetriever<FixedLengthOutput,0,1>::InternalGetColData;
          v72 = ColDataRetriever<FixedLengthOutput,0,1>::InternalGetColData(
                  v68,
                  (__int64)&v148,
                  (__int64)&v147,
                  v65,
                  v144,
                  0xFFFFFFFF,
                  0,
                  0);
        }
        goto LABEL_182;
      }
      if ( v65 == -2 )
      {
        *((_QWORD *)v69 + 23) = ColDataRetriever<BinaryOutputWithFixedLengthSqlType,1,1>::InternalGetColData;
        v72 = ColDataRetriever<BinaryOutputWithFixedLengthSqlType,1,1>::InternalGetColData(
                (char *)v68,
                (__int64)v69,
                (unsigned __int8 *)v186,
                v67,
                (unsigned __int64 *)&v148,
                &v147,
                -2,
                v144,
                0xFFFFFFFF,
                0,
                0);
        goto LABEL_182;
      }
      if ( v65 != 1 && v65 != -8 )
      {
LABEL_160:
        *((_QWORD *)v69 + 23) = ColDataRetriever<FixedLengthOutput,1,0>::InternalGetColData;
        v72 = ColDataRetriever<FixedLengthOutput,1,0>::InternalGetColData(
                (char *)v68,
                (__int64)v69,
                (unsigned __int8 *)v186,
                v67,
                (unsigned __int64 *)&v148,
                &v147,
                v65,
                v144,
                0xFFFFFFFF,
                0,
                0);
        goto LABEL_182;
      }
    }
    else
    {
      if ( !(unsigned int)FIsConversionNeeded(v84, v69, v65, v83, 1) )
      {
        if ( v65 == -2 || v65 == 16386 )
        {
          *((_QWORD *)v69 + 23) = ColDataRetriever<BinaryOutputWithVaribleSqlType,0,0>::InternalGetColData;
          v72 = ColDataRetriever<BinaryOutputWithVaribleSqlType,0,0>::InternalGetColData(
                  v68,
                  (__int64)&v148,
                  (__int64)&v147,
                  v65,
                  v144,
                  0xFFFFFFFF,
                  0,
                  0);
        }
        else if ( v65 == 1 || v65 == -8 )
        {
          *((_QWORD *)v69 + 23) = ColDataRetriever<StringhOutput,0,0>::InternalGetColData;
          v72 = ColDataRetriever<StringhOutput,0,0>::InternalGetColData(
                  (char *)v68,
                  (__int64)v69,
                  v186,
                  v67,
                  (__int64)&v148,
                  &v147,
                  v65,
                  v144,
                  0xFFFFFFFF,
                  0,
                  0);
        }
        else
        {
          *((_QWORD *)v69 + 23) = ColDataRetriever<FixedLengthOutput,0,0>::InternalGetColData;
          v72 = ColDataRetriever<FixedLengthOutput,0,0>::InternalGetColData(
                  v68,
                  (__int64)&v148,
                  (__int64)&v147,
                  v65,
                  v144,
                  0xFFFFFFFF,
                  0,
                  0);
        }
        goto LABEL_182;
      }
      if ( v65 == -2 || v65 == 16386 )
      {
        *((_QWORD *)v69 + 23) = ColDataRetriever<BinaryOutputWithVaribleSqlType,1,0>::InternalGetColData;
        v72 = ColDataRetriever<BinaryOutputWithVaribleSqlType,1,0>::InternalGetColData(
                (char *)v68,
                v69,
                v186,
                v67,
                (__int64)&v148,
                &v147,
                v65,
                v144,
                0xFFFFFFFF,
                0,
                0);
        goto LABEL_182;
      }
      if ( v65 != 1 && v65 != -8 )
        goto LABEL_160;
    }
    *((_QWORD *)v69 + 23) = ColDataRetriever<StringhOutput,1,0>::InternalGetColData;
    v72 = ColDataRetriever<StringhOutput,1,0>::InternalGetColData(
            (char *)v68,
            v69,
            v186,
            v67,
            (__int64)&v148,
            &v147,
            v65,
            v144,
            0xFFFFFFFF,
            0,
            0);
    goto LABEL_182;
  }
  LOWORD(v143) = v144;
  LOWORD(v142) = v65;
  v72 = (*((__int64 (__fastcall **)(BATCHCTX **, struct tagCOLUMN_INFO *, char *, _QWORD, __int64 *, __int64 *, _DWORD, _DWORD, int, _DWORD, _DWORD))v69
         + 23))(
          v68,
          v69,
          v186,
          (unsigned int)v67,
          &v148,
          &v147,
          v142,
          v143,
          -1,
          0,
          0);
LABEL_182:
  BatchCtxOrRecover = v72;
  if ( v72 == 0xFFFF )
  {
    if ( *((_DWORD *)a1 + 608) != v167 )
      *((_DWORD *)a1 + 608) = v167;
    XferErrors(a1, *((struct tagOBJBASE **)a1 + 12));
    goto LABEL_480;
  }
  if ( v147 != -1 && (*v63 == 40 || *v63 == 41 || (unsigned int)(unsigned __int8)*v63 - 42 <= 1) )
  {
    v14 = v153;
    v85 = bcpConvertToDateTimeTDSFormat(v153, (unsigned __int8 *)v186, v148, (unsigned __int8 *)v186, v148, &v148);
    if ( v85 )
    {
      if ( (bidGblFlags & 2) != 0 )
        bidTraceMark(0, 7765001);
      PostSQLErrorEx(a1, v85, 0, 0xFFFFFFFFFFFFFFFFuLL, v145 + 1);
      BatchCtxOrRecover = -1;
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_480;
      v86 = 7766025;
      goto LABEL_442;
    }
  }
  else
  {
    v14 = v153;
  }
  v165 = 0;
  v4 = v162;
  if ( *(_BYTE *)(v162 + 48) >= 0x5Au )
  {
    v165 = 0;
    if ( *((_DWORD *)v14 + 24) == 8 )
    {
      if ( v148 == -4 || (v165 = 0, v148 > 0x7FFFFFFF) )
      {
        LODWORD(v156) = 1;
        v165 = 1;
      }
    }
  }
  v18 = v148 - v159;
  v148 = v18;
LABEL_199:
  if ( v147 == -1 )
    goto LABEL_200;
  if ( v18 || v146 == 98 && (_DWORD)v155 )
  {
    if ( *(_WORD *)(v157 + 16) != 11 )
      goto LABEL_201;
    if ( *((_WORD *)v14 + 25) == 1 && (*(_BYTE *)(v4 + 52) & 4) != 0 )
    {
      if ( (unsigned __int16)bcpWrite(a1, v154, 5, "{ts '") != 0xFFFF )
      {
        v18 = v148;
        goto LABEL_201;
      }
      if ( (bidGblFlags & 2) != 0 )
        bidTraceMark(0, 7811081);
      v87 = v145;
      PostSQLErrorEx(a1, 0x9D16u, 0, 0xFFFFFFFFFFFFFFFFuLL, v145 + 1);
      v18 = v148;
    }
    else
    {
      v87 = v145;
    }
  }
  else
  {
    if ( *((_DWORD *)v14 + 24) )
      goto LABEL_201;
    if ( *((_WORD *)v14 + 25) == 1 )
    {
      v18 = 1;
      v148 = 1;
      v186[0] = 0;
      goto LABEL_201;
    }
    v87 = v145;
    if ( *((_WORD *)v14 + 25) == 0xFFF8 )
    {
      v18 = 2;
      v148 = 2;
      *(_WORD *)v186 = 0;
    }
  }
LABEL_202:
  BatchCtxOrRecover = 0;
  v88 = v18;
  *(_QWORD *)v151 = v18;
  if ( *((_WORD *)v14 + 25) == 1 )
  {
    v89 = 1;
  }
  else
  {
    v89 = 0;
    if ( *((_WORD *)v14 + 25) == 0xFFF8 )
      v89 = 2;
  }
  v169 = v89;
  v90 = v163[0];
  v155 = v163[0];
  if ( v18 == -4 || (*(_QWORD *)v161 = v18, v18 > v163[0] - v89) )
    *(_QWORD *)v161 = v163[0] - v89;
  v91 = *((int *)v14 + 24);
  if ( (_DWORD)v91 )
  {
    if ( v147 == -1 )
    {
      v92 = (unsigned __int8 *)&qword_10059DE30;
      v156 = 0;
LABEL_261:
      BatchCtxOrRecover = bcpWrite(a1, v154, v91, v92);
      if ( BatchCtxOrRecover == 0xFFFF )
      {
        if ( (bidGblFlags & 2) != 0 )
          bidTraceMark(0, 7878665);
        PostSQLErrorEx(a1, 0x9D16u, 0, 0xFFFFFFFFFFFFFFFFuLL, v87 + 1);
      }
      v18 = v148;
      v88 = *(_QWORD *)v151;
      v99 = v156;
      goto LABEL_266;
    }
    if ( (_DWORD)v156 )
    {
      v164 = 0;
      if ( (unsigned __int16)bcpWrite(a1, v154, v91, &qword_10059DE38) == 0xFFFF )
      {
        if ( (bidGblFlags & 2) != 0 )
          bidTraceMark(0, 7851017);
        PostSQLErrorEx(a1, 0x9D16u, 0, 0xFFFFFFFFFFFFFFFFuLL, v87 + 1);
      }
      v91 = 4;
      v92 = v161;
      v156 = 0;
      goto LABEL_261;
    }
    v164 = 1;
    if ( v18 == -4 )
      goto LABEL_249;
    if ( v18 <= 0 )
    {
LABEL_248:
      v156 = 0;
LABEL_260:
      v168 = v18;
      *(_QWORD *)v172 = v18;
      v91 = *((int *)v14 + 24);
      v92 = v172;
      goto LABEL_261;
    }
    switch ( (_DWORD)v91 )
    {
      case 1:
        v94 = 254;
        break;
      case 2:
        v94 = 65534;
        break;
      case 4:
      case 8:
        v94 = 0x7FFFFFFF;
        break;
      default:
        v93 = 0;
        goto LABEL_247;
    }
    v93 = v94 & 0xFFFFFFFFFFFFFFFEuLL;
    if ( *((_WORD *)v14 + 25) != 0xFFF8 )
      v93 = v94;
LABEL_247:
    if ( v18 <= v93 )
      goto LABEL_248;
LABEL_249:
    v95 = v91 - 1;
    if ( v95 )
    {
      v96 = v95 - 1;
      if ( v96 )
      {
        v97 = v96 - 2;
        if ( v97 && v97 != 4 )
        {
          v18 = 0;
LABEL_259:
          v156 = 1;
          goto LABEL_260;
        }
        v98 = 0x7FFFFFFF;
      }
      else
      {
        v98 = 65534;
      }
    }
    else
    {
      v98 = 254;
    }
    v18 = v98 & 0xFFFFFFFFFFFFFFFEuLL;
    if ( *((_WORD *)v14 + 25) != 0xFFF8 )
      v18 = v98;
    goto LABEL_259;
  }
  v106 = *((int *)v14 + 23);
  v99 = 0;
  v156 = 0;
  if ( (int)v106 <= 0 )
  {
LABEL_266:
    v100 = v153;
    goto LABEL_267;
  }
  v156 = 0;
  v100 = v153;
  if ( !*((_DWORD *)v153 + 28) )
  {
    v156 = 0;
    if ( v18 > v106 )
    {
      LODWORD(v143) = v87 + 1;
      LODWORD(v142) = v106;
      v107 = PostFormattedError(a1, 0xFFFFFFFFFFFFFFFFuLL, v87 + 1, 1, 0x9D41u, v18, v142, v143);
      v99 = 0;
      v156 = 0;
      if ( (v107 & 0xFFFE) != 0 )
      {
        BatchCtxOrRecover = -1;
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_480;
        v86 = 7896073;
        goto LABEL_442;
      }
      v18 = v148;
      v88 = *(_QWORD *)v151;
      goto LABEL_266;
    }
  }
LABEL_267:
  if ( !v18 && *((int *)v100 + 28) > 0 && !*(_DWORD *)(v162 + 2196) )
  {
    bcpLog(a1, 0x9D68u, v87);
    *(_DWORD *)(v162 + 2196) = 1;
    v88 = *(_QWORD *)v151;
  }
  if ( (BatchCtxOrRecover & 0xFFFE) != 0 )
  {
LABEL_376:
    v127 = v145;
    v104 = v154;
LABEL_381:
    v126 = v160;
LABEL_382:
    if ( (BatchCtxOrRecover & 0xFFFE) == 0 && v164 && v126 != v168 )
    {
      v128 = *((_QWORD *)v104 + 6);
      BatchCtxOrRecover = bcpWriteSeek(a1, v154, v178);
      if ( BatchCtxOrRecover == 0xFFFF )
      {
        if ( (bidGblFlags & 2) != 0 )
          bidTraceMark(0, 8045577);
        PostSQLErrorEx(a1, 0x9D16u, 0, 0xFFFFFFFFFFFFFFFFuLL, v127 + 1);
      }
      else
      {
        *(_QWORD *)v172 = v126;
        v129 = v153;
        if ( (unsigned __int16)bcpWrite(a1, v154, *((int *)v153 + 24), v172) == 0xFFFF )
        {
          if ( (bidGblFlags & 2) != 0 )
            bidTraceMark(0, 8058889);
          v130 = v127 + 1;
          PostSQLErrorEx(a1, 0x9D16u, 0, 0xFFFFFFFFFFFFFFFFuLL, v130);
        }
        else
        {
          v130 = v127 + 1;
        }
        v131 = v128;
        v104 = v154;
        BatchCtxOrRecover = bcpWriteSeek(a1, v154, v131);
        if ( BatchCtxOrRecover != 0xFFFF )
        {
LABEL_392:
          if ( *((_DWORD *)a1 + 608) != v167 )
            *((_DWORD *)a1 + 608) = v167;
          v148 = v160;
          v132 = v152;
          if ( !BatchCtxOrRecover )
          {
            *(_WORD *)(*((_QWORD *)a1 + 12) + 264LL) = v152 + 1;
            if ( !*((_DWORD *)v129 + 24)
              && !*((_DWORD *)v129 + 28)
              && (v148 < (int)(*((_DWORD *)v129 + 23) - v159) || !v148) )
            {
              v133 = *((__int16 *)v129 + 25);
              if ( v133 == -8 )
              {
                v134 = (const unsigned __int8 *)off_1005D07C8;
              }
              else
              {
                v134 = (const unsigned __int8 *)off_1005D07D8;
                if ( v133 == 1 )
                  v134 = off_1005D07D0;
              }
              v135 = *((int *)v129 + 23) - v148;
              if ( v135 > 0x1E )
              {
                v136 = (v135 - 31) / 0x1E + 1;
                v135 += -30LL * v136;
                v137 = v154;
                do
                {
                  BatchCtxOrRecover = bcpWrite(a1, v137, 30, v134);
                  --v136;
                }
                while ( v136 );
                v129 = v153;
                v104 = v154;
              }
              if ( v135 )
                BatchCtxOrRecover = bcpWrite(a1, v104, v135, v134);
              if ( BatchCtxOrRecover == 0xFFFF )
              {
                if ( (bidGblFlags & 2) != 0 )
                  bidTraceMark(0, 8117257);
                v138 = v145;
                PostSQLErrorEx(a1, 0x9D16u, 0, 0xFFFFFFFFFFFFFFFFuLL, v145 + 1);
                v132 = v152;
                goto LABEL_417;
              }
              v132 = v152;
            }
          }
          v138 = v145;
LABEL_417:
          if ( !*(_QWORD *)(v173 + 136) && !*(_QWORD *)(v173 + 144) )
            *(_WORD *)(*((_QWORD *)a1 + 12) + 264LL) = v132 + 1;
          if ( BatchCtxOrRecover )
          {
            if ( BatchCtxOrRecover == 0xFFFF )
              goto LABEL_476;
            goto LABEL_431;
          }
          if ( v148 && *(_WORD *)(v157 + 16) == 11 && *((_WORD *)v129 + 25) == 1 && (*(_BYTE *)(v162 + 52) & 4) != 0 )
            BatchCtxOrRecover = bcpWrite(a1, v104, 2, "'}");
          if ( *((int *)v129 + 28) > 0 )
            BatchCtxOrRecover = bcpWrite(a1, v104, *((int *)v129 + 28), *((const unsigned __int8 **)v129 + 13));
          if ( BatchCtxOrRecover != 0xFFFF )
          {
LABEL_431:
            v4 = v162;
            goto LABEL_432;
          }
          if ( (bidGblFlags & 2) != 0 )
            bidTraceMark(0, 8133641);
          PostSQLErrorEx(a1, 0x9D16u, 0, 0xFFFFFFFFFFFFFFFFuLL, v138 + 1);
LABEL_476:
          FlushColData(*((struct tagSTMT **)a1 + 12), 0, 0xFFFFFFFF);
LABEL_434:
          v139 = ProcessTDSStream(*((struct tagSTMT **)a1 + 12), 0x24u, *((_DWORD *)a1 + 344));
          if ( (BatchCtxOrRecover & 0xFFFE) == 0 && v139 )
            BatchCtxOrRecover = v139;
          if ( BatchCtxOrRecover == 0xFFFF && *(_DWORD *)(v173 + 32) == 16 )
          {
            v2 = v150;
            *v150 = 1;
            goto LABEL_481;
          }
          if ( (unsigned __int8)(*(_BYTE *)(v173 + 56) + 47) > 2u )
          {
            *(_DWORD *)(*((_QWORD *)a1 + 12) + 1516LL) |= 4u;
            CleanUphStmt(*((struct tagSTMT **)a1 + 12), 0);
          }
LABEL_479:
          if ( BatchCtxOrRecover != 0xFFFF )
            goto LABEL_485;
LABEL_480:
          v2 = v150;
          goto LABEL_481;
        }
        if ( (bidGblFlags & 2) != 0 )
          bidTraceMark(0, 8065033);
        PostSQLErrorEx(a1, 0x9D16u, 0, 0xFFFFFFFFFFFFFFFFuLL, v130);
      }
      *v150 = 1;
      goto LABEL_485;
    }
    v129 = v153;
    goto LABEL_392;
  }
  v101 = v159;
  v177 = v159;
  v102 = (unsigned __int8 *)&v186[v159];
  v176 = v102;
  v103 = v102;
  while ( 1 )
  {
    if ( v88 <= 0 )
    {
      v103 = v102;
      if ( v88 != -4 )
        goto LABEL_376;
    }
    if ( v99 && *(_QWORD *)v161 + v160 > v168 )
      break;
    *(_QWORD *)v163 = &v186[v101];
    v104 = v154;
    BatchCtxOrRecover = bcpWrite(a1, v154, *(__int64 *)v161, (const unsigned __int8 *)&v186[v101]);
    if ( BatchCtxOrRecover == 0xFFFF )
    {
      if ( (bidGblFlags & 2) != 0 )
        bidTraceMark(0, 7961609);
      v127 = v145;
      PostSQLErrorEx(a1, 0x9D16u, 0, 0xFFFFFFFFFFFFFFFFuLL, v145 + 1);
      if ( (bidGblFlags & 2) != 0 )
        bidTraceMark(0, 7962633);
      goto LABEL_381;
    }
    v160 += *(_QWORD *)v161;
    v105 = v90 - v169;
    v88 = *(_QWORD *)v151;
    if ( *(__int64 *)v151 <= v105 && *(_QWORD *)v151 != -4 )
    {
      v88 = 0;
      *(_QWORD *)v151 = 0;
      if ( v165 )
      {
        BatchCtxOrRecover = bcpWrite(a1, v104, 4, v151);
        if ( BatchCtxOrRecover == 0xFFFF )
        {
          if ( (bidGblFlags & 2) != 0 )
            bidTraceMark(0, 7979017);
          v87 = v145;
          PostSQLErrorEx(a1, 0x9D16u, 0, 0xFFFFFFFFFFFFFFFFuLL, v145 + 1);
          v88 = *(_QWORD *)v151;
          goto LABEL_364;
        }
        v88 = *(_QWORD *)v151;
      }
    }
    if ( BatchCtxOrRecover || v88 <= 0 && v88 != -4 )
      goto LABEL_363;
    v158[0] = 0;
    v171 = 0;
    v108 = *((_WORD *)v153 + 25);
    v109 = (BATCHCTX **)*((_QWORD *)a1 + 12);
    v110 = IRDTag::GetColInfoByOrdinal((IRDTag *)(v109 + 7), v144);
    v111 = *((_WORD *)v110 + 80);
    v112 = 0;
    if ( v111 == v108 && v111 )
    {
      LOWORD(v143) = v144;
      LOWORD(v142) = v108;
      v113 = (*((__int64 (__fastcall **)(BATCHCTX **, struct tagCOLUMN_INFO *, char *, rsize_t, unsigned __int8 *, __int64 *, _DWORD, _DWORD, int, _DWORD, _DWORD))v110
              + 23))(
               v109,
               v110,
               v186,
               v155,
               v151,
               &v147,
               v142,
               v143,
               -1,
               0,
               0);
      goto LABEL_348;
    }
    *((_OWORD *)v110 + 10) = 0;
    *((_OWORD *)v110 + 11) = 0;
    if ( v108 == 99 )
    {
      v114 = *((__int16 *)v110 + 8);
      if ( (*((_BYTE *)v109[14] + 2488) & 0x24) != 0 )
        v108 = word_1005ACF56[v114];
      else
        v108 = word_1005ACF16[v114];
    }
    v115 = *((__int16 *)v110 + 8);
    if ( v115 == 13 )
    {
      v116 = GetVariantBaseTypeInfo(v109, v144, 0xFFFFFFFF, v110);
      if ( v116 )
      {
        v113 = ColDataRetriever<FixedLengthOutput,0,1>::HandleError(v109, 0xFFFFFFFFLL, v116);
        goto LABEL_348;
      }
      LOWORD(v117) = Srv2SqlType(*((_BYTE *)v110 + 72), *((_QWORD *)v110 + 10));
      v118 = (__int16)v117 + 10;
      v112 = 0;
      if ( v118 > 0x19 || (v119 = 54526659, !_bittest(&v119, v118)) )
      {
        LOWORD(v117) = v117 + 8;
        if ( (unsigned __int16)v117 > 0x1Bu || (v120 = 134218305, !_bittest(&v120, v117)) )
          v112 = 1;
      }
    }
    else
    {
      if ( v115 + 10 > 0x19 || (v121 = 54526659, !_bittest(&v121, v115 + 10)) )
      {
        LOWORD(v115) = v115 + 8;
        if ( (unsigned __int16)v115 > 0x1Bu || (v122 = 134218305, !_bittest(&v122, v115)) )
          v112 = 1;
      }
      *((_WORD *)v110 + 80) = v108;
    }
    v123 = (*((_BYTE *)v110 + 72) & 0x30) == 0x20 || ((*((_BYTE *)v110 + 72) + 15) & 0xFB) == 0;
    *((_DWORD *)v110 + 44) = v123;
    v124 = *((_DWORD *)v110 + 30);
    v125 = v109[14];
    if ( v112 )
    {
      if ( !(unsigned int)FIsConversionNeeded(v125, v110, v108, v124, 1) )
      {
        if ( v108 == -2 )
        {
          *((_QWORD *)v110 + 23) = ColDataRetriever<BinaryOutputWithFixedLengthSqlType,0,1>::InternalGetColData;
          v113 = ColDataRetriever<BinaryOutputWithFixedLengthSqlType,0,1>::InternalGetColData(
                   v109,
                   (__int64)v151,
                   (__int64)&v147,
                   -2,
                   v144,
                   0xFFFFFFFF,
                   0,
                   0);
        }
        else if ( v108 == 1 || v108 == -8 )
        {
          *((_QWORD *)v110 + 23) = ColDataRetriever<StringhOutput,0,1>::InternalGetColData;
          v113 = ColDataRetriever<StringhOutput,0,1>::InternalGetColData(
                   (char *)v109,
                   (__int64)v110,
                   v186,
                   v155,
                   (__int64)v151,
                   &v147,
                   v108,
                   v144,
                   0xFFFFFFFF,
                   0,
                   0);
        }
        else
        {
          *((_QWORD *)v110 + 23) = ColDataRetriever<FixedLengthOutput,0,1>::InternalGetColData;
          v113 = ColDataRetriever<FixedLengthOutput,0,1>::InternalGetColData(
                   v109,
                   (__int64)v151,
                   (__int64)&v147,
                   v108,
                   v144,
                   0xFFFFFFFF,
                   0,
                   0);
        }
        goto LABEL_348;
      }
      if ( v108 == -2 )
      {
        *((_QWORD *)v110 + 23) = ColDataRetriever<BinaryOutputWithFixedLengthSqlType,1,1>::InternalGetColData;
        v113 = ColDataRetriever<BinaryOutputWithFixedLengthSqlType,1,1>::InternalGetColData(
                 (char *)v109,
                 (__int64)v110,
                 (unsigned __int8 *)v186,
                 v155,
                 (unsigned __int64 *)v151,
                 &v147,
                 -2,
                 v144,
                 0xFFFFFFFF,
                 0,
                 0);
        goto LABEL_348;
      }
      if ( v108 != 1 && v108 != -8 )
      {
LABEL_326:
        *((_QWORD *)v110 + 23) = ColDataRetriever<FixedLengthOutput,1,0>::InternalGetColData;
        v113 = ColDataRetriever<FixedLengthOutput,1,0>::InternalGetColData(
                 (char *)v109,
                 (__int64)v110,
                 (unsigned __int8 *)v186,
                 v155,
                 (unsigned __int64 *)v151,
                 &v147,
                 v108,
                 v144,
                 0xFFFFFFFF,
                 0,
                 0);
        goto LABEL_348;
      }
      goto LABEL_339;
    }
    if ( !(unsigned int)FIsConversionNeeded(v125, v110, v108, v124, 1) )
    {
      if ( v108 == -2 || v108 == 16386 )
      {
        *((_QWORD *)v110 + 23) = ColDataRetriever<BinaryOutputWithVaribleSqlType,0,0>::InternalGetColData;
        v113 = ColDataRetriever<BinaryOutputWithVaribleSqlType,0,0>::InternalGetColData(
                 v109,
                 (__int64)v151,
                 (__int64)&v147,
                 v108,
                 v144,
                 0xFFFFFFFF,
                 0,
                 0);
      }
      else if ( v108 == 1 || v108 == -8 )
      {
        *((_QWORD *)v110 + 23) = ColDataRetriever<StringhOutput,0,0>::InternalGetColData;
        v113 = ColDataRetriever<StringhOutput,0,0>::InternalGetColData(
                 (char *)v109,
                 (__int64)v110,
                 v186,
                 v155,
                 (__int64)v151,
                 &v147,
                 v108,
                 v144,
                 0xFFFFFFFF,
                 0,
                 0);
      }
      else
      {
        *((_QWORD *)v110 + 23) = ColDataRetriever<FixedLengthOutput,0,0>::InternalGetColData;
        v113 = ColDataRetriever<FixedLengthOutput,0,0>::InternalGetColData(
                 v109,
                 (__int64)v151,
                 (__int64)&v147,
                 v108,
                 v144,
                 0xFFFFFFFF,
                 0,
                 0);
      }
      goto LABEL_348;
    }
    if ( v108 != -2 && v108 != 16386 )
    {
      if ( v108 != 1 && v108 != -8 )
        goto LABEL_326;
LABEL_339:
      *((_QWORD *)v110 + 23) = ColDataRetriever<StringhOutput,1,0>::InternalGetColData;
      v113 = ColDataRetriever<StringhOutput,1,0>::InternalGetColData(
               (char *)v109,
               v110,
               v186,
               v155,
               (__int64)v151,
               &v147,
               v108,
               v144,
               0xFFFFFFFF,
               0,
               0);
      goto LABEL_348;
    }
    *((_QWORD *)v110 + 23) = ColDataRetriever<BinaryOutputWithVaribleSqlType,1,0>::InternalGetColData;
    v113 = ColDataRetriever<BinaryOutputWithVaribleSqlType,1,0>::InternalGetColData(
             (char *)v109,
             v110,
             v186,
             v155,
             (__int64)v151,
             &v147,
             v108,
             v144,
             0xFFFFFFFF,
             0,
             0);
LABEL_348:
    BatchCtxOrRecover = v113;
    if ( v113 == 1 && !PeekError(*((struct tagOBJBASE **)a1 + 12), v158, &v171) && v158[0] == 0x9DDA )
      FreeErrors(*((struct tagOBJBASE **)a1 + 12));
    v88 = *(_QWORD *)v151;
    if ( *(_QWORD *)v151 == -4 || (*(_QWORD *)v161 = *(_QWORD *)v151, *(__int64 *)v151 > v105) )
      *(_QWORD *)v161 = v105;
    if ( (BatchCtxOrRecover & 0xFFFE) != 0 || !v165 )
      goto LABEL_362;
    BatchCtxOrRecover = bcpWrite(a1, v154, 4, v161);
    if ( BatchCtxOrRecover != 0xFFFF )
    {
      v88 = *(_QWORD *)v151;
LABEL_362:
      v99 = v156;
LABEL_363:
      v87 = v145;
      goto LABEL_364;
    }
    if ( (bidGblFlags & 2) != 0 )
      bidTraceMark(0, 8029193);
    v87 = v145;
    PostSQLErrorEx(a1, 0x9D16u, 0, 0xFFFFFFFFFFFFFFFFuLL, v145 + 1);
    v88 = *(_QWORD *)v151;
    v99 = v156;
LABEL_364:
    if ( (BatchCtxOrRecover & 0xFFFE) != 0 )
      goto LABEL_376;
    v103 = *(const unsigned __int8 **)v163;
    v102 = v176;
    v101 = v177;
    v90 = v155;
  }
  v126 = v160;
  *(_QWORD *)v161 = v168 - v160;
  BatchCtxOrRecover = bcpWrite(a1, v154, v168 - v160, v103);
  if ( BatchCtxOrRecover == 0xFFFF )
  {
    if ( (bidGblFlags & 2) != 0 )
      bidTraceMark(0, 7933961);
    PostSQLErrorEx(a1, 0x9D16u, 0, 0xFFFFFFFFFFFFFFFFuLL, v87 + 1);
    if ( (bidGblFlags & 2) != 0 )
      bidTraceMark(0, 7934985);
LABEL_371:
    v127 = v145;
    v104 = v154;
    goto LABEL_382;
  }
  v126 += *(_QWORD *)v161;
  v160 = v126;
  BatchCtxOrRecover = FlushColData(*((struct tagSTMT **)a1 + 12), v144 + 1, 0xFFFFFFFF);
  if ( BatchCtxOrRecover != 0xFFFF )
  {
    if ( (bidGblFlags & 2) != 0 )
      bidTraceMark(0, 7950345);
    PostSQLErrorEx(a1, 0x9DDAu, 0, 0xFFFFFFFFFFFFFFFFuLL, v87 + 1);
    goto LABEL_371;
  }
  XferErrors(a1, *((struct tagOBJBASE **)a1 + 12));
  if ( (bidGblFlags & 2) != 0 )
    bidTraceMark(0, 7945225);
  v2 = v150;
LABEL_481:
  if ( (unsigned __int16)bcpWriteSeek(a1, v154, v179) == 0xFFFF )
  {
    if ( (bidGblFlags & 2) != 0 )
      bidTraceMark(0, 8170505);
    PostSQLErrorEx(a1, 0x9D16u, 0, 0xFFFFFFFFFFFFFFFFuLL, 0xFFFFFFFF);
    *v2 = 1;
  }
LABEL_485:
  if ( (bidGblFlags & 2) != 0 )
    BatchCtxOrRecover = _bidx_SNACOdbc_ErrCode(0, 0x7CC009u, BatchCtxOrRecover);
  CAutoBatchCtx_ODBC::Reset((CAutoBatchCtx_ODBC *)&v180);
  return BatchCtxOrRecover;
}

```

## disassembly

```asm
0x1004b5c74  mov     rax, rsp
0x1004b5c77  push    rbp
0x1004b5c78  push    rsi
0x1004b5c79  push    rdi
0x1004b5c7a  push    r12
0x1004b5c7c  push    r13
0x1004b5c7e  push    r14
0x1004b5c80  push    r15
0x1004b5c82  lea     rbp, [rax-598h]
0x1004b5c89  sub     rsp, 660h
0x1004b5c90  mov     [rbp+590h+var_520], 0FFFFFFFFFFFFFFFEh
0x1004b5c98  mov     [rax+18h], rbx
0x1004b5c9c  mov     rax, cs:__security_cookie
0x1004b5ca3  xor     rax, rsp
0x1004b5ca6  mov     [rbp+590h+var_40], rax
0x1004b5cad  mov     r15, rdx
0x1004b5cb0  mov     [rbp+590h+var_608], rdx
0x1004b5cb4  mov     r13, rcx
0x1004b5cb7  mov     rsi, [rcx+78h]
0x1004b5cbb  mov     [rbp+590h+var_5B0], rsi
0x1004b5cbf  mov     eax, [rcx+980h]
0x1004b5cc5  mov     [rbp+590h+var_58C], eax
0x1004b5cc8  mov     rax, [rcx+60h]
0x1004b5ccc  movzx   edi, word ptr [rax+10Ch]
0x1004b5cd3  xorps   xmm0, xmm0
0x1004b5cd6  movdqu  [rbp+590h+var_530], xmm0
0x1004b5cdb  lea     rax, [rsi+690h]
0x1004b5ce2  mov     [rbp+590h+var_5E8], rax
0x1004b5ce6  mov     rax, [rax+30h]
0x1004b5cea  mov     [rbp+590h+var_538], rax
0x1004b5cee  xor     eax, eax
0x1004b5cf0  mov     [rdx], eax
0x1004b5cf2  mov     rcx, [rcx+60h]; struct tagSTMT *
0x1004b5cf6  lea     edx, [rax+1]
0x1004b5cf9  mov     [rbp+590h+var_560], rdx
0x1004b5cfd  mov     dword ptr [rsp+690h+var_668], edx; unsigned int
0x1004b5d01  mov     [rsp+690h+var_670], rax; unsigned int *
0x1004b5d06  mov     r9d, [rcx+5E4h]; unsigned int
0x1004b5d0d  xor     r8d, r8d; unsigned __int8
0x1004b5d10  lea     rdx, [rbp+590h+var_530]; struct CAutoBatchCtx_ODBC *
0x1004b5d14  call    ?GetBatchCtxOrRecover@@YAFPEAUtagSTMT@@PEAVCAutoBatchCtx_ODBC@@EKPEAKK@Z; GetBatchCtxOrRecover(tagSTMT *,CAutoBatchCtx_ODBC *,uchar,ulong,ulong *,ulong)
0x1004b5d19  movzx   ebx, ax
0x1004b5d1c  mov     rcx, [r13+60h]
0x1004b5d20  mov     r8, [rcx+468h]
0x1004b5d27  mov     [rbp+590h+var_568], r8
0x1004b5d2b  mov     eax, 0FFFEh
0x1004b5d30  or      r14, 0FFFFFFFFFFFFFFFFh
0x1004b5d34  test    ax, bx
0x1004b5d37  jz      short loc_1004B5D5B
0x1004b5d39  lea     r12d, [r14+3]
0x1004b5d3d  test    byte ptr cs:_bidGblFlags, r12b
0x1004b5d44  jz      loc_1004B81EE
0x1004b5d4a  mov     edx, 707C09h
0x1004b5d4f  xor     ecx, ecx
0x1004b5d51  call    _bidTraceMark
0x1004b5d56  jmp     loc_1004B81EE
0x1004b5d5b  movzx   eax, word ptr [rcx+122h]
0x1004b5d62  xor     r9d, r9d
0x1004b5d65  lea     r10d, [r9+1]
0x1004b5d69  test    ax, ax
0x1004b5d6c  jz      short loc_1004B5DA8
0x1004b5d6e  mov     r8d, eax
0x1004b5d71  mov     eax, r10d
0x1004b5d74  mov     rcx, [rcx+0C8h]
0x1004b5d7b  test    rcx, rcx
0x1004b5d7e  jz      short loc_1004B5DD2
0x1004b5d80  cmp     rax, r8
0x1004b5d83  jnb     short loc_1004B5D9B
0x1004b5d85  mov     rdx, [rcx+18h]
0x1004b5d89  test    rdx, rdx
0x1004b5d8c  jz      short loc_1004B5D96
0x1004b5d8e  mov     rcx, rdx
0x1004b5d91  add     rax, r10
0x1004b5d94  jmp     short loc_1004B5D80
0x1004b5d96  test    rcx, rcx
0x1004b5d99  jz      short loc_1004B5DD2
0x1004b5d9b  movzx   eax, word ptr [rcx+26h]
0x1004b5d9f  cmp     rax, r8
0x1004b5da2  jnz     short loc_1004B5DD2
0x1004b5da4  movzx   edi, word ptr [rcx+20h]
0x1004b5da8  movzx   eax, di
0x1004b5dab  mov     r12d, 2
0x1004b5db1  cmp     [rsi+14h], eax
0x1004b5db4  jbe     short loc_1004B5DFB
0x1004b5db6  or      r14, 0FFFFFFFFFFFFFFFFh
0x1004b5dba  movzx   ebx, r14w
0x1004b5dbe  test    byte ptr cs:_bidGblFlags, r12b
0x1004b5dc5  jz      loc_1004B81F8
0x1004b5dcb  mov     edx, 70C009h
0x1004b5dd0  jmp     short loc_1004B5DEF
0x1004b5dd2  or      r14, 0FFFFFFFFFFFFFFFFh
0x1004b5dd6  mov     ebx, r14d
0x1004b5dd9  lea     r12d, [r14+3]
0x1004b5ddd  test    byte ptr cs:_bidGblFlags, r12b
0x1004b5de4  jz      loc_1004B81F8
0x1004b5dea  mov     edx, 709C09h
0x1004b5def  xor     ecx, ecx
0x1004b5df1  call    _bidTraceMark
0x1004b5df6  jmp     loc_1004B81F8
0x1004b5dfb  mov     r11d, r9d
0x1004b5dfe  mov     [rsp+64h], r9d
0x1004b5e03  mov     [rbp+590h+var_558], 4
0x1004b5e0b  cmp     [rsi+14h], r9d
0x1004b5e0f  jbe     loc_1004B7F5E
0x1004b5e15  mov     eax, r11d
0x1004b5e18  imul    rdi, rax, 1C0h
0x1004b5e1f  add     rdi, [rsi]
0x1004b5e22  mov     [rbp+590h+var_5F0], rdi
0x1004b5e26  movzx   eax, word ptr [rdi+30h]
0x1004b5e2a  mov     [rbp+590h+var_5F8], ax
0x1004b5e2e  add     r11w, r10w
0x1004b5e32  mov     [rsp+690h+var_630], r11w
0x1004b5e38  mov     dword ptr [rbp+590h+var_5D8], r9d
0x1004b5e3c  test    ax, ax
0x1004b5e3f  jz      loc_1004B7F47
0x1004b5e45  imul    rcx, rax, 268h
0x1004b5e4c  mov     rdx, [rsi+8]
0x1004b5e50  add     rcx, 0FFFFFFFFFFFFFD98h
0x1004b5e57  add     rdx, rcx
0x1004b5e5a  mov     [rbp+590h+var_5D0], rdx
0x1004b5e5e  mov     rax, [rsi+6C0h]
0x1004b5e65  mov     [rbp+590h+var_540], rax
0x1004b5e69  mov     [rbp+590h+var_5A0], r9d
0x1004b5e6d  mov     [rbp+590h+var_588], r9
0x1004b5e71  mov     [rbp+590h+var_5C0], r9
0x1004b5e75  mov     rcx, r9
0x1004b5e78  mov     [rsp+690h+var_618], rcx
0x1004b5e7d  mov     [rsp+690h+var_620], r9
0x1004b5e82  mov     [rbp+590h+var_5C4], r9d
0x1004b5e86  mov     dword ptr [rbp+590h+var_5E0], r9d
0x1004b5e8a  mov     r10b, [rdx+24h]
0x1004b5e8e  mov     byte ptr [rsp+690h+var_628], r10b
0x1004b5e93  mov     r8b, r10b
0x1004b5e96  mov     [rbp+590h+var_610], r10b
0x1004b5e9a  mov     r12b, [rdi+64h]
0x1004b5e9e  cmp     r10b, 62h ; 'b'
0x1004b5ea2  jnz     loc_1004B660D
0x1004b5ea8  xor     eax, eax
0x1004b5eaa  mov     [rbp+590h+var_450], rax
0x1004b5eb1  mov     [rbp+590h+var_448], al
0x1004b5eb7  mov     r15, [rdx+30h]
0x1004b5ebb  mov     [rbp+590h+var_580], r15
0x1004b5ebf  mov     rcx, r15
0x1004b5ec2  mov     rax, rdx
0x1004b5ec5  mov     edx, 4
0x1004b5eca  lea     r8d, [rdx+7Ch]
0x1004b5ece  movups  xmm0, xmmword ptr [rax]
0x1004b5ed1  movups  xmmword ptr [rcx], xmm0
0x1004b5ed4  movups  xmm1, xmmword ptr [rax+10h]
0x1004b5ed8  movups  xmmword ptr [rcx+10h], xmm1
0x1004b5edc  movups  xmm0, xmmword ptr [rax+20h]
0x1004b5ee0  movups  xmmword ptr [rcx+20h], xmm0
0x1004b5ee4  movups  xmm1, xmmword ptr [rax+30h]
0x1004b5ee8  movups  xmmword ptr [rcx+30h], xmm1
0x1004b5eec  movups  xmm0, xmmword ptr [rax+40h]
0x1004b5ef0  movups  xmmword ptr [rcx+40h], xmm0
0x1004b5ef4  movups  xmm1, xmmword ptr [rax+50h]
0x1004b5ef8  movups  xmmword ptr [rcx+50h], xmm1
0x1004b5efc  movups  xmm0, xmmword ptr [rax+60h]
0x1004b5f00  movups  xmmword ptr [rcx+60h], xmm0
0x1004b5f04  add     rcx, r8
0x1004b5f07  movups  xmm1, xmmword ptr [rax+70h]
0x1004b5f0b  movups  xmmword ptr [rcx-10h], xmm1
0x1004b5f0f  add     rax, r8
0x1004b5f12  sub     rdx, 1
0x1004b5f16  jnz     short loc_1004B5ECE
0x1004b5f18  movups  xmm0, xmmword ptr [rax]
0x1004b5f1b  movups  xmmword ptr [rcx], xmm0
0x1004b5f1e  movups  xmm1, xmmword ptr [rax+10h]
0x1004b5f22  movups  xmmword ptr [rcx+10h], xmm1
0x1004b5f26  movups  xmm0, xmmword ptr [rax+20h]
0x1004b5f2a  movups  xmmword ptr [rcx+20h], xmm0
0x1004b5f2e  movups  xmm1, xmmword ptr [rax+30h]
0x1004b5f32  movups  xmmword ptr [rcx+30h], xmm1
0x1004b5f36  movups  xmm0, xmmword ptr [rax+40h]
0x1004b5f3a  movups  xmmword ptr [rcx+40h], xmm0
0x1004b5f3e  movups  xmm1, xmmword ptr [rax+50h]
0x1004b5f42  movups  xmmword ptr [rcx+50h], xmm1
0x1004b5f46  mov     rax, [rax+60h]
0x1004b5f4a  mov     [rcx+60h], rax
0x1004b5f4e  mov     [r15+38h], r9d
0x1004b5f52  mov     [r15+30h], r9
0x1004b5f56  cmp     r12b, 62h ; 'b'
0x1004b5f5a  jnz     loc_1004B607C
0x1004b5f60  mov     rsi, [rdi+90h]
0x1004b5f67  test    rsi, rsi
0x1004b5f6a  jnz     short loc_1004B5F93
0x1004b5f6c  mov     edx, 1C0h; dwBytes
0x1004b5f71  lea     r8d, [rsi+1]; int
0x1004b5f75  mov     rcx, r13; struct tagOBJBASE *
0x1004b5f78  call    ?SQLAllocateMemoryEx@@YAPEAXPEAUtagOBJBASE@@_KH@Z; SQLAllocateMemoryEx(tagOBJBASE *,unsigned __int64,int)
0x1004b5f7d  mov     rsi, rax
0x1004b5f80  mov     [rdi+90h], rax
0x1004b5f87  xor     r9d, r9d
0x1004b5f8a  test    rax, rax
0x1004b5f8d  jz      loc_1004B7FBA
0x1004b5f93  cmp     [rsi+78h], r9
0x1004b5f97  jbe     short loc_1004B5FBD
0x1004b5f99  mov     rdx, [rsi+48h]
0x1004b5f9d  test    rdx, rdx
0x1004b5fa0  jz      short loc_1004B5FBD
0x1004b5fa2  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x1004b5fa9  mov     rax, [rcx]
0x1004b5fac  mov     rax, [rax+28h]
0x1004b5fb0  call    cs:__guard_dispatch_icall_fptr
0x1004b5fb6  xor     r9d, r9d
0x1004b5fb9  mov     [rsi+48h], r9
0x1004b5fbd  mov     rdx, [rsi+68h]
0x1004b5fc1  test    rdx, rdx
0x1004b5fc4  jz      short loc_1004B5FE7
0x1004b5fc6  cmp     rdx, [rdi+68h]
0x1004b5fca  jz      short loc_1004B5FE7
0x1004b5fcc  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x1004b5fd3  mov     rax, [rcx]
0x1004b5fd6  mov     rax, [rax+28h]
0x1004b5fda  call    cs:__guard_dispatch_icall_fptr
0x1004b5fe0  xor     r9d, r9d
0x1004b5fe3  mov     [rsi+68h], r9
0x1004b5fe7  mov     rax, rsi
0x1004b5fea  mov     rcx, rdi
0x1004b5fed  mov     edx, 3
0x1004b5ff2  lea     r8d, [rdx+7Dh]
0x1004b5ff6  movups  xmm0, xmmword ptr [rcx]
0x1004b5ff9  movups  xmmword ptr [rax], xmm0
0x1004b5ffc  movups  xmm1, xmmword ptr [rcx+10h]
0x1004b6000  movups  xmmword ptr [rax+10h], xmm1
0x1004b6004  movups  xmm0, xmmword ptr [rcx+20h]
0x1004b6008  movups  xmmword ptr [rax+20h], xmm0
0x1004b600c  movups  xmm1, xmmword ptr [rcx+30h]
0x1004b6010  movups  xmmword ptr [rax+30h], xmm1
0x1004b6014  movups  xmm0, xmmword ptr [rcx+40h]
0x1004b6018  movups  xmmword ptr [rax+40h], xmm0
0x1004b601c  movups  xmm1, xmmword ptr [rcx+50h]
0x1004b6020  movups  xmmword ptr [rax+50h], xmm1
0x1004b6024  movups  xmm0, xmmword ptr [rcx+60h]
0x1004b6028  movups  xmmword ptr [rax+60h], xmm0
0x1004b602c  add     rax, r8
0x1004b602f  movups  xmm1, xmmword ptr [rcx+70h]
0x1004b6033  movups  xmmword ptr [rax-10h], xmm1
0x1004b6037  add     rcx, r8
0x1004b603a  sub     rdx, 1
0x1004b603e  jnz     short loc_1004B5FF6
0x1004b6040  movups  xmm0, xmmword ptr [rcx]
0x1004b6043  movups  xmmword ptr [rax], xmm0
0x1004b6046  movups  xmm1, xmmword ptr [rcx+10h]
0x1004b604a  movups  xmmword ptr [rax+10h], xmm1
0x1004b604e  movups  xmm0, xmmword ptr [rcx+20h]
0x1004b6052  movups  xmmword ptr [rax+20h], xmm0
0x1004b6056  movups  xmm1, xmmword ptr [rcx+30h]
0x1004b605a  movups  xmmword ptr [rax+30h], xmm1
0x1004b605e  mov     [rsi+68h], r9
0x1004b6062  mov     [rsi+70h], r9d
0x1004b6066  mov     [rsi+98h], r9d
0x1004b606d  mov     [rsi+90h], r9
0x1004b6074  movzx   r11d, [rsp+690h+var_630]
0x1004b607a  jmp     short loc_1004B607F
0x1004b607c  mov     rsi, rdi
0x1004b607f  movzx   edx, r11w; unsigned int
0x1004b6083  mov     r14, [r13+60h]
0x1004b6087  lea     rcx, [r14+38h]; this
0x1004b608b  call    ?GetColInfoByOrdinal@IRDTag@@QEAAPEAUtagCOLUMN_INFO@@K@Z; IRDTag::GetColInfoByOrdinal(ulong)
0x1004b6090  mov     rdi, rax
0x1004b6093  mov     r8, 0FFFFFFFFFFFFFFFEh; __int16
0x1004b609a  cmp     [rax+0A0h], r8w
0x1004b60a2  jnz     short loc_1004B60F9
0x1004b60a4  xor     eax, eax
0x1004b60a6  mov     [rsp+50h], eax
0x1004b60aa  mov     [rsp+690h+var_648], eax
0x1004b60ae  or      [rsp+690h+var_650], 0FFFFFFFFh
0x1004b60b3  movzx   edx, [rsp+690h+var_630]
0x1004b60b8  mov     word ptr [rsp+690h+var_658], dx
0x1004b60bd  mov     [rsp+690h+var_660], r8w
0x1004b60c3  lea     rax, [rsp+690h+var_620]
0x1004b60c8  mov     [rsp+690h+var_668], rax
0x1004b60cd  lea     rax, [rsp+690h+var_618]
0x1004b60d2  mov     [rsp+690h+var_670], rax
0x1004b60d7  xor     r9d, r9d
0x1004b60da  lea     r8, [rbp+590h+var_440]
0x1004b60e1  mov     rdx, rdi
0x1004b60e4  mov     rcx, r14
0x1004b60e7  mov     rax, [rdi+0B8h]
0x1004b60ee  call    cs:__guard_dispatch_icall_fptr
0x1004b60f4  jmp     loc_1004B634C
0x1004b60f9  xorps   xmm0, xmm0
0x1004b60fc  movups  xmmword ptr [rax+0A0h], xmm0
0x1004b6103  movups  xmmword ptr [rax+0B0h], xmm0
0x1004b610a  movsx   ecx, word ptr [rax+10h]
0x1004b610e  cmp     ecx, 0Dh
0x1004b6111  jnz     short loc_1004B6187
0x1004b6113  mov     r9, rdi; struct tagCOLUMN_INFO *
0x1004b6116  or      r8d, 0FFFFFFFFh; unsigned int
0x1004b611a  movzx   edx, [rsp+690h+var_630]; unsigned __int16
0x1004b611f  mov     rcx, r14; struct tagSTMT *
0x1004b6122  call    ?GetVariantBaseTypeInfo@@YAJPEAUtagSTMT@@GKPEAUtagCOLUMN_INFO@@@Z; GetVariantBaseTypeInfo(tagSTMT *,ushort,ulong,tagCOLUMN_INFO *)
0x1004b6127  test    eax, eax
0x1004b6129  jz      short loc_1004B613E
0x1004b612b  mov     r8d, eax
0x1004b612e  or      edx, 0FFFFFFFFh
0x1004b6131  mov     rcx, r14
0x1004b6134  call    ?HandleError@?$ColDataRetriever@VFixedLengthOutput@@$0A@$00@@CAFPEAUtagSTMT@@KJ@Z; ColDataRetriever<FixedLengthOutput,0,1>::HandleError(tagSTMT *,ulong,long)
  ... truncated ...
```
