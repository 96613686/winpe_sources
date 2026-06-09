# Intl_CreateRegTree(HKEY__ *,HKEY__ *)

- ea: `0x180024da4`
- end: `0x180024f49`
- name: `?Intl_CreateRegTree@@YAKPEAUHKEY__@@0@Z`
- size: `421`
- prototype: `unsigned int __fastcall(HKEY, HKEY)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180024da4`
- `0x1800265bc`
- `0x18002665c`

## callees

- `0x180024c0c`
- `0x180024da4`
- `0x18002a150`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180024ed3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180024ed3`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180024e58`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180024e58`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180024eae`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180024eae`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180024ef5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180024f00`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180024f16`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180024ef5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180024f00`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180024f16`

## pseudocode

```c
unsigned int __fastcall Intl_CreateRegTree(HKEY a1, HKEY a2)
{
  unsigned int result; // eax
  DWORD i; // edi
  LSTATUS v6; // eax
  LSTATUS RegTree; // ebx
  DWORD cchClass; // [rsp+50h] [rbp-B0h] BYREF
  DWORD cchName; // [rsp+54h] [rbp-ACh] BYREF
  HKEY phkResult; // [rsp+58h] [rbp-A8h] BYREF
  DWORD dwDisposition; // [rsp+60h] [rbp-A0h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  WCHAR Name[256]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR Class[264]; // [rsp+270h] [rbp+170h] BYREF

  cchClass = 0;
  cchName = 0;
  dwDisposition = 0;
  phkResult = 0;
  hKey = 0;
  result = Intl_CopyRegKeyValues(a1, a2);
  if ( !result )
  {
    for ( i = 0; ; ++i )
    {
      cchName = 256;
      cchClass = 256;
      v6 = RegEnumKeyExW(a1, i, Name, &cchName, 0, Class, &cchClass, 0);
      RegTree = v6;
      if ( v6 == 259 )
        break;
      if ( v6 )
        return RegTree;
      if ( !RegCreateKeyExW(a2, Name, 0, Class, 0, 0xF003Fu, 0, &phkResult, &dwDisposition) )
      {
        RegTree = RegOpenKeyExW(a1, Name, 0, 0xF003Fu, &hKey);
        if ( RegTree )
        {
          RegCloseKey(phkResult);
          return RegTree;
        }
        RegTree = Intl_CreateRegTree(hKey, phkResult);
        RegCloseKey(hKey);
        RegCloseKey(phkResult);
        if ( RegTree )
          return RegTree;
      }
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180024da4  mov     [rsp-8+arg_10], rbx
0x180024da9  mov     [rsp-8+arg_18], rsi
0x180024dae  push    rbp
0x180024daf  push    rdi
0x180024db0  push    r14
0x180024db2  lea     rbp, [rsp-390h]
0x180024dba  sub     rsp, 490h
0x180024dc1  mov     rax, cs:__security_cookie
0x180024dc8  xor     rax, rsp
0x180024dcb  mov     [rbp+3A0h+var_20], rax
0x180024dd2  mov     r14, rdx
0x180024dd5  mov     [rsp+4A0h+cchClass], 0
0x180024ddd  mov     rsi, rcx
0x180024de0  mov     [rsp+4A0h+cchName], 0
0x180024de8  mov     [rsp+4A0h+dwDisposition], 0
0x180024df0  mov     [rsp+4A0h+phkResult], 0
0x180024df9  mov     [rsp+4A0h+hKey], 0
0x180024e02  call    ?Intl_CopyRegKeyValues@@YAKPEAUHKEY__@@0@Z; Intl_CopyRegKeyValues(HKEY__ *,HKEY__ *)
0x180024e07  test    eax, eax
0x180024e09  jnz     loc_180024F22
0x180024e0f  xor     edi, edi
0x180024e11  mov     [rsp+4A0h+lpftLastWriteTime], 0; lpftLastWriteTime
0x180024e1a  lea     rax, [rsp+4A0h+cchClass]
0x180024e1f  mov     [rsp+4A0h+lpcchClass], rax; lpcchClass
0x180024e24  lea     r9, [rsp+4A0h+cchName]; lpcchName
0x180024e29  lea     rax, [rbp+3A0h+Class]
0x180024e30  mov     [rsp+4A0h+cchName], 100h
0x180024e38  mov     [rsp+4A0h+lpClass], rax; lpClass
0x180024e3d  lea     r8, [rsp+4A0h+Name]; lpName
0x180024e42  mov     edx, edi; dwIndex
0x180024e44  mov     [rsp+4A0h+lpReserved], 0; lpReserved
0x180024e4d  mov     rcx, rsi; hKey
0x180024e50  mov     [rsp+4A0h+cchClass], 100h
0x180024e58  call    cs:__imp_RegEnumKeyExW
0x180024e5e  mov     ebx, eax
0x180024e60  cmp     eax, 103h
0x180024e65  jz      loc_180024F1E
0x180024e6b  test    eax, eax
0x180024e6d  jnz     loc_180024F20
0x180024e73  lea     rax, [rsp+4A0h+dwDisposition]
0x180024e78  xor     r8d, r8d; Reserved
0x180024e7b  mov     [rsp+4A0h+lpdwDisposition], rax; lpdwDisposition
0x180024e80  lea     r9, [rbp+3A0h+Class]; lpClass
0x180024e87  lea     rax, [rsp+4A0h+phkResult]
0x180024e8c  mov     rcx, r14; hKey
0x180024e8f  mov     [rsp+4A0h+lpftLastWriteTime], rax; phkResult
0x180024e94  lea     rdx, [rsp+4A0h+Name]; lpSubKey
0x180024e99  mov     [rsp+4A0h+lpcchClass], 0; lpSecurityAttributes
0x180024ea2  mov     dword ptr [rsp+4A0h+lpClass], 0F003Fh; samDesired
0x180024eaa  mov     dword ptr [rsp+4A0h+lpReserved], ebx; dwOptions
0x180024eae  call    cs:__imp_RegCreateKeyExW
0x180024eb4  test    eax, eax
0x180024eb6  jnz     short loc_180024F0A
0x180024eb8  lea     rax, [rsp+4A0h+hKey]
0x180024ebd  mov     r9d, 0F003Fh; samDesired
0x180024ec3  xor     r8d, r8d; ulOptions
0x180024ec6  mov     [rsp+4A0h+lpReserved], rax; phkResult
0x180024ecb  lea     rdx, [rsp+4A0h+Name]; lpSubKey
0x180024ed0  mov     rcx, rsi; hKey
0x180024ed3  call    cs:__imp_RegOpenKeyExW
0x180024ed9  mov     ebx, eax
0x180024edb  test    eax, eax
0x180024edd  jnz     short loc_180024F11
0x180024edf  mov     rdx, [rsp+4A0h+phkResult]; HKEY
0x180024ee4  mov     rcx, [rsp+4A0h+hKey]; HKEY
0x180024ee9  call    ?Intl_CreateRegTree@@YAKPEAUHKEY__@@0@Z; Intl_CreateRegTree(HKEY__ *,HKEY__ *)
0x180024eee  mov     rcx, [rsp+4A0h+hKey]; hKey
0x180024ef3  mov     ebx, eax
0x180024ef5  call    cs:__imp_RegCloseKey
0x180024efb  mov     rcx, [rsp+4A0h+phkResult]; hKey
0x180024f00  call    cs:__imp_RegCloseKey
0x180024f06  test    ebx, ebx
0x180024f08  jnz     short loc_180024F20
0x180024f0a  inc     edi
0x180024f0c  jmp     loc_180024E11
0x180024f11  mov     rcx, [rsp+4A0h+phkResult]; hKey
0x180024f16  call    cs:__imp_RegCloseKey
0x180024f1c  jmp     short loc_180024F20
0x180024f1e  xor     ebx, ebx
0x180024f20  mov     eax, ebx
0x180024f22  mov     rcx, [rbp+3A0h+var_20]
0x180024f29  xor     rcx, rsp; StackCookie
0x180024f2c  call    __security_check_cookie
0x180024f31  lea     r11, [rsp+4A0h+var_10]
0x180024f39  mov     rbx, [r11+30h]
0x180024f3d  mov     rsi, [r11+38h]
0x180024f41  mov     rsp, r11
0x180024f44  pop     r14
0x180024f46  pop     rdi
0x180024f47  pop     rbp
0x180024f48  retn
```
