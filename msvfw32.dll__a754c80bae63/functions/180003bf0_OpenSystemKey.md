# OpenSystemKey

- ea: `0x180003bf0`
- end: `0x180003c9a`
- name: `OpenSystemKey`
- size: `170`
- prototype: `__int64 __fastcall(PHKEY phkResult)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180004088`

## callees

- `0x1800014b0`
- `0x180002198`
- `0x180002280`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180003c6f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180003c6f`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180003c39`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180003c39`

## pseudocode

```c
LSTATUS __fastcall OpenSystemKey(PHKEY phkResult, __int64 a2, const wchar_t *a3)
{
  int v5; // eax
  wchar_t pszDest[256]; // [rsp+30h] [rbp-218h] BYREF

  StringCchCopyW(pszDest, 0x100u, L"Software\\Microsoft\\Windows NT\\CurrentVersion\\");
  v5 = lstrlenW(L"Software\\Microsoft\\Windows NT\\CurrentVersion\\");
  StringCchCatW(pszDest, 256LL - v5, a3);
  return RegOpenKeyExW(HKEY_LOCAL_MACHINE, pszDest, 0, 1u, phkResult);
}

```

## disassembly

```asm
0x180003bf0  mov     [rsp+arg_8], rbx
0x180003bf5  mov     [rsp+arg_18], rsi
0x180003bfa  push    rdi
0x180003bfb  sub     rsp, 240h
0x180003c02  mov     rax, cs:__security_cookie
0x180003c09  xor     rax, rsp
0x180003c0c  mov     [rsp+248h+var_18], rax
0x180003c14  mov     rdi, r8
0x180003c17  mov     rsi, rcx
0x180003c1a  mov     ebx, 100h
0x180003c1f  lea     r8, aSoftwareMicros; "Software\\Microsoft\\Windows NT\\Curren"...
0x180003c26  mov     edx, ebx; cchDest
0x180003c28  lea     rcx, [rsp+248h+pszDest]; pszDest
0x180003c2d  call    StringCchCopyW
0x180003c32  lea     rcx, aSoftwareMicros; "Software\\Microsoft\\Windows NT\\Curren"...
0x180003c39  call    cs:__imp_lstrlenW
0x180003c3f  movsxd  rcx, eax
0x180003c42  mov     r8, rdi; pszSrc
0x180003c45  sub     rbx, rcx
0x180003c48  lea     rcx, [rsp+248h+pszDest]; pszDest
0x180003c4d  mov     rdx, rbx; cchDest
0x180003c50  call    StringCchCatW
0x180003c55  mov     r9d, 1; samDesired
0x180003c5b  mov     [rsp+248h+phkResult], rsi; phkResult
0x180003c60  xor     r8d, r8d; ulOptions
0x180003c63  lea     rdx, [rsp+248h+pszDest]; lpSubKey
0x180003c68  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180003c6f  call    cs:__imp_RegOpenKeyExW
0x180003c75  mov     rcx, [rsp+248h+var_18]
0x180003c7d  xor     rcx, rsp; StackCookie
0x180003c80  call    __security_check_cookie
0x180003c85  lea     r11, [rsp+248h+var_8]
0x180003c8d  mov     rbx, [r11+18h]
0x180003c91  mov     rsi, [r11+28h]
0x180003c95  mov     rsp, r11
0x180003c98  pop     rdi
0x180003c99  retn
```
