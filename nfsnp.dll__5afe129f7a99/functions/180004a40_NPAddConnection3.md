# NPAddConnection3

- ea: `0x180004a40`
- end: `0x180005c35`
- name: `NPAddConnection3`
- size: `4597`
- prototype: `DWORD __stdcall(HWND hwndOwner, LPNETRESOURCEW lpNetResource, LPWSTR lpPassword, LPWSTR lpUserName, DWORD dwFlags)`
- caller_count: `1`
- callee_count: `22`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800049c0`

## callees

- `0x1800016c8`
- `0x180002320`
- `0x180002508`
- `0x18000261c`
- `0x180004914`
- `0x180004a40`
- `0x180008b28`
- `0x180008d00`
- `0x180009004`
- `0x18000937c`
- `0x1800093e0`
- `0x18000945c`
- `0x1800094f4`
- `0x1800095a4`
- `0x180009a2c`
- `0x180009d1c`
- `0x18000b0d8`
- `0x18000c738`
- `0x18000d710`
- `0x180012e32`
- `0x180012e70`
- `0x180012f00`

## import_xrefs

- `msvcrt!wcsstr` at `0x180005575`
- `msvcrt!wcsstr` at `0x180005575`
- `msvcrt!wcschr` at `0x180004d62`
- `msvcrt!wcschr` at `0x180004e19`
- `msvcrt!wcschr` at `0x180005120`
- `msvcrt!wcschr` at `0x180004d62`
- `msvcrt!wcschr` at `0x180004e19`
- `msvcrt!wcschr` at `0x180005120`
- `msvcrt!wcspbrk` at `0x180004cc5`
- `msvcrt!wcspbrk` at `0x180004cc5`
- `msvcrt!_wcsnicmp` at `0x18000530f`
- `msvcrt!_wcsnicmp` at `0x18000530f`
- `msvcrt!wcscpy_s` at `0x1800055a0`
- `msvcrt!wcscpy_s` at `0x1800055a0`
- `msvcrt!wcsncpy_s` at `0x180004c5a`
- `msvcrt!wcsncpy_s` at `0x1800050ac`
- `msvcrt!wcsncpy_s` at `0x180005159`
- `msvcrt!wcsncpy_s` at `0x1800055c2`
- `msvcrt!wcsncpy_s` at `0x180004c5a`
- `msvcrt!wcsncpy_s` at `0x1800050ac`
- `msvcrt!wcsncpy_s` at `0x180005159`
- `msvcrt!wcsncpy_s` at `0x1800055c2`
- `ntdll!NtClose` at `0x180005a1e`
- `ntdll!NtClose` at `0x180005b0b`
- `ntdll!NtClose` at `0x180005a1e`
- `ntdll!NtClose` at `0x180005b0b`
- `ntdll!NtCreateFile` at `0x180005893`
- `ntdll!NtCreateFile` at `0x180005893`
- `ntdll!RtlInitUnicodeString` at `0x18000581c`
- `ntdll!RtlInitUnicodeString` at `0x18000581c`
- `KERNEL32!CloseHandle` at `0x1800051e0`
- `KERNEL32!CloseHandle` at `0x1800051e0`
- `KERNEL32!QueryDosDeviceW` at `0x1800056f2`
- `KERNEL32!QueryDosDeviceW` at `0x1800056f2`
- `KERNEL32!GetLastError` at `0x180004fa6`
- `KERNEL32!GetLastError` at `0x180005706`
- `KERNEL32!GetLastError` at `0x180005731`
- `KERNEL32!GetLastError` at `0x180005960`
- `KERNEL32!GetLastError` at `0x180004fa6`
- `KERNEL32!GetLastError` at `0x180005706`
- `KERNEL32!GetLastError` at `0x180005731`
- `KERNEL32!GetLastError` at `0x180005960`
- `KERNEL32!GetModuleHandleW` at `0x180004f92`
- `KERNEL32!GetModuleHandleW` at `0x180004f92`
- `KERNEL32!GlobalFree` at `0x180005ae7`
- `KERNEL32!GlobalFree` at `0x180005afb`
- `KERNEL32!GlobalFree` at `0x180005ae7`
- `KERNEL32!GlobalFree` at `0x180005afb`
- `KERNEL32!GetModuleFileNameW` at `0x1800052bb`
- `KERNEL32!GetModuleFileNameW` at `0x1800052bb`
- `KERNEL32!DefineDosDeviceW` at `0x180005950`
- `KERNEL32!DefineDosDeviceW` at `0x180005950`
- `ADVAPI32!LsaNtStatusToWinError` at `0x1800058a5`
- `ADVAPI32!LsaNtStatusToWinError` at `0x1800058a5`
- `ADVAPI32!LogonUserW` at `0x1800051c9`
- `ADVAPI32!LogonUserW` at `0x1800051c9`
- `ADVAPI32!EventWrite` at `0x18000568a`
- `ADVAPI32!EventWrite` at `0x18000568a`
- `ADVAPI32!RegCloseKey` at `0x1800053ab`
- `ADVAPI32!RegCloseKey` at `0x1800053ab`
- `ADVAPI32!RegQueryValueExW` at `0x18000538e`
- `ADVAPI32!RegQueryValueExW` at `0x18000538e`
- `ADVAPI32!RegOpenKeyExW` at `0x18000534c`
- `ADVAPI32!RegOpenKeyExW` at `0x18000534c`
- `WSOCK32!__imp_WSAStartup` at `0x180004b78`
- `WSOCK32!__imp_WSAStartup` at `0x180004b78`
- `WSOCK32!__imp_WSACleanup` at `0x180004e96`
- `WSOCK32!__imp_WSACleanup` at `0x180005b45`
- `WSOCK32!__imp_WSACleanup` at `0x180004e96`
- `WSOCK32!__imp_WSACleanup` at `0x180005b45`

## string_xrefs

- `0x180004f8b`: `nfsnp.dll`
- `0x1800052f5`: `mount.exe`
- `0x18000533e`: `SOFTWARE\Microsoft\ClientForNFS\CurrentVersion\MountUtility\Mount`
- `0x18000536b`: `MountAsAnonymousUser`

## pseudocode

```c
DWORD __stdcall NPAddConnection3(
        HWND hwndOwner,
        LPNETRESOURCEW lpNetResource,
        LPWSTR lpPassword,
        LPWSTR lpUserName,
        DWORD dwFlags)
{
  int v8; // edx
  int v9; // r8d
  char v10; // bl
  int v11; // ebx
  unsigned int v12; // r15d
  _QWORD *v13; // rcx
  wchar_t *v14; // rax
  wchar_t *v15; // rcx
  wchar_t *v16; // rdx
  _QWORD *v17; // rcx
  __int64 v18; // rdx
  wchar_t *v19; // r12
  wchar_t *v20; // rax
  __int64 v21; // rdx
  __int64 v22; // r13
  const wchar_t *i; // rcx
  wchar_t *v24; // rax
  __int64 v25; // rdx
  LPWSTR lpLocalName; // r8
  _QWORD *v28; // rcx
  _BOOL8 v29; // r12
  HMODULE ModuleHandleW; // r13
  DWORD LastError; // eax
  _QWORD *v32; // rcx
  __int64 v33; // rdx
  wchar_t v34; // ax
  wchar_t *j; // rcx
  wchar_t *v36; // rax
  const WCHAR *v37; // rbx
  int v38; // edi
  __int64 v39; // rax
  int v40; // eax
  __int64 v41; // r9
  _QWORD *v42; // rcx
  wchar_t *v43; // rax
  wchar_t *v44; // rdi
  wchar_t *v45; // rdi
  __int64 v46; // r9
  unsigned __int64 v47; // rbx
  int v48; // eax
  PVOID EaBuffer; // rdi
  __int64 EaLength; // r14
  __int64 v51; // rbx
  char v52; // al
  NTSTATUS v53; // eax
  ULONG v54; // eax
  __int64 v55; // rax
  _BYTE *v56; // rcx
  DWORD v57; // eax
  int v58; // eax
  void *v59; // rcx
  __int64 v60; // rdx
  _BYTE *v61; // rax
  BYTE Data[4]; // [rsp+60h] [rbp-A0h] BYREF
  ULONG v63; // [rsp+64h] [rbp-9Ch] BYREF
  HANDLE hObject; // [rsp+68h] [rbp-98h] BYREF
  DWORD cbData[2]; // [rsp+70h] [rbp-90h] BYREF
  PVOID hMem; // [rsp+78h] [rbp-88h] BYREF
  void *FileHandle; // [rsp+80h] [rbp-80h] BYREF
  __int128 v68; // [rsp+88h] [rbp-78h] BYREF
  LPWSTR lpRemoteName; // [rsp+98h] [rbp-68h]
  wchar_t *v70; // [rsp+A0h] [rbp-60h]
  _UNICODE_STRING DestinationString; // [rsp+A8h] [rbp-58h] BYREF
  HWND v72; // [rsp+B8h] [rbp-48h]
  char *v73; // [rsp+C0h] [rbp-40h]
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+C8h] [rbp-38h] BYREF
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+F8h] [rbp-8h] BYREF
  __int128 v76; // [rsp+110h] [rbp+10h] BYREF
  int v77; // [rsp+12Ch] [rbp+2Ch]
  __int64 v78; // [rsp+150h] [rbp+50h] BYREF
  LPWSTR v79; // [rsp+158h] [rbp+58h]
  wchar_t Str[260]; // [rsp+160h] [rbp+60h] BYREF
  WCHAR v81[260]; // [rsp+368h] [rbp+268h] BYREF
  int v82; // [rsp+570h] [rbp+470h]
  wchar_t v83[260]; // [rsp+578h] [rbp+478h] BYREF
  _BYTE v84[528]; // [rsp+780h] [rbp+680h] BYREF
  WSAData WSAData; // [rsp+990h] [rbp+890h] BYREF
  char v86[32]; // [rsp+B30h] [rbp+A30h] BYREF
  wchar_t Destination[2]; // [rsp+B50h] [rbp+A50h] BYREF
  wchar_t String[262]; // [rsp+B54h] [rbp+A54h] BYREF
  WCHAR SourceString[264]; // [rsp+D60h] [rbp+C60h] BYREF
  wchar_t TargetPath[264]; // [rsp+F70h] [rbp+E70h] BYREF
  wchar_t Source[264]; // [rsp+1180h] [rbp+1080h] BYREF
  WCHAR Filename[264]; // [rsp+1390h] [rbp+1290h] BYREF
  __int16 v93; // [rsp+15A0h] [rbp+14A0h] BYREF
  DWORD dwFlagsa; // [rsp+1830h] [rbp+1730h]

  v72 = hwndOwner;
  *(_QWORD *)cbData = lpUserName;
  strcpy(v86, "NPAddConnection3");
  memset_0(Source, 0, 0x208u);
  LODWORD(lpRemoteName) = 0;
  v68 = 0;
  memset_0(&v78, 0, 0x838u);
  memset_0(&v76, 0, 0x40u);
  IoStatusBlock = 0;
  memset(&ObjectAttributes, 0, 44);
  DestinationString = 0;
  memset_0(&WSAData, 0, sizeof(WSAData));
  FileHandle = 0;
  hMem = 0;
  v63 = 0;
  *(_DWORD *)Data = 0;
  v10 = dwFlags;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_sDD(*((_QWORD *)WPP_GLOBAL_Control + 2), v8, v9, (unsigned int)v86, lpNetResource->dwType, dwFlags);
  v93 = 0;
  String[257] = 0;
  if ( !WSAStartup(0x101u, &WSAData) )
  {
    if ( (int)NfsNpIsClientRunning(Data) < 0 || !*(_DWORD *)Data )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 129, &WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids, v86);
      v11 = 1222;
      goto LABEL_57;
    }
    v12 = 0;
    memset_0(&v78, 0, 0x838u);
    if ( lpNetResource->lpLocalName )
    {
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      {
        WPP_SF_sS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          130,
          (unsigned int)&WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids,
          (unsigned int)v86,
          (__int64)lpNetResource->lpLocalName);
        v13 = WPP_GLOBAL_Control;
      }
      v12 = 1;
    }
    else
    {
      v13 = WPP_GLOBAL_Control;
    }
    if ( v13 != &WPP_GLOBAL_Control && (*((_BYTE *)v13 + 28) & 8) != 0 )
      WPP_SF_sS(
        v13[2],
        131,
        (unsigned int)&WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids,
        (unsigned int)v86,
        (__int64)lpNetResource->lpRemoteName);
    wcsncpy_s(Destination, 0x104u, lpNetResource->lpRemoteName, 0x103u);
    if ( Destination[0] == 92 )
    {
      if ( Destination[1] != 92 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 132, &WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids, v86);
        v11 = 67;
        goto LABEL_57;
      }
      v14 = wcspbrk(String, L"\\/");
      v15 = v14;
      if ( !v14 )
      {
        if ( v12 )
        {
          v15 = (wchar_t *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 133, &WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids, v86);
          v16 = String;
          goto LABEL_29;
        }
        v17 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
          return 0;
        v18 = 134;
LABEL_209:
        WPP_SF_s(v17[2], v18, &WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids, v86);
        return 0;
      }
      v19 = String;
      *v14 = 0;
