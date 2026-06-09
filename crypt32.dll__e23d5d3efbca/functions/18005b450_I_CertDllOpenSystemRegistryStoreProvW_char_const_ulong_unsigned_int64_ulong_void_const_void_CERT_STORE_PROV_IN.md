# I_CertDllOpenSystemRegistryStoreProvW(char const *,ulong,unsigned __int64,ulong,void const *,void *,_CERT_STORE_PROV_INFO *)

- ea: `0x18005b450`
- end: `0x18005be7a`
- name: `?I_CertDllOpenSystemRegistryStoreProvW@@YAHPEBDK_KKPEBXPEAXPEAU_CERT_STORE_PROV_INFO@@@Z`
- size: `2602`
- prototype: `__int64 __fastcall(const char *, unsigned int, unsigned __int64, int, void *, HCERTSTORE hCertStore, struct _CERT_STORE_PROV_INFO *)`
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800b77d0`

## callees

- `0x180028d60`
- `0x180031b18`
- `0x1800336b8`
- `0x180043070`
- `0x180059d6c`
- `0x18005a06c`
- `0x18005a2b8`
- `0x18005abb4`
- `0x18005b0b4`
- `0x18005b450`
- `0x18005cfc0`
- `0x18005d484`
- `0x18005d530`
- `0x18005db3c`
- `0x18005de50`
- `0x1800a8b6c`
- `0x1800adb18`
- `0x1800c83b0`
- `0x1800c91fc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b708`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b72e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b762`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b780`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b7a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b708`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b72e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b762`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b780`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b7a0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005b71b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005b741`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005b775`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005b793`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005b7c2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005b934`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005b94f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005ba84`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005bb95`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005b71b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005b741`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005b775`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005b793`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005b7c2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005b934`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005b94f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005ba84`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005bb95`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005b78b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005b7ba`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005b78b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005b7ba`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005b713`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005b739`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005b76d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005b713`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005b739`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005b76d`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18005b574`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18005b5a5`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18005b825`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18005b86c`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18005b8f6`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18005b920`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18005bc8e`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18005bd9b`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18005b574`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18005b5a5`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18005b825`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18005b86c`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18005b8f6`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18005b920`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18005bc8e`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18005bd9b`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18005b499`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18005b50e`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18005b499`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18005b50e`

## pseudocode

```c
__int64 __fastcall I_CertDllOpenSystemRegistryStoreProvW(
        const char *a1,
        unsigned int a2,
        unsigned __int64 a3,
        int a4,
        void *a5,
        HCERTSTORE hCertStore,
        struct _CERT_STORE_PROV_INFO *a7)
{
  int v8; // edi
  int IsAppContainerToken; // r12d
  int v10; // r14d
  __int64 v11; // rcx
  char IsStateSeparationEnabled; // al
  const WCHAR *v13; // r15
  int v14; // r13d
  const WCHAR *v15; // rdi
  int v16; // esi
  unsigned int v17; // edi
  HLOCAL *v18; // r15
  unsigned int v19; // edi
  unsigned int v20; // edi
  int v21; // r12d
  int (*v22)(const struct _CERT_CONTEXT *, void *); // r8
  HKEY v23; // r15
  DWORD dwStoreProvFlags; // edx
  unsigned int v25; // ebx
  __int64 v26; // rax
  unsigned int v27; // esi
  HLOCAL v28; // rdi
  DWORD LastError; // ebx
  __int64 i; // rdi
  WCHAR *v31; // r14
  DWORD v32; // ebx
  HLOCAL v33; // rdi
  DWORD v34; // ebx
  DWORD v35; // ebx
  DWORD v36; // ebx
  int v38; // esi
  unsigned __int16 *RoamingStoreDirectory; // rdi
  int *hStoreProv; // r9
  int v41; // eax
  void (__fastcall **v42)(struct _REG_STORE *, unsigned int); // rcx
  const unsigned __int16 *v43; // rcx
  HKEY v44; // r14
  const unsigned __int16 *v45; // rax
  HKEY v46; // rdi
  unsigned __int16 *v47; // rsi
  int v48; // eax
  DWORD v49; // ecx
  int v50; // eax
  DWORD v51; // ecx
  DWORD v52; // eax
  __int64 v53; // rax
  bool v54; // zf
  int v55; // eax
  __int64 v56; // r8
  __int64 v57; // rax
  WCHAR *v58; // r9
  WCHAR *v59; // rcx
  __int64 v60; // rdx
  HKEY hKey; // [rsp+48h] [rbp-61h] BYREF
  int v62; // [rsp+50h] [rbp-59h]
  HLOCAL v63; // [rsp+58h] [rbp-51h]
  HKEY phkResult; // [rsp+60h] [rbp-49h] BYREF
  PCNZWCH lpString1[2]; // [rsp+68h] [rbp-41h] BYREF
  __int128 v66; // [rsp+78h] [rbp-31h]
  HKEY v67; // [rsp+88h] [rbp-21h]
  HLOCAL hMem[2]; // [rsp+90h] [rbp-19h] BYREF
  __int128 v69; // [rsp+A0h] [rbp-9h] BYREF
  int v72; // [rsp+110h] [rbp+67h]

