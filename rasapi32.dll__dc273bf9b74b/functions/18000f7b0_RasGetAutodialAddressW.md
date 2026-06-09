# RasGetAutodialAddressW

- ea: `0x18000f7b0`
- end: `0x18001016e`
- name: `RasGetAutodialAddressW`
- size: `2494`
- prototype: `DWORD __stdcall(LPCWSTR, LPDWORD, struct tagRASAUTODIALENTRYW *, LPDWORD, LPDWORD)`
- caller_count: `3`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800430dc`
- `0x18006ea30`
- `0x180097c80`

## callees

- `0x180006afc`
- `0x18000eea0`
- `0x18000f31c`
- `0x18000f4fc`
- `0x18000f7b0`
- `0x180010d10`
- `0x18004e580`
- `0x18004e984`
- `0x1800661c4`
- `0x18006a074`
- `0x18007e5f0`
- `0x1800ded06`
- `0x1800ded50`

## import_xrefs

- `msvcrt!_wtol` at `0x180010013`
- `msvcrt!_wtol` at `0x180010013`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000fc81`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000fd9d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000fc81`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000fd9d`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000fe1f`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000fe1f`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18000fff1`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18000fff1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f943`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f95c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f9d0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f943`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f95c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f9d0`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18000feea`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18000ff49`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18000feea`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18000ff49`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18000f971`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18000f98a`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18000f99f`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18000f9b8`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18000f971`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18000f98a`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18000f99f`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18000f9b8`

## pseudocode

