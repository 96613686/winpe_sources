# Currency_SetGroupingValues(HWND__ *)

- ea: `0x180010024`
- end: `0x180010400`
- name: `?Currency_SetGroupingValues@@YAXPEAUHWND__@@@Z`
- size: `988`
- prototype: `void __fastcall(HWND)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180010408`

## callees

- `0x180010024`
- `0x18002a112`
- `0x18002a150`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoEx` at `0x1800100be`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoEx` at `0x180010230`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoEx` at `0x1800100be`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoEx` at `0x180010230`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180010253`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001027f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800102a3`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800102c7`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800102eb`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180010327`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180010253`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001027f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800102a3`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800102c7`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800102eb`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180010327`
- `api-ms-win-core-localization-l2-1-0!GetCurrencyFormatEx` at `0x180010101`
- `api-ms-win-core-localization-l2-1-0!GetCurrencyFormatEx` at `0x180010159`
- `api-ms-win-core-localization-l2-1-0!GetCurrencyFormatEx` at `0x1800101a7`
- `api-ms-win-core-localization-l2-1-0!GetCurrencyFormatEx` at `0x1800101f5`
- `api-ms-win-core-localization-l2-1-0!GetCurrencyFormatEx` at `0x180010378`
- `api-ms-win-core-localization-l2-1-0!GetCurrencyFormatEx` at `0x180010101`
- `api-ms-win-core-localization-l2-1-0!GetCurrencyFormatEx` at `0x180010159`
- `api-ms-win-core-localization-l2-1-0!GetCurrencyFormatEx` at `0x1800101a7`
- `api-ms-win-core-localization-l2-1-0!GetCurrencyFormatEx` at `0x1800101f5`
- `api-ms-win-core-localization-l2-1-0!GetCurrencyFormatEx` at `0x180010378`
- `USER32!GetDlgItem` at `0x180010055`
- `USER32!GetDlgItem` at `0x180010055`
- `USER32!SendMessageW` at `0x18001011e`
- `USER32!SendMessageW` at `0x18001016c`
- `USER32!SendMessageW` at `0x1800101ba`
- `USER32!SendMessageW` at `0x180010208`
- `USER32!SendMessageW` at `0x18001038f`
- `USER32!SendMessageW` at `0x1800103ad`
- `USER32!SendMessageW` at `0x1800103d2`
- `USER32!SendMessageW` at `0x18001011e`
- `USER32!SendMessageW` at `0x18001016c`
- `USER32!SendMessageW` at `0x1800101ba`
- `USER32!SendMessageW` at `0x180010208`
- `USER32!SendMessageW` at `0x18001038f`
- `USER32!SendMessageW` at `0x1800103ad`
- `USER32!SendMessageW` at `0x1800103d2`

## pseudocode

