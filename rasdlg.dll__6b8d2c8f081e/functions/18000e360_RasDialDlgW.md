# RasDialDlgW

- ea: `0x18000e360`
- end: `0x18000edd0`
- name: `RasDialDlgW`
- size: `2672`
- prototype: `BOOL __stdcall(LPWSTR lpszPhonebook, LPWSTR lpszEntry, LPWSTR lpszPhoneNumber, struct tagRASDIALDLG *lpInfo)`
- caller_count: `2`
- callee_count: `24`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000e220`
- `0x1800247ac`

## callees

- `0x1800076d8`
- `0x180007730`
- `0x180007820`
- `0x180007b1c`
- `0x1800080d4`
- `0x18000d674`
- `0x18000e360`
- `0x180010500`
- `0x180026618`
- `0x18002b418`
- `0x18002b960`
- `0x18002b9f4`
- `0x18002be80`
- `0x18002bfc8`
- `0x18003aa3c`
- `0x18003b6b8`
- `0x18003bda0`
- `0x18003c170`
- `0x18003e9ec`
- `0x180041c9c`
- `0x180048778`
- `0x1800490c4`
- `0x18004d0d2`
- `0x18004e010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18000e486`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18000e486`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18000edc2`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18000edc2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e41b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e41b`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000edb9`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000edb9`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18000e506`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18000e506`
- `RASAPI32!GetPbkAndEntryName` at `0x18000e740`
- `RASAPI32!GetPbkAndEntryName` at `0x18000e740`
- `RASAPI32!ReadPhonebookFile` at `0x18000e64d`
- `RASAPI32!ReadPhonebookFile` at `0x18000e685`
- `RASAPI32!ReadPhonebookFile` at `0x18000e64d`
- `RASAPI32!ReadPhonebookFile` at `0x18000e685`
- `RASAPI32!GetOverridableParam` at `0x18000e982`
- `RASAPI32!GetOverridableParam` at `0x18000e996`
- `RASAPI32!GetOverridableParam` at `0x18000e982`
- `RASAPI32!GetOverridableParam` at `0x18000e996`
- `RASAPI32!ClosePhonebookFile` at `0x18000e725`
- `RASAPI32!ClosePhonebookFile` at `0x18000ed15`
- `RASAPI32!ClosePhonebookFile` at `0x18000ed3a`
- `RASAPI32!ClosePhonebookFile` at `0x18000e725`
- `RASAPI32!ClosePhonebookFile` at `0x18000ed15`
- `RASAPI32!ClosePhonebookFile` at `0x18000ed3a`
- `rtutils!TracePrintfExA` at `0x18000e3ca`
- `rtutils!TracePrintfExA` at `0x18000e40e`
- `rtutils!TracePrintfExA` at `0x18000e53b`
- `rtutils!TracePrintfExA` at `0x18000ea0d`
- `rtutils!TracePrintfExA` at `0x18000ec60`
- `rtutils!TracePrintfExA` at `0x18000eca8`
- `rtutils!TracePrintfExA` at `0x18000ecdd`
- `rtutils!TracePrintfExA` at `0x18000ed05`
- `rtutils!TracePrintfExA` at `0x18000e3ca`
- `rtutils!TracePrintfExA` at `0x18000e40e`
- `rtutils!TracePrintfExA` at `0x18000e53b`
- `rtutils!TracePrintfExA` at `0x18000ea0d`
- `rtutils!TracePrintfExA` at `0x18000ec60`
- `rtutils!TracePrintfExA` at `0x18000eca8`
- `rtutils!TracePrintfExA` at `0x18000ecdd`
- `rtutils!TracePrintfExA` at `0x18000ed05`

## string_xrefs

- `0x18000ecd1`: `RasDialDlgW: RasCompleteDialMachineCleanup start.`
- `0x18000ecf9`: `RasDialDlgW: RasCompleteDialMachineCleanup completed.`

## pseudocode

