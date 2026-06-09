# DABrowse

- ea: `0x1400030c0`
- end: `0x140003a41`
- name: `DABrowse`
- size: `2433`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x140002908`
- `0x140002c40`
- `0x140002fbc`
- `0x1400030c0`
- `0x140004374`
- `0x140004868`
- `0x140004e64`
- `0x140004f0c`
- `0x14000fa94`
- `0x14000fc9c`
- `0x14000fe8c`
- `0x140018350`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x14000328b`
- `ADVAPI32!RegOpenKeyExW` at `0x140003424`
- `ADVAPI32!RegOpenKeyExW` at `0x14000328b`
- `ADVAPI32!RegOpenKeyExW` at `0x140003424`
- `ADVAPI32!RegCloseKey` at `0x14000354f`
- `ADVAPI32!RegCloseKey` at `0x140003598`
- `ADVAPI32!RegCloseKey` at `0x140003754`
- `ADVAPI32!RegCloseKey` at `0x140003783`
- `ADVAPI32!RegCloseKey` at `0x14000354f`
- `ADVAPI32!RegCloseKey` at `0x140003598`
- `ADVAPI32!RegCloseKey` at `0x140003754`
- `ADVAPI32!RegCloseKey` at `0x140003783`
- `ADVAPI32!RegQueryValueExW` at `0x14000330e`
- `ADVAPI32!RegQueryValueExW` at `0x14000345f`
- `ADVAPI32!RegQueryValueExW` at `0x14000330e`
- `ADVAPI32!RegQueryValueExW` at `0x14000345f`
- `ADVAPI32!RegEnumKeyExW` at `0x140003583`
- `ADVAPI32!RegEnumKeyExW` at `0x140003583`
- `KERNEL32!CreateMutexW` at `0x14000318f`
- `KERNEL32!CreateMutexW` at `0x14000318f`
- `KERNEL32!GlobalAlloc` at `0x1400033db`
- `KERNEL32!GlobalAlloc` at `0x140003701`
- `KERNEL32!GlobalAlloc` at `0x1400033db`
- `KERNEL32!GlobalAlloc` at `0x140003701`
- `KERNEL32!GlobalFree` at `0x140003769`
- `KERNEL32!GlobalFree` at `0x140003769`
- `KERNEL32!GetLastError` at `0x140003198`
- `KERNEL32!GetLastError` at `0x1400031c8`
- `KERNEL32!GetLastError` at `0x14000320d`
- `KERNEL32!GetLastError` at `0x140003295`
- `KERNEL32!GetLastError` at `0x140003318`
- `KERNEL32!GetLastError` at `0x14000361a`
- `KERNEL32!GetLastError` at `0x140003667`
- `KERNEL32!GetLastError` at `0x140003198`
- `KERNEL32!GetLastError` at `0x1400031c8`
- `KERNEL32!GetLastError` at `0x14000320d`
- `KERNEL32!GetLastError` at `0x140003295`
- `KERNEL32!GetLastError` at `0x140003318`
- `KERNEL32!GetLastError` at `0x14000361a`
- `KERNEL32!GetLastError` at `0x140003667`
- `KERNEL32!CreateEventW` at `0x140003160`
- `KERNEL32!CreateEventW` at `0x140003160`
- `KERNEL32!WaitForMultipleObjects` at `0x140003931`
- `KERNEL32!WaitForMultipleObjects` at `0x140003931`
- `KERNEL32!ReleaseMutex` at `0x140003966`
- `KERNEL32!ReleaseMutex` at `0x140003966`
- `KERNEL32!WaitForSingleObject` at `0x140003979`
- `KERNEL32!WaitForSingleObject` at `0x140003988`
- `KERNEL32!WaitForSingleObject` at `0x140003979`
- `KERNEL32!WaitForSingleObject` at `0x140003988`
- `KERNEL32!CloseHandle` at `0x14000379f`
- `KERNEL32!CloseHandle` at `0x1400037bb`
- `KERNEL32!CloseHandle` at `0x14000379f`
- `KERNEL32!CloseHandle` at `0x1400037bb`
- `KERNEL32!SetLastError` at `0x1400031ac`
- `KERNEL32!SetLastError` at `0x1400031ac`
- `msvcrt!_beginthreadex` at `0x1400038a9`
- `msvcrt!_beginthreadex` at `0x1400038a9`
- `msvcrt!wcscpy_s` at `0x1400033fb`
- `msvcrt!wcscpy_s` at `0x1400033fb`

