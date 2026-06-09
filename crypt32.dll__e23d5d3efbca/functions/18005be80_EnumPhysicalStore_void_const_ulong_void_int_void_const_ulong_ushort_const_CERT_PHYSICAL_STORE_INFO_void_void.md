# EnumPhysicalStore(void const *,ulong,void *,int (*)(void const *,ulong,ushort const *,_CERT_PHYSICAL_STORE_INFO *,void *,void *))

- ea: `0x18005be80`
- end: `0x18005cfb4`
- name: `?EnumPhysicalStore@@YAHPEBXKPEAXP6AH0KPEBGPEAU_CERT_PHYSICAL_STORE_INFO@@11@Z@Z`
- size: `4404`
- prototype: `__int64 __fastcall(unsigned __int16 *, signed int, void *, int (*)(const void *, unsigned int, const unsigned __int16 *, struct _CERT_PHYSICAL_STORE_INFO *, void *, void *))`
- caller_count: `3`
- callee_count: `30`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18005acf0`
- `0x180085aa0`
- `0x1800c9990`

## callees

- `0x1800126d0`
- `0x18001bbec`
- `0x180026220`
- `0x1800286e0`
- `0x180028d60`
- `0x180030e60`
- `0x180031940`
- `0x180031b18`
- `0x180034270`
- `0x180057a8c`
- `0x180058084`
- `0x18005b0b4`
- `0x18005b130`
- `0x18005be80`
- `0x18005cfc0`
- `0x18005d484`
- `0x18005d530`
- `0x18005de50`
- `0x180061270`
- `0x180068c94`
- `0x18008a2c0`
- `0x18009be5c`
- `0x1800a06cc`
- `0x1800ae1f0`
- `0x1800bd034`
- `0x1800bec20`
- `0x1800bf4ea`
- `0x1800c8110`
- `0x1800df8a8`
- `0x18011f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c045`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c527`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c551`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c56f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c591`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c5b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c5d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c87e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c045`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c527`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c551`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c56f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c591`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c5b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c5d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c87e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005c53a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005c564`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005c582`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005c5a4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005c5c6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005c5e8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005c748`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005ce02`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005cf6f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005c53a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005c564`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005c582`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005c5a4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005c5c6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005c5e8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005c748`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005ce02`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005cf6f`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18011921f`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18011921f`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18005cc6b`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18005cc6b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005c0b4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005c532`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005c0b4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005c532`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005c55c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005c57a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005c59c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005c5be`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005c5e0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005c55c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005c57a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005c59c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005c5be`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005c5e0`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18005c0f3`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18005c126`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18005c159`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18005c18c`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18005c1bf`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18005c1f2`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18005c225`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18005c254`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18005c426`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18005c661`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18005c694`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18005c6fc`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18005c7ce`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18005c801`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18005cacc`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18005cb00`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18005cb34`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18005ce53`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180119156`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180119189`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1801191bc`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180119301`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18005c0f3`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18005c126`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18005c159`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18005c18c`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18005c1bf`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18005c1f2`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18005c225`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18005c254`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18005c426`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18005c661`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18005c694`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18005c6fc`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18005c7ce`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18005c801`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18005cacc`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18005cb00`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18005cb34`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18005ce53`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180119156`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180119189`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1801191bc`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180119301`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18005c29e`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18005c29e`

## string_xrefs

- `0x18005c2bd`: `SystemRegistry`
- `0x18005c3f5`: `SystemRegistry`
- `0x18005c960`: `SystemRegistry`
- `0x18005c9ad`: `SystemRegistry`
- `0x18005ca55`: `SystemRegistry`
- `0x18005cb4d`: `SystemRegistry`
- `0x18005cc06`: `SystemRegistry`
- `0x18005cee0`: `SystemRegistry`

## pseudocode

```c
__int64 __fastcall EnumPhysicalStore(
        unsigned __int16 *a1,
        signed int a2,
        void *a3,
        int (*a4)(const void *, unsigned int, const unsigned __int16 *, struct _CERT_PHYSICAL_STORE_INFO *, void *, void *))
{
  __int64 v8; // r15
  struct _ENUM_PHYSICAL_STORE_INFO *v9; // rbx
  _DWORD *v10; // rdi
  HKEY v11; // r12
  _DWORD *Tls; // rax
  unsigned int v13; // edi
  const unsigned __int16 *v14; // rax
  HKEY v15; // rsi
  unsigned __int16 *v16; // r14
  const unsigned __int16 *v17; // rax
  HKEY v18; // rsi
  unsigned __int16 *v19; // r14
  WCHAR *v20; // r14
  __int64 v21; // rcx
  unsigned int v22; // esi
  unsigned __int16 *v23; // r15
  struct _ENUM_PHYSICAL_STORE_INFO *j; // rdi
  __int64 v25; // rax
  int v26; // ebx
  int v27; // eax
  __int64 v28; // r12
  unsigned int v29; // ecx
  __int64 v30; // rax
  const WCHAR *v31; // r8
  unsigned __int16 *v32; // rdi
  int v33; // ecx
  unsigned int v34; // r15d
  DWORD LastError; // edi
  WCHAR *v36; // rsi
  DWORD v37; // edi
  DWORD v38; // edi
  HLOCAL v39; // rsi
  DWORD v40; // edi
  HLOCAL v41; // rsi
  DWORD v42; // edi
  HLOCAL v43; // rsi
  DWORD v44; // edi
  struct _ENUM_PHYSICAL_STORE_INFO *v45; // rcx
  int HasAppContainerUserCertCapability; // r15d
  int v48; // edi
  int v49; // eax
  const unsigned __int16 *v50; // rax
  HKEY v51; // rsi
  unsigned __int16 *v52; // r14
  int v53; // edi
  int IsTestSignRootsAllowed; // eax
  const WCHAR *v55; // rax
  _DWORD *v56; // rax
  __int64 v57; // rcx
  __int64 ProtectedRootFlags; // rax
  unsigned int v59; // ebx
  DWORD v60; // eax
  WCHAR *v61; // r15
  DWORD i; // edi
  LSTATUS v63; // eax
  DWORD v64; // eax
  int v65; // ecx
  int v66; // r14d
  int v67; // eax
  char *v68; // rax
  __int64 v69; // r15
  int v70; // r14d
  unsigned __int16 *UserDsUserCertificateUrl; // rax
  __int64 v72; // rax
  LSTATUS v73; // eax
  struct _ENUM_PHYSICAL_STORE_INFO *EnumPhysicalStoreInfo; // rax
  struct _ENUM_PHYSICAL_STORE_INFO *v75; // rcx
  unsigned int v76; // r8d
  struct _ENUM_PHYSICAL_STORE_INFO *v77; // rdx
  __int64 v78; // rax
  DWORD cSubKeys; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v81; // [rsp+64h] [rbp-9Ch] BYREF
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+70h] [rbp-90h] BYREF
  int v84; // [rsp+74h] [rbp-8Ch]
  int IsAppContainerToken; // [rsp+78h] [rbp-88h]
  int v86; // [rsp+7Ch] [rbp-84h]
  _DWORD *v87; // [rsp+80h] [rbp-80h]
  DWORD cchName; // [rsp+88h] [rbp-78h] BYREF
  int v89; // [rsp+8Ch] [rbp-74h]
  HCRYPTOIDFUNCADDR phFuncAddr; // [rsp+90h] [rbp-70h] BYREF
  HLOCAL ppvFuncAddr; // [rsp+98h] [rbp-68h] BYREF
  PCNZWCH lpString1[2]; // [rsp+A0h] [rbp-60h] BYREF
  HLOCAL hMem[2]; // [rsp+B0h] [rbp-50h]
  __int64 v94; // [rsp+C0h] [rbp-40h]
  unsigned __int16 *v95; // [rsp+C8h] [rbp-38h]
  int v96; // [rsp+D0h] [rbp-30h]
  struct _ENUM_PHYSICAL_STORE_INFO *v97; // [rsp+D8h] [rbp-28h]
  void *v98; // [rsp+E0h] [rbp-20h]
  _QWORD v99[2]; // [rsp+E8h] [rbp-18h] BYREF
  _QWORD v100[2]; // [rsp+F8h] [rbp-8h] BYREF
  char Buffer[16]; // [rsp+108h] [rbp+8h] BYREF
  __int128 v102; // [rsp+118h] [rbp+18h]
  __int128 v103; // [rsp+128h] [rbp+28h]

  v95 = a1;
  v94 = 0;
  phFuncAddr = a4;
  cSubKeys = 0;
  v98 = a3;
  cbMaxSubKeyLen = 0;
  *(_OWORD *)lpString1 = 0;
  *(_OWORD *)hMem = 0;
  if ( BYTE2(a2) >= 0xBu || (v8 = 12LL * BYTE2(a2), (*(_DWORD *)&byte_180138E30[v8] & 1) != 0) )
  {
    ppvFuncAddr = 0;
    phFuncAddr = 0;
    if ( !CryptGetOIDFunctionAddress(qword_180158320, 0, (LPCSTR)BYTE2(a2), 0, &ppvFuncAddr, &phFuncAddr) )
      return 0;
    v59 = ((__int64 (__fastcall *)(unsigned __int16 *, _QWORD, void *, int (*)(const void *, unsigned int, const unsigned __int16 *, struct _CERT_PHYSICAL_STORE_INFO *, void *, void *)))ppvFuncAddr)(
            a1,
            (unsigned int)a2,
            a3,
            a4);
    CryptFreeOIDFunctionAddress(phFuncAddr, 0);
    return v59;
  }
  v9 = 0;
  v97 = 0;
  hKey = 0;
  ppvFuncAddr = 0;
  v10 = 0;
  v11 = 0;
  if ( !(unsigned int)ParseSystemStorePara(a1, a2, 1u, (struct _SYSTEM_NAME_INFO *)lpString1) )
    goto LABEL_105;
  if ( (a2 & 0x273F) != 0 )
    goto LABEL_216;
  v89 = a2 & 0x800;
  if ( (a2 & 0x800) != 0 )
  {
    IPR_EnableSecurityPrivilege(17);
    IPR_EnableSecurityPrivilege(18);
  }
  Tls = (_DWORD *)I_CryptGetTls((unsigned int)dword_1801582C4);
  v87 = Tls;
  v10 = Tls;
  if ( Tls )
  {
    if ( (int)++*Tls <= 20 )
      goto LABEL_9;
    SetLastError(0x8000FFFF);
LABEL_105:
    v20 = (WCHAR *)lpString1[1];
    goto LABEL_106;
  }
  v56 = (_DWORD *)PkiNonzeroAlloc(4u);
  v87 = v56;
  v10 = v56;
  if ( !v56 )
    goto LABEL_105;
  v57 = (unsigned int)dword_1801582C4;
  *v56 = 1;
  I_CryptSetTls(v57, v56);
