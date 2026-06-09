# Intl_LoadNtUserHive(ushort const *,ushort const *,uchar *)

- ea: `0x180025d38`
- end: `0x180025eb1`
- name: `?Intl_LoadNtUserHive@@YAPEAUHKEY__@@PEBG0PEAE@Z`
- size: `377`
- prototype: `HKEY(const unsigned __int16 *, const unsigned __int16 *, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `7`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180008408`
- `0x180026304`
- `0x1800265bc`

## callees

- `0x1800061e0`
- `0x1800062b0`
- `0x180025d38`
- `0x180026874`
- `0x180026df0`
- `0x18002a112`
- `0x18002a150`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180025e67`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180025e67`
- `api-ms-win-core-registry-l1-1-0!RegLoadKeyW` at `0x180025de9`
- `api-ms-win-core-registry-l1-1-0!RegLoadKeyW` at `0x180025de9`
- `USERENV!GetDefaultUserProfileDirectoryW` at `0x180025d94`
- `USERENV!GetDefaultUserProfileDirectoryW` at `0x180025d94`

## string_xrefs

- `0x180025de2`: `TempKey`
- `0x180025e1e`: `TempKey`
- `0x180025dc0`: `SeRestorePrivilege`
- `0x180025df1`: `SeRestorePrivilege`

## pseudocode

```c
HKEY __fastcall Intl_LoadNtUserHive(const unsigned __int16 *a1, const unsigned __int16 *a2, char *a3)
{
  LSTATUS KeyW; // ebx
  const unsigned __int16 *v6; // rcx
  HKEY phkResult; // [rsp+30h] [rbp-D0h] BYREF
  DWORD cchSize; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR ProfileDir[264]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR SubKey[256]; // [rsp+250h] [rbp+150h] BYREF

  phkResult = 0;
  memset_0(ProfileDir, 0, 0x208u);
  cchSize = 260;
  if ( GetDefaultUserProfileDirectoryW(ProfileDir, &cchSize) )
  {
    if ( StringCchCatW(ProfileDir, 0x104u, L"\\NTUSER.DAT") >= 0
      && (int)Intl_SetPrivilegeAccessToken(L"SeRestorePrivilege", 1, (bool *)a3) >= 0 )
    {
      KeyW = RegLoadKeyW(HKEY_USERS, L"TempKey", ProfileDir);
      Intl_SetPrivilegeAccessToken(L"SeRestorePrivilege", *a3, (bool *)a3);
      if ( !KeyW )
      {
        memset_0(SubKey, 0, sizeof(SubKey));
        if ( StringCchPrintfW(SubKey, 0x100u, L"%s\\%s", L"TempKey", a2) >= 0
          && RegOpenKeyExW(HKEY_USERS, SubKey, 0, 0x20006u, &phkResult) )
        {
          phkResult = 0;
        }
        if ( !phkResult )
          Intl_UnloadNtUserHive(v6, (unsigned __int8 *)a3);
      }
    }
  }
  return phkResult;
}

```

## disassembly

