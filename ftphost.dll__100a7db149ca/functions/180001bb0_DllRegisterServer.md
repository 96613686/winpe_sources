# DllRegisterServer

- ea: `0x180001bb0`
- end: `0x1800029b6`
- name: `DllRegisterServer`
- size: `3590`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180001bb0`
- `0x1800040c8`
- `0x1800043f6`
- `0x180004420`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x180001da0`
- `ADVAPI32!RegSetValueExW` at `0x180001df5`
- `ADVAPI32!RegSetValueExW` at `0x180001e43`
- `ADVAPI32!RegSetValueExW` at `0x180001e72`
- `ADVAPI32!RegSetValueExW` at `0x180001ea5`
- `ADVAPI32!RegSetValueExW` at `0x180001f29`
- `ADVAPI32!RegSetValueExW` at `0x180001f9a`
- `ADVAPI32!RegSetValueExW` at `0x18000202a`
- `ADVAPI32!RegSetValueExW` at `0x180002095`
- `ADVAPI32!RegSetValueExW` at `0x180002175`
- `ADVAPI32!RegSetValueExW` at `0x1800021a1`
- `ADVAPI32!RegSetValueExW` at `0x180002214`
- `ADVAPI32!RegSetValueExW` at `0x18000224a`
- `ADVAPI32!RegSetValueExW` at `0x1800022cb`
- `ADVAPI32!RegSetValueExW` at `0x18000234c`
- `ADVAPI32!RegSetValueExW` at `0x1800023ca`
- `ADVAPI32!RegSetValueExW` at `0x18000244b`
- `ADVAPI32!RegSetValueExW` at `0x18000255f`
- `ADVAPI32!RegSetValueExW` at `0x1800025d5`
- `ADVAPI32!RegSetValueExW` at `0x180002656`
- `ADVAPI32!RegSetValueExW` at `0x1800026d7`
- `ADVAPI32!RegSetValueExW` at `0x1800027bc`
- `ADVAPI32!RegSetValueExW` at `0x180002827`
- `ADVAPI32!RegSetValueExW` at `0x18000285b`
- `ADVAPI32!RegSetValueExW` at `0x180002919`
- `ADVAPI32!RegSetValueExW` at `0x180002977`
- `ADVAPI32!RegSetValueExW` at `0x180001da0`
- `ADVAPI32!RegSetValueExW` at `0x180001df5`
- `ADVAPI32!RegSetValueExW` at `0x180001e43`
- `ADVAPI32!RegSetValueExW` at `0x180001e72`
- `ADVAPI32!RegSetValueExW` at `0x180001ea5`
- `ADVAPI32!RegSetValueExW` at `0x180001f29`
- `ADVAPI32!RegSetValueExW` at `0x180001f9a`
- `ADVAPI32!RegSetValueExW` at `0x18000202a`
- `ADVAPI32!RegSetValueExW` at `0x180002095`
- `ADVAPI32!RegSetValueExW` at `0x180002175`
- `ADVAPI32!RegSetValueExW` at `0x1800021a1`
- `ADVAPI32!RegSetValueExW` at `0x180002214`
- `ADVAPI32!RegSetValueExW` at `0x18000224a`
- `ADVAPI32!RegSetValueExW` at `0x1800022cb`
- `ADVAPI32!RegSetValueExW` at `0x18000234c`
- `ADVAPI32!RegSetValueExW` at `0x1800023ca`
- `ADVAPI32!RegSetValueExW` at `0x18000244b`
- `ADVAPI32!RegSetValueExW` at `0x18000255f`
- `ADVAPI32!RegSetValueExW` at `0x1800025d5`
- `ADVAPI32!RegSetValueExW` at `0x180002656`
- `ADVAPI32!RegSetValueExW` at `0x1800026d7`
- `ADVAPI32!RegSetValueExW` at `0x1800027bc`
- `ADVAPI32!RegSetValueExW` at `0x180002827`
- `ADVAPI32!RegSetValueExW` at `0x18000285b`
- `ADVAPI32!RegSetValueExW` at `0x180002919`
- `ADVAPI32!RegSetValueExW` at `0x180002977`
- `ADVAPI32!RegCreateKeyExW` at `0x180001cba`
- `ADVAPI32!RegCreateKeyExW` at `0x180001ef6`
- `ADVAPI32!RegCreateKeyExW` at `0x180001f68`
- `ADVAPI32!RegCreateKeyExW` at `0x180001ffb`
- `ADVAPI32!RegCreateKeyExW` at `0x180002069`
- `ADVAPI32!RegCreateKeyExW` at `0x180002143`
- `ADVAPI32!RegCreateKeyExW` at `0x1800021e0`
- `ADVAPI32!RegCreateKeyExW` at `0x180002299`
- `ADVAPI32!RegCreateKeyExW` at `0x18000231a`
- `ADVAPI32!RegCreateKeyExW` at `0x18000239b`
- `ADVAPI32!RegCreateKeyExW` at `0x180002419`
- `ADVAPI32!RegCreateKeyExW` at `0x18000252d`
- `ADVAPI32!RegCreateKeyExW` at `0x18000259e`
- `ADVAPI32!RegCreateKeyExW` at `0x180002624`
- `ADVAPI32!RegCreateKeyExW` at `0x1800026a5`
- `ADVAPI32!RegCreateKeyExW` at `0x18000278c`
- `ADVAPI32!RegCreateKeyExW` at `0x1800027f9`
- `ADVAPI32!RegCreateKeyExW` at `0x1800028e9`
- `ADVAPI32!RegCreateKeyExW` at `0x180002952`
- `ADVAPI32!RegCreateKeyExW` at `0x180001cba`
- `ADVAPI32!RegCreateKeyExW` at `0x180001ef6`
- `ADVAPI32!RegCreateKeyExW` at `0x180001f68`
- `ADVAPI32!RegCreateKeyExW` at `0x180001ffb`
- `ADVAPI32!RegCreateKeyExW` at `0x180002069`
- `ADVAPI32!RegCreateKeyExW` at `0x180002143`
- `ADVAPI32!RegCreateKeyExW` at `0x1800021e0`
- `ADVAPI32!RegCreateKeyExW` at `0x180002299`
- `ADVAPI32!RegCreateKeyExW` at `0x18000231a`
- `ADVAPI32!RegCreateKeyExW` at `0x18000239b`
- `ADVAPI32!RegCreateKeyExW` at `0x180002419`
- `ADVAPI32!RegCreateKeyExW` at `0x18000252d`
- `ADVAPI32!RegCreateKeyExW` at `0x18000259e`
- `ADVAPI32!RegCreateKeyExW` at `0x180002624`
- `ADVAPI32!RegCreateKeyExW` at `0x1800026a5`
- `ADVAPI32!RegCreateKeyExW` at `0x18000278c`
- `ADVAPI32!RegCreateKeyExW` at `0x1800027f9`
- `ADVAPI32!RegCreateKeyExW` at `0x1800028e9`
- `ADVAPI32!RegCreateKeyExW` at `0x180002952`
- `ADVAPI32!RegCloseKey` at `0x180001d1d`
- `ADVAPI32!RegCloseKey` at `0x180001d32`
- `ADVAPI32!RegCloseKey` at `0x180001eba`
- `ADVAPI32!RegCloseKey` at `0x180001faf`
- `ADVAPI32!RegCloseKey` at `0x180001fbf`
- `ADVAPI32!RegCloseKey` at `0x1800020aa`
- `ADVAPI32!RegCloseKey` at `0x1800020ba`
- `ADVAPI32!RegCloseKey` at `0x18000225f`
- `ADVAPI32!RegCloseKey` at `0x1800022e0`
- `ADVAPI32!RegCloseKey` at `0x180002361`
- `ADVAPI32!RegCloseKey` at `0x1800023df`
- `ADVAPI32!RegCloseKey` at `0x180002460`
- `ADVAPI32!RegCloseKey` at `0x180002470`
- `ADVAPI32!RegCloseKey` at `0x1800025ea`
- `ADVAPI32!RegCloseKey` at `0x18000266b`
- `ADVAPI32!RegCloseKey` at `0x1800026ec`
- `ADVAPI32!RegCloseKey` at `0x1800026fc`
- `ADVAPI32!RegCloseKey` at `0x18000286e`
- `ADVAPI32!RegCloseKey` at `0x18000287e`
- `ADVAPI32!RegCloseKey` at `0x180002993`
- `ADVAPI32!RegCloseKey` at `0x1800029a3`
- `ADVAPI32!RegCloseKey` at `0x180001d1d`
- `ADVAPI32!RegCloseKey` at `0x180001d32`
- `ADVAPI32!RegCloseKey` at `0x180001eba`
- `ADVAPI32!RegCloseKey` at `0x180001faf`
- `ADVAPI32!RegCloseKey` at `0x180001fbf`
- `ADVAPI32!RegCloseKey` at `0x1800020aa`
- `ADVAPI32!RegCloseKey` at `0x1800020ba`
- `ADVAPI32!RegCloseKey` at `0x18000225f`
- `ADVAPI32!RegCloseKey` at `0x1800022e0`
- `ADVAPI32!RegCloseKey` at `0x180002361`
- `ADVAPI32!RegCloseKey` at `0x1800023df`
- `ADVAPI32!RegCloseKey` at `0x180002460`
- `ADVAPI32!RegCloseKey` at `0x180002470`
- `ADVAPI32!RegCloseKey` at `0x1800025ea`
- `ADVAPI32!RegCloseKey` at `0x18000266b`
- `ADVAPI32!RegCloseKey` at `0x1800026ec`
- `ADVAPI32!RegCloseKey` at `0x1800026fc`
- `ADVAPI32!RegCloseKey` at `0x18000286e`
- `ADVAPI32!RegCloseKey` at `0x18000287e`
- `ADVAPI32!RegCloseKey` at `0x180002993`
- `ADVAPI32!RegCloseKey` at `0x1800029a3`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180001d4c`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180001d4c`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180001c31`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180001c31`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180001c43`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800020d1`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180002487`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180002713`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180002895`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180001c43`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800020d1`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180002487`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180002713`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180002895`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180001d42`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180001d42`
- `iisutil!PuDbgPrintError` at `0x180001d0d`
- `iisutil!PuDbgPrintError` at `0x180001d0d`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180001c5f`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180001c7a`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800020ed`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180002105`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800024a3`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800024bb`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800024d7`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800024ef`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000272f`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000274e`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800028a7`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800028b5`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180001c5f`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180001c7a`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800020ed`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180002105`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800024a3`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800024bb`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800024d7`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800024ef`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000272f`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000274e`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800028a7`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800028b5`

