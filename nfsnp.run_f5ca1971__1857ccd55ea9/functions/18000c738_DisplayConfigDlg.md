# DisplayConfigDlg

- ea: `0x18000c738`
- end: `0x18000d4d7`
- name: `DisplayConfigDlg`
- size: `3487`
- prototype: ``
- caller_count: `1`
- callee_count: `35`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180004a40`

## callees

- `0x1800016c8`
- `0x1800017f4`
- `0x180001901`
- `0x18000190d`
- `0x18000c704`
- `0x18000c738`
- `0x18000d4e0`
- `0x18000d584`
- `0x18000d644`
- `0x18000da44`
- `0x18000e000`
- `0x18000e198`
- `0x18000e354`
- `0x18000e4a8`
- `0x18000e5f4`
- `0x18000e8ac`
- `0x18000ea28`
- `0x18000ec64`
- `0x18000eda4`
- `0x18000ef28`
- `0x18000f074`
- `0x18000f1c8`
- `0x18000f264`
- `0x18000f64c`
- `0x18000f774`
- `0x18000f89c`
- `0x18000f9f4`
- `0x180010144`
- `0x1800106fc`
- `0x180010bec`
- `0x180010eb8`
- `0x1800127a4`
- `0x180012e32`
- `0x180012e70`
- `0x180012f00`

## import_xrefs

- `msvcrt!wcscat_s` at `0x18000cb67`
- `msvcrt!wcscat_s` at `0x18000cb84`
- `msvcrt!wcscat_s` at `0x18000cc08`
- `msvcrt!wcscat_s` at `0x18000ce70`
- `msvcrt!wcscat_s` at `0x18000ce8d`
- `msvcrt!wcscat_s` at `0x18000cec7`
- `msvcrt!wcscat_s` at `0x18000d27c`
- `msvcrt!wcscat_s` at `0x18000d2f5`
- `msvcrt!wcscat_s` at `0x18000d313`
- `msvcrt!wcscat_s` at `0x18000cb67`
- `msvcrt!wcscat_s` at `0x18000cb84`
- `msvcrt!wcscat_s` at `0x18000cc08`
- `msvcrt!wcscat_s` at `0x18000ce70`
- `msvcrt!wcscat_s` at `0x18000ce8d`
- `msvcrt!wcscat_s` at `0x18000cec7`
- `msvcrt!wcscat_s` at `0x18000d27c`
- `msvcrt!wcscat_s` at `0x18000d2f5`
- `msvcrt!wcscat_s` at `0x18000d313`
- `msvcrt!wcscpy_s` at `0x18000caa2`
- `msvcrt!wcscpy_s` at `0x18000cb4a`
- `msvcrt!wcscpy_s` at `0x18000ce3b`
- `msvcrt!wcscpy_s` at `0x18000ce53`
- `msvcrt!wcscpy_s` at `0x18000ceaa`
- `msvcrt!wcscpy_s` at `0x18000d25e`
- `msvcrt!wcscpy_s` at `0x18000d2c2`
- `msvcrt!wcscpy_s` at `0x18000d2d7`
- `msvcrt!wcscpy_s` at `0x18000d37a`
- `msvcrt!wcscpy_s` at `0x18000caa2`
- `msvcrt!wcscpy_s` at `0x18000cb4a`
- `msvcrt!wcscpy_s` at `0x18000ce3b`
- `msvcrt!wcscpy_s` at `0x18000ce53`
- `msvcrt!wcscpy_s` at `0x18000ceaa`
- `msvcrt!wcscpy_s` at `0x18000d25e`
- `msvcrt!wcscpy_s` at `0x18000d2c2`
- `msvcrt!wcscpy_s` at `0x18000d2d7`
- `msvcrt!wcscpy_s` at `0x18000d37a`
- `KERNEL32!GetCurrentProcess` at `0x18000c81c`
- `KERNEL32!GetCurrentProcess` at `0x18000d0eb`
- `KERNEL32!GetCurrentProcess` at `0x18000c81c`
- `KERNEL32!GetCurrentProcess` at `0x18000d0eb`
- `KERNEL32!GetCurrentThread` at `0x18000d050`
- `KERNEL32!GetCurrentThread` at `0x18000d050`
- `KERNEL32!CloseHandle` at `0x18000d155`
- `KERNEL32!CloseHandle` at `0x18000d1e9`
- `KERNEL32!CloseHandle` at `0x18000d155`
- `KERNEL32!CloseHandle` at `0x18000d1e9`
- `KERNEL32!GetLastError` at `0x18000d083`
- `KERNEL32!GetLastError` at `0x18000d0d4`
- `KERNEL32!GetLastError` at `0x18000d083`
- `KERNEL32!GetLastError` at `0x18000d0d4`
- `KERNEL32!GetModuleHandleW` at `0x18000c934`
- `KERNEL32!GetModuleHandleW` at `0x18000c934`
- `ADVAPI32!GetTokenInformation` at `0x18000d140`
- `ADVAPI32!GetTokenInformation` at `0x18000d140`
- `ADVAPI32!OpenProcessToken` at `0x18000d10d`
- `ADVAPI32!OpenProcessToken` at `0x18000d10d`
- `ADVAPI32!OpenThreadToken` at `0x18000d0a4`
- `ADVAPI32!OpenThreadToken` at `0x18000d0c4`
- `ADVAPI32!OpenThreadToken` at `0x18000d0a4`
- `ADVAPI32!OpenThreadToken` at `0x18000d0c4`
- `ADVAPI32!RegOpenKeyW` at `0x18000cee4`
- `ADVAPI32!RegOpenKeyW` at `0x18000cf32`
- `ADVAPI32!RegOpenKeyW` at `0x18000cee4`
- `ADVAPI32!RegOpenKeyW` at `0x18000cf32`
- `ADVAPI32!LookupAccountSidW` at `0x18000d19b`
- `ADVAPI32!LookupAccountSidW` at `0x18000d19b`
- `ADVAPI32!RegCloseKey` at `0x18000cbc8`
- `ADVAPI32!RegCloseKey` at `0x18000cc4d`
- `ADVAPI32!RegCloseKey` at `0x18000cda5`
- `ADVAPI32!RegCloseKey` at `0x18000cefe`
- `ADVAPI32!RegCloseKey` at `0x18000cf4b`
- `ADVAPI32!RegCloseKey` at `0x18000cbc8`
- `ADVAPI32!RegCloseKey` at `0x18000cc4d`
- `ADVAPI32!RegCloseKey` at `0x18000cda5`
- `ADVAPI32!RegCloseKey` at `0x18000cefe`
- `ADVAPI32!RegCloseKey` at `0x18000cf4b`
- `ADVAPI32!RegQueryValueExW` at `0x18000cd5e`
- `ADVAPI32!RegQueryValueExW` at `0x18000cd94`
- `ADVAPI32!RegQueryValueExW` at `0x18000cd5e`
- `ADVAPI32!RegQueryValueExW` at `0x18000cd94`
- `ADVAPI32!RegOpenKeyExW` at `0x18000c876`
- `ADVAPI32!RegOpenKeyExW` at `0x18000cbaf`
- `ADVAPI32!RegOpenKeyExW` at `0x18000cc32`
- `ADVAPI32!RegOpenKeyExW` at `0x18000cd1d`
- `ADVAPI32!RegOpenKeyExW` at `0x18000c876`
- `ADVAPI32!RegOpenKeyExW` at `0x18000cbaf`
- `ADVAPI32!RegOpenKeyExW` at `0x18000cc32`
- `ADVAPI32!RegOpenKeyExW` at `0x18000cd1d`
- `WSOCK32!__imp_WSAStartup` at `0x18000c7fe`
- `WSOCK32!__imp_WSAStartup` at `0x18000c7fe`
- `WSOCK32!__imp_WSACleanup` at `0x18000c8fa`
- `WSOCK32!__imp_WSACleanup` at `0x18000c984`
- `WSOCK32!__imp_WSACleanup` at `0x18000d459`
- `WSOCK32!__imp_WSACleanup` at `0x18000d480`
- `WSOCK32!__imp_WSACleanup` at `0x18000c8fa`
- `WSOCK32!__imp_WSACleanup` at `0x18000c984`
- `WSOCK32!__imp_WSACleanup` at `0x18000d459`
- `WSOCK32!__imp_WSACleanup` at `0x18000d480`
- `USER32!LoadAcceleratorsW` at `0x18000c9c6`
- `USER32!LoadAcceleratorsW` at `0x18000c9c6`

## string_xrefs

- `0x18000c913`: `nfsnp.dll`
- `0x18000ceb6`: `\Mount`
- `0x18000ce34`: `SOFTWARE\Microsoft\ClientForNFS\CurrentVersion\MountUtility`

## pseudocode

```c
DWORD __fastcall DisplayConfigDlg(HINSTANCE a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5, char a6, int a7)
{
  int v10; // ebx
  __int64 v11; // rcx
  int v12; // eax
  _QWORD *v13; // rsi
  _QWORD *v14; // rax
  _QWORD *v15; // rdi
  HMODULE ModuleHandleW; // rax
  bool v17; // zf
  int v18; // ebx
  const wchar_t *v19; // r8
  __int64 v20; // rcx
  __int64 v21; // rax
  unsigned __int64 v22; // rdx
  unsigned __int64 v23; // rcx
  __int64 v24; // rdx
  __int64 v25; // rcx
  __int64 v26; // rdx
  __int64 v27; // rcx
  __int64 v28; // rdx
  __int64 v29; // rcx
  __int64 v30; // rdx
  __int64 v31; // rcx
  int v32; // ebx
  __int64 v33; // rdx
  __int64 v34; // rcx
  __int64 v35; // rdx
  __int64 v36; // rcx
  __int64 v37; // rdx
  __int64 v38; // rcx
  __int64 v39; // rdx
  __int64 v40; // rcx
  HANDLE CurrentThread; // rax
  void *v42; // rbx
  HANDLE CurrentProcess; // rax
  __int64 v45; // rax
  const wchar_t *v46; // rcx
  int v47; // ebx
  wchar_t *v48; // rax
  WCHAR **v49; // r8
  wchar_t *v50; // rcx
  WCHAR *v51; // r8
  WCHAR **v52; // r8
  wchar_t *v53; // rcx
  WCHAR *v54; // r8
  wchar_t *v55; // rax
  __int64 v56; // rdx
  int v57; // eax
  __int64 v58; // rax
  const wchar_t *v59; // r8
  __int64 v60; // rcx
  _BYTE *v61; // rax
  char *v62; // rax
  char *v63; // r9
  int v64; // r8d
  int v65; // ecx
  int v66; // ebx
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  int v68; // [rsp+48h] [rbp-B8h] BYREF
  HKEY v69; // [rsp+50h] [rbp-B0h] BYREF
  DWORD cbData; // [rsp+58h] [rbp-A8h] BYREF
  HKEY phkResult; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cchName; // [rsp+68h] [rbp-98h] BYREF
  DWORD cchReferencedDomainName; // [rsp+6Ch] [rbp-94h] BYREF
  BYTE Data[4]; // [rsp+70h] [rbp-90h] BYREF
  BYTE v75[4]; // [rsp+74h] [rbp-8Ch] BYREF
  DWORD ReturnLength; // [rsp+78h] [rbp-88h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+7Ch] [rbp-84h] BYREF
  struct WSAData WSAData; // [rsp+80h] [rbp-80h] BYREF
  _BYTE pSid[128]; // [rsp+220h] [rbp+120h] BYREF
  WCHAR SubKey[4]; // [rsp+2A0h] [rbp+1A0h] BYREF
  wchar_t Source[264]; // [rsp+6B0h] [rbp+5B0h] BYREF
  wchar_t v82[264]; // [rsp+8C0h] [rbp+7C0h] BYREF
  wchar_t Destination[264]; // [rsp+AD0h] [rbp+9D0h] BYREF
  wchar_t Name[264]; // [rsp+CE0h] [rbp+BE0h] BYREF
  wchar_t ReferencedDomainName[264]; // [rsp+EF0h] [rbp+DF0h] BYREF
  WCHAR v86[264]; // [rsp+1100h] [rbp+1000h] BYREF
  _BYTE v87[528]; // [rsp+1310h] [rbp+1210h] BYREF

  memset_0(Destination, 0, 0x208u);
  *(_DWORD *)Data = 1;
  phkResult = 0;
  hKey = 0;
  cbData = 0;
  *(_DWORD *)v75 = 1;
  memset_0(&WSAData, 0, sizeof(WSAData));
  memset_0(Name, 0, 0x20Au);
  memset_0(ReferencedDomainName, 0, 0x20Au);
  cchName = 260;
  cchReferencedDomainName = 260;
  v10 = WSAStartup(0x101u, &WSAData);
  *(_DWORD *)(a3 + 56) = 7069;
  *(_DWORD *)(a3 + 60) = 15;
  GetCurrentProcess();
  if ( (unsigned int)DaGetProcessSid(v11, pSid)
    || (unsigned int)DaConvertSidToString(pSid, SubKey, 0x104u)
    || RegOpenKeyExW(HKEY_USERS, SubKey, 0, 0x20019u, &hKey) )
  {
    hKey = HKEY_CURRENT_USER;
    v12 = 0;
  }
  else
  {
    v12 = 1;
  }
  v68 = v12;
  if ( v10 )
    goto LABEL_102;
  if ( !*(_QWORD *)a3 || !a5 || !a4 || (v13 = malloc_0(0x18u)) == 0 )
  {
    WSACleanup();
    goto LABEL_102;
  }
  *(_OWORD *)v13 = 0;
  v13[2] = 0;
  v14 = malloc_0(0x478u);
  v15 = v14;
  if ( !v14 )
  {
    WSACleanup();
    free_0(v13);
LABEL_102:
    DeleteCurrentUserKey(&hKey, &v68);
    return -2147286787;
  }
  *v14 = a3;
  v14[1] = a5;
  v14[2] = a4;
  v14[3] = v13;
  *((_DWORD *)v14 + 8) = 128;
  v14[5] = a1;
  ModuleHandleW = GetModuleHandleW(L"nfsnp.dll");
  v15[7] = 0;
  v15[6] = ModuleHandleW;
  v15[8] = -2147483646;
  *((_DWORD *)v15 + 18) = 0;
  *((_DWORD *)v15 + 19) = a6 & 1;
  v17 = *(_DWORD *)&szAppName[28] == 0;
  v15[10] = 0;
  *(_QWORD *)((char *)v15 + 92) = 0;
  *((_DWORD *)v15 + 25) = 0;
  if ( !v17 )
  {
    if ( !(unsigned int)InitApplication(a1) )
    {
      WSACleanup();
      DeleteCurrentUserKey(&hKey, &v68);
      free_0(v13);
      free_0(v15);
      return -2147286787;
    }
    *(_DWORD *)&szAppName[28] = 0;
  }
  LoadAcceleratorsW((HINSTANCE)v15[5], (LPCWSTR)szAppName);
  if ( (unsigned int)TestUserAccessToProfile() )
  {
    v15[8] = hKey;
    v18 = 1;
    DaBuildRegistryPath(0, L"Persistent", hKey, v82);
    ISDKRegCopyKey(
      (_DWORD)hKey,
      (unsigned int)L"SOFTWARE\\Microsoft\\ClientForNFS\\Persistent",
      (_DWORD)hKey,
      (unsigned int)v82,
      1);
    DaBuildRegistryPath(0, L"Default", hKey, v82);
    ISDKRegCopyKey(
      (_DWORD)hKey,
      (unsigned int)L"SOFTWARE\\Microsoft\\ClientForNFS\\Default",
      (_DWORD)hKey,
      (unsigned int)v82,
      1);
  }
  else
  {
    v18 = 0;
    v15[8] = -2147483646;
  }
  CopyBrowseOptions((LPBYTE)v15[3]);
  v19 = *(const wchar_t **)(v15[2] + 8LL);
  if ( !v19 || !*v19 )
  {
LABEL_39:
    if ( *((_DWORD *)v15 + 20) )
      goto LABEL_48;
    goto LABEL_40;
  }
  wcscpy_s(Destination, 0x104u, v19);
  v20 = -1;
  v21 = -1;
  do
    ++v21;
  while ( Destination[v21] );
  if ( v21 )
  {
    if ( v82[v21 + 263] == 92 || v82[v21 + 263] == 58 )
    {
      v22 = 2 * v21 - 2;
      if ( v22 >= 0x208 )
        goto LABEL_104;
      *(wchar_t *)((char *)Destination + v22) = 0;
    }
    do
      ++v20;
    while ( Destination[v20] );
    if ( v82[v20 + 263] == 58 )
    {
      v23 = 2 * v20 - 2;
      if ( v23 < 0x208 )
      {
        *(wchar_t *)((char *)Destination + v23) = 0;
        goto LABEL_33;
      }
LABEL_104:
      _report_rangecheckfailure();
    }
  }
LABEL_33:
  wcscpy_s(v82, 0x104u, L"Network");
  wcscat_s(v82, 0x104u, L"\\");
  wcscat_s(v82, 0x104u, Destination);
  if ( !RegOpenKeyExW(hKey, v82, 0, 0xF003Fu, &phkResult) )
  {
    *((_DWORD *)v15 + 20) = 1;
    RegCloseKey(phkResult);
  }
  if ( *((_DWORD *)v15 + 20) )
  {
    DaBuildRegistryPath(0, L"Persistent", v15[8], v82);
    wcscat_s(v82, 0x104u, Destination);
    if ( RegOpenKeyExW((HKEY)v15[8], v82, 0, 0xF003Fu, &phkResult) )
      *((_DWORD *)v15 + 20) = 0;
    else
      RegCloseKey(phkResult);
    goto LABEL_39;
  }
LABEL_40:
  if ( v18 )
  {
    if ( !(unsigned int)FindDefaultOptions(hKey) && (unsigned int)FindDefaultOptions(HKEY_LOCAL_MACHINE) )
    {
      DaBuildRegistryPath(0, L"Default", -2147483646, v82);
      DaBuildRegistryPath(0, L"Default", hKey, v87);
      ISDKRegCopyKey(-2147483646, (unsigned int)v82, (_DWORD)hKey, (unsigned int)v87, 0);
    }
    v15[8] = hKey;
  }
  if ( !*((_DWORD *)v15 + 20) )
  {
    DaBuildRegistryPath(0, L"Default", v15[8], v82);
    if ( !RegOpenKeyExW((HKEY)v15[8], v82, 0, 0xF003Fu, &phkResult) )
    {
      cbData = 4;
      RegQueryValueExW(phkResult, L"ConnectDisplay", 0, 0, Data, &cbData);
      cbData = 4;
      RegQueryValueExW(phkResult, L"DisplayConfirmation", 0, 0, v75, &cbData);
      RegCloseKey(phkResult);
    }
  }
LABEL_48:
  if ( a7 || *((_DWORD *)v15 + 20) )
  {
    v69 = 0;
    v32 = 0;
    memset_0(Source, 0, 0x208u);
    memset_0(SubKey, 0, 0x208u);
    if ( *((_DWORD *)v15 + 20) )
    {
      wcscpy_s(Source, 0x104u, L"Network");
      wcscat_s(Source, 0x104u, L"\\");
      wcscat_s(Source, 0x104u, Destination);
      wcscpy_s(SubKey, 0x104u, Source);
      wcscat_s(SubKey, 0x104u, L"\\Mount");
      if ( RegOpenKeyW(hKey, SubKey, &v69) )
        v32 = 1;
      else
        RegCloseKey(v69);
    }
    else
    {
      wcscpy_s(Source, 0x104u, L"SOFTWARE\\Microsoft\\ClientForNFS\\CurrentVersion\\MountUtility");
    }
    *(_DWORD *)(*v15 + 56LL) = 0;
    SetFilenameOptions(v34, v33, *v15);
    if ( v32 || RegOpenKeyW(hKey, Source, &v69) )
    {
      SetMountOptions(v36, v35, v15);
      SetFileAccess(v38, v37, *v15);
    }
    else
    {
      RegCloseKey(v69);
      SetBufferSizes(hKey, Source);
      SetTimeout(hKey, Source);
      SetRetrans(hKey, Source);
      SetMountType(hKey, Source);
      SetVersion3AndLocking2(hKey, Source);
      SetForceCaseSensitiveLookup(hKey, Source);
      SetMountFileAccessOptions(hKey, Source);
      SetAnon(hKey, Source);
      SetSecFlags(hKey, Source);
    }
  }
  else
  {
    memset_0(v86, 0, 0x208u);
    SetMountOptions(v25, v24, v15);
    SetFileAccess(v27, v26, *v15);
    SetFilenameOptions(v29, v28, *v15);
  }
  SetCacheOptions(v31, v30, v15);
  SetSymLinksOptions(v40, v39, *v15);
  v69 = 0;
  peUse = 0;
  ReturnLength = 0;
  memset_0(v86, 0, 0x208u);
  CurrentThread = GetCurrentThread();
  v42 = CurrentThread;
  if ( !CurrentThread )
    goto LABEL_61;
  if ( !OpenThreadToken(CurrentThread, 0x20008u, 0, (PHANDLE)&v69) && !OpenThreadToken(v42, 0x20008u, 1, (PHANDLE)&v69) )
  {
    if ( GetLastError() != 1008 )
      goto LABEL_61;
    CurrentProcess = GetCurrentProcess();
    if ( !CurrentProcess || !OpenProcessToken(CurrentProcess, 0x20008u, (PHANDLE)&v69) )
      goto LABEL_61;
  }
  if ( !GetTokenInformation(v69, TokenUser, SubKey, 0x410u, &ReturnLength)
    || !LookupAccountSidW(0, *(PSID *)SubKey, Name, &cchName, ReferencedDomainName, &cchReferencedDomainName, &peUse) )
  {
    CloseHandle(v69);
LABEL_61:
    DeleteCurrentUserKey(&hKey, &v68);
    free_0(v13);
    free_0(v15);
    return GetLastError();
  }
  if ( 2 * (unsigned __int64)cchName >= 0x20A
    || (v45 = cchReferencedDomainName, Name[cchName] = 0, (unsigned __int64)(2 * v45) >= 0x20A) )
  {
    _report_rangecheckfailure();
  }
  ReferencedDomainName[v45] = 0;
  CloseHandle(v69);
  DaBuildRegistryPath(0, L"Default", v15[8], v86);
  SetAuthOptions((HKEY)v15[8], v86);
  v46 = *(const wchar_t **)v15[1];
  if ( !v46 || !*v46 )
  {
    v47 = 1;
    v55 = wcsstr_0(Name, L"\\");
    v50 = (wchar_t *)(v15[1] + 16LL);
    if ( v55 )
    {
      v51 = Name;
      goto LABEL_79;
    }
    wcscpy_s(v50, 0x104u, ReferencedDomainName);
    wcscat_s((wchar_t *)(v15[1] + 16LL), 0x104u, L"\\");
    v54 = Name;
    v53 = (wchar_t *)(v15[1] + 16LL);
LABEL_81:
    wcscat_s(v53, 0x104u, v54);
    goto LABEL_82;
  }
  v47 = 0;
  v48 = wcsstr_0(v46, L"\\");
  v49 = (WCHAR **)v15[1];
  v50 = (wchar_t *)(v49 + 2);
  if ( !v48 )
  {
    wcscpy_s(v50, 0x104u, ReferencedDomainName);
    wcscat_s((wchar_t *)(v15[1] + 16LL), 0x104u, L"\\");
    v52 = (WCHAR **)v15[1];
    v53 = (wchar_t *)(v52 + 2);
    v54 = *v52;
    goto LABEL_81;
  }
  v51 = *v49;
LABEL_79:
  wcscpy_s(v50, 0x104u, v51);
LABEL_82:
  if ( a7 == 16 )
  {
    *((_DWORD *)v15 + 18) = 1326;
    v57 = 0;
    *((_DWORD *)v15 + 21) = 0;
  }
  else
  {
    v58 = v15[1];
    if ( v47 )
    {
      v60 = 520;
      v61 = (_BYTE *)(v58 + 536);
      do
      {
        *v61++ = 0;
        --v60;
      }
      while ( v60 );
      *(_DWORD *)(v15[1] + 1060LL) |= 1u;
    }
    else
    {
      v59 = *(const wchar_t **)(v58 + 8);
      if ( !v59 )
      {
        DeleteCurrentUserKey(&hKey, &v68);
        free_0(v13);
        free_0(v15);
        return 86;
      }
      wcscpy_s((wchar_t *)(v58 + 536), 0x104u, v59);
      *(_DWORD *)(v15[1] + 1060LL) &= ~1u;
    }
    v57 = DoLogin(v60, v56, v15);
  }
  *((_DWORD *)v15 + 22) = v57;
  if ( *((_DWORD *)v15 + 18) != 21 && !*((_DWORD *)v15 + 24) && *((_DWORD *)v15 + 21) )
  {
    memset_0(SubKey, 0, 0x208u);
    WriteOptsToRegistry((HKEY)v15[8]);
    v62 = (char *)(v15[1] + 16LL);
    v63 = (char *)((char *)Name - v62);
    do
    {
      v64 = *(unsigned __int16 *)&v63[(_QWORD)v62];
      v65 = *(unsigned __int16 *)v62 - v64;
      if ( v65 )
        break;
      v62 += 2;
    }
    while ( v64 );
    if ( !v65 )
    {
      DaBuildRegistryPath(0, L"Default", v15[8], SubKey);
      WriteLoginOpts((HKEY)v15[8], SubKey);
    }
  }
  v66 = *((_DWORD *)v15 + 18);
  free_0(v15);
  WSACleanup();
  DeleteCurrentUserKey(&hKey, &v68);
  free_0(v13);
  return v66;
}