```c
void __fastcall Currency_SetGroupingValues(HWND a1)
{
  HWND DlgItem; // rdi
  int v2; // ebx
  WCHAR v3; // cx
  int v4; // eax
  CURRENCYFMTW Format; // [rsp+30h] [rbp-99h] BYREF
  WCHAR LCData[8]; // [rsp+60h] [rbp-69h] BYREF
  WCHAR CurrencyStr; // [rsp+70h] [rbp-59h] BYREF
  WCHAR String1[63]; // [rsp+72h] [rbp-57h] BYREF

  *(_QWORD *)&Format.Grouping = 0;
  DlgItem = GetDlgItem(a1, 1074);
  memset_0(&CurrencyStr, 0, 0x80u);
  Format.lpDecimalSep = (LPWSTR)&LocaleName;
  Format.lpCurrencySymbol = (LPWSTR)&LocaleName;
  *(_QWORD *)LCData = 0;
  Format.lpThousandSep = LCData;
  *(_QWORD *)&Format.NumDigits = 0;
  *(_QWORD *)&Format.NegativeOrder = 0;
  GetLocaleInfoEx(*(LPCWSTR *)(*((_QWORD *)g_localeInfo + UserLocaleIndex) + 8LL), 0x17u, LCData, 4);
  GetCurrencyFormatEx(
    *(LPCWSTR *)(*((_QWORD *)g_localeInfo + UserLocaleIndex) + 8LL),
    0,
    L"123456789",
    &Format,
    &CurrencyStr,
    64);
  SendMessageW(DlgItem, 0x14Au, 0xFFFFFFFFFFFFFFFFuLL, (LPARAM)&CurrencyStr);
  Format.Grouping = 3;
  GetCurrencyFormatEx(
    *(LPCWSTR *)(*((_QWORD *)g_localeInfo + UserLocaleIndex) + 8LL),
    0,
    L"123456789",
    &Format,
    &CurrencyStr,
    64);
  SendMessageW(DlgItem, 0x14Au, 0xFFFFFFFFFFFFFFFFuLL, (LPARAM)&CurrencyStr);
  Format.Grouping = 30;
  GetCurrencyFormatEx(
    *(LPCWSTR *)(*((_QWORD *)g_localeInfo + UserLocaleIndex) + 8LL),
    0,
    L"123456789",
    &Format,
    &CurrencyStr,
    64);
  SendMessageW(DlgItem, 0x14Au, 0xFFFFFFFFFFFFFFFFuLL, (LPARAM)&CurrencyStr);
  Format.Grouping = 32;
  GetCurrencyFormatEx(
    *(LPCWSTR *)(*((_QWORD *)g_localeInfo + UserLocaleIndex) + 8LL),
    0,
    L"123456789",
    &Format,
    &CurrencyStr,
    64);
  SendMessageW(DlgItem, 0x14Au, 0xFFFFFFFFFFFFFFFFuLL, (LPARAM)&CurrencyStr);
  v2 = 0;
  if ( GetLocaleInfoEx(*(LPCWSTR *)(*((_QWORD *)g_localeInfo + UserLocaleIndex) + 8LL), 0x18u, &CurrencyStr, 64) )
  {
    if ( CompareStringOrdinal(&CurrencyStr, -1, L"3;0", -1, 0) == 2 )
    {
      v2 = 1;
    }
    else
    {
      if ( CompareStringOrdinal(&CurrencyStr, -1, L"3", -1, 0) == 2
        || CompareStringOrdinal(&CurrencyStr, -1, L"3;0;0", -1, 0) == 2 )
      {
        v2 = 2;
        goto LABEL_18;
      }
      if ( CompareStringOrdinal(&CurrencyStr, -1, L"3;2", -1, 0) == 2
        || CompareStringOrdinal(&CurrencyStr, -1, L"3;2;0", -1, 0) == 2 )
      {
        v2 = 3;
        goto LABEL_18;
      }
      v3 = CurrencyStr;
      if ( (unsigned __int16)(CurrencyStr - 49) <= 8u )
      {
        if ( String1[0] )
        {
          if ( CompareStringOrdinal(String1, -1, L";0", -1, 0) != 2 )
            goto LABEL_18;
          v3 = CurrencyStr;
        }
        Format.Grouping = v3 - 48;
        if ( GetCurrencyFormatEx(
               *(LPCWSTR *)(*((_QWORD *)g_localeInfo + UserLocaleIndex) + 8LL),
               0,
               L"123456789",
               &Format,
               &CurrencyStr,
               64) )
        {
          v4 = SendMessageW(DlgItem, 0x14Au, 0xFFFFFFFFFFFFFFFFuLL, (LPARAM)&CurrencyStr);
          v2 = v4;
          if ( v4 == -1 )
            v2 = 0;
          else
            SendMessageW(DlgItem, 0x151u, v4, Format.Grouping);
        }
      }
    }
  }
LABEL_18:
  SendMessageW(DlgItem, 0x14Eu, v2, 0);
}

```

## disassembly

