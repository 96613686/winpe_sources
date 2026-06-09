# CleanupRegistry

- ea: `0x18000663c`
- end: `0x1800069d1`
- name: `CleanupRegistry`
- size: `917`
- prototype: `LSTATUS()`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180006afc`
- `0x180007200`

## callees

- `0x18000663c`
- `0x180014ae0`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x18000673c`
- `ADVAPI32!RegCloseKey` at `0x180006810`
- `ADVAPI32!RegCloseKey` at `0x18000689b`
- `ADVAPI32!RegCloseKey` at `0x18000694a`
- `ADVAPI32!RegCloseKey` at `0x1800069ae`
- `ADVAPI32!RegCloseKey` at `0x18000673c`
- `ADVAPI32!RegCloseKey` at `0x180006810`
- `ADVAPI32!RegCloseKey` at `0x18000689b`
- `ADVAPI32!RegCloseKey` at `0x18000694a`
- `ADVAPI32!RegCloseKey` at `0x1800069ae`
- `ADVAPI32!RegOpenKeyExW` at `0x1800066b3`
- `ADVAPI32!RegOpenKeyExW` at `0x180006787`
- `ADVAPI32!RegOpenKeyExW` at `0x180006857`
- `ADVAPI32!RegOpenKeyExW` at `0x18000687a`
- `ADVAPI32!RegOpenKeyExW` at `0x1800068c1`
- `ADVAPI32!RegOpenKeyExW` at `0x18000698d`
- `ADVAPI32!RegOpenKeyExW` at `0x1800066b3`
- `ADVAPI32!RegOpenKeyExW` at `0x180006787`
- `ADVAPI32!RegOpenKeyExW` at `0x180006857`
- `ADVAPI32!RegOpenKeyExW` at `0x18000687a`
- `ADVAPI32!RegOpenKeyExW` at `0x1800068c1`
- `ADVAPI32!RegOpenKeyExW` at `0x18000698d`
- `ADVAPI32!RegDeleteKeyW` at `0x180006764`
- `ADVAPI32!RegDeleteKeyW` at `0x180006834`
- `ADVAPI32!RegDeleteKeyW` at `0x18000688e`
- `ADVAPI32!RegDeleteKeyW` at `0x18000696e`
- `ADVAPI32!RegDeleteKeyW` at `0x1800069a1`
- `ADVAPI32!RegDeleteKeyW` at `0x180006764`
- `ADVAPI32!RegDeleteKeyW` at `0x180006834`
- `ADVAPI32!RegDeleteKeyW` at `0x18000688e`
- `ADVAPI32!RegDeleteKeyW` at `0x18000696e`
- `ADVAPI32!RegDeleteKeyW` at `0x1800069a1`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18000672f`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180006803`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18000693d`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18000672f`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180006803`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18000693d`

## pseudocode