  v67 = 0;
  *(_OWORD *)lpString1 = 0;
  phkResult = 0;
  v66 = 0;
  v69 = 0;
  *(_OWORD *)hMem = 0;
  if ( !(unsigned __int8)RtlIsStateSeparationEnabled(a1) && (a4 & 0xFF0000) == 0xA0000 )
    a4 = a4 & 0xFF00FFFF | 0x20000;
  if ( (a4 & 0x10000000) != 0 )
  {
    v8 = 1;
    v72 = 1;
    goto LABEL_6;
  }
  v72 = 0;
  v8 = 0;
  if ( (a4 & 0xFF0000) != 0x10000 )
  {
LABEL_6:
    IsAppContainerToken = 0;
    goto LABEL_7;
  }
  IsAppContainerToken = I_CryptIsAppContainerToken(0);
LABEL_7:
  if ( (a4 & 0x20) != 0 )
  {
    if ( a4 < 0 )
    {
      SetLastError(0x80070057);
      return 0;
    }
    a4 &= ~0x20u;
  }
  v10 = 0;
  hKey = 0;
  v63 = 0;
  if ( !(unsigned int)ParseSystemStorePara(a5, a4, 1u, (struct _SYSTEM_NAME_INFO *)lpString1) )
    goto LABEL_76;
  IsStateSeparationEnabled = RtlIsStateSeparationEnabled(v11);
  v13 = lpString1[1];
  if ( IsStateSeparationEnabled
    && CompareStringW(0x409u, 1u, lpString1[1], -1, L"My", -1) == 2
    && (a4 & 0xFF0000) == 0x20000 )
  {
    a4 = a4 & 0xFF00FFFF | 0xA0000;
  }
  if ( (a4 & 0x2C) != 0 )
    goto LABEL_75;
  if ( (a4 & 0x800) != 0 )
    ILS_EnableBackupRestorePrivileges();
  if ( v8 && ((a4 & 0xFF0000) != 0x10000 || (a4 & 0xC0000010) != 0) )
    goto LABEL_75;
  v62 = 0;
  v14 = 0;
  if ( IsAppContainerToken )
  {
    if ( a4 < 0
      || (a4 & 0x10000000) != 0
      || CompareStringW(0x409u, 1u, v13, -1, L"SmartCardRoot", -1) == 2
      || CompareStringW(0x409u, 1u, v13, -1, L"SmartCardRootCtrl", -1) == 2 )
    {
LABEL_75:
      SetLastError(0x80070057);
      goto LABEL_76;
    }
    goto LABEL_18;
  }
  if ( CompareStringW(0x409u, 1u, v13, -1, L"Root", -1) != 2 || (a4 & 0x40000000) != 0 )
  {
    v15 = L"SmartCardRoot";
    if ( CompareStringW(0x409u, 1u, v13, -1, L"SmartCardRoot", -1) == 2 && (a4 & 0x40000000) == 0 )
    {
      v50 = a4 & 0xFF0000;
      if ( (a4 & 0xFF0000) != 0x10000 )
      {
        if ( v50 == 0x20000 )
        {
          if ( a4 >= 0 )
            goto LABEL_108;
        }
        else if ( v50 != 393216 )
        {
          goto LABEL_18;
        }
LABEL_99:
        v49 = -2147024891;
LABEL_100:
        SetLastError(v49);
        v23 = 0;
        goto LABEL_42;
      }
      if ( !v67 )
      {
        v52 = RegOpenHKCUEx(&phkResult);
        if ( v52 )
          goto LABEL_130;
        a4 |= 0x80000000;
        v67 = phkResult;
      }
LABEL_108:
      v14 = 1;
      goto LABEL_18;
    }
    if ( (a4 & 0x40000000) == 0 || CompareStringW(0x409u, 1u, v13, -1, L"SmartCardRootCtrl", -1) != 2 )
      goto LABEL_18;
    if ( v13 )
    {
      v53 = -1;
      do
        ++v53;
      while ( v13[v53] );
    }
    else
    {
      LODWORD(v53) = 0;
    }
    v54 = (_DWORD)v53 == -1;
    v55 = v53 + 1;
    v56 = v55;
    if ( v54 )
    {
      LODWORD(v60) = -2147024809;
      if ( !v55 )
        goto LABEL_167;
    }
    else
    {
      if ( (unsigned __int64)v55 <= 0x7FFFFFFF )
      {
        v57 = 2147483646;
        v58 = (WCHAR *)v13;
        do
        {
          if ( !v57 )
            break;
          if ( !*v15 )
            break;
          *v58++ = *v15++;
          --v57;
          --v56;
        }
        while ( v56 );
        v59 = v58 - 1;
        v60 = v56 == 0 ? 0x8007007A : 0;
        if ( v56 )
          v59 = v58;
        *v59 = 0;
        if ( v56 )
        {
          v14 = 2;
          if ( (a4 & 0xFF0000) == 0x10000 && !(unsigned int)ILS_SetAppContainerUserCertReadSmartCardRootStore(v67, v60) )
            goto LABEL_76;
          goto LABEL_18;
        }
LABEL_167:
        v49 = v60;
        goto LABEL_100;
      }
      LODWORD(v60) = -2147024809;
    }
    *v13 = 0;
    goto LABEL_167;
  }
  v48 = a4 & 0xFF0000;
  if ( (a4 & 0xFF0000) == 0x10000 )
  {
    if ( v67 )
    {
LABEL_122:
      v62 = 1;
      goto LABEL_18;
    }
    v52 = RegOpenHKCUEx(&phkResult);
    if ( !v52 )
    {
      a4 |= 0x80000000;
      v67 = phkResult;
      goto LABEL_122;
    }
LABEL_130:
    v49 = v52;
    goto LABEL_100;
  }
  if ( v48 == 393216 || a4 < 0 && v48 == 0x20000 )
    goto LABEL_99;
LABEL_18:
  v16 = a4 & 0xFF0000;
  if ( (a4 & 0xFF0000) == 0x70000 || v16 == 0x80000 )
  {
    v17 = a4 & 0x80000010;
    if ( (a4 & 0x80000010) == 0 )
    {
      hMem[1] = FormatSystemRegPath((struct _SYSTEM_NAME_INFO *)lpString1, 0, a4, (HKEY *)hMem);
      if ( !hMem[1] )
      {
LABEL_76:
        v23 = 0;
        goto LABEL_42;
      }
      v18 = hMem;
      v19 = -2130706432;
      if ( v16 != 0x80000 )
        v19 = 0x80000000;
      v20 = a4 & 0xFFFD | v19;
      if ( *((_QWORD *)&v66 + 1) )
        v20 |= 0x10000u;
      goto LABEL_25;
    }
  }
  else
  {
    v17 = a4 & 0x80000010;
  }
  if ( v16 == 0x10000 && CompareStringW(0x409u, 1u, v13, -1, L"My", -1) == 2 )
  {
    if ( !v17 )
    {
      v38 = 1;
      v43 = L"Microsoft\\SystemCertificates\\My";
LABEL_81:
      RoamingStoreDirectory = ILS_GetRoamingStoreDirectory(v43, IsAppContainerToken);
      v63 = RoamingStoreDirectory;
      goto LABEL_82;
    }
    v38 = 0;
LABEL_65:
    if ( CompareStringW(0x409u, 1u, v13, -1, L"Request", -1) != 2 || v17 )
    {
      RoamingStoreDirectory = 0;
      goto LABEL_82;
    }
    v10 = 1;
    v43 = L"Microsoft\\SystemCertificates\\Request";
    goto LABEL_81;
  }
  v38 = 0;
  if ( (a4 & 0xFF0000) == 0x10000 )
    goto LABEL_65;
  RoamingStoreDirectory = 0;
LABEL_82:
  if ( IsAppContainerToken && (v38 || v10) )
  {
    v44 = 0;
    if ( !RoamingStoreDirectory )
      goto LABEL_76;
    goto LABEL_110;
  }
  v44 = 0;
  if ( RoamingStoreDirectory )
  {
    if ( !IsAppContainerToken && !v72 )
    {
      hKey = OpenSystemRegPathKey((struct _SYSTEM_NAME_INFO *)lpString1, 0, a4 & 0xFFFF9FFF | 0x4000);
      v44 = hKey;
      if ( v38 )
        ILS_SetAppContainerUserCertReadFileStore(RoamingStoreDirectory);
      goto LABEL_111;
    }
LABEL_110:
    hKey = 0;
LABEL_111:
    *((_QWORD *)&v69 + 1) = RoamingStoreDirectory;
    v18 = (HLOCAL *)&v69;
    *(_QWORD *)&v69 = v44;
    v20 = a4 & 0xDFFD | 0x40000;
    goto LABEL_25;
  }
  if ( v72 )
  {
    v44 = OpenSharedUserSystemRegPathKey((struct _SYSTEM_NAME_INFO *)lpString1, a4);
    hKey = v44;
  }
  else
  {
    hKey = 0;
    v45 = FormatSystemRegPath((struct _SYSTEM_NAME_INFO *)lpString1, 0, a4, &hKey);
    v46 = hKey;
    v47 = (unsigned __int16 *)v45;
    if ( v45 )
      v44 = OpenSubKeyEx(hKey, v45, a4, 0);
    hKey = v44;
    PkiDefaultCryptFree(v47);
    if ( *((_QWORD *)&v66 + 1) && v46 )
      ILS_CloseRegistryKey(v46);
  }
  if ( !v44 )
    goto LABEL_41;
  v18 = (HLOCAL *)v44;
  v20 = a4 & 0xDFFD;
  if ( *((_QWORD *)&v66 + 1) )
    v20 |= 0x10000u;
  if ( BYTE2(a4) < 0xBu && (*(_DWORD *)&byte_180138E30[12 * BYTE2(a4)] & 4) != 0 )
    v20 |= 0x20000u;
LABEL_25:
  v21 = v62;
  if ( (a4 & 0x20000000) != 0 )
  {
    if ( v62 )
    {
      v51 = -2147024809;
    }
    else
    {
      if ( !v14 )
      {
        v20 |= 0x100000u;
        goto LABEL_28;
      }
      v51 = 2;
    }
    SetLastError(v51);
    v23 = hKey;
    goto LABEL_42;
  }
  if ( v62 )
    IPR_InitProtectedRootInfo();
LABEL_28:
  if ( !(unsigned int)I_CertDllOpenRegStoreProv(0, a2, a3, v20, (HKEY)v18, hCertStore, a7) )
  {
LABEL_41:
    v23 = hKey;
    goto LABEL_42;
  }
  if ( v72 )
  {
    *((_DWORD *)a7->hStoreProv + 22) = *((_DWORD *)a7->hStoreProv + 22) & 0xFFFFFFFC | 2;
    a7->dwStoreProvFlags |= 0x44u;
  }
  if ( v21 )
  {
    hStoreProv = (int *)a7->hStoreProv;
    a7->cStoreProvFunc = 0;
    v41 = IPR_DeleteUnprotectedRootsFromStore(hCertStore, hStoreProv + 19, v22, hStoreProv);
    v42 = &off_180123570;
    v23 = hKey;
  }
  else
  {
    v23 = hKey;
    if ( !v14 )
      goto LABEL_33;
    *((_DWORD *)a7->hStoreProv + 20) = v14;
    v41 = 1;
    if ( (v14 & 1) != 0 )
    {
      a7->cStoreProvFunc = 0;
      v41 = IPR_DeleteUnprotectedSmartCardRootsFromStore(hCertStore, v23);
    }
    v42 = &off_1801235E0;
  }
  a7->rgpvStoreProvFunc = (void **)v42;
  a7->cStoreProvFunc = 14;
  if ( v41 )
  {
LABEL_33:
    if ( (a4 & 2) != 0 )
      SetLocalizedNameStoreProperty(hCertStore, (struct _SYSTEM_NAME_INFO *)lpString1);
    a7->dwStoreProvFlags |= 8u;
    dwStoreProvFlags = a7->dwStoreProvFlags;
    v25 = HIWORD(a4);
    if ( (unsigned __int8)v25 >= 0xBu )
    {
      v26 = (unsigned __int8)v25;
    }
    else
    {
      v26 = (unsigned __int8)v25;
      if ( (*(_DWORD *)&byte_180138E30[12 * (unsigned __int8)v25] & 8) != 0 )
      {
        dwStoreProvFlags |= 0x10u;
        a7->dwStoreProvFlags = dwStoreProvFlags;
        goto LABEL_38;
      }
    }
    if ( (unsigned __int8)v25 >= 0xBu )
    {
LABEL_40:
      v27 = 1;
      goto LABEL_43;
    }
LABEL_38:
    if ( (*(_DWORD *)&byte_180138E30[12 * v26] & 0x10) != 0 )
      a7->dwStoreProvFlags = dwStoreProvFlags | 0x20;
    goto LABEL_40;
  }
LABEL_42:
  v27 = 0;
LABEL_43:
  if ( *((_QWORD *)&v66 + 1) && hMem[0] )
    ILS_CloseRegistryKey((HKEY)hMem[0]);
  v28 = hMem[1];
  if ( hMem[1] )
  {
    LastError = GetLastError();
    LocalFree(v28);
    SetLastError(LastError);
  }
  for ( i = 0; i != 4; ++i )
  {
    v31 = (WCHAR *)lpString1[i];
    if ( v31 )
    {
      v32 = GetLastError();
      LocalFree(v31);
      SetLastError(v32);
      lpString1[i] = 0;
    }
  }
  v33 = v63;
  if ( v63 )
  {
    v34 = GetLastError();
    LocalFree(v33);
    SetLastError(v34);
  }
  if ( v23 )
  {
    v35 = GetLastError();
    RegCloseKey(v23);
    SetLastError(v35);
  }
  if ( phkResult )
  {
    v36 = GetLastError();
    if ( phkResult )
    {
      if ( phkResult != HKEY_CURRENT_USER )
        RegCloseKey(phkResult);
    }
    SetLastError(v36);
  }
  return v27;
}

