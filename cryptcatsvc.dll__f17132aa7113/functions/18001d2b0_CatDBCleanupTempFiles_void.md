# _CatDBCleanupTempFiles(void)

- ea: `0x18001d2b0`
- end: `0x18001d4d5`
- name: `?_CatDBCleanupTempFiles@@YAXXZ`
- size: `549`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18000ad54`

## callees

- `0x18000be40`
- `0x18001d2b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001d2f2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001d2f2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001d4b1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001d4b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d42d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d42d`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18001d423`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18001d423`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18001d487`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18001d487`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18001d379`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18001d379`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001d4a4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001d4a4`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18001d3d1`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18001d3d1`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001d331`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001d331`

## string_xrefs

- `0x18001d305`: `Software\Microsoft\Cryptography\CatDBTempFiles`

## pseudocode

```c
void _CatDBCleanupTempFiles(void)
{
  DWORD i; // eax
  unsigned int v1; // edx
  __int64 v2; // rax
  unsigned __int64 v3; // rcx
  unsigned int v4; // edx
  __int64 v5; // rax
  unsigned __int64 v6; // rcx
  HKEY hKey; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cSubKeys; // [rsp+68h] [rbp-98h] BYREF
  DWORD cchName; // [rsp+6Ch] [rbp-94h] BYREF
  DWORD dwDisposition[4]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR Name[264]; // [rsp+80h] [rbp-80h] BYREF

  hKey = 0;
  cSubKeys = 0;
  dwDisposition[0] = 0;
  cchName = 0;
  EnterCriticalSection(&g_CleanupTempFilesCS);
  if ( !RegCreateKeyExW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Cryptography\\CatDBTempFiles",
          0,
          0,
          0,
          0x2001Fu,
          0,
          &hKey,
          dwDisposition) )
  {
    if ( !RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0) )
    {
      for ( i = cSubKeys; cSubKeys; i = cSubKeys )
      {
        cSubKeys = i - 1;
        cchName = 261;
        if ( !RegEnumKeyExW(hKey, i - 1, Name, &cchName, 0, 0, 0, 0) )
        {
          v1 = 0;
          v2 = -1;
          do
            ++v2;
          while ( Name[v2] );
          if ( v2 )
          {
            do
            {
              if ( Name[v1] == 42 )
                Name[v1] = 92;
              ++v1;
              v3 = -1;
              do
                ++v3;
              while ( Name[v3] );
            }
            while ( v1 < v3 );
          }
          if ( DeleteFileW(Name) || GetLastError() == 2 )
          {
            v4 = 0;
            v5 = -1;
            do
              ++v5;
            while ( Name[v5] );
            if ( v5 )
            {
              do
              {
                if ( Name[v4] == 92 )
                  Name[v4] = 42;
                ++v4;
                v6 = -1;
                do
                  ++v6;
                while ( Name[v6] );
              }
              while ( v4 < v6 );
            }
            RegDeleteKeyExW(hKey, Name, 0, 0);
          }
        }
      }
      cSubKeys = i - 1;
    }
    RegCloseKey(hKey);
  }
  LeaveCriticalSection(&g_CleanupTempFilesCS);
}

```

## disassembly

