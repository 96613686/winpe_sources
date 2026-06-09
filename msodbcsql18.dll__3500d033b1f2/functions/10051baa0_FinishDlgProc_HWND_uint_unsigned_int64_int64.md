# FinishDlgProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x10051baa0`
- end: `0x10051cdec`
- name: `?FinishDlgProc@@YA_JPEAUHWND__@@I_K_J@Z`
- size: `4940`
- prototype: `INT_PTR __stdcall(HWND, UINT, WPARAM, LPARAM)`
- caller_count: `0`
- callee_count: `30`
- tags: `installer_update`

## callees

- `0x1004070bc`
- `0x10046d140`
- `0x1004bc288`
- `0x1004ea8d8`
- `0x1004eaf58`
- `0x1004eb0b4`
- `0x1004eb81c`
- `0x1004ebd04`
- `0x1004ec470`
- `0x1004fa5c0`
- `0x1005188a4`
- `0x100518ac4`
- `0x10051ac58`
- `0x10051baa0`
- `0x10051cfa0`
- `0x100520be4`
- `0x100521310`
- `0x100522bdc`
- `0x100526b90`
- `0x100526d38`
- `0x100529b4c`
- `0x100535e58`
- `0x10053f624`
- `0x100546a7c`
- `0x100546f80`
- `0x1005470b0`
- `0x100547180`
- `0x100548140`
- `0x100548210`
- `0x1005495d0`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x10051bb56`
- `KERNEL32!CreateEventW` at `0x10051bb56`
- `KERNEL32!WaitForSingleObject` at `0x10051bb91`
- `KERNEL32!WaitForSingleObject` at `0x10051bb91`
- `KERNEL32!CloseHandle` at `0x10051bb9e`
- `KERNEL32!CloseHandle` at `0x10051bb9e`
- `USER32!LoadStringW` at `0x10051bc59`
- `USER32!LoadStringW` at `0x10051bc95`
- `USER32!LoadStringW` at `0x10051c07d`
- `USER32!LoadStringW` at `0x10051c0bc`
- `USER32!LoadStringW` at `0x10051c36d`
- `USER32!LoadStringW` at `0x10051c452`
- `USER32!LoadStringW` at `0x10051c4d1`
- `USER32!LoadStringW` at `0x10051c51d`
- `USER32!LoadStringW` at `0x10051c5d8`
- `USER32!LoadStringW` at `0x10051c665`
- `USER32!LoadStringW` at `0x10051cac2`
- `USER32!LoadStringW` at `0x10051bc59`
- `USER32!LoadStringW` at `0x10051bc95`
- `USER32!LoadStringW` at `0x10051c07d`
- `USER32!LoadStringW` at `0x10051c0bc`
- `USER32!LoadStringW` at `0x10051c36d`
- `USER32!LoadStringW` at `0x10051c452`
- `USER32!LoadStringW` at `0x10051c4d1`
- `USER32!LoadStringW` at `0x10051c51d`
- `USER32!LoadStringW` at `0x10051c5d8`
- `USER32!LoadStringW` at `0x10051c665`
- `USER32!LoadStringW` at `0x10051cac2`
- `USER32!SetDlgItemTextW` at `0x10051cd79`
- `USER32!SetDlgItemTextW` at `0x10051cd79`
- `USER32!NotifyWinEvent` at `0x10051c6ac`
- `USER32!NotifyWinEvent` at `0x10051c6ac`
- `USER32!SetWindowLongPtrW` at `0x10051c6e2`
- `USER32!SetWindowLongPtrW` at `0x10051c7a5`
- `USER32!SetWindowLongPtrW` at `0x10051c6e2`
- `USER32!SetWindowLongPtrW` at `0x10051c7a5`
- `USER32!GetWindowLongPtrW` at `0x10051bafd`
- `USER32!GetWindowLongPtrW` at `0x10051bafd`
- `USER32!SetWindowTextW` at `0x10051c697`
- `USER32!SetWindowTextW` at `0x10051c697`
- `USER32!SetForegroundWindow` at `0x10051bb18`
- `USER32!SetForegroundWindow` at `0x10051bb18`
- `USER32!UpdateWindow` at `0x10051c723`
- `USER32!UpdateWindow` at `0x10051c723`
- `USER32!EnableMenuItem` at `0x10051bbc3`
- `USER32!EnableMenuItem` at `0x10051c76a`
- `USER32!EnableMenuItem` at `0x10051bbc3`
- `USER32!EnableMenuItem` at `0x10051c76a`
- `USER32!GetSystemMenu` at `0x10051bbad`
- `USER32!GetSystemMenu` at `0x10051bbad`
- `USER32!EnableWindow` at `0x10051c73f`
- `USER32!EnableWindow` at `0x10051c73f`
- `USER32!SetFocus` at `0x10051c758`
- `USER32!SetFocus` at `0x10051c758`
- `USER32!GetDlgItem` at `0x10051bbe2`
- `USER32!GetDlgItem` at `0x10051c687`
- `USER32!GetDlgItem` at `0x10051c733`
- `USER32!GetDlgItem` at `0x10051c74f`
- `USER32!GetDlgItem` at `0x10051cda5`
- `USER32!GetDlgItem` at `0x10051bbe2`
- `USER32!GetDlgItem` at `0x10051c687`
- `USER32!GetDlgItem` at `0x10051c733`
- `USER32!GetDlgItem` at `0x10051c74f`
- `USER32!GetDlgItem` at `0x10051cda5`
- `USER32!EndDialog` at `0x10051c786`
- `USER32!EndDialog` at `0x10051c786`
- `USER32!PostMessageA` at `0x10051c718`
- `USER32!PostMessageA` at `0x10051cdb9`
- `USER32!PostMessageA` at `0x10051c718`
- `USER32!PostMessageA` at `0x10051cdb9`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x10051c295`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x10051c2d2`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x10051c432`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x10051c4b1`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x10051c566`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x10051cb96`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x10051c295`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x10051c2d2`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x10051c432`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x10051c4b1`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x10051c566`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x10051cb96`
- `api-ms-win-crt-runtime-l1-1-0!_beginthreadex` at `0x10051bb7a`
- `api-ms-win-crt-runtime-l1-1-0!_beginthreadex` at `0x10051bb7a`
- `api-ms-win-crt-convert-l1-1-0!_wtol` at `0x10051c326`
- `api-ms-win-crt-convert-l1-1-0!_wtol` at `0x10051c326`

## string_xrefs

- `0x10051bdaf`: `SQLServerDriver##TEMPDSN`
- `0x10051be35`: `SQLServerDriver##TEMPDSN`
- `0x10051bec5`: `SQLServerDriver##TEMPDSN`
- `0x10051c0e5`: `SQLServerDriver##TEMPDSN`

## pseudocode

