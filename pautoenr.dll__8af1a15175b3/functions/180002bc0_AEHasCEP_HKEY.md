# AEHasCEP(HKEY__ *)

- ea: `0x180002bc0`
- end: `0x180002da0`
- name: `?AEHasCEP@@YAHPEAUHKEY__@@@Z`
- size: `480`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180001d90`

## callees

- `0x180002bc0`
- `0x180007cf2`
- `0x180007d20`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180002ce0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180002ce0`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180002d29`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180002d7b`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180002d29`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180002d7b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180002c47`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180002c7b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180002c47`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180002c7b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002d43`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002d95`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002d43`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002d95`

## pseudocode

```c
__int64 __fastcall AEHasCEP(HKEY hKey)
{
  unsigned int v2; // ebx
  BYTE Data[4]; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cchName; // [rsp+44h] [rbp-BCh] BYREF
  DWORD Type; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hKeya; // [rsp+50h] [rbp-B0h] BYREF
  DWORD cbData; // [rsp+58h] [rbp-A8h] BYREF
  HKEY phkResult; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR Name; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v11[526]; // [rsp+72h] [rbp-8Eh] BYREF

  hKeya = 0;
  phkResult = 0;
  Name = 0;
  v2 = 0;
  memset_0(v11, 0, 0x206u);
  cchName = 0;
  *(_DWORD *)Data = 0;
  cbData = 4;
  Type = 0;
  if ( RegOpenKeyExW(hKey, L"Software\\Policies\\Microsoft\\Cryptography\\PolicyServers", 0, 0x108u, &hKeya) )
    goto LABEL_3;
  if ( !RegQueryValueExW(hKeya, L"Flags", 0, &Type, Data, &cbData) && Type != 4 )
    *(_DWORD *)Data = 0;
  if ( (Data[0] & 2) == 0 )
  {
    cchName = 260;
    if ( !RegEnumKeyExW(hKeya, 0, &Name, &cchName, 0, 0, 0, 0) )
      v2 = 1;
  }
  if ( hKeya )
    RegCloseKey(hKeya);
  if ( !v2 )
  {
LABEL_3:
    if ( (Data[0] & 4) == 0
      && !RegOpenKeyExW(hKey, L"Software\\Microsoft\\Cryptography\\PolicyServers", 0, 0x108u, &phkResult) )
    {
      cchName = 260;
      if ( !RegEnumKeyExW(phkResult, 0, &Name, &cchName, 0, 0, 0, 0) )
        v2 = 1;
      if ( phkResult )
        RegCloseKey(phkResult);
    }
  }
  return v2;
}

