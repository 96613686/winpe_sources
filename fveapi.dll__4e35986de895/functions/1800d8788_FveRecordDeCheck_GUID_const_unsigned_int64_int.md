# FveRecordDeCheck(_GUID const *,unsigned __int64,int)

- ea: `0x1800d8788`
- end: `0x1800d91b7`
- name: `?FveRecordDeCheck@@YAXPEBU_GUID@@_KH@Z`
- size: `2607`
- prototype: `void __fastcall(GUID *rguid, unsigned __int64, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800d7284`

## callees

- `0x1800050c0`
- `0x18003a230`
- `0x1800600c0`
- `0x1800601a2`
- `0x1800d8788`
- `0x18011efc2`
- `0x18011efce`
- `0x18011f010`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x1800d8e0a`
- `msvcrt!wcsncpy_s` at `0x1800d8e2b`
- `msvcrt!wcsncpy_s` at `0x1800d8e0a`
- `msvcrt!wcsncpy_s` at `0x1800d8e2b`
- `msvcrt!swscanf_s` at `0x1800d8cc5`
- `msvcrt!swscanf_s` at `0x1800d8d1f`
- `msvcrt!swscanf_s` at `0x1800d8cc5`
- `msvcrt!swscanf_s` at `0x1800d8d1f`
- `msvcrt!_snwprintf_s` at `0x1800d8fb8`
- `msvcrt!_snwprintf_s` at `0x1800d8ffa`
- `msvcrt!_snwprintf_s` at `0x1800d8fb8`
- `msvcrt!_snwprintf_s` at `0x1800d8ffa`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800d8b1f`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800d8b37`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800d8b52`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800d904e`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800d9069`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800d9084`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800d9128`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800d913c`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800d9150`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800d8b1f`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800d8b37`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800d8b52`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800d904e`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800d9069`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800d9084`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800d9128`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800d913c`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800d9150`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d89de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d89de`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1800d8f54`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1800d8f54`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800d8a33`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800d8a33`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800d910d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800d910d`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800d90ce`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800d90ce`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800d8ab0`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800d8e95`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800d8ab0`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800d8e95`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1800d8c4d`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1800d8c4d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d9166`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d9166`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x1800d8ce2`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x1800d8ce2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800d9180`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800d9180`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800d8969`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800d8969`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800d89ce`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800d89ce`

## pseudocode

```c
void __fastcall FveRecordDeCheck(GUID *rguid, __int64 a2, int a3)
{
  PSECURITY_DESCRIPTOR v4; // rcx
  unsigned int v5; // r10d
  unsigned int i; // ebx
  LSTATUS v7; // eax
  char *v8; // r12
  void *v9; // r14
  struct _FILETIME *v10; // r15
  unsigned int v11; // r13d
  int v12; // esi
  LSTATUS v13; // eax
  LSTATUS v14; // edi
  int v15; // eax
  DWORD v16; // ebx
  unsigned __int64 v17; // rax
  unsigned __int64 v18; // rax
  unsigned __int64 v19; // rax
  DWORD j; // edi
  LSTATUS v21; // eax
  struct _FILETIME v22; // rbx
  unsigned int v23; // ecx
  struct _FILETIME v24; // r8
  struct _FILETIME v25; // rdx
  __int64 v26; // r14
  __int64 v27; // rsi
  __int64 v28; // rsi
  __int64 v29; // rdi
  __int64 v30; // rbx
  bool v31; // cf
  __int64 v32; // rax
  unsigned int v33; // r13d
  unsigned int v34; // ebx
  struct _FILETIME v35; // rcx
  DWORD dwOptions[2]; // [rsp+20h] [rbp-E0h]
  DWORD dwOptionsa[2]; // [rsp+20h] [rbp-E0h]
  REGSAM samDesired[2]; // [rsp+28h] [rbp-D8h]
  REGSAM samDesireda[2]; // [rsp+28h] [rbp-D8h]
  LPSECURITY_ATTRIBUTES lpSecurityAttributes; // [rsp+30h] [rbp-D0h]
  PHKEY phkResult; // [rsp+38h] [rbp-C8h]
  LPDWORD lpdwDisposition; // [rsp+40h] [rbp-C0h]
  LPDWORD lpcbMaxValueLen; // [rsp+48h] [rbp-B8h]
  LPDWORD lpcbSecurityDescriptor; // [rsp+50h] [rbp-B0h]
  DWORD cValues; // [rsp+60h] [rbp-A0h] BYREF
  __int16 v46; // [rsp+64h] [rbp-9Ch] BYREF
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  struct _FILETIME Buf2; // [rsp+70h] [rbp-90h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+78h] [rbp-88h] BYREF
  DWORD dwDisposition; // [rsp+80h] [rbp-80h] BYREF
  DWORD cbData; // [rsp+84h] [rbp-7Ch] BYREF
  DWORD cchValueName; // [rsp+88h] [rbp-78h] BYREF
  DWORD Type; // [rsp+8Ch] [rbp-74h] BYREF
  unsigned int v54; // [rsp+90h] [rbp-70h]
  DWORD v55; // [rsp+94h] [rbp-6Ch]
  int v56; // [rsp+98h] [rbp-68h]
  int v57; // [rsp+9Ch] [rbp-64h]
  char *v58; // [rsp+A0h] [rbp-60h]
  struct _FILETIME FileTime; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v60; // [rsp+B0h] [rbp-50h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor[2]; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v62; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v63; // [rsp+D0h] [rbp-30h]
  REGSAM v64[2]; // [rsp+D8h] [rbp-28h]
  LPSECURITY_ATTRIBUTES v65; // [rsp+E0h] [rbp-20h]
  int v66; // [rsp+E8h] [rbp-18h]
  __int64 v67; // [rsp+F0h] [rbp-10h]
  int v68; // [rsp+F8h] [rbp-8h]
  __int64 v69; // [rsp+100h] [rbp+0h]
  SYSTEMTIME SystemTime; // [rsp+108h] [rbp+8h] BYREF
  struct _SYSTEMTIME v71; // [rsp+118h] [rbp+18h] BYREF
  wchar_t v72[20]; // [rsp+128h] [rbp+28h] BYREF
  wchar_t Format[40]; // [rsp+150h] [rbp+50h] BYREF
  unsigned __int16 v74[8]; // [rsp+1A0h] [rbp+A0h] BYREF
  __int128 v75; // [rsp+1B0h] [rbp+B0h]
  __int128 v76; // [rsp+1C0h] [rbp+C0h]
  __int128 v77; // [rsp+1D0h] [rbp+D0h]
  __int128 v78; // [rsp+1E0h] [rbp+E0h]
  __int128 v79; // [rsp+1F0h] [rbp+F0h]
  __int128 v80; // [rsp+200h] [rbp+100h]
  __int128 v81; // [rsp+210h] [rbp+110h]
  int v82; // [rsp+220h] [rbp+120h]
  OLECHAR sz[40]; // [rsp+230h] [rbp+130h] BYREF
  WCHAR SubKey[112]; // [rsp+280h] [rbp+180h] BYREF
  WCHAR ValueName[264]; // [rsp+360h] [rbp+260h] BYREF
  wchar_t Data[259]; // [rsp+570h] [rbp+470h] BYREF
  __int16 v87; // [rsp+776h] [rbp+676h]

  wcscpy(Format, L"%04u-%02u-%02uT%02u:%02u:%02u.%03uZ");
  v57 = a3;
  v63 = a2;
  wcscpy(v72, L"%c;0016I64X");
  dwDisposition = 0;
  hKey = 0;
  v75 = *(_OWORD *)L"urrentControlSet\\Control\\BitLocker\\AutoDE\\ProvisionCheck\\";
  cValues = 0;
  *(_OWORD *)v74 = *(_OWORD *)L"SYSTEM\\CurrentControlSet\\Control\\BitLocker\\AutoDE\\ProvisionCheck\\";
  cchValueName = 0;
  v77 = *(_OWORD *)L"\\Control\\BitLocker\\AutoDE\\ProvisionCheck\\";
  cbData = 0;
  v76 = *(_OWORD *)L"ntrolSet\\Control\\BitLocker\\AutoDE\\ProvisionCheck\\";
  Buf2 = 0;
  v79 = *(_OWORD *)L"er\\AutoDE\\ProvisionCheck\\";
  ftLastWriteTime = 0;
  v78 = *(_OWORD *)L"\\BitLocker\\AutoDE\\ProvisionCheck\\";
  Type = 0;
  v81 = *(_OWORD *)L"ionCheck\\";
  v82 = *(_DWORD *)L"\\";
  v80 = *(_OWORD *)L"E\\ProvisionCheck\\";
  memset_0(sz, 0, 0x4Eu);
  memset_0(SubKey, 0, 0xD2u);
  FileTime = 0;
  v46 = 0;
  v62 = 0;
  v58 = 0;
  SystemTime = 0;
  v71 = 0;
  memset_0(ValueName, 0, 0x208u);
  memset_0(Data, 0, 0x208u);
  v60 = 24;
  v4 = 0;
  v64[0] = 983103;
  SecurityDescriptor[0] = 0;
  v65 = (LPSECURITY_ATTRIBUTES)&v60;
  v66 = 983103;
  SecurityDescriptor[1] = 0;
  v67 = 0;
  v68 = 131103;
  v69 = 0;
  if ( !rguid )
    goto LABEL_89;
  if ( StringFromGUID2(rguid, sz, 39)
    && (int)StringCchCopyW(SubKey, 0x69u, v74) >= 0
    && (int)StringCchCatW(SubKey, v5, sz) >= 0 )
  {
    if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
            L"D:(A;OICI;KR;;;WD)(A;OICI;KRKW;;;AU)(A;OICI;KA;;;BA)(A;OICI;KA;;;SY)",
            1u,
            SecurityDescriptor,
            0) )
    {
      GetLastError();
      goto LABEL_86;
    }
    for ( i = 0; i < 3; ++i )
    {
      v7 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0, 0, v64[4 * i], *(&v65 + 2 * i), &hKey, &dwDisposition);
      if ( v7 != 5 )
        break;
    }
    if ( v7 )
      goto LABEL_86;
    v8 = 0;
    v9 = 0;
    v10 = 0;
    v11 = 0;
    if ( dwDisposition == 2 )
    {
      v12 = 16;
      v56 = 16;
      v13 = RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, &cValues, 0, 0, 0, &ftLastWriteTime);
      while ( 1 )
      {
        v14 = v13;
        if ( v13 )
          break;
        v15 = memcmp_0(&ftLastWriteTime, &Buf2, 8u);
        v16 = cValues;
        if ( !v15 || !cValues || !v12 )
        {
          if ( !memcmp_0(&ftLastWriteTime, &Buf2, 8u) && v16 && v11 && v11 < v16 + 1 )
            goto LABEL_58;
          break;
        }
        if ( cValues + 1 < cValues || 260 * (cValues + 1) < 0x104 )
          goto LABEL_80;
        if ( v8 )
        {
          operator delete(v8);
          v16 = cValues;
        }
        if ( v9 )
        {
          operator delete(v9);
          v16 = cValues;
          v9 = 0;
        }
        if ( v10 )
        {
          operator delete(v10);
          v16 = cValues;
          v10 = 0;
        }
        v17 = 520LL * (v16 + 1);
        if ( !is_mul_ok(260 * (v16 + 1), 2u) )
          v17 = -1;
        v8 = (char *)operator new[](v17, (const struct std::nothrow_t *)&std::nothrow);
        if ( !v8 )
          goto LABEL_82;
        v18 = 520LL * (cValues + 1);
        if ( !is_mul_ok(260 * (cValues + 1), 2u) )
          v18 = -1;
        v58 = (char *)operator new[](v18, (const struct std::nothrow_t *)&std::nothrow);
        v9 = v58;
        if ( !v58 )
          goto LABEL_81;
        v19 = 8LL * (cValues + 1);
        if ( !is_mul_ok(cValues + 1, 8u) )
          v19 = -1;
        v10 = (struct _FILETIME *)operator new[](v19, (const struct std::nothrow_t *)&std::nothrow);
        if ( !v10 )
          goto LABEL_81;
        v11 = 0;
        for ( j = 0; ; ++j )
        {
          v55 = j;
          if ( j >= cValues )
            break;
          cchValueName = 260;
          cbData = 520;
          v21 = RegEnumValueW(hKey, j, ValueName, &cchValueName, 0, &Type, (LPBYTE)Data, &cbData);
          if ( v21 == 259 )
          {
            ftLastWriteTime = 0;
            break;
          }
          if ( v21 )
            goto LABEL_81;
          ValueName[259] = 0;
          v87 = 0;
          v10[v11] = (struct _FILETIME)1LL;
          if ( swscanf_s(
                 ValueName,
                 Format,
                 &SystemTime,
                 &SystemTime.wMonth,
                 &SystemTime.wDay,
                 &SystemTime.wHour,
                 &SystemTime.wMinute,
                 &SystemTime.wSecond,
                 &SystemTime.wMilliseconds) == 7
            && SystemTimeToFileTime(&SystemTime, &FileTime)
            && Type == 1
            && swscanf_s(Data, v72, &v46, 1, &v62) == 2
            && ((v46 - 43) & 0xFFFD) == 0 )
          {
            v22 = FileTime;
            v23 = 0;
            v54 = 0;
            if ( v11 )
            {
              do
              {
                if ( *(_QWORD *)&v10[v23] > *(unsigned __int64 *)&FileTime )
                  break;
                ++v23;
              }
              while ( v23 < v11 );
              v54 = v23;
            }
            v24 = (struct _FILETIME)(260 * v23);
            v25 = v24;
            Buf2 = v24;
            if ( v23 >= v11 )
            {
              v28 = v23;
              Buf2 = (struct _FILETIME)(260 * v23);
            }
            else
            {
              v26 = v11 - v23;
              v27 = v24.dwLowDateTime + 260;
              memmove_0(&v8[2 * v27], &v8[2 * *(_QWORD *)&v24], 2LL * (unsigned int)(260 * v26));
              memmove_0(&v58[2 * v27], &v58[2 * *(_QWORD *)&Buf2], 2LL * (unsigned int)(260 * v26));
              v28 = v54;
              memmove_0(&v10[v54 + 1], &v10[v54], 8 * v26);
              v25 = Buf2;
              v9 = v58;
              j = v55;
            }
            v10[v28] = v22;
            wcsncpy_s((wchar_t *)&v8[2 * *(_QWORD *)&v25], 0x104u, ValueName, 0xFFFFFFFFFFFFFFFFuLL);
            wcsncpy_s((wchar_t *)v9 + *(_QWORD *)&Buf2, 0x104u, Data, 0xFFFFFFFFFFFFFFFFuLL);
            ++v11;
          }
        }
        Buf2 = ftLastWriteTime;
        v13 = RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, &cValues, 0, 0, 0, &ftLastWriteTime);
        v12 = --v56;
      }
      v16 = 0;
      v11 = 0;
      cValues = 0;
      if ( v8 )
      {
        operator delete(v8);
        v16 = cValues;
        v8 = 0;
      }
      if ( v9 )
      {
        operator delete(v9);
        v16 = cValues;
        v9 = 0;
      }
      if ( v10 )
      {
        operator delete(v10);
        v16 = cValues;
        v10 = 0;
      }
      if ( v14 )
        goto LABEL_80;
    }
    else
    {
      v16 = cValues;
    }
