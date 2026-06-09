# HteReplaceSelectPqte(x,x,x,x)

- ea: `0x100e11d0`
- end: `0x100e190b`
- name: `_HteReplaceSelectPqte@16`
- size: `1851`
- prototype: ``
- caller_count: `0`
- callee_count: `21`
- tags: ``

## callees

- `0x100b74ab`
- `0x100b78ee`
- `0x100b7b08`
- `0x100b7fdc`
- `0x100b8316`
- `0x100b8377`
- `0x100b847f`
- `0x100b84ca`
- `0x100b853d`
- `0x100bb791`
- `0x100e07f9`
- `0x100e08b5`
- `0x100e0b27`
- `0x100e0db3`
- `0x100e11d0`
- `0x100e196b`
- `0x100e974c`
- `0x100e9da0`
- `0x100ea4c7`
- `0x100ea62f`
- `0x100ebdcf`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!longjmp` at `0x100e13bd`
- `api-ms-win-crt-private-l1-1-0!longjmp` at `0x100e13bd`

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
0x100e11d0  mov     edi, edi
0x100e11d2  push    ebp
0x100e11d3  mov     ebp, esp
0x100e11d5  sub     esp, 28h
0x100e11d8  mov     eax, [ebp+arg_8]
0x100e11db  push    ebx
0x100e11dc  push    esi
0x100e11dd  mov     esi, [ebp+arg_4]
0x100e11e0  xor     ebx, ebx
0x100e11e2  push    edi
0x100e11e3  mov     edi, [eax+8]
0x100e11e6  mov     eax, [eax+4]
0x100e11e9  mov     dh, [esi+4]
0x100e11ec  mov     [ebp+var_10], eax
0x100e11ef  lea     eax, [esi+5]
0x100e11f2  mov     [ebp+var_1C], edi
0x100e11f5  mov     [ebp+var_8], ebx
0x100e11f8  mov     [ebp+var_4], esi
0x100e11fb  mov     [ebp+var_C], 1
0x100e1202  mov     [ebp+var_24], ebx
0x100e1205  cmp     dh, 0Ch
0x100e1208  jnz     loc_100E12DD
0x100e120e  mov     dl, [eax]
0x100e1210  mov     ecx, eax
0x100e1212  test    dl, dl
0x100e1214  jz      short loc_100E124A
0x100e1216  cmp     dl, 30h ; '0'
0x100e1219  jz      short loc_100E124A
0x100e121b  cmp     dl, 31h ; '1'
0x100e121e  jz      short loc_100E124A
0x100e1220  cmp     dl, 2Fh ; '/'
0x100e1223  jz      short loc_100E124A
0x100e1225  cmp     dl, 32h ; '2'
0x100e1228  jz      short loc_100E124A
0x100e122a  mov     ecx, eax
0x100e122c  cmp     dh, 3
0x100e122f  jz      short loc_100E124A
0x100e1231  cmp     dh, 1
0x100e1234  jnz     loc_100E12F1
0x100e123a  mov     dl, [eax]
0x100e123c  cmp     dl, 3
0x100e123f  jz      short loc_100E124A
0x100e1241  cmp     dl, 32h ; '2'
0x100e1244  jnz     loc_100E12F1
0x100e124a  cmp     dh, 1
0x100e124d  jnz     short loc_100E12BC
0x100e124f  cmp     byte ptr [ecx], 3
0x100e1252  jnz     short loc_100E12BC
0x100e1254  mov     eax, [esi+0Ch]
0x100e1257  cmp     byte ptr [eax+4], 4
0x100e125b  jnz     loc_100E12F1
0x100e1261  cmp     byte ptr [eax+5], 5
0x100e1265  jnz     loc_100E12F1
0x100e126b  mov     edx, [eax+0Ch]
0x100e126e  mov     [ebp+var_20], edx
0x100e1271  cmp     byte ptr [edx+4], 0Ch
0x100e1275  jnz     short loc_100E12F1
0x100e1277  mov     dl, [edx+5]
0x100e127a  test    dl, dl
0x100e127c  jz      short loc_100E1292
0x100e127e  cmp     dl, 30h ; '0'
0x100e1281  jz      short loc_100E1292
0x100e1283  cmp     dl, 31h ; '1'
0x100e1286  jz      short loc_100E1292
0x100e1288  cmp     dl, 2Fh ; '/'
0x100e128b  jz      short loc_100E1292
0x100e128d  cmp     dl, 32h ; '2'
0x100e1290  jnz     short loc_100E12F1
0x100e1292  mov     edx, [ebp+var_20]
0x100e1295  mov     edi, [ebp+arg_8]
0x100e1298  cmp     [edx+8], edi
0x100e129b  mov     edi, [ebp+var_1C]
0x100e129e  jnz     short loc_100E12F1
0x100e12a0  mov     byte ptr [edx+5], 31h ; '1'
0x100e12a4  mov     [eax+0Ch], esi
0x100e12a7  mov     word ptr [eax+4], 903h
0x100e12ad  mov     byte ptr [esi+4], 1
0x100e12b1  mov     [esi+0Ch], edx
0x100e12b4  mov     esi, eax
0x100e12b6  mov     byte ptr [ecx], 31h ; '1'
0x100e12b9  mov     [ebp+arg_4], esi
0x100e12bc  mov     al, [esi+4]
0x100e12bf  cmp     al, 4
0x100e12c1  jz      short loc_100E1302
0x100e12c3  cmp     al, 3
0x100e12c5  jz      short loc_100E1302
0x100e12c7  cmp     al, 1
0x100e12c9  jnz     short loc_100E12FA
0x100e12cb  cmp     byte ptr [esi+5], 32h ; '2'
0x100e12cf  jnz     loc_100E1379
0x100e12d5  mov     ebx, [esi+0Ch]
0x100e12d8  jmp     loc_100E1376
0x100e12dd  cmp     dh, 4
0x100e12e0  jnz     loc_100E122A
0x100e12e6  cmp     byte ptr [eax], 5
0x100e12e9  mov     ecx, eax
0x100e12eb  jz      loc_100E124A
0x100e12f1  mov     eax, esi
0x100e12f3  pop     edi
0x100e12f4  pop     esi
0x100e12f5  pop     ebx
0x100e12f6  leave
0x100e12f7  retn    10h
0x100e12fa  cmp     al, 0Ch
0x100e12fc  jnz     short loc_100E1379
0x100e12fe  mov     ebx, esi
0x100e1300  jmp     short loc_100E1376
0x100e1302  mov     cl, [esi+5]
0x100e1305  mov     ebx, [esi+0Ch]
0x100e1308  mov     [ebp+var_8], ebx
0x100e130b  cmp     cl, 5
0x100e130e  jnz     short loc_100E1316
0x100e1310  cmp     byte ptr [ebx+4], 0Ch
0x100e1314  jz      short loc_100E1379
0x100e1316  mov     al, [ebx+5]
0x100e1319  cmp     al, 30h ; '0'
0x100e131b  jz      short loc_100E1373
0x100e131d  cmp     al, 31h ; '1'
0x100e131f  jz      short loc_100E1373
0x100e1321  cmp     al, 2Fh ; '/'
0x100e1323  jz      short loc_100E1373
0x100e1325  mov     edx, [esi+8]
0x100e1328  cmp     cl, 7
0x100e132b  jb      short loc_100E136E
0x100e132d  cmp     cl, 0Eh
0x100e1330  jnb     short loc_100E136E
0x100e1332  cmp     cl, 8
0x100e1335  jz      short loc_100E136E
0x100e1337  cmp     byte ptr [edx+4], 0Ch
0x100e133b  jnz     short loc_100E136E
0x100e133d  cmp     byte ptr [edx+5], 0
0x100e1341  jnz     short loc_100E136E
0x100e1343  mov     cl, [ebx+4]
0x100e1346  cmp     cl, 0Ah
0x100e1349  jnz     short loc_100E135A
0x100e134b  test    al, al
0x100e134d  jnz     short loc_100E1367
0x100e134f  mov     eax, [ebx+8]
0x100e1352  cmp     byte ptr [eax+9], 6
0x100e1356  jnz     short loc_100E1367
0x100e1358  jmp     short loc_100E136E
0x100e135a  cmp     cl, 0Ch
0x100e135d  jnz     short loc_100E1367
0x100e135f  test    al, al
0x100e1361  jz      short loc_100E136E
0x100e1363  cmp     al, 32h ; '2'
0x100e1365  jz      short loc_100E136E
0x100e1367  mov     edx, esi
0x100e1369  call    _SwapPqte@8; SwapPqte(x,x)
0x100e136e  mov     eax, [ebp+var_4]
0x100e1371  jmp     short loc_100E12F3
0x100e1373  mov     ebx, [ebx+0Ch]
0x100e1376  mov     [ebp+var_8], ebx
0x100e1379  mov     eax, [ebp+arg_8]
0x100e137c  cmp     [ebx+8], eax
0x100e137f  jnz     short loc_100E136E
0x100e1381  mov     ecx, [ebp+var_10]
0x100e1384  cmp     byte ptr [ebx+5], 32h ; '2'
0x100e1388  mov     ebx, [ebp+arg_0]
0x100e138b  mov     eax, [ecx+4]
0x100e138e  mov     [ebp+var_14], eax
0x100e1391  jz      loc_100E141B
0x100e1397  push    0
0x100e1399  mov     edx, eax
0x100e139b  mov     ecx, ebx
0x100e139d  call    _FFLDLvInPqgref@12; FFLDLvInPqgref(x,x,x)
0x100e13a2  test    eax, eax
0x100e13a4  jz      short loc_100E13C3
0x100e13a6  mov     edx, [ebp+var_14]
0x100e13a9  mov     ecx, ebx
0x100e13ab  push    0FFFFE005h
0x100e13b0  call    _SetErrorInfoPqgref@12; SetErrorInfoPqgref(x,x,x)
0x100e13b5  push    0FFFFF3E3h; Value
0x100e13ba  push    dword ptr [ebx+18h]; Buf
0x100e13bd  call    ds:__imp__longjmp
0x100e13c3  cmp     byte ptr [esi+5], 5
0x100e13c7  jz      short loc_100E13D2
0x100e13c9  mov     eax, [ebp+var_8]
0x100e13cc  cmp     byte ptr [eax+5], 0
0x100e13d0  jz      short loc_100E1423
0x100e13d2  mov     eax, [esi+8]
0x100e13d5  lea     ecx, [ebp+var_20]
0x100e13d8  push    offset _FLDLvVisitPqte@16; FLDLvVisitPqte(x,x,x,x)
0x100e13dd  push    6
0x100e13df  push    ecx
0x100e13e0  lea     ecx, [ebp+var_18]
0x100e13e3  mov     [ebp+var_4], eax
0x100e13e6  push    ecx
0x100e13e7  mov     edx, eax
0x100e13e9  mov     [ebp+var_20], 0
0x100e13f0  mov     ecx, ebx
0x100e13f2  mov     [ebp+var_18], 0
0x100e13f9  call    _TraverseExpn@24; TraverseExpn(x,x,x,x,x,x)
0x100e13fe  cmp     [ebp+var_18], 0
0x100e1402  jz      short loc_100E1420
0x100e1404  push    0
0x100e1406  push    0
0x100e1408  push    0FFFFE005h
0x100e140d  push    [ebp+var_4]
0x100e1410  xor     edx, edx
0x100e1412  mov     ecx, ebx
0x100e1414  call    _QEMSetErrorInfo@24; QEMSetErrorInfo(x,x,x,x,x,x)
0x100e1419  jmp     short loc_100E13B5
0x100e141b  mov     eax, [ebp+var_8]
0x100e141e  jmp     short loc_100E1426
0x100e1420  mov     eax, [ebp+var_8]
0x100e1423  mov     ecx, [ebp+var_10]
0x100e1426  mov     al, [eax+5]
0x100e1429  cmp     al, 32h ; '2'
0x100e142b  jz      loc_100E1500
0x100e1431  cmp     dword ptr [ecx+8], 1
0x100e1435  jz      short loc_100E1441
0x100e1437  push    0FFFFF409h
0x100e143c  jmp     loc_100E13BA
0x100e1441  test    al, al
0x100e1443  jnz     short loc_100E14B5
0x100e1445  cmp     byte ptr [esi+5], 5
0x100e1449  jnz     loc_100E1500
0x100e144f  jmp     short loc_100E14B5
0x100e1451  mov     edx, [ebp+var_4]
0x100e1454  call    _ConsumeSubquery@8; ConsumeSubquery(x,x)
0x100e1459  mov     edx, [ebp+var_4]
0x100e145c  mov     eax, [edx+8]
0x100e145f  test    byte ptr [eax+88h], 1
0x100e1466  jz      short loc_100E14B5
0x100e1468  mov     eax, [edi+98h]
0x100e146e  cmp     eax, 8
0x100e1471  jge     short loc_100E14B5
0x100e1473  test    eax, eax
0x100e1475  jnz     short loc_100E148D
0x100e1477  lea     eax, [edi+94h]
0x100e147d  mov     ecx, ebx
0x100e147f  push    eax
0x100e1480  push    0
0x100e1482  push    20h ; ' '
0x100e1484  pop     edx
0x100e1485  call    _CallocPvHsegREAL@16; CallocPvHsegREAL(x,x,x,x)
0x100e148a  mov     edx, [ebp+var_4]
0x100e148d  mov     ecx, [edi+98h]
0x100e1493  lea     eax, [ecx+1]
0x100e1496  mov     [edi+98h], eax
0x100e149c  mov     eax, [edi+94h]
0x100e14a2  mov     [eax+ecx*4], edx
0x100e14a5  mov     eax, [ebp+var_4]
0x100e14a8  mov     eax, [eax+8]
0x100e14ab  or      dword ptr [eax+88h], 100h
0x100e14b5  mov     edx, [esi+8]
0x100e14b8  lea     eax, [ebp+var_4]
0x100e14bb  push    eax
0x100e14bc  mov     ecx, ebx
0x100e14be  call    _FPqteHasSelect@12; FPqteHasSelect(x,x,x)
0x100e14c3  mov     ecx, ebx
0x100e14c5  test    eax, eax
0x100e14c7  jnz     short loc_100E1451
0x100e14c9  mov     edx, [esi+8]
0x100e14cc  push    eax
0x100e14cd  push    offset _HteMarkDfnsAsConsumed@16; HteMarkDfnsAsConsumed(x,x,x,x)
0x100e14d2  push    eax
0x100e14d3  push    eax
0x100e14d4  call    _HteModifyAllExpn@24; HteModifyAllExpn(x,x,x,x,x,x)
0x100e14d9  mov     edx, [esi+8]
0x100e14dc  mov     ecx, ebx
0x100e14de  push    ebx
0x100e14df  call    _HteCopyPqte@12; HteCopyPqte(x,x,x)
0x100e14e4  push    offset _IncCrefPqte@16; IncCrefPqte(x,x,x,x)
0x100e14e9  push    2
0x100e14eb  push    0
0x100e14ed  lea     ecx, [ebp+var_C]
0x100e14f0  mov     [edi+8Ch], eax
0x100e14f6  push    ecx
0x100e14f7  mov     edx, eax
0x100e14f9  mov     ecx, ebx
0x100e14fb  call    _TraverseExpn@24; TraverseExpn(x,x,x,x,x,x)
0x100e1500  mov     edx, [ebp+arg_8]
0x100e1503  mov     eax, [edx+4]
0x100e1506  mov     [ebp+var_4], eax
0x100e1509  mov     ecx, [eax+0B4h]
0x100e150f  test    ecx, 2000h
0x100e1515  jz      short loc_100E1593
0x100e1517  cmp     dword ptr [eax+0DCh], 0
0x100e151e  jnz     short loc_100E1555
0x100e1520  cmp     dword ptr [eax], 4
0x100e1523  jz      short loc_100E152F
0x100e1525  cmp     dword ptr [eax], 2
0x100e1528  jnz     short loc_100E1555
0x100e152a  test    cl, 10h
0x100e152d  jz      short loc_100E1555
0x100e152f  test    ecx, 4202h
0x100e1535  jnz     short loc_100E1555
0x100e1537  test    byte ptr [edx+14h], 20h
0x100e153b  jnz     short loc_100E1555
0x100e153d  cmp     dword ptr [eax], 4
0x100e1540  jz      short loc_100E154C
0x100e1542  cmp     dword ptr [eax], 2
0x100e1545  jnz     short loc_100E1593
0x100e1547  test    cl, 10h
0x100e154a  jz      short loc_100E1593
0x100e154c  test    byte ptr [eax+0B8h], 1
0x100e1553  jnz     short loc_100E155E
0x100e1555  or      dword ptr [edi+88h], 2
  ... truncated ...
```
