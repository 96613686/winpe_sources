# helium::RemoveLookasideRegistryKey(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180014b54`
- end: `0x180014c94`
- name: `?RemoveLookasideRegistryKey@helium@@YAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z`
- size: `320`
- prototype: `void __fastcall(const WCHAR *lpSubKey, const WCHAR *)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180014c9c`
- `0x180014d28`

## callees

- `0x180014b54`
- `0x180014e74`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180014bf5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180014bf5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014bd6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014bd6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180014bb2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180014bb2`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180014c22`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180014c22`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180014be7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180014c44`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180014be7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180014c44`

## string_xrefs

- `0x180014c6d`: `onecore\base\appmodel\execmodel\desktopappx\lib\lookaside.cpp`
- `0x180014c82`: `onecore\base\appmodel\execmodel\desktopappx\lib\lookaside.cpp`

## pseudocode

```c
void __fastcall helium::RemoveLookasideRegistryKey(const WCHAR *lpSubKey, const WCHAR *a2)
{
  unsigned int v3; // esi
  unsigned int v4; // eax
  unsigned int phkResult; // [rsp+20h] [rbp-30h]
  HKEY v6; // [rsp+38h] [rbp-18h] BYREF
  char v7; // [rsp+40h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]
  HKEY hKey; // [rsp+80h] [rbp+30h]

  hKey = 0;
  v6 = 0;
  v7 = 1;
  if ( *((_QWORD *)lpSubKey + 3) > 7u )
    lpSubKey = *(const WCHAR **)lpSubKey;
  v3 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0xF003Fu, &v6);
  if ( v7 )
    hKey = v6;
  if ( v3 != 2 )
  {
    if ( v3 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0xBF,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\lookaside.cpp",
        (const char *)v3,
        phkResult);
    if ( *((_QWORD *)a2 + 3) > 7u )
      a2 = *(const WCHAR **)a2;
    v4 = RegDeleteTreeW(hKey, a2);
    if ( v4 != 2 && v4 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0xC6,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\lookaside.cpp",
        (const char *)v4,
        phkResult);
  }
  if ( hKey )
    RegCloseKey(hKey);
}

```

## disassembly

```asm
0x180014b54  mov     [rsp-28h+arg_8], rbx
0x180014b59  mov     [rsp-28h+arg_10], rsi
0x180014b5e  push    rbp
0x180014b5f  push    rdi
0x180014b60  push    r12
0x180014b62  push    r14
0x180014b64  push    r15
0x180014b66  mov     rbp, rsp
0x180014b69  sub     rsp, 50h
0x180014b6d  mov     rdi, rdx
0x180014b70  mov     [rbp+hKey], 0
0x180014b78  lea     rax, [rbp+hKey]
0x180014b7c  mov     [rbp+var_20], rax
0x180014b80  mov     [rbp+var_18], 0
0x180014b88  mov     [rbp+var_10], 1
0x180014b8c  cmp     qword ptr [rcx+18h], 7
0x180014b91  jbe     short loc_180014B96
0x180014b93  mov     rcx, [rcx]
0x180014b96  lea     rax, [rbp+var_18]
0x180014b9a  mov     qword ptr [rsp+50h+phkResult], rax; unsigned int
0x180014b9f  mov     r9d, 0F003Fh; samDesired
0x180014ba5  xor     r8d, r8d; ulOptions
0x180014ba8  mov     rdx, rcx; lpSubKey
0x180014bab  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180014bb2  call    cs:__imp_RegOpenKeyExW
0x180014bb9  nop     dword ptr [rax+rax+00h]
0x180014bbe  mov     esi, eax
0x180014bc0  cmp     [rbp+var_10], 0
0x180014bc4  jz      short loc_180014C04
0x180014bc6  mov     r12, [rbp+var_18]
0x180014bca  mov     r14, [rbp+var_20]
0x180014bce  mov     r15, [r14]
0x180014bd1  test    r15, r15
0x180014bd4  jz      short loc_180014C01
0x180014bd6  call    cs:__imp_GetLastError
0x180014bdd  nop     dword ptr [rax+rax+00h]
0x180014be2  mov     ebx, eax
0x180014be4  mov     rcx, r15; hKey
0x180014be7  call    cs:__imp_RegCloseKey
0x180014bee  nop     dword ptr [rax+rax+00h]
0x180014bf3  mov     ecx, ebx; dwErrCode
0x180014bf5  call    cs:__imp_SetLastError
0x180014bfc  nop     dword ptr [rax+rax+00h]
0x180014c01  mov     [r14], r12
0x180014c04  cmp     esi, 2
0x180014c07  jz      short loc_180014C3B
0x180014c09  mov     rcx, [rbp+28h]; this
0x180014c0d  test    esi, esi
0x180014c0f  jnz     short loc_180014C7F
0x180014c11  cmp     qword ptr [rdi+18h], 7
0x180014c16  jbe     short loc_180014C1B
0x180014c18  mov     rdi, [rdi]
0x180014c1b  mov     rdx, rdi; lpSubKey
0x180014c1e  mov     rcx, [rbp+hKey]; hKey
0x180014c22  call    cs:__imp_RegDeleteTreeW
0x180014c29  nop     dword ptr [rax+rax+00h]
0x180014c2e  cmp     eax, 2
0x180014c31  jz      short loc_180014C3B
0x180014c33  mov     rcx, [rbp+28h]; this
0x180014c37  test    eax, eax
0x180014c39  jnz     short loc_180014C6A
0x180014c3b  mov     rcx, [rbp+hKey]; hKey
0x180014c3f  test    rcx, rcx
0x180014c42  jz      short loc_180014C50
0x180014c44  call    cs:__imp_RegCloseKey
0x180014c4b  nop     dword ptr [rax+rax+00h]
0x180014c50  lea     r11, [rsp+50h+var_s0]
0x180014c55  mov     rbx, [r11+38h]
0x180014c59  mov     rsi, [r11+40h]
0x180014c5d  mov     rsp, r11
0x180014c60  pop     r15
0x180014c62  pop     r14
0x180014c64  pop     r12
0x180014c66  pop     rdi
0x180014c67  pop     rbp
0x180014c68  retn
0x180014c6a  mov     r9d, eax; char *
0x180014c6d  lea     r8, aOnecoreBaseApp_58; "onecore\\base\\appmodel\\execmodel\\des"...
0x180014c74  mov     edx, 0C6h; void *
0x180014c79  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180014c7f  mov     r9d, esi; char *
0x180014c82  lea     r8, aOnecoreBaseApp_58; "onecore\\base\\appmodel\\execmodel\\des"...
0x180014c89  mov     edx, 0BFh; void *
0x180014c8e  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