LABEL_9:
  v86 = a2 & 0xFF0000;
  if ( (a2 & 0xFF0000) == 0x10000 )
  {
    IsAppContainerToken = I_CryptIsAppContainerToken(0);
    if ( !IsAppContainerToken )
    {
      IsAppContainerToken = 0;
      goto LABEL_15;
    }
    if ( a2 >= 0 && (a2 & 0x10000000) == 0 )
    {
      v20 = (WCHAR *)lpString1[1];
      if ( CompareStringW(0x409u, 1u, lpString1[1], -1, L"SmartCardRoot", -1) != 2
        && CompareStringW(0x409u, 1u, v20, -1, L"SmartCardRootCtrl", -1) != 2 )
      {
        cSubKeys = 0;
        HasAppContainerUserCertCapability = I_CryptHasAppContainerUserCertCapability(0);
        if ( (unsigned int)I_CryptHasAppContainerPackageCertificates() )
        {
          v48 = 0;
          LODWORD(v11) = ILS_HasAppContainerExclusiveTrust();
          if ( (_DWORD)v11 )
          {
            v22 = 2;
LABEL_100:
            v49 = CompareStringW(0x409u, 1u, v20, -1, L"Root", -1);
            v21 = (__int64)L"My";
            if ( v49 == 2 )
            {
              if ( !(_DWORD)v11 && HasAppContainerUserCertCapability )
                v22 |= 0x200u;
            }
            else if ( CompareStringW(0x409u, 1u, v20, -1, L"My", -1) == 2 )
            {
              v22 = (HasAppContainerUserCertCapability != 0 ? 4 : 0) | 2;
              if ( v48 )
                v22 = HasAppContainerUserCertCapability != 0 ? 4 : 0;
            }
            else if ( CompareStringW(0x409u, 1u, v20, -1, L"Request", -1) == 2 )
            {
              v22 = 2 * (v48 ^ 1);
            }
            else if ( CompareStringW(0x409u, 1u, v20, -1, L"UserDS", -1) == 2 )
            {
              v22 = 64;
            }
            v11 = 0;
            hKey = 0;
            goto LABEL_37;
          }
        }
        else
        {
          v48 = 1;
        }
        v22 = 36;
        if ( !HasAppContainerUserCertCapability )
          v22 = 32;
        if ( !v48 )
          v22 |= 2u;
        goto LABEL_100;
      }
LABEL_217:
      SetLastError(0x80070057);
      goto LABEL_106;
    }
LABEL_216:
    v20 = (WCHAR *)lpString1[1];
    goto LABEL_217;
  }
  IsAppContainerToken = 0;
  if ( (((a2 & 0xFF0000) - 458752) & 0xFFFEFFFF) == 0 && (a2 & 0x80000010) == 0 )
  {
    cSubKeys = 0;
    goto LABEL_26;
  }