```asm
0x18001d2b0  push    rbp
0x18001d2b2  push    rbx
0x18001d2b3  push    rdi
0x18001d2b4  push    r14
0x18001d2b6  push    r15
0x18001d2b8  lea     rbp, [rsp-1A0h]
0x18001d2c0  sub     rsp, 2A0h
0x18001d2c7  mov     rax, cs:__security_cookie
0x18001d2ce  xor     rax, rsp
0x18001d2d1  mov     [rbp+1C0h+var_30], rax
0x18001d2d8  xor     ebx, ebx
0x18001d2da  lea     rcx, ?g_CleanupTempFilesCS@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18001d2e1  mov     [rsp+2C0h+hKey], rbx
0x18001d2e6  mov     [rsp+2C0h+cSubKeys], ebx
0x18001d2ea  mov     [rsp+2C0h+dwDisposition], ebx
0x18001d2ee  mov     [rsp+2C0h+cchName], ebx
0x18001d2f2  call    cs:__imp_EnterCriticalSection
0x18001d2f8  lea     rax, [rsp+2C0h+dwDisposition]
0x18001d2fd  xor     r9d, r9d; lpClass
0x18001d300  mov     [rsp+2C0h+lpdwDisposition], rax; lpdwDisposition
0x18001d305  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Cryptography\\CatD"...
0x18001d30c  lea     rax, [rsp+2C0h+hKey]
0x18001d311  xor     r8d, r8d; Reserved
0x18001d314  mov     [rsp+2C0h+phkResult], rax; phkResult
0x18001d319  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001d320  mov     [rsp+2C0h+lpSecurityAttributes], rbx; lpSecurityAttributes
0x18001d325  mov     [rsp+2C0h+samDesired], 2001Fh; samDesired
0x18001d32d  mov     [rsp+2C0h+dwOptions], ebx; dwOptions
0x18001d331  call    cs:__imp_RegCreateKeyExW
0x18001d337  test    eax, eax
0x18001d339  jnz     loc_18001D4AA
0x18001d33f  mov     rcx, [rsp+2C0h+hKey]; hKey
0x18001d344  lea     rax, [rsp+2C0h+cSubKeys]
0x18001d349  mov     [rsp+2C0h+lpftLastWriteTime], rbx; lpftLastWriteTime
0x18001d34e  xor     r9d, r9d; lpReserved
0x18001d351  mov     [rsp+2C0h+lpcbSecurityDescriptor], rbx; lpcbSecurityDescriptor
0x18001d356  xor     r8d, r8d; lpcchClass
0x18001d359  mov     [rsp+2C0h+lpcbMaxValueLen], rbx; lpcbMaxValueLen
0x18001d35e  xor     edx, edx; lpClass
0x18001d360  mov     [rsp+2C0h+lpdwDisposition], rbx; lpcbMaxValueNameLen
0x18001d365  mov     [rsp+2C0h+phkResult], rbx; lpcValues
0x18001d36a  mov     [rsp+2C0h+lpSecurityAttributes], rbx; lpcbMaxClassLen
0x18001d36f  mov     qword ptr [rsp+2C0h+samDesired], rbx; lpcbMaxSubKeyLen
0x18001d374  mov     qword ptr [rsp+2C0h+dwOptions], rax; lpcSubKeys
0x18001d379  call    cs:__imp_RegQueryInfoKeyW
0x18001d37f  test    eax, eax
0x18001d381  jnz     loc_18001D49F
0x18001d387  mov     eax, [rsp+2C0h+cSubKeys]
0x18001d38b  test    eax, eax
0x18001d38d  jz      loc_18001D499
0x18001d393  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18001d397  lea     r15d, [rbx+2Ah]
0x18001d39b  lea     r14d, [rbx+5Ch]
0x18001d39f  mov     rcx, [rsp+2C0h+hKey]; hKey
0x18001d3a4  lea     r9, [rsp+2C0h+cchName]; lpcchName
0x18001d3a9  dec     eax
0x18001d3ab  mov     [rsp+2C0h+phkResult], rbx; lpftLastWriteTime
0x18001d3b0  mov     [rsp+2C0h+lpSecurityAttributes], rbx; lpcchClass
0x18001d3b5  lea     r8, [rbp+1C0h+Name]; lpName
0x18001d3b9  mov     qword ptr [rsp+2C0h+samDesired], rbx; lpClass
0x18001d3be  mov     edx, eax; dwIndex
0x18001d3c0  mov     qword ptr [rsp+2C0h+dwOptions], rbx; lpReserved
0x18001d3c5  mov     [rsp+2C0h+cSubKeys], eax
0x18001d3c9  mov     [rsp+2C0h+cchName], 105h
0x18001d3d1  call    cs:__imp_RegEnumKeyExW
0x18001d3d7  test    eax, eax
0x18001d3d9  jnz     loc_18001D48D
0x18001d3df  mov     edx, ebx
0x18001d3e1  lea     rcx, [rbp+1C0h+Name]
0x18001d3e5  mov     rax, rdi
0x18001d3e8  inc     rax
0x18001d3eb  cmp     [rcx+rax*2], bx
0x18001d3ef  jnz     short loc_18001D3E8
0x18001d3f1  test    rax, rax
0x18001d3f4  jz      short loc_18001D41F
0x18001d3f6  mov     eax, edx
0x18001d3f8  cmp     [rbp+rax*2+1C0h+Name], r15w
0x18001d3fe  jnz     short loc_18001D406
0x18001d400  mov     [rbp+rax*2+1C0h+Name], r14w
0x18001d406  inc     edx
0x18001d408  lea     rax, [rbp+1C0h+Name]
0x18001d40c  mov     rcx, rdi
0x18001d40f  inc     rcx
0x18001d412  cmp     [rax+rcx*2], bx
0x18001d416  jnz     short loc_18001D40F
0x18001d418  mov     eax, edx
0x18001d41a  cmp     rax, rcx
0x18001d41d  jb      short loc_18001D3F6
0x18001d41f  lea     rcx, [rbp+1C0h+Name]; lpFileName
0x18001d423  call    cs:__imp_DeleteFileW
0x18001d429  test    eax, eax
0x18001d42b  jnz     short loc_18001D438
0x18001d42d  call    cs:__imp_GetLastError
0x18001d433  cmp     eax, 2
0x18001d436  jnz     short loc_18001D48D
0x18001d438  mov     edx, ebx
0x18001d43a  lea     rcx, [rbp+1C0h+Name]
0x18001d43e  mov     rax, rdi
0x18001d441  inc     rax
0x18001d444  cmp     [rcx+rax*2], bx
0x18001d448  jnz     short loc_18001D441
0x18001d44a  test    rax, rax
0x18001d44d  jz      short loc_18001D478
0x18001d44f  mov     eax, edx
0x18001d451  cmp     [rbp+rax*2+1C0h+Name], r14w
0x18001d457  jnz     short loc_18001D45F
0x18001d459  mov     [rbp+rax*2+1C0h+Name], r15w
0x18001d45f  inc     edx
0x18001d461  lea     rax, [rbp+1C0h+Name]
0x18001d465  mov     rcx, rdi
0x18001d468  inc     rcx
0x18001d46b  cmp     [rax+rcx*2], bx
0x18001d46f  jnz     short loc_18001D468
0x18001d471  mov     eax, edx
0x18001d473  cmp     rax, rcx
0x18001d476  jb      short loc_18001D44F
0x18001d478  mov     rcx, [rsp+2C0h+hKey]; hKey
0x18001d47d  lea     rdx, [rbp+1C0h+Name]; lpSubKey
0x18001d481  xor     r9d, r9d; Reserved
0x18001d484  xor     r8d, r8d; samDesired
0x18001d487  call    cs:__imp_RegDeleteKeyExW
0x18001d48d  mov     eax, [rsp+2C0h+cSubKeys]
0x18001d491  test    eax, eax
0x18001d493  jnz     loc_18001D39F
0x18001d499  dec     eax
0x18001d49b  mov     [rsp+2C0h+cSubKeys], eax
0x18001d49f  mov     rcx, [rsp+2C0h+hKey]; hKey
0x18001d4a4  call    cs:__imp_RegCloseKey
0x18001d4aa  lea     rcx, ?g_CleanupTempFilesCS@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18001d4b1  call    cs:__imp_LeaveCriticalSection
0x18001d4b7  mov     rcx, [rbp+1C0h+var_30]
0x18001d4be  xor     rcx, rsp; StackCookie
0x18001d4c1  call    __security_check_cookie
0x18001d4c6  add     rsp, 2A0h
0x18001d4cd  pop     r15
0x18001d4cf  pop     r14
0x18001d4d1  pop     rdi
0x18001d4d2  pop     rbx
0x18001d4d3  pop     rbp
0x18001d4d4  retn
```