LABEL_58:
    if ( v11 >= v16 + 1 )
      goto LABEL_80;
    if ( !v16 )
    {
      v8 = (char *)operator new[](0x208u, (const struct std::nothrow_t *)&std::nothrow);
      if ( !v8 )
        goto LABEL_82;
      v9 = operator new[](0x208u, (const struct std::nothrow_t *)&std::nothrow);
      if ( !v9 )
        goto LABEL_81;
      v10 = (struct _FILETIME *)operator new[](8u, (const struct std::nothrow_t *)&std::nothrow);
      if ( !v10 )
        goto LABEL_81;
    }
    GetSystemTime(&v71);
    LODWORD(lpcbSecurityDescriptor) = v71.wMilliseconds;
    LODWORD(lpcbMaxValueLen) = v71.wSecond;
    LODWORD(lpdwDisposition) = v71.wMinute;
    LODWORD(phkResult) = v71.wHour;
    LODWORD(lpSecurityAttributes) = v71.wDay;
    samDesired[0] = v71.wMonth;
    v29 = 260 * v11;
    dwOptions[0] = v71.wYear;
    _snwprintf_s(
      (wchar_t *const)&v8[2 * v29],
      0x104u,
      0x103u,
      Format,
      *(_QWORD *)dwOptions,
      *(_QWORD *)samDesired,
      lpSecurityAttributes,
      phkResult,
      lpdwDisposition,
      lpcbMaxValueLen,
      lpcbSecurityDescriptor);
    v30 = (unsigned int)(v29 + 259);
    *(_QWORD *)samDesireda = v63;
    v31 = v57 != 0;
    v57 = -v57;
    *(_WORD *)&v8[2 * v30] = 0;
    dwOptionsa[0] = v31 ? 43 : 45;
    _snwprintf_s((wchar_t *const)v9 + v29, 0x104u, 0x103u, v72, *(_QWORD *)dwOptionsa, *(_QWORD *)samDesireda);
    v32 = v11;
    v33 = v11 + 1;
    *((_WORD *)v9 + v30) = 0;
    v10[v32] = (struct _FILETIME)-1LL;
    if ( v33 <= 0x10 )
    {
      v34 = 0;
      if ( !v33 )
        goto LABEL_80;
    }
    else
    {
      memset_0(v10, 0, 8LL * (v33 - 16));
      v34 = 0;
    }
    do
    {
      v35 = v10[v34];
      if ( v35 )
      {
        if ( v35 == -1 )
          RegSetValueExW(hKey, (LPCWSTR)&v8[520 * v34], 0, 1u, (const BYTE *)v9 + 520 * v34, 0x208u);
      }
      else
      {
        RegDeleteValueW(hKey, (LPCWSTR)&v8[520 * v34]);
      }
      ++v34;
    }
    while ( v34 < v33 );