LABEL_15:
  hKey = 0;
  v13 = a2 | 0xC000;
  v14 = FormatSystemRegPath((struct _SYSTEM_NAME_INFO *)lpString1, L"PhysicalStores", a2 | 0xC000u, &hKey);
  v15 = hKey;
  v16 = (unsigned __int16 *)v14;
  if ( v14 )
    v11 = OpenSubKeyEx(hKey, v14, v13, 0);
  hKey = v11;
  PkiDefaultCryptFree(v16);
  if ( hMem[1] && v15 )
    ILS_CloseRegistryKey(v15);
  if ( !v11 )
  {
    if ( GetLastError() == 2 )
    {
      hKey = 0;
      v17 = FormatSystemRegPath((struct _SYSTEM_NAME_INFO *)lpString1, 0, a2, &hKey);
      v18 = hKey;
      v19 = (unsigned __int16 *)v17;
      if ( v17 )
        v11 = OpenSubKeyEx(hKey, v17, a2, 0);
      else
        v11 = 0;
      hKey = v11;
      PkiDefaultCryptFree(v19);
      if ( hMem[1] && v18 )
        ILS_CloseRegistryKey(v18);
      if ( v11 )
        goto LABEL_24;
      if ( (a2 & 0x1000) == 0 )
        goto LABEL_120;
      hKey = 0;
      v50 = FormatSystemRegPath((struct _SYSTEM_NAME_INFO *)lpString1, 0, v13, &hKey);
      v51 = hKey;
      v52 = (unsigned __int16 *)v50;
      if ( v50 )
        v11 = OpenSubKeyEx(hKey, v50, v13, 0);
      else
        v11 = 0;
      hKey = v11;
      PkiDefaultCryptFree(v52);
      if ( hMem[1] && v51 )
        ILS_CloseRegistryKey(v51);
      if ( v11 )
      {
LABEL_24:
        RegCloseKey(v11);
        v11 = 0;
        hKey = 0;
      }
      else
      {
LABEL_120:
        if ( GetLastError() != 2 )
          goto LABEL_121;
      }
      cSubKeys = 0;
      goto LABEL_26;
    }
LABEL_121:
    v20 = (WCHAR *)lpString1[1];
    goto LABEL_122;
  }
  cSubKeys = 0;
  cbMaxSubKeyLen = 0;
  v63 = RegQueryInfoKeyW(v11, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
  if ( v63 )
  {
    SetLastError(v63);
    v64 = 0;
    cSubKeys = 0;
    cbMaxSubKeyLen = 0;
    v65 = 0;
  }
  else
  {
    v64 = cbMaxSubKeyLen;
    v65 = 1;
  }
  if ( v64 )
    cbMaxSubKeyLen = 2 * v64 + 4;
  if ( !v65 )
    goto LABEL_121;
LABEL_26:
  v20 = (WCHAR *)lpString1[1];
  if ( CompareStringW(0x409u, 1u, lpString1[1], -1, L"My", -1) == 2
    || CompareStringW(0x409u, 1u, v20, -1, L"Request", -1) == 2
    || CompareStringW(0x409u, 1u, v20, -1, L"FlightRoot", -1) == 2
    || CompareStringW(0x409u, 1u, v20, -1, L"TestSignRoot", -1) == 2
    || CompareStringW(0x409u, 1u, v20, -1, L"SmartCardRoot", -1) == 2 )
  {
    v22 = 2;
  }
  else
  {
    if ( CompareStringW(0x409u, 1u, v20, -1, L"Root", -1) == 2 )
    {
      switch ( a2 & 0xFF0000 )
      {
        case 65536:
          if ( (GetProtectedRootFlags() & 1) != 0 )
          {
            v22 = 32;
            IPR_InitProtectedRootInfo();
          }
          else
          {
            v22 = 546;
          }
          cSubKeys = 0;
          goto LABEL_37;
        case 131072:
          v53 = ~(unsigned __int8)GetProtectedRootFlags() & 8 | 0x312;
          v22 = v53 | 0x400;
          if ( !(unsigned int)IPR_IsFlightRootsAllowed() )
            v22 = v53;
          IsTestSignRootsAllowed = IPR_IsTestSignRootsAllowed();
          v21 = v22;
          cSubKeys = 0;
          LODWORD(v21) = v22 | 0x800;
          if ( IsTestSignRootsAllowed )
            v22 |= 0x800u;
          goto LABEL_37;
        case 393216:
          v22 = 32;
          cSubKeys = 0;
          goto LABEL_37;
      }
    }
    else if ( CompareStringW(0x409u, 1u, v20, -1, L"TrustedPublisher", -1) == 2
           || CompareStringW(0x409u, 1u, v20, -1, L"Disallowed", -1) == 2 )
    {
      if ( (a2 & 0xFF0000) == 0x10000 )
      {
        v81 = 0;
        I_CryptReadTrustedPublisherDWORDValueFromRegistry(L"AuthenticodeFlags");
        v22 = 48;
        cSubKeys = 0;
        v21 = 50;
        if ( (v81 & 3) == 0 )
          v22 = 50;
        goto LABEL_37;
      }
      if ( (a2 & 0xFF0000) == 0x20000 )
      {
        v81 = 0;
        I_CryptReadTrustedPublisherDWORDValueFromRegistry(L"AuthenticodeFlags");
        cSubKeys = 0;
        v22 = ~(_BYTE)v81 & 2 | 0x110;
        goto LABEL_37;
      }
    }
    else
    {
      if ( CompareStringW(0x409u, 1u, v20, -1, L"TrustedPeople", -1) == 2 )
      {
        v22 = *(_DWORD *)&algn_180138E38[v8];
        if ( (a2 & 0xFF0000) == 0x10000 )
        {
          ProtectedRootFlags = GetProtectedRootFlags();
          cSubKeys = 0;
          v21 = v22 & 0xFFFFFFFD;
          if ( (ProtectedRootFlags & 0x10000) != 0 )
            v22 &= ~2u;
        }
        goto LABEL_37;
      }
      if ( CompareStringW(0x409u, 1u, v20, -1, L"UserDS", -1) == 2 )
      {
        v22 = 64;
        goto LABEL_37;
      }
    }
    v22 = *(_DWORD *)&algn_180138E38[v8];
  }
LABEL_37:
  if ( (unsigned __int8)RtlIsStateSeparationEnabled(v21) )
  {
    if ( (a2 & 0xFF0000) == 0x20000 )
    {
      if ( CompareStringW(0x409u, 1u, v20, -1, L"My", -1) == 2 )
      {
        v22 = 2;
      }
      else if ( CompareStringW(0x409u, 1u, v20, -1, L"AuthRoot", -1) != 2
             && CompareStringW(0x409u, 1u, v20, -1, L"FlightRoot", -1) != 2
             && CompareStringW(0x409u, 1u, v20, -1, L"TestSignRoot", -1) != 2 )
      {
        v22 |= 1u;
      }
    }
    else if ( (a2 & 0xFF0000) == 0xA0000 )
    {
      v22 = 2;
    }
  }
  if ( cSubKeys )
  {
    v60 = cbMaxSubKeyLen;
    if ( cbMaxSubKeyLen )
    {
      ++cbMaxSubKeyLen;
      ppvFuncAddr = (HLOCAL)PkiNonzeroAlloc(2LL * (v60 + 1));
      v61 = (WCHAR *)ppvFuncAddr;
      if ( !ppvFuncAddr )
        goto LABEL_122;
      for ( i = 0; i < cSubKeys; ++i )
      {
        cchName = cbMaxSubKeyLen;
        v73 = RegEnumKeyExW(v11, i, v61, &cchName, 0, 0, 0, 0);
        if ( v73 )
        {
          if ( v73 == 259 )
            break;
        }
        else if ( cchName )
        {
          EnumPhysicalStoreInfo = GetEnumPhysicalStoreInfo(v11, v61, a2);
          v75 = EnumPhysicalStoreInfo;
          if ( EnumPhysicalStoreInfo )
          {
            if ( v9 )
            {
              v76 = *((_DWORD *)EnumPhysicalStoreInfo + 11);
              if ( v76 <= *((_DWORD *)v9 + 11) )
              {
                v77 = v9;
                if ( *((_QWORD *)v9 + 7) )
                {
                  do
                  {
                    v78 = *((_QWORD *)v77 + 7);
                    if ( v76 > *(_DWORD *)(v78 + 44) )
                      break;
                    v77 = (struct _ENUM_PHYSICAL_STORE_INFO *)*((_QWORD *)v77 + 7);
                  }
                  while ( *(_QWORD *)(v78 + 56) );
                }
                *((_QWORD *)v75 + 7) = *((_QWORD *)v77 + 7);
                *((_QWORD *)v77 + 7) = v75;
              }
              else
              {
                *((_QWORD *)EnumPhysicalStoreInfo + 7) = v9;
                v9 = EnumPhysicalStoreInfo;
                v97 = EnumPhysicalStoreInfo;
              }
            }
            else
            {
              v9 = EnumPhysicalStoreInfo;
              v97 = EnumPhysicalStoreInfo;
            }
          }
        }
      }
    }
  }
  v23 = v95;
  for ( j = v9; j; j = (struct _ENUM_PHYSICAL_STORE_INFO *)*((_QWORD *)j + 7) )
  {
    v81 = 0;
    if ( (unsigned int)IsSelfPhysicalStoreInfo(
                         (struct _SYSTEM_NAME_INFO *)lpString1,
                         a2,
                         (struct _CERT_PHYSICAL_STORE_INFO *)j,
                         &v81) )
    {
      PkiDefaultCryptFree(*((HLOCAL *)j + 1));
      if ( (v81 & 2) != 0 )
      {
        Buffer[0] = 35;
        ltoa(12, &Buffer[1], 10);
        v68 = Buffer;
      }
      else
      {
        v68 = "SystemRegistry";
      }
      *((_QWORD *)j + 1) = v68;
      v22 &= ~2u;
      v66 = 1;
    }
    else
    {
      if ( v22 )
      {
        v69 = 0;
        v70 = 1;
        while ( (unsigned int)v69 < 0xC )
        {
          if ( (v70 & v22) != 0 && CompareStringW(0x409u, 1u, *((PCNZWCH *)j + 6), -1, off_180127AF0[v69], -1) == 2 )
          {
            v22 &= ~v70;
            break;
          }
          v69 = (unsigned int)(v69 + 1);
          v70 *= 2;
        }
        v23 = v95;
      }
      v66 = 0;
    }
    if ( (a2 & 0x1000) != 0 )
      *((_DWORD *)j + 5) = *((_DWORD *)j + 5) & 0xFFFF6FFF | 0x1000;
    if ( v89 )
      *((_DWORD *)j + 5) |= 0x800u;
    v67 = ((__int64 (__fastcall *)(unsigned __int16 *, _QWORD, _QWORD, struct _ENUM_PHYSICAL_STORE_INFO *, _QWORD, void *))phFuncAddr)(
            v23,
            a2 & 0xFFFF0000,
            *((_QWORD *)j + 6),
            j,
            0,
            v98);
    if ( v66 )
      *((_QWORD *)j + 1) = 0;
    if ( !v67 )
      goto LABEL_121;
  }
  v20 = (WCHAR *)lpString1[1];
  if ( !v22 )
    goto LABEL_75;
  *(_OWORD *)Buffer = 0;
  v102 = 0;
  v103 = 0;
  if ( hMem[1] )
  {
    v99[0] = 2;
    v99[1] = v100;
    v100[0] = hMem[0];
    v100[1] = lpString1[1];
    v23 = FormatSystemNamePath(1u, (struct _SYSTEM_NAME_GROUP *const)v99);
    if ( !v23 )
      goto LABEL_122;
  }
  else
  {
    if ( a2 < 0 )
      v23 = (unsigned __int16 *)*((_QWORD *)v23 + 1);
    if ( !v23 )
    {
      LODWORD(v25) = 0;
      goto LABEL_50;
    }
  }
  v25 = -1;
  do
    ++v25;
  while ( v23[v25] );
LABEL_50:
  v96 = 2 * v25 + 2;
  v26 = v96;
  *(_OWORD *)Buffer = 0;
  *(_DWORD *)Buffer = 48;
  v27 = 1;
  v102 = 0;
  v84 = 1;
  v28 = 0;
  v103 = 0;
  v29 = 1;
  v81 = 1;
  while ( (v29 & v22) == 0 )
  {
LABEL_71:
    v29 *= 2;
    v28 = (unsigned int)(v28 + 1);
    v81 = v29;
    if ( (unsigned int)v28 >= 0xC )
      goto LABEL_72;
  }
  *(_QWORD *)&Buffer[8] = "System";
  *(_QWORD *)&v103 = v20;
  if ( v20 )
  {
    v30 = -1;
    do
      ++v30;
    while ( v20[v30] );
    v31 = v20;
  }
  else
  {
    LODWORD(v30) = 0;
    v31 = 0;
  }
  v27 = 2 * v30 + 2;
  DWORD2(v103) = 0;
  DWORD2(v102) = v27;
  v32 = 0;
  switch ( (int)v28 )
  {
    case 0:
      v33 = 655360;
      *(_QWORD *)&Buffer[8] = "SystemRegistry";
      goto LABEL_140;
    case 1:
      *(_QWORD *)&Buffer[8] = "SystemRegistry";
      DWORD1(v102) = v86;
      if ( CompareStringW(0x409u, 1u, v31, -1, L"My", -1) != 2 || IsAppContainerToken )
      {
        v33 = DWORD1(v102);
      }
      else
      {
        v33 = DWORD1(v102) | 0x400;
        DWORD1(v102) |= 0x400u;
      }
      *(_QWORD *)&v103 = v23;
      DWORD2(v102) = v26;
      DWORD2(v103) = 1;
      goto LABEL_63;
    case 2:
      v33 = 268533760;
      *(_QWORD *)&Buffer[8] = "SystemRegistry";
      goto LABEL_62;
    case 3:
      DWORD2(v102) = 18;
      *(_QWORD *)&Buffer[8] = "SystemRegistry";
      v55 = L"AuthRoot";
      goto LABEL_139;
    case 4:
      v33 = 491520;
      if ( (a2 & 0xFF0000) == 0x20000 )
        v33 = 557056;
      goto LABEL_62;
    case 5:
      v33 = 163840;
      goto LABEL_62;
    case 6:
      UserDsUserCertificateUrl = GetUserDsUserCertificateUrl();
      v32 = UserDsUserCertificateUrl;
      if ( !UserDsUserCertificateUrl )
      {
        v27 = v84;
LABEL_70:
        v29 = v81;
        goto LABEL_71;
      }
      *(_QWORD *)&v103 = UserDsUserCertificateUrl;
      v33 = 0;
      *(_QWORD *)&Buffer[8] = "Ldap";
      v72 = -1;
      DWORD1(v102) = 0;
      while ( v32[++v72] != 0 )
        ;
      DWORD2(v103) = 1;
      DWORD2(v102) = 2 * v72 + 2;
LABEL_63:
      if ( (a2 & 0x1000) != 0 )
      {
        v33 = v33 & 0xFFFF6FFF | 0x1000;
        DWORD1(v102) = v33;
      }
      if ( v89 )
        DWORD1(v102) = v33 | 0x800;
      v27 = ((__int64 (__fastcall *)(unsigned __int16 *, _QWORD, wchar_t *, char *, _QWORD, void *))phFuncAddr)(
              v95,
              a2 & 0xFFFF0000 | 1,
              off_180127AF0[v28],
              Buffer,
              0,
              v98);
      v84 = v27;
      if ( v32 )
      {
        ICM_Free(v32);
        v27 = v84;
      }
      if ( v27 )
        goto LABEL_70;
LABEL_72:
      v9 = v97;
      if ( hMem[1] )
      {
        PkiDefaultCryptFree(v23);
        v27 = v84;
      }
      v11 = hKey;
      if ( v27 )
      {
LABEL_75:
        v10 = v87;
        v34 = 1;
        goto LABEL_76;
      }
LABEL_122:
      v10 = v87;
LABEL_106:
      v34 = 0;
LABEL_76:
      if ( v10 )
        --*v10;
      if ( v11 )
      {
        LastError = GetLastError();
        RegCloseKey(v11);
        SetLastError(LastError);
      }
      v36 = (WCHAR *)lpString1[0];
      if ( lpString1[0] )
      {
        v37 = GetLastError();
        LocalFree(v36);
        SetLastError(v37);
      }
      if ( v20 )
      {
        v38 = GetLastError();
        LocalFree(v20);
        SetLastError(v38);
      }
      v39 = hMem[0];
      if ( hMem[0] )
      {
        v40 = GetLastError();
        LocalFree(v39);
        SetLastError(v40);
      }
      v41 = hMem[1];
      if ( hMem[1] )
      {
        v42 = GetLastError();
        LocalFree(v41);
        SetLastError(v42);
      }
      v43 = ppvFuncAddr;
      if ( ppvFuncAddr )
      {
        v44 = GetLastError();
        LocalFree(v43);
        SetLastError(v44);
      }
      while ( v9 )
      {
        v45 = v9;
        v9 = (struct _ENUM_PHYSICAL_STORE_INFO *)*((_QWORD *)v9 + 7);
        FreeEnumPhysicalStoreInfo(v45);
      }
      return v34;
    case 7:
      v33 = 557056;
      goto LABEL_62;
    case 8:
      v33 = 622592;
      goto LABEL_62;
    case 9:
      *(_QWORD *)&Buffer[8] = "SystemRegistry";
      if ( IsAppContainerToken )
        v33 = 268533760;
      else
        v33 = v86 | 0x8000;
      DWORD2(v102) = 28;
      *(_QWORD *)&v103 = L"SmartCardRoot";
      goto LABEL_62;
    case 10:
      DWORD2(v102) = 22;
      *(_QWORD *)&Buffer[8] = "SystemRegistry";
      v33 = 163840;
      *(_QWORD *)&v103 = L"FlightRoot";
      goto LABEL_62;
    case 11:
      DWORD2(v102) = 26;
      *(_QWORD *)&Buffer[8] = "SystemRegistry";
      v55 = L"TestSignRoot";
LABEL_139:
      *(_QWORD *)&v103 = v55;
      v33 = 0x20000;
LABEL_140:
      DWORD2(v103) = 1;
LABEL_62:
      DWORD1(v102) = v33;
      goto LABEL_63;
    default:
      goto LABEL_72;
  }
}

