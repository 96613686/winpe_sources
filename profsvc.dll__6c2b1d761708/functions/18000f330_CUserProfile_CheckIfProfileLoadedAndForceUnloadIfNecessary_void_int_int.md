# CUserProfile::CheckIfProfileLoadedAndForceUnloadIfNecessary(void *,int *,int *)

- ea: `0x18000f330`
- end: `0x1800101fe`
- name: `?CheckIfProfileLoadedAndForceUnloadIfNecessary@CUserProfile@@IEAAJPEAXPEAH1@Z`
- size: `3790`
- prototype: `__int64 __fastcall(CUserProfile *this, void *, int *, int *)`
- caller_count: `1`
- callee_count: `26`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180030744`

## callees

- `0x180005330`
- `0x180007450`
- `0x1800084bc`
- `0x18000b020`
- `0x18000d030`
- `0x18000d2c0`
- `0x18000e1a0`
- `0x18000e200`
- `0x18000f330`
- `0x180010210`
- `0x1800103d4`
- `0x180010524`
- `0x180014c30`
- `0x180015f90`
- `0x180018c0c`
- `0x18001a950`
- `0x180030ad0`
- `0x180031060`
- `0x1800331cc`
- `0x180033650`
- `0x18003672c`
- `0x18003bc70`
- `0x18003c040`
- `0x18003c190`
- `0x1800444a4`
- `0x18005411c`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18001016d`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18001016d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f528`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f8cb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f8f9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f93e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f9b4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f9e2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000fa08`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000fa2e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000faa2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000fac8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000faee`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000fb14`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000fbf2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000fc61`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000fc87`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000fcad`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000fe2f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000fe5d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000fea2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f528`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f8cb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f8f9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f93e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f9b4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f9e2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000fa08`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000fa2e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000faa2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000fac8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000faee`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000fb14`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000fbf2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000fc61`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000fc87`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000fcad`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000fe2f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000fe5d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000fea2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f514`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f8b7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f8e5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f92a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f9a0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f9ce`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f9f4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000fa1a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000fa8e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000fab4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000fada`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000fb00`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000fbde`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000fc4d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000fc73`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000fc99`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000fcff`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000fe1b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000fe49`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000fe8e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f514`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f8b7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f8e5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f92a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f9a0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f9ce`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f9f4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000fa1a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000fa8e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000fab4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000fada`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000fb00`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000fbde`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000fc4d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000fc73`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000fc99`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000fcff`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000fe1b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000fe49`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000fe8e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001019c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800101ca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001019c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800101ca`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000fda6`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000fda6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000f47b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000f7b9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000f47b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000f7b9`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000f82c`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000f82c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000f4c8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000fb76`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000f4c8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000fb76`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f539`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f913`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000fc03`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000fe77`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000fee6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ffa3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f539`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f913`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000fc03`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000fe77`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000fee6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ffa3`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18000fd78`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18000fd78`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000f695`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000f695`
- `ntdll!NtQueryObject` at `0x18000f6d1`
- `ntdll!NtQueryObject` at `0x18000f72c`
- `ntdll!NtQueryObject` at `0x18000f6d1`
- `ntdll!NtQueryObject` at `0x18000f72c`

## string_xrefs

- `0x18000f899`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x18000fc2e`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x18000fccb`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x18000fec6`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x18000ff76`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x18001009e`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x180010133`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x18000f4be`: `ProfileImagePath`
- `0x18000f545`: `ProfileImagePath`
- `0x18000fb6c`: `ProfileImagePath`

## pseudocode

