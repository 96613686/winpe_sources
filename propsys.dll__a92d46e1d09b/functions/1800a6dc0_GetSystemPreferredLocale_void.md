# GetSystemPreferredLocale(void)

- ea: `0x1800a6dc0`
- end: `0x1800a6e6b`
- name: `?GetSystemPreferredLocale@@YAKXZ`
- size: `171`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18006b87c`

## callees

- `0x18006ed20`
- `0x1800a6dc0`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!ResolveLocaleName` at `0x1800a6e24`
- `api-ms-win-core-localization-l1-2-0!ResolveLocaleName` at `0x1800a6e24`
- `api-ms-win-core-localization-l1-2-0!LocaleNameToLCID` at `0x1800a6e35`
- `api-ms-win-core-localization-l1-2-0!LocaleNameToLCID` at `0x1800a6e35`
- `api-ms-win-core-localization-l1-2-0!GetSystemDefaultLCID` at `0x1800a6e4d`
- `api-ms-win-core-localization-l1-2-0!GetSystemDefaultLCID` at `0x1800a6e4d`
- `api-ms-win-core-localization-l1-2-0!GetSystemPreferredUILanguages` at `0x1800a6e00`
- `api-ms-win-core-localization-l1-2-0!GetSystemPreferredUILanguages` at `0x1800a6e00`

## pseudocode

```c
unsigned int GetSystemPreferredLocale(void)
{
  unsigned int result; // eax
  ULONG pulNumLanguages; // [rsp+20h] [rbp-2D8h] BYREF
  ULONG pcchLanguagesBuffer[3]; // [rsp+24h] [rbp-2D4h] BYREF
  WCHAR LocaleName[88]; // [rsp+30h] [rbp-2C8h] BYREF
  WCHAR pwszLanguagesBuffer[256]; // [rsp+E0h] [rbp-218h] BYREF

  pulNumLanguages = 0;
  pcchLanguagesBuffer[0] = 256;
  if ( !GetSystemPreferredUILanguages(8u, &pulNumLanguages, pwszLanguagesBuffer, pcchLanguagesBuffer)
    || !pulNumLanguages
    || ResolveLocaleName(pwszLanguagesBuffer, LocaleName, 85) <= 0 )
  {
    return GetSystemDefaultLCID();
  }
  result = LocaleNameToLCID(LocaleName, 0);
  if ( result == 4096 )
    return 127;
  if ( !result )
    return GetSystemDefaultLCID();
  return result;
}

```

## disassembly

```asm
0x1800a6dc0  sub     rsp, 2F8h
0x1800a6dc7  mov     rax, cs:__security_cookie
0x1800a6dce  xor     rax, rsp
0x1800a6dd1  mov     [rsp+2F8h+var_18], rax
0x1800a6dd9  lea     r9, [rsp+2F8h+pcchLanguagesBuffer]; pcchLanguagesBuffer
0x1800a6dde  mov     [rsp+2F8h+pulNumLanguages], 0
0x1800a6de6  lea     r8, [rsp+2F8h+pwszLanguagesBuffer]; pwszLanguagesBuffer
0x1800a6dee  mov     [rsp+2F8h+pcchLanguagesBuffer], 100h
0x1800a6df6  lea     rdx, [rsp+2F8h+pulNumLanguages]; pulNumLanguages
0x1800a6dfb  mov     ecx, 8; dwFlags
0x1800a6e00  call    cs:__imp_GetSystemPreferredUILanguages
0x1800a6e06  test    eax, eax
0x1800a6e08  jz      short loc_1800A6E4D
0x1800a6e0a  cmp     [rsp+2F8h+pulNumLanguages], 0
0x1800a6e0f  jbe     short loc_1800A6E4D
0x1800a6e11  mov     r8d, 55h ; 'U'; cchLocaleName
0x1800a6e17  lea     rdx, [rsp+2F8h+LocaleName]; lpLocaleName
0x1800a6e1c  lea     rcx, [rsp+2F8h+pwszLanguagesBuffer]; lpNameToResolve
0x1800a6e24  call    cs:__imp_ResolveLocaleName
0x1800a6e2a  test    eax, eax
0x1800a6e2c  jle     short loc_1800A6E4D
0x1800a6e2e  xor     edx, edx; dwFlags
0x1800a6e30  lea     rcx, [rsp+2F8h+LocaleName]; lpName
0x1800a6e35  call    cs:__imp_LocaleNameToLCID
0x1800a6e3b  cmp     eax, 1000h
0x1800a6e40  jnz     short loc_1800A6E49
0x1800a6e42  mov     eax, 7Fh
0x1800a6e47  jmp     short loc_1800A6E53
0x1800a6e49  test    eax, eax
0x1800a6e4b  jnz     short loc_1800A6E53
0x1800a6e4d  call    cs:__imp_GetSystemDefaultLCID
0x1800a6e53  mov     rcx, [rsp+2F8h+var_18]
0x1800a6e5b  xor     rcx, rsp; StackCookie
0x1800a6e5e  call    __security_check_cookie
0x1800a6e63  add     rsp, 2F8h
0x1800a6e6a  retn
```
