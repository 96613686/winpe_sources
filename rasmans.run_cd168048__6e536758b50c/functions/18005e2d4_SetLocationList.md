# SetLocationList

- ea: `0x18005e2d4`
- end: `0x18005e4d6`
- name: `SetLocationList`
- size: `514`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18005e4dc`

## callees

- `0x18005e2d4`
- `0x180060014`
- `0x180060d1c`
- `0x1800e8ef0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005e47d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005e4a3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005e47d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005e4a3`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18005e344`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18005e437`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18005e344`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18005e437`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18005e3a1`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18005e3a1`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18005e368`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18005e368`

## pseudocode

```c
LSTATUS __fastcall SetLocationList(HKEY a1, __int64 *a2)
{
  LSTATUS result; // eax
  LSTATUS v4; // eax
  LSTATUS v5; // ebx
  __int64 v6; // rdi
  _DWORD *v7; // rsi
  LPDWORD lpcchClass; // [rsp+38h] [rbp-19h]
  DWORD cchName; // [rsp+58h] [rbp+7h] BYREF
  HKEY hKey; // [rsp+60h] [rbp+Fh] BYREF
  DWORD dwDisposition; // [rsp+68h] [rbp+17h] BYREF
  HKEY phkResult; // [rsp+70h] [rbp+1Fh] BYREF
  WCHAR SubKey[12]; // [rsp+78h] [rbp+27h] BYREF

  cchName = 0;
  dwDisposition = 0;
  hKey = 0;
  phkResult = 0;
  result = RegCreateKeyExW(a1, L"Location", 0, (LPWSTR)&Class, 0, 0x2000Eu, 0, &hKey, &dwDisposition);
  if ( !result )
  {
    do
    {
      cchName = 12;
      v4 = RegEnumKeyExW(hKey, 0, SubKey, &cchName, 0, 0, 0, 0);
      if ( v4 )
        break;
      v4 = RegDeleteKeyExW(hKey, SubKey, 0, 0);
    }
    while ( !v4 );
    v5 = 0;
    if ( v4 != 259 )
      v5 = v4;
    if ( !v5 )
    {
      v6 = *a2;
      if ( v6 )
      {
        do
        {
          v7 = *(_DWORD **)(v6 + 16);
          LODWORD(lpcchClass) = *v7;
          StringCchPrintfExW(SubKey, 0xCu, 0, 0, 0x100u, L"%d", lpcchClass);
          v5 = RegCreateKeyExW(hKey, SubKey, 0, (LPWSTR)&Class, 0, 0x20006u, 0, &phkResult, &dwDisposition);
          if ( v5 )
            break;
          v5 = SetRegDword(phkResult, L"Prefix", (unsigned int)v7[1]);
          if ( !v5 )
            v5 = SetRegDword(phkResult, L"Suffix", (unsigned int)v7[2]);
          RegCloseKey(phkResult);
          if ( v5 )
            break;
          v6 = *(_QWORD *)(v6 + 8);
        }
        while ( v6 );
      }
      else
      {
        v5 = 0;
      }
    }
    RegCloseKey(hKey);
    return v5;
  }
  return result;
}

