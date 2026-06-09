# ErrRseekUpdate(x,x,x,x,x)

- ea: `0x100d2c30`
- end: `0x100d3e9d`
- name: `_ErrRseekUpdate@20`
- size: `4717`
- prototype: `int __stdcall(int, int, void *, int, int)`
- caller_count: `1`
- callee_count: `37`
- tags: `file_ops, authz_impersonation, installer_update`

## callers

- `0x100d2860`

## callees

- `0x10012a60`
- `0x10017010`
- `0x1003e830`
- `0x10043890`
- `0x10044f80`
- `0x1004cf26`
- `0x10050190`
- `0x10096b5f`
- `0x10097fca`
- `0x1009e4ea`
- `0x100a4694`
- `0x100a65ec`
- `0x100a667d`
- `0x100a67b5`
- `0x100a68ed`
- `0x100a7132`
- `0x100a7838`
- `0x100c6dad`
- `0x100c7cb7`
- `0x100c8414`
- `0x100c93d1`
- `0x100d0efc`
- `0x100d16f8`
- `0x100d18a9`
- `0x100d1992`
- `0x100d1af2`
- `0x100d1bb4`
- `0x100d1ec9`
- `0x100d2120`
- `0x100d28ab`
- `0x100d2b59`
- `0x100d2c30`
- `0x100d3ea3`
- `0x100d4357`
- `0x100d4902`
- `0x10123110`
- `0x10124078`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x100d3d63`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x100d3d63`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x100d3daa`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x100d3daa`

## string_xrefs

- `0x100d2f2e`: `(UPDATE)`
- `0x100d2eb7`: `(DELETE)`

## pseudocode