```c
__int64 __fastcall CUserProfile::CheckIfProfileLoadedAndForceUnloadIfNecessary(
        CUserProfile *this,
        void *a2,
        int *a3,
        int *a4)
{
  bool IsUserProfileLoadedByProfileService; // al
  const char *v8; // r9
  int ProfileSidString; // eax
  unsigned int v10; // ebx
  WCHAR *v11; // r12
  int ProfileListKeyNameFromSid; // eax
  unsigned int v13; // ebx
  unsigned __int16 *v14; // r14
  int v15; // eax
  unsigned int v16; // ebx
  WCHAR *v17; // rsi
  LSTATUS v18; // eax
  bool v19; // sf
  HKEY v20; // rbx
  BYTE *v21; // rdi
  LSTATUS v22; // eax
  bool v23; // sf
  HANDLE v24; // rax
  BYTE *v25; // r8
  unsigned __int64 v26; // rbx
  size_t v27; // rbx
  __int64 v28; // rax
  const WCHAR *v29; // rcx
  char *FileW; // r13
  NTSTATUS Object; // eax
  unsigned __int64 v32; // rdx
  const void **v33; // rbx
  unsigned int v34; // eax
  __int64 v35; // rdx
  __int64 v36; // rdx
  BYTE *v37; // rsi
  unsigned __int64 v38; // rdx
  void *v39; // rbx
  HANDLE v40; // rax
  LPWSTR v41; // rbx
  HANDLE v42; // rax
  HKEY v43; // rbx
  HANDLE v44; // rax
  HANDLE v45; // rax
  WCHAR *v46; // rbx
  HANDLE v47; // rax
  HANDLE v48; // rax
  HANDLE v49; // rax
  __int64 result; // rax
  HANDLE v51; // rax
  HANDLE v52; // rax
  HANDLE v53; // rax
  HANDLE v54; // rax
  LSTATUS v55; // eax
  bool v56; // sf
  __int64 v57; // rbx
  HANDLE v58; // rax
  WCHAR *v59; // rdi
  HANDLE ProcessHeap; // rax
  HANDLE v61; // rax
  HANDLE v62; // rax
  DWORD i; // ebx
  HANDLE v64; // rax
  LPWSTR v65; // rbx
  HANDLE v66; // rax
  HKEY v67; // rbx
  HANDLE v68; // rax
  unsigned int v69; // ebx
  unsigned __int64 v70; // rdx
  unsigned __int64 v71; // rdx
  __int64 v72; // r13
  char *v73; // rsi
  size_t v74; // rbx
  unsigned __int64 v75; // rdx
  int phkResult; // [rsp+20h] [rbp-178h]
  int phkResulta; // [rsp+20h] [rbp-178h]
  unsigned int phkResultb; // [rsp+20h] [rbp-178h]
  DWORD cbData; // [rsp+60h] [rbp-138h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-130h] BYREF
  DWORD Type; // [rsp+70h] [rbp-128h] BYREF
  DWORD cchValueName[2]; // [rsp+78h] [rbp-120h] BYREF
  void *v83; // [rsp+80h] [rbp-118h] BYREF
  LPWSTR lpValueName; // [rsp+88h] [rbp-110h] BYREF
  DWORD cbMaxValueLen; // [rsp+90h] [rbp-108h] BYREF
  HKEY v86; // [rsp+98h] [rbp-100h] BYREF
  DWORD cValues; // [rsp+A0h] [rbp-F8h] BYREF
  LPVOID lpMem; // [rsp+A8h] [rbp-F0h] BYREF
  void *Src; // [rsp+B0h] [rbp-E8h] BYREF
  __int64 v90; // [rsp+B8h] [rbp-E0h]
  __int64 v91; // [rsp+C0h] [rbp-D8h]
  DWORD v92; // [rsp+C8h] [rbp-D0h] BYREF
  LPCWSTR lpSubKey[3]; // [rsp+D0h] [rbp-C8h] BYREF
  LPCWCH lpString1[3]; // [rsp+E8h] [rbp-B0h] BYREF
  unsigned __int16 *v95[3]; // [rsp+100h] [rbp-98h] BYREF
  LPCWSTR lpFileName[2]; // [rsp+118h] [rbp-80h] BYREF
  __int128 v97; // [rsp+128h] [rbp-70h]
  __int128 v98; // [rsp+138h] [rbp-60h] BYREF
  unsigned __int64 v99; // [rsp+148h] [rbp-50h]
  unsigned __int64 v100; // [rsp+150h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+198h] [rbp+0h]

  IsUserProfileLoadedByProfileService = CUserProfile::IsUserProfileLoadedByProfileService(this);
  try
  {
    *a3 = IsUserProfileLoadedByProfileService;
    *a4 = 0;
    if ( *a3 )
      return 0;
    lpString1[0] = 0;
    lpString1[1] = (LPCWCH)-1LL;
    lpString1[2] = (LPCWCH)-1LL;
    ProfileSidString = GetProfileSidString(a2, (unsigned __int16 **)lpString1);
    v10 = ProfileSidString;
    if ( ProfileSidString < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x256,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
        (const char *)(unsigned int)ProfileSidString,
        phkResult);
      Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(lpString1);
      return v10;
    }
    v95[0] = 0;
    v95[1] = (unsigned __int16 *)-1LL;
    v95[2] = (unsigned __int16 *)-1LL;
    v11 = (WCHAR *)lpString1[0];
    ProfileListKeyNameFromSid = GetProfileListKeyNameFromSid(lpString1[0], v95, (int *)cchValueName);
    v13 = ProfileListKeyNameFromSid;
    if ( ProfileListKeyNameFromSid < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x25A,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
        (const char *)(unsigned int)ProfileListKeyNameFromSid,
        phkResult);
      Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(v95);
      Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(lpString1);
      return v13;
    }
    memset(lpSubKey, 0, sizeof(lpSubKey));
    v14 = v95[0];
    v15 = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::InitializeFormat(
            lpSubKey,
            L"%s.bak",
            v95[0]);
    v16 = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x25D,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
        (const char *)(unsigned int)v15,
        phkResult);
      v59 = (WCHAR *)lpSubKey[0];
      if ( lpSubKey[0] )
      {
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v59);
      }
      if ( v14 )
      {
        v61 = GetProcessHeap();
        HeapFree(v61, 0, v14);
      }
      if ( v11 )
      {
        v62 = GetProcessHeap();
        HeapFree(v62, 0, v11);
      }
      return v16;
    }
    Src = 0;
    v90 = 0;
    v91 = 0;
    hKey = 0;
    v17 = (WCHAR *)lpSubKey[0];
    v18 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey[0], 0, 0x20019u, &hKey);
    v19 = v18 < 0;
    if ( v18 > 0 )
      v19 = 1;
    if ( v19 )
      goto LABEL_18;
    v20 = hKey;
    v21 = 0;
    Type = 0;
    cbData = 0;
    v22 = RegQueryValueExW(hKey, L"ProfileImagePath", 0, &Type, 0, &cbData);
    v23 = v22 < 0;
    if ( v22 > 0 )
      v23 = 1;
    if ( !v23 )
    {
      if ( Type - 1 > 1 || !cbData || (cbData & 1) != 0 )
      {
        v24 = GetProcessHeap();
        v25 = 0;
        goto LABEL_17;
      }
      v21 = (BYTE *)Windows::Internal::ProcessHeapMemPolicy<unsigned short>::Alloc(cbData);
      if ( v21 )
      {
        v55 = RegQueryValueExW(v20, L"ProfileImagePath", 0, &Type, v21, &cbData);
        v56 = v55 < 0;
        if ( v55 > 0 )
          v56 = 1;
        if ( !v56 && !*(_WORD *)&v21[2 * (cbData >> 1) - 2] )
        {
          v57 = cbData >> 1;
          Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&Src);
          if ( v57 )
          {
            Src = v21;
            v91 = v57;
            v90 = v57 - 1;
            *(_WORD *)&v21[2 * v57 - 2] = 0;
          }
          else
          {
            v21 = (BYTE *)Src;
          }
          v58 = GetProcessHeap();
          HeapFree(v58, 0, 0);
          RegCloseKey(hKey);
          goto LABEL_19;
        }
      }
    }
    v24 = GetProcessHeap();
    v25 = v21;
LABEL_17:
    HeapFree(v24, 0, v25);
    RegCloseKey(hKey);
LABEL_18:
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::InitializeNoExpand(
      &Src,
      -2147483646,
      v14,
      L"ProfileImagePath");
    v21 = (BYTE *)Src;
LABEL_19:
    if ( !v21 || !*(_WORD *)v21 )
    {
LABEL_68:
      if ( v21 )
      {
        v51 = GetProcessHeap();
        HeapFree(v51, 0, v21);
      }
      if ( v17 )
      {
        v52 = GetProcessHeap();
        HeapFree(v52, 0, v17);
      }
      if ( v14 )
      {
        v53 = GetProcessHeap();
        HeapFree(v53, 0, v14);
      }
      if ( v11 )
      {
        v54 = GetProcessHeap();
        HeapFree(v54, 0, v11);
      }
      return 0;
    }
    v98 = 0;
    v99 = 0;
    v100 = 0;
    v26 = -1;
    do
      ++v26;
    while ( *(_WORD *)&v21[2 * v26] );
    if ( v26 > 0x7FFFFFFFFFFFFFFELL )
      std::_Xlength_error("string too long");
    if ( v26 > 7 )
    {
      v72 = std::wstring::_Calculate_growth(v26, 7, 0x7FFFFFFFFFFFFFFELL);
      if ( (unsigned __int64)(v72 + 1) > 0x7FFFFFFFFFFFFFFFLL )
        std::_Throw_bad_array_new_length();
      v73 = (char *)std::_Allocate<16,std::_Default_allocate_traits>(2 * (v72 + 1));
      *(_QWORD *)&v98 = v73;
      v99 = v26;
      v100 = v72;
      v74 = 2 * v26;
      memcpy_0(v73, v21, v74);
      *(_WORD *)&v73[v74] = 0;
    }
    else
    {
      v99 = v26;
      v100 = 7;
      v27 = 2 * v26;
      memcpy_0(&v98, v21, v27);
      *(_WORD *)((char *)&v98 + v27) = 0;
    }
    v28 = std::wstring::_Append<unsigned short>(&v98);
    *(_OWORD *)lpFileName = 0;
    v97 = 0u;
    *(_OWORD *)lpFileName = *(_OWORD *)v28;
    v97 = *(_OWORD *)(v28 + 16);
    *(_QWORD *)(v28 + 16) = 0;
    *(_QWORD *)(v28 + 24) = 7;
    *(_WORD *)v28 = 0;
    if ( v100 > 7 )
      std::_Deallocate<16>(v98, 2 * v100 + 2);
    v29 = (const WCHAR *)lpFileName;
    if ( *((_QWORD *)&v97 + 1) > 7u )
      v29 = lpFileName[0];
    FileW = (char *)CreateFileW(v29, 0, 0, 0, 3u, 0, 0);
    *(_QWORD *)cchValueName = FileW;
    if ( FileW == (char *)-1LL )
    {
LABEL_63:
      if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
        CloseHandle(FileW);
      if ( *((_QWORD *)&v97 + 1) > 7u )
        std::_Deallocate<16>(lpFileName[0], 2LL * *((_QWORD *)&v97 + 1) + 2);
      v17 = (WCHAR *)lpSubKey[0];
      goto LABEL_68;
    }
    Type = 0;
    Object = NtQueryObject(FileW, ObjectNameInformation, 0, 0, &Type);
    v33 = 0;
    v83 = 0;
    *(_QWORD *)&v98 = &v83;
    BYTE8(v98) = 1;
    if ( Object == -1073741820 )
    {
      v83 = operator new[](Type);
      Object = NtQueryObject(FileW, ObjectNameInformation, v83, Type, 0);
      v33 = (const void **)v83;
    }
    if ( Object < 0 || !v33 )
    {
LABEL_61:
      if ( v33 )
        operator delete(v33, v32);
      goto LABEL_63;
    }
    wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &hKey,
      v32,
      *(unsigned __int16 *)v33 + 2LL);
    if ( !hKey )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x294,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
        (const char *)0x8007000ELL,
        phkResulta);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&hKey);
      if ( v83 )
        operator delete(v83, v75);
      goto LABEL_117;
    }
    memcpy_0(hKey, v33[1], *(unsigned __int16 *)v33);
    *((_WORD *)hKey + *(unsigned __int16 *)v33) = 0;
    v86 = 0;
    if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\HiveList", 0, 1u, &v86) )
    {
LABEL_103:
      if ( v86 )
        RegCloseKey(v86);
      v67 = hKey;
      if ( hKey )
      {
        v68 = GetProcessHeap();
        HeapFree(v68, 0, v67);
      }
      v33 = (const void **)v83;
      goto LABEL_61;
    }
    cValues = 0;
    cbData = 0;
    cbMaxValueLen = 0;
    v34 = RegQueryInfoKeyW(v86, 0, 0, 0, 0, 0, 0, &cValues, &cbData, &cbMaxValueLen, 0, 0);
    if ( !v34 )
    {
      wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        &lpValueName,
        v35,
        2LL * cbData);
      if ( lpValueName )
      {
        wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
          &lpMem,
          v36,
          cbMaxValueLen);
        v37 = (BYTE *)lpMem;
        if ( !lpMem )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x2A7,
            (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
            (const char *)0x8007000ELL,
            phkResultb);
          v39 = lpMem;
          if ( lpMem )
          {
            v40 = GetProcessHeap();
            HeapFree(v40, 0, v39);
          }
          v41 = lpValueName;
          if ( lpValueName )
          {
            v42 = GetProcessHeap();
            HeapFree(v42, 0, v41);
          }
          if ( v86 )
            RegCloseKey(v86);
          v43 = hKey;
          if ( hKey )
          {
            v44 = GetProcessHeap();
            HeapFree(v44, 0, v43);
          }
          if ( v83 )
            operator delete(v83, v38);
          if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
            CloseHandle(FileW);
          if ( *((_QWORD *)&v97 + 1) > 7u )
            std::_Deallocate<16>(lpFileName[0], 2LL * *((_QWORD *)&v97 + 1) + 2);
          *(_QWORD *)&v97 = 0;
          *((_QWORD *)&v97 + 1) = 7;
          LOWORD(lpFileName[0]) = 0;
          v45 = GetProcessHeap();
          HeapFree(v45, 0, v21);
          v46 = (WCHAR *)lpSubKey[0];
          if ( lpSubKey[0] )
          {
            v47 = GetProcessHeap();
            HeapFree(v47, 0, v46);
          }
          if ( v14 )
          {
            v48 = GetProcessHeap();
            HeapFree(v48, 0, v14);
          }
          if ( v11 )
          {
            v49 = GetProcessHeap();
            HeapFree(v49, 0, v11);
          }
          return 2147942414LL;
        }
        for ( i = 0; i < cValues; ++i )
        {
          cchValueName[0] = 2 * cbData;
          v92 = cbMaxValueLen;
          if ( !RegEnumValueW(v86, i, lpValueName, cchValueName, 0, 0, v37, &v92)
            && CompareStringOrdinal((LPCWCH)lpMem, -1, (LPCWCH)hKey, -1, 1) == 2 )
          {
            LogOpenKeys(lpValueName);
            UnmountRegHiveFromPath(lpValueName, 2, 0);
            *(_QWORD *)&v98 = lpValueName;
            ProfileTelemetry::ForceUnloadedHive<unsigned short *>(&v98);
            *a4 = 1;
            v37 = (BYTE *)lpMem;
            break;
          }
          v37 = (BYTE *)lpMem;
        }
        if ( v37 )
        {
          v64 = GetProcessHeap();
          HeapFree(v64, 0, v37);
        }
        v65 = lpValueName;
        if ( lpValueName )
        {
          v66 = GetProcessHeap();
          HeapFree(v66, 0, v65);
        }
        goto LABEL_103;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2A4,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
        (const char *)0x8007000ELL,
        phkResultb);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpValueName);
      if ( v86 )
        RegCloseKey(v86);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&hKey);
      if ( v83 )
        operator delete(v83, v71);
LABEL_117:
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(cchValueName);
      std::wstring::~wstring(lpFileName);
      Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&Src);
      Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(lpSubKey);
      Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(v95);
      Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(lpString1);
      return 2147942414LL;
    }
    v69 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x2A1,
            (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
            (const char *)v34,
            phkResultb);
    if ( v86 )
      RegCloseKey(v86);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&hKey);
    if ( v83 )
      operator delete(v83, v70);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(cchValueName);
    std::wstring::~wstring(lpFileName);
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&Src);
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(lpSubKey);
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(v95);
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(lpString1);
    result = v69;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x2C1,
                           (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
                           v8);
  }
  return result;
}

```

