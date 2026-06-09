# ReadSettingsFromRegistry(ushort const *,REGKEYINFORMATION const *,int,void *,ulong,int,void *,ushort const *)

- ea: `0x18063ac50`
- end: `0x18063b702`
- name: `?ReadSettingsFromRegistry@@YAJPEBGPEBUREGKEYINFORMATION@@HPEAXKH20@Z`
- size: `2738`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const struct REGKEYINFORMATION *, int, void *, unsigned int, int, void *, LPCWSTR lpSubKey)`
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800086cc`
- `0x180774440`

## callees

- `0x1801100c4`
- `0x1801bf344`
- `0x1802e23bc`
- `0x1802e3acc`
- `0x18030035c`
- `0x18063ac50`
- `0x18063b708`
- `0x18063b8a8`
- `0x18070c988`
- `0x18073d830`
- `0x1810c2d60`
- `0x1810cd6c0`

## import_xrefs

- `api-ms-win-downlevel-advapi32-l1-1-0!RegQueryValueExW` at `0x18063ae66`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegQueryValueExW` at `0x18063aebf`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegQueryValueExW` at `0x18063af15`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegQueryValueExW` at `0x18063b0f6`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegQueryValueExW` at `0x18063b136`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegQueryValueExW` at `0x18063b1d5`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegQueryValueExW` at `0x18063b237`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegQueryValueExW` at `0x18063b274`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegQueryValueExW` at `0x18063b36c`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegQueryValueExW` at `0x18063b3d3`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegQueryValueExW` at `0x18063b41f`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegQueryValueExW` at `0x18063b492`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegQueryValueExW` at `0x18063b542`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegQueryValueExW` at `0x18063b599`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegQueryValueExW` at `0x18063b5f7`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegQueryValueExW` at `0x18063b655`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegQueryValueExW` at `0x18063b6a4`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegQueryValueExW` at `0x18063ae66`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegQueryValueExW` at `0x18063aebf`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegQueryValueExW` at `0x18063af15`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegQueryValueExW` at `0x18063b0f6`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegQueryValueExW` at `0x18063b136`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegQueryValueExW` at `0x18063b1d5`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegQueryValueExW` at `0x18063b237`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegQueryValueExW` at `0x18063b274`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegQueryValueExW` at `0x18063b36c`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegQueryValueExW` at `0x18063b3d3`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegQueryValueExW` at `0x18063b41f`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegQueryValueExW` at `0x18063b492`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegQueryValueExW` at `0x18063b542`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegQueryValueExW` at `0x18063b599`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegQueryValueExW` at `0x18063b5f7`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegQueryValueExW` at `0x18063b655`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegQueryValueExW` at `0x18063b6a4`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegOpenKeyExW` at `0x18063ad2d`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegOpenKeyExW` at `0x18063ad5d`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegOpenKeyExW` at `0x18063ad98`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegOpenKeyExW` at `0x18063b020`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegOpenKeyExW` at `0x18063b048`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegOpenKeyExW` at `0x18063b07b`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegOpenKeyExW` at `0x18063ad2d`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegOpenKeyExW` at `0x18063ad5d`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegOpenKeyExW` at `0x18063ad98`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegOpenKeyExW` at `0x18063b020`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegOpenKeyExW` at `0x18063b048`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegOpenKeyExW` at `0x18063b07b`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x18063af8c`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x18063afa8`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x18063afc4`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x18063b2b3`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x18063b2be`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x18063b2db`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x18063b2eb`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x18063b308`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x18063b318`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x18063af8c`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x18063afa8`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x18063afc4`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x18063b2b3`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x18063b2be`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x18063b2db`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x18063b2eb`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x18063b308`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x18063b318`

## pseudocode

```c
__int64 __fastcall ReadSettingsFromRegistry(
        const unsigned __int16 *a1,
        const struct REGKEYINFORMATION *a2,
        int a3,
        _BYTE *a4,
        char a5,
        int a6,
        _DWORD *a7,
        WCHAR *lpSubKey)
{
  int v8; // r13d
  HKEY v9; // rsi
  LSTATUS v14; // eax
  int v15; // r14d
  __int64 v16; // rbx
  unsigned int v17; // ecx
  unsigned int v18; // ecx
  unsigned int v19; // ecx
  unsigned int v20; // ecx
  unsigned int v21; // ecx
  unsigned int v22; // ecx
  unsigned int v23; // ecx
  const WCHAR *v24; // rdx
  const WCHAR *v25; // rdx
  const WCHAR *v26; // rdx
  WCHAR *v27; // rbx
  LSTATUS v28; // esi
  __int64 v29; // rax
  unsigned int v30; // ecx
  unsigned int v31; // ecx
  unsigned int v32; // ecx
  unsigned int v33; // ecx
  unsigned int v34; // ecx
  unsigned int v35; // ecx
  unsigned int v36; // ecx
  const WCHAR *v37; // rdx
  const WCHAR *v38; // rdx
  const WCHAR *v39; // rdx
  HKEY v40; // rcx
  HKEY v41; // rcx
  __int64 v43; // rax
  __int64 v44; // rax
  const WCHAR *v45; // rdx
  __int16 v46; // dx
  __int16 v47; // cx
  const WCHAR *v48; // rdx
  __int16 v49; // dx
  __int16 v50; // cx
  LSTATUS v51; // eax
  const WCHAR *v52; // rdx
  const WCHAR *v53; // rdx
  char v54; // al
  const WCHAR *v55; // rdx
  const WCHAR *v56; // rdx
  const WCHAR *v57; // rdx
  PHKEY phkResult; // [rsp+20h] [rbp-E0h]
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  DWORD Type; // [rsp+34h] [rbp-CCh] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  HKEY v62; // [rsp+40h] [rbp-C0h] BYREF
  int v63; // [rsp+48h] [rbp-B8h] BYREF
  HKEY v64; // [rsp+50h] [rbp-B0h] BYREF
  HKEY v65; // [rsp+58h] [rbp-A8h] BYREF
  HKEY v66; // [rsp+60h] [rbp-A0h] BYREF
  int v67; // [rsp+68h] [rbp-98h] BYREF
  HKEY v68; // [rsp+70h] [rbp-90h] BYREF
  int IsFeatureEnabledInternal; // [rsp+78h] [rbp-88h]
  _DWORD *v70; // [rsp+80h] [rbp-80h]
  unsigned __int16 Data[2056]; // [rsp+90h] [rbp-70h] BYREF
  WCHAR SubKey[64]; // [rsp+10A0h] [rbp+FA0h] BYREF

  v8 = 0;
  v9 = (HKEY)lpSubKey;
  v70 = a7;
  v68 = 0;
  hKey = 0;
  Type = 0;
  cbData = 0;
  IsFeatureEnabledInternal = CFeatureControlKey::_CoInternetIsFeatureEnabledInternal((CFeatureControlKey *)&FCK::FEATURE_INITIALIZE_SETTINGS_USING_IE_DEFAULTS);
  if ( !a6 )
    goto LABEL_4;
  if ( (a5 & 1) == 0 )
    return 0;
  if ( (a5 & 2) != 0 )
LABEL_4:
    v8 = 1;
  v66 = 0;
  v62 = 0;
  v65 = 0;
  v64 = 0;
  if ( lpSubKey )
  {
    if ( (a5 & 4) == 0 && RegOpenKeyExW(HKEY_CURRENT_USER, lpSubKey, 0, 0x20019u, &v66) )
      v66 = 0;
    v9 = 0;
    if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 1u, &v65) )
      v65 = 0;
  }
  v14 = RegOpenKeyExW((HKEY)(((a5 & 4) != 0) - 0x7FFFFFFFLL), a1, 0, 0x20019u, &v68);
  if ( v68 != v9 && !v14 )
  {
    v15 = (int)v9;
    if ( a3 > 0 )
    {
      while ( 1 )
      {
        v16 = 56LL * v15;
        if ( !v8 && *(_DWORD *)((char *)a2 + v16 + 32) != (_DWORD)v9
          || IsFeatureEnabledInternal != (_DWORD)v9 && *(_DWORD *)((char *)a2 + v16 + 48) == (_DWORD)v9 )
        {
          goto LABEL_89;
        }
        v17 = *((unsigned __int8 *)a2 + v16 + 8);
        if ( v17 > 8 )
          break;
        if ( v17 == 8 )
        {
          v29 = *(_QWORD *)((char *)a2 + v16 + 24);
          cbData = (unsigned int)v9;
          if ( (!v29 || a4[v29] != (_BYTE)v9)
            && !RegQueryValueExW(hKey, *(LPCWSTR *)((char *)a2 + v16), 0, &Type, (LPBYTE)v9, &cbData)
            && cbData <= 0x1000
            && !RegQueryValueExW(hKey, *(LPCWSTR *)((char *)a2 + v16), 0, &Type, (LPBYTE)Data, &cbData)
            && Type == 1 )
          {
            CStr::Set((const unsigned __int16 **)&a4[*(_QWORD *)((char *)a2 + v16 + 16)], Data);
          }
          goto LABEL_89;
        }
        if ( !*((_BYTE *)a2 + v16 + 8) || (v18 = v17 - 1) == 0 )
        {
          if ( *(HKEY *)((char *)a2 + v16) == v9 )
          {
            hKey = v68;
            if ( v66 )
              v62 = v66;
            if ( v65 )
              v64 = v65;
          }
          else
          {
            if ( hKey && hKey != v68 )
            {
              RegCloseKey(hKey);
              hKey = v9;
            }
            if ( v62 && v62 != v66 )
            {
              RegCloseKey(v62);
              v62 = v9;
            }
            if ( v64 && v64 != v65 )
            {
              RegCloseKey(v64);
              v64 = v9;
            }
            if ( *((_BYTE *)a2 + v16 + 8) == 1 )
            {
              LODWORD(phkResult) = *v70;
              Format(0, SubKey, 0x40u, *(const unsigned __int16 **)((char *)a2 + v16), phkResult);
              v27 = SubKey;
            }
            else
            {
              v27 = *(WCHAR **)((char *)a2 + v16);
            }
            v28 = RegOpenKeyExW(v68, v27, 0, 0x20019u, &hKey);
            if ( v66 && RegOpenKeyExW(v66, v27, 0, 0x20019u, &v62) )
              v62 = 0;
            if ( v65 && RegOpenKeyExW(v65, v27, 0, 0x20019u, &v64) )
              v64 = 0;
            if ( v28 )
            {
              do
                ++v15;
              while ( v15 < a3 && *((_BYTE *)a2 + 56 * v15 + 8) >= 2u );
              --v15;
              v9 = 0;
              hKey = 0;
            }
            else
            {
              v9 = 0;
            }
          }
          goto LABEL_89;
        }
        v19 = v18 - 1;
        if ( !v19 )
          goto LABEL_148;
        v20 = v19 - 1;
        if ( !v20 )
          goto LABEL_110;
        v21 = v20 - 1;
        if ( !v21 )
        {
          v26 = *(const WCHAR **)((char *)a2 + v16);
          cbData = 64;
          if ( !RegQueryValueExW(hKey, v26, 0, &Type, (LPBYTE)Data, &cbData) && Type == 1 )
            SetOptionSettingsFont(a4, *(_QWORD *)((char *)a2 + v16 + 16), Data);
          goto LABEL_89;
        }
        v22 = v21 - 1;
        if ( !v22 )
          goto LABEL_125;
        v23 = v22 - 1;
        if ( v23 )
        {
          if ( v23 == 1 )
          {
            v24 = *(const WCHAR **)((char *)a2 + v16);
            cbData = 4;
            if ( !RegQueryValueExW(hKey, v24, 0, &Type, (LPBYTE)Data, &cbData) && Type == 3 )
              a4[*(_QWORD *)((char *)a2 + v16 + 16)] = *(_DWORD *)Data != (_DWORD)v9;
          }
          goto LABEL_89;
        }
        v25 = *(const WCHAR **)((char *)a2 + v16);
        cbData = 4;
        if ( !RegQueryValueExW(hKey, v25, 0, &Type, (LPBYTE)Data, &cbData) && Type == 3 )
          goto LABEL_33;
LABEL_89:
        if ( ++v15 >= a3 )
          goto LABEL_90;
      }
      v30 = v17 - 9;
      if ( !v30 )
        goto LABEL_86;
      v31 = v30 - 1;
      if ( !v31 )
      {
        v57 = *(const WCHAR **)((char *)a2 + v16);
        cbData = 50;
        if ( !RegQueryValueExW(hKey, v57, 0, &Type, (LPBYTE)Data, &cbData) && Type == 1 )
          SetOptionSettingsStrictCSS(a4, *(_QWORD *)((char *)a2 + v16 + 16), Data);
        goto LABEL_89;
      }
      v32 = v31 - 1;
      if ( !v32 )
      {
        v56 = *(const WCHAR **)((char *)a2 + v16);
        cbData = 4;
        if ( RegQueryValueExW(hKey, v56, 0, &Type, (LPBYTE)Data, &cbData) || Type - 3 > 1 )
          goto LABEL_89;
LABEL_33:
        *(_DWORD *)&a4[*(_QWORD *)((char *)a2 + v16 + 16)] = *(_DWORD *)Data;
        goto LABEL_89;
      }
      v33 = v32 - 1;
      if ( !v33 )
      {
        if ( v62 == v9 && v64 == v9 )
          goto LABEL_148;
        v63 = (int)v9;
        GetBOOL((__int64 *)SettingStore::IEVALUE_Browser_Security_HKLM_only[0], &v63);
        v51 = 3;
        v67 = (int)v9;
        if ( v64 )
        {
          v52 = *(const WCHAR **)((char *)a2 + v16);
          cbData = 50;
          v51 = RegQueryValueExW(v64, v52, 0, &Type, (LPBYTE)Data, &cbData);
          if ( !v51 )
            v51 = IERegValueToBoolW(Type, Data, &v67);
        }
        if ( v63 == (_DWORD)v9 )
        {
          if ( v51 )
          {
            if ( v62 )
            {
              v53 = *(const WCHAR **)((char *)a2 + v16);
              cbData = 50;
              if ( !RegQueryValueExW(v62, v53, 0, &Type, (LPBYTE)Data, &cbData) )
              {
                v51 = IERegValueToBoolW(Type, Data, &v67);
                goto LABEL_145;
              }
            }
LABEL_148:
            v55 = *(const WCHAR **)((char *)a2 + v16);
            cbData = 50;
            if ( RegQueryValueExW(hKey, v55, 0, &Type, (LPBYTE)Data, &cbData) )
              goto LABEL_89;
            v63 = (int)v9;
            if ( (unsigned int)IERegValueToBoolW(Type, Data, &v63) )
              goto LABEL_89;
            v54 = v63;
LABEL_147:
            a4[*(_QWORD *)((char *)a2 + v16 + 16)] = v54;
            goto LABEL_89;
          }
        }
        else
        {
LABEL_145:
          if ( v51 )
            goto LABEL_148;
        }
        v54 = v67;
        goto LABEL_147;
      }
      v34 = v33 - 1;
      if ( v34 )
      {
        v35 = v34 - 1;
        if ( !v35 )
        {
          if ( v62 == v9 )
            goto LABEL_110;
          v43 = *(_QWORD *)((char *)a2 + v16 + 24);
          cbData = 50;
          if ( v43 && a4[v43] != (_BYTE)v9 )
            goto LABEL_89;
          if ( RegQueryValueExW(v62, *(LPCWSTR *)((char *)a2 + v16), 0, &Type, (LPBYTE)Data, &cbData) || Type != 1 )
          {
LABEL_110:
            v44 = *(_QWORD *)((char *)a2 + v16 + 24);
            cbData = 50;
            if ( v44 && a4[v44] != (_BYTE)v9
              || RegQueryValueExW(hKey, *(LPCWSTR *)((char *)a2 + v16), 0, &Type, (LPBYTE)Data, &cbData)
              || Type != 1 )
            {
              goto LABEL_89;
            }
          }
          SetOptionSettingsColor(a4, *(_QWORD *)((char *)a2 + v16 + 16), Data);
          goto LABEL_89;
        }
        v36 = v35 - 1;
        if ( v36 )
        {
          if ( v36 == 1 )
          {
            v37 = *(const WCHAR **)((char *)a2 + v16);
            cbData = 4;
            if ( !RegQueryValueExW(hKey, v37, 0, &Type, (LPBYTE)Data, &cbData) && Type - 3 <= 1 )
              *(_WORD *)&a4[*(_QWORD *)((char *)a2 + v16 + 16)] = Data[0];
          }
          goto LABEL_89;
        }
        if ( !v62
          || (v38 = *(const WCHAR **)((char *)a2 + v16),
              cbData = 50,
              RegQueryValueExW(v62, v38, 0, &Type, (LPBYTE)Data, &cbData))
          || Type != 1 )
        {
LABEL_86:
          v39 = *(const WCHAR **)((char *)a2 + v16);
          cbData = 50;
          if ( RegQueryValueExW(hKey, v39, 0, &Type, (LPBYTE)Data, &cbData) || Type != 1 )
            goto LABEL_89;
        }
        SetOptionSettingsAnchorUnderline(a4, *(_QWORD *)((char *)a2 + v16 + 16), Data);
        goto LABEL_89;
      }
      if ( v62 )
      {
        v45 = *(const WCHAR **)((char *)a2 + v16);
        cbData = 50;
        if ( !RegQueryValueExW(v62, v45, 0, &Type, (LPBYTE)Data, &cbData) )
        {
          v46 = 4;
          if ( Type == 3 )
          {
            v47 = LOBYTE(Data[0]);
            goto LABEL_121;
          }
          if ( Type == 4 )
          {
            v47 = Data[0];
LABEL_121:
            if ( v47 < 5 )
            {
              v46 = (__int16)v9;
              if ( (__int16)v9 <= v47 )
                v46 = v47;
            }
            *(_WORD *)&a4[*(_QWORD *)((char *)a2 + v16 + 16)] = v46;
            goto LABEL_89;
          }
        }
      }
LABEL_125:
      v48 = *(const WCHAR **)((char *)a2 + v16);
      cbData = 50;
      if ( !RegQueryValueExW(hKey, v48, 0, &Type, (LPBYTE)Data, &cbData) )
      {
        if ( Type == 3 )
        {
          v49 = LOBYTE(Data[0]);
LABEL_130:
          v50 = (__int16)v9;
          if ( (__int16)v9 <= v49 )
            v50 = v49;
          if ( v50 > 4 )
            v50 = 4;
          *(_WORD *)&a4[*(_QWORD *)((char *)a2 + v16 + 16)] = v50;
          goto LABEL_89;
        }
        if ( Type == 4 )
        {
          v49 = Data[0];
          goto LABEL_130;
        }
      }
      goto LABEL_89;
    }
LABEL_90:
    if ( hKey && hKey != v68 )
      RegCloseKey(hKey);
    RegCloseKey(v68);
    v40 = v65;
    if ( v64 && v64 != v65 )
    {
      RegCloseKey(v64);
      v40 = v65;
    }
    if ( v40 )
      RegCloseKey(v40);
    v41 = v66;
    if ( v62 && v62 != v66 )
    {
      RegCloseKey(v62);
      v41 = v66;
    }
    if ( v41 )
      RegCloseKey(v41);
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x18063ac50  mov     [rsp-8+arg_10], rbx
0x18063ac55  push    rbp
0x18063ac56  push    rsi
0x18063ac57  push    rdi
0x18063ac58  push    r12
0x18063ac5a  push    r13
0x18063ac5c  push    r14
0x18063ac5e  push    r15
0x18063ac60  lea     rbp, [rsp-1030h]
0x18063ac68  mov     eax, 1130h
0x18063ac6d  call    _alloca_probe
0x18063ac72  sub     rsp, rax
0x18063ac75  mov     rax, cs:__security_cookie
0x18063ac7c  xor     rax, rsp
0x18063ac7f  mov     [rbp+1060h+var_40], rax
0x18063ac86  mov     rax, [rbp+1060h+arg_30]
0x18063ac8d  xor     r13d, r13d
0x18063ac90  mov     rsi, [rbp+1060h+lpSubKey]
0x18063ac97  mov     r14, rcx
0x18063ac9a  lea     rcx, ?FEATURE_INITIALIZE_SETTINGS_USING_IE_DEFAULTS@FCK@@3VCFeatureControlKey@@A; this
0x18063aca1  mov     [rbp+1060h+var_10E0], rax
0x18063aca5  mov     [rsp+1160h+var_10F0], r13
0x18063acaa  mov     r15, r9
0x18063acad  mov     [rsp+1160h+hKey], r13
0x18063acb2  mov     r12d, r8d
0x18063acb5  mov     [rsp+1160h+Type], r13d
0x18063acba  mov     rdi, rdx
0x18063acbd  mov     [rsp+1160h+cbData], r13d
0x18063acc2  call    ?_CoInternetIsFeatureEnabledInternal@CFeatureControlKey@@QEAAJXZ; CFeatureControlKey::_CoInternetIsFeatureEnabledInternal(void)
0x18063acc7  mov     ebx, dword ptr [rbp+1060h+arg_20]
0x18063accd  mov     [rsp+1160h+var_10E8], eax
0x18063acd1  cmp     [rbp+1060h+arg_28], r13d
0x18063acd8  jz      short loc_18063ACE8
0x18063acda  test    bl, 1
0x18063acdd  jz      loc_18063B31E
0x18063ace3  test    bl, 2
0x18063ace6  jz      short loc_18063ACEE
0x18063ace8  mov     r13d, 1
0x18063acee  xor     eax, eax
0x18063acf0  mov     [rsp+1160h+var_1100], rax
0x18063acf5  mov     [rsp+1160h+var_1120], rax
0x18063acfa  mov     [rsp+1160h+var_1108], rax
0x18063acff  mov     [rsp+1160h+var_1110], rax
0x18063ad04  lea     ecx, [rax+4]
0x18063ad07  test    rsi, rsi
0x18063ad0a  jz      short loc_18063AD71
0x18063ad0c  test    cl, bl
0x18063ad0e  jnz     short loc_18063AD40
0x18063ad10  lea     rax, [rsp+1160h+var_1100]
0x18063ad15  mov     r9d, 20019h; samDesired
0x18063ad1b  xor     r8d, r8d; ulOptions
0x18063ad1e  mov     [rsp+1160h+phkResult], rax; phkResult
0x18063ad23  mov     rdx, rsi; lpSubKey
0x18063ad26  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18063ad2d  call    cs:__imp_RegOpenKeyExW
0x18063ad33  test    eax, eax
0x18063ad35  jz      short loc_18063AD40
0x18063ad37  mov     [rsp+1160h+var_1100], 0
0x18063ad40  lea     rax, [rsp+1160h+var_1108]
0x18063ad45  mov     r9d, 1; samDesired
0x18063ad4b  xor     r8d, r8d; ulOptions
0x18063ad4e  mov     [rsp+1160h+phkResult], rax; phkResult
0x18063ad53  mov     rdx, rsi; lpSubKey
0x18063ad56  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18063ad5d  call    cs:__imp_RegOpenKeyExW
0x18063ad63  xor     esi, esi
0x18063ad65  lea     ecx, [rsi+4]
0x18063ad68  test    eax, eax
0x18063ad6a  jz      short loc_18063AD71
0x18063ad6c  mov     [rsp+1160h+var_1108], rsi
0x18063ad71  and     bl, cl
0x18063ad73  lea     rax, [rsp+1160h+var_10F0]
0x18063ad78  neg     bl
0x18063ad7a  mov     [rsp+1160h+phkResult], rax; phkResult
0x18063ad7f  mov     r9d, 20019h; samDesired
0x18063ad85  mov     rdx, r14; lpSubKey
0x18063ad88  sbb     rcx, rcx
0x18063ad8b  xor     r8d, r8d; ulOptions
0x18063ad8e  neg     rcx
0x18063ad91  add     rcx, 0FFFFFFFF80000001h; hKey
0x18063ad98  call    cs:__imp_RegOpenKeyExW
0x18063ad9e  cmp     [rsp+1160h+var_10F0], rsi
0x18063ada3  jz      loc_18063B6D3
0x18063ada9  test    eax, eax
0x18063adab  jnz     loc_18063B6D3
0x18063adb1  mov     r14d, esi
0x18063adb4  test    r12d, r12d
0x18063adb7  jle     loc_18063B2A2
0x18063adbd  movsxd  rax, r14d
0x18063adc0  imul    rbx, rax, 38h ; '8'
0x18063adc4  test    r13d, r13d
0x18063adc7  jnz     short loc_18063ADD3
0x18063adc9  cmp     [rbx+rdi+20h], esi
0x18063adcd  jnz     loc_18063B296
0x18063add3  cmp     [rsp+1160h+var_10E8], esi
0x18063add7  jz      short loc_18063ADE3
0x18063add9  cmp     [rbx+rdi+30h], esi
0x18063addd  jz      loc_18063B296
0x18063ade3  movzx   ecx, byte ptr [rbx+rdi+8]
0x18063ade8  cmp     ecx, 8
0x18063adeb  ja      loc_18063B165
0x18063adf1  jz      loc_18063B0BE
0x18063adf7  test    ecx, ecx
0x18063adf9  jz      loc_18063AF44
0x18063adff  sub     ecx, 1
0x18063ae02  jz      loc_18063AF44
0x18063ae08  sub     ecx, 1
0x18063ae0b  jz      loc_18063B5CB
0x18063ae11  sub     ecx, 1
0x18063ae14  jz      loc_18063B393
0x18063ae1a  sub     ecx, 1
0x18063ae1d  jz      loc_18063AEE9
0x18063ae23  sub     ecx, 1
0x18063ae26  jz      loc_18063B466
0x18063ae2c  sub     ecx, 1
0x18063ae2f  jz      short loc_18063AE93
0x18063ae31  cmp     ecx, 1
0x18063ae34  jnz     loc_18063B296
0x18063ae3a  mov     rdx, [rbx+rdi]; lpValueName
0x18063ae3e  lea     rax, [rsp+1160h+cbData]
0x18063ae43  mov     rcx, [rsp+1160h+hKey]; hKey
0x18063ae48  lea     r9, [rsp+1160h+Type]; lpType
0x18063ae4d  mov     [rsp+1160h+lpcbData], rax; lpcbData
0x18063ae52  xor     r8d, r8d; lpReserved
0x18063ae55  lea     rax, [rbp+1060h+Data]
0x18063ae59  mov     [rsp+1160h+cbData], 4
0x18063ae61  mov     [rsp+1160h+phkResult], rax; lpData
0x18063ae66  call    cs:__imp_RegQueryValueExW
0x18063ae6c  test    eax, eax
0x18063ae6e  jnz     loc_18063B296
0x18063ae74  cmp     [rsp+1160h+Type], 3
0x18063ae79  jnz     loc_18063B296
0x18063ae7f  cmp     dword ptr [rbp+1060h+Data], esi
0x18063ae82  mov     rax, [rbx+rdi+10h]
0x18063ae87  setnz   cl
0x18063ae8a  mov     [r15+rax], cl
0x18063ae8e  jmp     loc_18063B296
0x18063ae93  mov     rdx, [rbx+rdi]; lpValueName
0x18063ae97  lea     rax, [rsp+1160h+cbData]
0x18063ae9c  mov     rcx, [rsp+1160h+hKey]; hKey
0x18063aea1  lea     r9, [rsp+1160h+Type]; lpType
0x18063aea6  mov     [rsp+1160h+lpcbData], rax; lpcbData
0x18063aeab  xor     r8d, r8d; lpReserved
0x18063aeae  lea     rax, [rbp+1060h+Data]
0x18063aeb2  mov     [rsp+1160h+cbData], 4
0x18063aeba  mov     [rsp+1160h+phkResult], rax; lpData
0x18063aebf  call    cs:__imp_RegQueryValueExW
0x18063aec5  test    eax, eax
0x18063aec7  jnz     loc_18063B296
0x18063aecd  cmp     [rsp+1160h+Type], 3
0x18063aed2  jnz     loc_18063B296
0x18063aed8  mov     rcx, [rbx+rdi+10h]
0x18063aedd  mov     eax, dword ptr [rbp+1060h+Data]
0x18063aee0  mov     [r15+rcx], eax
0x18063aee4  jmp     loc_18063B296
0x18063aee9  mov     rdx, [rbx+rdi]; lpValueName
0x18063aeed  lea     rax, [rsp+1160h+cbData]
0x18063aef2  mov     rcx, [rsp+1160h+hKey]; hKey
0x18063aef7  lea     r9, [rsp+1160h+Type]; lpType
0x18063aefc  mov     [rsp+1160h+lpcbData], rax; lpcbData
0x18063af01  xor     r8d, r8d; lpReserved
0x18063af04  lea     rax, [rbp+1060h+Data]
0x18063af08  mov     [rsp+1160h+cbData], 40h ; '@'
0x18063af10  mov     [rsp+1160h+phkResult], rax; lpData
0x18063af15  call    cs:__imp_RegQueryValueExW
0x18063af1b  test    eax, eax
0x18063af1d  jnz     loc_18063B296
0x18063af23  cmp     [rsp+1160h+Type], 1
0x18063af28  jnz     loc_18063B296
0x18063af2e  mov     rdx, [rbx+rdi+10h]; unsigned __int64
0x18063af33  lea     r8, [rbp+1060h+Data]; unsigned __int16 *
0x18063af37  mov     rcx, r15; void *
0x18063af3a  call    ?SetOptionSettingsFont@@YAXPEAX_KPEAG@Z; SetOptionSettingsFont(void *,unsigned __int64,ushort *)
0x18063af3f  jmp     loc_18063B296
0x18063af44  cmp     [rbx+rdi], rsi
0x18063af48  jnz     short loc_18063AF7B
0x18063af4a  mov     rcx, [rsp+1160h+var_1100]
0x18063af4f  mov     rax, [rsp+1160h+var_10F0]
0x18063af54  mov     [rsp+1160h+hKey], rax
0x18063af59  test    rcx, rcx
0x18063af5c  jz      short loc_18063AF63
0x18063af5e  mov     [rsp+1160h+var_1120], rcx
0x18063af63  mov     rcx, [rsp+1160h+var_1108]
0x18063af68  test    rcx, rcx
0x18063af6b  jz      loc_18063B296
0x18063af71  mov     [rsp+1160h+var_1110], rcx
0x18063af76  jmp     loc_18063B296
0x18063af7b  mov     rcx, [rsp+1160h+hKey]; hKey
0x18063af80  test    rcx, rcx
0x18063af83  jz      short loc_18063AF97
0x18063af85  cmp     rcx, [rsp+1160h+var_10F0]
0x18063af8a  jz      short loc_18063AF97
0x18063af8c  call    cs:__imp_RegCloseKey
0x18063af92  mov     [rsp+1160h+hKey], rsi
0x18063af97  mov     rcx, [rsp+1160h+var_1120]; hKey
0x18063af9c  test    rcx, rcx
0x18063af9f  jz      short loc_18063AFB3
0x18063afa1  cmp     rcx, [rsp+1160h+var_1100]
0x18063afa6  jz      short loc_18063AFB3
0x18063afa8  call    cs:__imp_RegCloseKey
0x18063afae  mov     [rsp+1160h+var_1120], rsi
0x18063afb3  mov     rcx, [rsp+1160h+var_1110]; hKey
0x18063afb8  test    rcx, rcx
0x18063afbb  jz      short loc_18063AFCF
0x18063afbd  cmp     rcx, [rsp+1160h+var_1108]
0x18063afc2  jz      short loc_18063AFCF
0x18063afc4  call    cs:__imp_RegCloseKey
0x18063afca  mov     [rsp+1160h+var_1110], rsi
0x18063afcf  cmp     byte ptr [rbx+rdi+8], 1
0x18063afd4  jnz     short loc_18063B001
0x18063afd6  mov     rax, [rbp+1060h+var_10E0]
0x18063afda  lea     rdx, [rbp+1060h+SubKey]; unsigned __int16 *
0x18063afe1  mov     r9, [rbx+rdi]; unsigned __int16 *
0x18063afe5  mov     r8d, 40h ; '@'; unsigned __int64
0x18063afeb  xor     ecx, ecx; unsigned int
0x18063afed  mov     eax, [rax]
0x18063afef  mov     dword ptr [rsp+1160h+phkResult], eax
0x18063aff3  call    ?Format@@YAJKPEAG_KPEBGZZ; Format(ulong,ushort *,unsigned __int64,ushort const *,...)
0x18063aff8  lea     rbx, [rbp+1060h+SubKey]
0x18063afff  jmp     short loc_18063B005
0x18063b001  mov     rbx, [rbx+rdi]
0x18063b005  mov     rcx, [rsp+1160h+var_10F0]; hKey
0x18063b00a  lea     rax, [rsp+1160h+hKey]
0x18063b00f  mov     r9d, 20019h; samDesired
0x18063b015  mov     [rsp+1160h+phkResult], rax; phkResult
0x18063b01a  xor     r8d, r8d; ulOptions
0x18063b01d  mov     rdx, rbx; lpSubKey
0x18063b020  call    cs:__imp_RegOpenKeyExW
0x18063b026  mov     rcx, [rsp+1160h+var_1100]; hKey
0x18063b02b  mov     esi, eax
0x18063b02d  test    rcx, rcx
0x18063b030  jz      short loc_18063B05B
0x18063b032  lea     rax, [rsp+1160h+var_1120]
0x18063b037  mov     r9d, 20019h; samDesired
0x18063b03d  xor     r8d, r8d; ulOptions
0x18063b040  mov     [rsp+1160h+phkResult], rax; phkResult
0x18063b045  mov     rdx, rbx; lpSubKey
0x18063b048  call    cs:__imp_RegOpenKeyExW
0x18063b04e  test    eax, eax
0x18063b050  jz      short loc_18063B05B
0x18063b052  mov     [rsp+1160h+var_1120], 0
0x18063b05b  mov     rcx, [rsp+1160h+var_1108]; hKey
0x18063b060  test    rcx, rcx
0x18063b063  jz      short loc_18063B08E
0x18063b065  lea     rax, [rsp+1160h+var_1110]
0x18063b06a  mov     r9d, 20019h; samDesired
0x18063b070  xor     r8d, r8d; ulOptions
0x18063b073  mov     [rsp+1160h+phkResult], rax; phkResult
0x18063b078  mov     rdx, rbx; lpSubKey
0x18063b07b  call    cs:__imp_RegOpenKeyExW
0x18063b081  test    eax, eax
0x18063b083  jz      short loc_18063B08E
0x18063b085  mov     [rsp+1160h+var_1110], 0
0x18063b08e  test    esi, esi
0x18063b090  jnz     short loc_18063B0A7
0x18063b092  xor     esi, esi
0x18063b094  jmp     loc_18063B296
0x18063b099  movsxd  rax, r14d
0x18063b09c  imul    rcx, rax, 38h ; '8'
0x18063b0a0  cmp     byte ptr [rcx+rdi+8], 2
0x18063b0a5  jb      short loc_18063B0AF
0x18063b0a7  inc     r14d
0x18063b0aa  cmp     r14d, r12d
0x18063b0ad  jl      short loc_18063B099
0x18063b0af  dec     r14d
0x18063b0b2  xor     esi, esi
0x18063b0b4  mov     [rsp+1160h+hKey], rsi
0x18063b0b9  jmp     loc_18063B296
0x18063b0be  mov     rax, [rbx+rdi+18h]
0x18063b0c3  mov     [rsp+1160h+cbData], esi
0x18063b0c7  test    rax, rax
0x18063b0ca  jz      short loc_18063B0D6
0x18063b0cc  cmp     [rax+r15], sil
0x18063b0d0  jz      loc_18063B296
0x18063b0d6  mov     rdx, [rbx+rdi]; lpValueName
0x18063b0da  lea     rax, [rsp+1160h+cbData]
0x18063b0df  mov     rcx, [rsp+1160h+hKey]; hKey
0x18063b0e4  lea     r9, [rsp+1160h+Type]; lpType
0x18063b0e9  mov     [rsp+1160h+lpcbData], rax; lpcbData
0x18063b0ee  xor     r8d, r8d; lpReserved
0x18063b0f1  mov     [rsp+1160h+phkResult], rsi; lpData
0x18063b0f6  call    cs:__imp_RegQueryValueExW
0x18063b0fc  test    eax, eax
0x18063b0fe  jnz     loc_18063B296
0x18063b104  cmp     [rsp+1160h+cbData], 1000h
0x18063b10c  ja      loc_18063B296
0x18063b112  mov     rdx, [rbx+rdi]; lpValueName
0x18063b116  lea     rax, [rsp+1160h+cbData]
0x18063b11b  mov     rcx, [rsp+1160h+hKey]; hKey
0x18063b120  lea     r9, [rsp+1160h+Type]; lpType
0x18063b125  mov     [rsp+1160h+lpcbData], rax; lpcbData
0x18063b12a  xor     r8d, r8d; lpReserved
0x18063b12d  lea     rax, [rbp+1060h+Data]
0x18063b131  mov     [rsp+1160h+phkResult], rax; lpData
0x18063b136  call    cs:__imp_RegQueryValueExW
0x18063b13c  test    eax, eax
0x18063b13e  jnz     loc_18063B296
0x18063b144  cmp     [rsp+1160h+Type], 1
0x18063b149  jnz     loc_18063B296
0x18063b14f  mov     rcx, [rbx+rdi+10h]
  ... truncated ...
```