```c
INT_PTR __fastcall FinishDlgProc(HWND a1, int a2, __int64 a3, LONG_PTR a4)
{
  __int16 v5; // r14
  HWND v6; // r12
  int v7; // edx
  LONG_PTR WindowLongPtrW; // rax
  INT_PTR v9; // rsi
  LONG_PTR v10; // rdi
  uintptr_t v11; // rax
  void *v12; // rcx
  struct tagDBC *v13; // rdx
  ExportImp **v14; // r15
  __int64 v15; // r8
  struct tagENV **v16; // rdx
  _WORD *v17; // rcx
  _WORD *v18; // rax
  struct tagDBC *v19; // rdx
  struct tagDBC **v20; // r8
  struct tagENV *v21; // rdx
  __int64 v22; // rcx
  __int16 v23; // dx
  __int64 v24; // rcx
  const WCHAR *v25; // rcx
  const WCHAR *v26; // rax
  __int64 v27; // rax
  __int64 v28; // rcx
  __int16 v29; // ax
  unsigned __int16 v30; // r13
  unsigned int v31; // r9d
  __int16 v32; // ax
  struct tagSTMT *v33; // rdx
  SQLSMALLINT v34; // r13
  WCHAR *v35; // r8
  __int64 v36; // rdx
  int *p_Buffer; // rcx
  __int16 v38; // ax
  int *v39; // rax
  struct tagDBC *v40; // rdx
  ExportImp *v41; // rcx
  ExportImp *v42; // rbx
  struct tagENV *v43; // rdx
  HWND v44; // rbx
  int v45; // eax
  HWND v46; // rax
  HWND v47; // rax
  unsigned int FormattedMessage; // eax
  __int64 v50; // rdx
  __int64 v51; // rcx
  signed int v52; // edi
  int v53; // eax
  unsigned int StringW; // eax
  _WORD *v55; // r8
  __int64 v56; // r9
  __int64 v57; // rdx
  __int64 v58; // r9
  __int64 v59; // r8
  __int64 v60; // r9
  _WORD *v61; // r8
  char *v62; // rcx
  char *v63; // r10
  int v64; // eax
  int v65; // r9d
  HWND v66; // rax
  unsigned int InitFlaga[2]; // [rsp+20h] [rbp-E0h]
  unsigned int InitFlag[2]; // [rsp+20h] [rbp-E0h]
  unsigned int *ThrdAddr; // [rsp+28h] [rbp-D8h]
  unsigned __int16 *pcbStringLength; // [rsp+30h] [rbp-D0h]
  __int16 *v71; // [rsp+40h] [rbp-C0h]
  SQLHANDLE handle; // [rsp+48h] [rbp-B8h] BYREF
  HWND hWnd; // [rsp+50h] [rbp-B0h]
  __int16 v74; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v75; // [rsp+60h] [rbp-A0h]
  ExportImp *v76; // [rsp+68h] [rbp-98h] BYREF
  SQLSMALLINT v77[2]; // [rsp+74h] [rbp-8Ch] BYREF
  HWND DlgItem; // [rsp+78h] [rbp-88h]
  HMENU hMenu; // [rsp+80h] [rbp-80h]
  __int16 v80[12]; // [rsp+88h] [rbp-78h] BYREF
  WCHAR szRetBuffer[32]; // [rsp+A0h] [rbp-60h] BYREF
  int Buffer; // [rsp+E0h] [rbp-20h] BYREF
  wchar_t String[774]; // [rsp+E4h] [rbp-1Ch] BYREF
  WCHAR v84[512]; // [rsp+6F0h] [rbp+5F0h] BYREF

  v75 = a3;
  hWnd = a1;
  v5 = a3;
  v6 = a1;
  v7 = a2 - 272;
  if ( v7 )
  {
    if ( v7 != 1 )
      return 0;
    WindowLongPtrW = GetWindowLongPtrW(a1, -21);
    v9 = 0;
    v10 = WindowLongPtrW;
    if ( *(_QWORD *)(WindowLongPtrW + 1800) )
    {
      SetForegroundWindow(*(HWND *)(WindowLongPtrW + 1808));
      return 0;
    }
    if ( v5 == 1 || v5 == 2 )
    {
      LOBYTE(v9) = v5 == 1;
      EndDialog(v6, v9);
      return 1;
    }
    if ( v5 != 30717 )
      return 0;
    *(_QWORD *)(WindowLongPtrW + 1816) = CreateEventW(0, 1, 0, 0);
    v11 = _beginthreadex(0, 0, TestDlgThread, (void *)v10, 0, 0);
    v12 = *(void **)(v10 + 1816);
    *(_QWORD *)(v10 + 1800) = v11;
    WaitForSingleObject(v12, 0xFFFFFFFF);
    CloseHandle(*(HANDLE *)(v10 + 1816));
    hMenu = GetSystemMenu(*(HWND *)(v10 + 1808), 0);
    EnableMenuItem(hMenu, 0xF060u, 3u);
    memset_0(&Buffer, 0, 0x608u);
    LODWORD(pcbStringLength) = 2;
    LODWORD(ThrdAddr) = 6;
    InitFlaga[0] = 18;
    DlgItem = GetDlgItem(v6, 30700);
    LoadFormattedMessage(
      g_hinstance_language,
      0x9C62u,
      (unsigned __int16 *)&Buffer,
      0x304u,
      *(_QWORD *)InitFlaga,
      ThrdAddr);
    AppendTestDlgMsg(*(HWND *)(v10 + 1808), (unsigned __int16 *)&Buffer);
    AppendTestDlgMsg(*(HWND *)(v10 + 1808), L"\r\n\r\n");
    LoadStringW(g_hinstance_language, 0x9C66u, (LPWSTR)&Buffer, 772);
    AppendTestDlgMsg(*(HWND *)(v10 + 1808), (unsigned __int16 *)&Buffer);
    AppendTestDlgMsg(*(HWND *)(v10 + 1808), L"\r\n\r\n");
    LoadStringW(g_hinstance_language, 0x9C67u, (LPWSTR)&Buffer, 772);
    AppendTestDlgMsg(*(HWND *)(v10 + 1808), (unsigned __int16 *)&Buffer);
    AppendTestDlgMsg(*(HWND *)(v10 + 1808), L"\r\n");
    v14 = (ExportImp **)(v10 + 64);
    if ( (*(_BYTE *)(v10 + 120) & 4) != 0 )
    {
      ExportImp::SQLDisconnect(*v14, v13);
      *(_WORD *)(v10 + 120) &= ~4u;
    }
    *(_QWORD *)(v10 + 72) = *v14;
    v15 = 641;
    *v14 = 0;
    v16 = (struct tagENV **)(*(_QWORD *)(*(_QWORD *)(v10 + 144) + 56LL) + *(_QWORD *)(*(_QWORD *)(v10 + 152) + 32LL));
    v17 = (_WORD *)(v10 + 258);
    do
    {
      if ( v15 == -2147483005 )
        break;
      if ( !*(_WORD *)v16 )
        break;
      *v17 = *(_WORD *)v16;
      v16 = (struct tagENV **)((char *)v16 + 2);
      ++v17;
      --v15;
    }
    while ( v15 );
    v18 = v17 - 1;
    if ( v15 )
      v18 = v17;
    *v18 = 0;
    *(_WORD *)(v10 + 120) ^= (*(_WORD *)(v10 + 120) ^ (16 * *(_WORD *)(v10 + 120))) & 0x200;
    LOWORD(v71) = ExportImp::SQLAllocEnv((ExportImp *)&v76, v16);
    if ( !(_WORD)v71 )
    {
      *((_QWORD *)v76 + 13) = 3;
      LOWORD(v71) = ExportImp::SQLAllocConnect(v76, (struct tagENV *)(v10 + 64), v20);
      if ( (_WORD)v71 )
      {
        ExportImp::SQLFreeEnv(v76, v21);
      }
      else
      {
        SQLRemoveDSNFromIniW(L"SQLServerDriver##TEMPDSN");
        memset_0(szRetBuffer, 0, sizeof(szRetBuffer));
        v22 = *(_QWORD *)(v10 + 144);
        if ( (*(_BYTE *)(v22 + 96) & 1) != 0 || (*(_BYTE *)(v22 + 48) & 1) != 0 )
        {
          v23 = *(_WORD *)(v22 + 48) & 1;
          if ( v23 )
            v24 = *(_QWORD *)(v22 + 56);
          else
            v24 = *(_QWORD *)(v22 + 104);
          v25 = (const WCHAR *)(*(_QWORD *)(*(_QWORD *)(v10 + 152) + 32LL) + v24);
          v26 = L"ODBCINST.INI";
          if ( v23 )
            v26 = L"ODBC.INI";
          SQLGetPrivateProfileStringW(v25, L"ADALuseWAM", &szDefault, szRetBuffer, 64, v26);
        }
        if ( CDlgATTRs::SetATTRValue((CDlgATTRs *)(v10 + 136), 2, L"SQLServerDriver##TEMPDSN") >= 0 )
        {
          _mm_lfence();
          v27 = *(_QWORD *)(v10 + 144);
          *(_WORD *)(v10 + 120) |= 0x20u;
          *(_WORD *)(v27 + 264) &= ~4u;
          *(_WORD *)(*(_QWORD *)(v10 + 144) + 288LL) &= ~4u;
          if ( (*(_BYTE *)(*(_QWORD *)(v10 + 144) + 96LL) & 1) != 0
            || CDlgATTRs::SetATTRValue((CDlgATTRs *)(v10 + 136), 4, L"ODBC Driver 18 for SQL Server") >= 0 )
          {
            SaveDSNAttributes(0, (struct tagDLGSTRUCT *)v10, 1);
            if ( szRetBuffer[0] )
              SQLWritePrivateProfileStringW(L"SQLServerDriver##TEMPDSN", L"ADALuseWAM", szRetBuffer, L"ODBC.INI");
            *((_WORD *)*v14 + 1244) &= ~2u;
            if ( (*(_BYTE *)(*(_QWORD *)(v10 + 144) + 456LL) & 0x20) != 0 )
              *((_WORD *)*v14 + 1244) |= 2u;
            SyncConnAttrWithKeyVal(*v14, (struct CDlgATTRs *)(v10 + 136));
            *((_QWORD *)*v14 + 18) = 15;
            *((_DWORD *)*v14 + 345) = 15000;
            if ( (*(_BYTE *)(*(_QWORD *)(v10 + 144) + 912LL) & 1) != 0
              && (GetAuthenticationModeValue((struct CDlgATTRs *)(v10 + 136)) == 3
               || GetAuthenticationModeValue((struct CDlgATTRs *)(v10 + 136)) == 4
               || GetAuthenticationModeValue((struct CDlgATTRs *)(v10 + 136)) == 7) )
            {
              v28 = *(_QWORD *)(v10 + 144);
              v29 = *(_WORD *)(v28 + 144);
              if ( (v29 & 1) != 0 )
              {
                *(_WORD *)(v28 + 144) = v29 & 0xFFF7;
                *(_WORD *)(*(_QWORD *)(v10 + 144) + 144LL) &= ~4u;
              }
            }
            if ( DoDlgConnection(hWnd, (struct tagDLGSTRUCT *)v10, 7u) == -1 )
            {
              LOWORD(pcbStringLength) = 772;
              if ( !ExportImp::SQLGetDiagRecW(
                      (ExportImp *)2,
                      (__int16)*v14,
                      (void *)1,
                      (__int16)v80,
                      0,
                      &Buffer,
                      pcbStringLength,
                      (__int16)&v74,
                      v71) )
              {
                v30 = 1;
                do
                {
                  if ( v80[0] != 48 || v80[1] != 49 )
                  {
                    AppendTestDlgMsg(*(HWND *)(v10 + 1808), (unsigned __int16 *)&Buffer);
                    AppendTestDlgMsg(*(HWND *)(v10 + 1808), L"\r\n");
                  }
                  LOWORD(pcbStringLength) = 772;
                  ++v30;
                }
                while ( !ExportImp::SQLGetDiagRecW(
                           (ExportImp *)2,
                           (__int16)*v14,
                           (void *)v30,
                           (__int16)v80,
                           0,
                           &Buffer,
                           pcbStringLength,
                           (__int16)&v74,
                           v71) );
              }
              v75 = -1;
            }
            else
            {
              LoadStringW(g_hinstance_language, 0x9C68u, (LPWSTR)&Buffer, 772);
              AppendTestDlgMsg(*(HWND *)(v10 + 1808), (unsigned __int16 *)&Buffer);
              AppendTestDlgMsg(*(HWND *)(v10 + 1808), L"\r\n");
              LoadStringW(g_hinstance_language, 0x9C69u, (LPWSTR)&Buffer, 772);
              AppendTestDlgMsg(*(HWND *)(v10 + 1808), (unsigned __int16 *)&Buffer);
              AppendTestDlgMsg(*(HWND *)(v10 + 1808), L"\r\n");
            }
            SQLRemoveDSNFromIniW(L"SQLServerDriver##TEMPDSN");
            if ( v75 != -1 )
            {
              _mm_lfence();
              v31 = *((_DWORD *)*v14 + 344);
              handle = (SQLHANDLE)*((_QWORD *)*v14 + 12);
              v32 = ExecImmediate((struct tagSTMT *)handle, g_szSqlCharsetQuery, -3, v31, 1);
              LOWORD(v71) = v32;
              if ( (v32 & 0xFFFE) == 0 )
              {
                LOWORD(v71) = ExportImp::SQLFetch((ExportImp *)handle, v33);
                if ( !(_WORD)v71 )
                  LOWORD(v71) = ExportImp::SQLGetData(
                                  (ExportImp *)handle,
                                  (struct tagSTMT *)1,
                                  0xFFF8u,
                                  (__int16)&Buffer,
                                  (void *)0x608,
                                  0,
                                  (__int64 *)pcbStringLength);
                Cancel((struct tagSTMT *)handle, 0);
                v32 = (__int16)v71;
              }
              if ( v32 == -1 )
              {
                if ( !SQLGetDiagFieldW(3, handle, 1, 6, &Buffer, 1540, v77) )
                {
                  v34 = 1;
                  do
                  {
                    AppendTestDlgMsg(*(HWND *)(v10 + 1808), (unsigned __int16 *)&Buffer);
                    AppendTestDlgMsg(*(HWND *)(v10 + 1808), L"\r\n");
                    ++v34;
                  }
                  while ( !SQLGetDiagFieldW(3, handle, v34, 6, &Buffer, 1540, v77) );
                }
                v75 = -1;
              }
              else
              {
                _mm_lfence();
                if ( !_wcsicmp((const wchar_t *)&Buffer, L"ISO_1") )
                {
                  v36 = 772;
                  p_Buffer = &Buffer;
                  do
                  {
                    if ( v36 == -2147482874 )
                      break;
                    v38 = *(_WORD *)((char *)p_Buffer + (char *)L"cp1252" - (char *)&Buffer);
                    if ( !v38 )
                      break;
                    *(_WORD *)p_Buffer = v38;
                    p_Buffer = (int *)((char *)p_Buffer + 2);
                    --v36;
                  }
                  while ( v36 );
                  v39 = (int *)((char *)p_Buffer - 2);
                  if ( v36 )
                    v39 = p_Buffer;
                  *(_WORD *)v39 = 0;
                }
                if ( _wtol(String) != *((_DWORD *)*v14 + 609) )
                {
                  _mm_lfence();
                  if ( (*(_BYTE *)(*(_QWORD *)(v10 + 144) + 456LL) & 0x20) == 0 )
                  {
                    _mm_lfence();
                    LoadStringW(g_hinstance_language, 0x9C72u, (LPWSTR)&Buffer, 772);
                    AppendTestDlgMsg(*(HWND *)(v10 + 1808), (unsigned __int16 *)&Buffer);
                    AppendTestDlgMsg(*(HWND *)(v10 + 1808), L"\r\n");
                  }
                }
              }
              if ( (*(_BYTE *)(*(_QWORD *)(v10 + 144) + 312LL) & 1) != 0 )
              {
                _mm_lfence();
                if ( (*(_BYTE *)(*(_QWORD *)(v10 + 144) + 336LL) & 1) != 0 )
                {
                  _mm_lfence();
                  if ( _wcsicmp(
                         (const wchar_t *)(*(_QWORD *)(*(_QWORD *)(v10 + 152) + 32LL)
                                         + *(_QWORD *)(*(_QWORD *)(v10 + 144) + 320LL)),
                         L"DBNETLIB") )
                  {
                    _mm_lfence();
                    v35 = (WCHAR *)(*(_QWORD *)(*(_QWORD *)(v10 + 152) + 32LL)
                                  + *(_QWORD *)(*(_QWORD *)(v10 + 144) + 320LL));
                  }
                  else
                  {
                    v35 = &szLocDefault;
                  }
                  LoadFormattedMessage(
                    g_hinstance_language,
                    0x9C74u,
                    (unsigned __int16 *)&Buffer,
                    0x304u,
                    v35,
                    *(_QWORD *)(*(_QWORD *)(v10 + 152) + 32LL) + *(_QWORD *)(*(_QWORD *)(v10 + 144) + 344LL));
                  AppendTestDlgMsg(*(HWND *)(v10 + 1808), (unsigned __int16 *)&Buffer);
                  AppendTestDlgMsg(*(HWND *)(v10 + 1808), L"\r\n");
                }
              }
              if ( !*((_QWORD *)*v14 + 62) )
              {
                _mm_lfence();
                if ( !_wcsicmp(
                        (const wchar_t *)(*(_QWORD *)(*(_QWORD *)(v10 + 152) + 32LL)
                                        + *(_QWORD *)(*(_QWORD *)(v10 + 144) + 416LL)),
                        L"Yes") )
                {
                  _mm_lfence();
                  LoadStringW(g_hinstance_language, 0x9C75u, (LPWSTR)&Buffer, 772);
                  AppendTestDlgMsg(*(HWND *)(v10 + 1808), (unsigned __int16 *)&Buffer);
                  AppendTestDlgMsg(*(HWND *)(v10 + 1808), L"\r\n");
                }
              }
              if ( *((_QWORD *)*v14 + 61) )
              {
                _mm_lfence();
                if ( !_wcsicmp(
                        (const wchar_t *)(*(_QWORD *)(*(_QWORD *)(v10 + 152) + 32LL)
                                        + *(_QWORD *)(*(_QWORD *)(v10 + 144) + 368LL)),
                        L"No") )
                {
                  _mm_lfence();
                  LoadStringW(g_hinstance_language, 0x9C76u, (LPWSTR)&Buffer, 772);
                  AppendTestDlgMsg(*(HWND *)(v10 + 1808), (unsigned __int16 *)&Buffer);
                  AppendTestDlgMsg(*(HWND *)(v10 + 1808), L"\r\n");
                }
                LoadStringW(g_hinstance_language, 40056 - (*((_QWORD *)*v14 + 66) != 0), (LPWSTR)&Buffer, 772);
                AppendTestDlgMsg(*(HWND *)(v10 + 1808), (unsigned __int16 *)&Buffer);
                AppendTestDlgMsg(*(HWND *)(v10 + 1808), L"\r\n");
              }
              if ( *((_QWORD *)*v14 + 63) )
              {
                _mm_lfence();
                if ( _wcsicmp(*((const wchar_t **)*v14 + 63), (const wchar_t *)*v14 + 3796) )
                {
                  _mm_lfence();
                  LoadFormattedMessage(
                    g_hinstance_language,
                    0x9C79u,
                    (unsigned __int16 *)&Buffer,
                    0x304u,
                    (char *)*v14 + 7592);
                  AppendTestDlgMsg(*(HWND *)(v10 + 1808), (unsigned __int16 *)&Buffer);
                  AppendTestDlgMsg(*(HWND *)(v10 + 1808), L"\r\n");
                }
              }
            }
            goto LABEL_87;
          }
        }
      }
    }
    v75 = -1;
LABEL_87:
    if ( (*(_BYTE *)(v10 + 120) & 4) != 0 )
    {
      LoadStringW(g_hinstance_language, 0x9C6Au, (LPWSTR)&Buffer, 772);
      AppendTestDlgMsg(*(HWND *)(v10 + 1808), (unsigned __int16 *)&Buffer);
      AppendTestDlgMsg(*(HWND *)(v10 + 1808), L"\r\n");
      ExportImp::SQLDisconnect(*v14, v40);
      *(_WORD *)(v10 + 120) &= ~4u;
    }
    v41 = *v14;
    if ( *v14 )
    {
      v42 = (ExportImp *)*((_QWORD *)v41 + 11);
      ExportImp::SQLFreeConnect(v41, v19);
      *v14 = 0;
      ExportImp::SQLFreeEnv(v42, v43);
    }
    AppendTestDlgMsg(*(HWND *)(v10 + 1808), L"\r\n");
    LoadStringW(g_hinstance_language, 40044 - (v75 != -1), (LPWSTR)&Buffer, 772);
    AppendTestDlgMsg(*(HWND *)(v10 + 1808), (unsigned __int16 *)&Buffer);
    v44 = GetDlgItem(*(HWND *)(v10 + 1808), 30719);
    SetWindowTextW(v44, (LPCWSTR)&Buffer);
    NotifyWinEvent(0x8019u, v44, -4, 0);
    *v14 = *(ExportImp **)(v10 + 72);
    v45 = CDlgATTRs::SetATTRValue((CDlgATTRs *)(v10 + 136), 2, (const unsigned __int16 *)(v10 + 258));
    _mm_lfence();
    if ( v45 >= 0 )
    {
      *(_WORD *)(v10 + 120) ^= (*(_WORD *)(v10 + 120) ^ (*(_WORD *)(v10 + 120) >> 4)) & 0x20;
      if ( !(_WORD)v71 )
      {
        PostMessageA(DlgItem, 0xB1u, 0xFFFFFFFFFFFFFFFFuLL, -1);
        UpdateWindow(DlgItem);
      }
      v46 = GetDlgItem(*(HWND *)(v10 + 1808), 1);
      EnableWindow(v46, 1);
      v47 = GetDlgItem(*(HWND *)(v10 + 1808), 1);
      SetFocus(v47);
      EnableMenuItem(hMenu, 0xF060u, 0);
    }
    else
    {
      SetWindowLongPtrW(hWnd, 0, -1);
    }
    return 0;
  }
  handle = 0;
  *(_QWORD *)(a4 + 1800) = 0;
  SetWindowLongPtrW(a1, -21, a4);
  CenterDialog(v6);
  if ( CreateExtBufferEx((struct tagOBJBASE *)a4, (struct ext_buffer **)&handle, 0x7D0u, 0x200u, 1) )
    return 0;
  InitFlag[0] = 18;
  FormattedMessage = LoadFormattedMessage(g_hinstance_language, 0x9C62u, v84, 0x200u, *(_QWORD *)InitFlag, 6, 2);
  if ( WriteToExtBufferEx((struct tagOBJBASE *)a4, (struct ext_buffer **)&handle, v84, 2LL * FormattedMessage, 1) )
  {
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_184;
    v50 = 4675593;
    goto LABEL_102;
  }
  if ( WriteToExtBufferEx((struct tagOBJBASE *)a4, (struct ext_buffer **)&handle, L"\r\n", 4, 1) )
  {
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_184;
    v50 = 4678665;
LABEL_102:
    bidTraceMark(0, v50);
    goto LABEL_184;
  }
  v51 = 24;
  v52 = 1;
  v76 = (ExportImp *)24;
  v75 = (__int64)&off_1005A14C8;
  while ( 1 )
  {
    if ( (unsigned int)(v52 - 1) <= 1 && (*(_BYTE *)(v51 + *(_QWORD *)(a4 + 144)) & 1) != 0
      || (unsigned int)(v52 - 21) <= 1 && (*(_BYTE *)(*(_QWORD *)(a4 + 144) + 480LL) & 0x20) == 0 )
    {
      goto LABEL_142;
    }
    switch ( v52 )
    {
      case 24:
        if ( (*(_BYTE *)(*(_QWORD *)(a4 + 144) + 552LL) & 0x20) == 0 )
          goto LABEL_142;
        break;
      case 28:
        if ( (*(_BYTE *)(*(_QWORD *)(a4 + 144) + 672LL) & 0x20) == 0 )
          goto LABEL_142;
        break;
      case 18:
        if ( (*(_BYTE *)(*(_QWORD *)(a4 + 144) + 264LL) & 0x20) == 0 )
          goto LABEL_142;
        goto LABEL_115;
    }
    if ( v52 == 29 )
    {
      if ( (*(_BYTE *)(*(_QWORD *)(a4 + 144) + 696LL) & 0x20) == 0 )
        goto LABEL_142;
      goto LABEL_130;
    }
LABEL_115:
    if ( v52 == 30 )
    {
      if ( (*(_BYTE *)(*(_QWORD *)(a4 + 144) + 720LL) & 0x20) == 0 )
        goto LABEL_142;
      goto LABEL_117;
    }
LABEL_130:
    if ( v52 == 31 )
    {
      if ( (*(_BYTE *)(*(_QWORD *)(a4 + 144) + 744LL) & 0x20) == 0 )
        goto LABEL_142;
      goto LABEL_132;
    }
LABEL_117:
    if ( v52 == 32 )
    {
      if ( (*(_BYTE *)(*(_QWORD *)(a4 + 144) + 768LL) & 0x20) == 0 )
        goto LABEL_142;
      goto LABEL_119;
    }
LABEL_132:
    if ( v52 == 37 )
    {
      if ( (*(_BYTE *)(*(_QWORD *)(a4 + 144) + 888LL) & 0x20) == 0 )
        goto LABEL_142;
      goto LABEL_134;
    }
LABEL_119:
    if ( v52 == 36 )
    {
      if ( (*(_BYTE *)(*(_QWORD *)(a4 + 144) + 864LL) & 0x20) == 0 )
        goto LABEL_142;
      goto LABEL_121;
    }
LABEL_134:
    if ( v52 == 33 )
    {
      if ( (*(_BYTE *)(*(_QWORD *)(a4 + 144) + 792LL) & 0x20) == 0 )
        goto LABEL_142;
      goto LABEL_136;
    }
LABEL_121:
    if ( v52 == 34 )
    {
      if ( (*(_BYTE *)(*(_QWORD *)(a4 + 144) + 816LL) & 0x20) == 0 )
        goto LABEL_142;
      goto LABEL_123;
    }
LABEL_136:
    if ( v52 == 43 )
    {
      if ( (*(_BYTE *)(*(_QWORD *)(a4 + 144) + 1032LL) & 0x20) == 0 )
        goto LABEL_142;
      goto LABEL_138;
    }
LABEL_123:
    if ( v52 == 8 )
    {
      if ( (*(_BYTE *)(v51 + *(_QWORD *)(a4 + 144)) & 1) == 0 )
        goto LABEL_174;
      goto LABEL_142;
    }
LABEL_138:
    if ( v52 != 38 || (*(_BYTE *)(v51 + *(_QWORD *)(a4 + 144)) & 1) == 0 )
    {
      if ( (unsigned int)v52 > 0x1B )
        goto LABEL_174;
      v53 = 245078056;
      if ( !_bittest(&v53, v52) )
        goto LABEL_174;
    }
LABEL_142:
    if ( WriteToExtBufferEx((struct tagOBJBASE *)a4, (struct ext_buffer **)&handle, L"\r\n", 4, 1) )
      break;
    StringW = LoadStringW(g_hinstance_language, *(unsigned __int16 *)(v75 - 4), v84, 512);
    WriteToExtBufferEx((struct tagOBJBASE *)a4, (struct ext_buffer **)&handle, v84, 2LL * StringW, 1);
    if ( WriteToExtBufferEx((struct tagOBJBASE *)a4, (struct ext_buffer **)&handle, L": ", 4, 1) )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_183;
      v57 = 4724745;
      goto LABEL_182;
    }
    if ( v52 == 12 )
    {
      if ( (*(_BYTE *)(*(_QWORD *)(a4 + 144) + 288LL) & 0x20) == 0 )
      {
        v55 = (_WORD *)(a4 + 1540);
        v56 = -1;
        do
          ++v56;
        while ( v55[v56] );
        if ( WriteToExtBufferEx((struct tagOBJBASE *)a4, (struct ext_buffer **)&handle, v55, 2 * v56, 1) )
        {
          if ( (bidGblFlags & 2) == 0 )
            goto LABEL_183;
          v57 = 4732937;
          goto LABEL_182;
        }
        goto LABEL_174;
      }
    }
    else if ( v52 == 5
           && !_wcsicmp(
                 (const wchar_t *)(*(_QWORD *)(*(_QWORD *)(a4 + 152) + 32LL) + *(_QWORD *)(*(_QWORD *)(a4 + 144) + 128LL)),
                 L"(local)") )
    {
      v58 = -1;
      do
        ++v58;
      while ( *(&g_wszLocal + v58) );
      if ( WriteToExtBufferEx((struct tagOBJBASE *)a4, (struct ext_buffer **)&handle, &g_wszLocal, 2 * v58, 1) )
      {
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_183;
        v57 = 4741129;
        goto LABEL_182;
      }
      goto LABEL_174;
    }
    v59 = *(_QWORD *)(a4 + 144);
    if ( (*((_BYTE *)v76 + v59) & 0x20) != 0 )
    {
      if ( v52 != 5 )
      {
        v60 = -1;
        v61 = *(_WORD **)v75;
        do
          ++v60;
        while ( v61[v60] );
        if ( WriteToExtBufferEx((struct tagOBJBASE *)a4, (struct ext_buffer **)&handle, v61, 2 * v60, 1) )
        {
          if ( (bidGblFlags & 2) == 0 )
            goto LABEL_183;
          v57 = 4749321;
          goto LABEL_182;
        }
        goto LABEL_174;
      }
    }
    else if ( v52 == 16 )
    {
      v62 = (char *)(*(_QWORD *)(*(_QWORD *)(a4 + 152) + 32LL) + *(_QWORD *)(v59 + 368));
      v63 = (char *)((char *)off_1005D1780 - v62);
      do
      {
        v64 = *(unsigned __int16 *)&v63[(_QWORD)v62];
        v65 = *(unsigned __int16 *)v62 - v64;
        if ( v65 )
          break;
        v62 += 2;
      }
      while ( v64 );
      if ( !v65 )
      {
        if ( WriteToExtBufferEx((struct tagOBJBASE *)a4, (struct ext_buffer **)&handle, L"No", 4, 1) )
        {
          if ( (bidGblFlags & 2) == 0 )
            goto LABEL_183;
          v57 = 4759561;
          goto LABEL_182;
        }
        goto LABEL_174;
      }
    }
    if ( WriteToExtBufferEx(
           (struct tagOBJBASE *)a4,
           (struct ext_buffer **)&handle,
           (const void *)(*(_QWORD *)(*(_QWORD *)(a4 + 152) + 32LL) + *(_QWORD *)((char *)v76 + v59 + 8)),
           2LL * *(_QWORD *)((char *)v76 + v59 + 16),
           1) )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_183;
      v57 = 4767753;
      goto LABEL_182;
    }
LABEL_174:
    v75 += 88;
    ++v52;
    v76 = (ExportImp *)((char *)v76 + 24);
    if ( v52 >= 57 )
      goto LABEL_183;
    v51 = (__int64)v76;
  }
  if ( (bidGblFlags & 2) == 0 )
    goto LABEL_183;
  v57 = 4714505;
LABEL_182:
  bidTraceMark(0, v57);
LABEL_183:
  v6 = hWnd;
LABEL_184:
  if ( !WriteCharToExtBufferEx((struct tagOBJBASE *)a4, (struct ext_buffer **)&handle, 0, 1u, 1) )
    SetDlgItemTextW(v6, 30700, (LPCWSTR)handle + 12);
  if ( handle )
    ((void (__fastcall *)(struct IMalloc *))g_pMO->lpVtbl->Free)(g_pMO);
  v66 = GetDlgItem(v6, 30700);
  PostMessageA(v66, 0xB1u, 0, 0);
  return 1;
}

```