```

## disassembly

```asm
0x18005be80  push    rbp
0x18005be82  push    rbx
0x18005be83  push    rsi
0x18005be84  push    rdi
0x18005be85  push    r13
0x18005be87  push    r14
0x18005be89  push    r15
0x18005be8b  lea     rbp, [rsp-50h]
0x18005be90  sub     rsp, 150h
0x18005be97  mov     rax, cs:__security_cookie
0x18005be9e  xor     rax, rsp
0x18005bea1  mov     [rbp+80h+var_48], rax
0x18005bea5  xor     eax, eax
0x18005bea7  mov     [rbp+80h+var_B8], rcx
0x18005beab  xor     r14d, r14d
0x18005beae  mov     [rbp+80h+var_C0], rax
0x18005beb2  xorps   xmm0, xmm0
0x18005beb5  mov     [rbp+80h+phFuncAddr], r9
0x18005beb9  mov     eax, edx
0x18005bebb  mov     [rsp+180h+cSubKeys], r14d
0x18005bec0  shr     eax, 10h
0x18005bec3  mov     rsi, rcx
0x18005bec6  movzx   ecx, al
0x18005bec9  mov     rbx, r8
0x18005becc  mov     [rbp+80h+var_A0], rbx
0x18005bed0  mov     rdi, r9
0x18005bed3  mov     [rsp+180h+cbMaxSubKeyLen], r14d
0x18005bed8  mov     r13d, edx
0x18005bedb  movups  xmmword ptr [rbp+80h+lpString1], xmm0
0x18005bedf  movups  xmmword ptr [rbp+80h+hMem], xmm0
0x18005bee3  cmp     ecx, 0Bh
0x18005bee6  jnb     loc_18005CB62
0x18005beec  lea     rcx, [rcx+rcx*2]
0x18005bef0  lea     r15, ds:0[rcx*4]
0x18005bef8  lea     rax, __ImageBase
0x18005beff  mov     eax, [r15+rax+138E30h]
0x18005bf07  test    al, 1
0x18005bf09  jnz     loc_18005CB62
0x18005bf0f  mov     ebx, r14d
0x18005bf12  mov     [rsp+180h+var_38], r12
0x18005bf1a  lea     r9, [rbp+80h+lpString1]; struct _SYSTEM_NAME_INFO *
0x18005bf1e  mov     [rbp+80h+var_A8], rbx
0x18005bf22  mov     r8d, 1; unsigned int
0x18005bf28  mov     [rsp+180h+hKey], r14
0x18005bf2d  mov     rcx, rsi; void *
0x18005bf30  mov     [rbp+80h+ppvFuncAddr], r14
0x18005bf34  mov     edi, r14d
0x18005bf37  mov     r12d, r14d
0x18005bf3a  call    ?ParseSystemStorePara@@YAHPEBXKKPEAU_SYSTEM_NAME_INFO@@@Z; ParseSystemStorePara(void const *,ulong,ulong,_SYSTEM_NAME_INFO *)
0x18005bf3f  test    eax, eax
0x18005bf41  jz      loc_18005C74E
0x18005bf47  test    r13d, 273Fh
0x18005bf4e  jnz     loc_18005CF66
0x18005bf54  mov     eax, r13d
0x18005bf57  and     eax, 800h
0x18005bf5c  mov     [rbp+80h+var_F4], eax
0x18005bf5f  jnz     loc_18005CD3F
0x18005bf65  mov     ecx, cs:dword_1801582C4
0x18005bf6b  call    I_CryptGetTls
0x18005bf70  mov     [rbp+80h+var_100], rax
0x18005bf74  mov     rdi, rax
0x18005bf77  test    rax, rax
0x18005bf7a  jz      loc_18005CA04
0x18005bf80  inc     dword ptr [rax]
0x18005bf82  cmp     dword ptr [rax], 14h
0x18005bf85  jg      loc_18005C743
0x18005bf8b  mov     esi, 1
0x18005bf90  mov     eax, r13d
0x18005bf93  and     eax, 0FF0000h
0x18005bf98  mov     [rsp+180h+var_104], eax
0x18005bf9c  cmp     eax, 10000h
0x18005bfa1  jz      short loc_18005BFC7
0x18005bfa3  add     eax, 0FFF90000h
0x18005bfa8  mov     [rsp+180h+var_108], r14d
0x18005bfad  test    eax, 0FFFEFFFFh
0x18005bfb2  jnz     short loc_18005BFDE
0x18005bfb4  test    r13d, 80000010h
0x18005bfbb  jnz     short loc_18005BFDE
0x18005bfbd  mov     [rsp+180h+cSubKeys], r14d
0x18005bfc2  jmp     loc_18005C0CB
0x18005bfc7  xor     ecx, ecx
0x18005bfc9  call    I_CryptIsAppContainerToken
0x18005bfce  mov     [rsp+180h+var_108], eax
0x18005bfd2  test    eax, eax
0x18005bfd4  jnz     loc_18005C625
0x18005bfda  mov     [rsp+180h+var_108], eax
0x18005bfde  mov     edi, r13d
0x18005bfe1  mov     [rsp+180h+hKey], r14
0x18005bfe6  or      edi, 0C000h
0x18005bfec  lea     r9, [rsp+180h+hKey]; HKEY *
0x18005bff1  mov     r8d, edi; unsigned int
0x18005bff4  lea     rdx, aPhysicalstores; "PhysicalStores"
0x18005bffb  lea     rcx, [rbp+80h+lpString1]; struct _SYSTEM_NAME_INFO *
0x18005bfff  call    ?FormatSystemRegPath@@YAPEAGPEAU_SYSTEM_NAME_INFO@@PEBGKPEAPEAUHKEY__@@@Z; FormatSystemRegPath(_SYSTEM_NAME_INFO *,ushort const *,ulong,HKEY__ * *)
0x18005c004  mov     rsi, [rsp+180h+hKey]
0x18005c009  mov     r14, rax
0x18005c00c  test    rax, rax
0x18005c00f  jz      short loc_18005C025
0x18005c011  xor     r9d, r9d; unsigned int *
0x18005c014  mov     r8d, edi; unsigned int
0x18005c017  mov     rdx, rax; unsigned __int16 *
0x18005c01a  mov     rcx, rsi; HKEY
0x18005c01d  call    ?OpenSubKeyEx@@YAPEAUHKEY__@@PEAU1@PEBGKPEAK@Z; OpenSubKeyEx(HKEY__ *,ushort const *,ulong,ulong *)
0x18005c022  mov     r12, rax
0x18005c025  mov     [rsp+180h+hKey], r12
0x18005c02a  mov     rcx, r14; hMem
0x18005c02d  call    PkiDefaultCryptFree
0x18005c032  cmp     [rbp+80h+hMem+8], rbx
0x18005c036  jnz     loc_18005CDAE
0x18005c03c  test    r12, r12
0x18005c03f  jnz     loc_18005CC24
0x18005c045  call    cs:__imp_GetLastError
0x18005c04b  cmp     eax, 2
0x18005c04e  jnz     loc_18005C88D
0x18005c054  lea     r9, [rsp+180h+hKey]; HKEY *
0x18005c059  mov     [rsp+180h+hKey], rbx
0x18005c05e  mov     r8d, r13d; unsigned int
0x18005c061  lea     rcx, [rbp+80h+lpString1]; struct _SYSTEM_NAME_INFO *
0x18005c065  xor     edx, edx; unsigned __int16 *
0x18005c067  call    ?FormatSystemRegPath@@YAPEAGPEAU_SYSTEM_NAME_INFO@@PEBGKPEAPEAUHKEY__@@@Z; FormatSystemRegPath(_SYSTEM_NAME_INFO *,ushort const *,ulong,HKEY__ * *)
0x18005c06c  mov     rsi, [rsp+180h+hKey]
0x18005c071  mov     r14, rax
0x18005c074  test    rax, rax
0x18005c077  jz      loc_18005CDC4
0x18005c07d  xor     r9d, r9d; unsigned int *
0x18005c080  mov     r8d, r13d; unsigned int
0x18005c083  mov     rdx, rax; unsigned __int16 *
0x18005c086  mov     rcx, rsi; HKEY
0x18005c089  call    ?OpenSubKeyEx@@YAPEAUHKEY__@@PEAU1@PEBGKPEAK@Z; OpenSubKeyEx(HKEY__ *,ushort const *,ulong,ulong *)
0x18005c08e  mov     r12, rax
0x18005c091  mov     [rsp+180h+hKey], r12
0x18005c096  mov     rcx, r14; hMem
0x18005c099  call    PkiDefaultCryptFree
0x18005c09e  cmp     [rbp+80h+hMem+8], rbx
0x18005c0a2  jnz     loc_18005CDCC
0x18005c0a8  test    r12, r12
0x18005c0ab  jz      loc_18005C81A
0x18005c0b1  mov     rcx, r12; hKey
0x18005c0b4  call    cs:__imp_RegCloseKey
0x18005c0ba  xor     r12d, r12d
0x18005c0bd  mov     [rsp+180h+hKey], r12
0x18005c0c2  mov     [rsp+180h+cSubKeys], ebx
0x18005c0c6  mov     esi, 1
0x18005c0cb  mov     r14, [rbp+80h+lpString1+8]
0x18005c0cf  lea     rdi, pvPara; "My"
0x18005c0d6  mov     r8, r14; lpString1
0x18005c0d9  mov     [rsp+180h+cchCount2], 0FFFFFFFFh; cchCount2
0x18005c0e1  mov     r9d, 0FFFFFFFFh; cchCount1
0x18005c0e7  mov     [rsp+180h+lpString2], rdi; lpString2
0x18005c0ec  mov     edx, esi; dwCmpFlags
0x18005c0ee  mov     ecx, 409h; Locale
0x18005c0f3  call    cs:__imp_CompareStringW
0x18005c0f9  cmp     eax, 2
0x18005c0fc  jz      loc_18005C735
0x18005c102  lea     rax, aRequest; "Request"
0x18005c109  mov     [rsp+180h+cchCount2], 0FFFFFFFFh; cchCount2
0x18005c111  mov     r9d, 0FFFFFFFFh; cchCount1
0x18005c117  mov     [rsp+180h+lpString2], rax; lpString2
0x18005c11c  mov     r8, r14; lpString1
0x18005c11f  mov     edx, esi; dwCmpFlags
0x18005c121  mov     ecx, 409h; Locale
0x18005c126  call    cs:__imp_CompareStringW
0x18005c12c  cmp     eax, 2
0x18005c12f  jz      loc_18005C735
0x18005c135  lea     rax, aFlightroot; "FlightRoot"
0x18005c13c  mov     [rsp+180h+cchCount2], 0FFFFFFFFh; cchCount2
0x18005c144  mov     r9d, 0FFFFFFFFh; cchCount1
0x18005c14a  mov     [rsp+180h+lpString2], rax; lpString2
0x18005c14f  mov     r8, r14; lpString1
0x18005c152  mov     edx, esi; dwCmpFlags
0x18005c154  mov     ecx, 409h; Locale
0x18005c159  call    cs:__imp_CompareStringW
0x18005c15f  cmp     eax, 2
0x18005c162  jz      loc_18005C735
0x18005c168  lea     rax, aTestsignroot; "TestSignRoot"
0x18005c16f  mov     [rsp+180h+cchCount2], 0FFFFFFFFh; cchCount2
0x18005c177  mov     r9d, 0FFFFFFFFh; cchCount1
0x18005c17d  mov     [rsp+180h+lpString2], rax; lpString2
0x18005c182  mov     r8, r14; lpString1
0x18005c185  mov     edx, esi; dwCmpFlags
0x18005c187  mov     ecx, 409h; Locale
0x18005c18c  call    cs:__imp_CompareStringW
0x18005c192  cmp     eax, 2
0x18005c195  jz      loc_18005C735
0x18005c19b  lea     rax, aSmartcardroot; "SmartCardRoot"
0x18005c1a2  mov     [rsp+180h+cchCount2], 0FFFFFFFFh; cchCount2
0x18005c1aa  mov     r9d, 0FFFFFFFFh; cchCount1
0x18005c1b0  mov     [rsp+180h+lpString2], rax; lpString2
0x18005c1b5  mov     r8, r14; lpString1
0x18005c1b8  mov     edx, esi; dwCmpFlags
0x18005c1ba  mov     ecx, 409h; Locale
0x18005c1bf  call    cs:__imp_CompareStringW
0x18005c1c5  cmp     eax, 2
0x18005c1c8  jz      loc_18005C735
0x18005c1ce  lea     rax, aRoot_0; "Root"
0x18005c1d5  mov     [rsp+180h+cchCount2], 0FFFFFFFFh; cchCount2
0x18005c1dd  mov     r9d, 0FFFFFFFFh; cchCount1
0x18005c1e3  mov     [rsp+180h+lpString2], rax; lpString2
0x18005c1e8  mov     r8, r14; lpString1
0x18005c1eb  mov     edx, esi; dwCmpFlags
0x18005c1ed  mov     ecx, 409h; Locale
0x18005c1f2  call    cs:__imp_CompareStringW
0x18005c1f8  cmp     eax, 2
0x18005c1fb  jz      loc_18005C8CF
0x18005c201  lea     rax, aTrustedpublish; "TrustedPublisher"
0x18005c208  mov     [rsp+180h+cchCount2], 0FFFFFFFFh; cchCount2
0x18005c210  mov     r9d, 0FFFFFFFFh; cchCount1
0x18005c216  mov     [rsp+180h+lpString2], rax; lpString2
0x18005c21b  mov     r8, r14; lpString1
0x18005c21e  mov     edx, esi; dwCmpFlags
0x18005c220  mov     ecx, 409h; Locale
0x18005c225  call    cs:__imp_CompareStringW
0x18005c22b  cmp     eax, 2
0x18005c22e  jz      short loc_18005C263
0x18005c230  lea     rax, aDisallowed; "Disallowed"
0x18005c237  mov     [rsp+180h+cchCount2], 0FFFFFFFFh; cchCount2
0x18005c23f  mov     r9d, 0FFFFFFFFh; cchCount1
0x18005c245  mov     [rsp+180h+lpString2], rax; lpString2
0x18005c24a  mov     r8, r14; lpString1
0x18005c24d  mov     edx, esi; dwCmpFlags
0x18005c24f  mov     ecx, 409h; Locale
0x18005c254  call    cs:__imp_CompareStringW
0x18005c25a  cmp     eax, 2
0x18005c25d  jnz     loc_18005C7AA
0x18005c263  mov     eax, r13d
0x18005c266  and     eax, 0FF0000h
0x18005c26b  cmp     eax, 10000h
0x18005c270  jz      loc_18005C76E
0x18005c276  mov     eax, r13d
0x18005c279  and     eax, 0FF0000h
0x18005c27e  cmp     eax, 20000h
0x18005c283  jz      loc_18005C89A
0x18005c289  lea     rax, __ImageBase
0x18005c290  mov     esi, [r15+rax+138E38h]
0x18005c298  mov     r15d, 2
0x18005c29e  call    cs:__imp_RtlIsStateSeparationEnabled
0x18005c2a4  test    al, al
0x18005c2a6  jnz     loc_18005CE1E
0x18005c2ac  cmp     [rsp+180h+cSubKeys], ebx
0x18005c2b0  jnz     loc_18005CBC9
0x18005c2b6  mov     r15, [rbp+80h+var_B8]
0x18005c2ba  mov     rdi, rbx
0x18005c2bd  lea     r14, aSystemregistry; "SystemRegistry"
0x18005c2c4  test    rdi, rdi
0x18005c2c7  jnz     loc_18005CCA0
0x18005c2cd  mov     r14, [rbp+80h+lpString1+8]
0x18005c2d1  test    esi, esi
0x18005c2d3  jz      loc_18005C511
0x18005c2d9  xorps   xmm0, xmm0
0x18005c2dc  movups  xmmword ptr [rbp+80h+Buffer], xmm0
0x18005c2e0  movups  [rbp+80h+var_68], xmm0
0x18005c2e4  movups  [rbp+80h+var_58], xmm0
0x18005c2e8  cmp     [rbp+80h+hMem+8], rdi
0x18005c2ec  jz      short loc_18005C326
0x18005c2ee  lea     rax, [rbp+80h+var_88]
0x18005c2f2  mov     [rbp+80h+var_98], 2
0x18005c2fa  mov     [rbp+80h+var_90], rax
0x18005c2fe  lea     rdx, [rbp+80h+var_98]; struct _SYSTEM_NAME_GROUP *
0x18005c302  mov     rax, [rbp+80h+hMem]
0x18005c306  mov     ecx, 1; unsigned int
0x18005c30b  mov     [rbp+80h+var_88], rax
0x18005c30f  mov     [rbp+80h+var_80], r14
0x18005c313  call    ?FormatSystemNamePath@@YAPEAGKQEAU_SYSTEM_NAME_GROUP@@@Z; FormatSystemNamePath(ulong,_SYSTEM_NAME_GROUP * const)
0x18005c318  mov     r15, rax
0x18005c31b  test    rax, rax
0x18005c31e  jz      loc_18005C891
0x18005c324  jmp     short loc_18005C340
0x18005c326  mov     eax, [rsp+180h+var_104]
0x18005c32a  mov     [rsp+180h+var_104], eax
0x18005c32e  test    r13d, r13d
0x18005c331  js      loc_18005CD36
0x18005c337  test    r15, r15
0x18005c33a  jz      loc_18005CED9
0x18005c340  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18005c347  nop     word ptr [rax+rax+00000000h]
0x18005c350  inc     rax
0x18005c353  cmp     word ptr [r15+rax*2], 0
0x18005c359  jnz     short loc_18005C350
0x18005c35b  mov     edx, 1; dwCmpFlags
0x18005c360  lea     eax, ds:2[rax*2]
0x18005c367  xorps   xmm0, xmm0
0x18005c36a  mov     [rbp+80h+var_B0], eax
0x18005c36d  mov     ebx, [rbp+80h+var_B0]
0x18005c370  lea     r8, aSystem; "System"
0x18005c377  movups  xmmword ptr [rbp+80h+Buffer], xmm0
0x18005c37b  mov     dword ptr [rbp+80h+Buffer], 30h ; '0'
0x18005c382  mov     eax, edx
0x18005c384  movups  [rbp+80h+var_68], xmm0
0x18005c388  mov     [rsp+180h+var_10C], edx
0x18005c38c  xor     r12d, r12d
0x18005c38f  movups  [rbp+80h+var_58], xmm0
0x18005c393  mov     ecx, edx
0x18005c395  mov     [rsp+180h+var_11C], edx
0x18005c399  mov     r9d, 88000h
0x18005c39f  test    esi, ecx
0x18005c3a1  jz      loc_18005C4E2
0x18005c3a7  mov     qword ptr [rbp+80h+Buffer+8], r8
0x18005c3ab  mov     qword ptr [rbp+80h+var_58], r14
0x18005c3af  test    r14, r14
0x18005c3b2  jz      loc_18005CD2C
  ... truncated ...
```
