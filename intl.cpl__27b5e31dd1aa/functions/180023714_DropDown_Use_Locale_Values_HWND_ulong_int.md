# DropDown_Use_Locale_Values(HWND__ *,ulong,int)

- ea: `0x180023714`
- end: `0x180023ac5`
- name: `?DropDown_Use_Locale_Values@@YAXPEAUHWND__@@KH@Z`
- size: `945`
- prototype: `void __fastcall(HWND hWnd, LCTYPE LCType, int nIDDlgItem)`
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180010408`
- `0x18001b3f0`
- `0x1800211d4`
- `0x180021afc`

## callees

- `0x180023714`
- `0x18002a150`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoEx` at `0x18002377a`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoEx` at `0x1800237da`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoEx` at `0x180023863`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoEx` at `0x180023936`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoEx` at `0x18002377a`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoEx` at `0x1800237da`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoEx` at `0x180023863`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoEx` at `0x180023936`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x180023820`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x1800238b0`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x1800238fd`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x180023820`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x1800238b0`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x1800238fd`
- `USER32!GetDlgItem` at `0x18002374c`
- `USER32!GetDlgItem` at `0x18002374c`
- `USER32!SendMessageW` at `0x1800237a3`
- `USER32!SendMessageW` at `0x1800237b6`
- `USER32!SendMessageW` at `0x180023838`
- `USER32!SendMessageW` at `0x18002394e`
- `USER32!SendMessageW` at `0x180023962`
- `USER32!SendMessageW` at `0x1800239b8`
- `USER32!SendMessageW` at `0x1800239d4`
- `USER32!SendMessageW` at `0x180023a02`
- `USER32!SendMessageW` at `0x180023a31`
- `USER32!SendMessageW` at `0x180023a4c`
- `USER32!SendMessageW` at `0x180023a72`
- `USER32!SendMessageW` at `0x180023a8e`
- `USER32!SendMessageW` at `0x1800237a3`
- `USER32!SendMessageW` at `0x1800237b6`
- `USER32!SendMessageW` at `0x180023838`
- `USER32!SendMessageW` at `0x18002394e`
- `USER32!SendMessageW` at `0x180023962`
- `USER32!SendMessageW` at `0x1800239b8`
- `USER32!SendMessageW` at `0x1800239d4`
- `USER32!SendMessageW` at `0x180023a02`
- `USER32!SendMessageW` at `0x180023a31`
- `USER32!SendMessageW` at `0x180023a4c`
- `USER32!SendMessageW` at `0x180023a72`
- `USER32!SendMessageW` at `0x180023a8e`
- `USER32!MessageBoxW` at `0x180023981`
- `USER32!MessageBoxW` at `0x180023981`

## pseudocode

```c
void __fastcall DropDown_Use_Locale_Values(HWND hWnd, LCTYPE LCType, int nIDDlgItem)
{
  HWND DlgItem; // rbx
  int v6; // eax
  WCHAR *v7; // r9
  WPARAM v8; // r8
  UINT v9; // edx
  unsigned int i; // esi
  LPARAM v11; // r9
  unsigned int j; // edi
  WCHAR LCData[128]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR String1[128]; // [rsp+150h] [rbp+50h] BYREF
  WCHAR v15[128]; // [rsp+250h] [rbp+150h] BYREF

  DlgItem = GetDlgItem(hWnd, nIDDlgItem);
  if ( GetLocaleInfoEx(*(LPCWSTR *)(*((_QWORD *)g_localeInfo + UserLocaleIndex) + 8LL), LCType, LCData, 128) )
  {
    v6 = SendMessageW(DlgItem, 0x14Au, 0xFFFFFFFFFFFFFFFFuLL, (LPARAM)LCData);
    SendMessageW(DlgItem, 0x14Eu, v6, 0);
    if ( GetLocaleInfoEx(*(LPCWSTR *)(*((_QWORD *)g_localeInfo + SysLocaleIndex) + 8LL), LCType, String1, 128)
      && CompareStringEx(
           *(LPCWSTR *)(*((_QWORD *)g_localeInfo + UserLocaleIndex) + 8LL),
           0,
           String1,
           -1,
           LCData,
           -1,
           0,
           0,
           0) != 2 )
    {
      SendMessageW(DlgItem, 0x14Au, 0xFFFFFFFFFFFFFFFFuLL, (LPARAM)String1);
    }
    if ( GetLocaleInfoEx(*(LPCWSTR *)(*((_QWORD *)g_localeInfo + UserLocaleIndex) + 8LL), LCType | 0x80000000, v15, 128)
      && CompareStringEx(
           *(LPCWSTR *)(*((_QWORD *)g_localeInfo + UserLocaleIndex) + 8LL),
           0,
           v15,
           -1,
           LCData,
           -1,
           0,
           0,
           0) != 2
      && CompareStringEx(
           *(LPCWSTR *)(*((_QWORD *)g_localeInfo + UserLocaleIndex) + 8LL),
           0,
           v15,
           -1,
           String1,
           -1,
           0,
           0,
           0) != 2 )
    {
      v7 = v15;
      v8 = -1;
      v9 = 330;
LABEL_11:
      SendMessageW(DlgItem, v9, v8, (LPARAM)v7);
    }
  }
  else
  {
    if ( GetLocaleInfoEx(*(LPCWSTR *)(*((_QWORD *)g_localeInfo + UserLocaleIndex) + 8LL), LCType, LCData, 128) )
    {
      v8 = (int)SendMessageW(DlgItem, 0x14Au, 0xFFFFFFFFFFFFFFFFuLL, (LPARAM)LCData);
      v7 = 0;
      v9 = 334;
      goto LABEL_11;
    }
    MessageBoxW(hWnd, &g_szLocaleGetError, &g_szLocaleCustomName, 0x40u);
  }
  if ( ((LCType - 14) & 0xFFFFFFF6) == 0 )
  {
    for ( i = 0; i < 4; ++i )
    {
      if ( (unsigned int)SendMessageW(
                           DlgItem,
                           0x158u,
                           0xFFFFFFFFFFFFFFFFuLL,
                           (LPARAM)(&pDecimalAndThousandSeparators)[i]) == -1 )
        SendMessageW(DlgItem, 0x14Au, 0xFFFFFFFFFFFFFFFFuLL, (LPARAM)(&pDecimalAndThousandSeparators)[i]);
    }
  }
  switch ( LCType )
  {
    case 0x28u:
      if ( (unsigned int)SendMessageW(DlgItem, 0x158u, 0xFFFFFFFFFFFFFFFFuLL, pAMSymbols) != -1 )
        return;
      v11 = pAMSymbols;
LABEL_24:
      SendMessageW(DlgItem, 0x14Au, 0xFFFFFFFFFFFFFFFFuLL, v11);
      return;
    case 0x29u:
      if ( (unsigned int)SendMessageW(DlgItem, 0x158u, 0xFFFFFFFFFFFFFFFFuLL, pPMSymbols) != -1 )
        return;
      v11 = pPMSymbols;
      goto LABEL_24;
    case 0x14u:
      for ( j = 0; j < 2; ++j )
      {
        if ( (unsigned int)SendMessageW(DlgItem, 0x158u, 0xFFFFFFFFFFFFFFFFuLL, (LPARAM)(&pCurrencySymbols)[j]) == -1 )
          SendMessageW(DlgItem, 0x14Au, 0xFFFFFFFFFFFFFFFFuLL, (LPARAM)(&pCurrencySymbols)[j]);
      }
      break;
  }
}

