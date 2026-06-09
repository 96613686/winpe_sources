# ChangeFontLocaleSettings

- ea: `0x18000739c`
- end: `0x180007519`
- name: `ChangeFontLocaleSettings`
- size: `381`
- prototype: `__int64 __fastcall(LCID Locale)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update`

## callers

- `0x1800245e0`

## callees

- `0x18000739c`
- `0x180007520`
- `0x180007adc`
- `0x180007cec`
- `0x18002a150`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007481`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007481`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x180007477`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x180007477`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000742c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000745d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000742c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000745d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800074ca`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800074da`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002a5be`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002a5cf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800074ca`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800074da`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002a5be`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002a5cf`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x1800073df`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x1800073df`
- `SETUPAPI!SetupCloseInfFile` at `0x1800074e5`
- `SETUPAPI!SetupCloseInfFile` at `0x1800074e5`

## pseudocode

```c
__int64 __fastcall ChangeFontLocaleSettings(LCID Locale)
{
  unsigned int AnsiCpString; // ebx
  DWORD LastError; // eax
  HKEY hKey; // [rsp+30h] [rbp-268h] BYREF
  HKEY phkResult; // [rsp+38h] [rbp-260h] BYREF
  HINF InfHandle; // [rsp+40h] [rbp-258h] BYREF
  WCHAR LCData[8]; // [rsp+48h] [rbp-250h] BYREF
  unsigned __int16 v9[12]; // [rsp+58h] [rbp-240h] BYREF
  WCHAR Buffer[264]; // [rsp+70h] [rbp-228h] BYREF

  hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  phkResult = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  InfHandle = (HINF)-1LL;
  if ( GetSystemWindowsDirectoryW(Buffer, 0x104u) - 1 <= 0x103 )
  {
    AnsiCpString = LoadFontInfFile(Buffer, &InfHandle);
    if ( AnsiCpString )
      return AnsiCpString;
    AnsiCpString = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System", 0, 0xF003Fu, &phkResult);
    if ( !AnsiCpString )
    {
      AnsiCpString = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software", 0, 0xF003Fu, &hKey);
      if ( !AnsiCpString )
      {
        if ( !GetLocaleInfoW(Locale, 0xBu, LCData, 6) )
        {
          LastError = GetLastError();
LABEL_9:
          AnsiCpString = LastError;
          goto LABEL_10;
        }
        AnsiCpString = CreateAnsiCpString(Locale, v9);
        if ( !AnsiCpString )
        {
          LastError = SetFontLocaleSettings(phkResult, LCData);
          goto LABEL_9;
        }
      }
    }
LABEL_10:
    if ( hKey != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
      RegCloseKey(hKey);
    if ( phkResult != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
      RegCloseKey(phkResult);
    SetupCloseInfFile(InfHandle);
    return AnsiCpString;
  }
  return 1359;
}

```

## disassembly

```asm
0x18000739c  mov     [rsp+arg_8], rbx
0x1800073a1  mov     [rsp+arg_10], rsi
0x1800073a6  push    rdi
0x1800073a7  sub     rsp, 290h
0x1800073ae  mov     rax, cs:__security_cookie
0x1800073b5  xor     rax, rsp
0x1800073b8  mov     [rsp+298h+var_18], rax
0x1800073c0  mov     edi, ecx
0x1800073c2  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800073c6  mov     [rsp+298h+hKey], rsi
0x1800073cb  mov     [rsp+298h+var_260], rsi
0x1800073d0  mov     [rsp+298h+InfHandle], rsi
0x1800073d5  mov     edx, 104h; uSize
0x1800073da  lea     rcx, [rsp+298h+Buffer]; lpBuffer
0x1800073df  call    cs:__imp_GetSystemWindowsDirectoryW
0x1800073e5  dec     eax
0x1800073e7  cmp     eax, 103h
0x1800073ec  ja      loc_1800074EF
0x1800073f2  lea     rdx, [rsp+298h+InfHandle]
0x1800073f7  lea     rcx, [rsp+298h+Buffer]
0x1800073fc  call    LoadFontInfFile
0x180007401  mov     ebx, eax
0x180007403  test    eax, eax
0x180007405  jnz     loc_1800074EB
0x18000740b  lea     rax, [rsp+298h+var_260]
0x180007410  mov     [rsp+298h+phkResult], rax; phkResult
0x180007415  mov     r9d, 0F003Fh; samDesired
0x18000741b  xor     r8d, r8d; ulOptions
0x18000741e  lea     rdx, SubKey; "System"
0x180007425  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000742c  call    cs:__imp_RegOpenKeyExW
0x180007432  mov     ebx, eax
0x180007434  test    eax, eax
0x180007436  jnz     loc_1800074C0
0x18000743c  lea     rax, [rsp+298h+hKey]
0x180007441  mov     [rsp+298h+phkResult], rax; phkResult
0x180007446  mov     r9d, 0F003Fh; samDesired
0x18000744c  xor     r8d, r8d; ulOptions
0x18000744f  lea     rdx, aSoftware; "Software"
0x180007456  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000745d  call    cs:__imp_RegOpenKeyExW
0x180007463  mov     ebx, eax
0x180007465  test    eax, eax
0x180007467  jnz     short loc_1800074C0
0x180007469  lea     r9d, [rsi+7]; cchData
0x18000746d  lea     r8, [rsp+298h+LCData]; lpLCData
0x180007472  lea     edx, [rsi+0Ch]; LCType
0x180007475  mov     ecx, edi; Locale
0x180007477  call    cs:__imp_GetLocaleInfoW
0x18000747d  test    eax, eax
0x18000747f  jnz     short loc_180007489
0x180007481  call    cs:__imp_GetLastError
0x180007487  jmp     short loc_1800074BE
0x180007489  lea     rdx, [rsp+298h+var_240]; unsigned __int16 *
0x18000748e  mov     ecx, edi; Locale
0x180007490  call    CreateAnsiCpString
0x180007495  mov     ebx, eax
0x180007497  test    eax, eax
0x180007499  jnz     short loc_1800074C0
0x18000749b  lea     rax, [rsp+298h+LCData]
0x1800074a0  mov     [rsp+298h+phkResult], rax; psz
0x1800074a5  lea     r9, [rsp+298h+var_240]
0x1800074aa  mov     r8, [rsp+298h+InfHandle]
0x1800074af  mov     rdx, [rsp+298h+hKey]
0x1800074b4  mov     rcx, [rsp+298h+var_260]; hKey
0x1800074b9  call    SetFontLocaleSettings
0x1800074be  mov     ebx, eax
0x1800074c0  mov     rcx, [rsp+298h+hKey]; hKey
0x1800074c5  cmp     rcx, rsi
0x1800074c8  jz      short loc_1800074D0
0x1800074ca  call    cs:__imp_RegCloseKey
0x1800074d0  mov     rcx, [rsp+298h+var_260]; hKey
0x1800074d5  cmp     rcx, rsi
0x1800074d8  jz      short loc_1800074E0
0x1800074da  call    cs:__imp_RegCloseKey
0x1800074e0  mov     rcx, [rsp+298h+InfHandle]; InfHandle
0x1800074e5  call    cs:__imp_SetupCloseInfFile
0x1800074eb  mov     eax, ebx
0x1800074ed  jmp     short loc_1800074F4
0x1800074ef  mov     eax, 54Fh
0x1800074f4  mov     rcx, [rsp+298h+var_18]
0x1800074fc  xor     rcx, rsp; StackCookie
0x1800074ff  call    __security_check_cookie
0x180007504  lea     r11, [rsp+298h+var_8]
0x18000750c  mov     rbx, [r11+18h]
0x180007510  mov     rsi, [r11+20h]
0x180007514  mov     rsp, r11
0x180007517  pop     rdi
0x180007518  retn
0x18002a5ab  push    rbp
0x18002a5ad  sub     rsp, 30h
0x18002a5b1  mov     rbp, rdx
0x18002a5b4  mov     rcx, [rbp+30h]; hKey
0x18002a5b8  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18002a5bc  jz      short loc_18002A5C5
0x18002a5be  call    cs:__imp_RegCloseKey
0x18002a5c4  nop
0x18002a5c5  mov     rcx, [rbp+38h]; hKey
0x18002a5c9  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18002a5cd  jz      short loc_18002A5D6
0x18002a5cf  call    cs:__imp_RegCloseKey
0x18002a5d5  nop
0x18002a5d6  add     rsp, 30h
0x18002a5da  pop     rbp
0x18002a5db  retn
```
