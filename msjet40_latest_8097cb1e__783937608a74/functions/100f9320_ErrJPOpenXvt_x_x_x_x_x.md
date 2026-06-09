# ErrJPOpenXvt(x,x,x,x,x)

- ea: `0x100f9320`
- end: `0x100f9ea0`
- name: `_ErrJPOpenXvt@20`
- size: `2944`
- prototype: `int __stdcall(void *, _DWORD *, _DWORD *, int, int)`
- caller_count: `0`
- callee_count: `25`
- tags: `installer_update`

## callees

- `0x1003ea00`
- `0x10043890`
- `0x100439d0`
- `0x100443d0`
- `0x10044a70`
- `0x100450d0`
- `0x10045280`
- `0x100454a0`
- `0x10050190`
- `0x10088729`
- `0x100a023f`
- `0x100b1e0b`
- `0x100b767a`
- `0x100b76b2`
- `0x100b779b`
- `0x100dae00`
- `0x100e88d2`
- `0x100f6ea4`
- `0x100f7025`
- `0x100f8fda`
- `0x100f9320`
- `0x100fa380`
- `0x10121fc0`
- `0x10123110`
- `0x10124078`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x100f9ab5`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x100f9ab5`

## pseudocode

```c
int __stdcall ErrJPOpenXvt(void *a1, _DWORD *a2, _DWORD *a3, int a4, int a5)
{
  _DWORD *v5; // ebx
  int *v6; // edx
  unsigned int v7; // esi
  int v8; // ecx
  int result; // eax
  int v10; // eax
  _DWORD *v11; // ecx
  int v12; // eax
  unsigned int v13; // ecx
  int v14; // eax
  bool v15; // zf
  void *v16; // esi
  _DWORD *v17; // edi
  int TableInfo; // edi
  unsigned int v19; // edi
  unsigned int v20; // eax
  int v21; // esi
  int v22; // eax
  int v23; // edx
  int v24; // eax
  int v25; // eax
  _DWORD *v26; // eax
  int v27; // ecx
  int v28; // edx
  int *v29; // edi
  _DWORD *v30; // ecx
  int v31; // eax
  _DWORD *v32; // edx
  int v33; // ecx
  int v34; // eax
  _DWORD *v35; // ecx
  int v36; // ecx
  _DWORD *v37; // eax
  int v38; // eax
  int v39; // edx
  unsigned int v40; // ecx
  unsigned int v41; // edx
  _DWORD *v42; // ebx
  _DWORD *v43; // edi
  _DWORD *v44; // esi
  _DWORD *v45; // edi
  _DWORD *v46; // esi
  _DWORD *v47; // esi
  _DWORD *v48; // eax
  _DWORD *v49; // esi
  _DWORD *v50; // esi
  int v51; // esi
  int *v52; // eax
  int v53; // edi
  int v54; // ecx
  int v55; // eax
  _DWORD *v56; // ecx
  int v57; // eax
  int v58; // eax
  int v59; // edi
  wchar_t *v60; // esi
  wchar_t j; // cx
  void **v62; // esi
  void *v63; // eax
  _DWORD *v64; // esi
  int v65; // edx
  size_t v66; // eax
  int *v67; // ecx
  int v68; // eax
  int v69; // eax
  int v70; // eax
  int v71; // eax
  int v72; // esi
  _DWORD *v73; // edx
  unsigned int v74; // edi
  _DWORD *v75; // eax
  int *v76; // esi
  void *v77; // ecx
  unsigned int *v78; // edx
  char *v79; // ecx
  int v80; // eax
  _DWORD *v81; // ecx
  int v82; // edx
  int v83; // [esp+8h] [ebp-140h]
  int v84; // [esp+8h] [ebp-140h]
  _DWORD *v85; // [esp+Ch] [ebp-13Ch]
  _DWORD *v86; // [esp+10h] [ebp-138h]
  _DWORD *v87; // [esp+10h] [ebp-138h]
  int v88; // [esp+14h] [ebp-134h]
  int v89; // [esp+14h] [ebp-134h]
  int *lpAddress; // [esp+28h] [ebp-120h]
  int v91; // [esp+2Ch] [ebp-11Ch]
  _DWORD *v92; // [esp+2Ch] [ebp-11Ch]
  int v93; // [esp+30h] [ebp-118h] BYREF
  void *Src; // [esp+34h] [ebp-114h] BYREF
  _DWORD *v95; // [esp+38h] [ebp-110h]
  int v96; // [esp+3Ch] [ebp-10Ch]
  int v97; // [esp+40h] [ebp-108h] BYREF
  int *v98; // [esp+44h] [ebp-104h] BYREF
  int v99; // [esp+48h] [ebp-100h] BYREF
  int v100; // [esp+4Ch] [ebp-FCh]
  unsigned int v101; // [esp+50h] [ebp-F8h]
  _DWORD *v102; // [esp+54h] [ebp-F4h]
  size_t Size; // [esp+58h] [ebp-F0h] BYREF
  int v104; // [esp+5Ch] [ebp-ECh]
  int *v105; // [esp+60h] [ebp-E8h]
  _DWORD *v106; // [esp+64h] [ebp-E4h]
  int v107; // [esp+68h] [ebp-E0h]
  _DWORD *v108; // [esp+6Ch] [ebp-DCh]
  unsigned int v109; // [esp+70h] [ebp-D8h]
  int v110; // [esp+74h] [ebp-D4h]
  _DWORD *v111; // [esp+78h] [ebp-D0h]
  _DWORD *i; // [esp+7Ch] [ebp-CCh]
  _DWORD *v113; // [esp+80h] [ebp-C8h]
  _DWORD *v114; // [esp+84h] [ebp-C4h]
  _DWORD *v115; // [esp+88h] [ebp-C0h]
  _DWORD *v116; // [esp+8Ch] [ebp-BCh]
  char v117[32]; // [esp+90h] [ebp-B8h] BYREF
  int v118; // [esp+B0h] [ebp-98h]
  _WORD v119[70]; // [esp+B8h] [ebp-90h] BYREF

  v5 = a2;
  v6 = (int *)a2[8];
  v7 = a2[13];
  v8 = a2[12];
  v96 = a2[17];
  i = (_DWORD *)a2[15];
  v102 = a2;
  v111 = a3;
  lpAddress = v6;
  v109 = v7;
  v107 = 0;
  v110 = -1;
  v93 = -1;
  v101 = -1;
  if ( !a4 )
  {
    *a3 = -1;
    v15 = a2[19] == 0;
    v98 = a2 + 10;
    if ( v15 )
    {
      v16 = a1;
      v107 = *(_DWORD *)(v8 + 44);
      result = ErrOpenAllGB(a1, v107, 2, (int)(a2 + 10), 8, (int)&v99);
      if ( result < 0 )
        return result;
    }
    else
    {
      v16 = a1;
      v17 = (_DWORD *)(*(_DWORD *)(v8 + 188) + 140);
      a2[10] = -1;
      a2[11] = -1;
      result = ErrJPOpenGB(a1, (int)v17, (int)(a2 + 10), 0, a5);
      if ( result < 0 )
        return result;
      v97 = ErrJPOpenGB(a1, (int)(v17 + 35), (int)(a2 + 11), 0, a5);
      if ( v97 < 0 )
      {
        ((void (__thiscall *)(int, void *, _DWORD *, int))mpjpobjtyppfnErrJPClose[*v17])(
          mpjpobjtyppfnErrJPClose[*v17],
          a1,
          v17,
          *v98);
        result = v97;
        *v98 = -1;
        return result;
      }
    }
    *(_DWORD *)(a2[15] + 340) = -1;
    TableInfo = ErrOpenColumnTT(v16, (int)lpAddress, a2);
    if ( TableInfo < 0 )
      goto LABEL_30;
    TableInfo = ErrJPIOpenJoin(v16, (int)&v93, 0, 0, a5);
    v110 = v93;
    if ( TableInfo < 0 )
      goto LABEL_30;
    v19 = v109;
    ErrUpdateTableid(v93, v109, &vtfndefJPMJoin);
    *(_DWORD *)(v19 + 56) = a2[14];
    *(_DWORD *)(v19 + 64) = a2[10];
    a2[10] = v110;
    if ( !a2[19] )
    {
      v95 = (_DWORD *)a2[14];
      v108 = (_DWORD *)lpAddress[24];
      v100 = *(_DWORD *)(v107 + 1276);
      TableInfo = ErrDispGetTableInfo(v16, i[10], v117, 40, 0);
      if ( TableInfo < 0 )
      {
LABEL_30:
        v21 = v96;
        if ( *(_DWORD *)(v96 + 340) != -1 )
        {
          ReleaseTableid(*(_DWORD *)(v96 + 340));
          *(_DWORD *)(v21 + 340) = -1;
        }
        if ( *(_DWORD *)(v5[15] + 340) != -1 )
        {
          ReleaseTableid(*(_DWORD *)(v5[15] + 340));
          *(_DWORD *)(v5[15] + 340) = -1;
        }
        v22 = v5[15];
        if ( *(_DWORD *)(v22 + 40) != -1 )
        {
          ErrDispCloseTable(a1, *(_DWORD *)(v22 + 40));
          *(_DWORD *)(v5[15] + 40) = -1;
          --*(_DWORD *)(v5[15] + 280);
          v5[14] = -1;
        }
        v23 = v5[10];
        if ( v23 == v110 )
        {
          v23 = *(_DWORD *)(v109 + 64);
          v5[10] = v23;
        }
        v24 = v5[12];
        if ( v5[19] )
        {
          ((void (__thiscall *)(int, void *, int, int))mpjpobjtyppfnErrJPClose[*(_DWORD *)(*(_DWORD *)(v24 + 188) + 140)])(
            mpjpobjtyppfnErrJPClose[*(_DWORD *)(*(_DWORD *)(v24 + 188) + 140)],
            a1,
            *(_DWORD *)(v24 + 188) + 140,
            v23);
          v25 = v5[12];
          v5[10] = -1;
          v26 = (_DWORD *)(*(_DWORD *)(v25 + 188) + 280);
        }
        else
        {
          ((void (__thiscall *)(int, void *, _DWORD, int))mpjpobjtyppfnErrJPClose[**(_DWORD **)(v24 + 44)])(
            mpjpobjtyppfnErrJPClose[**(_DWORD **)(v24 + 44)],
            a1,
            *(_DWORD *)(v24 + 44),
            v23);
          v80 = v5[12];
          v5[10] = -1;
          v26 = (_DWORD *)(*(_DWORD *)(v80 + 44) + 1224);
        }
        ((void (__thiscall *)(int, void *, _DWORD *, _DWORD))mpjpobjtyppfnErrJPClose[*v26])(
          mpjpobjtyppfnErrJPClose[*v26],
          a1,
          v26,
          v5[11]);
        v81 = (_DWORD *)v109;
        v5[11] = -1;
        v82 = v110;
        v81[14] = -1;
        v81[16] = -1;
        if ( v82 != -1 )
          ((void (__thiscall *)(int, void *, _DWORD *, int))mpjpobjtyppfnErrJPClose[*v81])(
            mpjpobjtyppfnErrJPClose[*v81],
            a1,
            v81,
            v82);
        *v111 = -1;
        return TableInfo;
      }
      v20 = v118 + v100;
      v100 = v20;
      if ( v20 > 0xFF )
      {
        UtilSetErrorInfoReal((int)v16, 0, 0, 0, -8151, v20, 0, 0);
LABEL_29:
        TableInfo = -1040;
        goto LABEL_30;
      }
      v91 = 16 * v20;
      TableInfo = ErrCallocPvHsegREAL(lpAddress, 16 * v20, 0, &v98);
      if ( TableInfo < 0 )
        goto LABEL_30;
      v27 = v96;
      v28 = v100;
      v29 = v98;
      *(_DWORD *)(v96 + 288) = (__int16)v100;
      v93 = (int)&v29[v91 / 4u];
      *(_DWORD *)(v27 + 296) = v29;
      v105 = v29;
      TableInfo = ErrCallocPvHsegREAL(lpAddress, 56 * v28, 0, v27 + 312);
      if ( TableInfo < 0 )
        goto LABEL_30;
      v30 = v108;
      *(_DWORD *)(v96 + 332) = a2;
      v31 = v100;
      v30[13] = v100;
      TableInfo = ErrCallocPvHsegREAL(lpAddress, 20 * v31, 0, &v98);
      if ( TableInfo < 0 )
        goto LABEL_30;
      v108[12] = v98;
      TableInfo = ErrCallocPvHsegREAL(lpAddress, v91, 0, &v97);
      if ( TableInfo < 0 )
        goto LABEL_30;
      v32 = v108;
      v33 = v97;
      v34 = v100;
      v104 = v97;
      v108[16] = v97;
      v35 = (_DWORD *)(v33 + 4 * v34);
      v32[17] = v35;
      v106 = v35;
      v36 = (int)&v35[v34];
      v37 = (_DWORD *)(v36 + 4 * v34);
      v32[18] = v36;
      v32[19] = v37;
      v116 = v37;
      v99 = v36;
      TableInfo = ErrCallocPvHsegREAL(lpAddress, v91, 0, &v97);
      if ( TableInfo < 0 )
        goto LABEL_30;
      v92 = (_DWORD *)v97;
      v108[20] = v97;
      v38 = v107;
      v39 = 20 * *(_DWORD *)(v107 + 1276);
      v113 = *(_DWORD **)(v107 + 1288);
      v114 = *(_DWORD **)(v107 + 1292);
      v115 = *(_DWORD **)(v107 + 1296);
      Src = *(void **)(v107 + 1300);
      v97 = *(_DWORD *)(v107 + 1304);
      v40 = *(_DWORD *)(v107 + 1272);
      v41 = v40 + v39;
      if ( v40 < v41 )
      {
        v42 = (_DWORD *)v99;
        do
        {
          v43 = (_DWORD *)v104;
          v104 += 4;
          v44 = v113 + 1;
          *v43 = *v113;
          v45 = v106;
          v113 = v44;
          v46 = v114;
          *v106 = *v114;
          v106 = v45 + 1;
          v114 = v46 + 1;
          v47 = v115 + 1;
          *v42++ = *v115;
          v48 = Src;
          Src = (char *)Src + 4;
          v115 = v47;
          v49 = v116;
          *v116 = *v48;
          v116 = v49 + 1;
          v50 = (_DWORD *)v97;
          v97 += 16;
          *v92 = *v50++;
          v92[1] = *v50++;
          v92[2] = *v50;
          v92[3] = v50[1];
          if ( *(_DWORD *)(v40 + 4) == 16 )
            v51 = v92[3];
          else
            v51 = v92[1];
          v52 = v105;
          v92 += 4;
          v105 += 4;
          v53 = *(_DWORD *)(v40 + 4);
          v40 += 20;
          *v52 = v53;
          v52[1] = v51;
          v52[2] = 0;
        }
        while ( v40 < v41 );
        v5 = v102;
        v16 = a1;
        v38 = v107;
      }
      if ( (unsigned int)v105 < v93 )
      {
        v54 = *(_DWORD *)(v38 + 80);
        v55 = *(_DWORD *)(v38 + 48);
        v102 = (_DWORD *)(v54 + 16);
        v99 = *(_DWORD *)(v55 + 24);
        v56 = (_DWORD *)i[74];
        for ( i = v56; ; v56 = i )
        {
          Src = v119;
          v57 = ErrDispRetrieveColumn(v16, v95, v56[3], v119, 128, &Size, 0, 0);
          TableInfo = v57;
          if ( v57 < 0 )
            goto LABEL_30;
          if ( v57 == 1006 )
          {
            Size = 128;
          }
          else if ( v57 == 1004 )
          {
            goto LABEL_66;
          }
          if ( *i != 10 )
          {
            v58 = ErrQJetConvType(lpAddress[11], v119, 128, &Size, *i, 10, 1, 0);
            TableInfo = v58;
            if ( v58 )
            {
              if ( v58 > 0 || v58 < -32760 )
              {
                if ( v58 == 13 )
                  v58 = 0;
                v88 = v58;
                v69 = -8239;
                if ( TableInfo != 13 )
                  v69 = -8084;
                UtilSetErrorInfoReal((int)v16, 0, 0, 0, v69, 0, 0, v88);
                TableInfo = -3030;
              }
              goto LABEL_30;
            }
          }
          v59 = CchStripSurroundingSpaces(&Src);
          if ( !v59 )
          {
LABEL_66:
            v59 = 3;
            v119[0] = 60;
            v119[1] = 62;
            v119[2] = 0;
            goto LABEL_67;
          }
          v60 = (wchar_t *)Src;
          *((_WORD *)Src + v59) = 0;
          for ( j = *v60; *v60; j = *v60 )
          {
            if ( _wcschr(L".![]", j) )
              *v60 = 95;
            ++v60;
          }
LABEL_67:
          v62 = (void **)v104;
          Size = 2 * v59 + 2;
          TableInfo = ErrAllocPvHsegREAL(lpAddress, 0, v104);
          if ( TableInfo < 0 )
            goto LABEL_30;
          memcpy(*v62, Src, Size);
          v63 = *v62;
          v64 = v102;
          v65 = v99;
          *v106 = v63;
          *v92 = *v64++;
          v92[1] = *v64++;
          v92[2] = *v64;
          v92[3] = v64[1];
          v66 = v65 == 16 ? v92[3] : v92[1];
          v67 = v105;
          v16 = a1;
          v85 = v95;
          Size = v66;
          *v105 = v65;
          v67[1] = v66;
          v67[2] = 0;
          v68 = ErrDispMove2(a1, v85, 1, 0);
          TableInfo = v68;
          if ( v68 < 0 && v68 != -1603 )
            goto LABEL_30;
          v104 += 4;
          ++v106;
          v92 += 4;
          v105 += 4;
          if ( (unsigned int)v105 >= v93 )
            break;
        }
      }
      v70 = ErrDispMove2(v16, v95, 0x80000000, 0);
      TableInfo = v70;
      if ( v70 < 0 && v70 != -1603 )
        goto LABEL_30;
      v89 = *(_DWORD *)(v96 + 284);
      v99 = *(_DWORD *)(v96 + 296);
      v71 = ErrOldOpenTempTable((int)v16, v100, v99, lpAddress[8], v89);
      TableInfo = v71;
      if ( v71 == -1040 || v71 == -1041 || v71 == -1042 || v71 == -1026 )
      {
        UtilSetErrorInfoReal((int)v16, 0, 0, 0, -8151, v100, 0, 0);
        goto LABEL_29;
      }
      if ( v71 < 0 )
        goto LABEL_30;
      ErrDispCloseTable(v16, v101);
      v72 = v107;
      v101 = *(_DWORD *)(v107 + 1272);
      v102 = (_DWORD *)(*(_DWORD *)(v107 + 48) + 20);
      TableInfo = ErrReallocPvHsegREAL(lpAddress, 20 * (*(_DWORD *)(v107 + 1276) + 1));
      if ( TableInfo < 0 )
        goto LABEL_30;
      v73 = (_DWORD *)v96;
      v74 = v101;
      *(_DWORD *)(v96 + 324) = v101;
      v73[80] = *(_DWORD *)(v72 + 1276) + 1;
      v75 = v108;
      v101 = 20 * *(_DWORD *)(v72 + 1276) + v74;
      qmemcpy((void *)v101, v102, 0x14u);
      v76 = (int *)v99;
      v75[11] = 2;
      v77 = (void *)v73[78];
      v95 = (_DWORD *)v73[81];
      while ( 1 )
      {
        Src = v77;
        if ( (unsigned int)v76 >= v93 )
          break;
        TableInfo = ErrSetValcolSortinfo(v73, v76);
        if ( TableInfo < 0 )
          goto LABEL_30;
        v78 = (unsigned int *)v98;
        v98[1] = *v76;
        if ( *v76 == 12 || *v76 == 11 )
        {
          v79 = (char *)Src;
          *((_DWORD *)Src + 12) = *(_DWORD *)(v95[4] + 48);
        }
        else
        {
          v79 = (char *)Src;
        }
        if ( (unsigned int)v95 < v101 )
          v95 += 5;
        v76 += 4;
        *v78 = *v78 & 0xFFFFFE00 | 2;
        v78[4] = (unsigned int)v79;
        v77 = v79 + 56;
        v98 = (int *)(v78 + 5);
        v73 = (_DWORD *)v96;
      }
      v16 = a1;
      v73[83] = v5;
    }
    TableInfo = ErrAllocateTableid(&vtfndefJPXvt);
    if ( TableInfo >= 0 )
    {
      v84 = v96;
      *(_DWORD *)(v96 + 284) = 8;
      v102 = v5 + 16;
      TableInfo = ErrJPOpenSort(v16, v84, (int)(v5 + 16), 0, a5);
      if ( TableInfo >= 0 )
      {
        v10 = *v102;
        goto LABEL_8;
      }
    }
    goto LABEL_30;
  }
  if ( !a2[19] )
    return -1001;
  v83 = *(_DWORD *)(v8 + 188) + 280;
  v95 = (_DWORD *)(v7 + 64);
  v93 = ErrJPOpenGB(a1, v83, v7 + 64, a4, a5);
  if ( v93 >= 0 )
  {
    v93 = ErrDispMove2(a1, a2[14], 0x80000000, 0);
    if ( v93 >= 0 )
    {
      ErrJPIOpenMJoin(a2 + 10, 0, a4, a5);
      v93 = ErrJPOpenSort(a1, v96, (int)(a2 + 16), a4, a5);
      if ( v93 >= 0 )
      {
        v10 = a2[16];
LABEL_8:
        *v111 = v10;
        return 0;
      }
    }
  }
  if ( a2[16] != -1 )
  {
    ReleaseTableid(*(_DWORD *)(a2[17] + 340));
    *(_DWORD *)(a2[17] + 340) = -1;
    ((void (__thiscall *)(int, void *, _DWORD, _DWORD))mpjpobjtyppfnErrJPClose[*(_DWORD *)a2[17]])(
      mpjpobjtyppfnErrJPClose[*(_DWORD *)a2[17]],
      a1,
      a2[17],
      a2[16]);
    v11 = v111;
    a2[16] = -1;
    *v11 = -1;
  }
  if ( *v95 != -1 )
  {
    v86 = (_DWORD *)(*(_DWORD *)(a2[12] + 188) + 140);
    ((void (__thiscall *)(int, void *, _DWORD *, _DWORD))mpjpobjtyppfnErrJPClose[*v86])(
      mpjpobjtyppfnErrJPClose[*v86],
      a1,
      v86,
      *v95);
    *v95 = -1;
    v87 = (_DWORD *)(*(_DWORD *)(a2[12] + 188) + 280);
    ((void (__thiscall *)(int, void *, _DWORD *, _DWORD))mpjpobjtyppfnErrJPClose[*v87])(
      mpjpobjtyppfnErrJPClose[*v87],
      a1,
      v87,
      a2[11]);
    a2[11] = -1;
  }
  v12 = a2[15];
  if ( *(_DWORD *)(v12 + 40) != -1 )
  {
    ErrDispCloseTable(a1, *(_DWORD *)(v12 + 40));
    *(_DWORD *)(a2[15] + 40) = -1;
    --*(_DWORD *)(a2[15] + 280);
    a2[14] = -1;
  }
  if ( a2[10] != -1 )
  {
    v13 = v109;
    v14 = *(_DWORD *)v109;
    *(_DWORD *)(v109 + 56) = -1;
    ((void (__thiscall *)(int, void *, unsigned int, _DWORD))mpjpobjtyppfnErrJPClose[v14])(
      mpjpobjtyppfnErrJPClose[v14],
      a1,
      v13,
      a2[10]);
    a2[10] = -1;
  }
  *v111 = -1;
  return v93;
}

```