```c
LSTATUS CleanupRegistry()
{
  LSTATUS v0; // ebx
  LSTATUS v1; // ebx
  LSTATUS v2; // ebx
  DWORD cSubKeys; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cValues; // [rsp+64h] [rbp-9Ch] BYREF
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  DWORD cchClass; // [rsp+70h] [rbp-90h] BYREF
  DWORD cbSecurityDescriptor; // [rsp+74h] [rbp-8Ch] BYREF
  DWORD cbMaxValueLen; // [rsp+78h] [rbp-88h] BYREF
  DWORD cbMaxValueNameLen; // [rsp+7Ch] [rbp-84h] BYREF
  DWORD cbMaxClassLen; // [rsp+80h] [rbp-80h] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+84h] [rbp-7Ch] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+88h] [rbp-78h] BYREF
  WCHAR Class[128]; // [rsp+90h] [rbp-70h] BYREF

  hKey = 0;
  cSubKeys = 0;
  cValues = 0;
  cchClass = 0;
  cbMaxSubKeyLen = 0;
  cbMaxClassLen = 0;
  cbMaxValueNameLen = 0;
  cbMaxValueLen = 0;
  cbSecurityDescriptor = 0;
  ftLastWriteTime = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\ODBC\\ODBCINST.INI", 0, 0x2001Fu, &hKey) )
  {
    cValues = 0;
    cSubKeys = 0;
    cchClass = 128;
    v0 = RegQueryInfoKeyW(
           hKey,
           Class,
           &cchClass,
           0,
           &cSubKeys,
           &cbMaxSubKeyLen,
           &cbMaxClassLen,
           &cValues,
           &cbMaxValueNameLen,
           &cbMaxValueLen,
           &cbSecurityDescriptor,
           &ftLastWriteTime);
    RegCloseKey(hKey);
    if ( (!v0 || v0 == 234) && !cSubKeys && !cValues )
      RegDeleteKeyW(HKEY_LOCAL_MACHINE, L"Software\\ODBC\\ODBCINST.INI");
  }
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\ODBC\\ODBC.INI", 0, 0x2001Fu, &hKey) )
  {
    cValues = 0;
    cSubKeys = 0;
    cchClass = 128;
    v1 = RegQueryInfoKeyW(
           hKey,
           Class,
           &cchClass,
           0,
           &cSubKeys,
           &cbMaxSubKeyLen,
           &cbMaxClassLen,
           &cValues,
           &cbMaxValueNameLen,
           &cbMaxValueLen,
           &cbSecurityDescriptor,
           &ftLastWriteTime);
    RegCloseKey(hKey);
    if ( (!v1 || v1 == 234) && !cSubKeys && !cValues )
      RegDeleteKeyW(HKEY_LOCAL_MACHINE, L"Software\\ODBC\\ODBC.INI");
  }
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\ODBC\\ODBCINST.INI", 0, 0x20019u, &hKey)
    && RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\ODBC\\ODBC.INI", 0, 0x20019u, &hKey) )
  {
    RegDeleteKeyW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\ODBC\\");
  }
  else
  {
    RegCloseKey(hKey);
  }
  if ( !RegOpenKeyExW(HKEY_CURRENT_USER, L"Software\\ODBC\\ODBC.INI", 0, 0x2001Fu, &hKey) )
  {
    cValues = 0;
    cSubKeys = 0;
    cchClass = 128;
    v2 = RegQueryInfoKeyW(
           hKey,
           Class,
           &cchClass,
           0,
           &cSubKeys,
           &cbMaxSubKeyLen,
           &cbMaxClassLen,
           &cValues,
           &cbMaxValueNameLen,
           &cbMaxValueLen,
           &cbSecurityDescriptor,
           &ftLastWriteTime);
    RegCloseKey(hKey);
    if ( (!v2 || v2 == 234) && !cSubKeys && !cValues )
      RegDeleteKeyW(HKEY_CURRENT_USER, L"Software\\ODBC\\ODBC.INI");
  }
  if ( RegOpenKeyExW(HKEY_CURRENT_USER, L"Software\\ODBC\\ODBC.INI", 0, 0x20019u, &hKey) )
    return RegDeleteKeyW(HKEY_CURRENT_USER, L"SOFTWARE\\ODBC\\");
  else
    return RegCloseKey(hKey);
}

```

## disassembly

