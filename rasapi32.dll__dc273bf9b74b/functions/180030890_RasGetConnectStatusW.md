# RasGetConnectStatusW

- ea: `0x180030890`
- end: `0x1800315f4`
- name: `RasGetConnectStatusW`
- size: `3428`
- prototype: `DWORD __stdcall(HRASCONN, struct tagRASCONNSTATUSW *)`
- caller_count: `3`
- callee_count: `19`
- tags: `loader_planting, service_task`

## callers

- `0x18006f560`
- `0x180075e60`
- `0x1800b14d0`

## callees

- `0x180006afc`
- `0x180010d10`
- `0x180011084`
- `0x1800111f4`
- `0x180012570`
- `0x180030890`
- `0x1800315fc`
- `0x18003174c`
- `0x180031b0c`
- `0x18003e0a8`
- `0x18004e580`
- `0x18004e984`
- `0x18007e5f0`
- `0x18007e6c8`
- `0x18007f18c`
- `0x180097e90`
- `0x1800ded06`
- `0x1800ded50`
- `0x1800e0010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180030c1d`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180030c1d`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180030d07`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180030f03`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180030f5a`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180030d07`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180030f03`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180030f5a`
- `rtutils!TracePrintfExA` at `0x180030e96`
- `rtutils!TracePrintfExA` at `0x180031290`
- `rtutils!TracePrintfExA` at `0x1800313b3`
- `rtutils!TracePrintfExA` at `0x180030e96`
- `rtutils!TracePrintfExA` at `0x180031290`
- `rtutils!TracePrintfExA` at `0x1800313b3`
- `rasman!RasGetUnicodeDeviceName` at `0x180030f44`
- `rasman!RasGetUnicodeDeviceName` at `0x1800311d2`
- `rasman!RasGetUnicodeDeviceName` at `0x180030f44`
- `rasman!RasGetUnicodeDeviceName` at `0x1800311d2`

## string_xrefs

- `0x180030e8a`: `StringCchCopy failed due to error 0x%x`
- `0x180031284`: `StringCchCopy failed due to error 0x%x`
- `0x1800313a7`: `StringCchCopy failed due to error 0x%x`

## pseudocode

```c
DWORD __stdcall RasGetConnectStatusW(HRASCONN a1, struct tagRASCONNSTATUSW *a2)
{
  int v4; // r13d
  DWORD v5; // eax
  DWORD v6; // ebx
  _DWORD *v7; // rcx
  __int64 v8; // rdx
  DWORD RasmanDllAndInit; // eax
  enum tagRASCONNSTATE *p_rasconnstate; // rcx
  bool v12; // zf
  int v13; // edi
  int v14; // r14d
  _DWORD *v15; // rcx
  __int64 v16; // rdx
  DWORD v17; // eax
  unsigned int *v18; // rax
  unsigned int *v19; // rsi
  _QWORD *v20; // rcx
  DWORD v21; // eax
  unsigned int i; // edi
  __int64 v23; // r12
  __int64 v24; // rcx
  __int64 v25; // rax
  __int64 v26; // rdx
  void *v27; // rdi
  const WCHAR *v28; // rcx
  __int64 v29; // rax
  wchar_t *v30; // r8
  wchar_t *v31; // rcx
  unsigned int v32; // edi
  _QWORD *v33; // rcx
  __int64 v34; // rdx
  STRSAFE_LPWSTR v35; // r12
  enum tagRASCONNSTATE *v36; // r14
  DWORD v37; // eax
  DWORD v38; // eax
  __int64 v39; // rcx
  __int64 v40; // rcx
  __int64 v41; // rax
  WCHAR *szDeviceName; // rcx
  unsigned int v43; // edi
  __int64 v44; // r11
  WCHAR *v45; // rdx
  __int64 v46; // rax
  __int64 v47; // r8
  WCHAR *v48; // r9
  WCHAR *v49; // rdx
  unsigned int v50; // esi
  WCHAR *szDeviceType; // rcx
  wchar_t *v52; // rax
  WCHAR *v53; // r9
  __int64 v54; // r10
  WCHAR *v55; // r8
  int v56; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v57; // [rsp+34h] [rbp-CCh] BYREF
  int v58; // [rsp+38h] [rbp-C8h] BYREF
  STRSAFE_LPWSTR v59; // [rsp+40h] [rbp-C0h] BYREF
  SIZE_T dwBytes; // [rsp+48h] [rbp-B8h] BYREF
  size_t pcchRemaining; // [rsp+50h] [rbp-B0h] BYREF
  STRSAFE_LPWSTR ppszDestEnd; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v63[4]; // [rsp+60h] [rbp-A0h] BYREF
  int v64; // [rsp+64h] [rbp-9Ch]
  unsigned int v65; // [rsp+1A8h] [rbp+A8h]
  int v66; // [rsp+3C8h] [rbp+2C8h]
  wchar_t pszDest[2]; // [rsp+400h] [rbp+300h] BYREF
  _BYTE v68[30]; // [rsp+404h] [rbp+304h] BYREF
  int v69; // [rsp+430h] [rbp+330h] BYREF
  _BYTE v70[268]; // [rsp+434h] [rbp+334h] BYREF

  v59 = (STRSAFE_LPWSTR)a1;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 62, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids);
  }
  v4 = 0;
  v56 = 0;
  memset(v68, 0, sizeof(v68));
  LODWORD(dwBytes) = 0;
  v57 = 0;
  *(_DWORD *)pszDest = 0;
  v69 = 0;
  memset_0(v70, 0, 0xFEu);
  v58 = 0;
  memset_0(v63, 0, 0x398u);
  DebugInit();
  v5 = CheckRasGetConnectStatusW(&v58, a1, a2);
  v6 = v5;
  if ( v5 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 63, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids, v5);
        v7 = WPP_GLOBAL_Control;
      }
      if ( v7 != (_DWORD *)&WPP_GLOBAL_Control && (v7[7] & 0x800) != 0 && *((_BYTE *)v7 + 25) >= 6u )
      {
        v8 = 64;
        goto LABEL_14;
      }
    }
    return v6;
  }
  if ( !(unsigned int)IsRasmanServiceRunning() )
  {
    v7 = WPP_GLOBAL_Control;
    v6 = 668;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 65, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids, 668);
        v7 = WPP_GLOBAL_Control;
      }
      if ( v7 != (_DWORD *)&WPP_GLOBAL_Control && (v7[7] & 0x800) != 0 && *((_BYTE *)v7 + 25) >= 6u )
      {
        v8 = 66;
        goto LABEL_14;
      }
    }
    return v6;
  }
  RasmanDllAndInit = LoadRasmanDllAndInit();
  v6 = RasmanDllAndInit;
  if ( RasmanDllAndInit )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          67,
          WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids,
          RasmanDllAndInit);
        v7 = WPP_GLOBAL_Control;
      }
      if ( v7 != (_DWORD *)&WPP_GLOBAL_Control && (v7[7] & 0x800) != 0 && *((_BYTE *)v7 + 25) >= 6u )
      {
        v8 = 68;
        goto LABEL_14;
      }
    }
    return v6;
  }
  p_rasconnstate = &a2->rasconnstate;
  if ( v58 == 1 )
  {
    memset_0(p_rasconnstate, 0, 0x12Cu);
    a2->dwSize = 304;
  }
  else if ( v58 == 2 )
  {
    memset_0(p_rasconnstate, 0, 0x230u);
    a2->dwSize = 564;
  }
  else
  {
    memset_0(p_rasconnstate, 0, 0x25Cu);
    a2->dwSize = 608;
  }
  if ( !a1 || (v12 = ((unsigned int)a1 & 0xFFFF0000) == 0, v13 = 0, v12) )
    v13 = 1;
  v14 = SubEntryFromConnection(&v59);
  if ( !v14 )
  {
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      return 6;
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 69, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids, 6);
      v15 = WPP_GLOBAL_Control;
    }
    if ( v15 == (_DWORD *)&WPP_GLOBAL_Control || (v15[7] & 0x800) == 0 || *((_BYTE *)v15 + 25) < 6u )
      return 6;
    v16 = 70;
    goto LABEL_217;
  }
  v17 = ((__int64 (__fastcall *)(STRSAFE_LPWSTR, _QWORD, SIZE_T *, unsigned int *))g_pRasEnumConnectionPorts)(
          v59,
          0,
          &dwBytes,
          &v57);
  v6 = v17;
  if ( !v17 )
    goto LABEL_56;
  v15 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
