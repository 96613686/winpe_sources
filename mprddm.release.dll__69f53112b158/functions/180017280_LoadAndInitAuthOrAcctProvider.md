# LoadAndInitAuthOrAcctProvider

- ea: `0x180017280`
- end: `0x180017fbf`
- name: `LoadAndInitAuthOrAcctProvider`
- size: `3391`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18001bf40`

## callees

- `0x180007c0c`
- `0x180017280`
- `0x18004df80`
- `0x18004e290`
- `0x180092aaa`
- `0x180092ad0`
- `0x180095010`

## import_xrefs

- `msvcrt!_itoa_s` at `0x180017c8d`
- `msvcrt!_itoa_s` at `0x180017c8d`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x180017b05`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x180017b83`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x180017b05`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x180017b83`
- `KERNEL32!GetProcAddress` at `0x180017cf0`
- `KERNEL32!GetProcAddress` at `0x180017d30`
- `KERNEL32!GetProcAddress` at `0x180017d56`
- `KERNEL32!GetProcAddress` at `0x180017d7c`
- `KERNEL32!GetProcAddress` at `0x180017da2`
- `KERNEL32!GetProcAddress` at `0x180017dd1`
- `KERNEL32!GetProcAddress` at `0x180017e11`
- `KERNEL32!GetProcAddress` at `0x180017e37`
- `KERNEL32!GetProcAddress` at `0x180017e5d`
- `KERNEL32!GetProcAddress` at `0x180017e83`
- `KERNEL32!GetProcAddress` at `0x180017ea9`
- `KERNEL32!GetProcAddress` at `0x180017ecf`
- `KERNEL32!GetProcAddress` at `0x180017cf0`
- `KERNEL32!GetProcAddress` at `0x180017d30`
- `KERNEL32!GetProcAddress` at `0x180017d56`
- `KERNEL32!GetProcAddress` at `0x180017d7c`
- `KERNEL32!GetProcAddress` at `0x180017da2`
- `KERNEL32!GetProcAddress` at `0x180017dd1`
- `KERNEL32!GetProcAddress` at `0x180017e11`
- `KERNEL32!GetProcAddress` at `0x180017e37`
- `KERNEL32!GetProcAddress` at `0x180017e5d`
- `KERNEL32!GetProcAddress` at `0x180017e83`
- `KERNEL32!GetProcAddress` at `0x180017ea9`
- `KERNEL32!GetProcAddress` at `0x180017ecf`
- `KERNEL32!GetComputerNameW` at `0x1800178ca`
- `KERNEL32!GetComputerNameW` at `0x1800178ca`
- `KERNEL32!LoadLibraryExW` at `0x180017bca`
- `KERNEL32!LoadLibraryExW` at `0x180017bca`
- `KERNEL32!HeapAlloc` at `0x1800175e5`
- `KERNEL32!HeapAlloc` at `0x180017a3b`
- `KERNEL32!HeapAlloc` at `0x180017b37`
- `KERNEL32!HeapAlloc` at `0x1800175e5`
- `KERNEL32!HeapAlloc` at `0x180017a3b`
- `KERNEL32!HeapAlloc` at `0x180017b37`
- `KERNEL32!GetLastError` at `0x1800175fe`
- `KERNEL32!GetLastError` at `0x1800178de`
- `KERNEL32!GetLastError` at `0x180017a54`
- `KERNEL32!GetLastError` at `0x180017b17`
- `KERNEL32!GetLastError` at `0x180017b50`
- `KERNEL32!GetLastError` at `0x180017b95`
- `KERNEL32!GetLastError` at `0x180017be2`
- `KERNEL32!GetLastError` at `0x1800175fe`
- `KERNEL32!GetLastError` at `0x1800178de`
- `KERNEL32!GetLastError` at `0x180017a54`
- `KERNEL32!GetLastError` at `0x180017b17`
- `KERNEL32!GetLastError` at `0x180017b50`
- `KERNEL32!GetLastError` at `0x180017b95`
- `KERNEL32!GetLastError` at `0x180017be2`
- `KERNEL32!HeapFree` at `0x1800174d6`
- `KERNEL32!HeapFree` at `0x1800174f3`
- `KERNEL32!HeapFree` at `0x180017510`
- `KERNEL32!HeapFree` at `0x1800174d6`
- `KERNEL32!HeapFree` at `0x1800174f3`
- `KERNEL32!HeapFree` at `0x180017510`
- `KERNEL32!WideCharToMultiByte` at `0x180017c2b`
- `KERNEL32!WideCharToMultiByte` at `0x180017c2b`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180017595`
- `ADVAPI32!RegQueryInfoKeyW` at `0x1800179ef`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180017595`
- `ADVAPI32!RegQueryInfoKeyW` at `0x1800179ef`
- `ADVAPI32!RegOpenKeyExW` at `0x18001736c`
- `ADVAPI32!RegOpenKeyExW` at `0x18001746b`
- `ADVAPI32!RegOpenKeyExW` at `0x18001774a`
- `ADVAPI32!RegOpenKeyExW` at `0x180017948`
- `ADVAPI32!RegOpenKeyExW` at `0x18001736c`
- `ADVAPI32!RegOpenKeyExW` at `0x18001746b`
- `ADVAPI32!RegOpenKeyExW` at `0x18001774a`
- `ADVAPI32!RegOpenKeyExW` at `0x180017948`
- `ADVAPI32!RegQueryValueExW` at `0x1800173f5`
- `ADVAPI32!RegQueryValueExW` at `0x180017636`
- `ADVAPI32!RegQueryValueExW` at `0x180017788`
- `ADVAPI32!RegQueryValueExW` at `0x180017abe`
- `ADVAPI32!RegQueryValueExW` at `0x1800173f5`
- `ADVAPI32!RegQueryValueExW` at `0x180017636`
- `ADVAPI32!RegQueryValueExW` at `0x180017788`
- `ADVAPI32!RegQueryValueExW` at `0x180017abe`
- `ADVAPI32!RegCloseKey` at `0x18001741c`
- `ADVAPI32!RegCloseKey` at `0x1800174a4`
- `ADVAPI32!RegCloseKey` at `0x1800174b9`
- `ADVAPI32!RegCloseKey` at `0x1800177a7`
- `ADVAPI32!RegCloseKey` at `0x18001741c`
- `ADVAPI32!RegCloseKey` at `0x1800174a4`
- `ADVAPI32!RegCloseKey` at `0x1800174b9`
- `ADVAPI32!RegCloseKey` at `0x1800177a7`
- `rtutils!RouterLogEventW` at `0x1800173b2`
- `rtutils!RouterLogEventW` at `0x180017671`
- `rtutils!RouterLogEventW` at `0x180017990`
- `rtutils!RouterLogEventW` at `0x180017a86`
- `rtutils!RouterLogEventW` at `0x1800173b2`
- `rtutils!RouterLogEventW` at `0x180017671`
- `rtutils!RouterLogEventW` at `0x180017990`
- `rtutils!RouterLogEventW` at `0x180017a86`

## string_xrefs

- `0x1800172b7`: `System\CurrentControlSet\Services\RemoteAccess\Parameters`
- `0x1800173d7`: `QuarantineInstalled`
- `0x180017444`: `SYSTEM\CurrentControlSet\Services\RemoteAccess\Authentication\Providers`
- `0x18001743a`: `SYSTEM\CurrentControlSet\Services\RemoteAccess\Accounting\Providers`
- `0x180017964`: `SYSTEM\CurrentControlSet\Services\RemoteAccess\Accounting\Providers`
- `0x18001773c`: `SYSTEM\CurrentControlSet\Services\RemoteAccess\Accounting`
- `0x180017d98`: `RasAuthConfigChangeNotification`
- `0x180017ec5`: `RasAcctConfigChangeNotification`

## pseudocode

```c
__int64 __fastcall LoadAndInitAuthOrAcctProvider(
        int a1,
        DWORD a2,
        BYTE *a3,
        FARPROC *a4,
        FARPROC *a5,
        __int64 a6,
        FARPROC *a7,
        FARPROC *a8,
        FARPROC *a9,
        FARPROC *a10,
        WCHAR *a11)
{
  LPBYTE v11; // r15
  BYTE *v13; // rdi
  HMODULE Library; // rsi
  BOOL v15; // r13d
  LSTATUS v16; // eax
  DWORD LastError; // ebx
  WCHAR *v18; // r15
  __int64 v19; // r14
  WCHAR *v20; // r15
  LSTATUS v22; // eax
  LSTATUS v23; // eax
  __int64 v24; // r8
  __int64 v25; // rax
  LPBYTE v26; // rbx
  int v27; // eax
  __int64 v28; // r8
  const wchar_t *v29; // rcx
  __int64 v30; // rax
  const wchar_t *v31; // rcx
  __int64 v32; // rax
  CHAR *v33; // rax
  LSTATUS v34; // eax
  LSTATUS v35; // eax
  DWORD v36; // eax
  DWORD v37; // r8d
  DWORD v38; // eax
  DWORD v39; // eax
  DWORD v40; // ebx
  WCHAR *v41; // rax
  DWORD v42; // eax
  DWORD v43; // eax
  __int64 v44; // rax
  int v45; // ecx
  FARPROC ProcAddress; // rax
  FARPROC v47; // rax
  FARPROC v48; // rax
  FARPROC v49; // rax
  LPWSTR v50; // rcx
  FARPROC v51; // rax
  FARPROC v52; // rax
  FARPROC v53; // rax
  FARPROC v54; // rax
  FARPROC v55; // rax
  __int64 (__fastcall *v56)(); // rax
  LPWSTR v57; // rcx
  DWORD dwErrorCode; // [rsp+28h] [rbp-D8h]
  BYTE *v59; // [rsp+60h] [rbp-A0h]
  WCHAR *v60; // [rsp+68h] [rbp-98h]
  BYTE *v61; // [rsp+70h] [rbp-90h]
  DWORD cbData; // [rsp+78h] [rbp-88h] BYREF
  DWORD Type; // [rsp+7Ch] [rbp-84h] BYREF
  LPWSTR plpszSubStringArray; // [rsp+80h] [rbp-80h] BYREF
  DWORD nSize; // [rsp+88h] [rbp-78h] BYREF
  LPBYTE lpData; // [rsp+90h] [rbp-70h]
  BYTE Data[4]; // [rsp+98h] [rbp-68h] BYREF
  DWORD cbMaxValueNameLen; // [rsp+9Ch] [rbp-64h] BYREF
  DWORD cValues; // [rsp+A0h] [rbp-60h] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+A4h] [rbp-5Ch] BYREF
  DWORD cSubKeys; // [rsp+A8h] [rbp-58h] BYREF
  HKEY phkResult; // [rsp+B0h] [rbp-50h] BYREF
  HKEY v73; // [rsp+B8h] [rbp-48h] BYREF
  HKEY v74; // [rsp+C0h] [rbp-40h] BYREF
  HKEY hKey; // [rsp+C8h] [rbp-38h] BYREF
  FARPROC *v76; // [rsp+D0h] [rbp-30h]
  FARPROC *v77; // [rsp+D8h] [rbp-28h]
  __int64 v78; // [rsp+E0h] [rbp-20h]
  FARPROC *v79; // [rsp+E8h] [rbp-18h]
  FARPROC *v80; // [rsp+F0h] [rbp-10h]
  FARPROC *v81; // [rsp+F8h] [rbp-8h]
  FARPROC *v82; // [rsp+100h] [rbp+0h]
  _BYTE v83[16]; // [rsp+108h] [rbp+8h] BYREF
  const wchar_t *v84; // [rsp+118h] [rbp+18h]
  int v85; // [rsp+120h] [rbp+20h]
  int v86; // [rsp+124h] [rbp+24h]
  int v87; // [rsp+128h] [rbp+28h] BYREF
  int v88; // [rsp+12Ch] [rbp+2Ch]
  CHAR *v89; // [rsp+130h] [rbp+30h]
  __int64 v90; // [rsp+138h] [rbp+38h]
  char *v91; // [rsp+140h] [rbp+40h]
  __int64 v92; // [rsp+148h] [rbp+48h]
  __int64 v93; // [rsp+150h] [rbp+50h]
  char v94[16]; // [rsp+158h] [rbp+58h] BYREF
  int v95; // [rsp+168h] [rbp+68h]
  CHAR MultiByteStr[16]; // [rsp+170h] [rbp+70h] BYREF
  WCHAR Buffer[16]; // [rsp+180h] [rbp+80h] BYREF

  v77 = a5;
  v11 = a3;
  v78 = a6;
  v79 = a7;
  v81 = a8;
  v80 = a9;
  v82 = a10;
  plpszSubStringArray = a11;
  phkResult = 0;
  v13 = 0;
  v73 = 0;
  Library = 0;
  v61 = 0;
  v15 = 0;
  v60 = 0;
  v59 = 0;
  cSubKeys = 0;
  cbMaxSubKeyLen = 0;
  cValues = 0;
  cbMaxValueNameLen = 0;
  cbData = 0;
  Type = 0;
  hKey = 0;
  *(_DWORD *)Data = 0;
  v76 = a4;
  lpData = a3;
  nSize = a2;
  v16 = RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"System\\CurrentControlSet\\Services\\RemoteAccess\\Parameters",
          0,
          0x20019u,
          &hKey);
  LastError = v16;
  if ( v16 )
  {
    plpszSubStringArray = (LPWSTR)L"System\\CurrentControlSet\\Services\\RemoteAccess\\Parameters";
    if ( dword_1800CF4E4 )
    {
LABEL_3:
      RouterLogEventW(hLogHandle, 1u, 0x4E84u, 1u, &plpszSubStringArray, v16);
LABEL_4:
      v13 = 0;
LABEL_5:
      v18 = 0;
      goto LABEL_18;
    }
    goto LABEL_17;
  }
  cbData = 4;
  if ( !RegQueryValueExW(hKey, L"QuarantineInstalled", 0, 0, Data, &cbData) )
    v15 = *(_DWORD *)Data == 1;
  if ( hKey )
    RegCloseKey(hKey);
  v19 = -1;
  if ( v15 && a1 )
  {
LABEL_69:
    v33 = (CHAR *)nSize;
    if ( nSize )
    {
      v87 = 4;
      v88 = 4;
    }
    else
    {
      nSize = 16;
      if ( !GetComputerNameW(Buffer, &nSize) )
        goto LABEL_71;
      WideCharToMultiByte(0, 0x400u, Buffer, -1, MultiByteStr, 16, 0, 0);
      v87 = 32;
      v44 = -1;
      do
        ++v44;
      while ( MultiByteStr[v44] );
      v88 = v44;
      v33 = MultiByteStr;
    }
    v89 = v33;
    if ( a1 )
    {
      v90 = 0;
      v91 = 0;
    }
    else
    {
      v45 = *(_DWORD *)v11;
      v95 = 0;
      *(_DWORD *)v11 = v45 + 1;
      *(_OWORD *)v94 = 0;
      _itoa_s(v45, v94, 0x14u, 10);
      LODWORD(v90) = 44;
      do
        ++v19;
      while ( v94[v19] );
      v92 = 0;
      v91 = v94;
      HIDWORD(v90) = v19;
      v93 = 0;
    }
    if ( v15 )
    {
      if ( a1 )
      {
        qword_1800CF580 = 0;
        LastError = RasAuthProviderInitialize(&v87, hLogHandle, (unsigned int)dword_1800CF4E4);
        if ( LastError )
          goto LABEL_72;
        qword_1800CF578 = (__int64)RasAuthProviderTerminate;
        *v76 = RasAuthProviderAuthenticateUser;
        *v77 = RasAuthProviderFreeAttributes;
        v56 = RasAuthConfigChangeNotification;
        v57 = (LPWSTR)v78;
      }
      else
      {
        qword_1800CF590 = 0;
        LastError = RasAcctProviderInitialize(&v87, hLogHandle, (unsigned int)dword_1800CF4E4);
        if ( LastError )
          goto LABEL_72;
        qword_1800CF588 = (__int64)RasAcctProviderTerminate;
        *v79 = RasAcctProviderStartAccounting;
        *v80 = RasAcctProviderStopAccounting;
        *v81 = RasAcctProviderInterimAccounting;
        *v82 = RasAuthProviderFreeAttributes;
        v56 = RasAcctConfigChangeNotification;
        v57 = plpszSubStringArray;
      }
      *(_QWORD *)v57 = v56;
      goto LABEL_72;
    }
    if ( a1 )
    {
      qword_1800CF580 = Library;
      ProcAddress = GetProcAddress(Library, "RasAuthProviderInitialize");
      if ( !ProcAddress )
        goto LABEL_71;
      LastError = ((__int64 (__fastcall *)(int *, HANDLE, _QWORD))ProcAddress)(
                    &v87,
                    hLogHandle,
                    (unsigned int)dword_1800CF4E4);
      if ( LastError )
        goto LABEL_72;
      qword_1800CF578 = (__int64)GetProcAddress(Library, "RasAuthProviderTerminate");
      if ( !qword_1800CF578
        || (v47 = GetProcAddress(Library, "RasAuthProviderAuthenticateUser"), (*v76 = v47) == 0)
        || (v48 = GetProcAddress(Library, "RasAuthProviderFreeAttributes"), (*v77 = v48) == 0) )
      {
LABEL_71:
        LastError = GetLastError();
LABEL_72:
        v13 = v59;
        Library = (HMODULE)v61;
        v18 = v60;
        goto LABEL_18;
      }
      v49 = GetProcAddress(Library, "RasAuthConfigChangeNotification");
      v50 = (LPWSTR)v78;
    }
    else
    {
      qword_1800CF590 = Library;
      v51 = GetProcAddress(Library, "RasAcctProviderInitialize");
      if ( !v51 )
        goto LABEL_71;
      LastError = ((__int64 (__fastcall *)(int *, HANDLE, _QWORD))v51)(&v87, hLogHandle, (unsigned int)dword_1800CF4E4);
      if ( LastError )
        goto LABEL_72;
      qword_1800CF588 = (__int64)GetProcAddress(Library, "RasAcctProviderTerminate");
      if ( !qword_1800CF588 )
        goto LABEL_71;
      v52 = GetProcAddress(Library, "RasAcctProviderStartAccounting");
      *v79 = v52;
      if ( !v52 )
        goto LABEL_71;
      v53 = GetProcAddress(Library, "RasAcctProviderStopAccounting");
      *v80 = v53;
      if ( !v53 )
        goto LABEL_71;
      v54 = GetProcAddress(Library, "RasAcctProviderInterimAccounting");
      *v81 = v54;
      if ( !v54 )
        goto LABEL_71;
      v55 = GetProcAddress(Library, "RasAcctProviderFreeAttributes");
      *v82 = v55;
      if ( !v55 )
        goto LABEL_71;
      v49 = GetProcAddress(Library, "RasAcctConfigChangeNotification");
      v50 = plpszSubStringArray;
    }
    *(_QWORD *)v50 = v49;
    if ( v49 )
      goto LABEL_72;
    goto LABEL_71;
  }
  v20 = L"SYSTEM\\CurrentControlSet\\Services\\RemoteAccess\\Authentication\\Providers";
  if ( !a1 )
    v20 = (WCHAR *)L"SYSTEM\\CurrentControlSet\\Services\\RemoteAccess\\Accounting\\Providers";
  v16 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v20, 0, 0x20019u, &phkResult);
  LastError = v16;
  if ( v16 )
  {
    plpszSubStringArray = v20;
    if ( dword_1800CF4E4 )
      goto LABEL_3;
    v13 = 0;
    goto LABEL_17;
  }
  v22 = RegQueryInfoKeyW(phkResult, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, &cValues, &cbMaxValueNameLen, &cbData, 0, 0);
  LastError = v22;
  if ( v22 )
  {
    if ( dword_1800CF4E4 )
      RouterLogEventW(hLogHandle, 1u, 0x4E22u, 0, 0, v22);
    goto LABEL_4;
  }
  cbData += 2;
  v59 = (BYTE *)HeapAlloc(hHeap, 8u, cbData);
  if ( !v59 )
  {
    LastError = GetLastError();
    goto LABEL_34;
  }
  v23 = RegQueryValueExW(phkResult, L"ActiveProvider", 0, &Type, v59, &cbData);
  LastError = v23;
  if ( v23 )
  {
LABEL_36:
    if ( !dword_1800CF4E4 )
    {
      v13 = v59;
LABEL_17:
      v18 = 0;
      Library = 0;
      goto LABEL_18;
    }
    RouterLogEventW(hLogHandle, 1u, 0x4E22u, 0, 0, v23);
LABEL_34:
    v13 = v59;
    goto LABEL_5;
  }
  if ( Type != 1 )
  {
    v23 = 1015;
    LastError = 1015;
    goto LABEL_36;
  }
  *(_WORD *)&v59[2 * ((unsigned __int64)cbData >> 1) - 2] = 0;
  v25 = -1;
  do
    ++v25;
  while ( *(_WORD *)&v59[2 * v25] );
  if ( !v25 )
  {
    LastError = a1 != 0 ? 0x3F7 : 0;
    if ( !a1 && (byte_1800CF404 & 0x10) != 0 )
    {
      do
        ++v19;
      while ( aNoAccountingIn[v19] );
      v84 = L"No Accounting  in SQM";
      v85 = 2 * v19 + 2;
      v86 = 0;
      McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceInfo, v24, 2, v83);
    }
    goto LABEL_34;
  }
  if ( a1 )
  {
    if ( !v15 )
      goto LABEL_78;
    goto LABEL_68;
  }
  v74 = 0;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"SYSTEM\\CurrentControlSet\\Services\\RemoteAccess\\Accounting",
          0,
          0x20019u,
          &v74) )
  {
    v26 = lpData;
    cbData = 4;
    if ( RegQueryValueExW(v74, L"AccountSessionIdStart", 0, &Type, lpData, &cbData) || Type != 4 )
      *(_DWORD *)v26 = 0;
    RegCloseKey(v74);
  }
  v27 = wcscmp_0((const wchar_t *)v59, L"{1AA7F840-C7F5-11D0-A376-00C04FC9DA04}");
  if ( v15 )
  {
    if ( v27 )
    {
      if ( (byte_1800CF404 & 0x10) == 0 )
        goto LABEL_68;
      v31 = L"Windows Accounting in SQM";
      v32 = -1;
      do
        ++v32;
      while ( aWindowsAccount[v32] );
      goto LABEL_67;
    }
    if ( (byte_1800CF404 & 0x10) != 0 )
    {
      v31 = L"Radius Accounting in SQM";
      v32 = -1;
      do
        ++v32;
      while ( aRadiusAccounti[v32] );
LABEL_67:
      v84 = v31;
      v85 = 2 * v32 + 2;
      v86 = 0;
      McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceInfo, v28, 2, v83);
    }
