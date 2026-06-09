# ReadSettingsFromRegistry(ushort const *,REGKEYINFORMATION const *,int,void *,ulong,int,void *,ushort const *)

- ea: `0x180636064`
- end: `0x180636bd7`
- name: `?ReadSettingsFromRegistry@@YAJPEBGPEBUREGKEYINFORMATION@@HPEAXKH20@Z`
- size: `2931`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const struct REGKEYINFORMATION *, int, char *, char, int, _DWORD *, WCHAR *lpSubKey)`
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1803beba8`
- `0x18077f1dc`

## callees

- `0x18005ce98`
- `0x180402d68`
- `0x18040addc`
- `0x18040b6e8`
- `0x18042d198`
- `0x180636064`
- `0x180636be0`
- `0x180636de0`
- `0x180712004`
- `0x180746200`
- `0x1810f65c0`
- `0x181100f20`

## import_xrefs

- `api-ms-win-downlevel-advapi32-l1-1-0!RegQueryValueExW` at `0x18063628c`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegQueryValueExW` at `0x1806362eb`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegQueryValueExW` at `0x180636347`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegQueryValueExW` at `0x180636552`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegQueryValueExW` at `0x180636598`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegQueryValueExW` at `0x18063663d`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegQueryValueExW` at `0x1806366a5`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegQueryValueExW` at `0x1806366e8`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegQueryValueExW` at `0x18063680a`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegQueryValueExW` at `0x180636877`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegQueryValueExW` at `0x1806368c9`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegQueryValueExW` at `0x180636942`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegQueryValueExW` at `0x1806369f8`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegQueryValueExW` at `0x180636a55`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegQueryValueExW` at `0x180636ab9`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegQueryValueExW` at `0x180636b1d`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegQueryValueExW` at `0x180636b72`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegQueryValueExW` at `0x18063628c`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegQueryValueExW` at `0x1806362eb`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegQueryValueExW` at `0x180636347`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegQueryValueExW` at `0x180636552`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegQueryValueExW` at `0x180636598`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegQueryValueExW` at `0x18063663d`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegQueryValueExW` at `0x1806366a5`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegQueryValueExW` at `0x1806366e8`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegQueryValueExW` at `0x18063680a`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegQueryValueExW` at `0x180636877`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegQueryValueExW` at `0x1806368c9`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegQueryValueExW` at `0x180636942`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegQueryValueExW` at `0x1806369f8`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegQueryValueExW` at `0x180636a55`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegQueryValueExW` at `0x180636ab9`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegQueryValueExW` at `0x180636b1d`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegQueryValueExW` at `0x180636b72`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegOpenKeyExW` at `0x180636141`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegOpenKeyExW` at `0x180636177`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegOpenKeyExW` at `0x1806361b8`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegOpenKeyExW` at `0x18063646a`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegOpenKeyExW` at `0x180636498`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegOpenKeyExW` at `0x1806364d1`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegOpenKeyExW` at `0x180636141`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegOpenKeyExW` at `0x180636177`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegOpenKeyExW` at `0x1806361b8`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegOpenKeyExW` at `0x18063646a`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegOpenKeyExW` at `0x180636498`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegOpenKeyExW` at `0x1806364d1`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x1806363c4`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x1806363e6`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x180636408`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x18063672d`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x18063673e`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x180636761`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x180636777`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x18063679a`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x1806367b0`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x1806363c4`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x1806363e6`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x180636408`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x18063672d`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x18063673e`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x180636761`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x180636777`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x18063679a`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x1806367b0`

## pseudocode

```c
__int64 __fastcall ReadSettingsFromRegistry(
        const unsigned __int16 *a1,
        const struct REGKEYINFORMATION *a2,
        int a3,
        char *a4,
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
  int v51; // eax
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
              Format(0, SubKey, 64, *(const unsigned __int16 **)((char *)a2 + v16), phkResult);
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
        GetBOOL((__int64)SettingStore::IEVALUE_Browser_Security_HKLM_only[0], &v63);
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
0x180636064  mov     [rsp-8+arg_10], rbx
0x180636069  push    rbp
0x18063606a  push    rsi
0x18063606b  push    rdi
0x18063606c  push    r12
0x18063606e  push    r13
0x180636070  push    r14
0x180636072  push    r15
0x180636074  lea     rbp, [rsp-1030h]
0x18063607c  mov     eax, 1130h
0x180636081  call    _alloca_probe
0x180636086  sub     rsp, rax
0x180636089  mov     rax, cs:__security_cookie
0x180636090  xor     rax, rsp
0x180636093  mov     [rbp+1060h+var_40], rax
0x18063609a  mov     rax, [rbp+1060h+arg_30]
0x1806360a1  xor     r13d, r13d
0x1806360a4  mov     rsi, [rbp+1060h+lpSubKey]
0x1806360ab  mov     r14, rcx
0x1806360ae  lea     rcx, ?FEATURE_INITIALIZE_SETTINGS_USING_IE_DEFAULTS@FCK@@3VCFeatureControlKey@@A; this
0x1806360b5  mov     [rbp+1060h+var_10E0], rax
0x1806360b9  mov     [rsp+1160h+var_10F0], r13
0x1806360be  mov     r15, r9
0x1806360c1  mov     [rsp+1160h+hKey], r13
0x1806360c6  mov     r12d, r8d
0x1806360c9  mov     [rsp+1160h+Type], r13d
0x1806360ce  mov     rdi, rdx
0x1806360d1  mov     [rsp+1160h+cbData], r13d
0x1806360d6  call    ?_CoInternetIsFeatureEnabledInternal@CFeatureControlKey@@QEAAJXZ; CFeatureControlKey::_CoInternetIsFeatureEnabledInternal(void)
0x1806360db  mov     ebx, dword ptr [rbp+1060h+arg_20]
0x1806360e1  mov     [rsp+1160h+var_10E8], eax
0x1806360e5  cmp     [rbp+1060h+arg_28], r13d
0x1806360ec  jz      short loc_1806360FC
0x1806360ee  test    bl, 1
0x1806360f1  jz      loc_1806367BC
0x1806360f7  test    bl, 2
0x1806360fa  jz      short loc_180636102
0x1806360fc  mov     r13d, 1
0x180636102  xor     eax, eax
0x180636104  mov     [rsp+1160h+var_1100], rax
0x180636109  mov     [rsp+1160h+var_1120], rax
0x18063610e  mov     [rsp+1160h+var_1108], rax
0x180636113  mov     [rsp+1160h+var_1110], rax
0x180636118  lea     ecx, [rax+4]
0x18063611b  test    rsi, rsi
0x18063611e  jz      short loc_180636191
0x180636120  test    cl, bl
0x180636122  jnz     short loc_18063615A
0x180636124  lea     rax, [rsp+1160h+var_1100]
0x180636129  mov     r9d, 20019h; samDesired
0x18063612f  xor     r8d, r8d; ulOptions
0x180636132  mov     [rsp+1160h+phkResult], rax; phkResult
0x180636137  mov     rdx, rsi; lpSubKey
0x18063613a  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180636141  call    cs:__imp_RegOpenKeyExW
0x180636148  nop     dword ptr [rax+rax+00h]
0x18063614d  test    eax, eax
0x18063614f  jz      short loc_18063615A
0x180636151  mov     [rsp+1160h+var_1100], 0
0x18063615a  lea     rax, [rsp+1160h+var_1108]
0x18063615f  mov     r9d, 1; samDesired
0x180636165  xor     r8d, r8d; ulOptions
0x180636168  mov     [rsp+1160h+phkResult], rax; phkResult
0x18063616d  mov     rdx, rsi; lpSubKey
0x180636170  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180636177  call    cs:__imp_RegOpenKeyExW
0x18063617e  nop     dword ptr [rax+rax+00h]
0x180636183  xor     esi, esi
0x180636185  lea     ecx, [rsi+4]
0x180636188  test    eax, eax
0x18063618a  jz      short loc_180636191
0x18063618c  mov     [rsp+1160h+var_1108], rsi
0x180636191  and     bl, cl
0x180636193  lea     rax, [rsp+1160h+var_10F0]
0x180636198  neg     bl
0x18063619a  mov     [rsp+1160h+phkResult], rax; phkResult
0x18063619f  mov     r9d, 20019h; samDesired
0x1806361a5  mov     rdx, r14; lpSubKey
0x1806361a8  sbb     rcx, rcx
0x1806361ab  xor     r8d, r8d; ulOptions
0x1806361ae  neg     rcx
0x1806361b1  add     rcx, 0FFFFFFFF80000001h; hKey
0x1806361b8  call    cs:__imp_RegOpenKeyExW
0x1806361bf  nop     dword ptr [rax+rax+00h]
0x1806361c4  cmp     [rsp+1160h+var_10F0], rsi
0x1806361c9  jz      loc_180636BA7
0x1806361cf  test    eax, eax
0x1806361d1  jnz     loc_180636BA7
0x1806361d7  mov     r14d, esi
0x1806361da  test    r12d, r12d
0x1806361dd  jle     loc_18063671C
0x1806361e3  movsxd  rax, r14d
0x1806361e6  imul    rbx, rax, 38h ; '8'
0x1806361ea  test    r13d, r13d
0x1806361ed  jnz     short loc_1806361F9
0x1806361ef  cmp     [rbx+rdi+20h], esi
0x1806361f3  jnz     loc_180636710
0x1806361f9  cmp     [rsp+1160h+var_10E8], esi
0x1806361fd  jz      short loc_180636209
0x1806361ff  cmp     [rbx+rdi+30h], esi
0x180636203  jz      loc_180636710
0x180636209  movzx   ecx, byte ptr [rbx+rdi+8]
0x18063620e  cmp     ecx, 8
0x180636211  ja      loc_1806365CD
0x180636217  jz      loc_18063651A
0x18063621d  test    ecx, ecx
0x18063621f  jz      loc_18063637C
0x180636225  sub     ecx, 1
0x180636228  jz      loc_18063637C
0x18063622e  sub     ecx, 1
0x180636231  jz      loc_180636A8D
0x180636237  sub     ecx, 1
0x18063623a  jz      loc_180636837
0x180636240  sub     ecx, 1
0x180636243  jz      loc_18063631B
0x180636249  sub     ecx, 1
0x18063624c  jz      loc_180636916
0x180636252  sub     ecx, 1
0x180636255  jz      short loc_1806362BF
0x180636257  cmp     ecx, 1
0x18063625a  jnz     loc_180636710
0x180636260  mov     rdx, [rbx+rdi]; lpValueName
0x180636264  lea     rax, [rsp+1160h+cbData]
0x180636269  mov     rcx, [rsp+1160h+hKey]; hKey
0x18063626e  lea     r9, [rsp+1160h+Type]; lpType
0x180636273  mov     [rsp+1160h+lpcbData], rax; lpcbData
0x180636278  xor     r8d, r8d; lpReserved
0x18063627b  lea     rax, [rbp+1060h+Data]
0x18063627f  mov     [rsp+1160h+cbData], 4
0x180636287  mov     [rsp+1160h+phkResult], rax; lpData
0x18063628c  call    cs:__imp_RegQueryValueExW
0x180636293  nop     dword ptr [rax+rax+00h]
0x180636298  test    eax, eax
0x18063629a  jnz     loc_180636710
0x1806362a0  cmp     [rsp+1160h+Type], 3
0x1806362a5  jnz     loc_180636710
0x1806362ab  cmp     dword ptr [rbp+1060h+Data], esi
0x1806362ae  mov     rax, [rbx+rdi+10h]
0x1806362b3  setnz   cl
0x1806362b6  mov     [r15+rax], cl
0x1806362ba  jmp     loc_180636710
0x1806362bf  mov     rdx, [rbx+rdi]; lpValueName
0x1806362c3  lea     rax, [rsp+1160h+cbData]
0x1806362c8  mov     rcx, [rsp+1160h+hKey]; hKey
0x1806362cd  lea     r9, [rsp+1160h+Type]; lpType
0x1806362d2  mov     [rsp+1160h+lpcbData], rax; lpcbData
0x1806362d7  xor     r8d, r8d; lpReserved
0x1806362da  lea     rax, [rbp+1060h+Data]
0x1806362de  mov     [rsp+1160h+cbData], 4
0x1806362e6  mov     [rsp+1160h+phkResult], rax; lpData
0x1806362eb  call    cs:__imp_RegQueryValueExW
0x1806362f2  nop     dword ptr [rax+rax+00h]
0x1806362f7  test    eax, eax
0x1806362f9  jnz     loc_180636710
0x1806362ff  cmp     [rsp+1160h+Type], 3
0x180636304  jnz     loc_180636710
0x18063630a  mov     rcx, [rbx+rdi+10h]
0x18063630f  mov     eax, dword ptr [rbp+1060h+Data]
0x180636312  mov     [r15+rcx], eax
0x180636316  jmp     loc_180636710
0x18063631b  mov     rdx, [rbx+rdi]; lpValueName
0x18063631f  lea     rax, [rsp+1160h+cbData]
0x180636324  mov     rcx, [rsp+1160h+hKey]; hKey
0x180636329  lea     r9, [rsp+1160h+Type]; lpType
0x18063632e  mov     [rsp+1160h+lpcbData], rax; lpcbData
0x180636333  xor     r8d, r8d; lpReserved
0x180636336  lea     rax, [rbp+1060h+Data]
0x18063633a  mov     [rsp+1160h+cbData], 40h ; '@'
0x180636342  mov     [rsp+1160h+phkResult], rax; lpData
0x180636347  call    cs:__imp_RegQueryValueExW
0x18063634e  nop     dword ptr [rax+rax+00h]
0x180636353  test    eax, eax
0x180636355  jnz     loc_180636710
0x18063635b  cmp     [rsp+1160h+Type], 1
0x180636360  jnz     loc_180636710
0x180636366  mov     rdx, [rbx+rdi+10h]; unsigned __int64
0x18063636b  lea     r8, [rbp+1060h+Data]; unsigned __int16 *
0x18063636f  mov     rcx, r15; void *
0x180636372  call    ?SetOptionSettingsFont@@YAXPEAX_KPEAG@Z; SetOptionSettingsFont(void *,unsigned __int64,ushort *)
0x180636377  jmp     loc_180636710
0x18063637c  cmp     [rbx+rdi], rsi
0x180636380  jnz     short loc_1806363B3
0x180636382  mov     rcx, [rsp+1160h+var_1100]
0x180636387  mov     rax, [rsp+1160h+var_10F0]
0x18063638c  mov     [rsp+1160h+hKey], rax
0x180636391  test    rcx, rcx
0x180636394  jz      short loc_18063639B
0x180636396  mov     [rsp+1160h+var_1120], rcx
0x18063639b  mov     rcx, [rsp+1160h+var_1108]
0x1806363a0  test    rcx, rcx
0x1806363a3  jz      loc_180636710
0x1806363a9  mov     [rsp+1160h+var_1110], rcx
0x1806363ae  jmp     loc_180636710
0x1806363b3  mov     rcx, [rsp+1160h+hKey]; hKey
0x1806363b8  test    rcx, rcx
0x1806363bb  jz      short loc_1806363D5
0x1806363bd  cmp     rcx, [rsp+1160h+var_10F0]
0x1806363c2  jz      short loc_1806363D5
0x1806363c4  call    cs:__imp_RegCloseKey
0x1806363cb  nop     dword ptr [rax+rax+00h]
0x1806363d0  mov     [rsp+1160h+hKey], rsi
0x1806363d5  mov     rcx, [rsp+1160h+var_1120]; hKey
0x1806363da  test    rcx, rcx
0x1806363dd  jz      short loc_1806363F7
0x1806363df  cmp     rcx, [rsp+1160h+var_1100]
0x1806363e4  jz      short loc_1806363F7
0x1806363e6  call    cs:__imp_RegCloseKey
0x1806363ed  nop     dword ptr [rax+rax+00h]
0x1806363f2  mov     [rsp+1160h+var_1120], rsi
0x1806363f7  mov     rcx, [rsp+1160h+var_1110]; hKey
0x1806363fc  test    rcx, rcx
0x1806363ff  jz      short loc_180636419
0x180636401  cmp     rcx, [rsp+1160h+var_1108]
0x180636406  jz      short loc_180636419
0x180636408  call    cs:__imp_RegCloseKey
0x18063640f  nop     dword ptr [rax+rax+00h]
0x180636414  mov     [rsp+1160h+var_1110], rsi
0x180636419  cmp     byte ptr [rbx+rdi+8], 1
0x18063641e  jnz     short loc_18063644B
0x180636420  mov     rax, [rbp+1060h+var_10E0]
0x180636424  lea     rdx, [rbp+1060h+SubKey]; unsigned __int16 *
0x18063642b  mov     r9, [rbx+rdi]; unsigned __int16 *
0x18063642f  mov     r8d, 40h ; '@'; unsigned __int64
0x180636435  xor     ecx, ecx; unsigned int
0x180636437  mov     eax, [rax]
0x180636439  mov     dword ptr [rsp+1160h+phkResult], eax
0x18063643d  call    ?Format@@YAJKPEAG_KPEBGZZ; Format(ulong,ushort *,unsigned __int64,ushort const *,...)
0x180636442  lea     rbx, [rbp+1060h+SubKey]
0x180636449  jmp     short loc_18063644F
0x18063644b  mov     rbx, [rbx+rdi]
0x18063644f  mov     rcx, [rsp+1160h+var_10F0]; hKey
0x180636454  lea     rax, [rsp+1160h+hKey]
0x180636459  mov     r9d, 20019h; samDesired
0x18063645f  mov     [rsp+1160h+phkResult], rax; phkResult
0x180636464  xor     r8d, r8d; ulOptions
0x180636467  mov     rdx, rbx; lpSubKey
0x18063646a  call    cs:__imp_RegOpenKeyExW
0x180636471  nop     dword ptr [rax+rax+00h]
0x180636476  mov     rcx, [rsp+1160h+var_1100]; hKey
0x18063647b  mov     esi, eax
0x18063647d  test    rcx, rcx
0x180636480  jz      short loc_1806364B1
0x180636482  lea     rax, [rsp+1160h+var_1120]
0x180636487  mov     r9d, 20019h; samDesired
0x18063648d  xor     r8d, r8d; ulOptions
0x180636490  mov     [rsp+1160h+phkResult], rax; phkResult
0x180636495  mov     rdx, rbx; lpSubKey
0x180636498  call    cs:__imp_RegOpenKeyExW
0x18063649f  nop     dword ptr [rax+rax+00h]
0x1806364a4  test    eax, eax
0x1806364a6  jz      short loc_1806364B1
0x1806364a8  mov     [rsp+1160h+var_1120], 0
0x1806364b1  mov     rcx, [rsp+1160h+var_1108]; hKey
0x1806364b6  test    rcx, rcx
0x1806364b9  jz      short loc_1806364EA
0x1806364bb  lea     rax, [rsp+1160h+var_1110]
0x1806364c0  mov     r9d, 20019h; samDesired
0x1806364c6  xor     r8d, r8d; ulOptions
0x1806364c9  mov     [rsp+1160h+phkResult], rax; phkResult
0x1806364ce  mov     rdx, rbx; lpSubKey
0x1806364d1  call    cs:__imp_RegOpenKeyExW
0x1806364d8  nop     dword ptr [rax+rax+00h]
0x1806364dd  test    eax, eax
0x1806364df  jz      short loc_1806364EA
0x1806364e1  mov     [rsp+1160h+var_1110], 0
0x1806364ea  test    esi, esi
0x1806364ec  jnz     short loc_180636503
0x1806364ee  xor     esi, esi
0x1806364f0  jmp     loc_180636710
0x1806364f5  movsxd  rax, r14d
0x1806364f8  imul    rcx, rax, 38h ; '8'
0x1806364fc  cmp     byte ptr [rcx+rdi+8], 2
0x180636501  jb      short loc_18063650B
0x180636503  inc     r14d
0x180636506  cmp     r14d, r12d
0x180636509  jl      short loc_1806364F5
0x18063650b  dec     r14d
0x18063650e  xor     esi, esi
0x180636510  mov     [rsp+1160h+hKey], rsi
0x180636515  jmp     loc_180636710
0x18063651a  mov     rax, [rbx+rdi+18h]
0x18063651f  mov     [rsp+1160h+cbData], esi
0x180636523  test    rax, rax
0x180636526  jz      short loc_180636532
0x180636528  cmp     [rax+r15], sil
0x18063652c  jz      loc_180636710
0x180636532  mov     rdx, [rbx+rdi]; lpValueName
0x180636536  lea     rax, [rsp+1160h+cbData]
0x18063653b  mov     rcx, [rsp+1160h+hKey]; hKey
0x180636540  lea     r9, [rsp+1160h+Type]; lpType
0x180636545  mov     [rsp+1160h+lpcbData], rax; lpcbData
0x18063654a  xor     r8d, r8d; lpReserved
0x18063654d  mov     [rsp+1160h+phkResult], rsi; lpData
0x180636552  call    cs:__imp_RegQueryValueExW
0x180636559  nop     dword ptr [rax+rax+00h]
0x18063655e  test    eax, eax
0x180636560  jnz     loc_180636710
0x180636566  cmp     [rsp+1160h+cbData], 1000h
0x18063656e  ja      loc_180636710
0x180636574  mov     rdx, [rbx+rdi]; lpValueName
  ... truncated ...
```