```c
DWORD __stdcall RasGetAutodialAddressW(LPCWSTR a1, LPDWORD a2, struct tagRASAUTODIALENTRYW *a3, LPDWORD a4, LPDWORD a5)
{
  BYTE *v5; // r12
  int v8; // ebx
  DWORD v10; // r15d
  unsigned int v11; // eax
  DWORD v12; // ebx
  _QWORD *v13; // rcx
  __int64 v14; // rdx
  void *v15; // r14
  __int64 v16; // rdx
  DWORD v18; // eax
  _QWORD *v19; // rcx
  __int64 v20; // rdx
  LPDWORD v21; // rax
  __int64 v22; // rcx
  int *v23; // rax
  __int128 v24; // xmm1
  __int128 v25; // xmm0
  __int128 v26; // xmm1
  __int128 v27; // xmm0
  __int128 v28; // xmm1
  __int128 v29; // xmm0
  __int128 v30; // xmm1
  DWORD v31; // eax
  __int64 v32; // r9
  __int64 v33; // rdx
  unsigned int v34; // eax
  DWORD v35; // edx
  DWORD v36; // ebx
  _DWORD *v37; // rcx
  unsigned __int64 v38; // rax
  __int64 v39; // r9
  __int64 v40; // rdx
  SIZE_T v41; // rdx
  HGLOBAL v42; // rcx
  unsigned int v43; // eax
  const wchar_t *v44; // rcx
  __int64 v45; // rbx
  DWORD cbMaxValueLen; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cchValueName; // [rsp+68h] [rbp-98h] BYREF
  DWORD cValues; // [rsp+70h] [rbp-90h] BYREF
  DWORD cbMaxValueNameLen; // [rsp+74h] [rbp-8Ch] BYREF
  DWORD cbData; // [rsp+78h] [rbp-88h] BYREF
  int v51; // [rsp+7Ch] [rbp-84h]
  HGLOBAL v52; // [rsp+80h] [rbp-80h]
  BYTE *v53; // [rsp+88h] [rbp-78h] BYREF
  LPDWORD v54; // [rsp+90h] [rbp-70h]
  HKEY hKey; // [rsp+98h] [rbp-68h] BYREF
  HKEY phkResult; // [rsp+A0h] [rbp-60h] BYREF
  HGLOBAL hMem; // [rsp+A8h] [rbp-58h]
  HKEY v58; // [rsp+B0h] [rbp-50h] BYREF
  int v59; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v60[524]; // [rsp+C4h] [rbp-3Ch] BYREF

  v5 = 0;
  v54 = a5;
  v8 = (int)a2;
  if ( a1 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 710, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids, a1);
    }
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
         && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 711, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids);
  }
  v51 = 0;
  v10 = 0;
  v58 = 0;
  hKey = 0;
  phkResult = 0;
  cValues = 0;
  cbMaxValueNameLen = 0;
  cbMaxValueLen = 0;
  hMem = 0;
  v52 = 0;
  v53 = 0;
  cbData = 0;
  DebugInit();
  v11 = CheckRasGetAutodialAddressW((unsigned int)&cbData, (_DWORD)a1, v8, (_DWORD)a3, (__int64)a4, (__int64)v54);
  v12 = v11;
  if ( v11 )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_16;
    }
    v14 = 712;
LABEL_15:
    WPP_SF_d(v13[2], v14, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids, v11);
    v13 = WPP_GLOBAL_Control;
LABEL_16:
    v15 = 0;
    goto LABEL_17;
  }
  if ( a1 )
  {
    v11 = DwOpenUsersRegistry(&v58);
    v12 = v11;
    if ( v11 )
    {
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_16;
      }
      v14 = 719;
      goto LABEL_15;
    }
    v11 = RegOpenKeyExW(v58, L"Software\\Microsoft\\RAS AutoDial", 0, 0x2001Du, &hKey);
    v12 = v11;
    if ( v11 )
    {
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_16;
      }
      v14 = 720;
      goto LABEL_15;
    }
    v31 = AutodialAddressToNetwork(hKey, (__int64)a1, &v53);
    v12 = v31;
    if ( v31 )
    {
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 721, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids, v31);
        v13 = WPP_GLOBAL_Control;
      }
      v5 = v53;
      v15 = 0;
LABEL_17:
      if ( !a4 )
      {
LABEL_19:
        if ( v54 )
        {
          *v54 = v10;
          v13 = WPP_GLOBAL_Control;
        }
        if ( hKey )
        {
          RegCloseKey(hKey);
          v13 = WPP_GLOBAL_Control;
        }
        if ( phkResult )
        {
          RegCloseKey(phkResult);
          v13 = WPP_GLOBAL_Control;
        }
        if ( v15 )
        {
          GlobalFree(v15);
          v13 = WPP_GLOBAL_Control;
        }
        if ( hMem )
        {
          GlobalFree(hMem);
          v13 = WPP_GLOBAL_Control;
        }
        if ( v5 )
        {
          GlobalFree(v5);
          v13 = WPP_GLOBAL_Control;
        }
        if ( v52 )
        {
          GlobalFree(v52);
          v13 = WPP_GLOBAL_Control;
        }
        if ( v51 )
        {
          RegCloseKey(v58);
          v13 = WPP_GLOBAL_Control;
        }
        if ( v13 == &WPP_GLOBAL_Control || (*((_DWORD *)v13 + 7) & 0x800) == 0 || *((_BYTE *)v13 + 25) < 6u )
          return v12;
        v16 = 733;
        goto LABEL_39;
      }
      goto LABEL_18;
    }
    v5 = v53;
    v15 = (void *)FormatKey(L"Networks", v53);
    if ( !v15 )
    {
      v32 = 8;
      v12 = 8;
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_17;
      }
      v33 = 722;
      goto LABEL_94;
    }
    v34 = RegOpenKeyExW(hKey, (LPCWSTR)v15, 0, 0x20019u, &phkResult);
    v12 = v34;
    if ( v34 )
    {
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_17;
      }
      v33 = 723;
LABEL_101:
      v32 = v34;
LABEL_94:
      WPP_SF_d(v13[2], v33, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids, v32);
LABEL_95:
      v13 = WPP_GLOBAL_Control;
      goto LABEL_17;
    }
    v34 = RegQueryInfoKeyW(phkResult, 0, 0, 0, 0, 0, 0, &cValues, &cbMaxValueNameLen, &cbMaxValueLen, 0, 0);
    v12 = v34;
    if ( v34 )
    {
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_17;
      }
      v33 = 724;
      goto LABEL_101;
    }
    v35 = cValues;
    if ( !cValues )
      goto LABEL_95;
    if ( *a4 < 528 * cValues || !a3 )
    {
      v12 = 603;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 725, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids, 603);
        v35 = cValues;
      }
      v10 = v35;
      goto LABEL_18;
    }
    v36 = cbMaxValueNameLen + 1;
    if ( cbMaxValueNameLen + 1 < cbMaxValueNameLen )
    {
      v36 = -1;
      v37 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
LABEL_116:
        v38 = 2LL * v36;
        if ( v38 > 0xFFFFFFFF )
        {
          v12 = -2147024362;
          if ( v37 == (_DWORD *)&WPP_GLOBAL_Control || (v37[7] & 0x800) == 0 || *((_BYTE *)v37 + 25) < 2u )
            goto LABEL_18;
          v40 = 727;
          v39 = 2147942934LL;
        }
        else
        {
          hMem = GlobalAlloc(0x40u, (unsigned int)v38);
          if ( hMem )
          {
            v41 = cbMaxValueLen + 1;
            if ( (unsigned int)v41 < cbMaxValueLen )
            {
              cbMaxValueLen = -1;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  729,
                  WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids,
                  2147942934LL);
              }
              v12 = -2147024362;
              goto LABEL_18;
            }
            ++cbMaxValueLen;
            v52 = GlobalAlloc(0x40u, v41);
            v42 = v52;
            if ( v52 )
            {
              v12 = 0;
              while ( 1 )
              {
                if ( v10 >= cValues )
                  goto LABEL_18;
                cchValueName = cbMaxValueNameLen + 1;
                cbData = cbMaxValueLen;
                memset_0(v42, 0, cbMaxValueLen);
                v43 = RegEnumValueW(phkResult, v10, (LPWSTR)hMem, &cchValueName, 0, 0, (LPBYTE)v52, &cbData);
                v12 = v43;
                if ( v43 )
                  break;
                v44 = (const wchar_t *)hMem;
                v45 = v10;
                *(_QWORD *)&a3[v45].dwSize = 528;
                a3[v45].dwDialingLocation = _wtol(v44);
                v43 = StringCchCopyWrapW(a3[v45].szEntry);
                v12 = v43;
                if ( v43 )
                {
                  v37 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                  {
                    v40 = 732;
LABEL_141:
                    v39 = v43;
                    goto LABEL_151;
                  }
                  goto LABEL_18;
                }
                v42 = v52;
                ++v10;
              }
              v37 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                v40 = 731;
                goto LABEL_141;
              }
              goto LABEL_18;
            }
            v39 = 8;
            v12 = 8;
            v37 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
              || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
LABEL_18:
              *a4 = 528 * v10;
              v13 = WPP_GLOBAL_Control;
              goto LABEL_19;
            }
            v40 = 730;
          }
          else
          {
            v39 = 8;
            v12 = 8;
            v37 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
              || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_18;
            }
            v40 = 728;
          }
        }
LABEL_151:
        WPP_SF_d(*((_QWORD *)v37 + 2), v40, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids, v39);
        goto LABEL_18;
      }
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 726, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids, 2147942934LL);
    }
    v37 = WPP_GLOBAL_Control;
    goto LABEL_116;
  }
  memset_0(v60, 0, sizeof(v60));
  v59 = 528;
  v18 = RasDefIntConnGet(&v59);
  v12 = v18;
  if ( !v18 )
  {
    v21 = v54;
    *a4 = 528;
    *v21 = 1;
    if ( a3 )
    {
      v22 = 4;
      v23 = &v59;
      do
      {
        v24 = *((_OWORD *)v23 + 1);
        *(_OWORD *)&a3->dwSize = *(_OWORD *)v23;
        v25 = *((_OWORD *)v23 + 2);
        *(_OWORD *)&a3->szEntry[2] = v24;
        v26 = *((_OWORD *)v23 + 3);
        *(_OWORD *)&a3->szEntry[10] = v25;
        v27 = *((_OWORD *)v23 + 4);
        *(_OWORD *)&a3->szEntry[18] = v26;
        v28 = *((_OWORD *)v23 + 5);
        *(_OWORD *)&a3->szEntry[26] = v27;
        v29 = *((_OWORD *)v23 + 6);
        *(_OWORD *)&a3->szEntry[34] = v28;
        v30 = *((_OWORD *)v23 + 7);
        v23 += 32;
        *(_OWORD *)&a3->szEntry[42] = v29;
        *(_OWORD *)&a3->szEntry[50] = v30;
        a3 = (struct tagRASAUTODIALENTRYW *)((char *)a3 + 128);
        --v22;
      }
      while ( v22 );
      *(_OWORD *)&a3->dwSize = *(_OWORD *)v23;
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 6u )
      {
        return 0;
      }
      v20 = 718;
      goto LABEL_71;
    }
    v13 = WPP_GLOBAL_Control;
    v12 = 603;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      return v12;
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 716, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids, 603);
      v13 = WPP_GLOBAL_Control;
    }
    if ( v13 == &WPP_GLOBAL_Control || (*((_DWORD *)v13 + 7) & 0x800) == 0 || *((_BYTE *)v13 + 25) < 6u )
      return v12;
    v16 = 717;
LABEL_39:
    WPP_SF_d(v13[2], v16, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids, v12);
    return v12;
  }
  v13 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 713, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids, v18);
    v13 = WPP_GLOBAL_Control;
  }
  if ( v12 != 2 )
  {
    if ( v13 == &WPP_GLOBAL_Control || (*((_DWORD *)v13 + 7) & 0x800) == 0 || *((_BYTE *)v13 + 25) < 6u )
      return v12;
    v16 = 715;
    goto LABEL_39;
  }
  *v54 = 0;
  *a4 = 0;
  v19 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
    || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0
    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 6u )
  {
    return 0;
  }
  v20 = 714;
LABEL_71:
  WPP_SF_d(v19[2], v20, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids, 0);
  return 0;
}

```

