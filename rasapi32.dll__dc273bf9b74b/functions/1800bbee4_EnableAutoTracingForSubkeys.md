# EnableAutoTracingForSubkeys

- ea: `0x1800bbee4`
- end: `0x1800bc142`
- name: `EnableAutoTracingForSubkeys`
- size: `606`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800bbcf8`

## callees

- `0x1800203dc`
- `0x18008d814`
- `0x1800bbee4`
- `0x1800bcecc`
- `0x1800bcf04`
- `0x1800ded50`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800bbfa4`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800bbfa4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800bc011`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800bc011`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800bc08c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800bc0f2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800bc08c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800bc0f2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800bc0fd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800bc0fd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800bc04a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800bc0be`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800bc04a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800bc0be`

## pseudocode

```c
__int64 __fastcall EnableAutoTracingForSubkeys(DWORD a1, DWORD a2, HKEY a3)
{
  WCHAR *v6; // rdi
  DWORD i; // ebx
  unsigned int v9; // r11d
  BYTE v10[4]; // [rsp+40h] [rbp-C0h] BYREF
  BYTE Data[4]; // [rsp+44h] [rbp-BCh] BYREF
  DWORD cbData; // [rsp+48h] [rbp-B8h] BYREF
  HKEY phkResult; // [rsp+50h] [rbp-B0h] BYREF
  DWORD cchName; // [rsp+58h] [rbp-A8h] BYREF
  wchar_t pszDest[264]; // [rsp+60h] [rbp-A0h] BYREF

  cchName = 0;
  *(_DWORD *)Data = 0;
  *(_DWORD *)v10 = 0;
  phkResult = 0;
  cbData = 4;
  v6 = (WCHAR *)MemoryAlloc(2 * a2, 0);
  if ( !v6 )
    return 8;
  for ( i = 0; i < a1; ++i )
  {
    cchName = a2;
    if ( RegEnumKeyExW(a3, i, v6, &cchName, 0, 0, 0, 0) )
      continue;
    StringCchCopyW(pszDest, 0x105u, L"SOFTWARE\\Microsoft\\Tracing");
    StringCchCatW(pszDest, v9, L"\\");
    StringCchCatW(pszDest, 0x105u, v6);
    if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, pszDest, 0, 0x2011Fu, &phkResult) )
      continue;
    cbData = 4;
    if ( !RegQueryValueExW(phkResult, L"EnableFileTracing", 0, 0, Data, &cbData) )
    {
      if ( *(_DWORD *)Data )
      {
        cbData = 4;
        if ( RegQueryValueExW(phkResult, L"EnableAutoFileTracing", 0, 0, v10, &cbData) == 2 )
        {
          *(_DWORD *)v10 = 0;
LABEL_12:
          RegSetValueExW(phkResult, L"EnableAutoFileTracing", 0, 4u, v10, 4u);
        }
      }
      else
      {
        *(_DWORD *)Data = 1;
        *(_DWORD *)v10 = 1;
        if ( !RegSetValueExW(phkResult, L"EnableFileTracing", 0, 4u, Data, 4u) )
          goto LABEL_12;
      }
    }
    RegCloseKey(phkResult);
  }
  MemoryFree(v6);
  return 0;
}

```

## disassembly

