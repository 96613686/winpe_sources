# Intl_HasAdminPrivileges(void)

- ea: `0x180025a1c`
- end: `0x180025ab3`
- name: `?Intl_HasAdminPrivileges@@YAHXZ`
- size: `151`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180014488`

## callees

- `0x180025a1c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180025a7e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180025a7e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180025a51`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180025a51`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180025aa0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180025aa0`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180025a90`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180025a90`

## pseudocode

```c
__int64 Intl_HasAdminPrivileges(void)
{
  unsigned int v0; // ebx
  HKEY hKey; // [rsp+40h] [rbp+8h] BYREF

  hKey = 0;
  v0 = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\Nls\\Locale", 0, 0x20006u, &hKey) )
  {
    if ( !RegSetValueExW(hKey, (LPCWSTR)L"Test", 0, 1u, L"Test", 0xAu) )
    {
      RegDeleteValueW(hKey, (LPCWSTR)L"Test");
      v0 = 1;
    }
    RegCloseKey(hKey);
  }
  return v0;
}

```

## disassembly

```asm
0x180025a1c  mov     r11, rsp
0x180025a1f  mov     [r11+10h], rbx
0x180025a23  push    rdi
0x180025a24  sub     rsp, 30h
0x180025a28  lea     rax, [r11+8]
0x180025a2c  mov     qword ptr [r11+8], 0
0x180025a34  mov     r9d, 20006h; samDesired
0x180025a3a  mov     [r11-18h], rax
0x180025a3e  xor     r8d, r8d; ulOptions
0x180025a41  lea     rdx, ?c_szInstalledLocales@@3QBGB; "System\\CurrentControlSet\\Control\\Nls"...
0x180025a48  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180025a4f  xor     ebx, ebx
0x180025a51  call    cs:__imp_RegOpenKeyExW
0x180025a57  test    eax, eax
0x180025a59  jnz     short loc_180025AA6
0x180025a5b  mov     rcx, [rsp+38h+hKey]; hKey
0x180025a60  lea     rdi, Data; "Test"
0x180025a67  mov     rdx, rdi; lpValueName
0x180025a6a  mov     [rsp+38h+cbData], 0Ah; cbData
0x180025a72  lea     r9d, [rbx+1]; dwType
0x180025a76  mov     [rsp+38h+lpData], rdi; lpData
0x180025a7b  xor     r8d, r8d; Reserved
0x180025a7e  call    cs:__imp_RegSetValueExW
0x180025a84  test    eax, eax
0x180025a86  jnz     short loc_180025A9B
0x180025a88  mov     rcx, [rsp+38h+hKey]; hKey
0x180025a8d  mov     rdx, rdi; lpValueName
0x180025a90  call    cs:__imp_RegDeleteValueW
0x180025a96  mov     ebx, 1
0x180025a9b  mov     rcx, [rsp+38h+hKey]; hKey
0x180025aa0  call    cs:__imp_RegCloseKey
0x180025aa6  mov     eax, ebx
0x180025aa8  mov     rbx, [rsp+38h+arg_8]
0x180025aad  add     rsp, 30h
0x180025ab1  pop     rdi
0x180025ab2  retn
```
