# ErrRseekUpdate(x,x,x,x,x)

- ea: `0x100d2aa0`
- end: `0x100d3d0d`
- name: `_ErrRseekUpdate@20`
- size: `4717`
- prototype: `int __stdcall(void *, int, void *, int, size_t *)`
- caller_count: `1`
- callee_count: `37`
- tags: `file_ops, authz_impersonation, installer_update`

## callers

- `0x100d26d0`

## callees

- `0x10012920`
- `0x10016ed0`
- `0x1003e6a0`
- `0x10043700`
- `0x10044e00`
- `0x1004cd96`
- `0x10050000`
- `0x100969cf`
- `0x10097e3a`
- `0x1009e35a`
- `0x100a4504`
- `0x100a645c`
- `0x100a64ed`
- `0x100a6625`
- `0x100a675d`
- `0x100a6fa2`
- `0x100a76a8`
- `0x100c6c1d`
- `0x100c7b27`
- `0x100c8284`
- `0x100c9241`
- `0x100d0d6c`
- `0x100d1568`
- `0x100d1719`
- `0x100d1802`
- `0x100d1962`
- `0x100d1a24`
- `0x100d1d39`
- `0x100d1f90`
- `0x100d271b`
- `0x100d29c9`
- `0x100d2aa0`
- `0x100d3d13`
- `0x100d41c7`
- `0x100d4772`
- `0x10122f60`
- `0x10123ec8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x100d3bd3`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x100d3bd3`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x100d3c1a`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x100d3c1a`

## string_xrefs

- `0x100d2d9e`: `(UPDATE)`
- `0x100d2d27`: `(DELETE)`

## pseudocode

```c
int __stdcall ErrRseekUpdate(void *a1, int a2, void *a3, int a4, size_t *a5)
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
  int (__thiscall *v19)(_DWORD, _DWORD); // [esp+20h] [ebp-4ECh]
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
  wchar_t *v42; // [esp+7Ch] [ebp-490h] BYREF
  unsigned int v43; // [esp+80h] [ebp-48Ch]
  unsigned int v44; // [esp+84h] [ebp-488h] BYREF
  BOOL v45; // [esp+88h] [ebp-484h]
  __int16 v46; // [esp+8Eh] [ebp-47Eh]
  int *v47; // [esp+90h] [ebp-47Ch]
  _WORD *v48; // [esp+94h] [ebp-478h]
  _WORD *v49; // [esp+98h] [ebp-474h]
  int v50; // [esp+9Ch] [ebp-470h]
  const unsigned __int16 *v51; // [esp+A0h] [ebp-46Ch]
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
  int v68; // [esp+500h] [ebp-Ch] BYREF
  int v69; // [esp+504h] [ebp-8h]

  v61 = *(_DWORD *)(a2 + 28);
  v60 = a2;
  v55 = *(_DWORD **)a2;
  v63 = v55[51];
  v58 = *(_DWORD *)(a2 + 8);
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
          v51 = *(const unsigned __int16 **)(v63 + 1048);
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
    v51 = *(const unsigned __int16 **)(v63 + 1040);
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
    v51 = *(const unsigned __int16 **)(v63 + 1032);
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
      IsNullUpdDelQry = ErrPrepIsNullUpdDelQry(a1, (_DWORD *)v60, v51, (int)Src, Size, v25, v53, v36, &v42);
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
        IsNullUpdDelQry = ErrRmtJPSetTSQualParm((int)a1, v60, v62, (int)&v54, (int)v67, 40);
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
    pfnSQLCancel(pfnSQLCancel, v62);
    v18 = pfnSQLFreeStmt;
    pfnSQLFreeStmt(pfnSQLFreeStmt, v62, v43);
    ErrSQLCheckError(v11, v12);
    return IsNullUpdDelQry;
  }
  if ( (wSQLTrace & 1) != 0 )
    ErrLogSQLTextOut(v41, 3);
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
      IsNullUpdDelQry = ErrRmtRetrieveIdentity(v61, (int)v55, &v68, &v13);
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
  IsNullUpdDelQry = ErrRVTConvJncolData(v61, v31, v40, v55 + 55, 4, v65, (int *)&v14);
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
0x100d2aa0  mov     edi, edi
0x100d2aa2  push    ebp
0x100d2aa3  mov     ebp, esp
0x100d2aa5  sub     esp, 50Ch
0x100d2aab  mov     eax, ___security_cookie
0x100d2ab0  xor     eax, ebp
0x100d2ab2  mov     [ebp+var_4], eax
0x100d2ab5  mov     eax, [ebp+arg_4]
0x100d2ab8  mov     eax, [eax+1Ch]
0x100d2abb  mov     [ebp+var_444], eax
0x100d2ac1  mov     eax, [ebp+arg_4]
0x100d2ac4  mov     [ebp+var_448], eax
0x100d2aca  mov     eax, [ebp+var_448]
0x100d2ad0  mov     eax, [eax]
0x100d2ad2  mov     [ebp+var_45C], eax
0x100d2ad8  mov     eax, [ebp+var_45C]
0x100d2ade  mov     eax, [eax+0CCh]
0x100d2ae4  mov     [ebp+var_43C], eax
0x100d2aea  mov     eax, [ebp+var_448]
0x100d2af0  mov     eax, [eax+8]
0x100d2af3  mov     [ebp+var_450], eax
0x100d2af9  mov     [ebp+var_46C], 0
0x100d2b03  mov     [ebp+var_454], 0
0x100d2b0d  mov     [ebp+var_440], 0
0x100d2b17  mov     [ebp+Size], 0
0x100d2b21  mov     [ebp+var_490], 0
0x100d2b2b  mov     [ebp+var_4AC], 0
0x100d2b35  mov     eax, [ebp+var_444]
0x100d2b3b  add     eax, 18h
0x100d2b3e  mov     [ebp+var_458], eax
0x100d2b44  mov     eax, [ebp+var_458]
0x100d2b4a  cmp     dword ptr [eax+8Ch], 4
0x100d2b51  jz      short loc_100D2B8C
0x100d2b53  mov     eax, [ebp+var_458]
0x100d2b59  cmp     dword ptr [eax+8Ch], 5
0x100d2b60  jz      short loc_100D2B8C
0x100d2b62  mov     eax, [ebp+var_458]
0x100d2b68  cmp     dword ptr [eax+8Ch], 2
0x100d2b6f  jz      short loc_100D2B8C
0x100d2b71  mov     eax, [ebp+var_458]
0x100d2b77  cmp     dword ptr [eax+8Ch], 3
0x100d2b7e  jz      short loc_100D2B8C
0x100d2b80  mov     [ebp+var_4C0], 0
0x100d2b8a  jmp     short loc_100D2B96
0x100d2b8c  mov     [ebp+var_4C0], 1
0x100d2b96  mov     eax, [ebp+var_4C0]
0x100d2b9c  mov     [ebp+var_484], eax
0x100d2ba2  mov     [ebp+var_470], 0
0x100d2bac  mov     [ebp+var_464], 0
0x100d2bb6  mov     [ebp+var_4B8], 0
0x100d2bc0  mov     eax, [ebp+var_43C]
0x100d2bc6  movzx   eax, word ptr [eax+0Ch]
0x100d2bca  and     eax, 1
0x100d2bcd  jz      short loc_100D2BDB
0x100d2bcf  mov     [ebp+var_4C4], 1
0x100d2bd9  jmp     short loc_100D2BE5
0x100d2bdb  mov     [ebp+var_4C4], 0
0x100d2be5  mov     eax, [ebp+var_4C4]
0x100d2beb  mov     [ebp+var_4B4], eax
0x100d2bf1  mov     [ebp+var_494], 0
0x100d2bfb  mov     [ebp+var_49C], 0
0x100d2c05  mov     [ebp+var_4A0], 0
0x100d2c0f  mov     eax, [ebp+var_43C]
0x100d2c15  cmp     dword ptr [eax], 0
0x100d2c18  jz      short loc_100D2C27
0x100d2c1a  mov     eax, [ebp+var_43C]
0x100d2c20  mov     eax, [eax]
0x100d2c22  cmp     dword ptr [eax], 0
0x100d2c25  jnz     short loc_100D2C55
0x100d2c27  push    [ebp+var_45C]
0x100d2c2d  mov     edx, [ebp+var_444]
0x100d2c33  mov     ecx, [ebp+arg_0]
0x100d2c36  call    _ErrEnsureRseekConn@12; ErrEnsureRseekConn(x,x,x)
0x100d2c3b  mov     [ebp+var_438], eax
0x100d2c41  cmp     [ebp+var_438], 0
0x100d2c48  jge     short loc_100D2C55
0x100d2c4a  mov     eax, [ebp+var_438]
0x100d2c50  jmp     loc_100D3CFF
0x100d2c55  mov     eax, [ebp+var_43C]
0x100d2c5b  mov     eax, [eax]
0x100d2c5d  mov     eax, [eax]
0x100d2c5f  mov     [ebp+var_44C], eax
0x100d2c65  mov     eax, [ebp+var_450]
0x100d2c6b  mov     [ebp+var_4A4], eax
0x100d2c71  cmp     [ebp+var_4A4], 0
0x100d2c78  jz      short loc_100D2CA2
0x100d2c7a  cmp     [ebp+var_4A4], 2
0x100d2c81  jz      loc_100D2D51
0x100d2c87  cmp     [ebp+var_4A4], 4
0x100d2c8e  jz      loc_100D2D47
0x100d2c94  cmp     [ebp+var_4A4], 32h ; '2'
0x100d2c9b  jz      short loc_100D2D04
0x100d2c9d  jmp     loc_100D2DBC
0x100d2ca2  cmp     _wPreparedInsert, 0
0x100d2ca9  jnz     short loc_100D2CBE
0x100d2cab  cmp     [ebp+var_484], 0
0x100d2cb2  jnz     short loc_100D2CBE
0x100d2cb4  mov     [ebp+var_470], 1
0x100d2cbe  mov     eax, [ebp+var_43C]
0x100d2cc4  add     eax, 424h
0x100d2cc9  mov     [ebp+var_454], eax
0x100d2ccf  mov     eax, [ebp+var_43C]
0x100d2cd5  mov     eax, [eax+408h]
0x100d2cdb  mov     [ebp+var_46C], eax
0x100d2ce1  mov     [ebp+var_494], offset aInsert_0; "(INSERT)"
0x100d2ceb  mov     [ebp+var_49C], 0FFFFF829h
0x100d2cf5  mov     [ebp+var_4A0], 0FFFFE03Dh
0x100d2cff  jmp     loc_100D2DBC
0x100d2d04  mov     eax, [ebp+var_43C]
0x100d2d0a  add     eax, 42Ch
0x100d2d0f  mov     [ebp+var_454], eax
0x100d2d15  mov     eax, [ebp+var_43C]
0x100d2d1b  mov     eax, [eax+418h]
0x100d2d21  mov     [ebp+var_46C], eax
0x100d2d27  mov     [ebp+var_494], offset aDelete_0; "(DELETE)"
0x100d2d31  mov     [ebp+var_49C], 0FFFFF828h
0x100d2d3b  mov     [ebp+var_4A0], 0FFFFE03Eh
0x100d2d45  jmp     short loc_100D2DBC
0x100d2d47  mov     [ebp+var_450], 2
0x100d2d51  cmp     _wPreparedUpdate, 0
0x100d2d58  jnz     short loc_100D2D6D
0x100d2d5a  cmp     [ebp+var_484], 0
0x100d2d61  jnz     short loc_100D2D6D
0x100d2d63  mov     [ebp+var_464], 1
0x100d2d6d  mov     eax, [ebp+var_43C]
0x100d2d73  add     eax, 428h
0x100d2d78  mov     [ebp+var_454], eax
0x100d2d7e  mov     eax, [ebp+var_43C]
0x100d2d84  mov     eax, [eax+410h]
0x100d2d8a  mov     [ebp+var_46C], eax
0x100d2d90  cmp     [ebp+var_46C], 0
0x100d2d97  jnz     short loc_100D2D9E
0x100d2d99  jmp     loc_100D3CB2
0x100d2d9e  mov     [ebp+var_494], offset aUpdate_0; "(UPDATE)"
0x100d2da8  mov     [ebp+var_49C], 0FFFFF827h
0x100d2db2  mov     [ebp+var_4A0], 0FFFFE03Ah
0x100d2dbc  cmp     [ebp+var_470], 0
0x100d2dc3  jnz     short loc_100D2DCE
0x100d2dc5  cmp     [ebp+var_464], 0
0x100d2dcc  jz      short loc_100D2E4D
0x100d2dce  mov     eax, [ebp+var_43C]
0x100d2dd4  mov     eax, [eax+10h]
0x100d2dd7  mov     [ebp+var_474], eax
0x100d2ddd  mov     eax, [ebp+var_43C]
0x100d2de3  movsx   eax, word ptr [eax+0Eh]
0x100d2de7  imul    eax, 18h
0x100d2dea  add     eax, [ebp+var_474]
0x100d2df0  mov     [ebp+var_4C8], eax
0x100d2df6  jmp     short loc_100D2E07
0x100d2df8  mov     eax, [ebp+var_474]
0x100d2dfe  add     eax, 18h
0x100d2e01  mov     [ebp+var_474], eax
0x100d2e07  mov     eax, [ebp+var_474]
0x100d2e0d  cmp     eax, [ebp+var_4C8]
0x100d2e13  jnb     short loc_100D2E27
0x100d2e15  mov     eax, [ebp+var_474]
0x100d2e1b  movzx   eax, word ptr [eax]
0x100d2e1e  and     eax, 40h
0x100d2e21  jz      short loc_100D2E25
0x100d2e23  jmp     short loc_100D2E27
0x100d2e25  jmp     short loc_100D2DF8
0x100d2e27  mov     eax, [ebp+var_474]
0x100d2e2d  cmp     eax, [ebp+var_4C8]
0x100d2e33  jb      short loc_100D2E4D
0x100d2e35  cmp     [ebp+var_464], 0
0x100d2e3c  jz      short loc_100D2E43
0x100d2e3e  jmp     loc_100D3CB2
0x100d2e43  mov     [ebp+var_470], 0
0x100d2e4d  cmp     [ebp+var_470], 0
0x100d2e54  jnz     loc_100D2FB9
0x100d2e5a  cmp     [ebp+var_464], 0
0x100d2e61  jnz     loc_100D2FB9
0x100d2e67  mov     eax, [ebp+var_454]
0x100d2e6d  cmp     dword ptr [eax], 0
0x100d2e70  jnz     loc_100D2F5E
0x100d2e76  mov     eax, [ebp+var_458]
0x100d2e7c  push    dword ptr [eax+10Ch]
0x100d2e82  push    0
0x100d2e84  push    [ebp+var_454]
0x100d2e8a  mov     edx, [ebp+var_44C]
0x100d2e90  mov     ecx, [ebp+arg_0]
0x100d2e93  call    _ErrSQLAllocStmt@20; ErrSQLAllocStmt(x,x,x,x,x)
0x100d2e98  mov     [ebp+var_438], eax
0x100d2e9e  cmp     [ebp+var_438], 0
0x100d2ea5  jge     short loc_100D2EB2
0x100d2ea7  mov     eax, [ebp+var_438]
0x100d2ead  jmp     loc_100D3CFF
0x100d2eb2  push    [ebp+var_46C]
0x100d2eb8  mov     eax, [ebp+var_454]
0x100d2ebe  push    dword ptr [eax]
0x100d2ec0  push    [ebp+var_44C]
0x100d2ec6  mov     edx, [ebp+arg_0]
0x100d2ec9  mov     ecx, [ebp+var_458]
0x100d2ecf  call    _ErrSQLPrepare@20; ErrSQLPrepare(x,x,x,x,x)
0x100d2ed4  mov     [ebp+var_438], eax
0x100d2eda  cmp     [ebp+var_438], 0
0x100d2ee1  jge     short loc_100D2F39
0x100d2ee3  push    [ebp+arg_0]
0x100d2ee6  mov     eax, [ebp+var_454]
0x100d2eec  push    dword ptr [eax]
0x100d2eee  push    1; unsigned int
0x100d2ef0  mov     eax, [ebp+var_454]
0x100d2ef6  push    dword ptr [eax]; void *
0x100d2ef8  mov     eax, _pfnSQLFreeStmt
0x100d2efd  mov     [ebp+var_4CC], eax
0x100d2f03  mov     ecx, [ebp+var_4CC]
0x100d2f09  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100d2f0f  call    [ebp+var_4CC]
0x100d2f15  mov     edx, [ebp+var_44C]
0x100d2f1b  mov     ecx, eax
0x100d2f1d  call    _ErrSQLCheckError@16; ErrSQLCheckError(x,x,x,x)
0x100d2f22  mov     eax, [ebp+var_454]
0x100d2f28  mov     dword ptr [eax], 0
0x100d2f2e  mov     eax, [ebp+var_438]
0x100d2f34  jmp     loc_100D3CFF
0x100d2f39  push    0
0x100d2f3b  mov     edx, [ebp+var_454]
0x100d2f41  mov     ecx, [ebp+var_44C]
0x100d2f47  call    _RegisterHdbcHstmt@12; RegisterHdbcHstmt(x,x,x)
0x100d2f4c  mov     eax, [ebp+var_43C]
0x100d2f52  mov     dword ptr [eax+430h], 1
0x100d2f5c  jmp     short loc_100D2FB9
0x100d2f5e  mov     eax, [ebp+var_43C]
0x100d2f64  cmp     dword ptr [eax+430h], 0
0x100d2f6b  jnz     short loc_100D2FB9
0x100d2f6d  push    [ebp+var_46C]
0x100d2f73  mov     eax, [ebp+var_454]
0x100d2f79  push    dword ptr [eax]
0x100d2f7b  push    [ebp+var_44C]
0x100d2f81  mov     edx, [ebp+arg_0]
0x100d2f84  mov     ecx, [ebp+var_458]
0x100d2f8a  call    _ErrSQLPrepare@20; ErrSQLPrepare(x,x,x,x,x)
0x100d2f8f  mov     [ebp+var_438], eax
0x100d2f95  cmp     [ebp+var_438], 0
0x100d2f9c  jge     short loc_100D2FA9
0x100d2f9e  mov     eax, [ebp+var_438]
0x100d2fa4  jmp     loc_100D3CFF
0x100d2fa9  mov     eax, [ebp+var_43C]
0x100d2faf  mov     dword ptr [eax+430h], 1
0x100d2fb9  cmp     [ebp+var_450], 0
0x100d2fc0  jz      short loc_100D3005
0x100d2fc2  push    0
0x100d2fc4  lea     eax, [ebp+Size]
0x100d2fca  push    eax
0x100d2fcb  push    1FEh
0x100d2fd0  lea     eax, [ebp+Src]
0x100d2fd6  push    eax
0x100d2fd7  push    [ebp+var_448]
0x100d2fdd  mov     edx, [ebp+var_444]
0x100d2fe3  mov     ecx, [ebp+arg_0]
0x100d2fe6  call    _ErrRmtBMOfTTRow@28; ErrRmtBMOfTTRow(x,x,x,x,x,x,x)
0x100d2feb  mov     [ebp+var_438], eax
0x100d2ff1  cmp     [ebp+var_438], 0
0x100d2ff8  jge     short loc_100D3005
0x100d2ffa  mov     eax, [ebp+var_438]
0x100d3000  jmp     loc_100D3CFF
0x100d3005  cmp     [ebp+var_470], 0
0x100d300c  jnz     short loc_100D3017
0x100d300e  cmp     [ebp+var_464], 0
0x100d3015  jz      short loc_100D306A
0x100d3017  mov     eax, [ebp+var_458]
0x100d301d  push    dword ptr [eax+10Ch]
0x100d3023  push    0
0x100d3025  lea     eax, [ebp+var_440]
0x100d302b  push    eax
0x100d302c  mov     edx, [ebp+var_44C]
0x100d3032  mov     ecx, [ebp+arg_0]
0x100d3035  call    _ErrSQLAllocStmt@20; ErrSQLAllocStmt(x,x,x,x,x)
0x100d303a  mov     [ebp+var_438], eax
0x100d3040  cmp     [ebp+var_438], 0
0x100d3047  jge     short loc_100D3054
0x100d3049  mov     eax, [ebp+var_438]
0x100d304f  jmp     loc_100D3CFF
0x100d3054  mov     [ebp+var_4B4], 1
0x100d305e  xor     eax, eax
0x100d3060  inc     eax
0x100d3061  mov     word ptr [ebp+var_48C], ax
0x100d3068  jmp     short loc_100D308B
0x100d306a  mov     eax, [ebp+var_454]
0x100d3070  mov     eax, [eax]
0x100d3072  mov     [ebp+var_440], eax
0x100d3078  mov     [ebp+var_4AC], 0
0x100d3082  xor     eax, eax
0x100d3084  mov     word ptr [ebp+var_48C], ax
0x100d308b  mov     [ebp+var_4B4], 1
0x100d3095  cmp     [ebp+var_450], 0
0x100d309c  jz      loc_100D3248
0x100d30a2  cmp     [ebp+var_4B4], 0
0x100d30a9  jz      loc_100D3248
0x100d30af  mov     [ebp+var_4A8], 0
0x100d30b9  cmp     [ebp+var_464], 0
0x100d30c0  jz      short loc_100D30F0
0x100d30c2  mov     [ebp+var_4D0], 1
0x100d30cc  cmp     [ebp+var_484], 0
0x100d30d3  jnz     short loc_100D30EE
0x100d30d5  mov     eax, [ebp+var_43C]
0x100d30db  cmp     dword ptr [eax+3F8h], 0
0x100d30e2  jnz     short loc_100D30EE
0x100d30e4  mov     [ebp+var_4A8], 1
0x100d30ee  jmp     short loc_100D3156
  ... truncated ...
```