LABEL_46:
      v22 = (__int64)(v15 + 1);
      v70 = v19;
      v73 = (char *)(v15 + 1);
      for ( i = v15 + 1; ; i = v24 + 1 )
      {
        v24 = wcschr(i, 0x2Fu);
        if ( !v24 )
          break;
        *v24 = 92;
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_sSS(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)v19, v22);
      if ( v12 )
        lpLocalName = lpNetResource->lpLocalName;
      else
        lpLocalName = 0;
      if ( (int)NfsNpCreateObjectName(SourceString, v25, lpLocalName, v19, v22) < 0 )
      {
        v11 = 67;
        goto LABEL_57;
      }
      v28 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      {
        WPP_SF_sS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          141,
          (unsigned int)&WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids,
          (unsigned int)v86,
          (__int64)SourceString);
        v28 = WPP_GLOBAL_Control;
      }
      dwFlagsa = dwFlags & 8;
      v29 = (v10 & 8) != 0;
      if ( v28 != &WPP_GLOBAL_Control && (*((_BYTE *)v28 + 28) & 8) != 0 )
        WPP_SF_sdd(
          v28[2],
          142,
          (unsigned int)&WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids,
          (unsigned int)v86,
          3,
          v29);
      ModuleHandleW = GetModuleHandleW(L"nfsnp.dll");
      if ( !ModuleHandleW )
      {
        LastError = GetLastError();
        v11 = LastError;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            143,
            (unsigned int)&WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids,
            (unsigned int)v86,
            LastError);
        LOG_ERROR_EVENT_WIN32();
        goto LABEL_57;
      }
      if ( lpPassword )
      {
        v32 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        {
          v33 = 145;
          goto LABEL_80;
        }
      }
      else
      {
        v32 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          v33 = 144;
LABEL_80:
          WPP_SF_s(v32[2], v33, &WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids, v86);
          v32 = WPP_GLOBAL_Control;
        }
      }
      if ( lpUserName )
      {
        wcsncpy_s(Source, 0x104u, lpUserName, 0x103u);
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          WPP_SF_sS(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            147,
            (unsigned int)&WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids,
            (unsigned int)v86,
            (__int64)lpUserName);
        v34 = Source[0];
        for ( j = Source; *j; v34 = *j )
        {
          if ( v34 != 92 )
            break;
          ++j;
        }
        v36 = wcschr(j, 0x5Cu);
        if ( v36 )
        {
          hObject = 0;
          *v36 = 0;
          v37 = v36 + 1;
          wcsncpy_s(v83, 0x104u, Source, 0x103u);
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
            WPP_SF_sSS(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)v37, (__int64)v83);
          if ( !LogonUserW(v37, Source, lpPassword, 3u, 0, &hObject) )
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
              WPP_SF_sd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                149,
                (unsigned int)&WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids,
                (unsigned int)v86,
                31);
            v11 = lpPassword != 0 ? 1311 : 86;
            goto LABEL_57;
          }
          CloseHandle(hObject);
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
            WPP_SF_sd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              150,
              (unsigned int)&WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids,
              (unsigned int)v86,
              0);
        }
        else
        {
          v83[0] = 0;
        }
      }
      else if ( v32 != &WPP_GLOBAL_Control && (*((_BYTE *)v32 + 28) & 4) != 0 )
      {
        WPP_SF_s(v32[2], 146, &WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids, v86);
      }
      v78 = *(_QWORD *)cbData;
      v79 = lpPassword;
      *(_QWORD *)&v76 = &v93;
      v38 = 0;
      DWORD2(v76) = 260;
      memset_0(Filename, 0, 0x208u);
      if ( GetModuleFileNameW(0, Filename, 0x104u) )
      {
        v39 = -1;
        do
          ++v39;
        while ( Filename[v39] );
        if ( (unsigned int)v39 >= 9 && !_wcsnicmp(&Filename[(unsigned int)(v39 - 9)], L"mount.exe", 9u) )
        {
          v38 = 1;
          hObject = 0;
          if ( !RegOpenKeyExW(
                  HKEY_CURRENT_USER,
                  L"SOFTWARE\\Microsoft\\ClientForNFS\\CurrentVersion\\MountUtility\\Mount",
                  0,
                  0x20019u,
                  (PHKEY)&hObject) )
          {
            cbData[0] = 4;
            *(_DWORD *)Data = 0;
            if ( !RegQueryValueExW((HKEY)hObject, L"MountAsAnonymousUser", 0, 0, Data, cbData) && *(_DWORD *)Data )
              v38 = 16;
            RegCloseKey((HKEY)hObject);
          }
        }
      }
      *((_QWORD *)&v68 + 1) = lpNetResource->lpLocalName;
      lpRemoteName = lpNetResource->lpRemoteName;
      LODWORD(v68) = lpNetResource->dwType;
      v40 = DisplayConfigDlg(
              (_DWORD)ModuleHandleW,
              (_DWORD)v72,
              (unsigned int)&v76,
              (unsigned int)&v68,
              (__int64)&v78,
              v29,
              v38);
      v11 = v40;
      switch ( v40 )
      {
        case 1223:
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 159, &WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids, v86);
          v11 = 1223;
          goto LABEL_57;
        case 1326:
          if ( dwFlagsa || v38 == 16 )
          {
            v42 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            {
              WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 160, &WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids, v86);
              v42 = WPP_GLOBAL_Control;
            }
            v79 = 0;
            v78 = 0;
            v81[0] = 0;
            Str[0] = 0;