```

## disassembly

```asm
0x18005b450  mov     rax, rsp
0x18005b453  mov     [rax+8], rbx
0x18005b457  mov     [rax+18h], r8
0x18005b45b  mov     [rax+10h], edx
0x18005b45e  push    rbp
0x18005b45f  push    rsi
0x18005b460  push    rdi
0x18005b461  push    r12
0x18005b463  push    r13
0x18005b465  push    r14
0x18005b467  push    r15
0x18005b469  lea     rbp, [rax-47h]
0x18005b46d  sub     rsp, 0B0h
0x18005b474  xorps   xmm0, xmm0
0x18005b477  xor     eax, eax
0x18005b479  xorps   xmm1, xmm1
0x18005b47c  mov     [rbp+3Fh+var_60], rax
0x18005b480  xor     esi, esi
0x18005b482  mov     ebx, r9d
0x18005b485  movups  xmmword ptr [rbp+3Fh+lpString1], xmm0
0x18005b489  mov     [rbp+3Fh+phkResult], rsi
0x18005b48d  movups  [rbp+3Fh+var_70], xmm0
0x18005b491  movups  [rbp+3Fh+var_48], xmm0
0x18005b495  movups  xmmword ptr [rbp+3Fh+hMem], xmm1
0x18005b499  call    cs:__imp_RtlIsStateSeparationEnabled
0x18005b49f  mov     ecx, 0FF0000h
0x18005b4a4  mov     r13d, 0A0000h
0x18005b4aa  test    al, al
0x18005b4ac  jnz     short loc_18005B4BB
0x18005b4ae  mov     eax, ebx
0x18005b4b0  and     eax, ecx
0x18005b4b2  cmp     eax, r13d
0x18005b4b5  jz      loc_18005BA3A
0x18005b4bb  bt      ebx, 1Ch
0x18005b4bf  jb      loc_18005BBE3
0x18005b4c5  mov     eax, ebx
0x18005b4c7  mov     [rbp+3Fh+arg_18], esi
0x18005b4ca  and     eax, ecx
0x18005b4cc  mov     edi, esi
0x18005b4ce  cmp     eax, 10000h
0x18005b4d3  jz      loc_18005B883
0x18005b4d9  mov     r12d, esi
0x18005b4dc  test    bl, 20h
0x18005b4df  jnz     loc_18005B942
0x18005b4e5  mov     rcx, [rbp+3Fh+arg_20]; void *
0x18005b4e9  lea     r9, [rbp+3Fh+lpString1]; struct _SYSTEM_NAME_INFO *
0x18005b4ed  xor     r14d, r14d
0x18005b4f0  mov     [rbp+3Fh+hKey], rsi
0x18005b4f4  mov     edx, ebx; unsigned int
0x18005b4f6  mov     [rbp+3Fh+var_90], r14
0x18005b4fa  lea     esi, [r14+1]
0x18005b4fe  mov     r8d, esi; unsigned int
0x18005b501  call    ?ParseSystemStorePara@@YAHPEBXKKPEAU_SYSTEM_NAME_INFO@@@Z; ParseSystemStorePara(void const *,ulong,ulong,_SYSTEM_NAME_INFO *)
0x18005b506  test    eax, eax
0x18005b508  jz      loc_18005B93A
0x18005b50e  call    cs:__imp_RtlIsStateSeparationEnabled
0x18005b514  mov     r15, [rbp+3Fh+lpString1+8]
0x18005b518  lea     rcx, pvPara; "My"
0x18005b51f  test    al, al
0x18005b521  jnz     loc_18005BD80
0x18005b527  test    bl, 2Ch
0x18005b52a  jnz     loc_18005B92F
0x18005b530  bt      ebx, 0Bh
0x18005b534  jb      loc_18005BDCA
0x18005b53a  test    edi, edi
0x18005b53c  jnz     loc_18005BC3E
0x18005b542  mov     [rbp+3Fh+var_98], r14d
0x18005b546  mov     r13d, r14d
0x18005b549  test    r12d, r12d
0x18005b54c  jnz     loc_18005B8C8
0x18005b552  lea     rax, aRoot_0; "Root"
0x18005b559  mov     [rsp+0E0h+cchCount2], 0FFFFFFFFh; cchCount2
0x18005b561  or      r9d, 0FFFFFFFFh; cchCount1
0x18005b565  mov     [rsp+0E0h+lpString2], rax; lpString2
0x18005b56a  mov     r8, r15; lpString1
0x18005b56d  mov     edx, esi; dwCmpFlags
0x18005b56f  mov     ecx, 409h; Locale
0x18005b574  call    cs:__imp_CompareStringW
0x18005b57a  cmp     eax, 2
0x18005b57d  jz      loc_18005BA49
0x18005b583  lea     rdi, aSmartcardroot; "SmartCardRoot"
0x18005b58a  mov     [rsp+0E0h+cchCount2], 0FFFFFFFFh; cchCount2
0x18005b592  or      r9d, 0FFFFFFFFh; cchCount1
0x18005b596  mov     [rsp+0E0h+lpString2], rdi; lpString2
0x18005b59b  mov     r8, r15; lpString1
0x18005b59e  mov     edx, esi; dwCmpFlags
0x18005b5a0  mov     ecx, 409h; Locale
0x18005b5a5  call    cs:__imp_CompareStringW
0x18005b5ab  cmp     eax, 2
0x18005b5ae  jz      loc_18005BAAD
0x18005b5b4  bt      ebx, 1Eh
0x18005b5b8  jb      loc_18005BC6C
0x18005b5be  mov     esi, ebx
0x18005b5c0  and     esi, 0FF0000h
0x18005b5c6  cmp     esi, 70000h
0x18005b5cc  jnz     loc_18005B7E5
0x18005b5d2  mov     edi, ebx
0x18005b5d4  and     edi, 80000010h
0x18005b5da  jnz     loc_18005B7F9
0x18005b5e0  lea     r9, [rbp+3Fh+hMem]; HKEY *
0x18005b5e4  mov     r8d, ebx; unsigned int
0x18005b5e7  xor     edx, edx; unsigned __int16 *
0x18005b5e9  lea     rcx, [rbp+3Fh+lpString1]; struct _SYSTEM_NAME_INFO *
0x18005b5ed  call    ?FormatSystemRegPath@@YAPEAGPEAU_SYSTEM_NAME_INFO@@PEBGKPEAPEAUHKEY__@@@Z; FormatSystemRegPath(_SYSTEM_NAME_INFO *,ushort const *,ulong,HKEY__ * *)
0x18005b5f2  mov     [rbp+3Fh+hMem+8], rax
0x18005b5f6  test    rax, rax
0x18005b5f9  jz      loc_18005B93A
0x18005b5ff  cmp     esi, 80000h
0x18005b605  lea     r15, [rbp+3Fh+hMem]
0x18005b609  mov     eax, 80000000h
0x18005b60e  mov     edi, 81000000h
0x18005b613  cmovnz  edi, eax
0x18005b616  mov     eax, ebx
0x18005b618  and     eax, 0FFFDh
0x18005b61d  or      edi, eax
0x18005b61f  cmp     qword ptr [rbp+3Fh+var_70+8], r14
0x18005b623  jnz     loc_18005BE02
0x18005b629  mov     r12d, [rbp+3Fh+var_98]
0x18005b62d  bt      ebx, 1Dh
0x18005b631  jb      loc_18005BA92
0x18005b637  test    r12d, r12d
0x18005b63a  jz      short loc_18005B641
0x18005b63c  call    ?IPR_InitProtectedRootInfo@@YAXXZ; IPR_InitProtectedRootInfo(void)
0x18005b641  mov     rsi, [rbp+3Fh+arg_30]
0x18005b645  mov     r9d, edi; unsigned int
0x18005b648  mov     r14, [rbp+3Fh+hCertStore]
0x18005b64c  xor     ecx, ecx; char *
0x18005b64e  mov     r8, [rbp+3Fh+arg_10]; unsigned __int64
0x18005b652  mov     edx, [rbp+3Fh+arg_8]; unsigned int
0x18005b655  mov     [rsp+30h], rsi; struct _CERT_STORE_PROV_INFO *
0x18005b65a  mov     qword ptr [rsp+0E0h+cchCount2], r14; void *
0x18005b65f  mov     [rsp+0E0h+lpString2], r15; HKEY
0x18005b664  call    ?I_CertDllOpenRegStoreProv@@YAHPEBDK_KKPEBXPEAXPEAU_CERT_STORE_PROV_INFO@@@Z; I_CertDllOpenRegStoreProv(char const *,ulong,unsigned __int64,ulong,void const *,void *,_CERT_STORE_PROV_INFO *)
0x18005b669  xor     edi, edi
0x18005b66b  test    eax, eax
0x18005b66d  jz      short loc_18005B6EB
0x18005b66f  cmp     [rbp+3Fh+arg_18], edi
0x18005b672  jnz     loc_18005BB09
0x18005b678  test    r12d, r12d
0x18005b67b  jnz     loc_18005B892
0x18005b681  mov     r15, [rbp+3Fh+hKey]
0x18005b685  test    r13d, r13d
0x18005b688  jnz     loc_18005BB2A
0x18005b68e  test    bl, 2
0x18005b691  jnz     loc_18005BE34
0x18005b697  or      dword ptr [rsi+18h], 8
0x18005b69b  lea     r9, byte_180138E30
0x18005b6a2  mov     edx, [rsi+18h]
0x18005b6a5  xor     r14d, r14d
0x18005b6a8  shr     ebx, 10h
0x18005b6ab  movzx   r8d, bl
0x18005b6af  cmp     r8d, 0Bh
0x18005b6b3  jnb     loc_18005BE50
0x18005b6b9  lea     rax, [r8+r8*2]
0x18005b6bd  mov     ecx, [r9+rax*4]
0x18005b6c1  mov     eax, r8d
0x18005b6c4  test    cl, 8
0x18005b6c7  jnz     loc_18005BE45
0x18005b6cd  cmp     r8d, 0Bh
0x18005b6d1  jnb     short loc_18005B6E4
0x18005b6d3  lea     rax, [rax+rax*2]
0x18005b6d7  mov     ecx, [r9+rax*4]
0x18005b6db  test    cl, 10h
0x18005b6de  jnz     loc_18005BE58
0x18005b6e4  mov     esi, 1
0x18005b6e9  jmp     short loc_18005B6F5
0x18005b6eb  mov     r15, [rbp+3Fh+hKey]
0x18005b6ef  xor     r14d, r14d
0x18005b6f2  mov     esi, r14d
0x18005b6f5  cmp     qword ptr [rbp+3Fh+var_70+8], r14
0x18005b6f9  jnz     loc_18005BE63
0x18005b6ff  mov     rdi, [rbp+3Fh+hMem+8]
0x18005b703  test    rdi, rdi
0x18005b706  jz      short loc_18005B721
0x18005b708  call    cs:__imp_GetLastError
0x18005b70e  mov     rcx, rdi; hMem
0x18005b711  mov     ebx, eax
0x18005b713  call    cs:__imp_LocalFree
0x18005b719  mov     ecx, ebx; dwErrCode
0x18005b71b  call    cs:__imp_SetLastError
0x18005b721  mov     rdi, r14
0x18005b724  mov     r14, [rbp+rdi*8+3Fh+lpString1]
0x18005b729  test    r14, r14
0x18005b72c  jz      short loc_18005B750
0x18005b72e  call    cs:__imp_GetLastError
0x18005b734  mov     rcx, r14; hMem
0x18005b737  mov     ebx, eax
0x18005b739  call    cs:__imp_LocalFree
0x18005b73f  mov     ecx, ebx; dwErrCode
0x18005b741  call    cs:__imp_SetLastError
0x18005b747  mov     [rbp+rdi*8+3Fh+lpString1], 0
0x18005b750  inc     rdi
0x18005b753  cmp     rdi, 4
0x18005b757  jnz     short loc_18005B724
0x18005b759  mov     rdi, [rbp+3Fh+var_90]
0x18005b75d  test    rdi, rdi
0x18005b760  jz      short loc_18005B77B
0x18005b762  call    cs:__imp_GetLastError
0x18005b768  mov     rcx, rdi; hMem
0x18005b76b  mov     ebx, eax
0x18005b76d  call    cs:__imp_LocalFree
0x18005b773  mov     ecx, ebx; dwErrCode
0x18005b775  call    cs:__imp_SetLastError
0x18005b77b  test    r15, r15
0x18005b77e  jz      short loc_18005B799
0x18005b780  call    cs:__imp_GetLastError
0x18005b786  mov     rcx, r15; hKey
0x18005b789  mov     ebx, eax
0x18005b78b  call    cs:__imp_RegCloseKey
0x18005b791  mov     ecx, ebx; dwErrCode
0x18005b793  call    cs:__imp_SetLastError
0x18005b799  cmp     [rbp+3Fh+phkResult], 0
0x18005b79e  jz      short loc_18005B7C8
0x18005b7a0  call    cs:__imp_GetLastError
0x18005b7a6  mov     rcx, [rbp+3Fh+phkResult]; hKey
0x18005b7aa  mov     ebx, eax
0x18005b7ac  test    rcx, rcx
0x18005b7af  jz      short loc_18005B7C0
0x18005b7b1  cmp     rcx, 0FFFFFFFF80000001h
0x18005b7b8  jz      short loc_18005B7C0
0x18005b7ba  call    cs:__imp_RegCloseKey
0x18005b7c0  mov     ecx, ebx; dwErrCode
0x18005b7c2  call    cs:__imp_SetLastError
0x18005b7c8  mov     eax, esi
0x18005b7ca  mov     rbx, [rsp+0E0h+arg_0]
0x18005b7d2  add     rsp, 0B0h
0x18005b7d9  pop     r15
0x18005b7db  pop     r14
0x18005b7dd  pop     r13
0x18005b7df  pop     r12
0x18005b7e1  pop     rdi
0x18005b7e2  pop     rsi
0x18005b7e3  pop     rbp
0x18005b7e4  retn
0x18005b7e5  cmp     esi, 80000h
0x18005b7eb  jz      loc_18005B5D2
0x18005b7f1  mov     edi, ebx
0x18005b7f3  and     edi, 80000010h
0x18005b7f9  cmp     esi, 10000h
0x18005b7ff  jnz     short loc_18005B834
0x18005b801  or      r9d, 0FFFFFFFFh; cchCount1
0x18005b805  mov     [rsp+0E0h+cchCount2], 0FFFFFFFFh; cchCount2
0x18005b80d  lea     rax, pvPara; "My"
0x18005b814  mov     r8, r15; lpString1
0x18005b817  mov     ecx, 409h; Locale
0x18005b81c  mov     [rsp+0E0h+lpString2], rax; lpString2
0x18005b821  lea     edx, [r9+2]; dwCmpFlags
0x18005b825  call    cs:__imp_CompareStringW
0x18005b82b  cmp     eax, 2
0x18005b82e  jz      loc_18005B95C
0x18005b834  mov     eax, ebx
0x18005b836  xor     esi, esi
0x18005b838  and     eax, 0FF0000h
0x18005b83d  cmp     eax, 10000h
0x18005b842  jnz     loc_18005BB22
0x18005b848  or      r9d, 0FFFFFFFFh; cchCount1
0x18005b84c  mov     [rsp+0E0h+cchCount2], 0FFFFFFFFh; cchCount2
0x18005b854  lea     rax, aRequest; "Request"
0x18005b85b  mov     r8, r15; lpString1
0x18005b85e  mov     ecx, 409h; Locale
0x18005b863  mov     [rsp+0E0h+lpString2], rax; lpString2
0x18005b868  lea     edx, [r9+2]; dwCmpFlags
0x18005b86c  call    cs:__imp_CompareStringW
0x18005b872  cmp     eax, 2
0x18005b875  jz      loc_18005BBF0
0x18005b87b  mov     rdi, r14
0x18005b87e  jmp     loc_18005B97D
0x18005b883  xor     ecx, ecx
0x18005b885  call    I_CryptIsAppContainerToken
0x18005b88a  mov     r12d, eax
0x18005b88d  jmp     loc_18005B4DC
0x18005b892  mov     r9, [rsi+10h]; void *
0x18005b896  mov     rcx, r14; hCertStore
0x18005b899  mov     [rsi+4], edi
0x18005b89c  lea     rdx, [r9+4Ch]; int *
0x18005b8a0  call    ?IPR_DeleteUnprotectedRootsFromStore@@YAHPEAXPEAHP6AHPEBU_CERT_CONTEXT@@0@Z0@Z; IPR_DeleteUnprotectedRootsFromStore(void *,int *,int (*)(_CERT_CONTEXT const *,void *),void *)
0x18005b8a5  lea     rcx, off_180123570
0x18005b8ac  mov     r15, [rbp+3Fh+hKey]
0x18005b8b0  mov     [rsi+8], rcx
0x18005b8b4  mov     dword ptr [rsi+4], 0Eh
0x18005b8bb  test    eax, eax
0x18005b8bd  jz      loc_18005B6EF
0x18005b8c3  jmp     loc_18005B68E
0x18005b8c8  test    ebx, ebx
0x18005b8ca  js      short loc_18005B92F
0x18005b8cc  bt      ebx, 1Ch
0x18005b8d0  jb      short loc_18005B92F
0x18005b8d2  lea     rdi, aSmartcardroot; "SmartCardRoot"
0x18005b8d9  mov     [rsp+0E0h+cchCount2], 0FFFFFFFFh; cchCount2
0x18005b8e1  mov     [rsp+0E0h+lpString2], rdi; lpString2
0x18005b8e6  or      r9d, 0FFFFFFFFh; cchCount1
0x18005b8ea  mov     edi, 409h
0x18005b8ef  mov     r8, r15; lpString1
0x18005b8f2  mov     ecx, edi; Locale
0x18005b8f4  mov     edx, esi; dwCmpFlags
0x18005b8f6  call    cs:__imp_CompareStringW
0x18005b8fc  cmp     eax, 2
0x18005b8ff  jz      short loc_18005B92F
0x18005b901  lea     rax, aSmartcardrootc; "SmartCardRootCtrl"
0x18005b908  mov     [rsp+0E0h+cchCount2], 0FFFFFFFFh; cchCount2
  ... truncated ...
```
