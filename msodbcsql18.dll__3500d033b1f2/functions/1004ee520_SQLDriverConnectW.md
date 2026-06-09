# SQLDriverConnectW

- ea: `0x1004ee520`
- end: `0x1004ef23d`
- name: `SQLDriverConnectW`
- size: `3357`
- prototype: `SQLRETURN __stdcall(SQLHDBC hdbc, SQLHWND hwnd, SQLWCHAR *szConnStrIn, SQLSMALLINT cchConnStrIn, SQLWCHAR *szConnStrOut, SQLSMALLINT cchConnStrOutMax, SQLSMALLINT *pcchConnStrOut, SQLUSMALLINT fDriverCompletion)`
- caller_count: `0`
- callee_count: `29`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x100406928`
- `0x10046d020`
- `0x10046d140`
- `0x10048b9c4`
- `0x1004e5874`
- `0x1004e7ee8`
- `0x1004e9140`
- `0x1004e9494`
- `0x1004e9708`
- `0x1004eb0b4`
- `0x1004ec37c`
- `0x1004ec4f0`
- `0x1004ee520`
- `0x10051aa9c`
- `0x10051ac58`
- `0x10051e610`
- `0x10051fc98`
- `0x100520370`
- `0x1005212b4`
- `0x100525dbc`
- `0x100545d74`
- `0x100545d84`
- `0x1005468d8`
- `0x100546a7c`
- `0x100546aa8`
- `0x100546b40`
- `0x100548140`
- `0x100548210`
- `0x1005495d0`

## import_xrefs

- `USER32!DialogBoxParamW` at `0x1004eeee1`
- `USER32!DialogBoxParamW` at `0x1004eeee1`
- `USER32!GetDesktopWindow` at `0x1004eeeb9`
- `USER32!GetDesktopWindow` at `0x1004eeeb9`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1004eea49`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1004eea49`
- `api-ms-win-crt-convert-l1-1-0!_wtoi` at `0x1004eeb69`
- `api-ms-win-crt-convert-l1-1-0!_wtoi` at `0x1004eeb69`

## pseudocode

```c
SQLRETURN __stdcall SQLDriverConnectW(
        SQLHDBC hdbc,
        SQLHWND hwnd,
        SQLWCHAR *szConnStrIn,
        SQLSMALLINT cchConnStrIn,
        SQLWCHAR *szConnStrOut,
        SQLSMALLINT cchConnStrOutMax,
        SQLSMALLINT *pcchConnStrOut,
        SQLUSMALLINT fDriverCompletion)
{
  unsigned __int64 v9; // rbx
  int v11; // eax
  __int64 v12; // rdx
  __int64 *v13; // r14
  __int16 v14; // bx
  __int64 v15; // rdx
  __int64 v16; // rcx
  char *v17; // rax
  __int64 v18; // rcx
  char *v19; // rsi
  int v20; // eax
  _BYTE *v21; // rax
  int v22; // eax
  int v23; // eax
  unsigned __int64 v24; // rax
  __int64 v25; // rcx
  __int16 v26; // ax
  LPARAM dwInitParam; // rsi
  HWND v28; // rbx
  __int64 v29; // rax
  HWND v30; // rcx
  int Wizard; // ebx
  int v32; // eax
  int v33; // ecx
  __int64 v34; // rcx
  __int16 v35; // ax
  unsigned __int16 *v36; // r15
  int v37; // eax
  __int16 v38; // ax
  __int16 v40[2]; // [rsp+60h] [rbp-A0h] BYREF
  int v41; // [rsp+64h] [rbp-9Ch]
  HWND v42; // [rsp+68h] [rbp-98h]
  unsigned __int64 v43; // [rsp+70h] [rbp-90h] BYREF
  __int64 v44; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int16 *v45; // [rsp+80h] [rbp-80h]
  SQLSMALLINT *v46; // [rsp+88h] [rbp-78h]
  unsigned __int16 v47[80]; // [rsp+90h] [rbp-70h] BYREF

  v9 = cchConnStrIn;
  v45 = szConnStrOut;
  v42 = hwnd;
  v46 = pcchConnStrOut;
  v40[0] = 0;
  v41 = 0;
  v44 = -1;
  if ( (bidGblFlags & 4) != 0 && off_1005E8178[0] )
    bidScopeEnterW(&v44, off_1005E8178[0], *(unsigned int *)hdbc);
  if ( (bidGblFlags & 0x40002) == 0x40002
    && (unsigned int)ConstrBidActID(v47, 0x50u)
    && (bidGblFlags & 2) != 0
    && off_1005E72F0[0] )
  {
    bidTraceW(0, 1516544, off_1005E72F0[0], *(unsigned int *)hdbc);
  }
  (*(void (__fastcall **)(__int64))(*(_QWORD *)(*((_QWORD *)hdbc + 9) + 32LL) + 8LL))(*((_QWORD *)hdbc + 9) + 32LL);
  v11 = ODBCCheckAsyncConnect((struct tagDBC *)hdbc, v40);
  v12 = 1;
  if ( v11 )
  {
    v13 = (__int64 *)((char *)hdbc + 3176);
    if ( (*(_BYTE *)(*((_QWORD *)hdbc + 397) + 120LL) & 1) != 0 )
    {
LABEL_172:
      v14 = v40[0];
      goto LABEL_170;
    }
    v14 = v40[0];
    if ( v40[0] == 2 )
      goto LABEL_179;
    if ( v40[0] == -1 )
    {
      if ( *((_QWORD *)hdbc + 41) == 1 || *((_QWORD *)hdbc + 93) == 2 )
      {
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_18;
        v15 = 1544201;
        goto LABEL_17;
      }
      goto LABEL_118;
    }
    goto LABEL_104;
  }
  if ( (*((_BYTE *)hdbc + 24) & 0x10) != 0 )
    FreeErrors((struct tagOBJBASE *)hdbc);
  if ( !szConnStrIn || (__int16)(v9 + 0x8000) >= 0 && (_WORD)v9 != 0xFFFD )
  {
    if ( (bidGblFlags & 2) != 0 )
      bidTraceMark(0, 1560585);
    PostSQLErrorEx((struct tagOBJBASE *)hdbc, 0x9E02u, 0, 0xFFFFFFFFFFFFFFFFuLL, 0xFFFFFFFF);
    v14 = -1;
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_18;
    bidTraceMark(0, 1561609);
    goto LABEL_170;
  }
  if ( (_WORD)v9 == 0xFFFD )
  {
    v9 = -1;
    do
      ++v9;
    while ( szConnStrIn[v9] );
  }
  if ( !v9 )
  {
    if ( (bidGblFlags & 2) != 0 )
      bidTraceMark(0, 1572873);
    PostSQLErrorEx((struct tagOBJBASE *)hdbc, 0x9E02u, 0, 0xFFFFFFFFFFFFFFFFuLL, 0xFFFFFFFF);
    v14 = -1;
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_18;
    v15 = 1573897;
    goto LABEL_17;
  }
  v17 = (char *)SQLAllocateMemoryEx(0, 0x720u, 1);
  v13 = (__int64 *)((char *)hdbc + 3176);
  v18 = *((_QWORD *)hdbc + 397);
  v19 = v17;
  if ( v18 )
  {
    CDlgATTRs::Uninitialize((CDlgATTRs *)(v18 + 136));
    v12 = *v13;
    if ( *v13 )
      ((void (__fastcall *)(struct IMalloc *))g_pMO->lpVtbl->Free)(g_pMO);
  }
  *v13 = (__int64)v19;
  if ( !v19
    || (memset_0(v19, 0, 0x88u),
        *((_WORD *)v19 + 96) = 0,
        *((_WORD *)v19 + 129) = 0,
        *((_WORD *)v19 + 770) = 0,
        !CDlgATTRs::FInit(
           (CDlgATTRs *)(v19 + 136),
           0x3Au,
           (const struct tagATTRSTOSECURE *)&g_AttrsToSecure,
           0x3E8u,
           0x200u)) )
  {
    v14 = -1;
    if ( (bidGblFlags & 2) != 0 )
    {
      v15 = 1587209;
      goto LABEL_17;
    }
    goto LABEL_18;
  }
  *((_DWORD *)v19 + 1) = 7;
  *((_QWORD *)v19 + 8) = hdbc;
  if ( *((_DWORD *)hdbc + 787) )
  {
    *((_DWORD *)hdbc + 792) = 0;
    v14 = -1;
    v40[0] = -1;
    *((_DWORD *)hdbc + 787) = 0;
    if ( (bidGblFlags & 2) != 0 )
      bidTraceMark(0, 1886217);
    PostSQLErrorEx((struct tagOBJBASE *)hdbc, 0x9CE0u, 0, 0xFFFFFFFFFFFFFFFFuLL, 0xFFFFFFFF);
    goto LABEL_18;
  }
  v20 = ParseAttrStr(
          (struct tagOBJBASE *)hdbc,
          szConnStrIn,
          v9,
          0x3Bu,
          (struct CDlgATTRs *)(v19 + 136),
          0x1FFFFFFFFFFFFFFuLL);
  if ( v20 )
  {
    v41 = 1;
    if ( v20 < 0 )
    {
      v14 = -1;
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_18;
      v15 = 1604617;
      goto LABEL_17;
    }
  }
  if ( (unsigned int)IsEmbeddedSNAC() )
  {
    v21 = (_BYTE *)*((_QWORD *)v19 + 18);
    if ( (v21[48] & 1) != 0 || (*v21 & 1) != 0 || (v21[24] & 1) != 0 )
    {
      if ( (bidGblFlags & 2) != 0 )
        bidTraceMark(0, 1614857);
      PostSQLErrorEx((struct tagOBJBASE *)hdbc, 0x9E02u, 0, 0xFFFFFFFFFFFFFFFFuLL, 0xFFFFFFFF);
      v14 = -1;
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_18;
      v15 = 1615881;
      goto LABEL_17;
    }
  }
  v22 = FillAttrStructFromDSN((struct tagDBC *)hdbc, (struct tagDLGSTRUCT *)v19, v42);
  _mm_lfence();
  if ( v22 < 0 )
  {
    if ( (bidGblFlags & 2) != 0 )
      bidTraceMark(0, 1622025);
    PostSQLErrorEx((struct tagOBJBASE *)hdbc, 0x9E02u, 0, 0xFFFFFFFFFFFFFFFFuLL, 0xFFFFFFFF);
    v14 = -1;
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_18;
    v15 = 1623049;
    goto LABEL_17;
  }
  if ( (*(_BYTE *)(*((_QWORD *)v19 + 18) + 1368LL) & 1) != 0 )
  {
    _mm_lfence();
    if ( (*(_BYTE *)(*((_QWORD *)v19 + 18) + 192LL) & 1) != 0 )
    {
      _mm_lfence();
      if ( !_wcsicmp(
              (const wchar_t *)(*(_QWORD *)(*((_QWORD *)v19 + 18) + 200LL) + *(_QWORD *)(*((_QWORD *)v19 + 19) + 32LL)),
              L"Yes") )
      {
        _mm_lfence();
        if ( (bidGblFlags & 2) != 0 )
          bidTraceMark(0, 1631241);
        PostSQLErrorEx((struct tagOBJBASE *)hdbc, 0x9DA0u, 0, 0xFFFFFFFFFFFFFFFFuLL, 0xFFFFFFFF);
        v14 = -1;
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_18;
        v15 = 1632265;
        goto LABEL_17;
      }
    }
  }
  _mm_lfence();
  v23 = SetOptionFlag(
          (const struct CDlgATTRs *)(v19 + 136),
          43,
          L"Yes",
          L"No",
          (unsigned __int64 *)(*((_QWORD *)v19 + 8) + 760LL));
  _mm_lfence();
  if ( v23 == 1 )
  {
    if ( (bidGblFlags & 2) != 0 )
      bidTraceMark(0, 1640457);
    PostSQLErrorEx((struct tagOBJBASE *)hdbc, 0x9E02u, 0, 0xFFFFFFFFFFFFFFFFuLL, 0xFFFFFFFF);
    v14 = -1;
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_18;
    v15 = 1641481;
    goto LABEL_17;
  }
  if ( (*(_BYTE *)(*((_QWORD *)v19 + 18) + 1320LL) & 1) != 0 )
  {
    _mm_lfence();
    if ( !*(_QWORD *)(*((_QWORD *)v19 + 8) + 216LL) )
    {
      _mm_lfence();
      *(_QWORD *)(*((_QWORD *)v19 + 8) + 216LL) = _wtoi((const wchar_t *)(*(_QWORD *)(*((_QWORD *)v19 + 18) + 1328LL)
                                                                        + *(_QWORD *)(*((_QWORD *)v19 + 19) + 32LL)));
    }
  }
  if ( !fDriverCompletion )
  {
    _mm_lfence();
    if ( (*(_BYTE *)(*((_QWORD *)v19 + 18) + 144LL) & 2) == 0 && *((_QWORD *)hdbc + 93) != 6 )
    {
      _mm_lfence();
      *(_QWORD *)(*((_QWORD *)v19 + 18) + 152LL) = 0;
      *(_QWORD *)(*((_QWORD *)v19 + 18) + 160LL) = 0;
    }
    if ( (*(_BYTE *)(*((_QWORD *)v19 + 18) + 96LL) & 1) != 0 )
    {
      _mm_lfence();
      if ( (*(_BYTE *)(*((_QWORD *)v19 + 18) + 120LL) & 1) == 0 )
      {
        _mm_lfence();
        if ( (*(_BYTE *)(*((_QWORD *)v19 + 18) + 336LL) & 1) == 0 )
        {
          _mm_lfence();
          if ( (bidGblFlags & 2) != 0 )
            bidTraceMark(0, 1670153);
          PostSQLErrorEx((struct tagOBJBASE *)hdbc, 0x9D22u, 0, 0xFFFFFFFFFFFFFFFFuLL, 0xFFFFFFFF);
          v14 = -1;
          if ( (bidGblFlags & 2) == 0 )
            goto LABEL_18;
          v15 = 1671177;
          goto LABEL_17;
        }
      }
    }
  }
  *((_WORD *)v19 + 59) = fDriverCompletion;
  if ( !fDriverCompletion )
    goto LABEL_106;
  if ( *((_QWORD *)hdbc + 423) )
  {
    _mm_lfence();
    if ( (bidGblFlags & 2) != 0 )
      bidTraceMark(0, 1679369);
    PostSQLErrorEx((struct tagOBJBASE *)hdbc, 0xA1BEu, 0, 0xFFFFFFFFFFFFFFFFuLL, 0xFFFFFFFF);
    v14 = -1;
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_18;
    v15 = 1680393;
    goto LABEL_17;
  }
  if ( fDriverCompletion != 2
    && ((_mm_lfence(), (*(_BYTE *)(*((_QWORD *)v19 + 18) + 48LL) & 1) != 0)
     || (_mm_lfence(), (*(_BYTE *)(*((_QWORD *)v19 + 18) + 120LL) & 1) != 0)
     || (_mm_lfence(), (*(_BYTE *)(*((_QWORD *)v19 + 18) + 336LL) & 1) != 0))
    && (*((_QWORD *)hdbc + 41) == 1
     || (v24 = *((_QWORD *)hdbc + 93), v24 <= 7) && (v25 = 212, _bittest64(&v25, v24))
     || *((_QWORD *)hdbc + 423)
     || (_mm_lfence(), (*(_BYTE *)(*((_QWORD *)v19 + 18) + 144LL) & 2) != 0)
     && (_mm_lfence(), (*(_BYTE *)(*((_QWORD *)v19 + 18) + 168LL) & 2) != 0)) )
  {
LABEL_106:
    _mm_lfence();
    v40[0] = DoDlgConnection(0, (struct tagDLGSTRUCT *)v19, 1u);
    v14 = v40[0];
    if ( v40[0] == -1 )
    {
      if ( fDriverCompletion && *((_QWORD *)hdbc + 41) != 1 && *((_QWORD *)hdbc + 93) != 2 && !*((_QWORD *)hdbc + 423) )
      {
        _mm_lfence();
        ProcessErrors((struct tagDLGSTRUCT *)v19);
        v26 = *((_WORD *)v19 + 60);
        if ( (v26 & 1) != 0 )
        {
          if ( (bidGblFlags & 2) != 0 )
            bidTraceMark(0, 1719305);
          v14 = v40[0];
          goto LABEL_18;
        }
        v14 = v40[0];
        *((_WORD *)v19 + 60) = v26 | 1;
        goto LABEL_118;
      }
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_18;
      v15 = 1710089;
LABEL_17:
      bidTraceMark(0, v15);
      goto LABEL_18;
    }
  }
  else
  {
    v14 = v40[0];
    *((_WORD *)v19 + 60) &= ~1u;
  }
LABEL_104:
  if ( v14 == 2 )
    goto LABEL_179;
LABEL_118:
  dwInitParam = *v13;
  if ( !*v13 )
    goto LABEL_170;
  UnProtectPwdAttr((struct tagDBC *)hdbc, (struct CDlgATTRs *)(dwInitParam + 136), 7);
  UnProtectPwdAttr((struct tagDBC *)hdbc, (struct CDlgATTRs *)(dwInitParam + 136), 57);
  if ( (*(_BYTE *)(dwInitParam + 120) & 4) != 0 )
  {
    *(_DWORD *)hdbc = bidUpdateItemIDW(*(unsigned int *)hdbc, off_1005E83F8[0], (char *)hdbc + 3312);
    v32 = ConfigureKeystore((struct tagDBC *)hdbc, (struct CDlgATTRs *)(dwInitParam + 136));
    v33 = v41;
    v14 = v40[0];
    if ( v32 )
      v33 = 1;
    v41 = v33;
  }
  else if ( *(_WORD *)(dwInitParam + 118) )
  {
    v28 = v42;
    if ( !v42 )
      goto LABEL_133;
    v29 = *(_QWORD *)(dwInitParam + 144);
    if ( (*(_BYTE *)v29 & 1) != 0 )
    {
      v30 = v42;
      *(_WORD *)(dwInitParam + 120) ^= (*(_WORD *)(dwInitParam + 120) ^ (32 * ~*(_WORD *)(v29 + 120))) & 0x20;
      Wizard = CreateWizard(v30, (struct tagDLGSTRUCT *)dwInitParam);
      if ( Wizard <= 0 )
      {
        _mm_lfence();
        v12 = *(_QWORD *)(*(_QWORD *)(dwInitParam + 64) + 64LL);
        if ( v12 )
        {
          _mm_lfence();
          ExportImp::SQLDisconnect(*(ExportImp **)(dwInitParam + 64), (struct tagDBC *)v12);
        }
      }
    }
    else
    {
      if ( v28 == GetDesktopWindow() )
        v28 = 0;
      Wizard = (__int16)DialogBoxParamW(
                          g_hinstance_language,
                          (LPCWSTR)0x7918,
                          v28,
                          (DLGPROC)ConnectDlgProc,
                          dwInitParam);
    }
    if ( Wizard == -1 )
    {
LABEL_133:
      if ( (bidGblFlags & 2) != 0 )
        bidTraceMark(0, 1779721);
      PostSQLErrorEx((struct tagOBJBASE *)hdbc, 0x9CCDu, 0, 0xFFFFFFFFFFFFFFFFuLL, 0xFFFFFFFF);
      v14 = -1;
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_18;
      v15 = 1780745;
      goto LABEL_17;
    }
    if ( !Wizard )
    {
      v14 = 100;
      goto LABEL_18;
    }
    v14 = (*(_WORD *)(dwInitParam + 120) >> 3) & 1;
    v40[0] = v14;
  }
  if ( v14 == -1 )
    goto LABEL_170;
  if ( (**(_BYTE **)(dwInitParam + 144) & 1) != 0 )
  {
LABEL_149:
    v34 = *(_QWORD *)(dwInitParam + 144);
    if ( (*(_BYTE *)(v34 + 48) & 1) != 0 )
    {
      v35 = *(_WORD *)(v34 + 120);
      if ( (v35 & 4) != 0 )
        *(_WORD *)(v34 + 120) = v35 & 0xFFFE;
    }
    v36 = v45;
    v37 = 0;
    v43 = 0;
    if ( cchConnStrOutMax > 0 )
      v37 = cchConnStrOutMax;
    if ( (unsigned int)OutputConnString((struct CDlgATTRs *)(dwInitParam + 136), 2u, 0x39u, v45, v37, &v43, 0) )
    {
      if ( v36 && cchConnStrOutMax > 0 )
      {
        if ( (bidGblFlags & 2) != 0 )
          bidTraceMark(0, 1846281);
        PostSQLErrorEx((struct tagOBJBASE *)hdbc, 0x9DDAu, 0, 0xFFFFFFFFFFFFFFFFuLL, 0xFFFFFFFF);
      }
      v14 = 1;
      v40[0] = 1;
    }
    if ( v46 )
    {
      v38 = v43;
      v12 = 0x7FFF;
      if ( v43 > 0x7FFF )
        v38 = 0x7FFF;
      *v46 = v38;
    }
    if ( (bidGblFlags & 2) != 0 && v36 && cchConnStrOutMax > 0 )
    {
      if ( off_1005E72F8[0] )
      {
        _mm_lfence();
        bidTraceW(0, 1860608, off_1005E72F8[0], (unsigned int)cchConnStrOutMax);
        v14 = v40[0];
        goto LABEL_170;
      }
      goto LABEL_172;
    }
LABEL_170:
    if ( v14 == 2 )
      goto LABEL_179;
    goto LABEL_18;
  }
  if ( CDlgATTRs::SetATTRValue((CDlgATTRs *)(dwInitParam + 136), 11, (const unsigned __int16 *)hdbc + 2758) >= 0 )
  {
    _mm_lfence();
    if ( CDlgATTRs::SetATTRValue((CDlgATTRs *)(dwInitParam + 136), 12, (const unsigned __int16 *)hdbc + 2629) < 0 )
    {
      v14 = -1;
      if ( (bidGblFlags & 2) != 0 )
      {
        v15 = 1819657;
        goto LABEL_17;
      }
      goto LABEL_18;
    }
    v14 = v40[0];
    goto LABEL_149;
  }
  v14 = -1;
  if ( (bidGblFlags & 2) != 0 )
  {
    v15 = 1813513;
    goto LABEL_17;
  }
LABEL_18:
  v16 = *((_QWORD *)hdbc + 397);
  if ( v16 )
  {
    CDlgATTRs::Uninitialize((CDlgATTRs *)(v16 + 136));
    v12 = *((_QWORD *)hdbc + 397);
    if ( v12 )
      ((void (__fastcall *)(struct IMalloc *))g_pMO->lpVtbl->Free)(g_pMO);
    *((_QWORD *)hdbc + 397) = 0;
  }
LABEL_179:
  if ( !v14 )
    v14 = v41 != 0;
  (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)(*((_QWORD *)hdbc + 9) + 32LL) + 24LL))(
    *((_QWORD *)hdbc + 9) + 32LL,
    v12);
  if ( (bidGblFlags & 2) != 0 )
    v14 = _bidx_SNACOdbc_ErrCode(0, 0x1CB409u, v14);
  _bidCAutoScopeAnchor::Out((_bidCAutoScopeAnchor *)&v44);
  return v14;
}

