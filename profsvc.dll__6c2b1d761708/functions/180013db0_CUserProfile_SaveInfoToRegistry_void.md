# CUserProfile::SaveInfoToRegistry(void)

- ea: `0x180013db0`
- end: `0x1800146e9`
- name: `?SaveInfoToRegistry@CUserProfile@@IEAAJXZ`
- size: `2361`
- prototype: `__int64 __fastcall(CUserProfile *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18002ef18`

## callees

- `0x1800053c0`
- `0x18000d2c0`
- `0x18000e1a0`
- `0x180012508`
- `0x180013db0`
- `0x1800146f0`
- `0x180014b4c`
- `0x180022440`
- `0x18002df48`
- `0x180030ad0`
- `0x180031060`
- `0x180040bcc`
- `0x180051820`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800140a8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180014114`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800140a8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180014114`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014094`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014100`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014094`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014100`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180013e16`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180013e16`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180014083`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800140ef`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180014228`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180014421`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180014467`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180014083`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800140ef`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180014228`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180014421`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180014467`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180013e55`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180013ea8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180013f1e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180013f8b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180014044`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180014198`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800141dd`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800142c1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180014309`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180014366`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800143aa`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180013e55`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180013ea8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180013f1e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180013f8b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180014044`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180014198`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800141dd`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800142c1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180014309`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180014366`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800143aa`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180013ff9`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180013ff9`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180013f5e`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180013f5e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180014161`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180014161`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013fc2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014213`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014264`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013fc2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014213`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014264`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180013f46`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180013f46`

## string_xrefs

- `0x180013fa6`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x180014069`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x1800140c6`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x180014407`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x18001444b`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x180014491`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x1800144fd`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x180014533`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x180014587`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x1800145a3`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x1800145cb`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x18001461b`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x180014638`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x180014655`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x180014672`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x18001468f`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x1800146ac`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x1800142b6`: `ProfileAttemptedProfileDownloadTimeLow`
- `0x1800142fe`: `ProfileAttemptedProfileDownloadTimeHigh`

## pseudocode