```c
BOOL __stdcall RasDialDlgW(
        LPWSTR lpszPhonebook,
        LPWSTR lpszEntry,
        LPWSTR lpszPhoneNumber,
        struct tagRASDIALDLG *lpInfo)
{
  struct tagRASDIALDLG *v4; // rbx
  const WCHAR *v7; // r12
  DWORD v8; // edi
  DWORD Ras; // eax
  __int64 v11; // r9
  __int64 v12; // r8
  HWND v13; // rax
  HWND v14; // r13
  __int64 v15; // r15
  int v16; // esi
  int v17; // r14d
  HRESULT v18; // eax
  DWORD v19; // edi
  ULONG_PTR reserved; // rcx
  __int64 v21; // rax
  HWND v22; // r15
  DWORD v23; // eax
  __int64 v24; // r9
  __int64 v25; // r8
  HWND v26; // r12
  DWORD PhonebookFile; // eax
  HWND hwndOwner; // rcx
  int v29; // r15d
  DWORD EntryAndSetDialParams; // eax
  HWND v31; // rdi
  int PbkAndEntryName; // eax
  ULONG_PTR v33; // rax
  __int64 v34; // r10
  _WORD *v35; // r8
  int v36; // edx
  const WCHAR **v37; // rcx
  DWORD v38; // eax
  int v39; // eax
  int v40; // ecx
  __int64 v41; // rdi
  __int64 v42; // rsi
  __int64 v43; // r15
  HWND v44; // r12
  __int64 v45; // r14
  int OverridableParam; // ebx
  int v47; // eax
  DWORD v48; // eax
  DWORD v49; // eax
  __int64 v50; // rax
  DWORD v51; // eax
  HWND v52; // rcx
  __int64 v53; // rax
  _WORD *v54; // rcx
  __int64 v55; // rcx
  __int64 v56; // rcx
  __int64 v57; // rcx
  _BYTE *v58; // rax
  __int64 *v59; // rcx
  __int64 v60; // [rsp+38h] [rbp-89h]
  __int64 v61; // [rsp+40h] [rbp-81h]
  int v62; // [rsp+68h] [rbp-59h] BYREF
  __int64 v63; // [rsp+70h] [rbp-51h]
  DWORD v64; // [rsp+78h] [rbp-49h]
  BYTE *pData; // [rsp+80h] [rbp-41h] BYREF
  BYTE *v66; // [rsp+88h] [rbp-39h] BYREF
  int v67; // [rsp+90h] [rbp-31h]
  int v68; // [rsp+94h] [rbp-2Dh]
  int v69; // [rsp+98h] [rbp-29h]
  __int64 v70; // [rsp+A0h] [rbp-21h] BYREF
  int v71; // [rsp+A8h] [rbp-19h] BYREF
  HWND v72; // [rsp+ACh] [rbp-15h]
  int v73; // [rsp+B4h] [rbp-Dh]
  LONG xDlg; // [rsp+B8h] [rbp-9h]
  LONG yDlg; // [rsp+BCh] [rbp-5h]
  __int128 v76; // [rsp+C0h] [rbp-1h]
  __int64 v77; // [rsp+D0h] [rbp+Fh]

  v4 = lpInfo;
  v66 = 0;
  pData = 0;
  v7 = lpszPhonebook;
  RasDlgInit();
  if ( g_dwTraceId != -1 )
    TracePrintfExA(g_dwTraceId, 0xCu, "RasDialDlgW");
  v8 = CheckPhonebookAndEntryWParams((__int64)v7, (__int64)lpszEntry, 0);
  if ( v8 )
    goto LABEL_8;
  if ( (unsigned int)IsBadInputStringW(lpszPhoneNumber, 261, 1) )
  {
    if ( g_dwTraceId != -1 )
      TracePrintfExA(g_dwTraceId, 0xCu, "Invalid phone number or IP address.");
    v8 = 87;
    goto LABEL_8;
  }
  v8 = CheckRASDIALDLGParams(v4);
  if ( v8 )
  {
LABEL_8:
    SetLastError(v8);
    v4->dwError = v8;
    return 0;
  }
  Ras = LoadRas();
  v4->dwError = Ras;
  if ( Ras )
  {
    v11 = 5;
    if ( Ras == 5 )
    {
      v12 = 1685;
    }
    else
    {
      v11 = Ras;
      v12 = 29900;
    }
    DialDlgDisplayError(v4, v4->hwndOwner, v12, v11);
    return 0;
  }
  v13 = (HWND)GlobalAlloc(0x40u, 0x1B00u);
  v14 = v13;
  if ( !v13 )
  {
    DialDlgDisplayError(v4, v4->hwndOwner, 318, 8);
    v4->dwError = 8;
    return 0;
  }
  v15 = 0;
  v68 = 0;
  v63 = 0;
  v67 = 0;
  v69 = 0;
  v16 = 0;
  memset_0(v13 + 8, 0, 0x1AE0u);
  *((_QWORD *)v14 + 2) = lpszPhoneNumber;
  *(_QWORD *)v14 = v7;
  *((_QWORD *)v14 + 1) = lpszEntry;
  *((_QWORD *)v14 + 3) = v4;
  *((_DWORD *)v14 + 90) = FIsUserAdminOrNCO();
  v62 = 0;
  v17 = 0;
  v18 = CoInitializeEx(0, 2u);
  LOWORD(v19) = v18;
  if ( v18 != -2147417850 )
  {
    if ( v18 < 0 )
    {
      if ( g_dwTraceId != -1 )
        TracePrintfExA(g_dwTraceId, 0xCu, "CoInitializeEx failed with error %x", v18);
      v19 = (unsigned __int16)v19;
      goto LABEL_126;
    }
    v69 = 1;
  }
  reserved = v4->reserved;
  if ( reserved )
  {
    v21 = *(_QWORD *)(reserved + 8);
    *((_QWORD *)v14 + 5) = v21;
    *((_QWORD *)v14 + 4) = v21;
    *((_QWORD *)v14 + 21) = *(_QWORD *)(reserved + 16);
    *((_QWORD *)v14 + 47) = *(_QWORD *)(reserved + 32);
    *((_QWORD *)v14 + 48) = reserved + 40;
    if ( (*(_BYTE *)(reserved + 24) & 0x40) != 0 )
      *((_DWORD *)v14 + 98) = 1;
    if ( (*(_BYTE *)(reserved + 24) & 2) != 0 )
      *((_DWORD *)v14 + 103) = 1;
    if ( (*(_BYTE *)(reserved + 24) & 1) != 0 )
      *((_DWORD *)v14 + 102) = 1;
    if ( (*(_BYTE *)(reserved + 24) & 8) != 0 )
      *((_DWORD *)v14 + 114) = 1;
    if ( (*(_BYTE *)(reserved + 24) & 0x20) != 0 )
      *((_DWORD *)v14 + 100) = 1;
    if ( (*(_BYTE *)(reserved + 24) & 0x10) != 0 )
      *((_DWORD *)v14 + 101) = 1;
  }
  v22 = (HWND)*((_QWORD *)v14 + 21);
  if ( !v22 )
  {
    v22 = v14 + 44;
    v23 = ((__int64 (__fastcall *)(_QWORD, HWND, _QWORD))g_pGetUserPreferences)(0, v14 + 44, 0);
    v19 = v23;
    if ( v23 )
    {
      v24 = v23;
      v25 = 323;
LABEL_40:
      DialDlgDisplayError(v4, v4->hwndOwner, v25, v24);
      v15 = 0;
      goto LABEL_126;
    }
    *((_QWORD *)v14 + 21) = v22;
    v68 = 1;
  }
  if ( !*((_QWORD *)v14 + 4) )
  {
    v26 = v14 + 12;
    PhonebookFile = ReadPhonebookFile(lpszPhonebook, v22, 0, 0);
    v19 = PhonebookFile;
    if ( PhonebookFile )
    {
      if ( lpszPhonebook
        || PhonebookFile != 621
        || (unsigned int)IsLowProcess()
        || (v19 = ReadPhonebookFile(0, *((_QWORD *)v14 + 21), 0, 128)) != 0 )
      {
        v24 = v19;
        v25 = 321;
        goto LABEL_40;
      }
    }
    *((_QWORD *)v14 + 5) = v26;
    *((_QWORD *)v14 + 4) = v26;
    v7 = lpszPhonebook;
    v67 = 1;
  }
  if ( !*((_DWORD *)v14 + 114) )
    *((_DWORD *)v14 + 114) = IsPasswordSavingDisabled();
  hwndOwner = v4->hwndOwner;
  if ( hwndOwner && *((_DWORD *)v14 + 100) )
    SetOffDesktop(hwndOwner);
  *((_DWORD *)v14 + 117) = 1;
  v29 = 1;
  while ( 1 )
  {
    while ( 1 )
    {
      *((_DWORD *)v14 + 118) = 0;
      EntryAndSetDialParams = FindEntryAndSetDialParams(v14);
      v64 = EntryAndSetDialParams;
      v19 = EntryAndSetDialParams;
      if ( EntryAndSetDialParams )
      {
        if ( EntryAndSetDialParams != 623 || v7 )
          goto LABEL_118;
        v31 = v14 + 12;
        v70 = 0;
        ClosePhonebookFile(v14 + 12);
        PbkAndEntryName = GetPbkAndEntryName(0, lpszEntry, 0, v14 + 12, &v70);
        if ( !v70 || PbkAndEntryName )
        {
          v19 = 623;
LABEL_118:
          v16 = 0;
          goto LABEL_125;
        }
        *((_QWORD *)v14 + 5) = v31;
        *((_QWORD *)v14 + 4) = v31;
        v64 = FindEntryAndSetDialParams(v14);
        v19 = v64;
        if ( v64 )
          goto LABEL_118;
      }
      v33 = v4->reserved;
      if ( v33 )
      {
        if ( *((_DWORD *)v14 + 117) )
          *((_QWORD *)v14 + 48) = 0;
        else
          *((_QWORD *)v14 + 48) = v33 + 40;
      }
      v34 = *((_QWORD *)v14 + 55);
      v35 = *(_WORD **)(v34 + 448);
      if ( !v35 || !*v35 )
        break;
      v16 = 1;
      v36 = (*(_DWORD *)(v34 + 164) >> 6) & 2;
      if ( *((_QWORD *)v14 + 47) && *((_DWORD *)v14 + 98) )
        v36 |= 4u;
      v61 = *(_QWORD *)(v34 + 448);
      v60 = v4->reserved;
      if ( !*((_DWORD *)v14 + 117) )
      {
        v51 = DwCustomDialDlg(v7, lpszEntry, (__int64)lpszPhoneNumber, (__int64)v4, v36, &v62, v60, v61);
        v17 = v62;
        v19 = v51;
        goto LABEL_125;
      }
      v37 = (const WCHAR **)*((_QWORD *)v14 + 4);
      v73 = 0;
      v77 = 0;
      v72 = v4->hwndOwner;
      xDlg = v4->xDlg;
      yDlg = v4->yDlg;
      v76 = 0;
      v71 = 48;
      v38 = DwCustomDialDlg(*v37, *(const WCHAR **)(v34 + 8), 0, (__int64)&v71, v36, &v62, v60, v61);
      v17 = v62;
      v19 = v38;
      if ( !v62 )
      {
        v4->dwError = DWORD1(v76);
        goto LABEL_125;
      }
      *((_DWORD *)v14 + 117) = 0;
    }
    if ( *((_DWORD *)v14 + 117) && HrasconnFromEntry(**((PCNZWCH **)v14 + 4), *(PCNZWCH *)(v34 + 8)) )
      *((_DWORD *)v14 + 118) = 1;
    *((_OWORD *)v14 + 428) = 0;
    v39 = 1026;
    *((_OWORD *)v14 + 429) = 0;
    *((_OWORD *)v14 + 430) = 0;
    *(_OWORD *)(v14 + 1723) = 0;
    *((_DWORD *)v14 + 1712) = 60;
    *((_DWORD *)v14 + 1713) = 1026;
    if ( *((_QWORD *)v14 + 47) && *((_DWORD *)v14 + 98) )
    {
      v39 = 1538;
      *((_DWORD *)v14 + 1713) = 1538;
    }
    if ( !*((_QWORD *)v14 + 2) )
      *((_DWORD *)v14 + 1713) = v39 | 1;
    v40 = *((_DWORD *)v14 + 99);
    if ( !v40
      || !*((_DWORD *)v14 + 115) && !*((_DWORD *)v14 + 116) && (*(_DWORD *)(*((_QWORD *)v14 + 55) + 164LL) & 0x880) == 0 )
    {
      break;
    }
    if ( (v4->dwFlags & 4) != 0 )
    {
      v17 = 1;
      *((_DWORD *)v14 + 121) = 1;
      v62 = 1;
    }
    else
    {
      v41 = *((_QWORD *)v14 + 55);
      v42 = *((_QWORD *)v14 + 21);
      v43 = *(_QWORD *)v14;
      v44 = v4->hwndOwner;
      v45 = *(_QWORD *)(v41 + 8);
      OverridableParam = GetOverridableParam(v42, v41, 16);
      v47 = GetOverridableParam(v42, v41, 2);
      v62 = DialErrorDlg(v44, (__int64)v14, v43, v45, 0, 0, 0, 0, 0, v47, OverridableParam);
      v17 = v62;
      if ( !v62 )
      {
        v19 = v64;
        v16 = 0;
        goto LABEL_125;
      }
      v4 = lpInfo;
    }
    if ( *(char *)(*((_QWORD *)v14 + 55) + 164LL) >= 0 )
    {
      v19 = v64;
    }
    else
    {
      if ( g_dwTraceId != -1 )
        TracePrintfExA(g_dwTraceId, 0xCu, "Not showing the EAP UI. Delaying it until LCP is done.");
      v48 = DoEapProcessing((_DWORD)v4, (_DWORD)v14, (unsigned int)&pData, (unsigned int)&v66, (__int64)&v62);
      v17 = v62;
      v19 = v48;
      if ( v48 || !v62 )
        goto LABEL_118;
    }
LABEL_109:
    if ( !v17 )
    {
      v15 = v63;
      goto LABEL_112;
    }
LABEL_110:
    v15 = 0;
    v17 = DialProgressDlg(v14);
    v62 = v17;
LABEL_112:
    v16 = 0;
    if ( !v17 || !*((_DWORD *)v14 + 117) )
      goto LABEL_126;
    v50 = HrasconnFromEntry(**((PCNZWCH **)v14 + 4), *(PCNZWCH *)(*((_QWORD *)v14 + 55) + 8LL));
    *((_DWORD *)v14 + 117) = 0;
    v29 = 0;
    v63 = v50;
    if ( pData )
    {
      RasFreeEapMemory(pData);
      pData = 0;
    }
    v7 = lpszPhonebook;
    if ( v66 )
    {
      RasFreeEapMemory(v66);
      v66 = 0;
    }
  }
  if ( *((_DWORD *)v14 + 118) )
  {
    v17 = 1;
    v62 = 1;
    goto LABEL_109;
  }
  if ( !v40 && v29 && !(unsigned int)VpnDoubleDialDlg(v4->hwndOwner, v14) )
    goto LABEL_118;
  if ( *((_DWORD *)v14 + 102) && !*((_DWORD *)v14 + 117) || (unsigned int)DialerDlg(v4->hwndOwner) )
  {
    if ( *(char *)(*((_QWORD *)v14 + 55) + 164LL) < 0 )
    {
      v49 = DoEapProcessing((_DWORD)v4, (_DWORD)v14, (unsigned int)&pData, (unsigned int)&v66, (__int64)&v62);
      v17 = v62;
      v19 = v49;
      v16 = 0;
      if ( v49 || !v62 )
        goto LABEL_125;
    }
    goto LABEL_110;
  }
  v16 = 0;
  if ( !v29 )
    v17 = 0;
LABEL_125:
  v15 = v63;
LABEL_126:
  v52 = lpInfo->hwndOwner;
  if ( v52 && *((_DWORD *)v14 + 100) )
    SetOffDesktop(v52);
  if ( v16 )
  {
LABEL_142:
    if ( !v17 )
      goto LABEL_147;
    goto LABEL_143;
  }
  ((void (__fastcall *)(_QWORD, _QWORD, bool))g_pSetUserPreferences[0])(
    0,
    *((_QWORD *)v14 + 21),
    *((_DWORD *)v14 + 98) != 0);
  if ( v19 )
  {
    DialDlgDisplayError(lpInfo, lpInfo->hwndOwner, 318, v19);
    lpInfo->dwError = v19;
  }
  if ( g_dwTraceId != -1 )
    TracePrintfExA(g_dwTraceId, 0xCu, "hrasconnPrereq=0x%x", v15);
  if ( v17 )
  {
LABEL_143:
    v55 = g_dwTraceId;
    if ( g_dwTraceId != -1 )
      TracePrintfExA(g_dwTraceId, 0xCu, "RasDialDlgW: RasCompleteDialMachineCleanup start.");
    ((void (__fastcall *)(__int64))g_pRasCompleteDialMachineCleanup)(v55);
    if ( g_dwTraceId != -1 )
      TracePrintfExA(g_dwTraceId, 0xCu, "RasDialDlgW: RasCompleteDialMachineCleanup completed.");
    goto LABEL_147;
  }
  if ( v15 )
  {
    v53 = *((_QWORD *)v14 + 55);
    if ( v53 )
    {
      v54 = *(_WORD **)(v53 + 56);
      if ( v54 )
      {
        if ( *v54 )
        {
          if ( g_dwTraceId != -1 )
            TracePrintfExA(g_dwTraceId, 0xCu, "RasDialDlgW:Call g_pRasHangUp");
          ((void (__fastcall *)(__int64))g_pRasHangUp)(v15);
          goto LABEL_142;
        }
      }
    }
  }
LABEL_147:
  if ( v67 )
    ClosePhonebookFile(*((_QWORD *)v14 + 5));
  if ( v68 )
    DestroyUserPreferences(*((void **)v14 + 21));
  if ( *((_DWORD *)v14 + 40) )
    ClosePhonebookFile(v14 + 26);
  v56 = *((_QWORD *)v14 + 46);
  if ( v56 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v56 + 16LL))(v56);
    *((_QWORD *)v14 + 46) = 0;
  }
  v57 = 514;
  v58 = v14 + 509;
  do
  {
    *v58++ = 0;
    --v57;
  }
  while ( v57 );
  v59 = (__int64 *)*((_QWORD *)v14 + 53);
  if ( v59 )
    DtlDestroyList(v59, (void (__fastcall *)(__int64))DestroyPszNode);
  if ( pData )
  {
    RasFreeEapMemory(pData);
    pData = 0;
  }
  if ( v66 )
  {
    RasFreeEapMemory(v66);
    v66 = 0;
  }
  if ( v69 )
    CoUninitialize();
  GlobalFree(v14);
  return v17;
}

```