```

## disassembly

```asm
0x18005e2d4  mov     r11, rsp
0x18005e2d7  mov     [r11+18h], rbx
0x18005e2db  mov     [r11+20h], rsi
0x18005e2df  push    rbp
0x18005e2e0  push    rdi
0x18005e2e1  push    r14
0x18005e2e3  lea     rbp, [r11-5Fh]
0x18005e2e7  sub     rsp, 90h
0x18005e2ee  mov     rax, cs:__security_cookie
0x18005e2f5  xor     rax, rsp
0x18005e2f8  mov     [rbp+57h+var_18], rax
0x18005e2fc  xor     r14d, r14d
0x18005e2ff  lea     rax, [rbp+57h+dwDisposition]
0x18005e303  mov     [r11-68h], rax
0x18005e307  lea     r9, Class; lpClass
0x18005e30e  lea     rax, [rbp+57h+hKey]
0x18005e312  mov     [rbp+57h+cchName], r14d
0x18005e316  mov     [r11-70h], rax
0x18005e31a  mov     rdi, rdx
0x18005e31d  mov     [r11-78h], r14
0x18005e321  lea     rdx, aLocation; "Location"
0x18005e328  mov     [rsp+0A0h+samDesired], 2000Eh; samDesired
0x18005e330  xor     r8d, r8d; Reserved
0x18005e333  mov     [rsp+0A0h+dwOptions], r14d; dwOptions
0x18005e338  mov     [rbp+57h+dwDisposition], r14d
0x18005e33c  mov     [rbp+57h+hKey], r14
0x18005e340  mov     [rbp+57h+phkResult], r14
0x18005e344  call    cs:__imp_RegCreateKeyExW
0x18005e34b  nop     dword ptr [rax+rax+00h]
0x18005e350  test    eax, eax
0x18005e352  jnz     loc_18005E4B1
0x18005e358  jmp     short loc_18005E378
0x18005e35a  mov     rcx, [rbp+57h+hKey]; hKey
0x18005e35e  lea     rdx, [rbp+57h+SubKey]; lpSubKey
0x18005e362  xor     r9d, r9d; Reserved
0x18005e365  xor     r8d, r8d; samDesired
0x18005e368  call    cs:__imp_RegDeleteKeyExW
0x18005e36f  nop     dword ptr [rax+rax+00h]
0x18005e374  test    eax, eax
0x18005e376  jnz     short loc_18005E3B1
0x18005e378  mov     rcx, [rbp+57h+hKey]; hKey
0x18005e37c  lea     r9, [rbp+57h+cchName]; lpcchName
0x18005e380  mov     [rsp+0A0h+lpftLastWriteTime], r14; lpftLastWriteTime
0x18005e385  lea     r8, [rbp+57h+SubKey]; lpName
0x18005e389  mov     [rsp+0A0h+lpcchClass], r14; lpcchClass
0x18005e38e  xor     edx, edx; dwIndex
0x18005e390  mov     qword ptr [rsp+0A0h+samDesired], r14; lpClass
0x18005e395  mov     qword ptr [rsp+0A0h+dwOptions], r14; lpReserved
0x18005e39a  mov     [rbp+57h+cchName], 0Ch
0x18005e3a1  call    cs:__imp_RegEnumKeyExW
0x18005e3a8  nop     dword ptr [rax+rax+00h]
0x18005e3ad  test    eax, eax
0x18005e3af  jz      short loc_18005E35A
0x18005e3b1  cmp     eax, 103h
0x18005e3b6  mov     ebx, r14d
0x18005e3b9  cmovnz  ebx, eax
0x18005e3bc  test    ebx, ebx
0x18005e3be  jnz     loc_18005E49F
0x18005e3c4  mov     rdi, [rdi]
0x18005e3c7  test    rdi, rdi
0x18005e3ca  jz      loc_18005E49C
0x18005e3d0  mov     rsi, [rdi+10h]
0x18005e3d4  lea     rcx, [rbp+57h+SubKey]; pszDest
0x18005e3d8  xor     r9d, r9d; pcchRemaining
0x18005e3db  xor     r8d, r8d; ppszDestEnd
0x18005e3de  mov     eax, [rsi]
0x18005e3e0  mov     dword ptr [rsp+0A0h+lpcchClass], eax
0x18005e3e4  lea     edx, [r9+0Ch]; cchDest
0x18005e3e8  lea     rax, aD; "%d"
0x18005e3ef  mov     qword ptr [rsp+0A0h+samDesired], rax; pszFormat
0x18005e3f4  mov     [rsp+0A0h+dwOptions], 100h; dwFlags
0x18005e3fc  call    StringCchPrintfExW
0x18005e401  mov     rcx, [rbp+57h+hKey]; hKey
0x18005e405  lea     rax, [rbp+57h+dwDisposition]
0x18005e409  mov     [rsp+0A0h+lpdwDisposition], rax; lpdwDisposition
0x18005e40e  lea     r9, Class; lpClass
0x18005e415  lea     rax, [rbp+57h+phkResult]
0x18005e419  xor     r8d, r8d; Reserved
0x18005e41c  mov     [rsp+0A0h+lpftLastWriteTime], rax; phkResult
0x18005e421  lea     rdx, [rbp+57h+SubKey]; lpSubKey
0x18005e425  mov     [rsp+0A0h+lpcchClass], r14; lpSecurityAttributes
0x18005e42a  mov     [rsp+0A0h+samDesired], 20006h; samDesired
0x18005e432  mov     [rsp+0A0h+dwOptions], r14d; dwOptions
0x18005e437  call    cs:__imp_RegCreateKeyExW
0x18005e43e  nop     dword ptr [rax+rax+00h]
0x18005e443  mov     ebx, eax
0x18005e445  test    eax, eax
0x18005e447  jnz     short loc_18005E49F
0x18005e449  mov     r8d, [rsi+4]
0x18005e44d  lea     rdx, aPrefix; "Prefix"
0x18005e454  mov     rcx, [rbp+57h+phkResult]
0x18005e458  call    SetRegDword
0x18005e45d  mov     ebx, eax
0x18005e45f  test    eax, eax
0x18005e461  jnz     short loc_18005E479
0x18005e463  mov     r8d, [rsi+8]
0x18005e467  lea     rdx, aSuffix; "Suffix"
0x18005e46e  mov     rcx, [rbp+57h+phkResult]
0x18005e472  call    SetRegDword
0x18005e477  mov     ebx, eax
0x18005e479  mov     rcx, [rbp+57h+phkResult]; hKey
0x18005e47d  call    cs:__imp_RegCloseKey
0x18005e484  nop     dword ptr [rax+rax+00h]
0x18005e489  test    ebx, ebx
0x18005e48b  jnz     short loc_18005E49F
0x18005e48d  mov     rdi, [rdi+8]
0x18005e491  test    rdi, rdi
0x18005e494  jnz     loc_18005E3D0
0x18005e49a  jmp     short loc_18005E49F
0x18005e49c  mov     ebx, r14d
0x18005e49f  mov     rcx, [rbp+57h+hKey]; hKey
0x18005e4a3  call    cs:__imp_RegCloseKey
0x18005e4aa  nop     dword ptr [rax+rax+00h]
0x18005e4af  mov     eax, ebx
0x18005e4b1  mov     rcx, [rbp+57h+var_18]
0x18005e4b5  xor     rcx, rsp; StackCookie
0x18005e4b8  call    __security_check_cookie
0x18005e4bd  lea     r11, [rsp+0A0h+var_10]
0x18005e4c5  mov     rbx, [r11+30h]
0x18005e4c9  mov     rsi, [r11+38h]
0x18005e4cd  mov     rsp, r11
0x18005e4d0  pop     r14
0x18005e4d2  pop     rdi
0x18005e4d3  pop     rbp
0x18005e4d4  retn
```
