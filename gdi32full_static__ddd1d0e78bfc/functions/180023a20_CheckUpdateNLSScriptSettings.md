# CheckUpdateNLSScriptSettings

- ea: `0x180023a20`
- end: `0x180023ae8`
- name: `CheckUpdateNLSScriptSettings`
- size: `200`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config, installer_update`

## callers

- `0x180017c60`
- `0x180018070`
- `0x180021f80`
- `0x180022e60`

## callees

- `0x180023a20`
- `0x180023af0`
- `0x18007f800`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLCID` at `0x180023a59`
- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLCID` at `0x180023a59`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x180023a80`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x180023a80`
- `api-ms-win-core-localization-private-l1-1-0!NlsGetCacheUpdateCount` at `0x180023a3b`
- `api-ms-win-core-localization-private-l1-1-0!NlsGetCacheUpdateCount` at `0x180023a3b`

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
0x180023a20  push    rbx
0x180023a22  sub     rsp, 0D0h
0x180023a29  mov     rax, cs:__security_cookie
0x180023a30  xor     rax, rsp
0x180023a33  mov     [rsp+0D8h+var_18], rax
0x180023a3b  call    cs:__imp_NlsGetCacheUpdateCount
0x180023a42  nop     dword ptr [rax+rax+00h]
0x180023a47  cmp     eax, cs:g_ulNlsUpdateCacheCount
0x180023a4d  jz      loc_180023ADD
0x180023a53  mov     cs:g_ulNlsUpdateCacheCount, eax
0x180023a59  call    cs:__imp_GetUserDefaultLCID
0x180023a60  nop     dword ptr [rax+rax+00h]
0x180023a65  mov     r9d, 50h ; 'P'; cchData
0x180023a6b  lea     r8, [rsp+0D8h+LCData]; lpLCData
0x180023a70  mov     edx, 58h ; 'X'; LCType
0x180023a75  mov     cs:g_UserLocale, eax
0x180023a7b  mov     ecx, 400h; Locale
0x180023a80  call    cs:__imp_GetLocaleInfoW
0x180023a87  nop     dword ptr [rax+rax+00h]
0x180023a8c  mov     ebx, 1
0x180023a91  test    eax, eax
0x180023a93  jz      short loc_180023AE4
0x180023a95  mov     eax, 800h
0x180023a9a  test    [rsp+0D8h+var_AA], ax
0x180023a9f  jz      short loc_180023AE4
0x180023aa1  mov     eax, ebx
0x180023aa3  lea     rdx, g_DigitSubstitute; psds
0x180023aaa  mov     cs:g_UserBidiLocale, eax
0x180023ab0  mov     ecx, 400h; Locale
0x180023ab5  call    ScriptRecordDigitSubstitution
0x180023aba  xor     ecx, ecx
0x180023abc  test    eax, eax
0x180023abe  cmovs   ebx, ecx
0x180023ac1  mov     eax, ebx
0x180023ac3  mov     rcx, [rsp+0D8h+var_18]
0x180023acb  xor     rcx, rsp; StackCookie
0x180023ace  call    __security_check_cookie
0x180023ad3  add     rsp, 0D0h
0x180023ada  pop     rbx
0x180023adb  retn
0x180023add  mov     eax, 1
0x180023ae2  jmp     short loc_180023AC3
0x180023ae4  xor     eax, eax
0x180023ae6  jmp     short loc_180023AA3
```
