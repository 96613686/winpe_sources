# MprConfigServerBackup

- ea: `0x180025e20`
- end: `0x1800265ad`
- name: `MprConfigServerBackup`
- size: `1933`
- prototype: `DWORD __stdcall(HANDLE hMprConfig, LPWSTR lpwsPath)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x1800097e8`
- `0x180009868`
- `0x180017700`
- `0x180017df8`
- `0x180025e20`
- `0x180027d5c`
- `0x180029224`
- `0x1800294a4`
- `0x18005112a`
- `0x180051160`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180025f88`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180026567`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180025f88`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180026567`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180025e8d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180025e8d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026184`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026251`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002651f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026184`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026251`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002651f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180025f5d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800260a1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800260d2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002612f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800261d1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800261e5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180026275`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180026347`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180026363`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180026525`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180026539`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002656d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180025f5d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800260a1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800260d2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002612f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800261d1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800261e5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180026275`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180026347`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180026363`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180026525`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180026539`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002656d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180025f6b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800260af`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800260e0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002613d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180026283`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180026355`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180025f6b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800260af`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800260e0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002613d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180026283`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180026355`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800261df`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800261f3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180026533`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180026547`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002657b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800261df`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800261f3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180026533`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180026547`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002657b`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x18002639c`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x18002639c`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180025fd1`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18002600e`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18002604f`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180025fd1`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18002600e`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18002604f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800261ae`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180026245`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800261ae`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180026245`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800261c1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002625f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800261c1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002625f`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x180026178`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x180026178`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x180025e9f`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x180025e9f`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180025ec8`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180025ec8`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180025f42`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180025f4d`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180026094`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800260c5`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180026111`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180026120`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180026268`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800262b2`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800262be`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800262cf`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800262db`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800262eb`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800262f6`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180026306`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180026313`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180026322`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180025f42`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180025f4d`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180026094`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800260c5`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180026111`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180026120`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180026268`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800262b2`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800262be`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800262cf`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800262db`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800262eb`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800262f6`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180026306`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180026313`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180026322`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenA` at `0x1800263ef`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenA` at `0x180026435`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenA` at `0x18002647a`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenA` at `0x1800264bf`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenA` at `0x1800263ef`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenA` at `0x180026435`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenA` at `0x18002647a`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenA` at `0x1800264bf`
- `api-ms-win-core-privateprofile-l1-1-0!WritePrivateProfileSectionA` at `0x180026515`
- `api-ms-win-core-privateprofile-l1-1-0!WritePrivateProfileSectionA` at `0x180026515`
- `api-ms-win-core-registry-l2-1-0!RegSaveKeyW` at `0x180025fe0`
- `api-ms-win-core-registry-l2-1-0!RegSaveKeyW` at `0x18002601e`
- `api-ms-win-core-registry-l2-1-0!RegSaveKeyW` at `0x180025fe0`
- `api-ms-win-core-registry-l2-1-0!RegSaveKeyW` at `0x18002601e`

## string_xrefs

- `0x180026117`: `\ADMIN$\System32\RAS\Router.pbk`
- `0x18002614f`: `\ADMIN$\System32\RAS\Router.pbk`
- `0x180026508`: `MprConfig`
- `0x180026319`: `ConfigVersion`
- `0x1800264d9`: `ConfigVersion`

## pseudocode

```c
DWORD __stdcall MprConfigServerBackup(HANDLE hMprConfig, LPWSTR lpwsPath)
{
  DWORD result; // eax
  DWORD v5; // ebx
  const WCHAR *v6; // rcx
  int v7; // ebx
  size_t v8; // r12
  HANDLE ProcessHeap; // rax
  void *v10; // rdi
  const WCHAR *v11; // rcx
  size_t v12; // rbx
  HANDLE v13; // rax
  wchar_t *v14; // r15
  WCHAR *v15; // rax
  HANDLE v16; // rax
  int v17; // ebx
  unsigned int v18; // esi
  HANDLE v19; // rax
  wchar_t *v20; // rbx
  BOOL v21; // esi
  HANDLE FileW; // rax
  HANDLE v23; // rax
  HANDLE v24; // rax
  HANDLE v25; // rax
  unsigned int v26; // ebx
  HANDLE v27; // rax
  CHAR *v28; // rax
  int v29; // r13d
  int v30; // r15d
  int v31; // r12d
  int v32; // esi
  int v33; // r14d
  int v34; // ebx
  int v35; // edi
  SIZE_T v36; // rbx
  HANDLE v37; // rax
  char *v38; // rax
  char *v39; // rsi
  HANDLE v40; // rax
  CHAR *v41; // r8
  const wchar_t *v42; // rdi
  char *v43; // rbx
  char *v44; // rbx
  char *v45; // rbx
  int v46; // eax
  LPCSTR v47; // rbx
  HANDLE v48; // rax
  HANDLE v49; // rax
  size_t pcbRemaining; // [rsp+50h] [rbp-B0h] BYREF
  DWORD nSize; // [rsp+58h] [rbp-A8h] BYREF
  LPCWSTR lpString; // [rsp+60h] [rbp-A0h]
  LPCSTR lpFileName; // [rsp+68h] [rbp-98h]
  LPVOID v54; // [rsp+70h] [rbp-90h]
  _OSVERSIONINFOW VersionInformation; // [rsp+80h] [rbp-80h] BYREF
  WCHAR Buffer[128]; // [rsp+1A0h] [rbp+A0h] BYREF

  lpString = lpwsPath;
  nSize = 128;
  memset_0(&VersionInformation, 0, sizeof(VersionInformation));
  result = MprConfigServerValidateCb(hMprConfig);
  if ( !result )
  {
    EnterCriticalSection(&CfgLock);
    if ( !GetComputerNameW(Buffer, &nSize) )
    {
      v5 = 1003;
LABEL_16:
      LeaveCriticalSection(&CfgLock);
      return v5;
    }
    v6 = (const WCHAR *)*((_QWORD *)hMprConfig + 1);
    if ( v6 && !*v6 && lstrcmpiW(v6, Buffer) )
    {
      v5 = 50;
      goto LABEL_16;
    }
    if ( !*((_QWORD *)hMprConfig + 7) )
      AccessRouterSubkey(*((HKEY *)hMprConfig + 2), L"Interfaces");
    if ( !*((_QWORD *)hMprConfig + 5) )
      AccessRouterSubkey(*((HKEY *)hMprConfig + 2), L"RouterManagers");
    if ( !*((_QWORD *)hMprConfig + 3) )
      AccessRouterSubkey(*((HKEY *)hMprConfig + 2), L"Parameters");
    v7 = lstrlenW(lpwsPath);
    v8 = (unsigned int)(2 * (lstrlenW(L"RouterManagers") + v7) + 2);
    ProcessHeap = GetProcessHeap();
    v54 = HeapAlloc(ProcessHeap, 0, (unsigned int)v8);
    v10 = v54;
    if ( !v54 )
    {
      v5 = 8;
      goto LABEL_16;
    }
    v5 = EnableBackupPrivilege(1);
    if ( v5 )
    {
LABEL_43:
      LeaveCriticalSection(&CfgLock);
      v49 = GetProcessHeap();
      HeapFree(v49, 0, v10);
      return v5;
    }
    StringCbPrintfW((STRSAFE_LPWSTR)v10, v8, L"%s%s", lpwsPath, L"Parameters");
    DeleteFileW((LPCWSTR)v10);
    if ( RegSaveKeyW(*((HKEY *)hMprConfig + 3), (LPCWSTR)v10, 0) )
      goto LABEL_42;
    StringCbPrintfW((STRSAFE_LPWSTR)v10, v8, L"%s%s", lpwsPath, L"RouterManagers");
    DeleteFileW((LPCWSTR)v10);
    if ( RegSaveKeyW(*((HKEY *)hMprConfig + 5), (LPCWSTR)v10, 0) )
      goto LABEL_42;
    StringCbPrintfW((STRSAFE_LPWSTR)v10, v8, L"%s%s", lpwsPath, L"Interfaces");
    DeleteFileW((LPCWSTR)v10);
    if ( (unsigned int)TranslateAndSaveInterfaceKey(hMprConfig, (LPCWSTR)v10) )
      goto LABEL_42;
    StringCbPrintfW((STRSAFE_LPWSTR)v10, v8, L"%s%s", lpwsPath, L"Phonebook");
    v11 = (const WCHAR *)*((_QWORD *)hMprConfig + 1);
    if ( v11 && *v11 )
    {
      v12 = (unsigned int)(2 * lstrlenW(v11) + 6);
      v13 = GetProcessHeap();
      v14 = (wchar_t *)HeapAlloc(v13, 0, (unsigned int)v12);
      v15 = (WCHAR *)*((_QWORD *)hMprConfig + 1);
    }
    else
    {
      v12 = (unsigned int)(2 * lstrlenW(Buffer) + 6);
      v16 = GetProcessHeap();
      v14 = (wchar_t *)HeapAlloc(v16, 0, (unsigned int)v12);
      v15 = Buffer;
    }
    StringCbPrintfW(v14, v12, L"%s%s", L"\\\\", v15);
    v17 = lstrlenW(v14);
    v18 = 2 * (lstrlenW(L"\\ADMIN$\\System32\\RAS\\Router.pbk") + v17) + 2;
    v19 = GetProcessHeap();
    v20 = (wchar_t *)HeapAlloc(v19, 0, v18);
    if ( !v20 )
    {
LABEL_42:
      v5 = EnableBackupPrivilege(0);
      goto LABEL_43;
    }
    StringCbPrintfW(v20, v18, L"%s%s", v14, L"\\ADMIN$\\System32\\RAS\\Router.pbk");
    v21 = CopyFileW(v20, (LPCWSTR)v10, 0);
    if ( !v21 && GetLastError() == 2 )
    {
      FileW = CreateFileW((LPCWSTR)v10, 0x40000000u, 0, 0, 2u, 0x80u, 0);
      if ( FileW == (HANDLE)-1LL )
      {
LABEL_34:
        GetLastError();
        goto LABEL_42;
      }
      CloseHandle(FileW);
      v21 = 1;
    }
    if ( v14 )
    {
      v23 = GetProcessHeap();
      HeapFree(v23, 0, v14);
    }
    v24 = GetProcessHeap();
    HeapFree(v24, 0, v20);
    if ( !v21 )
      goto LABEL_42;
    StringCbPrintfW((STRSAFE_LPWSTR)v10, v8, L"%s%s", lpwsPath, L".mpr");
    v25 = CreateFileW((LPCWSTR)v10, 0x40000000u, 0, 0, 2u, 0x80u, 0);
    if ( v25 != (HANDLE)-1LL )
    {
      CloseHandle(v25);
      v26 = 2 * lstrlenW((LPCWSTR)v10) + 2;
      v27 = GetProcessHeap();
      v28 = (CHAR *)HeapAlloc(v27, 0, v26);
      lpFileName = v28;
      if ( v28 )
      {
        StringCbPrintfA(v28, v26, "%ls", (const wchar_t *)v10);
        v29 = lstrlenW(L"Parameters");
        LODWORD(pcbRemaining) = lstrlenW(lpwsPath);
        v30 = lstrlenW(L"RouterManagers");
        v31 = lstrlenW(lpwsPath);
        v32 = lstrlenW(L"Interfaces");
        v33 = lstrlenW(lpwsPath);
        v34 = lstrlenW(L"Phonebook");
        v35 = lstrlenW(lpString);
        v36 = 2 * ((int)pcbRemaining + v31 + v33 + v35 + 2 * (v29 + v30 + v32 + 8 + v34 + lstrlenW(L"ConfigVersion")));
        v37 = GetProcessHeap();
        v38 = (char *)HeapAlloc(v37, 0, v36);
        v39 = v38;
        if ( v38 )
        {
          memset_0(v38, 0, v36);
          memset_0(&VersionInformation.dwMajorVersion, 0, 0x110u);
          VersionInformation.dwOSVersionInfoSize = 276;
          GetVersionExW(&VersionInformation);
          v42 = lpString;
          pcbRemaining = v36;
          StringCbPrintfExA(v39, v36, 0, &pcbRemaining, 0x800u, "%ls=%ls%ls", L"Parameters", lpString, L"Parameters");
          v43 = &v39[lstrlenA(v39) + 1];
          StringCbPrintfExA(
            v43,
            pcbRemaining,
            0,
            &pcbRemaining,
            0x800u,
            "%ls=%ls%ls",
            L"RouterManagers",
            v42,
            L"RouterManagers");
          v44 = &v43[lstrlenA(v43) + 1];
          StringCbPrintfExA(
            v44,
            pcbRemaining,
            0,
            &pcbRemaining,
            0x800u,
            "%ls=%ls%ls",
            L"Interfaces",
            v42,
            L"Interfaces");
          v45 = &v44[lstrlenA(v44) + 1];
          StringCbPrintfExA(v45, pcbRemaining, 0, &pcbRemaining, 0x800u, "%ls=%ls%ls", L"Phonebook", v42, L"Phonebook");
          v46 = lstrlenA(v45);
          StringCbPrintfExA(
            &v45[v46 + 1],
            pcbRemaining,
            0,
            &pcbRemaining,
            0x800u,
            "%ls=%d",
            L"ConfigVersion",
            VersionInformation.dwBuildNumber);
          v47 = lpFileName;
          if ( !WritePrivateProfileSectionA("MprConfig", v39, lpFileName) )
            GetLastError();
          v48 = GetProcessHeap();
          HeapFree(v48, 0, v39);
          v40 = GetProcessHeap();
          v41 = (CHAR *)v47;
        }
        else
        {
          v40 = GetProcessHeap();
          v41 = (CHAR *)lpFileName;
        }
        HeapFree(v40, 0, v41);
        v10 = v54;
      }
      goto LABEL_42;
    }
    goto LABEL_34;
  }
  return result;
}

