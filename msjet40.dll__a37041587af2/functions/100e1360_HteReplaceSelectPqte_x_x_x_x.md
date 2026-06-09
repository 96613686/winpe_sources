# HteReplaceSelectPqte(x,x,x,x)

- ea: `0x100e1360`
- end: `0x100e1a9b`
- name: `_HteReplaceSelectPqte@16`
- size: `1851`
- prototype: ``
- caller_count: `0`
- callee_count: `21`
- tags: ``

## callees

- `0x100b763b`
- `0x100b7a7e`
- `0x100b7c98`
- `0x100b816c`
- `0x100b84a6`
- `0x100b8507`
- `0x100b860f`
- `0x100b865a`
- `0x100b86cd`
- `0x100bb921`
- `0x100e0989`
- `0x100e0a45`
- `0x100e0cb7`
- `0x100e0f43`
- `0x100e1360`
- `0x100e1afb`
- `0x100e98dc`
- `0x100e9f30`
- `0x100ea657`
- `0x100ea7bf`
- `0x100ebf5f`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!longjmp` at `0x100e154d`
- `api-ms-win-crt-private-l1-1-0!longjmp` at `0x100e154d`

## pseudocode

```c
_DWORD *__stdcall HteReplaceSelectPqte(int a1, int a2, int a3, int a4)
{
  int v4; // esi
  int v5; // ebx
  int v6; // edi
  char v7; // dh
  char *v8; // eax
  char v9; // dl
  _BYTE *v10; // ecx
  int v11; // eax
  int v12; // edx
  char v13; // dl
  int v14; // edx
  char v15; // al
  _DWORD *result; // eax
  unsigned __int8 v17; // cl
  char v18; // al
  int v19; // edx
  char v20; // cl
  _DWORD *v21; // ecx
  bool v22; // zf
  int v23; // eax
  char v24; // al
  _DWORD *v25; // edx
  int v26; // eax
  int v27; // ecx
  int v28; // edx
  _DWORD *v29; // eax
  int v30; // ecx
  char v31; // cl
  int v32; // eax
  int v33; // edi
  int v34; // esi
  int v35; // edx
  char v36; // al
  int Bound; // eax
  char v38; // al
  int v39; // ecx
  int v40; // ecx
  int BinopSpec; // edx
  int v42; // ecx
  int v43; // eax
  _DWORD *v44; // edx
  int v45; // ecx
  int v46; // esi
  int v47; // edi
  char v48; // al
  char v49; // al
  int v50; // [esp+Ch] [ebp-28h]
  int v51; // [esp+10h] [ebp-24h] BYREF
  int v52; // [esp+14h] [ebp-20h] BYREF
  int v53; // [esp+18h] [ebp-1Ch]
  int v54; // [esp+1Ch] [ebp-18h] BYREF
  int v55; // [esp+20h] [ebp-14h]
  _DWORD *v56; // [esp+24h] [ebp-10h]
  int v57; // [esp+28h] [ebp-Ch] BYREF
  int v58; // [esp+2Ch] [ebp-8h]
  _DWORD *v59; // [esp+30h] [ebp-4h] BYREF

  v4 = a2;
  v5 = 0;
  v6 = *(_DWORD *)(a3 + 8);
  v7 = *(_BYTE *)(a2 + 4);
  v56 = *(_DWORD **)(a3 + 4);
  v8 = (char *)(a2 + 5);
  v53 = v6;
  v58 = 0;
  v59 = (_DWORD *)a2;
  v57 = 1;
  v51 = 0;
  if ( v7 == 12 )
  {
    v9 = *v8;
    v10 = (_BYTE *)(a2 + 5);
    if ( !*v8 || v9 == 48 || v9 == 49 || v9 == 47 || v9 == 50 )
      goto LABEL_11;
    goto LABEL_7;
  }
  if ( v7 != 4 )
  {
LABEL_7:
    v10 = (_BYTE *)(a2 + 5);
    if ( v7 != 3 && (v7 != 1 || *v8 != 3 && *v8 != 50) )
      return (_DWORD *)a2;
    goto LABEL_11;
  }
  v10 = (_BYTE *)(a2 + 5);
  if ( *v8 != 5 )
    return (_DWORD *)a2;
LABEL_11:
  if ( v7 == 1 && *v10 == 3 )
  {
    v11 = *(_DWORD *)(a2 + 12);
    if ( *(_BYTE *)(v11 + 4) == 4 && *(_BYTE *)(v11 + 5) == 5 )
    {
      v12 = *(_DWORD *)(v11 + 12);
      v52 = v12;
      if ( *(_BYTE *)(v12 + 4) == 12 )
      {
        v13 = *(_BYTE *)(v12 + 5);
        if ( !v13 || v13 == 48 || v13 == 49 || v13 == 47 || v13 == 50 )
        {
          v14 = v52;
          v6 = v53;
          if ( *(_DWORD *)(v52 + 8) == a3 )
          {
            *(_BYTE *)(v52 + 5) = 49;
            *(_DWORD *)(v11 + 12) = a2;
            *(_WORD *)(v11 + 4) = 2307;
            *(_BYTE *)(a2 + 4) = 1;
            *(_DWORD *)(a2 + 12) = v14;
            v4 = v11;
            *v10 = 49;
            a2 = v11;
            goto LABEL_23;
          }
        }
      }
    }
    return (_DWORD *)a2;
  }
LABEL_23:
  v15 = *(_BYTE *)(v4 + 4);
  if ( v15 != 4 && v15 != 3 )
  {
    if ( v15 == 1 )
    {
      if ( *(_BYTE *)(v4 + 5) != 50 )
        goto LABEL_54;
      v5 = *(_DWORD *)(v4 + 12);
    }
    else
    {
      if ( v15 != 12 )
        goto LABEL_54;
      v5 = v4;
    }
    goto LABEL_53;
  }
  v17 = *(_BYTE *)(v4 + 5);
  v5 = *(_DWORD *)(v4 + 12);
  v58 = v5;
  if ( v17 != 5 || *(_BYTE *)(v5 + 4) != 12 )
  {
    v18 = *(_BYTE *)(v5 + 5);
    if ( v18 != 48 && v18 != 49 && v18 != 47 )
    {
      v19 = *(_DWORD *)(v4 + 8);
      if ( v17 < 7u || v17 >= 0xEu || v17 == 8 || *(_BYTE *)(v19 + 4) != 12 || *(_BYTE *)(v19 + 5) )
        return v59;
      v20 = *(_BYTE *)(v5 + 4);
      if ( v20 == 10 )
      {
        if ( !v18 && *(_BYTE *)(*(_DWORD *)(v5 + 8) + 9) == 6 )
          return v59;
      }
      else if ( v20 == 12 && (!v18 || v18 == 50) )
      {
        return v59;
      }
      SwapPqte();
      return v59;
    }
    v5 = *(_DWORD *)(v5 + 12);
LABEL_53:
    v58 = v5;
  }
LABEL_54:
  if ( *(_DWORD *)(v5 + 8) != a3 )
    return v59;
  v21 = v56;
  v22 = *(_BYTE *)(v5 + 5) == 50;
  v55 = v56[1];
  if ( v22 )
  {
    v23 = v58;
  }
  else
  {
    if ( FFLDLvInPqgref(0) )
    {
      SetErrorInfoPqgref(-8187);
      goto LABEL_58;
    }
    if ( *(_BYTE *)(v4 + 5) == 5 || (v23 = v58, *(_BYTE *)(v58 + 5)) )
    {
      v59 = *(_DWORD **)(v4 + 8);
      v52 = 0;
      v54 = 0;
      TraverseExpn(&v54, &v52, 6, FLDLvVisitPqte);
      if ( v54 )
      {
        QEMSetErrorInfo(v59, -8187, 0, 0);
LABEL_58:
        _longjmp(*(int **)(a1 + 24), -3101);
      }
      v23 = v58;
    }
    v21 = v56;
  }
  v24 = *(_BYTE *)(v23 + 5);
  if ( v24 != 50 )
  {
    if ( v21[2] != 1 )
      _longjmp(*(int **)(a1 + 24), -3063);
    if ( v24 || *(_BYTE *)(v4 + 5) == 5 )
    {
      while ( FPqteHasSelect(&v59) )
      {
        ConsumeSubquery(a1, v59);
        v25 = v59;
        if ( (*(_BYTE *)(v59[2] + 136) & 1) != 0 )
        {
          v26 = *(_DWORD *)(v6 + 152);
          if ( v26 < 8 )
          {
            if ( !v26 )
            {
              CallocPvHsegREAL(a1, 32, 0, v6 + 148);
              v25 = v59;
            }
            v27 = *(_DWORD *)(v6 + 152);
            *(_DWORD *)(v6 + 152) = v27 + 1;
            *(_DWORD *)(*(_DWORD *)(v6 + 148) + 4 * v27) = v25;
            *(_DWORD *)(v59[2] + 136) |= 0x100u;
          }
        }
      }
      HteModifyAllExpn(0, 0, HteMarkDfnsAsConsumed, 0);
      *(_DWORD *)(v6 + 140) = HteCopyPqte(a1);
      TraverseExpn(&v57, 0, 2, IncCrefPqte);
    }
  }
  v28 = a3;
  v29 = *(_DWORD **)(a3 + 4);
  v59 = v29;
  v30 = v29[45];
  if ( (v30 & 0x2000) != 0 )
  {
    if ( v29[55]
      || *v29 != 4 && (*v29 != 2 || (v30 & 0x10) == 0)
      || (v30 & 0x4202) != 0
      || (*(_BYTE *)(a3 + 20) & 0x20) != 0 )
    {
      goto LABEL_90;
    }
    if ( *v29 == 4 || *v29 == 2 && (v30 & 0x10) != 0 )
    {
      if ( (v29[46] & 1) == 0 )
      {
LABEL_90:
        *(_DWORD *)(v6 + 136) |= 2u;
        goto LABEL_95;
      }
      if ( v29[53] )
      {
        v54 = 0;
        HteModifyAllExpn(v29, &v54, HteFHasCorrAggs, 0);
        v29 = v59;
        v28 = a3;
        if ( v54 )
          goto LABEL_90;
      }
      else
      {
        v28 = a3;
      }
    }
  }
LABEL_95:
  v31 = *(_BYTE *)(v58 + 5);
  if ( v31 == 50 )
  {
    *(_DWORD *)(v6 + 128) = 4;
    goto LABEL_140;
  }
  if ( *(_BYTE *)(v4 + 5) == 5 )
  {
    *(_DWORD *)(v6 + 136) |= 1u;
    *(_DWORD *)(v6 + 128) = 2;
    *(_WORD *)(v4 + 4) = 1795;
LABEL_107:
    v22 = v29[55] == 0;
    v52 = 0;
    if ( !v22
      || *v29 != 4 && (*v29 != 2 || (v29[45] & 0x10) == 0)
      || (v29[45] & 0x4202) != 0
      || (*(_BYTE *)(v28 + 20) & 0x20) != 0 )
    {
      *(_DWORD *)(v6 + 136) |= 2u;
    }
    if ( (v29[45] & 0x4000) != 0 )
    {
      SpliceQOAboveTopN(a1);
      v59 = *(_DWORD **)(a3 + 4);
      v56 = v59;
      v32 = v59[1];
      v55 = v32;
    }
    else
    {
      v32 = v55;
    }
    v22 = (*(_BYTE *)(v32 + 40) & 2) == 0;
    v58 = v32 + 4;
    if ( v22 )
    {
      CallocPvHsegREAL(a1, 14, 0, &v54);
      v33 = v54;
      v34 = v58;
      *(_DWORD *)v54 = *(_DWORD *)v58;
      v34 += 4;
      v33 += 4;
      *(_DWORD *)v33 = *(_DWORD *)v34;
      v34 += 4;
      v33 += 4;
      *(_DWORD *)v33 = *(_DWORD *)v34;
      *(_WORD *)(v33 + 4) = *(_WORD *)(v34 + 4);
      IncCrefPqgcol(1);
      v36 = MapColtypVlt(*(unsigned __int8 *)(v35 + 8));
      Bound = PqteCreateBound(v36);
      v58 = Bound;
      if ( !Bound )
        goto LABEL_120;
      v4 = a2;
      v6 = v53;
      *(_DWORD *)(a2 + 12) = Bound;
    }
    else
    {
      *(_DWORD *)(v4 + 12) = HteCopyPqte(a1);
      TraverseExpn(&v57, 0, 2, IncCrefPqte);
      v58 = HteCopyPqte(a1);
      TraverseExpn(&v57, 0, 2, IncCrefPqte);
    }
    v38 = FIgnoreNullChecks(v4);
    *(_DWORD *)(v6 + 136) ^= ((unsigned __int8)*(_DWORD *)(v6 + 136) ^ (unsigned __int8)(v38 << 7)) & 0x80;
    v39 = v58;
    if ( (v38 & 1) != 0 || *(_BYTE *)(v58 + 4) == 7 )
    {
      BinopSpec = v52;
    }
    else
    {
      v52 = PqteNULL(a1);
      if ( !v52 )
        goto LABEL_120;
      v53 = HteCopyPqte(a1);
      if ( !v53 )
        goto LABEL_120;
      TraverseExpn(&v57, 0, 2, IncCrefPqte);
      BinopSpec = PqteCreateBinopSpec(v40, v53, v52);
      if ( !BinopSpec )
        goto LABEL_120;
      v39 = v58;
    }
    v22 = *(_DWORD *)(v6 + 128) == 6;
    *(_BYTE *)(v6 + 144) = *(_BYTE *)(v4 + 5);
    if ( v22 )
      *(_BYTE *)(v4 + 5) = *((_BYTE *)L"pr" + *(unsigned __int8 *)(v4 + 5) + 1);
    if ( *(char *)(v6 + 136) >= 0 )
    {
      if ( *(_BYTE *)(v39 + 4) != 7 )
        v4 = PqteAndOr(BinopSpec, 29, 1);
      if ( *(char *)(v6 + 136) >= 0 )
      {
        v52 = PqteNULL(a1);
        if ( !v52 )
          goto LABEL_120;
        v50 = HteCopyPqte(a1);
        if ( !v50 )
          goto LABEL_120;
        TraverseExpn(&v57, 0, 2, IncCrefPqte);
        v43 = PqteCreateBinopSpec(v42, v50, v52);
        if ( !v43 )
          goto LABEL_120;
        v4 = PqteAndOr(v43, 29, 1);
      }
    }
    AddPredToSubquery(v4, a4);
    goto LABEL_140;
  }
  switch ( v31 )
  {
    case 0:
      *(_DWORD *)(v6 + 128) = 1;
      break;
    case 48:
    case 47:
      *(_DWORD *)(v6 + 128) = 3;
      goto LABEL_106;
    case 49:
      *(_DWORD *)(v6 + 128) = 6;
LABEL_106:
      *(_DWORD *)(v6 + 136) |= 1u;
      goto LABEL_107;
  }
LABEL_140:
  v44 = v59;
  v45 = *(_DWORD *)(v6 + 136) ^ ((unsigned __int8)*(_DWORD *)(v6 + 136) ^ (unsigned __int8)(v59[45] >> 7)) & 0x40;
  *(_DWORD *)(v6 + 136) = v45;
  if ( (v44[45] & 0x2000) != 0 )
    *(_DWORD *)(v6 + 136) = v45 | 1;
  CallocPvHsegREAL(a1, 14, 0, &v54);
  v46 = v54;
  *(_BYTE *)(v54 + 9) = 6;
  *(_DWORD *)v46 = a3;
  v22 = *(_DWORD *)(v6 + 128) == 1;
  v47 = v55;
  if ( v22 )
    v48 = ColtypOfPqgref(&v51);
  else
    v48 = 3;
  *(_BYTE *)(v46 + 8) = v48;
  *(_DWORD *)(v46 + 10) = v51;
  v49 = MapColtypVlt(*(unsigned __int8 *)(v46 + 8));
  result = (_DWORD *)PqteCreateBound(v49);
  if ( !result )
LABEL_120:
    _longjmp(*(int **)(a1 + 24), -3071);
  ++*(_WORD *)(v47 + 44);
  return result;
}