## disassembly

```asm
0x10051baa0  mov     [rsp-8+arg_8], rbx
0x10051baa5  push    rbp
0x10051baa6  push    rsi
0x10051baa7  push    rdi
0x10051baa8  push    r12
0x10051baaa  push    r13
0x10051baac  push    r14
0x10051baae  push    r15
0x10051bab0  lea     rbp, [rsp-0A00h]
0x10051bab8  sub     rsp, 0B00h
0x10051babf  mov     rax, cs:__security_cookie
0x10051bac6  xor     rax, rsp
0x10051bac9  mov     [rbp+0A30h+var_40], rax
0x10051bad0  mov     [rsp+0B30h+var_AD0], r8
0x10051bad5  mov     rbx, r9
0x10051bad8  mov     [rsp+0B30h+hWnd], rcx
0x10051badd  mov     r14, r8
0x10051bae0  mov     r12, rcx
0x10051bae3  sub     edx, 110h
0x10051bae9  jz      loc_10051C791
0x10051baef  cmp     edx, 1
0x10051baf2  jnz     loc_10051C7DC
0x10051baf8  mov     edx, 0FFFFFFEBh; nIndex
0x10051bafd  call    cs:__imp_GetWindowLongPtrW
0x10051bb03  xor     esi, esi
0x10051bb05  mov     rdi, rax
0x10051bb08  cmp     [rax+708h], rsi
0x10051bb0f  jz      short loc_10051BB23
0x10051bb11  mov     rcx, [rax+710h]; hWnd
0x10051bb18  call    cs:__imp_SetForegroundWindow
0x10051bb1e  jmp     loc_10051C7DC
0x10051bb23  movzx   edx, r14w
0x10051bb27  mov     ecx, edx
0x10051bb29  sub     ecx, 1
0x10051bb2c  jz      loc_10051C772
0x10051bb32  sub     ecx, 1
0x10051bb35  jz      loc_10051C772
0x10051bb3b  cmp     ecx, 77FBh
0x10051bb41  jnz     loc_10051C7DC
0x10051bb47  xor     r9d, r9d; lpName
0x10051bb4a  xor     r8d, r8d; bInitialState
0x10051bb4d  xor     ecx, ecx; lpEventAttributes
0x10051bb4f  lea     r14d, [r9+1]
0x10051bb53  mov     edx, r14d; bManualReset
0x10051bb56  call    cs:__imp_CreateEventW
0x10051bb5c  mov     r9, rdi; ArgList
0x10051bb5f  mov     [rsp+0B30h+ThrdAddr], rsi; ThrdAddr
0x10051bb64  lea     r8, ?TestDlgThread@@YAIPEAX@Z; StartAddress
0x10051bb6b  mov     [rdi+718h], rax
0x10051bb72  xor     edx, edx; StackSize
0x10051bb74  mov     [rsp+0B30h+InitFlag], esi; InitFlag
0x10051bb78  xor     ecx, ecx; Security
0x10051bb7a  call    cs:__imp__beginthreadex
0x10051bb80  mov     rcx, [rdi+718h]; hHandle
0x10051bb87  or      edx, 0FFFFFFFFh; dwMilliseconds
0x10051bb8a  mov     [rdi+708h], rax
0x10051bb91  call    cs:__imp_WaitForSingleObject
0x10051bb97  mov     rcx, [rdi+718h]; hObject
0x10051bb9e  call    cs:__imp_CloseHandle
0x10051bba4  mov     rcx, [rdi+710h]; hWnd
0x10051bbab  xor     edx, edx; bRevert
0x10051bbad  call    cs:__imp_GetSystemMenu
0x10051bbb3  mov     edx, 0F060h; uIDEnableItem
0x10051bbb8  lea     r8d, [r14+2]; uEnable
0x10051bbbc  mov     rcx, rax; hMenu
0x10051bbbf  mov     [rbp+0A30h+hMenu], rax
0x10051bbc3  call    cs:__imp_EnableMenuItem
0x10051bbc9  xor     edx, edx; Val
0x10051bbcb  lea     rcx, [rbp+0A30h+Buffer]; void *
0x10051bbcf  mov     r8d, 608h; Size
0x10051bbd5  call    memset_0
0x10051bbda  mov     edx, 77ECh; nIDDlgItem
0x10051bbdf  mov     rcx, r12; hDlg
0x10051bbe2  call    cs:__imp_GetDlgItem
0x10051bbe8  mov     rcx, cs:?g_hinstance_language@@3PEAUHINSTANCE__@@EA; HINSTANCE
0x10051bbef  lea     ebx, [r14+1]
0x10051bbf3  mov     dword ptr [rsp+0B30h+pcbStringLength], ebx; __int64 *
0x10051bbf7  lea     r8, [rbp+0A30h+Buffer]; unsigned __int16 *
0x10051bbfb  mov     r15d, 304h
0x10051bc01  mov     dword ptr [rsp+0B30h+ThrdAddr], 6
0x10051bc09  mov     r9d, r15d; unsigned int
0x10051bc0c  mov     [rsp+0B30h+InitFlag], 12h
0x10051bc14  mov     edx, 9C62h; unsigned int
0x10051bc19  mov     [rsp+0B30h+var_AB8], rax
0x10051bc1e  call    ?LoadFormattedMessage@@YAKPEAUHINSTANCE__@@KPEAGKZZ; LoadFormattedMessage(HINSTANCE__ *,ulong,ushort *,ulong,...)
0x10051bc23  mov     rcx, [rdi+710h]; HWND
0x10051bc2a  lea     rdx, [rbp+0A30h+Buffer]; unsigned __int16 *
0x10051bc2e  call    ?AppendTestDlgMsg@@YAXPEAUHWND__@@PEAG@Z; AppendTestDlgMsg(HWND__ *,ushort *)
0x10051bc33  mov     rcx, [rdi+710h]; HWND
0x10051bc3a  lea     rdx, asc_1005AB1F0; "\r\n\r\n"
0x10051bc41  call    ?AppendTestDlgMsg@@YAXPEAUHWND__@@PEAG@Z; AppendTestDlgMsg(HWND__ *,ushort *)
0x10051bc46  mov     rcx, cs:?g_hinstance_language@@3PEAUHINSTANCE__@@EA; hInstance
0x10051bc4d  lea     r8, [rbp+0A30h+Buffer]; lpBuffer
0x10051bc51  mov     r9d, r15d; cchBufferMax
0x10051bc54  mov     edx, 9C66h; uID
0x10051bc59  call    cs:__imp_LoadStringW
0x10051bc5f  mov     rcx, [rdi+710h]; HWND
0x10051bc66  lea     rdx, [rbp+0A30h+Buffer]; unsigned __int16 *
0x10051bc6a  call    ?AppendTestDlgMsg@@YAXPEAUHWND__@@PEAG@Z; AppendTestDlgMsg(HWND__ *,ushort *)
0x10051bc6f  mov     rcx, [rdi+710h]; HWND
0x10051bc76  lea     rdx, asc_1005AB1F0; "\r\n\r\n"
0x10051bc7d  call    ?AppendTestDlgMsg@@YAXPEAUHWND__@@PEAG@Z; AppendTestDlgMsg(HWND__ *,ushort *)
0x10051bc82  mov     rcx, cs:?g_hinstance_language@@3PEAUHINSTANCE__@@EA; hInstance
0x10051bc89  lea     r8, [rbp+0A30h+Buffer]; lpBuffer
0x10051bc8d  mov     r9d, r15d; cchBufferMax
0x10051bc90  mov     edx, 9C67h; uID
0x10051bc95  call    cs:__imp_LoadStringW
0x10051bc9b  mov     rcx, [rdi+710h]; HWND
0x10051bca2  lea     rdx, [rbp+0A30h+Buffer]; unsigned __int16 *
0x10051bca6  call    ?AppendTestDlgMsg@@YAXPEAUHWND__@@PEAG@Z; AppendTestDlgMsg(HWND__ *,ushort *)
0x10051bcab  mov     rcx, [rdi+710h]; HWND
0x10051bcb2  lea     rdx, asc_1005AB1E0; "\r\n"
0x10051bcb9  call    ?AppendTestDlgMsg@@YAXPEAUHWND__@@PEAG@Z; AppendTestDlgMsg(HWND__ *,ushort *)
0x10051bcbe  test    byte ptr [rdi+78h], 4
0x10051bcc2  lea     r15, [rdi+40h]
0x10051bcc6  mov     r12d, 0FFFBh
0x10051bccc  jz      short loc_10051BCDB
0x10051bcce  mov     rcx, [r15]; this
0x10051bcd1  call    ?SQLDisconnect@ExportImp@@YAFPEAUtagDBC@@@Z; ExportImp::SQLDisconnect(tagDBC *)
0x10051bcd6  and     [rdi+78h], r12w
0x10051bcdb  mov     rax, [r15]
0x10051bcde  lea     r12, [rdi+88h]
0x10051bce5  mov     [rdi+48h], rax
0x10051bce9  mov     r8d, 281h
0x10051bcef  mov     [r15], rsi
0x10051bcf2  mov     rcx, [rdi+90h]
0x10051bcf9  mov     rax, [rdi+98h]
0x10051bd00  mov     rdx, [rax+20h]
0x10051bd04  add     rdx, [rcx+38h]
0x10051bd08  lea     rcx, [rdi+102h]
0x10051bd0f  lea     rax, [r8+7FFFFD7Dh]
0x10051bd16  test    rax, rax
0x10051bd19  jz      short loc_10051BD31
0x10051bd1b  movzx   eax, word ptr [rdx]
0x10051bd1e  test    ax, ax
0x10051bd21  jz      short loc_10051BD31
0x10051bd23  mov     [rcx], ax
0x10051bd26  add     rdx, rbx; struct tagENV **
0x10051bd29  add     rcx, rbx
0x10051bd2c  sub     r8, r14
0x10051bd2f  jnz     short loc_10051BD0F
0x10051bd31  lea     rax, [rcx-2]
0x10051bd35  test    r8, r8
0x10051bd38  cmovnz  rax, rcx
0x10051bd3c  mov     ecx, 200h
0x10051bd41  mov     [rax], si
0x10051bd44  movzx   eax, word ptr [rdi+78h]
0x10051bd48  shl     ax, 4
0x10051bd4c  xor     ax, [rdi+78h]
0x10051bd50  and     ax, cx
0x10051bd53  lea     rcx, [rsp+0B30h+var_AC8]; this
0x10051bd58  xor     [rdi+78h], ax
0x10051bd5c  call    ?SQLAllocEnv@ExportImp@@YAFPEAPEAUtagENV@@@Z; ExportImp::SQLAllocEnv(tagENV * *)
0x10051bd61  mov     word ptr [rsp+0B30h+var_AF0], ax
0x10051bd66  mov     r13d, 20h ; ' '
0x10051bd6c  test    ax, ax
0x10051bd6f  jz      short loc_10051BD7F
0x10051bd71  or      r12, 0FFFFFFFFFFFFFFFFh
0x10051bd75  mov     [rsp+0B30h+var_AD0], r12
0x10051bd7a  jmp     loc_10051C5BC
0x10051bd7f  mov     rax, [rsp+0B30h+var_AC8]
0x10051bd84  mov     rdx, r15; struct tagENV *
0x10051bd87  mov     qword ptr [rax+68h], 3
0x10051bd8f  mov     rcx, [rsp+0B30h+var_AC8]; this
0x10051bd94  call    ?SQLAllocConnect@ExportImp@@YAFPEAUtagENV@@PEAPEAUtagDBC@@@Z; ExportImp::SQLAllocConnect(tagENV *,tagDBC * *)
0x10051bd99  mov     word ptr [rsp+0B30h+var_AF0], ax; __int16 *
0x10051bd9e  test    ax, ax
0x10051bda1  jz      short loc_10051BDAF
0x10051bda3  mov     rcx, [rsp+0B30h+var_AC8]; this
0x10051bda8  call    ?SQLFreeEnv@ExportImp@@YAFPEAUtagENV@@@Z; ExportImp::SQLFreeEnv(tagENV *)
0x10051bdad  jmp     short loc_10051BD71
0x10051bdaf  lea     rcx, szDSN; "SQLServerDriver##TEMPDSN"
0x10051bdb6  call    SQLRemoveDSNFromIniW
0x10051bdbb  xor     edx, edx; Val
0x10051bdbd  lea     rcx, [rbp+0A30h+szRetBuffer]; void *
0x10051bdc1  lea     r8d, [rdx+40h]; Size
0x10051bdc5  call    memset_0
0x10051bdca  mov     rcx, [rdi+90h]
0x10051bdd1  lea     r8, szFilename; "ODBC.INI"
0x10051bdd8  test    [rcx+60h], r14b
0x10051bddc  jnz     short loc_10051BDE4
0x10051bdde  test    [rcx+30h], r14b
0x10051bde2  jz      short loc_10051BE35
0x10051bde4  movzx   edx, word ptr [rcx+30h]
0x10051bde8  mov     rax, [rdi+98h]
0x10051bdef  and     dx, r14w
0x10051bdf3  jz      short loc_10051BDFB
0x10051bdf5  mov     rcx, [rcx+38h]
0x10051bdf9  jmp     short loc_10051BDFF
0x10051bdfb  mov     rcx, [rcx+68h]
0x10051bdff  add     rcx, [rax+r13]; lpszSection
0x10051be03  lea     r9, [rbp+0A30h+szRetBuffer]; lpszRetBuffer
0x10051be07  test    dx, dx
0x10051be0a  lea     rax, aOdbcinstIni; "ODBCINST.INI"
0x10051be11  lea     rdx, aAdalusewam; "ADALuseWAM"
0x10051be18  cmovnz  rax, r8
0x10051be1c  lea     r8, szDefault; lpszDefault
0x10051be23  mov     [rsp+0B30h+ThrdAddr], rax; lpszFilename
0x10051be28  mov     [rsp+0B30h+InitFlag], 40h ; '@'; cchRetBuffer
0x10051be30  call    SQLGetPrivateProfileStringW
0x10051be35  lea     r8, szDSN; "SQLServerDriver##TEMPDSN"
0x10051be3c  mov     edx, ebx; int
0x10051be3e  mov     rcx, r12; this
0x10051be41  call    ?SetATTRValue@CDlgATTRs@@QEAAJHPEBG@Z; CDlgATTRs::SetATTRValue(int,ushort const *)
0x10051be46  test    eax, eax
0x10051be48  js      loc_10051BD71
0x10051be4e  lfence
0x10051be51  mov     rax, [rdi+90h]
0x10051be58  mov     ecx, 0FFFBh
0x10051be5d  or      [rdi+78h], r13w
0x10051be62  and     [rax+108h], cx
0x10051be69  mov     rax, [rdi+90h]
0x10051be70  and     [rax+120h], cx
0x10051be77  mov     rax, [rdi+90h]
0x10051be7e  test    [rax+60h], r14b
0x10051be82  jnz     short loc_10051BEA0
0x10051be84  lea     r8, szDriver; "ODBC Driver 18 for SQL Server"
0x10051be8b  mov     edx, 4; int
0x10051be90  mov     rcx, r12; this
0x10051be93  call    ?SetATTRValue@CDlgATTRs@@QEAAJHPEBG@Z; CDlgATTRs::SetATTRValue(int,ushort const *)
0x10051be98  test    eax, eax
0x10051be9a  js      loc_10051BD71
0x10051bea0  mov     r8d, r14d; int
0x10051bea3  mov     rdx, rdi; struct tagDLGSTRUCT *
0x10051bea6  xor     ecx, ecx; hWnd
0x10051bea8  call    ?SaveDSNAttributes@@YAKPEAUHWND__@@PEAUtagDLGSTRUCT@@H@Z; SaveDSNAttributes(HWND__ *,tagDLGSTRUCT *,int)
0x10051bead  cmp     [rbp+0A30h+szRetBuffer], si
0x10051beb1  jz      short loc_10051BED1
0x10051beb3  lea     r9, szFilename; "ODBC.INI"
0x10051beba  lea     r8, [rbp+0A30h+szRetBuffer]; lpszString
0x10051bebe  lea     rdx, aAdalusewam; "ADALuseWAM"
0x10051bec5  lea     rcx, szDSN; "SQLServerDriver##TEMPDSN"
0x10051becc  call    SQLWritePrivateProfileStringW
0x10051bed1  mov     rax, [r15]
0x10051bed4  mov     ecx, 0FFFDh
0x10051bed9  and     [rax+9B8h], cx
0x10051bee0  mov     rax, [rdi+90h]
0x10051bee7  test    [rax+1C8h], r13b
0x10051beee  jz      short loc_10051BEFA
0x10051bef0  mov     rax, [r15]
0x10051bef3  or      [rax+9B8h], bx
0x10051befa  mov     rcx, [r15]; struct tagDBC *
0x10051befd  mov     rdx, r12; struct CDlgATTRs *
0x10051bf00  call    ?SyncConnAttrWithKeyVal@@YAJPEAUtagDBC@@AEAVCDlgATTRs@@@Z; SyncConnAttrWithKeyVal(tagDBC *,CDlgATTRs &)
0x10051bf05  mov     rax, [r15]
0x10051bf08  mov     qword ptr [rax+90h], 0Fh
0x10051bf13  mov     rax, [r15]
0x10051bf16  mov     dword ptr [rax+564h], 3A98h
0x10051bf20  mov     rax, [rdi+90h]
0x10051bf27  test    [rax+390h], r14b
0x10051bf2e  jz      short loc_10051BF8A
0x10051bf30  mov     rcx, r12; struct CDlgATTRs *
0x10051bf33  call    ?GetAuthenticationModeValue@@YAKAEAVCDlgATTRs@@@Z; GetAuthenticationModeValue(CDlgATTRs &)
0x10051bf38  cmp     eax, 3
0x10051bf3b  jz      short loc_10051BF57
0x10051bf3d  mov     rcx, r12; struct CDlgATTRs *
0x10051bf40  call    ?GetAuthenticationModeValue@@YAKAEAVCDlgATTRs@@@Z; GetAuthenticationModeValue(CDlgATTRs &)
0x10051bf45  cmp     eax, 4
0x10051bf48  jz      short loc_10051BF57
0x10051bf4a  mov     rcx, r12; struct CDlgATTRs *
0x10051bf4d  call    ?GetAuthenticationModeValue@@YAKAEAVCDlgATTRs@@@Z; GetAuthenticationModeValue(CDlgATTRs &)
0x10051bf52  cmp     eax, 7
0x10051bf55  jnz     short loc_10051BF8A
0x10051bf57  mov     rcx, [rdi+90h]
0x10051bf5e  movzx   eax, word ptr [rcx+90h]
0x10051bf65  test    r14b, al
0x10051bf68  jz      short loc_10051BF8A
0x10051bf6a  mov     edx, 0FFF7h
0x10051bf6f  and     ax, dx
0x10051bf72  mov     [rcx+90h], ax
0x10051bf79  mov     rax, [rdi+90h]
0x10051bf80  lea     ecx, [rdx+4]
0x10051bf83  and     [rax+90h], cx
0x10051bf8a  mov     rcx, [rsp+0B30h+hWnd]; hWnd
0x10051bf8f  mov     r8d, 7; unsigned int
0x10051bf95  mov     rdx, rdi; struct tagDLGSTRUCT *
0x10051bf98  call    ?DoDlgConnection@@YAFPEAUHWND__@@PEAUtagDLGSTRUCT@@K@Z; DoDlgConnection(HWND__ *,tagDLGSTRUCT *,ulong)
0x10051bf9d  or      r12, 0FFFFFFFFFFFFFFFFh
0x10051bfa1  cmp     ax, r12w
0x10051bfa5  jnz     loc_10051C067
0x10051bfab  mov     rdx, [r15]; __int16
0x10051bfae  lea     rax, [rsp+0B30h+var_AD8]
0x10051bfb3  mov     qword ptr [rsp+0B30h+var_AF8], rax; __int16
0x10051bfb8  lea     r9, [rbp+0A30h+var_AA8]; __int16
0x10051bfbc  mov     eax, 304h
0x10051bfc1  mov     r8d, r14d; void *
0x10051bfc4  mov     word ptr [rsp+0B30h+pcbStringLength], ax; unsigned __int16 *
0x10051bfc9  mov     ecx, ebx; this
0x10051bfcb  lea     rax, [rbp+0A30h+Buffer]
0x10051bfcf  mov     [rsp+0B30h+ThrdAddr], rax; int *
0x10051bfd4  mov     qword ptr [rsp+0B30h+InitFlag], rsi; unsigned __int16 *
0x10051bfd9  call    ?SQLGetDiagRecW@ExportImp@@YAFFPEAXFPEAGPEAJ1FPEAF@Z; ExportImp::SQLGetDiagRecW(short,void *,short,ushort *,long *,ushort *,short,short *)
0x10051bfde  test    ax, ax
0x10051bfe1  jnz     short loc_10051C060
0x10051bfe3  movzx   r13d, r14w
0x10051bfe7  mov     r12d, 304h
0x10051bfed  cmp     [rbp+0A30h+var_AA8], 30h ; '0'
0x10051bff2  jnz     short loc_10051BFFB
0x10051bff4  cmp     [rbp+0A30h+var_AA6], 31h ; '1'
0x10051bff9  jz      short loc_10051C01E
  ... truncated ...
```