LABEL_68:
    v11 = lpData;
    goto LABEL_69;
  }
  if ( !v27 )
  {
    dword_1800CF4E0 |= 2u;
    if ( (byte_1800CF404 & 0x10) == 0 )
      goto LABEL_78;
    v29 = L"Radius Accounting in SQM";
    v30 = -1;
    do
      ++v30;
    while ( aRadiusAccounti[v30] );
    goto LABEL_58;
  }
  if ( (byte_1800CF404 & 0x10) != 0 )
  {
    v29 = L"Windows Accounting  in SQM";
    v30 = -1;
    do
      ++v30;
    while ( aWindowsAccount_0[v30] );
LABEL_58:
    v84 = v29;
    v85 = 2 * v30 + 2;
    v86 = 0;
    McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceInfo, v28, 2, v83);
  }
LABEL_78:
  v34 = RegOpenKeyExW(phkResult, (LPCWSTR)v59, 0, 0x20019u, &v73);
  v18 = 0;
  LastError = v34;
  if ( v34 )
  {
    plpszSubStringArray = (LPWSTR)L"SYSTEM\\CurrentControlSet\\Services\\RemoteAccess\\Accounting\\Providers";
    if ( dword_1800CF4E4 )
      RouterLogEventW(hLogHandle, 1u, 0x4E84u, 1u, &plpszSubStringArray, v34);
LABEL_81:
    v13 = v59;
    goto LABEL_5;
  }
  v35 = RegQueryInfoKeyW(v73, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, &cValues, &cbMaxValueNameLen, &cbData, 0, 0);
  LastError = v35;
  if ( v35 )
  {
    if ( dword_1800CF4E4 )
      RouterLogEventW(hLogHandle, 1u, 0x4E22u, 0, 0, v35);
    goto LABEL_81;
  }
  cbData += 2;
  v61 = (BYTE *)HeapAlloc(hHeap, 8u, cbData);
  Library = (HMODULE)v61;
  if ( !v61 )
  {
    v36 = GetLastError();
    LastError = v36;
    if ( !dword_1800CF4E4 )
    {
LABEL_90:
      v13 = v59;
      goto LABEL_18;
    }
    dwErrorCode = v36;
    goto LABEL_88;
  }
  v38 = RegQueryValueExW(v73, L"Path", 0, &Type, v61, &cbData);
  LastError = v38;
  if ( v38 )
    goto LABEL_92;
  if ( Type - 1 > 1 )
  {
    v38 = 1015;
LABEL_97:
    LastError = v38;
LABEL_92:
    if ( !dword_1800CF4E4 )
      goto LABEL_90;
    dwErrorCode = v38;
    goto LABEL_94;
  }
  v39 = ExpandEnvironmentStringsW((LPCWSTR)v61, 0, 0);
  v40 = v39;
  if ( !v39 )
  {
    v38 = GetLastError();
    goto LABEL_97;
  }
  v41 = (WCHAR *)HeapAlloc(hHeap, 8u, 2LL * v39);
  v60 = v41;
  v18 = v41;
  if ( !v41 )
  {
    v42 = GetLastError();
    LastError = v42;
    if ( !dword_1800CF4E4 )
      goto LABEL_90;
    dwErrorCode = v42;
LABEL_88:
    v37 = 20104;
LABEL_89:
    RouterLogEventW(hLogHandle, 1u, v37, 0, 0, dwErrorCode);
    goto LABEL_90;
  }
  if ( !ExpandEnvironmentStringsW((LPCWSTR)v61, v41, v40) )
  {
    v43 = GetLastError();
    LastError = v43;
    if ( !dword_1800CF4E4 )
      goto LABEL_90;
    dwErrorCode = v43;
LABEL_94:
    v37 = 20002;
    goto LABEL_89;
  }
  Library = LoadLibraryExW(v18, 0, 0x1000u);
  if ( Library )
    goto LABEL_68;
  v13 = v59;
  LastError = GetLastError();
  Library = (HMODULE)v61;