```

## disassembly

```asm
0x180025e20  mov     [rsp-8+arg_10], rbx
0x180025e25  push    rbp
0x180025e26  push    rsi
0x180025e27  push    rdi
0x180025e28  push    r12
0x180025e2a  push    r13
0x180025e2c  push    r14
0x180025e2e  push    r15
0x180025e30  lea     rbp, [rsp-1B0h]
0x180025e38  sub     rsp, 2B0h
0x180025e3f  mov     rax, cs:__security_cookie
0x180025e46  xor     rax, rsp
0x180025e49  mov     [rbp+1E0h+var_40], rax
0x180025e50  mov     r14, rdx
0x180025e53  mov     [rsp+2E0h+lpString], rdx
0x180025e58  mov     rsi, rcx
0x180025e5b  mov     [rsp+2E0h+nSize], 80h
0x180025e63  xor     edx, edx; Val
0x180025e65  lea     rcx, [rbp+1E0h+VersionInformation]; void *
0x180025e69  mov     r8d, 114h; Size
0x180025e6f  call    memset_0
0x180025e74  mov     rcx, rsi
0x180025e77  call    MprConfigServerValidateCb
0x180025e7c  xor     ebx, ebx
0x180025e7e  test    eax, eax
0x180025e80  jnz     loc_180026583
0x180025e86  lea     rcx, CfgLock; lpCriticalSection
0x180025e8d  call    cs:__imp_EnterCriticalSection
0x180025e93  lea     rdx, [rsp+2E0h+nSize]; nSize
0x180025e98  lea     rcx, [rbp+1E0h+Buffer]; lpBuffer
0x180025e9f  call    cs:__imp_GetComputerNameW
0x180025ea5  test    eax, eax
0x180025ea7  jnz     short loc_180025EB3
0x180025ea9  mov     ebx, 3EBh
0x180025eae  jmp     loc_180025F81
0x180025eb3  mov     rcx, [rsi+8]; lpString1
0x180025eb7  test    rcx, rcx
0x180025eba  jz      short loc_180025EDC
0x180025ebc  cmp     [rcx], bx
0x180025ebf  jnz     short loc_180025EDC
0x180025ec1  lea     rdx, [rbp+1E0h+Buffer]; lpString2
0x180025ec8  call    cs:__imp_lstrcmpiW
0x180025ece  test    eax, eax
0x180025ed0  jz      short loc_180025EDC
0x180025ed2  mov     ebx, 32h ; '2'
0x180025ed7  jmp     loc_180025F81
0x180025edc  lea     r9, [rsi+38h]
0x180025ee0  mov     edi, 1
0x180025ee5  cmp     [r9], rbx
0x180025ee8  jnz     short loc_180025EFD
0x180025eea  mov     rcx, [rsi+10h]; hKey
0x180025eee  lea     rdx, c_szInterfaces; "Interfaces"
0x180025ef5  mov     r8d, edi
0x180025ef8  call    AccessRouterSubkey
0x180025efd  lea     r13, [rsi+28h]
0x180025f01  lea     r12, c_szRouterManagers; "RouterManagers"
0x180025f08  cmp     [r13+0], rbx
0x180025f0c  jnz     short loc_180025F20
0x180025f0e  mov     rcx, [rsi+10h]; hKey
0x180025f12  mov     r9, r13
0x180025f15  mov     r8d, edi
0x180025f18  mov     rdx, r12; lpSubKey
0x180025f1b  call    AccessRouterSubkey
0x180025f20  lea     r15, [rsi+18h]
0x180025f24  cmp     [r15], rbx
0x180025f27  jnz     short loc_180025F3F
0x180025f29  mov     rcx, [rsi+10h]; hKey
0x180025f2d  lea     rdx, c_szParameters; "Parameters"
0x180025f34  mov     r9, r15
0x180025f37  mov     r8d, edi
0x180025f3a  call    AccessRouterSubkey
0x180025f3f  mov     rcx, r14; lpString
0x180025f42  call    cs:__imp_lstrlenW
0x180025f48  mov     rcx, r12; lpString
0x180025f4b  mov     ebx, eax
0x180025f4d  call    cs:__imp_lstrlenW
0x180025f53  add     ebx, eax
0x180025f55  lea     r12d, ds:2[rbx*2]
0x180025f5d  call    cs:__imp_GetProcessHeap
0x180025f63  mov     r8d, r12d; dwBytes
0x180025f66  xor     edx, edx; dwFlags
0x180025f68  mov     rcx, rax; hHeap
0x180025f6b  call    cs:__imp_HeapAlloc
0x180025f71  mov     [rsp+2E0h+var_270], rax
0x180025f76  mov     rdi, rax
0x180025f79  test    rax, rax
0x180025f7c  jnz     short loc_180025F93
0x180025f7e  lea     ebx, [rax+8]
0x180025f81  lea     rcx, CfgLock; lpCriticalSection
0x180025f88  call    cs:__imp_LeaveCriticalSection
0x180025f8e  jmp     loc_180026581
0x180025f93  mov     edx, 11h
0x180025f98  lea     ecx, [rdx-10h]
0x180025f9b  call    EnableBackupPrivilege
0x180025fa0  mov     ebx, eax
0x180025fa2  test    eax, eax
0x180025fa4  jnz     loc_180026560
0x180025faa  lea     rax, c_szParameters; "Parameters"
0x180025fb1  mov     r9, r14
0x180025fb4  lea     rbx, aSS_1; "%s%s"
0x180025fbb  mov     qword ptr [rsp+2E0h+dwCreationDisposition], rax
0x180025fc0  mov     r8, rbx; pszFormat
0x180025fc3  mov     rdx, r12; cbDest
0x180025fc6  mov     rcx, rdi; pszDest
0x180025fc9  call    StringCbPrintfW
0x180025fce  mov     rcx, rdi; lpFileName
0x180025fd1  call    cs:__imp_DeleteFileW
0x180025fd7  mov     rcx, [r15]; hKey
0x180025fda  xor     r8d, r8d; lpSecurityAttributes
0x180025fdd  mov     rdx, rdi; lpFile
0x180025fe0  call    cs:__imp_RegSaveKeyW
0x180025fe6  test    eax, eax
0x180025fe8  jnz     loc_180026552
0x180025fee  lea     rax, c_szRouterManagers; "RouterManagers"
0x180025ff5  mov     r9, r14
0x180025ff8  mov     r8, rbx; pszFormat
0x180025ffb  mov     qword ptr [rsp+2E0h+dwCreationDisposition], rax
0x180026000  mov     rdx, r12; cbDest
0x180026003  mov     rcx, rdi; pszDest
0x180026006  call    StringCbPrintfW
0x18002600b  mov     rcx, rdi; lpFileName
0x18002600e  call    cs:__imp_DeleteFileW
0x180026014  mov     rcx, [r13+0]; hKey
0x180026018  xor     r8d, r8d; lpSecurityAttributes
0x18002601b  mov     rdx, rdi; lpFile
0x18002601e  call    cs:__imp_RegSaveKeyW
0x180026024  xor     r13d, r13d
0x180026027  test    eax, eax
0x180026029  jnz     loc_180026552
0x18002602f  lea     rax, c_szInterfaces; "Interfaces"
0x180026036  mov     r9, r14
0x180026039  mov     r8, rbx; pszFormat
0x18002603c  mov     qword ptr [rsp+2E0h+dwCreationDisposition], rax
0x180026041  mov     rdx, r12; cbDest
0x180026044  mov     rcx, rdi; pszDest
0x180026047  call    StringCbPrintfW
0x18002604c  mov     rcx, rdi; lpFileName
0x18002604f  call    cs:__imp_DeleteFileW
0x180026055  mov     rdx, rdi; lpFile
0x180026058  mov     rcx, rsi; hMprConfig
0x18002605b  call    TranslateAndSaveInterfaceKey
0x180026060  test    eax, eax
0x180026062  jnz     loc_180026552
0x180026068  lea     rax, c_szPhonebook; "Phonebook"
0x18002606f  mov     r9, r14
0x180026072  mov     r8, rbx; pszFormat
0x180026075  mov     qword ptr [rsp+2E0h+dwCreationDisposition], rax
0x18002607a  mov     rdx, r12; cbDest
0x18002607d  mov     rcx, rdi; pszDest
0x180026080  call    StringCbPrintfW
0x180026085  mov     rcx, [rsi+8]; lpString
0x180026089  test    rcx, rcx
0x18002608c  jz      short loc_1800260BE
0x18002608e  cmp     [rcx], r13w
0x180026092  jz      short loc_1800260BE
0x180026094  call    cs:__imp_lstrlenW
0x18002609a  lea     ebx, ds:6[rax*2]
0x1800260a1  call    cs:__imp_GetProcessHeap
0x1800260a7  mov     r8d, ebx; dwBytes
0x1800260aa  xor     edx, edx; dwFlags
0x1800260ac  mov     rcx, rax; hHeap
0x1800260af  call    cs:__imp_HeapAlloc
0x1800260b5  mov     r15, rax
0x1800260b8  mov     rax, [rsi+8]
0x1800260bc  jmp     short loc_1800260F0
0x1800260be  lea     rcx, [rbp+1E0h+Buffer]; lpString
0x1800260c5  call    cs:__imp_lstrlenW
0x1800260cb  lea     ebx, ds:6[rax*2]
0x1800260d2  call    cs:__imp_GetProcessHeap
0x1800260d8  mov     r8d, ebx; dwBytes
0x1800260db  xor     edx, edx; dwFlags
0x1800260dd  mov     rcx, rax; hHeap
0x1800260e0  call    cs:__imp_HeapAlloc
0x1800260e6  mov     r15, rax
0x1800260e9  lea     rax, [rbp+1E0h+Buffer]
0x1800260f0  lea     r9, c_szUncPrefix; "\\\\"
0x1800260f7  mov     qword ptr [rsp+2E0h+dwCreationDisposition], rax
0x1800260fc  lea     r8, aSS_1; "%s%s"
0x180026103  mov     rdx, rbx; cbDest
0x180026106  mov     rcx, r15; pszDest
0x180026109  call    StringCbPrintfW
0x18002610e  mov     rcx, r15; lpString
0x180026111  call    cs:__imp_lstrlenW
0x180026117  lea     rcx, c_szRouterPbkPath; "\\ADMIN$\\System32\\RAS\\Router.pbk"
0x18002611e  mov     ebx, eax
0x180026120  call    cs:__imp_lstrlenW
0x180026126  add     ebx, eax
0x180026128  lea     esi, ds:2[rbx*2]
0x18002612f  call    cs:__imp_GetProcessHeap
0x180026135  mov     r8d, esi; dwBytes
0x180026138  xor     edx, edx; dwFlags
0x18002613a  mov     rcx, rax; hHeap
0x18002613d  call    cs:__imp_HeapAlloc
0x180026143  mov     rbx, rax
0x180026146  test    rax, rax
0x180026149  jz      loc_180026552
0x18002614f  lea     rax, c_szRouterPbkPath; "\\ADMIN$\\System32\\RAS\\Router.pbk"
0x180026156  mov     r9, r15
0x180026159  lea     r8, aSS_1; "%s%s"
0x180026160  mov     qword ptr [rsp+2E0h+dwCreationDisposition], rax
0x180026165  mov     edx, esi; cbDest
0x180026167  mov     rcx, rbx; pszDest
0x18002616a  call    StringCbPrintfW
0x18002616f  xor     r8d, r8d; bFailIfExists
0x180026172  mov     rdx, rdi; lpNewFileName
0x180026175  mov     rcx, rbx; lpExistingFileName
0x180026178  call    cs:__imp_CopyFileW
0x18002617e  mov     esi, eax
0x180026180  test    eax, eax
0x180026182  jnz     short loc_1800261CC
0x180026184  call    cs:__imp_GetLastError
0x18002618a  cmp     eax, 2
0x18002618d  jnz     short loc_1800261CC
0x18002618f  mov     [rsp+2E0h+hTemplateFile], r13; hTemplateFile
0x180026194  xor     r9d, r9d; lpSecurityAttributes
0x180026197  mov     [rsp+2E0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18002619f  xor     r8d, r8d; dwShareMode
0x1800261a2  mov     edx, 40000000h; dwDesiredAccess
0x1800261a7  mov     [rsp+2E0h+dwCreationDisposition], eax; dwCreationDisposition
0x1800261ab  mov     rcx, rdi; lpFileName
0x1800261ae  call    cs:__imp_CreateFileW
0x1800261b4  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800261b8  jz      loc_180026251
0x1800261be  mov     rcx, rax; hObject
0x1800261c1  call    cs:__imp_CloseHandle
0x1800261c7  mov     esi, 1
0x1800261cc  test    r15, r15
0x1800261cf  jz      short loc_1800261E5
0x1800261d1  call    cs:__imp_GetProcessHeap
0x1800261d7  mov     r8, r15; lpMem
0x1800261da  xor     edx, edx; dwFlags
0x1800261dc  mov     rcx, rax; hHeap
0x1800261df  call    cs:__imp_HeapFree
0x1800261e5  call    cs:__imp_GetProcessHeap
0x1800261eb  mov     r8, rbx; lpMem
0x1800261ee  xor     edx, edx; dwFlags
0x1800261f0  mov     rcx, rax; hHeap
0x1800261f3  call    cs:__imp_HeapFree
0x1800261f9  test    esi, esi
0x1800261fb  jz      loc_180026552
0x180026201  lea     rax, c_szMpr; ".mpr"
0x180026208  mov     r9, r14
0x18002620b  lea     r8, aSS_1; "%s%s"
0x180026212  mov     qword ptr [rsp+2E0h+dwCreationDisposition], rax
0x180026217  mov     rdx, r12; cbDest
0x18002621a  mov     rcx, rdi; pszDest
0x18002621d  call    StringCbPrintfW
0x180026222  mov     [rsp+2E0h+hTemplateFile], r13; hTemplateFile
0x180026227  xor     r9d, r9d; lpSecurityAttributes
0x18002622a  mov     [rsp+2E0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180026232  xor     r8d, r8d; dwShareMode
0x180026235  mov     edx, 40000000h; dwDesiredAccess
0x18002623a  mov     [rsp+2E0h+dwCreationDisposition], 2; dwCreationDisposition
0x180026242  mov     rcx, rdi; lpFileName
0x180026245  call    cs:__imp_CreateFileW
0x18002624b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002624f  jnz     short loc_18002625C
0x180026251  call    cs:__imp_GetLastError
0x180026257  jmp     loc_180026552
0x18002625c  mov     rcx, rax; hObject
0x18002625f  call    cs:__imp_CloseHandle
0x180026265  mov     rcx, rdi; lpString
0x180026268  call    cs:__imp_lstrlenW
0x18002626e  lea     ebx, ds:2[rax*2]
0x180026275  call    cs:__imp_GetProcessHeap
0x18002627b  mov     r8d, ebx; dwBytes
0x18002627e  xor     edx, edx; dwFlags
0x180026280  mov     rcx, rax; hHeap
0x180026283  call    cs:__imp_HeapAlloc
0x180026289  mov     [rsp+2E0h+lpFileName], rax
0x18002628e  test    rax, rax
0x180026291  jz      loc_180026552
0x180026297  mov     r9, rdi
0x18002629a  lea     r8, aLs; "%ls"
0x1800262a1  mov     edx, ebx; cbDest
0x1800262a3  mov     rcx, rax; pszDest
0x1800262a6  call    StringCbPrintfA
0x1800262ab  lea     rcx, c_szParameters; "Parameters"
0x1800262b2  call    cs:__imp_lstrlenW
0x1800262b8  mov     rcx, r14; lpString
0x1800262bb  mov     r13d, eax
0x1800262be  call    cs:__imp_lstrlenW
0x1800262c4  lea     rcx, c_szRouterManagers; "RouterManagers"
0x1800262cb  mov     dword ptr [rsp+2E0h+pcbRemaining], eax
0x1800262cf  call    cs:__imp_lstrlenW
0x1800262d5  mov     rcx, r14; lpString
0x1800262d8  mov     r15d, eax
0x1800262db  call    cs:__imp_lstrlenW
0x1800262e1  lea     rcx, c_szInterfaces; "Interfaces"
0x1800262e8  mov     r12d, eax
0x1800262eb  call    cs:__imp_lstrlenW
0x1800262f1  mov     rcx, r14; lpString
0x1800262f4  mov     esi, eax
0x1800262f6  call    cs:__imp_lstrlenW
0x1800262fc  lea     rcx, c_szPhonebook; "Phonebook"
0x180026303  mov     r14d, eax
0x180026306  call    cs:__imp_lstrlenW
0x18002630c  mov     rcx, [rsp+2E0h+lpString]; lpString
0x180026311  mov     ebx, eax
0x180026313  call    cs:__imp_lstrlenW
  ... truncated ...
```