```c
int __stdcall ErrRseekUpdate(int a1, _DWORD *a2, void *a3, int a4, size_t *a5)
{
  void *v6; // eax
  void *v7; // [esp-10h] [ebp-51Ch]
  void *v8; // [esp-8h] [ebp-514h]
  void *v9; // [esp-8h] [ebp-514h]
  void *v10; // [esp-8h] [ebp-514h]
  int v11; // [esp-8h] [ebp-514h]
  int v12; // [esp-4h] [ebp-510h]
  int v13; // [esp+8h] [ebp-504h] BYREF
  size_t v14; // [esp+Ch] [ebp-500h] BYREF
  _WORD *v15; // [esp+10h] [ebp-4FCh]
  int v16; // [esp+14h] [ebp-4F8h] BYREF
  int v17; // [esp+18h] [ebp-4F4h]
  int (__thiscall *v18)(_DWORD, _DWORD, _DWORD); // [esp+1Ch] [ebp-4F0h]
  int (__thiscall *v19)(_DWORD, _DWORD, _DWORD, _DWORD); // [esp+20h] [ebp-4ECh]
  int v20; // [esp+24h] [ebp-4E8h] BYREF
  size_t v21; // [esp+28h] [ebp-4E4h]
  int (__thiscall *v22)(_DWORD, _DWORD, _DWORD); // [esp+2Ch] [ebp-4E0h]
  int (__thiscall *v23)(_DWORD, _DWORD, _DWORD); // [esp+30h] [ebp-4DCh]
  int v24; // [esp+34h] [ebp-4D8h]
  BOOL v25; // [esp+38h] [ebp-4D4h]
  int v26; // [esp+3Ch] [ebp-4D0h]
  int (__thiscall *v27)(_DWORD, _DWORD, _DWORD); // [esp+40h] [ebp-4CCh]
  _WORD *v28; // [esp+44h] [ebp-4C8h]
  BOOL v29; // [esp+48h] [ebp-4C4h]
  BOOL v30; // [esp+4Ch] [ebp-4C0h]
  int v31; // [esp+50h] [ebp-4BCh]
  int v32; // [esp+54h] [ebp-4B8h] BYREF
  int v33; // [esp+58h] [ebp-4B4h]
  __int16 IsibOfSesid; // [esp+5Ch] [ebp-4B0h]
  int v35; // [esp+60h] [ebp-4ACh]
  BOOL v36; // [esp+64h] [ebp-4A8h] BYREF
  int v37; // [esp+68h] [ebp-4A4h]
  int v38; // [esp+6Ch] [ebp-4A0h]
  int v39; // [esp+70h] [ebp-49Ch]
  int v40; // [esp+74h] [ebp-498h]
  const wchar_t *v41; // [esp+78h] [ebp-494h]
  int v42; // [esp+7Ch] [ebp-490h] BYREF
  unsigned int v43; // [esp+80h] [ebp-48Ch]
  unsigned int v44; // [esp+84h] [ebp-488h] BYREF
  BOOL v45; // [esp+88h] [ebp-484h]
  __int16 v46; // [esp+8Eh] [ebp-47Eh]
  int *v47; // [esp+90h] [ebp-47Ch]
  _WORD *v48; // [esp+94h] [ebp-478h]
  _WORD *v49; // [esp+98h] [ebp-474h]
  int v50; // [esp+9Ch] [ebp-470h]
  int v51; // [esp+A0h] [ebp-46Ch]
  size_t Size; // [esp+A4h] [ebp-468h] BYREF
  int v53; // [esp+A8h] [ebp-464h]
  int v54; // [esp+ACh] [ebp-460h] BYREF
  _DWORD *v55; // [esp+B0h] [ebp-45Ch]
  _DWORD *v56; // [esp+B4h] [ebp-458h]
  void **v57; // [esp+B8h] [ebp-454h]
  int v58; // [esp+BCh] [ebp-450h]
  int v59; // [esp+C0h] [ebp-44Ch]
  int v60; // [esp+C4h] [ebp-448h]
  int v61; // [esp+C8h] [ebp-444h]
  void *v62; // [esp+CCh] [ebp-440h] BYREF
  int v63; // [esp+D0h] [ebp-43Ch]
  int IsNullUpdDelQry; // [esp+D4h] [ebp-438h]
  int v65[128]; // [esp+D8h] [ebp-434h] BYREF
  _BYTE Src[512]; // [esp+2D8h] [ebp-234h] BYREF
  int v67[10]; // [esp+4D8h] [ebp-34h] BYREF
  char v68[4]; // [esp+500h] [ebp-Ch] BYREF
  int v69; // [esp+504h] [ebp-8h]

  v61 = a2[7];
  v60 = (int)a2;
  v55 = (_DWORD *)*a2;
  v63 = v55[51];
  v58 = a2[2];
  v51 = 0;
  v57 = 0;
  v62 = 0;
  Size = 0;
  v42 = 0;
  v35 = 0;
  v56 = (_DWORD *)(v61 + 24);
  v30 = *(_DWORD *)(v61 + 164) == 4 || v56[35] == 5 || v56[35] == 2 || v56[35] == 3;
  v45 = v30;
  v50 = 0;
  v53 = 0;
  v32 = 0;
  v29 = (*(_WORD *)(v63 + 12) & 1) != 0;
  v33 = v29;
  v41 = 0;
  v39 = 0;
  v38 = 0;
  if ( !*(_DWORD *)v63 || !**(_DWORD **)v63 )
  {
    IsNullUpdDelQry = ErrEnsureRseekConn(v55);
    if ( IsNullUpdDelQry < 0 )
      return IsNullUpdDelQry;
  }
  v59 = **(_DWORD **)v63;
  v37 = v58;
  if ( v58 )
  {
    if ( v37 != 2 )
    {
      if ( v37 != 4 )
      {
        if ( v37 == 50 )
        {
          v57 = (void **)(v63 + 1068);
          v51 = *(_DWORD *)(v63 + 1048);
          v41 = L"(DELETE)";
          v39 = -2008;
          v38 = -8130;
        }
        goto LABEL_27;
      }
      v58 = 2;
    }
    if ( !*(_DWORD *)&wPreparedUpdate && !v45 )
      v53 = 1;
    v57 = (void **)(v63 + 1064);
    v51 = *(_DWORD *)(v63 + 1040);
    if ( !v51 )
      goto LABEL_167;
    v41 = L"(UPDATE)";
    v39 = -2009;
    v38 = -8134;
  }
  else
  {
    if ( !*(_DWORD *)&wPreparedInsert && !v45 )
      v50 = 1;
    v57 = (void **)(v63 + 1060);
    v51 = *(_DWORD *)(v63 + 1032);
    v41 = L"(INSERT)";
    v39 = -2007;
    v38 = -8131;
  }
LABEL_27:
  if ( v50 || v53 )
  {
    v49 = *(_WORD **)(v63 + 16);
    v28 = &v49[12 * *(__int16 *)(v63 + 14)];
    while ( v49 < v28 && (*v49 & 0x40) == 0 )
      v49 += 12;
    if ( v49 >= v28 )
    {
      if ( !v53 )
      {
        v50 = 0;
        goto LABEL_36;
      }
LABEL_167:
      IsNullUpdDelQry = ErrDispUpdate(a1, *(_DWORD *)(v60 + 4), 0, 0, 0);
      if ( IsNullUpdDelQry >= 0 )
        return ErrRmtBMOfTTRow(v60, a3, a4, a5, 0);
      else
        return IsNullUpdDelQry;
    }
  }
LABEL_36:
  if ( !v50 && !v53 )
  {
    if ( *v57 )
    {
      if ( !*(_DWORD *)(v63 + 1072) )
      {
        IsNullUpdDelQry = ErrSQLPrepare(v56, a1, v59, *v57, v51);
        if ( IsNullUpdDelQry < 0 )
          return IsNullUpdDelQry;
        *(_DWORD *)(v63 + 1072) = 1;
      }
    }
    else
    {
      IsNullUpdDelQry = ErrSQLAllocStmt(a1, v59, v57, 0, v56[67]);
      if ( IsNullUpdDelQry < 0 )
        return IsNullUpdDelQry;
      IsNullUpdDelQry = ErrSQLPrepare(v56, a1, v59, *v57, v51);
      if ( IsNullUpdDelQry < 0 )
      {
        v8 = *v57;
        v7 = *v57;
        v27 = pfnSQLFreeStmt;
        pfnSQLFreeStmt(pfnSQLFreeStmt, v7, 1);
        ErrSQLCheckError(v8, a1);
        *v57 = 0;
        return IsNullUpdDelQry;
      }
      RegisterHdbcHstmt(0);
      *(_DWORD *)(v63 + 1072) = 1;
    }
  }
  if ( v58 )
  {
    IsNullUpdDelQry = ErrRmtBMOfTTRow(v60, Src, 510, &Size, 0);
    if ( IsNullUpdDelQry < 0 )
      return IsNullUpdDelQry;
  }
  if ( v50 || v53 )
  {
    IsNullUpdDelQry = ErrSQLAllocStmt(a1, v59, &v62, 0, v56[67]);
    if ( IsNullUpdDelQry < 0 )
      return IsNullUpdDelQry;
    v33 = 1;
    LOWORD(v43) = 1;
  }
  else
  {
    v62 = *v57;
    v35 = 0;
    LOWORD(v43) = 0;
  }
  v33 = 1;
  if ( v58 )
  {
    v36 = 0;
    if ( v53 )
    {
      v26 = 1;
      if ( !v45 )
        v36 = *(_DWORD *)(v63 + 1016) == 0;
    }
    else
    {
      v26 = FPartiallyNullBM(Src, Size);
      if ( !v45 && !*(_DWORD *)(v63 + 1016) )
      {
        IsNullUpdDelQry = ErrCheckPrevNulls(v60, 0, &v36);
        if ( IsNullUpdDelQry < 0 )
          return IsNullUpdDelQry;
      }
    }
    if ( v26 || v36 || *(_DWORD *)(v63 + 1016) )
    {
      if ( !v62 )
      {
        IsNullUpdDelQry = ErrSQLAllocStmt(a1, v59, &v62, 0, v56[67]);
        if ( IsNullUpdDelQry < 0 )
          return IsNullUpdDelQry;
        LOWORD(v43) = 1;
      }
      v35 = 1;
      v25 = v58 == 2;
      IsNullUpdDelQry = ErrPrepIsNullUpdDelQry(v60, v51, Src, Size, v25, v53, v36, &v42);
      if ( IsNullUpdDelQry < 0 )
        goto LABEL_162;
    }
  }
  LOWORD(v54) = 1;
  if ( v58 == 50 )
  {
    *(_DWORD *)(v63 + 1028) = 0;
  }
  else
  {
    v24 = v50 || v53;
    IsNullUpdDelQry = ErrRmtJPSetUpdColsParams(v60, v62, (int)&v54, 0, 0, v24);
    if ( IsNullUpdDelQry < 0 )
      goto LABEL_162;
  }
  if ( v58 )
  {
    IsNullUpdDelQry = ErrRmtJPSetBMQualParms(v60, v62, (int)&v54, (int)Src, Size, v35);
    if ( IsNullUpdDelQry < 0 )
      goto LABEL_162;
    if ( !v45 )
    {
      if ( *(_DWORD *)(v63 + 1016) )
      {
        IsNullUpdDelQry = ErrRmtJPSetTSQualParm(a1, v60, v62, (int)&v54, (int)v67, 40);
        if ( IsNullUpdDelQry < 0 )
          goto LABEL_162;
      }
      else
      {
        IsNullUpdDelQry = ErrRmtJPSetUpdColsParams(v60, v62, (int)&v54, 1, v35, 0);
        if ( IsNullUpdDelQry < 0 )
          goto LABEL_162;
      }
    }
  }
  if ( v50 )
  {
    v32 = 0;
    IsNullUpdDelQry = ErrPrepCustomInsert(&v42, &v32);
    if ( IsNullUpdDelQry < 0 )
      goto LABEL_162;
  }
  if ( *(_DWORD *)(v63 + 1144) && (*(_DWORD *)(v63 + 1148) & 1) != 0 && v58 != 50 && v58 != 2 && v32 )
  {
    SetIdentityInsert((int)v62, *(wchar_t **)(v63 + 1144), 1);
    *(_DWORD *)(v63 + 1148) &= ~1u;
    *(_DWORD *)(v63 + 1148) |= 2u;
  }
  if ( v42 )
  {
    *(_DWORD *)(v63 + 1072) = 0;
    IsNullUpdDelQry = ErrSQLExecDirect(v56, a1, v59, v62, v42);
    if ( IsNullUpdDelQry >= 0 )
      goto LABEL_103;
LABEL_162:
    if ( IsNullUpdDelQry == -2001 )
    {
      IsNullUpdDelQry = v39;
      IsibOfSesid = UtilGetIsibOfSesid(a1);
      v47 = &rgsib[26 * IsibOfSesid];
      v47[4] = v38;
      if ( v47[8] )
        _free((void *)v47[8]);
      v47[8] = 0;
      TableNameOfJptbl(&v20);
      v21 = 2 * WCSLEN(v20) + 2;
      v6 = _malloc(v21);
      v47[8] = (int)v6;
      WCSCPY2(v21 >> 1);
    }
    v19 = pfnSQLCancel;
    ((void (__thiscall *)(_DWORD, _DWORD))pfnSQLCancel)(pfnSQLCancel, v62);
    v18 = pfnSQLFreeStmt;
    pfnSQLFreeStmt(pfnSQLFreeStmt, v62, v43);
    ErrSQLCheckError(v11, v12);
    return IsNullUpdDelQry;
  }
  if ( (wSQLTrace & 1) != 0 )
    ErrLogSQLTextOut((int)v41, 3);
  IsNullUpdDelQry = ErrSQLExecute(v59, v62);
  if ( IsNullUpdDelQry < 0 )
    goto LABEL_162;
LABEL_103:
  if ( IsNullUpdDelQry == 2023 )
  {
    while ( 1 )
    {
      IsNullUpdDelQry = ErrSQLParamData(a1, v59, v62, &v16);
      if ( IsNullUpdDelQry != 2023 )
        break;
      IsNullUpdDelQry = ErrRMTSendLvData(
                          *(_DWORD *)(v63 + 1028),
                          *(__int16 *)(v63 + 1020) + *(_DWORD *)(v63 + 1024) - *(_DWORD *)(v63 + 1028),
                          v16,
                          v59,
                          v62);
      if ( IsNullUpdDelQry < 0 )
        goto LABEL_162;
    }
    if ( IsNullUpdDelQry < 0 )
      goto LABEL_162;
  }
  v9 = v62;
  v23 = pfnSQLFreeStmt;
  pfnSQLFreeStmt(pfnSQLFreeStmt, v62, 3);
  IsNullUpdDelQry = ErrSQLCheckError(v9, a1);
  if ( IsNullUpdDelQry < 0 )
    goto LABEL_162;
  RmtStartIdle(v59);
  IsNullUpdDelQry = ErrSQLRowCount(v62, (unsigned int)&v44);
  if ( IsNullUpdDelQry < 0 )
    goto LABEL_162;
  if ( !v44 )
  {
    if ( v58 )
      IsNullUpdDelQry = -1611;
    goto LABEL_162;
  }
  if ( v44 == -1 )
  {
    v44 = 1;
    goto LABEL_118;
  }
  if ( (v44 & 0x80000000) != 0 )
  {
    IsNullUpdDelQry = -2001;
    goto LABEL_162;
  }
LABEL_118:
  if ( (int)v44 > 1 )
  {
    IsNullUpdDelQry = -2032;
    goto LABEL_162;
  }
  if ( (unsigned __int16)v43 == 1 )
  {
    v10 = v62;
    v22 = pfnSQLFreeStmt;
    pfnSQLFreeStmt(pfnSQLFreeStmt, v62, v43);
    ErrSQLCheckError(v10, a1);
  }
  if ( v58 == 50 )
    return 0;
  if ( !v58 )
  {
    v48 = *(_WORD **)(v63 + 16);
    v15 = &v48[12 * *(__int16 *)(v63 + 14)];
    v17 = 0;
    while ( v48 < v15 )
    {
      if ( (*v48 & 0x200) != 0 && (*v48 & 0x40) == 0 )
      {
        v17 = 1;
        break;
      }
      v48 += 12;
    }
    if ( v17 )
    {
      v13 = 8;
      *(_WORD *)(v63 + 12) |= 0x400u;
      IsNullUpdDelQry = ErrRmtRetrieveIdentity(v68, &v13);
      if ( IsNullUpdDelQry < 0 )
        return IsNullUpdDelQry;
      v55[54] = 1;
      v55[55] = v69;
      ErrIsamSetIdentity(a1, v69);
    }
    else
    {
      v55[54] = 0;
    }
  }
  if ( *(__int16 *)(v63 + 1002) > 0 )
  {
    IsNullUpdDelQry = ErrRmtBMOfTTRow(v60, Src, 510, &Size, 1);
    if ( IsNullUpdDelQry < 0 )
      return IsNullUpdDelQry;
  }
  IsNullUpdDelQry = ErrDispUpdate(a1, *(_DWORD *)(v60 + 4), 0, 0, 0);
  if ( IsNullUpdDelQry < 0 )
    return IsNullUpdDelQry;
  if ( !v58 )
    ErrDispMove2(a1, *(_DWORD *)(v60 + 4), 0x7FFFFFFF, 0);
  if ( !v58 )
  {
    v46 = *(_WORD *)(v63 + 1152) + 1;
    *(_WORD *)(v63 + 1152) = v46;
    if ( v46 > 5 )
    {
      *(_WORD *)(v60 + 20) |= 0x20u;
      *(_WORD *)(v63 + 1152) = 0;
    }
  }
  if ( *(__int16 *)(v63 + 1002) > 0 )
  {
    if ( *(_DWORD *)(v63 + 1016) )
    {
      IsNullUpdDelQry = ErrRseekGotoBookmark(a1, a2, Src, Size);
      if ( IsNullUpdDelQry == -1017 )
        IsNullUpdDelQry = 0;
      if ( IsNullUpdDelQry < 0 )
        return IsNullUpdDelQry;
    }
    if ( a3 )
    {
      memcpy(a3, Src, Size);
      *a5 = Size;
    }
  }
  if ( v58 )
    return 0;
  if ( RVTUpdatePass(v61, v55) )
    return 0;
  v31 = *(_DWORD *)(v55[60] + 4);
  v40 = *(_DWORD *)(v55[61] + 4);
  if ( (*(_DWORD *)(*(_DWORD *)(*(_DWORD *)(**(_DWORD **)v40 + 36) + 228) + 8 * v56[29] + 4) & 1) == 0 )
    return 0;
  IsNullUpdDelQry = ErrRVTConvJncolData(v40, v55 + 55, 4u, v65, (int)&v14);
  if ( IsNullUpdDelQry < 0 )
    return IsNullUpdDelQry;
  IsNullUpdDelQry = ErrRVTSetUpdcol((int)v65, v14, 0, 0, *(_DWORD *)(**(_DWORD **)v31 + 36), 9);
  if ( IsNullUpdDelQry >= 0 )
    return 0;
  else
    return IsNullUpdDelQry;
}

```