## string_xrefs

- `0x180001e24`: `AccessPermission`
- `0x180001e58`: `DllSurrogate`
- `0x180002049`: `CLSID`
- `0x180002238`: `ThreadingModel`
- `0x180002849`: `ThreadingModel`
- `0x180002932`: `ProxyStubClsid32`
- `0x180001ce9`: `DllRegisterServer failed\n`
- `0x180001cf5`: `DllRegisterServer`
- `0x1800026ba`: `%SystemRoot%\system32\inetsrv`
- `0x1800020c0`: `CLSID`
- `0x180002702`: `CLSID`
- `0x1800021f5`: `%SystemRoot%\system32\inetsrv\ftphost.dll`
- `0x1800025b7`: `%SystemRoot%\system32\inetsrv\ftphost.dll`
- `0x18000280c`: `%SystemRoot%\system32\inetsrv\ftphost.dll`

## pseudocode

```c
HRESULT __stdcall DllRegisterServer()
{
  HRESULT v0; // ebx
  LSTATUS v1; // eax
  bool v2; // cc
  HKEY v3; // rcx
  bool v5; // cc
  HKEY phkResult; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  DWORD cbData; // [rsp+60h] [rbp-A0h] BYREF
  BYTE Data[4]; // [rsp+64h] [rbp-9Ch] BYREF
  _BYTE v10[32]; // [rsp+68h] [rbp-98h] BYREF
  LPCWSTR lpSubKey; // [rsp+88h] [rbp-78h]
  _QWORD v12[4]; // [rsp+A0h] [rbp-60h] BYREF
  BYTE *lpData; // [rsp+C0h] [rbp-40h]
  int v14; // [rsp+C8h] [rbp-38h]
  __int16 v15; // [rsp+CCh] [rbp-34h]
  unsigned __int16 v16[256]; // [rsp+D0h] [rbp-30h] BYREF

  v14 = 32;
  hKey = 0;
  phkResult = 0;
  v12[0] = 0;
  lpData = (BYTE *)v12;
  v15 = 256;
  cbData = 0;
  *(_DWORD *)Data = 6;
  memset_0(v16, 0, sizeof(v16));
  STRU::STRU((STRU *)v10, v16, 0x100u);
  v0 = STRU::Copy((STRU *)v10, L"AppID");
  if ( v0 < 0 )
    goto LABEL_8;
  v0 = STRU::Append((STRU *)v10, L"\\");
  if ( v0 < 0 )
    goto LABEL_8;
  v0 = STRU::Append((STRU *)v10, L"{315fa593-3cf5-4310-887b-3977a578488a}");
  if ( v0 < 0 )
    goto LABEL_8;
  v1 = RegCreateKeyExW(HKEY_CLASSES_ROOT, lpSubKey, 0, 0, 0, 0xF003Fu, 0, &hKey, 0);
  v0 = v1;
  v2 = v1 <= 0;
  if ( v1 )
    goto LABEL_5;
  v1 = RegSetValueExW(hKey, &ValueName, 0, 1u, L"IIS FtpHost", 0x18u);
  v0 = v1;
  v2 = v1 <= 0;
  if ( v1 )
    goto LABEL_5;
  v0 = CreateSecurityDescriptorForCom((struct BUFFER *)v12, &cbData, 9u);
  if ( v0 < 0 )
    goto LABEL_8;
  v1 = RegSetValueExW(hKey, L"LaunchPermission", 0, 3u, lpData, cbData);
  v0 = v1;
  v2 = v1 <= 0;
  if ( v1 )
    goto LABEL_5;
  v0 = CreateSecurityDescriptorForCom((struct BUFFER *)v12, &cbData, 3u);
  if ( v0 < 0 )
    goto LABEL_8;
  v1 = RegSetValueExW(hKey, L"AccessPermission", 0, 3u, lpData, cbData);
  v0 = v1;
  v2 = v1 <= 0;
  if ( v1 )
    goto LABEL_5;
  v1 = RegSetValueExW(hKey, L"DllSurrogate", 0, 1u, (const BYTE *)&ValueName, 2u);
  v0 = v1;
  v2 = v1 <= 0;
  if ( v1 )
    goto LABEL_5;
  v1 = RegSetValueExW(hKey, L"AuthenticationLevel", 0, 4u, Data, 4u);
  v0 = v1;
  v2 = v1 <= 0;
  if ( v1 )
    goto LABEL_5;
  RegCloseKey(hKey);
  hKey = 0;
  v1 = RegCreateKeyExW(HKEY_CLASSES_ROOT, L"IISFtpHost.IISFtpHost", 0, 0, 0, 0xF003Fu, 0, &hKey, 0);
  v0 = v1;
  v2 = v1 <= 0;
  if ( v1 )
    goto LABEL_5;
  v1 = RegSetValueExW(hKey, &ValueName, 0, 1u, L"IIS FtpHost Class", 0x24u);
  v0 = v1;
  v2 = v1 <= 0;
  if ( v1 )
    goto LABEL_5;
  v1 = RegCreateKeyExW(hKey, L"CurVer", 0, 0, 0, 0xF003Fu, 0, &phkResult, 0);
  v0 = v1;
  v2 = v1 <= 0;
  if ( v1 )
    goto LABEL_5;
  v1 = RegSetValueExW(phkResult, &ValueName, 0, 1u, L"IISFtpHost.IISFtpHost.1", 0x30u);
  v0 = v1;
  v2 = v1 <= 0;
  if ( v1 )
    goto LABEL_5;
  RegCloseKey(phkResult);
  phkResult = 0;
  RegCloseKey(hKey);
  hKey = 0;
  v1 = RegCreateKeyExW(HKEY_CLASSES_ROOT, (LPCWSTR)L"IISFtpHost.IISFtpHost.1", 0, 0, 0, 0xF003Fu, 0, &hKey, 0);
  v0 = v1;
  v2 = v1 <= 0;
  if ( v1 )
    goto LABEL_5;
  v1 = RegSetValueExW(hKey, &ValueName, 0, 1u, L"IIS FtpHost Class", 0x24u);
  v0 = v1;
  v2 = v1 <= 0;
  if ( v1 )
    goto LABEL_5;
  v1 = RegCreateKeyExW(hKey, L"CLSID", 0, 0, 0, 0xF003Fu, 0, &phkResult, 0);
  v0 = v1;
  v2 = v1 <= 0;
  if ( v1 )
    goto LABEL_5;
  v1 = RegSetValueExW(phkResult, &ValueName, 0, 1u, L"{315fa593-3cf5-4310-887b-3977a578488a}", 0x4Eu);
  v0 = v1;
  v2 = v1 <= 0;
  if ( v1 )
    goto LABEL_5;
  RegCloseKey(phkResult);
  phkResult = 0;
  RegCloseKey(hKey);
  hKey = 0;
  v0 = STRU::Copy((STRU *)v10, L"CLSID");
  if ( v0 < 0 )
    goto LABEL_8;
  v0 = STRU::Append((STRU *)v10, L"\\");
  if ( v0 < 0 )
    goto LABEL_8;
  v0 = STRU::Append((STRU *)v10, L"{315fa593-3cf5-4310-887b-3977a578488a}");
  if ( v0 < 0 )
    goto LABEL_8;
  v1 = RegCreateKeyExW(HKEY_CLASSES_ROOT, lpSubKey, 0, 0, 0, 0xF003Fu, 0, &hKey, 0);
  v0 = v1;
  v2 = v1 <= 0;
  if ( v1 )
    goto LABEL_5;
  v1 = RegSetValueExW(hKey, &ValueName, 0, 1u, L"IIS FtpHost", 0x18u);
  v0 = v1;
  v2 = v1 <= 0;
  if ( v1 )
    goto LABEL_5;
  v1 = RegSetValueExW(hKey, L"AppID", 0, 1u, L"{315fa593-3cf5-4310-887b-3977a578488a}", 0x4Eu);
  v0 = v1;
  v2 = v1 <= 0;
  if ( v1 )
    goto LABEL_5;
  v1 = RegCreateKeyExW(hKey, L"InprocServer32", 0, 0, 0, 0xF003Fu, 0, &phkResult, 0);
  v0 = v1;
  v2 = v1 <= 0;
  if ( v1 )
    goto LABEL_5;
  v1 = RegSetValueExW(phkResult, &ValueName, 0, 2u, L"%SystemRoot%\\system32\\inetsrv\\ftphost.dll", 0x54u);
  v0 = v1;
  v2 = v1 <= 0;
  if ( v1 )
    goto LABEL_5;
  v1 = RegSetValueExW(phkResult, L"ThreadingModel", 0, 1u, L"Both", 0xAu);
  v0 = v1;
  v2 = v1 <= 0;
  if ( v1 )
    goto LABEL_5;
  RegCloseKey(phkResult);
  phkResult = 0;
  v1 = RegCreateKeyExW(hKey, L"ProgID", 0, 0, 0, 0xF003Fu, 0, &phkResult, 0);
  v0 = v1;
  v2 = v1 <= 0;
  if ( v1 )
    goto LABEL_5;
  v1 = RegSetValueExW(phkResult, &ValueName, 0, 1u, L"IISFtpHost.IISFtpHost.1", 0x30u);
  v0 = v1;
  v2 = v1 <= 0;
  if ( v1 )
    goto LABEL_5;
  RegCloseKey(phkResult);
  phkResult = 0;
  v1 = RegCreateKeyExW(hKey, L"VersionIndependentProgID", 0, 0, 0, 0xF003Fu, 0, &phkResult, 0);
  v0 = v1;
  v2 = v1 <= 0;
  if ( v1 )
    goto LABEL_5;
  v1 = RegSetValueExW(phkResult, &ValueName, 0, 1u, (const BYTE *)L"IISFtpHost.IISFtpHost", 0x2Cu);
  v0 = v1;
  v2 = v1 <= 0;
  if ( v1 )
    goto LABEL_5;
  RegCloseKey(phkResult);
  phkResult = 0;
  v1 = RegCreateKeyExW(hKey, L"TypeLib", 0, 0, 0, 0xF003Fu, 0, &phkResult, 0);
  v0 = v1;
  v2 = v1 <= 0;
  if ( v1 )
    goto LABEL_5;
  v1 = RegSetValueExW(phkResult, &ValueName, 0, 1u, L"{a8ac6f3f-3165-41af-9911-511d0772708e}", 0x4Eu);
  v0 = v1;
  v2 = v1 <= 0;
  if ( v1 )
    goto LABEL_5;
  RegCloseKey(phkResult);
  phkResult = 0;
  v1 = RegCreateKeyExW(hKey, L"Version", 0, 0, 0, 0xF003Fu, 0, &phkResult, 0);
  v0 = v1;
  v2 = v1 <= 0;
  if ( v1 )
    goto LABEL_5;
  v1 = RegSetValueExW(phkResult, &ValueName, 0, 1u, L"1.0", 8u);
  v0 = v1;
  v2 = v1 <= 0;
  if ( v1 )
    goto LABEL_5;
  RegCloseKey(phkResult);
  phkResult = 0;
  RegCloseKey(hKey);
  hKey = 0;
  v0 = STRU::Copy((STRU *)v10, L"TypeLib");
  if ( v0 < 0 )
    goto LABEL_8;
  v0 = STRU::Append((STRU *)v10, L"\\");
  if ( v0 < 0 )
    goto LABEL_8;
  v0 = STRU::Append((STRU *)v10, L"{a8ac6f3f-3165-41af-9911-511d0772708e}");
  if ( v0 < 0 )
    goto LABEL_8;
  v0 = STRU::Append((STRU *)v10, L"\\");
  if ( v0 < 0 )
    goto LABEL_8;
  v0 = STRU::Append((STRU *)v10, L"1.0");
  if ( v0 < 0 )
    goto LABEL_8;
  v1 = RegCreateKeyExW(HKEY_CLASSES_ROOT, lpSubKey, 0, 0, 0, 0xF003Fu, 0, &hKey, 0);
  v0 = v1;
  v2 = v1 <= 0;
  if ( v1 )
    goto LABEL_5;
  v1 = RegSetValueExW(hKey, &ValueName, 0, 1u, L"IIS FtpHost Type Library", 0x32u);
  v0 = v1;
  v2 = v1 <= 0;
  if ( v1 )
    goto LABEL_5;
  v1 = RegCreateKeyExW(hKey, L"0\\win32", 0, 0, 0, 0xF003Fu, 0, &phkResult, 0);
  v0 = v1;
  v2 = v1 <= 0;
  if ( v1 )
    goto LABEL_5;
  v1 = RegSetValueExW(phkResult, &ValueName, 0, 2u, L"%SystemRoot%\\system32\\inetsrv\\ftphost.dll", 0x54u);
  v0 = v1;
  v2 = v1 <= 0;
  if ( v1 )
    goto LABEL_5;
  RegCloseKey(phkResult);
  phkResult = 0;
  v1 = RegCreateKeyExW(hKey, L"FLAGS", 0, 0, 0, 0xF003Fu, 0, &phkResult, 0);
  v0 = v1;
  v2 = v1 <= 0;
  if ( v1 )
    goto LABEL_5;
  v1 = RegSetValueExW(phkResult, &ValueName, 0, 1u, L"0", 4u);
  v0 = v1;
  v2 = v1 <= 0;
  if ( v1 )
    goto LABEL_5;
  RegCloseKey(phkResult);
  phkResult = 0;
  v1 = RegCreateKeyExW(hKey, L"HELPDIR", 0, 0, 0, 0xF003Fu, 0, &phkResult, 0);
  v0 = v1;
  v2 = v1 <= 0;
  if ( v1
    || (v1 = RegSetValueExW(phkResult, &ValueName, 0, 2u, L"%SystemRoot%\\system32\\inetsrv", 0x3Cu),
        v0 = v1,
        v2 = v1 <= 0,
        v1) )
  {
LABEL_5:
    if ( v2 )
      goto LABEL_7;
    goto LABEL_6;
  }
  RegCloseKey(phkResult);
  phkResult = 0;
  RegCloseKey(hKey);
  hKey = 0;
  v0 = STRU::Copy((STRU *)v10, L"CLSID");
  if ( v0 < 0 )
    goto LABEL_8;
  v0 = STRU::Append((STRU *)v10, L"\\");
  if ( v0 < 0 )
    goto LABEL_8;
  v0 = STRU::Append((STRU *)v10, L"{ee673f07-b5ab-4036-80ae-59c7b5d32d89}");
  if ( v0 < 0 )
    goto LABEL_8;
  v1 = RegCreateKeyExW(HKEY_CLASSES_ROOT, lpSubKey, 0, 0, 0, 0xF003Fu, 0, &hKey, 0);
  v5 = v1 <= 0;
  if ( v1 )
    goto LABEL_73;
  v1 = RegSetValueExW(hKey, &ValueName, 0, 1u, L"IIS Ftp Host Interface ProxyStub", 0x42u);
  v5 = v1 <= 0;
  if ( v1 )
    goto LABEL_73;
  v1 = RegCreateKeyExW(hKey, L"InprocServer32", 0, 0, 0, 0xF003Fu, 0, &phkResult, 0);
  v5 = v1 <= 0;
  if ( v1 )
    goto LABEL_73;
  v1 = RegSetValueExW(phkResult, &ValueName, 0, 2u, L"%SystemRoot%\\system32\\inetsrv\\ftphost.dll", 0x54u);
  v5 = v1 <= 0;
  if ( v1 )
    goto LABEL_73;
  v1 = RegSetValueExW(phkResult, L"ThreadingModel", 0, 1u, L"Both", 0xAu);
  v5 = v1 <= 0;
  if ( v1 )
    goto LABEL_73;
  RegCloseKey(phkResult);
  phkResult = 0;
  RegCloseKey(hKey);
  hKey = 0;
  STRU::Copy((STRU *)v10, L"Interface");
  STRU::Append((STRU *)v10, L"\\");
  STRU::Append((STRU *)v10, L"{ee673f07-b5ab-4036-80ae-59c7b5d32d89}");
  v1 = RegCreateKeyExW(HKEY_CLASSES_ROOT, lpSubKey, 0, 0, 0, 0xF003Fu, 0, &hKey, 0);
  v5 = v1 <= 0;
  if ( v1
    || (v1 = RegSetValueExW(hKey, &ValueName, 0, 1u, L"IFtpHost", 0x12u), v5 = v1 <= 0, v1)
    || (v1 = RegCreateKeyExW(hKey, L"ProxyStubClsid32", 0, 0, 0, 0xF003Fu, 0, &phkResult, 0), v5 = v1 <= 0, v1)
    || (v1 = RegSetValueExW(phkResult, &ValueName, 0, 1u, L"{ee673f07-b5ab-4036-80ae-59c7b5d32d89}", 0x4Eu),
        v5 = v1 <= 0,
        v1) )
  {
LABEL_73:
    if ( v5 )
    {
      v0 = v1;
LABEL_7:
      if ( v0 >= 0 )
      {
LABEL_10:
        v3 = hKey;
        goto LABEL_11;
      }
LABEL_8:
      if ( (g_dwDebugFlags & 0xF) != 0 )
        PuDbgPrintError(
          g_pDebug,
          "inetsrv\\iis\\iisrearc\\ftp\\server\\extensibility\\ftphost\\main.cxx",
          1022,
          "DllRegisterServer",
          v0,
          "DllRegisterServer failed\n");
      goto LABEL_10;
    }
LABEL_6:
    v0 = (unsigned __int16)v1 | 0x80070000;
    goto LABEL_7;
  }
  RegCloseKey(phkResult);
  phkResult = 0;
  RegCloseKey(hKey);
  v3 = 0;
  hKey = 0;
LABEL_11:
  if ( v3 )
  {
    RegCloseKey(v3);
    hKey = 0;
  }
  if ( phkResult )
  {
    RegCloseKey(phkResult);
    phkResult = 0;
  }
  STRU::~STRU((STRU *)v10);
  BUFFER::~BUFFER((BUFFER *)v12);
  return v0;
}

```

