# LoadAdminModule

- ea: `0x1800167fc`
- end: `0x18001727a`
- name: `LoadAdminModule`
- size: `2686`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001bf40`

## callees

- `0x180007c0c`
- `0x18001612c`
- `0x18001618c`
- `0x1800167fc`
- `0x1800755b8`
- `0x180092a92`
- `0x180092ad0`
- `0x180095010`

## import_xrefs

- `msvcrt!wcschr` at `0x180016b02`
- `msvcrt!wcschr` at `0x180016c07`
- `msvcrt!wcschr` at `0x180016b02`
- `msvcrt!wcschr` at `0x180016c07`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x180016a29`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x180016ab7`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x180016a29`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x180016ab7`
- `KERNEL32!GetProcAddress` at `0x180016c65`
- `KERNEL32!GetProcAddress` at `0x180016d66`
- `KERNEL32!GetProcAddress` at `0x180016d7f`
- `KERNEL32!GetProcAddress` at `0x180016d99`
- `KERNEL32!GetProcAddress` at `0x180016db3`
- `KERNEL32!GetProcAddress` at `0x180016dcd`
- `KERNEL32!GetProcAddress` at `0x180016de7`
- `KERNEL32!GetProcAddress` at `0x180016e01`
- `KERNEL32!GetProcAddress` at `0x180016e1b`
- `KERNEL32!GetProcAddress` at `0x180016e35`
- `KERNEL32!GetProcAddress` at `0x180016e4f`
- `KERNEL32!GetProcAddress` at `0x180016e80`
- `KERNEL32!GetProcAddress` at `0x180016e9a`
- `KERNEL32!GetProcAddress` at `0x180016eb4`
- `KERNEL32!GetProcAddress` at `0x180016ece`
- `KERNEL32!GetProcAddress` at `0x180016ee8`
- `KERNEL32!GetProcAddress` at `0x180016c65`
- `KERNEL32!GetProcAddress` at `0x180016d66`
- `KERNEL32!GetProcAddress` at `0x180016d7f`
- `KERNEL32!GetProcAddress` at `0x180016d99`
- `KERNEL32!GetProcAddress` at `0x180016db3`
- `KERNEL32!GetProcAddress` at `0x180016dcd`
- `KERNEL32!GetProcAddress` at `0x180016de7`
- `KERNEL32!GetProcAddress` at `0x180016e01`
- `KERNEL32!GetProcAddress` at `0x180016e1b`
- `KERNEL32!GetProcAddress` at `0x180016e35`
- `KERNEL32!GetProcAddress` at `0x180016e4f`
- `KERNEL32!GetProcAddress` at `0x180016e80`
- `KERNEL32!GetProcAddress` at `0x180016e9a`
- `KERNEL32!GetProcAddress` at `0x180016eb4`
- `KERNEL32!GetProcAddress` at `0x180016ece`
- `KERNEL32!GetProcAddress` at `0x180016ee8`
- `KERNEL32!FreeLibrary` at `0x180017089`
- `KERNEL32!FreeLibrary` at `0x180017089`
- `KERNEL32!LoadLibraryExW` at `0x180016c3e`
- `KERNEL32!LoadLibraryExW` at `0x180016c3e`
- `KERNEL32!HeapAlloc` at `0x180016945`
- `KERNEL32!HeapAlloc` at `0x180016a6d`
- `KERNEL32!HeapAlloc` at `0x180016ba2`
- `KERNEL32!HeapAlloc` at `0x180016945`
- `KERNEL32!HeapAlloc` at `0x180016a6d`
- `KERNEL32!HeapAlloc` at `0x180016ba2`
- `KERNEL32!GetLastError` at `0x180016a3b`
- `KERNEL32!GetLastError` at `0x180016a83`
- `KERNEL32!GetLastError` at `0x180016ac9`
- `KERNEL32!GetLastError` at `0x180016bbd`
- `KERNEL32!GetLastError` at `0x18001709a`
- `KERNEL32!GetLastError` at `0x180016a3b`
- `KERNEL32!GetLastError` at `0x180016a83`
- `KERNEL32!GetLastError` at `0x180016ac9`
- `KERNEL32!GetLastError` at `0x180016bbd`
- `KERNEL32!GetLastError` at `0x18001709a`
- `KERNEL32!HeapFree` at `0x180017206`
- `KERNEL32!HeapFree` at `0x180017225`
- `KERNEL32!HeapFree` at `0x180017206`
- `KERNEL32!HeapFree` at `0x180017225`
- `ADVAPI32!RegOpenKeyW` at `0x18001687c`
- `ADVAPI32!RegOpenKeyW` at `0x18001687c`
- `ADVAPI32!RegQueryValueExW` at `0x180016994`
- `ADVAPI32!RegQueryValueExW` at `0x180016994`
- `ADVAPI32!RegCloseKey` at `0x180017236`
- `ADVAPI32!RegCloseKey` at `0x180017236`
- `rtutils!RouterLogEventW` at `0x18001691b`
- `rtutils!RouterLogEventW` at `0x1800169da`
- `rtutils!RouterLogEventW` at `0x18001691b`
- `rtutils!RouterLogEventW` at `0x1800169da`
- `rtutils!RouterLogEventStringW` at `0x1800168bf`
- `rtutils!RouterLogEventStringW` at `0x180017007`
- `rtutils!RouterLogEventStringW` at `0x180017152`
- `rtutils!RouterLogEventStringW` at `0x1800168bf`
- `rtutils!RouterLogEventStringW` at `0x180017007`
- `rtutils!RouterLogEventStringW` at `0x180017152`

## string_xrefs

- `0x18001698d`: `DllPath`
- `0x180016875`: `Software\Microsoft\RAS\AdminDll`
- `0x180016b2c`: `NumAdminDlls %d`
- `0x18001719b`: `DDM has loaded more AdminDlls than what it has computed. Configured=%d;Loaded=%d`
- `0x1800170bd`: `Admin DLL %ws Load Library Failed with error %d`
- `0x180016c5b`: `MprAdminInitializeDllEx`
- `0x180016f65`: `Admin DLL %ws AdminInitializeDllEx returned error %d`
- `0x180016cab`: `AdminInitializeDllEx present`
- `0x180016d5b`: `MprAdminInitializeDll`
- `0x180016d75`: `MprAdminTerminateDll`
- `0x180016ddc`: `MprAdminAcceptNewLink`
- `0x180016e79`: `MprAdminLinkHangupNotification`
- `0x180017025`: `ValidateAdminDllFunctions failed %d`

## pseudocode

```c
__int64 LoadAdminModule()
{
  LSTATUS v0; // eax
  DWORD v1; // ebx
  DWORD KeyMax; // eax
  BYTE *v4; // r13
  LSTATUS v5; // eax
  DWORD v6; // r9d
  DWORD v7; // r8d
  DWORD v8; // eax
  DWORD v9; // esi
  DWORD LastError; // eax
  wchar_t *v11; // rax
  DWORD v12; // eax
  DWORD v13; // eax
  wchar_t *v14; // rcx
  unsigned int v15; // r12d
  wchar_t *v16; // rax
  wchar_t *v17; // r15
  __int64 v18; // r14
  __int64 v19; // r8
  __int64 v20; // rax
  char *v21; // rcx
  unsigned int v22; // r9d
  HMODULE *v23; // rsi
  wchar_t *v24; // rax
  HMODULE Library; // rax
  FARPROC ProcAddress; // rbx
  DWORD v27; // eax
  __int64 v28; // r8
  HMODULE v29; // rcx
  __int64 (*v30)(void); // rbx
  FARPROC v31; // rax
  HMODULE v32; // rcx
  FARPROC v33; // rax
  HMODULE v34; // rcx
  FARPROC v35; // rax
  HMODULE v36; // rcx
  FARPROC v37; // rax
  HMODULE v38; // rcx
  FARPROC v39; // rax
  HMODULE v40; // rcx
  FARPROC v41; // rax
  HMODULE v42; // rcx
  FARPROC v43; // rax
  HMODULE v44; // rcx
  FARPROC v45; // rax
  HMODULE v46; // rcx
  DWORD v47; // eax
  FARPROC v48; // rax
  HMODULE v49; // rcx
  FARPROC v50; // rax
  HMODULE v51; // rcx
  FARPROC v52; // rax
  HMODULE v53; // rcx
  FARPROC v54; // rax
  HMODULE v55; // rcx
  unsigned int v56; // eax
  __int64 v57; // r8
  DWORD v58; // eax
  __int64 v59; // r8
  __int64 v60; // r8
  wchar_t **plpszSubStringArray; // [rsp+28h] [rbp-E0h]
  DWORD dwErrorCode; // [rsp+30h] [rbp-D8h]
  DWORD cbData; // [rsp+48h] [rbp-C0h] BYREF
  DWORD Type; // [rsp+4Ch] [rbp-BCh] BYREF
  __int64 v65; // [rsp+50h] [rbp-B8h]
  wchar_t *Str; // [rsp+58h] [rbp-B0h] BYREF
  HKEY phkResult; // [rsp+60h] [rbp-A8h] BYREF
  unsigned int v68[2]; // [rsp+68h] [rbp-A0h] BYREF
  wchar_t *v69; // [rsp+70h] [rbp-98h]
  wchar_t *v70; // [rsp+78h] [rbp-90h]
  HMODULE hLibModule; // [rsp+80h] [rbp-88h]
  char v72[8]; // [rsp+88h] [rbp-80h] BYREF
  HMODULE v73; // [rsp+90h] [rbp-78h]
  HMODULE v74; // [rsp+98h] [rbp-70h]
  HMODULE v75; // [rsp+A0h] [rbp-68h]
  HMODULE v76; // [rsp+A8h] [rbp-60h]
  HMODULE v77; // [rsp+B0h] [rbp-58h]
  HMODULE v78; // [rsp+B8h] [rbp-50h]
  HMODULE v79; // [rsp+C0h] [rbp-48h]
  HMODULE v80; // [rsp+C8h] [rbp-40h]
  HMODULE v81; // [rsp+D0h] [rbp-38h]
  HMODULE v82; // [rsp+D8h] [rbp-30h]
  HMODULE v83; // [rsp+E0h] [rbp-28h]
  HMODULE v84; // [rsp+E8h] [rbp-20h]
  _BYTE v85[16]; // [rsp+F8h] [rbp-10h] BYREF
  const wchar_t *v86; // [rsp+108h] [rbp+0h]
  __int64 v87; // [rsp+110h] [rbp+8h]
  int v88; // [rsp+118h] [rbp+10h] BYREF
  char v89[2044]; // [rsp+11Ch] [rbp+14h] BYREF

  cbData = 0;
  v68[1] = 0;
  v68[0] = 0;
  Type = 0;
  Str = 0;
  phkResult = 0;
  dword_1800CF568 = 0;
  v88 = 0;
  memset_0(v89, 0, sizeof(v89));
  v0 = RegOpenKeyW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\RAS\\AdminDll", &phkResult);
  v1 = v0;
  if ( v0 != 2 )
  {
    if ( v0 )
    {
      if ( dword_1800CF4E4 )
        RouterLogEventStringW(hLogHandle, 1u, 0x4E90u, 0, 0, v0, 0);
      return v1;
    }
    KeyMax = GetKeyMax(phkResult, &v68[1], v68, &cbData);
    v1 = KeyMax;
    if ( KeyMax )
    {
      if ( dword_1800CF4E4 )
        RouterLogEventW(hLogHandle, 1u, 0x4E22u, 0, 0, KeyMax);
      goto LABEL_84;
    }
    v4 = (BYTE *)HeapAlloc(hHeap, 8u, cbData + 2LL);
    if ( !v4 )
    {
      if ( dword_1800CF4E4 )
        RouterLogEventW(hLogHandle, 1u, 0x4E88u, 0, 0, 0);
      goto LABEL_84;
    }
    v5 = RegQueryValueExW(phkResult, L"DllPath", 0, &Type, v4, &cbData);
    v1 = v5;
    if ( cbData > 2 )
    {
      if ( v5 )
      {
        if ( dword_1800CF4E4 )
        {
          v6 = 0;
          dwErrorCode = v5;
          plpszSubStringArray = 0;
          v7 = 20002;
LABEL_16:
          RouterLogEventW(hLogHandle, 1u, v7, v6, plpszSubStringArray, dwErrorCode);
        }
LABEL_83:
        HeapFree(hHeap, 0, v4);
LABEL_84:
        if ( Str )
          HeapFree(hHeap, 0, Str);
        RegCloseKey(phkResult);
        return v1;
      }
      if ( Type - 1 > 1 )
      {
        v1 = 1015;
        if ( !dword_1800CF4E4 )
          goto LABEL_83;
        dwErrorCode = 1015;
        goto LABEL_20;
      }
      v8 = ExpandEnvironmentStringsW((LPCWSTR)v4, 0, 0);
      v9 = v8;
      if ( !v8 )
      {
LABEL_23:
        LastError = GetLastError();
        v1 = LastError;
        if ( !dword_1800CF4E4 )
          goto LABEL_83;
        dwErrorCode = LastError;
LABEL_20:
        v7 = 20002;
LABEL_21:
        v6 = 0;
        plpszSubStringArray = 0;
        goto LABEL_16;
      }
      v11 = (wchar_t *)HeapAlloc(hHeap, 8u, 2LL * v8);
      Str = v11;
      if ( v11 )
      {
        v13 = ExpandEnvironmentStringsW((LPCWSTR)v4, v11, v9);
        if ( !v13 )
          goto LABEL_23;
        v14 = Str;
        v15 = 1;
        v70 = &Str[v13 - 1];
        while ( 1 )
        {
          v16 = wcschr(v14, 0x3Bu);
          if ( !v16 )
            break;
          ++v15;
          v14 = v16 + 1;
        }
        v17 = Str;
        v18 = -1;
        if ( (byte_1800CF404 & 0x10) != 0 )
        {
          LOWORD(v88) = 0;
          FormatRRASErrorString(&v88, L"NumAdminDlls %d", v15);
          if ( (byte_1800CF404 & 0x10) != 0 )
          {
            v20 = -1;
            do
              ++v20;
            while ( *(_WORD *)&v89[2 * v20 - 4] );
            v87 = (unsigned int)(2 * v20 + 2);
            v86 = (const wchar_t *)&v88;
            McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceInfo, v19, 2, v85);
          }
        }
        qword_1800CF560 = HeapAlloc(hHeap, 8u, 168LL * v15);
        v21 = (char *)qword_1800CF560;
        if ( qword_1800CF560 )
        {
          v22 = dword_1800CF568;
          LODWORD(v65) = 0;
          if ( v15 <= dword_1800CF568 )
          {
LABEL_79:
            if ( (byte_1800CF404 & 0x10) != 0 )
            {
              LOWORD(v88) = 0;
              FormatRRASErrorString(
                &v88,
                L"DDM has loaded more AdminDlls than what it has computed. Configured=%d;Loaded=%d",
                v15);
              if ( (byte_1800CF404 & 0x10) != 0 )
              {
                do
                  ++v18;
                while ( *(_WORD *)&v89[2 * v18 - 4] );
                v87 = (unsigned int)(2 * v18 + 2);
                v86 = (const wchar_t *)&v88;
                McGenEventWrite_EventWriteTransfer(
                  &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                  RasDdmTraceInfo,
                  v60,
                  2,
                  v85);
              }
            }
            goto LABEL_83;
          }
          while ( 1 )
          {
            v23 = (HMODULE *)&v21[168 * v22];
            memset_0(v23, 0, 0xA8u);
            v24 = wcschr(v17, 0x3Bu);
            v69 = v24;
            if ( v24 )
              *v24 = 0;
            else
              LODWORD(v65) = 1;
            if ( *v17 == 32 )
              goto LABEL_83;
            Library = LoadLibraryExW(v17, 0, 0x1000u);
            hLibModule = Library;
            *v23 = Library;
            if ( !Library )
              break;
            ProcAddress = GetProcAddress(Library, "MprAdminInitializeDllEx");
            if ( ProcAddress )
            {
              memset_0(v72, 0, 0x68u);
              v27 = ((__int64 (__fastcall *)(char *))ProcAddress)(v72);
              v1 = v27;
              if ( v27 )
              {
                if ( (byte_1800CF404 & 0x10) != 0 )
                {
                  LOWORD(v88) = 0;
                  FormatRRASErrorString(&v88, L"Admin DLL %ws AdminInitializeDllEx returned error %d", v17, v27);
                  if ( (byte_1800CF404 & 0x10) != 0 )
                  {
                    do
                      ++v18;
                    while ( *(_WORD *)&v89[2 * v18 - 4] );
                    v87 = (unsigned int)(2 * v18 + 2);
                    v86 = (const wchar_t *)&v88;
                    McGenEventWrite_EventWriteTransfer(
                      &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                      RasDdmTraceInfo,
                      &v88,
                      2,
                      v85);
                  }
                }
                if ( dword_1800CF4E4 )
                  RouterLogEventStringW(hLogHandle, 1u, 0x4E91u, 0, 0, v1, 0);
                goto LABEL_69;
              }
              if ( (byte_1800CF404 & 0x10) != 0 )
              {
                v87 = 58;
                v86 = L"AdminInitializeDllEx present";
                McGenEventWrite_EventWriteTransfer(
                  &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                  RasDdmTraceInfo,
                  v28,
                  2,
                  v85);
              }
              *((_BYTE *)v23 + 8) = v72[0];
              v23[2] = v73;
              v23[3] = v74;
              v23[4] = v75;
              v23[5] = v76;
              v23[9] = v77;
              v23[13] = v78;
              v23[14] = v79;
              v23[16] = v80;
              v23[17] = v81;
              v23[18] = v82;
              v23[19] = v83;
              v23[20] = v84;
            }
            else
            {
              v29 = *v23;
              *((_BYTE *)v23 + 8) = 1;
              v30 = GetProcAddress(v29, "MprAdminInitializeDll");
              v31 = GetProcAddress(*v23, "MprAdminTerminateDll");
              v32 = *v23;
              v23[14] = (HMODULE)v31;
              v33 = GetProcAddress(v32, "MprAdminAcceptNewConnection");
              v34 = *v23;
              v23[6] = (HMODULE)v33;
              v35 = GetProcAddress(v34, "MprAdminAcceptNewConnection2");
              v36 = *v23;
              v23[7] = (HMODULE)v35;
              v37 = GetProcAddress(v36, "MprAdminAcceptNewConnection3");
              v38 = *v23;
              v23[8] = (HMODULE)v37;
              v39 = GetProcAddress(v38, "MprAdminAcceptNewLink");
              v40 = *v23;
              v23[9] = (HMODULE)v39;
              v41 = GetProcAddress(v40, "MprAdminAcceptReauthentication");
              v42 = *v23;
              v23[15] = (HMODULE)v41;
              v43 = GetProcAddress(v42, "MprAdminConnectionHangupNotification");
              v44 = *v23;
              v23[10] = (HMODULE)v43;
              v45 = GetProcAddress(v44, "MprAdminConnectionHangupNotification2");
              v46 = *v23;
              v23[11] = (HMODULE)v45;
              v23[12] = (HMODULE)GetProcAddress(v46, "MprAdminConnectionHangupNotification3");
              if ( v30 )
              {
                v47 = v30();
                v1 = v47;
                if ( v47 )
                {
                  if ( dword_1800CF4E4 )
                    RouterLogEventStringW(hLogHandle, 1u, 0x4E91u, 0, 0, v47, 0);
                  goto LABEL_69;
                }
              }
              v48 = GetProcAddress(*v23, "MprAdminLinkHangupNotification");
              v49 = *v23;
              v23[13] = (HMODULE)v48;
              v50 = GetProcAddress(v49, "MprAdminGetIpAddressForUser");
              v51 = *v23;
              v23[2] = (HMODULE)v50;
              v52 = GetProcAddress(v51, "MprAdminReleaseIpAddress");
              v53 = *v23;
              v23[3] = (HMODULE)v52;
              v54 = GetProcAddress(v53, "MprAdminGetIpv6AddressForUser");
              v55 = *v23;
              v23[4] = (HMODULE)v54;
              v23[5] = (HMODULE)GetProcAddress(v55, "MprAdminReleaseIpv6AddressForUser");
            }
            v56 = ValidateAdminDllFunctions((struct _ADMIN_DLL_CALLBACKS *)v23);
            v1 = v56;
            if ( v56 )
            {
              if ( (byte_1800CF404 & 8) != 0 )
              {
                LOWORD(v88) = 0;
                FormatRRASErrorString(&v88, L"ValidateAdminDllFunctions failed %d", v56);
                if ( (byte_1800CF404 & 8) != 0 )
                {
                  do
                    ++v18;
                  while ( *(_WORD *)&v89[2 * v18 - 4] );
                  v87 = (unsigned int)(2 * v18 + 2);
                  v86 = (const wchar_t *)&v88;
                  McGenEventWrite_EventWriteTransfer(
                    &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                    RasDdmTraceError,
                    v57,
                    2,
                    v85);
                }
              }
LABEL_69:
              FreeLibrary(hLibModule);
              goto LABEL_83;
            }
            v22 = ++dword_1800CF568;
            if ( (_DWORD)v65 )
              goto LABEL_83;
            v17 = v69 + 1;
            if ( v69 + 1 >= v70 )
              goto LABEL_83;
            if ( v15 <= v22 )
              goto LABEL_79;
            v21 = (char *)qword_1800CF560;
          }
          v58 = GetLastError();
          v1 = v58;
          if ( (byte_1800CF404 & 8) != 0 )
          {
            LOWORD(v88) = 0;
            FormatRRASErrorString(&v88, L"Admin DLL %ws Load Library Failed with error %d", v17, v58);
            if ( (byte_1800CF404 & 8) != 0 )
            {
              do
                ++v18;
              while ( *(_WORD *)&v89[2 * v18 - 4] );
              v87 = (unsigned int)(2 * v18 + 2);
              v86 = (const wchar_t *)&v88;
              McGenEventWrite_EventWriteTransfer(
                &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                RasDdmTraceError,
                v59,
                2,
                v85);
            }
          }
          if ( v1 - 191 > 2 )
          {
            if ( dword_1800CF4E4 )
              RouterLogEventStringW(hLogHandle, 1u, 0x4E91u, 0, 0, v1, 0);
            goto LABEL_83;
          }
          if ( dword_1800CF4E4 )
          {
            dwErrorCode = 0;
            plpszSubStringArray = &Str;
            v6 = 1;
            v7 = 20204;
            goto LABEL_16;
          }
          goto LABEL_83;
        }
      }
      v12 = GetLastError();
      v1 = v12;
      if ( !dword_1800CF4E4 )
        goto LABEL_83;
      dwErrorCode = v12;
      v7 = 20104;
      goto LABEL_21;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800167fc  mov     rax, rsp
0x1800167ff  mov     [rax+8], rbx
0x180016803  mov     [rax+10h], rsi
0x180016807  mov     [rax+18h], rdi
0x18001680b  push    rbp
0x18001680c  push    r12
0x18001680e  push    r13
0x180016810  push    r14
0x180016812  push    r15
0x180016814  lea     rbp, [rax-848h]
0x18001681b  sub     rsp, 920h
0x180016822  mov     rax, cs:__security_cookie
0x180016829  xor     rax, rsp
0x18001682c  mov     [rbp+840h+var_30], rax
0x180016833  xor     esi, esi
0x180016835  lea     rcx, [rbp+840h+var_82C]; void *
0x180016839  xor     edx, edx; Val
0x18001683b  mov     [rsp+940h+cbData], esi
0x18001683f  mov     r8d, 7FCh; Size
0x180016845  mov     [rsp+940h+var_8E0+4], esi
0x180016849  mov     [rsp+940h+var_8E0], esi
0x18001684d  mov     [rsp+940h+Type], esi
0x180016851  mov     [rsp+940h+Str], rsi
0x180016856  mov     [rsp+940h+phkResult], rsi
0x18001685b  mov     cs:dword_1800CF568, esi
0x180016861  mov     [rbp+840h+var_830], esi
0x180016864  call    memset_0
0x180016869  lea     r8, [rsp+940h+phkResult]; phkResult
0x18001686e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180016875  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\RAS\\AdminDll"
0x18001687c  call    cs:__imp_RegOpenKeyW
0x180016883  nop     dword ptr [rax+rax+00h]
0x180016888  mov     ebx, eax
0x18001688a  cmp     eax, 2
0x18001688d  jz      loc_180017247
0x180016893  test    eax, eax
0x180016895  jz      short loc_1800168D2
0x180016897  cmp     cs:dword_1800CF4E4, esi
0x18001689d  jbe     short loc_1800168CB
0x18001689f  mov     rcx, cs:hLogHandle; hLogHandle
0x1800168a6  lea     edx, [rsi+1]; dwEventType
0x1800168a9  mov     [rsp+940h+dwErrorIndex], esi; dwErrorIndex
0x1800168ad  xor     r9d, r9d; dwSubStringCount
0x1800168b0  mov     [rsp+940h+dwErrorCode], eax; dwErrorCode
0x1800168b4  mov     r8d, 4E90h; dwMessageId
0x1800168ba  mov     [rsp+940h+plpszSubStringArray], rsi; plpszSubStringArray
0x1800168bf  call    cs:__imp_RouterLogEventStringW
0x1800168c6  nop     dword ptr [rax+rax+00h]
0x1800168cb  mov     eax, ebx
0x1800168cd  jmp     loc_180017249
0x1800168d2  mov     rcx, [rsp+940h+phkResult]; HKEY
0x1800168d7  lea     r9, [rsp+940h+cbData]; unsigned int *
0x1800168dc  lea     r8, [rsp+940h+var_8E0]; unsigned int *
0x1800168e1  lea     rdx, [rsp+940h+var_8E0+4]; unsigned int *
0x1800168e6  call    ?GetKeyMax@@YAKPEAUHKEY__@@PEAK11@Z; GetKeyMax(HKEY__ *,ulong *,ulong *,ulong *)
0x1800168eb  mov     ebx, eax
0x1800168ed  test    eax, eax
0x1800168ef  jz      short loc_18001692C
0x1800168f1  cmp     cs:dword_1800CF4E4, esi
0x1800168f7  jbe     loc_180017212
0x1800168fd  mov     [rsp+940h+dwErrorCode], eax; dwErrorCode
0x180016901  mov     r8d, 4E22h; dwMessageId
0x180016907  mov     rcx, cs:hLogHandle; hLogHandle
0x18001690e  mov     edx, 1; dwEventType
0x180016913  xor     r9d, r9d; dwSubStringCount
0x180016916  mov     [rsp+940h+plpszSubStringArray], rsi; plpszSubStringArray
0x18001691b  call    cs:__imp_RouterLogEventW
0x180016922  nop     dword ptr [rax+rax+00h]
0x180016927  jmp     loc_180017212
0x18001692c  mov     r8d, [rsp+940h+cbData]
0x180016931  mov     r15d, 8
0x180016937  mov     rcx, cs:hHeap; hHeap
0x18001693e  add     r8, 2; dwBytes
0x180016942  mov     edx, r15d; dwFlags
0x180016945  call    cs:__imp_HeapAlloc
0x18001694c  nop     dword ptr [rax+rax+00h]
0x180016951  mov     r13, rax
0x180016954  test    rax, rax
0x180016957  jnz     short loc_180016971
0x180016959  cmp     cs:dword_1800CF4E4, esi
0x18001695f  jbe     loc_180017212
0x180016965  mov     [rsp+940h+dwErrorCode], esi
0x180016969  mov     r8d, 4E88h
0x18001696f  jmp     short loc_180016907
0x180016971  mov     rcx, [rsp+940h+phkResult]; hKey
0x180016976  lea     rax, [rsp+940h+cbData]
0x18001697b  mov     qword ptr [rsp+940h+dwErrorCode], rax; lpcbData
0x180016980  lea     r9, [rsp+940h+Type]; lpType
0x180016985  xor     r8d, r8d; lpReserved
0x180016988  mov     [rsp+940h+plpszSubStringArray], r13; lpData
0x18001698d  lea     rdx, aDllpath; "DllPath"
0x180016994  call    cs:__imp_RegQueryValueExW
0x18001699b  nop     dword ptr [rax+rax+00h]
0x1800169a0  cmp     [rsp+940h+cbData], 2
0x1800169a5  mov     ebx, eax
0x1800169a7  jbe     loc_180017247
0x1800169ad  test    eax, eax
0x1800169af  jz      short loc_1800169EB
0x1800169b1  cmp     cs:dword_1800CF4E4, esi
0x1800169b7  jbe     loc_1800171FA
0x1800169bd  xor     r9d, r9d; dwSubStringCount
0x1800169c0  mov     [rsp+940h+dwErrorCode], eax; dwErrorCode
0x1800169c4  mov     [rsp+940h+plpszSubStringArray], rsi; plpszSubStringArray
0x1800169c9  mov     r8d, 4E22h; dwMessageId
0x1800169cf  lea     edx, [r9+1]; dwEventType
0x1800169d3  mov     rcx, cs:hLogHandle; hLogHandle
0x1800169da  call    cs:__imp_RouterLogEventW
0x1800169e1  nop     dword ptr [rax+rax+00h]
0x1800169e6  jmp     loc_1800171FA
0x1800169eb  mov     eax, [rsp+940h+Type]
0x1800169ef  mov     edi, 1
0x1800169f4  dec     eax
0x1800169f6  cmp     eax, edi
0x1800169f8  jbe     short loc_180016A21
0x1800169fa  cmp     cs:dword_1800CF4E4, esi
0x180016a00  mov     ebx, 3F7h
0x180016a05  jbe     loc_1800171FA
0x180016a0b  mov     [rsp+940h+dwErrorCode], ebx
0x180016a0f  mov     r8d, 4E22h
0x180016a15  xor     r9d, r9d
0x180016a18  mov     [rsp+940h+plpszSubStringArray], rsi
0x180016a1d  mov     edx, edi
0x180016a1f  jmp     short loc_1800169D3
0x180016a21  xor     r8d, r8d; nSize
0x180016a24  xor     edx, edx; lpDst
0x180016a26  mov     rcx, r13; lpSrc
0x180016a29  call    cs:__imp_ExpandEnvironmentStringsW
0x180016a30  nop     dword ptr [rax+rax+00h]
0x180016a35  mov     esi, eax
0x180016a37  test    eax, eax
0x180016a39  jnz     short loc_180016A5D
0x180016a3b  call    cs:__imp_GetLastError
0x180016a42  nop     dword ptr [rax+rax+00h]
0x180016a47  xor     esi, esi
0x180016a49  cmp     cs:dword_1800CF4E4, esi
0x180016a4f  mov     ebx, eax
0x180016a51  jbe     loc_1800171FA
0x180016a57  mov     [rsp+940h+dwErrorCode], eax
0x180016a5b  jmp     short loc_180016A0F
0x180016a5d  mov     rcx, cs:hHeap; hHeap
0x180016a64  mov     r8, rsi
0x180016a67  add     r8, r8; dwBytes
0x180016a6a  mov     edx, r15d; dwFlags
0x180016a6d  call    cs:__imp_HeapAlloc
0x180016a74  nop     dword ptr [rax+rax+00h]
0x180016a79  mov     [rsp+940h+Str], rax
0x180016a7e  test    rax, rax
0x180016a81  jnz     short loc_180016AAE
0x180016a83  call    cs:__imp_GetLastError
0x180016a8a  nop     dword ptr [rax+rax+00h]
0x180016a8f  xor     esi, esi
0x180016a91  cmp     cs:dword_1800CF4E4, esi
0x180016a97  mov     ebx, eax
0x180016a99  jbe     loc_1800171FA
0x180016a9f  mov     [rsp+940h+dwErrorCode], eax
0x180016aa3  mov     r8d, 4E88h
0x180016aa9  jmp     loc_180016A15
0x180016aae  mov     r8d, esi; nSize
0x180016ab1  mov     rdx, rax; lpDst
0x180016ab4  mov     rcx, r13; lpSrc
0x180016ab7  call    cs:__imp_ExpandEnvironmentStringsW
0x180016abe  nop     dword ptr [rax+rax+00h]
0x180016ac3  xor     esi, esi
0x180016ac5  test    eax, eax
0x180016ac7  jnz     short loc_180016ADA
0x180016ac9  call    cs:__imp_GetLastError
0x180016ad0  nop     dword ptr [rax+rax+00h]
0x180016ad5  jmp     loc_180016A49
0x180016ada  mov     rcx, [rsp+940h+Str]
0x180016adf  mov     r12d, edi
0x180016ae2  mov     eax, eax
0x180016ae4  mov     r14d, 3Bh ; ';'
0x180016aea  dec     rax
0x180016aed  lea     rax, [rcx+rax*2]
0x180016af1  mov     [rsp+940h+var_8D0], rax
0x180016af6  jmp     short loc_180016AFF
0x180016af8  add     r12d, edi
0x180016afb  lea     rcx, [rax+2]; Str
0x180016aff  mov     edx, r14d; Ch
0x180016b02  call    cs:__imp_wcschr
0x180016b09  nop     dword ptr [rax+rax+00h]
0x180016b0e  test    rax, rax
0x180016b11  jnz     short loc_180016AF8
0x180016b13  mov     r15, [rsp+940h+Str]
0x180016b18  or      r14, 0FFFFFFFFFFFFFFFFh
0x180016b1c  test    cs:byte_1800CF404, 10h
0x180016b23  jz      short loc_180016B8C
0x180016b25  mov     r8d, r12d
0x180016b28  mov     word ptr [rbp+840h+var_830], si
0x180016b2c  lea     rdx, aNumadmindllsD; "NumAdminDlls %d"
0x180016b33  lea     rcx, [rbp+840h+var_830]
0x180016b37  call    FormatRRASErrorString
0x180016b3c  test    cs:byte_1800CF404, 10h
0x180016b43  jz      short loc_180016B8C
0x180016b45  lea     rcx, [rbp+840h+var_830]
0x180016b49  mov     rax, r14
0x180016b4c  inc     rax
0x180016b4f  cmp     [rcx+rax*2], si
0x180016b53  jnz     short loc_180016B4C
0x180016b55  lea     eax, ds:2[rax*2]
0x180016b5c  mov     dword ptr [rbp+840h+var_838+4], esi
0x180016b5f  lea     rcx, [rbp+840h+var_830]
0x180016b63  mov     dword ptr [rbp+840h+var_838], eax
0x180016b66  lea     rax, [rbp+840h+var_850]
0x180016b6a  mov     [rbp+840h+var_840], rcx
0x180016b6e  mov     r9d, 2
0x180016b74  mov     [rsp+940h+plpszSubStringArray], rax
0x180016b79  lea     rdx, RasDdmTraceInfo
0x180016b80  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180016b87  call    McGenEventWrite_EventWriteTransfer
0x180016b8c  mov     rcx, cs:hHeap; hHeap
0x180016b93  mov     edx, 8; dwFlags
0x180016b98  mov     eax, r12d
0x180016b9b  imul    r8, rax, 0A8h; dwBytes
0x180016ba2  call    cs:__imp_HeapAlloc
0x180016ba9  nop     dword ptr [rax+rax+00h]
0x180016bae  mov     cs:qword_1800CF560, rax
0x180016bb5  mov     rcx, rax
0x180016bb8  test    rax, rax
0x180016bbb  jnz     short loc_180016BCE
0x180016bbd  call    cs:__imp_GetLastError
0x180016bc4  nop     dword ptr [rax+rax+00h]
0x180016bc9  jmp     loc_180016A91
0x180016bce  mov     r9d, cs:dword_1800CF568
0x180016bd5  mov     dword ptr [rsp+940h+var_8F8], esi
0x180016bd9  cmp     r12d, r9d
0x180016bdc  jbe     loc_18001718B
0x180016be2  mov     eax, r9d
0x180016be5  xor     edx, edx; Val
0x180016be7  imul    rsi, rax, 0A8h
0x180016bee  mov     r8d, 0A8h; Size
0x180016bf4  add     rsi, rcx
0x180016bf7  mov     rcx, rsi; void *
0x180016bfa  call    memset_0
0x180016bff  mov     edx, 3Bh ; ';'; Ch
0x180016c04  mov     rcx, r15; Str
0x180016c07  call    cs:__imp_wcschr
0x180016c0e  nop     dword ptr [rax+rax+00h]
0x180016c13  xor     ecx, ecx
0x180016c15  mov     [rsp+940h+var_8D8], rax
0x180016c1a  test    rax, rax
0x180016c1d  jz      short loc_180016C24
0x180016c1f  mov     [rax], cx
0x180016c22  jmp     short loc_180016C28
0x180016c24  mov     dword ptr [rsp+940h+var_8F8], edi
0x180016c28  cmp     word ptr [r15], 20h ; ' '
0x180016c2d  jz      loc_1800171FA
0x180016c33  xor     edx, edx; hFile
0x180016c35  mov     r8d, 1000h; dwFlags
0x180016c3b  mov     rcx, r15; lpLibFileName
0x180016c3e  call    cs:__imp_LoadLibraryExW
0x180016c45  nop     dword ptr [rax+rax+00h]
0x180016c4a  mov     [rsp+940h+hLibModule], rax
0x180016c4f  mov     [rsi], rax
0x180016c52  test    rax, rax
0x180016c55  jz      loc_18001709A
0x180016c5b  lea     rdx, ProcName; "MprAdminInitializeDllEx"
0x180016c62  mov     rcx, rax; hModule
0x180016c65  call    cs:__imp_GetProcAddress
0x180016c6c  nop     dword ptr [rax+rax+00h]
0x180016c71  mov     rbx, rax
0x180016c74  test    rax, rax
0x180016c77  jz      loc_180016D58
0x180016c7d  xor     edx, edx; Val
0x180016c7f  lea     rcx, [rbp+840h+var_8C0]; void *
0x180016c83  lea     r8d, [rdx+68h]; Size
0x180016c87  call    memset_0
0x180016c8c  lea     rcx, [rbp+840h+var_8C0]
0x180016c90  mov     rax, rbx
0x180016c93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016c98  mov     ebx, eax
0x180016c9a  test    eax, eax
0x180016c9c  jnz     loc_180016F50
0x180016ca2  test    cs:byte_1800CF404, 10h
0x180016ca9  jz      short loc_180016CDE
0x180016cab  lea     rax, aAdmininitializ; "AdminInitializeDllEx present"
0x180016cb2  mov     [rbp+840h+var_838], 3Ah ; ':'
0x180016cba  mov     [rbp+840h+var_840], rax
0x180016cbe  lea     r9d, [rbx+2]
0x180016cc2  lea     rax, [rbp+840h+var_850]
0x180016cc6  lea     rdx, RasDdmTraceInfo
0x180016ccd  mov     [rsp+940h+plpszSubStringArray], rax
0x180016cd2  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180016cd9  call    McGenEventWrite_EventWriteTransfer
0x180016cde  mov     al, [rbp+840h+var_8C0]
0x180016ce1  mov     [rsi+8], al
0x180016ce4  mov     rax, [rbp+840h+var_8B8]
0x180016ce8  mov     [rsi+10h], rax
0x180016cec  mov     rax, [rbp+840h+var_8B0]
0x180016cf0  mov     [rsi+18h], rax
0x180016cf4  mov     rax, [rbp+840h+var_8A8]
0x180016cf8  mov     [rsi+20h], rax
0x180016cfc  mov     rax, [rbp+840h+var_8A0]
0x180016d00  mov     [rsi+28h], rax
0x180016d04  mov     rax, [rbp+840h+var_898]
0x180016d08  mov     [rsi+48h], rax
0x180016d0c  mov     rax, [rbp+840h+var_890]
0x180016d10  mov     [rsi+68h], rax
0x180016d14  mov     rax, [rbp+840h+var_888]
0x180016d18  mov     [rsi+70h], rax
  ... truncated ...
```