## disassembly

```asm
0x18000f7b0  push    rbp
0x18000f7b2  push    rbx
0x18000f7b3  push    rsi
0x18000f7b4  push    rdi
0x18000f7b5  push    r12
0x18000f7b7  push    r13
0x18000f7b9  push    r14
0x18000f7bb  push    r15
0x18000f7bd  lea     rbp, [rsp-1E8h]
0x18000f7c5  sub     rsp, 2E8h
0x18000f7cc  mov     rax, cs:__security_cookie
0x18000f7d3  xor     rax, rsp
0x18000f7d6  mov     [rbp+220h+var_50], rax
0x18000f7dd  mov     rax, [rbp+220h+arg_20]
0x18000f7e4  xor     r12d, r12d
0x18000f7e7  mov     [rbp+220h+var_290], rax
0x18000f7eb  mov     eax, 800h
0x18000f7f0  mov     r13, r9
0x18000f7f3  mov     rsi, r8
0x18000f7f6  mov     rbx, rdx
0x18000f7f9  mov     r14, rcx
0x18000f7fc  test    rcx, rcx
0x18000f7ff  jz      short loc_18000F839
0x18000f801  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f808  lea     rdi, WPP_GLOBAL_Control
0x18000f80f  cmp     rcx, rdi
0x18000f812  jz      short loc_18000F86C
0x18000f814  test    [rcx+1Ch], eax
0x18000f817  jz      short loc_18000F86C
0x18000f819  cmp     byte ptr [rcx+19h], 6
0x18000f81d  jb      short loc_18000F86C
0x18000f81f  mov     rcx, [rcx+10h]
0x18000f823  lea     r8, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids
0x18000f82a  mov     edx, 2C6h
0x18000f82f  mov     r9, r14
0x18000f832  call    WPP_SF_S
0x18000f837  jmp     short loc_18000F86C
0x18000f839  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f840  lea     rdi, WPP_GLOBAL_Control
0x18000f847  cmp     rcx, rdi
0x18000f84a  jz      short loc_18000F86C
0x18000f84c  test    [rcx+1Ch], eax
0x18000f84f  jz      short loc_18000F86C
0x18000f851  cmp     byte ptr [rcx+19h], 6
0x18000f855  jb      short loc_18000F86C
0x18000f857  mov     rcx, [rcx+10h]
0x18000f85b  lea     r8, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids
0x18000f862  mov     edx, 2C7h
0x18000f867  call    WPP_SF_
0x18000f86c  mov     [rsp+320h+var_2A4], r12d
0x18000f871  mov     r15d, r12d
0x18000f874  mov     [rbp+220h+var_270], r12
0x18000f878  mov     [rbp+220h+hKey], r12
0x18000f87c  mov     [rbp+220h+var_280], r12
0x18000f880  mov     [rsp+320h+cValues], r12d
0x18000f885  mov     [rsp+320h+cbMaxValueNameLen], r12d
0x18000f88a  mov     [rsp+320h+cbMaxValueLen], r12d
0x18000f88f  mov     [rbp+220h+hMem], r12
0x18000f893  mov     [rbp+220h+var_2A0], r12
0x18000f897  mov     [rbp+220h+var_298], r12
0x18000f89b  mov     [rsp+320h+cbData], r12d
0x18000f8a0  call    DebugInit
0x18000f8a5  mov     rax, [rbp+220h+var_290]
0x18000f8a9  lea     rcx, [rsp+320h+cbData]
0x18000f8ae  mov     [rsp+320h+lpcbMaxSubKeyLen], rax
0x18000f8b3  mov     r9, rsi
0x18000f8b6  mov     r8, rbx
0x18000f8b9  mov     [rsp+320h+phkResult], r13
0x18000f8be  mov     rdx, r14
0x18000f8c1  call    CheckRasGetAutodialAddressW
0x18000f8c6  mov     ebx, eax
0x18000f8c8  test    eax, eax
0x18000f8ca  jz      loc_18000FA2E
0x18000f8d0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f8d7  cmp     rcx, rdi
0x18000f8da  jz      short loc_18000F90A
0x18000f8dc  test    dword ptr [rcx+1Ch], 800h
0x18000f8e3  jz      short loc_18000F90A
0x18000f8e5  cmp     byte ptr [rcx+19h], 2
0x18000f8e9  jb      short loc_18000F90A
0x18000f8eb  mov     edx, 2C8h
0x18000f8f0  mov     rcx, [rcx+10h]
0x18000f8f4  lea     r8, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids
0x18000f8fb  mov     r9d, eax
0x18000f8fe  call    WPP_SF_d
0x18000f903  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f90a  mov     r14, r12
0x18000f90d  test    r13, r13
0x18000f910  jz      short loc_18000F924
0x18000f912  imul    eax, r15d, 210h
0x18000f919  mov     [r13+0], eax
0x18000f91d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f924  mov     rax, [rbp+220h+var_290]
0x18000f928  test    rax, rax
0x18000f92b  jz      short loc_18000F937
0x18000f92d  mov     [rax], r15d
0x18000f930  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f937  mov     rax, [rbp+220h+hKey]
0x18000f93b  test    rax, rax
0x18000f93e  jz      short loc_18000F950
0x18000f940  mov     rcx, rax; hKey
0x18000f943  call    cs:__imp_RegCloseKey
0x18000f949  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f950  mov     rax, [rbp+220h+var_280]
0x18000f954  test    rax, rax
0x18000f957  jz      short loc_18000F969
0x18000f959  mov     rcx, rax; hKey
0x18000f95c  call    cs:__imp_RegCloseKey
0x18000f962  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f969  test    r14, r14
0x18000f96c  jz      short loc_18000F97E
0x18000f96e  mov     rcx, r14; hMem
0x18000f971  call    cs:__imp_GlobalFree
0x18000f977  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f97e  mov     rax, [rbp+220h+hMem]
0x18000f982  test    rax, rax
0x18000f985  jz      short loc_18000F997
0x18000f987  mov     rcx, rax; hMem
0x18000f98a  call    cs:__imp_GlobalFree
0x18000f990  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f997  test    r12, r12
0x18000f99a  jz      short loc_18000F9AC
0x18000f99c  mov     rcx, r12; hMem
0x18000f99f  call    cs:__imp_GlobalFree
0x18000f9a5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f9ac  mov     rax, [rbp+220h+var_2A0]
0x18000f9b0  test    rax, rax
0x18000f9b3  jz      short loc_18000F9C5
0x18000f9b5  mov     rcx, rax; hMem
0x18000f9b8  call    cs:__imp_GlobalFree
0x18000f9be  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f9c5  cmp     [rsp+320h+var_2A4], 0
0x18000f9ca  jz      short loc_18000F9DD
0x18000f9cc  mov     rcx, [rbp+220h+var_270]; hKey
0x18000f9d0  call    cs:__imp_RegCloseKey
0x18000f9d6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f9dd  cmp     rcx, rdi
0x18000f9e0  jz      short loc_18000FA09
0x18000f9e2  test    dword ptr [rcx+1Ch], 800h
0x18000f9e9  jz      short loc_18000FA09
0x18000f9eb  cmp     byte ptr [rcx+19h], 6
0x18000f9ef  jb      short loc_18000FA09
0x18000f9f1  mov     edx, 2DDh
0x18000f9f6  mov     rcx, [rcx+10h]
0x18000f9fa  lea     r8, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids
0x18000fa01  mov     r9d, ebx
0x18000fa04  call    WPP_SF_d
0x18000fa09  mov     eax, ebx
0x18000fa0b  mov     rcx, [rbp+220h+var_50]
0x18000fa12  xor     rcx, rsp; StackCookie
0x18000fa15  call    __security_check_cookie
0x18000fa1a  add     rsp, 2E8h
0x18000fa21  pop     r15
0x18000fa23  pop     r14
0x18000fa25  pop     r13
0x18000fa27  pop     r12
0x18000fa29  pop     rdi
0x18000fa2a  pop     rsi
0x18000fa2b  pop     rbx
0x18000fa2c  pop     rbp
0x18000fa2d  retn
0x18000fa2e  test    r14, r14
0x18000fa31  jnz     loc_18000FC1F
0x18000fa37  xor     edx, edx; Val
0x18000fa39  lea     rcx, [rbp+220h+var_25C]; void *
0x18000fa3d  mov     r8d, 20Ch; Size
0x18000fa43  call    memset_0
0x18000fa48  lea     rcx, [rbp+220h+var_260]
0x18000fa4c  mov     [rbp+220h+var_260], 210h
0x18000fa53  call    RasDefIntConnGet
0x18000fa58  mov     ebx, eax
0x18000fa5a  test    eax, eax
0x18000fa5c  jz      loc_18000FB07
0x18000fa62  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fa69  cmp     rcx, rdi
0x18000fa6c  jz      short loc_18000FA9C
0x18000fa6e  test    dword ptr [rcx+1Ch], 800h
0x18000fa75  jz      short loc_18000FA9C
0x18000fa77  cmp     byte ptr [rcx+19h], 2
0x18000fa7b  jb      short loc_18000FA9C
0x18000fa7d  mov     rcx, [rcx+10h]
0x18000fa81  lea     r8, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids
0x18000fa88  mov     edx, 2C9h
0x18000fa8d  mov     r9d, eax
0x18000fa90  call    WPP_SF_d
0x18000fa95  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fa9c  cmp     ebx, 2
0x18000fa9f  jnz     short loc_18000FADD
0x18000faa1  mov     rax, [rbp+220h+var_290]
0x18000faa5  mov     [rax], r12d
0x18000faa8  mov     [r13+0], r12d
0x18000faac  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fab3  cmp     rcx, rdi
0x18000fab6  jz      loc_18000FC18
0x18000fabc  test    dword ptr [rcx+1Ch], 800h
0x18000fac3  jz      loc_18000FC18
0x18000fac9  cmp     byte ptr [rcx+19h], 6
0x18000facd  jb      loc_18000FC18
0x18000fad3  mov     edx, 2CAh
0x18000fad8  jmp     loc_18000FC05
0x18000fadd  cmp     rcx, rdi
0x18000fae0  jz      loc_18000FA09
0x18000fae6  test    dword ptr [rcx+1Ch], 800h
0x18000faed  jz      loc_18000FA09
0x18000faf3  cmp     byte ptr [rcx+19h], 6
0x18000faf7  jb      loc_18000FA09
0x18000fafd  mov     edx, 2CBh
0x18000fb02  jmp     loc_18000F9F6
0x18000fb07  mov     rax, [rbp+220h+var_290]
0x18000fb0b  mov     dword ptr [r13+0], 210h
0x18000fb13  mov     dword ptr [rax], 1
0x18000fb19  test    rsi, rsi
0x18000fb1c  jnz     short loc_18000FB89
0x18000fb1e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fb25  mov     ebx, 25Bh
0x18000fb2a  cmp     rcx, rdi
0x18000fb2d  jz      loc_18000FA09
0x18000fb33  test    dword ptr [rcx+1Ch], 800h
0x18000fb3a  jz      short loc_18000FB5F
0x18000fb3c  cmp     byte ptr [rcx+19h], 2
0x18000fb40  jb      short loc_18000FB5F
0x18000fb42  mov     rcx, [rcx+10h]
0x18000fb46  lea     edx, [rbx+71h]
0x18000fb49  mov     r9d, ebx
0x18000fb4c  lea     r8, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids
0x18000fb53  call    WPP_SF_d
0x18000fb58  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fb5f  cmp     rcx, rdi
0x18000fb62  jz      loc_18000FA09
0x18000fb68  test    dword ptr [rcx+1Ch], 800h
0x18000fb6f  jz      loc_18000FA09
0x18000fb75  cmp     byte ptr [rcx+19h], 6
0x18000fb79  jb      loc_18000FA09
0x18000fb7f  mov     edx, 2CDh
0x18000fb84  jmp     loc_18000F9F6
0x18000fb89  mov     ecx, 4
0x18000fb8e  lea     rax, [rbp+220h+var_260]
0x18000fb92  lea     edx, [rcx+7Ch]
0x18000fb95  movups  xmm0, xmmword ptr [rax]
0x18000fb98  movups  xmm1, xmmword ptr [rax+10h]
0x18000fb9c  movups  xmmword ptr [rsi], xmm0
0x18000fb9f  movups  xmm0, xmmword ptr [rax+20h]
0x18000fba3  movups  xmmword ptr [rsi+10h], xmm1
0x18000fba7  movups  xmm1, xmmword ptr [rax+30h]
0x18000fbab  movups  xmmword ptr [rsi+20h], xmm0
0x18000fbaf  movups  xmm0, xmmword ptr [rax+40h]
0x18000fbb3  movups  xmmword ptr [rsi+30h], xmm1
0x18000fbb7  movups  xmm1, xmmword ptr [rax+50h]
0x18000fbbb  movups  xmmword ptr [rsi+40h], xmm0
0x18000fbbf  movups  xmm0, xmmword ptr [rax+60h]
0x18000fbc3  movups  xmmword ptr [rsi+50h], xmm1
0x18000fbc7  movups  xmm1, xmmword ptr [rax+70h]
0x18000fbcb  add     rax, rdx
0x18000fbce  movups  xmmword ptr [rsi+60h], xmm0
0x18000fbd2  movups  xmmword ptr [rsi+70h], xmm1
0x18000fbd6  add     rsi, rdx
0x18000fbd9  sub     rcx, 1
0x18000fbdd  jnz     short loc_18000FB95
0x18000fbdf  movups  xmm0, xmmword ptr [rax]
0x18000fbe2  movups  xmmword ptr [rsi], xmm0
0x18000fbe5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fbec  cmp     rcx, rdi
0x18000fbef  jz      short loc_18000FC18
0x18000fbf1  test    dword ptr [rcx+1Ch], 800h
0x18000fbf8  jz      short loc_18000FC18
0x18000fbfa  cmp     byte ptr [rcx+19h], 6
0x18000fbfe  jb      short loc_18000FC18
0x18000fc00  mov     edx, 2CEh
0x18000fc05  mov     rcx, [rcx+10h]
0x18000fc09  lea     r8, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids
0x18000fc10  xor     r9d, r9d
0x18000fc13  call    WPP_SF_d
0x18000fc18  xor     eax, eax
0x18000fc1a  jmp     loc_18000FA0B
0x18000fc1f  lea     rdx, [rsp+320h+var_2A4]
0x18000fc24  lea     rcx, [rbp+220h+var_270]; phkResult
0x18000fc28  call    DwOpenUsersRegistry
0x18000fc2d  mov     ebx, eax
0x18000fc2f  test    eax, eax
0x18000fc31  jz      short loc_18000FC64
0x18000fc33  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fc3a  cmp     rcx, rdi
0x18000fc3d  jz      loc_18000F90A
0x18000fc43  test    dword ptr [rcx+1Ch], 800h
0x18000fc4a  jz      loc_18000F90A
0x18000fc50  cmp     byte ptr [rcx+19h], 2
0x18000fc54  jb      loc_18000F90A
0x18000fc5a  mov     edx, 2CFh
0x18000fc5f  jmp     loc_18000F8F0
0x18000fc64  mov     rcx, [rbp+220h+var_270]; hKey
0x18000fc68  lea     rax, [rbp+220h+hKey]
0x18000fc6c  mov     r9d, 2001Dh; samDesired
0x18000fc72  mov     [rsp+320h+phkResult], rax; phkResult
0x18000fc77  xor     r8d, r8d; ulOptions
0x18000fc7a  lea     rdx, aSoftwareMicros_3; "Software\\Microsoft\\RAS AutoDial"
0x18000fc81  call    cs:__imp_RegOpenKeyExW
0x18000fc87  mov     ebx, eax
0x18000fc89  test    eax, eax
0x18000fc8b  jz      short loc_18000FCBE
0x18000fc8d  mov     rcx, cs:WPP_GLOBAL_Control
  ... truncated ...
```