## disassembly

```asm
0x18000f330  push    rbx
0x18000f332  push    rsi
0x18000f333  push    rdi
0x18000f334  push    r12
0x18000f336  push    r13
0x18000f338  push    r14
0x18000f33a  push    r15
0x18000f33c  sub     rsp, 160h
0x18000f343  mov     rax, cs:__security_cookie
0x18000f34a  xor     rax, rsp
0x18000f34d  mov     [rsp+198h+var_40], rax
0x18000f355  mov     r15, r9
0x18000f358  mov     rbx, r8
0x18000f35b  mov     rdi, rdx
0x18000f35e  xor     r13d, r13d
0x18000f361  call    ?IsUserProfileLoadedByProfileService@CUserProfile@@IEAA_NXZ; CUserProfile::IsUserProfileLoadedByProfileService(void)
0x18000f366  movzx   eax, al
0x18000f369  mov     [rbx], eax
0x18000f36b  mov     [r15], r13d
0x18000f36e  cmp     [rbx], r13d
0x18000f371  jnz     loc_18000FB20
0x18000f377  mov     [rsp+198h+lpString1], r13
0x18000f37f  mov     [rsp+198h+var_A8], 0FFFFFFFFFFFFFFFFh
0x18000f38b  mov     [rsp+198h+var_A0], 0FFFFFFFFFFFFFFFFh
0x18000f397  lea     rdx, [rsp+198h+lpString1]; unsigned __int16 **
0x18000f39f  mov     rcx, rdi; TokenHandle
0x18000f3a2  call    ?GetProfileSidString@@YAJPEAXPEAPEAG@Z; GetProfileSidString(void *,ushort * *)
0x18000f3a7  mov     ebx, eax
0x18000f3a9  test    eax, eax
0x18000f3ab  js      loc_180010128
0x18000f3b1  mov     [rsp+198h+var_98], r13
0x18000f3b9  mov     [rsp+198h+var_90], 0FFFFFFFFFFFFFFFFh
0x18000f3c5  mov     [rsp+198h+var_88], 0FFFFFFFFFFFFFFFFh
0x18000f3d1  lea     r8, [rsp+198h+cchValueName]; int *
0x18000f3d6  lea     rdx, [rsp+198h+var_98]; unsigned __int16 **
0x18000f3de  mov     r12, [rsp+198h+lpString1]
0x18000f3e6  mov     rcx, r12; lpString1
0x18000f3e9  call    ?GetProfileListKeyNameFromSid@@YAJPEBGPEAPEAGPEAH@Z; GetProfileListKeyNameFromSid(ushort const *,ushort * *,int *)
0x18000f3ee  mov     ebx, eax
0x18000f3f0  test    eax, eax
0x18000f3f2  js      loc_18000FCC0
0x18000f3f8  mov     [rsp+198h+lpSubKey], r13
0x18000f400  mov     [rsp+198h+var_C0], r13
0x18000f408  mov     [rsp+198h+var_B8], r13
0x18000f410  mov     r14, [rsp+198h+var_98]
0x18000f418  mov     r8, r14
0x18000f41b  lea     rdx, aSBak; "%s.bak"
0x18000f422  lea     rcx, [rsp+198h+lpSubKey]
0x18000f42a  call    ?InitializeFormat@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x18000f42f  mov     ebx, eax
0x18000f431  test    eax, eax
0x18000f433  js      loc_18000FC23
0x18000f439  mov     [rsp+198h+Src], r13
0x18000f441  mov     [rsp+198h+var_E0], r13
0x18000f449  mov     [rsp+198h+var_D8], r13
0x18000f451  mov     [rsp+198h+hKey], r13
0x18000f456  lea     rax, [rsp+198h+hKey]
0x18000f45b  mov     [rsp+198h+phkResult], rax; phkResult
0x18000f460  mov     r9d, 20019h; samDesired
0x18000f466  xor     r8d, r8d; ulOptions
0x18000f469  mov     rsi, [rsp+198h+lpSubKey]
0x18000f471  mov     rdx, rsi; lpSubKey
0x18000f474  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000f47b  call    cs:__imp_RegOpenKeyExW
0x18000f482  nop     dword ptr [rax+rax+00h]
0x18000f487  test    eax, eax
0x18000f489  jg      loc_18000FA44
0x18000f48f  js      loc_18000F545
0x18000f495  mov     rbx, [rsp+198h+hKey]
0x18000f49a  mov     rdi, r13
0x18000f49d  mov     [rsp+198h+Type], r13d
0x18000f4a2  mov     [rsp+198h+cbData], r13d
0x18000f4a7  lea     rax, [rsp+198h+cbData]
0x18000f4ac  mov     [rsp+198h+lpcbData], rax; lpcbData
0x18000f4b1  mov     [rsp+198h+phkResult], r13; lpData
0x18000f4b6  lea     r9, [rsp+198h+Type]; lpType
0x18000f4bb  xor     r8d, r8d; lpReserved
0x18000f4be  lea     rdx, aProfileimagepa; "ProfileImagePath"
0x18000f4c5  mov     rcx, rbx; hKey
0x18000f4c8  call    cs:__imp_RegQueryValueExW
0x18000f4cf  nop     dword ptr [rax+rax+00h]
0x18000f4d4  test    eax, eax
0x18000f4d6  jg      loc_18000FB46
0x18000f4dc  js      short loc_18000F514
0x18000f4de  mov     eax, [rsp+198h+Type]
0x18000f4e2  dec     eax
0x18000f4e4  cmp     eax, 1
0x18000f4e7  ja      loc_18000FCFF
0x18000f4ed  mov     eax, [rsp+198h+cbData]
0x18000f4f1  test    eax, eax
0x18000f4f3  jz      loc_18000FCFF
0x18000f4f9  test    al, 1
0x18000f4fb  jnz     loc_18000FCFF
0x18000f501  mov     ecx, eax
0x18000f503  call    ?Alloc@?$ProcessHeapMemPolicy@G@Internal@Windows@@SAPEAG_K@Z; Windows::Internal::ProcessHeapMemPolicy<ushort>::Alloc(unsigned __int64)
0x18000f508  mov     rdi, rax
0x18000f50b  test    rax, rax
0x18000f50e  jnz     loc_18000FB55
0x18000f514  call    cs:__imp_GetProcessHeap
0x18000f51b  nop     dword ptr [rax+rax+00h]
0x18000f520  mov     r8, rdi; lpMem
0x18000f523  xor     edx, edx; dwFlags
0x18000f525  mov     rcx, rax; hHeap
0x18000f528  call    cs:__imp_HeapFree
0x18000f52f  nop     dword ptr [rax+rax+00h]
0x18000f534  mov     rcx, [rsp+198h+hKey]; hKey
0x18000f539  call    cs:__imp_RegCloseKey
0x18000f540  nop     dword ptr [rax+rax+00h]
0x18000f545  lea     r9, aProfileimagepa; "ProfileImagePath"
0x18000f54c  mov     r8, r14
0x18000f54f  mov     rdx, 0FFFFFFFF80000002h
0x18000f556  lea     rcx, [rsp+198h+Src]
0x18000f55e  call    ?InitializeNoExpand@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEAUHKEY__@@PEBG1@Z; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::InitializeNoExpand(HKEY__ *,ushort const *,ushort const *)
0x18000f563  mov     rdi, [rsp+198h+Src]
0x18000f56b  test    rdi, rdi
0x18000f56e  jz      loc_18000FA89
0x18000f574  cmp     word ptr [rdi], 0
0x18000f578  jz      loc_18000FA89
0x18000f57e  xorps   xmm0, xmm0
0x18000f581  movups  [rsp+198h+var_60], xmm0
0x18000f589  mov     [rsp+198h+var_50], r13
0x18000f591  mov     [rsp+198h+var_48], r13
0x18000f599  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18000f5a0  inc     rbx
0x18000f5a3  cmp     word ptr [rdi+rbx*2], 0
0x18000f5a8  jnz     short loc_18000F5A0
0x18000f5aa  mov     r8, 7FFFFFFFFFFFFFFEh
0x18000f5b4  cmp     rbx, r8
0x18000f5b7  ja      loc_180010166
0x18000f5bd  cmp     rbx, 7
0x18000f5c1  ja      loc_180010028
0x18000f5c7  mov     [rsp+198h+var_50], rbx
0x18000f5cf  mov     [rsp+198h+var_48], 7
0x18000f5db  add     rbx, rbx
0x18000f5de  mov     r8, rbx; Size
0x18000f5e1  mov     rdx, rdi; Src
0x18000f5e4  lea     rcx, [rsp+198h+var_60]; void *
0x18000f5ec  call    memcpy_0
0x18000f5f1  mov     word ptr [rsp+rbx+198h+var_60], r13w
0x18000f5fa  mov     r8d, 0Bh
0x18000f600  lea     rcx, [rsp+198h+var_60]; Src
0x18000f608  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18000f60d  xorps   xmm0, xmm0
0x18000f610  movups  xmmword ptr [rsp+198h+lpFileName], xmm0
0x18000f618  mov     qword ptr [rsp+198h+var_70], r13
0x18000f620  mov     qword ptr [rsp+198h+var_70+8], r13
0x18000f628  movups  xmm0, xmmword ptr [rax]
0x18000f62b  movups  xmmword ptr [rsp+198h+lpFileName], xmm0
0x18000f633  movups  xmm1, xmmword ptr [rax+10h]
0x18000f637  movups  [rsp+198h+var_70], xmm1
0x18000f63f  mov     [rax+10h], r13
0x18000f643  mov     qword ptr [rax+18h], 7
0x18000f64b  mov     [rax], r13w
0x18000f64f  mov     rdx, [rsp+198h+var_48]
0x18000f657  cmp     rdx, 7
0x18000f65b  ja      loc_18001017F
0x18000f661  lea     rcx, [rsp+198h+lpFileName]
0x18000f669  cmp     qword ptr [rsp+198h+var_70+8], 7
0x18000f672  cmova   rcx, [rsp+198h+lpFileName]; lpFileName
0x18000f67b  mov     [rsp+198h+hTemplateFile], r13; hTemplateFile
0x18000f680  mov     dword ptr [rsp+198h+lpcbData], r13d; dwFlagsAndAttributes
0x18000f685  mov     dword ptr [rsp+198h+phkResult], 3; dwCreationDisposition
0x18000f68d  xor     r9d, r9d; lpSecurityAttributes
0x18000f690  xor     r8d, r8d; dwShareMode
0x18000f693  xor     edx, edx; dwDesiredAccess
0x18000f695  call    cs:__imp_CreateFileW
0x18000f69c  nop     dword ptr [rax+rax+00h]
0x18000f6a1  mov     r13, rax
0x18000f6a4  mov     qword ptr [rsp+198h+cchValueName], rax
0x18000f6a9  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000f6ad  jz      loc_18000FA61
0x18000f6b3  xor     esi, esi
0x18000f6b5  mov     [rsp+198h+Type], esi
0x18000f6b9  lea     rax, [rsp+198h+Type]
0x18000f6be  mov     [rsp+198h+phkResult], rax; ReturnLength
0x18000f6c3  xor     r9d, r9d; ObjectInformationLength
0x18000f6c6  xor     r8d, r8d; ObjectInformation
0x18000f6c9  mov     edx, 1; ObjectInformationClass
0x18000f6ce  mov     rcx, r13; Handle
0x18000f6d1  call    cs:__imp_NtQueryObject
0x18000f6d8  nop     dword ptr [rax+rax+00h]
0x18000f6dd  mov     ebx, esi
0x18000f6df  mov     [rsp+198h+var_118], rbx
0x18000f6e7  lea     rcx, [rsp+198h+var_118]
0x18000f6ef  mov     qword ptr [rsp+198h+var_60], rcx
0x18000f6f7  mov     byte ptr [rsp+198h+var_60+8], 1
0x18000f6ff  cmp     eax, 0C0000004h
0x18000f704  jnz     short loc_18000F740
0x18000f706  mov     ecx, [rsp+198h+Type]; unsigned __int64
0x18000f70a  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000f70f  mov     [rsp+198h+var_118], rax
0x18000f717  mov     [rsp+198h+phkResult], rsi; int
0x18000f71c  mov     r9d, [rsp+198h+Type]; ObjectInformationLength
0x18000f721  mov     r8, rax; ObjectInformation
0x18000f724  mov     edx, 1; ObjectInformationClass
0x18000f729  mov     rcx, r13; Handle
0x18000f72c  call    cs:__imp_NtQueryObject
0x18000f733  nop     dword ptr [rax+rax+00h]
0x18000f738  mov     rbx, [rsp+198h+var_118]
0x18000f740  test    eax, eax
0x18000f742  js      loc_18000FA53
0x18000f748  test    rbx, rbx
0x18000f74b  jz      loc_18000FA53
0x18000f751  movzx   r8d, word ptr [rbx]
0x18000f755  add     r8, 2
0x18000f759  lea     rcx, [rsp+198h+hKey]
0x18000f75e  call    ??$make_unique_string@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18000f763  nop
0x18000f764  mov     rcx, [rsp+198h+hKey]; void *
0x18000f769  test    rcx, rcx
0x18000f76c  jz      loc_180010090
0x18000f772  movzx   r8d, word ptr [rbx]; Size
0x18000f776  mov     rdx, [rbx+8]; Src
0x18000f77a  call    memcpy_0
0x18000f77f  movzx   r8d, word ptr [rbx]
0x18000f783  mov     rax, [rsp+198h+hKey]
0x18000f788  mov     [rax+r8*2], si
0x18000f78d  mov     [rsp+198h+var_100], rsi
0x18000f795  lea     rax, [rsp+198h+var_100]
0x18000f79d  mov     [rsp+198h+phkResult], rax; phkResult
0x18000f7a2  mov     r9d, 1; samDesired
0x18000f7a8  xor     r8d, r8d; ulOptions
0x18000f7ab  lea     rdx, aSystemCurrentc_2; "System\\CurrentControlSet\\Control\\Hiv"...
0x18000f7b2  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000f7b9  call    cs:__imp_RegOpenKeyExW
0x18000f7c0  nop     dword ptr [rax+rax+00h]
0x18000f7c5  test    eax, eax
0x18000f7c7  jnz     loc_18000FE6A
0x18000f7cd  mov     [rsp+198h+cValues], esi
0x18000f7d4  mov     [rsp+198h+cbData], esi
0x18000f7d8  mov     [rsp+198h+cbMaxValueLen], esi
0x18000f7df  mov     [rsp+198h+lpftLastWriteTime], rsi; lpftLastWriteTime
0x18000f7e4  mov     [rsp+198h+lpcbSecurityDescriptor], rsi; lpcbSecurityDescriptor
0x18000f7e9  lea     rax, [rsp+198h+cbMaxValueLen]
0x18000f7f1  mov     [rsp+198h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x18000f7f6  lea     rax, [rsp+198h+cbData]
0x18000f7fb  mov     [rsp+198h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x18000f800  lea     rax, [rsp+198h+cValues]
0x18000f808  mov     [rsp+198h+lpcValues], rax; lpcValues
0x18000f80d  mov     [rsp+198h+hTemplateFile], rsi; lpcbMaxClassLen
0x18000f812  mov     [rsp+198h+lpcbData], rsi; lpcbMaxSubKeyLen
0x18000f817  mov     [rsp+198h+phkResult], rsi; int
0x18000f81c  xor     r9d, r9d; lpReserved
0x18000f81f  xor     r8d, r8d; lpcchClass
0x18000f822  xor     edx, edx; lpClass
0x18000f824  mov     rcx, [rsp+198h+var_100]; hKey
0x18000f82c  call    cs:__imp_RegQueryInfoKeyW
0x18000f833  nop     dword ptr [rax+rax+00h]
0x18000f838  test    eax, eax
0x18000f83a  jnz     loc_18000FEBB
0x18000f840  mov     r8d, [rsp+198h+cbData]
0x18000f845  add     r8, r8
0x18000f848  lea     rcx, [rsp+198h+lpValueName]
0x18000f850  call    ??$make_unique_string@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18000f855  nop
0x18000f856  cmp     [rsp+198h+lpValueName], 0
0x18000f85f  jz      loc_18000FF68
0x18000f865  mov     r8d, [rsp+198h+cbMaxValueLen]
0x18000f86d  lea     rcx, [rsp+198h+lpMem]
0x18000f875  call    ??$make_unique_string@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18000f87a  mov     rsi, [rsp+198h+lpMem]
0x18000f882  test    rsi, rsi
0x18000f885  jnz     loc_18000FD13
0x18000f88b  mov     rcx, [rsp+198h]; this
0x18000f893  mov     r9d, 8007000Eh; char *
0x18000f899  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x18000f8a0  mov     edx, 2A7h; void *
0x18000f8a5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f8aa  mov     rbx, [rsp+198h+lpMem]
0x18000f8b2  test    rbx, rbx
0x18000f8b5  jz      short loc_18000F8D8
0x18000f8b7  call    cs:__imp_GetProcessHeap
0x18000f8be  nop     dword ptr [rax+rax+00h]
0x18000f8c3  mov     rcx, rax; hHeap
0x18000f8c6  mov     r8, rbx; lpMem
0x18000f8c9  xor     edx, edx; dwFlags
0x18000f8cb  call    cs:__imp_HeapFree
0x18000f8d2  nop     dword ptr [rax+rax+00h]
0x18000f8d7  nop
0x18000f8d8  mov     rbx, [rsp+198h+lpValueName]
0x18000f8e0  test    rbx, rbx
0x18000f8e3  jz      short loc_18000F906
0x18000f8e5  call    cs:__imp_GetProcessHeap
0x18000f8ec  nop     dword ptr [rax+rax+00h]
0x18000f8f1  mov     rcx, rax; hHeap
0x18000f8f4  mov     r8, rbx; lpMem
0x18000f8f7  xor     edx, edx; dwFlags
0x18000f8f9  call    cs:__imp_HeapFree
0x18000f900  nop     dword ptr [rax+rax+00h]
0x18000f905  nop
0x18000f906  mov     rcx, [rsp+198h+var_100]; hKey
0x18000f90e  test    rcx, rcx
0x18000f911  jz      short loc_18000F920
0x18000f913  call    cs:__imp_RegCloseKey
0x18000f91a  nop     dword ptr [rax+rax+00h]
0x18000f91f  nop
0x18000f920  mov     rbx, [rsp+198h+hKey]
0x18000f925  test    rbx, rbx
0x18000f928  jz      short loc_18000F94B
0x18000f92a  call    cs:__imp_GetProcessHeap
  ... truncated ...
```
