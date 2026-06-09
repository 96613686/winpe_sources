# LoadAdminModule

- ea: `0x1800161f0`
- end: `0x180016bc4`
- name: `LoadAdminModule`
- size: `2516`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001b570`

## callees

- `0x180007b7c`
- `0x180015bf4`
- `0x1800161f0`
- `0x180071cec`
- `0x18008c5f2`
- `0x18008c630`
- `0x18008e010`

## import_xrefs

- `msvcrt!wcschr` at `0x1800164c1`
- `msvcrt!wcschr` at `0x1800165cd`
- `msvcrt!wcschr` at `0x1800164c1`
- `msvcrt!wcschr` at `0x1800165cd`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x180016430`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x180016493`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x180016430`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x180016493`
- `KERNEL32!GetProcAddress` at `0x18001661b`
- `KERNEL32!GetProcAddress` at `0x180016719`
- `KERNEL32!GetProcAddress` at `0x18001672c`
- `KERNEL32!GetProcAddress` at `0x180016740`
- `KERNEL32!GetProcAddress` at `0x180016754`
- `KERNEL32!GetProcAddress` at `0x180016768`
- `KERNEL32!GetProcAddress` at `0x18001677c`
- `KERNEL32!GetProcAddress` at `0x180016790`
- `KERNEL32!GetProcAddress` at `0x1800167a4`
- `KERNEL32!GetProcAddress` at `0x1800167b8`
- `KERNEL32!GetProcAddress` at `0x1800167cc`
- `KERNEL32!GetProcAddress` at `0x1800167fa`
- `KERNEL32!GetProcAddress` at `0x18001680e`
- `KERNEL32!GetProcAddress` at `0x180016822`
- `KERNEL32!GetProcAddress` at `0x180016836`
- `KERNEL32!GetProcAddress` at `0x18001684a`
- `KERNEL32!GetProcAddress` at `0x18001661b`
- `KERNEL32!GetProcAddress` at `0x180016719`
- `KERNEL32!GetProcAddress` at `0x18001672c`
- `KERNEL32!GetProcAddress` at `0x180016740`
- `KERNEL32!GetProcAddress` at `0x180016754`
- `KERNEL32!GetProcAddress` at `0x180016768`
- `KERNEL32!GetProcAddress` at `0x18001677c`
- `KERNEL32!GetProcAddress` at `0x180016790`
- `KERNEL32!GetProcAddress` at `0x1800167a4`
- `KERNEL32!GetProcAddress` at `0x1800167b8`
- `KERNEL32!GetProcAddress` at `0x1800167cc`
- `KERNEL32!GetProcAddress` at `0x1800167fa`
- `KERNEL32!GetProcAddress` at `0x18001680e`
- `KERNEL32!GetProcAddress` at `0x180016822`
- `KERNEL32!GetProcAddress` at `0x180016836`
- `KERNEL32!GetProcAddress` at `0x18001684a`
- `KERNEL32!FreeLibrary` at `0x1800169e4`
- `KERNEL32!FreeLibrary` at `0x1800169e4`
- `KERNEL32!LoadLibraryExW` at `0x1800165fc`
- `KERNEL32!LoadLibraryExW` at `0x1800165fc`
- `KERNEL32!HeapAlloc` at `0x18001636e`
- `KERNEL32!HeapAlloc` at `0x180016456`
- `KERNEL32!HeapAlloc` at `0x18001655d`
- `KERNEL32!HeapAlloc` at `0x18001636e`
- `KERNEL32!HeapAlloc` at `0x180016456`
- `KERNEL32!HeapAlloc` at `0x18001655d`
- `KERNEL32!GetLastError` at `0x18001643c`
- `KERNEL32!GetLastError` at `0x180016466`
- `KERNEL32!GetLastError` at `0x180016572`
- `KERNEL32!GetLastError` at `0x1800169ef`
- `KERNEL32!GetLastError` at `0x18001643c`
- `KERNEL32!GetLastError` at `0x180016466`
- `KERNEL32!GetLastError` at `0x180016572`
- `KERNEL32!GetLastError` at `0x1800169ef`
- `KERNEL32!HeapFree` at `0x180016b71`
- `KERNEL32!HeapFree` at `0x180016b8a`
- `KERNEL32!HeapFree` at `0x180016b71`
- `KERNEL32!HeapFree` at `0x180016b8a`
- `ADVAPI32!RegOpenKeyW` at `0x18001626a`
- `ADVAPI32!RegOpenKeyW` at `0x18001626a`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18001630d`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18001630d`
- `ADVAPI32!RegQueryValueExW` at `0x1800163bc`
- `ADVAPI32!RegQueryValueExW` at `0x1800163bc`
- `ADVAPI32!RegCloseKey` at `0x180016b94`
- `ADVAPI32!RegCloseKey` at `0x180016b94`
- `rtutils!RouterLogEventW` at `0x18001634a`
- `rtutils!RouterLogEventW` at `0x1800163fb`
- `rtutils!RouterLogEventW` at `0x180016ae5`
- `rtutils!RouterLogEventW` at `0x18001634a`
- `rtutils!RouterLogEventW` at `0x1800163fb`
- `rtutils!RouterLogEventW` at `0x180016ae5`
- `rtutils!RouterLogEventStringW` at `0x1800162aa`
- `rtutils!RouterLogEventStringW` at `0x180016968`
- `rtutils!RouterLogEventStringW` at `0x180016aac`
- `rtutils!RouterLogEventStringW` at `0x1800162aa`
- `rtutils!RouterLogEventStringW` at `0x180016968`
- `rtutils!RouterLogEventStringW` at `0x180016aac`

## string_xrefs

- `0x1800163b5`: `DllPath`
- `0x180016263`: `Software\Microsoft\RAS\AdminDll`
- `0x1800164e5`: `NumAdminDlls %d`
- `0x180016af9`: `DDM has loaded more AdminDlls than what it has computed. Configured=%d;Loaded=%d`
- `0x180016a02`: `Admin DLL %ws Load Library Failed with error %d`
- `0x180016611`: `MprAdminInitializeDllEx`
- `0x1800168c1`: `Admin DLL %ws AdminInitializeDllEx returned error %d`
- `0x18001665e`: `AdminInitializeDllEx present`
- `0x18001670e`: `MprAdminInitializeDll`
- `0x180016722`: `MprAdminTerminateDll`
- `0x180016771`: `MprAdminAcceptNewLink`
- `0x1800167f3`: `MprAdminLinkHangupNotification`
- `0x180016981`: `ValidateAdminDllFunctions failed %d`

## pseudocode

```c
__int64 LoadAdminModule()
{
  LSTATUS v0; // eax
  DWORD v1; // ebx
  LSTATUS v3; // eax
  LPBYTE v4; // r13
  DWORD LastError; // eax
  DWORD v6; // eax
  DWORD v7; // esi
  wchar_t *v8; // rax
  DWORD v9; // eax
  DWORD v10; // eax
  wchar_t *v11; // rsi
  unsigned int v12; // r12d
  wchar_t *v13; // rcx
  wchar_t *v14; // rax
  wchar_t *v15; // r15
  __int64 v16; // r14
  __int64 v17; // r8
  __int64 v18; // rax
  char *v19; // rdx
  unsigned int v20; // r9d
  HMODULE *v21; // rsi
  wchar_t *v22; // rax
  HMODULE Library; // rax
  HMODULE v24; // r13
  FARPROC ProcAddress; // rbx
  DWORD v26; // eax
  __int64 v27; // r8
  HMODULE v28; // rcx
  __int64 (*v29)(void); // rbx
  FARPROC v30; // rax
  HMODULE v31; // rcx
  FARPROC v32; // rax
  HMODULE v33; // rcx
  FARPROC v34; // rax
  HMODULE v35; // rcx
  FARPROC v36; // rax
  HMODULE v37; // rcx
  FARPROC v38; // rax
  HMODULE v39; // rcx
  FARPROC v40; // rax
  HMODULE v41; // rcx
  FARPROC v42; // rax
  HMODULE v43; // rcx
  FARPROC v44; // rax
  HMODULE v45; // rcx
  DWORD v46; // eax
  FARPROC v47; // rax
  HMODULE v48; // rcx
  FARPROC v49; // rax
  HMODULE v50; // rcx
  FARPROC v51; // rax
  HMODULE v52; // rcx
  FARPROC v53; // rax
  HMODULE v54; // rcx
  unsigned int v55; // eax
  __int64 v56; // r8
  __int64 v57; // r8
  __int64 v58; // r8
  DWORD dwErrorCode; // [rsp+28h] [rbp-D8h]
  DWORD cbMaxValueLen; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+64h] [rbp-9Ch] BYREF
  DWORD cbMaxValueNameLen; // [rsp+68h] [rbp-98h] BYREF
  DWORD Type; // [rsp+6Ch] [rbp-94h] BYREF
  wchar_t *Str; // [rsp+70h] [rbp-90h] BYREF
  DWORD cSubKeys[2]; // [rsp+78h] [rbp-88h] BYREF
  HKEY phkResult; // [rsp+80h] [rbp-80h] BYREF
  DWORD cValues; // [rsp+88h] [rbp-78h] BYREF
  wchar_t *v68; // [rsp+90h] [rbp-70h]
  unsigned __int64 v69; // [rsp+98h] [rbp-68h]
  LPBYTE v70; // [rsp+A0h] [rbp-60h]
  char v71[8]; // [rsp+B0h] [rbp-50h] BYREF
  HMODULE v72; // [rsp+B8h] [rbp-48h]
  HMODULE v73; // [rsp+C0h] [rbp-40h]
  HMODULE v74; // [rsp+C8h] [rbp-38h]
  HMODULE v75; // [rsp+D0h] [rbp-30h]
  HMODULE v76; // [rsp+D8h] [rbp-28h]
  HMODULE v77; // [rsp+E0h] [rbp-20h]
  HMODULE v78; // [rsp+E8h] [rbp-18h]
  HMODULE v79; // [rsp+F0h] [rbp-10h]
  HMODULE v80; // [rsp+F8h] [rbp-8h]
  HMODULE v81; // [rsp+100h] [rbp+0h]
  HMODULE v82; // [rsp+108h] [rbp+8h]
  HMODULE v83; // [rsp+110h] [rbp+10h]
  _BYTE v84[16]; // [rsp+120h] [rbp+20h] BYREF
  const wchar_t *v85; // [rsp+130h] [rbp+30h]
  __int64 v86; // [rsp+138h] [rbp+38h]
  int v87; // [rsp+140h] [rbp+40h] BYREF
  char v88[2044]; // [rsp+144h] [rbp+44h] BYREF

  cbMaxValueLen = 0;
  cbMaxValueNameLen = 0;
  cValues = 0;
  Type = 0;
  Str = 0;
  phkResult = 0;
  dword_1800C8568 = 0;
  v87 = 0;
  memset_0(v88, 0, sizeof(v88));
  v0 = RegOpenKeyW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\RAS\\AdminDll", &phkResult);
  v1 = v0;
  if ( v0 != 2 )
  {
    if ( v0 )
    {
      if ( dword_1800C84E4 )
        RouterLogEventStringW(hLogHandle, 1u, 0x4E90u, 0, 0, v0, 0);
      return v1;
    }
    cSubKeys[0] = 0;
    cbMaxSubKeyLen = 0;
    v3 = RegQueryInfoKeyW(
           phkResult,
           0,
           0,
           0,
           cSubKeys,
           &cbMaxSubKeyLen,
           0,
           &cValues,
           &cbMaxValueNameLen,
           &cbMaxValueLen,
           0,
           0);
    v1 = v3;
    ++cbMaxValueNameLen;
    if ( v3 )
    {
      if ( dword_1800C84E4 )
        RouterLogEventW(hLogHandle, 1u, 0x4E22u, 0, 0, v3);
      goto LABEL_82;
    }
    v70 = (LPBYTE)HeapAlloc(hHeap, 8u, cbMaxValueLen + 2LL);
    v4 = v70;
    if ( !v70 )
    {
      if ( dword_1800C84E4 )
        RouterLogEventW(hLogHandle, 1u, 0x4E88u, 0, 0, 0);
      goto LABEL_82;
    }
    LastError = RegQueryValueExW(phkResult, L"DllPath", 0, &Type, v70, &cbMaxValueLen);
    v1 = LastError;
    if ( cbMaxValueLen > 2 )
    {
      if ( LastError )
      {
LABEL_14:
        if ( !dword_1800C84E4 )
        {
LABEL_81:
          HeapFree(hHeap, 0, v4);
LABEL_82:
          if ( Str )
            HeapFree(hHeap, 0, Str);
          RegCloseKey(phkResult);
          return v1;
        }
        dwErrorCode = LastError;
LABEL_16:
        RouterLogEventW(hLogHandle, 1u, 0x4E22u, 0, 0, dwErrorCode);
        goto LABEL_81;
      }
      if ( Type - 1 > 1 )
      {
        v1 = 1015;
        if ( !dword_1800C84E4 )
          goto LABEL_81;
        dwErrorCode = 1015;
        goto LABEL_16;
      }
      v6 = ExpandEnvironmentStringsW((LPCWSTR)v4, 0, 0);
      v7 = v6;
      if ( !v6 )
      {
LABEL_21:
        LastError = GetLastError();
        v1 = LastError;
        goto LABEL_14;
      }
      v8 = (wchar_t *)HeapAlloc(hHeap, 8u, 2LL * v6);
      Str = v8;
      if ( v8 )
      {
        v10 = ExpandEnvironmentStringsW((LPCWSTR)v4, v8, v7);
        if ( !v10 )
          goto LABEL_21;
        v11 = Str;
        v12 = 1;
        v13 = Str;
        *(_QWORD *)cSubKeys = v10;
        while ( 1 )
        {
          v14 = wcschr(v13, 0x3Bu);
          if ( !v14 )
            break;
          ++v12;
          v13 = v14 + 1;
        }
        v15 = Str;
        v16 = -1;
        if ( (byte_1800C8404 & 0x10) != 0 )
        {
          LOWORD(v87) = 0;
          FormatRRASErrorString(&v87, L"NumAdminDlls %d", v12);
          if ( (byte_1800C8404 & 0x10) != 0 )
          {
            v18 = -1;
            do
              ++v18;
            while ( *(_WORD *)&v88[2 * v18 - 4] );
            v86 = (unsigned int)(2 * v18 + 2);
            v85 = (const wchar_t *)&v87;
            McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceInfo, v17, 2, v84);
          }
        }
        qword_1800C8560 = HeapAlloc(hHeap, 8u, 168LL * v12);
        v19 = (char *)qword_1800C8560;
        if ( qword_1800C8560 )
        {
          v20 = dword_1800C8568;
          cbMaxSubKeyLen = 0;
          v69 = (unsigned __int64)&v11[*(_QWORD *)cSubKeys - 1];
          if ( v12 <= dword_1800C8568 )
          {
LABEL_76:
            if ( (byte_1800C8404 & 0x10) != 0 )
            {
              LOWORD(v87) = 0;
              FormatRRASErrorString(
                &v87,
                L"DDM has loaded more AdminDlls than what it has computed. Configured=%d;Loaded=%d",
                v12);
              if ( (byte_1800C8404 & 0x10) != 0 )
              {
                do
                  ++v16;
                while ( *(_WORD *)&v88[2 * v16 - 4] );
                v86 = (unsigned int)(2 * v16 + 2);
                v85 = (const wchar_t *)&v87;
                McGenEventWrite_EventWriteTransfer(
                  &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                  RasDdmTraceInfo,
                  v58,
                  2,
                  v84);
              }
            }
          }
          else
          {
            while ( 1 )
            {
              v21 = (HMODULE *)&v19[168 * v20];
              memset_0(v21, 0, 0xA8u);
              v22 = wcschr(v15, 0x3Bu);
              v68 = v22;
              if ( v22 )
                *v22 = 0;
              else
                cbMaxSubKeyLen = 1;
              if ( *v15 == 32 )
                goto LABEL_80;
              Library = LoadLibraryExW(v15, 0, 0x1000u);
              *v21 = Library;
              v24 = Library;
              if ( !Library )
                break;
              ProcAddress = GetProcAddress(Library, "MprAdminInitializeDllEx");
              if ( ProcAddress )
              {
                memset_0(v71, 0, 0x68u);
                v26 = ((__int64 (__fastcall *)(char *))ProcAddress)(v71);
                v1 = v26;
                if ( v26 )
                {
                  if ( (byte_1800C8404 & 0x10) != 0 )
                  {
                    LOWORD(v87) = 0;
                    FormatRRASErrorString(&v87, L"Admin DLL %ws AdminInitializeDllEx returned error %d", v15, v26);
                    if ( (byte_1800C8404 & 0x10) != 0 )
                    {
                      do
                        ++v16;
                      while ( *(_WORD *)&v88[2 * v16 - 4] );
                      v86 = (unsigned int)(2 * v16 + 2);
                      v85 = (const wchar_t *)&v87;
                      McGenEventWrite_EventWriteTransfer(
                        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                        RasDdmTraceInfo,
                        &v87,
                        2,
                        v84);
                    }
                  }
                  if ( dword_1800C84E4 )
                    RouterLogEventStringW(hLogHandle, 1u, 0x4E91u, 0, 0, v1, 0);
                  goto LABEL_66;
                }
                if ( (byte_1800C8404 & 0x10) != 0 )
                {
                  v86 = 58;
                  v85 = L"AdminInitializeDllEx present";
                  McGenEventWrite_EventWriteTransfer(
                    &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                    RasDdmTraceInfo,
                    v27,
                    2,
                    v84);
                }
                *((_BYTE *)v21 + 8) = v71[0];
                v21[2] = v72;
                v21[3] = v73;
                v21[4] = v74;
                v21[5] = v75;
                v21[9] = v76;
                v21[13] = v77;
                v21[14] = v78;
                v21[16] = v79;
                v21[17] = v80;
                v21[18] = v81;
                v21[19] = v82;
                v21[20] = v83;
              }
              else
              {
                v28 = *v21;
                *((_BYTE *)v21 + 8) = 1;
                v29 = GetProcAddress(v28, "MprAdminInitializeDll");
                v30 = GetProcAddress(*v21, "MprAdminTerminateDll");
                v31 = *v21;
                v21[14] = (HMODULE)v30;
                v32 = GetProcAddress(v31, "MprAdminAcceptNewConnection");
                v33 = *v21;
                v21[6] = (HMODULE)v32;
                v34 = GetProcAddress(v33, "MprAdminAcceptNewConnection2");
                v35 = *v21;
                v21[7] = (HMODULE)v34;
                v36 = GetProcAddress(v35, "MprAdminAcceptNewConnection3");
                v37 = *v21;
                v21[8] = (HMODULE)v36;
                v38 = GetProcAddress(v37, "MprAdminAcceptNewLink");
                v39 = *v21;
                v21[9] = (HMODULE)v38;
                v40 = GetProcAddress(v39, "MprAdminAcceptReauthentication");
                v41 = *v21;
                v21[15] = (HMODULE)v40;
                v42 = GetProcAddress(v41, "MprAdminConnectionHangupNotification");
                v43 = *v21;
                v21[10] = (HMODULE)v42;
                v44 = GetProcAddress(v43, "MprAdminConnectionHangupNotification2");
                v45 = *v21;
                v21[11] = (HMODULE)v44;
                v21[12] = (HMODULE)GetProcAddress(v45, "MprAdminConnectionHangupNotification3");
                if ( v29 )
                {
                  v46 = v29();
                  v1 = v46;
                  if ( v46 )
                  {
                    if ( dword_1800C84E4 )
                      RouterLogEventStringW(hLogHandle, 1u, 0x4E91u, 0, 0, v46, 0);
                    goto LABEL_66;
                  }
                }
                v47 = GetProcAddress(*v21, "MprAdminLinkHangupNotification");
                v48 = *v21;
                v21[13] = (HMODULE)v47;
                v49 = GetProcAddress(v48, "MprAdminGetIpAddressForUser");
                v50 = *v21;
                v21[2] = (HMODULE)v49;
                v51 = GetProcAddress(v50, "MprAdminReleaseIpAddress");
                v52 = *v21;
                v21[3] = (HMODULE)v51;
                v53 = GetProcAddress(v52, "MprAdminGetIpv6AddressForUser");
                v54 = *v21;
                v21[4] = (HMODULE)v53;
                v21[5] = (HMODULE)GetProcAddress(v54, "MprAdminReleaseIpv6AddressForUser");
              }
              v55 = ValidateAdminDllFunctions((struct _ADMIN_DLL_CALLBACKS *)v21);
              v1 = v55;
              if ( v55 )
              {
                if ( (byte_1800C8404 & 8) != 0 )
                {
                  LOWORD(v87) = 0;
                  FormatRRASErrorString(&v87, L"ValidateAdminDllFunctions failed %d", v55);
                  if ( (byte_1800C8404 & 8) != 0 )
                  {
                    do
                      ++v16;
                    while ( *(_WORD *)&v88[2 * v16 - 4] );
                    v86 = (unsigned int)(2 * v16 + 2);
                    v85 = (const wchar_t *)&v87;
                    McGenEventWrite_EventWriteTransfer(
                      &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                      RasDdmTraceError,
                      v56,
                      2,
                      v84);
                  }
                }
LABEL_66:
                FreeLibrary(v24);
                goto LABEL_80;
              }
              v20 = ++dword_1800C8568;
              if ( cbMaxSubKeyLen )
                goto LABEL_80;
              v15 = v68 + 1;
              if ( (unsigned __int64)(v68 + 1) >= v69 )
                goto LABEL_80;
              if ( v12 <= v20 )
                goto LABEL_76;
              v19 = (char *)qword_1800C8560;
            }
            v1 = GetLastError();
            if ( (byte_1800C8404 & 8) != 0 )
            {
              LOWORD(v87) = 0;
              FormatRRASErrorString(&v87, L"Admin DLL %ws Load Library Failed with error %d", v15, v1);
              if ( (byte_1800C8404 & 8) != 0 )
              {
                do
                  ++v16;
                while ( *(_WORD *)&v88[2 * v16 - 4] );
                v86 = (unsigned int)(2 * v16 + 2);
                v85 = (const wchar_t *)&v87;
                McGenEventWrite_EventWriteTransfer(
                  &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                  RasDdmTraceError,
                  v57,
                  2,
                  v84);
              }
            }
            if ( v1 - 191 <= 2 )
            {
              if ( dword_1800C84E4 )
                RouterLogEventW(hLogHandle, 1u, 0x4EECu, 1u, &Str, 0);
            }
            else if ( dword_1800C84E4 )
            {
              RouterLogEventStringW(hLogHandle, 1u, 0x4E91u, 0, 0, v1, 0);
            }
          }
LABEL_80:
          v4 = v70;
          goto LABEL_81;
        }
      }
      v9 = GetLastError();
      v1 = v9;
      if ( dword_1800C84E4 )
        RouterLogEventW(hLogHandle, 1u, 0x4E88u, 0, 0, v9);
      goto LABEL_81;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800161f0  push    rbp
0x1800161f2  push    rbx
0x1800161f3  push    rsi
0x1800161f4  push    rdi
0x1800161f5  push    r12
0x1800161f7  push    r13
0x1800161f9  push    r14
0x1800161fb  push    r15
0x1800161fd  lea     rbp, [rsp-858h]
0x180016205  sub     rsp, 958h
0x18001620c  mov     rax, cs:__security_cookie
0x180016213  xor     rax, rsp
0x180016216  mov     [rbp+890h+var_50], rax
0x18001621d  xor     r15d, r15d
0x180016220  lea     rcx, [rbp+890h+var_84C]; void *
0x180016224  xor     edx, edx; Val
0x180016226  mov     [rsp+990h+cbMaxValueLen], r15d
0x18001622b  mov     r8d, 7FCh; Size
0x180016231  mov     [rsp+990h+cbMaxValueNameLen], r15d
0x180016236  mov     [rbp+890h+cValues], r15d
0x18001623a  mov     [rsp+990h+Type], r15d
0x18001623f  mov     [rsp+990h+Str], r15
0x180016244  mov     [rbp+890h+phkResult], r15
0x180016248  mov     cs:dword_1800C8568, r15d
0x18001624f  mov     [rbp+890h+var_850], r15d
0x180016253  call    memset_0
0x180016258  lea     r8, [rbp+890h+phkResult]; phkResult
0x18001625c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180016263  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\RAS\\AdminDll"
0x18001626a  call    cs:__imp_RegOpenKeyW
0x180016270  mov     ebx, eax
0x180016272  cmp     eax, 2
0x180016275  jz      loc_180016B9F
0x18001627b  test    eax, eax
0x18001627d  jz      short loc_1800162B7
0x18001627f  cmp     cs:dword_1800C84E4, r15d
0x180016286  jbe     short loc_1800162B0
0x180016288  mov     rcx, cs:hLogHandle; hLogHandle
0x18001628f  lea     edx, [r15+1]; dwEventType
0x180016293  mov     [rsp+990h+dwErrorIndex], r15d; dwErrorIndex
0x180016298  xor     r9d, r9d; dwSubStringCount
0x18001629b  mov     [rsp+990h+dwErrorCode], eax; dwErrorCode
0x18001629f  mov     r8d, 4E90h; dwMessageId
0x1800162a5  mov     [rsp+990h+plpszSubStringArray], r15; plpszSubStringArray
0x1800162aa  call    cs:__imp_RouterLogEventStringW
0x1800162b0  mov     eax, ebx
0x1800162b2  jmp     loc_180016BA1
0x1800162b7  mov     rcx, [rbp+890h+phkResult]; hKey
0x1800162bb  lea     rax, [rsp+990h+cbMaxValueLen]
0x1800162c0  mov     [rsp+990h+lpftLastWriteTime], r15; lpftLastWriteTime
0x1800162c5  xor     r9d, r9d; lpReserved
0x1800162c8  mov     [rsp+990h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x1800162cd  xor     r8d, r8d; lpcchClass
0x1800162d0  mov     [rsp+990h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x1800162d5  xor     edx, edx; lpClass
0x1800162d7  lea     rax, [rsp+990h+cbMaxValueNameLen]
0x1800162dc  mov     [rsp+990h+cSubKeys], r15d
0x1800162e1  mov     [rsp+990h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x1800162e6  lea     rax, [rbp+890h+cValues]
0x1800162ea  mov     [rsp+990h+lpcValues], rax; lpcValues
0x1800162ef  lea     rax, [rsp+990h+cbMaxSubKeyLen]
0x1800162f4  mov     qword ptr [rsp+990h+dwErrorIndex], r15; lpcbMaxClassLen
0x1800162f9  mov     qword ptr [rsp+990h+dwErrorCode], rax; lpcbMaxSubKeyLen
0x1800162fe  lea     rax, [rsp+990h+cSubKeys]
0x180016303  mov     [rsp+990h+plpszSubStringArray], rax; lpcSubKeys
0x180016308  mov     [rsp+990h+cbMaxSubKeyLen], r15d
0x18001630d  call    cs:__imp_RegQueryInfoKeyW
0x180016313  mov     edi, 1
0x180016318  mov     ebx, eax
0x18001631a  add     [rsp+990h+cbMaxValueNameLen], edi
0x18001631e  test    eax, eax
0x180016320  jz      short loc_180016355
0x180016322  cmp     cs:dword_1800C84E4, r15d
0x180016329  jbe     loc_180016B77
0x18001632f  mov     [rsp+990h+dwErrorCode], eax; dwErrorCode
0x180016333  mov     r8d, 4E22h; dwMessageId
0x180016339  mov     rcx, cs:hLogHandle; hLogHandle
0x180016340  xor     r9d, r9d; dwSubStringCount
0x180016343  mov     edx, edi; dwEventType
0x180016345  mov     [rsp+990h+plpszSubStringArray], r15; plpszSubStringArray
0x18001634a  call    cs:__imp_RouterLogEventW
0x180016350  jmp     loc_180016B77
0x180016355  mov     r8d, [rsp+990h+cbMaxValueLen]
0x18001635a  mov     r14d, 8
0x180016360  mov     rcx, cs:hHeap; hHeap
0x180016367  add     r8, 2; dwBytes
0x18001636b  mov     edx, r14d; dwFlags
0x18001636e  call    cs:__imp_HeapAlloc
0x180016374  mov     [rbp+890h+var_8F0], rax
0x180016378  mov     r13, rax
0x18001637b  test    rax, rax
0x18001637e  jnz     short loc_18001639A
0x180016380  cmp     cs:dword_1800C84E4, r15d
0x180016387  jbe     loc_180016B77
0x18001638d  mov     [rsp+990h+dwErrorCode], r15d
0x180016392  mov     r8d, 4E88h
0x180016398  jmp     short loc_180016339
0x18001639a  mov     rcx, [rbp+890h+phkResult]; hKey
0x18001639e  lea     rax, [rsp+990h+cbMaxValueLen]
0x1800163a3  mov     qword ptr [rsp+990h+dwErrorCode], rax; lpcbData
0x1800163a8  lea     r9, [rsp+990h+Type]; lpType
0x1800163ad  xor     r8d, r8d; lpReserved
0x1800163b0  mov     [rsp+990h+plpszSubStringArray], r13; lpData
0x1800163b5  lea     rdx, aDllpath; "DllPath"
0x1800163bc  call    cs:__imp_RegQueryValueExW
0x1800163c2  cmp     [rsp+990h+cbMaxValueLen], 2
0x1800163c7  mov     ebx, eax
0x1800163c9  jbe     loc_180016B9F
0x1800163cf  test    eax, eax
0x1800163d1  jz      short loc_180016406
0x1800163d3  cmp     cs:dword_1800C84E4, r15d
0x1800163da  jbe     loc_180016B65
0x1800163e0  mov     [rsp+990h+dwErrorCode], eax; dwErrorCode
0x1800163e4  mov     r8d, 4E22h; dwMessageId
0x1800163ea  mov     rcx, cs:hLogHandle; hLogHandle
0x1800163f1  xor     r9d, r9d; dwSubStringCount
0x1800163f4  mov     edx, edi; dwEventType
0x1800163f6  mov     [rsp+990h+plpszSubStringArray], r15; plpszSubStringArray
0x1800163fb  call    cs:__imp_RouterLogEventW
0x180016401  jmp     loc_180016B65
0x180016406  mov     eax, [rsp+990h+Type]
0x18001640a  dec     eax
0x18001640c  cmp     eax, edi
0x18001640e  jbe     short loc_180016428
0x180016410  cmp     cs:dword_1800C84E4, r15d
0x180016417  mov     ebx, 3F7h
0x18001641c  jbe     loc_180016B65
0x180016422  mov     [rsp+990h+dwErrorCode], ebx
0x180016426  jmp     short loc_1800163E4
0x180016428  xor     r8d, r8d; nSize
0x18001642b  xor     edx, edx; lpDst
0x18001642d  mov     rcx, r13; lpSrc
0x180016430  call    cs:__imp_ExpandEnvironmentStringsW
0x180016436  mov     esi, eax
0x180016438  test    eax, eax
0x18001643a  jnz     short loc_180016446
0x18001643c  call    cs:__imp_GetLastError
0x180016442  mov     ebx, eax
0x180016444  jmp     short loc_1800163D3
0x180016446  mov     rcx, cs:hHeap; hHeap
0x18001644d  mov     r8, rsi
0x180016450  add     r8, r8; dwBytes
0x180016453  mov     edx, r14d; dwFlags
0x180016456  call    cs:__imp_HeapAlloc
0x18001645c  mov     [rsp+990h+Str], rax
0x180016461  test    rax, rax
0x180016464  jnz     short loc_18001648A
0x180016466  call    cs:__imp_GetLastError
0x18001646c  cmp     cs:dword_1800C84E4, r15d
0x180016473  mov     ebx, eax
0x180016475  jbe     loc_180016B65
0x18001647b  mov     [rsp+990h+dwErrorCode], eax
0x18001647f  mov     r8d, 4E88h
0x180016485  jmp     loc_1800163EA
0x18001648a  mov     r8d, esi; nSize
0x18001648d  mov     rdx, rax; lpDst
0x180016490  mov     rcx, r13; lpSrc
0x180016493  call    cs:__imp_ExpandEnvironmentStringsW
0x180016499  test    eax, eax
0x18001649b  jz      short loc_18001643C
0x18001649d  mov     rsi, [rsp+990h+Str]
0x1800164a2  mov     r12d, edi
0x1800164a5  mov     eax, eax
0x1800164a7  mov     rcx, rsi
0x1800164aa  mov     qword ptr [rsp+990h+cSubKeys], rax
0x1800164af  mov     r14d, 3Bh ; ';'
0x1800164b5  jmp     short loc_1800164BE
0x1800164b7  add     r12d, edi
0x1800164ba  lea     rcx, [rax+2]; Str
0x1800164be  mov     edx, r14d; Ch
0x1800164c1  call    cs:__imp_wcschr
0x1800164c7  test    rax, rax
0x1800164ca  jnz     short loc_1800164B7
0x1800164cc  mov     r15, [rsp+990h+Str]
0x1800164d1  or      r14, 0FFFFFFFFFFFFFFFFh
0x1800164d5  test    cs:byte_1800C8404, 10h
0x1800164dc  jz      short loc_180016547
0x1800164de  mov     r8d, r12d
0x1800164e1  mov     word ptr [rbp+890h+var_850], ax
0x1800164e5  lea     rdx, aNumadmindllsD; "NumAdminDlls %d"
0x1800164ec  lea     rcx, [rbp+890h+var_850]
0x1800164f0  call    FormatRRASErrorString
0x1800164f5  test    cs:byte_1800C8404, 10h
0x1800164fc  jz      short loc_180016547
0x1800164fe  lea     rcx, [rbp+890h+var_850]
0x180016502  mov     rax, r14
0x180016505  xor     edx, edx
0x180016507  inc     rax
0x18001650a  cmp     [rcx+rax*2], dx
0x18001650e  jnz     short loc_180016507
0x180016510  lea     eax, ds:2[rax*2]
0x180016517  mov     dword ptr [rbp+890h+var_858+4], edx
0x18001651a  lea     rcx, [rbp+890h+var_850]
0x18001651e  mov     dword ptr [rbp+890h+var_858], eax
0x180016521  lea     rax, [rbp+890h+var_870]
0x180016525  mov     [rbp+890h+var_860], rcx
0x180016529  mov     r9d, 2
0x18001652f  mov     [rsp+990h+plpszSubStringArray], rax
0x180016534  lea     rdx, RasDdmTraceInfo
0x18001653b  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180016542  call    McGenEventWrite_EventWriteTransfer
0x180016547  mov     rcx, cs:hHeap; hHeap
0x18001654e  mov     edx, 8; dwFlags
0x180016553  mov     eax, r12d
0x180016556  imul    r8, rax, 0A8h; dwBytes
0x18001655d  call    cs:__imp_HeapAlloc
0x180016563  mov     cs:qword_1800C8560, rax
0x18001656a  mov     rdx, rax
0x18001656d  test    rax, rax
0x180016570  jnz     short loc_180016580
0x180016572  call    cs:__imp_GetLastError
0x180016578  xor     r15d, r15d
0x18001657b  jmp     loc_18001646C
0x180016580  mov     rax, qword ptr [rsp+990h+cSubKeys]
0x180016585  xor     r13d, r13d
0x180016588  mov     r9d, cs:dword_1800C8568
0x18001658f  dec     rax
0x180016592  mov     [rsp+990h+cbMaxSubKeyLen], r13d
0x180016597  lea     rax, [rsi+rax*2]
0x18001659b  mov     [rbp+890h+var_8F8], rax
0x18001659f  cmp     r12d, r9d
0x1800165a2  jbe     loc_180016AED
0x1800165a8  mov     eax, r9d
0x1800165ab  mov     r8d, 0A8h; Size
0x1800165b1  imul    rsi, rax, 0A8h
0x1800165b8  add     rsi, rdx
0x1800165bb  xor     edx, edx; Val
0x1800165bd  mov     rcx, rsi; void *
0x1800165c0  call    memset_0
0x1800165c5  mov     edx, 3Bh ; ';'; Ch
0x1800165ca  mov     rcx, r15; Str
0x1800165cd  call    cs:__imp_wcschr
0x1800165d3  mov     [rbp+890h+var_900], rax
0x1800165d7  test    rax, rax
0x1800165da  jz      short loc_1800165E2
0x1800165dc  mov     [rax], r13w
0x1800165e0  jmp     short loc_1800165E6
0x1800165e2  mov     [rsp+990h+cbMaxSubKeyLen], edi
0x1800165e6  cmp     word ptr [r15], 20h ; ' '
0x1800165eb  jz      loc_180016B61
0x1800165f1  xor     edx, edx; hFile
0x1800165f3  mov     r8d, 1000h; dwFlags
0x1800165f9  mov     rcx, r15; lpLibFileName
0x1800165fc  call    cs:__imp_LoadLibraryExW
0x180016602  mov     [rsi], rax
0x180016605  mov     r13, rax
0x180016608  test    rax, rax
0x18001660b  jz      loc_1800169EF
0x180016611  lea     rdx, ProcName; "MprAdminInitializeDllEx"
0x180016618  mov     rcx, rax; hModule
0x18001661b  call    cs:__imp_GetProcAddress
0x180016621  mov     rbx, rax
0x180016624  test    rax, rax
0x180016627  jz      loc_18001670B
0x18001662d  xor     edx, edx; Val
0x18001662f  lea     rcx, [rbp+890h+var_8E0]; void *
0x180016633  lea     r8d, [rdx+68h]; Size
0x180016637  call    memset_0
0x18001663c  lea     rcx, [rbp+890h+var_8E0]
0x180016640  mov     rax, rbx
0x180016643  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016648  mov     ebx, eax
0x18001664a  test    eax, eax
0x18001664c  jnz     loc_1800168AC
0x180016652  xor     r15d, r15d
0x180016655  test    cs:byte_1800C8404, 10h
0x18001665c  jz      short loc_180016691
0x18001665e  lea     rax, aAdmininitializ; "AdminInitializeDllEx present"
0x180016665  mov     [rbp+890h+var_858], 3Ah ; ':'
0x18001666d  mov     [rbp+890h+var_860], rax
0x180016671  lea     r9d, [rbx+2]
0x180016675  lea     rax, [rbp+890h+var_870]
0x180016679  lea     rdx, RasDdmTraceInfo
0x180016680  mov     [rsp+990h+plpszSubStringArray], rax
0x180016685  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001668c  call    McGenEventWrite_EventWriteTransfer
0x180016691  mov     al, [rbp+890h+var_8E0]
0x180016694  mov     [rsi+8], al
0x180016697  mov     rax, [rbp+890h+var_8D8]
0x18001669b  mov     [rsi+10h], rax
0x18001669f  mov     rax, [rbp+890h+var_8D0]
0x1800166a3  mov     [rsi+18h], rax
0x1800166a7  mov     rax, [rbp+890h+var_8C8]
0x1800166ab  mov     [rsi+20h], rax
0x1800166af  mov     rax, [rbp+890h+var_8C0]
0x1800166b3  mov     [rsi+28h], rax
0x1800166b7  mov     rax, [rbp+890h+var_8B8]
0x1800166bb  mov     [rsi+48h], rax
0x1800166bf  mov     rax, [rbp+890h+var_8B0]
0x1800166c3  mov     [rsi+68h], rax
0x1800166c7  mov     rax, [rbp+890h+var_8A8]
0x1800166cb  mov     [rsi+70h], rax
0x1800166cf  mov     rax, [rbp+890h+var_8A0]
0x1800166d3  mov     [rsi+80h], rax
0x1800166da  mov     rax, [rbp+890h+var_898]
0x1800166de  mov     [rsi+88h], rax
0x1800166e5  mov     rax, [rbp+890h+var_890]
0x1800166e9  mov     [rsi+90h], rax
0x1800166f0  mov     rax, [rbp+890h+var_888]
0x1800166f4  mov     [rsi+98h], rax
  ... truncated ...
```