```asm
0x1800bbee4  mov     [rsp-8+arg_0], rbx
0x1800bbee9  mov     [rsp-8+arg_18], rsi
0x1800bbeee  push    rbp
0x1800bbeef  push    rdi
0x1800bbef0  push    r13
0x1800bbef2  push    r14
0x1800bbef4  push    r15
0x1800bbef6  lea     rbp, [rsp-180h]
0x1800bbefe  sub     rsp, 280h
0x1800bbf05  mov     rax, cs:__security_cookie
0x1800bbf0c  xor     rax, rsp
0x1800bbf0f  mov     [rbp+1A0h+var_30], rax
0x1800bbf16  mov     esi, ecx
0x1800bbf18  mov     [rsp+2A0h+cchName], 0
0x1800bbf20  lea     ecx, [rdx+rdx]
0x1800bbf23  mov     dword ptr [rsp+2A0h+Data], 0
0x1800bbf2b  mov     r14d, edx
0x1800bbf2e  mov     dword ptr [rsp+2A0h+var_260], 0
0x1800bbf36  mov     r13d, 4
0x1800bbf3c  mov     [rsp+2A0h+phkResult], 0
0x1800bbf45  xor     edx, edx
0x1800bbf47  mov     [rsp+2A0h+cbData], r13d
0x1800bbf4c  mov     r15, r8
0x1800bbf4f  call    MemoryAlloc
0x1800bbf54  mov     rdi, rax
0x1800bbf57  test    rax, rax
0x1800bbf5a  jnz     short loc_1800BBF64
0x1800bbf5c  lea     eax, [rdi+8]
0x1800bbf5f  jmp     loc_1800BC117
0x1800bbf64  xor     ebx, ebx
0x1800bbf66  test    esi, esi
0x1800bbf68  jz      loc_1800BC10D
0x1800bbf6e  mov     [rsp+2A0h+lpftLastWriteTime], 0; lpftLastWriteTime
0x1800bbf77  lea     r9, [rsp+2A0h+cchName]; lpcchName
0x1800bbf7c  mov     [rsp+2A0h+lpcchClass], 0; lpcchClass
0x1800bbf85  mov     r8, rdi; lpName
0x1800bbf88  mov     [rsp+2A0h+lpClass], 0; lpClass
0x1800bbf91  mov     edx, ebx; dwIndex
0x1800bbf93  mov     rcx, r15; hKey
0x1800bbf96  mov     [rsp+2A0h+lpReserved], 0; lpReserved
0x1800bbf9f  mov     [rsp+2A0h+cchName], r14d
0x1800bbfa4  call    cs:__imp_RegEnumKeyExW
0x1800bbfaa  test    eax, eax
0x1800bbfac  jnz     loc_1800BC103
0x1800bbfb2  mov     r11d, 105h
0x1800bbfb8  lea     r8, aSoftwareMicros_7; "SOFTWARE\\Microsoft\\Tracing"
0x1800bbfbf  mov     edx, r11d; cchDest
0x1800bbfc2  lea     rcx, [rsp+2A0h+pszDest]; pszDest
0x1800bbfc7  call    StringCchCopyW
0x1800bbfcc  lea     r8, asc_1800E75F8; "\\"
0x1800bbfd3  mov     edx, r11d; cchDest
0x1800bbfd6  lea     rcx, [rsp+2A0h+pszDest]; pszDest
0x1800bbfdb  call    StringCchCatW
0x1800bbfe0  mov     r8, rdi; pszSrc
0x1800bbfe3  lea     rcx, [rsp+2A0h+pszDest]; pszDest
0x1800bbfe8  mov     edx, 105h; cchDest
0x1800bbfed  call    StringCchCatW
0x1800bbff2  lea     rax, [rsp+2A0h+phkResult]
0x1800bbff7  mov     r9d, 2011Fh; samDesired
0x1800bbffd  xor     r8d, r8d; ulOptions
0x1800bc000  mov     [rsp+2A0h+lpReserved], rax; phkResult
0x1800bc005  lea     rdx, [rsp+2A0h+pszDest]; lpSubKey
0x1800bc00a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800bc011  call    cs:__imp_RegOpenKeyExW
0x1800bc017  test    eax, eax
0x1800bc019  jnz     loc_1800BC103
0x1800bc01f  mov     rcx, [rsp+2A0h+phkResult]; hKey
0x1800bc024  lea     rax, [rsp+2A0h+cbData]
0x1800bc029  mov     [rsp+2A0h+lpClass], rax; lpcbData
0x1800bc02e  lea     rdx, aEnablefiletrac; "EnableFileTracing"
0x1800bc035  lea     rax, [rsp+2A0h+Data]
0x1800bc03a  mov     [rsp+2A0h+cbData], r13d
0x1800bc03f  xor     r9d, r9d; lpType
0x1800bc042  mov     [rsp+2A0h+lpReserved], rax; lpData
0x1800bc047  xor     r8d, r8d; lpReserved
0x1800bc04a  call    cs:__imp_RegQueryValueExW
0x1800bc050  test    eax, eax
0x1800bc052  jnz     loc_1800BC0F8
0x1800bc058  mov     rcx, [rsp+2A0h+phkResult]; hKey
0x1800bc05d  cmp     dword ptr [rsp+2A0h+Data], eax
0x1800bc061  jnz     short loc_1800BC098
0x1800bc063  mov     eax, 1
0x1800bc068  mov     dword ptr [rsp+2A0h+lpClass], r13d; cbData
0x1800bc06d  mov     dword ptr [rsp+2A0h+Data], eax
0x1800bc071  lea     rdx, aEnablefiletrac; "EnableFileTracing"
0x1800bc078  mov     dword ptr [rsp+2A0h+var_260], eax
0x1800bc07c  mov     r9d, r13d; dwType
0x1800bc07f  lea     rax, [rsp+2A0h+Data]
0x1800bc084  xor     r8d, r8d; Reserved
0x1800bc087  mov     [rsp+2A0h+lpReserved], rax; lpData
0x1800bc08c  call    cs:__imp_RegSetValueExW
0x1800bc092  test    eax, eax
0x1800bc094  jnz     short loc_1800BC0F8
0x1800bc096  jmp     short loc_1800BC0D1
0x1800bc098  lea     rax, [rsp+2A0h+cbData]
0x1800bc09d  mov     [rsp+2A0h+cbData], r13d
0x1800bc0a2  mov     [rsp+2A0h+lpClass], rax; lpcbData
0x1800bc0a7  lea     rdx, aEnableautofile; "EnableAutoFileTracing"
0x1800bc0ae  lea     rax, [rsp+2A0h+var_260]
0x1800bc0b3  xor     r9d, r9d; lpType
0x1800bc0b6  xor     r8d, r8d; lpReserved
0x1800bc0b9  mov     [rsp+2A0h+lpReserved], rax; lpData
0x1800bc0be  call    cs:__imp_RegQueryValueExW
0x1800bc0c4  cmp     eax, 2
0x1800bc0c7  jnz     short loc_1800BC0F8
0x1800bc0c9  mov     dword ptr [rsp+2A0h+var_260], 0
0x1800bc0d1  mov     rcx, [rsp+2A0h+phkResult]; hKey
0x1800bc0d6  lea     rax, [rsp+2A0h+var_260]
0x1800bc0db  mov     dword ptr [rsp+2A0h+lpClass], r13d; cbData
0x1800bc0e0  lea     rdx, aEnableautofile; "EnableAutoFileTracing"
0x1800bc0e7  mov     r9d, r13d; dwType
0x1800bc0ea  mov     [rsp+2A0h+lpReserved], rax; lpData
0x1800bc0ef  xor     r8d, r8d; Reserved
0x1800bc0f2  call    cs:__imp_RegSetValueExW
0x1800bc0f8  mov     rcx, [rsp+2A0h+phkResult]; hKey
0x1800bc0fd  call    cs:__imp_RegCloseKey
0x1800bc103  inc     ebx
0x1800bc105  cmp     ebx, esi
0x1800bc107  jb      loc_1800BBF6E
0x1800bc10d  mov     rcx, rdi; lpMem
0x1800bc110  call    MemoryFree
0x1800bc115  xor     eax, eax
0x1800bc117  mov     rcx, [rbp+1A0h+var_30]
0x1800bc11e  xor     rcx, rsp; StackCookie
0x1800bc121  call    __security_check_cookie
0x1800bc126  lea     r11, [rsp+2A0h+var_20]
0x1800bc12e  mov     rbx, [r11+30h]
0x1800bc132  mov     rsi, [r11+48h]
0x1800bc136  mov     rsp, r11
0x1800bc139  pop     r15
0x1800bc13b  pop     r14
0x1800bc13d  pop     r13
0x1800bc13f  pop     rdi
0x1800bc140  pop     rbp
0x1800bc141  retn
```