LABEL_57:
      if ( v15 != (_DWORD *)&WPP_GLOBAL_Control && (v15[7] & 0x800) != 0 && *((_BYTE *)v15 + 25) >= 5u )
      {
        WPP_SF_d(*((_QWORD *)v15 + 2), 72, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids, v57);
        v15 = WPP_GLOBAL_Control;
      }
      goto LABEL_61;
    }
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 71, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids, v17);
LABEL_56:
    v15 = WPP_GLOBAL_Control;
    goto LABEL_57;
  }
LABEL_61:
  if ( v6 != 603 || !v57 )
  {
    if ( !v13 )
    {
      if ( v15 == (_DWORD *)&WPP_GLOBAL_Control || (v15[7] & 0x800) == 0 || *((_BYTE *)v15 + 25) < 6u )
        return 6;
      v16 = 73;
      goto LABEL_217;
    }
    goto LABEL_205;
  }
  v18 = (unsigned int *)GlobalAlloc(0x40u, (unsigned int)dwBytes);
  v19 = v18;
  if ( !v18 )
  {
    v20 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 74, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids, 8);
        v20 = WPP_GLOBAL_Control;
      }
      if ( v20 != &WPP_GLOBAL_Control && (*((_DWORD *)v20 + 7) & 0x800) != 0 && *((_BYTE *)v20 + 25) >= 6u )
        WPP_SF_d(v20[2], 75, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids, 8);
    }
    return 8;
  }
  memset_0(v18, 0, (unsigned int)dwBytes);
  v21 = ((__int64 (__fastcall *)(STRSAFE_LPWSTR, unsigned int *, SIZE_T *, unsigned int *))g_pRasEnumConnectionPorts)(
          v59,
          v19,
          &dwBytes,
          &v57);
  v6 = v21;
  if ( v21 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 76, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids, v21);
    }
    GlobalFree(v19);
    if ( !v13 )
    {
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 6u )
      {
        return 6;
      }
      v16 = 77;
