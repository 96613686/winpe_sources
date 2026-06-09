# Region_RevertChanges(void)

- ea: `0x18001f70c`
- end: `0x18001f82d`
- name: `?Region_RevertChanges@@YAHXZ`
- size: `289`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x18001e340`

## callees

- `0x18000fd7c`
- `0x180012dc8`
- `0x18001ab90`
- `0x18001f70c`
- `0x18001f834`
- `0x1800217a4`
- `0x180025bec`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!SetLocaleInfoW` at `0x18001f79a`
- `api-ms-win-core-localization-l1-2-0!SetLocaleInfoW` at `0x18001f7b1`
- `api-ms-win-core-localization-l1-2-0!SetLocaleInfoW` at `0x18001f7c8`
- `api-ms-win-core-localization-l1-2-0!SetLocaleInfoW` at `0x18001f7df`
- `api-ms-win-core-localization-l1-2-0!SetLocaleInfoW` at `0x18001f79a`
- `api-ms-win-core-localization-l1-2-0!SetLocaleInfoW` at `0x18001f7b1`
- `api-ms-win-core-localization-l1-2-0!SetLocaleInfoW` at `0x18001f7c8`
- `api-ms-win-core-localization-l1-2-0!SetLocaleInfoW` at `0x18001f7df`
- `KERNEL32!NlsUpdateLocale` at `0x18001f813`
- `KERNEL32!NlsUpdateLocale` at `0x18001f813`
- `USER32!SetCursor` at `0x18001f722`
- `USER32!SetCursor` at `0x18001f81c`
- `USER32!SetCursor` at `0x18001f722`
- `USER32!SetCursor` at `0x18001f81c`
- `USER32!LoadCursorW` at `0x18001f719`
- `USER32!LoadCursorW` at `0x18001f719`

## pseudocode

```c
__int64 Region_RevertChanges(void)
{
  HCURSOR CursorW; // rax
  HCURSOR v1; // rax
  char v2; // dl
  HCURSOR v3; // rbx

  CursorW = LoadCursorW(0, (LPCWSTR)0x7F02);
  v1 = SetCursor(CursorW);
  v2 = g_dwCustLastChange;
  v3 = v1;
  if ( (g_dwCustLastChange & 0x10) != 0 && UserLocaleIndex != dword_18003C438 )
  {
    Intl_InstallUserLocale(dword_18003C438);
    UserLocaleIndex = dword_18003C438;
    RegUserLocaleIndex = dword_18003C438;
    Input_InstallLayout(0, *(LPCWSTR *)(*((_QWORD *)g_localeInfo + dword_18003C438) + 8LL), 0);
    v2 = g_dwCustLastChange;
    Verified_Regional_Chg = 31;
  }
  if ( (v2 & 8) != 0 )
  {
    SetLocaleInfoW(0x400u, 0x1009u, &word_18003C290);
    SetLocaleInfoW(0x400u, 0x20u, &word_18003C2A0);
    SetLocaleInfoW(0x400u, 0x1Fu, &word_18003C340);
    SetLocaleInfoW(0x400u, 0x100Cu, &word_18003C3E4);
  }
  Currency_RestoreValues();
  Time_RestoreValues();
  Number_RestoreValues();
  Region_RevertTempDigitSubst();
  NlsUpdateLocale(*(_QWORD *)(*((_QWORD *)g_localeInfo + RegUserLocaleIndex) + 8LL), 4);
  SetCursor(v3);
  return 1;
}

```

## disassembly