## disassembly

```asm
0x100d2c30  mov     edi, edi
0x100d2c32  push    ebp
0x100d2c33  mov     ebp, esp
0x100d2c35  sub     esp, 50Ch
0x100d2c3b  mov     eax, ___security_cookie
0x100d2c40  xor     eax, ebp
0x100d2c42  mov     [ebp+var_4], eax
0x100d2c45  mov     eax, [ebp+arg_4]
0x100d2c48  mov     eax, [eax+1Ch]
0x100d2c4b  mov     [ebp+var_444], eax
0x100d2c51  mov     eax, [ebp+arg_4]
0x100d2c54  mov     [ebp+var_448], eax
0x100d2c5a  mov     eax, [ebp+var_448]
0x100d2c60  mov     eax, [eax]
0x100d2c62  mov     [ebp+var_45C], eax
0x100d2c68  mov     eax, [ebp+var_45C]
0x100d2c6e  mov     eax, [eax+0CCh]
0x100d2c74  mov     [ebp+var_43C], eax
0x100d2c7a  mov     eax, [ebp+var_448]
0x100d2c80  mov     eax, [eax+8]
0x100d2c83  mov     [ebp+var_450], eax
0x100d2c89  mov     [ebp+var_46C], 0
0x100d2c93  mov     [ebp+var_454], 0
0x100d2c9d  mov     [ebp+var_440], 0
0x100d2ca7  mov     [ebp+Size], 0
0x100d2cb1  mov     [ebp+var_490], 0
0x100d2cbb  mov     [ebp+var_4AC], 0
0x100d2cc5  mov     eax, [ebp+var_444]
0x100d2ccb  add     eax, 18h
0x100d2cce  mov     [ebp+var_458], eax
0x100d2cd4  mov     eax, [ebp+var_458]
0x100d2cda  cmp     dword ptr [eax+8Ch], 4
0x100d2ce1  jz      short loc_100D2D1C
0x100d2ce3  mov     eax, [ebp+var_458]
0x100d2ce9  cmp     dword ptr [eax+8Ch], 5
0x100d2cf0  jz      short loc_100D2D1C
0x100d2cf2  mov     eax, [ebp+var_458]
0x100d2cf8  cmp     dword ptr [eax+8Ch], 2
0x100d2cff  jz      short loc_100D2D1C
0x100d2d01  mov     eax, [ebp+var_458]
0x100d2d07  cmp     dword ptr [eax+8Ch], 3
0x100d2d0e  jz      short loc_100D2D1C
0x100d2d10  mov     [ebp+var_4C0], 0
0x100d2d1a  jmp     short loc_100D2D26
0x100d2d1c  mov     [ebp+var_4C0], 1
0x100d2d26  mov     eax, [ebp+var_4C0]
0x100d2d2c  mov     [ebp+var_484], eax
0x100d2d32  mov     [ebp+var_470], 0
0x100d2d3c  mov     [ebp+var_464], 0
0x100d2d46  mov     [ebp+var_4B8], 0
0x100d2d50  mov     eax, [ebp+var_43C]
0x100d2d56  movzx   eax, word ptr [eax+0Ch]
0x100d2d5a  and     eax, 1
0x100d2d5d  jz      short loc_100D2D6B
0x100d2d5f  mov     [ebp+var_4C4], 1
0x100d2d69  jmp     short loc_100D2D75
0x100d2d6b  mov     [ebp+var_4C4], 0
0x100d2d75  mov     eax, [ebp+var_4C4]
0x100d2d7b  mov     [ebp+var_4B4], eax
0x100d2d81  mov     [ebp+var_494], 0
0x100d2d8b  mov     [ebp+var_49C], 0
0x100d2d95  mov     [ebp+var_4A0], 0
0x100d2d9f  mov     eax, [ebp+var_43C]
0x100d2da5  cmp     dword ptr [eax], 0
0x100d2da8  jz      short loc_100D2DB7
0x100d2daa  mov     eax, [ebp+var_43C]
0x100d2db0  mov     eax, [eax]
0x100d2db2  cmp     dword ptr [eax], 0
0x100d2db5  jnz     short loc_100D2DE5
0x100d2db7  push    [ebp+var_45C]
0x100d2dbd  mov     edx, [ebp+var_444]
0x100d2dc3  mov     ecx, [ebp+arg_0]
0x100d2dc6  call    _ErrEnsureRseekConn@12; ErrEnsureRseekConn(x,x,x)
0x100d2dcb  mov     [ebp+var_438], eax
0x100d2dd1  cmp     [ebp+var_438], 0
0x100d2dd8  jge     short loc_100D2DE5
0x100d2dda  mov     eax, [ebp+var_438]
0x100d2de0  jmp     loc_100D3E8F
0x100d2de5  mov     eax, [ebp+var_43C]
0x100d2deb  mov     eax, [eax]
0x100d2ded  mov     eax, [eax]
0x100d2def  mov     [ebp+var_44C], eax
0x100d2df5  mov     eax, [ebp+var_450]
0x100d2dfb  mov     [ebp+var_4A4], eax
0x100d2e01  cmp     [ebp+var_4A4], 0
0x100d2e08  jz      short loc_100D2E32
0x100d2e0a  cmp     [ebp+var_4A4], 2
0x100d2e11  jz      loc_100D2EE1
0x100d2e17  cmp     [ebp+var_4A4], 4
0x100d2e1e  jz      loc_100D2ED7
0x100d2e24  cmp     [ebp+var_4A4], 32h ; '2'
0x100d2e2b  jz      short loc_100D2E94
0x100d2e2d  jmp     loc_100D2F4C
0x100d2e32  cmp     _wPreparedInsert, 0
0x100d2e39  jnz     short loc_100D2E4E
0x100d2e3b  cmp     [ebp+var_484], 0
0x100d2e42  jnz     short loc_100D2E4E
0x100d2e44  mov     [ebp+var_470], 1
0x100d2e4e  mov     eax, [ebp+var_43C]
0x100d2e54  add     eax, 424h
0x100d2e59  mov     [ebp+var_454], eax
0x100d2e5f  mov     eax, [ebp+var_43C]
0x100d2e65  mov     eax, [eax+408h]
0x100d2e6b  mov     [ebp+var_46C], eax
0x100d2e71  mov     [ebp+var_494], offset aInsert_0; "(INSERT)"
0x100d2e7b  mov     [ebp+var_49C], 0FFFFF829h
0x100d2e85  mov     [ebp+var_4A0], 0FFFFE03Dh
0x100d2e8f  jmp     loc_100D2F4C
0x100d2e94  mov     eax, [ebp+var_43C]
0x100d2e9a  add     eax, 42Ch
0x100d2e9f  mov     [ebp+var_454], eax
0x100d2ea5  mov     eax, [ebp+var_43C]
0x100d2eab  mov     eax, [eax+418h]
0x100d2eb1  mov     [ebp+var_46C], eax
0x100d2eb7  mov     [ebp+var_494], offset aDelete_0; "(DELETE)"
0x100d2ec1  mov     [ebp+var_49C], 0FFFFF828h
0x100d2ecb  mov     [ebp+var_4A0], 0FFFFE03Eh
0x100d2ed5  jmp     short loc_100D2F4C
0x100d2ed7  mov     [ebp+var_450], 2
0x100d2ee1  cmp     _wPreparedUpdate, 0
0x100d2ee8  jnz     short loc_100D2EFD
0x100d2eea  cmp     [ebp+var_484], 0
0x100d2ef1  jnz     short loc_100D2EFD
0x100d2ef3  mov     [ebp+var_464], 1
0x100d2efd  mov     eax, [ebp+var_43C]
0x100d2f03  add     eax, 428h
0x100d2f08  mov     [ebp+var_454], eax
0x100d2f0e  mov     eax, [ebp+var_43C]
0x100d2f14  mov     eax, [eax+410h]
0x100d2f1a  mov     [ebp+var_46C], eax
0x100d2f20  cmp     [ebp+var_46C], 0
0x100d2f27  jnz     short loc_100D2F2E
0x100d2f29  jmp     loc_100D3E42
0x100d2f2e  mov     [ebp+var_494], offset aUpdate_0; "(UPDATE)"
0x100d2f38  mov     [ebp+var_49C], 0FFFFF827h
0x100d2f42  mov     [ebp+var_4A0], 0FFFFE03Ah
0x100d2f4c  cmp     [ebp+var_470], 0
0x100d2f53  jnz     short loc_100D2F5E
0x100d2f55  cmp     [ebp+var_464], 0
0x100d2f5c  jz      short loc_100D2FDD
0x100d2f5e  mov     eax, [ebp+var_43C]
0x100d2f64  mov     eax, [eax+10h]
0x100d2f67  mov     [ebp+var_474], eax
0x100d2f6d  mov     eax, [ebp+var_43C]
0x100d2f73  movsx   eax, word ptr [eax+0Eh]
0x100d2f77  imul    eax, 18h
0x100d2f7a  add     eax, [ebp+var_474]
0x100d2f80  mov     [ebp+var_4C8], eax
0x100d2f86  jmp     short loc_100D2F97
0x100d2f88  mov     eax, [ebp+var_474]
0x100d2f8e  add     eax, 18h
0x100d2f91  mov     [ebp+var_474], eax
0x100d2f97  mov     eax, [ebp+var_474]
0x100d2f9d  cmp     eax, [ebp+var_4C8]
0x100d2fa3  jnb     short loc_100D2FB7
0x100d2fa5  mov     eax, [ebp+var_474]
0x100d2fab  movzx   eax, word ptr [eax]
0x100d2fae  and     eax, 40h
0x100d2fb1  jz      short loc_100D2FB5
0x100d2fb3  jmp     short loc_100D2FB7
0x100d2fb5  jmp     short loc_100D2F88
0x100d2fb7  mov     eax, [ebp+var_474]
0x100d2fbd  cmp     eax, [ebp+var_4C8]
0x100d2fc3  jb      short loc_100D2FDD
0x100d2fc5  cmp     [ebp+var_464], 0
0x100d2fcc  jz      short loc_100D2FD3
0x100d2fce  jmp     loc_100D3E42
0x100d2fd3  mov     [ebp+var_470], 0
0x100d2fdd  cmp     [ebp+var_470], 0
0x100d2fe4  jnz     loc_100D3149
0x100d2fea  cmp     [ebp+var_464], 0
0x100d2ff1  jnz     loc_100D3149
0x100d2ff7  mov     eax, [ebp+var_454]
0x100d2ffd  cmp     dword ptr [eax], 0
0x100d3000  jnz     loc_100D30EE
0x100d3006  mov     eax, [ebp+var_458]
0x100d300c  push    dword ptr [eax+10Ch]
0x100d3012  push    0
0x100d3014  push    [ebp+var_454]
0x100d301a  mov     edx, [ebp+var_44C]
0x100d3020  mov     ecx, [ebp+arg_0]
0x100d3023  call    _ErrSQLAllocStmt@20; ErrSQLAllocStmt(x,x,x,x,x)
0x100d3028  mov     [ebp+var_438], eax
0x100d302e  cmp     [ebp+var_438], 0
0x100d3035  jge     short loc_100D3042
0x100d3037  mov     eax, [ebp+var_438]
0x100d303d  jmp     loc_100D3E8F
0x100d3042  push    [ebp+var_46C]
0x100d3048  mov     eax, [ebp+var_454]
0x100d304e  push    dword ptr [eax]
0x100d3050  push    [ebp+var_44C]
0x100d3056  mov     edx, [ebp+arg_0]
0x100d3059  mov     ecx, [ebp+var_458]
0x100d305f  call    _ErrSQLPrepare@20; ErrSQLPrepare(x,x,x,x,x)
0x100d3064  mov     [ebp+var_438], eax
0x100d306a  cmp     [ebp+var_438], 0
0x100d3071  jge     short loc_100D30C9
0x100d3073  push    [ebp+arg_0]
0x100d3076  mov     eax, [ebp+var_454]
0x100d307c  push    dword ptr [eax]
0x100d307e  push    1; unsigned int
0x100d3080  mov     eax, [ebp+var_454]
0x100d3086  push    dword ptr [eax]; void *
0x100d3088  mov     eax, _pfnSQLFreeStmt
0x100d308d  mov     [ebp+var_4CC], eax
0x100d3093  mov     ecx, [ebp+var_4CC]
0x100d3099  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100d309f  call    [ebp+var_4CC]
0x100d30a5  mov     edx, [ebp+var_44C]
0x100d30ab  mov     ecx, eax
0x100d30ad  call    _ErrSQLCheckError@16; ErrSQLCheckError(x,x,x,x)
0x100d30b2  mov     eax, [ebp+var_454]
0x100d30b8  mov     dword ptr [eax], 0
0x100d30be  mov     eax, [ebp+var_438]
0x100d30c4  jmp     loc_100D3E8F
0x100d30c9  push    0
0x100d30cb  mov     edx, [ebp+var_454]
0x100d30d1  mov     ecx, [ebp+var_44C]
0x100d30d7  call    _RegisterHdbcHstmt@12; RegisterHdbcHstmt(x,x,x)
0x100d30dc  mov     eax, [ebp+var_43C]
0x100d30e2  mov     dword ptr [eax+430h], 1
0x100d30ec  jmp     short loc_100D3149
0x100d30ee  mov     eax, [ebp+var_43C]
0x100d30f4  cmp     dword ptr [eax+430h], 0
0x100d30fb  jnz     short loc_100D3149
0x100d30fd  push    [ebp+var_46C]
0x100d3103  mov     eax, [ebp+var_454]
0x100d3109  push    dword ptr [eax]
0x100d310b  push    [ebp+var_44C]
0x100d3111  mov     edx, [ebp+arg_0]
0x100d3114  mov     ecx, [ebp+var_458]
0x100d311a  call    _ErrSQLPrepare@20; ErrSQLPrepare(x,x,x,x,x)
0x100d311f  mov     [ebp+var_438], eax
0x100d3125  cmp     [ebp+var_438], 0
0x100d312c  jge     short loc_100D3139
0x100d312e  mov     eax, [ebp+var_438]
0x100d3134  jmp     loc_100D3E8F
0x100d3139  mov     eax, [ebp+var_43C]
0x100d313f  mov     dword ptr [eax+430h], 1
0x100d3149  cmp     [ebp+var_450], 0
0x100d3150  jz      short loc_100D3195
0x100d3152  push    0
0x100d3154  lea     eax, [ebp+Size]
0x100d315a  push    eax
0x100d315b  push    1FEh
0x100d3160  lea     eax, [ebp+Src]
0x100d3166  push    eax
0x100d3167  push    [ebp+var_448]
0x100d316d  mov     edx, [ebp+var_444]
0x100d3173  mov     ecx, [ebp+arg_0]
0x100d3176  call    _ErrRmtBMOfTTRow@28; ErrRmtBMOfTTRow(x,x,x,x,x,x,x)
0x100d317b  mov     [ebp+var_438], eax
0x100d3181  cmp     [ebp+var_438], 0
0x100d3188  jge     short loc_100D3195
0x100d318a  mov     eax, [ebp+var_438]
0x100d3190  jmp     loc_100D3E8F
0x100d3195  cmp     [ebp+var_470], 0
0x100d319c  jnz     short loc_100D31A7
0x100d319e  cmp     [ebp+var_464], 0
0x100d31a5  jz      short loc_100D31FA
0x100d31a7  mov     eax, [ebp+var_458]
0x100d31ad  push    dword ptr [eax+10Ch]
0x100d31b3  push    0
0x100d31b5  lea     eax, [ebp+var_440]
0x100d31bb  push    eax
0x100d31bc  mov     edx, [ebp+var_44C]
0x100d31c2  mov     ecx, [ebp+arg_0]
0x100d31c5  call    _ErrSQLAllocStmt@20; ErrSQLAllocStmt(x,x,x,x,x)
0x100d31ca  mov     [ebp+var_438], eax
0x100d31d0  cmp     [ebp+var_438], 0
0x100d31d7  jge     short loc_100D31E4
0x100d31d9  mov     eax, [ebp+var_438]
0x100d31df  jmp     loc_100D3E8F
0x100d31e4  mov     [ebp+var_4B4], 1
0x100d31ee  xor     eax, eax
0x100d31f0  inc     eax
0x100d31f1  mov     word ptr [ebp+var_48C], ax
0x100d31f8  jmp     short loc_100D321B
0x100d31fa  mov     eax, [ebp+var_454]
0x100d3200  mov     eax, [eax]
0x100d3202  mov     [ebp+var_440], eax
0x100d3208  mov     [ebp+var_4AC], 0
0x100d3212  xor     eax, eax
0x100d3214  mov     word ptr [ebp+var_48C], ax
0x100d321b  mov     [ebp+var_4B4], 1
0x100d3225  cmp     [ebp+var_450], 0
0x100d322c  jz      loc_100D33D8
0x100d3232  cmp     [ebp+var_4B4], 0
0x100d3239  jz      loc_100D33D8
0x100d323f  mov     [ebp+var_4A8], 0
0x100d3249  cmp     [ebp+var_464], 0
0x100d3250  jz      short loc_100D3280
0x100d3252  mov     [ebp+var_4D0], 1
0x100d325c  cmp     [ebp+var_484], 0
0x100d3263  jnz     short loc_100D327E
0x100d3265  mov     eax, [ebp+var_43C]
0x100d326b  cmp     dword ptr [eax+3F8h], 0
0x100d3272  jnz     short loc_100D327E
0x100d3274  mov     [ebp+var_4A8], 1
0x100d327e  jmp     short loc_100D32E6
  ... truncated ...
```