LABEL_217:
      WPP_SF_d(*((_QWORD *)v15 + 2), v16, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids, 6);
      return 6;
    }
    goto LABEL_203;
  }
  v59 = 0;
  for ( i = 0; ; ++i )
  {
    if ( i >= v57 )
      goto LABEL_114;
    v23 = 54LL * i;
    v6 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _BYTE *))g_pRasGetInfo)(0, *(_QWORD *)&v19[v23], v63);
    if ( !v6 )
      break;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 78, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids, v6);
    }
LABEL_91:
    ;
  }
  if ( v66 != v14 )
    goto LABEL_91;
  v4 = 1;
  v24 = v19[7];
  v59 = *(STRSAFE_LPWSTR *)&v19[v23];
  v25 = pszDeviceTypeFromRdt(v24);
  v26 = 17;
  v27 = (void *)v25;
  if ( !v25 )
  {
    v6 = 0;
    v28 = L"modem";
    v29 = 2147483646;
    v30 = pszDest;
    do
    {
      if ( !v29 )
        break;
      if ( !*v28 )
        break;
      *v30++ = *v28++;
      --v29;
      --v26;
    }
    while ( v26 );
    v31 = v30 - 1;
    v32 = v26 == 0 ? 0x8007007A : 0;
    if ( v26 )
      v31 = v30;
    *v31 = 0;
    if ( !v26 )
    {
      StringExHandleOtherFlagsW(pszDest, 0x22u, (size_t)v30, &ppszDestEnd, &pcchRemaining, 0x900u);
      v6 = (unsigned __int16)v32;
      if ( g_dwTraceId != -1 )
        TracePrintfExA(g_dwTraceId, 0xCu, "StringCchCopy failed due to error 0x%x", v32);
    }
    if ( v6 )
    {
      v33 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v34 = 79;
LABEL_107:
        WPP_SF_d(v33[2], v34, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids, v6);
        goto LABEL_114;
      }
      goto LABEL_114;
    }
LABEL_113:
    RasGetUnicodeDeviceName(*(_QWORD *)&v19[v23], &v69);
    goto LABEL_114;
  }
  v6 = StringCchCopyWrapW(pszDest);
  GlobalFree(v27);
  if ( !v6 )
    goto LABEL_113;
  v33 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v34 = 80;
    goto LABEL_107;
  }