```

## disassembly

```asm
0x180023714  mov     [rsp-8+arg_18], rbx
0x180023719  push    rbp
0x18002371a  push    rsi
0x18002371b  push    rdi
0x18002371c  push    r12
0x18002371e  push    r13
0x180023720  push    r14
0x180023722  push    r15
0x180023724  lea     rbp, [rsp-260h]
0x18002372c  sub     rsp, 360h
0x180023733  mov     rax, cs:__security_cookie
0x18002373a  xor     rax, rsp
0x18002373d  mov     [rbp+290h+var_40], rax
0x180023744  mov     edi, edx
0x180023746  mov     rsi, rcx
0x180023749  mov     edx, r8d; nIDDlgItem
0x18002374c  call    cs:__imp_GetDlgItem
0x180023752  mov     edx, cs:?UserLocaleIndex@@3KA; ulong UserLocaleIndex
0x180023758  lea     r8, [rsp+390h+LCData]; lpLCData
0x18002375d  mov     rcx, cs:?g_localeInfo@@3PEAPEAULocaleInfo@@EA; LocaleInfo * * g_localeInfo
0x180023764  mov     r14d, 80h
0x18002376a  mov     r9d, r14d; cchData
0x18002376d  mov     rbx, rax
0x180023770  mov     rcx, [rcx+rdx*8]
0x180023774  mov     edx, edi; LCType
0x180023776  mov     rcx, [rcx+8]; lpLocaleName
0x18002377a  call    cs:__imp_GetLocaleInfoEx
0x180023780  or      r15, 0FFFFFFFFFFFFFFFFh
0x180023784  xor     r12d, r12d
0x180023787  mov     r13d, 14Ah
0x18002378d  test    eax, eax
0x18002378f  jz      loc_180023917
0x180023795  lea     r9, [rsp+390h+LCData]; lParam
0x18002379a  mov     r8, r15; wParam
0x18002379d  mov     edx, r13d; Msg
0x1800237a0  mov     rcx, rbx; hWnd
0x1800237a3  call    cs:__imp_SendMessageW
0x1800237a9  movsxd  r8, eax; wParam
0x1800237ac  xor     r9d, r9d; lParam
0x1800237af  lea     edx, [r13+4]; Msg
0x1800237b3  mov     rcx, rbx; hWnd
0x1800237b6  call    cs:__imp_SendMessageW
0x1800237bc  mov     ecx, cs:?SysLocaleIndex@@3KA; ulong SysLocaleIndex
0x1800237c2  lea     r8, [rbp+290h+String1]; lpLCData
0x1800237c6  mov     rax, cs:?g_localeInfo@@3PEAPEAULocaleInfo@@EA; LocaleInfo * * g_localeInfo
0x1800237cd  mov     r9d, r14d; cchData
0x1800237d0  mov     edx, edi; LCType
0x1800237d2  mov     rcx, [rax+rcx*8]
0x1800237d6  mov     rcx, [rcx+8]; lpLocaleName
0x1800237da  call    cs:__imp_GetLocaleInfoEx
0x1800237e0  test    eax, eax
0x1800237e2  jz      short loc_18002383E
0x1800237e4  mov     rax, cs:?g_localeInfo@@3PEAPEAULocaleInfo@@EA; LocaleInfo * * g_localeInfo
0x1800237eb  lea     r8, [rbp+290h+String1]; lpString1
0x1800237ef  mov     ecx, cs:?UserLocaleIndex@@3KA; ulong UserLocaleIndex
0x1800237f5  mov     r9d, r15d; cchCount1
0x1800237f8  mov     [rsp+390h+lParam], r12; lParam
0x1800237fd  xor     edx, edx; dwCmpFlags
0x1800237ff  mov     [rsp+390h+lpReserved], r12; lpReserved
0x180023804  mov     [rsp+390h+lpVersionInformation], r12; lpVersionInformation
0x180023809  mov     rcx, [rax+rcx*8]
0x18002380d  lea     rax, [rsp+390h+LCData]
0x180023812  mov     [rsp+390h+cchCount2], r15d; cchCount2
0x180023817  mov     [rsp+390h+lpString2], rax; lpString2
0x18002381c  mov     rcx, [rcx+8]; lpLocaleName
0x180023820  call    cs:__imp_CompareStringEx
0x180023826  cmp     eax, 2
0x180023829  jz      short loc_18002383E
0x18002382b  lea     r9, [rbp+290h+String1]; lParam
0x18002382f  mov     r8, r15; wParam
0x180023832  mov     edx, r13d; Msg
0x180023835  mov     rcx, rbx; hWnd
0x180023838  call    cs:__imp_SendMessageW
0x18002383e  mov     ecx, cs:?UserLocaleIndex@@3KA; ulong UserLocaleIndex
0x180023844  lea     r8, [rbp+290h+var_140]; lpLCData
0x18002384b  mov     rax, cs:?g_localeInfo@@3PEAPEAULocaleInfo@@EA; LocaleInfo * * g_localeInfo
0x180023852  mov     edx, edi
0x180023854  bts     edx, 1Fh; LCType
0x180023858  mov     r9d, r14d; cchData
0x18002385b  mov     rcx, [rax+rcx*8]
0x18002385f  mov     rcx, [rcx+8]; lpLocaleName
0x180023863  call    cs:__imp_GetLocaleInfoEx
0x180023869  test    eax, eax
0x18002386b  jz      loc_180023987
0x180023871  mov     rax, cs:?g_localeInfo@@3PEAPEAULocaleInfo@@EA; LocaleInfo * * g_localeInfo
0x180023878  lea     r8, [rbp+290h+var_140]; lpString1
0x18002387f  mov     ecx, cs:?UserLocaleIndex@@3KA; ulong UserLocaleIndex
0x180023885  mov     r9d, r15d; cchCount1
0x180023888  mov     [rsp+390h+lParam], r12; lParam
0x18002388d  xor     edx, edx; dwCmpFlags
0x18002388f  mov     [rsp+390h+lpReserved], r12; lpReserved
0x180023894  mov     [rsp+390h+lpVersionInformation], r12; lpVersionInformation
0x180023899  mov     rcx, [rax+rcx*8]
0x18002389d  lea     rax, [rsp+390h+LCData]
0x1800238a2  mov     [rsp+390h+cchCount2], r15d; cchCount2
0x1800238a7  mov     [rsp+390h+lpString2], rax; lpString2
0x1800238ac  mov     rcx, [rcx+8]; lpLocaleName
0x1800238b0  call    cs:__imp_CompareStringEx
0x1800238b6  cmp     eax, 2
0x1800238b9  jz      loc_180023987
0x1800238bf  mov     rax, cs:?g_localeInfo@@3PEAPEAULocaleInfo@@EA; LocaleInfo * * g_localeInfo
0x1800238c6  lea     r8, [rbp+290h+var_140]; lpString1
0x1800238cd  mov     ecx, cs:?UserLocaleIndex@@3KA; ulong UserLocaleIndex
0x1800238d3  mov     r9d, r15d; cchCount1
0x1800238d6  mov     [rsp+390h+lParam], r12; lParam
0x1800238db  xor     edx, edx; dwCmpFlags
0x1800238dd  mov     [rsp+390h+lpReserved], r12; lpReserved
0x1800238e2  mov     [rsp+390h+lpVersionInformation], r12; lpVersionInformation
0x1800238e7  mov     rcx, [rax+rcx*8]
0x1800238eb  lea     rax, [rbp+290h+String1]
0x1800238ef  mov     [rsp+390h+cchCount2], r15d; cchCount2
0x1800238f4  mov     [rsp+390h+lpString2], rax; lpString2
0x1800238f9  mov     rcx, [rcx+8]; lpLocaleName
0x1800238fd  call    cs:__imp_CompareStringEx
0x180023903  cmp     eax, 2
0x180023906  jz      short loc_180023987
0x180023908  lea     r9, [rbp+290h+var_140]
0x18002390f  mov     r8, r15
0x180023912  mov     edx, r13d
0x180023915  jmp     short loc_18002395F
0x180023917  mov     ecx, cs:?UserLocaleIndex@@3KA; ulong UserLocaleIndex
0x18002391d  lea     r8, [rsp+390h+LCData]; lpLCData
0x180023922  mov     rax, cs:?g_localeInfo@@3PEAPEAULocaleInfo@@EA; LocaleInfo * * g_localeInfo
0x180023929  mov     r9d, r14d; cchData
0x18002392c  mov     edx, edi; LCType
0x18002392e  mov     rcx, [rax+rcx*8]
0x180023932  mov     rcx, [rcx+8]; lpLocaleName
0x180023936  call    cs:__imp_GetLocaleInfoEx
0x18002393c  test    eax, eax
0x18002393e  jz      short loc_18002396A
0x180023940  lea     r9, [rsp+390h+LCData]; lParam
0x180023945  mov     r8, r15; wParam
0x180023948  mov     edx, r13d; Msg
0x18002394b  mov     rcx, rbx; hWnd
0x18002394e  call    cs:__imp_SendMessageW
0x180023954  movsxd  r8, eax; wParam
0x180023957  xor     r9d, r9d; lParam
0x18002395a  mov     edx, 14Eh; Msg
0x18002395f  mov     rcx, rbx; hWnd
0x180023962  call    cs:__imp_SendMessageW
0x180023968  jmp     short loc_180023987
0x18002396a  mov     r9d, 40h ; '@'; uType
0x180023970  lea     r8, ?g_szLocaleCustomName@@3PAGA; lpCaption
0x180023977  lea     rdx, ?g_szLocaleGetError@@3PAGA; lpText
0x18002397e  mov     rcx, rsi; hWnd
0x180023981  call    cs:__imp_MessageBoxW
0x180023987  lea     eax, [rdi-0Eh]
0x18002398a  lea     r14, cs:180000000h
0x180023991  test    eax, 0FFFFFFF6h
0x180023996  jnz     short loc_1800239EB
0x180023998  mov     esi, r12d
0x18002399b  lea     r12, cs:180000000h
0x1800239a2  movsxd  r14, esi
0x1800239a5  mov     r8, r15; wParam
0x1800239a8  mov     edx, 158h; Msg
0x1800239ad  mov     rcx, rbx; hWnd
0x1800239b0  mov     r9, ds:rva ?pDecimalAndThousandSeparators@@3PAPEAGA[r12+r14*8]; lParam
0x1800239b8  call    cs:__imp_SendMessageW
0x1800239be  cmp     eax, r15d
0x1800239c1  jnz     short loc_1800239DA
0x1800239c3  mov     r9, ds:rva ?pDecimalAndThousandSeparators@@3PAPEAGA[r12+r14*8]; lParam
0x1800239cb  mov     r8, r15; wParam
0x1800239ce  mov     edx, r13d; Msg
0x1800239d1  mov     rcx, rbx; hWnd
0x1800239d4  call    cs:__imp_SendMessageW
0x1800239da  inc     esi
0x1800239dc  cmp     esi, 4
0x1800239df  jb      short loc_1800239A2
0x1800239e1  xor     r12d, r12d
0x1800239e4  lea     r14, cs:180000000h
0x1800239eb  cmp     edi, 28h ; '('
0x1800239ee  jnz     short loc_180023A1A
0x1800239f0  mov     r9, cs:?pAMSymbols@@3PAPEAGA; lParam
0x1800239f7  mov     r8, r15; wParam
0x1800239fa  mov     edx, 158h; Msg
0x1800239ff  mov     rcx, rbx; hWnd
0x180023a02  call    cs:__imp_SendMessageW
0x180023a08  cmp     eax, r15d
0x180023a0b  jnz     loc_180023A9B
0x180023a11  mov     r9, cs:?pAMSymbols@@3PAPEAGA; ushort * near * pAMSymbols
0x180023a18  jmp     short loc_180023A43
0x180023a1a  cmp     edi, 29h ; ')'
0x180023a1d  jnz     short loc_180023A54
0x180023a1f  mov     r9, cs:?pPMSymbols@@3PAPEAGA; lParam
0x180023a26  mov     r8, r15; wParam
0x180023a29  mov     edx, 158h; Msg
0x180023a2e  mov     rcx, rbx; hWnd
0x180023a31  call    cs:__imp_SendMessageW
0x180023a37  cmp     eax, r15d
0x180023a3a  jnz     short loc_180023A9B
0x180023a3c  mov     r9, cs:?pPMSymbols@@3PAPEAGA; lParam
0x180023a43  mov     r8, r15; wParam
0x180023a46  mov     edx, r13d; Msg
0x180023a49  mov     rcx, rbx; hWnd
0x180023a4c  call    cs:__imp_SendMessageW
0x180023a52  jmp     short loc_180023A9B
0x180023a54  cmp     edi, 14h
0x180023a57  jnz     short loc_180023A9B
0x180023a59  mov     edi, r12d
0x180023a5c  movsxd  rsi, edi
0x180023a5f  mov     r8, r15; wParam
0x180023a62  mov     edx, 158h; Msg
0x180023a67  mov     rcx, rbx; hWnd
0x180023a6a  mov     r9, ds:rva ?pCurrencySymbols@@3PAPEAGA[r14+rsi*8]; lParam
0x180023a72  call    cs:__imp_SendMessageW
0x180023a78  cmp     eax, r15d
0x180023a7b  jnz     short loc_180023A94
0x180023a7d  mov     r9, ds:rva ?pCurrencySymbols@@3PAPEAGA[r14+rsi*8]; lParam
0x180023a85  mov     r8, r15; wParam
0x180023a88  mov     edx, r13d; Msg
0x180023a8b  mov     rcx, rbx; hWnd
0x180023a8e  call    cs:__imp_SendMessageW
0x180023a94  inc     edi
0x180023a96  cmp     edi, 2
0x180023a99  jb      short loc_180023A5C
0x180023a9b  mov     rcx, [rbp+290h+var_40]
0x180023aa2  xor     rcx, rsp; StackCookie
0x180023aa5  call    __security_check_cookie
0x180023aaa  mov     rbx, [rsp+390h+arg_18]
0x180023ab2  add     rsp, 360h
0x180023ab9  pop     r15
0x180023abb  pop     r14
0x180023abd  pop     r13
0x180023abf  pop     r12
0x180023ac1  pop     rdi
0x180023ac2  pop     rsi
0x180023ac3  pop     rbp
0x180023ac4  retn
```
