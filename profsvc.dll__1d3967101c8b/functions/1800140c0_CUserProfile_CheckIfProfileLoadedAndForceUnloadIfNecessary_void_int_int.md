# CUserProfile::CheckIfProfileLoadedAndForceUnloadIfNecessary(void *,int *,int *)

- ea: `0x1800140c0`
- end: `0x180014e1e`
- name: `?CheckIfProfileLoadedAndForceUnloadIfNecessary@CUserProfile@@IEAAJPEAXPEAH1@Z`
- size: `3422`
- prototype: `__int64 __fastcall(CUserProfile *this, void *, int *, int *)`
- caller_count: `1`
- callee_count: `26`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18002bf94`

## callees

- `0x180007978`
- `0x180009120`
- `0x180009bf0`
- `0x18000a9b8`
- `0x18000d460`
- `0x18000f1b0`
- `0x18000ff50`
- `0x180010f30`
- `0x1800111a0`
- `0x1800138c4`
- `0x1800140c0`
- `0x180014e30`
- `0x180014fc4`
- `0x180015108`
- `0x1800152dc`
- `0x1800154b0`
- `0x18002d2d8`
- `0x18002e648`
- `0x180032538`
- `0x180032a04`
- `0x1800360f8`
- `0x18003a730`
- `0x18003ab00`
- `0x18003ac50`
- `0x180042994`
- `0x1800510ec`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180014d9f`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180014d9f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800142a6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180014617`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180014639`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001466c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800146d2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800146f4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001470e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180014728`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180014790`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800147aa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800147c4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800147de`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800148a7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180014904`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001491e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180014938`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180014a9e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180014ac0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180014af3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800142a6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180014617`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180014639`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001466c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800146d2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800146f4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001470e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180014728`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180014790`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800147aa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800147c4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800147de`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800148a7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180014904`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001491e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180014938`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180014a9e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180014ac0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180014af3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014298`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014609`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001462b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001465e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800146c4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800146e6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014700`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001471a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014782`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001479c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800147b6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800147d0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014899`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800148f6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014910`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001492a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014984`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014a90`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014ab2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014ae5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014298`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014609`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001462b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001465e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800146c4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800146e6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014700`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001471a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014782`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001479c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800147b6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800147d0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014899`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800148f6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014910`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001492a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014984`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014a90`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014ab2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014ae5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014dc8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014df0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014dc8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014df0`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180014a20`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180014a20`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001420c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180014517`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001420c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180014517`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180014584`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180014584`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180014252`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180014839`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180014252`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180014839`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800142b1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001464d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800148b2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180014ad4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180014b31`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180014be8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800142b1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001464d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800148b2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180014ad4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180014b31`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180014be8`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1800149f8`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1800149f8`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180014406`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180014406`
- `ntdll!NtQueryObject` at `0x18001443a`
- `ntdll!NtQueryObject` at `0x180014490`
- `ntdll!NtQueryObject` at `0x18001443a`
- `ntdll!NtQueryObject` at `0x180014490`

## string_xrefs