```c
__int64 __fastcall CUserProfile::SaveInfoToRegistry(CUserProfile *this)
{
  int ProfileListKeyNameFromSid; // eax
  unsigned int v3; // edi
  WCHAR *v4; // rsi
  unsigned int v5; // eax
  LSTATUS v6; // eax
  signed int v7; // edi
  LSTATUS v8; // eax
  const BYTE *v9; // rcx
  unsigned __int64 v10; // rax
  int v11; // eax
  const char *v12; // r9
  DWORD cbData; // eax
  unsigned int v14; // eax
  __int64 v15; // r9
  unsigned int LastError; // ebx
  HKEY v17; // rcx
  LSTATUS v18; // eax
  unsigned int v19; // edi
  HANDLE ProcessHeap; // rax
  HANDLE v22; // rax
  int v23; // eax
  bool v24; // sf
  int v25; // eax
  bool v26; // sf
  int v27; // eax
  bool v28; // sf
  int v29; // eax
  bool v30; // sf
  int v31; // eax
  bool v32; // sf
  int v33; // eax
  bool v34; // sf
  __int64 v35; // rdx
  HKEY v36; // rcx
  unsigned int v37; // ebx
  int v38; // eax
  const unsigned __int16 *v39; // r8
  int v40; // eax
  int v41; // eax
  int phkResult; // [rsp+20h] [rbp-40h]
  unsigned int phkResulta; // [rsp+20h] [rbp-40h]
  int phkResultb; // [rsp+20h] [rbp-40h]
  int phkResultc; // [rsp+20h] [rbp-40h]
  unsigned int phkResultd; // [rsp+20h] [rbp-40h]
  int phkResulte; // [rsp+20h] [rbp-40h]
  int phkResultf; // [rsp+20h] [rbp-40h]
  int phkResultg; // [rsp+20h] [rbp-40h]
  int phkResulth; // [rsp+20h] [rbp-40h]
  int phkResulti; // [rsp+20h] [rbp-40h]
  int phkResultj; // [rsp+20h] [rbp-40h]
  unsigned __int16 *v53; // [rsp+30h] [rbp-30h] BYREF
  __int64 v54; // [rsp+38h] [rbp-28h]
  __int64 v55; // [rsp+40h] [rbp-20h]
  LPCWSTR lpSubKey[3]; // [rsp+48h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]
  DWORD Data; // [rsp+90h] [rbp+30h] BYREF
  HKEY hKey; // [rsp+98h] [rbp+38h] BYREF
  PSID Sid; // [rsp+A0h] [rbp+40h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+A8h] [rbp+48h] BYREF

  lpSubKey[0] = 0;
  lpSubKey[1] = (LPCWSTR)-1LL;
  lpSubKey[2] = (LPCWSTR)-1LL;
  ProfileListKeyNameFromSid = GetProfileListKeyNameFromSid(*((LPCWCH *)this + 6), (unsigned __int16 **)lpSubKey, 0);
  v3 = ProfileListKeyNameFromSid;
  if ( ProfileListKeyNameFromSid < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x61A,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
      (const char *)(unsigned int)ProfileListKeyNameFromSid,
      phkResult);
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(lpSubKey);
    return v3;
  }
  hKey = 0;
  v4 = (WCHAR *)lpSubKey[0];
  v5 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey[0], 0, 0x2001Fu, &hKey);
  if ( !v5 )
  {
    Data = *((_DWORD *)this + 2);
    v6 = RegSetValueExW(hKey, L"Flags", 0, 4u, (const BYTE *)&Data, 4u);
    v7 = v6;
    if ( v6 > 0 )
      v7 = (unsigned __int16)v6 | 0x80070000;
    if ( v7 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x620,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
        (const char *)(unsigned int)v7,
        phkResultb);
      v36 = hKey;
      if ( !hKey )
        goto LABEL_77;
    }
    else
    {
      if ( (*((_BYTE *)this + 8) & 4) == 0 )
      {
        Data = 1;
        v18 = RegSetValueExW(hKey, L"FullProfile", 0, 4u, (const BYTE *)&Data, 4u);
        v19 = v18;
        if ( v18 > 0 )
          v19 = (unsigned __int16)v18 | 0x80070000;
        if ( (v19 & 0x80000000) != 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x625,
            (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
            (const char *)v19,
            phkResulte);
          if ( hKey )
            RegCloseKey(hKey);
          if ( v4 )
          {
            ProcessHeap = GetProcessHeap();
            HeapFree(ProcessHeap, 0, v4);
          }
          return v19;
        }
      }
      Data = *((_DWORD *)this + 3);
      v8 = RegSetValueExW(hKey, L"State", 0, 4u, (const BYTE *)&Data, 4u);
      v7 = v8;
      if ( v8 > 0 )
        v7 = (unsigned __int16)v8 | 0x80070000;
      if ( v7 >= 0 )
      {
        v9 = (const BYTE *)*((_QWORD *)this + 13);
        if ( !v9 || !*(_WORD *)v9 )
        {
          RegDeleteValueW(hKey, L"CentralProfile");
          goto LABEL_18;
        }
        v10 = -1;
        do
          ++v10;
        while ( *(_WORD *)&v9[2 * v10] );
        if ( v10 >= 0x7FFFFFFF )
        {
          LOWORD(v11) = 534;
        }
        else
        {
          v11 = RegSetValueExW(hKey, L"CentralProfile", 0, 1u, v9, 2 * v10 + 2);
          if ( v11 <= 0 )
            goto LABEL_16;
        }
        v11 = (unsigned __int16)v11 | 0x80070000;
LABEL_16:
        if ( v11 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x630,
            (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
            (const char *)(unsigned int)v11,
            phkResultc);
LABEL_18:
        Sid = 0;
        if ( !ConvertStringSidToSidW(*((LPCWSTR *)this + 6), &Sid) )
        {
          LastError = wil::details::in1diag3::Return_GetLastError(
                        retaddr,
                        (void *)0x63C,
                        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
                        v12);
          if ( Sid )
            LocalFree(Sid);
          v17 = hKey;
          if ( !hKey )
            goto LABEL_37;
LABEL_36:
          RegCloseKey(v17);
LABEL_37:
          if ( v4 )
          {
            v22 = GetProcessHeap();
            HeapFree(v22, 0, v4);
          }
          return LastError;
        }
        cbData = GetLengthSid(Sid);
        v14 = RegSetValueExW(hKey, L"Sid", 0, 3u, (const BYTE *)Sid, cbData);
        if ( v14 )
        {
          LastError = wil::details::in1diag3::Return_Win32(
                        retaddr,
                        (void *)0x63D,
                        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
                        (const char *)v14,
                        phkResultd);
          if ( Sid )
            LocalFree(Sid);
          v17 = hKey;
          if ( !hKey )
            goto LABEL_37;
          goto LABEL_36;
        }
        v53 = 0;
        v54 = 0;
        v55 = 0;
        LOBYTE(v15) = 1;
        if ( (int)Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_InitializeFromRegistry(
                    &v53,
                    hKey,
                    L"Guid",
                    v15) < 0 )
        {
          Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&v53);
          v54 = -1;
          v55 = -1;
          if ( (int)GetUserGuid(*((void **)this + 3), &v53) >= 0 && v53 && *v53 )
          {
            v38 = SHRegSetString(hKey, 0, L"Guid", v53);
            if ( v38 < 0 )
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x645,
                (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
                (const char *)(unsigned int)v38,
                phkResultd);
            v40 = SetOldSidString(*((void **)this + 3), *((const unsigned __int16 **)this + 6), v39);
            if ( v40 < 0 )
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x648,
                (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
                (const char *)(unsigned int)v40,
                phkResultd);
          }
        }
        SystemTimeAsFileTime = 0;
        GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
        Data = SystemTimeAsFileTime.dwLowDateTime;
        v23 = RegSetValueExW(hKey, L"LocalProfileLoadTimeLow", 0, 4u, (const BYTE *)&Data, 4u);
        v24 = v23 < 0;
        if ( v23 > 0 )
        {
          v23 = (unsigned __int16)v23 | 0x80070000;
          v24 = v23 < 0;
        }
        if ( v24 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x64F,
            (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
            (const char *)(unsigned int)v23,
            phkResultf);
        Data = SystemTimeAsFileTime.dwHighDateTime;
        v25 = RegSetValueExW(hKey, L"LocalProfileLoadTimeHigh", 0, 4u, (const BYTE *)&Data, 4u);
        v26 = v25 < 0;
        if ( v25 > 0 )
        {
          v25 = (unsigned __int16)v25 | 0x80070000;
          v26 = v25 < 0;
        }
        if ( v26 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x650,
            (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
            (const char *)(unsigned int)v25,
            phkResultg);
        if ( (*((_BYTE *)this + 8) & 4) == 0 )
        {
          Data = *((_DWORD *)this + 64);
          v27 = RegSetValueExW(hKey, L"ProfileAttemptedProfileDownloadTimeLow", 0, 4u, (const BYTE *)&Data, 4u);
          v28 = v27 < 0;
          if ( v27 > 0 )
          {
            v27 = (unsigned __int16)v27 | 0x80070000;
            v28 = v27 < 0;
          }
          if ( v28 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x654,
              (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
              (const char *)(unsigned int)v27,
              phkResulth);
          Data = *((_DWORD *)this + 65);
          v29 = RegSetValueExW(hKey, L"ProfileAttemptedProfileDownloadTimeHigh", 0, 4u, (const BYTE *)&Data, 4u);
          v30 = v29 < 0;
          if ( v29 > 0 )
          {
            v29 = (unsigned __int16)v29 | 0x80070000;
            v30 = v29 < 0;
          }
          if ( v30 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x655,
              (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
              (const char *)(unsigned int)v29,
              phkResulti);
          if ( *((_DWORD *)this + 61) && *((_DWORD *)this + 60) )
          {
            Data = *((_DWORD *)this + 60);
            v31 = RegSetValueExW(hKey, L"ProfileLoadTimeLow", 0, 4u, (const BYTE *)&Data, 4u);
            v32 = v31 < 0;
            if ( v31 > 0 )
            {
              v31 = (unsigned __int16)v31 | 0x80070000;
              v32 = v31 < 0;
            }
            if ( v32 )
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x65C,
                (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
                (const char *)(unsigned int)v31,
                phkResultj);
            Data = *((_DWORD *)this + 61);
            v33 = RegSetValueExW(hKey, L"ProfileLoadTimeHigh", 0, 4u, (const BYTE *)&Data, 4u);
            v34 = v33 < 0;
            if ( v33 > 0 )
            {
              v33 = (unsigned __int16)v33 | 0x80070000;
              v34 = v33 < 0;
            }
            if ( !v34 )
              goto LABEL_50;
            v35 = 1629;
          }
          else
          {
            Data = 0;
            if ( SHRegGetDWORD(hKey, 0, L"ProfileLoadTimeLow", &Data) < 0 )
            {
              v41 = SHRegSetDWORD(hKey, 0, L"ProfileLoadTimeLow", 0);
              if ( v41 < 0 )
                wil::details::in1diag3::_Log_Hr(
                  retaddr,
                  (void *)0x66C,
                  (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
                  (const char *)(unsigned int)v41,
                  phkResulti);
            }
            if ( SHRegGetDWORD(hKey, 0, L"ProfileLoadTimeHigh", &Data) >= 0 )
              goto LABEL_50;
            v33 = SHRegSetDWORD(hKey, 0, L"ProfileLoadTimeHigh", 0);
            if ( v33 >= 0 )
              goto LABEL_50;
            v35 = 1649;
          }
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)v35,
            (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
            (const char *)(unsigned int)v33,
            phkResulti);
        }
LABEL_50:
        Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&v53);
        if ( Sid )
          LocalFree(Sid);
        if ( hKey )
          RegCloseKey(hKey);
        Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(lpSubKey);
        return 0;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x629,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
        (const char *)(unsigned int)v7,
        phkResultc);
      v36 = hKey;
      if ( !hKey )
      {
LABEL_77:
        Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(lpSubKey);
        return (unsigned int)v7;
      }
    }
    RegCloseKey(v36);
    goto LABEL_77;
  }
  v37 = wil::details::in1diag3::Return_Win32(
          retaddr,
          (void *)0x61D,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
          (const char *)v5,
          phkResulta);
  if ( hKey )
    RegCloseKey(hKey);
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(lpSubKey);
  return v37;
}

```

