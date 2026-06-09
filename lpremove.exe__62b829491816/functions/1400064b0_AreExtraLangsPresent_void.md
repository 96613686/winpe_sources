# AreExtraLangsPresent(void)

- ea: `0x1400064b0`
- end: `0x1400065a4`
- name: `?AreExtraLangsPresent@@YAHXZ`
- size: `244`
- prototype: `_BOOL8(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callers

- `0x14000d8b8`

## callees

- `0x1400064b0`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x14000658c`
- `ADVAPI32!RegCloseKey` at `0x14000658c`
- `ADVAPI32!RegOpenKeyExW` at `0x140006516`
- `ADVAPI32!RegOpenKeyExW` at `0x140006516`
- `ADVAPI32!RegQueryInfoKeyW` at `0x140006579`
- `ADVAPI32!RegQueryInfoKeyW` at `0x140006579`
- `KERNEL32!EnumUILanguagesW` at `0x1400064d5`
- `KERNEL32!EnumUILanguagesW` at `0x1400064d5`

## pseudocode

```c
_BOOL8 AreExtraLangsPresent(void)
{
  LONG_PTR lParam; // [rsp+70h] [rbp+8h] BYREF
  DWORD cSubKeys; // [rsp+78h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+80h] [rbp+18h] BYREF

  LODWORD(lParam) = 0;
  cSubKeys = 0;
  EnumUILanguagesW(EnumUILanguagesProc_CountInstalledLangs, 0xA8u, (LONG_PTR)&lParam);
  if ( (_DWORD)lParam )
  {
    hKey = 0;
    if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\MUI\\UILanguages", 0, 0x20019u, &hKey) )
      RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
    if ( hKey )
      RegCloseKey(hKey);
  }
  return (unsigned int)lParam < cSubKeys;
}

```

## disassembly

```asm
0x1400064b0  sub     rsp, 68h
0x1400064b4  lea     r8, [rsp+68h+lParam]; lParam
0x1400064b9  mov     dword ptr [rsp+68h+lParam], 0
0x1400064c1  mov     edx, 0A8h; dwFlags
0x1400064c6  mov     [rsp+68h+cSubKeys], 0
0x1400064ce  lea     rcx, ?EnumUILanguagesProc_CountInstalledLangs@@YAHPEAG_J@Z; lpUILanguageEnumProc
0x1400064d5  call    cs:__imp_EnumUILanguagesW
0x1400064db  cmp     dword ptr [rsp+68h+lParam], 0
0x1400064e0  jz      loc_140006592
0x1400064e6  lea     rax, [rsp+68h+hKey]
0x1400064ee  mov     [rsp+68h+hKey], 0
0x1400064fa  mov     r9d, 20019h; samDesired
0x140006500  mov     [rsp+68h+phkResult], rax; phkResult
0x140006505  xor     r8d, r8d; ulOptions
0x140006508  lea     rdx, SubKey; "System\\CurrentControlSet\\Control\\MUI"...
0x14000650f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140006516  call    cs:__imp_RegOpenKeyExW
0x14000651c  test    eax, eax
0x14000651e  jnz     short loc_14000657F
0x140006520  mov     rcx, [rsp+68h+hKey]; hKey
0x140006528  lea     rax, [rsp+68h+cSubKeys]
0x14000652d  mov     [rsp+68h+lpftLastWriteTime], 0; lpftLastWriteTime
0x140006536  xor     r9d, r9d; lpReserved
0x140006539  mov     [rsp+68h+lpcbSecurityDescriptor], 0; lpcbSecurityDescriptor
0x140006542  xor     r8d, r8d; lpcchClass
0x140006545  mov     [rsp+68h+lpcbMaxValueLen], 0; lpcbMaxValueLen
0x14000654e  xor     edx, edx; lpClass
0x140006550  mov     [rsp+68h+lpcbMaxValueNameLen], 0; lpcbMaxValueNameLen
0x140006559  mov     [rsp+68h+lpcValues], 0; lpcValues
0x140006562  mov     [rsp+68h+lpcbMaxClassLen], 0; lpcbMaxClassLen
0x14000656b  mov     [rsp+68h+lpcbMaxSubKeyLen], 0; lpcbMaxSubKeyLen
0x140006574  mov     [rsp+68h+phkResult], rax; lpcSubKeys
0x140006579  call    cs:__imp_RegQueryInfoKeyW
0x14000657f  mov     rcx, [rsp+68h+hKey]; hKey
0x140006587  test    rcx, rcx
0x14000658a  jz      short loc_140006592
0x14000658c  call    cs:__imp_RegCloseKey
0x140006592  mov     ecx, [rsp+68h+cSubKeys]
0x140006596  xor     eax, eax
0x140006598  cmp     dword ptr [rsp+68h+lParam], ecx
0x14000659c  setb    al
0x14000659f  add     rsp, 68h
0x1400065a3  retn
```