- `0x1800145eb`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x1800148d7`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x180014950`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x180014b11`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x180014bbb`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x180014cdd`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x180014d72`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x180014248`: `ProfileImagePath`
- `0x1800142b9`: `ProfileImagePath`
- `0x18001482f`: `ProfileImagePath`

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
  WCHAR *v11; // r13
  int ProfileListKeyNameFromSid; // eax
  unsigned int v13; // ebx
  unsigned __int16 *v14; // r14
  int v15; // eax
  unsigned int v16; // ebx
  _WORD *v17; // rdi
  WCHAR *v18; // r15
  LSTATUS v19; // eax
  bool v20; // sf
  HKEY v21; // rsi
  BYTE *v22; // rbx
  LSTATUS v23; // eax
  bool v24; // sf
  HANDLE v25; // rax
  BYTE *v26; // r8
  unsigned __int64 v27; // rbx
  size_t v28; // rbx
  __int64 v29; // rax
  const WCHAR *v30; // rcx
  char *FileW; // r15
  NTSTATUS Object; // eax
  __int64 v33; // rdx
  const void **v34; // rbx
  unsigned int v35; // eax
  __int64 v36; // rdx
  __int64 v37; // rdx
  BYTE *v38; // rsi
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
  __int64 v57; // rdx
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
  __int64 v70; // r15
  char *v71; // rsi
  size_t v72; // rbx
  int phkResult; // [rsp+20h] [rbp-178h]
  int phkResulta; // [rsp+20h] [rbp-178h]
  unsigned int phkResultb; // [rsp+20h] [rbp-178h]
  DWORD cbData; // [rsp+60h] [rbp-138h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-130h] BYREF
  DWORD Type; // [rsp+70h] [rbp-128h] BYREF
  DWORD cchValueName[2]; // [rsp+78h] [rbp-120h] BYREF
  void *v80; // [rsp+80h] [rbp-118h] BYREF
  LPWSTR lpValueName; // [rsp+88h] [rbp-110h] BYREF
  DWORD cbMaxValueLen; // [rsp+90h] [rbp-108h] BYREF
  HKEY v83; // [rsp+98h] [rbp-100h] BYREF
  DWORD cValues; // [rsp+A0h] [rbp-F8h] BYREF
  LPVOID lpMem; // [rsp+A8h] [rbp-F0h] BYREF
  void *Src; // [rsp+B0h] [rbp-E8h] BYREF
  __int64 v87; // [rsp+B8h] [rbp-E0h]
  __int64 v88; // [rsp+C0h] [rbp-D8h]
  DWORD v89; // [rsp+C8h] [rbp-D0h] BYREF
  LPCWSTR lpSubKey[3]; // [rsp+D0h] [rbp-C8h] BYREF
  LPCWCH lpString1[3]; // [rsp+E8h] [rbp-B0h] BYREF
  unsigned __int16 *v92[3]; // [rsp+100h] [rbp-98h] BYREF
  LPCWSTR lpFileName[2]; // [rsp+118h] [rbp-80h] BYREF
  __int128 v94; // [rsp+128h] [rbp-70h]
  __int128 v95; // [rsp+138h] [rbp-60h] BYREF
  unsigned __int64 v96; // [rsp+148h] [rbp-50h]
  unsigned __int64 v97; // [rsp+150h] [rbp-48h]
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
      Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)lpString1);
      return v10;
    }
    v92[0] = 0;
    v92[1] = (unsigned __int16 *)-1LL;
    v92[2] = (unsigned __int16 *)-1LL;
    v11 = (WCHAR *)lpString1[0];
    ProfileListKeyNameFromSid = GetProfileListKeyNameFromSid(lpString1[0], v92, (int *)cchValueName);
    v13 = ProfileListKeyNameFromSid;
    if ( ProfileListKeyNameFromSid < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x25A,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
        (const char *)(unsigned int)ProfileListKeyNameFromSid,
        phkResult);
      Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)v92);
      Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)lpString1);
      return v13;
    }
    memset(lpSubKey, 0, sizeof(lpSubKey));
    v14 = v92[0];
    v15 = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::InitializeFormat(
            lpSubKey,
            L"%s.bak",
            v92[0]);
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
    v17 = 0;
    Src = 0;
    v87 = 0;
    v88 = 0;
    hKey = 0;
    v18 = (WCHAR *)lpSubKey[0];
    v19 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey[0], 0, 0x20019u, &hKey);
    v20 = v19 < 0;
    if ( v19 > 0 )
      v20 = 1;
    if ( v20 )
      goto LABEL_18;
    v21 = hKey;
    v22 = 0;
    Type = 0;
    cbData = 0;
    v23 = RegQueryValueExW(hKey, L"ProfileImagePath", 0, &Type, 0, &cbData);
    v24 = v23 < 0;
    if ( v23 > 0 )
      v24 = 1;
    if ( !v24 )
    {
      if ( Type - 1 > 1 || !cbData || (cbData & 1) != 0 )
      {
        v25 = GetProcessHeap();
        v26 = 0;
        goto LABEL_17;
      }
      v22 = (BYTE *)Windows::Internal::ProcessHeapMemPolicy<unsigned short>::Alloc(cbData);
      if ( v22 )
      {
        v55 = RegQueryValueExW(v21, L"ProfileImagePath", 0, &Type, v22, &cbData);
        v56 = v55 < 0;
        if ( v55 > 0 )
          v56 = 1;
        if ( !v56 )
        {
          v57 = cbData >> 1;
          if ( !*(_WORD *)&v22[2 * (unsigned int)(v57 - 1)] )
          {
            v87 = 0;
            v88 = 0;
            if ( (_DWORD)v57 )
            {
              v17 = v22;
              Src = v22;
              v88 = (unsigned int)v57;
              v87 = v57 - 1;
              *(_WORD *)&v22[2 * v57 - 2] = 0;
            }
            v58 = GetProcessHeap();
            HeapFree(v58, 0, 0);
            RegCloseKey(hKey);
            goto LABEL_19;
          }
        }
      }
    }
    v25 = GetProcessHeap();
    v26 = v22;
LABEL_17:
    HeapFree(v25, 0, v26);
    RegCloseKey(hKey);
LABEL_18:
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::InitializeNoExpand(
      &Src,
      -2147483646,
      v14,
      L"ProfileImagePath");
    v17 = Src;
LABEL_19:
    if ( !v17 || !*v17 )
    {
LABEL_68:
      if ( v17 )
      {
        v51 = GetProcessHeap();
        HeapFree(v51, 0, v17);
      }
      if ( v18 )
      {
        v52 = GetProcessHeap();
        HeapFree(v52, 0, v18);
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
    v95 = 0;
    v96 = 0;
    v97 = 0;
    v27 = -1;
    do
      ++v27;
    while ( v17[v27] );
    if ( v27 > 0x7FFFFFFFFFFFFFFELL )
      std::_Xlength_error("string too long");
    if ( v27 > 7 )
    {
      v70 = std::wstring::_Calculate_growth(v27, 7);
      if ( (unsigned __int64)(v70 + 1) > 0x7FFFFFFFFFFFFFFFLL )
        std::_Throw_bad_array_new_length();
      v71 = (char *)std::_Allocate<16,std::_Default_allocate_traits>(2 * (v70 + 1));
      *(_QWORD *)&v95 = v71;
      v96 = v27;
      v97 = v70;
      v72 = 2 * v27;
      memcpy_0(v71, v17, v72);
      *(_WORD *)&v71[v72] = 0;
    }
    else
    {
      v96 = v27;
      v97 = 7;
      v28 = 2 * v27;
      memcpy_0(&v95, v17, v28);
      *(_WORD *)((char *)&v95 + v28) = 0;
    }
    v29 = std::wstring::_Append<unsigned short>(&v95);
    *(_OWORD *)lpFileName = 0;
    v94 = 0u;
    *(_OWORD *)lpFileName = *(_OWORD *)v29;
    v94 = *(_OWORD *)(v29 + 16);
    *(_QWORD *)(v29 + 16) = 0;
    *(_QWORD *)(v29 + 24) = 7;
    *(_WORD *)v29 = 0;
    if ( v97 > 7 )
      std::_Deallocate<16>((_QWORD *)v95, 2 * v97 + 2);
    v30 = (const WCHAR *)lpFileName;
    if ( *((_QWORD *)&v94 + 1) > 7u )
      v30 = lpFileName[0];
    FileW = (char *)CreateFileW(v30, 0, 0, 0, 3u, 0, 0);
    *(_QWORD *)cchValueName = FileW;
    if ( FileW == (char *)-1LL )
    {
LABEL_63:
      if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
        CloseHandle(FileW);
      if ( *((_QWORD *)&v94 + 1) > 7u )
        std::_Deallocate<16>((_QWORD *)lpFileName[0], 2LL * *((_QWORD *)&v94 + 1) + 2);
      v18 = (WCHAR *)lpSubKey[0];
      goto LABEL_68;
    }
    Type = 0;
    Object = NtQueryObject(FileW, ObjectNameInformation, 0, 0, &Type);
    v34 = 0;
    v80 = 0;
    *(_QWORD *)&v95 = &v80;
    BYTE8(v95) = 1;
    if ( Object == -1073741820 )
    {
      v80 = operator new[](Type);
      Object = NtQueryObject(FileW, ObjectNameInformation, v80, Type, 0);
      v34 = (const void **)v80;
    }
    if ( Object < 0 || !v34 )
    {
LABEL_61:
      if ( v34 )
        operator delete(v34);
      goto LABEL_63;
    }
    wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &hKey,
      v33,
      *(unsigned __int16 *)v34 + 2LL);
    if ( !hKey )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x294,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
        (const char *)0x8007000ELL,
        phkResulta);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((void **)&hKey);
      if ( v80 )
        operator delete(v80);
      goto LABEL_117;
    }
    memcpy_0(hKey, v34[1], *(unsigned __int16 *)v34);
    *((_WORD *)hKey + *(unsigned __int16 *)v34) = 0;
    v83 = 0;
    if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\HiveList", 0, 1u, &v83) )
    {
LABEL_103:
      if ( v83 )
        RegCloseKey(v83);
      v67 = hKey;
      if ( hKey )
      {
        v68 = GetProcessHeap();
        HeapFree(v68, 0, v67);
      }
      v34 = (const void **)v80;
      goto LABEL_61;
    }
    cValues = 0;
    cbData = 0;
    cbMaxValueLen = 0;
    v35 = RegQueryInfoKeyW(v83, 0, 0, 0, 0, 0, 0, &cValues, &cbData, &cbMaxValueLen, 0, 0);
    if ( !v35 )
    {
      wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        &lpValueName,
        v36,
        2LL * cbData);
      if ( lpValueName )
      {
        wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
          &lpMem,
          v37,
          cbMaxValueLen);
        v38 = (BYTE *)lpMem;
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
          if ( v83 )
            RegCloseKey(v83);
          v43 = hKey;
          if ( hKey )
          {
            v44 = GetProcessHeap();
            HeapFree(v44, 0, v43);
          }
          if ( v80 )
            operator delete(v80);
          if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
            CloseHandle(FileW);
          if ( *((_QWORD *)&v94 + 1) > 7u )
            std::_Deallocate<16>((_QWORD *)lpFileName[0], 2LL * *((_QWORD *)&v94 + 1) + 2);
          *(_QWORD *)&v94 = 0;
          *((_QWORD *)&v94 + 1) = 7;
          LOWORD(lpFileName[0]) = 0;
          v45 = GetProcessHeap();
          HeapFree(v45, 0, v17);
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
          v89 = cbMaxValueLen;
          if ( !RegEnumValueW(v83, i, lpValueName, cchValueName, 0, 0, v38, &v89)
            && CompareStringOrdinal((LPCWCH)lpMem, -1, (LPCWCH)hKey, -1, 1) == 2 )
          {
            LogOpenKeys(lpValueName);
            UnmountRegHiveFromPath(lpValueName, 2, 0);
            *(_QWORD *)&v95 = lpValueName;
            ProfileTelemetry::ForceUnloadedHive<unsigned short *>(&v95);
            *a4 = 1;
            v38 = (BYTE *)lpMem;
            break;
          }
          v38 = (BYTE *)lpMem;
        }
        if ( v38 )
        {
          v64 = GetProcessHeap();
          HeapFree(v64, 0, v38);
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
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((void **)&lpValueName);
      if ( v83 )
        RegCloseKey(v83);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((void **)&hKey);
      if ( v80 )
        operator delete(v80);
LABEL_117:
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>((void **)cchValueName);
      std::wstring::~wstring(lpFileName);
      Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)&Src);
      Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)lpSubKey);
      Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)v92);
      Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)lpString1);
      return 2147942414LL;
    }
    v69 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x2A1,
            (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
            (const char *)v35,
            phkResultb);
    if ( v83 )
      RegCloseKey(v83);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((void **)&hKey);
    if ( v80 )
      operator delete(v80);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>((void **)cchValueName);
    std::wstring::~wstring(lpFileName);
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)&Src);
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)lpSubKey);
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)v92);
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)lpString1);
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
0x1800140c0  push    rbx
0x1800140c2  push    rsi
0x1800140c3  push    rdi
0x1800140c4  push    r12
0x1800140c6  push    r13
0x1800140c8  push    r14
0x1800140ca  push    r15
0x1800140cc  sub     rsp, 160h
0x1800140d3  mov     rax, cs:__security_cookie
0x1800140da  xor     rax, rsp
0x1800140dd  mov     [rsp+198h+var_40], rax
0x1800140e5  mov     r12, r9
0x1800140e8  mov     rbx, r8
0x1800140eb  mov     rdi, rdx
0x1800140ee  xor     esi, esi
0x1800140f0  call    ?IsUserProfileLoadedByProfileService@CUserProfile@@IEAA_NXZ; CUserProfile::IsUserProfileLoadedByProfileService(void)
0x1800140f5  movzx   eax, al
0x1800140f8  mov     [rbx], eax
0x1800140fa  mov     [r12], esi
0x1800140fe  cmp     [rbx], esi
0x180014100  jnz     loc_1800147E4
0x180014106  mov     [rsp+198h+lpString1], rsi
0x18001410e  mov     [rsp+198h+var_A8], 0FFFFFFFFFFFFFFFFh
0x18001411a  mov     [rsp+198h+var_A0], 0FFFFFFFFFFFFFFFFh
0x180014126  lea     rdx, [rsp+198h+lpString1]; unsigned __int16 **
0x18001412e  mov     rcx, rdi; TokenHandle
0x180014131  call    ?GetProfileSidString@@YAJPEAXPEAPEAG@Z; GetProfileSidString(void *,ushort * *)
0x180014136  mov     ebx, eax
0x180014138  test    eax, eax
0x18001413a  js      loc_180014D67
0x180014140  mov     [rsp+198h+var_98], rsi
0x180014148  mov     [rsp+198h+var_90], 0FFFFFFFFFFFFFFFFh
0x180014154  mov     [rsp+198h+var_88], 0FFFFFFFFFFFFFFFFh
0x180014160  lea     r8, [rsp+198h+cchValueName]; int *
0x180014165  lea     rdx, [rsp+198h+var_98]; unsigned __int16 **
0x18001416d  mov     r13, [rsp+198h+lpString1]
0x180014175  mov     rcx, r13; lpString1
0x180014178  call    ?GetProfileListKeyNameFromSid@@YAJPEBGPEAPEAGPEAH@Z; GetProfileListKeyNameFromSid(ushort const *,ushort * *,int *)
0x18001417d  mov     ebx, eax
0x18001417f  test    eax, eax
0x180014181  js      loc_180014945
0x180014187  mov     [rsp+198h+lpSubKey], rsi
0x18001418f  mov     [rsp+198h+var_C0], rsi
0x180014197  mov     [rsp+198h+var_B8], rsi
0x18001419f  mov     r14, [rsp+198h+var_98]
0x1800141a7  mov     r8, r14
0x1800141aa  lea     rdx, aSBak; "%s.bak"
0x1800141b1  lea     rcx, [rsp+198h+lpSubKey]
0x1800141b9  call    ?InitializeFormat@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x1800141be  mov     ebx, eax
0x1800141c0  test    eax, eax
0x1800141c2  js      loc_1800148CC
0x1800141c8  mov     edi, esi
0x1800141ca  mov     [rsp+198h+Src], rsi
0x1800141d2  mov     [rsp+198h+var_E0], rsi
0x1800141da  mov     [rsp+198h+var_D8], rsi
0x1800141e2  mov     [rsp+198h+hKey], rsi
0x1800141e7  lea     rax, [rsp+198h+hKey]
0x1800141ec  mov     [rsp+198h+phkResult], rax; phkResult
0x1800141f1  mov     r9d, 20019h; samDesired
0x1800141f7  xor     r8d, r8d; ulOptions
0x1800141fa  mov     r15, [rsp+198h+lpSubKey]
0x180014202  mov     rdx, r15; lpSubKey
0x180014205  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001420c  call    cs:__imp_RegOpenKeyExW
0x180014212  test    eax, eax
0x180014214  jg      loc_180014738
0x18001421a  js      loc_1800142B9
0x180014220  mov     rsi, [rsp+198h+hKey]
0x180014225  xor     edx, edx
0x180014227  mov     ebx, edx
0x180014229  mov     [rsp+198h+Type], edx
0x18001422d  mov     [rsp+198h+cbData], edx
0x180014231  lea     rax, [rsp+198h+cbData]
0x180014236  mov     [rsp+198h+lpcbData], rax; lpcbData
0x18001423b  mov     [rsp+198h+phkResult], rdx; lpData
0x180014240  lea     r9, [rsp+198h+Type]; lpType
0x180014245  xor     r8d, r8d; lpReserved
0x180014248  lea     rdx, aProfileimagepa; "ProfileImagePath"
0x18001424f  mov     rcx, rsi; hKey
0x180014252  call    cs:__imp_RegQueryValueExW
0x180014258  test    eax, eax
0x18001425a  jg      loc_180014809
0x180014260  js      short loc_180014298
0x180014262  mov     eax, [rsp+198h+Type]
0x180014266  dec     eax
0x180014268  cmp     eax, 1
0x18001426b  ja      loc_180014984
0x180014271  mov     eax, [rsp+198h+cbData]
0x180014275  test    eax, eax
0x180014277  jz      loc_180014984
0x18001427d  test    al, 1
0x18001427f  jnz     loc_180014984
0x180014285  mov     ecx, eax
0x180014287  call    ?Alloc@?$ProcessHeapMemPolicy@G@Internal@Windows@@SAPEAG_K@Z; Windows::Internal::ProcessHeapMemPolicy<ushort>::Alloc(unsigned __int64)
0x18001428c  mov     rbx, rax
0x18001428f  test    rax, rax
0x180014292  jnz     loc_180014818
0x180014298  call    cs:__imp_GetProcessHeap
0x18001429e  mov     r8, rbx; lpMem
0x1800142a1  xor     edx, edx; dwFlags
0x1800142a3  mov     rcx, rax; hHeap
0x1800142a6  call    cs:__imp_HeapFree
0x1800142ac  mov     rcx, [rsp+198h+hKey]; hKey
0x1800142b1  call    cs:__imp_RegCloseKey
0x1800142b7  xor     esi, esi
0x1800142b9  lea     r9, aProfileimagepa; "ProfileImagePath"
0x1800142c0  mov     r8, r14
0x1800142c3  mov     rdx, 0FFFFFFFF80000002h
0x1800142ca  lea     rcx, [rsp+198h+Src]
0x1800142d2  call    ?InitializeNoExpand@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEAUHKEY__@@PEBG1@Z; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::InitializeNoExpand(HKEY__ *,ushort const *,ushort const *)
0x1800142d7  mov     rdi, [rsp+198h+Src]
0x1800142df  test    rdi, rdi
0x1800142e2  jz      loc_18001477D
0x1800142e8  cmp     word ptr [rdi], 0
0x1800142ec  jz      loc_18001477D
0x1800142f2  xorps   xmm0, xmm0
0x1800142f5  movups  [rsp+198h+var_60], xmm0
0x1800142fd  mov     [rsp+198h+var_50], rsi
0x180014305  mov     [rsp+198h+var_48], rsi
0x18001430d  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180014314  inc     rbx
0x180014317  cmp     word ptr [rdi+rbx*2], 0
0x18001431c  jnz     short loc_180014314
0x18001431e  mov     r8, 7FFFFFFFFFFFFFFEh
0x180014328  cmp     rbx, r8
0x18001432b  ja      loc_180014D98
0x180014331  cmp     rbx, 7
0x180014335  ja      loc_180014C67
0x18001433b  mov     [rsp+198h+var_50], rbx
0x180014343  mov     [rsp+198h+var_48], 7
0x18001434f  add     rbx, rbx
0x180014352  mov     r8, rbx; Size
0x180014355  mov     rdx, rdi; Src
0x180014358  lea     rcx, [rsp+198h+var_60]; void *
0x180014360  call    memcpy_0
0x180014365  mov     word ptr [rsp+rbx+198h+var_60], si
0x18001436d  mov     r8d, 0Bh
0x180014373  lea     rcx, [rsp+198h+var_60]; Src
0x18001437b  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180014380  xorps   xmm0, xmm0
0x180014383  movups  xmmword ptr [rsp+198h+lpFileName], xmm0
0x18001438b  mov     qword ptr [rsp+198h+var_70], rsi
0x180014393  mov     qword ptr [rsp+198h+var_70+8], rsi
0x18001439b  movups  xmm0, xmmword ptr [rax]
0x18001439e  movups  xmmword ptr [rsp+198h+lpFileName], xmm0
0x1800143a6  movups  xmm1, xmmword ptr [rax+10h]
0x1800143aa  movups  [rsp+198h+var_70], xmm1
0x1800143b2  mov     [rax+10h], rsi
0x1800143b6  mov     qword ptr [rax+18h], 7
0x1800143be  mov     [rax], si
0x1800143c1  mov     rdx, [rsp+198h+var_48]
0x1800143c9  cmp     rdx, 7
0x1800143cd  ja      loc_180014DAB
0x1800143d3  lea     rcx, [rsp+198h+lpFileName]
0x1800143db  cmp     qword ptr [rsp+198h+var_70+8], 7
0x1800143e4  cmova   rcx, [rsp+198h+lpFileName]; lpFileName
0x1800143ed  mov     [rsp+198h+hTemplateFile], rsi; hTemplateFile
0x1800143f2  mov     dword ptr [rsp+198h+lpcbData], esi; dwFlagsAndAttributes
0x1800143f6  mov     dword ptr [rsp+198h+phkResult], 3; dwCreationDisposition
0x1800143fe  xor     r9d, r9d; lpSecurityAttributes
0x180014401  xor     r8d, r8d; dwShareMode
0x180014404  xor     edx, edx; dwDesiredAccess
0x180014406  call    cs:__imp_CreateFileW
0x18001440c  mov     r15, rax
0x18001440f  mov     qword ptr [rsp+198h+cchValueName], rax
0x180014414  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180014418  jz      loc_180014755
0x18001441e  mov     [rsp+198h+Type], esi
0x180014422  lea     rax, [rsp+198h+Type]
0x180014427  mov     [rsp+198h+phkResult], rax; ReturnLength
0x18001442c  xor     r9d, r9d; ObjectInformationLength
0x18001442f  xor     r8d, r8d; ObjectInformation
0x180014432  mov     edx, 1; ObjectInformationClass
0x180014437  mov     rcx, r15; Handle
0x18001443a  call    cs:__imp_NtQueryObject
0x180014440  mov     rbx, rsi
0x180014443  mov     [rsp+198h+var_118], rbx
0x18001444b  lea     rcx, [rsp+198h+var_118]
0x180014453  mov     qword ptr [rsp+198h+var_60], rcx
0x18001445b  mov     byte ptr [rsp+198h+var_60+8], 1
0x180014463  cmp     eax, 0C0000004h
0x180014468  jnz     short loc_18001449E
0x18001446a  mov     ecx, [rsp+198h+Type]; unsigned __int64
0x18001446e  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180014473  mov     [rsp+198h+var_118], rax
0x18001447b  mov     [rsp+198h+phkResult], rsi; int
0x180014480  mov     r9d, [rsp+198h+Type]; ObjectInformationLength
0x180014485  mov     r8, rax; ObjectInformation
0x180014488  mov     edx, 1; ObjectInformationClass
0x18001448d  mov     rcx, r15; Handle
0x180014490  call    cs:__imp_NtQueryObject
0x180014496  mov     rbx, [rsp+198h+var_118]
0x18001449e  test    eax, eax
0x1800144a0  js      loc_180014747
0x1800144a6  test    rbx, rbx
0x1800144a9  jz      loc_180014747
0x1800144af  movzx   r8d, word ptr [rbx]
0x1800144b3  add     r8, 2
0x1800144b7  lea     rcx, [rsp+198h+hKey]
0x1800144bc  call    ??$make_unique_string@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1800144c1  nop
0x1800144c2  mov     rcx, [rsp+198h+hKey]; void *
0x1800144c7  test    rcx, rcx
0x1800144ca  jz      loc_180014CCF
0x1800144d0  movzx   r8d, word ptr [rbx]; Size
0x1800144d4  mov     rdx, [rbx+8]; Src
0x1800144d8  call    memcpy_0
0x1800144dd  movzx   r8d, word ptr [rbx]
0x1800144e1  mov     rax, [rsp+198h+hKey]
0x1800144e6  mov     [rax+r8*2], si
0x1800144eb  mov     [rsp+198h+var_100], rsi
0x1800144f3  lea     rax, [rsp+198h+var_100]
0x1800144fb  mov     [rsp+198h+phkResult], rax; phkResult
0x180014500  mov     r9d, 1; samDesired
0x180014506  xor     r8d, r8d; ulOptions
0x180014509  lea     rdx, aSystemCurrentc_2; "System\\CurrentControlSet\\Control\\Hiv"...
0x180014510  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180014517  call    cs:__imp_RegOpenKeyExW
0x18001451d  test    eax, eax
0x18001451f  jnz     loc_180014AC7
0x180014525  mov     [rsp+198h+cValues], esi
0x18001452c  mov     [rsp+198h+cbData], esi
0x180014530  mov     [rsp+198h+cbMaxValueLen], esi
0x180014537  mov     [rsp+198h+lpftLastWriteTime], rsi; lpftLastWriteTime
0x18001453c  mov     [rsp+198h+lpcbSecurityDescriptor], rsi; lpcbSecurityDescriptor
0x180014541  lea     rax, [rsp+198h+cbMaxValueLen]
0x180014549  mov     [rsp+198h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x18001454e  lea     rax, [rsp+198h+cbData]
0x180014553  mov     [rsp+198h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x180014558  lea     rax, [rsp+198h+cValues]
0x180014560  mov     [rsp+198h+lpcValues], rax; lpcValues
0x180014565  mov     [rsp+198h+hTemplateFile], rsi; lpcbMaxClassLen
0x18001456a  mov     [rsp+198h+lpcbData], rsi; lpcbMaxSubKeyLen
0x18001456f  mov     [rsp+198h+phkResult], rsi; int
0x180014574  xor     r9d, r9d; lpReserved
0x180014577  xor     r8d, r8d; lpcchClass
0x18001457a  xor     edx, edx; lpClass
0x18001457c  mov     rcx, [rsp+198h+var_100]; hKey
0x180014584  call    cs:__imp_RegQueryInfoKeyW
0x18001458a  test    eax, eax
0x18001458c  jnz     loc_180014B06
0x180014592  mov     r8d, [rsp+198h+cbData]
0x180014597  add     r8, r8
0x18001459a  lea     rcx, [rsp+198h+lpValueName]
0x1800145a2  call    ??$make_unique_string@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1800145a7  nop
0x1800145a8  cmp     [rsp+198h+lpValueName], 0
0x1800145b1  jz      loc_180014BAD
0x1800145b7  mov     r8d, [rsp+198h+cbMaxValueLen]
0x1800145bf  lea     rcx, [rsp+198h+lpMem]
0x1800145c7  call    ??$make_unique_string@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1800145cc  mov     rsi, [rsp+198h+lpMem]
0x1800145d4  test    rsi, rsi
0x1800145d7  jnz     loc_180014992
0x1800145dd  mov     rcx, [rsp+198h]; this
0x1800145e5  mov     r9d, 8007000Eh; char *
0x1800145eb  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800145f2  mov     edx, 2A7h; void *
0x1800145f7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800145fc  mov     rbx, [rsp+198h+lpMem]
0x180014604  test    rbx, rbx
0x180014607  jz      short loc_18001461E
0x180014609  call    cs:__imp_GetProcessHeap
0x18001460f  mov     rcx, rax; hHeap
0x180014612  mov     r8, rbx; lpMem
0x180014615  xor     edx, edx; dwFlags
0x180014617  call    cs:__imp_HeapFree
0x18001461d  nop
0x18001461e  mov     rbx, [rsp+198h+lpValueName]
0x180014626  test    rbx, rbx
0x180014629  jz      short loc_180014640
0x18001462b  call    cs:__imp_GetProcessHeap
0x180014631  mov     rcx, rax; hHeap
0x180014634  mov     r8, rbx; lpMem
0x180014637  xor     edx, edx; dwFlags
0x180014639  call    cs:__imp_HeapFree
0x18001463f  nop
0x180014640  mov     rcx, [rsp+198h+var_100]; hKey
0x180014648  test    rcx, rcx
0x18001464b  jz      short loc_180014654
0x18001464d  call    cs:__imp_RegCloseKey
0x180014653  nop
0x180014654  mov     rbx, [rsp+198h+hKey]
0x180014659  test    rbx, rbx
0x18001465c  jz      short loc_180014673
0x18001465e  call    cs:__imp_GetProcessHeap
0x180014664  mov     rcx, rax; hHeap
0x180014667  mov     r8, rbx; lpMem
0x18001466a  xor     edx, edx; dwFlags
0x18001466c  call    cs:__imp_HeapFree
0x180014672  nop
0x180014673  mov     rcx, [rsp+198h+var_118]; void *
0x18001467b  test    rcx, rcx
0x18001467e  jz      short loc_180014686
0x180014680  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180014685  nop
0x180014686  lea     rax, [r15-1]
0x18001468a  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001468e  jbe     loc_180014DC5
  ... truncated ...
```