## disassembly

```asm
0x180013db0  push    rbp
0x180013db2  push    rbx
0x180013db3  push    rsi
0x180013db4  push    rdi
0x180013db5  push    r14
0x180013db7  mov     rbp, rsp
0x180013dba  sub     rsp, 60h
0x180013dbe  mov     rbx, rcx
0x180013dc1  xor     r14d, r14d
0x180013dc4  mov     [rbp+lpSubKey], r14
0x180013dc8  mov     [rbp+var_10], 0FFFFFFFFFFFFFFFFh
0x180013dd0  mov     [rbp+var_8], 0FFFFFFFFFFFFFFFFh
0x180013dd8  xor     r8d, r8d; int *
0x180013ddb  lea     rdx, [rbp+lpSubKey]; unsigned __int16 **
0x180013ddf  mov     rcx, [rcx+30h]; lpString1
0x180013de3  call    ?GetProfileListKeyNameFromSid@@YAJPEBGPEAPEAGPEAH@Z; GetProfileListKeyNameFromSid(ushort const *,ushort * *,int *)
0x180013de8  mov     edi, eax
0x180013dea  test    eax, eax
0x180013dec  js      loc_18001459C
0x180013df2  mov     [rbp+hKey], r14
0x180013df6  lea     rax, [rbp+hKey]
0x180013dfa  mov     [rsp+60h+phkResult], rax; unsigned int
0x180013dff  mov     r9d, 2001Fh; samDesired
0x180013e05  xor     r8d, r8d; ulOptions
0x180013e08  mov     rsi, [rbp+lpSubKey]
0x180013e0c  mov     rdx, rsi; lpSubKey
0x180013e0f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180013e16  call    cs:__imp_RegOpenKeyExW
0x180013e1d  nop     dword ptr [rax+rax+00h]
0x180013e22  test    eax, eax
0x180013e24  jnz     loc_180014444
0x180013e2a  mov     eax, [rbx+8]
0x180013e2d  mov     [rbp+Data], eax
0x180013e30  mov     [rsp+60h+cbData], 4; cbData
0x180013e38  lea     rax, [rbp+Data]
0x180013e3c  mov     [rsp+60h+phkResult], rax; int
0x180013e41  mov     r9d, 4; dwType
0x180013e47  xor     r8d, r8d; Reserved
0x180013e4a  lea     rdx, Value; "Flags"
0x180013e51  mov     rcx, [rbp+hKey]; hKey
0x180013e55  call    cs:__imp_RegSetValueExW
0x180013e5c  nop     dword ptr [rax+rax+00h]
0x180013e61  mov     edi, eax
0x180013e63  test    eax, eax
0x180013e65  jg      loc_180013FE0
0x180013e6b  test    edi, edi
0x180013e6d  js      loc_18001448A
0x180013e73  test    byte ptr [rbx+8], 4
0x180013e77  jz      loc_180014018
0x180013e7d  mov     eax, [rbx+0Ch]
0x180013e80  mov     [rbp+Data], eax
0x180013e83  mov     [rsp+60h+cbData], 4; cbData
0x180013e8b  lea     rax, [rbp+Data]
0x180013e8f  mov     [rsp+60h+phkResult], rax; int
0x180013e94  mov     r9d, 4; dwType
0x180013e9a  xor     r8d, r8d; Reserved
0x180013e9d  lea     rdx, aState; "State"
0x180013ea4  mov     rcx, [rbp+hKey]; hKey
0x180013ea8  call    cs:__imp_RegSetValueExW
0x180013eaf  nop     dword ptr [rax+rax+00h]
0x180013eb4  mov     edi, eax
0x180013eb6  test    eax, eax
0x180013eb8  jg      loc_18001400A
0x180013ebe  test    edi, edi
0x180013ec0  js      loc_180014400
0x180013ec6  mov     rcx, [rbx+68h]
0x180013eca  test    rcx, rcx
0x180013ecd  jz      loc_180013FEE
0x180013ed3  cmp     [rcx], r14w
0x180013ed7  jz      loc_180013FEE
0x180013edd  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180013ee4  inc     rax
0x180013ee7  cmp     [rcx+rax*2], r14w
0x180013eec  jnz     short loc_180013EE4
0x180013eee  cmp     rax, 7FFFFFFFh
0x180013ef4  jnb     loc_180014244
0x180013efa  lea     eax, ds:2[rax*2]
0x180013f01  mov     [rsp+60h+cbData], eax; cbData
0x180013f05  mov     [rsp+60h+phkResult], rcx; int
0x180013f0a  mov     r9d, 1; dwType
0x180013f10  xor     r8d, r8d; Reserved
0x180013f13  lea     rdx, aCentralprofile; "CentralProfile"
0x180013f1a  mov     rcx, [rbp+hKey]; hKey
0x180013f1e  call    cs:__imp_RegSetValueExW
0x180013f25  nop     dword ptr [rax+rax+00h]
0x180013f2a  test    eax, eax
0x180013f2c  jg      loc_180014249
0x180013f32  test    eax, eax
0x180013f34  js      loc_1800145C4
0x180013f3a  mov     [rbp+Sid], r14
0x180013f3e  lea     rdx, [rbp+Sid]; Sid
0x180013f42  mov     rcx, [rbx+30h]; StringSid
0x180013f46  call    cs:__imp_ConvertStringSidToSidW
0x180013f4d  nop     dword ptr [rax+rax+00h]
0x180013f52  test    eax, eax
0x180013f54  jz      loc_1800140C2
0x180013f5a  mov     rcx, [rbp+Sid]; pSid
0x180013f5e  call    cs:__imp_GetLengthSid
0x180013f65  nop     dword ptr [rax+rax+00h]
0x180013f6a  mov     rdx, [rbp+Sid]
0x180013f6e  mov     [rsp+60h+cbData], eax; cbData
0x180013f72  mov     [rsp+60h+phkResult], rdx; int
0x180013f77  mov     r9d, 3; dwType
0x180013f7d  xor     r8d, r8d; Reserved
0x180013f80  lea     rdx, aSid; "Sid"
0x180013f87  mov     rcx, [rbp+hKey]; hKey
0x180013f8b  call    cs:__imp_RegSetValueExW
0x180013f92  nop     dword ptr [rax+rax+00h]
0x180013f97  test    eax, eax
0x180013f99  jz      loc_18001412E
0x180013f9f  mov     rcx, [rbp+28h]; this
0x180013fa3  mov     r9d, eax; char *
0x180013fa6  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x180013fad  mov     edx, 63Dh; void *
0x180013fb2  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180013fb7  mov     ebx, eax
0x180013fb9  mov     rcx, [rbp+Sid]; hMem
0x180013fbd  test    rcx, rcx
0x180013fc0  jz      short loc_180013FCE
0x180013fc2  call    cs:__imp_LocalFree
0x180013fc9  nop     dword ptr [rax+rax+00h]
0x180013fce  mov     rcx, [rbp+hKey]
0x180013fd2  test    rcx, rcx
0x180013fd5  jz      loc_1800140FB
0x180013fdb  jmp     loc_1800140EF
0x180013fe0  movzx   edi, ax
0x180013fe3  or      edi, 80070000h
0x180013fe9  jmp     loc_180013E6B
0x180013fee  lea     rdx, aCentralprofile; "CentralProfile"
0x180013ff5  mov     rcx, [rbp+hKey]; hKey
0x180013ff9  call    cs:__imp_RegDeleteValueW
0x180014000  nop     dword ptr [rax+rax+00h]
0x180014005  jmp     loc_180013F3A
0x18001400a  movzx   edi, ax
0x18001400d  or      edi, 80070000h
0x180014013  jmp     loc_180013EBE
0x180014018  mov     [rbp+Data], 1
0x18001401f  mov     [rsp+60h+cbData], 4; cbData
0x180014027  lea     rax, [rbp+Data]
0x18001402b  mov     [rsp+60h+phkResult], rax; int
0x180014030  mov     r9d, 4; dwType
0x180014036  xor     r8d, r8d; Reserved
0x180014039  lea     rdx, aFullprofile; "FullProfile"
0x180014040  mov     rcx, [rbp+hKey]; hKey
0x180014044  call    cs:__imp_RegSetValueExW
0x18001404b  nop     dword ptr [rax+rax+00h]
0x180014050  mov     edi, eax
0x180014052  test    eax, eax
0x180014054  jg      loc_180014256
0x18001405a  test    edi, edi
0x18001405c  jns     loc_180013E7D
0x180014062  mov     rcx, [rbp+28h]; this
0x180014066  mov     r9d, edi; char *
0x180014069  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x180014070  mov     edx, 625h; void *
0x180014075  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001407a  mov     rcx, [rbp+hKey]; hKey
0x18001407e  test    rcx, rcx
0x180014081  jz      short loc_18001408F
0x180014083  call    cs:__imp_RegCloseKey
0x18001408a  nop     dword ptr [rax+rax+00h]
0x18001408f  test    rsi, rsi
0x180014092  jz      short loc_1800140B4
0x180014094  call    cs:__imp_GetProcessHeap
0x18001409b  nop     dword ptr [rax+rax+00h]
0x1800140a0  mov     rcx, rax; hHeap
0x1800140a3  mov     r8, rsi; lpMem
0x1800140a6  xor     edx, edx; dwFlags
0x1800140a8  call    cs:__imp_HeapFree
0x1800140af  nop     dword ptr [rax+rax+00h]
0x1800140b4  mov     eax, edi
0x1800140b6  add     rsp, 60h
0x1800140ba  pop     r14
0x1800140bc  pop     rdi
0x1800140bd  pop     rsi
0x1800140be  pop     rbx
0x1800140bf  pop     rbp
0x1800140c0  retn
0x1800140c2  mov     rcx, [rbp+28h]; this
0x1800140c6  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800140cd  mov     edx, 63Ch; void *
0x1800140d2  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800140d7  mov     ebx, eax
0x1800140d9  mov     rcx, [rbp+Sid]; hMem
0x1800140dd  test    rcx, rcx
0x1800140e0  jnz     loc_180014264
0x1800140e6  mov     rcx, [rbp+hKey]; hKey
0x1800140ea  test    rcx, rcx
0x1800140ed  jz      short loc_1800140FB
0x1800140ef  call    cs:__imp_RegCloseKey
0x1800140f6  nop     dword ptr [rax+rax+00h]
0x1800140fb  test    rsi, rsi
0x1800140fe  jz      short loc_180014120
0x180014100  call    cs:__imp_GetProcessHeap
0x180014107  nop     dword ptr [rax+rax+00h]
0x18001410c  mov     rcx, rax; hHeap
0x18001410f  mov     r8, rsi; lpMem
0x180014112  xor     edx, edx; dwFlags
0x180014114  call    cs:__imp_HeapFree
0x18001411b  nop     dword ptr [rax+rax+00h]
0x180014120  mov     eax, ebx
0x180014122  add     rsp, 60h
0x180014126  pop     r14
0x180014128  pop     rdi
0x180014129  pop     rsi
0x18001412a  pop     rbx
0x18001412b  pop     rbp
0x18001412c  retn
0x18001412e  mov     [rbp+var_30], r14
0x180014132  mov     [rbp+var_28], r14
0x180014136  mov     [rbp+var_20], r14
0x18001413a  mov     r9b, 1
0x18001413d  lea     r8, aGuid; "Guid"
0x180014144  mov     rdx, [rbp+hKey]
0x180014148  lea     rcx, [rbp+var_30]
0x18001414c  call    ?_InitializeFromRegistry@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEAUHKEY__@@PEBG_N@Z; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_InitializeFromRegistry(HKEY__ *,ushort const *,bool)
0x180014151  test    eax, eax
0x180014153  js      loc_1800145E1
0x180014159  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], r14
0x18001415d  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180014161  call    cs:__imp_GetSystemTimeAsFileTime
0x180014168  nop     dword ptr [rax+rax+00h]
0x18001416d  mov     eax, [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180014170  mov     [rbp+Data], eax
0x180014173  mov     [rsp+60h+cbData], 4; cbData
0x18001417b  lea     rax, [rbp+Data]
0x18001417f  mov     [rsp+60h+phkResult], rax; int
0x180014184  mov     r9d, 4; dwType
0x18001418a  xor     r8d, r8d; Reserved
0x18001418d  lea     rdx, aLocalprofilelo; "LocalProfileLoadTimeLow"
0x180014194  mov     rcx, [rbp+hKey]; hKey
0x180014198  call    cs:__imp_RegSetValueExW
0x18001419f  nop     dword ptr [rax+rax+00h]
0x1800141a4  test    eax, eax
0x1800141a6  jg      loc_180014275
0x1800141ac  js      loc_180014631
0x1800141b2  mov     eax, [rbp+SystemTimeAsFileTime.dwHighDateTime]
0x1800141b5  mov     [rbp+Data], eax
0x1800141b8  mov     [rsp+60h+cbData], 4; cbData
0x1800141c0  lea     rax, [rbp+Data]
0x1800141c4  mov     [rsp+60h+phkResult], rax; int
0x1800141c9  mov     r9d, 4; dwType
0x1800141cf  xor     r8d, r8d; Reserved
0x1800141d2  lea     rdx, aLocalprofilelo_0; "LocalProfileLoadTimeHigh"
0x1800141d9  mov     rcx, [rbp+hKey]; hKey
0x1800141dd  call    cs:__imp_RegSetValueExW
0x1800141e4  nop     dword ptr [rax+rax+00h]
0x1800141e9  test    eax, eax
0x1800141eb  jg      loc_180014284
0x1800141f1  js      loc_18001464E
0x1800141f7  test    byte ptr [rbx+8], 4
0x1800141fb  jz      loc_180014293
0x180014201  lea     rcx, [rbp+var_30]
0x180014205  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18001420a  mov     rcx, [rbp+Sid]; hMem
0x18001420e  test    rcx, rcx
0x180014211  jz      short loc_18001421F
0x180014213  call    cs:__imp_LocalFree
0x18001421a  nop     dword ptr [rax+rax+00h]
0x18001421f  mov     rcx, [rbp+hKey]; hKey
0x180014223  test    rcx, rcx
0x180014226  jz      short loc_180014234
0x180014228  call    cs:__imp_RegCloseKey
0x18001422f  nop     dword ptr [rax+rax+00h]
0x180014234  lea     rcx, [rbp+lpSubKey]
0x180014238  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18001423d  xor     eax, eax
0x18001423f  jmp     loc_180014122
0x180014244  mov     eax, 216h
0x180014249  movzx   eax, ax
0x18001424c  or      eax, 80070000h
0x180014251  jmp     loc_180013F32
0x180014256  movzx   edi, ax
0x180014259  or      edi, 80070000h
0x18001425f  jmp     loc_18001405A
0x180014264  call    cs:__imp_LocalFree
0x18001426b  nop     dword ptr [rax+rax+00h]
0x180014270  jmp     loc_1800140E6
0x180014275  movzx   eax, ax
0x180014278  or      eax, 80070000h
0x18001427d  test    eax, eax
0x18001427f  jmp     loc_1800141AC
0x180014284  movzx   eax, ax
0x180014287  or      eax, 80070000h
0x18001428c  test    eax, eax
0x18001428e  jmp     loc_1800141F1
0x180014293  mov     eax, [rbx+100h]
0x180014299  mov     [rbp+Data], eax
0x18001429c  mov     [rsp+60h+cbData], 4; cbData
0x1800142a4  lea     rax, [rbp+Data]
0x1800142a8  mov     [rsp+60h+phkResult], rax; int
0x1800142ad  mov     r9d, 4; dwType
0x1800142b3  xor     r8d, r8d; Reserved
0x1800142b6  lea     rdx, aProfileattempt_0; "ProfileAttemptedProfileDownloadTimeLow"
0x1800142bd  mov     rcx, [rbp+hKey]; hKey
0x1800142c1  call    cs:__imp_RegSetValueExW
0x1800142c8  nop     dword ptr [rax+rax+00h]
0x1800142cd  test    eax, eax
0x1800142cf  jg      loc_1800143CA
0x1800142d5  js      loc_18001466B
  ... truncated ...
```
