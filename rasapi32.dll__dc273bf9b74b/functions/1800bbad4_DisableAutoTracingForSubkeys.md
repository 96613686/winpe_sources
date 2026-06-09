# DisableAutoTracingForSubkeys

- ea: `0x1800bbad4`
- end: `0x1800bbcef`
- name: `DisableAutoTracingForSubkeys`
- size: `539`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800bb96c`

## callees

- `0x1800203dc`
- `0x18008d814`
- `0x1800bbad4`
- `0x1800bcecc`
- `0x1800bcf04`
- `0x1800ded50`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800bbb94`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800bbb94`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800bbc01`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800bbc01`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800bbc74`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800bbc9f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800bbc74`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800bbc9f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800bbcaa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800bbcaa`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800bbc3a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800bbc3a`

## pseudocode

```c
__int64 __fastcall DisableAutoTracingForSubkeys(DWORD a1, DWORD a2, HKEY a3)
{
  wchar_t *v6; // rdi
  DWORD i; // ebx
  unsigned int v9; // r11d
  BYTE Data[8]; // [rsp+40h] [rbp-C0h] BYREF
  HKEY phkResult; // [rsp+48h] [rbp-B8h] BYREF
  DWORD cchName; // [rsp+50h] [rbp-B0h] BYREF
  DWORD cbData; // [rsp+54h] [rbp-ACh] BYREF
  BYTE v14[8]; // [rsp+58h] [rbp-A8h] BYREF
  wchar_t pszDest[264]; // [rsp+60h] [rbp-A0h] BYREF

  cchName = 0;
  *(_DWORD *)v14 = 0;
  *(_DWORD *)Data = 0;
  phkResult = 0;
  cbData = 4;
  v6 = (wchar_t *)MemoryAlloc(2 * a2, 0);
  if ( !v6 )
    return 8;
  for ( i = 0; i < a1; ++i )
  {
    cchName = a2;
    if ( !RegEnumKeyExW(a3, i, v6, &cchName, 0, 0, 0, 0) )
    {
      StringCchCopyW(pszDest, 0x105u, L"SOFTWARE\\Microsoft\\Tracing");
      StringCchCatW(pszDest, v9, L"\\");
      StringCchCatW(pszDest, 0x105u, v6);
      if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, pszDest, 0, 0x2011Fu, &phkResult) )
      {
        cbData = 4;
        if ( !RegQueryValueExW(phkResult, L"EnableAutoFileTracing", 0, 0, Data, &cbData) && *(_DWORD *)Data == 1 )
        {
          *(_DWORD *)v14 = 0;
          *(_DWORD *)Data = 0;
          if ( !RegSetValueExW(phkResult, L"EnableAutoFileTracing", 0, 4u, Data, 4u) )
            RegSetValueExW(phkResult, L"EnableFileTracing", 0, 4u, v14, 4u);
        }
        RegCloseKey(phkResult);
      }
    }
  }
  MemoryFree(v6);
  return 0;
}

