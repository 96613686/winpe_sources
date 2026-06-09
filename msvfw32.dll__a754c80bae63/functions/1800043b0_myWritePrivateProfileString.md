# myWritePrivateProfileString

- ea: `0x1800043b0`
- end: `0x180004581`
- name: `myWritePrivateProfileString`
- size: `465`
- prototype: `__int64 __fastcall(LPCWSTR lpAppName, LPCWSTR lpValueName, LPCWSTR)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800031d0`
- `0x180003960`

## callees

- `0x1800014b0`
- `0x180002198`
- `0x180002280`
- `0x180003b1c`
- `0x180003ca0`
- `0x1800043b0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000453a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004555`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000453a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004555`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000454a`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000454a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180004457`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000452f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180004457`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000452f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800044fb`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800044fb`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180004430`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180004460`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800044a3`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180004508`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180004430`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180004460`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800044a3`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180004508`
- `api-ms-win-core-privateprofile-l1-1-0!WritePrivateProfileStringW` at `0x1800043fc`
- `api-ms-win-core-privateprofile-l1-1-0!WritePrivateProfileStringW` at `0x1800043fc`

## pseudocode

```c
BOOL __fastcall myWritePrivateProfileString(LPCWSTR lpAppName, LPCWSTR lpValueName, LPCWSTR a3)
{
  int v7; // eax
  const WCHAR *v8; // rsi
  int v9; // eax
  int v10; // eax
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  DWORD dwDisposition; // [rsp+58h] [rbp-A8h] BYREF
  HKEY phkResult; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t pszDest[256]; // [rsp+70h] [rbp-90h] BYREF

  if ( (unsigned int)IsAdmin() )
    return WritePrivateProfileStringW(lpAppName, lpValueName, a3, FileName);
  hKey = 0;
  if ( (unsigned int)OpenUserKey(&hKey) )
    return 0;
  if ( a3 )
  {
    v7 = lstrlenW(a3);
    RegSetValueExW(hKey, lpValueName, 0, 1u, (const BYTE *)a3, 2 * v7 + 2);
    v8 = &a3[lstrlenW(a3) + 1];
    if ( *v8 )
    {
      phkResult = 0;
      dwDisposition = 0;
      StringCchCopyW(pszDest, 0x100u, L"Software\\Microsoft\\Windows NT\\CurrentVersion\\");
      v9 = lstrlenW(L"Software\\Microsoft\\Windows NT\\CurrentVersion\\");
      StringCchCatW(pszDest, 256LL - v9, L"Drivers.desc");
      if ( !RegCreateKeyExW(HKEY_CURRENT_USER, pszDest, 0, 0, 0, 2u, 0, &phkResult, &dwDisposition) )
      {
        v10 = lstrlenW(v8);
        RegSetValueExW(phkResult, a3, 0, 1u, (const BYTE *)v8, 2 * v10 + 2);
        RegCloseKey(phkResult);
      }
    }
  }
  else
  {
    RegDeleteValueW(hKey, lpValueName);
  }
  RegCloseKey(hKey);
  return 1;
}

```

## disassembly