LABEL_80:
    if ( v8 )
LABEL_81:
      operator delete(v8);
LABEL_82:
    if ( v9 )
      operator delete(v9);
    if ( v10 )
      operator delete(v10);
  }
LABEL_86:
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  v4 = SecurityDescriptor[0];
LABEL_89:
  if ( v4 )
    LocalFree(v4);
}

```

## disassembly

```asm
0x1800d8788  mov     [rsp-8+arg_10], rbx
0x1800d878d  push    rbp
0x1800d878e  push    rsi
0x1800d878f  push    rdi
0x1800d8790  push    r12
0x1800d8792  push    r13
0x1800d8794  push    r14
0x1800d8796  push    r15
0x1800d8798  lea     rbp, [rsp-690h]
0x1800d87a0  sub     rsp, 790h
0x1800d87a7  mov     rax, cs:__security_cookie
0x1800d87ae  xor     rax, rsp
0x1800d87b1  mov     [rbp+6C0h+var_40], rax
0x1800d87b8  movaps  xmm0, xmmword ptr cs:a04u02u02ut02u0; "%04u-%02u-%02uT%02u:%02u:%02u.%03uZ"
0x1800d87bf  xor     esi, esi
0x1800d87c1  movaps  xmm1, xmmword ptr cs:a04u02u02ut02u0+10h; "u-%02uT%02u:%02u:%02u.%03uZ"
0x1800d87c8  mov     rbx, rcx
0x1800d87cb  mov     eax, dword ptr cs:aSystemCurrentc_1+80h; "\\"
0x1800d87d1  lea     rcx, [rbp+6C0h+sz]; void *
0x1800d87d8  movaps  xmmword ptr [rbp+6C0h+Format], xmm0
0x1800d87dc  movaps  xmm0, xmmword ptr cs:a04u02u02ut02u0+20h; "02u:%02u:%02u.%03uZ"
0x1800d87e3  movaps  [rbp+6C0h+var_660], xmm1
0x1800d87e7  movaps  xmm1, xmmword ptr cs:a04u02u02ut02u0+30h; ":%02u.%03uZ"
0x1800d87ee  movaps  [rbp+6C0h+var_650], xmm0
0x1800d87f2  movsd   xmm0, qword ptr cs:a04u02u02ut02u0+40h; "3uZ"
0x1800d87fa  movaps  [rbp+6C0h+var_640], xmm1
0x1800d8801  movups  xmm1, xmmword ptr cs:aC0x016i64x; "%c;0x%016I64X"
0x1800d8808  mov     [rbp+6C0h+var_724], r8d
0x1800d880c  lea     r8d, [rsi+4Eh]; Size
0x1800d8810  movsd   [rbp+6C0h+var_630], xmm0
0x1800d8818  movups  xmm0, xmmword ptr cs:aC0x016i64x+0Ch; "016I64X"
0x1800d881f  mov     [rbp+6C0h+var_6F0], rdx
0x1800d8823  xor     edx, edx; Val
0x1800d8825  movups  xmmword ptr [rbp+6C0h+var_698], xmm1
0x1800d8829  mov     [rbp+6C0h+dwDisposition], esi
0x1800d882c  movaps  xmm1, xmmword ptr cs:aSystemCurrentc_1; "SYSTEM\\CurrentControlSet\\Control\\Bit"...
0x1800d8833  movups  xmmword ptr [rbp+6C0h+var_698+0Ch], xmm0
0x1800d8837  mov     [rsp+7C0h+hKey], rsi
0x1800d883c  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_1+10h; "urrentControlSet\\Control\\BitLocker\\A"...
0x1800d8843  movups  [rbp+6C0h+var_610], xmm0
0x1800d884a  mov     [rsp+7C0h+cValues], esi
0x1800d884e  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_1+30h; "\\Control\\BitLocker\\AutoDE\\Provision"...
0x1800d8855  movups  xmmword ptr [rbp+6C0h+var_620], xmm1
0x1800d885c  mov     [rbp+6C0h+cchValueName], esi
0x1800d885f  movaps  xmm1, xmmword ptr cs:aSystemCurrentc_1+20h; "ntrolSet\\Control\\BitLocker\\AutoDE\\P"...
0x1800d8866  movups  [rbp+6C0h+var_5F0], xmm0
0x1800d886d  mov     [rbp+6C0h+cbData], esi
0x1800d8870  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_1+50h; "er\\AutoDE\\ProvisionCheck\\"
0x1800d8877  movups  [rbp+6C0h+var_600], xmm1
0x1800d887e  mov     [rsp+7C0h+Buf2], rsi
0x1800d8883  movaps  xmm1, xmmword ptr cs:aSystemCurrentc_1+40h; "\\BitLocker\\AutoDE\\ProvisionCheck\\"
0x1800d888a  movups  [rbp+6C0h+var_5D0], xmm0
0x1800d8891  mov     qword ptr [rsp+7C0h+ftLastWriteTime.dwLowDateTime], rsi
0x1800d8896  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_1+70h; "ionCheck\\"
0x1800d889d  movups  [rbp+6C0h+var_5E0], xmm1
0x1800d88a4  mov     [rbp+6C0h+Type], esi
0x1800d88a7  movaps  xmm1, xmmword ptr cs:aSystemCurrentc_1+60h; "E\\ProvisionCheck\\"
0x1800d88ae  movups  [rbp+6C0h+var_5B0], xmm0
0x1800d88b5  mov     [rbp+6C0h+var_5A0], eax
0x1800d88bb  movups  [rbp+6C0h+var_5C0], xmm1
0x1800d88c2  call    memset_0
0x1800d88c7  xor     edx, edx; Val
0x1800d88c9  lea     rcx, [rbp+6C0h+SubKey]; void *
0x1800d88d0  mov     r8d, 0D2h; Size
0x1800d88d6  call    memset_0
0x1800d88db  xorps   xmm0, xmm0
0x1800d88de  mov     qword ptr [rbp+6C0h+FileTime.dwLowDateTime], rsi
0x1800d88e2  mov     edi, 208h
0x1800d88e7  mov     [rsp+7C0h+var_75C], si
0x1800d88ec  mov     r8d, edi; Size
0x1800d88ef  mov     [rbp+6C0h+var_6F8], rsi
0x1800d88f3  xor     edx, edx; Val
0x1800d88f5  mov     [rbp+6C0h+var_720], rsi
0x1800d88f9  lea     rcx, [rbp+6C0h+ValueName]; void *
0x1800d8900  movups  xmmword ptr [rbp+6C0h+SystemTime.wYear], xmm0
0x1800d8904  movups  xmmword ptr [rbp+6C0h+var_6A8.wYear], xmm0
0x1800d8908  call    memset_0
0x1800d890d  mov     r8d, edi; Size
0x1800d8910  lea     rcx, [rbp+6C0h+Data]; void *
0x1800d8917  xor     edx, edx; Val
0x1800d8919  call    memset_0
0x1800d891e  mov     edx, 0F003Fh
0x1800d8923  mov     [rbp+6C0h+var_710], 18h
0x1800d892b  mov     ecx, esi
0x1800d892d  mov     [rbp+6C0h+var_6E8], edx
0x1800d8930  lea     rax, [rbp+6C0h+var_710]
0x1800d8934  mov     [rbp+6C0h+SecurityDescriptor], rcx
0x1800d8938  mov     [rbp+6C0h+var_6E0], rax
0x1800d893c  test    rbx, rbx
0x1800d893f  mov     [rbp+6C0h+var_6D8], edx
0x1800d8942  mov     [rbp+6C0h+var_700], rsi
0x1800d8946  mov     [rbp+6C0h+var_6D0], rsi
0x1800d894a  mov     [rbp+6C0h+var_6C8], 2001Fh
0x1800d8951  mov     [rbp+6C0h+var_6C0], rsi
0x1800d8955  jz      loc_1800D917B
0x1800d895b  lea     r8d, [rsi+27h]; cchMax
0x1800d895f  mov     rcx, rbx; rguid
0x1800d8962  lea     rdx, [rbp+6C0h+sz]; lpsz
0x1800d8969  call    cs:__imp_StringFromGUID2
0x1800d8970  nop     dword ptr [rax+rax+00h]
0x1800d8975  test    eax, eax
0x1800d8977  jz      loc_1800D915C
0x1800d897d  lea     r10d, [rsi+69h]
0x1800d8981  mov     edx, r10d; unsigned __int64
0x1800d8984  lea     r8, [rbp+6C0h+var_620]; unsigned __int16 *
0x1800d898b  lea     rcx, [rbp+6C0h+SubKey]; unsigned __int16 *
0x1800d8992  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800d8997  test    eax, eax
0x1800d8999  js      loc_1800D915C
0x1800d899f  lea     r8, [rbp+6C0h+sz]; unsigned __int16 *
0x1800d89a6  mov     edx, r10d; unsigned __int64
0x1800d89a9  lea     rcx, [rbp+6C0h+SubKey]; unsigned __int16 *
0x1800d89b0  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800d89b5  test    eax, eax
0x1800d89b7  js      loc_1800D915C
0x1800d89bd  xor     r9d, r9d; SecurityDescriptorSize
0x1800d89c0  lea     r8, [rbp+6C0h+SecurityDescriptor]; SecurityDescriptor
0x1800d89c4  lea     edx, [rsi+1]; StringSDRevision
0x1800d89c7  lea     rcx, StringSecurityDescriptor; "D:(A;OICI;KR;;;WD)(A;OICI;KRKW;;;AU)(A;"...
0x1800d89ce  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800d89d5  nop     dword ptr [rax+rax+00h]
0x1800d89da  test    eax, eax
0x1800d89dc  jnz     short loc_1800D89EF
0x1800d89de  call    cs:__imp_GetLastError
0x1800d89e5  nop     dword ptr [rax+rax+00h]
0x1800d89ea  jmp     loc_1800D915C
0x1800d89ef  mov     ebx, esi
0x1800d89f1  lea     rax, [rbp+6C0h+dwDisposition]
0x1800d89f5  mov     ecx, ebx
0x1800d89f7  mov     [rsp+7C0h+lpdwDisposition], rax; lpdwDisposition
0x1800d89fc  lea     rdx, [rbp+6C0h+SubKey]; lpSubKey
0x1800d8a03  add     rcx, rcx
0x1800d8a06  lea     rax, [rsp+7C0h+hKey]
0x1800d8a0b  mov     [rsp+7C0h+phkResult], rax; phkResult
0x1800d8a10  xor     r9d, r9d; lpClass
0x1800d8a13  xor     r8d, r8d; Reserved
0x1800d8a16  mov     rax, [rbp+rcx*8+6C0h+var_6E0]
0x1800d8a1b  mov     [rsp+7C0h+lpSecurityAttributes], rax; lpSecurityAttributes
0x1800d8a20  mov     eax, [rbp+rcx*8+6C0h+var_6E8]
0x1800d8a24  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800d8a2b  mov     [rsp+7C0h+samDesired], eax; samDesired
0x1800d8a2f  mov     [rsp+7C0h+dwOptions], esi; dwOptions
0x1800d8a33  call    cs:__imp_RegCreateKeyExW
0x1800d8a3a  nop     dword ptr [rax+rax+00h]
0x1800d8a3f  cmp     eax, 5
0x1800d8a42  jnz     short loc_1800D8A4B
0x1800d8a44  inc     ebx
0x1800d8a46  cmp     ebx, 3
0x1800d8a49  jb      short loc_1800D89F1
0x1800d8a4b  test    eax, eax
0x1800d8a4d  jnz     loc_1800D915C
0x1800d8a53  cmp     [rbp+6C0h+dwDisposition], 2
0x1800d8a57  mov     r12, rsi
0x1800d8a5a  mov     r14, rsi
0x1800d8a5d  mov     r15, rsi
0x1800d8a60  mov     r13d, esi
0x1800d8a63  jnz     loc_1800D90A4
0x1800d8a69  mov     rcx, [rsp+7C0h+hKey]; hKey
0x1800d8a6e  lea     esi, [rax+10h]
0x1800d8a71  xor     ebx, ebx
0x1800d8a73  mov     [rbp+6C0h+var_728], esi
0x1800d8a76  lea     rax, [rsp+7C0h+ftLastWriteTime]
0x1800d8a7b  xor     r9d, r9d; lpReserved
0x1800d8a7e  mov     [rsp+7C0h+lpftLastWriteTime], rax; lpftLastWriteTime
0x1800d8a83  xor     r8d, r8d; lpcchClass
0x1800d8a86  mov     [rsp+7C0h+lpcbSecurityDescriptor], rbx; lpcbSecurityDescriptor
0x1800d8a8b  lea     rax, [rsp+7C0h+cValues]
0x1800d8a90  mov     [rsp+7C0h+lpcbMaxValueLen], rbx; lpcbMaxValueLen
0x1800d8a95  xor     edx, edx; lpClass
0x1800d8a97  mov     [rsp+7C0h+lpdwDisposition], rbx; lpcbMaxValueNameLen
0x1800d8a9c  mov     [rsp+7C0h+phkResult], rax; lpcValues
0x1800d8aa1  mov     [rsp+7C0h+lpSecurityAttributes], rbx; lpcbMaxClassLen
0x1800d8aa6  mov     qword ptr [rsp+7C0h+samDesired], rbx; lpcbMaxSubKeyLen
0x1800d8aab  mov     qword ptr [rsp+7C0h+dwOptions], rbx; lpcSubKeys
0x1800d8ab0  call    cs:__imp_RegQueryInfoKeyW
0x1800d8ab7  nop     dword ptr [rax+rax+00h]
0x1800d8abc  mov     edi, eax
0x1800d8abe  test    eax, eax
0x1800d8ac0  jnz     loc_1800D903B
0x1800d8ac6  lea     r8d, [rax+8]; Size
0x1800d8aca  lea     rdx, [rsp+7C0h+Buf2]; Buf2
0x1800d8acf  lea     rcx, [rsp+7C0h+ftLastWriteTime]; Buf1
0x1800d8ad4  call    memcmp_0
0x1800d8ad9  mov     ebx, [rsp+7C0h+cValues]
0x1800d8add  test    eax, eax
0x1800d8adf  jz      loc_1800D8EAE
0x1800d8ae5  test    ebx, ebx
0x1800d8ae7  jz      loc_1800D8EAE
0x1800d8aed  test    esi, esi
0x1800d8aef  jz      loc_1800D8EAE
0x1800d8af5  lea     eax, [rbx+1]
0x1800d8af8  xor     esi, esi
0x1800d8afa  cmp     eax, ebx
0x1800d8afc  jb      loc_1800D9120
0x1800d8b02  lea     eax, [rbx+1]
0x1800d8b05  imul    edx, eax, 104h
0x1800d8b0b  cmp     edx, 104h
0x1800d8b11  jb      loc_1800D9120
0x1800d8b17  test    r12, r12
0x1800d8b1a  jz      short loc_1800D8B2F
0x1800d8b1c  mov     rcx, r12
0x1800d8b1f  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800d8b26  nop     dword ptr [rax+rax+00h]
0x1800d8b2b  mov     ebx, [rsp+7C0h+cValues]
0x1800d8b2f  test    r14, r14
0x1800d8b32  jz      short loc_1800D8B4A
0x1800d8b34  mov     rcx, r14
0x1800d8b37  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800d8b3e  nop     dword ptr [rax+rax+00h]
0x1800d8b43  mov     ebx, [rsp+7C0h+cValues]
0x1800d8b47  mov     r14, rsi
0x1800d8b4a  test    r15, r15
0x1800d8b4d  jz      short loc_1800D8B65
0x1800d8b4f  mov     rcx, r15
0x1800d8b52  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800d8b59  nop     dword ptr [rax+rax+00h]
0x1800d8b5e  mov     ebx, [rsp+7C0h+cValues]
0x1800d8b62  mov     r15, rsi
0x1800d8b65  lea     eax, [rbx+1]
0x1800d8b68  mov     r13d, 2
0x1800d8b6e  imul    edx, eax, 104h
0x1800d8b74  lea     rbx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x1800d8b7b  mov     eax, r13d
0x1800d8b7e  lea     rdi, [r13-3]
0x1800d8b82  mul     rdx
0x1800d8b85  mov     rdx, rbx; struct std::nothrow_t *
0x1800d8b88  cmovb   rax, rdi
0x1800d8b8c  mov     rcx, rax; unsigned __int64
0x1800d8b8f  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800d8b94  mov     r12, rax
0x1800d8b97  test    rax, rax
0x1800d8b9a  jz      loc_1800D9134
0x1800d8ba0  mov     eax, [rsp+7C0h+cValues]
0x1800d8ba4  inc     eax
0x1800d8ba6  imul    edx, eax, 104h
0x1800d8bac  mov     eax, r13d
0x1800d8baf  mul     rdx
0x1800d8bb2  mov     rdx, rbx; struct std::nothrow_t *
0x1800d8bb5  cmovb   rax, rdi
0x1800d8bb9  mov     rcx, rax; unsigned __int64
0x1800d8bbc  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800d8bc1  mov     [rbp+6C0h+var_720], rax
0x1800d8bc5  mov     r14, rax
0x1800d8bc8  test    rax, rax
0x1800d8bcb  jz      loc_1800D9125
0x1800d8bd1  mov     ecx, [rsp+7C0h+cValues]
0x1800d8bd5  lea     eax, [rdi+9]
0x1800d8bd8  inc     ecx
0x1800d8bda  mul     rcx
0x1800d8bdd  mov     rdx, rbx; struct std::nothrow_t *
0x1800d8be0  cmovb   rax, rdi
0x1800d8be4  mov     rcx, rax; unsigned __int64
0x1800d8be7  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800d8bec  mov     r15, rax
0x1800d8bef  test    rax, rax
0x1800d8bf2  jz      loc_1800D9125
0x1800d8bf8  mov     r13d, esi
0x1800d8bfb  mov     edi, esi
0x1800d8bfd  mov     [rbp+6C0h+var_72C], edi
0x1800d8c00  cmp     edi, [rsp+7C0h+cValues]
0x1800d8c04  jnb     loc_1800D8E4C
0x1800d8c0a  mov     rcx, [rsp+7C0h+hKey]; hKey
0x1800d8c0f  lea     rax, [rbp+6C0h+cbData]
0x1800d8c13  mov     [rsp+7C0h+phkResult], rax; lpcbData
0x1800d8c18  lea     r9, [rbp+6C0h+cchValueName]; lpcchValueName
0x1800d8c1c  lea     rax, [rbp+6C0h+Data]
0x1800d8c23  mov     [rbp+6C0h+cchValueName], 104h
0x1800d8c2a  mov     [rsp+7C0h+lpSecurityAttributes], rax; lpData
0x1800d8c2f  lea     r8, [rbp+6C0h+ValueName]; lpValueName
0x1800d8c36  lea     rax, [rbp+6C0h+Type]
0x1800d8c3a  mov     [rbp+6C0h+cbData], 208h
0x1800d8c41  mov     qword ptr [rsp+7C0h+samDesired], rax; lpType
0x1800d8c46  mov     edx, edi; dwIndex
0x1800d8c48  mov     qword ptr [rsp+7C0h+dwOptions], rsi; lpReserved
0x1800d8c4d  call    cs:__imp_RegEnumValueW
0x1800d8c54  nop     dword ptr [rax+rax+00h]
0x1800d8c59  cmp     eax, 103h
0x1800d8c5e  jz      loc_1800D8E43
0x1800d8c64  test    eax, eax
0x1800d8c66  jnz     loc_1800D9125
0x1800d8c6c  mov     eax, r13d
0x1800d8c6f  lea     r9, [rbp+6C0h+SystemTime.wMonth]
0x1800d8c73  mov     [rbp+6C0h+var_25A], si
0x1800d8c7a  lea     r8, [rbp+6C0h+SystemTime]
0x1800d8c7e  mov     [rbp+6C0h+var_4A], si
0x1800d8c85  lea     rdx, [rbp+6C0h+Format]; Format
0x1800d8c89  lea     rcx, [rbp+6C0h+ValueName]; Buffer
0x1800d8c90  mov     qword ptr [r15+rax*8], 1
0x1800d8c98  lea     rax, [rbp+6C0h+SystemTime.wMilliseconds]
0x1800d8c9c  mov     [rsp+7C0h+lpdwDisposition], rax
0x1800d8ca1  lea     rax, [rbp+6C0h+SystemTime.wSecond]
0x1800d8ca5  mov     [rsp+7C0h+phkResult], rax
0x1800d8caa  lea     rax, [rbp+6C0h+SystemTime.wMinute]
0x1800d8cae  mov     [rsp+7C0h+lpSecurityAttributes], rax
0x1800d8cb3  lea     rax, [rbp+6C0h+SystemTime.wHour]
0x1800d8cb7  mov     qword ptr [rsp+7C0h+samDesired], rax
0x1800d8cbc  lea     rax, [rbp+6C0h+SystemTime.wDay]
0x1800d8cc0  mov     qword ptr [rsp+7C0h+dwOptions], rax
0x1800d8cc5  call    cs:__imp_swscanf_s
0x1800d8ccc  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