```asm
0x18001f70c  push    rbx
0x18001f70e  sub     rsp, 20h
0x18001f712  mov     edx, 7F02h; lpCursorName
0x18001f717  xor     ecx, ecx; hInstance
0x18001f719  call    cs:__imp_LoadCursorW
0x18001f71f  mov     rcx, rax; hCursor
0x18001f722  call    cs:__imp_SetCursor
0x18001f728  mov     edx, cs:?g_dwCustLastChange@@3KA; ulong g_dwCustLastChange
0x18001f72e  mov     rbx, rax
0x18001f731  test    dl, 10h
0x18001f734  jz      short loc_18001F784
0x18001f736  mov     ecx, cs:dword_18003C438; unsigned int
0x18001f73c  cmp     cs:?UserLocaleIndex@@3KA, ecx; ulong UserLocaleIndex
0x18001f742  jz      short loc_18001F784
0x18001f744  call    ?Intl_InstallUserLocale@@YAHK@Z; Intl_InstallUserLocale(ulong)
0x18001f749  mov     ecx, cs:dword_18003C438
0x18001f74f  xor     r8d, r8d; unsigned int
0x18001f752  mov     rax, cs:?g_localeInfo@@3PEAPEAULocaleInfo@@EA; LocaleInfo * * g_localeInfo
0x18001f759  mov     cs:?UserLocaleIndex@@3KA, ecx; ulong UserLocaleIndex
0x18001f75f  mov     cs:?RegUserLocaleIndex@@3KA, ecx; ulong RegUserLocaleIndex
0x18001f765  mov     rdx, [rax+rcx*8]
0x18001f769  xor     ecx, ecx; hWnd
0x18001f76b  mov     rdx, [rdx+8]; lpLocaleName
0x18001f76f  call    ?Input_InstallLayout@@YAHPEAUHWND__@@PEBGK@Z; Input_InstallLayout(HWND__ *,ushort const *,ulong)
0x18001f774  mov     edx, cs:?g_dwCustLastChange@@3KA; ulong g_dwCustLastChange
0x18001f77a  mov     cs:?Verified_Regional_Chg@@3HA, 1Fh; int Verified_Regional_Chg
0x18001f784  test    dl, 8
0x18001f787  jz      short loc_18001F7E5
0x18001f789  lea     r8, word_18003C290; lpLCData
0x18001f790  mov     edx, 1009h; LCType
0x18001f795  mov     ecx, 400h; Locale
0x18001f79a  call    cs:__imp_SetLocaleInfoW
0x18001f7a0  lea     r8, word_18003C2A0; lpLCData
0x18001f7a7  mov     edx, 20h ; ' '; LCType
0x18001f7ac  mov     ecx, 400h; Locale
0x18001f7b1  call    cs:__imp_SetLocaleInfoW
0x18001f7b7  lea     r8, word_18003C340; lpLCData
0x18001f7be  mov     edx, 1Fh; LCType
0x18001f7c3  mov     ecx, 400h; Locale
0x18001f7c8  call    cs:__imp_SetLocaleInfoW
0x18001f7ce  lea     r8, word_18003C3E4; lpLCData
0x18001f7d5  mov     edx, 100Ch; LCType
0x18001f7da  mov     ecx, 400h; Locale
0x18001f7df  call    cs:__imp_SetLocaleInfoW
0x18001f7e5  call    ?Currency_RestoreValues@@YAXXZ; Currency_RestoreValues(void)
0x18001f7ea  call    ?Time_RestoreValues@@YAXXZ; Time_RestoreValues(void)
0x18001f7ef  call    ?Number_RestoreValues@@YAXXZ; Number_RestoreValues(void)
0x18001f7f4  call    ?Region_RevertTempDigitSubst@@YAXXZ; Region_RevertTempDigitSubst(void)
0x18001f7f9  mov     ecx, cs:?RegUserLocaleIndex@@3KA; ulong RegUserLocaleIndex
0x18001f7ff  mov     edx, 4
0x18001f804  mov     rax, cs:?g_localeInfo@@3PEAPEAULocaleInfo@@EA; LocaleInfo * * g_localeInfo
0x18001f80b  mov     rcx, [rax+rcx*8]
0x18001f80f  mov     rcx, [rcx+8]
0x18001f813  call    cs:__imp_NlsUpdateLocale
0x18001f819  mov     rcx, rbx; hCursor
0x18001f81c  call    cs:__imp_SetCursor
0x18001f822  mov     eax, 1
0x18001f827  add     rsp, 20h
0x18001f82b  pop     rbx
0x18001f82c  retn
```