LABEL_131:
            if ( v42 != &WPP_GLOBAL_Control && (*((_BYTE *)v42 + 28) & 8) != 0 )
            {
              WPP_SF_sS(
                v42[2],
                162,
                (unsigned int)&WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids,
                (unsigned int)v86,
                (__int64)v83);
              v42 = WPP_GLOBAL_Control;
            }
            if ( v82 == 5 )
            {
              if ( v42 != &WPP_GLOBAL_Control && (*((_BYTE *)v42 + 28) & 8) != 0 )
                WPP_SF_(v42[2], 163, &WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids);
              v43 = wcsstr(Str, L"\\");
              v44 = v43;
              if ( v43 )
              {
                wcsncpy_s(TargetPath, 0x104u, Str, v43 - Str);
                v47 = v44 - Str;
                if ( v47 >= 260 )
                  _report_rangecheckfailure();
                v45 = v44 + 1;
                TargetPath[v47] = 0;
              }
              else
              {
                v45 = Str;
                wcscpy_s(TargetPath, 0x104u, &::Source);
              }
              v48 = BuildEA((unsigned __int64)TargetPath, v45, v81, v46, &v76, v82, (char **)&hMem, &v63);
              v11 = v48;
              if ( v48 )
              {
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                {
                  WPP_SF_sd(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    164,
                    (unsigned int)&WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids,
                    (unsigned int)v86,
                    v48);
                }
LABEL_146:
                if ( g_hEventProviderHandle && *(int *)&g_dwLoggingLevel >= 0 )
                  EventWrite(g_hEventProviderHandle, &EVENT_ERROR_BUILDEA, 0, 0);
                goto LABEL_57;
              }
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
              {
                WPP_SF_sd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  165,
                  (unsigned int)&WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids,
                  (unsigned int)v86,
                  0);
              }
            }
            else if ( (unsigned int)BuildEA((unsigned __int64)v84, Str, v81, v41, &v76, v82, (char **)&hMem, &v63) )
            {
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
              {
                WPP_SF_sd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  166,
                  (unsigned int)&WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids,
                  (unsigned int)v86,
                  v11);
              }
              goto LABEL_146;
            }
            EaBuffer = hMem;
            EaLength = v63;
            if ( v12 )
            {
              if ( QueryDosDeviceW(lpNetResource->lpLocalName, TargetPath, 0x80u) )
              {
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                {
                  WPP_SF_sS(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    168,
                    (unsigned int)&WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids,
                    (unsigned int)v86,
                    (__int64)TargetPath);
                }
                goto LABEL_158;
              }
              if ( GetLastError() != 2 )
              {
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                {
                  v51 = *((_QWORD *)WPP_GLOBAL_Control + 2);
                  v52 = GetLastError();
                  WPP_SF_sd(
                    v51,
                    167,
                    (unsigned int)&WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids,
                    (unsigned int)v86,
                    v52);
                }
LABEL_158:
                v11 = 85;
                goto LABEL_194;
              }
            }
            RtlInitUnicodeString(&DestinationString, SourceString);
            DestinationString.MaximumLength -= 2;
            ObjectAttributes.ObjectName = &DestinationString;
            ObjectAttributes.Length = 48;
            ObjectAttributes.RootDirectory = 0;
            ObjectAttributes.Attributes = 64;
            *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
            v53 = NtCreateFile(
                    &FileHandle,
                    0x100000u,
                    &ObjectAttributes,
                    &IoStatusBlock,
                    0,
                    2u,
                    7u,
                    1u,
                    0xA0u,
                    EaBuffer,
                    EaLength);
            if ( v53 )
            {
              v54 = LsaNtStatusToWinError(v53);
              v11 = v54;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
              {
                WPP_SF_sd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  169,
                  (unsigned int)&WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids,
                  (unsigned int)v86,
                  v54);
              }
            }
            else
            {
              v55 = EaLength;
              v56 = EaBuffer;
              if ( (_DWORD)EaLength )
              {
                do
                {
                  *v56++ = 0;
                  --v55;
                }
                while ( v55 );
              }
              if ( !v12 )
                goto LABEL_180;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
              {
                WPP_SF_s(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  170,
                  &WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids,
                  v86);
              }
              if ( DefineDosDeviceW(9u, lpNetResource->lpLocalName, SourceString) )
              {
LABEL_180:
                v58 = AddDeviceEntry(lpNetResource->lpLocalName, v70, v73, SourceString, v77);
                v11 = v58;
                if ( !v58 )
                {
                  GlobalFree(EaBuffer);
                  NtClose(FileHandle);
                  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                  {
                    WPP_SF_s(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      173,
                      &WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids,
                      v86);
                  }
                  WSACleanup();
                  return 0;
                }
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                {
                  WPP_SF_sd(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    172,
                    (unsigned int)&WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids,
                    (unsigned int)v86,
                    v58);
                }
                if ( v12 )
                  RemoveDosDevice(lpNetResource->lpLocalName, SourceString);
              }
              else
              {
                v57 = GetLastError();
                v11 = v57;
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                {
                  WPP_SF_sd(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    171,
                    (unsigned int)&WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids,
                    (unsigned int)v86,
                    v57);
                }
              }
              NtClose(FileHandle);
              if ( (unsigned int)DeleteConnection(
                                   1,
                                   v12,
                                   *((_QWORD *)&lpNetResource->lpLocalName + (v12 ^ 1LL)),
                                   SourceString) )
              {
                v59 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                {
                  WPP_SF_s(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    174,
                    &WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids,
                    v86);
                }
              }
              *((_QWORD *)&v68 + 1) = lpNetResource->lpLocalName;
              lpRemoteName = lpNetResource->lpRemoteName;
              LODWORD(v68) = lpNetResource->dwType;
              if ( (unsigned int)DeleteRememberedConnection(v59, &v68)
                && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
              {
                WPP_SF_s(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  175,
                  &WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids,
                  v86);
              }
            }
LABEL_194:
            v60 = EaLength;
            v61 = EaBuffer;
            if ( (_DWORD)EaLength )
            {
              do
              {
                *v61++ = 0;
                --v60;
              }
              while ( v60 );
            }
            GlobalFree(EaBuffer);
            goto LABEL_57;
          }
          break;
        case 0:
          v42 = WPP_GLOBAL_Control;
          goto LABEL_131;
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          161,
          (unsigned int)&WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids,
          (unsigned int)v86,
          v40);
      goto LABEL_57;
    }
    v20 = wcschr(Destination, 0x3Au);
    if ( v20 )
    {
      *v20 = 0;
      v15 = v20 + 1;
      if ( v20[1] == 47 )
      {
        v19 = Destination;
        *v15 = 0;
        goto LABEL_46;
      }
      if ( *v15 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_sS(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            139,
            (unsigned int)&WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids,
            (unsigned int)v86,
            (__int64)v15);
        goto LABEL_40;
      }
      if ( !v12 )
      {
        v17 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
          return 0;
        v18 = 138;
        goto LABEL_209;
      }
      v15 = (wchar_t *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v21 = 137;
        goto LABEL_39;
      }
    }
    else
    {
      if ( !v12 )
      {
        v17 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
          return 0;
        v18 = 136;
        goto LABEL_209;
      }
      v15 = (wchar_t *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v21 = 135;
LABEL_39:
        WPP_SF_s(*((_QWORD *)v15 + 2), v21, &WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids, v86);
      }
    }