## disassembly

```asm
0x100f9320  mov     edi, edi
0x100f9322  push    ebp
0x100f9323  mov     ebp, esp
0x100f9325  and     esp, 0FFFFFFF8h
0x100f9328  sub     esp, 124h
0x100f932e  mov     eax, ___security_cookie
0x100f9333  xor     eax, esp
0x100f9335  mov     [esp+124h+var_4], eax
0x100f933c  push    ebx
0x100f933d  mov     ebx, [ebp+arg_4]
0x100f9340  push    esi
0x100f9341  push    edi
0x100f9342  mov     edi, [ebp+arg_8]
0x100f9345  mov     eax, [ebx+44h]
0x100f9348  mov     edx, [ebx+20h]
0x100f934b  mov     esi, [ebx+34h]
0x100f934e  mov     ecx, [ebx+30h]
0x100f9351  mov     [esp+130h+var_10C], eax
0x100f9355  mov     eax, [ebx+3Ch]
0x100f9358  mov     [esp+130h+var_CC], eax
0x100f935c  or      eax, 0FFFFFFFFh
0x100f935f  cmp     [ebp+arg_C], 0
0x100f9363  mov     [esp+130h+var_F4], ebx
0x100f9367  mov     [esp+130h+var_D0], edi
0x100f936b  mov     [esp+130h+lpAddress], edx
0x100f936f  mov     [esp+130h+var_D8], esi
0x100f9373  mov     [esp+130h+var_E0], 0
0x100f937b  mov     [esp+130h+var_D4], eax
0x100f937f  mov     [esp+130h+var_118], eax
0x100f9383  mov     [esp+130h+var_F8], 0FFFFFFFFh
0x100f938b  jz      loc_100F952B
0x100f9391  cmp     dword ptr [ebx+4Ch], 0
0x100f9395  jnz     short loc_100F93A1
0x100f9397  mov     eax, 0FFFFFC17h
0x100f939c  jmp     loc_100F9E89
0x100f93a1  push    [ebp+arg_10]; int
0x100f93a4  mov     eax, [ecx+0BCh]
0x100f93aa  lea     ecx, [esi+40h]
0x100f93ad  push    [ebp+arg_C]; int
0x100f93b0  mov     edi, [ebp+arg_0]
0x100f93b3  add     eax, 118h
0x100f93b8  push    ecx; int
0x100f93b9  push    eax; int
0x100f93ba  push    edi; void *
0x100f93bb  mov     [esp+144h+var_110], ecx
0x100f93bf  call    _ErrJPOpenGB@20; ErrJPOpenGB(x,x,x,x,x)
0x100f93c4  mov     [esp+130h+var_118], eax
0x100f93c8  test    eax, eax
0x100f93ca  js      short loc_100F9425
0x100f93cc  push    0
0x100f93ce  push    80000000h
0x100f93d3  push    dword ptr [ebx+38h]
0x100f93d6  push    edi
0x100f93d7  call    _ErrDispMove2@16; ErrDispMove2(x,x,x,x)
0x100f93dc  mov     [esp+130h+var_118], eax
0x100f93e0  test    eax, eax
0x100f93e2  js      short loc_100F9425
0x100f93e4  push    [ebp+arg_10]
0x100f93e7  lea     eax, [ebx+28h]
0x100f93ea  mov     edx, esi
0x100f93ec  push    [ebp+arg_C]
0x100f93ef  mov     ecx, edi
0x100f93f1  push    0
0x100f93f3  push    eax
0x100f93f4  call    _ErrJPIOpenMJoin@24; ErrJPIOpenMJoin(x,x,x,x,x,x)
0x100f93f9  push    [ebp+arg_10]; int
0x100f93fc  mov     eax, [esp+134h+var_10C]
0x100f9400  lea     esi, [ebx+40h]
0x100f9403  push    [ebp+arg_C]; int
0x100f9406  push    esi; int
0x100f9407  push    eax; int
0x100f9408  push    edi; void *
0x100f9409  call    _ErrJPOpenSort@20; ErrJPOpenSort(x,x,x,x,x)
0x100f940e  mov     [esp+130h+var_118], eax
0x100f9412  test    eax, eax
0x100f9414  js      short loc_100F9425
0x100f9416  mov     eax, [esi]
0x100f9418  mov     ecx, [esp+130h+var_D0]
0x100f941c  mov     [ecx], eax
0x100f941e  xor     eax, eax
0x100f9420  jmp     loc_100F9E89
0x100f9425  or      esi, 0FFFFFFFFh
0x100f9428  cmp     [ebx+40h], esi
0x100f942b  jz      short loc_100F946B
0x100f942d  mov     eax, [ebx+44h]
0x100f9430  push    dword ptr [eax+154h]
0x100f9436  call    _ReleaseTableid@4; ReleaseTableid(x)
0x100f943b  mov     eax, [ebx+44h]
0x100f943e  mov     [eax+154h], esi
0x100f9444  mov     eax, [ebx+44h]
0x100f9447  push    dword ptr [ebx+40h]
0x100f944a  push    eax; unsigned int
0x100f944b  mov     ecx, [eax]
0x100f944d  push    edi; void *
0x100f944e  mov     esi, ds:_mpjpobjtyppfnErrJPClose[ecx*4]
0x100f9455  mov     ecx, esi
0x100f9457  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100f945d  call    esi ; _mpjpobjtyppfnErrJPClose
0x100f945f  mov     ecx, [esp+130h+var_D0]
0x100f9463  or      esi, 0FFFFFFFFh
0x100f9466  mov     [ebx+40h], esi
0x100f9469  mov     [ecx], esi
0x100f946b  mov     eax, [esp+130h+var_110]
0x100f946f  mov     edx, [eax]
0x100f9471  cmp     edx, esi
0x100f9473  jz      short loc_100F94CF
0x100f9475  mov     eax, [ebx+30h]
0x100f9478  push    edx
0x100f9479  mov     eax, [eax+0BCh]
0x100f947f  add     eax, 8Ch
0x100f9484  push    eax; unsigned int
0x100f9485  push    edi; void *
0x100f9486  mov     ecx, [eax]
0x100f9488  mov     esi, ds:_mpjpobjtyppfnErrJPClose[ecx*4]
0x100f948f  mov     ecx, esi
0x100f9491  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100f9497  call    esi ; _mpjpobjtyppfnErrJPClose
0x100f9499  mov     eax, [esp+130h+var_110]
0x100f949d  mov     dword ptr [eax], 0FFFFFFFFh
0x100f94a3  mov     eax, [ebx+30h]
0x100f94a6  push    dword ptr [ebx+2Ch]
0x100f94a9  mov     eax, [eax+0BCh]
0x100f94af  add     eax, 118h
0x100f94b4  push    eax; unsigned int
0x100f94b5  push    edi; void *
0x100f94b6  mov     ecx, [eax]
0x100f94b8  mov     esi, ds:_mpjpobjtyppfnErrJPClose[ecx*4]
0x100f94bf  mov     ecx, esi
0x100f94c1  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100f94c7  call    esi ; _mpjpobjtyppfnErrJPClose
0x100f94c9  or      esi, 0FFFFFFFFh
0x100f94cc  mov     [ebx+2Ch], esi
0x100f94cf  mov     eax, [ebx+3Ch]
0x100f94d2  cmp     [eax+28h], esi
0x100f94d5  jz      short loc_100F94F2
0x100f94d7  push    dword ptr [eax+28h]
0x100f94da  push    edi
0x100f94db  call    _ErrDispCloseTable@8; ErrDispCloseTable(x,x)
0x100f94e0  mov     eax, [ebx+3Ch]
0x100f94e3  mov     [eax+28h], esi
0x100f94e6  mov     eax, [ebx+3Ch]
0x100f94e9  dec     dword ptr [eax+118h]
0x100f94ef  mov     [ebx+38h], esi
0x100f94f2  cmp     [ebx+28h], esi
0x100f94f5  jz      short loc_100F951C
0x100f94f7  mov     ecx, [esp+130h+var_D8]
0x100f94fb  mov     eax, [ecx]
0x100f94fd  mov     [ecx+38h], esi
0x100f9500  push    dword ptr [ebx+28h]
0x100f9503  mov     esi, ds:_mpjpobjtyppfnErrJPClose[eax*4]
0x100f950a  push    ecx; unsigned int
0x100f950b  push    edi; void *
0x100f950c  mov     ecx, esi
0x100f950e  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100f9514  call    esi ; _mpjpobjtyppfnErrJPClose
0x100f9516  or      esi, 0FFFFFFFFh
0x100f9519  mov     [ebx+28h], esi
0x100f951c  mov     eax, [esp+130h+var_D0]
0x100f9520  mov     [eax], esi
0x100f9522  mov     eax, [esp+130h+var_118]
0x100f9526  jmp     loc_100F9E89
0x100f952b  mov     dword ptr [edi], 0FFFFFFFFh
0x100f9531  lea     eax, [ebx+28h]
0x100f9534  cmp     dword ptr [ebx+4Ch], 0
0x100f9538  mov     [esp+130h+var_104], eax
0x100f953c  jz      short loc_100F95B7
0x100f953e  push    [ebp+arg_10]; int
0x100f9541  mov     edi, [ecx+0BCh]
0x100f9547  mov     esi, [ebp+arg_0]
0x100f954a  add     edi, 8Ch
0x100f9550  push    0; int
0x100f9552  push    eax; int
0x100f9553  push    edi; int
0x100f9554  push    esi; void *
0x100f9555  mov     dword ptr [eax], 0FFFFFFFFh
0x100f955b  mov     dword ptr [ebx+2Ch], 0FFFFFFFFh
0x100f9562  call    _ErrJPOpenGB@20; ErrJPOpenGB(x,x,x,x,x)
0x100f9567  test    eax, eax
0x100f9569  js      loc_100F9E89
0x100f956f  push    [ebp+arg_10]; int
0x100f9572  lea     eax, [ebx+2Ch]
0x100f9575  push    0; int
0x100f9577  push    eax; int
0x100f9578  lea     eax, [edi+8Ch]
0x100f957e  push    eax; int
0x100f957f  push    esi; void *
0x100f9580  call    _ErrJPOpenGB@20; ErrJPOpenGB(x,x,x,x,x)
0x100f9585  mov     [esp+130h+var_108], eax
0x100f9589  test    eax, eax
0x100f958b  jns     short loc_100F95DB
0x100f958d  mov     ebx, [esp+130h+var_104]
0x100f9591  mov     ecx, [edi]
0x100f9593  push    dword ptr [ebx]
0x100f9595  push    edi; unsigned int
0x100f9596  push    esi; void *
0x100f9597  mov     esi, ds:_mpjpobjtyppfnErrJPClose[ecx*4]
0x100f959e  mov     ecx, esi
0x100f95a0  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100f95a6  call    esi ; _mpjpobjtyppfnErrJPClose
0x100f95a8  mov     eax, [esp+130h+var_108]
0x100f95ac  mov     dword ptr [ebx], 0FFFFFFFFh
0x100f95b2  jmp     loc_100F9E89
0x100f95b7  mov     ecx, [ecx+2Ch]
0x100f95ba  lea     esi, [esp+130h+var_100]
0x100f95be  push    esi; int
0x100f95bf  mov     esi, [ebp+arg_0]
0x100f95c2  push    8; int
0x100f95c4  push    eax; int
0x100f95c5  push    2; int
0x100f95c7  mov     [esp+140h+var_E0], ecx
0x100f95cb  push    ecx; int
0x100f95cc  mov     ecx, esi; void *
0x100f95ce  call    _ErrOpenAllGB@28; ErrOpenAllGB(x,x,x,x,x,x,x)
0x100f95d3  test    eax, eax
0x100f95d5  js      loc_100F9E89
0x100f95db  mov     eax, [ebx+3Ch]
0x100f95de  mov     ecx, esi
0x100f95e0  mov     edx, [esp+130h+lpAddress]
0x100f95e4  push    ebx
0x100f95e5  mov     dword ptr [eax+154h], 0FFFFFFFFh
0x100f95ef  call    _ErrOpenColumnTT@12; ErrOpenColumnTT(x,x,x)
0x100f95f4  mov     edi, eax
0x100f95f6  test    edi, edi
0x100f95f8  js      loc_100F96C5
0x100f95fe  push    [ebp+arg_10]; int
0x100f9601  mov     edx, [esp+134h+var_D8]
0x100f9605  lea     eax, [esp+134h+var_118]
0x100f9609  push    0; int
0x100f960b  push    0; int
0x100f960d  push    eax; int
0x100f960e  mov     ecx, esi; void *
0x100f9610  call    _ErrJPIOpenJoin@24; ErrJPIOpenJoin(x,x,x,x,x,x)
0x100f9615  mov     edi, eax
0x100f9617  mov     eax, [esp+130h+var_118]
0x100f961b  mov     [esp+130h+var_D4], eax
0x100f961f  test    edi, edi
0x100f9621  js      loc_100F96C5
0x100f9627  mov     edi, [esp+130h+var_D8]
0x100f962b  push    offset _vtfndefJPMJoin
0x100f9630  push    edi
0x100f9631  push    eax
0x100f9632  call    _ErrUpdateTableid@12; ErrUpdateTableid(x,x,x)
0x100f9637  mov     eax, [ebx+38h]
0x100f963a  mov     [edi+38h], eax
0x100f963d  mov     eax, [ebx+28h]
0x100f9640  mov     [edi+40h], eax
0x100f9643  mov     eax, [esp+130h+var_D4]
0x100f9647  mov     [ebx+28h], eax
0x100f964a  cmp     dword ptr [ebx+4Ch], 0
0x100f964e  jnz     loc_100F9DB2
0x100f9654  mov     eax, [ebx+38h]
0x100f9657  mov     [esp+130h+var_110], eax
0x100f965b  mov     eax, [esp+130h+lpAddress]
0x100f965f  push    0
0x100f9661  push    28h ; '('
0x100f9663  mov     eax, [eax+60h]
0x100f9666  mov     [esp+138h+var_DC], eax
0x100f966a  mov     eax, [esp+138h+var_E0]
0x100f966e  mov     eax, [eax+4FCh]
0x100f9674  mov     [esp+138h+var_FC], eax
0x100f9678  lea     eax, [esp+138h+var_B8]
0x100f967f  push    eax
0x100f9680  mov     eax, [esp+13Ch+var_CC]
0x100f9684  push    dword ptr [eax+28h]
0x100f9687  push    esi
0x100f9688  call    _ErrDispGetTableInfo@20; ErrDispGetTableInfo(x,x,x,x,x)
0x100f968d  mov     edi, eax
0x100f968f  test    edi, edi
0x100f9691  js      short loc_100F96C5
0x100f9693  mov     eax, [esp+130h+var_FC]
0x100f9697  add     eax, [esp+130h+var_98]
0x100f969e  mov     [esp+130h+var_FC], eax
0x100f96a2  cmp     eax, 0FFh
0x100f96a7  jbe     loc_100F978F
0x100f96ad  xor     ecx, ecx
0x100f96af  push    ecx; int
0x100f96b0  push    ecx; int
0x100f96b1  push    eax; int
0x100f96b2  push    0FFFFE029h; int
0x100f96b7  push    ecx; void *
0x100f96b8  push    ecx; void *
0x100f96b9  push    ecx; Src
0x100f96ba  push    esi; int
0x100f96bb  call    _UtilSetErrorInfoReal@32; UtilSetErrorInfoReal(x,x,x,x,x,x,x,x)
0x100f96c0  mov     edi, 0FFFFFBF0h
0x100f96c5  mov     esi, [esp+130h+var_10C]
0x100f96c9  mov     eax, [esi+154h]
0x100f96cf  cmp     eax, 0FFFFFFFFh
0x100f96d2  jz      short loc_100F96E4
0x100f96d4  push    eax
0x100f96d5  call    _ReleaseTableid@4; ReleaseTableid(x)
0x100f96da  mov     dword ptr [esi+154h], 0FFFFFFFFh
0x100f96e4  mov     eax, [ebx+3Ch]
0x100f96e7  mov     eax, [eax+154h]
0x100f96ed  cmp     eax, 0FFFFFFFFh
0x100f96f0  jz      short loc_100F9705
0x100f96f2  push    eax
0x100f96f3  call    _ReleaseTableid@4; ReleaseTableid(x)
0x100f96f8  mov     eax, [ebx+3Ch]
0x100f96fb  mov     dword ptr [eax+154h], 0FFFFFFFFh
  ... truncated ...
```
