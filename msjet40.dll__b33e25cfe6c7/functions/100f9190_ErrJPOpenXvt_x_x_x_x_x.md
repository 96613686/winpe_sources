# ErrJPOpenXvt(x,x,x,x,x)

- ea: `0x100f9190`
- end: `0x100f9d10`
- name: `_ErrJPOpenXvt@20`
- size: `2944`
- prototype: `int __stdcall(void *, _DWORD *, _DWORD *, int, int)`
- caller_count: `0`
- callee_count: `25`
- tags: `installer_update`

## callees

- `0x1003e870`
- `0x10043700`
- `0x10043840`
- `0x10044250`
- `0x100448f0`
- `0x10044f50`
- `0x10045100`
- `0x10045320`
- `0x10050000`
- `0x10088599`
- `0x100a00af`
- `0x100b1c7c`
- `0x100b74ea`
- `0x100b7522`
- `0x100b760b`
- `0x100dac70`
- `0x100e8742`
- `0x100f6d14`
- `0x100f6e95`
- `0x100f8e4a`
- `0x100f9190`
- `0x100fa1f0`
- `0x10121e10`
- `0x10122f60`
- `0x10123ec8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x100f9925`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x100f9925`

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
  int v97; // [esp+40h] [ebp-108h]
  int *v98; // [esp+44h] [ebp-104h]
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
      TableInfo = ErrCallocPvHsegREAL(lpAddress, 16 * v20, 0);
      if ( TableInfo < 0 )
        goto LABEL_30;
      v27 = v96;
      v28 = v100;
      v29 = v98;
      *(_DWORD *)(v96 + 288) = (__int16)v100;
      v93 = (int)&v29[v91 / 4u];
      *(_DWORD *)(v27 + 296) = v29;
      v105 = v29;
      TableInfo = ErrCallocPvHsegREAL(lpAddress, 56 * v28, 0);
      if ( TableInfo < 0 )
        goto LABEL_30;
      v30 = v108;
      *(_DWORD *)(v96 + 332) = a2;
      v31 = v100;
      v30[13] = v100;
      TableInfo = ErrCallocPvHsegREAL(lpAddress, 20 * v31, 0);
      if ( TableInfo < 0 )
        goto LABEL_30;
      v108[12] = v98;
      TableInfo = ErrCallocPvHsegREAL(lpAddress, v91, 0);
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
      TableInfo = ErrCallocPvHsegREAL(lpAddress, v91, 0);
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
0x100f9190  mov     edi, edi
0x100f9192  push    ebp
0x100f9193  mov     ebp, esp
0x100f9195  and     esp, 0FFFFFFF8h
0x100f9198  sub     esp, 124h
0x100f919e  mov     eax, ___security_cookie
0x100f91a3  xor     eax, esp
0x100f91a5  mov     [esp+124h+var_4], eax
0x100f91ac  push    ebx
0x100f91ad  mov     ebx, [ebp+arg_4]
0x100f91b0  push    esi
0x100f91b1  push    edi
0x100f91b2  mov     edi, [ebp+arg_8]
0x100f91b5  mov     eax, [ebx+44h]
0x100f91b8  mov     edx, [ebx+20h]
0x100f91bb  mov     esi, [ebx+34h]
0x100f91be  mov     ecx, [ebx+30h]
0x100f91c1  mov     [esp+130h+var_10C], eax
0x100f91c5  mov     eax, [ebx+3Ch]
0x100f91c8  mov     [esp+130h+var_CC], eax
0x100f91cc  or      eax, 0FFFFFFFFh
0x100f91cf  cmp     [ebp+arg_C], 0
0x100f91d3  mov     [esp+130h+var_F4], ebx
0x100f91d7  mov     [esp+130h+var_D0], edi
0x100f91db  mov     [esp+130h+lpAddress], edx
0x100f91df  mov     [esp+130h+var_D8], esi
0x100f91e3  mov     [esp+130h+var_E0], 0
0x100f91eb  mov     [esp+130h+var_D4], eax
0x100f91ef  mov     [esp+130h+var_118], eax
0x100f91f3  mov     [esp+130h+var_F8], 0FFFFFFFFh
0x100f91fb  jz      loc_100F939B
0x100f9201  cmp     dword ptr [ebx+4Ch], 0
0x100f9205  jnz     short loc_100F9211
0x100f9207  mov     eax, 0FFFFFC17h
0x100f920c  jmp     loc_100F9CF9
0x100f9211  push    [ebp+arg_10]; int
0x100f9214  mov     eax, [ecx+0BCh]
0x100f921a  lea     ecx, [esi+40h]
0x100f921d  push    [ebp+arg_C]; int
0x100f9220  mov     edi, [ebp+arg_0]
0x100f9223  add     eax, 118h
0x100f9228  push    ecx; int
0x100f9229  push    eax; int
0x100f922a  push    edi; void *
0x100f922b  mov     [esp+144h+var_110], ecx
0x100f922f  call    _ErrJPOpenGB@20; ErrJPOpenGB(x,x,x,x,x)
0x100f9234  mov     [esp+130h+var_118], eax
0x100f9238  test    eax, eax
0x100f923a  js      short loc_100F9295
0x100f923c  push    0
0x100f923e  push    80000000h
0x100f9243  push    dword ptr [ebx+38h]
0x100f9246  push    edi
0x100f9247  call    _ErrDispMove2@16; ErrDispMove2(x,x,x,x)
0x100f924c  mov     [esp+130h+var_118], eax
0x100f9250  test    eax, eax
0x100f9252  js      short loc_100F9295
0x100f9254  push    [ebp+arg_10]
0x100f9257  lea     eax, [ebx+28h]
0x100f925a  mov     edx, esi
0x100f925c  push    [ebp+arg_C]
0x100f925f  mov     ecx, edi
0x100f9261  push    0
0x100f9263  push    eax
0x100f9264  call    _ErrJPIOpenMJoin@24; ErrJPIOpenMJoin(x,x,x,x,x,x)
0x100f9269  push    [ebp+arg_10]; int
0x100f926c  mov     eax, [esp+134h+var_10C]
0x100f9270  lea     esi, [ebx+40h]
0x100f9273  push    [ebp+arg_C]; int
0x100f9276  push    esi; int
0x100f9277  push    eax; int
0x100f9278  push    edi; void *
0x100f9279  call    _ErrJPOpenSort@20; ErrJPOpenSort(x,x,x,x,x)
0x100f927e  mov     [esp+130h+var_118], eax
0x100f9282  test    eax, eax
0x100f9284  js      short loc_100F9295
0x100f9286  mov     eax, [esi]
0x100f9288  mov     ecx, [esp+130h+var_D0]
0x100f928c  mov     [ecx], eax
0x100f928e  xor     eax, eax
0x100f9290  jmp     loc_100F9CF9
0x100f9295  or      esi, 0FFFFFFFFh
0x100f9298  cmp     [ebx+40h], esi
0x100f929b  jz      short loc_100F92DB
0x100f929d  mov     eax, [ebx+44h]
0x100f92a0  push    dword ptr [eax+154h]
0x100f92a6  call    _ReleaseTableid@4; ReleaseTableid(x)
0x100f92ab  mov     eax, [ebx+44h]
0x100f92ae  mov     [eax+154h], esi
0x100f92b4  mov     eax, [ebx+44h]
0x100f92b7  push    dword ptr [ebx+40h]
0x100f92ba  push    eax; unsigned int
0x100f92bb  mov     ecx, [eax]
0x100f92bd  push    edi; void *
0x100f92be  mov     esi, ds:_mpjpobjtyppfnErrJPClose[ecx*4]
0x100f92c5  mov     ecx, esi
0x100f92c7  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100f92cd  call    esi ; _mpjpobjtyppfnErrJPClose
0x100f92cf  mov     ecx, [esp+130h+var_D0]
0x100f92d3  or      esi, 0FFFFFFFFh
0x100f92d6  mov     [ebx+40h], esi
0x100f92d9  mov     [ecx], esi
0x100f92db  mov     eax, [esp+130h+var_110]
0x100f92df  mov     edx, [eax]
0x100f92e1  cmp     edx, esi
0x100f92e3  jz      short loc_100F933F
0x100f92e5  mov     eax, [ebx+30h]
0x100f92e8  push    edx
0x100f92e9  mov     eax, [eax+0BCh]
0x100f92ef  add     eax, 8Ch
0x100f92f4  push    eax; unsigned int
0x100f92f5  push    edi; void *
0x100f92f6  mov     ecx, [eax]
0x100f92f8  mov     esi, ds:_mpjpobjtyppfnErrJPClose[ecx*4]
0x100f92ff  mov     ecx, esi
0x100f9301  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100f9307  call    esi ; _mpjpobjtyppfnErrJPClose
0x100f9309  mov     eax, [esp+130h+var_110]
0x100f930d  mov     dword ptr [eax], 0FFFFFFFFh
0x100f9313  mov     eax, [ebx+30h]
0x100f9316  push    dword ptr [ebx+2Ch]
0x100f9319  mov     eax, [eax+0BCh]
0x100f931f  add     eax, 118h
0x100f9324  push    eax; unsigned int
0x100f9325  push    edi; void *
0x100f9326  mov     ecx, [eax]
0x100f9328  mov     esi, ds:_mpjpobjtyppfnErrJPClose[ecx*4]
0x100f932f  mov     ecx, esi
0x100f9331  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100f9337  call    esi ; _mpjpobjtyppfnErrJPClose
0x100f9339  or      esi, 0FFFFFFFFh
0x100f933c  mov     [ebx+2Ch], esi
0x100f933f  mov     eax, [ebx+3Ch]
0x100f9342  cmp     [eax+28h], esi
0x100f9345  jz      short loc_100F9362
0x100f9347  push    dword ptr [eax+28h]
0x100f934a  push    edi
0x100f934b  call    _ErrDispCloseTable@8; ErrDispCloseTable(x,x)
0x100f9350  mov     eax, [ebx+3Ch]
0x100f9353  mov     [eax+28h], esi
0x100f9356  mov     eax, [ebx+3Ch]
0x100f9359  dec     dword ptr [eax+118h]
0x100f935f  mov     [ebx+38h], esi
0x100f9362  cmp     [ebx+28h], esi
0x100f9365  jz      short loc_100F938C
0x100f9367  mov     ecx, [esp+130h+var_D8]
0x100f936b  mov     eax, [ecx]
0x100f936d  mov     [ecx+38h], esi
0x100f9370  push    dword ptr [ebx+28h]
0x100f9373  mov     esi, ds:_mpjpobjtyppfnErrJPClose[eax*4]
0x100f937a  push    ecx; unsigned int
0x100f937b  push    edi; void *
0x100f937c  mov     ecx, esi
0x100f937e  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100f9384  call    esi ; _mpjpobjtyppfnErrJPClose
0x100f9386  or      esi, 0FFFFFFFFh
0x100f9389  mov     [ebx+28h], esi
0x100f938c  mov     eax, [esp+130h+var_D0]
0x100f9390  mov     [eax], esi
0x100f9392  mov     eax, [esp+130h+var_118]
0x100f9396  jmp     loc_100F9CF9
0x100f939b  mov     dword ptr [edi], 0FFFFFFFFh
0x100f93a1  lea     eax, [ebx+28h]
0x100f93a4  cmp     dword ptr [ebx+4Ch], 0
0x100f93a8  mov     [esp+130h+var_104], eax
0x100f93ac  jz      short loc_100F9427
0x100f93ae  push    [ebp+arg_10]; int
0x100f93b1  mov     edi, [ecx+0BCh]
0x100f93b7  mov     esi, [ebp+arg_0]
0x100f93ba  add     edi, 8Ch
0x100f93c0  push    0; int
0x100f93c2  push    eax; int
0x100f93c3  push    edi; int
0x100f93c4  push    esi; void *
0x100f93c5  mov     dword ptr [eax], 0FFFFFFFFh
0x100f93cb  mov     dword ptr [ebx+2Ch], 0FFFFFFFFh
0x100f93d2  call    _ErrJPOpenGB@20; ErrJPOpenGB(x,x,x,x,x)
0x100f93d7  test    eax, eax
0x100f93d9  js      loc_100F9CF9
0x100f93df  push    [ebp+arg_10]; int
0x100f93e2  lea     eax, [ebx+2Ch]
0x100f93e5  push    0; int
0x100f93e7  push    eax; int
0x100f93e8  lea     eax, [edi+8Ch]
0x100f93ee  push    eax; int
0x100f93ef  push    esi; void *
0x100f93f0  call    _ErrJPOpenGB@20; ErrJPOpenGB(x,x,x,x,x)
0x100f93f5  mov     [esp+130h+var_108], eax
0x100f93f9  test    eax, eax
0x100f93fb  jns     short loc_100F944B
0x100f93fd  mov     ebx, [esp+130h+var_104]
0x100f9401  mov     ecx, [edi]
0x100f9403  push    dword ptr [ebx]
0x100f9405  push    edi; unsigned int
0x100f9406  push    esi; void *
0x100f9407  mov     esi, ds:_mpjpobjtyppfnErrJPClose[ecx*4]
0x100f940e  mov     ecx, esi
0x100f9410  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100f9416  call    esi ; _mpjpobjtyppfnErrJPClose
0x100f9418  mov     eax, [esp+130h+var_108]
0x100f941c  mov     dword ptr [ebx], 0FFFFFFFFh
0x100f9422  jmp     loc_100F9CF9
0x100f9427  mov     ecx, [ecx+2Ch]
0x100f942a  lea     esi, [esp+130h+var_100]
0x100f942e  push    esi; int
0x100f942f  mov     esi, [ebp+arg_0]
0x100f9432  push    8; int
0x100f9434  push    eax; int
0x100f9435  push    2; int
0x100f9437  mov     [esp+140h+var_E0], ecx
0x100f943b  push    ecx; int
0x100f943c  mov     ecx, esi; void *
0x100f943e  call    _ErrOpenAllGB@28; ErrOpenAllGB(x,x,x,x,x,x,x)
0x100f9443  test    eax, eax
0x100f9445  js      loc_100F9CF9
0x100f944b  mov     eax, [ebx+3Ch]
0x100f944e  mov     ecx, esi
0x100f9450  mov     edx, [esp+130h+lpAddress]
0x100f9454  push    ebx
0x100f9455  mov     dword ptr [eax+154h], 0FFFFFFFFh
0x100f945f  call    _ErrOpenColumnTT@12; ErrOpenColumnTT(x,x,x)
0x100f9464  mov     edi, eax
0x100f9466  test    edi, edi
0x100f9468  js      loc_100F9535
0x100f946e  push    [ebp+arg_10]; int
0x100f9471  mov     edx, [esp+134h+var_D8]
0x100f9475  lea     eax, [esp+134h+var_118]
0x100f9479  push    0; int
0x100f947b  push    0; int
0x100f947d  push    eax; int
0x100f947e  mov     ecx, esi; void *
0x100f9480  call    _ErrJPIOpenJoin@24; ErrJPIOpenJoin(x,x,x,x,x,x)
0x100f9485  mov     edi, eax
0x100f9487  mov     eax, [esp+130h+var_118]
0x100f948b  mov     [esp+130h+var_D4], eax
0x100f948f  test    edi, edi
0x100f9491  js      loc_100F9535
0x100f9497  mov     edi, [esp+130h+var_D8]
0x100f949b  push    offset _vtfndefJPMJoin
0x100f94a0  push    edi
0x100f94a1  push    eax
0x100f94a2  call    _ErrUpdateTableid@12; ErrUpdateTableid(x,x,x)
0x100f94a7  mov     eax, [ebx+38h]
0x100f94aa  mov     [edi+38h], eax
0x100f94ad  mov     eax, [ebx+28h]
0x100f94b0  mov     [edi+40h], eax
0x100f94b3  mov     eax, [esp+130h+var_D4]
0x100f94b7  mov     [ebx+28h], eax
0x100f94ba  cmp     dword ptr [ebx+4Ch], 0
0x100f94be  jnz     loc_100F9C22
0x100f94c4  mov     eax, [ebx+38h]
0x100f94c7  mov     [esp+130h+var_110], eax
0x100f94cb  mov     eax, [esp+130h+lpAddress]
0x100f94cf  push    0
0x100f94d1  push    28h ; '('
0x100f94d3  mov     eax, [eax+60h]
0x100f94d6  mov     [esp+138h+var_DC], eax
0x100f94da  mov     eax, [esp+138h+var_E0]
0x100f94de  mov     eax, [eax+4FCh]
0x100f94e4  mov     [esp+138h+var_FC], eax
0x100f94e8  lea     eax, [esp+138h+var_B8]
0x100f94ef  push    eax
0x100f94f0  mov     eax, [esp+13Ch+var_CC]
0x100f94f4  push    dword ptr [eax+28h]
0x100f94f7  push    esi
0x100f94f8  call    _ErrDispGetTableInfo@20; ErrDispGetTableInfo(x,x,x,x,x)
0x100f94fd  mov     edi, eax
0x100f94ff  test    edi, edi
0x100f9501  js      short loc_100F9535
0x100f9503  mov     eax, [esp+130h+var_FC]
0x100f9507  add     eax, [esp+130h+var_98]
0x100f950e  mov     [esp+130h+var_FC], eax
0x100f9512  cmp     eax, 0FFh
0x100f9517  jbe     loc_100F95FF
0x100f951d  xor     ecx, ecx
0x100f951f  push    ecx; int
0x100f9520  push    ecx; int
0x100f9521  push    eax; int
0x100f9522  push    0FFFFE029h; int
0x100f9527  push    ecx; void *
0x100f9528  push    ecx; void *
0x100f9529  push    ecx; Src
0x100f952a  push    esi; int
0x100f952b  call    _UtilSetErrorInfoReal@32; UtilSetErrorInfoReal(x,x,x,x,x,x,x,x)
0x100f9530  mov     edi, 0FFFFFBF0h
0x100f9535  mov     esi, [esp+130h+var_10C]
0x100f9539  mov     eax, [esi+154h]
0x100f953f  cmp     eax, 0FFFFFFFFh
0x100f9542  jz      short loc_100F9554
0x100f9544  push    eax
0x100f9545  call    _ReleaseTableid@4; ReleaseTableid(x)
0x100f954a  mov     dword ptr [esi+154h], 0FFFFFFFFh
0x100f9554  mov     eax, [ebx+3Ch]
0x100f9557  mov     eax, [eax+154h]
0x100f955d  cmp     eax, 0FFFFFFFFh
0x100f9560  jz      short loc_100F9575
0x100f9562  push    eax
0x100f9563  call    _ReleaseTableid@4; ReleaseTableid(x)
0x100f9568  mov     eax, [ebx+3Ch]
0x100f956b  mov     dword ptr [eax+154h], 0FFFFFFFFh
  ... truncated ...
```