```asm
0x180025d38  mov     [rsp-8+arg_0], rbx
0x180025d3d  push    rbp
0x180025d3e  push    rsi
0x180025d3f  push    rdi
0x180025d40  lea     rbp, [rsp-360h]
0x180025d48  sub     rsp, 460h
0x180025d4f  mov     rax, cs:__security_cookie
0x180025d56  xor     rax, rsp
0x180025d59  mov     [rbp+370h+var_20], rax
0x180025d60  mov     rdi, r8
0x180025d63  mov     [rsp+470h+var_440], 0
0x180025d6c  mov     rsi, rdx
0x180025d6f  lea     rcx, [rsp+470h+ProfileDir]; void *
0x180025d74  xor     edx, edx; Val
0x180025d76  mov     r8d, 208h; Size
0x180025d7c  call    memset_0
0x180025d81  mov     ebx, 104h
0x180025d86  lea     rdx, [rsp+470h+cchSize]; lpcchSize
0x180025d8b  lea     rcx, [rsp+470h+ProfileDir]; lpProfileDir
0x180025d90  mov     [rsp+470h+cchSize], ebx
0x180025d94  call    cs:__imp_GetDefaultUserProfileDirectoryW
0x180025d9a  test    eax, eax
0x180025d9c  jz      loc_180025E8A
0x180025da2  lea     r8, aNtuserDat; "\\NTUSER.DAT"
0x180025da9  mov     edx, ebx; unsigned __int64
0x180025dab  lea     rcx, [rsp+470h+ProfileDir]; unsigned __int16 *
0x180025db0  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180025db5  test    eax, eax
0x180025db7  js      loc_180025E8A
0x180025dbd  mov     r8, rdi; unsigned __int8 *
0x180025dc0  lea     rcx, aSerestoreprivi; "SeRestorePrivilege"
0x180025dc7  mov     dl, 1; unsigned __int8
0x180025dc9  call    ?Intl_SetPrivilegeAccessToken@@YAKPEBGEPEAE@Z; Intl_SetPrivilegeAccessToken(ushort const *,uchar,uchar *)
0x180025dce  test    eax, eax
0x180025dd0  js      loc_180025E8A
0x180025dd6  lea     r8, [rsp+470h+ProfileDir]; lpFile
0x180025ddb  mov     rcx, 0FFFFFFFF80000003h; hKey
0x180025de2  lea     rdx, aTempkey; "TempKey"
0x180025de9  call    cs:__imp_RegLoadKeyW
0x180025def  mov     dl, [rdi]; unsigned __int8
0x180025df1  lea     rcx, aSerestoreprivi; "SeRestorePrivilege"
0x180025df8  mov     r8, rdi; unsigned __int8 *
0x180025dfb  mov     ebx, eax
0x180025dfd  call    ?Intl_SetPrivilegeAccessToken@@YAKPEBGEPEAE@Z; Intl_SetPrivilegeAccessToken(ushort const *,uchar,uchar *)
0x180025e02  test    ebx, ebx
0x180025e04  jnz     loc_180025E8A
0x180025e0a  xor     edx, edx; Val
0x180025e0c  lea     rcx, [rbp+370h+SubKey]; void *
0x180025e13  mov     r8d, 200h; Size
0x180025e19  call    memset_0
0x180025e1e  lea     r9, aTempkey; "TempKey"
0x180025e25  mov     [rsp+470h+phkResult], rsi
0x180025e2a  lea     r8, aSS_0; "%s\\%s"
0x180025e31  mov     edx, 100h; unsigned __int64
0x180025e36  lea     rcx, [rbp+370h+SubKey]; unsigned __int16 *
0x180025e3d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180025e42  test    eax, eax
0x180025e44  js      short loc_180025E7A
0x180025e46  lea     rax, [rsp+470h+var_440]
0x180025e4b  mov     r9d, 20006h; samDesired
0x180025e51  xor     r8d, r8d; ulOptions
0x180025e54  mov     [rsp+470h+phkResult], rax; phkResult
0x180025e59  lea     rdx, [rbp+370h+SubKey]; lpSubKey
0x180025e60  mov     rcx, 0FFFFFFFF80000003h; hKey
0x180025e67  call    cs:__imp_RegOpenKeyExW
0x180025e6d  test    eax, eax
0x180025e6f  jz      short loc_180025E7A
0x180025e71  mov     [rsp+470h+var_440], 0
0x180025e7a  cmp     [rsp+470h+var_440], 0
0x180025e80  jnz     short loc_180025E8A
0x180025e82  mov     rdx, rdi; unsigned __int8 *
0x180025e85  call    ?Intl_UnloadNtUserHive@@YAXPEBGPEAE@Z; Intl_UnloadNtUserHive(ushort const *,uchar *)
0x180025e8a  mov     rax, [rsp+470h+var_440]
0x180025e8f  mov     rcx, [rbp+370h+var_20]
0x180025e96  xor     rcx, rsp; StackCookie
0x180025e99  call    __security_check_cookie
0x180025e9e  mov     rbx, [rsp+470h+arg_0]
0x180025ea6  add     rsp, 460h
0x180025ead  pop     rdi
0x180025eae  pop     rsi
0x180025eaf  pop     rbp
0x180025eb0  retn
```
