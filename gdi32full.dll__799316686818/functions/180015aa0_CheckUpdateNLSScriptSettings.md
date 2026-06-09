# CheckUpdateNLSScriptSettings

- ea: `0x180015aa0`
- end: `0x180015b51`
- name: `CheckUpdateNLSScriptSettings`
- size: `177`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config, installer_update`

## callers

- `0x18000f4b0`
- `0x18000f970`
- `0x180013a50`
- `0x180015dc0`

## callees

- `0x180015aa0`
- `0x1800169c0`
- `0x18007ac50`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLCID` at `0x180015acf`
- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLCID` at `0x180015acf`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x180015af0`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x180015af0`
- `api-ms-win-core-localization-private-l1-1-0!NlsGetCacheUpdateCount` at `0x180015abb`
- `api-ms-win-core-localization-private-l1-1-0!NlsGetCacheUpdateCount` at `0x180015abb`

## pseudocode

```c
__int64 CheckUpdateNLSScriptSettings()
{
  int CacheUpdateCount; // eax
  unsigned int v1; // ebx
  BOOL v2; // eax
  WCHAR LCData[80]; // [rsp+20h] [rbp-B8h] BYREF

  CacheUpdateCount = NlsGetCacheUpdateCount();
  if ( CacheUpdateCount == g_ulNlsUpdateCacheCount )
    return 1;
  g_ulNlsUpdateCacheCount = CacheUpdateCount;
  g_UserLocale = GetUserDefaultLCID();
  v1 = 1;
  v2 = GetLocaleInfoW(0x400u, 0x58u, LCData, 80) && (LCData[7] & 0x800) != 0;
  g_UserBidiLocale = v2;
  if ( ScriptRecordDigitSubstitution(0x400u, &g_DigitSubstitute) < 0 )
    return 0;
  return v1;
}

```

## disassembly

```asm
0x180015aa0  push    rbx
0x180015aa2  sub     rsp, 0D0h
0x180015aa9  mov     rax, cs:__security_cookie
0x180015ab0  xor     rax, rsp
0x180015ab3  mov     [rsp+0D8h+var_18], rax
0x180015abb  call    cs:__imp_NlsGetCacheUpdateCount
0x180015ac1  cmp     eax, cs:g_ulNlsUpdateCacheCount
0x180015ac7  jz      short loc_180015B46
0x180015ac9  mov     cs:g_ulNlsUpdateCacheCount, eax
0x180015acf  call    cs:__imp_GetUserDefaultLCID
0x180015ad5  mov     r9d, 50h ; 'P'; cchData
0x180015adb  lea     r8, [rsp+0D8h+LCData]; lpLCData
0x180015ae0  mov     edx, 58h ; 'X'; LCType
0x180015ae5  mov     cs:g_UserLocale, eax
0x180015aeb  mov     ecx, 400h; Locale
0x180015af0  call    cs:__imp_GetLocaleInfoW
0x180015af6  mov     ebx, 1
0x180015afb  test    eax, eax
0x180015afd  jz      short loc_180015B4D
0x180015aff  mov     eax, 800h
0x180015b04  test    [rsp+0D8h+var_AA], ax
0x180015b09  jz      short loc_180015B4D
0x180015b0b  mov     eax, ebx
0x180015b0d  lea     rdx, g_DigitSubstitute; psds
0x180015b14  mov     cs:g_UserBidiLocale, eax
0x180015b1a  mov     ecx, 400h; Locale
0x180015b1f  call    ScriptRecordDigitSubstitution
0x180015b24  xor     ecx, ecx
0x180015b26  test    eax, eax
0x180015b28  cmovs   ebx, ecx
0x180015b2b  mov     eax, ebx
0x180015b2d  mov     rcx, [rsp+0D8h+var_18]
0x180015b35  xor     rcx, rsp; StackCookie
0x180015b38  call    __security_check_cookie
0x180015b3d  add     rsp, 0D0h
0x180015b44  pop     rbx
0x180015b45  retn
0x180015b46  mov     eax, 1
0x180015b4b  jmp     short loc_180015B2D
0x180015b4d  xor     eax, eax
0x180015b4f  jmp     short loc_180015B0D
```