```asm
0x18000663c  push    rbp
0x18000663e  push    rbx
0x18000663f  push    rsi
0x180006640  push    rdi
0x180006641  push    r14
0x180006643  lea     rbp, [rsp-0A0h]
0x18000664b  sub     rsp, 1A0h
0x180006652  mov     rax, cs:__security_cookie
0x180006659  xor     rax, rsp
0x18000665c  mov     [rbp+0C0h+var_30], rax
0x180006663  xor     edi, edi
0x180006665  lea     rax, [rsp+1C0h+hKey]
0x18000666a  mov     r14d, 2001Fh
0x180006670  mov     [rsp+1C0h+hKey], rdi
0x180006675  mov     rsi, 0FFFFFFFF80000002h
0x18000667c  mov     [rsp+1C0h+cSubKeys], edi
0x180006680  mov     r9d, r14d; samDesired
0x180006683  mov     [rsp+1C0h+cValues], edi
0x180006687  mov     rcx, rsi; hKey
0x18000668a  mov     [rsp+1C0h+cchClass], edi
0x18000668e  xor     r8d, r8d; ulOptions
0x180006691  mov     [rbp+0C0h+cbMaxSubKeyLen], edi
0x180006694  lea     rdx, aSoftwareOdbcOd; "Software\\ODBC\\ODBCINST.INI"
0x18000669b  mov     [rbp+0C0h+cbMaxClassLen], edi
0x18000669e  mov     [rsp+1C0h+cbMaxValueNameLen], edi
0x1800066a2  mov     [rsp+1C0h+cbMaxValueLen], edi
0x1800066a6  mov     [rsp+1C0h+cbSecurityDescriptor], edi
0x1800066aa  mov     qword ptr [rbp+0C0h+ftLastWriteTime.dwLowDateTime], rdi
0x1800066ae  mov     [rsp+1C0h+phkResult], rax; phkResult
0x1800066b3  call    cs:__imp_RegOpenKeyExW
0x1800066b9  test    eax, eax
0x1800066bb  jnz     loc_18000676A
0x1800066c1  mov     rcx, [rsp+1C0h+hKey]; hKey
0x1800066c6  lea     rax, [rbp+0C0h+ftLastWriteTime]
0x1800066ca  mov     [rsp+1C0h+lpftLastWriteTime], rax; lpftLastWriteTime
0x1800066cf  lea     r8, [rsp+1C0h+cchClass]; lpcchClass
0x1800066d4  lea     rax, [rsp+1C0h+cbSecurityDescriptor]
0x1800066d9  mov     [rsp+1C0h+cValues], edi
0x1800066dd  mov     [rsp+1C0h+lpcbSecurityDescriptor], rax; lpcbSecurityDescriptor
0x1800066e2  lea     rdx, [rbp+0C0h+Class]; lpClass
0x1800066e6  lea     rax, [rsp+1C0h+cbMaxValueLen]
0x1800066eb  mov     [rsp+1C0h+cSubKeys], edi
0x1800066ef  mov     [rsp+1C0h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x1800066f4  xor     r9d, r9d; lpReserved
0x1800066f7  lea     rax, [rsp+1C0h+cbMaxValueNameLen]
0x1800066fc  mov     [rsp+1C0h+cchClass], 80h
0x180006704  mov     [rsp+1C0h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x180006709  lea     rax, [rsp+1C0h+cValues]
0x18000670e  mov     [rsp+1C0h+lpcValues], rax; lpcValues
0x180006713  lea     rax, [rbp+0C0h+cbMaxClassLen]
0x180006717  mov     [rsp+1C0h+lpcbMaxClassLen], rax; lpcbMaxClassLen
0x18000671c  lea     rax, [rbp+0C0h+cbMaxSubKeyLen]
0x180006720  mov     [rsp+1C0h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x180006725  lea     rax, [rsp+1C0h+cSubKeys]
0x18000672a  mov     [rsp+1C0h+phkResult], rax; lpcSubKeys
0x18000672f  call    cs:__imp_RegQueryInfoKeyW
0x180006735  mov     rcx, [rsp+1C0h+hKey]; hKey
0x18000673a  mov     ebx, eax
0x18000673c  call    cs:__imp_RegCloseKey
0x180006742  test    ebx, ebx
0x180006744  jz      short loc_18000674E
0x180006746  cmp     ebx, 0EAh
0x18000674c  jnz     short loc_18000676A
0x18000674e  cmp     [rsp+1C0h+cSubKeys], edi
0x180006752  jnz     short loc_18000676A
0x180006754  cmp     [rsp+1C0h+cValues], edi
0x180006758  jnz     short loc_18000676A
0x18000675a  lea     rdx, aSoftwareOdbcOd; "Software\\ODBC\\ODBCINST.INI"
0x180006761  mov     rcx, rsi; hKey
0x180006764  call    cs:__imp_RegDeleteKeyW
0x18000676a  mov     r9d, r14d; samDesired
0x18000676d  lea     rax, [rsp+1C0h+hKey]
0x180006772  lea     r14, aSoftwareOdbcOd_1; "Software\\ODBC\\ODBC.INI"
0x180006779  mov     [rsp+1C0h+phkResult], rax; phkResult
0x18000677e  mov     rdx, r14; lpSubKey
0x180006781  xor     r8d, r8d; ulOptions
0x180006784  mov     rcx, rsi; hKey
0x180006787  call    cs:__imp_RegOpenKeyExW
0x18000678d  test    eax, eax
0x18000678f  jnz     loc_18000683A
0x180006795  mov     rcx, [rsp+1C0h+hKey]; hKey
0x18000679a  lea     rax, [rbp+0C0h+ftLastWriteTime]
0x18000679e  mov     [rsp+1C0h+lpftLastWriteTime], rax; lpftLastWriteTime
0x1800067a3  lea     r8, [rsp+1C0h+cchClass]; lpcchClass
0x1800067a8  lea     rax, [rsp+1C0h+cbSecurityDescriptor]
0x1800067ad  mov     [rsp+1C0h+cValues], edi
0x1800067b1  mov     [rsp+1C0h+lpcbSecurityDescriptor], rax; lpcbSecurityDescriptor
0x1800067b6  lea     rdx, [rbp+0C0h+Class]; lpClass
0x1800067ba  lea     rax, [rsp+1C0h+cbMaxValueLen]
0x1800067bf  mov     [rsp+1C0h+cSubKeys], edi
0x1800067c3  mov     [rsp+1C0h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x1800067c8  xor     r9d, r9d; lpReserved
0x1800067cb  lea     rax, [rsp+1C0h+cbMaxValueNameLen]
0x1800067d0  mov     [rsp+1C0h+cchClass], 80h
0x1800067d8  mov     [rsp+1C0h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x1800067dd  lea     rax, [rsp+1C0h+cValues]
0x1800067e2  mov     [rsp+1C0h+lpcValues], rax; lpcValues
0x1800067e7  lea     rax, [rbp+0C0h+cbMaxClassLen]
0x1800067eb  mov     [rsp+1C0h+lpcbMaxClassLen], rax; lpcbMaxClassLen
0x1800067f0  lea     rax, [rbp+0C0h+cbMaxSubKeyLen]
0x1800067f4  mov     [rsp+1C0h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x1800067f9  lea     rax, [rsp+1C0h+cSubKeys]
0x1800067fe  mov     [rsp+1C0h+phkResult], rax; lpcSubKeys
0x180006803  call    cs:__imp_RegQueryInfoKeyW
0x180006809  mov     rcx, [rsp+1C0h+hKey]; hKey
0x18000680e  mov     ebx, eax
0x180006810  call    cs:__imp_RegCloseKey
0x180006816  test    ebx, ebx
0x180006818  jz      short loc_180006822
0x18000681a  cmp     ebx, 0EAh
0x180006820  jnz     short loc_18000683A
0x180006822  cmp     [rsp+1C0h+cSubKeys], edi
0x180006826  jnz     short loc_18000683A
0x180006828  cmp     [rsp+1C0h+cValues], edi
0x18000682c  jnz     short loc_18000683A
0x18000682e  mov     rdx, r14; lpSubKey
0x180006831  mov     rcx, rsi; hKey
0x180006834  call    cs:__imp_RegDeleteKeyW
0x18000683a  lea     rax, [rsp+1C0h+hKey]
0x18000683f  mov     r9d, 20019h; samDesired
0x180006845  xor     r8d, r8d; ulOptions
0x180006848  mov     [rsp+1C0h+phkResult], rax; phkResult
0x18000684d  lea     rdx, aSoftwareOdbcOd; "Software\\ODBC\\ODBCINST.INI"
0x180006854  mov     rcx, rsi; hKey
0x180006857  call    cs:__imp_RegOpenKeyExW
0x18000685d  test    eax, eax
0x18000685f  jz      short loc_180006896
0x180006861  lea     rax, [rsp+1C0h+hKey]
0x180006866  mov     r9d, 20019h; samDesired
0x18000686c  xor     r8d, r8d; ulOptions
0x18000686f  mov     [rsp+1C0h+phkResult], rax; phkResult
0x180006874  mov     rdx, r14; lpSubKey
0x180006877  mov     rcx, rsi; hKey
0x18000687a  call    cs:__imp_RegOpenKeyExW
0x180006880  test    eax, eax
0x180006882  jz      short loc_180006896
0x180006884  lea     rdx, aSoftwareOdbc; "SOFTWARE\\ODBC\\"
0x18000688b  mov     rcx, rsi; hKey
0x18000688e  call    cs:__imp_RegDeleteKeyW
0x180006894  jmp     short loc_1800068A1
0x180006896  mov     rcx, [rsp+1C0h+hKey]; hKey
0x18000689b  call    cs:__imp_RegCloseKey
0x1800068a1  lea     rax, [rsp+1C0h+hKey]
0x1800068a6  mov     rsi, 0FFFFFFFF80000001h
0x1800068ad  mov     rcx, rsi; hKey
0x1800068b0  mov     [rsp+1C0h+phkResult], rax; phkResult
0x1800068b5  mov     r9d, 2001Fh; samDesired
0x1800068bb  xor     r8d, r8d; ulOptions
0x1800068be  mov     rdx, r14; lpSubKey
0x1800068c1  call    cs:__imp_RegOpenKeyExW
0x1800068c7  test    eax, eax
0x1800068c9  jnz     loc_180006974
0x1800068cf  mov     rcx, [rsp+1C0h+hKey]; hKey
0x1800068d4  lea     rax, [rbp+0C0h+ftLastWriteTime]
0x1800068d8  mov     [rsp+1C0h+lpftLastWriteTime], rax; lpftLastWriteTime
0x1800068dd  lea     r8, [rsp+1C0h+cchClass]; lpcchClass
0x1800068e2  lea     rax, [rsp+1C0h+cbSecurityDescriptor]
0x1800068e7  mov     [rsp+1C0h+cValues], edi
0x1800068eb  mov     [rsp+1C0h+lpcbSecurityDescriptor], rax; lpcbSecurityDescriptor
0x1800068f0  lea     rdx, [rbp+0C0h+Class]; lpClass
0x1800068f4  lea     rax, [rsp+1C0h+cbMaxValueLen]
0x1800068f9  mov     [rsp+1C0h+cSubKeys], edi
0x1800068fd  mov     [rsp+1C0h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x180006902  xor     r9d, r9d; lpReserved
0x180006905  lea     rax, [rsp+1C0h+cbMaxValueNameLen]
0x18000690a  mov     [rsp+1C0h+cchClass], 80h
0x180006912  mov     [rsp+1C0h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x180006917  lea     rax, [rsp+1C0h+cValues]
0x18000691c  mov     [rsp+1C0h+lpcValues], rax; lpcValues
0x180006921  lea     rax, [rbp+0C0h+cbMaxClassLen]
0x180006925  mov     [rsp+1C0h+lpcbMaxClassLen], rax; lpcbMaxClassLen
0x18000692a  lea     rax, [rbp+0C0h+cbMaxSubKeyLen]
0x18000692e  mov     [rsp+1C0h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x180006933  lea     rax, [rsp+1C0h+cSubKeys]
0x180006938  mov     [rsp+1C0h+phkResult], rax; lpcSubKeys
0x18000693d  call    cs:__imp_RegQueryInfoKeyW
0x180006943  mov     rcx, [rsp+1C0h+hKey]; hKey
0x180006948  mov     ebx, eax
0x18000694a  call    cs:__imp_RegCloseKey
0x180006950  test    ebx, ebx
0x180006952  jz      short loc_18000695C
0x180006954  cmp     ebx, 0EAh
0x18000695a  jnz     short loc_180006974
0x18000695c  cmp     [rsp+1C0h+cSubKeys], edi
0x180006960  jnz     short loc_180006974
0x180006962  cmp     [rsp+1C0h+cValues], edi
0x180006966  jnz     short loc_180006974
0x180006968  mov     rdx, r14; lpSubKey
0x18000696b  mov     rcx, rsi; hKey
0x18000696e  call    cs:__imp_RegDeleteKeyW
0x180006974  lea     rax, [rsp+1C0h+hKey]
0x180006979  mov     r9d, 20019h; samDesired
0x18000697f  xor     r8d, r8d; ulOptions
0x180006982  mov     [rsp+1C0h+phkResult], rax; phkResult
0x180006987  mov     rdx, r14; lpSubKey
0x18000698a  mov     rcx, rsi; hKey
0x18000698d  call    cs:__imp_RegOpenKeyExW
0x180006993  test    eax, eax
0x180006995  jz      short loc_1800069A9
0x180006997  lea     rdx, aSoftwareOdbc; "SOFTWARE\\ODBC\\"
0x18000699e  mov     rcx, rsi; hKey
0x1800069a1  call    cs:__imp_RegDeleteKeyW
0x1800069a7  jmp     short loc_1800069B4
0x1800069a9  mov     rcx, [rsp+1C0h+hKey]; hKey
0x1800069ae  call    cs:__imp_RegCloseKey
0x1800069b4  mov     rcx, [rbp+0C0h+var_30]
0x1800069bb  xor     rcx, rsp; StackCookie
0x1800069be  call    __security_check_cookie
0x1800069c3  add     rsp, 1A0h
0x1800069ca  pop     r14
0x1800069cc  pop     rdi
0x1800069cd  pop     rsi
0x1800069ce  pop     rbx
0x1800069cf  pop     rbp
0x1800069d0  retn
```
