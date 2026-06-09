# Region_RevertTempDigitSubst(void)

- ea: `0x18001f834`
- end: `0x18001f922`
- name: `?Region_RevertTempDigitSubst@@YAXXZ`
- size: `238`
- prototype: `void(void)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18001e340`
- `0x18001ebc8`
- `0x18001f70c`

## callees

- `0x18001f834`
- `0x18002a150`

## import_xrefs

- `SHLWAPI!StrToIntW` at `0x18001f881`
- `SHLWAPI!StrToIntW` at `0x18001f890`
- `SHLWAPI!StrToIntW` at `0x18001f881`
- `SHLWAPI!StrToIntW` at `0x18001f890`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoEx` at `0x18001f86e`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoEx` at `0x18001f8db`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoEx` at `0x18001f86e`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoEx` at `0x18001f8db`
- `api-ms-win-core-localization-l1-2-0!SetLocaleInfoW` at `0x18001f8ab`
- `api-ms-win-core-localization-l1-2-0!SetLocaleInfoW` at `0x18001f909`
- `api-ms-win-core-localization-l1-2-0!SetLocaleInfoW` at `0x18001f8ab`
- `api-ms-win-core-localization-l1-2-0!SetLocaleInfoW` at `0x18001f909`
- `KERNEL32!lstrcmpiW` at `0x18001f8f1`
- `KERNEL32!lstrcmpiW` at `0x18001f8f1`

## pseudocode

```c
void Region_RevertTempDigitSubst(void)
{
  int v0; // ebx
  WCHAR LCData; // [rsp+20h] [rbp-38h] BYREF
  WCHAR String1[12]; // [rsp+28h] [rbp-30h] BYREF

  if ( GetLocaleInfoEx(*(LPCWSTR *)(*((_QWORD *)g_localeInfo + g_savedLocaleIndex) + 8LL), 0x1014u, &LCData, 3) )
  {
    v0 = StrToIntW(&LCData);
    if ( v0 == StrToIntW(&g_szDigitSubstitution) || SetLocaleInfoW(0x400u, 0x1014u, &g_szDigitSubstitution) )
    {
      if ( GetLocaleInfoEx(*(LPCWSTR *)(*((_QWORD *)g_localeInfo + g_savedLocaleIndex) + 8LL), 0x13u, String1, 12) )
      {
        if ( lstrcmpiW(String1, &g_szNativeDigits) )
          SetLocaleInfoW(0x400u, 0x13u, &g_szNativeDigits);
      }
    }
  }
}

```

## disassembly

```asm
0x18001f834  push    rbx
0x18001f836  sub     rsp, 50h
0x18001f83a  mov     rax, cs:__security_cookie
0x18001f841  xor     rax, rsp
0x18001f844  mov     [rsp+58h+var_18], rax
0x18001f849  mov     ecx, cs:?g_savedLocaleIndex@@3KA; ulong g_savedLocaleIndex
0x18001f84f  lea     r8, [rsp+58h+LCData]; lpLCData
0x18001f854  mov     rax, cs:?g_localeInfo@@3PEAPEAULocaleInfo@@EA; LocaleInfo * * g_localeInfo
0x18001f85b  mov     r9d, 3; cchData
0x18001f861  mov     edx, 1014h; LCType
0x18001f866  mov     rcx, [rax+rcx*8]
0x18001f86a  mov     rcx, [rcx+8]; lpLocaleName
0x18001f86e  call    cs:__imp_GetLocaleInfoEx
0x18001f874  test    eax, eax
0x18001f876  jz      loc_18001F90F
0x18001f87c  lea     rcx, [rsp+58h+LCData]; pszSrc
0x18001f881  call    cs:__imp_StrToIntW
0x18001f887  lea     rcx, ?g_szDigitSubstitution@@3PAGA; pszSrc
0x18001f88e  mov     ebx, eax
0x18001f890  call    cs:__imp_StrToIntW
0x18001f896  cmp     ebx, eax
0x18001f898  jz      short loc_18001F8B5
0x18001f89a  lea     r8, ?g_szDigitSubstitution@@3PAGA; lpLCData
0x18001f8a1  mov     edx, 1014h; LCType
0x18001f8a6  mov     ecx, 400h; Locale
0x18001f8ab  call    cs:__imp_SetLocaleInfoW
0x18001f8b1  test    eax, eax
0x18001f8b3  jz      short loc_18001F90F
0x18001f8b5  mov     ecx, cs:?g_savedLocaleIndex@@3KA; ulong g_savedLocaleIndex
0x18001f8bb  lea     r8, [rsp+58h+String1]; lpLCData
0x18001f8c0  mov     rax, cs:?g_localeInfo@@3PEAPEAULocaleInfo@@EA; LocaleInfo * * g_localeInfo
0x18001f8c7  mov     r9d, 0Ch; cchData
0x18001f8cd  mov     rcx, [rax+rcx*8]
0x18001f8d1  lea     ebx, [r9+7]
0x18001f8d5  mov     edx, ebx; LCType
0x18001f8d7  mov     rcx, [rcx+8]; lpLocaleName
0x18001f8db  call    cs:__imp_GetLocaleInfoEx
0x18001f8e1  test    eax, eax
0x18001f8e3  jz      short loc_18001F90F
0x18001f8e5  lea     rdx, ?g_szNativeDigits@@3PAGA; lpString2
0x18001f8ec  lea     rcx, [rsp+58h+String1]; lpString1
0x18001f8f1  call    cs:__imp_lstrcmpiW
0x18001f8f7  test    eax, eax
0x18001f8f9  jz      short loc_18001F90F
0x18001f8fb  lea     r8, ?g_szNativeDigits@@3PAGA; lpLCData
0x18001f902  mov     edx, ebx; LCType
0x18001f904  mov     ecx, 400h; Locale
0x18001f909  call    cs:__imp_SetLocaleInfoW
0x18001f90f  mov     rcx, [rsp+58h+var_18]
0x18001f914  xor     rcx, rsp; StackCookie
0x18001f917  call    __security_check_cookie
0x18001f91c  add     rsp, 50h
0x18001f920  pop     rbx
0x18001f921  retn
```
