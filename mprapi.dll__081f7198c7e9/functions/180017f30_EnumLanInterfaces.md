# EnumLanInterfaces

- ea: `0x180017f30`
- end: `0x180018085`
- name: `EnumLanInterfaces`
- size: `341`
- prototype: `__int64 __fastcall(HANDLE hMprConfig, HKEY hKey)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800276c0`
- `0x1800294a4`

## callees

- `0x180009868`
- `0x180017f30`
- `0x180022f2c`
- `0x180051160`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001804f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001804f`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180017fab`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180017fab`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180017ff7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180017ff7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001802c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001802c`

## pseudocode

```c
LSTATUS __fastcall EnumLanInterfaces(HANDLE hMprConfig, HKEY hKey)
{
  LSTATUS result; // eax
  DWORD i; // ebx
  DWORD cSubKeys; // [rsp+68h] [rbp-9h] BYREF
  DWORD cbData; // [rsp+6Ch] [rbp-5h] BYREF
  BYTE Data[8]; // [rsp+70h] [rbp-1h] BYREF
  HKEY phkResult; // [rsp+78h] [rbp+7h] BYREF
  DWORD Type; // [rsp+80h] [rbp+Fh] BYREF
  wchar_t pszDest[8]; // [rsp+88h] [rbp+17h] BYREF

  Type = 0;
  *(_DWORD *)Data = 0;
  cbData = 0;
  cSubKeys = 0;
  phkResult = 0;
  result = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
  if ( !result )
  {
    for ( i = 0; i < cSubKeys; ++i )
    {
      StringCbPrintfW(pszDest, 0xAu, L"%d", i);
      if ( !RegOpenKeyExW(hKey, pszDest, 0, 0x2001Fu, &phkResult) )
      {
        cbData = 4;
        if ( !RegQueryValueExW(phkResult, L"Type", 0, &Type, Data, &cbData) && *(_DWORD *)Data == 3 )
          MapInterfaceNamesCb(hMprConfig, phkResult);
        RegCloseKey(phkResult);
      }
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180017f30  mov     r11, rsp
0x180017f33  mov     [r11+18h], rbx
0x180017f37  push    rbp
0x180017f38  push    rsi
0x180017f39  push    rdi
0x180017f3a  push    r14
0x180017f3c  push    r15
0x180017f3e  lea     rbp, [r11-5Fh]
0x180017f42  sub     rsp, 0A0h
0x180017f49  mov     rax, cs:__security_cookie
0x180017f50  xor     rax, rsp
0x180017f53  mov     [rbp+57h+var_30], rax
0x180017f57  xor     r15d, r15d
0x180017f5a  lea     rax, [rbp+57h+cSubKeys]
0x180017f5e  mov     [r11-70h], r15
0x180017f62  mov     r14, rdx
0x180017f65  mov     [r11-78h], r15
0x180017f69  mov     esi, r9d
0x180017f6c  mov     [r11-80h], r15
0x180017f70  mov     rdi, rcx
0x180017f73  mov     [rsp+40h], r15; lpcbMaxValueNameLen
0x180017f78  xor     r9d, r9d; lpReserved
0x180017f7b  mov     [rsp+0C0h+lpcValues], r15; lpcValues
0x180017f80  xor     r8d, r8d; lpcchClass
0x180017f83  mov     [rsp+0C0h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x180017f88  xor     edx, edx; lpClass
0x180017f8a  mov     [rsp+0C0h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x180017f8f  mov     rcx, r14; hKey
0x180017f92  mov     [rsp+0C0h+lpcSubKeys], rax; lpcSubKeys
0x180017f97  mov     [rbp+57h+Type], r15d
0x180017f9b  mov     dword ptr [rbp+57h+Data], r15d
0x180017f9f  mov     [rbp+57h+cbData], r15d
0x180017fa3  mov     [rbp+57h+cSubKeys], r15d
0x180017fa7  mov     [rbp+57h+phkResult], r15
0x180017fab  call    cs:__imp_RegQueryInfoKeyW
0x180017fb1  test    eax, eax
0x180017fb3  jnz     loc_180018062
0x180017fb9  mov     ebx, r15d
0x180017fbc  cmp     [rbp+57h+cSubKeys], r15d
0x180017fc0  jbe     loc_180018060
0x180017fc6  mov     r9d, ebx
0x180017fc9  lea     r8, aD; "%d"
0x180017fd0  mov     edx, 0Ah; cbDest
0x180017fd5  lea     rcx, [rbp+57h+pszDest]; pszDest
0x180017fd9  call    StringCbPrintfW
0x180017fde  lea     rax, [rbp+57h+phkResult]
0x180017fe2  mov     r9d, 2001Fh; samDesired
0x180017fe8  xor     r8d, r8d; ulOptions
0x180017feb  mov     [rsp+0C0h+lpcSubKeys], rax; phkResult
0x180017ff0  lea     rdx, [rbp+57h+pszDest]; lpSubKey
0x180017ff4  mov     rcx, r14; hKey
0x180017ff7  call    cs:__imp_RegOpenKeyExW
0x180017ffd  test    eax, eax
0x180017fff  jnz     short loc_180018055
0x180018001  mov     rcx, [rbp+57h+phkResult]; hKey
0x180018005  lea     rax, [rbp+57h+cbData]
0x180018009  mov     [rsp+0C0h+lpcbMaxSubKeyLen], rax; lpcbData
0x18001800e  lea     r9, [rbp+57h+Type]; lpType
0x180018012  lea     rax, [rbp+57h+Data]
0x180018016  mov     [rbp+57h+cbData], 4
0x18001801d  xor     r8d, r8d; lpReserved
0x180018020  mov     [rsp+0C0h+lpcSubKeys], rax; lpData
0x180018025  lea     rdx, c_szType; "Type"
0x18001802c  call    cs:__imp_RegQueryValueExW
0x180018032  test    eax, eax
0x180018034  jnz     short loc_18001804B
0x180018036  cmp     dword ptr [rbp+57h+Data], 3
0x18001803a  jnz     short loc_18001804B
0x18001803c  mov     rdx, [rbp+57h+phkResult]; hKey
0x180018040  mov     r8d, esi
0x180018043  mov     rcx, rdi; hMprConfig
0x180018046  call    MapInterfaceNamesCb
0x18001804b  mov     rcx, [rbp+57h+phkResult]; hKey
0x18001804f  call    cs:__imp_RegCloseKey
0x180018055  inc     ebx
0x180018057  cmp     ebx, [rbp+57h+cSubKeys]
0x18001805a  jb      loc_180017FC6
0x180018060  xor     eax, eax
0x180018062  mov     rcx, [rbp+57h+var_30]
0x180018066  xor     rcx, rsp; StackCookie
0x180018069  call    __security_check_cookie
0x18001806e  mov     rbx, [rsp+0C0h+arg_10]
0x180018076  add     rsp, 0A0h
0x18001807d  pop     r15
0x18001807f  pop     r14
0x180018081  pop     rdi
0x180018082  pop     rsi
0x180018083  pop     rbp
0x180018084  retn
```