## string_xrefs

- `0x1400032ea`: `SPUpdateMinutes`
- `0x140003458`: `Configure Mode`
- `0x14000364e`: `Configure Mode`
- `0x140003272`: `SYSTEM\CurrentControlSet\Services\NfsClnt\NFS LANS`

## pseudocode

```c
__int64 __fastcall DABrowse(void *a1)
{
  __int64 MutexW; // rdi
  __int64 v2; // rdx
  DWORD LastError; // ebx
  int v4; // eax
  char v5; // bl
  _QWORD *v6; // rcx
  int v7; // edx
  char v8; // al
  char v9; // al
  int v10; // ecx
  DWORD v11; // esi
  DWORD v12; // edx
  __int64 v13; // rax
  __int64 v14; // rbx
  wchar_t *v15; // rax
  wchar_t *v16; // rdi
  const WCHAR *v17; // rdx
  int *v18; // rbx
  int HostsList; // eax
  int v20; // edx
  HGLOBAL v21; // rax
  LSTATUS v22; // eax
  unsigned int v23; // eax
  char v24; // al
  char v25; // al
  _QWORD *v26; // rsi
  _QWORD *v28; // rbx
  DWORD v29; // edi
  _QWORD *v30; // rcx
  int v31; // edx
  __int64 v32; // rax
  _QWORD *v33; // rcx
  _QWORD *i; // rbx
  DWORD cbData; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  HKEY phkResult; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int ThrdAddr; // [rsp+58h] [rbp-A8h] BYREF
  LPSECURITY_ATTRIBUTES lpMutexAttributes; // [rsp+60h] [rbp-A0h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+68h] [rbp-98h] BYREF
  char v41[16]; // [rsp+70h] [rbp-90h] BYREF
  wchar_t Source[264]; // [rsp+80h] [rbp-80h] BYREF

  strcpy(v41, "DABrowse");
  ftLastWriteTime = 0;
  hKey = 0;
  phkResult = 0;
  cbData = 0;
  ThrdAddr = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, &WPP_90b53e51910230494b81f4a05de1546d_Traceguids, v41);
  lpMutexAttributes = 0;
  DaBrowseEvent = CreateEventW(0, 0, 0, 0);
  MutexW = -1;
  if ( (unsigned int)SfuCreateDefaultSecurityAttributes((void **)&lpMutexAttributes, v2) )
  {
    MutexW = (__int64)CreateMutexW(lpMutexAttributes, 1, 0);
    LastError = GetLastError();
    FreeSecurityAttributes(&lpMutexAttributes);
    SetLastError(LastError);
  }
  DaUpdateMutex = (HANDLE)MutexW;
  if ( !DaBrowseEvent )
  {
    LOBYTE(v4) = GetLastError();
    v5 = v4;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_90;
    v7 = 33;
    goto LABEL_10;
  }
  if ( !MutexW )
  {
    LOBYTE(v4) = GetLastError();
    v5 = v4;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_90;
    v7 = 34;
    goto LABEL_10;
  }
  v4 = SafeInitializeCriticalSection(&LanListCS);
  v5 = v4;
  if ( v4 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_90;
    v7 = 35;
LABEL_10:
    WPP_SF_sd(v6[2], v7, (unsigned int)&WPP_90b53e51910230494b81f4a05de1546d_Traceguids, (unsigned int)v41, v4);
    goto LABEL_89;
  }
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Services\\NfsClnt\\NFS LANS", 0, 0x20019u, &hKey) )
  {
    v8 = GetLastError();
    v5 = v8;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_sSd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        36,
        (unsigned int)&WPP_90b53e51910230494b81f4a05de1546d_Traceguids,
        (unsigned int)v41,
        (__int64)L"SYSTEM\\CurrentControlSet\\Services\\NfsClnt\\NFS LANS",
        v8);
      goto LABEL_89;
    }
    goto LABEL_90;
  }
  cbData = 4;
  if ( RegQueryValueExW(hKey, L"SPUpdateMinutes", 0, 0, &UpdateCycle, &cbData) )
  {
    v9 = GetLastError();
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_sSd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        37,
        (unsigned int)&WPP_90b53e51910230494b81f4a05de1546d_Traceguids,
        (unsigned int)v41,
        (__int64)L"SPUpdateMinutes",
        v9);
    v10 = 0;
  }
  else
  {
    v10 = *(_DWORD *)&UpdateCycle;
  }
  if ( (unsigned int)(v10 - 1) > 0x275F )
    v10 = 10080;
  v11 = 0;
  cbData = 261;
  v12 = 0;
  *(_DWORD *)&UpdateCycle = 60000 * v10;
  while ( 1 )
  {
    v22 = RegEnumKeyExW(hKey, v12, Source, &cbData, 0, 0, 0, &ftLastWriteTime);
    v5 = v22;
    if ( v22 )
    {
      RegCloseKey(hKey);
      v16 = (wchar_t *)pLanHead;
      v23 = 0;
      hKey = 0;
      while ( v16 )
      {
        v16 = (wchar_t *)*((_QWORD *)v16 + 6);
        ++v23;
      }
      hObjects = GlobalAlloc(0x40u, 8LL * v23);
      v26 = hObjects;
      if ( !hObjects )
      {
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 60, &WPP_90b53e51910230494b81f4a05de1546d_Traceguids, v41);
LABEL_81:
          v6 = WPP_GLOBAL_Control;
        }
        goto LABEL_82;
      }
      v28 = pLanHead;
      v29 = 0;
      v30 = WPP_GLOBAL_Control;
      while ( v28 )
      {
        if ( *((_DWORD *)v28 + 4) == 1 )
        {
          if ( v30 != &WPP_GLOBAL_Control && (*((_BYTE *)v30 + 28) & 8) != 0 )
          {
            v31 = 61;
LABEL_104:
            WPP_SF_sS(
              v30[2],
              v31,
              (unsigned int)&WPP_90b53e51910230494b81f4a05de1546d_Traceguids,
              (unsigned int)v41,
              v28[1]);
LABEL_114:
            v30 = WPP_GLOBAL_Control;
          }
        }
        else
        {
          v32 = v28[3];
          if ( *(_DWORD *)(v32 + 20) == 2 )
          {
            if ( v30 != &WPP_GLOBAL_Control && (*((_BYTE *)v30 + 28) & 8) != 0 )
            {
              v31 = 62;
              goto LABEL_104;
            }
          }
          else
          {
            *v26 = *(_QWORD *)(v32 + 32);
            if ( _beginthreadex(0, 0, RPCBroadcast, v28, 0, &ThrdAddr) != -1 )
            {
              ++v26;
              ++v29;
              goto LABEL_114;
            }
            v30 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            {
              WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 63, &WPP_90b53e51910230494b81f4a05de1546d_Traceguids, v41);
              goto LABEL_114;
            }
          }
        }
        v28 = (_QWORD *)v28[6];
      }
      if ( v30 != &WPP_GLOBAL_Control && (*((_BYTE *)v30 + 28) & 8) != 0 )
        WPP_SF_sd(v30[2], 64, (unsigned int)&WPP_90b53e51910230494b81f4a05de1546d_Traceguids, (unsigned int)v41, v29);
      if ( v29 )
      {
        WaitForMultipleObjects(v29, (const HANDLE *)hObjects, 1, 0xFFFFFFFF);
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 65, &WPP_90b53e51910230494b81f4a05de1546d_Traceguids, v41);
      }
LABEL_123:
      ReleaseMutex(DaUpdateMutex);
      WaitForSingleObject(DaBrowseEvent, *(DWORD *)&UpdateCycle);
      WaitForSingleObject(DaUpdateMutex, 0xFFFFFFFF);
      v33 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      {
        WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 66, &WPP_90b53e51910230494b81f4a05de1546d_Traceguids, v41);
        v33 = WPP_GLOBAL_Control;
      }
      for ( i = pLanHead; ; i = (_QWORD *)i[6] )
      {
        if ( !i )
        {
          if ( v33 != &WPP_GLOBAL_Control && (*((_BYTE *)v33 + 28) & 8) != 0 )
            WPP_SF_sd(v33[2], 68, (unsigned int)&WPP_90b53e51910230494b81f4a05de1546d_Traceguids, (unsigned int)v41, 0);
          goto LABEL_123;
        }
        if ( *((_DWORD *)i + 4) != 1 )
          break;
        if ( v33 != &WPP_GLOBAL_Control && (*((_BYTE *)v33 + 28) & 8) != 0 )
        {
          WPP_SF_sS(v33[2], 67, (unsigned int)&WPP_90b53e51910230494b81f4a05de1546d_Traceguids, (unsigned int)v41, i[1]);
LABEL_132:
          v33 = WPP_GLOBAL_Control;
          continue;
        }
      }
      RegenerateNames(i);
      goto LABEL_132;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_sS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        38,
        (unsigned int)&WPP_90b53e51910230494b81f4a05de1546d_Traceguids,
        (unsigned int)v41,
        (__int64)Source);
    v13 = -1;
    do
      ++v13;
    while ( Source[v13] );
    v14 = (unsigned int)(v13 + 1);
    v15 = (wchar_t *)GlobalAlloc(0x40u, 2 * v14 + 104);
    v16 = v15;
    if ( !v15 )
      break;
    *((_QWORD *)v15 + 1) = v15 + 52;
    wcscpy_s(v15 + 52, (unsigned int)v14, Source);
    v17 = (const WCHAR *)*((_QWORD *)v16 + 1);
    *((_QWORD *)v16 + 5) = 0;
    *(_DWORD *)v16 = 0;
    if ( RegOpenKeyExW(hKey, v17, 0, 0x20019u, &phkResult) )
    {
      v25 = GetLastError();
      v5 = v25;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_sSd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          40,
          (unsigned int)&WPP_90b53e51910230494b81f4a05de1546d_Traceguids,
          (unsigned int)v41,
          *((_QWORD *)v16 + 1),
          v25);
LABEL_85:
      GlobalFree(v16);
LABEL_86:
      v6 = WPP_GLOBAL_Control;
      goto LABEL_87;
    }
    v18 = (int *)(v16 + 8);
    cbData = 4;
    if ( RegQueryValueExW(phkResult, L"Configure Mode", 0, 0, (LPBYTE)v16 + 16, &cbData) )
    {
      v24 = GetLastError();
      v5 = v24;
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_sSd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          41,
          (unsigned int)&WPP_90b53e51910230494b81f4a05de1546d_Traceguids,
          (unsigned int)v41,
          (__int64)L"Configure Mode",
          v24);
        goto LABEL_81;
      }
LABEL_82:
      if ( phkResult )
      {
        RegCloseKey(phkResult);
        v6 = WPP_GLOBAL_Control;
      }
      if ( !v16 )
        goto LABEL_87;
      goto LABEL_85;
    }
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        42,
        (unsigned int)&WPP_90b53e51910230494b81f4a05de1546d_Traceguids,
        (unsigned int)v41,
        *v18);
      v6 = WPP_GLOBAL_Control;
    }
    HostsList = *v18;
    if ( *v18 )
    {
      if ( HostsList != 1 )
      {
        v5 = 87;
        if ( v6 == &WPP_GLOBAL_Control || (*((_BYTE *)v6 + 28) & 2) == 0 )
          goto LABEL_82;
        v20 = 45;
LABEL_48:
        WPP_SF_sd(
          v6[2],
          v20,
          (unsigned int)&WPP_90b53e51910230494b81f4a05de1546d_Traceguids,
          (unsigned int)v41,
          HostsList);
        goto LABEL_81;
      }
      HostsList = ReadHostsList(v16, phkResult);
      v5 = HostsList;
      if ( HostsList )
      {
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          goto LABEL_82;
        v20 = 44;
        goto LABEL_48;
      }
    }
    else
    {
      HostsList = ReadBroadcastOptions(v16, phkResult);
      v5 = HostsList;
      if ( HostsList )
      {
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          goto LABEL_82;
        v20 = 43;
        goto LABEL_48;
      }
    }
    HostsList = SafeInitializeCriticalSection((LPCRITICAL_SECTION)(v16 + 32));
    v5 = HostsList;
    if ( HostsList )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_82;
      v20 = 46;
      goto LABEL_48;
    }
    v21 = pLanHead;
    if ( pLanHead )
    {
      *((_QWORD *)pLanHead + 7) = v16;
      *((_QWORD *)v16 + 6) = v21;
    }
    ++v11;
    pLanHead = v16;
    cbData = 260;
    RegCloseKey(phkResult);
    v12 = v11;
    phkResult = 0;
  }
  v5 = 8;
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      39,
      (unsigned int)&WPP_90b53e51910230494b81f4a05de1546d_Traceguids,
      (unsigned int)v41,
      8);
    goto LABEL_86;
  }
LABEL_87:
  if ( hKey )
  {
    RegCloseKey(hKey);
LABEL_89:
    v6 = WPP_GLOBAL_Control;
  }
LABEL_90:
  if ( DaUpdateMutex )
  {
    CloseHandle(DaUpdateMutex);
    v6 = WPP_GLOBAL_Control;
  }
  if ( DaBrowseEvent )
  {
    CloseHandle(DaBrowseEvent);
    v6 = WPP_GLOBAL_Control;
  }
  if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 2) != 0 )
    WPP_SF_sd(v6[2], 70, (unsigned int)&WPP_90b53e51910230494b81f4a05de1546d_Traceguids, (unsigned int)v41, v5);
  return 1;
}

```