LABEL_18:
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( v73 )
    RegCloseKey(v73);
  if ( Library )
    HeapFree(hHeap, 0, Library);
  if ( v18 )
    HeapFree(hHeap, 0, v18);
  if ( v13 )
    HeapFree(hHeap, 0, v13);
  return LastError;
}

```

## disassembly

```asm
0x180017280  mov     [rsp-8+arg_0], rbx
0x180017285  push    rbp
0x180017286  push    rsi
0x180017287  push    rdi
0x180017288  push    r12
0x18001728a  push    r13
0x18001728c  push    r14
0x18001728e  push    r15
0x180017290  lea     rbp, [rsp-0B0h]
0x180017298  sub     rsp, 1B0h
0x18001729f  mov     rax, cs:__security_cookie
0x1800172a6  xor     rax, rsp
0x1800172a9  mov     [rbp+0E0h+var_40], rax
0x1800172b0  mov     rax, [rbp+0E0h+arg_20]
0x1800172b7  lea     r14, aSystemCurrentc_21; "System\\CurrentControlSet\\Services\\Re"...
0x1800172be  mov     [rbp+0E0h+var_108], rax
0x1800172c2  mov     r15, r8
0x1800172c5  mov     rax, [rbp+0E0h+arg_28]
0x1800172cc  mov     r12d, ecx
0x1800172cf  mov     [rbp+0E0h+var_100], rax
0x1800172d3  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800172da  mov     rax, [rbp+0E0h+arg_30]
0x1800172e1  mov     [rbp+0E0h+var_F8], rax
0x1800172e5  mov     rax, [rbp+0E0h+arg_38]
0x1800172ec  mov     [rbp+0E0h+var_E8], rax
0x1800172f0  mov     rax, [rbp+0E0h+arg_40]
0x1800172f7  mov     [rbp+0E0h+var_F0], rax
0x1800172fb  mov     rax, [rbp+0E0h+arg_48]
0x180017302  mov     [rbp+0E0h+var_E0], rax
0x180017306  mov     rax, [rbp+0E0h+arg_50]
0x18001730d  mov     [rbp+0E0h+plpszSubStringArray], rax
0x180017311  xor     eax, eax
0x180017313  mov     [rbp+0E0h+var_130], rax
0x180017317  mov     edi, eax
0x180017319  mov     [rbp+0E0h+var_128], rax
0x18001731d  mov     esi, eax
0x18001731f  mov     [rsp+1E0h+var_170], rax
0x180017324  mov     r13d, eax
0x180017327  mov     [rsp+1E0h+var_178], rax
0x18001732c  mov     [rsp+1E0h+var_180], rax
0x180017331  mov     [rbp+0E0h+cSubKeys], eax
0x180017334  mov     [rbp+0E0h+cbMaxSubKeyLen], eax
0x180017337  mov     [rbp+0E0h+cValues], eax
0x18001733a  mov     [rbp+0E0h+cbMaxValueNameLen], eax
0x18001733d  mov     [rsp+1E0h+cbData], eax
0x180017341  mov     [rsp+1E0h+Type], eax
0x180017345  mov     [rbp+0E0h+hKey], rax
0x180017349  mov     dword ptr [rbp+0E0h+Data], eax
0x18001734c  lea     rax, [rbp+0E0h+hKey]
0x180017350  mov     [rbp+0E0h+var_110], r9
0x180017354  mov     r9d, 20019h; samDesired
0x18001735a  mov     [rbp+0E0h+lpData], r8
0x18001735e  xor     r8d, r8d; ulOptions
0x180017361  mov     [rbp+0E0h+nSize], edx
0x180017364  mov     rdx, r14; lpSubKey
0x180017367  mov     [rsp+1E0h+phkResult], rax; phkResult
0x18001736c  call    cs:__imp_RegOpenKeyExW
0x180017373  nop     dword ptr [rax+rax+00h]
0x180017378  xor     ecx, ecx
0x18001737a  mov     ebx, eax
0x18001737c  test    eax, eax
0x18001737e  jz      short loc_1800173C9
0x180017380  cmp     cs:dword_1800CF4E4, ecx
0x180017386  mov     [rbp+0E0h+plpszSubStringArray], r14
0x18001738a  jbe     loc_180017495
0x180017390  lea     edi, [rsi+1]
0x180017393  mov     [rsp+1E0h+dwErrorCode], eax; dwErrorCode
0x180017397  mov     r9d, edi; dwSubStringCount
0x18001739a  lea     rax, [rbp+0E0h+plpszSubStringArray]
0x18001739e  mov     r8d, 4E84h; dwMessageId
0x1800173a4  mov     [rsp+1E0h+phkResult], rax; plpszSubStringArray
0x1800173a9  mov     rcx, cs:hLogHandle; hLogHandle
0x1800173b0  mov     edx, edi; dwEventType
0x1800173b2  call    cs:__imp_RouterLogEventW
0x1800173b9  nop     dword ptr [rax+rax+00h]
0x1800173be  mov     rdi, rsi
0x1800173c1  mov     r15, rsi
0x1800173c4  jmp     loc_18001749B
0x1800173c9  mov     rcx, [rbp+0E0h+hKey]; hKey
0x1800173cd  lea     rax, [rsp+1E0h+cbData]
0x1800173d2  mov     qword ptr [rsp+1E0h+dwErrorCode], rax; lpcbData
0x1800173d7  lea     rdx, aQuarantineinst; "QuarantineInstalled"
0x1800173de  lea     rax, [rbp+0E0h+Data]
0x1800173e2  mov     [rsp+1E0h+cbData], 4
0x1800173ea  xor     r9d, r9d; lpType
0x1800173ed  mov     [rsp+1E0h+phkResult], rax; lpData
0x1800173f2  xor     r8d, r8d; lpReserved
0x1800173f5  call    cs:__imp_RegQueryValueExW
0x1800173fc  nop     dword ptr [rax+rax+00h]
0x180017401  xor     ebx, ebx
0x180017403  mov     edi, 1
0x180017408  test    eax, eax
0x18001740a  jnz     short loc_180017413
0x18001740c  cmp     dword ptr [rbp+0E0h+Data], edi
0x18001740f  cmovz   r13d, edi
0x180017413  mov     rcx, [rbp+0E0h+hKey]; hKey
0x180017417  test    rcx, rcx
0x18001741a  jz      short loc_180017428
0x18001741c  call    cs:__imp_RegCloseKey
0x180017423  nop     dword ptr [rax+rax+00h]
0x180017428  or      r14, 0FFFFFFFFFFFFFFFFh
0x18001742c  test    r13d, r13d
0x18001742f  jz      short loc_18001743A
0x180017431  test    r12d, r12d
0x180017434  jnz     loc_1800178AD
0x18001743a  lea     rax, aSystemCurrentc_33; "SYSTEM\\CurrentControlSet\\Services\\Re"...
0x180017441  test    r12d, r12d
0x180017444  lea     r15, aSystemCurrentc_13; "SYSTEM\\CurrentControlSet\\Services\\Re"...
0x18001744b  mov     r9d, 20019h; samDesired
0x180017451  cmovz   r15, rax
0x180017455  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001745c  lea     rax, [rbp+0E0h+var_130]
0x180017460  mov     rdx, r15; lpSubKey
0x180017463  xor     r8d, r8d; ulOptions
0x180017466  mov     [rsp+1E0h+phkResult], rax; phkResult
0x18001746b  call    cs:__imp_RegOpenKeyExW
0x180017472  nop     dword ptr [rax+rax+00h]
0x180017477  xor     ecx, ecx
0x180017479  mov     ebx, eax
0x18001747b  test    eax, eax
0x18001747d  jz      loc_180017549
0x180017483  cmp     cs:dword_1800CF4E4, ecx
0x180017489  mov     [rbp+0E0h+plpszSubStringArray], r15
0x18001748d  ja      loc_180017393
0x180017493  mov     edi, ecx
0x180017495  mov     r15, rcx
0x180017498  mov     rsi, rcx
0x18001749b  mov     rcx, [rbp+0E0h+var_130]; hKey
0x18001749f  test    rcx, rcx
0x1800174a2  jz      short loc_1800174B0
0x1800174a4  call    cs:__imp_RegCloseKey
0x1800174ab  nop     dword ptr [rax+rax+00h]
0x1800174b0  mov     rcx, [rbp+0E0h+var_128]; hKey
0x1800174b4  test    rcx, rcx
0x1800174b7  jz      short loc_1800174C5
0x1800174b9  call    cs:__imp_RegCloseKey
0x1800174c0  nop     dword ptr [rax+rax+00h]
0x1800174c5  test    rsi, rsi
0x1800174c8  jz      short loc_1800174E2
0x1800174ca  mov     rcx, cs:hHeap; hHeap
0x1800174d1  mov     r8, rsi; lpMem
0x1800174d4  xor     edx, edx; dwFlags
0x1800174d6  call    cs:__imp_HeapFree
0x1800174dd  nop     dword ptr [rax+rax+00h]
0x1800174e2  test    r15, r15
0x1800174e5  jz      short loc_1800174FF
0x1800174e7  mov     rcx, cs:hHeap; hHeap
0x1800174ee  mov     r8, r15; lpMem
0x1800174f1  xor     edx, edx; dwFlags
0x1800174f3  call    cs:__imp_HeapFree
0x1800174fa  nop     dword ptr [rax+rax+00h]
0x1800174ff  test    rdi, rdi
0x180017502  jz      short loc_18001751C
0x180017504  mov     rcx, cs:hHeap; hHeap
0x18001750b  mov     r8, rdi; lpMem
0x18001750e  xor     edx, edx; dwFlags
0x180017510  call    cs:__imp_HeapFree
0x180017517  nop     dword ptr [rax+rax+00h]
0x18001751c  mov     eax, ebx
0x18001751e  mov     rcx, [rbp+0E0h+var_40]
0x180017525  xor     rcx, rsp; StackCookie
0x180017528  call    __security_check_cookie
0x18001752d  mov     rbx, [rsp+1E0h+arg_0]
0x180017535  add     rsp, 1B0h
0x18001753c  pop     r15
0x18001753e  pop     r14
0x180017540  pop     r13
0x180017542  pop     r12
0x180017544  pop     rdi
0x180017545  pop     rsi
0x180017546  pop     rbp
0x180017547  retn
0x180017549  mov     rcx, [rbp+0E0h+var_130]; hKey
0x18001754d  lea     rax, [rsp+1E0h+cbData]
0x180017552  xor     r15d, r15d
0x180017555  xor     r9d, r9d; lpReserved
0x180017558  mov     [rsp+1E0h+lpftLastWriteTime], r15; lpftLastWriteTime
0x18001755d  xor     r8d, r8d; lpcchClass
0x180017560  mov     [rsp+1E0h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x180017565  xor     edx, edx; lpClass
0x180017567  mov     [rsp+1E0h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x18001756c  lea     rax, [rbp+0E0h+cbMaxValueNameLen]
0x180017570  mov     [rsp+1E0h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x180017575  lea     rax, [rbp+0E0h+cValues]
0x180017579  mov     [rsp+1E0h+lpcValues], rax; lpcValues
0x18001757e  lea     rax, [rbp+0E0h+cbMaxSubKeyLen]
0x180017582  mov     [rsp+1E0h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x180017587  mov     qword ptr [rsp+1E0h+dwErrorCode], rax; lpcbMaxSubKeyLen
0x18001758c  lea     rax, [rbp+0E0h+cSubKeys]
0x180017590  mov     [rsp+1E0h+phkResult], rax; lpcSubKeys
0x180017595  call    cs:__imp_RegQueryInfoKeyW
0x18001759c  nop     dword ptr [rax+rax+00h]
0x1800175a1  mov     ebx, eax
0x1800175a3  test    eax, eax
0x1800175a5  jz      short loc_1800175CB
0x1800175a7  cmp     cs:dword_1800CF4E4, r15d
0x1800175ae  jbe     loc_1800173BE
0x1800175b4  mov     [rsp+1E0h+dwErrorCode], eax
0x1800175b8  xor     r9d, r9d
0x1800175bb  mov     [rsp+1E0h+phkResult], r15
0x1800175c0  mov     r8d, 4E22h
0x1800175c6  jmp     loc_1800173A9
0x1800175cb  mov     eax, [rsp+1E0h+cbData]
0x1800175cf  mov     edx, 8; dwFlags
0x1800175d4  mov     rcx, cs:hHeap; hHeap
0x1800175db  add     eax, 2
0x1800175de  mov     r8d, eax; dwBytes
0x1800175e1  mov     [rsp+1E0h+cbData], eax
0x1800175e5  call    cs:__imp_HeapAlloc
0x1800175ec  nop     dword ptr [rax+rax+00h]
0x1800175f1  mov     [rsp+1E0h+var_180], rax
0x1800175f6  mov     r15, rax
0x1800175f9  test    rax, rax
0x1800175fc  jnz     short loc_180017614
0x1800175fe  call    cs:__imp_GetLastError
0x180017605  nop     dword ptr [rax+rax+00h]
0x18001760a  mov     ebx, eax
0x18001760c  mov     rdi, r15
0x18001760f  jmp     loc_1800173C1
0x180017614  mov     rcx, [rbp+0E0h+var_130]; hKey
0x180017618  lea     rax, [rsp+1E0h+cbData]
0x18001761d  mov     qword ptr [rsp+1E0h+dwErrorCode], rax; lpcbData
0x180017622  lea     r9, [rsp+1E0h+Type]; lpType
0x180017627  xor     r8d, r8d; lpReserved
0x18001762a  mov     [rsp+1E0h+phkResult], r15; lpData
0x18001762f  lea     rdx, aActiveprovider; "ActiveProvider"
0x180017636  call    cs:__imp_RegQueryValueExW
0x18001763d  nop     dword ptr [rax+rax+00h]
0x180017642  xor     ecx, ecx
0x180017644  mov     ebx, eax
0x180017646  test    eax, eax
0x180017648  jz      short loc_18001767F
0x18001764a  cmp     cs:dword_1800CF4E4, ecx
0x180017650  jbe     loc_180017FB7
0x180017656  mov     [rsp+1E0h+dwErrorCode], eax; dwErrorCode
0x18001765a  xor     r9d, r9d; dwSubStringCount
0x18001765d  mov     [rsp+1E0h+phkResult], rcx; plpszSubStringArray
0x180017662  mov     r8d, 4E22h; dwMessageId
0x180017668  mov     rcx, cs:hLogHandle; hLogHandle
0x18001766f  mov     edx, edi; dwEventType
0x180017671  call    cs:__imp_RouterLogEventW
0x180017678  nop     dword ptr [rax+rax+00h]
0x18001767d  jmp     short loc_18001760C
0x18001767f  cmp     [rsp+1E0h+Type], edi
0x180017683  jz      short loc_18001768E
0x180017685  mov     eax, 3F7h
0x18001768a  mov     ebx, eax
0x18001768c  jmp     short loc_18001764A
0x18001768e  mov     eax, [rsp+1E0h+cbData]
0x180017692  shr     rax, 1
0x180017695  xor     ebx, ebx
0x180017697  mov     [r15+rax*2-2], bx
0x18001769d  mov     rax, r14
0x1800176a0  inc     rax
0x1800176a3  cmp     [r15+rax*2], bx
0x1800176a8  jnz     short loc_1800176A0
0x1800176aa  test    rax, rax
0x1800176ad  jnz     short loc_18001771D
0x1800176af  mov     eax, r12d
0x1800176b2  neg     eax
0x1800176b4  mov     eax, 3F7h
0x1800176b9  sbb     ebx, ebx
0x1800176bb  and     ebx, eax
0x1800176bd  test    r12d, r12d
0x1800176c0  jnz     loc_18001760C
0x1800176c6  test    cs:byte_1800CF404, 10h
0x1800176cd  jz      loc_18001760C
0x1800176d3  lea     rdx, aNoAccountingIn; "No Accounting  in SQM"
0x1800176da  inc     r14
0x1800176dd  cmp     [rdx+r14*2], cx
0x1800176e2  jnz     short loc_1800176DA
0x1800176e4  lea     eax, ds:2[r14*2]
0x1800176ec  mov     [rbp+0E0h+var_C8], rdx
0x1800176f0  mov     [rbp+0E0h+var_C0], eax
0x1800176f3  lea     rdx, RasDdmTraceInfo
0x1800176fa  lea     rax, [rbp+0E0h+var_D8]
0x1800176fe  mov     [rbp+0E0h+var_BC], ecx
0x180017701  mov     r9d, 2
0x180017707  mov     [rsp+1E0h+phkResult], rax
0x18001770c  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180017713  call    McGenEventWrite_EventWriteTransfer
0x180017718  jmp     loc_18001760C
0x18001771d  test    r12d, r12d
0x180017720  jnz     loc_180017921
0x180017726  lea     rax, [rbp+0E0h+var_120]
0x18001772a  mov     [rbp+0E0h+var_120], rbx
0x18001772e  mov     r9d, 20019h; samDesired
0x180017734  mov     [rsp+1E0h+phkResult], rax; phkResult
0x180017739  xor     r8d, r8d; ulOptions
0x18001773c  lea     rdx, aSystemCurrentc_9; "SYSTEM\\CurrentControlSet\\Services\\Re"...
0x180017743  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001774a  call    cs:__imp_RegOpenKeyExW
0x180017751  nop     dword ptr [rax+rax+00h]
0x180017756  test    eax, eax
0x180017758  jnz     short loc_1800177B5
0x18001775a  mov     rbx, [rbp+0E0h+lpData]
0x18001775e  lea     rax, [rsp+1E0h+cbData]
0x180017763  mov     rcx, [rbp+0E0h+var_120]; hKey
0x180017767  lea     r9, [rsp+1E0h+Type]; lpType
0x18001776c  mov     qword ptr [rsp+1E0h+dwErrorCode], rax; lpcbData
  ... truncated ...
```