```

## disassembly

```asm
0x100e1360  mov     edi, edi
0x100e1362  push    ebp
0x100e1363  mov     ebp, esp
0x100e1365  sub     esp, 28h
0x100e1368  mov     eax, [ebp+arg_8]
0x100e136b  push    ebx
0x100e136c  push    esi
0x100e136d  mov     esi, [ebp+arg_4]
0x100e1370  xor     ebx, ebx
0x100e1372  push    edi
0x100e1373  mov     edi, [eax+8]
0x100e1376  mov     eax, [eax+4]
0x100e1379  mov     dh, [esi+4]
0x100e137c  mov     [ebp+var_10], eax
0x100e137f  lea     eax, [esi+5]
0x100e1382  mov     [ebp+var_1C], edi
0x100e1385  mov     [ebp+var_8], ebx
0x100e1388  mov     [ebp+var_4], esi
0x100e138b  mov     [ebp+var_C], 1
0x100e1392  mov     [ebp+var_24], ebx
0x100e1395  cmp     dh, 0Ch
0x100e1398  jnz     loc_100E146D
0x100e139e  mov     dl, [eax]
0x100e13a0  mov     ecx, eax
0x100e13a2  test    dl, dl
0x100e13a4  jz      short loc_100E13DA
0x100e13a6  cmp     dl, 30h ; '0'
0x100e13a9  jz      short loc_100E13DA
0x100e13ab  cmp     dl, 31h ; '1'
0x100e13ae  jz      short loc_100E13DA
0x100e13b0  cmp     dl, 2Fh ; '/'
0x100e13b3  jz      short loc_100E13DA
0x100e13b5  cmp     dl, 32h ; '2'
0x100e13b8  jz      short loc_100E13DA
0x100e13ba  mov     ecx, eax
0x100e13bc  cmp     dh, 3
0x100e13bf  jz      short loc_100E13DA
0x100e13c1  cmp     dh, 1
0x100e13c4  jnz     loc_100E1481
0x100e13ca  mov     dl, [eax]
0x100e13cc  cmp     dl, 3
0x100e13cf  jz      short loc_100E13DA
0x100e13d1  cmp     dl, 32h ; '2'
0x100e13d4  jnz     loc_100E1481
0x100e13da  cmp     dh, 1
0x100e13dd  jnz     short loc_100E144C
0x100e13df  cmp     byte ptr [ecx], 3
0x100e13e2  jnz     short loc_100E144C
0x100e13e4  mov     eax, [esi+0Ch]
0x100e13e7  cmp     byte ptr [eax+4], 4
0x100e13eb  jnz     loc_100E1481
0x100e13f1  cmp     byte ptr [eax+5], 5
0x100e13f5  jnz     loc_100E1481
0x100e13fb  mov     edx, [eax+0Ch]
0x100e13fe  mov     [ebp+var_20], edx
0x100e1401  cmp     byte ptr [edx+4], 0Ch
0x100e1405  jnz     short loc_100E1481
0x100e1407  mov     dl, [edx+5]
0x100e140a  test    dl, dl
0x100e140c  jz      short loc_100E1422
0x100e140e  cmp     dl, 30h ; '0'
0x100e1411  jz      short loc_100E1422
0x100e1413  cmp     dl, 31h ; '1'
0x100e1416  jz      short loc_100E1422
0x100e1418  cmp     dl, 2Fh ; '/'
0x100e141b  jz      short loc_100E1422
0x100e141d  cmp     dl, 32h ; '2'
0x100e1420  jnz     short loc_100E1481
0x100e1422  mov     edx, [ebp+var_20]
0x100e1425  mov     edi, [ebp+arg_8]
0x100e1428  cmp     [edx+8], edi
0x100e142b  mov     edi, [ebp+var_1C]
0x100e142e  jnz     short loc_100E1481
0x100e1430  mov     byte ptr [edx+5], 31h ; '1'
0x100e1434  mov     [eax+0Ch], esi
0x100e1437  mov     word ptr [eax+4], 903h
0x100e143d  mov     byte ptr [esi+4], 1
0x100e1441  mov     [esi+0Ch], edx
0x100e1444  mov     esi, eax
0x100e1446  mov     byte ptr [ecx], 31h ; '1'
0x100e1449  mov     [ebp+arg_4], esi
0x100e144c  mov     al, [esi+4]
0x100e144f  cmp     al, 4
0x100e1451  jz      short loc_100E1492
0x100e1453  cmp     al, 3
0x100e1455  jz      short loc_100E1492
0x100e1457  cmp     al, 1
0x100e1459  jnz     short loc_100E148A
0x100e145b  cmp     byte ptr [esi+5], 32h ; '2'
0x100e145f  jnz     loc_100E1509
0x100e1465  mov     ebx, [esi+0Ch]
0x100e1468  jmp     loc_100E1506
0x100e146d  cmp     dh, 4
0x100e1470  jnz     loc_100E13BA
0x100e1476  cmp     byte ptr [eax], 5
0x100e1479  mov     ecx, eax
0x100e147b  jz      loc_100E13DA
0x100e1481  mov     eax, esi
0x100e1483  pop     edi
0x100e1484  pop     esi
0x100e1485  pop     ebx
0x100e1486  leave
0x100e1487  retn    10h
0x100e148a  cmp     al, 0Ch
0x100e148c  jnz     short loc_100E1509
0x100e148e  mov     ebx, esi
0x100e1490  jmp     short loc_100E1506
0x100e1492  mov     cl, [esi+5]
0x100e1495  mov     ebx, [esi+0Ch]
0x100e1498  mov     [ebp+var_8], ebx
0x100e149b  cmp     cl, 5
0x100e149e  jnz     short loc_100E14A6
0x100e14a0  cmp     byte ptr [ebx+4], 0Ch
0x100e14a4  jz      short loc_100E1509
0x100e14a6  mov     al, [ebx+5]
0x100e14a9  cmp     al, 30h ; '0'
0x100e14ab  jz      short loc_100E1503
0x100e14ad  cmp     al, 31h ; '1'
0x100e14af  jz      short loc_100E1503
0x100e14b1  cmp     al, 2Fh ; '/'
0x100e14b3  jz      short loc_100E1503
0x100e14b5  mov     edx, [esi+8]
0x100e14b8  cmp     cl, 7
0x100e14bb  jb      short loc_100E14FE
0x100e14bd  cmp     cl, 0Eh
0x100e14c0  jnb     short loc_100E14FE
0x100e14c2  cmp     cl, 8
0x100e14c5  jz      short loc_100E14FE
0x100e14c7  cmp     byte ptr [edx+4], 0Ch
0x100e14cb  jnz     short loc_100E14FE
0x100e14cd  cmp     byte ptr [edx+5], 0
0x100e14d1  jnz     short loc_100E14FE
0x100e14d3  mov     cl, [ebx+4]
0x100e14d6  cmp     cl, 0Ah
0x100e14d9  jnz     short loc_100E14EA
0x100e14db  test    al, al
0x100e14dd  jnz     short loc_100E14F7
0x100e14df  mov     eax, [ebx+8]
0x100e14e2  cmp     byte ptr [eax+9], 6
0x100e14e6  jnz     short loc_100E14F7
0x100e14e8  jmp     short loc_100E14FE
0x100e14ea  cmp     cl, 0Ch
0x100e14ed  jnz     short loc_100E14F7
0x100e14ef  test    al, al
0x100e14f1  jz      short loc_100E14FE
0x100e14f3  cmp     al, 32h ; '2'
0x100e14f5  jz      short loc_100E14FE
0x100e14f7  mov     edx, esi
0x100e14f9  call    _SwapPqte@8; SwapPqte(x,x)
0x100e14fe  mov     eax, [ebp+var_4]
0x100e1501  jmp     short loc_100E1483
0x100e1503  mov     ebx, [ebx+0Ch]
0x100e1506  mov     [ebp+var_8], ebx
0x100e1509  mov     eax, [ebp+arg_8]
0x100e150c  cmp     [ebx+8], eax
0x100e150f  jnz     short loc_100E14FE
0x100e1511  mov     ecx, [ebp+var_10]
0x100e1514  cmp     byte ptr [ebx+5], 32h ; '2'
0x100e1518  mov     ebx, [ebp+arg_0]
0x100e151b  mov     eax, [ecx+4]
0x100e151e  mov     [ebp+var_14], eax
0x100e1521  jz      loc_100E15AB
0x100e1527  push    0
0x100e1529  mov     edx, eax
0x100e152b  mov     ecx, ebx
0x100e152d  call    _FFLDLvInPqgref@12; FFLDLvInPqgref(x,x,x)
0x100e1532  test    eax, eax
0x100e1534  jz      short loc_100E1553
0x100e1536  mov     edx, [ebp+var_14]
0x100e1539  mov     ecx, ebx
0x100e153b  push    0FFFFE005h
0x100e1540  call    _SetErrorInfoPqgref@12; SetErrorInfoPqgref(x,x,x)
0x100e1545  push    0FFFFF3E3h; Value
0x100e154a  push    dword ptr [ebx+18h]; Buf
0x100e154d  call    ds:__imp__longjmp
0x100e1553  cmp     byte ptr [esi+5], 5
0x100e1557  jz      short loc_100E1562
0x100e1559  mov     eax, [ebp+var_8]
0x100e155c  cmp     byte ptr [eax+5], 0
0x100e1560  jz      short loc_100E15B3
0x100e1562  mov     eax, [esi+8]
0x100e1565  lea     ecx, [ebp+var_20]
0x100e1568  push    offset _FLDLvVisitPqte@16; FLDLvVisitPqte(x,x,x,x)
0x100e156d  push    6
0x100e156f  push    ecx
0x100e1570  lea     ecx, [ebp+var_18]
0x100e1573  mov     [ebp+var_4], eax
0x100e1576  push    ecx
0x100e1577  mov     edx, eax
0x100e1579  mov     [ebp+var_20], 0
0x100e1580  mov     ecx, ebx
0x100e1582  mov     [ebp+var_18], 0
0x100e1589  call    _TraverseExpn@24; TraverseExpn(x,x,x,x,x,x)
0x100e158e  cmp     [ebp+var_18], 0
0x100e1592  jz      short loc_100E15B0
0x100e1594  push    0
0x100e1596  push    0
0x100e1598  push    0FFFFE005h
0x100e159d  push    [ebp+var_4]
0x100e15a0  xor     edx, edx
0x100e15a2  mov     ecx, ebx
0x100e15a4  call    _QEMSetErrorInfo@24; QEMSetErrorInfo(x,x,x,x,x,x)
0x100e15a9  jmp     short loc_100E1545
0x100e15ab  mov     eax, [ebp+var_8]
0x100e15ae  jmp     short loc_100E15B6
0x100e15b0  mov     eax, [ebp+var_8]
0x100e15b3  mov     ecx, [ebp+var_10]
0x100e15b6  mov     al, [eax+5]
0x100e15b9  cmp     al, 32h ; '2'
0x100e15bb  jz      loc_100E1690
0x100e15c1  cmp     dword ptr [ecx+8], 1
0x100e15c5  jz      short loc_100E15D1
0x100e15c7  push    0FFFFF409h
0x100e15cc  jmp     loc_100E154A
0x100e15d1  test    al, al
0x100e15d3  jnz     short loc_100E1645
0x100e15d5  cmp     byte ptr [esi+5], 5
0x100e15d9  jnz     loc_100E1690
0x100e15df  jmp     short loc_100E1645
0x100e15e1  mov     edx, [ebp+var_4]
0x100e15e4  call    _ConsumeSubquery@8; ConsumeSubquery(x,x)
0x100e15e9  mov     edx, [ebp+var_4]
0x100e15ec  mov     eax, [edx+8]
0x100e15ef  test    byte ptr [eax+88h], 1
0x100e15f6  jz      short loc_100E1645
0x100e15f8  mov     eax, [edi+98h]
0x100e15fe  cmp     eax, 8
0x100e1601  jge     short loc_100E1645
0x100e1603  test    eax, eax
0x100e1605  jnz     short loc_100E161D
0x100e1607  lea     eax, [edi+94h]
0x100e160d  mov     ecx, ebx
0x100e160f  push    eax
0x100e1610  push    0
0x100e1612  push    20h ; ' '
0x100e1614  pop     edx
0x100e1615  call    _CallocPvHsegREAL@16; CallocPvHsegREAL(x,x,x,x)
0x100e161a  mov     edx, [ebp+var_4]
0x100e161d  mov     ecx, [edi+98h]
0x100e1623  lea     eax, [ecx+1]
0x100e1626  mov     [edi+98h], eax
0x100e162c  mov     eax, [edi+94h]
0x100e1632  mov     [eax+ecx*4], edx
0x100e1635  mov     eax, [ebp+var_4]
0x100e1638  mov     eax, [eax+8]
0x100e163b  or      dword ptr [eax+88h], 100h
0x100e1645  mov     edx, [esi+8]
0x100e1648  lea     eax, [ebp+var_4]
0x100e164b  push    eax
0x100e164c  mov     ecx, ebx
0x100e164e  call    _FPqteHasSelect@12; FPqteHasSelect(x,x,x)
0x100e1653  mov     ecx, ebx
0x100e1655  test    eax, eax
0x100e1657  jnz     short loc_100E15E1
0x100e1659  mov     edx, [esi+8]
0x100e165c  push    eax
0x100e165d  push    offset _HteMarkDfnsAsConsumed@16; HteMarkDfnsAsConsumed(x,x,x,x)
0x100e1662  push    eax
0x100e1663  push    eax
0x100e1664  call    _HteModifyAllExpn@24; HteModifyAllExpn(x,x,x,x,x,x)
0x100e1669  mov     edx, [esi+8]
0x100e166c  mov     ecx, ebx
0x100e166e  push    ebx
0x100e166f  call    _HteCopyPqte@12; HteCopyPqte(x,x,x)
0x100e1674  push    offset _IncCrefPqte@16; IncCrefPqte(x,x,x,x)
0x100e1679  push    2
0x100e167b  push    0
0x100e167d  lea     ecx, [ebp+var_C]
0x100e1680  mov     [edi+8Ch], eax
0x100e1686  push    ecx
0x100e1687  mov     edx, eax
0x100e1689  mov     ecx, ebx
0x100e168b  call    _TraverseExpn@24; TraverseExpn(x,x,x,x,x,x)
0x100e1690  mov     edx, [ebp+arg_8]
0x100e1693  mov     eax, [edx+4]
0x100e1696  mov     [ebp+var_4], eax
0x100e1699  mov     ecx, [eax+0B4h]
0x100e169f  test    ecx, 2000h
0x100e16a5  jz      short loc_100E1723
0x100e16a7  cmp     dword ptr [eax+0DCh], 0
0x100e16ae  jnz     short loc_100E16E5
0x100e16b0  cmp     dword ptr [eax], 4
0x100e16b3  jz      short loc_100E16BF
0x100e16b5  cmp     dword ptr [eax], 2
0x100e16b8  jnz     short loc_100E16E5
0x100e16ba  test    cl, 10h
0x100e16bd  jz      short loc_100E16E5
0x100e16bf  test    ecx, 4202h
0x100e16c5  jnz     short loc_100E16E5
0x100e16c7  test    byte ptr [edx+14h], 20h
0x100e16cb  jnz     short loc_100E16E5
0x100e16cd  cmp     dword ptr [eax], 4
0x100e16d0  jz      short loc_100E16DC
0x100e16d2  cmp     dword ptr [eax], 2
0x100e16d5  jnz     short loc_100E1723
0x100e16d7  test    cl, 10h
0x100e16da  jz      short loc_100E1723
0x100e16dc  test    byte ptr [eax+0B8h], 1
0x100e16e3  jnz     short loc_100E16EE
0x100e16e5  or      dword ptr [edi+88h], 2
  ... truncated ...
```