## disassembly

```asm
0x1400030c0  push    rbp
0x1400030c2  push    rbx
0x1400030c3  push    rsi
0x1400030c4  push    rdi
0x1400030c5  push    r12
0x1400030c7  push    r13
0x1400030c9  push    r14
0x1400030cb  push    r15
0x1400030cd  lea     rbp, [rsp-1A8h]
0x1400030d5  sub     rsp, 2A8h
0x1400030dc  mov     rax, cs:__security_cookie
0x1400030e3  xor     rax, rsp
0x1400030e6  mov     [rbp+1E0h+var_50], rax
0x1400030ed  movsd   xmm0, qword ptr cs:aDabrowse; "DABrowse"
0x1400030f5  xor     r14d, r14d
0x1400030f8  mov     al, byte ptr cs:aDabrowse+8; ""
0x1400030fe  movsd   qword ptr [rsp+2E0h+var_270], xmm0
0x140003104  mov     [rsp+2E0h+var_270+8], al
0x140003108  mov     qword ptr [rsp+2E0h+ftLastWriteTime.dwLowDateTime], r14
0x14000310d  mov     [rsp+2E0h+hKey], r14
0x140003112  mov     [rsp+2E0h+var_290], r14
0x140003117  mov     [rsp+2E0h+cbData], r14d
0x14000311c  mov     [rsp+2E0h+ThrdAddr], r14d
0x140003121  mov     rcx, cs:WPP_GLOBAL_Control
0x140003128  lea     r15, WPP_GLOBAL_Control
0x14000312f  lea     r12, WPP_90b53e51910230494b81f4a05de1546d_Traceguids
0x140003136  cmp     rcx, r15
0x140003139  jz      short loc_140003156
0x14000313b  test    byte ptr [rcx+1Ch], 1
0x14000313f  jz      short loc_140003156
0x140003141  mov     rcx, [rcx+10h]
0x140003145  lea     edx, [r14+20h]
0x140003149  lea     r9, [rsp+2E0h+var_270]
0x14000314e  mov     r8, r12
0x140003151  call    WPP_SF_s
0x140003156  xor     r9d, r9d; lpName
0x140003159  xor     r8d, r8d; bInitialState
0x14000315c  xor     edx, edx; bManualReset
0x14000315e  xor     ecx, ecx; lpEventAttributes
0x140003160  call    cs:__imp_CreateEventW
0x140003166  lea     rcx, [rsp+2E0h+lpMutexAttributes]
0x14000316b  mov     [rsp+2E0h+lpMutexAttributes], r14
0x140003170  mov     cs:DaBrowseEvent, rax
0x140003177  or      rdi, 0FFFFFFFFFFFFFFFFh
0x14000317b  call    SfuCreateDefaultSecurityAttributes
0x140003180  test    eax, eax
0x140003182  jz      short loc_1400031B2
0x140003184  mov     rcx, [rsp+2E0h+lpMutexAttributes]; lpMutexAttributes
0x140003189  lea     edx, [rdi+2]; bInitialOwner
0x14000318c  xor     r8d, r8d; lpName
0x14000318f  call    cs:__imp_CreateMutexW
0x140003195  mov     rdi, rax
0x140003198  call    cs:__imp_GetLastError
0x14000319e  lea     rcx, [rsp+2E0h+lpMutexAttributes]
0x1400031a3  mov     ebx, eax
0x1400031a5  call    FreeSecurityAttributes
0x1400031aa  mov     ecx, ebx; dwErrCode
0x1400031ac  call    cs:__imp_SetLastError
0x1400031b2  cmp     cs:DaBrowseEvent, r14
0x1400031b9  mov     r13d, 2
0x1400031bf  mov     cs:DaUpdateMutex, rdi
0x1400031c6  jnz     short loc_140003208
0x1400031c8  call    cs:__imp_GetLastError
0x1400031ce  mov     ebx, eax
0x1400031d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400031d7  cmp     rcx, r15
0x1400031da  jz      loc_140003790
0x1400031e0  test    [rcx+1Ch], r13b
0x1400031e4  jz      loc_140003790
0x1400031ea  lea     edx, [r13+1Fh]
0x1400031ee  mov     rcx, [rcx+10h]
0x1400031f2  lea     r9, [rsp+2E0h+var_270]
0x1400031f7  mov     r8, r12
0x1400031fa  mov     dword ptr [rsp+2E0h+phkResult], eax
0x1400031fe  call    WPP_SF_sd
0x140003203  jmp     loc_140003789
0x140003208  test    rdi, rdi
0x14000320b  jnz     short loc_140003234
0x14000320d  call    cs:__imp_GetLastError
0x140003213  mov     ebx, eax
0x140003215  mov     rcx, cs:WPP_GLOBAL_Control
0x14000321c  cmp     rcx, r15
0x14000321f  jz      loc_140003790
0x140003225  test    [rcx+1Ch], r13b
0x140003229  jz      loc_140003790
0x14000322f  lea     edx, [rdi+22h]
0x140003232  jmp     short loc_1400031EE
0x140003234  lea     rcx, LanListCS; lpCriticalSection
0x14000323b  call    SafeInitializeCriticalSection
0x140003240  mov     ebx, eax
0x140003242  test    eax, eax
0x140003244  jz      short loc_140003267
0x140003246  mov     rcx, cs:WPP_GLOBAL_Control
0x14000324d  cmp     rcx, r15
0x140003250  jz      loc_140003790
0x140003256  test    [rcx+1Ch], r13b
0x14000325a  jz      loc_140003790
0x140003260  mov     edx, 23h ; '#'
0x140003265  jmp     short loc_1400031EE
0x140003267  lea     rax, [rsp+2E0h+hKey]
0x14000326c  mov     r9d, 20019h; samDesired
0x140003272  lea     rdi, aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Services\\Nf"...
0x140003279  mov     [rsp+2E0h+phkResult], rax; phkResult
0x14000327e  mov     rdx, rdi; lpSubKey
0x140003281  xor     r8d, r8d; ulOptions
0x140003284  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14000328b  call    cs:__imp_RegOpenKeyExW
0x140003291  test    eax, eax
0x140003293  jz      short loc_1400032DB
0x140003295  call    cs:__imp_GetLastError
0x14000329b  mov     ebx, eax
0x14000329d  mov     rcx, cs:WPP_GLOBAL_Control
0x1400032a4  cmp     rcx, r15
0x1400032a7  jz      loc_140003790
0x1400032ad  test    [rcx+1Ch], r13b
0x1400032b1  jz      loc_140003790
0x1400032b7  mov     rcx, [rcx+10h]
0x1400032bb  lea     r9, [rsp+2E0h+var_270]
0x1400032c0  mov     dword ptr [rsp+2E0h+lpcbData], eax
0x1400032c4  mov     edx, 24h ; '$'
0x1400032c9  mov     r8, r12
0x1400032cc  mov     [rsp+2E0h+phkResult], rdi
0x1400032d1  call    WPP_SF_sSd
0x1400032d6  jmp     loc_140003789
0x1400032db  mov     rcx, [rsp+2E0h+hKey]; hKey
0x1400032e0  lea     rax, [rsp+2E0h+cbData]
0x1400032e5  mov     [rsp+2E0h+lpcbData], rax; lpcbData
0x1400032ea  lea     rbx, aSpupdateminute; "SPUpdateMinutes"
0x1400032f1  lea     rax, UpdateCycle
0x1400032f8  mov     [rsp+2E0h+cbData], 4
0x140003300  xor     r9d, r9d; lpType
0x140003303  mov     [rsp+2E0h+phkResult], rax; lpData
0x140003308  xor     r8d, r8d; lpReserved
0x14000330b  mov     rdx, rbx; lpValueName
0x14000330e  call    cs:__imp_RegQueryValueExW
0x140003314  test    eax, eax
0x140003316  jz      short loc_140003354
0x140003318  call    cs:__imp_GetLastError
0x14000331e  mov     rcx, cs:WPP_GLOBAL_Control
0x140003325  cmp     rcx, r15
0x140003328  jz      short loc_14000334F
0x14000332a  test    [rcx+1Ch], r13b
0x14000332e  jz      short loc_14000334F
0x140003330  mov     rcx, [rcx+10h]
0x140003334  lea     r9, [rsp+2E0h+var_270]
0x140003339  mov     dword ptr [rsp+2E0h+lpcbData], eax
0x14000333d  mov     edx, 25h ; '%'
0x140003342  mov     r8, r12
0x140003345  mov     [rsp+2E0h+phkResult], rbx
0x14000334a  call    WPP_SF_sSd
0x14000334f  mov     ecx, r14d
0x140003352  jmp     short loc_14000335A
0x140003354  mov     ecx, cs:UpdateCycle
0x14000335a  lea     eax, [rcx-1]
0x14000335d  cmp     eax, 275Fh
0x140003362  jbe     short loc_140003369
0x140003364  mov     ecx, 2760h
0x140003369  imul    eax, ecx, 0EA60h
0x14000336f  mov     esi, r14d
0x140003372  mov     [rsp+2E0h+cbData], 105h
0x14000337a  xor     edx, edx
0x14000337c  mov     cs:UpdateCycle, eax
0x140003382  jmp     loc_14000355C
0x140003387  mov     rcx, cs:WPP_GLOBAL_Control
0x14000338e  cmp     rcx, r15
0x140003391  jz      short loc_1400033B8
0x140003393  test    byte ptr [rcx+1Ch], 10h
0x140003397  jz      short loc_1400033B8
0x140003399  mov     rcx, [rcx+10h]
0x14000339d  lea     rax, [rbp+1E0h+Source]
0x1400033a1  mov     edx, 26h ; '&'
0x1400033a6  mov     [rsp+2E0h+phkResult], rax
0x1400033ab  lea     r9, [rsp+2E0h+var_270]
0x1400033b0  mov     r8, r12
0x1400033b3  call    WPP_SF_sS
0x1400033b8  lea     rcx, [rbp+1E0h+Source]
0x1400033bc  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400033c0  inc     rax
0x1400033c3  cmp     [rcx+rax*2], r14w
0x1400033c8  jnz     short loc_1400033C0
0x1400033ca  inc     eax
0x1400033cc  mov     ecx, 40h ; '@'; uFlags
0x1400033d1  mov     ebx, eax
0x1400033d3  lea     rdx, ds:68h[rax*2]; dwBytes
0x1400033db  call    cs:__imp_GlobalAlloc
0x1400033e1  mov     rdi, rax
0x1400033e4  test    rax, rax
0x1400033e7  jz      loc_1400036B1
0x1400033ed  lea     rcx, [rax+68h]; Destination
0x1400033f1  mov     edx, ebx; SizeInWords
0x1400033f3  lea     r8, [rbp+1E0h+Source]; Source
0x1400033f7  mov     [rax+8], rcx
0x1400033fb  call    cs:__imp_wcscpy_s
0x140003401  mov     rdx, [rdi+8]; lpSubKey
0x140003405  lea     rax, [rsp+2E0h+var_290]
0x14000340a  mov     [rdi+28h], r14
0x14000340e  mov     r9d, 20019h; samDesired
0x140003414  mov     [rdi], r14d
0x140003417  xor     r8d, r8d; ulOptions
0x14000341a  mov     rcx, [rsp+2E0h+hKey]; hKey
0x14000341f  mov     [rsp+2E0h+phkResult], rax; phkResult
0x140003424  call    cs:__imp_RegOpenKeyExW
0x14000342a  test    eax, eax
0x14000342c  jnz     loc_140003667
0x140003432  mov     rcx, [rsp+2E0h+var_290]; hKey
0x140003437  lea     rax, [rsp+2E0h+cbData]
0x14000343c  mov     [rsp+2E0h+lpcbData], rax; lpcbData
0x140003441  lea     rbx, [rdi+10h]
0x140003445  xor     r9d, r9d; lpType
0x140003448  mov     [rsp+2E0h+phkResult], rbx; lpData
0x14000344d  xor     r8d, r8d; lpReserved
0x140003450  mov     [rsp+2E0h+cbData], 4
0x140003458  lea     rdx, aConfigureMode; "Configure Mode"
0x14000345f  call    cs:__imp_RegQueryValueExW
0x140003465  test    eax, eax
0x140003467  jnz     loc_14000361A
0x14000346d  mov     rcx, cs:WPP_GLOBAL_Control
0x140003474  cmp     rcx, r15
0x140003477  jz      short loc_1400034A0
0x140003479  test    byte ptr [rcx+1Ch], 8
0x14000347d  jz      short loc_1400034A0
0x14000347f  mov     rcx, [rcx+10h]
0x140003483  lea     edx, [rax+2Ah]
0x140003486  mov     eax, [rbx]
0x140003488  lea     r9, [rsp+2E0h+var_270]
0x14000348d  mov     r8, r12
0x140003490  mov     dword ptr [rsp+2E0h+phkResult], eax
0x140003494  call    WPP_SF_sd
0x140003499  mov     rcx, cs:WPP_GLOBAL_Control
0x1400034a0  mov     eax, [rbx]
0x1400034a2  test    eax, eax
0x1400034a4  jnz     short loc_1400034F2
0x1400034a6  mov     rdx, [rsp+2E0h+var_290]
0x1400034ab  mov     rcx, rdi
0x1400034ae  call    ReadBroadcastOptions
0x1400034b3  mov     ebx, eax
0x1400034b5  test    eax, eax
0x1400034b7  jz      short loc_140003512
0x1400034b9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400034c0  cmp     rcx, r15
0x1400034c3  jz      loc_140003747
0x1400034c9  test    [rcx+1Ch], r13b
0x1400034cd  jz      loc_140003747
0x1400034d3  mov     edx, 2Bh ; '+'
0x1400034d8  mov     rcx, [rcx+10h]
0x1400034dc  lea     r9, [rsp+2E0h+var_270]
0x1400034e1  mov     r8, r12
0x1400034e4  mov     dword ptr [rsp+2E0h+phkResult], eax
0x1400034e8  call    WPP_SF_sd
0x1400034ed  jmp     loc_140003740
0x1400034f2  cmp     eax, 1
0x1400034f5  jnz     loc_1400035FA
0x1400034fb  mov     rdx, [rsp+2E0h+var_290]
0x140003500  mov     rcx, rdi
0x140003503  call    ReadHostsList
0x140003508  mov     ebx, eax
0x14000350a  test    eax, eax
0x14000350c  jnz     loc_1400035D6
0x140003512  lea     rcx, [rdi+40h]; lpCriticalSection
0x140003516  call    SafeInitializeCriticalSection
0x14000351b  mov     ebx, eax
0x14000351d  test    eax, eax
0x14000351f  jnz     loc_1400035B2
0x140003525  mov     rax, cs:pLanHead
0x14000352c  test    rax, rax
0x14000352f  jz      short loc_140003539
0x140003531  mov     [rax+38h], rdi
0x140003535  mov     [rdi+30h], rax
0x140003539  mov     rcx, [rsp+2E0h+var_290]; hKey
0x14000353e  inc     esi
0x140003540  mov     cs:pLanHead, rdi
0x140003547  mov     [rsp+2E0h+cbData], 104h
0x14000354f  call    cs:__imp_RegCloseKey
0x140003555  mov     edx, esi; dwIndex
0x140003557  mov     [rsp+2E0h+var_290], r14
0x14000355c  mov     rcx, [rsp+2E0h+hKey]; hKey
0x140003561  lea     rax, [rsp+2E0h+ftLastWriteTime]
0x140003566  mov     [rsp+2E0h+lpftLastWriteTime], rax; lpftLastWriteTime
0x14000356b  lea     r9, [rsp+2E0h+cbData]; lpcchName
0x140003570  mov     [rsp+2E0h+lpcchClass], r14; lpcchClass
0x140003575  lea     r8, [rbp+1E0h+Source]; lpName
0x140003579  mov     [rsp+2E0h+lpcbData], r14; lpClass
0x14000357e  mov     [rsp+2E0h+phkResult], r14; lpReserved
0x140003583  call    cs:__imp_RegEnumKeyExW
0x140003589  mov     ebx, eax
0x14000358b  test    eax, eax
0x14000358d  jz      loc_140003387
0x140003593  mov     rcx, [rsp+2E0h+hKey]; hKey
0x140003598  call    cs:__imp_RegCloseKey
0x14000359e  mov     rdi, cs:pLanHead
0x1400035a5  mov     eax, r14d
0x1400035a8  mov     [rsp+2E0h+hKey], r14
0x1400035ad  jmp     loc_1400036F3
0x1400035b2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400035b9  cmp     rcx, r15
0x1400035bc  jz      loc_140003747
0x1400035c2  test    [rcx+1Ch], r13b
0x1400035c6  jz      loc_140003747
0x1400035cc  mov     edx, 2Eh ; '.'
0x1400035d1  jmp     loc_1400034D8
  ... truncated ...
```