## disassembly

```asm
0x18000e360  mov     rax, rsp
0x18000e363  mov     [rax+20h], r9
0x18000e367  mov     [rax+18h], r8
0x18000e36b  mov     [rax+10h], rdx
0x18000e36f  mov     [rax+8], rcx
0x18000e373  push    rbp
0x18000e374  push    rbx
0x18000e375  push    rsi
0x18000e376  push    rdi
0x18000e377  push    r12
0x18000e379  push    r13
0x18000e37b  push    r14
0x18000e37d  push    r15
0x18000e37f  lea     rbp, [rax-5Fh]
0x18000e383  sub     rsp, 0D8h
0x18000e38a  mov     rbx, r9
0x18000e38d  mov     [rbp+57h+var_90], 0
0x18000e395  mov     rsi, r8
0x18000e398  mov     [rbp+57h+pData], 0
0x18000e3a0  mov     r14, rdx
0x18000e3a3  mov     r12, rcx
0x18000e3a6  call    RasDlgInit
0x18000e3ab  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18000e3b1  or      r15d, 0FFFFFFFFh
0x18000e3b5  mov     r13d, 0Ch
0x18000e3bb  cmp     ecx, r15d
0x18000e3be  jz      short loc_18000E3D0
0x18000e3c0  lea     r8, aRasdialdlgw_0; "RasDialDlgW"
0x18000e3c7  mov     edx, r13d; dwFlags
0x18000e3ca  call    cs:__imp_TracePrintfExA
0x18000e3d0  xor     r8d, r8d
0x18000e3d3  mov     rdx, r14
0x18000e3d6  mov     rcx, r12
0x18000e3d9  call    CheckPhonebookAndEntryWParams
0x18000e3de  mov     edi, eax
0x18000e3e0  test    eax, eax
0x18000e3e2  jnz     short loc_18000E419
0x18000e3e4  mov     edx, 105h
0x18000e3e9  lea     r8d, [rax+1]
0x18000e3ed  mov     rcx, rsi
0x18000e3f0  call    IsBadInputStringW
0x18000e3f5  test    eax, eax
0x18000e3f7  jz      short loc_18000E43A
0x18000e3f9  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18000e3ff  cmp     ecx, r15d
0x18000e402  jz      short loc_18000E414
0x18000e404  lea     r8, aInvalidPhoneNu; "Invalid phone number or IP address."
0x18000e40b  mov     edx, r13d; dwFlags
0x18000e40e  call    cs:__imp_TracePrintfExA
0x18000e414  mov     edi, 57h ; 'W'
0x18000e419  mov     ecx, edi; dwErrCode
0x18000e41b  call    cs:__imp_SetLastError
0x18000e421  mov     [rbx+1Ch], edi
0x18000e424  xor     eax, eax
0x18000e426  add     rsp, 0D8h
0x18000e42d  pop     r15
0x18000e42f  pop     r14
0x18000e431  pop     r13
0x18000e433  pop     r12
0x18000e435  pop     rdi
0x18000e436  pop     rsi
0x18000e437  pop     rbx
0x18000e438  pop     rbp
0x18000e439  retn
0x18000e43a  mov     rcx, rbx
0x18000e43d  call    CheckRASDIALDLGParams
0x18000e442  mov     edi, eax
0x18000e444  test    eax, eax
0x18000e446  jnz     short loc_18000E419
0x18000e448  call    LoadRas
0x18000e44d  mov     [rbx+1Ch], eax
0x18000e450  test    eax, eax
0x18000e452  jz      short loc_18000E47C
0x18000e454  mov     rdx, [rbx+4]
0x18000e458  lea     r9d, [rdi+5]
0x18000e45c  mov     rcx, rbx
0x18000e45f  cmp     eax, r9d
0x18000e462  jnz     short loc_18000E46C
0x18000e464  mov     r8d, 695h
0x18000e46a  jmp     short loc_18000E475
0x18000e46c  mov     r9d, eax
0x18000e46f  mov     r8d, 74CCh
0x18000e475  call    DialDlgDisplayError
0x18000e47a  jmp     short loc_18000E424
0x18000e47c  mov     edx, 1B00h; dwBytes
0x18000e481  mov     ecx, 40h ; '@'; uFlags
0x18000e486  call    cs:__imp_GlobalAlloc
0x18000e48c  mov     r13, rax
0x18000e48f  test    rax, rax
0x18000e492  jnz     short loc_18000E4B6
0x18000e494  mov     rdx, [rbx+4]
0x18000e498  lea     r9d, [rax+8]
0x18000e49c  mov     r8d, 13Eh
0x18000e4a2  mov     rcx, rbx
0x18000e4a5  call    DialDlgDisplayError
0x18000e4aa  mov     dword ptr [rbx+1Ch], 8
0x18000e4b1  jmp     loc_18000E424
0x18000e4b6  xor     edi, edi
0x18000e4b8  lea     rcx, [rax+20h]; void *
0x18000e4bc  xor     r15d, r15d
0x18000e4bf  mov     [rbp+57h+var_84], edi
0x18000e4c2  xor     edx, edx; Val
0x18000e4c4  mov     [rbp+57h+var_A8], r15
0x18000e4c8  mov     r8d, 1AE0h; Size
0x18000e4ce  mov     [rbp+57h+var_88], edi
0x18000e4d1  mov     [rbp+57h+var_80], edi
0x18000e4d4  xor     esi, esi
0x18000e4d6  call    memset_0
0x18000e4db  mov     rax, [rbp+57h+arg_10]
0x18000e4df  mov     [r13+10h], rax
0x18000e4e3  mov     [r13+0], r12
0x18000e4e7  mov     [r13+8], r14
0x18000e4eb  mov     [r13+18h], rbx
0x18000e4ef  call    FIsUserAdminOrNCO
0x18000e4f4  lea     edx, [rsi+2]; dwCoInit
0x18000e4f7  mov     [r13+168h], eax
0x18000e4fe  xor     ecx, ecx; pvReserved
0x18000e500  mov     [rbp+57h+var_B0], edi
0x18000e503  mov     r14d, edi
0x18000e506  call    cs:__imp_CoInitializeEx
0x18000e50c  mov     edi, eax
0x18000e50e  cmp     eax, 80010106h
0x18000e513  jz      short loc_18000E549
0x18000e515  test    eax, eax
0x18000e517  js      short loc_18000E521
0x18000e519  lea     edi, [rsi+1]
0x18000e51c  mov     [rbp+57h+var_80], edi
0x18000e51f  jmp     short loc_18000E54E
0x18000e521  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18000e527  cmp     ecx, 0FFFFFFFFh
0x18000e52a  jz      short loc_18000E541
0x18000e52c  mov     r9d, edi
0x18000e52f  lea     r8, aCoinitializeex_0; "CoInitializeEx failed with error %x"
0x18000e536  mov     edx, 0Ch; dwFlags
0x18000e53b  call    cs:__imp_TracePrintfExA
0x18000e541  movzx   edi, di
0x18000e544  jmp     loc_18000E617
0x18000e549  mov     edi, 1
0x18000e54e  mov     rcx, [rbx+20h]
0x18000e552  test    rcx, rcx
0x18000e555  jz      short loc_18000E5D2
0x18000e557  mov     rax, [rcx+8]
0x18000e55b  mov     [r13+28h], rax
0x18000e55f  mov     [r13+20h], rax
0x18000e563  mov     rax, [rcx+10h]
0x18000e567  mov     [r13+0A8h], rax
0x18000e56e  mov     rax, [rcx+20h]
0x18000e572  mov     [r13+178h], rax
0x18000e579  lea     rax, [rcx+28h]
0x18000e57d  mov     [r13+180h], rax
0x18000e584  test    byte ptr [rcx+18h], 40h
0x18000e588  jz      short loc_18000E591
0x18000e58a  mov     [r13+188h], edi
0x18000e591  test    byte ptr [rcx+18h], 2
0x18000e595  jz      short loc_18000E59E
0x18000e597  mov     [r13+19Ch], edi
0x18000e59e  test    [rcx+18h], dil
0x18000e5a2  jz      short loc_18000E5AB
0x18000e5a4  mov     [r13+198h], edi
0x18000e5ab  test    byte ptr [rcx+18h], 8
0x18000e5af  jz      short loc_18000E5B8
0x18000e5b1  mov     [r13+1C8h], edi
0x18000e5b8  test    byte ptr [rcx+18h], 20h
0x18000e5bc  jz      short loc_18000E5C5
0x18000e5be  mov     [r13+190h], edi
0x18000e5c5  test    byte ptr [rcx+18h], 10h
0x18000e5c9  jz      short loc_18000E5D2
0x18000e5cb  mov     [r13+194h], edi
0x18000e5d2  mov     r15, [r13+0A8h]
0x18000e5d9  test    r15, r15
0x18000e5dc  jnz     short loc_18000E62E
0x18000e5de  mov     rax, cs:g_pGetUserPreferences
0x18000e5e5  lea     r15, [r13+0B0h]
0x18000e5ec  mov     rdx, r15
0x18000e5ef  xor     r8d, r8d
0x18000e5f2  xor     ecx, ecx
0x18000e5f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e5f9  mov     edi, eax
0x18000e5fb  test    eax, eax
0x18000e5fd  jz      short loc_18000E61F
0x18000e5ff  mov     r9d, eax
0x18000e602  mov     r8d, 143h
0x18000e608  mov     rdx, [rbx+4]
0x18000e60c  mov     rcx, rbx
0x18000e60f  call    DialDlgDisplayError
0x18000e614  mov     r15, rsi
0x18000e617  xor     r12d, r12d
0x18000e61a  jmp     loc_18000EBDB
0x18000e61f  mov     edi, 1
0x18000e624  mov     [r13+0A8h], r15
0x18000e62b  mov     [rbp+57h+var_84], edi
0x18000e62e  cmp     [r13+20h], rsi
0x18000e632  jnz     short loc_18000E6B3
0x18000e634  mov     rdx, r15
0x18000e637  lea     r12, [r13+30h]
0x18000e63b  mov     r15, [rbp+57h+arg_0]
0x18000e63f  xor     r9d, r9d
0x18000e642  mov     rcx, r15
0x18000e645  mov     qword ptr [rsp+110h+var_F0], r12
0x18000e64a  xor     r8d, r8d
0x18000e64d  call    cs:__imp_ReadPhonebookFile
0x18000e653  mov     edi, eax
0x18000e655  test    eax, eax
0x18000e657  jz      short loc_18000E69F
0x18000e659  test    r15, r15
0x18000e65c  jnz     short loc_18000E691
0x18000e65e  cmp     eax, 26Dh
0x18000e663  jnz     short loc_18000E691
0x18000e665  call    IsLowProcess
0x18000e66a  test    eax, eax
0x18000e66c  jnz     short loc_18000E691
0x18000e66e  mov     rdx, [r13+0A8h]
0x18000e675  mov     r9d, 80h
0x18000e67b  xor     r8d, r8d
0x18000e67e  mov     qword ptr [rsp+110h+var_F0], r12
0x18000e683  xor     ecx, ecx
0x18000e685  call    cs:__imp_ReadPhonebookFile
0x18000e68b  mov     edi, eax
0x18000e68d  test    eax, eax
0x18000e68f  jz      short loc_18000E69F
0x18000e691  mov     r9d, edi
0x18000e694  mov     r8d, 141h
0x18000e69a  jmp     loc_18000E608
0x18000e69f  mov     edi, 1
0x18000e6a4  mov     [r13+28h], r12
0x18000e6a8  mov     [r13+20h], r12
0x18000e6ac  mov     r12, [rbp+57h+arg_0]
0x18000e6b0  mov     [rbp+57h+var_88], edi
0x18000e6b3  cmp     [r13+1C8h], esi
0x18000e6ba  jnz     short loc_18000E6C8
0x18000e6bc  call    IsPasswordSavingDisabled
0x18000e6c1  mov     [r13+1C8h], eax
0x18000e6c8  mov     rcx, [rbx+4]; hWnd
0x18000e6cc  test    rcx, rcx
0x18000e6cf  jz      short loc_18000E6E4
0x18000e6d1  cmp     [r13+190h], esi
0x18000e6d8  jz      short loc_18000E6E4
0x18000e6da  xor     r8d, r8d
0x18000e6dd  mov     edx, edi
0x18000e6df  call    SetOffDesktop
0x18000e6e4  mov     [r13+1D4h], edi
0x18000e6eb  mov     r15d, edi
0x18000e6ee  mov     rcx, r13
0x18000e6f1  mov     [r13+1D8h], esi
0x18000e6f8  call    FindEntryAndSetDialParams
0x18000e6fd  mov     [rbp+57h+var_A0], eax
0x18000e700  mov     edi, eax
0x18000e702  test    eax, eax
0x18000e704  jz      short loc_18000E775
0x18000e706  cmp     eax, 26Fh
0x18000e70b  jnz     loc_18000EB82
0x18000e711  test    r12, r12
0x18000e714  jnz     loc_18000EB82
0x18000e71a  lea     rdi, [r13+30h]
0x18000e71e  mov     [rbp+57h+var_78], rsi
0x18000e722  mov     rcx, rdi
0x18000e725  call    cs:__imp_ClosePhonebookFile
0x18000e72b  mov     rdx, [rbp+57h+arg_8]
0x18000e72f  lea     rax, [rbp+57h+var_78]
0x18000e733  mov     r9, rdi
0x18000e736  mov     qword ptr [rsp+110h+var_F0], rax
0x18000e73b  xor     r8d, r8d
0x18000e73e  xor     ecx, ecx
0x18000e740  call    cs:__imp_GetPbkAndEntryName
0x18000e746  cmp     [rbp+57h+var_78], rsi
0x18000e74a  jz      loc_18000EB8A
0x18000e750  test    eax, eax
0x18000e752  jnz     loc_18000EB8A
0x18000e758  mov     rcx, r13
0x18000e75b  mov     [r13+28h], rdi
0x18000e75f  mov     [r13+20h], rdi
0x18000e763  call    FindEntryAndSetDialParams
0x18000e768  mov     [rbp+57h+var_A0], eax
0x18000e76b  mov     edi, eax
0x18000e76d  test    eax, eax
0x18000e76f  jnz     loc_18000EB82
0x18000e775  mov     rax, [rbx+20h]
0x18000e779  test    rax, rax
0x18000e77c  jz      short loc_18000E79B
0x18000e77e  cmp     [r13+1D4h], esi
0x18000e785  jz      short loc_18000E790
0x18000e787  mov     [r13+180h], rsi
0x18000e78e  jmp     short loc_18000E79B
0x18000e790  add     rax, 28h ; '('
0x18000e794  mov     [r13+180h], rax
0x18000e79b  mov     r10, [r13+1B8h]
0x18000e7a2  mov     r8, [r10+1C0h]
0x18000e7a9  test    r8, r8
0x18000e7ac  jz      loc_18000E86B
0x18000e7b2  cmp     si, [r8]
0x18000e7b6  jz      loc_18000E86B
0x18000e7bc  mov     edx, [r10+0A4h]
0x18000e7c3  xor     eax, eax
0x18000e7c5  shr     edx, 6
0x18000e7c8  mov     esi, 1
0x18000e7cd  and     edx, 2
0x18000e7d0  cmp     [r13+178h], rax
0x18000e7d7  jz      short loc_18000E7E5
0x18000e7d9  cmp     [r13+188h], eax
0x18000e7e0  jz      short loc_18000E7E5
  ... truncated ...
```
