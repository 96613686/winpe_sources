# OpenUserKey

- ea: `0x180003ca0`
- end: `0x180003d81`
- name: `OpenUserKey`
- size: `225`
- prototype: `__int64 __fastcall(PHKEY phkResult)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180004088`
- `0x1800043b0`

## callees

- `0x1800014b0`
- `0x180002198`
- `0x180002280`
- `0x180003ca0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180003d58`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180003d58`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180003d45`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180003d45`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180003cf1`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180003cf1`

## pseudocode

```c
LSTATUS __fastcall OpenUserKey(PHKEY phkResult, __int64 a2, const wchar_t *a3)
{
  int v6; // eax
  DWORD dwDisposition[4]; // [rsp+50h] [rbp-238h] BYREF
  wchar_t pszDest[256]; // [rsp+60h] [rbp-228h] BYREF

  dwDisposition[0] = 0;
  StringCchCopyW(pszDest, 0x100u, L"Software\\Microsoft\\Windows NT\\CurrentVersion\\");
  v6 = lstrlenW(L"Software\\Microsoft\\Windows NT\\CurrentVersion\\");
  StringCchCatW(pszDest, 256LL - v6, a3);
  if ( a2 )
    return RegCreateKeyExW(HKEY_CURRENT_USER, pszDest, 0, 0, 0, 2u, 0, phkResult, dwDisposition);
  else
    return RegOpenKeyExW(HKEY_CURRENT_USER, pszDest, 0, 1u, phkResult);
}

```

## disassembly

```asm
0x180003ca0  mov     [rsp+arg_8], rbx
0x180003ca5  push    rbp
0x180003ca6  push    rsi
0x180003ca7  push    rdi
0x180003ca8  sub     rsp, 270h
0x180003caf  mov     rax, cs:__security_cookie
0x180003cb6  xor     rax, rsp
0x180003cb9  mov     [rsp+288h+var_28], rax
0x180003cc1  mov     rdi, r8
0x180003cc4  mov     [rsp+288h+dwDisposition], 0
0x180003ccc  mov     rsi, rdx
0x180003ccf  lea     r8, aSoftwareMicros; "Software\\Microsoft\\Windows NT\\Curren"...
0x180003cd6  mov     rbp, rcx
0x180003cd9  mov     ebx, 100h
0x180003cde  mov     edx, ebx; cchDest
0x180003ce0  lea     rcx, [rsp+288h+pszDest]; pszDest
0x180003ce5  call    StringCchCopyW
0x180003cea  lea     rcx, aSoftwareMicros; "Software\\Microsoft\\Windows NT\\Curren"...
0x180003cf1  call    cs:__imp_lstrlenW
0x180003cf7  movsxd  rcx, eax
0x180003cfa  mov     r8, rdi; pszSrc
0x180003cfd  sub     rbx, rcx
0x180003d00  lea     rcx, [rsp+288h+pszDest]; pszDest
0x180003d05  mov     rdx, rbx; cchDest
0x180003d08  call    StringCchCatW
0x180003d0d  xor     r8d, r8d; ulOptions
0x180003d10  lea     rdx, [rsp+288h+pszDest]; lpSubKey
0x180003d15  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180003d1c  test    rsi, rsi
0x180003d1f  jz      short loc_180003D4D
0x180003d21  lea     rax, [rsp+288h+dwDisposition]
0x180003d26  xor     r9d, r9d; lpClass
0x180003d29  mov     [rsp+288h+lpdwDisposition], rax; lpdwDisposition
0x180003d2e  mov     [rsp+288h+phkResult], rbp; phkResult
0x180003d33  mov     [rsp+288h+lpSecurityAttributes], r8; lpSecurityAttributes
0x180003d38  mov     [rsp+288h+samDesired], 2; samDesired
0x180003d40  mov     [rsp+288h+dwOptions], r8d; dwOptions
0x180003d45  call    cs:__imp_RegCreateKeyExW
0x180003d4b  jmp     short loc_180003D5E
0x180003d4d  mov     r9d, 1; samDesired
0x180003d53  mov     qword ptr [rsp+288h+dwOptions], rbp; phkResult
0x180003d58  call    cs:__imp_RegOpenKeyExW
0x180003d5e  mov     rcx, [rsp+288h+var_28]
0x180003d66  xor     rcx, rsp; StackCookie
0x180003d69  call    __security_check_cookie
0x180003d6e  mov     rbx, [rsp+288h+arg_8]
0x180003d76  add     rsp, 270h
0x180003d7d  pop     rdi
0x180003d7e  pop     rsi
0x180003d7f  pop     rbp
0x180003d80  retn
```