## disassembly

```asm
0x180001bb0  push    rbp
0x180001bb2  push    rbx
0x180001bb3  push    rsi
0x180001bb4  push    rdi
0x180001bb5  push    r12
0x180001bb7  push    r13
0x180001bb9  push    r14
0x180001bbb  push    r15
0x180001bbd  lea     rbp, [rsp-1E8h]
0x180001bc5  sub     rsp, 2E8h
0x180001bcc  mov     rax, cs:__security_cookie
0x180001bd3  xor     rax, rsp
0x180001bd6  mov     [rbp+220h+var_50], rax
0x180001bdd  xor     edi, edi
0x180001bdf  mov     [rbp+220h+var_258], 20h ; ' '
0x180001be6  lea     rax, [rbp+220h+var_280]
0x180001bea  mov     [rsp+320h+hKey], rdi
0x180001bef  xor     edx, edx; Val
0x180001bf1  mov     [rsp+320h+var_2D0], rdi
0x180001bf6  mov     r8d, 200h; Size
0x180001bfc  mov     [rbp+220h+var_280], rdi
0x180001c00  lea     rcx, [rbp+220h+var_250]; void *
0x180001c04  mov     [rbp+220h+lpData], rax
0x180001c08  lea     esi, [rdi+1]
0x180001c0b  mov     [rbp+220h+var_254], 100h
0x180001c11  mov     [rsp+320h+cbData], edi
0x180001c15  mov     dword ptr [rsp+320h+Data], 6
0x180001c1d  call    memset_0
0x180001c22  mov     r8d, 100h
0x180001c28  lea     rdx, [rbp+220h+var_250]
0x180001c2c  lea     rcx, [rsp+320h+var_2B8]
0x180001c31  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180001c37  lea     rdx, aAppid_1; "AppID"
0x180001c3e  lea     rcx, [rsp+320h+var_2B8]
0x180001c43  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180001c49  mov     ebx, eax
0x180001c4b  test    eax, eax
0x180001c4d  js      loc_180001CD9
0x180001c53  lea     rdx, asc_180007DB8; "\\"
0x180001c5a  lea     rcx, [rsp+320h+var_2B8]
0x180001c5f  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180001c65  mov     ebx, eax
0x180001c67  test    eax, eax
0x180001c69  js      short loc_180001CD9
0x180001c6b  lea     r13, a315fa5933cf543; "{315fa593-3cf5-4310-887b-3977a578488a}"
0x180001c72  mov     rdx, r13
0x180001c75  lea     rcx, [rsp+320h+var_2B8]
0x180001c7a  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180001c80  mov     ebx, eax
0x180001c82  test    eax, eax
0x180001c84  js      short loc_180001CD9
0x180001c86  mov     rdx, [rbp+220h+lpSubKey]; lpSubKey
0x180001c8a  lea     rax, [rsp+320h+hKey]
0x180001c8f  mov     [rsp+320h+lpdwDisposition], rdi; lpdwDisposition
0x180001c94  mov     r15d, 0F003Fh
0x180001c9a  mov     [rsp+320h+phkResult], rax; phkResult
0x180001c9f  xor     r9d, r9d; lpClass
0x180001ca2  mov     [rsp+320h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x180001ca7  xor     r8d, r8d; Reserved
0x180001caa  mov     [rsp+320h+samDesired], r15d; samDesired
0x180001caf  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180001cb6  mov     [rsp+320h+dwOptions], edi; dwOptions
0x180001cba  call    cs:__imp_RegCreateKeyExW
0x180001cc0  mov     ebx, eax
0x180001cc2  test    eax, eax
0x180001cc4  jz      loc_180001D77
0x180001cca  jle     short loc_180001CD5
0x180001ccc  movzx   ebx, ax
0x180001ccf  or      ebx, 80070000h
0x180001cd5  test    ebx, ebx
0x180001cd7  jns     short loc_180001D13
0x180001cd9  test    cs:g_dwDebugFlags, 0Fh
0x180001ce0  jz      short loc_180001D13
0x180001ce2  mov     rcx, cs:g_pDebug
0x180001ce9  lea     rax, aDllregisterser_1; "DllRegisterServer failed\n"
0x180001cf0  mov     qword ptr [rsp+320h+samDesired], rax
0x180001cf5  lea     r9, aDllregisterser_0; "DllRegisterServer"
0x180001cfc  mov     r8d, 3FEh
0x180001d02  mov     [rsp+320h+dwOptions], ebx
0x180001d06  lea     rdx, aInetsrvIisIisr_1; "inetsrv\\iis\\iisrearc\\ftp\\server\\ex"...
0x180001d0d  call    cs:__imp_PuDbgPrintError
0x180001d13  mov     rcx, [rsp+320h+hKey]; hKey
0x180001d18  test    rcx, rcx
0x180001d1b  jz      short loc_180001D28
0x180001d1d  call    cs:__imp_RegCloseKey
0x180001d23  mov     [rsp+320h+hKey], rdi
0x180001d28  mov     rcx, [rsp+320h+var_2D0]; hKey
0x180001d2d  test    rcx, rcx
0x180001d30  jz      short loc_180001D3D
0x180001d32  call    cs:__imp_RegCloseKey
0x180001d38  mov     [rsp+320h+var_2D0], rdi
0x180001d3d  lea     rcx, [rsp+320h+var_2B8]
0x180001d42  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180001d48  lea     rcx, [rbp+220h+var_280]
0x180001d4c  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180001d52  mov     eax, ebx
0x180001d54  mov     rcx, [rbp+220h+var_50]
0x180001d5b  xor     rcx, rsp; StackCookie
0x180001d5e  call    __security_check_cookie
0x180001d63  add     rsp, 2E8h
0x180001d6a  pop     r15
0x180001d6c  pop     r14
0x180001d6e  pop     r13
0x180001d70  pop     r12
0x180001d72  pop     rdi
0x180001d73  pop     rsi
0x180001d74  pop     rbx
0x180001d75  pop     rbp
0x180001d76  retn
0x180001d77  mov     rcx, [rsp+320h+hKey]; hKey
0x180001d7c  lea     rax, Data; "IIS FtpHost"
0x180001d83  lea     r14, ValueName
0x180001d8a  mov     [rsp+320h+samDesired], 18h; cbData
0x180001d92  mov     rdx, r14; lpValueName
0x180001d95  mov     qword ptr [rsp+320h+dwOptions], rax; int
0x180001d9a  mov     r9d, esi; dwType
0x180001d9d  xor     r8d, r8d; Reserved
0x180001da0  call    cs:__imp_RegSetValueExW
0x180001da6  mov     ebx, eax
0x180001da8  test    eax, eax
0x180001daa  jnz     loc_180001CCA
0x180001db0  lea     r8d, [rax+9]; unsigned int
0x180001db4  lea     rdx, [rsp+320h+cbData]; unsigned int *
0x180001db9  lea     rcx, [rbp+220h+var_280]; struct BUFFER *
0x180001dbd  call    ?CreateSecurityDescriptorForCom@@YAJPEAVBUFFER@@PEAKKHH@Z; CreateSecurityDescriptorForCom(BUFFER *,ulong *,ulong,int,int)
0x180001dc2  mov     ebx, eax
0x180001dc4  test    eax, eax
0x180001dc6  js      loc_180001CD9
0x180001dcc  mov     rcx, [rbp+220h+lpData]
0x180001dd0  lea     rdx, aLaunchpermissi; "LaunchPermission"
0x180001dd7  mov     eax, [rsp+320h+cbData]
0x180001ddb  mov     r12d, 3
0x180001de1  mov     [rsp+320h+samDesired], eax; cbData
0x180001de5  mov     r9d, r12d; dwType
0x180001de8  mov     qword ptr [rsp+320h+dwOptions], rcx; int
0x180001ded  xor     r8d, r8d; Reserved
0x180001df0  mov     rcx, [rsp+320h+hKey]; hKey
0x180001df5  call    cs:__imp_RegSetValueExW
0x180001dfb  mov     ebx, eax
0x180001dfd  test    eax, eax
0x180001dff  jnz     loc_180001CCA
0x180001e05  mov     r8d, r12d; unsigned int
0x180001e08  lea     rdx, [rsp+320h+cbData]; unsigned int *
0x180001e0d  lea     rcx, [rbp+220h+var_280]; struct BUFFER *
0x180001e11  call    ?CreateSecurityDescriptorForCom@@YAJPEAVBUFFER@@PEAKKHH@Z; CreateSecurityDescriptorForCom(BUFFER *,ulong *,ulong,int,int)
0x180001e16  mov     ebx, eax
0x180001e18  test    eax, eax
0x180001e1a  js      loc_180001CD9
0x180001e20  mov     rcx, [rbp+220h+lpData]
0x180001e24  lea     rdx, aAccesspermissi; "AccessPermission"
0x180001e2b  mov     eax, [rsp+320h+cbData]
0x180001e2f  mov     r9d, r12d; dwType
0x180001e32  mov     [rsp+320h+samDesired], eax; cbData
0x180001e36  xor     r8d, r8d; Reserved
0x180001e39  mov     qword ptr [rsp+320h+dwOptions], rcx; lpData
0x180001e3e  mov     rcx, [rsp+320h+hKey]; hKey
0x180001e43  call    cs:__imp_RegSetValueExW
0x180001e49  mov     ebx, eax
0x180001e4b  test    eax, eax
0x180001e4d  jnz     loc_180001CCA
0x180001e53  mov     rcx, [rsp+320h+hKey]; hKey
0x180001e58  lea     rdx, aDllsurrogate; "DllSurrogate"
0x180001e5f  mov     [rsp+320h+samDesired], 2; cbData
0x180001e67  mov     r9d, esi; dwType
0x180001e6a  xor     r8d, r8d; Reserved
0x180001e6d  mov     qword ptr [rsp+320h+dwOptions], r14; lpData
0x180001e72  call    cs:__imp_RegSetValueExW
0x180001e78  mov     ebx, eax
0x180001e7a  test    eax, eax
0x180001e7c  jnz     loc_180001CCA
0x180001e82  lea     ecx, [rax+4]
0x180001e85  xor     r8d, r8d; Reserved
0x180001e88  mov     [rsp+320h+samDesired], ecx; cbData
0x180001e8c  lea     rax, [rsp+320h+Data]
0x180001e91  mov     r9d, ecx; dwType
0x180001e94  mov     qword ptr [rsp+320h+dwOptions], rax; lpData
0x180001e99  mov     rcx, [rsp+320h+hKey]; hKey
0x180001e9e  lea     rdx, aAuthentication; "AuthenticationLevel"
0x180001ea5  call    cs:__imp_RegSetValueExW
0x180001eab  mov     ebx, eax
0x180001ead  test    eax, eax
0x180001eaf  jnz     loc_180001CCA
0x180001eb5  mov     rcx, [rsp+320h+hKey]; hKey
0x180001eba  call    cs:__imp_RegCloseKey
0x180001ec0  mov     [rsp+320h+lpdwDisposition], rdi; lpdwDisposition
0x180001ec5  lea     rax, [rsp+320h+hKey]
0x180001eca  mov     [rsp+320h+phkResult], rax; phkResult
0x180001ecf  lea     rdx, SubKey; "IISFtpHost.IISFtpHost"
0x180001ed6  mov     [rsp+320h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x180001edb  xor     r9d, r9d; lpClass
0x180001ede  mov     [rsp+320h+samDesired], r15d; samDesired
0x180001ee3  xor     r8d, r8d; Reserved
0x180001ee6  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180001eed  mov     [rsp+320h+dwOptions], edi; dwOptions
0x180001ef1  mov     [rsp+320h+hKey], rdi
0x180001ef6  call    cs:__imp_RegCreateKeyExW
0x180001efc  mov     ebx, eax
0x180001efe  test    eax, eax
0x180001f00  jnz     loc_180001CCA
0x180001f06  mov     rcx, [rsp+320h+hKey]; hKey
0x180001f0b  lea     r12d, [rax+24h]
0x180001f0f  lea     rax, aIisFtphostClas; "IIS FtpHost Class"
0x180001f16  mov     [rsp+320h+samDesired], r12d; cbData
0x180001f1b  mov     r9d, esi; dwType
0x180001f1e  mov     qword ptr [rsp+320h+dwOptions], rax; lpData
0x180001f23  xor     r8d, r8d; Reserved
0x180001f26  mov     rdx, r14; lpValueName
0x180001f29  call    cs:__imp_RegSetValueExW
0x180001f2f  mov     ebx, eax
0x180001f31  test    eax, eax
0x180001f33  jnz     loc_180001CCA
0x180001f39  mov     rcx, [rsp+320h+hKey]; hKey
0x180001f3e  lea     rax, [rsp+320h+var_2D0]
0x180001f43  mov     [rsp+320h+lpdwDisposition], rdi; lpdwDisposition
0x180001f48  lea     rdx, aCurver; "CurVer"
0x180001f4f  mov     [rsp+320h+phkResult], rax; phkResult
0x180001f54  xor     r9d, r9d; lpClass
0x180001f57  mov     [rsp+320h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x180001f5c  xor     r8d, r8d; Reserved
0x180001f5f  mov     [rsp+320h+samDesired], r15d; samDesired
0x180001f64  mov     [rsp+320h+dwOptions], edi; dwOptions
0x180001f68  call    cs:__imp_RegCreateKeyExW
0x180001f6e  mov     ebx, eax
0x180001f70  test    eax, eax
0x180001f72  jnz     loc_180001CCA
0x180001f78  mov     rcx, [rsp+320h+var_2D0]; hKey
0x180001f7d  lea     rax, aIisftphostIisf_0; "IISFtpHost.IISFtpHost.1"
0x180001f84  mov     [rsp+320h+samDesired], 30h ; '0'; cbData
0x180001f8c  mov     r9d, esi; dwType
0x180001f8f  xor     r8d, r8d; Reserved
0x180001f92  mov     qword ptr [rsp+320h+dwOptions], rax; lpData
0x180001f97  mov     rdx, r14; lpValueName
0x180001f9a  call    cs:__imp_RegSetValueExW
0x180001fa0  mov     ebx, eax
0x180001fa2  test    eax, eax
0x180001fa4  jnz     loc_180001CCA
0x180001faa  mov     rcx, [rsp+320h+var_2D0]; hKey
0x180001faf  call    cs:__imp_RegCloseKey
0x180001fb5  mov     rcx, [rsp+320h+hKey]; hKey
0x180001fba  mov     [rsp+320h+var_2D0], rdi
0x180001fbf  call    cs:__imp_RegCloseKey
0x180001fc5  mov     [rsp+320h+lpdwDisposition], rdi; lpdwDisposition
0x180001fca  lea     rax, [rsp+320h+hKey]
0x180001fcf  mov     [rsp+320h+phkResult], rax; phkResult
0x180001fd4  lea     rdx, aIisftphostIisf_0; "IISFtpHost.IISFtpHost.1"
0x180001fdb  mov     [rsp+320h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x180001fe0  xor     r9d, r9d; lpClass
0x180001fe3  mov     [rsp+320h+samDesired], r15d; samDesired
0x180001fe8  xor     r8d, r8d; Reserved
0x180001feb  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180001ff2  mov     [rsp+320h+dwOptions], edi; dwOptions
0x180001ff6  mov     [rsp+320h+hKey], rdi
0x180001ffb  call    cs:__imp_RegCreateKeyExW
0x180002001  mov     ebx, eax
0x180002003  test    eax, eax
0x180002005  jnz     loc_180001CCA
0x18000200b  mov     rcx, [rsp+320h+hKey]; hKey
0x180002010  lea     rax, aIisFtphostClas; "IIS FtpHost Class"
0x180002017  mov     [rsp+320h+samDesired], r12d; cbData
0x18000201c  mov     r9d, esi; dwType
0x18000201f  xor     r8d, r8d; Reserved
0x180002022  mov     qword ptr [rsp+320h+dwOptions], rax; lpData
0x180002027  mov     rdx, r14; lpValueName
0x18000202a  call    cs:__imp_RegSetValueExW
0x180002030  mov     ebx, eax
0x180002032  test    eax, eax
0x180002034  jnz     loc_180001CCA
0x18000203a  mov     rcx, [rsp+320h+hKey]; hKey
0x18000203f  lea     rax, [rsp+320h+var_2D0]
0x180002044  mov     [rsp+320h+lpdwDisposition], rdi; lpdwDisposition
0x180002049  lea     rdx, aClsid; "CLSID"
0x180002050  mov     [rsp+320h+phkResult], rax; phkResult
0x180002055  xor     r9d, r9d; lpClass
0x180002058  mov     [rsp+320h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x18000205d  xor     r8d, r8d; Reserved
0x180002060  mov     [rsp+320h+samDesired], r15d; samDesired
0x180002065  mov     [rsp+320h+dwOptions], edi; dwOptions
0x180002069  call    cs:__imp_RegCreateKeyExW
0x18000206f  mov     ebx, eax
0x180002071  test    eax, eax
0x180002073  jnz     loc_180001CCA
0x180002079  mov     rcx, [rsp+320h+var_2D0]; hKey
0x18000207e  lea     r12d, [rax+4Eh]
0x180002082  mov     [rsp+320h+samDesired], r12d; cbData
0x180002087  mov     r9d, esi; dwType
0x18000208a  xor     r8d, r8d; Reserved
0x18000208d  mov     qword ptr [rsp+320h+dwOptions], r13; lpData
0x180002092  mov     rdx, r14; lpValueName
0x180002095  call    cs:__imp_RegSetValueExW
0x18000209b  mov     ebx, eax
0x18000209d  test    eax, eax
0x18000209f  jnz     loc_180001CCA
0x1800020a5  mov     rcx, [rsp+320h+var_2D0]; hKey
0x1800020aa  call    cs:__imp_RegCloseKey
0x1800020b0  mov     rcx, [rsp+320h+hKey]; hKey
0x1800020b5  mov     [rsp+320h+var_2D0], rdi
0x1800020ba  call    cs:__imp_RegCloseKey
0x1800020c0  lea     rdx, aClsid_0; "CLSID"
0x1800020c7  mov     [rsp+320h+hKey], rdi
0x1800020cc  lea     rcx, [rsp+320h+var_2B8]
  ... truncated ...
```