LABEL_114:
  GlobalFree(v19);
  if ( !v4 )
  {
LABEL_203:
    v15 = WPP_GLOBAL_Control;
LABEL_205:
    if ( v15 != (_DWORD *)&WPP_GLOBAL_Control && (v15[7] & 0x800) != 0 && *((_BYTE *)v15 + 25) >= 5u )
      WPP_SF_(*((_QWORD *)v15 + 2), 81, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids);
    a2->rasconnstate = RASCS_Disconnected;
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 6u )
    {
      return v6;
    }
    v8 = 82;
    goto LABEL_14;
  }
  v35 = v59;
  v36 = &a2->rasconnstate;
  v56 = 4;
  v37 = ((__int64 (__fastcall *)(STRSAFE_LPWSTR, __int64, enum tagRASCONNSTATE *, int *))g_pRasGetPortUserData)(
          v59,
          3,
          &a2->rasconnstate,
          &v56);
  v6 = v37;
  if ( !v37 )
  {
    v56 = 4;
    v38 = ((__int64 (__fastcall *)(STRSAFE_LPWSTR, __int64, DWORD *, int *))g_pRasGetPortUserData)(
            v35,
            4,
            &a2->dwError,
            &v56);
    v6 = v38;
    if ( v38 )
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        return v6;
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 85, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids, v38);
        v7 = WPP_GLOBAL_Control;
      }
      if ( v7 == (_DWORD *)&WPP_GLOBAL_Control || (v7[7] & 0x800) == 0 || *((_BYTE *)v7 + 25) < 6u )
        return v6;
      v8 = 86;
      goto LABEL_14;
    }
    if ( *v36 == RASCS_Connected && v64 == 4 )
    {
      v39 = v65;
      *v36 = RASCS_Disconnected;
      a2->dwError = ErrorFromDisconnectReason(v39);
    }
    if ( *(int *)v36 < 0x2000 )
    {
      LODWORD(pcchRemaining) = 34;
      LODWORD(v59) = 258;
      LOWORD(v69) = 0;
      pszDest[0] = 0;
      if ( !(unsigned int)((__int64 (__fastcall *)(STRSAFE_LPWSTR, __int64, wchar_t *, size_t *))g_pRasGetPortUserData)(
                            v35,
                            2,
                            pszDest,
                            &pcchRemaining)
        && !(unsigned int)((__int64 (__fastcall *)(STRSAFE_LPWSTR, __int64, int *, STRSAFE_LPWSTR *))g_pRasGetPortUserData)(
                            v35,
                            1,
                            &v69,
                            &v59) )
      {
        v40 = -1;
        v41 = -1;
        do
          ++v41;
        while ( pszDest[v41] );
        if ( v41 )
        {
          do
            ++v40;
          while ( *(_WORD *)&v70[2 * v40 - 4] );
          if ( v40
            && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_SS(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              87,
              (unsigned int)WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids,
              (unsigned int)pszDest,
              (__int64)&v69);
          }
        }
      }
    }
    if ( !CaseInsensitiveMatch(pszDest, L"switch") )
      RasGetUnicodeDeviceName(v35, &v69);
    szDeviceName = a2->szDeviceName;
    v43 = -2147024809;
    if ( a2 == (struct tagRASCONNSTATUSW *)-46LL )
    {
      v50 = -2147024809;
      *szDeviceName = 0;
    }
    else
    {
      v44 = 2147483646;
      v45 = (WCHAR *)&v69;
      v46 = 2147483646;
      v47 = 129;
      v48 = a2->szDeviceName;
      do
      {
        if ( !v46 )
          break;
        if ( !*v45 )
          break;
        *v48++ = *v45++;
        --v46;
        --v47;
      }
      while ( v47 );
      v49 = v48 - 1;
      v50 = v47 == 0 ? 0x8007007A : 0;
      if ( v47 )
        v49 = v48;
      *v49 = 0;
      if ( v47 )
        goto LABEL_172;
      StringExHandleOtherFlagsW(szDeviceName, 0x102u, 0, &v59, (size_t *)&ppszDestEnd, 0x900u);
    }
    v6 = (unsigned __int16)v50;
    if ( g_dwTraceId != -1 )
      TracePrintfExA(g_dwTraceId, 0xCu, "StringCchCopy failed due to error 0x%x", v50);
    if ( (_WORD)v50 )
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        return v6;
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          88,
          WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids,
          (unsigned __int16)v50);
        v7 = WPP_GLOBAL_Control;
      }
      if ( v7 == (_DWORD *)&WPP_GLOBAL_Control || (v7[7] & 0x800) == 0 || *((_BYTE *)v7 + 25) < 6u )
        return v6;
      v8 = 89;
      goto LABEL_14;
    }
    v44 = 2147483646;
LABEL_172:
    szDeviceType = a2->szDeviceType;
    if ( a2 == (struct tagRASCONNSTATUSW *)-12LL )
    {
      *szDeviceType = 0;
    }
    else
    {
      v52 = pszDest;
      v53 = a2->szDeviceType;
      v54 = 17;
      do
      {
        if ( !v44 )
          break;
        if ( !*v52 )
          break;
        *v53++ = *v52++;
        --v44;
        --v54;
      }
      while ( v54 );
      v55 = v53 - 1;
      v43 = v54 == 0 ? 0x8007007A : 0;
      if ( v54 )
        v55 = v53;
      *v55 = 0;
      if ( v54 )
        goto LABEL_193;
      StringExHandleOtherFlagsW(szDeviceType, 0x22u, (size_t)v55, &v59, (size_t *)&ppszDestEnd, 0x900u);
    }
    v6 = (unsigned __int16)v43;
    if ( g_dwTraceId != -1 )
      TracePrintfExA(g_dwTraceId, 0xCu, "StringCchCopy failed due to error 0x%x", v43);
    if ( (_WORD)v43 )
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        return v6;
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          90,
          WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids,
          (unsigned __int16)v43);
        v7 = WPP_GLOBAL_Control;
      }
      if ( v7 == (_DWORD *)&WPP_GLOBAL_Control || (v7[7] & 0x800) == 0 || *((_BYTE *)v7 + 25) < 6u )
        return v6;
      v8 = 91;
