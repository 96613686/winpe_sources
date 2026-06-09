# LsapLoadLsaInterfaces

- ea: `0x1400038cc`
- end: `0x140003a65`
- name: `LsapLoadLsaInterfaces`
- size: `409`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x1400031bc`

## callees

- `0x1400020c0`
- `0x1400037b8`
- `0x1400038cc`
- `0x140003c04`
- `0x140006010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x14000399a`
- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x14000399a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000392a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400039ca`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000392a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400039ca`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x140003975`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x140003975`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140003a25`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140003a45`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140003a25`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140003a45`

## string_xrefs

- `0x14000390d`: `System\CurrentControlSet\Control\LsaExtensionConfig\Interfaces`

## pseudocode

```c
__int64 LsapLoadLsaInterfaces()
{
  unsigned int v0; // ebx
  DWORD i; // edi
  LSTATUS v2; // eax
  unsigned int v3; // esi
  __int64 v4; // rbx
  int (__fastcall *v5)(_QWORD, __int64 *); // rax
  DWORD cchName; // [rsp+40h] [rbp-49h] BYREF
  HKEY phkResult; // [rsp+48h] [rbp-41h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-39h] BYREF
  __int64 v10; // [rsp+58h] [rbp-31h]
  __int64 v11; // [rsp+60h] [rbp-29h] BYREF
  WCHAR Name[32]; // [rsp+70h] [rbp-19h] BYREF

  hKey = 0;
  phkResult = 0;
  cchName = 0;
  v10 = 0;
  v0 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\Control\\LsaExtensionConfig\\Interfaces",
         0,
         0x20019u,
         &hKey);
  if ( !v0 )
  {
    for ( i = 0; ; ++i )
    {
      cchName = 32;
      v2 = RegEnumKeyExW(hKey, i, Name, &cchName, 0, 0, 0, 0);
      v0 = v2;
      if ( v2 == 259 )
      {
        v0 = 0;
        break;
      }
      if ( v2 )
        break;
      v3 = wcstol(Name, 0, 10);
      if ( v3 - 1001 <= 0x2326 )
      {
        if ( RegOpenKeyExW(hKey, Name, 0, 0x20019u, &phkResult) )
          goto LABEL_14;
        if ( !(unsigned int)LsapLoadExtensionFromRegistry(phkResult) )
        {
          v4 = v10;
          v11 = 0;
          v5 = *(int (__fastcall **)(_QWORD, __int64 *))(v10 + 80);
          if ( v5 )
          {
            if ( v5(v3, &v11) >= 0 )
            {
              if ( v11 )
                LsapRegisterInterface(v4, v3);
            }
          }
        }
      }
      if ( !phkResult )
        continue;
      RegCloseKey(phkResult);
LABEL_14:
      phkResult = 0;
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v0;
}

```

## disassembly

```asm
0x1400038cc  push    rbp
0x1400038ce  push    rbx
0x1400038cf  push    rsi
0x1400038d0  push    rdi
0x1400038d1  lea     rbp, [rsp-3Fh]
0x1400038d6  sub     rsp, 0C8h
0x1400038dd  mov     rax, cs:__security_cookie
0x1400038e4  xor     rax, rsp
0x1400038e7  mov     [rbp+57h+var_30], rax
0x1400038eb  lea     rax, [rbp+57h+hKey]
0x1400038ef  mov     [rbp+57h+hKey], 0
0x1400038f7  mov     r9d, 20019h; samDesired
0x1400038fd  mov     [rsp+0E0h+phkResult], rax; phkResult
0x140003902  xor     r8d, r8d; ulOptions
0x140003905  mov     [rbp+57h+var_98], 0
0x14000390d  lea     rdx, SubKey; "System\\CurrentControlSet\\Control\\Lsa"...
0x140003914  mov     [rbp+57h+cchName], 0
0x14000391b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140003922  mov     [rbp+57h+var_88], 0
0x14000392a  call    cs:__imp_RegOpenKeyExW
0x140003930  mov     ebx, eax
0x140003932  test    eax, eax
0x140003934  jnz     loc_140003A3C
0x14000393a  xor     edi, edi
0x14000393c  mov     rcx, [rbp+57h+hKey]; hKey
0x140003940  lea     r9, [rbp+57h+cchName]; lpcchName
0x140003944  mov     [rsp+0E0h+lpftLastWriteTime], 0; lpftLastWriteTime
0x14000394d  lea     r8, [rbp+57h+Name]; lpName
0x140003951  mov     [rsp+0E0h+lpcchClass], 0; lpcchClass
0x14000395a  mov     edx, edi; dwIndex
0x14000395c  mov     [rsp+0E0h+lpClass], 0; lpClass
0x140003965  mov     [rsp+0E0h+phkResult], 0; lpReserved
0x14000396e  mov     [rbp+57h+cchName], 20h ; ' '
0x140003975  call    cs:__imp_RegEnumKeyExW
0x14000397b  mov     ebx, eax
0x14000397d  cmp     eax, 103h
0x140003982  jz      loc_140003A3A
0x140003988  test    eax, eax
0x14000398a  jnz     loc_140003A3C
0x140003990  xor     edx, edx; EndPtr
0x140003992  lea     r8d, [rax+0Ah]; Radix
0x140003996  lea     rcx, [rbp+57h+Name]; String
0x14000399a  call    cs:__imp_wcstol
0x1400039a0  mov     esi, eax
0x1400039a2  lea     ecx, [rax-3E9h]
0x1400039a8  cmp     ecx, 2326h
0x1400039ae  ja      short loc_140003A1C
0x1400039b0  mov     rcx, [rbp+57h+hKey]; hKey
0x1400039b4  lea     rax, [rbp+57h+var_98]
0x1400039b8  mov     r9d, 20019h; samDesired
0x1400039be  mov     [rsp+0E0h+phkResult], rax; phkResult
0x1400039c3  xor     r8d, r8d; ulOptions
0x1400039c6  lea     rdx, [rbp+57h+Name]; lpSubKey
0x1400039ca  call    cs:__imp_RegOpenKeyExW
0x1400039d0  test    eax, eax
0x1400039d2  jnz     short loc_140003A2B
0x1400039d4  mov     rcx, [rbp+57h+var_98]; hKey
0x1400039d8  lea     rdx, [rbp+57h+var_88]
0x1400039dc  call    LsapLoadExtensionFromRegistry
0x1400039e1  test    eax, eax
0x1400039e3  jnz     short loc_140003A1C
0x1400039e5  mov     rbx, [rbp+57h+var_88]
0x1400039e9  mov     [rbp+57h+var_80], 0
0x1400039f1  mov     rax, [rbx+50h]
0x1400039f5  test    rax, rax
0x1400039f8  jz      short loc_140003A1C
0x1400039fa  lea     rdx, [rbp+57h+var_80]
0x1400039fe  mov     ecx, esi
0x140003a00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003a05  test    eax, eax
0x140003a07  js      short loc_140003A1C
0x140003a09  mov     r8, [rbp+57h+var_80]
0x140003a0d  test    r8, r8
0x140003a10  jz      short loc_140003A1C
0x140003a12  mov     edx, esi
0x140003a14  mov     rcx, rbx
0x140003a17  call    LsapRegisterInterface
0x140003a1c  mov     rcx, [rbp+57h+var_98]; hKey
0x140003a20  test    rcx, rcx
0x140003a23  jz      short loc_140003A33
0x140003a25  call    cs:__imp_RegCloseKey
0x140003a2b  mov     [rbp+57h+var_98], 0
0x140003a33  inc     edi
0x140003a35  jmp     loc_14000393C
0x140003a3a  xor     ebx, ebx
0x140003a3c  mov     rcx, [rbp+57h+hKey]; hKey
0x140003a40  test    rcx, rcx
0x140003a43  jz      short loc_140003A4B
0x140003a45  call    cs:__imp_RegCloseKey
0x140003a4b  mov     eax, ebx
0x140003a4d  mov     rcx, [rbp+57h+var_30]
0x140003a51  xor     rcx, rsp; StackCookie
0x140003a54  call    __security_check_cookie
0x140003a59  add     rsp, 0C8h
0x140003a60  pop     rdi
0x140003a61  pop     rsi
0x140003a62  pop     rbx
0x140003a63  pop     rbp
0x140003a64  retn
```