LABEL_40:
    v16 = Destination;
LABEL_29:
    v11 = 67;
    LogInfoEventString(v15, v16);
LABEL_57:
    WSACleanup();
    goto LABEL_58;
  }
  v11 = 1222;
LABEL_58:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      176,
      (unsigned int)&WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids,
      (unsigned int)v86,
      v11);
  return v11;
}

```

## disassembly

```asm
0x180004a40  push    rbp
0x180004a42  push    rbx
0x180004a43  push    rsi
0x180004a44  push    rdi
0x180004a45  push    r12
0x180004a47  push    r13
0x180004a49  push    r14
0x180004a4b  push    r15
0x180004a4d  lea     rbp, [rsp-16C8h]
0x180004a55  mov     eax, 17C8h
0x180004a5a  call    _alloca_probe
0x180004a5f  sub     rsp, rax
0x180004a62  mov     rax, cs:__security_cookie
0x180004a69  xor     rax, rsp
0x180004a6c  mov     [rbp+1700h+var_50], rax
0x180004a73  movups  xmm0, xmmword ptr cs:aNpaddconnectio_1; "NPAddConnection3"
0x180004a7a  mov     al, byte ptr cs:aNpaddconnectio_1+10h; ""
0x180004a80  mov     r14, r8
0x180004a83  mov     rsi, rdx
0x180004a86  mov     [rbp+1700h+var_1748], rcx
0x180004a8a  xor     edx, edx; Val
0x180004a8c  mov     qword ptr [rsp+1800h+cbData], r9
0x180004a91  mov     r8d, 208h; Size
0x180004a97  mov     [rbp+1700h+var_CD0+10h], al
0x180004a9d  lea     rcx, [rbp+1700h+Source]; void *
0x180004aa4  mov     rdi, r9
0x180004aa7  movups  xmmword ptr [rbp+1700h+var_CD0], xmm0
0x180004aae  call    memset_0
0x180004ab3  xor     eax, eax
0x180004ab5  lea     rcx, [rbp+1700h+var_16B0]; void *
0x180004ab9  xorps   xmm0, xmm0
0x180004abc  mov     dword ptr [rbp+1700h+var_1768], eax
0x180004abf  xor     edx, edx; Val
0x180004ac1  mov     r8d, 838h; Size
0x180004ac7  movups  [rbp+1700h+var_1778], xmm0
0x180004acb  call    memset_0
0x180004ad0  xor     edx, edx; Val
0x180004ad2  lea     rcx, [rbp+1700h+var_16F0]; void *
0x180004ad6  lea     r8d, [rdx+40h]; Size
0x180004ada  call    memset_0
0x180004adf  xorps   xmm0, xmm0
0x180004ae2  lea     rcx, [rbp+1700h+WSAData]; void *
0x180004ae9  movups  xmmword ptr [rbp+1700h+ObjectAttributes.ObjectName], xmm0
0x180004aed  xor     eax, eax
0x180004aef  xor     edx, edx; Val
0x180004af1  mov     r8d, 198h; Size
0x180004af7  movups  xmmword ptr [rbp+1700h+ObjectAttributes+1Ch], xmm0
0x180004afb  movups  xmmword ptr [rbp+1700h+IoStatusBlock], xmm0
0x180004aff  movups  xmmword ptr [rbp+1700h+ObjectAttributes.Length], xmm0
0x180004b03  movups  xmmword ptr [rbp+1700h+DestinationString.Length], xmm0
0x180004b07  call    memset_0
0x180004b0c  xor     r13d, r13d
0x180004b0f  mov     [rbp+1700h+FileHandle], r13
0x180004b13  mov     [rsp+1800h+hMem], r13
0x180004b18  mov     [rsp+1800h+var_179C], r13d
0x180004b1d  mov     dword ptr [rsp+1800h+Data], r13d
0x180004b22  mov     rcx, cs:WPP_GLOBAL_Control
0x180004b29  lea     r12, WPP_GLOBAL_Control
0x180004b30  mov     ebx, [rbp+1700h+dwFlags]
0x180004b36  cmp     rcx, r12
0x180004b39  jz      short loc_180004B5C
0x180004b3b  test    byte ptr [rcx+1Ch], 1
0x180004b3f  jz      short loc_180004B5C
0x180004b41  mov     eax, [rsi+4]
0x180004b44  lea     r9, [rbp+1700h+var_CD0]
0x180004b4b  mov     rcx, [rcx+10h]
0x180004b4f  mov     dword ptr [rsp+1800h+phToken], ebx
0x180004b53  mov     [rsp+1800h+dwLogonProvider], eax
0x180004b57  call    WPP_SF_sDD
0x180004b5c  mov     ecx, 101h; wVersionRequested
0x180004b61  mov     [rbp+1700h+var_260], r13w
0x180004b69  lea     rdx, [rbp+1700h+WSAData]; lpWSAData
0x180004b70  mov     [rbp+1700h+var_AAA], r13w
0x180004b78  call    cs:__imp_WSAStartup
0x180004b7f  nop     dword ptr [rax+rax+00h]
0x180004b84  test    eax, eax
0x180004b86  jz      short loc_180004B92
0x180004b88  mov     ebx, 4C6h
0x180004b8d  jmp     loc_180004EA2
0x180004b92  lea     rcx, [rsp+1800h+Data]
0x180004b97  call    NfsNpIsClientRunning
0x180004b9c  test    eax, eax
0x180004b9e  js      loc_180005BF7
0x180004ba4  cmp     dword ptr [rsp+1800h+Data], r13d
0x180004ba9  jz      loc_180005BF7
0x180004baf  xor     edx, edx; Val
0x180004bb1  lea     rcx, [rbp+1700h+var_16B0]; void *
0x180004bb5  mov     r8d, 838h; Size
0x180004bbb  mov     r15d, r13d
0x180004bbe  call    memset_0
0x180004bc3  mov     rax, [rsi+10h]
0x180004bc7  test    rax, rax
0x180004bca  jz      short loc_180004C0E
0x180004bcc  mov     rcx, cs:WPP_GLOBAL_Control
0x180004bd3  cmp     rcx, r12
0x180004bd6  jz      short loc_180004C06
0x180004bd8  test    byte ptr [rcx+1Ch], 8
0x180004bdc  jz      short loc_180004C06
0x180004bde  mov     rcx, [rcx+10h]
0x180004be2  lea     r9, [rbp+1700h+var_CD0]
0x180004be9  mov     edx, 82h
0x180004bee  mov     qword ptr [rsp+1800h+dwLogonProvider], rax
0x180004bf3  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x180004bfa  call    WPP_SF_sS
0x180004bff  mov     rcx, cs:WPP_GLOBAL_Control
0x180004c06  mov     r15d, 1
0x180004c0c  jmp     short loc_180004C15
0x180004c0e  mov     rcx, cs:WPP_GLOBAL_Control
0x180004c15  cmp     rcx, r12
0x180004c18  jz      short loc_180004C45
0x180004c1a  test    byte ptr [rcx+1Ch], 8
0x180004c1e  jz      short loc_180004C45
0x180004c20  mov     rax, [rsi+18h]
0x180004c24  lea     r9, [rbp+1700h+var_CD0]
0x180004c2b  mov     rcx, [rcx+10h]
0x180004c2f  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x180004c36  mov     edx, 83h
0x180004c3b  mov     qword ptr [rsp+1800h+dwLogonProvider], rax
0x180004c40  call    WPP_SF_sS
0x180004c45  mov     r8, [rsi+18h]; Source
0x180004c49  lea     rcx, [rbp+1700h+Destination]; Destination
0x180004c50  mov     r9d, 103h; MaxCount
0x180004c56  lea     edx, [r9+1]; SizeInWords
0x180004c5a  call    cs:__imp_wcsncpy_s
0x180004c61  nop     dword ptr [rax+rax+00h]
0x180004c66  mov     eax, 5Ch ; '\'
0x180004c6b  cmp     [rbp+1700h+Destination], ax
0x180004c72  jnz     loc_180004D56
0x180004c78  cmp     [rbp+1700h+var_CAE], ax
0x180004c7f  jz      short loc_180004CB7
0x180004c81  mov     rcx, cs:WPP_GLOBAL_Control
0x180004c88  cmp     rcx, r12
0x180004c8b  jz      short loc_180004CAD
0x180004c8d  test    byte ptr [rcx+1Ch], 2
0x180004c91  jz      short loc_180004CAD
0x180004c93  mov     rcx, [rcx+10h]
0x180004c97  lea     edx, [rax+28h]
0x180004c9a  lea     r9, [rbp+1700h+var_CD0]
0x180004ca1  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x180004ca8  call    WPP_SF_s
0x180004cad  mov     ebx, 43h ; 'C'
0x180004cb2  jmp     loc_180004E96
0x180004cb7  lea     rdx, asc_180014F34; "\\/"
0x180004cbe  lea     rcx, [rbp+1700h+String]; String
0x180004cc5  call    cs:__imp_wcspbrk
0x180004ccc  nop     dword ptr [rax+rax+00h]
0x180004cd1  mov     rcx, rax
0x180004cd4  test    rax, rax
0x180004cd7  jnz     short loc_180004D46
0x180004cd9  test    r15d, r15d
0x180004cdc  jz      short loc_180004D22
0x180004cde  mov     rcx, cs:WPP_GLOBAL_Control
0x180004ce5  cmp     rcx, r12
0x180004ce8  jz      short loc_180004D0C
0x180004cea  test    byte ptr [rcx+1Ch], 2
0x180004cee  jz      short loc_180004D0C
0x180004cf0  mov     rcx, [rcx+10h]
0x180004cf4  lea     r9, [rbp+1700h+var_CD0]
0x180004cfb  mov     edx, 85h
0x180004d00  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x180004d07  call    WPP_SF_s
0x180004d0c  lea     rdx, [rbp+1700h+String]
0x180004d13  mov     ebx, 43h ; 'C'
0x180004d18  call    LogInfoEventString
0x180004d1d  jmp     loc_180004E96
0x180004d22  mov     rcx, cs:WPP_GLOBAL_Control
0x180004d29  cmp     rcx, r12
0x180004d2c  jz      loc_180005BB0
0x180004d32  test    byte ptr [rcx+1Ch], 4
0x180004d36  jz      loc_180005BB0
0x180004d3c  mov     edx, 86h
0x180004d41  jmp     loc_180005B99
0x180004d46  lea     r12, [rbp+1700h+String]
0x180004d4d  mov     [rax], r13w
0x180004d51  jmp     loc_180004DFA
0x180004d56  mov     edx, 3Ah ; ':'; Ch
0x180004d5b  lea     rcx, [rbp+1700h+Destination]; Str
0x180004d62  call    cs:__imp_wcschr
0x180004d69  nop     dword ptr [rax+rax+00h]
0x180004d6e  mov     rcx, rax
0x180004d71  test    rax, rax
0x180004d74  jnz     short loc_180004DD9
0x180004d76  test    r15d, r15d
0x180004d79  jz      short loc_180004DB5
0x180004d7b  mov     rcx, cs:WPP_GLOBAL_Control
0x180004d82  cmp     rcx, r12
0x180004d85  jz      short loc_180004DA9
0x180004d87  test    byte ptr [rcx+1Ch], 2
0x180004d8b  jz      short loc_180004DA9
0x180004d8d  mov     edx, 87h
0x180004d92  mov     rcx, [rcx+10h]
0x180004d96  lea     r9, [rbp+1700h+var_CD0]
0x180004d9d  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x180004da4  call    WPP_SF_s
0x180004da9  lea     rdx, [rbp+1700h+Destination]
0x180004db0  jmp     loc_180004D13
0x180004db5  mov     rcx, cs:WPP_GLOBAL_Control
0x180004dbc  cmp     rcx, r12
0x180004dbf  jz      loc_180005BB0
0x180004dc5  test    byte ptr [rcx+1Ch], 4
0x180004dc9  jz      loc_180005BB0
0x180004dcf  mov     edx, 88h
0x180004dd4  jmp     loc_180005B99
0x180004dd9  mov     [rax], r13w
0x180004ddd  add     rcx, 2
0x180004de1  mov     eax, 2Fh ; '/'
0x180004de6  cmp     [rcx], ax
0x180004de9  jnz     loc_180005B53
0x180004def  lea     r12, [rbp+1700h+Destination]
0x180004df6  mov     [rcx], r13w
0x180004dfa  lea     r13, [rcx+2]
0x180004dfe  mov     [rbp+1700h+var_1760], r12
0x180004e02  mov     [rbp+1700h+var_1740], r13
0x180004e06  mov     rcx, r13
0x180004e09  jmp     short loc_180004E14
0x180004e0b  mov     word ptr [rax], 5Ch ; '\'
0x180004e10  lea     rcx, [rax+2]; Str
0x180004e14  mov     edx, 2Fh ; '/'; Ch
0x180004e19  call    cs:__imp_wcschr
0x180004e20  nop     dword ptr [rax+rax+00h]
0x180004e25  test    rax, rax
0x180004e28  jnz     short loc_180004E0B
0x180004e2a  mov     rcx, cs:WPP_GLOBAL_Control
0x180004e31  lea     rax, WPP_GLOBAL_Control
0x180004e38  cmp     rcx, rax
0x180004e3b  jz      short loc_180004E62
0x180004e3d  test    byte ptr [rcx+1Ch], 8
0x180004e41  jz      short loc_180004E62
0x180004e43  mov     rcx, [rcx+10h]; LoggerHandle
0x180004e47  lea     r9, [rbp+1700h+var_CD0]
0x180004e4e  mov     edx, 8Ch
0x180004e53  mov     [rsp+1800h+phToken], r13; __int64
0x180004e58  mov     qword ptr [rsp+1800h+dwLogonProvider], r12; __int64
0x180004e5d  call    WPP_SF_sSS
0x180004e62  xor     eax, eax
0x180004e64  test    r15d, r15d
0x180004e67  jz      short loc_180004E6F
0x180004e69  mov     r8, [rsi+10h]
0x180004e6d  jmp     short loc_180004E72
0x180004e6f  mov     r8, rax
0x180004e72  mov     r9, r12
0x180004e75  mov     qword ptr [rsp+1800h+dwLogonProvider], r13
0x180004e7a  lea     rcx, [rbp+1700h+SourceString]
0x180004e81  call    NfsNpCreateObjectName
0x180004e86  test    eax, eax
0x180004e88  jns     short loc_180004EFA
0x180004e8a  mov     ebx, 43h ; 'C'
0x180004e8f  lea     r12, WPP_GLOBAL_Control
0x180004e96  call    cs:__imp_WSACleanup
0x180004e9d  nop     dword ptr [rax+rax+00h]
0x180004ea2  mov     rcx, cs:WPP_GLOBAL_Control
0x180004ea9  cmp     rcx, r12
0x180004eac  jz      short loc_180004ED4
0x180004eae  test    byte ptr [rcx+1Ch], 2
0x180004eb2  jz      short loc_180004ED4
0x180004eb4  mov     rcx, [rcx+10h]
0x180004eb8  lea     r9, [rbp+1700h+var_CD0]
0x180004ebf  mov     edx, 0B0h
0x180004ec4  mov     [rsp+1800h+dwLogonProvider], ebx
0x180004ec8  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x180004ecf  call    WPP_SF_sd
0x180004ed4  mov     eax, ebx
0x180004ed6  mov     rcx, [rbp+1700h+var_50]
0x180004edd  xor     rcx, rsp; StackCookie
0x180004ee0  call    __security_check_cookie
0x180004ee5  add     rsp, 17C8h
0x180004eec  pop     r15
0x180004eee  pop     r14
0x180004ef0  pop     r13
0x180004ef2  pop     r12
0x180004ef4  pop     rdi
0x180004ef5  pop     rsi
0x180004ef6  pop     rbx
0x180004ef7  pop     rbp
0x180004ef8  retn
0x180004efa  mov     rcx, cs:WPP_GLOBAL_Control
0x180004f01  lea     r13, WPP_GLOBAL_Control
0x180004f08  cmp     rcx, r13
0x180004f0b  jz      short loc_180004F42
0x180004f0d  test    byte ptr [rcx+1Ch], 8
0x180004f11  jz      short loc_180004F42
0x180004f13  mov     rcx, [rcx+10h]
0x180004f17  lea     rax, [rbp+1700h+SourceString]
0x180004f1e  mov     edx, 8Dh
0x180004f23  mov     qword ptr [rsp+1800h+dwLogonProvider], rax
0x180004f28  lea     r9, [rbp+1700h+var_CD0]
0x180004f2f  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x180004f36  call    WPP_SF_sS
0x180004f3b  mov     rcx, cs:WPP_GLOBAL_Control
0x180004f42  and     ebx, 8
0x180004f45  mov     [rbp+1700h+dwFlags], ebx
0x180004f4b  mov     ebx, 0
0x180004f50  mov     r12d, ebx
0x180004f53  setnz   r12b
0x180004f57  cmp     rcx, r13
0x180004f5a  jz      short loc_180004F8B
0x180004f5c  test    byte ptr [rcx+1Ch], 8
0x180004f60  jz      short loc_180004F8B
0x180004f62  mov     rcx, [rcx+10h]
0x180004f66  lea     r9, [rbp+1700h+var_CD0]
  ... truncated ...
```