LABEL_14:
      WPP_SF_d(*((_QWORD *)v7 + 2), v8, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids, v6);
      return v6;
    }
LABEL_193:
    if ( v58 >= 2 )
    {
      v56 = 258;
      if ( !(unsigned int)((__int64 (__fastcall *)(STRSAFE_LPWSTR, _QWORD, WCHAR *, int *))g_pRasGetPortUserData)(
                            v35,
                            0,
                            a2->szPhoneNumber,
                            &v56)
        && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_S(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          92,
          WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids,
          a2->szPhoneNumber);
      }
    }
    if ( v58 >= 6 )
    {
      v56 = 20;
      ((void (__fastcall *)(STRSAFE_LPWSTR, __int64, struct tagRASTUNNELENDPOINT *, int *))g_pRasGetPortUserData)(
        v35,
        12,
        &a2->localEndPoint,
        &v56);
      v56 = 20;
      ((void (__fastcall *)(STRSAFE_LPWSTR, __int64, struct tagRASTUNNELENDPOINT *, int *))g_pRasGetPortUserData)(
        v35,
        13,
        &a2->remoteEndPoint,
        &v56);
      v12 = *v36 == RASCS_Connected;
      a2->rasconnsubstate = RASCSS_None;
      if ( v12 )
      {
        v56 = 4;
        ((void (__fastcall *)(STRSAFE_LPWSTR, __int64, enum tagRASCONNSUBSTATE *, int *))g_pRasGetPortUserData)(
          v35,
          14,
          &a2->rasconnsubstate,
          &v56);
      }
    }
    return 0;
  }
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 83, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids, v37);
      v7 = WPP_GLOBAL_Control;
    }
    if ( v7 != (_DWORD *)&WPP_GLOBAL_Control && (v7[7] & 0x800) != 0 && *((_BYTE *)v7 + 25) >= 6u )
    {
      v8 = 84;
      goto LABEL_14;
    }
  }
  return v6;
}