```

## disassembly

```asm
0x18000c738  mov     [rsp-8+arg_8], rbx
0x18000c73d  push    rbp
0x18000c73e  push    rsi
0x18000c73f  push    rdi
0x18000c740  push    r12
0x18000c742  push    r13
0x18000c744  push    r14
0x18000c746  push    r15
0x18000c748  lea     rbp, [rsp-1430h]
0x18000c750  mov     eax, 1530h
0x18000c755  call    _alloca_probe
0x18000c75a  sub     rsp, rax
0x18000c75d  mov     rax, cs:__security_cookie
0x18000c764  xor     rax, rsp
0x18000c767  mov     [rbp+1460h+var_40], rax
0x18000c76e  mov     r14, r8
0x18000c771  mov     r12, rcx
0x18000c774  mov     r8d, 208h; Size
0x18000c77a  lea     rcx, [rbp+1460h+Destination]; void *
0x18000c781  xor     edx, edx; Val
0x18000c783  mov     r15, r9
0x18000c786  call    memset_0
0x18000c78b  xor     r13d, r13d
0x18000c78e  mov     dword ptr [rsp+1560h+Data], 1
0x18000c796  xor     edx, edx; Val
0x18000c798  mov     [rsp+1560h+var_1500], r13
0x18000c79d  mov     r8d, 198h; Size
0x18000c7a3  mov     [rsp+1560h+hKey], r13
0x18000c7a8  lea     rcx, [rbp+1460h+WSAData]; void *
0x18000c7ac  mov     [rsp+1560h+cbData], r13d
0x18000c7b1  mov     dword ptr [rsp+1560h+var_14EC], 1
0x18000c7b9  call    memset_0
0x18000c7be  mov     ebx, 20Ah
0x18000c7c3  lea     rcx, [rbp+1460h+Name]; void *
0x18000c7ca  mov     r8d, ebx; Size
0x18000c7cd  xor     edx, edx; Val
0x18000c7cf  call    memset_0
0x18000c7d4  mov     r8d, ebx; Size
0x18000c7d7  lea     rcx, [rbp+1460h+ReferencedDomainName]; void *
0x18000c7de  xor     edx, edx; Val
0x18000c7e0  call    memset_0
0x18000c7e5  mov     ecx, 101h; wVersionRequested
0x18000c7ea  mov     [rsp+1560h+cchName], 104h
0x18000c7f2  lea     rdx, [rbp+1460h+WSAData]; lpWSAData
0x18000c7f6  mov     [rsp+1560h+cchReferencedDomainName], 104h
0x18000c7fe  call    cs:__imp_WSAStartup
0x18000c805  nop     dword ptr [rax+rax+00h]
0x18000c80a  mov     ebx, eax
0x18000c80c  mov     dword ptr [r14+38h], 1B9Dh
0x18000c814  mov     dword ptr [r14+3Ch], 0Fh
0x18000c81c  call    cs:__imp_GetCurrentProcess
0x18000c823  nop     dword ptr [rax+rax+00h]
0x18000c828  lea     rdx, [rbp+1460h+pSid]
0x18000c82f  call    DaGetProcessSid
0x18000c834  test    eax, eax
0x18000c836  jnz     short loc_18000C88C
0x18000c838  mov     r8d, 104h; BufferCount
0x18000c83e  lea     rdx, [rbp+1460h+SubKey]; Buffer
0x18000c845  lea     rcx, [rbp+1460h+pSid]; pSid
0x18000c84c  call    DaConvertSidToString
0x18000c851  test    eax, eax
0x18000c853  jnz     short loc_18000C88C
0x18000c855  lea     rax, [rsp+1560h+hKey]
0x18000c85a  mov     r9d, 20019h; samDesired
0x18000c860  xor     r8d, r8d; ulOptions
0x18000c863  mov     [rsp+1560h+phkResult], rax; phkResult
0x18000c868  lea     rdx, [rbp+1460h+SubKey]; lpSubKey
0x18000c86f  mov     rcx, 0FFFFFFFF80000003h; hKey
0x18000c876  call    cs:__imp_RegOpenKeyExW
0x18000c87d  nop     dword ptr [rax+rax+00h]
0x18000c882  test    eax, eax
0x18000c884  jnz     short loc_18000C88C
0x18000c886  lea     eax, [r13+1]
0x18000c88a  jmp     short loc_18000C898
0x18000c88c  mov     [rsp+1560h+hKey], 0FFFFFFFF80000001h
0x18000c895  mov     eax, r13d
0x18000c898  mov     [rsp+1560h+var_1518], eax
0x18000c89c  test    ebx, ebx
0x18000c89e  jnz     loc_18000D48C
0x18000c8a4  cmp     [r14], r13
0x18000c8a7  jz      loc_18000D480
0x18000c8ad  mov     rbx, [rbp+1460h+arg_20]
0x18000c8b4  test    rbx, rbx
0x18000c8b7  jz      loc_18000D480
0x18000c8bd  test    r15, r15
0x18000c8c0  jz      loc_18000D480
0x18000c8c6  mov     ecx, 18h; Size
0x18000c8cb  call    malloc_0
0x18000c8d0  mov     rsi, rax
0x18000c8d3  test    rax, rax
0x18000c8d6  jz      loc_18000D480
0x18000c8dc  xorps   xmm0, xmm0
0x18000c8df  xor     eax, eax
0x18000c8e1  movups  xmmword ptr [rsi], xmm0
0x18000c8e4  mov     ecx, 478h; Size
0x18000c8e9  mov     [rsi+10h], rax
0x18000c8ed  call    malloc_0
0x18000c8f2  mov     rdi, rax
0x18000c8f5  test    rax, rax
0x18000c8f8  jnz     short loc_18000C913
0x18000c8fa  call    cs:__imp_WSACleanup
0x18000c901  nop     dword ptr [rax+rax+00h]
0x18000c906  mov     rcx, rsi; Block
0x18000c909  call    free_0
0x18000c90e  jmp     loc_18000D48C
0x18000c913  lea     rcx, ModuleName; "nfsnp.dll"
0x18000c91a  mov     [rax], r14
0x18000c91d  mov     [rax+8], rbx
0x18000c921  mov     [rax+10h], r15
0x18000c925  mov     [rax+18h], rsi
0x18000c929  mov     dword ptr [rax+20h], 80h
0x18000c930  mov     [rax+28h], r12
0x18000c934  call    cs:__imp_GetModuleHandleW
0x18000c93b  nop     dword ptr [rax+rax+00h]
0x18000c940  mov     r14, 0FFFFFFFF80000002h
0x18000c947  mov     [rdi+38h], r13
0x18000c94b  mov     [rdi+30h], rax
0x18000c94f  mov     eax, dword ptr [rbp+1460h+arg_28]
0x18000c955  and     eax, 1
0x18000c958  mov     [rdi+40h], r14
0x18000c95c  mov     [rdi+48h], r13d
0x18000c960  mov     [rdi+4Ch], eax
0x18000c963  cmp     dword ptr cs:szAppName+1Ch, r13d
0x18000c96a  mov     [rdi+50h], r13
0x18000c96e  mov     [rdi+5Ch], r13
0x18000c972  mov     [rdi+64h], r13d
0x18000c976  jz      short loc_18000C9BB
0x18000c978  mov     rcx, r12; hInstance
0x18000c97b  call    InitApplication
0x18000c980  test    eax, eax
0x18000c982  jnz     short loc_18000C9B4
0x18000c984  call    cs:__imp_WSACleanup
0x18000c98b  nop     dword ptr [rax+rax+00h]
0x18000c990  lea     rdx, [rsp+1560h+var_1518]
0x18000c995  lea     rcx, [rsp+1560h+hKey]
0x18000c99a  call    DeleteCurrentUserKey
0x18000c99f  mov     rcx, rsi; Block
0x18000c9a2  call    free_0
0x18000c9a7  mov     rcx, rdi; Block
0x18000c9aa  call    free_0
0x18000c9af  jmp     loc_18000D49B
0x18000c9b4  mov     dword ptr cs:szAppName+1Ch, r13d
0x18000c9bb  mov     rcx, [rdi+28h]; hInstance
0x18000c9bf  lea     rdx, szAppName; lpTableName
0x18000c9c6  call    cs:__imp_LoadAcceleratorsW
0x18000c9cd  nop     dword ptr [rax+rax+00h]
0x18000c9d2  call    TestUserAccessToProfile
0x18000c9d7  mov     r12d, 1
0x18000c9dd  test    eax, eax
0x18000c9df  jz      loc_18000CA67
0x18000c9e5  mov     rax, [rsp+1560h+hKey]
0x18000c9ea  lea     r9, [rbp+1460h+var_CA0]
0x18000c9f1  mov     [rdi+40h], rax
0x18000c9f5  lea     rdx, aPersistent; "Persistent"
0x18000c9fc  mov     r8, [rsp+1560h+hKey]
0x18000ca01  xor     ecx, ecx
0x18000ca03  mov     ebx, r12d
0x18000ca06  call    DaBuildRegistryPath
0x18000ca0b  mov     rcx, [rsp+1560h+hKey]
0x18000ca10  lea     r9, [rbp+1460h+var_CA0]
0x18000ca17  mov     r8, rcx
0x18000ca1a  mov     dword ptr [rsp+1560h+phkResult], r12d
0x18000ca1f  lea     rdx, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\ClientForNFS\\Pers"...
0x18000ca26  call    ISDKRegCopyKey
0x18000ca2b  mov     r8, [rsp+1560h+hKey]
0x18000ca30  lea     r9, [rbp+1460h+var_CA0]
0x18000ca37  lea     rdx, aDefault; "Default"
0x18000ca3e  xor     ecx, ecx
0x18000ca40  call    DaBuildRegistryPath
0x18000ca45  mov     rcx, [rsp+1560h+hKey]
0x18000ca4a  lea     r9, [rbp+1460h+var_CA0]
0x18000ca51  mov     r8, rcx
0x18000ca54  mov     dword ptr [rsp+1560h+phkResult], r12d
0x18000ca59  lea     rdx, aSoftwareMicros_3; "SOFTWARE\\Microsoft\\ClientForNFS\\Defa"...
0x18000ca60  call    ISDKRegCopyKey
0x18000ca65  jmp     short loc_18000CA6E
0x18000ca67  mov     ebx, r13d
0x18000ca6a  mov     [rdi+40h], r14
0x18000ca6e  mov     rcx, [rdi+18h]; lpData
0x18000ca72  call    CopyBrowseOptions
0x18000ca77  mov     rax, [rdi+10h]
0x18000ca7b  mov     r15d, 104h
0x18000ca81  mov     r8, [rax+8]; Source
0x18000ca85  test    r8, r8
0x18000ca88  jz      loc_18000CC59
0x18000ca8e  cmp     [r8], r13w
0x18000ca92  jz      loc_18000CC59
0x18000ca98  mov     edx, r15d; SizeInWords
0x18000ca9b  lea     rcx, [rbp+1460h+Destination]; Destination
0x18000caa2  call    cs:__imp_wcscpy_s
0x18000caa9  nop     dword ptr [rax+rax+00h]
0x18000caae  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000cab2  lea     rdx, [rbp+1460h+Destination]
0x18000cab9  mov     rax, rcx
0x18000cabc  inc     rax
0x18000cabf  cmp     [rdx+rax*2], r13w
0x18000cac4  jnz     short loc_18000CABC
0x18000cac6  test    rax, rax
0x18000cac9  jz      short loc_18000CB39
0x18000cacb  cmp     [rbp+rax*2+1460h+var_A92], 5Ch ; '\'
0x18000cad4  jz      short loc_18000CAE1
0x18000cad6  cmp     [rbp+rax*2+1460h+var_A92], 3Ah ; ':'
0x18000cadf  jnz     short loc_18000CAFF
0x18000cae1  lea     rdx, ds:0FFFFFFFFFFFFFFFEh[rax*2]
0x18000cae9  cmp     rdx, 208h
0x18000caf0  jnb     loc_18000D4CB
0x18000caf6  mov     [rbp+rdx+1460h+Destination], r13w
0x18000caff  lea     rax, [rbp+1460h+Destination]
0x18000cb06  inc     rcx
0x18000cb09  cmp     [rax+rcx*2], r13w
0x18000cb0e  jnz     short loc_18000CB06
0x18000cb10  cmp     [rbp+rcx*2+1460h+var_A92], 3Ah ; ':'
0x18000cb19  jnz     short loc_18000CB39
0x18000cb1b  lea     rcx, ds:0FFFFFFFFFFFFFFFEh[rcx*2]
0x18000cb23  cmp     rcx, 208h
0x18000cb2a  jnb     loc_18000D4CB
0x18000cb30  mov     [rbp+rcx+1460h+Destination], r13w
0x18000cb39  lea     r8, aNetwork; "Network"
0x18000cb40  mov     rdx, r15; SizeInWords
0x18000cb43  lea     rcx, [rbp+1460h+var_CA0]; Destination
0x18000cb4a  call    cs:__imp_wcscpy_s
0x18000cb51  nop     dword ptr [rax+rax+00h]
0x18000cb56  lea     r8, SubStr; "\\"
0x18000cb5d  mov     rdx, r15; SizeInWords
0x18000cb60  lea     rcx, [rbp+1460h+var_CA0]; Destination
0x18000cb67  call    cs:__imp_wcscat_s
0x18000cb6e  nop     dword ptr [rax+rax+00h]
0x18000cb73  lea     r8, [rbp+1460h+Destination]; Source
0x18000cb7a  mov     rdx, r15; SizeInWords
0x18000cb7d  lea     rcx, [rbp+1460h+var_CA0]; Destination
0x18000cb84  call    cs:__imp_wcscat_s
0x18000cb8b  nop     dword ptr [rax+rax+00h]
0x18000cb90  mov     rcx, [rsp+1560h+hKey]; hKey
0x18000cb95  lea     rax, [rsp+1560h+var_1500]
0x18000cb9a  mov     r9d, 0F003Fh; samDesired
0x18000cba0  mov     [rsp+1560h+phkResult], rax; phkResult
0x18000cba5  xor     r8d, r8d; ulOptions
0x18000cba8  lea     rdx, [rbp+1460h+var_CA0]; lpSubKey
0x18000cbaf  call    cs:__imp_RegOpenKeyExW
0x18000cbb6  nop     dword ptr [rax+rax+00h]
0x18000cbbb  test    eax, eax
0x18000cbbd  jnz     short loc_18000CBD4
0x18000cbbf  mov     [rdi+50h], r12d
0x18000cbc3  mov     rcx, [rsp+1560h+var_1500]; hKey
0x18000cbc8  call    cs:__imp_RegCloseKey
0x18000cbcf  nop     dword ptr [rax+rax+00h]
0x18000cbd4  cmp     [rdi+50h], r13d
0x18000cbd8  jz      loc_18000CC63
0x18000cbde  mov     r8, [rdi+40h]
0x18000cbe2  lea     r9, [rbp+1460h+var_CA0]
0x18000cbe9  lea     rdx, aPersistent; "Persistent"
0x18000cbf0  xor     ecx, ecx
0x18000cbf2  call    DaBuildRegistryPath
0x18000cbf7  lea     r8, [rbp+1460h+Destination]; Source
0x18000cbfe  mov     rdx, r15; SizeInWords
0x18000cc01  lea     rcx, [rbp+1460h+var_CA0]; Destination
0x18000cc08  call    cs:__imp_wcscat_s
0x18000cc0f  nop     dword ptr [rax+rax+00h]
0x18000cc14  mov     rcx, [rdi+40h]; hKey
0x18000cc18  lea     rax, [rsp+1560h+var_1500]
0x18000cc1d  mov     r9d, 0F003Fh; samDesired
0x18000cc23  mov     [rsp+1560h+phkResult], rax; phkResult
0x18000cc28  xor     r8d, r8d; ulOptions
0x18000cc2b  lea     rdx, [rbp+1460h+var_CA0]; lpSubKey
0x18000cc32  call    cs:__imp_RegOpenKeyExW
0x18000cc39  nop     dword ptr [rax+rax+00h]
0x18000cc3e  test    eax, eax
0x18000cc40  jz      short loc_18000CC48
0x18000cc42  mov     [rdi+50h], r13d
0x18000cc46  jmp     short loc_18000CC59
0x18000cc48  mov     rcx, [rsp+1560h+var_1500]; hKey
0x18000cc4d  call    cs:__imp_RegCloseKey
0x18000cc54  nop     dword ptr [rax+rax+00h]
0x18000cc59  cmp     [rdi+50h], r13d
0x18000cc5d  jnz     loc_18000CDB1
0x18000cc63  test    ebx, ebx
0x18000cc65  jz      short loc_18000CCDC
0x18000cc67  mov     rcx, [rsp+1560h+hKey]; hKey
0x18000cc6c  call    FindDefaultOptions
0x18000cc71  test    eax, eax
0x18000cc73  jnz     short loc_18000CCD3
0x18000cc75  mov     rcx, r14; hKey
0x18000cc78  call    FindDefaultOptions
0x18000cc7d  test    eax, eax
0x18000cc7f  jz      short loc_18000CCD3
0x18000cc81  lea     r9, [rbp+1460h+var_CA0]
0x18000cc88  mov     r8, r14
0x18000cc8b  lea     rdx, aDefault; "Default"
0x18000cc92  xor     ecx, ecx
0x18000cc94  call    DaBuildRegistryPath
0x18000cc99  mov     r8, [rsp+1560h+hKey]
0x18000cc9e  lea     r9, [rbp+1460h+var_250]
0x18000cca5  lea     rdx, aDefault; "Default"
0x18000ccac  xor     ecx, ecx
0x18000ccae  call    DaBuildRegistryPath
0x18000ccb3  mov     r8, [rsp+1560h+hKey]
0x18000ccb8  lea     r9, [rbp+1460h+var_250]
0x18000ccbf  lea     rdx, [rbp+1460h+var_CA0]
0x18000ccc6  mov     dword ptr [rsp+1560h+phkResult], r13d
0x18000cccb  mov     rcx, r14
  ... truncated ...
```