```asm
0x180010024  mov     [rsp-8+arg_8], rbx
0x180010029  mov     [rsp-8+arg_10], rsi
0x18001002e  push    rbp
0x18001002f  push    rdi
0x180010030  push    r13
0x180010032  push    r14
0x180010034  push    r15
0x180010036  lea     rbp, [rsp-37h]
0x18001003b  sub     rsp, 100h
0x180010042  mov     rax, cs:__security_cookie
0x180010049  xor     rax, rsp
0x18001004c  mov     [rbp+57h+var_30], rax
0x180010050  mov     edx, 432h; nIDDlgItem
0x180010055  call    cs:__imp_GetDlgItem
0x18001005b  xor     r14d, r14d
0x18001005e  lea     rcx, [rbp+57h+CurrencyStr]; void *
0x180010062  xor     edx, edx; Val
0x180010064  mov     qword ptr [rsp+120h+Format.Grouping], r14
0x180010069  mov     r8d, 80h; Size
0x18001006f  mov     rdi, rax
0x180010072  call    memset_0
0x180010077  mov     ecx, cs:?UserLocaleIndex@@3KA; ulong UserLocaleIndex
0x18001007d  lea     rax, LocaleName
0x180010084  mov     [rsp+120h+Format.lpDecimalSep], rax
0x180010089  lea     r9d, [r14+4]; cchData
0x18001008d  mov     [rbp+57h+Format.lpCurrencySymbol], rax
0x180010091  lea     r8, [rbp+57h+LCData]; lpLCData
0x180010095  mov     qword ptr [rbp+57h+LCData], r14
0x180010099  lea     rax, [rbp+57h+LCData]
0x18001009d  mov     [rsp+120h+Format.lpThousandSep], rax
0x1800100a2  lea     edx, [r14+17h]; LCType
0x1800100a6  mov     rax, cs:?g_localeInfo@@3PEAPEAULocaleInfo@@EA; LocaleInfo * * g_localeInfo
0x1800100ad  mov     qword ptr [rsp+120h+Format.NumDigits], r14
0x1800100b2  mov     qword ptr [rbp+57h+Format.NegativeOrder], r14
0x1800100b6  mov     rcx, [rax+rcx*8]
0x1800100ba  mov     rcx, [rcx+8]; lpLocaleName
0x1800100be  call    cs:__imp_GetLocaleInfoEx
0x1800100c4  mov     rax, cs:?g_localeInfo@@3PEAPEAULocaleInfo@@EA; LocaleInfo * * g_localeInfo
0x1800100cb  lea     r15d, [r14+40h]
0x1800100cf  mov     ecx, cs:?UserLocaleIndex@@3KA; ulong UserLocaleIndex
0x1800100d5  lea     rbx, a123456789; "123456789"
0x1800100dc  mov     [rsp+120h+Format.Grouping], r14d
0x1800100e1  lea     r9, [rsp+120h+Format]; lpFormat
0x1800100e6  mov     [rsp+120h+cchCurrency], r15d; cchCurrency
0x1800100eb  mov     r8, rbx; lpValue
0x1800100ee  xor     edx, edx; dwFlags
0x1800100f0  mov     rcx, [rax+rcx*8]
0x1800100f4  lea     rax, [rbp+57h+CurrencyStr]
0x1800100f8  mov     [rsp+120h+lpCurrencyStr], rax; lpCurrencyStr
0x1800100fd  mov     rcx, [rcx+8]; lpLocaleName
0x180010101  call    cs:__imp_GetCurrencyFormatEx
0x180010107  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18001010b  lea     r9, [rbp+57h+CurrencyStr]; lParam
0x18001010f  mov     r13d, 14Ah
0x180010115  mov     r8, rsi; wParam
0x180010118  mov     edx, r13d; Msg
0x18001011b  mov     rcx, rdi; hWnd
0x18001011e  call    cs:__imp_SendMessageW
0x180010124  mov     rax, cs:?g_localeInfo@@3PEAPEAULocaleInfo@@EA; LocaleInfo * * g_localeInfo
0x18001012b  lea     r9, [rsp+120h+Format]; lpFormat
0x180010130  mov     ecx, cs:?UserLocaleIndex@@3KA; ulong UserLocaleIndex
0x180010136  mov     r8, rbx; lpValue
0x180010139  mov     [rsp+120h+Format.Grouping], 3
0x180010141  xor     edx, edx; dwFlags
0x180010143  mov     [rsp+120h+cchCurrency], r15d; cchCurrency
0x180010148  mov     rcx, [rax+rcx*8]
0x18001014c  lea     rax, [rbp+57h+CurrencyStr]
0x180010150  mov     [rsp+120h+lpCurrencyStr], rax; lpCurrencyStr
0x180010155  mov     rcx, [rcx+8]; lpLocaleName
0x180010159  call    cs:__imp_GetCurrencyFormatEx
0x18001015f  lea     r9, [rbp+57h+CurrencyStr]; lParam
0x180010163  mov     r8, rsi; wParam
0x180010166  mov     edx, r13d; Msg
0x180010169  mov     rcx, rdi; hWnd
0x18001016c  call    cs:__imp_SendMessageW
0x180010172  mov     rax, cs:?g_localeInfo@@3PEAPEAULocaleInfo@@EA; LocaleInfo * * g_localeInfo
0x180010179  lea     r9, [rsp+120h+Format]; lpFormat
0x18001017e  mov     ecx, cs:?UserLocaleIndex@@3KA; ulong UserLocaleIndex
0x180010184  mov     r8, rbx; lpValue
0x180010187  mov     [rsp+120h+Format.Grouping], 1Eh
0x18001018f  xor     edx, edx; dwFlags
0x180010191  mov     [rsp+120h+cchCurrency], r15d; cchCurrency
0x180010196  mov     rcx, [rax+rcx*8]
0x18001019a  lea     rax, [rbp+57h+CurrencyStr]
0x18001019e  mov     [rsp+120h+lpCurrencyStr], rax; lpCurrencyStr
0x1800101a3  mov     rcx, [rcx+8]; lpLocaleName
0x1800101a7  call    cs:__imp_GetCurrencyFormatEx
0x1800101ad  lea     r9, [rbp+57h+CurrencyStr]; lParam
0x1800101b1  mov     r8, rsi; wParam
0x1800101b4  mov     edx, r13d; Msg
0x1800101b7  mov     rcx, rdi; hWnd
0x1800101ba  call    cs:__imp_SendMessageW
0x1800101c0  mov     [rsp+120h+Format.Grouping], 20h ; ' '
0x1800101c8  mov     rax, cs:?g_localeInfo@@3PEAPEAULocaleInfo@@EA; LocaleInfo * * g_localeInfo
0x1800101cf  lea     r9, [rsp+120h+Format]; lpFormat
0x1800101d4  mov     ecx, cs:?UserLocaleIndex@@3KA; ulong UserLocaleIndex
0x1800101da  mov     r8, rbx; lpValue
0x1800101dd  mov     [rsp+120h+cchCurrency], r15d; cchCurrency
0x1800101e2  xor     edx, edx; dwFlags
0x1800101e4  mov     rcx, [rax+rcx*8]
0x1800101e8  lea     rax, [rbp+57h+CurrencyStr]
0x1800101ec  mov     [rsp+120h+lpCurrencyStr], rax; lpCurrencyStr
0x1800101f1  mov     rcx, [rcx+8]; lpLocaleName
0x1800101f5  call    cs:__imp_GetCurrencyFormatEx
0x1800101fb  lea     r9, [rbp+57h+CurrencyStr]; lParam
0x1800101ff  mov     r8, rsi; wParam
0x180010202  mov     edx, r13d; Msg
0x180010205  mov     rcx, rdi; hWnd
0x180010208  call    cs:__imp_SendMessageW
0x18001020e  mov     ecx, cs:?UserLocaleIndex@@3KA; ulong UserLocaleIndex
0x180010214  lea     r8, [rbp+57h+CurrencyStr]; lpLCData
0x180010218  mov     rax, cs:?g_localeInfo@@3PEAPEAULocaleInfo@@EA; LocaleInfo * * g_localeInfo
0x18001021f  lea     edx, [rsi+19h]; LCType
0x180010222  mov     r9d, r15d; cchData
0x180010225  mov     ebx, r14d
0x180010228  mov     rcx, [rax+rcx*8]
0x18001022c  mov     rcx, [rcx+8]; lpLocaleName
0x180010230  call    cs:__imp_GetLocaleInfoEx
0x180010236  test    eax, eax
0x180010238  jz      loc_1800103C4
0x18001023e  mov     r9d, esi; cchCount2
0x180010241  mov     dword ptr [rsp+120h+lpCurrencyStr], r14d; bIgnoreCase
0x180010246  lea     r8, a30; "3;0"
0x18001024d  mov     edx, esi; cchCount1
0x18001024f  lea     rcx, [rbp+57h+CurrencyStr]; lpString1
0x180010253  call    cs:__imp_CompareStringOrdinal
0x180010259  lea     r15d, [r14+2]
0x18001025d  cmp     eax, r15d
0x180010260  jnz     short loc_18001026A
0x180010262  lea     ebx, [rsi+2]
0x180010265  jmp     loc_1800103C4
0x18001026a  mov     r9d, esi; cchCount2
0x18001026d  mov     dword ptr [rsp+120h+lpCurrencyStr], r14d; bIgnoreCase
0x180010272  lea     r8, a3; "3"
0x180010279  mov     edx, esi; cchCount1
0x18001027b  lea     rcx, [rbp+57h+CurrencyStr]; lpString1
0x18001027f  call    cs:__imp_CompareStringOrdinal
0x180010285  cmp     eax, r15d
0x180010288  jz      loc_1800103C1
0x18001028e  mov     r9d, esi; cchCount2
0x180010291  mov     dword ptr [rsp+120h+lpCurrencyStr], r14d; bIgnoreCase
0x180010296  lea     r8, a300; "3;0;0"
0x18001029d  mov     edx, esi; cchCount1
0x18001029f  lea     rcx, [rbp+57h+CurrencyStr]; lpString1
0x1800102a3  call    cs:__imp_CompareStringOrdinal
0x1800102a9  cmp     eax, r15d
0x1800102ac  jz      loc_1800103C1
0x1800102b2  mov     r9d, esi; cchCount2
0x1800102b5  mov     dword ptr [rsp+120h+lpCurrencyStr], r14d; bIgnoreCase
0x1800102ba  lea     r8, a32; "3;2"
0x1800102c1  mov     edx, esi; cchCount1
0x1800102c3  lea     rcx, [rbp+57h+CurrencyStr]; lpString1
0x1800102c7  call    cs:__imp_CompareStringOrdinal
0x1800102cd  cmp     eax, r15d
0x1800102d0  jz      loc_1800103BA
0x1800102d6  mov     r9d, esi; cchCount2
0x1800102d9  mov     dword ptr [rsp+120h+lpCurrencyStr], r14d; bIgnoreCase
0x1800102de  lea     r8, a320; "3;2;0"
0x1800102e5  mov     edx, esi; cchCount1
0x1800102e7  lea     rcx, [rbp+57h+CurrencyStr]; lpString1
0x1800102eb  call    cs:__imp_CompareStringOrdinal
0x1800102f1  cmp     eax, r15d
0x1800102f4  jz      loc_1800103BA
0x1800102fa  movzx   ecx, [rbp+57h+CurrencyStr]
0x1800102fe  lea     eax, [rcx-31h]
0x180010301  cmp     ax, 8
0x180010305  ja      loc_1800103C4
0x18001030b  cmp     [rbp+57h+String1], r14w
0x180010310  jz      short loc_18001033A
0x180010312  mov     r9d, esi; cchCount2
0x180010315  mov     dword ptr [rsp+120h+lpCurrencyStr], r14d; bIgnoreCase
0x18001031a  lea     r8, a0_0; ";0"
0x180010321  mov     edx, esi; cchCount1
0x180010323  lea     rcx, [rbp+57h+String1]; lpString1
0x180010327  call    cs:__imp_CompareStringOrdinal
0x18001032d  cmp     eax, r15d
0x180010330  jnz     loc_1800103C4
0x180010336  movzx   ecx, [rbp+57h+CurrencyStr]
0x18001033a  movzx   eax, cx
0x18001033d  lea     r9, [rsp+120h+Format]; lpFormat
0x180010342  mov     ecx, cs:?UserLocaleIndex@@3KA; ulong UserLocaleIndex
0x180010348  lea     r8, a123456789; "123456789"
0x18001034f  sub     eax, 30h ; '0'
0x180010352  mov     [rsp+120h+cchCurrency], 40h ; '@'; cchCurrency
0x18001035a  mov     [rsp+120h+Format.Grouping], eax
0x18001035e  xor     edx, edx; dwFlags
0x180010360  mov     rax, cs:?g_localeInfo@@3PEAPEAULocaleInfo@@EA; LocaleInfo * * g_localeInfo
0x180010367  mov     rcx, [rax+rcx*8]
0x18001036b  lea     rax, [rbp+57h+CurrencyStr]
0x18001036f  mov     [rsp+120h+lpCurrencyStr], rax; lpCurrencyStr
0x180010374  mov     rcx, [rcx+8]; lpLocaleName
0x180010378  call    cs:__imp_GetCurrencyFormatEx
0x18001037e  test    eax, eax
0x180010380  jz      short loc_1800103C4
0x180010382  lea     r9, [rbp+57h+CurrencyStr]; lParam
0x180010386  mov     r8, rsi; wParam
0x180010389  mov     edx, r13d; Msg
0x18001038c  mov     rcx, rdi; hWnd
0x18001038f  call    cs:__imp_SendMessageW
0x180010395  mov     rbx, rax
0x180010398  cmp     eax, 0FFFFFFFFh
0x18001039b  jz      short loc_1800103B5
0x18001039d  mov     r9d, [rsp+120h+Format.Grouping]; lParam
0x1800103a2  mov     edx, 151h; Msg
0x1800103a7  movsxd  r8, eax; wParam
0x1800103aa  mov     rcx, rdi; hWnd
0x1800103ad  call    cs:__imp_SendMessageW
0x1800103b3  jmp     short loc_1800103C4
0x1800103b5  mov     ebx, r14d
0x1800103b8  jmp     short loc_1800103C4
0x1800103ba  mov     ebx, 3
0x1800103bf  jmp     short loc_1800103C4
0x1800103c1  mov     ebx, r15d
0x1800103c4  movsxd  r8, ebx; wParam
0x1800103c7  xor     r9d, r9d; lParam
0x1800103ca  mov     edx, 14Eh; Msg
0x1800103cf  mov     rcx, rdi; hWnd
0x1800103d2  call    cs:__imp_SendMessageW
0x1800103d8  mov     rcx, [rbp+57h+var_30]
0x1800103dc  xor     rcx, rsp; StackCookie
0x1800103df  call    __security_check_cookie
0x1800103e4  lea     r11, [rsp+120h+var_20]
0x1800103ec  mov     rbx, [r11+38h]
0x1800103f0  mov     rsi, [r11+40h]
0x1800103f4  mov     rsp, r11
0x1800103f7  pop     r15
0x1800103f9  pop     r14
0x1800103fb  pop     r13
0x1800103fd  pop     rdi
0x1800103fe  pop     rbp
0x1800103ff  retn
```