```

## disassembly

```asm
0x180030890  mov     [rsp-8+arg_10], rbx
0x180030895  push    rbp
0x180030896  push    rsi
0x180030897  push    rdi
0x180030898  push    r12
0x18003089a  push    r13
0x18003089c  push    r14
0x18003089e  push    r15
0x1800308a0  lea     rbp, [rsp-450h]
0x1800308a8  sub     rsp, 550h
0x1800308af  mov     rax, cs:__security_cookie
0x1800308b6  xor     rax, rsp
0x1800308b9  mov     [rbp+480h+var_40], rax
0x1800308c0  mov     r15, rdx
0x1800308c3  mov     [rsp+580h+var_540], rcx
0x1800308c8  mov     rdi, rcx
0x1800308cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800308d2  lea     rsi, WPP_GLOBAL_Control
0x1800308d9  lea     r14, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids
0x1800308e0  mov     r12d, 800h
0x1800308e6  cmp     rcx, rsi
0x1800308e9  jz      short loc_18003090B
0x1800308eb  test    [rcx+1Ch], r12d
0x1800308ef  jz      short loc_18003090B
0x1800308f1  cmp     byte ptr [rcx+19h], 6
0x1800308f5  jb      short loc_18003090B
0x1800308f7  mov     rcx, [rcx+10h]
0x1800308fb  mov     edx, 3Eh ; '>'
0x180030900  mov     r9, rdi
0x180030903  mov     r8, r14
0x180030906  call    WPP_SF_q
0x18003090b  xor     r13d, r13d
0x18003090e  lea     rcx, [rbp+480h+var_14C]; void *
0x180030915  xorps   xmm0, xmm0
0x180030918  mov     [rsp+580h+var_550], r13d
0x18003091d  movups  xmmword ptr [rbp+480h+var_17C], xmm0
0x180030924  xor     edx, edx; Val
0x180030926  mov     dword ptr [rsp+580h+dwBytes], r13d
0x18003092b  mov     r8d, 0FEh; Size
0x180030931  mov     [rsp+580h+var_54C], r13d
0x180030936  movups  xmmword ptr [rbp+480h+var_17C+0Eh], xmm0
0x18003093d  mov     dword ptr [rbp+480h+pszDest], r13d
0x180030944  mov     [rbp+480h+var_150], r13d
0x18003094b  call    memset_0
0x180030950  xor     edx, edx; Val
0x180030952  mov     [rsp+580h+var_548], r13d
0x180030957  mov     r8d, 398h; Size
0x18003095d  lea     rcx, [rsp+580h+var_520]; void *
0x180030962  call    memset_0
0x180030967  call    DebugInit
0x18003096c  mov     r8, r15
0x18003096f  lea     rcx, [rsp+580h+var_548]
0x180030974  mov     rdx, rdi
0x180030977  call    CheckRasGetConnectStatusW
0x18003097c  mov     ebx, eax
0x18003097e  test    eax, eax
0x180030980  jz      short loc_1800309E0
0x180030982  mov     rcx, cs:WPP_GLOBAL_Control
0x180030989  cmp     rcx, rsi
0x18003098c  jz      short loc_1800309D9
0x18003098e  test    [rcx+1Ch], r12d
0x180030992  jz      short loc_1800309B4
0x180030994  cmp     byte ptr [rcx+19h], 2
0x180030998  jb      short loc_1800309B4
0x18003099a  mov     rcx, [rcx+10h]
0x18003099e  lea     edx, [r13+3Fh]
0x1800309a2  mov     r9d, eax
0x1800309a5  mov     r8, r14
0x1800309a8  call    WPP_SF_d
0x1800309ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1800309b4  cmp     rcx, rsi
0x1800309b7  jz      short loc_1800309D9
0x1800309b9  test    [rcx+1Ch], r12d
0x1800309bd  jz      short loc_1800309D9
0x1800309bf  cmp     byte ptr [rcx+19h], 6
0x1800309c3  jb      short loc_1800309D9
0x1800309c5  mov     edx, 40h ; '@'
0x1800309ca  mov     r8, r14
0x1800309cd  mov     rcx, [rcx+10h]
0x1800309d1  mov     r9d, ebx
0x1800309d4  call    WPP_SF_d
0x1800309d9  mov     eax, ebx
0x1800309db  jmp     loc_1800315CA
0x1800309e0  call    IsRasmanServiceRunning
0x1800309e5  test    eax, eax
0x1800309e7  jnz     short loc_180030A37
0x1800309e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800309f0  mov     ebx, 29Ch
0x1800309f5  cmp     rcx, rsi
0x1800309f8  jz      short loc_1800309D9
0x1800309fa  test    [rcx+1Ch], r12d
0x1800309fe  jz      short loc_180030A1F
0x180030a00  cmp     byte ptr [rcx+19h], 2
0x180030a04  jb      short loc_180030A1F
0x180030a06  mov     rcx, [rcx+10h]
0x180030a0a  lea     edx, [rax+41h]
0x180030a0d  mov     r9d, ebx
0x180030a10  mov     r8, r14
0x180030a13  call    WPP_SF_d
0x180030a18  mov     rcx, cs:WPP_GLOBAL_Control
0x180030a1f  cmp     rcx, rsi
0x180030a22  jz      short loc_1800309D9
0x180030a24  test    [rcx+1Ch], r12d
0x180030a28  jz      short loc_1800309D9
0x180030a2a  cmp     byte ptr [rcx+19h], 6
0x180030a2e  jb      short loc_1800309D9
0x180030a30  mov     edx, 42h ; 'B'
0x180030a35  jmp     short loc_1800309CA
0x180030a37  call    LoadRasmanDllAndInit
0x180030a3c  mov     ebx, eax
0x180030a3e  test    eax, eax
0x180030a40  jz      short loc_180030A9C
0x180030a42  mov     rcx, cs:WPP_GLOBAL_Control
0x180030a49  cmp     rcx, rsi
0x180030a4c  jz      short loc_1800309D9
0x180030a4e  test    [rcx+1Ch], r12d
0x180030a52  jz      short loc_180030A75
0x180030a54  cmp     byte ptr [rcx+19h], 2
0x180030a58  jb      short loc_180030A75
0x180030a5a  mov     rcx, [rcx+10h]
0x180030a5e  mov     edx, 43h ; 'C'
0x180030a63  mov     r9d, eax
0x180030a66  mov     r8, r14
0x180030a69  call    WPP_SF_d
0x180030a6e  mov     rcx, cs:WPP_GLOBAL_Control
0x180030a75  cmp     rcx, rsi
0x180030a78  jz      loc_1800309D9
0x180030a7e  test    [rcx+1Ch], r12d
0x180030a82  jz      loc_1800309D9
0x180030a88  cmp     byte ptr [rcx+19h], 6
0x180030a8c  jb      loc_1800309D9
0x180030a92  mov     edx, 44h ; 'D'
0x180030a97  jmp     loc_1800309CA
0x180030a9c  xor     edx, edx; Val
0x180030a9e  lea     rcx, [r15+4]; void *
0x180030aa2  cmp     [rsp+580h+var_548], 1
0x180030aa7  jnz     short loc_180030ABD
0x180030aa9  mov     r8d, 12Ch; Size
0x180030aaf  call    memset_0
0x180030ab4  mov     dword ptr [r15], 130h
0x180030abb  jmp     short loc_180030AEA
0x180030abd  cmp     [rsp+580h+var_548], 2
0x180030ac2  jnz     short loc_180030AD8
0x180030ac4  mov     r8d, 230h; Size
0x180030aca  call    memset_0
0x180030acf  mov     dword ptr [r15], 234h
0x180030ad6  jmp     short loc_180030AEA
0x180030ad8  mov     r8d, 25Ch; Size
0x180030ade  call    memset_0
0x180030ae3  mov     dword ptr [r15], 260h
0x180030aea  test    rdi, rdi
0x180030aed  jz      short loc_180030AFA
0x180030aef  test    edi, 0FFFF0000h
0x180030af5  mov     edi, r13d
0x180030af8  jnz     short loc_180030AFF
0x180030afa  mov     edi, 1
0x180030aff  lea     rcx, [rsp+580h+var_540]
0x180030b04  call    SubEntryFromConnection
0x180030b09  mov     r14d, eax
0x180030b0c  test    eax, eax
0x180030b0e  jnz     short loc_180030B71
0x180030b10  mov     rcx, cs:WPP_GLOBAL_Control
0x180030b17  cmp     rcx, rsi
0x180030b1a  jz      loc_1800315C5
0x180030b20  test    [rcx+1Ch], r12d
0x180030b24  jz      short loc_180030B4A
0x180030b26  cmp     byte ptr [rcx+19h], 2
0x180030b2a  jb      short loc_180030B4A
0x180030b2c  mov     rcx, [rcx+10h]
0x180030b30  lea     edx, [rax+45h]
0x180030b33  lea     r9d, [rax+6]
0x180030b37  lea     r8, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids
0x180030b3e  call    WPP_SF_d
0x180030b43  mov     rcx, cs:WPP_GLOBAL_Control
0x180030b4a  cmp     rcx, rsi
0x180030b4d  jz      loc_1800315C5
0x180030b53  test    [rcx+1Ch], r12d
0x180030b57  jz      loc_1800315C5
0x180030b5d  cmp     byte ptr [rcx+19h], 6
0x180030b61  jb      loc_1800315C5
0x180030b67  mov     edx, 46h ; 'F'
0x180030b6c  jmp     loc_1800315AF
0x180030b71  mov     rcx, [rsp+580h+var_540]
0x180030b76  lea     r9, [rsp+580h+var_54C]
0x180030b7b  mov     rax, cs:g_pRasEnumConnectionPorts
0x180030b82  lea     r8, [rsp+580h+dwBytes]
0x180030b87  xor     edx, edx
0x180030b89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030b8e  mov     ebx, eax
0x180030b90  test    eax, eax
0x180030b92  jz      short loc_180030BC4
0x180030b94  mov     rcx, cs:WPP_GLOBAL_Control
0x180030b9b  cmp     rcx, rsi
0x180030b9e  jz      short loc_180030BFD
0x180030ba0  test    [rcx+1Ch], r12d
0x180030ba4  jz      short loc_180030BCB
0x180030ba6  cmp     byte ptr [rcx+19h], 2
0x180030baa  jb      short loc_180030BCB
0x180030bac  mov     rcx, [rcx+10h]
0x180030bb0  lea     r8, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids
0x180030bb7  mov     edx, 47h ; 'G'
0x180030bbc  mov     r9d, eax
0x180030bbf  call    WPP_SF_d
0x180030bc4  mov     rcx, cs:WPP_GLOBAL_Control
0x180030bcb  cmp     rcx, rsi
0x180030bce  jz      short loc_180030BFD
0x180030bd0  test    [rcx+1Ch], r12d
0x180030bd4  jz      short loc_180030BFD
0x180030bd6  cmp     byte ptr [rcx+19h], 5
0x180030bda  jb      short loc_180030BFD
0x180030bdc  mov     r9d, [rsp+580h+var_54C]
0x180030be1  lea     r8, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids
0x180030be8  mov     rcx, [rcx+10h]
0x180030bec  mov     edx, 48h ; 'H'
0x180030bf1  call    WPP_SF_d
0x180030bf6  mov     rcx, cs:WPP_GLOBAL_Control
0x180030bfd  cmp     ebx, 25Bh
0x180030c03  jnz     loc_180031532
0x180030c09  cmp     [rsp+580h+var_54C], r13d
0x180030c0e  jz      loc_180031532
0x180030c14  mov     edx, dword ptr [rsp+580h+dwBytes]; dwBytes
0x180030c18  mov     ecx, 40h ; '@'; uFlags
0x180030c1d  call    cs:__imp_GlobalAlloc
0x180030c23  mov     rsi, rax
0x180030c26  test    rax, rax
0x180030c29  jnz     short loc_180030C9A
0x180030c2b  mov     rcx, cs:WPP_GLOBAL_Control
0x180030c32  lea     rbx, WPP_GLOBAL_Control
0x180030c39  lea     edi, [rax+8]
0x180030c3c  cmp     rcx, rbx
0x180030c3f  jz      short loc_180030C93
0x180030c41  test    [rcx+1Ch], r12d
0x180030c45  jz      short loc_180030C6A
0x180030c47  cmp     byte ptr [rcx+19h], 2
0x180030c4b  jb      short loc_180030C6A
0x180030c4d  mov     rcx, [rcx+10h]
0x180030c51  lea     edx, [rax+4Ah]
0x180030c54  mov     r9d, edi
0x180030c57  lea     r8, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids
0x180030c5e  call    WPP_SF_d
0x180030c63  mov     rcx, cs:WPP_GLOBAL_Control
0x180030c6a  cmp     rcx, rbx
0x180030c6d  jz      short loc_180030C93
0x180030c6f  test    [rcx+1Ch], r12d
0x180030c73  jz      short loc_180030C93
0x180030c75  cmp     byte ptr [rcx+19h], 6
0x180030c79  jb      short loc_180030C93
0x180030c7b  mov     rcx, [rcx+10h]
0x180030c7f  lea     r8, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids
0x180030c86  mov     edx, 4Bh ; 'K'
0x180030c8b  mov     r9d, edi
0x180030c8e  call    WPP_SF_d
0x180030c93  mov     eax, edi
0x180030c95  jmp     loc_1800315CA
0x180030c9a  mov     r8d, dword ptr [rsp+580h+dwBytes]; Size
0x180030c9f  xor     edx, edx; Val
0x180030ca1  mov     rcx, rsi; void *
0x180030ca4  call    memset_0
0x180030ca9  mov     rcx, [rsp+580h+var_540]
0x180030cae  lea     r9, [rsp+580h+var_54C]
0x180030cb3  mov     rax, cs:g_pRasEnumConnectionPorts
0x180030cba  lea     r8, [rsp+580h+dwBytes]
0x180030cbf  mov     rdx, rsi
0x180030cc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030cc7  mov     ebx, eax
0x180030cc9  test    eax, eax
0x180030ccb  jz      short loc_180030D41
0x180030ccd  mov     rcx, cs:WPP_GLOBAL_Control
0x180030cd4  lea     r14, WPP_GLOBAL_Control
0x180030cdb  cmp     rcx, r14
0x180030cde  jz      short loc_180030D04
0x180030ce0  test    [rcx+1Ch], r12d
0x180030ce4  jz      short loc_180030D04
0x180030ce6  cmp     byte ptr [rcx+19h], 2
0x180030cea  jb      short loc_180030D04
0x180030cec  mov     rcx, [rcx+10h]
0x180030cf0  lea     r8, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids
0x180030cf7  mov     edx, 4Ch ; 'L'
0x180030cfc  mov     r9d, eax
0x180030cff  call    WPP_SF_d
0x180030d04  mov     rcx, rsi; hMem
0x180030d07  call    cs:__imp_GlobalFree
0x180030d0d  test    edi, edi
0x180030d0f  jnz     loc_180031522
0x180030d15  mov     rcx, cs:WPP_GLOBAL_Control
0x180030d1c  cmp     rcx, r14
0x180030d1f  jz      loc_1800315C5
0x180030d25  test    [rcx+1Ch], r12d
0x180030d29  jz      loc_1800315C5
0x180030d2f  cmp     byte ptr [rcx+19h], 6
0x180030d33  jb      loc_1800315C5
0x180030d39  lea     edx, [rdi+4Dh]
0x180030d3c  jmp     loc_1800315AF
0x180030d41  mov     [rsp+580h+var_540], r13
0x180030d46  xor     edi, edi
0x180030d48  cmp     edi, [rsp+580h+var_54C]
0x180030d4c  jnb     loc_180030F50
0x180030d52  mov     eax, edi
0x180030d54  lea     r8, [rsp+580h+var_520]
0x180030d59  imul    r12, rax, 0D8h
  ... truncated ...
```