```

## disassembly

```asm
0x1004ee520  push    rbp
0x1004ee522  push    rbx
0x1004ee523  push    rsi
0x1004ee524  push    rdi
0x1004ee525  push    r12
0x1004ee527  push    r13
0x1004ee529  push    r14
0x1004ee52b  push    r15
0x1004ee52d  lea     rbp, [rsp-48h]
0x1004ee532  sub     rsp, 148h
0x1004ee539  mov     rax, cs:__security_cookie
0x1004ee540  xor     rax, rsp
0x1004ee543  mov     [rbp+80h+var_50], rax
0x1004ee547  mov     r10, [rbp+80h+pcchConnStrOut]
0x1004ee54e  xor     r14d, r14d
0x1004ee551  movzx   r13d, [rbp+80h+fDriverCompletion]
0x1004ee559  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1004ee55d  test    byte ptr cs:_bidGblFlags, 4
0x1004ee564  mov     r15, r8
0x1004ee567  movsx   rbx, r9w
0x1004ee56b  mov     rdi, rcx
0x1004ee56e  mov     r9, [rbp+80h+szConnStrOut]
0x1004ee575  mov     [rbp+80h+var_100], r9
0x1004ee579  mov     [rsp+180h+var_118], rdx
0x1004ee57e  mov     [rbp+80h+var_F8], r10
0x1004ee582  mov     [rsp+180h+var_120], r14w
0x1004ee588  mov     [rsp+180h+var_11C], r14d
0x1004ee58d  mov     [rsp+180h+var_108], rsi
0x1004ee592  jz      short loc_1004EE5E3
0x1004ee594  mov     rax, cs:off_1005E8178; "<SQLDriverConnectW|API|ODBC|DRIVER> %u#"...
0x1004ee59b  test    rax, rax
0x1004ee59e  jz      short loc_1004EE5E3
0x1004ee5a0  movsx   ecx, [rbp+80h+cchConnStrOutMax]
0x1004ee5a7  mov     [rsp+180h+var_128], r13d
0x1004ee5ac  mov     [rsp+180h+var_130], r10
0x1004ee5b1  mov     [rsp+180h+var_138], ecx
0x1004ee5b5  lea     rcx, [rsp+180h+var_108]
0x1004ee5ba  mov     [rsp+180h+var_140], r9
0x1004ee5bf  mov     r9, rdi
0x1004ee5c2  mov     [rsp+180h+var_148], ebx
0x1004ee5c6  mov     qword ptr [rsp+180h+var_150], r8
0x1004ee5cb  mov     r8d, [rdi]
0x1004ee5ce  mov     dword ptr [rsp+180h+var_158], ebx
0x1004ee5d2  mov     [rsp+180h+dwInitParam], rdx
0x1004ee5d7  mov     rdx, cs:off_1005E8178; "<SQLDriverConnectW|API|ODBC|DRIVER> %u#"...
0x1004ee5de  call    _bidScopeEnterW
0x1004ee5e3  mov     eax, cs:_bidGblFlags
0x1004ee5e9  mov     ecx, 40002h
0x1004ee5ee  and     eax, ecx
0x1004ee5f0  mov     r12d, 2
0x1004ee5f6  cmp     eax, ecx
0x1004ee5f8  jnz     short loc_1004EE64C
0x1004ee5fa  lea     edx, [r12+4Eh]; unsigned __int64
0x1004ee5ff  lea     rcx, [rbp+80h+var_F0]; unsigned __int16 *
0x1004ee603  call    ?ConstrBidActID@@YAHPEAG_K@Z; ConstrBidActID(ushort *,unsigned __int64)
0x1004ee608  test    eax, eax
0x1004ee60a  jz      short loc_1004EE64C
0x1004ee60c  test    byte ptr cs:_bidGblFlags, r12b
0x1004ee613  jz      short loc_1004EE64C
0x1004ee615  mov     rax, cs:off_1005E72F0; "<SQLDriverConnectW|ODBC|DRIVER> %u#{%ls"...
0x1004ee61c  test    rax, rax
0x1004ee61f  jz      short loc_1004EE64C
0x1004ee621  mov     r9d, [rdi]
0x1004ee624  lea     rax, [rbp+80h+var_F0]
0x1004ee628  mov     r8, cs:off_1005E72F0; "<SQLDriverConnectW|ODBC|DRIVER> %u#{%ls"...
0x1004ee62f  mov     edx, 172400h
0x1004ee634  mov     [rsp+180h+var_158], rax
0x1004ee639  xor     ecx, ecx
0x1004ee63b  lea     rax, aDbc; "DBC"
0x1004ee642  mov     [rsp+180h+dwInitParam], rax; unsigned int
0x1004ee647  call    _bidTraceW
0x1004ee64c  mov     rcx, [rdi+48h]
0x1004ee650  add     rcx, 20h ; ' '
0x1004ee654  mov     rax, [rcx]
0x1004ee657  mov     rax, [rax+8]
0x1004ee65b  call    cs:__guard_dispatch_icall_fptr
0x1004ee661  lea     rdx, [rsp+180h+var_120]; __int16 *
0x1004ee666  mov     rcx, rdi; struct tagDBC *
0x1004ee669  call    ?ODBCCheckAsyncConnect@@YAHPEAUtagDBC@@PEAF@Z; ODBCCheckAsyncConnect(tagDBC *,short *)
0x1004ee66e  mov     edx, 1
0x1004ee673  test    eax, eax
0x1004ee675  jz      loc_1004EE720
0x1004ee67b  lea     r14, [rdi+0C68h]
0x1004ee682  mov     r15d, edx
0x1004ee685  mov     rax, [r14]
0x1004ee688  test    [rax+78h], r15b
0x1004ee68c  jnz     loc_1004EF157
0x1004ee692  movzx   ebx, [rsp+180h+var_120]
0x1004ee697  cmp     bx, r12w
0x1004ee69b  jz      loc_1004EF1CB
0x1004ee6a1  cmp     bx, si
0x1004ee6a4  jnz     loc_1004EED4A
0x1004ee6aa  cmp     [rdi+148h], rdx
0x1004ee6b1  jz      short loc_1004EE6C0
0x1004ee6b3  cmp     [rdi+2E8h], r12
0x1004ee6ba  jnz     loc_1004EEE06
0x1004ee6c0  test    byte ptr cs:_bidGblFlags, r12b
0x1004ee6c7  jz      short loc_1004EE6D5
0x1004ee6c9  mov     edx, 179009h
0x1004ee6ce  xor     ecx, ecx
0x1004ee6d0  call    _bidTraceMark
0x1004ee6d5  xor     r15d, r15d
0x1004ee6d8  mov     rcx, [rdi+0C68h]
0x1004ee6df  test    rcx, rcx
0x1004ee6e2  jz      loc_1004EF1CE
0x1004ee6e8  add     rcx, 88h; this
0x1004ee6ef  call    ?Uninitialize@CDlgATTRs@@QEAAXXZ; CDlgATTRs::Uninitialize(void)
0x1004ee6f4  mov     rdx, [rdi+0C68h]
0x1004ee6fb  test    rdx, rdx
0x1004ee6fe  jz      short loc_1004EE714
0x1004ee700  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x1004ee707  mov     rax, [rcx]
0x1004ee70a  mov     rax, [rax+28h]
0x1004ee70e  call    cs:__guard_dispatch_icall_fptr
0x1004ee714  mov     [rdi+0C68h], r15
0x1004ee71b  jmp     loc_1004EF1CE
0x1004ee720  test    byte ptr [rdi+18h], 10h
0x1004ee724  jz      short loc_1004EE733
0x1004ee726  mov     rcx, rdi; struct tagOBJBASE *
0x1004ee729  call    ?FreeErrors@@YAXPEAUtagOBJBASE@@@Z; FreeErrors(tagOBJBASE *)
0x1004ee72e  mov     edx, 1
0x1004ee733  test    r15, r15
0x1004ee736  jz      loc_1004EF17D
0x1004ee73c  mov     ecx, 8000h
0x1004ee741  lea     eax, [rcx+rbx]
0x1004ee744  test    cx, ax
0x1004ee747  jnz     short loc_1004EE753
0x1004ee749  cmp     bx, 0FFFDh
0x1004ee74d  jnz     loc_1004EF17D
0x1004ee753  cmp     bx, 0FFFDh
0x1004ee757  jnz     short loc_1004EE766
0x1004ee759  mov     rbx, rsi
0x1004ee75c  inc     rbx
0x1004ee75f  cmp     [r15+rbx*2], r14w
0x1004ee764  jnz     short loc_1004EE75C
0x1004ee766  test    rbx, rbx
0x1004ee769  jnz     short loc_1004EE7B1
0x1004ee76b  test    byte ptr cs:_bidGblFlags, r12b
0x1004ee772  jz      short loc_1004EE780
0x1004ee774  mov     edx, 180009h
0x1004ee779  xor     ecx, ecx
0x1004ee77b  call    _bidTraceMark
0x1004ee780  or      dword ptr [rsp+180h+dwInitParam], 0FFFFFFFFh
0x1004ee785  mov     edx, 9E02h; unsigned __int16
0x1004ee78a  mov     r9, rsi; unsigned __int64
0x1004ee78d  xor     r8d, r8d; int
0x1004ee790  mov     rcx, rdi; struct tagOBJBASE *
0x1004ee793  call    ?PostSQLErrorEx@@YAFPEAUtagOBJBASE@@GJ_KK@Z; PostSQLErrorEx(tagOBJBASE *,ushort,long,unsigned __int64,ulong)
0x1004ee798  test    byte ptr cs:_bidGblFlags, r12b
0x1004ee79f  mov     ebx, esi
0x1004ee7a1  jz      loc_1004EE6D5
0x1004ee7a7  mov     edx, 180409h
0x1004ee7ac  jmp     loc_1004EE6CE
0x1004ee7b1  mov     r8d, edx; int
0x1004ee7b4  xor     ecx, ecx; struct tagOBJBASE *
0x1004ee7b6  mov     edx, 720h; dwBytes
0x1004ee7bb  call    ?SQLAllocateMemoryEx@@YAPEAXPEAUtagOBJBASE@@_KH@Z; SQLAllocateMemoryEx(tagOBJBASE *,unsigned __int64,int)
0x1004ee7c0  lea     r14, [rdi+0C68h]
0x1004ee7c7  xor     r12d, r12d
0x1004ee7ca  mov     rcx, [r14]
0x1004ee7cd  mov     rsi, rax
0x1004ee7d0  test    rcx, rcx
0x1004ee7d3  jz      short loc_1004EE7FD
0x1004ee7d5  add     rcx, 88h; this
0x1004ee7dc  call    ?Uninitialize@CDlgATTRs@@QEAAXXZ; CDlgATTRs::Uninitialize(void)
0x1004ee7e1  mov     rdx, [r14]
0x1004ee7e4  test    rdx, rdx
0x1004ee7e7  jz      short loc_1004EE7FD
0x1004ee7e9  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x1004ee7f0  mov     rax, [rcx]
0x1004ee7f3  mov     rax, [rax+28h]
0x1004ee7f7  call    cs:__guard_dispatch_icall_fptr
0x1004ee7fd  mov     [r14], rsi
0x1004ee800  test    rsi, rsi
0x1004ee803  jz      loc_1004EF15E
0x1004ee809  xor     edx, edx; Val
0x1004ee80b  mov     r8d, 88h; Size
0x1004ee811  mov     rcx, rsi; void *
0x1004ee814  call    memset_0
0x1004ee819  mov     [rsi+0C0h], r12w
0x1004ee821  lea     r8, ?g_AttrsToSecure@@3UtagATTRSTOSECURE@@B; struct tagATTRSTOSECURE *
0x1004ee828  mov     [rsi+102h], r12w
0x1004ee830  mov     edx, 3Ah ; ':'; unsigned __int16
0x1004ee835  mov     [rsi+604h], r12w
0x1004ee83d  mov     r9d, 3E8h; unsigned __int64
0x1004ee843  lea     r12, [rsi+88h]
0x1004ee84a  mov     [rsp+180h+dwInitParam], 200h; unsigned int
0x1004ee853  mov     rcx, r12; this
0x1004ee856  call    ?FInit@CDlgATTRs@@QEAAHGAEBUtagATTRSTOSECURE@@_K1@Z; CDlgATTRs::FInit(ushort,tagATTRSTOSECURE const &,unsigned __int64,unsigned __int64)
0x1004ee85b  xor     ecx, ecx
0x1004ee85d  test    eax, eax
0x1004ee85f  jz      loc_1004EF15E
0x1004ee865  mov     dword ptr [rsi+4], 7
0x1004ee86c  mov     [rsi+40h], rdi
0x1004ee870  mov     eax, [rdi+0C4Ch]
0x1004ee876  test    eax, eax
0x1004ee878  jz      short loc_1004EE8C7
0x1004ee87a  or      r15, 0FFFFFFFFFFFFFFFFh
0x1004ee87e  mov     [rdi+0C60h], ecx
0x1004ee884  movzx   ebx, r15w
0x1004ee888  lea     r12d, [rcx+2]
0x1004ee88c  mov     [rsp+180h+var_120], bx
0x1004ee891  mov     [rdi+0C4Ch], ecx
0x1004ee897  test    byte ptr cs:_bidGblFlags, r12b
0x1004ee89e  jz      short loc_1004EE8AA
0x1004ee8a0  mov     edx, 1CC809h
0x1004ee8a5  call    _bidTraceMark
0x1004ee8aa  or      dword ptr [rsp+180h+dwInitParam], 0FFFFFFFFh
0x1004ee8af  mov     edx, 9CE0h; unsigned __int16
0x1004ee8b4  mov     r9, r15; unsigned __int64
0x1004ee8b7  xor     r8d, r8d; int
0x1004ee8ba  mov     rcx, rdi; struct tagOBJBASE *
0x1004ee8bd  call    ?PostSQLErrorEx@@YAFPEAUtagOBJBASE@@GJ_KK@Z; PostSQLErrorEx(tagOBJBASE *,ushort,long,unsigned __int64,ulong)
0x1004ee8c2  jmp     loc_1004EE6D5
0x1004ee8c7  mov     rax, 1FFFFFFFFFFFFFFh
0x1004ee8d1  mov     r9d, 3Bh ; ';'; unsigned __int16
0x1004ee8d7  mov     [rsp+180h+var_158], rax; unsigned __int64
0x1004ee8dc  mov     r8, rbx; unsigned __int64
0x1004ee8df  mov     rdx, r15; unsigned __int16 *
0x1004ee8e2  mov     [rsp+180h+dwInitParam], r12; unsigned int
0x1004ee8e7  mov     rcx, rdi; struct tagOBJBASE *
0x1004ee8ea  call    ?ParseAttrStr@@YAJPEAUtagOBJBASE@@PEBG_KGAEAVCDlgATTRs@@2@Z; ParseAttrStr(tagOBJBASE *,ushort const *,unsigned __int64,ushort,CDlgATTRs &,unsigned __int64)
0x1004ee8ef  xor     ebx, ebx
0x1004ee8f1  lea     r15d, [rbx+1]
0x1004ee8f5  test    eax, eax
0x1004ee8f7  jz      short loc_1004EE91F
0x1004ee8f9  mov     [rsp+180h+var_11C], r15d
0x1004ee8fe  jns     short loc_1004EE91F
0x1004ee900  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1004ee904  lea     r12d, [r15+1]
0x1004ee908  test    byte ptr cs:_bidGblFlags, r12b
0x1004ee90f  jz      loc_1004EE6D5
0x1004ee915  mov     edx, 187C09h
0x1004ee91a  jmp     loc_1004EE6CE
0x1004ee91f  call    ?IsEmbeddedSNAC@@YAHXZ; IsEmbeddedSNAC(void)
0x1004ee924  test    eax, eax
0x1004ee926  jz      short loc_1004EE992
0x1004ee928  mov     rax, [rsi+90h]
0x1004ee92f  test    [rax+30h], r15b
0x1004ee933  jnz     short loc_1004EE940
0x1004ee935  test    [rax], r15b
0x1004ee938  jnz     short loc_1004EE940
0x1004ee93a  test    [rax+18h], r15b
0x1004ee93e  jz      short loc_1004EE992
0x1004ee940  mov     r12d, 2
0x1004ee946  test    byte ptr cs:_bidGblFlags, r12b
0x1004ee94d  jz      short loc_1004EE95B
0x1004ee94f  mov     edx, 18A409h
0x1004ee954  xor     ecx, ecx
0x1004ee956  call    _bidTraceMark
0x1004ee95b  or      dword ptr [rsp+180h+dwInitParam], 0FFFFFFFFh
0x1004ee960  or      r15, 0FFFFFFFFFFFFFFFFh
0x1004ee964  mov     r9, r15; unsigned __int64
0x1004ee967  mov     edx, 9E02h; unsigned __int16
0x1004ee96c  xor     r8d, r8d; int
0x1004ee96f  mov     rcx, rdi; struct tagOBJBASE *
0x1004ee972  call    ?PostSQLErrorEx@@YAFPEAUtagOBJBASE@@GJ_KK@Z; PostSQLErrorEx(tagOBJBASE *,ushort,long,unsigned __int64,ulong)
0x1004ee977  test    byte ptr cs:_bidGblFlags, r12b
0x1004ee97e  movzx   ebx, r15w
0x1004ee982  jz      loc_1004EE6D5
0x1004ee988  mov     edx, 18A809h
0x1004ee98d  jmp     loc_1004EE6CE
0x1004ee992  mov     r8, [rsp+180h+var_118]; HWND
0x1004ee997  mov     rdx, rsi; struct tagDLGSTRUCT *
0x1004ee99a  mov     rcx, rdi; struct tagDBC *
0x1004ee99d  call    ?FillAttrStructFromDSN@@YAJPEAUtagDBC@@PEAUtagDLGSTRUCT@@PEAUHWND__@@@Z; FillAttrStructFromDSN(tagDBC *,tagDLGSTRUCT *,HWND__ *)
0x1004ee9a2  lfence
0x1004ee9a5  test    eax, eax
0x1004ee9a7  jns     short loc_1004EE9FB
0x1004ee9a9  mov     r12d, 2
0x1004ee9af  test    byte ptr cs:_bidGblFlags, r12b
0x1004ee9b6  jz      short loc_1004EE9C4
0x1004ee9b8  mov     edx, 18C009h
0x1004ee9bd  xor     ecx, ecx
0x1004ee9bf  call    _bidTraceMark
0x1004ee9c4  or      dword ptr [rsp+180h+dwInitParam], 0FFFFFFFFh
0x1004ee9c9  or      r15, 0FFFFFFFFFFFFFFFFh
0x1004ee9cd  mov     r9, r15; unsigned __int64
0x1004ee9d0  mov     edx, 9E02h; unsigned __int16
0x1004ee9d5  xor     r8d, r8d; int
0x1004ee9d8  mov     rcx, rdi; struct tagOBJBASE *
0x1004ee9db  call    ?PostSQLErrorEx@@YAFPEAUtagOBJBASE@@GJ_KK@Z; PostSQLErrorEx(tagOBJBASE *,ushort,long,unsigned __int64,ulong)
0x1004ee9e0  test    byte ptr cs:_bidGblFlags, r12b
0x1004ee9e7  movzx   ebx, r15w
0x1004ee9eb  jz      loc_1004EE6D5
0x1004ee9f1  mov     edx, 18C409h
0x1004ee9f6  jmp     loc_1004EE6CE
0x1004ee9fb  mov     rax, [rsi+90h]
0x1004eea02  test    [rax+558h], r15b
0x1004eea09  jz      loc_1004EEAA6
0x1004eea0f  lfence
0x1004eea12  mov     rax, [rsi+90h]
0x1004eea19  test    [rax+0C0h], r15b
0x1004eea20  jz      loc_1004EEAA6
0x1004eea26  lfence
0x1004eea29  mov     rdx, [rsi+90h]
0x1004eea30  mov     rax, [rsi+98h]
0x1004eea37  mov     rcx, [rax+20h]
0x1004eea3b  add     rcx, [rdx+0C8h]; String1
0x1004eea42  lea     rdx, aYes_1; "Yes"
  ... truncated ...
```