```asm
0x1800043b0  push    rbp
0x1800043b2  push    rbx
0x1800043b3  push    rsi
0x1800043b4  push    rdi
0x1800043b5  push    r14
0x1800043b7  lea     rbp, [rsp-180h]
0x1800043bf  sub     rsp, 280h
0x1800043c6  mov     rax, cs:__security_cookie
0x1800043cd  xor     rax, rsp
0x1800043d0  mov     [rbp+1A0h+var_30], rax
0x1800043d7  mov     rdi, r8
0x1800043da  mov     rbx, rdx
0x1800043dd  mov     rsi, rcx
0x1800043e0  call    IsAdmin
0x1800043e5  xor     r14d, r14d
0x1800043e8  test    eax, eax
0x1800043ea  jz      short loc_180004407
0x1800043ec  lea     r9, FileName; "SYSTEM.INI"
0x1800043f3  mov     r8, rdi; lpString
0x1800043f6  mov     rdx, rbx; lpKeyName
0x1800043f9  mov     rcx, rsi; lpAppName
0x1800043fc  call    cs:__imp_WritePrivateProfileStringW
0x180004402  jmp     loc_180004564
0x180004407  mov     r8, rsi
0x18000440a  mov     [rsp+2A0h+hKey], r14
0x18000440f  mov     rdx, rdi
0x180004412  lea     rcx, [rsp+2A0h+hKey]; phkResult
0x180004417  call    OpenUserKey
0x18000441c  test    eax, eax
0x18000441e  jnz     loc_180004562
0x180004424  test    rdi, rdi
0x180004427  jz      loc_180004542
0x18000442d  mov     rcx, rdi; lpString
0x180004430  call    cs:__imp_lstrlenW
0x180004436  mov     rcx, [rsp+2A0h+hKey]; hKey
0x18000443b  mov     r9d, 1; dwType
0x180004441  xor     r8d, r8d; Reserved
0x180004444  mov     rdx, rbx; lpValueName
0x180004447  lea     eax, ds:2[rax*2]
0x18000444e  mov     [rsp+2A0h+cbData], eax; cbData
0x180004452  mov     [rsp+2A0h+lpData], rdi; lpData
0x180004457  call    cs:__imp_RegSetValueExW
0x18000445d  mov     rcx, rdi; lpString
0x180004460  call    cs:__imp_lstrlenW
0x180004466  movsxd  rsi, eax
0x180004469  inc     rsi
0x18000446c  lea     rsi, [rdi+rsi*2]
0x180004470  cmp     [rsi], r14w
0x180004474  jz      loc_180004550
0x18000447a  mov     ebx, 100h
0x18000447f  mov     [rsp+2A0h+var_240], r14
0x180004484  mov     edx, ebx; cchDest
0x180004486  mov     [rsp+2A0h+dwDisposition], r14d
0x18000448b  lea     r8, aSoftwareMicros; "Software\\Microsoft\\Windows NT\\Curren"...
0x180004492  lea     rcx, [rsp+2A0h+pszDest]; pszDest
0x180004497  call    StringCchCopyW
0x18000449c  lea     rcx, aSoftwareMicros; "Software\\Microsoft\\Windows NT\\Curren"...
0x1800044a3  call    cs:__imp_lstrlenW
0x1800044a9  movsxd  rcx, eax
0x1800044ac  lea     r8, aDriversDesc; "Drivers.desc"
0x1800044b3  sub     rbx, rcx
0x1800044b6  lea     rcx, [rsp+2A0h+pszDest]; pszDest
0x1800044bb  mov     rdx, rbx; cchDest
0x1800044be  call    StringCchCatW
0x1800044c3  lea     rax, [rsp+2A0h+dwDisposition]
0x1800044c8  xor     r9d, r9d; lpClass
0x1800044cb  mov     [rsp+2A0h+lpdwDisposition], rax; lpdwDisposition
0x1800044d0  lea     rdx, [rsp+2A0h+pszDest]; lpSubKey
0x1800044d5  lea     rax, [rsp+2A0h+var_240]
0x1800044da  xor     r8d, r8d; Reserved
0x1800044dd  mov     [rsp+2A0h+phkResult], rax; phkResult
0x1800044e2  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1800044e9  mov     [rsp+2A0h+lpSecurityAttributes], r14; lpSecurityAttributes
0x1800044ee  mov     [rsp+2A0h+cbData], 2; samDesired
0x1800044f6  mov     dword ptr [rsp+2A0h+lpData], r14d; dwOptions
0x1800044fb  call    cs:__imp_RegCreateKeyExW
0x180004501  test    eax, eax
0x180004503  jnz     short loc_180004550
0x180004505  mov     rcx, rsi; lpString
0x180004508  call    cs:__imp_lstrlenW
0x18000450e  mov     rcx, [rsp+2A0h+var_240]; hKey
0x180004513  mov     r9d, 1; dwType
0x180004519  xor     r8d, r8d; Reserved
0x18000451c  mov     rdx, rdi; lpValueName
0x18000451f  lea     eax, ds:2[rax*2]
0x180004526  mov     [rsp+2A0h+cbData], eax; cbData
0x18000452a  mov     [rsp+2A0h+lpData], rsi; lpData
0x18000452f  call    cs:__imp_RegSetValueExW
0x180004535  mov     rcx, [rsp+2A0h+var_240]; hKey
0x18000453a  call    cs:__imp_RegCloseKey
0x180004540  jmp     short loc_180004550
0x180004542  mov     rcx, [rsp+2A0h+hKey]; hKey
0x180004547  mov     rdx, rbx; lpValueName
0x18000454a  call    cs:__imp_RegDeleteValueW
0x180004550  mov     rcx, [rsp+2A0h+hKey]; hKey
0x180004555  call    cs:__imp_RegCloseKey
0x18000455b  mov     eax, 1
0x180004560  jmp     short loc_180004564
0x180004562  xor     eax, eax
0x180004564  mov     rcx, [rbp+1A0h+var_30]
0x18000456b  xor     rcx, rsp; StackCookie
0x18000456e  call    __security_check_cookie
0x180004573  add     rsp, 280h
0x18000457a  pop     r14
0x18000457c  pop     rdi
0x18000457d  pop     rsi
0x18000457e  pop     rbx
0x18000457f  pop     rbp
0x180004580  retn
```
