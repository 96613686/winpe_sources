# NPAddConnection3

- ea: `0x180004720`
- end: `0x180005842`
- name: `NPAddConnection3`
- size: `4386`
- prototype: `DWORD __stdcall(HWND hwndOwner, LPNETRESOURCEW lpNetResource, LPWSTR lpPassword, LPWSTR lpUserName, DWORD dwFlags)`
- caller_count: `1`
- callee_count: `22`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800046a0`

## callees

- `0x1800016c8`
- `0x18000222c`
- `0x1800023f0`
- `0x1800024e8`
- `0x180004604`
- `0x180004720`
- `0x180008548`
- `0x180008730`
- `0x1800089d4`
- `0x180008d20`
- `0x180008d7c`
- `0x180008df0`
- `0x180008e80`
- `0x180008f28`
- `0x180009390`
- `0x180009660`
- `0x18000a92c`
- `0x18000be24`
- `0x18000cc98`
- `0x180011b62`
- `0x180011ba0`
- `0x180011c30`

## import_xrefs

- `msvcrt!wcsstr` at `0x1800051e8`
- `msvcrt!wcsstr` at `0x1800051e8`
- `msvcrt!wcschr` at `0x180004a30`
- `msvcrt!wcschr` at `0x180004ae1`
- `msvcrt!wcschr` at `0x180004dc9`
- `msvcrt!wcschr` at `0x180004a30`
- `msvcrt!wcschr` at `0x180004ae1`
- `msvcrt!wcschr` at `0x180004dc9`
- `msvcrt!wcspbrk` at `0x180004999`
- `msvcrt!wcspbrk` at `0x180004999`
- `msvcrt!_wcsnicmp` at `0x180004f9a`
- `msvcrt!_wcsnicmp` at `0x180004f9a`
- `msvcrt!wcscpy_s` at `0x18000520d`
- `msvcrt!wcscpy_s` at `0x18000520d`
- `msvcrt!wcsncpy_s` at `0x180004934`
- `msvcrt!wcsncpy_s` at `0x180004d5b`
- `msvcrt!wcsncpy_s` at `0x180004dfc`
- `msvcrt!wcsncpy_s` at `0x180005229`
- `msvcrt!wcsncpy_s` at `0x180004934`
- `msvcrt!wcsncpy_s` at `0x180004d5b`
- `msvcrt!wcsncpy_s` at `0x180004dfc`
- `msvcrt!wcsncpy_s` at `0x180005229`
- `ntdll!NtClose` at `0x180005649`
- `ntdll!NtClose` at `0x180005724`
- `ntdll!NtClose` at `0x180005649`
- `ntdll!NtClose` at `0x180005724`
- `ntdll!NtCreateFile` at `0x1800054d6`
- `ntdll!NtCreateFile` at `0x1800054d6`
- `ntdll!RtlInitUnicodeString` at `0x180005465`
- `ntdll!RtlInitUnicodeString` at `0x180005465`
- `KERNEL32!CloseHandle` at `0x180004e77`
- `KERNEL32!CloseHandle` at `0x180004e77`
- `KERNEL32!QueryDosDeviceW` at `0x18000534d`
- `KERNEL32!QueryDosDeviceW` at `0x18000534d`
- `KERNEL32!GetLastError` at `0x180004c5b`
- `KERNEL32!GetLastError` at `0x18000535b`
- `KERNEL32!GetLastError` at `0x180005380`
- `KERNEL32!GetLastError` at `0x180005591`
- `KERNEL32!GetLastError` at `0x180004c5b`
- `KERNEL32!GetLastError` at `0x18000535b`
- `KERNEL32!GetLastError` at `0x180005380`
- `KERNEL32!GetLastError` at `0x180005591`
- `KERNEL32!GetModuleHandleW` at `0x180004c4d`
- `KERNEL32!GetModuleHandleW` at `0x180004c4d`
- `KERNEL32!GlobalFree` at `0x18000570c`
- `KERNEL32!GlobalFree` at `0x18000571a`
- `KERNEL32!GlobalFree` at `0x18000570c`
- `KERNEL32!GlobalFree` at `0x18000571a`
- `KERNEL32!GetModuleFileNameW` at `0x180004f4c`
- `KERNEL32!GetModuleFileNameW` at `0x180004f4c`
- `KERNEL32!DefineDosDeviceW` at `0x180005587`
- `KERNEL32!DefineDosDeviceW` at `0x180005587`
- `ADVAPI32!LsaNtStatusToWinError` at `0x1800054e2`
- `ADVAPI32!LsaNtStatusToWinError` at `0x1800054e2`
- `ADVAPI32!LogonUserW` at `0x180004e66`
- `ADVAPI32!LogonUserW` at `0x180004e66`
- `ADVAPI32!EventWrite` at `0x1800052eb`
- `ADVAPI32!EventWrite` at `0x1800052eb`
- `ADVAPI32!RegCloseKey` at `0x180005024`
- `ADVAPI32!RegCloseKey` at `0x180005024`
- `ADVAPI32!RegQueryValueExW` at `0x18000500d`
- `ADVAPI32!RegQueryValueExW` at `0x18000500d`
- `ADVAPI32!RegOpenKeyExW` at `0x180004fd1`
- `ADVAPI32!RegOpenKeyExW` at `0x180004fd1`
- `WSOCK32!__imp_WSAStartup` at `0x180004858`
- `WSOCK32!__imp_WSAStartup` at `0x180004858`
- `WSOCK32!__imp_WSACleanup` at `0x180004b58`
- `WSOCK32!__imp_WSACleanup` at `0x180005758`
- `WSOCK32!__imp_WSACleanup` at `0x180004b58`
- `WSOCK32!__imp_WSACleanup` at `0x180005758`

## string_xrefs

- `0x180004c46`: `nfsnp.dll`
- `0x180004f80`: `mount.exe`
- `0x180004fc3`: `SOFTWARE\Microsoft\ClientForNFS\CurrentVersion\MountUtility\Mount`
- `0x180004fea`: `MountAsAnonymousUser`

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
0x180004720  push    rbp
0x180004722  push    rbx
0x180004723  push    rsi
0x180004724  push    rdi
0x180004725  push    r12
0x180004727  push    r13
0x180004729  push    r14
0x18000472b  push    r15
0x18000472d  lea     rbp, [rsp-16C8h]
0x180004735  mov     eax, 17C8h
0x18000473a  call    _alloca_probe
0x18000473f  sub     rsp, rax
0x180004742  mov     rax, cs:__security_cookie
0x180004749  xor     rax, rsp
0x18000474c  mov     [rbp+1700h+var_50], rax
0x180004753  movups  xmm0, xmmword ptr cs:aNpaddconnectio_1; "NPAddConnection3"
0x18000475a  mov     al, byte ptr cs:aNpaddconnectio_1+10h; ""
0x180004760  mov     r14, r8
0x180004763  mov     rsi, rdx
0x180004766  mov     [rbp+1700h+var_1748], rcx
0x18000476a  xor     edx, edx; Val
0x18000476c  mov     qword ptr [rsp+1800h+cbData], r9
0x180004771  mov     r8d, 208h; Size
0x180004777  mov     [rbp+1700h+var_CD0+10h], al
0x18000477d  lea     rcx, [rbp+1700h+Source]; void *
0x180004784  mov     rdi, r9
0x180004787  movups  xmmword ptr [rbp+1700h+var_CD0], xmm0
0x18000478e  call    memset_0
0x180004793  xor     eax, eax
0x180004795  lea     rcx, [rbp+1700h+var_16B0]; void *
0x180004799  xorps   xmm0, xmm0
0x18000479c  mov     dword ptr [rbp+1700h+var_1768], eax
0x18000479f  xor     edx, edx; Val
0x1800047a1  mov     r8d, 838h; Size
0x1800047a7  movups  [rbp+1700h+var_1778], xmm0
0x1800047ab  call    memset_0
0x1800047b0  xor     edx, edx; Val
0x1800047b2  lea     rcx, [rbp+1700h+var_16F0]; void *
0x1800047b6  lea     r8d, [rdx+40h]; Size
0x1800047ba  call    memset_0
0x1800047bf  xorps   xmm0, xmm0
0x1800047c2  lea     rcx, [rbp+1700h+WSAData]; void *
0x1800047c9  movups  xmmword ptr [rbp+1700h+ObjectAttributes.ObjectName], xmm0
0x1800047cd  xor     eax, eax
0x1800047cf  xor     edx, edx; Val
0x1800047d1  mov     r8d, 198h; Size
0x1800047d7  movups  xmmword ptr [rbp+1700h+ObjectAttributes+1Ch], xmm0
0x1800047db  movups  xmmword ptr [rbp+1700h+IoStatusBlock], xmm0
0x1800047df  movups  xmmword ptr [rbp+1700h+ObjectAttributes.Length], xmm0
0x1800047e3  movups  xmmword ptr [rbp+1700h+DestinationString.Length], xmm0
0x1800047e7  call    memset_0
0x1800047ec  xor     r13d, r13d
0x1800047ef  mov     [rbp+1700h+FileHandle], r13
0x1800047f3  mov     [rsp+1800h+hMem], r13
0x1800047f8  mov     [rsp+1800h+var_179C], r13d
0x1800047fd  mov     dword ptr [rsp+1800h+Data], r13d
0x180004802  mov     rcx, cs:WPP_GLOBAL_Control
0x180004809  lea     r12, WPP_GLOBAL_Control
0x180004810  mov     ebx, [rbp+1700h+dwFlags]
0x180004816  cmp     rcx, r12
0x180004819  jz      short loc_18000483C
0x18000481b  test    byte ptr [rcx+1Ch], 1
0x18000481f  jz      short loc_18000483C
0x180004821  mov     eax, [rsi+4]
0x180004824  lea     r9, [rbp+1700h+var_CD0]
0x18000482b  mov     rcx, [rcx+10h]
0x18000482f  mov     dword ptr [rsp+1800h+phToken], ebx
0x180004833  mov     [rsp+1800h+dwLogonProvider], eax
0x180004837  call    WPP_SF_sDD
0x18000483c  mov     ecx, 101h; wVersionRequested
0x180004841  mov     [rbp+1700h+var_260], r13w
0x180004849  lea     rdx, [rbp+1700h+WSAData]; lpWSAData
0x180004850  mov     [rbp+1700h+var_AAA], r13w
0x180004858  call    cs:__imp_WSAStartup
0x18000485e  test    eax, eax
0x180004860  jz      short loc_18000486C
0x180004862  mov     ebx, 4C6h
0x180004867  jmp     loc_180004B5E
0x18000486c  lea     rcx, [rsp+1800h+Data]
0x180004871  call    NfsNpIsClientRunning
0x180004876  test    eax, eax
0x180004878  js      loc_180005804
0x18000487e  cmp     dword ptr [rsp+1800h+Data], r13d
0x180004883  jz      loc_180005804
0x180004889  xor     edx, edx; Val
0x18000488b  lea     rcx, [rbp+1700h+var_16B0]; void *
0x18000488f  mov     r8d, 838h; Size
0x180004895  mov     r15d, r13d
0x180004898  call    memset_0
0x18000489d  mov     rax, [rsi+10h]
0x1800048a1  test    rax, rax
0x1800048a4  jz      short loc_1800048E8
0x1800048a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800048ad  cmp     rcx, r12
0x1800048b0  jz      short loc_1800048E0
0x1800048b2  test    byte ptr [rcx+1Ch], 8
0x1800048b6  jz      short loc_1800048E0
0x1800048b8  mov     rcx, [rcx+10h]
0x1800048bc  lea     r9, [rbp+1700h+var_CD0]
0x1800048c3  mov     edx, 82h
0x1800048c8  mov     qword ptr [rsp+1800h+dwLogonProvider], rax
0x1800048cd  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x1800048d4  call    WPP_SF_sS
0x1800048d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800048e0  mov     r15d, 1
0x1800048e6  jmp     short loc_1800048EF
0x1800048e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800048ef  cmp     rcx, r12
0x1800048f2  jz      short loc_18000491F
0x1800048f4  test    byte ptr [rcx+1Ch], 8
0x1800048f8  jz      short loc_18000491F
0x1800048fa  mov     rax, [rsi+18h]
0x1800048fe  lea     r9, [rbp+1700h+var_CD0]
0x180004905  mov     rcx, [rcx+10h]
0x180004909  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x180004910  mov     edx, 83h
0x180004915  mov     qword ptr [rsp+1800h+dwLogonProvider], rax
0x18000491a  call    WPP_SF_sS
0x18000491f  mov     r8, [rsi+18h]; Source
0x180004923  lea     rcx, [rbp+1700h+Destination]; Destination
0x18000492a  mov     r9d, 103h; MaxCount
0x180004930  lea     edx, [r9+1]; SizeInWords
0x180004934  call    cs:__imp_wcsncpy_s
0x18000493a  mov     eax, 5Ch ; '\'
0x18000493f  cmp     [rbp+1700h+Destination], ax
0x180004946  jnz     loc_180004A24
0x18000494c  cmp     [rbp+1700h+var_CAE], ax
0x180004953  jz      short loc_18000498B
0x180004955  mov     rcx, cs:WPP_GLOBAL_Control
0x18000495c  cmp     rcx, r12
0x18000495f  jz      short loc_180004981
0x180004961  test    byte ptr [rcx+1Ch], 2
0x180004965  jz      short loc_180004981
0x180004967  mov     rcx, [rcx+10h]
0x18000496b  lea     edx, [rax+28h]
0x18000496e  lea     r9, [rbp+1700h+var_CD0]
0x180004975  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x18000497c  call    WPP_SF_s
0x180004981  mov     ebx, 43h ; 'C'
0x180004986  jmp     loc_180004B58
0x18000498b  lea     rdx, asc_180013F34; "\\/"
0x180004992  lea     rcx, [rbp+1700h+String]; String
0x180004999  call    cs:__imp_wcspbrk
0x18000499f  mov     rcx, rax
0x1800049a2  test    rax, rax
0x1800049a5  jnz     short loc_180004A14
0x1800049a7  test    r15d, r15d
0x1800049aa  jz      short loc_1800049F0
0x1800049ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800049b3  cmp     rcx, r12
0x1800049b6  jz      short loc_1800049DA
0x1800049b8  test    byte ptr [rcx+1Ch], 2
0x1800049bc  jz      short loc_1800049DA
0x1800049be  mov     rcx, [rcx+10h]
0x1800049c2  lea     r9, [rbp+1700h+var_CD0]
0x1800049c9  mov     edx, 85h
0x1800049ce  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x1800049d5  call    WPP_SF_s
0x1800049da  lea     rdx, [rbp+1700h+String]
0x1800049e1  mov     ebx, 43h ; 'C'
0x1800049e6  call    LogInfoEventString
0x1800049eb  jmp     loc_180004B58
0x1800049f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800049f7  cmp     rcx, r12
0x1800049fa  jz      loc_1800057BD
0x180004a00  test    byte ptr [rcx+1Ch], 4
0x180004a04  jz      loc_1800057BD
0x180004a0a  mov     edx, 86h
0x180004a0f  jmp     loc_1800057A6
0x180004a14  lea     r12, [rbp+1700h+String]
0x180004a1b  mov     [rax], r13w
0x180004a1f  jmp     loc_180004AC2
0x180004a24  mov     edx, 3Ah ; ':'; Ch
0x180004a29  lea     rcx, [rbp+1700h+Destination]; Str
0x180004a30  call    cs:__imp_wcschr
0x180004a36  mov     rcx, rax
0x180004a39  test    rax, rax
0x180004a3c  jnz     short loc_180004AA1
0x180004a3e  test    r15d, r15d
0x180004a41  jz      short loc_180004A7D
0x180004a43  mov     rcx, cs:WPP_GLOBAL_Control
0x180004a4a  cmp     rcx, r12
0x180004a4d  jz      short loc_180004A71
0x180004a4f  test    byte ptr [rcx+1Ch], 2
0x180004a53  jz      short loc_180004A71
0x180004a55  mov     edx, 87h
0x180004a5a  mov     rcx, [rcx+10h]
0x180004a5e  lea     r9, [rbp+1700h+var_CD0]
0x180004a65  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x180004a6c  call    WPP_SF_s
0x180004a71  lea     rdx, [rbp+1700h+Destination]
0x180004a78  jmp     loc_1800049E1
0x180004a7d  mov     rcx, cs:WPP_GLOBAL_Control
0x180004a84  cmp     rcx, r12
0x180004a87  jz      loc_1800057BD
0x180004a8d  test    byte ptr [rcx+1Ch], 4
0x180004a91  jz      loc_1800057BD
0x180004a97  mov     edx, 88h
0x180004a9c  jmp     loc_1800057A6
0x180004aa1  mov     [rax], r13w
0x180004aa5  add     rcx, 2
0x180004aa9  mov     eax, 2Fh ; '/'
0x180004aae  cmp     [rcx], ax
0x180004ab1  jnz     loc_180005760
0x180004ab7  lea     r12, [rbp+1700h+Destination]
0x180004abe  mov     [rcx], r13w
0x180004ac2  lea     r13, [rcx+2]
0x180004ac6  mov     [rbp+1700h+var_1760], r12
0x180004aca  mov     [rbp+1700h+var_1740], r13
0x180004ace  mov     rcx, r13
0x180004ad1  jmp     short loc_180004ADC
0x180004ad3  mov     word ptr [rax], 5Ch ; '\'
0x180004ad8  lea     rcx, [rax+2]; Str
0x180004adc  mov     edx, 2Fh ; '/'; Ch
0x180004ae1  call    cs:__imp_wcschr
0x180004ae7  test    rax, rax
0x180004aea  jnz     short loc_180004AD3
0x180004aec  mov     rcx, cs:WPP_GLOBAL_Control
0x180004af3  lea     rax, WPP_GLOBAL_Control
0x180004afa  cmp     rcx, rax
0x180004afd  jz      short loc_180004B24
0x180004aff  test    byte ptr [rcx+1Ch], 8
0x180004b03  jz      short loc_180004B24
0x180004b05  mov     rcx, [rcx+10h]; LoggerHandle
0x180004b09  lea     r9, [rbp+1700h+var_CD0]
0x180004b10  mov     edx, 8Ch
0x180004b15  mov     [rsp+1800h+phToken], r13; __int64
0x180004b1a  mov     qword ptr [rsp+1800h+dwLogonProvider], r12; __int64
0x180004b1f  call    WPP_SF_sSS
0x180004b24  xor     eax, eax
0x180004b26  test    r15d, r15d
0x180004b29  jz      short loc_180004B31
0x180004b2b  mov     r8, [rsi+10h]
0x180004b2f  jmp     short loc_180004B34
0x180004b31  mov     r8, rax
0x180004b34  mov     r9, r12
0x180004b37  mov     qword ptr [rsp+1800h+dwLogonProvider], r13
0x180004b3c  lea     rcx, [rbp+1700h+SourceString]
0x180004b43  call    NfsNpCreateObjectName
0x180004b48  test    eax, eax
0x180004b4a  jns     short loc_180004BB5
0x180004b4c  mov     ebx, 43h ; 'C'
0x180004b51  lea     r12, WPP_GLOBAL_Control
0x180004b58  call    cs:__imp_WSACleanup
0x180004b5e  mov     rcx, cs:WPP_GLOBAL_Control
0x180004b65  cmp     rcx, r12
0x180004b68  jz      short loc_180004B90
0x180004b6a  test    byte ptr [rcx+1Ch], 2
0x180004b6e  jz      short loc_180004B90
0x180004b70  mov     rcx, [rcx+10h]
0x180004b74  lea     r9, [rbp+1700h+var_CD0]
0x180004b7b  mov     edx, 0B0h
0x180004b80  mov     [rsp+1800h+dwLogonProvider], ebx
0x180004b84  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x180004b8b  call    WPP_SF_sd
0x180004b90  mov     eax, ebx
0x180004b92  mov     rcx, [rbp+1700h+var_50]
0x180004b99  xor     rcx, rsp; StackCookie
0x180004b9c  call    __security_check_cookie
0x180004ba1  add     rsp, 17C8h
0x180004ba8  pop     r15
0x180004baa  pop     r14
0x180004bac  pop     r13
0x180004bae  pop     r12
0x180004bb0  pop     rdi
0x180004bb1  pop     rsi
0x180004bb2  pop     rbx
0x180004bb3  pop     rbp
0x180004bb4  retn
0x180004bb5  mov     rcx, cs:WPP_GLOBAL_Control
0x180004bbc  lea     r13, WPP_GLOBAL_Control
0x180004bc3  cmp     rcx, r13
0x180004bc6  jz      short loc_180004BFD
0x180004bc8  test    byte ptr [rcx+1Ch], 8
0x180004bcc  jz      short loc_180004BFD
0x180004bce  mov     rcx, [rcx+10h]
0x180004bd2  lea     rax, [rbp+1700h+SourceString]
0x180004bd9  mov     edx, 8Dh
0x180004bde  mov     qword ptr [rsp+1800h+dwLogonProvider], rax
0x180004be3  lea     r9, [rbp+1700h+var_CD0]
0x180004bea  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x180004bf1  call    WPP_SF_sS
0x180004bf6  mov     rcx, cs:WPP_GLOBAL_Control
0x180004bfd  and     ebx, 8
0x180004c00  mov     [rbp+1700h+dwFlags], ebx
0x180004c06  mov     ebx, 0
0x180004c0b  mov     r12d, ebx
0x180004c0e  setnz   r12b
0x180004c12  cmp     rcx, r13
0x180004c15  jz      short loc_180004C46
0x180004c17  test    byte ptr [rcx+1Ch], 8
0x180004c1b  jz      short loc_180004C46
0x180004c1d  mov     rcx, [rcx+10h]
0x180004c21  lea     r9, [rbp+1700h+var_CD0]
0x180004c28  mov     edx, 8Eh
0x180004c2d  mov     dword ptr [rsp+1800h+phToken], r12d
0x180004c32  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x180004c39  mov     [rsp+1800h+dwLogonProvider], 3
0x180004c41  call    WPP_SF_sdd
0x180004c46  lea     rcx, ModuleName; "nfsnp.dll"
  ... truncated ...
```