```

## disassembly

```asm
0x180002bc0  mov     [rsp-8+arg_8], rbx
0x180002bc5  mov     [rsp-8+arg_10], rsi
0x180002bca  push    rbp
0x180002bcb  push    rdi
0x180002bcc  push    r14
0x180002bce  lea     rbp, [rsp-190h]
0x180002bd6  sub     rsp, 290h
0x180002bdd  mov     rax, cs:__security_cookie
0x180002be4  xor     rax, rsp
0x180002be7  mov     [rbp+1A0h+var_20], rax
0x180002bee  xor     esi, esi
0x180002bf0  mov     rdi, rcx
0x180002bf3  lea     rcx, [rsp+2A0h+var_22E]; void *
0x180002bf8  mov     [rsp+2A0h+hKey], rsi
0x180002bfd  xor     edx, edx; Val
0x180002bff  mov     [rsp+2A0h+var_240], rsi
0x180002c04  mov     r8d, 206h; Size
0x180002c0a  mov     [rsp+2A0h+Name], si
0x180002c0f  mov     ebx, esi
0x180002c11  call    memset_0
0x180002c16  lea     rax, [rsp+2A0h+hKey]
0x180002c1b  mov     [rsp+2A0h+cchName], esi
0x180002c1f  mov     r9d, 108h; samDesired
0x180002c25  mov     [rsp+2A0h+phkResult], rax; phkResult
0x180002c2a  xor     r8d, r8d; ulOptions
0x180002c2d  mov     dword ptr [rsp+2A0h+Data], esi
0x180002c31  lea     rdx, aSoftwarePolici_0; "Software\\Policies\\Microsoft\\Cryptogr"...
0x180002c38  mov     [rsp+2A0h+cbData], 4
0x180002c40  mov     rcx, rdi; hKey
0x180002c43  mov     [rsp+2A0h+Type], esi
0x180002c47  call    cs:__imp_RegOpenKeyExW
0x180002c4d  mov     r14d, 1
0x180002c53  test    eax, eax
0x180002c55  jz      short loc_180002CB8
0x180002c57  test    [rsp+2A0h+Data], 4
0x180002c5c  jnz     short loc_180002C89
0x180002c5e  lea     rax, [rsp+2A0h+var_240]
0x180002c63  mov     r9d, 108h; samDesired
0x180002c69  xor     r8d, r8d; ulOptions
0x180002c6c  mov     [rsp+2A0h+phkResult], rax; phkResult
0x180002c71  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Cryptography\\Poli"...
0x180002c78  mov     rcx, rdi; hKey
0x180002c7b  call    cs:__imp_RegOpenKeyExW
0x180002c81  test    eax, eax
0x180002c83  jz      loc_180002D4E
0x180002c89  mov     eax, ebx
0x180002c8b  mov     rcx, [rbp+1A0h+var_20]
0x180002c92  xor     rcx, rsp; StackCookie
0x180002c95  call    __security_check_cookie
0x180002c9a  lea     r11, [rsp+2A0h+var_10]
0x180002ca2  mov     rbx, [r11+28h]
0x180002ca6  mov     rsi, [r11+30h]
0x180002caa  mov     rsp, r11
0x180002cad  pop     r14
0x180002caf  pop     rdi
0x180002cb0  pop     rbp
0x180002cb1  retn
0x180002cb2  test    ebx, ebx
0x180002cb4  jnz     short loc_180002C89
0x180002cb6  jmp     short loc_180002C57
0x180002cb8  mov     rcx, [rsp+2A0h+hKey]; hKey
0x180002cbd  lea     rax, [rsp+2A0h+cbData]
0x180002cc2  mov     [rsp+2A0h+lpcbData], rax; lpcbData
0x180002cc7  lea     r9, [rsp+2A0h+Type]; lpType
0x180002ccc  lea     rax, [rsp+2A0h+Data]
0x180002cd1  xor     r8d, r8d; lpReserved
0x180002cd4  lea     rdx, aFlags; "Flags"
0x180002cdb  mov     [rsp+2A0h+phkResult], rax; lpData
0x180002ce0  call    cs:__imp_RegQueryValueExW
0x180002ce6  test    eax, eax
0x180002ce8  jnz     short loc_180002CF5
0x180002cea  cmp     [rsp+2A0h+Type], 4
0x180002cef  jz      short loc_180002CF5
0x180002cf1  mov     dword ptr [rsp+2A0h+Data], esi
0x180002cf5  test    [rsp+2A0h+Data], 2
0x180002cfa  jnz     short loc_180002D35
0x180002cfc  mov     rcx, [rsp+2A0h+hKey]; hKey
0x180002d01  lea     r9, [rsp+2A0h+cchName]; lpcchName
0x180002d06  mov     [rsp+2A0h+lpftLastWriteTime], rsi; lpftLastWriteTime
0x180002d0b  lea     r8, [rsp+2A0h+Name]; lpName
0x180002d10  mov     [rsp+2A0h+lpcchClass], rsi; lpcchClass
0x180002d15  xor     edx, edx; dwIndex
0x180002d17  mov     [rsp+2A0h+lpcbData], rsi; lpClass
0x180002d1c  mov     [rsp+2A0h+phkResult], rsi; lpReserved
0x180002d21  mov     [rsp+2A0h+cchName], 104h
0x180002d29  call    cs:__imp_RegEnumKeyExW
0x180002d2f  test    eax, eax
0x180002d31  cmovz   ebx, r14d
0x180002d35  mov     rcx, [rsp+2A0h+hKey]; hKey
0x180002d3a  test    rcx, rcx
0x180002d3d  jz      loc_180002CB2
0x180002d43  call    cs:__imp_RegCloseKey
0x180002d49  jmp     loc_180002CB2
0x180002d4e  mov     rcx, [rsp+2A0h+var_240]; hKey
0x180002d53  lea     r9, [rsp+2A0h+cchName]; lpcchName
0x180002d58  mov     [rsp+2A0h+lpftLastWriteTime], rsi; lpftLastWriteTime
0x180002d5d  lea     r8, [rsp+2A0h+Name]; lpName
0x180002d62  mov     [rsp+2A0h+lpcchClass], rsi; lpcchClass
0x180002d67  xor     edx, edx; dwIndex
0x180002d69  mov     [rsp+2A0h+lpcbData], rsi; lpClass
0x180002d6e  mov     [rsp+2A0h+phkResult], rsi; lpReserved
0x180002d73  mov     [rsp+2A0h+cchName], 104h
0x180002d7b  call    cs:__imp_RegEnumKeyExW
0x180002d81  mov     rcx, [rsp+2A0h+var_240]; hKey
0x180002d86  test    eax, eax
0x180002d88  cmovz   ebx, r14d
0x180002d8c  test    rcx, rcx
0x180002d8f  jz      loc_180002C89
0x180002d95  call    cs:__imp_RegCloseKey
0x180002d9b  jmp     loc_180002C89
```
