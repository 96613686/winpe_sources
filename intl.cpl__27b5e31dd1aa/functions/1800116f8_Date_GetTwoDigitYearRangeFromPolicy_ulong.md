# Date_GetTwoDigitYearRangeFromPolicy(ulong)

- ea: `0x1800116f8`
- end: `0x1800117f3`
- name: `?Date_GetTwoDigitYearRangeFromPolicy@@YAHK@Z`
- size: `251`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180011590`

## callees

- `0x1800062b0`
- `0x1800116f8`
- `0x18002a150`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001177b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001177b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800117aa`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800117aa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800117c7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800117c7`

## pseudocode

```c
_BOOL8 __fastcall Date_GetTwoDigitYearRangeFromPolicy(unsigned int a1)
{
  BOOL v2; // ebx
  DWORD Type; // [rsp+30h] [rbp-D0h] BYREF
  DWORD cbData; // [rsp+34h] [rbp-CCh] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  BYTE Data[272]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR ValueName[264]; // [rsp+150h] [rbp+50h] BYREF

  hKey = 0;
  cbData = 260;
  Type = 0;
  if ( StringCchPrintfW(ValueName, 0x104u, L"%d", a1) < 0 )
    return 0;
  v2 = 0;
  if ( !RegOpenKeyExW(
          HKEY_CURRENT_USER,
          L"Software\\Policies\\Microsoft\\Control Panel\\International\\Calendars\\TwoDigitYearMax",
          0,
          1u,
          &hKey) )
  {
    if ( !RegQueryValueExW(hKey, ValueName, 0, &Type, Data, &cbData) && Type == 1 )
      v2 = cbData > 2;
    RegCloseKey(hKey);
  }
  return v2;
}

```

## disassembly

```asm
0x1800116f8  mov     [rsp-8+arg_8], rbx
0x1800116fd  mov     [rsp-8+arg_10], rdi
0x180011702  push    rbp
0x180011703  lea     rbp, [rsp-270h]
0x18001170b  sub     rsp, 370h
0x180011712  mov     rax, cs:__security_cookie
0x180011719  xor     rax, rsp
0x18001171c  mov     [rbp+270h+var_10], rax
0x180011723  mov     edx, 104h; unsigned __int64
0x180011728  mov     [rsp+370h+hKey], 0
0x180011731  mov     r9d, ecx
0x180011734  mov     [rsp+370h+cbData], edx
0x180011738  lea     rcx, [rbp+270h+ValueName]; unsigned __int16 *
0x18001173c  mov     [rsp+370h+Type], 0
0x180011744  lea     r8, aD; "%d"
0x18001174b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180011750  test    eax, eax
0x180011752  jns     short loc_180011758
0x180011754  xor     eax, eax
0x180011756  jmp     short loc_1800117CF
0x180011758  lea     rax, [rsp+370h+hKey]
0x18001175d  xor     ebx, ebx
0x18001175f  xor     r8d, r8d; ulOptions
0x180011762  mov     [rsp+370h+phkResult], rax; phkResult
0x180011767  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft\\Control "...
0x18001176e  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180011775  lea     edi, [rbx+1]
0x180011778  mov     r9d, edi; samDesired
0x18001177b  call    cs:__imp_RegOpenKeyExW
0x180011781  test    eax, eax
0x180011783  jnz     short loc_1800117CD
0x180011785  mov     rcx, [rsp+370h+hKey]; hKey
0x18001178a  lea     rax, [rsp+370h+cbData]
0x18001178f  mov     [rsp+370h+lpcbData], rax; lpcbData
0x180011794  lea     r9, [rsp+370h+Type]; lpType
0x180011799  lea     rax, [rsp+370h+Data]
0x18001179e  xor     r8d, r8d; lpReserved
0x1800117a1  lea     rdx, [rbp+270h+ValueName]; lpValueName
0x1800117a5  mov     [rsp+370h+phkResult], rax; lpData
0x1800117aa  call    cs:__imp_RegQueryValueExW
0x1800117b0  test    eax, eax
0x1800117b2  jnz     short loc_1800117C2
0x1800117b4  cmp     [rsp+370h+Type], edi
0x1800117b8  jnz     short loc_1800117C2
0x1800117ba  cmp     [rsp+370h+cbData], 2
0x1800117bf  cmova   ebx, edi
0x1800117c2  mov     rcx, [rsp+370h+hKey]; hKey
0x1800117c7  call    cs:__imp_RegCloseKey
0x1800117cd  mov     eax, ebx
0x1800117cf  mov     rcx, [rbp+270h+var_10]
0x1800117d6  xor     rcx, rsp; StackCookie
0x1800117d9  call    __security_check_cookie
0x1800117de  lea     r11, [rsp+370h+var_s0]
0x1800117e6  mov     rbx, [r11+18h]
0x1800117ea  mov     rdi, [r11+20h]
0x1800117ee  mov     rsp, r11
0x1800117f1  pop     rbp
0x1800117f2  retn
```