```

## disassembly

```asm
0x1800bbad4  mov     [rsp-8+arg_0], rbx
0x1800bbad9  mov     [rsp-8+arg_18], rsi
0x1800bbade  push    rbp
0x1800bbadf  push    rdi
0x1800bbae0  push    r13
0x1800bbae2  push    r14
0x1800bbae4  push    r15
0x1800bbae6  lea     rbp, [rsp-180h]
0x1800bbaee  sub     rsp, 280h
0x1800bbaf5  mov     rax, cs:__security_cookie
0x1800bbafc  xor     rax, rsp
0x1800bbaff  mov     [rbp+1A0h+var_30], rax
0x1800bbb06  mov     esi, ecx
0x1800bbb08  mov     [rsp+2A0h+cchName], 0
0x1800bbb10  lea     ecx, [rdx+rdx]
0x1800bbb13  mov     dword ptr [rsp+2A0h+var_248], 0
0x1800bbb1b  mov     r14d, edx
0x1800bbb1e  mov     dword ptr [rsp+2A0h+Data], 0
0x1800bbb26  mov     r13d, 4
0x1800bbb2c  mov     [rsp+2A0h+phkResult], 0
0x1800bbb35  xor     edx, edx
0x1800bbb37  mov     [rsp+2A0h+cbData], r13d
0x1800bbb3c  mov     r15, r8
0x1800bbb3f  call    MemoryAlloc
0x1800bbb44  mov     rdi, rax
0x1800bbb47  test    rax, rax
0x1800bbb4a  jnz     short loc_1800BBB54
0x1800bbb4c  lea     eax, [rdi+8]
0x1800bbb4f  jmp     loc_1800BBCC4
0x1800bbb54  xor     ebx, ebx
0x1800bbb56  test    esi, esi
0x1800bbb58  jz      loc_1800BBCBA
0x1800bbb5e  mov     [rsp+2A0h+lpftLastWriteTime], 0; lpftLastWriteTime
0x1800bbb67  lea     r9, [rsp+2A0h+cchName]; lpcchName
0x1800bbb6c  mov     [rsp+2A0h+lpcchClass], 0; lpcchClass
0x1800bbb75  mov     r8, rdi; lpName
0x1800bbb78  mov     [rsp+2A0h+lpClass], 0; lpClass
0x1800bbb81  mov     edx, ebx; dwIndex
0x1800bbb83  mov     rcx, r15; hKey
0x1800bbb86  mov     [rsp+2A0h+lpReserved], 0; lpReserved
0x1800bbb8f  mov     [rsp+2A0h+cchName], r14d
0x1800bbb94  call    cs:__imp_RegEnumKeyExW
0x1800bbb9a  test    eax, eax
0x1800bbb9c  jnz     loc_1800BBCB0
0x1800bbba2  mov     r11d, 105h
0x1800bbba8  lea     r8, aSoftwareMicros_7; "SOFTWARE\\Microsoft\\Tracing"
0x1800bbbaf  mov     edx, r11d; cchDest
0x1800bbbb2  lea     rcx, [rsp+2A0h+pszDest]; pszDest
0x1800bbbb7  call    StringCchCopyW
0x1800bbbbc  lea     r8, asc_1800E75F8; "\\"
0x1800bbbc3  mov     edx, r11d; cchDest
0x1800bbbc6  lea     rcx, [rsp+2A0h+pszDest]; pszDest
0x1800bbbcb  call    StringCchCatW
0x1800bbbd0  mov     r8, rdi; pszSrc
0x1800bbbd3  lea     rcx, [rsp+2A0h+pszDest]; pszDest
0x1800bbbd8  mov     edx, 105h; cchDest
0x1800bbbdd  call    StringCchCatW
0x1800bbbe2  lea     rax, [rsp+2A0h+phkResult]
0x1800bbbe7  mov     r9d, 2011Fh; samDesired
0x1800bbbed  xor     r8d, r8d; ulOptions
0x1800bbbf0  mov     [rsp+2A0h+lpReserved], rax; phkResult
0x1800bbbf5  lea     rdx, [rsp+2A0h+pszDest]; lpSubKey
0x1800bbbfa  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800bbc01  call    cs:__imp_RegOpenKeyExW
0x1800bbc07  test    eax, eax
0x1800bbc09  jnz     loc_1800BBCB0
0x1800bbc0f  mov     rcx, [rsp+2A0h+phkResult]; hKey
0x1800bbc14  lea     rax, [rsp+2A0h+cbData]
0x1800bbc19  mov     [rsp+2A0h+lpClass], rax; lpcbData
0x1800bbc1e  lea     rdx, aEnableautofile; "EnableAutoFileTracing"
0x1800bbc25  lea     rax, [rsp+2A0h+Data]
0x1800bbc2a  mov     [rsp+2A0h+cbData], r13d
0x1800bbc2f  xor     r9d, r9d; lpType
0x1800bbc32  mov     [rsp+2A0h+lpReserved], rax; lpData
0x1800bbc37  xor     r8d, r8d; lpReserved
0x1800bbc3a  call    cs:__imp_RegQueryValueExW
0x1800bbc40  test    eax, eax
0x1800bbc42  jnz     short loc_1800BBCA5
0x1800bbc44  cmp     dword ptr [rsp+2A0h+Data], 1
0x1800bbc49  jnz     short loc_1800BBCA5
0x1800bbc4b  mov     rcx, [rsp+2A0h+phkResult]; hKey
0x1800bbc50  lea     rdx, aEnableautofile; "EnableAutoFileTracing"
0x1800bbc57  mov     dword ptr [rsp+2A0h+var_248], eax
0x1800bbc5b  mov     r9d, r13d; dwType
0x1800bbc5e  mov     dword ptr [rsp+2A0h+Data], eax
0x1800bbc62  xor     r8d, r8d; Reserved
0x1800bbc65  lea     rax, [rsp+2A0h+Data]
0x1800bbc6a  mov     dword ptr [rsp+2A0h+lpClass], r13d; cbData
0x1800bbc6f  mov     [rsp+2A0h+lpReserved], rax; lpData
0x1800bbc74  call    cs:__imp_RegSetValueExW
0x1800bbc7a  test    eax, eax
0x1800bbc7c  jnz     short loc_1800BBCA5
0x1800bbc7e  mov     rcx, [rsp+2A0h+phkResult]; hKey
0x1800bbc83  lea     rax, [rsp+2A0h+var_248]
0x1800bbc88  mov     dword ptr [rsp+2A0h+lpClass], r13d; cbData
0x1800bbc8d  lea     rdx, aEnablefiletrac; "EnableFileTracing"
0x1800bbc94  mov     r9d, r13d; dwType
0x1800bbc97  mov     [rsp+2A0h+lpReserved], rax; lpData
0x1800bbc9c  xor     r8d, r8d; Reserved
0x1800bbc9f  call    cs:__imp_RegSetValueExW
0x1800bbca5  mov     rcx, [rsp+2A0h+phkResult]; hKey
0x1800bbcaa  call    cs:__imp_RegCloseKey
0x1800bbcb0  inc     ebx
0x1800bbcb2  cmp     ebx, esi
0x1800bbcb4  jb      loc_1800BBB5E
0x1800bbcba  mov     rcx, rdi; lpMem
0x1800bbcbd  call    MemoryFree
0x1800bbcc2  xor     eax, eax
0x1800bbcc4  mov     rcx, [rbp+1A0h+var_30]
0x1800bbccb  xor     rcx, rsp; StackCookie
0x1800bbcce  call    __security_check_cookie
0x1800bbcd3  lea     r11, [rsp+2A0h+var_20]
0x1800bbcdb  mov     rbx, [r11+30h]
0x1800bbcdf  mov     rsi, [r11+48h]
0x1800bbce3  mov     rsp, r11
0x1800bbce6  pop     r15
0x1800bbce8  pop     r14
0x1800bbcea  pop     r13
0x1800bbcec  pop     rdi
0x1800bbced  pop     rbp
0x1800bbcee  retn
```
